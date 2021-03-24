---
title: Corrigir sensores não salubres no Microsoft Defender para Ponto de Extremidade
description: Correção de sensores de dispositivo que estão relatando como mal configurados ou inativos para que o serviço receba dados do dispositivo.
keywords: misconfigured, inactive, fix sensor, sensor health, no sensor data, sensor data, sensor data, comunicações prejudicadas, comunicação
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
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: a24dc4ef23d32b19de9d2871b7d87aae90d05828
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053769"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="6622f-104">Corrigir sensores não salubres no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6622f-104">Fix unhealthy sensors in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6622f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6622f-105">**Applies to:**</span></span>
- [<span data-ttu-id="6622f-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6622f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6622f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6622f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="6622f-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="6622f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6622f-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="6622f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

<span data-ttu-id="6622f-110">Dispositivos categorizados como mal configurados ou inativos podem ser sinalizados devido a causas variáveis.</span><span class="sxs-lookup"><span data-stu-id="6622f-110">Devices that are categorized as misconfigured or inactive can be flagged due to varying causes.</span></span> <span data-ttu-id="6622f-111">Esta seção fornece algumas explicações sobre o que pode ter causado a categorização de um dispositivo como inativo ou mal configurado.</span><span class="sxs-lookup"><span data-stu-id="6622f-111">This section provides some explanations as to what might have caused a device to be categorized as inactive or misconfigured.</span></span>

## <a name="inactive-devices"></a><span data-ttu-id="6622f-112">Dispositivos inativos</span><span class="sxs-lookup"><span data-stu-id="6622f-112">Inactive devices</span></span>

<span data-ttu-id="6622f-113">Um dispositivo inativo não é necessariamente sinalizado devido a um problema.</span><span class="sxs-lookup"><span data-stu-id="6622f-113">An inactive device is not necessarily flagged due to an issue.</span></span> <span data-ttu-id="6622f-114">As seguintes ações tomadas em um dispositivo podem fazer com que um dispositivo seja categorizado como inativo:</span><span class="sxs-lookup"><span data-stu-id="6622f-114">The following actions taken on a device can cause a device to be categorized as inactive:</span></span>

### <a name="device-is-not-in-use"></a><span data-ttu-id="6622f-115">O dispositivo não está em uso</span><span class="sxs-lookup"><span data-stu-id="6622f-115">Device is not in use</span></span>

<span data-ttu-id="6622f-116">Se o dispositivo não estiver em uso por mais de sete dias por qualquer motivo, ele permanecerá em um status 'Inativo' no portal.</span><span class="sxs-lookup"><span data-stu-id="6622f-116">If the device has not been in use for more than seven days for any reason, it will remain in an ‘Inactive’ status in the portal.</span></span>

### <a name="device-was-reinstalled-or-renamed"></a><span data-ttu-id="6622f-117">O dispositivo foi reinstalado ou renomeado</span><span class="sxs-lookup"><span data-stu-id="6622f-117">Device was reinstalled or renamed</span></span>
<span data-ttu-id="6622f-118">Um dispositivo reinstalado ou renomeado gerará uma nova entidade de dispositivo no Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="6622f-118">A reinstalled or renamed device will generate a new device entity in Microsoft Defender Security Center.</span></span> <span data-ttu-id="6622f-119">A entidade de dispositivo anterior permanecerá com um status 'Inativo' no portal.</span><span class="sxs-lookup"><span data-stu-id="6622f-119">The previous device entity will remain with an ‘Inactive’ status in the portal.</span></span> <span data-ttu-id="6622f-120">Se você reinstalou um dispositivo e implantou o pacote do Defender for Endpoint, procure o novo nome do dispositivo para verificar se o dispositivo está relatando normalmente.</span><span class="sxs-lookup"><span data-stu-id="6622f-120">If you reinstalled a device and deployed the Defender for Endpoint package, search for the new device name to verify that the device is reporting normally.</span></span>

### <a name="device-was-offboarded"></a><span data-ttu-id="6622f-121">O dispositivo foi desligado</span><span class="sxs-lookup"><span data-stu-id="6622f-121">Device was offboarded</span></span>
<span data-ttu-id="6622f-122">Se o dispositivo foi desligado, ele ainda aparecerá na lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="6622f-122">If the device was offboarded, it will still appear in devices list.</span></span> <span data-ttu-id="6622f-123">Após sete dias, o estado de saúde do dispositivo deve mudar para inativo.</span><span class="sxs-lookup"><span data-stu-id="6622f-123">After seven days, the device health state should change to inactive.</span></span>

### <a name="device-is-not-sending-signals"></a><span data-ttu-id="6622f-124">O dispositivo não está enviando sinais</span><span class="sxs-lookup"><span data-stu-id="6622f-124">Device is not sending signals</span></span>
<span data-ttu-id="6622f-125">Se o dispositivo não estiver enviando sinais por mais de sete dias para qualquer um dos canais do Microsoft Defender para Ponto de Extremidade por qualquer motivo, incluindo condições que se enquadram na classificação de dispositivos mal configurados, um dispositivo pode ser considerado inativo.</span><span class="sxs-lookup"><span data-stu-id="6622f-125">If the device is not sending any signals for more than seven days to any of the Microsoft Defender for Endpoint channels for any reason including conditions that fall under misconfigured devices classification, a device can be considered inactive.</span></span> 

<span data-ttu-id="6622f-126">Você espera que um dispositivo está no status 'Ativo'?</span><span class="sxs-lookup"><span data-stu-id="6622f-126">Do you expect a device to be in ‘Active’ status?</span></span> <span data-ttu-id="6622f-127">[Abra um tíquete de suporte](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).</span><span class="sxs-lookup"><span data-stu-id="6622f-127">[Open a support ticket](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).</span></span>

## <a name="misconfigured-devices"></a><span data-ttu-id="6622f-128">Dispositivos mal configurados</span><span class="sxs-lookup"><span data-stu-id="6622f-128">Misconfigured devices</span></span>
<span data-ttu-id="6622f-129">Dispositivos mal configurados ainda podem ser classificados para:</span><span class="sxs-lookup"><span data-stu-id="6622f-129">Misconfigured devices can further be classified to:</span></span>
- <span data-ttu-id="6622f-130">Comunicações prejudicadas</span><span class="sxs-lookup"><span data-stu-id="6622f-130">Impaired communications</span></span>
- <span data-ttu-id="6622f-131">Sem dados do sensor</span><span class="sxs-lookup"><span data-stu-id="6622f-131">No sensor data</span></span>

### <a name="impaired-communications"></a><span data-ttu-id="6622f-132">Comunicações prejudicadas</span><span class="sxs-lookup"><span data-stu-id="6622f-132">Impaired communications</span></span>
<span data-ttu-id="6622f-133">Esse status indica que há comunicação limitada entre o dispositivo e o serviço.</span><span class="sxs-lookup"><span data-stu-id="6622f-133">This status indicates that there's limited communication between the device and the service.</span></span>

<span data-ttu-id="6622f-134">As seguintes ações sugeridas podem ajudar a corrigir problemas relacionados a um dispositivo mal configurado com comunicações prejudicadas:</span><span class="sxs-lookup"><span data-stu-id="6622f-134">The following suggested actions can help fix issues related to a misconfigured device with impaired communications:</span></span>

- [<span data-ttu-id="6622f-135">Verifique se o dispositivo tem conexão com a Internet</span><span class="sxs-lookup"><span data-stu-id="6622f-135">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="6622f-136">O sensor Windows Defender ATP exige que o Microsoft Windows HTTP (WinHTTP) reporte dados do sensor e se comunique com o serviço Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="6622f-136">The Window Defender ATP sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="6622f-137">Verificar a conectividade do cliente com o Microsoft Defender para URLs de serviço de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="6622f-137">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls)</br>
  <span data-ttu-id="6622f-138">Verifique se a configuração de proxy foi concluída com êxito, se o WinHTTP pode descobrir e se comunicar por meio do servidor proxy em seu ambiente e se o servidor proxy permite o tráfego para as URLs de serviço do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="6622f-138">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

<span data-ttu-id="6622f-139">Se você tiver ações corretivas e o status do dispositivo ainda estiver configurado incorretamente, [abra um tíquete de suporte](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="6622f-139">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

### <a name="no-sensor-data"></a><span data-ttu-id="6622f-140">Sem dados do sensor</span><span class="sxs-lookup"><span data-stu-id="6622f-140">No sensor data</span></span>
<span data-ttu-id="6622f-141">Um dispositivo mal configurado com o status 'Sem dados do sensor' tem comunicação com o serviço, mas só pode relatar dados parciais do sensor.</span><span class="sxs-lookup"><span data-stu-id="6622f-141">A misconfigured device with status ‘No sensor data’ has communication with the service but can only report partial sensor data.</span></span>
<span data-ttu-id="6622f-142">Siga estas ações para corrigir problemas conhecidos relacionados a um dispositivo mal configurado com o status 'Sem dados do sensor':</span><span class="sxs-lookup"><span data-stu-id="6622f-142">Follow theses actions to correct known issues related to a misconfigured device with status ‘No sensor data’:</span></span>

- [<span data-ttu-id="6622f-143">Verifique se o dispositivo tem conexão com a Internet</span><span class="sxs-lookup"><span data-stu-id="6622f-143">Ensure the device has Internet connection</span></span>](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  <span data-ttu-id="6622f-144">O sensor Windows Defender ATP exige que o Microsoft Windows HTTP (WinHTTP) reporte dados do sensor e se comunique com o serviço Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="6622f-144">The Window Defender ATP sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

- [<span data-ttu-id="6622f-145">Verificar a conectividade do cliente com o Microsoft Defender para URLs de serviço de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="6622f-145">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls)</br>
  <span data-ttu-id="6622f-146">Verifique se a configuração de proxy foi concluída com êxito, se o WinHTTP pode descobrir e se comunicar por meio do servidor proxy em seu ambiente e se o servidor proxy permite o tráfego para as URLs de serviço do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="6622f-146">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Microsoft Defender for Endpoint service URLs.</span></span>

- [<span data-ttu-id="6622f-147">Verifique se o serviço de dados de diagnóstico está habilitado</span><span class="sxs-lookup"><span data-stu-id="6622f-147">Ensure the diagnostic data service is enabled</span></span>](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
<span data-ttu-id="6622f-148">Se os dispositivos não estão relatando corretamente, talvez seja necessário verificar se o serviço de dados de diagnóstico do Windows 10 está definido para iniciar automaticamente e está sendo executado no ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="6622f-148">If the devices aren't reporting correctly, you might need to check that the Windows 10 diagnostic data service is set to automatically start and is running on the endpoint.</span></span>

- [<span data-ttu-id="6622f-149">Verifique se o Microsoft Defender Antivírus não está desabilitado por política</span><span class="sxs-lookup"><span data-stu-id="6622f-149">Ensure that Microsoft Defender Antivirus is not disabled by policy</span></span>](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
<span data-ttu-id="6622f-150">Se seus dispositivos estão executando um cliente antimalware de terceiros, o agente defender para ponto de extremidade precisa do driver antimalware de início antecipado do Microsoft Defender Antivírus (ELAM) para ser habilitado.</span><span class="sxs-lookup"><span data-stu-id="6622f-150">If your devices are running a third-party antimalware client, the Defender for Endpoint agent needs the Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver to be enabled.</span></span>

<span data-ttu-id="6622f-151">Se você tiver ações corretivas e o status do dispositivo ainda estiver configurado incorretamente, [abra um tíquete de suporte](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="6622f-151">If you took corrective actions and the device status is still misconfigured, [open a support ticket](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409).</span></span>

## <a name="see-also"></a><span data-ttu-id="6622f-152">Confira também</span><span class="sxs-lookup"><span data-stu-id="6622f-152">See also</span></span>
- [<span data-ttu-id="6622f-153">Verificar o estado de saúde do sensor no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6622f-153">Check sensor health state in Microsoft Defender for Endpoint</span></span>](check-sensor-status.md)
