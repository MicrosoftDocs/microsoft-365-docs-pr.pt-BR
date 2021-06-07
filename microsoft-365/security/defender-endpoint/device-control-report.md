---
title: Proteger dados da sua organização com controle de dispositivo
description: Monitore a segurança de dados da sua organização por meio de relatórios de controle de dispositivo.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: deniseb
author: denisebmsft
ms.reviewer: dansimp
ms.topic: article
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 47eb80af58c948db5997dc9f5edfa5737a796837
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772360"
---
# <a name="protect-your-organizations-data-with-device-control"></a><span data-ttu-id="62da0-103">Proteger dados da sua organização com controle de dispositivo</span><span class="sxs-lookup"><span data-stu-id="62da0-103">Protect your organization’s data with device control</span></span>

<span data-ttu-id="62da0-104">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span><span class="sxs-lookup"><span data-stu-id="62da0-104">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span></span>

<span data-ttu-id="62da0-105">O controle de dispositivo do Microsoft Defender for Endpoint protege contra perda de dados, monitorando e controlando o uso de mídia por dispositivos em sua organização, como o uso de dispositivos de armazenamento removíveis e unidades USB.</span><span class="sxs-lookup"><span data-stu-id="62da0-105">Microsoft Defender for Endpoint device control protects against data loss, by monitoring and controlling media use by devices in your organization, such as the use of removable storage devices and USB drives.</span></span>

<span data-ttu-id="62da0-106">Com o relatório de controle de dispositivo, você pode exibir eventos relacionados ao uso de mídia, como:</span><span class="sxs-lookup"><span data-stu-id="62da0-106">With the device control report, you can view events that relate to media usage, such as:</span></span>

- <span data-ttu-id="62da0-107">**Eventos de auditoria:** Mostra o número de eventos de auditoria que ocorrem quando a mídia externa está conectada.</span><span class="sxs-lookup"><span data-stu-id="62da0-107">**Audit events:** Shows the number of audit events that occur when external media is connected.</span></span>
- <span data-ttu-id="62da0-108">**Eventos de política:** Mostra o número de eventos de política que ocorrem quando uma política de controle de dispositivo é disparada.</span><span class="sxs-lookup"><span data-stu-id="62da0-108">**Policy events:** Shows the number of policy events that occur when a device control policy is triggered.</span></span>

> [!NOTE]
> <span data-ttu-id="62da0-109">O evento de auditoria para controlar o uso de mídia é habilitado por padrão para dispositivos conectados ao Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="62da0-109">The audit event to track media usage is enabled by default for devices onboarded to Microsoft Defender for Endpoint.</span></span>

## <a name="understanding-the-audit-events"></a><span data-ttu-id="62da0-110">Noções básicas sobre os eventos de auditoria</span><span class="sxs-lookup"><span data-stu-id="62da0-110">Understanding the audit events</span></span>

<span data-ttu-id="62da0-111">Os eventos de auditoria incluem:</span><span class="sxs-lookup"><span data-stu-id="62da0-111">The audit events include:</span></span>

- <span data-ttu-id="62da0-112">**Montagem e desmontagem da** unidade USB: Eventos de auditoria gerados quando uma unidade USB é montada ou desmontada.</span><span class="sxs-lookup"><span data-stu-id="62da0-112">**USB drive mount and unmount:** Audit events that are generated when a USB drive is mounted or unmounted.</span></span>
- <span data-ttu-id="62da0-113">**PnP:** Os eventos de auditoria Plug and Play são gerados quando o armazenamento removível, uma impressora ou Bluetooth mídia está conectada.</span><span class="sxs-lookup"><span data-stu-id="62da0-113">**PnP:** Plug and Play audit events are generated when removable storage, a printer, or Bluetooth media is connected.</span></span>

## <a name="monitor-device-control-security"></a><span data-ttu-id="62da0-114">Monitorar a segurança do controle de dispositivo</span><span class="sxs-lookup"><span data-stu-id="62da0-114">Monitor device control security</span></span>

<span data-ttu-id="62da0-115">O controle de dispositivo no Microsoft Defender para Ponto de Extremidade capacita os administradores de segurança com ferramentas que permitem controlar a segurança de controle de dispositivos da organização por meio de relatórios.</span><span class="sxs-lookup"><span data-stu-id="62da0-115">Device control in Microsoft Defender for Endpoint empowers security administrators with tools that enable them to track their organization’s device control security through reports.</span></span> <span data-ttu-id="62da0-116">Você pode encontrar o relatório de controle de dispositivo no centro Microsoft 365 segurança indo para **Relatórios > Proteção de dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="62da0-116">You can find the device control report in the Microsoft 365 security center by going to **Reports > Device protection**.</span></span>

