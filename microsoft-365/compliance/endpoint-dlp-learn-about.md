---
title: Saiba mais sobre a prevenção contra perda de dados do Microsoft 365 Endpoint
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'A prevenção contra perda de dados do Microsoft 365 Endpoint estende o monitoramento de atividades de arquivo e ações de proteção desses arquivos para os pontos de extremidade. Os arquivos do são visíveis nas soluções do Centro de conformidade do Microsoft 365 '
ms.openlocfilehash: c97368dd48515dc787dbac66aa93844889efbdbc
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314411"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="8ffb3-104">Saiba mais sobre a prevenção contra perda de dados do ponto de extremidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8ffb3-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="8ffb3-105">Você pode usar a prevenção contra perda de dados (DLP) da Microsoft 365 para monitorar as ações que estão sendo executadas em itens que você concluiu a ser sensível e para ajudar a evitar o compartilhamento não intencional desses itens.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="8ffb3-106">Para obter mais informações sobre DLP, consulte [Saiba mais sobre prevenção contra perda de dados](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="8ffb3-106">For more information on DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="8ffb3-107">**A prevenção contra perda de dados de pontos de extremidade** (Endpoint DLP) estende os recursos de proteção e monitoramento de atividades da DLP para itens confidenciais que estão em dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="8ffb3-108">Depois que os dispositivos estiverem integrados às soluções de conformidade do Microsoft 365, as informações sobre o que os usuários estão fazendo com itens confidenciais serão visíveis no [explorador de atividades](data-classification-activity-explorer.md) e você poderá aplicar ações de proteção a esses itens por meio das [políticas DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="8ffb3-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

