---
title: Relatório de & dispositivo - Central de segurança
description: Descreve como você pode manter seus dispositivos seguros, atualizados e possíveis ameaças em sua organização
keywords: segurança, malware, Microsoft 365, M365, centro de segurança, monitorar, relatório, dispositivos
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: b9580f904f9cc5043fa3e825007339ce66daaa72
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930493"
---
# <a name="device-monitoring-and-reporting-in-the-microsoft-365-security-center"></a><span data-ttu-id="bf153-104">Monitoramento e relatório de dispositivos no centro de segurança do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bf153-104">Device monitoring and reporting in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bf153-105">Mantenha seus dispositivos seguros, atualizados e possíveis ameaças na central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bf153-105">Keep your devices secure, up-to-date, and spot potential threats in the Microsoft 365 security center.</span></span>

## <a name="view-device-alerts"></a><span data-ttu-id="bf153-106">Exibir alertas de dispositivo</span><span class="sxs-lookup"><span data-stu-id="bf153-106">View device alerts</span></span>

<span data-ttu-id="bf153-107">Receba alertas atualizados sobre atividades de violação e outras ameaças em seus dispositivos do Microsoft Defender para Ponto de Extremidade (disponível com uma licença E5).</span><span class="sxs-lookup"><span data-stu-id="bf153-107">Get up-to-date alerts about breach activity and other threats on your devices from Microsoft Defender for Endpoint (available with an E5 license).</span></span> <span data-ttu-id="bf153-108">O centro de segurança do Microsoft 365 monitora efetivamente esses alertas em um alto nível usando seu fluxo de trabalho preferido.</span><span class="sxs-lookup"><span data-stu-id="bf153-108">Microsoft 365 security center effectively monitors these alerts at a high level using your preferred workflow.</span></span>

### <a name="monitor-high-impact-alerts"></a><span data-ttu-id="bf153-109">Monitorar alertas de alto impacto</span><span class="sxs-lookup"><span data-stu-id="bf153-109">Monitor high-impact alerts</span></span>

<span data-ttu-id="bf153-110">Cada alerta do Microsoft Defender para Ponto de Extremidade tem uma gravidade correspondente (alta, média, baixa ou informacional).</span><span class="sxs-lookup"><span data-stu-id="bf153-110">Each Microsoft Defender for Endpoint alert has a corresponding severity (high, medium, low, or informational).</span></span> <span data-ttu-id="bf153-111">Isso indica um possível impacto em sua rede, caso não seja autônoma.</span><span class="sxs-lookup"><span data-stu-id="bf153-111">It indicates potential impact to your network if left unattended.</span></span>  

<span data-ttu-id="bf153-112">Use o **cartão de severidade de alerta** do dispositivo para se concentrar especificamente em alertas que são mais graves e podem exigir resposta imediata.</span><span class="sxs-lookup"><span data-stu-id="bf153-112">Use the **Device alert severity** card to focus specifically on alerts that are more severe and might require immediate response.</span></span> <span data-ttu-id="bf153-113">Neste cartão, você pode exibir mais informações no portal da Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="bf153-113">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Cartão de gravidade de alertas de dispositivo](../../media/device-alerts-severity.png)

### <a name="understand-sources-of-alerts"></a><span data-ttu-id="bf153-115">Compreender as fontes de alertas</span><span class="sxs-lookup"><span data-stu-id="bf153-115">Understand sources of alerts</span></span>

<span data-ttu-id="bf153-116">O Microsoft Defender para Ponto de Extremidade aproveita os dados de uma ampla variedade de sensores de segurança e fontes de inteligência para gerar alertas.</span><span class="sxs-lookup"><span data-stu-id="bf153-116">Microsoft Defender for Endpoint leverages data from a broad range of security sensors and intelligence sources to generate alerts.</span></span> <span data-ttu-id="bf153-117">Por exemplo, ele pode usar informações de detecção do Microsoft Defender Antivírus e antimalware de terceiros.</span><span class="sxs-lookup"><span data-stu-id="bf153-117">For example, it can use detection information from Microsoft Defender Antivirus and third-party antimalware.</span></span> <span data-ttu-id="bf153-118">Ele também pode usar sua própria inteligência de ameaça personalizada fornecida por meio da API do serviço Web.</span><span class="sxs-lookup"><span data-stu-id="bf153-118">It can also use your own custom threat intelligence provided through the web service API.</span></span>

