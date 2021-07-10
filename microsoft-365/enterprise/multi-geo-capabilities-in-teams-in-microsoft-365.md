---
title: Recursos multi-geo no Microsoft Teams
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
description: Saiba mais sobre como Teams funciona com Microsoft 365 Multi-Geo.
ms.openlocfilehash: 9fe9b289b0ffbef12327c4232b9deb6727b6d718
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362637"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a><span data-ttu-id="25669-103">Recursos multi-geo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="25669-103">Multi-Geo capabilities in Microsoft Teams</span></span>

<span data-ttu-id="25669-104">Recursos multi-geo no Teams permite que Teams dados de chat sejam armazenados em repouso em uma localização geográfica especificada.</span><span class="sxs-lookup"><span data-stu-id="25669-104">Multi-Geo capabilities in Teams enables Teams chat data to be stored at rest in a specified geo location.</span></span> <span data-ttu-id="25669-105">Os dados de chat consistem em mensagens de chat, incluindo mensagens privadas, mensagens de canal e imagens usadas em chats.</span><span class="sxs-lookup"><span data-stu-id="25669-105">Chat data consists of chat messages, including private messages, channel messages, and images used in chats.</span></span>

<span data-ttu-id="25669-106">Teams usa o PDL (Preferred Data Location) para usuários e grupos determinarem onde armazenar dados.</span><span class="sxs-lookup"><span data-stu-id="25669-106">Teams uses the Preferred Data Location (PDL) for users and groups to determine where to store data.</span></span> <span data-ttu-id="25669-107">Se o PDL não estiver definido ou for inválido, os dados serão armazenados no local central do locatário.</span><span class="sxs-lookup"><span data-stu-id="25669-107">If the PDL is not set or is invalid, data is stored in the tenant's central location.</span></span>

## <a name="user-chat"></a><span data-ttu-id="25669-108">Chat do usuário</span><span class="sxs-lookup"><span data-stu-id="25669-108">User chat</span></span>

<span data-ttu-id="25669-109">O chat do usuário inclui mensagens de reunião particulares, um para um e um para muitos.</span><span class="sxs-lookup"><span data-stu-id="25669-109">User chat includes one-to-one, one-to-many, and private meeting messages.</span></span>

<span data-ttu-id="25669-110">Quando um novo usuário é criado, Teams lê o PDL do usuário e armazena todos os seus dados de chat nessa localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="25669-110">When a new user is created, Teams reads the user's PDL and stores all their chat data in that geo location.</span></span>

<span data-ttu-id="25669-111">Para usuários existentes, se um administrador adicionar ou modificar o PDL de um usuário, os dados de chat desse usuário serão adicionados a uma fila de migração para serem movidos para a localização geográfica especificada.</span><span class="sxs-lookup"><span data-stu-id="25669-111">For existing users, if an administrator adds or modifies the PDL for a user, that user's chat data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="25669-112">O local de armazenamento para um chat de um para um ou um para muitos é baseado no PDL da pessoa que criou o chat.</span><span class="sxs-lookup"><span data-stu-id="25669-112">The storage location for a one-to-one or one-to-many chat is based on the PDL of the person who created the chat.</span></span> <span data-ttu-id="25669-113">Se o PDL desse usuário for alterado, o chat será migrado para a nova localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="25669-113">If that user's PDL is changed, the chat will be migrated to the new geo location.</span></span> <span data-ttu-id="25669-114">O local de armazenamento de um chat de reunião é baseado no PDL do organizador da reunião.</span><span class="sxs-lookup"><span data-stu-id="25669-114">The storage location for a meeting chat is based on the PDL of the meeting organizer.</span></span>

<span data-ttu-id="25669-115">Para localizar o local atual dos dados de Teams de um usuário, conecte-se [ao Teams PowerShell](/powershell/module/teams/connect-microsoftteams) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="25669-115">To find the current location of a user's Teams data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a><span data-ttu-id="25669-116">Mensagens de canal</span><span class="sxs-lookup"><span data-stu-id="25669-116">Channel messages</span></span>

<span data-ttu-id="25669-117">Cada Microsoft 365 grupo tem um PDL (Preferred Data Location) que indica a localização geográfica onde os dados relacionados devem ser armazenados.</span><span class="sxs-lookup"><span data-stu-id="25669-117">Each Microsoft 365 group has a Preferred Data Location (PDL) which denotes the geo location where related data is to be stored.</span></span> <span data-ttu-id="25669-118">Teams usa o PDL para o grupo associado a cada equipe para determinar onde armazenar dados de mensagens de canal para essa equipe.</span><span class="sxs-lookup"><span data-stu-id="25669-118">Teams uses the PDL for the group associated with each team to determine where to store channel messaging data for that team.</span></span> <span data-ttu-id="25669-119">Isso inclui um chat que ocorre em uma reunião de canal.</span><span class="sxs-lookup"><span data-stu-id="25669-119">This includes chat that occurs within a channel meeting.</span></span>

