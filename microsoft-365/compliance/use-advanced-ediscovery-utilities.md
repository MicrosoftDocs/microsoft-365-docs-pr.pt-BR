---
title: Usar utilitários da Descoberta Eletrônica Avançada
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 66ca9993-75f4-4724-aea2-5a0719b660c1
description: Saiba mais sobre os utilitários em descoberta eletrônica avançada, incluindo log de caso, dados claros, erros de processo, modificação de relevância e análise de transparência.
ms.openlocfilehash: 4283bc7bea509c8a01fb45c433964230a5256f8a
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936614"
---
# <a name="use-advanced-ediscovery-classic-utilities"></a><span data-ttu-id="ebec0-103">Usar utilitários da Descoberta Eletrônica Avançada (clássica)</span><span class="sxs-lookup"><span data-stu-id="ebec0-103">Use Advanced eDiscovery (classic) utilities</span></span>

> [!NOTE]
> <span data-ttu-id="ebec0-p101">A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="ebec0-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="ebec0-106">Os utilitários que são exibidos e estão disponíveis na descoberta eletrônica avançada dependem de contexto e funções de usuário.</span><span class="sxs-lookup"><span data-stu-id="ebec0-106">The utilities that are displayed and available in Advanced eDiscovery depend on context and user roles.</span></span>
  
## <a name="case-log"></a><span data-ttu-id="ebec0-107">Log de caso</span><span class="sxs-lookup"><span data-stu-id="ebec0-107">Case log</span></span>

<span data-ttu-id="ebec0-108">O log de caso fornece uma lista detalhada das atividades de processamento do aplicativo, que podem ser usadas para controlar, solucionar problemas e para endereçar erros e avisos.</span><span class="sxs-lookup"><span data-stu-id="ebec0-108">The Case log provides a detailed list of application processing activities, which can be used for tracking, troubleshooting, and for addressing errors and warnings.</span></span> <span data-ttu-id="ebec0-109">O log pode ser gerado e armazenado localmente no host ou servidor ou enviado diretamente para um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="ebec0-109">The log can be generated and stored locally on the host or server, or sent directly to an email address.</span></span>
  
<span data-ttu-id="ebec0-110">O arquivo de log também pode ser baixado no computador do cliente.</span><span class="sxs-lookup"><span data-stu-id="ebec0-110">The log file can also be downloaded to the client's computer.</span></span> <span data-ttu-id="ebec0-111">A opção de download do cliente pode ser habilitada ou desabilitada de acordo com a configuração e a função do usuário.</span><span class="sxs-lookup"><span data-stu-id="ebec0-111">The client download option may be enabled or disabled according to configuration and user role.</span></span>
  
1. <span data-ttu-id="ebec0-112">Na barra de menus, clique no ícone **engrenagem** .</span><span class="sxs-lookup"><span data-stu-id="ebec0-112">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="ebec0-113">Na guia \*\* \> utilitários de configurações e utilitários\*\* , selecione \*\* \> a configuração de log de caso\*\*.</span><span class="sxs-lookup"><span data-stu-id="ebec0-113">In the **Settings and utilities \> Utilities** tab, select **Case log \> Setup**.</span></span>
    
3. <span data-ttu-id="ebec0-114">Selecione o **nível de log** da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="ebec0-114">Select the **Log level** as follows:</span></span> 
    
  - <span data-ttu-id="ebec0-115">**Padrão**: inclui os dados de log básicos.</span><span class="sxs-lookup"><span data-stu-id="ebec0-115">**Standard**: Includes the basic log data.</span></span> <span data-ttu-id="ebec0-116">Essa opção geralmente é necessária para monitoramento e deve ser usada, a menos que o contrário seja recomendado.</span><span class="sxs-lookup"><span data-stu-id="ebec0-116">This option is usually necessary for monitoring, and should be used unless recommended otherwise.</span></span>
    
  - <span data-ttu-id="ebec0-117">**Mínimo**: usado em casos muito grandes e retorna apenas os dados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="ebec0-117">**Minimal**: Used for very large cases, and returns only the latest data.</span></span>
    
4. <span data-ttu-id="ebec0-118">Clique em **executar log de caso**.</span><span class="sxs-lookup"><span data-stu-id="ebec0-118">Click **Run Case log**.</span></span> <span data-ttu-id="ebec0-119">O log é gerado e o caminho é exibido.</span><span class="sxs-lookup"><span data-stu-id="ebec0-119">The log is generated and path is displayed.</span></span> <span data-ttu-id="ebec0-120">As informações de progresso da tarefa para a tarefa atual e a última são exibidas no painel de status da tarefa.</span><span class="sxs-lookup"><span data-stu-id="ebec0-120">The task progress information for the current and last task is displayed in the Task status pane.</span></span>
    
