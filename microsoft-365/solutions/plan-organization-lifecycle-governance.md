---
title: Planejar a governança da organização e do ciclo de vida para grupos do Microsoft 365 e Microsoft Teams
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Saber mais sobre as opções de governança do ciclo de vida para ferramentas de colaboração no Microsoft 365
ms.openlocfilehash: 4d779701d241fc7178ab759063be1b8cdf2e960c
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613015"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="45b0c-103">Planejar a governança da organização e do ciclo de vida para grupos do Microsoft 365 e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45b0c-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="45b0c-104">Os grupos do Microsoft 365 têm um conjunto rico de ferramentas para implementar os recursos de governança necessários para sua organização.</span><span class="sxs-lookup"><span data-stu-id="45b0c-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="45b0c-105">A seção a seguir descreve os recursos, recomenda as práticas recomendadas e fornece orientações para fazer as perguntas certas para determinar os requisitos de governança e como atender a eles.</span><span class="sxs-lookup"><span data-stu-id="45b0c-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="45b0c-106">Controlar quem pode criar grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="45b0c-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="45b0c-107">Os grupos podem ser criados por usuários finais de vários pontos de extremidade, incluindo o Outlook, o SharePoint, o Teams e outros ambientes.</span><span class="sxs-lookup"><span data-stu-id="45b0c-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![desc de imagem](../media/04.png)