<span data-ttu-id="25669-120">Quando um usuário cria uma nova equipe, o PDL desse usuário determina qual PDL é atribuído ao Microsoft 365 grupo.</span><span class="sxs-lookup"><span data-stu-id="25669-120">When a user creates a new team, that user's PDL determines what PDL is assigned to the Microsoft 365 group.</span></span> <span data-ttu-id="25669-121">O PDL do grupo determina onde os dados dessa equipe são armazenados.</span><span class="sxs-lookup"><span data-stu-id="25669-121">The group PDL determines where that team's data is stored.</span></span> <span data-ttu-id="25669-122">Se o PDL desse usuário for alterado posteriormente, o PDL do grupo não será alterado.</span><span class="sxs-lookup"><span data-stu-id="25669-122">If that user's PDL later changes, the group's PDL is not changed.</span></span>

<span data-ttu-id="25669-123">Para equipes existentes, se um administrador adicionar ou modificar o PDL para o grupo Microsoft 365 que faz o suporte a uma equipe, os dados de mensagens de canal dessa equipe serão adicionados a uma fila de migração a ser movida para a localização geográfica especificada.</span><span class="sxs-lookup"><span data-stu-id="25669-123">For existing teams, if an administrator adds or modifies the PDL for the Microsoft 365 group that backs a team, that team's channel messaging data is added to a migration queue to be moved to the specified geo location.</span></span>

<span data-ttu-id="25669-124">A alteração da PDL do grupo Microsoft 365 enfileia os dados Teams para migrar para o local escolhido.</span><span class="sxs-lookup"><span data-stu-id="25669-124">Changing the PDL of the Microsoft 365 group queues the Teams data to migrate to the chosen location.</span></span> <span data-ttu-id="25669-125">No entanto, isso não migra automaticamente o site SharePoint ou arquivos associados ao Grupo.</span><span class="sxs-lookup"><span data-stu-id="25669-125">However, this does not migrate the SharePoint site or files associated with the Group automatically.</span></span> <span data-ttu-id="25669-126">Você deve mover o site separadamente seguindo os procedimentos em [Move a SharePoint site para uma localização geográfica diferente.](/microsoft-365/enterprise/move-sharepoint-between-geo-locations)</span><span class="sxs-lookup"><span data-stu-id="25669-126">You must move the site separately by following the procedures in [Move a SharePoint site to a different geo location](/microsoft-365/enterprise/move-sharepoint-between-geo-locations).</span></span> <span data-ttu-id="25669-127">Certifique-se de fazer as duas etapas para evitar Teams dados e SharePoint dados para um grupo em locais diferentes.</span><span class="sxs-lookup"><span data-stu-id="25669-127">Be sure to do both steps to avoid Teams data and SharePoint data for one group in different locations.</span></span>

<span data-ttu-id="25669-128">Para localizar o local atual dos dados de uma equipe, conecte-se ao [Teams PowerShell](/powershell/module/teams/connect-microsoftteams) e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="25669-128">To find the current location of a team's data, [connect to Teams PowerShell](/powershell/module/teams/connect-microsoftteams) and run the following command:</span></span>

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a><span data-ttu-id="25669-129">Experiência do Usuário</span><span class="sxs-lookup"><span data-stu-id="25669-129">User Experience</span></span>

<span data-ttu-id="25669-130">Teams Multi-Geo é perfeita para o usuário final.</span><span class="sxs-lookup"><span data-stu-id="25669-130">Teams Multi-Geo is seamless to the end user.</span></span> <span data-ttu-id="25669-131">Depois que você alterar a PDL de um usuário ou grupo, os respectivos dados serão enfilados para migração e a migração ocorrerá automaticamente sem impacto para o usuário ou seu cliente Teams, mesmo que eles sejam ativos enquanto a migração ocorrer.</span><span class="sxs-lookup"><span data-stu-id="25669-131">Once you change the PDL of a user or a group, the respective data will queue for migration and the migration will occur automatically with no impact to the user or their Teams client even if they are active while the migration occurs.</span></span>

## <a name="see-also"></a><span data-ttu-id="25669-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="25669-132">See also</span></span>

[<span data-ttu-id="25669-133">Configuração do locatário do Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="25669-133">Microsoft 365 Multi-Geo tenant configuration</span></span>](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[<span data-ttu-id="25669-134">Administrar um ambiente multigeográfico</span><span class="sxs-lookup"><span data-stu-id="25669-134">Administering a multi-geo environment</span></span>](administering-a-multi-geo-environment.md)

[<span data-ttu-id="25669-135">Administrar caixas de correio do Exchange Online em um ambiente multigeográfico</span><span class="sxs-lookup"><span data-stu-id="25669-135">Administering Exchange Online mailboxes in a multi-geo environment</span></span>](administering-exchange-online-multi-geo.md)
