---
title: Definir opções de análise na descoberta eletrônica avançada do Office 365
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
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: 'Revise as etapas para configurar opções para o processo de análise na descoberta eletrônica avançada do Office 365, incluindo duplicatas, threads de email e temas.  '
ms.openlocfilehash: 8897099d7531b48f7c6618c106eeb6f051dac546
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557781"
---
# <a name="set-analyze-options-in-advanced-ediscovery-classic"></a><span data-ttu-id="a943e-103">Definir opções de análise na descoberta eletrônica avançada (clássica)</span><span class="sxs-lookup"><span data-stu-id="a943e-103">Set Analyze options in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="a943e-p101">A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="a943e-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="a943e-106">Em descoberta eletrônica avançada, defina as opções de análise antes de executar Analyze.</span><span class="sxs-lookup"><span data-stu-id="a943e-106">In Advanced eDiscovery, set the Analyze options prior to running Analyze.</span></span>
  
## <a name="set-analyze-options"></a><span data-ttu-id="a943e-107">Definir opções de análise</span><span class="sxs-lookup"><span data-stu-id="a943e-107">Set Analyze options</span></span>

<span data-ttu-id="a943e-108">Abra \> **a configuração**de \*\*análise de preparação \> \*\* .</span><span class="sxs-lookup"><span data-stu-id="a943e-108">Open **Prepare \> Analyze** \> **Setup**.</span></span> <span data-ttu-id="a943e-109">A janela a seguir é exibida.</span><span class="sxs-lookup"><span data-stu-id="a943e-109">The following window is displayed.</span></span>
  
