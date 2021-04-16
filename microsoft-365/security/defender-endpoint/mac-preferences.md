---
title: Definir preferências do Microsoft Defender para Ponto de Extremidade para Mac
description: Configure o Microsoft Defender para Ponto de Extremidade para Mac em organizações corporativas.
keywords: microsoft, defender, atp, mac, gerenciamento, preferências, enterprise, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d2bea469031e2c5932e859fbad7d442ebe4d34ed
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860914"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-macos"></a>Definir preferências para o Microsoft Defender para Ponto de Extremidade no macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade no macOS](microsoft-defender-endpoint-mac.md)

>[!IMPORTANT]
>Este artigo contém instruções sobre como definir preferências do Microsoft Defender para Endpoint no macOS em organizações corporativas. Para configurar o Microsoft Defender para Ponto de Extremidade no macOS usando a interface de linha de comando, consulte [Resources](mac-resources.md#configuring-from-the-command-line).

## <a name="summary"></a>Resumo

Em organizações corporativas, o Microsoft Defender para Ponto de Extremidade no macOS pode ser gerenciado por meio de um perfil de configuração implantado usando uma das várias ferramentas de gerenciamento. As preferências gerenciadas pela equipe de operações de segurança têm precedência sobre as preferências definidas localmente no dispositivo. Alterar as preferências definidas por meio do perfil de configuração exige privilégios escalonados e não está disponível para usuários sem permissões administrativas.

Este artigo descreve a estrutura do perfil de configuração, inclui um perfil recomendado que você pode usar para começar e fornece instruções sobre como implantar o perfil.

## <a name="configuration-profile-structure"></a>Estrutura de perfil de configuração

O perfil de configuração é um *arquivo .plist* que consiste em entradas identificadas por uma chave (que indica o nome da preferência), seguida por um valor, que depende da natureza da preferência. Os valores podem ser simples (como um valor numérico) ou complexos, como uma lista aninhada de preferências.

>[!CAUTION]
>O layout do perfil de configuração depende do console de gerenciamento que você está usando. As seções a seguir contêm exemplos de perfis de configuração para JAMF e Intune.

O nível superior do perfil de configuração inclui preferências e entradas para subáreas do Microsoft Defender para Ponto de Extremidade, que são explicadas com mais detalhes nas próximas seções.

### <a name="antivirus-engine-preferences"></a>Preferências do mecanismo antivírus

A *seção antivírusEngine* do perfil de configuração é usada para gerenciar as preferências do componente antivírus do Microsoft Defender para Ponto de Extremidade.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | antivirusEngine |
| **Tipo de dados** | Dicionário (preferência aninhada) |
| **Comentário** | Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário. |

#### <a name="enable--disable-real-time-protection"></a>Habilitar/desabilitar a proteção em tempo real

Especifique se é necessário habilitar a proteção em tempo real, que verifica os arquivos conforme eles são acessados.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | enableRealTimeProtection |
| **Tipo de dados** | Booliano |
| **Valores possíveis** | true (padrão) <br/> falso |

#### <a name="enable--disable-passive-mode"></a>Habilitar/desabilitar o modo passivo

Especifique se o mecanismo antivírus é executado no modo passivo. O modo passivo tem as seguintes implicações: 
- A proteção em tempo real está desligada
- A verificação sob demanda está 24h
- A correção automática de ameaças está desligada
- Atualizações de inteligência de segurança estão ativas
- O ícone do menu Status está oculto

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | passiveMode |
| **Tipo de dados** | Booliano |
| **Valores possíveis** | falso (padrão) <br/> verdadeiro |
| **Comentário** | Disponível no Microsoft Defender para Endpoint versão 100.67.60 ou superior. |

#### <a name="exclusion-merge-policy"></a>Política de mesclagem de exclusão

Especifique a política de mesclagem para exclusões. Isso pode ser uma combinação de exclusões definidas pelo administrador e definidas pelo usuário ( ) ou apenas exclusões definidas pelo administrador `merge` ( `admin_only` ). Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias exclusões.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | exclusionsMergePolicy |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | merge (padrão) <br/> admin_only |
| **Comentário** | Disponível no Microsoft Defender para Endpoint versão 100.83.73 ou superior. |

#### <a name="scan-exclusions"></a>Exclusões de verificação

Especifique entidades excluídas da verificação. As exclusões podem ser especificadas por caminhos completos, extensões ou nomes de arquivo.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | exclusões |
| **Tipo de dados** | Dicionário (preferência aninhada) |
| **Comentário** | Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário. |

##### <a name="type-of-exclusion"></a>Tipo de exclusão

Especifique o conteúdo excluído de ser verificado por tipo.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | $type |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | excludedPath <br/> excludedFileExtension <br/> excludedFileName |

##### <a name="path-to-excluded-content"></a>Caminho para conteúdo excluído

Especifique o conteúdo excluído de ser verificado pelo caminho completo do arquivo.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | caminho |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | caminhos válidos |
| **Comentário** | Aplicável somente se *$type* *for excludedPath* |

##### <a name="path-type-file--directory"></a>Tipo de caminho (arquivo/diretório)

Indique se a *propriedade path* se refere a um arquivo ou diretório. 

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | isDirectory |
| **Tipo de dados** | Booliano |
| **Valores possíveis** | falso (padrão) <br/> verdadeiro |
| **Comentário** | Aplicável somente se *$type* *for excludedPath* |

##### <a name="file-extension-excluded-from-the-scan"></a>Extensão de arquivo excluída da verificação

Especifique o conteúdo excluído de ser verificado por extensão de arquivo.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | extension |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | extensões de arquivo válidas |
| **Comentário** | Aplicável somente se *$type* *for excludedFileExtension* |

##### <a name="process-excluded-from-the-scan"></a>Processo excluído da verificação

Especifique um processo para o qual todas as atividades de arquivo são excluídas da verificação. O processo pode ser especificado pelo nome (por exemplo) ou caminho `cat` completo (por `/bin/cat` exemplo).

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | nome |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | qualquer cadeia de caracteres |
| **Comentário** | Aplicável somente *se* $type *for excludedFileName* |

#### <a name="allowed-threats"></a>Ameaças permitidas

Especifique ameaças por nome que não são bloqueadas pelo Defender para Ponto de Extremidade para Mac. Essas ameaças terão permissão para serem executados.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | allowedThreats |
| **Tipo de dados** | Matriz de cadeias de caracteres |

#### <a name="disallowed-threat-actions"></a>Ações de ameaça não permitidos

Restringe as ações que o usuário local de um dispositivo pode tomar quando as ameaças são detectadas. As ações incluídas nesta lista não são exibidas na interface do usuário.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | disallowedThreatActions |
| **Tipo de dados** | Matriz de cadeias de caracteres |
| **Valores possíveis** | allow (restringe os usuários a permitir ameaças) <br/> restore (restringe os usuários de restaurar ameaças da quarentena) |
| **Comentário** | Disponível no Microsoft Defender para Endpoint versão 100.83.73 ou superior. |

#### <a name="threat-type-settings"></a>Configurações de tipo de ameaça

Especifique como determinados tipos de ameaça são manipulados pelo Microsoft Defender para Ponto de Extremidade no macOS.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | threatTypeSettings |
| **Tipo de dados** | Dicionário (preferência aninhada) |
| **Comentário** | Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário. |

##### <a name="threat-type"></a>Tipo de ameaça

Especifique tipos de ameaça.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | chave |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | potentially_unwanted_application <br/> archive_bomb |

##### <a name="action-to-take"></a>O que fazer

Especifique qual ação tomar quando uma ameaça do tipo especificado na seção anterior for detectada. Escolha entre as seguintes opções:

- **Auditoria**: seu dispositivo não está protegido contra esse tipo de ameaça, mas uma entrada sobre a ameaça é registrada.
- **Bloquear**: seu dispositivo é protegido contra esse tipo de ameaça e você é notificado na interface do usuário e no console de segurança.
- **Off**: seu dispositivo não está protegido contra esse tipo de ameaça e nada é registrado.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | valor |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | audit (padrão) <br/> block <br/> off |

#### <a name="threat-type-settings-merge-policy"></a>Política de mesclagem de configurações de tipo de ameaça

Especifique a política de mesclagem para configurações de tipo de ameaça. Isso pode ser uma combinação de configurações definidas pelo administrador e definidas pelo usuário ( ) ou apenas `merge` configurações definidas pelo administrador ( `admin_only` ). Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias configurações para tipos de ameaça diferentes.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | threatTypeSettingsMergePolicy |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | merge (padrão) <br/> admin_only |
| **Comentário** | Disponível no Microsoft Defender para Endpoint versão 100.83.73 ou superior. |

#### <a name="antivirus-scan-history-retention-in-days"></a>Retenção de histórico de verificação de antivírus (em dias)

Especifique o número de dias que os resultados são mantidos no histórico de verificação no dispositivo. Os resultados antigos da verificação são removidos do histórico. Arquivos em quarentena antigos que também são removidos do disco.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | scanResultsRetentionDays |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | 90 (padrão). Os valores permitidos são de 1 dia a 180 dias. |
| **Comentário** | Disponível no Microsoft Defender para Endpoint versão 101.07.23 ou superior. |

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>Número máximo de itens no histórico de verificação de antivírus

Especifique o número máximo de entradas a manter no histórico de verificação. As entradas incluem todas as verificações sob demanda realizadas no passado e todas as detecções de antivírus.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | scanHistoryMaximumItems |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | 10000 (padrão). Os valores permitidos são de 5.000 itens a 15.000 itens. |
| **Comentário** | Disponível no Microsoft Defender para Endpoint versão 101.07.23 ou superior. |

### <a name="cloud-delivered-protection-preferences"></a>Preferências de proteção entregues na nuvem

Configure os recursos de proteção orientados por nuvem do Microsoft Defender para Endpoint no macOS.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | cloudService |
| **Tipo de dados** | Dicionário (preferência aninhada) |
| **Comentário** | Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário. |

#### <a name="enable--disable-cloud-delivered-protection"></a>Habilitar/desabilitar a proteção entregue na nuvem

Especifique se o dispositivo deve ser habilitado ou não para a proteção entregue na nuvem. Para melhorar a segurança dos seus serviços, recomendamos manter esse recurso ligado.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | habilitadas |
| **Tipo de dados** | Booliano |
| **Valores possíveis** | true (padrão) <br/> falso |

#### <a name="diagnostic-collection-level"></a>Nível de coleta de diagnóstico

Os dados de diagnóstico são usados para manter o Microsoft Defender para o Ponto de Extremidade seguro e atualizado, detectar, diagnosticar e corrigir problemas e também fazer melhorias no produto. Essa configuração determina o nível de diagnóstico enviado pelo Microsoft Defender para o Ponto de Extremidade para a Microsoft.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | diagnosticLevel |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | opcional (padrão) <br/> obrigatório |

#### <a name="enable--disable-automatic-sample-submissions"></a>Habilitar/desabilitar envios automáticos de exemplo

Determina se amostras suspeitas (que provavelmente contêm ameaças) são enviadas à Microsoft. Você será solicitado se o arquivo enviado provavelmente conter informações pessoais.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | automaticSampleSubmission |
| **Tipo de dados** | Booliano |
| **Valores possíveis** | true (padrão) <br/> falso |

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>Habilitar/desabilitar atualizações automáticas de inteligência de segurança

Determina se as atualizações de inteligência de segurança são instaladas automaticamente:

|Section|Valor|
|:---|:---|
| **Tecla** | automaticDefinitionUpdateEnabled |
| **Tipo de dados** | Booliano |
| **Valores possíveis** | true (padrão) <br/> falso |

### <a name="user-interface-preferences"></a>Preferências de interface do usuário

Gerencie as preferências para a interface do usuário do Microsoft Defender para Ponto de Extremidade no macOS.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | userInterface |
| **Tipo de dados** | Dicionário (preferência aninhada) |
| **Comentário** | Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário. |

#### <a name="show--hide-status-menu-icon"></a>Mostrar/ocultar ícone de menu de status

Especifique se deve mostrar ou ocultar o ícone do menu de status no canto superior direito da tela.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | hideStatusMenuIcon |
| **Tipo de dados** | Booliano |
| **Valores possíveis** | falso (padrão) <br/> verdadeiro |

#### <a name="show--hide-option-to-send-feedback"></a>Mostrar/ocultar opção para enviar comentários

Especifique se os usuários podem enviar comentários para a Microsoft indo para `Help`  >  `Send Feedback` .

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | userInitiatedFeedback |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | habilitado (padrão) <br/> desabilitadas |
| **Comentário** | Disponível no Microsoft Defender para Endpoint versão 101.19.61 ou superior. |

### <a name="endpoint-detection-and-response-preferences"></a>Preferências de detecção e resposta do ponto de extremidade

Gerencie as preferências do componente de detecção e resposta do ponto de extremidade (EDR) do Microsoft Defender para Ponto de Extremidade no macOS.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | edr |
| **Tipo de dados** | Dicionário (preferência aninhada) |
| **Comentário** | Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário. |

#### <a name="device-tags"></a>Marcas de dispositivo

Especifique um nome de marca e seu valor. 

- A marca GROUP marca o dispositivo com o valor especificado. A marca é refletida no portal sob a página do dispositivo e pode ser usada para filtrar e agrupar dispositivos.

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | categorias |
| **Tipo de dados** | Dicionário (preferência aninhada) |
| **Comentário** | Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário. |

##### <a name="type-of-tag"></a>Tipo de marca

Especifica o tipo de marca

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | chave |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | `GROUP` |

##### <a name="value-of-tag"></a>Valor da marca

Especifica o valor da marca

|Section|Valor|
|:---|:---|
| **Domínio** | `com.microsoft.wdav` |
| **Tecla** | valor |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | qualquer cadeia de caracteres |

> [!IMPORTANT]  
> - Somente um valor por tipo de marca pode ser definido.
> - O tipo de marcas é exclusivo e não deve ser repetido no mesmo perfil de configuração.

## <a name="recommended-configuration-profile"></a>Perfil de configuração recomendado

Para começar, recomendamos que a configuração a seguir para sua empresa tire proveito de todos os recursos de proteção que o Microsoft Defender para Ponto de Extremidade fornece.

O perfil de configuração a seguir (ou, no caso de JAMF, uma lista de propriedades que poderia ser carregada no perfil de configuração de configurações personalizadas) será:
- Habilitar a proteção em tempo real (RTP)
- Especifique como os seguintes tipos de ameaça são tratados:
  - **Aplicativos potencialmente indesejados (PUA)** são bloqueados
  - **As bombas de** arquivo morto (arquivo com alta taxa de compactação) são auditadas para logs do Microsoft Defender para pontos de extremidade
- Habilitar atualizações automáticas de inteligência de segurança
- Habilitar a proteção entregue na nuvem
- Habilitar envio automático de exemplo

### <a name="property-list-for-jamf-configuration-profile"></a>Lista de propriedades para perfil de configuração JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a>Perfil do Intune

```XML
<?xml version="1.0" encoding="utf-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>com.microsoft.wdav</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

## <a name="full-configuration-profile-example"></a>Exemplo de perfil de configuração completa

Os modelos a seguir contêm entradas para todas as configurações descritas neste documento e podem ser usadas para cenários mais avançados em que você deseja mais controle sobre o Microsoft Defender para Ponto de Extremidade no macOS.

### <a name="property-list-for-jamf-configuration-profile"></a>Lista de propriedades para perfil de configuração JAMF

```XML
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>antivirusEngine</key>
    <dict>
        <key>enableRealTimeProtection</key>
        <true/>
        <key>passiveMode</key>
        <false/>
        <key>exclusions</key>
        <array>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <false/>
                <key>path</key>
                <string>/var/log/system.log</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedPath</string>
                <key>isDirectory</key>
                <true/>
                <key>path</key>
                <string>/home</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileExtension</string>
                <key>extension</key>
                <string>pdf</string>
            </dict>
            <dict>
                <key>$type</key>
                <string>excludedFileName</string>
                <key>name</key>
                <string>cat</string>
            </dict>
        </array>
        <key>exclusionsMergePolicy</key>
        <string>merge</string>
        <key>allowedThreats</key>
        <array>
            <string>EICAR-Test-File (not a virus)</string>
        </array>
        <key>disallowedThreatActions</key>
        <array>
            <string>allow</string>
            <string>restore</string>
        </array>
        <key>threatTypeSettings</key>
        <array>
            <dict>
                <key>key</key>
                <string>potentially_unwanted_application</string>
                <key>value</key>
                <string>block</string>
            </dict>
            <dict>
                <key>key</key>
                <string>archive_bomb</string>
                <key>value</key>
                <string>audit</string>
            </dict>
        </array>
        <key>threatTypeSettingsMergePolicy</key>
        <string>merge</string>
    </dict>
    <key>cloudService</key>
    <dict>
        <key>enabled</key>
        <true/>
        <key>diagnosticLevel</key>
        <string>optional</string>
        <key>automaticSampleSubmission</key>
        <true/>
        <key>automaticDefinitionUpdateEnabled</key>
        <true/>
    </dict>
    <key>edr</key>
    <dict>
        <key>tags</key>
        <array>
            <dict>
                <key>key</key>
                <string>GROUP</string>
                <key>value</key>
                <string>ExampleTag</string>
            </dict>
        </array>
    </dict>
    <key>userInterface</key>
    <dict>
        <key>hideStatusMenuIcon</key>
        <false/>
        <key>userInitiatedFeedback</key>
        <string>enabled</string>
    </dict>
</dict>
</plist>
```

### <a name="intune-profile"></a>Perfil do Intune

```XML
        <key>PayloadUUID</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft</string>
        <key>PayloadIdentifier</key>
        <string>C4E6A782-0C8D-44AB-A025-EB893987A295</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender for Endpoint settings</string>
        <key>PayloadDescription</key>
        <string>Microsoft Defender for Endpoint configuration settings</string>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadType</key>
                <string>com.microsoft.wdav</string>
                <key>PayloadOrganization</key>
                <string>Microsoft</string>
                <key>PayloadIdentifier</key>
                <string>99DBC2BC-3B3A-46A2-A413-C8F9BB9A7295</string>
                <key>PayloadDisplayName</key>
                <string>Microsoft Defender for Endpoint configuration settings</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>antivirusEngine</key>
                <dict>
                    <key>enableRealTimeProtection</key>
                    <true/>
                    <key>passiveMode</key>
                    <false/>
                    <key>exclusions</key>
                    <array>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <false/>
                            <key>path</key>
                            <string>/var/log/system.log</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedPath</string>
                            <key>isDirectory</key>
                            <true/>
                            <key>path</key>
                            <string>/home</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileExtension</string>
                            <key>extension</key>
                            <string>pdf</string>
                        </dict>
                        <dict>
                            <key>$type</key>
                            <string>excludedFileName</string>
                            <key>name</key>
                            <string>cat</string>
                        </dict>
                    </array>
                    <key>exclusionsMergePolicy</key>
                    <string>merge</string>
                    <key>allowedThreats</key>
                    <array>
                        <string>EICAR-Test-File (not a virus)</string>
                    </array>
                    <key>disallowedThreatActions</key>
                    <array>
                        <string>allow</string>
                        <string>restore</string>
                    </array>
                    <key>threatTypeSettings</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>potentially_unwanted_application</string>
                            <key>value</key>
                            <string>block</string>
                        </dict>
                        <dict>
                            <key>key</key>
                            <string>archive_bomb</string>
                            <key>value</key>
                            <string>audit</string>
                        </dict>
                    </array>
                    <key>threatTypeSettingsMergePolicy</key>
                    <string>merge</string>
                </dict>
                <key>cloudService</key>
                <dict>
                    <key>enabled</key>
                    <true/>
                    <key>diagnosticLevel</key>
                    <string>optional</string>
                    <key>automaticSampleSubmission</key>
                    <true/>
                    <key>automaticDefinitionUpdateEnabled</key>
                    <true/>
                </dict>
                <key>edr</key>
                <dict>
                    <key>tags</key>
                    <array>
                        <dict>
                            <key>key</key>
                            <string>GROUP</string>
                            <key>value</key>
                            <string>ExampleTag</string>
                        </dict>
                    </array>
                </dict>
                <key>userInterface</key>
                <dict>
                    <key>hideStatusMenuIcon</key>
                    <false/>
                    <key>userInitiatedFeedback</key>
                    <string>enabled</string>
                </dict>
            </dict>
        </array>
```

## <a name="property-list-validation"></a>Validação de lista de propriedades

A lista de propriedades deve ser um arquivo *.plist* válido. Isso pode ser verificado executando:

```bash
plutil -lint com.microsoft.wdav.plist
```
```Output
com.microsoft.wdav.plist: OK
```

Se o arquivo for bem formado, o comando acima sairá e retornará um código `OK` de saída de `0` . Caso contrário, um erro que descreve o problema é exibido e o comando retorna um código de saída de `1` .

## <a name="configuration-profile-deployment"></a>Implantação de perfil de configuração

Depois de construir o perfil de configuração da sua empresa, você pode implantá-lo por meio do console de gerenciamento que sua empresa está usando. As seções a seguir fornecem instruções sobre como implantar esse perfil usando JAMF e Intune.

### <a name="jamf-deployment"></a>Implantação jamf

No console JAMF, **abra** Perfis de Configuração de Computadores, navegue até o perfil de configuração que você gostaria de  >  usar e selecione **Configurações Personalizadas.** Crie uma entrada com `com.microsoft.wdav` como o domínio de preferência e carregue o *.plist* produzido anteriormente.

>[!CAUTION]
>Você deve inserir o domínio de preferência correto ( ); caso contrário, as preferências não serão reconhecidas pelo `com.microsoft.wdav` Microsoft Defender para o Ponto de Extremidade.

### <a name="intune-deployment"></a>Implantação do Intune

1. Abra **Gerenciar**  >  **Configuração do Dispositivo**. Selecione **Gerenciar**  >    >  **Perfis Criar Perfil**.

2. Escolha um nome para o perfil. Alterar **Platform=macOS** para **Profile type=Custom**. Selecione Configurar.

3. Salve o .plist produzido anteriormente como `com.microsoft.wdav.xml` .

4. Insira `com.microsoft.wdav` como o nome do perfil de **configuração personalizado**.

5. Abra o perfil de configuração e carregue o `com.microsoft.wdav.xml` arquivo. (Esse arquivo foi criado na etapa 3.)

6. Selecione **OK**.

7. Selecione **Gerenciar**  >  **atribuições**. Na guia **Incluir,** selecione **Atribuir a Todos os Usuários & Todos os dispositivos**.

>[!CAUTION]
>Você deve inserir o nome de perfil de configuração personalizado correto; caso contrário, essas preferências não serão reconhecidas pelo Microsoft Defender para Ponto de Extremidade.

## <a name="resources"></a>Recursos

- [Referência do Perfil de Configuração (Documentação do desenvolvedor da Apple)](https://developer.apple.com/business/documentation/Configuration-Profile-Reference.pdf)
