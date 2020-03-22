---
title: Perfil do computador no portal de segurança do Microsoft 365
description: Exibir os níveis de risco e de exposição de um dispositivo em sua organização. Analise as ameaças passadas e apresente e proteja a máquina com as atualizações mais recentes.
keywords: segurança, malware, Microsoft 365, M365, proteção contra ameaças da Microsoft, MTP, central de segurança, Microsoft defender ATP, Office 365 ATP, Azure ATP, página de máquina, lista de máquina, perfil de máquina
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
ms.openlocfilehash: 1dfb567c8e6b8573397d503ae27c0aceb447c916
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895458"
---
# <a name="machine-profile-page"></a><span data-ttu-id="aa5f3-105">Página do perfil da máquina</span><span class="sxs-lookup"><span data-stu-id="aa5f3-105">Machine profile page</span></span>

<span data-ttu-id="aa5f3-106">O portal de segurança do Microsoft 365 fornece páginas de perfil de máquina para que você possa avaliar a integridade e o status dos dispositivos na sua rede.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-106">The Microsoft 365 security portal provides you with Machine profile pages, so you can assess the health and status of devices on your network.</span></span> <span data-ttu-id="aa5f3-107">Cada página de perfil de máquina contém uma infinidade de informações sobre o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-107">Each Machine profile page contains a wealth of information about the device.</span></span>

<span data-ttu-id="aa5f3-108">Você pode revisar informações detalhadas sobre qual software é executado, os eventos de segurança e os alertas de segurança passados e apresentar e encontrar links para patches de software relevantes.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-108">You can review in-depth information about what software it is running, any past and present security events or alerts, and find links to relevant software patches.</span></span>

<span data-ttu-id="aa5f3-109">Você também pode usar o perfil de máquina para executar tarefas comuns relacionadas à segurança e rapidamente examinar detalhes básicos sobre o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-109">You can also use the Machine profile to perform common security-related tasks, and quickly review basic details about the device.</span></span>

## <a name="navigating-the-machine-profile-page"></a><span data-ttu-id="aa5f3-110">Navegando na página de perfil de máquina</span><span class="sxs-lookup"><span data-stu-id="aa5f3-110">Navigating the Machine profile page</span></span>

<span data-ttu-id="aa5f3-111">A página de perfil de máquina é dividida em três seções.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-111">The machine profile page is broken up into three sections.</span></span>

![Imagem da página de perfil da máquina com (1) barra de guias (2) barra lateral e (3) ações realçadas em vermelho](../../media/mtp-machine-profile/mtp-machine-profile-all.png)

<span data-ttu-id="aa5f3-113">A área de conteúdo principal (1) contém sete guias que podem ser alternadas para exibir diferentes tipos de informações sobre a máquina.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-113">The main content area (1) contains seven tabs that you can toggle through to view different kinds of information about the machine.</span></span>

<span data-ttu-id="aa5f3-114">A barra lateral (2) lista detalhes básicos sobre o computador.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-114">The sidebar (2) lists basic details about the machine.</span></span>

<span data-ttu-id="aa5f3-115">Há também ações de resposta disponíveis em um cabeçalho (3) antes da barra lateral e das seções de conteúdo principal.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-115">There are also response actions available in a header (3) before the sidebar and main content sections.</span></span> <span data-ttu-id="aa5f3-116">Você pode usar as ações neste cabeçalho para executar tarefas comuns relacionadas à segurança.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-116">You can use the actions in this header to perform common security-related tasks.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="aa5f3-117">Seção Tabs</span><span class="sxs-lookup"><span data-stu-id="aa5f3-117">Tabs section</span></span>

<span data-ttu-id="aa5f3-118">As guias de perfil de máquina permitem que você alterne uma visão geral dos detalhes de segurança sobre a máquina e tabelas que contenham uma lista de alertas, uma linha do tempo, uma lista de recomendações de segurança, um inventário de software, uma lista de vulnerabilidades descobertas e faltam KBs (atualizações de segurança).</span><span class="sxs-lookup"><span data-stu-id="aa5f3-118">The Machine profile tabs allow you to toggle through an overview of security details about the machine, and tables containing a list of alerts, a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="aa5f3-119">Guia Visão geral</span><span class="sxs-lookup"><span data-stu-id="aa5f3-119">Overview tab</span></span>

<span data-ttu-id="aa5f3-120">A guia padrão é **visão geral**.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-120">The default tab is **Overview**.</span></span> <span data-ttu-id="aa5f3-121">Ele fornece uma visão rápida do fato de segurança mais importante sobre o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-121">It provides a quick look at the most important security fact about the device.</span></span>

![Imagem da guia Visão geral do perfil do computador](../../media/mtp-machine-profile/overview.png)

