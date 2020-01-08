---
title: Monitoramento e relatórios de dispositivos no centro de segurança do Microsoft 365
description: Descreve como você pode manter seus dispositivos seguros, atualizados e identificar possíveis ameaças em sua organização
keywords: segurança, malware, Microsoft 365, M365, central de segurança, monitor, relatório, dispositivos
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 37e273a3e01177dec23b668ecb8a6301011ab88d
ms.sourcegitcommit: 72d0280c2481250cf9114d32317ad2be59ab6789
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40966899"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="2118c-104">Monitoramento e relatórios de dispositivos no centro de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2118c-104">Device monitoring and reporting in the Microsoft 365 security center</span></span>

<span data-ttu-id="2118c-105">Mantenha seus dispositivos seguros, atualizados e identifique as possíveis ameaças no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2118c-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="2118c-106">Exibir alertas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="2118c-106">View device alerts</span></span>

<span data-ttu-id="2118c-107">Obtenha alertas atualizados sobre a atividade de violação e outras ameaças em seus dispositivos do Microsoft defender ATP (disponível com uma licença E5).</span><span class="sxs-lookup"><span data-stu-id="2118c-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender ATP (available with an E5 license).</span></span> <span data-ttu-id="2118c-108">O Microsoft 365 Security Center monitora efetivamente esses alertas em um nível alto usando seu fluxo de trabalho preferido.</span><span class="sxs-lookup"><span data-stu-id="2118c-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="2118c-109">Monitorar alertas de alto impacto</span><span class="sxs-lookup"><span data-stu-id="2118c-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="2118c-110">Cada alerta ATP do Microsoft defender tem uma severidade correspondente alta, média, baixa ou informativa que indica seu impacto em potencial para a sua rede, se for deixado autônomo.</span><span class="sxs-lookup"><span data-stu-id="2118c-110">Each Microsoft Defender ATP alert has a corresponding severity�high, medium, low, or informational�that indicates its potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="2118c-111">Use o cartão de **severidade de alerta de dispositivo** para se concentrar especificamente nos alertas que são mais graves e podem exigir resposta imediata.</span><span class="sxs-lookup"><span data-stu-id="2118c-111">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="2118c-112">Neste cartão, você pode exibir mais informações no portal da central de segurança do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="2118c-112">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Cartão de severidade de alertas de dispositivo](../images/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="2118c-114">Entender fontes de alertas</span><span class="sxs-lookup"><span data-stu-id="2118c-114">Understand sources of alerts</span></span>

<span data-ttu-id="2118c-115">O Microsoft defender ATP aproveita dados de uma ampla variedade de sensores de segurança e fontes de inteligência para gerar alertas.</span><span class="sxs-lookup"><span data-stu-id="2118c-115">Microsoft Defender ATP leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="2118c-116">Por exemplo, ele pode usar informações de detecção do Windows Defender Antivirus e antimalware de terceiros, bem como sua própria inteligência de ameaças personalizada fornecida por meio da API do serviço Web.</span><span class="sxs-lookup"><span data-stu-id="2118c-116">For example, it can use detection information from Windows Defender Antivirus and third-party antimalware, as well as your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="2118c-117">O cartão de fontes de **detecção de alerta de dispositivo** mostra a distribuição de alertas por fonte.</span><span class="sxs-lookup"><span data-stu-id="2118c-117">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="2118c-118">Este cartão pode ajudá-lo a controlar atividades relacionadas a determinadas fontes, particularmente suas fontes personalizadas.</span><span class="sxs-lookup"><span data-stu-id="2118c-118">This card can help you track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="2118c-119">Você também pode usá-lo para se concentrar nos alertas provenientes de sensores que não estão configurados para bloquear automaticamente atividades ou componentes mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="2118c-119">You can also use this to focus on alerts coming from sensors that are not configured to automatically block malicious activity or components.</span></span>

![Cartão de fontes de detecção de alerta de dispositivo](../images/device-alert-detection-sources.png)

