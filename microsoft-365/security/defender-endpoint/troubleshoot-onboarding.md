---
title: Solucionar problemas de integração do Microsoft Defender para pontos de extremidade
description: Solucionar problemas que podem surgir durante a integração de dispositivos ou para o serviço Microsoft Defender para Ponto de Extremidade.
keywords: solucionar problemas de integração, problemas de integração, visualizador de eventos, builds de coleta e visualização de dados, dados do sensor e diagnósticos
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: b9d6cd374a107a403269bc3babbe4220d69e1cce
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844869"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-onboarding-issues"></a><span data-ttu-id="bef28-104">Solucionar problemas de integração do Microsoft Defender para pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="bef28-104">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bef28-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="bef28-105">**Applies to:**</span></span>

- [<span data-ttu-id="bef28-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="bef28-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- <span data-ttu-id="bef28-107">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="bef28-107">Windows Server 2012 R2</span></span>
- <span data-ttu-id="bef28-108">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="bef28-108">Windows Server 2016</span></span>
- [<span data-ttu-id="bef28-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bef28-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bef28-110">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="bef28-110">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bef28-111">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="bef28-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="bef28-112">Talvez seja necessário solucionar problemas do processo de integração do Microsoft Defender for Endpoint se encontrar problemas.</span><span class="sxs-lookup"><span data-stu-id="bef28-112">You might need to troubleshoot the Microsoft Defender for Endpoint onboarding process if you encounter issues.</span></span>
<span data-ttu-id="bef28-113">Esta página fornece etapas detalhadas para solucionar problemas de integração que podem ocorrer ao implantar com uma das ferramentas de implantação e erros comuns que podem ocorrer nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bef28-113">This page provides detailed steps to troubleshoot onboarding issues that might occur when deploying with one of the deployment tools and common errors that might occur on the devices.</span></span>

## <a name="troubleshoot-issues-with-onboarding-tools"></a><span data-ttu-id="bef28-114">Solucionar problemas com ferramentas de integração</span><span class="sxs-lookup"><span data-stu-id="bef28-114">Troubleshoot issues with onboarding tools</span></span>

<span data-ttu-id="bef28-115">Se você concluiu o processo de integração [](investigate-machines.md) e não vê dispositivos na lista Dispositivos após uma hora, pode indicar um problema de integração ou conectividade.</span><span class="sxs-lookup"><span data-stu-id="bef28-115">If you have completed the onboarding process and don't see devices in the [Devices list](investigate-machines.md) after an hour, it might indicate an onboarding or connectivity problem.</span></span>

### <a name="troubleshoot-onboarding-when-deploying-with-group-policy"></a><span data-ttu-id="bef28-116">Solucionar problemas de integração ao implantar com a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="bef28-116">Troubleshoot onboarding when deploying with Group Policy</span></span>

<span data-ttu-id="bef28-117">A implantação com a Política de Grupo é feita executando o script de integração nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bef28-117">Deployment with Group Policy is done by running the onboarding script on the devices.</span></span> <span data-ttu-id="bef28-118">O console da Política de Grupo não indica se a implantação foi bem-sucedida ou não.</span><span class="sxs-lookup"><span data-stu-id="bef28-118">The Group Policy console does not indicate if the deployment has succeeded or not.</span></span>

<span data-ttu-id="bef28-119">Se você tiver concluído o processo de integração [](investigate-machines.md) e não vir dispositivos na lista Dispositivos após uma hora, poderá verificar a saída do script nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bef28-119">If you have completed the onboarding process and don't see devices in the [Devices list](investigate-machines.md) after an hour, you can check the output of the script on the devices.</span></span> <span data-ttu-id="bef28-120">Para obter mais informações, consulte [Solucionar problemas de integração ao implantar com um script](#troubleshoot-onboarding-when-deploying-with-a-script).</span><span class="sxs-lookup"><span data-stu-id="bef28-120">For more information, see [Troubleshoot onboarding when deploying with a script](#troubleshoot-onboarding-when-deploying-with-a-script).</span></span>

<span data-ttu-id="bef28-121">Se o script for concluído com êxito, consulte [Solucionar](#troubleshoot-onboarding-issues-on-the-device) problemas de integração nos dispositivos para obter erros adicionais que possam ocorrer.</span><span class="sxs-lookup"><span data-stu-id="bef28-121">If the script completes successfully, see [Troubleshoot onboarding issues on the devices](#troubleshoot-onboarding-issues-on-the-device) for additional errors that might occur.</span></span>

### <a name="troubleshoot-onboarding-issues-when-deploying-with-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="bef28-122">Solucionar problemas de integração ao implantar com Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bef28-122">Troubleshoot onboarding issues when deploying with Microsoft Endpoint Configuration Manager</span></span>

<span data-ttu-id="bef28-123">Ao integrar dispositivos usando as seguintes versões do Configuration Manager:</span><span class="sxs-lookup"><span data-stu-id="bef28-123">When onboarding devices using the following versions of Configuration Manager:</span></span>

- <span data-ttu-id="bef28-124">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="bef28-124">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="bef28-125">System Center Configuration Manager 2012</span><span class="sxs-lookup"><span data-stu-id="bef28-125">System Center 2012 Configuration Manager</span></span>
- <span data-ttu-id="bef28-126">Gerenciador de Configurações do System Center 2012 R2</span><span class="sxs-lookup"><span data-stu-id="bef28-126">System Center 2012 R2 Configuration Manager</span></span>

<span data-ttu-id="bef28-127">A implantação com as versões mencionadas acima do Configuration Manager é feita executando o script de integração nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bef28-127">Deployment with the above-mentioned versions of Configuration Manager is done by running the onboarding script on the devices.</span></span> <span data-ttu-id="bef28-128">Você pode acompanhar a implantação no Console do Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="bef28-128">You can track the deployment in the Configuration Manager Console.</span></span>

<span data-ttu-id="bef28-129">Se a implantação falhar, você poderá verificar a saída do script nos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bef28-129">If the deployment fails, you can check the output of the script on the devices.</span></span>

<span data-ttu-id="bef28-130">Se a integração for concluída com êxito,  mas os dispositivos não aparecerem na lista Dispositivos após uma hora, consulte [Solucionar](#troubleshoot-onboarding-issues-on-the-device) problemas de integração no dispositivo para obter erros adicionais que possam ocorrer.</span><span class="sxs-lookup"><span data-stu-id="bef28-130">If the onboarding completed successfully but the devices are not showing up in the **Devices list** after an hour, see [Troubleshoot onboarding issues on the device](#troubleshoot-onboarding-issues-on-the-device) for additional errors that might occur.</span></span>

### <a name="troubleshoot-onboarding-when-deploying-with-a-script"></a><span data-ttu-id="bef28-131">Solucionar problemas de integração ao implantar com um script</span><span class="sxs-lookup"><span data-stu-id="bef28-131">Troubleshoot onboarding when deploying with a script</span></span>

<span data-ttu-id="bef28-132">**Verifique o resultado do script no dispositivo:**</span><span class="sxs-lookup"><span data-stu-id="bef28-132">**Check the result of the script on the device:**</span></span>

1. <span data-ttu-id="bef28-133">Clique **em Iniciar,** digite **Visualizador de Eventos** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="bef28-133">Click **Start**, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="bef28-134">Vá para **o Windows Logs**  >  **Application**.</span><span class="sxs-lookup"><span data-stu-id="bef28-134">Go to **Windows Logs** > **Application**.</span></span>

3. <span data-ttu-id="bef28-135">Procure um evento da **fonte de eventos WDATPOnboarding.**</span><span class="sxs-lookup"><span data-stu-id="bef28-135">Look for an event from **WDATPOnboarding** event source.</span></span>

<span data-ttu-id="bef28-136">Se o script falhar e o evento for um erro, você poderá verificar a ID do evento na tabela a seguir para ajudá-lo a solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="bef28-136">If the script fails and the event is an error, you can check the event ID in the following table to help you troubleshoot the issue.</span></span>

> [!NOTE]
> <span data-ttu-id="bef28-137">As IDs de evento a seguir são específicas apenas para o script de integração.</span><span class="sxs-lookup"><span data-stu-id="bef28-137">The following event IDs are specific to the onboarding script only.</span></span>

<span data-ttu-id="bef28-138">ID de evento</span><span class="sxs-lookup"><span data-stu-id="bef28-138">Event ID</span></span> | <span data-ttu-id="bef28-139">Tipo de erro</span><span class="sxs-lookup"><span data-stu-id="bef28-139">Error Type</span></span> | <span data-ttu-id="bef28-140">Etapas de resolução</span><span class="sxs-lookup"><span data-stu-id="bef28-140">Resolution steps</span></span>
:---:|:---|:---
 `5` | <span data-ttu-id="bef28-141">Os dados de offboard foram encontrados, mas não puderam ser excluídos</span><span class="sxs-lookup"><span data-stu-id="bef28-141">Offboarding data was found but couldn't be deleted</span></span> | <span data-ttu-id="bef28-142">Verifique as permissões no Registro, especificamente</span><span class="sxs-lookup"><span data-stu-id="bef28-142">Check the permissions on the registry, specifically</span></span><br> <span data-ttu-id="bef28-143">`HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.</span><span class="sxs-lookup"><span data-stu-id="bef28-143">`HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.</span></span>
`10` | <span data-ttu-id="bef28-144">Os dados de integração não puderam ser gravados no Registro</span><span class="sxs-lookup"><span data-stu-id="bef28-144">Onboarding data couldn't be written to registry</span></span> |  <span data-ttu-id="bef28-145">Verifique as permissões no Registro, especificamente</span><span class="sxs-lookup"><span data-stu-id="bef28-145">Check the permissions on the registry, specifically</span></span><br> <span data-ttu-id="bef28-146">`HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.</span><span class="sxs-lookup"><span data-stu-id="bef28-146">`HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`.</span></span><br><span data-ttu-id="bef28-147">Verifique se o script foi executado como administrador.</span><span class="sxs-lookup"><span data-stu-id="bef28-147">Verify that the script has been run as an administrator.</span></span>
`15` |  <span data-ttu-id="bef28-148">Falha ao iniciar o serviço SENSE</span><span class="sxs-lookup"><span data-stu-id="bef28-148">Failed to start SENSE service</span></span> |<span data-ttu-id="bef28-149">Verifique a saúde do serviço ( `sc query sense` comando).</span><span class="sxs-lookup"><span data-stu-id="bef28-149">Check the service health (`sc query sense` command).</span></span> <span data-ttu-id="bef28-150">Certifique-se de que ele não está em um estado intermediário (*'Pending_Stopped'*, *'Pending_Running'*) e tente executar o script novamente (com direitos de administrador).</span><span class="sxs-lookup"><span data-stu-id="bef28-150">Make sure it's not in an intermediate state (*'Pending_Stopped'*, *'Pending_Running'*) and try to run the script again (with administrator rights).</span></span> <br> <br> <span data-ttu-id="bef28-151">Se o dispositivo estiver executando Windows 10, a versão 1607 e a execução do comando `sc query sense` `START_PENDING` retornarão , reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bef28-151">If the device is running Windows 10, version 1607 and running the command `sc query sense` returns `START_PENDING`, reboot the device.</span></span> <span data-ttu-id="bef28-152">Se a reinicialização do dispositivo não resolver o problema, atualize para KB4015217 e tente integração novamente.</span><span class="sxs-lookup"><span data-stu-id="bef28-152">If rebooting the device doesn't address the issue, upgrade to KB4015217 and try onboarding again.</span></span>
`15` | <span data-ttu-id="bef28-153">Falha ao iniciar o serviço SENSE</span><span class="sxs-lookup"><span data-stu-id="bef28-153">Failed to start SENSE service</span></span> | <span data-ttu-id="bef28-154">Se a mensagem do erro for: Erro do sistema 577 ou erro 1058, você precisará habilitar o driver ELAM do Microsoft Defender Antivírus, consulte Ensure that Microsoft Defender Antivírus is not [disabled by a policy](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy) for instructions.</span><span class="sxs-lookup"><span data-stu-id="bef28-154">If the message of the error is: System error 577  or error 1058 has occurred, you need to enable the Microsoft Defender Antivirus ELAM driver, see [Ensure that Microsoft Defender Antivirus is not disabled by a policy](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy) for instructions.</span></span>
`30` |  <span data-ttu-id="bef28-155">O script falhou ao aguardar que o serviço começasse a ser executado</span><span class="sxs-lookup"><span data-stu-id="bef28-155">The script failed to wait for the service to start running</span></span> | <span data-ttu-id="bef28-156">O serviço pode ter levado mais tempo para iniciar ou encontrou erros ao tentar iniciar.</span><span class="sxs-lookup"><span data-stu-id="bef28-156">The service could have taken more time to start or has encountered errors while trying to start.</span></span> <span data-ttu-id="bef28-157">Para obter mais informações sobre eventos e erros relacionados ao SENSE, consulte [Review events and errors using Event viewer](event-error-codes.md).</span><span class="sxs-lookup"><span data-stu-id="bef28-157">For more information on events and errors related to SENSE, see [Review events and errors using Event viewer](event-error-codes.md).</span></span>
`35` |  <span data-ttu-id="bef28-158">O script falhou ao encontrar o valor necessário do registro de status de integração</span><span class="sxs-lookup"><span data-stu-id="bef28-158">The script failed to find needed onboarding status registry value</span></span> | <span data-ttu-id="bef28-159">Quando o serviço SENSE é iniciado pela primeira vez, ele grava o status de integração no local do Registro</span><span class="sxs-lookup"><span data-stu-id="bef28-159">When the SENSE service starts for the first time, it writes onboarding status to the registry location</span></span><br><span data-ttu-id="bef28-160">`HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status`.</span><span class="sxs-lookup"><span data-stu-id="bef28-160">`HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection\Status`.</span></span><br> <span data-ttu-id="bef28-161">O script falhou ao encontrá-lo após vários segundos.</span><span class="sxs-lookup"><span data-stu-id="bef28-161">The script failed to find it after several seconds.</span></span> <span data-ttu-id="bef28-162">Você pode testá-lo manualmente e verificar se ele está lá.</span><span class="sxs-lookup"><span data-stu-id="bef28-162">You can manually test it and check if it's there.</span></span> <span data-ttu-id="bef28-163">Para obter mais informações sobre eventos e erros relacionados ao SENSE, consulte [Review events and errors using Event viewer](event-error-codes.md).</span><span class="sxs-lookup"><span data-stu-id="bef28-163">For more information on events and errors related to SENSE, see [Review events and errors using Event viewer](event-error-codes.md).</span></span>
`40` | <span data-ttu-id="bef28-164">O status de integração do serviço SENSE não está definido como **1**</span><span class="sxs-lookup"><span data-stu-id="bef28-164">SENSE service onboarding status is not set to **1**</span></span> | <span data-ttu-id="bef28-165">O serviço SENSE falhou ao fazer a integração adequadamente.</span><span class="sxs-lookup"><span data-stu-id="bef28-165">The SENSE service has failed to onboard properly.</span></span> <span data-ttu-id="bef28-166">Para obter mais informações sobre eventos e erros relacionados ao SENSE, consulte [Review events and errors using Event viewer](event-error-codes.md).</span><span class="sxs-lookup"><span data-stu-id="bef28-166">For more information on events and errors related to SENSE, see [Review events and errors using Event viewer](event-error-codes.md).</span></span>
`65` | <span data-ttu-id="bef28-167">Privilégios insuficientes</span><span class="sxs-lookup"><span data-stu-id="bef28-167">Insufficient privileges</span></span>| <span data-ttu-id="bef28-168">Execute o script novamente com privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="bef28-168">Run the script again with administrator privileges.</span></span>

### <a name="troubleshoot-onboarding-issues-using-microsoft-intune"></a><span data-ttu-id="bef28-169">Solucionar problemas de integração usando Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bef28-169">Troubleshoot onboarding issues using Microsoft Intune</span></span>

<span data-ttu-id="bef28-170">Você pode usar Microsoft Intune para verificar códigos de erro e tentar solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="bef28-170">You can use Microsoft Intune to check error codes and attempt to troubleshoot the cause of the issue.</span></span>

<span data-ttu-id="bef28-171">Se você configurou políticas no Intune e elas não são propagadas em dispositivos, talvez seja necessário configurar o registro MDM automático.</span><span class="sxs-lookup"><span data-stu-id="bef28-171">If you have configured policies in Intune and they are not propagated on devices, you might need to configure automatic MDM enrollment.</span></span>

<span data-ttu-id="bef28-172">Use as tabelas a seguir para entender as possíveis causas de problemas durante a integração:</span><span class="sxs-lookup"><span data-stu-id="bef28-172">Use the following tables to understand the possible causes of issues while onboarding:</span></span>

- <span data-ttu-id="bef28-173">Microsoft Intune códigos de erro e OMA-URIs tabela</span><span class="sxs-lookup"><span data-stu-id="bef28-173">Microsoft Intune error codes and OMA-URIs table</span></span>
- <span data-ttu-id="bef28-174">Problemas conhecidos com tabela de não conformidade</span><span class="sxs-lookup"><span data-stu-id="bef28-174">Known issues with non-compliance table</span></span>
- <span data-ttu-id="bef28-175">Tabela de logs de eventos do Gerenciamento de Dispositivo Móvel (MDM)</span><span class="sxs-lookup"><span data-stu-id="bef28-175">Mobile Device Management (MDM) event logs table</span></span>

<span data-ttu-id="bef28-176">Se nenhum dos logs de eventos e as etapas  de solução de problemas funcionarem, baixe o script Local da seção Gerenciamento de dispositivos do portal e execute-o em um prompt de comando elevado.</span><span class="sxs-lookup"><span data-stu-id="bef28-176">If none of the event logs and troubleshooting steps work, download the Local script from the **Device management** section of the portal, and run it in an elevated command prompt.</span></span>

#### <a name="microsoft-intune-error-codes-and-oma-uris"></a><span data-ttu-id="bef28-177">Microsoft Intune códigos de erro e OMA-URIs</span><span class="sxs-lookup"><span data-stu-id="bef28-177">Microsoft Intune error codes and OMA-URIs</span></span>

<span data-ttu-id="bef28-178">Hex de código de erro</span><span class="sxs-lookup"><span data-stu-id="bef28-178">Error Code Hex</span></span> | <span data-ttu-id="bef28-179">Dec de código de erro</span><span class="sxs-lookup"><span data-stu-id="bef28-179">Error Code Dec</span></span> | <span data-ttu-id="bef28-180">Descrição do erro</span><span class="sxs-lookup"><span data-stu-id="bef28-180">Error Description</span></span> | <span data-ttu-id="bef28-181">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="bef28-181">OMA-URI</span></span> | <span data-ttu-id="bef28-182">Possíveis etapas de causa e solução de problemas</span><span class="sxs-lookup"><span data-stu-id="bef28-182">Possible cause and troubleshooting steps</span></span>
:---:|:---|:---|:---|:---
<span data-ttu-id="bef28-183">0x87D1FDE8</span><span class="sxs-lookup"><span data-stu-id="bef28-183">0x87D1FDE8</span></span> | <span data-ttu-id="bef28-184">-2016281112</span><span class="sxs-lookup"><span data-stu-id="bef28-184">-2016281112</span></span> | <span data-ttu-id="bef28-185">Falha na correção</span><span class="sxs-lookup"><span data-stu-id="bef28-185">Remediation failed</span></span> | <span data-ttu-id="bef28-186">Integração</span><span class="sxs-lookup"><span data-stu-id="bef28-186">Onboarding</span></span> <br> <span data-ttu-id="bef28-187">Offboarding</span><span class="sxs-lookup"><span data-stu-id="bef28-187">Offboarding</span></span> | <span data-ttu-id="bef28-188">**Causa possível:** A integração ou o offboarding falharam em um blob errado: assinatura errada ou campos PreviousOrgIds ausentes.</span><span class="sxs-lookup"><span data-stu-id="bef28-188">**Possible cause:** Onboarding or offboarding failed on a wrong blob: wrong signature or missing PreviousOrgIds fields.</span></span> <br><br> <span data-ttu-id="bef28-189">**Etapas de solução de problemas:**</span><span class="sxs-lookup"><span data-stu-id="bef28-189">**Troubleshooting steps:**</span></span> <br> <span data-ttu-id="bef28-190">Verifique as IDs de evento na seção Exibir erros de integração do agente [no log de eventos do](#view-agent-onboarding-errors-in-the-device-event-log) dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bef28-190">Check the event IDs in the [View agent onboarding errors in the device event log](#view-agent-onboarding-errors-in-the-device-event-log) section.</span></span> <br><br> <span data-ttu-id="bef28-191">Verifique os logs de eventos MDM na tabela a seguir ou siga as instruções em [Diagnostic MDM failures in Windows 10](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10).</span><span class="sxs-lookup"><span data-stu-id="bef28-191">Check the MDM event logs in the following table or follow the instructions in [Diagnose MDM failures in Windows 10](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10).</span></span>
 | | | | <span data-ttu-id="bef28-192">Integração</span><span class="sxs-lookup"><span data-stu-id="bef28-192">Onboarding</span></span> <br> <span data-ttu-id="bef28-193">Offboarding</span><span class="sxs-lookup"><span data-stu-id="bef28-193">Offboarding</span></span> <br> <span data-ttu-id="bef28-194">SampleSharing</span><span class="sxs-lookup"><span data-stu-id="bef28-194">SampleSharing</span></span> | <span data-ttu-id="bef28-195">**Causa possível:** A chave do Registro da Política de Ponto de Extremidade do Microsoft Defender não existe ou o cliente do OMA DM não tem permissões para gravar nele.</span><span class="sxs-lookup"><span data-stu-id="bef28-195">**Possible cause:** Microsoft Defender for Endpoint Policy registry key does not exist or the OMA DM client doesn't have permissions to write to it.</span></span> <br><br> <span data-ttu-id="bef28-196">**Etapas de solução de problemas:** Verifique se a seguinte chave do Registro existe: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="bef28-196">**Troubleshooting steps:** Ensure that the following registry key exists: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span> <br> <br> <span data-ttu-id="bef28-197">Se ele não existir, abra um comando elevado e adicione a chave.</span><span class="sxs-lookup"><span data-stu-id="bef28-197">If it doesn't exist, open an elevated command and add the key.</span></span>
 | | | | <span data-ttu-id="bef28-198">SenseIsRunning</span><span class="sxs-lookup"><span data-stu-id="bef28-198">SenseIsRunning</span></span> <br> <span data-ttu-id="bef28-199">OnboardingState</span><span class="sxs-lookup"><span data-stu-id="bef28-199">OnboardingState</span></span> <br> <span data-ttu-id="bef28-200">OrgId</span><span class="sxs-lookup"><span data-stu-id="bef28-200">OrgId</span></span> |  <span data-ttu-id="bef28-201">**Causa possível:** Uma tentativa de correção por propriedade somente leitura.</span><span class="sxs-lookup"><span data-stu-id="bef28-201">**Possible cause:** An attempt to remediate by read-only property.</span></span> <span data-ttu-id="bef28-202">A integração falhou.</span><span class="sxs-lookup"><span data-stu-id="bef28-202">Onboarding has failed.</span></span> <br><br> <span data-ttu-id="bef28-203">**Etapas de solução de problemas:** Verifique as etapas de solução de problemas em [Solucionar problemas de integração no dispositivo](#troubleshoot-onboarding-issues-on-the-device).</span><span class="sxs-lookup"><span data-stu-id="bef28-203">**Troubleshooting steps:** Check the troubleshooting steps in [Troubleshoot onboarding issues on the device](#troubleshoot-onboarding-issues-on-the-device).</span></span> <br><br> <span data-ttu-id="bef28-204">Verifique os logs de eventos MDM na tabela a seguir ou siga as instruções em [Diagnostic MDM failures in Windows 10](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10).</span><span class="sxs-lookup"><span data-stu-id="bef28-204">Check the MDM event logs in the following table or follow the instructions in [Diagnose MDM failures in Windows 10](/windows/client-management/mdm/diagnose-mdm-failures-in-windows-10).</span></span>
 | | | | <span data-ttu-id="bef28-205">Todos</span><span class="sxs-lookup"><span data-stu-id="bef28-205">All</span></span> | <span data-ttu-id="bef28-206">**Causa possível:** Tente implantar o Microsoft Defender para Ponto de Extremidade em SKU/Platform sem suporte, especialmente SKU holográfico.</span><span class="sxs-lookup"><span data-stu-id="bef28-206">**Possible cause:** Attempt to deploy Microsoft Defender for Endpoint on non-supported SKU/Platform, particularly Holographic SKU.</span></span> <br><br> <span data-ttu-id="bef28-207">Plataformas com suporte no momento:</span><span class="sxs-lookup"><span data-stu-id="bef28-207">Currently supported platforms:</span></span><br> <span data-ttu-id="bef28-208">Enterprise, Educação e Professional.</span><span class="sxs-lookup"><span data-stu-id="bef28-208">Enterprise, Education, and Professional.</span></span><br> <span data-ttu-id="bef28-209">O servidor não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="bef28-209">Server is not supported.</span></span>
 <span data-ttu-id="bef28-210">0x87D101A9</span><span class="sxs-lookup"><span data-stu-id="bef28-210">0x87D101A9</span></span> | <span data-ttu-id="bef28-211">-2016345687</span><span class="sxs-lookup"><span data-stu-id="bef28-211">-2016345687</span></span> |<span data-ttu-id="bef28-212">SyncML(425): O comando solicitado falhou porque o remetente não tem permissões adequadas de controle de acesso (ACL) no destinatário.</span><span class="sxs-lookup"><span data-stu-id="bef28-212">SyncML(425): The requested command failed because the sender does not have adequate access control permissions (ACL) on the recipient.</span></span> | <span data-ttu-id="bef28-213">Todos</span><span class="sxs-lookup"><span data-stu-id="bef28-213">All</span></span> |  <span data-ttu-id="bef28-214">**Causa possível:** Tente implantar o Microsoft Defender para Ponto de Extremidade em SKU/Platform sem suporte, especialmente SKU holográfico.</span><span class="sxs-lookup"><span data-stu-id="bef28-214">**Possible cause:** Attempt to deploy Microsoft Defender for Endpoint on non-supported SKU/Platform, particularly Holographic SKU.</span></span><br><br> <span data-ttu-id="bef28-215">Plataformas com suporte no momento:</span><span class="sxs-lookup"><span data-stu-id="bef28-215">Currently supported platforms:</span></span><br>  <span data-ttu-id="bef28-216">Enterprise, Educação e Professional.</span><span class="sxs-lookup"><span data-stu-id="bef28-216">Enterprise, Education, and Professional.</span></span>

#### <a name="known-issues-with-non-compliance"></a><span data-ttu-id="bef28-217">Problemas conhecidos com falta de conformidade</span><span class="sxs-lookup"><span data-stu-id="bef28-217">Known issues with non-compliance</span></span>

<span data-ttu-id="bef28-218">A tabela a seguir fornece informações sobre problemas de não conformidade e como você pode resolver os problemas.</span><span class="sxs-lookup"><span data-stu-id="bef28-218">The following table provides information on issues with non-compliance and how you can address the issues.</span></span>

<span data-ttu-id="bef28-219">Caso</span><span class="sxs-lookup"><span data-stu-id="bef28-219">Case</span></span> | <span data-ttu-id="bef28-220">Sintomas</span><span class="sxs-lookup"><span data-stu-id="bef28-220">Symptoms</span></span> | <span data-ttu-id="bef28-221">Possíveis etapas de causa e solução de problemas</span><span class="sxs-lookup"><span data-stu-id="bef28-221">Possible cause and troubleshooting steps</span></span>
:---:|:---|:---
 `1` | <span data-ttu-id="bef28-222">O dispositivo é compatível com SenseIsRunning OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="bef28-222">Device is compliant by SenseIsRunning OMA-URI.</span></span> <span data-ttu-id="bef28-223">Mas não é compatível com OrgId, Onboarding e OnboardingState OMA-URIs.</span><span class="sxs-lookup"><span data-stu-id="bef28-223">But is non-compliant by OrgId, Onboarding and OnboardingState OMA-URIs.</span></span> | <span data-ttu-id="bef28-224">**Causa possível:** Verifique se o usuário passou o OOBE após Windows instalação ou atualização.</span><span class="sxs-lookup"><span data-stu-id="bef28-224">**Possible cause:** Check that user passed OOBE after Windows installation or upgrade.</span></span> <span data-ttu-id="bef28-225">Durante a integração OOBE não foi possível concluir, mas o SENSE já está em execução.</span><span class="sxs-lookup"><span data-stu-id="bef28-225">During OOBE onboarding couldn't be completed but SENSE is running already.</span></span><br><br> <span data-ttu-id="bef28-226">**Etapas de solução de problemas:** Aguarde a conclusão do OOBE.</span><span class="sxs-lookup"><span data-stu-id="bef28-226">**Troubleshooting steps:** Wait for OOBE to complete.</span></span>
 `2` |  <span data-ttu-id="bef28-227">O dispositivo é compatível com OrgId, Onboarding e OnboardingState OMA-URIs, mas não é compatível com SenseIsRunning OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="bef28-227">Device is compliant by OrgId, Onboarding, and OnboardingState OMA-URIs, but is non-compliant by SenseIsRunning OMA-URI.</span></span> |  <span data-ttu-id="bef28-228">**Causa possível:** O tipo de inicialização do serviço Sense é definido como "Início Atrasado".</span><span class="sxs-lookup"><span data-stu-id="bef28-228">**Possible cause:** Sense service's startup type is set as "Delayed Start".</span></span> <span data-ttu-id="bef28-229">Às vezes, isso faz com que Microsoft Intune servidor do Microsoft Intune reporte o dispositivo como não compatível com SenseIsRunning quando a sessão de DM ocorre no início do sistema.</span><span class="sxs-lookup"><span data-stu-id="bef28-229">Sometimes this causes the Microsoft Intune server to report the device as non-compliant by SenseIsRunning when DM session occurs on system start.</span></span> <br><br> <span data-ttu-id="bef28-230">**Etapas de solução de problemas:** O problema deve ser corrigido automaticamente dentro de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="bef28-230">**Troubleshooting steps:** The issue should automatically be fixed within 24 hours.</span></span>
 `3` | <span data-ttu-id="bef28-231">O dispositivo não é compatível</span><span class="sxs-lookup"><span data-stu-id="bef28-231">Device is non-compliant</span></span> | <span data-ttu-id="bef28-232">**Etapas de solução de problemas:** Verifique se as políticas de integração e de offboard não são implantadas no mesmo dispositivo ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="bef28-232">**Troubleshooting steps:** Ensure that Onboarding and Offboarding policies are not deployed on the same device at same time.</span></span>

#### <a name="mobile-device-management-mdm-event-logs"></a><span data-ttu-id="bef28-233">Logs de eventos do Gerenciamento de Dispositivo Móvel (MDM)</span><span class="sxs-lookup"><span data-stu-id="bef28-233">Mobile Device Management (MDM) event logs</span></span>

<span data-ttu-id="bef28-234">Exibir os logs de eventos MDM para solucionar problemas que podem surgir durante a integração:</span><span class="sxs-lookup"><span data-stu-id="bef28-234">View the MDM event logs to troubleshoot issues that might arise during onboarding:</span></span>

<span data-ttu-id="bef28-235">Nome do log: Microsoft\Windows\DeviceManagement-EnterpriseDiagnostics-Provider</span><span class="sxs-lookup"><span data-stu-id="bef28-235">Log name: Microsoft\Windows\DeviceManagement-EnterpriseDiagnostics-Provider</span></span>

<span data-ttu-id="bef28-236">Nome do canal: Admin</span><span class="sxs-lookup"><span data-stu-id="bef28-236">Channel name: Admin</span></span>

<span data-ttu-id="bef28-237">ID</span><span class="sxs-lookup"><span data-stu-id="bef28-237">ID</span></span> | <span data-ttu-id="bef28-238">Severity</span><span class="sxs-lookup"><span data-stu-id="bef28-238">Severity</span></span> | <span data-ttu-id="bef28-239">Descrição do Evento</span><span class="sxs-lookup"><span data-stu-id="bef28-239">Event description</span></span> | <span data-ttu-id="bef28-240">Etapas para a solução de problemas</span><span class="sxs-lookup"><span data-stu-id="bef28-240">Troubleshooting steps</span></span>
:---|:---|:---|:---
<span data-ttu-id="bef28-241">1819</span><span class="sxs-lookup"><span data-stu-id="bef28-241">1819</span></span> | <span data-ttu-id="bef28-242">Error</span><span class="sxs-lookup"><span data-stu-id="bef28-242">Error</span></span> | <span data-ttu-id="bef28-243">CSP do Microsoft Defender para Ponto de Extremidade: Falha ao definir o valor do nó.</span><span class="sxs-lookup"><span data-stu-id="bef28-243">Microsoft Defender for Endpoint CSP: Failed to Set Node's Value.</span></span> <span data-ttu-id="bef28-244">NodeId: (%1), TokenName: (%2), Resultado: (%3).</span><span class="sxs-lookup"><span data-stu-id="bef28-244">NodeId: (%1), TokenName: (%2), Result: (%3).</span></span> | <span data-ttu-id="bef28-245">Baixe a [Atualização Cumulativa para Windows 10, 1607](https://go.microsoft.com/fwlink/?linkid=829760).</span><span class="sxs-lookup"><span data-stu-id="bef28-245">Download the [Cumulative Update for Windows 10, 1607](https://go.microsoft.com/fwlink/?linkid=829760).</span></span>

## <a name="troubleshoot-onboarding-issues-on-the-device"></a><span data-ttu-id="bef28-246">Solucionar problemas de integração no dispositivo</span><span class="sxs-lookup"><span data-stu-id="bef28-246">Troubleshoot onboarding issues on the device</span></span>

<span data-ttu-id="bef28-247">Se as ferramentas de implantação usadas não indicarem um erro no processo de integração, mas os dispositivos ainda não aparecerem na lista de dispositivos em uma hora, consulte os tópicos de verificação a seguir para verificar se ocorreu um erro com o agente do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="bef28-247">If the deployment tools used does not indicate an error in the onboarding process, but devices are still not appearing in the devices list in an hour, go through the following verification topics to check if an error occurred with the Microsoft Defender for Endpoint agent.</span></span>

- [<span data-ttu-id="bef28-248">Exibir erros de integração do agente no log de eventos do dispositivo</span><span class="sxs-lookup"><span data-stu-id="bef28-248">View agent onboarding errors in the device event log</span></span>](#view-agent-onboarding-errors-in-the-device-event-log)
- [<span data-ttu-id="bef28-249">Verifique se o serviço de dados de diagnóstico está habilitado</span><span class="sxs-lookup"><span data-stu-id="bef28-249">Ensure the diagnostic data service is enabled</span></span>](#ensure-the-diagnostics-service-is-enabled)
- [<span data-ttu-id="bef28-250">Verifique se o serviço está definido para iniciar</span><span class="sxs-lookup"><span data-stu-id="bef28-250">Ensure the service is set to start</span></span>](#ensure-the-service-is-set-to-start)
- [<span data-ttu-id="bef28-251">Verifique se o dispositivo tem uma conexão com a Internet</span><span class="sxs-lookup"><span data-stu-id="bef28-251">Ensure the device has an Internet connection</span></span>](#ensure-the-device-has-an-internet-connection)
- [<span data-ttu-id="bef28-252">Verifique se Microsoft Defender Antivírus não está desabilitado por uma política</span><span class="sxs-lookup"><span data-stu-id="bef28-252">Ensure that Microsoft Defender Antivirus is not disabled by a policy</span></span>](#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)

### <a name="view-agent-onboarding-errors-in-the-device-event-log"></a><span data-ttu-id="bef28-253">Exibir erros de integração do agente no log de eventos do dispositivo</span><span class="sxs-lookup"><span data-stu-id="bef28-253">View agent onboarding errors in the device event log</span></span>

1. <span data-ttu-id="bef28-254">Clique **em Iniciar,** digite **Visualizador de Eventos** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="bef28-254">Click **Start**, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="bef28-255">No painel Visualizador de Eventos **(Local),** expanda **Logs de** Aplicativos e Serviços  >  **da Microsoft**  >  **Windows**  >  **SENSE**.</span><span class="sxs-lookup"><span data-stu-id="bef28-255">In the **Event Viewer (Local)** pane, expand **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bef28-256">SENSE é o nome interno usado para se referir ao sensor comportamental que alimenta o Microsoft Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="bef28-256">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="bef28-257">Selecione **Operacional** para carregar o log.</span><span class="sxs-lookup"><span data-stu-id="bef28-257">Select **Operational** to load the log.</span></span>

4. <span data-ttu-id="bef28-258">No painel **Ação,** clique em **Filtrar log atual.**</span><span class="sxs-lookup"><span data-stu-id="bef28-258">In the **Action** pane, click **Filter Current log**.</span></span>

5. <span data-ttu-id="bef28-259">Na guia **Filtro,** em **Nível de evento:** selecione **Crítico,** **Aviso** e **Erro** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="bef28-259">On the **Filter** tab, under **Event level:** select **Critical**, **Warning**, and **Error**, and click **OK**.</span></span>

   ![Imagem do filtro de log do Visualizador de Eventos](images/filter-log.png)

6. <span data-ttu-id="bef28-261">Os eventos que podem indicar problemas serão exibidos no **painel** Operacional.</span><span class="sxs-lookup"><span data-stu-id="bef28-261">Events which can indicate issues will appear in the **Operational** pane.</span></span> <span data-ttu-id="bef28-262">Você pode tentar solucionar problemas com base nas soluções na tabela a seguir:</span><span class="sxs-lookup"><span data-stu-id="bef28-262">You can attempt to troubleshoot them based on the solutions in the following table:</span></span>

<span data-ttu-id="bef28-263">ID do evento</span><span class="sxs-lookup"><span data-stu-id="bef28-263">Event ID</span></span> | <span data-ttu-id="bef28-264">Mensagem</span><span class="sxs-lookup"><span data-stu-id="bef28-264">Message</span></span> | <span data-ttu-id="bef28-265">Etapas de resolução</span><span class="sxs-lookup"><span data-stu-id="bef28-265">Resolution steps</span></span>
:---:|:---|:---
 `5` | <span data-ttu-id="bef28-266">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao se conectar ao servidor em _variável_</span><span class="sxs-lookup"><span data-stu-id="bef28-266">Microsoft Defender for Endpoint service failed to connect to the server at _variable_</span></span> | <span data-ttu-id="bef28-267">[Verifique se o dispositivo tem acesso à Internet.](#ensure-the-device-has-an-internet-connection)</span><span class="sxs-lookup"><span data-stu-id="bef28-267">[Ensure the device has Internet access](#ensure-the-device-has-an-internet-connection).</span></span>
 `6` | <span data-ttu-id="bef28-268">O serviço do Microsoft Defender para Ponto de Extremidade não está integrado e nenhum parâmetro de integração foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="bef28-268">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span> <span data-ttu-id="bef28-269">Código de falha: _variável_</span><span class="sxs-lookup"><span data-stu-id="bef28-269">Failure code: _variable_</span></span> | <span data-ttu-id="bef28-270">[Execute o script de integração novamente](configure-endpoints-script.md).</span><span class="sxs-lookup"><span data-stu-id="bef28-270">[Run the onboarding script again](configure-endpoints-script.md).</span></span>
 `7` | <span data-ttu-id="bef28-271">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao ler os parâmetros de integração.</span><span class="sxs-lookup"><span data-stu-id="bef28-271">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="bef28-272">Código de falha: _variável_</span><span class="sxs-lookup"><span data-stu-id="bef28-272">Failure code: _variable_</span></span> | <span data-ttu-id="bef28-273">[Verifique se o dispositivo tem acesso à Internet](#ensure-the-device-has-an-internet-connection)e execute todo o processo de integração novamente.</span><span class="sxs-lookup"><span data-stu-id="bef28-273">[Ensure the device has Internet access](#ensure-the-device-has-an-internet-connection), then run the entire onboarding process again.</span></span>
 `9` | <span data-ttu-id="bef28-274">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao alterar seu tipo de início.</span><span class="sxs-lookup"><span data-stu-id="bef28-274">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="bef28-275">Código de falha: variável</span><span class="sxs-lookup"><span data-stu-id="bef28-275">Failure code: variable</span></span> | <span data-ttu-id="bef28-276">Se o evento aconteceu durante a integração, reinicie e tente executar o script de integração.</span><span class="sxs-lookup"><span data-stu-id="bef28-276">If the event happened during onboarding, reboot and re-attempt running the onboarding script.</span></span> <span data-ttu-id="bef28-277">Para obter mais informações, consulte [Executar o script de integração novamente](configure-endpoints-script.md).</span><span class="sxs-lookup"><span data-stu-id="bef28-277">For more information, see [Run the onboarding script again](configure-endpoints-script.md).</span></span> <br><br><span data-ttu-id="bef28-278">Se o evento ocorreu durante o offboard, contate o suporte.</span><span class="sxs-lookup"><span data-stu-id="bef28-278">If the event happened during offboarding, contact support.</span></span>
`10` | <span data-ttu-id="bef28-279">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao manter as informações de integração.</span><span class="sxs-lookup"><span data-stu-id="bef28-279">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="bef28-280">Código de falha: variável</span><span class="sxs-lookup"><span data-stu-id="bef28-280">Failure code: variable</span></span> | <span data-ttu-id="bef28-281">Se o evento aconteceu durante a integração, tente executar o script de integração.</span><span class="sxs-lookup"><span data-stu-id="bef28-281">If the event happened during onboarding, re-attempt running the onboarding script.</span></span> <span data-ttu-id="bef28-282">Para obter mais informações, consulte [Executar o script de integração novamente](configure-endpoints-script.md).</span><span class="sxs-lookup"><span data-stu-id="bef28-282">For more information, see [Run the onboarding script again](configure-endpoints-script.md).</span></span> <br><br><span data-ttu-id="bef28-283">Se o problema persistir, contate o suporte.</span><span class="sxs-lookup"><span data-stu-id="bef28-283">If the problem persists, contact support.</span></span>
`15` | <span data-ttu-id="bef28-284">O Microsoft Defender para Ponto de Extremidade não pode iniciar o canal de comando com URL: _variável_</span><span class="sxs-lookup"><span data-stu-id="bef28-284">Microsoft Defender for Endpoint cannot start command channel with URL: _variable_</span></span> | <span data-ttu-id="bef28-285">[Verifique se o dispositivo tem acesso à Internet.](#ensure-the-device-has-an-internet-connection)</span><span class="sxs-lookup"><span data-stu-id="bef28-285">[Ensure the device has Internet access](#ensure-the-device-has-an-internet-connection).</span></span>
`17` | <span data-ttu-id="bef28-286">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao alterar o local do serviço Experiências do Usuário Conectado e Telemetria.</span><span class="sxs-lookup"><span data-stu-id="bef28-286">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="bef28-287">Código de falha: variável</span><span class="sxs-lookup"><span data-stu-id="bef28-287">Failure code: variable</span></span> | <span data-ttu-id="bef28-288">[Execute o script de integração novamente](configure-endpoints-script.md).</span><span class="sxs-lookup"><span data-stu-id="bef28-288">[Run the onboarding script again](configure-endpoints-script.md).</span></span> <span data-ttu-id="bef28-289">Se o problema persistir, contate o suporte.</span><span class="sxs-lookup"><span data-stu-id="bef28-289">If the problem persists, contact support.</span></span>
`25` | <span data-ttu-id="bef28-290">O serviço do Microsoft Defender para Ponto de Extremidade falhou ao redefinir o status de saúde no Registro.</span><span class="sxs-lookup"><span data-stu-id="bef28-290">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="bef28-291">Código de falha: _variável_</span><span class="sxs-lookup"><span data-stu-id="bef28-291">Failure code: _variable_</span></span> | <span data-ttu-id="bef28-292">Fale com o suporte.</span><span class="sxs-lookup"><span data-stu-id="bef28-292">Contact support.</span></span>
`27` | <span data-ttu-id="bef28-293">Falha ao habilitar o Microsoft Defender para o modo Ponto de Extremidade Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="bef28-293">Failed to enable Microsoft Defender for Endpoint mode in Windows Defender.</span></span> <span data-ttu-id="bef28-294">Falha no processo de integração.</span><span class="sxs-lookup"><span data-stu-id="bef28-294">Onboarding process failed.</span></span> <span data-ttu-id="bef28-295">Código de falha: variável</span><span class="sxs-lookup"><span data-stu-id="bef28-295">Failure code: variable</span></span> | <span data-ttu-id="bef28-296">Fale com o suporte.</span><span class="sxs-lookup"><span data-stu-id="bef28-296">Contact support.</span></span>
`29` | <span data-ttu-id="bef28-297">Falha ao ler os parâmetros de offboarding.</span><span class="sxs-lookup"><span data-stu-id="bef28-297">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="bef28-298">Tipo de erro: %1, Código de erro: %2, Descrição: %3</span><span class="sxs-lookup"><span data-stu-id="bef28-298">Error type: %1, Error code: %2, Description: %3</span></span> | <span data-ttu-id="bef28-299">Verifique se o dispositivo tem acesso à Internet e execute todo o processo de offboard novamente.</span><span class="sxs-lookup"><span data-stu-id="bef28-299">Ensure the device has Internet access, then run the entire offboarding process again.</span></span>
`30` | <span data-ttu-id="bef28-300">Falha ao desabilitar o modo $(build.sense.productDisplayName) no Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="bef28-300">Failed to disable $(build.sense.productDisplayName) mode in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="bef28-301">Código de falha: %1</span><span class="sxs-lookup"><span data-stu-id="bef28-301">Failure code: %1</span></span> | <span data-ttu-id="bef28-302">Fale com o suporte.</span><span class="sxs-lookup"><span data-stu-id="bef28-302">Contact support.</span></span>
`32` | <span data-ttu-id="bef28-303">$ serviço $(build.sense.productDisplayName) falhou ao solicitar para parar a si mesmo após o processo de offboard.</span><span class="sxs-lookup"><span data-stu-id="bef28-303">$(build.sense.productDisplayName) service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="bef28-304">Código de falha: %1</span><span class="sxs-lookup"><span data-stu-id="bef28-304">Failure code: %1</span></span> | <span data-ttu-id="bef28-305">Verifique se o tipo de início do serviço é manual e reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bef28-305">Verify that the service start type is manual and reboot the device.</span></span>
`55` | <span data-ttu-id="bef28-306">Falha ao criar o autologger ETW seguro.</span><span class="sxs-lookup"><span data-stu-id="bef28-306">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="bef28-307">Código de falha: %1</span><span class="sxs-lookup"><span data-stu-id="bef28-307">Failure code: %1</span></span> | <span data-ttu-id="bef28-308">Reinicie o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bef28-308">Reboot the device.</span></span>
`63` | <span data-ttu-id="bef28-309">Atualizando o tipo de início do serviço externo.</span><span class="sxs-lookup"><span data-stu-id="bef28-309">Updating the start type of external service.</span></span> <span data-ttu-id="bef28-310">Nome: %1, tipo de início real: %2, tipo de início esperado: %3, código de saída: %4</span><span class="sxs-lookup"><span data-stu-id="bef28-310">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span> | <span data-ttu-id="bef28-311">Identifique o que está causando alterações no tipo de início do serviço mencionado.</span><span class="sxs-lookup"><span data-stu-id="bef28-311">Identify what is causing changes in start type of mentioned service.</span></span> <span data-ttu-id="bef28-312">Se o código de saída não for 0, corrige o tipo de início manualmente para o tipo de início esperado.</span><span class="sxs-lookup"><span data-stu-id="bef28-312">If the exit code is not 0, fix the start type manually to expected start type.</span></span>
`64` | <span data-ttu-id="bef28-313">Iniciando o serviço externo interrompido.</span><span class="sxs-lookup"><span data-stu-id="bef28-313">Starting stopped external service.</span></span> <span data-ttu-id="bef28-314">Nome: %1, código de saída: %2</span><span class="sxs-lookup"><span data-stu-id="bef28-314">Name: %1, exit code: %2</span></span> | <span data-ttu-id="bef28-315">Contate o suporte se o evento continuar a aparecer.</span><span class="sxs-lookup"><span data-stu-id="bef28-315">Contact support if the event keeps re-appearing.</span></span>
`68` | <span data-ttu-id="bef28-316">O tipo de início do serviço é inesperado.</span><span class="sxs-lookup"><span data-stu-id="bef28-316">The start type of the service is unexpected.</span></span> <span data-ttu-id="bef28-317">Nome do serviço: %1, tipo de início real: %2, tipo de início esperado: %3</span><span class="sxs-lookup"><span data-stu-id="bef28-317">Service name: %1, actual start type: %2, expected start type: %3</span></span> | <span data-ttu-id="bef28-318">Identifique o que está causando alterações no tipo de início.</span><span class="sxs-lookup"><span data-stu-id="bef28-318">Identify what is causing changes in start type.</span></span> <span data-ttu-id="bef28-319">Corrigir o tipo de início de serviço mencionado.</span><span class="sxs-lookup"><span data-stu-id="bef28-319">Fix mentioned service start type.</span></span>
`69` | <span data-ttu-id="bef28-320">O serviço é interrompido.</span><span class="sxs-lookup"><span data-stu-id="bef28-320">The service is stopped.</span></span> <span data-ttu-id="bef28-321">Nome do serviço: %1</span><span class="sxs-lookup"><span data-stu-id="bef28-321">Service name: %1</span></span> | <span data-ttu-id="bef28-322">Inicie o serviço mencionado.</span><span class="sxs-lookup"><span data-stu-id="bef28-322">Start the mentioned service.</span></span> <span data-ttu-id="bef28-323">Contate o suporte se persistir.</span><span class="sxs-lookup"><span data-stu-id="bef28-323">Contact support if persists.</span></span>

<br />

<span data-ttu-id="bef28-324">Há componentes adicionais no dispositivo de que o agente do Microsoft Defender for Endpoint depende para funcionar corretamente.</span><span class="sxs-lookup"><span data-stu-id="bef28-324">There are additional components on the device that the Microsoft Defender for Endpoint agent depends on to function properly.</span></span> <span data-ttu-id="bef28-325">Se não houver erros relacionados à integração no log de eventos do agente do Microsoft Defender for Endpoint, prossiga com as etapas a seguir para garantir que os componentes adicionais sejam configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="bef28-325">If there are no onboarding related errors in the Microsoft Defender for Endpoint agent event log, proceed with the following steps to ensure that the additional components are configured correctly.</span></span>

<span id="ensure-the-diagnostics-service-is-enabled" />

### <a name="ensure-the-diagnostic-data-service-is-enabled"></a><span data-ttu-id="bef28-326">Verifique se o serviço de dados de diagnóstico está habilitado</span><span class="sxs-lookup"><span data-stu-id="bef28-326">Ensure the diagnostic data service is enabled</span></span>

<span data-ttu-id="bef28-327">Se os dispositivos não estão relatando corretamente, talvez seja necessário verificar se o serviço Windows 10 de dados de diagnóstico está definido para iniciar automaticamente e está sendo executado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bef28-327">If the devices aren't reporting correctly, you might need to check that the Windows 10 diagnostic data service is set to automatically start and is running on the device.</span></span> <span data-ttu-id="bef28-328">O serviço pode ter sido desabilitado por outros programas ou alterações na configuração do usuário.</span><span class="sxs-lookup"><span data-stu-id="bef28-328">The service might have been disabled by other programs or user configuration changes.</span></span>

<span data-ttu-id="bef28-329">Primeiro, você deve verificar se o serviço está definido para ser iniciado automaticamente quando o Windows for iniciado, em seguida, verifique se o serviço está em execução no momento (e inicie-o se não estiver).</span><span class="sxs-lookup"><span data-stu-id="bef28-329">First, you should check that the service is set to start automatically when Windows starts, then you should check that the service is currently running (and start it if it isn't).</span></span>

### <a name="ensure-the-service-is-set-to-start"></a><span data-ttu-id="bef28-330">Verifique se o serviço está definido para iniciar</span><span class="sxs-lookup"><span data-stu-id="bef28-330">Ensure the service is set to start</span></span>

<span data-ttu-id="bef28-331">**Use a linha de comando para verificar o tipo Windows 10 de inicialização** do serviço de dados de diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="bef28-331">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="bef28-332">Abra um prompt de linha de comando elevada no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="bef28-332">Open an elevated command-line prompt on the device:</span></span>

   <span data-ttu-id="bef28-333">a.</span><span class="sxs-lookup"><span data-stu-id="bef28-333">a.</span></span> <span data-ttu-id="bef28-334">Clique **em Iniciar,** **digite cmd** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="bef28-334">Click **Start**, type **cmd**, and press **Enter**.</span></span>

   <span data-ttu-id="bef28-335">b.</span><span class="sxs-lookup"><span data-stu-id="bef28-335">b.</span></span> <span data-ttu-id="bef28-336">Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="bef28-336">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="bef28-337">Insira o seguinte comando e pressione **Enter**:</span><span class="sxs-lookup"><span data-stu-id="bef28-337">Enter the following command, and press **Enter**:</span></span>

   ```text
   sc qc diagtrack
   ```

   <span data-ttu-id="bef28-338">Se o serviço estiver habilitado, o resultado deverá ter a seguinte captura de tela:</span><span class="sxs-lookup"><span data-stu-id="bef28-338">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![Resultado do comando de consulta sc para diagtrack](images/windefatp-sc-qc-diagtrack.png)

   <span data-ttu-id="bef28-340">Se o `START_TYPE` não estiver definido como , você precisará definir o serviço para iniciar `AUTO_START` automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bef28-340">If the `START_TYPE` is not set to `AUTO_START`, then you'll need to set the service to automatically start.</span></span>

<span data-ttu-id="bef28-341">**Use a linha de comando para definir o serviço Windows 10 de dados de diagnóstico para iniciar automaticamente:**</span><span class="sxs-lookup"><span data-stu-id="bef28-341">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1. <span data-ttu-id="bef28-342">Abra um prompt de linha de comando elevada no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="bef28-342">Open an elevated command-line prompt on the device:</span></span>

   <span data-ttu-id="bef28-343">a.</span><span class="sxs-lookup"><span data-stu-id="bef28-343">a.</span></span> <span data-ttu-id="bef28-344">Clique **em Iniciar,** **digite cmd** e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="bef28-344">Click **Start**, type **cmd**, and press **Enter**.</span></span>

   <span data-ttu-id="bef28-345">b.</span><span class="sxs-lookup"><span data-stu-id="bef28-345">b.</span></span> <span data-ttu-id="bef28-346">Clique com o botão direito do mouse em **Prompt de Comando** e selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="bef28-346">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="bef28-347">Insira o seguinte comando e pressione **Enter**:</span><span class="sxs-lookup"><span data-stu-id="bef28-347">Enter the following command, and press **Enter**:</span></span>

   ```text
   sc config diagtrack start=auto
   ```

3. <span data-ttu-id="bef28-348">Uma mensagem de sucesso é exibida.</span><span class="sxs-lookup"><span data-stu-id="bef28-348">A success message is displayed.</span></span> <span data-ttu-id="bef28-349">Verifique a alteração inserindo o seguinte comando e pressione **Enter**:</span><span class="sxs-lookup"><span data-stu-id="bef28-349">Verify the change by entering the following command, and press **Enter**:</span></span>

   ```text
   sc qc diagtrack
   ```

4. <span data-ttu-id="bef28-350">Inicie o serviço.</span><span class="sxs-lookup"><span data-stu-id="bef28-350">Start the service.</span></span>

   <span data-ttu-id="bef28-351">a.</span><span class="sxs-lookup"><span data-stu-id="bef28-351">a.</span></span> <span data-ttu-id="bef28-352">No prompt de comando, digite o seguinte comando e pressione **Enter**:</span><span class="sxs-lookup"><span data-stu-id="bef28-352">In the command prompt, type the following command and press **Enter**:</span></span>

   ```text
   sc start diagtrack
   ```

### <a name="ensure-the-device-has-an-internet-connection"></a><span data-ttu-id="bef28-353">Verifique se o dispositivo tem uma conexão com a Internet</span><span class="sxs-lookup"><span data-stu-id="bef28-353">Ensure the device has an Internet connection</span></span>

<span data-ttu-id="bef28-354">O sensor Microsoft Defender ATP requer o Microsoft Windows HTTP (WinHTTP) para relatar os dados do sensor e se comunicar com o serviço Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="bef28-354">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span>

<span data-ttu-id="bef28-355">O WinHTTP é independente das configurações de proxy de navegação na Internet e de outros aplicativos de contexto de usuário e deve ser capaz de detectar os servidores proxy que estão disponíveis em seu ambiente específico.</span><span class="sxs-lookup"><span data-stu-id="bef28-355">WinHTTP is independent of the Internet browsing proxy settings and other user context applications and must be able to detect the proxy servers that are available in your particular environment.</span></span>

<span data-ttu-id="bef28-356">Para garantir que o sensor tenha conectividade de serviço, siga as etapas descritas no tópico Verificar a conectividade do cliente com o [Microsoft Defender para URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls) de serviço de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="bef28-356">To ensure that sensor has service connectivity, follow the steps described in the [Verify client connectivity to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls) topic.</span></span>

<span data-ttu-id="bef28-357">Se a verificação falhar e seu ambiente estiver usando um proxy para se conectar à Internet, siga as etapas descritas em [Configure proxy and Internet connectivity settings](configure-proxy-internet.md) topic.</span><span class="sxs-lookup"><span data-stu-id="bef28-357">If the verification fails and your environment is using a proxy to connect to the Internet, then follow the steps described in [Configure proxy and Internet connectivity settings](configure-proxy-internet.md) topic.</span></span>

### <a name="ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy"></a><span data-ttu-id="bef28-358">Verifique se Microsoft Defender Antivírus não está desabilitado por uma política</span><span class="sxs-lookup"><span data-stu-id="bef28-358">Ensure that Microsoft Defender Antivirus is not disabled by a policy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bef28-359">O seguinte só se aplica  a dispositivos que ainda não receberam a atualização de agosto de 2020 (versão 4.18.2007.8) para Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="bef28-359">The following only applies to devices that have **not** yet received the August 2020 (version 4.18.2007.8) update to Microsoft Defender Antivirus.</span></span>
>
> <span data-ttu-id="bef28-360">A atualização garante que o Microsoft Defender Antivírus não possa ser desligado em dispositivos cliente por meio da política do sistema.</span><span class="sxs-lookup"><span data-stu-id="bef28-360">The update ensures that Microsoft Defender Antivirus cannot be turned off on client devices via system policy.</span></span>

<span data-ttu-id="bef28-361">**Problema**: o serviço do Microsoft Defender para Ponto de Extremidade não começa após a integração.</span><span class="sxs-lookup"><span data-stu-id="bef28-361">**Problem**: The Microsoft Defender for Endpoint service does not start after onboarding.</span></span>

<span data-ttu-id="bef28-362">**Sintoma**: a integração é concluída com êxito, mas você vê o erro 577 ou o erro 1058 ao tentar iniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="bef28-362">**Symptom**: Onboarding successfully completes, but you see error 577 or error 1058 when trying to start the service.</span></span>

<span data-ttu-id="bef28-363">**Solução**: se seus dispositivos estão executando um cliente antimalware de terceiros, o agente do Microsoft Defender for Endpoint precisa do driver ELAM (Antimalware de Início Antecipado) para ser habilitado.</span><span class="sxs-lookup"><span data-stu-id="bef28-363">**Solution**: If your devices are running a third-party antimalware client, the Microsoft Defender for Endpoint agent needs the Early Launch Antimalware (ELAM) driver to be enabled.</span></span> <span data-ttu-id="bef28-364">Você deve garantir que ele não está desligado por uma política do sistema.</span><span class="sxs-lookup"><span data-stu-id="bef28-364">You must ensure that it's not turned off by a system policy.</span></span>

- <span data-ttu-id="bef28-365">Dependendo da ferramenta que você usa para implementar políticas, você precisará verificar se as seguintes políticas Windows Defender estão limpas:</span><span class="sxs-lookup"><span data-stu-id="bef28-365">Depending on the tool that you use to implement policies, you'll need to verify that the following Windows Defender policies are cleared:</span></span>

  - <span data-ttu-id="bef28-366">DisableAntiSpyware</span><span class="sxs-lookup"><span data-stu-id="bef28-366">DisableAntiSpyware</span></span>
  - <span data-ttu-id="bef28-367">DisableAntiVirus</span><span class="sxs-lookup"><span data-stu-id="bef28-367">DisableAntiVirus</span></span>

  <span data-ttu-id="bef28-368">Por exemplo, na Política de Grupo, não deve haver entradas como os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="bef28-368">For example, in Group Policy there should be no entries such as the following values:</span></span>

  - `<Key Path="SOFTWARE\Policies\Microsoft\Windows Defender"><KeyValue Value="0" ValueKind="DWord" Name="DisableAntiSpyware"/></Key>`
  - `<Key Path="SOFTWARE\Policies\Microsoft\Windows Defender"><KeyValue Value="0" ValueKind="DWord" Name="DisableAntiVirus"/></Key>`

> [!IMPORTANT]
> <span data-ttu-id="bef28-369">A configuração é descontinuada e será ignorada em todos os dispositivos clientes, a partir da atualização de agosto de `disableAntiSpyware` 2020 (versão 4.18.2007.8) para Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="bef28-369">The `disableAntiSpyware` setting is discontinued and will be ignored on all client devices, as of the August 2020 (version 4.18.2007.8) update to Microsoft Defender Antivirus.</span></span>

- <span data-ttu-id="bef28-370">Depois de limpar a política, execute as etapas de integração novamente.</span><span class="sxs-lookup"><span data-stu-id="bef28-370">After clearing the policy, run the onboarding steps again.</span></span>

- <span data-ttu-id="bef28-371">Você também pode verificar os valores de chave do Registro anterior para verificar se a política está desabilitada, abrindo a chave do Registro `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` .</span><span class="sxs-lookup"><span data-stu-id="bef28-371">You can also check the previous registry key values to verify that the policy is disabled, by opening the registry key `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender`.</span></span>

    ![Imagem da chave do Registro para Microsoft Defender Antivírus](images/atp-disableantispyware-regkey.png)

   > [!NOTE]
   > <span data-ttu-id="bef28-373">Todos os Windows Defender (wdboot, wdfilter, wdnisdrv, wdnissvc e windefend) devem estar em seu estado padrão.</span><span class="sxs-lookup"><span data-stu-id="bef28-373">All Windows Defender services (wdboot, wdfilter, wdnisdrv, wdnissvc, and windefend) should be in their default state.</span></span> <span data-ttu-id="bef28-374">Alterar a inicialização desses serviços não é compatível e pode forçar você a reimagear seu sistema.</span><span class="sxs-lookup"><span data-stu-id="bef28-374">Changing the startup of these services is unsupported and may force you to reimage your system.</span></span>
   >
   > <span data-ttu-id="bef28-375">Exemplo de configurações padrão para WdBoot e WdFilter:</span><span class="sxs-lookup"><span data-stu-id="bef28-375">Example default configurations for WdBoot and WdFilter:</span></span>
   > - `<Key Path="SYSTEM\CurrentControlSet\Services\WdBoot"><KeyValue Value="0" ValueKind="DWord" Name="Start"/></Key>`
   > - `<Key Path="SYSTEM\CurrentControlSet\Services\WdFilter"><KeyValue Value="0" ValueKind="DWord" Name="Start"/></Key>`

## <a name="troubleshoot-onboarding-issues-on-a-server"></a><span data-ttu-id="bef28-376">Solucionar problemas de integração em um servidor</span><span class="sxs-lookup"><span data-stu-id="bef28-376">Troubleshoot onboarding issues on a server</span></span>

<span data-ttu-id="bef28-377">Se você encontrar problemas durante a integração de um servidor, vá pelas etapas de verificação a seguir para resolver possíveis problemas.</span><span class="sxs-lookup"><span data-stu-id="bef28-377">If you encounter issues while onboarding a server, go through the following verification steps to address possible issues.</span></span>

- [<span data-ttu-id="bef28-378">Verifique se Microsoft Monitoring Agent (MMA) está instalado e configurado para relatar dados do sensor ao serviço</span><span class="sxs-lookup"><span data-stu-id="bef28-378">Ensure Microsoft Monitoring Agent (MMA) is installed and configured to report sensor data to the service</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="bef28-379">Verifique se o proxy do servidor e as configurações de conectividade com a Internet estão configuradas corretamente</span><span class="sxs-lookup"><span data-stu-id="bef28-379">Ensure that the server proxy and Internet connectivity settings are configured properly</span></span>](configure-server-endpoints.md)

<span data-ttu-id="bef28-380">Você também pode precisar verificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bef28-380">You might also need to check the following:</span></span>

- <span data-ttu-id="bef28-381">Verifique se há um Serviço do Microsoft Defender para Ponto de Extremidade em execução na guia **Processos** no **Gerenciador de Tarefas.**</span><span class="sxs-lookup"><span data-stu-id="bef28-381">Check that there is a Microsoft Defender for Endpoint Service running in the **Processes** tab in **Task Manager**.</span></span> <span data-ttu-id="bef28-382">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bef28-382">For example:</span></span>

    ![Imagem de exibição de processo com o Microsoft Defender para Serviço de Ponto de Extremidade em execução](images/atp-task-manager.png)

- <span data-ttu-id="bef28-384">Verifique **o Gerenciador de** Operações de Logs de Aplicativos e Serviços do Visualizador de Eventos para ver se há algum  >    >   erro.</span><span class="sxs-lookup"><span data-stu-id="bef28-384">Check **Event Viewer** > **Applications and Services Logs** > **Operation Manager** to see if there are any errors.</span></span>

- <span data-ttu-id="bef28-385">Em **Serviços,** verifique se o **Microsoft Monitoring Agent** está sendo executado no servidor.</span><span class="sxs-lookup"><span data-stu-id="bef28-385">In **Services**, check if the **Microsoft Monitoring Agent** is running on the server.</span></span> <span data-ttu-id="bef28-386">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="bef28-386">For example,</span></span>

    ![Imagem dos Serviços](images/atp-services.png)

- <span data-ttu-id="bef28-388">Em **Microsoft Monitoring Agent**  >  **Análise de Log do Azure (OMS),** verifique os Espaços de Trabalho e verifique se o status está em execução.</span><span class="sxs-lookup"><span data-stu-id="bef28-388">In **Microsoft Monitoring Agent** > **Azure Log Analytics (OMS)**, check the Workspaces and verify that the status is running.</span></span>

    ![Imagem de Microsoft Monitoring Agent Propriedades](images/atp-mma-properties.png)

- <span data-ttu-id="bef28-390">Verifique se os dispositivos são refletidos na lista **Dispositivos** no portal.</span><span class="sxs-lookup"><span data-stu-id="bef28-390">Check to see that devices are reflected in the **Devices list** in the portal.</span></span>

## <a name="confirming-onboarding-of-newly-built-devices"></a><span data-ttu-id="bef28-391">Confirmando a integração de dispositivos recém-construídos</span><span class="sxs-lookup"><span data-stu-id="bef28-391">Confirming onboarding of newly built devices</span></span>

<span data-ttu-id="bef28-392">Pode haver instâncias em que a integração é implantada em um dispositivo recém-criado, mas não concluída.</span><span class="sxs-lookup"><span data-stu-id="bef28-392">There may be instances when onboarding is deployed on a newly built device but not completed.</span></span>

<span data-ttu-id="bef28-393">As etapas a seguir fornecem orientações para o seguinte cenário:</span><span class="sxs-lookup"><span data-stu-id="bef28-393">The steps below provide guidance for the following scenario:</span></span>

- <span data-ttu-id="bef28-394">O pacote de integração é implantado em dispositivos recém-construídos</span><span class="sxs-lookup"><span data-stu-id="bef28-394">Onboarding package is deployed to newly built devices</span></span>
- <span data-ttu-id="bef28-395">O sensor não inicia porque a experiência inicial (OOBE) ou o primeiro logon do usuário não foi concluído</span><span class="sxs-lookup"><span data-stu-id="bef28-395">Sensor does not start because the Out-of-box experience (OOBE) or first user logon has not been completed</span></span>
- <span data-ttu-id="bef28-396">O dispositivo é desligado ou reiniciado antes que o usuário final execute um primeiro logon</span><span class="sxs-lookup"><span data-stu-id="bef28-396">Device is turned off or restarted before the end user performs a first logon</span></span>
- <span data-ttu-id="bef28-397">Nesse cenário, o serviço SENSE não iniciará automaticamente, mesmo que o pacote de integração tenha sido implantado</span><span class="sxs-lookup"><span data-stu-id="bef28-397">In this scenario, the SENSE service will not start automatically even though onboarding package was deployed</span></span>

> [!NOTE]
> <span data-ttu-id="bef28-398">As etapas a seguir só são relevantes ao usar Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="bef28-398">The following steps are only relevant when using Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="bef28-399">Para obter mais detalhes sobre a integração usando Microsoft Endpoint Configuration Manager, consulte [Microsoft Defender for Endpoint](/mem/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="bef28-399">For more details about onboarding using Microsoft Endpoint Configuration Manager, see [Microsoft Defender for Endpoint](/mem/configmgr/protect/deploy-use/windows-defender-advanced-threat-protection).</span></span>

1. <span data-ttu-id="bef28-400">Crie um aplicativo em Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="bef28-400">Create an application in Microsoft Endpoint Configuration Manager.</span></span>

    ![Imagem de Microsoft Endpoint Configuration Manager configuração1](images/mecm-1.png)

2. <span data-ttu-id="bef28-402">Selecione **Especificar manualmente as informações do aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="bef28-402">Select **Manually specify the application information**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 2](images/mecm-2.png)

3. <span data-ttu-id="bef28-404">Especifique informações sobre o aplicativo e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="bef28-404">Specify information about the application, then select **Next**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 3](images/mecm-3.png)

4. <span data-ttu-id="bef28-406">Especifique informações sobre o centro de software e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="bef28-406">Specify information about the software center, then select **Next**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 4](images/mecm-4.png)

5. <span data-ttu-id="bef28-408">Em **Tipos de implantação,** **selecione Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="bef28-408">In **Deployment types** select **Add**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 5](images/mecm-5.png)

6. <span data-ttu-id="bef28-410">Selecione **Especificar manualmente as informações de tipo de implantação** e, em seguida, **selecione Next**.</span><span class="sxs-lookup"><span data-stu-id="bef28-410">Select **Manually specify the deployment type information**, then select **Next**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 6](images/mecm-6.png)

7. <span data-ttu-id="bef28-412">Especifique informações sobre o tipo de implantação e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="bef28-412">Specify information about the deployment type, then select **Next**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 7](images/mecm-7.png)

8. <span data-ttu-id="bef28-414">Em **Programa de** Instalação de  >  **Conteúdo,** especifique o comando: `net start sense` .</span><span class="sxs-lookup"><span data-stu-id="bef28-414">In **Content** > **Installation program** specify the command: `net start sense`.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 8](images/mecm-8.png)

9. <span data-ttu-id="bef28-416">No **método Detection,** selecione **Configurar regras para detectar a** presença desse tipo de implantação e, em seguida, selecione Adicionar **Cláusula**.</span><span class="sxs-lookup"><span data-stu-id="bef28-416">In **Detection method**, select **Configure rules to detect the presence of this deployment type**, then select **Add Clause**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 9](images/mecm-9.png)

10. <span data-ttu-id="bef28-418">Especifique os seguintes detalhes da regra de detecção e selecione **OK**:</span><span class="sxs-lookup"><span data-stu-id="bef28-418">Specify the following detection rule details, then select **OK**:</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 10](images/mecm-10.png)

11. <span data-ttu-id="bef28-420">No **método Detection,** selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="bef28-420">In **Detection method** select **Next**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 11](images/mecm-11.png)

12. <span data-ttu-id="bef28-422">Na **Experiência do Usuário,** especifique as seguintes informações e selecione **Next**:</span><span class="sxs-lookup"><span data-stu-id="bef28-422">In **User Experience**, specify the following information, then select **Next**:</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 12](images/mecm-12.png)

13. <span data-ttu-id="bef28-424">Em **Requisitos,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="bef28-424">In **Requirements**, select **Next**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 13](images/mecm-13.png)

14. <span data-ttu-id="bef28-426">Em **Dependências,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="bef28-426">In **Dependencies**, select **Next**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 14](images/mecm-14.png)

15. <span data-ttu-id="bef28-428">Em **Resumo,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="bef28-428">In **Summary**, select **Next**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 15](images/mecm-15.png)

16. <span data-ttu-id="bef28-430">Em **Conclusão,** selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="bef28-430">In **Completion**, select **Close**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 16](images/mecm-16.png)

17. <span data-ttu-id="bef28-432">Em **Tipos de implantação,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="bef28-432">In **Deployment types**, select **Next**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager configuração17](images/mecm-17.png)