<span data-ttu-id="aa5f3-123">Aqui, você pode encontrar um gráfico do nível de risco e dos alertas ativos do dispositivo, qualquer usuário conectado no momento, uma breve lista de usuários mais e menos frequentes e avaliações de segurança que detalham o nível de exposição do dispositivo, recomendações de segurança, softwares afetados e vulnerabilidades descobertas.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-123">Here, you can find a chart of the device's risk level and active alerts, any currently logged on users, a brief list of most and least frequent users, and security assessments that detail the device's exposure level, security recommendations, affected software, and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="aa5f3-124">Guia alertas</span><span class="sxs-lookup"><span data-stu-id="aa5f3-124">Alerts tab</span></span>

<span data-ttu-id="aa5f3-125">A guia **alertas** contém uma lista de alertas que foram relatados no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-125">The **Alerts** tab contains a list of alerts that have been reported on the device.</span></span>

![Imagem da guia alertas para o perfil de máquina](../../media/mtp-machine-profile/alerts.png)

<span data-ttu-id="aa5f3-127">Você pode personalizar o número de itens exibidos, bem como quais colunas são exibidas para cada item.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-127">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="aa5f3-128">O comportamento padrão é listar 30 itens por página e ter 11 colunas alternadas para exibir.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-128">The default behavior is to list 30 items per page, and have 11 columns toggled on to display.</span></span>

<span data-ttu-id="aa5f3-129">As colunas nesta guia incluem informações sobre a gravidade da ameaça que disparou o alerta, bem como o status, o estado de investigação e quem se o alerta foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-129">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who if anyone the alert has been assigned to.</span></span>

<span data-ttu-id="aa5f3-130">A coluna de *entidades impactadas* se refere à máquina (entidade) cujo perfil você está exibindo atualmente, além de qualquer outra máquina em sua rede afetada.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-130">The *impacted entities* column refers to the machine (entity) whose profile you are currently viewing, plus any other machines in your network that are affected.</span></span>

<span data-ttu-id="aa5f3-131">Selecionar um item da lista abrirá um link para o alerta selecionado.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-131">Selecting an item from this list will open a link to the selected alert.</span></span>

<span data-ttu-id="aa5f3-132">Essa lista pode ser filtrada por severidade, status ou destinatário.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-132">This list can be filtered by severity, status, or assignee.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="aa5f3-133">Guia linha do tempo</span><span class="sxs-lookup"><span data-stu-id="aa5f3-133">Timeline tab</span></span>

<span data-ttu-id="aa5f3-134">A guia **linha do tempo** inclui um gráfico de eventos interativo e cronológico gerado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-134">The **Timeline** tab includes a interactive, chronological chart of events raised on the device.</span></span> <span data-ttu-id="aa5f3-135">Ao mover a área realçada do gráfico, você pode exibir eventos por diferentes intervalos de tempo.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-135">By moving the highlighted area of the chart, you can view events over different ranges of time.</span></span> <span data-ttu-id="aa5f3-136">Você também pode digitar um intervalo de datas personalizado.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-136">You can also type in a custom range of dates.</span></span>

<span data-ttu-id="aa5f3-137">Abaixo do gráfico há uma lista de eventos para o intervalo de datas selecionado.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-137">Below the chart is a list of events for the selected range of dates.</span></span>

![Imagem da guia linha do tempo para o perfil do computador](../../media/mtp-machine-profile/timeline.png)

<span data-ttu-id="aa5f3-139">O número de itens exibidos e as colunas na lista podem ser personalizados.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-139">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="aa5f3-140">As colunas padrão listam a hora do evento, o usuário ativo, o tipo de ação, as entidades (processos) e informações adicionais sobre o evento.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-140">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="aa5f3-141">Selecionar um item da lista abrirá um submenu que exibe um gráfico de entidades de evento, mostrando os processos pai e filho que acionaram o evento.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-141">Selecting an item from the list will open a flyout displaying an Event entities graph, showing the parent and child processes that triggered the event.</span></span>

<span data-ttu-id="aa5f3-142">Essa lista pode ser filtrada pelo tipo específico de evento; por exemplo, eventos do registro ou eventos de tela inteligente.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-142">This list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="aa5f3-143">Guia recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="aa5f3-143">Security recommendations tab</span></span>

<span data-ttu-id="aa5f3-144">A guia **recomendações de segurança** lista as ações que você pode tomar para proteger o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-144">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="aa5f3-145">Selecionar um item nessa lista abrirá um submenu onde você pode obter instruções sobre como aplicar a recomendação.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-145">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Imagem da guia recomendações de segurança para o perfil de máquina](../../media/mtp-machine-profile/security-recs.png)

<span data-ttu-id="aa5f3-147">Como com as guias anteriores, o número de itens exibidos por página e quais colunas estão visíveis podem ser personalizados.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-147">As with the previous tabs, the number of items displayed per page and which columns are visible can be customized.</span></span>

