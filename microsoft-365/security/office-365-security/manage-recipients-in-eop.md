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
description: O Microsoft Proteção do Exchange Online (EOP) oferece várias maneiras de gerenciar seus destinatários de email. Como administrador, você pode executar determinadas tarefas de gerenciamento no centro de administração do Exchange (Eat) ou usar o Windows PowerShell remoto e verificar outras tarefas de gerenciamento executadas no centro de administração do Microsoft 365.
ms.openlocfilehash: b5d1efa0fb54b97f226f25375fb747e5373a36cd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635335"
---
# <a name="manage-recipients-in-eop"></a><span data-ttu-id="7fd52-104">Gerenciar destinatários no EOP</span><span class="sxs-lookup"><span data-stu-id="7fd52-104">Manage recipients in EOP</span></span>

<span data-ttu-id="7fd52-105">O Microsoft Proteção do Exchange Online (EOP) oferece várias maneiras de gerenciar seus destinatários de email.</span><span class="sxs-lookup"><span data-stu-id="7fd52-105">Microsoft Exchange Online Protection (EOP) offers several ways to manage your mail recipients.</span></span> <span data-ttu-id="7fd52-106">Como administrador, você pode executar determinadas tarefas de gerenciamento no centro de administração do Exchange (Eat) ou usar o Windows PowerShell remoto e verificar outras tarefas de gerenciamento executadas no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7fd52-106">As an administrator, you can perform certain management tasks within the Exchange admin center (EAC) or using remote Windows PowerShell, and verify other management tasks performed in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="7fd52-107">O EOP oferece suporte a estes três tipos de destinatários:</span><span class="sxs-lookup"><span data-stu-id="7fd52-107">EOP supports the following types of recipients:</span></span>

- <span data-ttu-id="7fd52-108">**Usuários de email**: os usuários de email são destinatários em seus domínios gerenciados pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="7fd52-108">**Mail Users**: Mail users are recipients in your EOP managed domains.</span></span> <span data-ttu-id="7fd52-109">Esses destinatários têm credenciais de logon na sua organização, mas têm endereços de email externos, o que significa que suas caixas de correio de destinatário estão localizadas fora da organização da nuvem.</span><span class="sxs-lookup"><span data-stu-id="7fd52-109">These recipients have logon credentials in your organization, but they have external email addresses, meaning that their recipient mailboxes are located outside of your cloud organization.</span></span>

  <span data-ttu-id="7fd52-110">Você pode adicionar usuários de email para que eles possam receber emails e também pode criar regras de fluxo de emails (também conhecidas como regras de transporte) para usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="7fd52-110">You can add mail users so that they can receive mail and you can also create mail flow rules (also known as transport rules) for specific users.</span></span> <span data-ttu-id="7fd52-111">Você também pode atribuir funções aos usuários de email em sua organização; os usuários com privilégios de grupo de função de gerenciamento podem acessar o centro de administração do Exchange (Eat) e realizar determinadas tarefas de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="7fd52-111">You can also assign roles to mail users in your organization; users with management role group privileges can access the Exchange admin center (EAC) and perform certain management tasks.</span></span> <span data-ttu-id="7fd52-112">Para saber mais sobre as funções de usuário e como atribuir funções de usuário no EOP, confira [gerenciar permissões do grupo de funções de administrador no EOP](manage-admin-role-group-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="7fd52-112">To learn more about user roles and how to assign user roles in EOP, see [Manage admin role group permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span></span>

  <span data-ttu-id="7fd52-113">Para obter mais informações sobre o gerenciamento de usuários de email no EOP, consulte [Gerenciar usuários de email no EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="7fd52-113">For more information about managing mail users in EOP, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

- <span data-ttu-id="7fd52-114">**Grupos**: os usuários de email podem ser agrupados em grupos de distribuição ou em grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="7fd52-114">**Groups**: Mail users can be grouped together into distribution groups or security groups.</span></span>

<span data-ttu-id="7fd52-115">Para obter mais informações sobre o gerenciamento de grupos no EOP, consulte [Gerenciar grupos no EOP](manage-groups-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="7fd52-115">For more information about managing groups in EOP, see [Manage groups in EOP](manage-groups-in-eop.md).</span></span>
