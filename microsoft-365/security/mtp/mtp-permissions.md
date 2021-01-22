---
title: Gerenciar o acesso aos dados do Microsoft 365 Defender na central de segurança do Microsoft 365
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
ms.openlocfilehash: 6f042b0c6314e8e5f80d40d76159712bc817a01c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930133"
---
# <a name="manage-access-to-microsoft-365-defender"></a><span data-ttu-id="6adbc-104">Gerenciar o acesso ao Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6adbc-104">Manage access to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6adbc-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6adbc-105">**Applies to:**</span></span>
- <span data-ttu-id="6adbc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6adbc-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6adbc-107">As contas atribuídas às seguintes funções do Azure Active Directory (AD) podem acessar a funcionalidade e os dados do Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="6adbc-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="6adbc-108">Administrador global</span><span class="sxs-lookup"><span data-stu-id="6adbc-108">Global administrator</span></span>
- <span data-ttu-id="6adbc-109">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="6adbc-109">Security administrator</span></span>
- <span data-ttu-id="6adbc-110">Operador de segurança</span><span class="sxs-lookup"><span data-stu-id="6adbc-110">Security Operator</span></span>
- <span data-ttu-id="6adbc-111">Leitor global</span><span class="sxs-lookup"><span data-stu-id="6adbc-111">Global Reader</span></span>
- <span data-ttu-id="6adbc-112">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="6adbc-112">Security Reader</span></span>

<span data-ttu-id="6adbc-113">Para revisar as contas com essas funções, [exiba as Permissões no centro de segurança do Microsoft 365](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="6adbc-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="6adbc-114">Acesso à funcionalidade</span><span class="sxs-lookup"><span data-stu-id="6adbc-114">Access to functionality</span></span>
<span data-ttu-id="6adbc-115">O acesso a uma funcionalidade específica é determinado pela sua [função do Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="6adbc-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="6adbc-116">Entre em contato com um administrador global caso precise de acesso a uma funcionalidade específica que exija que você ou seu grupo de usuários tenham uma nova função.</span><span class="sxs-lookup"><span data-stu-id="6adbc-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="6adbc-117">Aprovação de tarefas automatizadas pendentes</span><span class="sxs-lookup"><span data-stu-id="6adbc-117">Approve pending automated tasks</span></span>
<span data-ttu-id="6adbc-118">[A investigação e a correção automáticas](mtp-autoir-actions.md) podem executar ações em emails, regras de encaminhamento, arquivos, mecanismos de persistência e outros artefatos encontrados durante investigações.</span><span class="sxs-lookup"><span data-stu-id="6adbc-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="6adbc-119">Para aprovar ou rejeitar ações pendentes que exijam aprovação explícita, você deve ter determinadas funções atribuídas no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6adbc-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="6adbc-120">Para saber mais, confira [Permissões da central de ações](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="6adbc-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="6adbc-121">Acesso a dados</span><span class="sxs-lookup"><span data-stu-id="6adbc-121">Access to data</span></span>
<span data-ttu-id="6adbc-122">O acesso aos dados do Microsoft 365 Defender pode ser controlado usando o escopo atribuído a grupos de usuários no Microsoft Defender para RBAC (controle de acesso baseado em função) do Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="6adbc-122">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="6adbc-123">Se o acesso não tiver sido definido para um conjunto específico de dispositivos no Defender para Ponto de Extremidade, você terá acesso total aos dados no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6adbc-123">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="6adbc-124">No entanto, depois que sua conta tiver um escopo, você só verá os dados dos dispositivos dentro do seu escopo.</span><span class="sxs-lookup"><span data-stu-id="6adbc-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="6adbc-125">Por exemplo, se você pertencer a apenas um grupo de usuários com uma função Microsoft Defender para Ponto de Extremidade e esse grupo de usuários tiver acesso somente a dispositivos de vendas, você verá apenas dados sobre dispositivos de vendas no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="6adbc-125">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="6adbc-126">Saiba mais sobre as configurações de RBAC no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6adbc-126">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="6adbc-127">Controles de acesso ao Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6adbc-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="6adbc-128">Durante a visualização, o Microsoft 365 Defender não impõe controles de acesso com base nas configurações do Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="6adbc-128">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="6adbc-129">O acesso aos dados do Microsoft 365 Defender não é afetado por essas configurações.</span><span class="sxs-lookup"><span data-stu-id="6adbc-129">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6adbc-130">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6adbc-130">Related topics</span></span>

- [<span data-ttu-id="6adbc-131">Funções do Azure AD</span><span class="sxs-lookup"><span data-stu-id="6adbc-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="6adbc-132">Microsoft Defender for Endpoint RBAC</span><span class="sxs-lookup"><span data-stu-id="6adbc-132">Microsoft Defender for Endpoint RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="6adbc-133">Funções do Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6adbc-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
