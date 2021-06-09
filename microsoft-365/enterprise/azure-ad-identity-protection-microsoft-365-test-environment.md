---
title: Proteção de Identidade do Azure AD para seu Microsoft 365 para ambiente de teste corporativo
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
description: Configure a Proteção de Identidade do Azure AD e analise as contas atuais em seu Microsoft 365 ambiente de teste empresarial.
ms.openlocfilehash: 0cb0acf3faee13676573b04178bd6b4d3d36da4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905339"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="5566f-103">Proteção de Identidade do Azure AD para seu Microsoft 365 para ambiente de teste corporativo</span><span class="sxs-lookup"><span data-stu-id="5566f-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="5566f-104">*Este Guia de Laboratório de Teste só pode ser usado para Microsoft 365 ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="5566f-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="5566f-105">Você pode usar Azure Active Directory Proteção de Identidade (Azure AD) para detectar possíveis vulnerabilidades que afetam as identidades da sua organização, configurar respostas automatizadas e investigar incidentes.</span><span class="sxs-lookup"><span data-stu-id="5566f-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="5566f-106">Este artigo descreve como usar a Proteção de Identidade do Azure AD para exibir a análise de suas contas de ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="5566f-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="5566f-107">Configurar a Proteção de Identidade do Azure AD em seu Microsoft 365 ambiente de teste empresarial envolve duas fases:</span><span class="sxs-lookup"><span data-stu-id="5566f-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="5566f-108">Fase 1: criar seu Microsoft 365 para ambiente de teste empresarial</span><span class="sxs-lookup"><span data-stu-id="5566f-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="5566f-109">Fase 2: Usar a Proteção de Identidade do Azure AD</span><span class="sxs-lookup"><span data-stu-id="5566f-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="5566f-111">Para um mapa visual de todos os artigos na pilha Microsoft 365 guia do laboratório de teste empresarial, vá para o Microsoft 365 para a pilha de guias de laboratório [de teste corporativos.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="5566f-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="5566f-112">Fase 1: criar seu Microsoft 365 para ambiente de teste empresarial</span><span class="sxs-lookup"><span data-stu-id="5566f-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="5566f-113">Se você quiser apenas testar a Proteção de Identidade do Azure AD de forma leve com os requisitos mínimos, siga as instruções em [Configuração base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="5566f-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="5566f-114">Se você quiser testar a Proteção de Identidade do Azure AD em uma empresa simulada, siga as instruções em [Autenticação passagem.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="5566f-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5566f-115">Testar a Proteção de Identidade do Azure AD não exige o ambiente de teste empresarial simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos Serviços de Domínio do Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="5566f-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="5566f-116">Ele é fornecido aqui como uma opção para que você possa testar a Proteção de Identidade do Azure AD e experimentá-la em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="5566f-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="5566f-117">Fase 2: Usar a Proteção de Identidade do Azure AD</span><span class="sxs-lookup"><span data-stu-id="5566f-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="5566f-118">Abra uma instância privada do navegador e entre no portal do Azure em com a conta de administrador global do seu Microsoft 365 [https://portal.azure.com](https://portal.azure.com) para ambiente de teste empresarial.</span><span class="sxs-lookup"><span data-stu-id="5566f-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="5566f-119">No portal do Azure, digite **proteção de** identidade na caixa de pesquisa e selecione Proteção de Identidade do **Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="5566f-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="5566f-120">Na folha **Proteção de Identidade - Visão** geral, selecione cada relatório para ver o que ele está relatando.</span><span class="sxs-lookup"><span data-stu-id="5566f-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="5566f-121">Em **Notificar**, selecione **Usuários em risco detectados alertas**.</span><span class="sxs-lookup"><span data-stu-id="5566f-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="5566f-122">No painel **Usuários em risco detectados alertas,** selecione **Médio**.</span><span class="sxs-lookup"><span data-stu-id="5566f-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="5566f-123">Para **Emails são enviados para os seguintes usuários**, selecione **Incluído** e verifique se sua conta de administrador global está na lista de membros selecionados.</span><span class="sxs-lookup"><span data-stu-id="5566f-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="5566f-124">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5566f-124">Select **Save**.</span></span>

<span data-ttu-id="5566f-125">Em **Proteger**, selecione várias polícias para ver como configurá-las.</span><span class="sxs-lookup"><span data-stu-id="5566f-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="5566f-126">Se você criar e ativar uma política, certifique-se de que ela não está bloqueando o acesso para todos os usuários, ou talvez você não consiga entrar.</span><span class="sxs-lookup"><span data-stu-id="5566f-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="5566f-127">Para evitar isso, exclua contas de usuário específicas, como administradores globais.</span><span class="sxs-lookup"><span data-stu-id="5566f-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="5566f-128">Para mais testes e experimentações, consulte [Simulando eventos de risco](/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="5566f-128">For further testing and experimentation, see [Simulating risk events](/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="5566f-129">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="5566f-129">Next step</span></span>

<span data-ttu-id="5566f-130">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="5566f-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="5566f-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="5566f-131">See also</span></span>

[<span data-ttu-id="5566f-132">Roteiro de identidade</span><span class="sxs-lookup"><span data-stu-id="5566f-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="5566f-133">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5566f-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5566f-134">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5566f-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5566f-135">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5566f-135">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)