<span data-ttu-id="bf153-119">O **cartão de fontes de detecção** de alerta do dispositivo mostra a distribuição de alertas por origem.</span><span class="sxs-lookup"><span data-stu-id="bf153-119">The **Device alert detection** sources card shows the distribution of alerts by source.</span></span> <span data-ttu-id="bf153-120">Acompanhe as atividades relacionadas a determinadas fontes, especialmente suas fontes personalizadas.</span><span class="sxs-lookup"><span data-stu-id="bf153-120">Track activity related to certain sources, particularly your custom sources.</span></span> <span data-ttu-id="bf153-121">Você também pode usar o cartão para se concentrar em alertas provenientes de sensores que não estão configurados para bloquear automaticamente atividades ou componentes mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="bf153-121">You can also use the card to focus on alerts coming from sensors that aren't configured to automatically block malicious activity or components.</span></span>

![Cartão de fontes de detecção de alerta de dispositivo](../../media/device-alert-detection-sources.png)

<span data-ttu-id="bf153-123">Neste cartão, você pode exibir mais informações no portal da Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="bf153-123">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

### <a name="understand-the-types-of-threats-that-trigger-alerts"></a><span data-ttu-id="bf153-124">Compreender os tipos de ameaças que disparam alertas</span><span class="sxs-lookup"><span data-stu-id="bf153-124">Understand the types of threats that trigger alerts</span></span>

<span data-ttu-id="bf153-125">O Microsoft Defender para Ponto de Extremidade classifica cada alerta em uma categoria que representa um determinado estágio na cadeia de ataque ou tipo de componente de ameaça.</span><span class="sxs-lookup"><span data-stu-id="bf153-125">Microsoft Defender for Endpoint sorts each alert into a category representing a certain stage in the attack chain or type of threat component.</span></span> <span data-ttu-id="bf153-126">Por exemplo, uma atividade de ameaça detectada pode ser categorizada como "movimento lateral" para indicar que houve uma tentativa de alcançar outros dispositivos na rede.</span><span class="sxs-lookup"><span data-stu-id="bf153-126">For example, a detected threat activity might be categorized as "lateral movement" to indicate there was an attempt to reach other devices on the network.</span></span> <span data-ttu-id="bf153-127">A atividade provavelmente ocorreu após os invasores ganharem um rodapé inicial.</span><span class="sxs-lookup"><span data-stu-id="bf153-127">The activity has likely occurred after attackers gained an initial foothold.</span></span> <span data-ttu-id="bf153-128">Quando detectado, um componente de ameaça pode ser amplamente classificado como malware ou especificamente como um tipo de ameaça específico.</span><span class="sxs-lookup"><span data-stu-id="bf153-128">When detected, a threat component might be classified broadly as malware or specifically as a specific threat type.</span></span> <span data-ttu-id="bf153-129">As especificidades incluem ransomware, roubo de credenciais ou outros tipos de software mal-intencionado ou indesejado.</span><span class="sxs-lookup"><span data-stu-id="bf153-129">Specifics include ransomware, credential stealing, or other types of malicious or unwanted software.</span></span>

<span data-ttu-id="bf153-130">O **cartão de categorias de ameaças** do dispositivo mostra a distribuição de alertas nessas categorias.</span><span class="sxs-lookup"><span data-stu-id="bf153-130">The **Device threat categories** card shows the distribution of alerts into these categories.</span></span> <span data-ttu-id="bf153-131">Use essas informações para identificar a atividade de ameaças, como tentativas de roubo de credenciais, que geralmente têm um impacto maior do que as tentativas de engenharia social.</span><span class="sxs-lookup"><span data-stu-id="bf153-131">Use this information to identify threat activity, such as credential theft attempts, that usually have higher impact than social engineering attempts.</span></span> <span data-ttu-id="bf153-132">Você também pode monitorar ameaças potencialmente destrutivas, como ransomware.</span><span class="sxs-lookup"><span data-stu-id="bf153-132">You can also to monitor for potentially destructive threats like ransomware.</span></span>

![Cartão de categorias de ameaças do dispositivo](../../media/device-threat-categories.png)

### <a name="monitor-active-alerts"></a><span data-ttu-id="bf153-134">Monitorar alertas ativos</span><span class="sxs-lookup"><span data-stu-id="bf153-134">Monitor active alerts</span></span>

<span data-ttu-id="bf153-135">O **cartão de status do alerta** do dispositivo indica o número de alertas que não foram resolvidos e podem exigir atenção.</span><span class="sxs-lookup"><span data-stu-id="bf153-135">The **Device alert status** card indicates the number of alerts that haven't been resolved and may require attention.</span></span> <span data-ttu-id="bf153-136">Neste cartão, você pode exibir mais informações no portal da Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="bf153-136">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

![Cartão de status do alerta do dispositivo](../../media/device-alert-status.png)

### <a name="monitor-classification-of-resolved-alerts"></a><span data-ttu-id="bf153-138">Monitorar a classificação de alertas resolvidos</span><span class="sxs-lookup"><span data-stu-id="bf153-138">Monitor classification of resolved alerts</span></span>

