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
ms.openlocfilehash: 264a3b7a4a24c446048d6cfc6863f1ae9765566f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789178"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="ebe17-104">Gerenciar Microsoft Defender Antivírus e aplicar linhas de base</span><span class="sxs-lookup"><span data-stu-id="ebe17-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="ebe17-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ebe17-105">**Applies to:**</span></span>

- [<span data-ttu-id="ebe17-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ebe17-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="ebe17-107">Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="ebe17-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="ebe17-108">Há dois tipos de atualizações relacionadas à Microsoft Defender Antivírus atualizadas:</span><span class="sxs-lookup"><span data-stu-id="ebe17-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="ebe17-109">Atualizações de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="ebe17-109">Security intelligence updates</span></span>
- <span data-ttu-id="ebe17-110">Atualizações de produtos</span><span class="sxs-lookup"><span data-stu-id="ebe17-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebe17-111">Manter Microsoft Defender Antivírus atualizado é fundamental para garantir que seus dispositivos tenham a tecnologia e os recursos mais recentes necessários para proteger contra novas técnicas de malware e ataque.</span><span class="sxs-lookup"><span data-stu-id="ebe17-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="ebe17-112">Certifique-se de atualizar sua proteção antivírus mesmo que Microsoft Defender Antivírus está sendo executado no [modo passivo](./microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="ebe17-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="ebe17-113">Para ver o mecanismo, a plataforma e a data de assinatura mais atuais, visite as atualizações de inteligência de segurança para Microsoft Defender Antivírus e outros [antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ebe17-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="ebe17-114">Atualizações de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="ebe17-114">Security intelligence updates</span></span>

<span data-ttu-id="ebe17-115">Microsoft Defender Antivírus usa [proteção](cloud-protection-microsoft-defender-antivirus.md) entregue na nuvem (também chamada de Serviço de Proteção Avançada da Microsoft ou MAPS) e baixa periodicamente atualizações de inteligência de segurança para fornecer proteção.</span><span class="sxs-lookup"><span data-stu-id="ebe17-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="ebe17-116">As atualizações são lançadas nos números KB abaixo:</span><span class="sxs-lookup"><span data-stu-id="ebe17-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="ebe17-117">Microsoft Defender Antivírus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="ebe17-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="ebe17-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="ebe17-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="ebe17-119">A proteção entregue na nuvem está sempre ativa e requer uma conexão ativa com a Internet para funcionar.</span><span class="sxs-lookup"><span data-stu-id="ebe17-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="ebe17-120">As atualizações de inteligência de segurança ocorrem em uma cadência agendada (configurável por meio da política).</span><span class="sxs-lookup"><span data-stu-id="ebe17-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="ebe17-121">Para obter mais informações, [consulte Use Microsoft cloud-provided protection in Microsoft Defender Antivírus](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="ebe17-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="ebe17-122">Para ver uma lista de atualizações recentes de inteligência de segurança, consulte Atualizações de inteligência de segurança para Microsoft Defender Antivírus [e outros antimalware da Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="ebe17-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="ebe17-123">As atualizações do mecanismo são incluídas com atualizações de inteligência de segurança e são lançadas em uma cadência mensal.</span><span class="sxs-lookup"><span data-stu-id="ebe17-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="ebe17-124">Atualizações de produtos</span><span class="sxs-lookup"><span data-stu-id="ebe17-124">Product updates</span></span>

<span data-ttu-id="ebe17-125">Microsoft Defender Antivírus exige atualizações mensais [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) *(conhecidas* como atualizações de plataforma) e receberá atualizações de recursos principais juntamente com Windows 10 versões.</span><span class="sxs-lookup"><span data-stu-id="ebe17-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="ebe17-126">Você pode gerenciar a distribuição de atualizações por meio de um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="ebe17-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="ebe17-127">Windows Serviço de Atualização do Servidor (WSUS)</span><span class="sxs-lookup"><span data-stu-id="ebe17-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="ebe17-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ebe17-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="ebe17-129">O método comum que você usa para implantar a Microsoft e Windows atualizações para pontos de extremidade em sua rede.</span><span class="sxs-lookup"><span data-stu-id="ebe17-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="ebe17-130">Para obter mais informações, consulte [Manage the sources for Microsoft Defender Antivírus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="ebe17-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="ebe17-131">As atualizações mensais são lançadas em fases, resultando em vários pacotes visíveis em seus [Serviços de Atualização do Servidor de Janelas.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="ebe17-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="ebe17-132">Versões mensais de plataforma e mecanismo</span><span class="sxs-lookup"><span data-stu-id="ebe17-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="ebe17-133">Para obter informações sobre como atualizar ou instalar a atualização da plataforma, consulte [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="ebe17-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="ebe17-134">Todas as nossas atualizações contêm</span><span class="sxs-lookup"><span data-stu-id="ebe17-134">All our updates contain</span></span> 
- <span data-ttu-id="ebe17-135">melhorias de desempenho;</span><span class="sxs-lookup"><span data-stu-id="ebe17-135">performance improvements;</span></span>
- <span data-ttu-id="ebe17-136">melhorias de capacidade de serviço; e</span><span class="sxs-lookup"><span data-stu-id="ebe17-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="ebe17-137">melhorias de integração (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="ebe17-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="ebe17-138">Maio-2021 (plataforma: 4.18.2105.4 | Mecanismo: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="ebe17-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="ebe17-139">&ensp;Versão de atualização de inteligência de segurança: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="ebe17-140">&ensp;Lançado: **4 de junho de 2021**</span><span class="sxs-lookup"><span data-stu-id="ebe17-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="ebe17-141">&ensp;Plataforma: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="ebe17-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="ebe17-142">&ensp;Mecanismo: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="ebe17-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="ebe17-143">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="ebe17-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ebe17-144">Novidades</span><span class="sxs-lookup"><span data-stu-id="ebe17-144">What's new</span></span>
- <span data-ttu-id="ebe17-145">Melhorias no monitoramento de comportamento</span><span class="sxs-lookup"><span data-stu-id="ebe17-145">Improvements to behavior monitoring</span></span> 

### <a name="known-issues"></a><span data-ttu-id="ebe17-146">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="ebe17-146">Known Issues</span></span>
<span data-ttu-id="ebe17-147">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="ebe17-147">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ebe17-148">Abril-2021 (Plataforma: 4.18.2104.14 | Mecanismo: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="ebe17-148">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="ebe17-149">&ensp;Versão de atualização de inteligência de segurança: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-149">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="ebe17-150">&ensp;Lançado: **1º de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="ebe17-150">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="ebe17-151">&ensp;Plataforma: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="ebe17-151">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="ebe17-152">&ensp;Mecanismo: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="ebe17-152">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="ebe17-153">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="ebe17-153">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ebe17-154">Novidades</span><span class="sxs-lookup"><span data-stu-id="ebe17-154">What's new</span></span>
- <span data-ttu-id="ebe17-155">Lógica adicional de monitoramento de comportamento</span><span class="sxs-lookup"><span data-stu-id="ebe17-155">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="ebe17-156">Detecção aprimorada do keylogger do modo kernel</span><span class="sxs-lookup"><span data-stu-id="ebe17-156">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="ebe17-157">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="ebe17-157">Known Issues</span></span>
<span data-ttu-id="ebe17-158">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="ebe17-158">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ebe17-159">Março-2021 (Plataforma: 4.18.2103.7 | Mecanismo: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="ebe17-159">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="ebe17-160">&ensp;Versão de atualização de inteligência de segurança: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-160">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="ebe17-161">&ensp;Lançado: **1º de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="ebe17-161">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="ebe17-162">&ensp;Plataforma: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="ebe17-162">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="ebe17-163">&ensp;Mecanismo: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="ebe17-163">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="ebe17-164">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="ebe17-164">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ebe17-165">Novidades</span><span class="sxs-lookup"><span data-stu-id="ebe17-165">What's new</span></span>

- <span data-ttu-id="ebe17-166">Melhoria no mecanismo de Monitoramento de Comportamento</span><span class="sxs-lookup"><span data-stu-id="ebe17-166">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="ebe17-167">Mitigações de ataques de força bruta de rede expandida</span><span class="sxs-lookup"><span data-stu-id="ebe17-167">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="ebe17-168">Geração adicional de eventos de tentativa de adulteração com falha quando [a Proteção contra Adulteração](prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada</span><span class="sxs-lookup"><span data-stu-id="ebe17-168">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="ebe17-169">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="ebe17-169">Known Issues</span></span>
<span data-ttu-id="ebe17-170">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="ebe17-170">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="ebe17-171">Atualizações de versão anterior: Suporte técnico somente a atualização</span><span class="sxs-lookup"><span data-stu-id="ebe17-171">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="ebe17-172">Depois que uma nova versão de pacote é lançada, o suporte para as duas versões anteriores é reduzido apenas ao suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="ebe17-172">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="ebe17-173">Versões anteriores às listadas nesta seção são fornecidas apenas para suporte técnico de atualização.</span><span class="sxs-lookup"><span data-stu-id="ebe17-173">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="ebe17-174">Fevereiro-2021 (plataforma: 4.18.2102.3 | Mecanismo: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="ebe17-174">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="ebe17-175">&ensp;Versão de atualização de inteligência de segurança: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-175">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="ebe17-176">&ensp;Lançado: **9 de março de 2021**</span><span class="sxs-lookup"><span data-stu-id="ebe17-176">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="ebe17-177">&ensp;Plataforma: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="ebe17-177">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="ebe17-178">&ensp;Mecanismo: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="ebe17-178">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="ebe17-179">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="ebe17-179">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ebe17-180">Novidades</span><span class="sxs-lookup"><span data-stu-id="ebe17-180">What's new</span></span>

- <span data-ttu-id="ebe17-181">Recuperação aprimorada do serviço por meio [da proteção contra violações](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="ebe17-181">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="ebe17-182">Estender escopo de proteção contra violações</span><span class="sxs-lookup"><span data-stu-id="ebe17-182">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="ebe17-183">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="ebe17-183">Known Issues</span></span>
<span data-ttu-id="ebe17-184">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="ebe17-184">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ebe17-185">Janeiro-2021 (Plataforma: 4.18.2101.9 | Mecanismo: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="ebe17-185">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="ebe17-186">&ensp;Versão de atualização de inteligência de segurança: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-186">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="ebe17-187">&ensp;Lançado: **2 de fevereiro de 2021**</span><span class="sxs-lookup"><span data-stu-id="ebe17-187">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="ebe17-188">&ensp;Plataforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="ebe17-188">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="ebe17-189">&ensp;Mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="ebe17-189">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="ebe17-190">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="ebe17-190">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ebe17-191">Novidades</span><span class="sxs-lookup"><span data-stu-id="ebe17-191">What's new</span></span>

- <span data-ttu-id="ebe17-192">Melhorias na detecção de exploração de shellcode</span><span class="sxs-lookup"><span data-stu-id="ebe17-192">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="ebe17-193">Maior visibilidade para tentativas de roubo de credenciais</span><span class="sxs-lookup"><span data-stu-id="ebe17-193">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="ebe17-194">Melhorias nos recursos anti-amperes em serviços Microsoft Defender Antivírus serviços</span><span class="sxs-lookup"><span data-stu-id="ebe17-194">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="ebe17-195">Suporte aprimorado para ARM emulação x64</span><span class="sxs-lookup"><span data-stu-id="ebe17-195">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="ebe17-196">Correção: EDR a notificação de bloqueio permanece no histórico de ameaças depois que a proteção em tempo real realizou a detecção inicial</span><span class="sxs-lookup"><span data-stu-id="ebe17-196">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="ebe17-197">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="ebe17-197">Known Issues</span></span>
<span data-ttu-id="ebe17-198">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="ebe17-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ebe17-199">Novembro-2020 (Plataforma: 4.18.2011.6 | Mecanismo: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="ebe17-199">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="ebe17-200">&ensp;Versão de atualização de inteligência de segurança: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-200">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="ebe17-201">&ensp;Lançado: **03 de dezembro de 2020**</span><span class="sxs-lookup"><span data-stu-id="ebe17-201">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="ebe17-202">&ensp;Plataforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="ebe17-202">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="ebe17-203">&ensp;Mecanismo: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="ebe17-203">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="ebe17-204">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="ebe17-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ebe17-205">Novidades</span><span class="sxs-lookup"><span data-stu-id="ebe17-205">What's new</span></span>

- <span data-ttu-id="ebe17-206">Registro em log de suporte ao status [do SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) aprimorado</span><span class="sxs-lookup"><span data-stu-id="ebe17-206">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="ebe17-207">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="ebe17-207">Known Issues</span></span>
<span data-ttu-id="ebe17-208">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="ebe17-208">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ebe17-209">Outubro-2020 (Plataforma: 4.18.2010.7 | Mecanismo: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="ebe17-209">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="ebe17-210">&ensp;Versão de atualização de inteligência de segurança: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-210">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="ebe17-211">&ensp;Lançado: **29 de outubro de 2020**</span><span class="sxs-lookup"><span data-stu-id="ebe17-211">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="ebe17-212">&ensp;Plataforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="ebe17-212">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="ebe17-213">&ensp;Mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ebe17-213">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="ebe17-214">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="ebe17-214">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ebe17-215">Novidades</span><span class="sxs-lookup"><span data-stu-id="ebe17-215">What's new</span></span>

- <span data-ttu-id="ebe17-216">Novas descrições para categorias de ameaças especiais</span><span class="sxs-lookup"><span data-stu-id="ebe17-216">New descriptions for special threat categories</span></span>
- <span data-ttu-id="ebe17-217">Recursos de emulação aprimorados</span><span class="sxs-lookup"><span data-stu-id="ebe17-217">Improved emulation capabilities</span></span>
- <span data-ttu-id="ebe17-218">Recursos de permitir/bloquear endereço de host aprimorados</span><span class="sxs-lookup"><span data-stu-id="ebe17-218">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="ebe17-219">Nova opção no CSP do Defender para Ignorar a mesclação de exclusões de usuários locais</span><span class="sxs-lookup"><span data-stu-id="ebe17-219">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="ebe17-220">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="ebe17-220">Known Issues</span></span>

<span data-ttu-id="ebe17-221">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="ebe17-221">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="ebe17-222">Setembro-2020 (Plataforma: 4.18.2009.7 | Mecanismo: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="ebe17-222">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="ebe17-223">&ensp;Versão de atualização de inteligência de segurança: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-223">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="ebe17-224">&ensp;Lançado: **01 de outubro de 2020**</span><span class="sxs-lookup"><span data-stu-id="ebe17-224">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="ebe17-225">&ensp;Plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="ebe17-225">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="ebe17-226">&ensp;Mecanismo: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="ebe17-226">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="ebe17-227">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="ebe17-227">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ebe17-228">Novidades</span><span class="sxs-lookup"><span data-stu-id="ebe17-228">What's new</span></span>

- <span data-ttu-id="ebe17-229">Permissões de administrador são necessárias para restaurar arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="ebe17-229">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="ebe17-230">Eventos formatados xml agora são suportados</span><span class="sxs-lookup"><span data-stu-id="ebe17-230">XML formatted events are now supported</span></span>
- <span data-ttu-id="ebe17-231">Suporte a CSP para ignorar mesclações de exclusão</span><span class="sxs-lookup"><span data-stu-id="ebe17-231">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="ebe17-232">Novas interfaces de gerenciamento para:</span><span class="sxs-lookup"><span data-stu-id="ebe17-232">New management interfaces for:</span></span>
   - <span data-ttu-id="ebe17-233">Inspeção UDP</span><span class="sxs-lookup"><span data-stu-id="ebe17-233">UDP Inspection</span></span>
   - <span data-ttu-id="ebe17-234">Proteção de Rede no Server 2019</span><span class="sxs-lookup"><span data-stu-id="ebe17-234">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="ebe17-235">Exclusões de endereço IP para Proteção de Rede</span><span class="sxs-lookup"><span data-stu-id="ebe17-235">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="ebe17-236">Visibilidade aprimorada nas medições do TPM</span><span class="sxs-lookup"><span data-stu-id="ebe17-236">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="ebe17-237">Verificação aprimorada Office módulo VBA</span><span class="sxs-lookup"><span data-stu-id="ebe17-237">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="ebe17-238">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="ebe17-238">Known Issues</span></span>

<span data-ttu-id="ebe17-239">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="ebe17-239">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="ebe17-240">Agosto-2020 (plataforma: 4.18.2008.9 | Mecanismo: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="ebe17-240">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="ebe17-241">&ensp;Versão de atualização de inteligência de segurança: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-241">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="ebe17-242">&ensp;Lançado: **27 de agosto de 2020**</span><span class="sxs-lookup"><span data-stu-id="ebe17-242">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="ebe17-243">&ensp;Plataforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="ebe17-243">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="ebe17-244">&ensp;Mecanismo: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="ebe17-244">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="ebe17-245">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="ebe17-245">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="ebe17-246">Novidades</span><span class="sxs-lookup"><span data-stu-id="ebe17-246">What's new</span></span>

- <span data-ttu-id="ebe17-247">Adicionar mais eventos de telemetria</span><span class="sxs-lookup"><span data-stu-id="ebe17-247">Add more telemetry events</span></span>
- <span data-ttu-id="ebe17-248">Telemetria de eventos de verificação aprimorada</span><span class="sxs-lookup"><span data-stu-id="ebe17-248">Improved scan event telemetry</span></span>
- <span data-ttu-id="ebe17-249">Monitoramento de comportamento aprimorado para verificações de memória</span><span class="sxs-lookup"><span data-stu-id="ebe17-249">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="ebe17-250">Verificação de fluxos de macros aprimorados</span><span class="sxs-lookup"><span data-stu-id="ebe17-250">Improved macro streams scanning</span></span>
- <span data-ttu-id="ebe17-251">Adicionado `AMRunningMode` ao cmdlet Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="ebe17-251">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="ebe17-252">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) é ignorado.</span><span class="sxs-lookup"><span data-stu-id="ebe17-252">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="ebe17-253">Microsoft Defender Antivírus se desliga automaticamente quando detecta outro programa antivírus.</span><span class="sxs-lookup"><span data-stu-id="ebe17-253">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="ebe17-254">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="ebe17-254">Known Issues</span></span>
<span data-ttu-id="ebe17-255">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="ebe17-255">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ebe17-256">Julho-2020 (Plataforma: 4.18.2007.8 | Mecanismo: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="ebe17-256">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="ebe17-257">&ensp;Versão de atualização de inteligência de segurança: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-257">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="ebe17-258">&ensp;Lançado: **28 de julho de 2020**</span><span class="sxs-lookup"><span data-stu-id="ebe17-258">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="ebe17-259">&ensp;Plataforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="ebe17-259">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="ebe17-260">&ensp;Mecanismo: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="ebe17-260">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="ebe17-261">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="ebe17-261">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ebe17-262">Novidades</span><span class="sxs-lookup"><span data-stu-id="ebe17-262">What's new</span></span>

- <span data-ttu-id="ebe17-263">Telemetria aprimorada para BITS</span><span class="sxs-lookup"><span data-stu-id="ebe17-263">Improved telemetry for BITS</span></span>
- <span data-ttu-id="ebe17-264">Validação aprimorada de certificado de assinatura de código Authenticode</span><span class="sxs-lookup"><span data-stu-id="ebe17-264">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="ebe17-265">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="ebe17-265">Known Issues</span></span>
<span data-ttu-id="ebe17-266">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="ebe17-266">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ebe17-267">Junho-2020 (Plataforma: 4.18.2006.10 | Mecanismo: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="ebe17-267">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="ebe17-268">&ensp;Versão de atualização de inteligência de segurança: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-268">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="ebe17-269">&ensp;Lançado: **22 de junho de 2020**</span><span class="sxs-lookup"><span data-stu-id="ebe17-269">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="ebe17-270">&ensp;Plataforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="ebe17-270">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="ebe17-271">&ensp;Mecanismo: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="ebe17-271">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="ebe17-272">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="ebe17-272">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ebe17-273">Novidades</span><span class="sxs-lookup"><span data-stu-id="ebe17-273">What's new</span></span>

- <span data-ttu-id="ebe17-274">Possibilidade de especificar o [local dos logs de suporte](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="ebe17-274">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="ebe17-275">Ignorar a verificação de captura agressiva no modo Passivo.</span><span class="sxs-lookup"><span data-stu-id="ebe17-275">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="ebe17-276">Permitir que o Defender atualize em conexões com metros</span><span class="sxs-lookup"><span data-stu-id="ebe17-276">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="ebe17-277">Ajuste de desempenho fixo quando o cache está desabilitado</span><span class="sxs-lookup"><span data-stu-id="ebe17-277">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="ebe17-278">Consulta de registro fixa</span><span class="sxs-lookup"><span data-stu-id="ebe17-278">Fixed registry query</span></span> 
- <span data-ttu-id="ebe17-279">Randomização de tempo de verificação fixa no ADMX</span><span class="sxs-lookup"><span data-stu-id="ebe17-279">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="ebe17-280">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="ebe17-280">Known Issues</span></span>
<span data-ttu-id="ebe17-281">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="ebe17-281">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ebe17-282">Maio-2020 (plataforma: 4.18.2005.4 | Mecanismo: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="ebe17-282">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="ebe17-283">&ensp;Versão de atualização de inteligência de segurança: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-283">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="ebe17-284">&ensp;Lançado: **26 de maio de 2020**</span><span class="sxs-lookup"><span data-stu-id="ebe17-284">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="ebe17-285">&ensp;Plataforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="ebe17-285">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="ebe17-286">&ensp;Mecanismo: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="ebe17-286">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="ebe17-287">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="ebe17-287">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ebe17-288">Novidades</span><span class="sxs-lookup"><span data-stu-id="ebe17-288">What's new</span></span>

- <span data-ttu-id="ebe17-289">Registro em log aprimorado para eventos de verificação</span><span class="sxs-lookup"><span data-stu-id="ebe17-289">Improved logging for scan events</span></span>
- <span data-ttu-id="ebe17-290">Melhor tratamento de falhas no modo de usuário.</span><span class="sxs-lookup"><span data-stu-id="ebe17-290">Improved user mode crash handling.</span></span>
- <span data-ttu-id="ebe17-291">Rastreamento de eventos adicionado para proteção contra adulteração</span><span class="sxs-lookup"><span data-stu-id="ebe17-291">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="ebe17-292">Envio de amostra AMSI corrigido</span><span class="sxs-lookup"><span data-stu-id="ebe17-292">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="ebe17-293">Bloqueio fixo da nuvem AMSI</span><span class="sxs-lookup"><span data-stu-id="ebe17-293">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="ebe17-294">Log de instalação de atualização de segurança fixa</span><span class="sxs-lookup"><span data-stu-id="ebe17-294">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="ebe17-295">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="ebe17-295">Known Issues</span></span>
<span data-ttu-id="ebe17-296">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="ebe17-296">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ebe17-297">Abril-2020 (Plataforma: 4.18.2004.6 | Mecanismo: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="ebe17-297">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="ebe17-298">&ensp;Versão de atualização de inteligência de segurança: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-298">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="ebe17-299">&ensp;Lançado: **30 de abril de 2020**</span><span class="sxs-lookup"><span data-stu-id="ebe17-299">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="ebe17-300">&ensp;Plataforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="ebe17-300">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="ebe17-301">&ensp;Mecanismo: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="ebe17-301">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="ebe17-302">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="ebe17-302">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ebe17-303">Novidades</span><span class="sxs-lookup"><span data-stu-id="ebe17-303">What's new</span></span>
- <span data-ttu-id="ebe17-304">Melhorias do WDfilter</span><span class="sxs-lookup"><span data-stu-id="ebe17-304">WDfilter improvements</span></span>
- <span data-ttu-id="ebe17-305">Adicionar mais dados de evento acionáveis para atacar eventos de detecção de redução de superfície</span><span class="sxs-lookup"><span data-stu-id="ebe17-305">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="ebe17-306">Informações de versão fixas em dados de diagnóstico e WMI</span><span class="sxs-lookup"><span data-stu-id="ebe17-306">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="ebe17-307">Versão da plataforma incorreta corrigida na interface do usuário após a atualização da plataforma</span><span class="sxs-lookup"><span data-stu-id="ebe17-307">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="ebe17-308">Intel de URL dinâmica para proteção contra ameaças sem arquivo</span><span class="sxs-lookup"><span data-stu-id="ebe17-308">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="ebe17-309">Recurso de verificação UEFI</span><span class="sxs-lookup"><span data-stu-id="ebe17-309">UEFI scan capability</span></span>
- <span data-ttu-id="ebe17-310">Estender o log para atualizações</span><span class="sxs-lookup"><span data-stu-id="ebe17-310">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="ebe17-311">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="ebe17-311">Known Issues</span></span>
<span data-ttu-id="ebe17-312">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="ebe17-312">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="ebe17-313">Março-2020 (Plataforma: 4.18.2003.8 | Mecanismo: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="ebe17-313">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="ebe17-314">&ensp;Versão de atualização de inteligência de segurança: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-314">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="ebe17-315">&ensp;Lançado: **24 de março de 2020**</span><span class="sxs-lookup"><span data-stu-id="ebe17-315">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="ebe17-316">&ensp;Plataforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="ebe17-316">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="ebe17-317">&ensp;Mecanismo: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="ebe17-317">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="ebe17-318">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="ebe17-318">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="ebe17-319">Novidades</span><span class="sxs-lookup"><span data-stu-id="ebe17-319">What's new</span></span>

- <span data-ttu-id="ebe17-320">Opção de throttling de CPU adicionada ao [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="ebe17-320">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="ebe17-321">Melhorar a funcionalidade de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ebe17-321">Improve diagnostic capability</span></span>
- <span data-ttu-id="ebe17-322">reduzir o tempo de tempo de inteligência de segurança (5 minutos)</span><span class="sxs-lookup"><span data-stu-id="ebe17-322">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="ebe17-323">Estender a funcionalidade de log interno do mecanismo AMSI</span><span class="sxs-lookup"><span data-stu-id="ebe17-323">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="ebe17-324">Melhorar a notificação para bloqueio de processos</span><span class="sxs-lookup"><span data-stu-id="ebe17-324">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="ebe17-325">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="ebe17-325">Known Issues</span></span>
<span data-ttu-id="ebe17-326">[**Fixo**] Microsoft Defender Antivírus está ignorando arquivos ao executar uma verificação.</span><span class="sxs-lookup"><span data-stu-id="ebe17-326">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="ebe17-327">Fevereiro-2020 (Plataforma: - | Mecanismo: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="ebe17-327">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="ebe17-328">&ensp;Versão de atualização de inteligência de segurança: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="ebe17-328">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="ebe17-329">&ensp;Lançado: **25 de fevereiro de 2020**</span><span class="sxs-lookup"><span data-stu-id="ebe17-329">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="ebe17-330">&ensp;Plataforma/Cliente: **-**</span><span class="sxs-lookup"><span data-stu-id="ebe17-330">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="ebe17-331">&ensp;Mecanismo: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="ebe17-331">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="ebe17-332">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="ebe17-332">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="ebe17-333">Novidades</span><span class="sxs-lookup"><span data-stu-id="ebe17-333">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="ebe17-334">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="ebe17-334">Known Issues</span></span>
<span data-ttu-id="ebe17-335">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="ebe17-335">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="ebe17-336">Janeiro-2020 (Plataforma: 4.18.2001.10 | Mecanismo: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="ebe17-336">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="ebe17-337">Versão de atualização de inteligência de segurança: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-337">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="ebe17-338">Lançado: **30 de janeiro de 2020**</span><span class="sxs-lookup"><span data-stu-id="ebe17-338">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="ebe17-339">Plataforma/Cliente: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="ebe17-339">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="ebe17-340">Mecanismo: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="ebe17-340">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="ebe17-341">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="ebe17-341">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="ebe17-342">Novidades</span><span class="sxs-lookup"><span data-stu-id="ebe17-342">What's new</span></span>

- <span data-ttu-id="ebe17-343">BSOD fixo no WS2016 com Exchange</span><span class="sxs-lookup"><span data-stu-id="ebe17-343">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="ebe17-344">Atualizações da plataforma de suporte quando o TMP é redirecionado para o caminho da rede</span><span class="sxs-lookup"><span data-stu-id="ebe17-344">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="ebe17-345">As versões de plataforma e mecanismo são [adicionadas ao WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="ebe17-345">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="ebe17-346">estender a atualização de assinatura de emergência para [o modo passivo](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="ebe17-346">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="ebe17-347">Corrigir trava 4.18.1911.3</span><span class="sxs-lookup"><span data-stu-id="ebe17-347">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="ebe17-348">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="ebe17-348">Known Issues</span></span>

<span data-ttu-id="ebe17-349">[**Fixo**] dispositivos [que](/windows-hardware/design/device-experiences/modern-standby) usam o modo de espera moderno podem ter uma trava com o driver de filtro Windows Defender que resulta em uma lacuna de proteção.</span><span class="sxs-lookup"><span data-stu-id="ebe17-349">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="ebe17-350">Os máquinas afetados aparecem para o cliente como não atualizados para a plataforma antimalware mais recente.</span><span class="sxs-lookup"><span data-stu-id="ebe17-350">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="ebe17-351">Esta atualização é:</span><span class="sxs-lookup"><span data-stu-id="ebe17-351">This update is:</span></span>
> - <span data-ttu-id="ebe17-352">necessário por dispositivos RS1 que executam a versão inferior da plataforma para dar suporte ao SHA2;</span><span class="sxs-lookup"><span data-stu-id="ebe17-352">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="ebe17-353">tem um sinalizador de reinicialização para sistemas que têm problemas de suspensão;</span><span class="sxs-lookup"><span data-stu-id="ebe17-353">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="ebe17-354">é re-lançado em abril de 2020 e não será superada por atualizações mais novas para manter a disponibilidade futura;</span><span class="sxs-lookup"><span data-stu-id="ebe17-354">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="ebe17-355">é categorizado como uma atualização devido ao requisito de reinicialização; e</span><span class="sxs-lookup"><span data-stu-id="ebe17-355">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="ebe17-356">só será oferecido com o [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="ebe17-356">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="ebe17-357">Novembro-2019 (plataforma: 4.18.1911.3 | Mecanismo: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="ebe17-357">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="ebe17-358">Versão de atualização de inteligência de segurança: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-358">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="ebe17-359">Lançado: **7 de dezembro de 2019**</span><span class="sxs-lookup"><span data-stu-id="ebe17-359">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="ebe17-360">Plataforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="ebe17-360">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="ebe17-361">Mecanismo: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="ebe17-361">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="ebe17-362">Fase de suporte: **sem suporte**</span><span class="sxs-lookup"><span data-stu-id="ebe17-362">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="ebe17-363">Novidades</span><span class="sxs-lookup"><span data-stu-id="ebe17-363">What's new</span></span>

- <span data-ttu-id="ebe17-364">Nível de rastreamento De MpCmdRun fixo</span><span class="sxs-lookup"><span data-stu-id="ebe17-364">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="ebe17-365">Informações de versão fixas do WDFilter</span><span class="sxs-lookup"><span data-stu-id="ebe17-365">Fixed WDFilter version info</span></span>
- <span data-ttu-id="ebe17-366">Melhorar notificações (PUA)</span><span class="sxs-lookup"><span data-stu-id="ebe17-366">Improve notifications (PUA)</span></span>
- <span data-ttu-id="ebe17-367">adicionar logs MRT para dar suporte a arquivos</span><span class="sxs-lookup"><span data-stu-id="ebe17-367">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="ebe17-368">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="ebe17-368">Known Issues</span></span>
<span data-ttu-id="ebe17-369">Quando essa atualização é instalada, o dispositivo precisa do pacote de salto 4.10.2001.10 para poder atualizar para a versão mais recente da plataforma.</span><span class="sxs-lookup"><span data-stu-id="ebe17-369">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="ebe17-370">Microsoft Defender Antivírus plataforma</span><span class="sxs-lookup"><span data-stu-id="ebe17-370">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="ebe17-371">As atualizações de plataforma e mecanismo são fornecidas em uma cadência mensal.</span><span class="sxs-lookup"><span data-stu-id="ebe17-371">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="ebe17-372">Para ter suporte total, mantenha-se atualizado com as atualizações mais recentes da plataforma.</span><span class="sxs-lookup"><span data-stu-id="ebe17-372">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="ebe17-373">Nossa estrutura de suporte é dinâmica, evoluindo em duas fases, dependendo da disponibilidade da versão mais recente da plataforma:</span><span class="sxs-lookup"><span data-stu-id="ebe17-373">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="ebe17-374">Fase de manutenção de Atualizações **Críticas** e Segurança - Ao executar a versão mais recente da plataforma, você estará qualificado para receber atualizações de segurança e críticas para a plataforma anti-malware.</span><span class="sxs-lookup"><span data-stu-id="ebe17-374">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="ebe17-375">Fase de Suporte Técnico **(Somente)** - Depois que uma nova versão da plataforma for lançada, o suporte para versões mais antigas (N-2) será redução apenas para suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="ebe17-375">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="ebe17-376">As versões da plataforma anteriores ao N-2 não serão mais suportadas.\*</span><span class="sxs-lookup"><span data-stu-id="ebe17-376">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="ebe17-377">\*O suporte técnico continuará a ser fornecido para atualizações da versão Windows 10 versão do Windows 10 (consulte Versão da plataforma incluída com Windows 10 [versões](#platform-version-included-with-windows-10-releases)) para a versão mais recente da plataforma.</span><span class="sxs-lookup"><span data-stu-id="ebe17-377">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="ebe17-378">Durante a fase de suporte técnico (somente), incidentes de suporte comercialmente razoáveis serão fornecidos por meio do Serviço de Atendimento ao Cliente da Microsoft & Suporte e ofertas de suporte gerenciado da Microsoft (como o Suporte Premier).</span><span class="sxs-lookup"><span data-stu-id="ebe17-378">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="ebe17-379">Se um incidente de suporte exigir escalonamento para desenvolvimento para obter mais orientações, exigir uma atualização que não seja de segurança ou exigir uma atualização de segurança, os clientes serão solicitados a atualizar para a versão mais recente da plataforma ou uma atualização intermediária (\*).</span><span class="sxs-lookup"><span data-stu-id="ebe17-379">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="ebe17-380">Versão da plataforma incluída com Windows 10 versões</span><span class="sxs-lookup"><span data-stu-id="ebe17-380">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="ebe17-381">A tabela a seguir fornece as versões Microsoft Defender Antivírus plataforma e mecanismo que são enviadas com as versões Windows 10 versão mais recentes:</span><span class="sxs-lookup"><span data-stu-id="ebe17-381">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="ebe17-382">Windows 10 versão</span><span class="sxs-lookup"><span data-stu-id="ebe17-382">Windows 10 release</span></span>  |<span data-ttu-id="ebe17-383">Versão da plataforma</span><span class="sxs-lookup"><span data-stu-id="ebe17-383">Platform version</span></span>  |<span data-ttu-id="ebe17-384">Versão do mecanismo</span><span class="sxs-lookup"><span data-stu-id="ebe17-384">Engine version</span></span> |<span data-ttu-id="ebe17-385">Fase de suporte</span><span class="sxs-lookup"><span data-stu-id="ebe17-385">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="ebe17-386">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="ebe17-386">2004  (20H1/20H2)</span></span> |<span data-ttu-id="ebe17-387">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="ebe17-387">4.18.1909.6</span></span> |<span data-ttu-id="ebe17-388">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="ebe17-388">1.1.17000.2</span></span> | <span data-ttu-id="ebe17-389">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="ebe17-389">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ebe17-390">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="ebe17-390">1909  (19H2)</span></span> |<span data-ttu-id="ebe17-391">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="ebe17-391">4.18.1902.5</span></span> |<span data-ttu-id="ebe17-392">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="ebe17-392">1.1.16700.3</span></span> | <span data-ttu-id="ebe17-393">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="ebe17-393">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ebe17-394">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="ebe17-394">1903  (19H1)</span></span> |<span data-ttu-id="ebe17-395">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="ebe17-395">4.18.1902.5</span></span> |<span data-ttu-id="ebe17-396">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="ebe17-396">1.1.15600.4</span></span> | <span data-ttu-id="ebe17-397">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="ebe17-397">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ebe17-398">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="ebe17-398">1809  (RS5)</span></span> |<span data-ttu-id="ebe17-399">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="ebe17-399">4.18.1807.18075</span></span> |<span data-ttu-id="ebe17-400">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="ebe17-400">1.1.15000.2</span></span> | <span data-ttu-id="ebe17-401">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="ebe17-401">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ebe17-402">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="ebe17-402">1803  (RS4)</span></span> |<span data-ttu-id="ebe17-403">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="ebe17-403">4.13.17134.1</span></span> |<span data-ttu-id="ebe17-404">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="ebe17-404">1.1.14600.4</span></span> | <span data-ttu-id="ebe17-405">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="ebe17-405">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ebe17-406">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="ebe17-406">1709  (RS3)</span></span> |<span data-ttu-id="ebe17-407">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="ebe17-407">4.12.16299.15</span></span> |<span data-ttu-id="ebe17-408">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="ebe17-408">1.1.14104.0</span></span> | <span data-ttu-id="ebe17-409">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="ebe17-409">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ebe17-410">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="ebe17-410">1703  (RS2)</span></span> |<span data-ttu-id="ebe17-411">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="ebe17-411">4.11.15603.2</span></span> |<span data-ttu-id="ebe17-412">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="ebe17-412">1.1.13504.0</span></span> | <span data-ttu-id="ebe17-413">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="ebe17-413">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="ebe17-414">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="ebe17-414">1607 (RS1)</span></span> |<span data-ttu-id="ebe17-415">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="ebe17-415">4.10.14393.3683</span></span> |<span data-ttu-id="ebe17-416">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="ebe17-416">1.1.12805.0</span></span> | <span data-ttu-id="ebe17-417">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="ebe17-417">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="ebe17-418">Para Windows 10 informações de versão, consulte a planilha Windows de fatos do ciclo [de vida.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="ebe17-418">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="ebe17-419">Atualizações para Manutenção e Gerenciamento de Imagens de Implantação (DISM)</span><span class="sxs-lookup"><span data-stu-id="ebe17-419">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="ebe17-420">Recomendamos atualizar suas Windows 10 (Enterprise, Pro e edições Home), o Windows Server 2019 e Windows Server 2016 imagens de instalação do sistema operacional com as atualizações mais recentes de antivírus e antimalware.</span><span class="sxs-lookup"><span data-stu-id="ebe17-420">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="ebe17-421">Manter as imagens de instalação do sistema operacional atualizadas ajuda a evitar uma lacuna na proteção.</span><span class="sxs-lookup"><span data-stu-id="ebe17-421">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="ebe17-422">Para obter mais informações, consulte [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="ebe17-422">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="ebe17-423">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="ebe17-423">1.1.2106.01</span></span></summary>

<span data-ttu-id="ebe17-424">&ensp;Versão do pacote: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="ebe17-424">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="ebe17-425">&ensp;Versão da plataforma: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="ebe17-425">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="ebe17-426">&ensp;Versão do mecanismo: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="ebe17-426">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="ebe17-427">&ensp;Versão de assinatura: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-427">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ebe17-428">Correções</span><span class="sxs-lookup"><span data-stu-id="ebe17-428">Fixes</span></span>
- <span data-ttu-id="ebe17-429">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ebe17-429">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ebe17-430">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="ebe17-430">Additional information</span></span>
- <span data-ttu-id="ebe17-431">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ebe17-431">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ebe17-432">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="ebe17-432">1.1.2105.01</span></span></summary>

<span data-ttu-id="ebe17-433">&ensp;Versão do pacote: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="ebe17-433">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="ebe17-434">&ensp;Versão da plataforma: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="ebe17-434">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="ebe17-435">&ensp;Versão do mecanismo: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="ebe17-435">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="ebe17-436">&ensp;Versão de assinatura: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-436">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ebe17-437">Correções</span><span class="sxs-lookup"><span data-stu-id="ebe17-437">Fixes</span></span>
- <span data-ttu-id="ebe17-438">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ebe17-438">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ebe17-439">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="ebe17-439">Additional information</span></span>
- <span data-ttu-id="ebe17-440">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ebe17-440">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ebe17-441">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="ebe17-441">1.1.2104.01</span></span></summary>

<span data-ttu-id="ebe17-442">&ensp;Versão do pacote: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="ebe17-442">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="ebe17-443">&ensp;Versão da plataforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="ebe17-443">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="ebe17-444">&ensp;Versão do mecanismo: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="ebe17-444">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="ebe17-445">&ensp;Versão de assinatura: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-445">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ebe17-446">Correções</span><span class="sxs-lookup"><span data-stu-id="ebe17-446">Fixes</span></span>
- <span data-ttu-id="ebe17-447">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ebe17-447">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ebe17-448">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="ebe17-448">Additional information</span></span>
- <span data-ttu-id="ebe17-449">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ebe17-449">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ebe17-450">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="ebe17-450">1.1.2103.01</span></span></summary>

<span data-ttu-id="ebe17-451">&ensp;Versão do pacote: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="ebe17-451">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="ebe17-452">&ensp;Versão da plataforma: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="ebe17-452">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="ebe17-453">&ensp;Versão do mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="ebe17-453">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="ebe17-454">&ensp;Versão de assinatura: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-454">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ebe17-455">Correções</span><span class="sxs-lookup"><span data-stu-id="ebe17-455">Fixes</span></span>
- <span data-ttu-id="ebe17-456">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ebe17-456">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ebe17-457">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="ebe17-457">Additional information</span></span>
- <span data-ttu-id="ebe17-458">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ebe17-458">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ebe17-459">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="ebe17-459">1.1.2102.03</span></span></summary>

<span data-ttu-id="ebe17-460">&ensp;Versão do pacote: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="ebe17-460">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="ebe17-461">&ensp;Versão da plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="ebe17-461">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="ebe17-462">&ensp;Versão do mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="ebe17-462">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="ebe17-463">&ensp;Versão de assinatura: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-463">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ebe17-464">Correções</span><span class="sxs-lookup"><span data-stu-id="ebe17-464">Fixes</span></span>
- <span data-ttu-id="ebe17-465">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ebe17-465">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ebe17-466">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="ebe17-466">Additional information</span></span>
- <span data-ttu-id="ebe17-467">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ebe17-467">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ebe17-468">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="ebe17-468">1.1.2101.02</span></span></summary>

<span data-ttu-id="ebe17-469">&ensp;Versão do pacote: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="ebe17-469">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="ebe17-470">&ensp;Versão da plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="ebe17-470">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="ebe17-471">&ensp;Versão do mecanismo: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="ebe17-471">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="ebe17-472">&ensp;Versão de assinatura: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-472">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ebe17-473">Correções</span><span class="sxs-lookup"><span data-stu-id="ebe17-473">Fixes</span></span>
- <span data-ttu-id="ebe17-474">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ebe17-474">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ebe17-475">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="ebe17-475">Additional information</span></span>
- <span data-ttu-id="ebe17-476">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ebe17-476">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ebe17-477">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="ebe17-477">1.1.2012.01</span></span></summary>

<span data-ttu-id="ebe17-478">&ensp;Versão do pacote: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="ebe17-478">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="ebe17-479">&ensp;Versão da plataforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="ebe17-479">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="ebe17-480">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ebe17-480">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="ebe17-481">&ensp;Versão de assinatura: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-481">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ebe17-482">Correções</span><span class="sxs-lookup"><span data-stu-id="ebe17-482">Fixes</span></span>
- <span data-ttu-id="ebe17-483">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ebe17-483">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ebe17-484">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="ebe17-484">Additional information</span></span>
- <span data-ttu-id="ebe17-485">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ebe17-485">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ebe17-486">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="ebe17-486">1.1.2011.02</span></span></summary>

<span data-ttu-id="ebe17-487">&ensp;Versão do pacote: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="ebe17-487">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="ebe17-488">&ensp;Versão da plataforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="ebe17-488">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="ebe17-489">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ebe17-489">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="ebe17-490">&ensp;Versão de assinatura: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-490">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ebe17-491">Correções</span><span class="sxs-lookup"><span data-stu-id="ebe17-491">Fixes</span></span>
- <span data-ttu-id="ebe17-492">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ebe17-492">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ebe17-493">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="ebe17-493">Additional information</span></span>
- <span data-ttu-id="ebe17-494">Assinaturas Microsoft Defender Antivírus atualizadas</span><span class="sxs-lookup"><span data-stu-id="ebe17-494">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ebe17-495">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="ebe17-495">1.1.2011.01</span></span></summary>

<span data-ttu-id="ebe17-496">&ensp;Versão do pacote: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="ebe17-496">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="ebe17-497">&ensp;Versão da plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="ebe17-497">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="ebe17-498">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="ebe17-498">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="ebe17-499">&ensp;Versão de assinatura: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-499">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ebe17-500">Correções</span><span class="sxs-lookup"><span data-stu-id="ebe17-500">Fixes</span></span>
- <span data-ttu-id="ebe17-501">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ebe17-501">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ebe17-502">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="ebe17-502">Additional information</span></span>
- <span data-ttu-id="ebe17-503">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ebe17-503">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="ebe17-504">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="ebe17-504">1.1.2009.10</span></span></summary>

<span data-ttu-id="ebe17-505">&ensp;Versão do pacote: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="ebe17-505">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="ebe17-506">&ensp;Versão da plataforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="ebe17-506">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="ebe17-507">&ensp;Versão do mecanismo: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="ebe17-507">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="ebe17-508">&ensp;Versão de assinatura: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="ebe17-508">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="ebe17-509">Correções</span><span class="sxs-lookup"><span data-stu-id="ebe17-509">Fixes</span></span>
- <span data-ttu-id="ebe17-510">Nenhuma</span><span class="sxs-lookup"><span data-stu-id="ebe17-510">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="ebe17-511">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="ebe17-511">Additional information</span></span>
- <span data-ttu-id="ebe17-512">Adicionado suporte para Windows 10 RS1 ou imagens de instalação posteriores do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="ebe17-512">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="ebe17-513">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ebe17-513">Additional resources</span></span>

| <span data-ttu-id="ebe17-514">Artigo</span><span class="sxs-lookup"><span data-stu-id="ebe17-514">Article</span></span> | <span data-ttu-id="ebe17-515">Descrição</span><span class="sxs-lookup"><span data-stu-id="ebe17-515">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="ebe17-516">Atualização do Microsoft Defender para Windows de instalação do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="ebe17-516">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="ebe17-517">Revise os pacotes de atualização antimalware para as imagens de instalação do sistema operacional (arquivos WIM e VHD).</span><span class="sxs-lookup"><span data-stu-id="ebe17-517">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="ebe17-518">Obter Microsoft Defender Antivírus atualizações para Windows 10 (Enterprise, Pro e edições Home), Windows Server 2019 e Windows Server 2016 de instalação.</span><span class="sxs-lookup"><span data-stu-id="ebe17-518">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="ebe17-519">Gerenciar como as atualizações de proteção são baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="ebe17-519">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="ebe17-520">As atualizações de proteção podem ser entregues por meio de várias fontes.</span><span class="sxs-lookup"><span data-stu-id="ebe17-520">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="ebe17-521">Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="ebe17-521">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="ebe17-522">Você pode agendar quando as atualizações de proteção devem ser baixadas.</span><span class="sxs-lookup"><span data-stu-id="ebe17-522">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="ebe17-523">Gerenciar atualizações para pontos de extremidade que estão des date</span><span class="sxs-lookup"><span data-stu-id="ebe17-523">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="ebe17-524">Se um ponto de extremidade perder uma atualização ou uma verificação agendada, você poderá forçar uma atualização ou verificar na próxima vez que um usuário entrar.</span><span class="sxs-lookup"><span data-stu-id="ebe17-524">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="ebe17-525">Gerenciar atualizações aplicadas com base em evento</span><span class="sxs-lookup"><span data-stu-id="ebe17-525">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="ebe17-526">Você pode definir atualizações de proteção a serem baixadas na inicialização ou após determinados eventos de proteção entregues na nuvem.</span><span class="sxs-lookup"><span data-stu-id="ebe17-526">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="ebe17-527">Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)</span><span class="sxs-lookup"><span data-stu-id="ebe17-527">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="ebe17-528">Você pode especificar configurações, como se as atualizações devem ocorrer na energia da bateria, que são especialmente úteis para dispositivos móveis e máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="ebe17-528">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
