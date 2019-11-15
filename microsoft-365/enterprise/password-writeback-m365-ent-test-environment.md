---
title: Write-back de senha do ambiente de teste do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumo: configure o write-back de senha do ambiente de teste do Microsoft 365.'
ms.openlocfilehash: d946aefa38884923d70d2c530d61f84861cc914e
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639751"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="7dcb9-103">Write-back de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7dcb9-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="7dcb9-p101">O write-back de senha permite aos usuários atualizar suas senhas pelo Azure Active Directory (Azure AD), o que é então replicado para o Active Directory Domain Services local (AD DS). Com o write-back de senha, os usuários não precisam atualizar suas senhas pelo AD DS local, onde as contas de usuários originais são armazenadas. Isso ajuda os usuários móveis ou remotos que não têm uma conexão de acesso remoto à rede local.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-p101">Password writeback allows users to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS). With password writeback, users don’t need to update their passwords through the on-premises AD DS where their original user accounts are stored. This helps roaming or remote users who do not have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="7dcb9-107">Este artigo descreve como você pode configurar seu ambiente de teste do Microsoft 365 para o write-back de senha.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-107">This article describes how you can configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="7dcb9-108">Há duas etapas para fazer a configuração:</span><span class="sxs-lookup"><span data-stu-id="7dcb9-108">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="7dcb9-109">Criar o ambiente de teste de empresa simulada do Microsoft 365 com sincronização de hash de senha.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="7dcb9-110">Habilitar o write-back de senha para o domínio TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-110">Enable password writeback for the TESTLAB AD DS domain.</span></span>
    
