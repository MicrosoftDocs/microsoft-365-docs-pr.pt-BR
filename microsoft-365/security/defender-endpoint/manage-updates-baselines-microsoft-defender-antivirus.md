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
ms.reviewer: pahuijbr, mkaminska
manager: dansimp
ms.technology: mde
ms.date: 07/06/2021
ms.openlocfilehash: f64c71501a550aabdf16b9de2d7a5db93e48caef
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314459"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a><span data-ttu-id="80a38-104">Gerenciar Microsoft Defender Antivírus e aplicar linhas de base</span><span class="sxs-lookup"><span data-stu-id="80a38-104">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>

<span data-ttu-id="80a38-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="80a38-105">**Applies to:**</span></span>

- [<span data-ttu-id="80a38-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="80a38-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- <span data-ttu-id="80a38-107">Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="80a38-107">Microsoft Defender Antivirus</span></span>

<span data-ttu-id="80a38-108">Manter Microsoft Defender Antivírus atualizado é fundamental para garantir que seus dispositivos tenham a tecnologia e os recursos mais recentes necessários para proteger contra novas técnicas de malware e ataque.</span><span class="sxs-lookup"><span data-stu-id="80a38-108">Keeping Microsoft Defender Antivirus up to date is critical to assure your devices have the latest technology and features needed to protect against new malware and attack techniques.</span></span> <span data-ttu-id="80a38-109">Certifique-se de atualizar sua proteção antivírus, mesmo que Microsoft Defender Antivírus está sendo executado no [modo passivo](microsoft-defender-antivirus-compatibility.md).</span><span class="sxs-lookup"><span data-stu-id="80a38-109">Make sure to update your antivirus protection, even if Microsoft Defender Antivirus is running in [passive mode](microsoft-defender-antivirus-compatibility.md).</span></span> <span data-ttu-id="80a38-110">Há dois tipos de atualizações relacionadas à Microsoft Defender Antivírus atualizadas:</span><span class="sxs-lookup"><span data-stu-id="80a38-110">There are two types of updates related to keeping Microsoft Defender Antivirus up to date:</span></span>

- <span data-ttu-id="80a38-111">Atualizações de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="80a38-111">Security intelligence updates</span></span>
- <span data-ttu-id="80a38-112">Atualizações de produtos</span><span class="sxs-lookup"><span data-stu-id="80a38-112">Product updates</span></span>

> [!TIP]
> <span data-ttu-id="80a38-113">Para ver o mecanismo, a plataforma e a data de assinatura mais atuais, visite as atualizações de inteligência de segurança para Microsoft Defender Antivírus [e outros antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates) da Microsoft</span><span class="sxs-lookup"><span data-stu-id="80a38-113">To see the most current engine, platform, and signature date, visit the [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span>

## <a name="security-intelligence-updates"></a><span data-ttu-id="80a38-114">Atualizações de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="80a38-114">Security intelligence updates</span></span>

<span data-ttu-id="80a38-115">Microsoft Defender Antivírus usa [proteção](cloud-protection-microsoft-defender-antivirus.md) entregue na nuvem (também chamada de Serviço de Proteção Avançada da Microsoft ou MAPS) e baixa periodicamente atualizações de inteligência de segurança para fornecer proteção.</span><span class="sxs-lookup"><span data-stu-id="80a38-115">Microsoft Defender Antivirus uses [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) (also called the Microsoft Advanced Protection Service or MAPS) and periodically downloads security intelligence updates to provide protection.</span></span>

> [!NOTE]
> <span data-ttu-id="80a38-116">As atualizações são lançadas nos números KB abaixo:</span><span class="sxs-lookup"><span data-stu-id="80a38-116">Updates are released under the below KB numbers:</span></span>  
> - <span data-ttu-id="80a38-117">Microsoft Defender Antivírus: KB2267602</span><span class="sxs-lookup"><span data-stu-id="80a38-117">Microsoft Defender Antivirus: KB2267602</span></span>  
> - <span data-ttu-id="80a38-118">System Center Endpoint Protection: KB2461484</span><span class="sxs-lookup"><span data-stu-id="80a38-118">System Center Endpoint Protection: KB2461484</span></span>

<span data-ttu-id="80a38-119">A proteção entregue na nuvem está sempre ativa e requer uma conexão ativa com a Internet para funcionar.</span><span class="sxs-lookup"><span data-stu-id="80a38-119">Cloud-delivered protection is always on and requires an active connection to the Internet to function.</span></span> <span data-ttu-id="80a38-120">As atualizações de inteligência de segurança ocorrem em uma cadência agendada (configurável por meio da política).</span><span class="sxs-lookup"><span data-stu-id="80a38-120">Security intelligence updates occur on a scheduled cadence (configurable via policy).</span></span> <span data-ttu-id="80a38-121">Para obter mais informações, [consulte Use Microsoft cloud-provided protection in Microsoft Defender Antivírus](cloud-protection-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="80a38-121">For more information, see [Use Microsoft cloud-provided protection in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="80a38-122">Para ver uma lista de atualizações recentes de inteligência de segurança, consulte Atualizações de inteligência de segurança para Microsoft Defender Antivírus [e outros antimalware da Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="80a38-122">For a list of recent security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates).</span></span>

<span data-ttu-id="80a38-123">As atualizações do mecanismo são incluídas com atualizações de inteligência de segurança e são lançadas em uma cadência mensal.</span><span class="sxs-lookup"><span data-stu-id="80a38-123">Engine updates are included with security intelligence updates and are released on a monthly cadence.</span></span>

## <a name="product-updates"></a><span data-ttu-id="80a38-124">Atualizações de produtos</span><span class="sxs-lookup"><span data-stu-id="80a38-124">Product updates</span></span>

<span data-ttu-id="80a38-125">Microsoft Defender Antivírus exige [atualizações mensais (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) *conhecidas como atualizações de plataforma.*</span><span class="sxs-lookup"><span data-stu-id="80a38-125">Microsoft Defender Antivirus requires [monthly updates (KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) known as *platform updates*.</span></span>

<span data-ttu-id="80a38-126">Você pode gerenciar a distribuição de atualizações por meio de um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="80a38-126">You can manage the distribution of updates through one of the following methods:</span></span> 

- [<span data-ttu-id="80a38-127">Windows Serviço de Atualização do Servidor (WSUS)</span><span class="sxs-lookup"><span data-stu-id="80a38-127">Windows Server Update Service (WSUS)</span></span>](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [<span data-ttu-id="80a38-128">Gerenciador de Configuração do Microsoft Endpoint</span><span class="sxs-lookup"><span data-stu-id="80a38-128">Microsoft Endpoint Configuration Manager</span></span>](/configmgr/sum/understand/software-updates-introduction)
- <span data-ttu-id="80a38-129">O método comum que você usa para implantar a Microsoft e Windows atualizações para pontos de extremidade em sua rede.</span><span class="sxs-lookup"><span data-stu-id="80a38-129">The usual method you use to deploy Microsoft and Windows updates to endpoints in your network.</span></span>

<span data-ttu-id="80a38-130">Para obter mais informações, consulte [Manage the sources for Microsoft Defender Antivírus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span><span class="sxs-lookup"><span data-stu-id="80a38-130">For more information, see [Manage the sources for Microsoft Defender Antivirus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).</span></span>

> [!NOTE]
> - <span data-ttu-id="80a38-131">As atualizações mensais são lançadas em fases, resultando em vários pacotes visíveis em seus [Serviços de Atualização do Servidor de Janelas.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)</span><span class="sxs-lookup"><span data-stu-id="80a38-131">Monthly updates are released in phases, resulting in multiple packages visible in your [Window Server Update Services](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus).</span></span>
> - <span data-ttu-id="80a38-132">Este artigo lista as alterações incluídas no canal de lançamento amplo.</span><span class="sxs-lookup"><span data-stu-id="80a38-132">This article lists changes that are included in the broad release channel.</span></span> <span data-ttu-id="80a38-133">[Consulte a versão mais recente do canal amplo aqui](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info).</span><span class="sxs-lookup"><span data-stu-id="80a38-133">[See the latest broad channel release here](https://www.microsoft.com/security/encyclopedia/adlpackages.aspx?action=info).</span></span> 
> - <span data-ttu-id="80a38-134">Para saber mais sobre o processo de lançamento gradual e para ver mais informações sobre a próxima versão, consulte [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span><span class="sxs-lookup"><span data-stu-id="80a38-134">To learn more about the gradual rollout process, and to see more information about the next release, see [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
> - <span data-ttu-id="80a38-135">Para saber mais sobre atualizações de inteligência de segurança, consulte Atualizações de inteligência de segurança para Microsoft Defender Antivírus [e outros antimalware da Microsoft.](https://www.microsoft.com/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="80a38-135">To learn more about security intelligence updates, see [Security intelligence updates for Microsoft Defender Antivirus and other Microsoft antimalware](https://www.microsoft.com/wdsi/defenderupdates).</span></span> 

## <a name="monthly-platform-and-engine-versions"></a><span data-ttu-id="80a38-136">Versões mensais de plataforma e mecanismo</span><span class="sxs-lookup"><span data-stu-id="80a38-136">Monthly platform and engine versions</span></span>

<span data-ttu-id="80a38-137">Para obter informações sobre como atualizar ou instalar a atualização da plataforma, consulte [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span><span class="sxs-lookup"><span data-stu-id="80a38-137">For information how to update or install the platform update, see [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).</span></span>

<span data-ttu-id="80a38-138">Todas as nossas atualizações contêm</span><span class="sxs-lookup"><span data-stu-id="80a38-138">All our updates contain</span></span> 
- <span data-ttu-id="80a38-139">melhorias de desempenho;</span><span class="sxs-lookup"><span data-stu-id="80a38-139">performance improvements;</span></span>
- <span data-ttu-id="80a38-140">melhorias de capacidade de serviço; e</span><span class="sxs-lookup"><span data-stu-id="80a38-140">serviceability improvements; and</span></span> 
- <span data-ttu-id="80a38-141">melhorias de integração (Nuvem, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span><span class="sxs-lookup"><span data-stu-id="80a38-141">integration improvements (Cloud, [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)).</span></span>
<br/>
<details>
<summary> <span data-ttu-id="80a38-142">Junho-2021 (plataforma: 4.18.2106.5 | Mecanismo: 1.1.18300.4)</span><span class="sxs-lookup"><span data-stu-id="80a38-142">June-2021 (Platform: 4.18.2106.5 | Engine: 1.1.18300.4)</span></span></summary>

<span data-ttu-id="80a38-143">&ensp;Versão de atualização de inteligência de segurança: **1.343.17.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-143">&ensp;Security intelligence update version: **1.343.17.0**</span></span>  
<span data-ttu-id="80a38-144">&ensp;Lançado: **28 de junho de 2021**</span><span class="sxs-lookup"><span data-stu-id="80a38-144">&ensp;Released: **June 28, 2021**</span></span>  
<span data-ttu-id="80a38-145">&ensp;Plataforma: **4.18.2106.5**</span><span class="sxs-lookup"><span data-stu-id="80a38-145">&ensp;Platform: **4.18.2106.5**</span></span>  
<span data-ttu-id="80a38-146">&ensp;Mecanismo: **1.1.18300.4**</span><span class="sxs-lookup"><span data-stu-id="80a38-146">&ensp;Engine: **1.1.18300.4**</span></span>  
<span data-ttu-id="80a38-147">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="80a38-147">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="80a38-148">Novidades</span><span class="sxs-lookup"><span data-stu-id="80a38-148">What's new</span></span>
- <span data-ttu-id="80a38-149">Novos controles para gerenciar o processo de lançamento gradual das atualizações do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="80a38-149">New controls for managing the gradual rollout process of Microsoft Defender updates.</span></span> <span data-ttu-id="80a38-150">Consulte [Gerenciar o processo de lançamento gradual para atualizações do Microsoft Defender.](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="80a38-150">See [Manage the gradual rollout process for Microsoft Defender updates](manage-gradual-rollout.md).</span></span>
- <span data-ttu-id="80a38-151">Melhoria no mecanismo de monitoramento de comportamento</span><span class="sxs-lookup"><span data-stu-id="80a38-151">Improvement to the behavior monitoring engine</span></span>
- <span data-ttu-id="80a38-152">Melhorias na adoção de definições de antimalware</span><span class="sxs-lookup"><span data-stu-id="80a38-152">Improvements to the rollout of antimalware definitions</span></span>
- <span data-ttu-id="80a38-153">Inspeções de eventos de rede de Borda Estendida</span><span class="sxs-lookup"><span data-stu-id="80a38-153">Extended Edge network event inspections</span></span>

### <a name="known-issues"></a><span data-ttu-id="80a38-154">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="80a38-154">Known Issues</span></span>
<span data-ttu-id="80a38-155">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="80a38-155">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="80a38-156">Maio-2021 (plataforma: 4.18.2105.4 | Mecanismo: 1.1.18200.4)</span><span class="sxs-lookup"><span data-stu-id="80a38-156">May-2021 (Platform: 4.18.2105.4 | Engine: 1.1.18200.4)</span></span></summary>

<span data-ttu-id="80a38-157">&ensp;Versão de atualização de inteligência de segurança: **1.341.8.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-157">&ensp;Security intelligence update version: **1.341.8.0**</span></span>  
<span data-ttu-id="80a38-158">&ensp;Lançado: **3 de junho de 2021**</span><span class="sxs-lookup"><span data-stu-id="80a38-158">&ensp;Released: **June 3, 2021**</span></span>  
<span data-ttu-id="80a38-159">&ensp;Plataforma: **4.18.2105.4**</span><span class="sxs-lookup"><span data-stu-id="80a38-159">&ensp;Platform: **4.18.2105.4**</span></span>  
<span data-ttu-id="80a38-160">&ensp;Mecanismo: **1.1.18200.4**</span><span class="sxs-lookup"><span data-stu-id="80a38-160">&ensp;Engine: **1.1.18200.4**</span></span>  
<span data-ttu-id="80a38-161">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="80a38-161">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="80a38-162">Novidades</span><span class="sxs-lookup"><span data-stu-id="80a38-162">What's new</span></span>
- <span data-ttu-id="80a38-163">Melhorias [no monitoramento de comportamento](client-behavioral-blocking.md)</span><span class="sxs-lookup"><span data-stu-id="80a38-163">Improvements to [behavior monitoring](client-behavioral-blocking.md)</span></span> 
- <span data-ttu-id="80a38-164">Recurso [de filtragem de notificação](network-protection.md) de proteção de rede fixa</span><span class="sxs-lookup"><span data-stu-id="80a38-164">Fixed [network protection](network-protection.md) notification filtering feature</span></span>

### <a name="known-issues"></a><span data-ttu-id="80a38-165">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="80a38-165">Known Issues</span></span>
<span data-ttu-id="80a38-166">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="80a38-166">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="80a38-167">Abril-2021 (Plataforma: 4.18.2104.14 | Mecanismo: 1.1.18100.5)</span><span class="sxs-lookup"><span data-stu-id="80a38-167">April-2021 (Platform: 4.18.2104.14 | Engine: 1.1.18100.5)</span></span></summary>

<span data-ttu-id="80a38-168">&ensp;Versão de atualização de inteligência de segurança: **1.337.2.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-168">&ensp;Security intelligence update version: **1.337.2.0**</span></span>  
<span data-ttu-id="80a38-169">&ensp;Lançado: 26 de abril de **2021**  (Engine: 1.1.18100.6 lançado em 5 de maio de 2021) &ensp; Plataforma: **4.18.2104.14**</span><span class="sxs-lookup"><span data-stu-id="80a38-169">&ensp;Released: **April 26, 2021**  (Engine: 1.1.18100.6 released May 5, 2021) &ensp;Platform: **4.18.2104.14**</span></span>  
<span data-ttu-id="80a38-170">&ensp;Mecanismo: **1.1.18100.5**</span><span class="sxs-lookup"><span data-stu-id="80a38-170">&ensp;Engine: **1.1.18100.5**</span></span>  
<span data-ttu-id="80a38-171">&ensp;Fase de suporte: **Segurança e Atualizações Críticas**</span><span class="sxs-lookup"><span data-stu-id="80a38-171">&ensp;Support phase: **Security and Critical Updates**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="80a38-172">Novidades</span><span class="sxs-lookup"><span data-stu-id="80a38-172">What's new</span></span>
- <span data-ttu-id="80a38-173">Lógica adicional de monitoramento de comportamento</span><span class="sxs-lookup"><span data-stu-id="80a38-173">Additional behavior monitoring logic</span></span>
- <span data-ttu-id="80a38-174">Detecção aprimorada do fator de chave do modo kernel</span><span class="sxs-lookup"><span data-stu-id="80a38-174">Improved kernel mode key logger detection</span></span>
- <span data-ttu-id="80a38-175">Adicionados novos controles para gerenciar o processo de lançamento gradual para [atualizações do Microsoft Defender](manage-gradual-rollout.md)</span><span class="sxs-lookup"><span data-stu-id="80a38-175">Added new controls to manage the gradual rollout process for [Microsoft Defender updates](manage-gradual-rollout.md)</span></span>


### <a name="known-issues"></a><span data-ttu-id="80a38-176">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="80a38-176">Known Issues</span></span>
<span data-ttu-id="80a38-177">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="80a38-177">No known issues</span></span>  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a><span data-ttu-id="80a38-178">Atualizações de versão anterior: Suporte técnico somente a atualização</span><span class="sxs-lookup"><span data-stu-id="80a38-178">Previous version updates: Technical upgrade support only</span></span>

<span data-ttu-id="80a38-179">Depois que uma nova versão de pacote é lançada, o suporte para as duas versões anteriores é reduzido apenas ao suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="80a38-179">After a new package version is released, support for the previous two versions is reduced to technical support only.</span></span> <span data-ttu-id="80a38-180">Versões anteriores às listadas nesta seção são fornecidas apenas para suporte técnico de atualização.</span><span class="sxs-lookup"><span data-stu-id="80a38-180">Versions older than that are listed in this section, and are provided for technical upgrade support only.</span></span> 
<details>
<summary> <span data-ttu-id="80a38-181">Março-2021 (Plataforma: 4.18.2103.7 | Mecanismo: 1.1.18000.5)</span><span class="sxs-lookup"><span data-stu-id="80a38-181">March-2021 (Platform: 4.18.2103.7 | Engine: 1.1.18000.5)</span></span></summary>

<span data-ttu-id="80a38-182">&ensp;Versão de atualização de inteligência de segurança: **1.335.36.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-182">&ensp;Security intelligence update version: **1.335.36.0**</span></span>  
<span data-ttu-id="80a38-183">&ensp;Lançado: **2 de abril de 2021**</span><span class="sxs-lookup"><span data-stu-id="80a38-183">&ensp;Released: **April 2, 2021**</span></span>  
<span data-ttu-id="80a38-184">&ensp;Plataforma: **4.18.2103.7**</span><span class="sxs-lookup"><span data-stu-id="80a38-184">&ensp;Platform: **4.18.2103.7**</span></span>  
<span data-ttu-id="80a38-185">&ensp;Mecanismo: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="80a38-185">&ensp;Engine: **1.1.18000.5**</span></span>  
<span data-ttu-id="80a38-186">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="80a38-186">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="80a38-187">Novidades</span><span class="sxs-lookup"><span data-stu-id="80a38-187">What's new</span></span>

- <span data-ttu-id="80a38-188">Melhoria no mecanismo de Monitoramento de Comportamento</span><span class="sxs-lookup"><span data-stu-id="80a38-188">Improvement to the Behavior Monitoring engine</span></span> 
- <span data-ttu-id="80a38-189">Mitigações de ataques de força bruta de rede expandida</span><span class="sxs-lookup"><span data-stu-id="80a38-189">Expanded network brute-force-attack mitigations</span></span> 
- <span data-ttu-id="80a38-190">Geração adicional de eventos de tentativa de adulteração com falha quando [a Proteção contra Adulteração](prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada</span><span class="sxs-lookup"><span data-stu-id="80a38-190">Additional failed tampering attempt event generation when [Tamper Protection](prevent-changes-to-security-settings-with-tamper-protection.md) is enabled</span></span>

### <a name="known-issues"></a><span data-ttu-id="80a38-191">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="80a38-191">Known Issues</span></span>
<span data-ttu-id="80a38-192">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="80a38-192">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="80a38-193">Fevereiro-2021 (plataforma: 4.18.2102.3 | Mecanismo: 1.1.17900.7)</span><span class="sxs-lookup"><span data-stu-id="80a38-193">February-2021 (Platform: 4.18.2102.3 | Engine: 1.1.17900.7)</span></span></summary>

<span data-ttu-id="80a38-194">&ensp;Versão de atualização de inteligência de segurança: **1.333.7.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-194">&ensp;Security intelligence update version: **1.333.7.0**</span></span>  
<span data-ttu-id="80a38-195">&ensp;Lançado: **9 de março de 2021**</span><span class="sxs-lookup"><span data-stu-id="80a38-195">&ensp;Released: **March 9, 2021**</span></span>  
<span data-ttu-id="80a38-196">&ensp;Plataforma: **4.18.2102.3**</span><span class="sxs-lookup"><span data-stu-id="80a38-196">&ensp;Platform: **4.18.2102.3**</span></span>  
<span data-ttu-id="80a38-197">&ensp;Mecanismo: **1.1.17900.7**</span><span class="sxs-lookup"><span data-stu-id="80a38-197">&ensp;Engine: **1.1.17900.7**</span></span>  
<span data-ttu-id="80a38-198">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="80a38-198">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="80a38-199">Novidades</span><span class="sxs-lookup"><span data-stu-id="80a38-199">What's new</span></span>

- <span data-ttu-id="80a38-200">Recuperação aprimorada do serviço por meio [da proteção contra violações](prevent-changes-to-security-settings-with-tamper-protection.md)</span><span class="sxs-lookup"><span data-stu-id="80a38-200">Improved service recovery through [tamper protection](prevent-changes-to-security-settings-with-tamper-protection.md)</span></span>
- <span data-ttu-id="80a38-201">Estender escopo de proteção contra violações</span><span class="sxs-lookup"><span data-stu-id="80a38-201">Extend tamper protection scope</span></span>

### <a name="known-issues"></a><span data-ttu-id="80a38-202">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="80a38-202">Known Issues</span></span>
<span data-ttu-id="80a38-203">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="80a38-203">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="80a38-204">Janeiro-2021 (Plataforma: 4.18.2101.9 | Mecanismo: 1.1.17800.5)</span><span class="sxs-lookup"><span data-stu-id="80a38-204">January-2021 (Platform: 4.18.2101.9 | Engine: 1.1.17800.5)</span></span></summary>

<span data-ttu-id="80a38-205">&ensp;Versão de atualização de inteligência de segurança: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-205">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="80a38-206">&ensp;Lançado: **2 de fevereiro de 2021**</span><span class="sxs-lookup"><span data-stu-id="80a38-206">&ensp;Released: **February 2, 2021**</span></span>  
<span data-ttu-id="80a38-207">&ensp;Plataforma: **4.18.2101.9**</span><span class="sxs-lookup"><span data-stu-id="80a38-207">&ensp;Platform: **4.18.2101.9**</span></span>  
<span data-ttu-id="80a38-208">&ensp;Mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="80a38-208">&ensp;Engine: **1.1.17800.5**</span></span>  
<span data-ttu-id="80a38-209">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="80a38-209">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="80a38-210">Novidades</span><span class="sxs-lookup"><span data-stu-id="80a38-210">What's new</span></span>

- <span data-ttu-id="80a38-211">Melhorias na detecção de exploração de shellcode</span><span class="sxs-lookup"><span data-stu-id="80a38-211">Shellcode exploit detection improvements</span></span>
- <span data-ttu-id="80a38-212">Maior visibilidade para tentativas de roubo de credenciais</span><span class="sxs-lookup"><span data-stu-id="80a38-212">Increased visibility for credential stealing attempts</span></span>
- <span data-ttu-id="80a38-213">Melhorias nos recursos anti-amperes em serviços Microsoft Defender Antivírus serviços</span><span class="sxs-lookup"><span data-stu-id="80a38-213">Improvements in antitampering features in Microsoft Defender Antivirus services</span></span>
- <span data-ttu-id="80a38-214">Suporte aprimorado para ARM emulação x64</span><span class="sxs-lookup"><span data-stu-id="80a38-214">Improved support for ARM x64 emulation</span></span>
- <span data-ttu-id="80a38-215">Correção: EDR a notificação de bloqueio permanece no histórico de ameaças depois que a proteção em tempo real realizou a detecção inicial</span><span class="sxs-lookup"><span data-stu-id="80a38-215">Fix: EDR Block notification remains in threat history after real-time protection performed initial detection</span></span>

### <a name="known-issues"></a><span data-ttu-id="80a38-216">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="80a38-216">Known Issues</span></span>
<span data-ttu-id="80a38-217">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="80a38-217">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="80a38-218">Novembro-2020 (Plataforma: 4.18.2011.6 | Mecanismo: 1.1.17700.4)</span><span class="sxs-lookup"><span data-stu-id="80a38-218">November-2020 (Platform: 4.18.2011.6 | Engine: 1.1.17700.4)</span></span></summary>

<span data-ttu-id="80a38-219">&ensp;Versão de atualização de inteligência de segurança: **1.327.1854.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-219">&ensp;Security intelligence update version: **1.327.1854.0**</span></span>  
<span data-ttu-id="80a38-220">&ensp;Lançado: **03 de dezembro de 2020**</span><span class="sxs-lookup"><span data-stu-id="80a38-220">&ensp;Released: **December 03, 2020**</span></span>  
<span data-ttu-id="80a38-221">&ensp;Plataforma: **4.18.2011.6**</span><span class="sxs-lookup"><span data-stu-id="80a38-221">&ensp;Platform: **4.18.2011.6**</span></span>  
<span data-ttu-id="80a38-222">&ensp;Mecanismo: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="80a38-222">&ensp;Engine: **1.1.17700.4**</span></span>  
<span data-ttu-id="80a38-223">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="80a38-223">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="80a38-224">Novidades</span><span class="sxs-lookup"><span data-stu-id="80a38-224">What's new</span></span>

- <span data-ttu-id="80a38-225">Registro em log de suporte ao status [do SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) aprimorado</span><span class="sxs-lookup"><span data-stu-id="80a38-225">Improved [SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) status support logging</span></span>

### <a name="known-issues"></a><span data-ttu-id="80a38-226">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="80a38-226">Known Issues</span></span>
<span data-ttu-id="80a38-227">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="80a38-227">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="80a38-228">Outubro-2020 (Plataforma: 4.18.2010.7 | Mecanismo: 1.1.17600.5)</span><span class="sxs-lookup"><span data-stu-id="80a38-228">October-2020 (Platform: 4.18.2010.7 | Engine: 1.1.17600.5)</span></span></summary>

<span data-ttu-id="80a38-229">&ensp;Versão de atualização de inteligência de segurança: **1.327.7.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-229">&ensp;Security intelligence update version: **1.327.7.0**</span></span>  
<span data-ttu-id="80a38-230">&ensp;Lançado: **29 de outubro de 2020**</span><span class="sxs-lookup"><span data-stu-id="80a38-230">&ensp;Released: **October 29, 2020**</span></span>  
<span data-ttu-id="80a38-231">&ensp;Plataforma: **4.18.2010.7**</span><span class="sxs-lookup"><span data-stu-id="80a38-231">&ensp;Platform: **4.18.2010.7**</span></span>  
<span data-ttu-id="80a38-232">&ensp;Mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="80a38-232">&ensp;Engine: **1.1.17600.5**</span></span>  
<span data-ttu-id="80a38-233">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="80a38-233">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="80a38-234">Novidades</span><span class="sxs-lookup"><span data-stu-id="80a38-234">What's new</span></span>

- <span data-ttu-id="80a38-235">Novas descrições para categorias de ameaças especiais</span><span class="sxs-lookup"><span data-stu-id="80a38-235">New descriptions for special threat categories</span></span>
- <span data-ttu-id="80a38-236">Recursos de emulação aprimorados</span><span class="sxs-lookup"><span data-stu-id="80a38-236">Improved emulation capabilities</span></span>
- <span data-ttu-id="80a38-237">Recursos de permitir/bloquear endereço de host aprimorados</span><span class="sxs-lookup"><span data-stu-id="80a38-237">Improved host address allow/block capabilities</span></span>
- <span data-ttu-id="80a38-238">Nova opção no CSP do Defender para Ignorar a mesclação de exclusões de usuários locais</span><span class="sxs-lookup"><span data-stu-id="80a38-238">New option in Defender CSP to Ignore merging of local user exclusions</span></span>

### <a name="known-issues"></a><span data-ttu-id="80a38-239">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="80a38-239">Known Issues</span></span>

<span data-ttu-id="80a38-240">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="80a38-240">No known issues</span></span>  
<br/>
</details><details>
<summary> <span data-ttu-id="80a38-241">Setembro-2020 (Plataforma: 4.18.2009.7 | Mecanismo: 1.1.17500.4)</span><span class="sxs-lookup"><span data-stu-id="80a38-241">September-2020 (Platform: 4.18.2009.7 | Engine: 1.1.17500.4)</span></span></summary>

<span data-ttu-id="80a38-242">&ensp;Versão de atualização de inteligência de segurança: **1.325.10.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-242">&ensp;Security intelligence update version: **1.325.10.0**</span></span>  
<span data-ttu-id="80a38-243">&ensp;Lançado: **01 de outubro de 2020**</span><span class="sxs-lookup"><span data-stu-id="80a38-243">&ensp;Released: **October 01, 2020**</span></span>  
<span data-ttu-id="80a38-244">&ensp;Plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="80a38-244">&ensp;Platform: **4.18.2009.7**</span></span>  
<span data-ttu-id="80a38-245">&ensp;Mecanismo: **1.1.17500.4**</span><span class="sxs-lookup"><span data-stu-id="80a38-245">&ensp;Engine: **1.1.17500.4**</span></span>  
<span data-ttu-id="80a38-246">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="80a38-246">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="80a38-247">Novidades</span><span class="sxs-lookup"><span data-stu-id="80a38-247">What's new</span></span>

- <span data-ttu-id="80a38-248">Permissões de administrador são necessárias para restaurar arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="80a38-248">Admin permissions are required to restore files in quarantine</span></span>
- <span data-ttu-id="80a38-249">Eventos formatados xml agora são suportados</span><span class="sxs-lookup"><span data-stu-id="80a38-249">XML formatted events are now supported</span></span>
- <span data-ttu-id="80a38-250">Suporte a CSP para ignorar mesclações de exclusão</span><span class="sxs-lookup"><span data-stu-id="80a38-250">CSP support for ignoring exclusion merges</span></span>
- <span data-ttu-id="80a38-251">Novas interfaces de gerenciamento para:</span><span class="sxs-lookup"><span data-stu-id="80a38-251">New management interfaces for:</span></span>
   - <span data-ttu-id="80a38-252">Inspeção UDP</span><span class="sxs-lookup"><span data-stu-id="80a38-252">UDP Inspection</span></span>
   - <span data-ttu-id="80a38-253">Proteção de Rede no Server 2019</span><span class="sxs-lookup"><span data-stu-id="80a38-253">Network Protection on Server 2019</span></span>
   - <span data-ttu-id="80a38-254">Exclusões de endereço IP para Proteção de Rede</span><span class="sxs-lookup"><span data-stu-id="80a38-254">IP Address exclusions for Network Protection</span></span>
- <span data-ttu-id="80a38-255">Visibilidade aprimorada nas medições do TPM</span><span class="sxs-lookup"><span data-stu-id="80a38-255">Improved visibility into TPM measurements</span></span>
- <span data-ttu-id="80a38-256">Verificação aprimorada Office módulo VBA</span><span class="sxs-lookup"><span data-stu-id="80a38-256">Improved Office VBA module scanning</span></span>

### <a name="known-issues"></a><span data-ttu-id="80a38-257">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="80a38-257">Known Issues</span></span>

<span data-ttu-id="80a38-258">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="80a38-258">No known issues</span></span>  
<br/>
</details>
<details>
<summary> <span data-ttu-id="80a38-259">Agosto-2020 (plataforma: 4.18.2008.9 | Mecanismo: 1.1.17400.5)</span><span class="sxs-lookup"><span data-stu-id="80a38-259">August-2020 (Platform: 4.18.2008.9 | Engine: 1.1.17400.5)</span></span></summary>

<span data-ttu-id="80a38-260">&ensp;Versão de atualização de inteligência de segurança: **1.323.9.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-260">&ensp;Security intelligence update version: **1.323.9.0**</span></span>  
<span data-ttu-id="80a38-261">&ensp;Lançado: **27 de agosto de 2020**</span><span class="sxs-lookup"><span data-stu-id="80a38-261">&ensp;Released: **August 27, 2020**</span></span>  
<span data-ttu-id="80a38-262">&ensp;Plataforma: **4.18.2008.9**</span><span class="sxs-lookup"><span data-stu-id="80a38-262">&ensp;Platform: **4.18.2008.9**</span></span>  
<span data-ttu-id="80a38-263">&ensp;Mecanismo: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="80a38-263">&ensp;Engine: **1.1.17400.5**</span></span>  
<span data-ttu-id="80a38-264">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="80a38-264">&ensp;Support phase: **Technical upgrade support (only)**</span></span>

### <a name="whats-new"></a><span data-ttu-id="80a38-265">Novidades</span><span class="sxs-lookup"><span data-stu-id="80a38-265">What's new</span></span>

- <span data-ttu-id="80a38-266">Adicionar mais eventos de telemetria</span><span class="sxs-lookup"><span data-stu-id="80a38-266">Add more telemetry events</span></span>
- <span data-ttu-id="80a38-267">Telemetria de eventos de verificação aprimorada</span><span class="sxs-lookup"><span data-stu-id="80a38-267">Improved scan event telemetry</span></span>
- <span data-ttu-id="80a38-268">Monitoramento de comportamento aprimorado para verificações de memória</span><span class="sxs-lookup"><span data-stu-id="80a38-268">Improved behavior monitoring for memory scans</span></span>
- <span data-ttu-id="80a38-269">Verificação de fluxos de macros aprimorados</span><span class="sxs-lookup"><span data-stu-id="80a38-269">Improved macro streams scanning</span></span>
- <span data-ttu-id="80a38-270">Adicionado `AMRunningMode` ao cmdlet Get-MpComputerStatus PowerShell</span><span class="sxs-lookup"><span data-stu-id="80a38-270">Added `AMRunningMode` to Get-MpComputerStatus PowerShell cmdlet</span></span>
- <span data-ttu-id="80a38-271">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) é ignorado.</span><span class="sxs-lookup"><span data-stu-id="80a38-271">[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) is ignored.</span></span> <span data-ttu-id="80a38-272">Microsoft Defender Antivírus se desliga automaticamente quando detecta outro programa antivírus.</span><span class="sxs-lookup"><span data-stu-id="80a38-272">Microsoft Defender Antivirus automatically turns itself off when it detects another antivirus program.</span></span>


### <a name="known-issues"></a><span data-ttu-id="80a38-273">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="80a38-273">Known Issues</span></span>
<span data-ttu-id="80a38-274">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="80a38-274">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="80a38-275">Julho-2020 (Plataforma: 4.18.2007.8 | Mecanismo: 1.1.17300.4)</span><span class="sxs-lookup"><span data-stu-id="80a38-275">July-2020 (Platform: 4.18.2007.8 | Engine: 1.1.17300.4)</span></span></summary>

<span data-ttu-id="80a38-276">&ensp;Versão de atualização de inteligência de segurança: **1.321.30.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-276">&ensp;Security intelligence update version: **1.321.30.0**</span></span>  
<span data-ttu-id="80a38-277">&ensp;Lançado: **28 de julho de 2020**</span><span class="sxs-lookup"><span data-stu-id="80a38-277">&ensp;Released: **July 28, 2020**</span></span>  
<span data-ttu-id="80a38-278">&ensp;Plataforma: **4.18.2007.8**</span><span class="sxs-lookup"><span data-stu-id="80a38-278">&ensp;Platform: **4.18.2007.8**</span></span>  
<span data-ttu-id="80a38-279">&ensp;Mecanismo: **1.1.17300.4**</span><span class="sxs-lookup"><span data-stu-id="80a38-279">&ensp;Engine: **1.1.17300.4**</span></span>  
<span data-ttu-id="80a38-280">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="80a38-280">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="80a38-281">Novidades</span><span class="sxs-lookup"><span data-stu-id="80a38-281">What's new</span></span>

- <span data-ttu-id="80a38-282">Telemetria aprimorada para BITS</span><span class="sxs-lookup"><span data-stu-id="80a38-282">Improved telemetry for BITS</span></span>
- <span data-ttu-id="80a38-283">Validação aprimorada de certificado de assinatura de código Authenticode</span><span class="sxs-lookup"><span data-stu-id="80a38-283">Improved Authenticode code signing certificate validation</span></span>

### <a name="known-issues"></a><span data-ttu-id="80a38-284">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="80a38-284">Known Issues</span></span>
<span data-ttu-id="80a38-285">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="80a38-285">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="80a38-286">Junho-2020 (Plataforma: 4.18.2006.10 | Mecanismo: 1.1.17200.2)</span><span class="sxs-lookup"><span data-stu-id="80a38-286">June-2020 (Platform: 4.18.2006.10 | Engine: 1.1.17200.2)</span></span></summary>

<span data-ttu-id="80a38-287">&ensp;Versão de atualização de inteligência de segurança: **1.319.20.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-287">&ensp;Security intelligence update version: **1.319.20.0**</span></span>  
<span data-ttu-id="80a38-288">&ensp;Lançado: **22 de junho de 2020**</span><span class="sxs-lookup"><span data-stu-id="80a38-288">&ensp;Released: **June 22, 2020**</span></span>  
<span data-ttu-id="80a38-289">&ensp;Plataforma: **4.18.2006.10**</span><span class="sxs-lookup"><span data-stu-id="80a38-289">&ensp;Platform: **4.18.2006.10**</span></span>  
<span data-ttu-id="80a38-290">&ensp;Mecanismo: **1.1.17200.2**</span><span class="sxs-lookup"><span data-stu-id="80a38-290">&ensp;Engine: **1.1.17200.2**</span></span>  
<span data-ttu-id="80a38-291">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="80a38-291">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="80a38-292">Novidades</span><span class="sxs-lookup"><span data-stu-id="80a38-292">What's new</span></span>

- <span data-ttu-id="80a38-293">Possibilidade de especificar o [local dos logs de suporte](./collect-diagnostic-data.md)</span><span class="sxs-lookup"><span data-stu-id="80a38-293">Possibility to specify the [location of the support logs](./collect-diagnostic-data.md)</span></span>
- <span data-ttu-id="80a38-294">Ignorar a verificação de captura agressiva no modo Passivo.</span><span class="sxs-lookup"><span data-stu-id="80a38-294">Skipping aggressive catchup scan in Passive mode.</span></span>
- <span data-ttu-id="80a38-295">Permitir que o Defender atualize em conexões com metros</span><span class="sxs-lookup"><span data-stu-id="80a38-295">Allow Defender to update on metered connections</span></span>
- <span data-ttu-id="80a38-296">Ajuste de desempenho fixo quando o cache está desabilitado</span><span class="sxs-lookup"><span data-stu-id="80a38-296">Fixed performance tuning when caching is disabled</span></span> 
- <span data-ttu-id="80a38-297">Consulta de registro fixa</span><span class="sxs-lookup"><span data-stu-id="80a38-297">Fixed registry query</span></span> 
- <span data-ttu-id="80a38-298">Randomização de tempo de verificação fixa no ADMX</span><span class="sxs-lookup"><span data-stu-id="80a38-298">Fixed scantime randomization in ADMX</span></span>

### <a name="known-issues"></a><span data-ttu-id="80a38-299">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="80a38-299">Known Issues</span></span>
<span data-ttu-id="80a38-300">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="80a38-300">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="80a38-301">Maio-2020 (plataforma: 4.18.2005.4 | Mecanismo: 1.1.17100.2)</span><span class="sxs-lookup"><span data-stu-id="80a38-301">May-2020 (Platform: 4.18.2005.4 | Engine: 1.1.17100.2)</span></span></summary>

<span data-ttu-id="80a38-302">&ensp;Versão de atualização de inteligência de segurança: **1.317.20.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-302">&ensp;Security intelligence update version: **1.317.20.0**</span></span>  
<span data-ttu-id="80a38-303">&ensp;Lançado: **26 de maio de 2020**</span><span class="sxs-lookup"><span data-stu-id="80a38-303">&ensp;Released: **May 26, 2020**</span></span>  
<span data-ttu-id="80a38-304">&ensp;Plataforma: **4.18.2005.4**</span><span class="sxs-lookup"><span data-stu-id="80a38-304">&ensp;Platform: **4.18.2005.4**</span></span>  
<span data-ttu-id="80a38-305">&ensp;Mecanismo: **1.1.17100.2**</span><span class="sxs-lookup"><span data-stu-id="80a38-305">&ensp;Engine: **1.1.17100.2**</span></span>  
<span data-ttu-id="80a38-306">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="80a38-306">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="80a38-307">Novidades</span><span class="sxs-lookup"><span data-stu-id="80a38-307">What's new</span></span>

- <span data-ttu-id="80a38-308">Registro em log aprimorado para eventos de verificação</span><span class="sxs-lookup"><span data-stu-id="80a38-308">Improved logging for scan events</span></span>
- <span data-ttu-id="80a38-309">Melhor tratamento de falhas no modo de usuário.</span><span class="sxs-lookup"><span data-stu-id="80a38-309">Improved user mode crash handling.</span></span>
- <span data-ttu-id="80a38-310">Rastreamento de eventos adicionado para proteção contra adulteração</span><span class="sxs-lookup"><span data-stu-id="80a38-310">Added event tracing for Tamper protection</span></span>
- <span data-ttu-id="80a38-311">Envio de amostra AMSI corrigido</span><span class="sxs-lookup"><span data-stu-id="80a38-311">Fixed AMSI Sample submission</span></span>
- <span data-ttu-id="80a38-312">Bloqueio fixo da nuvem AMSI</span><span class="sxs-lookup"><span data-stu-id="80a38-312">Fixed AMSI Cloud blocking</span></span>
- <span data-ttu-id="80a38-313">Log de instalação de atualização de segurança fixa</span><span class="sxs-lookup"><span data-stu-id="80a38-313">Fixed Security update install log</span></span>

### <a name="known-issues"></a><span data-ttu-id="80a38-314">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="80a38-314">Known Issues</span></span>
<span data-ttu-id="80a38-315">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="80a38-315">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="80a38-316">Abril-2020 (Plataforma: 4.18.2004.6 | Mecanismo: 1.1.17000.2)</span><span class="sxs-lookup"><span data-stu-id="80a38-316">April-2020 (Platform: 4.18.2004.6 | Engine: 1.1.17000.2)</span></span></summary>

<span data-ttu-id="80a38-317">&ensp;Versão de atualização de inteligência de segurança: **1.315.12.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-317">&ensp;Security intelligence update version: **1.315.12.0**</span></span>  
<span data-ttu-id="80a38-318">&ensp;Lançado: **30 de abril de 2020**</span><span class="sxs-lookup"><span data-stu-id="80a38-318">&ensp;Released: **April 30, 2020**</span></span>  
<span data-ttu-id="80a38-319">&ensp;Plataforma: **4.18.2004.6**</span><span class="sxs-lookup"><span data-stu-id="80a38-319">&ensp;Platform: **4.18.2004.6**</span></span>  
<span data-ttu-id="80a38-320">&ensp;Mecanismo: **1.1.17000.2**</span><span class="sxs-lookup"><span data-stu-id="80a38-320">&ensp;Engine: **1.1.17000.2**</span></span>  
<span data-ttu-id="80a38-321">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="80a38-321">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="80a38-322">Novidades</span><span class="sxs-lookup"><span data-stu-id="80a38-322">What's new</span></span>
- <span data-ttu-id="80a38-323">Melhorias do WDfilter</span><span class="sxs-lookup"><span data-stu-id="80a38-323">WDfilter improvements</span></span>
- <span data-ttu-id="80a38-324">Adicionar mais dados de evento acionáveis para atacar eventos de detecção de redução de superfície</span><span class="sxs-lookup"><span data-stu-id="80a38-324">Add more actionable event data to attack surface reduction detection events</span></span>
- <span data-ttu-id="80a38-325">Informações de versão fixas em dados de diagnóstico e WMI</span><span class="sxs-lookup"><span data-stu-id="80a38-325">Fixed version information in diagnostic data and WMI</span></span>
- <span data-ttu-id="80a38-326">Versão da plataforma incorreta corrigida na interface do usuário após a atualização da plataforma</span><span class="sxs-lookup"><span data-stu-id="80a38-326">Fixed incorrect platform version in UI after platform update</span></span>
- <span data-ttu-id="80a38-327">Intel de URL dinâmica para proteção contra ameaças sem arquivo</span><span class="sxs-lookup"><span data-stu-id="80a38-327">Dynamic URL intel for Fileless threat protection</span></span>
- <span data-ttu-id="80a38-328">Recurso de verificação UEFI</span><span class="sxs-lookup"><span data-stu-id="80a38-328">UEFI scan capability</span></span>
- <span data-ttu-id="80a38-329">Estender o log para atualizações</span><span class="sxs-lookup"><span data-stu-id="80a38-329">Extend logging for updates</span></span>

### <a name="known-issues"></a><span data-ttu-id="80a38-330">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="80a38-330">Known Issues</span></span>
<span data-ttu-id="80a38-331">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="80a38-331">No known issues</span></span>  
<br/>
</details>

<details>
<summary> <span data-ttu-id="80a38-332">Março-2020 (Plataforma: 4.18.2003.8 | Mecanismo: 1.1.16900.2)</span><span class="sxs-lookup"><span data-stu-id="80a38-332">March-2020 (Platform: 4.18.2003.8 | Engine: 1.1.16900.2)</span></span></summary>

<span data-ttu-id="80a38-333">&ensp;Versão de atualização de inteligência de segurança: **1.313.8.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-333">&ensp;Security intelligence update version: **1.313.8.0**</span></span>  
<span data-ttu-id="80a38-334">&ensp;Lançado: **24 de março de 2020**</span><span class="sxs-lookup"><span data-stu-id="80a38-334">&ensp;Released: **March 24, 2020**</span></span>  
<span data-ttu-id="80a38-335">&ensp;Plataforma: **4.18.2003.8**</span><span class="sxs-lookup"><span data-stu-id="80a38-335">&ensp;Platform: **4.18.2003.8**</span></span>  
<span data-ttu-id="80a38-336">&ensp;Mecanismo: **1.1.16900.4**</span><span class="sxs-lookup"><span data-stu-id="80a38-336">&ensp;Engine: **1.1.16900.4**</span></span>  
<span data-ttu-id="80a38-337">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="80a38-337">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
    
### <a name="whats-new"></a><span data-ttu-id="80a38-338">Novidades</span><span class="sxs-lookup"><span data-stu-id="80a38-338">What's new</span></span>

- <span data-ttu-id="80a38-339">Opção de throttling de CPU adicionada ao [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="80a38-339">CPU Throttling option added to [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)</span></span>
- <span data-ttu-id="80a38-340">Melhorar a funcionalidade de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="80a38-340">Improve diagnostic capability</span></span>
- <span data-ttu-id="80a38-341">reduzir o tempo de tempo de inteligência de segurança (5 minutos)</span><span class="sxs-lookup"><span data-stu-id="80a38-341">reduce Security intelligence timeout (5 min)</span></span>
- <span data-ttu-id="80a38-342">Estender a funcionalidade de log interno do mecanismo AMSI</span><span class="sxs-lookup"><span data-stu-id="80a38-342">Extend AMSI engine internal log capability</span></span>
- <span data-ttu-id="80a38-343">Melhorar a notificação para bloqueio de processos</span><span class="sxs-lookup"><span data-stu-id="80a38-343">Improve notification for process blocking</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="80a38-344">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="80a38-344">Known Issues</span></span>
<span data-ttu-id="80a38-345">[**Fixo**] Microsoft Defender Antivírus está ignorando arquivos ao executar uma verificação.</span><span class="sxs-lookup"><span data-stu-id="80a38-345">[**Fixed**] Microsoft Defender Antivirus is skipping files when running a scan.</span></span>

<br/>
</details>

<details>

<summary> <span data-ttu-id="80a38-346">Fevereiro-2020 (Plataforma: - | Mecanismo: 1.1.16800.2)</span><span class="sxs-lookup"><span data-stu-id="80a38-346">February-2020 (Platform: - | Engine: 1.1.16800.2)</span></span></summary>
  

<span data-ttu-id="80a38-347">&ensp;Versão de atualização de inteligência de segurança: **1.311.4.0** </span><span class="sxs-lookup"><span data-stu-id="80a38-347">&ensp;Security intelligence update version: **1.311.4.0** </span></span>  
<span data-ttu-id="80a38-348">&ensp;Lançado: **25 de fevereiro de 2020**</span><span class="sxs-lookup"><span data-stu-id="80a38-348">&ensp;Released: **February 25, 2020**</span></span>  
<span data-ttu-id="80a38-349">&ensp;Plataforma/Cliente: **-**</span><span class="sxs-lookup"><span data-stu-id="80a38-349">&ensp;Platform/Client: **-**</span></span>  
<span data-ttu-id="80a38-350">&ensp;Mecanismo: **1.1.16800.2**</span><span class="sxs-lookup"><span data-stu-id="80a38-350">&ensp;Engine: **1.1.16800.2**</span></span>  
<span data-ttu-id="80a38-351">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="80a38-351">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="80a38-352">Novidades</span><span class="sxs-lookup"><span data-stu-id="80a38-352">What's new</span></span>

  
### <a name="known-issues"></a><span data-ttu-id="80a38-353">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="80a38-353">Known Issues</span></span>
<span data-ttu-id="80a38-354">Nenhum problema conhecido</span><span class="sxs-lookup"><span data-stu-id="80a38-354">No known issues</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="80a38-355">Janeiro-2020 (Plataforma: 4.18.2001.10 | Mecanismo: 1.1.16700.2)</span><span class="sxs-lookup"><span data-stu-id="80a38-355">January-2020 (Platform: 4.18.2001.10 | Engine: 1.1.16700.2)</span></span></summary>
  

<span data-ttu-id="80a38-356">Versão de atualização de inteligência de segurança: **1.309.32.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-356">Security intelligence update version: **1.309.32.0**</span></span>  
<span data-ttu-id="80a38-357">Lançado: **30 de janeiro de 2020**</span><span class="sxs-lookup"><span data-stu-id="80a38-357">Released: **January 30, 2020**</span></span>  
<span data-ttu-id="80a38-358">Plataforma/Cliente: **4.18.2001.10**</span><span class="sxs-lookup"><span data-stu-id="80a38-358">Platform/Client: **4.18.2001.10**</span></span>  
<span data-ttu-id="80a38-359">Mecanismo: **1.1.16700.2**</span><span class="sxs-lookup"><span data-stu-id="80a38-359">Engine: **1.1.16700.2**</span></span>  
<span data-ttu-id="80a38-360">&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**</span><span class="sxs-lookup"><span data-stu-id="80a38-360">&ensp;Support phase: **Technical upgrade support (only)**</span></span>
     
### <a name="whats-new"></a><span data-ttu-id="80a38-361">Novidades</span><span class="sxs-lookup"><span data-stu-id="80a38-361">What's new</span></span>

- <span data-ttu-id="80a38-362">BSOD fixo no WS2016 com Exchange</span><span class="sxs-lookup"><span data-stu-id="80a38-362">Fixed BSOD on WS2016 with Exchange</span></span>
- <span data-ttu-id="80a38-363">Atualizações da plataforma de suporte quando o TMP é redirecionado para o caminho da rede</span><span class="sxs-lookup"><span data-stu-id="80a38-363">Support platform updates when TMP is redirected to network path</span></span>
- <span data-ttu-id="80a38-364">As versões de plataforma e mecanismo são [adicionadas ao WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span><span class="sxs-lookup"><span data-stu-id="80a38-364">Platform and engine versions are added to [WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates)</span></span> <!-- The preceding URL must include "/en-us" -->
- <span data-ttu-id="80a38-365">estender a atualização de assinatura de emergência para [o modo passivo](./microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="80a38-365">extend Emergency signature update to [passive mode](./microsoft-defender-antivirus-compatibility.md)</span></span>
- <span data-ttu-id="80a38-366">Corrigir trava 4.18.1911.3</span><span class="sxs-lookup"><span data-stu-id="80a38-366">Fix 4.18.1911.3 hang</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="80a38-367">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="80a38-367">Known Issues</span></span>

<span data-ttu-id="80a38-368">[**Fixo**] dispositivos [que](/windows-hardware/design/device-experiences/modern-standby) usam o modo de espera moderno podem ter uma trava com o driver de filtro Windows Defender que resulta em uma lacuna de proteção.</span><span class="sxs-lookup"><span data-stu-id="80a38-368">[**Fixed**] devices utilizing [modern standby mode](/windows-hardware/design/device-experiences/modern-standby) may experience a hang with the Windows Defender filter driver that results in a gap of protection.</span></span>  <span data-ttu-id="80a38-369">Os máquinas afetados aparecem para o cliente como não atualizados para a plataforma antimalware mais recente.</span><span class="sxs-lookup"><span data-stu-id="80a38-369">Affected machines appear to the customer as having not updated to the latest antimalware platform.</span></span>  
<br/>
> [!IMPORTANT]
> <span data-ttu-id="80a38-370">Esta atualização é:</span><span class="sxs-lookup"><span data-stu-id="80a38-370">This update is:</span></span>
> - <span data-ttu-id="80a38-371">necessário por dispositivos RS1 que executam a versão inferior da plataforma para dar suporte ao SHA2;</span><span class="sxs-lookup"><span data-stu-id="80a38-371">needed by RS1 devices running lower version of the platform to support SHA2;</span></span>
> - <span data-ttu-id="80a38-372">tem um sinalizador de reinicialização para sistemas que têm problemas de suspensão;</span><span class="sxs-lookup"><span data-stu-id="80a38-372">has a reboot flag for systems that have hanging issues;</span></span>
> - <span data-ttu-id="80a38-373">é re-lançado em abril de 2020 e não será superada por atualizações mais novas para manter a disponibilidade futura;</span><span class="sxs-lookup"><span data-stu-id="80a38-373">is re-released in April 2020 and will not be superseded by newer updates to keep future availability;</span></span>  
> - <span data-ttu-id="80a38-374">é categorizado como uma atualização devido ao requisito de reinicialização; e</span><span class="sxs-lookup"><span data-stu-id="80a38-374">is categorized as an update due to the reboot requirement; and</span></span>
> - <span data-ttu-id="80a38-375">só será oferecido com o [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span><span class="sxs-lookup"><span data-stu-id="80a38-375">is only be offered with [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).</span></span>
<br/>
</details>

<details>
<summary> <span data-ttu-id="80a38-376">Novembro-2019 (plataforma: 4.18.1911.3 | Mecanismo: 1.1.16600.7)</span><span class="sxs-lookup"><span data-stu-id="80a38-376">November-2019 (Platform: 4.18.1911.3 | Engine: 1.1.16600.7)</span></span></summary>

<span data-ttu-id="80a38-377">Versão de atualização de inteligência de segurança: **1.307.13.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-377">Security intelligence update version: **1.307.13.0**</span></span>  
<span data-ttu-id="80a38-378">Lançado: **7 de dezembro de 2019**</span><span class="sxs-lookup"><span data-stu-id="80a38-378">Released: **December 7, 2019**</span></span>  
<span data-ttu-id="80a38-379">Plataforma: **4.18.1911.3**</span><span class="sxs-lookup"><span data-stu-id="80a38-379">Platform: **4.18.1911.3**</span></span>  
<span data-ttu-id="80a38-380">Mecanismo: **1.1.17000.7**</span><span class="sxs-lookup"><span data-stu-id="80a38-380">Engine: **1.1.17000.7**</span></span>  
<span data-ttu-id="80a38-381">Fase de suporte: **sem suporte**</span><span class="sxs-lookup"><span data-stu-id="80a38-381">Support phase: **No support**</span></span>  
     
### <a name="whats-new"></a><span data-ttu-id="80a38-382">Novidades</span><span class="sxs-lookup"><span data-stu-id="80a38-382">What's new</span></span>

- <span data-ttu-id="80a38-383">Nível de rastreamento De MpCmdRun fixo</span><span class="sxs-lookup"><span data-stu-id="80a38-383">Fixed MpCmdRun tracing level</span></span>
- <span data-ttu-id="80a38-384">Informações de versão fixas do WDFilter</span><span class="sxs-lookup"><span data-stu-id="80a38-384">Fixed WDFilter version info</span></span>
- <span data-ttu-id="80a38-385">Melhorar notificações (PUA)</span><span class="sxs-lookup"><span data-stu-id="80a38-385">Improve notifications (PUA)</span></span>
- <span data-ttu-id="80a38-386">adicionar logs MRT para dar suporte a arquivos</span><span class="sxs-lookup"><span data-stu-id="80a38-386">add MRT logs to support files</span></span>
   
### <a name="known-issues"></a><span data-ttu-id="80a38-387">Problemas Conhecidos</span><span class="sxs-lookup"><span data-stu-id="80a38-387">Known Issues</span></span>
<span data-ttu-id="80a38-388">Quando essa atualização é instalada, o dispositivo precisa do pacote de salto 4.18.2001.10 para poder atualizar para a versão mais recente da plataforma.</span><span class="sxs-lookup"><span data-stu-id="80a38-388">When this update is installed, the device needs the jump package 4.18.2001.10 to be able to update to the latest platform version.</span></span>
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a><span data-ttu-id="80a38-389">Microsoft Defender Antivírus plataforma</span><span class="sxs-lookup"><span data-stu-id="80a38-389">Microsoft Defender Antivirus platform support</span></span>
<span data-ttu-id="80a38-390">As atualizações de plataforma e mecanismo são fornecidas em uma cadência mensal.</span><span class="sxs-lookup"><span data-stu-id="80a38-390">Platform and engine updates are provided on a monthly cadence.</span></span> <span data-ttu-id="80a38-391">Para ter suporte total, mantenha-se atualizado com as atualizações mais recentes da plataforma.</span><span class="sxs-lookup"><span data-stu-id="80a38-391">To be fully supported, keep current with the latest platform updates.</span></span> <span data-ttu-id="80a38-392">Nossa estrutura de suporte é dinâmica, evoluindo em duas fases, dependendo da disponibilidade da versão mais recente da plataforma:</span><span class="sxs-lookup"><span data-stu-id="80a38-392">Our support structure is dynamic, evolving into two phases depending on the availability of the latest platform version:</span></span>

- <span data-ttu-id="80a38-393">Fase de manutenção de Atualizações **Críticas** e Segurança - Ao executar a versão mais recente da plataforma, você estará qualificado para receber atualizações de segurança e críticas para a plataforma anti-malware.</span><span class="sxs-lookup"><span data-stu-id="80a38-393">**Security and Critical Updates servicing phase** - When running the latest platform version, you will be eligible to receive both Security and Critical updates to the anti-malware platform.</span></span>
 
- <span data-ttu-id="80a38-394">Fase de Suporte Técnico **(Somente)** - Depois que uma nova versão da plataforma for lançada, o suporte para versões mais antigas (N-2) será redução apenas para suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="80a38-394">**Technical Support (Only) phase** - After a new platform version is released, support for older versions (N-2) will reduce to technical support only.</span></span> <span data-ttu-id="80a38-395">As versões da plataforma anteriores ao N-2 não serão mais suportadas.\*</span><span class="sxs-lookup"><span data-stu-id="80a38-395">Platform versions older than N-2 will no longer be supported.\*</span></span>

<span data-ttu-id="80a38-396">\*O suporte técnico continuará a ser fornecido para atualizações da versão Windows 10 versão do Windows 10 (consulte Versão da plataforma incluída com Windows 10 [versões](#platform-version-included-with-windows-10-releases)) para a versão mais recente da plataforma.</span><span class="sxs-lookup"><span data-stu-id="80a38-396">\* Technical support will continue to be provided for upgrades from the Windows 10 release version (see [Platform version included with Windows 10 releases](#platform-version-included-with-windows-10-releases)) to the latest platform version.</span></span>

<span data-ttu-id="80a38-397">Durante a fase de suporte técnico (somente), incidentes de suporte comercialmente razoáveis serão fornecidos por meio do Serviço de Atendimento ao Cliente da Microsoft & Suporte e ofertas de suporte gerenciado da Microsoft (como o Suporte Premier).</span><span class="sxs-lookup"><span data-stu-id="80a38-397">During the technical support (only) phase, commercially reasonable support incidents will be provided through Microsoft Customer Service & Support and Microsoft’s managed support offerings (such as Premier Support).</span></span> <span data-ttu-id="80a38-398">Se um incidente de suporte exigir escalonamento para desenvolvimento para obter mais orientações, exigir uma atualização que não seja de segurança ou exigir uma atualização de segurança, os clientes serão solicitados a atualizar para a versão mais recente da plataforma ou uma atualização intermediária (\*).</span><span class="sxs-lookup"><span data-stu-id="80a38-398">If a support incident requires escalation to development for further guidance, requires a non-security update, or requires a security update, customers will be asked to upgrade to the latest platform version or an intermediate update (\*).</span></span>

### <a name="platform-version-included-with-windows-10-releases"></a><span data-ttu-id="80a38-399">Versão da plataforma incluída com Windows 10 versões</span><span class="sxs-lookup"><span data-stu-id="80a38-399">Platform version included with Windows 10 releases</span></span>
<span data-ttu-id="80a38-400">A tabela a seguir fornece as versões Microsoft Defender Antivírus plataforma e mecanismo que são enviadas com as versões Windows 10 versão mais recentes:</span><span class="sxs-lookup"><span data-stu-id="80a38-400">The below table provides the Microsoft Defender Antivirus platform and engine versions that are shipped with the latest Windows 10 releases:</span></span>    

|<span data-ttu-id="80a38-401">Windows 10 versão</span><span class="sxs-lookup"><span data-stu-id="80a38-401">Windows 10 release</span></span>  |<span data-ttu-id="80a38-402">Versão da plataforma</span><span class="sxs-lookup"><span data-stu-id="80a38-402">Platform version</span></span>  |<span data-ttu-id="80a38-403">Versão do mecanismo</span><span class="sxs-lookup"><span data-stu-id="80a38-403">Engine version</span></span> |<span data-ttu-id="80a38-404">Fase de suporte</span><span class="sxs-lookup"><span data-stu-id="80a38-404">Support phase</span></span> |
|:---|:---|:---|:---|
|<span data-ttu-id="80a38-405">2004 (20H1/20H2)</span><span class="sxs-lookup"><span data-stu-id="80a38-405">2004  (20H1/20H2)</span></span> |<span data-ttu-id="80a38-406">4.18.1909.6</span><span class="sxs-lookup"><span data-stu-id="80a38-406">4.18.1909.6</span></span> |<span data-ttu-id="80a38-407">1.1.17000.2</span><span class="sxs-lookup"><span data-stu-id="80a38-407">1.1.17000.2</span></span> | <span data-ttu-id="80a38-408">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="80a38-408">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="80a38-409">1909 (19H2)</span><span class="sxs-lookup"><span data-stu-id="80a38-409">1909  (19H2)</span></span> |<span data-ttu-id="80a38-410">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="80a38-410">4.18.1902.5</span></span> |<span data-ttu-id="80a38-411">1.1.16700.3</span><span class="sxs-lookup"><span data-stu-id="80a38-411">1.1.16700.3</span></span> | <span data-ttu-id="80a38-412">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="80a38-412">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="80a38-413">1903 (19H1)</span><span class="sxs-lookup"><span data-stu-id="80a38-413">1903  (19H1)</span></span> |<span data-ttu-id="80a38-414">4.18.1902.5</span><span class="sxs-lookup"><span data-stu-id="80a38-414">4.18.1902.5</span></span> |<span data-ttu-id="80a38-415">1.1.15600.4</span><span class="sxs-lookup"><span data-stu-id="80a38-415">1.1.15600.4</span></span> | <span data-ttu-id="80a38-416">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="80a38-416">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="80a38-417">1809 (RS5)</span><span class="sxs-lookup"><span data-stu-id="80a38-417">1809  (RS5)</span></span> |<span data-ttu-id="80a38-418">4.18.1807.18075</span><span class="sxs-lookup"><span data-stu-id="80a38-418">4.18.1807.18075</span></span> |<span data-ttu-id="80a38-419">1.1.15000.2</span><span class="sxs-lookup"><span data-stu-id="80a38-419">1.1.15000.2</span></span> | <span data-ttu-id="80a38-420">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="80a38-420">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="80a38-421">1803 (RS4)</span><span class="sxs-lookup"><span data-stu-id="80a38-421">1803  (RS4)</span></span> |<span data-ttu-id="80a38-422">4.13.17134.1</span><span class="sxs-lookup"><span data-stu-id="80a38-422">4.13.17134.1</span></span> |<span data-ttu-id="80a38-423">1.1.14600.4</span><span class="sxs-lookup"><span data-stu-id="80a38-423">1.1.14600.4</span></span> | <span data-ttu-id="80a38-424">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="80a38-424">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="80a38-425">1709 (RS3)</span><span class="sxs-lookup"><span data-stu-id="80a38-425">1709  (RS3)</span></span> |<span data-ttu-id="80a38-426">4.12.16299.15</span><span class="sxs-lookup"><span data-stu-id="80a38-426">4.12.16299.15</span></span> |<span data-ttu-id="80a38-427">1.1.14104.0</span><span class="sxs-lookup"><span data-stu-id="80a38-427">1.1.14104.0</span></span> | <span data-ttu-id="80a38-428">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="80a38-428">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="80a38-429">1703 (RS2)</span><span class="sxs-lookup"><span data-stu-id="80a38-429">1703  (RS2)</span></span> |<span data-ttu-id="80a38-430">4.11.15603.2</span><span class="sxs-lookup"><span data-stu-id="80a38-430">4.11.15603.2</span></span> |<span data-ttu-id="80a38-431">1.1.13504.0</span><span class="sxs-lookup"><span data-stu-id="80a38-431">1.1.13504.0</span></span> | <span data-ttu-id="80a38-432">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="80a38-432">Technical upgrade support (only)</span></span> |
|<span data-ttu-id="80a38-433">1607 (RS1)</span><span class="sxs-lookup"><span data-stu-id="80a38-433">1607 (RS1)</span></span> |<span data-ttu-id="80a38-434">4.10.14393.3683</span><span class="sxs-lookup"><span data-stu-id="80a38-434">4.10.14393.3683</span></span> |<span data-ttu-id="80a38-435">1.1.12805.0</span><span class="sxs-lookup"><span data-stu-id="80a38-435">1.1.12805.0</span></span> | <span data-ttu-id="80a38-436">Suporte técnico de atualização (somente)</span><span class="sxs-lookup"><span data-stu-id="80a38-436">Technical upgrade support (only)</span></span> |  

<span data-ttu-id="80a38-437">Para Windows 10 informações de versão, consulte a planilha Windows de fatos do ciclo [de vida.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)</span><span class="sxs-lookup"><span data-stu-id="80a38-437">For Windows 10 release information, see the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a><span data-ttu-id="80a38-438">Atualizações para Manutenção e Gerenciamento de Imagens de Implantação (DISM)</span><span class="sxs-lookup"><span data-stu-id="80a38-438">Updates for Deployment Image Servicing and Management (DISM)</span></span>

<span data-ttu-id="80a38-439">Recomendamos atualizar suas Windows 10 (Enterprise, Pro e edições Home), o Windows Server 2019 e Windows Server 2016 imagens de instalação do sistema operacional com as atualizações mais recentes de antivírus e antimalware.</span><span class="sxs-lookup"><span data-stu-id="80a38-439">We recommend updating your Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 OS installation images with the latest antivirus and antimalware updates.</span></span> <span data-ttu-id="80a38-440">Manter as imagens de instalação do sistema operacional atualizadas ajuda a evitar uma lacuna na proteção.</span><span class="sxs-lookup"><span data-stu-id="80a38-440">Keeping your OS installation images up to date helps avoid a gap in protection.</span></span> 

<span data-ttu-id="80a38-441">Para obter mais informações, consulte [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span><span class="sxs-lookup"><span data-stu-id="80a38-441">For more information, see [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).</span></span>

<details>
<summary><span data-ttu-id="80a38-442">1.1.2106.01</span><span class="sxs-lookup"><span data-stu-id="80a38-442">1.1.2106.01</span></span></summary>

<span data-ttu-id="80a38-443">&ensp;Versão do pacote: **1.1.2106.01**  </span><span class="sxs-lookup"><span data-stu-id="80a38-443">&ensp;Package version: **1.1.2106.01**  </span></span>  
<span data-ttu-id="80a38-444">&ensp;Versão da plataforma: **4.18.2104.14** </span><span class="sxs-lookup"><span data-stu-id="80a38-444">&ensp;Platform version: **4.18.2104.14** </span></span>  
<span data-ttu-id="80a38-445">&ensp;Versão do mecanismo: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="80a38-445">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="80a38-446">&ensp;Versão de assinatura: **1.339.1923.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-446">&ensp;Signature version: **1.339.1923.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="80a38-447">Correções</span><span class="sxs-lookup"><span data-stu-id="80a38-447">Fixes</span></span>
- <span data-ttu-id="80a38-448">Nenhum</span><span class="sxs-lookup"><span data-stu-id="80a38-448">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="80a38-449">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="80a38-449">Additional information</span></span>
- <span data-ttu-id="80a38-450">Nenhum</span><span class="sxs-lookup"><span data-stu-id="80a38-450">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="80a38-451">1.1.2105.01</span><span class="sxs-lookup"><span data-stu-id="80a38-451">1.1.2105.01</span></span></summary>

<span data-ttu-id="80a38-452">&ensp;Versão do pacote: **1.1.2105.01**  </span><span class="sxs-lookup"><span data-stu-id="80a38-452">&ensp;Package version: **1.1.2105.01**  </span></span>  
<span data-ttu-id="80a38-453">&ensp;Versão da plataforma: **4.18.2103.7** </span><span class="sxs-lookup"><span data-stu-id="80a38-453">&ensp;Platform version: **4.18.2103.7** </span></span>  
<span data-ttu-id="80a38-454">&ensp;Versão do mecanismo: **1.1.18100.6**</span><span class="sxs-lookup"><span data-stu-id="80a38-454">&ensp;Engine version: **1.1.18100.6**</span></span>  
<span data-ttu-id="80a38-455">&ensp;Versão de assinatura: **1.339.42.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-455">&ensp;Signature version: **1.339.42.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="80a38-456">Correções</span><span class="sxs-lookup"><span data-stu-id="80a38-456">Fixes</span></span>
- <span data-ttu-id="80a38-457">Nenhum</span><span class="sxs-lookup"><span data-stu-id="80a38-457">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="80a38-458">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="80a38-458">Additional information</span></span>
- <span data-ttu-id="80a38-459">Nenhum</span><span class="sxs-lookup"><span data-stu-id="80a38-459">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="80a38-460">1.1.2104.01</span><span class="sxs-lookup"><span data-stu-id="80a38-460">1.1.2104.01</span></span></summary>

<span data-ttu-id="80a38-461">&ensp;Versão do pacote: **1.1.2104.01**  </span><span class="sxs-lookup"><span data-stu-id="80a38-461">&ensp;Package version: **1.1.2104.01**  </span></span>  
<span data-ttu-id="80a38-462">&ensp;Versão da plataforma: **4.18.2102.4** </span><span class="sxs-lookup"><span data-stu-id="80a38-462">&ensp;Platform version: **4.18.2102.4** </span></span>  
<span data-ttu-id="80a38-463">&ensp;Versão do mecanismo: **1.1.18000.5**</span><span class="sxs-lookup"><span data-stu-id="80a38-463">&ensp;Engine version: **1.1.18000.5**</span></span>  
<span data-ttu-id="80a38-464">&ensp;Versão de assinatura: **1.335.232.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-464">&ensp;Signature version: **1.335.232.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="80a38-465">Correções</span><span class="sxs-lookup"><span data-stu-id="80a38-465">Fixes</span></span>
- <span data-ttu-id="80a38-466">Nenhum</span><span class="sxs-lookup"><span data-stu-id="80a38-466">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="80a38-467">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="80a38-467">Additional information</span></span>
- <span data-ttu-id="80a38-468">Nenhum</span><span class="sxs-lookup"><span data-stu-id="80a38-468">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="80a38-469">1.1.2103.01</span><span class="sxs-lookup"><span data-stu-id="80a38-469">1.1.2103.01</span></span></summary>

<span data-ttu-id="80a38-470">&ensp;Versão do pacote: **1.1.2103.01**  </span><span class="sxs-lookup"><span data-stu-id="80a38-470">&ensp;Package version: **1.1.2103.01**  </span></span>  
<span data-ttu-id="80a38-471">&ensp;Versão da plataforma: **4.18.2101.9** </span><span class="sxs-lookup"><span data-stu-id="80a38-471">&ensp;Platform version: **4.18.2101.9** </span></span>  
<span data-ttu-id="80a38-472">&ensp;Versão do mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="80a38-472">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="80a38-473">&ensp;Versão de assinatura: **1.331.2302.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-473">&ensp;Signature version: **1.331.2302.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="80a38-474">Correções</span><span class="sxs-lookup"><span data-stu-id="80a38-474">Fixes</span></span>
- <span data-ttu-id="80a38-475">Nenhum</span><span class="sxs-lookup"><span data-stu-id="80a38-475">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="80a38-476">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="80a38-476">Additional information</span></span>
- <span data-ttu-id="80a38-477">Nenhum</span><span class="sxs-lookup"><span data-stu-id="80a38-477">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="80a38-478">1.1.2102.03</span><span class="sxs-lookup"><span data-stu-id="80a38-478">1.1.2102.03</span></span></summary>

<span data-ttu-id="80a38-479">&ensp;Versão do pacote: **1.1.2102.03**  </span><span class="sxs-lookup"><span data-stu-id="80a38-479">&ensp;Package version: **1.1.2102.03**  </span></span>  
<span data-ttu-id="80a38-480">&ensp;Versão da plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="80a38-480">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="80a38-481">&ensp;Versão do mecanismo: **1.1.17800.5**</span><span class="sxs-lookup"><span data-stu-id="80a38-481">&ensp;Engine version: **1.1.17800.5**</span></span>  
<span data-ttu-id="80a38-482">&ensp;Versão de assinatura: **1.331.174.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-482">&ensp;Signature version: **1.331.174.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="80a38-483">Correções</span><span class="sxs-lookup"><span data-stu-id="80a38-483">Fixes</span></span>
- <span data-ttu-id="80a38-484">Nenhum</span><span class="sxs-lookup"><span data-stu-id="80a38-484">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="80a38-485">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="80a38-485">Additional information</span></span>
- <span data-ttu-id="80a38-486">Nenhum</span><span class="sxs-lookup"><span data-stu-id="80a38-486">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="80a38-487">1.1.2101.02</span><span class="sxs-lookup"><span data-stu-id="80a38-487">1.1.2101.02</span></span></summary>

<span data-ttu-id="80a38-488">&ensp;Versão do pacote: **1.1.2101.02**  </span><span class="sxs-lookup"><span data-stu-id="80a38-488">&ensp;Package version: **1.1.2101.02**  </span></span>  
<span data-ttu-id="80a38-489">&ensp;Versão da plataforma: **4.18.2011.6** </span><span class="sxs-lookup"><span data-stu-id="80a38-489">&ensp;Platform version: **4.18.2011.6** </span></span>  
<span data-ttu-id="80a38-490">&ensp;Versão do mecanismo: **1.1.17700.4**</span><span class="sxs-lookup"><span data-stu-id="80a38-490">&ensp;Engine version: **1.1.17700.4**</span></span>  
<span data-ttu-id="80a38-491">&ensp;Versão de assinatura: **1.329.1796.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-491">&ensp;Signature version: **1.329.1796.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="80a38-492">Correções</span><span class="sxs-lookup"><span data-stu-id="80a38-492">Fixes</span></span>
- <span data-ttu-id="80a38-493">Nenhum</span><span class="sxs-lookup"><span data-stu-id="80a38-493">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="80a38-494">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="80a38-494">Additional information</span></span>
- <span data-ttu-id="80a38-495">Nenhum</span><span class="sxs-lookup"><span data-stu-id="80a38-495">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="80a38-496">1.1.2012.01</span><span class="sxs-lookup"><span data-stu-id="80a38-496">1.1.2012.01</span></span></summary>

<span data-ttu-id="80a38-497">&ensp;Versão do pacote: **1.1.2012.01**  </span><span class="sxs-lookup"><span data-stu-id="80a38-497">&ensp;Package version: **1.1.2012.01**  </span></span>  
<span data-ttu-id="80a38-498">&ensp;Versão da plataforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="80a38-498">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="80a38-499">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="80a38-499">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="80a38-500">&ensp;Versão de assinatura: **1.327.1991.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-500">&ensp;Signature version: **1.327.1991.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="80a38-501">Correções</span><span class="sxs-lookup"><span data-stu-id="80a38-501">Fixes</span></span>
- <span data-ttu-id="80a38-502">Nenhum</span><span class="sxs-lookup"><span data-stu-id="80a38-502">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="80a38-503">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="80a38-503">Additional information</span></span>
- <span data-ttu-id="80a38-504">Nenhum</span><span class="sxs-lookup"><span data-stu-id="80a38-504">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="80a38-505">1.1.2011.02</span><span class="sxs-lookup"><span data-stu-id="80a38-505">1.1.2011.02</span></span></summary>

<span data-ttu-id="80a38-506">&ensp;Versão do pacote: **1.1.2011.02**  </span><span class="sxs-lookup"><span data-stu-id="80a38-506">&ensp;Package version: **1.1.2011.02**  </span></span>  
<span data-ttu-id="80a38-507">&ensp;Versão da plataforma: **4.18.2010.7** </span><span class="sxs-lookup"><span data-stu-id="80a38-507">&ensp;Platform version: **4.18.2010.7** </span></span>  
<span data-ttu-id="80a38-508">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="80a38-508">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="80a38-509">&ensp;Versão de assinatura: **1.327.658.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-509">&ensp;Signature version: **1.327.658.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="80a38-510">Correções</span><span class="sxs-lookup"><span data-stu-id="80a38-510">Fixes</span></span>
- <span data-ttu-id="80a38-511">Nenhum</span><span class="sxs-lookup"><span data-stu-id="80a38-511">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="80a38-512">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="80a38-512">Additional information</span></span>
- <span data-ttu-id="80a38-513">Assinaturas Microsoft Defender Antivírus atualizadas</span><span class="sxs-lookup"><span data-stu-id="80a38-513">Refreshed Microsoft Defender Antivirus signatures</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="80a38-514">1.1.2011.01</span><span class="sxs-lookup"><span data-stu-id="80a38-514">1.1.2011.01</span></span></summary>

<span data-ttu-id="80a38-515">&ensp;Versão do pacote: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="80a38-515">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="80a38-516">&ensp;Versão da plataforma: **4.18.2009.7**</span><span class="sxs-lookup"><span data-stu-id="80a38-516">&ensp;Platform version: **4.18.2009.7**</span></span>  
<span data-ttu-id="80a38-517">&ensp;Versão do mecanismo: **1.1.17600.5**</span><span class="sxs-lookup"><span data-stu-id="80a38-517">&ensp;Engine version: **1.1.17600.5**</span></span>  
<span data-ttu-id="80a38-518">&ensp;Versão de assinatura: **1.327.344.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-518">&ensp;Signature version: **1.327.344.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="80a38-519">Correções</span><span class="sxs-lookup"><span data-stu-id="80a38-519">Fixes</span></span>
- <span data-ttu-id="80a38-520">Nenhum</span><span class="sxs-lookup"><span data-stu-id="80a38-520">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="80a38-521">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="80a38-521">Additional information</span></span>
- <span data-ttu-id="80a38-522">Nenhum</span><span class="sxs-lookup"><span data-stu-id="80a38-522">None</span></span>  
<br/>
</details><details>
<summary><span data-ttu-id="80a38-523">1.1.2009.10</span><span class="sxs-lookup"><span data-stu-id="80a38-523">1.1.2009.10</span></span></summary>

<span data-ttu-id="80a38-524">&ensp;Versão do pacote: **1.1.2011.01**  </span><span class="sxs-lookup"><span data-stu-id="80a38-524">&ensp;Package version: **1.1.2011.01**  </span></span>  
<span data-ttu-id="80a38-525">&ensp;Versão da plataforma: **4.18.2008.9** </span><span class="sxs-lookup"><span data-stu-id="80a38-525">&ensp;Platform version: **4.18.2008.9** </span></span>  
<span data-ttu-id="80a38-526">&ensp;Versão do mecanismo: **1.1.17400.5**</span><span class="sxs-lookup"><span data-stu-id="80a38-526">&ensp;Engine version: **1.1.17400.5**</span></span>  
<span data-ttu-id="80a38-527">&ensp;Versão de assinatura: **1.327.2216.0**</span><span class="sxs-lookup"><span data-stu-id="80a38-527">&ensp;Signature version: **1.327.2216.0**</span></span>    
    
### <a name="fixes"></a><span data-ttu-id="80a38-528">Correções</span><span class="sxs-lookup"><span data-stu-id="80a38-528">Fixes</span></span>
- <span data-ttu-id="80a38-529">Nenhum</span><span class="sxs-lookup"><span data-stu-id="80a38-529">None</span></span>

### <a name="additional-information"></a><span data-ttu-id="80a38-530">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="80a38-530">Additional information</span></span>
- <span data-ttu-id="80a38-531">Adicionado suporte para Windows 10 RS1 ou imagens de instalação posteriores do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="80a38-531">Added support for Windows 10 RS1 or later OS install images.</span></span>  
<br/>
</details>

## <a name="additional-resources"></a><span data-ttu-id="80a38-532">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="80a38-532">Additional resources</span></span>

| <span data-ttu-id="80a38-533">Artigo</span><span class="sxs-lookup"><span data-stu-id="80a38-533">Article</span></span> | <span data-ttu-id="80a38-534">Descrição</span><span class="sxs-lookup"><span data-stu-id="80a38-534">Description</span></span>  |
|:---|:---|
|[<span data-ttu-id="80a38-535">Atualização do Microsoft Defender para Windows de instalação do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="80a38-535">Microsoft Defender update for Windows operating system installation images</span></span>](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | <span data-ttu-id="80a38-536">Revise os pacotes de atualização antimalware para as imagens de instalação do sistema operacional (arquivos WIM e VHD).</span><span class="sxs-lookup"><span data-stu-id="80a38-536">Review antimalware update packages for your OS installation images (WIM and VHD files).</span></span> <span data-ttu-id="80a38-537">Obter Microsoft Defender Antivírus atualizações para Windows 10 (Enterprise, Pro e edições Home), Windows Server 2019 e Windows Server 2016 de instalação.</span><span class="sxs-lookup"><span data-stu-id="80a38-537">Get Microsoft Defender Antivirus updates for Windows 10 (Enterprise, Pro, and Home editions), Windows Server 2019, and Windows Server 2016 installation images.</span></span>  |
|[<span data-ttu-id="80a38-538">Gerenciar como as atualizações de proteção são baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="80a38-538">Manage how protection updates are downloaded and applied</span></span>](manage-protection-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="80a38-539">As atualizações de proteção podem ser entregues por meio de várias fontes.</span><span class="sxs-lookup"><span data-stu-id="80a38-539">Protection updates can be delivered through many sources.</span></span> |
|[<span data-ttu-id="80a38-540">Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas</span><span class="sxs-lookup"><span data-stu-id="80a38-540">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md) | <span data-ttu-id="80a38-541">Você pode agendar quando as atualizações de proteção devem ser baixadas.</span><span class="sxs-lookup"><span data-stu-id="80a38-541">You can schedule when protection updates should be downloaded.</span></span> |
|[<span data-ttu-id="80a38-542">Gerenciar atualizações para pontos de extremidade que estão des date</span><span class="sxs-lookup"><span data-stu-id="80a38-542">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md) | <span data-ttu-id="80a38-543">Se um ponto de extremidade perder uma atualização ou uma verificação agendada, você poderá forçar uma atualização ou verificar na próxima vez que um usuário entrar.</span><span class="sxs-lookup"><span data-stu-id="80a38-543">If an endpoint misses an update or scheduled scan, you can force an update or scan the next time a user signs in.</span></span> |
|[<span data-ttu-id="80a38-544">Gerenciar atualizações aplicadas com base em evento</span><span class="sxs-lookup"><span data-stu-id="80a38-544">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md) | <span data-ttu-id="80a38-545">Você pode definir atualizações de proteção a serem baixadas na inicialização ou após determinados eventos de proteção entregues na nuvem.</span><span class="sxs-lookup"><span data-stu-id="80a38-545">You can set protection updates to be downloaded at startup or after certain cloud-delivered protection events.</span></span> |
|[<span data-ttu-id="80a38-546">Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)</span><span class="sxs-lookup"><span data-stu-id="80a38-546">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| <span data-ttu-id="80a38-547">Você pode especificar configurações, como se as atualizações devem ocorrer na energia da bateria, que são especialmente úteis para dispositivos móveis e máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="80a38-547">You can specify settings, such as whether updates should occur on battery power, that are especially useful for mobile devices and virtual machines.</span></span> |