<span data-ttu-id="bf153-139">Ao resolver um alerta do Microsoft Defender para Ponto de Extremidade, sua equipe de segurança pode especificar se um alerta foi verificado como:</span><span class="sxs-lookup"><span data-stu-id="bf153-139">When resolving a Microsoft Defender for Endpoint alert, your security staff can specify whether an alert has been verified as:</span></span>

* <span data-ttu-id="bf153-140">Um alerta verdadeiro que identifica a atividade de violação real ou os componentes de ameaças</span><span class="sxs-lookup"><span data-stu-id="bf153-140">A true alert that identifies actual breach activity or threat components</span></span>
* <span data-ttu-id="bf153-141">Um alerta falso que detectou incorretamente a atividade normal</span><span class="sxs-lookup"><span data-stu-id="bf153-141">A false alert that has incorrectly detected normal activity</span></span>

<span data-ttu-id="bf153-142">O **cartão de classificação de alerta** do dispositivo mostra se os alertas resolvidos foram classificados como alertas verdadeiros ou falsos.</span><span class="sxs-lookup"><span data-stu-id="bf153-142">The **Device alert classification** card shows whether your resolved alerts have been classified as true or false alerts.</span></span> <span data-ttu-id="bf153-143">Neste cartão, você pode exibir mais informações no portal da Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="bf153-143">From this card, you can view more information on the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="bf153-144">Observação: em alguns casos, as informações de classificação não estão disponíveis para determinados alertas.</span><span class="sxs-lookup"><span data-stu-id="bf153-144">Note: In some cases, classification information is unavailable for certain alerts.</span></span>

![Cartão de classificação de alerta do dispositivo](../../media/device-alert-classification.png)

### <a name="monitor-determination-of-resolved-alerts"></a><span data-ttu-id="bf153-146">Monitorar a determinação de alertas resolvidos</span><span class="sxs-lookup"><span data-stu-id="bf153-146">Monitor determination of resolved alerts</span></span>

<span data-ttu-id="bf153-147">Além de classificar se um alerta é verdadeiro ou falso durante a resolução, sua equipe de segurança pode fornecer uma determinação.</span><span class="sxs-lookup"><span data-stu-id="bf153-147">Along with classifying whether an alert is true or false during resolution, your security staff can provide a determination.</span></span> <span data-ttu-id="bf153-148">Uma determinação indica o tipo de atividade normal ou mal-intencionada encontrada durante a validação do alerta.</span><span class="sxs-lookup"><span data-stu-id="bf153-148">A determination indicates the type of normal or malicious activity that was found while validating the alert.</span></span>

<span data-ttu-id="bf153-149">O **cartão de determinação do alerta** do dispositivo mostra a determinação fornecida para cada alerta.</span><span class="sxs-lookup"><span data-stu-id="bf153-149">The **Device alert determination** card shows the determination provided for each alert.</span></span>

* <span data-ttu-id="bf153-150">**APT**: ameaça persistente avançada, indicando que a atividade detectada ou componente de ameaça faz parte de uma violação sofisticada projetada para obter um rodapé na rede afetada</span><span class="sxs-lookup"><span data-stu-id="bf153-150">**APT**: advanced persistent threat, indicating that the detected activity or threat component is part of a sophisticated breach designed to gain a foothold in the affected network</span></span>  
* <span data-ttu-id="bf153-151">**Malware**: arquivo ou código mal-intencionado</span><span class="sxs-lookup"><span data-stu-id="bf153-151">**Malware**: malicious file or code</span></span>
* <span data-ttu-id="bf153-152">**Equipe de segurança:** atividade normal executada pela equipe de segurança</span><span class="sxs-lookup"><span data-stu-id="bf153-152">**Security personnel**: normal activity performed by security staff</span></span>
* <span data-ttu-id="bf153-153">**Teste de segurança:** atividade ou componentes projetados para simular ameaças reais e esperado acionar sensores de segurança e gerar alertas</span><span class="sxs-lookup"><span data-stu-id="bf153-153">**Security testing**: activity or components designed to simulate actual threats and expected to trigger security sensors and generate alerts</span></span>
* <span data-ttu-id="bf153-154">**Software indesejado:** aplicativos e outros softwares que não são considerados mal-intencionados, mas que violam a política ou padrões de uso aceitável</span><span class="sxs-lookup"><span data-stu-id="bf153-154">**Unwanted software**: apps and other software that are not considered malicious, but otherwise violate policy or acceptable use standards</span></span>
* <span data-ttu-id="bf153-155">**Outros:** qualquer outra determinação que não se enquadra nos tipos fornecidos</span><span class="sxs-lookup"><span data-stu-id="bf153-155">**Others**: any other determination that doesn't fall under the provided types</span></span>

<span data-ttu-id="bf153-156">Neste cartão, você pode exibir mais informações na Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="bf153-156">From this card, you can view more information in Microsoft Defender Security Center.</span></span>