<span data-ttu-id="aa5f3-148">O modo de exibição padrão inclui colunas que detalham as desvantagens de segurança abordadas, a ameaça associada, o componente relacionado ou o software afetado pela ameaça e muito mais.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-148">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="aa5f3-149">Os itens podem ser filtrados pelo status da recomendação.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-149">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="aa5f3-150">Inventário de software</span><span class="sxs-lookup"><span data-stu-id="aa5f3-150">Software inventory</span></span>

<span data-ttu-id="aa5f3-151">A guia **inventário de software** lista o software instalado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-151">The **Software inventory** tab lists software installed on the device.</span></span>

![Imagem da guia Inventário de software para o perfil de máquina](../../media/mtp-machine-profile/software-inventory.png)

<span data-ttu-id="aa5f3-153">O modo de exibição padrão exibe o fornecedor do software, o número da versão instalada, o número de deficiências de software conhecidas, informações sobre ameaças, código do produto e marcas.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-153">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="aa5f3-154">O número de itens exibidos e quais colunas são exibidas podem ser personalizados.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-154">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="aa5f3-155">Selecionar um item dessa lista abre um submenu contendo mais detalhes sobre o software selecionado, bem como o caminho e o carimbo de data/hora da última vez que o software foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-155">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="aa5f3-156">Essa lista pode ser filtrada pelo código do produto.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-156">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="aa5f3-157">Guia vulnerabilidades descobertas</span><span class="sxs-lookup"><span data-stu-id="aa5f3-157">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="aa5f3-158">A guia **vulnerabilidades descobertas** lista as vulnerabilidades e explorações comuns (CVEs) que podem afetar o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-158">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Imagem da guia de vulnerabilidades descobertas para o perfil de máquina](../../media/mtp-machine-profile/discovered-vulnerabilities.png)

<span data-ttu-id="aa5f3-160">O modo de exibição padrão lista a gravidade do CVE, a pontuação de vulnerabilidade comum (CVS), o software relacionado ao CVE, quando o CVE foi publicado, quando o CVE foi atualizado pela última vez e ameaças associadas ao CVE.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-160">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="aa5f3-161">Assim como as guias anteriores, o número de itens exibidos e as colunas visíveis podem ser personalizados.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-161">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="aa5f3-162">Selecionar um item da lista abrirá um submenu que descreve o CVE.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-162">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="aa5f3-163">KB ausentes</span><span class="sxs-lookup"><span data-stu-id="aa5f3-163">Missing KBs</span></span>

<span data-ttu-id="aa5f3-164">A guia **KB ausentes** lista as atualizações da Microsoft que ainda devem ser aplicadas ao computador.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-164">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the machine.</span></span> <span data-ttu-id="aa5f3-165">Os "KBs" em questão são [artigos da base de conhecimento](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) que descrevem essas atualizações; por exemplo, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="aa5f3-165">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Imagem da guia ausente de KB para o perfil de máquina](../../media/mtp-machine-profile/missing-kbs.PNG)

<span data-ttu-id="aa5f3-167">O modo de exibição padrão lista o boletim que contém as atualizações, a versão do sistema operacional, os produtos afetados, os CVEs tratados, o número do KB e as marcas.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-167">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="aa5f3-168">O número de itens exibidos por página e quais colunas são exibidas podem ser personalizados.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-168">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="aa5f3-169">Selecionar um item abrirá um submenu que vincule à atualização.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-169">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="sidebar"></a><span data-ttu-id="aa5f3-170">Cepções</span><span class="sxs-lookup"><span data-stu-id="aa5f3-170">Sidebar</span></span>

<span data-ttu-id="aa5f3-171">Ao lado da área de conteúdo principal da página de perfil de máquina é a barra lateral.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-171">Beside the main content area of the Machine profile page is the sidebar.</span></span>

![Imagem da guia de barra lateral para perfil de máquina](../../media/mtp-machine-profile/sidebar.png)

<span data-ttu-id="aa5f3-173">A barra lateral fornece algumas informações básicas importantes em subseções pequenas que podem ser ativadas ou abertas ou fechadas:</span><span class="sxs-lookup"><span data-stu-id="aa5f3-173">The sidebar provides some important basic information in small subsections which can be toggled open or closed:</span></span>

