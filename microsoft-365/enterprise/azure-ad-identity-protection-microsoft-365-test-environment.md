---
title: Azure AD Identity Protection para seu ambiente de teste do Microsoft 365 para empresas
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
description: Configure o Azure AD Identity Protection e analise as contas atuais em seu ambiente de teste do Microsoft 365 para empresas.
ms.openlocfilehash: 162a6504fb7541874798f5e795bd2ecd590b5035
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487703"
---
# <a name="azure-ad-identity-protection-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ef973-103">Azure AD Identity Protection para seu ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="ef973-103">Azure AD Identity Protection for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ef973-104">*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="ef973-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="ef973-105">Você pode usar a Proteção de Identidade do Azure Active Directory (Azure AD) para detectar possíveis vulnerabilidades que afetam as identidades da sua organização, configurar respostas automatizadas e investigar incidentes.</span><span class="sxs-lookup"><span data-stu-id="ef973-105">You can use Azure Active Directory (Azure AD) Identity Protection to detect potential vulnerabilities that affect your organization’s identities, configure automated responses, and investigate incidents.</span></span> <span data-ttu-id="ef973-106">Este artigo descreve como usar o Azure AD Identity Protection para exibir a análise de suas contas de ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="ef973-106">This article describes how to use Azure AD Identity Protection to view the analysis of your test environment accounts.</span></span>

<span data-ttu-id="ef973-107">Configurar o Azure AD Identity Protection no ambiente de teste do Microsoft 365 para empresas envolve duas fases:</span><span class="sxs-lookup"><span data-stu-id="ef973-107">Setting up Azure AD Identity Protection in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="ef973-108">Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="ef973-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="ef973-109">Fase 2: Usar o Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="ef973-109">Phase 2: Use Azure AD Identity Protection</span></span>](#phase-2-use-azure-ad-identity-protection)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="ef973-111">Para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas, vá para a Pilha de Guias de Laboratório de Teste do [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)para empresas.</span><span class="sxs-lookup"><span data-stu-id="ef973-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="ef973-112">Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="ef973-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="ef973-113">Se você quiser testar apenas o Azure AD Identity Protection de maneira leve com os requisitos mínimos, siga as instruções na configuração [de base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="ef973-113">If you want to only test Azure AD Identity Protection in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ef973-114">Se você quiser testar o Azure AD Identity Protection em uma empresa simulada, siga as instruções na autenticação [de passagem.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="ef973-114">If you want to test Azure AD Identity Protection in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ef973-115">O teste do Azure AD Identity Protection não exige o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta do AD DS (Serviços de Domínio Active Directory).</span><span class="sxs-lookup"><span data-stu-id="ef973-115">Testing Azure AD Identity Protection doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="ef973-116">Ele é fornecido aqui como uma opção para que você possa testar o Azure AD Identity Protection e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="ef973-116">It is provided here as an option so that you can test Azure AD Identity Protection and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-use-azure-ad-identity-protection"></a><span data-ttu-id="ef973-117">Fase 2: Usar o Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="ef973-117">Phase 2: Use Azure AD Identity Protection</span></span>

1. <span data-ttu-id="ef973-118">Abra uma instância privada do navegador e entre no portal do Azure com a conta de administrador global do seu ambiente de teste do [https://portal.azure.com](https://portal.azure.com) Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="ef973-118">Open a private instance of your browser and sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the global administrator account of your Microsoft 365 for enterprise test environment.</span></span>
2. <span data-ttu-id="ef973-119">No portal do Azure, digite **a proteção de** identidade na caixa de pesquisa e selecione **Azure AD Identity Protection.**</span><span class="sxs-lookup"><span data-stu-id="ef973-119">In the Azure portal, type **identity protection** in the search box, and then select **Azure AD Identity Protection**.</span></span>
3. <span data-ttu-id="ef973-120">Na folha **Proteção de Identidade - Visão** geral, selecione cada relatório para ver o que está relatando.</span><span class="sxs-lookup"><span data-stu-id="ef973-120">In the **Identity Protection - Overview** blade, select each report to see what it's reporting.</span></span>
4. <span data-ttu-id="ef973-121">Em **Notificar,** **selecione Usuários em risco alertas detectados.**</span><span class="sxs-lookup"><span data-stu-id="ef973-121">Under **Notify**, select **Users at risk detected alerts**.</span></span>
5. <span data-ttu-id="ef973-122">No painel **Usuários em risco detectado alertas,** selecione **Médio**.</span><span class="sxs-lookup"><span data-stu-id="ef973-122">In the **Users at risk detected alerts** pane, select **Medium**.</span></span>
6. <span data-ttu-id="ef973-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span><span class="sxs-lookup"><span data-stu-id="ef973-123">For **Emails are sent to the following users**, select **Included** and verify that your global admin account is in the list of selected members.</span></span>
7. <span data-ttu-id="ef973-124">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ef973-124">Select **Save**.</span></span>

<span data-ttu-id="ef973-125">Em **Proteger,** selecione várias polícias para ver como configurá-las.</span><span class="sxs-lookup"><span data-stu-id="ef973-125">Under **Protect**, select various polices to see how to configure them.</span></span> <span data-ttu-id="ef973-126">Se você criar e ativar uma política, certifique-se de que ela não está bloqueando o acesso de todos os usuários ou talvez não consiga entrar.</span><span class="sxs-lookup"><span data-stu-id="ef973-126">If you create and activate a policy, make sure that it's not blocking access for all users, or you might not be able to sign in.</span></span> <span data-ttu-id="ef973-127">Para evitar isso, exclua contas de usuário específicas, como administradores globais.</span><span class="sxs-lookup"><span data-stu-id="ef973-127">To prevent this, exclude specific user accounts, such as global admins.</span></span>

<span data-ttu-id="ef973-128">Para mais testes e experimentação, consulte [Simulando eventos de risco.](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook)</span><span class="sxs-lookup"><span data-stu-id="ef973-128">For further testing and experimentation, see [Simulating risk events](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-playbook).</span></span>

## <a name="next-step"></a><span data-ttu-id="ef973-129">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="ef973-129">Next step</span></span>

<span data-ttu-id="ef973-130">Explorar recursos e funcionalidades adicionais de [identidade](m365-enterprise-test-lab-guides.md#identity) no ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="ef973-130">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ef973-131">Confira também</span><span class="sxs-lookup"><span data-stu-id="ef973-131">See also</span></span>

[<span data-ttu-id="ef973-132">Mapa de identidade</span><span class="sxs-lookup"><span data-stu-id="ef973-132">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="ef973-133">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="ef973-133">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ef973-134">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="ef973-134">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="ef973-135">Documentação do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="ef973-135">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
