---
title: Automatizar o licenciamento e a associação de grupo para seu ambiente de teste do Microsoft 365 for Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure o licenciamento baseado em grupo e a associação de grupos dinâmicos em seu ambiente de teste do Microsoft 365 for Enterprise.
ms.openlocfilehash: a25a47b81ce8c119e7aeb44660af32bb9cafb08a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685553"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7c665-103">Automatizar o licenciamento e a associação de grupo para seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="7c665-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7c665-104">*Este guia de laboratório de teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="7c665-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="7c665-105">O licenciamento baseado em grupo atribui ou remove automaticamente licenças de uma conta de usuário com base na associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="7c665-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="7c665-106">A associação de grupo dinâmico adiciona ou remove membros de um grupo com base nas propriedades da conta de usuário, como departamento ou país.</span><span class="sxs-lookup"><span data-stu-id="7c665-106">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="7c665-107">Este artigo orienta você através de uma demonstração do ambiente de teste do Microsoft 365 for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7c665-107">This article steps you through a demonstration of both in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="7c665-108">Há duas fases para configurar o licenciamento automático e a associação de grupo dinâmico no ambiente de teste do Microsoft 365 for Enterprise:</span><span class="sxs-lookup"><span data-stu-id="7c665-108">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment:</span></span>

1. <span data-ttu-id="7c665-109">Crie o ambiente de teste do Microsoft 365 for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="7c665-109">Create the Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="7c665-110">Configurar e testar a associação de grupo dinâmico e o licenciamento automático.</span><span class="sxs-lookup"><span data-stu-id="7c665-110">Configure and test dynamic group membership and automatic licensing.</span></span>

