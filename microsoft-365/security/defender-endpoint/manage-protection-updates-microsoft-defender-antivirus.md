---
title: Gerenciar como e onde Microsoft Defender Antivírus recebe atualizações
description: Gerencie a ordem de fallback para saber Microsoft Defender Antivírus recebe atualizações de proteção.
keywords: atualizações, linhas de base de segurança, proteção, ordem de fallback, ADL, MMPC, UNC, caminho de arquivo, compartilhamento, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 35873b371e773e793ae966a338150e2e5e256a42
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926026"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a>Gerenciar as fontes das atualizações de proteção do Microsoft Defender Antivírus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=22154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

Manter a proteção antivírus atualizada é fundamental. Há dois componentes para gerenciar atualizações de proteção para Microsoft Defender Antivírus: 
- *De* onde as atualizações são baixadas; e 
- *Quando* as atualizações são baixadas e aplicadas. 

Este artigo descreve como especificar de onde as atualizações devem ser baixadas (isso também é conhecido como ordem de fallback). Consulte [Manage Microsoft Defender Antivírus updates and](manage-updates-baselines-microsoft-defender-antivirus.md) apply baselines topic for an overview on how updates work, and how to configure other aspects of updates (such as scheduling updates).

> [!IMPORTANT]
> Microsoft Defender Antivírus As atualizações de inteligência de segurança são entregues por meio do Windows Update e, a partir de segunda-feira, 21 de outubro de 2019, todas as atualizações de inteligência de segurança serão assinadas exclusivamente pelo SHA-2. Seus dispositivos devem ser atualizados para dar suporte ao SHA-2 para atualizar sua inteligência de segurança. Para saber mais, confira [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).  


<a id="fallback-order"></a>

## <a name="fallback-order"></a>Ordem de fallback

Normalmente, você configura pontos de extremidade para baixar as atualizações individualmente de uma fonte primária seguida por outras fontes em ordem de prioridade, com base em sua configuração de rede. As atualizações são obtidas de fontes na ordem especificada. Se uma fonte não estiver disponível, a próxima fonte da lista será usada imediatamente.

Quando as atualizações são publicadas, alguma lógica é aplicada para minimizar o tamanho da atualização. Na maioria dos casos, apenas as diferenças entre a atualização mais recente e a atualização instalada no momento (isso é chamado de delta) no dispositivo são baixadas e aplicadas. No entanto, o tamanho do delta depende de dois fatores principais:
- A idade da última atualização no dispositivo; e 
- A fonte usada para baixar e aplicar atualizações. 

Quanto mais antigas as atualizações em um ponto de extremidade, maior será o download. No entanto, você também deve considerar a frequência de download. Um agendamento de atualização mais frequente pode resultar em mais uso de rede, enquanto um agendamento menos frequente pode resultar em tamanhos maiores de arquivo por download. 

Há cinco locais onde você pode especificar onde um ponto de extremidade deve obter atualizações: 

