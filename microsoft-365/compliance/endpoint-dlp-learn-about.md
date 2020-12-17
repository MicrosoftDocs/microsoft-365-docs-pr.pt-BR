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
ms.openlocfilehash: 1dac32505144c3966ad2219cc69a33ba29f194dc
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49682622"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="26ca7-104">Saiba mais sobre a prevenção contra perda de dados do ponto de extremidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="26ca7-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="26ca7-105">Você pode usar a prevenção contra perda de dados (DLP) da Microsoft 365 para monitorar as ações que estão sendo executadas em itens que você concluiu a ser sensível e para ajudar a evitar o compartilhamento não intencional desses itens.</span><span class="sxs-lookup"><span data-stu-id="26ca7-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="26ca7-106">Para mais informações sobre a DLP, confira [Visão geral das políticas de prevenção contra perda de dados](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="26ca7-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="26ca7-107">**A prevenção contra perda de dados de pontos de extremidade** (Endpoint DLP) estende os recursos de proteção e monitoramento de atividades da DLP para itens confidenciais que estão em dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="26ca7-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="26ca7-108">Depois que os dispositivos estiverem integrados às soluções de conformidade do Microsoft 365, as informações sobre o que os usuários estão fazendo com itens confidenciais serão visíveis no [explorador de atividades](data-classification-activity-explorer.md) e você poderá aplicar ações de proteção a esses itens por meio das [políticas DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="26ca7-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="26ca7-109">Atividades do ponto de extremidade que você pode monitorar e executar</span><span class="sxs-lookup"><span data-stu-id="26ca7-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="26ca7-110">O Microsoft Endpoint DLP permite a auditoria e o gerenciamento dos seguintes tipos de atividades que os usuários têm em itens confidenciais em dispositivos com Windows 10.</span><span class="sxs-lookup"><span data-stu-id="26ca7-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>


|<span data-ttu-id="26ca7-111">atividade</span><span class="sxs-lookup"><span data-stu-id="26ca7-111">activity</span></span> |<span data-ttu-id="26ca7-112">descrição</span><span class="sxs-lookup"><span data-stu-id="26ca7-112">description</span></span>  | <span data-ttu-id="26ca7-113">auditável/restringivel</span><span class="sxs-lookup"><span data-stu-id="26ca7-113">auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="26ca7-114">carregar para o serviço de nuvem ou acessar por navegadores não permitidos</span><span class="sxs-lookup"><span data-stu-id="26ca7-114">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="26ca7-115">Detecta quando um usuário tenta carregar um item em um domínio de serviço restrito ou acessar um item por meio de um navegador.</span><span class="sxs-lookup"><span data-stu-id="26ca7-115">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="26ca7-116">Se eles estiverem usando um navegador listado na DLP como um navegador não permitido, a atividade de carregamento será bloqueada e o usuário será redirecionado para usar o Edge Chromium.</span><span class="sxs-lookup"><span data-stu-id="26ca7-116">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="26ca7-117">O Edge Chromium permitirá ou bloqueará o carregamento ou o acesso com base na configuração da política DLP</span><span class="sxs-lookup"><span data-stu-id="26ca7-117">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="26ca7-118">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="26ca7-118">auditable and restrictable</span></span>|
|<span data-ttu-id="26ca7-119">copiar para outro aplicativo</span><span class="sxs-lookup"><span data-stu-id="26ca7-119">copy to other app</span></span>    |<span data-ttu-id="26ca7-120">Detecta quando um usuário tenta copiar informações de um item protegido e, em seguida, colá-las em outro aplicativo, processo ou item.</span><span class="sxs-lookup"><span data-stu-id="26ca7-120">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="26ca7-121">A cópia e a colagem de informações dentro do mesmo aplicativo, processo ou item não é detectada por essa atividade.</span><span class="sxs-lookup"><span data-stu-id="26ca7-121">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="26ca7-122">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="26ca7-122">auditable and restrictable</span></span>|
|<span data-ttu-id="26ca7-123">copiar para mídia removível USB</span><span class="sxs-lookup"><span data-stu-id="26ca7-123">copy to USB removable media</span></span> |<span data-ttu-id="26ca7-124">Detecta quando um usuário tenta copiar um item ou informação para uma mídia removível ou dispositivo USB.</span><span class="sxs-lookup"><span data-stu-id="26ca7-124">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="26ca7-125">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="26ca7-125">auditable and restrictable</span></span>|
|<span data-ttu-id="26ca7-126">Copiar para um compartilhamento de rede</span><span class="sxs-lookup"><span data-stu-id="26ca7-126">copy to a network share</span></span>    |<span data-ttu-id="26ca7-127">Detecta quando um usuário tenta copiar um item para um compartilhamento de rede ou unidade de rede mapeada</span><span class="sxs-lookup"><span data-stu-id="26ca7-127">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="26ca7-128">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="26ca7-128">auditable and restrictable</span></span>|
|<span data-ttu-id="26ca7-129">imprimir um documento</span><span class="sxs-lookup"><span data-stu-id="26ca7-129">print a document</span></span>    |<span data-ttu-id="26ca7-130">Detecta quando um usuário tenta imprimir um item protegido em uma impressora local ou de rede.</span><span class="sxs-lookup"><span data-stu-id="26ca7-130">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="26ca7-131">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="26ca7-131">auditable and restrictable</span></span>         |
|<span data-ttu-id="26ca7-132">criar um Item</span><span class="sxs-lookup"><span data-stu-id="26ca7-132">create an item</span></span>|<span data-ttu-id="26ca7-133">Detecta quando um usuário cria um item</span><span class="sxs-lookup"><span data-stu-id="26ca7-133">Detects when a user creates an item</span></span>| <span data-ttu-id="26ca7-134">auditável</span><span class="sxs-lookup"><span data-stu-id="26ca7-134">auditable</span></span>|
|<span data-ttu-id="26ca7-135">renomear um item</span><span class="sxs-lookup"><span data-stu-id="26ca7-135">rename an item</span></span>|<span data-ttu-id="26ca7-136">Detecta quando um usuário renomeia um item</span><span class="sxs-lookup"><span data-stu-id="26ca7-136">Detects when a user renames an item</span></span>| <span data-ttu-id="26ca7-137">auditável</span><span class="sxs-lookup"><span data-stu-id="26ca7-137">auditable</span></span>|


## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="26ca7-138">O que é diferente no Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="26ca7-138">What's different in Endpoint DLP</span></span>

<span data-ttu-id="26ca7-139">Há alguns conceitos adicionais que você precisa saber antes de mergulhar no Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="26ca7-139">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="26ca7-140">Habilitar o gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="26ca7-140">Enabling Device management</span></span>

<span data-ttu-id="26ca7-141">O gerenciamento de dispositivos é a funcionalidade que habilita o conjunto de telemetria de dispositivos e a reúne para as soluções do Centro de conformidade do Microsoft 365, como Endpoint DLP e [gerenciamento de risco interno](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="26ca7-141">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="26ca7-142">Será necessário integrar todos os dispositivos que você deseja usar como locais nas políticas DLP.</span><span class="sxs-lookup"><span data-stu-id="26ca7-142">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="26ca7-143">![habilite o gerenciamento de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="26ca7-143">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="26ca7-144">A integração e a remoção são manipuladas por meio de scripts que você baixa no centro de gerenciamento de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="26ca7-144">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="26ca7-145">O centro tem scripts personalizados para cada um desses métodos de implantação:</span><span class="sxs-lookup"><span data-stu-id="26ca7-145">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="26ca7-146">script local (até 10 máquinas)</span><span class="sxs-lookup"><span data-stu-id="26ca7-146">local script (up to 10 machines)</span></span>
- <span data-ttu-id="26ca7-147">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="26ca7-147">Group policy</span></span>
- <span data-ttu-id="26ca7-148">System Center Configuration Manager (versão 1610 ou posterior)</span><span class="sxs-lookup"><span data-stu-id="26ca7-148">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="26ca7-149">Gerenciamento de dispositivos móveis/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="26ca7-149">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="26ca7-150">Scripts de integração VDI para máquinas não persistentes</span><span class="sxs-lookup"><span data-stu-id="26ca7-150">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="26ca7-151">![página de integração de dispositivos](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="26ca7-151">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="26ca7-152">Use os procedimentos no [Introdução ao Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) a dispositivos integrados.</span><span class="sxs-lookup"><span data-stu-id="26ca7-152">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="26ca7-153">Se você tiver dispositivos integrados por meio do [Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/), esses dispositivos aparecerão automaticamente na lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="26ca7-153">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="26ca7-154">![lista de dispositivos gerenciados](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="26ca7-154">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="26ca7-155">Exibir dados de DLP do Endpoint</span><span class="sxs-lookup"><span data-stu-id="26ca7-155">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="26ca7-156">O DLP do ponto de extremidade monitora a atividade com base no tipo MIME, portanto, as atividades serão capturadas mesmo se a extensão do arquivo for alterada.</span><span class="sxs-lookup"><span data-stu-id="26ca7-156">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span> <span data-ttu-id="26ca7-157">Neste momento, os seguintes tipos de arquivos são compatíveis:</span><span class="sxs-lookup"><span data-stu-id="26ca7-157">At this time the following file types are supported:</span></span>

- <span data-ttu-id="26ca7-158">Arquivos do Word</span><span class="sxs-lookup"><span data-stu-id="26ca7-158">Word files</span></span>
- <span data-ttu-id="26ca7-159">Arquivos do PowerPoint</span><span class="sxs-lookup"><span data-stu-id="26ca7-159">PowerPoint files</span></span>
- <span data-ttu-id="26ca7-160">Arquivos do Excel</span><span class="sxs-lookup"><span data-stu-id="26ca7-160">Excel files</span></span>
- <span data-ttu-id="26ca7-161">Arquivos PDF</span><span class="sxs-lookup"><span data-stu-id="26ca7-161">PDF files</span></span>
- <span data-ttu-id="26ca7-162">Arquivos .csv</span><span class="sxs-lookup"><span data-stu-id="26ca7-162">.csv files</span></span>
- <span data-ttu-id="26ca7-163">Arquivos .tsv</span><span class="sxs-lookup"><span data-stu-id="26ca7-163">.tsv files</span></span>
- <span data-ttu-id="26ca7-164">Arquivos .txt</span><span class="sxs-lookup"><span data-stu-id="26ca7-164">.txt files</span></span>
- <span data-ttu-id="26ca7-165">Arquivos .rtf</span><span class="sxs-lookup"><span data-stu-id="26ca7-165">.rtf files</span></span>
- <span data-ttu-id="26ca7-166">Arquivos .c</span><span class="sxs-lookup"><span data-stu-id="26ca7-166">.c files</span></span>
- <span data-ttu-id="26ca7-167">Arquivos .class</span><span class="sxs-lookup"><span data-stu-id="26ca7-167">.class files</span></span>
- <span data-ttu-id="26ca7-168">Arquivos .cpp</span><span class="sxs-lookup"><span data-stu-id="26ca7-168">.cpp files</span></span>
- <span data-ttu-id="26ca7-169">Arquivos .cs</span><span class="sxs-lookup"><span data-stu-id="26ca7-169">.cs files</span></span>
- <span data-ttu-id="26ca7-170">Arquivos .h</span><span class="sxs-lookup"><span data-stu-id="26ca7-170">.h files</span></span>
- <span data-ttu-id="26ca7-171">Arquivos .java</span><span class="sxs-lookup"><span data-stu-id="26ca7-171">.java files</span></span>

> [!NOTE]
> <span data-ttu-id="26ca7-172">O DLP de ponto de extremidade avalia os arquivos de todos os tipos acima em relação à política de DLP e aplica as ações de proteção de acordo.</span><span class="sxs-lookup"><span data-stu-id="26ca7-172">Endpoint DLP evaluates files of all the above types against the DLP policy and applies protection actions accordingly.</span></span> <span data-ttu-id="26ca7-173">Todos os arquivos que correspondem a uma política DLP são auditados para todas as ações com suporte, mesmo se não forem bloqueadas.</span><span class="sxs-lookup"><span data-stu-id="26ca7-173">All files that match a DLP policy are audited for all supported actions, even if they aren't blocked.</span></span> <span data-ttu-id="26ca7-174">Além disso, a atividade de arquivo realizada em qualquer arquivo de Word, PowerPoint, Excel, PDF e .csv é auditado por padrão, independentemente da existência de uma política DLP ou da correspondência desses arquivos.</span><span class="sxs-lookup"><span data-stu-id="26ca7-174">In addition, file activity performed on any Word, PowerPoint, Excel, PDF, and .csv file is audited by default, independent of whether a DLP policy exists or matches these files.</span></span>

<span data-ttu-id="26ca7-175">Visualize os alertas relacionados às políticas DLP aplicadas em dispositivos de ponto de extremidade no [Painel de Gerenciamento de Alertas DLP](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="26ca7-175">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![Informações sobre alertas](../media/Alert-info-1.png)

<span data-ttu-id="26ca7-177">Você também pode visualizar detalhes do evento associado com metadados ricos no mesmo painel</span><span class="sxs-lookup"><span data-stu-id="26ca7-177">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![informações do evento](../media/Event-info-1.png)

<span data-ttu-id="26ca7-179">Após a integração de um dispositivo, as informações sobre as atividades auditadas fluem no explorador de atividades mesmo antes de você configurar e implantar as políticas DLP que têm dispositivos como um local.</span><span class="sxs-lookup"><span data-stu-id="26ca7-179">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="26ca7-180">![eventos do DLP do ponto de extremidade no gerenciador de atividades](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="26ca7-180">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="26ca7-181">O Endpoint DLP coleta informações abrangentes sobre atividades auditadas.</span><span class="sxs-lookup"><span data-stu-id="26ca7-181">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="26ca7-182">Por exemplo, se um arquivo for copiado para uma mídia USB removível, você verá esses atributos nos detalhes da atividade:</span><span class="sxs-lookup"><span data-stu-id="26ca7-182">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="26ca7-183">tipo de atividade</span><span class="sxs-lookup"><span data-stu-id="26ca7-183">activity type</span></span>
- <span data-ttu-id="26ca7-184">IP do Cliente</span><span class="sxs-lookup"><span data-stu-id="26ca7-184">client IP</span></span>
- <span data-ttu-id="26ca7-185">caminho do arquivo de destino</span><span class="sxs-lookup"><span data-stu-id="26ca7-185">target file path</span></span>
- <span data-ttu-id="26ca7-186">carimbo de data/hora ocorrido</span><span class="sxs-lookup"><span data-stu-id="26ca7-186">happened timestamp</span></span>
- <span data-ttu-id="26ca7-187">nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="26ca7-187">file name</span></span>
- <span data-ttu-id="26ca7-188">usuário</span><span class="sxs-lookup"><span data-stu-id="26ca7-188">user</span></span>
- <span data-ttu-id="26ca7-189">extensão do arquivo</span><span class="sxs-lookup"><span data-stu-id="26ca7-189">file extension</span></span>
- <span data-ttu-id="26ca7-190">tamanho do arquivo</span><span class="sxs-lookup"><span data-stu-id="26ca7-190">file size</span></span>
- <span data-ttu-id="26ca7-191">tipo de informação confidencial (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="26ca7-191">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="26ca7-192">valor SHA1</span><span class="sxs-lookup"><span data-stu-id="26ca7-192">sha1 value</span></span>
- <span data-ttu-id="26ca7-193">valor SHA256</span><span class="sxs-lookup"><span data-stu-id="26ca7-193">sha256 value</span></span>
- <span data-ttu-id="26ca7-194">nome do arquivo anterior</span><span class="sxs-lookup"><span data-stu-id="26ca7-194">previous file name</span></span>
- <span data-ttu-id="26ca7-195">localização</span><span class="sxs-lookup"><span data-stu-id="26ca7-195">location</span></span>
- <span data-ttu-id="26ca7-196">primário</span><span class="sxs-lookup"><span data-stu-id="26ca7-196">parent</span></span>
- <span data-ttu-id="26ca7-197">FilePath</span><span class="sxs-lookup"><span data-stu-id="26ca7-197">filepath</span></span>
- <span data-ttu-id="26ca7-198">Tipo de local de origem</span><span class="sxs-lookup"><span data-stu-id="26ca7-198">source location type</span></span>
- <span data-ttu-id="26ca7-199">plataforma</span><span class="sxs-lookup"><span data-stu-id="26ca7-199">platform</span></span>
- <span data-ttu-id="26ca7-200">nome do dispositivo</span><span class="sxs-lookup"><span data-stu-id="26ca7-200">device name</span></span>
- <span data-ttu-id="26ca7-201">Tipo de local de destino</span><span class="sxs-lookup"><span data-stu-id="26ca7-201">destination location type</span></span>
- <span data-ttu-id="26ca7-202">aplicativo que executou a cópia</span><span class="sxs-lookup"><span data-stu-id="26ca7-202">application that performed the copy</span></span>
- <span data-ttu-id="26ca7-203">ID de dispositivo do Microsoft Defender para Ponto de Extremidade (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="26ca7-203">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="26ca7-204">fabricante do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="26ca7-204">removable media device manufacturer</span></span>
- <span data-ttu-id="26ca7-205">modelo do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="26ca7-205">removable media device model</span></span>
- <span data-ttu-id="26ca7-206">número de série do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="26ca7-206">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="26ca7-207">![copiar para atributos de atividades USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="26ca7-207">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="26ca7-208">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="26ca7-208">Next steps</span></span>

<span data-ttu-id="26ca7-209">Agora que você aprendeu sobre o Endpoint DLP, as próximas etapas são:</span><span class="sxs-lookup"><span data-stu-id="26ca7-209">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="26ca7-210">Introdução à prevenção contra perda de dados do ponto de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="26ca7-210">Getting started with Microsoft Endpoint data loss prevention </span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="26ca7-211">Usar a prevenção contra perda de dados do Ponto de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="26ca7-211">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="26ca7-212">Confira também</span><span class="sxs-lookup"><span data-stu-id="26ca7-212">See also</span></span>

- [<span data-ttu-id="26ca7-213">Introdução à prevenção contra perda de dados do Ponto de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="26ca7-213">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="26ca7-214">Usar a prevenção contra perda de dados do Ponto de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="26ca7-214">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="26ca7-215">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="26ca7-215">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="26ca7-216">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="26ca7-216">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="26ca7-217">Começar a usar o Explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="26ca7-217">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="26ca7-218">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="26ca7-218">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="26ca7-219">Gerenciamento de risco interno</span><span class="sxs-lookup"><span data-stu-id="26ca7-219">Insider Risk management</span></span>](insider-risk-management.md)
