---
title: Automatizar a associação de grupo e licenciamento para o seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Configure o licenciamento do grupo e a associação ao grupo dinâmico em seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 45a78af202f2d9ab029683aae4d95ed9a3370b08
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865067"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="ddcc1-103">Automatizar a associação de grupo e licenciamento para o seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ddcc1-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="ddcc1-p101">Licenciamento baseado no grupo automaticamente atribui ou remove licenças para uma conta de usuário com base na associação de grupo. A associação ao grupo dinâmico adiciona ou remove membros a um grupo com base em Propriedades de conta de usuário, como departamento ou país. Este artigo orienta uma demonstração de ambos no seu ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-p101">Group-based licensing automatically assigns or removes licenses for a user account based on group membership. Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country. This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="ddcc1-107">Há duas fases para configurar a participação no grupo de licenciamento automático e dinâmicas no seu ambiente de teste do Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="ddcc1-107">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="ddcc1-108">Crie o ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="ddcc1-109">Configurar e testar a associação ao grupo dinâmico e licenciamento automático.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-109">Configure and test dynamic group membership and automatic licensing.</span></span>

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="ddcc1-111">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="ddcc1-112">Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ddcc1-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="ddcc1-113">Se você quiser testar automatizada de licenciamento e participação no grupo em uma maneira leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="ddcc1-113">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ddcc1-114">Se você deseja testar automatizada de licenciamento e a participação no grupo em uma empresa simulada, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="ddcc1-114">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ddcc1-p102">Testando automatizada de licenciamento e a associação de grupo não requer o ambiente de teste de simulado empresarial, que inclui uma intranet simulada conectada à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar automatizada de licenciamento e a associação ao grupo e experimentar em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-p102">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="ddcc1-117">Fase 2: Configurar e testar a associação ao grupo dinâmico e licenciamento automático</span><span class="sxs-lookup"><span data-stu-id="ddcc1-117">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="ddcc1-118">Primeiro, você pode cria um novo grupo de vendas e adicionar uma regra de associação de grupo dinâmico de modo que as contas de usuário com o departamento definido como vendas são automaticamente adicionadas ao grupo de vendas.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-118">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="ddcc1-119">Usando uma instância particular do seu navegador da Internet, entrar no portal do Office em [https://office.com](https://office.com) com a conta de administrador global de sua assinatura de avaliação do Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-119">Using a private instance of your Internet browser, sign in to the Office portal at [https://office.com](https://office.com) with the global administrator account of your Office 365 E5 trial subscription.</span></span>
2. <span data-ttu-id="ddcc1-120">Em uma guia separada do navegador, vá para o portal do Windows Azure em [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="ddcc1-120">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="ddcc1-121">No Portal do Azure, clique em **Azure Active Directory > Usuários e grupos > Todos os grupos**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-121">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
4. <span data-ttu-id="ddcc1-122">No blade **todos os grupos** , clique em **novo grupo**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-122">On the **All groups** blade, click **New group**.</span></span>
5. <span data-ttu-id="ddcc1-123">Em **tipo de grupo**, selecione **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-123">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="ddcc1-124">Em **nome do grupo**, digite **vendas**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-124">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="ddcc1-125">Em **tipo de associação**, selecione **usuário dinâmico** .</span><span class="sxs-lookup"><span data-stu-id="ddcc1-125">In **Membership type**, select **Dynamic user** .</span></span>
8. <span data-ttu-id="ddcc1-126">Clique em **Adicionar consulta dinâmica**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-126">Click **Add dynamic query**.</span></span>
9. <span data-ttu-id="ddcc1-127">Em **Adicionar usuários onde**, selecione **departamento**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-127">In **Add users where**, select **department**.</span></span>
10. <span data-ttu-id="ddcc1-128">No campo seguinte, selecione **Igual a**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-128">In the next field, select **Equals**.</span></span>
11. <span data-ttu-id="ddcc1-129">No campo próximo, digite **vendas**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-129">In the next field, type **Sales**.</span></span>
12. <span data-ttu-id="ddcc1-130">Clique em **Adicionar consulta** e, em seguida, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-130">Click **Add query**, and then click **Create**.</span></span>
13. <span data-ttu-id="ddcc1-131">Feche as lâminas de **grupo** e **os grupos de grupos a todos** .</span><span class="sxs-lookup"><span data-stu-id="ddcc1-131">Close the **Group** and **Groups-All groups** blades.</span></span>

<span data-ttu-id="ddcc1-132">Em seguida, você configurar o grupo de vendas para que os membros são automaticamente atribuídos E5 do Office 365 e mobilidade corporativos + segurança E5 licenças.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-132">Next, you configure the Sales group so that members are automatically assigned Office 365 E5 and Enterprise Mobility + Security E5 licenses.</span></span>

1. <span data-ttu-id="ddcc1-133">No blade **Visão geral** do Azure Active Directory, clique em **licenças > todos os produtos**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-133">On the **Overview** blade for Azure Active Directory, click **Licenses > All products**.</span></span>
2. <span data-ttu-id="ddcc1-134">Na lista, escolha **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5** e clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-134">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
3. <span data-ttu-id="ddcc1-135">No blade **atribuir licença** , clique em **usuários e grupos**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-135">On the **Assign license** blade, click **Users and groups**.</span></span>
4. <span data-ttu-id="ddcc1-136">Na lista de grupos, selecione o grupo de **vendas** .</span><span class="sxs-lookup"><span data-stu-id="ddcc1-136">In the list of groups, select the **Sales** group.</span></span>
5. <span data-ttu-id="ddcc1-137">Clique em **Selecionar** e clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-137">Click **Select**, and then click **Assign**.</span></span>
6. <span data-ttu-id="ddcc1-138">Feche a guia do Portal do Azure no navegador.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-138">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="ddcc1-139">Em seguida, você teste a associação ao grupo dinâmico e licenciamento automático na conta do usuário 4.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-139">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="ddcc1-140">Na guia **Página inicial do Microsoft Office** no seu navegador, clique em **Admin**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-140">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="ddcc1-141">A partir da guia do **Centro de administração do Office** , clique em **usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-141">From the **Office Admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="ddcc1-142">Na página **usuários ativos** , clique na conta de **usuário 4** .</span><span class="sxs-lookup"><span data-stu-id="ddcc1-142">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="ddcc1-143">No painel de **4 de usuário** , clique em **Editar** para **licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-143">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="ddcc1-144">No painel de **licenças do produto** , ative a **mobilidade corporativos + segurança E5** e licenças do **Office 365 Enterprise E5** desativada e clique em **Salvar > fechar**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-144">On the **Product licenses** pane, turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses off, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="ddcc1-145">Nas propriedades da conta de usuário 4, verifique não se tiverem sido atribuída a nenhuma licença do produto e não há nenhuma associações de grupo.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-145">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="ddcc1-146">Para **obter informações de contato**, clique em **Editar** .</span><span class="sxs-lookup"><span data-stu-id="ddcc1-146">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="ddcc1-147">No painel de **informações de contato de editar** , clique em **informações de contato**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-147">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="ddcc1-148">No campo **departamento** , digite **vendas**e clique em **Salvar > fechar**.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-148">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="ddcc1-149">Aguarde alguns minutos e clique no ícone Atualizar no canto superior direito do painel de conta de usuário 4 periodicamente.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-149">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="ddcc1-150">No momento, você deverá ver a:</span><span class="sxs-lookup"><span data-stu-id="ddcc1-150">In time you should see the:</span></span>

- <span data-ttu-id="ddcc1-151">Propriedade de **associações de grupo** atualizada com o grupo de **vendas** .</span><span class="sxs-lookup"><span data-stu-id="ddcc1-151">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="ddcc1-152">Propriedade de **licenças de produto** atualizada com as licenças de **mobilidade corporativos + E5 de segurança** e o **Office 365 Enterprise E5** .</span><span class="sxs-lookup"><span data-stu-id="ddcc1-152">**Product licenses** property updated with the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses.</span></span>

<span data-ttu-id="ddcc1-153">Consulte estas etapas na fase de identidade para obter informações e links para implantar a associação ao grupo dinâmico e licenciamento automático na produção:</span><span class="sxs-lookup"><span data-stu-id="ddcc1-153">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="ddcc1-154">Configurar licenciamentos automáticos</span><span class="sxs-lookup"><span data-stu-id="ddcc1-154">Set up automatic licensing</span></span>](identity-group-based-licensing.md)
- [<span data-ttu-id="ddcc1-155">Configurar associações de grupo dinâmico</span><span class="sxs-lookup"><span data-stu-id="ddcc1-155">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md)

## <a name="next-step"></a><span data-ttu-id="ddcc1-156">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="ddcc1-156">Next step</span></span>

<span data-ttu-id="ddcc1-157">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="ddcc1-157">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ddcc1-158">Confira também</span><span class="sxs-lookup"><span data-stu-id="ddcc1-158">See also</span></span>

[<span data-ttu-id="ddcc1-159">Fase 2: Identidade</span><span class="sxs-lookup"><span data-stu-id="ddcc1-159">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="ddcc1-160">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ddcc1-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ddcc1-161">Implantação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ddcc1-161">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="ddcc1-162">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ddcc1-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
