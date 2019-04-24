---
title: Automatizar o licenciamento e a associação de grupo para seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure o licenciamento baseado em grupo e a associação de grupos dinâmicos em seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 8ced249ee56e15c057001af60d790a8a4315dd17
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277233"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="7c3fb-103">Automatizar o licenciamento e a associação de grupo para seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7c3fb-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="7c3fb-104">O licenciamento baseado em grupo atribui ou remove automaticamente licenças de uma conta de usuário com base na associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-104">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="7c3fb-105">A associação de grupo dinâmico adiciona ou remove membros de um grupo com base nas propriedades da conta de usuário, como departamento ou país.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-105">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="7c3fb-106">Este artigo orienta você através de uma demonstração do ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-106">This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="7c3fb-107">Há duas fases para configurar o licenciamento automático e a associação de grupo dinâmico no ambiente de teste do Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="7c3fb-107">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="7c3fb-108">Crie o ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="7c3fb-109">Configurar e testar a associação de grupo dinâmico e o licenciamento automático.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-109">Configure and test dynamic group membership and automatic licensing.</span></span>

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="7c3fb-111">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="7c3fb-112">Fase 1: criar seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7c3fb-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="7c3fb-113">Se você só quiser testar o licenciamento automatizado e a associação de grupo de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="7c3fb-113">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="7c3fb-114">Se você quiser testar o licenciamento automatizado e a associação de grupo em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7c3fb-114">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7c3fb-115">Testar o licenciamento automatizado e a associação de grupo não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="7c3fb-115">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="7c3fb-116">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-116">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="7c3fb-117">Fase 2: configurar e testar a associação de grupo dinâmico e o licenciamento automático</span><span class="sxs-lookup"><span data-stu-id="7c3fb-117">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="7c3fb-118">Primeiro, você cria um novo grupo de vendas e adiciona uma regra de associação de grupo dinâmico para que as contas de usuário com o departamento definida como vendas sejam automaticamente adicionadas ao grupo vendas.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-118">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="7c3fb-119">Usando uma instância privada do navegador da Internet, entre no portal do Office em [https://office.com](https://office.com) com a conta de administrador global da sua assinatura de avaliação do Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-119">Using a private instance of your Internet browser, sign in to the Office portal at [https://office.com](https://office.com) with the global administrator account of your Office 365 E5 trial subscription.</span></span>
2. <span data-ttu-id="7c3fb-120">Em uma guia separada do navegador, vá para o portal do Azure em [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="7c3fb-120">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="7c3fb-121">No Portal do Azure, clique em **Azure Active Directory > Usuários e grupos > Todos os grupos**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-121">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
4. <span data-ttu-id="7c3fb-122">Na folha **todos os grupos** , clique em **novo grupo**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-122">On the **All groups** blade, click **New group**.</span></span>
5. <span data-ttu-id="7c3fb-123">Em **tipo de grupo**, selecione **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-123">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="7c3fb-124">Em **nome do grupo**, digite **vendas**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-124">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="7c3fb-125">Em **tipo de associação**, selecione **usuário dinâmico** .</span><span class="sxs-lookup"><span data-stu-id="7c3fb-125">In **Membership type**, select **Dynamic user** .</span></span>
8. <span data-ttu-id="7c3fb-126">Clique em **Adicionar consulta dinâmica**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-126">Click **Add dynamic query**.</span></span>
9. <span data-ttu-id="7c3fb-127">Em **Adicionar usuários onde**, selecione **departamento**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-127">In **Add users where**, select **department**.</span></span>
10. <span data-ttu-id="7c3fb-128">No campo seguinte, selecione **Igual a**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-128">In the next field, select **Equals**.</span></span>
11. <span data-ttu-id="7c3fb-129">No campo seguinte, digite **Sales**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-129">In the next field, type **Sales**.</span></span>
12. <span data-ttu-id="7c3fb-130">Clique em **Adicionar consulta** e, em seguida, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-130">Click **Add query**, and then click **Create**.</span></span>
13. <span data-ttu-id="7c3fb-131">Feche as lâminas **Group** e **groups-All Groups** .</span><span class="sxs-lookup"><span data-stu-id="7c3fb-131">Close the **Group** and **Groups-All groups** blades.</span></span>

<span data-ttu-id="7c3fb-132">Em seguida, configure o grupo de vendas para que os Membros recebam automaticamente licenças do Office 365 E5 e Enterprise Mobility + Security e5.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-132">Next, you configure the Sales group so that members are automatically assigned Office 365 E5 and Enterprise Mobility + Security E5 licenses.</span></span>

1. <span data-ttu-id="7c3fb-133">Na folha **visão geral** do Azure Active Directory, clique em **licenças > todos os produtos**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-133">On the **Overview** blade for Azure Active Directory, click **Licenses > All products**.</span></span>
2. <span data-ttu-id="7c3fb-134">Na lista, escolha **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5** e clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-134">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
3. <span data-ttu-id="7c3fb-135">Na folha **atribuir licença** , clique em **usuários e grupos**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-135">On the **Assign license** blade, click **Users and groups**.</span></span>
4. <span data-ttu-id="7c3fb-136">Na lista de grupos, selecione o grupo **vendas** .</span><span class="sxs-lookup"><span data-stu-id="7c3fb-136">In the list of groups, select the **Sales** group.</span></span>
5. <span data-ttu-id="7c3fb-137">Clique em **Selecionar** e clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-137">Click **Select**, and then click **Assign**.</span></span>
6. <span data-ttu-id="7c3fb-138">Feche a guia do Portal do Azure no navegador.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-138">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="7c3fb-139">Em seguida, teste a associação de grupo dinâmico e o licenciamento automático na conta do usuário 4.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-139">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="7c3fb-140">Na guia **Microsoft Office Home** no navegador, clique em **administrador**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-140">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="7c3fb-141">Na guia **centro de administração do Microsoft 365** , clique em **usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-141">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="7c3fb-142">Na página **usuários ativos** , clique na conta do **usuário 4** .</span><span class="sxs-lookup"><span data-stu-id="7c3fb-142">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="7c3fb-143">No painel **usuário 4** , clique em **Editar** para **licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-143">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="7c3fb-144">No painel **de licenças de produto** , desative as licenças do **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5** e clique em **salvar > fechar**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-144">On the **Product licenses** pane, turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses off, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="7c3fb-145">Nas propriedades da conta do usuário 4, verifique se nenhuma licença de produto foi atribuída e se não há associações de grupo.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-145">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="7c3fb-146">Clique em **Editar** para obter **informações de contato**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-146">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="7c3fb-147">No painel **Editar informações de contato** , clique em **informações de contato**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-147">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="7c3fb-148">No campo **Departamento** , digite **vendas**e clique em **salvar > fechar**.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-148">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="7c3fb-149">Aguarde alguns minutos e clique periodicamente no ícone atualizar no canto superior direito do painel usuário 4 da conta.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-149">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="7c3fb-150">No momento, você verá:</span><span class="sxs-lookup"><span data-stu-id="7c3fb-150">In time you should see the:</span></span>

- <span data-ttu-id="7c3fb-151">Propriedade de **associações de grupo** atualizada com o grupo **Sales** .</span><span class="sxs-lookup"><span data-stu-id="7c3fb-151">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="7c3fb-152">Propriedade **Product licenses** atualizadas com as licenças do **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5** .</span><span class="sxs-lookup"><span data-stu-id="7c3fb-152">**Product licenses** property updated with the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses.</span></span>

<span data-ttu-id="7c3fb-153">Consulte estas etapas na fase de identidade para obter informações e links para implantar a associação de grupo dinâmico e o licenciamento automático em produção:</span><span class="sxs-lookup"><span data-stu-id="7c3fb-153">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="7c3fb-154">Configurar licenciamentos automáticos</span><span class="sxs-lookup"><span data-stu-id="7c3fb-154">Set up automatic licensing</span></span>](identity-self-service-group-management.md#identity-group-license)
- [<span data-ttu-id="7c3fb-155">Configurar a associação de grupo dinâmica</span><span class="sxs-lookup"><span data-stu-id="7c3fb-155">Set up dynamic group membership</span></span>](identity-self-service-group-management.md#identity-dyn-groups)

## <a name="next-step"></a><span data-ttu-id="7c3fb-156">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="7c3fb-156">Next step</span></span>

<span data-ttu-id="7c3fb-157">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="7c3fb-157">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c3fb-158">Confira também</span><span class="sxs-lookup"><span data-stu-id="7c3fb-158">See also</span></span>

[<span data-ttu-id="7c3fb-159">Fase 2: Identidade</span><span class="sxs-lookup"><span data-stu-id="7c3fb-159">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="7c3fb-160">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7c3fb-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7c3fb-161">Implantação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7c3fb-161">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="7c3fb-162">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="7c3fb-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
