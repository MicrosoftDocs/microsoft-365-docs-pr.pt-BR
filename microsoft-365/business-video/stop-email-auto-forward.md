---
title: Interromper o encaminhamento automático de emails
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como interromper o encaminhamento automático de emails.
ms.openlocfilehash: 0683e133f6c261dc19cc098b13be298cd8086001
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701449"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="2de98-103">Parar envio automático de email</span><span class="sxs-lookup"><span data-stu-id="2de98-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="2de98-104">Se um hacker obtiver acesso à caixa de correio de um usuário, ele poderá encaminhar automaticamente o email do usuário para um endereço externo e roubar informações proprietárias.</span><span class="sxs-lookup"><span data-stu-id="2de98-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="2de98-105">Você pode parar isso criando uma regra de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="2de98-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="2de98-106">Experimente!</span><span class="sxs-lookup"><span data-stu-id="2de98-106">Try it!</span></span>

1. <span data-ttu-id="2de98-107">No centro de administração do Microsoft 365, selecione **Exchange**, **fluxo de emails** e na guia **regras** , selecione o sinal de adição e escolha **criar uma nova regra**.</span><span class="sxs-lookup"><span data-stu-id="2de98-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="2de98-108">Selecione **Mais opções**.</span><span class="sxs-lookup"><span data-stu-id="2de98-108">Select **More options**.</span></span> <span data-ttu-id="2de98-109">Nomeie sua nova regra.</span><span class="sxs-lookup"><span data-stu-id="2de98-109">Name your new rule.</span></span>
1. <span data-ttu-id="2de98-110">Em seguida, abra o menu suspenso para **aplicar esta regra se**, selecione **o remetente** e, em seguida, **for externo interno**.</span><span class="sxs-lookup"><span data-stu-id="2de98-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="2de98-111">Selecione **dentro da organização** e **OK**.</span><span class="sxs-lookup"><span data-stu-id="2de98-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="2de98-112">Escolha **Adicionar condição**, abra a lista suspensa, selecione **as propriedades da mensagem** e, em seguida, **inclua o tipo de mensagem**.</span><span class="sxs-lookup"><span data-stu-id="2de98-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="2de98-113">Abra a lista suspensa **Selecionar tipo de mensagem** , escolha **Avançar** e **OK**.</span><span class="sxs-lookup"><span data-stu-id="2de98-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="2de98-114">Abra o menu suspenso **fazer o seguinte** , selecione **bloquear a mensagem** e, em seguida, **rejeitar a mensagem e incluir uma explicação**.</span><span class="sxs-lookup"><span data-stu-id="2de98-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="2de98-115">Digite o texto da mensagem para sua explicação e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2de98-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="2de98-116">Role até a parte inferior e selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="2de98-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="2de98-117">Sua regra foi criada e os hackers não poderão mais enviar mensagens automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2de98-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>