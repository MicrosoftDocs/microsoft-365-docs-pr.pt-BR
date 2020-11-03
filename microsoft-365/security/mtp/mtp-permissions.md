---
title: Gerenciar o acesso aos dados do Microsoft 365 defender no centro de segurança do Microsoft 365
description: Saiba como gerenciar permissões para dados no Microsoft 365 defender
keywords: acesso, permissões, MTP, Proteção contra Ameaças da Microsoft, M365, segurança, MCAS, MDATP, Cloud App Security, Proteção Avançada contra Ameaças do Microsoft Defender, escopo, gerar escopo, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 55b7b8c5755b773a4d53c95017a0a17a85495dee
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847243"
---
# <a name="manage-access-to-microsoft-365-defender"></a><span data-ttu-id="bf531-104">Gerenciar o acesso ao Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="bf531-104">Manage access to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bf531-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="bf531-105">**Applies to:**</span></span>
- <span data-ttu-id="bf531-106">Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="bf531-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="bf531-107">As contas atribuídas às seguintes funções do Azure Active Directory (AD) podem acessar a funcionalidade e os dados do Microsoft 365 defender:</span><span class="sxs-lookup"><span data-stu-id="bf531-107">Accounts assigned the following Azure Active Directory (AD) roles can access Microsoft 365 Defender functionality and data:</span></span>
- <span data-ttu-id="bf531-108">Administrador global</span><span class="sxs-lookup"><span data-stu-id="bf531-108">Global administrator</span></span>
- <span data-ttu-id="bf531-109">Administrador de segurança</span><span class="sxs-lookup"><span data-stu-id="bf531-109">Security administrator</span></span>
- <span data-ttu-id="bf531-110">Operador de segurança</span><span class="sxs-lookup"><span data-stu-id="bf531-110">Security Operator</span></span>
- <span data-ttu-id="bf531-111">Leitor global</span><span class="sxs-lookup"><span data-stu-id="bf531-111">Global Reader</span></span>
- <span data-ttu-id="bf531-112">Leitor de segurança</span><span class="sxs-lookup"><span data-stu-id="bf531-112">Security Reader</span></span>

