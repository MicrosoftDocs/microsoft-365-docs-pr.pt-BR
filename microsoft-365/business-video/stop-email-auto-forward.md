---
title: Parar de encaminhar e-mails automaticamente
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Saiba como parar o encaminhamento automático de emails.
ms.openlocfilehash: b6715cfdf8622521d977e0746cb9a340a8f70a5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578598"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="d605a-103">Parar o encaminhamento automático de email</span><span class="sxs-lookup"><span data-stu-id="d605a-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="d605a-104">Se um hacker tiver acesso à caixa de correio de um usuário, ele poderá encaminhar automaticamente o email do usuário para um endereço externo e roubar informações proprietárias.</span><span class="sxs-lookup"><span data-stu-id="d605a-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="d605a-105">Você pode parar isso criando uma regra de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="d605a-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="d605a-106">Experimente!</span><span class="sxs-lookup"><span data-stu-id="d605a-106">Try it!</span></span>

1. <span data-ttu-id="d605a-107">No Centro de administração do Microsoft 365, selecione  **Exchange**, **fluxo** de emails e, na guia regras, selecione o sinal de a mais e escolha **criar uma nova regra**.</span><span class="sxs-lookup"><span data-stu-id="d605a-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="d605a-108">Selecione **Mais opções**.</span><span class="sxs-lookup"><span data-stu-id="d605a-108">Select **More options**.</span></span> <span data-ttu-id="d605a-109">Nomeia sua nova regra.</span><span class="sxs-lookup"><span data-stu-id="d605a-109">Name your new rule.</span></span>
1. <span data-ttu-id="d605a-110">Em seguida, abra o drop-down para **aplicar essa regra se**, selecione o **remetente** e, em seguida, é **interno externo**.</span><span class="sxs-lookup"><span data-stu-id="d605a-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="d605a-111">Selecione **Dentro da organização** e, em seguida, **OK**.</span><span class="sxs-lookup"><span data-stu-id="d605a-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="d605a-112">Escolha **adicionar condição,** abra o drop-down, selecione As propriedades **da mensagem**, inclua o tipo de **mensagem**.</span><span class="sxs-lookup"><span data-stu-id="d605a-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="d605a-113">Abra o **drop-down selecionar tipo** de mensagem, escolha Encaminhar **automaticamente**, em **seguida, OK**.</span><span class="sxs-lookup"><span data-stu-id="d605a-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="d605a-114">Abra o **drop-down Fazer o** seguinte, selecione Bloquear **a** mensagem , rejeitar a mensagem e incluir **uma explicação**.</span><span class="sxs-lookup"><span data-stu-id="d605a-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="d605a-115">Insira o texto da mensagem para sua explicação e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d605a-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="d605a-116">Role até a parte inferior e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d605a-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="d605a-117">Sua regra foi criada e os hackers não poderão mais encaminhar mensagens automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d605a-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>