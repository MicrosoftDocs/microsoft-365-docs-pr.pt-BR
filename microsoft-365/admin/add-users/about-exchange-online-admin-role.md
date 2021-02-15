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
description: 'Os administradores do Exchange Online gerenciam o email e as caixas de correio da sua organização. Por exemplo, eles recuperam itens excluídos na caixa de correio de um usuário. '
ms.openlocfilehash: 8e332e886ca25221fefbbc5d1bb790bd4f513f00
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527508"
---
# <a name="about-the-exchange-online-admin-role"></a><span data-ttu-id="58fa7-104">Sobre a função de administrador do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="58fa7-104">About the Exchange Online admin role</span></span>

<span data-ttu-id="58fa7-105">Para ajudá-lo a administrar o [](assign-admin-roles.md) Microsoft 365, você pode atribuir permissões aos usuários para gerenciar o email e as caixas de correio da sua organização no Centro de administração [do Exchange.](https://go.microsoft.com/fwlink/p/?LinkID=271807)</span><span class="sxs-lookup"><span data-stu-id="58fa7-105">To help you administer Microsoft 365, you can [assign](assign-admin-roles.md) users permissions to manage your organization's email and mailboxes from the [Exchange admin center](https://go.microsoft.com/fwlink/p/?LinkID=271807).</span></span> <span data-ttu-id="58fa7-106">Para fazer isso, atribua-os à função de administrador do Exchange.</span><span class="sxs-lookup"><span data-stu-id="58fa7-106">You do this by assigning them to the Exchange admin role.</span></span>
  
 <span data-ttu-id="58fa7-107">**Dica:** quando você atribuir uma pessoa à função de administrador do Exchange, atribua-a também à função de administrador de serviço.</span><span class="sxs-lookup"><span data-stu-id="58fa7-107">**Tip**: When you assign someone to the Exchange admin role, also assign them to the Service admin role.</span></span> <span data-ttu-id="58fa7-108">Dessa forma, eles podem ver informações importantes no centro de administração do Microsoft 365, como a saúde do serviço Exchange Online e notificações de alteração e lançamento.</span><span class="sxs-lookup"><span data-stu-id="58fa7-108">This way they can see important information in the Microsoft 365 admin center, such as the health of the Exchange Online service, and change and release notifications.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="58fa7-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="58fa7-109">Before you begin</span></span>

<span data-ttu-id="58fa7-110">Aqui estão algumas das principais tarefas que os usuários podem realizar quando são atribuídos à função de administrador do Exchange:</span><span class="sxs-lookup"><span data-stu-id="58fa7-110">Here are some of the key tasks users can do when they are assigned to the Exchange admin role:</span></span>
  
- [<span data-ttu-id="58fa7-111">Recuperar itens excluídos na caixa de correio do usuário – Ajuda para Administradores</span><span class="sxs-lookup"><span data-stu-id="58fa7-111">Recover deleted items in a user mailbox - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/recover-deleted-items-in-a-mailbox)

- <span data-ttu-id="58fa7-112">[Configurar uma política de arquivamento e exclusão para caixas de correio em sua organização.](https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="58fa7-112">[Set up an archive and deletion policy for mailboxes in your organization](https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes).</span></span>

- <span data-ttu-id="58fa7-113">Configurar recursos de caixa de correio, como a política de compartilhamento de caixa de correio: como os usuários podem compartilhar informações de calendário e contatos com outras pessoas de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="58fa7-113">Set up mailbox features such as the mailbox sharing policy: how users can share calendar and contacts information with others outside of your organization.</span></span>

- <span data-ttu-id="58fa7-114">Configurar representantes "[Enviar como](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" e "[Enviar](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)em nome " para a caixa de correio de alguém.</span><span class="sxs-lookup"><span data-stu-id="58fa7-114">Set up "[Send as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" and "[Send on behalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" delegates for someone's mailbox.</span></span> <span data-ttu-id="58fa7-115">Por exemplo, um executivo pode querer que seu assistente tenha a capacidade de enviar emails em seu nome.</span><span class="sxs-lookup"><span data-stu-id="58fa7-115">For example, an executive may want their assistant to have the ability to send mail on their behalf.</span></span>

- <span data-ttu-id="58fa7-116">[Crie uma caixa de correio compartilhada](../email/create-a-shared-mailbox.md) para que um grupo de pessoas possa monitorar e enviar emails de um endereço de email comum.</span><span class="sxs-lookup"><span data-stu-id="58fa7-116">[Create a shared mailbox](../email/create-a-shared-mailbox.md) so a group of people can monitor and send email from a common email address.</span></span>

- <span data-ttu-id="58fa7-117">[Filtros de proteção anti-spam](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) e malware de email para a organização.</span><span class="sxs-lookup"><span data-stu-id="58fa7-117">[Email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) and malware filters for the organization.</span></span>

- <span data-ttu-id="58fa7-118">Gerenciar grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58fa7-118">Manage Microsoft 365 groups</span></span>

## <a name="exchange-online-role-groups"></a><span data-ttu-id="58fa7-119">Grupos de função do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="58fa7-119">Exchange Online role groups</span></span>

<span data-ttu-id="58fa7-120">Se você tiver uma organização de grande porte, o administrador do Exchange talvez queira atribuir usuários a grupos de função do Exchange.</span><span class="sxs-lookup"><span data-stu-id="58fa7-120">If you have a large organization, the Exchange admin might want to assign users to Exchange role groups.</span></span> <span data-ttu-id="58fa7-121">Quando um administrador adiciona um usuário a um grupo de funções, ele obtém permissões para executar determinadas funções comerciais que somente membros desse grupo podem fazer.</span><span class="sxs-lookup"><span data-stu-id="58fa7-121">When an admin adds a user to a role group, the user gets permissions to perform certain business functions only members of that group can do.</span></span>
  
 <span data-ttu-id="58fa7-122">Por exemplo, o administrador do Exchange pode atribuir alguém ao grupo de funções Gerenciamento de Descoberta para que ele possa realizar pesquisas de caixas de correio para dados que atendam a determinados critérios.</span><span class="sxs-lookup"><span data-stu-id="58fa7-122">For example, the Exchange admin might assign someone to the Discovery Management role group so they can perform searches of mailboxes for data that meets certain criteria.</span></span> <span data-ttu-id="58fa7-123">Para saber mais, consulte [Permissões no Exchange Online e](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) Gerenciar Grupos de [Função.](https://docs.microsoft.com/exchange/manage-role-groups-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="58fa7-123">To learn more, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Manage Role Groups](https://docs.microsoft.com/exchange/manage-role-groups-exchange-2013-help).</span></span>
  
## <a name="learn-about-other-admin-roles"></a><span data-ttu-id="58fa7-124">Saiba mais sobre outras funções de administrador</span><span class="sxs-lookup"><span data-stu-id="58fa7-124">Learn about other admin roles</span></span>

- [<span data-ttu-id="58fa7-125">Sobre as funções de administrador do Microsoft 365 </span><span class="sxs-lookup"><span data-stu-id="58fa7-125">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

- [<span data-ttu-id="58fa7-126">Sobre a função de administrador do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="58fa7-126">About the SharePoint Online admin role</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)

- [<span data-ttu-id="58fa7-127">Sobre a função de administrador do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="58fa7-127">About the Skype for Business admin role</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online)

- [<span data-ttu-id="58fa7-128">Usar a função de administrador do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="58fa7-128">Use Microsoft Teams admin role</span></span>](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles) 
