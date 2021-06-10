---
title: Simular um ataque de phishing com o Microsoft Defender para Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os administradores podem aprender a simular ataques de phishing e treinar seus usuários na prevenção contra phishing usando treinamento de simulação de ataque no Microsoft Defender para Office 365.
ms.technology: mdo
ms.openlocfilehash: 27279f927a15ea94ae84112ffdc23d88ea42d2ff
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203141"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="a692b-103">Simular um ataque de phishing</span><span class="sxs-lookup"><span data-stu-id="a692b-103">Simulate a phishing attack</span></span>

<span data-ttu-id="a692b-104">O treinamento de simulação de ataque no Microsoft Defender Office 365 permite que você execute simulações de ataques cibernéticos benignos em sua organização para testar suas políticas e práticas de segurança, bem como treinar seus funcionários para aumentar sua conscientização e diminuir sua suscetibilidade a ataques.</span><span class="sxs-lookup"><span data-stu-id="a692b-104">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="a692b-105">Este artigo orienta você a criar um ataque de phishing simulado usando treinamento de simulação de ataque.</span><span class="sxs-lookup"><span data-stu-id="a692b-105">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

<span data-ttu-id="a692b-106">Para obter informações sobre o treinamento de simulação de ataque, consulte [Começar a usar o treinamento de simulação de ataque.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="a692b-106">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="a692b-107">Para iniciar um ataque de phishing simulado, abra o centro de segurança [Microsoft 365,](https://security.microsoft.com/)acesse **Email &** treinamento de simulação de ataque de colaboração e alternar para a guia \>  [**Simulações.**](https://security.microsoft.com/attacksimulator?viewid=simulations)</span><span class="sxs-lookup"><span data-stu-id="a692b-107">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulation training**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="a692b-108">Em **Simulações,** selecione **+ Iniciar uma simulação.**</span><span class="sxs-lookup"><span data-stu-id="a692b-108">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Iniciar um botão de simulação no Microsoft 365 de segurança](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="a692b-110">A qualquer momento durante a criação da simulação, você pode salvar e fechar para continuar configurando a simulação posteriormente.</span><span class="sxs-lookup"><span data-stu-id="a692b-110">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="a692b-111">Selecionar uma técnica de engenharia social</span><span class="sxs-lookup"><span data-stu-id="a692b-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="a692b-112">Selecione de 4 técnicas diferentes, com a curadoria da estrutura [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span><span class="sxs-lookup"><span data-stu-id="a692b-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="a692b-113">Cargas diferentes estão disponíveis para diferentes técnicas:</span><span class="sxs-lookup"><span data-stu-id="a692b-113">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="a692b-114">**A coleta de** credenciais tenta coletar credenciais levando os usuários a um site de aparência conhecido com caixas de entrada para enviar um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="a692b-114">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="a692b-115">**O anexo de malware** adiciona um anexo mal-intencionado a uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="a692b-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="a692b-116">Quando o usuário abre o anexo, o código arbitrário é executado que ajudará o invasor a comprometer o dispositivo do destino.</span><span class="sxs-lookup"><span data-stu-id="a692b-116">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="a692b-117">**Link in attachment** é um tipo de coleta de credenciais híbrida.</span><span class="sxs-lookup"><span data-stu-id="a692b-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="a692b-118">Um invasor insere uma URL em um anexo de email.</span><span class="sxs-lookup"><span data-stu-id="a692b-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="a692b-119">A URL dentro do anexo segue a mesma técnica que a coleta de credenciais.</span><span class="sxs-lookup"><span data-stu-id="a692b-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="a692b-120">**O link para malware** executará algum código arbitrário de um arquivo hospedado em um serviço de compartilhamento de arquivos conhecido.</span><span class="sxs-lookup"><span data-stu-id="a692b-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="a692b-121">A mensagem enviada ao usuário conterá um link para esse arquivo mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="a692b-121">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="a692b-122">Abrir o arquivo e ajudar o invasor a comprometer o dispositivo do destino.</span><span class="sxs-lookup"><span data-stu-id="a692b-122">Opening the file and help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="a692b-123">**A URL** de unidade por unidade é onde a URL mal-intencionada na mensagem leva o usuário a um site de aparência familiar que executa silenciosamente e/ou instala código de código no dispositivo do usuário.</span><span class="sxs-lookup"><span data-stu-id="a692b-123">**Drive-by URL** is where the malicious URL in the message takes the user to a familiar-looking website that silently runs and/or installs code code on the user's device.</span></span>

> [!TIP]
> <span data-ttu-id="a692b-124">Clicar em **Exibir detalhes na** descrição de cada técnica exibirá mais informações e as etapas de simulação da técnica.</span><span class="sxs-lookup"><span data-stu-id="a692b-124">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Etapas de simulação para coleta de credenciais no treinamento de simulação de ataque Microsoft 365 centro de segurança](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="a692b-126">Depois de selecionar a técnica e clicar em **Next,** dê um nome à simulação e, opcionalmente, uma descrição.</span><span class="sxs-lookup"><span data-stu-id="a692b-126">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="a692b-127">Selecionar uma carga</span><span class="sxs-lookup"><span data-stu-id="a692b-127">Selecting a payload</span></span>

<span data-ttu-id="a692b-128">Em seguida, você precisará selecionar uma carga no catálogo de carga pré-existente.</span><span class="sxs-lookup"><span data-stu-id="a692b-128">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="a692b-129">Os carregadores têm vários pontos de dados para ajudá-lo a escolher:</span><span class="sxs-lookup"><span data-stu-id="a692b-129">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="a692b-130">**A taxa de** clique conta quantas pessoas clicaram nessa carga.</span><span class="sxs-lookup"><span data-stu-id="a692b-130">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="a692b-131">**A taxa de comprometimento** prevista prevê a porcentagem de pessoas que serão comprometidas por essa carga com base em dados históricos para a carga no Microsoft Defender para clientes Office 365.</span><span class="sxs-lookup"><span data-stu-id="a692b-131">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="a692b-132">**As simulações lançadas** contam o número de vezes que essa carga foi usada em outras simulações.</span><span class="sxs-lookup"><span data-stu-id="a692b-132">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="a692b-133">**A complexidade**, disponível por **meio** de filtros, é calculada com base no número de indicadores dentro da carga que a pista direciona para ele como um ataque.</span><span class="sxs-lookup"><span data-stu-id="a692b-133">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="a692b-134">Mais indicadores levam à menor complexidade.</span><span class="sxs-lookup"><span data-stu-id="a692b-134">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="a692b-135">**Source**, disponível por meio **de** filtros , indica se a carga foi criada em seu locatário ou faz parte do catálogo de carga pré-existente da Microsoft (global).</span><span class="sxs-lookup"><span data-stu-id="a692b-135">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Carga selecionada no treinamento de simulação de ataque no Microsoft 365 de segurança](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="a692b-137">Selecione uma carga na lista para ver uma visualização da carga com informações adicionais sobre ele.</span><span class="sxs-lookup"><span data-stu-id="a692b-137">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="a692b-138">Se você quiser criar sua própria carga, leia criar uma carga para treinamento de [simulação de ataque.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="a692b-138">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="a692b-139">Segmentação por público-alvo</span><span class="sxs-lookup"><span data-stu-id="a692b-139">Audience targeting</span></span>

<span data-ttu-id="a692b-140">Agora é hora de selecionar a audiência dessa simulação.</span><span class="sxs-lookup"><span data-stu-id="a692b-140">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="a692b-141">Você pode optar por **incluir todos os usuários em sua organização ou** incluir apenas usuários e grupos **específicos.**</span><span class="sxs-lookup"><span data-stu-id="a692b-141">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="a692b-142">Ao optar por **incluir apenas usuários e grupos específicos,** você pode:</span><span class="sxs-lookup"><span data-stu-id="a692b-142">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="a692b-143">**Adicione usuários**, o que permite aproveitar a pesquisa para seu locatário, bem como recursos avançados de pesquisa e filtragem, como direcionar usuários que não foram direcionados por uma simulação nos últimos três meses.</span><span class="sxs-lookup"><span data-stu-id="a692b-143">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="a692b-144">![Filtragem do usuário no treinamento de simulação de ataque no Microsoft 365 de segurança](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="a692b-144">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="a692b-145">**A importação de CSV** permite importar um conjunto predefinido de usuários para essa simulação.</span><span class="sxs-lookup"><span data-stu-id="a692b-145">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="a692b-146">Atribuindo treinamento</span><span class="sxs-lookup"><span data-stu-id="a692b-146">Assigning training</span></span>

<span data-ttu-id="a692b-147">Recomendamos que você atribua treinamento para cada simulação, pois os funcionários que passam pelo treinamento são menos suscetíveis a ataques semelhantes.</span><span class="sxs-lookup"><span data-stu-id="a692b-147">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="a692b-148">Você pode optar por ter treinamento atribuído a você ou selecionar cursos de treinamento e módulos por conta própria.</span><span class="sxs-lookup"><span data-stu-id="a692b-148">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="a692b-149">Selecione a **data de vencimento do treinamento** para garantir que os funcionários terminem o treinamento em tempo hábil.</span><span class="sxs-lookup"><span data-stu-id="a692b-149">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="a692b-150">Se você optar por selecionar cursos e módulos por conta própria, ainda poderá ver o conteúdo recomendado, bem como todos os cursos e módulos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a692b-150">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Adicionando treinamento recomendado no treinamento de simulação de ataque no Microsoft 365 de segurança](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="a692b-152">Nas próximas etapas, você precisará adicionar **treinamentos** se você optou por selecioná-lo por conta própria e personalizar sua página inicial de treinamento.</span><span class="sxs-lookup"><span data-stu-id="a692b-152">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="a692b-153">Você poderá visualizar a página de aterrissagem do treinamento, bem como alterar o header e o corpo dela.</span><span class="sxs-lookup"><span data-stu-id="a692b-153">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="a692b-154">Iniciar detalhes e revisar</span><span class="sxs-lookup"><span data-stu-id="a692b-154">Launch details and review</span></span>

<span data-ttu-id="a692b-155">Agora que tudo está configurado, você pode iniciar essa simulação imediatamente ou agende-a para uma data posterior.</span><span class="sxs-lookup"><span data-stu-id="a692b-155">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="a692b-156">Você também precisará escolher quando encerrar essa simulação.</span><span class="sxs-lookup"><span data-stu-id="a692b-156">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="a692b-157">Vamos parar de capturar a interação com essa simulação após o tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="a692b-157">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="a692b-158">**Habilita a entrega de zona** de tempo ciente da região para entregar mensagens de ataque simuladas aos funcionários durante o horário de trabalho com base em sua região.</span><span class="sxs-lookup"><span data-stu-id="a692b-158">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="a692b-159">Depois de terminar, clique em **Next** e revise os detalhes da simulação.</span><span class="sxs-lookup"><span data-stu-id="a692b-159">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="a692b-160">Clique em **Editar** em qualquer uma das partes para voltar e alterar todos os detalhes que precisam ser mudados.</span><span class="sxs-lookup"><span data-stu-id="a692b-160">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="a692b-161">Depois de terminar, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="a692b-161">Once done, click **Submit**.</span></span>