- [Microsoft Update](https://support.microsoft.com/help/12373/windows-update-faq)
- [Windows Serviço de Atualização do Servidor](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/core/servers/manage/updates)
- [Compartilhamento de arquivos de rede](#unc-share)
- Atualizações de inteligência de segurança para Microsoft Defender Antivírus e outros [antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates) da Microsoft (Sua política e registro podem ter isso listado como inteligência de segurança Centro de Proteção contra Malware da Microsoft (MMPC), seu nome anterior.)

Para garantir o melhor nível de proteção, o Microsoft Update permite versões rápidas, o que significa downloads menores com frequência. As Windows do Serviço de Atualização do Servidor, Microsoft Endpoint Configuration Manager e as fontes de inteligência de segurança da Microsoft oferecem atualizações menos frequentes. Assim, o delta pode ser maior, resultando em downloads maiores. 

> [!IMPORTANT]
> Se você definiu as atualizações de página de inteligência do [Microsoft Security](https://www.microsoft.com/security/portal/definitions/adl.aspx) como uma fonte de fallback após o Serviço de Atualização do Servidor Windows ou o Microsoft Update, as atualizações só serão baixadas de atualizações de inteligência de segurança quando a atualização atual for considerada desajustada. (Por padrão, são sete dias consecutivos em que não é possível aplicar atualizações do serviço Windows De atualização do servidor ou dos serviços do Microsoft Update).
> No entanto, você pode definir o número de dias antes que a [proteção seja relatada como desa data.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)<p>
> A partir de segunda-feira, 21 de outubro de 2019, as atualizações de inteligência de segurança serão assinadas exclusivamente pelo SHA-2. Os dispositivos devem ser atualizados para dar suporte ao SHA-2 para obter as atualizações mais recentes de inteligência de segurança. Para saber mais, confira [2019 SHA-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).

Cada fonte tem cenários típicos que dependem de como sua rede é configurada, além da frequência com que publicam atualizações, conforme descrito na tabela a seguir:

|Local | Cenário de exemplo |
|---|---|
|Windows Serviço de Atualização do Servidor | Você está usando o Windows De Atualização do Servidor para gerenciar atualizações para sua rede.|
|Microsoft Update | Você deseja que seus pontos de extremidade se conectem diretamente ao Microsoft Update. Isso pode ser útil para pontos de extremidade que se conectam irregularmente à sua rede corporativa ou se você não usar o Serviço de Atualização do Servidor Windows para gerenciar suas atualizações.|
|Compartilhamento de arquivos | Você tem dispositivos não conectados à Internet (como VMs). Você pode usar seu host de VM conectado à Internet para baixar as atualizações para um compartilhamento de rede, a partir do qual as VMs podem obter as atualizações. Consulte o [guia de implantação da VDI](deployment-vdi-microsoft-defender-antivirus.md) sobre como os compartilhamentos de arquivos podem ser usados em ambientes de infraestrutura de área de trabalho virtual (VDI).|
|Microsoft Endpoint Manager | Você está usando Microsoft Endpoint Manager para atualizar seus pontos de extremidade.|
|Atualizações de inteligência de segurança para Microsoft Defender Antivírus e outros antimalware da Microsoft (anteriormente chamado de MMPC) |[Certifique-se de que seus dispositivos sejam atualizados para dar suporte a SHA-2](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus). Microsoft Defender Antivírus As atualizações de inteligência de segurança são entregues por meio do Windows Update e, a partir de segunda-feira, 21 de outubro de 2019, as atualizações de inteligência de segurança serão assinadas exclusivamente pelo SHA-2. <br/>Baixe as atualizações de proteção mais recentes devido a uma infecção recente ou para ajudar a provisionar uma imagem forte e base para implantação [VDI.](deployment-vdi-microsoft-defender-antivirus.md) Essa opção geralmente deve ser usada apenas como uma fonte de fallback final, e não como a fonte primária. Ele só será usado se as atualizações não puderem ser baixadas do Serviço de Atualização do Servidor Windows ou do Microsoft Update por um [número especificado de dias.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)|

Você pode gerenciar a ordem na qual as fontes de atualização são usadas com a Política de Grupo, Microsoft Endpoint Configuration Manager, cmdlets do PowerShell e WMI.

> [!IMPORTANT]
> Se você definir Windows Server Update Service como local de download, deverá aprovar as atualizações, independentemente da ferramenta de gerenciamento usada para especificar o local. Você pode configurar uma regra de aprovação automática com Windows Server Update Service, que pode ser útil à medida que as atualizações chegam pelo menos uma vez por dia. Para saber mais, confira [sincronizar atualizações](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)de proteção de ponto de extremidade no Serviço de Atualização Windows Servidor Autônomo.

Os procedimentos neste artigo descrevem primeiro como definir a ordem e, em seguida, como configurar a opção **Compartilhamento** de arquivos se você a habilitar.

## <a name="use-group-policy-to-manage-the-update-location"></a>Usar a Política de Grupo para gerenciar o local de atualização

1. Em sua máquina de gerenciamento de Política de Grupo, abra o Console de Gerenciamento de Política de [Grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), clique com o botão direito do mouse no Objeto de Política de Grupo que você deseja configurar e clique em **Editar**.

2. No Editor **de Gerenciamento de Política de Grupo,** vá para **Configuração do computador.**

3. Clique **em Políticas** e modelos **administrativos.**

4. Expanda a árvore para **Windows componentes > Windows Defender > atualizações de assinatura e** configure as seguintes configurações:

   1.  Clique duas vezes na **configuração Definir a ordem das fontes para baixar** atualizações de inteligência de segurança e defina a opção como **Habilitado**.

   2.  Insira a ordem das fontes, separada por um único pipe, por exemplo: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC` , conforme mostrado na captura de tela a seguir.

   ![Captura de tela da configuração da política de grupo listando a ordem das fontes](images/defender/wdav-order-update-sources.png)

   3. Clique em **OK**. Isso definirá a ordem das fontes de atualização de proteção.

   4. Clique duas vezes na **configuração Definir compartilhamentos** de arquivos para baixar atualizações de inteligência de segurança e defina a opção **como Habilitado**.

   5. Insira a fonte de compartilhamento de arquivos. Se você tiver várias fontes, insira cada fonte na ordem em que elas devem ser usadas, separadas por um único pipe. Use [a notação UNC padrão](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) para denotar o caminho, por exemplo: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name` .  Se você não inserir nenhum caminho, essa fonte será ignorada quando a VM baixar atualizações.

   6. Clique em **OK**. Isso definirá a ordem dos compartilhamentos de arquivos quando essa fonte for referenciada na configuração Definir a ordem **das fontes...** da política de grupo.

> [!NOTE]
> Para Windows 10, versões 1703 até e incluindo 1809, o caminho da política é **Windows Components > Microsoft Defender Antivírus > Signature Updates** For Windows 10, versão 1903, o caminho da política é Windows Components > Microsoft Defender Antivírus > Security Intelligence **Updates**

## <a name="use-configuration-manager-to-manage-the-update-location"></a>Usar o Configuration Manager para gerenciar o local de atualização

Consulte [Configure Security intelligence Updates for Endpoint Protection](/configmgr/protect/deploy-use/endpoint-definition-updates) for details on configuring Microsoft Endpoint Manager (branch atual).


## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a>Usar cmdlets do PowerShell para gerenciar o local de atualização

Use os seguintes cmdlets do PowerShell para definir a ordem de atualização.

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```
Confira os seguintes artigos para obter mais informações:
- [Set-MpPreference -SignatureFallbackOrder](/powershell/module/defender/set-mppreference)
- [Set-MpPreference -SignatureDefinitionUpdateFileSharesSource](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [Usar cmdlets do PowerShell para configurar e executar Microsoft Defender Antivírus](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Cmdlets defender](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a>Use Windows Instrução de Gerenciamento (WMI) para gerenciar o local de atualização

Use o [ **método Set** da classe **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) para as seguintes propriedades:

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

Confira os seguintes artigos para obter mais informações:
- [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a>Usar o Gerenciamento de Dispositivo Móvel (MDM) para gerenciar o local da atualização

Consulte [CSP de política - Defender/SignatureUpdateFallbackOrder](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) para obter detalhes sobre como configurar o MDM.

## <a name="what-if-were-using-a-third-party-vendor"></a>E se estamos usando um fornecedor de terceiros?

Este artigo descreve como configurar e gerenciar atualizações para Microsoft Defender Antivírus. No entanto, fornecedores de terceiros podem ser usados para executar essas tarefas. 

Por exemplo, suponha que a Contoso tenha contratado a Fabrikam para gerenciar sua solução de segurança, que inclui Microsoft Defender Antivírus. A Fabrikam normalmente usa [Windows Instrumentação](./use-wmi-microsoft-defender-antivirus.md)de Gerenciamento, [cmdlets](./use-powershell-cmdlets-microsoft-defender-antivirus.md)do PowerShell ou Windows [linha de](./command-line-arguments-microsoft-defender-antivirus.md) comando para implantar patches e atualizações. 

> [!NOTE]
> A Microsoft não testa soluções de terceiros para gerenciar Microsoft Defender Antivírus.

<a id="unc-share"></a>
## <a name="create-a-unc-share-for-security-intelligence-updates"></a>Criar um compartilhamento UNC para atualizações de inteligência de segurança

Configurar um compartilhamento de arquivos de rede (UNC/unidade mapeada) para baixar atualizações de inteligência de segurança do site MMPC usando uma tarefa agendada.

1. No sistema no qual você deseja provisionar o compartilhamento e baixar as atualizações, crie uma pasta para a qual você salvará o script.
    ```DOS
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. Crie a pasta na qual você salvará as atualizações de assinatura.
    ```DOS
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. Baixe o script do PowerShell do [www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4).

4. Clique **em Download Manual**.

5. Clique **em Baixar o arquivo nupkg bruto.**

6. Extraia o arquivo.

7. Copie o arquivo SignatureDownloadCustomTask.ps1 para a pasta que você criou anteriormente, C:\Tool\PS-Scripts\ .

8. Use a linha de comando para configurar a tarefa agendada.
    > [!NOTE]
    > Há dois tipos de atualizações: completo e delta.
   - Para delta x64:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - Para x64 completo:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - Para delta x86:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - Para x86 completo:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

    > [!NOTE]
    > Quando as tarefas agendadas são criadas, você pode encontrá-los no Agendador de Tarefas em Microsoft\Windows\Windows Defender
9. Execute cada tarefa manualmente e verifique se você tem dados (mpam-d.exe, mpam-fe.exe e nis_full.exe) nas pastas a seguir (você pode ter escolhido locais diferentes):

   - C:\Temp\TempSigs\x86
   - C:\Temp\TempSigs\x64

   Se a tarefa agendada falhar, execute os seguintes comandos:

    ```DOS
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86"
    ```
    > [!NOTE]
    > Os problemas também podem ser devido à política de execução.
    
10. Crie um compartilhamento apontando para C:\Temp\TempSigs (por exemplo, \\ server\updates).
    > [!NOTE]
    > No mínimo, os usuários autenticados devem ter acesso a "Leitura".
11. De definir o local de compartilhamento na política para o compartilhamento.

    > [!NOTE]
    > Não adicione a pasta x64 (ou x86) no caminho. O mpcmdrun.exe o processo adiciona automaticamente.

## <a name="related-articles"></a>Artigos relacionados

- [Implantar Microsoft Defender Antivírus](deploy-manage-report-microsoft-defender-antivirus.md)
- [Gerenciar Microsoft Defender Antivírus e aplicar linhas de base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Gerenciar atualizações para pontos de extremidade que estão des date](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Gerenciar atualizações aplicadas com base em evento](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Gerenciar atualizações para dispositivos móveis e VMs](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus no Windows 10](microsoft-defender-antivirus-in-windows-10.md)