![Cartão de determinação do alerta do dispositivo](../../media/device-alert-determination.png)

### <a name="understand-which-devices-are-at-risk"></a><span data-ttu-id="bf153-158">Entender quais dispositivos estão em risco</span><span class="sxs-lookup"><span data-stu-id="bf153-158">Understand which devices are at risk</span></span>

<span data-ttu-id="bf153-159">**A proteção de** dispositivo mostra o nível de risco para dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bf153-159">**Device protection** shows the risk level for devices.</span></span> <span data-ttu-id="bf153-160">O nível de risco é baseado em fatores como o tipo e a gravidade dos alertas no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="bf153-160">The risk level is based on factors such as the type and severity of alerts on the device.</span></span>

![Cartão de proteção do dispositivo](../../media/device-protection.png)

## <a name="monitor-and-report-status-of-intune-managed-devices"></a><span data-ttu-id="bf153-162">Monitorar e relatar o status de dispositivos gerenciados pelo Intune</span><span class="sxs-lookup"><span data-stu-id="bf153-162">Monitor and report status of Intune-managed devices</span></span>

<span data-ttu-id="bf153-163">Os relatórios a seguir contêm dados de dispositivos inscritos no Intune.</span><span class="sxs-lookup"><span data-stu-id="bf153-163">The following reports contain data from devices enrolled in Intune.</span></span> <span data-ttu-id="bf153-164">Os dados de dispositivos não conectados não estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="bf153-164">Data from unenrolled devices isn't included.</span></span> <span data-ttu-id="bf153-165">Somente administradores globais podem exibir esses cartões.</span><span class="sxs-lookup"><span data-stu-id="bf153-165">Only Global Administrators can view these cards.</span></span>

<span data-ttu-id="bf153-166">Os dados de dispositivos inscritos no Intune incluem:</span><span class="sxs-lookup"><span data-stu-id="bf153-166">Intune enrolled device data includes:</span></span>

* <span data-ttu-id="bf153-167">Conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="bf153-167">Device compliance</span></span>
* <span data-ttu-id="bf153-168">Dispositivos com malware ativo</span><span class="sxs-lookup"><span data-stu-id="bf153-168">Devices with active malware</span></span>
* <span data-ttu-id="bf153-169">Tipos de malware em dispositivos</span><span class="sxs-lookup"><span data-stu-id="bf153-169">Types of malware on devices</span></span>
* <span data-ttu-id="bf153-170">Malware em dispositivos</span><span class="sxs-lookup"><span data-stu-id="bf153-170">Malware on devices</span></span>
* <span data-ttu-id="bf153-171">Dispositivos com detecções de malware</span><span class="sxs-lookup"><span data-stu-id="bf153-171">Devices with malware detections</span></span>
* <span data-ttu-id="bf153-172">Usuários com detecções de malware</span><span class="sxs-lookup"><span data-stu-id="bf153-172">Users with malware detections</span></span>

### <a name="monitor-device-compliance"></a><span data-ttu-id="bf153-173">Monitorar a conformidade do dispositivo</span><span class="sxs-lookup"><span data-stu-id="bf153-173">Monitor device compliance</span></span>

<span data-ttu-id="bf153-174">**A conformidade do** dispositivo mostra quantos dispositivos estão inscritos no Intune estão em conformidade com as políticas de configuração.</span><span class="sxs-lookup"><span data-stu-id="bf153-174">**Device compliance** shows how many devices that are enrolled in Intune comply with configuration policies.</span></span>

![Cartão de conformidade do dispositivo](../../media/device-compliance.png)

### <a name="discover-devices-with-malware-detections"></a><span data-ttu-id="bf153-176">Descobrir dispositivos com detecções de malware</span><span class="sxs-lookup"><span data-stu-id="bf153-176">Discover devices with malware detections</span></span>

<span data-ttu-id="bf153-177">**As detecções de malware de** dispositivo fornecem o número de dispositivos inscritos no Intune com malware que não foram totalmente resolvidos.</span><span class="sxs-lookup"><span data-stu-id="bf153-177">**Device malware detections** provide the number of Intune enrolled devices with malware that hasn't been fully resolved.</span></span> <span data-ttu-id="bf153-178">A falta de resolução pode ser devido a ações pendentes, uma reinicialização, uma verificação completa, ações manuais do usuário ou se a ação de correção não foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="bf153-178">A lack of resolution can be because of pending actions, a restart, a full scan, manual user actions, or if the remediation action was not successfully completed.</span></span>

![Cartão de detecções de malware do dispositivo](../../media/device-malware-detections.png)

### <a name="understand-the-types-of-malware-detected"></a><span data-ttu-id="bf153-180">Compreender os tipos de malware detectados</span><span class="sxs-lookup"><span data-stu-id="bf153-180">Understand the types of malware detected</span></span>