![Definir Opções de Análise](../media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 <span data-ttu-id="a943e-111">**Threads quase duplicados e email** Marque esta caixa se você deseja executar a análise.</span><span class="sxs-lookup"><span data-stu-id="a943e-111">**Near-duplicates and email threads** Check this box if you want to run the analysis.</span></span> <span data-ttu-id="a943e-112">Ele é selecionado por padrão.</span><span class="sxs-lookup"><span data-stu-id="a943e-112">It is selected by default.</span></span> 
  
 <span data-ttu-id="a943e-113">**Similaridade de documentos** Insira o valor de limite Near-duplicates ou aceite o padrão de 65%.</span><span class="sxs-lookup"><span data-stu-id="a943e-113">**Document similarity** Enter the Near-duplicates threshold value or accept the default of 65%.</span></span> 
  
 <span data-ttu-id="a943e-114">**Temas** Marque esta caixa para processar todos os arquivos e atribuir temas a eles.</span><span class="sxs-lookup"><span data-stu-id="a943e-114">**Themes**Check this box to process all files and assign themes to them.</span></span> <span data-ttu-id="a943e-115">Por padrão, essa caixa de seleção não está selecionada.</span><span class="sxs-lookup"><span data-stu-id="a943e-115">By default, this check box is not selected.</span></span> <span data-ttu-id="a943e-116">Insira as opções a seguir se você deseja executar o processamento de temas.</span><span class="sxs-lookup"><span data-stu-id="a943e-116">Enter the following options if you want to perform Themes processing.</span></span>
  
- <span data-ttu-id="a943e-117">**Número máximo de temas** Insira ou selecione um valor para o número de temas a serem criados.</span><span class="sxs-lookup"><span data-stu-id="a943e-117">**Max number of themes**Enter or select a value for the number of themes to create.</span></span> <span data-ttu-id="a943e-118">O padrão é 200.</span><span class="sxs-lookup"><span data-stu-id="a943e-118">The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="a943e-119">Aumentar o número de temas afeta o desempenho, bem como a capacidade de um tema generalizar.</span><span class="sxs-lookup"><span data-stu-id="a943e-119">Increasing the number of themes affects performance, as well as the ability of a theme to generalize.</span></span> <span data-ttu-id="a943e-120">Quanto maior o número de temas, mais granulares eles são.</span><span class="sxs-lookup"><span data-stu-id="a943e-120">The higher the number of themes, the more granular they are.</span></span> <span data-ttu-id="a943e-121">Por exemplo, se um conjunto de 50 temas incluir um tema como "basquete, Spurs, clipes, Lakers"; 300 temas podem incluir temas separados: "Spurs", "Clippings", "Lakers".</span><span class="sxs-lookup"><span data-stu-id="a943e-121">For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers".</span></span> <span data-ttu-id="a943e-122">Se você não teve conhecimento do tema "basquete" e usar esse recurso para ECA, ver o tema "basquete" pode ser útil.</span><span class="sxs-lookup"><span data-stu-id="a943e-122">If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful.</span></span> <span data-ttu-id="a943e-123">Mas, se o processamento tiver muitos temas, talvez você nunca veja a palavra "basquete" e talvez não saiba que Spurs e recortes são bons temas de basquete para revisar, em vez de itens que entram em inicializações e usados para cabelo.</span><span class="sxs-lookup"><span data-stu-id="a943e-123">But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
- <span data-ttu-id="a943e-124">**Temas sugeridos** Você pode sugerir palavras de tema para controlar o processamento de temas.</span><span class="sxs-lookup"><span data-stu-id="a943e-124">**Suggested themes** You can suggest theme words to control Themes processing.</span></span> <span data-ttu-id="a943e-125">A descoberta eletrônica avançada se concentrará nessas palavras sugeridas e tentará criar um ou mais temas relevantes, com base nas configurações de "número máximo de temas".</span><span class="sxs-lookup"><span data-stu-id="a943e-125">Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="a943e-126">Por exemplo, se a palavra sugerida for "computador" e você tiver especificado "2" como o "número máximo de temas", a descoberta eletrônica avançada tentará gerar dois temas relacionados à palavra "computador".</span><span class="sxs-lookup"><span data-stu-id="a943e-126">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer".</span></span> <span data-ttu-id="a943e-127">Os dois temas podem ser "software de computador" e "hardware de computador", por exemplo.</span><span class="sxs-lookup"><span data-stu-id="a943e-127">The two themes might be "computer software" and "computer hardware", for example.</span></span> 
    
    ![Adicionar tema sugerido](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. <span data-ttu-id="a943e-129">Para exibir, adicionar ou editar temas sugeridos, clique em **Modificar**.</span><span class="sxs-lookup"><span data-stu-id="a943e-129">To view, add, or edit suggested themes, click **Modify**.</span></span>
    
2. <span data-ttu-id="a943e-130">No painel **temas sugeridos** , clique no ícone **Adicionar** ![ícone](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) de adição para adicionar um tema.</span><span class="sxs-lookup"><span data-stu-id="a943e-130">In the **Suggested themes** panel, click the **Add** ![add icon](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icon to add a theme.</span></span> <span data-ttu-id="a943e-131">No painel **Adicionar tema sugerido** , adicione as palavras, separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="a943e-131">In the **Add suggested theme** panel, add the words, separated by commas.</span></span> 
    
3. <span data-ttu-id="a943e-132">Em **número de temas**, selecione um valor para determinar o número de temas que a descoberta eletrônica avançada tentará gerar para essas palavras (o padrão é 1 tema).</span><span class="sxs-lookup"><span data-stu-id="a943e-132">In **Number of themes**, select a value to determine the number of themes Advanced eDiscovery will try to generate for these words (default is 1 theme).</span></span>
    
4. <span data-ttu-id="a943e-133">Clique em **salvar** e feche a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a943e-133">Click **Save** and then close the dialogue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="a943e-134">O número total de temas inclui temas sugeridos.</span><span class="sxs-lookup"><span data-stu-id="a943e-134">The total number of themes includes Suggested Themes.</span></span> <span data-ttu-id="a943e-135">O total de temas sugeridos não pode exceder o total de temas.</span><span class="sxs-lookup"><span data-stu-id="a943e-135">The total Suggested Themes cannot exceed the total themes.</span></span> <span data-ttu-id="a943e-136">Se houver muitos temas sugeridos em relação ao total de temas, apenas alguns temas "romance" serão detectados pelo sistema porque a maioria dos temas será dedicada aos temas sugeridos.</span><span class="sxs-lookup"><span data-stu-id="a943e-136">If there are many Suggested Themes relative to the total themes, only a few "novel" themes will be detected by the system because most of the themes will be dedicated to Suggested Themes.</span></span> 
  
- <span data-ttu-id="a943e-137">**Modo** Na lista suspensa, selecione uma opção de **temas** :</span><span class="sxs-lookup"><span data-stu-id="a943e-137">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="a943e-138">**Criar e aplicar modelo**: calcula temas por modelos de um segmento dos arquivos e, em seguida, distribui arquivos entre eles.</span><span class="sxs-lookup"><span data-stu-id="a943e-138">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="a943e-139">**Criar modelo**: calcula um modelo de temas de um segmento dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="a943e-139">**Create model**: Calculates a themes model from a segment of the files.</span></span> <span data-ttu-id="a943e-140">O processo de aplicação de divisão de arquivos é feito separadamente em outro momento.</span><span class="sxs-lookup"><span data-stu-id="a943e-140">The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="a943e-141">**Aplicar modelo**: essa opção só será mostrada se um modelo foi criado anteriormente e ainda não foi aplicado.</span><span class="sxs-lookup"><span data-stu-id="a943e-141">**Apply model**: This option is only shown if a model was created previously and not yet applied.</span></span> <span data-ttu-id="a943e-142">Isso irá dividir os arquivos com base nos temas.</span><span class="sxs-lookup"><span data-stu-id="a943e-142">This will divide the files based on the themes.</span></span>
    
<span data-ttu-id="a943e-143">Você também pode [definir ignorar texto](set-ignore-text-in-advanced-ediscovery.md) e [definir as configurações avançadas de análise](set-analyze-advanced-settings-in-advanced-ediscovery.md) para análise.</span><span class="sxs-lookup"><span data-stu-id="a943e-143">You can also [set ignore text](set-ignore-text-in-advanced-ediscovery.md) and [set Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze.</span></span> 
  
<span data-ttu-id="a943e-144">Após definir essas opções, clique em **analisar** para executar.</span><span class="sxs-lookup"><span data-stu-id="a943e-144">After you've set these options, click **Analyze** to run.</span></span> <span data-ttu-id="a943e-145">[Exibir resultados da análise](view-analyze-results-in-advanced-ediscovery.md) são exibidos.</span><span class="sxs-lookup"><span data-stu-id="a943e-145">[View Analyze results](view-analyze-results-in-advanced-ediscovery.md) are displayed.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a943e-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="a943e-146">See also</span></span>

[<span data-ttu-id="a943e-147">Descoberta eletrônica avançada (clássica)</span><span class="sxs-lookup"><span data-stu-id="a943e-147">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="a943e-148">Noções básicas sobre a similaridade de documentos</span><span class="sxs-lookup"><span data-stu-id="a943e-148">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a943e-149">Definir o texto de ignorar</span><span class="sxs-lookup"><span data-stu-id="a943e-149">Set Ignore text </span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a943e-150">Definir as configurações avançadas de análise</span><span class="sxs-lookup"><span data-stu-id="a943e-150">Set Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="a943e-151">Exibir resultados de análise</span><span class="sxs-lookup"><span data-stu-id="a943e-151">View Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