18. <span data-ttu-id="bef28-434">Em **Resumo,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="bef28-434">In **Summary**, select **Next**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 18](images/mecm-18.png)

    <span data-ttu-id="bef28-436">Em seguida, o status é exibido: ![ Imagem da Microsoft Endpoint Configuration Manager configuração19](images/mecm-19.png)</span><span class="sxs-lookup"><span data-stu-id="bef28-436">The status is then displayed: ![Image of Microsoft Endpoint Configuration Manager configuration19](images/mecm-19.png)</span></span>

19. <span data-ttu-id="bef28-437">Em **Conclusão,** selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="bef28-437">In **Completion**, select **Close**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 20](images/mecm-20.png)

20. <span data-ttu-id="bef28-439">Agora você pode implantar o aplicativo clicando com o botão direito do mouse no aplicativo e selecionando **Implantar**.</span><span class="sxs-lookup"><span data-stu-id="bef28-439">You can now deploy the application by right-clicking the app and selecting **Deploy**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 21](images/mecm-21.png)

21. <span data-ttu-id="bef28-441">Em **Geral,** **selecione Distribuir automaticamente conteúdo para dependências** e **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="bef28-441">In **General** select **Automatically distribute content for dependencies** and **Browse**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 22](images/mecm-22.png)

22. <span data-ttu-id="bef28-443">Em **Conteúdo,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="bef28-443">In **Content** select **Next**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 23](images/mecm-23.png)