<span data-ttu-id="bf153-181">**Os tipos de malware em dispositivos** mostram diferentes tipos de malware que foram detectados em dispositivos inscritos no Intune.</span><span class="sxs-lookup"><span data-stu-id="bf153-181">**Types of malware on devices** show different kinds of malware that have been detected on devices enrolled in Intune.</span></span> <span data-ttu-id="bf153-182">Você pode investigar cada tipo no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bf153-182">You can investigate each type in the Microsoft 365 security center.</span></span>

![Tipos de malware no cartão de dispositivos](../../media/types-of-malware-on-devices.png)

### <a name="understand-the-specific-malware-detected-on-your-devices"></a><span data-ttu-id="bf153-184">Entenda o malware específico detectado em seus dispositivos</span><span class="sxs-lookup"><span data-stu-id="bf153-184">Understand the specific malware detected on your devices</span></span>

<span data-ttu-id="bf153-185">**Malware em dispositivos** fornece uma lista do malware específico detectado em seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bf153-185">**Malware on devices** provides a list of the specific malware detected on your devices.</span></span>

![Cartão de malware em dispositivos](../../media/malware-on-devices.png)

### <a name="understand-which-devices-have-the-most-malware"></a><span data-ttu-id="bf153-187">Entender quais dispositivos têm mais malware</span><span class="sxs-lookup"><span data-stu-id="bf153-187">Understand which devices have the most malware</span></span>

<span data-ttu-id="bf153-188">**Dispositivos com detecções de malware** mostram quais dispositivos têm mais detecções de malware.</span><span class="sxs-lookup"><span data-stu-id="bf153-188">**Devices with malware detections** show which devices have the most malware detections.</span></span> <span data-ttu-id="bf153-189">no centro de segurança do Microsoft 365, você pode investigar se o malware está ativo, quem usa o dispositivo e seu status de gerenciamento no Intune.</span><span class="sxs-lookup"><span data-stu-id="bf153-189">in the Microsoft 365 security center, you can investigate whether malware is active, who uses the device, and its management status in Intune.</span></span>

![Dispositivos com cartão de detecções de malware](../../media/devices-with-malware-detections.png)

### <a name="understand-which-users-have-devices-with-the-most-malware"></a><span data-ttu-id="bf153-191">Entender quais usuários têm dispositivos com mais malware</span><span class="sxs-lookup"><span data-stu-id="bf153-191">Understand which users have devices with the most malware</span></span>

<span data-ttu-id="bf153-192">**Os usuários com detecções de malware** mostram os usuários com dispositivos que tiveram a maioria das detecções de malware.</span><span class="sxs-lookup"><span data-stu-id="bf153-192">**Users with malware detections** show users with devices that had the most malware detections.</span></span> <span data-ttu-id="bf153-193">Na central de segurança do Microsoft 365, você pode ver quantos dispositivos estão atribuídos a cada usuário e mais informações sobre cada dispositivo e o tipo de malware.</span><span class="sxs-lookup"><span data-stu-id="bf153-193">In the Microsoft 365 security center, you can see how many devices are assigned to each user and more information about each device and the type of malware.</span></span>

![Usuários com cartão de detecção de malware](../../media/users-with-malware-detections.png)

## <a name="monitor-and-manage-attack-surface-reduction-rule-deployment-and-detections"></a><span data-ttu-id="bf153-195">Monitorar e gerenciar detecções e implantação de regras de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="bf153-195">Monitor and manage attack surface reduction rule deployment and detections</span></span>

<span data-ttu-id="bf153-196">As regras de Redução de Superfície de Ataque [(ASR)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) ajudam a evitar ações e aplicativos que normalmente são usados por malware em busca de exploração para infectar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bf153-196">[Attack Surface Reduction (ASR) rules](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) help prevent actions and apps that are typically used by exploit-seeking malware to infect devices.</span></span> <span data-ttu-id="bf153-197">Essas regras controlam quando e como os executáveis podem ser executados.</span><span class="sxs-lookup"><span data-stu-id="bf153-197">These rules control when and how executables can run.</span></span> <span data-ttu-id="bf153-198">Por exemplo, você pode impedir que o JavaScript ou o VBScript inicializem um item executável baixado, bloqueie chamadas de API do Win32 recebidas de macros do Office ou bloqueie processos executados em unidades USB.</span><span class="sxs-lookup"><span data-stu-id="bf153-198">For example, you can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, or block processes that run from USB drives.</span></span>

![Cartão de reduções de superfície de ataque](../../media/attack-surface-reduction-rules.png)

<span data-ttu-id="bf153-200">O cartão de **Regras de redução de superfície de ataque** fornece uma visão geral da implantação de regras nos seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bf153-200">The **Attack surface reduction rules** card provides an overview of the deployment of rules across your devices.</span></span>

