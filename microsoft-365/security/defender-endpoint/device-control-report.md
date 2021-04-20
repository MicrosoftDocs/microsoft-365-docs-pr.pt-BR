---
title: Proteger dados da sua organização com controle de dispositivo
description: Monitore a segurança de dados da sua organização por meio de relatórios de controle de dispositivo.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: dansimp
author: dansimp
ms.reviewer: dansimp
ms.topic: article
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: ee8e7be20076bde41867981008e53a70c134e47e
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893659"
---
# <a name="protect-your-organizations-data-with-device-control"></a><span data-ttu-id="0f48b-103">Proteger dados da sua organização com controle de dispositivo</span><span class="sxs-lookup"><span data-stu-id="0f48b-103">Protect your organization’s data with device control</span></span>

<span data-ttu-id="0f48b-104">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span><span class="sxs-lookup"><span data-stu-id="0f48b-104">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)</span></span>

<span data-ttu-id="0f48b-105">O controle de dispositivo do Microsoft Defender for Endpoint protege contra perda de dados, monitorando e controlando o uso de mídia por dispositivos em sua organização, como o uso de dispositivos de armazenamento removíveis e unidades USB.</span><span class="sxs-lookup"><span data-stu-id="0f48b-105">Microsoft Defender for Endpoint device control protects against data loss, by monitoring and controlling media use by devices in your organization, such as the use of removable storage devices and USB drives.</span></span>

<span data-ttu-id="0f48b-106">Com o relatório de controle de dispositivo, você pode exibir eventos relacionados ao uso de mídia, como:</span><span class="sxs-lookup"><span data-stu-id="0f48b-106">With the device control report, you can view events that relate to media usage, such as:</span></span>

- <span data-ttu-id="0f48b-107">**Eventos de auditoria:** Mostra o número de eventos de auditoria que ocorrem quando a mídia externa está conectada.</span><span class="sxs-lookup"><span data-stu-id="0f48b-107">**Audit events:** Shows the number of audit events that occur when external media is connected.</span></span>
- <span data-ttu-id="0f48b-108">**Eventos de política:** Mostra o número de eventos de política que ocorrem quando uma política de controle de dispositivo é disparada.</span><span class="sxs-lookup"><span data-stu-id="0f48b-108">**Policy events:** Shows the number of policy events that occur when a device control policy is triggered.</span></span>

> [!NOTE]
> <span data-ttu-id="0f48b-109">O evento de auditoria para controlar o uso de mídia é habilitado por padrão para dispositivos conectados ao Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="0f48b-109">The audit event to track media usage is enabled by default for devices onboarded to Microsoft Defender for Endpoint.</span></span>

## <a name="understanding-the-audit-events"></a><span data-ttu-id="0f48b-110">Noções básicas sobre os eventos de auditoria</span><span class="sxs-lookup"><span data-stu-id="0f48b-110">Understanding the audit events</span></span>

<span data-ttu-id="0f48b-111">Os eventos de auditoria incluem:</span><span class="sxs-lookup"><span data-stu-id="0f48b-111">The audit events include:</span></span>

- <span data-ttu-id="0f48b-112">**Montagem e desmontagem da** unidade USB: Eventos de auditoria gerados quando uma unidade USB é montada ou desmontada.</span><span class="sxs-lookup"><span data-stu-id="0f48b-112">**USB drive mount and unmount:** Audit events that are generated when a USB drive is mounted or unmounted.</span></span>
- <span data-ttu-id="0f48b-113">**PnP:** Os eventos de auditoria Plug and Play são gerados quando o armazenamento removível, uma impressora ou Bluetooth mídia está conectada.</span><span class="sxs-lookup"><span data-stu-id="0f48b-113">**PnP:** Plug and Play audit events are generated when removable storage, a printer, or Bluetooth media is connected.</span></span>

## <a name="monitor-device-control-security"></a><span data-ttu-id="0f48b-114">Monitorar a segurança do controle de dispositivo</span><span class="sxs-lookup"><span data-stu-id="0f48b-114">Monitor device control security</span></span>

<span data-ttu-id="0f48b-115">O controle de dispositivo no Microsoft Defender para Ponto de Extremidade capacita os administradores de segurança com ferramentas que permitem controlar a segurança de controle de dispositivos da organização por meio de relatórios.</span><span class="sxs-lookup"><span data-stu-id="0f48b-115">Device control in Microsoft Defender for Endpoint empowers security administrators with tools that enable them to track their organization’s device control security through reports.</span></span> <span data-ttu-id="0f48b-116">Você pode encontrar o relatório de controle de dispositivo no centro de segurança do Microsoft 365 indo para **Relatórios > Proteção de dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="0f48b-116">You can find the device control report in the Microsoft 365 security center by going to **Reports > Device protection**.</span></span>