23. <span data-ttu-id="bef28-445">Em **Configurações de implantação,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="bef28-445">In **Deployment settings**, select **Next**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 24](images/mecm-24.png)

24. <span data-ttu-id="bef28-447">Em **Agendamento** selecione Assim que possível após o horário **disponível,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="bef28-447">In **Scheduling** select **As soon as possible after the available time**, then select **Next**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 25](images/mecm-25.png)

25. <span data-ttu-id="bef28-449">Na **experiência do usuário,** selecione Confirma as alterações no prazo ou durante uma janela de **manutenção (requer reinicializações)** e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="bef28-449">In **User experience**, select **Commit changes at deadline or during a maintenance window (requires restarts)**, then select **Next**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 26](images/mecm-26.png)

26. <span data-ttu-id="bef28-451">Em **Alertas,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="bef28-451">In **Alerts** select **Next**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 27](images/mecm-27.png)

27. <span data-ttu-id="bef28-453">Em **Resumo,** selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="bef28-453">In **Summary**, select **Next**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 28](images/mecm-28.png)

    <span data-ttu-id="bef28-455">Em seguida, o status é exibido ![ Image of Microsoft Endpoint Configuration Manager configuration29](images/mecm-29.png)</span><span class="sxs-lookup"><span data-stu-id="bef28-455">The status is then displayed ![Image of Microsoft Endpoint Configuration Manager configuration29](images/mecm-29.png)</span></span>

28. <span data-ttu-id="bef28-456">Em **Conclusão,** selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="bef28-456">In **Completion**, select **Close**.</span></span>

    ![Imagem da Microsoft Endpoint Configuration Manager 30](images/mecm-30.png)


## <a name="related-topics"></a><span data-ttu-id="bef28-458">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="bef28-458">Related topics</span></span>

- [<span data-ttu-id="bef28-459">Solucionar problemas do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="bef28-459">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-mdatp.md)
- [<span data-ttu-id="bef28-460">Integração de dispositivos</span><span class="sxs-lookup"><span data-stu-id="bef28-460">Onboard devices</span></span>](onboard-configure.md)
- [<span data-ttu-id="bef28-461">Definir as configurações de proxy de dispositivo e conectividade com a Internet</span><span class="sxs-lookup"><span data-stu-id="bef28-461">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