<span data-ttu-id="bf153-201">A barra superior do cartão mostra o número total de dispositivos que estão nos seguintes modos de implantação:</span><span class="sxs-lookup"><span data-stu-id="bf153-201">The top bar on the card shows the total number of devices that are in the following deployment modes:</span></span>

* <span data-ttu-id="bf153-202">**Modo de bloqueio:** dispositivos com pelo menos uma regra configurada para bloquear a atividade detectada</span><span class="sxs-lookup"><span data-stu-id="bf153-202">**Block mode**: devices with at least one rule configured to block detected activity</span></span>
* <span data-ttu-id="bf153-203">**Modo de** auditoria: dispositivos sem regras definidas para bloquear atividade detectada, mas tem pelo menos uma regra definida para auditar a atividade detectada</span><span class="sxs-lookup"><span data-stu-id="bf153-203">**Audit mode**: devices with no rules set to block detected activity, but has at least one rule set to audit detected activity</span></span>  
* <span data-ttu-id="bf153-204">**Desligado:** dispositivos com todas as regras ASR desligadas</span><span class="sxs-lookup"><span data-stu-id="bf153-204">**Off**: devices with all ASR rules turned off</span></span>

<span data-ttu-id="bf153-205">A parte inferior do cartão mostra as configurações da regra em todos os seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="bf153-205">The lower part of this card shows settings by rule across your devices.</span></span> <span data-ttu-id="bf153-206">Cada barra indica o número de dispositivos definidos para bloquear, detectar auditoria ou ter a regra completamente desligada.</span><span class="sxs-lookup"><span data-stu-id="bf153-206">Each bar indicates the number of devices that are set to block, audit detection, or have the rule completely turned off.</span></span>

### <a name="view-asr-detections"></a><span data-ttu-id="bf153-207">Exibir detecções de ASR</span><span class="sxs-lookup"><span data-stu-id="bf153-207">View ASR detections</span></span>

<span data-ttu-id="bf153-208">Para exibir informações **detalhadas** sobre detecções de regra ASR em sua rede, selecione Exibir detecções no cartão de regras de **Redução de superfície de** ataque.</span><span class="sxs-lookup"><span data-stu-id="bf153-208">To view detailed information about ASR rule detections in your network, select **View detections** on the **Attack surface reduction rules** card.</span></span> <span data-ttu-id="bf153-209">A **guia Detecções** na página de relatório detalhado será aberta.</span><span class="sxs-lookup"><span data-stu-id="bf153-209">The **Detections** tab in the detailed report page will open.</span></span>

![Guia Detecções](../../media/detections-tab.png)

<span data-ttu-id="bf153-211">O gráfico na parte superior da página mostra detecções ao longo do tempo empilhando detecções que foram bloqueadas ou auditadas.</span><span class="sxs-lookup"><span data-stu-id="bf153-211">The chart at the top of the page shows detections over time stacking detections that were either blocked or audited.</span></span> <span data-ttu-id="bf153-212">A tabela na parte inferior lista as detecções mais recentes.</span><span class="sxs-lookup"><span data-stu-id="bf153-212">The table at the bottom lists the most recent detections.</span></span> <span data-ttu-id="bf153-213">Confira as seguintes informações na tabela para entender a natureza das detecções:</span><span class="sxs-lookup"><span data-stu-id="bf153-213">Use the following information on the table to understand the nature of the detections:</span></span>

* <span data-ttu-id="bf153-214">**Arquivo detectado:** o arquivo, normalmente um script ou documento, cujo conteúdo disparou a atividade suspeita de ataque</span><span class="sxs-lookup"><span data-stu-id="bf153-214">**Detected file**: the file, typically a script or document, whose contents triggered the suspected attack activity</span></span>
* <span data-ttu-id="bf153-215">**Regra**: nome que descreve as atividades de ataque que a regra foi projetada para capturar.</span><span class="sxs-lookup"><span data-stu-id="bf153-215">**Rule**: name describing the attack activities the rule is designed to catch.</span></span> <span data-ttu-id="bf153-216">Ler sobre regras ASR existentes</span><span class="sxs-lookup"><span data-stu-id="bf153-216">Read about existing ASR rules</span></span>
* <span data-ttu-id="bf153-217">**Aplicativo de** origem : o aplicativo que carregou ou executou conteúdo disparando a atividade suspeita de ataque.</span><span class="sxs-lookup"><span data-stu-id="bf153-217">**Source app**: the application that loaded or executed content triggering the suspected attack activity.</span></span> <span data-ttu-id="bf153-218">Pode ser um aplicativo legítimo, como um navegador da Web, um aplicativo do Office ou uma ferramenta do sistema, como o PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf153-218">It could be a legitimate application, such as web browser, an Office application, or a system tool like PowerShell</span></span>
* <span data-ttu-id="bf153-219">**Fornecedor**: o fornecedor que lançou o aplicativo de origem</span><span class="sxs-lookup"><span data-stu-id="bf153-219">**Publisher**: the vendor that released the source app</span></span>

