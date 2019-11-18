---
title: Usar rótulos de confidencialidade com o Microsoft Teams, grupos do Office 365 e sites do SharePoint (visualização pública)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/13/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Você pode aplicar rótulos ao Microsoft Teams, grupos do Office 365 e sites do SharePoint.
ms.openlocfilehash: 5fc7fec199482449baf9174d6e854d0a5564faa6
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38684924"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a>Usar rótulos de confidencialidade com o Microsoft Teams, grupos do Office 365 e sites do SharePoint (visualização pública)

Ao criar rótulos de confidencialidade no [centro de conformidade da Microsoft 365](https://protection.office.com/), agora você pode aplicá-los ao Microsoft Teams, grupos do Office 365 e sites do SharePoint. Você pode associar políticas aos rótulos a serem controlados:

- Configurações públicas/privadas
- Acesso de convidados
- Acesso de dispositivos não gerenciados

Quando você aplica um rótulo a uma equipe ou grupo, o rótulo se aplica automaticamente ao site de equipe do SharePoint conectado e ao contrário.

Agora, você também pode habilitar os rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive. [Saiba mais](sensitivity-labels-sharepoint-onedrive-files.md).

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a>Sobre a visualização pública do Microsoft Teams, grupos do Office 365 e sites do SharePoint

Os rótulos de confidencialidade para o Microsoft Teams, os grupos do Office 365 e os sites do SharePoint são implantados gradualmente para locatários e podem ser alterados antes da versão final.

## <a name="overview"></a>Visão geral

Quando você publica rótulos de sensibilidade, os usuários no Office 365 têm acesso à mesma lista de rótulos.

Estas imagens mostram:

- Como a lista aparece quando você cria um novo site de equipe do SharePoint

- Ao exibir a lista no Word

![Um rótulo de confidencialidade ao criar um site de equipe do SharePoint](media/sensitivity-label-new-team-site.png)

![Um rótulo de confidencialidade exibido no aplicativo da área de trabalho Word](media/sensitivity-label-word.png)

## <a name="enable-this-preview-by-using-azure-powershell"></a>Habilitar esta visualização usando o Azure PowerShell

1. Entre no Azure como um administrador global usando o Azure PowerShell. Para obter instruções, consulte [entrar com o Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Execute o seguinte comando:

```powershell
  Connect-AzureAD
  $setting=(Get-AzureADDirectorySetting | where -Property DisplayName -Value "Group.Unified" -EQ)
  if ($setting -eq $null)
  {
    $template = Get-AzureADDirectorySettingTemplate -Id 62375ab9-6b52-47ed-826b-58e47e0e304b
    $setting = $template.CreateDirectorySetting()
    $setting["EnableMIPLabels"] = "True"
    New-AzureADDirectorySetting -DirectorySetting $setting
  }
  else
  {
    $setting["EnableMIPLabels"] = "True"
    Set-AzureADDirectorySetting -Id $setting.Id -DirectorySetting $setting
  }
```

O Office 365 não usa mais as classificações antigas para novos grupos e sites do SharePoint quando você habilita essa visualização. Se você usou a [classificação de site do Azure ad](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting ["classificationlist"]), os grupos e sites existentes ainda exibem as classificações antigas. Para exibir as novas classificações, converta-as. Para obter informações sobre como converter, confira [se você usou a classificação clássica de sites do Azure ad](#if-you-used-classic-azure-ad-site-classification).

## <a name="set-site-and-group-settings-when-you-create-sensitivity-labels"></a>Definir configurações de site e de grupo ao criar rótulos de confidencialidade

Após habilitar a visualização, siga estas etapas:

1. No centro de conformidade da Microsoft 365, selecione**Rótulos de sensibilidade**de **classificação** > .

2. Selecione **criar um rótulo**.

3. Selecione as opções desejadas e, na guia **configurações de site e grupo** , escolha:

    - Privacidade (pública/privada): privada significa que somente membros aprovados em sua organização podem ver o que está dentro do grupo. Qualquer outra pessoa em sua organização não consegue ver o que está no grupo. [Saiba mais](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - Acesso de convidados: você pode controlar se os convidados podem ser adicionados a um grupo. [Saiba mais sobre como gerenciar o acesso de convidados nos grupos do Office 365](/office365/admin/create-groups/manage-guest-access-in-groups)
    - Dispositivos não gerenciados: essa configuração permite bloquear ou limitar o acesso ao conteúdo do SharePoint de dispositivos que não são internos ou compatíveis com o AD híbrido no Intune. Se você selecionar dispositivos não gerenciados, precisará ir para o Azure AD para concluir a configuração da política. Para obter informações, consulte [controlar o acesso de dispositivos não gerenciados](/sharepoint/control-access-from-unmanaged-devices).

![A guia Configurações de site e grupo](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> Somente as configurações de site e grupo terão efeito quando você aplicar um rótulo a uma equipe, grupo ou site. Outras configurações, como a criptografia e a marcação de conteúdo, não são aplicadas a todo o conteúdo dentro da equipe, grupo ou site. Da mesma forma, se você criar um rótulo e não ativar as configurações de site e de grupo, o rótulo ainda estará disponível quando os usuários criarem equipes, grupos e sites, mas não fizer nada quando os usuários a aplicarem.

[Saiba como publicar um rótulo de confidencialidade](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="apply-a-sensitivity-label-to-a-new-team"></a>Aplicar um rótulo de confidencialidade a uma nova equipe

Os usuários podem selecionar rótulos de confidencialidade quando criarem novas equipes no Microsoft Teams. Quando eles selecionam o nível de sensibilidade, a configuração de privacidade muda conforme necessário. Dependendo da configuração de acesso de convidados selecionada para o rótulo, os usuários podem ou não adicionar pessoas de fora da organização para a equipe.

![A configuração de privacidade ao criar uma nova equipe](media/privacy-setting-new-team.png)

Depois de criar a equipe, o rótulo de confidencialidade aparecerá no canto superior direito de todos os canais.

![O rótulo de confidencialidade aparece na equipe](media/privacy-setting-teams.png)

O serviço aplica automaticamente o mesmo rótulo de confidencialidade ao grupo do Office 365 e ao site de equipe do SharePoint conectado.

## <a name="apply-a-sensitivity-label-to-a-new-group"></a>Aplicar um rótulo de confidencialidade a um novo grupo

No Outlook na Web, a caixa nova **sensibilidade** contém rótulos publicados. Se os usuários quiserem mais informações, poderão clicar no ícone ajuda para ler os detalhes sobre os rótulos disponíveis e as políticas associadas.

![Criar um grupo e selecionar uma opção em sensibilidade](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a>Aplicar um rótulo de confidencialidade a um novo site

Administradores e usuários finais podem selecionar rótulos de confidencialidade ao criar sites de equipe e sites de comunicação modernos.

[Saiba como criar um site no novo centro de administração do SharePoint](/sharepoint/create-site-collection)

Quando os usuários criam sites de comunicação e equipe modernos, um rótulo de confidencialidade já estará selecionado por padrão. Os usuários podem selecionar o ícone de ajuda para saber mais sobre os rótulos.

![Criar um site e selecionar uma opção em sensibilidade](media/sensitivity-label-new-communication-site.png)

Quando os usuários navegam até o site, eles podem ver o nome do rótulo e as políticas aplicadas.

![Um site com um rótulo de sensibilidade aplicado](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>Gerenciar rótulos de sensibilidade no centro de administração do SharePoint

Para exibir e editar os rótulos, use a página sites ativos no novo centro de administração do SharePoint.

![A coluna sensibilidade na página sites ativos](media/manage-site-sensitivity-labels.png)

[Saiba mais sobre o gerenciamento de sites no novo centro de administração do SharePoint](/sharepoint/manage-sites-in-new-admin-center).

## <a name="change-site-and-group-settings-for-a-label"></a>Alterar as configurações de site e de grupo de um rótulo

Como prática recomendada, não altere as configurações depois de aplicar um rótulo a várias equipes, grupos ou sites. Se for necessário fazer uma alteração, você precisará usar um script do PowerShell do Azure AD para aplicar as atualizações manualmente. Esse método garante que todas as equipes, sites e grupos existentes imponham a nova configuração.

## <a name="support-for-the-new-sensitivity-labels"></a>Suporte para os novos rótulos de confidencialidade

Os seguintes aplicativos e serviços suportam os rótulos de confidencialidade nesta visualização:

- Centro de conformidade do Microsoft 365
- SharePoint
- Outlook Online
- Teams
- Centro de administração do SharePoint
- Centro de administração do Azure AD

Você não pode usar os seguintes aplicativos e serviços para criar grupos do Office 365 com os novos rótulos de sensibilidade:

- Outlook para Mac
- Móvel do Outlook  
- Área de trabalho do Outlook para Windows
- Formulários  
- Dynamics 365  
- Yammer  
- Stream  
- Planner  
- Project  
- PowerBI  
- Centro de administração do Microsoft Teams  
- Centro de administração do Microsoft 365  
- Centro de administração do Exchange

## <a name="if-you-used-classic-azure-ad-site-classification"></a>Se você usou a classificação clássica de site do Azure AD

O Office 365 não oferece mais suporte às classificações antigas para novos grupos e sites do SharePoint quando você habilita essa visualização. No entanto, os grupos e sites existentes ainda exibem as classificações antigas, a menos que você as converta. As classificações antigas incluem a classificação de sites "modernos" que você configurou, possivelmente por meio do Azure AD PowerShell ou da biblioteca principal de PnP `ClassificationList` , que definiu valores para a configuração.

Por exemplo, no PowerShell:

```powershell
   ($setting["ClassificationList"])
```

Para obter mais informações sobre o antigo método de classificação, confira [classificação de sites "modernos" do SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).

Com base em sua implantação atual, você tem duas opções para converter suas classificações antigas para as novas classificações.

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>Se você nunca usou rótulos de confidencialidade (rótulos unificados de proteção de informações da Microsoft) para arquivos e email

Recomendamos que você:

1. Crie novos rótulos de sensibilidade no centro de conformidade da Microsoft 365 com os mesmos nomes de suas classificações existentes.
2. Use o PowerShell para aplicar os novos rótulos aos grupos existentes do Office 365 e sites do SharePoint usando o mapeamento de nome.
3. Exclua as classificações antigas.

Os aplicativos e serviços que dão suporte aos novos rótulos de sensibilidade irão mostrá-los. Você cria novas equipes, grupos e sites com os novos rótulos. Os usuários ainda podem criar grupos de aplicativos e serviços que não dão suporte aos novos rótulos. No entanto, os usuários não podem aplicar um rótulo a esses grupos. Use o PowerShell para aplicar os novos rótulos de sensibilidade a esses grupos.

Você pode manter suas classificações antigas; no entanto, é altamente recomendável usar o PowerShell para aplicar os novos rótulos de sensibilidade a esses grupos.

Os aplicativos e serviços que dão suporte aos novos rótulos de sensibilidade serão criados com os novos rótulos. Quando os usuários criam grupos de aplicativos e serviços que não dão suporte aos novos rótulos, eles podem selecionar uma classificação.

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>Se você usar rótulos de confidencialidade (rótulos unificados de proteção de informações da Microsoft) para arquivos e email

Assim que você habilitar esta visualização, vá para cada etiqueta no centro de conformidade da Microsoft 365 e aplique as políticas desejadas para sites e grupos. Os usuários começarão a ver seus rótulos existentes disponíveis para sites e grupos.

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a>Prepare o Shell de gerenciamento do SharePoint Online antes de rerotular grupos do Office 365

Antes de aplicar novos rótulos, verifique se você está executando o Shell de gerenciamento do SharePoint Online mais recente. Se você já tiver a versão mais recente, poderá ir em frente e [rerotular grupos do Office 365 com novos rótulos de sensibilidade](#relabel-office-365-groups-with-new-sensitivity-labels).

Para preparar o Shell de gerenciamento do SharePoint Online para a visualização:

1. Se você instalou uma versão anterior do Shell de gerenciamento do SharePoint Online, vá para **Adicionar ou remover programas** e desinstalar o "Shell de gerenciamento do SharePoint Online".

2. Em um navegador da Web, vá até a página centro de download e [Baixe o Shell de gerenciamento do SharePoint Online mais recente](https://go.microsoft.com/fwlink/p/?LinkId=255251).

3. Selecione seu idioma e clique em **baixar**.

4. Escolha entre o arquivo x64 e x86. msi. Baixe o arquivo x64 se você executar a versão de 64 bits do Windows ou o arquivo x86 se você estiver executando a versão de 32 bits. Se você não souber, confira [qual versão do sistema operacional Windows estou executando?](https://support.microsoft.com/help/13443/windows-which-operating-system).

5. Depois de baixar o arquivo, execute o arquivo e siga as etapas no assistente de instalação.

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a>Reetiquetar grupos do Office 365 com novos rótulos de confidencialidade

1. Verifique se você está usando a versão mais recente do Shell de gerenciamento do SharePoint Online. Para obter instruções, consulte [preparar o Shell de gerenciamento do SharePoint Online antes de rerotular grupos do Office 365](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).

2. Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global ou de administrador do SharePoint no Office 365, conecte-se ao Shell de gerenciamento do SharePoint Online. Veja como em [Introdução ao Shell de Gerenciamento do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

3. Execute o seguinte comando para obter a lista de rótulos de confidencialidade e seus GUIDs.

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. Anote o GUID do rótulo que você deseja substituir. Por exemplo, o rótulo "geral".

5. Use o seguinte comando para obter a lista de grupos que têm a classificação "geral". Ao executar este comando, você se conectará ao PowerShell do Exchange Online e executará o cmdlet Get-unificado.

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   ```

6. Para cada grupo, adicione o novo GUID de rótulo de confidencialidade.

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
