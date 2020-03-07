---
title: Gerenciar a configuração de relevância na Descoberta Eletrônica Avançada do Office 365
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
description: Leia as recomendações para a configuração do treinamento em relevância na Descoberta Eletrônica Avançada do Office 365 para classificar arquivos por relevância e gerar resultados analíticos.
ms.openlocfilehash: 49c7614eb1fec4e61fb374fb637093fd6e860619
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557881"
---
# <a name="manage-relevance-setup-in-advanced-ediscovery-classic"></a><span data-ttu-id="1555e-103">Gerenciar a configuração da Relevância na Descoberta Eletrônica Avançada (clássica)</span><span class="sxs-lookup"><span data-stu-id="1555e-103">Manage Relevance setup in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="1555e-p101">A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="1555e-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
 <span data-ttu-id="1555e-p102">A tecnologia de Relevância de Descoberta Eletrônica Avançada emprega software guiado por especialista para pontuar arquivos por relevância. A Relevância da Descoberta Eletrônica Avançada pode ser usada para Avaliação de Caso Antecipado (ECA), remoção e análise do arquivo de exemplo.</span><span class="sxs-lookup"><span data-stu-id="1555e-p102">Advanced eDiscovery Relevance technology employs expert-guided software for scoring files by their relevance. Advanced eDiscovery Relevance can be used for Early Case Assessment (ECA), culling, and file sample review.</span></span> 
  
 <span data-ttu-id="1555e-p103">A Descoberta Eletrônica Avançada inclui os componentes de treinamento e marcação de Relevância de arquivos relevantes a um caso. A Descoberta Eletrônica Avançada aprende com os exemplos treinados de arquivos relevantes e não relevantes para fornecer pontuações de relevância para cada arquivo e gera resultados analíticos que podem ser usados durante e após o processo de revisão do arquivo.</span><span class="sxs-lookup"><span data-stu-id="1555e-p103">Advanced eDiscovery includes components for the Relevance training and tagging of files relevant to a case. Advanced eDiscovery learns from the trained samples of Relevant and Not Relevant files to provide Relevance scores for each file, and generates analytical results that can be used during and after the file review process.</span></span> 
  
## <a name="guidelines-for-setting-up-relevance-training"></a><span data-ttu-id="1555e-110">Diretrizes para configurar o treinamento de relevância</span><span class="sxs-lookup"><span data-stu-id="1555e-110">Guidelines for setting up Relevance training</span></span>

 <span data-ttu-id="1555e-p104">Na Descoberta Eletrônica Avançada, na janela **Casos**, selecione um caso e clique em **Vá para o caso**. Clique em **Relevância** \> **Configuração de relevância**. Siga essas orientações recomendadas para configurar a Relevância.</span><span class="sxs-lookup"><span data-stu-id="1555e-p104">In Advance eDiscovery, in the **Cases** window, select a case and click **Go to case**. Click **Relevance** \> **Relevanace setup**. Follow these recommended guidelines to setup Relevance.</span></span> 
  
- <span data-ttu-id="1555e-114">**Marcação**: a eficácia do processo de treinamento de relevância interativa depende da capacidade de o especialista marcar os arquivos de amostra com precisão e consistência.</span><span class="sxs-lookup"><span data-stu-id="1555e-114">**Tagging**: The effectiveness of the iterative Relevance training process is dependent on the ability of the expert to tag the file samples with precision and consistency.</span></span>
    
- <span data-ttu-id="1555e-115">**Problemas de caso**:</span><span class="sxs-lookup"><span data-stu-id="1555e-115">**Case issues**:</span></span> 
    
  - <span data-ttu-id="1555e-p105">Para cada problema, use o mesmo especialista em todo o processo de treinamento de relevância. Não é permitido marcar simultaneamente o mesmo problema por vários especialistas.</span><span class="sxs-lookup"><span data-stu-id="1555e-p105">For each issue, use the same expert throughout the entire Relevance training process. Simultaneous tagging of the same issue by multiple experts is not permitted.</span></span>
    
  - <span data-ttu-id="1555e-118">Determine se cada grupo de arquivos é pertinente a apenas um problema específico.</span><span class="sxs-lookup"><span data-stu-id="1555e-118">Determine if each group of files is pertinent only to a specific issue.</span></span> 
    
  - <span data-ttu-id="1555e-p106">Se um problema for definido de maneira muito genérica, a Descoberta Eletrônica Avançada poderá gerar arquivos demais que realmente não são relevantes. Se um problema for definido de maneira muito estrita, o processo de treinamento de relevância poderá levar mais tempo.</span><span class="sxs-lookup"><span data-stu-id="1555e-p106">If an issue is defined too generally, Advanced eDiscovery may yield too many files that are actually not relevant. If an issue is defined too narrowly, the Relevance training process may take more time.</span></span> 
    
  - <span data-ttu-id="1555e-121">Durante cada ciclo de treinamento de relevância, a Descoberta Eletrônica Avançada concentra-se em um único problema ativo e os resultados de exemplo provisórios são exibidos adequadamente.</span><span class="sxs-lookup"><span data-stu-id="1555e-121">During each Relevance training cycle, Advanced eDiscovery focuses on a single active issue and interim sample results are displayed accordingly.</span></span>
    
  - <span data-ttu-id="1555e-p107">Em um cenário de vários problemas, o modo de amostragem permite a seleção dos problemas a serem incluídos no processamento. Os problemas definidos como "desativados" não são tratados até o modo de amostragem ser alterado. Um problema pode estar "ocioso" ou "ativado" para apenas um especialista.</span><span class="sxs-lookup"><span data-stu-id="1555e-p107">In a multiple-issue scenario, the Sampling mode enables the selection of issues to be included in processing. Issues defined as "off" are not handled until their Sampling mode is changed. An issue can be "idle" or "on" for only one expert.</span></span>
    
  -  <span data-ttu-id="1555e-p108">A Descoberta Eletrônica Avançada pode ser usada para gerar arquivos de privilégio de candidato. Configure um problema separado para privilégio. Se possível, treine e selecione primeiro para relevância e treine para privilégio no conjunto selecionado (recarregar o conjunto definido como um caso separado).</span><span class="sxs-lookup"><span data-stu-id="1555e-p108">Advanced eDiscovery can be used to generate candidate privilege files. Set up a separate issue for privilege. If possible, train and cull for relevance first, and then train for privilege on the culled set only (reload the culled set as a separate case).</span></span> 
    
  - <span data-ttu-id="1555e-p109">O cálculo em lote pode ser realizado somente quando não houver amostras abertas (quando você clica em cálculo em lote, haverá uma lista de usuários com amostras abertas). Para "fechar" amostras de outros usuários (isso deverá ser executado somente se esses usuários não estiverem marcando essas amostras), um administrador pode usar o utilitário de "Modificar relevância" com a opção "Amostra de todos os usuários".</span><span class="sxs-lookup"><span data-stu-id="1555e-p109">Batch calculation can be performed only when there are no open samples (when clicking Batch Calculation, there will be a list displayed of users with open samples). To "close" samples of other users (this should be performed only if these users are not tagging these samples), an Administrator can use the "Modify relevance" utility with the "All users sample" option.</span></span>
    