### <a name="review-device-asr-rule-settings"></a><span data-ttu-id="bf153-220">Revisar as configurações de regra ASR do dispositivo</span><span class="sxs-lookup"><span data-stu-id="bf153-220">Review device ASR rule settings</span></span>

<span data-ttu-id="bf153-221">Na página **Relatório de regras de Redução de superfície** de ataque, vá para a guia Configuração para revisar as configurações de regra para dispositivos individuais. </span><span class="sxs-lookup"><span data-stu-id="bf153-221">In the **Attack surface reduction rules** report page, go to the **Configuration** tab to review rule settings for individual devices.</span></span> <span data-ttu-id="bf153-222">Selecione um dispositivo para obter informações detalhadas sobre se cada regra está no modo de bloqueio, no modo de auditoria ou totalmente desligada.</span><span class="sxs-lookup"><span data-stu-id="bf153-222">Select a device to get detailed information about whether each rule is in block mode, audit mode, or turned off entirely.</span></span>

![Guia Configuração](../../media/configuration-tab.png)

<span data-ttu-id="bf153-224">O Microsoft Intune fornece funcionalidade de gerenciamento para suas regras asR.</span><span class="sxs-lookup"><span data-stu-id="bf153-224">Microsoft Intune provides management functionality for your ASR rules.</span></span> <span data-ttu-id="bf153-225">Se você quiser atualizar suas configurações,  selecione **Começar** em Configurar dispositivos na guia para abrir o gerenciamento de dispositivos no Intune.</span><span class="sxs-lookup"><span data-stu-id="bf153-225">If you want to update your settings, select **Get started** under **Configure devices** in the tab to open device management on Intune.</span></span>

### <a name="exclude-files-from-asr-rules"></a><span data-ttu-id="bf153-226">Excluir arquivos de regras ASR</span><span class="sxs-lookup"><span data-stu-id="bf153-226">Exclude files from ASR rules</span></span>

