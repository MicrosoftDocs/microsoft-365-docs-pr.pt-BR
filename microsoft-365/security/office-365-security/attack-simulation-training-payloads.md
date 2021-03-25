---
title: Criar uma carga para treinamento de simulação de ataque
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os administradores podem aprender a criar cargas personalizadas para treinamento de simulação de ataque no Microsoft Defender para Office 365.
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51202956"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="e2de3-103">Criar um conteúdo personalizado para treinamento de simulação de Ataque</span><span class="sxs-lookup"><span data-stu-id="e2de3-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="e2de3-104">A Microsoft oferece um catálogo de carga robusto para várias técnicas de engenharia social para emparelhar com seu treinamento de simulação de ataque.</span><span class="sxs-lookup"><span data-stu-id="e2de3-104">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="e2de3-105">No entanto, talvez você queira criar cargas personalizadas que funcionarão melhor para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e2de3-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="e2de3-106">Este artigo descreve como criar uma carga no treinamento de simulação de ataque no Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2de3-106">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="e2de3-107">Você pode criar uma carga clicando em **Criar** uma carga na guia Carga [ **dedicada**](https://security.microsoft.com/attacksimulator?viewid=payload) ou no assistente de criação [de simulação.](attack-simulation-training.md#selecting-a-payload)</span><span class="sxs-lookup"><span data-stu-id="e2de3-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="e2de3-108">A primeira etapa do assistente fará com que você selecione um tipo de carga.</span><span class="sxs-lookup"><span data-stu-id="e2de3-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="e2de3-109">**Atualmente, somente o email está disponível**.</span><span class="sxs-lookup"><span data-stu-id="e2de3-109">**Currently, only email is available**.</span></span>

