---
title: Automatizar o licenciamento e a associação de grupo para seu Microsoft 365 para ambiente de teste empresarial
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
description: Configure o licenciamento baseado em grupo e a associação dinâmica de grupo em seu Microsoft 365 ambiente de teste empresarial.
ms.openlocfilehash: 26840e2884202a0fa9c4bb563f3d7c653482ef87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905363"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a8d3e-103">Automatizar o licenciamento e a associação de grupo para seu Microsoft 365 para ambiente de teste empresarial</span><span class="sxs-lookup"><span data-stu-id="a8d3e-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a8d3e-104">*Este Guia de Laboratório de Teste só pode ser usado para Microsoft 365 ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="a8d3e-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="a8d3e-105">O licenciamento baseado em grupo atribui ou remove automaticamente licenças para uma conta de usuário com base na associação ao grupo.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="a8d3e-106">A associação de grupo dinâmica adiciona ou remove membros a um grupo com base nas propriedades da conta de usuário, como **Departamento** ou **País.**</span><span class="sxs-lookup"><span data-stu-id="a8d3e-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="a8d3e-107">Este artigo explica as demonstrações de como adicionar e remover membros do grupo em seu Microsoft 365 ambiente de teste empresarial.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="a8d3e-108">Configurar o licenciamento automático e a associação dinâmica de grupo em seu Microsoft 365 ambiente de teste empresarial envolve duas fases:</span><span class="sxs-lookup"><span data-stu-id="a8d3e-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="a8d3e-109">Fase 1: criar seu Microsoft 365 para ambiente de teste empresarial</span><span class="sxs-lookup"><span data-stu-id="a8d3e-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="a8d3e-110">Fase 2: Configurar e testar a associação dinâmica do grupo e o licenciamento automático</span><span class="sxs-lookup"><span data-stu-id="a8d3e-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="a8d3e-112">Para um mapa visual de todos os artigos na pilha Microsoft 365 guia do laboratório de teste empresarial, vá para o Microsoft 365 para a pilha de guias de laboratório [de teste corporativos.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="a8d3e-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="a8d3e-113">Fase 1: criar seu Microsoft 365 para ambiente de teste empresarial</span><span class="sxs-lookup"><span data-stu-id="a8d3e-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="a8d3e-114">Se você quiser testar apenas o licenciamento automatizado e a associação de grupo de forma leve com os requisitos mínimos, siga as instruções em [Configuração base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="a8d3e-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="a8d3e-115">Se você quiser testar o licenciamento automatizado e a associação de grupo em uma empresa simulada, siga as instruções em [Autenticação passagem.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="a8d3e-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="a8d3e-116">Testar o licenciamento automatizado e a associação ao grupo não exige o ambiente de teste empresarial simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio do Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="a8d3e-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="a8d3e-117">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento automatizado e a associação ao grupo e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="a8d3e-118">Fase 2: Configurar e testar a associação dinâmica do grupo e o licenciamento automático</span><span class="sxs-lookup"><span data-stu-id="a8d3e-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="a8d3e-119">Primeiro, crie um novo grupo chamado Vendas e adicione uma regra dinâmica de associação de grupo para que as contas de usuário com o **Departamento** definidas como **Vendas** insuem automaticamente no grupo Vendas.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="a8d3e-120">Em uma instância privada do navegador da [](https://admin.microsoft.com) Internet, entre no centro de administração Microsoft 365 com a conta de administrador global da sua assinatura de laboratório de teste Microsoft 365 E5 de teste.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="a8d3e-121">Em uma guia separada do navegador, vá para o portal do Azure em [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="a8d3e-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="a8d3e-122">No portal do Azure, insira **grupos** na caixa de pesquisa e selecione **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="a8d3e-123">no painel **Todos os grupos,** selecione **Novo grupo**.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="a8d3e-124">Em **Tipo de grupo,** selecione **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="a8d3e-125">Em **Nome do grupo,** insira **Vendas**.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="a8d3e-126">Em **Tipo de associação,** selecione **Usuário dinâmico**.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="a8d3e-127">Selecione **Membros do usuário dinâmico**.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="a8d3e-128">No painel **Regras de associação** dinâmicas:</span><span class="sxs-lookup"><span data-stu-id="a8d3e-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="a8d3e-129">Selecione a **propriedade department.**</span><span class="sxs-lookup"><span data-stu-id="a8d3e-129">Select the **department** property.</span></span>
   - <span data-ttu-id="a8d3e-130">Selecione o **operador Equals.**</span><span class="sxs-lookup"><span data-stu-id="a8d3e-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="a8d3e-131">Na caixa **Valor,** digite **Vendas**.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="a8d3e-132">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-132">Select **Save**.</span></span>
11. <span data-ttu-id="a8d3e-133">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-133">Select **Create**.</span></span>

<span data-ttu-id="a8d3e-134">Em seguida, configure o grupo Vendas para que os membros sejam atribuídos automaticamente Microsoft 365 E5 licença.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="a8d3e-135">Selecione o **grupo Vendas** e selecione **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="a8d3e-136">No painel **Atualizar atribuições** de licença, selecione **Microsoft 365 E5** e, em seguida, **selecione Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="a8d3e-137">No navegador, feche a guia portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="a8d3e-138">Em seguida, teste a associação dinâmica do grupo e o licenciamento automático na conta usuário 4:</span><span class="sxs-lookup"><span data-stu-id="a8d3e-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="a8d3e-139">Na guia **Microsoft Office Página** 1 do navegador, selecione **Admin**.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="a8d3e-140">Na guia **Microsoft 365 centro de administração,** selecione **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="a8d3e-141">Na página **Usuários ativos,** selecione a **conta Usuário 4.**</span><span class="sxs-lookup"><span data-stu-id="a8d3e-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="a8d3e-142">No painel **Usuário 4,** selecione **Editar** para **licenças de produto.**</span><span class="sxs-lookup"><span data-stu-id="a8d3e-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="a8d3e-143">No painel **Licenças de** produto, desabilite a **Microsoft 365 E5** e selecione **Salvar**  >  **Fechar.**</span><span class="sxs-lookup"><span data-stu-id="a8d3e-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="a8d3e-144">Nas propriedades da conta Usuário 4, verifique se nenhuma licença de produto foi atribuída e se não há associações de grupo.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="a8d3e-145">Para **obter informações de contato,** selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="a8d3e-146">No painel **Editar informações de** contato, selecione Informações de **contato**.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="a8d3e-147">Na caixa **Departamento,** digite **Vendas** e, em seguida, selecione **Salvar**  >  **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="a8d3e-148">Aguarde alguns minutos e selecione periodicamente o ícone Atualizar no canto superior direito do painel de contas Usuário 4. </span><span class="sxs-lookup"><span data-stu-id="a8d3e-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="a8d3e-149">Com o tempo, você deve ver o:</span><span class="sxs-lookup"><span data-stu-id="a8d3e-149">In time, you should see the:</span></span>

- <span data-ttu-id="a8d3e-150">**Propriedade de associações de** grupo atualizada com o **grupo Vendas.**</span><span class="sxs-lookup"><span data-stu-id="a8d3e-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="a8d3e-151">**Propriedade product licenses** updated with the **Microsoft 365 E5** license.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="a8d3e-152">Consulte estes artigos para implantar a associação dinâmica de grupo e o licenciamento automático na produção:</span><span class="sxs-lookup"><span data-stu-id="a8d3e-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="a8d3e-153">Licenciamento baseado em grupo em Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a8d3e-153">Group-based licensing in Azure Active Directory</span></span>](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="a8d3e-154">Grupos dinâmicos no Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a8d3e-154">Dynamic groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="a8d3e-155">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="a8d3e-155">Next step</span></span>

<span data-ttu-id="a8d3e-156">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="a8d3e-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="a8d3e-157">Confira também</span><span class="sxs-lookup"><span data-stu-id="a8d3e-157">See also</span></span>

[<span data-ttu-id="a8d3e-158">Roteiro de identidade</span><span class="sxs-lookup"><span data-stu-id="a8d3e-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="a8d3e-159">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="a8d3e-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="a8d3e-160">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="a8d3e-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="a8d3e-161">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="a8d3e-161">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)