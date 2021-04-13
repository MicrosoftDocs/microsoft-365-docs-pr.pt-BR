---
title: Solucionar problemas com ferramentas de relatórios para o Microsoft Defender AV
description: Identificar e resolver problemas comuns ao tentar relatar o status de proteção do Microsoft Defender AV no Update Compliance
keywords: solução de problemas, erro, correção, conformidade de atualização, oms, monitor, relatório, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3b1a1c807c86aa95148300298484319001b59963
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690017"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a><span data-ttu-id="3918b-104">Solucionar problemas de relatórios do Microsoft Defender Antivírus em Conformidade com Atualizações</span><span class="sxs-lookup"><span data-stu-id="3918b-104">Troubleshoot Microsoft Defender Antivirus reporting in Update Compliance</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3918b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="3918b-105">**Applies to:**</span></span>

- [<span data-ttu-id="3918b-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="3918b-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> <span data-ttu-id="3918b-107">Em 31 de março de 2020, o recurso de relatório do Microsoft Defender Antivírus de Conformidade de Atualização será removido.</span><span class="sxs-lookup"><span data-stu-id="3918b-107">On March 31, 2020, the Microsoft Defender Antivirus reporting feature of Update Compliance will be removed.</span></span> <span data-ttu-id="3918b-108">Você pode continuar a definir e revisar políticas de conformidade de segurança usando o [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), o que permite um controle mais preciso sobre recursos e atualizações de segurança.</span><span class="sxs-lookup"><span data-stu-id="3918b-108">You can continue to define and review security compliance policies using [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), which allows finer control over security features and updates.</span></span>

<span data-ttu-id="3918b-109">Você pode usar o Microsoft Defender Antivírus com Conformidade de Atualização.</span><span class="sxs-lookup"><span data-stu-id="3918b-109">You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="3918b-110">Você verá status para licenças E3, B, F1, VL e Pro.</span><span class="sxs-lookup"><span data-stu-id="3918b-110">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="3918b-111">No entanto, para licenças do E5, você precisa usar o [portal do Microsoft Defender para Ponto de Extremidade.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)</span><span class="sxs-lookup"><span data-stu-id="3918b-111">However, for E5 licenses, you need to use the [Microsoft Defender for Endpoint portal](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="3918b-112">Para saber mais sobre opções de licenciamento, consulte Opções de licenciamento [de produto do Windows 10.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)</span><span class="sxs-lookup"><span data-stu-id="3918b-112">To learn more about licensing options, see [Windows 10 product licensing options](https://www.microsoft.com/licensing/product-licensing/windows10.aspx).</span></span>

<span data-ttu-id="3918b-113">Quando você usa a Conformidade de Atualização do Windows Analytics para obter relatórios sobre o status de proteção de [dispositivos](/windows/deployment/update/update-compliance-using#wdav-assessment) ou pontos de extremidade em sua rede que estão usando o Microsoft Defender Antivírus, você pode encontrar problemas ou problemas.</span><span class="sxs-lookup"><span data-stu-id="3918b-113">When you use [Windows Analytics Update Compliance to obtain reporting into the protection status of devices or endpoints](/windows/deployment/update/update-compliance-using#wdav-assessment) in your network that are using Microsoft Defender Antivirus, you might encounter problems or issues.</span></span>

<span data-ttu-id="3918b-114">Normalmente, os indicadores mais comuns de um problema são:</span><span class="sxs-lookup"><span data-stu-id="3918b-114">Typically, the most common indicators of a problem are:</span></span>
- <span data-ttu-id="3918b-115">Você só vê um pequeno número ou subconjunto de todos os dispositivos que você estava esperando ver</span><span class="sxs-lookup"><span data-stu-id="3918b-115">You only see a small number or subset of all the devices you were expecting to see</span></span>
- <span data-ttu-id="3918b-116">Você não vê nenhum dispositivo</span><span class="sxs-lookup"><span data-stu-id="3918b-116">You do not see any devices at all</span></span>
- <span data-ttu-id="3918b-117">Os relatórios e informações que você vê estão desatualizados (mais antigos do que alguns dias)</span><span class="sxs-lookup"><span data-stu-id="3918b-117">The reports and information you do see is outdated (older than a few days)</span></span>

<span data-ttu-id="3918b-118">Para códigos de erro comuns e IDs de evento relacionadas ao serviço Microsoft Defender Antivírus que não estão relacionados à Conformidade de Atualização, consulte Eventos do [Microsoft Defender Antivírus](troubleshoot-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="3918b-118">For common error codes and event IDs related to the Microsoft Defender Antivirus service that are not related to Update Compliance, see [Microsoft Defender Antivirus events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="3918b-119">Há três etapas para solucionar esses problemas:</span><span class="sxs-lookup"><span data-stu-id="3918b-119">There are three steps to troubleshooting these problems:</span></span>

1. <span data-ttu-id="3918b-120">Confirme se você atendeu a todos os pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="3918b-120">Confirm that you have met all prerequisites</span></span>
2. <span data-ttu-id="3918b-121">Verifique sua conectividade com o serviço Windows Defender baseado em nuvem</span><span class="sxs-lookup"><span data-stu-id="3918b-121">Check your connectivity to the Windows Defender cloud-based service</span></span>
3. <span data-ttu-id="3918b-122">Enviar logs de suporte</span><span class="sxs-lookup"><span data-stu-id="3918b-122">Submit support logs</span></span>

>[!IMPORTANT]
><span data-ttu-id="3918b-123">Normalmente, leva 3 dias para que os dispositivos comecem a aparecer em Conformidade de Atualização.</span><span class="sxs-lookup"><span data-stu-id="3918b-123">It typically takes 3 days for devices to start appearing in Update Compliance.</span></span>


## <a name="confirm-prerequisites"></a><span data-ttu-id="3918b-124">Confirmar pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="3918b-124">Confirm prerequisites</span></span>

<span data-ttu-id="3918b-125">Para que os dispositivos mostrem corretamente em Conformidade de Atualização, você precisa atender a determinados pré-requisitos para o serviço de Conformidade de Atualização e para o Microsoft Defender Antivírus:</span><span class="sxs-lookup"><span data-stu-id="3918b-125">In order for devices to properly show up in Update Compliance, you have to meet certain prerequisites for both the Update Compliance service and for Microsoft Defender Antivirus:</span></span>

>[!div class="checklist"]
>- <span data-ttu-id="3918b-126">Os pontos de extremidade estão usando o Microsoft Defender Antivírus como o único aplicativo de proteção antivírus.</span><span class="sxs-lookup"><span data-stu-id="3918b-126">Endpoints are using Microsoft Defender Antivirus as the sole antivirus protection app.</span></span> <span data-ttu-id="3918b-127">[O uso de qualquer outro aplicativo antivírus](microsoft-defender-antivirus-compatibility.md) fará com que o Microsoft Defender AV se desabilite e o ponto de extremidade não será relatado em Conformidade de Atualização.</span><span class="sxs-lookup"><span data-stu-id="3918b-127">[Using any other antivirus app will cause Microsoft Defender AV to disable itself](microsoft-defender-antivirus-compatibility.md) and the endpoint will not be reported in Update Compliance.</span></span>
> - <span data-ttu-id="3918b-128">[A proteção entregue na nuvem está habilitada](enable-cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="3918b-128">[Cloud-delivered protection is enabled](enable-cloud-protection-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="3918b-129">Os pontos de extremidade podem [se conectar à nuvem do Microsoft Defender AV](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="3918b-129">Endpoints can [connect to the Microsoft Defender AV cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span></span>
> - <span data-ttu-id="3918b-130">Se o ponto de extremidade estiver executando o Windows 10 versão 1607 ou anterior, os dados de diagnóstico do Windows 10 devem ser definidos para [o nível aprimorado](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).</span><span class="sxs-lookup"><span data-stu-id="3918b-130">If the endpoint is running Windows 10 version 1607 or earlier, [Windows 10 diagnostic data must be set to the Enhanced level](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).</span></span>
> - <span data-ttu-id="3918b-131">Faz três dias que todos os requisitos foram atendidos</span><span class="sxs-lookup"><span data-stu-id="3918b-131">It has been 3 days since all requirements have been met</span></span>

<span data-ttu-id="3918b-132">"Você pode usar o Microsoft Defender Antivírus com Conformidade de Atualização.</span><span class="sxs-lookup"><span data-stu-id="3918b-132">“You can use Microsoft Defender Antivirus with Update Compliance.</span></span> <span data-ttu-id="3918b-133">Você verá status para licenças E3, B, F1, VL e Pro.</span><span class="sxs-lookup"><span data-stu-id="3918b-133">You’ll see status for E3, B, F1, VL, and Pro licenses.</span></span> <span data-ttu-id="3918b-134">No entanto, para licenças do E5, você precisa usar o portal do Microsoft Defender para Ponto de Extremidade ( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) .</span><span class="sxs-lookup"><span data-stu-id="3918b-134">However, for E5 licenses, you need to use the Microsoft Defender for Endpoint portal (https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="3918b-135">Para saber mais sobre opções de licenciamento, consulte Opções de licenciamento de produtos do Windows 10"</span><span class="sxs-lookup"><span data-stu-id="3918b-135">To learn more about licensing options, see Windows 10 product licensing options"</span></span>

<span data-ttu-id="3918b-136">Se todos os pré-requisitos acima foram atendidos, talvez seja necessário prosseguir para a próxima etapa para coletar informações de diagnóstico e enviá-la para nós.</span><span class="sxs-lookup"><span data-stu-id="3918b-136">If the above prerequisites have all been met, you might need to proceed to the next step to collect diagnostic information and send it to us.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3918b-137">Coletar dados de diagnóstico para solução de problemas de conformidade de atualização</span><span class="sxs-lookup"><span data-stu-id="3918b-137">Collect diagnostic data for Update Compliance troubleshooting</span></span>](collect-diagnostic-data.md)  

## <a name="related-topics"></a><span data-ttu-id="3918b-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3918b-138">Related topics</span></span>

- [<span data-ttu-id="3918b-139">Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="3918b-139">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="3918b-140">Implantar o Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="3918b-140">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)