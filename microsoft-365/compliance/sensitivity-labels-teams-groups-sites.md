---
title: Use etiquetas de confidencialidade com o Microsoft Teams, grupos do Office 365 e sites do SharePoint (visualização pública)
f1.keywords:
- NOCSH
ms.author: krowley
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Você pode aplicar rótulos ao Microsoft Teams, grupos do Office 365 e sites do SharePoint.
ms.openlocfilehash: 7fd19d9d8f84bd6463d61aec68dbd86c4fc627c0
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601558"
---
# <a name="use-sensitivity-labels-with-microsoft-teams-office-365-groups-and-sharepoint-sites-public-preview"></a>Use etiquetas de confidencialidade com o Microsoft Teams, grupos do Office 365 e sites do SharePoint (visualização pública)

Ao criar rótulos de confidencialidade no [centro de conformidade do Microsoft 365](https://protection.office.com/), você pode aplicá-los ao Microsoft Teams, grupos do Office 365 e sites do SharePoint. Você pode associar políticas a rótulos para controlar:

- Configurações público/privada
- Acesso de convidados
- Acesso de dispositivos não gerenciados

Quando você aplica um rótulo a uma equipe ou grupo, o rótulo se aplica automaticamente ao site de equipe do SharePoint conectada e vice-versa.

Agora você também pode habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive. Para saber mais, confira [Habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive (visualização pública)](sensitivity-labels-sharepoint-onedrive-files.md)

## <a name="about-the-public-preview-for-microsoft-teams-office-365-groups-and-sharepoint-sites"></a>Sobre a visualização pública do Microsoft Teams, grupos do Office 365 e sites do SharePoint

Os rótulos de confidencialidade do Microsoft Teams, grupos do Office 365 e de sites do SharePoint são gradualmente implementados para locatários e podem ser alterados antes do lançamento final.

Esta versão pública não funciona com as CDNs (redes de distribuição de conteúdo do Office 365).

## <a name="overview"></a>Visão Geral

Quando você publica rótulos de confidencialidade, os usuários do Office 365 têm acesso à mesma lista de etiquetas.

Essas imagens são exibidas:

- Como a lista é exibida quando você cria um novo site de equipe do SharePoint

- Quando você visualiza a lista no Word

Por exemplo:

![Um rótulo de confidencialidade ao criar um site de equipe do SharePoint](media/sensitivity-label-new-team-site.png)

![Um rótulo de confidencialidade exibido no aplicativo Word para área de trabalho](media/sensitivity-label-word.png)

## <a name="enable-this-preview"></a>Habilitar esta visualização

Você deve usar a versão de visualização do [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) (nome do módulo **AzureADPreview**) para habilitar essa visualização de rótulos de confidencialidade no Microsoft Teams, nos grupos do Office 365 e sites do SharePoint:

- Caso ainda não tenha instalado uma versão do módulo Azure AD PowerShell antes, confira [instalando o módulo Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) e siga as instruções para instalar a versão de visualização pública.

- Se você tiver a versão de disponibilidade geral 2.0 do módulo do Azure AD PowerShell (AzureAD) instalada, desinstale-a executando `Uninstall-Module AzureAD` em sua sessão do PowerShell e instale a versão de visualização executando `Install-Module AzureADPreview`.

- Se você já tiver instalado a versão de visualização, execute `Install-Module AzureADPreview` para ter certeza de que esta é a versão mais recente deste módulo.

Agora você está pronto para habilitar a visualização de etiquetas de confidencialidade com o Microsoft Teams, grupos do Office 365 e sites do SharePoint:

1. Em uma sessão do PowerShell, usando uma conta corporativa ou de estudante com privilégios de administrador global, conecte-se ao Azure Active Directory. Por exemplo, execute:
    
    ```powershell
    Connect-AzureAD
    ````
    
    Para obter instruções completas, confira [Conectar ao Azure AD](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#connect-to-azure-ad).

2. Execute os seguintes comandos:
    
    ```powershell
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
    
    > [!NOTE]
    > O Office 365 não usará mais as classificações antigas para novos grupos e sites do SharePoint quando você habilitar essa visualização. Se você usar a [classificação de sites do Azure AD](/sharepoint/dev/solution-guidance/modern-experience-site-classification) ($setting["ClassificationList"]), os grupos e sites existentes ainda exibirão as classificações antigas. Para exibir as novas classificações, converta-as. Para obter informações sobre como convertê-los, consulte [Se você usou a classificação clássica do site do Azure AD](#if-you-used-classic-azure-ad-site-classification). 

3. Na mesma sessão do PowerShell, conecte-se ao Centro de Conformidade e Segurança usando uma conta corporativa ou de estudante com privilégios de administrador global. Para mais instruções, confira [conecte-se ao PowerShell do Centro de Conformidade e Segurança do Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

4. Execute os seguintes comandos para sincronizar os rótulos com o Azure AD, para que eles possam ser usados com grupos do Office 365:
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Execute-AzureAdLabelSync
    ```
## <a name="set-site-and-group-settings-when-you-create-or-edit-sensitivity-labels"></a>Definir as configurações de site e grupo quando ao criar ou editar rótulos de confidencialidade

Depois de habilitar a visualização, use as etapas a seguir para criar ou editar rótulos de confidencialidade. Você deve concluir essas etapas para os novos rótulos de confidencialidade para trabalhar com sites e grupos, mesmo que você já tenha os rótulos definidos. As alterações nessas configurações podem levar até 24 horas para serem sincronizadas.

1. No Centro de Conformidade do Microsoft 365, selecione **Classificação** > **Rótulos de confidencialidade**.

2. Selecione **Criar um rótulo**. Se você já tiver um rótulo, vá para a próxima etapa.

3. Selecione as opções desejadas e, em seguida, na guia **Configurações de site e grupo**, escolha:
    
    - Privacidade (pública/privada): Privada significa que somente membros aprovados da sua organização podem ver o que está dentro do grupo. Outras pessoas em sua organização não conseguem ver o que há no grupo. [Saiba mais](https://support.office.com/article/36236e39-26d3-420b-b0ac-8072d2d2bedc)
    - Acesso de convidados: você pode controlar se os convidados podem ser adicionados a um grupo. [Saiba mais sobre como gerenciar o acesso de convidados em grupos do Office 365](/office365/admin/create-groups/manage-guest-access-in-groups)
    - Dispositivos não gerenciados: essa configuração permite bloquear ou limitar o acesso ao conteúdo do SharePoint de dispositivos que não são híbridos ao AD ou compatíveis com o Intune. Se você selecionar dispositivos não gerenciados, deverá ir para o Azure AD para concluir a configuração da política. Para mais informações, confira [Controlar o acesso de dispositivos não gerenciados](/sharepoint/control-access-from-unmanaged-devices).
    
    ![Guia configurações de site e grupo](media/edit-sensitivity-label-site-group.png)

> [!IMPORTANT]
> Somente as configurações de site e grupo entrarão em vigor quando você aplicar um rótulo a uma equipe, grupo ou site. Outras configurações, como a criptografia e a marcação de conteúdo, não são aplicadas a todo o conteúdo na equipe, grupo ou site.
> 
> Da mesma forma, se você criar um rótulo e não ativar as configurações de site e grupo, ele continuará disponível quando os usuários criarem equipes, grupos e sites, mas será classificado sem aplicar nenhuma configuração.

[Saiba mais sobre como publicar rótulos de confidencialidade](/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do)

## <a name="sensitivity-label-management"></a>Gerenciamento de rótulo de confidencialidade

> [!WARNING]
> Criar, modificar e excluir rótulos de confidencialidade que você usa para o Microsoft Teams, grupos do Office 365 e sites do SharePoint exige uma coordenação cuidadosa com as políticas de rótulo de publicação para os usuários. 

Evite erros de criação para sites e grupos que possam afetar todos os usuários usando as diretrizes a seguir.

**Criar e publicar rótulos:**

Depois de criar e publicar um rótulo de confidencialidade, pode levar até 24 horas para que o rótulo se torne visível para usuários em equipes, grupos e sites. Use as etapas a seguir para publicar um rótulo para todos os usuários no locatário:

1. Crie o rótulo de confidencialidade e publique-o para apenas algumas contas de usuários no locatário.

2. Aguarde 24 horas.

3. Após essas 24 horas, use uma das contas de usuário especificadas na etapa 1 para criar uma equipe, um grupo do Office 365 ou um site do SharePoint com o rótulo que você criou na etapa 1.

4. Se não houver erros durante a operação de criação da etapa 3, publique o rótulo para todos os usuários em seu locatário. Se houver erros, contate o [suporte da Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

**Modificar e excluir rótulos publicados:**

Se você modificar ou excluir um rótulo de confidencialidade incluído em uma ou mais políticas de rótulo, essas ações poderão resultar em falhas de criação para todas as equipes, grupos e sites. Para evitar essa situação, use as instruções a seguir:

1. Remova o rótulo de confidencialidade de todas as políticas de rótulo que incluam o rótulo.

2. Aguarde por 48 horas.

3. Após as 48 horas de espera, experimente criar uma equipe, grupo ou site e confirme se o rótulo não está mais visível.

4. Se a etiqueta de confidencialidade não estiver visível, agora você pode modificá-la ou excluí-la com segurança. Se o rótulo ainda estiver visível, contate o [suporte da Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

## <a name="troubleshoot-sensitivity-label-deployment"></a>Solucionar problemas de implantação de rótulo de confidencialidade

### <a name="labels-not-visible-after-publishing"></a>Rótulos não visíveis após a publicação
Se você tiver problemas ao criar uma equipe ou grupo do Office 365 depois de habilitar essas configurações ou modificar a descrição de uma etiqueta de confidencialidade, salve o rótulo, aguarde algumas horas e, em seguida, tente criar a equipe ou o grupo novamente. Para saber mais, confira [Agendar a distribuição após criar ou alterar um rótulo de confidencialidade](sensitivity-labels-sharepoint-onedrive-files.md#schedule-roll-out-after-you-create-or-change-a-sensitivity-label).

Se você ainda não conseguir ver o novo rótulo de confidencialidade do SharePoint Online, contate o [suporte da Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

### <a name="team-group-or-sharepoint-site-creation-errors"></a>Erros de criação de site de equipe, grupo ou SharePoint
Se ocorrerem erros de criação durante a visualização pública, você tem duas opções:

- Certifique-se de que os rótulos de confidencialidade não sejam obrigatórios para qualquer usuário.

- Você pode desativar os rótulos de confidencialidade do Microsoft Teams, dos grupos do Office 365 e de sites do SharePoint, usando as mesmas instruções de[Habilite esta seção de visualização](#enable-this-preview) nesta página. No entanto, para desativar a visualização, procure a linha `$setting["EnableMIPLabels"] = "True"` e altere o valor de **Verdadeiro** para **Falso**.

## <a name="apply-a-sensitivity-label-to-a-new-team"></a>Aplicar um rótulo de confidencialidade a uma nova equipe

Os usuários podem selecionar os rótulos de confidencialidade ao criar novas equipes no Microsoft Teams. Quando eles selecionam o nível de confidencialidade, a configuração de privacidade é alterada conforme necessário. Dependendo da configuração de acesso de convidado que você selecionou para a etiqueta, os usuários podem ou não adicionar pessoas de fora da organização para a equipe.

[Saiba mais sobre Rótulos de confidencialidade](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![A configuração de privacidade ao criar uma nova equipe](media/privacy-setting-new-team.png)

Depois de criar a equipe, o rótulo de confidencialidade aparecerá no canto superior direito de todos os canais.

![O rótulo de confidencialidade aparece na equipe](media/privacy-setting-teams.png)

O serviço aplica automaticamente o mesmo rótulo de confidencialidade ao grupo do Office 365 e ao site de equipe do SharePoint conectado.

## <a name="apply-a-sensitivity-label-to-a-new-group"></a>Aplicar um rótulo de confidencialidade a um novo grupo

No Outlook na Web, a nova caixa de **confidencialidade** contém rótulos publicados. Se os usuários quiserem mais informações, eles poderão clicar no ícone ajuda para ler detalhes sobre os rótulos disponíveis e políticas associadas.

![Criando um grupo e selecionando uma opção em Confidencialidade](media/sensitivity-label-new-group.png)

## <a name="apply-a-sensitivity-label-to-a-new-site"></a>Aplicar um rótulo de confidencialidade a um novo site

Os administradores e os usuários finais podem selecionar os rótulos de confidencialidade ao criar sites de equipe e sites de comunicação modernos.

Saiba como [Criar um site no novo centro de administração do SharePoint](/sharepoint/create-site-collection)

Quando os usuários criam sites modernos de comunicação e equipe, um rótulo de confidencialidade já estará selecionado por padrão. Os usuários podem selecionar o ícone de ajuda para saber mais sobre os rótulos.

![Criando um site e selecionando uma opção de confidencialidade](media/sensitivity-label-new-communication-site.png)

Quando os usuários acessam o site, eles podem ver o nome do rótulo e as políticas aplicadas.

![Um site com uma etiqueta de confidencialidade aplicada](media/sensitivity-label-site.png)

## <a name="manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>Gerenciar rótulos de confidencialidade no centro de administração do SharePoint

Para exibir e editar os rótulos, use a página de sites ativas no novo centro de administração do SharePoint.

![A coluna Confidencialidade na página sites ativos](media/manage-site-sensitivity-labels.png)

[Saiba mais sobre como gerenciar sites no novo centro de administração do SharePoint](/sharepoint/manage-sites-in-new-admin-center).

## <a name="change-site-and-group-settings-for-a-label"></a>Alterar as configurações de um título

Sempre que você alterar as configurações de site e grupo de um rótulo, deverá executar os seguintes comandos do PowerShell para que suas equipes, sites e grupos possam usar as novas configurações. Como prática recomendada, não altere as configurações de site e grupo de um rótulo após aplicá-lo a várias equipes, grupos ou sites.

1. Execute os seguintes comandos para se conectar ao PowerShell do Centro de Conformidade e Segurança do Office 365, e obter a lista de rótulos de confidencialidade e seus GUIDs.
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid
    ```

2. Anote o GUID do rótulo ou os rótulos que você alterou.

3. Conecte-se agora ao PowerShell do Exchange Online e execute o cmdlet Get-UnifiedGroup, especificando o GUID do rótulo no lugar do GUID de exemplo de "e48058ea-98e8-4940-8db0-ba1310fd955e": 
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    $Groups= Get-UnifiedGroup | Where {$_.SensitivityLabel  -eq "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

4. Para cada grupo, aplique novamente o rótulo de confidencialidade, especificando o GUID do rótulo no lugar do GUID de exemplo de "e48058ea-98e8-4940-8db0-ba1310fd955e":
    
    ```powershell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "e48058ea-98e8-4940-8db0-ba1310fd955e"}
    ```

## <a name="support-for-the-new-sensitivity-labels"></a>Suporte para os novos rótulos de confidencialidade

Os seguintes aplicativos e serviços oferecem suporte a rótulos de confidencialidade nesta visualização:

- Centro de conformidade do Microsoft 365
- SharePoint
- Outlook na Web
- Teams
- Centro de administração do SharePoint
- Centro de Administração do Microsoft Azure AD

Não é possível usar os seguintes aplicativos e serviços para criar grupos do Office 365 com os novos rótulos de confidencialidade:

- Outlook para Mac
- Outlook Mobile  
- Área de trabalho do Outlook para Windows
- Forms  
- Dynamics 365  
- Yammer  
- Stream  
- Planner  
- Project  
- PowerBI  
- Centro de administração do Teams  
- Centro de administração do Microsoft 365  
- Centro de administração do Exchange

## <a name="if-you-used-classic-azure-ad-site-classification"></a>Se você usou a classificação clássica do site do Azure AD

O Office 365 já não será mais compatível com as classificações antigas para novos grupos e sites do SharePoint quando você habilitar essa visualização. No entanto, os grupos e sites existentes ainda exibem as classificações antigas, a menos que você as converta. As classificações antigas incluem a classificação de sites "modernos" que você configurou, possivelmente por meio do Azure AD PowerShell ou da biblioteca PnP Core, que definiu valores para a configuração do `ClassificationList`.

Por exemplo, no PowerShell:

```powershell
   ($setting["ClassificationList"])
```

Para obter mais informações sobre o método antigo de classificação, confira [Classificação de sites "modernos" do SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).

Com base na implantação atual, você tem duas opções para converter as classificações antigas em novas classificações.

### <a name="if-you-never-used-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>Caso nunca tenha usado rótulos de confidencialidade (rótulos de proteção de informações unificados da Microsoft) para arquivos e e-mail

Recomendamos que você:

1. Crie novos rótulos de confidencialidade no centro de conformidade do Microsoft 365 que tenham os mesmos nomes das suas classificações existentes.
2. Use o PowerShell para aplicar os novos rótulos aos grupos existentes do Office 365 e aos sites do SharePoint usando mapeamento de nomes.
3. Exclua as classificações antigas.

Os aplicativos e serviços que oferecem suporte aos novos rótulos de confidencialidade serão mostrados. Você cria novas equipes, grupos e sites com os novos rótulos. Os usuários ainda podem criar grupos de aplicativos e serviços que não têm suporte para os novos rótulos. No entanto, os usuários não podem aplicar um rótulo a esses grupos. Use o PowerShell para aplicar os novos rótulos de confidencialidade para esses grupos.

Você pode manter suas classificações antigas. no entanto, é altamente recomendável usar o PowerShell para aplicar os novos rótulos de confidencialidade a esses grupos.

Os aplicativos e serviços que oferecem suporte aos novos rótulos de confidencialidade serão criados com os novos rótulos. Quando os usuários criam grupos de aplicativos e serviços que não têm suporte para os novos rótulos, eles podem selecionar uma classificação.

### <a name="if-you-use-sensitivity-labels-unified-microsoft-information-protection-labels-for-files-and-email"></a>Se você usa rótulos de confidencialidade(rótulos de proteção de informações unificados da Microsoft) para arquivos e e-mail

Assim que você habilitar essa visualização, vá para cada etiqueta no centro de conformidade do Microsoft 365 e aplique as políticas desejadas para sites e grupos. Os usuários começarão a ver seus rótulos existentes disponíveis para sites e grupos.

### <a name="prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups"></a>Preparar o Shell de gerenciamento do SharePoint Online antes de rotular novamente os grupos do Office 365

Antes de aplicar novos rótulos, certifique-se de estar executando o Shell de gerenciamento do SharePoint Online mais recente. Se você já tem a versão mais recente, é possível prosseguir e [Rotular novamente os grupos do Office 365 com novos rótulos de confidencialidade](#relabel-office-365-groups-with-new-sensitivity-labels).

Para preparar o Shell de Gerenciamento do SharePoint Online para a visualização:

1. Se você tiver instalado uma versão anterior do Shell de Gerenciamento do SharePoint Online, vá para **Adicionar ou remover programas** e desinstale o “Shell de Gerenciamento do SharePoint Online”.

2. Em um navegador da Web, acesse a página do centro de download e [Baixe o Shell de gerenciamento do SharePoint Online mais recente](https://go.microsoft.com/fwlink/p/?LinkId=255251).

3. Escolha o idioma e clique em **Salvar**.

4. Escolha entre o arquivo .msi x64 e x86. Baixe o arquivo x64 se você estiver executando a versão de 64 bits do Windows ou o arquivo x86 se estiver executando a versão de 32 bits. Se não souber, confira [Qual versão do sistema operacional Windows estou executando?](https://support.microsoft.com/help/13443/windows-which-operating-system).

5. Depois de baixar o arquivo, execute o arquivo e siga as etapas no assistente de configuração.

### <a name="relabel-office-365-groups-with-new-sensitivity-labels"></a>Rotule novamente os grupos do Office 365 com novas etiquetas de confidencialidade

1. Verifique se você está usando a versão mais recente do Shell de gerenciamento do SharePoint Online. Para obter instruções, confira [Preparar o Shell de gerenciamento do SharePoint Online antes de rotular novamente os grupos do Office 365](#prepare-the-sharepoint-online-management-shell-before-you-relabel-office-365-groups).

2. Usando uma conta corporativa ou de estudante com privilégios de administrador global ou de administrador do SharePoint no Office 365, conecte-se ao Shell de gerenciamento do SharePoint Online. Veja como em [Introdução ao Shell de Gerenciamento do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

3. Execute o seguinte comando para obter a lista de rótulos de confidencialidade e suas GUIDs.

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Authentication Basic -AllowRedirection -Credential $UserCredential
    Import-PSSession $Session
    Get-Label |ft Name, Guid  
    ```

4. Anote o GUID do rótulo que você deseja substituir. Por exemplo, o rótulo "geral".

5. Use o seguinte comando para obter a lista de grupos que têm a classificação "geral". Ao executar esse comando, você se conectará ao PowerShell do Exchange Online e executará o cmdlet Get-UnifiedGroup.

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $UserCredential = Get-Credential
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   Import-PSSession $Session
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. Para cada grupo, adicione o novo GUID de rótulo de confidencialidade.

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```
