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
ms.date: 06/08/2021
ms.openlocfilehash: ccbb57d781196e352e0fed456a1f7cb43eb17300
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822269"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="18dee-104">Gerenciar Microsoft Defender Antivírus e aplicar linhas de base</span><span class="sxs-lookup"><span data-stu-id="18dee-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="18dee-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="18dee-105">**Applies to:**</span></span>

- [<span data-ttu-id="18dee-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="18dee-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="18dee-107">Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="18dee-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="18dee-108">Há dois tipos de atualizações relacionadas à Microsoft Defender Antivírus atualizadas:</span><span class="sxs-lookup"><span data-stu-id="18dee-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="18dee-109">Atualizações de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="18dee-109">Security intelligence updates</span></span>
- <span data-ttu-id="18dee-110">Atualizações de produtos</span><span class="sxs-lookup"><span data-stu-id="18dee-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18dee-111">Manter Microsoft Defender Antivírus atualizado é fundamental para garantir que seus dispositivos tenham a tecnologia e os recursos mais recentes necessários para proteger contra novas técnicas de malware e ataque.</span><span class="sxs-lookup"><span data-stu-id="18dee-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="18dee-112">Certifique-se de atualizar sua proteção antivírus mesmo que Microsoft Defender Antivírus está sendo executado no [modo passivo](./microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="18dee-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="18dee-113">Para ver o mecanismo, a plataforma e a data de assinatura mais atuais, visite as atualizações de inteligência de segurança para Microsoft Defender Antivírus e outros [antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18dee-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="18dee-114">Atualizações de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="18dee-114">Security intelligence updates</span></span>

<span data-ttu-id="18dee-115">Microsoft Defender Antivírus usa [proteção](cloud-protection-microsoft-defender-antivirus.md) entregue na nuvem (também chamada de Serviço de Proteção Avançada da Microsoft ou MAPS) e baixa periodicamente atualizações de inteligência de segurança para fornecer proteção.</span><span class="sxs-lookup"><span data-stu-id="18dee-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="18dee-116">As atualizações são lançadas nos números KB abaixo:</span><span class="sxs-lookup"><span data-stu-id="18dee-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="18dee-117">Microsoft Defender Antivírus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="18dee-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="18dee-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="18dee-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="18dee-119">A proteção entregue na nuvem está sempre ativa e requer uma conexão ativa com a Internet para funcionar.</span><span class="sxs-lookup"><span data-stu-id="18dee-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="18dee-120">As atualizações de inteligência de segurança ocorrem em uma cadência agendada (configurável por meio da política).</span><span class="sxs-lookup"><span data-stu-id="18dee-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="18dee-121">Para obter mais informações, [consulte Use Microsoft cloud-provided protection in Microsoft Defender Antivírus](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="18dee-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="18dee-122">Para ver uma lista de atualizações recentes de inteligência de segurança, consulte Atualizações de inteligência de segurança para Microsoft Defender Antivírus [e outros antimalware da Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="18dee-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="18dee-123">As atualizações do mecanismo são incluídas com atualizações de inteligência de segurança e são lançadas em uma cadência mensal.</span><span class="sxs-lookup"><span data-stu-id="18dee-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="18dee-124">Atualizações de produtos</span><span class="sxs-lookup"><span data-stu-id="18dee-124">Product updates</span></span>

<span data-ttu-id="18dee-125">Microsoft Defender Antivírus exige atualizações mensais [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) *(conhecidas* como atualizações de plataforma) e receberá atualizações de recursos principais juntamente com Windows 10 versões.</span><span class="sxs-lookup"><span data-stu-id="18dee-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="18dee-126">Você pode gerenciar a distribuição de atualizações por meio de um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="18dee-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="18dee-127">Windows Serviço de Atualização do Servidor (WSUS)</span><span class="sxs-lookup"><span data-stu-id="18dee-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="18dee-128">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="18dee-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="18dee-129">O método comum que você usa para implantar a Microsoft e Windows atualizações para pontos de extremidade em sua rede.</span><span class="sxs-lookup"><span data-stu-id="18dee-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="18dee-130">Para obter mais informações, consulte [Manage the sources for Microsoft Defender Antivírus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="18dee-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="18dee-131">As atualizações mensais são lançadas em fases, resultando em vários pacotes visíveis em seus [Serviços de Atualização do Servidor de Janelas.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="18dee-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="18dee-132">Versões mensais de plataforma e mecanismo</span><span class="sxs-lookup"><span data-stu-id="18dee-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="18dee-133">Para obter informações sobre como atualizar ou instalar a atualização da plataforma, consulte [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="18dee-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="18dee-134">Todas as nossas atualizações contêm</span><span class="sxs-lookup"><span data-stu-id="18dee-134">All our updates contain</span></span> 
- <span data-ttu-id="18dee-135">melhorias de desempenho;</span><span class="sxs-lookup"><span data-stu-id="18dee-135">performance improvements;</span></span>
- <span data-ttu-id="18dee-136">melhorias de capacidade de serviço; e</span><span class="sxs-lookup"><span data-stu-id="18dee-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="18dee-137">melhorias de integração (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span><span class="sxs-lookup"><span data-stu-id="18dee-137">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="18dee-138">Maio-2021 (plataforma: 4.18.2105.4 | Mecanismo: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="18dee-138">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="18dee-139">&ensp;Versão de atualização de inteligência de segurança: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-139">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="18dee-140">&ensp;Lançado: **4 de junho de 2021**</span><span class="sxs-lookup"><span data-stu-id="18dee-140">&ensp;Released: **June 4, 2021**</span></span>  
<span data-ttu-id="18dee-141">&ensp;Plataforma: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="18dee-141">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="18dee-142">&ensp;Mecanismo: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="18dee-142">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="18dee-143">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="18dee-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="18dee-144">Novidades</span><span class="sxs-lookup"><span data-stu-id="18dee-144">What's new</span></span>
- <span data-ttu-id="18dee-145">Melhorias [no monitoramento de comportamento](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="18dee-145">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="18dee-146">Recurso [de filtragem de notificação](network-protection.md) de proteção de rede fixa</span><span class="sxs-lookup"><span data-stu-id="18dee-146">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="18dee-147">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="18dee-147">Known Issues</span></span>
<span data-ttu-id="18dee-148">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="18dee-148">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="18dee-149">Abril-2021 (Plataforma: 4.18.2104.14 | Mecanismo: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="18dee-149">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="18dee-150">&ensp;Versão de atualização de inteligência de segurança: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-150">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="18dee-151">&ensp;Lançado: **1º de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="18dee-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="18dee-152">&ensp;Plataforma: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="18dee-152">&ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="18dee-153">&ensp;Mecanismo: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="18dee-153">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="18dee-154">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="18dee-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="18dee-155">Novidades</span><span class="sxs-lookup"><span data-stu-id="18dee-155">What's new</span></span>
- <span data-ttu-id="18dee-156">Lógica adicional de monitoramento de comportamento</span><span class="sxs-lookup"><span data-stu-id="18dee-156">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="18dee-157">Detecção aprimorada do keylogger do modo kernel</span><span class="sxs-lookup"><span data-stu-id="18dee-157">Improved kernel mode keylogger detection</span></span>
- <span data-ttu-id="18dee-158">Adicionados novos controles para gerenciar o processo de lançamento gradual para [atualizações do Microsoft Defender](updates.md)</span><span class="sxs-lookup"><span data-stu-id="18dee-158">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](updates.md)</span></span>

### <a name="known-issues"></a><span data-ttu-id="18dee-159">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="18dee-159">Known Issues</span></span>
<span data-ttu-id="18dee-160">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="18dee-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="18dee-161">Março-2021 (Plataforma: 4.18.2103.7 | Mecanismo: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="18dee-161">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="18dee-162">&ensp;Versão de atualização de inteligência de segurança: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-162">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="18dee-163">&ensp;Lançado: **1º de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="18dee-163">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="18dee-164">&ensp;Plataforma: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="18dee-164">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="18dee-165">&ensp;Mecanismo: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="18dee-165">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="18dee-166">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="18dee-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="18dee-167">Novidades</span><span class="sxs-lookup"><span data-stu-id="18dee-167">What's new</span></span>

- <span data-ttu-id="18dee-168">Melhoria no mecanismo de Monitoramento de Comportamento</span><span class="sxs-lookup"><span data-stu-id="18dee-168">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="18dee-169">Mitigações de ataques de força bruta de rede expandida</span><span class="sxs-lookup"><span data-stu-id="18dee-169">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="18dee-170">Geração adicional de eventos de tentativa de adulteração com falha quando [a Proteção contra Adulteração](prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada</span><span class="sxs-lookup"><span data-stu-id="18dee-170">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="18dee-171">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="18dee-171">Known Issues</span></span>
<span data-ttu-id="18dee-172">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="18dee-172">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="18dee-173">Atualizações de versão anterior: Suporte técnico somente a atualização</span><span class="sxs-lookup"><span data-stu-id="18dee-173">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="18dee-174">Depois que uma nova versão de pacote é lançada, o suporte para as duas versões anteriores é reduzido apenas ao suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="18dee-174">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="18dee-175">Versões anteriores às listadas nesta seção são fornecidas apenas para suporte técnico de atualização.</span><span class="sxs-lookup"><span data-stu-id="18dee-175">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="18dee-176">Fevereiro-2021 (plataforma: 4.18.2102.3 | Mecanismo: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="18dee-176">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="18dee-177">&ensp;Versão de atualização de inteligência de segurança: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-177">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="18dee-178">&ensp;Lançado: **9 de março de 2021**</span><span class="sxs-lookup"><span data-stu-id="18dee-178">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="18dee-179">&ensp;Plataforma: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="18dee-179">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="18dee-180">&ensp;Mecanismo: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="18dee-180">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="18dee-181">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="18dee-181">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="18dee-182">Novidades</span><span class="sxs-lookup"><span data-stu-id="18dee-182">What's new</span></span>

- <span data-ttu-id="18dee-183">Recuperação aprimorada do serviço por meio [da proteção contra violações](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="18dee-183">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="18dee-184">Estender escopo de proteção contra violações</span><span class="sxs-lookup"><span data-stu-id="18dee-184">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="18dee-185">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="18dee-185">Known Issues</span></span>
<span data-ttu-id="18dee-186">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="18dee-186">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="18dee-187">Janeiro-2021 (Plataforma: 4.18.2101.9 | Mecanismo: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="18dee-187">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="18dee-188">&ensp;Versão de atualização de inteligência de segurança: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-188">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="18dee-189">&ensp;Lançado: **2 de fevereiro de 2021**</span><span class="sxs-lookup"><span data-stu-id="18dee-189">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="18dee-190">&ensp;Plataforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="18dee-190">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="18dee-191">&ensp;Mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="18dee-191">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="18dee-192">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="18dee-192">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="18dee-193">Novidades</span><span class="sxs-lookup"><span data-stu-id="18dee-193">What's new</span></span>

- <span data-ttu-id="18dee-194">Melhorias na detecção de exploração de shellcode</span><span class="sxs-lookup"><span data-stu-id="18dee-194">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="18dee-195">Maior visibilidade para tentativas de roubo de credenciais</span><span class="sxs-lookup"><span data-stu-id="18dee-195">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="18dee-196">Melhorias nos recursos anti-amperes em serviços Microsoft Defender Antivírus serviços</span><span class="sxs-lookup"><span data-stu-id="18dee-196">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="18dee-197">Suporte aprimorado para ARM emulação x64</span><span class="sxs-lookup"><span data-stu-id="18dee-197">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="18dee-198">Correção: EDR a notificação de bloqueio permanece no histórico de ameaças depois que a proteção em tempo real realizou a detecção inicial</span><span class="sxs-lookup"><span data-stu-id="18dee-198">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="18dee-199">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="18dee-199">Known Issues</span></span>
<span data-ttu-id="18dee-200">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="18dee-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="18dee-201">Novembro-2020 (Plataforma: 4.18.2011.6 | Mecanismo: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="18dee-201">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="18dee-202">&ensp;Versão de atualização de inteligência de segurança: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-202">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="18dee-203">&ensp;Lançado: **03 de dezembro de 2020**</span><span class="sxs-lookup"><span data-stu-id="18dee-203">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="18dee-204">&ensp;Plataforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="18dee-204">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="18dee-205">&ensp;Mecanismo: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="18dee-205">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="18dee-206">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="18dee-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="18dee-207">Novidades</span><span class="sxs-lookup"><span data-stu-id="18dee-207">What's new</span></span>

- <span data-ttu-id="18dee-208">Registro em log de suporte ao status [do SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) aprimorado</span><span class="sxs-lookup"><span data-stu-id="18dee-208">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="18dee-209">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="18dee-209">Known Issues</span></span>
<span data-ttu-id="18dee-210">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="18dee-210">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="18dee-211">Outubro-2020 (Plataforma: 4.18.2010.7 | Mecanismo: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="18dee-211">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="18dee-212">&ensp;Versão de atualização de inteligência de segurança: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-212">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="18dee-213">&ensp;Lançado: **29 de outubro de 2020**</span><span class="sxs-lookup"><span data-stu-id="18dee-213">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="18dee-214">&ensp;Plataforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="18dee-214">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="18dee-215">&ensp;Mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="18dee-215">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="18dee-216">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="18dee-216">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="18dee-217">Novidades</span><span class="sxs-lookup"><span data-stu-id="18dee-217">What's new</span></span>

- <span data-ttu-id="18dee-218">Novas descrições para categorias de ameaças especiais</span><span class="sxs-lookup"><span data-stu-id="18dee-218">New descriptions for special threat categories</span></span>
- <span data-ttu-id="18dee-219">Recursos de emulação aprimorados</span><span class="sxs-lookup"><span data-stu-id="18dee-219">Improved emulation capabilities</span></span>
- <span data-ttu-id="18dee-220">Recursos de permitir/bloquear endereço de host aprimorados</span><span class="sxs-lookup"><span data-stu-id="18dee-220">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="18dee-221">Nova opção no CSP do Defender para Ignorar a mesclação de exclusões de usuários locais</span><span class="sxs-lookup"><span data-stu-id="18dee-221">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="18dee-222">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="18dee-222">Known Issues</span></span>

<span data-ttu-id="18dee-223">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="18dee-223">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="18dee-224">Setembro-2020 (Plataforma: 4.18.2009.7 | Mecanismo: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="18dee-224">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="18dee-225">&ensp;Versão de atualização de inteligência de segurança: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-225">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="18dee-226">&ensp;Lançado: **01 de outubro de 2020**</span><span class="sxs-lookup"><span data-stu-id="18dee-226">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="18dee-227">&ensp;Plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="18dee-227">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="18dee-228">&ensp;Mecanismo: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="18dee-228">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="18dee-229">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="18dee-229">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="18dee-230">Novidades</span><span class="sxs-lookup"><span data-stu-id="18dee-230">What's new</span></span>

- <span data-ttu-id="18dee-231">Permissões de administrador são necessárias para restaurar arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="18dee-231">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="18dee-232">Eventos formatados xml agora são suportados</span><span class="sxs-lookup"><span data-stu-id="18dee-232">XML formatted events are now supported</span></span>
- <span data-ttu-id="18dee-233">Suporte a CSP para ignorar mesclações de exclusão</span><span class="sxs-lookup"><span data-stu-id="18dee-233">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="18dee-234">Novas interfaces de gerenciamento para:</span><span class="sxs-lookup"><span data-stu-id="18dee-234">New management interfaces for:</span></span>
   - <span data-ttu-id="18dee-235">Inspeção UDP</span><span class="sxs-lookup"><span data-stu-id="18dee-235">UDP Inspection</span></span>
   - <span data-ttu-id="18dee-236">Proteção de Rede no Server 2019</span><span class="sxs-lookup"><span data-stu-id="18dee-236">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="18dee-237">Exclusões de endereço IP para Proteção de Rede</span><span class="sxs-lookup"><span data-stu-id="18dee-237">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="18dee-238">Visibilidade aprimorada nas medições do TPM</span><span class="sxs-lookup"><span data-stu-id="18dee-238">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="18dee-239">Verificação aprimorada Office módulo VBA</span><span class="sxs-lookup"><span data-stu-id="18dee-239">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="18dee-240">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="18dee-240">Known Issues</span></span>

<span data-ttu-id="18dee-241">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="18dee-241">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="18dee-242">Agosto-2020 (plataforma: 4.18.2008.9 | Mecanismo: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="18dee-242">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="18dee-243">&ensp;Versão de atualização de inteligência de segurança: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-243">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="18dee-244">&ensp;Lançado: **27 de agosto de 2020**</span><span class="sxs-lookup"><span data-stu-id="18dee-244">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="18dee-245">&ensp;Plataforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="18dee-245">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="18dee-246">&ensp;Mecanismo: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="18dee-246">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="18dee-247">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="18dee-247">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="18dee-248">Novidades</span><span class="sxs-lookup"><span data-stu-id="18dee-248">What's new</span></span>

- <span data-ttu-id="18dee-249">Adicionar mais eventos de telemetria</span><span class="sxs-lookup"><span data-stu-id="18dee-249">Add more telemetry events</span></span>
- <span data-ttu-id="18dee-250">Telemetria de eventos de verificação aprimorada</span><span class="sxs-lookup"><span data-stu-id="18dee-250">Improved scan event telemetry</span></span>
- <span data-ttu-id="18dee-251">Monitoramento de comportamento aprimorado para verificações de memória</span><span class="sxs-lookup"><span data-stu-id="18dee-251">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="18dee-252">Verificação de fluxos de macros aprimorados</span><span class="sxs-lookup"><span data-stu-id="18dee-252">Improved macro streams scanning</span></span>
- <span data-ttu-id="18dee-253">Adicionado `AMRunningMode` ao cmdlet Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="18dee-253">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="18dee-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) é ignorado.</span><span class="sxs-lookup"><span data-stu-id="18dee-254">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="18dee-255">Microsoft Defender Antivírus se desliga automaticamente quando detecta outro programa antivírus.</span><span class="sxs-lookup"><span data-stu-id="18dee-255">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="18dee-256">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="18dee-256">Known Issues</span></span>
<span data-ttu-id="18dee-257">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="18dee-257">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="18dee-258">Julho-2020 (Plataforma: 4.18.2007.8 | Mecanismo: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="18dee-258">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="18dee-259">&ensp;Versão de atualização de inteligência de segurança: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-259">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="18dee-260">&ensp;Lançado: **28 de julho de 2020**</span><span class="sxs-lookup"><span data-stu-id="18dee-260">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="18dee-261">&ensp;Plataforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="18dee-261">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="18dee-262">&ensp;Mecanismo: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="18dee-262">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="18dee-263">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="18dee-263">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="18dee-264">Novidades</span><span class="sxs-lookup"><span data-stu-id="18dee-264">What's new</span></span>

- <span data-ttu-id="18dee-265">Telemetria aprimorada para BITS</span><span class="sxs-lookup"><span data-stu-id="18dee-265">Improved telemetry for BITS</span></span>
- <span data-ttu-id="18dee-266">Validação aprimorada de certificado de assinatura de código Authenticode</span><span class="sxs-lookup"><span data-stu-id="18dee-266">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="18dee-267">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="18dee-267">Known Issues</span></span>
<span data-ttu-id="18dee-268">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="18dee-268">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="18dee-269">Junho-2020 (Plataforma: 4.18.2006.10 | Mecanismo: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="18dee-269">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="18dee-270">&ensp;Versão de atualização de inteligência de segurança: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-270">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="18dee-271">&ensp;Lançado: **22 de junho de 2020**</span><span class="sxs-lookup"><span data-stu-id="18dee-271">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="18dee-272">&ensp;Plataforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="18dee-272">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="18dee-273">&ensp;Mecanismo: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="18dee-273">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="18dee-274">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="18dee-274">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="18dee-275">Novidades</span><span class="sxs-lookup"><span data-stu-id="18dee-275">What's new</span></span>

- <span data-ttu-id="18dee-276">Possibilidade de especificar o [local dos logs de suporte](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="18dee-276">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="18dee-277">Ignorar a verificação de captura agressiva no modo Passivo.</span><span class="sxs-lookup"><span data-stu-id="18dee-277">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="18dee-278">Permitir que o Defender atualize em conexões com metros</span><span class="sxs-lookup"><span data-stu-id="18dee-278">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="18dee-279">Ajuste de desempenho fixo quando o cache está desabilitado</span><span class="sxs-lookup"><span data-stu-id="18dee-279">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="18dee-280">Consulta de registro fixa</span><span class="sxs-lookup"><span data-stu-id="18dee-280">Fixed registry query</span></span> 
- <span data-ttu-id="18dee-281">Randomização de tempo de verificação fixa no ADMX</span><span class="sxs-lookup"><span data-stu-id="18dee-281">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="18dee-282">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="18dee-282">Known Issues</span></span>
<span data-ttu-id="18dee-283">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="18dee-283">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="18dee-284">Maio-2020 (plataforma: 4.18.2005.4 | Mecanismo: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="18dee-284">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="18dee-285">&ensp;Versão de atualização de inteligência de segurança: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-285">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="18dee-286">&ensp;Lançado: **26 de maio de 2020**</span><span class="sxs-lookup"><span data-stu-id="18dee-286">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="18dee-287">&ensp;Plataforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="18dee-287">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="18dee-288">&ensp;Mecanismo: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="18dee-288">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="18dee-289">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="18dee-289">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="18dee-290">Novidades</span><span class="sxs-lookup"><span data-stu-id="18dee-290">What's new</span></span>

- <span data-ttu-id="18dee-291">Registro em log aprimorado para eventos de verificação</span><span class="sxs-lookup"><span data-stu-id="18dee-291">Improved logging for scan events</span></span>
- <span data-ttu-id="18dee-292">Melhor tratamento de falhas no modo de usuário.</span><span class="sxs-lookup"><span data-stu-id="18dee-292">Improved user mode crash handling.</span></span>
- <span data-ttu-id="18dee-293">Rastreamento de eventos adicionado para proteção contra adulteração</span><span class="sxs-lookup"><span data-stu-id="18dee-293">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="18dee-294">Envio de amostra AMSI corrigido</span><span class="sxs-lookup"><span data-stu-id="18dee-294">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="18dee-295">Bloqueio fixo da nuvem AMSI</span><span class="sxs-lookup"><span data-stu-id="18dee-295">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="18dee-296">Log de instalação de atualização de segurança fixa</span><span class="sxs-lookup"><span data-stu-id="18dee-296">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="18dee-297">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="18dee-297">Known Issues</span></span>
<span data-ttu-id="18dee-298">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="18dee-298">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="18dee-299">Abril-2020 (Plataforma: 4.18.2004.6 | Mecanismo: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="18dee-299">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="18dee-300">&ensp;Versão de atualização de inteligência de segurança: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-300">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="18dee-301">&ensp;Lançado: **30 de abril de 2020**</span><span class="sxs-lookup"><span data-stu-id="18dee-301">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="18dee-302">&ensp;Plataforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="18dee-302">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="18dee-303">&ensp;Mecanismo: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="18dee-303">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="18dee-304">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="18dee-304">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="18dee-305">Novidades</span><span class="sxs-lookup"><span data-stu-id="18dee-305">What's new</span></span>
- <span data-ttu-id="18dee-306">Melhorias do WDfilter</span><span class="sxs-lookup"><span data-stu-id="18dee-306">WDfilter improvements</span></span>
- <span data-ttu-id="18dee-307">Adicionar mais dados de evento acionáveis para atacar eventos de detecção de redução de superfície</span><span class="sxs-lookup"><span data-stu-id="18dee-307">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="18dee-308">Informações de versão fixas em dados de diagnóstico e WMI</span><span class="sxs-lookup"><span data-stu-id="18dee-308">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="18dee-309">Versão da plataforma incorreta corrigida na interface do usuário após a atualização da plataforma</span><span class="sxs-lookup"><span data-stu-id="18dee-309">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="18dee-310">Intel de URL dinâmica para proteção contra ameaças sem arquivo</span><span class="sxs-lookup"><span data-stu-id="18dee-310">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="18dee-311">Recurso de verificação UEFI</span><span class="sxs-lookup"><span data-stu-id="18dee-311">UEFI scan capability</span></span>
- <span data-ttu-id="18dee-312">Estender o log para atualizações</span><span class="sxs-lookup"><span data-stu-id="18dee-312">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="18dee-313">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="18dee-313">Known Issues</span></span>
<span data-ttu-id="18dee-314">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="18dee-314">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="18dee-315">Março-2020 (Plataforma: 4.18.2003.8 | Mecanismo: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="18dee-315">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="18dee-316">&ensp;Versão de atualização de inteligência de segurança: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-316">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="18dee-317">&ensp;Lançado: **24 de março de 2020**</span><span class="sxs-lookup"><span data-stu-id="18dee-317">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="18dee-318">&ensp;Plataforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="18dee-318">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="18dee-319">&ensp;Mecanismo: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="18dee-319">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="18dee-320">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="18dee-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="18dee-321">Novidades</span><span class="sxs-lookup"><span data-stu-id="18dee-321">What's new</span></span>

- <span data-ttu-id="18dee-322">Opção de throttling de CPU adicionada ao [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="18dee-322">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="18dee-323">Melhorar a funcionalidade de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="18dee-323">Improve diagnostic capability</span></span>
- <span data-ttu-id="18dee-324">reduzir o tempo de tempo de inteligência de segurança (5 minutos)</span><span class="sxs-lookup"><span data-stu-id="18dee-324">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="18dee-325">Estender a funcionalidade de log interno do mecanismo AMSI</span><span class="sxs-lookup"><span data-stu-id="18dee-325">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="18dee-326">Melhorar a notificação para bloqueio de processos</span><span class="sxs-lookup"><span data-stu-id="18dee-326">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="18dee-327">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="18dee-327">Known Issues</span></span>
<span data-ttu-id="18dee-328">[**Fixo**] Microsoft Defender Antivírus está ignorando arquivos ao executar uma verificação.</span><span class="sxs-lookup"><span data-stu-id="18dee-328">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="18dee-329">Fevereiro-2020 (Plataforma: - | Mecanismo: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="18dee-329">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="18dee-330">&ensp;Versão de atualização de inteligência de segurança: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="18dee-330">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="18dee-331">&ensp;Lançado: **25 de fevereiro de 2020**</span><span class="sxs-lookup"><span data-stu-id="18dee-331">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="18dee-332">&ensp;Plataforma/Cliente: **-**</span><span class="sxs-lookup"><span data-stu-id="18dee-332">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="18dee-333">&ensp;Mecanismo: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="18dee-333">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="18dee-334">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="18dee-334">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="18dee-335">Novidades</span><span class="sxs-lookup"><span data-stu-id="18dee-335">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="18dee-336">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="18dee-336">Known Issues</span></span>
<span data-ttu-id="18dee-337">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="18dee-337">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="18dee-338">Janeiro-2020 (Plataforma: 4.18.2001.10 | Mecanismo: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="18dee-338">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="18dee-339">Versão de atualização de inteligência de segurança: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-339">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="18dee-340">Lançado: **30 de janeiro de 2020**</span><span class="sxs-lookup"><span data-stu-id="18dee-340">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="18dee-341">Plataforma/Cliente: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="18dee-341">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="18dee-342">Mecanismo: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="18dee-342">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="18dee-343">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="18dee-343">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="18dee-344">Novidades</span><span class="sxs-lookup"><span data-stu-id="18dee-344">What's new</span></span>

- <span data-ttu-id="18dee-345">BSOD fixo no WS2016 com Exchange</span><span class="sxs-lookup"><span data-stu-id="18dee-345">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="18dee-346">Atualizações da plataforma de suporte quando o TMP é redirecionado para o caminho da rede</span><span class="sxs-lookup"><span data-stu-id="18dee-346">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="18dee-347">As versões de plataforma e mecanismo são [adicionadas ao WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="18dee-347">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="18dee-348">estender a atualização de assinatura de emergência para [o modo passivo](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="18dee-348">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="18dee-349">Corrigir trava 4.18.1911.3</span><span class="sxs-lookup"><span data-stu-id="18dee-349">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="18dee-350">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="18dee-350">Known Issues</span></span>

<span data-ttu-id="18dee-351">[**Fixo**] dispositivos [que](/windows-hardware/design/device-experiences/modern-standby) usam o modo de espera moderno podem ter uma trava com o driver de filtro Windows Defender que resulta em uma lacuna de proteção.</span><span class="sxs-lookup"><span data-stu-id="18dee-351">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="18dee-352">Os máquinas afetados aparecem para o cliente como não atualizados para a plataforma antimalware mais recente.</span><span class="sxs-lookup"><span data-stu-id="18dee-352">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="18dee-353">Esta atualização é:</span><span class="sxs-lookup"><span data-stu-id="18dee-353">This update is:</span></span>
> - <span data-ttu-id="18dee-354">necessário por dispositivos RS1 que executam a versão inferior da plataforma para dar suporte ao SHA2;</span><span class="sxs-lookup"><span data-stu-id="18dee-354">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="18dee-355">tem um sinalizador de reinicialização para sistemas que têm problemas de suspensão;</span><span class="sxs-lookup"><span data-stu-id="18dee-355">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="18dee-356">é re-lançado em abril de 2020 e não será superada por atualizações mais novas para manter a disponibilidade futura;</span><span class="sxs-lookup"><span data-stu-id="18dee-356">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="18dee-357">é categorizado como uma atualização devido ao requisito de reinicialização; e</span><span class="sxs-lookup"><span data-stu-id="18dee-357">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="18dee-358">só será oferecido com o [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="18dee-358">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="18dee-359">Novembro-2019 (plataforma: 4.18.1911.3 | Mecanismo: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="18dee-359">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="18dee-360">Versão de atualização de inteligência de segurança: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-360">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="18dee-361">Lançado: **7 de dezembro de 2019**</span><span class="sxs-lookup"><span data-stu-id="18dee-361">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="18dee-362">Plataforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="18dee-362">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="18dee-363">Mecanismo: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="18dee-363">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="18dee-364">Fase de suporte: **sem suporte**</span><span class="sxs-lookup"><span data-stu-id="18dee-364">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="18dee-365">Novidades</span><span class="sxs-lookup"><span data-stu-id="18dee-365">What's new</span></span>

- <span data-ttu-id="18dee-366">Nível de rastreamento De MpCmdRun fixo</span><span class="sxs-lookup"><span data-stu-id="18dee-366">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="18dee-367">Informações de versão fixas do WDFilter</span><span class="sxs-lookup"><span data-stu-id="18dee-367">Fixed WDFilter version info</span></span>
- <span data-ttu-id="18dee-368">Melhorar notificações (PUA)</span><span class="sxs-lookup"><span data-stu-id="18dee-368">Improve notifications (PUA)</span></span>
- <span data-ttu-id="18dee-369">adicionar logs MRT para dar suporte a arquivos</span><span class="sxs-lookup"><span data-stu-id="18dee-369">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="18dee-370">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="18dee-370">Known Issues</span></span>
<span data-ttu-id="18dee-371">Quando essa atualização é instalada, o dispositivo precisa do pacote de salto 4.18.2001.10 para poder atualizar para a versão mais recente da plataforma.</span><span class="sxs-lookup"><span data-stu-id="18dee-371">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="18dee-372">Microsoft Defender Antivírus plataforma</span><span class="sxs-lookup"><span data-stu-id="18dee-372">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="18dee-373">As atualizações de plataforma e mecanismo são fornecidas em uma cadência mensal.</span><span class="sxs-lookup"><span data-stu-id="18dee-373">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="18dee-374">Para ter suporte total, mantenha-se atualizado com as atualizações mais recentes da plataforma.</span><span class="sxs-lookup"><span data-stu-id="18dee-374">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="18dee-375">Nossa estrutura de suporte é dinâmica, evoluindo em duas fases, dependendo da disponibilidade da versão mais recente da plataforma:</span><span class="sxs-lookup"><span data-stu-id="18dee-375">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="18dee-376">Fase de manutenção de Atualizações **Críticas** e Segurança - Ao executar a versão mais recente da plataforma, você estará qualificado para receber atualizações de segurança e críticas para a plataforma anti-malware.</span><span class="sxs-lookup"><span data-stu-id="18dee-376">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="18dee-377">Fase de Suporte Técnico **(Somente)** - Depois que uma nova versão da plataforma for lançada, o suporte para versões mais antigas (N-2) será redução apenas para suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="18dee-377">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="18dee-378">As versões da plataforma anteriores ao N-2 não serão mais suportadas.\*</span><span class="sxs-lookup"><span data-stu-id="18dee-378">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="18dee-379">\*O suporte técnico continuará a ser fornecido para atualizações da versão Windows 10 versão do Windows 10 (consulte Versão da plataforma incluída com Windows 10 [versões](#platform-version-included-with-windows-10-releases)) para a versão mais recente da plataforma.</span><span class="sxs-lookup"><span data-stu-id="18dee-379">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="18dee-380">Durante a fase de suporte técnico (somente), incidentes de suporte comercialmente razoáveis serão fornecidos por meio do Serviço de Atendimento ao Cliente da Microsoft & Suporte e ofertas de suporte gerenciado da Microsoft (como o Suporte Premier).</span><span class="sxs-lookup"><span data-stu-id="18dee-380">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="18dee-381">Se um incidente de suporte exigir escalonamento para desenvolvimento para obter mais orientações, exigir uma atualização que não seja de segurança ou exigir uma atualização de segurança, os clientes serão solicitados a atualizar para a versão mais recente da plataforma ou uma atualização intermediária (\*).</span><span class="sxs-lookup"><span data-stu-id="18dee-381">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="18dee-382">Versão da plataforma incluída com Windows 10 versões</span><span class="sxs-lookup"><span data-stu-id="18dee-382">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="18dee-383">A tabela a seguir fornece as versões Microsoft Defender Antivírus plataforma e mecanismo que são enviadas com as versões Windows 10 versão mais recentes:</span><span class="sxs-lookup"><span data-stu-id="18dee-383">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="18dee-384">Windows 10 versão</span><span class="sxs-lookup"><span data-stu-id="18dee-384">Windows 10 release</span></span>  |<span data-ttu-id="18dee-385">Versão da plataforma</span><span class="sxs-lookup"><span data-stu-id="18dee-385">Platform version</span></span>  |<span data-ttu-id="18dee-386">Versão do mecanismo</span><span class="sxs-lookup"><span data-stu-id="18dee-386">Engine version</span></span> |<span data-ttu-id="18dee-387">Fase de suporte</span><span class="sxs-lookup"><span data-stu-id="18dee-387">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="18dee-388">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="18dee-388">2004  (20H1/20H2)</span></span> |<span data-ttu-id="18dee-389">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="18dee-389">4.18.1909.6</span></span> |<span data-ttu-id="18dee-390">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="18dee-390">1.1.17000.2</span></span> | <span data-ttu-id="18dee-391">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="18dee-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="18dee-392">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="18dee-392">1909  (19H2)</span></span> |<span data-ttu-id="18dee-393">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="18dee-393">4.18.1902.5</span></span> |<span data-ttu-id="18dee-394">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="18dee-394">1.1.16700.3</span></span> | <span data-ttu-id="18dee-395">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="18dee-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="18dee-396">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="18dee-396">1903  (19H1)</span></span> |<span data-ttu-id="18dee-397">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="18dee-397">4.18.1902.5</span></span> |<span data-ttu-id="18dee-398">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="18dee-398">1.1.15600.4</span></span> | <span data-ttu-id="18dee-399">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="18dee-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="18dee-400">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="18dee-400">1809  (RS5)</span></span> |<span data-ttu-id="18dee-401">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="18dee-401">4.18.1807.18075</span></span> |<span data-ttu-id="18dee-402">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="18dee-402">1.1.15000.2</span></span> | <span data-ttu-id="18dee-403">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="18dee-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="18dee-404">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="18dee-404">1803  (RS4)</span></span> |<span data-ttu-id="18dee-405">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="18dee-405">4.13.17134.1</span></span> |<span data-ttu-id="18dee-406">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="18dee-406">1.1.14600.4</span></span> | <span data-ttu-id="18dee-407">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="18dee-407">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="18dee-408">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="18dee-408">1709  (RS3)</span></span> |<span data-ttu-id="18dee-409">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="18dee-409">4.12.16299.15</span></span> |<span data-ttu-id="18dee-410">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="18dee-410">1.1.14104.0</span></span> | <span data-ttu-id="18dee-411">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="18dee-411">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="18dee-412">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="18dee-412">1703  (RS2)</span></span> |<span data-ttu-id="18dee-413">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="18dee-413">4.11.15603.2</span></span> |<span data-ttu-id="18dee-414">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="18dee-414">1.1.13504.0</span></span> | <span data-ttu-id="18dee-415">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="18dee-415">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="18dee-416">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="18dee-416">1607 (RS1)</span></span> |<span data-ttu-id="18dee-417">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="18dee-417">4.10.14393.3683</span></span> |<span data-ttu-id="18dee-418">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="18dee-418">1.1.12805.0</span></span> | <span data-ttu-id="18dee-419">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="18dee-419">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="18dee-420">Para Windows 10 informações de versão, consulte a planilha Windows de fatos do ciclo [de vida.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="18dee-420">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="18dee-421">Atualizações para Manutenção e Gerenciamento de Imagens de Implantação (DISM)</span><span class="sxs-lookup"><span data-stu-id="18dee-421">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="18dee-422">Recomendamos atualizar suas Windows 10 (Enterprise, Pro e edições Home), o Windows Server 2019 e Windows Server 2016 imagens de instalação do sistema operacional com as atualizações mais recentes de antivírus e antimalware.</span><span class="sxs-lookup"><span data-stu-id="18dee-422">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="18dee-423">Manter as imagens de instalação do sistema operacional atualizadas ajuda a evitar uma lacuna na proteção.</span><span class="sxs-lookup"><span data-stu-id="18dee-423">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="18dee-424">Para obter mais informações, consulte [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="18dee-424">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="18dee-425">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="18dee-425">1.1.2106.01</span></span></summary>

<span data-ttu-id="18dee-426">&ensp;Versão do pacote: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="18dee-426">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="18dee-427">&ensp;Versão da plataforma: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="18dee-427">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="18dee-428">&ensp;Versão do mecanismo: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="18dee-428">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="18dee-429">&ensp;Versão de assinatura: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-429">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="18dee-430">Correções</span><span class="sxs-lookup"><span data-stu-id="18dee-430">Fixes</span></span>
- <span data-ttu-id="18dee-431">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18dee-431">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="18dee-432">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="18dee-432">Additional information</span></span>
- <span data-ttu-id="18dee-433">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18dee-433">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="18dee-434">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="18dee-434">1.1.2105.01</span></span></summary>

<span data-ttu-id="18dee-435">&ensp;Versão do pacote: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="18dee-435">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="18dee-436">&ensp;Versão da plataforma: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="18dee-436">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="18dee-437">&ensp;Versão do mecanismo: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="18dee-437">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="18dee-438">&ensp;Versão de assinatura: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-438">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="18dee-439">Correções</span><span class="sxs-lookup"><span data-stu-id="18dee-439">Fixes</span></span>
- <span data-ttu-id="18dee-440">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18dee-440">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="18dee-441">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="18dee-441">Additional information</span></span>
- <span data-ttu-id="18dee-442">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18dee-442">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="18dee-443">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="18dee-443">1.1.2104.01</span></span></summary>

<span data-ttu-id="18dee-444">&ensp;Versão do pacote: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="18dee-444">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="18dee-445">&ensp;Versão da plataforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="18dee-445">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="18dee-446">&ensp;Versão do mecanismo: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="18dee-446">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="18dee-447">&ensp;Versão de assinatura: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-447">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="18dee-448">Correções</span><span class="sxs-lookup"><span data-stu-id="18dee-448">Fixes</span></span>
- <span data-ttu-id="18dee-449">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18dee-449">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="18dee-450">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="18dee-450">Additional information</span></span>
- <span data-ttu-id="18dee-451">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18dee-451">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="18dee-452">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="18dee-452">1.1.2103.01</span></span></summary>

<span data-ttu-id="18dee-453">&ensp;Versão do pacote: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="18dee-453">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="18dee-454">&ensp;Versão da plataforma: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="18dee-454">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="18dee-455">&ensp;Versão do mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="18dee-455">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="18dee-456">&ensp;Versão de assinatura: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-456">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="18dee-457">Correções</span><span class="sxs-lookup"><span data-stu-id="18dee-457">Fixes</span></span>
- <span data-ttu-id="18dee-458">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18dee-458">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="18dee-459">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="18dee-459">Additional information</span></span>
- <span data-ttu-id="18dee-460">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18dee-460">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="18dee-461">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="18dee-461">1.1.2102.03</span></span></summary>

<span data-ttu-id="18dee-462">&ensp;Versão do pacote: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="18dee-462">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="18dee-463">&ensp;Versão da plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="18dee-463">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="18dee-464">&ensp;Versão do mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="18dee-464">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="18dee-465">&ensp;Versão de assinatura: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-465">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="18dee-466">Correções</span><span class="sxs-lookup"><span data-stu-id="18dee-466">Fixes</span></span>
- <span data-ttu-id="18dee-467">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18dee-467">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="18dee-468">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="18dee-468">Additional information</span></span>
- <span data-ttu-id="18dee-469">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18dee-469">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="18dee-470">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="18dee-470">1.1.2101.02</span></span></summary>

<span data-ttu-id="18dee-471">&ensp;Versão do pacote: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="18dee-471">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="18dee-472">&ensp;Versão da plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="18dee-472">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="18dee-473">&ensp;Versão do mecanismo: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="18dee-473">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="18dee-474">&ensp;Versão de assinatura: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-474">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="18dee-475">Correções</span><span class="sxs-lookup"><span data-stu-id="18dee-475">Fixes</span></span>
- <span data-ttu-id="18dee-476">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18dee-476">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="18dee-477">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="18dee-477">Additional information</span></span>
- <span data-ttu-id="18dee-478">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18dee-478">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="18dee-479">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="18dee-479">1.1.2012.01</span></span></summary>

<span data-ttu-id="18dee-480">&ensp;Versão do pacote: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="18dee-480">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="18dee-481">&ensp;Versão da plataforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="18dee-481">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="18dee-482">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="18dee-482">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="18dee-483">&ensp;Versão de assinatura: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-483">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="18dee-484">Correções</span><span class="sxs-lookup"><span data-stu-id="18dee-484">Fixes</span></span>
- <span data-ttu-id="18dee-485">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18dee-485">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="18dee-486">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="18dee-486">Additional information</span></span>
- <span data-ttu-id="18dee-487">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18dee-487">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="18dee-488">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="18dee-488">1.1.2011.02</span></span></summary>

<span data-ttu-id="18dee-489">&ensp;Versão do pacote: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="18dee-489">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="18dee-490">&ensp;Versão da plataforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="18dee-490">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="18dee-491">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="18dee-491">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="18dee-492">&ensp;Versão de assinatura: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-492">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="18dee-493">Correções</span><span class="sxs-lookup"><span data-stu-id="18dee-493">Fixes</span></span>
- <span data-ttu-id="18dee-494">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18dee-494">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="18dee-495">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="18dee-495">Additional information</span></span>
- <span data-ttu-id="18dee-496">Assinaturas Microsoft Defender Antivírus atualizadas</span><span class="sxs-lookup"><span data-stu-id="18dee-496">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="18dee-497">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="18dee-497">1.1.2011.01</span></span></summary>

<span data-ttu-id="18dee-498">&ensp;Versão do pacote: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="18dee-498">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="18dee-499">&ensp;Versão da plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="18dee-499">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="18dee-500">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="18dee-500">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="18dee-501">&ensp;Versão de assinatura: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-501">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="18dee-502">Correções</span><span class="sxs-lookup"><span data-stu-id="18dee-502">Fixes</span></span>
- <span data-ttu-id="18dee-503">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18dee-503">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="18dee-504">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="18dee-504">Additional information</span></span>
- <span data-ttu-id="18dee-505">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18dee-505">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="18dee-506">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="18dee-506">1.1.2009.10</span></span></summary>

<span data-ttu-id="18dee-507">&ensp;Versão do pacote: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="18dee-507">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="18dee-508">&ensp;Versão da plataforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="18dee-508">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="18dee-509">&ensp;Versão do mecanismo: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="18dee-509">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="18dee-510">&ensp;Versão de assinatura: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="18dee-510">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="18dee-511">Correções</span><span class="sxs-lookup"><span data-stu-id="18dee-511">Fixes</span></span>
- <span data-ttu-id="18dee-512">Nenhum</span><span class="sxs-lookup"><span data-stu-id="18dee-512">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="18dee-513">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="18dee-513">Additional information</span></span>
- <span data-ttu-id="18dee-514">Adicionado suporte para Windows 10 RS1 ou imagens de instalação posteriores do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="18dee-514">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="18dee-515">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="18dee-515">Additional resources</span></span>

| <span data-ttu-id="18dee-516">Artigo</span><span class="sxs-lookup"><span data-stu-id="18dee-516">Article</span></span> | <span data-ttu-id="18dee-517">Descrição</span><span class="sxs-lookup"><span data-stu-id="18dee-517">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="18dee-518">Atualização do Microsoft Defender para Windows de instalação do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="18dee-518">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="18dee-519">Revise os pacotes de atualização antimalware para as imagens de instalação do sistema operacional (arquivos WIM e VHD).</span><span class="sxs-lookup"><span data-stu-id="18dee-519">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="18dee-520">Obter Microsoft Defender Antivírus atualizações para Windows 10 (Enterprise, Pro e edições Home), Windows Server 2019 e Windows Server 2016 de instalação.</span><span class="sxs-lookup"><span data-stu-id="18dee-520">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="18dee-521">Gerenciar como as atualizações de proteção são baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="18dee-521">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="18dee-522">As atualizações de proteção podem ser entregues por meio de várias fontes.</span><span class="sxs-lookup"><span data-stu-id="18dee-522">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="18dee-523">Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="18dee-523">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="18dee-524">Você pode agendar quando as atualizações de proteção devem ser baixadas.</span><span class="sxs-lookup"><span data-stu-id="18dee-524">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="18dee-525">Gerenciar atualizações para pontos de extremidade que estão des date</span><span class="sxs-lookup"><span data-stu-id="18dee-525">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="18dee-526">Se um ponto de extremidade perder uma atualização ou uma verificação agendada, você poderá forçar uma atualização ou verificar na próxima vez que um usuário entrar.</span><span class="sxs-lookup"><span data-stu-id="18dee-526">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="18dee-527">Gerenciar atualizações aplicadas com base em evento</span><span class="sxs-lookup"><span data-stu-id="18dee-527">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="18dee-528">Você pode definir atualizações de proteção a serem baixadas na inicialização ou após determinados eventos de proteção entregues na nuvem.</span><span class="sxs-lookup"><span data-stu-id="18dee-528">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="18dee-529">Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)</span><span class="sxs-lookup"><span data-stu-id="18dee-529">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="18dee-530">Você pode especificar configurações, como se as atualizações devem ocorrer na energia da bateria, que são especialmente úteis para dispositivos móveis e máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="18dee-530">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
