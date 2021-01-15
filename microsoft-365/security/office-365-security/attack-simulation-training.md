---
title: Simular um ataque de phishing com o Microsoft Defender para Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os administradores podem aprender a simular ataques de phishing e treinar seus usuários sobre prevenção contra phishing usando o treinamento de simulação de ataque no Microsoft Defender para Office 365.
ms.openlocfilehash: dfdd3c93afb1b0fb30cc5b5affc040a369c29447
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870962"
---
# <a name="simulate-a-phishing-attack"></a><span data-ttu-id="851e4-103">Simular um ataque de phishing</span><span class="sxs-lookup"><span data-stu-id="851e4-103">Simulate a phishing attack</span></span>

<span data-ttu-id="851e4-104">O treinamento de simulação de ataque no Microsoft Defender para Office 365 permite que você execute simulações de ataques cibernéticos benignos em sua organização para testar suas políticas e práticas de segurança, bem como treinar seus funcionários para aumentar a conscientização e diminuir a suscetibilidade a ataques.</span><span class="sxs-lookup"><span data-stu-id="851e4-104">Attack simulation training in Microsoft Defender for Office 365 lets you run benign cyberattack simulations on your organization to test your security policies and practices, as well as train your employees to increase their awareness and decrease their susceptibility to attacks.</span></span> <span data-ttu-id="851e4-105">Este artigo orienta você em meio à criação de um ataque simulado de phishing usando o treinamento de simulação de ataque.</span><span class="sxs-lookup"><span data-stu-id="851e4-105">This article walks you through creating  a simulated phishing attack using attack simulation training.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="851e4-106">Para obter informações de iniciação sobre treinamento de simulação de ataque, consulte [Começar a usar o treinamento de simulação de ataque.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="851e4-106">For getting started information about Attack simulation training, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>

<span data-ttu-id="851e4-107">Para iniciar um ataque simulado de phishing, abra o centro de segurança do [Microsoft 365,](https://security.microsoft.com/)vá para **Email &** treinamento de simulação de ataques de colaboração e alterne para a guia \>  [**Simulações.**](https://security.microsoft.com/attacksimulator?viewid=simulations)</span><span class="sxs-lookup"><span data-stu-id="851e4-107">To launch a simulated phishing attack, open the [Microsoft 365 security center](https://security.microsoft.com/), go to **Email & collaboration** \> **Attack simulation training**, and switch to the [**Simulations**](https://security.microsoft.com/attacksimulator?viewid=simulations) tab.</span></span>

<span data-ttu-id="851e4-108">Em **Simulações,** selecione **+ Iniciar uma simulação.**</span><span class="sxs-lookup"><span data-stu-id="851e4-108">Under **Simulations**, select **+ Launch a simulation**.</span></span>

![Iniciar um botão de simulação na central de segurança do Microsoft 365](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> <span data-ttu-id="851e4-110">A qualquer momento durante a criação da simulação, você pode salvar e fechar para continuar configurando a simulação posteriormente.</span><span class="sxs-lookup"><span data-stu-id="851e4-110">At any point during simulation creation, you can save and close to continue configuring the simulation at a later time.</span></span>

## <a name="selecting-a-social-engineering-technique"></a><span data-ttu-id="851e4-111">Selecionando uma técnica de engenharia social</span><span class="sxs-lookup"><span data-stu-id="851e4-111">Selecting a social engineering technique</span></span>

<span data-ttu-id="851e4-112">Selecione de 4 técnicas diferentes, selecionadas a partir da estrutura [MITRE ATT&CK® estrutura.](https://attack.mitre.org/techniques/enterprise/)</span><span class="sxs-lookup"><span data-stu-id="851e4-112">Select from 4 different techniques, curated from the [MITRE ATT&CK® framework](https://attack.mitre.org/techniques/enterprise/).</span></span> <span data-ttu-id="851e4-113">Cargas diferentes estão disponíveis para diferentes técnicas:</span><span class="sxs-lookup"><span data-stu-id="851e4-113">Different payloads are available for different techniques:</span></span>

- <span data-ttu-id="851e4-114">**A coleta de** credenciais tenta coletar credenciais levando os usuários a um site com aparência conhecida com caixas de entrada para enviar um nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="851e4-114">**Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.</span></span>
- <span data-ttu-id="851e4-115">**O anexo de malware** adiciona um anexo mal-intencionado a uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="851e4-115">**Malware attachment** adds a malicious attachment to a message.</span></span> <span data-ttu-id="851e4-116">Quando o usuário abre o anexo, é executado um código arbitrário que ajudará o invasor a comprometer o dispositivo do destino.</span><span class="sxs-lookup"><span data-stu-id="851e4-116">When the user opens the attachment, arbitrary code is run that will help the attacker compromise the target's device.</span></span>
- <span data-ttu-id="851e4-117">**O link no anexo** é um tipo de coleta híbrida de credencial.</span><span class="sxs-lookup"><span data-stu-id="851e4-117">**Link in attachment** is a type of credential harvest hybrid.</span></span> <span data-ttu-id="851e4-118">Um invasor insere uma URL em um anexo de email.</span><span class="sxs-lookup"><span data-stu-id="851e4-118">An attacker inserts a URL into an email attachment.</span></span> <span data-ttu-id="851e4-119">A URL dentro do anexo segue a mesma técnica que a coleta de credenciais.</span><span class="sxs-lookup"><span data-stu-id="851e4-119">The URL within the attachment follows the same technique as credential harvest.</span></span>
- <span data-ttu-id="851e4-120">**O link para malware** executará alguns códigos arbitrários de um arquivo hospedado em um serviço de compartilhamento de arquivos conhecido.</span><span class="sxs-lookup"><span data-stu-id="851e4-120">**Link to malware** will run some arbitrary code from a file hosted on a well-known file sharing service.</span></span> <span data-ttu-id="851e4-121">A mensagem enviada ao usuário conterá um link para esse arquivo mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="851e4-121">The message sent to the user will contain a link to this malicious file.</span></span> <span data-ttu-id="851e4-122">Abrir o arquivo e ajudar o invasor a comprometer o dispositivo do destino.</span><span class="sxs-lookup"><span data-stu-id="851e4-122">Opening the file and help the attacker compromise the target's device.</span></span>

> [!TIP]
> <span data-ttu-id="851e4-123">Clicar em Exibir **detalhes na** descrição de cada técnica exibirá mais informações e as etapas de simulação para a técnica.</span><span class="sxs-lookup"><span data-stu-id="851e4-123">Clicking on **View details** within the description of each technique will display further information and the simulation steps for the technique.</span></span>
>
> ![Etapas de simulação para coleta de credenciais dentro do treinamento de simulação de ataque no centro de segurança do Microsoft 365](../../media/attack-sim-preview-sim-steps.png)

<span data-ttu-id="851e4-125">Depois de selecionar a técnica e clicar em **Próximo,** dê um nome à simulação e, opcionalmente, uma descrição.</span><span class="sxs-lookup"><span data-stu-id="851e4-125">After you've selected the technique and clicked on **Next**, give your simulation a name and optionally a description.</span></span>

## <a name="selecting-a-payload"></a><span data-ttu-id="851e4-126">Selecionando uma carga</span><span class="sxs-lookup"><span data-stu-id="851e4-126">Selecting a payload</span></span>

<span data-ttu-id="851e4-127">Em seguida, você precisará selecionar uma carga do catálogo de carga pré-existente.</span><span class="sxs-lookup"><span data-stu-id="851e4-127">Next, you'll need to either select a payload from the pre-existing payload catalog.</span></span>

<span data-ttu-id="851e4-128">As cargas têm vários pontos de dados para ajudá-lo a escolher:</span><span class="sxs-lookup"><span data-stu-id="851e4-128">Payloads have a number of data points to help you choose:</span></span>

- <span data-ttu-id="851e4-129">**A taxa de** clique conta quantas pessoas clicaram nessa carga.</span><span class="sxs-lookup"><span data-stu-id="851e4-129">**Click rate** counts how many people clicked this payload.</span></span>
- <span data-ttu-id="851e4-130">**A taxa de** comprometimento prevista prevê a porcentagem de pessoas que serão comprometidas por essa carga com base nos dados históricos da carga nos clientes do Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="851e4-130">**Predicted compromise rate** predicts the percentage of people that will get compromised by this payload based on historical data for the payload across Microsoft Defender for Office 365 customers.</span></span>
- <span data-ttu-id="851e4-131">**As simulações lançadas** conta o número de vezes que essa carga foi usada em outras simulações.</span><span class="sxs-lookup"><span data-stu-id="851e4-131">**Simulations launched** counts the number of times this payload was used in other simulations.</span></span>
- <span data-ttu-id="851e4-132">**A complexidade,** disponível por **meio** de filtros, é calculada com base no número de indicadores dentro da carga que indica um ataque.</span><span class="sxs-lookup"><span data-stu-id="851e4-132">**Complexity**, available through **filters**, is calculated based on the number of indicators within the payload that clue targets in on it being an attack.</span></span> <span data-ttu-id="851e4-133">Mais indicadores levam à menor complexidade.</span><span class="sxs-lookup"><span data-stu-id="851e4-133">More indicators lead to lower complexity.</span></span>
- <span data-ttu-id="851e4-134">**Source**, disponível por **meio** de filtros , indica se a carga foi criada em seu locatário ou é uma parte do catálogo de carga pré-existente da Microsoft (global).</span><span class="sxs-lookup"><span data-stu-id="851e4-134">**Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).</span></span>

![Carga selecionada no treinamento de simulação de ataque no centro de segurança do Microsoft 365](../../media/attack-sim-preview-select-payload.png)

<span data-ttu-id="851e4-136">Selecione uma carga na lista para ver uma visualização da carga com informações adicionais sobre ela.</span><span class="sxs-lookup"><span data-stu-id="851e4-136">Select a payload from the list to see a preview of the payload with additional information about it.</span></span>

<span data-ttu-id="851e4-137">Se você quiser criar sua própria carga, leia criar uma carga para treinamento [de simulação de ataque.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="851e4-137">If you'd like to create your own payload, read [create a payload for attack simulation training](attack-simulation-training-payloads.md).</span></span>

## <a name="audience-targeting"></a><span data-ttu-id="851e4-138">Segmentação por público-alvo</span><span class="sxs-lookup"><span data-stu-id="851e4-138">Audience targeting</span></span>

<span data-ttu-id="851e4-139">Agora é hora de selecionar o público desta simulação.</span><span class="sxs-lookup"><span data-stu-id="851e4-139">Now it's time to select this simulation's audience.</span></span> <span data-ttu-id="851e4-140">Você pode optar por **incluir todos os usuários em sua organização ou** incluir somente usuários e grupos **específicos.**</span><span class="sxs-lookup"><span data-stu-id="851e4-140">You can choose to **include all users in your organization** or **include only specific users and groups**.</span></span>

<span data-ttu-id="851e4-141">Ao optar por **incluir somente usuários e grupos específicos,** você pode:</span><span class="sxs-lookup"><span data-stu-id="851e4-141">When you choose to **include only specific users and groups** you can either:</span></span>

- <span data-ttu-id="851e4-142">**Adicione** usuários , que permite que você aproveite a pesquisa para seu locatário, bem como recursos avançados de pesquisa e filtragem, como direcionamento para usuários que não foram direcionados por uma simulação nos últimos 3 meses.</span><span class="sxs-lookup"><span data-stu-id="851e4-142">**Add users**, which allows you to leverage search for your tenant, as well as advanced search and filtering capabilities, like targeting users who haven't been targeted by a simulation in the last 3 months.</span></span>
  <span data-ttu-id="851e4-143">![Filtragem de usuário no treinamento de simulação de ataque no centro de segurança do Microsoft 365](../../media/attack-sim-preview-user-targeting.png)</span><span class="sxs-lookup"><span data-stu-id="851e4-143">![User filtering in attack simulation training on Microsoft 365 security center](../../media/attack-sim-preview-user-targeting.png)</span></span>
- <span data-ttu-id="851e4-144">**A importação de CSV** permite importar um conjunto predefinido de usuários para esta simulação.</span><span class="sxs-lookup"><span data-stu-id="851e4-144">**Import from CSV** allows you to import a predefined set of users for this simulation.</span></span>

## <a name="assigning-training"></a><span data-ttu-id="851e4-145">Atribuindo treinamento</span><span class="sxs-lookup"><span data-stu-id="851e4-145">Assigning training</span></span>

<span data-ttu-id="851e4-146">Recomendamos que você atribua treinamento para cada simulação, pois os funcionários que passam pelo treinamento são menos suscetíveis a ataques semelhantes.</span><span class="sxs-lookup"><span data-stu-id="851e4-146">We recommend that you assign training for each simulation, as employees who go through training are less susceptible to similar attacks.</span></span>

<span data-ttu-id="851e4-147">Você pode optar por ter treinamento atribuído a você ou selecionar cursos e módulos de treinamento por conta própria.</span><span class="sxs-lookup"><span data-stu-id="851e4-147">You can either choose to have training assigned for you or select training courses and modules yourself.</span></span>

<span data-ttu-id="851e4-148">Selecione a **data de vencimento do treinamento** para garantir que os funcionários terminem o treinamento em tempo hábil.</span><span class="sxs-lookup"><span data-stu-id="851e4-148">Select the **training due date** to make sure employees finish their training in a timely manner.</span></span>

> [!NOTE]
> <span data-ttu-id="851e4-149">Se você optar por selecionar cursos e módulos por conta própria, ainda poderá ver o conteúdo recomendado, bem como todos os cursos e módulos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="851e4-149">If you choose to select courses and modules yourself, you'll still be able to see the recommended content as well as all available courses and modules.</span></span>
>
> ![Adicionando treinamento recomendado no treinamento de simulação de ataque no centro de segurança do Microsoft 365](../../media/attack-sim-preview-add-training.png)

<span data-ttu-id="851e4-151">Nas próximas etapas, você precisará adicionar **treinamentos** se optar por selecioná-lo por conta própria e personalizar sua página inicial de treinamento.</span><span class="sxs-lookup"><span data-stu-id="851e4-151">In the next steps you'll need to **Add trainings** if you opted to select it yourself, and customize your training landing page.</span></span> <span data-ttu-id="851e4-152">Você poderá visualizar a página inicial de treinamento, bem como alterar o corpo e o header dela.</span><span class="sxs-lookup"><span data-stu-id="851e4-152">You'll be able to preview the training landing page, as well as change the header and body of it.</span></span>

## <a name="launch-details-and-review"></a><span data-ttu-id="851e4-153">Detalhes e revisão do lançamento</span><span class="sxs-lookup"><span data-stu-id="851e4-153">Launch details and review</span></span>

<span data-ttu-id="851e4-154">Agora que tudo está configurado, você pode iniciar essa simulação imediatamente ou agende-a para uma data posterior.</span><span class="sxs-lookup"><span data-stu-id="851e4-154">Now that everything is configured, you can launch this simulation immediately or schedule it for a later date.</span></span> <span data-ttu-id="851e4-155">Você também precisará escolher quando finalizar essa simulação.</span><span class="sxs-lookup"><span data-stu-id="851e4-155">You will also need to choose when to end this simulation.</span></span> <span data-ttu-id="851e4-156">Paramos de capturar a interação com essa simulação após o tempo selecionado.</span><span class="sxs-lookup"><span data-stu-id="851e4-156">We will stop capturing interaction with this simulation past the selected time.</span></span>

<span data-ttu-id="851e4-157">**Habilita a entrega de zona de** tempo ciente da região para entregar mensagens de ataque simuladas aos funcionários durante o horário de trabalho com base na região.</span><span class="sxs-lookup"><span data-stu-id="851e4-157">**Enable region aware timezone delivery** to deliver simulated attack messages to your employees during their working hours based on their region.</span></span>

<span data-ttu-id="851e4-158">Quando terminar, clique em Próximo **e** revise os detalhes da simulação.</span><span class="sxs-lookup"><span data-stu-id="851e4-158">Once you're done, click on **Next** and review the details of your simulation.</span></span> <span data-ttu-id="851e4-159">Clique em **Editar** em qualquer uma das partes para voltar e alterar todos os detalhes que precisam ser mudados.</span><span class="sxs-lookup"><span data-stu-id="851e4-159">Click on **Edit** on any of the parts to go back and change any details that need changing.</span></span> <span data-ttu-id="851e4-160">Depois de terminar, clique **em Enviar.**</span><span class="sxs-lookup"><span data-stu-id="851e4-160">Once done, click **Submit**.</span></span>
