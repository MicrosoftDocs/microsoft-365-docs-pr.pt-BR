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
ms.openlocfilehash: d5394499b5514e6e0a49f958a62e70cde61ebf44
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279305"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="aead5-104">Saiba mais sobre a prevenção contra perda de dados do ponto de extremidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aead5-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="aead5-105">Você pode usar a prevenção contra perda de dados (DLP) da Microsoft 365 para monitorar as ações que estão sendo executadas em itens que você concluiu a ser sensível e para ajudar a evitar o compartilhamento não intencional desses itens.</span><span class="sxs-lookup"><span data-stu-id="aead5-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="aead5-106">Para mais informações sobre a DLP, confira [Visão geral das políticas de prevenção contra perda de dados](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="aead5-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="aead5-107">**A prevenção contra perda de dados de pontos de extremidade** (Endpoint DLP) estende os recursos de proteção e monitoramento de atividades da DLP para itens confidenciais que estão em dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="aead5-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="aead5-108">Depois que os dispositivos estiverem integrados às soluções de conformidade do Microsoft 365, as informações sobre o que os usuários estão fazendo com itens confidenciais serão visíveis no [explorador de atividades](data-classification-activity-explorer.md) e você poderá aplicar ações de proteção a esses itens por meio das [políticas DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="aead5-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="aead5-109">Atividades do ponto de extremidade que você pode monitorar e executar</span><span class="sxs-lookup"><span data-stu-id="aead5-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="aead5-110">O Microsoft Endpoint DLP permite a auditoria e o gerenciamento dos seguintes tipos de atividades que os usuários têm em itens confidenciais em dispositivos com Windows 10.</span><span class="sxs-lookup"><span data-stu-id="aead5-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> 

|<span data-ttu-id="aead5-111">atividade</span><span class="sxs-lookup"><span data-stu-id="aead5-111">activity</span></span> |<span data-ttu-id="aead5-112">descrição</span><span class="sxs-lookup"><span data-stu-id="aead5-112">description</span></span>  | <span data-ttu-id="aead5-113">auditável/restringivel</span><span class="sxs-lookup"><span data-stu-id="aead5-113">auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="aead5-114">carregar para o serviço de nuvem ou acessar por navegadores não permitidos</span><span class="sxs-lookup"><span data-stu-id="aead5-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="aead5-115">Detecta quando um usuário tenta carregar um item em um domínio de serviço restrito ou acessar um item por meio de um navegador.</span><span class="sxs-lookup"><span data-stu-id="aead5-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="aead5-116">Se eles estiverem usando um navegador listado na DLP como um navegador não permitido, a atividade de carregamento será bloqueada e o usuário será redirecionado para usar o Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="aead5-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="aead5-117">O Edge Chromium permitirá ou bloqueará o carregamento ou o acesso com base na configuração da política DLP</span><span class="sxs-lookup"><span data-stu-id="aead5-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="aead5-118">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="aead5-118">auditable and restrictable</span></span>|
|<span data-ttu-id="aead5-119">copiar para outro aplicativo</span><span class="sxs-lookup"><span data-stu-id="aead5-119">copy to other app</span></span>    |<span data-ttu-id="aead5-120">Detecta quando um usuário tenta copiar informações de um item protegido e, em seguida, colá-las em outro aplicativo, processo ou item.</span><span class="sxs-lookup"><span data-stu-id="aead5-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="aead5-121">A cópia e a colagem de informações dentro do mesmo aplicativo, processo ou item não é detectada por essa atividade.</span><span class="sxs-lookup"><span data-stu-id="aead5-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="aead5-122">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="aead5-122">auditable and restrictable</span></span>|
|<span data-ttu-id="aead5-123">copiar para mídia removível USB</span><span class="sxs-lookup"><span data-stu-id="aead5-123">copy to USB removable media</span></span> |<span data-ttu-id="aead5-124">Detecta quando um usuário tenta copiar um item ou informação para uma mídia removível ou dispositivo USB.</span><span class="sxs-lookup"><span data-stu-id="aead5-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="aead5-125">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="aead5-125">auditable and restrictable</span></span>|
|<span data-ttu-id="aead5-126">Copiar para um compartilhamento de rede</span><span class="sxs-lookup"><span data-stu-id="aead5-126">copy to a network share</span></span>    |<span data-ttu-id="aead5-127">Detecta quando um usuário tenta copiar um item para um compartilhamento de rede ou unidade de rede mapeada</span><span class="sxs-lookup"><span data-stu-id="aead5-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="aead5-128">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="aead5-128">auditable and restrictable</span></span>|
|<span data-ttu-id="aead5-129">imprimir um documento</span><span class="sxs-lookup"><span data-stu-id="aead5-129">print a document</span></span>    |<span data-ttu-id="aead5-130">Detecta quando um usuário tenta imprimir um item protegido em uma impressora local ou de rede.</span><span class="sxs-lookup"><span data-stu-id="aead5-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="aead5-131">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="aead5-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="aead5-132">criar um Item</span><span class="sxs-lookup"><span data-stu-id="aead5-132">create an item</span></span>|<span data-ttu-id="aead5-133">Detecta quando um usuário cria um item</span><span class="sxs-lookup"><span data-stu-id="aead5-133">Detects when a user creates an item</span></span>| <span data-ttu-id="aead5-134">auditável</span><span class="sxs-lookup"><span data-stu-id="aead5-134">auditable</span></span>|
|<span data-ttu-id="aead5-135">renomear um item</span><span class="sxs-lookup"><span data-stu-id="aead5-135">rename an item</span></span>|<span data-ttu-id="aead5-136">Detecta quando um usuário renomeia um item</span><span class="sxs-lookup"><span data-stu-id="aead5-136">Detects when a user renames an item</span></span>| <span data-ttu-id="aead5-137">auditável</span><span class="sxs-lookup"><span data-stu-id="aead5-137">auditable</span></span>|

 ## <a name="monitored-files"></a><span data-ttu-id="aead5-138">Arquivos monitorados</span><span class="sxs-lookup"><span data-stu-id="aead5-138">Monitored files</span></span>

<span data-ttu-id="aead5-139">Endpoint DLP oferece suporte ao monitoramento destes tipos de arquivo:</span><span class="sxs-lookup"><span data-stu-id="aead5-139">Endpoint DLP supports monitoring of these file types:</span></span>

- <span data-ttu-id="aead5-140">Arquivos do Word</span><span class="sxs-lookup"><span data-stu-id="aead5-140">Word files</span></span>
- <span data-ttu-id="aead5-141">Arquivos do PowerPoint</span><span class="sxs-lookup"><span data-stu-id="aead5-141">PowerPoint files</span></span>
- <span data-ttu-id="aead5-142">Arquivos do Excel</span><span class="sxs-lookup"><span data-stu-id="aead5-142">Excel files</span></span>
- <span data-ttu-id="aead5-143">Arquivos PDF</span><span class="sxs-lookup"><span data-stu-id="aead5-143">PDF files</span></span>
- <span data-ttu-id="aead5-144">Arquivos .csv</span><span class="sxs-lookup"><span data-stu-id="aead5-144">.csv files</span></span>
- <span data-ttu-id="aead5-145">Arquivos .tsv</span><span class="sxs-lookup"><span data-stu-id="aead5-145">.tsv files</span></span>
- <span data-ttu-id="aead5-146">Arquivos .txt</span><span class="sxs-lookup"><span data-stu-id="aead5-146">.txt files</span></span>
- <span data-ttu-id="aead5-147">Arquivos .rtf</span><span class="sxs-lookup"><span data-stu-id="aead5-147">.rtf files</span></span>
- <span data-ttu-id="aead5-148">Arquivos .c</span><span class="sxs-lookup"><span data-stu-id="aead5-148">.c files</span></span>
- <span data-ttu-id="aead5-149">Arquivos .class</span><span class="sxs-lookup"><span data-stu-id="aead5-149">.class files</span></span>
- <span data-ttu-id="aead5-150">Arquivos .cpp</span><span class="sxs-lookup"><span data-stu-id="aead5-150">.cpp files</span></span>
- <span data-ttu-id="aead5-151">Arquivos .cs</span><span class="sxs-lookup"><span data-stu-id="aead5-151">.cs files</span></span>
- <span data-ttu-id="aead5-152">Arquivos .h</span><span class="sxs-lookup"><span data-stu-id="aead5-152">.h files</span></span>
- <span data-ttu-id="aead5-153">Arquivos .java</span><span class="sxs-lookup"><span data-stu-id="aead5-153">.java files</span></span>
 
<span data-ttu-id="aead5-154">Por padrão, o DLP do endpoint audita as atividades para esses tipos de arquivo, mesmo se não houver uma correspondência de política.</span><span class="sxs-lookup"><span data-stu-id="aead5-154">By default, endpoint DLP audits the activities for these file types, even if there isn't a policy match.</span></span> <span data-ttu-id="aead5-155">Se quiser apenas monitorar dados de correspondências de política, você pode desligar **Sempre auditar atividade de arquivo para dispositivos** nas configurações globais de DLP do endpoint.</span><span class="sxs-lookup"><span data-stu-id="aead5-155">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span> <span data-ttu-id="aead5-156">Não importa o que aconteça, as atividades em qualquer arquivo Word, PowerPoint, Excel, PDF e .csv são sempre auditadas.</span><span class="sxs-lookup"><span data-stu-id="aead5-156">No matter what, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited.</span></span>

<span data-ttu-id="aead5-157">O DLP do ponto de extremidade monitora a atividade com base no tipo MIME, portanto, as atividades serão capturadas mesmo se a extensão do arquivo for alterada.</span><span class="sxs-lookup"><span data-stu-id="aead5-157">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> 

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="aead5-158">O que é diferente no Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="aead5-158">What's different in Endpoint DLP</span></span>

<span data-ttu-id="aead5-159">Há alguns conceitos adicionais que você precisa saber antes de mergulhar no Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="aead5-159">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="aead5-160">Habilitar o gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="aead5-160">Enabling Device management</span></span>

<span data-ttu-id="aead5-161">O gerenciamento de dispositivos é a funcionalidade que habilita o conjunto de telemetria de dispositivos e a reúne para as soluções do Centro de conformidade do Microsoft 365, como Endpoint DLP e [gerenciamento de risco interno](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="aead5-161">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="aead5-162">Será necessário integrar todos os dispositivos que você deseja usar como locais nas políticas DLP.</span><span class="sxs-lookup"><span data-stu-id="aead5-162">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="aead5-163">![habilite o gerenciamento de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="aead5-163">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="aead5-164">A integração e a remoção são manipuladas por meio de scripts que você baixa no centro de gerenciamento de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="aead5-164">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="aead5-165">O centro tem scripts personalizados para cada um desses métodos de implantação:</span><span class="sxs-lookup"><span data-stu-id="aead5-165">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="aead5-166">script local (até 10 máquinas)</span><span class="sxs-lookup"><span data-stu-id="aead5-166">local script (up to 10 machines)</span></span>
- <span data-ttu-id="aead5-167">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="aead5-167">Group policy</span></span>
- <span data-ttu-id="aead5-168">System Center Configuration Manager (versão 1610 ou posterior)</span><span class="sxs-lookup"><span data-stu-id="aead5-168">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="aead5-169">Gerenciamento de dispositivos móveis/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="aead5-169">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="aead5-170">Scripts de integração VDI para máquinas não persistentes</span><span class="sxs-lookup"><span data-stu-id="aead5-170">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="aead5-171">![página de integração de dispositivos](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="aead5-171">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="aead5-172">Use os procedimentos no [Introdução ao Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) a dispositivos integrados.</span><span class="sxs-lookup"><span data-stu-id="aead5-172">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="aead5-173">Se você tiver dispositivos integrados por meio do [Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/), esses dispositivos aparecerão automaticamente na lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="aead5-173">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="aead5-174">![lista de dispositivos gerenciados](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="aead5-174">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="aead5-175">Exibir dados de DLP do Endpoint</span><span class="sxs-lookup"><span data-stu-id="aead5-175">Viewing Endpoint DLP data</span></span>



<span data-ttu-id="aead5-176">Visualize os alertas relacionados às políticas DLP aplicadas em dispositivos de ponto de extremidade no [Painel de Gerenciamento de Alertas DLP](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="aead5-176">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![Informações sobre alertas](../media/Alert-info-1.png)

<span data-ttu-id="aead5-178">Você também pode visualizar detalhes do evento associado com metadados ricos no mesmo painel</span><span class="sxs-lookup"><span data-stu-id="aead5-178">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![informações do evento](../media/Event-info-1.png)

<span data-ttu-id="aead5-180">Após a integração de um dispositivo, as informações sobre as atividades auditadas fluem no explorador de atividades mesmo antes de você configurar e implantar as políticas DLP que têm dispositivos como um local.</span><span class="sxs-lookup"><span data-stu-id="aead5-180">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="aead5-181">![eventos do DLP do ponto de extremidade no gerenciador de atividades](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="aead5-181">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="aead5-182">O Endpoint DLP coleta informações abrangentes sobre atividades auditadas.</span><span class="sxs-lookup"><span data-stu-id="aead5-182">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="aead5-183">Por exemplo, se um arquivo for copiado para uma mídia USB removível, você verá esses atributos nos detalhes da atividade:</span><span class="sxs-lookup"><span data-stu-id="aead5-183">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="aead5-184">tipo de atividade</span><span class="sxs-lookup"><span data-stu-id="aead5-184">activity type</span></span>
- <span data-ttu-id="aead5-185">IP do Cliente</span><span class="sxs-lookup"><span data-stu-id="aead5-185">client IP</span></span>
- <span data-ttu-id="aead5-186">caminho do arquivo de destino</span><span class="sxs-lookup"><span data-stu-id="aead5-186">target file path</span></span>
- <span data-ttu-id="aead5-187">carimbo de data/hora ocorrido</span><span class="sxs-lookup"><span data-stu-id="aead5-187">happened timestamp</span></span>
- <span data-ttu-id="aead5-188">nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="aead5-188">file name</span></span>
- <span data-ttu-id="aead5-189">usuário</span><span class="sxs-lookup"><span data-stu-id="aead5-189">user</span></span>
- <span data-ttu-id="aead5-190">extensão do arquivo</span><span class="sxs-lookup"><span data-stu-id="aead5-190">file extension</span></span>
- <span data-ttu-id="aead5-191">tamanho do arquivo</span><span class="sxs-lookup"><span data-stu-id="aead5-191">file size</span></span>
- <span data-ttu-id="aead5-192">tipo de informação confidencial (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="aead5-192">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="aead5-193">valor SHA1</span><span class="sxs-lookup"><span data-stu-id="aead5-193">sha1 value</span></span>
- <span data-ttu-id="aead5-194">valor SHA256</span><span class="sxs-lookup"><span data-stu-id="aead5-194">sha256 value</span></span>
- <span data-ttu-id="aead5-195">nome do arquivo anterior</span><span class="sxs-lookup"><span data-stu-id="aead5-195">previous file name</span></span>
- <span data-ttu-id="aead5-196">localização</span><span class="sxs-lookup"><span data-stu-id="aead5-196">location</span></span>
- <span data-ttu-id="aead5-197">primário</span><span class="sxs-lookup"><span data-stu-id="aead5-197">parent</span></span>
- <span data-ttu-id="aead5-198">FilePath</span><span class="sxs-lookup"><span data-stu-id="aead5-198">filepath</span></span>
- <span data-ttu-id="aead5-199">Tipo de local de origem</span><span class="sxs-lookup"><span data-stu-id="aead5-199">source location type</span></span>
- <span data-ttu-id="aead5-200">plataforma</span><span class="sxs-lookup"><span data-stu-id="aead5-200">platform</span></span>
- <span data-ttu-id="aead5-201">nome do dispositivo</span><span class="sxs-lookup"><span data-stu-id="aead5-201">device name</span></span>
- <span data-ttu-id="aead5-202">Tipo de local de destino</span><span class="sxs-lookup"><span data-stu-id="aead5-202">destination location type</span></span>
- <span data-ttu-id="aead5-203">aplicativo que executou a cópia</span><span class="sxs-lookup"><span data-stu-id="aead5-203">application that performed the copy</span></span>
- <span data-ttu-id="aead5-204">ID de dispositivo do Microsoft Defender para Ponto de Extremidade (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="aead5-204">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="aead5-205">fabricante do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="aead5-205">removable media device manufacturer</span></span>
- <span data-ttu-id="aead5-206">modelo do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="aead5-206">removable media device model</span></span>
- <span data-ttu-id="aead5-207">número de série do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="aead5-207">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="aead5-208">![copiar para atributos de atividades USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="aead5-208">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="aead5-209">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="aead5-209">Next steps</span></span>

<span data-ttu-id="aead5-210">Agora que você aprendeu sobre o Endpoint DLP, as próximas etapas são:</span><span class="sxs-lookup"><span data-stu-id="aead5-210">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="aead5-211">Introdução à prevenção contra perda de dados do ponto de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="aead5-211">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="aead5-212">Usar a prevenção contra perda de dados do Ponto de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="aead5-212">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="aead5-213">Confira também</span><span class="sxs-lookup"><span data-stu-id="aead5-213">See also</span></span>

- [<span data-ttu-id="aead5-214">Introdução à prevenção contra perda de dados do Ponto de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="aead5-214">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="aead5-215">Usar a prevenção contra perda de dados do Ponto de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="aead5-215">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="aead5-216">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="aead5-216">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="aead5-217">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="aead5-217">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="aead5-218">Começar a usar o Explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="aead5-218">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="aead5-219">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="aead5-219">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="aead5-220">Gerenciamento de risco interno</span><span class="sxs-lookup"><span data-stu-id="aead5-220">Insider Risk management</span></span>](insider-risk-management.md)
