---
title: Criar uma assinatura para toda a empresa
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
description: Saiba como criar uma assinatura de email em toda a empresa.
ms.openlocfilehash: 64c269abd25cab74ec5b0836975902e46a611c8c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701530"
---
# <a name="create-a-company-wide-email-signature"></a><span data-ttu-id="c8074-103">Criar uma assinatura de email em toda a empresa</span><span class="sxs-lookup"><span data-stu-id="c8074-103">Create a company-wide email signature</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf?autoplay=false]

<span data-ttu-id="c8074-104">Uma assinatura de email em toda a empresa é exibida em todos os emails enviados por pessoas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c8074-104">A company-wide email signature appears on every email sent by people in your organization.</span></span> <span data-ttu-id="c8074-105">Você pode usá-lo para exibir detalhes importantes, como as informações de contato da sua empresa ou um aviso de isenção de responsabilidade legal.</span><span class="sxs-lookup"><span data-stu-id="c8074-105">You can use it to display important details, like your company contact information or a legal disclaimer.</span></span> 

## <a name="try-it"></a><span data-ttu-id="c8074-106">Experimente!</span><span class="sxs-lookup"><span data-stu-id="c8074-106">Try it!</span></span>

1. <span data-ttu-id="c8074-107">No centro de administração do Microsoft 365, selecione **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="c8074-107">In the Microsoft 365 admin center, select **Exchange**.</span></span>
1. <span data-ttu-id="c8074-108">Selecione **fluxo de emails**.</span><span class="sxs-lookup"><span data-stu-id="c8074-108">Select **Mail flow**.</span></span>
1. <span data-ttu-id="c8074-109">Selecione **Adicionar +** e, em seguida, selecione **aplicar avisos de isenção de responsabilidade**.</span><span class="sxs-lookup"><span data-stu-id="c8074-109">Select **Add +**, and then select **Apply disclaimers**.</span></span>
1. <span data-ttu-id="c8074-110">Na página **nova regra** :</span><span class="sxs-lookup"><span data-stu-id="c8074-110">On the **New rule** page:</span></span>
    1. <span data-ttu-id="c8074-111">Insira um nome para a regra.</span><span class="sxs-lookup"><span data-stu-id="c8074-111">Enter a name for the rule.</span></span>
    1. <span data-ttu-id="c8074-112">Na lista suspensa **aplicar esta regra se** , selecione **aplicar a todas as mensagens**.</span><span class="sxs-lookup"><span data-stu-id="c8074-112">From the **Apply this rule if** drop-down list, select **Apply to all messages**.</span></span>
    1. <span data-ttu-id="c8074-113">Na lista suspensa **fazer o seguinte** , verifique se **anexar o aviso de isenção de responsabilidade** é exibido.</span><span class="sxs-lookup"><span data-stu-id="c8074-113">In the **Do the following** drop-down list, verify that **Append the disclaimer** is displayed.</span></span>
    1. <span data-ttu-id="c8074-114">No lado direito da página, selecione **Inserir texto** e digite o texto da sua assinatura de email na caixa de texto **especificar aviso de isenção de responsabilidade** .</span><span class="sxs-lookup"><span data-stu-id="c8074-114">On the right side of the page, select **Enter text**, and then enter the text for your email signature in the **Specify disclaimer** text box.</span></span> <span data-ttu-id="c8074-115">Você pode melhorar a aparência da sua assinatura Formatando o texto com HTML.</span><span class="sxs-lookup"><span data-stu-id="c8074-115">You can improve the look of your signature by formatting the text with HTML.</span></span>
    1. <span data-ttu-id="c8074-116">Se quiser que uma imagem apareça na assinatura, você precisará usar uma URL disponível publicamente para essa imagem.</span><span class="sxs-lookup"><span data-stu-id="c8074-116">If you want an image to appear in your signature, you'll need to use a publicly available URL for that image.</span></span> <span data-ttu-id="c8074-117">Navegue até a imagem na Web, clique com o botão direito do mouse e selecione **copiar endereço da imagem**.</span><span class="sxs-lookup"><span data-stu-id="c8074-117">Browse to the image on the web, right-click it, and select **Copy image address**.</span></span> <span data-ttu-id="c8074-118">Cole o endereço na caixa de texto **especificar aviso de isenção de responsabilidade** .</span><span class="sxs-lookup"><span data-stu-id="c8074-118">Paste the address into the **Specify disclaimer** text box.</span></span> <span data-ttu-id="c8074-119">Selecione **OK** e role para baixo.</span><span class="sxs-lookup"><span data-stu-id="c8074-119">Select **OK**, then scroll down.</span></span>
    1. <span data-ttu-id="c8074-120">Para certificar-se de que a assinatura funciona com emails criptografados, adicione uma opção de fallback.</span><span class="sxs-lookup"><span data-stu-id="c8074-120">To make sure the signature works with encrypted emails, add a fallback option.</span></span> <span data-ttu-id="c8074-121">No lado direito da página, escolha **selecionar um**, escolha **quebrar** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8074-121">On the right of the page, choose **Select one**, choose **Wrap**, and then select **OK**.</span></span>
    1. <span data-ttu-id="c8074-122">Role para baixo e deixe o modo definido para **impor** e, em seguida, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="c8074-122">Scroll down and leave the mode set to **Enforce**, and then select **Save**.</span></span>
1. <span data-ttu-id="c8074-123">Uma mensagem de aviso será exibida.</span><span class="sxs-lookup"><span data-stu-id="c8074-123">A warning message will appear.</span></span> <span data-ttu-id="c8074-124">Selecione **Sim** para aplicar a regra a todas as mensagens futuras.</span><span class="sxs-lookup"><span data-stu-id="c8074-124">Select **Yes** to apply the rule to all future messages.</span></span>

    <span data-ttu-id="c8074-125">Sua assinatura foi criada.</span><span class="sxs-lookup"><span data-stu-id="c8074-125">Your signature has been created.</span></span> <span data-ttu-id="c8074-126">Ao enviar seu próximo email, você não verá a assinatura que acabou de criar, mas os destinatários de email o verão.</span><span class="sxs-lookup"><span data-stu-id="c8074-126">When you send your next email, you won't see the signature you just created, but the email recipients will see it.</span></span>