![Guias do Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="7c665-112">Clique [aqui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos na pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="7c665-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="7c665-113">Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="7c665-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="7c665-114">Se você só quiser testar o licenciamento automatizado e a associação de grupo de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="7c665-114">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="7c665-115">Se você quiser testar o licenciamento automatizado e a associação de grupo em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="7c665-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="7c665-116">Testar o licenciamento automatizado e a associação de grupo não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="7c665-116">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="7c665-117">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="7c665-117">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="7c665-118">Fase 2: configurar e testar a associação de grupo dinâmico e o licenciamento automático</span><span class="sxs-lookup"><span data-stu-id="7c665-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="7c665-119">Primeiro, você cria um novo grupo de vendas e adiciona uma regra de associação de grupo dinâmico para que as contas de usuário com o departamento definida como vendas sejam automaticamente adicionadas ao grupo vendas.</span><span class="sxs-lookup"><span data-stu-id="7c665-119">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="7c665-120">Usando uma instância privada do navegador da Internet, entre no centro de [Administração do microsoft 365](https://admin.microsoft.com) com a conta de administrador global da sua assinatura de laboratório de teste do Microsoft 365 e5.</span><span class="sxs-lookup"><span data-stu-id="7c665-120">Using a private instance of your Internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="7c665-121">Em uma guia separada do navegador, vá para o portal do Azure em [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="7c665-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="7c665-122">No portal do Azure, digite **grupos** na caixa de pesquisa e clique em **grupos**.</span><span class="sxs-lookup"><span data-stu-id="7c665-122">In the Azure portal, type **groups** in the search box, and then click **Groups**.</span></span>
4. <span data-ttu-id="7c665-123">no painel **todos os grupos** , clique em **novo grupo**.</span><span class="sxs-lookup"><span data-stu-id="7c665-123">in the **All groups** pane, click **New group**.</span></span>
5. <span data-ttu-id="7c665-124">Em **tipo de grupo**, selecione **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="7c665-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="7c665-125">Em **nome do grupo**, digite **vendas**.</span><span class="sxs-lookup"><span data-stu-id="7c665-125">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="7c665-126">Em **tipo de associação**, selecione **usuário dinâmico**.</span><span class="sxs-lookup"><span data-stu-id="7c665-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="7c665-127">Clique em **membros dinâmicos do usuário**.</span><span class="sxs-lookup"><span data-stu-id="7c665-127">Click **Dynamic user members**.</span></span>
9. <span data-ttu-id="7c665-128">No painel **regras de associação dinâmicas** :</span><span class="sxs-lookup"><span data-stu-id="7c665-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="7c665-129">Selecione a propriedade **Department** .</span><span class="sxs-lookup"><span data-stu-id="7c665-129">Select the **department** property.</span></span>
   - <span data-ttu-id="7c665-130">Selecione o operador **Equals** .</span><span class="sxs-lookup"><span data-stu-id="7c665-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="7c665-131">Digite **vendas** em **valor**.</span><span class="sxs-lookup"><span data-stu-id="7c665-131">Type **Sales** in **Value**.</span></span>
10. <span data-ttu-id="7c665-132">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7c665-132">Click **Save**.</span></span>
11. <span data-ttu-id="7c665-133">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="7c665-133">Click **Create**.</span></span>

<span data-ttu-id="7c665-134">Em seguida, configure o grupo de vendas para que os Membros recebam automaticamente a licença do Microsoft 365 e5.</span><span class="sxs-lookup"><span data-stu-id="7c665-134">Next, you configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="7c665-135">Clique no grupo **vendas** e, em seguida, clique em **licenças**.</span><span class="sxs-lookup"><span data-stu-id="7c665-135">Click the **Sales** group, and then click **Licenses**.</span></span>
2. <span data-ttu-id="7c665-136">No painel **Atualizar atribuições de licença** , selecione **Microsoft 365 E5**e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="7c665-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then click **Save**.</span></span>
3. <span data-ttu-id="7c665-137">Feche a guia do Portal do Azure no navegador.</span><span class="sxs-lookup"><span data-stu-id="7c665-137">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="7c665-138">Em seguida, teste a associação de grupo dinâmico e o licenciamento automático na conta do usuário 4.</span><span class="sxs-lookup"><span data-stu-id="7c665-138">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="7c665-139">Na guia **Microsoft Office Home** no navegador, clique em **administrador**.</span><span class="sxs-lookup"><span data-stu-id="7c665-139">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="7c665-140">Na guia **centro de administração do Microsoft 365** , clique em **usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="7c665-140">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="7c665-141">Na página **usuários ativos** , clique na conta do **usuário 4** .</span><span class="sxs-lookup"><span data-stu-id="7c665-141">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="7c665-142">No painel **usuário 4** , clique em **Editar** para **licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="7c665-142">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="7c665-143">No painel **licenças de produto** , desabilite a licença do **Microsoft 365 E5** e clique em **salvar > fechar**.</span><span class="sxs-lookup"><span data-stu-id="7c665-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="7c665-144">Nas propriedades da conta do usuário 4, verifique se nenhuma licença de produto foi atribuída e se não há associações de grupo.</span><span class="sxs-lookup"><span data-stu-id="7c665-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="7c665-145">Clique em **Editar** para obter **informações de contato**.</span><span class="sxs-lookup"><span data-stu-id="7c665-145">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="7c665-146">No painel **Editar informações de contato** , clique em **informações de contato**.</span><span class="sxs-lookup"><span data-stu-id="7c665-146">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="7c665-147">No campo **Departamento** , digite **vendas**e clique em **salvar > fechar**.</span><span class="sxs-lookup"><span data-stu-id="7c665-147">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="7c665-148">Aguarde alguns minutos e clique periodicamente no ícone atualizar no canto superior direito do painel usuário 4 da conta.</span><span class="sxs-lookup"><span data-stu-id="7c665-148">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="7c665-149">No momento, você verá:</span><span class="sxs-lookup"><span data-stu-id="7c665-149">In time you should see the:</span></span>

- <span data-ttu-id="7c665-150">Propriedade de **associações de grupo** atualizada com o grupo **Sales** .</span><span class="sxs-lookup"><span data-stu-id="7c665-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="7c665-151">Propriedade **Product licenses** atualizada com a licença do **Microsoft 365 E5** .</span><span class="sxs-lookup"><span data-stu-id="7c665-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="7c665-152">Consulte estes artigos para implantar a associação de grupo dinâmico e o licenciamento automático em produção:</span><span class="sxs-lookup"><span data-stu-id="7c665-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- <span data-ttu-id="7c665-153">LINK TBD</span><span class="sxs-lookup"><span data-stu-id="7c665-153">LINK TBD</span></span>
- <span data-ttu-id="7c665-154">LINK TBD</span><span class="sxs-lookup"><span data-stu-id="7c665-154">LINK TBD</span></span>

## <a name="next-step"></a><span data-ttu-id="7c665-155">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="7c665-155">Next step</span></span>

<span data-ttu-id="7c665-156">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="7c665-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c665-157">Confira também</span><span class="sxs-lookup"><span data-stu-id="7c665-157">See also</span></span>

[<span data-ttu-id="7c665-158">Roteiro de identidade</span><span class="sxs-lookup"><span data-stu-id="7c665-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="7c665-159">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="7c665-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="7c665-160">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="7c665-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="7c665-161">Documentação da Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="7c665-161">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
