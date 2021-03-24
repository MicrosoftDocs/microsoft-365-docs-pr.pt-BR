---
title: Integração de versões anteriores do Windows no Microsoft Defender ATP
description: Integração com versões anteriores de dispositivos Windows para que eles possam enviar dados do sensor para o sensor do Microsoft Defender ATP
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
ms.openlocfilehash: a70826ee6e245f6744d8fc64eaf06e8cd1bdb265
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052617"
---
# <a name="onboard-previous-versions-of-windows"></a><span data-ttu-id="60b9b-104">Integração de versões anteriores do Windows</span><span class="sxs-lookup"><span data-stu-id="60b9b-104">Onboard previous versions of Windows</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="60b9b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="60b9b-105">**Applies to:**</span></span>
- [<span data-ttu-id="60b9b-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="60b9b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="60b9b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60b9b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="60b9b-108">**Plataformas**</span><span class="sxs-lookup"><span data-stu-id="60b9b-108">**Platforms**</span></span>
- <span data-ttu-id="60b9b-109">Windows 7 SP1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="60b9b-109">Windows 7 SP1 Enterprise</span></span>
- <span data-ttu-id="60b9b-110">Windows 7 SP1 Pro</span><span class="sxs-lookup"><span data-stu-id="60b9b-110">Windows 7 SP1 Pro</span></span>
- <span data-ttu-id="60b9b-111">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="60b9b-111">Windows 8.1 Pro</span></span>
- <span data-ttu-id="60b9b-112">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="60b9b-112">Windows 8.1 Enterprise</span></span>


><span data-ttu-id="60b9b-113">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="60b9b-113">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="60b9b-114">[Inscreva-se para uma avaliação gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="60b9b-114">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevel-abovefoldlink).</span></span>

<span data-ttu-id="60b9b-115">O Defender for Endpoint estende o suporte para incluir sistemas operacionais de nível inferior, fornecendo recursos avançados de detecção e investigação de ataques em versões com suporte do Windows.</span><span class="sxs-lookup"><span data-stu-id="60b9b-115">Defender for Endpoint extends support to include down-level operating systems, providing advanced attack detection and investigation capabilities on supported Windows versions.</span></span>

<span data-ttu-id="60b9b-116">Para fazer a integração de pontos de extremidade de cliente do Windows no Nível Inferior do Defender para Ponto de Extremidade, você precisará:</span><span class="sxs-lookup"><span data-stu-id="60b9b-116">To onboard down-level Windows client endpoints to Defender for Endpoint, you'll need to:</span></span>
- <span data-ttu-id="60b9b-117">Configurar e atualizar clientes de Proteção de Ponto de Extremidade do System Center.</span><span class="sxs-lookup"><span data-stu-id="60b9b-117">Configure and update System Center Endpoint Protection clients.</span></span>
- <span data-ttu-id="60b9b-118">Instale e configure o Microsoft Monitoring Agent (MMA) para relatar dados do sensor ao Defender para o Ponto de Extremidade, conforme instruído a seguir.</span><span class="sxs-lookup"><span data-stu-id="60b9b-118">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Defender for Endpoint as instructed below.</span></span>

> [!TIP]
> <span data-ttu-id="60b9b-119">Após a integração do dispositivo, você pode optar por executar um teste de detecção para verificar se ele está corretamente conectado ao serviço.</span><span class="sxs-lookup"><span data-stu-id="60b9b-119">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="60b9b-120">Para obter mais informações, [consulte Execute a detection test on a newly onboarded Defender for Endpoint endpoint endpoint endpoint](run-detection-test.md).</span><span class="sxs-lookup"><span data-stu-id="60b9b-120">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="60b9b-121">Configurar e atualizar clientes de Proteção de Ponto de Extremidade do System Center</span><span class="sxs-lookup"><span data-stu-id="60b9b-121">Configure and update System Center Endpoint Protection clients</span></span>
> [!IMPORTANT]
> <span data-ttu-id="60b9b-122">Esta etapa só será necessária se sua organização usar o System Center Endpoint Protection (SCEP).</span><span class="sxs-lookup"><span data-stu-id="60b9b-122">This step is required only if your organization uses System Center Endpoint Protection (SCEP).</span></span>

<span data-ttu-id="60b9b-123">O Defender for Endpoint integra-se à Proteção de Ponto de Extremidade do System Center para fornecer visibilidade a detecções de malware e parar a propagação de um ataque em sua organização, proibindo arquivos potencialmente mal-intencionados ou malwares suspeitos.</span><span class="sxs-lookup"><span data-stu-id="60b9b-123">Defender for Endpoint integrates with System Center Endpoint Protection to provide visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 

<span data-ttu-id="60b9b-124">As etapas a seguir são necessárias para habilitar essa integração:</span><span class="sxs-lookup"><span data-stu-id="60b9b-124">The following steps are required to enable this integration:</span></span> 
- <span data-ttu-id="60b9b-125">Instalar a atualização da plataforma anti-malware de janeiro de [2017](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie) para clientes de Proteção de Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="60b9b-125">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)</span></span> 
- <span data-ttu-id="60b9b-126">Configurar a associação do Serviço de Proteção de Nuvem do cliente SCEP à **configuração** Avançada</span><span class="sxs-lookup"><span data-stu-id="60b9b-126">Configure the SCEP client Cloud Protection Service membership to the **Advanced** setting</span></span>
- <span data-ttu-id="60b9b-127">Configure sua rede para permitir conexões com a nuvem do Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="60b9b-127">Configure your network to allow connections to the Microsoft Defender Antivirus cloud.</span></span> <span data-ttu-id="60b9b-128">Para obter mais informações, consulte [Permitir conexões com a nuvem do Microsoft Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span><span class="sxs-lookup"><span data-stu-id="60b9b-128">For more information, see [Allow connections to the Microsoft Defender Antivirus cloud](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus#allow-connections-to-the-microsoft-defender-antivirus-cloud)</span></span>

## <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="60b9b-129">Instalar e configurar o Microsoft Monitoring Agent (MMA) para relatar dados do sensor ao Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="60b9b-129">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="60b9b-130">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="60b9b-130">Before you begin</span></span>
<span data-ttu-id="60b9b-131">Revise os seguintes detalhes para verificar os requisitos mínimos do sistema:</span><span class="sxs-lookup"><span data-stu-id="60b9b-131">Review the following details to verify minimum system requirements:</span></span>
- <span data-ttu-id="60b9b-132">Instalar a atualização mensal de fevereiro de [2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="60b9b-132">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
  > [!NOTE]
  > <span data-ttu-id="60b9b-133">Aplicável somente para Windows 7 SP1 Enterprise e Windows 7 SP1 Pro.</span><span class="sxs-lookup"><span data-stu-id="60b9b-133">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span> 

- <span data-ttu-id="60b9b-134">Instalar a [telemetria de](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) diagnóstico e a experiência do cliente</span><span class="sxs-lookup"><span data-stu-id="60b9b-134">Install the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)</span></span>

- <span data-ttu-id="60b9b-135">Instalar o [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (ou posterior) ou [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="60b9b-135">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="60b9b-136">Aplicável somente para Windows 7 SP1 Enterprise e Windows 7 SP1 Pro.</span><span class="sxs-lookup"><span data-stu-id="60b9b-136">Only applicable for Windows 7 SP1 Enterprise and Windows 7 SP1 Pro.</span></span>
    > <span data-ttu-id="60b9b-137">Não instale o .NET Framework 4.0.x, pois isso negará a instalação acima.</span><span class="sxs-lookup"><span data-stu-id="60b9b-137">Don't install .NET Framework 4.0.x, since it will negate the above installation.</span></span>

- <span data-ttu-id="60b9b-138">Atender aos requisitos mínimos do sistema do agente do Azure Log Analytics.</span><span class="sxs-lookup"><span data-stu-id="60b9b-138">Meet the Azure Log Analytics agent minimum system requirements.</span></span> <span data-ttu-id="60b9b-139">Para obter mais informações, consulte [Coletar dados de computadores em seu ambiente com o Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="60b9b-139">For more information, see [Collect data from computers in you environment with Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-concept-hybrid#prerequisites)</span></span>



1. <span data-ttu-id="60b9b-140">Baixe o arquivo de instalação do agente: [agente do Windows 64 ou](https://go.microsoft.com/fwlink/?LinkId=828603) agente do Windows [32 bits.](https://go.microsoft.com/fwlink/?LinkId=828604)</span><span class="sxs-lookup"><span data-stu-id="60b9b-140">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603) or [Windows 32-bit agent](https://go.microsoft.com/fwlink/?LinkId=828604).</span></span>

2. <span data-ttu-id="60b9b-141">Obtenha a ID do espaço de trabalho:</span><span class="sxs-lookup"><span data-stu-id="60b9b-141">Obtain the workspace ID:</span></span>
   - <span data-ttu-id="60b9b-142">No painel de navegação Defender para Ponto de Extremidade, selecione Configurações > Gerenciamento de **dispositivos > Integração**</span><span class="sxs-lookup"><span data-stu-id="60b9b-142">In the Defender for Endpoint navigation pane, select **Settings > Device management > Onboarding**</span></span>
   - <span data-ttu-id="60b9b-143">Selecione **Windows 7 SP1 e 8.1** como o sistema operacional</span><span class="sxs-lookup"><span data-stu-id="60b9b-143">Select **Windows 7 SP1 and 8.1** as the operating system</span></span>
   - <span data-ttu-id="60b9b-144">Copie a ID do espaço de trabalho e a chave do espaço de trabalho</span><span class="sxs-lookup"><span data-stu-id="60b9b-144">Copy the workspace ID and workspace key</span></span>

3. <span data-ttu-id="60b9b-145">Usando a ID do Espaço de Trabalho e a tecla Workspace, escolha qualquer um dos seguintes métodos de instalação para instalar o agente:</span><span class="sxs-lookup"><span data-stu-id="60b9b-145">Using the Workspace ID and Workspace key choose any of the following installation methods to install the agent:</span></span>
    - <span data-ttu-id="60b9b-146">[Instale manualmente o agente usando a instalação](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="60b9b-146">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> <br>
      <span data-ttu-id="60b9b-147">Na página **Opções de Instalação do** Agente, selecione Conectar o agente ao **OMS (Análise de Log do Azure)**</span><span class="sxs-lookup"><span data-stu-id="60b9b-147">On the **Agent Setup Options** page, select **Connect the agent to Azure Log Analytics (OMS)**</span></span>
    - <span data-ttu-id="60b9b-148">[Instale o agente usando a linha de comando](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span><span class="sxs-lookup"><span data-stu-id="60b9b-148">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="60b9b-149">[Configure o agente usando um script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span><span class="sxs-lookup"><span data-stu-id="60b9b-149">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

   > [!NOTE]
   > <span data-ttu-id="60b9b-150">Se você for um cliente do Governo dos EUA [,](gov.md)em "Nuvem do Azure" precisará escolher "Azure US Government" se estiver usando o assistente de instalação ou se estiver usando uma linha de comando ou um script , de definir o parâmetro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" como 1.</span><span class="sxs-lookup"><span data-stu-id="60b9b-150">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

4. <span data-ttu-id="60b9b-151">Se você estiver usando um proxy para se conectar à Internet, consulte a seção Configurar configurações de proxy.</span><span class="sxs-lookup"><span data-stu-id="60b9b-151">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="60b9b-152">Depois de concluído, você deverá ver pontos de extremidade integrados no portal dentro de uma hora.</span><span class="sxs-lookup"><span data-stu-id="60b9b-152">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="configure-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="60b9b-153">Configurar configurações de conectividade de proxy e Internet</span><span class="sxs-lookup"><span data-stu-id="60b9b-153">Configure proxy and Internet connectivity settings</span></span>
 
- <span data-ttu-id="60b9b-154">Cada ponto de extremidade do Windows deve ser capaz de se conectar à Internet usando HTTPS.</span><span class="sxs-lookup"><span data-stu-id="60b9b-154">Each Windows endpoint must be able to connect to the Internet using HTTPS.</span></span> <span data-ttu-id="60b9b-155">Essa conexão pode ser direta, usando um proxy ou por meio do [Gateway OMS.](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway)</span><span class="sxs-lookup"><span data-stu-id="60b9b-155">This connection can be direct, using a proxy, or through the [OMS Gateway](https://docs.microsoft.com/azure/log-analytics/log-analytics-oms-gateway).</span></span>
- <span data-ttu-id="60b9b-156">Se um proxy ou firewall estiver bloqueando todo o tráfego por padrão e permitindo apenas domínios específicos por meio ou a verificação de HTTPS (inspeção SSL) estiver habilitada, certifique-se de que você habilita o acesso a [URLs](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)de serviço do Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="60b9b-156">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through or HTTPS scanning (SSL inspection) is enabled, make sure that you [enable access to Defender for Endpoint service URLs](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

## <a name="offboard-client-endpoints"></a><span data-ttu-id="60b9b-157">Pontos de extremidade do cliente de offboard</span><span class="sxs-lookup"><span data-stu-id="60b9b-157">Offboard client endpoints</span></span>
<span data-ttu-id="60b9b-158">Para offboard, você pode desinstalar o agente MMA do ponto de extremidade ou desconecta-lo do relatório para o seu espaço de trabalho do Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="60b9b-158">To offboard, you can uninstall the MMA agent from the endpoint or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="60b9b-159">Depois de fazer o offboard do agente, o ponto de extremidade não enviará mais dados do sensor para o Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="60b9b-159">After offboarding the agent, the endpoint will no longer send sensor data to Defender for Endpoint.</span></span> 

> <span data-ttu-id="60b9b-160">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="60b9b-160">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="60b9b-161">[Inscreva-se para uma avaliação gratuita](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).</span><span class="sxs-lookup"><span data-stu-id="60b9b-161">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-downlevele-belowfoldlink).</span></span>

