---
title: Personalizar regras da redução da superfície de ataque
description: Definir regras individualmente em modos de auditoria, bloqueio ou desabilitação e adicionar arquivos e pastas que devem ser excluídos das regras de redução de superfície de ataque
keywords: Redução de superfície de ataque, quadris, sistema de prevenção contra invasões de host, regras de proteção, antiexploit, exploração, prevenção de infecção, personalizar, configurar, excluir
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 52a51b1035f1aa0fb152cf17dc9561cce378d59d
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570346"
---
# <a name="customize-attack-surface-reduction-rules"></a>Personalizar regras da redução da superfície de ataque

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial. A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.

[As regras de redução de superfície de](enable-attack-surface-reduction.md) ataque ajudam a evitar comportamentos de software que muitas vezes são abusadas para comprometer seu dispositivo ou rede. Por exemplo, um invasor pode tentar executar um script não assinado de uma unidade USB ou ter uma macro em um documento do Office fazer chamadas diretamente para a API Win32. As regras de redução de superfície de ataque podem restringir esses tipos de comportamentos de risco e melhorar a postura defensiva da sua organização.

Saiba como personalizar regras de [](#exclude-files-and-folders) redução de superfície [](#customize-the-notification) de ataque excluindo arquivos e pastas ou adicionando texto personalizado ao alerta de notificação que aparece no computador de um usuário.

Você pode definir regras de redução de superfície de ataque para dispositivos que executam qualquer uma das seguintes edições e versões do Windows:
- Windows 10 Pro, [versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) ou posterior
- Windows 10 Enterprise, [versão 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) ou posterior
- Windows Server, [versão 1803 (Canal Semesanuais)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) ou posterior
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19) Você pode usar provedores de serviço de configuração de Política de Grupo, PowerShell e Gerenciamento de Dispositivo Móvel (CSP) para configurar essas configurações.

## <a name="exclude-files-and-folders"></a>Excluir arquivos e pastas

Você pode optar por excluir arquivos e pastas de serem avaliados pelas regras de redução de superfície de ataque. Depois de excluído, o arquivo não será impedido de ser executado mesmo que uma regra de redução de superfície de ataque detecte que o arquivo contém comportamento mal-intencionado.

> [!WARNING]
> Isso pode permitir que arquivos não seguros executem e infectem seus dispositivos. A exclusão de arquivos ou pastas pode reduzir gravemente a proteção fornecida pelas regras de redução de superfície de ataque. Os arquivos que teriam sido bloqueados por uma regra terão permissão para serem executados e não haverá nenhum relatório ou evento gravado.

Uma exclusão se aplica a todas as regras que permitem exclusões. Você pode especificar um arquivo individual, caminho de pasta ou o nome de domínio totalmente qualificado para um recurso. No entanto, você não pode limitar uma exclusão a uma regra específica.

Uma exclusão é aplicada somente quando o aplicativo ou serviço excluído é iniciado. Por exemplo, se você adicionar uma exclusão para um serviço de atualização que já está em execução, o serviço de atualização continuará disparando eventos até que o serviço seja interrompido e reiniciado.

A redução de superfície de ataque dá suporte a variáveis de ambiente e curingas. Para obter informações sobre como usar caracteres curinga, consulte use curingas no nome do arquivo e no caminho da pasta ou listas de [exclusão de extensão.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)
Se você estiver encontrando problemas com regras que detectam arquivos que você acredita que não devem ser detectados, use o modo de auditoria [para testar a regra](evaluate-attack-surface-reduction.md).

Descrição da regra | GUID
-|-|-
Bloquear todos os aplicativos do Office da criação de processos filho | D4F940AB-401B-4EFC-AADC-AD5F3C50688A
Bloquear a execução de scripts potencialmente ofuscados | 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC
Bloquear chamadas de API Win32 da macro do Office | 92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B
Impedir aplicativos do Office de criar conteúdo executável | 3B576869-A4EC-4529-8536-B80A7769E899
Impedir que aplicativos do Office injetem código em outros processos | 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84
Bloquear JavaScript ou VBScript de iniciar conteúdo executável baixado | D3E037E1-3EB8-44C8-A917-57927947596D
Bloquear conteúdo executável do cliente de email e do webmail | BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550
Impedir a execução de arquivos executáveis, a menos que eles atendem a uma prevalência, idade ou critérios de lista confiáveis | 01443614-cd74-433a-b99e-2ecdc07bfc25
Usar proteção avançada contra ransomware | c1db55ab-c21a-4637-bb3f-a12568109d35
Bloquear o roubo de credenciais do subsistema de autoridade de segurança local do Windows (lsass.exe) | 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2
Bloquear criações de processo provenientes de comandos PSExec e WMI | d1e49aac-8f56-4280-b9ba-993a6d77406c
Bloquear processos não assinados e não assinados que são executados a partir do USB | b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4
Bloquear aplicativos de comunicação do Office da criação de processos filho | 26190899-1602-49e8-8b27-eb1d0a1ce869
Impedir o Adobe Reader de criar processos filho | 7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c
Bloquear a persistência por meio da assinatura de evento WMI | e6db77e5-3df2-4cf1-b95a-636979351e5b

Consulte o [tópico de redução de](attack-surface-reduction.md) superfície de ataque para obter detalhes sobre cada regra.

### <a name="use-group-policy-to-exclude-files-and-folders"></a>Usar a Política de Grupo para excluir arquivos e pastas

1. No computador de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](https://technet.microsoft.com/library/cc731212.aspx), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e selecione **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** acesse **Configuração do** computador e clique em Modelos **Administrativos.**

3. Expanda a árvore para **componentes do Windows**  >  **Microsoft Defender**  >  **Antivírus Windows Defender redução de** superfície de ataque do Exploit  >  Guard.

4. Clique duas vezes na **configuração Excluir arquivos e caminhos da** redução de superfície de ataque Regras e de definir a opção como **Habilitado**. Selecione **Mostrar** e insira cada arquivo ou pasta na coluna **Nome do** valor. Insira **0** na coluna **Valor** para cada item.

> [!WARNING]
> Não use aspas, pois elas não são suportadas para a coluna **Nome do** valor ou para a **coluna Valor.**

### <a name="use-powershell-to-exclude-files-and-folders"></a>Usar o PowerShell para excluir arquivos e pastas

1. Digite **o powershell** no menu Iniciar, clique com o botão direito do **mouse Windows PowerShell** e selecione Executar como **administrador**
2. Insira o seguinte cmdlet:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

Continue a usar `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` para adicionar mais pastas à lista.

> [!IMPORTANT]
> Use `Add-MpPreference` para acrescentar ou adicionar aplicativos à lista. O uso `Set-MpPreference` do cmdlet substituirá a lista existente.

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>Usar CSPs MDM para excluir arquivos e pastas

Use o provedor de serviços de configuração [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) (CSP) para adicionar exclusões.

## <a name="customize-the-notification"></a>Personalizar a notificação

Você pode personalizar a notificação para quando uma regra é disparada e bloqueia um aplicativo ou arquivo. Consulte o [artigo segurança do Windows.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)

## <a name="related-topics"></a>Tópicos relacionados

* [Reduzir superfícies de ataque com regras de redução de superfície de ataque](attack-surface-reduction.md)
* [Habilitar regras da redução da superfície de ataque](enable-attack-surface-reduction.md)
* [Avaliar as regras da redução da superfície de ataque](evaluate-attack-surface-reduction.md)
* [Perguntas frequentes sobre a redução da superfície de ataque](attack-surface-reduction.md)