## <a name="clear-data"></a><span data-ttu-id="ebec0-121">Limpar dados</span><span class="sxs-lookup"><span data-stu-id="ebec0-121">Clear data</span></span>

<span data-ttu-id="ebec0-122">Se for necessário excluir ou reinicializar os dados da ocorrência, a instância do banco de dados deverá ser inicializada.</span><span class="sxs-lookup"><span data-stu-id="ebec0-122">If it is necessary to delete or reinitialize case data, the database instance must be initialized.</span></span> <span data-ttu-id="ebec0-123">O utilitário limpar dados exclui todas as entradas especificadas do banco de dados de casos, arquivos de texto, pastas de casos e resultados acumulados.</span><span class="sxs-lookup"><span data-stu-id="ebec0-123">The Clear data utility deletes all specified entries from the case database, text files, case folder, and accumulated results.</span></span> <span data-ttu-id="ebec0-124">A função só pode ser executada por um administrador.</span><span class="sxs-lookup"><span data-stu-id="ebec0-124">The function can only be performed by an administrator.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ebec0-125">Esta ação não é reversível e desmarcará toda a marcação e análise de relevância executada pelo especialista.</span><span class="sxs-lookup"><span data-stu-id="ebec0-125">This action is not reversible and will clear all Relevance tagging and analysis performed by the expert.</span></span> <span data-ttu-id="ebec0-126">Salve um backup de dados, se necessário.</span><span class="sxs-lookup"><span data-stu-id="ebec0-126">Save a backup of data, if necessary.</span></span> <span data-ttu-id="ebec0-127">Use essa opção com extrema cautela.</span><span class="sxs-lookup"><span data-stu-id="ebec0-127">Use this option with extreme care.</span></span> <span data-ttu-id="ebec0-128">Excluir arquivos marcados e classificados pode afetar os resultados de relevância.</span><span class="sxs-lookup"><span data-stu-id="ebec0-128">Deleting tagged and ranked files can impact the Relevance results.</span></span> 
  
1. <span data-ttu-id="ebec0-129">Na barra de menus, clique no ícone **engrenagem** .</span><span class="sxs-lookup"><span data-stu-id="ebec0-129">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="ebec0-130">Na guia \*\* \> utilitários de configurações e utilitários\*\* , selecione **limpar \> configuração de dados**.</span><span class="sxs-lookup"><span data-stu-id="ebec0-130">In the **Settings and utilities \> Utilities** tab, select **Clear data \> Setup**.</span></span>
    
3. <span data-ttu-id="ebec0-131">Selecione uma opção para que as informações sejam inicializadas:</span><span class="sxs-lookup"><span data-stu-id="ebec0-131">Select an option for the information to initialize:</span></span>
    
  - <span data-ttu-id="ebec0-132">**Relevância**: exclui todo o trabalho realizado de relevância, incluindo a definição de cargas e Associação de arquivos a serem carregados.</span><span class="sxs-lookup"><span data-stu-id="ebec0-132">**Relevance**: Deletes all work done in Relevance, including definition of loads and association of files to loads.</span></span> <span data-ttu-id="ebec0-133">Ele exclui todos os exemplos e marcação.</span><span class="sxs-lookup"><span data-stu-id="ebec0-133">It deletes all samples and tagging.</span></span>
    
  - <span data-ttu-id="ebec0-134">**Duplicatas e threads de email**: exclui todas as informações de análise de quase duplicatas e threads de email.</span><span class="sxs-lookup"><span data-stu-id="ebec0-134">**Near-duplicates and email threads**: Deletes all analysis information of near-duplicates and email threads.</span></span>
    
  - <span data-ttu-id="ebec0-135">**Themes**: exclui os dados relacionados a temas.</span><span class="sxs-lookup"><span data-stu-id="ebec0-135">**Themes**: Deletes themes-related data.</span></span>
    
  - <span data-ttu-id="ebec0-136">**Export History**: Exclui informações de histórico de lotes de exportação.</span><span class="sxs-lookup"><span data-stu-id="ebec0-136">**Export history**: Deletes history information of Export batches.</span></span>
    
