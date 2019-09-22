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
ms.openlocfilehash: 06d936a68432b55912b1c10839336dc94e698f51
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073205"
---
# <a name="step-2-secure-your-passwords"></a><span data-ttu-id="eefff-103">Etapa 2: proteger suas senhas</span><span class="sxs-lookup"><span data-stu-id="eefff-103">Step 2: Secure your privileged identities</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a><span data-ttu-id="eefff-104">Evitar o uso de senhas ruins</span><span class="sxs-lookup"><span data-stu-id="eefff-104">Prevent bad passwords</span></span>

<span data-ttu-id="eefff-105">*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="eefff-105">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="eefff-106">Todos os usuários devem usar as [Diretrizes de senhas da Microsoft](https://www.microsoft.com/research/publication/password-guidance/) para criar senhas de conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="eefff-106">All you users should be using [Microsoft's password guidance](https://www.microsoft.com/research/publication/password-guidance/) to create their user account passwords.</span></span>

<span data-ttu-id="eefff-107">Para impedir que os usuários criem senhas que possam ser facilmente descobertas, use a proteção de senhas do Azure AD, que usa uma lista geral e uma opcional de senhas proibidas, sendo a última especificada por você.</span><span class="sxs-lookup"><span data-stu-id="eefff-107">To prevent users from creating easily determined password, use Azure AD password protection, which uses both a global banned password list and an optional custom banned password list that you specify.</span></span> <span data-ttu-id="eefff-108">Você pode, por exemplo, usar termos específicos da sua organização, como:</span><span class="sxs-lookup"><span data-stu-id="eefff-108">For example, you can specify terms that are specific to your organization, such as:</span></span>

- <span data-ttu-id="eefff-109">Nomes de marcas</span><span class="sxs-lookup"><span data-stu-id="eefff-109">Brand names</span></span>
- <span data-ttu-id="eefff-110">Nomes de produtos</span><span class="sxs-lookup"><span data-stu-id="eefff-110">Product names</span></span>
- <span data-ttu-id="eefff-111">Locais (por exemplo, sedes de empresas)</span><span class="sxs-lookup"><span data-stu-id="eefff-111">Locations (for example, such as company headquarters)</span></span>
- <span data-ttu-id="eefff-112">Termos internos específicos da empresa</span><span class="sxs-lookup"><span data-stu-id="eefff-112">Company-specific internal terms</span></span>
- <span data-ttu-id="eefff-113">Abreviaturas com significados específicos da empresa.</span><span class="sxs-lookup"><span data-stu-id="eefff-113">Abbreviations that have specific company meaning</span></span>

<span data-ttu-id="eefff-114">Você pode bloquear senhas ruins [na nuvem](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) e para seu [Active Directory Domain Services (AD DS) local](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span><span class="sxs-lookup"><span data-stu-id="eefff-114">You can ban bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises).</span></span>

<span data-ttu-id="eefff-115">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-password-prot) desta seção.</span><span class="sxs-lookup"><span data-stu-id="eefff-115">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-password-prot) for this section.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="eefff-116">Simplificar as redefinições de senha</span><span class="sxs-lookup"><span data-stu-id="eefff-116">Simplify password resets</span></span>

<span data-ttu-id="eefff-117">*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="eefff-117">*This is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="eefff-118">Nesta seção, você habilitará a redefinição de senha de autoatendimento (SSPR) para permitir que usuários redefinam ou desbloqueiem suas senhas ou contas.</span><span class="sxs-lookup"><span data-stu-id="eefff-118">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="eefff-119">Para ser alertado sobre uso indevido ou abuso, você pode usar os relatórios detalhados que rastreiam quando usuários acessam o sistema, junto com as notificações.</span><span class="sxs-lookup"><span data-stu-id="eefff-119">To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="eefff-120">Você deve habilitar o write-back de senha antes que possa implantar as redefinições de senha.</span><span class="sxs-lookup"><span data-stu-id="eefff-120">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="eefff-121">Confira as[instruções para implantar redefinição de senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="eefff-121">See the [instructions to roll out password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="eefff-123">Guia de laboratório de teste: redefinição de senha</span><span class="sxs-lookup"><span data-stu-id="eefff-123">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="eefff-124">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-pw-reset) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="eefff-124">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this section.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="eefff-125">Simplificar a entrada do usuário</span><span class="sxs-lookup"><span data-stu-id="eefff-125">Simplify user sign-in</span></span>

<span data-ttu-id="eefff-126">*Isso é opcional para ambientes híbridos e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="eefff-126">*This is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="eefff-127">Nesta seção, você vai configurar o Azure AD Seamless SSO (Logon Único Contínuo do Azure Active Directory), que funciona com PHS (Sincronização de Hash de Senha) e PTA (Autenticação de Passagem), para permitir que seus usuários entrem nos serviços que usam as contas de usuário do Azure AD sem precisar digitar suas senhas e em muitos casos, seus nomes de usuário.</span><span class="sxs-lookup"><span data-stu-id="eefff-127">In this section, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames.</span></span> <span data-ttu-id="eefff-128">Isso facilita o acesso de seus usuários a aplicativos baseados na nuvem, como o Office 365, sem precisar de nenhum componente adicional local, como servidores de federação de identidades.</span><span class="sxs-lookup"><span data-stu-id="eefff-128">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="eefff-129">Você configura o SSO Contínuo do Azure Active Directory com a ferramenta Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="eefff-129">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="eefff-130">Confira as [instruções para configurar o SSO Contínuo do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="eefff-130">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="eefff-132">Guia do Laboratório de Teste: Logon Único Contínuo do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="eefff-132">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="eefff-133">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-sso) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="eefff-133">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this section.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a><span data-ttu-id="eefff-134">Personalizar páginas de entrada do Office 365</span><span class="sxs-lookup"><span data-stu-id="eefff-134">Customize the Office 365 sign-in page</span></span>

<span data-ttu-id="eefff-135">*Isso é opcional e para as versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="eefff-135">*This is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="eefff-136">Nesta seção, você ajudará usuários a reconhecer a página de entrada da sua organização ao adicionar o nome, o logotipo da sua empresa e outros elementos reconhecíveis.</span><span class="sxs-lookup"><span data-stu-id="eefff-136">In this section, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="eefff-137">Com o Microsoft 365 Enterprise, é possível personalizar a aparência das páginas de entrada e do Painel de acesso para incluírem o logotipo da empresa, os esquemas de cores e as informações do usuário personalizadas.</span><span class="sxs-lookup"><span data-stu-id="eefff-137">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="eefff-138">Saiba mais em [Adicionar a marca da empresa na página de entrada do Office 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span><span class="sxs-lookup"><span data-stu-id="eefff-138">For more information, see [Add your company branding to Office 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="eefff-139">Confira as instruções de configuração em [Adicionar a marca da empresa na página de entrada e no Painel de acesso](http://aka.ms/aadpaddbranding).</span><span class="sxs-lookup"><span data-stu-id="eefff-139">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="eefff-140">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-custom-sign-in) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="eefff-140">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this section.</span></span>

## <a name="next-step"></a><span data-ttu-id="eefff-141">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="eefff-141">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)| [<span data-ttu-id="eefff-142">Proteger e gerenciar as entradas do seu usuário</span><span class="sxs-lookup"><span data-stu-id="eefff-142">Secure and manage your user sign-ins</span></span>](identity-secure-user-sign-ins.md) |