<span data-ttu-id="bf153-227">O centro de segurança do Microsoft 365 coleta os nomes dos arquivos que talvez você queira excluir das detecções pelas regras de redução de superfície de ataque. [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules)</span><span class="sxs-lookup"><span data-stu-id="bf153-227">Microsoft 365 security center collects the names of the [files you might want to exclude](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-attack-surface-reduction#exclude-files-and-folders-from-asr-rules) from detections by attack surface reduction rules.</span></span> <span data-ttu-id="bf153-228">Ao excluir arquivos, você pode reduzir detecções de falsos positivos e implantar com mais confiança regras de redução de superfície de ataque no modo de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="bf153-228">By excluding files, you can reduce false positive detections and more confidently deploy attack surface reduction rules in block mode.</span></span>

<span data-ttu-id="bf153-229">As exclusões são gerenciadas no Microsoft Intune, mas o centro de segurança do Microsoft 365 fornece uma ferramenta de análise para ajudá-lo a entender os arquivos.</span><span class="sxs-lookup"><span data-stu-id="bf153-229">The exclusions are managed on Microsoft Intune, but Microsoft 365 security center provides an analysis tool to help you understand the files.</span></span> <span data-ttu-id="bf153-230">Para começar a coletar arquivos para exclusão, vá para a **guia Adicionar exclusões** na página relatório de regras de **Redução de superfície de** ataque.</span><span class="sxs-lookup"><span data-stu-id="bf153-230">To start collecting files for exclusion, go to the **Add exclusions** tab in the **Attack surface reduction rules** report page.</span></span>

>[!NOTE]  
><span data-ttu-id="bf153-231">A ferramenta analisa detecções por todas as regras de redução de superfície de ataque, mas [apenas algumas regras suportam exclusões.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr)</span><span class="sxs-lookup"><span data-stu-id="bf153-231">The tool analyzes detections by all attack surface reduction rules, but [only some rules support exclusions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-asr).</span></span>

![Guia Adicionar exclusões](../../media/add-exclusions-tab.png)

<span data-ttu-id="bf153-233">A tabela lista todos os nomes de arquivo detectados pelas regras de redução de superfície de ataque.</span><span class="sxs-lookup"><span data-stu-id="bf153-233">The table lists all the file names detected by your attack surface reduction rules.</span></span> <span data-ttu-id="bf153-234">Você pode selecionar arquivos para revisar o impacto de excluí-los:</span><span class="sxs-lookup"><span data-stu-id="bf153-234">You can select files to review the impact of excluding them:</span></span>

* <span data-ttu-id="bf153-235">Quantas detecções menos</span><span class="sxs-lookup"><span data-stu-id="bf153-235">How many fewer detections</span></span>
* <span data-ttu-id="bf153-236">Quantos menos dispositivos relatam as detecções</span><span class="sxs-lookup"><span data-stu-id="bf153-236">How many fewer devices report the detections</span></span>

<span data-ttu-id="bf153-237">Para obter uma lista dos arquivos selecionados com seus caminhos completos para exclusão, selecione **Obter caminhos de exclusão.**</span><span class="sxs-lookup"><span data-stu-id="bf153-237">To get a list of the selected files with their full paths for exclusion, select **Get exclusion paths**.</span></span>

<span data-ttu-id="bf153-238">Logs para a regra ASR Bloquear roubo de credenciais do subsistema de autoridade de segurança **local do Windows (lsass.exe)** capturam o aplicativo de origem **lsass.exe**.</span><span class="sxs-lookup"><span data-stu-id="bf153-238">Logs for the ASR rule **Block credential stealing from the Windows local security authority subsystem (lsass.exe)** capture the source app **lsass.exe**.</span></span> <span data-ttu-id="bf153-239">É um arquivo normal do sistema, mas capturado como o arquivo detectado.</span><span class="sxs-lookup"><span data-stu-id="bf153-239">It is a normal system file, but captured as the detected file.</span></span> <span data-ttu-id="bf153-240">Como resultado, a lista gerada de caminhos de exclusão incluirá esse arquivo.</span><span class="sxs-lookup"><span data-stu-id="bf153-240">As a result, the generated list of exclusion paths will include this file.</span></span> <span data-ttu-id="bf153-241">Para excluir o arquivo que disparou essa regra em vez **delsass.exe**, use o caminho para o aplicativo de origem em vez do arquivo detectado.</span><span class="sxs-lookup"><span data-stu-id="bf153-241">To exclude the file that triggered this rule instead of **lsass.exe**, use the path to the source app instead of the detected file.</span></span>

<span data-ttu-id="bf153-242">Para localizar o aplicativo de [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) origem, execute a seguinte consulta de busca avançada para esta regra específica (identificada pela regra ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span><span class="sxs-lookup"><span data-stu-id="bf153-242">To locate the source app, run the following [advanced hunting query](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting) for this specific rule (identified by rule ID 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2):</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType startswith "Asr"
| where AdditionalFields contains "9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2"
| project InitiatingProcessFolderPath, InitiatingProcessFileName
```

#### <a name="check-files-for-exclusion"></a><span data-ttu-id="bf153-243">Verificar arquivos para exclusão</span><span class="sxs-lookup"><span data-stu-id="bf153-243">Check files for exclusion</span></span>

<span data-ttu-id="bf153-244">Antes de excluir um arquivo do ASR, recomendamos que você inspecione o arquivo para determinar se ele realmente não é mal-intencionado.</span><span class="sxs-lookup"><span data-stu-id="bf153-244">Before excluding a file from ASR, we recommend that you inspect the file to determine if it's indeed not malicious.</span></span>

<span data-ttu-id="bf153-245">Para revisar um arquivo, use a página [de informações do arquivo](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) na Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="bf153-245">To review a file, use the [file information page](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-files) on Microsoft Defender Security Center.</span></span> <span data-ttu-id="bf153-246">A página fornece informações de prevalência e a taxa de detecção de antivírus VirusTotal.</span><span class="sxs-lookup"><span data-stu-id="bf153-246">The page provides prevalence information and the VirusTotal antivirus detection ratio.</span></span> <span data-ttu-id="bf153-247">Você também pode usar a página para enviar o arquivo para uma análise profunda.</span><span class="sxs-lookup"><span data-stu-id="bf153-247">You can also use the page to submit the file for deep analysis.</span></span>

<span data-ttu-id="bf153-248">Para localizar um arquivo detectado na Central de Segurança do Microsoft Defender, procure todas as detecções de ASR usando a seguinte consulta de busca avançada:</span><span class="sxs-lookup"><span data-stu-id="bf153-248">To locate a detected file in Microsoft Defender Security Center, search for all ASR detections using the following advanced hunting query:</span></span>

```kusto
MiscEvents
| where EventTime > ago(7d)
| where ActionType startswith "Asr"
| project FolderPath, FileName, SHA1, InitiatingProcessFolderPath, InitiatingProcessFileName, InitiatingProcessSHA1
```

<span data-ttu-id="bf153-249">Use **SHA1 ou** **InitiatingProcessSHA1** nos resultados para pesquisar o arquivo usando a barra de pesquisa universal na Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="bf153-249">Use the **SHA1** or the **InitiatingProcessSHA1** in the results to search for the file using the universal search bar in Microsoft Defender Security Center.</span></span>
