---
title: Proteger o acesso de usuários e dispositivos
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
description: página de aterrissagem para proteger o acesso a dados e serviços do O365
ms.openlocfilehash: 9fc1691e7e36f994b5d0b8a6a9735fe8ccd8735a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073420"
---
# <a name="protect-user-and-device-access"></a><span data-ttu-id="fb7ad-103">Proteger o acesso de usuários e dispositivos</span><span class="sxs-lookup"><span data-stu-id="fb7ad-103">Protect user and device access</span></span>

<span data-ttu-id="fb7ad-104">Proteger o acesso aos dados e serviços do Office 365 é crucial para se defender contra o cyberattacks e a proteção contra a perda de dados.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-104">Protecting access to your Office 365 data and services is crucial to defending against cyberattacks and guarding against data loss.</span></span> <span data-ttu-id="fb7ad-105">As mesmas proteções podem ser aplicadas a outros aplicativos SaaS em seu ambiente e até mesmo para aplicativos locais publicados com o proxy de aplicativo do Active Directory do Azure.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-105">The same protections can be applied to other SaaS applications in your environment and even to on-premises applications published with Azure Active Directory Application Proxy.</span></span>
  
## <a name="step-1-review-recommendations"></a><span data-ttu-id="fb7ad-106">Etapa 1: analisar as recomendações</span><span class="sxs-lookup"><span data-stu-id="fb7ad-106">Step 1: Review recommendations</span></span>

<span data-ttu-id="fb7ad-107">Recursos recomendados para proteger identidades e dispositivos que acessam o Office 365, outros serviços SaaS e aplicativos locais publicados com o Proxy de Aplicativo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-107">Recommended capabilities for protecting identities and devices that access Office 365, other SaaS services, and on-premises applications published with Azure AD Application Proxy.</span></span>
  
<span data-ttu-id="fb7ad-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Mais idiomas](https://www.microsoft.com/download/details.aspx?id=55032)</span><span class="sxs-lookup"><span data-stu-id="fb7ad-108">[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [More languages](https://www.microsoft.com/download/details.aspx?id=55032)</span></span>
  
## <a name="step-2-protect-administrator-accounts-and-access"></a><span data-ttu-id="fb7ad-109">Etapa 2: proteger contas de administrador e acessar</span><span class="sxs-lookup"><span data-stu-id="fb7ad-109">Step 2: Protect administrator accounts and access</span></span>
<span data-ttu-id="fb7ad-110">As contas administrativas que você usa para administrar seu ambiente do Office 365 incluem privilégios elevados.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-110">The administrative accounts you use to administer your Office 365 environment include elevated privileges.</span></span> <span data-ttu-id="fb7ad-111">Estes são alvos valiosos para hackers e cyberattackers.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-111">These are valuable targets for hackers and cyberattackers.</span></span> 

<span data-ttu-id="fb7ad-112">Comece usando contas de administrador somente para administração.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-112">Begin by using administrator accounts only for administration.</span></span> <span data-ttu-id="fb7ad-113">Os administradores devem ter uma conta de usuário separada para uso regular e não administrativo e só usarem a conta administrativa, quando necessário, para concluir uma tarefa associada à função de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-113">Admins should have a separate user account for regular, non-administrative use and only use their administrative account when necessary to complete a task associated with their job function.</span></span>

<span data-ttu-id="fb7ad-114">Proteger suas contas de administrador com autenticação multifator e acesso condicional.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-114">Protect your administrator accounts with multi-factor authentication and conditional access.</span></span> <span data-ttu-id="fb7ad-115">Para obter mais informações, consulte [protegendo contas de administrador](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts).</span><span class="sxs-lookup"><span data-stu-id="fb7ad-115">For more information, see [Protecting administrator accounts](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts).</span></span> 

<span data-ttu-id="fb7ad-116">Em seguida, configure o gerenciamento de acesso privilegiado no Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-116">Next, configure privileged access management in Office 365.</span></span> <span data-ttu-id="fb7ad-117">O gerenciamento de acesso privilegiado permite o controle de acesso granular sobre tarefas administrativas privilegiadas no Office 365.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-117">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="fb7ad-118">Ele pode ajudar a proteger sua organização contra violações que podem usar contas de administrador privilegiadas existentes com acesso à dados confidenciais ou acesso a definições de configuração crítica.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-118">It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span>

- [<span data-ttu-id="fb7ad-119">Visão geral do gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="fb7ad-119">Overview of privileged access management</span></span>](privileged-access-management-overview.md)
- [<span data-ttu-id="fb7ad-120">Configurar gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="fb7ad-120">Configure privileged access management</span></span>](privileged-access-management-configuration.md)

