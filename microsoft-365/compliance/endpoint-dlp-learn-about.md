---
title: Saiba mais sobre a prevenção contra perda de dados do ponto de extremidade da Microsoft 365 (visualização)
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
description: 'A prevenção contra perda de dados do ponto de extremidade da Microsoft 365 estende o monitoramento de atividades de arquivo e ações de proteção para os pontos de extremidade desse arquivo. Os arquivos do são visíveis nas soluções do Centro de conformidade do Microsoft 365 '
ms.openlocfilehash: cbf4a53658885102226d2b874180f5cc5f264a91
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841857"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="08198-104">Saiba mais sobre a prevenção contra perda de dados do ponto de extremidade da Microsoft 365 (visualização)</span><span class="sxs-lookup"><span data-stu-id="08198-104">Learn about Microsoft 365 Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="08198-105">Você pode usar a prevenção contra perda de dados (DLP) da Microsoft 365 para monitorar as ações que estão sendo executadas em itens que você concluiu a ser sensível e para ajudar a evitar o compartilhamento não intencional desses itens.</span><span class="sxs-lookup"><span data-stu-id="08198-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="08198-106">Para mais informações sobre a DLP, confira [Visão geral das políticas de prevenção contra perda de dados](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="08198-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="08198-107">**A prevenção contra perda de dados de pontos de extremidade** (Endpoint DLP) estende os recursos de proteção e monitoramento de atividades da DLP para itens confidenciais que estão em dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="08198-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="08198-108">Depois que os dispositivos estiverem integrados às soluções de conformidade do Microsoft 365, as informações sobre o que os usuários estão fazendo com itens confidenciais serão visíveis no [explorador de atividades](data-classification-activity-explorer.md) e você poderá aplicar ações de proteção a esses itens por meio das [políticas DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="08198-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="08198-109">Atividades do ponto de extremidade que você pode monitorar e executar</span><span class="sxs-lookup"><span data-stu-id="08198-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="08198-110">O Microsoft Endpoint DLP permite a auditoria e o gerenciamento dos seguintes tipos de atividades que os usuários têm em itens confidenciais em dispositivos com Windows 10.</span><span class="sxs-lookup"><span data-stu-id="08198-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> <span data-ttu-id="08198-111">Isso inclui:</span><span class="sxs-lookup"><span data-stu-id="08198-111">This includes:</span></span>


|<span data-ttu-id="08198-112">atividade no item</span><span class="sxs-lookup"><span data-stu-id="08198-112">activity on item</span></span> |<span data-ttu-id="08198-113">auditável/restringivel</span><span class="sxs-lookup"><span data-stu-id="08198-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="08198-114">criado</span><span class="sxs-lookup"><span data-stu-id="08198-114">created</span></span>    | <span data-ttu-id="08198-115">auditável</span><span class="sxs-lookup"><span data-stu-id="08198-115">auditable</span></span>      |
|<span data-ttu-id="08198-116">renomeado</span><span class="sxs-lookup"><span data-stu-id="08198-116">renamed</span></span>    |  <span data-ttu-id="08198-117">auditável</span><span class="sxs-lookup"><span data-stu-id="08198-117">auditable</span></span>       |
|<span data-ttu-id="08198-118">copiado ou criado em mídia removível</span><span class="sxs-lookup"><span data-stu-id="08198-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="08198-119">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="08198-119">auditable and restrictable</span></span>|
|<span data-ttu-id="08198-120">copiado para compartilhamento de rede, por exemplo \\my-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="08198-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="08198-121">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="08198-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="08198-122">impresso</span><span class="sxs-lookup"><span data-stu-id="08198-122">printed</span></span> |    <span data-ttu-id="08198-123">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="08198-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="08198-124">copiado para a nuvem por meio do Chromium Edge</span><span class="sxs-lookup"><span data-stu-id="08198-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="08198-125">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="08198-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="08198-126">acessado por aplicativos e navegadores que não tem permissão de acesso</span><span class="sxs-lookup"><span data-stu-id="08198-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="08198-127">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="08198-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="08198-128">O que é diferente no Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="08198-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="08198-129">Há alguns conceitos adicionais que você precisa saber antes de mergulhar no Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="08198-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="08198-130">Habilitar o gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="08198-130">Enabling Device management</span></span>

<span data-ttu-id="08198-131">O gerenciamento de dispositivos é a funcionalidade que habilita o conjunto de telemetria de dispositivos e a reúne para as soluções do Centro de conformidade do Microsoft 365, como Endpoint DLP e [gerenciamento de risco interno](insider-risk-management.md).</span><span class="sxs-lookup"><span data-stu-id="08198-131">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="08198-132">Será necessário integrar todos os dispositivos que você deseja usar como locais nas políticas DLP.</span><span class="sxs-lookup"><span data-stu-id="08198-132">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

![habilitar o gerenciamento de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

<span data-ttu-id="08198-134">A integração e a remoção são manipuladas por meio de scripts que você baixa no centro de gerenciamento de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="08198-134">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="08198-135">O centro tem scripts personalizados para cada um desses métodos de implantação:</span><span class="sxs-lookup"><span data-stu-id="08198-135">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="08198-136">script local (até 10 máquinas)</span><span class="sxs-lookup"><span data-stu-id="08198-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="08198-137">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="08198-137">Group policy</span></span>
- <span data-ttu-id="08198-138">System Center Configuration Manager (versão 1610 ou posterior)</span><span class="sxs-lookup"><span data-stu-id="08198-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="08198-139">Gerenciamento de dispositivos móveis/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="08198-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="08198-140">Scripts de integração VDI para máquinas não persistentes</span><span class="sxs-lookup"><span data-stu-id="08198-140">VDI onboarding scripts for non-persistent machines</span></span>

![página de integração de dispositivos](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 <span data-ttu-id="08198-142">Use os procedimentos no [Introdução ao Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) a dispositivos integrados.</span><span class="sxs-lookup"><span data-stu-id="08198-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="08198-143">Se você tiver dispositivos integrados por meio do [Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/), esses dispositivos serão mostrados automaticamente na lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="08198-143">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

![lista de dispositivos gerenciados](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="08198-145">Exibir dados de DLP do Endpoint</span><span class="sxs-lookup"><span data-stu-id="08198-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="08198-146">O Endpoint DLP monitora a atividade do tipo MIME do OM baseado na atividade, portanto, as atividades serão capturadas, mesmo que a extensão de arquivo seja alterada.</span><span class="sxs-lookup"><span data-stu-id="08198-146">Endpoint DLP monitors activity based om MIME type, so activities will be captured even if the file extension is changed.</span></span> <span data-ttu-id="08198-147">Na visualização pública, ela observa todos:</span><span class="sxs-lookup"><span data-stu-id="08198-147">At public preview it watches all:</span></span>

- <span data-ttu-id="08198-148">Arquivos do Word</span><span class="sxs-lookup"><span data-stu-id="08198-148">Word files</span></span>
- <span data-ttu-id="08198-149">Arquivos do PowerPoint</span><span class="sxs-lookup"><span data-stu-id="08198-149">PowerPoint files</span></span>
- <span data-ttu-id="08198-150">Arquivos do Excel</span><span class="sxs-lookup"><span data-stu-id="08198-150">Excel files</span></span>
- <span data-ttu-id="08198-151">Arquivos PDF</span><span class="sxs-lookup"><span data-stu-id="08198-151">PDF files</span></span>
- <span data-ttu-id="08198-152">Arquivos .csv</span><span class="sxs-lookup"><span data-stu-id="08198-152">.csv files</span></span>
- <span data-ttu-id="08198-153">Arquivos .tsv</span><span class="sxs-lookup"><span data-stu-id="08198-153">.tsv files</span></span>
- <span data-ttu-id="08198-154">Arquivos C</span><span class="sxs-lookup"><span data-stu-id="08198-154">c files</span></span>
- <span data-ttu-id="08198-155">Arquivos de classe</span><span class="sxs-lookup"><span data-stu-id="08198-155">class files</span></span>
- <span data-ttu-id="08198-156">Arquivos CPP</span><span class="sxs-lookup"><span data-stu-id="08198-156">cpp files</span></span>
- <span data-ttu-id="08198-157">Arquivos CS</span><span class="sxs-lookup"><span data-stu-id="08198-157">cs files</span></span>
- <span data-ttu-id="08198-158">Arquivos H</span><span class="sxs-lookup"><span data-stu-id="08198-158">h files</span></span>
- <span data-ttu-id="08198-159">Arquivos Java</span><span class="sxs-lookup"><span data-stu-id="08198-159">java files</span></span>

> [!NOTE]
> <span data-ttu-id="08198-160">Os arquivos .txt e de código-fonte não são auditados por padrão, a DLP os avalia em relação às políticas aplicadas e as ações do usuário são auditadas ou bloqueadas de acordo.</span><span class="sxs-lookup"><span data-stu-id="08198-160">.txt and source code files are not audited by default, DLP evaluates them against the applied policies and then user actions are audited or blocked accordingly.</span></span>

<span data-ttu-id="08198-161">Após a integração de um dispositivo, as informações sobre as atividades auditadas fluem no explorador de atividades mesmo antes de você configurar e implantar as políticas DLP que têm dispositivos como um local.</span><span class="sxs-lookup"><span data-stu-id="08198-161">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

![eventos do Endpoint DLP no explorador de atividades](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

<span data-ttu-id="08198-163">O Endpoint DLP coleta informações abrangentes sobre atividades auditadas.</span><span class="sxs-lookup"><span data-stu-id="08198-163">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="08198-164">Por exemplo, se um arquivo for copiado para uma mídia USB removível, você verá esses atributos nos detalhes da atividade:</span><span class="sxs-lookup"><span data-stu-id="08198-164">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="08198-165">tipo de atividade</span><span class="sxs-lookup"><span data-stu-id="08198-165">activity type</span></span>
- <span data-ttu-id="08198-166">IP do Cliente</span><span class="sxs-lookup"><span data-stu-id="08198-166">client IP</span></span>
- <span data-ttu-id="08198-167">caminho do arquivo de destino</span><span class="sxs-lookup"><span data-stu-id="08198-167">target file path</span></span>
- <span data-ttu-id="08198-168">carimbo de data/hora ocorrido</span><span class="sxs-lookup"><span data-stu-id="08198-168">happened timestamp</span></span>
- <span data-ttu-id="08198-169">nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="08198-169">file name</span></span>
- <span data-ttu-id="08198-170">usuário</span><span class="sxs-lookup"><span data-stu-id="08198-170">user</span></span>
- <span data-ttu-id="08198-171">extensão do arquivo</span><span class="sxs-lookup"><span data-stu-id="08198-171">file extension</span></span>
- <span data-ttu-id="08198-172">tamanho do arquivo</span><span class="sxs-lookup"><span data-stu-id="08198-172">file size</span></span>
- <span data-ttu-id="08198-173">tipo de informação confidencial (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="08198-173">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="08198-174">valor SHA1</span><span class="sxs-lookup"><span data-stu-id="08198-174">sha1 value</span></span>
- <span data-ttu-id="08198-175">valor SHA256</span><span class="sxs-lookup"><span data-stu-id="08198-175">sha256 value</span></span>
- <span data-ttu-id="08198-176">nome do arquivo anterior</span><span class="sxs-lookup"><span data-stu-id="08198-176">previous file name</span></span>
- <span data-ttu-id="08198-177">localização</span><span class="sxs-lookup"><span data-stu-id="08198-177">location</span></span>
- <span data-ttu-id="08198-178">primário</span><span class="sxs-lookup"><span data-stu-id="08198-178">parent</span></span>
- <span data-ttu-id="08198-179">FilePath</span><span class="sxs-lookup"><span data-stu-id="08198-179">filepath</span></span>
- <span data-ttu-id="08198-180">Tipo de local de origem</span><span class="sxs-lookup"><span data-stu-id="08198-180">source location type</span></span>
- <span data-ttu-id="08198-181">plataforma</span><span class="sxs-lookup"><span data-stu-id="08198-181">platform</span></span>
- <span data-ttu-id="08198-182">nome do dispositivo</span><span class="sxs-lookup"><span data-stu-id="08198-182">device name</span></span>
- <span data-ttu-id="08198-183">Tipo de local de destino</span><span class="sxs-lookup"><span data-stu-id="08198-183">destination location type</span></span>
- <span data-ttu-id="08198-184">aplicativo que executou a cópia</span><span class="sxs-lookup"><span data-stu-id="08198-184">application that performed the copy</span></span>
- <span data-ttu-id="08198-185">ID de dispositivo do Microsoft Defender para Ponto de Extremidade (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="08198-185">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="08198-186">fabricante do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="08198-186">removable media device manufacturer</span></span>
- <span data-ttu-id="08198-187">modelo do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="08198-187">removable media device model</span></span>
- <span data-ttu-id="08198-188">número de série do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="08198-188">removable media device serial number</span></span>

![copiar para atributos de atividades USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a><span data-ttu-id="08198-190">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="08198-190">Next steps</span></span>

<span data-ttu-id="08198-191">Agora que você aprendeu sobre o Endpoint DLP, as próximas etapas são:</span><span class="sxs-lookup"><span data-stu-id="08198-191">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="08198-192">Introdução à prevenção contra perda de dados do Microsoft EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="08198-192">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="08198-193">Usar a prevenção contra perda de dados do Microsoft EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="08198-193">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="08198-194">Confira também</span><span class="sxs-lookup"><span data-stu-id="08198-194">See also</span></span>

- [<span data-ttu-id="08198-195">Introdução à prevenção contra perda de dados do Microsoft EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="08198-195">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="08198-196">Usar a prevenção contra perda de dados do Microsoft EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="08198-196">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="08198-197">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="08198-197">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="08198-198">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="08198-198">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="08198-199">Começar a usar o Explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="08198-199">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="08198-200">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="08198-200">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="08198-201">Gerenciamento de risco interno</span><span class="sxs-lookup"><span data-stu-id="08198-201">Insider Risk management</span></span>](insider-risk-management.md)