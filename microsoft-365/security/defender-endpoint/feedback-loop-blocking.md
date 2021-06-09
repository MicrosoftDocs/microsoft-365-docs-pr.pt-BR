---
title: Bloqueio do loop de comentários
description: O bloqueio de loop de feedback, também chamado de proteção rápida, faz parte dos recursos de bloqueio comportamental e de contenção no Microsoft Defender para Ponto de Extremidade
keywords: bloqueio comportamental, proteção rápida, bloqueio de comentários, Microsoft Defender para Ponto de Extremidade
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: 7319ff5a89a20529eed7d36aa0d0b1522013abd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842453"
---
# <a name="feedback-loop-blocking"></a><span data-ttu-id="a3130-104">Bloqueio do loop de comentários</span><span class="sxs-lookup"><span data-stu-id="a3130-104">Feedback-loop blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="a3130-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="a3130-105">**Applies to:**</span></span>
- [<span data-ttu-id="a3130-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="a3130-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a><span data-ttu-id="a3130-107">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="a3130-107">Overview</span></span>

<span data-ttu-id="a3130-108">O bloqueio de loop de feedback, também conhecido [](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) como proteção rápida, é um componente dos recursos de bloqueio e contenção comportamental no Microsoft Defender para Ponto de [Extremidade.](/windows/security/threat-protection/)</span><span class="sxs-lookup"><span data-stu-id="a3130-108">Feedback-loop blocking, also referred to as rapid protection, is a component of [behavioral blocking and containment capabilities](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in [Microsoft Defender for Endpoint](/windows/security/threat-protection/).</span></span> <span data-ttu-id="a3130-109">Com o bloqueio de loop de feedback, os dispositivos em toda a sua organização são mais protegidos contra ataques.</span><span class="sxs-lookup"><span data-stu-id="a3130-109">With feedback-loop blocking, devices across your organization are better protected from attacks.</span></span> 

## <a name="how-feedback-loop-blocking-works"></a><span data-ttu-id="a3130-110">Como funciona o bloqueio de loop de feedback</span><span class="sxs-lookup"><span data-stu-id="a3130-110">How feedback-loop blocking works</span></span>

<span data-ttu-id="a3130-111">Quando um comportamento ou arquivo suspeito é detectado, como por Microsoft Defender Antivírus [,](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)as informações sobre esse artefato são enviadas a vários classificadores.</span><span class="sxs-lookup"><span data-stu-id="a3130-111">When a suspicious behavior or file is detected, such as by [Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10), information about that artifact is sent to multiple classifiers.</span></span> <span data-ttu-id="a3130-112">O mecanismo de loop de proteção rápida inspeciona e correlaciona as informações com outros sinais para chegar a uma decisão sobre se deve bloquear um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a3130-112">The rapid protection loop engine inspects and correlates the information with other signals to arrive at a decision as to whether to block a file.</span></span> <span data-ttu-id="a3130-113">A verificação e a classificação de artefatos ocorrem rapidamente.</span><span class="sxs-lookup"><span data-stu-id="a3130-113">Checking and classifying artifacts happens quickly.</span></span> <span data-ttu-id="a3130-114">Isso resulta no bloqueio rápido do malware confirmado e gera proteção em todo o ecossistema.</span><span class="sxs-lookup"><span data-stu-id="a3130-114">It results in rapid blocking of confirmed malware, and drives protection across the entire ecosystem.</span></span> 

<span data-ttu-id="a3130-115">Com a proteção rápida no local, um ataque pode ser interrompido em um dispositivo, em outros dispositivos na organização e em dispositivos em outras organizações, como uma tentativa de ataque para ampliar sua posição.</span><span class="sxs-lookup"><span data-stu-id="a3130-115">With rapid protection in place, an attack can be stopped on a device, other devices in the organization, and devices in other organizations, as an attack attempts to broaden its foothold.</span></span>


## <a name="configuring-feedback-loop-blocking"></a><span data-ttu-id="a3130-116">Configurando o bloqueio de loop de feedback</span><span class="sxs-lookup"><span data-stu-id="a3130-116">Configuring feedback-loop blocking</span></span>

<span data-ttu-id="a3130-117">Se sua organização estiver usando o Defender para Ponto de Extremidade, o bloqueio de loop de feedback será habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="a3130-117">If your organization is using Defender for Endpoint, feedback-loop blocking is enabled by default.</span></span> <span data-ttu-id="a3130-118">No entanto, a proteção rápida ocorre por meio de uma combinação de recursos do Defender para Ponto de Extremidade, recursos de proteção de aprendizado de máquina e compartilhamento de sinal nos serviços de segurança da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a3130-118">However, rapid protection occurs through a combination of Defender for Endpoint capabilities, machine learning protection features, and signal-sharing across Microsoft security services.</span></span> <span data-ttu-id="a3130-119">Certifique-se de que os seguintes recursos e recursos do Defender para Ponto de Extremidade estão habilitados e configurados:</span><span class="sxs-lookup"><span data-stu-id="a3130-119">Make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="a3130-120">Linha de base do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="a3130-120">Microsoft Defender for Endpoint baselines</span></span>](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="a3130-121">Dispositivos a bordo do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="a3130-121">Devices onboarded to Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="a3130-122">EDR em modo de bloco</span><span class="sxs-lookup"><span data-stu-id="a3130-122">EDR in block mode</span></span>](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="a3130-123">Redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="a3130-123">Attack surface reduction</span></span>](/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="a3130-124">[Proteção de última geração](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivírus)</span><span class="sxs-lookup"><span data-stu-id="a3130-124">[Next-generation protection](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="a3130-125">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="a3130-125">Related articles</span></span>

- [<span data-ttu-id="a3130-126">Bloqueio e contenção comportamental</span><span class="sxs-lookup"><span data-stu-id="a3130-126">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="a3130-127">(Blog) Bloqueio comportamental e contenção: transformar a ótica em proteção</span><span class="sxs-lookup"><span data-stu-id="a3130-127">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="a3130-128">Microsoft Defender útil para recursos de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="a3130-128">Helpful Microsoft Defender for Endpoint resources</span></span>](/microsoft-365/security/defender-endpoint/helpful-resources)
