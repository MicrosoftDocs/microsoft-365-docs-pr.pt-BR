---
title: Perfil de dispositivo no portal de segurança do Microsoft 365
description: Exibir níveis de risco e exposição para um dispositivo em sua organização. Analise as ameaças passadas e presentes e proteja o dispositivo com as atualizações mais recentes.
keywords: segurança, malware, Microsoft 365, M365, Proteção contra Ameaças da Microsoft, MTP, central de segurança, Microsoft Defender ATP, Office 365 ATP, Azure ATP, página de dispositivo, perfil de dispositivo, página de máquina, perfil de máquina
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: c51c002d263452142a1bcf6fc5603d6ec4ef4cf7
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51197964"
---
# <a name="device-profile-page"></a><span data-ttu-id="33228-105">Página de perfil de dispositivo</span><span class="sxs-lookup"><span data-stu-id="33228-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="33228-106">O portal de segurança do Microsoft 365 fornece páginas de perfil de dispositivo, para que você possa avaliar rapidamente a saúde e o status dos dispositivos em sua rede.</span><span class="sxs-lookup"><span data-stu-id="33228-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33228-107">A página de perfil de dispositivo pode parecer um pouco diferente, dependendo se o dispositivo está inscrito no Microsoft Defender para Ponto de Extremidade, No Microsoft Defender para Identidade ou ambos.</span><span class="sxs-lookup"><span data-stu-id="33228-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender for Endpoint, Microsoft Defender for Identity, or both.</span></span>

<span data-ttu-id="33228-108">Se o dispositivo estiver inscrito no Microsoft Defender para Ponto de Extremidade, você também poderá usar a página de perfil do dispositivo para executar algumas tarefas comuns de segurança.</span><span class="sxs-lookup"><span data-stu-id="33228-108">If the device is enrolled in Microsoft Defender for Endpoint, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="33228-109">Navegando a página de perfil do dispositivo</span><span class="sxs-lookup"><span data-stu-id="33228-109">Navigating the device profile page</span></span>

<span data-ttu-id="33228-110">A página de perfil é dividida em várias seções amplas.</span><span class="sxs-lookup"><span data-stu-id="33228-110">The profile page is broken up into several broad sections.</span></span>

