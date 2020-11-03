---
title: Perfil de dispositivo no portal de segurança do Microsoft 365
description: Exibir os níveis de risco e de exposição de um dispositivo em sua organização. Analise as ameaças passadas e apresente e proteja o dispositivo com as atualizações mais recentes.
keywords: segurança, malware, Microsoft 365, M365, proteção contra ameaças da Microsoft, MTP, central de segurança, Microsoft defender ATP, Office 365 ATP, Azure ATP, página de dispositivo, perfil de dispositivo, página de máquina, perfil de máquina
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 3840a6beae3b586fc90420f7813ff6e9d3cc6c60
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843847"
---
# <a name="device-profile-page"></a><span data-ttu-id="66b66-105">Página de perfil de dispositivo</span><span class="sxs-lookup"><span data-stu-id="66b66-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="66b66-106">O portal de segurança do Microsoft 365 fornece páginas de perfil de dispositivo para que você possa avaliar rapidamente a integridade e o status dos dispositivos na sua rede.</span><span class="sxs-lookup"><span data-stu-id="66b66-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66b66-107">A página de perfil de dispositivo pode parecer um pouco diferente, dependendo se o dispositivo está inscrito no Microsoft defender para ponto de extremidade, Microsoft defender para identidade ou ambos.</span><span class="sxs-lookup"><span data-stu-id="66b66-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender for Endpoint, Microsoft Defender for Identity, or both.</span></span>

<span data-ttu-id="66b66-108">Se o dispositivo estiver inscrito no Microsoft defender para ponto de extremidade, você também pode usar a página de perfil de dispositivo para executar algumas tarefas comuns de segurança.</span><span class="sxs-lookup"><span data-stu-id="66b66-108">If the device is enrolled in Microsoft Defender for Endpoint, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="66b66-109">Navegando na página de perfil do dispositivo</span><span class="sxs-lookup"><span data-stu-id="66b66-109">Navigating the device profile page</span></span>

<span data-ttu-id="66b66-110">A página de perfil é dividida em várias seções abrangentes.</span><span class="sxs-lookup"><span data-stu-id="66b66-110">The profile page is broken up into several broad sections.</span></span>