> [!TIP]
> <span data-ttu-id="8ffb3-109">Se você estiver procurando controle de dispositivo para repositório removível, consulte [Controle de acesso para repositório removível do controle de dispositivo do Microsoft Defender para Ponto de Extremidade](../security/defender-endpoint/device-control-removable-storage-access-control.md#microsoft-defender-for-endpoint-device-control-removable-storage-access-control).</span><span class="sxs-lookup"><span data-stu-id="8ffb3-109">If you are looking for device control for removable storage, see [Microsoft Defender for Endpoint Device Control Removable Storage Access Control](../security/defender-endpoint/device-control-removable-storage-access-control.md#microsoft-defender-for-endpoint-device-control-removable-storage-access-control).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="8ffb3-110">Atividades do ponto de extremidade que você pode monitorar e executar</span><span class="sxs-lookup"><span data-stu-id="8ffb3-110">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="8ffb3-111">O Microsoft Endpoint DLP permite a auditoria e o gerenciamento dos seguintes tipos de atividades que os usuários têm em itens confidenciais em dispositivos com Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-111">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

|<span data-ttu-id="8ffb3-112">Atividade</span><span class="sxs-lookup"><span data-stu-id="8ffb3-112">Activity</span></span> |<span data-ttu-id="8ffb3-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="8ffb3-113">Description</span></span>  | <span data-ttu-id="8ffb3-114">Auditável/restringivel</span><span class="sxs-lookup"><span data-stu-id="8ffb3-114">Auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="8ffb3-115">carregar para o serviço de nuvem ou acessar por navegadores não permitidos</span><span class="sxs-lookup"><span data-stu-id="8ffb3-115">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="8ffb3-116">Detecta quando um usuário tenta carregar um item em um domínio de serviço restrito ou acessar um item por meio de um navegador.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-116">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="8ffb3-117">Se eles estiverem usando um navegador listado na DLP como um navegador não permitido, a atividade de carregamento será bloqueada e o usuário será redirecionado para usar o Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-117">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="8ffb3-118">O Edge Chromium permitirá ou bloqueará o carregamento ou o acesso com base na configuração da política DLP</span><span class="sxs-lookup"><span data-stu-id="8ffb3-118">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="8ffb3-119">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="8ffb3-119">auditable and restrictable</span></span>|
|<span data-ttu-id="8ffb3-120">copiar para outro aplicativo</span><span class="sxs-lookup"><span data-stu-id="8ffb3-120">copy to other app</span></span>    |<span data-ttu-id="8ffb3-121">Detecta quando um usuário tenta copiar informações de um item protegido e, em seguida, colá-las em outro aplicativo, processo ou item.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-121">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="8ffb3-122">A cópia e a colagem de informações dentro do mesmo aplicativo, processo ou item não é detectada por essa atividade.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-122">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="8ffb3-123">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="8ffb3-123">auditable and restrictable</span></span>|
|<span data-ttu-id="8ffb3-124">copiar para mídia removível USB</span><span class="sxs-lookup"><span data-stu-id="8ffb3-124">copy to USB removable media</span></span> |<span data-ttu-id="8ffb3-125">Detecta quando um usuário tenta copiar um item ou informação para uma mídia removível ou dispositivo USB.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-125">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="8ffb3-126">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="8ffb3-126">auditable and restrictable</span></span>|
|<span data-ttu-id="8ffb3-127">Copiar para um compartilhamento de rede</span><span class="sxs-lookup"><span data-stu-id="8ffb3-127">copy to a network share</span></span>    |<span data-ttu-id="8ffb3-128">Detecta quando um usuário tenta copiar um item para um compartilhamento de rede ou unidade de rede mapeada</span><span class="sxs-lookup"><span data-stu-id="8ffb3-128">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="8ffb3-129">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="8ffb3-129">auditable and restrictable</span></span>|
|<span data-ttu-id="8ffb3-130">imprimir um documento</span><span class="sxs-lookup"><span data-stu-id="8ffb3-130">print a document</span></span>    |<span data-ttu-id="8ffb3-131">Detecta quando um usuário tenta imprimir um item protegido em uma impressora local ou de rede.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-131">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="8ffb3-132">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="8ffb3-132">auditable and restrictable</span></span>         |
|<span data-ttu-id="8ffb3-133">copiar para uma sessão remota</span><span class="sxs-lookup"><span data-stu-id="8ffb3-133">copy to a remote session</span></span>|<span data-ttu-id="8ffb3-134">Detecta quando um usuário tenta copiar um item para uma sessão remota da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="8ffb3-134">Detects when a user attempts to copy an item to a remote desktop session</span></span> |  <span data-ttu-id="8ffb3-135">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="8ffb3-135">auditable and restrictable</span></span>|
|<span data-ttu-id="8ffb3-136">copiar para um dispositivo Bluetooth</span><span class="sxs-lookup"><span data-stu-id="8ffb3-136">copy to a Bluetooth device</span></span>|<span data-ttu-id="8ffb3-137">Detecta quando um usuário tenta copiar um item para um aplicativo Bluetooth não conectado (conforme definido na lista de aplicativos Bluetooth não relacionados nas configurações de DLP do ponto de extremidade).</span><span class="sxs-lookup"><span data-stu-id="8ffb3-137">Detects when a user attempts to copy an item to an unallowed Bluetooth app (as defined in the list of unallowed Bluetooth aps in Endpoint DLP settings).</span></span>| <span data-ttu-id="8ffb3-138">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="8ffb3-138">auditable and restrictable</span></span>|
|<span data-ttu-id="8ffb3-139">criar um Item</span><span class="sxs-lookup"><span data-stu-id="8ffb3-139">create an item</span></span>|<span data-ttu-id="8ffb3-140">Detecta quando um usuário cria um item</span><span class="sxs-lookup"><span data-stu-id="8ffb3-140">Detects when a user creates an item</span></span>| <span data-ttu-id="8ffb3-141">auditável</span><span class="sxs-lookup"><span data-stu-id="8ffb3-141">auditable</span></span>|
|<span data-ttu-id="8ffb3-142">renomear um item</span><span class="sxs-lookup"><span data-stu-id="8ffb3-142">rename an item</span></span>|<span data-ttu-id="8ffb3-143">Detecta quando um usuário renomeia um item</span><span class="sxs-lookup"><span data-stu-id="8ffb3-143">Detects when a user renames an item</span></span>| <span data-ttu-id="8ffb3-144">auditável</span><span class="sxs-lookup"><span data-stu-id="8ffb3-144">auditable</span></span>|

## <a name="monitored-files"></a><span data-ttu-id="8ffb3-145">Arquivos monitorados</span><span class="sxs-lookup"><span data-stu-id="8ffb3-145">Monitored files</span></span>

<span data-ttu-id="8ffb3-146">Endpoint DLP oferece suporte ao monitoramento destes tipos de arquivo:</span><span class="sxs-lookup"><span data-stu-id="8ffb3-146">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="8ffb3-147">Arquivos do Word</span><span class="sxs-lookup"><span data-stu-id="8ffb3-147">Word files</span></span>
- <span data-ttu-id="8ffb3-148">Arquivos do PowerPoint</span><span class="sxs-lookup"><span data-stu-id="8ffb3-148">PowerPoint files</span></span>
- <span data-ttu-id="8ffb3-149">Arquivos do Excel</span><span class="sxs-lookup"><span data-stu-id="8ffb3-149">Excel files</span></span>
- <span data-ttu-id="8ffb3-150">Arquivos PDF</span><span class="sxs-lookup"><span data-stu-id="8ffb3-150">PDF files</span></span>
- <span data-ttu-id="8ffb3-151">Arquivos .csv</span><span class="sxs-lookup"><span data-stu-id="8ffb3-151">.csv files</span></span>
- <span data-ttu-id="8ffb3-152">Arquivos .tsv</span><span class="sxs-lookup"><span data-stu-id="8ffb3-152">.tsv files</span></span>
- <span data-ttu-id="8ffb3-153">Arquivos .txt</span><span class="sxs-lookup"><span data-stu-id="8ffb3-153">.txt files</span></span>
- <span data-ttu-id="8ffb3-154">Arquivos .rtf</span><span class="sxs-lookup"><span data-stu-id="8ffb3-154">.rtf files</span></span>
- <span data-ttu-id="8ffb3-155">Arquivos .c</span><span class="sxs-lookup"><span data-stu-id="8ffb3-155">.c files</span></span>
- <span data-ttu-id="8ffb3-156">Arquivos .class</span><span class="sxs-lookup"><span data-stu-id="8ffb3-156">.class files</span></span>
- <span data-ttu-id="8ffb3-157">Arquivos .cpp</span><span class="sxs-lookup"><span data-stu-id="8ffb3-157">.cpp files</span></span>
- <span data-ttu-id="8ffb3-158">Arquivos .cs</span><span class="sxs-lookup"><span data-stu-id="8ffb3-158">.cs files</span></span>
- <span data-ttu-id="8ffb3-159">Arquivos .h</span><span class="sxs-lookup"><span data-stu-id="8ffb3-159">.h files</span></span>
- <span data-ttu-id="8ffb3-160">Arquivos .java</span><span class="sxs-lookup"><span data-stu-id="8ffb3-160">.java files</span></span>

<span data-ttu-id="8ffb3-161">Por padrão, o DLP do endpoint audita as atividades para esses tipos de arquivo, mesmo se não houver uma correspondência de política.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-161">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="8ffb3-162">Se quiser apenas monitorar dados de correspondências de política, você pode desligar **Sempre auditar atividade de arquivo para dispositivos** nas configurações globais de DLP do endpoint.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-162">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="8ffb3-163">Se esta configuração estiver ativada, as atividades em qualquer arquivo do Word, PowerPoint, Excel, PDF e .CSV serão sempre auditadas, mesmo que o dispositivo não seja direcionado por nenhuma política.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-163">If this setting is on, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited even if the device is not targeted by any policy.</span></span>

<span data-ttu-id="8ffb3-164">O DLP do ponto de extremidade monitora a atividade com base no tipo MIME, portanto, as atividades serão capturadas mesmo se a extensão do arquivo for alterada.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-164">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span>

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="8ffb3-165">O que é diferente no Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="8ffb3-165">What's different in Endpoint DLP</span></span>

<span data-ttu-id="8ffb3-166">Há alguns conceitos adicionais que você precisa saber antes de mergulhar no Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-166">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="8ffb3-167">Habilitar o gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="8ffb3-167">Enabling Device management</span></span>

<span data-ttu-id="8ffb3-168">O gerenciamento de dispositivos é a funcionalidade que habilita o conjunto de telemetria de dispositivos e a reúne para as soluções do Centro de conformidade do Microsoft 365, como Endpoint DLP e [gerenciamento de risco interno](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="8ffb3-168">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="8ffb3-169">Será necessário integrar todos os dispositivos que você deseja usar como locais nas políticas DLP.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-169">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8ffb3-170">![habilite o gerenciamento de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="8ffb3-170">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="8ffb3-171">A integração e a remoção são manipuladas por meio de scripts que você baixa no centro de gerenciamento de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-171">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="8ffb3-172">O centro tem scripts personalizados para cada um desses métodos de implantação:</span><span class="sxs-lookup"><span data-stu-id="8ffb3-172">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="8ffb3-173">script local (até 10 máquinas)</span><span class="sxs-lookup"><span data-stu-id="8ffb3-173">local script (up to 10 machines)</span></span>
- <span data-ttu-id="8ffb3-174">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="8ffb3-174">Group policy</span></span>
- <span data-ttu-id="8ffb3-175">System Center Configuration Manager (versão 1610 ou posterior)</span><span class="sxs-lookup"><span data-stu-id="8ffb3-175">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="8ffb3-176">Gerenciamento de dispositivos móveis/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8ffb3-176">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="8ffb3-177">Scripts de integração VDI para máquinas não persistentes</span><span class="sxs-lookup"><span data-stu-id="8ffb3-177">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8ffb3-178">![página de integração de dispositivos](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="8ffb3-178">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="8ffb3-179">Use os procedimentos no [Introdução ao Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) a dispositivos integrados.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-179">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="8ffb3-180">Se você tiver dispositivos integrados por meio do [Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/), esses dispositivos aparecerão automaticamente na lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-180">If you have onboarded devices through [Microsoft Defender for Endpoint](/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8ffb3-181">![lista de dispositivos gerenciados](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="8ffb3-181">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="8ffb3-182">Exibir dados de DLP do Endpoint</span><span class="sxs-lookup"><span data-stu-id="8ffb3-182">Viewing Endpoint DLP data</span></span>

<span data-ttu-id="8ffb3-183">Visualize os alertas relacionados às políticas DLP aplicadas em dispositivos de ponto de extremidade no [Painel de Gerenciamento de Alertas DLP](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8ffb3-183">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8ffb3-184">![Informações sobre alertas](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="8ffb3-184">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="8ffb3-185">Você também pode exibir os detalhes do evento associado com metadados ricos no mesmo painel</span><span class="sxs-lookup"><span data-stu-id="8ffb3-185">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8ffb3-186">![informações do evento](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="8ffb3-186">![event info](../media/Event-info-1.png)</span></span>

<span data-ttu-id="8ffb3-187">Após a integração de um dispositivo, as informações sobre as atividades auditadas fluem no explorador de atividades mesmo antes de você configurar e implantar as políticas DLP que têm dispositivos como um local.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-187">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8ffb3-188">![eventos do DLP do ponto de extremidade no gerenciador de atividades](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="8ffb3-188">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="8ffb3-189">O Endpoint DLP coleta informações abrangentes sobre atividades auditadas.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-189">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="8ffb3-190">Por exemplo, se um arquivo for copiado para uma mídia USB removível, você verá esses atributos nos detalhes da atividade:</span><span class="sxs-lookup"><span data-stu-id="8ffb3-190">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="8ffb3-191">tipo de atividade</span><span class="sxs-lookup"><span data-stu-id="8ffb3-191">activity type</span></span>
- <span data-ttu-id="8ffb3-192">IP do Cliente</span><span class="sxs-lookup"><span data-stu-id="8ffb3-192">client IP</span></span>
- <span data-ttu-id="8ffb3-193">caminho do arquivo de destino</span><span class="sxs-lookup"><span data-stu-id="8ffb3-193">target file path</span></span>
- <span data-ttu-id="8ffb3-194">carimbo de data/hora ocorrido</span><span class="sxs-lookup"><span data-stu-id="8ffb3-194">happened timestamp</span></span>
- <span data-ttu-id="8ffb3-195">nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="8ffb3-195">file name</span></span>
- <span data-ttu-id="8ffb3-196">usuário</span><span class="sxs-lookup"><span data-stu-id="8ffb3-196">user</span></span>
- <span data-ttu-id="8ffb3-197">extensão do arquivo</span><span class="sxs-lookup"><span data-stu-id="8ffb3-197">file extension</span></span>
- <span data-ttu-id="8ffb3-198">tamanho do arquivo</span><span class="sxs-lookup"><span data-stu-id="8ffb3-198">file size</span></span>
- <span data-ttu-id="8ffb3-199">tipo de informação confidencial (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="8ffb3-199">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="8ffb3-200">valor SHA1</span><span class="sxs-lookup"><span data-stu-id="8ffb3-200">sha1 value</span></span>
- <span data-ttu-id="8ffb3-201">valor SHA256</span><span class="sxs-lookup"><span data-stu-id="8ffb3-201">sha256 value</span></span>
- <span data-ttu-id="8ffb3-202">nome do arquivo anterior</span><span class="sxs-lookup"><span data-stu-id="8ffb3-202">previous file name</span></span>
- <span data-ttu-id="8ffb3-203">localização</span><span class="sxs-lookup"><span data-stu-id="8ffb3-203">location</span></span>
- <span data-ttu-id="8ffb3-204">primário</span><span class="sxs-lookup"><span data-stu-id="8ffb3-204">parent</span></span>
- <span data-ttu-id="8ffb3-205">FilePath</span><span class="sxs-lookup"><span data-stu-id="8ffb3-205">filepath</span></span>
- <span data-ttu-id="8ffb3-206">Tipo de local de origem</span><span class="sxs-lookup"><span data-stu-id="8ffb3-206">source location type</span></span>
- <span data-ttu-id="8ffb3-207">plataforma</span><span class="sxs-lookup"><span data-stu-id="8ffb3-207">platform</span></span>
- <span data-ttu-id="8ffb3-208">nome do dispositivo</span><span class="sxs-lookup"><span data-stu-id="8ffb3-208">device name</span></span>
- <span data-ttu-id="8ffb3-209">Tipo de local de destino</span><span class="sxs-lookup"><span data-stu-id="8ffb3-209">destination location type</span></span>
- <span data-ttu-id="8ffb3-210">aplicativo que executou a cópia</span><span class="sxs-lookup"><span data-stu-id="8ffb3-210">application that performed the copy</span></span>
- <span data-ttu-id="8ffb3-211">ID de dispositivo do Microsoft Defender para Ponto de Extremidade (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="8ffb3-211">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="8ffb3-212">fabricante do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="8ffb3-212">removable media device manufacturer</span></span>
- <span data-ttu-id="8ffb3-213">modelo do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="8ffb3-213">removable media device model</span></span>
- <span data-ttu-id="8ffb3-214">número de série do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="8ffb3-214">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8ffb3-215">![copiar para atributos de atividades USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="8ffb3-215">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="8ffb3-216">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="8ffb3-216">Next steps</span></span>

<span data-ttu-id="8ffb3-217">Agora que você aprendeu sobre o Endpoint DLP, as próximas etapas são:</span><span class="sxs-lookup"><span data-stu-id="8ffb3-217">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1. [<span data-ttu-id="8ffb3-218">Introdução à prevenção contra perda de dados do Ponto de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ffb3-218">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="8ffb3-219">Usar a prevenção contra perda de dados do Ponto de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ffb3-219">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="8ffb3-220">Confira também</span><span class="sxs-lookup"><span data-stu-id="8ffb3-220">See also</span></span>

- [<span data-ttu-id="8ffb3-221">Introdução à prevenção contra perda de dados do Ponto de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ffb3-221">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="8ffb3-222">Usar a prevenção contra perda de dados do Ponto de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="8ffb3-222">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="8ffb3-223">Saiba mais sobre prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="8ffb3-223">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="8ffb3-224">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="8ffb3-224">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="8ffb3-225">Começar a usar o Explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="8ffb3-225">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="8ffb3-226">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8ffb3-226">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="8ffb3-227">Gerenciamento de risco interno</span><span class="sxs-lookup"><span data-stu-id="8ffb3-227">Insider Risk management</span></span>](insider-risk-management.md)
