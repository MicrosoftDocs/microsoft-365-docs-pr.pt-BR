---
title: Gerenciar destinatários no EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 2921f544-8257-4bae-8e3a-ce9250e9f162
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá sobre destinatários de email com suporte do Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: eb2855f93083c88725492be2691799c3521bbf8f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036144"
---
# <a name="manage-recipients-in-eop"></a><span data-ttu-id="88a81-103">Gerenciar destinatários no EOP</span><span class="sxs-lookup"><span data-stu-id="88a81-103">Manage recipients in EOP</span></span>

<span data-ttu-id="88a81-104">O Microsoft Proteção do Exchange Online (EOP) oferece várias maneiras de gerenciar seus destinatários de email.</span><span class="sxs-lookup"><span data-stu-id="88a81-104">Microsoft Exchange Online Protection (EOP) offers several ways to manage your mail recipients.</span></span> <span data-ttu-id="88a81-105">Como administrador, você pode executar determinadas tarefas de gerenciamento no centro de administração do Exchange (Eat) ou usar o Windows PowerShell remoto e verificar outras tarefas de gerenciamento executadas no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="88a81-105">As an administrator, you can perform certain management tasks within the Exchange admin center (EAC) or using remote Windows PowerShell, and verify other management tasks performed in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="88a81-106">O EOP oferece suporte a estes três tipos de destinatários:</span><span class="sxs-lookup"><span data-stu-id="88a81-106">EOP supports the following types of recipients:</span></span>

- <span data-ttu-id="88a81-107">**Usuários de email**: os usuários de email são destinatários em seus domínios gerenciados pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="88a81-107">**Mail Users**: Mail users are recipients in your EOP managed domains.</span></span> <span data-ttu-id="88a81-108">Esses destinatários têm credenciais de logon na sua organização, mas têm endereços de email externos, o que significa que suas caixas de correio de destinatário estão localizadas fora da organização da nuvem.</span><span class="sxs-lookup"><span data-stu-id="88a81-108">These recipients have logon credentials in your organization, but they have external email addresses, meaning that their recipient mailboxes are located outside of your cloud organization.</span></span>

  <span data-ttu-id="88a81-109">Você pode adicionar usuários de email para que eles possam receber emails e também pode criar regras de fluxo de emails (também conhecidas como regras de transporte) para usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="88a81-109">You can add mail users so that they can receive mail and you can also create mail flow rules (also known as transport rules) for specific users.</span></span> <span data-ttu-id="88a81-110">Você também pode atribuir funções aos usuários de email em sua organização; os usuários com privilégios de grupo de função de gerenciamento podem acessar o centro de administração do Exchange (Eat) e realizar determinadas tarefas de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="88a81-110">You can also assign roles to mail users in your organization; users with management role group privileges can access the Exchange admin center (EAC) and perform certain management tasks.</span></span> <span data-ttu-id="88a81-111">Para saber mais sobre as funções de usuário e como atribuir funções de usuário no EOP, confira [gerenciar permissões do grupo de funções de administrador no EOP](manage-admin-role-group-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="88a81-111">To learn more about user roles and how to assign user roles in EOP, see [Manage admin role group permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span></span>

  <span data-ttu-id="88a81-112">Para obter mais informações sobre o gerenciamento de usuários de email no EOP, consulte [Gerenciar usuários de email no EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="88a81-112">For more information about managing mail users in EOP, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

- <span data-ttu-id="88a81-113">**Grupos**: os usuários de email podem ser agrupados em grupos de distribuição ou em grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="88a81-113">**Groups**: Mail users can be grouped together into distribution groups or security groups.</span></span>

<span data-ttu-id="88a81-114">Para obter mais informações sobre o gerenciamento de grupos no EOP, consulte [Gerenciar grupos no EOP](manage-groups-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="88a81-114">For more information about managing groups in EOP, see [Manage groups in EOP](manage-groups-in-eop.md).</span></span>
