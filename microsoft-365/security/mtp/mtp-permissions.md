---
title: Gerenciar o acesso aos dados do Microsoft 365 Defender no centro de segurança do Microsoft 365
description: Saiba como gerenciar permissões para dados no Microsoft 365 Defender
keywords: acesso, permissões, MTP, Proteção contra Ameaças da Microsoft, M365, segurança, MCAS, MDATP, Cloud App Security, Proteção Avançada contra Ameaças do Microsoft Defender, escopo, gerar escopo, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: a619a6ff5256b3b70302d1bef4f0bc21bd7ac3e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927901"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a><span data-ttu-id="ff065-104">Gerenciar o acesso ao Microsoft 365 Defender com funções globais do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ff065-104">Manage access to Microsoft 365 Defender with Azure Active Directory global roles</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ff065-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ff065-105">**Applies to:**</span></span>
- <span data-ttu-id="ff065-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff065-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ff065-107">Há duas maneiras de gerenciar o acesso ao Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff065-107">There are two ways to manage access to Microsoft 365 Defender</span></span>
- <span data-ttu-id="ff065-108">**Funções do Azure Active Directory Global (AD)**</span><span class="sxs-lookup"><span data-stu-id="ff065-108">**Global Azure Active Directory (AD) roles**</span></span>
- <span data-ttu-id="ff065-109">**Acesso de função personalizado**</span><span class="sxs-lookup"><span data-stu-id="ff065-109">**Custom role access**</span></span>

<span data-ttu-id="ff065-110">As contas atribuídas às seguintes **funções do Azure Active Directory (AD)** globais podem acessar a funcionalidade e os dados do Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="ff065-110">Accounts assigned the following **Global Azure Active Directory (AD) roles** can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="ff065-111">Administrador global</span><span class="sxs-lookup"><span data-stu-id="ff065-111">Global administrator</span></span>
- <span data-ttu-id="ff065-112">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="ff065-112">Security administrator</span></span>
- <span data-ttu-id="ff065-113">Operador de segurança</span><span class="sxs-lookup"><span data-stu-id="ff065-113">Security Operator</span></span>
- <span data-ttu-id="ff065-114">Leitor global</span><span class="sxs-lookup"><span data-stu-id="ff065-114">Global Reader</span></span>
- <span data-ttu-id="ff065-115">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="ff065-115">Security Reader</span></span>

