---
title: Verifique o estado de saúde do sensor no Microsoft Defender para Ponto de Extremidade
description: Verifique a saúde do sensor em dispositivos para identificar quais estão configurados de forma mal configurada, inativas ou não estão relatando dados do sensor.
keywords: sensor, a saúde do sensor, configurada inativa, sem dados do sensor, dados do sensor, comunicações prejudicadas, comunicação
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
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 0361b7956339670d006c9f050274e07d4e979bca
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904159"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="2c1a0-104">Verificar o estado de saúde do sensor no Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2c1a0-104">Check sensor health state in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2c1a0-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="2c1a0-105">**Applies to:**</span></span>
- [<span data-ttu-id="2c1a0-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2c1a0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2c1a0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2c1a0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2c1a0-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="2c1a0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2c1a0-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="2c1a0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-checksensor-abovefoldlink)

<span data-ttu-id="2c1a0-110">O **painel Dispositivos com problemas** de sensor é encontrado no painel Operações de Segurança.</span><span class="sxs-lookup"><span data-stu-id="2c1a0-110">The **Devices with sensor issues** tile is found on the Security Operations dashboard.</span></span> <span data-ttu-id="2c1a0-111">Esse tile fornece informações sobre a capacidade do dispositivo individual de fornecer dados do sensor e se comunicar com o serviço Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="2c1a0-111">This tile provides information on the individual device’s ability to provide sensor data and communicate with the Defender for Endpoint service.</span></span> <span data-ttu-id="2c1a0-112">Ele relata quantos dispositivos exigem atenção e ajuda você a identificar dispositivos problemáticos e a tomar medidas para corrigir problemas conhecidos.</span><span class="sxs-lookup"><span data-stu-id="2c1a0-112">It reports how many devices require attention and helps you identify problematic devices and take action to correct known issues.</span></span>

<span data-ttu-id="2c1a0-113">Há dois indicadores de status no azulejo que fornecem informações sobre o número de dispositivos que não estão relatando corretamente para o serviço:</span><span class="sxs-lookup"><span data-stu-id="2c1a0-113">There are two status indicators on the tile that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="2c1a0-114">**Configuração incorretamente** - Esses dispositivos podem estar relatando parcialmente dados do sensor para o serviço Defender para Ponto de Extremidade e podem ter erros de configuração que precisam ser corrigidos.</span><span class="sxs-lookup"><span data-stu-id="2c1a0-114">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="2c1a0-115">**Inativos** - Dispositivos que pararam de relatar para o serviço Defender para Ponto de Extremidade por mais de sete dias no mês passado.</span><span class="sxs-lookup"><span data-stu-id="2c1a0-115">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="2c1a0-116">Clicar em qualquer um dos grupos direciona você para a lista **Dispositivos**, filtrada de acordo com sua escolha.</span><span class="sxs-lookup"><span data-stu-id="2c1a0-116">Clicking any of the groups directs you to **Devices list**, filtered according to your choice.</span></span>

![Screenshot of Devices with sensor issues tile](images/atp-devices-with-sensor-issues-tile.png)

<span data-ttu-id="2c1a0-118">Na **lista Dispositivos,** você pode filtrar a lista de estado de saúde pelo seguinte status:</span><span class="sxs-lookup"><span data-stu-id="2c1a0-118">On **Devices list**, you can filter the health state list by the following status:</span></span>
- <span data-ttu-id="2c1a0-119">**Ativo** - Dispositivos que estão relatando ativamente para o serviço Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="2c1a0-119">**Active** - Devices that are actively reporting to the Defender for Endpoint service.</span></span>
- <span data-ttu-id="2c1a0-120">**Configuração incorretamente** - Esses dispositivos podem estar relatando parcialmente dados do sensor para o serviço Defender para Ponto de Extremidade, mas têm erros de configuração que precisam ser corrigidos.</span><span class="sxs-lookup"><span data-stu-id="2c1a0-120">**Misconfigured** - These devices might partially be reporting sensor data to the Defender for Endpoint service but have configuration errors that need to be corrected.</span></span> <span data-ttu-id="2c1a0-121">Dispositivos mal configurados podem ter um ou uma combinação dos seguintes problemas:</span><span class="sxs-lookup"><span data-stu-id="2c1a0-121">Misconfigured devices can have either one or a combination of the following issues:</span></span>
  - <span data-ttu-id="2c1a0-122">**Sem dados do sensor** - Os dispositivos pararam de enviar dados do sensor.</span><span class="sxs-lookup"><span data-stu-id="2c1a0-122">**No sensor data** - Devices has stopped sending sensor data.</span></span> <span data-ttu-id="2c1a0-123">Alertas limitados podem ser disparados do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2c1a0-123">Limited alerts can be triggered from the device.</span></span>
  - <span data-ttu-id="2c1a0-124">**Comunicações prejudicadas** - A capacidade de se comunicar com o dispositivo está prejudicada.</span><span class="sxs-lookup"><span data-stu-id="2c1a0-124">**Impaired communications** - Ability to communicate with device is impaired.</span></span> <span data-ttu-id="2c1a0-125">O envio de arquivos para análise profunda, bloqueio de arquivos, isolamento do dispositivo da rede e outras ações que exigem comunicação com o dispositivo pode não funcionar.</span><span class="sxs-lookup"><span data-stu-id="2c1a0-125">Sending files for deep analysis, blocking files, isolating device from network and other actions that require communication with the device may not work.</span></span>
- <span data-ttu-id="2c1a0-126">**Inativo -** Dispositivos que pararam de relatar para o serviço Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="2c1a0-126">**Inactive** - Devices that have stopped reporting to the Defender for Endpoint service.</span></span>

<span data-ttu-id="2c1a0-127">Você também pode baixar a lista inteira no formato CSV usando o **recurso Exportar.**</span><span class="sxs-lookup"><span data-stu-id="2c1a0-127">You can also download the entire list in CSV format using the **Export** feature.</span></span> <span data-ttu-id="2c1a0-128">Para obter mais informações sobre filtros, [consulte Exibir e organizar a lista Dispositivos](machines-view-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2c1a0-128">For more information on filters, see [View and organize the Devices list](machines-view-overview.md).</span></span>

>[!NOTE]
><span data-ttu-id="2c1a0-129">Exporte a lista no formato CSV para exibir os dados não filtrados.</span><span class="sxs-lookup"><span data-stu-id="2c1a0-129">Export the list in CSV format to display the unfiltered data.</span></span> <span data-ttu-id="2c1a0-130">O arquivo CSV incluirá todos os dispositivos na organização, independentemente de qualquer filtragem aplicada no próprio exibição e pode levar um tempo significativo para ser baixado, dependendo do tamanho da sua organização.</span><span class="sxs-lookup"><span data-stu-id="2c1a0-130">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself and can take a significant amount of time to download, depending on how large your organization is.</span></span>

![Captura de tela da página de lista Dispositivos](images/atp-devices-list-page.png)

<span data-ttu-id="2c1a0-132">Você pode exibir os detalhes do dispositivo quando clicar em um dispositivo mal configurado ou inativo.</span><span class="sxs-lookup"><span data-stu-id="2c1a0-132">You can view the device details when you click on a misconfigured or inactive device.</span></span>

## <a name="related-topic"></a><span data-ttu-id="2c1a0-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2c1a0-133">Related topic</span></span>
- [<span data-ttu-id="2c1a0-134">Corrigir sensores não salubres no Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="2c1a0-134">Fix unhealthy sensors in Defender for Endpoint</span></span>](fix-unhealthy-sensors.md)
