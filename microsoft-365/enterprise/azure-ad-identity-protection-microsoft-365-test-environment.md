---
title: Proteção de identidade do Azure AD para seu ambiente de teste do Microsoft 365 Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure o Azure AD Identity Protection e analise as contas atuais em seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 3f3740e42c7ec909f44a3c761dfc743359b3f030
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633639"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="634e9-103">Proteção de identidade do Azure AD para seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="634e9-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="634e9-104">*Este Guia de Laboratório de Testes pode ser usado apenas em ambientes de teste do Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="634e9-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="634e9-105">A proteção de identidade do Azure Active Directory (Azure AD) permite que você detecte possíveis vulnerabilidades que afetam as identidades da sua organização, configurem respostas automatizadas e investigue incidentes.</span><span class="sxs-lookup"><span data-stu-id="634e9-105">Azure Active Directory (Azure AD) Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="634e9-106">Este artigo descreve como usar a proteção de identidade do Azure AD para exibir a análise de suas contas de ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="634e9-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="634e9-107">Há duas fases para configurar a proteção de identidade do Azure AD no seu ambiente de teste do Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="634e9-107">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="634e9-108">Criar o ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="634e9-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="634e9-109">Usar a proteção de identidade do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="634e9-109">Use Azure AD Identity Protection.</span></span>

![Guias de laboratório de teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="634e9-111">Clique [aqui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos na pilha do Guia do Test Lab do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="634e9-111">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="634e9-112">Fase 1: Criar o ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="634e9-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="634e9-113">Se você só quiser testar a proteção de identidade do Azure AD de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="634e9-113">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="634e9-114">Se você quiser testar a proteção de identidade do Azure AD em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="634e9-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="634e9-115">O teste da proteção de identidade do Azure AD não exige o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="634e9-115">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="634e9-116">Ele é fornecido aqui como uma opção para que você possa testar a proteção de identidade do Azure AD e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="634e9-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="634e9-117">Fase 2: usar a proteção de identidade do Azure AD</span><span class="sxs-lookup"><span data-stu-id="634e9-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="634e9-118">Abra uma instância privada do navegador e entre no portal do Azure em [https://portal.azure.com](https://portal.azure.com) com a conta de administrador global do ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="634e9-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="634e9-119">No portal do Azure, digite **proteção de identidade** na caixa de pesquisa e clique em **proteção de identidade do Azure ad**.</span><span class="sxs-lookup"><span data-stu-id="634e9-119">In the Azure portal, type **identity protection** in the search box, and then click **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="634e9-120">Na folha **proteção de identidade – visão geral** , clique em cada um dos relatórios para ver o que estão subordinados.</span><span class="sxs-lookup"><span data-stu-id="634e9-120">In the **Identity Protection - Overview** blade, click on each of the reports to see what they are reporting.</span></span>
4. <span data-ttu-id="634e9-121">Em **notificar**, clique em **usuários em risco detectados alertas**.</span><span class="sxs-lookup"><span data-stu-id="634e9-121">Under **Notify**, click **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="634e9-122">No painel **usuários em risco detectados** , selecione **médio**.</span><span class="sxs-lookup"><span data-stu-id="634e9-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="634e9-123">Para **emails são enviados para os usuários a seguir**, clique em **incluído** e verifique se sua conta de administrador global está na lista de membros selecionados.</span><span class="sxs-lookup"><span data-stu-id="634e9-123">For **Emails are sent to the following users**, click **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="634e9-124">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="634e9-124">Click **Save**.</span></span>

<span data-ttu-id="634e9-125">Clique nas diferentes políticas em **proteger** para ver como configurá-las.</span><span class="sxs-lookup"><span data-stu-id="634e9-125">Click through the different policies under **Protect** to see how to configure them.</span></span> <span data-ttu-id="634e9-126">Se você criar e ativar uma política, certifique-se de que ela não está bloqueando o acesso para um escopo de condições muito grande ou talvez você não consiga entrar, mesmo que o administrador global.</span><span class="sxs-lookup"><span data-stu-id="634e9-126">If you create and activate a policy, make sure it is not blocking access for too wide a scope of conditions, or you might not be able to sign in, even as the global admin.</span></span>

<span data-ttu-id="634e9-127">Para outros testes e experimentos, consulte [simulating Risk Events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="634e9-127">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="634e9-128">Consulte a etapa [proteger contra o comprometimento de credenciais](identity-secure-user-sign-ins.md#identity-ident-prot) na fase de identidade para obter informações e links para implantar a proteção de identidade do Azure AD em produção.</span><span class="sxs-lookup"><span data-stu-id="634e9-128">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="634e9-129">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="634e9-129">Next step</span></span>

<span data-ttu-id="634e9-130">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="634e9-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="634e9-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="634e9-131">See also</span></span>

[<span data-ttu-id="634e9-132">Fase 2: Identidade</span><span class="sxs-lookup"><span data-stu-id="634e9-132">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="634e9-133">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="634e9-133">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="634e9-134">Implantação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="634e9-134">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="634e9-135">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="634e9-135">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
