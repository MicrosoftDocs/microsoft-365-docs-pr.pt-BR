---
title: Integração de versões anteriores Windows no Microsoft Defender para Ponto de Extremidade
description: A integração suportava versões anteriores Windows dispositivos de modo que eles possam enviar dados do sensor para o sensor do Microsoft Defender para Ponto de Extremidade
keywords: onboard, windows, 7, 81, oms, sp1, enterprise, pro, down level
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d0cb4a3d01c1380f4fd06999c8f81a4054e2fd00
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844425"
---
# <a name="onboard-previous-versions-of-windows"></a><span data-ttu-id="f8a53-104">Versões anteriores integradas do Windows</span><span class="sxs-lookup"><span data-stu-id="f8a53-104">Onboard previous versions of Windows</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f8a53-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f8a53-105">**Applies to:**</span></span>
- [<span data-ttu-id="f8a53-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f8a53-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f8a53-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8a53-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="f8a53-108">**Plataformas**</span><span class="sxs-lookup"><span data-stu-id="f8a53-108">**Platforms**</span></span>
- <span data-ttu-id="f8a53-109">Windows 7 sp1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f8a53-109">Windows 7 SP1 Enterprise</span></span>
- <span data-ttu-id="f8a53-110">Windows 7 sp1 Pro</span><span class="sxs-lookup"><span data-stu-id="f8a53-110">Windows 7 SP1 Pro</span></span>
- <span data-ttu-id="f8a53-111">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="f8a53-111">Windows 8.1 Pro</span></span>
- <span data-ttu-id="f8a53-112">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="f8a53-112">Windows 8.1 Enterprise</span></span>


><span data-ttu-id="f8a53-113">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="f8a53-113">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="f8a53-114">[Inscreva-se para uma avaliação gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="f8a53-114">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).</span></span>

<span data-ttu-id="f8a53-115">O Defender for Endpoint estende o suporte para incluir sistemas operacionais de nível inferior, fornecendo recursos avançados de detecção e investigação de ataques em versões Windows suportadas.</span><span class="sxs-lookup"><span data-stu-id="f8a53-115">Defender for Endpoint extends support to include down-level operating systems, providing advanced attack detection and investigation capabilities on supported Windows versions.</span></span>

<span data-ttu-id="f8a53-116">Para fazer a integração de pontos de extremidade Windows cliente para o Defender para Ponto de Extremidade, você precisará:</span><span class="sxs-lookup"><span data-stu-id="f8a53-116">To onboard down-level Windows client endpoints to Defender for Endpoint, you'll need to:</span></span>
- <span data-ttu-id="f8a53-117">Configure e atualize System Center Endpoint Protection clientes.</span><span class="sxs-lookup"><span data-stu-id="f8a53-117">Configure and update System Center Endpoint Protection clients.</span></span>
- <span data-ttu-id="f8a53-118">Instale e configure Microsoft Monitoring Agent (MMA) para relatar dados do sensor ao Defender para Ponto de Extremidade, conforme instruído a seguir.</span><span class="sxs-lookup"><span data-stu-id="f8a53-118">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Defender for Endpoint as instructed below.</span></span>

> [!TIP]
> <span data-ttu-id="f8a53-119">Após a integração do dispositivo, você pode optar por executar um teste de detecção para verificar se ele está corretamente conectado ao serviço.</span><span class="sxs-lookup"><span data-stu-id="f8a53-119">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="f8a53-120">Para obter mais informações, [consulte Execute a detection test on a newly onboarded Defender for Endpoint endpoint endpoint endpoint](run-detection-test.md).</span><span class="sxs-lookup"><span data-stu-id="f8a53-120">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="f8a53-121">Configurar e atualizar System Center Endpoint Protection clientes</span><span class="sxs-lookup"><span data-stu-id="f8a53-121">Configure and update System Center Endpoint Protection clients</span></span>
> [!IMPORTANT]
> <span data-ttu-id="f8a53-122">Esta etapa só será necessária se sua organização usar System Center Endpoint Protection (SCEP).</span><span class="sxs-lookup"><span data-stu-id="f8a53-122">This step is required only if your organization uses System Center Endpoint Protection (SCEP).</span></span>

<span data-ttu-id="f8a53-123">O Defender for Endpoint se integra ao System Center Endpoint Protection para fornecer visibilidade a detecções de malware e parar a propagação de um ataque em sua organização, proibindo arquivos potencialmente mal-intencionados ou malware suspeito.</span><span class="sxs-lookup"><span data-stu-id="f8a53-123">Defender for Endpoint integrates with System Center Endpoint Protection to provide visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 

<span data-ttu-id="f8a53-124">As etapas a seguir são necessárias para habilitar essa integração:</span><span class="sxs-lookup"><span data-stu-id="f8a53-124">The following steps are required to enable this integration:</span></span> 
- <span data-ttu-id="f8a53-125">Instalar a atualização da plataforma anti-malware de janeiro de [2017 para Endpoint Protection clientes](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span><span class="sxs-lookup"><span data-stu-id="f8a53-125">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span></span> 
- <span data-ttu-id="f8a53-126">Configurar a associação do Serviço de Proteção de Nuvem do cliente SCEP à **configuração** Avançada</span><span class="sxs-lookup"><span data-stu-id="f8a53-126">Configure the SCEP client Cloud Protection Service membership to the **Advanced** setting</span></span>
- <span data-ttu-id="f8a53-127">Configure sua rede para permitir conexões com a Microsoft Defender Antivírus nuvem.</span><span class="sxs-lookup"><span data-stu-id="f8a53-127">Configure your network to allow connections to the Microsoft Defender Antivirus cloud.</span></span> <span data-ttu-id="f8a53-128">Para obter mais informações, consulte [Allow connections to the Microsoft Defender Antivírus cloud](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span><span class="sxs-lookup"><span data-stu-id="f8a53-128">For more information, see [Allow connections to the Microsoft Defender Antivirus cloud](/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span></span>

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="f8a53-129">Instalar e configurar o Microsoft Monitoring Agent (MMA) para relatar dados do sensor ao Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f8a53-129">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="f8a53-130">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="f8a53-130">Before you begin</span></span>
<span data-ttu-id="f8a53-131">Revise os seguintes detalhes para verificar os requisitos mínimos do sistema:</span><span class="sxs-lookup"><span data-stu-id="f8a53-131">Review the following details to verify minimum system requirements:</span></span>
- <span data-ttu-id="f8a53-132">Instalar a atualização mensal de fevereiro de [2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="f8a53-132">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="f8a53-133">Aplicável apenas para Windows 7 sp1 Enterprise e Windows 7 sp1 Pro.</span><span class="sxs-lookup"><span data-stu-id="f8a53-133">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span> 

- <span data-ttu-id="f8a53-134">Instalar a [telemetria de](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) diagnóstico e a experiência do cliente</span><span class="sxs-lookup"><span data-stu-id="f8a53-134">Install the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span></span>

- <span data-ttu-id="f8a53-135">Instalar o [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (ou posterior) ou [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="f8a53-135">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="f8a53-136">Aplicável apenas para Windows 7 sp1 Enterprise e Windows 7 sp1 Pro.</span><span class="sxs-lookup"><span data-stu-id="f8a53-136">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span>
    > <span data-ttu-id="f8a53-137">Não instale o .NET Framework 4.0.x, pois isso negará a instalação acima.</span><span class="sxs-lookup"><span data-stu-id="f8a53-137">Don't install .NET Framework 4.0.x, since it will negate the above installation.</span></span>

- <span data-ttu-id="f8a53-138">Atender aos requisitos mínimos do sistema do agente do Azure Log Analytics.</span><span class="sxs-lookup"><span data-stu-id="f8a53-138">Meet the Azure Log Analytics agent minimum system requirements.</span></span> <span data-ttu-id="f8a53-139">Para obter mais informações, consulte [Coletar dados de computadores em seu ambiente com o Log Analytics.](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="f8a53-139">For more information, see [Collect data from computers in your environment with Log Analytics](/azure/log-analytics/log-analytics-concept-hybrid#prerequisites).</span></span>



1. <span data-ttu-id="f8a53-140">Baixe o arquivo de instalação do agente: Windows agente de [64 bits](https://go.microsoft.com/fwlink/?LinkId=828603) ou Windows agente [de 32 bits.](https://go.microsoft.com/fwlink/?LinkId=828604)</span><span class="sxs-lookup"><span data-stu-id="f8a53-140">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603) or [Windows 32-bit agent](https://go.microsoft.com/fwlink/?LinkId=828604).</span></span>

2. <span data-ttu-id="f8a53-141">Obtenha a ID do espaço de trabalho:</span><span class="sxs-lookup"><span data-stu-id="f8a53-141">Obtain the workspace ID:</span></span>
   - <span data-ttu-id="f8a53-142">No painel de navegação Defender para Ponto de Extremidade, selecione Configurações > **Gerenciamento de dispositivos > Integração**</span><span class="sxs-lookup"><span data-stu-id="f8a53-142">In the Defender for Endpoint navigation pane, select **Settings > Device management > Onboarding**</span></span>
   - <span data-ttu-id="f8a53-143">Selecione **Windows 7 SP1 e 8.1** como o sistema operacional</span><span class="sxs-lookup"><span data-stu-id="f8a53-143">Select **Windows 7 SP1 and 8.1** as the operating system</span></span>
   - <span data-ttu-id="f8a53-144">Copie a ID do espaço de trabalho e a chave do espaço de trabalho</span><span class="sxs-lookup"><span data-stu-id="f8a53-144">Copy the workspace ID and workspace key</span></span>

3. <span data-ttu-id="f8a53-145">Usando a ID do Espaço de Trabalho e a tecla Workspace, escolha qualquer um dos seguintes métodos de instalação para instalar o agente:</span><span class="sxs-lookup"><span data-stu-id="f8a53-145">Using the Workspace ID and Workspace key choose any of the following installation methods to install the agent:</span></span>
    - <span data-ttu-id="f8a53-146">[Instale manualmente o agente usando a instalação](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="f8a53-146">[Manually install the agent using setup](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
      <span data-ttu-id="f8a53-147">Na página **Opções de Instalação do** Agente, selecione Conexão o agente para **OMS (Análise de Log do Azure)**</span><span class="sxs-lookup"><span data-stu-id="f8a53-147">On the **Agent Setup Options** page, select **Connect the agent to Azure Log Analytics (OMS)**</span></span>
    - <span data-ttu-id="f8a53-148">[Instale o agente usando a linha de comando](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span><span class="sxs-lookup"><span data-stu-id="f8a53-148">[Install the agent using the command line](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="f8a53-149">[Configure o agente usando um script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span><span class="sxs-lookup"><span data-stu-id="f8a53-149">[Configure the agent using a script](/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

   > [!NOTE]
   > <span data-ttu-id="f8a53-150">Se você for um cliente do Governo dos EUA [,](gov.md)em "Nuvem do Azure" precisará escolher "Azure US Government" se estiver usando o assistente de instalação ou se estiver usando uma linha de comando ou um script , de definir o parâmetro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" como 1.</span><span class="sxs-lookup"><span data-stu-id="f8a53-150">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

4. <span data-ttu-id="f8a53-151">Se você estiver usando um proxy para se conectar à Internet, consulte a seção Configurar configurações de proxy.</span><span class="sxs-lookup"><span data-stu-id="f8a53-151">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="f8a53-152">Depois de concluído, você deverá ver pontos de extremidade integrados no portal dentro de uma hora.</span><span class="sxs-lookup"><span data-stu-id="f8a53-152">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="configure-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="f8a53-153">Definir as configurações de proxy e conectividade com a Internet</span><span class="sxs-lookup"><span data-stu-id="f8a53-153">Configure proxy and Internet connectivity settings</span></span>
 
- <span data-ttu-id="f8a53-154">Cada Windows ponto de extremidade deve ser capaz de se conectar à Internet usando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f8a53-154">Each Windows endpoint must be able to connect to the Internet using HTTPS.</span></span> <span data-ttu-id="f8a53-155">Essa conexão pode ser direta, usando um proxy ou por meio do [Gateway OMS.](/azure/log-analytics/log-analytics-oms-gateway)</span><span class="sxs-lookup"><span data-stu-id="f8a53-155">This connection can be direct, using a proxy, or through the [OMS Gateway](/azure/log-analytics/log-analytics-oms-gateway).</span></span>
- <span data-ttu-id="f8a53-156">Se um proxy ou firewall estiver bloqueando todo o tráfego por padrão e permitindo apenas domínios específicos por meio ou a verificação de HTTPS (inspeção SSL) estiver habilitada, certifique-se de que você habilita o acesso a [URLs](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)de serviço do Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="f8a53-156">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through or HTTPS scanning (SSL inspection) is enabled, make sure that you [enable access to Defender for Endpoint service URLs](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

## <a name="offboard-client-endpoints"></a><span data-ttu-id="f8a53-157">Pontos de extremidade do cliente de offboard</span><span class="sxs-lookup"><span data-stu-id="f8a53-157">Offboard client endpoints</span></span>
<span data-ttu-id="f8a53-158">Para offboard, você pode desinstalar o agente MMA do ponto de extremidade ou desconecta-lo do relatório para o seu espaço de trabalho do Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="f8a53-158">To offboard, you can uninstall the MMA agent from the endpoint or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="f8a53-159">Depois de fazer o offboard do agente, o ponto de extremidade não enviará mais dados do sensor para o Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="f8a53-159">After offboarding the agent, the endpoint will no longer send sensor data to Defender for Endpoint.</span></span> 

> <span data-ttu-id="f8a53-160">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="f8a53-160">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="f8a53-161">[Inscreva-se para uma avaliação gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).</span><span class="sxs-lookup"><span data-stu-id="f8a53-161">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).</span></span>
