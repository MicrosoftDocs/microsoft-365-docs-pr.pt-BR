---
title: Bloqueio comportamental do cliente
description: O bloqueio comportamental do cliente faz parte dos recursos de bloqueio comportamental e de contenção no Microsoft Defender para Ponto de Extremidade
keywords: bloqueio comportamental, proteção rápida, comportamento do cliente, Microsoft Defender para Ponto de Extremidade
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 83f269a13a54ee38b7e7a464d794d87ddbd7b520
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289926"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="b9401-104">Bloqueio comportamental do cliente</span><span class="sxs-lookup"><span data-stu-id="b9401-104">Client behavioral blocking</span></span>

<span data-ttu-id="b9401-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b9401-105">**Applies to:**</span></span>
- [<span data-ttu-id="b9401-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="b9401-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b9401-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9401-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b9401-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="b9401-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b9401-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="b9401-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="b9401-110">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="b9401-110">Overview</span></span>

<span data-ttu-id="b9401-111">O bloqueio comportamental do cliente é um componente dos recursos de [bloqueio comportamental e de contenção](behavioral-blocking-containment.md) no Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="b9401-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](behavioral-blocking-containment.md) in Defender for Endpoint.</span></span> <span data-ttu-id="b9401-112">À medida que comportamentos suspeitos são detectados em dispositivos (também chamados de clientes ou pontos de extremidade), artefatos (como arquivos ou aplicativos) são bloqueados, verificados e remediados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b9401-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Proteção de nuvem e cliente":::

<span data-ttu-id="b9401-114">A proteção antivírus funciona melhor quando emparelhada com a proteção de nuvem.</span><span class="sxs-lookup"><span data-stu-id="b9401-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="b9401-115">Como funciona o bloqueio comportamental do cliente</span><span class="sxs-lookup"><span data-stu-id="b9401-115">How client behavioral blocking works</span></span>

<span data-ttu-id="b9401-116">[Microsoft Defender Antivírus](microsoft-defender-antivirus-in-windows-10.md) pode detectar comportamento suspeito, código mal-intencionado, ataques sem arquivo e na memória e muito mais em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b9401-116">[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="b9401-117">Quando comportamentos suspeitos são detectados, Microsoft Defender Antivírus monitora e envia esses comportamentos suspeitos e suas árvores de processo para o serviço de proteção na nuvem.</span><span class="sxs-lookup"><span data-stu-id="b9401-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="b9401-118">O aprendizado de máquina diferencia entre aplicativos mal-intencionados e bons comportamentos em milissegundos e classifica cada artefato.</span><span class="sxs-lookup"><span data-stu-id="b9401-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="b9401-119">Em tempo quase real, assim que um artefato é considerado mal-intencionado, ele é bloqueado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b9401-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="b9401-120">Sempre que um comportamento suspeito [](alerts-queue.md) é detectado, um alerta é gerado e fica visível no [portal](microsoft-defender-security-center.md) de Microsoft 365 Defender (anteriormente o Central de Segurança do Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="b9401-120">Whenever a suspicious behavior is detected, an [alert](alerts-queue.md) is generated, and is visible in the [Microsoft 365 Defender portal](microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center).</span></span>

<span data-ttu-id="b9401-121">O bloqueio comportamental do cliente é eficaz porque não só ajuda a impedir que um ataque seja iniciado, como também pode ajudar a parar um ataque que começou a ser executado.</span><span class="sxs-lookup"><span data-stu-id="b9401-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="b9401-122">E, com [o bloqueio de loop](feedback-loop-blocking.md) de feedback (outra funcionalidade de bloqueio comportamental e contenção), os ataques são impedidos em outros dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b9401-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="b9401-123">Detecções baseadas em comportamento</span><span class="sxs-lookup"><span data-stu-id="b9401-123">Behavior-based detections</span></span>

<span data-ttu-id="b9401-124">As detecções baseadas em comportamento são nomeadas de acordo com o [MITRE ATT&CK Matrix para Enterprise](https://attack.mitre.org/matrices/enterprise).</span><span class="sxs-lookup"><span data-stu-id="b9401-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="b9401-125">A convenção de nomeniste ajuda a identificar o estágio de ataque em que o comportamento mal-intencionado foi observado:</span><span class="sxs-lookup"><span data-stu-id="b9401-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>

|<span data-ttu-id="b9401-126">Tática</span><span class="sxs-lookup"><span data-stu-id="b9401-126">Tactic</span></span> | <span data-ttu-id="b9401-127">Nome da ameaça de detecção</span><span class="sxs-lookup"><span data-stu-id="b9401-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="b9401-128">Acesso Inicial</span><span class="sxs-lookup"><span data-stu-id="b9401-128">Initial Access</span></span> | `Behavior:Win32/InitialAccess.*!ml` |
|<span data-ttu-id="b9401-129">Execução</span><span class="sxs-lookup"><span data-stu-id="b9401-129">Execution</span></span> | `Behavior:Win32/Execution.*!ml` |
|<span data-ttu-id="b9401-130">Persistência</span><span class="sxs-lookup"><span data-stu-id="b9401-130">Persistence</span></span> | `Behavior:Win32/Persistence.*!ml` |
|<span data-ttu-id="b9401-131">Escalonamento de privilégios</span><span class="sxs-lookup"><span data-stu-id="b9401-131">Privilege Escalation</span></span> | `Behavior:Win32/PrivilegeEscalation.*!ml` |
|<span data-ttu-id="b9401-132">Evasão de Defesa</span><span class="sxs-lookup"><span data-stu-id="b9401-132">Defense Evasion</span></span> | `Behavior:Win32/DefenseEvasion.*!ml` |
|<span data-ttu-id="b9401-133">Acesso de Credenciais</span><span class="sxs-lookup"><span data-stu-id="b9401-133">Credential Access</span></span> | `Behavior:Win32/CredentialAccess.*!ml` |
|<span data-ttu-id="b9401-134">Descoberta</span><span class="sxs-lookup"><span data-stu-id="b9401-134">Discovery</span></span> | `Behavior:Win32/Discovery.*!ml` |
|<span data-ttu-id="b9401-135">Movimento Lateral</span><span class="sxs-lookup"><span data-stu-id="b9401-135">Lateral Movement</span></span> | `Behavior:Win32/LateralMovement.*!ml` |
|<span data-ttu-id="b9401-136">Coleção</span><span class="sxs-lookup"><span data-stu-id="b9401-136">Collection</span></span> | `Behavior:Win32/Collection.*!ml` |
|<span data-ttu-id="b9401-137">Comando e Controle</span><span class="sxs-lookup"><span data-stu-id="b9401-137">Command and Control</span></span> | `Behavior:Win32/CommandAndControl.*!ml` |
|<span data-ttu-id="b9401-138">Exfiltração</span><span class="sxs-lookup"><span data-stu-id="b9401-138">Exfiltration</span></span> | `Behavior:Win32/Exfiltration.*!ml` |
|<span data-ttu-id="b9401-139">Impacto</span><span class="sxs-lookup"><span data-stu-id="b9401-139">Impact</span></span> | `Behavior:Win32/Impact.*!ml` |
|<span data-ttu-id="b9401-140">Não categorizado</span><span class="sxs-lookup"><span data-stu-id="b9401-140">Uncategorized</span></span> | `Behavior:Win32/Generic.*!ml` |

> [!TIP]
> <span data-ttu-id="b9401-141">Para saber mais sobre ameaças específicas, consulte **[atividade de ameaça global recente.](https://www.microsoft.com/wdsi/threats)**</span><span class="sxs-lookup"><span data-stu-id="b9401-141">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>

## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="b9401-142">Configurando o bloqueio comportamental do cliente</span><span class="sxs-lookup"><span data-stu-id="b9401-142">Configuring client behavioral blocking</span></span>

<span data-ttu-id="b9401-143">Se sua organização estiver usando o Defender para Ponto de Extremidade, o bloqueio comportamental do cliente será habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="b9401-143">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="b9401-144">No entanto, para se beneficiar de [](behavioral-blocking-containment.md)todos os recursos do Defender para Ponto de Extremidade, incluindo bloqueio comportamental e contenção, certifique-se de que os seguintes recursos e recursos do Defender para Ponto de Extremidade estão habilitados e configurados:</span><span class="sxs-lookup"><span data-stu-id="b9401-144">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="b9401-145">Linha de base do Defender para Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="b9401-145">Defender for Endpoint baselines</span></span>](configure-machines-security-baseline.md)

- [<span data-ttu-id="b9401-146">Dispositivos a bordo do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="b9401-146">Devices onboarded to Defender for Endpoint</span></span>](onboard-configure.md)

- [<span data-ttu-id="b9401-147">EDR em modo de bloco</span><span class="sxs-lookup"><span data-stu-id="b9401-147">EDR in block mode</span></span>](edr-in-block-mode.md)

- [<span data-ttu-id="b9401-148">Redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="b9401-148">Attack surface reduction</span></span>](attack-surface-reduction.md)

- <span data-ttu-id="b9401-149">[Proteção de última geração](configure-microsoft-defender-antivirus-features.md) (antivírus, antimalware e outros recursos de proteção contra ameaças)</span><span class="sxs-lookup"><span data-stu-id="b9401-149">[Next-generation protection](configure-microsoft-defender-antivirus-features.md) (antivirus, antimalware, and other threat protection capabilities)</span></span>
