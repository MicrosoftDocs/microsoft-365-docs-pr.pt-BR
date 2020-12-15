---
title: Simular um ataque de phishing com o Microsoft defender para Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Os administradores podem aprender a simular ataques de phishing e treinar seus usuários sobre prevenção de phishing usando o treinamento de simulação de ataque no Microsoft defender para Office 365.
ms.openlocfilehash: 3707041067fd76ee9535d0dccf5cdfcb9d74fbd7
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667498"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="56524-103">Simular um ataque de phishing</span><span class="sxs-lookup"><span data-stu-id="56524-103">Simulate a phishing attack</span></span>

<span data-ttu-id="56524-104">O treinamento do simulador de ataque no Microsoft defender para Office 365 permite executar simulações benignas do cyberattack em sua organização para testar suas práticas e políticas de segurança, bem como treinar seus funcionários para aumentar a conscientização e reduzir o susceptibility a ataques.</span><span class="sxs-lookup"><span data-stu-id="56524-104">Attack simulator training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="56524-105">Este artigo orienta você durante a criação de um ataque de phishing simulado usando o treinamento do Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="56524-105">This article walks you through creating  a simulated phishing attack using attack simulator training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="56524-106">Para iniciar um ataque de phishing simulado, abra o [centro de segurança do Microsoft 365](https://security.microsoft.com/), acesse **e-mail & Collaboration** Attack disparation \> **Simulator** e alterne para a guia [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) .</span><span class="sxs-lookup"><span data-stu-id="56524-106">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulator**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="56524-107">Em **simulações**, selecione **+ iniciar uma simulação**.</span><span class="sxs-lookup"><span data-stu-id="56524-107">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Iniciar um botão de simulação no centro de segurança do Microsoft 365](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="56524-109">A qualquer momento durante a criação da simulação, você pode salvar e fechar para continuar Configurando a simulação mais tarde.</span><span class="sxs-lookup"><span data-stu-id="56524-109">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="56524-110">Selecionar uma técnica de engenharia social</span><span class="sxs-lookup"><span data-stu-id="56524-110">Selecting a social engineering technique</span></span>

<span data-ttu-id="56524-111">Selecione dentre 4 técnicas diferentes, organizadas da [estrutura Mitre ATT&CK®](https://attack.mitre.org/techniques/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="56524-111">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="56524-112">Cargas diferentes estão disponíveis para diferentes técnicas:</span><span class="sxs-lookup"><span data-stu-id="56524-112">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="56524-113">A **coleta de credenciais** tenta coletar credenciais levando os usuários a um site de aparência conhecido com caixas de entrada para enviar um nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="56524-113">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="56524-114">O **anexo de malware** adiciona um anexo mal-intencionado a uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="56524-114">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="56524-115">Quando o usuário abre o anexo, o código arbitrário é executado e ajudará o invasor a comprometer o dispositivo de destino.</span><span class="sxs-lookup"><span data-stu-id="56524-115">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="56524-116">**Link no anexo** é um tipo de coleta de credenciais híbrido.</span><span class="sxs-lookup"><span data-stu-id="56524-116">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="56524-117">Um invasor insere uma URL em um anexo de email.</span><span class="sxs-lookup"><span data-stu-id="56524-117">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="56524-118">A URL no anexo segue a mesma técnica que a coleta de credenciais.</span><span class="sxs-lookup"><span data-stu-id="56524-118">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="56524-119">O **link para malware** executará um código arbitrário de um arquivo hospedado em um serviço de compartilhamento de arquivos conhecido.</span><span class="sxs-lookup"><span data-stu-id="56524-119">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="56524-120">A mensagem enviada para o usuário conterá um link para este arquivo mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="56524-120">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="56524-121">Abrir o arquivo e ajudar o atacante a comprometer o dispositivo de destino.</span><span class="sxs-lookup"><span data-stu-id="56524-121">Opening the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="56524-122">Ao clicar em **Exibir detalhes** dentro da descrição de cada técnica, serão exibidas mais informações e as etapas de simulação da técnica.</span><span class="sxs-lookup"><span data-stu-id="56524-122">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Etapas de simulação para coleta de credenciais no treinamento de simulação de ataque no centro de segurança do Microsoft 365](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="56524-124">Depois de selecionar a técnica e clicar em **Avançar**, dê um nome à sua simulação e, opcionalmente, uma descrição.</span><span class="sxs-lookup"><span data-stu-id="56524-124">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="56524-125">Selecionar uma carga</span><span class="sxs-lookup"><span data-stu-id="56524-125">Selecting a payload</span></span>

<span data-ttu-id="56524-126">Em seguida, você precisará selecionar uma carga no catálogo de carga pré-existente.</span><span class="sxs-lookup"><span data-stu-id="56524-126">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="56524-127">As cargas têm vários pontos de dados para ajudá-lo a escolher:</span><span class="sxs-lookup"><span data-stu-id="56524-127">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="56524-128">A **taxa de clique** considera quantas pessoas clicaram nesta carga.</span><span class="sxs-lookup"><span data-stu-id="56524-128">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="56524-129">A **taxa de comprometimento prevista** prevê a porcentagem de pessoas que serão comprometidas por essa carga com base em dados históricos para a carga nos clientes do Microsoft defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="56524-129">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="56524-130">**Simulações iniciadas** conta o número de vezes que essa carga foi usada em outras simulações.</span><span class="sxs-lookup"><span data-stu-id="56524-130">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="56524-131">A **complexidade**, disponível através de **filtros**, é calculada com base no número de indicadores dentro da carga que apontam os destinos em que eles estão sendo um ataque.</span><span class="sxs-lookup"><span data-stu-id="56524-131">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="56524-132">Mais indicadores levam a uma complexidade mais baixa.</span><span class="sxs-lookup"><span data-stu-id="56524-132">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="56524-133">**Fonte**, disponível através de **filtros**, indica se a carga foi criada em seu locatário ou faz parte do catálogo de carga (global) da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="56524-133">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Carga selecionada dentro do treinamento de simulação de ataque no centro de segurança do Microsoft 365](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="56524-135">Selecione uma carga na lista para ver uma visualização da carga com informações adicionais sobre ela.</span><span class="sxs-lookup"><span data-stu-id="56524-135">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="56524-136">Se quiser criar sua própria carga, leia [criar uma carga de treinamento de simulação de ataque](attack-simulation-training-payloads.md).</span><span class="sxs-lookup"><span data-stu-id="56524-136">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="56524-137">Segmentação por público-alvo</span><span class="sxs-lookup"><span data-stu-id="56524-137">Audience targeting</span></span>

<span data-ttu-id="56524-138">Agora é hora de selecionar o público da simulação.</span><span class="sxs-lookup"><span data-stu-id="56524-138">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="56524-139">Você pode optar por **incluir todos os usuários em sua organização** ou **incluir apenas usuários e grupos específicos**.</span><span class="sxs-lookup"><span data-stu-id="56524-139">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="56524-140">Ao optar por **incluir apenas usuários e grupos específicos** , você pode:</span><span class="sxs-lookup"><span data-stu-id="56524-140">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="56524-141">**Adicione usuários**, que permite que você aproveite a pesquisa para seu locatário, bem como recursos avançados de pesquisa e filtragem, como direcionar os usuários que não foram direcionados a uma simulação nos últimos 3 meses.</span><span class="sxs-lookup"><span data-stu-id="56524-141">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="56524-142">![Filtragem de usuário no treinamento de simulação de ataque no centro de segurança do Microsoft 365](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="56524-142">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="56524-143">**Import from CSV** permite que você importe um conjunto predefinido de usuários para esta simulação.</span><span class="sxs-lookup"><span data-stu-id="56524-143">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="56524-144">Atribuindo treinamento</span><span class="sxs-lookup"><span data-stu-id="56524-144">Assigning training</span></span>

<span data-ttu-id="56524-145">Recomendamos que você atribua treinamento para cada simulação, pois os funcionários que passam pelo treinamento são menos suscetíveis a ataques semelhantes.</span><span class="sxs-lookup"><span data-stu-id="56524-145">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="56524-146">Você pode optar por ter o treinamento atribuído ou selecionar cursos e módulos de treinamento por conta própria.</span><span class="sxs-lookup"><span data-stu-id="56524-146">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="56524-147">Selecione a **data de conclusão de treinamento** para garantir que os funcionários concluam o treinamento em tempo hábil.</span><span class="sxs-lookup"><span data-stu-id="56524-147">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="56524-148">Se você optar por selecionar cursos e módulos por conta própria, ainda poderá ver o conteúdo recomendado, bem como todos os cursos e módulos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="56524-148">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Adição de treinamento recomendado ao treinamento de simulação de ataque no centro de segurança do Microsoft 365](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="56524-150">Nas próximas etapas, você precisará **Adicionar treinamentos** se optar por selecioná-lo e personalizar sua página inicial de treinamento.</span><span class="sxs-lookup"><span data-stu-id="56524-150">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="56524-151">Você poderá visualizar a página de aterrissagem de treinamento, bem como alterar o cabeçalho e o corpo do mesmo.</span><span class="sxs-lookup"><span data-stu-id="56524-151">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="56524-152">Detalhes e análise do lançamento</span><span class="sxs-lookup"><span data-stu-id="56524-152">Launch details and review</span></span>

<span data-ttu-id="56524-153">Agora que tudo está configurado, você pode iniciar essa simulação imediatamente ou agendá-la para uma data posterior.</span><span class="sxs-lookup"><span data-stu-id="56524-153">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="56524-154">Você também precisará escolher quando terminar esta simulação.</span><span class="sxs-lookup"><span data-stu-id="56524-154">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="56524-155">Vamos parar a captura da interação com essa simulação após o horário selecionado.</span><span class="sxs-lookup"><span data-stu-id="56524-155">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="56524-156">**Habilitar a entrega de fuso horário que reconhece a região** para entregar mensagens de ataque simuladas a seus funcionários durante as horas de trabalho com base em sua região.</span><span class="sxs-lookup"><span data-stu-id="56524-156">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="56524-157">Após concluir, clique em **Avançar** e revise os detalhes de sua simulação.</span><span class="sxs-lookup"><span data-stu-id="56524-157">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="56524-158">Clique em **Editar** em qualquer uma das partes para voltar e alterar os detalhes que precisam ser alterados.</span><span class="sxs-lookup"><span data-stu-id="56524-158">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="56524-159">Após concluir, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="56524-159">Once done, click **Submit**.</span></span>
