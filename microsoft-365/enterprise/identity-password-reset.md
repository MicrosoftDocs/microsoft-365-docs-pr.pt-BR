---
title: 'Etapa 5: Simplificar o acesso para usuários'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda e configure a redefinição de senha de autoatendimento (SSPR) do Azure Active Directory.
ms.openlocfilehash: 98118a5891ea8224843faa638b52a421d96e8a0b
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287042"
---
# <a name="step-5-simplify-access-for-users"></a><span data-ttu-id="2eb0e-103">Etapa 5: Simplificar o acesso para usuários</span><span class="sxs-lookup"><span data-stu-id="2eb0e-103">Step 5: Simplify access for users</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a><span data-ttu-id="2eb0e-104">Simplificar as atualizações de senha</span><span class="sxs-lookup"><span data-stu-id="2eb0e-104">Simplify password updates</span></span>

<span data-ttu-id="2eb0e-105">*Isso é opcional para ambientes híbridos e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="2eb0e-105">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="2eb0e-106">Nesta seção, você permitirá que os usuários redefinam suas senhas através do Azure Active Directory (Azure AD) que depois é replicada para os seus serviços locais de domínio do Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="2eb0e-106">In this section, you'll allow users to reset their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="2eb0e-107">Este processo é conhecido como write-back de senha.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-107">This process is known as password writeback.</span></span> <span data-ttu-id="2eb0e-108">Com o write-back de senha, os usuários não precisam atualizar suas senhas através dos serviços locais de domínio do Active Directory (AD DS), onde as contas de usuário e seus atributos são armazenados.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-108">With password writeback, users don’t need to update their passwords through the on-premises Active Directory Domain Services (AD DS) where user accounts and their attributes are stored.</span></span> <span data-ttu-id="2eb0e-109">Isso é valioso para usuários móveis ou remotos que não têm uma conexão de acesso remoto à rede local.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-109">This is valuable to roaming or remote users who do not have a remote access connection to the on-premises network.</span></span>

<span data-ttu-id="2eb0e-110">O write-back de senha é necessário para utilizar completamente as capacidades de recursos de Proteção de Identidade, por exemplo para exigir que os usuários alterem a senha local quando for detectado um alto risco de comprometimento da conta.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-110">Password writeback is required to fully utilize Identity Protection feature capabilities, such as requiring users to change their on-premises passwords when there has been a high risk of account compromise detected.</span></span>

<span data-ttu-id="2eb0e-111">Para obter mais informações e instruções de configuração, consulte o artigo sobre o [Azure AD SSPR com o write-back de senha](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span><span class="sxs-lookup"><span data-stu-id="2eb0e-111">For additional information and configuration instructions, see [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback).</span></span>

>[!Note]
><span data-ttu-id="2eb0e-p102">Atualize para a versão mais recente do Azure AD Connect a fim de garantir a melhor experiência possível e o acesso a novos recursos à medida que são lançados. Para saber mais, consulte as informações sobre a [instalação personalizada do Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span><span class="sxs-lookup"><span data-stu-id="2eb0e-p102">Upgrade to the latest version of Azure AD Connect to ensure the best possible experience and new features as they are released. For more information, see [Custom installation of Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom).</span></span>
>

|||
|:-------|:-----|
|![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="2eb0e-115">Guia de laboratório de teste: write-back de senha</span><span class="sxs-lookup"><span data-stu-id="2eb0e-115">Test Lab Guide: Password reset</span></span>](password-writeback-m365-ent-test-environment.md) |
|||

<span data-ttu-id="2eb0e-116">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-pw-writeback) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-116">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-writeback) for this step.</span></span>

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a><span data-ttu-id="2eb0e-117">Simplificar as redefinições de senha</span><span class="sxs-lookup"><span data-stu-id="2eb0e-117">Simplify password resets</span></span>

<span data-ttu-id="2eb0e-118">*Isso é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="2eb0e-118">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="2eb0e-119">Nesta seção, você habilitará a redefinição de senha de autoatendimento (SSPR) para permitir que usuários redefinam ou desbloqueiem suas senhas ou contas.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-119">In this section, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts.</span></span> <span data-ttu-id="2eb0e-120">Para ser alertado sobre uso indevido ou abuso, você pode usar os relatórios detalhados que rastreiam quando usuários acessam o sistema, junto com as notificações.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-120">In this step, you'll enable self-service password reset (SSPR) to allow users to reset or unlock their passwords or accounts. To alert you to misuse or abuse, you can use the detailed reporting that tracks when users access the system, along with notifications.</span></span> <span data-ttu-id="2eb0e-121">Você deve habilitar o write-back de senha antes que possa implantar as redefinições de senha.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-121">You must enable password writeback before you can deploy password resets.</span></span>

<span data-ttu-id="2eb0e-122">Confira as[instruções para implantar redefinição de senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span><span class="sxs-lookup"><span data-stu-id="2eb0e-122">See the [instructions to enable password reset](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).</span></span>

|||
|:-------|:-----|
|![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="2eb0e-124">Guia de laboratório de teste: redefinição de senha</span><span class="sxs-lookup"><span data-stu-id="2eb0e-124">Test Lab Guide: Password reset</span></span>](password-reset-m365-ent-test-environment.md) |
|||

<span data-ttu-id="2eb0e-125">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-pw-reset) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-125">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pw-reset) for this step.</span></span>


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a><span data-ttu-id="2eb0e-126">Simplificar a entrada do usuário</span><span class="sxs-lookup"><span data-stu-id="2eb0e-126">Simplify user sign-in</span></span>

<span data-ttu-id="2eb0e-127">*Isso é opcional para ambientes híbridos e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="2eb0e-127">*This step is optional for hybrid environments and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="2eb0e-128">Nesta seção, você vai configurar o Logon Único Contínuo do Azure Active Directory (Azure AD Seamless SSO) para permitir que seus usuários entrem nos serviços que usam as contas de usuário do Azure AD sem precisar digitar suas senhas e em muitos casos, seus nomes de usuário.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-128">In this step, you'll set up Azure Active Directory Seamless Single Sign-On (Azure AD Seamless SSO) to allow your users to sign in to services that use Azure AD user accounts without having to type in their passwords, and in many cases, their usernames. This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span> <span data-ttu-id="2eb0e-129">Isso facilita o acesso de seus usuários a aplicativos baseados na nuvem, como o Office 365, sem precisar de nenhum componente adicional local, como servidores de federação de identidades.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-129">This gives your users easier access to cloud-based applications, such as Office 365, without needing any additional on-premises components such as identity federation servers.</span></span>

<span data-ttu-id="2eb0e-130">Você configurará o SSO Contínuo do Azure Active Directory com a ferramenta Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-130">You'll configure Azure AD Seamless SSO with the Azure AD Connect tool.</span></span>

<span data-ttu-id="2eb0e-131">Confira as [instruções para configurar o SSO Contínuo do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span><span class="sxs-lookup"><span data-stu-id="2eb0e-131">See the [instructions to configure Azure AD Seamless SSO](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).</span></span>

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="2eb0e-133">Guia do Laboratório de Teste: Logon Único Contínuo do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="2eb0e-133">Test Lab Guide: Azure AD Seamless Single Sign-on</span></span>](single-sign-on-m365-ent-test-environment.md) |
|||

<span data-ttu-id="2eb0e-134">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-sso) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-134">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-sso) for this step.</span></span>


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a><span data-ttu-id="2eb0e-135">Personalizar páginas de entrada do Office 365</span><span class="sxs-lookup"><span data-stu-id="2eb0e-135">Customize the Office 365 sign-in page</span></span>

