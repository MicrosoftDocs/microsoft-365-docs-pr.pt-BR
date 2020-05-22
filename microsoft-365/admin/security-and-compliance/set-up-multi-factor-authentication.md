---
title: Configurar a autenticação multifator para usuários
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Saiba como configurar a autenticação multifator para sua organização.
monikerRange: o365-worldwide
ms.openlocfilehash: 893a4ae535dfb781a4f77ee57c0ead40fda8454f
ms.sourcegitcommit: 185d62f41f6b173894ba6e3e87b11b2b5d02db58
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2020
ms.locfileid: "44340769"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="3a161-103">Configurar a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="3a161-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="3a161-104">Com base na sua compreensão da [MFA (autenticação multifator) e de seu suporte no Microsoft 365](multi-factor-authentication-microsoft-365.md), é hora de configurá-la e revertê-la em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3a161-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="3a161-105">Antes de começar, determine se essas condições especiais se aplicam a você e execute a ação apropriada:</span><span class="sxs-lookup"><span data-stu-id="3a161-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="3a161-106">Se você tiver clientes do Office 2013 em dispositivos Windows, [habilite a autenticação moderna](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="3a161-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="3a161-107">Se você tiver serviços de diretório de terceiros com o AD FS (serviços de Federação do Active Directory), configure o servidor do Azure MFA.</span><span class="sxs-lookup"><span data-stu-id="3a161-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="3a161-108">Consulte [cenários avançados com a autenticação multifator do Azure e soluções VPN de terceiros](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3a161-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="3a161-109">Etapa 1: decida o método de exigir que seus usuários usem a MFA</span><span class="sxs-lookup"><span data-stu-id="3a161-109">Step 1: Decide on the method of requiring your users to use MFA</span></span>

<span data-ttu-id="3a161-110">Há três maneiras de exigir que os usuários utilizem a MFA para entradas. Confira [suporte da MFA no Microsoft 365](multi-factor-authentication-microsoft-365.md) para obter os detalhes.</span><span class="sxs-lookup"><span data-stu-id="3a161-110">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="3a161-111">Padrões de segurança (recomendado para pequenas empresas)</span><span class="sxs-lookup"><span data-stu-id="3a161-111">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="3a161-112">Se você comprou sua assinatura ou avaliação após 21 de outubro de 2019, e se você for solicitado inesperadamente pela MFA, [os padrões de segurança](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) foram automaticamente habilitados para sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="3a161-112">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="3a161-113">Todas as novas assinaturas do Microsoft 365 terão automaticamente os padrões de segurança ativados.</span><span class="sxs-lookup"><span data-stu-id="3a161-113">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="3a161-114">Isso significa que cada usuário terá que configurar a MFA e instalar o aplicativo Microsoft Authenticator em seu dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="3a161-114">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="3a161-115">Todos os usuários devem usar o aplicativo Microsoft Authenticator, pois o método adicional de verificação e a autenticação herdada são bloqueados.</span><span class="sxs-lookup"><span data-stu-id="3a161-115">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="3a161-116">Políticas de acesso condicional (recomendadas para empresas)</span><span class="sxs-lookup"><span data-stu-id="3a161-116">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="3a161-117">Os usuários escolhem o método de verificação adicional durante o registro de MFA.</span><span class="sxs-lookup"><span data-stu-id="3a161-117">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="3a161-118">Conta por usuário (não recomendado)</span><span class="sxs-lookup"><span data-stu-id="3a161-118">Per-user account (not recommended)</span></span>

  <span data-ttu-id="3a161-119">Os usuários escolhem o método de verificação adicional durante o registro de MFA.</span><span class="sxs-lookup"><span data-stu-id="3a161-119">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="3a161-120">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="3a161-120">Step 2.</span></span> <span data-ttu-id="3a161-121">Teste MFA nos seus usuários pilotos</span><span class="sxs-lookup"><span data-stu-id="3a161-121">Test MFA on your pilot users</span></span>

<span data-ttu-id="3a161-122">Se você estiver usando políticas de acesso condicional ou por usuário (não recomendado), selecione usuários piloto em sua empresa ou organização para testar o registro e as entradas da MFA. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3a161-122">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="3a161-123">Para políticas de acesso condicional, crie um grupo de usuários piloto e uma política que exija MFA para os membros do grupo e para todos os aplicativos.</span><span class="sxs-lookup"><span data-stu-id="3a161-123">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="3a161-124">Em seguida, adicione as contas do usuário piloto ao grupo.</span><span class="sxs-lookup"><span data-stu-id="3a161-124">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="3a161-125">Para a MFA por usuário, habilite a MFA para as contas de usuário de seus usuários pilotos uma vez.</span><span class="sxs-lookup"><span data-stu-id="3a161-125">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="3a161-126">Trabalhe com seus usuários pilotos para resolver dúvidas e problemas para se preparar para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="3a161-126">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="3a161-127">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="3a161-127">Step 3.</span></span> <span data-ttu-id="3a161-128">Informar à sua organização que a MFA está chegando</span><span class="sxs-lookup"><span data-stu-id="3a161-128">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="3a161-129">Use notificações por email, cartazes de corredor, reuniões de equipe ou treinamento formal para garantir que seus funcionários compreendam:</span><span class="sxs-lookup"><span data-stu-id="3a161-129">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="3a161-130">Por que a MFA é necessária para os logins</span><span class="sxs-lookup"><span data-stu-id="3a161-130">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="3a161-131">Como se registrar para o método de verificação adicional</span><span class="sxs-lookup"><span data-stu-id="3a161-131">How to register for their additional verification method</span></span>](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [<span data-ttu-id="3a161-132">Como entrar após o registro</span><span class="sxs-lookup"><span data-stu-id="3a161-132">How to sign-in after registration</span></span>](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="3a161-133">Como alterar o método de verificação adicional</span><span class="sxs-lookup"><span data-stu-id="3a161-133">How to change their additional verification method</span></span>](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="3a161-134">Como lidar com situações como um novo telefone inteligente</span><span class="sxs-lookup"><span data-stu-id="3a161-134">How to deal with situations like a new smart phone</span></span>](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="3a161-135">Mais importante, certifique-se de que seus funcionários entendam ***quando o requisito da MFA será imposto*** para que ele não seja surpresa.</span><span class="sxs-lookup"><span data-stu-id="3a161-135">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="3a161-136">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="3a161-136">Step 4.</span></span> <span data-ttu-id="3a161-137">Distribuir o requisito da MFA para sua organização ou usuários</span><span class="sxs-lookup"><span data-stu-id="3a161-137">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="3a161-138">Com base no método de solicitação de MFA escolhido, distribua a autenticação MFA para os funcionários além dos seus testadores piloto.</span><span class="sxs-lookup"><span data-stu-id="3a161-138">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="3a161-139">Padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="3a161-139">Security defaults</span></span>

<span data-ttu-id="3a161-140">Habilite ou desabilite os padrões de segurança no painel de **Propriedades** do Azure Active Directory (Azure AD) no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="3a161-140">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="3a161-141">Entre no centro de [Administração do Microsoft 365](https://admin.microsoft.com) com as credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="3a161-141">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="3a161-142">Vá para a [página Azure Active Directory-Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="3a161-142">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="3a161-143">Na parte inferior da página, clique em **Gerenciar padrões de segurança**.</span><span class="sxs-lookup"><span data-stu-id="3a161-143">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="3a161-144">Escolha **Sim** para habilitar os padrões de segurança e **não** para desabilitar os padrões de segurança e, em seguida, escolha **salvar**.</span><span class="sxs-lookup"><span data-stu-id="3a161-144">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="3a161-145">Se você estiver usando [políticas de acesso condicional da linha de base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), veja como mover para usar os padrões de segurança.</span><span class="sxs-lookup"><span data-stu-id="3a161-145">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="3a161-146">Vá para a [página de políticas de acesso condicional](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="3a161-146">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="3a161-147">Escolha cada política de linha de base que está **ativada** e defina **habilitar política** como **desativado**.</span><span class="sxs-lookup"><span data-stu-id="3a161-147">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="3a161-148">Vá para a [página Azure Active Directory-Properties](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="3a161-148">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="3a161-149">Na parte inferior da página, clique em **Gerenciar padrões de segurança**.</span><span class="sxs-lookup"><span data-stu-id="3a161-149">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="3a161-150">Escolha **Sim** para habilitar os padrões de segurança e **não** para desabilitar os padrões de segurança e, em seguida, escolha **salvar**.</span><span class="sxs-lookup"><span data-stu-id="3a161-150">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="3a161-151">Políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="3a161-151">Conditional Access policies</span></span>

<span data-ttu-id="3a161-152">Crie, configure ou habilite as políticas apropriadas que incluem o grupo de usuários que exigem MFA de entrada.</span><span class="sxs-lookup"><span data-stu-id="3a161-152">Create, configure, or enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="3a161-153">MFA por usuário (não recomendado)</span><span class="sxs-lookup"><span data-stu-id="3a161-153">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="3a161-154">Habilitar contas de usuário para MFA correspondente à sua distribuição.</span><span class="sxs-lookup"><span data-stu-id="3a161-154">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="3a161-155">Suporte aos seus funcionários</span><span class="sxs-lookup"><span data-stu-id="3a161-155">Supporting your employees</span></span>

<span data-ttu-id="3a161-156">À medida que seus funcionários se registram e começam a entrar com a MFA, certifique-se de que seus especialistas de ti, departamento de ti ou helpdesk podem responder perguntas e resolver problemas rapidamente.</span><span class="sxs-lookup"><span data-stu-id="3a161-156">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="3a161-157">Confira este artigo para obter [informações sobre como solucionar problemas de entradas MFA](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span><span class="sxs-lookup"><span data-stu-id="3a161-157">See this article for [information about troubleshooting MFA sign-ins](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


