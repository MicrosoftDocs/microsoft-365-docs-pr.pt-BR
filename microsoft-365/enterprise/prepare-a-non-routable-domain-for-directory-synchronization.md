---
title: Preparar um domínio não roteável para sincronização de diretórios
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365E_SetupDirSyncLocalDir
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: e7968303-c234-46c4-b8b0-b5c93c6d57a7
description: Saiba o que fazer se você tiver um domínio não stável associado às suas contas de usuário locais antes de sincroná-las com seu locatário do Microsoft 365.
ms.openlocfilehash: e4d0e020c5792c610d501c33e8f3d5131b7a1ff0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927391"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a><span data-ttu-id="194d6-103">Preparar um domínio não roteável para sincronização de diretórios</span><span class="sxs-lookup"><span data-stu-id="194d6-103">Prepare a non-routable domain for directory synchronization</span></span>

<span data-ttu-id="194d6-104">Ao sincronizar seu diretório local com o Microsoft 365, você precisa ter um domínio verificado no Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="194d6-104">When you synchronize your on-premises directory with Microsoft 365, you have to have a verified domain in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="194d6-105">Somente os UPNs (Nomes de Entidades de Usuário) associados ao domínio do AD DS (Serviços de Domínio do Active Directory) local são sincronizados.</span><span class="sxs-lookup"><span data-stu-id="194d6-105">Only the User Principal Names (UPNs) that are associated with the on-premises Active Directory Domain Services (AD DS) domain are synchronized.</span></span> <span data-ttu-id="194d6-106">No entanto, qualquer UPN que contenha um domínio não stável, como ".local" (exemplo: billa@contoso.local), será sincronizado com um domínio .onmicrosoft.com (exemplo: billa@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="194d6-106">However, any UPN that contains a non-routable domain, such as ".local" (example: billa@contoso.local), will be synchronized to an .onmicrosoft.com domain (example: billa@contoso.onmicrosoft.com).</span></span> 

<span data-ttu-id="194d6-107">Se você usa atualmente um domínio ".local" para suas contas de usuário no AD DS, é recomendável alterá-las para usar um domínio verificado, como o billa@contoso.com, para sincronizar corretamente com seu domínio do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="194d6-107">If you currently use a ".local" domain for your user accounts in AD DS, it's recommended that you change them to use a verified domain, such as billa@contoso.com, in order to properly synchronize with your Microsoft 365 domain.</span></span>
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a><span data-ttu-id="194d6-108">E se eu tiver apenas um domínio local ".local"?</span><span class="sxs-lookup"><span data-stu-id="194d6-108">What if I only have a ".local" on-premises domain?</span></span>

<span data-ttu-id="194d6-109">Você usa o Azure AD Connect para sincronizar seu AD DS com o locatário do Azure AD do locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="194d6-109">You use Azure AD Connect for synchronizing your AD DS to the Azure AD tenant of your Microsoft 365 tenant.</span></span> <span data-ttu-id="194d6-110">Para obter mais informações, consulte Integrando suas identidades locais [ao Azure AD](/azure/architecture/reference-architectures/identity/azure-ad).</span><span class="sxs-lookup"><span data-stu-id="194d6-110">For more information, see [Integrating your on-premises identities with Azure AD](/azure/architecture/reference-architectures/identity/azure-ad).</span></span>
  
<span data-ttu-id="194d6-111">O Azure AD Connect sincroniza o UPN e a senha dos usuários para que os usuários possam entrar com as mesmas credenciais que usam no local.</span><span class="sxs-lookup"><span data-stu-id="194d6-111">Azure AD Connect synchronizes your users' UPN and password so that users can sign in with the same credentials they use on-premises.</span></span> <span data-ttu-id="194d6-112">No entanto, o Azure AD Connect só sincroniza usuários com domínios verificados pelo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="194d6-112">However, Azure AD Connect only synchronizes users to domains that are verified by Microsoft 365.</span></span> <span data-ttu-id="194d6-113">Isso significa que o domínio também é verificado pelo Azure AD porque as identidades do Microsoft 365 são gerenciadas pelo Azure AD.</span><span class="sxs-lookup"><span data-stu-id="194d6-113">This means that the domain also is verified by Azure AD because Microsoft 365 identities are managed by Azure AD.</span></span> <span data-ttu-id="194d6-114">Em outras palavras, o domínio deve ser um domínio válido da Internet (como, .com, .org, .net, .us).</span><span class="sxs-lookup"><span data-stu-id="194d6-114">In other words, the domain has to be a valid Internet domain (such as, .com, .org, .net, .us).</span></span> <span data-ttu-id="194d6-115">Se o AD DS interno usa apenas um domínio não stável (por exemplo, ".local"), isso não poderá corresponder ao domínio verificado que você tem para seu locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="194d6-115">If your internal AD DS only uses a non-routable domain (for example, ".local"), this can't possibly match the verified domain you have for your Microsoft 365 tenant.</span></span> <span data-ttu-id="194d6-116">Você pode corrigir esse problema alterando seu domínio principal no AD DS local ou adicionando um ou mais sufixos UPN.</span><span class="sxs-lookup"><span data-stu-id="194d6-116">You can fix this issue by either changing your primary domain in your on-premises AD DS, or by adding one or more UPN suffixes.</span></span>
  
### <a name="change-your-primary-domain"></a><span data-ttu-id="194d6-117">Alterar seu domínio primário</span><span class="sxs-lookup"><span data-stu-id="194d6-117">Change your primary domain</span></span>

<span data-ttu-id="194d6-118">Altere seu domínio principal para um domínio que você verificou no Microsoft 365, por exemplo, contoso.com.</span><span class="sxs-lookup"><span data-stu-id="194d6-118">Change your primary domain to a domain you have verified in Microsoft 365, for example, contoso.com.</span></span> <span data-ttu-id="194d6-119">Todos os usuários que têm o domínio contoso.local são atualizados para contoso.com.</span><span class="sxs-lookup"><span data-stu-id="194d6-119">Every user that has the domain contoso.local is then updated to contoso.com.</span></span> <span data-ttu-id="194d6-120">No entanto, esse é um processo muito envolvido e uma solução mais fácil é descrita na seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="194d6-120">This is a very involved process, however, and an easier solution is described in the following section.</span></span>
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a><span data-ttu-id="194d6-121">Adicionar sufixos UPN e atualizar seus usuários para eles</span><span class="sxs-lookup"><span data-stu-id="194d6-121">Add UPN suffixes and update your users to them</span></span>

<span data-ttu-id="194d6-122">Você pode resolver o problema ".local" registrando o novo sufixo ou sufixo UPN no AD DS para corresponder ao domínio (ou domínios) verificado no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="194d6-122">You can solve the ".local" problem by registering new UPN suffix or suffixes in AD DS to match the domain (or domains) you verified in Microsoft 365.</span></span> <span data-ttu-id="194d6-123">Depois de registrar o novo sufixo, atualize os UPNs do usuário para substituir o ".local" pelo novo nome de domínio, por exemplo, para que uma conta de usuário se pareça com billa@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="194d6-123">After you register the new suffix, you update the user UPNs to replace the ".local" with the new domain name, for example, so that a user account looks like billa@contoso.com.</span></span>
  
<span data-ttu-id="194d6-124">Depois de atualizar os UPNs para usar o domínio verificado, você estará pronto para sincronizar o AD DS local com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="194d6-124">After you have updated the UPNs to use the verified domain, you are ready to synchronize your on-premises AD DS with Microsoft 365.</span></span>
  
#### <a name="step-1-add-the-new-upn-suffix"></a><span data-ttu-id="194d6-125">Etapa 1: Adicionar o novo sufixo UPN\*\*</span><span class="sxs-lookup"><span data-stu-id="194d6-125">Step 1: Add the new UPN suffix\*\*</span></span>
  
1. <span data-ttu-id="194d6-126">No controlador de domínio do AD DS, no Gerenciador de Servidores, escolha **Ferramentas** \> **Domínios e Confiações do Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="194d6-126">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Domains and Trusts**.</span></span>
    
    <span data-ttu-id="194d6-127">**Ou, se você não tiver o Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="194d6-127">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="194d6-128">Pressione **a tecla Windows + R** para abrir a caixa de diálogo **Executar** e digite Domain.msc e escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="194d6-128">Press **Windows key + R** to open the **Run** dialog, and then type in Domain.msc, and then choose **OK**.</span></span>
    
    ![Escolha Domínios e Confiações do Active Directory.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. <span data-ttu-id="194d6-130">Na janela **Domínios e Confiações** do Active Directory, clique com o botão direito do mouse em **Domínios** e Confiações do Active Directory e escolha **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="194d6-130">In the **Active Directory Domains and Trusts** window, right-click **Active Directory Domains and Trusts**, and then choose **Properties**.</span></span>
    
    ![Clique com o botão direito do mouse em Domínios e Confiações do Active Directory e escolha Propriedades](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. <span data-ttu-id="194d6-132">Na guia **Sufixos UPN,** na caixa **Sufixos UPN** alternativos, digite seu novo sufixo ou sufixo UPN e escolha **Adicionar** \> **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="194d6-132">On the **UPN Suffixes** tab, in the **Alternative UPN Suffixes** box, type your new UPN suffix or suffixes, and then choose **Add** \> **Apply**.</span></span>
    
    ![Adicionar um novo sufixo UPN](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    <span data-ttu-id="194d6-134">Escolha **OK** quando terminar de adicionar sufixos.</span><span class="sxs-lookup"><span data-stu-id="194d6-134">Choose **OK** when you're done adding suffixes.</span></span> 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a><span data-ttu-id="194d6-135">Etapa 2: Alterar o sufixo UPN para usuários existentes</span><span class="sxs-lookup"><span data-stu-id="194d6-135">Step 2: Change the UPN suffix for existing users</span></span>
  
1. <span data-ttu-id="194d6-136">No controlador de domínio do AD DS, no Gerenciador de Servidores, escolha **Ferramentas** \> **usuários e computadores do Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="194d6-136">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="194d6-137">**Ou, se você não tiver o Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="194d6-137">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="194d6-138">Pressione **a tecla windows + R** para abrir a caixa de diálogo **Executar** e digite Dsa.msc e clique em **OK**</span><span class="sxs-lookup"><span data-stu-id="194d6-138">Press **Windows key + R** to open the **Run** dialog, and then type in Dsa.msc, and then click **OK**</span></span>
    
2. <span data-ttu-id="194d6-139">Selecione um usuário, clique com o botão direito do mouse e escolha **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="194d6-139">Select a user, right-click, and then choose **Properties**.</span></span>
    
3. <span data-ttu-id="194d6-140">Na guia **Conta,** na lista de sufixos UPN, escolha o novo sufixo UPN e escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="194d6-140">On the **Account** tab, in the UPN suffix drop-down list, choose the new UPN suffix, and then choose **OK**.</span></span>
    
    ![Adicionar novo sufixo UPN para um usuário](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. <span data-ttu-id="194d6-142">Conclua estas etapas para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="194d6-142">Complete these steps for every user.</span></span>
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a><span data-ttu-id="194d6-143">Use o PowerShell para alterar o sufixo UPN para todos os seus usuários</span><span class="sxs-lookup"><span data-stu-id="194d6-143">Use PowerShell to change the UPN suffix for all of your users</span></span>

<span data-ttu-id="194d6-144">Se você tiver muitas contas de usuário para atualizar, é mais fácil usar o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="194d6-144">If you have a lot of user accounts to update, it's easier to use PowerShell.</span></span> <span data-ttu-id="194d6-145">O exemplo a seguir usa os cmdlets [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) e [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) para alterar todos os sufixos contoso.local para contoso.com no AD DS.</span><span class="sxs-lookup"><span data-stu-id="194d6-145">The following example uses the cmdlets [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) and [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) to change all contoso.local suffixes to contoso.com in AD DS.</span></span> 

<span data-ttu-id="194d6-146">Por exemplo, você pode executar os seguintes comandos do PowerShell para atualizar todos os sufixos contoso.local para contoso.com:</span><span class="sxs-lookup"><span data-stu-id="194d6-146">For example, you could run the following PowerShell commands to update all contoso.local suffixes to contoso.com:</span></span>
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

<span data-ttu-id="194d6-147">Consulte [o módulo Windows PowerShell active Directory](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10)) para saber mais sobre como usar Windows PowerShell no AD DS.</span><span class="sxs-lookup"><span data-stu-id="194d6-147">See [Active Directory Windows PowerShell module](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10)) to learn more about using Windows PowerShell in AD DS.</span></span>