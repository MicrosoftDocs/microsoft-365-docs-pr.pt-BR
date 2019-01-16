---
title: Ambiente de teste de proteção de identidade AD Azure para a sua empresa de 365 da Microsoft
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
description: Configurar a proteção de identidade do Windows Azure AD e analisar as contas atuais em seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 165667ad2122839336ef0790ab5661cff53ca32b
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864763"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e4326-103">Ambiente de teste de proteção de identidade AD Azure para a sua empresa de 365 da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e4326-103">Azure AD Identity Protection for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="e4326-p101">Proteção de identidade AD Azure permite detectar possíveis vulnerabilidades afetar identidades da sua organização, configurar respostas automatizadas e investigar incidentes. Este artigo descreve como habilitar a proteção de identidade do Windows Azure AD e exibir a análise de suas contas do ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="e4326-p101">Azure AD Identity Protection allows you to detect potential vulnerabilities affecting your organization’s identities, configure automated responses, and investigate incidents. This article describes how to enable Azure AD Identity Protection and view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="e4326-106">Há duas fases à configuração de proteção de identidade do Windows Azure AD no seu ambiente de teste do Microsoft 365 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="e4326-106">There are two phases to setting up Azure AD Identity Protection in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="e4326-107">Crie o ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e4326-107">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="e4326-108">Habilitar e usar a proteção de identidade do Windows Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e4326-108">Enable and use Azure AD Identity Protection.</span></span>

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="e4326-110">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e4326-110">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="e4326-111">Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e4326-111">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="e4326-112">Se você deseja testar a proteção de identidade do Windows Azure AD de forma leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="e4326-112">If you just want to test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="e4326-113">Se você deseja testar a proteção de identidade do Windows Azure AD em uma empresa simulada, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="e4326-113">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e4326-p102">Testando a proteção de identidade do Windows Azure AD não requer que o ambiente de teste de simulado empresarial, que inclui uma intranet simulada conectada à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar a proteção de identidade do Windows Azure AD e experimentar em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="e4326-p102">Testing Azure AD Identity Protection does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-enable-and-use-azure-ad-identity-protection"></a><span data-ttu-id="e4326-116">Fase 2: Habilitar e usar a proteção de identidade do Windows Azure AD</span><span class="sxs-lookup"><span data-stu-id="e4326-116">Phase 2: Enable and use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="e4326-117">Abra uma instância particular do navegador e acesse o portal do Windows Azure em [https://portal.azure.com](https://portal.azure.com) com a conta de administrador global do seu ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e4326-117">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="e4326-118">No portal do Azure, clique em **todos os serviços > Marketplace**.</span><span class="sxs-lookup"><span data-stu-id="e4326-118">In the Azure portal, click **All services > Marketplace**.</span></span>
3. <span data-ttu-id="e4326-119">Digite **proteção de identidade do Windows Azure AD** e, em seguida, clique nele.</span><span class="sxs-lookup"><span data-stu-id="e4326-119">Type **Azure AD Identity Protection** and then click it.</span></span>
4. <span data-ttu-id="e4326-120">No blade **Introdução** , clique em **Onboard** em **configurações**, clique em **Fixar no painel**e, em seguida, clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="e4326-120">On the **Getting Started** blade, click **Onboard** under **Settings**, click **Pin to dashboard**, and then click **Create**.</span></span>
5. <span data-ttu-id="e4326-121">No portal do Azure, clique em **proteção de identidade do Windows Azure AD** , no painel.</span><span class="sxs-lookup"><span data-stu-id="e4326-121">In the Azure portal, click **Azure AD Identity Protection** on the dashboard.</span></span> 

   <span data-ttu-id="e4326-p103">Você deverá ver um blade **Azure AD proteção-visão geral da identidade** com um painel. Sob **vulnerabilidades**, observe que ele determinado o número de contas de usuário sem registro a autenticação multifator. Esse número variará com base no anterior Microsoft 365 Enterprise Test Lab Guides que você fez.</span><span class="sxs-lookup"><span data-stu-id="e4326-p103">You should see an **Azure AD Identity Protection-Overview** blade with a dashboard. Under **Vulnerabilities**, notice that it determined the number of user accounts without multi-factor authentication registration. This number will vary based on previous Microsoft 365 Enterprise Test Lab Guides that you have done.</span></span>

6. <span data-ttu-id="e4326-125">Clique nas categorias para **investigar** ver se há qualquer usuários ou os eventos que foram detectados.</span><span class="sxs-lookup"><span data-stu-id="e4326-125">Click through the categories for **Investigate** to see if there are any users or events that have been detected.</span></span>

<span data-ttu-id="e4326-126">Para outros testes e experimentação, consulte [Simulating eventos de risco](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="e4326-126">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

<span data-ttu-id="e4326-127">Consulte a etapa de [proteger contra credencial comprometer](identity-azure-ad-identity-protection.md) na fase de identidade para obter informações e links para implantar a proteção de identidade do Windows Azure AD na produção.</span><span class="sxs-lookup"><span data-stu-id="e4326-127">See the [Protect against credential compromise](identity-azure-ad-identity-protection.md) step in the Identity phase for information and links to deploy Azure AD Identity Protection in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="e4326-128">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="e4326-128">Next step</span></span>

<span data-ttu-id="e4326-129">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="e4326-129">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4326-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="e4326-130">See also</span></span>

[<span data-ttu-id="e4326-131">Fase 2: Identidade</span><span class="sxs-lookup"><span data-stu-id="e4326-131">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="e4326-132">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e4326-132">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e4326-133">Implantação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e4326-133">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="e4326-134">Documentação do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e4326-134">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
