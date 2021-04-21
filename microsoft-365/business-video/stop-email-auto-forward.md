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
ms.openlocfilehash: f8bd599c7c8bca8d4789188acbcd3574b7473dcb
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903677"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="6084c-103">Parar o encaminhamento automático de email</span><span class="sxs-lookup"><span data-stu-id="6084c-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="6084c-104">Se um hacker tiver acesso à caixa de correio de um usuário, ele poderá encaminhar automaticamente o email do usuário para um endereço externo e roubar informações proprietárias.</span><span class="sxs-lookup"><span data-stu-id="6084c-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="6084c-105">Você pode parar isso criando uma regra de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="6084c-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="6084c-106">Experimente!</span><span class="sxs-lookup"><span data-stu-id="6084c-106">Try it!</span></span>

1. <span data-ttu-id="6084c-107">No Centro de administração do Microsoft 365, selecione  **Exchange**, **fluxo** de emails e, na guia regras, selecione o sinal de a mais e escolha **criar uma nova regra**.</span><span class="sxs-lookup"><span data-stu-id="6084c-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="6084c-108">Selecione **Mais opções**.</span><span class="sxs-lookup"><span data-stu-id="6084c-108">Select **More options**.</span></span> <span data-ttu-id="6084c-109">Nomeia sua nova regra.</span><span class="sxs-lookup"><span data-stu-id="6084c-109">Name your new rule.</span></span>
1. <span data-ttu-id="6084c-110">Em seguida, abra o drop-down para **aplicar essa regra se**, selecione o **remetente** e, em seguida, é **interno externo**.</span><span class="sxs-lookup"><span data-stu-id="6084c-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="6084c-111">Selecione **Dentro da organização** e, em seguida, **OK**.</span><span class="sxs-lookup"><span data-stu-id="6084c-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="6084c-112">Escolha **adicionar condição,** abra o drop-down, selecione As propriedades **da mensagem**, inclua o tipo de **mensagem**.</span><span class="sxs-lookup"><span data-stu-id="6084c-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="6084c-113">Abra o **drop-down selecionar tipo** de mensagem, escolha Encaminhar **automaticamente**, em **seguida, OK**.</span><span class="sxs-lookup"><span data-stu-id="6084c-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="6084c-114">Abra o **drop-down Fazer o** seguinte, selecione Bloquear **a** mensagem , rejeitar a mensagem e incluir **uma explicação**.</span><span class="sxs-lookup"><span data-stu-id="6084c-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="6084c-115">Insira o texto da mensagem para sua explicação e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="6084c-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="6084c-116">Role até a parte inferior e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6084c-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="6084c-117">Sua regra foi criada e os hackers não poderão mais encaminhar mensagens automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6084c-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>

## <a name="related-content"></a><span data-ttu-id="6084c-118">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="6084c-118">Related content</span></span>

<span data-ttu-id="6084c-119">[Adicionar outro alias de email para](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) um usuário (artigo) Configure email [forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) (article) [Find and fix email delivery issues as an Office 365 for business admin](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)</span><span class="sxs-lookup"><span data-stu-id="6084c-119">[Add another email alias for a user](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) (article) [Configure email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) (article) [Find and fix email delivery issues as an Office 365 for business admin](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)</span></span>