![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="7dcb9-112">Clique [aqui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-112">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="7dcb9-113">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7dcb9-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="7dcb9-p102">Primeiro, siga as instruções em [sincronização de hash de senha](password-hash-sync-m365-ent-test-environment.md). Aqui está sua configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-p102">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="7dcb9-117">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="7dcb9-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="7dcb9-118">Assinaturas pagas ou de avaliação do Office 365 E5 e EMS E5.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-118">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="7dcb9-119">Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="7dcb9-120">Azure AD Connect é executado no APP1 para sincronizar o domínio TESTLAB AD DS ao locatário do Azure AD de suas assinaturas do Office 365 e EMS E5.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="7dcb9-121">Fase 2: Habilitar o write-back de senha para o domínio TESTLAB AD DS</span><span class="sxs-lookup"><span data-stu-id="7dcb9-121">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="7dcb9-122">Primeiro, configure a conta de Usuário 1 com a função de administrador global.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-122">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="7dcb9-123">No [centro de administração do Microsoft 365](https://portal.microsoft.com), entre com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-123">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="7dcb9-124">Clique em **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-124">Click **Active users**.</span></span>
 
3. <span data-ttu-id="7dcb9-125">Na página **Usuários ativos**, clique na conta **usuário1**,</span><span class="sxs-lookup"><span data-stu-id="7dcb9-125">On the **Active users** page, click the **user1** account,</span></span>

4. <span data-ttu-id="7dcb9-126">No painel **usuário1**, clique em **Editar** ao lado de **Funções**.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-126">On the **user1** pane, click **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="7dcb9-p103">No painel **Editar funções de usuário** de usuário1, clique em **Administrador global**. Clique em **Salvar** e depois em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-p103">On the **Edit user roles** pane for user1, click **Global administrator**. Click **Save**, and then click **Close**.</span></span>

<span data-ttu-id="7dcb9-129">Em seguida, configure a conta de Usuário 1 com as configurações de segurança que permitem a alteração de senhas em nome do domínio de outros usuários do TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-129">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="7dcb9-130">No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se ao APP1 com a conta TESTLAB\Usuário1.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-130">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="7dcb9-131">Na área de trabalho do APP1, clique em **Iniciar**, digite **ativo** e clique em **Usuários e Computadores do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-131">From the desktop of APP1, click **Start**, type **active**, and then click **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="7dcb9-p104">Clique em **Modo de exibição** na barra de menus. Se **Recursos avançados** não estiver habilitado, clique nele para habilitá-lo.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-p104">Click **View** in the menu bar. If **Advanced features** is not enabled, click it to enable it.</span></span>

4. <span data-ttu-id="7dcb9-134">No painel de árvore, clique com botão direito no seu domínio, clique em **Propriedades** e depois na guia **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-134">In the tree pane, right-click your domain, click **Properties**, and then click the **Security** tab.</span></span>

5. <span data-ttu-id="7dcb9-135">Clique em **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-135">Click **Advanced**.</span></span>

6. <span data-ttu-id="7dcb9-136">Na guia **Permissões**, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-136">On the **Permissions** tab, click **Add**.</span></span>

7. <span data-ttu-id="7dcb9-137">Clique em **Selecionar uma entidade de segurança**, digite **Usuário1** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-137">Click **Select a principal**, type **User1**, and then click **OK**.</span></span>

8. <span data-ttu-id="7dcb9-138">Em **Aplica-se a**, selecione **Objetos de usuário descendente**.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-138">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="7dcb9-139">Em **Permissões**, selecione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7dcb9-139">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="7dcb9-140">Alterar senha</span><span class="sxs-lookup"><span data-stu-id="7dcb9-140">Change password</span></span>
    - <span data-ttu-id="7dcb9-141">Redefinir senha</span><span class="sxs-lookup"><span data-stu-id="7dcb9-141">Reset password</span></span>

10. <span data-ttu-id="7dcb9-142">Em **Propriedades**, selecione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="7dcb9-142">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="7dcb9-143">Gravar lockoutTime</span><span class="sxs-lookup"><span data-stu-id="7dcb9-143">Write lockoutTime</span></span>
    - <span data-ttu-id="7dcb9-144">Gravar pwdLastSet</span><span class="sxs-lookup"><span data-stu-id="7dcb9-144">Write pwdLastSet</span></span>

11. <span data-ttu-id="7dcb9-145">Clique em **OK** três vezes para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-145">Click **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="7dcb9-146">Feche **Usuários e Computadores do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-146">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="7dcb9-147">Configure o Azure AD Connect em APP1 para write-back de senha.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-147">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="7dcb9-148">Se necessário, conecte ao APP1 com a conta TESTLAB\Usuário1.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-148">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="7dcb9-149">Na área de trabalho de APP1, clique duas vezes em **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-149">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="7dcb9-150">Na **Página inicial**, clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-150">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="7dcb9-151">Na página **Tarefas adicionais**, clique em **Personalizar as opções de sincronização** e depois em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-151">On the **Additional tasks** page, click **Customize synchronization options**, and then click **Next**.</span></span>

5. <span data-ttu-id="7dcb9-152">Na página **Conectar ao Azure AD**, digite suas credenciais de conta de administrador global e clique em **Próxima**.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-152">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="7dcb9-153">Nas páginas **Conectar os diretórios** e **Filtrar domínio/UO**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-153">On the **Connect directories** and **Domain/OU filtering** pages, click **Next**.</span></span>

7. <span data-ttu-id="7dcb9-154">Na página **Recursos opcionais**, selecione **Write-back de senha** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-154">On the **Optional features** page, select **Password writeback** and click **Next**.</span></span> 

8. <span data-ttu-id="7dcb9-155">Na página **Pronto para configurar**, clique em **Configurar** e aguarde que o processo seja concluído.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-155">On the **Ready to configure** page, click **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="7dcb9-156">Ao concluir a configuração, clique em **Sair**.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-156">When you see the configuration finish, click **Exit**.</span></span>

<span data-ttu-id="7dcb9-157">Agora você está pronto para testar o write-back de senha para os usuários em computadores que não estão conectados à rede virtual da sua intranet simulada.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-157">You are now ready to test password writeback for users on computers that are not connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="7dcb9-158">Esta é a configuração resultante:</span><span class="sxs-lookup"><span data-stu-id="7dcb9-158">Here is your resulting configuration:</span></span>

![A empresa simulada com ambiente de teste de autenticação de passagem](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="7dcb9-160">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="7dcb9-160">This configuration consists of:</span></span>

- <span data-ttu-id="7dcb9-161">Assinaturas pagas ou de avaliação do Office 365 E5 e EMS E5 com o domínio DNS TESTLAB.\<seu nome de domínio> registrado.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-161">Office 365 E5 and EMS E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="7dcb9-162">Uma intranet de organização simplificada conectado à Internet, que consiste em máquinas virtuais do DC1 APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-162">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="7dcb9-163">O Azure AD Connect é executado no APP1 para sincronizar a lista de contas e grupos de locatário do Azure AD de suas assinaturas do Office 365 e EMS E5 para o domínio TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-163">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Office 365 and EMS E5 subscriptions to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="7dcb9-164">O write-back de senha está habilitado para que os usuários possam alterar as próprias senhas pelo Azure AD sem precisar se conectar à intranet simplificada.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-164">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

<span data-ttu-id="7dcb9-165">Confira informações e links para configurar o write-back de senhas em produção na etapa [Simplificar a atualização de senhas](identity-add-user-accounts.md#identity-pw-writeback), na fase Identidade.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-165">See the [Simplify password updates](identity-add-user-accounts.md#identity-pw-writeback) step in the Identity phase for information and links to configure password writeback in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="7dcb9-166">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="7dcb9-166">Next step</span></span>

<span data-ttu-id="7dcb9-167">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="7dcb9-167">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7dcb9-168">Confira também</span><span class="sxs-lookup"><span data-stu-id="7dcb9-168">See also</span></span>

[<span data-ttu-id="7dcb9-169">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7dcb9-169">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7dcb9-170">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7dcb9-170">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="7dcb9-171">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7dcb9-171">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


