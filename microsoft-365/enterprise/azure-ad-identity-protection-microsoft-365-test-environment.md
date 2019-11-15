---
title: Proteção de identidade do Azure AD para seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Configure o Azure AD Identity Protection e analise as contas atuais em seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: a21b20f4ca774ad38990e44abc18d666426e74d5
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640400"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="12493-103">Proteção de identidade do Azure AD para seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="12493-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="12493-104">O Azure AD Identity Protection permite que você detecte possíveis vulnerabilidades que afetam as identidades da sua organização, configure respostas automatizadas e investigue incidentes.</span><span class="sxs-lookup"><span data-stu-id="12493-104">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="12493-105">Este artigo descreve como habilitar a proteção de identidade do Azure AD e exibir a análise de suas contas de ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="12493-105">This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="12493-106">Há duas fases para configurar a proteção de identidade do Azure AD no seu ambiente de teste do Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="12493-106">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="12493-107">Criar o ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="12493-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="12493-108">Habilitar e usar a proteção de identidade do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="12493-108">Enable and use Azure AD Identity Protection.</span></span>

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="12493-110">Clique [aqui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="12493-110">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="12493-111">Fase 1: Criar o ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="12493-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="12493-112">Se você só quiser testar a proteção de identidade do Azure AD de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="12493-112">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="12493-113">Se você quiser testar a proteção de identidade do Azure AD em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="12493-113">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="12493-114">O teste da proteção de identidade do Azure AD não exige o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="12493-114">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="12493-115">Ele é fornecido aqui como uma opção para que você possa testar a proteção de identidade do Azure AD e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="12493-115">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="12493-116">Fase 2: habilitar e usar a proteção de identidade do Azure AD</span><span class="sxs-lookup"><span data-stu-id="12493-116">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="12493-117">Abra uma instância privada do navegador e entre no portal do Azure em [https://portal.azure.com](https://portal.azure.com) com a conta de administrador global do ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="12493-117">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="12493-118">No portal do Azure, clique em **todos os serviços > Marketplace**.</span><span class="sxs-lookup"><span data-stu-id="12493-118">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="12493-119">Digite **proteção de identidade do Azure ad** e clique nele.</span><span class="sxs-lookup"><span data-stu-id="12493-119">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="12493-120">Na folha **introdução** , clique em em **configurações** **, clique em** **fixar no painel**e clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="12493-120">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="12493-121">No portal do Azure, clique em **proteção de identidade do Azure ad** no painel.</span><span class="sxs-lookup"><span data-stu-id="12493-121">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="12493-122">Você deve ver uma lâmina **do Azure ad Identity Protection-visão geral** com um painel.</span><span class="sxs-lookup"><span data-stu-id="12493-122">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard.</span></span> <span data-ttu-id="12493-123">Em **vulnerabilidades**, observe que ela determinou o número de contas de usuário sem registro de autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="12493-123">Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration.</span></span> <span data-ttu-id="12493-124">Esse número varia de acordo com os guias anteriores do laboratório de teste do Microsoft 365 Enterprise que você fez.</span><span class="sxs-lookup"><span data-stu-id="12493-124">This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="12493-125">Clique nas categorias para **investigar** para ver se há usuários ou eventos detectados.</span><span class="sxs-lookup"><span data-stu-id="12493-125">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="12493-126">Para outros testes e experimentos, consulte [simulating Risk Events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="12493-126">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="12493-127">Consulte a etapa [proteger contra o comprometimento de credenciais](identity-secure-user-sign-ins.md#identity-ident-prot) na fase de identidade para obter informações e links para implantar a proteção de identidade do Azure AD em produção.</span><span class="sxs-lookup"><span data-stu-id="12493-127">See the [Protect against credential compromise](identity-secure-user-sign-ins.md#identity-ident-prot) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="12493-128">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="12493-128">Next step</span></span>

<span data-ttu-id="12493-129">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="12493-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="12493-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="12493-130">See also</span></span>

[<span data-ttu-id="12493-131">Fase 2: Identidade</span><span class="sxs-lookup"><span data-stu-id="12493-131">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="12493-132">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="12493-132">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="12493-133">Implantação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="12493-133">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="12493-134">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="12493-134">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
