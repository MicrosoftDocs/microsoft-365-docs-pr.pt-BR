---
title: Gerenciar atualizações do Microsoft Defender Antivírus e aplicar linhas de base
description: Gerencie como o Microsoft Defender Antivírus recebe atualizações de produtos e proteção.
keywords: atualizações, linhas de base de segurança, proteção, agendar atualizações, forçar atualizações, atualizações móveis, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: bf027dd7f5fad032d57d2dd0b686ccd129f568c7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689807"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="af555-104">Gerenciar atualizações do Microsoft Defender Antivírus e aplicar linhas de base</span><span class="sxs-lookup"><span data-stu-id="af555-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="af555-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="af555-105">**Applies to:**</span></span>

- [<span data-ttu-id="af555-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="af555-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="af555-107">Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="af555-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="af555-108">Há dois tipos de atualizações relacionadas a manter o Microsoft Defender Antivírus atualizado:</span><span class="sxs-lookup"><span data-stu-id="af555-108">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="af555-109">Atualizações de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="af555-109">Security intelligence updates</span></span>
- <span data-ttu-id="af555-110">Atualizações de produtos</span><span class="sxs-lookup"><span data-stu-id="af555-110">Product updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af555-111">Manter o Microsoft Defender Antivírus atualizado é fundamental para garantir que seus dispositivos tenham a tecnologia e os recursos mais recentes necessários para proteger contra novas técnicas de malware e ataque.</span><span class="sxs-lookup"><span data-stu-id="af555-111">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span>  
> <span data-ttu-id="af555-112">Certifique-se de atualizar sua proteção antivírus mesmo se o Microsoft Defender Antivírus estiver em execução no [modo passivo](./microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="af555-112">Make sure to update your antivirus protection even if Microsoft Defender Antivirus is running in [passive mode](./microsoft-defender-antivirus-compatibility.md).</span></span>
> 
> <span data-ttu-id="af555-113">Para ver o mecanismo, a plataforma e a data de assinatura mais atuais, visite as atualizações de inteligência de segurança do Microsoft Defender Antivírus e [outros antimalware da Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="af555-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="af555-114">Atualizações de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="af555-114">Security intelligence updates</span></span>

<span data-ttu-id="af555-115">O Microsoft Defender [Antivírus](cloud-protection-microsoft-defender-antivirus.md) usa proteção entregue na nuvem (também chamado de Serviço de Proteção Avançada da Microsoft ou MAPS) e baixa periodicamente atualizações de inteligência de segurança para fornecer proteção.</span><span class="sxs-lookup"><span data-stu-id="af555-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="af555-116">As atualizações são lançadas nos números KB abaixo:</span><span class="sxs-lookup"><span data-stu-id="af555-116">Updates are released under the below KB numbers:</span></span>  
> <span data-ttu-id="af555-117">Microsoft Defender Antivírus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="af555-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> <span data-ttu-id="af555-118">Proteção do Ponto de Extremidade do System Center: KB2461484</span><span class="sxs-lookup"><span data-stu-id="af555-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="af555-119">A proteção entregue na nuvem está sempre ativa e requer uma conexão ativa com a Internet para funcionar.</span><span class="sxs-lookup"><span data-stu-id="af555-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="af555-120">As atualizações de inteligência de segurança ocorrem em uma cadência agendada (configurável por meio da política).</span><span class="sxs-lookup"><span data-stu-id="af555-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="af555-121">Para obter mais informações, [consulte Use Microsoft cloud-provided protection in Microsoft Defender Antivírus](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="af555-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="af555-122">Para ver uma lista de atualizações recentes de inteligência de segurança, consulte Atualizações de inteligência de segurança para [o Microsoft Defender Antivírus e outros antimalware da Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="af555-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="af555-123">As atualizações do mecanismo são incluídas com atualizações de inteligência de segurança e são lançadas em uma cadência mensal.</span><span class="sxs-lookup"><span data-stu-id="af555-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="af555-124">Atualizações de produtos</span><span class="sxs-lookup"><span data-stu-id="af555-124">Product updates</span></span>

<span data-ttu-id="af555-125">O Microsoft Defender Antivírus exige atualizações mensais [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) *(conhecidas* como atualizações de plataforma) e receberá atualizações de recursos importantes juntamente com versões do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="af555-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) (known as *platform updates*), and will receive major feature updates alongside Windows 10 releases.</span></span>

<span data-ttu-id="af555-126">Você pode gerenciar a distribuição de atualizações por meio de um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="af555-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="af555-127">Serviço de Atualização do Windows Server (WSUS)</span><span class="sxs-lookup"><span data-stu-id="af555-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="af555-128">Gerenciador de Configuração do Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="af555-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="af555-129">O método comum que você usa para implantar atualizações da Microsoft e do Windows nos pontos de extremidade em sua rede.</span><span class="sxs-lookup"><span data-stu-id="af555-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="af555-130">Para obter mais informações, consulte Gerenciar as fontes para atualizações de proteção [do Microsoft Defender Antivírus.](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)</span><span class="sxs-lookup"><span data-stu-id="af555-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> <span data-ttu-id="af555-131">As atualizações mensais são lançadas em fases, resultando em vários pacotes visíveis em seus [Serviços de Atualização do Servidor de Janelas.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="af555-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="af555-132">Versões mensais de plataforma e mecanismo</span><span class="sxs-lookup"><span data-stu-id="af555-132">Monthly platform and engine versions</span></span>

<span data-ttu-id="af555-133">Para obter informações sobre como atualizar ou instalar a atualização da plataforma, consulte [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="af555-133">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="af555-134">Todas as nossas atualizações contêm</span><span class="sxs-lookup"><span data-stu-id="af555-134">All our updates contain</span></span> 
- <span data-ttu-id="af555-135">melhorias de desempenho;</span><span class="sxs-lookup"><span data-stu-id="af555-135">performance improvements;</span></span>
- <span data-ttu-id="af555-136">melhorias de capacidade de serviço; e</span><span class="sxs-lookup"><span data-stu-id="af555-136">serviceability improvements; and</span></span> 
- <span data-ttu-id="af555-137">melhorias de integração (Cloud, Microsoft 365 Defender).</span><span class="sxs-lookup"><span data-stu-id="af555-137">integration improvements (Cloud, Microsoft 365 Defender).</span></span>
<br/><br/>

<details>
<summary> <span data-ttu-id="af555-138">Março-2021 (Plataforma: 4.18.2103.7 | Mecanismo: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="af555-138">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="af555-139">&ensp;Versão de atualização de inteligência de segurança: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="af555-139">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="af555-140">&ensp;Lançado: **1º de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="af555-140">&ensp;Released: **April 1, 2021**</span></span>  
<span data-ttu-id="af555-141">&ensp;Plataforma: **4.19.2103.7**</span><span class="sxs-lookup"><span data-stu-id="af555-141">&ensp;Platform: **4.19.2103.7**</span></span>  
<span data-ttu-id="af555-142">&ensp;Mecanismo: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="af555-142">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="af555-143">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="af555-143">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="af555-144">Novidades</span><span class="sxs-lookup"><span data-stu-id="af555-144">What's new</span></span>

- <span data-ttu-id="af555-145">Melhoria no mecanismo de Monitoramento de Comportamento</span><span class="sxs-lookup"><span data-stu-id="af555-145">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="af555-146">Mitigações de ataques de força bruta de rede expandida</span><span class="sxs-lookup"><span data-stu-id="af555-146">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="af555-147">Geração adicional de eventos de tentativa de adulteração com falha quando [a Proteção contra Adulteração](prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada</span><span class="sxs-lookup"><span data-stu-id="af555-147">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="af555-148">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="af555-148">Known Issues</span></span>
<span data-ttu-id="af555-149">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="af555-149">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="af555-150">Fevereiro-2021 (plataforma: 4.18.2102.3 | Mecanismo: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="af555-150">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="af555-151">&ensp;Versão de atualização de inteligência de segurança: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="af555-151">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="af555-152">&ensp;Lançado: **9 de março de 2021**</span><span class="sxs-lookup"><span data-stu-id="af555-152">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="af555-153">&ensp;Plataforma: **4.19.2102.3**</span><span class="sxs-lookup"><span data-stu-id="af555-153">&ensp;Platform: **4.19.2102.3**</span></span>  
<span data-ttu-id="af555-154">&ensp;Mecanismo: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="af555-154">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="af555-155">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="af555-155">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="af555-156">Novidades</span><span class="sxs-lookup"><span data-stu-id="af555-156">What's new</span></span>

- <span data-ttu-id="af555-157">Recuperação aprimorada do serviço por meio [da proteção contra violações](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="af555-157">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="af555-158">Estender escopo de proteção contra violações</span><span class="sxs-lookup"><span data-stu-id="af555-158">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="af555-159">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="af555-159">Known Issues</span></span>
<span data-ttu-id="af555-160">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="af555-160">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="af555-161">Janeiro-2021 (Plataforma: 4.18.2101.9 | Mecanismo: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="af555-161">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="af555-162">&ensp;Versão de atualização de inteligência de segurança: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="af555-162">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="af555-163">&ensp;Lançado: **2 de fevereiro de 2021**</span><span class="sxs-lookup"><span data-stu-id="af555-163">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="af555-164">&ensp;Plataforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="af555-164">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="af555-165">&ensp;Mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="af555-165">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="af555-166">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="af555-166">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="af555-167">Novidades</span><span class="sxs-lookup"><span data-stu-id="af555-167">What's new</span></span>

- <span data-ttu-id="af555-168">Melhorias na detecção de exploração de shellcode</span><span class="sxs-lookup"><span data-stu-id="af555-168">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="af555-169">Maior visibilidade para tentativas de roubo de credenciais</span><span class="sxs-lookup"><span data-stu-id="af555-169">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="af555-170">Melhorias nos recursos anti-amperes nos serviços do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="af555-170">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="af555-171">Suporte aprimorado para ARM emulação x64</span><span class="sxs-lookup"><span data-stu-id="af555-171">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="af555-172">Correção: a notificação de bloqueio de EDR permanece no histórico de ameaças depois que a proteção em tempo real realizou a detecção inicial</span><span class="sxs-lookup"><span data-stu-id="af555-172">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="af555-173">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="af555-173">Known Issues</span></span>
<span data-ttu-id="af555-174">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="af555-174">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="af555-175">Atualizações de versão anterior: Suporte técnico somente a atualização</span><span class="sxs-lookup"><span data-stu-id="af555-175">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="af555-176">Depois que uma nova versão de pacote é lançada, o suporte para as duas versões anteriores é reduzido apenas ao suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="af555-176">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="af555-177">Versões anteriores às listadas nesta seção são fornecidas apenas para suporte técnico de atualização.</span><span class="sxs-lookup"><span data-stu-id="af555-177">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<br/><br/>
<details>
<summary> <span data-ttu-id="af555-178">Novembro-2020 (Plataforma: 4.18.2011.6 | Mecanismo: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="af555-178">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="af555-179">&ensp;Versão de atualização de inteligência de segurança: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="af555-179">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="af555-180">&ensp;Lançado: **03 de dezembro de 2020**</span><span class="sxs-lookup"><span data-stu-id="af555-180">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="af555-181">&ensp;Plataforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="af555-181">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="af555-182">&ensp;Mecanismo: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="af555-182">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="af555-183">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="af555-183">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="af555-184">Novidades</span><span class="sxs-lookup"><span data-stu-id="af555-184">What's new</span></span>

- <span data-ttu-id="af555-185">Registro em log de suporte ao status [do SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) aprimorado</span><span class="sxs-lookup"><span data-stu-id="af555-185">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="af555-186">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="af555-186">Known Issues</span></span>
<span data-ttu-id="af555-187">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="af555-187">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="af555-188">Outubro-2020 (Plataforma: 4.18.2010.7 | Mecanismo: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="af555-188">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="af555-189">&ensp;Versão de atualização de inteligência de segurança: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="af555-189">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="af555-190">&ensp;Lançado: **29 de outubro de 2020**</span><span class="sxs-lookup"><span data-stu-id="af555-190">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="af555-191">&ensp;Plataforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="af555-191">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="af555-192">&ensp;Mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="af555-192">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="af555-193">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="af555-193">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="af555-194">Novidades</span><span class="sxs-lookup"><span data-stu-id="af555-194">What's new</span></span>

- <span data-ttu-id="af555-195">Novas descrições para categorias de ameaças especiais</span><span class="sxs-lookup"><span data-stu-id="af555-195">New descriptions for special threat categories</span></span>
- <span data-ttu-id="af555-196">Recursos de emulação aprimorados</span><span class="sxs-lookup"><span data-stu-id="af555-196">Improved emulation capabilities</span></span>
- <span data-ttu-id="af555-197">Recursos de permitir/bloquear endereço de host aprimorados</span><span class="sxs-lookup"><span data-stu-id="af555-197">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="af555-198">Nova opção no CSP do Defender para Ignorar a mesclação de exclusões de usuários locais</span><span class="sxs-lookup"><span data-stu-id="af555-198">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="af555-199">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="af555-199">Known Issues</span></span>

<span data-ttu-id="af555-200">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="af555-200">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="af555-201">Setembro-2020 (Plataforma: 4.18.2009.7 | Mecanismo: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="af555-201">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="af555-202">&ensp;Versão de atualização de inteligência de segurança: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="af555-202">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="af555-203">&ensp;Lançado: **01 de outubro de 2020**</span><span class="sxs-lookup"><span data-stu-id="af555-203">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="af555-204">&ensp;Plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="af555-204">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="af555-205">&ensp;Mecanismo: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="af555-205">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="af555-206">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="af555-206">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="af555-207">Novidades</span><span class="sxs-lookup"><span data-stu-id="af555-207">What's new</span></span>

- <span data-ttu-id="af555-208">Permissões de administrador são necessárias para restaurar arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="af555-208">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="af555-209">Eventos formatados xml agora são suportados</span><span class="sxs-lookup"><span data-stu-id="af555-209">XML formatted events are now supported</span></span>
- <span data-ttu-id="af555-210">Suporte a CSP para ignorar mesclações de exclusão</span><span class="sxs-lookup"><span data-stu-id="af555-210">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="af555-211">Novas interfaces de gerenciamento para:</span><span class="sxs-lookup"><span data-stu-id="af555-211">New management interfaces for:</span></span>
   - <span data-ttu-id="af555-212">Inspeção UDP</span><span class="sxs-lookup"><span data-stu-id="af555-212">UDP Inspection</span></span>
   - <span data-ttu-id="af555-213">Proteção de Rede no Server 2019</span><span class="sxs-lookup"><span data-stu-id="af555-213">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="af555-214">Exclusões de endereço IP para Proteção de Rede</span><span class="sxs-lookup"><span data-stu-id="af555-214">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="af555-215">Visibilidade aprimorada nas medições do TPM</span><span class="sxs-lookup"><span data-stu-id="af555-215">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="af555-216">Verificação aprimorada do módulo VBA do Office</span><span class="sxs-lookup"><span data-stu-id="af555-216">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="af555-217">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="af555-217">Known Issues</span></span>

<span data-ttu-id="af555-218">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="af555-218">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="af555-219">Agosto-2020 (plataforma: 4.18.2008.9 | Mecanismo: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="af555-219">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="af555-220">&ensp;Versão de atualização de inteligência de segurança: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="af555-220">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="af555-221">&ensp;Lançado: **27 de agosto de 2020**</span><span class="sxs-lookup"><span data-stu-id="af555-221">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="af555-222">&ensp;Plataforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="af555-222">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="af555-223">&ensp;Mecanismo: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="af555-223">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="af555-224">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="af555-224">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="af555-225">Novidades</span><span class="sxs-lookup"><span data-stu-id="af555-225">What's new</span></span>

- <span data-ttu-id="af555-226">Adicionar mais eventos de telemetria</span><span class="sxs-lookup"><span data-stu-id="af555-226">Add more telemetry events</span></span>
- <span data-ttu-id="af555-227">Telemetria de eventos de verificação aprimorada</span><span class="sxs-lookup"><span data-stu-id="af555-227">Improved scan event telemetry</span></span>
- <span data-ttu-id="af555-228">Monitoramento de comportamento aprimorado para verificações de memória</span><span class="sxs-lookup"><span data-stu-id="af555-228">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="af555-229">Verificação de fluxos de macros aprimorados</span><span class="sxs-lookup"><span data-stu-id="af555-229">Improved macro streams scanning</span></span>
- <span data-ttu-id="af555-230">Adicionado `AMRunningMode` ao cmdlet Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="af555-230">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="af555-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) é ignorado.</span><span class="sxs-lookup"><span data-stu-id="af555-231">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="af555-232">O Microsoft Defender Antivírus automaticamente se desliga quando detecta outro programa antivírus.</span><span class="sxs-lookup"><span data-stu-id="af555-232">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="af555-233">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="af555-233">Known Issues</span></span>
<span data-ttu-id="af555-234">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="af555-234">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="af555-235">Julho-2020 (Plataforma: 4.18.2007.8 | Mecanismo: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="af555-235">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="af555-236">&ensp;Versão de atualização de inteligência de segurança: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="af555-236">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="af555-237">&ensp;Lançado: **28 de julho de 2020**</span><span class="sxs-lookup"><span data-stu-id="af555-237">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="af555-238">&ensp;Plataforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="af555-238">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="af555-239">&ensp;Mecanismo: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="af555-239">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="af555-240">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="af555-240">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="af555-241">Novidades</span><span class="sxs-lookup"><span data-stu-id="af555-241">What's new</span></span>

- <span data-ttu-id="af555-242">Telemetria aprimorada para BITS</span><span class="sxs-lookup"><span data-stu-id="af555-242">Improved telemetry for BITS</span></span>
- <span data-ttu-id="af555-243">Validação aprimorada de certificado de assinatura de código Authenticode</span><span class="sxs-lookup"><span data-stu-id="af555-243">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="af555-244">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="af555-244">Known Issues</span></span>
<span data-ttu-id="af555-245">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="af555-245">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="af555-246">Junho-2020 (Plataforma: 4.18.2006.10 | Mecanismo: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="af555-246">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="af555-247">&ensp;Versão de atualização de inteligência de segurança: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="af555-247">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="af555-248">&ensp;Lançado: **22 de junho de 2020**</span><span class="sxs-lookup"><span data-stu-id="af555-248">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="af555-249">&ensp;Plataforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="af555-249">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="af555-250">&ensp;Mecanismo: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="af555-250">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="af555-251">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="af555-251">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="af555-252">Novidades</span><span class="sxs-lookup"><span data-stu-id="af555-252">What's new</span></span>

- <span data-ttu-id="af555-253">Possibilidade de especificar o [local dos logs de suporte](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="af555-253">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="af555-254">Ignorar a verificação de captura agressiva no modo Passivo.</span><span class="sxs-lookup"><span data-stu-id="af555-254">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="af555-255">Permitir que o Defender atualize em conexões com metros</span><span class="sxs-lookup"><span data-stu-id="af555-255">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="af555-256">Ajuste de desempenho fixo quando o cache está desabilitado</span><span class="sxs-lookup"><span data-stu-id="af555-256">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="af555-257">Consulta de registro fixa</span><span class="sxs-lookup"><span data-stu-id="af555-257">Fixed registry query</span></span> 
- <span data-ttu-id="af555-258">Randomização de tempo de verificação fixa no ADMX</span><span class="sxs-lookup"><span data-stu-id="af555-258">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="af555-259">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="af555-259">Known Issues</span></span>
<span data-ttu-id="af555-260">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="af555-260">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="af555-261">Maio-2020 (plataforma: 4.18.2005.4 | Mecanismo: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="af555-261">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="af555-262">&ensp;Versão de atualização de inteligência de segurança: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="af555-262">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="af555-263">&ensp;Lançado: **26 de maio de 2020**</span><span class="sxs-lookup"><span data-stu-id="af555-263">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="af555-264">&ensp;Plataforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="af555-264">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="af555-265">&ensp;Mecanismo: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="af555-265">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="af555-266">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="af555-266">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="af555-267">Novidades</span><span class="sxs-lookup"><span data-stu-id="af555-267">What's new</span></span>

- <span data-ttu-id="af555-268">Registro em log aprimorado para eventos de verificação</span><span class="sxs-lookup"><span data-stu-id="af555-268">Improved logging for scan events</span></span>
- <span data-ttu-id="af555-269">Melhor tratamento de falhas no modo de usuário.</span><span class="sxs-lookup"><span data-stu-id="af555-269">Improved user mode crash handling.</span></span>
- <span data-ttu-id="af555-270">Rastreamento de eventos adicionado para proteção contra adulteração</span><span class="sxs-lookup"><span data-stu-id="af555-270">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="af555-271">Envio de amostra AMSI corrigido</span><span class="sxs-lookup"><span data-stu-id="af555-271">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="af555-272">Bloqueio fixo da nuvem AMSI</span><span class="sxs-lookup"><span data-stu-id="af555-272">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="af555-273">Log de instalação de atualização de segurança fixa</span><span class="sxs-lookup"><span data-stu-id="af555-273">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="af555-274">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="af555-274">Known Issues</span></span>
<span data-ttu-id="af555-275">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="af555-275">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="af555-276">Abril-2020 (Plataforma: 4.18.2004.6 | Mecanismo: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="af555-276">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="af555-277">&ensp;Versão de atualização de inteligência de segurança: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="af555-277">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="af555-278">&ensp;Lançado: **30 de abril de 2020**</span><span class="sxs-lookup"><span data-stu-id="af555-278">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="af555-279">&ensp;Plataforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="af555-279">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="af555-280">&ensp;Mecanismo: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="af555-280">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="af555-281">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="af555-281">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="af555-282">Novidades</span><span class="sxs-lookup"><span data-stu-id="af555-282">What's new</span></span>
- <span data-ttu-id="af555-283">Melhorias do WDfilter</span><span class="sxs-lookup"><span data-stu-id="af555-283">WDfilter improvements</span></span>
- <span data-ttu-id="af555-284">Adicionar mais dados de evento acionáveis para atacar eventos de detecção de redução de superfície</span><span class="sxs-lookup"><span data-stu-id="af555-284">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="af555-285">Informações de versão fixas em dados de diagnóstico e WMI</span><span class="sxs-lookup"><span data-stu-id="af555-285">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="af555-286">Versão da plataforma incorreta corrigida na interface do usuário após a atualização da plataforma</span><span class="sxs-lookup"><span data-stu-id="af555-286">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="af555-287">Intel de URL dinâmica para proteção contra ameaças sem arquivo</span><span class="sxs-lookup"><span data-stu-id="af555-287">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="af555-288">Recurso de verificação UEFI</span><span class="sxs-lookup"><span data-stu-id="af555-288">UEFI scan capability</span></span>
- <span data-ttu-id="af555-289">Estender o log para atualizações</span><span class="sxs-lookup"><span data-stu-id="af555-289">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="af555-290">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="af555-290">Known Issues</span></span>
<span data-ttu-id="af555-291">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="af555-291">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="af555-292">Março-2020 (Plataforma: 4.18.2003.8 | Mecanismo: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="af555-292">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="af555-293">&ensp;Versão de atualização de inteligência de segurança: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="af555-293">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="af555-294">&ensp;Lançado: **24 de março de 2020**</span><span class="sxs-lookup"><span data-stu-id="af555-294">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="af555-295">&ensp;Plataforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="af555-295">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="af555-296">&ensp;Mecanismo: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="af555-296">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="af555-297">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="af555-297">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="af555-298">Novidades</span><span class="sxs-lookup"><span data-stu-id="af555-298">What's new</span></span>

- <span data-ttu-id="af555-299">Opção de throttling de CPU adicionada ao [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="af555-299">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="af555-300">Melhorar a funcionalidade de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="af555-300">Improve diagnostic capability</span></span>
- <span data-ttu-id="af555-301">reduzir o tempo de tempo de inteligência de segurança (5 minutos)</span><span class="sxs-lookup"><span data-stu-id="af555-301">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="af555-302">Estender a funcionalidade de log interno do mecanismo AMSI</span><span class="sxs-lookup"><span data-stu-id="af555-302">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="af555-303">Melhorar a notificação para bloqueio de processos</span><span class="sxs-lookup"><span data-stu-id="af555-303">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="af555-304">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="af555-304">Known Issues</span></span>
<span data-ttu-id="af555-305">[**Fixo**] O Microsoft Defender Antivírus está ignorando arquivos ao executar uma verificação.</span><span class="sxs-lookup"><span data-stu-id="af555-305">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="af555-306">Fevereiro-2020 (Plataforma: - | Mecanismo: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="af555-306">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="af555-307">&ensp;Versão de atualização de inteligência de segurança: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="af555-307">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="af555-308">&ensp;Lançado: **25 de fevereiro de 2020**</span><span class="sxs-lookup"><span data-stu-id="af555-308">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="af555-309">&ensp;Plataforma/Cliente: **-**</span><span class="sxs-lookup"><span data-stu-id="af555-309">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="af555-310">&ensp;Mecanismo: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="af555-310">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="af555-311">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="af555-311">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="af555-312">Novidades</span><span class="sxs-lookup"><span data-stu-id="af555-312">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="af555-313">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="af555-313">Known Issues</span></span>
<span data-ttu-id="af555-314">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="af555-314">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="af555-315">Janeiro-2020 (Plataforma: 4.18.2001.10 | Mecanismo: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="af555-315">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="af555-316">Versão de atualização de inteligência de segurança: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="af555-316">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="af555-317">Lançado: **30 de janeiro de 2020**</span><span class="sxs-lookup"><span data-stu-id="af555-317">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="af555-318">Plataforma/Cliente: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="af555-318">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="af555-319">Mecanismo: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="af555-319">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="af555-320">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="af555-320">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="af555-321">Novidades</span><span class="sxs-lookup"><span data-stu-id="af555-321">What's new</span></span>

- <span data-ttu-id="af555-322">BSOD fixo no WS2016 com o Exchange</span><span class="sxs-lookup"><span data-stu-id="af555-322">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="af555-323">Atualizações da plataforma de suporte quando o TMP é redirecionado para o caminho da rede</span><span class="sxs-lookup"><span data-stu-id="af555-323">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="af555-324">As versões de plataforma e mecanismo são [adicionadas ao WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="af555-324">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="af555-325">estender a atualização de assinatura de emergência para [o modo passivo](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="af555-325">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="af555-326">Corrigir trava 4.18.1911.3</span><span class="sxs-lookup"><span data-stu-id="af555-326">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="af555-327">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="af555-327">Known Issues</span></span>

<span data-ttu-id="af555-328">[**Corrigido**] [dispositivos](/windows-hardware/design/device-experiences/modern-standby) que usam o modo de espera moderno podem ter uma trava com o driver de filtro Windows Defender que resulta em uma lacuna de proteção.</span><span class="sxs-lookup"><span data-stu-id="af555-328">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="af555-329">Os máquinas afetados aparecem para o cliente como não atualizados para a plataforma antimalware mais recente.</span><span class="sxs-lookup"><span data-stu-id="af555-329">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="af555-330">Esta atualização é:</span><span class="sxs-lookup"><span data-stu-id="af555-330">This update is:</span></span>
> - <span data-ttu-id="af555-331">necessário por dispositivos RS1 que executam a versão inferior da plataforma para dar suporte ao SHA2;</span><span class="sxs-lookup"><span data-stu-id="af555-331">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="af555-332">tem um sinalizador de reinicialização para sistemas que têm problemas de suspensão;</span><span class="sxs-lookup"><span data-stu-id="af555-332">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="af555-333">é re-lançado em abril de 2020 e não será superada por atualizações mais novas para manter a disponibilidade futura;</span><span class="sxs-lookup"><span data-stu-id="af555-333">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="af555-334">é categorizado como uma atualização devido ao requisito de reinicialização; e</span><span class="sxs-lookup"><span data-stu-id="af555-334">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="af555-335">só é oferecido com [o Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="af555-335">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="af555-336">Novembro-2019 (plataforma: 4.18.1911.3 | Mecanismo: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="af555-336">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="af555-337">Versão de atualização de inteligência de segurança: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="af555-337">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="af555-338">Lançado: **7 de dezembro de 2019**</span><span class="sxs-lookup"><span data-stu-id="af555-338">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="af555-339">Plataforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="af555-339">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="af555-340">Mecanismo: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="af555-340">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="af555-341">Fase de suporte: **sem suporte**</span><span class="sxs-lookup"><span data-stu-id="af555-341">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="af555-342">Novidades</span><span class="sxs-lookup"><span data-stu-id="af555-342">What's new</span></span>

- <span data-ttu-id="af555-343">Nível de rastreamento De MpCmdRun fixo</span><span class="sxs-lookup"><span data-stu-id="af555-343">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="af555-344">Informações de versão fixas do WDFilter</span><span class="sxs-lookup"><span data-stu-id="af555-344">Fixed WDFilter version info</span></span>
- <span data-ttu-id="af555-345">Melhorar notificações (PUA)</span><span class="sxs-lookup"><span data-stu-id="af555-345">Improve notifications (PUA)</span></span>
- <span data-ttu-id="af555-346">adicionar logs MRT para dar suporte a arquivos</span><span class="sxs-lookup"><span data-stu-id="af555-346">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="af555-347">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="af555-347">Known Issues</span></span>
<span data-ttu-id="af555-348">Quando essa atualização é instalada, o dispositivo precisa do pacote de salto 4.10.2001.10 para poder atualizar para a versão mais recente da plataforma.</span><span class="sxs-lookup"><span data-stu-id="af555-348">When this update is installed, the device needs the jump package 4.10.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="af555-349">Suporte à plataforma Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="af555-349">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="af555-350">As atualizações de plataforma e mecanismo são fornecidas em uma cadência mensal.</span><span class="sxs-lookup"><span data-stu-id="af555-350">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="af555-351">Para ter suporte total, mantenha-se atualizado com as atualizações mais recentes da plataforma.</span><span class="sxs-lookup"><span data-stu-id="af555-351">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="af555-352">Nossa estrutura de suporte é dinâmica, evoluindo em duas fases, dependendo da disponibilidade da versão mais recente da plataforma:</span><span class="sxs-lookup"><span data-stu-id="af555-352">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="af555-353">Fase de manutenção de Atualizações **Críticas** e Segurança - Ao executar a versão mais recente da plataforma, você estará qualificado para receber atualizações de segurança e críticas para a plataforma anti-malware.</span><span class="sxs-lookup"><span data-stu-id="af555-353">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="af555-354">Fase de Suporte Técnico **(Somente)** - Depois que uma nova versão da plataforma for lançada, o suporte para versões mais antigas (N-2) será redução apenas para suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="af555-354">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="af555-355">As versões da plataforma anteriores ao N-2 não serão mais suportadas.\*</span><span class="sxs-lookup"><span data-stu-id="af555-355">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="af555-356">\* O suporte técnico continuará a ser fornecido para atualizações da versão de lançamento do Windows 10 (consulte Versão da plataforma incluída com versões do [Windows 10](#platform-version-included-with-windows-10-releases)) para a versão mais recente da plataforma.</span><span class="sxs-lookup"><span data-stu-id="af555-356">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="af555-357">Durante a fase de suporte técnico (somente), incidentes de suporte comercialmente razoáveis serão fornecidos por meio do Serviço de Atendimento ao Cliente da Microsoft & Suporte e ofertas de suporte gerenciado da Microsoft (como o Suporte Premier).</span><span class="sxs-lookup"><span data-stu-id="af555-357">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="af555-358">Se um incidente de suporte exigir escalonamento para desenvolvimento para obter mais orientações, exigir uma atualização que não seja de segurança ou exigir uma atualização de segurança, os clientes serão solicitados a atualizar para a versão mais recente da plataforma ou uma atualização intermediária (\*).</span><span class="sxs-lookup"><span data-stu-id="af555-358">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="af555-359">Versão da plataforma incluída nas versões do Windows 10</span><span class="sxs-lookup"><span data-stu-id="af555-359">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="af555-360">A tabela a seguir fornece as versões de mecanismo e plataforma do Microsoft Defender Antivírus fornecidas com as versões mais recentes do Windows 10:</span><span class="sxs-lookup"><span data-stu-id="af555-360">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="af555-361">Versão do Windows 10</span><span class="sxs-lookup"><span data-stu-id="af555-361">Windows 10 release</span></span>  |<span data-ttu-id="af555-362">Versão da plataforma</span><span class="sxs-lookup"><span data-stu-id="af555-362">Platform version</span></span>  |<span data-ttu-id="af555-363">Versão do mecanismo</span><span class="sxs-lookup"><span data-stu-id="af555-363">Engine version</span></span> |<span data-ttu-id="af555-364">Fase de suporte</span><span class="sxs-lookup"><span data-stu-id="af555-364">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="af555-365">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="af555-365">2004  (20H1/20H2)</span></span> |<span data-ttu-id="af555-366">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="af555-366">4.18.1909.6</span></span> |<span data-ttu-id="af555-367">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="af555-367">1.1.17000.2</span></span> | <span data-ttu-id="af555-368">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="af555-368">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="af555-369">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="af555-369">1909  (19H2)</span></span> |<span data-ttu-id="af555-370">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="af555-370">4.18.1902.5</span></span> |<span data-ttu-id="af555-371">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="af555-371">1.1.16700.3</span></span> | <span data-ttu-id="af555-372">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="af555-372">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="af555-373">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="af555-373">1903  (19H1)</span></span> |<span data-ttu-id="af555-374">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="af555-374">4.18.1902.5</span></span> |<span data-ttu-id="af555-375">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="af555-375">1.1.15600.4</span></span> | <span data-ttu-id="af555-376">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="af555-376">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="af555-377">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="af555-377">1809  (RS5)</span></span> |<span data-ttu-id="af555-378">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="af555-378">4.18.1807.18075</span></span> |<span data-ttu-id="af555-379">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="af555-379">1.1.15000.2</span></span> | <span data-ttu-id="af555-380">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="af555-380">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="af555-381">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="af555-381">1803  (RS4)</span></span> |<span data-ttu-id="af555-382">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="af555-382">4.13.17134.1</span></span> |<span data-ttu-id="af555-383">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="af555-383">1.1.14600.4</span></span> | <span data-ttu-id="af555-384">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="af555-384">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="af555-385">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="af555-385">1709  (RS3)</span></span> |<span data-ttu-id="af555-386">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="af555-386">4.12.16299.15</span></span> |<span data-ttu-id="af555-387">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="af555-387">1.1.14104.0</span></span> | <span data-ttu-id="af555-388">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="af555-388">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="af555-389">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="af555-389">1703  (RS2)</span></span> |<span data-ttu-id="af555-390">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="af555-390">4.11.15603.2</span></span> |<span data-ttu-id="af555-391">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="af555-391">1.1.13504.0</span></span> | <span data-ttu-id="af555-392">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="af555-392">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="af555-393">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="af555-393">1607 (RS1)</span></span> |<span data-ttu-id="af555-394">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="af555-394">4.10.14393.3683</span></span> |<span data-ttu-id="af555-395">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="af555-395">1.1.12805.0</span></span> | <span data-ttu-id="af555-396">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="af555-396">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="af555-397">Para obter informações de versão do Windows 10, consulte a planilha de fatos do [ciclo de vida do Windows.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="af555-397">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="af555-398">Atualizações para Manutenção e Gerenciamento de Imagens de Implantação (DISM)</span><span class="sxs-lookup"><span data-stu-id="af555-398">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="af555-399">Recomendamos atualizar suas imagens de instalação do sistema operacional Windows 10 (Enterprise, Pro e Home), Windows Server 2019 e Windows Server 2016 com as atualizações mais recentes de antivírus e antimalware.</span><span class="sxs-lookup"><span data-stu-id="af555-399">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="af555-400">Manter as imagens de instalação do sistema operacional atualizadas ajuda a evitar uma lacuna na proteção.</span><span class="sxs-lookup"><span data-stu-id="af555-400">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="af555-401">Para obter mais informações, consulte [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="af555-401">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="af555-402">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="af555-402">1.1.2104.01</span></span></summary>

<span data-ttu-id="af555-403">&ensp;Versão do pacote: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="af555-403">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="af555-404">&ensp;Versão da plataforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="af555-404">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="af555-405">&ensp;Versão do mecanismo: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="af555-405">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="af555-406">&ensp;Versão de assinatura: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="af555-406">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="af555-407">Correções</span><span class="sxs-lookup"><span data-stu-id="af555-407">Fixes</span></span>
- <span data-ttu-id="af555-408">Nenhum</span><span class="sxs-lookup"><span data-stu-id="af555-408">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="af555-409">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="af555-409">Additional information</span></span>
- <span data-ttu-id="af555-410">Nenhum</span><span class="sxs-lookup"><span data-stu-id="af555-410">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="af555-411">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="af555-411">1.1.2103.01</span></span></summary>

<span data-ttu-id="af555-412">&ensp;Versão do pacote: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="af555-412">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="af555-413">&ensp;Versão da plataforma: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="af555-413">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="af555-414">&ensp;Versão do mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="af555-414">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="af555-415">&ensp;Versão de assinatura: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="af555-415">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="af555-416">Correções</span><span class="sxs-lookup"><span data-stu-id="af555-416">Fixes</span></span>
- <span data-ttu-id="af555-417">Nenhum</span><span class="sxs-lookup"><span data-stu-id="af555-417">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="af555-418">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="af555-418">Additional information</span></span>
- <span data-ttu-id="af555-419">Nenhum</span><span class="sxs-lookup"><span data-stu-id="af555-419">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="af555-420">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="af555-420">1.1.2102.03</span></span></summary>

<span data-ttu-id="af555-421">&ensp;Versão do pacote: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="af555-421">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="af555-422">&ensp;Versão da plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="af555-422">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="af555-423">&ensp;Versão do mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="af555-423">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="af555-424">&ensp;Versão de assinatura: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="af555-424">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="af555-425">Correções</span><span class="sxs-lookup"><span data-stu-id="af555-425">Fixes</span></span>
- <span data-ttu-id="af555-426">Nenhum</span><span class="sxs-lookup"><span data-stu-id="af555-426">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="af555-427">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="af555-427">Additional information</span></span>
- <span data-ttu-id="af555-428">Nenhum</span><span class="sxs-lookup"><span data-stu-id="af555-428">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="af555-429">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="af555-429">1.1.2101.02</span></span></summary>

<span data-ttu-id="af555-430">&ensp;Versão do pacote: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="af555-430">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="af555-431">&ensp;Versão da plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="af555-431">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="af555-432">&ensp;Versão do mecanismo: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="af555-432">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="af555-433">&ensp;Versão de assinatura: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="af555-433">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="af555-434">Correções</span><span class="sxs-lookup"><span data-stu-id="af555-434">Fixes</span></span>
- <span data-ttu-id="af555-435">Nenhum</span><span class="sxs-lookup"><span data-stu-id="af555-435">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="af555-436">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="af555-436">Additional information</span></span>
- <span data-ttu-id="af555-437">Nenhum</span><span class="sxs-lookup"><span data-stu-id="af555-437">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="af555-438">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="af555-438">1.1.2012.01</span></span></summary>

<span data-ttu-id="af555-439">&ensp;Versão do pacote: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="af555-439">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="af555-440">&ensp;Versão da plataforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="af555-440">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="af555-441">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="af555-441">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="af555-442">&ensp;Versão de assinatura: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="af555-442">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="af555-443">Correções</span><span class="sxs-lookup"><span data-stu-id="af555-443">Fixes</span></span>
- <span data-ttu-id="af555-444">Nenhum</span><span class="sxs-lookup"><span data-stu-id="af555-444">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="af555-445">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="af555-445">Additional information</span></span>
- <span data-ttu-id="af555-446">Nenhum</span><span class="sxs-lookup"><span data-stu-id="af555-446">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="af555-447">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="af555-447">1.1.2011.02</span></span></summary>

<span data-ttu-id="af555-448">&ensp;Versão do pacote: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="af555-448">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="af555-449">&ensp;Versão da plataforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="af555-449">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="af555-450">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="af555-450">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="af555-451">&ensp;Versão de assinatura: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="af555-451">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="af555-452">Correções</span><span class="sxs-lookup"><span data-stu-id="af555-452">Fixes</span></span>
- <span data-ttu-id="af555-453">Nenhum</span><span class="sxs-lookup"><span data-stu-id="af555-453">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="af555-454">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="af555-454">Additional information</span></span>
- <span data-ttu-id="af555-455">Assinaturas atualizadas do Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="af555-455">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="af555-456">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="af555-456">1.1.2011.01</span></span></summary>

<span data-ttu-id="af555-457">&ensp;Versão do pacote: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="af555-457">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="af555-458">&ensp;Versão da plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="af555-458">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="af555-459">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="af555-459">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="af555-460">&ensp;Versão de assinatura: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="af555-460">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="af555-461">Correções</span><span class="sxs-lookup"><span data-stu-id="af555-461">Fixes</span></span>
- <span data-ttu-id="af555-462">Nenhum</span><span class="sxs-lookup"><span data-stu-id="af555-462">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="af555-463">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="af555-463">Additional information</span></span>
- <span data-ttu-id="af555-464">Nenhum</span><span class="sxs-lookup"><span data-stu-id="af555-464">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="af555-465">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="af555-465">1.1.2009.10</span></span></summary>

<span data-ttu-id="af555-466">&ensp;Versão do pacote: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="af555-466">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="af555-467">&ensp;Versão da plataforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="af555-467">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="af555-468">&ensp;Versão do mecanismo: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="af555-468">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="af555-469">&ensp;Versão de assinatura: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="af555-469">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="af555-470">Correções</span><span class="sxs-lookup"><span data-stu-id="af555-470">Fixes</span></span>
- <span data-ttu-id="af555-471">Nenhum</span><span class="sxs-lookup"><span data-stu-id="af555-471">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="af555-472">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="af555-472">Additional information</span></span>
- <span data-ttu-id="af555-473">Adicionado suporte para imagens de instalação do sistema operacional windows 10 RS1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="af555-473">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="af555-474">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="af555-474">Additional resources</span></span>

| <span data-ttu-id="af555-475">Artigo</span><span class="sxs-lookup"><span data-stu-id="af555-475">Article</span></span> | <span data-ttu-id="af555-476">Descrição</span><span class="sxs-lookup"><span data-stu-id="af555-476">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="af555-477">Atualização do Microsoft Defender para imagens de instalação do sistema operacional Windows</span><span class="sxs-lookup"><span data-stu-id="af555-477">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="af555-478">Revise os pacotes de atualização antimalware para as imagens de instalação do sistema operacional (arquivos WIM e VHD).</span><span class="sxs-lookup"><span data-stu-id="af555-478">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="af555-479">Obter atualizações do Microsoft Defender Antivírus para Windows 10 (edições Enterprise, Pro e Home), Windows Server 2019 e imagens de instalação do Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="af555-479">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="af555-480">Gerenciar como as atualizações de proteção são baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="af555-480">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="af555-481">As atualizações de proteção podem ser entregues por meio de várias fontes.</span><span class="sxs-lookup"><span data-stu-id="af555-481">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="af555-482">Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="af555-482">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="af555-483">Você pode agendar quando as atualizações de proteção devem ser baixadas.</span><span class="sxs-lookup"><span data-stu-id="af555-483">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="af555-484">Gerenciar atualizações para pontos de extremidade que estão des date</span><span class="sxs-lookup"><span data-stu-id="af555-484">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="af555-485">Se um ponto de extremidade perder uma atualização ou uma verificação agendada, você poderá forçar uma atualização ou verificar na próxima vez que um usuário entrar.</span><span class="sxs-lookup"><span data-stu-id="af555-485">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="af555-486">Gerenciar atualizações forçadas baseadas em eventos</span><span class="sxs-lookup"><span data-stu-id="af555-486">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="af555-487">Você pode definir atualizações de proteção a serem baixadas na inicialização ou após determinados eventos de proteção entregues na nuvem.</span><span class="sxs-lookup"><span data-stu-id="af555-487">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="af555-488">Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)</span><span class="sxs-lookup"><span data-stu-id="af555-488">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="af555-489">Você pode especificar configurações, como se as atualizações devem ocorrer na energia da bateria, que são especialmente úteis para dispositivos móveis e máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="af555-489">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
