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
description: Saiba como parar o encaminhamento automático de emails criando uma regra de fluxo de emails para evitar o roubo de informações proprietárias.
ms.openlocfilehash: 82e4c80b0edc501889e0fc4dc28f1ec1ad703568
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706469"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="78a5a-103">Parar o encaminhamento automático de email</span><span class="sxs-lookup"><span data-stu-id="78a5a-103">Stop email auto-forward</span></span>

## <a name="watch-stop-auto-forwarding-emails"></a><span data-ttu-id="78a5a-104">Assista: Pare o encaminhamento automático de emails</span><span class="sxs-lookup"><span data-stu-id="78a5a-104">Watch: Stop auto-forwarding emails</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="78a5a-105">Se um hacker tiver acesso à caixa de correio de um usuário, ele poderá encaminhar automaticamente o email do usuário para um endereço externo e roubar informações proprietárias.</span><span class="sxs-lookup"><span data-stu-id="78a5a-105">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="78a5a-106">Você pode parar isso criando uma regra de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="78a5a-106">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="78a5a-107">Experimente!</span><span class="sxs-lookup"><span data-stu-id="78a5a-107">Try it!</span></span>

1. <span data-ttu-id="78a5a-108">No centro Microsoft 365 de administração, selecione **Exchange** **,** fluxo de  email e, na guia regras, selecione o sinal de a mais e escolha criar **uma nova regra**.</span><span class="sxs-lookup"><span data-stu-id="78a5a-108">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="78a5a-109">Selecione **Mais opções**.</span><span class="sxs-lookup"><span data-stu-id="78a5a-109">Select **More options**.</span></span> <span data-ttu-id="78a5a-110">Nomeia sua nova regra.</span><span class="sxs-lookup"><span data-stu-id="78a5a-110">Name your new rule.</span></span>
1. <span data-ttu-id="78a5a-111">Em seguida, abra o drop-down para **aplicar essa regra se**, selecione o **remetente** e, em seguida, é **interno externo**.</span><span class="sxs-lookup"><span data-stu-id="78a5a-111">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="78a5a-112">Selecione **Dentro da organização** e, em seguida, **OK**.</span><span class="sxs-lookup"><span data-stu-id="78a5a-112">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="78a5a-113">Escolha **adicionar condição,** abra o drop-down, selecione As propriedades **da mensagem**, inclua o tipo de **mensagem**.</span><span class="sxs-lookup"><span data-stu-id="78a5a-113">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="78a5a-114">Abra o **drop-down selecionar tipo** de mensagem, escolha Encaminhar **automaticamente**, em **seguida, OK**.</span><span class="sxs-lookup"><span data-stu-id="78a5a-114">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="78a5a-115">Abra o **drop-down Fazer o** seguinte, selecione Bloquear **a** mensagem , rejeitar a mensagem e incluir **uma explicação**.</span><span class="sxs-lookup"><span data-stu-id="78a5a-115">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="78a5a-116">Insira o texto da mensagem para sua explicação e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="78a5a-116">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="78a5a-117">Role até a parte inferior e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="78a5a-117">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="78a5a-118">Sua regra foi criada e os hackers não poderão mais encaminhar mensagens automaticamente.</span><span class="sxs-lookup"><span data-stu-id="78a5a-118">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>

## <a name="related-content"></a><span data-ttu-id="78a5a-119">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="78a5a-119">Related content</span></span>

<span data-ttu-id="78a5a-120">[Adicionar outro alias de email para um usuário](../admin/email/add-another-email-alias-for-a-user.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="78a5a-120">[Add another email alias for a user](../admin/email/add-another-email-alias-for-a-user.md) (article)</span></span>\
<span data-ttu-id="78a5a-121">[Configurar o encaminhamento de email no Microsoft 365](../admin/email/configure-email-forwarding.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="78a5a-121">[Configure email forwarding in Microsoft 365](../admin/email/configure-email-forwarding.md) (article)</span></span>\
<span data-ttu-id="78a5a-122">[Encontrar e corrigir problemas de entrega de email como um Office 365 para administradores](/exchange/troubleshoot/email-delivery/email-delivery-issues) de negócios (artigo)</span><span class="sxs-lookup"><span data-stu-id="78a5a-122">[Find and fix email delivery issues as an Office 365 for business admin](/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)</span></span>