---
title: Visão geral do portal do Microsoft Defender para Ponto de Extremidade
description: O Centro de Segurança do Microsoft Defender pode monitorar sua rede corporativa e ajudar a responder a possíveis ameaças persistentes (APT) ou violações de dados.
keywords: Centro de Segurança do Microsoft Defender, portal, inteligência contra ameaças de segurança cibernética, painel, fila de alertas, lista de dispositivos, configurações, gerenciamento de dispositivos, ataques avançados
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aa7f2df1f0164f24c7f4698e8aa0b699f4884c09
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186216"
---
# <a name="microsoft-defender-security-center-portal-overview"></a><span data-ttu-id="30e2d-104">Visão geral do portal do Centro de Segurança do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="30e2d-104">Microsoft Defender Security Center portal overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="30e2d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="30e2d-105">**Applies to:**</span></span>
- [<span data-ttu-id="30e2d-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="30e2d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="30e2d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30e2d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="30e2d-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="30e2d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="30e2d-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="30e2d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink) 

<span data-ttu-id="30e2d-110">As equipes de segurança corporativas podem usar o Centro de Segurança do Microsoft Defender para monitorar e ajudar a responder a alertas de possíveis atividades avançadas de ameaças persistentes ou violações de dados.</span><span class="sxs-lookup"><span data-stu-id="30e2d-110">Enterprise security teams can use Microsoft Defender Security Center to monitor and assist in responding to alerts of potential advanced persistent threat activity or data breaches.</span></span>

<span data-ttu-id="30e2d-111">Você pode usar o [Centro de Segurança do Microsoft Defender](https://securitycenter.windows.com/) para:</span><span class="sxs-lookup"><span data-stu-id="30e2d-111">You can use [Microsoft Defender Security Center](https://securitycenter.windows.com/) to:</span></span>

- <span data-ttu-id="30e2d-112">Exibir, classificar e alertas de triagem de seus pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="30e2d-112">View, sort, and triage alerts from your endpoints</span></span>
- <span data-ttu-id="30e2d-113">Pesquisar mais informações sobre indicadores observados, como arquivos e endereços IP</span><span class="sxs-lookup"><span data-stu-id="30e2d-113">Search for more information on observed indicators such as files and IP Addresses</span></span>
- <span data-ttu-id="30e2d-114">Alterar as configurações do Microsoft Defender para Ponto de Extremidade, incluindo fuso horário e informações de licenciamento de revisão</span><span class="sxs-lookup"><span data-stu-id="30e2d-114">Change Microsoft Defender for Endpoint settings, including time zone and review licensing information</span></span>

## <a name="microsoft-defender-security-center"></a><span data-ttu-id="30e2d-115">Centro de Segurança do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="30e2d-115">Microsoft Defender Security Center</span></span>

<span data-ttu-id="30e2d-116">Ao abrir o portal, você verá:</span><span class="sxs-lookup"><span data-stu-id="30e2d-116">When you open the portal, you'll see:</span></span>

- <span data-ttu-id="30e2d-117">(1) Painel de navegação (selecione as linhas horizontais na parte superior do painel de navegação para mostrar ou ocultar)</span><span class="sxs-lookup"><span data-stu-id="30e2d-117">(1) Navigation pane (select the horizontal lines at the top of the navigation pane to show or hide it)</span></span>
- <span data-ttu-id="30e2d-118">(2) Pesquisa, Centro da comunidade, Localização, Ajuda e suporte, Feedback</span><span class="sxs-lookup"><span data-stu-id="30e2d-118">(2) Search, Community center, Localization, Help and support, Feedback</span></span>

 ![Portal do Microsoft Defender para Ponto de Extremidade](images/mdatp-portal-overview.png)

> [!NOTE]
> <span data-ttu-id="30e2d-120">As detecções relacionadas a malware só serão exibidas se seus dispositivos estão usando o Microsoft Defender Antivírus como o produto antimalware de proteção em tempo real padrão.</span><span class="sxs-lookup"><span data-stu-id="30e2d-120">Malware related detections will only appear if your devices are using Microsoft Defender Antivirus as the default real-time protection antimalware product.</span></span>

<span data-ttu-id="30e2d-121">Você pode navegar pelo portal usando as opções de menu disponíveis em todas as seções.</span><span class="sxs-lookup"><span data-stu-id="30e2d-121">You can navigate through the portal using the menu options available in all sections.</span></span> <span data-ttu-id="30e2d-122">Consulte a tabela a seguir para ver uma descrição de cada seção.</span><span class="sxs-lookup"><span data-stu-id="30e2d-122">Refer to the following table for a description of each section.</span></span>

<span data-ttu-id="30e2d-123">Área</span><span class="sxs-lookup"><span data-stu-id="30e2d-123">Area</span></span> | <span data-ttu-id="30e2d-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="30e2d-124">Description</span></span>
:---|:---
<span data-ttu-id="30e2d-125">**(1) Painel de navegação**</span><span class="sxs-lookup"><span data-stu-id="30e2d-125">**(1) Navigation pane**</span></span> | <span data-ttu-id="30e2d-126">Use o painel de navegação para se mover entre Painéis, **Incidentes,** Lista de Dispositivos, Fila de  **Alertas, Investigações** **Automatizadas,** Busca **Avançada,** **Relatórios** **&, APIs** de Parceiros, Gerenciamento de **Vulnerabilidades**& Ameaças, Avaliação e **tutoriais,** **Saúde** do **serviço,** Gerenciamento de configuração e **Configurações.**</span><span class="sxs-lookup"><span data-stu-id="30e2d-126">Use the navigation pane to move between **Dashboards**, **Incidents**, **Devices list**, **Alerts queue**, **Automated investigations**, **Advanced hunting**, **Reports**, **Partners & APIs**, **Threat & Vulnerability Management**, **Evaluation and tutorials**, **Service health**, **Configuration management**, and **Settings**.</span></span> <span data-ttu-id="30e2d-127">Selecione as linhas horizontais na parte superior do painel de navegação para mostrar ou ocultar.</span><span class="sxs-lookup"><span data-stu-id="30e2d-127">Select the horizontal lines at the top of the navigation pane to show or hide it.</span></span>
<span data-ttu-id="30e2d-128">**Painéis**</span><span class="sxs-lookup"><span data-stu-id="30e2d-128">**Dashboards**</span></span> | <span data-ttu-id="30e2d-129">Acesse as investigações automatizadas ativas, alertas ativos, estatísticas de investigações automatizadas, dispositivos em risco, usuários em risco, dispositivos com problemas de sensor, saúde do serviço, fontes de detecção e painéis de relatórios de dispositivos diários.</span><span class="sxs-lookup"><span data-stu-id="30e2d-129">Access the active automated investigations, active alerts, automated investigations statistics, devices at risk, users at risk, devices with sensor issues, service health, detection sources, and daily devices reporting dashboards.</span></span>
<span data-ttu-id="30e2d-130">**Incidentes**</span><span class="sxs-lookup"><span data-stu-id="30e2d-130">**Incidents**</span></span> | <span data-ttu-id="30e2d-131">Exibir alertas que foram agregados como incidentes.</span><span class="sxs-lookup"><span data-stu-id="30e2d-131">View alerts that have been aggregated as incidents.</span></span>
<span data-ttu-id="30e2d-132">**Lista de dispositivos**</span><span class="sxs-lookup"><span data-stu-id="30e2d-132">**Devices list**</span></span> | <span data-ttu-id="30e2d-133">Exibe a lista de dispositivos que estão internados no Defender for Endpoint, algumas informações sobre eles e seus níveis de exposição e risco.</span><span class="sxs-lookup"><span data-stu-id="30e2d-133">Displays the list of devices that are onboarded to Defender for Endpoint, some information about them, and their exposure and risk levels.</span></span>
<span data-ttu-id="30e2d-134">**Fila de alertas**</span><span class="sxs-lookup"><span data-stu-id="30e2d-134">**Alerts queue**</span></span> | <span data-ttu-id="30e2d-135">Exibir alertas gerados de dispositivos em suas organizações.</span><span class="sxs-lookup"><span data-stu-id="30e2d-135">View alerts generated from devices in your organizations.</span></span>
<span data-ttu-id="30e2d-136">**Investigações automatizadas**</span><span class="sxs-lookup"><span data-stu-id="30e2d-136">**Automated investigations**</span></span> | <span data-ttu-id="30e2d-137">Exibe investigações automatizadas que foram conduzidas na rede, disparando alerta, o status de cada investigação e outros detalhes, como quando a investigação começou e a duração da investigação.</span><span class="sxs-lookup"><span data-stu-id="30e2d-137">Displays automated investigations that have been conducted in the network, triggering alert, the status of each investigation and other details such as when the investigation started and the duration of the investigation.</span></span>
<span data-ttu-id="30e2d-138">**Busca avançada**</span><span class="sxs-lookup"><span data-stu-id="30e2d-138">**Advanced hunting**</span></span> | <span data-ttu-id="30e2d-139">A busca avançada permite que você pesquise e investigue proativamente em toda a sua organização usando uma ferramenta de pesquisa e consulta avançada.</span><span class="sxs-lookup"><span data-stu-id="30e2d-139">Advanced hunting allows you to proactively hunt and investigate across your organization using a powerful search and query tool.</span></span>
<span data-ttu-id="30e2d-140">**Relatórios**</span><span class="sxs-lookup"><span data-stu-id="30e2d-140">**Reports**</span></span> | <span data-ttu-id="30e2d-141">Exibir gráficos detalhando a proteção contra ameaças, a conformidade e a saúde do dispositivo, a proteção da Web e a vulnerabilidade.</span><span class="sxs-lookup"><span data-stu-id="30e2d-141">View graphs detailing threat protection, device health and compliance, web protection, and vulnerability.</span></span>
<span data-ttu-id="30e2d-142">**Parceiros & APIs**</span><span class="sxs-lookup"><span data-stu-id="30e2d-142">**Partners & APIs**</span></span> | <span data-ttu-id="30e2d-143">Exibir conexões de parceiros com suporte, que aprimoram os recursos de detecção, investigação e inteligência contra ameaças da plataforma.</span><span class="sxs-lookup"><span data-stu-id="30e2d-143">View supported partner connections, which enhance the detection, investigation, and threat intelligence capabilities of the platform.</span></span> <span data-ttu-id="30e2d-144">Você também pode exibir aplicativos conectados, o explorador de API, a visão geral de uso da API e as configurações de exportação de dados.</span><span class="sxs-lookup"><span data-stu-id="30e2d-144">You can also view connected applications, the API explorer, API usage overview, and data export settings.</span></span>
<span data-ttu-id="30e2d-145">**Gerenciamento de & de vulnerabilidades**</span><span class="sxs-lookup"><span data-stu-id="30e2d-145">**Threat & Vulnerability management**</span></span> | <span data-ttu-id="30e2d-146">Exibir a Pontuação Segura da Microsoft para Dispositivos, a pontuação de exposição, os dispositivos expostos, o software vulnerável e tomar medidas sobre as principais recomendações de segurança.</span><span class="sxs-lookup"><span data-stu-id="30e2d-146">View your Microsoft Secure Score for Devices, exposure score, exposed devices, vulnerable software, and take action on top security recommendations.</span></span>
<span data-ttu-id="30e2d-147">**Avaliação e tutoriais**</span><span class="sxs-lookup"><span data-stu-id="30e2d-147">**Evaluation and tutorials**</span></span> | <span data-ttu-id="30e2d-148">Gerenciar dispositivos de teste, simulações de ataque e relatórios.</span><span class="sxs-lookup"><span data-stu-id="30e2d-148">Manage test devices, attack simulations, and reports.</span></span> <span data-ttu-id="30e2d-149">Aprenda e experimente os recursos do Defender para Ponto de Extremidade por meio de um passo a passo guiado em um ambiente de avaliação.</span><span class="sxs-lookup"><span data-stu-id="30e2d-149">Learn and experience the Defender for Endpoint capabilities through a guided walk-through in a trial environment.</span></span>
<span data-ttu-id="30e2d-150">**Integridade do Serviço**</span><span class="sxs-lookup"><span data-stu-id="30e2d-150">**Service health**</span></span> | <span data-ttu-id="30e2d-151">Fornece informações sobre o status atual do serviço Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="30e2d-151">Provides information on the current status of the Defender for Endpoint service.</span></span> <span data-ttu-id="30e2d-152">Você poderá verificar se a saúde do serviço está saudável ou se há problemas atuais.</span><span class="sxs-lookup"><span data-stu-id="30e2d-152">You'll be able to verify that the service health is healthy or if there are current issues.</span></span>
<span data-ttu-id="30e2d-153">**Gerenciamento de configuração**</span><span class="sxs-lookup"><span data-stu-id="30e2d-153">**Configuration management**</span></span> | <span data-ttu-id="30e2d-154">Exibe dispositivos a bordo, linha de base de segurança de suas organizações, análise preditiva, cobertura de proteção da Web e permite que você execute o gerenciamento de superfície de ataque em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="30e2d-154">Displays on-boarded devices, your organizations' security baseline, predictive analysis, web protection coverage, and allows you to perform attack surface management on your devices.</span></span>
<span data-ttu-id="30e2d-155">**Settings**</span><span class="sxs-lookup"><span data-stu-id="30e2d-155">**Settings**</span></span> | <span data-ttu-id="30e2d-156">Mostra as configurações selecionadas durante a integração e permite atualizar suas preferências do setor e o período da política de retenção.</span><span class="sxs-lookup"><span data-stu-id="30e2d-156">Shows the settings you selected during onboarding and lets you update your industry preferences and retention policy period.</span></span> <span data-ttu-id="30e2d-157">Você também pode definir outras configurações, como permissões, APIs, regras, gerenciamento de dispositivos, gerenciamento de serviço de TI e avaliações de rede.</span><span class="sxs-lookup"><span data-stu-id="30e2d-157">You can also set other configuration settings such as permissions, APIs, rules, device management, IT service management, and network assessments.</span></span>
<span data-ttu-id="30e2d-158">**(2) Pesquisa, Centro da comunidade, Localização, Ajuda e suporte, Feedback**</span><span class="sxs-lookup"><span data-stu-id="30e2d-158">**(2) Search, Community center, Localization,  Help and support, Feedback**</span></span> | <span data-ttu-id="30e2d-159">**Pesquisa** - pesquisa por dispositivo, arquivo, usuário, URL, IP, vulnerabilidade, software e recomendação.</span><span class="sxs-lookup"><span data-stu-id="30e2d-159">**Search** - search by device, file, user, URL, IP, vulnerability, software, and recommendation.</span></span> </br></br> <span data-ttu-id="30e2d-160">**Centro de comunidade** - Acesse o Centro da Comunidade para aprender, colaborar e compartilhar experiências sobre o produto.</span><span class="sxs-lookup"><span data-stu-id="30e2d-160">**Community center** - Access the Community center to learn, collaborate, and share experiences about the product.</span></span> </br></br>  <span data-ttu-id="30e2d-161">**Localização** - Definir fusos horário.</span><span class="sxs-lookup"><span data-stu-id="30e2d-161">**Localization** - Set time zones.</span></span> </br></br>  <span data-ttu-id="30e2d-162">**Ajuda e** suporte - Acesse o guia Defender para Ponto de Extremidade, suporte da Microsoft e Microsoft Premier, informações de licença, simulações & tutoriais, laboratório de avaliação do Defender para Ponto de Extremidade, consulte um especialista em ameaças.</span><span class="sxs-lookup"><span data-stu-id="30e2d-162">**Help and support** - Access the Defender for Endpoint guide, Microsoft and Microsoft Premier support, license information, simulations & tutorials, Defender for Endpoint evaluation lab, consult a threat expert.</span></span></br></br> <span data-ttu-id="30e2d-163">**Comentários** - Forneça comentários sobre o que você gosta ou o que podemos fazer melhor.</span><span class="sxs-lookup"><span data-stu-id="30e2d-163">**Feedback** - Provide comments about what you like or what we can do better.</span></span>

> [!NOTE]
> <span data-ttu-id="30e2d-164">Para dispositivos com problemas de dimensionamento de DPI de alta resolução, consulte Problemas de dimensionamento do Windows para dispositivos de [alta DPI](https://support.microsoft.com/help/3025083/windows-scaling-issues-for-high-dpi-devices) para possíveis soluções.</span><span class="sxs-lookup"><span data-stu-id="30e2d-164">For devices with high resolution DPI scaling issues, please see [Windows scaling issues for high-DPI devices](https://support.microsoft.com/help/3025083/windows-scaling-issues-for-high-dpi-devices) for possible solutions.</span></span>

## <a name="microsoft-defender-for-endpoint-icons"></a><span data-ttu-id="30e2d-165">Ícones do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="30e2d-165">Microsoft Defender for Endpoint icons</span></span>

<span data-ttu-id="30e2d-166">A tabela a seguir fornece informações sobre os ícones usados em todo o portal:</span><span class="sxs-lookup"><span data-stu-id="30e2d-166">The following table provides information on the icons used all throughout the portal:</span></span>

<span data-ttu-id="30e2d-167">Ícone</span><span class="sxs-lookup"><span data-stu-id="30e2d-167">Icon</span></span> | <span data-ttu-id="30e2d-168">Descrição</span><span class="sxs-lookup"><span data-stu-id="30e2d-168">Description</span></span>
:---|:---
![Ícone de logotipo atp](images/atp-logo-icon.png)| <span data-ttu-id="30e2d-170">Logotipo do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="30e2d-170">Microsoft Defender for Endpoint logo</span></span>
![Ícone de alerta](images/alert-icon.png)| <span data-ttu-id="30e2d-172">Alerta – Indicação de uma atividade correlacionada com ataques avançados.</span><span class="sxs-lookup"><span data-stu-id="30e2d-172">Alert – Indication of an activity correlated with advanced attacks.</span></span>
![Ícone de detecção](images/detection-icon.png)| <span data-ttu-id="30e2d-174">Detecção – Indicação de uma detecção de ameaças de malware.</span><span class="sxs-lookup"><span data-stu-id="30e2d-174">Detection – Indication of a malware threat detection.</span></span>
![Ícone de ameaça ativa](images/active-threat-icon.png)| <span data-ttu-id="30e2d-176">Ameaça ativa – Ameaças sendo executadas ativamente no momento da detecção.</span><span class="sxs-lookup"><span data-stu-id="30e2d-176">Active threat – Threats actively executing at the time of detection.</span></span>
![Ícone remediado1](images/remediated-icon.png)| <span data-ttu-id="30e2d-178">Correção – Ameaça removida do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="30e2d-178">Remediated – Threat removed from the device.</span></span>
![Ícone não remediado](images/not-remediated-icon.png)| <span data-ttu-id="30e2d-180">Não remediada – Ameaça não removida do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="30e2d-180">Not remediated – Threat not removed from the device.</span></span>
![Ícone thunderbolt](images/atp-thunderbolt-icon.png)| <span data-ttu-id="30e2d-182">Indica eventos que dispararam um alerta na árvore **do processo de alerta.**</span><span class="sxs-lookup"><span data-stu-id="30e2d-182">Indicates events that triggered an alert in the **Alert process tree**.</span></span>
![Ícone do dispositivo](images/atp-machine-icon.png)| <span data-ttu-id="30e2d-184">Ícone do dispositivo</span><span class="sxs-lookup"><span data-stu-id="30e2d-184">Device icon</span></span>
![Ícone de eventos do Microsoft Defender AV](images/atp-windows-defender-av-events-icon.png)| <span data-ttu-id="30e2d-186">Eventos do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="30e2d-186">Microsoft Defender Antivirus events</span></span>
![Ícone de eventos do Application Guard](images/atp-Application-Guard-events-icon.png)| <span data-ttu-id="30e2d-188">Windows Defender eventos do Application Guard</span><span class="sxs-lookup"><span data-stu-id="30e2d-188">Windows Defender Application Guard events</span></span>
![Ícone de eventos do Device Guard](images/atp-Device-Guard-events-icon.png)| <span data-ttu-id="30e2d-190">Windows Defender eventos do Device Guard</span><span class="sxs-lookup"><span data-stu-id="30e2d-190">Windows Defender Device Guard events</span></span>
![Ícone de eventos do Exploit Guard](images/atp-Exploit-Guard-events-icon.png)| <span data-ttu-id="30e2d-192">Windows Defender eventos do Exploit Guard</span><span class="sxs-lookup"><span data-stu-id="30e2d-192">Windows Defender Exploit Guard events</span></span>
![Ícone de eventos SmartScreen](images/atp-Smart-Screen-events-icon.png)| <span data-ttu-id="30e2d-194">Windows Defender eventos SmartScreen</span><span class="sxs-lookup"><span data-stu-id="30e2d-194">Windows Defender SmartScreen events</span></span>
![Ícone de eventos de firewall](images/atp-Firewall-events-icon.png)| <span data-ttu-id="30e2d-196">Eventos do Firewall do Windows</span><span class="sxs-lookup"><span data-stu-id="30e2d-196">Windows Firewall events</span></span>
![Ícone de ação de resposta](images/atp-respond-action-icon.png)| <span data-ttu-id="30e2d-198">Ação de resposta</span><span class="sxs-lookup"><span data-stu-id="30e2d-198">Response action</span></span>
![Ícone de eventos de processo](images/atp-process-event-icon.png)| <span data-ttu-id="30e2d-200">Processar eventos</span><span class="sxs-lookup"><span data-stu-id="30e2d-200">Process events</span></span>
![Ícone de eventos de comunicação de rede](images/atp-network-communications-icon.png)| <span data-ttu-id="30e2d-202">Eventos de rede</span><span class="sxs-lookup"><span data-stu-id="30e2d-202">Network events</span></span>
![Ícone de eventos observados por arquivo](images/atp-file-observed-icon.png)| <span data-ttu-id="30e2d-204">Eventos de arquivo</span><span class="sxs-lookup"><span data-stu-id="30e2d-204">File  events</span></span>
![Ícone de eventos do Registro](images/atp-registry-event-icon.png)| <span data-ttu-id="30e2d-206">Eventos do Registro</span><span class="sxs-lookup"><span data-stu-id="30e2d-206">Registry events</span></span>
![Ícone de eventos DLL de carregamento de módulo](images/atp-module-load-icon.png)| <span data-ttu-id="30e2d-208">Carregar eventos DLL</span><span class="sxs-lookup"><span data-stu-id="30e2d-208">Load DLL events</span></span>
![Ícone de outros eventos](images/atp-Other-events-icon.png)| <span data-ttu-id="30e2d-210">Outros eventos</span><span class="sxs-lookup"><span data-stu-id="30e2d-210">Other events</span></span>
![Ícone de modificação de token de acesso](images/atp-access-token-modification-icon.png)| <span data-ttu-id="30e2d-212">Modificação de token de acesso</span><span class="sxs-lookup"><span data-stu-id="30e2d-212">Access token modification</span></span>
![Ícone de criação de arquivo](images/atp-file-creation-icon.png)| <span data-ttu-id="30e2d-214">Criação de arquivos</span><span class="sxs-lookup"><span data-stu-id="30e2d-214">File creation</span></span>
![Ícone do signator](images/atp-signer-icon.png)| <span data-ttu-id="30e2d-216">Signer</span><span class="sxs-lookup"><span data-stu-id="30e2d-216">Signer</span></span>
![Ícone do caminho do arquivo](images/atp-File-path-icon.png)| <span data-ttu-id="30e2d-218">Caminho do arquivo</span><span class="sxs-lookup"><span data-stu-id="30e2d-218">File path</span></span>
![Ícone de linha de comando](images/atp-command-line-icon.png)| <span data-ttu-id="30e2d-220">Linha de comando</span><span class="sxs-lookup"><span data-stu-id="30e2d-220">Command line</span></span>
![Ícone de arquivo não assinado](images/atp-unsigned-file-icon.png)| <span data-ttu-id="30e2d-222">Arquivo não assinado</span><span class="sxs-lookup"><span data-stu-id="30e2d-222">Unsigned file</span></span>
![Ícone de árvore de processo](images/atp-process-tree.png)| <span data-ttu-id="30e2d-224">Árvore de processos</span><span class="sxs-lookup"><span data-stu-id="30e2d-224">Process tree</span></span>
![Ícone de alocação de memória](images/atp-memory-allocation-icon.png)| <span data-ttu-id="30e2d-226">Alocação de memória</span><span class="sxs-lookup"><span data-stu-id="30e2d-226">Memory allocation</span></span>
![Ícone de injeção de processo](images/atp-process-injection.png)| <span data-ttu-id="30e2d-228">Injeção de processo</span><span class="sxs-lookup"><span data-stu-id="30e2d-228">Process injection</span></span>
![Ícone de executar comando do Powershell](images/atp-powershell-command-run-icon.png)| <span data-ttu-id="30e2d-230">Executar o comando do Powershell</span><span class="sxs-lookup"><span data-stu-id="30e2d-230">Powershell command run</span></span>
![Ícone do Centro de Comunidade](images/atp-community-center.png) | <span data-ttu-id="30e2d-232">Centro de comunidade</span><span class="sxs-lookup"><span data-stu-id="30e2d-232">Community center</span></span>
![Ícone de notificações](images/atp-notifications.png) | <span data-ttu-id="30e2d-234">Notificações</span><span class="sxs-lookup"><span data-stu-id="30e2d-234">Notifications</span></span>
![Nenhuma ameaça encontrada](images/no-threats-found.png) | <span data-ttu-id="30e2d-236">Investigação automatizada - nenhuma ameaça encontrada</span><span class="sxs-lookup"><span data-stu-id="30e2d-236">Automated investigation - no threats found</span></span>
![Ícone com falha](images/failed.png) | <span data-ttu-id="30e2d-238">Investigação automatizada - falha</span><span class="sxs-lookup"><span data-stu-id="30e2d-238">Automated investigation - failed</span></span>
![Ícone parcialmente remediado](images/partially-investigated.png) | <span data-ttu-id="30e2d-240">Investigação automatizada - parcialmente investigada</span><span class="sxs-lookup"><span data-stu-id="30e2d-240">Automated investigation - partially investigated</span></span>
![Encerrado pelo sistema](images/terminated-by-system.png) | <span data-ttu-id="30e2d-242">Investigação automatizada - encerrada pelo sistema</span><span class="sxs-lookup"><span data-stu-id="30e2d-242">Automated investigation - terminated by system</span></span>
![Ícone pendente](images/pending.png) | <span data-ttu-id="30e2d-244">Investigação automatizada - pendente</span><span class="sxs-lookup"><span data-stu-id="30e2d-244">Automated investigation - pending</span></span>
![Ícone de execução](images/running.png) | <span data-ttu-id="30e2d-246">Investigação automatizada - em execução</span><span class="sxs-lookup"><span data-stu-id="30e2d-246">Automated investigation - running</span></span>
![Ícone remediado2](images/remediated.png) | <span data-ttu-id="30e2d-248">Investigação automatizada - correção</span><span class="sxs-lookup"><span data-stu-id="30e2d-248">Automated investigation - remediated</span></span>
![Ícone parcialmente investigado](images/partially_remediated.png) | <span data-ttu-id="30e2d-250">Investigação automatizada - parcialmente remediada</span><span class="sxs-lookup"><span data-stu-id="30e2d-250">Automated investigation - partially remediated</span></span>
![Ícone de insights de ameaça](images/tvm_bug_icon.png) | <span data-ttu-id="30e2d-252">Gerenciamento & de Vulnerabilidades - insights sobre ameaças</span><span class="sxs-lookup"><span data-stu-id="30e2d-252">Threat & Vulnerability Management - threat insights</span></span>
![Ícone de alerta ativo possível](images/tvm_alert_icon.png) | <span data-ttu-id="30e2d-254">Gerenciamento & de Vulnerabilidades - alerta ativo possível</span><span class="sxs-lookup"><span data-stu-id="30e2d-254">Threat & Vulnerability Management - possible active alert</span></span>
![Ícone de insights de recomendação](images/tvm_insight_icon.png) | <span data-ttu-id="30e2d-256">Gerenciamento & de Vulnerabilidades - insights de recomendação</span><span class="sxs-lookup"><span data-stu-id="30e2d-256">Threat & Vulnerability Management - recommendation insights</span></span>

## <a name="related-topics"></a><span data-ttu-id="30e2d-257">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="30e2d-257">Related topics</span></span>

- [<span data-ttu-id="30e2d-258">Visão geral do Centro de Segurança do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="30e2d-258">Overview of Microsoft Defender Security Center</span></span>](use.md)
- [<span data-ttu-id="30e2d-259">Exibir o painel de operações de segurança</span><span class="sxs-lookup"><span data-stu-id="30e2d-259">View the Security operations dashboard</span></span>](security-operations-dashboard.md)
- [<span data-ttu-id="30e2d-260">Exibir o painel gerenciamento de & de vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="30e2d-260">View the Threat & Vulnerability Management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="30e2d-261">Exibir o painel de análise de ameaças e tomar ações de mitigação recomendadas</span><span class="sxs-lookup"><span data-stu-id="30e2d-261">View the Threat analytics dashboard and take recommended mitigation actions</span></span>](threat-analytics.md)