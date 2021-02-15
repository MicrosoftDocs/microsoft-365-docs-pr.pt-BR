---
title: Parar de encaminhar e-mails automaticamente
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como parar o encaminhamento automático de emails.
ms.openlocfilehash: ebbe37ab5c4a60c6ac4b6ebf8877247199460fa1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925881"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="87da7-103">Parar o encaminhamento automático de emails</span><span class="sxs-lookup"><span data-stu-id="87da7-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="87da7-104">Se um hacker ganha acesso à caixa de correio de um usuário, ele pode encaminhar automaticamente o email do usuário para um endereço externo e roubar informações proprietárias.</span><span class="sxs-lookup"><span data-stu-id="87da7-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="87da7-105">Você pode parar isso criando uma regra de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="87da7-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="87da7-106">Experimente!</span><span class="sxs-lookup"><span data-stu-id="87da7-106">Try it!</span></span>

1. <span data-ttu-id="87da7-107">No centro de administração do Microsoft 365, selecione  **Exchange** **,** fluxo de emails e, na guia regras, selecione o sinal de a mais e escolha criar uma **nova regra.**</span><span class="sxs-lookup"><span data-stu-id="87da7-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="87da7-108">Selecione **Mais opções**.</span><span class="sxs-lookup"><span data-stu-id="87da7-108">Select **More options**.</span></span> <span data-ttu-id="87da7-109">Nome da nova regra.</span><span class="sxs-lookup"><span data-stu-id="87da7-109">Name your new rule.</span></span>
1. <span data-ttu-id="87da7-110">Em seguida, abra o drop-down para **aplicar essa regra se**, selecione **o** remetente e, em **seguida, é interno externo**.</span><span class="sxs-lookup"><span data-stu-id="87da7-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="87da7-111">Selecione **Dentro da organização** e, em seguida, **OK**.</span><span class="sxs-lookup"><span data-stu-id="87da7-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="87da7-112">Choose **add condition**, open the drop-down, select The message **properties**, then include the **message type**.</span><span class="sxs-lookup"><span data-stu-id="87da7-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="87da7-113">Abra o **drop-down selecionar** tipo de mensagem, escolha **Encaminhar automaticamente** e **OK**.</span><span class="sxs-lookup"><span data-stu-id="87da7-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="87da7-114">Abra o **drop-down Fazer** o seguinte, selecione Bloquear a **mensagem** e, em seguida, rejeite a mensagem e inclua **uma explicação.**</span><span class="sxs-lookup"><span data-stu-id="87da7-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="87da7-115">Insira o texto da mensagem para a explicação e selecione **OK.**</span><span class="sxs-lookup"><span data-stu-id="87da7-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="87da7-116">Role até a parte inferior e selecione **Salvar.**</span><span class="sxs-lookup"><span data-stu-id="87da7-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="87da7-117">Sua regra foi criada, e os hackers não poderão mais encaminhar mensagens automaticamente.</span><span class="sxs-lookup"><span data-stu-id="87da7-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>