* <span data-ttu-id="aa5f3-174">**Marcas** -qualquer marca associada ao dispositivo</span><span class="sxs-lookup"><span data-stu-id="aa5f3-174">**Tags** - Any tags associated with the device</span></span>
* <span data-ttu-id="aa5f3-175">**Informações de segurança** -incidentes de abertura, alertas ativos, nível de exposição e nível de risco</span><span class="sxs-lookup"><span data-stu-id="aa5f3-175">**Security info** - Open incidents, active alerts, exposure level and risk level</span></span>
* <span data-ttu-id="aa5f3-176">**Detalhes do dispositivo** -domínio, sistema operacional, grupo de ativos, estado de integridade, confidencialidade de dados e endereços IP</span><span class="sxs-lookup"><span data-stu-id="aa5f3-176">**Device details** - Domain, OS, Asset group, health state, data sensitivity, and IP addresses</span></span>
* <span data-ttu-id="aa5f3-177">**Atividade de rede** -carimbos de data/hora pela primeira vez e última vez em que o dispositivo foi visto na rede</span><span class="sxs-lookup"><span data-stu-id="aa5f3-177">**Network activity** - Timestamps for the first time and last time the device was seen on the network</span></span>

<span data-ttu-id="aa5f3-178">Esta seção também inclui o nível de nome e exposição do dispositivo e um ícone para indicar se ele está ativo na rede no momento.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-178">This section also includes the name and exposure level of the device, and an icon to indicate if it is currently active on the network.</span></span>

## <a name="response-actions"></a><span data-ttu-id="aa5f3-179">Ações de resposta</span><span class="sxs-lookup"><span data-stu-id="aa5f3-179">Response actions</span></span>

<span data-ttu-id="aa5f3-180">As ações de resposta oferecem uma maneira rápida de se defender e analisar ameaças.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-180">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Imagem da guia de barra lateral para perfil de máquina](../../media/mtp-machine-profile/actions.PNG)

<span data-ttu-id="aa5f3-182">As ações de resposta disponíveis aqui incluem:</span><span class="sxs-lookup"><span data-stu-id="aa5f3-182">The response actions available to you here include:</span></span>

* <span data-ttu-id="aa5f3-183">**Manage Tags** – atualiza as marcas personalizadas que você aplicou a este dispositivo.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-183">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="aa5f3-184">**Isolar computador** -isola a máquina da rede da sua organização enquanto a mantém conectada à proteção avançada contra ameaças do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-184">**Isolate machine** - Isolates the machine from your organization's network while keeping it connected to Microsoft Defender Advanced Threat Protection.</span></span> <span data-ttu-id="aa5f3-185">Você pode optar por permitir que o Outlook, o Teams e o Skype for Business sejam executados enquanto a máquina estiver isolada, para fins de comunicação.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-185">You can choose to allow Outlook, Teams, and Skype for Business to run while the machine is isolated, for communication purposes.</span></span>
* <span data-ttu-id="aa5f3-186">**Restringir execução de aplicativo** -impede que aplicativos não assinados pela Microsoft sejam executados</span><span class="sxs-lookup"><span data-stu-id="aa5f3-186">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running</span></span>
* <span data-ttu-id="aa5f3-187">**Execute verificação antivírus** – atualiza as definições do Windows Defender antivírus e executa imediatamente uma verificação antivírus.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-187">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="aa5f3-188">Escolha entre verificação rápida ou verificação completa.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-188">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="aa5f3-189">**Coletar pacote de investigação** -coleta informações sobre o computador.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-189">**Collect investigation package** - Gathers information about the machine.</span></span> <span data-ttu-id="aa5f3-190">Quando a investigação estiver concluída, você pode baixá-la.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-190">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="aa5f3-191">**Iniciar sessão de resposta ao vivo** – carrega um shell remoto no computador para [investigações de segurança aprofundadas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span><span class="sxs-lookup"><span data-stu-id="aa5f3-191">**Initiate Live Response session** - Loads a remote shell on the machine for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="aa5f3-192">**Iniciar investigação automatizada** - [investiga e corrige ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)automaticamente.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-192">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="aa5f3-193">Embora seja possível disparar manualmente as investigações automatizadas para executar a partir desta página, [determinadas políticas de alerta](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) disparam investigações automáticas por conta própria.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-193">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="aa5f3-194">**Central de ações** -exiba o status das ações enviadas.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-194">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="aa5f3-195">Disponível somente se outra ação já tiver sido selecionada.</span><span class="sxs-lookup"><span data-stu-id="aa5f3-195">Only available if another action has already been selected.</span></span>

## <a name="related-topics"></a><span data-ttu-id="aa5f3-196">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="aa5f3-196">Related topics</span></span>

* [<span data-ttu-id="aa5f3-197">Visão geral da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="aa5f3-197">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="aa5f3-198">Habilitar a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="aa5f3-198">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
* [<span data-ttu-id="aa5f3-199">Investigar entidades em máquinas usando resposta ao vivo</span><span class="sxs-lookup"><span data-stu-id="aa5f3-199">Investigate entities on machines using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="aa5f3-200">Investigação e resposta automatizadas (AIR) no Office 365</span><span class="sxs-lookup"><span data-stu-id="aa5f3-200">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