<span data-ttu-id="ff065-116">Para revisar as contas com essas funções, [exiba as Permissões no centro de segurança do Microsoft 365](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="ff065-116">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

<span data-ttu-id="ff065-117">**O acesso** à função personalizada é um novo recurso no Microsoft 365 Defender e permite gerenciar o acesso a dados, tarefas e recursos específicos no Microsoft Defender 365.</span><span class="sxs-lookup"><span data-stu-id="ff065-117">**Custom role** access is a new capability in Microsoft 365 Defender and allows you to manage access to specific data, tasks, and capabilities in Microsoft Defender 365.</span></span> <span data-ttu-id="ff065-118">Funções personalizadas oferecem mais controle do que funções globais do Azure AD, fornecendo aos usuários apenas o acesso de que precisam com as funções menos permissivas necessárias.</span><span class="sxs-lookup"><span data-stu-id="ff065-118">Custom roles offer more control than global Azure AD roles, providing users only the access they need with the least-permissive roles necessary.</span></span>  <span data-ttu-id="ff065-119">Funções personalizadas podem ser criadas além de funções globais do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ff065-119">Custom roles can be created in addition to global Azure AD roles.</span></span> <span data-ttu-id="ff065-120">[Saiba mais sobre funções personalizadas.](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="ff065-120">[Learn more about custom roles](custom-roles.md).</span></span>

> <span data-ttu-id="ff065-121">! [OBSERVAÇÃO] Este artigo se aplica apenas ao gerenciamento de funções globais do Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ff065-121">![NOTE] This article applies only to managing global Azure Active Directory roles.</span></span> <span data-ttu-id="ff065-122">Para obter mais informações sobre como usar o controle de acesso baseado em função personalizado, consulte [Funções personalizadas para controle de](custom-roles.md) acesso baseado em função</span><span class="sxs-lookup"><span data-stu-id="ff065-122">For more information about using custom role-based access control, see [Custom roles for role-based access control](custom-roles.md)</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="ff065-123">Acesso à funcionalidade</span><span class="sxs-lookup"><span data-stu-id="ff065-123">Access to functionality</span></span>
<span data-ttu-id="ff065-124">O acesso a uma funcionalidade específica é determinado pela sua [função do Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="ff065-124">Access to specific functionality is determined by your [Azure AD role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="ff065-125">Entre em contato com um administrador global caso precise de acesso a uma funcionalidade específica que exija que você ou seu grupo de usuários tenham uma nova função.</span><span class="sxs-lookup"><span data-stu-id="ff065-125">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="ff065-126">Aprovação de tarefas automatizadas pendentes</span><span class="sxs-lookup"><span data-stu-id="ff065-126">Approve pending automated tasks</span></span>
<span data-ttu-id="ff065-127">[A investigação e a correção automáticas](mtp-autoir-actions.md) podem executar ações em emails, regras de encaminhamento, arquivos, mecanismos de persistência e outros artefatos encontrados durante investigações.</span><span class="sxs-lookup"><span data-stu-id="ff065-127">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="ff065-128">Para aprovar ou rejeitar ações pendentes que exijam aprovação explícita, você deve ter determinadas funções atribuídas no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ff065-128">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="ff065-129">Para saber mais, confira [Permissões da central de ações](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="ff065-129">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="ff065-130">Acesso a dados</span><span class="sxs-lookup"><span data-stu-id="ff065-130">Access to data</span></span>
<span data-ttu-id="ff065-131">O acesso aos dados do Microsoft 365 Defender pode ser controlado usando o escopo atribuído a grupos de usuários no Microsoft Defender para controle de acesso baseado em função de ponto de extremidade (RBAC).</span><span class="sxs-lookup"><span data-stu-id="ff065-131">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="ff065-132">Se seu acesso não tiver sido limitado a um conjunto específico de dispositivos no Defender para Ponto de Extremidade, você terá acesso total aos dados no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ff065-132">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="ff065-133">No entanto, depois que sua conta tiver um escopo, você só verá os dados dos dispositivos dentro do seu escopo.</span><span class="sxs-lookup"><span data-stu-id="ff065-133">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="ff065-134">Por exemplo, se você pertencer a apenas um grupo de usuários com uma função do Microsoft Defender para Ponto de Extremidade e esse grupo de usuários tiver acesso apenas a dispositivos de vendas, você verá apenas dados sobre dispositivos de vendas no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="ff065-134">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="ff065-135">Saiba mais sobre as configurações do RBAC no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ff065-135">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="ff065-136">Controles de acesso ao Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ff065-136">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="ff065-137">Durante a visualização, o Microsoft 365 Defender não impõe controles de acesso com base nas configurações de Segurança do Aplicativo na Nuvem.</span><span class="sxs-lookup"><span data-stu-id="ff065-137">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="ff065-138">O acesso aos dados do Microsoft 365 Defender não é afetado por essas configurações.</span><span class="sxs-lookup"><span data-stu-id="ff065-138">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ff065-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ff065-139">Related topics</span></span>
- [<span data-ttu-id="ff065-140">Funções personalizadas no controle de acesso baseado em função para o Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ff065-140">Custom roles in role-based access control for Microsoft 365 Defender</span></span>](custom-roles.md)
- [<span data-ttu-id="ff065-141">Funções do Microsoft Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="ff065-141">Azure AD roles</span></span>](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="ff065-142">Microsoft Defender para Endpoint RBAC</span><span class="sxs-lookup"><span data-stu-id="ff065-142">Microsoft Defender for Endpoint RBAC</span></span>](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="ff065-143">Funções do Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ff065-143">Cloud App Security roles</span></span>](/cloud-app-security/manage-admins)