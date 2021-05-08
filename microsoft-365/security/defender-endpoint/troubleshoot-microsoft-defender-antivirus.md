---
title: IDs de evento do Microsoft Defender AV e códigos de erro
description: Procure as causas e soluções para Microsoft Defender Antivírus IDs e erros de evento
keywords: event, error code, siem, logging, troubleshooting, wef, windows event forwarding
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: cd222760f3a5cc005c679bf28365237cc70e8950
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275343"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a><span data-ttu-id="f4b38-104">Revise logs de eventos e códigos de erro para solucionar problemas com o Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="f4b38-104">Review event logs and error codes to troubleshoot issues with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f4b38-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f4b38-105">**Applies to:**</span></span>

- [<span data-ttu-id="f4b38-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f4b38-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f4b38-107">Se você encontrar um problema com Microsoft Defender Antivírus, poderá pesquisar as tabelas neste tópico para encontrar um problema correspondente e uma solução em potencial.</span><span class="sxs-lookup"><span data-stu-id="f4b38-107">If you encounter a problem with Microsoft Defender Antivirus, you can search the tables in this topic to find a matching issue and potential solution.</span></span>

<span data-ttu-id="f4b38-108">A lista de tabelas:</span><span class="sxs-lookup"><span data-stu-id="f4b38-108">The tables list:</span></span>

- <span data-ttu-id="f4b38-109">[Microsoft Defender Antivírus IDs de evento](#windows-defender-av-ids) (elas se aplicam a Windows 10 e Windows Server 2016)</span><span class="sxs-lookup"><span data-stu-id="f4b38-109">[Microsoft Defender Antivirus event IDs](#windows-defender-av-ids) (these apply to both Windows 10 and Windows Server 2016)</span></span>
- [<span data-ttu-id="f4b38-110">Microsoft Defender Antivírus de erro do cliente</span><span class="sxs-lookup"><span data-stu-id="f4b38-110">Microsoft Defender Antivirus client error codes</span></span>](#error-codes)
- [<span data-ttu-id="f4b38-111">Códigos de Microsoft Defender Antivírus de erro do cliente internos (usados pela Microsoft durante o desenvolvimento e teste)</span><span class="sxs-lookup"><span data-stu-id="f4b38-111">Internal Microsoft Defender Antivirus client error codes (used by Microsoft during development and testing)</span></span>](#internal-error-codes)

> [!TIP]
> <span data-ttu-id="f4b38-112">Você também pode visitar o site de demonstração do Microsoft Defender para Ponto de Extremidade [no demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que os seguintes recursos estão funcionando:</span><span class="sxs-lookup"><span data-stu-id="f4b38-112">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working:</span></span>
> 
> - <span data-ttu-id="f4b38-113">Proteção fornecida na nuvem</span><span class="sxs-lookup"><span data-stu-id="f4b38-113">Cloud-delivered protection</span></span>
> - <span data-ttu-id="f4b38-114">Aprendizado rápido (incluindo Bloquear à primeira vista)</span><span class="sxs-lookup"><span data-stu-id="f4b38-114">Fast learning (including Block at first sight)</span></span>
> - <span data-ttu-id="f4b38-115">Bloqueio de aplicativo potencialmente indesejado</span><span class="sxs-lookup"><span data-stu-id="f4b38-115">Potentially unwanted application blocking</span></span>

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a><span data-ttu-id="f4b38-116">Microsoft Defender Antivírus IDs de evento</span><span class="sxs-lookup"><span data-stu-id="f4b38-116">Microsoft Defender Antivirus event IDs</span></span>

<span data-ttu-id="f4b38-117">Microsoft Defender Antivírus registra IDs de evento no log Windows evento.</span><span class="sxs-lookup"><span data-stu-id="f4b38-117">Microsoft Defender Antivirus records event IDs in the Windows event log.</span></span>

<span data-ttu-id="f4b38-118">Você pode exibir diretamente o log de eventos ou se tiver uma ferramenta siem (gerenciamento de eventos) e informações de segurança de terceiros Microsoft Defender Antivírus, também poderá consumir as [IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) de evento do cliente para analisar eventos e erros específicos dos pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="f4b38-118">You can directly view the event log, or if you have a third-party security information and event management (SIEM) tool, you can also consume [Microsoft Defender Antivirus client event IDs](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) to review specific events and errors from your endpoints.</span></span>

<span data-ttu-id="f4b38-119">A tabela nesta seção lista as IDs Microsoft Defender Antivírus eventos principais e, quando possível, fornece soluções sugeridas para corrigir ou resolver o erro.</span><span class="sxs-lookup"><span data-stu-id="f4b38-119">The table in this section lists the main Microsoft Defender Antivirus event IDs and, where possible, provides suggested solutions to fix or resolve the error.</span></span> 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a><span data-ttu-id="f4b38-120">Para exibir um Microsoft Defender Antivírus evento</span><span class="sxs-lookup"><span data-stu-id="f4b38-120">To view a Microsoft Defender Antivirus event</span></span>

1.  <span data-ttu-id="f4b38-121">Abra **o Visualizador de Eventos**.</span><span class="sxs-lookup"><span data-stu-id="f4b38-121">Open **Event Viewer**.</span></span>
2.  <span data-ttu-id="f4b38-122">Na árvore de console, expanda **Logs de** Aplicativos e Serviços , em seguida, **Microsoft**, **Windows**, em seguida, **Windows Defender**.</span><span class="sxs-lookup"><span data-stu-id="f4b38-122">In the console tree, expand **Applications and Services Logs**, then **Microsoft**, then **Windows**, then **Windows Defender**.</span></span>
3.  <span data-ttu-id="f4b38-123">Clique duas vezes em **Operacional**.</span><span class="sxs-lookup"><span data-stu-id="f4b38-123">Double-click on **Operational**.</span></span>
4.  <span data-ttu-id="f4b38-124">No painel de detalhes, veja a lista de eventos individuais para encontrar seu evento.</span><span class="sxs-lookup"><span data-stu-id="f4b38-124">In the details pane, view the list of individual events to find your event.</span></span>
5.  <span data-ttu-id="f4b38-125">Clique no evento para ver detalhes específicos sobre um evento no painel inferior, nas guias **Geral** **e Detalhes.**</span><span class="sxs-lookup"><span data-stu-id="f4b38-125">Click the event to see specific details about an event in the lower pane, under the **General** and **Details** tabs.</span></span>

<table> 
<tr>
<th colspan="2" ><span data-ttu-id="f4b38-126">ID do Evento: 1000</span><span class="sxs-lookup"><span data-stu-id="f4b38-126">Event ID: 1000</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-127">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-127">Symbolic name:</span></span>
</td>
<td><span data-ttu-id="f4b38-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-128">
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-129">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-129">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-130">
<b>Uma verificação antimalware foi iniciada. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-130">
<b>An antimalware scan started. </b>
</span></span></td>
</tr>
<tr>
<td >
<span data-ttu-id="f4b38-131">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-131">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="f4b38-132">
<dt>ID de verificação: &lt; Número de ID da &gt; verificação relevante.</dt> 
<dt> Tipo de verificação: &lt; Tipo de verificação , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-132">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-133">Antivírus</span><span class="sxs-lookup"><span data-stu-id="f4b38-133">Antivirus</span></span></li>
<li><span data-ttu-id="f4b38-134">Antispyware</span><span class="sxs-lookup"><span data-stu-id="f4b38-134">Antispyware</span></span></li>
<li><span data-ttu-id="f4b38-135">Antimalware</span><span class="sxs-lookup"><span data-stu-id="f4b38-135">Antimalware</span></span></li>
</ul><span data-ttu-id="f4b38-136">
</dt>
<dt>Parâmetros de verificação: &lt; Parâmetros de &gt; verificação, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-136">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-137">Verificação completa</span><span class="sxs-lookup"><span data-stu-id="f4b38-137">Full scan</span></span></li>
<li><span data-ttu-id="f4b38-138">Verificação rápida</span><span class="sxs-lookup"><span data-stu-id="f4b38-138">Quick scan</span></span></li>
<li><span data-ttu-id="f4b38-139">Verificação do cliente</span><span class="sxs-lookup"><span data-stu-id="f4b38-139">Customer scan</span></span></li>
</ul><span data-ttu-id="f4b38-140">
</dt>
<dt>Recursos de verificação: &lt; Recursos (como arquivos/diretórios/BHO) que foram &gt; verificados.</dt> 
<dt>Usuário: &lt; Domínio &gt; \& lt; Usuário &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-140">
</dt>
<dt>Scan Resources: &lt;Resources (such as files/directories/BHO) that were scanned.&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-141">ID do Evento: 1001</span><span class="sxs-lookup"><span data-stu-id="f4b38-141">Event ID: 1001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-142">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-142">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-143">
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-144">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-144">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-145">
<b>Uma verificação antimalware concluída.</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-145">
<b>An antimalware scan finished.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-146">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-146">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="f4b38-147">
<dt>ID de verificação: &lt; Número de ID da &gt; verificação relevante.</dt> 
<dt> Tipo de verificação: &lt; Tipo de verificação , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-147">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-148">Antivírus</span><span class="sxs-lookup"><span data-stu-id="f4b38-148">Antivirus</span></span></li>
<li><span data-ttu-id="f4b38-149">Antispyware</span><span class="sxs-lookup"><span data-stu-id="f4b38-149">Antispyware</span></span></li>
<li><span data-ttu-id="f4b38-150">Antimalware</span><span class="sxs-lookup"><span data-stu-id="f4b38-150">Antimalware</span></span></li>
</ul><span data-ttu-id="f4b38-151">
</dt>
<dt>Parâmetros de verificação: &lt; Parâmetros de &gt; verificação, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-151">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-152">Verificação completa</span><span class="sxs-lookup"><span data-stu-id="f4b38-152">Full scan</span></span></li>
<li><span data-ttu-id="f4b38-153">Verificação rápida</span><span class="sxs-lookup"><span data-stu-id="f4b38-153">Quick scan</span></span></li>
<li><span data-ttu-id="f4b38-154">Verificação do cliente</span><span class="sxs-lookup"><span data-stu-id="f4b38-154">Customer scan</span></span></li>
</ul><span data-ttu-id="f4b38-155">
</dt>
<dt>Usuário: &lt; Domínio &gt; \& lt; Tempo &gt; </dt>
<dt>de verificação do usuário: a &lt; duração de uma verificação. &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-155">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-156">ID do Evento: 1002</span><span class="sxs-lookup"><span data-stu-id="f4b38-156">Event ID: 1002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-157">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-157">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-158">
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-159">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-159">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-160">
<b>Uma verificação antimalware foi interrompida antes de ser concluída. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-160">
<b>An antimalware scan was stopped before it finished. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-161">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-161">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="f4b38-162">
<dt>ID de verificação: &lt; Número de ID da &gt; verificação relevante.</dt> 
<dt> Tipo de verificação: &lt; Tipo de verificação , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-162">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-163">Antivírus</span><span class="sxs-lookup"><span data-stu-id="f4b38-163">Antivirus</span></span></li>
<li><span data-ttu-id="f4b38-164">Antispyware</span><span class="sxs-lookup"><span data-stu-id="f4b38-164">Antispyware</span></span></li>
<li><span data-ttu-id="f4b38-165">Antimalware</span><span class="sxs-lookup"><span data-stu-id="f4b38-165">Antimalware</span></span></li>
</ul><span data-ttu-id="f4b38-166">
</dt>
<dt>Parâmetros de verificação: &lt; Parâmetros de &gt; verificação, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-166">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-167">Verificação completa</span><span class="sxs-lookup"><span data-stu-id="f4b38-167">Full scan</span></span></li>
<li><span data-ttu-id="f4b38-168">Verificação rápida</span><span class="sxs-lookup"><span data-stu-id="f4b38-168">Quick scan</span></span></li>
<li><span data-ttu-id="f4b38-169">Verificação do cliente</span><span class="sxs-lookup"><span data-stu-id="f4b38-169">Customer scan</span></span></li>
</ul><span data-ttu-id="f4b38-170">
</dt>
<dt>Usuário: &lt; Domínio &gt; &amp; lt; Tempo &gt; </dt>
<dt>de verificação do usuário: a &lt; duração de uma verificação. &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-170">
</dt>
<dt>User: &lt;Domain&gt;&amp;lt;User&gt;</dt>
<dt>Scan Time: &lt;The duration of a scan.&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-171">ID do Evento: 1003</span><span class="sxs-lookup"><span data-stu-id="f4b38-171">Event ID: 1003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-172">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-172">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-173">
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-174">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-174">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-175">
<b>Uma verificação antimalware foi pausada. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-175">
<b>An antimalware scan was paused. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-176">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-176">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="f4b38-177">
<dt>ID de verificação: &lt; Número de ID da &gt; verificação relevante.</dt> 
<dt> Tipo de verificação: &lt; Tipo de verificação , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-177">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-178">Antivírus</span><span class="sxs-lookup"><span data-stu-id="f4b38-178">Antivirus</span></span></li>
<li><span data-ttu-id="f4b38-179">Antispyware</span><span class="sxs-lookup"><span data-stu-id="f4b38-179">Antispyware</span></span></li>
<li><span data-ttu-id="f4b38-180">Antimalware</span><span class="sxs-lookup"><span data-stu-id="f4b38-180">Antimalware</span></span></li>
</ul><span data-ttu-id="f4b38-181">
</dt>
<dt>Parâmetros de verificação: &lt; Parâmetros de &gt; verificação, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-181">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-182">Verificação completa</span><span class="sxs-lookup"><span data-stu-id="f4b38-182">Full scan</span></span></li>
<li><span data-ttu-id="f4b38-183">Verificação rápida</span><span class="sxs-lookup"><span data-stu-id="f4b38-183">Quick scan</span></span></li>
<li><span data-ttu-id="f4b38-184">Verificação do cliente</span><span class="sxs-lookup"><span data-stu-id="f4b38-184">Customer scan</span></span></li>
</ul><span data-ttu-id="f4b38-185">
</dt>
<dt>Usuário: &lt; Domínio &gt; \& lt; Usuário&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-185">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-186">ID do Evento: 1004</span><span class="sxs-lookup"><span data-stu-id="f4b38-186">Event ID: 1004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-187">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-187">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-188">
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-189">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-189">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-190">
<b>Uma verificação antimalware foi retomada. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-190">
<b>An antimalware scan was resumed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-191">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-191">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="f4b38-192">
<dt>ID de verificação: &lt; Número de ID da &gt; verificação relevante.</dt> 
<dt> Tipo de verificação: &lt; Tipo de verificação , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-192">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-193">Antivírus</span><span class="sxs-lookup"><span data-stu-id="f4b38-193">Antivirus</span></span></li>
<li><span data-ttu-id="f4b38-194">Antispyware</span><span class="sxs-lookup"><span data-stu-id="f4b38-194">Antispyware</span></span></li>
<li><span data-ttu-id="f4b38-195">Antimalware</span><span class="sxs-lookup"><span data-stu-id="f4b38-195">Antimalware</span></span></li>
</ul><span data-ttu-id="f4b38-196">
</dt>
<dt>Parâmetros de verificação: &lt; Parâmetros de &gt; verificação, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-196">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-197">Verificação completa</span><span class="sxs-lookup"><span data-stu-id="f4b38-197">Full scan</span></span></li>
<li><span data-ttu-id="f4b38-198">Verificação rápida</span><span class="sxs-lookup"><span data-stu-id="f4b38-198">Quick scan</span></span></li>
<li><span data-ttu-id="f4b38-199">Verificação do cliente</span><span class="sxs-lookup"><span data-stu-id="f4b38-199">Customer scan</span></span></li>
</ul><span data-ttu-id="f4b38-200">
</dt>
<dt>Usuário: &lt; Domínio &gt; \& lt; Usuário&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-200">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-201">ID do Evento: 1005</span><span class="sxs-lookup"><span data-stu-id="f4b38-201">Event ID: 1005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-202">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-202">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-203">
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-204">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-204">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-205">
<b>Falha na verificação de antimalware. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-205">
<b>An antimalware scan failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-206">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-206">Description:</span></span>
</td>
<td >
<dl><span data-ttu-id="f4b38-207">
<dt>ID de verificação: &lt; Número de ID da &gt; verificação relevante.</dt> 
<dt> Tipo de verificação: &lt; Tipo de verificação , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-207">
<dt>Scan ID: &lt;ID number of the relevant scan.&gt;</dt>
<dt>Scan Type: &lt;Scan type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-208">Antivírus</span><span class="sxs-lookup"><span data-stu-id="f4b38-208">Antivirus</span></span></li>
<li><span data-ttu-id="f4b38-209">Antispyware</span><span class="sxs-lookup"><span data-stu-id="f4b38-209">Antispyware</span></span></li>
<li><span data-ttu-id="f4b38-210">Antimalware</span><span class="sxs-lookup"><span data-stu-id="f4b38-210">Antimalware</span></span></li>
</ul><span data-ttu-id="f4b38-211">
</dt>
<dt>Parâmetros de verificação: &lt; Parâmetros de &gt; verificação, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-211">
</dt>
<dt>Scan Parameters: &lt;Scan parameters&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-212">Verificação completa</span><span class="sxs-lookup"><span data-stu-id="f4b38-212">Full scan</span></span></li>
<li><span data-ttu-id="f4b38-213">Verificação rápida</span><span class="sxs-lookup"><span data-stu-id="f4b38-213">Quick scan</span></span></li>
<li><span data-ttu-id="f4b38-214">Verificação do cliente</span><span class="sxs-lookup"><span data-stu-id="f4b38-214">Customer scan</span></span></li>
</ul><span data-ttu-id="f4b38-215">
</dt>
<dt>Usuário: &lt; Domínio &gt; \& lt; Código &gt; </dt>
<dt>de Erro do Usuário: Código de erro &lt; Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-215">
</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-216">Ação do usuário:</span><span class="sxs-lookup"><span data-stu-id="f4b38-216">User action:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-217">O cliente antivírus encontrou um erro e a verificação atual parou.</span><span class="sxs-lookup"><span data-stu-id="f4b38-217">The antivirus client encountered an error, and the current scan has stopped.</span></span> <span data-ttu-id="f4b38-218">A verificação pode falhar devido a um problema do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="f4b38-218">The scan might fail due to a client-side issue.</span></span> <span data-ttu-id="f4b38-219">Esse registro de evento inclui a ID de verificação, o tipo de verificação (Microsoft Defender Antivírus, antispyware, antimalware), parâmetros de verificação, o usuário que iniciou a verificação, o código de erro e uma descrição do erro.</span><span class="sxs-lookup"><span data-stu-id="f4b38-219">This event record includes the scan ID, type of scan (Microsoft Defender Antivirus, antispyware, antimalware), scan parameters, the user that started the scan, the error code, and a description of the error.</span></span>
<span data-ttu-id="f4b38-220">Para solucionar problemas deste evento:</span><span class="sxs-lookup"><span data-stu-id="f4b38-220">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="f4b38-221">Execute a verificação novamente.</span><span class="sxs-lookup"><span data-stu-id="f4b38-221">Run the scan again.</span></span></li>
<li><span data-ttu-id="f4b38-222">Se ele falhar da mesma forma, vá para o site <b></b> de Suporte da <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, insira o número de erro na caixa Pesquisar para procurar o código de erro.</span><span class="sxs-lookup"><span data-stu-id="f4b38-222">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="f4b38-223">Entre em contato com o <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Suporte Técnico da Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="f4b38-223">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-224">ID do Evento: 1006</span><span class="sxs-lookup"><span data-stu-id="f4b38-224">Event ID: 1006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-225">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-225">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-226">
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-227">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-227">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-228">
<b>O mecanismo antimalware encontrou malware ou outro software potencialmente indesejado. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-228">
<b>The antimalware engine found malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-229">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-229">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-230">Para obter mais informações, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f4b38-230">For more information, see the following:</span></span>
<dl><span data-ttu-id="f4b38-231">
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-231">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-232">Baixo</span><span class="sxs-lookup"><span data-stu-id="f4b38-232">Low</span></span></li>
<li><span data-ttu-id="f4b38-233">Moderado</span><span class="sxs-lookup"><span data-stu-id="f4b38-233">Moderate</span></span></li>
<li><span data-ttu-id="f4b38-234">Alto</span><span class="sxs-lookup"><span data-stu-id="f4b38-234">High</span></span></li>
<li><span data-ttu-id="f4b38-235">Grave</span><span class="sxs-lookup"><span data-stu-id="f4b38-235">Severe</span></span></li>
</ul><span data-ttu-id="f4b38-236">
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Origem &gt; da</dt>detecção do caminho 
<dt> do arquivo: &lt; &gt; origem da detecção, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-236">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-237">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="f4b38-237">Unknown</span></span></li>
<li><span data-ttu-id="f4b38-238">Computador local</span><span class="sxs-lookup"><span data-stu-id="f4b38-238">Local computer</span></span></li>
<li><span data-ttu-id="f4b38-239">Compartilhamento de rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-239">Network share</span></span></li>
<li><span data-ttu-id="f4b38-240">Internet</span><span class="sxs-lookup"><span data-stu-id="f4b38-240">Internet</span></span></li>
<li><span data-ttu-id="f4b38-241">Tráfego de entrada</span><span class="sxs-lookup"><span data-stu-id="f4b38-241">Incoming traffic</span></span></li>
<li><span data-ttu-id="f4b38-242">Tráfego de saída</span><span class="sxs-lookup"><span data-stu-id="f4b38-242">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="f4b38-243">
</dt>
<dt>Tipo de detecção: &lt; Tipo de detecção , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-243">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-244">Heurística</span><span class="sxs-lookup"><span data-stu-id="f4b38-244">Heuristics</span></span></li>
<li><span data-ttu-id="f4b38-245">Generic</span><span class="sxs-lookup"><span data-stu-id="f4b38-245">Generic</span></span></li>
<li><span data-ttu-id="f4b38-246">Concreto</span><span class="sxs-lookup"><span data-stu-id="f4b38-246">Concrete</span></span></li>
<li><span data-ttu-id="f4b38-247">Assinatura dinâmica</span><span class="sxs-lookup"><span data-stu-id="f4b38-247">Dynamic signature</span></span></li>
</ul><span data-ttu-id="f4b38-248">
</dt>
<dt>Fonte de detecção: &lt; Fonte de detecção por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-248">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="f4b38-249">Usuário: iniciado pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f4b38-249">User: user initiated</span></span></li>
<li><span data-ttu-id="f4b38-250">Sistema: iniciado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="f4b38-250">System: system initiated</span></span></li>
<li><span data-ttu-id="f4b38-251">Em tempo real: componente em tempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="f4b38-251">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="f4b38-252">IOAV: IE Downloads e Outlook Express Attachments iniciados</span><span class="sxs-lookup"><span data-stu-id="f4b38-252">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="f4b38-253">NIS: Sistema de inspeção de rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-253">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="f4b38-254">IEPROTECT: IE - IExtensionValidation; isso protege contra controles de página da Web mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="f4b38-254">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="f4b38-255">Antimalware de início antecipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="f4b38-255">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="f4b38-256">Isso inclui malware detectado pela sequência de inicialização</span><span class="sxs-lookup"><span data-stu-id="f4b38-256">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="f4b38-257">Atestado remoto</span><span class="sxs-lookup"><span data-stu-id="f4b38-257">Remote attestation</span></span></li>
</ul><span data-ttu-id="f4b38-258">Interface de verificação antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="f4b38-258">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="f4b38-259">Usado principalmente para proteger scripts (PS, VBS), embora também possa ser invocado por terceiros.</span><span class="sxs-lookup"><span data-stu-id="f4b38-259">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="f4b38-260">Status do </dt> 
<dt>UAC: Usuário &lt; de &gt; Status:</dt>Domínio
<dt> &lt; &gt; \& lt; Nome &gt; </dt>do Processo de Usuário: Processo na Versão de Assinatura
<dt> &lt; &gt; PID:</dt>Versão
<dt> &lt; &gt; do</dt>mecanismo de definição: Antimalware Engine
<dt> &lt; versão &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-260">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-261">ID do Evento: 1007</span><span class="sxs-lookup"><span data-stu-id="f4b38-261">Event ID: 1007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-262">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-262">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-263">
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-264">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-264">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-265">
<b>A plataforma antimalware realizou uma ação para proteger seu sistema contra malware ou outro software potencialmente indesejado. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-265">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-266">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-266">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-267">Microsoft Defender Antivírus tomou medidas para proteger esse computador contra malware ou outros softwares potencialmente indesejados.</span><span class="sxs-lookup"><span data-stu-id="f4b38-267">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span> <span data-ttu-id="f4b38-268">Para obter mais informações, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f4b38-268">For more information, see the following:</span></span>
<dl><span data-ttu-id="f4b38-269">
<dt>Usuário: &lt; Domínio &gt; \& lt; Nome &gt; </dt>do usuário: ID
<dt> &lt; do &gt; nome</dt>da ameaça: Gravidade da
<dt> &lt; ID &gt; </dt>de 
<dt> Ameaça: &lt; &gt; Severidade , por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-269">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-270">Baixo</span><span class="sxs-lookup"><span data-stu-id="f4b38-270">Low</span></span></li>
<li><span data-ttu-id="f4b38-271">Moderado</span><span class="sxs-lookup"><span data-stu-id="f4b38-271">Moderate</span></span></li>
<li><span data-ttu-id="f4b38-272">Alto</span><span class="sxs-lookup"><span data-stu-id="f4b38-272">High</span></span></li>
<li><span data-ttu-id="f4b38-273">Grave</span><span class="sxs-lookup"><span data-stu-id="f4b38-273">Severe</span></span></li>
</ul><span data-ttu-id="f4b38-274">
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt> Ação: &lt; Ação , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-274">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-275">Clean: o recurso foi limpo</span><span class="sxs-lookup"><span data-stu-id="f4b38-275">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="f4b38-276">Quarentena: o recurso foi colocado em quarentena</span><span class="sxs-lookup"><span data-stu-id="f4b38-276">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="f4b38-277">Remover: o recurso foi excluído</span><span class="sxs-lookup"><span data-stu-id="f4b38-277">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="f4b38-278">Permitir: o recurso teve permissão para executar/existir</span><span class="sxs-lookup"><span data-stu-id="f4b38-278">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="f4b38-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span><span class="sxs-lookup"><span data-stu-id="f4b38-279">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="f4b38-280">Nenhuma ação: nenhuma ação</span><span class="sxs-lookup"><span data-stu-id="f4b38-280">No action: No action</span></span></li>
<li><span data-ttu-id="f4b38-281">Bloquear: o recurso foi impedido de executar</span><span class="sxs-lookup"><span data-stu-id="f4b38-281">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="f4b38-282">
</dt>
<dt>Status: &lt; Versão &gt; de</dt>
<dt>Assinatura de Status: Versão &lt; do &gt; </dt>mecanismo de
<dt>definição: &lt; Antimalware Engine versão &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-282">
</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-283">ID do Evento: 1008</span><span class="sxs-lookup"><span data-stu-id="f4b38-283">Event ID: 1008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-284">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-284">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-285">
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-286">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-286">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-287">
<b>A plataforma antimalware tentou executar uma ação para proteger seu sistema contra malware ou outro software potencialmente indesejado, mas a ação falhou.</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-287">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-288">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-288">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-289">Microsoft Defender Antivírus encontrou um erro ao tomar medidas sobre malware ou outro software potencialmente indesejado.</span><span class="sxs-lookup"><span data-stu-id="f4b38-289">Microsoft Defender Antivirus has encountered an error when taking action on malware or other potentially unwanted software.</span></span> <span data-ttu-id="f4b38-290">Para obter mais informações, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f4b38-290">For more information, see the following:</span></span>
<dl><span data-ttu-id="f4b38-291">
<dt>Usuário: &lt; Domínio &gt; \& lt; Nome &gt; </dt>do usuário: ID
<dt> &lt; do &gt; nome</dt>da ameaça: Gravidade da
<dt> &lt; ID &gt; </dt>de 
<dt> Ameaça: &lt; &gt; Severidade , por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-291">
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-292">Baixo</span><span class="sxs-lookup"><span data-stu-id="f4b38-292">Low</span></span></li>
<li><span data-ttu-id="f4b38-293">Moderado</span><span class="sxs-lookup"><span data-stu-id="f4b38-293">Moderate</span></span></li>
<li><span data-ttu-id="f4b38-294">Alto</span><span class="sxs-lookup"><span data-stu-id="f4b38-294">High</span></span></li>
<li><span data-ttu-id="f4b38-295">Grave</span><span class="sxs-lookup"><span data-stu-id="f4b38-295">Severe</span></span></li>
</ul><span data-ttu-id="f4b38-296">
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Ação &gt; do caminho do</dt> 
<dt> arquivo: Ação , por &lt; &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-296">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-297">Clean: o recurso foi limpo</span><span class="sxs-lookup"><span data-stu-id="f4b38-297">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="f4b38-298">Quarentena: o recurso foi colocado em quarentena</span><span class="sxs-lookup"><span data-stu-id="f4b38-298">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="f4b38-299">Remover: o recurso foi excluído</span><span class="sxs-lookup"><span data-stu-id="f4b38-299">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="f4b38-300">Permitir: o recurso teve permissão para executar/existir</span><span class="sxs-lookup"><span data-stu-id="f4b38-300">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="f4b38-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span><span class="sxs-lookup"><span data-stu-id="f4b38-301">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="f4b38-302">Nenhuma ação: nenhuma ação</span><span class="sxs-lookup"><span data-stu-id="f4b38-302">No action: No action</span></span></li>
<li><span data-ttu-id="f4b38-303">Bloquear: o recurso foi impedido de executar</span><span class="sxs-lookup"><span data-stu-id="f4b38-303">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="f4b38-304">
</dt>
<dt>Código de Erro: &lt; Código de erro &gt; Código de resultado associado ao status da ameaça. Valores HRESULT padrão. </dt> 
<dt>Descrição do erro: &lt; Descrição &gt; do erro Descrição do erro.</dt> 
<dt>Status: &lt; Versão &gt; de</dt>
<dt>Assinatura de Status: Versão &lt; do &gt; </dt>mecanismo de
<dt>definição: &lt; Antimalware Engine versão &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-304">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-305">ID do Evento: 1009</span><span class="sxs-lookup"><span data-stu-id="f4b38-305">Event ID: 1009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-306">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-306">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-307">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-308">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-308">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-309">
<b>A plataforma antimalware restaurou um item da quarentena. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-309">
<b>The antimalware platform restored an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-310">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-310">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-311">Microsoft Defender Antivírus restaurou um item da quarentena.</span><span class="sxs-lookup"><span data-stu-id="f4b38-311">Microsoft Defender Antivirus has restored an item from quarantine.</span></span> <span data-ttu-id="f4b38-312">Para obter mais informações, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f4b38-312">For more information, see the following:</span></span>
<dl><span data-ttu-id="f4b38-313">
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-313">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-314">Baixo</span><span class="sxs-lookup"><span data-stu-id="f4b38-314">Low</span></span></li>
<li><span data-ttu-id="f4b38-315">Moderado</span><span class="sxs-lookup"><span data-stu-id="f4b38-315">Moderate</span></span></li>
<li><span data-ttu-id="f4b38-316">Alto</span><span class="sxs-lookup"><span data-stu-id="f4b38-316">High</span></span></li>
<li><span data-ttu-id="f4b38-317">Grave</span><span class="sxs-lookup"><span data-stu-id="f4b38-317">Severe</span></span></li>
</ul><span data-ttu-id="f4b38-318">
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Usuário &gt; do caminho do</dt>
<dt>arquivo: Domínio &lt; &gt; \& lt; Versão &gt; da</dt>
<dt>assinatura do usuário: Versão &lt; do &gt; </dt>mecanismo de
<dt>definição: &lt; Antimalware Engine versão &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-318">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-319">ID do Evento: 1010</span><span class="sxs-lookup"><span data-stu-id="f4b38-319">Event ID: 1010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-320">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-320">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-321">
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-322">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-322">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-323">
<b>A plataforma antimalware não pôde restaurar um item da quarentena. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-323">
<b>The antimalware platform could not restore an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-324">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-324">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-325">Microsoft Defender Antivírus encontrou um erro ao tentar restaurar um item da quarentena.</span><span class="sxs-lookup"><span data-stu-id="f4b38-325">Microsoft Defender Antivirus has encountered an error trying to restore an item from quarantine.</span></span> <span data-ttu-id="f4b38-326">Para obter mais informações, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f4b38-326">For more information, see the following:</span></span>
<dl><span data-ttu-id="f4b38-327">
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-327">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-328">Baixo</span><span class="sxs-lookup"><span data-stu-id="f4b38-328">Low</span></span></li>
<li><span data-ttu-id="f4b38-329">Moderado</span><span class="sxs-lookup"><span data-stu-id="f4b38-329">Moderate</span></span></li>
<li><span data-ttu-id="f4b38-330">Alto</span><span class="sxs-lookup"><span data-stu-id="f4b38-330">High</span></span></li>
<li><span data-ttu-id="f4b38-331">Grave</span><span class="sxs-lookup"><span data-stu-id="f4b38-331">Severe</span></span></li>
</ul><span data-ttu-id="f4b38-332">
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Usuário &gt; do caminho do</dt>
<dt>arquivo: Domínio &lt; &gt; \& lt; Código &gt; </dt>
<dt>de Erro do Usuário: Código de erro &lt; Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão. </dt> 
<dt>Descrição do erro: &lt; Descrição &gt; do erro Descrição do erro.</dt> 
<dt>Versão de assinatura: &lt; Versão &gt; de definição</dt>
<dt>Versão do mecanismo: &lt; Antimalware Engine versão &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-332">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-333">ID do Evento: 1011</span><span class="sxs-lookup"><span data-stu-id="f4b38-333">Event ID: 1011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-334">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-334">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-335">
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-336">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-336">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-337">
<b>A plataforma antimalware excluiu um item da quarentena. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-337">
<b>The antimalware platform deleted an item from quarantine. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-338">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-338">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-339">Microsoft Defender Antivírus excluiu um item da quarentena.</span><span class="sxs-lookup"><span data-stu-id="f4b38-339">Microsoft Defender Antivirus has deleted an item from quarantine.</span></span><br/><span data-ttu-id="f4b38-340">Para obter mais informações, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f4b38-340">For more information, see the following:</span></span>
<dl><span data-ttu-id="f4b38-341">
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-341">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-342">Baixo</span><span class="sxs-lookup"><span data-stu-id="f4b38-342">Low</span></span></li>
<li><span data-ttu-id="f4b38-343">Moderado</span><span class="sxs-lookup"><span data-stu-id="f4b38-343">Moderate</span></span></li>
<li><span data-ttu-id="f4b38-344">Alto</span><span class="sxs-lookup"><span data-stu-id="f4b38-344">High</span></span></li>
<li><span data-ttu-id="f4b38-345">Grave</span><span class="sxs-lookup"><span data-stu-id="f4b38-345">Severe</span></span></li>
</ul><span data-ttu-id="f4b38-346">
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Usuário &gt; do caminho do</dt>
<dt>arquivo: Domínio &lt; &gt; \& lt; Versão &gt; da</dt>
<dt>assinatura do usuário: Versão &lt; do &gt; </dt>mecanismo de
<dt>definição: &lt; Antimalware Engine versão &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-346">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-347">ID do Evento: 1012</span><span class="sxs-lookup"><span data-stu-id="f4b38-347">Event ID: 1012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-348">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-348">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-349">
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-350">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-350">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-351">
<b>A plataforma antimalware não pôde excluir um item da quarentena.</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-351">
<b>The antimalware platform could not delete an item from quarantine.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-352">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-352">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-353">Microsoft Defender Antivírus encontrou um erro ao tentar excluir um item da quarentena.</span><span class="sxs-lookup"><span data-stu-id="f4b38-353">Microsoft Defender Antivirus has encountered an error trying to delete an item from quarantine.</span></span>
<span data-ttu-id="f4b38-354">Para obter mais informações, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f4b38-354">For more information, see the following:</span></span>
<dl><span data-ttu-id="f4b38-355">
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-355">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-356">Baixo</span><span class="sxs-lookup"><span data-stu-id="f4b38-356">Low</span></span></li>
<li><span data-ttu-id="f4b38-357">Moderado</span><span class="sxs-lookup"><span data-stu-id="f4b38-357">Moderate</span></span></li>
<li><span data-ttu-id="f4b38-358">Alto</span><span class="sxs-lookup"><span data-stu-id="f4b38-358">High</span></span></li>
<li><span data-ttu-id="f4b38-359">Grave</span><span class="sxs-lookup"><span data-stu-id="f4b38-359">Severe</span></span></li>
</ul><span data-ttu-id="f4b38-360">
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Usuário &gt; do caminho do</dt>
<dt>arquivo: Domínio &lt; &gt; \& lt; Código &gt; </dt>
<dt>de Erro do Usuário: Código de erro &lt; Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão. </dt> 
<dt>Descrição do erro: &lt; Descrição &gt; do erro Descrição do erro.</dt> 
<dt>Versão de assinatura: &lt; Versão &gt; de definição</dt>
<dt>Versão do mecanismo: &lt; Antimalware Engine versão &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-360">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-361">ID do Evento: 1013</span><span class="sxs-lookup"><span data-stu-id="f4b38-361">Event ID: 1013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-362">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-362">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-363">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-364">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-364">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-365">
<b>A plataforma antimalware excluiu o histórico de malware e outros softwares potencialmente indesejados.</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-365">
<b>The antimalware platform deleted history of malware and other potentially unwanted software.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-366">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-366">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-367">Microsoft Defender Antivírus o histórico de malware e outros softwares potencialmente indesejados.</span><span class="sxs-lookup"><span data-stu-id="f4b38-367">Microsoft Defender Antivirus has removed history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="f4b38-368">
<dt>Hora: a hora em que o evento ocorreu, por exemplo, quando o histórico é limpo. Esse parâmetro não é usado em eventos de ameaça para que não haja confusão em relação ao tempo de correção ou ao tempo de infecção. Para eles, especificamente os chamamos como Tempo de Ação ou Hora de Detecção.</dt> 
<dt>Usuário: &lt; Domínio &gt; \& lt; Usuário &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-368">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-369">ID do Evento: 1014</span><span class="sxs-lookup"><span data-stu-id="f4b38-369">Event ID: 1014</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-370">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-370">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-371">
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-372">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-372">Message:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-373">A plataforma antimalware não pôde excluir o histórico de malware e outros softwares potencialmente indesejados.</span><span class="sxs-lookup"><span data-stu-id="f4b38-373">The antimalware platform could not delete history of malware and other potentially unwanted software.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-374">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-374">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-375">Microsoft Defender Antivírus encontrou um erro ao tentar remover o histórico de malware e outros softwares potencialmente indesejados.</span><span class="sxs-lookup"><span data-stu-id="f4b38-375">Microsoft Defender Antivirus has encountered an error trying to remove history of malware and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="f4b38-376">
<dt>Hora: a hora em que o evento ocorreu, por exemplo, quando o histórico é limpo. Esse parâmetro não é usado em eventos de ameaça para que não haja confusão em relação ao tempo de correção ou ao tempo de infecção. Para eles, especificamente os chamamos como Tempo de Ação ou Hora de Detecção.</dt> 
<dt>Usuário: &lt; Domínio &gt; \& lt; Código &gt; </dt>
<dt>de Erro do Usuário: Código de erro &lt; Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão. </dt> 
<dt>Descrição do erro: &lt; Descrição &gt; do erro Descrição do erro.</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-376">
<dt>Time: The time when the event occurred, for example when the history is purged. This parameter is not used in threat events so that there is no confusion regarding whether it is remediation time or infection time. For those, we specifically call them as Action Time or Detection Time.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values. </dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-377">ID do Evento: 1015</span><span class="sxs-lookup"><span data-stu-id="f4b38-377">Event ID: 1015</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-378">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-378">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-379">
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-380">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-380">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-381">
<b>A plataforma antimalware detectou comportamento suspeito.</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-381">
<b>The antimalware platform detected suspicious behavior.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-382">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-382">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-383">Microsoft Defender Antivírus detectou um comportamento suspeito.</span><span class="sxs-lookup"><span data-stu-id="f4b38-383">Microsoft Defender Antivirus has detected a suspicious behavior.</span></span><br/><span data-ttu-id="f4b38-384">Para obter mais informações, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f4b38-384">For more information, see the following:</span></span>
<dl><span data-ttu-id="f4b38-385">
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-385">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-386">Baixo</span><span class="sxs-lookup"><span data-stu-id="f4b38-386">Low</span></span></li>
<li><span data-ttu-id="f4b38-387">Moderado</span><span class="sxs-lookup"><span data-stu-id="f4b38-387">Moderate</span></span></li>
<li><span data-ttu-id="f4b38-388">Alto</span><span class="sxs-lookup"><span data-stu-id="f4b38-388">High</span></span></li>
<li><span data-ttu-id="f4b38-389">Grave</span><span class="sxs-lookup"><span data-stu-id="f4b38-389">Severe</span></span></li>
</ul><span data-ttu-id="f4b38-390">
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Origem &gt; da</dt>detecção do caminho 
<dt> do arquivo: &lt; &gt; origem da detecção, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-390">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="f4b38-391">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="f4b38-391">Unknown</span></span></li>
<li><span data-ttu-id="f4b38-392">Computador local</span><span class="sxs-lookup"><span data-stu-id="f4b38-392">Local computer</span></span></li>
<li><span data-ttu-id="f4b38-393">Compartilhamento de rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-393">Network share</span></span></li>
<li><span data-ttu-id="f4b38-394">Internet</span><span class="sxs-lookup"><span data-stu-id="f4b38-394">Internet</span></span></li>
<li><span data-ttu-id="f4b38-395">Tráfego de entrada</span><span class="sxs-lookup"><span data-stu-id="f4b38-395">Incoming traffic</span></span></li>
<li><span data-ttu-id="f4b38-396">Tráfego de saída</span><span class="sxs-lookup"><span data-stu-id="f4b38-396">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="f4b38-397">
</dt>
<dt>Tipo de detecção: &lt; Tipo de detecção , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-397">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-398">Heurística</span><span class="sxs-lookup"><span data-stu-id="f4b38-398">Heuristics</span></span></li>
<li><span data-ttu-id="f4b38-399">Generic</span><span class="sxs-lookup"><span data-stu-id="f4b38-399">Generic</span></span></li>
<li><span data-ttu-id="f4b38-400">Concreto</span><span class="sxs-lookup"><span data-stu-id="f4b38-400">Concrete</span></span></li>
<li><span data-ttu-id="f4b38-401">Assinatura dinâmica</span><span class="sxs-lookup"><span data-stu-id="f4b38-401">Dynamic signature</span></span></li>
</ul><span data-ttu-id="f4b38-402">
</dt>
<dt>Fonte de detecção: &lt; Fonte de detecção por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-402">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="f4b38-403">Usuário: iniciado pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f4b38-403">User: user initiated</span></span></li>
<li><span data-ttu-id="f4b38-404">Sistema: iniciado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="f4b38-404">System: system initiated</span></span></li>
<li><span data-ttu-id="f4b38-405">Em tempo real: componente em tempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="f4b38-405">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="f4b38-406">IOAV: IE Downloads e Outlook Express Attachments iniciados</span><span class="sxs-lookup"><span data-stu-id="f4b38-406">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="f4b38-407">NIS: Sistema de inspeção de rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-407">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="f4b38-408">IEPROTECT: IE - IExtensionValidation; isso protege contra controles de página da Web mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="f4b38-408">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="f4b38-409">Antimalware de início antecipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="f4b38-409">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="f4b38-410">Isso inclui malware detectado pela sequência de inicialização</span><span class="sxs-lookup"><span data-stu-id="f4b38-410">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="f4b38-411">Atestado remoto</span><span class="sxs-lookup"><span data-stu-id="f4b38-411">Remote attestation</span></span></li>
</ul><span data-ttu-id="f4b38-412">Interface de verificação antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="f4b38-412">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="f4b38-413">Usado principalmente para proteger scripts (PS, VBS), embora também possa ser invocado por terceiros.</span><span class="sxs-lookup"><span data-stu-id="f4b38-413">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="f4b38-414">Status do </dt> 
<dt>UAC: Usuário &lt; de &gt; Status:</dt>Domínio
<dt> &lt; &gt; \& lt; Nome &gt; </dt>do Processo de Usuário: Processo na ID de Assinatura
<dt> &lt; &gt; PID:</dt>
<dt>gravidade correspondente à enumeração.</dt> 
<dt>Versão de assinatura: &lt; Versão &gt; de</dt>
<dt>definição Versão do mecanismo: &lt; Antimalware Engine &gt; versão</dt>
<dt>Fidelity Label:</dt>
<dt>Target File Name: File name of the &lt; &gt; file.</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-414">UAC</dt>
<dt>Status: &lt;Status&gt;</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature ID: Enumeration matching severity.</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Fidelity Label:</dt>
<dt>Target File Name: &lt;File name&gt; Name of the file.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-415">ID do Evento: 1116</span><span class="sxs-lookup"><span data-stu-id="f4b38-415">Event ID: 1116</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-416">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-416">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-417">
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-418">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-418">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-419">
<b>A plataforma antimalware detectou malware ou outro software potencialmente indesejado. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-419">
<b>The antimalware platform detected malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-420">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-420">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-421">Microsoft Defender Antivírus detectou malware ou outro software potencialmente indesejado.</span><span class="sxs-lookup"><span data-stu-id="f4b38-421">Microsoft Defender Antivirus has detected malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="f4b38-422">Para obter mais informações, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f4b38-422">For more information, see the following:</span></span>
<dl><span data-ttu-id="f4b38-423">
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-423">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-424">Baixo</span><span class="sxs-lookup"><span data-stu-id="f4b38-424">Low</span></span></li>
<li><span data-ttu-id="f4b38-425">Moderado</span><span class="sxs-lookup"><span data-stu-id="f4b38-425">Moderate</span></span></li>
<li><span data-ttu-id="f4b38-426">Alto</span><span class="sxs-lookup"><span data-stu-id="f4b38-426">High</span></span></li>
<li><span data-ttu-id="f4b38-427">Grave</span><span class="sxs-lookup"><span data-stu-id="f4b38-427">Severe</span></span></li>
</ul><span data-ttu-id="f4b38-428">
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Origem &gt; da</dt>detecção do caminho 
<dt> do arquivo: &lt; &gt; origem da detecção, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-428">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="f4b38-429">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="f4b38-429">Unknown</span></span></li>
<li><span data-ttu-id="f4b38-430">Computador local</span><span class="sxs-lookup"><span data-stu-id="f4b38-430">Local computer</span></span></li>
<li><span data-ttu-id="f4b38-431">Compartilhamento de rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-431">Network share</span></span></li>
<li><span data-ttu-id="f4b38-432">Internet</span><span class="sxs-lookup"><span data-stu-id="f4b38-432">Internet</span></span></li>
<li><span data-ttu-id="f4b38-433">Tráfego de entrada</span><span class="sxs-lookup"><span data-stu-id="f4b38-433">Incoming traffic</span></span></li>
<li><span data-ttu-id="f4b38-434">Tráfego de saída</span><span class="sxs-lookup"><span data-stu-id="f4b38-434">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="f4b38-435">
</dt>
<dt>Tipo de detecção: &lt; Tipo de detecção , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-435">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-436">Heurística</span><span class="sxs-lookup"><span data-stu-id="f4b38-436">Heuristics</span></span></li>
<li><span data-ttu-id="f4b38-437">Generic</span><span class="sxs-lookup"><span data-stu-id="f4b38-437">Generic</span></span></li>
<li><span data-ttu-id="f4b38-438">Concreto</span><span class="sxs-lookup"><span data-stu-id="f4b38-438">Concrete</span></span></li>
<li><span data-ttu-id="f4b38-439">Assinatura dinâmica</span><span class="sxs-lookup"><span data-stu-id="f4b38-439">Dynamic signature</span></span></li>
</ul><span data-ttu-id="f4b38-440">
</dt>
<dt>Fonte de detecção: &lt; Fonte de detecção por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-440">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="f4b38-441">Usuário: iniciado pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f4b38-441">User: user initiated</span></span></li>
<li><span data-ttu-id="f4b38-442">Sistema: iniciado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="f4b38-442">System: system initiated</span></span></li>
<li><span data-ttu-id="f4b38-443">Em tempo real: componente em tempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="f4b38-443">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="f4b38-444">IOAV: IE Downloads e Outlook Express Attachments iniciados</span><span class="sxs-lookup"><span data-stu-id="f4b38-444">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="f4b38-445">NIS: Sistema de inspeção de rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-445">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="f4b38-446">IEPROTECT: IE - IExtensionValidation; isso protege contra controles de página da Web mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="f4b38-446">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="f4b38-447">Antimalware de início antecipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="f4b38-447">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="f4b38-448">Isso inclui malware detectado pela sequência de inicialização</span><span class="sxs-lookup"><span data-stu-id="f4b38-448">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="f4b38-449">Atestado remoto</span><span class="sxs-lookup"><span data-stu-id="f4b38-449">Remote attestation</span></span></li>
</ul><span data-ttu-id="f4b38-450">Interface de verificação antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="f4b38-450">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="f4b38-451">Usado principalmente para proteger scripts (PS, VBS), embora também possa ser invocado por terceiros.</span><span class="sxs-lookup"><span data-stu-id="f4b38-451">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="f4b38-452">Usuário </dt> 
<dt>UAC: &lt; Domínio &gt; \& lt; Nome &gt; </dt>do Processo de Usuário: Processo na Versão de Assinatura
<dt> &lt; &gt; PID:</dt>Versão
<dt> &lt; &gt; do</dt>mecanismo de definição: Antimalware Engine
<dt> &lt; versão &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-452">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-453">Ação do usuário:</span><span class="sxs-lookup"><span data-stu-id="f4b38-453">User action:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-454">Nenhuma ação é necessária.</span><span class="sxs-lookup"><span data-stu-id="f4b38-454">No action is required.</span></span> <span data-ttu-id="f4b38-455">Microsoft Defender Antivírus pode suspender e tomar medidas de rotina sobre essa ameaça.</span><span class="sxs-lookup"><span data-stu-id="f4b38-455">Microsoft Defender Antivirus can suspend and take routine action on this threat.</span></span> <span data-ttu-id="f4b38-456">Se você quiser remover a ameaça manualmente, na interface Microsoft Defender Antivírus, clique em <b>Limpar Computador</b>.</span><span class="sxs-lookup"><span data-stu-id="f4b38-456">If you want to remove the threat manually, in the Microsoft Defender Antivirus interface, click <b>Clean Computer</b>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-457">ID do Evento: 1117</span><span class="sxs-lookup"><span data-stu-id="f4b38-457">Event ID: 1117</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-458">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-458">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-459">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-460">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-460">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-461">
<b>A plataforma antimalware realizou uma ação para proteger seu sistema contra malware ou outro software potencialmente indesejado. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-461">
<b>The antimalware platform performed an action to protect your system from malware or other potentially unwanted software. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-462">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-462">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-463">Microsoft Defender Antivírus tomou medidas para proteger esse computador contra malware ou outros softwares potencialmente indesejados.</span><span class="sxs-lookup"><span data-stu-id="f4b38-463">Microsoft Defender Antivirus has taken action to protect this machine from malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="f4b38-464">Para obter mais informações, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f4b38-464">For more information, see the following:</span></span>
<dl><span data-ttu-id="f4b38-465">
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-465">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-466">Baixo</span><span class="sxs-lookup"><span data-stu-id="f4b38-466">Low</span></span></li>
<li><span data-ttu-id="f4b38-467">Moderado</span><span class="sxs-lookup"><span data-stu-id="f4b38-467">Moderate</span></span></li>
<li><span data-ttu-id="f4b38-468">Alto</span><span class="sxs-lookup"><span data-stu-id="f4b38-468">High</span></span></li>
<li><span data-ttu-id="f4b38-469">Grave</span><span class="sxs-lookup"><span data-stu-id="f4b38-469">Severe</span></span></li>
</ul><span data-ttu-id="f4b38-470">
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Origem &gt; da</dt>detecção do caminho 
<dt> do arquivo: &lt; &gt; origem da detecção, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-470">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="f4b38-471">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="f4b38-471">Unknown</span></span></li>
<li><span data-ttu-id="f4b38-472">Computador local</span><span class="sxs-lookup"><span data-stu-id="f4b38-472">Local computer</span></span></li>
<li><span data-ttu-id="f4b38-473">Compartilhamento de rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-473">Network share</span></span></li>
<li><span data-ttu-id="f4b38-474">Internet</span><span class="sxs-lookup"><span data-stu-id="f4b38-474">Internet</span></span></li>
<li><span data-ttu-id="f4b38-475">Tráfego de entrada</span><span class="sxs-lookup"><span data-stu-id="f4b38-475">Incoming traffic</span></span></li>
<li><span data-ttu-id="f4b38-476">Tráfego de saída</span><span class="sxs-lookup"><span data-stu-id="f4b38-476">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="f4b38-477">
</dt>
<dt>Tipo de detecção: &lt; Tipo de detecção , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-477">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-478">Heurística</span><span class="sxs-lookup"><span data-stu-id="f4b38-478">Heuristics</span></span></li>
<li><span data-ttu-id="f4b38-479">Generic</span><span class="sxs-lookup"><span data-stu-id="f4b38-479">Generic</span></span></li>
<li><span data-ttu-id="f4b38-480">Concreto</span><span class="sxs-lookup"><span data-stu-id="f4b38-480">Concrete</span></span></li>
<li><span data-ttu-id="f4b38-481">Assinatura dinâmica</span><span class="sxs-lookup"><span data-stu-id="f4b38-481">Dynamic signature</span></span></li>
</ul><span data-ttu-id="f4b38-482">
</dt>
<dt>Fonte de detecção: &lt; Fonte de detecção por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-482">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="f4b38-483">Usuário: iniciado pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f4b38-483">User: user initiated</span></span></li>
<li><span data-ttu-id="f4b38-484">Sistema: iniciado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="f4b38-484">System: system initiated</span></span></li>
<li><span data-ttu-id="f4b38-485">Em tempo real: componente em tempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="f4b38-485">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="f4b38-486">IOAV: IE Downloads e Outlook Express Attachments iniciados</span><span class="sxs-lookup"><span data-stu-id="f4b38-486">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="f4b38-487">NIS: Sistema de inspeção de rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-487">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="f4b38-488">IEPROTECT: IE - IExtensionValidation; isso protege contra controles de página da Web mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="f4b38-488">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="f4b38-489">Antimalware de início antecipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="f4b38-489">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="f4b38-490">Isso inclui malware detectado pela sequência de inicialização</span><span class="sxs-lookup"><span data-stu-id="f4b38-490">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="f4b38-491">Atestado remoto</span><span class="sxs-lookup"><span data-stu-id="f4b38-491">Remote attestation</span></span></li>
</ul><span data-ttu-id="f4b38-492">Interface de verificação antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="f4b38-492">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="f4b38-493">Usado principalmente para proteger scripts (PS, VBS), embora também possa ser invocado por terceiros.</span><span class="sxs-lookup"><span data-stu-id="f4b38-493">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="f4b38-494">Usuário </dt> 
<dt>UAC: &lt; Domínio &gt; \& lt; Nome &gt; </dt>
<dt>do Processo de Usuário: Processo na Ação &lt; &gt; PID:</dt>Ação , por 
<dt> &lt; &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-494">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-495">Clean: o recurso foi limpo</span><span class="sxs-lookup"><span data-stu-id="f4b38-495">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="f4b38-496">Quarentena: o recurso foi colocado em quarentena</span><span class="sxs-lookup"><span data-stu-id="f4b38-496">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="f4b38-497">Remover: o recurso foi excluído</span><span class="sxs-lookup"><span data-stu-id="f4b38-497">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="f4b38-498">Permitir: o recurso teve permissão para executar/existir</span><span class="sxs-lookup"><span data-stu-id="f4b38-498">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="f4b38-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span><span class="sxs-lookup"><span data-stu-id="f4b38-499">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="f4b38-500">Nenhuma ação: nenhuma ação</span><span class="sxs-lookup"><span data-stu-id="f4b38-500">No action: No action</span></span></li>
<li><span data-ttu-id="f4b38-501">Bloquear: o recurso foi impedido de executar</span><span class="sxs-lookup"><span data-stu-id="f4b38-501">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="f4b38-502">
</dt>
<dt>Status da Ação: &lt; Descrição de &gt; ações adicionais</dt>
<dt>Código de erro: &lt; Código de erro Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt> 
<dt>Versão de assinatura: &lt; &gt;</dt>Versão do mecanismo de
<dt>definição: Antimalware Engine &lt; versão &gt; </dt> OBSERVAÇÃO: sempre que Microsoft Defender Antivírus, Microsoft Security Essentials, Ferramenta de Remoção de Software Mal-Intencionado ou System Center Endpoint Protection detecta um malware, ele restaurará as seguintes configurações e serviços do sistema que o malware pode ter alterado:</span><span class="sxs-lookup"><span data-stu-id="f4b38-502">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt> NOTE: Whenever Microsoft Defender Antivirus, Microsoft Security Essentials, Malicious Software Removal Tool, or System Center Endpoint Protection detects a malware, it will restore the following system settings and services that the malware might have changed:</span></span><ul>
<li><span data-ttu-id="f4b38-503">Configuração padrão do Internet Explorer ou Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f4b38-503">Default Internet Explorer or Microsoft Edge setting</span></span></li>
<li><span data-ttu-id="f4b38-504">Configurações do Controle de Acesso para Usuário</span><span class="sxs-lookup"><span data-stu-id="f4b38-504">User Access Control settings</span></span></li>
<li><span data-ttu-id="f4b38-505">Configurações do Chrome</span><span class="sxs-lookup"><span data-stu-id="f4b38-505">Chrome settings</span></span></li>
<li><span data-ttu-id="f4b38-506">Dados de controle de inicialização</span><span class="sxs-lookup"><span data-stu-id="f4b38-506">Boot Control Data</span></span></li>
<li><span data-ttu-id="f4b38-507">Configurações do Registro do Gerenciador de Tarefas e regedit</span><span class="sxs-lookup"><span data-stu-id="f4b38-507">Regedit and Task Manager registry settings</span></span></li>
<li><span data-ttu-id="f4b38-508">Windows Serviço de Atualização, Transferência Inteligente em Segundo Plano e Serviço de Chamada de Procedimento Remoto</span><span class="sxs-lookup"><span data-stu-id="f4b38-508">Windows Update, Background Intelligent Transfer Service, and Remote Procedure Call service</span></span></li>
<li><span data-ttu-id="f4b38-509">Windows Arquivos do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="f4b38-509">Windows Operating System files</span></span></li></ul>
<span data-ttu-id="f4b38-510">O contexto acima se aplica às seguintes versões de cliente e servidor:</span><span class="sxs-lookup"><span data-stu-id="f4b38-510">The above context applies to the following client and server versions:</span></span>
<table>
<tr>
<th><span data-ttu-id="f4b38-511">Sistema operacional</span><span class="sxs-lookup"><span data-stu-id="f4b38-511">Operating system</span></span></th>
<th><span data-ttu-id="f4b38-512">Versão do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="f4b38-512">Operating system version</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-513">Sistema Operacional Cliente</span><span class="sxs-lookup"><span data-stu-id="f4b38-513">Client Operating System</span></span>
</td>
<td>
<span data-ttu-id="f4b38-514">Windows Vista (Service Pack 1 ou Service Pack 2), Windows 7 e posteriores</span><span class="sxs-lookup"><span data-stu-id="f4b38-514">Windows Vista (Service Pack 1, or Service Pack 2), Windows 7 and later</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-515">Sistema Operacional do Servidor</span><span class="sxs-lookup"><span data-stu-id="f4b38-515">Server Operating System</span></span>
</td>
<td>
<span data-ttu-id="f4b38-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 e Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="f4b38-516">Windows Server 2008, Windows Server 2008 R2, Windows Server 2012, and Windows Server 2016</span></span>
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-517">Ação do usuário:</span><span class="sxs-lookup"><span data-stu-id="f4b38-517">User action:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-518">Nenhuma ação é necessária.</span><span class="sxs-lookup"><span data-stu-id="f4b38-518">No action is necessary.</span></span> <span data-ttu-id="f4b38-519">Microsoft Defender Antivírus uma ameaça removida ou em quarentena.</span><span class="sxs-lookup"><span data-stu-id="f4b38-519">Microsoft Defender Antivirus removed or quarantined a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-520">ID do Evento: 1118</span><span class="sxs-lookup"><span data-stu-id="f4b38-520">Event ID: 1118</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-521">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-521">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-522">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-523">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-523">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-524">
<b>A plataforma antimalware tentou executar uma ação para proteger seu sistema contra malware ou outro software potencialmente indesejado, mas a ação falhou. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-524">
<b>The antimalware platform attempted to perform an action to protect your system from malware or other potentially unwanted software, but the action failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-525">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-525">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-526">Microsoft Defender Antivírus encontrou um erro não crítico ao tomar medidas sobre malware ou outro software potencialmente indesejado.</span><span class="sxs-lookup"><span data-stu-id="f4b38-526">Microsoft Defender Antivirus has encountered a non-critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="f4b38-527">Para obter mais informações, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f4b38-527">For more information, see the following:</span></span>
<dl><span data-ttu-id="f4b38-528">
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-528">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-529">Baixo</span><span class="sxs-lookup"><span data-stu-id="f4b38-529">Low</span></span></li>
<li><span data-ttu-id="f4b38-530">Moderado</span><span class="sxs-lookup"><span data-stu-id="f4b38-530">Moderate</span></span></li>
<li><span data-ttu-id="f4b38-531">Alto</span><span class="sxs-lookup"><span data-stu-id="f4b38-531">High</span></span></li>
<li><span data-ttu-id="f4b38-532">Grave</span><span class="sxs-lookup"><span data-stu-id="f4b38-532">Severe</span></span></li>
</ul><span data-ttu-id="f4b38-533">
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Origem &gt; da</dt>detecção do caminho 
<dt> do arquivo: &lt; &gt; origem da detecção, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-533">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="f4b38-534">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="f4b38-534">Unknown</span></span></li>
<li><span data-ttu-id="f4b38-535">Computador local</span><span class="sxs-lookup"><span data-stu-id="f4b38-535">Local computer</span></span></li>
<li><span data-ttu-id="f4b38-536">Compartilhamento de rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-536">Network share</span></span></li>
<li><span data-ttu-id="f4b38-537">Internet</span><span class="sxs-lookup"><span data-stu-id="f4b38-537">Internet</span></span></li>
<li><span data-ttu-id="f4b38-538">Tráfego de entrada</span><span class="sxs-lookup"><span data-stu-id="f4b38-538">Incoming traffic</span></span></li>
<li><span data-ttu-id="f4b38-539">Tráfego de saída</span><span class="sxs-lookup"><span data-stu-id="f4b38-539">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="f4b38-540">
</dt>
<dt>Tipo de detecção: &lt; Tipo de detecção , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-540">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-541">Heurística</span><span class="sxs-lookup"><span data-stu-id="f4b38-541">Heuristics</span></span></li>
<li><span data-ttu-id="f4b38-542">Generic</span><span class="sxs-lookup"><span data-stu-id="f4b38-542">Generic</span></span></li>
<li><span data-ttu-id="f4b38-543">Concreto</span><span class="sxs-lookup"><span data-stu-id="f4b38-543">Concrete</span></span></li>
<li><span data-ttu-id="f4b38-544">Assinatura dinâmica</span><span class="sxs-lookup"><span data-stu-id="f4b38-544">Dynamic signature</span></span></li>
</ul><span data-ttu-id="f4b38-545">
</dt>
<dt>Fonte de detecção: &lt; Fonte de detecção por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-545">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="f4b38-546">Usuário: iniciado pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f4b38-546">User: user initiated</span></span></li>
<li><span data-ttu-id="f4b38-547">Sistema: iniciado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="f4b38-547">System: system initiated</span></span></li>
<li><span data-ttu-id="f4b38-548">Em tempo real: componente em tempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="f4b38-548">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="f4b38-549">IOAV: IE Downloads e Outlook Express Attachments iniciados</span><span class="sxs-lookup"><span data-stu-id="f4b38-549">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="f4b38-550">NIS: Sistema de inspeção de rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-550">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="f4b38-551">IEPROTECT: IE - IExtensionValidation; isso protege contra controles de página da Web mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="f4b38-551">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="f4b38-552">Antimalware de início antecipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="f4b38-552">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="f4b38-553">Isso inclui malware detectado pela sequência de inicialização</span><span class="sxs-lookup"><span data-stu-id="f4b38-553">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="f4b38-554">Atestado remoto</span><span class="sxs-lookup"><span data-stu-id="f4b38-554">Remote attestation</span></span></li>
</ul><span data-ttu-id="f4b38-555">Interface de verificação antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="f4b38-555">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="f4b38-556">Usado principalmente para proteger scripts (PS, VBS), embora também possa ser invocado por terceiros.</span><span class="sxs-lookup"><span data-stu-id="f4b38-556">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="f4b38-557">Usuário </dt> 
<dt>UAC: &lt; Domínio &gt; \& lt; Nome &gt; </dt>
<dt>do Processo de Usuário: Processo na Ação &lt; &gt; PID:</dt>Ação , por 
<dt> &lt; &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-557">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-558">Clean: o recurso foi limpo</span><span class="sxs-lookup"><span data-stu-id="f4b38-558">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="f4b38-559">Quarentena: o recurso foi colocado em quarentena</span><span class="sxs-lookup"><span data-stu-id="f4b38-559">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="f4b38-560">Remover: o recurso foi excluído</span><span class="sxs-lookup"><span data-stu-id="f4b38-560">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="f4b38-561">Permitir: o recurso teve permissão para executar/existir</span><span class="sxs-lookup"><span data-stu-id="f4b38-561">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="f4b38-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span><span class="sxs-lookup"><span data-stu-id="f4b38-562">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="f4b38-563">Nenhuma ação: nenhuma ação</span><span class="sxs-lookup"><span data-stu-id="f4b38-563">No action: No action</span></span></li>
<li><span data-ttu-id="f4b38-564">Bloquear: o recurso foi impedido de executar</span><span class="sxs-lookup"><span data-stu-id="f4b38-564">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="f4b38-565">
</dt>
<dt>Status da Ação: &lt; Descrição de &gt; ações adicionais</dt>
<dt>Código de erro: &lt; Código de erro Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt> 
<dt>Versão de assinatura: &lt; Versão &gt; de definição</dt>
<dt>Versão do mecanismo: &lt; Antimalware Engine versão &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-565">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-566">Ação do usuário:</span><span class="sxs-lookup"><span data-stu-id="f4b38-566">User action:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-567">Nenhuma ação é necessária.</span><span class="sxs-lookup"><span data-stu-id="f4b38-567">No action is necessary.</span></span> <span data-ttu-id="f4b38-568">Microsoft Defender Antivírus falha ao concluir uma tarefa relacionada à correção de malware.</span><span class="sxs-lookup"><span data-stu-id="f4b38-568">Microsoft Defender Antivirus failed to complete a task related to the malware remediation.</span></span> <span data-ttu-id="f4b38-569">Isso não é uma falha crítica.</span><span class="sxs-lookup"><span data-stu-id="f4b38-569">This is not a critical failure.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-570">ID do Evento: 1119</span><span class="sxs-lookup"><span data-stu-id="f4b38-570">Event ID: 1119</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-571">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-571">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-572">
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-573">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-573">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-574">
<b>A plataforma antimalware encontrou um erro crítico ao tentar tomar medidas sobre malware ou outro software potencialmente indesejado. Há mais detalhes na mensagem de evento.</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-574">
<b>The antimalware platform encountered a critical error when trying to take action on malware or other potentially unwanted software. There are more details in the event message.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-575">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-575">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-576">Microsoft Defender Antivírus encontrou um erro crítico ao tomar medidas sobre malware ou outro software potencialmente indesejado.</span><span class="sxs-lookup"><span data-stu-id="f4b38-576">Microsoft Defender Antivirus has encountered a critical error when taking action on malware or other potentially unwanted software.</span></span><br/><span data-ttu-id="f4b38-577">Para obter mais informações, confira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f4b38-577">For more information, see the following:</span></span>
<dl><span data-ttu-id="f4b38-578">
<dt>Nome: &lt; ID &gt; do</dt>nome da ameaça: Gravidade da
<dt> &lt; &gt; ID</dt>da 
<dt> Ameaça: &lt; &gt; Severidade, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-578">
<dt>Name: &lt;Threat name&gt;</dt>
<dt>ID: &lt;Threat ID&gt;</dt>
<dt>Severity: &lt;Severity&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-579">Baixo</span><span class="sxs-lookup"><span data-stu-id="f4b38-579">Low</span></span></li>
<li><span data-ttu-id="f4b38-580">Moderado</span><span class="sxs-lookup"><span data-stu-id="f4b38-580">Moderate</span></span></li>
<li><span data-ttu-id="f4b38-581">Alto</span><span class="sxs-lookup"><span data-stu-id="f4b38-581">High</span></span></li>
<li><span data-ttu-id="f4b38-582">Grave</span><span class="sxs-lookup"><span data-stu-id="f4b38-582">Severe</span></span></li>
</ul><span data-ttu-id="f4b38-583">
</dt>
<dt>Categoria: &lt; Descrição &gt; da categoria , por exemplo, qualquer tipo de ameaça ou malware.</dt> 
<dt>Caminho: &lt; Origem &gt; da</dt>detecção do caminho 
<dt> do arquivo: &lt; &gt; origem da detecção, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-583">
</dt>
<dt>Category: &lt;Category description&gt;, for example, any threat or malware type.</dt>
<dt>Path: &lt;File path&gt;</dt>
<dt>Detection Origin: &lt;Detection origin&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="f4b38-584">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="f4b38-584">Unknown</span></span></li>
<li><span data-ttu-id="f4b38-585">Computador local</span><span class="sxs-lookup"><span data-stu-id="f4b38-585">Local computer</span></span></li>
<li><span data-ttu-id="f4b38-586">Compartilhamento de rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-586">Network share</span></span></li>
<li><span data-ttu-id="f4b38-587">Internet</span><span class="sxs-lookup"><span data-stu-id="f4b38-587">Internet</span></span></li>
<li><span data-ttu-id="f4b38-588">Tráfego de entrada</span><span class="sxs-lookup"><span data-stu-id="f4b38-588">Incoming traffic</span></span></li>
<li><span data-ttu-id="f4b38-589">Tráfego de saída</span><span class="sxs-lookup"><span data-stu-id="f4b38-589">Outgoing traffic</span></span></li>
</ul><span data-ttu-id="f4b38-590">
</dt>
<dt>Tipo de detecção: &lt; Tipo de detecção , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-590">
</dt>
<dt>Detection Type: &lt;Detection type&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-591">Heurística</span><span class="sxs-lookup"><span data-stu-id="f4b38-591">Heuristics</span></span></li>
<li><span data-ttu-id="f4b38-592">Generic</span><span class="sxs-lookup"><span data-stu-id="f4b38-592">Generic</span></span></li>
<li><span data-ttu-id="f4b38-593">Concreto</span><span class="sxs-lookup"><span data-stu-id="f4b38-593">Concrete</span></span></li>
<li><span data-ttu-id="f4b38-594">Assinatura dinâmica</span><span class="sxs-lookup"><span data-stu-id="f4b38-594">Dynamic signature</span></span></li>
</ul><span data-ttu-id="f4b38-595">
</dt>
<dt>Fonte de detecção: &lt; Fonte de detecção por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-595">
</dt>
<dt>Detection Source: &lt;Detection source&gt; for example:</span></span><ul>
<li><span data-ttu-id="f4b38-596">Usuário: iniciado pelo usuário</span><span class="sxs-lookup"><span data-stu-id="f4b38-596">User: user initiated</span></span></li>
<li><span data-ttu-id="f4b38-597">Sistema: iniciado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="f4b38-597">System: system initiated</span></span></li>
<li><span data-ttu-id="f4b38-598">Em tempo real: componente em tempo real iniciado</span><span class="sxs-lookup"><span data-stu-id="f4b38-598">Real-time: real-time component initiated</span></span></li>
<li><span data-ttu-id="f4b38-599">IOAV: IE Downloads e Outlook Express Attachments iniciados</span><span class="sxs-lookup"><span data-stu-id="f4b38-599">IOAV: IE Downloads and Outlook Express Attachments initiated</span></span></li>
<li><span data-ttu-id="f4b38-600">NIS: Sistema de inspeção de rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-600">NIS: Network inspection system</span></span></li>
<li><span data-ttu-id="f4b38-601">IEPROTECT: IE - IExtensionValidation; isso protege contra controles de página da Web mal-intencionados</span><span class="sxs-lookup"><span data-stu-id="f4b38-601">IEPROTECT: IE - IExtensionValidation; this protects against malicious webpage controls</span></span></li>
<li><span data-ttu-id="f4b38-602">Antimalware de início antecipado (ELAM).</span><span class="sxs-lookup"><span data-stu-id="f4b38-602">Early Launch Antimalware (ELAM).</span></span> <span data-ttu-id="f4b38-603">Isso inclui malware detectado pela sequência de inicialização</span><span class="sxs-lookup"><span data-stu-id="f4b38-603">This includes malware detected by the boot sequence</span></span></li>
<li><span data-ttu-id="f4b38-604">Atestado remoto</span><span class="sxs-lookup"><span data-stu-id="f4b38-604">Remote attestation</span></span></li>
</ul><span data-ttu-id="f4b38-605">Interface de verificação antimalware (AMSI).</span><span class="sxs-lookup"><span data-stu-id="f4b38-605">Antimalware Scan Interface (AMSI).</span></span> <span data-ttu-id="f4b38-606">Usado principalmente para proteger scripts (PS, VBS), embora também possa ser invocado por terceiros.</span><span class="sxs-lookup"><span data-stu-id="f4b38-606">Primarily used to protect scripts (PS, VBS), though it can be invoked by third parties as well.</span></span>
<span data-ttu-id="f4b38-607">Usuário </dt> 
<dt>UAC: &lt; Domínio &gt; \& lt; Nome &gt; </dt>
<dt>do Processo de Usuário: Processo na Ação &lt; &gt; PID:</dt>Ação , por 
<dt> &lt; &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-607">UAC</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Process Name: &lt;Process in the PID&gt;</dt>
<dt>Action: &lt;Action&gt;, for example:</span></span><ul>
<li><span data-ttu-id="f4b38-608">Clean: o recurso foi limpo</span><span class="sxs-lookup"><span data-stu-id="f4b38-608">Clean: The resource was cleaned</span></span></li>
<li><span data-ttu-id="f4b38-609">Quarentena: o recurso foi colocado em quarentena</span><span class="sxs-lookup"><span data-stu-id="f4b38-609">Quarantine: The resource was quarantined</span></span></li>
<li><span data-ttu-id="f4b38-610">Remover: o recurso foi excluído</span><span class="sxs-lookup"><span data-stu-id="f4b38-610">Remove: The resource was deleted</span></span></li>
<li><span data-ttu-id="f4b38-611">Permitir: o recurso teve permissão para executar/existir</span><span class="sxs-lookup"><span data-stu-id="f4b38-611">Allow: The resource was allowed to execute/exist</span></span></li>
<li><span data-ttu-id="f4b38-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span><span class="sxs-lookup"><span data-stu-id="f4b38-612">User defined: User-defined action that is normally one from this list of actions that the user has specified</span></span></li>
<li><span data-ttu-id="f4b38-613">Nenhuma ação: nenhuma ação</span><span class="sxs-lookup"><span data-stu-id="f4b38-613">No action: No action</span></span></li>
<li><span data-ttu-id="f4b38-614">Bloquear: o recurso foi impedido de executar</span><span class="sxs-lookup"><span data-stu-id="f4b38-614">Block: The resource was blocked from executing</span></span></li>
</ul><span data-ttu-id="f4b38-615">
</dt>
<dt>Status da Ação: &lt; Descrição de &gt; ações adicionais</dt>
<dt>Código de erro: &lt; Código de erro Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt> 
<dt>Versão de assinatura: &lt; Versão &gt; de definição</dt>
<dt>Versão do mecanismo: &lt; Antimalware Engine versão &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-615">
</dt>
<dt>Action Status: &lt;Description of additional actions&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-616">Ação do usuário:</span><span class="sxs-lookup"><span data-stu-id="f4b38-616">User action:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-617">O Microsoft Defender Antivírus cliente encontrou esse erro devido a problemas críticos.</span><span class="sxs-lookup"><span data-stu-id="f4b38-617">The Microsoft Defender Antivirus client encountered this error due to critical issues.</span></span> <span data-ttu-id="f4b38-618">O ponto de extremidade pode não estar protegido.</span><span class="sxs-lookup"><span data-stu-id="f4b38-618">The endpoint might not be protected.</span></span> <span data-ttu-id="f4b38-619">Revise a descrição do erro e siga as etapas <b>de ação do usuário</b> relevantes abaixo.</span><span class="sxs-lookup"><span data-stu-id="f4b38-619">Review the error description then follow the relevant <b>User action</b> steps below.</span></span>
<table>
<tr>
<th><span data-ttu-id="f4b38-620">Ação</span><span class="sxs-lookup"><span data-stu-id="f4b38-620">Action</span></span></th>
<th><span data-ttu-id="f4b38-621">Ação do usuário</span><span class="sxs-lookup"><span data-stu-id="f4b38-621">User action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="f4b38-622">
<b>Remover</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-622">
<b>Remove</b>
</span></span></td>
<td>
<span data-ttu-id="f4b38-623">Atualize as definições e verifique se a remoção foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="f4b38-623">Update the definitions then verify that the removal was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="f4b38-624">
<b>Clean</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-624">
<b>Clean</b>
</span></span></td>
<td>
<span data-ttu-id="f4b38-625">Atualize as definições e verifique se a correção foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="f4b38-625">Update the definitions then verify that the remediation was successful.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="f4b38-626">
<b>Quarentena</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-626">
<b>Quarantine</b>
</span></span></td>
<td>
<span data-ttu-id="f4b38-627">Atualize as definições e verifique se o usuário tem permissão para acessar os recursos necessários.</span><span class="sxs-lookup"><span data-stu-id="f4b38-627">Update the definitions and verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
<tr>
<td><span data-ttu-id="f4b38-628">
<b>Permitir</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-628">
<b>Allow</b>
</span></span></td>
<td>
<span data-ttu-id="f4b38-629">Verifique se o usuário tem permissão para acessar os recursos necessários.</span><span class="sxs-lookup"><span data-stu-id="f4b38-629">Verify that the user has permission to access the necessary resources.</span></span>
</td>
</tr>
</table>

<span data-ttu-id="f4b38-630">Se esse evento persistir:</span><span class="sxs-lookup"><span data-stu-id="f4b38-630">If this event persists:</span></span><ol>
<li><span data-ttu-id="f4b38-631">Execute a verificação novamente.</span><span class="sxs-lookup"><span data-stu-id="f4b38-631">Run the scan again.</span></span></li>
<li><span data-ttu-id="f4b38-632">Se ele falhar da mesma forma, vá para o site <b></b> de Suporte da <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, insira o número de erro na caixa Pesquisar para procurar o código de erro.</span><span class="sxs-lookup"><span data-stu-id="f4b38-632">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="f4b38-633">Entre em contato com o <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Suporte Técnico da Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="f4b38-633">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-634">ID do Evento: 1120</span><span class="sxs-lookup"><span data-stu-id="f4b38-634">Event ID: 1120</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-635">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-635">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-636">
<b>MALWAREPROTECTION_THREAT_HASH</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-637">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-637">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-638">
<b>Microsoft Defender Antivírus os hashes de um recurso de ameaça.</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-638">
<b>Microsoft Defender Antivirus has deduced the hashes for a threat resource.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-639">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-639">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-640">Microsoft Defender Antivírus cliente está funcionando em um estado saudável.</span><span class="sxs-lookup"><span data-stu-id="f4b38-640">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="f4b38-641">
<dt>Versão da plataforma atual: &lt; Versão atual &gt; da plataforma</dt>
<dt>Caminho do Recurso de &lt; &gt; Ameaças:</dt>
<dt>Hashes de Caminho: &lt; Hashes &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-641">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Threat Resource Path: &lt;Path&gt;</dt>
<dt>Hashes: &lt;Hashes&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><span data-ttu-id="f4b38-642"><b>Observação: esse evento só será registrado se a seguinte política estiver definida: <b>ThreatFileHashLogging não assinado</b>.</span><span class="sxs-lookup"><span data-stu-id="f4b38-642"><b>Note: This event will only be logged if the following policy is set: <b>ThreatFileHashLogging     unsigned</b>.</span></span></div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-643">ID do Evento: 1150</span><span class="sxs-lookup"><span data-stu-id="f4b38-643">Event ID: 1150</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-644">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-644">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-645">
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-646">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-646">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-647">
<b>Se sua plataforma antimalware relata o status para uma plataforma de monitoramento, esse evento indica que a plataforma antimalware está em execução e em um estado saudável. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-647">
<b>If your antimalware platform reports status to a monitoring platform, this event indicates that the antimalware platform is running and in a healthy state. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-648">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-648">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-649">Microsoft Defender Antivírus cliente está funcionando em um estado saudável.</span><span class="sxs-lookup"><span data-stu-id="f4b38-649">Microsoft Defender Antivirus client is up and running in a healthy state.</span></span>
<dl><span data-ttu-id="f4b38-650">
<dt>Versão da plataforma: &lt; Versão de &gt; assinatura da plataforma atual:</dt>
<dt>Versão &lt; do &gt; </dt>
<dt>mecanismo de definição: &lt; Antimalware Engine &gt; versão</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-650">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-651">Ação do usuário:</span><span class="sxs-lookup"><span data-stu-id="f4b38-651">User action:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-652">Nenhuma ação é necessária.</span><span class="sxs-lookup"><span data-stu-id="f4b38-652">No action is necessary.</span></span> <span data-ttu-id="f4b38-653">O Microsoft Defender Antivírus cliente está em um estado saudável.</span><span class="sxs-lookup"><span data-stu-id="f4b38-653">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="f4b38-654">Esse evento é relatado a cada hora.</span><span class="sxs-lookup"><span data-stu-id="f4b38-654">This event is reported on an hourly basis.</span></span>
</td>
</tr>

<tr>
<th colspan="2"><span data-ttu-id="f4b38-655">ID do Evento: 1151</span><span class="sxs-lookup"><span data-stu-id="f4b38-655">Event ID: 1151</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-656">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-656">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-657">
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-658">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-658">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-659">
<b>Endpoint Protection relatório de saúde do cliente (hora em UTC)</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-659">
<b>Endpoint Protection client health report (time in UTC) </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-660">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-660">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-661">Relatório de saúde do cliente antivírus.</span><span class="sxs-lookup"><span data-stu-id="f4b38-661">Antivirus client health report.</span></span>
<dl><span data-ttu-id="f4b38-662">
<dt>Versão da plataforma: &lt; &gt;</dt>Versão do mecanismo da plataforma
<dt>atual: versão &lt; &gt; </dt>do mecanismo de inspeção em tempo real de rede da Antimalware Engine versão: Versão do mecanismo de inspeção em tempo
<dt> &lt; real &gt; </dt>de rede Versão de assinatura antivírus
<dt> &lt; &gt; Versão</dt>de assinatura
<dt>antispyware Versão da assinatura do &lt; Antispyware &gt; </dt>Versão da assinatura de Inspeção real de
<dt>Rede: Estado da versão RTP da assinatura de Inspeção em Tempo &lt; Real &gt; </dt>da Rede: Estado do OA de proteção em tempo real
<dt> &lt; &gt; (habilitado</dt>ou desabilitado) estado do OA: Estado do IOAV no acesso
<dt> &lt; &gt; (habilitado</dt>ou desabilitado) estado do IOAV: IE Download Estado BM
<dt>dos &lt; Anexos Expressos &gt; e</dt>do
<dt>Outlook: Estado BM: Estado do Monitoramento de Comportamento (Habilitado ou &lt; Desabilitado) &gt; </dt>Idade da assinatura do antivírus: Idade da assinatura do antivírus
<dt> &lt; &gt; (em dias)</dt>Idade da assinatura do Antispyware: idade da assinatura do
<dt> &lt; Antispyware &gt; (em dias)</dt>Idade da última verificação rápida: Idade da última verificação rápida
<dt> &lt; &gt; (em dias)</dt>Última idade de verificação completa: Última idade de verificação completa
<dt> &lt; &gt; (em dias)</dt>Tempo de criação da assinatura do Antivírus:
<dt>? &lt; Tempo de &gt; criação de assinatura antivírus</dt>Hora de criação da assinatura do
<dt>Antispyware: ? &lt; Tempo de criação de &gt; assinatura antispyware</dt>Última hora de início
<dt>da verificação rápida: ? &lt; Última hora de &gt; início da verificação rápida</dt>Última hora de término da verificação
<dt>rápida: ? &lt; Última &gt; hora</dt>de término da verificação rápida Última fonte de verificação rápida: Última fonte de verificação rápida (0 = verificação&#39;não foi executado, 1 = iniciado pelo
<dt> &lt; &gt; usuário, 2 =</dt>iniciado pelo sistema) Última hora de início da verificação
<dt>completa: ? &lt; Última hora de &gt; início de verificação completa</dt>Última hora de término da verificação
<dt>completa: ? &lt; Última hora de &gt; </dt>término de verificação completa Última fonte de verificação completa: Última fonte de verificação completa (0 = verificação&#39;não foi executado, 1 = iniciado pelo
<dt> &lt; &gt; usuário, 2 =</dt>sistema iniciado) Status do produto: Para solução de problemas internos 
<dt></span><span class="sxs-lookup"><span data-stu-id="f4b38-662">
<dt>Platform Version: &lt;Current platform version&gt;</dt>
<dt>Engine Version: &lt;Antimalware Engine version&gt;</dt>
<dt>Network Realtime Inspection engine version: &lt;Network Realtime Inspection engine version&gt;</dt>
<dt>Antivirus signature version: &lt;Antivirus signature version&gt;</dt>
<dt>Antispyware signature version: &lt;Antispyware signature version&gt;</dt>
<dt>Network Realtime Inspection signature version: &lt;Network Realtime Inspection signature version&gt;</dt>
<dt>RTP state: &lt;Realtime protection state&gt; (Enabled or Disabled)</dt>
<dt>OA state: &lt;On Access state&gt; (Enabled or Disabled)</dt>
<dt>IOAV state: &lt;IE Downloads and Outlook Express Attachments state&gt; (Enabled or Disabled)</dt>
<dt>BM state: &lt;Behavior Monitoring state&gt; (Enabled or Disabled)</dt>
<dt>Antivirus signature age: &lt;Antivirus signature age&gt; (in days)</dt>
<dt>Antispyware signature age: &lt;Antispyware signature age&gt; (in days)</dt>
<dt>Last quick scan age: &lt;Last quick scan age&gt; (in days)</dt>
<dt>Last full scan age: &lt;Last full scan age&gt; (in days)</dt>
<dt>Antivirus signature creation time: ?&lt;Antivirus signature creation time&gt;</dt>
<dt>Antispyware signature creation time: ?&lt;Antispyware signature creation time&gt;</dt>
<dt>Last quick scan start time: ?&lt;Last quick scan start time&gt;</dt>
<dt>Last quick scan end time: ?&lt;Last quick scan end time&gt;</dt>
<dt>Last quick scan source: &lt;Last quick scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Last full scan start time: ?&lt;Last full scan start time&gt;</dt>
<dt>Last full scan end time: ?&lt;Last full scan end time&gt;</dt>
<dt>Last full scan source: &lt;Last full scan source&gt; (0 = scan didn&#39;t run, 1 = user initiated, 2 = system initiated)</dt>
<dt>Product status: For internal troubleshooting</span></span>
</dl>
</td>
</tr>

<tr><span data-ttu-id="f4b38-663">
<th colspan="2">ID do Evento: 2000</span><span class="sxs-lookup"><span data-stu-id="f4b38-663">
<th colspan="2">Event ID: 2000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-664">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-664">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-665">
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-666">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-666">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-667">
<b>As definições antimalware atualizadas com êxito. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-667">
<b>The antimalware definitions updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-668">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-668">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-669">A versão de assinatura do antivírus foi atualizada.</span><span class="sxs-lookup"><span data-stu-id="f4b38-669">Antivirus signature version has been updated.</span></span>
<dl><span data-ttu-id="f4b38-670">
<dt>Versão de assinatura atual: &lt; Versão de &gt; assinatura atual</dt>
<dt>Versão anterior da assinatura: Versão de assinatura &lt; &gt; anterior</dt>Tipo de 
<dt> assinatura: Tipo de assinatura , por &lt; &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-670">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Previous Signature Version: &lt;Previous signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="f4b38-671">Antivírus</span><span class="sxs-lookup"><span data-stu-id="f4b38-671">Antivirus</span></span></li>
<li><span data-ttu-id="f4b38-672">Antispyware</span><span class="sxs-lookup"><span data-stu-id="f4b38-672">Antispyware</span></span></li>
<li><span data-ttu-id="f4b38-673">Antimalware</span><span class="sxs-lookup"><span data-stu-id="f4b38-673">Antimalware</span></span></li>
<li><span data-ttu-id="f4b38-674">Sistema de Inspeção de Rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-674">Network Inspection System</span></span></li>
</ul><span data-ttu-id="f4b38-675">
</dt>
<dt>Tipo de atualização: &lt; Tipo de &gt; atualização , Completo ou Delta.</dt> 
<dt>Usuário: &lt; Domínio &gt; \& lt; Versão &gt; </dt>
<dt>do Mecanismo Atual do Usuário: Versão anterior &lt; do &gt; </dt>
<dt>mecanismo do mecanismo atual: Versão anterior do &lt; mecanismo &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-675">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-676">Ação do usuário:</span><span class="sxs-lookup"><span data-stu-id="f4b38-676">User action:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-677">Nenhuma ação é necessária.</span><span class="sxs-lookup"><span data-stu-id="f4b38-677">No action is necessary.</span></span> <span data-ttu-id="f4b38-678">O Microsoft Defender Antivírus cliente está em um estado saudável.</span><span class="sxs-lookup"><span data-stu-id="f4b38-678">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="f4b38-679">Esse evento é relatado quando as assinaturas são atualizadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="f4b38-679">This event is reported when signatures are successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-680">ID do Evento: 2001</span><span class="sxs-lookup"><span data-stu-id="f4b38-680">Event ID: 2001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-681">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-681">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-682">
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-683">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-683">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-684">
<b>A atualização de inteligência de segurança falhou. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-684">
<b>The security intelligence update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-685">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-685">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-686">Microsoft Defender Antivírus encontrou um erro ao tentar atualizar assinaturas.</span><span class="sxs-lookup"><span data-stu-id="f4b38-686">Microsoft Defender Antivirus has encountered an error trying to update signatures.</span></span>
<dl><span data-ttu-id="f4b38-687">
<dt>Nova versão de inteligência de segurança: &lt; Novo número &gt; de versão</dt>
<dt>Versão anterior de inteligência de segurança: Versão &lt; &gt; anterior</dt>Fonte de 
<dt> atualização: Fonte de atualização , por &lt; &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-687">
<dt>New security intelligence version: &lt;New version number&gt;</dt>
<dt>Previous security intelligence version: &lt;Previous version&gt;</dt>
<dt>Update Source: &lt;Update source&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="f4b38-688">Pasta de atualização de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="f4b38-688">Security intelligence update folder</span></span></li>
<li><span data-ttu-id="f4b38-689">Servidor de atualização de inteligência de segurança interna</span><span class="sxs-lookup"><span data-stu-id="f4b38-689">Internal security intelligence update server</span></span></li>
<li><span data-ttu-id="f4b38-690">Microsoft Update Server</span><span class="sxs-lookup"><span data-stu-id="f4b38-690">Microsoft Update Server</span></span></li>
<li><span data-ttu-id="f4b38-691">Compartilhamento de arquivos</span><span class="sxs-lookup"><span data-stu-id="f4b38-691">File share</span></span></li>
<li><span data-ttu-id="f4b38-692">Centro de Proteção contra Malware da Microsoft (MMPC)</span><span class="sxs-lookup"><span data-stu-id="f4b38-692">Microsoft Malware Protection Center (MMPC)</span></span></li>
</ul><span data-ttu-id="f4b38-693">
</dt>
<dt>Estágio de atualização: &lt; estágio de atualização , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-693">
</dt>
<dt>Update Stage: &lt;Update stage&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="f4b38-694">Pesquisar</span><span class="sxs-lookup"><span data-stu-id="f4b38-694">Search</span></span></li>
<li><span data-ttu-id="f4b38-695">Baixar</span><span class="sxs-lookup"><span data-stu-id="f4b38-695">Download</span></span></li>
<li><span data-ttu-id="f4b38-696">Instalar</span><span class="sxs-lookup"><span data-stu-id="f4b38-696">Install</span></span></li>
</ul><span data-ttu-id="f4b38-697">
</dt>Caminho de origem: Nome do compartilhamento de arquivos para 
<dt>Unc (Convenção de Nomenização Universal), nome do servidor para Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt> 
<dt> Tipo de assinatura: &lt; Tipo de assinatura , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-697">
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="f4b38-698">Antivírus</span><span class="sxs-lookup"><span data-stu-id="f4b38-698">Antivirus</span></span></li>
<li><span data-ttu-id="f4b38-699">Antispyware</span><span class="sxs-lookup"><span data-stu-id="f4b38-699">Antispyware</span></span></li>
<li><span data-ttu-id="f4b38-700">Antimalware</span><span class="sxs-lookup"><span data-stu-id="f4b38-700">Antimalware</span></span></li>
<li><span data-ttu-id="f4b38-701">Sistema de Inspeção de Rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-701">Network Inspection System</span></span></li>
</ul><span data-ttu-id="f4b38-702">
</dt>
<dt>Tipo de atualização: &lt; Tipo de &gt; atualização , Completo ou Delta.</dt> 
<dt>Usuário: &lt; Domínio &gt; \& lt; Versão &gt; </dt>
<dt>do Mecanismo Atual do Usuário: &lt; &gt; Versão do mecanismo atual</dt>Versão anterior do mecanismo: Versão
<dt> &lt; &gt; anterior</dt>Código de erro: Código de erro Código de resultado
<dt>associado ao status da &lt; &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-702">
</dt>
<dt>Update Type: &lt;Update type&gt;, either Full or Delta.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-703">Ação do usuário:</span><span class="sxs-lookup"><span data-stu-id="f4b38-703">User action:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-704">Esse erro ocorre quando há um problema de atualização de definições.</span><span class="sxs-lookup"><span data-stu-id="f4b38-704">This error occurs when there is a problem updating definitions.</span></span>
<span data-ttu-id="f4b38-705">Para solucionar problemas deste evento:</span><span class="sxs-lookup"><span data-stu-id="f4b38-705">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="f4b38-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Atualize definições</a> e force uma nova varredura diretamente no ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="f4b38-706"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="f4b38-707">Revise as entradas no arquivo %Windir%\WindowsUpdate.log para obter mais informações sobre esse erro.</span><span class="sxs-lookup"><span data-stu-id="f4b38-707">Review the entries in the %Windir%\WindowsUpdate.log file for more information about this error.</span></span></li>
<li><span data-ttu-id="f4b38-708">Entre em contato com o <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Suporte Técnico da Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="f4b38-708">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-709">ID do Evento: 2002</span><span class="sxs-lookup"><span data-stu-id="f4b38-709">Event ID: 2002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-710">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-710">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-711">
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-712">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-712">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-713">
<b>O mecanismo antimalware atualizado com êxito. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-713">
<b>The antimalware engine updated successfully. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-714">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-714">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-715">Microsoft Defender Antivírus versão do mecanismo foi atualizada.</span><span class="sxs-lookup"><span data-stu-id="f4b38-715">Microsoft Defender Antivirus engine version has been updated.</span></span>
<dl><span data-ttu-id="f4b38-716">
<dt>Versão atual do mecanismo: &lt; Versão do &gt; mecanismo atual</dt>
<dt>Versão anterior do mecanismo: &lt; &gt; versão anterior</dt>Tipo de mecanismo: Tipo de mecanismo , mecanismo
<dt> &lt; &gt; antimalware ou mecanismo do Sistema de</dt> Inspeção de Rede. 
<dt>Usuário: &lt; Domínio &gt; \& lt; Usuário &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-716">
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-717">Ação do usuário:</span><span class="sxs-lookup"><span data-stu-id="f4b38-717">User action:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-718">Nenhuma ação é necessária.</span><span class="sxs-lookup"><span data-stu-id="f4b38-718">No action is necessary.</span></span> <span data-ttu-id="f4b38-719">O Microsoft Defender Antivírus cliente está em um estado saudável.</span><span class="sxs-lookup"><span data-stu-id="f4b38-719">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="f4b38-720">Esse evento é relatado quando o mecanismo antimalware é atualizado com êxito.</span><span class="sxs-lookup"><span data-stu-id="f4b38-720">This event is reported when the antimalware engine is successfully updated.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-721">ID do Evento: 2003</span><span class="sxs-lookup"><span data-stu-id="f4b38-721">Event ID: 2003</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-722">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-722">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-723">
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-724">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-724">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-725">
<b>A atualização do mecanismo antimalware falhou. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-725">
<b>The antimalware engine update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-726">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-726">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-727">Microsoft Defender Antivírus encontrou um erro ao tentar atualizar o mecanismo.</span><span class="sxs-lookup"><span data-stu-id="f4b38-727">Microsoft Defender Antivirus has encountered an error trying to update the engine.</span></span>
<dl><span data-ttu-id="f4b38-728">
<dt>Nova versão do mecanismo:</dt>
<dt>Versão anterior do mecanismo: &lt; &gt; versão anterior</dt>Tipo de mecanismo: Tipo de mecanismo , mecanismo
<dt> &lt; &gt; antimalware ou</dt> mecanismo do Sistema de Inspeção de Rede. 
<dt>Usuário: &lt; Domínio &gt; \& lt; Código &gt; </dt>
<dt>de Erro do Usuário: Código de erro &lt; Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-728">
<dt>New Engine Version:</dt>
<dt>Previous Engine Version: &lt;Previous engine version&gt;</dt>
<dt>Engine Type: &lt;Engine type&gt;, either antimalware engine or Network Inspection System engine.</dt>
<dt>User: &lt;Domain&gt;\&lt;User&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-729">Ação do usuário:</span><span class="sxs-lookup"><span data-stu-id="f4b38-729">User action:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-730">A Microsoft Defender Antivírus do cliente falhou.</span><span class="sxs-lookup"><span data-stu-id="f4b38-730">The Microsoft Defender Antivirus client update failed.</span></span> <span data-ttu-id="f4b38-731">Esse evento ocorre quando o cliente não consegue se atualizar.</span><span class="sxs-lookup"><span data-stu-id="f4b38-731">This event occurs when the client fails to update itself.</span></span> <span data-ttu-id="f4b38-732">Esse evento geralmente ocorre devido a uma interrupção na conectividade de rede durante uma atualização.</span><span class="sxs-lookup"><span data-stu-id="f4b38-732">This event is usually due to an interruption in network connectivity during an update.</span></span>
<span data-ttu-id="f4b38-733">Para solucionar problemas deste evento:</span><span class="sxs-lookup"><span data-stu-id="f4b38-733">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="f4b38-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Atualize definições</a> e force uma nova varredura diretamente no ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="f4b38-734"><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Update definitions</a> and force a rescan directly on the endpoint.</span></span></li>
<li><span data-ttu-id="f4b38-735">Entre em contato com o <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Suporte Técnico da Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="f4b38-735">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-736">ID do Evento: 2004</span><span class="sxs-lookup"><span data-stu-id="f4b38-736">Event ID: 2004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-737">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-737">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-738">
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-739">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-739">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-740">
<b>Houve um problema ao carregar definições de antimalware. O mecanismo antimalware tentará carregar o último bom conjunto de definições conhecido.</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-740">
<b>There was a problem loading antimalware definitions. The antimalware engine will attempt to load the last-known good set of definitions.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-741">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-741">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-742">Microsoft Defender Antivírus encontrou um erro ao tentar carregar assinaturas e tentará reverter para um conjunto conhecido de assinaturas.</span><span class="sxs-lookup"><span data-stu-id="f4b38-742">Microsoft Defender Antivirus has encountered an error trying to load signatures and will attempt reverting back to a known-good set of signatures.</span></span>
<dl><span data-ttu-id="f4b38-743">
<dt>Assinaturas Tentadas: Código</dt>
<dt>de Erro: Código de erro Código de &lt; resultado associado ao status da &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt> 
<dt>Versão de assinatura: &lt; Versão &gt; de definição</dt>
<dt>Versão do mecanismo: &lt; versão do mecanismo antimalware &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-743">
<dt>Signatures Attempted:</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Signature Version: &lt;Definition version&gt;</dt>
<dt>Engine Version: &lt;Antimalware engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-744">Ação do usuário:</span><span class="sxs-lookup"><span data-stu-id="f4b38-744">User action:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-745">O Microsoft Defender Antivírus cliente tentou baixar e instalar o arquivo de definições mais recentes e falhou.</span><span class="sxs-lookup"><span data-stu-id="f4b38-745">The Microsoft Defender Antivirus client attempted to download and install the latest definitions file and failed.</span></span> <span data-ttu-id="f4b38-746">Esse erro pode ocorrer quando o cliente encontrar um erro ao tentar carregar as definições ou se o arquivo estiver corrompido.</span><span class="sxs-lookup"><span data-stu-id="f4b38-746">This error can occur when the client encounters an error while trying to load the definitions, or if the file is corrupt.</span></span> <span data-ttu-id="f4b38-747">Microsoft Defender Antivírus tentará reverter para um conjunto conhecido de definições.</span><span class="sxs-lookup"><span data-stu-id="f4b38-747">Microsoft Defender Antivirus will attempt to revert back to a known-good set of definitions.</span></span>
<span data-ttu-id="f4b38-748">Para solucionar problemas deste evento:</span><span class="sxs-lookup"><span data-stu-id="f4b38-748">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="f4b38-749">Reinicie o computador e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="f4b38-749">Restart the computer and try again.</span></span></li>
<li><span data-ttu-id="f4b38-750">Baixe as definições mais recentes do <a href="https://aka.ms/wdsi">Inteligência de Segurança da Microsoft site</a>.</span><span class="sxs-lookup"><span data-stu-id="f4b38-750">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="f4b38-751">Observação: o tamanho do arquivo de definições baixado do site pode exceder 60 MB e não deve ser usado como uma solução de longo prazo para atualizar definições.</span><span class="sxs-lookup"><span data-stu-id="f4b38-751">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
<li><span data-ttu-id="f4b38-752">Entre em contato com o <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Suporte Técnico da Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="f4b38-752">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-753">ID do Evento: 2005</span><span class="sxs-lookup"><span data-stu-id="f4b38-753">Event ID: 2005</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-754">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-754">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-755">
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-756">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-756">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-757">
<b>O mecanismo antimalware falhou ao carregar porque a plataforma antimalware está desacorda. A plataforma antimalware carregará o último mecanismo antimalware bom conhecido e tentará atualizar.</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-757">
<b>The antimalware engine failed to load because the antimalware platform is out of date. The antimalware platform will load the last-known good antimalware engine and attempt to update.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-758">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-758">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-759">Microsoft Defender Antivírus não foi possível carregar o mecanismo antimalware porque a versão atual da plataforma não é suportada.</span><span class="sxs-lookup"><span data-stu-id="f4b38-759">Microsoft Defender Antivirus could not load antimalware engine because current platform version is not supported.</span></span> <span data-ttu-id="f4b38-760">Microsoft Defender Antivírus será revertida para o último mecanismo conhecido e uma atualização de plataforma será tentada.</span><span class="sxs-lookup"><span data-stu-id="f4b38-760">Microsoft Defender Antivirus will revert back to the last known-good engine and a platform update will be attempted.</span></span>
<dl><span data-ttu-id="f4b38-761">
<dt>Versão da plataforma atual: &lt; versão da plataforma atual&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-761">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-762">ID do Evento: 2006</span><span class="sxs-lookup"><span data-stu-id="f4b38-762">Event ID: 2006</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-763">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-763">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-764">
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-765">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-765">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-766">
<b>A atualização da plataforma falhou. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-766">
<b>The platform update failed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-767">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-767">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-768">Microsoft Defender Antivírus encontrou um erro ao tentar atualizar a plataforma.</span><span class="sxs-lookup"><span data-stu-id="f4b38-768">Microsoft Defender Antivirus has encountered an error trying to update the platform.</span></span>
<dl><span data-ttu-id="f4b38-769">
<dt>Versão da plataforma atual: &lt; Versão atual &gt; da plataforma</dt>
<dt>Código de Erro: Código de erro &lt; Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-769">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-770">ID do Evento: 2007</span><span class="sxs-lookup"><span data-stu-id="f4b38-770">Event ID: 2007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-771">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-771">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-772">
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-773">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-773">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-774">
<b>Em breve, a plataforma estará desa datada. Baixe a plataforma mais recente para manter a proteção atualizada.</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-774">
<b>The platform will soon be out of date. Download the latest platform to maintain up-to-date protection.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-775">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-775">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-776">Microsoft Defender Antivírus em breve exigirá uma versão mais recente da plataforma para dar suporte a versões futuras do mecanismo antimalware.</span><span class="sxs-lookup"><span data-stu-id="f4b38-776">Microsoft Defender Antivirus will soon require a newer platform version to support future versions of the antimalware engine.</span></span> <span data-ttu-id="f4b38-777">Baixe a plataforma Microsoft Defender Antivírus mais recente para manter o melhor nível de proteção disponível.</span><span class="sxs-lookup"><span data-stu-id="f4b38-777">Download the latest Microsoft Defender Antivirus platform to maintain the best level of protection available.</span></span>
<dl><span data-ttu-id="f4b38-778">
<dt>Versão da plataforma atual: &lt; versão da plataforma atual&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-778">
<dt>Current Platform Version: &lt;Current platform version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-779">ID do Evento: 2010</span><span class="sxs-lookup"><span data-stu-id="f4b38-779">Event ID: 2010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-780">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-780">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-781">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-782">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-782">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-783">
<b>O mecanismo antimalware usou o Serviço de Assinatura Dinâmica para obter definições adicionais. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-783">
<b>The antimalware engine used the Dynamic Signature Service to get additional definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-784">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-784">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-785">Microsoft Defender Antivírus o <i>Serviço de Assinatura Dinâmica</i> para recuperar assinaturas adicionais para ajudar a proteger seu computador.</span><span class="sxs-lookup"><span data-stu-id="f4b38-785">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to retrieve additional signatures to help protect your machine.</span></span>
<dl><span data-ttu-id="f4b38-786">
<dt>Versão de assinatura atual: &lt; Versão de &gt; assinatura atual</dt> 
<dt> Tipo de assinatura: Tipo de assinatura , &lt; por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-786">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="f4b38-787">Antivírus</span><span class="sxs-lookup"><span data-stu-id="f4b38-787">Antivirus</span></span></li>
<li><span data-ttu-id="f4b38-788">Antispyware</span><span class="sxs-lookup"><span data-stu-id="f4b38-788">Antispyware</span></span></li>
<li><span data-ttu-id="f4b38-789">Antimalware</span><span class="sxs-lookup"><span data-stu-id="f4b38-789">Antimalware</span></span></li>
<li><span data-ttu-id="f4b38-790">Sistema de Inspeção de Rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-790">Network Inspection System</span></span></li>
</ul><span data-ttu-id="f4b38-791">
</dt>
<dt>Versão atual do mecanismo: &lt; Versão atual &gt; do mecanismo</dt> 
<dt> Tipo de Assinatura Dinâmica: Tipo de assinatura &lt; dinâmica , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-791">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="f4b38-792">Versão</span><span class="sxs-lookup"><span data-stu-id="f4b38-792">Version</span></span></li>
<li><span data-ttu-id="f4b38-793">Carimbo de data/hora</span><span class="sxs-lookup"><span data-stu-id="f4b38-793">Timestamp</span></span></li>
<li><span data-ttu-id="f4b38-794">Sem limite</span><span class="sxs-lookup"><span data-stu-id="f4b38-794">No limit</span></span></li>
<li><span data-ttu-id="f4b38-795">Duration</span><span class="sxs-lookup"><span data-stu-id="f4b38-795">Duration</span></span></li>
</ul><span data-ttu-id="f4b38-796">
</dt>
<dt>Caminho de persistência: &lt; Versão &gt; </dt>
<dt>de Assinatura Dinâmica do Caminho: Número de &lt; versão &gt; </dt>Data/hora de compilação dinâmica da assinatura: Tipo de limite de persistência do
<dt> &lt; &gt; timestamp:</dt>tipo de limite de persistência , por 
<dt> &lt; &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-796">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="f4b38-797">Versão VDM</span><span class="sxs-lookup"><span data-stu-id="f4b38-797">VDM version</span></span></li>
<li><span data-ttu-id="f4b38-798">Carimbo de data/hora</span><span class="sxs-lookup"><span data-stu-id="f4b38-798">Timestamp</span></span></li>
<li><span data-ttu-id="f4b38-799">Sem limite</span><span class="sxs-lookup"><span data-stu-id="f4b38-799">No limit</span></span></li>
</ul><span data-ttu-id="f4b38-800">
</dt>
<dt>Limite de persistência: limite de persistência da assinatura do fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-800">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-801">ID do Evento: 2011</span><span class="sxs-lookup"><span data-stu-id="f4b38-801">Event ID: 2011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-802">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-802">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-803">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-804">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-804">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-805">
<b>O Serviço de Assinatura Dinâmica excluiu as definições dinâmicas desatendados. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-805">
<b>The Dynamic Signature Service deleted the out-of-date dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-806">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-806">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-807">Microsoft Defender Antivírus o <i>Serviço de Assinatura Dinâmica</i> para descartar assinaturas obsoletas.</span><span class="sxs-lookup"><span data-stu-id="f4b38-807">Microsoft Defender Antivirus used <i>Dynamic Signature Service</i> to discard obsolete signatures.</span></span>
<dl><span data-ttu-id="f4b38-808">
<dt>Versão de assinatura atual: &lt; Versão de &gt; assinatura atual</dt> 
<dt> Tipo de assinatura: Tipo de assinatura , &lt; por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-808">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="f4b38-809">Antivírus</span><span class="sxs-lookup"><span data-stu-id="f4b38-809">Antivirus</span></span></li>
<li><span data-ttu-id="f4b38-810">Antispyware</span><span class="sxs-lookup"><span data-stu-id="f4b38-810">Antispyware</span></span></li>
<li><span data-ttu-id="f4b38-811">Antimalware</span><span class="sxs-lookup"><span data-stu-id="f4b38-811">Antimalware</span></span></li>
<li><span data-ttu-id="f4b38-812">Sistema de Inspeção de Rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-812">Network Inspection System</span></span></li>
</ul><span data-ttu-id="f4b38-813">
</dt>
<dt>Versão atual do mecanismo: &lt; Versão atual &gt; do mecanismo</dt> 
<dt> Tipo de Assinatura Dinâmica: Tipo de assinatura &lt; dinâmica , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-813">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="f4b38-814">Versão</span><span class="sxs-lookup"><span data-stu-id="f4b38-814">Version</span></span></li>
<li><span data-ttu-id="f4b38-815">Carimbo de data/hora</span><span class="sxs-lookup"><span data-stu-id="f4b38-815">Timestamp</span></span></li>
<li><span data-ttu-id="f4b38-816">Sem limite</span><span class="sxs-lookup"><span data-stu-id="f4b38-816">No limit</span></span></li>
<li><span data-ttu-id="f4b38-817">Duration</span><span class="sxs-lookup"><span data-stu-id="f4b38-817">Duration</span></span></li>
</ul><span data-ttu-id="f4b38-818">
</dt>
<dt>Caminho de persistência: &lt; Versão &gt; </dt>
<dt>de Assinatura Dinâmica do Caminho: Número de &lt; versão &gt; </dt>Data/hora de compilação dinâmica da assinatura: Motivo da remoção do
<dt> &lt; &gt; timestamp:</dt>Tipo de limite de persistência: tipo de limite de
<dt></dt> 
<dt> &lt; &gt; persistência, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-818">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Removal Reason:</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="f4b38-819">Versão VDM</span><span class="sxs-lookup"><span data-stu-id="f4b38-819">VDM version</span></span></li>
<li><span data-ttu-id="f4b38-820">Carimbo de data/hora</span><span class="sxs-lookup"><span data-stu-id="f4b38-820">Timestamp</span></span></li>
<li><span data-ttu-id="f4b38-821">Sem limite</span><span class="sxs-lookup"><span data-stu-id="f4b38-821">No limit</span></span></li>
</ul><span data-ttu-id="f4b38-822">
</dt>
<dt>Limite de persistência: limite de persistência da assinatura do fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-822">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-823">Ação do usuário:</span><span class="sxs-lookup"><span data-stu-id="f4b38-823">User action:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-824">Nenhuma ação é necessária.</span><span class="sxs-lookup"><span data-stu-id="f4b38-824">No action is necessary.</span></span> <span data-ttu-id="f4b38-825">O Microsoft Defender Antivírus cliente está em um estado saudável.</span><span class="sxs-lookup"><span data-stu-id="f4b38-825">The Microsoft Defender Antivirus client is in a healthy state.</span></span> <span data-ttu-id="f4b38-826">Esse evento é relatado quando o Serviço de Assinatura Dinâmica exclui com êxito definições dinâmicas desatentadas.</span><span class="sxs-lookup"><span data-stu-id="f4b38-826">This event is reported when the Dynamic Signature Service successfully deletes out-of-date dynamic definitions.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-827">ID do Evento: 2012</span><span class="sxs-lookup"><span data-stu-id="f4b38-827">Event ID: 2012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-828">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-828">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-829">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-830">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-830">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-831">
<b>O mecanismo antimalware encontrou um erro ao tentar usar o Serviço de Assinatura Dinâmica. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-831">
<b>The antimalware engine encountered an error when trying to use the Dynamic Signature Service. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-832">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-832">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-833">Microsoft Defender Antivírus encontrou um erro ao tentar usar o <i>Serviço de Assinatura Dinâmica</i>.</span><span class="sxs-lookup"><span data-stu-id="f4b38-833">Microsoft Defender Antivirus has encountered an error trying to use <i>Dynamic Signature Service</i>.</span></span>
<dl><span data-ttu-id="f4b38-834">
<dt>Versão de assinatura atual: &lt; Versão de &gt; assinatura atual</dt> 
<dt> Tipo de assinatura: Tipo de assinatura , &lt; por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-834">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Signature Type: &lt;Signature type&gt;, for example:</span></span> <ul>
<li><span data-ttu-id="f4b38-835">Antivírus</span><span class="sxs-lookup"><span data-stu-id="f4b38-835">Antivirus</span></span></li>
<li><span data-ttu-id="f4b38-836">Antispyware</span><span class="sxs-lookup"><span data-stu-id="f4b38-836">Antispyware</span></span></li>
<li><span data-ttu-id="f4b38-837">Antimalware</span><span class="sxs-lookup"><span data-stu-id="f4b38-837">Antimalware</span></span></li>
<li><span data-ttu-id="f4b38-838">Sistema de Inspeção de Rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-838">Network Inspection System</span></span></li>
</ul><span data-ttu-id="f4b38-839">
</dt>
<dt>Versão atual do mecanismo: &lt; Versão atual &gt; código de erro</dt>
<dt>do mecanismo: Código de erro &lt; Código de resultado associado ao status da &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt> 
<dt> Tipo de Assinatura Dinâmica: &lt; Tipo de assinatura dinâmica , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-839">
</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Dynamic Signature Type: &lt;Dynamic signature type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="f4b38-840">Versão</span><span class="sxs-lookup"><span data-stu-id="f4b38-840">Version</span></span></li>
<li><span data-ttu-id="f4b38-841">Carimbo de data/hora</span><span class="sxs-lookup"><span data-stu-id="f4b38-841">Timestamp</span></span></li>
<li><span data-ttu-id="f4b38-842">Sem limite</span><span class="sxs-lookup"><span data-stu-id="f4b38-842">No limit</span></span></li>
<li><span data-ttu-id="f4b38-843">Duration</span><span class="sxs-lookup"><span data-stu-id="f4b38-843">Duration</span></span></li>
</ul><span data-ttu-id="f4b38-844">
</dt>
<dt>Caminho de persistência: &lt; Versão &gt; </dt>
<dt>de Assinatura Dinâmica do Caminho: Número de &lt; versão &gt; </dt>Data/hora de compilação dinâmica da assinatura: Tipo de limite de persistência do
<dt> &lt; &gt; timestamp:</dt>tipo de limite de persistência , por 
<dt> &lt; &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-844">
</dt>
<dt>Persistence Path: &lt;Path&gt;</dt>
<dt>Dynamic Signature Version: &lt;Version number&gt;</dt>
<dt>Dynamic Signature Compilation Timestamp: &lt;Timestamp&gt;</dt>
<dt>Persistence Limit Type: &lt;Persistence limit type&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="f4b38-845">Versão VDM</span><span class="sxs-lookup"><span data-stu-id="f4b38-845">VDM version</span></span></li>
<li><span data-ttu-id="f4b38-846">Carimbo de data/hora</span><span class="sxs-lookup"><span data-stu-id="f4b38-846">Timestamp</span></span></li>
<li><span data-ttu-id="f4b38-847">Sem limite</span><span class="sxs-lookup"><span data-stu-id="f4b38-847">No limit</span></span></li>
</ul><span data-ttu-id="f4b38-848">
</dt>
<dt>Limite de persistência: limite de persistência da assinatura do fastpath.</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-848">
</dt>
<dt>Persistence Limit: Persistence limit of the fastpath signature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-849">Ação do usuário:</span><span class="sxs-lookup"><span data-stu-id="f4b38-849">User action:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-850">Verifique suas configurações de conectividade com a Internet.</span><span class="sxs-lookup"><span data-stu-id="f4b38-850">Check your Internet connectivity settings.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-851">ID do Evento: 2013</span><span class="sxs-lookup"><span data-stu-id="f4b38-851">Event ID: 2013</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-852">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-852">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-853">
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-854">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-854">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-855">
<b>O Serviço de Assinatura Dinâmica excluiu todas as definições dinâmicas. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-855">
<b>The Dynamic Signature Service deleted all dynamic definitions. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-856">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-856">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-857">Microsoft Defender Antivírus todas as assinaturas <i>do Serviço</i> de Assinatura Dinâmica.</span><span class="sxs-lookup"><span data-stu-id="f4b38-857">Microsoft Defender Antivirus discarded all <i>Dynamic Signature Service</i> signatures.</span></span>
<dl><span data-ttu-id="f4b38-858">
<dt>Versão de assinatura atual: &lt; Versão de assinatura atual&gt;</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-858">
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-859">ID do Evento: 2020</span><span class="sxs-lookup"><span data-stu-id="f4b38-859">Event ID: 2020</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-860">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-860">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-861">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-862">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-862">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-863">
<b>O mecanismo antimalware baixou um arquivo limpo. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-863">
<b>The antimalware engine downloaded a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-864">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-864">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-865">Microsoft Defender Antivírus baixou um arquivo limpo.</span><span class="sxs-lookup"><span data-stu-id="f4b38-865">Microsoft Defender Antivirus downloaded a clean file.</span></span>
<dl><span data-ttu-id="f4b38-866">
<dt>Nomedo arquivo: &lt; Nome do &gt; arquivo Nome do arquivo.</dt> 
<dt>Versão de assinatura atual: &lt; Versão atual &gt; do</dt>
<dt>mecanismo de assinatura atual: versão atual do &lt; mecanismo &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-866">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-867">ID do Evento: 2021</span><span class="sxs-lookup"><span data-stu-id="f4b38-867">Event ID: 2021</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-868">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-868">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-869">
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-870">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-870">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-871">
<b>O mecanismo antimalware falhou ao baixar um arquivo limpo. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-871">
<b>The antimalware engine failed to download a clean file. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-872">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-872">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-873">Microsoft Defender Antivírus encontrou um erro ao tentar baixar um arquivo limpo.</span><span class="sxs-lookup"><span data-stu-id="f4b38-873">Microsoft Defender Antivirus has encountered an error trying to download a clean file.</span></span>
<dl><span data-ttu-id="f4b38-874">
<dt>Nomedo arquivo: &lt; Nome do &gt; arquivo Nome do arquivo.</dt> 
<dt>Versão de assinatura atual: &lt; Versão atual &gt; do</dt>
<dt>mecanismo de assinatura atual: &lt; &gt; Versão atual</dt>do mecanismo Código de erro: Código de erro Código de resultado associado ao status da
<dt> &lt; &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-874">
<dt>Filename: &lt;File name&gt; Name of the file.</dt>
<dt>Current Signature Version: &lt;Current signature version&gt;</dt>
<dt>Current Engine Version: &lt;Current engine version&gt;</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-875">Ação do usuário:</span><span class="sxs-lookup"><span data-stu-id="f4b38-875">User action:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-876">Verifique suas configurações de conectividade com a Internet.</span><span class="sxs-lookup"><span data-stu-id="f4b38-876">Check your Internet connectivity settings.</span></span>
<span data-ttu-id="f4b38-877">O Microsoft Defender Antivírus cliente encontrou um erro ao usar o Serviço de Assinatura Dinâmica para baixar as definições mais recentes para uma ameaça específica.</span><span class="sxs-lookup"><span data-stu-id="f4b38-877">The Microsoft Defender Antivirus client encountered an error when using the Dynamic Signature Service to download the latest definitions to a specific threat.</span></span> <span data-ttu-id="f4b38-878">Esse erro provavelmente é causado por um problema de conectividade de rede.</span><span class="sxs-lookup"><span data-stu-id="f4b38-878">This error is likely caused by a network connectivity issue.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-879">ID do Evento: 2030</span><span class="sxs-lookup"><span data-stu-id="f4b38-879">Event ID: 2030</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-880">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-880">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-881">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-882">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-882">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-883">
<b>O mecanismo antimalware foi baixado e está configurado para ser executado offline na próxima reinicialização do sistema.</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-883">
<b>The antimalware engine was downloaded and is configured to run offline on the next system restart.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-884">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-884">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-885">Microsoft Defender Antivírus baixado e configurado antivírus offline para ser executado na próxima reinicialização.</span><span class="sxs-lookup"><span data-stu-id="f4b38-885">Microsoft Defender Antivirus downloaded and configured offline antivirus to run on the next reboot.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-886">ID do Evento: 2031</span><span class="sxs-lookup"><span data-stu-id="f4b38-886">Event ID: 2031</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-887">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-887">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-888">
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-889">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-889">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-890">
<b>O mecanismo antimalware não pôde baixar e configurar uma verificação offline.</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-890">
<b>The antimalware engine was unable to download and configure an offline scan.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-891">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-891">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-892">Microsoft Defender Antivírus encontrou um erro ao tentar baixar e configurar antivírus offline.</span><span class="sxs-lookup"><span data-stu-id="f4b38-892">Microsoft Defender Antivirus has encountered an error trying to download and configure offline antivirus.</span></span>
<dl><span data-ttu-id="f4b38-893">
<dt>Código de Erro: &lt; Código de erro &gt; Código de resultado associado ao status da ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-893">
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-894">ID do Evento: 2040</span><span class="sxs-lookup"><span data-stu-id="f4b38-894">Event ID: 2040</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-895">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-895">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-896">
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-897">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-897">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-898">
<b>O suporte a antimalware para esta versão do sistema operacional terminará em breve. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-898">
<b>Antimalware support for this operating system version will soon end. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-899">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-899">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-900">O suporte para seu sistema operacional expirará em breve.</span><span class="sxs-lookup"><span data-stu-id="f4b38-900">The support for your operating system will expire shortly.</span></span> <span data-ttu-id="f4b38-901">Executar Microsoft Defender Antivírus em um sistema operacional sem suporte não é uma solução adequada para proteger contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="f4b38-901">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-902">ID do Evento: 2041</span><span class="sxs-lookup"><span data-stu-id="f4b38-902">Event ID: 2041</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-903">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-903">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-904">
<b>MALWAREPROTECTION_OS_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-905">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-905">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-906">
<b>O suporte a antimalware para este sistema operacional terminou. Você deve atualizar o sistema operacional para suporte contínuo. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-906">
<b>Antimalware support for this operating system has ended. You must upgrade the operating system for continued support. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-907">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-907">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-908">O suporte para seu sistema operacional expirou.</span><span class="sxs-lookup"><span data-stu-id="f4b38-908">The support for your operating system has expired.</span></span> <span data-ttu-id="f4b38-909">Executar Microsoft Defender Antivírus em um sistema operacional sem suporte não é uma solução adequada para proteger contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="f4b38-909">Running Microsoft Defender Antivirus on an out of support operating system is not an adequate solution to protect against threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-910">ID do Evento: 2042</span><span class="sxs-lookup"><span data-stu-id="f4b38-910">Event ID: 2042</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-911">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-911">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-912">
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-913">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-913">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-914">
<b>O mecanismo antimalware não dá mais suporte a esse sistema operacional e não está mais protegendo seu sistema contra malware. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-914">
<b>The antimalware engine no longer supports this operating system, and is no longer protecting your system from malware. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-915">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-915">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-916">O suporte para seu sistema operacional expirou.</span><span class="sxs-lookup"><span data-stu-id="f4b38-916">The support for your operating system has expired.</span></span> <span data-ttu-id="f4b38-917">Microsoft Defender Antivírus não é mais suportado em seu sistema operacional, parou de funcionar e não está protegendo contra ameaças de malware.</span><span class="sxs-lookup"><span data-stu-id="f4b38-917">Microsoft Defender Antivirus is no longer supported on your operating system, has stopped functioning, and is not protecting against malware threats.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-918">ID do Evento: 3002</span><span class="sxs-lookup"><span data-stu-id="f4b38-918">Event ID: 3002</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-919">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-919">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-920">
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-921">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-921">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-922">
<b>A proteção em tempo real encontrou um erro e falhou.</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-922">
<b>Real-time protection encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-923">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-923">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-924">Microsoft Defender Antivírus Real-Time proteção encontrou um erro e falhou.</span><span class="sxs-lookup"><span data-stu-id="f4b38-924">Microsoft Defender Antivirus Real-Time Protection feature has encountered an error and failed.</span></span>
<dl><span data-ttu-id="f4b38-925">
<dt>Recurso: &lt; Recurso , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-925">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="f4b38-926">No Access</span><span class="sxs-lookup"><span data-stu-id="f4b38-926">On Access</span></span></li>
<li><span data-ttu-id="f4b38-927">Downloads do Internet Explorer e anexos do Microsoft Outlook Express</span><span class="sxs-lookup"><span data-stu-id="f4b38-927">Internet Explorer downloads and Microsoft Outlook Express attachments</span></span></li>
<li><span data-ttu-id="f4b38-928">Monitoramento de comportamento</span><span class="sxs-lookup"><span data-stu-id="f4b38-928">Behavior monitoring</span></span></li>
<li><span data-ttu-id="f4b38-929">Sistema de Inspeção de Rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-929">Network Inspection System</span></span></li>
</ul><span data-ttu-id="f4b38-930">
</dt>
<dt>Código de Erro: &lt; Código de erro &gt; Código de resultado associado ao status da ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt> 
<dt>Motivo: o motivo Microsoft Defender Antivírus proteção em tempo real reiniciou um recurso.</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-930">
</dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-931">Ação do usuário:</span><span class="sxs-lookup"><span data-stu-id="f4b38-931">User action:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-932">Você deve reiniciar o sistema e executar uma verificação completa porque&#39;é possível que o sistema não estivesse protegido por algum tempo.</span><span class="sxs-lookup"><span data-stu-id="f4b38-932">You should restart the system then run a full scan because it&#39;s possible the system was not protected for some time.</span></span>
<span data-ttu-id="f4b38-933">O Microsoft Defender Antivírus cliente&#39;o recurso de proteção em tempo real encontrou um erro porque um dos serviços falhou ao iniciar.</span><span class="sxs-lookup"><span data-stu-id="f4b38-933">The Microsoft Defender Antivirus client&#39;s real-time protection feature encountered an error because one of the services failed to start.</span></span> <span data-ttu-id="f4b38-934">Se for seguida por uma ID de evento 3007, a falha foi temporária e o cliente antimalware foi recuperado da falha.</span><span class="sxs-lookup"><span data-stu-id="f4b38-934">If it is followed by a 3007 event ID, the failure was temporary and the antimalware client recovered from the failure.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-935">ID do Evento: 3007</span><span class="sxs-lookup"><span data-stu-id="f4b38-935">Event ID: 3007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-936">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-936">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-937">
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-938">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-938">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-939">
<b>Proteção em tempo real recuperada de uma falha. Recomendamos executar uma verificação completa do sistema quando você vir esse erro. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-939">
<b>Real-time protection recovered from a failure. We recommend running a full system scan when you see this error. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-940">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-940">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-941">Microsoft Defender Antivírus A Proteção em tempo real reinicie um recurso.</span><span class="sxs-lookup"><span data-stu-id="f4b38-941">Microsoft Defender Antivirus Real-time Protection has restarted a feature.</span></span> <span data-ttu-id="f4b38-942">É recomendável executar uma verificação completa do sistema para detectar todos os itens que podem ter sido faltados enquanto esse agente estava inotivo.</span><span class="sxs-lookup"><span data-stu-id="f4b38-942">It is recommended that you run a full system scan to detect any items that may have been missed while this agent was down.</span></span>
<dl><span data-ttu-id="f4b38-943">
<dt>Recurso: &lt; Recurso , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-943">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="f4b38-944">No Access</span><span class="sxs-lookup"><span data-stu-id="f4b38-944">On Access</span></span></li>
<li><span data-ttu-id="f4b38-945">Downloads e anexos do IE Outlook Express</span><span class="sxs-lookup"><span data-stu-id="f4b38-945">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="f4b38-946">Monitoramento de comportamento</span><span class="sxs-lookup"><span data-stu-id="f4b38-946">Behavior monitoring</span></span></li>
<li><span data-ttu-id="f4b38-947">Sistema de Inspeção de Rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-947">Network Inspection System</span></span></li>
</ul><span data-ttu-id="f4b38-948">
</dt>
<dt>Motivo: o motivo pelo qual Microsoft Defender Antivírus proteção em tempo real reiniciou um recurso.</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-948">
</dt>
<dt>Reason: The reason Microsoft Defender Antivirus real-time protection has restarted a feature.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-949">Ação do usuário:</span><span class="sxs-lookup"><span data-stu-id="f4b38-949">User action:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-950">O recurso de proteção em tempo real foi reiniciado.</span><span class="sxs-lookup"><span data-stu-id="f4b38-950">The real-time protection feature has restarted.</span></span> <span data-ttu-id="f4b38-951">Se esse evento acontecer novamente, entre em contato <a href="https://go.microsoft.com/fwlink/?LinkId=215491">com o Suporte Técnico da Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="f4b38-951">If this event happens again, contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-952">ID do Evento: 5000</span><span class="sxs-lookup"><span data-stu-id="f4b38-952">Event ID: 5000</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-953">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-953">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-954">
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-955">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-955">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-956">
<b>A proteção em tempo real está habilitada. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-956">
<b>Real-time protection is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-957">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-957">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-958">Microsoft Defender Antivírus verificação de proteção em tempo real para malware e outros softwares potencialmente indesejados foram habilitados.</span><span class="sxs-lookup"><span data-stu-id="f4b38-958">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-959">ID do Evento: 5001</span><span class="sxs-lookup"><span data-stu-id="f4b38-959">Event ID: 5001</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-960">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-960">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-961">
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-962">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-962">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-963">
<b>A proteção em tempo real está desabilitada. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-963">
<b>Real-time protection is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-964">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-964">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-965">Microsoft Defender Antivírus verificação de proteção em tempo real para malware e outros softwares potencialmente indesejados foram desabilitados.</span><span class="sxs-lookup"><span data-stu-id="f4b38-965">Microsoft Defender Antivirus real-time protection scanning for malware and other potentially unwanted software was disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-966">ID do Evento: 5004</span><span class="sxs-lookup"><span data-stu-id="f4b38-966">Event ID: 5004</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-967">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-967">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-968">
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-969">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-969">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-970">
<b>A configuração de proteção em tempo real foi alterada. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-970">
<b>The real-time protection configuration changed. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-971">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-971">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-972">Microsoft Defender Antivírus configuração de recurso de proteção em tempo real foi alterada.</span><span class="sxs-lookup"><span data-stu-id="f4b38-972">Microsoft Defender Antivirus real-time protection feature configuration has changed.</span></span>
<dl><span data-ttu-id="f4b38-973">
<dt>Recurso: &lt; Recurso , por &gt; exemplo:</span><span class="sxs-lookup"><span data-stu-id="f4b38-973">
<dt>Feature: &lt;Feature&gt;, for example:</span></span>
<ul>
<li><span data-ttu-id="f4b38-974">No Access</span><span class="sxs-lookup"><span data-stu-id="f4b38-974">On Access</span></span></li>
<li><span data-ttu-id="f4b38-975">Downloads e anexos do IE Outlook Express</span><span class="sxs-lookup"><span data-stu-id="f4b38-975">IE downloads and Outlook Express attachments</span></span></li>
<li><span data-ttu-id="f4b38-976">Monitoramento de comportamento</span><span class="sxs-lookup"><span data-stu-id="f4b38-976">Behavior monitoring</span></span></li>
<li><span data-ttu-id="f4b38-977">Sistema de Inspeção de Rede</span><span class="sxs-lookup"><span data-stu-id="f4b38-977">Network Inspection System</span></span></li>
</ul><span data-ttu-id="f4b38-978">
</dt>
<dt>Configuração: </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-978">
</dt>
<dt>Configuration: </dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-979">ID do Evento: 5007</span><span class="sxs-lookup"><span data-stu-id="f4b38-979">Event ID: 5007</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-980">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-980">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-981">
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-982">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-982">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-983">
<b>A configuração da plataforma antimalware foi alterada.</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-983">
<b>The antimalware platform configuration changed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-984">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-984">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-985">Microsoft Defender Antivírus configuração foi alterada.</span><span class="sxs-lookup"><span data-stu-id="f4b38-985">Microsoft Defender Antivirus configuration has changed.</span></span> <span data-ttu-id="f4b38-986">Se esse for um evento inesperado, você deve revisar as configurações, pois isso pode ser o resultado de malware.</span><span class="sxs-lookup"><span data-stu-id="f4b38-986">If this is an unexpected event, you should review the settings as this may be the result of malware.</span></span>
<dl><span data-ttu-id="f4b38-987">
<dt>Valor antigo: &lt; Número de valor antigo &gt; Valor de configuração do antivírus antigo.</dt> 
<dt>Novo valor: &lt; Novo número de valor &gt; Novo valor de configuração do antivírus.</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-987">
<dt>Old value: &lt;Old value number&gt; Old antivirus configuration value.</dt>
<dt>New value: &lt;New value number&gt; New antivirus configuration value.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-988">ID do Evento: 5008</span><span class="sxs-lookup"><span data-stu-id="f4b38-988">Event ID: 5008</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-989">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-989">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-990">
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-991">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-991">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-992">
<b>O mecanismo antimalware encontrou um erro e falhou.</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-992">
<b>The antimalware engine encountered an error and failed.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-993">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-993">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-994">Microsoft Defender Antivírus mecanismo foi encerrado devido a um erro inesperado.</span><span class="sxs-lookup"><span data-stu-id="f4b38-994">Microsoft Defender Antivirus engine has been terminated due to an unexpected error.</span></span>
<dl><span data-ttu-id="f4b38-995">
<dt>Tipo de falha: &lt; Tipo de &gt; falha , por exemplo: Crash ou Hang</dt>Exception
<dt>Code: Código de &lt; &gt; erro</dt>
<dt>Recurso: &lt; Recurso &gt; </dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-995">
<dt>Failure Type: &lt;Failure type&gt;, for example: Crash or Hang</dt>
<dt>Exception Code: &lt;Error code&gt;</dt>
<dt>Resource: &lt;Resource&gt;</dt>
</span></span></dl>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-996">Ação do usuário:</span><span class="sxs-lookup"><span data-stu-id="f4b38-996">User action:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-997">Para solucionar problemas deste evento:</span><span class="sxs-lookup"><span data-stu-id="f4b38-997">To troubleshoot this event:</span></span><ol>
<li><span data-ttu-id="f4b38-998">Tente reiniciar o serviço.</span><span class="sxs-lookup"><span data-stu-id="f4b38-998">Try to restart the service.</span></span><ul>
<li><span data-ttu-id="f4b38-999">Para antimalware, antivírus e spyware, em um prompt de comando elevado, digite <b>net stop msmpsvc</b>e digite <b>net start msmpsvc</b> para reiniciar o mecanismo antimalware.</span><span class="sxs-lookup"><span data-stu-id="f4b38-999">For antimalware, antivirus and spyware, at an elevated command prompt, type <b>net stop msmpsvc</b>, and then type <b>net start msmpsvc</b> to restart the antimalware engine.</span></span></li>
<li><span data-ttu-id="f4b38-1000">Para o <i></i> <i>Sistema</i>de Inspeção de Rede , em um prompt de comando elevado, digite net start <b>nissrv</b>e digite net start <b>nissrv</b> para reiniciar o mecanismo do Sistema de Inspeção de Rede usando o arquivo NiSSRV.exe.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1000">For the <i>Network Inspection System</i>, at an elevated command prompt, type <b>net start nissrv</b>, and then type <b>net start nissrv</b> to restart the <i>Network Inspection System</i> engine by using the NiSSRV.exe file.</span></span>
</li>
</ul>
</li>
<li><span data-ttu-id="f4b38-1001">Se ele falhar da mesma forma, procure o código de erro acessando o <b></b> Site de Suporte da <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a> e inserindo o número de erro na caixa Pesquisa e contate o Suporte Técnico da <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1001">If it fails in the same way, look up the error code by accessing the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support Site</a>  and entering the error number in the <b>Search</b> box, and contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span></li>
</ol>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1002">Ação do usuário:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1002">User action:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-1003">O Microsoft Defender Antivírus do cliente foi interrompido devido a um erro inesperado.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1003">The Microsoft Defender Antivirus client engine stopped due to an unexpected error.</span></span>
<span data-ttu-id="f4b38-1004">Para solucionar problemas deste evento:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1004">To troubleshoot this event:</span></span>
<ol>
<li><span data-ttu-id="f4b38-1005">Execute a verificação novamente.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1005">Run the scan again.</span></span></li>
<li><span data-ttu-id="f4b38-1006">Se ele falhar da mesma forma, vá para o site <b></b> de Suporte da <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>, insira o número de erro na caixa Pesquisar para procurar o código de erro.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1006">If it fails in the same way, go to the <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft Support site</a>, enter the error number in the <b>Search</b> box to look for the error code.</span></span></li>
<li><span data-ttu-id="f4b38-1007">Entre em contato com o <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Suporte Técnico da Microsoft</a>.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1007">Contact <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft Technical Support</a>.</span></span>
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-1008">ID do Evento: 5009</span><span class="sxs-lookup"><span data-stu-id="f4b38-1008">Event ID: 5009</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-1009">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1009">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1010">
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1011">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1011">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-1012">
<b>A verificação de malware e outros softwares potencialmente indesejados está habilitada. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1012">
<b>Scanning for malware and other potentially unwanted software is enabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1013">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1013">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-1014">Microsoft Defender Antivírus verificação de malware e outros softwares potencialmente indesejados foram habilitados.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1014">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software has been enabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-1015">ID do Evento: 5010</span><span class="sxs-lookup"><span data-stu-id="f4b38-1015">Event ID: 5010</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-1016">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1016">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1017">
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1018">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1018">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-1019">
<b>A verificação de malware e outros softwares potencialmente indesejados está desabilitada.</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1019">
<b>Scanning for malware and other potentially unwanted software is disabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1020">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1020">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-1021">Microsoft Defender Antivírus verificação de malware e outros softwares potencialmente indesejados está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1021">Microsoft Defender Antivirus scanning for malware and other potentially unwanted software is disabled.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-1022">ID do Evento: 5011</span><span class="sxs-lookup"><span data-stu-id="f4b38-1022">Event ID: 5011</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-1023">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1023">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1024">
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1025">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1025">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-1026">
<b>A verificação de vírus está habilitada.</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1026">
<b>Scanning for viruses is enabled.</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1027">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1027">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-1028">Microsoft Defender Antivírus verificação de vírus foi habilitada.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1028">Microsoft Defender Antivirus scanning for viruses has been enabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-1029">ID do Evento: 5012</span><span class="sxs-lookup"><span data-stu-id="f4b38-1029">Event ID: 5012</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-1030">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1030">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1031">
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1032">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1032">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-1033">
<b>A verificação de vírus está desabilitada. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1033">
<b>Scanning for viruses is disabled. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1034">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1034">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-1035">Microsoft Defender Antivírus verificação de vírus está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1035">Microsoft Defender Antivirus scanning for viruses is disabled.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-1036">ID do Evento: 5100</span><span class="sxs-lookup"><span data-stu-id="f4b38-1036">Event ID: 5100</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-1037">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1037">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1038">
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1039">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1039">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-1040">
<b>A plataforma antimalware expirará em breve. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1040">
<b>The antimalware platform will expire soon. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1041">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1041">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-1042">Microsoft Defender Antivírus entrou em um período de carência e expirará em breve.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1042">Microsoft Defender Antivirus has entered a grace period and will soon expire.</span></span> <span data-ttu-id="f4b38-1043">Após a expiração, este programa desabilitará a proteção contra vírus, spyware e outros softwares potencialmente indesejados.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1043">After expiration, this program will disable protection against viruses, spyware, and other potentially unwanted software.</span></span>
<dl><span data-ttu-id="f4b38-1044">
<dt>Motivo da expiração: o motivo Microsoft Defender Antivírus expirará.</dt> 
<dt>Data de expiração: a data Microsoft Defender Antivírus expirará.</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1044">
<dt>Expiration Reason: The reason Microsoft Defender Antivirus will expire.</dt>
<dt>Expiration Date: The date Microsoft Defender Antivirus will expire.</dt>
</span></span></dl>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-1045">ID do Evento: 5101</span><span class="sxs-lookup"><span data-stu-id="f4b38-1045">Event ID: 5101</span></span></th>
</tr>
<tr><td>
<span data-ttu-id="f4b38-1046">Nome simbólico:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1046">Symbolic name:</span></span>
</td>
<td ><span data-ttu-id="f4b38-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1047">
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1048">Mensagem:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1048">Message:</span></span>
</td>
<td ><span data-ttu-id="f4b38-1049">
<b>A plataforma antimalware expirou. </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1049">
<b>The antimalware platform is expired. </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1050">Descrição:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1050">Description:</span></span>
</td>
<td >
<span data-ttu-id="f4b38-1051">Microsoft Defender Antivírus período de carência expirou.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1051">Microsoft Defender Antivirus grace period has expired.</span></span> <span data-ttu-id="f4b38-1052">A proteção contra vírus, spyware e outros softwares potencialmente indesejados está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1052">Protection against viruses, spyware, and other potentially unwanted software is disabled.</span></span>
<dl><span data-ttu-id="f4b38-1053">
<dt>Motivo da expiração:</dt>
<dt>Data de expiração: Código </dt>de erro: Código de erro Código de resultado associado ao status da 
<dt> &lt; &gt; ameaça. Valores HRESULT padrão.</dt> 
<dt>Descrição do erro: &lt; Descrição do &gt; erro Descrição do erro.</dt>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1053">
<dt>Expiration Reason:</dt>
<dt>Expiration Date: </dt>
<dt>Error Code: &lt;Error code&gt; Result code associated with threat status. Standard HRESULT values.</dt>
<dt>Error Description: &lt;Error description&gt; Description of the error. </dt>
</span></span></dl>
</td>
</tr><span data-ttu-id="f4b38-1054">
</table>

<a id="error-codes"></a>
##Microsoft Defender Antivírus de erro do cliente Se Microsoft Defender Antivírus tiver problemas, ele geralmente lhe dará um código de erro para ajudá-lo a solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1054">
</table>

<a id="error-codes"></a>
## Microsoft Defender Antivirus client error codes If Microsoft Defender Antivirus experiences any issues it will usually give you an error code to help you troubleshoot the issue.</span></span> <span data-ttu-id="f4b38-1055">Na maioria das vezes, um erro significa que houve um problema ao instalar uma atualização.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1055">Most often an error means there was a problem installing an update.</span></span>
<span data-ttu-id="f4b38-1056">Esta seção fornece as informações a seguir sobre Microsoft Defender Antivírus erros do cliente.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1056">This section provides the following information about Microsoft Defender Antivirus client errors.</span></span>
<span data-ttu-id="f4b38-1057">-   O código de -   erro O motivo possível para o erro Conselhos sobre o que fazer -   agora</span><span class="sxs-lookup"><span data-stu-id="f4b38-1057">-   The error code -   The possible reason for the error -   Advice on what to do now</span></span>

<span data-ttu-id="f4b38-1058">Use as informações nessas tabelas para ajudar a solucionar problemas Microsoft Defender Antivírus códigos de erro.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1058">Use the information in these tables to help troubleshoot Microsoft Defender Antivirus error codes.</span></span>


<table> 
<tr>
<th colspan="2"><span data-ttu-id="f4b38-1059">Código de erro: 0x80508007</span><span class="sxs-lookup"><span data-stu-id="f4b38-1059">Error code: 0x80508007</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="f4b38-1060">Mensagem</span><span class="sxs-lookup"><span data-stu-id="f4b38-1060">Message</span></span></td>
<td><span data-ttu-id="f4b38-1061">
<b>ERR_MP_NO_MEMORY </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1061">
<b>ERR_MP_NO_MEMORY </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1062">Possível motivo</span><span class="sxs-lookup"><span data-stu-id="f4b38-1062">Possible reason</span></span>
</td>
<td>
<span data-ttu-id="f4b38-1063">Esse erro indica que você pode ter ficar sem memória.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1063">This error indicates that you might have run out of memory.</span></span> 
</td>
</tr>
<tr>
<td><span data-ttu-id="f4b38-1064">Resolução</span><span class="sxs-lookup"><span data-stu-id="f4b38-1064">Resolution</span></span></td>
<td>
<ol>
<li><span data-ttu-id="f4b38-1065">Verifique a memória disponível em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1065">Check the available memory on your device.</span></span></li>
<li><span data-ttu-id="f4b38-1066">Feche todos os aplicativos nãousados que estão sendo executados para liberar memória em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1066">Close any unused applications that are running to free up memory on your device.</span></span></li>
<li><span data-ttu-id="f4b38-1067">Reinicie o dispositivo e execute a verificação novamente.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1067">Restart the device and run the scan again.</span></span> 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-1068">Código de erro: 0x8050800C</span><span class="sxs-lookup"><span data-stu-id="f4b38-1068">Error code: 0x8050800C</span></span></th>
</tr><tr><td><span data-ttu-id="f4b38-1069">Mensagem</span><span class="sxs-lookup"><span data-stu-id="f4b38-1069">Message</span></span></td>
<td><span data-ttu-id="f4b38-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1070"><b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td></tr><tr><td><span data-ttu-id="f4b38-1071">Possível motivo</span><span class="sxs-lookup"><span data-stu-id="f4b38-1071">Possible reason</span></span></td>
<td>
<span data-ttu-id="f4b38-1072">Esse erro indica que pode haver um problema com seu produto de segurança.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1072">This error indicates that there might be a problem with your security product.</span></span>
</td>
</tr><tr><td><span data-ttu-id="f4b38-1073">Resolução</span><span class="sxs-lookup"><span data-stu-id="f4b38-1073">Resolution</span></span></td><td>
<ol>
<li><span data-ttu-id="f4b38-1074">Atualize as definições.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1074">Update the definitions.</span></span> <span data-ttu-id="f4b38-1075">Qualquer um deles:</span><span class="sxs-lookup"><span data-stu-id="f4b38-1075">Either:</span></span><ol>
<li><span data-ttu-id="f4b38-1076">Clique no <b>botão Atualizar definições</b> na guia <b>Atualizar</b> em Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1076">Click the <b>Update definitions</b> button on the <b>Update</b> tab in Microsoft Defender Antivirus.</span></span> <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/><span data-ttu-id="f4b38-1077">Ou</span><span class="sxs-lookup"><span data-stu-id="f4b38-1077">Or,</span></span>
</li>
<li><span data-ttu-id="f4b38-1078">Baixe as definições mais recentes do <a href="https://aka.ms/wdsi">Inteligência de Segurança da Microsoft site</a>.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1078">Download the latest definitions from the <a href="https://aka.ms/wdsi">Microsoft Security Intelligence site</a>.</span></span>
<span data-ttu-id="f4b38-1079">Observação: o tamanho do arquivo de definições baixado do site pode exceder 60 MB e não deve ser usado como uma solução de longo prazo para atualizar definições.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1079">Note: The size of the definitions file downloaded from the site can exceed 60 MB and should not be used as a long-term solution for updating definitions.</span></span>
</li>
</ol>
</li>
<li><span data-ttu-id="f4b38-1080">Execute uma verificação completa.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1080">Run a full scan.</span></span>
</li>
<li><span data-ttu-id="f4b38-1081">Reinicie o dispositivo e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1081">Restart the device and try again.</span></span></li>
</ol>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-1082">Código de erro: 0x80508020</span><span class="sxs-lookup"><span data-stu-id="f4b38-1082">Error code: 0x80508020</span></span></th>
</tr><tr><td><span data-ttu-id="f4b38-1083">Mensagem</span><span class="sxs-lookup"><span data-stu-id="f4b38-1083">Message</span></span></td>
<td><span data-ttu-id="f4b38-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1084"><b>ERR_MP_BAD_CONFIGURATION </b>
</span></span></td></tr><tr><td><span data-ttu-id="f4b38-1085">Possível motivo</span><span class="sxs-lookup"><span data-stu-id="f4b38-1085">Possible reason</span></span></td>
<td>
<span data-ttu-id="f4b38-1086">Esse erro indica que pode haver um erro de configuração do mecanismo; normalmente, isso está relacionado a dados de entrada que não permitem que o mecanismo funcione corretamente.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1086">This error indicates that there might be an engine configuration error; commonly, this is related to input data that does not allow the engine to function properly.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-1087">Código de erro: 0x805080211</span><span class="sxs-lookup"><span data-stu-id="f4b38-1087">Error code: 0x805080211</span></span>
</th>
</tr><tr><td><span data-ttu-id="f4b38-1088">Mensagem</span><span class="sxs-lookup"><span data-stu-id="f4b38-1088">Message</span></span></td>
<td><span data-ttu-id="f4b38-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1089"><b>ERR_MP_QUARANTINE_FAILED </b>
</span></span></td></tr><tr><td><span data-ttu-id="f4b38-1090">Possível motivo</span><span class="sxs-lookup"><span data-stu-id="f4b38-1090">Possible reason</span></span></td>
<td>
<span data-ttu-id="f4b38-1091">Esse erro indica que Microsoft Defender Antivírus falhou ao colocar em quarentena uma ameaça.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1091">This error indicates that Microsoft Defender Antivirus failed to quarantine a threat.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-1092">Código de erro: 0x80508022</span><span class="sxs-lookup"><span data-stu-id="f4b38-1092">Error code: 0x80508022</span></span>
</th>
</tr><tr><td><span data-ttu-id="f4b38-1093">Mensagem</span><span class="sxs-lookup"><span data-stu-id="f4b38-1093">Message</span></span></td>
<td><span data-ttu-id="f4b38-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1094"><b>ERR_MP_REBOOT_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="f4b38-1095">Possível motivo</span><span class="sxs-lookup"><span data-stu-id="f4b38-1095">Possible reason</span></span></td>
<td>
<span data-ttu-id="f4b38-1096">Esse erro indica que uma reinicialização é necessária para concluir a remoção de ameaças.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1096">This error indicates that a reboot is required to complete threat removal.</span></span> 
</td>
</tr>
<tr>
<th colspan="2">
<span data-ttu-id="f4b38-1097">0x80508023</span><span class="sxs-lookup"><span data-stu-id="f4b38-1097">0x80508023</span></span>
</th>
</tr><tr><td><span data-ttu-id="f4b38-1098">Mensagem</span><span class="sxs-lookup"><span data-stu-id="f4b38-1098">Message</span></span></td>
<td><span data-ttu-id="f4b38-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1099"><b>ERR_MP_THREAT_NOT_FOUND </b>
</span></span></td></tr><tr><td><span data-ttu-id="f4b38-1100">Possível motivo</span><span class="sxs-lookup"><span data-stu-id="f4b38-1100">Possible reason</span></span></td>
<td>
<span data-ttu-id="f4b38-1101">Esse erro indica que a ameaça pode não estar mais presente na mídia, ou o malware pode estar impedindo a verificação do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1101">This error indicates that the threat might no longer be present on the media, or malware might be stopping you from scanning your device.</span></span> 
</tr><tr><td><span data-ttu-id="f4b38-1102">Resolução</span><span class="sxs-lookup"><span data-stu-id="f4b38-1102">Resolution</span></span>
</td>
<td>
<span data-ttu-id="f4b38-1103">Execute o <a href="https://www.microsoft.com/security/scanner/default.aspx">Verificador de Segurança da Microsoft</a> atualize seu software de segurança e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1103">Run the <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> then update your security software and try again.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-1104">Código de erro: 0x80508024</span><span class="sxs-lookup"><span data-stu-id="f4b38-1104">Error code: 0x80508024</span></span> </th></tr>
<tr>
<td><span data-ttu-id="f4b38-1105">Mensagem</span><span class="sxs-lookup"><span data-stu-id="f4b38-1105">Message</span></span></td>
<td><span data-ttu-id="f4b38-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1106"><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="f4b38-1107">Possível motivo</span><span class="sxs-lookup"><span data-stu-id="f4b38-1107">Possible reason</span></span></td>
<td>
<span data-ttu-id="f4b38-1108">Esse erro indica que uma verificação completa do sistema pode ser necessária.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1108">This error indicates that a full system scan might be required.</span></span> 
</td></tr>
<tr>
<td><span data-ttu-id="f4b38-1109">Resolução</span><span class="sxs-lookup"><span data-stu-id="f4b38-1109">Resolution</span></span></td><td>
<span data-ttu-id="f4b38-1110">Execute uma verificação completa do sistema.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1110">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-1111">Código de erro: 0x80508025</span><span class="sxs-lookup"><span data-stu-id="f4b38-1111">Error code: 0x80508025</span></span>
</th>
</tr><tr><td><span data-ttu-id="f4b38-1112">Mensagem</span><span class="sxs-lookup"><span data-stu-id="f4b38-1112">Message</span></span></td>
<td><span data-ttu-id="f4b38-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1113"><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="f4b38-1114">Possível motivo</span><span class="sxs-lookup"><span data-stu-id="f4b38-1114">Possible reason</span></span></td>
<td>
<span data-ttu-id="f4b38-1115">Esse erro indica que as etapas manuais são necessárias para concluir a remoção de ameaças.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1115">This error indicates that manual steps are required to complete threat removal.</span></span> 
</td></tr><tr><td><span data-ttu-id="f4b38-1116">Resolução</span><span class="sxs-lookup"><span data-stu-id="f4b38-1116">Resolution</span></span></td><td>
<span data-ttu-id="f4b38-1117">Siga as etapas de correção manuais descritas na <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Enciclopédia de Proteção contra Malware da Microsoft.</a></span><span class="sxs-lookup"><span data-stu-id="f4b38-1117">Follow the manual remediation steps outlined in the <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">Microsoft Malware Protection Encyclopedia</a>.</span></span> <span data-ttu-id="f4b38-1118">Você pode encontrar um link específico de ameaça no histórico de eventos.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1118">You can find a threat-specific link in the event history.</span></span><br/></td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-1119">Código de erro: 0x80508026</span><span class="sxs-lookup"><span data-stu-id="f4b38-1119">Error code: 0x80508026</span></span>
</th>
</tr><tr><td><span data-ttu-id="f4b38-1120">Mensagem</span><span class="sxs-lookup"><span data-stu-id="f4b38-1120">Message</span></span></td>
<td><span data-ttu-id="f4b38-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1121"><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</span></span></td></tr><tr><td><span data-ttu-id="f4b38-1122">Possível motivo</span><span class="sxs-lookup"><span data-stu-id="f4b38-1122">Possible reason</span></span></td>
<td>
<span data-ttu-id="f4b38-1123">Esse erro indica que a remoção dentro do tipo contêiner pode não ser suportada.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1123">This error indicates that removal inside the container type might not be not supported.</span></span> 
</td></tr><tr><td><span data-ttu-id="f4b38-1124">Resolução</span><span class="sxs-lookup"><span data-stu-id="f4b38-1124">Resolution</span></span></td><td>
<span data-ttu-id="f4b38-1125">Microsoft Defender Antivírus é capaz de remediar ameaças detectadas dentro do arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1125">Microsoft Defender Antivirus is not able to remediate threats detected inside the archive.</span></span> <span data-ttu-id="f4b38-1126">Considere remover manualmente os recursos detectados.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1126">Consider manually removing the detected resources.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-1127">Código de erro: 0x80508027</span><span class="sxs-lookup"><span data-stu-id="f4b38-1127">Error code: 0x80508027</span></span>
</th>
</tr><tr><td><span data-ttu-id="f4b38-1128">Mensagem</span><span class="sxs-lookup"><span data-stu-id="f4b38-1128">Message</span></span></td>
<td><span data-ttu-id="f4b38-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1129"><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</span></span></td></tr><tr><td><span data-ttu-id="f4b38-1130">Possível motivo</span><span class="sxs-lookup"><span data-stu-id="f4b38-1130">Possible reason</span></span></td>
<td>
<span data-ttu-id="f4b38-1131">Esse erro indica que a remoção de ameaças baixas e médias pode ser desabilitada.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1131">This error indicates that removal of low and medium threats might be disabled.</span></span> 
</td></tr><tr><td><span data-ttu-id="f4b38-1132">Resolução</span><span class="sxs-lookup"><span data-stu-id="f4b38-1132">Resolution</span></span></td><td>
<span data-ttu-id="f4b38-1133">Verifique as ameaças detectadas e resolva-as conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1133">Check the detected threats and resolve them as required.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-1134">Código de erro: 0x80508029</span><span class="sxs-lookup"><span data-stu-id="f4b38-1134">Error code: 0x80508029</span></span>
</th>
</tr><tr><td><span data-ttu-id="f4b38-1135">Mensagem</span><span class="sxs-lookup"><span data-stu-id="f4b38-1135">Message</span></span></td>
<td><span data-ttu-id="f4b38-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1136"><b>ERROR_MP_RESCAN_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="f4b38-1137">Possível motivo</span><span class="sxs-lookup"><span data-stu-id="f4b38-1137">Possible reason</span></span></td>
<td>
<span data-ttu-id="f4b38-1138">Esse erro indica que uma nova verificação da ameaça é necessária.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1138">This error indicates a rescan of the threat is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="f4b38-1139">Resolução</span><span class="sxs-lookup"><span data-stu-id="f4b38-1139">Resolution</span></span></td><td>
<span data-ttu-id="f4b38-1140">Execute uma verificação completa do sistema.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1140">Run a full system scan.</span></span> 
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-1141">Código de erro: 0x80508030</span><span class="sxs-lookup"><span data-stu-id="f4b38-1141">Error code: 0x80508030</span></span>
</th>
</tr><tr><td><span data-ttu-id="f4b38-1142">Mensagem</span><span class="sxs-lookup"><span data-stu-id="f4b38-1142">Message</span></span></td>
<td><span data-ttu-id="f4b38-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1143"><b>ERROR_MP_CALLISTO_REQUIRED </b>
</span></span></td></tr><tr><td><span data-ttu-id="f4b38-1144">Possível motivo</span><span class="sxs-lookup"><span data-stu-id="f4b38-1144">Possible reason</span></span></td>
<td>
<span data-ttu-id="f4b38-1145">Esse erro indica que uma verificação offline é necessária.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1145">This error indicates that an offline scan is required.</span></span> 
</td></tr><tr><td><span data-ttu-id="f4b38-1146">Resolução</span><span class="sxs-lookup"><span data-stu-id="f4b38-1146">Resolution</span></span></td><td>
<span data-ttu-id="f4b38-1147">Execute o Microsoft Defender Antivírus offline.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1147">Run offline Microsoft Defender Antivirus.</span></span> <span data-ttu-id="f4b38-1148">Você pode ler sobre como fazer isso no <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">artigo Microsoft Defender Antivírus offline.</a></span><span class="sxs-lookup"><span data-stu-id="f4b38-1148">You can read about how to do this in the <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">offline Microsoft Defender Antivirus article</a>.</span></span>
</td>
</tr>
<tr>
<th colspan="2"><span data-ttu-id="f4b38-1149">Código de erro: 0x80508031</span><span class="sxs-lookup"><span data-stu-id="f4b38-1149">Error code: 0x80508031</span></span>
</th>
</tr><tr><td><span data-ttu-id="f4b38-1150">Mensagem</span><span class="sxs-lookup"><span data-stu-id="f4b38-1150">Message</span></span></td>
<td><span data-ttu-id="f4b38-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span><span class="sxs-lookup"><span data-stu-id="f4b38-1151"><b>ERROR_MP_PLATFORM_OUTDATED</span></span><br/></b>
</td></tr><tr><td><span data-ttu-id="f4b38-1152">Possível motivo</span><span class="sxs-lookup"><span data-stu-id="f4b38-1152">Possible reason</span></span></td>
<td>
<span data-ttu-id="f4b38-1153">Esse erro indica que Microsoft Defender Antivírus não dá suporte à versão atual da plataforma e exige uma nova versão da plataforma.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1153">This error indicates that Microsoft Defender Antivirus does not support the current version of the platform and requires a new version of the platform.</span></span> 
</td></tr><tr><td><span data-ttu-id="f4b38-1154">Resolução</span><span class="sxs-lookup"><span data-stu-id="f4b38-1154">Resolution</span></span></td><td>
<span data-ttu-id="f4b38-1155">Você só pode usar Microsoft Defender Antivírus em Windows 10.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1155">You can only use Microsoft Defender Antivirus in Windows 10.</span></span> <span data-ttu-id="f4b38-1156">Para Windows 8, Windows 7 e Windows Vista, você pode usar <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1156">For Windows 8, Windows 7 and Windows Vista, you can use <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.</span></span><br/></td>
</tr>
</table><span data-ttu-id="f4b38-1157">

<a id="internal-error-codes"></a>Os códigos de erro a seguir são usados durante testes internos de Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1157">

<a id="internal-error-codes"></a> The following error codes are used during internal testing of Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="f4b38-1158">Se você vir esses erros, [](manage-updates-baselines-microsoft-defender-antivirus.md) poderá tentar atualizar definições e forçar uma nova varredura diretamente no ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1158">If you see these errors, you can try to [update definitions](manage-updates-baselines-microsoft-defender-antivirus.md) and force a rescan directly on the endpoint.</span></span>


<table> 
<tr>
<th colspan="3"><span data-ttu-id="f4b38-1159">Códigos de erro internos</span><span class="sxs-lookup"><span data-stu-id="f4b38-1159">Internal error codes</span></span></th>
</tr>
<tr>
<th><span data-ttu-id="f4b38-1160"><b>Código de erro</b></span><span class="sxs-lookup"><span data-stu-id="f4b38-1160"><b>Error code</b></span></span></th>
<th><span data-ttu-id="f4b38-1161">Mensagem exibida</span><span class="sxs-lookup"><span data-stu-id="f4b38-1161">Message displayed</span></span></th>
<th><span data-ttu-id="f4b38-1162">Possível motivo para erro e resolução</span><span class="sxs-lookup"><span data-stu-id="f4b38-1162">Possible reason for error and resolution</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1163">0x80501004</span><span class="sxs-lookup"><span data-stu-id="f4b38-1163">0x80501004</span></span>
</td>
<td><span data-ttu-id="f4b38-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1164">
<b>ERROR_MP_NO_INTERNET_CONN </b>
</span></span></td>
<td>
<span data-ttu-id="f4b38-1165">Verifique sua conexão com a Internet e execute a verificação novamente.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1165">Check your Internet connection, then run the scan again.</span></span>
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1166">0x80501000</span><span class="sxs-lookup"><span data-stu-id="f4b38-1166">0x80501000</span></span>
</td>
<td><span data-ttu-id="f4b38-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E</span><span class="sxs-lookup"><span data-stu-id="f4b38-1167">
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b>E</span></span>
</td>
<td rowspan="34">
<span data-ttu-id="f4b38-1168">Este é um erro interno.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1168">This is an internal error.</span></span> <span data-ttu-id="f4b38-1169">A causa não está claramente definida.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1169">The cause is not clearly defined.</span></span>
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1170">0x80501001</span><span class="sxs-lookup"><span data-stu-id="f4b38-1170">0x80501001</span></span>
</td>
<td><span data-ttu-id="f4b38-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1171">
<b>ERROR_MP_ACTIONS_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1172">0x80501002</span><span class="sxs-lookup"><span data-stu-id="f4b38-1172">0x80501002</span></span>
</td>
<td><span data-ttu-id="f4b38-1173">
<b>ERROR_MP_NOENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1173">
<b>ERROR_MP_NOENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1174">0x80501003</span><span class="sxs-lookup"><span data-stu-id="f4b38-1174">0x80501003</span></span>
</td>
<td><span data-ttu-id="f4b38-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1175">
<b>ERROR_MP_ACTIVE_THREATS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1176">0x805011011</span><span class="sxs-lookup"><span data-stu-id="f4b38-1176">0x805011011</span></span>
</td>
<td><span data-ttu-id="f4b38-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1177">
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1178">0x80501101</span><span class="sxs-lookup"><span data-stu-id="f4b38-1178">0x80501101</span></span>
</td>
<td><span data-ttu-id="f4b38-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1179">
<b>ERROR_LUA_CANCELLATION </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1180">0x80501102</span><span class="sxs-lookup"><span data-stu-id="f4b38-1180">0x80501102</span></span>
</td>
<td><span data-ttu-id="f4b38-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1181">
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1182">0x80501103</span><span class="sxs-lookup"><span data-stu-id="f4b38-1182">0x80501103</span></span>
</td>
<td><span data-ttu-id="f4b38-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1183">
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1184">0x80501104</span><span class="sxs-lookup"><span data-stu-id="f4b38-1184">0x80501104</span></span>
</td>
<td><span data-ttu-id="f4b38-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1185">
<b>MP_ERROR_CODE_CANCELLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1186">0x80501105</span><span class="sxs-lookup"><span data-stu-id="f4b38-1186">0x80501105</span></span>
</td>
<td><span data-ttu-id="f4b38-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1187">
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1188">0x80501106</span><span class="sxs-lookup"><span data-stu-id="f4b38-1188">0x80501106</span></span>
</td>
<td><span data-ttu-id="f4b38-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1189">
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1190">0x80501107</span><span class="sxs-lookup"><span data-stu-id="f4b38-1190">0x80501107</span></span>
</td>
<td><span data-ttu-id="f4b38-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1191">
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1192">0x80501108</span><span class="sxs-lookup"><span data-stu-id="f4b38-1192">0x80501108</span></span>
</td>
<td><span data-ttu-id="f4b38-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1193">
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1194">0x80508001</span><span class="sxs-lookup"><span data-stu-id="f4b38-1194">0x80508001</span></span>
</td>
<td><span data-ttu-id="f4b38-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1195">
<b>ERR_MP_BAD_INIT_MODULES</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1196">0x80508002</span><span class="sxs-lookup"><span data-stu-id="f4b38-1196">0x80508002</span></span>
</td>
<td><span data-ttu-id="f4b38-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1197">
<b>ERR_MP_BAD_DATABASE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1198">0x80508004</span><span class="sxs-lookup"><span data-stu-id="f4b38-1198">0x80508004</span></span>
</td>
<td><span data-ttu-id="f4b38-1199">
<b>ERR_MP_BAD_UFS </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1199">
<b>ERR_MP_BAD_UFS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1200">0x8050800C</span><span class="sxs-lookup"><span data-stu-id="f4b38-1200">0x8050800C</span></span>
</td>
<td><span data-ttu-id="f4b38-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1201">
<b>ERR_MP_BAD_INPUT_DATA</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1202">0x8050800D</span><span class="sxs-lookup"><span data-stu-id="f4b38-1202">0x8050800D</span></span>
</td>
<td><span data-ttu-id="f4b38-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1203">
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1204">0x8050800E</span><span class="sxs-lookup"><span data-stu-id="f4b38-1204">0x8050800E</span></span>
</td>
<td><span data-ttu-id="f4b38-1205">
<b>ERR_MP_OBSOLETE</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1205">
<b>ERR_MP_OBSOLETE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1206">0x8050800F</span><span class="sxs-lookup"><span data-stu-id="f4b38-1206">0x8050800F</span></span>
</td>
<td><span data-ttu-id="f4b38-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1207">
<b>ERR_MP_NOT_SUPPORTED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1208">0x8050800F 0x80508010</span><span class="sxs-lookup"><span data-stu-id="f4b38-1208">0x8050800F 0x80508010</span></span>
</td>
<td><span data-ttu-id="f4b38-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1209">
<b>ERR_MP_NO_MORE_ITEMS </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1210">0x80508011</span><span class="sxs-lookup"><span data-stu-id="f4b38-1210">0x80508011</span></span>
</td>
<td><span data-ttu-id="f4b38-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1211">
<b>ERR_MP_DUPLICATE_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1212">0x80508012</span><span class="sxs-lookup"><span data-stu-id="f4b38-1212">0x80508012</span></span>
</td>
<td><span data-ttu-id="f4b38-1213">
<b>ERR_MP_BAD_SCANID</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1213">
<b>ERR_MP_BAD_SCANID</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1214">0x80508013</span><span class="sxs-lookup"><span data-stu-id="f4b38-1214">0x80508013</span></span>
</td>
<td><span data-ttu-id="f4b38-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1215">
<b>ERR_MP_BAD_USERDB_VERSION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1216">0x80508014</span><span class="sxs-lookup"><span data-stu-id="f4b38-1216">0x80508014</span></span>
</td>
<td><span data-ttu-id="f4b38-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1217">
<b>ERR_MP_RESTORE_FAILED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1218">0x80508016</span><span class="sxs-lookup"><span data-stu-id="f4b38-1218">0x80508016</span></span>
</td>
<td><span data-ttu-id="f4b38-1219">
<b>ERR_MP_BAD_ACTION</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1219">
<b>ERR_MP_BAD_ACTION</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1220">0x80508019</span><span class="sxs-lookup"><span data-stu-id="f4b38-1220">0x80508019</span></span>
</td>
<td><span data-ttu-id="f4b38-1221">
<b>ERR_MP_NOT_FOUND</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1221">
<b>ERR_MP_NOT_FOUND</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1222">0x80509001</span><span class="sxs-lookup"><span data-stu-id="f4b38-1222">0x80509001</span></span>
</td>
<td><span data-ttu-id="f4b38-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1223">
<b>ERR_RELO_BAD_EHANDLE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1224">0x80509003</span><span class="sxs-lookup"><span data-stu-id="f4b38-1224">0x80509003</span></span>
</td>
<td><span data-ttu-id="f4b38-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1225">
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1226">0x8050A001</span><span class="sxs-lookup"><span data-stu-id="f4b38-1226">0x8050A001</span></span>
</td>
<td><span data-ttu-id="f4b38-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1227">
<b>ERR_MP_BADDB_OPEN</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1228">0x8050A002</span><span class="sxs-lookup"><span data-stu-id="f4b38-1228">0x8050A002</span></span>
</td>
<td><span data-ttu-id="f4b38-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1229">
<b>ERR_MP_BADDB_HEADER</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1230">0x8050A003</span><span class="sxs-lookup"><span data-stu-id="f4b38-1230">0x8050A003</span></span>
</td>
<td><span data-ttu-id="f4b38-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1231">
<b>ERR_MP_BADDB_OLDENGINE</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1232">0x8050A004</span><span class="sxs-lookup"><span data-stu-id="f4b38-1232">0x8050A004</span></span>
</td>
<td><span data-ttu-id="f4b38-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1233">
<b>ERR_MP_BADDB_CONTENT </b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1234">0x8050A005</span><span class="sxs-lookup"><span data-stu-id="f4b38-1234">0x8050A005</span></span>
</td>
<td><span data-ttu-id="f4b38-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1235">
<b>ERR_MP_BADDB_NOTSIGNED</b>
</span></span></td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1236">0x8050801</span><span class="sxs-lookup"><span data-stu-id="f4b38-1236">0x8050801</span></span>
</td>
<td><span data-ttu-id="f4b38-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1237">
<b>ERR_MP_REMOVE_FAILED</b>
</span></span></td>
<td>
<span data-ttu-id="f4b38-1238">Este é um erro interno.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1238">This is an internal error.</span></span> <span data-ttu-id="f4b38-1239">Ele pode ser acionado quando a remoção de malware não for bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1239">It might be triggered when malware removal is not successful.</span></span> 
</td>
</tr>
<tr>
<td>
<span data-ttu-id="f4b38-1240">0x80508018</span><span class="sxs-lookup"><span data-stu-id="f4b38-1240">0x80508018</span></span>
</td>
<td><span data-ttu-id="f4b38-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span><span class="sxs-lookup"><span data-stu-id="f4b38-1241">
<b>ERR_MP_SCAN_ABORTED </b>
</span></span></td>
<td>
<span data-ttu-id="f4b38-1242">Este é um erro interno.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1242">This is an internal error.</span></span> <span data-ttu-id="f4b38-1243">Ele pode ter disparado quando uma verificação não é concluída.</span><span class="sxs-lookup"><span data-stu-id="f4b38-1243">It might have triggered when a scan fails to complete.</span></span> 
</td>
</tr>
</table>

## <a name="related-topics"></a><span data-ttu-id="f4b38-1244">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f4b38-1244">Related topics</span></span>

- [<span data-ttu-id="f4b38-1245">Relatório sobre Microsoft Defender Antivírus proteção</span><span class="sxs-lookup"><span data-stu-id="f4b38-1245">Report on Microsoft Defender Antivirus protection</span></span>](report-monitor-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f4b38-1246">Microsoft Defender Antivírus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="f4b38-1246">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)