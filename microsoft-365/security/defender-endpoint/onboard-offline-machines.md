---
title: Dispositivos de integração sem acesso à Internet ao Microsoft Defender para Ponto de Extremidade
ms.reviewer: ''
description: Dispositivos integrados sem acesso à Internet para que eles possam enviar dados do sensor para o sensor do Microsoft Defender para Ponto de Extremidade
keywords: onboard, servers, vm, on-premise, oms gateway, log analytics, azure log analytics, mma
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
ms.openlocfilehash: fb5a9a4d35af2d400cdff1e417727e662738514e
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861342"
---
# <a name="onboard-devices-without-internet-access-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="7687f-104">Dispositivos de integração sem acesso à Internet ao Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="7687f-104">Onboard devices without Internet access to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7687f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="7687f-105">**Applies to:**</span></span>
- [<span data-ttu-id="7687f-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="7687f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7687f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7687f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7687f-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="7687f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7687f-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="7687f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="7687f-110">Para os dispositivos de integração sem acesso à Internet, você precisará seguir as seguintes etapas gerais:</span><span class="sxs-lookup"><span data-stu-id="7687f-110">To onboard devices without Internet access, you'll need to take the following general steps:</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="7687f-111">As etapas a seguir são aplicáveis apenas a dispositivos que executam versões anteriores do Windows, como: Windows Server 2016 e anterior ou Windows 8.1 e anteriores.</span><span class="sxs-lookup"><span data-stu-id="7687f-111">The steps below are applicable only to devices running previous versions of Windows such as: Windows Server 2016 and earlier or Windows 8.1 and earlier.</span></span>

> [!NOTE]
> - <span data-ttu-id="7687f-112">Um servidor de gateway OMS não pode ser usado como proxy para dispositivos Windows 10 ou Windows Server 2019 desconectados quando configurado por meio do Registro ou GPO "TelemetryProxyServer".</span><span class="sxs-lookup"><span data-stu-id="7687f-112">An OMS gateway server cannot be used as proxy for disconnected Windows 10 or Windows Server 2019 devices when configured via 'TelemetryProxyServer' registry or GPO.</span></span>
> - <span data-ttu-id="7687f-113">Para Windows 10 ou Windows Server 2019 - embora você possa usar TelemetryProxyServer, ele deve apontar para um dispositivo ou dispositivo proxy padrão.</span><span class="sxs-lookup"><span data-stu-id="7687f-113">For Windows 10 or Windows Server 2019 - while you may use TelemetryProxyServer, it must point to a standard proxy device or appliance.</span></span>
> - <span data-ttu-id="7687f-114">Além disso, o Windows 10 ou o Windows Server 2019 em ambientes desconectados devem ser capazes de atualizar listas de confiança de certificado offline por meio de um arquivo interno ou servidor Web.</span><span class="sxs-lookup"><span data-stu-id="7687f-114">In addition, Windows 10 or Windows Server 2019 in disconnected environments must be able to update Certificate Trust Lists offline via an internal file or web server.</span></span>
> - <span data-ttu-id="7687f-115">Para obter mais informações sobre como atualizar CTLs offline, consulte [Configure a file or web server to download the CTL files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).</span><span class="sxs-lookup"><span data-stu-id="7687f-115">For more information about updating CTLs offline, see [Configure a file or web server to download the CTL files](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn265983(v=ws.11)#configure-a-file-or-web-server-to-download-the-ctl-files).</span></span>

<span data-ttu-id="7687f-116">Para obter mais informações sobre métodos de integração, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="7687f-116">For more information about onboarding methods, see the following articles:</span></span>
- [<span data-ttu-id="7687f-117">Versões anteriores integradas do Windows</span><span class="sxs-lookup"><span data-stu-id="7687f-117">Onboard previous versions of Windows</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel)
- [<span data-ttu-id="7687f-118">Servidores de integração para o serviço do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="7687f-118">Onboard servers to the Microsoft Defender for Endpoint service</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#windows-server-2008-r2-sp1--windows-server-2012-r2-and-windows-server-2016)
- [<span data-ttu-id="7687f-119">Configurar configurações de proxy de dispositivo e conectividade com a Internet</span><span class="sxs-lookup"><span data-stu-id="7687f-119">Configure device proxy and Internet connectivity settings</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#configure-the-proxy-server-manually-using-a-registry-based-static-proxy)

## <a name="on-premise-devices"></a><span data-ttu-id="7687f-120">Dispositivos locais</span><span class="sxs-lookup"><span data-stu-id="7687f-120">On-premise devices</span></span>

- <span data-ttu-id="7687f-121">Configurar o Azure Log Analytics (anteriormente conhecido como Gateway OMS) para atuar como proxy ou hub:</span><span class="sxs-lookup"><span data-stu-id="7687f-121">Setup Azure Log Analytics (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
  - [<span data-ttu-id="7687f-122">Agente de Análise de Log do Azure</span><span class="sxs-lookup"><span data-stu-id="7687f-122">Azure Log Analytics Agent</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
  - <span data-ttu-id="7687f-123">[Instalar e configurar o Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) aponte para o Defender for Endpoint Workspace key & ID</span><span class="sxs-lookup"><span data-stu-id="7687f-123">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>

- <span data-ttu-id="7687f-124">Dispositivos offline na mesma rede do Azure Log Analytics</span><span class="sxs-lookup"><span data-stu-id="7687f-124">Offline devices in the same network of Azure Log Analytics</span></span>
  -  <span data-ttu-id="7687f-125">Configurar o MMA para apontar para:</span><span class="sxs-lookup"><span data-stu-id="7687f-125">Configure MMA to point to:</span></span>
     - <span data-ttu-id="7687f-126">IP do Azure Log Analytics como proxy</span><span class="sxs-lookup"><span data-stu-id="7687f-126">Azure Log Analytics IP as a proxy</span></span>
     - <span data-ttu-id="7687f-127">Chave de espaço de trabalho do Defender para Ponto de Extremidade & ID</span><span class="sxs-lookup"><span data-stu-id="7687f-127">Defender for Endpoint workspace key & ID</span></span>

## <a name="azure-virtual-machines"></a><span data-ttu-id="7687f-128">Máquinas virtuais do Azure</span><span class="sxs-lookup"><span data-stu-id="7687f-128">Azure virtual machines</span></span>
- <span data-ttu-id="7687f-129">Configurar e habilitar o espaço de trabalho [do Azure Log Analytics](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)</span><span class="sxs-lookup"><span data-stu-id="7687f-129">Configure and enable [Azure Log Analytics workspace](https://docs.microsoft.com/azure/azure-monitor/platform/gateway)</span></span>

    - <span data-ttu-id="7687f-130">Configurar o Gateway de Análise de Log do Azure (anteriormente conhecido como Gateway OMS) para atuar como proxy ou hub:</span><span class="sxs-lookup"><span data-stu-id="7687f-130">Setup Azure Log Analytics Gateway (formerly known as OMS Gateway) to act as proxy or hub:</span></span>
      - [<span data-ttu-id="7687f-131">Gateway de Análise de Log do Azure</span><span class="sxs-lookup"><span data-stu-id="7687f-131">Azure Log Analytics Gateway</span></span>](https://docs.microsoft.com/azure/azure-monitor/platform/gateway#download-the-log-analytics-gateway)
      - <span data-ttu-id="7687f-132">[Instalar e configurar o Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) aponte para o Defender for Endpoint Workspace key & ID</span><span class="sxs-lookup"><span data-stu-id="7687f-132">[Install and configure Microsoft Monitoring Agent (MMA)](configure-server-endpoints.md#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-for-endpoint) point to Defender for Endpoint Workspace key & ID</span></span>
    - <span data-ttu-id="7687f-133">VMs offline do Azure na mesma rede do Gateway OMS</span><span class="sxs-lookup"><span data-stu-id="7687f-133">Offline Azure VMs in the same network of OMS Gateway</span></span>
      - <span data-ttu-id="7687f-134">Configurar o IP do Azure Log Analytics como proxy</span><span class="sxs-lookup"><span data-stu-id="7687f-134">Configure Azure Log Analytics IP as a proxy</span></span>
      - <span data-ttu-id="7687f-135">Chave de Espaço de Trabalho do Azure Log Analytics & ID</span><span class="sxs-lookup"><span data-stu-id="7687f-135">Azure Log Analytics Workspace Key & ID</span></span>

    - <span data-ttu-id="7687f-136">Centro de Segurança do Azure (ASC)</span><span class="sxs-lookup"><span data-stu-id="7687f-136">Azure Security Center (ASC)</span></span>
      - [<span data-ttu-id="7687f-137">Espaço de Trabalho \> de Análise de Log de Política de Segurança</span><span class="sxs-lookup"><span data-stu-id="7687f-137">Security Policy \> Log Analytics Workspace</span></span>](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)
      - [<span data-ttu-id="7687f-138">Detecção de \> ameaças Permitir que o Defender para o Ponto de Extremidade acesse meus dados</span><span class="sxs-lookup"><span data-stu-id="7687f-138">Threat Detection \> Allow Defender for Endpoint to access my data</span></span>](https://docs.microsoft.com/azure/security-center/security-center-wdatp#enable-windows-defender-atp-integration)

        <span data-ttu-id="7687f-139">Para obter mais informações, consulte [Trabalhando com políticas de segurança](https://docs.microsoft.com/azure/security-center/tutorial-security-policy).</span><span class="sxs-lookup"><span data-stu-id="7687f-139">For more information, see [Working with security policies](https://docs.microsoft.com/azure/security-center/tutorial-security-policy).</span></span>
