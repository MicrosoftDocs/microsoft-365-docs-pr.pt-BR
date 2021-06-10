---
title: Microsoft Defender for Endpoint Flow conector
ms.reviewer: ''
description: Use o Microsoft Defender for Endpoint Flow conector para automatizar a segurança e criar um fluxo que será disparado sempre que um novo alerta ocorrer em seu locatário.
keywords: fluxo, apis com suporte, api, fluxo da Microsoft, consulta, automação
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: a0718f8e3aba27e6fbfc92a4308278f4c629275f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843789"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a><span data-ttu-id="48b6b-104">Microsoft Power Automate (anteriormente Microsoft Flow) e funções do Azure</span><span class="sxs-lookup"><span data-stu-id="48b6b-104">Microsoft Power Automate (formerly Microsoft Flow), and Azure Functions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="48b6b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="48b6b-105">**Applies to:**</span></span>
- [<span data-ttu-id="48b6b-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="48b6b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="48b6b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="48b6b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="48b6b-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="48b6b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="48b6b-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="48b6b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="48b6b-110">Automatizar procedimentos de segurança é um requisito padrão para cada Centro de Operações de Segurança moderno.</span><span class="sxs-lookup"><span data-stu-id="48b6b-110">Automating security procedures is a standard requirement for every modern Security Operations Center.</span></span> <span data-ttu-id="48b6b-111">A falta de defensores cibernéticos profissionais força o SOC a trabalhar da maneira mais eficiente e a automação é uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="48b6b-111">The lack of professional cyber defenders forces SOC to work in the most efficient way and automation is a must.</span></span> <span data-ttu-id="48b6b-112">O Microsoft Power Automate oferece suporte a conectores diferentes que foram construídos exatamente para isso.</span><span class="sxs-lookup"><span data-stu-id="48b6b-112">Microsoft Power Automate supports different connectors that were built exactly for that.</span></span> <span data-ttu-id="48b6b-113">Você pode criar uma automação de procedimento de ponta a ponta em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="48b6b-113">You can build an end-to-end procedure automation within a few minutes.</span></span>

<span data-ttu-id="48b6b-114">A API do Microsoft Defender tem um conector Flow oficial com muitos recursos.</span><span class="sxs-lookup"><span data-stu-id="48b6b-114">Microsoft Defender API has an official Flow Connector with many capabilities.</span></span>

![Imagem de credenciais de edição1](images/api-flow-0.png)

> [!NOTE]
> <span data-ttu-id="48b6b-116">Para obter mais detalhes sobre os pré-requisitos de licenciamento de conectores premium, consulte [Licensing for premium connectors](/power-automate/triggers-introduction#licensing-for-premium-connectors).</span><span class="sxs-lookup"><span data-stu-id="48b6b-116">For more details about premium connectors licensing prerequisites, see [Licensing for premium connectors](/power-automate/triggers-introduction#licensing-for-premium-connectors).</span></span>


## <a name="usage-example"></a><span data-ttu-id="48b6b-117">Exemplo de uso</span><span class="sxs-lookup"><span data-stu-id="48b6b-117">Usage example</span></span>

<span data-ttu-id="48b6b-118">O exemplo a seguir demonstra como criar uma Flow que é disparada sempre que um novo Alerta ocorre em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="48b6b-118">The following example demonstrates how to create a Flow that is triggered any time a new Alert occurs on your tenant.</span></span>

1. <span data-ttu-id="48b6b-119">Faça logoff [no Microsoft Power Automate](https://flow.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="48b6b-119">Log in to [Microsoft Power Automate](https://flow.microsoft.com).</span></span>

2. <span data-ttu-id="48b6b-120">Vá para **Meus fluxos**  >    >  **New Automated-from em branco**.</span><span class="sxs-lookup"><span data-stu-id="48b6b-120">Go to **My flows** > **New** > **Automated-from blank**.</span></span>

    ![Imagem de credenciais de edição2](images/api-flow-1.png)

3. <span data-ttu-id="48b6b-122">Escolha um nome para sua Flow, procure "Microsoft Defender ATP Gatilhos" como o gatilho e selecione o novo gatilho Alertas.</span><span class="sxs-lookup"><span data-stu-id="48b6b-122">Choose a name for your Flow, search for "Microsoft Defender ATP Triggers" as the trigger, and then select the new Alerts trigger.</span></span>

    ![Imagem de credenciais de edição3](images/api-flow-2.png)

<span data-ttu-id="48b6b-124">Agora você tem uma Flow que é disparada sempre que um novo Alerta ocorre.</span><span class="sxs-lookup"><span data-stu-id="48b6b-124">Now you have a Flow that is triggered every time a new Alert occurs.</span></span>

![Imagem de credenciais de edição4](images/api-flow-3.png)

<span data-ttu-id="48b6b-126">Tudo o que você precisa fazer agora é escolher suas próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="48b6b-126">All you need to do now is choose your next steps.</span></span>
<span data-ttu-id="48b6b-127">Por exemplo, você pode isolar o dispositivo se a Gravidade do Alerta for Alta e enviar um email sobre ele.</span><span class="sxs-lookup"><span data-stu-id="48b6b-127">For example, you can isolate the device if the Severity of the Alert is High and send an email about it.</span></span>
<span data-ttu-id="48b6b-128">O gatilho Alerta fornece apenas a ID do Alerta e a ID do Computador.</span><span class="sxs-lookup"><span data-stu-id="48b6b-128">The Alert trigger provides only the Alert ID and the Machine ID.</span></span> <span data-ttu-id="48b6b-129">Você pode usar o conector para expandir essas entidades.</span><span class="sxs-lookup"><span data-stu-id="48b6b-129">You can use the connector to expand these entities.</span></span>

### <a name="get-the-alert-entity-using-the-connector"></a><span data-ttu-id="48b6b-130">Obter a entidade Alert usando o conector</span><span class="sxs-lookup"><span data-stu-id="48b6b-130">Get the Alert entity using the connector</span></span>

1. <span data-ttu-id="48b6b-131">Escolha **Microsoft Defender ATP** para a nova etapa.</span><span class="sxs-lookup"><span data-stu-id="48b6b-131">Choose **Microsoft Defender ATP** for the new step.</span></span>

2. <span data-ttu-id="48b6b-132">Escolha **Alertas - Obter API de alerta único.**</span><span class="sxs-lookup"><span data-stu-id="48b6b-132">Choose **Alerts - Get single alert API**.</span></span>

3. <span data-ttu-id="48b6b-133">De definir **a ID do Alerta** da última etapa como **Entrada**.</span><span class="sxs-lookup"><span data-stu-id="48b6b-133">Set the **Alert ID** from the last step as **Input**.</span></span>

    ![Imagem de credenciais de edição5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a><span data-ttu-id="48b6b-135">Isolar o dispositivo se a gravidade do Alerta for Alta</span><span class="sxs-lookup"><span data-stu-id="48b6b-135">Isolate the device if the Alert's severity is High</span></span>

1. <span data-ttu-id="48b6b-136">Adicionar **Condição** como uma nova etapa.</span><span class="sxs-lookup"><span data-stu-id="48b6b-136">Add **Condition** as a new step.</span></span>

2. <span data-ttu-id="48b6b-137">Verifique se a gravidade do alerta **é igual a** Alta.</span><span class="sxs-lookup"><span data-stu-id="48b6b-137">Check if the Alert severity **is equal to** High.</span></span>

   <span data-ttu-id="48b6b-138">Se sim, adicione o **Microsoft Defender ATP - Isolar** a ação do computador com a ID do computador e um comentário.</span><span class="sxs-lookup"><span data-stu-id="48b6b-138">If yes, add the **Microsoft Defender ATP - Isolate machine** action with the Machine ID and a comment.</span></span>

    ![Imagem de credenciais de edição6](images/api-flow-5.png)

3. <span data-ttu-id="48b6b-140">Adicione uma nova etapa para enviar emails sobre o Alerta e o Isolamento.</span><span class="sxs-lookup"><span data-stu-id="48b6b-140">Add a new step for emailing about the Alert and the Isolation.</span></span> <span data-ttu-id="48b6b-141">Há vários conectores de email que são muito fáceis de usar, como Outlook ou Gmail.</span><span class="sxs-lookup"><span data-stu-id="48b6b-141">There are multiple email connectors that are very easy to use, such as Outlook or Gmail.</span></span>

4. <span data-ttu-id="48b6b-142">Salve o fluxo.</span><span class="sxs-lookup"><span data-stu-id="48b6b-142">Save your flow.</span></span>

<span data-ttu-id="48b6b-143">Você também pode criar um **fluxo agendado** que executa consultas de Busca Avançada e muito mais!</span><span class="sxs-lookup"><span data-stu-id="48b6b-143">You can also create a **scheduled** flow that runs Advanced Hunting queries and much more!</span></span>

## <a name="related-topic"></a><span data-ttu-id="48b6b-144">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="48b6b-144">Related topic</span></span>
- [<span data-ttu-id="48b6b-145">APIs do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="48b6b-145">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
