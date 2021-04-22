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
ms.openlocfilehash: c58c81cd4623ec03850c167cad285e052413174c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933416"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="0f4df-104">Bloqueio comportamental do cliente</span><span class="sxs-lookup"><span data-stu-id="0f4df-104">Client behavioral blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0f4df-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="0f4df-105">**Applies to:**</span></span>
- [<span data-ttu-id="0f4df-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0f4df-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0f4df-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0f4df-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0f4df-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="0f4df-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0f4df-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="0f4df-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="0f4df-110">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="0f4df-110">Overview</span></span>

<span data-ttu-id="0f4df-111">O bloqueio comportamental do cliente é um componente dos recursos de [bloqueio comportamental e de contenção](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) no Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="0f4df-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in Defender for Endpoint.</span></span> <span data-ttu-id="0f4df-112">À medida que comportamentos suspeitos são detectados em dispositivos (também chamados de clientes ou pontos de extremidade), artefatos (como arquivos ou aplicativos) são bloqueados, verificados e remediados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0f4df-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Proteção de nuvem e cliente":::

<span data-ttu-id="0f4df-114">A proteção antivírus funciona melhor quando emparelhada com a proteção de nuvem.</span><span class="sxs-lookup"><span data-stu-id="0f4df-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="0f4df-115">Como funciona o bloqueio comportamental do cliente</span><span class="sxs-lookup"><span data-stu-id="0f4df-115">How client behavioral blocking works</span></span>

<span data-ttu-id="0f4df-116">[O Microsoft Defender Antivírus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) pode detectar comportamentos suspeitos, códigos mal-intencionados, ataques sem arquivo e na memória e muito mais em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0f4df-116">[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="0f4df-117">Quando comportamentos suspeitos são detectados, o Microsoft Defender Antivírus monitora e envia esses comportamentos suspeitos e suas árvores de processo para o serviço de proteção na nuvem.</span><span class="sxs-lookup"><span data-stu-id="0f4df-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="0f4df-118">O aprendizado de máquina diferencia entre aplicativos mal-intencionados e bons comportamentos em milissegundos e classifica cada artefato.</span><span class="sxs-lookup"><span data-stu-id="0f4df-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="0f4df-119">Em tempo quase real, assim que um artefato é considerado mal-intencionado, ele é bloqueado no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0f4df-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="0f4df-120">Sempre que um comportamento suspeito é detectado, um [alerta](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) é gerado e fica visível no Centro de Segurança do Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="0f4df-120">Whenever a suspicious behavior is detected, an [alert](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) is generated, and is visible in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="0f4df-121">O bloqueio comportamental do cliente é eficaz porque não só ajuda a impedir que um ataque seja iniciado, como também pode ajudar a parar um ataque que começou a ser executado.</span><span class="sxs-lookup"><span data-stu-id="0f4df-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="0f4df-122">E, com [o bloqueio de loop](feedback-loop-blocking.md) de feedback (outra funcionalidade de bloqueio comportamental e contenção), os ataques são impedidos em outros dispositivos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="0f4df-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="0f4df-123">Detecções baseadas em comportamento</span><span class="sxs-lookup"><span data-stu-id="0f4df-123">Behavior-based detections</span></span>

<span data-ttu-id="0f4df-124">As detecções baseadas em comportamento são nomeadas de acordo com o [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span><span class="sxs-lookup"><span data-stu-id="0f4df-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="0f4df-125">A convenção de nomeniste ajuda a identificar o estágio de ataque em que o comportamento mal-intencionado foi observado:</span><span class="sxs-lookup"><span data-stu-id="0f4df-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="0f4df-126">Tática</span><span class="sxs-lookup"><span data-stu-id="0f4df-126">Tactic</span></span> |   <span data-ttu-id="0f4df-127">Nome da ameaça de detecção</span><span class="sxs-lookup"><span data-stu-id="0f4df-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="0f4df-128">Acesso Inicial</span><span class="sxs-lookup"><span data-stu-id="0f4df-128">Initial Access</span></span> | <span data-ttu-id="0f4df-129">Behavior:Win32/InitialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0f4df-129">Behavior:Win32/InitialAccess.\*!ml</span></span> |
|<span data-ttu-id="0f4df-130">Execução</span><span class="sxs-lookup"><span data-stu-id="0f4df-130">Execution</span></span>  | <span data-ttu-id="0f4df-131">Behavior:Win32/Execution.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0f4df-131">Behavior:Win32/Execution.\*!ml</span></span> |
|<span data-ttu-id="0f4df-132">Persistência</span><span class="sxs-lookup"><span data-stu-id="0f4df-132">Persistence</span></span>    | <span data-ttu-id="0f4df-133">Behavior:Win32/Persistence.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0f4df-133">Behavior:Win32/Persistence.\*!ml</span></span> |
|<span data-ttu-id="0f4df-134">Escalonamento de privilégios</span><span class="sxs-lookup"><span data-stu-id="0f4df-134">Privilege Escalation</span></span>   | <span data-ttu-id="0f4df-135">Behavior:Win32/PrivilegeEscalation.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0f4df-135">Behavior:Win32/PrivilegeEscalation.\*!ml</span></span> |
|<span data-ttu-id="0f4df-136">Evasão de Defesa</span><span class="sxs-lookup"><span data-stu-id="0f4df-136">Defense Evasion</span></span>    | <span data-ttu-id="0f4df-137">Behavior:Win32/DefenseEvasion.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0f4df-137">Behavior:Win32/DefenseEvasion.\*!ml</span></span> |
|<span data-ttu-id="0f4df-138">Acesso de Credenciais</span><span class="sxs-lookup"><span data-stu-id="0f4df-138">Credential Access</span></span>  | <span data-ttu-id="0f4df-139">Behavior:Win32/CredentialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0f4df-139">Behavior:Win32/CredentialAccess.\*!ml</span></span> |
|<span data-ttu-id="0f4df-140">Descoberta</span><span class="sxs-lookup"><span data-stu-id="0f4df-140">Discovery</span></span>  | <span data-ttu-id="0f4df-141">Behavior:Win32/Discovery.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0f4df-141">Behavior:Win32/Discovery.\*!ml</span></span> |
|<span data-ttu-id="0f4df-142">Movimento Lateral</span><span class="sxs-lookup"><span data-stu-id="0f4df-142">Lateral Movement</span></span> | <span data-ttu-id="0f4df-143">Behavior:Win32/LateralMovement.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0f4df-143">Behavior:Win32/LateralMovement.\*!ml</span></span> |
|<span data-ttu-id="0f4df-144">Coleção</span><span class="sxs-lookup"><span data-stu-id="0f4df-144">Collection</span></span> |   <span data-ttu-id="0f4df-145">Behavior:Win32/Collection.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0f4df-145">Behavior:Win32/Collection.\*!ml</span></span> |
|<span data-ttu-id="0f4df-146">Comando e Controle</span><span class="sxs-lookup"><span data-stu-id="0f4df-146">Command and Control</span></span> | <span data-ttu-id="0f4df-147">Behavior:Win32/CommandAndControl.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0f4df-147">Behavior:Win32/CommandAndControl.\*!ml</span></span> |
|<span data-ttu-id="0f4df-148">Exfiltração</span><span class="sxs-lookup"><span data-stu-id="0f4df-148">Exfiltration</span></span>   | <span data-ttu-id="0f4df-149">Behavior:Win32/Exfiltration.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0f4df-149">Behavior:Win32/Exfiltration.\*!ml</span></span> |
|<span data-ttu-id="0f4df-150">Impacto</span><span class="sxs-lookup"><span data-stu-id="0f4df-150">Impact</span></span> | <span data-ttu-id="0f4df-151">Behavior:Win32/Impact.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0f4df-151">Behavior:Win32/Impact.\*!ml</span></span> |
|<span data-ttu-id="0f4df-152">Não categorizado</span><span class="sxs-lookup"><span data-stu-id="0f4df-152">Uncategorized</span></span>  | <span data-ttu-id="0f4df-153">Behavior:Win32/Generic.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0f4df-153">Behavior:Win32/Generic.\*!ml</span></span> |

> [!TIP]
> <span data-ttu-id="0f4df-154">Para saber mais sobre ameaças específicas, consulte **[atividade de ameaça global recente.](https://www.microsoft.com/wdsi/threats)**</span><span class="sxs-lookup"><span data-stu-id="0f4df-154">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="0f4df-155">Configurando o bloqueio comportamental do cliente</span><span class="sxs-lookup"><span data-stu-id="0f4df-155">Configuring client behavioral blocking</span></span>

<span data-ttu-id="0f4df-156">Se sua organização estiver usando o Defender para Ponto de Extremidade, o bloqueio comportamental do cliente será habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="0f4df-156">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="0f4df-157">No entanto, para se beneficiar de [](behavioral-blocking-containment.md)todos os recursos do Defender para Ponto de Extremidade, incluindo bloqueio comportamental e contenção, certifique-se de que os seguintes recursos e recursos do Defender para Ponto de Extremidade estão habilitados e configurados:</span><span class="sxs-lookup"><span data-stu-id="0f4df-157">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="0f4df-158">Linha de base do Defender para Pontos de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0f4df-158">Defender for Endpoint baselines</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="0f4df-159">Dispositivos a bordo do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0f4df-159">Devices onboarded to Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="0f4df-160">EDR em modo de bloco</span><span class="sxs-lookup"><span data-stu-id="0f4df-160">EDR in block mode</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="0f4df-161">Redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="0f4df-161">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="0f4df-162">[Proteção de última geração](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivírus)</span><span class="sxs-lookup"><span data-stu-id="0f4df-162">[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="0f4df-163">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="0f4df-163">Related articles</span></span>

- [<span data-ttu-id="0f4df-164">Bloqueio e contenção comportamental</span><span class="sxs-lookup"><span data-stu-id="0f4df-164">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="0f4df-165">Bloqueio do loop de comentários</span><span class="sxs-lookup"><span data-stu-id="0f4df-165">Feedback-loop blocking</span></span>](feedback-loop-blocking.md)

- [<span data-ttu-id="0f4df-166">(Blog) Bloqueio comportamental e contenção: transformar a ótica em proteção</span><span class="sxs-lookup"><span data-stu-id="0f4df-166">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="0f4df-167">Defender Útil para recursos do Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="0f4df-167">Helpful Defender for Endpoint resources</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