<span data-ttu-id="0f48b-117">O cartão de proteção de dispositivo no painel **Relatórios** mostra o número de eventos de auditoria gerados pelo tipo de mídia, nos últimos 180 dias.</span><span class="sxs-lookup"><span data-stu-id="0f48b-117">The Device protection card on the **Reports** dashboard shows the number of audit events generated by media type, over the last 180 days.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0f48b-118">![DeviceControlReportCard](images/devicecontrolcard.png)</span><span class="sxs-lookup"><span data-stu-id="0f48b-118">![DeviceControlReportCard](images/devicecontrolcard.png)</span></span>

<span data-ttu-id="0f48b-119">O **botão Exibir detalhes** mostra mais dados de uso de mídia na página relatório de controle **do** dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0f48b-119">The **View details** button shows more media usage data in the **device control report** page.</span></span>

<span data-ttu-id="0f48b-120">A página fornece um painel com o número agregado de eventos por tipo e uma lista de eventos.</span><span class="sxs-lookup"><span data-stu-id="0f48b-120">The page provides a dashboard with aggregated number of events per type and a list of events.</span></span> <span data-ttu-id="0f48b-121">Os administradores podem filtrar o intervalo de tempo, o nome da classe de mídia e a ID do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0f48b-121">Administrators can filter on time range, media class name, and device ID.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0f48b-122">![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)</span><span class="sxs-lookup"><span data-stu-id="0f48b-122">![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)</span></span>

<span data-ttu-id="0f48b-123">Quando você seleciona um evento, um flyout é exibido que mostra mais informações:</span><span class="sxs-lookup"><span data-stu-id="0f48b-123">When you select an event, a flyout appears that shows you more information:</span></span>

- <span data-ttu-id="0f48b-124">**Detalhes gerais:** Data, modo ação e a política deste evento.</span><span class="sxs-lookup"><span data-stu-id="0f48b-124">**General details:** Date, Action mode, and the policy of this event.</span></span>
- <span data-ttu-id="0f48b-125">**Informações de mídia:** As informações de mídia incluem nome de mídia, nome da classe, GUID de classe, ID do dispositivo, ID do fornecedor, volume, número de série e tipo de Barramento.</span><span class="sxs-lookup"><span data-stu-id="0f48b-125">**Media information:** Media information includes Media name, Class name, Class GUID, Device ID, Vendor ID, Volume, Serial number, and Bus type.</span></span>
- <span data-ttu-id="0f48b-126">**Detalhes do local:** Nome do dispositivo e ID do dispositivo MDATP.</span><span class="sxs-lookup"><span data-stu-id="0f48b-126">**Location details:** Device name and MDATP device ID.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0f48b-127">![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)</span><span class="sxs-lookup"><span data-stu-id="0f48b-127">![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)</span></span>

<span data-ttu-id="0f48b-128">Para ver a atividade em tempo real para essa mídia em toda a organização, selecione o **botão Abrir Busca Avançada.**</span><span class="sxs-lookup"><span data-stu-id="0f48b-128">To see real-time activity for this media across the organization, select the **Open Advanced hunting** button.</span></span> <span data-ttu-id="0f48b-129">Isso inclui uma consulta incorporada e pré-definida.</span><span class="sxs-lookup"><span data-stu-id="0f48b-129">This includes an embedded, pre-defined query.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0f48b-130">![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)</span><span class="sxs-lookup"><span data-stu-id="0f48b-130">![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)</span></span>

<span data-ttu-id="0f48b-131">Para ver a segurança do dispositivo, selecione o botão Abrir página **do** dispositivo no sobrevoo.</span><span class="sxs-lookup"><span data-stu-id="0f48b-131">To see the security of the device, select the **Open device page** button on the flyout.</span></span> <span data-ttu-id="0f48b-132">Este botão abre a página entidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0f48b-132">This button opens the device entity page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0f48b-133">![DeviceEntityPage](images/Devicesecuritypage.png)</span><span class="sxs-lookup"><span data-stu-id="0f48b-133">![DeviceEntityPage](images/Devicesecuritypage.png)</span></span>

## <a name="reporting-delays"></a><span data-ttu-id="0f48b-134">Atrasos de relatórios</span><span class="sxs-lookup"><span data-stu-id="0f48b-134">Reporting delays</span></span>

<span data-ttu-id="0f48b-135">O relatório de controle de dispositivo pode ter um atraso de 12 horas a partir do momento em que uma conexão de mídia ocorre até o momento em que o evento é refletido no cartão ou na lista de domínios.</span><span class="sxs-lookup"><span data-stu-id="0f48b-135">The device control report can have a 12-hour delay from the time a media connection occurs to the time the event is reflected in the card or in the domain list.</span></span>
