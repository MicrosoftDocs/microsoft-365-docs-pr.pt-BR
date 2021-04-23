---
title: Onboard Windows servers to the Microsoft Defender for Endpoint service
description: Integração de servidores Windows para que eles possam enviar dados do sensor para o sensor do Microsoft Defender para Ponto de Extremidade.
keywords: servidor de integração, servidor, 2012r2, 2016, 2019, integração de servidor, gerenciamento de dispositivos, configurar o Microsoft Defender para servidores de Ponto de Extremidade, a integração do Microsoft Defender para servidores de Ponto de Extremidade, a integração do Microsoft Defender para servidores de Ponto de Extremidade
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 17aca5fb388aef26504902ee63b22410420c8827
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952483"
---
# <a name="onboard-windows-servers-to-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="07ecd-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span><span class="sxs-lookup"><span data-stu-id="07ecd-104">Onboard Windows servers to the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="07ecd-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="07ecd-105">**Applies to:**</span></span>

- <span data-ttu-id="07ecd-106">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="07ecd-106">Windows Server 2008 R2 SP1</span></span>
- <span data-ttu-id="07ecd-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="07ecd-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="07ecd-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="07ecd-108">Windows Server 2016</span></span>
- <span data-ttu-id="07ecd-109">Windows Server (SAC) versão 1803 e posterior</span><span class="sxs-lookup"><span data-stu-id="07ecd-109">Windows Server (SAC) version 1803 and later</span></span>
- <span data-ttu-id="07ecd-110">Windows Server 2019 e posterior</span><span class="sxs-lookup"><span data-stu-id="07ecd-110">Windows Server 2019 and later</span></span>
- <span data-ttu-id="07ecd-111">Edição principal do Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="07ecd-111">Windows Server 2019 core edition</span></span>

> <span data-ttu-id="07ecd-112">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="07ecd-112">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="07ecd-113">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="07ecd-113">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configserver-abovefoldlink)

<span data-ttu-id="07ecd-114">O Defender for Endpoint estende o suporte para incluir também o sistema operacional Windows Server.</span><span class="sxs-lookup"><span data-stu-id="07ecd-114">Defender for Endpoint extends support to also include the Windows Server operating system.</span></span> <span data-ttu-id="07ecd-115">Esse suporte fornece recursos avançados de detecção e investigação de ataques perfeitamente por meio do console do Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="07ecd-115">This support provides advanced attack detection and investigation capabilities seamlessly through the Microsoft Defender Security Center console.</span></span>

