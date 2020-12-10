---
title: Criar uma carga para treinamento de simulação de ataque
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Saiba como criar uma carga personalizada para o treinamento de simulação de ataque no Microsoft defender para Office 365.
ms.openlocfilehash: a8366e6cbf703ef1e1a14e216ada71200668cd14
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616267"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a><span data-ttu-id="695e9-103">Criar um conteúdo personalizado para treinamento de simulação de Ataque</span><span class="sxs-lookup"><span data-stu-id="695e9-103">Create a custom payload for Attack simulation training</span></span>

<span data-ttu-id="695e9-104">A Microsoft oferece um catálogo de carga robusto para várias técnicas de engenharia social para emparelhar com seu treinamento de simulação de ataque.</span><span class="sxs-lookup"><span data-stu-id="695e9-104">Microsoft offer a robust payload catalog for various social engineering techniques to pair with your attack simulation training.</span></span> <span data-ttu-id="695e9-105">No entanto, talvez você queira criar cargas personalizadas que funcionem melhor para sua organização.</span><span class="sxs-lookup"><span data-stu-id="695e9-105">However, you might want to create custom payloads that will work better for your organization.</span></span> <span data-ttu-id="695e9-106">O seguinte descreve como criar uma carga no treinamento de simulação de ataque através do Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="695e9-106">The following describes how to create a payload in attack simulation training through Microsoft Defender for Office 365.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="695e9-107">Você pode criar uma carga clicando em **criar uma carga** na [guia **cargas** dedicadas](https://security.microsoft.com/attacksimulator?viewid=payload) ou no [Assistente de criação de simulação](attack-simulation-training.md#selecting-a-payload).</span><span class="sxs-lookup"><span data-stu-id="695e9-107">You can create a payload by clicking on **Create a payload** in either the [dedicated **Payloads** tab](https://security.microsoft.com/attacksimulator?viewid=payload) or within the [simulation creation wizard](attack-simulation-training.md#selecting-a-payload).</span></span>

<span data-ttu-id="695e9-108">A primeira etapa do assistente terá que você selecionar um tipo de carga.</span><span class="sxs-lookup"><span data-stu-id="695e9-108">The first step in the wizard will have you select a payload type.</span></span> <span data-ttu-id="695e9-109">**Atualmente, apenas o email está disponível**.</span><span class="sxs-lookup"><span data-stu-id="695e9-109">**Currently only email is available**.</span></span>

<span data-ttu-id="695e9-110">Em seguida, selecione uma técnica associada.</span><span class="sxs-lookup"><span data-stu-id="695e9-110">Next, select an associated technique.</span></span> <span data-ttu-id="695e9-111">Veja mais detalhes sobre as técnicas na [seleção de uma técnica de engenharia social](attack-simulation-training.md#selecting-a-social-engineering-technique).</span><span class="sxs-lookup"><span data-stu-id="695e9-111">See more details on techniques at [Selecting a social engineering technique](attack-simulation-training.md#selecting-a-social-engineering-technique).</span></span>

<span data-ttu-id="695e9-112">Na próxima etapa, nomeie sua carga.</span><span class="sxs-lookup"><span data-stu-id="695e9-112">In the next step name your payload.</span></span> <span data-ttu-id="695e9-113">Opcionalmente, você pode fornecer uma descrição.</span><span class="sxs-lookup"><span data-stu-id="695e9-113">Optionally, you can give it a description.</span></span>

## <a name="configure-payload"></a><span data-ttu-id="695e9-114">Configurar carga</span><span class="sxs-lookup"><span data-stu-id="695e9-114">Configure payload</span></span>

<span data-ttu-id="695e9-115">Agora é hora de criar sua carga.</span><span class="sxs-lookup"><span data-stu-id="695e9-115">Now it's time to build your payload.</span></span> <span data-ttu-id="695e9-116">Insira o nome do remetente, o email e o assunto do email na seção **detalhes do remetente** .</span><span class="sxs-lookup"><span data-stu-id="695e9-116">Input the sender's name, email and the email's subject in the **Sender details** section.</span></span> <span data-ttu-id="695e9-117">Escolha uma URL de phishing na lista fornecida.</span><span class="sxs-lookup"><span data-stu-id="695e9-117">Pick a phishing URL from the the provided list.</span></span> <span data-ttu-id="695e9-118">Essa URL será incorporada posteriormente ao corpo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="695e9-118">This URL will later be embedded into the body of the message.</span></span>

> [!TIP]
> <span data-ttu-id="695e9-119">Você pode escolher um email interno para o remetente da carga de conteúdo, que fará com que a carga apareça da mesma forma que vem de outro funcionário da empresa.</span><span class="sxs-lookup"><span data-stu-id="695e9-119">You can choose an internal email for your payload's sender, which will make the payload appear as coming from another employee of the company.</span></span> <span data-ttu-id="695e9-120">Isso aumentará o susceptibility da carga e ajudará a educar os funcionários sobre o risco de ameaças internas.</span><span class="sxs-lookup"><span data-stu-id="695e9-120">This will increase susceptibility to the payload and will help educate employees on the risk of internal threats.</span></span>

<span data-ttu-id="695e9-121">Um editor de Rich Text está disponível para criar sua carga.</span><span class="sxs-lookup"><span data-stu-id="695e9-121">A rich text editor is available to create your payload.</span></span> <span data-ttu-id="695e9-122">Você também pode importar um email que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="695e9-122">You can also import an email you've created beforehand.</span></span> <span data-ttu-id="695e9-123">Ao estruturar o corpo do email, aproveite as **marcas dinâmicas** para personalizar o email para seus destinos.</span><span class="sxs-lookup"><span data-stu-id="695e9-123">As you structure the body of the email, take advantage of the **dynamic tags** to personalize the email to your targets.</span></span> <span data-ttu-id="695e9-124">Clique em **link de phishing** para adicionar a URL de phishing selecionada anteriormente ao corpo do email.</span><span class="sxs-lookup"><span data-stu-id="695e9-124">Click on **Phishing link** to add the previously selected phishing URL into the body of the email.</span></span>

![Link de phishing e marcas dinâmicas realçadas na criação de carga para o Microsoft defender para Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> <span data-ttu-id="695e9-126">Para economizar tempo, alterne a opção para **substituir todos os links na mensagem de email pelo link de phishing**.</span><span class="sxs-lookup"><span data-stu-id="695e9-126">To save yourself some time, toggle on the option to **replace all links in the email message with the phishing link**.</span></span>

<span data-ttu-id="695e9-127">Após concluir a criação da carga de preferência, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="695e9-127">Once you're done building the payload to your liking, click **Next**.</span></span>

## <a name="adding-indicators"></a><span data-ttu-id="695e9-128">Adicionar indicadores</span><span class="sxs-lookup"><span data-stu-id="695e9-128">Adding indicators</span></span>

<span data-ttu-id="695e9-129">Os indicadores ajudarão os funcionários a passar pela simulação de ataque entendem o indício de que eles podem procurar em futuros ataques.</span><span class="sxs-lookup"><span data-stu-id="695e9-129">Indicators will help employees going through the attack simulation understand clue they can look for in future attacks.</span></span> <span data-ttu-id="695e9-130">Para começar, clique em **Adicionar indicador**.</span><span class="sxs-lookup"><span data-stu-id="695e9-130">To start, click **Add indicator**.</span></span>

<span data-ttu-id="695e9-131">Selecione um indicador que você gostaria de usar na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="695e9-131">Select an indicator you'd like to use from the drop-down list.</span></span> <span data-ttu-id="695e9-132">Essa lista é organizada para conter as dicas mais comuns que aparecem em mensagens de email de phishing.</span><span class="sxs-lookup"><span data-stu-id="695e9-132">This list is curated to contain the most common clues that appear in phishing email messages.</span></span> <span data-ttu-id="695e9-133">Depois de selecionado, certifique-se de que o posicionamento do indicador está definido para **o corpo do email** e clique em **selecionar texto**.</span><span class="sxs-lookup"><span data-stu-id="695e9-133">Once selected, make sure the indicator placement is set to **From the body of the email** and click on **Select text**.</span></span> <span data-ttu-id="695e9-134">Realce a parte da carga onde esse indicador aparece e clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="695e9-134">Highlight the portion of your payload where this indicator appears and click **Select**.</span></span>

![Texto realçado no corpo da mensagem a ser adicionado a um indicador no treinamento de simulação de ataque](../../media/attack-sim-preview-select-text.png)

<span data-ttu-id="695e9-136">Adicione uma descrição personalizada para descrever o indicador e clique no quadro de visualização do indicador para ver uma visualização do indicador.</span><span class="sxs-lookup"><span data-stu-id="695e9-136">Add a custom description to describe the indicator and click within the indicator preview frame to see a preview of your indicator.</span></span> <span data-ttu-id="695e9-137">Após concluir, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="695e9-137">Once done, click **Add**.</span></span> <span data-ttu-id="695e9-138">Repita essas etapas até que você tenha abordado todos os indicadores em sua carga.</span><span class="sxs-lookup"><span data-stu-id="695e9-138">Repeat these steps until you've covered all indicators in your payload.</span></span>

## <a name="review-payload"></a><span data-ttu-id="695e9-139">Examinar carga</span><span class="sxs-lookup"><span data-stu-id="695e9-139">Review payload</span></span>

<span data-ttu-id="695e9-140">Você terminou de criar sua carga.</span><span class="sxs-lookup"><span data-stu-id="695e9-140">You're done building your payload.</span></span> <span data-ttu-id="695e9-141">Agora é hora de revisar os detalhes e ver uma visualização da sua carga.</span><span class="sxs-lookup"><span data-stu-id="695e9-141">Now it's time to review the details and see a preview of your payload.</span></span> <span data-ttu-id="695e9-142">A visualização incluirá todos os indicadores que você criou.</span><span class="sxs-lookup"><span data-stu-id="695e9-142">The preview will include all indicators you've created.</span></span> <span data-ttu-id="695e9-143">Você pode editar cada parte da carga desta etapa.</span><span class="sxs-lookup"><span data-stu-id="695e9-143">You can edit each part of the payload from this step.</span></span> <span data-ttu-id="695e9-144">Depois de satisfeito, **envie** sua carga.</span><span class="sxs-lookup"><span data-stu-id="695e9-144">Once satisfied, **Submit** your payload.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="695e9-145">As cargas que você criou terão o **locatário** definido como sua fonte.</span><span class="sxs-lookup"><span data-stu-id="695e9-145">Payloads you've created will have **Tenant** set as their source.</span></span> <span data-ttu-id="695e9-146">Ao selecionar as cargas, certifique-se de que o **locatário** não foi filtrado.</span><span class="sxs-lookup"><span data-stu-id="695e9-146">When selecting payloads, make sure you don't have **Tenant** filtered out.</span></span>