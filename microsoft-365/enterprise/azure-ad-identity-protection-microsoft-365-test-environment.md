---
title: Proteção de identidade do Azure AD para seu ambiente de teste do Microsoft 365 for Enterprise
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
description: Configure o Azure AD Identity Protection e analise as contas atuais no ambiente de teste do Microsoft 365 for Enterprise.
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487703"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="2c11e-103">Proteção de identidade do Azure AD para seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="2c11e-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="2c11e-104">*Este guia de laboratório de teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="2c11e-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="2c11e-105">Você pode usar a proteção de identidade do Azure Active Directory (Azure AD) para detectar possíveis vulnerabilidades que afetam as identidades da sua organização, configurar respostas automatizadas e investigar incidentes.</span><span class="sxs-lookup"><span data-stu-id="2c11e-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="2c11e-106">Este artigo descreve como usar a proteção de identidade do Azure AD para exibir a análise de suas contas de ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="2c11e-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="2c11e-107">A configuração da proteção de identidade do Azure AD no seu ambiente de teste do Microsoft 365 for Enterprise envolve duas fases:</span><span class="sxs-lookup"><span data-stu-id="2c11e-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="2c11e-108">Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="2c11e-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="2c11e-109">Fase 2: usar a proteção de identidade do Azure AD</span><span class="sxs-lookup"><span data-stu-id="2c11e-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="2c11e-111">Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="2c11e-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="2c11e-112">Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="2c11e-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="2c11e-113">Se você quiser testar apenas a proteção de identidade do Azure AD de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="2c11e-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="2c11e-114">Se você quiser testar a proteção de identidade do Azure AD em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="2c11e-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2c11e-115">O teste da proteção de identidade do Azure AD não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="2c11e-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="2c11e-116">Ele é fornecido aqui como uma opção para que você possa testar a proteção de identidade do Azure AD e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="2c11e-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="2c11e-117">Fase 2: usar a proteção de identidade do Azure AD</span><span class="sxs-lookup"><span data-stu-id="2c11e-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="2c11e-118">Abra uma instância privada do navegador e entre no portal do Azure em [https://portal.azure.com](https://portal.azure.com) com a conta de administrador global do seu ambiente de teste do Microsoft 365 for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2c11e-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="2c11e-119">No portal do Azure, digite **proteção de identidade** na caixa de pesquisa e selecione **proteção de identidade do Azure ad**.</span><span class="sxs-lookup"><span data-stu-id="2c11e-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="2c11e-120">Na folha **proteção de identidade – visão geral** , selecione cada relatório para ver o que está subordinado.</span><span class="sxs-lookup"><span data-stu-id="2c11e-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="2c11e-121">Em **notificar**, selecione **usuários em risco detectados alertas**.</span><span class="sxs-lookup"><span data-stu-id="2c11e-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="2c11e-122">No painel **usuários em risco detectados** , selecione **médio**.</span><span class="sxs-lookup"><span data-stu-id="2c11e-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="2c11e-123">Para **emails são enviados para os usuários a seguir**, selecione **incluídos** e verifique se sua conta de administrador global está na lista de membros selecionados.</span><span class="sxs-lookup"><span data-stu-id="2c11e-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="2c11e-124">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2c11e-124">Select **Save**.</span></span>

<span data-ttu-id="2c11e-125">Em **proteger**, selecione várias políticas para ver como configurá-las.</span><span class="sxs-lookup"><span data-stu-id="2c11e-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="2c11e-126">Se você criar e ativar uma política, certifique-se de que ela não esteja bloqueando o acesso de todos os usuários ou que você não consiga entrar.</span><span class="sxs-lookup"><span data-stu-id="2c11e-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="2c11e-127">Para evitar isso, exclua contas de usuário específicas, como administradores globais.</span><span class="sxs-lookup"><span data-stu-id="2c11e-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="2c11e-128">Para outros testes e experimentos, consulte [simulating Risk Events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span><span class="sxs-lookup"><span data-stu-id="2c11e-128">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="2c11e-129">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="2c11e-129">Next step</span></span>

<span data-ttu-id="2c11e-130">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="2c11e-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c11e-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="2c11e-131">See also</span></span>

[<span data-ttu-id="2c11e-132">Roteiro de identidade</span><span class="sxs-lookup"><span data-stu-id="2c11e-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="2c11e-133">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="2c11e-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2c11e-134">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="2c11e-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="2c11e-135">Documentação da Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="2c11e-135">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
