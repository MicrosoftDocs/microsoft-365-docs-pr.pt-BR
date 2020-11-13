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
description: 'A prevenção contra perda de dados do Microsoft 365 Endpoint estende o monitoramento de atividades de arquivo e ações de proteção desses arquivos para pontos de extremidade. Os arquivos ficam visíveis nas soluções do Centro de conformidade do Microsoft 365 '
ms.openlocfilehash: 0f69261cb5617c7d6de7900b85a5a254a04bc45e
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999450"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="798f8-104">Saiba mais sobre a prevenção contra perda de dados do Microsoft 365 Endpoint</span><span class="sxs-lookup"><span data-stu-id="798f8-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="798f8-p102">Use a prevenção contra perda de dados (DLP) do Microsoft 365 para monitorar as ações que estão sendo executadas em itens que você determinou como confidenciais e para ajudar a evitar o compartilhamento não intencional desses itens. Para obter mais informações sobre DLP, confira [Visão geral da prevenção contra perda de dados](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="798f8-p102">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items. For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="798f8-p103">A **Prevenção contra perda de dados** (DLP do ponto de extremidade) estende os recursos de monitoramento e proteção de atividades do DLP a itens confidenciais que estão nos dispositivos Windows 10. Uma vez que os dispositivos são integrados nas soluções do Centro de conformidade do Microsoft 365, as informações sobre o que os usuários estão fazendo com itens confidenciais ficam visíveis no [explorador de atividades](data-classification-activity-explorer.md) e você pode aplicar ações de proteção nesses itens através de [políticas DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="798f8-p103">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices. Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="798f8-109">Atividades do ponto de extremidade que você pode monitorar e executar</span><span class="sxs-lookup"><span data-stu-id="798f8-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="798f8-p104">O Microsoft Endpoint DLP permite a auditoria e o gerenciamento dos seguintes tipos de atividades que os usuários realizam em itens confidenciais em dispositivos que executam o Windows 10. Isso inclui:</span><span class="sxs-lookup"><span data-stu-id="798f8-p104">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10. This includes:</span></span>


|<span data-ttu-id="798f8-112">atividade no item</span><span class="sxs-lookup"><span data-stu-id="798f8-112">activity on item</span></span> |<span data-ttu-id="798f8-113">auditável/restringivel</span><span class="sxs-lookup"><span data-stu-id="798f8-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="798f8-114">criado</span><span class="sxs-lookup"><span data-stu-id="798f8-114">created</span></span>    | <span data-ttu-id="798f8-115">auditável</span><span class="sxs-lookup"><span data-stu-id="798f8-115">auditable</span></span>      |
|<span data-ttu-id="798f8-116">renomeado</span><span class="sxs-lookup"><span data-stu-id="798f8-116">renamed</span></span>    |  <span data-ttu-id="798f8-117">auditável</span><span class="sxs-lookup"><span data-stu-id="798f8-117">auditable</span></span>       |
|<span data-ttu-id="798f8-118">copiado ou criado em mídia removível</span><span class="sxs-lookup"><span data-stu-id="798f8-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="798f8-119">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="798f8-119">auditable and restrictable</span></span>|
|<span data-ttu-id="798f8-120">copiado para compartilhamento de rede, por exemplo \\my-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="798f8-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="798f8-121">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="798f8-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="798f8-122">impresso</span><span class="sxs-lookup"><span data-stu-id="798f8-122">printed</span></span> |    <span data-ttu-id="798f8-123">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="798f8-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="798f8-124">copiado para a nuvem por meio do Chromium Edge</span><span class="sxs-lookup"><span data-stu-id="798f8-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="798f8-125">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="798f8-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="798f8-126">acessado por aplicativos e navegadores que não tem permissão de acesso</span><span class="sxs-lookup"><span data-stu-id="798f8-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="798f8-127">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="798f8-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="798f8-128">O que é diferente no Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="798f8-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="798f8-129">Há alguns conceitos adicionais que você precisa saber antes de mergulhar no Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="798f8-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="798f8-130">Habilitar o gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="798f8-130">Enabling Device management</span></span>

<span data-ttu-id="798f8-p105">O gerenciamento de dispositivos é a funcionalidade que permite a coleção de telemetria de dispositivos e as traz para as soluções do Centro de conformidade do Microsoft 365, como DLP do ponto de extremidade e [Gerenciamento de risco interno](insider-risk-management.md). Será necessário integrar todos os dispositivos que deseja usar como locais nas políticas DLP.</span><span class="sxs-lookup"><span data-stu-id="798f8-p105">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md). You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="798f8-133">![habilite o gerenciamento de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="798f8-133">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="798f8-p106">A integração e a remoção são tratadas através de scripts baixados do Centro de gerenciamento de dispositivos. O centro tem scripts personalizados para cada um desses métodos de implantação:</span><span class="sxs-lookup"><span data-stu-id="798f8-p106">Onboarding and offboarding are handled via scripts you download from the Device management center. The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="798f8-136">script local (até 10 computadores)</span><span class="sxs-lookup"><span data-stu-id="798f8-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="798f8-137">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="798f8-137">Group policy</span></span>
- <span data-ttu-id="798f8-138">System Center Configuration Manager (versão 1610 ou posterior)</span><span class="sxs-lookup"><span data-stu-id="798f8-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="798f8-139">Gerenciamento de dispositivos móveis/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="798f8-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="798f8-140">Scripts de integração VDI para máquinas não persistentes</span><span class="sxs-lookup"><span data-stu-id="798f8-140">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="798f8-141">![página de integração de dispositivos](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="798f8-141">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="798f8-142">Use os procedimentos no [Introdução ao Microsoft 365 Endpoint DPL](endpoint-dlp-getting-started.md) para dispositivos integrados.</span><span class="sxs-lookup"><span data-stu-id="798f8-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="798f8-143">Se você tiver dispositivos integrados por meio do [Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/), esses dispositivos aparecerão automaticamente na lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="798f8-143">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="798f8-144">![lista de dispositivos gerenciados](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="798f8-144">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="798f8-145">Exibir dados de DLP do Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="798f8-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="798f8-p107">O DLP do ponto de extremidade monitora a atividade com base no tipo MIME, de modo que as atividades serão capturadas mesmo que a extensão do arquivo seja alterada. Na visualização pública, são vistos todos:</span><span class="sxs-lookup"><span data-stu-id="798f8-p107">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed. At public preview it watches all:</span></span>

- <span data-ttu-id="798f8-148">Arquivos do Word</span><span class="sxs-lookup"><span data-stu-id="798f8-148">Word files</span></span>
- <span data-ttu-id="798f8-149">Arquivos do PowerPoint</span><span class="sxs-lookup"><span data-stu-id="798f8-149">PowerPoint files</span></span>
- <span data-ttu-id="798f8-150">Arquivos do Excel</span><span class="sxs-lookup"><span data-stu-id="798f8-150">Excel files</span></span>
- <span data-ttu-id="798f8-151">Arquivos PDF</span><span class="sxs-lookup"><span data-stu-id="798f8-151">PDF files</span></span>
- <span data-ttu-id="798f8-152">Arquivos .csv</span><span class="sxs-lookup"><span data-stu-id="798f8-152">.csv files</span></span>
- <span data-ttu-id="798f8-153">Arquivos .tsv</span><span class="sxs-lookup"><span data-stu-id="798f8-153">.tsv files</span></span>
- <span data-ttu-id="798f8-154">Arquivos .txt</span><span class="sxs-lookup"><span data-stu-id="798f8-154">.txt files</span></span>
- <span data-ttu-id="798f8-155">Arquivos .rtf</span><span class="sxs-lookup"><span data-stu-id="798f8-155">.rtf files</span></span>
- <span data-ttu-id="798f8-156">Arquivos .c</span><span class="sxs-lookup"><span data-stu-id="798f8-156">.c files</span></span>
- <span data-ttu-id="798f8-157">Arquivos .class</span><span class="sxs-lookup"><span data-stu-id="798f8-157">.class files</span></span>
- <span data-ttu-id="798f8-158">Arquivos .cpp</span><span class="sxs-lookup"><span data-stu-id="798f8-158">.cpp files</span></span>
- <span data-ttu-id="798f8-159">Arquivos .cs</span><span class="sxs-lookup"><span data-stu-id="798f8-159">.cs files</span></span>
- <span data-ttu-id="798f8-160">Arquivos .h</span><span class="sxs-lookup"><span data-stu-id="798f8-160">.h files</span></span>
- <span data-ttu-id="798f8-161">Arquivos .java</span><span class="sxs-lookup"><span data-stu-id="798f8-161">.java files</span></span>

> [!NOTE]
> <span data-ttu-id="798f8-p108">O Endpoint DLP avalia arquivos de todos os tipos acima em relação à política DLP e aplica ações de proteção em conformidade. Todos os arquivos que correspondem a uma política DLP são auditados para todas as ações suportadas, mesmo que não estejam bloqueados. Além disso, a atividade de arquivos realizada em qualquer arquivo Word, PowerPoint, Excel, PDF e .csv é auditada por padrão, independente da existência de uma política DLP ou se ela corresponde a esses arquivos.</span><span class="sxs-lookup"><span data-stu-id="798f8-p108">Endpoint DLP evaluates files of all the above types against the DLP policy and applies protection actions accordingly. All files that match a DLP policy are audited for all supported actions, even if they aren't blocked. In addition, file activity performed on any Word, PowerPoint, Excel, PDF, and .csv file is audited by default, independent of whether a DLP policy exists or matches these files.</span></span>

<span data-ttu-id="798f8-165">Você pode visualizar os alertas relacionados às políticas DLP aplicadas em dispositivos de ponto de extremidade indo até o Painel de Gerenciamento de Alertas [DLP](dlp-configure-view-alerts-policies.md).</span><span class="sxs-lookup"><span data-stu-id="798f8-165">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

![Informações sobre alertas](../media/Alert-info-1.png)

<span data-ttu-id="798f8-167">Você também pode visualizar detalhes do evento associado com metadados ricos no mesmo painel</span><span class="sxs-lookup"><span data-stu-id="798f8-167">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

![informações do evento](../media/Event-info-1.png)

<span data-ttu-id="798f8-169">Depois que um dispositivo é integrado, as informações sobre as atividades auditadas fluem para o Gerenciador de atividade antes mesmo de configurar e implantar qualquer política DLP que tenha dispositivos como local.</span><span class="sxs-lookup"><span data-stu-id="798f8-169">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="798f8-170">![eventos do DLP do ponto de extremidade no gerenciador de atividades](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="798f8-170">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="798f8-171">O DLP do ponto de extremidade coleta informações abrangentes sobre a atividade auditada.</span><span class="sxs-lookup"><span data-stu-id="798f8-171">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="798f8-172">Por exemplo, se um arquivo for copiado para uma mídia USB removível, você verá esses atributos nos detalhes da atividade:</span><span class="sxs-lookup"><span data-stu-id="798f8-172">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="798f8-173">tipo de atividade</span><span class="sxs-lookup"><span data-stu-id="798f8-173">activity type</span></span>
- <span data-ttu-id="798f8-174">IP do Cliente</span><span class="sxs-lookup"><span data-stu-id="798f8-174">client IP</span></span>
- <span data-ttu-id="798f8-175">caminho do arquivo de destino</span><span class="sxs-lookup"><span data-stu-id="798f8-175">target file path</span></span>
- <span data-ttu-id="798f8-176">carimbo de data/hora ocorrido</span><span class="sxs-lookup"><span data-stu-id="798f8-176">happened timestamp</span></span>
- <span data-ttu-id="798f8-177">nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="798f8-177">file name</span></span>
- <span data-ttu-id="798f8-178">usuário</span><span class="sxs-lookup"><span data-stu-id="798f8-178">user</span></span>
- <span data-ttu-id="798f8-179">extensão do arquivo</span><span class="sxs-lookup"><span data-stu-id="798f8-179">file extension</span></span>
- <span data-ttu-id="798f8-180">tamanho do arquivo</span><span class="sxs-lookup"><span data-stu-id="798f8-180">file size</span></span>
- <span data-ttu-id="798f8-181">tipo de informação confidencial (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="798f8-181">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="798f8-182">valor SHA1</span><span class="sxs-lookup"><span data-stu-id="798f8-182">sha1 value</span></span>
- <span data-ttu-id="798f8-183">valor SHA256</span><span class="sxs-lookup"><span data-stu-id="798f8-183">sha256 value</span></span>
- <span data-ttu-id="798f8-184">nome do arquivo anterior</span><span class="sxs-lookup"><span data-stu-id="798f8-184">previous file name</span></span>
- <span data-ttu-id="798f8-185">localização</span><span class="sxs-lookup"><span data-stu-id="798f8-185">location</span></span>
- <span data-ttu-id="798f8-186">primário</span><span class="sxs-lookup"><span data-stu-id="798f8-186">parent</span></span>
- <span data-ttu-id="798f8-187">FilePath</span><span class="sxs-lookup"><span data-stu-id="798f8-187">filepath</span></span>
- <span data-ttu-id="798f8-188">Tipo de local de origem</span><span class="sxs-lookup"><span data-stu-id="798f8-188">source location type</span></span>
- <span data-ttu-id="798f8-189">plataforma</span><span class="sxs-lookup"><span data-stu-id="798f8-189">platform</span></span>
- <span data-ttu-id="798f8-190">nome do dispositivo</span><span class="sxs-lookup"><span data-stu-id="798f8-190">device name</span></span>
- <span data-ttu-id="798f8-191">Tipo de local de destino</span><span class="sxs-lookup"><span data-stu-id="798f8-191">destination location type</span></span>
- <span data-ttu-id="798f8-192">aplicativo que executou a cópia</span><span class="sxs-lookup"><span data-stu-id="798f8-192">application that performed the copy</span></span>
- <span data-ttu-id="798f8-193">ID de dispositivo do Microsoft Defender para Ponto de Extremidade (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="798f8-193">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="798f8-194">fabricante do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="798f8-194">removable media device manufacturer</span></span>
- <span data-ttu-id="798f8-195">modelo do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="798f8-195">removable media device model</span></span>
- <span data-ttu-id="798f8-196">número de série do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="798f8-196">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="798f8-197">![copiar para atributos de atividades USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="798f8-197">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="798f8-198">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="798f8-198">Next steps</span></span>

<span data-ttu-id="798f8-199">Agora que você aprendeu sobre o Endpoint DLP, as próximas etapas são:</span><span class="sxs-lookup"><span data-stu-id="798f8-199">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="798f8-200">Introdução à prevenção contra perda de dados do Microsoft EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="798f8-200">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="798f8-201">Usar a prevenção contra perda de dados do Microsoft EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="798f8-201">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="798f8-202">Confira também</span><span class="sxs-lookup"><span data-stu-id="798f8-202">See also</span></span>

- [<span data-ttu-id="798f8-203">Introdução à prevenção contra perda de dados do Microsoft EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="798f8-203">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="798f8-204">Usar a prevenção contra perda de dados do Microsoft EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="798f8-204">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="798f8-205">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="798f8-205">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="798f8-206">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="798f8-206">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="798f8-207">Começar a usar o Explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="798f8-207">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="798f8-208">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="798f8-208">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="798f8-209">Gerenciamento de risco interno</span><span class="sxs-lookup"><span data-stu-id="798f8-209">Insider Risk management</span></span>](insider-risk-management.md)
