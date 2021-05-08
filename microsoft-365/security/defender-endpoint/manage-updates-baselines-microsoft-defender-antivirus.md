---
title: Gerenciar Microsoft Defender Antivírus e aplicar linhas de base
description: Gerenciar como Microsoft Defender Antivírus recebe atualizações de produtos e proteção.
keywords: atualizações, linhas de base de segurança, proteção, agendar atualizações, forçar atualizações, atualizações móveis, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 92f903f750ea5e7f2cb971b535c50bfecced65a2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52242307"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="4d421-104">Gerenciar Microsoft Defender Antivírus e aplicar linhas de base</span><span class="sxs-lookup"><span data-stu-id="4d421-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="4d421-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4d421-105">**Applies to:**</span></span>

- [<span data-ttu-id="4d421-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4d421-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="4d421-107">Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="4d421-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="4d421-108">Há dois tipos de atualizações relacionadas à Microsoft Defender Antivírus atualizadas:</span><span class="sxs-lookup"><span data-stu-id="4d421-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="4d421-109">Atualizações de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="4d421-109">Security intelligence updates</span></span>
- <span data-ttu-id="4d421-110">Atualizações de produtos</span><span class="sxs-lookup"><span data-stu-id="4d421-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4d421-111">Manter Microsoft Defender Antivírus atualizado é fundamental para garantir que seus dispositivos tenham a tecnologia e os recursos mais recentes necessários para proteger contra novas técnicas de malware e ataque.</span><span class="sxs-lookup"><span data-stu-id="4d421-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="4d421-112">Certifique-se de atualizar sua proteção antivírus mesmo que Microsoft Defender Antivírus está sendo executado no [modo passivo](./microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="4d421-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="4d421-113">Para ver o mecanismo, a plataforma e a data de assinatura mais atuais, visite as atualizações de inteligência de segurança para Microsoft Defender Antivírus e outros [antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4d421-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="4d421-114">Atualizações de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="4d421-114">Security intelligence updates</span></span>

<span data-ttu-id="4d421-115">Microsoft Defender Antivírus usa [proteção](cloud-protection-microsoft-defender-antivirus.md) entregue na nuvem (também chamada de Serviço de Proteção Avançada da Microsoft ou MAPS) e baixa periodicamente atualizações de inteligência de segurança para fornecer proteção.</span><span class="sxs-lookup"><span data-stu-id="4d421-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="4d421-116">As atualizações são lançadas nos números KB abaixo:</span><span class="sxs-lookup"><span data-stu-id="4d421-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="4d421-117">Microsoft Defender Antivírus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="4d421-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="4d421-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="4d421-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="4d421-119">A proteção entregue na nuvem está sempre ativa e requer uma conexão ativa com a Internet para funcionar.</span><span class="sxs-lookup"><span data-stu-id="4d421-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="4d421-120">As atualizações de inteligência de segurança ocorrem em uma cadência agendada (configurável por meio da política).</span><span class="sxs-lookup"><span data-stu-id="4d421-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="4d421-121">Para obter mais informações, [consulte Use Microsoft cloud-provided protection in Microsoft Defender Antivírus](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="4d421-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="4d421-122">Para ver uma lista de atualizações recentes de inteligência de segurança, consulte Atualizações de inteligência de segurança para Microsoft Defender Antivírus [e outros antimalware da Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="4d421-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="4d421-123">As atualizações do mecanismo são incluídas com atualizações de inteligência de segurança e são lançadas em uma cadência mensal.</span><span class="sxs-lookup"><span data-stu-id="4d421-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="4d421-124">Atualizações de produtos</span><span class="sxs-lookup"><span data-stu-id="4d421-124">Product updates</span></span>

<span data-ttu-id="4d421-125">Microsoft Defender Antivírus exige atualizações mensais [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) *(conhecidas* como atualizações de plataforma) e receberá atualizações de recursos principais juntamente com Windows 10 versões.</span><span class="sxs-lookup"><span data-stu-id="4d421-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="4d421-126">Você pode gerenciar a distribuição de atualizações por meio de um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="4d421-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="4d421-127">Windows Serviço de Atualização do Servidor (WSUS)</span><span class="sxs-lookup"><span data-stu-id="4d421-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="4d421-128">Gerenciador de Configuração do Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="4d421-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="4d421-129">O método comum que você usa para implantar a Microsoft e Windows atualizações para pontos de extremidade em sua rede.</span><span class="sxs-lookup"><span data-stu-id="4d421-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="4d421-130">Para obter mais informações, consulte [Manage the sources for Microsoft Defender Antivírus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="4d421-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="4d421-131">As atualizações mensais são lançadas em fases, resultando em vários pacotes visíveis em seus [Serviços de Atualização do Servidor de Janelas.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="4d421-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="4d421-132">Versões mensais de plataforma e mecanismo</span><span class="sxs-lookup"><span data-stu-id="4d421-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="4d421-133">Para obter informações sobre como atualizar ou instalar a atualização da plataforma, consulte [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="4d421-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="4d421-134">Todas as nossas atualizações contêm</span><span class="sxs-lookup"><span data-stu-id="4d421-134">All our updates contain</span></span> 
- <span data-ttu-id="4d421-135">melhorias de desempenho;</span><span class="sxs-lookup"><span data-stu-id="4d421-135">performance improvements;</span></span>
- <span data-ttu-id="4d421-136">melhorias de capacidade de serviço; e</span><span class="sxs-lookup"><span data-stu-id="4d421-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="4d421-137">melhorias de integração (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="4d421-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="4d421-138">Abril-2021 (Plataforma: 4.19.2104.9| Mecanismo: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="4d421-138">April-2021 (Platform: 4.19.2104.9| Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="4d421-139">&ensp;Versão de atualização de inteligência de segurança: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="4d421-140">&ensp;Lançado: **1º de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="4d421-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="4d421-141">&ensp;Plataforma: **4.19.2104.9**</span><span class="sxs-lookup"><span data-stu-id="4d421-141">&ensp;Platform: **4.19.2104.9**</span></span>  
<span data-ttu-id="4d421-142">&ensp;Mecanismo: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="4d421-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="4d421-143">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="4d421-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4d421-144">Novidades</span><span class="sxs-lookup"><span data-stu-id="4d421-144">What's new</span></span>
- <span data-ttu-id="4d421-145">Lógica adicional de monitoramento de comportamento</span><span class="sxs-lookup"><span data-stu-id="4d421-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="4d421-146">Detecção aprimorada do keylogger do modo kernel</span><span class="sxs-lookup"><span data-stu-id="4d421-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="4d421-147">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="4d421-147">Known Issues</span></span>
<span data-ttu-id="4d421-148">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="4d421-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="4d421-149">Março-2021 (plataforma: 4.19.2103.7 | Mecanismo: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="4d421-149">March-2021 (Platform: 4.19.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="4d421-150">&ensp;Versão de atualização de inteligência de segurança: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="4d421-151">&ensp;Lançado: **1º de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="4d421-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="4d421-152">&ensp;Plataforma: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="4d421-152">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="4d421-153">&ensp;Mecanismo: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="4d421-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="4d421-154">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="4d421-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4d421-155">Novidades</span><span class="sxs-lookup"><span data-stu-id="4d421-155">What's new</span></span>

- <span data-ttu-id="4d421-156">Melhoria no mecanismo de Monitoramento de Comportamento</span><span class="sxs-lookup"><span data-stu-id="4d421-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="4d421-157">Mitigações de ataques de força bruta de rede expandida</span><span class="sxs-lookup"><span data-stu-id="4d421-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="4d421-158">Geração adicional de eventos de tentativa de adulteração com falha quando [a Proteção contra Adulteração](prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada</span><span class="sxs-lookup"><span data-stu-id="4d421-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="4d421-159">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="4d421-159">Known Issues</span></span>
<span data-ttu-id="4d421-160">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="4d421-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="4d421-161">Fevereiro-2021 (plataforma: 4.19.2102.3 | Mecanismo: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="4d421-161">February-2021 (Platform: 4.19.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="4d421-162">&ensp;Versão de atualização de inteligência de segurança: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="4d421-163">&ensp;Lançado: **9 de março de 2021**</span><span class="sxs-lookup"><span data-stu-id="4d421-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="4d421-164">&ensp;Plataforma: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="4d421-164">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="4d421-165">&ensp;Mecanismo: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="4d421-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="4d421-166">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="4d421-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4d421-167">Novidades</span><span class="sxs-lookup"><span data-stu-id="4d421-167">What's new</span></span>

- <span data-ttu-id="4d421-168">Recuperação aprimorada do serviço por meio [da proteção contra violações](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="4d421-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="4d421-169">Estender escopo de proteção contra violações</span><span class="sxs-lookup"><span data-stu-id="4d421-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="4d421-170">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="4d421-170">Known Issues</span></span>
<span data-ttu-id="4d421-171">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="4d421-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="4d421-172">Atualizações de versão anterior: Suporte técnico somente a atualização</span><span class="sxs-lookup"><span data-stu-id="4d421-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="4d421-173">Depois que uma nova versão de pacote é lançada, o suporte para as duas versões anteriores é reduzido apenas ao suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="4d421-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="4d421-174">Versões anteriores às listadas nesta seção são fornecidas apenas para suporte técnico de atualização.</span><span class="sxs-lookup"><span data-stu-id="4d421-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="4d421-175">Janeiro-2021 (Plataforma: 4.18.2101.9 | Mecanismo: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="4d421-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="4d421-176">&ensp;Versão de atualização de inteligência de segurança: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="4d421-177">&ensp;Lançado: **2 de fevereiro de 2021**</span><span class="sxs-lookup"><span data-stu-id="4d421-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="4d421-178">&ensp;Plataforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="4d421-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="4d421-179">&ensp;Mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="4d421-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="4d421-180">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="4d421-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4d421-181">Novidades</span><span class="sxs-lookup"><span data-stu-id="4d421-181">What's new</span></span>

- <span data-ttu-id="4d421-182">Melhorias na detecção de exploração de shellcode</span><span class="sxs-lookup"><span data-stu-id="4d421-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="4d421-183">Maior visibilidade para tentativas de roubo de credenciais</span><span class="sxs-lookup"><span data-stu-id="4d421-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="4d421-184">Melhorias nos recursos anti-amperes em serviços Microsoft Defender Antivírus serviços</span><span class="sxs-lookup"><span data-stu-id="4d421-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="4d421-185">Suporte aprimorado para ARM emulação x64</span><span class="sxs-lookup"><span data-stu-id="4d421-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="4d421-186">Correção: EDR a notificação de bloqueio permanece no histórico de ameaças depois que a proteção em tempo real realizou a detecção inicial</span><span class="sxs-lookup"><span data-stu-id="4d421-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="4d421-187">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="4d421-187">Known Issues</span></span>
<span data-ttu-id="4d421-188">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="4d421-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="4d421-189">Novembro-2020 (Plataforma: 4.18.2011.6 | Mecanismo: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="4d421-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="4d421-190">&ensp;Versão de atualização de inteligência de segurança: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="4d421-191">&ensp;Lançado: **03 de dezembro de 2020**</span><span class="sxs-lookup"><span data-stu-id="4d421-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="4d421-192">&ensp;Plataforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="4d421-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="4d421-193">&ensp;Mecanismo: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="4d421-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="4d421-194">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="4d421-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4d421-195">Novidades</span><span class="sxs-lookup"><span data-stu-id="4d421-195">What's new</span></span>

- <span data-ttu-id="4d421-196">Registro em log de suporte ao status [do SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) aprimorado</span><span class="sxs-lookup"><span data-stu-id="4d421-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="4d421-197">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="4d421-197">Known Issues</span></span>
<span data-ttu-id="4d421-198">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="4d421-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="4d421-199">Outubro-2020 (Plataforma: 4.18.2010.7 | Mecanismo: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="4d421-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="4d421-200">&ensp;Versão de atualização de inteligência de segurança: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="4d421-201">&ensp;Lançado: **29 de outubro de 2020**</span><span class="sxs-lookup"><span data-stu-id="4d421-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="4d421-202">&ensp;Plataforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="4d421-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="4d421-203">&ensp;Mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="4d421-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="4d421-204">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="4d421-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4d421-205">Novidades</span><span class="sxs-lookup"><span data-stu-id="4d421-205">What's new</span></span>

- <span data-ttu-id="4d421-206">Novas descrições para categorias de ameaças especiais</span><span class="sxs-lookup"><span data-stu-id="4d421-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="4d421-207">Recursos de emulação aprimorados</span><span class="sxs-lookup"><span data-stu-id="4d421-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="4d421-208">Recursos de permitir/bloquear endereço de host aprimorados</span><span class="sxs-lookup"><span data-stu-id="4d421-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="4d421-209">Nova opção no CSP do Defender para Ignorar a mesclação de exclusões de usuários locais</span><span class="sxs-lookup"><span data-stu-id="4d421-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="4d421-210">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="4d421-210">Known Issues</span></span>

<span data-ttu-id="4d421-211">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="4d421-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="4d421-212">Setembro-2020 (Plataforma: 4.18.2009.7 | Mecanismo: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="4d421-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="4d421-213">&ensp;Versão de atualização de inteligência de segurança: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="4d421-214">&ensp;Lançado: **01 de outubro de 2020**</span><span class="sxs-lookup"><span data-stu-id="4d421-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="4d421-215">&ensp;Plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="4d421-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="4d421-216">&ensp;Mecanismo: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="4d421-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="4d421-217">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="4d421-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4d421-218">Novidades</span><span class="sxs-lookup"><span data-stu-id="4d421-218">What's new</span></span>

- <span data-ttu-id="4d421-219">Permissões de administrador são necessárias para restaurar arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="4d421-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="4d421-220">Eventos formatados xml agora são suportados</span><span class="sxs-lookup"><span data-stu-id="4d421-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="4d421-221">Suporte a CSP para ignorar mesclações de exclusão</span><span class="sxs-lookup"><span data-stu-id="4d421-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="4d421-222">Novas interfaces de gerenciamento para:</span><span class="sxs-lookup"><span data-stu-id="4d421-222">New management interfaces for:</span></span>
   - <span data-ttu-id="4d421-223">Inspeção UDP</span><span class="sxs-lookup"><span data-stu-id="4d421-223">UDP Inspection</span></span>
   - <span data-ttu-id="4d421-224">Proteção de Rede no Server 2019</span><span class="sxs-lookup"><span data-stu-id="4d421-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="4d421-225">Exclusões de endereço IP para Proteção de Rede</span><span class="sxs-lookup"><span data-stu-id="4d421-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="4d421-226">Visibilidade aprimorada nas medições do TPM</span><span class="sxs-lookup"><span data-stu-id="4d421-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="4d421-227">Verificação aprimorada Office módulo VBA</span><span class="sxs-lookup"><span data-stu-id="4d421-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="4d421-228">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="4d421-228">Known Issues</span></span>

<span data-ttu-id="4d421-229">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="4d421-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="4d421-230">Agosto-2020 (plataforma: 4.18.2008.9 | Mecanismo: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="4d421-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="4d421-231">&ensp;Versão de atualização de inteligência de segurança: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="4d421-232">&ensp;Lançado: **27 de agosto de 2020**</span><span class="sxs-lookup"><span data-stu-id="4d421-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="4d421-233">&ensp;Plataforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="4d421-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="4d421-234">&ensp;Mecanismo: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="4d421-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="4d421-235">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="4d421-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="4d421-236">Novidades</span><span class="sxs-lookup"><span data-stu-id="4d421-236">What's new</span></span>

- <span data-ttu-id="4d421-237">Adicionar mais eventos de telemetria</span><span class="sxs-lookup"><span data-stu-id="4d421-237">Add more telemetry events</span></span>
- <span data-ttu-id="4d421-238">Telemetria de eventos de verificação aprimorada</span><span class="sxs-lookup"><span data-stu-id="4d421-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="4d421-239">Monitoramento de comportamento aprimorado para verificações de memória</span><span class="sxs-lookup"><span data-stu-id="4d421-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="4d421-240">Verificação de fluxos de macros aprimorados</span><span class="sxs-lookup"><span data-stu-id="4d421-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="4d421-241">Adicionado `AMRunningMode` ao cmdlet Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d421-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="4d421-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) é ignorado.</span><span class="sxs-lookup"><span data-stu-id="4d421-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="4d421-243">Microsoft Defender Antivírus se desliga automaticamente quando detecta outro programa antivírus.</span><span class="sxs-lookup"><span data-stu-id="4d421-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="4d421-244">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="4d421-244">Known Issues</span></span>
<span data-ttu-id="4d421-245">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="4d421-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="4d421-246">Julho-2020 (Plataforma: 4.18.2007.8 | Mecanismo: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="4d421-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="4d421-247">&ensp;Versão de atualização de inteligência de segurança: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="4d421-248">&ensp;Lançado: **28 de julho de 2020**</span><span class="sxs-lookup"><span data-stu-id="4d421-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="4d421-249">&ensp;Plataforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="4d421-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="4d421-250">&ensp;Mecanismo: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="4d421-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="4d421-251">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="4d421-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4d421-252">Novidades</span><span class="sxs-lookup"><span data-stu-id="4d421-252">What's new</span></span>

- <span data-ttu-id="4d421-253">Telemetria aprimorada para BITS</span><span class="sxs-lookup"><span data-stu-id="4d421-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="4d421-254">Validação aprimorada de certificado de assinatura de código Authenticode</span><span class="sxs-lookup"><span data-stu-id="4d421-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="4d421-255">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="4d421-255">Known Issues</span></span>
<span data-ttu-id="4d421-256">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="4d421-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="4d421-257">Junho-2020 (Plataforma: 4.18.2006.10 | Mecanismo: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="4d421-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="4d421-258">&ensp;Versão de atualização de inteligência de segurança: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="4d421-259">&ensp;Lançado: **22 de junho de 2020**</span><span class="sxs-lookup"><span data-stu-id="4d421-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="4d421-260">&ensp;Plataforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="4d421-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="4d421-261">&ensp;Mecanismo: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="4d421-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="4d421-262">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="4d421-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4d421-263">Novidades</span><span class="sxs-lookup"><span data-stu-id="4d421-263">What's new</span></span>

- <span data-ttu-id="4d421-264">Possibilidade de especificar o [local dos logs de suporte](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="4d421-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="4d421-265">Ignorar a verificação de captura agressiva no modo Passivo.</span><span class="sxs-lookup"><span data-stu-id="4d421-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="4d421-266">Permitir que o Defender atualize em conexões com metros</span><span class="sxs-lookup"><span data-stu-id="4d421-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="4d421-267">Ajuste de desempenho fixo quando o cache está desabilitado</span><span class="sxs-lookup"><span data-stu-id="4d421-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="4d421-268">Consulta de registro fixa</span><span class="sxs-lookup"><span data-stu-id="4d421-268">Fixed registry query</span></span> 
- <span data-ttu-id="4d421-269">Randomização de tempo de verificação fixa no ADMX</span><span class="sxs-lookup"><span data-stu-id="4d421-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="4d421-270">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="4d421-270">Known Issues</span></span>
<span data-ttu-id="4d421-271">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="4d421-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="4d421-272">Maio-2020 (plataforma: 4.18.2005.4 | Mecanismo: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="4d421-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="4d421-273">&ensp;Versão de atualização de inteligência de segurança: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="4d421-274">&ensp;Lançado: **26 de maio de 2020**</span><span class="sxs-lookup"><span data-stu-id="4d421-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="4d421-275">&ensp;Plataforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="4d421-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="4d421-276">&ensp;Mecanismo: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="4d421-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="4d421-277">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="4d421-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4d421-278">Novidades</span><span class="sxs-lookup"><span data-stu-id="4d421-278">What's new</span></span>

- <span data-ttu-id="4d421-279">Registro em log aprimorado para eventos de verificação</span><span class="sxs-lookup"><span data-stu-id="4d421-279">Improved logging for scan events</span></span>
- <span data-ttu-id="4d421-280">Melhor tratamento de falhas no modo de usuário.</span><span class="sxs-lookup"><span data-stu-id="4d421-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="4d421-281">Rastreamento de eventos adicionado para proteção contra adulteração</span><span class="sxs-lookup"><span data-stu-id="4d421-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="4d421-282">Envio de amostra AMSI corrigido</span><span class="sxs-lookup"><span data-stu-id="4d421-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="4d421-283">Bloqueio fixo da nuvem AMSI</span><span class="sxs-lookup"><span data-stu-id="4d421-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="4d421-284">Log de instalação de atualização de segurança fixa</span><span class="sxs-lookup"><span data-stu-id="4d421-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="4d421-285">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="4d421-285">Known Issues</span></span>
<span data-ttu-id="4d421-286">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="4d421-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="4d421-287">Abril-2020 (Plataforma: 4.18.2004.6 | Mecanismo: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="4d421-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="4d421-288">&ensp;Versão de atualização de inteligência de segurança: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="4d421-289">&ensp;Lançado: **30 de abril de 2020**</span><span class="sxs-lookup"><span data-stu-id="4d421-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="4d421-290">&ensp;Plataforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="4d421-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="4d421-291">&ensp;Mecanismo: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="4d421-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="4d421-292">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="4d421-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4d421-293">Novidades</span><span class="sxs-lookup"><span data-stu-id="4d421-293">What's new</span></span>
- <span data-ttu-id="4d421-294">Melhorias do WDfilter</span><span class="sxs-lookup"><span data-stu-id="4d421-294">WDfilter improvements</span></span>
- <span data-ttu-id="4d421-295">Adicionar mais dados de evento acionáveis para atacar eventos de detecção de redução de superfície</span><span class="sxs-lookup"><span data-stu-id="4d421-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="4d421-296">Informações de versão fixas em dados de diagnóstico e WMI</span><span class="sxs-lookup"><span data-stu-id="4d421-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="4d421-297">Versão da plataforma incorreta corrigida na interface do usuário após a atualização da plataforma</span><span class="sxs-lookup"><span data-stu-id="4d421-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="4d421-298">Intel de URL dinâmica para proteção contra ameaças sem arquivo</span><span class="sxs-lookup"><span data-stu-id="4d421-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="4d421-299">Recurso de verificação UEFI</span><span class="sxs-lookup"><span data-stu-id="4d421-299">UEFI scan capability</span></span>
- <span data-ttu-id="4d421-300">Estender o log para atualizações</span><span class="sxs-lookup"><span data-stu-id="4d421-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="4d421-301">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="4d421-301">Known Issues</span></span>
<span data-ttu-id="4d421-302">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="4d421-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="4d421-303">Março-2020 (Plataforma: 4.18.2003.8 | Mecanismo: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="4d421-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="4d421-304">&ensp;Versão de atualização de inteligência de segurança: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="4d421-305">&ensp;Lançado: **24 de março de 2020**</span><span class="sxs-lookup"><span data-stu-id="4d421-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="4d421-306">&ensp;Plataforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="4d421-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="4d421-307">&ensp;Mecanismo: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="4d421-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="4d421-308">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="4d421-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="4d421-309">Novidades</span><span class="sxs-lookup"><span data-stu-id="4d421-309">What's new</span></span>

- <span data-ttu-id="4d421-310">Opção de throttling de CPU adicionada ao [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="4d421-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="4d421-311">Melhorar a funcionalidade de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="4d421-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="4d421-312">reduzir o tempo de tempo de inteligência de segurança (5 minutos)</span><span class="sxs-lookup"><span data-stu-id="4d421-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="4d421-313">Estender a funcionalidade de log interno do mecanismo AMSI</span><span class="sxs-lookup"><span data-stu-id="4d421-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="4d421-314">Melhorar a notificação para bloqueio de processos</span><span class="sxs-lookup"><span data-stu-id="4d421-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="4d421-315">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="4d421-315">Known Issues</span></span>
<span data-ttu-id="4d421-316">[**Fixo**] Microsoft Defender Antivírus está ignorando arquivos ao executar uma verificação.</span><span class="sxs-lookup"><span data-stu-id="4d421-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="4d421-317">Fevereiro-2020 (Plataforma: - | Mecanismo: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="4d421-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="4d421-318">&ensp;Versão de atualização de inteligência de segurança: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="4d421-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="4d421-319">&ensp;Lançado: **25 de fevereiro de 2020**</span><span class="sxs-lookup"><span data-stu-id="4d421-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="4d421-320">&ensp;Plataforma/Cliente: **-**</span><span class="sxs-lookup"><span data-stu-id="4d421-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="4d421-321">&ensp;Mecanismo: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="4d421-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="4d421-322">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="4d421-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="4d421-323">Novidades</span><span class="sxs-lookup"><span data-stu-id="4d421-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="4d421-324">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="4d421-324">Known Issues</span></span>
<span data-ttu-id="4d421-325">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="4d421-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="4d421-326">Janeiro-2020 (Plataforma: 4.18.2001.10 | Mecanismo: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="4d421-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="4d421-327">Versão de atualização de inteligência de segurança: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="4d421-328">Lançado: **30 de janeiro de 2020**</span><span class="sxs-lookup"><span data-stu-id="4d421-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="4d421-329">Plataforma/Cliente: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="4d421-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="4d421-330">Mecanismo: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="4d421-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="4d421-331">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="4d421-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="4d421-332">Novidades</span><span class="sxs-lookup"><span data-stu-id="4d421-332">What's new</span></span>

- <span data-ttu-id="4d421-333">BSOD fixo no WS2016 com Exchange</span><span class="sxs-lookup"><span data-stu-id="4d421-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="4d421-334">Atualizações da plataforma de suporte quando o TMP é redirecionado para o caminho da rede</span><span class="sxs-lookup"><span data-stu-id="4d421-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="4d421-335">As versões de plataforma e mecanismo são [adicionadas ao WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="4d421-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="4d421-336">estender a atualização de assinatura de emergência para [o modo passivo](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="4d421-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="4d421-337">Corrigir trava 4.18.1911.3</span><span class="sxs-lookup"><span data-stu-id="4d421-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="4d421-338">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="4d421-338">Known Issues</span></span>

<span data-ttu-id="4d421-339">[**Fixo**] dispositivos [que](/windows-hardware/design/device-experiences/modern-standby) usam o modo de espera moderno podem ter uma trava com o driver de filtro Windows Defender que resulta em uma lacuna de proteção.</span><span class="sxs-lookup"><span data-stu-id="4d421-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="4d421-340">Os máquinas afetados aparecem para o cliente como não atualizados para a plataforma antimalware mais recente.</span><span class="sxs-lookup"><span data-stu-id="4d421-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="4d421-341">Esta atualização é:</span><span class="sxs-lookup"><span data-stu-id="4d421-341">This update is:</span></span>
> - <span data-ttu-id="4d421-342">necessário por dispositivos RS1 que executam a versão inferior da plataforma para dar suporte ao SHA2;</span><span class="sxs-lookup"><span data-stu-id="4d421-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="4d421-343">tem um sinalizador de reinicialização para sistemas que têm problemas de suspensão;</span><span class="sxs-lookup"><span data-stu-id="4d421-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="4d421-344">é re-lançado em abril de 2020 e não será superada por atualizações mais novas para manter a disponibilidade futura;</span><span class="sxs-lookup"><span data-stu-id="4d421-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="4d421-345">é categorizado como uma atualização devido ao requisito de reinicialização; e</span><span class="sxs-lookup"><span data-stu-id="4d421-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="4d421-346">só será oferecido com o [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="4d421-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="4d421-347">Novembro-2019 (plataforma: 4.18.1911.3 | Mecanismo: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="4d421-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="4d421-348">Versão de atualização de inteligência de segurança: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="4d421-349">Lançado: **7 de dezembro de 2019**</span><span class="sxs-lookup"><span data-stu-id="4d421-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="4d421-350">Plataforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="4d421-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="4d421-351">Mecanismo: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="4d421-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="4d421-352">Fase de suporte: **sem suporte**</span><span class="sxs-lookup"><span data-stu-id="4d421-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="4d421-353">Novidades</span><span class="sxs-lookup"><span data-stu-id="4d421-353">What's new</span></span>

- <span data-ttu-id="4d421-354">Nível de rastreamento De MpCmdRun fixo</span><span class="sxs-lookup"><span data-stu-id="4d421-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="4d421-355">Informações de versão fixas do WDFilter</span><span class="sxs-lookup"><span data-stu-id="4d421-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="4d421-356">Melhorar notificações (PUA)</span><span class="sxs-lookup"><span data-stu-id="4d421-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="4d421-357">adicionar logs MRT para dar suporte a arquivos</span><span class="sxs-lookup"><span data-stu-id="4d421-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="4d421-358">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="4d421-358">Known Issues</span></span>
<span data-ttu-id="4d421-359">Quando essa atualização é instalada, o dispositivo precisa do pacote de salto 4.10.2001.10 para poder atualizar para a versão mais recente da plataforma.</span><span class="sxs-lookup"><span data-stu-id="4d421-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="4d421-360">Microsoft Defender Antivírus plataforma</span><span class="sxs-lookup"><span data-stu-id="4d421-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="4d421-361">As atualizações de plataforma e mecanismo são fornecidas em uma cadência mensal.</span><span class="sxs-lookup"><span data-stu-id="4d421-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="4d421-362">Para ter suporte total, mantenha-se atualizado com as atualizações mais recentes da plataforma.</span><span class="sxs-lookup"><span data-stu-id="4d421-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="4d421-363">Nossa estrutura de suporte é dinâmica, evoluindo em duas fases, dependendo da disponibilidade da versão mais recente da plataforma:</span><span class="sxs-lookup"><span data-stu-id="4d421-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="4d421-364">Fase de manutenção de Atualizações **Críticas** e Segurança - Ao executar a versão mais recente da plataforma, você estará qualificado para receber atualizações de segurança e críticas para a plataforma anti-malware.</span><span class="sxs-lookup"><span data-stu-id="4d421-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="4d421-365">Fase de Suporte Técnico **(Somente)** - Depois que uma nova versão da plataforma for lançada, o suporte para versões mais antigas (N-2) será redução apenas para suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="4d421-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="4d421-366">As versões da plataforma anteriores ao N-2 não serão mais suportadas.\*</span><span class="sxs-lookup"><span data-stu-id="4d421-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="4d421-367">\*O suporte técnico continuará a ser fornecido para atualizações da versão Windows 10 versão do Windows 10 (consulte Versão da plataforma incluída com Windows 10 [versões](#platform-version-included-with-windows-10-releases)) para a versão mais recente da plataforma.</span><span class="sxs-lookup"><span data-stu-id="4d421-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="4d421-368">Durante a fase de suporte técnico (somente), incidentes de suporte comercialmente razoáveis serão fornecidos por meio do Serviço de Atendimento ao Cliente da Microsoft & Suporte e ofertas de suporte gerenciado da Microsoft (como o Suporte Premier).</span><span class="sxs-lookup"><span data-stu-id="4d421-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="4d421-369">Se um incidente de suporte exigir escalonamento para desenvolvimento para obter mais orientações, exigir uma atualização que não seja de segurança ou exigir uma atualização de segurança, os clientes serão solicitados a atualizar para a versão mais recente da plataforma ou uma atualização intermediária (\*).</span><span class="sxs-lookup"><span data-stu-id="4d421-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="4d421-370">Versão da plataforma incluída com Windows 10 versões</span><span class="sxs-lookup"><span data-stu-id="4d421-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="4d421-371">A tabela a seguir fornece as versões Microsoft Defender Antivírus plataforma e mecanismo que são enviadas com as versões Windows 10 versão mais recentes:</span><span class="sxs-lookup"><span data-stu-id="4d421-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="4d421-372">Windows 10 versão</span><span class="sxs-lookup"><span data-stu-id="4d421-372">Windows 10 release</span></span>  |<span data-ttu-id="4d421-373">Versão da plataforma</span><span class="sxs-lookup"><span data-stu-id="4d421-373">Platform version</span></span>  |<span data-ttu-id="4d421-374">Versão do mecanismo</span><span class="sxs-lookup"><span data-stu-id="4d421-374">Engine version</span></span> |<span data-ttu-id="4d421-375">Fase de suporte</span><span class="sxs-lookup"><span data-stu-id="4d421-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="4d421-376">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="4d421-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="4d421-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="4d421-377">4.18.1909.6</span></span> |<span data-ttu-id="4d421-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="4d421-378">1.1.17000.2</span></span> | <span data-ttu-id="4d421-379">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="4d421-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="4d421-380">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="4d421-380">1909  (19H2)</span></span> |<span data-ttu-id="4d421-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="4d421-381">4.18.1902.5</span></span> |<span data-ttu-id="4d421-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="4d421-382">1.1.16700.3</span></span> | <span data-ttu-id="4d421-383">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="4d421-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="4d421-384">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="4d421-384">1903  (19H1)</span></span> |<span data-ttu-id="4d421-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="4d421-385">4.18.1902.5</span></span> |<span data-ttu-id="4d421-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="4d421-386">1.1.15600.4</span></span> | <span data-ttu-id="4d421-387">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="4d421-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="4d421-388">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="4d421-388">1809  (RS5)</span></span> |<span data-ttu-id="4d421-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="4d421-389">4.18.1807.18075</span></span> |<span data-ttu-id="4d421-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="4d421-390">1.1.15000.2</span></span> | <span data-ttu-id="4d421-391">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="4d421-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="4d421-392">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="4d421-392">1803  (RS4)</span></span> |<span data-ttu-id="4d421-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="4d421-393">4.13.17134.1</span></span> |<span data-ttu-id="4d421-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="4d421-394">1.1.14600.4</span></span> | <span data-ttu-id="4d421-395">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="4d421-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="4d421-396">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="4d421-396">1709  (RS3)</span></span> |<span data-ttu-id="4d421-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="4d421-397">4.12.16299.15</span></span> |<span data-ttu-id="4d421-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="4d421-398">1.1.14104.0</span></span> | <span data-ttu-id="4d421-399">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="4d421-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="4d421-400">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="4d421-400">1703  (RS2)</span></span> |<span data-ttu-id="4d421-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="4d421-401">4.11.15603.2</span></span> |<span data-ttu-id="4d421-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="4d421-402">1.1.13504.0</span></span> | <span data-ttu-id="4d421-403">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="4d421-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="4d421-404">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="4d421-404">1607 (RS1)</span></span> |<span data-ttu-id="4d421-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="4d421-405">4.10.14393.3683</span></span> |<span data-ttu-id="4d421-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="4d421-406">1.1.12805.0</span></span> | <span data-ttu-id="4d421-407">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="4d421-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="4d421-408">Para Windows 10 informações de versão, consulte a planilha Windows de fatos do ciclo [de vida.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="4d421-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="4d421-409">Atualizações para Manutenção e Gerenciamento de Imagens de Implantação (DISM)</span><span class="sxs-lookup"><span data-stu-id="4d421-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="4d421-410">Recomendamos atualizar suas Windows 10 (Enterprise, Pro e edições Home), o Windows Server 2019 e Windows Server 2016 imagens de instalação do sistema operacional com as atualizações mais recentes de antivírus e antimalware.</span><span class="sxs-lookup"><span data-stu-id="4d421-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="4d421-411">Manter as imagens de instalação do sistema operacional atualizadas ajuda a evitar uma lacuna na proteção.</span><span class="sxs-lookup"><span data-stu-id="4d421-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="4d421-412">Para obter mais informações, consulte [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="4d421-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="4d421-413">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="4d421-413">1.1.2104.01</span></span></summary>

<span data-ttu-id="4d421-414">&ensp;Versão do pacote: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="4d421-414">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="4d421-415">&ensp;Versão da plataforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="4d421-415">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="4d421-416">&ensp;Versão do mecanismo: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="4d421-416">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="4d421-417">&ensp;Versão de assinatura: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-417">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="4d421-418">Correções</span><span class="sxs-lookup"><span data-stu-id="4d421-418">Fixes</span></span>
- <span data-ttu-id="4d421-419">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4d421-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="4d421-420">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="4d421-420">Additional information</span></span>
- <span data-ttu-id="4d421-421">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4d421-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="4d421-422">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="4d421-422">1.1.2103.01</span></span></summary>

<span data-ttu-id="4d421-423">&ensp;Versão do pacote: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="4d421-423">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="4d421-424">&ensp;Versão da plataforma: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="4d421-424">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="4d421-425">&ensp;Versão do mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="4d421-425">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="4d421-426">&ensp;Versão de assinatura: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-426">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="4d421-427">Correções</span><span class="sxs-lookup"><span data-stu-id="4d421-427">Fixes</span></span>
- <span data-ttu-id="4d421-428">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4d421-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="4d421-429">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="4d421-429">Additional information</span></span>
- <span data-ttu-id="4d421-430">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4d421-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="4d421-431">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="4d421-431">1.1.2102.03</span></span></summary>

<span data-ttu-id="4d421-432">&ensp;Versão do pacote: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="4d421-432">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="4d421-433">&ensp;Versão da plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="4d421-433">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="4d421-434">&ensp;Versão do mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="4d421-434">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="4d421-435">&ensp;Versão de assinatura: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-435">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="4d421-436">Correções</span><span class="sxs-lookup"><span data-stu-id="4d421-436">Fixes</span></span>
- <span data-ttu-id="4d421-437">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4d421-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="4d421-438">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="4d421-438">Additional information</span></span>
- <span data-ttu-id="4d421-439">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4d421-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="4d421-440">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="4d421-440">1.1.2101.02</span></span></summary>

<span data-ttu-id="4d421-441">&ensp;Versão do pacote: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="4d421-441">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="4d421-442">&ensp;Versão da plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="4d421-442">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="4d421-443">&ensp;Versão do mecanismo: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="4d421-443">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="4d421-444">&ensp;Versão de assinatura: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-444">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="4d421-445">Correções</span><span class="sxs-lookup"><span data-stu-id="4d421-445">Fixes</span></span>
- <span data-ttu-id="4d421-446">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4d421-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="4d421-447">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="4d421-447">Additional information</span></span>
- <span data-ttu-id="4d421-448">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4d421-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="4d421-449">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="4d421-449">1.1.2012.01</span></span></summary>

<span data-ttu-id="4d421-450">&ensp;Versão do pacote: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="4d421-450">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="4d421-451">&ensp;Versão da plataforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="4d421-451">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="4d421-452">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="4d421-452">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="4d421-453">&ensp;Versão de assinatura: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-453">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="4d421-454">Correções</span><span class="sxs-lookup"><span data-stu-id="4d421-454">Fixes</span></span>
- <span data-ttu-id="4d421-455">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4d421-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="4d421-456">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="4d421-456">Additional information</span></span>
- <span data-ttu-id="4d421-457">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4d421-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="4d421-458">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="4d421-458">1.1.2011.02</span></span></summary>

<span data-ttu-id="4d421-459">&ensp;Versão do pacote: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="4d421-459">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="4d421-460">&ensp;Versão da plataforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="4d421-460">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="4d421-461">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="4d421-461">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="4d421-462">&ensp;Versão de assinatura: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-462">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="4d421-463">Correções</span><span class="sxs-lookup"><span data-stu-id="4d421-463">Fixes</span></span>
- <span data-ttu-id="4d421-464">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4d421-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="4d421-465">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="4d421-465">Additional information</span></span>
- <span data-ttu-id="4d421-466">Assinaturas Microsoft Defender Antivírus atualizadas</span><span class="sxs-lookup"><span data-stu-id="4d421-466">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="4d421-467">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="4d421-467">1.1.2011.01</span></span></summary>

<span data-ttu-id="4d421-468">&ensp;Versão do pacote: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="4d421-468">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="4d421-469">&ensp;Versão da plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="4d421-469">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="4d421-470">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="4d421-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="4d421-471">&ensp;Versão de assinatura: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-471">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="4d421-472">Correções</span><span class="sxs-lookup"><span data-stu-id="4d421-472">Fixes</span></span>
- <span data-ttu-id="4d421-473">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4d421-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="4d421-474">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="4d421-474">Additional information</span></span>
- <span data-ttu-id="4d421-475">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4d421-475">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="4d421-476">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="4d421-476">1.1.2009.10</span></span></summary>

<span data-ttu-id="4d421-477">&ensp;Versão do pacote: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="4d421-477">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="4d421-478">&ensp;Versão da plataforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="4d421-478">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="4d421-479">&ensp;Versão do mecanismo: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="4d421-479">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="4d421-480">&ensp;Versão de assinatura: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="4d421-480">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="4d421-481">Correções</span><span class="sxs-lookup"><span data-stu-id="4d421-481">Fixes</span></span>
- <span data-ttu-id="4d421-482">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4d421-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="4d421-483">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="4d421-483">Additional information</span></span>
- <span data-ttu-id="4d421-484">Adicionado suporte para Windows 10 RS1 ou imagens de instalação posteriores do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="4d421-484">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="4d421-485">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="4d421-485">Additional resources</span></span>

| <span data-ttu-id="4d421-486">Artigo</span><span class="sxs-lookup"><span data-stu-id="4d421-486">Article</span></span> | <span data-ttu-id="4d421-487">Descrição</span><span class="sxs-lookup"><span data-stu-id="4d421-487">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="4d421-488">Atualização do Microsoft Defender para Windows de instalação do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="4d421-488">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="4d421-489">Revise os pacotes de atualização antimalware para as imagens de instalação do sistema operacional (arquivos WIM e VHD).</span><span class="sxs-lookup"><span data-stu-id="4d421-489">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="4d421-490">Obter Microsoft Defender Antivírus atualizações para Windows 10 (Enterprise, Pro e edições Home), Windows Server 2019 e Windows Server 2016 de instalação.</span><span class="sxs-lookup"><span data-stu-id="4d421-490">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="4d421-491">Gerenciar como as atualizações de proteção são baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="4d421-491">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="4d421-492">As atualizações de proteção podem ser entregues por meio de várias fontes.</span><span class="sxs-lookup"><span data-stu-id="4d421-492">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="4d421-493">Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="4d421-493">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="4d421-494">Você pode agendar quando as atualizações de proteção devem ser baixadas.</span><span class="sxs-lookup"><span data-stu-id="4d421-494">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="4d421-495">Gerenciar atualizações para pontos de extremidade que estão des date</span><span class="sxs-lookup"><span data-stu-id="4d421-495">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="4d421-496">Se um ponto de extremidade perder uma atualização ou uma verificação agendada, você poderá forçar uma atualização ou verificar na próxima vez que um usuário entrar.</span><span class="sxs-lookup"><span data-stu-id="4d421-496">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="4d421-497">Gerenciar atualizações aplicadas com base em evento</span><span class="sxs-lookup"><span data-stu-id="4d421-497">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="4d421-498">Você pode definir atualizações de proteção a serem baixadas na inicialização ou após determinados eventos de proteção entregues na nuvem.</span><span class="sxs-lookup"><span data-stu-id="4d421-498">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="4d421-499">Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)</span><span class="sxs-lookup"><span data-stu-id="4d421-499">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="4d421-500">Você pode especificar configurações, como se as atualizações devem ocorrer na energia da bateria, que são especialmente úteis para dispositivos móveis e máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="4d421-500">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
