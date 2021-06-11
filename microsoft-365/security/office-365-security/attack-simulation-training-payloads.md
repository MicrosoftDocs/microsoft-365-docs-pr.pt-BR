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
ms.openlocfilehash: ac7963b71c466e8dfdc513a2563776cd4e10af95
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878755"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="30756-103">Criar um conteúdo personalizado para treinamento de simulação de Ataque</span><span class="sxs-lookup"><span data-stu-id="30756-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="30756-104">**Aplica-se ao** [Microsoft Defender para Office 365 plano 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="30756-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="30756-105">A Microsoft oferece um catálogo de carga robusto para várias técnicas de engenharia social para emparelhar com seu treinamento de simulação de ataque.</span><span class="sxs-lookup"><span data-stu-id="30756-105">Microsoft offers a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="30756-106">No entanto, talvez você queira criar cargas personalizadas que funcionarão melhor para sua organização.</span><span class="sxs-lookup"><span data-stu-id="30756-106">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="30756-107">Este artigo descreve como criar uma carga no treinamento de simulação de ataque no Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="30756-107">This article describes how to create a payload in Attack simulation training in Microsoft Defender for Office 365.</span></span>

<span data-ttu-id="30756-108">Você pode criar uma carga clicando em **Criar** uma carga na guia Carga [ **dedicada**](https://security.microsoft.com/attacksimulator?viewid=payload) ou no assistente de criação [de simulação.](attack-simulation-training.md#selecting-a-payload)</span><span class="sxs-lookup"><span data-stu-id="30756-108">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="30756-109">A primeira etapa do assistente fará com que você selecione um tipo de carga.</span><span class="sxs-lookup"><span data-stu-id="30756-109">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="30756-110">**Atualmente, somente o email está disponível**.</span><span class="sxs-lookup"><span data-stu-id="30756-110">**Currently, only email is available**.</span></span>

<span data-ttu-id="30756-111">Em seguida, selecione uma técnica associada.</span><span class="sxs-lookup"><span data-stu-id="30756-111">Next, select an associated technique.</span></span> <span data-ttu-id="30756-112">Confira mais detalhes sobre técnicas em [Selecionar uma técnica de engenharia social.](attack-simulation-training.md#selecting-a-social-engineering-technique)</span><span class="sxs-lookup"><span data-stu-id="30756-112">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="30756-113">Na próxima etapa, nomee sua carga.</span><span class="sxs-lookup"><span data-stu-id="30756-113">In the next step name your payload.</span></span> <span data-ttu-id="30756-114">Opcionalmente, você pode dar uma descrição.</span><span class="sxs-lookup"><span data-stu-id="30756-114">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="30756-115">Configurar carga</span><span class="sxs-lookup"><span data-stu-id="30756-115">Configure payload</span></span>

<span data-ttu-id="30756-116">Agora é hora de criar sua carga.</span><span class="sxs-lookup"><span data-stu-id="30756-116">Now it's time to build your payload.</span></span> <span data-ttu-id="30756-117">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span><span class="sxs-lookup"><span data-stu-id="30756-117">Input the sender's name, email address, and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="30756-118">Escolha uma URL de phishing na lista fornecida.</span><span class="sxs-lookup"><span data-stu-id="30756-118">Pick a phishing URL from the provided list.</span></span> <span data-ttu-id="30756-119">Essa URL será inserida posteriormente no corpo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="30756-119">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="30756-120">Você pode escolher um email interno para o remetente da carga, o que fará com que a carga apareça como proveniente de outro funcionário da empresa.</span><span class="sxs-lookup"><span data-stu-id="30756-120">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="30756-121">Isso aumentará a suscetibilidade à carga e ajudará a instruir os funcionários sobre o risco de ameaças internas.</span><span class="sxs-lookup"><span data-stu-id="30756-121">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="30756-122">Um editor de texto rico está disponível para criar sua carga.</span><span class="sxs-lookup"><span data-stu-id="30756-122">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="30756-123">Você também pode importar um email que você criou antecipadamente.</span><span class="sxs-lookup"><span data-stu-id="30756-123">You can also import an email that you've created beforehand.</span></span> <span data-ttu-id="30756-124">Ao criar o corpo do email, aproveite as **marcas** dinâmicas para personalizar o email para seus destinos.</span><span class="sxs-lookup"><span data-stu-id="30756-124">As you create the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="30756-125">Clique **em Link de phishing** para adicionar a URL de phishing selecionada anteriormente ao corpo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="30756-125">Click **Phishing link** to add the previously selected phishing URL into the body of the message.</span></span>

![Link de phishing e marcas dinâmicas realçadas na criação de carga para o Microsoft Defender para Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="30756-127">Para economizar tempo, alterne a opção para substituir todos os links na mensagem **de email pelo link de phishing**.</span><span class="sxs-lookup"><span data-stu-id="30756-127">To save time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="30756-128">Depois de terminar de criar a carga ao seu gosto, clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="30756-128">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="30756-129">Adicionando indicadores</span><span class="sxs-lookup"><span data-stu-id="30756-129">Adding indicators</span></span>

<span data-ttu-id="30756-130">Os indicadores ajudarão os funcionários que passam pela simulação de ataque a entender a dica que podem procurar em ataques futuros.</span><span class="sxs-lookup"><span data-stu-id="30756-130">Indicators will help employees going through the attack simulation understand the clue they can look for in future attacks.</span></span> <span data-ttu-id="30756-131">Para iniciar, clique em **Adicionar indicador**.</span><span class="sxs-lookup"><span data-stu-id="30756-131">To start, click **Add indicator**.</span></span>

<span data-ttu-id="30756-132">Selecione um indicador que você gostaria de usar na listada.</span><span class="sxs-lookup"><span data-stu-id="30756-132">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="30756-133">Essa lista é curada para conter as pistas mais comuns que aparecem em mensagens de email de phishing.</span><span class="sxs-lookup"><span data-stu-id="30756-133">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="30756-134">Depois de selecionado, certifique-se de que o posicionamento do indicador está definido como Do corpo do **email e** clique em Selecionar **texto**.</span><span class="sxs-lookup"><span data-stu-id="30756-134">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="30756-135">Realça a parte da carga em que esse indicador aparece e clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="30756-135">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Texto realçado no corpo da mensagem para adicionar a um indicador no treinamento de simulação de ataque](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="30756-137">Adicione uma descrição personalizada para descrever o indicador e clique no quadro de visualização do indicador para ver uma visualização do indicador.</span><span class="sxs-lookup"><span data-stu-id="30756-137">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="30756-138">Depois de terminar, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="30756-138">Once done, click **Add**.</span></span> <span data-ttu-id="30756-139">Repita estas etapas até que você tenha abordado todos os indicadores em sua carga.</span><span class="sxs-lookup"><span data-stu-id="30756-139">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="30756-140">Analisar carga</span><span class="sxs-lookup"><span data-stu-id="30756-140">Review payload</span></span>

<span data-ttu-id="30756-141">Você terminou de criar sua carga.</span><span class="sxs-lookup"><span data-stu-id="30756-141">You're done building your payload.</span></span> <span data-ttu-id="30756-142">Agora é hora de revisar os detalhes e ver uma visualização de sua carga.</span><span class="sxs-lookup"><span data-stu-id="30756-142">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="30756-143">A visualização incluirá todos os indicadores que você criou.</span><span class="sxs-lookup"><span data-stu-id="30756-143">The preview will include all indicators that you've created.</span></span> <span data-ttu-id="30756-144">Você pode editar cada parte da carga nesta etapa.</span><span class="sxs-lookup"><span data-stu-id="30756-144">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="30756-145">Depois de satisfeito, você pode **Enviar** sua carga.</span><span class="sxs-lookup"><span data-stu-id="30756-145">Once satisfied, you can **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30756-146">As cargas que você criou terão **Tenant** como fonte.</span><span class="sxs-lookup"><span data-stu-id="30756-146">Payloads that you've created will have **Tenant** as their source.</span></span> <span data-ttu-id="30756-147">Ao selecionar cargas, certifique-se de não filtrar **Tenant**.</span><span class="sxs-lookup"><span data-stu-id="30756-147">When selecting payloads, make sure that you don't filter out **Tenant**.</span></span>

## <a name="related-links"></a><span data-ttu-id="30756-148">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="30756-148">Related links</span></span>

[<span data-ttu-id="30756-149">Começar a usar o Treinamento de simulação de ataque</span><span class="sxs-lookup"><span data-stu-id="30756-149">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="30756-150">Criar uma simulação de ataque de phishing</span><span class="sxs-lookup"><span data-stu-id="30756-150">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="30756-151">Obter insights por meio do treinamento de simulação de Ataque</span><span class="sxs-lookup"><span data-stu-id="30756-151">Gain insights through Attack simulation training</span></span>](attack-simulation-training-insights.md)