4. <span data-ttu-id="ebec0-137">Clique em **limpar dados**.</span><span class="sxs-lookup"><span data-stu-id="ebec0-137">Click **Clear data**.</span></span> <span data-ttu-id="ebec0-138">Os dados de caso são limpos.</span><span class="sxs-lookup"><span data-stu-id="ebec0-138">The case data is cleared.</span></span> <span data-ttu-id="ebec0-139">As informações de progresso da tarefa para a tarefa atual e a última são exibidas no painel de **status da tarefa** .</span><span class="sxs-lookup"><span data-stu-id="ebec0-139">The task progress information for the current and last task is displayed in the **Task status** pane.</span></span> 
    
## <a name="modify-relevance"></a><span data-ttu-id="ebec0-140">Modificar relevância</span><span class="sxs-lookup"><span data-stu-id="ebec0-140">Modify Relevance</span></span>

<span data-ttu-id="ebec0-141">Esta seção descreve como ignorar ou reverter uma amostra de relevância.</span><span class="sxs-lookup"><span data-stu-id="ebec0-141">This section describes how to skip or roll back a Relevance sample.</span></span>
  
1. <span data-ttu-id="ebec0-142">Na barra de menus, clique no ícone **engrenagem** .</span><span class="sxs-lookup"><span data-stu-id="ebec0-142">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="ebec0-143">Na guia \*\* \> utilitários de configurações e utilitários\*\* , selecione **Modificar relevância**.</span><span class="sxs-lookup"><span data-stu-id="ebec0-143">In the **Settings and utilities \> Utilities** tab, select **Modify relevance**.</span></span>
    
3. <span data-ttu-id="ebec0-144">Selecione dentre as opções:</span><span class="sxs-lookup"><span data-stu-id="ebec0-144">Select from the options:</span></span> 
    
  - <span data-ttu-id="ebec0-145">**Ignorar amostra atual-para usuário atual**: isso marcará, como **ignorar**, todos os arquivos não marcados no exemplo de caso aberto do usuário que está executando o utilitário.</span><span class="sxs-lookup"><span data-stu-id="ebec0-145">**Skip current sample - for current user**: This will tag, as **Skip**, all untagged files in the open case sample of the user running the utility.</span></span> <span data-ttu-id="ebec0-146">O processamento de relevância não será executado em arquivos marcados como **Skip**.</span><span class="sxs-lookup"><span data-stu-id="ebec0-146">Relevance processing will not be performed on files tagged as **Skip**.</span></span>
    
  - <span data-ttu-id="ebec0-147">**Ignorar amostra atual-todos os exemplos abertos**: isso marcará, como **ignorar**, todos os arquivos não marcados em todos os exemplos abertos de todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="ebec0-147">**Skip current sample - all open samples**: This will tag, as **Skip**, all untagged files in all open samples for all users.</span></span> <span data-ttu-id="ebec0-148">Essa opção não é recomendada se os usuários estiverem atualmente em uma marcação de amostra.</span><span class="sxs-lookup"><span data-stu-id="ebec0-148">This option is not recommended if users are currently tagging samples.</span></span>
    
  - <span data-ttu-id="ebec0-149">**Reverter último exemplo**: a última amostra de treinamento de relevância será revertida, independentemente de estar antes ou após o processo de "cálculo".</span><span class="sxs-lookup"><span data-stu-id="ebec0-149">**Roll back last sample**: The last completed Relevance training sample will be rolled back, regardless of whether it is before or after the "Calculate" process.</span></span> <span data-ttu-id="ebec0-150">A reversão de um exemplo de atualização não é permitida.</span><span class="sxs-lookup"><span data-stu-id="ebec0-150">Rollback of a catch-up sample is not allowed.</span></span>
    
4. <span data-ttu-id="ebec0-151">Clique em **executar** para executar.</span><span class="sxs-lookup"><span data-stu-id="ebec0-151">Click **Execute** to run.</span></span> 
    
## <a name="transparency-analysis"></a><span data-ttu-id="ebec0-152">Análise de transparência</span><span class="sxs-lookup"><span data-stu-id="ebec0-152">Transparency analysis</span></span>