![Imagem da página de perfil do dispositivo com (1) área da guia (2) barra lateral e (3) ações realçadas em vermelho](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="66b66-112">A barra lateral (1) lista detalhes básicos sobre o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="66b66-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="66b66-113">A área de conteúdo principal (2) contém guias que você pode alternar para exibir diferentes tipos de informações sobre o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="66b66-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="66b66-114">Se o dispositivo estiver inscrito no Microsoft defender para ponto de extremidade, você também verá uma lista de ações de resposta (3).</span><span class="sxs-lookup"><span data-stu-id="66b66-114">If the device is enrolled in Microsoft Defender for Endpoint, you will also see a list of response actions (3).</span></span> <span data-ttu-id="66b66-115">As ações de resposta permitem que você realize tarefas comuns relacionadas à segurança.</span><span class="sxs-lookup"><span data-stu-id="66b66-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="66b66-116">Cepções</span><span class="sxs-lookup"><span data-stu-id="66b66-116">Sidebar</span></span>

<span data-ttu-id="66b66-117">Ao lado da área de conteúdo principal da página de perfil de dispositivo é a barra lateral.</span><span class="sxs-lookup"><span data-stu-id="66b66-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![Imagem da guia de barra lateral para perfil de dispositivo](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="66b66-119">A barra lateral lista o nome completo do dispositivo e o nível de exposição.</span><span class="sxs-lookup"><span data-stu-id="66b66-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="66b66-120">Ele também fornece algumas informações básicas importantes em subseções pequenas que podem ser ativadas ou abertas ou fechadas, como:</span><span class="sxs-lookup"><span data-stu-id="66b66-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="66b66-121">**Marcas** -qualquer Microsoft defender para ponto de extremidade, Microsoft defender para identidade ou marcas personalizadas associadas ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="66b66-121">**Tags** - Any Microsoft Defender for Endpoint, Microsoft Defender for Identity, or custom tags associated with the device.</span></span> <span data-ttu-id="66b66-122">Marcas do Microsoft defender for Identity não são editáveis.</span><span class="sxs-lookup"><span data-stu-id="66b66-122">Tags from Microsoft Defender for Identity are not editable.</span></span>
* <span data-ttu-id="66b66-123">**Informações de segurança** -incidentes abertos e alertas ativos.</span><span class="sxs-lookup"><span data-stu-id="66b66-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="66b66-124">Os dispositivos registrados no Microsoft defender para ponto de extremidade também exibirão o nível de exposição e o nível de risco.</span><span class="sxs-lookup"><span data-stu-id="66b66-124">Devices enrolled in Microsoft Defender for Endpoint will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="66b66-125">O nível de exposição se relaciona com o quanto o dispositivo está em conformidade com as recomendações de segurança, enquanto o nível de risco é calculado com base em vários fatores, incluindo os tipos e a gravidade dos alertas ativos.</span><span class="sxs-lookup"><span data-stu-id="66b66-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="66b66-126">**Detalhes do dispositivo** -domínio, sistema operacional, carimbo de data/hora para o momento em que o dispositivo foi visto pela primeira vez, endereços IP, recursos.</span><span class="sxs-lookup"><span data-stu-id="66b66-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="66b66-127">Os dispositivos registrados no Microsoft defender para ponto de extremidade também exibem o estado de integridade.</span><span class="sxs-lookup"><span data-stu-id="66b66-127">Devices enrolled in Microsoft Defender for Endpoint also display health state.</span></span> <span data-ttu-id="66b66-128">Os dispositivos registrados no Microsoft defender para identidade exibirão o nome SAM e um carimbo de data/hora para quando o dispositivo foi criado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="66b66-128">Devices enrolled in Microsoft Defender for Identity will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="66b66-129">**Atividade de rede** -carimbos de data/hora pela primeira vez e última vez em que o dispositivo foi visto na rede.</span><span class="sxs-lookup"><span data-stu-id="66b66-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="66b66-130">**Dados de diretório** ( *somente para dispositivos registrados no Microsoft defender para identidade* )-sinalizadores de [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) , [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names)e associações de grupo.</span><span class="sxs-lookup"><span data-stu-id="66b66-130">**Directory data** ( *only for devices enrolled in Microsoft Defender for Identity* ) - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="66b66-131">Ações de resposta</span><span class="sxs-lookup"><span data-stu-id="66b66-131">Response actions</span></span>

<span data-ttu-id="66b66-132">As ações de resposta oferecem uma maneira rápida de se defender e analisar ameaças.</span><span class="sxs-lookup"><span data-stu-id="66b66-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Imagem da barra de ações para o perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="66b66-134">As [ações de resposta](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) só estarão disponíveis se o dispositivo estiver inscrito no Microsoft defender para ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="66b66-134">[Response actions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender for Endpoint.</span></span>
> * <span data-ttu-id="66b66-135">Os dispositivos que estão registrados no Microsoft defender para ponto de extremidade podem exibir números diferentes de ações de resposta, com base no so do dispositivo e no número da versão.</span><span class="sxs-lookup"><span data-stu-id="66b66-135">Devices that are enrolled in Microsoft Defender for Endpoint may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="66b66-136">As ações disponíveis na página perfil do dispositivo incluem:</span><span class="sxs-lookup"><span data-stu-id="66b66-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="66b66-137">**Manage Tags** – atualiza as marcas personalizadas que você aplicou a este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="66b66-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="66b66-138">**Isolar dispositivo** -isola o dispositivo da rede da sua organização enquanto o mantém conectado ao Microsoft defender para ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="66b66-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="66b66-139">Você pode optar por permitir que o Outlook, o Teams e o Skype for Business sejam executados enquanto o dispositivo é isolado, para fins de comunicação.</span><span class="sxs-lookup"><span data-stu-id="66b66-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="66b66-140">**Central de ações** -exiba o status das ações enviadas.</span><span class="sxs-lookup"><span data-stu-id="66b66-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="66b66-141">Disponível somente se outra ação já tiver sido selecionada.</span><span class="sxs-lookup"><span data-stu-id="66b66-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="66b66-142">**Restringir execução de aplicativo** -impede que aplicativos não assinados pela Microsoft sejam executados.</span><span class="sxs-lookup"><span data-stu-id="66b66-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="66b66-143">**Execute verificação antivírus** – atualiza as definições do Windows Defender antivírus e executa imediatamente uma verificação antivírus.</span><span class="sxs-lookup"><span data-stu-id="66b66-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="66b66-144">Escolha entre verificação rápida ou verificação completa.</span><span class="sxs-lookup"><span data-stu-id="66b66-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="66b66-145">**Coletar pacote de investigação** -coleta informações sobre o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="66b66-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="66b66-146">Quando a investigação estiver concluída, você pode baixá-la.</span><span class="sxs-lookup"><span data-stu-id="66b66-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="66b66-147">**Iniciar sessão de resposta ao vivo** – carrega um shell remoto no dispositivo para [investigações de segurança aprofundadas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span><span class="sxs-lookup"><span data-stu-id="66b66-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="66b66-148">**Iniciar investigação automatizada** - [investiga e corrige ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)automaticamente.</span><span class="sxs-lookup"><span data-stu-id="66b66-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="66b66-149">Embora seja possível disparar manualmente as investigações automatizadas para executar a partir desta página, [determinadas políticas de alerta](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) disparam investigações automáticas por conta própria.</span><span class="sxs-lookup"><span data-stu-id="66b66-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="66b66-150">**Central de ações** -exibe informações sobre as ações de resposta que estão em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="66b66-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="66b66-151">Seção Tabs</span><span class="sxs-lookup"><span data-stu-id="66b66-151">Tabs section</span></span>

<span data-ttu-id="66b66-152">As guias de perfil de dispositivo permitem que você alterne uma visão geral dos detalhes de segurança sobre o dispositivo e tabelas que contenham uma lista de alertas.</span><span class="sxs-lookup"><span data-stu-id="66b66-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="66b66-153">Os dispositivos registrados no Microsoft defender para ponto de extremidade também exibirão guias que apresentam uma linha do tempo, uma lista de recomendações de segurança, um inventário de software, uma lista de vulnerabilidades descobertas e os KBs ausentes (atualizações de segurança).</span><span class="sxs-lookup"><span data-stu-id="66b66-153">Devices enrolled in Microsoft Defender for Endpoint will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="66b66-154">Guia Visão geral</span><span class="sxs-lookup"><span data-stu-id="66b66-154">Overview tab</span></span>

<span data-ttu-id="66b66-155">A guia padrão é **visão geral**.</span><span class="sxs-lookup"><span data-stu-id="66b66-155">The default tab is **Overview**.</span></span> <span data-ttu-id="66b66-156">Ele fornece uma visão rápida do fato de segurança mais importante sobre o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="66b66-156">It provides a quick look at the most important security fact about the device.</span></span>

![Imagem da guia Visão geral do perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="66b66-158">Aqui, você pode obter uma visão rápida dos alertas ativos do dispositivo e de qualquer usuário conectado no momento.</span><span class="sxs-lookup"><span data-stu-id="66b66-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="66b66-159">Se o dispositivo estiver inscrito no Microsoft defender para ponto de extremidade, você também verá o nível de risco do dispositivo e quaisquer dados disponíveis sobre avaliações de segurança.</span><span class="sxs-lookup"><span data-stu-id="66b66-159">If the device is enrolled in Microsoft Defender for Endpoint, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="66b66-160">As avaliações de segurança descrevem o nível de exposição do dispositivo, fornecem recomendações de segurança e listam softwares afetados e vulnerabilidades descobertas.</span><span class="sxs-lookup"><span data-stu-id="66b66-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="66b66-161">Guia alertas</span><span class="sxs-lookup"><span data-stu-id="66b66-161">Alerts tab</span></span>

<span data-ttu-id="66b66-162">A guia **alertas** contém uma lista de alertas que foram gerados no dispositivo, do Microsoft defender for Identity e do Microsoft defender para ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="66b66-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span>

![Imagem da guia alertas para o perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="66b66-164">Você pode personalizar o número de itens exibidos, bem como quais colunas são exibidas para cada item.</span><span class="sxs-lookup"><span data-stu-id="66b66-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="66b66-165">O comportamento padrão é listar trinta itens por página.</span><span class="sxs-lookup"><span data-stu-id="66b66-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="66b66-166">As colunas nesta guia incluem informações sobre a gravidade da ameaça que disparou o alerta, bem como o status, o estado de investigação e a quem o alerta foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="66b66-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="66b66-167">A coluna de *entidades impactadas* se refere ao dispositivo (entidade) cujo perfil você está exibindo atualmente, além de outros dispositivos na rede que são afetados.</span><span class="sxs-lookup"><span data-stu-id="66b66-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="66b66-168">Selecionar um item da lista abrirá um submenu que contém ainda mais informações sobre o alerta selecionado.</span><span class="sxs-lookup"><span data-stu-id="66b66-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="66b66-169">Essa lista pode ser filtrada por severidade, status ou quem foi atribuído ao alerta.</span><span class="sxs-lookup"><span data-stu-id="66b66-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="66b66-170">Guia linha do tempo</span><span class="sxs-lookup"><span data-stu-id="66b66-170">Timeline tab</span></span>

<span data-ttu-id="66b66-171">A guia **linha do tempo** inclui um gráfico interativo e cronológico de todos os eventos gerados no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="66b66-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="66b66-172">Ao mover a área realçada do gráfico para a esquerda ou direita, você pode exibir eventos por diferentes períodos de tempo.</span><span class="sxs-lookup"><span data-stu-id="66b66-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="66b66-173">Você também pode escolher um intervalo de datas personalizado no menu suspenso entre o gráfico interativo e a lista de eventos.</span><span class="sxs-lookup"><span data-stu-id="66b66-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="66b66-174">Abaixo do gráfico há uma lista de eventos para o intervalo de datas selecionado.</span><span class="sxs-lookup"><span data-stu-id="66b66-174">Below the chart is a list of events for the selected range of dates.</span></span>

![Imagem da guia linha do tempo para o perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="66b66-176">O número de itens exibidos e as colunas na lista podem ser personalizados.</span><span class="sxs-lookup"><span data-stu-id="66b66-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="66b66-177">As colunas padrão listam a hora do evento, o usuário ativo, o tipo de ação, as entidades (processos) e informações adicionais sobre o evento.</span><span class="sxs-lookup"><span data-stu-id="66b66-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="66b66-178">Selecionar um item da lista abrirá um submenu que exibe um gráfico de entidades de evento, mostrando os processos pai e filho envolvidos no evento.</span><span class="sxs-lookup"><span data-stu-id="66b66-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="66b66-179">A lista pode ser filtrada pelo tipo específico de evento; por exemplo, eventos do registro ou eventos de tela inteligente.</span><span class="sxs-lookup"><span data-stu-id="66b66-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="66b66-180">A lista também pode ser exportada para um arquivo CSV para download.</span><span class="sxs-lookup"><span data-stu-id="66b66-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="66b66-181">Embora o arquivo não seja limitado por número de eventos, o intervalo de tempo máximo que você pode escolher para exportar é de sete dias.</span><span class="sxs-lookup"><span data-stu-id="66b66-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="66b66-182">Guia recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="66b66-182">Security recommendations tab</span></span>

<span data-ttu-id="66b66-183">A guia **recomendações de segurança** lista as ações que você pode tomar para proteger o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="66b66-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="66b66-184">Selecionar um item nessa lista abrirá um submenu onde você pode obter instruções sobre como aplicar a recomendação.</span><span class="sxs-lookup"><span data-stu-id="66b66-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Imagem da guia recomendações de segurança para o perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="66b66-186">Assim como com as guias anteriores, o número de itens exibidos por página, bem como quais colunas estão visíveis, podem ser personalizados.</span><span class="sxs-lookup"><span data-stu-id="66b66-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="66b66-187">O modo de exibição padrão inclui colunas que detalham as desvantagens de segurança abordadas, a ameaça associada, o componente relacionado ou o software afetado pela ameaça e muito mais.</span><span class="sxs-lookup"><span data-stu-id="66b66-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="66b66-188">Os itens podem ser filtrados pelo status da recomendação.</span><span class="sxs-lookup"><span data-stu-id="66b66-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="66b66-189">Inventário de software</span><span class="sxs-lookup"><span data-stu-id="66b66-189">Software inventory</span></span>

<span data-ttu-id="66b66-190">A guia **inventário de software** lista o software instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="66b66-190">The **Software inventory** tab lists software installed on the device.</span></span>

![Imagem da guia Inventário de software para o perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="66b66-192">O modo de exibição padrão exibe o fornecedor do software, o número da versão instalada, o número de deficiências de software conhecidas, informações sobre ameaças, código do produto e marcas.</span><span class="sxs-lookup"><span data-stu-id="66b66-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="66b66-193">O número de itens exibidos e quais colunas são exibidas podem ser personalizados.</span><span class="sxs-lookup"><span data-stu-id="66b66-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="66b66-194">Selecionar um item dessa lista abre um submenu contendo mais detalhes sobre o software selecionado, bem como o caminho e o carimbo de data/hora da última vez que o software foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="66b66-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="66b66-195">Essa lista pode ser filtrada pelo código do produto.</span><span class="sxs-lookup"><span data-stu-id="66b66-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="66b66-196">Guia vulnerabilidades descobertas</span><span class="sxs-lookup"><span data-stu-id="66b66-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="66b66-197">A guia **vulnerabilidades descobertas** lista as vulnerabilidades e explorações comuns (CVEs) que podem afetar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="66b66-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Imagem da guia vulnerabilidades descobertas para o perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="66b66-199">O modo de exibição padrão lista a gravidade do CVE, a pontuação de vulnerabilidade comum (CVS), o software relacionado ao CVE, quando o CVE foi publicado, quando o CVE foi atualizado pela última vez e ameaças associadas ao CVE.</span><span class="sxs-lookup"><span data-stu-id="66b66-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="66b66-200">Assim como as guias anteriores, o número de itens exibidos e as colunas visíveis podem ser personalizados.</span><span class="sxs-lookup"><span data-stu-id="66b66-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="66b66-201">Selecionar um item da lista abrirá um submenu que descreve o CVE.</span><span class="sxs-lookup"><span data-stu-id="66b66-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="66b66-202">KB ausentes</span><span class="sxs-lookup"><span data-stu-id="66b66-202">Missing KBs</span></span>

<span data-ttu-id="66b66-203">A guia **KB ausentes** lista as atualizações da Microsoft que ainda devem ser aplicadas ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="66b66-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="66b66-204">Os "KBs" em questão são [artigos da base de conhecimento](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) que descrevem essas atualizações; por exemplo, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="66b66-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Imagem da guia ausente de KB para o perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="66b66-206">O modo de exibição padrão lista o boletim que contém as atualizações, a versão do sistema operacional, os produtos afetados, os CVEs tratados, o número do KB e as marcas.</span><span class="sxs-lookup"><span data-stu-id="66b66-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="66b66-207">O número de itens exibidos por página e quais colunas são exibidas podem ser personalizados.</span><span class="sxs-lookup"><span data-stu-id="66b66-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="66b66-208">Selecionar um item abrirá um submenu que vincule à atualização.</span><span class="sxs-lookup"><span data-stu-id="66b66-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="66b66-209">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="66b66-209">Related topics</span></span>

* [<span data-ttu-id="66b66-210">Visão geral do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="66b66-210">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="66b66-211">Ativar o Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="66b66-211">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
* [<span data-ttu-id="66b66-212">Investigar entidades em dispositivos, usando resposta ao vivo</span><span class="sxs-lookup"><span data-stu-id="66b66-212">Investigate entities on devices, using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="66b66-213">Investigação e resposta automatizadas (AIR) no Office 365</span><span class="sxs-lookup"><span data-stu-id="66b66-213">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