![Imagem da página de perfil do dispositivo com (1) Área de tabulação (2) Barra lateral e (3) Ações realçadas em vermelho](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="33228-112">A barra lateral (1) lista detalhes básicos sobre o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33228-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="33228-113">A área de conteúdo principal (2) contém guias que você pode alternar para exibir diferentes tipos de informações sobre o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33228-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="33228-114">Se o dispositivo estiver inscrito no Microsoft Defender para Ponto de Extremidade, você também verá uma lista de ações de resposta (3).</span><span class="sxs-lookup"><span data-stu-id="33228-114">If the device is enrolled in Microsoft Defender for Endpoint, you will also see a list of response actions (3).</span></span> <span data-ttu-id="33228-115">As ações de resposta permitem que você execute tarefas comuns relacionadas à segurança.</span><span class="sxs-lookup"><span data-stu-id="33228-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="33228-116">Barra lateral</span><span class="sxs-lookup"><span data-stu-id="33228-116">Sidebar</span></span>

<span data-ttu-id="33228-117">Ao lado da área de conteúdo principal da página de perfil de dispositivo está a barra lateral.</span><span class="sxs-lookup"><span data-stu-id="33228-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![Imagem da guia sidebar para perfil do dispositivo](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="33228-119">A barra lateral lista o nome completo do dispositivo e o nível de exposição.</span><span class="sxs-lookup"><span data-stu-id="33228-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="33228-120">Ele também fornece algumas informações básicas importantes em pequenas subseções que podem ser alternadas abertas ou fechadas, como:</span><span class="sxs-lookup"><span data-stu-id="33228-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="33228-121">**Tags** - Qualquer Microsoft Defender para Ponto de Extremidade, Microsoft Defender para Identidade ou marcas personalizadas associadas ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33228-121">**Tags** - Any Microsoft Defender for Endpoint, Microsoft Defender for Identity, or custom tags associated with the device.</span></span> <span data-ttu-id="33228-122">As marcas do Microsoft Defender para Identidade não são editáveis.</span><span class="sxs-lookup"><span data-stu-id="33228-122">Tags from Microsoft Defender for Identity are not editable.</span></span>
* <span data-ttu-id="33228-123">**Informações de segurança** - Abra incidentes e alertas ativos.</span><span class="sxs-lookup"><span data-stu-id="33228-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="33228-124">Os dispositivos inscritos no Microsoft Defender para Ponto de Extremidade também exibirão o nível de exposição e o nível de risco.</span><span class="sxs-lookup"><span data-stu-id="33228-124">Devices enrolled in Microsoft Defender for Endpoint will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="33228-125">O nível de exposição diz respeito ao quanto o dispositivo está em conformidade com as recomendações de segurança, enquanto o nível de risco é calculado com base em vários fatores, incluindo os tipos e a gravidade dos alertas ativos.</span><span class="sxs-lookup"><span data-stu-id="33228-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="33228-126">**Detalhes do** dispositivo - Domínio, sistema operacional, data/hora para quando o dispositivo foi visto pela primeira vez, endereços IP, recursos.</span><span class="sxs-lookup"><span data-stu-id="33228-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="33228-127">Os dispositivos inscritos no Microsoft Defender para Ponto de Extremidade também exibem estado de saúde.</span><span class="sxs-lookup"><span data-stu-id="33228-127">Devices enrolled in Microsoft Defender for Endpoint also display health state.</span></span> <span data-ttu-id="33228-128">Os dispositivos inscritos no Microsoft Defender para Identidade exibirão o nome SAM e um data/hora para quando o dispositivo foi criado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="33228-128">Devices enrolled in Microsoft Defender for Identity will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="33228-129">**Atividade de rede** - Timestamps pela primeira e última vez que o dispositivo foi visto na rede.</span><span class="sxs-lookup"><span data-stu-id="33228-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="33228-130">**Dados de** diretório (*somente para dispositivos inscritos* no Microsoft Defender para Identidade ) - sinalizadores [UAC,](/windows/security/identity-protection/user-account-control/user-account-control-overview) [SPNs](/windows/win32/ad/service-principal-names)e associações de grupo.</span><span class="sxs-lookup"><span data-stu-id="33228-130">**Directory data** (*only for devices enrolled in Microsoft Defender for Identity*) - [UAC](/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="33228-131">Ações de resposta</span><span class="sxs-lookup"><span data-stu-id="33228-131">Response actions</span></span>

<span data-ttu-id="33228-132">As ações de resposta oferecem uma maneira rápida de se defender e analisar ameaças.</span><span class="sxs-lookup"><span data-stu-id="33228-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Imagem da barra de ações para perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="33228-134">[As ações de](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) resposta só estarão disponíveis se o dispositivo estiver inscrito no Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="33228-134">[Response actions](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender for Endpoint.</span></span>
> * <span data-ttu-id="33228-135">Dispositivos que estão inscritos no Microsoft Defender para Ponto de Extremidade podem exibir números diferentes de ações de resposta, com base no sistema operacional do dispositivo e no número da versão.</span><span class="sxs-lookup"><span data-stu-id="33228-135">Devices that are enrolled in Microsoft Defender for Endpoint may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="33228-136">As ações disponíveis na página de perfil do dispositivo incluem:</span><span class="sxs-lookup"><span data-stu-id="33228-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="33228-137">**Gerenciar marcas** - Atualiza marcas personalizadas que você aplicou a este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33228-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="33228-138">**Isolar o** dispositivo - isola o dispositivo da rede da sua organização enquanto o mantém conectado ao Microsoft Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="33228-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="33228-139">Você pode optar por permitir que o Outlook, o Teams e o Skype for Business executem enquanto o dispositivo está isolado, para fins de comunicação.</span><span class="sxs-lookup"><span data-stu-id="33228-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="33228-140">**Centro de ações** - Exibir o status das ações enviadas.</span><span class="sxs-lookup"><span data-stu-id="33228-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="33228-141">Disponível somente se outra ação já tiver sido selecionada.</span><span class="sxs-lookup"><span data-stu-id="33228-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="33228-142">**Restringir a execução do** aplicativo - impede que aplicativos que não são assinados pela Microsoft sejam executados.</span><span class="sxs-lookup"><span data-stu-id="33228-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="33228-143">**Executar a verificação antivírus** - atualiza Windows Defender definições do Antivírus e executa imediatamente uma verificação antivírus.</span><span class="sxs-lookup"><span data-stu-id="33228-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="33228-144">Escolha entre Verificação Rápida ou Verificação Completa.</span><span class="sxs-lookup"><span data-stu-id="33228-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="33228-145">**Coletar pacote de investigação** - Coleta informações sobre o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33228-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="33228-146">Quando a investigação for concluída, você poderá baixá-la.</span><span class="sxs-lookup"><span data-stu-id="33228-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="33228-147">**Iniciar Sessão de Resposta Ao Vivo** - Carrega um shell remoto no dispositivo para [investigações detalhadas de segurança.](/microsoft-365/security/defender-endpoint/live-response)</span><span class="sxs-lookup"><span data-stu-id="33228-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](/microsoft-365/security/defender-endpoint/live-response).</span></span>
* <span data-ttu-id="33228-148">**Iniciar investigação automatizada** - Investiga e corrigi automaticamente [ameaças.](../office-365-security/office-365-air.md)</span><span class="sxs-lookup"><span data-stu-id="33228-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](../office-365-security/office-365-air.md).</span></span> <span data-ttu-id="33228-149">Embora você possa disparar manualmente investigações automatizadas para executar a partir desta [página,](../../compliance/alert-policies.md?view=o365-worldwide#default-alert-policies) determinadas políticas de alerta disparam investigações automáticas por conta própria.</span><span class="sxs-lookup"><span data-stu-id="33228-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](../../compliance/alert-policies.md?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="33228-150">**Centro de ações** - Exibe informações sobre todas as ações de resposta que estão sendo executados no momento.</span><span class="sxs-lookup"><span data-stu-id="33228-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="33228-151">Seção Tabs</span><span class="sxs-lookup"><span data-stu-id="33228-151">Tabs section</span></span>

<span data-ttu-id="33228-152">As guias de perfil de dispositivo permitem que você alterne uma visão geral dos detalhes de segurança sobre o dispositivo e tabelas que contêm uma lista de alertas.</span><span class="sxs-lookup"><span data-stu-id="33228-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="33228-153">Os dispositivos inscritos no Microsoft Defender para Ponto de Extremidade também exibirão guias que apresentam uma linha do tempo, uma lista de recomendações de segurança, um inventário de software, uma lista de vulnerabilidades descobertas e KBs ausentes (atualizações de segurança).</span><span class="sxs-lookup"><span data-stu-id="33228-153">Devices enrolled in Microsoft Defender for Endpoint will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="33228-154">Guia Visão geral</span><span class="sxs-lookup"><span data-stu-id="33228-154">Overview tab</span></span>

<span data-ttu-id="33228-155">A guia padrão é **Visão Geral**.</span><span class="sxs-lookup"><span data-stu-id="33228-155">The default tab is **Overview**.</span></span> <span data-ttu-id="33228-156">Ele fornece uma rápida olhada no fato de segurança mais importante sobre o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33228-156">It provides a quick look at the most important security fact about the device.</span></span>

![Imagem da guia visão geral do perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="33228-158">Aqui, você pode ver rapidamente os alertas ativos do dispositivo e qualquer usuário conectado no momento.</span><span class="sxs-lookup"><span data-stu-id="33228-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="33228-159">Se o dispositivo estiver inscrito no Microsoft Defender para Ponto de Extremidade, você também verá o nível de risco do dispositivo e todos os dados disponíveis sobre avaliações de segurança.</span><span class="sxs-lookup"><span data-stu-id="33228-159">If the device is enrolled in Microsoft Defender for Endpoint, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="33228-160">As avaliações de segurança descrevem o nível de exposição do dispositivo, fornecem recomendações de segurança e listam software afetado e vulnerabilidades descobertas.</span><span class="sxs-lookup"><span data-stu-id="33228-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="33228-161">Guia Alertas</span><span class="sxs-lookup"><span data-stu-id="33228-161">Alerts tab</span></span>

<span data-ttu-id="33228-162">A **guia Alertas** contém uma lista de alertas que foram gerados no dispositivo, tanto do Microsoft Defender para Identidade quanto do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="33228-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span>

![Imagem da guia alertas para o perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="33228-164">Você pode personalizar o número de itens exibidos, bem como quais colunas são exibidas para cada item.</span><span class="sxs-lookup"><span data-stu-id="33228-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="33228-165">O comportamento padrão é listar trinta itens por página.</span><span class="sxs-lookup"><span data-stu-id="33228-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="33228-166">As colunas nesta guia incluem informações sobre a gravidade da ameaça que disparou o alerta, bem como status, estado de investigação e a quem o alerta foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="33228-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="33228-167">A *coluna entidades* afetadas refere-se ao dispositivo (entidade) cujo perfil você está visualizando no momento, além de quaisquer outros dispositivos em sua rede afetados.</span><span class="sxs-lookup"><span data-stu-id="33228-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="33228-168">Selecionar um item desta lista abrirá um sobrevoo contendo ainda mais informações sobre o alerta selecionado.</span><span class="sxs-lookup"><span data-stu-id="33228-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="33228-169">Essa lista pode ser filtrada por gravidade, status ou a quem o alerta foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="33228-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="33228-170">Guia Linha do Tempo</span><span class="sxs-lookup"><span data-stu-id="33228-170">Timeline tab</span></span>

<span data-ttu-id="33228-171">A **guia Linha** do Tempo inclui um gráfico interativo e cronologicamente de todos os eventos gerados no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33228-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="33228-172">Ao mover a área realçada do gráfico para a esquerda ou para a direita, você pode exibir eventos em diferentes períodos de tempo.</span><span class="sxs-lookup"><span data-stu-id="33228-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="33228-173">Você também pode escolher um intervalo personalizado de datas no menu suspenso entre o gráfico interativo e a lista de eventos.</span><span class="sxs-lookup"><span data-stu-id="33228-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="33228-174">Abaixo do gráfico está uma lista de eventos para o intervalo de datas selecionado.</span><span class="sxs-lookup"><span data-stu-id="33228-174">Below the chart is a list of events for the selected range of dates.</span></span>

![Imagem da guia linha do tempo do perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="33228-176">O número de itens exibidos e as colunas na lista podem ser personalizadas.</span><span class="sxs-lookup"><span data-stu-id="33228-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="33228-177">As colunas padrão listam a hora do evento, o usuário ativo, o tipo de ação, as entidades (processos) e informações adicionais sobre o evento.</span><span class="sxs-lookup"><span data-stu-id="33228-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="33228-178">Selecionar um item desta lista abrirá um sobrevoo exibindo um gráfico de entidades de evento, mostrando os processos pai e filho envolvidos no evento.</span><span class="sxs-lookup"><span data-stu-id="33228-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="33228-179">A lista pode ser filtrada pelo tipo específico de evento; por exemplo, eventos do Registro ou Eventos de Tela Inteligente.</span><span class="sxs-lookup"><span data-stu-id="33228-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="33228-180">A lista também pode ser exportada para um arquivo CSV, para download.</span><span class="sxs-lookup"><span data-stu-id="33228-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="33228-181">Embora o arquivo não seja limitado pelo número de eventos, o intervalo máximo de tempo que você pode optar por exportar é de sete dias.</span><span class="sxs-lookup"><span data-stu-id="33228-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="33228-182">Guia Recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="33228-182">Security recommendations tab</span></span>

<span data-ttu-id="33228-183">A **guia Recomendações de segurança** lista ações que você pode tomar para proteger o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33228-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="33228-184">Selecionar um item nesta lista abrirá um sobrevoo onde você pode obter instruções sobre como aplicar a recomendação.</span><span class="sxs-lookup"><span data-stu-id="33228-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Guia De recomendações de segurança para perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="33228-186">Assim como nas guias anteriores, o número de itens exibidos por página, bem como quais colunas estão visíveis, pode ser personalizado.</span><span class="sxs-lookup"><span data-stu-id="33228-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="33228-187">O modo de exibição padrão inclui colunas que detalham as deficiências de segurança abordadas, a ameaça associada, o componente ou software relacionado afetado pela ameaça e muito mais.</span><span class="sxs-lookup"><span data-stu-id="33228-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="33228-188">Os itens podem ser filtrados pelo status da recomendação.</span><span class="sxs-lookup"><span data-stu-id="33228-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="33228-189">Inventário de software</span><span class="sxs-lookup"><span data-stu-id="33228-189">Software inventory</span></span>

<span data-ttu-id="33228-190">A **guia Inventário de** software lista software instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33228-190">The **Software inventory** tab lists software installed on the device.</span></span>

![Imagem da guia inventário de software para perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="33228-192">O modo de exibição padrão exibe o fornecedor de software, o número de versão instalado, o número de pontos fracos de software conhecidos, as percepções sobre ameaças, o código do produto e as marcas.</span><span class="sxs-lookup"><span data-stu-id="33228-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="33228-193">O número de itens exibidos e quais colunas são exibidas podem ser personalizadas.</span><span class="sxs-lookup"><span data-stu-id="33228-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="33228-194">Selecionar um item desta lista abre um flyout contendo mais detalhes sobre o software selecionado, bem como o caminho e o data/hora da última vez em que o software foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="33228-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="33228-195">Essa lista pode ser filtrada pelo código do produto.</span><span class="sxs-lookup"><span data-stu-id="33228-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="33228-196">Guia Vulnerabilidades descobertas</span><span class="sxs-lookup"><span data-stu-id="33228-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="33228-197">A **guia Vulnerabilidades Descobertas** lista quaisquer Vulnerabilidades Comuns e Explorações (CVEs) que possam afetar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33228-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Imagem da guia vulnerabilidades descobertas para perfil de dispositivo](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="33228-199">O modo de exibição padrão lista a gravidade do CVE, a Pontuação comum de vulnerabilidades (CVS), o software relacionado à CVE, quando o CVE foi publicado, quando a CVE foi atualizada pela última vez e as ameaças associadas à CVE.</span><span class="sxs-lookup"><span data-stu-id="33228-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="33228-200">Assim como nas guias anteriores, o número de itens exibidos e quais colunas estão visíveis podem ser personalizados.</span><span class="sxs-lookup"><span data-stu-id="33228-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="33228-201">Selecionar um item desta lista abrirá um sobrevoo que descreve o CVE.</span><span class="sxs-lookup"><span data-stu-id="33228-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="33228-202">KBs ausentes</span><span class="sxs-lookup"><span data-stu-id="33228-202">Missing KBs</span></span>

<span data-ttu-id="33228-203">A **guia KBs Ausentes** lista todas as Atualizações da Microsoft que ainda não foram aplicadas ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="33228-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="33228-204">Os "KBs" em questão são artigos [da Base](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) de Dados de Conhecimento que descrevem essas atualizações; por exemplo, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="33228-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Imagem da guia kbs ausente para o perfil do dispositivo](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="33228-206">O modo de exibição padrão lista o boletim que contém as atualizações, versão do sistema operacional, produtos afetados, CVEs endereçadas, o número KB e as marcas.</span><span class="sxs-lookup"><span data-stu-id="33228-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="33228-207">O número de itens exibidos por página e quais colunas são exibidas podem ser personalizadas.</span><span class="sxs-lookup"><span data-stu-id="33228-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="33228-208">Selecionar um item abrirá um flyout que se vincula à atualização.</span><span class="sxs-lookup"><span data-stu-id="33228-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="33228-209">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="33228-209">Related topics</span></span>

* [<span data-ttu-id="33228-210">Visão geral do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33228-210">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
* [<span data-ttu-id="33228-211">Ativar o Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="33228-211">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
* [<span data-ttu-id="33228-212">Investigar entidades em dispositivos usando a resposta ao vivo</span><span class="sxs-lookup"><span data-stu-id="33228-212">Investigate entities on devices, using live response</span></span>](../defender-endpoint/live-response.md)
* [<span data-ttu-id="33228-213">Investigação e resposta automatizadas (AIR) no Office 365</span><span class="sxs-lookup"><span data-stu-id="33228-213">Automated investigation and response (AIR) in Office 365</span></span>](../office-365-security/office-365-air.md)
