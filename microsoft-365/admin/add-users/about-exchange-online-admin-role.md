---
title: Sobre a função de administrador do Exchange Online
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 097ae285-c4af-4319-9770-e2559d66e4c8
description: 'Os administradores do Exchange online gerenciam os emails e caixas de correio da sua organização. Por exemplo, eles recuperam itens excluídos na caixa de correio de um usuário. '
ms.openlocfilehash: 4dc1f435571650ae4a805198782c3c24a92024fb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197644"
---
# <a name="about-the-exchange-online-admin-role"></a><span data-ttu-id="d65a3-104">Sobre a função de administrador do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d65a3-104">About the Exchange Online admin role</span></span>

<span data-ttu-id="d65a3-105">Para ajudá-lo a administrar o [](assign-admin-roles.md) Microsoft 365, você pode atribuir permissões aos usuários para gerenciar emails e caixas de correio da sua organização no Centro de administração [do Exchange.](/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="d65a3-105">To help you administer Microsoft 365, you can [assign](assign-admin-roles.md) users permissions to manage your organization's email and mailboxes from the [Exchange admin center](/exchange/exchange-admin-center).</span></span> <span data-ttu-id="d65a3-106">Faça isso atribuindo-os à função de administrador do Exchange.</span><span class="sxs-lookup"><span data-stu-id="d65a3-106">You do this by assigning them to the Exchange admin role.</span></span>
  
 <span data-ttu-id="d65a3-107">**Dica:** ao atribuir alguém à função de administrador do Exchange, atribua-o também à função de administrador do Serviço.</span><span class="sxs-lookup"><span data-stu-id="d65a3-107">**Tip**: When you assign someone to the Exchange admin role, also assign them to the Service admin role.</span></span> <span data-ttu-id="d65a3-108">Dessa forma, eles podem ver informações importantes no Centro de administração do Microsoft 365, como a saúde do serviço Exchange Online, e notificações de alteração e versão.</span><span class="sxs-lookup"><span data-stu-id="d65a3-108">This way they can see important information in the Microsoft 365 admin center, such as the health of the Exchange Online service, and change and release notifications.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="d65a3-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="d65a3-109">Before you begin</span></span>

<span data-ttu-id="d65a3-110">Aqui estão algumas das principais tarefas que os usuários podem realizar quando são atribuídos à função de administrador do Exchange:</span><span class="sxs-lookup"><span data-stu-id="d65a3-110">Here are some of the key tasks users can do when they are assigned to the Exchange admin role:</span></span>
  
- [<span data-ttu-id="d65a3-111">Recuperar itens excluídos na caixa de correio do usuário – Ajuda para Administradores</span><span class="sxs-lookup"><span data-stu-id="d65a3-111">Recover deleted items in a user mailbox - Admin Help</span></span>](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- <span data-ttu-id="d65a3-112">[Configurar uma política de arquivamento e exclusão para caixas de correio em sua organização.](../../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md)</span><span class="sxs-lookup"><span data-stu-id="d65a3-112">[Set up an archive and deletion policy for mailboxes in your organization](../../compliance/set-up-an-archive-and-deletion-policy-for-mailboxes.md).</span></span>

- <span data-ttu-id="d65a3-113">Configurar recursos de caixa de correio, como a política de compartilhamento de caixa de correio: como os usuários podem compartilhar informações de calendário e contatos com outras pessoas fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="d65a3-113">Set up mailbox features such as the mailbox sharing policy: how users can share calendar and contacts information with others outside of your organization.</span></span>

- <span data-ttu-id="d65a3-114">Configurar representantes "[Enviar como](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" e " Enviar em[nome](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" para a caixa de correio de alguém.</span><span class="sxs-lookup"><span data-stu-id="d65a3-114">Set up "[Send as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" and "[Send on behalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" delegates for someone's mailbox.</span></span> <span data-ttu-id="d65a3-115">Por exemplo, um executivo pode querer que seu assistente tenha a capacidade de enviar emails em seu nome.</span><span class="sxs-lookup"><span data-stu-id="d65a3-115">For example, an executive may want their assistant to have the ability to send mail on their behalf.</span></span>

- <span data-ttu-id="d65a3-116">[Crie uma caixa de correio compartilhada](../email/create-a-shared-mailbox.md) para que um grupo de pessoas possa monitorar e enviar emails de um endereço de email comum.</span><span class="sxs-lookup"><span data-stu-id="d65a3-116">[Create a shared mailbox](../email/create-a-shared-mailbox.md) so a group of people can monitor and send email from a common email address.</span></span>

- <span data-ttu-id="d65a3-117">[Filtros de malware e proteção anti-spam](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) de email para a organização.</span><span class="sxs-lookup"><span data-stu-id="d65a3-117">[Email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) and malware filters for the organization.</span></span>

- <span data-ttu-id="d65a3-118">Gerenciar grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d65a3-118">Manage Microsoft 365 groups</span></span>

## <a name="exchange-online-role-groups"></a><span data-ttu-id="d65a3-119">Grupos de função do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d65a3-119">Exchange Online role groups</span></span>

<span data-ttu-id="d65a3-120">Se você tiver uma organização grande, talvez o administrador do Exchange queira atribuir usuários a grupos de função do Exchange.</span><span class="sxs-lookup"><span data-stu-id="d65a3-120">If you have a large organization, the Exchange admin might want to assign users to Exchange role groups.</span></span> <span data-ttu-id="d65a3-121">Quando um administrador adiciona um usuário a um grupo de funções, o usuário obtém permissões para executar determinadas funções comerciais que somente membros desse grupo podem fazer.</span><span class="sxs-lookup"><span data-stu-id="d65a3-121">When an admin adds a user to a role group, the user gets permissions to perform certain business functions only members of that group can do.</span></span>
  
 <span data-ttu-id="d65a3-122">Por exemplo, o administrador do Exchange pode atribuir alguém ao grupo de função Gerenciamento de Descoberta para que ele possa executar pesquisas de caixas de correio para dados que atendam a determinados critérios.</span><span class="sxs-lookup"><span data-stu-id="d65a3-122">For example, the Exchange admin might assign someone to the Discovery Management role group so they can perform searches of mailboxes for data that meets certain criteria.</span></span> <span data-ttu-id="d65a3-123">Para saber mais, confira [Permissões no Exchange Online e](/exchange/permissions-exo/permissions-exo) Gerenciar Grupos de [Função.](/exchange/manage-role-groups-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="d65a3-123">To learn more, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Manage Role Groups](/exchange/manage-role-groups-exchange-2013-help).</span></span>
  
## <a name="learn-about-other-admin-roles"></a><span data-ttu-id="d65a3-124">Saiba mais sobre outras funções de administrador</span><span class="sxs-lookup"><span data-stu-id="d65a3-124">Learn about other admin roles</span></span>

- [<span data-ttu-id="d65a3-125">Sobre as funções de administrador do Microsoft 365 </span><span class="sxs-lookup"><span data-stu-id="d65a3-125">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

- [<span data-ttu-id="d65a3-126">Sobre a função de administrador do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d65a3-126">About the SharePoint Online admin role</span></span>](/sharepoint/sharepoint-admin-role)

- [<span data-ttu-id="d65a3-127">Sobre a função de administrador do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d65a3-127">About the Skype for Business admin role</span></span>](/skypeforbusiness/skype-for-business-online)

- [<span data-ttu-id="d65a3-128">Usar a função de administrador do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d65a3-128">Use Microsoft Teams admin role</span></span>](/MicrosoftTeams/using-admin-roles)