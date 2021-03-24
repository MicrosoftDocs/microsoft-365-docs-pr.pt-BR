---
title: Proteger acesso de usuário e de dispositivo
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Saiba como proteger o acesso de usuários e dispositivos aos dados e serviços do Microsoft 365 e se defender contra a perda de dados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ff7bd2ff8b4b333eb30a6cc82797a8968941e0b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051693"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="3a6f9-103">Proteger acesso de usuário e de dispositivo</span><span class="sxs-lookup"><span data-stu-id="3a6f9-103">Protect user and device access</span></span>

<span data-ttu-id="3a6f9-104">Proteger o acesso aos seus dados e serviços do Microsoft 365 é fundamental para se defender contra ataques cibernéticos e proteger contra a perda de dados.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-104">Protecting access to your Microsoft 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="3a6f9-105">As mesmas proteções podem ser aplicadas a outros aplicativos SaaS em seu ambiente e até mesmo a aplicativos locais publicados com o Proxy de Aplicativo do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="3a6f9-106">Etapa 1: Revisar recomendações</span><span class="sxs-lookup"><span data-stu-id="3a6f9-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="3a6f9-107">Recursos recomendados para proteger identidades e dispositivos que acessam o Office 365, outros serviços SaaS e aplicativos locais publicados com o Proxy de Aplicativo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="3a6f9-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Mais idiomas](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="3a6f9-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="3a6f9-109">Etapa 2: proteger contas de administrador e acesso</span><span class="sxs-lookup"><span data-stu-id="3a6f9-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="3a6f9-110">As contas administrativas que você usa para administrar seu ambiente do Microsoft 365 incluem privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-110">The administrative accounts you use to administer your Microsoft 365 environment include elevated privileges.</span></span> <span data-ttu-id="3a6f9-111">Esses são alvos valiosos para hackers e cyberattackers.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="3a6f9-112">Comece usando contas de administrador somente para administração.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="3a6f9-113">Os administradores devem ter uma conta de usuário separada para uso regular e não administrativo e usar somente sua conta administrativa quando necessário para concluir uma tarefa associada à função de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="3a6f9-114">Proteja suas contas de administrador com autenticação multifacional e acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="3a6f9-115">Para obter mais informações, consulte [Protegendo contas de administrador.](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts)</span><span class="sxs-lookup"><span data-stu-id="3a6f9-115">For more information, see [Protecting administrator accounts](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="3a6f9-116">Em seguida, configure o gerenciamento de acesso privilegiado no Office 365.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="3a6f9-117">O gerenciamento de acesso privilegiado permite o controle de acesso granular sobre tarefas de administrador privilegiadas no Office 365.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="3a6f9-118">Ele pode ajudar a proteger sua organização contra violações que podem usar contas de administrador privilegiadas existentes com acesso permanente a dados confidenciais ou acesso a configurações críticas.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="3a6f9-119">Visão geral do gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="3a6f9-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="3a6f9-120">Configurar gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="3a6f9-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="3a6f9-121">Outra recomendação principal é usar estações de trabalho configuradas especificamente para o trabalho administrativo.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="3a6f9-122">Esses são dispositivos dedicados que são usados apenas para tarefas administrativas.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="3a6f9-123">Consulte [Proteger o acesso privilegiado](/windows-server/identity/securing-privileged-access/securing-privileged-access).</span><span class="sxs-lookup"><span data-stu-id="3a6f9-123">See [Securing privileged access](/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="3a6f9-124">Por fim, você pode reduzir o impacto da falta de acesso administrativo inadvertida criando duas ou mais contas de acesso de emergência em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="3a6f9-125">Consulte [Gerenciar contas de acesso de emergência no Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="3a6f9-125">See [Manage emergency access accounts in Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="3a6f9-126">Etapa 3: Configurar políticas recomendadas de acesso a dispositivos e identidades</span><span class="sxs-lookup"><span data-stu-id="3a6f9-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="3a6f9-127">A autenticação multifacional (MFA) e as políticas de acesso condicional são ferramentas poderosas para atenuar contra contas comprometidas e acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="3a6f9-128">Recomendamos a implementação de um conjunto de políticas que foram testadas juntas.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="3a6f9-129">Para obter mais informações, incluindo etapas de implantação, consulte [Configurações de acesso a dispositivos](../security/defender-365-security/microsoft-365-policies-configurations.md)e identidade.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-129">For more information, including deployment steps, see [Identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md).</span></span>

 <span data-ttu-id="3a6f9-130">Essas políticas implementam os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="3a6f9-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="3a6f9-131">Autenticação de fator mult</span><span class="sxs-lookup"><span data-stu-id="3a6f9-131">Mult-factor authentication</span></span>
- <span data-ttu-id="3a6f9-132">Acesso condicional</span><span class="sxs-lookup"><span data-stu-id="3a6f9-132">Conditional access</span></span>
- <span data-ttu-id="3a6f9-133">Proteção de aplicativos do Intune (proteção de aplicativos e dados para dispositivos)</span><span class="sxs-lookup"><span data-stu-id="3a6f9-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="3a6f9-134">Conformidade de dispositivos com o Intune</span><span class="sxs-lookup"><span data-stu-id="3a6f9-134">Intune device compliance</span></span>
- <span data-ttu-id="3a6f9-135">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="3a6f9-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="3a6f9-136">Implementar a conformidade de dispositivos do Intune exige o registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="3a6f9-137">Gerenciar dispositivos permite garantir que eles sejam saudáveis e compatíveis antes de permitir que eles acessem recursos em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="3a6f9-138">Consulte [Registrar dispositivos para gerenciamento no Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="3a6f9-138">See [Enroll devices for management in Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="3a6f9-139">Etapa 4: Configurar políticas de acesso a dispositivos do SharePoint</span><span class="sxs-lookup"><span data-stu-id="3a6f9-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="3a6f9-140">A Microsoft recomenda que você proteja o conteúdo em sites do SharePoint com conteúdo altamente regulamentado e confidenciais com controles de acesso ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3a6f9-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="3a6f9-141">Para obter mais informações, consulte [Recomendações de política para proteger sites e arquivos do SharePoint.](../security/defender-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="3a6f9-141">For more information, see [Policy recommendations for securing SharePoint sites and files](../security/defender-365-security/sharepoint-file-access-policies.md).</span></span>



