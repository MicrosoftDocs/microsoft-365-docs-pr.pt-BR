---
title: Write-back de senha do ambiente de teste do Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumo: configure o write-back de senha do ambiente de teste do Microsoft 365.'
ms.openlocfilehash: f1118c22ad1f65ea29bb14afacb7506a60d1fe1a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921475"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="b7700-103">Write-back de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b7700-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="b7700-104">*Este Guia de Laboratório de Teste só pode ser usado para Microsoft 365 ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="b7700-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="b7700-105">Os usuários podem usar o writeback de senha para atualizar suas senhas por meio do Azure Active Directory (Azure AD), que é replicado para os Serviços de Domínio local do Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="b7700-105">Users can use password writeback to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="b7700-106">Com o writeback de senha, os usuários não têm que atualizar suas senhas por meio do AD DS local onde suas contas de usuário originais são armazenadas.</span><span class="sxs-lookup"><span data-stu-id="b7700-106">With password writeback, users don't have to update their passwords through the on-premises AD DS where their original user accounts are stored.</span></span> <span data-ttu-id="b7700-107">Isso ajuda usuários de roaming ou remotos que não têm uma conexão de acesso remoto à rede local.</span><span class="sxs-lookup"><span data-stu-id="b7700-107">This helps roaming or remote users who don't have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="b7700-108">Este artigo descreve como configurar seu ambiente de teste Microsoft 365 para writeback de senha.</span><span class="sxs-lookup"><span data-stu-id="b7700-108">This article describes how to configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="b7700-109">Configurar seu ambiente de teste para writeback de senha envolve duas fases:</span><span class="sxs-lookup"><span data-stu-id="b7700-109">Configuring your test environment for password writeback involves two phases:</span></span>
- [<span data-ttu-id="b7700-110">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b7700-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="b7700-111">Fase 2: Habilitar o write-back de senha para o domínio TESTLAB AD DS</span><span class="sxs-lookup"><span data-stu-id="b7700-111">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="b7700-113">Para um mapa visual de todos os artigos na pilha Microsoft 365 guia do laboratório de teste empresarial, vá para o Microsoft 365 para a pilha de guias de laboratório [de teste corporativos.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="b7700-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="b7700-114">Fase 1: configurar a sincronização de hash de senha do ambiente de teste do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b7700-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="b7700-115">Primeiro, siga as instruções na [sincronização de hash de senha](password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b7700-115">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md).</span></span> <span data-ttu-id="b7700-116">Sua configuração resultante tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="b7700-116">Your resulting configuration looks like this:</span></span>
  
![Empresa simulada com ambiente de teste de sincronização de hash de senha](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="b7700-118">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="b7700-118">This configuration consists of:</span></span>
  
- <span data-ttu-id="b7700-119">Uma assinatura de avaliação ou assinatura paga do Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="b7700-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="b7700-120">Uma intranet de organização simplificada conectada à Internet, que consiste nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="b7700-120">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="b7700-121">O Azure AD Connect é executado no APP1 para sincronizar o domínio TESTLAB AD DS com o locatário do Azure AD da sua assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b7700-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="b7700-122">Fase 2: Habilitar o write-back de senha para o domínio TESTLAB AD DS</span><span class="sxs-lookup"><span data-stu-id="b7700-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="b7700-123">Primeiro, configure a conta de Usuário 1 com a função de administrador global.</span><span class="sxs-lookup"><span data-stu-id="b7700-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="b7700-124">No [centro de administração do Microsoft 365](https://portal.microsoft.com), entre com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="b7700-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="b7700-125">Selecione **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="b7700-125">Select **Active users**.</span></span>
 
3. <span data-ttu-id="b7700-126">Na página **Usuários ativos,** selecione a **conta user1,**</span><span class="sxs-lookup"><span data-stu-id="b7700-126">On the **Active users** page, select the **user1** account,</span></span>

4. <span data-ttu-id="b7700-127">No painel **user1,** selecione **Editar** ao lado de **Funções**.</span><span class="sxs-lookup"><span data-stu-id="b7700-127">On the **user1** pane, select **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="b7700-128">No painel **Editar funções de usuário** para usuário1, selecione Administrador **global**, selecione **Salvar** e, em seguida, selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b7700-128">On the **Edit user roles** pane for user1, select **Global administrator**, select **Save**, and then select **Close**.</span></span>

<span data-ttu-id="b7700-129">Em seguida, configure a conta de Usuário 1 com as configurações de segurança que permitem a alteração de senhas em nome do domínio de outros usuários do TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="b7700-129">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="b7700-130">No [Portal do Azure](https://portal.azure.com), entre com a conta de administrador global e conecte-se ao APP1 com a conta TESTLAB\Usuário1.</span><span class="sxs-lookup"><span data-stu-id="b7700-130">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="b7700-131">Na área de trabalho do APP1, selecione **Iniciar**, insira **ativo** e selecione **Usuários e Computadores do Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="b7700-131">From the desktop of APP1, select **Start**, enter **active**, and then select **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="b7700-132">Na barra de menus, selecione **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="b7700-132">On the menu bar, select **View**.</span></span> <span data-ttu-id="b7700-133">Se **os recursos avançados** não estão habilitados, selecione-o para habilita-lo.</span><span class="sxs-lookup"><span data-stu-id="b7700-133">If **Advanced features** is not enabled, select it to enable it.</span></span>

4. <span data-ttu-id="b7700-134">No painel de árvore, selecione e segure (ou clique com o botão direito do mouse) no domínio, selecione **Propriedades** e selecione a **guia** Segurança.</span><span class="sxs-lookup"><span data-stu-id="b7700-134">In the tree pane, select and hold (or right-click) your domain, select **Properties**, and then select the **Security** tab.</span></span>

5. <span data-ttu-id="b7700-135">Selecione **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="b7700-135">Select **Advanced**.</span></span>

6. <span data-ttu-id="b7700-136">Na guia **Permissões,** selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b7700-136">On the **Permissions** tab, select **Add**.</span></span>

7. <span data-ttu-id="b7700-137">Selecione **Selecionar uma entidade principal,** insira **User1** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7700-137">Select **Select a principal**, enter **User1**, and then select **OK**.</span></span>

8. <span data-ttu-id="b7700-138">Em **Aplica-se a**, selecione **Objetos de usuário descendente**.</span><span class="sxs-lookup"><span data-stu-id="b7700-138">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="b7700-139">Em **Permissões**, selecione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b7700-139">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="b7700-140">**Alterar senha**</span><span class="sxs-lookup"><span data-stu-id="b7700-140">**Change password**</span></span>
    - <span data-ttu-id="b7700-141">**Redefinir senha**</span><span class="sxs-lookup"><span data-stu-id="b7700-141">**Reset password**</span></span>

10. <span data-ttu-id="b7700-142">Em **Propriedades**, selecione o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b7700-142">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="b7700-143">**Gravar lockoutTime**</span><span class="sxs-lookup"><span data-stu-id="b7700-143">**Write lockoutTime**</span></span>
    - <span data-ttu-id="b7700-144">**Gravar pwdLastSet**</span><span class="sxs-lookup"><span data-stu-id="b7700-144">**Write pwdLastSet**</span></span>

11. <span data-ttu-id="b7700-145">Selecione **OK** três vezes para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="b7700-145">Select **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="b7700-146">Feche **Usuários e Computadores do Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b7700-146">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="b7700-147">Configure o Azure AD Connect em APP1 para write-back de senha.</span><span class="sxs-lookup"><span data-stu-id="b7700-147">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="b7700-148">Se necessário, conecte ao APP1 com a conta TESTLAB\Usuário1.</span><span class="sxs-lookup"><span data-stu-id="b7700-148">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="b7700-149">Na área de trabalho de APP1, clique duas vezes em **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="b7700-149">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="b7700-150">Na página **Bem-vindo,** selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="b7700-150">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="b7700-151">Na página **Tarefas adicionais,** selecione **Personalizar opções de** sincronização e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="b7700-151">On the **Additional tasks** page, select **Customize synchronization options**, and then select **Next**.</span></span>

5. <span data-ttu-id="b7700-152">Na página **Conexão para o Azure AD,** insira suas credenciais de conta de administrador global e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="b7700-152">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="b7700-153">Nos **diretórios Conexão e** páginas de filtragem **domínio/UO,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="b7700-153">On the **Connect directories** and **Domain/OU filtering** pages, select **Next**.</span></span>

7. <span data-ttu-id="b7700-154">Na página **Recursos opcionais,** selecione **Writeback de senha** e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="b7700-154">On the **Optional features** page, select **Password writeback**, and then select **Next**.</span></span>

8. <span data-ttu-id="b7700-155">Na página **Pronto para configurar,** selecione **Configurar** e aguarde o final do processo.</span><span class="sxs-lookup"><span data-stu-id="b7700-155">On the **Ready to configure** page, select **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="b7700-156">Quando você vir a configuração terminar, selecione **Sair**.</span><span class="sxs-lookup"><span data-stu-id="b7700-156">When you see the configuration finish, select **Exit**.</span></span>

<span data-ttu-id="b7700-157">Agora você está pronto para testar o writeback de senha para usuários em computadores que não estão conectados à rede virtual da intranet simulada.</span><span class="sxs-lookup"><span data-stu-id="b7700-157">You are now ready to test password writeback for users on computers that aren't connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="b7700-158">Sua configuração resultante tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="b7700-158">Your resulting configuration looks like this:</span></span>

![A empresa simulada com ambiente de teste de autenticação de passagem](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="b7700-160">Esta configuração consiste em:</span><span class="sxs-lookup"><span data-stu-id="b7700-160">This configuration consists of:</span></span>

- <span data-ttu-id="b7700-161">Uma Microsoft 365 E5 de avaliação ou assinaturas pagas com o domínio DNS TESTLAB.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="b7700-161">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<*your domain name*></span></span> <span data-ttu-id="b7700-162">registrado.</span><span class="sxs-lookup"><span data-stu-id="b7700-162">registered.</span></span>
- <span data-ttu-id="b7700-163">Uma intranet de organização simplificada conectada à Internet, que consiste nas máquinas virtuais DC1, APP1 e CLIENT1 em uma sub-rede de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="b7700-163">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="b7700-164">O Azure AD Connect é executado no APP1 para sincronizar a lista de contas e grupos do locatário do Azure AD da sua assinatura do Microsoft 365 no domínio TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="b7700-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="b7700-165">O write-back de senha está habilitado para que os usuários possam alterar as próprias senhas pelo Azure AD sem precisar se conectar à intranet simplificada.</span><span class="sxs-lookup"><span data-stu-id="b7700-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="b7700-166">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="b7700-166">Next step</span></span>

<span data-ttu-id="b7700-167">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="b7700-167">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7700-168">Confira também</span><span class="sxs-lookup"><span data-stu-id="b7700-168">See also</span></span>

[<span data-ttu-id="b7700-169">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="b7700-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b7700-170">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="b7700-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b7700-171">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="b7700-171">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)