---
title: Revisar eventos e erros usando o Visualizador de Eventos
description: Obter descrições e etapas adicionais de solução de problemas (se necessário) para todos os eventos relatados pelo serviço do Microsoft Defender para Ponto de Extremidade.
keywords: troubleshoot, event viewer, log summary, failure code, failed, Microsoft Defender for Endpoint service, can't start, broken, can't start
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
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: a8b7268e89470a85a34015967b69abb1818fe64f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933836"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="e5b5b-104">Revisar eventos e erros usando o Visualizador de Eventos</span><span class="sxs-lookup"><span data-stu-id="e5b5b-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e5b5b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e5b5b-105">**Applies to:**</span></span>
- <span data-ttu-id="e5b5b-106">Visualizador de eventos</span><span class="sxs-lookup"><span data-stu-id="e5b5b-106">Event Viewer</span></span>
- [<span data-ttu-id="e5b5b-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e5b5b-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="e5b5b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5b5b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e5b5b-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="e5b5b-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e5b5b-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="e5b5b-111">Você pode revisar as IDs de eventos no [Visualizador de](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) Eventos em dispositivos individuais.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="e5b5b-112">Por exemplo, se os dispositivos não aparecerem na lista **Dispositivos,** talvez seja necessário procurar IDs de eventos nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-112">For example, if devices aren't appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="e5b5b-113">Em seguida, você pode usar essa tabela para determinar outras etapas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="e5b5b-114">**Abra o Visualizador de Eventos e encontre o log de eventos de serviço do Microsoft Defender for Endpoint:**</span><span class="sxs-lookup"><span data-stu-id="e5b5b-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="e5b5b-115">Clique **em** Iniciar no menu Windows, digite **Visualizador de** Eventos e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="e5b5b-116">Na lista de log, em **Resumo de Log,** role até ver **Microsoft-Windows-SENSE/Operational**.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="e5b5b-117">Clique duas vezes no item para abrir o log.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="e5b5b-118">a.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-118">a.</span></span>  <span data-ttu-id="e5b5b-119">Você também pode acessar o log expandindo Os Logs **de** Aplicativos e Serviços da  >  **Microsoft**  >  **Windows**  >  **SENSE** e clique em **Operacional**.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e5b5b-120">SENSE é o nome interno usado para se referir ao sensor comportamental que alimenta o Microsoft Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="e5b5b-121">Os eventos gravados pelo serviço serão exibidos no log.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="e5b5b-122">Consulte a tabela a seguir para ver uma lista de eventos gravados pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="e5b5b-123">ID do evento</span><span class="sxs-lookup"><span data-stu-id="e5b5b-123">Event ID</span></span></th>
<th><span data-ttu-id="e5b5b-124">Mensagem</span><span class="sxs-lookup"><span data-stu-id="e5b5b-124">Message</span></span></th>
<th><span data-ttu-id="e5b5b-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="e5b5b-125">Description</span></span></th>
<th><span data-ttu-id="e5b5b-126">Action</span><span class="sxs-lookup"><span data-stu-id="e5b5b-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-127">1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-127">1</span></span></td>
<td><span data-ttu-id="e5b5b-128">Microsoft Defender for Endpoint service started (Version <code>variable</code> ).</span><span class="sxs-lookup"><span data-stu-id="e5b5b-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="e5b5b-129">Ocorre durante a inicialização do sistema, o desligar e durante a integração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-129">Occurs during system startup, shut down, and during onboarding.</span></span></td>
<td><span data-ttu-id="e5b5b-130">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-131">2</span><span class="sxs-lookup"><span data-stu-id="e5b5b-131">2</span></span></td>
<td><span data-ttu-id="e5b5b-132">Desligamento do serviço do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="e5b5b-133">Ocorre quando o dispositivo é desligado ou desligado.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="e5b5b-134">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-135">3</span><span class="sxs-lookup"><span data-stu-id="e5b5b-135">3</span></span></td>
<td><span data-ttu-id="e5b5b-136">Falha ao iniciar o serviço do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="e5b5b-137">Código de falha: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-138">O serviço não começou.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-138">Service didn't start.</span></span></td>
<td><span data-ttu-id="e5b5b-139">Revise outras mensagens para determinar possíveis causas e etapas de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-140">4 </span><span class="sxs-lookup"><span data-stu-id="e5b5b-140">4</span></span></td>
<td><span data-ttu-id="e5b5b-141">O serviço do Microsoft Defender para Ponto de Extremidade entrou em contato com o servidor em <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-142">Variável = URL dos servidores de processamento do Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="e5b5b-143">Essa URL corresponderá às vistas na atividade firewall ou de rede.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="e5b5b-144">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-145">5 </span><span class="sxs-lookup"><span data-stu-id="e5b5b-145">5</span></span></td>
<td><span data-ttu-id="e5b5b-146">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao se conectar ao servidor em <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-147">Variável = URL dos servidores de processamento do Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="e5b5b-148">O serviço não pôde entrar em contato com os servidores de processamento externos nessa URL.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-148">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="e5b5b-149">Verifique a conexão com a URL.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-149">Check the connection to the URL.</span></span> <span data-ttu-id="e5b5b-150">Consulte <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-151">6 </span><span class="sxs-lookup"><span data-stu-id="e5b5b-151">6</span></span></td>
<td><span data-ttu-id="e5b5b-152">O serviço do Microsoft Defender para Ponto de Extremidade não está integrado e nenhum parâmetro de integração foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="e5b5b-153">O dispositivo não entrou corretamente e não estará relatando para o portal.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-153">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="e5b5b-154">A integração deve ser executado antes de iniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="e5b5b-155">Verifique se as configurações e scripts de integração foram implantados corretamente.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e5b5b-156">Tente reimplantar os pacotes de configuração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e5b5b-157">Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-158">7 </span><span class="sxs-lookup"><span data-stu-id="e5b5b-158">7</span></span></td>
<td><span data-ttu-id="e5b5b-159">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao ler os parâmetros de integração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="e5b5b-160">Falha: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-161">Variável = descrição de erro detalhada.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-161">Variable = detailed error description.</span></span> <span data-ttu-id="e5b5b-162">O dispositivo não entrou corretamente e não estará relatando para o portal.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-162">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="e5b5b-163">Verifique se as configurações e scripts de integração foram implantados corretamente.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e5b5b-164">Tente reimplantar os pacotes de configuração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e5b5b-165">Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-166">8 </span><span class="sxs-lookup"><span data-stu-id="e5b5b-166">8</span></span></td>
<td><span data-ttu-id="e5b5b-167">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao limpar sua configuração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="e5b5b-168">Código de falha: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-169"><b>Durante a integração:</b> O serviço falhou ao limpar sua configuração durante a integração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="e5b5b-170">O processo de integração continua.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="e5b5b-171"><b>Durante o offboard:</b> O serviço falhou ao limpar sua configuração durante o offboard.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="e5b5b-172">O processo de offboarding foi concluído, mas o serviço continua em execução.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="e5b5b-173"><b>Integração:</b> Nenhuma ação é necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="e5b5b-174"><b>Offboarding:</b> Reinicie o sistema.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="e5b5b-175">Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-176">9 </span><span class="sxs-lookup"><span data-stu-id="e5b5b-176">9</span></span></td>
<td><span data-ttu-id="e5b5b-177">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao alterar seu tipo de início.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="e5b5b-178">Código de falha: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-179"><b>Durante a integração:</b> O dispositivo não entrou corretamente e não estará relatando para o portal.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-179"><b>During onboarding:</b> The device didn't onboard correctly and won't be reporting to the portal.</span></span> <br><br><span data-ttu-id="e5b5b-180"><b>Durante o offboard:</b> Falha ao alterar o tipo de início do serviço.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="e5b5b-181">O processo de offboarding continua.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="e5b5b-182">Verifique se as configurações e scripts de integração foram implantados corretamente.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e5b5b-183">Tente reimplantar os pacotes de configuração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e5b5b-184">Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-185">10 </span><span class="sxs-lookup"><span data-stu-id="e5b5b-185">10</span></span></td>
<td><span data-ttu-id="e5b5b-186">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao manter as informações de integração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="e5b5b-187">Código de falha: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-188">O dispositivo não entrou corretamente e não estará relatando para o portal.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-188">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="e5b5b-189">Verifique se as configurações e scripts de integração foram implantados corretamente.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e5b5b-190">Tente reimplantar os pacotes de configuração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e5b5b-191">Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-192">11</span><span class="sxs-lookup"><span data-stu-id="e5b5b-192">11</span></span></td>
<td><span data-ttu-id="e5b5b-193">Integração ou rea integração do serviço do Defender for Endpoint concluída.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="e5b5b-194">O dispositivo foi corretamente conectado.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="e5b5b-195">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="e5b5b-196">Pode levar várias horas para que o dispositivo apareça no portal.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-197">12 </span><span class="sxs-lookup"><span data-stu-id="e5b5b-197">12</span></span></td>
<td><span data-ttu-id="e5b5b-198">O Microsoft Defender para Ponto de Extremidade falhou ao aplicar a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="e5b5b-199">O serviço não pôde aplicar a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="e5b5b-200">Esse erro deve ser resolvido após um curto período de tempo.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-201">13</span><span class="sxs-lookup"><span data-stu-id="e5b5b-201">13</span></span></td>
<td><span data-ttu-id="e5b5b-202">A ID do dispositivo Do Microsoft Defender para Ponto de Extremidade foi calculada: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-203">Processo operacional normal.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="e5b5b-204">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-205">15</span><span class="sxs-lookup"><span data-stu-id="e5b5b-205">15</span></span></td>
<td><span data-ttu-id="e5b5b-206">O Microsoft Defender para Ponto de Extremidade não pode iniciar o canal de comando com URL: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-207">Variável = URL dos servidores de processamento do Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="e5b5b-208">O serviço não pôde entrar em contato com os servidores de processamento externos nessa URL.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-208">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="e5b5b-209">Verifique a conexão com a URL.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-209">Check the connection to the URL.</span></span> <span data-ttu-id="e5b5b-210">Consulte <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-211">17 </span><span class="sxs-lookup"><span data-stu-id="e5b5b-211">17</span></span></td>
<td><span data-ttu-id="e5b5b-212">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao alterar o local do serviço Experiências do Usuário Conectado e Telemetria.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="e5b5b-213">Código de falha: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-214">Ocorreu um erro com o serviço Windows telemetria.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="e5b5b-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Verifique se o serviço de dados de diagnóstico está habilitado</a>.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="e5b5b-216">Verifique se as configurações e scripts de integração foram implantados corretamente.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e5b5b-217">Tente reimplantar os pacotes de configuração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e5b5b-218">Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-219">18 </span><span class="sxs-lookup"><span data-stu-id="e5b5b-219">18</span></span></td>
<td><span data-ttu-id="e5b5b-220">OOBE (Windows Bem-vindo) é concluído.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="e5b5b-221">O serviço só será a partir Windows as atualizações terminarem de instalar.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="e5b5b-222">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-223">19</span><span class="sxs-lookup"><span data-stu-id="e5b5b-223">19</span></span></td>
<td><span data-ttu-id="e5b5b-224">OOBE (Windows Bem-vindo) ainda não foi concluído.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="e5b5b-225">O serviço só será a partir Windows as atualizações terminarem de instalar.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="e5b5b-226">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="e5b5b-227">Se esse erro persistir após uma reinicialização do sistema, certifique-se de que todas as Windows atualizações tenham sido instaladas.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-228">20</span><span class="sxs-lookup"><span data-stu-id="e5b5b-228">20</span></span></td>
<td><span data-ttu-id="e5b5b-229">Não é possível aguardar a conclusão do OOBE (Windows Bem-vindo).</span><span class="sxs-lookup"><span data-stu-id="e5b5b-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="e5b5b-230">Código de falha: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-231">Erro interno.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-231">Internal error.</span></span></td>
<td><span data-ttu-id="e5b5b-232">Se esse erro persistir após uma reinicialização do sistema, certifique-se de que todas as Windows atualizações tenham sido instaladas.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-233">25</span><span class="sxs-lookup"><span data-stu-id="e5b5b-233">25</span></span></td>
<td><span data-ttu-id="e5b5b-234">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao redefinir o status de saúde no Registro.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="e5b5b-235">Código de falha: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-236">O dispositivo não foi a bordo corretamente.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-236">The device didn't onboard correctly.</span></span>
<span data-ttu-id="e5b5b-237">Ele informará ao portal, no entanto, o serviço pode não aparecer como registrado no SCCM ou no Registro.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="e5b5b-238">Verifique se as configurações e scripts de integração foram implantados corretamente.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e5b5b-239">Tente reimplantar os pacotes de configuração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e5b5b-240">Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-241">26</span><span class="sxs-lookup"><span data-stu-id="e5b5b-241">26</span></span></td>
<td><span data-ttu-id="e5b5b-242">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao definir o status de integração no Registro.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="e5b5b-243">Código de falha: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-244">O dispositivo não foi a bordo corretamente.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-244">The device didn't onboard correctly.</span></span><br>
<span data-ttu-id="e5b5b-245">Ele informará ao portal, no entanto, o serviço pode não aparecer como registrado no SCCM ou no Registro.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="e5b5b-246">Verifique se as configurações e scripts de integração foram implantados corretamente.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e5b5b-247">Tente reimplantar os pacotes de configuração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e5b5b-248">Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-249">27</span><span class="sxs-lookup"><span data-stu-id="e5b5b-249">27</span></span></td>
<td><span data-ttu-id="e5b5b-250">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao habilitar o modo de conhecimento SENSE Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="e5b5b-251">Falha no processo de integração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-251">Onboarding process failed.</span></span> <span data-ttu-id="e5b5b-252">Código de falha: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-253">Normalmente, Microsoft Defender Antivírus um estado passivo especial se outro produto antimalware em tempo real estiver sendo executado corretamente no dispositivo e o dispositivo estiver relatando para o Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="e5b5b-254">Verifique se as configurações e scripts de integração foram implantados corretamente.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e5b5b-255">Tente reimplantar os pacotes de configuração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e5b5b-256">Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="e5b5b-257">Verifique se a proteção antimalware em tempo real está sendo executado corretamente.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-258">28</span><span class="sxs-lookup"><span data-stu-id="e5b5b-258">28</span></span></td>
<td><span data-ttu-id="e5b5b-259">Falha no registro do serviço de Telemetria e experiências de usuário conectados do Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="e5b5b-260">Código de falha: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-261">Ocorreu um erro com o serviço Windows telemetria.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="e5b5b-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Verifique se o serviço de dados de diagnóstico está habilitado</a>.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="e5b5b-263">Verifique se as configurações e scripts de integração foram implantados corretamente.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e5b5b-264">Tente reimplantar os pacotes de configuração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e5b5b-265">Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-266">29</span><span class="sxs-lookup"><span data-stu-id="e5b5b-266">29</span></span></td>
<td><span data-ttu-id="e5b5b-267">Falha ao ler os parâmetros de offboarding.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="e5b5b-268">Tipo de erro: %1, Código de erro: %2, Descrição: %3</span><span class="sxs-lookup"><span data-stu-id="e5b5b-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="e5b5b-269">Esse evento ocorre quando o sistema não&#39;ler os parâmetros de offboarding.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="e5b5b-270">Verifique se o dispositivo tem acesso à Internet e execute todo o processo de offboard novamente.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="e5b5b-271">Verifique se o pacote de offboarding não expirou.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-271">Ensure the offboarding package hasn't expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-272">30</span><span class="sxs-lookup"><span data-stu-id="e5b5b-272">30</span></span></td>
<td><span data-ttu-id="e5b5b-273">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao desabilitar o modo de conhecimento SENSE Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="e5b5b-274">Código de falha: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-275">Normalmente, Microsoft Defender Antivírus um estado passivo especial se outro produto antimalware em tempo real estiver sendo executado corretamente no dispositivo e o dispositivo estiver relatando para o Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="e5b5b-276">Verifique se as configurações e scripts de integração foram implantados corretamente.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e5b5b-277">Tente reimplantar os pacotes de configuração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e5b5b-278">Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span><span class="sxs-lookup"><span data-stu-id="e5b5b-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="e5b5b-279">Verifique se a proteção antimalware em tempo real está sendo executado corretamente.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-280">31</span><span class="sxs-lookup"><span data-stu-id="e5b5b-280">31</span></span></td>
<td><span data-ttu-id="e5b5b-281">Falha no microsoft defender para experiências de usuário conectados e serviço de telemetria.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="e5b5b-282">Código de falha: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-283">Ocorreu um erro com o serviço Windows telemetria durante a integração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="e5b5b-284">O processo de offboarding continua.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="e5b5b-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Verifique se há erros com o serviço Windows telemetria</a>.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-286">32</span><span class="sxs-lookup"><span data-stu-id="e5b5b-286">32</span></span></td>
<td><span data-ttu-id="e5b5b-287">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao solicitar a interrupção de si mesmo após o processo de offboard.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="e5b5b-288">Código de falha: %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="e5b5b-289">Ocorreu um erro durante o offboarding.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="e5b5b-290">Reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-291">33</span><span class="sxs-lookup"><span data-stu-id="e5b5b-291">33</span></span></td>
<td><span data-ttu-id="e5b5b-292">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao manter o GUID DO SENSE.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="e5b5b-293">Código de falha: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-294">Um identificador exclusivo é usado para representar cada dispositivo que está relatando para o portal.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="e5b5b-295">Se o identificador não persistir, o mesmo dispositivo poderá aparecer duas vezes no portal.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-295">If the identifier doesn't persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="e5b5b-296">Verifique as permissões do Registro no dispositivo para garantir que o serviço possa atualizar o Registro.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-297">34</span><span class="sxs-lookup"><span data-stu-id="e5b5b-297">34</span></span></td>
<td><span data-ttu-id="e5b5b-298">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao adicionar a si mesmo como uma dependência do serviço Experiências de Usuário Conectado e Telemetria, causando falha no processo de integração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="e5b5b-299">Código de falha: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-300">Ocorreu um erro com o serviço Windows telemetria.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="e5b5b-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Verifique se o serviço de dados de diagnóstico está habilitado</a>.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="e5b5b-302">Verifique se as configurações e scripts de integração foram implantados corretamente.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="e5b5b-303">Tente reimplantar os pacotes de configuração.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="e5b5b-304">Consulte <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-305">35</span><span class="sxs-lookup"><span data-stu-id="e5b5b-305">35</span></span></td>
<td><span data-ttu-id="e5b5b-306">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao se remover como uma dependência do serviço Experiências de Usuário Conectado e Telemetria.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="e5b5b-307">Código de falha: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-308">Ocorreu um erro com o Windows de telemetria durante o offboard.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="e5b5b-309">O processo de offboarding continua.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="e5b5b-310">Verifique se há erros com o serviço de Windows de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-311">36</span><span class="sxs-lookup"><span data-stu-id="e5b5b-311">36</span></span></td>
<td><span data-ttu-id="e5b5b-312">O registro de serviço de Telemetria e Experiências de Usuário Conectados do Microsoft Defender for Endpoint foi bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="e5b5b-313">Código de conclusão: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="e5b5b-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="e5b5b-314">Registrar o Defender para Ponto de Extremidade com o serviço Experiências de Usuário Conectado e Telemetria concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="e5b5b-315">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-316">37</span><span class="sxs-lookup"><span data-stu-id="e5b5b-316">37</span></span></td>
<td><span data-ttu-id="e5b5b-317">Microsoft Defender para Ponto de Extremidade Um módulo está prestes a exceder sua cota.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="e5b5b-318">Módulo: %1, Cota: {%2} {%3}, Porcentagem de utilização da cota: %4.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="e5b5b-319">O dispositivo quase usou sua cota alocada da janela atual de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="e5b5b-320">Está prestes a ser acelerada.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="e5b5b-321">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-322">38</span><span class="sxs-lookup"><span data-stu-id="e5b5b-322">38</span></span></td>
<td><span data-ttu-id="e5b5b-323">A conexão de rede é identificada como baixa.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-323">Network connection is identified as low.</span></span> <span data-ttu-id="e5b5b-324">O Microsoft Defender para Ponto de Extremidade entrará em contato com o servidor a cada %1 minuto.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="e5b5b-325">Conexão com medida: %2, internet disponível: %3, rede gratuita disponível: %4.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="e5b5b-326">O dispositivo está usando uma rede medição/paga e entrará em contato com o servidor com menos frequência.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="e5b5b-327">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-328">39</span><span class="sxs-lookup"><span data-stu-id="e5b5b-328">39</span></span></td>
<td><span data-ttu-id="e5b5b-329">A conexão de rede é identificada como normal.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-329">Network connection is identified as normal.</span></span> <span data-ttu-id="e5b5b-330">O Microsoft Defender para Ponto de Extremidade entrará em contato com o servidor a cada %1 minuto.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="e5b5b-331">Conexão com medida: %2, internet disponível: %3, rede gratuita disponível: %4.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="e5b5b-332">O dispositivo não está usando uma conexão com medição/pagamento e entrará em contato com o servidor como de costume.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-332">The device isn't using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="e5b5b-333">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-334">40</span><span class="sxs-lookup"><span data-stu-id="e5b5b-334">40</span></span></td>
<td><span data-ttu-id="e5b5b-335">O estado da bateria é identificado como baixo.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-335">Battery state is identified as low.</span></span> <span data-ttu-id="e5b5b-336">O Microsoft Defender para Ponto de Extremidade entrará em contato com o servidor a cada %1 minuto.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="e5b5b-337">Estado da bateria: %2.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="e5b5b-338">O dispositivo tem baixo nível de bateria e entrará em contato com o servidor com menos frequência.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="e5b5b-339">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-340">41</span><span class="sxs-lookup"><span data-stu-id="e5b5b-340">41</span></span></td>
<td><span data-ttu-id="e5b5b-341">O estado da bateria é identificado como normal.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-341">Battery state is identified as normal.</span></span> <span data-ttu-id="e5b5b-342">O Microsoft Defender para Ponto de Extremidade entrará em contato com o servidor a cada %1 minuto.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="e5b5b-343">Estado da bateria: %2.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="e5b5b-344">O dispositivo não tem baixo nível de bateria e entrará em contato com o servidor como de costume.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="e5b5b-345">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-346">42</span><span class="sxs-lookup"><span data-stu-id="e5b5b-346">42</span></span></td>
<td><span data-ttu-id="e5b5b-347">O componente do Microsoft Defender para Ponto de Extremidade falhou ao executar a ação.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-347">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="e5b5b-348">Componente: %1, Ação: %2, Tipo de Exceção: %3, Mensagem de exceção: %4</span><span class="sxs-lookup"><span data-stu-id="e5b5b-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="e5b5b-349">Erro interno.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-349">Internal error.</span></span> <span data-ttu-id="e5b5b-350">Falha ao iniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="e5b5b-351">Se esse erro persistir, contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-352">43</span><span class="sxs-lookup"><span data-stu-id="e5b5b-352">43</span></span></td>
<td><span data-ttu-id="e5b5b-353">O componente do Microsoft Defender para Ponto de Extremidade falhou ao executar a ação.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-353">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="e5b5b-354">Componente: %1, Ação: %2, Tipo de Exceção: %3, Erro de Exceção: %4, Mensagem de exceção: %5</span><span class="sxs-lookup"><span data-stu-id="e5b5b-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="e5b5b-355">Erro interno.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-355">Internal error.</span></span> <span data-ttu-id="e5b5b-356">Falha ao iniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="e5b5b-357">Se esse erro persistir, contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-358">44</span><span class="sxs-lookup"><span data-stu-id="e5b5b-358">44</span></span></td>
<td><span data-ttu-id="e5b5b-359">Offboarding do Serviço do Defender para Ponto de Extremidade concluído.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="e5b5b-360">O serviço foi desligado.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="e5b5b-361">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-362">45</span><span class="sxs-lookup"><span data-stu-id="e5b5b-362">45</span></span></td>
<td><span data-ttu-id="e5b5b-363">Falha ao registrar e iniciar a sessão de rastreamento de eventos [%1].</span><span class="sxs-lookup"><span data-stu-id="e5b5b-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="e5b5b-364">Código de erro: %2</span><span class="sxs-lookup"><span data-stu-id="e5b5b-364">Error code: %2</span></span></td>
<td><span data-ttu-id="e5b5b-365">Ocorreu um erro na inicialização do serviço durante a criação da sessão ETW.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="e5b5b-366">Isso causou uma falha na iniciação do serviço.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="e5b5b-367">Se esse erro persistir, contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-368">46</span><span class="sxs-lookup"><span data-stu-id="e5b5b-368">46</span></span></td>
<td><span data-ttu-id="e5b5b-369">Falha ao registrar e iniciar a sessão de rastreamento de eventos [%1] devido à falta de recursos.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="e5b5b-370">Código de erro: %2.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-370">Error code: %2.</span></span> <span data-ttu-id="e5b5b-371">Isso é mais provável porque há muitas sessões de rastreamento de eventos ativas.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="e5b5b-372">O serviço repetirá em 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="e5b5b-373">Ocorreu um erro na inicialização do serviço ao criar sessão ETW devido à falta de recursos.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="e5b5b-374">O serviço foi iniciado e está em execução, mas não relatará nenhum evento de sensor até que a sessão ETW seja iniciada.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-374">The service started and is running, but won't report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="e5b5b-375">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="e5b5b-376">O serviço tentará iniciar a sessão a cada minuto.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-377">47</span><span class="sxs-lookup"><span data-stu-id="e5b5b-377">47</span></span></td>
<td><span data-ttu-id="e5b5b-378">Registrou com êxito e iniciou a sessão de rastreamento de eventos - recuperada após tentativas anteriores com falha.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="e5b5b-379">Este evento segue o evento anterior após o início com êxito da sessão ETW.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="e5b5b-380">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="e5b5b-381">48</span><span class="sxs-lookup"><span data-stu-id="e5b5b-381">48</span></span></td>
<td><span data-ttu-id="e5b5b-382">Falha ao adicionar um provedor [%1] à sessão de rastreamento de eventos [%2].</span><span class="sxs-lookup"><span data-stu-id="e5b5b-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="e5b5b-383">Código de erro: %3.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-383">Error code: %3.</span></span> <span data-ttu-id="e5b5b-384">Isso significa que os eventos deste provedor não serão relatados.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="e5b5b-385">Falha ao adicionar um provedor à sessão ETW.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="e5b5b-386">Como resultado, os eventos do provedor não são relatados.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="e5b5b-387">Verifique o código de erro.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-387">Check the error code.</span></span> <span data-ttu-id="e5b5b-388">Se o erro persistir, contate Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-389">49</span><span class="sxs-lookup"><span data-stu-id="e5b5b-389">49</span></span></td>
   <td><span data-ttu-id="e5b5b-390">Comando de configuração de nuvem inválido recebido e ignorado.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-390">Invalid cloud configuration command received and ignored.</span></span> <span data-ttu-id="e5b5b-391">Versão: %1, status: %2, código de erro: %3, mensagem: %4</span><span class="sxs-lookup"><span data-stu-id="e5b5b-391">Version: %1, status: %2, error code: %3, message: %4</span></span></td>
   <td><span data-ttu-id="e5b5b-392">Recebeu um arquivo de configuração inválido do serviço de nuvem que foi ignorado.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-392">Received an invalid configuration file from the cloud service that was ignored.</span></span></td>
   <td><span data-ttu-id="e5b5b-393">Se esse erro persistir, contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-393">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-394">50</span><span class="sxs-lookup"><span data-stu-id="e5b5b-394">50</span></span></td>
   <td><span data-ttu-id="e5b5b-395">Nova configuração de nuvem aplicada com êxito.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-395">New cloud configuration applied successfully.</span></span> <span data-ttu-id="e5b5b-396">Versão: %1.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-396">Version: %1.</span></span></td>
   <td><span data-ttu-id="e5b5b-397">Aplicou com êxito uma nova configuração do serviço de nuvem.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-397">Successfully applied a new configuration from the cloud service.</span></span></td>
   <td><span data-ttu-id="e5b5b-398">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-398">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-399">51</span><span class="sxs-lookup"><span data-stu-id="e5b5b-399">51</span></span></td>
   <td><span data-ttu-id="e5b5b-400">Falha na aplicação da nova configuração de nuvem, versão: %1.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-400">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="e5b5b-401">Aplicou com êxito a última boa configuração conhecida, versão %2.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-401">Successfully applied the last known good configuration, version %2.</span></span></td>
   <td><span data-ttu-id="e5b5b-402">Recebeu um arquivo de configuração ruim do serviço de nuvem.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-402">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="e5b5b-403">A última boa configuração conhecida foi aplicada com êxito.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-403">Last known good configuration was applied successfully.</span></span></td>
   <td><span data-ttu-id="e5b5b-404">Se esse erro persistir, contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-404">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-405">52</span><span class="sxs-lookup"><span data-stu-id="e5b5b-405">52</span></span></td>
   <td><span data-ttu-id="e5b5b-406">Falha na aplicação da nova configuração de nuvem, versão: %1.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-406">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="e5b5b-407">Também falhou ao aplicar a última boa configuração conhecida, versão %2.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-407">Also failed to apply last known good configuration, version %2.</span></span> <span data-ttu-id="e5b5b-408">Aplicou com êxito a configuração padrão.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-408">Successfully applied the default configuration.</span></span></td>
   <td><span data-ttu-id="e5b5b-409">Recebeu um arquivo de configuração ruim do serviço de nuvem.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-409">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="e5b5b-410">Falha ao aplicar a última boa configuração conhecida e a configuração padrão foi aplicada.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-410">Failed to apply the last known good configuration - and the default configuration was applied.</span></span></td>
   <td><span data-ttu-id="e5b5b-411">O serviço tentará baixar um novo arquivo de configuração em 5 minutos.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-411">The service will attempt to download a new configuration file within 5 minutes.</span></span> <span data-ttu-id="e5b5b-412">Se você não vir o evento #50 - entre em contato com o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-412">If you don't see event #50 - contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-413">53</span><span class="sxs-lookup"><span data-stu-id="e5b5b-413">53</span></span></td>
   <td><span data-ttu-id="e5b5b-414">Configuração de nuvem carregada do armazenamento persistente, versão: %1.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-414">Cloud configuration loaded from persistent storage, version: %1.</span></span></td>
   <td><span data-ttu-id="e5b5b-415">A configuração foi carregada do armazenamento persistente na inicialização do serviço.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-415">The configuration was loaded from persistent storage on service startup.</span></span></td>
   <td><span data-ttu-id="e5b5b-416">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-416">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-417">55</span><span class="sxs-lookup"><span data-stu-id="e5b5b-417">55</span></span></td>
   <td><span data-ttu-id="e5b5b-418">Falha ao criar o autologger ETW seguro.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-418">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="e5b5b-419">Código de falha: %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-419">Failure code: %1</span></span></td>
   <td><span data-ttu-id="e5b5b-420">Falha ao criar o madeireiro ETW seguro.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-420">Failed to create the secure ETW logger.</span></span></td>
   <td><span data-ttu-id="e5b5b-421">Reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-421">Reboot the device.</span></span> <span data-ttu-id="e5b5b-422">Se esse erro persistir, contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-422">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-423">56</span><span class="sxs-lookup"><span data-stu-id="e5b5b-423">56</span></span></td>
   <td><span data-ttu-id="e5b5b-424">Falha ao remover o autologger ETW seguro.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-424">Failed to remove the Secure ETW autologger.</span></span> <span data-ttu-id="e5b5b-425">Código de falha: %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-425">Failure code: %1</span></span></td>
   <td><span data-ttu-id="e5b5b-426">Falha ao remover a sessão ETW segura no offboard.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-426">Failed to remove the secure ETW session on offboarding.</span></span></td>
   <td><span data-ttu-id="e5b5b-427">Contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-427">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-428">57</span><span class="sxs-lookup"><span data-stu-id="e5b5b-428">57</span></span></td>
   <td><span data-ttu-id="e5b5b-429">Capturando um instantâneo do computador para fins de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-429">Capturing a snapshot of the machine for troubleshooting purposes.</span></span></td>
   <td><span data-ttu-id="e5b5b-430">Um pacote de investigação, também conhecido como pacote forense, está sendo coletado.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-430">An investigation package, also known as forensics package, is being collected.</span></span></td>
   <td><span data-ttu-id="e5b5b-431">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-431">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-432">59</span><span class="sxs-lookup"><span data-stu-id="e5b5b-432">59</span></span></td>
   <td><span data-ttu-id="e5b5b-433">Comando inicial: %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-433">Starting command: %1</span></span></td>
   <td><span data-ttu-id="e5b5b-434">Iniciando a execução do comando de resposta.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-434">Starting response command execution.</span></span></td>
   <td><span data-ttu-id="e5b5b-435">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-435">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-436">60</span><span class="sxs-lookup"><span data-stu-id="e5b5b-436">60</span></span></td>
   <td><span data-ttu-id="e5b5b-437">Falha ao executar o comando %1, erro: %2.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-437">Failed to run command %1, error: %2.</span></span></td>
   <td><span data-ttu-id="e5b5b-438">Falha ao executar o comando de resposta.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-438">Failed to execute response command.</span></span></td>
   <td><span data-ttu-id="e5b5b-439">Se esse erro persistir, contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-439">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-440">61</span><span class="sxs-lookup"><span data-stu-id="e5b5b-440">61</span></span></td>
   <td><span data-ttu-id="e5b5b-441">Os parâmetros de comando da coleção de dados são inválidos: SasUri: %1, compressionLevel: %2.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-441">Data collection command parameters are invalid: SasUri: %1, compressionLevel: %2.</span></span></td>
   <td><span data-ttu-id="e5b5b-442">Falha ao ler ou analisar os argumentos de comando da coleção de dados (argumentos inválidos).</span><span class="sxs-lookup"><span data-stu-id="e5b5b-442">Failed to read or parse the data collection command arguments (invalid arguments).</span></span></td>
   <td><span data-ttu-id="e5b5b-443">Se esse erro persistir, contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-443">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-444">62</span><span class="sxs-lookup"><span data-stu-id="e5b5b-444">62</span></span></td>
   <td><span data-ttu-id="e5b5b-445">Falha ao iniciar o serviço Experiências de Usuário Conectado e Telemetria.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-445">Failed to start Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="e5b5b-446">Código de falha: %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-446">Failure code: %1</span></span></td>
   <td><span data-ttu-id="e5b5b-447">Falha ao iniciar o serviço Experiências do Usuário Conectado e Telemetria (diagtrack).</span><span class="sxs-lookup"><span data-stu-id="e5b5b-447">Connected User Experiences and Telemetry (diagtrack) service failed to start.</span></span> <span data-ttu-id="e5b5b-448">A telemetria que não seja do Microsoft Defender para Ponto de Extremidade não será enviada desse computador.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-448">Non-Microsoft Defender for Endpoint telemetry won't be sent from this machine.</span></span></td>
   <td><span data-ttu-id="e5b5b-449">Procure mais dicas de solução de problemas no log de eventos: Microsoft-Windows-UniversalTelemetryClient/Operational.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-449">Look for more troubleshooting hints in the event log: Microsoft-Windows-UniversalTelemetryClient/Operational.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-450">63</span><span class="sxs-lookup"><span data-stu-id="e5b5b-450">63</span></span></td>
   <td><span data-ttu-id="e5b5b-451">Atualizando o tipo de início do serviço externo.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-451">Updating the start type of external service.</span></span> <span data-ttu-id="e5b5b-452">Nome: %1, tipo de início real: %2, tipo de início esperado: %3, código de saída: %4</span><span class="sxs-lookup"><span data-stu-id="e5b5b-452">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="e5b5b-453">Tipo de início atualizado do serviço externo.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-453">Updated start type of the external service.</span></span></td>
   <td><span data-ttu-id="e5b5b-454">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-454">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-455">64</span><span class="sxs-lookup"><span data-stu-id="e5b5b-455">64</span></span></td>
   <td><span data-ttu-id="e5b5b-456">Iniciando o serviço externo interrompido.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-456">Starting stopped external service.</span></span> <span data-ttu-id="e5b5b-457">Nome: %1, código de saída: %2</span><span class="sxs-lookup"><span data-stu-id="e5b5b-457">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="e5b5b-458">Iniciando um serviço externo.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-458">Starting an external service.</span></span></td>
   <td><span data-ttu-id="e5b5b-459">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-459">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-460">65</span><span class="sxs-lookup"><span data-stu-id="e5b5b-460">65</span></span></td>
   <td><span data-ttu-id="e5b5b-461">Falha ao carregar o driver de Minifiltro de Componente de Eventos de Segurança da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-461">Failed to load Microsoft Security Events Component Minifilter driver.</span></span> <span data-ttu-id="e5b5b-462">Código de falha: %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-462">Failure code: %1</span></span></td>
   <td><span data-ttu-id="e5b5b-463">Falha ao carregar MsSecFlt.sys minifiltro de sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-463">Failed to load MsSecFlt.sys filesystem minifilter.</span></span></td>
   <td><span data-ttu-id="e5b5b-464">Reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-464">Reboot the device.</span></span> <span data-ttu-id="e5b5b-465">Se esse erro persistir, contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-465">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-466">66</span><span class="sxs-lookup"><span data-stu-id="e5b5b-466">66</span></span></td>
   <td><span data-ttu-id="e5b5b-467">Atualização de política: modo de latência - %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-467">Policy update: Latency mode - %1</span></span></td>
   <td><span data-ttu-id="e5b5b-468">A C# de frequência de conexão do C&C foi atualizada.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-468">The C&C connection frequency policy was updated.</span></span></td>
   <td><span data-ttu-id="e5b5b-469">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-469">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-470">68</span><span class="sxs-lookup"><span data-stu-id="e5b5b-470">68</span></span></td>
   <td><span data-ttu-id="e5b5b-471">O tipo de início do serviço é inesperado.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-471">The start type of the service is unexpected.</span></span> <span data-ttu-id="e5b5b-472">Nome do serviço: %1, tipo de início real: %2, tipo de início esperado: %3</span><span class="sxs-lookup"><span data-stu-id="e5b5b-472">Service name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="e5b5b-473">Tipo de início de serviço externo inesperado.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-473">Unexpected external service start type.</span></span></td>
   <td><span data-ttu-id="e5b5b-474">Correção do tipo de início do serviço externo.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-474">Fix the external service start type.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-475">69</span><span class="sxs-lookup"><span data-stu-id="e5b5b-475">69</span></span></td>
   <td><span data-ttu-id="e5b5b-476">O serviço é interrompido.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-476">The service is stopped.</span></span> <span data-ttu-id="e5b5b-477">Nome do serviço: %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-477">Service name: %1</span></span></td>
   <td><span data-ttu-id="e5b5b-478">O serviço externo é interrompido.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-478">The external service is stopped.</span></span></td>
   <td><span data-ttu-id="e5b5b-479">Inicie o serviço externo.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-479">Start the external service.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-480">70</span><span class="sxs-lookup"><span data-stu-id="e5b5b-480">70</span></span></td>
   <td><span data-ttu-id="e5b5b-481">Atualização de política: Permitir coleta de amostras - %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-481">Policy update: Allow sample collection - %1</span></span></td>
   <td><span data-ttu-id="e5b5b-482">A política de coleta de exemplo foi atualizada.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-482">The sample collection policy was updated.</span></span></td>
   <td><span data-ttu-id="e5b5b-483">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-483">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-484">71</span><span class="sxs-lookup"><span data-stu-id="e5b5b-484">71</span></span></td>
   <td><span data-ttu-id="e5b5b-485">Com êxito para executar o comando: %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-485">Succeeded to run command: %1</span></span></td>
   <td><span data-ttu-id="e5b5b-486">O comando foi executado com êxito.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-486">The command was executed successfully.</span></span></td>
   <td><span data-ttu-id="e5b5b-487">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-487">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-488">72</span><span class="sxs-lookup"><span data-stu-id="e5b5b-488">72</span></span></td>
   <td><span data-ttu-id="e5b5b-489">Tentou enviar o primeiro relatório de perfil completo do computador.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-489">Tried to send first full machine profile report.</span></span> <span data-ttu-id="e5b5b-490">Código do resultado: %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-490">Result code: %1</span></span></td>
   <td><span data-ttu-id="e5b5b-491">Somente informações.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-491">Informational only.</span></span></td>
   <td><span data-ttu-id="e5b5b-492">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-492">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-493">73</span><span class="sxs-lookup"><span data-stu-id="e5b5b-493">73</span></span></td>
   <td><span data-ttu-id="e5b5b-494">Sentido de início da plataforma: %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-494">Sense starting for platform: %1</span></span></td>
   <td><span data-ttu-id="e5b5b-495">Somente informações.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-495">Informational only.</span></span></td>
   <td><span data-ttu-id="e5b5b-496">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-496">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-497">74</span><span class="sxs-lookup"><span data-stu-id="e5b5b-497">74</span></span></td>
   <td><span data-ttu-id="e5b5b-498">A marca de dispositivo no Registro excede o limite de comprimento.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-498">Device tag in registry exceeds length limit.</span></span> <span data-ttu-id="e5b5b-499">Nome da marca: %2.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-499">Tag name: %2.</span></span> <span data-ttu-id="e5b5b-500">Limite de comprimento: %1.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-500">Length limit: %1.</span></span></td>
   <td><span data-ttu-id="e5b5b-501">A marca do dispositivo excede o limite de comprimento.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-501">The device tag exceeds the length limit.</span></span></td>
   <td><span data-ttu-id="e5b5b-502">Use uma marca de dispositivo mais curta.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-502">Use a shorter device tag.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-503">81</span><span class="sxs-lookup"><span data-stu-id="e5b5b-503">81</span></span></td>
   <td><span data-ttu-id="e5b5b-504">Falha ao criar o Microsoft Defender para o autologger ETW do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-504">Failed to create Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="e5b5b-505">Código de falha: %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-505">Failure code: %1</span></span></td>
   <td><span data-ttu-id="e5b5b-506">Falha ao criar a sessão ETW.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-506">Failed to create the ETW session.</span></span></td>
   <td><span data-ttu-id="e5b5b-507">Reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-507">Reboot the device.</span></span> <span data-ttu-id="e5b5b-508">Se esse erro persistir, contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-508">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-509">82</span><span class="sxs-lookup"><span data-stu-id="e5b5b-509">82</span></span></td>
   <td><span data-ttu-id="e5b5b-510">Falha ao remover o microsoft defender para o autologger ETW do ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-510">Failed to remove Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="e5b5b-511">Código de falha: %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-511">Failure code: %1</span></span></td>
   <td><span data-ttu-id="e5b5b-512">Falha ao excluir a sessão ETW.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-512">Failed to delete the ETW session.</span></span></td>
   <td><span data-ttu-id="e5b5b-513">Contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-513">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-514">84</span><span class="sxs-lookup"><span data-stu-id="e5b5b-514">84</span></span></td>
   <td><span data-ttu-id="e5b5b-515">De Windows Defender Antivírus modo de execução.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-515">Set Windows Defender Antivirus running mode.</span></span> <span data-ttu-id="e5b5b-516">Forçar o modo passivo: %1, código de resultado: %2.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-516">Force passive mode: %1, result code: %2.</span></span></td>
   <td><span data-ttu-id="e5b5b-517">Definir o modo de execução do defender (ativo ou passivo).</span><span class="sxs-lookup"><span data-stu-id="e5b5b-517">Set defender running mode (active or passive).</span></span></td>
   <td><span data-ttu-id="e5b5b-518">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-518">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-519">85</span><span class="sxs-lookup"><span data-stu-id="e5b5b-519">85</span></span></td>
   <td><span data-ttu-id="e5b5b-520">Falha ao disparar o Microsoft Defender para o ponto de extremidade executável.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-520">Failed to trigger Microsoft Defender for Endpoint executable.</span></span> <span data-ttu-id="e5b5b-521">Código de falha: %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-521">Failure code: %1</span></span></td>
   <td><span data-ttu-id="e5b5b-522">Falha no executável SenseIR estrelado.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-522">Starring SenseIR executable failed.</span></span></td>
   <td><span data-ttu-id="e5b5b-523">Reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-523">Reboot the device.</span></span> <span data-ttu-id="e5b5b-524">Se esse erro persistir, contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-524">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-525">86</span><span class="sxs-lookup"><span data-stu-id="e5b5b-525">86</span></span></td>
   <td><span data-ttu-id="e5b5b-526">A partida novamente interrompeu o serviço externo que deveria estar para cima.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-526">Starting again stopped external service that should be up.</span></span> <span data-ttu-id="e5b5b-527">Nome: %1, código de saída: %2</span><span class="sxs-lookup"><span data-stu-id="e5b5b-527">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="e5b5b-528">Iniciando o serviço externo novamente.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-528">Starting the external service again.</span></span></td>
   <td><span data-ttu-id="e5b5b-529">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-529">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-530">87</span><span class="sxs-lookup"><span data-stu-id="e5b5b-530">87</span></span></td>
   <td><span data-ttu-id="e5b5b-531">Não é possível iniciar o serviço externo.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-531">Cannot start the external service.</span></span> <span data-ttu-id="e5b5b-532">Nome: %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-532">Name: %1</span></span></td>
   <td><span data-ttu-id="e5b5b-533">Falha ao iniciar o serviço externo.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-533">Failed to start the external service.</span></span></td>
   <td><span data-ttu-id="e5b5b-534">Contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-534">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-535">88</span><span class="sxs-lookup"><span data-stu-id="e5b5b-535">88</span></span></td>
   <td><span data-ttu-id="e5b5b-536">Atualizando o tipo de início do serviço externo novamente.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-536">Updating the start type of external service again.</span></span> <span data-ttu-id="e5b5b-537">Nome: %1, tipo de início real: %2, tipo de início esperado: %3, código de saída: %4</span><span class="sxs-lookup"><span data-stu-id="e5b5b-537">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="e5b5b-538">Atualizou o tipo de início do serviço externo.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-538">Updated the start type of the external service.</span></span></td>
   <td><span data-ttu-id="e5b5b-539">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-539">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-540">89</span><span class="sxs-lookup"><span data-stu-id="e5b5b-540">89</span></span></td>
   <td><span data-ttu-id="e5b5b-541">Não é possível atualizar o tipo de início do serviço externo.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-541">Cannot update the start type of external service.</span></span> <span data-ttu-id="e5b5b-542">Nome: %1, tipo de início real: %2, tipo de início esperado: %3</span><span class="sxs-lookup"><span data-stu-id="e5b5b-542">Name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="e5b5b-543">Não é possível atualizar o tipo de início do serviço externo.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-543">Can't update the start type of the external service.</span></span></td>
   <td><span data-ttu-id="e5b5b-544">Contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-544">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-545">90</span><span class="sxs-lookup"><span data-stu-id="e5b5b-545">90</span></span></td>
   <td><span data-ttu-id="e5b5b-546">Falha ao configurar o System Guard Runtime Monitor para se conectar ao serviço de nuvem na região geográfica %1.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-546">Failed to configure System Guard Runtime Monitor to connect to cloud service in geo-region %1.</span></span> <span data-ttu-id="e5b5b-547">Código de falha: %2</span><span class="sxs-lookup"><span data-stu-id="e5b5b-547">Failure code: %2</span></span></td>
   <td><span data-ttu-id="e5b5b-548">O System Guard Runtime Monitor não enviará dados de atestado para o serviço de nuvem.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-548">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="e5b5b-549">Verifique as permissões no caminho do registro: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="e5b5b-549">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="e5b5b-550">Se nenhum problema for detectado, entre em contato com o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-550">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-551">91</span><span class="sxs-lookup"><span data-stu-id="e5b5b-551">91</span></span></td>
   <td><span data-ttu-id="e5b5b-552">Falha ao remover informações de região geográfica do Monitor de Tempo de Execução do System Guard.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-552">Failed to remove System Guard Runtime Monitor geo-region information.</span></span> <span data-ttu-id="e5b5b-553">Código de falha: %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-553">Failure code: %1</span></span></td>
   <td><span data-ttu-id="e5b5b-554">O System Guard Runtime Monitor não enviará dados de atestado para o serviço de nuvem.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-554">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="e5b5b-555">Verifique as permissões no caminho do registro: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="e5b5b-555">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="e5b5b-556">Se nenhum problema for detectado, entre em contato com o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-556">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-557">92</span><span class="sxs-lookup"><span data-stu-id="e5b5b-557">92</span></span></td>
   <td><span data-ttu-id="e5b5b-558">Interromper o envio da cota de dados cibernéticos do sensor porque a cota de dados é excedida.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-558">Stopping sending sensor cyber data quota because data quota is exceeded.</span></span> <span data-ttu-id="e5b5b-559">Retomará o envio depois que o período de cota passar.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-559">Will resume sending once quota period passes.</span></span> <span data-ttu-id="e5b5b-560">Máscara de Estado: %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-560">State Mask: %1</span></span></td>
   <td><span data-ttu-id="e5b5b-561">Exceder o limite de limitação.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-561">Exceed throttling limit.</span></span></td>
   <td><span data-ttu-id="e5b5b-562">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-562">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-563">93</span><span class="sxs-lookup"><span data-stu-id="e5b5b-563">93</span></span></td>
   <td><span data-ttu-id="e5b5b-564">Retomando o envio de dados cibernéticos do sensor.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-564">Resuming sending sensor cyber data.</span></span> <span data-ttu-id="e5b5b-565">Máscara de Estado: %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-565">State Mask: %1</span></span></td>
   <td><span data-ttu-id="e5b5b-566">Retomar o envio de dados cibernéticos.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-566">Resume cyber data submission.</span></span></td>
   <td><span data-ttu-id="e5b5b-567">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-567">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-568">94</span><span class="sxs-lookup"><span data-stu-id="e5b5b-568">94</span></span></td>
   <td><span data-ttu-id="e5b5b-569">O executável do Microsoft Defender para Ponto de Extremidade foi iniciado</span><span class="sxs-lookup"><span data-stu-id="e5b5b-569">Microsoft Defender for Endpoint executable has started</span></span></td>
   <td><span data-ttu-id="e5b5b-570">O executável SenseCE foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-570">The SenseCE executable has started.</span></span></td>
   <td><span data-ttu-id="e5b5b-571">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-571">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-572">95</span><span class="sxs-lookup"><span data-stu-id="e5b5b-572">95</span></span></td>
   <td><span data-ttu-id="e5b5b-573">O executável do Microsoft Defender para Ponto de Extremidade terminou</span><span class="sxs-lookup"><span data-stu-id="e5b5b-573">Microsoft Defender for Endpoint executable has ended</span></span></td>
   <td><span data-ttu-id="e5b5b-574">O executável SenseCE foi encerrado.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-574">The SenseCE executable has ended.</span></span></td>
   <td><span data-ttu-id="e5b5b-575">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-575">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-576">96</span><span class="sxs-lookup"><span data-stu-id="e5b5b-576">96</span></span></td>
   <td><span data-ttu-id="e5b5b-577">O Microsoft Defender para Endpoint Init chamou.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-577">Microsoft Defender for Endpoint Init has called.</span></span> <span data-ttu-id="e5b5b-578">Código do resultado: %2</span><span class="sxs-lookup"><span data-stu-id="e5b5b-578">Result code: %2</span></span></td>
   <td><span data-ttu-id="e5b5b-579">O executável SenseCE chamou a inicialização do MCE.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-579">The SenseCE executable has called MCE initialization.</span></span></td>
   <td><span data-ttu-id="e5b5b-580">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-580">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-581">97</span><span class="sxs-lookup"><span data-stu-id="e5b5b-581">97</span></span></td>
   <td><span data-ttu-id="e5b5b-582">Há problemas de conectividade com a Nuvem para o cenário de DLP</span><span class="sxs-lookup"><span data-stu-id="e5b5b-582">There are connectivity issues to the Cloud for the DLP scenario</span></span></td>
   <td><span data-ttu-id="e5b5b-583">Há problemas de conectividade de rede que afetam o fluxo de classificação de DLP.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-583">There are network connectivity issues that affect the DLP classification flow.</span></span></td>
   <td><span data-ttu-id="e5b5b-584">Verifique a conectividade de rede.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-584">Check the network connectivity.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-585">98</span><span class="sxs-lookup"><span data-stu-id="e5b5b-585">98</span></span></td>
   <td><span data-ttu-id="e5b5b-586">A conectividade com a Nuvem para o cenário DLP foi restaurada</span><span class="sxs-lookup"><span data-stu-id="e5b5b-586">The connectivity to the Cloud for the DLP scenario has been restored</span></span></td>
   <td><span data-ttu-id="e5b5b-587">A conectividade com a rede foi restaurada e o fluxo de classificação DLP pode continuar.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-587">The connectivity to the network was restored and the DLP classification flow can continue.</span></span></td>
   <td><span data-ttu-id="e5b5b-588">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-588">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-589">99</span><span class="sxs-lookup"><span data-stu-id="e5b5b-589">99</span></span></td>
   <td><span data-ttu-id="e5b5b-590">Sense encontrou o seguinte erro ao se comunicar com o servidor: (%1).</span><span class="sxs-lookup"><span data-stu-id="e5b5b-590">Sense has encountered the following error while communicating with server: (%1).</span></span> <span data-ttu-id="e5b5b-591">Resultado: (%2)</span><span class="sxs-lookup"><span data-stu-id="e5b5b-591">Result: (%2)</span></span></td>
   <td><span data-ttu-id="e5b5b-592">Ocorreu um erro de comunicação.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-592">A communication error occurred.</span></span></td>
   <td><span data-ttu-id="e5b5b-593">Verifique os seguintes eventos no log de eventos para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-593">Check the following events in the event log for further details.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-594">100</span><span class="sxs-lookup"><span data-stu-id="e5b5b-594">100</span></span></td>
   <td><span data-ttu-id="e5b5b-595">O executável do Microsoft Defender para Ponto de Extremidade falhou ao iniciar.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-595">Microsoft Defender for Endpoint executable failed to start.</span></span> <span data-ttu-id="e5b5b-596">Código de falha: %1</span><span class="sxs-lookup"><span data-stu-id="e5b5b-596">Failure code: %1</span></span></td>
   <td><span data-ttu-id="e5b5b-597">O executável SenseCE falhou ao iniciar.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-597">The SenseCE executable has failed to start.</span></span></td>
   <td><span data-ttu-id="e5b5b-598">Reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-598">Reboot the device.</span></span> <span data-ttu-id="e5b5b-599">Se esse erro persistir, contate o Suporte.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-599">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-600">102</span><span class="sxs-lookup"><span data-stu-id="e5b5b-600">102</span></span></td>
   <td><span data-ttu-id="e5b5b-601">O microsoft Defender for Endpoint Network Detection and Response executable foi iniciado</span><span class="sxs-lookup"><span data-stu-id="e5b5b-601">Microsoft Defender for Endpoint Network Detection and Response executable has started</span></span></td>
   <td><span data-ttu-id="e5b5b-602">O executável SenseNdr foi iniciado.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-602">The SenseNdr executable has started.</span></span></td>
   <td><span data-ttu-id="e5b5b-603">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-603">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="e5b5b-604">103</span><span class="sxs-lookup"><span data-stu-id="e5b5b-604">103</span></span></td>
   <td><span data-ttu-id="e5b5b-605">Microsoft Defender for Endpoint Network Detection and Response executable has ended</span><span class="sxs-lookup"><span data-stu-id="e5b5b-605">Microsoft Defender for Endpoint Network Detection and Response executable has ended</span></span></td>
   <td><span data-ttu-id="e5b5b-606">O executável SenseNdr foi encerrado.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-606">The SenseNdr executable has ended.</span></span></td>
   <td><span data-ttu-id="e5b5b-607">Notificação operacional normal; nenhuma ação necessária.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-607">Normal operating notification; no action required.</span></span></td>
</tr>
</tbody>
</table>

><span data-ttu-id="e5b5b-608">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="e5b5b-608">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e5b5b-609">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="e5b5b-609">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="e5b5b-610">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e5b5b-610">Related topics</span></span>
- [<span data-ttu-id="e5b5b-611">Dispositivos integrados do Windows 10</span><span class="sxs-lookup"><span data-stu-id="e5b5b-611">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="e5b5b-612">Definir as configurações de proxy de dispositivo e conectividade com a Internet</span><span class="sxs-lookup"><span data-stu-id="e5b5b-612">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="e5b5b-613">Solucionar problemas do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e5b5b-613">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