<span data-ttu-id="07ecd-116">Para obter uma orientação prática sobre o que precisa ser feito para licenciamento e infraestrutura, consulte Protegendo servidores [Windows com o Defender para Ponto de Extremidade.](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128)</span><span class="sxs-lookup"><span data-stu-id="07ecd-116">For a practical guidance on what needs to be in place for licensing and infrastructure, see [Protecting Windows Servers with Defender for Endpoint](https://techcommunity.microsoft.com/t5/What-s-New/Protecting-Windows-Server-with-Windows-Defender-ATP/m-p/267114#M128).</span></span>

<span data-ttu-id="07ecd-117">Para obter orientações sobre como baixar e usar as Linhas de Base de Segurança do Windows para servidores Windows, consulte Linhas de Base de Segurança do [Windows.](https://docs.microsoft.com/windows/device-security/windows-security-baselines)</span><span class="sxs-lookup"><span data-stu-id="07ecd-117">For guidance on how to download and use Windows Security Baselines for Windows servers, see [Windows Security Baselines](https://docs.microsoft.com/windows/device-security/windows-security-baselines).</span></span>

## <a name="windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016"></a><span data-ttu-id="07ecd-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2 e Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="07ecd-118">Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016</span></span>

<span data-ttu-id="07ecd-119">Você pode integrar o Windows Server 2008 R2 SP1, o Windows Server 2012 R2 e o Windows Server 2016 para o Defender para Ponto de Extremidade usando qualquer uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="07ecd-119">You can onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, and Windows Server 2016 to Defender for Endpoint by using any of the following options:</span></span>

- <span data-ttu-id="07ecd-120">**Opção 1:** [Integrando instalando e configurando o Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span><span class="sxs-lookup"><span data-stu-id="07ecd-120">**Option 1**: [Onboard by installing and configuring Microsoft Monitoring Agent (MMA)](#option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma)</span></span>
- <span data-ttu-id="07ecd-121">**Opção 2**: [Integração por meio do Centro de Segurança do Azure](#option-2-onboard-windows-servers-through-azure-security-center)</span><span class="sxs-lookup"><span data-stu-id="07ecd-121">**Option 2**: [Onboard through Azure Security Center](#option-2-onboard-windows-servers-through-azure-security-center)</span></span>
- <span data-ttu-id="07ecd-122">**Opção 3**: [Integração com o Microsoft Endpoint Manager versão 2002 e posterior](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span><span class="sxs-lookup"><span data-stu-id="07ecd-122">**Option 3**: [Onboard through Microsoft Endpoint Manager version 2002 and later](#option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later)</span></span>

<span data-ttu-id="07ecd-123">Após concluir as etapas de integração usando qualquer uma das opções fornecidas, você precisará configurar e atualizar os clientes de Proteção de Ponto de Extremidade do [System Center.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="07ecd-123">After completing the onboarding steps using any of the provided options, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="07ecd-124">A licença de servidor autônomo do Defender for Endpoint é necessária, por nó, para a integração de um servidor Windows por meio do Microsoft Monitoring Agent (Opção 1) ou por meio do Microsoft Endpoint Manager (Opção 3).</span><span class="sxs-lookup"><span data-stu-id="07ecd-124">Defender for Endpoint standalone server license is required, per node, in order to onboard a Windows server through Microsoft Monitoring Agent (Option 1), or through Microsoft Endpoint Manager (Option 3).</span></span> <span data-ttu-id="07ecd-125">Como alternativa, uma licença do Azure Defender for Servers é necessária, por nó, para a integração de um servidor Windows por meio do Centro de Segurança do Azure (Opção 2), consulte Recursos com suporte disponíveis no [Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-services).</span><span class="sxs-lookup"><span data-stu-id="07ecd-125">Alternatively, an Azure Defender for Servers license is required, per node, in order to onboard a Windows server through Azure Security Center (Option 2), see [Supported features available in Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-services).</span></span>

### <a name="option-1-onboard-by-installing-and-configuring-microsoft-monitoring-agent-mma"></a><span data-ttu-id="07ecd-126">Opção 1: Integrando instalando e configurando o Microsoft Monitoring Agent (MMA)</span><span class="sxs-lookup"><span data-stu-id="07ecd-126">Option 1: Onboard by installing and configuring Microsoft Monitoring Agent (MMA)</span></span>

<span data-ttu-id="07ecd-127">Você precisará instalar e configurar o MMA para servidores Windows para relatar dados do sensor ao Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="07ecd-127">You'll need to install and configure MMA for Windows servers to report sensor data to Defender for Endpoint.</span></span> <span data-ttu-id="07ecd-128">Para obter mais informações, consulte [Coletar dados de log com o agente do Azure Log Analytics.](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)</span><span class="sxs-lookup"><span data-stu-id="07ecd-128">For more information, see [Collect log data with Azure Log Analytics agent](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span></span>

<span data-ttu-id="07ecd-129">Se você já estiver usando o System Center Operations Manager (SCOM) ou o Azure Monitor (anteriormente conhecido como Operations Management Suite (OMS),anexe o Microsoft Monitoring Agent (MMA) para relatar ao seu espaço de trabalho do Defender para Ponto de Extremidade por meio do suporte a Multihoming.</span><span class="sxs-lookup"><span data-stu-id="07ecd-129">If you're already using System Center Operations Manager (SCOM) or Azure Monitor (formerly known as Operations Management Suite (OMS)), attach the Microsoft Monitoring Agent (MMA) to report to your Defender for Endpoint workspace through Multihoming support.</span></span>

<span data-ttu-id="07ecd-130">Em geral, você precisará seguir as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="07ecd-130">In general, you'll need to take the following steps:</span></span>

1. <span data-ttu-id="07ecd-131">Cumpra os requisitos de integração descritos na **seção Antes de** começar.</span><span class="sxs-lookup"><span data-stu-id="07ecd-131">Fulfill the onboarding requirements outlined in **Before you begin** section.</span></span>
2. <span data-ttu-id="07ecd-132">Ativar o monitoramento do servidor do Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="07ecd-132">Turn on server monitoring from Microsoft Defender Security center.</span></span>
3. <span data-ttu-id="07ecd-133">Instale e configure o MMA para o servidor relatar dados do sensor ao Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="07ecd-133">Install and configure MMA for the server to report sensor data to Defender for Endpoint.</span></span>
4. <span data-ttu-id="07ecd-134">Configurar e atualizar clientes de Proteção de Ponto de Extremidade do System Center.</span><span class="sxs-lookup"><span data-stu-id="07ecd-134">Configure and update System Center Endpoint Protection clients.</span></span>

> [!TIP]
> <span data-ttu-id="07ecd-135">Após a integração do dispositivo, você pode optar por executar um teste de detecção para verificar se ele está corretamente conectado ao serviço.</span><span class="sxs-lookup"><span data-stu-id="07ecd-135">After onboarding the device, you can choose to run a detection test to verify that it is properly onboarded to the service.</span></span> <span data-ttu-id="07ecd-136">Para obter mais informações, [consulte Execute a detection test on a newly onboarded Defender for Endpoint endpoint endpoint endpoint](run-detection-test.md).</span><span class="sxs-lookup"><span data-stu-id="07ecd-136">For more information, see [Run a detection test on a newly onboarded Defender for Endpoint endpoint](run-detection-test.md).</span></span>

#### <a name="before-you-begin"></a><span data-ttu-id="07ecd-137">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="07ecd-137">Before you begin</span></span>

<span data-ttu-id="07ecd-138">Execute as seguintes etapas para atender aos requisitos de integração:</span><span class="sxs-lookup"><span data-stu-id="07ecd-138">Perform the following steps to fulfill the onboarding requirements:</span></span>

<span data-ttu-id="07ecd-139">Para Windows Server 2008 R2 SP1 ou Windows Server 2012 R2, certifique-se de instalar o seguinte hotfix:</span><span class="sxs-lookup"><span data-stu-id="07ecd-139">For Windows Server 2008 R2 SP1 or Windows Server 2012 R2, ensure that you install the following hotfix:</span></span>

- [<span data-ttu-id="07ecd-140">Atualização para experiência do cliente e telemetria de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="07ecd-140">Update for customer experience and diagnostic telemetry</span></span>](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)

<span data-ttu-id="07ecd-141">Para o Windows Server 2008 R2 SP1, certifique-se de atender aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="07ecd-141">For Windows Server 2008 R2 SP1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="07ecd-142">Instalar o [acúmulo de atualizações mensal de fevereiro](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="07ecd-142">Install the [February monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
- <span data-ttu-id="07ecd-143">Instalar o [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (ou posterior) ou [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="07ecd-143">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

    > [!NOTE]
    > <span data-ttu-id="07ecd-144">Se você estiver gerenciando seu Windows Server 2008 R2 SP1 com SCCM, o agente cliente SCCM instalará o .Net Framework 4.5.2.</span><span class="sxs-lookup"><span data-stu-id="07ecd-144">If you are managing your Windows Server 2008 R2 SP1 with SCCM, the SCCM client agent installs .Net Framework 4.5.2.</span></span> <span data-ttu-id="07ecd-145">Portanto, você não precisa instalar o .NET framework 4.5 (ou posterior).</span><span class="sxs-lookup"><span data-stu-id="07ecd-145">So you don't need to install the .NET framework 4.5 (or later).</span></span>

<span data-ttu-id="07ecd-146">Para Windows Server 2008 R2 SP1 e Windows Server 2012 R2: Configurar e atualizar clientes de Proteção de Ponto de Extremidade do [System Center.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="07ecd-146">For Windows Server 2008 R2 SP1 and Windows Server 2012 R2: [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
> <span data-ttu-id="07ecd-147">Esta etapa só será necessária se sua organização usar o System Center Endpoint Protection (SCEP) e você estiver integrando o Windows Server 2008 R2 SP1 e o Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="07ecd-147">This step is required only if your organization uses System Center Endpoint Protection (SCEP) and you're onboarding Windows Server 2008 R2 SP1 and Windows Server 2012 R2.</span></span>

### <a name="install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="07ecd-148">Instalar e configurar o Microsoft Monitoring Agent (MMA) para relatar dados do sensor ao Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="07ecd-148">Install and configure Microsoft Monitoring Agent (MMA) to report sensor data to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="07ecd-149">Baixe o arquivo de instalação do agente: [agente do Windows 64 bits.](https://go.microsoft.com/fwlink/?LinkId=828603)</span><span class="sxs-lookup"><span data-stu-id="07ecd-149">Download the agent setup file: [Windows 64-bit agent](https://go.microsoft.com/fwlink/?LinkId=828603).</span></span>

2. <span data-ttu-id="07ecd-150">Usando a ID do Workspace e a chave do Workspace obtidas no procedimento anterior, escolha qualquer um dos seguintes métodos de instalação para instalar o agente no servidor Windows:</span><span class="sxs-lookup"><span data-stu-id="07ecd-150">Using the Workspace ID and Workspace key obtained in the previous procedure, choose any of the following installation methods to install the agent on the Windows server:</span></span>
    - <span data-ttu-id="07ecd-151">[Instale manualmente o agente usando a instalação](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span><span class="sxs-lookup"><span data-stu-id="07ecd-151">[Manually install the agent using setup](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-setup-wizard).</span></span> 
    <span data-ttu-id="07ecd-152">Na página **Opções de Instalação do** Agente, escolha Conectar o agente ao **OMS (Análise de Log do Azure).**</span><span class="sxs-lookup"><span data-stu-id="07ecd-152">On the **Agent Setup Options** page, choose **Connect the agent to Azure Log Analytics (OMS)**.</span></span>
    - <span data-ttu-id="07ecd-153">[Instale o agente usando a linha de comando](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span><span class="sxs-lookup"><span data-stu-id="07ecd-153">[Install the agent using the command line](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-command-line).</span></span>
    - <span data-ttu-id="07ecd-154">[Configure o agente usando um script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span><span class="sxs-lookup"><span data-stu-id="07ecd-154">[Configure the agent using a script](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#install-agent-using-dsc-in-azure-automation).</span></span>

> [!NOTE]
> <span data-ttu-id="07ecd-155">Se você for um cliente do Governo dos EUA [,](gov.md)em "Nuvem do Azure" precisará escolher "Azure US Government" se estiver usando o assistente de instalação ou se estiver usando uma linha de comando ou um script , de definir o parâmetro "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" como 1.</span><span class="sxs-lookup"><span data-stu-id="07ecd-155">If you are a [US Government customer](gov.md), under "Azure Cloud" you'll need to choose "Azure US Government" if using the setup wizard, or if using a command line or a script - set the "OPINSIGHTS_WORKSPACE_AZURE_CLOUD_TYPE" parameter to 1.</span></span>

### <a name="configure-windows-server-proxy-and-internet-connectivity-settings-if-needed"></a><span data-ttu-id="07ecd-156">Configurar configurações de conectividade com o servidor Windows e a Internet, se necessário</span><span class="sxs-lookup"><span data-stu-id="07ecd-156">Configure Windows server proxy and Internet connectivity settings if needed</span></span>

<span data-ttu-id="07ecd-157">Se os servidores precisarem usar um proxy para se comunicar com o Defender para Ponto de Extremidade, use um dos seguintes métodos para configurar o MMA para usar o servidor proxy:</span><span class="sxs-lookup"><span data-stu-id="07ecd-157">If your servers need to use a proxy to communicate with Defender for Endpoint, use one of the following methods to configure the MMA to use the proxy server:</span></span>

- [<span data-ttu-id="07ecd-158">Configurar o MMA para usar um servidor proxy</span><span class="sxs-lookup"><span data-stu-id="07ecd-158">Configure the MMA to use a proxy server</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/agent-windows#install-agent-using-setup-wizard)

- [<span data-ttu-id="07ecd-159">Configurar o Windows para usar um servidor proxy para todas as conexões</span><span class="sxs-lookup"><span data-stu-id="07ecd-159">Configure Windows to use a proxy server for all connections</span></span>](configure-proxy-internet.md)

<span data-ttu-id="07ecd-160">Se um proxy ou firewall estiver em uso, verifique se os servidores podem acessar todas as URLs de serviço do Microsoft Defender para Ponto de Extremidade diretamente e sem interceptação SSL.</span><span class="sxs-lookup"><span data-stu-id="07ecd-160">If a proxy or firewall is in use, please ensure that servers can access all of the Microsoft Defender for Endpoint service URLs directly and without SSL interception.</span></span> <span data-ttu-id="07ecd-161">Para obter mais informações, consulte [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="07ecd-161">For more information, see [enable access to Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="07ecd-162">O uso da interceptação SSL impedirá que o sistema se comunique com o serviço Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="07ecd-162">Use of SSL interception will prevent the system from communicating with the Defender for Endpoint service.</span></span>

<span data-ttu-id="07ecd-163">Depois de concluído, você deverá ver servidores Windows internados no portal dentro de uma hora.</span><span class="sxs-lookup"><span data-stu-id="07ecd-163">Once completed, you should see onboarded Windows servers in the portal within an hour.</span></span>

### <a name="option-2-onboard-windows-servers-through-azure-security-center"></a><span data-ttu-id="07ecd-164">Opção 2: Integração de servidores Windows por meio do Centro de Segurança do Azure</span><span class="sxs-lookup"><span data-stu-id="07ecd-164">Option 2: Onboard Windows servers through Azure Security Center</span></span>

1. <span data-ttu-id="07ecd-165">No painel de navegação do Centro de Segurança do Microsoft Defender, selecione **Configurações**  >  **Gerenciamento de**  >  **dispositivos Integrando**.</span><span class="sxs-lookup"><span data-stu-id="07ecd-165">In the Microsoft Defender Security Center navigation pane, select **Settings** > **Device management** > **Onboarding**.</span></span>

2. <span data-ttu-id="07ecd-166">Selecione **Windows Server 2008 R2 SP1, 2012 R2 e 2016** como o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="07ecd-166">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system.</span></span>

3. <span data-ttu-id="07ecd-167">Clique **em Servidores Integrados no Centro de Segurança do Azure.**</span><span class="sxs-lookup"><span data-stu-id="07ecd-167">Click **Onboard Servers in Azure Security Center**.</span></span>

4. <span data-ttu-id="07ecd-168">Siga as instruções de integração no Microsoft Defender para Ponto de Extremidade com [o Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-wdatp) e, se você estiver usando o Azure ARC, siga as instruções de integração em [Habilitando](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration)a integração do Microsoft Defender para Ponto de Extremidade .</span><span class="sxs-lookup"><span data-stu-id="07ecd-168">Follow the onboarding instructions in [Microsoft Defender for Endpoint with Azure Defender](https://docs.microsoft.com/azure/security-center/security-center-wdatp) and If you are using Azure ARC, Follow the onboarding instructions in [Enabling the Microsoft Defender for Endpoint integration](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enabling-the-microsoft-defender-for-endpoint-integration).</span></span>

<span data-ttu-id="07ecd-169">Após concluir as etapas de integração, você precisará configurar e atualizar os clientes de Proteção de Ponto de Extremidade do [System Center.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="07ecd-169">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

> [!NOTE]
>
> - <span data-ttu-id="07ecd-170">Para que a integração por meio do Azure Defender for Servers funcione conforme o esperado, o servidor deve ter um espaço de trabalho e uma chave apropriados configurados nas configurações do Microsoft Monitoring Agent (MMA).</span><span class="sxs-lookup"><span data-stu-id="07ecd-170">For onboarding via Azure Defender for Servers to work as expected, the server must have an appropriate workspace and key configured within the Microsoft Monitoring Agent (MMA) settings.</span></span>
> - <span data-ttu-id="07ecd-171">Depois de configurado, o pacote de gerenciamento de nuvem apropriado é implantado no computador e o processo de sensor (MsSenseS.exe) será implantado e iniciado.</span><span class="sxs-lookup"><span data-stu-id="07ecd-171">Once configured, the appropriate cloud management pack is deployed on the machine and the sensor process (MsSenseS.exe) will be deployed and started.</span></span>
> - <span data-ttu-id="07ecd-172">Isso também será necessário se o servidor estiver configurado para usar um servidor gateway OMS como proxy.</span><span class="sxs-lookup"><span data-stu-id="07ecd-172">This is also required if the server is configured to use an OMS Gateway server as proxy.</span></span>

### <a name="option-3-onboard-windows-servers-through-microsoft-endpoint-manager-version-2002-and-later"></a><span data-ttu-id="07ecd-173">Opção 3: Integração de servidores Windows por meio do Microsoft Endpoint Manager versão 2002 e posterior</span><span class="sxs-lookup"><span data-stu-id="07ecd-173">Option 3: Onboard Windows servers through Microsoft Endpoint Manager version 2002 and later</span></span>

<span data-ttu-id="07ecd-174">Você pode integrar o Windows Server 2012 R2 e o Windows Server 2016 usando o Microsoft Endpoint Manager versão 2002 e posterior.</span><span class="sxs-lookup"><span data-stu-id="07ecd-174">You can onboard Windows Server 2012 R2 and Windows Server 2016 by using Microsoft Endpoint Manager version 2002 and later.</span></span> <span data-ttu-id="07ecd-175">Para obter mais informações, consulte [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="07ecd-175">For more information, see [Microsoft Defender for Endpoint in Microsoft Endpoint Manager current branch](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection).</span></span>

<span data-ttu-id="07ecd-176">Após concluir as etapas de integração, você precisará configurar e atualizar os clientes de Proteção de Ponto de Extremidade do [System Center.](#configure-and-update-system-center-endpoint-protection-clients)</span><span class="sxs-lookup"><span data-stu-id="07ecd-176">After completing the onboarding steps, you'll need to [Configure and update System Center Endpoint Protection clients](#configure-and-update-system-center-endpoint-protection-clients).</span></span>

## <a name="windows-server-sac-version-1803-windows-server-2019-and-windows-server-2019-core-edition"></a><span data-ttu-id="07ecd-177">Windows Server (SAC) versão 1803, Windows Server 2019 e Windows Server 2019 Core edition</span><span class="sxs-lookup"><span data-stu-id="07ecd-177">Windows Server (SAC) version 1803, Windows Server 2019, and Windows Server 2019 Core edition</span></span>

<span data-ttu-id="07ecd-178">Você pode integrar o Windows Server (SAC) versão 1803, o Windows Server 2019 ou a edição Core do Windows Server 2019 usando os seguintes métodos de implantação:</span><span class="sxs-lookup"><span data-stu-id="07ecd-178">You can onboard Windows Server (SAC) version 1803, Windows Server 2019, or Windows Server 2019 Core edition by using the following deployment methods:</span></span>

- [<span data-ttu-id="07ecd-179">Script local</span><span class="sxs-lookup"><span data-stu-id="07ecd-179">Local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="07ecd-180">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="07ecd-180">Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="07ecd-181">Gerenciador de Configuração do Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="07ecd-181">Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="07ecd-182">System Center Configuration Manager 2012 /2012 R2 1511 / 1602</span><span class="sxs-lookup"><span data-stu-id="07ecd-182">System Center Configuration Manager 2012 / 2012 R2  1511 / 1602</span></span>](configure-endpoints-sccm.md#onboard-devices-using-system-center-configuration-manager)
- [<span data-ttu-id="07ecd-183">Scripts de integração VDI para dispositivos não persistentes</span><span class="sxs-lookup"><span data-stu-id="07ecd-183">VDI onboarding scripts for non-persistent devices</span></span>](configure-endpoints-vdi.md)

> [!NOTE]
>
> - <span data-ttu-id="07ecd-184">O pacote de integração do Windows Server 2019 por meio do Microsoft Endpoint Manager atualmente envia um script.</span><span class="sxs-lookup"><span data-stu-id="07ecd-184">The Onboarding package for Windows Server 2019 through Microsoft Endpoint Manager currently ships a script.</span></span> <span data-ttu-id="07ecd-185">Para obter mais informações sobre como implantar scripts no Configuration Manager, consulte [Pacotes e programas no Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span><span class="sxs-lookup"><span data-stu-id="07ecd-185">For more information on how to deploy scripts in Configuration Manager, see [Packages and programs in Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/packages-and-programs).</span></span>
> - <span data-ttu-id="07ecd-186">Um script local é adequado para uma prova de conceito, mas não deve ser usado para implantação de produção.</span><span class="sxs-lookup"><span data-stu-id="07ecd-186">A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="07ecd-187">Para uma implantação de produção, recomendamos usar a Política de Grupo ou o Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="07ecd-187">For a production deployment, we recommend using Group Policy, or Microsoft Endpoint Configuration Manager.</span></span>

<span data-ttu-id="07ecd-188">O suporte para o Windows Server fornece informações mais profundas sobre atividades do servidor, cobertura para detecção de ataque de kernel e memória e habilita ações de resposta.</span><span class="sxs-lookup"><span data-stu-id="07ecd-188">Support for Windows Server provides deeper insight into server activities, coverage for kernel and memory attack detection, and enables response actions.</span></span>

1. <span data-ttu-id="07ecd-189">Configure as configurações de integração do Defender para Ponto de Extremidade no servidor Windows usando as mesmas ferramentas e métodos para dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="07ecd-189">Configure Defender for Endpoint onboarding settings on the Windows server using the same tools and methods for Windows 10 devices.</span></span> <span data-ttu-id="07ecd-190">Para obter mais informações, consulte [Onboard Windows 10 devices](configure-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="07ecd-190">For more information, see [Onboard Windows 10 devices](configure-endpoints.md).</span></span>

2. <span data-ttu-id="07ecd-191">Se você estiver executando uma solução anti-malware de terceiros, precisará aplicar as seguintes configurações de modo passivo do Microsoft Defender AV.</span><span class="sxs-lookup"><span data-stu-id="07ecd-191">If you're running a third-party anti-malware solution, you'll need to apply the following Microsoft Defender AV passive mode settings.</span></span> <span data-ttu-id="07ecd-192">Verifique se ele foi configurado corretamente:</span><span class="sxs-lookup"><span data-stu-id="07ecd-192">Verify that it was configured correctly:</span></span>

    1. <span data-ttu-id="07ecd-193">De definir a seguinte entrada do Registro:</span><span class="sxs-lookup"><span data-stu-id="07ecd-193">Set the following registry entry:</span></span>
       - <span data-ttu-id="07ecd-194">Caminho: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="07ecd-194">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
       - <span data-ttu-id="07ecd-195">Nome: ForceDefenderPassiveMode</span><span class="sxs-lookup"><span data-stu-id="07ecd-195">Name: ForceDefenderPassiveMode</span></span>
       - <span data-ttu-id="07ecd-196">Tipo: REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="07ecd-196">Type: REG_DWORD</span></span>
       - <span data-ttu-id="07ecd-197">Value: 1</span><span class="sxs-lookup"><span data-stu-id="07ecd-197">Value: 1</span></span>

    1. <span data-ttu-id="07ecd-198">Execute o seguinte comando do PowerShell para verificar se o modo passivo foi configurado:</span><span class="sxs-lookup"><span data-stu-id="07ecd-198">Run the following PowerShell command to verify that the passive mode was configured:</span></span>

       ```PowerShell
       Get-WinEvent -FilterHashtable @{ProviderName="Microsoft-Windows-Sense" ;ID=84}
       ```

    1. <span data-ttu-id="07ecd-199">Confirme se um evento recente que contém o evento de modo passivo foi encontrado:</span><span class="sxs-lookup"><span data-stu-id="07ecd-199">Confirm  that a recent event containing the passive mode event is found:</span></span>

       ![Imagem do resultado de verificação do modo passivo](images/atp-verify-passive-mode.png)

3. <span data-ttu-id="07ecd-201">Execute o seguinte comando para verificar se o Microsoft Defender AV está instalado:</span><span class="sxs-lookup"><span data-stu-id="07ecd-201">Run the following command to check if Microsoft Defender AV is installed:</span></span>

   ```sc.exe query Windefend```

    <span data-ttu-id="07ecd-202">Se o resultado for 'O serviço especificado não existe como um serviço instalado', você precisará instalar o Microsoft Defender AV.</span><span class="sxs-lookup"><span data-stu-id="07ecd-202">If the result is 'The specified service doesn't exist as an installed service', then you'll need to install Microsoft Defender AV.</span></span> <span data-ttu-id="07ecd-203">Para obter mais informações, consulte [Microsoft Defender Antivírus no Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span><span class="sxs-lookup"><span data-stu-id="07ecd-203">For more information, see [Microsoft Defender Antivirus in Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).</span></span>

    <span data-ttu-id="07ecd-204">Para obter informações sobre como usar a Política de Grupo para configurar e gerenciar o Microsoft Defender Antivírus em seus servidores Windows, consulte [Use Group Policy settings to configure and manage Microsoft Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="07ecd-204">For information on how to use Group Policy to configure and manage Microsoft Defender Antivirus on your Windows servers, see [Use Group Policy settings to configure and manage Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus).</span></span>

## <a name="integration-with-azure-defender"></a><span data-ttu-id="07ecd-205">Integração com o Azure Defender</span><span class="sxs-lookup"><span data-stu-id="07ecd-205">Integration with Azure Defender</span></span>

<span data-ttu-id="07ecd-206">O Defender for Endpoint pode se integrar ao Azure Defender para fornecer uma solução abrangente de proteção do servidor Windows.</span><span class="sxs-lookup"><span data-stu-id="07ecd-206">Defender for Endpoint can integrate with Azure Defender to provide a comprehensive Windows server protection solution.</span></span> <span data-ttu-id="07ecd-207">Com essa integração, o Azure Defender pode usar o poder do Defender para o Ponto de Extremidade para fornecer detecção aprimorada de ameaças para servidores Windows.</span><span class="sxs-lookup"><span data-stu-id="07ecd-207">With this integration, Azure Defender can use the power of Defender for Endpoint to provide improved threat detection for Windows Servers.</span></span>

<span data-ttu-id="07ecd-208">Os seguintes recursos estão incluídos nesta integração:</span><span class="sxs-lookup"><span data-stu-id="07ecd-208">The following capabilities are included in this integration:</span></span>

- <span data-ttu-id="07ecd-209">Integração automatizada - o sensor defender para ponto de extremidade é habilitado automaticamente em Servidores Windows que estão integrados ao Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="07ecd-209">Automated onboarding - Defender for Endpoint sensor is automatically enabled on Windows Servers that are onboarded to Azure Defender.</span></span> <span data-ttu-id="07ecd-210">Para obter mais informações sobre a integração do Azure Defender, [consulte Use the integrated Microsoft Defender for Endpoint license](https://docs.microsoft.com/azure/security-center/security-center-wdatp).</span><span class="sxs-lookup"><span data-stu-id="07ecd-210">For more information on Azure Defender onboarding, see [Use the integrated Microsoft Defender for Endpoint license](https://docs.microsoft.com/azure/security-center/security-center-wdatp).</span></span>

    > [!NOTE]
    > <span data-ttu-id="07ecd-211">A integração entre o Azure Defender for Servers e o Microsoft Defender for Endpoint foi expandida para dar suporte ao Windows Server 2019 e à Área de Trabalho [Virtual do Windows (WVD).](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)</span><span class="sxs-lookup"><span data-stu-id="07ecd-211">The integration between Azure Defender for Servers and Microsoft Defender for Endpoint has been expanded to support [Windows Server 2019 and Windows Virtual Desktop (WVD)](https://docs.microsoft.com/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview).</span></span>

- <span data-ttu-id="07ecd-212">Os servidores Windows monitorados pelo Azure Defender também estarão disponíveis no Defender para Ponto de Extremidade - o Azure Defender conecta-se perfeitamente ao locatário do Defender para Ponto de Extremidade, fornecendo uma única exibição entre clientes e servidores.</span><span class="sxs-lookup"><span data-stu-id="07ecd-212">Windows servers monitored by Azure Defender will also be available in Defender for Endpoint - Azure Defender seamlessly connects to the Defender for Endpoint tenant, providing a single view across clients and servers.</span></span>  <span data-ttu-id="07ecd-213">Além disso, os alertas do Defender para Ponto de Extremidade estarão disponíveis no console do Azure Defender.</span><span class="sxs-lookup"><span data-stu-id="07ecd-213">In addition, Defender for Endpoint alerts will be available in the Azure Defender console.</span></span>
- <span data-ttu-id="07ecd-214">Investigação do servidor - Os clientes do Azure Defender podem acessar o Centro de Segurança do Microsoft Defender para executar uma investigação detalhada para descobrir o escopo de uma possível violação.</span><span class="sxs-lookup"><span data-stu-id="07ecd-214">Server investigation -  Azure Defender customers can access Microsoft Defender Security Center to perform detailed investigation to uncover the scope of a potential breach.</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="07ecd-215">Quando você usa o Azure Defender para monitorar servidores, um locatário do Defender for Endpoint é criado automaticamente (nos EUA para usuários dos EUA, na UE para usuários europeus e do Reino Unido).</span><span class="sxs-lookup"><span data-stu-id="07ecd-215">When you use Azure Defender to monitor servers, a Defender for Endpoint tenant is automatically created (in the US for US users, in the EU for European and UK users).</span></span><br>
<span data-ttu-id="07ecd-216">Os dados coletados pelo Defender para Ponto de Extremidade são armazenados na localização geográfica do locatário conforme identificado durante o provisionamento.</span><span class="sxs-lookup"><span data-stu-id="07ecd-216">Data collected by Defender for Endpoint is stored in the geo-location of the tenant as identified during provisioning.</span></span>
> - <span data-ttu-id="07ecd-217">Se você usar o Defender para o Ponto de Extremidade antes de usar o Azure Defender, seus dados serão armazenados no local especificado ao criar seu locatário, mesmo que você se integre ao Azure Defender posteriormente.</span><span class="sxs-lookup"><span data-stu-id="07ecd-217">If you use Defender for Endpoint before using Azure Defender, your data will be stored in the location you specified when you created your tenant even if you integrate with Azure Defender at a later time.</span></span>
> - <span data-ttu-id="07ecd-218">Depois de configurado, você não pode alterar o local onde seus dados estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="07ecd-218">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="07ecd-219">Se precisar mover seus dados para outro local, entre em contato com o Suporte da Microsoft para redefinir o locatário.</span><span class="sxs-lookup"><span data-stu-id="07ecd-219">If you need to move your data to another location, you need to contact Microsoft Support to reset the tenant.</span></span> <br>
<span data-ttu-id="07ecd-220">O monitoramento do ponto de extremidade do servidor que utiliza essa integração foi desabilitado para clientes do Office 365 GCC.</span><span class="sxs-lookup"><span data-stu-id="07ecd-220">Server endpoint monitoring utilizing this integration has been disabled for Office 365 GCC customers.</span></span>

## <a name="configure-and-update-system-center-endpoint-protection-clients"></a><span data-ttu-id="07ecd-221">Configurar e atualizar clientes de Proteção de Ponto de Extremidade do System Center</span><span class="sxs-lookup"><span data-stu-id="07ecd-221">Configure and update System Center Endpoint Protection clients</span></span>

<span data-ttu-id="07ecd-222">O Defender para Ponto de Extremidade se integra à Proteção de Ponto de Extremidade do System Center.</span><span class="sxs-lookup"><span data-stu-id="07ecd-222">Defender for Endpoint integrates with System Center Endpoint Protection.</span></span> <span data-ttu-id="07ecd-223">A integração fornece visibilidade para detecções de malware e para interromper a propagação de um ataque em sua organização, proibindo arquivos potencialmente mal-intencionados ou malwares suspeitos.</span><span class="sxs-lookup"><span data-stu-id="07ecd-223">The integration provides visibility to malware detections and to stop propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span>

<span data-ttu-id="07ecd-224">As etapas a seguir são necessárias para habilitar essa integração:</span><span class="sxs-lookup"><span data-stu-id="07ecd-224">The following steps are required to enable this integration:</span></span>

- <span data-ttu-id="07ecd-225">Instale a atualização da plataforma anti-malware de janeiro de [2017](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie)para clientes de Proteção de Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="07ecd-225">Install the [January 2017 anti-malware platform update for Endpoint Protection clients](https://support.microsoft.com/help/3209361/january-2017-anti-malware-platform-update-for-endpoint-protection-clie).</span></span>

- <span data-ttu-id="07ecd-226">[Configure a associação do Serviço de Proteção de Nuvem](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) do cliente SCEP à **configuração** Avançado.</span><span class="sxs-lookup"><span data-stu-id="07ecd-226">[Configure the SCEP client Cloud Protection Service membership](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) to the **Advanced** setting.</span></span>

## <a name="offboard-windows-servers"></a><span data-ttu-id="07ecd-227">Servidores Windows de offboard</span><span class="sxs-lookup"><span data-stu-id="07ecd-227">Offboard Windows servers</span></span>

<span data-ttu-id="07ecd-228">Você pode tirar o windows server (SAC), o Windows Server 2019 e a edição Core do Windows Server 2019 no mesmo método disponível para dispositivos cliente Windows 10.</span><span class="sxs-lookup"><span data-stu-id="07ecd-228">You can offboard Windows Server (SAC), Windows Server 2019, and Windows Server 2019 Core edition in the same method available for Windows 10 client devices.</span></span>

<span data-ttu-id="07ecd-229">Para outras versões do servidor Windows, você tem duas opções para desligar servidores Windows do serviço:</span><span class="sxs-lookup"><span data-stu-id="07ecd-229">For other Windows server versions, you have two options to offboard Windows servers from the service:</span></span>

- <span data-ttu-id="07ecd-230">Desinstalar o agente MMA</span><span class="sxs-lookup"><span data-stu-id="07ecd-230">Uninstall the MMA agent</span></span>
- <span data-ttu-id="07ecd-231">Remover a configuração do espaço de trabalho do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="07ecd-231">Remove the Defender for Endpoint workspace configuration</span></span>

> [!NOTE]
> <span data-ttu-id="07ecd-232">O offboard faz com que o servidor Windows pare de enviar dados do sensor para o portal, mas os dados do servidor Windows, incluindo a referência a todos os alertas que ele teve, serão mantidos por até 6 meses.</span><span class="sxs-lookup"><span data-stu-id="07ecd-232">Offboarding causes the Windows server to stop sending sensor data to the portal but data from the Windows server, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

### <a name="uninstall-windows-servers-by-uninstalling-the-mma-agent"></a><span data-ttu-id="07ecd-233">Desinstalar servidores Windows desinstalando o agente MMA</span><span class="sxs-lookup"><span data-stu-id="07ecd-233">Uninstall Windows servers by uninstalling the MMA agent</span></span>

<span data-ttu-id="07ecd-234">Para desinstalar o servidor Windows, você pode desinstalar o agente MMA do servidor Windows ou desconecta-lo do relatório para o seu espaço de trabalho do Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="07ecd-234">To offboard the Windows server, you can uninstall the MMA agent from the Windows server or detach it from reporting to your Defender for Endpoint workspace.</span></span> <span data-ttu-id="07ecd-235">Depois de desligar o agente, o servidor Windows não enviará mais dados do sensor para o Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="07ecd-235">After offboarding the agent, the Windows server will no longer send sensor data to Defender for Endpoint.</span></span>
<span data-ttu-id="07ecd-236">Para obter mais informações, consulte [Para desabilitar um agente](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span><span class="sxs-lookup"><span data-stu-id="07ecd-236">For more information, see [To disable an agent](https://docs.microsoft.com/azure/log-analytics/log-analytics-windows-agents#to-disable-an-agent).</span></span>

### <a name="remove-the-defender-for-endpoint-workspace-configuration"></a><span data-ttu-id="07ecd-237">Remover a configuração do espaço de trabalho do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="07ecd-237">Remove the Defender for Endpoint workspace configuration</span></span>

<span data-ttu-id="07ecd-238">Para fazer o offboard do servidor Windows, você pode usar um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="07ecd-238">To offboard the Windows server, you can use either of the following methods:</span></span>

- <span data-ttu-id="07ecd-239">Remover a configuração do espaço de trabalho do Defender for Endpoint do agente MMA</span><span class="sxs-lookup"><span data-stu-id="07ecd-239">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>
- <span data-ttu-id="07ecd-240">Execute um comando do PowerShell para remover a configuração</span><span class="sxs-lookup"><span data-stu-id="07ecd-240">Run a PowerShell command to remove the configuration</span></span>

#### <a name="remove-the-defender-for-endpoint-workspace-configuration-from-the-mma-agent"></a><span data-ttu-id="07ecd-241">Remover a configuração do espaço de trabalho do Defender for Endpoint do agente MMA</span><span class="sxs-lookup"><span data-stu-id="07ecd-241">Remove the Defender for Endpoint workspace configuration from the MMA agent</span></span>

1. <span data-ttu-id="07ecd-242">Na guia Propriedades do Agente de Monitoramento **da Microsoft,** selecione a guia Análise de **Log do Azure (OMS).**</span><span class="sxs-lookup"><span data-stu-id="07ecd-242">In the **Microsoft Monitoring Agent Properties**, select the **Azure Log Analytics (OMS)** tab.</span></span>

2. <span data-ttu-id="07ecd-243">Selecione o espaço de trabalho Defender para Ponto de Extremidade e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="07ecd-243">Select the Defender for Endpoint workspace, and click **Remove**.</span></span>

    ![Imagem das propriedades do Agente de Monitoramento da Microsoft](images/atp-mma.png)

#### <a name="run-a-powershell-command-to-remove-the-configuration"></a><span data-ttu-id="07ecd-245">Execute um comando do PowerShell para remover a configuração</span><span class="sxs-lookup"><span data-stu-id="07ecd-245">Run a PowerShell command to remove the configuration</span></span>

1. <span data-ttu-id="07ecd-246">Obter sua ID do Workspace:</span><span class="sxs-lookup"><span data-stu-id="07ecd-246">Get your Workspace ID:</span></span>

   1. <span data-ttu-id="07ecd-247">No painel de navegação, selecione **Configurações**  >  **Integração**.</span><span class="sxs-lookup"><span data-stu-id="07ecd-247">In the navigation pane, select **Settings** > **Onboarding**.</span></span>

   1. <span data-ttu-id="07ecd-248">Selecione **Windows Server 2008 R2 SP1, 2012 R2 e 2016** como o sistema operacional e obter sua ID do Workspace:</span><span class="sxs-lookup"><span data-stu-id="07ecd-248">Select **Windows Server 2008 R2 SP1, 2012 R2 and 2016** as the operating system and get your Workspace ID:</span></span>

      ![Imagem da integração do servidor Windows](images/atp-server-offboarding-workspaceid.png)

2. <span data-ttu-id="07ecd-250&quot;>Abra um PowerShell elevado e execute o seguinte comando.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;07ecd-250&quot;>Open an elevated PowerShell and run the following command.</span></span> <span data-ttu-id=&quot;07ecd-251&quot;>Use a ID do Espaço de Trabalho obtida e substituindo `WorkspaceID` :</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;07ecd-251&quot;>Use the Workspace ID you obtained and replacing `WorkspaceID`:</span></span>

    ```powershell
    $ErrorActionPreference = &quot;SilentlyContinue&quot;
    # Load agent scripting object
    $AgentCfg = New-Object -ComObject AgentConfigManager.MgmtSvcCfg
    # Remove OMS Workspace
    $AgentCfg.RemoveCloudWorkspace(&quot;WorkspaceID")
    # Reload the configuration and apply changes
    $AgentCfg.ReloadConfiguration()

    ```

## <a name="onboarding-servers-with-no-management-solution"></a><span data-ttu-id="07ecd-252">Integrando servidores sem solução de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="07ecd-252">Onboarding Servers with no management solution</span></span>

### <a name="using-group-policy"></a><span data-ttu-id="07ecd-253">Usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="07ecd-253">Using Group Policy</span></span>

<span data-ttu-id="07ecd-254">**Etapa 1: Criar os arquivos necessários para copiar para baixo para os servidores.**</span><span class="sxs-lookup"><span data-stu-id="07ecd-254">**Step-1: Create the necessary files to copy down to the servers.**</span></span>

1. <span data-ttu-id="07ecd-255">Navegue até c:\windows\sysvol\domain\scripts (Pode ser necessário alterar o controle em um dos controladores de domínio).)</span><span class="sxs-lookup"><span data-stu-id="07ecd-255">Navigate to c:\windows\sysvol\domain\scripts (Change control could be needed on one of the domain controllers.)</span></span>
1. <span data-ttu-id="07ecd-256">Crie uma pasta chamada MMA.</span><span class="sxs-lookup"><span data-stu-id="07ecd-256">Create a folder named MMA.</span></span>
1. <span data-ttu-id="07ecd-257">Baixe o seguinte e local na pasta MMA:</span><span class="sxs-lookup"><span data-stu-id="07ecd-257">Download the following and place in the MMA folder:</span></span>

    <span data-ttu-id="07ecd-258">**Atualização para experiência do cliente e telemetria de diagnóstico (Windows Server 2008 R2 e Windows Server 2012 R2)**</span><span class="sxs-lookup"><span data-stu-id="07ecd-258">**Update for customer experience and diagnostic telemetry (Windows Server 2008 R2 and Windows Server 2012 R2)**</span></span>

    [<span data-ttu-id="07ecd-259">Para Windows 2008 R2 x64</span><span class="sxs-lookup"><span data-stu-id="07ecd-259">For Windows 2008 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=1bd1d18d-4631-4d8e-a897-327925765f71)

    [<span data-ttu-id="07ecd-260">Para Windows 2012 R2 x64</span><span class="sxs-lookup"><span data-stu-id="07ecd-260">For Windows 2012 R2 x64</span></span>](https://www.microsoft.com/download/details.aspx?familyid=94cf6d85-017a-4c4c-afca-7d00721b500f)

    > [!NOTE]
    > <span data-ttu-id="07ecd-261">Este artigo pressupo que você está usando servidores baseados em x64 (MMA Agent .exe x64 Nova versão compatível com [SHA-2](https://go.microsoft.com/fwlink/?LinkId=828603))</span><span class="sxs-lookup"><span data-stu-id="07ecd-261">This article assumes you are using x64-based servers (MMA Agent .exe x64 [New SHA-2 compliant version](https://go.microsoft.com/fwlink/?LinkId=828603))</span></span>

<span data-ttu-id="07ecd-262">**Etapa 2: criar um nome de arquivo DeployMMA.cmd (usando o bloco de notas)** Adicione as linhas a seguir ao arquivo cmd.</span><span class="sxs-lookup"><span data-stu-id="07ecd-262">**Step-2: Create a file name DeployMMA.cmd (using notepad)** Add the following lines to the cmd file.</span></span> <span data-ttu-id="07ecd-263">Observe que você precisará da ID do WORKSPACE e da CHAVE.</span><span class="sxs-lookup"><span data-stu-id="07ecd-263">Note that you'll need your WORKSPACE ID and KEY.</span></span>

```dos
@echo off 
cd "C:"
IF EXIST "C:\Program Files\Microsoft Monitoring Agent\Agent\MonitoringHost.exe" ( 
exit
) ELSE (
wusa.exe c:\Windows\MMA\Windows6.1-KB123456-x86.msu /quiet /norestart
wusa.exe c:\Windows\MMA\Windows8.1-KB123456-x86.msu /quiet /norestart
"c:\windows\MMA\MMASetup-AMD64.exe" /C:"setup.exe /qn ADD_OPINSIGHTS_WORKSPACE=1
OPINSIGHTS_WORKSPACE_ID=<your workspace ID>
OPINSIGHTS_WORKSPACE_KEY=<your workspace key>== AcceptEndUserLicenseAgreement=1"
)
```

## <a name="group-policy-configuration"></a><span data-ttu-id="07ecd-264">Configuração da Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="07ecd-264">Group Policy Configuration</span></span>

<span data-ttu-id="07ecd-265">Crie uma nova política de grupo especificamente para a integração de dispositivos como "Microsoft Defender para Integração do Ponto de Extremidade".</span><span class="sxs-lookup"><span data-stu-id="07ecd-265">Create a new group policy specifically for onboarding devices such as “Microsoft Defender for Endpoint Onboarding”.</span></span>

- <span data-ttu-id="07ecd-266">Criar uma Pasta de Política de Grupo chamada "c:\windows\MMA"</span><span class="sxs-lookup"><span data-stu-id="07ecd-266">Create a Group Policy Folder named “c:\windows\MMA”</span></span>

     :::image type="content" source="images/grppolicyconfig1.png" alt-text="folders":::

    <span data-ttu-id="07ecd-268">**Isso adicionará uma nova pasta em cada servidor que obtém o GPO aplicado, chamado MMA, e será armazenado em c:\windows. Isso conterá os arquivos de instalação para o MMA, os pré-requisitos e o script de instalação.**</span><span class="sxs-lookup"><span data-stu-id="07ecd-268">**This will add a new folder on every server that gets the GPO applied, called MMA, and will be stored in c:\windows. This will contain the installation files for the MMA, prerequisites, and install script.**</span></span>

- <span data-ttu-id="07ecd-269">Crie uma preferência de Arquivos de Política de Grupo para cada um dos arquivos armazenados no logon da Net.</span><span class="sxs-lookup"><span data-stu-id="07ecd-269">Create a Group Policy Files preference for each of the files stored in Net logon.</span></span>

     :::image type="content" source="images/grppolicyconfig2.png" alt-text="imagem da política de grupo1":::

<span data-ttu-id="07ecd-271">Ele copia os arquivos de DOMAIN\NETLOGON\MMA\filename para C:\windows\MMA\filename – portanto, os arquivos de instalação são locais para o **servidor**:</span><span class="sxs-lookup"><span data-stu-id="07ecd-271">It copies the files from DOMAIN\NETLOGON\MMA\filename to C:\windows\MMA\filename – **so the installation files are local to the server**:</span></span>

:::image type="content" source="images/deploymma.png" alt-text="implantar cmd mma":::

<span data-ttu-id="07ecd-273">Para os dois KBs (um para Windows Server 2008R2/Windows 7 e o outro para o Windows Server 2012 R2) repetir o processo, mas criar direcionamento de nível de item na guia COMMON, portanto, o arquivo só é copiado para a versão apropriada da plataforma/sistema operacional no escopo:</span><span class="sxs-lookup"><span data-stu-id="07ecd-273">For the two KBs (one for Windows Server 2008R2/Windows 7 and the other for Windows Server 2012 R2) repeat the process but create item level targeting on the COMMON tab, so the file only gets copied to the appropriate platform/Operating system version in scope:</span></span>

:::image type="content" source="images/targeteditor.png" alt-text="editor de destino":::

- <span data-ttu-id="07ecd-275">Para o Windows Server 2008 R2, você precisa (e ele só copiará) Windows6.1-BJ3080149-x64.msu</span><span class="sxs-lookup"><span data-stu-id="07ecd-275">For Windows Server 2008 R2 you need (and it will only copy down) Windows6.1-BJ3080149-x64.msu</span></span>
- <span data-ttu-id="07ecd-276">Para o Windows Server 2012 R2, você precisa (e ele só copiará) Windows8.1-BJ3080149-x64.msu</span><span class="sxs-lookup"><span data-stu-id="07ecd-276">For Windows Server 2012 R2 you need (and it will only copy down) Windows8.1-BJ3080149-x64.msu</span></span>

<span data-ttu-id="07ecd-277">Depois que isso for feito, você precisará criar uma política de script de início:</span><span class="sxs-lookup"><span data-stu-id="07ecd-277">Once this is done, you'll need to create a start-up script policy:</span></span>

:::image type="content" source="images/startupprops.png" alt-text="iniciar propriedades":::

<span data-ttu-id="07ecd-279">O nome do arquivo a ser executado aqui é c:\windows\MMA\DeployMMA.cmd.</span><span class="sxs-lookup"><span data-stu-id="07ecd-279">The name of the file to run here is c:\windows\MMA\DeployMMA.cmd.</span></span>
<span data-ttu-id="07ecd-280">Depois que o servidor for reiniciado como parte do processo de start-up, ele instalará o KB De atualização para experiência do cliente e telemetria de diagnóstico e, em seguida, instalará o Agente MMA, enquanto configura a ID e a Chave do Espaço de Trabalho, e o servidor será integrado.</span><span class="sxs-lookup"><span data-stu-id="07ecd-280">Once the server is restarted as part of the start-up process it will install the Update for customer experience and diagnostic telemetry KB, and then install the MMA Agent, while setting the Workspace ID and Key, and the server will be onboarded.</span></span>

<span data-ttu-id="07ecd-281">Você também pode usar uma **tarefa imediata** para executar o deployMMA.cmd se não quiser reiniciar todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="07ecd-281">You could also use an **immediate task** to run the deployMMA.cmd if you don't want to reboot all the servers.</span></span>
<span data-ttu-id="07ecd-282">Isso pode ser feito em duas fases.</span><span class="sxs-lookup"><span data-stu-id="07ecd-282">This could be done in two phases.</span></span> <span data-ttu-id="07ecd-283">Primeiro crie **os arquivos** e a pasta no GPO – dê tempo ao sistema para garantir que o GPO tenha sido aplicado e todos os servidores tenham os arquivos de instalação.</span><span class="sxs-lookup"><span data-stu-id="07ecd-283">First create **the files and the folder in** GPO – Give the system time to ensure the GPO has been applied, and all the servers have the install files.</span></span> <span data-ttu-id="07ecd-284">Em seguida, adicione a tarefa imediata.</span><span class="sxs-lookup"><span data-stu-id="07ecd-284">Then, add the immediate task.</span></span> <span data-ttu-id="07ecd-285">Isso alcançará o mesmo resultado sem exigir uma reinicialização.</span><span class="sxs-lookup"><span data-stu-id="07ecd-285">This will achieve the same result without requiring a reboot.</span></span>

<span data-ttu-id="07ecd-286">Como o Script tem um método exit e não será executado de novo se o MMA estiver instalado, você também pode usar uma tarefa agendada diariamente para obter o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="07ecd-286">As the Script has an exit method and wont re-run if the MMA is installed, you could also use a daily scheduled task to achieve the same result.</span></span> <span data-ttu-id="07ecd-287">Semelhante a uma política de conformidade do Configuration Manager, ela verificará diariamente para garantir que o MMA está presente.</span><span class="sxs-lookup"><span data-stu-id="07ecd-287">Similar to a Configuration Manager compliance policy it will check daily to ensure the MMA is present.</span></span>

:::image type="content" source="images/schtask.png" alt-text="agendar tarefa":::

:::image type="content" source="images/newtaskprops.png" alt-text="novas propriedades da tarefa":::

:::image type="content" source="images/deploymmadowmload.png" alt-text="implantar adereços de download de mma":::

:::image type="content" source="images/tasksch.png" alt-text="agendador de tarefas":::

<span data-ttu-id="07ecd-292">Conforme mencionado na documentação de integração do Server especificamente em torno do Server 2008 R2, consulte abaixo:</span><span class="sxs-lookup"><span data-stu-id="07ecd-292">As mentioned in the onboarding documentation for Server specifically around Server 2008 R2 please see below:</span></span>

<span data-ttu-id="07ecd-293">Para o Windows Server 2008 R2 PS1, certifique-se de atender aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="07ecd-293">For Windows Server 2008 R2 PS1, ensure that you fulfill the following requirements:</span></span>

- <span data-ttu-id="07ecd-294">Instalar a atualização mensal de fevereiro de [2018](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="07ecd-294">Install the [February 2018 monthly update rollup](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>
  
- <span data-ttu-id="07ecd-295">Instalar o [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (ou posterior) ou [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="07ecd-295">Install either [.NET framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) or [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span></span>

<span data-ttu-id="07ecd-296">Verifique se os KBs estão presentes antes de integração com o Windows Server 2008 R2 Esse processo permite a integração de todos os servidores se você não tiver o Configuration Manager gerenciando servidores.</span><span class="sxs-lookup"><span data-stu-id="07ecd-296">Please check the KBs are present before onboarding Windows Server 2008 R2 This process allows you to onboard all the servers if you don’t have Configuration Manager managing Servers.</span></span>

## <a name="related-topics"></a><span data-ttu-id="07ecd-297">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="07ecd-297">Related topics</span></span>

- [<span data-ttu-id="07ecd-298">Dispositivos integrados do Windows 10</span><span class="sxs-lookup"><span data-stu-id="07ecd-298">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="07ecd-299">Dispositivos Windows não integrados</span><span class="sxs-lookup"><span data-stu-id="07ecd-299">Onboard non-Windows devices</span></span>](configure-endpoints-non-windows.md)
- [<span data-ttu-id="07ecd-300">Definir as configurações de proxy e conectividade com a Internet</span><span class="sxs-lookup"><span data-stu-id="07ecd-300">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="07ecd-301">Executar um teste de detecção em um dispositivo Defender para Ponto de Extremidade recém-integrado</span><span class="sxs-lookup"><span data-stu-id="07ecd-301">Run a detection test on a newly onboarded Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="07ecd-302">Solução de problemas de integração do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="07ecd-302">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