<span data-ttu-id="ebec0-153">O utilitário de análise transparência permite uma visão detalhada dos arquivos e a pontuação de relevância atribuída.</span><span class="sxs-lookup"><span data-stu-id="ebec0-153">The Transparency analysis utility enables a detailed view of files and their assigned Relevance score.</span></span> <span data-ttu-id="ebec0-154">O relatório pode ser usado como uma verificação de sanidade ou para comparar a relevância de um arquivo definido por um revisor humano em comparação à relevância atribuída pela descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="ebec0-154">The report can be used as a sanity check or to compare the relevance of a file defined by a human reviewer as compared to the relevance assigned by Advanced eDiscovery.</span></span> 
  
<span data-ttu-id="ebec0-155">Além da Pontuação de relevância, a descoberta eletrônica avançada calcula e atribui pesos de palavras-chave que consideram o contexto da palavra-chave.</span><span class="sxs-lookup"><span data-stu-id="ebec0-155">In addition to Relevance scores, Advanced eDiscovery calculates and assigns keyword weights that consider the keyword context.</span></span> <span data-ttu-id="ebec0-156">A mesma palavra em um arquivo pode ser atribuída a diferentes pesos, dependendo do contexto e local.</span><span class="sxs-lookup"><span data-stu-id="ebec0-156">The same word in a file can be assigned different weights, depending on context and location.</span></span> <span data-ttu-id="ebec0-157">Cada palavra-chave é marcada usando uma escala crescente de intensidade de cor variando de amarelo para laranja escuro e tons de cinza variados.</span><span class="sxs-lookup"><span data-stu-id="ebec0-157">Each keyword is marked using an increasing scale of color intensity ranging from yellow to dark orange and varying shades of gray.</span></span> <span data-ttu-id="ebec0-158">A codificação de cores é usada para indicar visualmente a contribuição positiva ou negativa relativa do Word à pontuação de relevância.</span><span class="sxs-lookup"><span data-stu-id="ebec0-158">Color coding is used to visually indicate the word's relative positive or negative contribution to the Relevance score.</span></span> 
  
<span data-ttu-id="ebec0-159">Em um cenário de caso de vários problemas, um relatório de análise de transparência pode ser gerado para cada problema.</span><span class="sxs-lookup"><span data-stu-id="ebec0-159">In a multiple-issue case scenario, a Transparency analysis report can be generated for each issue.</span></span>
  
1. <span data-ttu-id="ebec0-160">Na barra de menus, clique no ícone **engrenagem** .</span><span class="sxs-lookup"><span data-stu-id="ebec0-160">In the menu bar, click the **Cogwheel** icon.</span></span> 
    
2. <span data-ttu-id="ebec0-161">Na guia \*\* \> utilitários de configurações e utilitários\*\* , selecione \*\* \> configuração de análise de transparência\*\*.</span><span class="sxs-lookup"><span data-stu-id="ebec0-161">In the **Settings and utilities \> Utilities** tab, select **Transparency analysis \> Setup**.</span></span>
    
3. <span data-ttu-id="ebec0-162">Em \* \* ID de arquivo \* \*, insira a ID de arquivo do arquivo a ser processado.</span><span class="sxs-lookup"><span data-stu-id="ebec0-162">In \*\* File ID \*\*, enter the file ID of the file to process.</span></span>
    
4. <span data-ttu-id="ebec0-163">Na lista **problema** , selecione o problema pertinente.</span><span class="sxs-lookup"><span data-stu-id="ebec0-163">In the **Issue** list, select the pertinent issue.</span></span> 
    
5. <span data-ttu-id="ebec0-164">Clique em **análise de transparência**.</span><span class="sxs-lookup"><span data-stu-id="ebec0-164">Click **Transparency analysis**.</span></span> <span data-ttu-id="ebec0-165">Após a conclusão, o relatório de análise de transparência do arquivo é exibido, mostrando como as cores de palavra-chave marcadas são correlacionadas à pontuação de relevância geral.</span><span class="sxs-lookup"><span data-stu-id="ebec0-165">Upon completion, the Transparency analysis report for the file is displayed, which shows how the marked keyword colors correlate to the overall Relevance score.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ebec0-166">Também consulte</span><span class="sxs-lookup"><span data-stu-id="ebec0-166">See also</span></span>

[<span data-ttu-id="ebec0-167">Descoberta Eletrônica Avançada (clássica)</span><span class="sxs-lookup"><span data-stu-id="ebec0-167">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="ebec0-168">Definindo configurações de caso e de locatário</span><span class="sxs-lookup"><span data-stu-id="ebec0-168">Defining case and tenant settings</span></span>](define-case-and-tenant-settings-in-advanced-ediscovery.md)

