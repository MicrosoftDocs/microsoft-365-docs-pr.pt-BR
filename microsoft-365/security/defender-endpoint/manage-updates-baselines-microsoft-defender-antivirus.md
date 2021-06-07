---
title: Gerenciar Microsoft Defender Antivírus e aplicar linhas de base
description: Gerenciar como Microsoft Defender Antivírus recebe atualizações de produtos e proteção.
keywords: atualizações, linhas de base de segurança, proteção, agendar atualizações, forçar atualizações, atualizações móveis, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 06/04/2021
ms.openlocfilehash: a1b7891e9e397e7345eb73a94d6298a9da781d98
ms.sourcegitcommit: bce733c1152dfbca782e716579074261e3c2ef65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52795977"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="354c2-104">Gerenciar Microsoft Defender Antivírus e aplicar linhas de base</span><span class="sxs-lookup"><span data-stu-id="354c2-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="354c2-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="354c2-105">**Applies to:**</span></span>

- [<span data-ttu-id="354c2-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="354c2-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="354c2-107">Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="354c2-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="354c2-108">Há dois tipos de atualizações relacionadas à Microsoft Defender Antivírus atualizadas:</span><span class="sxs-lookup"><span data-stu-id="354c2-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="354c2-109">Atualizações de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="354c2-109">Security intelligence updates</span></span>
- <span data-ttu-id="354c2-110">Atualizações de produtos</span><span class="sxs-lookup"><span data-stu-id="354c2-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="354c2-111">Manter Microsoft Defender Antivírus atualizado é fundamental para garantir que seus dispositivos tenham a tecnologia e os recursos mais recentes necessários para proteger contra novas técnicas de malware e ataque.</span><span class="sxs-lookup"><span data-stu-id="354c2-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="354c2-112">Certifique-se de atualizar sua proteção antivírus mesmo que Microsoft Defender Antivírus está sendo executado no [modo passivo](./microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="354c2-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="354c2-113">Para ver o mecanismo, a plataforma e a data de assinatura mais atuais, visite as atualizações de inteligência de segurança para Microsoft Defender Antivírus e outros [antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="354c2-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="354c2-114">Atualizações de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="354c2-114">Security intelligence updates</span></span>

<span data-ttu-id="354c2-115">Microsoft Defender Antivírus usa [proteção](cloud-protection-microsoft-defender-antivirus.md) entregue na nuvem (também chamada de Serviço de Proteção Avançada da Microsoft ou MAPS) e baixa periodicamente atualizações de inteligência de segurança para fornecer proteção.</span><span class="sxs-lookup"><span data-stu-id="354c2-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="354c2-116">As atualizações são lançadas nos números KB abaixo:</span><span class="sxs-lookup"><span data-stu-id="354c2-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="354c2-117">Microsoft Defender Antivírus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="354c2-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="354c2-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="354c2-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="354c2-119">A proteção entregue na nuvem está sempre ativa e requer uma conexão ativa com a Internet para funcionar.</span><span class="sxs-lookup"><span data-stu-id="354c2-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="354c2-120">As atualizações de inteligência de segurança ocorrem em uma cadência agendada (configurável por meio da política).</span><span class="sxs-lookup"><span data-stu-id="354c2-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="354c2-121">Para obter mais informações, [consulte Use Microsoft cloud-provided protection in Microsoft Defender Antivírus](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="354c2-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="354c2-122">Para ver uma lista de atualizações recentes de inteligência de segurança, consulte Atualizações de inteligência de segurança para Microsoft Defender Antivírus [e outros antimalware da Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="354c2-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="354c2-123">As atualizações do mecanismo são incluídas com atualizações de inteligência de segurança e são lançadas em uma cadência mensal.</span><span class="sxs-lookup"><span data-stu-id="354c2-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="354c2-124">Atualizações de produtos</span><span class="sxs-lookup"><span data-stu-id="354c2-124">Product updates</span></span>

<span data-ttu-id="354c2-125">Microsoft Defender Antivírus exige atualizações mensais [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) *(conhecidas* como atualizações de plataforma) e receberá atualizações de recursos principais juntamente com Windows 10 versões.</span><span class="sxs-lookup"><span data-stu-id="354c2-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="354c2-126">Você pode gerenciar a distribuição de atualizações por meio de um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="354c2-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="354c2-127">Windows Serviço de Atualização do Servidor (WSUS)</span><span class="sxs-lookup"><span data-stu-id="354c2-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="354c2-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="354c2-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="354c2-129">O método comum que você usa para implantar a Microsoft e Windows atualizações para pontos de extremidade em sua rede.</span><span class="sxs-lookup"><span data-stu-id="354c2-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="354c2-130">Para obter mais informações, consulte [Manage the sources for Microsoft Defender Antivírus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="354c2-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="354c2-131">As atualizações mensais são lançadas em fases, resultando em vários pacotes visíveis em seus [Serviços de Atualização do Servidor de Janelas.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="354c2-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="354c2-132">Versões mensais de plataforma e mecanismo</span><span class="sxs-lookup"><span data-stu-id="354c2-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="354c2-133">Para obter informações sobre como atualizar ou instalar a atualização da plataforma, consulte [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="354c2-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="354c2-134">Todas as nossas atualizações contêm</span><span class="sxs-lookup"><span data-stu-id="354c2-134">All our updates contain</span></span> 
- <span data-ttu-id="354c2-135">melhorias de desempenho;</span><span class="sxs-lookup"><span data-stu-id="354c2-135">performance improvements;</span></span>
- <span data-ttu-id="354c2-136">melhorias de capacidade de serviço; e</span><span class="sxs-lookup"><span data-stu-id="354c2-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="354c2-137">melhorias de integração (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span><span class="sxs-lookup"><span data-stu-id="354c2-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="354c2-138">Maio-2021 (plataforma: 4.18.2105.4 | Mecanismo: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="354c2-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="354c2-139">&ensp;Versão de atualização de inteligência de segurança: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="354c2-140">&ensp;Lançado: **4 de junho de 2021**</span><span class="sxs-lookup"><span data-stu-id="354c2-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="354c2-141">&ensp;Plataforma: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="354c2-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="354c2-142">&ensp;Mecanismo: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="354c2-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="354c2-143">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="354c2-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="354c2-144">Novidades</span><span class="sxs-lookup"><span data-stu-id="354c2-144">What's new</span></span>
- <span data-ttu-id="354c2-145">Melhorias [no monitoramento de comportamento](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="354c2-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="354c2-146">Recurso [de filtragem de notificação](network-protection.md) de proteção de rede fixa</span><span class="sxs-lookup"><span data-stu-id="354c2-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="354c2-147">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="354c2-147">Known Issues</span></span>
<span data-ttu-id="354c2-148">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="354c2-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="354c2-149">Abril-2021 (Plataforma: 4.18.2104.14 | Mecanismo: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="354c2-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="354c2-150">&ensp;Versão de atualização de inteligência de segurança: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="354c2-151">&ensp;Lançado: **1º de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="354c2-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="354c2-152">&ensp;Plataforma: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="354c2-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="354c2-153">&ensp;Mecanismo: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="354c2-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="354c2-154">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="354c2-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="354c2-155">Novidades</span><span class="sxs-lookup"><span data-stu-id="354c2-155">What's new</span></span>
- <span data-ttu-id="354c2-156">Lógica adicional de monitoramento de comportamento</span><span class="sxs-lookup"><span data-stu-id="354c2-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="354c2-157">Detecção aprimorada do keylogger do modo kernel</span><span class="sxs-lookup"><span data-stu-id="354c2-157">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="354c2-158">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="354c2-158">Known Issues</span></span>
<span data-ttu-id="354c2-159">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="354c2-159">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="354c2-160">Março-2021 (Plataforma: 4.18.2103.7 | Mecanismo: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="354c2-160">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="354c2-161">&ensp;Versão de atualização de inteligência de segurança: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-161">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="354c2-162">&ensp;Lançado: **1º de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="354c2-162">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="354c2-163">&ensp;Plataforma: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="354c2-163">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="354c2-164">&ensp;Mecanismo: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="354c2-164">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="354c2-165">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="354c2-165">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="354c2-166">Novidades</span><span class="sxs-lookup"><span data-stu-id="354c2-166">What's new</span></span>

- <span data-ttu-id="354c2-167">Melhoria no mecanismo de Monitoramento de Comportamento</span><span class="sxs-lookup"><span data-stu-id="354c2-167">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="354c2-168">Mitigações de ataques de força bruta de rede expandida</span><span class="sxs-lookup"><span data-stu-id="354c2-168">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="354c2-169">Geração adicional de eventos de tentativa de adulteração com falha quando [a Proteção contra Adulteração](prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada</span><span class="sxs-lookup"><span data-stu-id="354c2-169">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="354c2-170">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="354c2-170">Known Issues</span></span>
<span data-ttu-id="354c2-171">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="354c2-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="354c2-172">Atualizações de versão anterior: Suporte técnico somente a atualização</span><span class="sxs-lookup"><span data-stu-id="354c2-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="354c2-173">Depois que uma nova versão de pacote é lançada, o suporte para as duas versões anteriores é reduzido apenas ao suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="354c2-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="354c2-174">Versões anteriores às listadas nesta seção são fornecidas apenas para suporte técnico de atualização.</span><span class="sxs-lookup"><span data-stu-id="354c2-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="354c2-175">Fevereiro-2021 (plataforma: 4.18.2102.3 | Mecanismo: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="354c2-175">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="354c2-176">&ensp;Versão de atualização de inteligência de segurança: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-176">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="354c2-177">&ensp;Lançado: **9 de março de 2021**</span><span class="sxs-lookup"><span data-stu-id="354c2-177">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="354c2-178">&ensp;Plataforma: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="354c2-178">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="354c2-179">&ensp;Mecanismo: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="354c2-179">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="354c2-180">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="354c2-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="354c2-181">Novidades</span><span class="sxs-lookup"><span data-stu-id="354c2-181">What's new</span></span>

- <span data-ttu-id="354c2-182">Recuperação aprimorada do serviço por meio [da proteção contra violações](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="354c2-182">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="354c2-183">Estender escopo de proteção contra violações</span><span class="sxs-lookup"><span data-stu-id="354c2-183">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="354c2-184">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="354c2-184">Known Issues</span></span>
<span data-ttu-id="354c2-185">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="354c2-185">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="354c2-186">Janeiro-2021 (Plataforma: 4.18.2101.9 | Mecanismo: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="354c2-186">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="354c2-187">&ensp;Versão de atualização de inteligência de segurança: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-187">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="354c2-188">&ensp;Lançado: **2 de fevereiro de 2021**</span><span class="sxs-lookup"><span data-stu-id="354c2-188">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="354c2-189">&ensp;Plataforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="354c2-189">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="354c2-190">&ensp;Mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="354c2-190">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="354c2-191">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="354c2-191">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="354c2-192">Novidades</span><span class="sxs-lookup"><span data-stu-id="354c2-192">What's new</span></span>

- <span data-ttu-id="354c2-193">Melhorias na detecção de exploração de shellcode</span><span class="sxs-lookup"><span data-stu-id="354c2-193">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="354c2-194">Maior visibilidade para tentativas de roubo de credenciais</span><span class="sxs-lookup"><span data-stu-id="354c2-194">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="354c2-195">Melhorias nos recursos anti-amperes em serviços Microsoft Defender Antivírus serviços</span><span class="sxs-lookup"><span data-stu-id="354c2-195">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="354c2-196">Suporte aprimorado para ARM emulação x64</span><span class="sxs-lookup"><span data-stu-id="354c2-196">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="354c2-197">Correção: EDR a notificação de bloqueio permanece no histórico de ameaças depois que a proteção em tempo real realizou a detecção inicial</span><span class="sxs-lookup"><span data-stu-id="354c2-197">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="354c2-198">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="354c2-198">Known Issues</span></span>
<span data-ttu-id="354c2-199">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="354c2-199">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="354c2-200">Novembro-2020 (Plataforma: 4.18.2011.6 | Mecanismo: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="354c2-200">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="354c2-201">&ensp;Versão de atualização de inteligência de segurança: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-201">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="354c2-202">&ensp;Lançado: **03 de dezembro de 2020**</span><span class="sxs-lookup"><span data-stu-id="354c2-202">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="354c2-203">&ensp;Plataforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="354c2-203">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="354c2-204">&ensp;Mecanismo: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="354c2-204">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="354c2-205">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="354c2-205">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="354c2-206">Novidades</span><span class="sxs-lookup"><span data-stu-id="354c2-206">What's new</span></span>

- <span data-ttu-id="354c2-207">Registro em log de suporte ao status [do SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) aprimorado</span><span class="sxs-lookup"><span data-stu-id="354c2-207">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="354c2-208">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="354c2-208">Known Issues</span></span>
<span data-ttu-id="354c2-209">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="354c2-209">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="354c2-210">Outubro-2020 (Plataforma: 4.18.2010.7 | Mecanismo: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="354c2-210">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="354c2-211">&ensp;Versão de atualização de inteligência de segurança: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-211">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="354c2-212">&ensp;Lançado: **29 de outubro de 2020**</span><span class="sxs-lookup"><span data-stu-id="354c2-212">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="354c2-213">&ensp;Plataforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="354c2-213">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="354c2-214">&ensp;Mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="354c2-214">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="354c2-215">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="354c2-215">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="354c2-216">Novidades</span><span class="sxs-lookup"><span data-stu-id="354c2-216">What's new</span></span>

- <span data-ttu-id="354c2-217">Novas descrições para categorias de ameaças especiais</span><span class="sxs-lookup"><span data-stu-id="354c2-217">New descriptions for special threat categories</span></span>
- <span data-ttu-id="354c2-218">Recursos de emulação aprimorados</span><span class="sxs-lookup"><span data-stu-id="354c2-218">Improved emulation capabilities</span></span>
- <span data-ttu-id="354c2-219">Recursos de permitir/bloquear endereço de host aprimorados</span><span class="sxs-lookup"><span data-stu-id="354c2-219">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="354c2-220">Nova opção no CSP do Defender para Ignorar a mesclação de exclusões de usuários locais</span><span class="sxs-lookup"><span data-stu-id="354c2-220">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="354c2-221">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="354c2-221">Known Issues</span></span>

<span data-ttu-id="354c2-222">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="354c2-222">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="354c2-223">Setembro-2020 (Plataforma: 4.18.2009.7 | Mecanismo: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="354c2-223">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="354c2-224">&ensp;Versão de atualização de inteligência de segurança: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-224">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="354c2-225">&ensp;Lançado: **01 de outubro de 2020**</span><span class="sxs-lookup"><span data-stu-id="354c2-225">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="354c2-226">&ensp;Plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="354c2-226">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="354c2-227">&ensp;Mecanismo: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="354c2-227">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="354c2-228">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="354c2-228">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="354c2-229">Novidades</span><span class="sxs-lookup"><span data-stu-id="354c2-229">What's new</span></span>

- <span data-ttu-id="354c2-230">Permissões de administrador são necessárias para restaurar arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="354c2-230">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="354c2-231">Eventos formatados xml agora são suportados</span><span class="sxs-lookup"><span data-stu-id="354c2-231">XML formatted events are now supported</span></span>
- <span data-ttu-id="354c2-232">Suporte a CSP para ignorar mesclações de exclusão</span><span class="sxs-lookup"><span data-stu-id="354c2-232">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="354c2-233">Novas interfaces de gerenciamento para:</span><span class="sxs-lookup"><span data-stu-id="354c2-233">New management interfaces for:</span></span>
   - <span data-ttu-id="354c2-234">Inspeção UDP</span><span class="sxs-lookup"><span data-stu-id="354c2-234">UDP Inspection</span></span>
   - <span data-ttu-id="354c2-235">Proteção de Rede no Server 2019</span><span class="sxs-lookup"><span data-stu-id="354c2-235">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="354c2-236">Exclusões de endereço IP para Proteção de Rede</span><span class="sxs-lookup"><span data-stu-id="354c2-236">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="354c2-237">Visibilidade aprimorada nas medições do TPM</span><span class="sxs-lookup"><span data-stu-id="354c2-237">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="354c2-238">Verificação aprimorada Office módulo VBA</span><span class="sxs-lookup"><span data-stu-id="354c2-238">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="354c2-239">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="354c2-239">Known Issues</span></span>

<span data-ttu-id="354c2-240">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="354c2-240">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="354c2-241">Agosto-2020 (plataforma: 4.18.2008.9 | Mecanismo: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="354c2-241">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="354c2-242">&ensp;Versão de atualização de inteligência de segurança: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-242">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="354c2-243">&ensp;Lançado: **27 de agosto de 2020**</span><span class="sxs-lookup"><span data-stu-id="354c2-243">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="354c2-244">&ensp;Plataforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="354c2-244">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="354c2-245">&ensp;Mecanismo: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="354c2-245">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="354c2-246">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="354c2-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="354c2-247">Novidades</span><span class="sxs-lookup"><span data-stu-id="354c2-247">What's new</span></span>

- <span data-ttu-id="354c2-248">Adicionar mais eventos de telemetria</span><span class="sxs-lookup"><span data-stu-id="354c2-248">Add more telemetry events</span></span>
- <span data-ttu-id="354c2-249">Telemetria de eventos de verificação aprimorada</span><span class="sxs-lookup"><span data-stu-id="354c2-249">Improved scan event telemetry</span></span>
- <span data-ttu-id="354c2-250">Monitoramento de comportamento aprimorado para verificações de memória</span><span class="sxs-lookup"><span data-stu-id="354c2-250">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="354c2-251">Verificação de fluxos de macros aprimorados</span><span class="sxs-lookup"><span data-stu-id="354c2-251">Improved macro streams scanning</span></span>
- <span data-ttu-id="354c2-252">Adicionado `AMRunningMode` ao cmdlet Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="354c2-252">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="354c2-253">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) é ignorado.</span><span class="sxs-lookup"><span data-stu-id="354c2-253">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="354c2-254">Microsoft Defender Antivírus se desliga automaticamente quando detecta outro programa antivírus.</span><span class="sxs-lookup"><span data-stu-id="354c2-254">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="354c2-255">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="354c2-255">Known Issues</span></span>
<span data-ttu-id="354c2-256">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="354c2-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="354c2-257">Julho-2020 (Plataforma: 4.18.2007.8 | Mecanismo: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="354c2-257">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="354c2-258">&ensp;Versão de atualização de inteligência de segurança: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-258">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="354c2-259">&ensp;Lançado: **28 de julho de 2020**</span><span class="sxs-lookup"><span data-stu-id="354c2-259">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="354c2-260">&ensp;Plataforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="354c2-260">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="354c2-261">&ensp;Mecanismo: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="354c2-261">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="354c2-262">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="354c2-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="354c2-263">Novidades</span><span class="sxs-lookup"><span data-stu-id="354c2-263">What's new</span></span>

- <span data-ttu-id="354c2-264">Telemetria aprimorada para BITS</span><span class="sxs-lookup"><span data-stu-id="354c2-264">Improved telemetry for BITS</span></span>
- <span data-ttu-id="354c2-265">Validação aprimorada de certificado de assinatura de código Authenticode</span><span class="sxs-lookup"><span data-stu-id="354c2-265">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="354c2-266">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="354c2-266">Known Issues</span></span>
<span data-ttu-id="354c2-267">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="354c2-267">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="354c2-268">Junho-2020 (Plataforma: 4.18.2006.10 | Mecanismo: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="354c2-268">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="354c2-269">&ensp;Versão de atualização de inteligência de segurança: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-269">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="354c2-270">&ensp;Lançado: **22 de junho de 2020**</span><span class="sxs-lookup"><span data-stu-id="354c2-270">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="354c2-271">&ensp;Plataforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="354c2-271">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="354c2-272">&ensp;Mecanismo: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="354c2-272">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="354c2-273">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="354c2-273">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="354c2-274">Novidades</span><span class="sxs-lookup"><span data-stu-id="354c2-274">What's new</span></span>

- <span data-ttu-id="354c2-275">Possibilidade de especificar o [local dos logs de suporte](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="354c2-275">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="354c2-276">Ignorar a verificação de captura agressiva no modo Passivo.</span><span class="sxs-lookup"><span data-stu-id="354c2-276">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="354c2-277">Permitir que o Defender atualize em conexões com metros</span><span class="sxs-lookup"><span data-stu-id="354c2-277">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="354c2-278">Ajuste de desempenho fixo quando o cache está desabilitado</span><span class="sxs-lookup"><span data-stu-id="354c2-278">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="354c2-279">Consulta de registro fixa</span><span class="sxs-lookup"><span data-stu-id="354c2-279">Fixed registry query</span></span> 
- <span data-ttu-id="354c2-280">Randomização de tempo de verificação fixa no ADMX</span><span class="sxs-lookup"><span data-stu-id="354c2-280">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="354c2-281">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="354c2-281">Known Issues</span></span>
<span data-ttu-id="354c2-282">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="354c2-282">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="354c2-283">Maio-2020 (plataforma: 4.18.2005.4 | Mecanismo: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="354c2-283">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="354c2-284">&ensp;Versão de atualização de inteligência de segurança: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-284">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="354c2-285">&ensp;Lançado: **26 de maio de 2020**</span><span class="sxs-lookup"><span data-stu-id="354c2-285">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="354c2-286">&ensp;Plataforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="354c2-286">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="354c2-287">&ensp;Mecanismo: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="354c2-287">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="354c2-288">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="354c2-288">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="354c2-289">Novidades</span><span class="sxs-lookup"><span data-stu-id="354c2-289">What's new</span></span>

- <span data-ttu-id="354c2-290">Registro em log aprimorado para eventos de verificação</span><span class="sxs-lookup"><span data-stu-id="354c2-290">Improved logging for scan events</span></span>
- <span data-ttu-id="354c2-291">Melhor tratamento de falhas no modo de usuário.</span><span class="sxs-lookup"><span data-stu-id="354c2-291">Improved user mode crash handling.</span></span>
- <span data-ttu-id="354c2-292">Rastreamento de eventos adicionado para proteção contra adulteração</span><span class="sxs-lookup"><span data-stu-id="354c2-292">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="354c2-293">Envio de amostra AMSI corrigido</span><span class="sxs-lookup"><span data-stu-id="354c2-293">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="354c2-294">Bloqueio fixo da nuvem AMSI</span><span class="sxs-lookup"><span data-stu-id="354c2-294">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="354c2-295">Log de instalação de atualização de segurança fixa</span><span class="sxs-lookup"><span data-stu-id="354c2-295">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="354c2-296">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="354c2-296">Known Issues</span></span>
<span data-ttu-id="354c2-297">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="354c2-297">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="354c2-298">Abril-2020 (Plataforma: 4.18.2004.6 | Mecanismo: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="354c2-298">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="354c2-299">&ensp;Versão de atualização de inteligência de segurança: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-299">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="354c2-300">&ensp;Lançado: **30 de abril de 2020**</span><span class="sxs-lookup"><span data-stu-id="354c2-300">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="354c2-301">&ensp;Plataforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="354c2-301">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="354c2-302">&ensp;Mecanismo: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="354c2-302">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="354c2-303">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="354c2-303">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="354c2-304">Novidades</span><span class="sxs-lookup"><span data-stu-id="354c2-304">What's new</span></span>
- <span data-ttu-id="354c2-305">Melhorias do WDfilter</span><span class="sxs-lookup"><span data-stu-id="354c2-305">WDfilter improvements</span></span>
- <span data-ttu-id="354c2-306">Adicionar mais dados de evento acionáveis para atacar eventos de detecção de redução de superfície</span><span class="sxs-lookup"><span data-stu-id="354c2-306">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="354c2-307">Informações de versão fixas em dados de diagnóstico e WMI</span><span class="sxs-lookup"><span data-stu-id="354c2-307">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="354c2-308">Versão da plataforma incorreta corrigida na interface do usuário após a atualização da plataforma</span><span class="sxs-lookup"><span data-stu-id="354c2-308">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="354c2-309">Intel de URL dinâmica para proteção contra ameaças sem arquivo</span><span class="sxs-lookup"><span data-stu-id="354c2-309">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="354c2-310">Recurso de verificação UEFI</span><span class="sxs-lookup"><span data-stu-id="354c2-310">UEFI scan capability</span></span>
- <span data-ttu-id="354c2-311">Estender o log para atualizações</span><span class="sxs-lookup"><span data-stu-id="354c2-311">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="354c2-312">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="354c2-312">Known Issues</span></span>
<span data-ttu-id="354c2-313">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="354c2-313">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="354c2-314">Março-2020 (Plataforma: 4.18.2003.8 | Mecanismo: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="354c2-314">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="354c2-315">&ensp;Versão de atualização de inteligência de segurança: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-315">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="354c2-316">&ensp;Lançado: **24 de março de 2020**</span><span class="sxs-lookup"><span data-stu-id="354c2-316">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="354c2-317">&ensp;Plataforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="354c2-317">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="354c2-318">&ensp;Mecanismo: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="354c2-318">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="354c2-319">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="354c2-319">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="354c2-320">Novidades</span><span class="sxs-lookup"><span data-stu-id="354c2-320">What's new</span></span>

- <span data-ttu-id="354c2-321">Opção de throttling de CPU adicionada ao [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="354c2-321">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="354c2-322">Melhorar a funcionalidade de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="354c2-322">Improve diagnostic capability</span></span>
- <span data-ttu-id="354c2-323">reduzir o tempo de tempo de inteligência de segurança (5 minutos)</span><span class="sxs-lookup"><span data-stu-id="354c2-323">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="354c2-324">Estender a funcionalidade de log interno do mecanismo AMSI</span><span class="sxs-lookup"><span data-stu-id="354c2-324">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="354c2-325">Melhorar a notificação para bloqueio de processos</span><span class="sxs-lookup"><span data-stu-id="354c2-325">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="354c2-326">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="354c2-326">Known Issues</span></span>
<span data-ttu-id="354c2-327">[**Fixo**] Microsoft Defender Antivírus está ignorando arquivos ao executar uma verificação.</span><span class="sxs-lookup"><span data-stu-id="354c2-327">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="354c2-328">Fevereiro-2020 (Plataforma: - | Mecanismo: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="354c2-328">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="354c2-329">&ensp;Versão de atualização de inteligência de segurança: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="354c2-329">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="354c2-330">&ensp;Lançado: **25 de fevereiro de 2020**</span><span class="sxs-lookup"><span data-stu-id="354c2-330">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="354c2-331">&ensp;Plataforma/Cliente: **-**</span><span class="sxs-lookup"><span data-stu-id="354c2-331">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="354c2-332">&ensp;Mecanismo: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="354c2-332">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="354c2-333">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="354c2-333">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="354c2-334">Novidades</span><span class="sxs-lookup"><span data-stu-id="354c2-334">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="354c2-335">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="354c2-335">Known Issues</span></span>
<span data-ttu-id="354c2-336">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="354c2-336">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="354c2-337">Janeiro-2020 (Plataforma: 4.18.2001.10 | Mecanismo: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="354c2-337">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="354c2-338">Versão de atualização de inteligência de segurança: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-338">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="354c2-339">Lançado: **30 de janeiro de 2020**</span><span class="sxs-lookup"><span data-stu-id="354c2-339">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="354c2-340">Plataforma/Cliente: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="354c2-340">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="354c2-341">Mecanismo: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="354c2-341">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="354c2-342">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="354c2-342">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="354c2-343">Novidades</span><span class="sxs-lookup"><span data-stu-id="354c2-343">What's new</span></span>

- <span data-ttu-id="354c2-344">BSOD fixo no WS2016 com Exchange</span><span class="sxs-lookup"><span data-stu-id="354c2-344">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="354c2-345">Atualizações da plataforma de suporte quando o TMP é redirecionado para o caminho da rede</span><span class="sxs-lookup"><span data-stu-id="354c2-345">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="354c2-346">As versões de plataforma e mecanismo são [adicionadas ao WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="354c2-346">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="354c2-347">estender a atualização de assinatura de emergência para [o modo passivo](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="354c2-347">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="354c2-348">Corrigir trava 4.18.1911.3</span><span class="sxs-lookup"><span data-stu-id="354c2-348">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="354c2-349">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="354c2-349">Known Issues</span></span>

<span data-ttu-id="354c2-350">[**Fixo**] dispositivos [que](/windows-hardware/design/device-experiences/modern-standby) usam o modo de espera moderno podem ter uma trava com o driver de filtro Windows Defender que resulta em uma lacuna de proteção.</span><span class="sxs-lookup"><span data-stu-id="354c2-350">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="354c2-351">Os máquinas afetados aparecem para o cliente como não atualizados para a plataforma antimalware mais recente.</span><span class="sxs-lookup"><span data-stu-id="354c2-351">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="354c2-352">Esta atualização é:</span><span class="sxs-lookup"><span data-stu-id="354c2-352">This update is:</span></span>
> - <span data-ttu-id="354c2-353">necessário por dispositivos RS1 que executam a versão inferior da plataforma para dar suporte ao SHA2;</span><span class="sxs-lookup"><span data-stu-id="354c2-353">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="354c2-354">tem um sinalizador de reinicialização para sistemas que têm problemas de suspensão;</span><span class="sxs-lookup"><span data-stu-id="354c2-354">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="354c2-355">é re-lançado em abril de 2020 e não será superada por atualizações mais novas para manter a disponibilidade futura;</span><span class="sxs-lookup"><span data-stu-id="354c2-355">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="354c2-356">é categorizado como uma atualização devido ao requisito de reinicialização; e</span><span class="sxs-lookup"><span data-stu-id="354c2-356">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="354c2-357">só será oferecido com o [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="354c2-357">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="354c2-358">Novembro-2019 (plataforma: 4.18.1911.3 | Mecanismo: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="354c2-358">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="354c2-359">Versão de atualização de inteligência de segurança: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-359">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="354c2-360">Lançado: **7 de dezembro de 2019**</span><span class="sxs-lookup"><span data-stu-id="354c2-360">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="354c2-361">Plataforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="354c2-361">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="354c2-362">Mecanismo: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="354c2-362">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="354c2-363">Fase de suporte: **sem suporte**</span><span class="sxs-lookup"><span data-stu-id="354c2-363">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="354c2-364">Novidades</span><span class="sxs-lookup"><span data-stu-id="354c2-364">What's new</span></span>

- <span data-ttu-id="354c2-365">Nível de rastreamento De MpCmdRun fixo</span><span class="sxs-lookup"><span data-stu-id="354c2-365">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="354c2-366">Informações de versão fixas do WDFilter</span><span class="sxs-lookup"><span data-stu-id="354c2-366">Fixed WDFilter version info</span></span>
- <span data-ttu-id="354c2-367">Melhorar notificações (PUA)</span><span class="sxs-lookup"><span data-stu-id="354c2-367">Improve notifications (PUA)</span></span>
- <span data-ttu-id="354c2-368">adicionar logs MRT para dar suporte a arquivos</span><span class="sxs-lookup"><span data-stu-id="354c2-368">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="354c2-369">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="354c2-369">Known Issues</span></span>
<span data-ttu-id="354c2-370">Quando essa atualização é instalada, o dispositivo precisa do pacote de salto 4.10.2001.10 para poder atualizar para a versão mais recente da plataforma.</span><span class="sxs-lookup"><span data-stu-id="354c2-370">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="354c2-371">Microsoft Defender Antivírus plataforma</span><span class="sxs-lookup"><span data-stu-id="354c2-371">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="354c2-372">As atualizações de plataforma e mecanismo são fornecidas em uma cadência mensal.</span><span class="sxs-lookup"><span data-stu-id="354c2-372">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="354c2-373">Para ter suporte total, mantenha-se atualizado com as atualizações mais recentes da plataforma.</span><span class="sxs-lookup"><span data-stu-id="354c2-373">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="354c2-374">Nossa estrutura de suporte é dinâmica, evoluindo em duas fases, dependendo da disponibilidade da versão mais recente da plataforma:</span><span class="sxs-lookup"><span data-stu-id="354c2-374">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="354c2-375">Fase de manutenção de Atualizações **Críticas** e Segurança - Ao executar a versão mais recente da plataforma, você estará qualificado para receber atualizações de segurança e críticas para a plataforma anti-malware.</span><span class="sxs-lookup"><span data-stu-id="354c2-375">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="354c2-376">Fase de Suporte Técnico **(Somente)** - Depois que uma nova versão da plataforma for lançada, o suporte para versões mais antigas (N-2) será redução apenas para suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="354c2-376">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="354c2-377">As versões da plataforma anteriores ao N-2 não serão mais suportadas.\*</span><span class="sxs-lookup"><span data-stu-id="354c2-377">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="354c2-378">\*O suporte técnico continuará a ser fornecido para atualizações da versão Windows 10 versão do Windows 10 (consulte Versão da plataforma incluída com Windows 10 [versões](#platform-version-included-with-windows-10-releases)) para a versão mais recente da plataforma.</span><span class="sxs-lookup"><span data-stu-id="354c2-378">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="354c2-379">Durante a fase de suporte técnico (somente), incidentes de suporte comercialmente razoáveis serão fornecidos por meio do Serviço de Atendimento ao Cliente da Microsoft & Suporte e ofertas de suporte gerenciado da Microsoft (como o Suporte Premier).</span><span class="sxs-lookup"><span data-stu-id="354c2-379">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="354c2-380">Se um incidente de suporte exigir escalonamento para desenvolvimento para obter mais orientações, exigir uma atualização que não seja de segurança ou exigir uma atualização de segurança, os clientes serão solicitados a atualizar para a versão mais recente da plataforma ou uma atualização intermediária (\*).</span><span class="sxs-lookup"><span data-stu-id="354c2-380">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="354c2-381">Versão da plataforma incluída com Windows 10 versões</span><span class="sxs-lookup"><span data-stu-id="354c2-381">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="354c2-382">A tabela a seguir fornece as versões Microsoft Defender Antivírus plataforma e mecanismo que são enviadas com as versões Windows 10 versão mais recentes:</span><span class="sxs-lookup"><span data-stu-id="354c2-382">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="354c2-383">Windows 10 versão</span><span class="sxs-lookup"><span data-stu-id="354c2-383">Windows 10 release</span></span>  |<span data-ttu-id="354c2-384">Versão da plataforma</span><span class="sxs-lookup"><span data-stu-id="354c2-384">Platform version</span></span>  |<span data-ttu-id="354c2-385">Versão do mecanismo</span><span class="sxs-lookup"><span data-stu-id="354c2-385">Engine version</span></span> |<span data-ttu-id="354c2-386">Fase de suporte</span><span class="sxs-lookup"><span data-stu-id="354c2-386">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="354c2-387">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="354c2-387">2004  (20H1/20H2)</span></span> |<span data-ttu-id="354c2-388">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="354c2-388">4.18.1909.6</span></span> |<span data-ttu-id="354c2-389">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="354c2-389">1.1.17000.2</span></span> | <span data-ttu-id="354c2-390">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="354c2-390">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="354c2-391">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="354c2-391">1909  (19H2)</span></span> |<span data-ttu-id="354c2-392">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="354c2-392">4.18.1902.5</span></span> |<span data-ttu-id="354c2-393">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="354c2-393">1.1.16700.3</span></span> | <span data-ttu-id="354c2-394">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="354c2-394">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="354c2-395">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="354c2-395">1903  (19H1)</span></span> |<span data-ttu-id="354c2-396">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="354c2-396">4.18.1902.5</span></span> |<span data-ttu-id="354c2-397">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="354c2-397">1.1.15600.4</span></span> | <span data-ttu-id="354c2-398">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="354c2-398">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="354c2-399">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="354c2-399">1809  (RS5)</span></span> |<span data-ttu-id="354c2-400">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="354c2-400">4.18.1807.18075</span></span> |<span data-ttu-id="354c2-401">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="354c2-401">1.1.15000.2</span></span> | <span data-ttu-id="354c2-402">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="354c2-402">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="354c2-403">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="354c2-403">1803  (RS4)</span></span> |<span data-ttu-id="354c2-404">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="354c2-404">4.13.17134.1</span></span> |<span data-ttu-id="354c2-405">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="354c2-405">1.1.14600.4</span></span> | <span data-ttu-id="354c2-406">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="354c2-406">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="354c2-407">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="354c2-407">1709  (RS3)</span></span> |<span data-ttu-id="354c2-408">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="354c2-408">4.12.16299.15</span></span> |<span data-ttu-id="354c2-409">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="354c2-409">1.1.14104.0</span></span> | <span data-ttu-id="354c2-410">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="354c2-410">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="354c2-411">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="354c2-411">1703  (RS2)</span></span> |<span data-ttu-id="354c2-412">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="354c2-412">4.11.15603.2</span></span> |<span data-ttu-id="354c2-413">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="354c2-413">1.1.13504.0</span></span> | <span data-ttu-id="354c2-414">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="354c2-414">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="354c2-415">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="354c2-415">1607 (RS1)</span></span> |<span data-ttu-id="354c2-416">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="354c2-416">4.10.14393.3683</span></span> |<span data-ttu-id="354c2-417">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="354c2-417">1.1.12805.0</span></span> | <span data-ttu-id="354c2-418">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="354c2-418">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="354c2-419">Para Windows 10 informações de versão, consulte a planilha Windows de fatos do ciclo [de vida.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="354c2-419">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="354c2-420">Atualizações para Manutenção e Gerenciamento de Imagens de Implantação (DISM)</span><span class="sxs-lookup"><span data-stu-id="354c2-420">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="354c2-421">Recomendamos atualizar suas Windows 10 (Enterprise, Pro e edições Home), o Windows Server 2019 e Windows Server 2016 imagens de instalação do sistema operacional com as atualizações mais recentes de antivírus e antimalware.</span><span class="sxs-lookup"><span data-stu-id="354c2-421">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="354c2-422">Manter as imagens de instalação do sistema operacional atualizadas ajuda a evitar uma lacuna na proteção.</span><span class="sxs-lookup"><span data-stu-id="354c2-422">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="354c2-423">Para obter mais informações, consulte [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="354c2-423">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="354c2-424">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="354c2-424">1.1.2106.01</span></span></summary>

<span data-ttu-id="354c2-425">&ensp;Versão do pacote: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="354c2-425">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="354c2-426">&ensp;Versão da plataforma: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="354c2-426">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="354c2-427">&ensp;Versão do mecanismo: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="354c2-427">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="354c2-428">&ensp;Versão de assinatura: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-428">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="354c2-429">Correções</span><span class="sxs-lookup"><span data-stu-id="354c2-429">Fixes</span></span>
- <span data-ttu-id="354c2-430">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="354c2-430">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="354c2-431">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="354c2-431">Additional information</span></span>
- <span data-ttu-id="354c2-432">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="354c2-432">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="354c2-433">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="354c2-433">1.1.2105.01</span></span></summary>

<span data-ttu-id="354c2-434">&ensp;Versão do pacote: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="354c2-434">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="354c2-435">&ensp;Versão da plataforma: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="354c2-435">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="354c2-436">&ensp;Versão do mecanismo: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="354c2-436">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="354c2-437">&ensp;Versão de assinatura: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-437">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="354c2-438">Correções</span><span class="sxs-lookup"><span data-stu-id="354c2-438">Fixes</span></span>
- <span data-ttu-id="354c2-439">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="354c2-439">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="354c2-440">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="354c2-440">Additional information</span></span>
- <span data-ttu-id="354c2-441">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="354c2-441">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="354c2-442">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="354c2-442">1.1.2104.01</span></span></summary>

<span data-ttu-id="354c2-443">&ensp;Versão do pacote: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="354c2-443">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="354c2-444">&ensp;Versão da plataforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="354c2-444">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="354c2-445">&ensp;Versão do mecanismo: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="354c2-445">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="354c2-446">&ensp;Versão de assinatura: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-446">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="354c2-447">Correções</span><span class="sxs-lookup"><span data-stu-id="354c2-447">Fixes</span></span>
- <span data-ttu-id="354c2-448">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="354c2-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="354c2-449">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="354c2-449">Additional information</span></span>
- <span data-ttu-id="354c2-450">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="354c2-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="354c2-451">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="354c2-451">1.1.2103.01</span></span></summary>

<span data-ttu-id="354c2-452">&ensp;Versão do pacote: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="354c2-452">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="354c2-453">&ensp;Versão da plataforma: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="354c2-453">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="354c2-454">&ensp;Versão do mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="354c2-454">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="354c2-455">&ensp;Versão de assinatura: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-455">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="354c2-456">Correções</span><span class="sxs-lookup"><span data-stu-id="354c2-456">Fixes</span></span>
- <span data-ttu-id="354c2-457">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="354c2-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="354c2-458">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="354c2-458">Additional information</span></span>
- <span data-ttu-id="354c2-459">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="354c2-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="354c2-460">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="354c2-460">1.1.2102.03</span></span></summary>

<span data-ttu-id="354c2-461">&ensp;Versão do pacote: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="354c2-461">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="354c2-462">&ensp;Versão da plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="354c2-462">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="354c2-463">&ensp;Versão do mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="354c2-463">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="354c2-464">&ensp;Versão de assinatura: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-464">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="354c2-465">Correções</span><span class="sxs-lookup"><span data-stu-id="354c2-465">Fixes</span></span>
- <span data-ttu-id="354c2-466">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="354c2-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="354c2-467">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="354c2-467">Additional information</span></span>
- <span data-ttu-id="354c2-468">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="354c2-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="354c2-469">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="354c2-469">1.1.2101.02</span></span></summary>

<span data-ttu-id="354c2-470">&ensp;Versão do pacote: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="354c2-470">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="354c2-471">&ensp;Versão da plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="354c2-471">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="354c2-472">&ensp;Versão do mecanismo: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="354c2-472">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="354c2-473">&ensp;Versão de assinatura: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-473">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="354c2-474">Correções</span><span class="sxs-lookup"><span data-stu-id="354c2-474">Fixes</span></span>
- <span data-ttu-id="354c2-475">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="354c2-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="354c2-476">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="354c2-476">Additional information</span></span>
- <span data-ttu-id="354c2-477">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="354c2-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="354c2-478">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="354c2-478">1.1.2012.01</span></span></summary>

<span data-ttu-id="354c2-479">&ensp;Versão do pacote: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="354c2-479">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="354c2-480">&ensp;Versão da plataforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="354c2-480">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="354c2-481">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="354c2-481">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="354c2-482">&ensp;Versão de assinatura: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-482">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="354c2-483">Correções</span><span class="sxs-lookup"><span data-stu-id="354c2-483">Fixes</span></span>
- <span data-ttu-id="354c2-484">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="354c2-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="354c2-485">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="354c2-485">Additional information</span></span>
- <span data-ttu-id="354c2-486">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="354c2-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="354c2-487">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="354c2-487">1.1.2011.02</span></span></summary>

<span data-ttu-id="354c2-488">&ensp;Versão do pacote: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="354c2-488">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="354c2-489">&ensp;Versão da plataforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="354c2-489">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="354c2-490">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="354c2-490">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="354c2-491">&ensp;Versão de assinatura: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-491">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="354c2-492">Correções</span><span class="sxs-lookup"><span data-stu-id="354c2-492">Fixes</span></span>
- <span data-ttu-id="354c2-493">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="354c2-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="354c2-494">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="354c2-494">Additional information</span></span>
- <span data-ttu-id="354c2-495">Assinaturas Microsoft Defender Antivírus atualizadas</span><span class="sxs-lookup"><span data-stu-id="354c2-495">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="354c2-496">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="354c2-496">1.1.2011.01</span></span></summary>

<span data-ttu-id="354c2-497">&ensp;Versão do pacote: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="354c2-497">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="354c2-498">&ensp;Versão da plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="354c2-498">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="354c2-499">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="354c2-499">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="354c2-500">&ensp;Versão de assinatura: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-500">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="354c2-501">Correções</span><span class="sxs-lookup"><span data-stu-id="354c2-501">Fixes</span></span>
- <span data-ttu-id="354c2-502">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="354c2-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="354c2-503">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="354c2-503">Additional information</span></span>
- <span data-ttu-id="354c2-504">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="354c2-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="354c2-505">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="354c2-505">1.1.2009.10</span></span></summary>

<span data-ttu-id="354c2-506">&ensp;Versão do pacote: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="354c2-506">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="354c2-507">&ensp;Versão da plataforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="354c2-507">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="354c2-508">&ensp;Versão do mecanismo: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="354c2-508">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="354c2-509">&ensp;Versão de assinatura: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="354c2-509">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="354c2-510">Correções</span><span class="sxs-lookup"><span data-stu-id="354c2-510">Fixes</span></span>
- <span data-ttu-id="354c2-511">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="354c2-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="354c2-512">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="354c2-512">Additional information</span></span>
- <span data-ttu-id="354c2-513">Adicionado suporte para Windows 10 RS1 ou imagens de instalação posteriores do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="354c2-513">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="354c2-514">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="354c2-514">Additional resources</span></span>

| <span data-ttu-id="354c2-515">Artigo</span><span class="sxs-lookup"><span data-stu-id="354c2-515">Article</span></span> | <span data-ttu-id="354c2-516">Descrição</span><span class="sxs-lookup"><span data-stu-id="354c2-516">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="354c2-517">Atualização do Microsoft Defender para Windows de instalação do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="354c2-517">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="354c2-518">Revise os pacotes de atualização antimalware para as imagens de instalação do sistema operacional (arquivos WIM e VHD).</span><span class="sxs-lookup"><span data-stu-id="354c2-518">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="354c2-519">Obter Microsoft Defender Antivírus atualizações para Windows 10 (Enterprise, Pro e edições Home), Windows Server 2019 e Windows Server 2016 de instalação.</span><span class="sxs-lookup"><span data-stu-id="354c2-519">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="354c2-520">Gerenciar como as atualizações de proteção são baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="354c2-520">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="354c2-521">As atualizações de proteção podem ser entregues por meio de várias fontes.</span><span class="sxs-lookup"><span data-stu-id="354c2-521">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="354c2-522">Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="354c2-522">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="354c2-523">Você pode agendar quando as atualizações de proteção devem ser baixadas.</span><span class="sxs-lookup"><span data-stu-id="354c2-523">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="354c2-524">Gerenciar atualizações para pontos de extremidade que estão des date</span><span class="sxs-lookup"><span data-stu-id="354c2-524">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="354c2-525">Se um ponto de extremidade perder uma atualização ou uma verificação agendada, você poderá forçar uma atualização ou verificar na próxima vez que um usuário entrar.</span><span class="sxs-lookup"><span data-stu-id="354c2-525">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="354c2-526">Gerenciar atualizações aplicadas com base em evento</span><span class="sxs-lookup"><span data-stu-id="354c2-526">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="354c2-527">Você pode definir atualizações de proteção a serem baixadas na inicialização ou após determinados eventos de proteção entregues na nuvem.</span><span class="sxs-lookup"><span data-stu-id="354c2-527">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="354c2-528">Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)</span><span class="sxs-lookup"><span data-stu-id="354c2-528">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="354c2-529">Você pode especificar configurações, como se as atualizações devem ocorrer na energia da bateria, que são especialmente úteis para dispositivos móveis e máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="354c2-529">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