<span data-ttu-id="2118c-121">Neste cartão, você pode exibir mais informações no portal da central de segurança do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="2118c-121">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="2118c-122">Compreender os tipos de ameaças que acionam alertas</span><span class="sxs-lookup"><span data-stu-id="2118c-122">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="2118c-123">O Microsoft defender ATP classifica cada alerta em uma categoria que representa um determinado estágio na cadeia de ataque ou um tipo de componente de ameaça.</span><span class="sxs-lookup"><span data-stu-id="2118c-123">Microsoft Defender ATP sorts each alert into a category representing a certain stage in the attack chain or a type of threat component.</span></span> <span data-ttu-id="2118c-124">Por exemplo, as atividades de ameaça detectadas podem ser categorizadas no movimento lateral para indicar que a atividade envolvia uma tentativa de alcançar outros dispositivos na rede e que tenha sido provavelmente após os invasores terem um incorrido inicial.</span><span class="sxs-lookup"><span data-stu-id="2118c-124">For example, detected threat activity might be categorized into �lateral movement� to indicate that the activity involved an attempt to reach other devices on the network and has likely occurred after attackers have gained an initial foothold.</span></span> <span data-ttu-id="2118c-125">Quando detectada, um componente de ameaça pode ser classificado amplamente como malware ou mais especificamente como ransomware, roubo de credencial ou outros tipos de software mal-intencionado ou indesejado.</span><span class="sxs-lookup"><span data-stu-id="2118c-125">When detected, a threat component might either be classified broadly as �malware� or more specifically as �ransomware�, �credential stealing� or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="2118c-126">O cartão de **categorias de ameaça de dispositivo** mostra a distribuição de alertas nessas categorias.</span><span class="sxs-lookup"><span data-stu-id="2118c-126">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="2118c-127">Você pode usar essas informações para identificar a atividade de ameaças, como tentativas de roubo de credenciais, que podem ter um impacto mais significativo em comparação às tentativas da engenharia social, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="2118c-127">You can use this information to identify threat activity, such as attempts at credential theft, which can have more significant impact compared to attempts at social engineering, for example.</span></span> <span data-ttu-id="2118c-128">Você também pode usar isso para monitorar ameaças potencialmente destrutivas, como ransomware.</span><span class="sxs-lookup"><span data-stu-id="2118c-128">You can also use this to monitor for potentially destructive threats like ransomware.</span></span>