<span data-ttu-id="bf531-113">Para revisar as contas com essas funções, [exiba as Permissões no centro de segurança do Microsoft 365](https://security.microsoft.com/permissions).</span><span class="sxs-lookup"><span data-stu-id="bf531-113">To review accounts with these roles, [view Permissions in the Microsoft 365 security center](https://security.microsoft.com/permissions).</span></span>

## <a name="access-to-functionality"></a><span data-ttu-id="bf531-114">Acesso à funcionalidade</span><span class="sxs-lookup"><span data-stu-id="bf531-114">Access to functionality</span></span>
<span data-ttu-id="bf531-115">O acesso a uma funcionalidade específica é determinado pela sua [função do Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="bf531-115">Access to specific functionality is determined by your [Azure AD role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles).</span></span> <span data-ttu-id="bf531-116">Entre em contato com um administrador global caso precise de acesso a uma funcionalidade específica que exija que você ou seu grupo de usuários tenham uma nova função.</span><span class="sxs-lookup"><span data-stu-id="bf531-116">Contact a global administrator if you need access to specific functionality that requires you or your user group be assigned a new role.</span></span>

### <a name="approve-pending-automated-tasks"></a><span data-ttu-id="bf531-117">Aprovação de tarefas automatizadas pendentes</span><span class="sxs-lookup"><span data-stu-id="bf531-117">Approve pending automated tasks</span></span>
<span data-ttu-id="bf531-118">[A investigação e a correção automáticas](mtp-autoir-actions.md) podem executar ações em emails, regras de encaminhamento, arquivos, mecanismos de persistência e outros artefatos encontrados durante investigações.</span><span class="sxs-lookup"><span data-stu-id="bf531-118">[Automated investigation and remediation](mtp-autoir-actions.md) can take action on emails, forwarding rules, files, persistence mechanisms, and other artifacts found during investigations.</span></span> <span data-ttu-id="bf531-119">Para aprovar ou rejeitar ações pendentes que exijam aprovação explícita, você deve ter determinadas funções atribuídas no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bf531-119">To approve or reject pending actions that require explicit approval, you must have certain roles assigned in Microsoft 365.</span></span> <span data-ttu-id="bf531-120">Para saber mais, confira [Permissões da central de ações](mtp-action-center.md#required-permissions-for-action-center-tasks).</span><span class="sxs-lookup"><span data-stu-id="bf531-120">To learn more, see [Action center permissions](mtp-action-center.md#required-permissions-for-action-center-tasks).</span></span>

## <a name="access-to-data"></a><span data-ttu-id="bf531-121">Acesso a dados</span><span class="sxs-lookup"><span data-stu-id="bf531-121">Access to data</span></span>
<span data-ttu-id="bf531-122">O acesso aos dados do Microsoft 365 defender pode ser controlado usando o escopo atribuído aos grupos de usuários no Microsoft defender para controle de acesso baseado em função de ponto de extremidade (RBAC).</span><span class="sxs-lookup"><span data-stu-id="bf531-122">Access to Microsoft 365 Defender data can be controlled using the scope assigned to user groups in Microsoft Defender for Endpoint role-based access control (RBAC).</span></span> <span data-ttu-id="bf531-123">Se o seu acesso não tiver sido definido para um conjunto específico de dispositivos no defender para ponto de extremidade, você terá acesso total aos dados no Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="bf531-123">If your access has not been scoped to a specific set of devices in the Defender for Endpoint, you will have full access to data in Microsoft 365 Defender.</span></span> <span data-ttu-id="bf531-124">No entanto, depois que sua conta tiver um escopo, você só verá os dados dos dispositivos dentro do seu escopo.</span><span class="sxs-lookup"><span data-stu-id="bf531-124">However, once your account is scoped, you will only see data about the devices in your scope.</span></span>

<span data-ttu-id="bf531-125">Por exemplo, se você pertencer apenas um grupo de usuários com uma função do Microsoft defender para ponto de extremidade e esse grupo de usuários tiver acesso apenas aos dispositivos de vendas, você verá apenas dados sobre os dispositivos de vendas no Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="bf531-125">For example, if you belong to only one user group with a Microsoft Defender for Endpoint role and that user group has been given access to sales devices only, you will see only data about sales devices in Microsoft 365 Defender.</span></span> [<span data-ttu-id="bf531-126">Saiba mais sobre as configurações RBAC no Microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="bf531-126">Learn more about RBAC settings in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a><span data-ttu-id="bf531-127">Controles de acesso ao Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bf531-127">Microsoft Cloud App Security access controls</span></span>
<span data-ttu-id="bf531-128">Durante a visualização, o Microsoft 365 defender não aplica os controles de acesso com base nas configurações de segurança do aplicativo na nuvem.</span><span class="sxs-lookup"><span data-stu-id="bf531-128">During the preview, Microsoft 365 Defender does not enforce access controls based on  Cloud App Security settings.</span></span> <span data-ttu-id="bf531-129">O acesso aos dados do Microsoft 365 defender não é afetado por essas configurações.</span><span class="sxs-lookup"><span data-stu-id="bf531-129">Access to Microsoft 365 Defender data is not affected by these settings.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bf531-130">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="bf531-130">Related topics</span></span>

- [<span data-ttu-id="bf531-131">Funções do Azure AD</span><span class="sxs-lookup"><span data-stu-id="bf531-131">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [<span data-ttu-id="bf531-132">Microsoft defender para ponto de extremidade RBAC</span><span class="sxs-lookup"><span data-stu-id="bf531-132">Microsoft Defender for Endpoint RBAC</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [<span data-ttu-id="bf531-133">Funções do Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bf531-133">Cloud App Security roles</span></span>](https://docs.microsoft.com/cloud-app-security/manage-admins)
