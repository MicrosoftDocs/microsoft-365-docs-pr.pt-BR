---
title: Proteger sua organização contra ameaças da Web
description: Saiba mais sobre a proteção da Web no Microsoft Defender ATP e como ela pode proteger sua organização.
keywords: proteção da Web, proteção contra ameaças da Web, navegação na Web, segurança, phishing, malware, exploração, sites, proteção de rede, Edge, Internet Explorer, Chrome, Firefox, navegador da Web
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7754fa586b24fdedaa9691b45f5da4654c882a5b
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185976"
---
# <a name="protect-your-organization-against-web-threats"></a><span data-ttu-id="04122-104">Proteger sua organização contra ameaças da Web</span><span class="sxs-lookup"><span data-stu-id="04122-104">Protect your organization against web threats</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="04122-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="04122-105">**Applies to:**</span></span>
- [<span data-ttu-id="04122-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="04122-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="04122-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04122-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="04122-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="04122-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="04122-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="04122-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

<span data-ttu-id="04122-110">A proteção contra ameaças da Web faz parte da [proteção da Web](web-protection-overview.md) no Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="04122-110">Web threat protection is part of [Web protection](web-protection-overview.md) in Defender for Endpoint.</span></span> <span data-ttu-id="04122-111">Ele usa [a proteção de rede](network-protection.md) para proteger seus dispositivos contra ameaças da Web.</span><span class="sxs-lookup"><span data-stu-id="04122-111">It uses [network protection](network-protection.md) to secure your devices against web threats.</span></span> <span data-ttu-id="04122-112">Ao integrar-se ao Microsoft Edge e aos navegadores populares de terceiros, como o Chrome e o Firefox, a proteção contra ameaças da Web interrompe as ameaças da Web sem um proxy da Web e pode proteger dispositivos enquanto eles estão fora ou no local.</span><span class="sxs-lookup"><span data-stu-id="04122-112">By integrating with Microsoft Edge and popular third-party browsers like Chrome and Firefox, web threat protection stops web threats without a web proxy and can protect devices while they are away or on premises.</span></span> <span data-ttu-id="04122-113">A proteção contra ameaças da Web interrompe o acesso a sites de phishing, vetores de malware, sites de exploração, sites não falsos ou de baixa reputação, bem como sites bloqueados em sua lista de indicadores [personalizados.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="04122-113">Web threat protection stops access to phishing sites, malware vectors, exploit sites, untrusted or low-reputation sites, as well as sites that you have blocked in your [custom indicator list](manage-indicators.md).</span></span>

>[!Note]
><span data-ttu-id="04122-114">Pode levar até uma hora para que os dispositivos recebam novos indicadores de cliente.</span><span class="sxs-lookup"><span data-stu-id="04122-114">It can take up to an hour for devices to receive new customer indicators.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="04122-115">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="04122-115">Prerequisites</span></span>
<span data-ttu-id="04122-116">A proteção da Web usa a proteção de rede para fornecer segurança de navegação na Web no Microsoft Edge e em navegadores da Web de terceiros.</span><span class="sxs-lookup"><span data-stu-id="04122-116">Web protection uses network protection to provide web browsing security on Microsoft Edge and third-party web browsers.</span></span>

<span data-ttu-id="04122-117">Para ativar a proteção de rede em seus dispositivos:</span><span class="sxs-lookup"><span data-stu-id="04122-117">To turn on network protection on your devices:</span></span>
- <span data-ttu-id="04122-118">Edite a linha de base de segurança do Defender para Ponto de Extremidade em Proteção de Rede **& Web** para habilitar a proteção de rede antes de implantá-la ou reimplantá-la.</span><span class="sxs-lookup"><span data-stu-id="04122-118">Edit the Defender for Endpoint security baseline under **Web & Network Protection** to enable network protection before deploying or redeploying it.</span></span> [<span data-ttu-id="04122-119">Saiba mais sobre como revisar e atribuir a linha de base de segurança do Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="04122-119">Learn about reviewing and assigning the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- <span data-ttu-id="04122-120">Adeque a proteção de rede usando a configuração de dispositivo do Intune, SCCM, Política de Grupo ou sua solução MDM.</span><span class="sxs-lookup"><span data-stu-id="04122-120">Turn network protection on using Intune device configuration, SCCM, Group Policy, or your MDM solution.</span></span> [<span data-ttu-id="04122-121">Leia mais sobre a habilitação da proteção de rede</span><span class="sxs-lookup"><span data-stu-id="04122-121">Read more about enabling network protection</span></span>](enable-network-protection.md)  

>[!Note]
><span data-ttu-id="04122-122">Se você definir a proteção de rede como **Somente Auditoria,** o bloqueio ficará indisponível.</span><span class="sxs-lookup"><span data-stu-id="04122-122">If you set network protection to **Audit only**, blocking will be unavailable.</span></span> <span data-ttu-id="04122-123">Além disso, você poderá detectar e registrar tentativas de log para acessar sites mal-intencionados e indesejados apenas no Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="04122-123">Also, you will be able to detect and log attempts to access malicious and unwanted websites on Microsoft Edge only.</span></span>

## <a name="related-topics"></a><span data-ttu-id="04122-124">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="04122-124">Related topics</span></span>

- [<span data-ttu-id="04122-125">Visão geral da proteção da Web</span><span class="sxs-lookup"><span data-stu-id="04122-125">Web protection overview</span></span>](web-protection-overview.md)
- [<span data-ttu-id="04122-126">Proteção contra ameaças da Web</span><span class="sxs-lookup"><span data-stu-id="04122-126">Web threat protection</span></span>](web-threat-protection.md)
- [<span data-ttu-id="04122-127">Monitorar a segurança da Web</span><span class="sxs-lookup"><span data-stu-id="04122-127">Monitor web security</span></span>](web-protection-monitoring.md)
- [<span data-ttu-id="04122-128">Responder a ameaças da Web</span><span class="sxs-lookup"><span data-stu-id="04122-128">Respond to web threats</span></span>](web-protection-response.md)
- [<span data-ttu-id="04122-129">Proteção de rede</span><span class="sxs-lookup"><span data-stu-id="04122-129">Network protection</span></span>](network-protection.md)