![Cartão de categorias de ameaças de dispositivos](../images/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="2118c-130">Monitorar alertas ativos</span><span class="sxs-lookup"><span data-stu-id="2118c-130">Monitor active alerts</span></span>

<span data-ttu-id="2118c-131">O cartão de **status de alerta de dispositivo** indica o número de alertas que não foram resolvidos e podem exigir atenção.</span><span class="sxs-lookup"><span data-stu-id="2118c-131">The **Device alert status** card indicates the number of alerts that have not been resolved and might require attention.</span></span> <span data-ttu-id="2118c-132">Neste cartão, você pode exibir mais informações no portal da central de segurança do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="2118c-132">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Cartão de status de alerta de dispositivos](../images/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="2118c-134">Monitorar a classificação de alertas resolvidos</span><span class="sxs-lookup"><span data-stu-id="2118c-134">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="2118c-135">Ao resolver um alerta ATP do Microsoft defender, sua equipe de segurança pode especificar se um alerta foi verificado como:</span><span class="sxs-lookup"><span data-stu-id="2118c-135">When resolving a Microsoft Defender ATP alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="2118c-136">Um alerta verdadeiro que identifica atividade de violação real ou componentes de ameaça</span><span class="sxs-lookup"><span data-stu-id="2118c-136">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="2118c-137">Um alerta falso que foi detectado incorretamente uma atividade normal</span><span class="sxs-lookup"><span data-stu-id="2118c-137">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="2118c-138">O cartão de **classificação de alerta de dispositivo** mostra se seus alertas resolvidos foram classificados como verdadeiros ou falsos alertas.</span><span class="sxs-lookup"><span data-stu-id="2118c-138">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="2118c-139">Neste cartão, você pode exibir mais informações no portal da central de segurança do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="2118c-139">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="2118c-140">Observação: em alguns casos, as informações de classificação não estão disponíveis para determinados alertas.</span><span class="sxs-lookup"><span data-stu-id="2118c-140">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![Cartão de classificação de alerta de dispositivo](../images/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="2118c-142">Monitorar a determinação dos alertas resolvidos</span><span class="sxs-lookup"><span data-stu-id="2118c-142">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="2118c-143">Além de classificar se um alerta é verdadeiro ou falso durante a resolução, sua equipe de segurança pode fornecer uma determinação, indicando o tipo de atividade normal ou mal-intencionada encontrada durante a validação do alerta.</span><span class="sxs-lookup"><span data-stu-id="2118c-143">In addition to classifying whether an alert is true or false during resolution, your security staff can provide a determination, indicating the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="2118c-144">O cartão de **determinação de alerta de dispositivo** mostra a determinação oferecida para cada alerta, especificamente:</span><span class="sxs-lookup"><span data-stu-id="2118c-144">The **Device alert determination** card shows the determination provided for each alert, specifically:</span></span>

* <span data-ttu-id="2118c-145">A **apt** é uma ameaça persistente avançada, indicando que a atividade detectada ou o componente de ameaça faz parte de uma violação sofisticada projetada para obter uma brecha na rede afetada</span><span class="sxs-lookup"><span data-stu-id="2118c-145">**APT** � advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="2118c-146">Código ou arquivo mal-intencionado de **malware**</span><span class="sxs-lookup"><span data-stu-id="2118c-146">**Malware** � malicious file or code</span></span>
* <span data-ttu-id="2118c-147">Atividade normal da **equipe de segurança** realizada pela equipe de segurança</span><span class="sxs-lookup"><span data-stu-id="2118c-147">**Security personnel** � normal activity performed by security staff</span></span>
* <span data-ttu-id="2118c-148">Atividade de **teste de segurança** ou componentes projetados para simular ameaças reais e que devem disparar sensores de segurança e gerar alertas</span><span class="sxs-lookup"><span data-stu-id="2118c-148">**Security testing** � activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="2118c-149">Aplicativos de **software indesejados** e outros softwares que não são considerados mal intencionados, mas que, de outra forma, violam os padrões de uso aceitável</span><span class="sxs-lookup"><span data-stu-id="2118c-149">**Unwanted software** � apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="2118c-150">**Outras** determinam que não estão sob os tipos fornecidos</span><span class="sxs-lookup"><span data-stu-id="2118c-150">**Others** � any other determination that does not fall under the provided types</span></span>

<span data-ttu-id="2118c-151">Neste cartão, você pode exibir mais informações na central de segurança do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="2118c-151">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![Cartão de determinação de alerta do dispositivo](../images/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="2118c-153">Entender quais dispositivos estão em risco</span><span class="sxs-lookup"><span data-stu-id="2118c-153">Understand which devices are at risk</span></span>

<span data-ttu-id="2118c-154">**Proteção de dispositivo** mostra o nível de risco para dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2118c-154">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="2118c-155">O nível de risco é baseado em fatores como o tipo e a gravidade de alertas no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2118c-155">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![Cartão de proteção de dispositivos](../images/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="2118c-157">Monitorar e relatar o status dos dispositivos gerenciados pelo Intune</span><span class="sxs-lookup"><span data-stu-id="2118c-157">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="2118c-158">Os relatórios a seguir contêm dados de dispositivos registrados no Intune.</span><span class="sxs-lookup"><span data-stu-id="2118c-158">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="2118c-159">Dados de dispositivos não registrados não estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="2118c-159">Data from unenrolled devices is not included.</span></span> <span data-ttu-id="2118c-160">Somente os administradores globais podem exibir esses cartões.</span><span class="sxs-lookup"><span data-stu-id="2118c-160">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="2118c-161">Os dados do dispositivo registrados do Intune incluem:</span><span class="sxs-lookup"><span data-stu-id="2118c-161">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="2118c-162">Conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="2118c-162">Device compliance</span></span>
* <span data-ttu-id="2118c-163">Dispositivos com malware ativo</span><span class="sxs-lookup"><span data-stu-id="2118c-163">Devices with active malware</span></span>
* <span data-ttu-id="2118c-164">Tipos de malware em dispositivos</span><span class="sxs-lookup"><span data-stu-id="2118c-164">Types of malware on devices</span></span>
* <span data-ttu-id="2118c-165">Malware em dispositivos</span><span class="sxs-lookup"><span data-stu-id="2118c-165">Malware on devices</span></span>
* <span data-ttu-id="2118c-166">Dispositivos com detecções de malware</span><span class="sxs-lookup"><span data-stu-id="2118c-166">Devices with malware detections</span></span>
* <span data-ttu-id="2118c-167">Usuários com detecções de malware</span><span class="sxs-lookup"><span data-stu-id="2118c-167">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="2118c-168">Monitorar a conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="2118c-168">Monitor device compliance</span></span>

<span data-ttu-id="2118c-169">A **conformidade do dispositivo** mostra quantos dispositivos estão registrados no Intune em conformidade com as políticas de configuração.</span><span class="sxs-lookup"><span data-stu-id="2118c-169">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![Cartão de conformidade do dispositivo](../images/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="2118c-171">Descobrir dispositivos com detecções de malware</span><span class="sxs-lookup"><span data-stu-id="2118c-171">Discover devices with malware detections</span></span>

<span data-ttu-id="2118c-172">As **detecções de malware de dispositivo** fornecem o número de dispositivos registrados do Intune com malware que não foram totalmente resolvidos devido às ações pendentes de uma reinicialização, de uma verificação completa ou de ações de usuário manual ou se a ação de correção não for concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="2118c-172">**Device malware detections** provides the number of Intune enrolled devices with malware that have not been fully resolved due to pending actions�a restart, a full scan or manual user actions�or if the remediation action did not complete successfully.</span></span>

![Cartão de detecções de malware de dispositivo](../images/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="2118c-174">Compreender os tipos de malware detectados</span><span class="sxs-lookup"><span data-stu-id="2118c-174">Understand the types of malware detected</span></span>

<span data-ttu-id="2118c-175">**Tipos de malware em dispositivos** mostra diferentes tipos de malware detectados em dispositivos registrados no Intune.</span><span class="sxs-lookup"><span data-stu-id="2118c-175">**Types of malware on devices** shows different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="2118c-176">Você pode investigar cada tipo na central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2118c-176">You can investigate each type in the Microsoft 365 security center.</span></span>

![Tipos de malware no cartão de dispositivos](../images/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="2118c-178">Entender o malware específico detectado em seus dispositivos</span><span class="sxs-lookup"><span data-stu-id="2118c-178">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="2118c-179">**Malware em dispositivos** fornece uma lista de malware específico detectado em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2118c-179">**Malware on devices** provides a list of the specific malware detected on your devices.</span></span>

![Placa de malware em dispositivos](../images/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="2118c-181">Entender quais dispositivos têm mais malware</span><span class="sxs-lookup"><span data-stu-id="2118c-181">Understand which devices have the most malware</span></span>

<span data-ttu-id="2118c-182">**Dispositivos com detecções de malware** mostram quais dispositivos têm a maior quantidade de detecções de malware.</span><span class="sxs-lookup"><span data-stu-id="2118c-182">**Devices with malware detections** shows which devices have the most malware detections.</span></span> <span data-ttu-id="2118c-183">no centro de segurança do Microsoft 365, você pode investigar se o malware está ativo, quem usa o dispositivo e seu status de gerenciamento no Intune.</span><span class="sxs-lookup"><span data-stu-id="2118c-183">in the Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![Dispositivos com cartão de detecções de malware](../images/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="2118c-185">Entender quais usuários têm dispositivos com mais malware</span><span class="sxs-lookup"><span data-stu-id="2118c-185">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="2118c-186">**Os usuários com detecções de malware** mostram aos usuários dispositivos com mais detecções de malware.</span><span class="sxs-lookup"><span data-stu-id="2118c-186">**Users with malware detections** shows users with devices that had the most malware detections.</span></span> <span data-ttu-id="2118c-187">na central de segurança do Microsoft 365, você pode ver quantos dispositivos são atribuídos a cada usuário e mais informações sobre cada dispositivo e o tipo de malware.</span><span class="sxs-lookup"><span data-stu-id="2118c-187">in the Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![Usuários com cartão de detecção de malware](../images/users-with-malware-detections.png)

## <a name="monitor-and-manage-asr-rule-deployment-and-detections"></a><span data-ttu-id="2118c-189">Monitorar e gerenciar a implantação e as detecções de regras ASR</span><span class="sxs-lookup"><span data-stu-id="2118c-189">Monitor and manage ASR rule deployment and detections</span></span>

<span data-ttu-id="2118c-190">[As regras de redução da superfície de ataque (ASR)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) ajudam a evitar ações e aplicativos normalmente usados por malware de busca de exploração para infectar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2118c-190">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) help prevent actions and apps that are typically used by exploit-seeking malware to infect devices.</span></span> <span data-ttu-id="2118c-191">Essas regras controlam quando e como os executáveis podem ser executados.</span><span class="sxs-lookup"><span data-stu-id="2118c-191">These rules control when and how executables can run.</span></span> <span data-ttu-id="2118c-192">Por exemplo, você pode impedir que JavaScript ou VBScript inicie um executável baixado, bloqueie as chamadas da API Win32 de macros do Office ou bloqueie processos executados a partir de unidades USB.</span><span class="sxs-lookup"><span data-stu-id="2118c-192">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![Cartão de redução de superfície de ataque](../images/attack-surface-reduction-rules.png)

<span data-ttu-id="2118c-194">O cartão de **regras de redução da superfície de ataque** fornece uma visão geral da implantação de regras nos seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2118c-194">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="2118c-195">A barra superior do cartão mostra o número total de dispositivos que estão nos seguintes modos de implantação:</span><span class="sxs-lookup"><span data-stu-id="2118c-195">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="2118c-196">Dispositivos de **modo de bloqueio** com pelo menos uma regra configurada para bloquear a atividade detectada</span><span class="sxs-lookup"><span data-stu-id="2118c-196">**Block mode** � devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="2118c-197">Dispositivos de **modo de auditoria** sem regras definidas para bloquear a atividade detectada, mas tem pelo menos uma regra definida para auditar a atividade detectada</span><span class="sxs-lookup"><span data-stu-id="2118c-197">**Audit mode** � devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="2118c-198">**Desligar** dispositivos com todas as regras ASR desativadas</span><span class="sxs-lookup"><span data-stu-id="2118c-198">**Off** � devices with all ASR rules turned off</span></span>

<span data-ttu-id="2118c-199">A parte inferior deste cartão mostra as configurações por regra em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="2118c-199">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="2118c-200">Cada barra indica o número de dispositivos que estão configurados para bloquear ou auditar a detecção ou a regra completamente desativada.</span><span class="sxs-lookup"><span data-stu-id="2118c-200">Each bar indicates the number of devices that are set to block or audit detection or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="2118c-201">Exibir detecções ASR</span><span class="sxs-lookup"><span data-stu-id="2118c-201">View ASR detections</span></span>

<span data-ttu-id="2118c-202">Para exibir informações detalhadas sobre detecções de regra ASR em sua rede, selecione **Exibir detecções** no cartão de **regras de redução de superfície de ataque** .</span><span class="sxs-lookup"><span data-stu-id="2118c-202">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="2118c-203">A guia **detecções** da página relatório detalhado será aberta.</span><span class="sxs-lookup"><span data-stu-id="2118c-203">The **Detections** tab in the detailed report page will open.</span></span>

![Guia detecções](../images/detections-tab.png)

<span data-ttu-id="2118c-205">O gráfico na parte superior da página mostra as detecções com as detecções de empilhamento de tempo que foram bloqueadas ou auditadas.</span><span class="sxs-lookup"><span data-stu-id="2118c-205">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="2118c-206">A tabela na parte inferior lista as detecções mais recentes.</span><span class="sxs-lookup"><span data-stu-id="2118c-206">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="2118c-207">Use as seguintes informações na tabela para entender a natureza das detecções:</span><span class="sxs-lookup"><span data-stu-id="2118c-207">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="2118c-208">**Arquivo detectado** o arquivo, geralmente um script ou um documento, cujo conteúdo disparou a atividade de ataque suspeito</span><span class="sxs-lookup"><span data-stu-id="2118c-208">**Detected file** � the file, typically a script or a document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="2118c-209">Nome da **regra** que descreve as atividades de ataque que a regra foi projetada para capturar.</span><span class="sxs-lookup"><span data-stu-id="2118c-209">**Rule** � name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="2118c-210">Leia sobre regras de ASR existentes</span><span class="sxs-lookup"><span data-stu-id="2118c-210">Read about existing ASR rules</span></span>
* <span data-ttu-id="2118c-211">**Aplicativo de origem** o aplicativo que carregou ou executou o conteúdo que está disparando a atividade de ataque suspeito.</span><span class="sxs-lookup"><span data-stu-id="2118c-211">**Source app** � the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="2118c-212">Pode ser um aplicativo legítimo, como navegador da Web, um aplicativo do Office ou uma ferramenta do sistema, como o PowerShell</span><span class="sxs-lookup"><span data-stu-id="2118c-212">This could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="2118c-213">**Publisher** o fornecedor que lançou o aplicativo de origem</span><span class="sxs-lookup"><span data-stu-id="2118c-213">**Publisher** � the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="2118c-214">Examinar as configurações de regra ASR do dispositivo</span><span class="sxs-lookup"><span data-stu-id="2118c-214">Review device ASR rule settings</span></span>

<span data-ttu-id="2118c-215">Na página relatório de **regras de redução da superfície de ataque** , vá para a guia **configuração** para analisar as configurações de regra para dispositivos individuais.</span><span class="sxs-lookup"><span data-stu-id="2118c-215">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="2118c-216">Selecione um dispositivo para obter informações detalhadas sobre se cada regra está no modo de bloqueio, modo de auditoria ou desativada inteiramente.</span><span class="sxs-lookup"><span data-stu-id="2118c-216">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![Guia Configuração](../images/configuration-tab.png)

<span data-ttu-id="2118c-218">O Microsoft Intune fornece funcionalidade de gerenciamento para suas regras ASR.</span><span class="sxs-lookup"><span data-stu-id="2118c-218">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="2118c-219">Se você quiser atualizar suas configurações, selecione **começar** em **configurar dispositivos** na guia para abrir o gerenciamento de dispositivos no Intune.</span><span class="sxs-lookup"><span data-stu-id="2118c-219">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="2118c-220">Excluir arquivos de regras ASR</span><span class="sxs-lookup"><span data-stu-id="2118c-220">Exclude files from ASR rules</span></span>

<span data-ttu-id="2118c-221">A central de segurança do Microsoft 365 coleta os nomes dos [arquivos que você pode querer excluir](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) das detecções por regras de redução de superfície de ataque.</span><span class="sxs-lookup"><span data-stu-id="2118c-221">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="2118c-222">Ao excluir arquivos, você pode reduzir as detecções de falsos positivos e implantar com segurança as regras de redução de superfície de ataque no modo de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="2118c-222">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="2118c-223">As exclusões são gerenciadas no Microsoft Intune, mas o centro de segurança do Microsoft 365 oferece uma ferramenta de análise para ajudá-lo a entender os arquivos.</span><span class="sxs-lookup"><span data-stu-id="2118c-223">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="2118c-224">Para começar a coletar arquivos para exclusão, vá para a guia **adicionar exclusões** na página relatório de **regras de redução de superfície de ataque** .</span><span class="sxs-lookup"><span data-stu-id="2118c-224">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="2118c-225">A ferramenta analisa as detecções por todas as regras de redução da superfície de ataque, mas [apenas algumas regras dão suporte a exclusões](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).</span><span class="sxs-lookup"><span data-stu-id="2118c-225">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).</span></span>

![Adicionar guia exclusões](../images/add-exclusions-tab.png)

<span data-ttu-id="2118c-227">A tabela lista todos os nomes de arquivo detectados por suas regras de redução de superfície de ataque.</span><span class="sxs-lookup"><span data-stu-id="2118c-227">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="2118c-228">Você pode selecionar arquivos para revisar o impacto da exclusão deles:</span><span class="sxs-lookup"><span data-stu-id="2118c-228">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="2118c-229">Quantas detecções menos</span><span class="sxs-lookup"><span data-stu-id="2118c-229">How many fewer detections</span></span>
* <span data-ttu-id="2118c-230">Quantos dispositivos menos relatam as detecções</span><span class="sxs-lookup"><span data-stu-id="2118c-230">How many fewer devices report the detections</span></span>

<span data-ttu-id="2118c-231">Para obter uma lista dos arquivos selecionados com seus caminhos completos para exclusão, selecione **obter caminhos de exclusão**.</span><span class="sxs-lookup"><span data-stu-id="2118c-231">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="2118c-232">Os logs para o bloqueio de credenciais de bloqueio de regra ASR **do subsistema de autoridade de segurança local (Lsass. exe) do Windows** capturam o aplicativo de origem **LSASS. exe**, um arquivo de sistema normal, como o arquivo detectado.</span><span class="sxs-lookup"><span data-stu-id="2118c-232">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**, a normal system file, as the detected file.</span></span> <span data-ttu-id="2118c-233">Como resultado, a lista gerada de caminhos de exclusão incluirá esse arquivo.</span><span class="sxs-lookup"><span data-stu-id="2118c-233">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="2118c-234">Para excluir o arquivo que disparou essa regra em vez de **LSASS. exe**, use o caminho para o aplicativo de origem em vez do arquivo detectado.</span><span class="sxs-lookup"><span data-stu-id="2118c-234">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="2118c-235">Para localizar o aplicativo de origem, execute a seguinte [consulta de busca avançada](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) para esta regra específica (identificada por ID de regra 9e6c4e1f-7d60-472F-ba1a-a39ef669e4b2):</span><span class="sxs-lookup"><span data-stu-id="2118c-235">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="2118c-236">Verificar arquivos para exclusão</span><span class="sxs-lookup"><span data-stu-id="2118c-236">Check files for exclusion</span></span>
<span data-ttu-id="2118c-237">Antes de excluir um arquivo do ASR, recomendamos inspecionar o arquivo para determinar se ele não é mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="2118c-237">Before excluding a file from ASR, we recommend that you inspect the file to determine if it is indeed not malicious.</span></span>

<span data-ttu-id="2118c-238">Para revisar um arquivo, use a [página informações do arquivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) no centro de segurança do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="2118c-238">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="2118c-239">A página fornece informações de prevalência, bem como a taxa de detecção de antivírus do VirusTotal.</span><span class="sxs-lookup"><span data-stu-id="2118c-239">The page provides prevalence information as well as the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="2118c-240">Você também pode usar a página para enviar o arquivo para análise profunda.</span><span class="sxs-lookup"><span data-stu-id="2118c-240">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="2118c-241">Para localizar um arquivo detectado no centro de segurança do Microsoft defender, procure todas as detecções de ASR usando a seguinte consulta de busca avançada:</span><span class="sxs-lookup"><span data-stu-id="2118c-241">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="2118c-242">Use o **SHA1** ou o **InitiatingProcessSHA1** nos resultados para pesquisar o arquivo usando a barra de pesquisa universal na central de segurança do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="2118c-242">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>