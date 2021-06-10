---
title: Investigar um endereço IP associado a um alerta
description: Use as opções de investigação para examinar a possível comunicação entre dispositivos e endereços IP externos.
keywords: investigar, investigação, endereço IP, alerta, Microsoft Defender para Ponto de Extremidade, IP externo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: cb95deb890b52f0f5fde26a3a193181713b8ae5f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933824"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="43d5d-104">Investigar um endereço IP associado a um alerta do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="43d5d-104">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="43d5d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="43d5d-105">**Applies to:**</span></span>
- [<span data-ttu-id="43d5d-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="43d5d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="43d5d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43d5d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="43d5d-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="43d5d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="43d5d-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="43d5d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="43d5d-110">Examine a possível comunicação entre seus dispositivos e endereços IP (protocolo IP) externos.</span><span class="sxs-lookup"><span data-stu-id="43d5d-110">Examine possible communication between your devices and external internet protocol (IP) addresses.</span></span>

<span data-ttu-id="43d5d-111">Identificar todos os dispositivos na organização que se comunicaram com um endereço IP suspeito ou conhecido mal-intencionado, como servidores de Comando e Controle (C2), ajuda a determinar o escopo potencial de violação, arquivos associados e dispositivos infectados.</span><span class="sxs-lookup"><span data-stu-id="43d5d-111">Identifying all devices in the organization that communicated with a suspected or known malicious IP address, such as Command and Control (C2) servers, helps determine the potential scope of breach, associated files, and infected devices.</span></span>

<span data-ttu-id="43d5d-112">Você pode encontrar informações das seguintes seções no exibição de endereço IP:</span><span class="sxs-lookup"><span data-stu-id="43d5d-112">You can find information from the following sections in the IP address view:</span></span>

- <span data-ttu-id="43d5d-113">IP em todo o mundo</span><span class="sxs-lookup"><span data-stu-id="43d5d-113">IP worldwide</span></span>
- <span data-ttu-id="43d5d-114">Nomes DNS reverso</span><span class="sxs-lookup"><span data-stu-id="43d5d-114">Reverse DNS names</span></span>
- <span data-ttu-id="43d5d-115">Alertas relacionados a esse IP</span><span class="sxs-lookup"><span data-stu-id="43d5d-115">Alerts related to this IP</span></span>
- <span data-ttu-id="43d5d-116">IP na organização</span><span class="sxs-lookup"><span data-stu-id="43d5d-116">IP in organization</span></span>
- <span data-ttu-id="43d5d-117">Prevalência</span><span class="sxs-lookup"><span data-stu-id="43d5d-117">Prevalence</span></span>

## <a name="ip-worldwide-and-reverse-dns-names"></a><span data-ttu-id="43d5d-118">Nomes DNS de IP em todo o mundo e dns reverso</span><span class="sxs-lookup"><span data-stu-id="43d5d-118">IP Worldwide and Reverse DNS names</span></span>

<span data-ttu-id="43d5d-119">A seção Detalhes do endereço IP mostra atributos do endereço IP, como seu ASN e seus nomes DNS reverso.</span><span class="sxs-lookup"><span data-stu-id="43d5d-119">The IP address details section shows attributes of the IP address such as its ASN and its Reverse DNS names.</span></span>

## <a name="alerts-related-to-this-ip"></a><span data-ttu-id="43d5d-120">Alertas relacionados a esse IP</span><span class="sxs-lookup"><span data-stu-id="43d5d-120">Alerts related to this IP</span></span>

<span data-ttu-id="43d5d-121">A **seção Alertas relacionados** a esse IP fornece uma lista de alertas associados ao IP.</span><span class="sxs-lookup"><span data-stu-id="43d5d-121">The **Alerts related to this IP** section provides a list of alerts that are associated with the IP.</span></span>

## <a name="ip-in-organization"></a><span data-ttu-id="43d5d-122">IP na organização</span><span class="sxs-lookup"><span data-stu-id="43d5d-122">IP in organization</span></span>

<span data-ttu-id="43d5d-123">A **seção IP na organização** fornece detalhes sobre a prevalência do endereço IP na organização.</span><span class="sxs-lookup"><span data-stu-id="43d5d-123">The **IP in organization** section provides details on the prevalence of the IP address in the organization.</span></span>

## <a name="prevalence"></a><span data-ttu-id="43d5d-124">Prevalência</span><span class="sxs-lookup"><span data-stu-id="43d5d-124">Prevalence</span></span>

<span data-ttu-id="43d5d-125">A **seção Prevalência** exibe quantos dispositivos se conectaram a esse endereço IP e quando o IP foi visto pela primeira e última vez.</span><span class="sxs-lookup"><span data-stu-id="43d5d-125">The **Prevalence** section displays how many devices have connected to this IP address, and when the IP was first and last seen.</span></span> <span data-ttu-id="43d5d-126">Você pode filtrar os resultados desta seção por período de tempo; o período padrão é de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="43d5d-126">You can filter the results of this section by time period; the default period is 30 days.</span></span>

## <a name="most-recent-observed-devices-with-ip"></a><span data-ttu-id="43d5d-127">Dispositivos observados mais recentes com IP</span><span class="sxs-lookup"><span data-stu-id="43d5d-127">Most recent observed devices with IP</span></span>

<span data-ttu-id="43d5d-128">A **seção Dispositivos observados mais** recentes com IP fornece uma exibição cronológica sobre os eventos e alertas associados que foram observados no endereço IP.</span><span class="sxs-lookup"><span data-stu-id="43d5d-128">The **Most recent observed devices** with IP section provides a chronological view on the events and associated alerts that were observed on the IP address.</span></span>

<span data-ttu-id="43d5d-129">**Investigar um IP externo:**</span><span class="sxs-lookup"><span data-stu-id="43d5d-129">**Investigate an external IP:**</span></span>

1. <span data-ttu-id="43d5d-130">Selecione **IP** no menu suspenso **da barra** de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="43d5d-130">Select **IP** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="43d5d-131">Insira o endereço IP no **campo** Pesquisa.</span><span class="sxs-lookup"><span data-stu-id="43d5d-131">Enter the IP address in the **Search** field.</span></span>
3. <span data-ttu-id="43d5d-132">Clique no ícone de pesquisa ou pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="43d5d-132">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="43d5d-133">Detalhes sobre o endereço IP são exibidos, incluindo: detalhes do registro (se disponível), IPs reversos (por exemplo, domínios), prevalência de dispositivos na organização que se comunicaram com esse Endereço IP (durante o período selecionável) e os dispositivos na organização que foram observados se comunicando com esse endereço IP.</span><span class="sxs-lookup"><span data-stu-id="43d5d-133">Details about the IP address are displayed, including: registration details (if available), reverse IPs (for example, domains), prevalence of devices in the organization that communicated with this IP Address (during selectable time period), and the devices in the organization that were observed communicating with this IP address.</span></span>

> [!NOTE]
> <span data-ttu-id="43d5d-134">Os resultados da pesquisa só serão retornados para endereços IP observados na comunicação com dispositivos na organização.</span><span class="sxs-lookup"><span data-stu-id="43d5d-134">Search results will only be returned for IP addresses observed in communication with devices in the organization.</span></span>

<span data-ttu-id="43d5d-135">Use os filtros de pesquisa para definir os critérios de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="43d5d-135">Use the search filters to define the search criteria.</span></span> <span data-ttu-id="43d5d-136">Você também pode usar a caixa de pesquisa linha do tempo para filtrar os resultados exibidos de todos os dispositivos na organização observados se comunicando com o endereço IP, o arquivo associado à comunicação e a última data observada.</span><span class="sxs-lookup"><span data-stu-id="43d5d-136">You can also use the timeline search box to filter the displayed results of all devices in the organization observed communicating with the IP address, the file associated with the communication and the last date observed.</span></span>

<span data-ttu-id="43d5d-137">Clicar em qualquer um dos nomes de dispositivo o levará ao ponto de vista desse dispositivo, onde você pode continuar a investigar alertas, comportamentos e eventos relatados.</span><span class="sxs-lookup"><span data-stu-id="43d5d-137">Clicking any of the device names will take you to that device's view, where you can continue investigate reported alerts, behaviors, and events.</span></span>

## <a name="related-topics"></a><span data-ttu-id="43d5d-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="43d5d-138">Related topics</span></span>

- [<span data-ttu-id="43d5d-139">Exibir e organizar a fila de alertas do Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="43d5d-139">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="43d5d-140">Gerenciar alertas do Microsoft Defender para Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="43d5d-140">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="43d5d-141">Investigar alertas do Microsoft Defender para Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="43d5d-141">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="43d5d-142">Investigar um arquivo associado a um alerta do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="43d5d-142">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="43d5d-143">Investigar dispositivos na lista do Microsoft Defender for Endpoint Devices</span><span class="sxs-lookup"><span data-stu-id="43d5d-143">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="43d5d-144">Investigar um domínio associado a um alerta do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="43d5d-144">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="43d5d-145">Investigar uma conta de usuário no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="43d5d-145">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