- <span data-ttu-id="1555e-p110">**Metadados**: a Descoberta Eletrônica Avançada concentra-se no conteúdo e não considera metadados como parte dos critérios de relevância.</span><span class="sxs-lookup"><span data-stu-id="1555e-p110">**Metadata**: Advanced eDiscovery focuses on content. It does not consider metadata as part of the relevance criteria.</span></span> 
    
- <span data-ttu-id="1555e-132">**Riqueza**: se a riqueza para um problema for inferior a 3% após a avaliação, considere a propagação do treinamento em relevância com arquivos conhecidos relevantes e não relevantes.</span><span class="sxs-lookup"><span data-stu-id="1555e-132">**Richness**: If the Richness for an issue is less than 3% after Assessment, consider seeding the Relevance training with known Relevant and Not Relevant files.</span></span>
    
- <span data-ttu-id="1555e-p111">**Tamanho do arquivo**: arquivos grandes (mais de 5.242.880 de caracteres de texto extraído) são ignorados em Relevância. Os arquivos não participam do processo de treinamento de relevância e não recebem uma pontuação de relevância após o lote de cálculo. Os arquivos com mais de 5 MB podem ser incluídos no conjunto da avaliação.</span><span class="sxs-lookup"><span data-stu-id="1555e-p111">**File size**: Large files (over 5,242,880 characters of extracted text) are ignored in Relevance. The files do not participate in the Relevance training process and do not receive a Relevance score after Batch Calculation. Files over 5MB can be included in the Assessment set.</span></span>
    
## <a name="setting-up-case-issues"></a><span data-ttu-id="1555e-136">Como configurar os problemas de caso</span><span class="sxs-lookup"><span data-stu-id="1555e-136">Setting up case issues</span></span>

<span data-ttu-id="1555e-137">Os parâmetros descritos nesta seção estão disponíveis na Descoberta Eletrônica Avançada **Relevância** \> **Configuração de relevância**.</span><span class="sxs-lookup"><span data-stu-id="1555e-137">The parameters described in this section are available in the Advanced eDiscovery **Relevance** \> **Relevance setup**.</span></span> 
  
- <span data-ttu-id="1555e-138">Os problemas devem ser atribuídos a um usuário que treinará os arquivos.</span><span class="sxs-lookup"><span data-stu-id="1555e-138">Issues must be assigned to a user who will train the files.</span></span>
    
- <span data-ttu-id="1555e-139">Os arquivos importados, em seguida, devem ser adicionados para o carregamento que está sendo processado.</span><span class="sxs-lookup"><span data-stu-id="1555e-139">Imported files must then be added to the load being processed.</span></span>
    
- <span data-ttu-id="1555e-140">Defina e organize problemas com cuidado, porque isso poderá afetar os resultados de treinamento de relevância.</span><span class="sxs-lookup"><span data-stu-id="1555e-140">Define and organize issues carefully, as this can impact the Relevance training results.</span></span>
    
<span data-ttu-id="1555e-141">Após os parâmetros serem definidos, o revisor/especialista pode começar o treinamento dos arquivos na guia **Relevância**.</span><span class="sxs-lookup"><span data-stu-id="1555e-141">After parameters are set, the reviewer / expert can start training the files in the **Relevance** tab.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1555e-142">Também consulte</span><span class="sxs-lookup"><span data-stu-id="1555e-142">See also</span></span>

[<span data-ttu-id="1555e-143">Descoberta Eletrônica Avançada (clássica)</span><span class="sxs-lookup"><span data-stu-id="1555e-143">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="1555e-144">Como definir problemas e atribuir usuários</span><span class="sxs-lookup"><span data-stu-id="1555e-144">Defining issues and assigning users</span></span>](define-issues-and-assign-users.md)
  
[<span data-ttu-id="1555e-145">Como configurar carregamentos para adicionar os arquivos importados</span><span class="sxs-lookup"><span data-stu-id="1555e-145">Setting up loads to add imported files</span></span>](set-up-loads-to-add-imported-files.md)
  
[<span data-ttu-id="1555e-146">Como definir as palavras-chave realçadas e opções avançadas</span><span class="sxs-lookup"><span data-stu-id="1555e-146">Defining highlighted keywords and advanced options</span></span>](define-highlighted-keywords-and-advanced-options.md)

