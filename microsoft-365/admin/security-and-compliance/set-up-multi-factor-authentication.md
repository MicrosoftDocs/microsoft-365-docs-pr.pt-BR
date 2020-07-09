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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Saiba como configurar a autenticação multifator para a sua organização.
monikerRange: o365-worldwide
ms.openlocfilehash: b0fd16fc74319c88a6f91bf56ac96346915c35ac
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049755"
---
# <a name="set-up-multi-factor-authentication"></a><span data-ttu-id="54fd9-103">Configurar a autenticação multifator</span><span class="sxs-lookup"><span data-stu-id="54fd9-103">Set up multi-factor authentication</span></span>
  
<span data-ttu-id="54fd9-104">Com base no seu conhecimento de [MFA (autenticação multifator) e seu suporte no Microsoft 365](multi-factor-authentication-microsoft-365.md), é hora de configurá-la e distribuí-la para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="54fd9-104">Based on your understanding of [multi-factor authentication (MFA) and its support in Microsoft 365](multi-factor-authentication-microsoft-365.md), it’s time to set it up and roll it out to your organization.</span></span>

<span data-ttu-id="54fd9-105">Antes de começar, determine se estas condições especiais se aplicam a você e execute a ação adequada:</span><span class="sxs-lookup"><span data-stu-id="54fd9-105">Before you begin, determine if these special conditions apply to you and take the appropriate action:</span></span>

