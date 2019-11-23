---
title: Automatizar o licenciamento e a associação de grupo para seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure o licenciamento baseado em grupo e a associação de grupos dinâmicos em seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: b1f3bc4a44e66d162360e82295c8f2877131cd07
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202472"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="26c4f-103">Automatizar o licenciamento e a associação de grupo para seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="26c4f-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="26c4f-104">*Este Guia de Laboratório de Testes pode ser usado apenas em ambientes de teste do Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="26c4f-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="26c4f-105">O licenciamento baseado em grupo atribui ou remove automaticamente licenças de uma conta de usuário com base na associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="26c4f-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="26c4f-106">A associação de grupo dinâmico adiciona ou remove membros de um grupo com base nas propriedades da conta de usuário, como departamento ou país.</span><span class="sxs-lookup"><span data-stu-id="26c4f-106">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="26c4f-107">Este artigo orienta você através de uma demonstração do ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="26c4f-107">This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="26c4f-108">Há duas fases para configurar o licenciamento automático e a associação de grupo dinâmico no ambiente de teste do Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="26c4f-108">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="26c4f-109">Criar o ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="26c4f-109">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="26c4f-110">Configurar e testar a associação de grupo dinâmico e o licenciamento automático.</span><span class="sxs-lookup"><span data-stu-id="26c4f-110">Configure and test dynamic group membership and automatic licensing.</span></span>