<span data-ttu-id="fb7ad-121">Outra recomendação principal é usar as estações de trabalho especificamente configuradas para trabalhos administrativos.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-121">Another top recommendation is to use workstations specifically configured for administrative work.</span></span> <span data-ttu-id="fb7ad-122">Estes são dispositivos dedicados que são usados apenas para tarefas administrativas.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-122">These are dedicated devices that are only used for administrative tasks.</span></span> <span data-ttu-id="fb7ad-123">Consulte [protegendo o acesso privilegiado](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access).</span><span class="sxs-lookup"><span data-stu-id="fb7ad-123">See [Securing privileged access](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access).</span></span>

<span data-ttu-id="fb7ad-124">Por fim, você pode reduzir o impacto da falta inadvertida de acesso administrativo, criando duas ou mais contas de acesso de emergência em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-124">Finally, you can mitigate the impact of inadvertent lack of administrative access by creating two or more emergency access accounts in your tenant.</span></span> <span data-ttu-id="fb7ad-125">Consulte [gerenciar contas de acesso de emergência no Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span><span class="sxs-lookup"><span data-stu-id="fb7ad-125">See [Manage emergency access accounts in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access).</span></span> 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a><span data-ttu-id="fb7ad-126">Etapa 3: configurar as políticas recomendadas de acesso de dispositivo e identidades</span><span class="sxs-lookup"><span data-stu-id="fb7ad-126">Step 3: Configure recommended identity and device access policies</span></span>
<span data-ttu-id="fb7ad-127">A MFA (autenticação multifator) e as políticas de acesso condicional são ferramentas poderosas para reduzir as contas comprometidas e o acesso não autorizado.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-127">Multi-factor authentication (MFA) and conditional access policies are powerful tools for mitigating against compromised accounts and unauthorized access.</span></span> <span data-ttu-id="fb7ad-128">É recomendável implementar um conjunto de políticas que foram testadas juntas.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-128">We recommend implementing a set of policies that have been tested together.</span></span> <span data-ttu-id="fb7ad-129">Para obter mais informações, incluindo etapas de implantação, consulte [Identity and Device Access Configurations](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations).</span><span class="sxs-lookup"><span data-stu-id="fb7ad-129">For more information, including deployment steps, see [Identity and device access configurations](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations).</span></span>

 <span data-ttu-id="fb7ad-130">Essas políticas implementam os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="fb7ad-130">These policies implement the following capabilities:</span></span>
- <span data-ttu-id="fb7ad-131">Mediante-factor Authentication</span><span class="sxs-lookup"><span data-stu-id="fb7ad-131">Mult-factor authentication</span></span>
- <span data-ttu-id="fb7ad-132">Acesso condicional</span><span class="sxs-lookup"><span data-stu-id="fb7ad-132">Conditional access</span></span>
- <span data-ttu-id="fb7ad-133">Proteção de aplicativos do Intune (proteção de aplicativos e dados para dispositivos)</span><span class="sxs-lookup"><span data-stu-id="fb7ad-133">Intune app protection (app and data protection for devices)</span></span>
- <span data-ttu-id="fb7ad-134">Conformidade de dispositivo do Intune</span><span class="sxs-lookup"><span data-stu-id="fb7ad-134">Intune device compliance</span></span>
- <span data-ttu-id="fb7ad-135">Azure AD Identity Protection</span><span class="sxs-lookup"><span data-stu-id="fb7ad-135">Azure AD Identity Protection</span></span>

<span data-ttu-id="fb7ad-136">A implementação da conformidade do dispositivo do Intune requer o registro do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-136">Implementing Intune device compliance requires device enrollment.</span></span> <span data-ttu-id="fb7ad-137">O gerenciamento de dispositivos permite que você verifique se eles estão íntegros e em conformidade antes de permitir o acesso aos recursos em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-137">Managing devices allows you to ensure that they are healthy and compliant before allowing them access to resources in your environment.</span></span> <span data-ttu-id="fb7ad-138">Consulte [registrar dispositivos para gerenciamento no Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="fb7ad-138">See [Enroll devices for management in Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)</span></span>

## <a name="step-4-configure-sharepoint-device-access-policies"></a><span data-ttu-id="fb7ad-139">Etapa 4: configurar as políticas de acesso do dispositivo do SharePoint</span><span class="sxs-lookup"><span data-stu-id="fb7ad-139">Step 4: Configure SharePoint device access policies</span></span>

<span data-ttu-id="fb7ad-140">A Microsoft recomenda que você proteja o conteúdo em sites do SharePoint com conteúdo confidencial e altamente regulamentado com controles de acesso do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="fb7ad-140">Microsoft recommends you protect content in SharePoint sites with sensitive and highly-regulated content with device access controls.</span></span> <span data-ttu-id="fb7ad-141">Para mais informações, consulte [recomendações de política para proteger sites e arquivos do SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span><span class="sxs-lookup"><span data-stu-id="fb7ad-141">For more information, see [Policy recommendations for securing SharePoint sites and files](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).</span></span>



    