<span data-ttu-id="e2de3-110">Em seguida, selecione uma técnica associada.</span><span class="sxs-lookup"><span data-stu-id="e2de3-110">Next, select an associated technique.</span></span> <span data-ttu-id="e2de3-111">Confira mais detalhes sobre técnicas em [Selecionar uma técnica de engenharia social.](attack-simulation-training.md#selecting-a-social-engineering-technique)</span><span class="sxs-lookup"><span data-stu-id="e2de3-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="e2de3-112">Na próxima etapa, nomee sua carga.</span><span class="sxs-lookup"><span data-stu-id="e2de3-112">In the next step name your payload.</span></span> <span data-ttu-id="e2de3-113">Opcionalmente, você pode dar uma descrição.</span><span class="sxs-lookup"><span data-stu-id="e2de3-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="e2de3-114">Configurar carga</span><span class="sxs-lookup"><span data-stu-id="e2de3-114">Configure payload</span></span>

<span data-ttu-id="e2de3-115">Agora é hora de criar sua carga.</span><span class="sxs-lookup"><span data-stu-id="e2de3-115">Now it's time to build your payload.</span></span> <span data-ttu-id="e2de3-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span><span class="sxs-lookup"><span data-stu-id="e2de3-116">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="e2de3-117">Escolha uma URL de phishing na lista fornecida.</span><span class="sxs-lookup"><span data-stu-id="e2de3-117">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="e2de3-118">Essa URL será inserida posteriormente no corpo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="e2de3-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="e2de3-119">Você pode escolher um email interno para o remetente da carga, o que fará com que a carga apareça como proveniente de outro funcionário da empresa.</span><span class="sxs-lookup"><span data-stu-id="e2de3-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="e2de3-120">Isso aumentará a suscetibilidade à carga e ajudará a instruir os funcionários sobre o risco de ameaças internas.</span><span class="sxs-lookup"><span data-stu-id="e2de3-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="e2de3-121">Um editor de texto rico está disponível para criar sua carga.</span><span class="sxs-lookup"><span data-stu-id="e2de3-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="e2de3-122">Você também pode importar um email que você criou antecipadamente.</span><span class="sxs-lookup"><span data-stu-id="e2de3-122">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="e2de3-123">Ao criar o corpo do email, aproveite as **marcas** dinâmicas para personalizar o email para seus destinos.</span><span class="sxs-lookup"><span data-stu-id="e2de3-123">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="e2de3-124">Clique **em Link de phishing** para adicionar a URL de phishing selecionada anteriormente ao corpo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="e2de3-124">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Link de phishing e marcas dinâmicas realçadas na criação de carga para o Microsoft Defender para Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="e2de3-126">Para economizar tempo, alterne a opção para substituir todos os links na mensagem **de email pelo link de phishing**.</span><span class="sxs-lookup"><span data-stu-id="e2de3-126">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="e2de3-127">Depois de terminar de criar a carga ao seu gosto, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="e2de3-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="e2de3-128">Adicionando indicadores</span><span class="sxs-lookup"><span data-stu-id="e2de3-128">Adding indicators</span></span>

<span data-ttu-id="e2de3-129">Os indicadores ajudarão os funcionários que passam pela simulação de ataque a entender a dica que podem procurar em ataques futuros.</span><span class="sxs-lookup"><span data-stu-id="e2de3-129">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="e2de3-130">Para iniciar, clique em **Adicionar indicador**.</span><span class="sxs-lookup"><span data-stu-id="e2de3-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="e2de3-131">Selecione um indicador que você gostaria de usar na listada.</span><span class="sxs-lookup"><span data-stu-id="e2de3-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="e2de3-132">Essa lista é curada para conter as pistas mais comuns que aparecem em mensagens de email de phishing.</span><span class="sxs-lookup"><span data-stu-id="e2de3-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="e2de3-133">Depois de selecionado, certifique-se de que o posicionamento do indicador está definido como Do corpo do **email e** clique em Selecionar **texto**.</span><span class="sxs-lookup"><span data-stu-id="e2de3-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="e2de3-134">Realça a parte da carga em que esse indicador aparece e clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="e2de3-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Texto realçado no corpo da mensagem para adicionar a um indicador no treinamento de simulação de ataque](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="e2de3-136">Adicione uma descrição personalizada para descrever o indicador e clique no quadro de visualização do indicador para ver uma visualização do indicador.</span><span class="sxs-lookup"><span data-stu-id="e2de3-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="e2de3-137">Depois de terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="e2de3-137">Once done, click **Add**.</span></span> <span data-ttu-id="e2de3-138">Repita estas etapas até que você tenha abordado todos os indicadores em sua carga.</span><span class="sxs-lookup"><span data-stu-id="e2de3-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="e2de3-139">Analisar carga</span><span class="sxs-lookup"><span data-stu-id="e2de3-139">Review payload</span></span>

<span data-ttu-id="e2de3-140">Você terminou de criar sua carga.</span><span class="sxs-lookup"><span data-stu-id="e2de3-140">You're done building your payload.</span></span> <span data-ttu-id="e2de3-141">Agora é hora de revisar os detalhes e ver uma visualização de sua carga.</span><span class="sxs-lookup"><span data-stu-id="e2de3-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="e2de3-142">A visualização incluirá todos os indicadores que você criou.</span><span class="sxs-lookup"><span data-stu-id="e2de3-142">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="e2de3-143">Você pode editar cada parte da carga nesta etapa.</span><span class="sxs-lookup"><span data-stu-id="e2de3-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="e2de3-144">Depois de satisfeito, você pode **Enviar** sua carga.</span><span class="sxs-lookup"><span data-stu-id="e2de3-144">Once satisfied, you can **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2de3-145">As cargas que você criou terão **Tenant** como fonte.</span><span class="sxs-lookup"><span data-stu-id="e2de3-145">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="e2de3-146">Ao selecionar cargas, certifique-se de não filtrar **Tenant**.</span><span class="sxs-lookup"><span data-stu-id="e2de3-146">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="e2de3-147">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="e2de3-147">Related links</span></span>

[<span data-ttu-id="e2de3-148">Começar a usar o Treinamento de simulação de ataque</span><span class="sxs-lookup"><span data-stu-id="e2de3-148">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="e2de3-149">Criar uma simulação de ataque de phishing</span><span class="sxs-lookup"><span data-stu-id="e2de3-149">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="e2de3-150">Obter insights por meio do treinamento de simulação de Ataque</span><span class="sxs-lookup"><span data-stu-id="e2de3-150">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