<span data-ttu-id="2eb0e-136">*Isso é opcional e para as versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="2eb0e-136">*This step is optional and for both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="2eb0e-137">Nesta seção, você ajudará usuários a reconhecer a página de entrada da sua organização ao adicionar o nome, o logotipo da sua empresa e outros elementos reconhecíveis.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-137">In this step, you'll help users recognize your organization’s sign-in page by adding your company name, logo, and other recognizable elements.</span></span> 

<span data-ttu-id="2eb0e-138">Com o Microsoft 365 Enterprise, é possível personalizar a aparência das páginas de entrada e do Painel de acesso para incluírem o logotipo da empresa, os esquemas de cores e as informações do usuário personalizadas.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-138">With Microsoft 365 Enterprise, you can customize the appearance of the sign-in and Access Panel pages so they include your company logo, color schemes, and custom user information.</span></span> 

<span data-ttu-id="2eb0e-139">Quando um usuário tenta fazer logon por um dispositivo, ele vê algo parecido com o exemplo a seguir na página de entrada do Office 365 *antes da personalização*.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-139">When a user attempts to sign in from a device, they see something like the following example on the Office 365 sign-in page *before customization*.</span></span>

![Exemplo da página de entrada do Office 365 antes da personalização](./media/identity-customize-office-365-sign-in/id-step01-sign-in-before.png)

<span data-ttu-id="2eb0e-141">Aqui está o que o mesmo usuário da Contoso Corporation veria *após a personalização*.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-141">And here is what the same user of the Contoso Corporation would see *after customization*.</span></span>

![Exemplo da página de entrada do Office 365 depois da personalização](./media/identity-customize-office-365-sign-in/id-step01-sign-in-after.png)

<span data-ttu-id="2eb0e-143">Saiba mais em [Adicionar a marca da empresa na página de entrada do Office 365](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span><span class="sxs-lookup"><span data-stu-id="2eb0e-143">For more information, see [Add your company branding to Office 365 Sign In page](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page).</span></span>

<span data-ttu-id="2eb0e-144">Confira as instruções de configuração em [Adicionar a marca da empresa na página de entrada e no Painel de acesso](http://aka.ms/aadpaddbranding).</span><span class="sxs-lookup"><span data-stu-id="2eb0e-144">For configuration instructions, see [Add company branding to your sign-in and Access Panel pages](http://aka.ms/aadpaddbranding).</span></span>

<span data-ttu-id="2eb0e-145">Como um ponto de verificação provisório, você pode ver os [critérios de saída](identity-exit-criteria.md#crit-identity-custom-sign-in) para esta seção.</span><span class="sxs-lookup"><span data-stu-id="2eb0e-145">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-custom-sign-in) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="2eb0e-146">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="2eb0e-146">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [<span data-ttu-id="2eb0e-147">Usar grupos para facilitar o gerenciamento</span><span class="sxs-lookup"><span data-stu-id="2eb0e-147">Use groups for easier management</span></span>](identity-self-service-group-management.md) |


