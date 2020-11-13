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
ms.openlocfilehash: 966e201acb8038d85f0d06c0800c9845fd79097e
ms.sourcegitcommit: 89f56c3e0b619a4700a75a21927d9ffc90658632
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "48984925"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="d4b4b-104">Saiba mais sobre a prevenção contra perda de dados do Microsoft 365 Endpoint</span><span class="sxs-lookup"><span data-stu-id="d4b4b-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="d4b4b-p102">Use a prevenção contra perda de dados (DLP) do Microsoft 365 para monitorar as ações que estão sendo executadas em itens que você determinou como confidenciais e para ajudar a evitar o compartilhamento não intencional desses itens. Para obter mais informações sobre DLP, confira [Visão geral da prevenção contra perda de dados](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d4b4b-p102">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items. For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="d4b4b-p103">A **Prevenção contra perda de dados** (DLP do ponto de extremidade) estende os recursos de monitoramento e proteção de atividades do DLP a itens confidenciais que estão nos dispositivos Windows 10. Uma vez que os dispositivos são integrados nas soluções do Centro de conformidade do Microsoft 365, as informações sobre o que os usuários estão fazendo com itens confidenciais ficam visíveis no [explorador de atividades](data-classification-activity-explorer.md) e você pode aplicar ações de proteção nesses itens através de [políticas DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="d4b4b-p103">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices. Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="d4b4b-109">Atividades do ponto de extremidade que você pode monitorar e executar</span><span class="sxs-lookup"><span data-stu-id="d4b4b-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="d4b4b-p104">O Microsoft Endpoint DLP permite a auditoria e o gerenciamento dos seguintes tipos de atividades que os usuários realizam em itens confidenciais em dispositivos que executam o Windows 10. Isso inclui:</span><span class="sxs-lookup"><span data-stu-id="d4b4b-p104">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10. This includes:</span></span>


|<span data-ttu-id="d4b4b-112">atividade no item</span><span class="sxs-lookup"><span data-stu-id="d4b4b-112">activity on item</span></span> |<span data-ttu-id="d4b4b-113">auditável/restringivel</span><span class="sxs-lookup"><span data-stu-id="d4b4b-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="d4b4b-114">criado</span><span class="sxs-lookup"><span data-stu-id="d4b4b-114">created</span></span>    | <span data-ttu-id="d4b4b-115">auditável</span><span class="sxs-lookup"><span data-stu-id="d4b4b-115">auditable</span></span>      |
|<span data-ttu-id="d4b4b-116">renomeado</span><span class="sxs-lookup"><span data-stu-id="d4b4b-116">renamed</span></span>    |  <span data-ttu-id="d4b4b-117">auditável</span><span class="sxs-lookup"><span data-stu-id="d4b4b-117">auditable</span></span>       |
|<span data-ttu-id="d4b4b-118">copiado ou criado em mídia removível</span><span class="sxs-lookup"><span data-stu-id="d4b4b-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="d4b4b-119">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="d4b4b-119">auditable and restrictable</span></span>|
|<span data-ttu-id="d4b4b-120">copiado para compartilhamento de rede, por exemplo \\my-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="d4b4b-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="d4b4b-121">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="d4b4b-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="d4b4b-122">impresso</span><span class="sxs-lookup"><span data-stu-id="d4b4b-122">printed</span></span> |    <span data-ttu-id="d4b4b-123">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="d4b4b-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="d4b4b-124">copiado para a nuvem por meio do Chromium Edge</span><span class="sxs-lookup"><span data-stu-id="d4b4b-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="d4b4b-125">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="d4b4b-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="d4b4b-126">acessado por aplicativos e navegadores que não tem permissão de acesso</span><span class="sxs-lookup"><span data-stu-id="d4b4b-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="d4b4b-127">auditável e restringível</span><span class="sxs-lookup"><span data-stu-id="d4b4b-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="d4b4b-128">O que é diferente no Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="d4b4b-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="d4b4b-129">Há alguns conceitos adicionais que você precisa saber antes de mergulhar no Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="d4b4b-130">Habilitar o gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="d4b4b-130">Enabling Device management</span></span>

<span data-ttu-id="d4b4b-p105">O gerenciamento de dispositivos é a funcionalidade que permite a coleção de telemetria de dispositivos e as traz para as soluções do Centro de conformidade do Microsoft 365, como DLP do ponto de extremidade e [Gerenciamento de risco interno](insider-risk-management.md). Será necessário integrar todos os dispositivos que deseja usar como locais nas políticas DLP.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-p105">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md). You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d4b4b-133">![habilite o gerenciamento de dispositivos](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="d4b4b-133">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="d4b4b-p106">A integração e a remoção são tratadas através de scripts baixados do Centro de gerenciamento de dispositivos. O centro tem scripts personalizados para cada um desses métodos de implantação:</span><span class="sxs-lookup"><span data-stu-id="d4b4b-p106">Onboarding and offboarding are handled via scripts you download from the Device management center. The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="d4b4b-136">script local (até 10 computadores)</span><span class="sxs-lookup"><span data-stu-id="d4b4b-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="d4b4b-137">Política de grupo</span><span class="sxs-lookup"><span data-stu-id="d4b4b-137">Group policy</span></span>
- <span data-ttu-id="d4b4b-138">System Center Configuration Manager (versão 1610 ou posterior)</span><span class="sxs-lookup"><span data-stu-id="d4b4b-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="d4b4b-139">Gerenciamento de dispositivos móveis/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d4b4b-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="d4b4b-140">Scripts de integração VDI para máquinas não persistentes</span><span class="sxs-lookup"><span data-stu-id="d4b4b-140">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d4b4b-141">![página de integração de dispositivos](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="d4b4b-141">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="d4b4b-142">Use os procedimentos no [Introdução ao Microsoft 365 Endpoint DPL](endpoint-dlp-getting-started.md) para dispositivos integrados.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="d4b4b-143">Se você tiver dispositivos integrados por meio do [Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/), esses dispositivos aparecerão automaticamente na lista de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-143">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d4b4b-144">![lista de dispositivos gerenciados](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="d4b4b-144">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="d4b4b-145">Exibir dados de DLP do Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d4b4b-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="d4b4b-p107">O DLP do ponto de extremidade monitora a atividade com base no tipo MIME, de modo que as atividades serão capturadas mesmo que a extensão do arquivo seja alterada. Na visualização pública, são vistos todos:</span><span class="sxs-lookup"><span data-stu-id="d4b4b-p107">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed. At public preview it watches all:</span></span>

- <span data-ttu-id="d4b4b-148">Arquivos do Word</span><span class="sxs-lookup"><span data-stu-id="d4b4b-148">Word files</span></span>
- <span data-ttu-id="d4b4b-149">Arquivos do PowerPoint</span><span class="sxs-lookup"><span data-stu-id="d4b4b-149">PowerPoint files</span></span>
- <span data-ttu-id="d4b4b-150">Arquivos do Excel</span><span class="sxs-lookup"><span data-stu-id="d4b4b-150">Excel files</span></span>
- <span data-ttu-id="d4b4b-151">Arquivos PDF</span><span class="sxs-lookup"><span data-stu-id="d4b4b-151">PDF files</span></span>
- <span data-ttu-id="d4b4b-152">Arquivos .csv</span><span class="sxs-lookup"><span data-stu-id="d4b4b-152">.csv files</span></span>
- <span data-ttu-id="d4b4b-153">Arquivos .tsv</span><span class="sxs-lookup"><span data-stu-id="d4b4b-153">.tsv files</span></span>
- <span data-ttu-id="d4b4b-154">Arquivos .txt</span><span class="sxs-lookup"><span data-stu-id="d4b4b-154">.txt files</span></span>
- <span data-ttu-id="d4b4b-155">Arquivos .rtf</span><span class="sxs-lookup"><span data-stu-id="d4b4b-155">.rtf files</span></span>
- <span data-ttu-id="d4b4b-156">Arquivos .c</span><span class="sxs-lookup"><span data-stu-id="d4b4b-156">.c files</span></span>
- <span data-ttu-id="d4b4b-157">Arquivos .class</span><span class="sxs-lookup"><span data-stu-id="d4b4b-157">.class files</span></span>
- <span data-ttu-id="d4b4b-158">Arquivos .cpp</span><span class="sxs-lookup"><span data-stu-id="d4b4b-158">.cpp files</span></span>
- <span data-ttu-id="d4b4b-159">Arquivos .cs</span><span class="sxs-lookup"><span data-stu-id="d4b4b-159">.cs files</span></span>
- <span data-ttu-id="d4b4b-160">Arquivos .h</span><span class="sxs-lookup"><span data-stu-id="d4b4b-160">.h files</span></span>
- <span data-ttu-id="d4b4b-161">Arquivos .java</span><span class="sxs-lookup"><span data-stu-id="d4b4b-161">.java files</span></span>

> [!NOTE]
> <span data-ttu-id="d4b4b-p108">O DLP de ponto de extremidade avalia os arquivos de todos os tipos acima em relação à política de DLP e aplica as ações de proteção de acordo. Todos os arquivos que correspondem a uma política DLP recebem auditoria de todas as ações com suporte, mesmo que não estejam bloqueadas. Além disso, a atividade de arquivo realizada em qualquer arquivo do Word, PowerPoint, Excel, PDF e .csv é auditado por padrão, independentemente da existência de uma política DLP ou da correspondência desses arquivos.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-p108">Endpoint DLP evaluates files of all the above types against the DLP policy and applies protection actions accordingly. All files that match a DLP policy are audited for all supported actions, even if they aren't blocked. In addition, file activity performed on any Word, PowerPoint, Excel, PDF, and .csv file is audited by default, independent of whether a DLP policy exists or matches these files.</span></span>

<span data-ttu-id="d4b4b-165">Após a integração de um dispositivo, as informações sobre atividades auditadas fluem para o Gerenciador de atividade mesmo antes de você configurar e implantar qualquer política de DLP que tenha dispositivos como local.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-165">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d4b4b-166">![eventos do DLP do ponto de extremidade no gerenciador de atividades](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="d4b4b-166">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="d4b4b-167">O DLP do ponto de extremidade coleta informações abrangentes sobre a atividade auditada.</span><span class="sxs-lookup"><span data-stu-id="d4b4b-167">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="d4b4b-168">Por exemplo, se um arquivo for copiado para uma mídia USB removível, você verá esses atributos nos detalhes da atividade:</span><span class="sxs-lookup"><span data-stu-id="d4b4b-168">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="d4b4b-169">tipo de atividade</span><span class="sxs-lookup"><span data-stu-id="d4b4b-169">activity type</span></span>
- <span data-ttu-id="d4b4b-170">IP do Cliente</span><span class="sxs-lookup"><span data-stu-id="d4b4b-170">client IP</span></span>
- <span data-ttu-id="d4b4b-171">caminho do arquivo de destino</span><span class="sxs-lookup"><span data-stu-id="d4b4b-171">target file path</span></span>
- <span data-ttu-id="d4b4b-172">carimbo de data/hora ocorrido</span><span class="sxs-lookup"><span data-stu-id="d4b4b-172">happened timestamp</span></span>
- <span data-ttu-id="d4b4b-173">nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="d4b4b-173">file name</span></span>
- <span data-ttu-id="d4b4b-174">usuário</span><span class="sxs-lookup"><span data-stu-id="d4b4b-174">user</span></span>
- <span data-ttu-id="d4b4b-175">extensão do arquivo</span><span class="sxs-lookup"><span data-stu-id="d4b4b-175">file extension</span></span>
- <span data-ttu-id="d4b4b-176">tamanho do arquivo</span><span class="sxs-lookup"><span data-stu-id="d4b4b-176">file size</span></span>
- <span data-ttu-id="d4b4b-177">tipo de informação confidencial (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="d4b4b-177">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="d4b4b-178">valor SHA1</span><span class="sxs-lookup"><span data-stu-id="d4b4b-178">sha1 value</span></span>
- <span data-ttu-id="d4b4b-179">valor SHA256</span><span class="sxs-lookup"><span data-stu-id="d4b4b-179">sha256 value</span></span>
- <span data-ttu-id="d4b4b-180">nome do arquivo anterior</span><span class="sxs-lookup"><span data-stu-id="d4b4b-180">previous file name</span></span>
- <span data-ttu-id="d4b4b-181">localização</span><span class="sxs-lookup"><span data-stu-id="d4b4b-181">location</span></span>
- <span data-ttu-id="d4b4b-182">primário</span><span class="sxs-lookup"><span data-stu-id="d4b4b-182">parent</span></span>
- <span data-ttu-id="d4b4b-183">FilePath</span><span class="sxs-lookup"><span data-stu-id="d4b4b-183">filepath</span></span>
- <span data-ttu-id="d4b4b-184">Tipo de local de origem</span><span class="sxs-lookup"><span data-stu-id="d4b4b-184">source location type</span></span>
- <span data-ttu-id="d4b4b-185">plataforma</span><span class="sxs-lookup"><span data-stu-id="d4b4b-185">platform</span></span>
- <span data-ttu-id="d4b4b-186">nome do dispositivo</span><span class="sxs-lookup"><span data-stu-id="d4b4b-186">device name</span></span>
- <span data-ttu-id="d4b4b-187">Tipo de local de destino</span><span class="sxs-lookup"><span data-stu-id="d4b4b-187">destination location type</span></span>
- <span data-ttu-id="d4b4b-188">aplicativo que executou a cópia</span><span class="sxs-lookup"><span data-stu-id="d4b4b-188">application that performed the copy</span></span>
- <span data-ttu-id="d4b4b-189">ID de dispositivo do Microsoft Defender para Ponto de Extremidade (se aplicável)</span><span class="sxs-lookup"><span data-stu-id="d4b4b-189">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="d4b4b-190">fabricante do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="d4b4b-190">removable media device manufacturer</span></span>
- <span data-ttu-id="d4b4b-191">modelo do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="d4b4b-191">removable media device model</span></span>
- <span data-ttu-id="d4b4b-192">número de série do dispositivo de mídia removível</span><span class="sxs-lookup"><span data-stu-id="d4b4b-192">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d4b4b-193">![copiar para atributos de atividades USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="d4b4b-193">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="d4b4b-194">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="d4b4b-194">Next steps</span></span>

<span data-ttu-id="d4b4b-195">Agora que você aprendeu sobre o Endpoint DLP, as próximas etapas são:</span><span class="sxs-lookup"><span data-stu-id="d4b4b-195">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="d4b4b-196">Introdução à prevenção contra perda de dados do Microsoft EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="d4b4b-196">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="d4b4b-197">Usar a prevenção contra perda de dados do Microsoft EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="d4b4b-197">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="d4b4b-198">Confira também</span><span class="sxs-lookup"><span data-stu-id="d4b4b-198">See also</span></span>

- [<span data-ttu-id="d4b4b-199">Introdução à prevenção contra perda de dados do Microsoft EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="d4b4b-199">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="d4b4b-200">Usar a prevenção contra perda de dados do Microsoft EndPoint (visualização)</span><span class="sxs-lookup"><span data-stu-id="d4b4b-200">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="d4b4b-201">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="d4b4b-201">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="d4b4b-202">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="d4b4b-202">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="d4b4b-203">Começar a usar o Explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="d4b4b-203">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="d4b4b-204">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d4b4b-204">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="d4b4b-205">Gerenciamento de risco interno</span><span class="sxs-lookup"><span data-stu-id="d4b4b-205">Insider Risk management</span></span>](insider-risk-management.md)