- <span data-ttu-id="54fd9-106">Se você tem clientes do Office 2013 em dispositivos Windows, [habilitar Autenticação Moderna](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span><span class="sxs-lookup"><span data-stu-id="54fd9-106">If you have Office 2013 clients on Windows devices, [enable Modern Authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).</span></span>

- <span data-ttu-id="54fd9-107">Se você tiver serviços de diretório de terceiros com o AD FS (Serviços de Federação do Active Directory), configure o Servidor do Azure MFA.</span><span class="sxs-lookup"><span data-stu-id="54fd9-107">If you have third-party directory services with Active Directory Federation Services (AD FS), set up the Azure MFA Server.</span></span> <span data-ttu-id="54fd9-108">Confira [cenários avançados com a Autenticação Multifator do Azure e soluções VPN de terceiros](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="54fd9-108">See [advanced scenarios with Azure Multi-Factor Authentication and third-party VPN solutions](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) for more information.</span></span>

<span data-ttu-id="54fd9-109">Todos os outros usuários serão solicitados a executar uma autenticação adicional quando necessário.</span><span class="sxs-lookup"><span data-stu-id="54fd9-109">All other users will be asked to perform additional authentication when needed.</span></span> <span data-ttu-id="54fd9-110">Para saber mais, acesse [Método e configurações de verificação de dois fatores](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span><span class="sxs-lookup"><span data-stu-id="54fd9-110">For more information, please visit [Two-factor verification method and settings](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device).</span></span>

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a><span data-ttu-id="54fd9-111">Etapa 1: Decidir o método de exigir que os usuários usem a MFA</span><span class="sxs-lookup"><span data-stu-id="54fd9-111">Step 1: Decide on the method of requiring your users to use MFA</span></span>

> [!NOTE]
> <span data-ttu-id="54fd9-112">Você deve ser um administrador global para configurar ou modificar a MFA.</span><span class="sxs-lookup"><span data-stu-id="54fd9-112">You must be a global admin to set up or modify MFA.</span></span> <span data-ttu-id="54fd9-113">Há três maneiras de exigir que os usuários usem a MFA de entradas. Confira [Suporte a MFA no Microsoft 365](multi-factor-authentication-microsoft-365.md) para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="54fd9-113">There are three ways to require your users to use MFA for sign-ins. See [MFA support in Microsoft 365](multi-factor-authentication-microsoft-365.md) for the details.</span></span>

- <span data-ttu-id="54fd9-114">Padrões de segurança (recomendado para pequenas empresas)</span><span class="sxs-lookup"><span data-stu-id="54fd9-114">Security defaults (recommended for small businesses)</span></span>

  <span data-ttu-id="54fd9-115">Se você comprou a sua assinatura ou a versão de avaliação após 21 de outubro de 2019 e for inesperadamente solicitado a executar a MFA, [os padrões de segurança](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) foram automaticamente habilitados para a sua assinatura.</span><span class="sxs-lookup"><span data-stu-id="54fd9-115">If you purchased your subscription or trial after October 21, 2019, and you're unexpectedly prompted for MFA, [security defaults](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) have been automatically enabled for your subscription.</span></span>
  
  <span data-ttu-id="54fd9-116">Todos os novos recursos de assinatura do Microsoft 365 terão automaticamente os padrões de segurança ativados.</span><span class="sxs-lookup"><span data-stu-id="54fd9-116">Every new Microsoft 365 subscription will automatically have security defaults turned on.</span></span> <span data-ttu-id="54fd9-117">Isso significa que todos os usuários terão que configurar a MFA e instalar o aplicativo Microsoft Authenticator no seu dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="54fd9-117">This means that every user will have to set up MFA and install the Microsoft Authenticator app on their mobile device.</span></span>

  <span data-ttu-id="54fd9-118">Todos os usuários devem usar o aplicativo Microsoft Authenticator como método de verificação adicional e a autenticação herdada será bloqueada.</span><span class="sxs-lookup"><span data-stu-id="54fd9-118">All users must use the Microsoft Authenticator app as their additional verification method and legacy authentication is blocked.</span></span> 

- <span data-ttu-id="54fd9-119">Políticas de acesso condicional (recomendado para empresas)</span><span class="sxs-lookup"><span data-stu-id="54fd9-119">Conditional Access policies (recommended for enterprises)</span></span>

  <span data-ttu-id="54fd9-120">Os usuários escolhem o método de verificação adicional durante o registro da MFA.</span><span class="sxs-lookup"><span data-stu-id="54fd9-120">Users choose the additional verification method during MFA registration.</span></span>

- <span data-ttu-id="54fd9-121">Conta por usuário (não recomendado)</span><span class="sxs-lookup"><span data-stu-id="54fd9-121">Per-user account (not recommended)</span></span>

  <span data-ttu-id="54fd9-122">Os usuários escolhem o método de verificação adicional durante o registro da MFA.</span><span class="sxs-lookup"><span data-stu-id="54fd9-122">Users choose the additional verification method during MFA registration.</span></span>

## <a name="step-2-test-mfa-on-your-pilot-users"></a><span data-ttu-id="54fd9-123">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="54fd9-123">Step 2.</span></span> <span data-ttu-id="54fd9-124">Testar a MFA em seus usuários piloto</span><span class="sxs-lookup"><span data-stu-id="54fd9-124">Test MFA on your pilot users</span></span>

<span data-ttu-id="54fd9-125">Se você estiver usando políticas de acesso condicional ou MFA por usuário (não recomendado), selecione usuários piloto na sua empresa ou organização para testar o registro e as entradas da MFA. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="54fd9-125">If you are using Conditional Access policies or per-user MFA (not recommended), select pilot users in your business or organization to test MFA registration and sign-ins. For example:</span></span>

- <span data-ttu-id="54fd9-126">Para políticas de acesso condicional, crie um grupo de usuários piloto e uma política que exija MFA para os membros do grupo e para todos os aplicativos.</span><span class="sxs-lookup"><span data-stu-id="54fd9-126">For Conditional Access policies, create a pilot users group and a policy that requires MFA for the members of the group and for all apps.</span></span> <span data-ttu-id="54fd9-127">Em seguida, adicione as contas do usuário piloto ao grupo.</span><span class="sxs-lookup"><span data-stu-id="54fd9-127">Then, add your pilot user’s accounts to the group.</span></span>

- <span data-ttu-id="54fd9-128">No MFA por usuário, habilite a MFA das contas de usuários do piloto uma vez.</span><span class="sxs-lookup"><span data-stu-id="54fd9-128">For per-user MFA, enable MFA for the user accounts of your pilot users one a time.</span></span>

<span data-ttu-id="54fd9-129">Trabalhe com seus usuários piloto para solucionar problemas e dúvidas sobre como se preparar para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="54fd9-129">Work with your pilot users to address questions and issues to prepare for a smooth roll out to your organization.</span></span>

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a><span data-ttu-id="54fd9-130">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="54fd9-130">Step 3.</span></span> <span data-ttu-id="54fd9-131">Informar à sua organização que a MFA está chegando</span><span class="sxs-lookup"><span data-stu-id="54fd9-131">Inform your organization that MFA is coming</span></span>

<span data-ttu-id="54fd9-132">Use notificações por email, pôsteres de corredor, reuniões da equipe ou treinamento oficial para garantir que seus funcionários compreendam:</span><span class="sxs-lookup"><span data-stu-id="54fd9-132">Use email notifications, hallway posters, team meetings, or formal training to ensure that your employees understand:</span></span>

- <span data-ttu-id="54fd9-133">Por que a MFA está sendo necessária para entradas</span><span class="sxs-lookup"><span data-stu-id="54fd9-133">Why MFA is being required for sign-ins</span></span>
- [<span data-ttu-id="54fd9-134">Como se inscrever para obter o método de verificação adicional</span><span class="sxs-lookup"><span data-stu-id="54fd9-134">How to register for their additional verification method</span></span>](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [<span data-ttu-id="54fd9-135">Como entrar após o registro</span><span class="sxs-lookup"><span data-stu-id="54fd9-135">How to sign-in after registration</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [<span data-ttu-id="54fd9-136">Como alterar o método de verificação adicional</span><span class="sxs-lookup"><span data-stu-id="54fd9-136">How to change their additional verification method</span></span>](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [<span data-ttu-id="54fd9-137">Como lidar com situações como um novo smartphone</span><span class="sxs-lookup"><span data-stu-id="54fd9-137">How to deal with situations like a new smart phone</span></span>](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

<span data-ttu-id="54fd9-138">O mais importante, certifique-se de que seus funcionários entendem ***quando o requisito da MFA será imposto*** para que eles não se surpreendam.</span><span class="sxs-lookup"><span data-stu-id="54fd9-138">Most importantly, make sure your employees understand ***when the MFA requirement is going to be imposed*** so that it does not surprise them.</span></span>

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a><span data-ttu-id="54fd9-139">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="54fd9-139">Step 4.</span></span> <span data-ttu-id="54fd9-140">Implementar o requisito da MFA da sua organização ou usuários</span><span class="sxs-lookup"><span data-stu-id="54fd9-140">Roll out the MFA requirement to your organization or users</span></span>

<span data-ttu-id="54fd9-141">Com base no método de requisito da MFA, distribua a autenticação MFA para os funcionários que estão além de seus testadores piloto.</span><span class="sxs-lookup"><span data-stu-id="54fd9-141">Based on your chosen MFA requirement method, roll out MFA authentication to the employees beyond your pilot testers.</span></span>

### <a name="security-defaults"></a><span data-ttu-id="54fd9-142">Padrões de segurança</span><span class="sxs-lookup"><span data-stu-id="54fd9-142">Security defaults</span></span>

<span data-ttu-id="54fd9-143">Habilite ou desabilite as opções de segurança no painel de **Propriedades** para o Azure Active Directory (Azure AD) no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="54fd9-143">You enable or disable security defaults from the **Properties** pane for Azure Active Directory (Azure AD) in the Azure portal.</span></span>

1.  <span data-ttu-id="54fd9-144">Acessar o [Centro de administração do Microsoft 365](https://admin.microsoft.com) com credenciais de administrador global.</span><span class="sxs-lookup"><span data-stu-id="54fd9-144">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with global admin credentials.</span></span>
2.  <span data-ttu-id="54fd9-145">Vá para [Azure Active Directory - Página Propriedades](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="54fd9-145">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
3.  <span data-ttu-id="54fd9-146">Na parte inferior da página, clique em **Gerenciar Padrões de segurança**.</span><span class="sxs-lookup"><span data-stu-id="54fd9-146">At the bottom of the page, choose **Manage Security defaults**.</span></span>
4.  <span data-ttu-id="54fd9-147">Clique em **Sim** para habilitar os padrões de segurança e em **Não** para desabilitar o padrão de segurança e, em seguida, escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="54fd9-147">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

<span data-ttu-id="54fd9-148">Se você estiver usando [políticas de Acesso Condicional da linha de base](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), veja aqui como mover para usar padrões de segurança.</span><span class="sxs-lookup"><span data-stu-id="54fd9-148">If you have been using [baseline Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection), here is how you move to using security defaults.</span></span>

1.  <span data-ttu-id="54fd9-149">Vá para a página [Acesso Condicional - página Políticas](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span><span class="sxs-lookup"><span data-stu-id="54fd9-149">Go to the [Conditional Access - Policies page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).</span></span>
2.  <span data-ttu-id="54fd9-150">Escolha cada política de linha de base que esteja **Ativada** e defina **Permitir que a política** seja **Desativada**.</span><span class="sxs-lookup"><span data-stu-id="54fd9-150">Choose each baseline policy that is **On** and set **Enable policy** to **Off**.</span></span>
2.  <span data-ttu-id="54fd9-151">Vá para [Azure Active Directory - Página Propriedades](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="54fd9-151">Go to the [Azure Active Directory - Properties page](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span>
4.  <span data-ttu-id="54fd9-152">Na parte inferior da página, clique em **Gerenciar Padrões de segurança**.</span><span class="sxs-lookup"><span data-stu-id="54fd9-152">At the bottom of the page, choose **Manage Security defaults**.</span></span>
5.  <span data-ttu-id="54fd9-153">Clique em **Sim** para habilitar os padrões de segurança e em **Não** para desabilitar o padrão de segurança e, em seguida, escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="54fd9-153">Choose **Yes** to enable security defaults and **No** to disable security defaults, and then choose **Save**.</span></span>

### <a name="conditional-access-policies"></a><span data-ttu-id="54fd9-154">Políticas de Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="54fd9-154">Conditional Access policies</span></span>

<span data-ttu-id="54fd9-155">Crie, configure e habilite as políticas apropriadas que incluem o grupo de usuários que exigem MFA de entrada.</span><span class="sxs-lookup"><span data-stu-id="54fd9-155">Create, configure, and enable the appropriate policies that include the group of users that require MFA for sign-in.</span></span>

### <a name="per-user-mfa-not-recommended"></a><span data-ttu-id="54fd9-156">MFA por usuário (não recomendado)</span><span class="sxs-lookup"><span data-stu-id="54fd9-156">Per-user MFA (not recommended)</span></span>

<span data-ttu-id="54fd9-157">Habilite as contas de usuário da MFA correspondentes à sua distribuição.</span><span class="sxs-lookup"><span data-stu-id="54fd9-157">Enable user accounts for MFA corresponding to your rollout.</span></span>

### <a name="supporting-your-employees"></a><span data-ttu-id="54fd9-158">Suporte a seus funcionários</span><span class="sxs-lookup"><span data-stu-id="54fd9-158">Supporting your employees</span></span>

<span data-ttu-id="54fd9-159">À medida que seus funcionários se inscreverem e começarem a entrar com a MFA, certifique-se de que os especialistas de TI, o departamento de TI ou o helpdesk possam responder a perguntas e resolver problemas rapidamente.</span><span class="sxs-lookup"><span data-stu-id="54fd9-159">As your employees register and begin signing in with MFA, ensure that your IT specialists, IT department, or helpdesk can answer questions and address issues quickly.</span></span>

<span data-ttu-id="54fd9-160">Confira este artigo para obter [informações sobre como solucionar problemas de entrada MFA](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span><span class="sxs-lookup"><span data-stu-id="54fd9-160">See this article for [information about troubleshooting MFA sign-ins](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2).</span></span> 