<span data-ttu-id="62da0-117">O cartão de proteção de dispositivo no painel **Relatórios** mostra o número de eventos de auditoria gerados pelo tipo de mídia, nos últimos 180 dias.</span><span class="sxs-lookup"><span data-stu-id="62da0-117">The Device protection card on the **Reports** dashboard shows the number of audit events generated by media type, over the last 180 days.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="62da0-118">![DeviceControlReportCard](images/devicecontrolcard.png)</span><span class="sxs-lookup"><span data-stu-id="62da0-118">![DeviceControlReportCard](images/devicecontrolcard.png)</span></span>

<span data-ttu-id="62da0-119">O **botão Exibir detalhes** mostra mais dados de uso de mídia na página relatório de controle **do** dispositivo.</span><span class="sxs-lookup"><span data-stu-id="62da0-119">The **View details** button shows more media usage data in the **device control report** page.</span></span>

<span data-ttu-id="62da0-120">A página fornece um painel com o número agregado de eventos por tipo e uma lista de eventos.</span><span class="sxs-lookup"><span data-stu-id="62da0-120">The page provides a dashboard with aggregated number of events per type and a list of events.</span></span> <span data-ttu-id="62da0-121">Os administradores podem filtrar o intervalo de tempo, o nome da classe de mídia e a ID do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="62da0-121">Administrators can filter on time range, media class name, and device ID.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="62da0-122">![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)</span><span class="sxs-lookup"><span data-stu-id="62da0-122">![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)</span></span>

<span data-ttu-id="62da0-123">Quando você seleciona um evento, um flyout é exibido que mostra mais informações:</span><span class="sxs-lookup"><span data-stu-id="62da0-123">When you select an event, a flyout appears that shows you more information:</span></span>

- <span data-ttu-id="62da0-124">**Detalhes gerais:** Data, modo ação e a política deste evento.</span><span class="sxs-lookup"><span data-stu-id="62da0-124">**General details:** Date, Action mode, and the policy of this event.</span></span>
- <span data-ttu-id="62da0-125">**Informações de mídia:** As informações de mídia incluem nome de mídia, nome da classe, GUID de classe, ID do dispositivo, ID do fornecedor, volume, número de série e tipo de Barramento.</span><span class="sxs-lookup"><span data-stu-id="62da0-125">**Media information:** Media information includes Media name, Class name, Class GUID, Device ID, Vendor ID, Volume, Serial number, and Bus type.</span></span>
- <span data-ttu-id="62da0-126">**Detalhes do local:** Nome do dispositivo e MDATP ID do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="62da0-126">**Location details:** Device name and MDATP device ID.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="62da0-127">![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)</span><span class="sxs-lookup"><span data-stu-id="62da0-127">![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)</span></span>

<span data-ttu-id="62da0-128">Para ver a atividade em tempo real para essa mídia em toda a organização, selecione o **botão Abrir Busca Avançada.**</span><span class="sxs-lookup"><span data-stu-id="62da0-128">To see real-time activity for this media across the organization, select the **Open Advanced hunting** button.</span></span> <span data-ttu-id="62da0-129">Isso inclui uma consulta incorporada e pré-definida.</span><span class="sxs-lookup"><span data-stu-id="62da0-129">This includes an embedded, pre-defined query.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="62da0-130">![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)</span><span class="sxs-lookup"><span data-stu-id="62da0-130">![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)</span></span>

<span data-ttu-id="62da0-131">Para ver a segurança do dispositivo, selecione o botão Abrir página **do** dispositivo no sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="62da0-131">To see the security of the device, select the **Open device page** button on the flyout.</span></span> <span data-ttu-id="62da0-132">Este botão abre a página entidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="62da0-132">This button opens the device entity page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="62da0-133">![DeviceEntityPage](images/Devicesecuritypage.png)</span><span class="sxs-lookup"><span data-stu-id="62da0-133">![DeviceEntityPage](images/Devicesecuritypage.png)</span></span>

## <a name="reporting-delays"></a><span data-ttu-id="62da0-134">Atrasos de relatórios</span><span class="sxs-lookup"><span data-stu-id="62da0-134">Reporting delays</span></span>

<span data-ttu-id="62da0-135">O relatório de controle de dispositivo pode ter um atraso de 12 horas a partir do momento em que uma conexão de mídia ocorre até o momento em que o evento é refletido no cartão ou na lista de domínios.</span><span class="sxs-lookup"><span data-stu-id="62da0-135">The device control report can have a 12-hour delay from the time a media connection occurs to the time the event is reflected in the card or in the domain list.</span></span>
