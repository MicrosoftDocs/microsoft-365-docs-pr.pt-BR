---
title: Definir preferências para o Microsoft Defender para Ponto de Extremidade no Linux
ms.reviewer: ''
description: Descreve como configurar o Microsoft Defender para Ponto de Extremidade no Linux em empresas.
keywords: microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2c162d652656afb61f1d74bad9ec963825d25a14
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903865"
---
# <a name="set-preferences-for-microsoft-defender-for-endpoint-on-linux"></a>Definir preferências para o Microsoft Defender para Ponto de Extremidade no Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

>[!IMPORTANT]
>Este tópico contém instruções sobre como definir preferências para o Defender for Endpoint para Linux em ambientes corporativos. Se você estiver interessado em configurar o produto em um dispositivo da linha de comando, consulte [Resources](linux-resources.md#configure-from-the-command-line).

Em ambientes corporativos, o Defender for Endpoint para Linux pode ser gerenciado por meio de um perfil de configuração. Esse perfil é implantado a partir da ferramenta de gerenciamento de sua escolha. As preferências gerenciadas pela empresa têm precedência sobre as definidas localmente no dispositivo. Em outras palavras, os usuários em sua empresa não são capazes de alterar as preferências definidas por meio desse perfil de configuração.

Este artigo descreve a estrutura desse perfil (incluindo um perfil recomendado que você pode usar para começar) e instruções sobre como implantar o perfil.

## <a name="configuration-profile-structure"></a>Estrutura de perfil de configuração

O perfil de configuração é um arquivo .json que consiste em entradas identificadas por uma chave (que indica o nome da preferência), seguida por um valor, que depende da natureza da preferência. Os valores podem ser simples, como um valor numérico ou complexo, como uma lista aninhada de preferências.

Normalmente, você usaria uma ferramenta de gerenciamento de configuração para pressionar um arquivo com o nome ```mdatp_managed.json``` no local ```/etc/opt/microsoft/mdatp/managed/``` .

O nível superior do perfil de configuração inclui preferências e entradas para subáreas do produto, que são explicadas com mais detalhes nas próximas seções.

### <a name="antivirus-engine-preferences"></a>Preferências do mecanismo antivírus

A *seção antivírusEngine* do perfil de configuração é usada para gerenciar as preferências do componente antivírus do produto.

|||
|:---|:---|
| **Tecla** | antivirusEngine |
| **Tipo de dados** | Dicionário (preferência aninhada) |
| **Comentário** | Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário. |
|||

#### <a name="enable--disable-real-time-protection"></a>Habilitar/desabilitar a proteção em tempo real

Determina se a proteção em tempo real (arquivos de verificação conforme eles são acessados) está habilitada ou não.

|||
|:---|:---|
| **Tecla** | enableRealTimeProtection |
| **Tipo de dados** | Booliano |
| **Valores possíveis** | true (padrão) <br/> falso |
|||

#### <a name="enable--disable-passive-mode"></a>Habilitar/desabilitar o modo passivo

Determina se o mecanismo antivírus é executado no modo passivo ou não. No modo passivo:
- A proteção em tempo real está desligada.
- A verificação sob demanda está 100% 100%.
- A correção automática de ameaças está desligada.
- As atualizações de inteligência de segurança estão ativas.
- O ícone do menu Status está oculto.

|||
|:---|:---|
| **Tecla** | passiveMode |
| **Tipo de dados** | Booliano |
| **Valores possíveis** | falso (padrão) <br/> verdadeiro |
| **Comentário** | Disponível no Defender para Ponto de Extremidade versão 100.67.60 ou superior. |
|||

#### <a name="exclusion-merge-policy"></a>Política de mesclagem de exclusão

Especifica a política de mesclagem para exclusões. Pode ser uma combinação de exclusões definidas pelo administrador e definidas pelo usuário ( ) ou apenas exclusões definidas pelo administrador `merge` ( `admin_only` ). Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias exclusões.

|||
|:---|:---|
| **Tecla** | exclusionsMergePolicy |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | merge (padrão) <br/> admin_only |
| **Comentário** | Disponível no Defender para Ponto de Extremidade versão 100.83.73 ou superior. |
|||

#### <a name="scan-exclusions"></a>Exclusões de verificação

Entidades que foram excluídas da verificação. As exclusões podem ser especificadas por caminhos completos, extensões ou nomes de arquivo.

|||
|:---|:---|
| **Tecla** | exclusões |
| **Tipo de dados** | Dicionário (preferência aninhada) |
| **Comentário** | Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário. |
|||

**Tipo de exclusão**

Especifica o tipo de conteúdo excluído da verificação.

|||
|:---|:---|
| **Tecla** | $type |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | excludedPath <br/> excludedFileExtension <br/> excludedFileName |
|||

**Caminho para conteúdo excluído**

Usado para excluir conteúdo da verificação por caminho de arquivo completo.

|||
|:---|:---|
| **Tecla** | caminho |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | caminhos válidos |
| **Comentário** | Aplicável somente se *$type* *for excludedPath* |
|||

**Tipo de caminho (arquivo/diretório)**

Indica se a *propriedade path* se refere a um arquivo ou diretório. 

|||
|:---|:---|
| **Tecla** | isDirectory |
| **Tipo de dados** | Booliano |
| **Valores possíveis** | falso (padrão) <br/> verdadeiro |
| **Comentário** | Aplicável somente se *$type* *for excludedPath* |
|||

**Extensão de arquivo excluída da verificação**

Usado para excluir conteúdo da verificação por extensão de arquivo.

|||
|:---|:---|
| **Tecla** | extension |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | extensões de arquivo válidas |
| **Comentário** | Aplicável somente se *$type* *for excludedFileExtension* |
|||

**Processo excluído da verificação**

Especifica um processo para o qual todas as atividades de arquivo são excluídas da verificação. O processo pode ser especificado pelo nome (por exemplo) `cat` ou caminho completo (por exemplo, `/bin/cat` ).

|||
|:---|:---|
| **Tecla** | nome |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | qualquer cadeia de caracteres |
| **Comentário** | Aplicável somente *se* $type *for excludedFileName* |
|||

#### <a name="allowed-threats"></a>Ameaças permitidas

Lista de ameaças (identificadas pelo nome) que não são bloqueadas pelo produto e têm permissão para executar.

|||
|:---|:---|
| **Tecla** | allowedThreats |
| **Tipo de dados** | Matriz de cadeias de caracteres |
|||

#### <a name="disallowed-threat-actions"></a>Ações de ameaça não permitidos

Restringe as ações que o usuário local de um dispositivo pode tomar quando as ameaças são detectadas. As ações incluídas nesta lista não são exibidas na interface do usuário.

|||
|:---|:---|
| **Tecla** | disallowedThreatActions |
| **Tipo de dados** | Matriz de cadeias de caracteres |
| **Valores possíveis** | allow (restringe os usuários a permitir ameaças) <br/> restore (restringe os usuários de restaurar ameaças da quarentena) |
| **Comentário** | Disponível no Defender para Ponto de Extremidade versão 100.83.73 ou superior. |
|||

#### <a name="threat-type-settings"></a>Configurações de tipo de ameaça

A *preferência threatTypeSettings* no mecanismo antivírus é usada para controlar como determinados tipos de ameaça são manipulados pelo produto.

|||
|:---|:---|
| **Tecla** | threatTypeSettings |
| **Tipo de dados** | Dicionário (preferência aninhada) |
| **Comentário** | Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário. |
|||

**Tipo de ameaça**

Tipo de ameaça para a qual o comportamento está configurado.

|||
|:---|:---|
| **Tecla** | chave |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | potentially_unwanted_application <br/> archive_bomb |
|||

**O que fazer**

Ação a ser tomada ao se deparar com uma ameaça do tipo especificado na seção anterior. Pode ser:

- **Auditoria**: o dispositivo não está protegido contra esse tipo de ameaça, mas uma entrada sobre a ameaça é registrada.
- **Bloquear**: o dispositivo é protegido contra esse tipo de ameaça e você é notificado no console de segurança.
- **Off**: O dispositivo não está protegido contra esse tipo de ameaça e nada é registrado.

|||
|:---|:---|
| **Tecla** | valor |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | audit (padrão) <br/> block <br/> off |
|||

#### <a name="threat-type-settings-merge-policy"></a>Política de mesclagem de configurações de tipo de ameaça

Especifica a política de mesclagem para configurações de tipo de ameaça. Isso pode ser uma combinação de configurações definidas pelo administrador e definidas pelo usuário ( ) ou apenas `merge` configurações definidas pelo administrador ( `admin_only` ). Essa configuração pode ser usada para restringir os usuários locais de definir suas próprias configurações para tipos de ameaça diferentes.

|||
|:---|:---|
| **Tecla** | threatTypeSettingsMergePolicy |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | merge (padrão) <br/> admin_only |
| **Comentário** | Disponível no Defender para Ponto de Extremidade versão 100.83.73 ou superior. |
|||

#### <a name="antivirus-scan-history-retention-in-days"></a>Retenção de histórico de verificação de antivírus (em dias)

Especifique o número de dias que os resultados são mantidos no histórico de verificação no dispositivo. Os resultados antigos da verificação são removidos do histórico. Arquivos em quarentena antigos que também são removidos do disco.

|||
|:---|:---|
| **Tecla** | scanResultsRetentionDays |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | 90 (padrão). Os valores permitidos são de 1 dia a 180 dias. |
| **Comentário** | Disponível no Defender para Ponto de Extremidade versão 101.04.76 ou superior. |
|||

#### <a name="maximum-number-of-items-in-the-antivirus-scan-history"></a>Número máximo de itens no histórico de verificação de antivírus

Especifique o número máximo de entradas a manter no histórico de verificação. As entradas incluem todas as verificações sob demanda realizadas no passado e todas as detecções de antivírus.

|||
|:---|:---|
| **Tecla** | scanHistoryMaximumItems |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | 10000 (padrão). Os valores permitidos são de 5.000 itens a 15.000 itens. |
| **Comentário** | Disponível no Defender para Ponto de Extremidade versão 101.04.76 ou superior. |
|||

### <a name="cloud-delivered-protection-preferences"></a>Preferências de proteção entregues na nuvem

A *entrada do cloudService* no perfil de configuração é usada para configurar o recurso de proteção orientada por nuvem do produto.

|||
|:---|:---|
| **Tecla** | cloudService |
| **Tipo de dados** | Dicionário (preferência aninhada) |
| **Comentário** | Consulte as seções a seguir para ver uma descrição do conteúdo do dicionário. |
|||

#### <a name="enable--disable-cloud-delivered-protection"></a>Habilitar/desabilitar a proteção entregue na nuvem

Determina se a proteção entregue na nuvem está habilitada no dispositivo ou não. Para melhorar a segurança dos seus serviços, recomendamos manter esse recurso ligado.

|||
|:---|:---|
| **Tecla** | habilitadas |
| **Tipo de dados** | Booliano |
| **Valores possíveis** | true (padrão) <br/> falso |
|||

#### <a name="diagnostic-collection-level"></a>Nível de coleta de diagnóstico

Os dados de diagnóstico são usados para manter o Defender para o Ponto de Extremidade seguro e atualizado, detectar, diagnosticar e corrigir problemas e também fazer melhorias no produto. Essa configuração determina o nível de diagnóstico enviado pelo produto para a Microsoft.

|||
|:---|:---|
| **Tecla** | diagnosticLevel |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | opcional (padrão) <br/> obrigatório |
|||

#### <a name="enable--disable-automatic-sample-submissions"></a>Habilitar/desabilitar envios automáticos de exemplo

Determina se amostras suspeitas (que provavelmente contêm ameaças) são enviadas à Microsoft. Há três níveis para controlar o envio de exemplo:

- **Nenhum**: nenhum exemplo suspeito é enviado à Microsoft.
- **Seguro**: somente amostras suspeitas que não contêm informações de identificação pessoal (PII) são enviadas automaticamente. Esse é o valor padrão para essa configuração.
- **All**: todos os exemplos suspeitos são enviados à Microsoft.

|||
|:---|:---|
| **Tecla** | automaticSampleSubmissionConsent |
| **Tipo de dados** | Cadeia de caracteres |
| **Valores possíveis** | nenhuma <br/> safe (padrão) <br/> all |
|||

#### <a name="enable--disable-automatic-security-intelligence-updates"></a>Habilitar/desabilitar atualizações automáticas de inteligência de segurança

Determina se as atualizações de inteligência de segurança são instaladas automaticamente:

|||
|:---|:---|
| **Tecla** | automaticDefinitionUpdateEnabled |
| **Tipo de dados** | Booliano |
| **Valores possíveis** | true (padrão) <br/> falso |
|||

## <a name="recommended-configuration-profile"></a>Perfil de configuração recomendado

Para começar, recomendamos que o perfil de configuração a seguir para sua empresa tire proveito de todos os recursos de proteção que o Defender para Ponto de Extremidade fornece.

O seguinte perfil de configuração será:

- Habilitar a proteção em tempo real (RTP)
- Especifique como os seguintes tipos de ameaça são tratados:
  - **Aplicativos potencialmente indesejados (PUA)** são bloqueados
  - **As bombas de** arquivo morto (arquivo com alta taxa de compactação) são auditadas para os logs do produto
- Habilitar atualizações automáticas de inteligência de segurança
- Habilitar a proteção entregue na nuvem
- Habilitar o envio automático de exemplo no `safe` nível

### <a name="sample-profile"></a>Perfil de exemplo

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "automaticDefinitionUpdateEnabled":true,
      "automaticSampleSubmissionConsent":"safe",
      "enabled":true
      "proxy":"http://proxy.server:port/"
   }
}
```

## <a name="full-configuration-profile-example"></a>Exemplo de perfil de configuração completa

O perfil de configuração a seguir contém entradas para todas as configurações descritas neste documento e pode ser usado para cenários mais avançados em que você deseja mais controle sobre o produto.

### <a name="full-profile"></a>Perfil completo

```JSON
{
   "antivirusEngine":{
      "enableRealTimeProtection":true,
      "passiveMode":false,
      "exclusionsMergePolicy":"merge",
      "exclusions":[
         {
            "$type":"excludedPath",
            "isDirectory":false,
            "path":"/var/log/system.log"
         },
         {
            "$type":"excludedPath",
            "isDirectory":true,
            "path":"/home"
         },
         {
            "$type":"excludedFileExtension",
            "extension":"pdf"
         },
         {
            "$type":"excludedFileName",
            "name":"cat"
         }
      ],
      "allowedThreats":[
         "EICAR-Test-File (not a virus)"
      ],
      "disallowedThreatActions":[
         "allow",
         "restore"
      ],
      "threatTypeSettingsMergePolicy":"merge",
      "threatTypeSettings":[
         {
            "key":"potentially_unwanted_application",
            "value":"block"
         },
         {
            "key":"archive_bomb",
            "value":"audit"
         }
      ]
   },
   "cloudService":{
      "enabled":true,
      "diagnosticLevel":"optional",
      "automaticSampleSubmissionConsent":"safe",
      "automaticDefinitionUpdateEnabled":true
      "proxy": "http://proxy.server:port/"
   }
}
```

## <a name="configuration-profile-validation"></a>Validação de perfil de configuração

O perfil de configuração deve ser um arquivo JSON formatado válido. Há várias ferramentas que podem ser usadas para verificar isso. Por exemplo, se você `python` tiver instalado em seu dispositivo:

```bash
python -m json.tool mdatp_managed.json
```

Se o JSON for bem formado, o comando acima o retornará ao Terminal e retornará um código de saída de `0` . Caso contrário, um erro que descreve o problema é exibido e o comando retorna um código de saída de `1` .

## <a name="verifying-that-the-mdatp_managedjson-file-is-working-as-expected"></a>Verificar se o arquivo mdatp_managed.json está funcionando conforme o esperado
Para verificar se o /etc/opt/microsoft/mdatp/managed/mdatp_managed.json está funcionando corretamente, você deve ver "[gerenciado]" ao lado dessas configurações:  
- cloud_enabled
- cloud_automatic_sample_submission_consent
- passice_mode_enabled
- real_time_protection_enabled
- automatic_definition_update_enabled

> [!NOTE]
> Para que mdatp_managed.jsa ação entre em vigor, nenhuma reinicialização do wdavdaemon é necessária.

## <a name="configuration-profile-deployment"></a>Implantação de perfil de configuração

Depois de construir o perfil de configuração para sua empresa, você poderá implantá-lo por meio da ferramenta de gerenciamento que sua empresa está usando. O Defender for Endpoint para Linux lê a configuração gerenciada do *arquivo /etc/opt/microsoft/mdatp/managed/mdatp_managed.json.*