![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="26c4f-112">Clique [aqui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="26c4f-112">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="26c4f-113">Fase 1: Criar o ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="26c4f-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="26c4f-114">Se você só quiser testar o licenciamento automatizado e a associação de grupo de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="26c4f-114">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="26c4f-115">Se você quiser testar o licenciamento automatizado e a associação de grupo em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="26c4f-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="26c4f-116">Testar o licenciamento automatizado e a associação de grupo não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="26c4f-116">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="26c4f-117">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="26c4f-117">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="26c4f-118">Fase 2: configurar e testar a associação de grupo dinâmico e o licenciamento automático</span><span class="sxs-lookup"><span data-stu-id="26c4f-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="26c4f-119">Primeiro, você cria um novo grupo de vendas e adiciona uma regra de associação de grupo dinâmico para que as contas de usuário com o departamento definida como vendas sejam automaticamente adicionadas ao grupo vendas.</span><span class="sxs-lookup"><span data-stu-id="26c4f-119">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="26c4f-120">Usando uma instância privada do navegador da Internet, entre no portal do Office 365 em [https://portal.office.com](https://portal.office.com) com a conta de administrador global da sua assinatura de laboratório de teste do Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="26c4f-120">Using a private instance of your Internet browser, sign in to the Office 365 portal at [https://portal.office.com](https://portal.office.com) with the global administrator account of your Office 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="26c4f-121">Em uma guia separada do navegador, vá para o portal do Azure em [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="26c4f-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="26c4f-122">No Portal do Azure, clique em **Azure Active Directory > Usuários e grupos > Todos os grupos**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-122">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
4. <span data-ttu-id="26c4f-123">Na folha **todos os grupos** , clique em **novo grupo**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-123">On the **All groups** blade, click **New group**.</span></span>
5. <span data-ttu-id="26c4f-124">Em **tipo de grupo**, selecione **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-124">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="26c4f-125">Em **nome do grupo**, digite **vendas**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-125">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="26c4f-126">Em **tipo de associação**, selecione **usuário dinâmico** .</span><span class="sxs-lookup"><span data-stu-id="26c4f-126">In **Membership type**, select **Dynamic user** .</span></span>
8. <span data-ttu-id="26c4f-127">Clique em **Adicionar consulta dinâmica**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-127">Click **Add dynamic query**.</span></span>
9. <span data-ttu-id="26c4f-128">Em **Adicionar usuários onde**, selecione **departamento**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-128">In **Add users where**, select **department**.</span></span>
10. <span data-ttu-id="26c4f-129">No campo seguinte, selecione **Igual a**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-129">In the next field, select **Equals**.</span></span>
11. <span data-ttu-id="26c4f-130">No campo seguinte, digite **Sales**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-130">In the next field, type **Sales**.</span></span>
12. <span data-ttu-id="26c4f-131">Clique em **Adicionar consulta** e, em seguida, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-131">Click **Add query**, and then click **Create**.</span></span>
13. <span data-ttu-id="26c4f-132">Feche as lâminas **Group** e **groups-All Groups** .</span><span class="sxs-lookup"><span data-stu-id="26c4f-132">Close the **Group** and **Groups-All groups** blades.</span></span>

<span data-ttu-id="26c4f-133">Em seguida, configure o grupo de vendas para que os Membros recebam automaticamente a licença do Microsoft 365 e5.</span><span class="sxs-lookup"><span data-stu-id="26c4f-133">Next, you configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="26c4f-134">Na folha **visão geral** do Azure Active Directory, clique em **licenças > todos os produtos**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-134">On the **Overview** blade for Azure Active Directory, click **Licenses > All products**.</span></span>
2. <span data-ttu-id="26c4f-135">Na lista, selecione **Micrsooft 365 E5**e clique em **atribuir**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-135">In the list, select **Micrsooft 365 E5**, and then click **Assign**.</span></span>
3. <span data-ttu-id="26c4f-136">Na folha **atribuir licença** , clique em **usuários e grupos**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-136">On the **Assign license** blade, click **Users and groups**.</span></span>
4. <span data-ttu-id="26c4f-137">Na lista de grupos, selecione o grupo **vendas** .</span><span class="sxs-lookup"><span data-stu-id="26c4f-137">In the list of groups, select the **Sales** group.</span></span>
5. <span data-ttu-id="26c4f-138">Clique em **Selecionar** e clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-138">Click **Select**, and then click **Assign**.</span></span>
6. <span data-ttu-id="26c4f-139">Feche a guia do Portal do Azure no navegador.</span><span class="sxs-lookup"><span data-stu-id="26c4f-139">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="26c4f-140">Em seguida, teste a associação de grupo dinâmico e o licenciamento automático na conta do usuário 4.</span><span class="sxs-lookup"><span data-stu-id="26c4f-140">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="26c4f-141">Na guia **Microsoft Office Home** no navegador, clique em **administrador**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-141">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="26c4f-142">Na guia **centro de administração do Microsoft 365** , clique em **usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-142">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="26c4f-143">Na página **usuários ativos** , clique na conta do **usuário 4** .</span><span class="sxs-lookup"><span data-stu-id="26c4f-143">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="26c4f-144">No painel **usuário 4** , clique em **Editar** para **licenças de produto**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-144">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="26c4f-145">No painel **licenças de produto** , desabilite a licença do **Microsoft 365 E5** e clique em **salvar > fechar**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-145">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="26c4f-146">Nas propriedades da conta do usuário 4, verifique se nenhuma licença de produto foi atribuída e se não há associações de grupo.</span><span class="sxs-lookup"><span data-stu-id="26c4f-146">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="26c4f-147">Clique em **Editar** para obter **informações de contato**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-147">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="26c4f-148">No painel **Editar informações de contato** , clique em **informações de contato**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-148">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="26c4f-149">No campo **Departamento** , digite **vendas**e clique em **salvar > fechar**.</span><span class="sxs-lookup"><span data-stu-id="26c4f-149">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="26c4f-150">Aguarde alguns minutos e clique periodicamente no ícone atualizar no canto superior direito do painel usuário 4 da conta.</span><span class="sxs-lookup"><span data-stu-id="26c4f-150">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="26c4f-151">No momento, você verá:</span><span class="sxs-lookup"><span data-stu-id="26c4f-151">In time you should see the:</span></span>

- <span data-ttu-id="26c4f-152">Propriedade de **associações de grupo** atualizada com o grupo **Sales** .</span><span class="sxs-lookup"><span data-stu-id="26c4f-152">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="26c4f-153">Propriedade **Product licenses** atualizada com a licença do **Microsoft 365 E5** .</span><span class="sxs-lookup"><span data-stu-id="26c4f-153">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="26c4f-154">Consulte estas etapas na fase de identidade para obter informações e links para implantar a associação de grupo dinâmico e o licenciamento automático em produção:</span><span class="sxs-lookup"><span data-stu-id="26c4f-154">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="26c4f-155">Configurar licenciamentos automáticos</span><span class="sxs-lookup"><span data-stu-id="26c4f-155">Set up automatic licensing</span></span>](identity-use-group-management.md#identity-group-license)
- [<span data-ttu-id="26c4f-156">Configurar a associação de grupo dinâmica</span><span class="sxs-lookup"><span data-stu-id="26c4f-156">Set up dynamic group membership</span></span>](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a><span data-ttu-id="26c4f-157">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="26c4f-157">Next step</span></span>

<span data-ttu-id="26c4f-158">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="26c4f-158">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="26c4f-159">Confira também</span><span class="sxs-lookup"><span data-stu-id="26c4f-159">See also</span></span>

[<span data-ttu-id="26c4f-160">Fase 2: Identidade</span><span class="sxs-lookup"><span data-stu-id="26c4f-160">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="26c4f-161">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="26c4f-161">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="26c4f-162">Implantação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="26c4f-162">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="26c4f-163">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="26c4f-163">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
