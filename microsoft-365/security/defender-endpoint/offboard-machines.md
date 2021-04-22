---
title: Dispositivos offboard do serviço Microsoft Defender para Ponto de Extremidade
description: Onboard Windows 10 devices, servers, non-Windows devices from the Microsoft Defender for Endpoint service
keywords: offboarding, Microsoft Defender for Endpoint offboarding, offboarding
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 425e5b9e0be12b89c8fd3b7201010b0f776cc6a5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934148"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a><span data-ttu-id="4d834-104">Dispositivos offboard do serviço Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4d834-104">Offboard devices from the Microsoft Defender for Endpoint service</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4d834-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4d834-105">**Applies to:**</span></span>
- [<span data-ttu-id="4d834-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4d834-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4d834-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4d834-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="4d834-108">**Plataformas**</span><span class="sxs-lookup"><span data-stu-id="4d834-108">**Platforms**</span></span>
- <span data-ttu-id="4d834-109">macOS</span><span class="sxs-lookup"><span data-stu-id="4d834-109">macOS</span></span>
- <span data-ttu-id="4d834-110">Linux</span><span class="sxs-lookup"><span data-stu-id="4d834-110">Linux</span></span>
- <span data-ttu-id="4d834-111">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="4d834-111">Windows Server 2012 R2</span></span>
- <span data-ttu-id="4d834-112">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="4d834-112">Windows Server 2016</span></span>

><span data-ttu-id="4d834-113">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="4d834-113">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4d834-114">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="4d834-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

<span data-ttu-id="4d834-115">Siga as instruções correspondentes, dependendo do método de implantação preferencial.</span><span class="sxs-lookup"><span data-stu-id="4d834-115">Follow the corresponding instructions depending on your preferred deployment method.</span></span>

>[!NOTE]
> <span data-ttu-id="4d834-116">O status de um dispositivo será alternado para [Inativo](fix-unhealthy-sensors.md#inactive-devices) 7 dias após o offboard.</span><span class="sxs-lookup"><span data-stu-id="4d834-116">The status of a device will be switched to [Inactive](fix-unhealthy-sensors.md#inactive-devices) 7 days after offboarding.</span></span> <br> <span data-ttu-id="4d834-117">Os dados dos dispositivos de fora (como Linha do Tempo, Alertas, Vulnerabilidades etc.) permanecerão no portal até que o período de retenção configurado [expire.](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy)</span><span class="sxs-lookup"><span data-stu-id="4d834-117">Offboarded devices' data (such as Timeline, Alerts, Vulnerabilities, etc.) will remain in the portal until the configured [retention period](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) expires.</span></span> <br>
> <span data-ttu-id="4d834-118">O perfil do dispositivo (sem dados) [](machines-view-overview.md) permanecerá na Lista de Dispositivos por não mais de 180 dias.</span><span class="sxs-lookup"><span data-stu-id="4d834-118">The device's profile (without data) will remain in the [Devices List](machines-view-overview.md) for no longer than 180 days.</span></span>
> <span data-ttu-id="4d834-119">Além disso, os dispositivos que não estão ativos nos últimos 30 dias não são fatorados [](tvm-exposure-score.md) nos dados que refletem a pontuação de exposição a ameaças e vulnerabilidades da sua organização e a Pontuação Segura da Microsoft para Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4d834-119">In addition, devices that are not active in the last 30 days are not factored in on the data that reflects your organization's threat and vulnerability management [exposure score](tvm-exposure-score.md) and Microsoft Secure Score for Devices.</span></span> <br>
> <span data-ttu-id="4d834-120">Para exibir somente dispositivos ativos, você pode filtrar por estado de [saúde,](machines-view-overview.md#health-state)marcas [de dispositivo](machine-tags.md) ou grupos [de máquinas.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="4d834-120">To view only active devices, you can filter by [health state](machines-view-overview.md#health-state), [device tags](machine-tags.md) or [machine groups](machine-groups.md).</span></span> 

## <a name="offboard-windows-10-devices"></a><span data-ttu-id="4d834-121">Offboard dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="4d834-121">Offboard Windows 10 devices</span></span>
- [<span data-ttu-id="4d834-122">Dispositivos offboard usando um script local</span><span class="sxs-lookup"><span data-stu-id="4d834-122">Offboard devices using a local script</span></span>](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [<span data-ttu-id="4d834-123">Dispositivos offboard usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="4d834-123">Offboard devices using Group Policy</span></span>](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [<span data-ttu-id="4d834-124">Dispositivos offboard usando ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="4d834-124">Offboard devices using Mobile Device Management tools</span></span>](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a><span data-ttu-id="4d834-125">Servidores offboard</span><span class="sxs-lookup"><span data-stu-id="4d834-125">Offboard Servers</span></span>
- [<span data-ttu-id="4d834-126">Servidores offboard</span><span class="sxs-lookup"><span data-stu-id="4d834-126">Offboard servers</span></span>](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="4d834-127">Offboard de dispositivos que não são windows</span><span class="sxs-lookup"><span data-stu-id="4d834-127">Offboard non-Windows devices</span></span>
- [<span data-ttu-id="4d834-128">Offboard de dispositivos que não são windows</span><span class="sxs-lookup"><span data-stu-id="4d834-128">Offboard non-Windows devices</span></span>](configure-endpoints-non-windows.md#offboard-non-windows-devices)

