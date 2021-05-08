---
title: Gerenciar atualizações do Microsoft Defender Antivírus e aplicar linhas de base
description: Gerencie como o Microsoft Defender Antivírus recebe atualizações de produtos e proteção.
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
ms.date: 05/06/2021
ms.openlocfilehash: 22a173d39c3ab8d1afd91a33b05e02e58da24aaa
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274551"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="d1480-104">Gerenciar atualizações do Microsoft Defender Antivírus e aplicar linhas de base</span><span class="sxs-lookup"><span data-stu-id="d1480-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="d1480-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d1480-105">**Applies to:**</span></span>

- [<span data-ttu-id="d1480-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d1480-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="d1480-107">Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="d1480-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="d1480-108">Há dois tipos de atualizações relacionadas a manter o Microsoft Defender Antivírus atualizado:</span><span class="sxs-lookup"><span data-stu-id="d1480-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="d1480-109">Atualizações de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="d1480-109">Security intelligence updates</span></span>
- <span data-ttu-id="d1480-110">Atualizações de produtos</span><span class="sxs-lookup"><span data-stu-id="d1480-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d1480-111">Manter o Microsoft Defender Antivírus atualizado é fundamental para garantir que seus dispositivos tenham a tecnologia e os recursos mais recentes necessários para proteger contra novas técnicas de malware e ataque.</span><span class="sxs-lookup"><span data-stu-id="d1480-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>
> 
> <span data-ttu-id="d1480-112">Certifique-se de atualizar sua proteção antivírus mesmo se o Microsoft Defender Antivírus estiver em execução no [modo passivo](./microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="d1480-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="d1480-113">Para ver o mecanismo, a plataforma e a data de assinatura mais atuais, visite as atualizações de inteligência de segurança do Microsoft Defender Antivírus e [outros antimalware da Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="d1480-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="d1480-114">Atualizações de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="d1480-114">Security intelligence updates</span></span>

<span data-ttu-id="d1480-115">O Microsoft Defender [Antivírus](cloud-protection-microsoft-defender-antivirus.md) usa proteção entregue na nuvem (também chamado de Serviço de Proteção Avançada da Microsoft ou MAPS) e baixa periodicamente atualizações de inteligência de segurança para fornecer proteção.</span><span class="sxs-lookup"><span data-stu-id="d1480-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="d1480-116">As atualizações são lançadas nos números KB abaixo:</span><span class="sxs-lookup"><span data-stu-id="d1480-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="d1480-117">Microsoft Defender Antivírus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="d1480-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="d1480-118">Proteção do Ponto de Extremidade do System Center: KB2461484</span><span class="sxs-lookup"><span data-stu-id="d1480-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="d1480-119">A proteção entregue na nuvem está sempre ativa e requer uma conexão ativa com a Internet para funcionar.</span><span class="sxs-lookup"><span data-stu-id="d1480-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="d1480-120">As atualizações de inteligência de segurança ocorrem em uma cadência agendada (configurável por meio da política).</span><span class="sxs-lookup"><span data-stu-id="d1480-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="d1480-121">Para obter mais informações, [consulte Use Microsoft cloud-provided protection in Microsoft Defender Antivírus](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="d1480-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="d1480-122">Para ver uma lista de atualizações recentes de inteligência de segurança, consulte Atualizações de inteligência de segurança para [o Microsoft Defender Antivírus e outros antimalware da Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="d1480-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="d1480-123">As atualizações do mecanismo são incluídas com atualizações de inteligência de segurança e são lançadas em uma cadência mensal.</span><span class="sxs-lookup"><span data-stu-id="d1480-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="d1480-124">Atualizações de produtos</span><span class="sxs-lookup"><span data-stu-id="d1480-124">Product updates</span></span>

<span data-ttu-id="d1480-125">O Microsoft Defender Antivírus exige atualizações mensais [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) *(conhecidas* como atualizações de plataforma) e receberá atualizações de recursos importantes juntamente com versões do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d1480-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="d1480-126">Você pode gerenciar a distribuição de atualizações por meio de um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="d1480-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="d1480-127">Serviço de Atualização do Windows Server (WSUS)</span><span class="sxs-lookup"><span data-stu-id="d1480-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="d1480-128">Gerenciador de Configuração do Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="d1480-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="d1480-129">O método comum que você usa para implantar atualizações da Microsoft e do Windows nos pontos de extremidade em sua rede.</span><span class="sxs-lookup"><span data-stu-id="d1480-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="d1480-130">Para obter mais informações, consulte Gerenciar as fontes para atualizações de proteção [do Microsoft Defender Antivírus.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="d1480-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="d1480-131">As atualizações mensais são lançadas em fases, resultando em vários pacotes visíveis em seus [Serviços de Atualização do Servidor de Janelas.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="d1480-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="d1480-132">Versões mensais de plataforma e mecanismo</span><span class="sxs-lookup"><span data-stu-id="d1480-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="d1480-133">Para obter informações sobre como atualizar ou instalar a atualização da plataforma, consulte [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="d1480-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="d1480-134">Todas as nossas atualizações contêm</span><span class="sxs-lookup"><span data-stu-id="d1480-134">All our updates contain</span></span> 
- <span data-ttu-id="d1480-135">melhorias de desempenho;</span><span class="sxs-lookup"><span data-stu-id="d1480-135">performance improvements;</span></span>
- <span data-ttu-id="d1480-136">melhorias de capacidade de serviço; e</span><span class="sxs-lookup"><span data-stu-id="d1480-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="d1480-137">melhorias de integração (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="d1480-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="d1480-138">Abril-2021 (Plataforma: 4.19.2104.9| Mecanismo: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="d1480-138">April-2021 (Platform: 4.19.2104.9| Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="d1480-139">&ensp;Versão de atualização de inteligência de segurança: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-139">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="d1480-140">&ensp;Lançado: **1º de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="d1480-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="d1480-141">&ensp;Plataforma: **4.19.2104.9**</span><span class="sxs-lookup"><span data-stu-id="d1480-141">&ensp;Platform: **4.19.2104.9**</span></span>  
<span data-ttu-id="d1480-142">&ensp;Mecanismo: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="d1480-142">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="d1480-143">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="d1480-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d1480-144">Novidades</span><span class="sxs-lookup"><span data-stu-id="d1480-144">What's new</span></span>
- <span data-ttu-id="d1480-145">Lógica adicional de monitoramento de comportamento</span><span class="sxs-lookup"><span data-stu-id="d1480-145">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="d1480-146">Detecção aprimorada do keylogger do modo kernel</span><span class="sxs-lookup"><span data-stu-id="d1480-146">Improved kernel mode keylogger detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="d1480-147">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="d1480-147">Known Issues</span></span>
<span data-ttu-id="d1480-148">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="d1480-148">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="d1480-149">Março-2021 (plataforma: 4.19.2103.7 | Mecanismo: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="d1480-149">March-2021 (Platform: 4.19.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="d1480-150">&ensp;Versão de atualização de inteligência de segurança: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-150">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="d1480-151">&ensp;Lançado: **1º de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="d1480-151">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="d1480-152">&ensp;Plataforma: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="d1480-152">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="d1480-153">&ensp;Mecanismo: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="d1480-153">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="d1480-154">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="d1480-154">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d1480-155">Novidades</span><span class="sxs-lookup"><span data-stu-id="d1480-155">What's new</span></span>

- <span data-ttu-id="d1480-156">Melhoria no mecanismo de Monitoramento de Comportamento</span><span class="sxs-lookup"><span data-stu-id="d1480-156">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="d1480-157">Mitigações de ataques de força bruta de rede expandida</span><span class="sxs-lookup"><span data-stu-id="d1480-157">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="d1480-158">Geração adicional de eventos de tentativa de adulteração com falha quando [a Proteção contra Adulteração](prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada</span><span class="sxs-lookup"><span data-stu-id="d1480-158">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="d1480-159">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="d1480-159">Known Issues</span></span>
<span data-ttu-id="d1480-160">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="d1480-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="d1480-161">Fevereiro-2021 (plataforma: 4.19.2102.3 | Mecanismo: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="d1480-161">February-2021 (Platform: 4.19.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="d1480-162">&ensp;Versão de atualização de inteligência de segurança: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-162">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="d1480-163">&ensp;Lançado: **9 de março de 2021**</span><span class="sxs-lookup"><span data-stu-id="d1480-163">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="d1480-164">&ensp;Plataforma: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="d1480-164">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="d1480-165">&ensp;Mecanismo: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="d1480-165">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="d1480-166">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="d1480-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d1480-167">Novidades</span><span class="sxs-lookup"><span data-stu-id="d1480-167">What's new</span></span>

- <span data-ttu-id="d1480-168">Recuperação aprimorada do serviço por meio [da proteção contra violações](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="d1480-168">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="d1480-169">Estender escopo de proteção contra violações</span><span class="sxs-lookup"><span data-stu-id="d1480-169">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="d1480-170">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="d1480-170">Known Issues</span></span>
<span data-ttu-id="d1480-171">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="d1480-171">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="d1480-172">Atualizações de versão anterior: Suporte técnico somente a atualização</span><span class="sxs-lookup"><span data-stu-id="d1480-172">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="d1480-173">Depois que uma nova versão de pacote é lançada, o suporte para as duas versões anteriores é reduzido apenas ao suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="d1480-173">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="d1480-174">Versões anteriores às listadas nesta seção são fornecidas apenas para suporte técnico de atualização.</span><span class="sxs-lookup"><span data-stu-id="d1480-174">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="d1480-175">Janeiro-2021 (Plataforma: 4.18.2101.9 | Mecanismo: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="d1480-175">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="d1480-176">&ensp;Versão de atualização de inteligência de segurança: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-176">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="d1480-177">&ensp;Lançado: **2 de fevereiro de 2021**</span><span class="sxs-lookup"><span data-stu-id="d1480-177">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="d1480-178">&ensp;Plataforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="d1480-178">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="d1480-179">&ensp;Mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="d1480-179">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="d1480-180">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="d1480-180">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d1480-181">Novidades</span><span class="sxs-lookup"><span data-stu-id="d1480-181">What's new</span></span>

- <span data-ttu-id="d1480-182">Melhorias na detecção de exploração de shellcode</span><span class="sxs-lookup"><span data-stu-id="d1480-182">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="d1480-183">Maior visibilidade para tentativas de roubo de credenciais</span><span class="sxs-lookup"><span data-stu-id="d1480-183">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="d1480-184">Melhorias nos recursos anti-amperes nos serviços do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="d1480-184">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="d1480-185">Suporte aprimorado para ARM emulação x64</span><span class="sxs-lookup"><span data-stu-id="d1480-185">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="d1480-186">Correção: a notificação de bloqueio de EDR permanece no histórico de ameaças depois que a proteção em tempo real realizou a detecção inicial</span><span class="sxs-lookup"><span data-stu-id="d1480-186">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="d1480-187">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="d1480-187">Known Issues</span></span>
<span data-ttu-id="d1480-188">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="d1480-188">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="d1480-189">Novembro-2020 (Plataforma: 4.18.2011.6 | Mecanismo: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="d1480-189">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="d1480-190">&ensp;Versão de atualização de inteligência de segurança: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-190">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="d1480-191">&ensp;Lançado: **03 de dezembro de 2020**</span><span class="sxs-lookup"><span data-stu-id="d1480-191">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="d1480-192">&ensp;Plataforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="d1480-192">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="d1480-193">&ensp;Mecanismo: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="d1480-193">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="d1480-194">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="d1480-194">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d1480-195">Novidades</span><span class="sxs-lookup"><span data-stu-id="d1480-195">What's new</span></span>

- <span data-ttu-id="d1480-196">Registro em log de suporte ao status [do SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) aprimorado</span><span class="sxs-lookup"><span data-stu-id="d1480-196">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="d1480-197">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="d1480-197">Known Issues</span></span>
<span data-ttu-id="d1480-198">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="d1480-198">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="d1480-199">Outubro-2020 (Plataforma: 4.18.2010.7 | Mecanismo: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="d1480-199">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="d1480-200">&ensp;Versão de atualização de inteligência de segurança: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-200">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="d1480-201">&ensp;Lançado: **29 de outubro de 2020**</span><span class="sxs-lookup"><span data-stu-id="d1480-201">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="d1480-202">&ensp;Plataforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="d1480-202">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="d1480-203">&ensp;Mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="d1480-203">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="d1480-204">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="d1480-204">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d1480-205">Novidades</span><span class="sxs-lookup"><span data-stu-id="d1480-205">What's new</span></span>

- <span data-ttu-id="d1480-206">Novas descrições para categorias de ameaças especiais</span><span class="sxs-lookup"><span data-stu-id="d1480-206">New descriptions for special threat categories</span></span>
- <span data-ttu-id="d1480-207">Recursos de emulação aprimorados</span><span class="sxs-lookup"><span data-stu-id="d1480-207">Improved emulation capabilities</span></span>
- <span data-ttu-id="d1480-208">Recursos de permitir/bloquear endereço de host aprimorados</span><span class="sxs-lookup"><span data-stu-id="d1480-208">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="d1480-209">Nova opção no CSP do Defender para Ignorar a mesclação de exclusões de usuários locais</span><span class="sxs-lookup"><span data-stu-id="d1480-209">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="d1480-210">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="d1480-210">Known Issues</span></span>

<span data-ttu-id="d1480-211">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="d1480-211">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="d1480-212">Setembro-2020 (Plataforma: 4.18.2009.7 | Mecanismo: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="d1480-212">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="d1480-213">&ensp;Versão de atualização de inteligência de segurança: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-213">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="d1480-214">&ensp;Lançado: **01 de outubro de 2020**</span><span class="sxs-lookup"><span data-stu-id="d1480-214">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="d1480-215">&ensp;Plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="d1480-215">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="d1480-216">&ensp;Mecanismo: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="d1480-216">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="d1480-217">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="d1480-217">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d1480-218">Novidades</span><span class="sxs-lookup"><span data-stu-id="d1480-218">What's new</span></span>

- <span data-ttu-id="d1480-219">Permissões de administrador são necessárias para restaurar arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="d1480-219">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="d1480-220">Eventos formatados xml agora são suportados</span><span class="sxs-lookup"><span data-stu-id="d1480-220">XML formatted events are now supported</span></span>
- <span data-ttu-id="d1480-221">Suporte a CSP para ignorar mesclações de exclusão</span><span class="sxs-lookup"><span data-stu-id="d1480-221">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="d1480-222">Novas interfaces de gerenciamento para:</span><span class="sxs-lookup"><span data-stu-id="d1480-222">New management interfaces for:</span></span>
   - <span data-ttu-id="d1480-223">Inspeção UDP</span><span class="sxs-lookup"><span data-stu-id="d1480-223">UDP Inspection</span></span>
   - <span data-ttu-id="d1480-224">Proteção de Rede no Server 2019</span><span class="sxs-lookup"><span data-stu-id="d1480-224">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="d1480-225">Exclusões de endereço IP para Proteção de Rede</span><span class="sxs-lookup"><span data-stu-id="d1480-225">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="d1480-226">Visibilidade aprimorada nas medições do TPM</span><span class="sxs-lookup"><span data-stu-id="d1480-226">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="d1480-227">Verificação aprimorada do módulo VBA do Office</span><span class="sxs-lookup"><span data-stu-id="d1480-227">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="d1480-228">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="d1480-228">Known Issues</span></span>

<span data-ttu-id="d1480-229">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="d1480-229">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="d1480-230">Agosto-2020 (plataforma: 4.18.2008.9 | Mecanismo: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="d1480-230">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="d1480-231">&ensp;Versão de atualização de inteligência de segurança: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-231">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="d1480-232">&ensp;Lançado: **27 de agosto de 2020**</span><span class="sxs-lookup"><span data-stu-id="d1480-232">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="d1480-233">&ensp;Plataforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="d1480-233">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="d1480-234">&ensp;Mecanismo: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="d1480-234">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="d1480-235">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="d1480-235">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="d1480-236">Novidades</span><span class="sxs-lookup"><span data-stu-id="d1480-236">What's new</span></span>

- <span data-ttu-id="d1480-237">Adicionar mais eventos de telemetria</span><span class="sxs-lookup"><span data-stu-id="d1480-237">Add more telemetry events</span></span>
- <span data-ttu-id="d1480-238">Telemetria de eventos de verificação aprimorada</span><span class="sxs-lookup"><span data-stu-id="d1480-238">Improved scan event telemetry</span></span>
- <span data-ttu-id="d1480-239">Monitoramento de comportamento aprimorado para verificações de memória</span><span class="sxs-lookup"><span data-stu-id="d1480-239">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="d1480-240">Verificação de fluxos de macros aprimorados</span><span class="sxs-lookup"><span data-stu-id="d1480-240">Improved macro streams scanning</span></span>
- <span data-ttu-id="d1480-241">Adicionado `AMRunningMode` ao cmdlet Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="d1480-241">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="d1480-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) é ignorado.</span><span class="sxs-lookup"><span data-stu-id="d1480-242">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="d1480-243">O Microsoft Defender Antivírus automaticamente se desliga quando detecta outro programa antivírus.</span><span class="sxs-lookup"><span data-stu-id="d1480-243">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="d1480-244">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="d1480-244">Known Issues</span></span>
<span data-ttu-id="d1480-245">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="d1480-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="d1480-246">Julho-2020 (Plataforma: 4.18.2007.8 | Mecanismo: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="d1480-246">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="d1480-247">&ensp;Versão de atualização de inteligência de segurança: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-247">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="d1480-248">&ensp;Lançado: **28 de julho de 2020**</span><span class="sxs-lookup"><span data-stu-id="d1480-248">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="d1480-249">&ensp;Plataforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="d1480-249">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="d1480-250">&ensp;Mecanismo: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="d1480-250">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="d1480-251">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="d1480-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d1480-252">Novidades</span><span class="sxs-lookup"><span data-stu-id="d1480-252">What's new</span></span>

- <span data-ttu-id="d1480-253">Telemetria aprimorada para BITS</span><span class="sxs-lookup"><span data-stu-id="d1480-253">Improved telemetry for BITS</span></span>
- <span data-ttu-id="d1480-254">Validação aprimorada de certificado de assinatura de código Authenticode</span><span class="sxs-lookup"><span data-stu-id="d1480-254">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="d1480-255">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="d1480-255">Known Issues</span></span>
<span data-ttu-id="d1480-256">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="d1480-256">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="d1480-257">Junho-2020 (Plataforma: 4.18.2006.10 | Mecanismo: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="d1480-257">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="d1480-258">&ensp;Versão de atualização de inteligência de segurança: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-258">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="d1480-259">&ensp;Lançado: **22 de junho de 2020**</span><span class="sxs-lookup"><span data-stu-id="d1480-259">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="d1480-260">&ensp;Plataforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="d1480-260">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="d1480-261">&ensp;Mecanismo: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="d1480-261">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="d1480-262">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="d1480-262">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d1480-263">Novidades</span><span class="sxs-lookup"><span data-stu-id="d1480-263">What's new</span></span>

- <span data-ttu-id="d1480-264">Possibilidade de especificar o [local dos logs de suporte](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="d1480-264">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="d1480-265">Ignorar a verificação de captura agressiva no modo Passivo.</span><span class="sxs-lookup"><span data-stu-id="d1480-265">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="d1480-266">Permitir que o Defender atualize em conexões com metros</span><span class="sxs-lookup"><span data-stu-id="d1480-266">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="d1480-267">Ajuste de desempenho fixo quando o cache está desabilitado</span><span class="sxs-lookup"><span data-stu-id="d1480-267">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="d1480-268">Consulta de registro fixa</span><span class="sxs-lookup"><span data-stu-id="d1480-268">Fixed registry query</span></span> 
- <span data-ttu-id="d1480-269">Randomização de tempo de verificação fixa no ADMX</span><span class="sxs-lookup"><span data-stu-id="d1480-269">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="d1480-270">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="d1480-270">Known Issues</span></span>
<span data-ttu-id="d1480-271">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="d1480-271">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="d1480-272">Maio-2020 (plataforma: 4.18.2005.4 | Mecanismo: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="d1480-272">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="d1480-273">&ensp;Versão de atualização de inteligência de segurança: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-273">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="d1480-274">&ensp;Lançado: **26 de maio de 2020**</span><span class="sxs-lookup"><span data-stu-id="d1480-274">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="d1480-275">&ensp;Plataforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="d1480-275">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="d1480-276">&ensp;Mecanismo: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="d1480-276">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="d1480-277">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="d1480-277">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d1480-278">Novidades</span><span class="sxs-lookup"><span data-stu-id="d1480-278">What's new</span></span>

- <span data-ttu-id="d1480-279">Registro em log aprimorado para eventos de verificação</span><span class="sxs-lookup"><span data-stu-id="d1480-279">Improved logging for scan events</span></span>
- <span data-ttu-id="d1480-280">Melhor tratamento de falhas no modo de usuário.</span><span class="sxs-lookup"><span data-stu-id="d1480-280">Improved user mode crash handling.</span></span>
- <span data-ttu-id="d1480-281">Rastreamento de eventos adicionado para proteção contra adulteração</span><span class="sxs-lookup"><span data-stu-id="d1480-281">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="d1480-282">Envio de amostra AMSI corrigido</span><span class="sxs-lookup"><span data-stu-id="d1480-282">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="d1480-283">Bloqueio fixo da nuvem AMSI</span><span class="sxs-lookup"><span data-stu-id="d1480-283">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="d1480-284">Log de instalação de atualização de segurança fixa</span><span class="sxs-lookup"><span data-stu-id="d1480-284">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="d1480-285">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="d1480-285">Known Issues</span></span>
<span data-ttu-id="d1480-286">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="d1480-286">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="d1480-287">Abril-2020 (Plataforma: 4.18.2004.6 | Mecanismo: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="d1480-287">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="d1480-288">&ensp;Versão de atualização de inteligência de segurança: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-288">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="d1480-289">&ensp;Lançado: **30 de abril de 2020**</span><span class="sxs-lookup"><span data-stu-id="d1480-289">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="d1480-290">&ensp;Plataforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="d1480-290">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="d1480-291">&ensp;Mecanismo: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="d1480-291">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="d1480-292">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="d1480-292">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d1480-293">Novidades</span><span class="sxs-lookup"><span data-stu-id="d1480-293">What's new</span></span>
- <span data-ttu-id="d1480-294">Melhorias do WDfilter</span><span class="sxs-lookup"><span data-stu-id="d1480-294">WDfilter improvements</span></span>
- <span data-ttu-id="d1480-295">Adicionar mais dados de evento acionáveis para atacar eventos de detecção de redução de superfície</span><span class="sxs-lookup"><span data-stu-id="d1480-295">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="d1480-296">Informações de versão fixas em dados de diagnóstico e WMI</span><span class="sxs-lookup"><span data-stu-id="d1480-296">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="d1480-297">Versão da plataforma incorreta corrigida na interface do usuário após a atualização da plataforma</span><span class="sxs-lookup"><span data-stu-id="d1480-297">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="d1480-298">Intel de URL dinâmica para proteção contra ameaças sem arquivo</span><span class="sxs-lookup"><span data-stu-id="d1480-298">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="d1480-299">Recurso de verificação UEFI</span><span class="sxs-lookup"><span data-stu-id="d1480-299">UEFI scan capability</span></span>
- <span data-ttu-id="d1480-300">Estender o log para atualizações</span><span class="sxs-lookup"><span data-stu-id="d1480-300">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="d1480-301">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="d1480-301">Known Issues</span></span>
<span data-ttu-id="d1480-302">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="d1480-302">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="d1480-303">Março-2020 (Plataforma: 4.18.2003.8 | Mecanismo: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="d1480-303">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="d1480-304">&ensp;Versão de atualização de inteligência de segurança: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-304">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="d1480-305">&ensp;Lançado: **24 de março de 2020**</span><span class="sxs-lookup"><span data-stu-id="d1480-305">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="d1480-306">&ensp;Plataforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="d1480-306">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="d1480-307">&ensp;Mecanismo: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="d1480-307">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="d1480-308">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="d1480-308">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="d1480-309">Novidades</span><span class="sxs-lookup"><span data-stu-id="d1480-309">What's new</span></span>

- <span data-ttu-id="d1480-310">Opção de throttling de CPU adicionada ao [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d1480-310">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="d1480-311">Melhorar a funcionalidade de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="d1480-311">Improve diagnostic capability</span></span>
- <span data-ttu-id="d1480-312">reduzir o tempo de tempo de inteligência de segurança (5 minutos)</span><span class="sxs-lookup"><span data-stu-id="d1480-312">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="d1480-313">Estender a funcionalidade de log interno do mecanismo AMSI</span><span class="sxs-lookup"><span data-stu-id="d1480-313">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="d1480-314">Melhorar a notificação para bloqueio de processos</span><span class="sxs-lookup"><span data-stu-id="d1480-314">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="d1480-315">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="d1480-315">Known Issues</span></span>
<span data-ttu-id="d1480-316">[**Fixo**] O Microsoft Defender Antivírus está ignorando arquivos ao executar uma verificação.</span><span class="sxs-lookup"><span data-stu-id="d1480-316">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="d1480-317">Fevereiro-2020 (Plataforma: - | Mecanismo: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="d1480-317">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="d1480-318">&ensp;Versão de atualização de inteligência de segurança: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="d1480-318">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="d1480-319">&ensp;Lançado: **25 de fevereiro de 2020**</span><span class="sxs-lookup"><span data-stu-id="d1480-319">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="d1480-320">&ensp;Plataforma/Cliente: **-**</span><span class="sxs-lookup"><span data-stu-id="d1480-320">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="d1480-321">&ensp;Mecanismo: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="d1480-321">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="d1480-322">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="d1480-322">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="d1480-323">Novidades</span><span class="sxs-lookup"><span data-stu-id="d1480-323">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="d1480-324">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="d1480-324">Known Issues</span></span>
<span data-ttu-id="d1480-325">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="d1480-325">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="d1480-326">Janeiro-2020 (Plataforma: 4.18.2001.10 | Mecanismo: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="d1480-326">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="d1480-327">Versão de atualização de inteligência de segurança: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-327">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="d1480-328">Lançado: **30 de janeiro de 2020**</span><span class="sxs-lookup"><span data-stu-id="d1480-328">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="d1480-329">Plataforma/Cliente: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="d1480-329">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="d1480-330">Mecanismo: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="d1480-330">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="d1480-331">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="d1480-331">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="d1480-332">Novidades</span><span class="sxs-lookup"><span data-stu-id="d1480-332">What's new</span></span>

- <span data-ttu-id="d1480-333">BSOD fixo no WS2016 com o Exchange</span><span class="sxs-lookup"><span data-stu-id="d1480-333">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="d1480-334">Atualizações da plataforma de suporte quando o TMP é redirecionado para o caminho da rede</span><span class="sxs-lookup"><span data-stu-id="d1480-334">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="d1480-335">As versões de plataforma e mecanismo são [adicionadas ao WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="d1480-335">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="d1480-336">estender a atualização de assinatura de emergência para [o modo passivo](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="d1480-336">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="d1480-337">Corrigir trava 4.18.1911.3</span><span class="sxs-lookup"><span data-stu-id="d1480-337">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="d1480-338">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="d1480-338">Known Issues</span></span>

<span data-ttu-id="d1480-339">[**Corrigido**] [dispositivos](/windows-hardware/design/device-experiences/modern-standby) que usam o modo de espera moderno podem ter uma trava com o driver de filtro Windows Defender que resulta em uma lacuna de proteção.</span><span class="sxs-lookup"><span data-stu-id="d1480-339">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="d1480-340">Os máquinas afetados aparecem para o cliente como não atualizados para a plataforma antimalware mais recente.</span><span class="sxs-lookup"><span data-stu-id="d1480-340">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="d1480-341">Esta atualização é:</span><span class="sxs-lookup"><span data-stu-id="d1480-341">This update is:</span></span>
> - <span data-ttu-id="d1480-342">necessário por dispositivos RS1 que executam a versão inferior da plataforma para dar suporte ao SHA2;</span><span class="sxs-lookup"><span data-stu-id="d1480-342">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="d1480-343">tem um sinalizador de reinicialização para sistemas que têm problemas de suspensão;</span><span class="sxs-lookup"><span data-stu-id="d1480-343">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="d1480-344">é re-lançado em abril de 2020 e não será superada por atualizações mais novas para manter a disponibilidade futura;</span><span class="sxs-lookup"><span data-stu-id="d1480-344">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="d1480-345">é categorizado como uma atualização devido ao requisito de reinicialização; e</span><span class="sxs-lookup"><span data-stu-id="d1480-345">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="d1480-346">só é oferecido com [o Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="d1480-346">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="d1480-347">Novembro-2019 (plataforma: 4.18.1911.3 | Mecanismo: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="d1480-347">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="d1480-348">Versão de atualização de inteligência de segurança: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-348">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="d1480-349">Lançado: **7 de dezembro de 2019**</span><span class="sxs-lookup"><span data-stu-id="d1480-349">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="d1480-350">Plataforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="d1480-350">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="d1480-351">Mecanismo: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="d1480-351">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="d1480-352">Fase de suporte: **sem suporte**</span><span class="sxs-lookup"><span data-stu-id="d1480-352">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="d1480-353">Novidades</span><span class="sxs-lookup"><span data-stu-id="d1480-353">What's new</span></span>

- <span data-ttu-id="d1480-354">Nível de rastreamento De MpCmdRun fixo</span><span class="sxs-lookup"><span data-stu-id="d1480-354">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="d1480-355">Informações de versão fixas do WDFilter</span><span class="sxs-lookup"><span data-stu-id="d1480-355">Fixed WDFilter version info</span></span>
- <span data-ttu-id="d1480-356">Melhorar notificações (PUA)</span><span class="sxs-lookup"><span data-stu-id="d1480-356">Improve notifications (PUA)</span></span>
- <span data-ttu-id="d1480-357">adicionar logs MRT para dar suporte a arquivos</span><span class="sxs-lookup"><span data-stu-id="d1480-357">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="d1480-358">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="d1480-358">Known Issues</span></span>
<span data-ttu-id="d1480-359">Quando essa atualização é instalada, o dispositivo precisa do pacote de salto 4.10.2001.10 para poder atualizar para a versão mais recente da plataforma.</span><span class="sxs-lookup"><span data-stu-id="d1480-359">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="d1480-360">Suporte à plataforma Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="d1480-360">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="d1480-361">As atualizações de plataforma e mecanismo são fornecidas em uma cadência mensal.</span><span class="sxs-lookup"><span data-stu-id="d1480-361">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="d1480-362">Para ter suporte total, mantenha-se atualizado com as atualizações mais recentes da plataforma.</span><span class="sxs-lookup"><span data-stu-id="d1480-362">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="d1480-363">Nossa estrutura de suporte é dinâmica, evoluindo em duas fases, dependendo da disponibilidade da versão mais recente da plataforma:</span><span class="sxs-lookup"><span data-stu-id="d1480-363">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="d1480-364">Fase de manutenção de Atualizações **Críticas** e Segurança - Ao executar a versão mais recente da plataforma, você estará qualificado para receber atualizações de segurança e críticas para a plataforma anti-malware.</span><span class="sxs-lookup"><span data-stu-id="d1480-364">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="d1480-365">Fase de Suporte Técnico **(Somente)** - Depois que uma nova versão da plataforma for lançada, o suporte para versões mais antigas (N-2) será redução apenas para suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="d1480-365">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="d1480-366">As versões da plataforma anteriores ao N-2 não serão mais suportadas.\*</span><span class="sxs-lookup"><span data-stu-id="d1480-366">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="d1480-367">\* O suporte técnico continuará a ser fornecido para atualizações da versão de lançamento do Windows 10 (consulte Versão da plataforma incluída com versões do [Windows 10](#platform-version-included-with-windows-10-releases)) para a versão mais recente da plataforma.</span><span class="sxs-lookup"><span data-stu-id="d1480-367">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="d1480-368">Durante a fase de suporte técnico (somente), incidentes de suporte comercialmente razoáveis serão fornecidos por meio do Serviço de Atendimento ao Cliente da Microsoft & Suporte e ofertas de suporte gerenciado da Microsoft (como o Suporte Premier).</span><span class="sxs-lookup"><span data-stu-id="d1480-368">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="d1480-369">Se um incidente de suporte exigir escalonamento para desenvolvimento para obter mais orientações, exigir uma atualização que não seja de segurança ou exigir uma atualização de segurança, os clientes serão solicitados a atualizar para a versão mais recente da plataforma ou uma atualização intermediária (\*).</span><span class="sxs-lookup"><span data-stu-id="d1480-369">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="d1480-370">Versão da plataforma incluída nas versões do Windows 10</span><span class="sxs-lookup"><span data-stu-id="d1480-370">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="d1480-371">A tabela a seguir fornece as versões de mecanismo e plataforma do Microsoft Defender Antivírus fornecidas com as versões mais recentes do Windows 10:</span><span class="sxs-lookup"><span data-stu-id="d1480-371">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="d1480-372">Versão do Windows 10</span><span class="sxs-lookup"><span data-stu-id="d1480-372">Windows 10 release</span></span>  |<span data-ttu-id="d1480-373">Versão da plataforma</span><span class="sxs-lookup"><span data-stu-id="d1480-373">Platform version</span></span>  |<span data-ttu-id="d1480-374">Versão do mecanismo</span><span class="sxs-lookup"><span data-stu-id="d1480-374">Engine version</span></span> |<span data-ttu-id="d1480-375">Fase de suporte</span><span class="sxs-lookup"><span data-stu-id="d1480-375">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="d1480-376">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="d1480-376">2004  (20H1/20H2)</span></span> |<span data-ttu-id="d1480-377">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="d1480-377">4.18.1909.6</span></span> |<span data-ttu-id="d1480-378">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="d1480-378">1.1.17000.2</span></span> | <span data-ttu-id="d1480-379">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="d1480-379">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d1480-380">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="d1480-380">1909  (19H2)</span></span> |<span data-ttu-id="d1480-381">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="d1480-381">4.18.1902.5</span></span> |<span data-ttu-id="d1480-382">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="d1480-382">1.1.16700.3</span></span> | <span data-ttu-id="d1480-383">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="d1480-383">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d1480-384">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="d1480-384">1903  (19H1)</span></span> |<span data-ttu-id="d1480-385">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="d1480-385">4.18.1902.5</span></span> |<span data-ttu-id="d1480-386">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="d1480-386">1.1.15600.4</span></span> | <span data-ttu-id="d1480-387">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="d1480-387">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d1480-388">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="d1480-388">1809  (RS5)</span></span> |<span data-ttu-id="d1480-389">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="d1480-389">4.18.1807.18075</span></span> |<span data-ttu-id="d1480-390">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="d1480-390">1.1.15000.2</span></span> | <span data-ttu-id="d1480-391">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="d1480-391">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d1480-392">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="d1480-392">1803  (RS4)</span></span> |<span data-ttu-id="d1480-393">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="d1480-393">4.13.17134.1</span></span> |<span data-ttu-id="d1480-394">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="d1480-394">1.1.14600.4</span></span> | <span data-ttu-id="d1480-395">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="d1480-395">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d1480-396">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="d1480-396">1709  (RS3)</span></span> |<span data-ttu-id="d1480-397">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="d1480-397">4.12.16299.15</span></span> |<span data-ttu-id="d1480-398">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="d1480-398">1.1.14104.0</span></span> | <span data-ttu-id="d1480-399">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="d1480-399">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d1480-400">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="d1480-400">1703  (RS2)</span></span> |<span data-ttu-id="d1480-401">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="d1480-401">4.11.15603.2</span></span> |<span data-ttu-id="d1480-402">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="d1480-402">1.1.13504.0</span></span> | <span data-ttu-id="d1480-403">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="d1480-403">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="d1480-404">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="d1480-404">1607 (RS1)</span></span> |<span data-ttu-id="d1480-405">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="d1480-405">4.10.14393.3683</span></span> |<span data-ttu-id="d1480-406">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="d1480-406">1.1.12805.0</span></span> | <span data-ttu-id="d1480-407">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="d1480-407">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="d1480-408">Para obter informações de versão do Windows 10, consulte a planilha de fatos do [ciclo de vida do Windows.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="d1480-408">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="d1480-409">Atualizações para Manutenção e Gerenciamento de Imagens de Implantação (DISM)</span><span class="sxs-lookup"><span data-stu-id="d1480-409">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="d1480-410">Recomendamos atualizar suas imagens de instalação do sistema operacional Windows 10 (Enterprise, Pro e Home), Windows Server 2019 e Windows Server 2016 com as atualizações mais recentes de antivírus e antimalware.</span><span class="sxs-lookup"><span data-stu-id="d1480-410">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="d1480-411">Manter as imagens de instalação do sistema operacional atualizadas ajuda a evitar uma lacuna na proteção.</span><span class="sxs-lookup"><span data-stu-id="d1480-411">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="d1480-412">Para obter mais informações, consulte [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="d1480-412">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="d1480-413">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="d1480-413">1.1.2105.01</span></span></summary>

<span data-ttu-id="d1480-414">&ensp;Versão do pacote: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="d1480-414">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="d1480-415">&ensp;Versão da plataforma: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="d1480-415">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="d1480-416">&ensp;Versão do mecanismo: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="d1480-416">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="d1480-417">&ensp;Versão de assinatura: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-417">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d1480-418">Correções</span><span class="sxs-lookup"><span data-stu-id="d1480-418">Fixes</span></span>
- <span data-ttu-id="d1480-419">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d1480-419">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d1480-420">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="d1480-420">Additional information</span></span>
- <span data-ttu-id="d1480-421">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d1480-421">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d1480-422">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="d1480-422">1.1.2104.01</span></span></summary>

<span data-ttu-id="d1480-423">&ensp;Versão do pacote: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="d1480-423">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="d1480-424">&ensp;Versão da plataforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="d1480-424">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="d1480-425">&ensp;Versão do mecanismo: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="d1480-425">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="d1480-426">&ensp;Versão de assinatura: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-426">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d1480-427">Correções</span><span class="sxs-lookup"><span data-stu-id="d1480-427">Fixes</span></span>
- <span data-ttu-id="d1480-428">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d1480-428">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d1480-429">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="d1480-429">Additional information</span></span>
- <span data-ttu-id="d1480-430">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d1480-430">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d1480-431">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="d1480-431">1.1.2103.01</span></span></summary>

<span data-ttu-id="d1480-432">&ensp;Versão do pacote: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="d1480-432">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="d1480-433">&ensp;Versão da plataforma: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="d1480-433">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="d1480-434">&ensp;Versão do mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="d1480-434">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="d1480-435">&ensp;Versão de assinatura: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-435">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d1480-436">Correções</span><span class="sxs-lookup"><span data-stu-id="d1480-436">Fixes</span></span>
- <span data-ttu-id="d1480-437">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d1480-437">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d1480-438">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="d1480-438">Additional information</span></span>
- <span data-ttu-id="d1480-439">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d1480-439">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d1480-440">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="d1480-440">1.1.2102.03</span></span></summary>

<span data-ttu-id="d1480-441">&ensp;Versão do pacote: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="d1480-441">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="d1480-442">&ensp;Versão da plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="d1480-442">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="d1480-443">&ensp;Versão do mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="d1480-443">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="d1480-444">&ensp;Versão de assinatura: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-444">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d1480-445">Correções</span><span class="sxs-lookup"><span data-stu-id="d1480-445">Fixes</span></span>
- <span data-ttu-id="d1480-446">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d1480-446">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d1480-447">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="d1480-447">Additional information</span></span>
- <span data-ttu-id="d1480-448">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d1480-448">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d1480-449">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="d1480-449">1.1.2101.02</span></span></summary>

<span data-ttu-id="d1480-450">&ensp;Versão do pacote: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="d1480-450">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="d1480-451">&ensp;Versão da plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="d1480-451">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="d1480-452">&ensp;Versão do mecanismo: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="d1480-452">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="d1480-453">&ensp;Versão de assinatura: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-453">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d1480-454">Correções</span><span class="sxs-lookup"><span data-stu-id="d1480-454">Fixes</span></span>
- <span data-ttu-id="d1480-455">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d1480-455">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d1480-456">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="d1480-456">Additional information</span></span>
- <span data-ttu-id="d1480-457">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d1480-457">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d1480-458">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="d1480-458">1.1.2012.01</span></span></summary>

<span data-ttu-id="d1480-459">&ensp;Versão do pacote: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="d1480-459">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="d1480-460">&ensp;Versão da plataforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="d1480-460">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="d1480-461">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="d1480-461">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="d1480-462">&ensp;Versão de assinatura: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-462">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d1480-463">Correções</span><span class="sxs-lookup"><span data-stu-id="d1480-463">Fixes</span></span>
- <span data-ttu-id="d1480-464">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d1480-464">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d1480-465">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="d1480-465">Additional information</span></span>
- <span data-ttu-id="d1480-466">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d1480-466">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d1480-467">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="d1480-467">1.1.2011.02</span></span></summary>

<span data-ttu-id="d1480-468">&ensp;Versão do pacote: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="d1480-468">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="d1480-469">&ensp;Versão da plataforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="d1480-469">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="d1480-470">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="d1480-470">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="d1480-471">&ensp;Versão de assinatura: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-471">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d1480-472">Correções</span><span class="sxs-lookup"><span data-stu-id="d1480-472">Fixes</span></span>
- <span data-ttu-id="d1480-473">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d1480-473">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d1480-474">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="d1480-474">Additional information</span></span>
- <span data-ttu-id="d1480-475">Assinaturas atualizadas do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="d1480-475">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d1480-476">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="d1480-476">1.1.2011.01</span></span></summary>

<span data-ttu-id="d1480-477">&ensp;Versão do pacote: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="d1480-477">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="d1480-478">&ensp;Versão da plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="d1480-478">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="d1480-479">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="d1480-479">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="d1480-480">&ensp;Versão de assinatura: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-480">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d1480-481">Correções</span><span class="sxs-lookup"><span data-stu-id="d1480-481">Fixes</span></span>
- <span data-ttu-id="d1480-482">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d1480-482">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d1480-483">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="d1480-483">Additional information</span></span>
- <span data-ttu-id="d1480-484">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d1480-484">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="d1480-485">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="d1480-485">1.1.2009.10</span></span></summary>

<span data-ttu-id="d1480-486">&ensp;Versão do pacote: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="d1480-486">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="d1480-487">&ensp;Versão da plataforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="d1480-487">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="d1480-488">&ensp;Versão do mecanismo: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="d1480-488">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="d1480-489">&ensp;Versão de assinatura: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="d1480-489">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="d1480-490">Correções</span><span class="sxs-lookup"><span data-stu-id="d1480-490">Fixes</span></span>
- <span data-ttu-id="d1480-491">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d1480-491">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="d1480-492">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="d1480-492">Additional information</span></span>
- <span data-ttu-id="d1480-493">Adicionado suporte para imagens de instalação do sistema operacional windows 10 RS1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="d1480-493">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="d1480-494">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d1480-494">Additional resources</span></span>

| <span data-ttu-id="d1480-495">Artigo</span><span class="sxs-lookup"><span data-stu-id="d1480-495">Article</span></span> | <span data-ttu-id="d1480-496">Descrição</span><span class="sxs-lookup"><span data-stu-id="d1480-496">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="d1480-497">Atualização do Microsoft Defender para imagens de instalação do sistema operacional Windows</span><span class="sxs-lookup"><span data-stu-id="d1480-497">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="d1480-498">Revise os pacotes de atualização antimalware para as imagens de instalação do sistema operacional (arquivos WIM e VHD).</span><span class="sxs-lookup"><span data-stu-id="d1480-498">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="d1480-499">Obter atualizações do Microsoft Defender Antivírus para Windows 10 (edições Enterprise, Pro e Home), Windows Server 2019 e imagens de instalação do Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="d1480-499">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="d1480-500">Gerenciar como as atualizações de proteção são baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="d1480-500">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="d1480-501">As atualizações de proteção podem ser entregues por meio de várias fontes.</span><span class="sxs-lookup"><span data-stu-id="d1480-501">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="d1480-502">Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="d1480-502">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="d1480-503">Você pode agendar quando as atualizações de proteção devem ser baixadas.</span><span class="sxs-lookup"><span data-stu-id="d1480-503">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="d1480-504">Gerenciar atualizações para pontos de extremidade que estão des date</span><span class="sxs-lookup"><span data-stu-id="d1480-504">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="d1480-505">Se um ponto de extremidade perder uma atualização ou uma verificação agendada, você poderá forçar uma atualização ou verificar na próxima vez que um usuário entrar.</span><span class="sxs-lookup"><span data-stu-id="d1480-505">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="d1480-506">Gerenciar atualizações aplicadas com base em evento</span><span class="sxs-lookup"><span data-stu-id="d1480-506">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="d1480-507">Você pode definir atualizações de proteção a serem baixadas na inicialização ou após determinados eventos de proteção entregues na nuvem.</span><span class="sxs-lookup"><span data-stu-id="d1480-507">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="d1480-508">Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)</span><span class="sxs-lookup"><span data-stu-id="d1480-508">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="d1480-509">Você pode especificar configurações, como se as atualizações devem ocorrer na energia da bateria, que são especialmente úteis para dispositivos móveis e máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="d1480-509">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