<span data-ttu-id="45b0c-109">É altamente recomendável que o autoatendado capacite os proprietários do grupo e ajude os usuários a fazer seu trabalho com mais facilidade.</span><span class="sxs-lookup"><span data-stu-id="45b0c-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="45b0c-110">Limitar a criação de grupos e equipes pode reduzir a produtividade dos usuários porque muitos serviços do Microsoft 365 exigem que os grupos sejam criados para que o serviço funcione.</span><span class="sxs-lookup"><span data-stu-id="45b0c-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="45b0c-111">Considere as seguintes opções de governança para a criação de grupos:</span><span class="sxs-lookup"><span data-stu-id="45b0c-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="45b0c-112">Para limitar a expansão do grupo, use as políticas [de expiração de](microsoft-365-groups-expiration-policy.md) grupos para excluir automaticamente os grupos que não estão sendo usados.</span><span class="sxs-lookup"><span data-stu-id="45b0c-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="45b0c-113">Limitar a criação de grupos a membros de grupos [de segurança com](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) associação dinâmica contendo, por exemplo, todos os funcionários em tempo integral.</span><span class="sxs-lookup"><span data-stu-id="45b0c-113">Limit group creation to members of a [security groups with dynamic membership](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="45b0c-114">Limite a criação de grupos a um grupo de segurança e exige que os usuários concluam o treinamento nas políticas de uso de grupo da sua organização para se tornarem membros do grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="45b0c-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="45b0c-115">Se você quiser limitar quem pode criar grupos, confira Gerenciar quem pode criar grupos do [Microsoft 365](manage-creation-of-groups.md) para obter informações sobre como configurar isso.</span><span class="sxs-lookup"><span data-stu-id="45b0c-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="45b0c-116">Exclusão, restauração e arquivamento de grupo</span><span class="sxs-lookup"><span data-stu-id="45b0c-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="45b0c-117">Quando um grupo do Microsoft 365 é excluído, por padrão, ele é mantido por 30 dias.</span><span class="sxs-lookup"><span data-stu-id="45b0c-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="45b0c-118">Esse período de 30 dias é denominado "exclusão temporária" porque ainda é possível restaurar o grupo.</span><span class="sxs-lookup"><span data-stu-id="45b0c-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="45b0c-119">Após 30 dias, o grupo e o conteúdo associado são excluídos permanentemente e não podem mais ser restaurados.</span><span class="sxs-lookup"><span data-stu-id="45b0c-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="45b0c-120">Se você tiver políticas de retenção para reter chat, arquivos ou emails, esses itens serão preservados depois que o grupo for excluído.</span><span class="sxs-lookup"><span data-stu-id="45b0c-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="45b0c-121">Para [saber mais sobre políticas de retenção,](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) confira.</span><span class="sxs-lookup"><span data-stu-id="45b0c-121">See [Learn about retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) for details.</span></span>

<span data-ttu-id="45b0c-122">Se você quiser excluir um grupo, mas preservar o conteúdo de um ou mais serviços conectados ao grupo, confira Grupos de arquivamento, equipes e [Yammer](end-life-cycle-groups-teams-sites-yammer.md) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="45b0c-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="45b0c-123">Política de nomeação de grupo</span><span class="sxs-lookup"><span data-stu-id="45b0c-123">Group naming policy</span></span>

<span data-ttu-id="45b0c-124">Uma política de nomeação de grupos pode ajudá-lo a governá-los de duas maneiras:</span><span class="sxs-lookup"><span data-stu-id="45b0c-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="45b0c-125">Uma política de nomeação de prefixo/sufixo pode ser usada para impor cadeias de caracteres fixas ou atributos do Azure AD no início ou no final de um nome de grupo e seu endereço de email associado.</span><span class="sxs-lookup"><span data-stu-id="45b0c-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="45b0c-126">Ao fazer isso, você pode garantir a inclusão, por exemplo, de nomes de departamento ou regiões em nomes de grupo.</span><span class="sxs-lookup"><span data-stu-id="45b0c-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="45b0c-127">Uma política de palavras bloqueadas pode garantir que determinadas palavras, como os nomes de executivos, não sejam usadas em nomes de grupo.</span><span class="sxs-lookup"><span data-stu-id="45b0c-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="45b0c-128">As políticas de nomeação são aplicadas quando grupos são criados a partir de qualquer um dos serviços conectados ao grupo.</span><span class="sxs-lookup"><span data-stu-id="45b0c-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="45b0c-129">Se você decidir usar políticas de nomeação para grupos, confira a política de nomen por grupos [do Microsoft 365.](groups-naming-policy.md)</span><span class="sxs-lookup"><span data-stu-id="45b0c-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="45b0c-130">Política de expiração de grupo</span><span class="sxs-lookup"><span data-stu-id="45b0c-130">Group expiration policy</span></span>

<span data-ttu-id="45b0c-131">Você pode especificar um período de expiração e qualquer grupo que atinja o final desse período, e não for renovado, será excluído.</span><span class="sxs-lookup"><span data-stu-id="45b0c-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="45b0c-132">O período de expiração começa quando o grupo é criado ou na data em que foi renovado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="45b0c-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="45b0c-133">Depois de definir os grupos para expirarem:</span><span class="sxs-lookup"><span data-stu-id="45b0c-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="45b0c-134">Os proprietários do grupo são notificados para renovar o grupo à medida que a expiração se aproxima.</span><span class="sxs-lookup"><span data-stu-id="45b0c-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="45b0c-135">Os grupos ativos são renovados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="45b0c-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="45b0c-136">Qualquer grupo que não for renovado será excluído.</span><span class="sxs-lookup"><span data-stu-id="45b0c-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="45b0c-137">Qualquer grupo excluído pode ser restaurado dentro de 30 dias pelos proprietários do grupo ou pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="45b0c-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="45b0c-138">As políticas de expiração são uma boa maneira de limitar a expansão do grupo, garantindo que os grupos que não estão mais em uso sejam excluídos.</span><span class="sxs-lookup"><span data-stu-id="45b0c-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="45b0c-139">Se você quiser criar uma política de expiração de grupo, confira a Política de Expiração de Grupo do [Microsoft 365.](microsoft-365-groups-expiration-policy.md)</span><span class="sxs-lookup"><span data-stu-id="45b0c-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="45b0c-140">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="45b0c-140">Related topics</span></span>

[<span data-ttu-id="45b0c-141">Planejamento de governança de colaboração passo a passo</span><span class="sxs-lookup"><span data-stu-id="45b0c-141">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="45b0c-142">Criar seu plano de governança de colaboração</span><span class="sxs-lookup"><span data-stu-id="45b0c-142">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)
