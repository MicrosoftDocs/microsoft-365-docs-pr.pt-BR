---
title: Gerenciar o acesso aos dados da Proteção contra Ameaças da Microsoft no centro de segurança do Microsoft 365
description: Saiba como gerenciar permissões aos dados da Proteção contra Ameaças da Microsoft
keywords: acesso, permissões, MTP, Proteção contra Ameaças da Microsoft, M365, segurança, MCAS, MDATP, Cloud App Security, Proteção Avançada contra Ameaças do Microsoft Defender, escopo, gerar escopo, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: ca9d6320d7ba13b2af4200e5f270c9480d8336fd
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808566"
---
# <a name="manage-access-to-microsoft-threat-protection"></a><span data-ttu-id="5deb4-104">Gerenciar o acesso à Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="5deb4-104">Manage access to Microsoft Threat Protection</span></span>

<span data-ttu-id="5deb4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5deb4-105">**Applies to:**</span></span>
- <span data-ttu-id="5deb4-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="5deb4-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="5deb4-107">Contas atribuídas às seguintes funções do Azure Active Directory (AD) podem acessar a funcionalidade e os dados da Proteção contra Ameaças da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="5deb4-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft Threat Protection functionality and data:</span></span>
- <span data-ttu-id="5deb4-108">Administrador global</span><span class="sxs-lookup"><span data-stu-id="5deb4-108">Global administrator</span></span>
- <span data-ttu-id="5deb4-109">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="5deb4-109">Security administrator</span></span>
- <span data-ttu-id="5deb4-110">Operador de segurança</span><span class="sxs-lookup"><span data-stu-id="5deb4-110">Security Operator</span></span>
- <span data-ttu-id="5deb4-111">Leitor global</span><span class="sxs-lookup"><span data-stu-id="5deb4-111">Global Reader</span></span>
- <span data-ttu-id="5deb4-112">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="5deb4-112">Security Reader</span></span>

<span data-ttu-id="5deb4-113">Para revisar as contas com essas funções, [exiba as Permissões no centro de segurança do Microsoft 365](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="5deb4-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="5deb4-114">Acesso à funcionalidade</span><span class="sxs-lookup"><span data-stu-id="5deb4-114">Access to functionality</span></span>
<span data-ttu-id="5deb4-115">O acesso a uma funcionalidade específica é determinado pela sua [função do Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="5deb4-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="5deb4-116">Entre em contato com um administrador global caso precise de acesso a uma funcionalidade específica que exija que você ou seu grupo de usuários tenham uma nova função.</span><span class="sxs-lookup"><span data-stu-id="5deb4-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="5deb4-117">Aprovação de tarefas automatizadas pendentes</span><span class="sxs-lookup"><span data-stu-id="5deb4-117">Approve pending automated tasks</span></span>
<span data-ttu-id="5deb4-118">[A investigação e a correção automáticas](mtp-autoir-actions.md) podem executar ações em emails, regras de encaminhamento, arquivos, mecanismos de persistência e outros artefatos encontrados durante investigações.</span><span class="sxs-lookup"><span data-stu-id="5deb4-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="5deb4-119">Para aprovar ou rejeitar ações pendentes que exijam aprovação explícita, você deve ter determinadas funções atribuídas no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5deb4-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="5deb4-120">Para saber mais, confira [Permissões da central de ações](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="5deb4-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="5deb4-121">Acesso a dados</span><span class="sxs-lookup"><span data-stu-id="5deb4-121">Access to data</span></span>
<span data-ttu-id="5deb4-122">O acesso aos dados da Proteção contra Ameaças da Microsoft pode ser controlado usando o escopo atribuído aos grupos de usuários no RBAC (controle de acesso baseado em função) do Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="5deb4-122">Access to Microsoft Threat Protection data can be controlled using the scope assigned to user groups in Microsoft Defender ATP role-based access control (RBAC).</span></span> <span data-ttu-id="5deb4-123">Caso seu acesso não tenha sido delimitado a um conjunto específico de dispositivos no Microsoft Defender ATP, você terá acesso total aos dados de Proteção contra Ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5deb4-123">If your access has not been scoped to a specific set of devices in the Microsoft Defender ATP, you will have full access to data in Microsoft Threat Protection.</span></span> <span data-ttu-id="5deb4-124">No entanto, depois que sua conta tiver um escopo, você só verá os dados dos dispositivos dentro do seu escopo.</span><span class="sxs-lookup"><span data-stu-id="5deb4-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="5deb4-125">Por exemplo, caso você pertença a apenas um grupo de usuários com uma função do Microsoft Defender ATP e esse grupo tenha acesso apenas a dispositivos de vendas, você só verá dados sobre esse tipos de dispositivo na Proteção contra Ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5deb4-125">For example, if you belong to only one user group with a Microsoft Defender ATP role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft Threat Protection.</span></span> [<span data-ttu-id="5deb4-126">Saiba mais sobre as configurações de RBAC do Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="5deb4-126">Learn more about RBAC settings in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="5deb4-127">Controles de acesso ao Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5deb4-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="5deb4-128">Durante a visualização, a Proteção contra Ameaças da Microsoft não impõe controles de acesso com base nas configurações do Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="5deb4-128">During the preview, Microsoft Threat Protection does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="5deb4-129">Os dados de Proteção contra Ameaças da Microsoft não são afetados por essas configurações.</span><span class="sxs-lookup"><span data-stu-id="5deb4-129">Access to Microsoft Threat Protection data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5deb4-130">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5deb4-130">Related topics</span></span>

- [<span data-ttu-id="5deb4-131">Funções do Azure AD</span><span class="sxs-lookup"><span data-stu-id="5deb4-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="5deb4-132">RBAC do Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="5deb4-132">Microsoft Defender ATP RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="5deb4-133">Funções do Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5deb4-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)