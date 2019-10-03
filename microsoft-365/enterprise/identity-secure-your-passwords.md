---
title: 'Etapa 2: proteger suas senhas'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Você precisa de senhas fortes e gerenciáveis em toda a organização.
ms.openlocfilehash: 7bb4e0f296b320aa8a24916ded40089246308a20
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370398"
---
# <a name="step-2-secure-your-passwords"></a><span data-ttu-id="7c214-103">Etapa 2: proteger suas senhas</span><span class="sxs-lookup"><span data-stu-id="7c214-103">Step 2: Secure your passwords</span></span>

![Fase 2-identidade](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a><span data-ttu-id="7c214-105">Evitar o uso de senhas ruins</span><span class="sxs-lookup"><span data-stu-id="7c214-105">Prevent bad passwords</span></span>

<span data-ttu-id="7c214-106">*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="7c214-106">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7c214-107">Todos os usuários devem usar as [Diretrizes de senhas da Microsoft](https://www.microsoft.com/research/publication/password-guidance/) para criar senhas de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="7c214-107">All you users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance/) to create their user account passwords.</span></span>

<span data-ttu-id="7c214-108">Para impedir que os usuários criem senhas que possam ser facilmente descobertas, use a proteção de senhas do Azure AD, que usa uma lista geral e uma opcional de senhas proibidas, sendo a última especificada por você.</span><span class="sxs-lookup"><span data-stu-id="7c214-108">To prevent users from creating easily determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="7c214-109">Você pode, por exemplo, usar termos específicos da sua organização, como:</span><span class="sxs-lookup"><span data-stu-id="7c214-109">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="7c214-110">Nomes de marcas</span><span class="sxs-lookup"><span data-stu-id="7c214-110">Brand names</span></span>
- <span data-ttu-id="7c214-111">Nomes de produtos</span><span class="sxs-lookup"><span data-stu-id="7c214-111">Product names</span></span>
- <span data-ttu-id="7c214-112">Locais (por exemplo, sedes de empresas)</span><span class="sxs-lookup"><span data-stu-id="7c214-112">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="7c214-113">Termos internos específicos da empresa</span><span class="sxs-lookup"><span data-stu-id="7c214-113">Company-specific internal terms</span></span>
- <span data-ttu-id="7c214-114">Abreviaturas com significados específicos da empresa.</span><span class="sxs-lookup"><span data-stu-id="7c214-114">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="7c214-115">Você pode bloquear senhas ruins [na nuvem](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) e para seu [Active Directory Domain Services (AD DS) local](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span><span class="sxs-lookup"><span data-stu-id="7c214-115">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

<span data-ttu-id="7c214-116">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-password-prot) desta seção.</span><span class="sxs-lookup"><span data-stu-id="7c214-116">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-password-prot) for this section.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="7c214-117">Simplificar as redefinições de senha</span><span class="sxs-lookup"><span data-stu-id="7c214-117">Simplify password resets</span></span>

<span data-ttu-id="7c214-118">*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="7c214-118">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7c214-119">Nesta seção, você habilitará a redefinição de senha de autoatendimento (SSPR) para permitir que usuários redefinam ou desbloqueiem suas senhas ou contas.</span><span class="sxs-lookup"><span data-stu-id="7c214-119">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="7c214-120">Para ser alertado sobre uso indevido ou abuso, você pode usar os relatórios detalhados que rastreiam quando usuários acessam o sistema, junto com as notificações.</span><span class="sxs-lookup"><span data-stu-id="7c214-120">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="7c214-121">Você deve habilitar o write-back de senha antes que possa implantar as redefinições de senha.</span><span class="sxs-lookup"><span data-stu-id="7c214-121">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="7c214-122">Confira as[instruções para implantar redefinição de senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="7c214-122">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="7c214-124">Guia de laboratório de teste: redefinição de senha</span><span class="sxs-lookup"><span data-stu-id="7c214-124">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="7c214-125">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-pw-reset) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="7c214-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this section.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="7c214-126">Simplificar a entrada do usuário</span><span class="sxs-lookup"><span data-stu-id="7c214-126">Simplify user sign-in</span></span>

<span data-ttu-id="7c214-127">*Isso é opcional para ambientes híbridos e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="7c214-127">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7c214-128">Nesta seção, você vai configurar o Azure AD Seamless SSO (Logon Único Contínuo do Azure Active Directory), que funciona com PHS (Sincronização de Hash de Senha) e PTA (Autenticação de Passagem), para permitir que seus usuários entrem nos serviços que usam as contas de usuário do Azure AD sem precisar digitar suas senhas e em muitos casos, seus nomes de usuário.</span><span class="sxs-lookup"><span data-stu-id="7c214-128">In this section, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="7c214-129">Isso facilita o acesso de seus usuários a aplicativos baseados na nuvem, como o Office 365, sem precisar de nenhum componente adicional local, como servidores de federação de identidades.</span><span class="sxs-lookup"><span data-stu-id="7c214-129">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="7c214-130">Você configura o SSO Contínuo do Azure Active Directory com a ferramenta Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="7c214-130">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="7c214-131">Confira as [instruções para configurar o SSO Contínuo do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="7c214-131">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="7c214-133">Guia do Laboratório de Teste: Logon Único Contínuo do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="7c214-133">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="7c214-134">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-sso) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="7c214-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this section.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a><span data-ttu-id="7c214-135">Personalizar páginas de entrada do Office 365</span><span class="sxs-lookup"><span data-stu-id="7c214-135">Customize the Office 365 sign-in page</span></span>

<span data-ttu-id="7c214-136">*Isso é opcional e para as versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="7c214-136">*This is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="7c214-137">Nesta seção, você ajudará usuários a reconhecer a página de entrada da sua organização ao adicionar o nome, o logotipo da sua empresa e outros elementos reconhecíveis.</span><span class="sxs-lookup"><span data-stu-id="7c214-137">In this section, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="7c214-138">Com o Microsoft 365 Enterprise, é possível personalizar a aparência das páginas de entrada e do Painel de acesso para incluírem o logotipo da empresa, os esquemas de cores e as informações do usuário personalizadas.</span><span class="sxs-lookup"><span data-stu-id="7c214-138">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="7c214-139">Saiba mais em [Adicionar a marca da empresa na página de entrada do Office 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span><span class="sxs-lookup"><span data-stu-id="7c214-139">For more information, see [Add your company branding to Office 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="7c214-140">Confira as instruções de configuração em [Adicionar a marca da empresa na página de entrada e no Painel de acesso](http://aka.ms/aadpaddbranding).</span><span class="sxs-lookup"><span data-stu-id="7c214-140">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="7c214-141">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-custom-sign-in) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="7c214-141">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="7c214-142">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="7c214-142">Next step</span></span>

|||
|:-------|:-----|
|![Etapa 3](./media/stepnumbers/Step3.png)| [<span data-ttu-id="7c214-144">Proteger e gerenciar as entradas do seu usuário</span><span class="sxs-lookup"><span data-stu-id="7c214-144">Step 3: Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
