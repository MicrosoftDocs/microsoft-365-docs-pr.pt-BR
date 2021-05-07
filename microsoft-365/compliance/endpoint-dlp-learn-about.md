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
ms.openlocfilehash: b5aa6c737bc54129ce49378a7dcaf81e9d5c612f
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114099"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="12dd9-104">Saiba mais sobre a prevenção contra perda de dados do ponto de extremidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="12dd9-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="12dd9-105">Você pode usar a prevenção contra perda de dados (DLP) da Microsoft 365 para monitorar as ações que estão sendo executadas em itens que você concluiu a ser sensível e para ajudar a evitar o compartilhamento não intencional desses itens.</span><span class="sxs-lookup"><span data-stu-id="12dd9-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="12dd9-106">Para obter mais informações sobre DLP, consulte [Saiba mais sobre prevenção contra perda de dados](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="12dd9-106">For more information on DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="12dd9-107">**A prevenção contra perda de dados de pontos de extremidade** (Endpoint DLP) estende os recursos de proteção e monitoramento de atividades da DLP para itens confidenciais que estão em dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="12dd9-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="12dd9-108">Depois que os dispositivos estiverem integrados às soluções de conformidade do Microsoft 365, as informações sobre o que os usuários estão fazendo com itens confidenciais serão visíveis no [explorador de atividades](data-classification-activity-explorer.md) e você poderá aplicar ações de proteção a esses itens por meio das [políticas DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="12dd9-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="12dd9-109">Atividades do ponto de extremidade que você pode monitorar e executar</span><span class="sxs-lookup"><span data-stu-id="12dd9-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="12dd9-110">O Microsoft Endpoint DLP permite a auditoria e o gerenciamento dos seguintes tipos de atividades que os usuários têm em itens confidenciais em dispositivos com Windows 10.</span><span class="sxs-lookup"><span data-stu-id="12dd9-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> 

|<span data-ttu-id="12dd9-111">Atividade</span><span class="sxs-lookup"><span data-stu-id="12dd9-111">Activity</span></span> |<span data-ttu-id="12dd9-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="12dd9-112">Description</span></span>  | <span data-ttu-id="12dd9-113">Auditável/restringivel</span><span class="sxs-lookup"><span data-stu-id="12dd9-113">Auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="12dd9-114">carregar para o serviço de nuvem ou acessar por navegadores não permitidos</span><span class="sxs-lookup"><span data-stu-id="12dd9-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="12dd9-115">Detecta quando um usuário tenta carregar um item em um domínio de serviço restrito ou acessar um item por meio de um navegador.</span><span class="sxs-lookup"><span data-stu-id="12dd9-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="12dd9-116">Se eles estiverem usando um navegador listado na DLP como um navegador não permitido, a atividade de carregamento será bloqueada e o usuário será redirecionado para usar o Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="12dd9-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="12dd9-117">O Edge Chromium permitirá ou bloqueará o carregamento ou o acesso com base na configuração da política DLP</span><span class="sxs-lookup"><span data-stu-id="12dd9-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="12dd9-118">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="12dd9-118">auditable and restrictable</span></span>|
|<span data-ttu-id="12dd9-119">copiar para outro aplicativo</span><span class="sxs-lookup"><span data-stu-id="12dd9-119">copy to other app</span></span>    |<span data-ttu-id="12dd9-120">Detecta quando um usuário tenta copiar informações de um item protegido e, em seguida, colá-las em outro aplicativo, processo ou item.</span><span class="sxs-lookup"><span data-stu-id="12dd9-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="12dd9-121">A cópia e a colagem de informações dentro do mesmo aplicativo, processo ou item não é detectada por essa atividade.</span><span class="sxs-lookup"><span data-stu-id="12dd9-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="12dd9-122">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="12dd9-122">auditable and restrictable</span></span>|
|<span data-ttu-id="12dd9-123">copiar para mídia removível USB</span><span class="sxs-lookup"><span data-stu-id="12dd9-123">copy to USB removable media</span></span> |<span data-ttu-id="12dd9-124">Detecta quando um usuário tenta copiar um item ou informação para uma mídia removível ou dispositivo USB.</span><span class="sxs-lookup"><span data-stu-id="12dd9-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="12dd9-125">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="12dd9-125">auditable and restrictable</span></span>|
|<span data-ttu-id="12dd9-126">Copiar para um compartilhamento de rede</span><span class="sxs-lookup"><span data-stu-id="12dd9-126">copy to a network share</span></span>    |<span data-ttu-id="12dd9-127">Detecta quando um usuário tenta copiar um item para um compartilhamento de rede ou unidade de rede mapeada</span><span class="sxs-lookup"><span data-stu-id="12dd9-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="12dd9-128">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="12dd9-128">auditable and restrictable</span></span>|
|<span data-ttu-id="12dd9-129">imprimir um documento</span><span class="sxs-lookup"><span data-stu-id="12dd9-129">print a document</span></span>    |<span data-ttu-id="12dd9-130">Detecta quando um usuário tenta imprimir um item protegido em uma impressora local ou de rede.</span><span class="sxs-lookup"><span data-stu-id="12dd9-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="12dd9-131">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="12dd9-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="12dd9-132">copiar para uma sessão remota</span><span class="sxs-lookup"><span data-stu-id="12dd9-132">copy to a remote session</span></span>|<span data-ttu-id="12dd9-133">Detecta quando um usuário tenta copiar um item para uma sessão remota da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="12dd9-133">Detects when a user attempts to copy an item to a remote desktop session</span></span> |  <span data-ttu-id="12dd9-134">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="12dd9-134">auditable and restrictable</span></span>|
|<span data-ttu-id="12dd9-135">copiar para um dispositivo Bluetooth</span><span class="sxs-lookup"><span data-stu-id="12dd9-135">copy to a Bluetooth device</span></span>|<span data-ttu-id="12dd9-136">Detecta quando um usuário tenta copiar um item para um aplicativo Bluetooth não conectado (conforme definido na lista de aplicativos Bluetooth não relacionados nas configurações de DLP do ponto de extremidade).</span><span class="sxs-lookup"><span data-stu-id="12dd9-136">Detects when a user attempts to copy an item to an unallowed Bluetooth app (as defined in the list of unallowed Bluetooth aps in Endpoint DLP settings).</span></span>| <span data-ttu-id="12dd9-137">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="12dd9-137">auditable and restrictable</span></span>|
|<span data-ttu-id="12dd9-138">criar um Item</span><span class="sxs-lookup"><span data-stu-id="12dd9-138">create an item</span></span>|<span data-ttu-id="12dd9-139">Detecta quando um usuário cria um item</span><span class="sxs-lookup"><span data-stu-id="12dd9-139">Detects when a user creates an item</span></span>| <span data-ttu-id="12dd9-140">auditável</span><span class="sxs-lookup"><span data-stu-id="12dd9-140">auditable</span></span>|
|<span data-ttu-id="12dd9-141">renomear um item</span><span class="sxs-lookup"><span data-stu-id="12dd9-141">rename an item</span></span>|<span data-ttu-id="12dd9-142">Detecta quando um usuário renomeia um item</span><span class="sxs-lookup"><span data-stu-id="12dd9-142">Detects when a user renames an item</span></span>| <span data-ttu-id="12dd9-143">auditável</span><span class="sxs-lookup"><span data-stu-id="12dd9-143">auditable</span></span>|

 ## <a name="monitored-files"></a><span data-ttu-id="12dd9-144">Arquivos monitorados</span><span class="sxs-lookup"><span data-stu-id="12dd9-144">Monitored files</span></span>

<span data-ttu-id="12dd9-145">Endpoint DLP oferece suporte ao monitoramento destes tipos de arquivo:</span><span class="sxs-lookup"><span data-stu-id="12dd9-145">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="12dd9-146">Arquivos do Word</span><span class="sxs-lookup"><span data-stu-id="12dd9-146">Word files</span></span>
- <span data-ttu-id="12dd9-147">Arquivos do PowerPoint</span><span class="sxs-lookup"><span data-stu-id="12dd9-147">PowerPoint files</span></span>
- <span data-ttu-id="12dd9-148">Arquivos do Excel</span><span class="sxs-lookup"><span data-stu-id="12dd9-148">Excel files</span></span>
- <span data-ttu-id="12dd9-149">Arquivos PDF</span><span class="sxs-lookup"><span data-stu-id="12dd9-149">PDF files</span></span>
- <span data-ttu-id="12dd9-150">Arquivos .csv</span><span class="sxs-lookup"><span data-stu-id="12dd9-150">.csv files</span></span>
- <span data-ttu-id="12dd9-151">Arquivos .tsv</span><span class="sxs-lookup"><span data-stu-id="12dd9-151">.tsv files</span></span>
- <span data-ttu-id="12dd9-152">Arquivos .txt</span><span class="sxs-lookup"><span data-stu-id="12dd9-152">.txt files</span></span>
- <span data-ttu-id="12dd9-153">Arquivos .rtf</span><span class="sxs-lookup"><span data-stu-id="12dd9-153">.rtf files</span></span>
- <span data-ttu-id="12dd9-154">Arquivos .c</span><span class="sxs-lookup"><span data-stu-id="12dd9-154">.c files</span></span>
- <span data-ttu-id="12dd9-155">Arquivos .class</span><span class="sxs-lookup"><span data-stu-id="12dd9-155">.class files</span></span>
- <span data-ttu-id="12dd9-156">Arquivos .cpp</span><span class="sxs-lookup"><span data-stu-id="12dd9-156">.cpp files</span></span>
- <span data-ttu-id="12dd9-157">Arquivos .cs</span><span class="sxs-lookup"><span data-stu-id="12dd9-157">.cs files</span></span>
- <span data-ttu-id="12dd9-158">Arquivos .h</span><span class="sxs-lookup"><span data-stu-id="12dd9-158">.h files</span></span>
- <span data-ttu-id="12dd9-159">Arquivos .java</span><span class="sxs-lookup"><span data-stu-id="12dd9-159">.java files</span></span>
 
<span data-ttu-id="12dd9-160">Por padrão, o DLP do endpoint audita as atividades para esses tipos de arquivo, mesmo se não houver uma correspondência de política.</span><span class="sxs-lookup"><span data-stu-id="12dd9-160">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="12dd9-161">Se quiser apenas monitorar dados de correspondências de política, você pode desligar **Sempre auditar atividade de arquivo para dispositivos** nas configurações globais de DLP do endpoint.</span><span class="sxs-lookup"><span data-stu-id="12dd9-161">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="12dd9-162">Se esta configuração estiver ativada, as atividades em qualquer arquivo do Word, PowerPoint, Excel, PDF e .CSV serão sempre auditadas, mesmo que o dispositivo não seja direcionado por nenhuma política.</span><span class="sxs-lookup"><span data-stu-id="12dd9-162">If this setting is on, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited even if the device is not targeted by any policy.</span></span>

<span data-ttu-id="12dd9-163">O DLP do ponto de extremidade monitora a atividade com base no tipo MIME, portanto, as atividades serão capturadas mesmo se a extensão do arquivo for alterada.</span><span class="sxs-lookup"><span data-stu-id="12dd9-163">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> 

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="12dd9-164">O que é diferente no Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="12dd9-164">What's different in Endpoint DLP</span></span>

<span data-ttu-id="12dd9-165">Há alguns conceitos adicionais que você precisa saber antes de mergulhar no Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="12dd9-165">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="12dd9-166">Habilitar o gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="12dd9-166">Enabling Device management</span></span>

<span data-ttu-id="12dd9-167">O gerenciamento de dispositivos é a funcionalidade que habilita o conjunto de telemetria de dispositivos e a reúne para as soluções do Centro de conformidade do Microsoft 365, como Endpoint DLP e [gerenciamento de risco interno](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="12dd9-167">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="12dd9-168">Será necessário integrar todos os dispositivos que você deseja usar como locais nas políticas DLP.</span><span class="sxs-lookup"><span data-stu-id="12dd9-168">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="12dd9-169">![habilite o gerenciamento de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="12dd9-169">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="12dd9-170">A integração e a remoção são manipuladas por meio de scripts que você baixa no centro de gerenciamento de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="12dd9-170">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="12dd9-171">O centro tem scripts personalizados para cada um desses métodos de implantação:</span><span class="sxs-lookup"><span data-stu-id="12dd9-171">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="12dd9-172">script local (até 10 máquinas)</span><span class="sxs-lookup"><span data-stu-id="12dd9-172">local script (up to 10 machines)</span></span>
- <span data-ttu-id="12dd9-173">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="12dd9-173">Group policy</span></span>
- <span data-ttu-id="12dd9-174">System Center Configuration Manager (versão 1610 ou posterior)</span><span class="sxs-lookup"><span data-stu-id="12dd9-174">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="12dd9-175">Gerenciamento de dispositivos móveis/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="12dd9-175">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="12dd9-176">Scripts de integração VDI para máquinas não persistentes</span><span class="sxs-lookup"><span data-stu-id="12dd9-176">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="12dd9-177">![página de integração de dispositivos](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="12dd9-177">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="12dd9-178">Use os procedimentos no [Introdução ao Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) a dispositivos integrados.</span><span class="sxs-lookup"><span data-stu-id="12dd9-178">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="12dd9-179">Se você tiver dispositivos integrados por meio do [Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/), esses dispositivos aparecerão automaticamente na lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="12dd9-179">If you have onboarded devices through [Microsoft Defender for Endpoint](/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="12dd9-180">![lista de dispositivos gerenciados](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="12dd9-180">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="12dd9-181">Exibir dados de DLP do Endpoint</span><span class="sxs-lookup"><span data-stu-id="12dd9-181">Viewing Endpoint DLP data</span></span>

<span data-ttu-id="12dd9-182">Visualize os alertas relacionados às políticas DLP aplicadas em dispositivos de ponto de extremidade no [Painel de Gerenciamento de Alertas DLP](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="12dd9-182">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="12dd9-183">![Informações sobre alertas](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="12dd9-183">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="12dd9-184">Você também pode exibir os detalhes do evento associado com metadados ricos no mesmo painel</span><span class="sxs-lookup"><span data-stu-id="12dd9-184">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="12dd9-185">![informações do evento](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="12dd9-185">![event info](../media/Event-info-1.png)</span></span>

<span data-ttu-id="12dd9-186">Após a integração de um dispositivo, as informações sobre as atividades auditadas fluem no explorador de atividades mesmo antes de você configurar e implantar as políticas DLP que têm dispositivos como um local.</span><span class="sxs-lookup"><span data-stu-id="12dd9-186">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="12dd9-187">![eventos do DLP do ponto de extremidade no gerenciador de atividades](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="12dd9-187">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="12dd9-188">O Endpoint DLP coleta informações abrangentes sobre atividades auditadas.</span><span class="sxs-lookup"><span data-stu-id="12dd9-188">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="12dd9-189">Por exemplo, se um arquivo for copiado para uma mídia USB removível, você verá esses atributos nos detalhes da atividade:</span><span class="sxs-lookup"><span data-stu-id="12dd9-189">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="12dd9-190">tipo de atividade</span><span class="sxs-lookup"><span data-stu-id="12dd9-190">activity type</span></span>
- <span data-ttu-id="12dd9-191">IP do Cliente</span><span class="sxs-lookup"><span data-stu-id="12dd9-191">client IP</span></span>
- <span data-ttu-id="12dd9-192">caminho do arquivo de destino</span><span class="sxs-lookup"><span data-stu-id="12dd9-192">target file path</span></span>
- <span data-ttu-id="12dd9-193">carimbo de data/hora ocorrido</span><span class="sxs-lookup"><span data-stu-id="12dd9-193">happened timestamp</span></span>
- <span data-ttu-id="12dd9-194">nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="12dd9-194">file name</span></span>
- <span data-ttu-id="12dd9-195">usuário</span><span class="sxs-lookup"><span data-stu-id="12dd9-195">user</span></span>
- <span data-ttu-id="12dd9-196">extensão do arquivo</span><span class="sxs-lookup"><span data-stu-id="12dd9-196">file extension</span></span>
- <span data-ttu-id="12dd9-197">tamanho do arquivo</span><span class="sxs-lookup"><span data-stu-id="12dd9-197">file size</span></span>
- <span data-ttu-id="12dd9-198">tipo de informação confidencial (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="12dd9-198">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="12dd9-199">valor SHA1</span><span class="sxs-lookup"><span data-stu-id="12dd9-199">sha1 value</span></span>
- <span data-ttu-id="12dd9-200">valor SHA256</span><span class="sxs-lookup"><span data-stu-id="12dd9-200">sha256 value</span></span>
- <span data-ttu-id="12dd9-201">nome do arquivo anterior</span><span class="sxs-lookup"><span data-stu-id="12dd9-201">previous file name</span></span>
- <span data-ttu-id="12dd9-202">localização</span><span class="sxs-lookup"><span data-stu-id="12dd9-202">location</span></span>
- <span data-ttu-id="12dd9-203">primário</span><span class="sxs-lookup"><span data-stu-id="12dd9-203">parent</span></span>
- <span data-ttu-id="12dd9-204">FilePath</span><span class="sxs-lookup"><span data-stu-id="12dd9-204">filepath</span></span>
- <span data-ttu-id="12dd9-205">Tipo de local de origem</span><span class="sxs-lookup"><span data-stu-id="12dd9-205">source location type</span></span>
- <span data-ttu-id="12dd9-206">plataforma</span><span class="sxs-lookup"><span data-stu-id="12dd9-206">platform</span></span>
- <span data-ttu-id="12dd9-207">nome do dispositivo</span><span class="sxs-lookup"><span data-stu-id="12dd9-207">device name</span></span>
- <span data-ttu-id="12dd9-208">Tipo de local de destino</span><span class="sxs-lookup"><span data-stu-id="12dd9-208">destination location type</span></span>
- <span data-ttu-id="12dd9-209">aplicativo que executou a cópia</span><span class="sxs-lookup"><span data-stu-id="12dd9-209">application that performed the copy</span></span>
- <span data-ttu-id="12dd9-210">ID de dispositivo do Microsoft Defender para Ponto de Extremidade (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="12dd9-210">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="12dd9-211">fabricante do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="12dd9-211">removable media device manufacturer</span></span>
- <span data-ttu-id="12dd9-212">modelo do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="12dd9-212">removable media device model</span></span>
- <span data-ttu-id="12dd9-213">número de série do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="12dd9-213">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="12dd9-214">![copiar para atributos de atividades USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="12dd9-214">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="12dd9-215">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="12dd9-215">Next steps</span></span>

<span data-ttu-id="12dd9-216">Agora que você aprendeu sobre o Endpoint DLP, as próximas etapas são:</span><span class="sxs-lookup"><span data-stu-id="12dd9-216">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="12dd9-217">Introdução à prevenção contra perda de dados do ponto de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="12dd9-217">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="12dd9-218">Usar a prevenção contra perda de dados do Ponto de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="12dd9-218">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="12dd9-219">Confira também</span><span class="sxs-lookup"><span data-stu-id="12dd9-219">See also</span></span>

- [<span data-ttu-id="12dd9-220">Introdução à prevenção contra perda de dados do Ponto de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="12dd9-220">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="12dd9-221">Usar a prevenção contra perda de dados do Ponto de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="12dd9-221">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="12dd9-222">Saiba mais sobre prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="12dd9-222">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="12dd9-223">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="12dd9-223">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="12dd9-224">Começar a usar o Explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="12dd9-224">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="12dd9-225">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="12dd9-225">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="12dd9-226">Gerenciamento de risco interno</span><span class="sxs-lookup"><span data-stu-id="12dd9-226">Insider Risk management</span></span>](insider-risk-management.md)