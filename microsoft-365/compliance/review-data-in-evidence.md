---
title: Revise os dados em evidência
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Saiba mais sobre os métodos para revisar os dados em suas evidências, como exibir em formatos nativos, de texto ou quase nativos.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f094718bd14ee86ff8fdae482e86c22ecfbdc483
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034605"
---
# <a name="review-the-data-in-evidence"></a><span data-ttu-id="725fe-103">Revise os dados em evidência</span><span class="sxs-lookup"><span data-stu-id="725fe-103">Review the data in evidence</span></span>

<span data-ttu-id="725fe-104">Os dados em um conjunto de evidências em uma investigação de dados é um instantâneo dos resultados da pesquisa que você coletou e adicionou ao conjunto de evidências.</span><span class="sxs-lookup"><span data-stu-id="725fe-104">The data in an evidence set in a data investigation is a snapshot of the search results that you collected and added to the evidence set.</span></span> <span data-ttu-id="725fe-105">Quando você adiciona resultados de pesquisa a evidências, um processo é disparado para extrair arquivos, metadados e texto dos itens retornados pela pesquisa.</span><span class="sxs-lookup"><span data-stu-id="725fe-105">When you add search results to evidence, a process is triggered to extract files, metadata, and text from the items returned by the search.</span></span> <span data-ttu-id="725fe-106">Em seguida, a ferramenta de investigações de dados (visualização) cria um novo índice (por um processo chamado *indexação avançada*) de todos os dados e adiciona a uma evidência definida na guia **evidência** .</span><span class="sxs-lookup"><span data-stu-id="725fe-106">Then the Data Investigations (Preview) tool then builds a new index (by a process called *Advanced indexing*) of all the data and adds to an evidence set on the **Evidence** tab.</span></span> 

<span data-ttu-id="725fe-107">Para investigações temporais, isso permite que você contenha rapidamente o ambiente, excluindo os dados reais derramados ou mal-intencionados localizados na fonte de dados original, enquanto ao mesmo tempo, permitindo que você investigue a evidência recriada em um ambiente em quarentena, que neste caso é os dados copiados para o conjunto de evidências).</span><span class="sxs-lookup"><span data-stu-id="725fe-107">For time-sensitive investigations, this allows you to quickly contain the environment by deleting the actual spilled or malicious data located in the at original data source, while at the same time allowing you to investigate the re-created evidence in a quarantined environment, which in this case is the data copied to the evidence set).</span></span> <span data-ttu-id="725fe-108">Depois que as evidências são coletadas e adicionadas ao conjunto de evidências, você pode revisar documentos individuais no formato nativo, no formato de texto ou em um formato Near-nativo que você pode usar para anotar e redigir documentos.</span><span class="sxs-lookup"><span data-stu-id="725fe-108">After the evidence is collected and added to the evidence set, you can review individual documents in their native format, text format, or a near-native format that you can use to annotate and redact documents.</span></span> <span data-ttu-id="725fe-109">Além disso, você pode executar consultas para restringir o conjunto de dados por intervalo de tempo, tipos de arquivo, proprietários de dados e muitas outras propriedades e condições de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="725fe-109">Additionally, you can run queries to narrow the data set by time range, file types, data owners, and many other properties and search conditions.</span></span> <span data-ttu-id="725fe-110">Por exemplo, usando as condições autor, remetente ou destinatário, você pode identificar rapidamente as pessoas estão envolvidas no incidente e, se algum dado da sua organização tiver sido compartilhado com usuários externos.</span><span class="sxs-lookup"><span data-stu-id="725fe-110">For example, by using the Author, Sender, or Recipient conditions, you can quickly identify the people are involved in the incident and if any data from your organization has been shared with external users.</span></span> <span data-ttu-id="725fe-111">Para obter mais informações sobre como pesquisar dados em um conjunto de evidências, consulte [Query The data in Evidence](evidence-query.md).</span><span class="sxs-lookup"><span data-stu-id="725fe-111">For more information about searching through data in an evidence set, see [Query the data in evidence](evidence-query.md).</span></span>

<span data-ttu-id="725fe-112">Para agrupar documentos e obter mais assistência para revisão, selecione um conjunto de evidências na guia **evidência** e clique em **gerenciar evidência**.</span><span class="sxs-lookup"><span data-stu-id="725fe-112">To group documents and get more assistance for your review, select an evidence set on the **Evidence** tab, and then click **Manage evidence**.</span></span> <span data-ttu-id="725fe-113">No bloco de **análise** , clique em **Recompilar análise de todo o conjunto**.</span><span class="sxs-lookup"><span data-stu-id="725fe-113">In the **Analytics** tile, click **Rebuild analytics for the whole set**.</span></span> <span data-ttu-id="725fe-114">Isso executará análises avançadas, como detecção de duplicidades, encadeamento de emails e análise de tema.</span><span class="sxs-lookup"><span data-stu-id="725fe-114">This will run advanced analytics such as duplicate detection, email threading, and theme analysis.</span></span> <span data-ttu-id="725fe-115">Posteriormente, você pode ver os temas gerais dos dados e também organizar documentos por threads de email, próximos duplicatas e duplicatas exatas para ajudar sua investigação.</span><span class="sxs-lookup"><span data-stu-id="725fe-115">Afterwards, you can see the general themes of the data and also organize documents by email threads, near duplicates, and exact duplicates to help your investigation.</span></span> <span data-ttu-id="725fe-116">Para obter mais informações, consulte [executar análise para investigar mais rápido](run-analytics-to-investigate-faster.md).</span><span class="sxs-lookup"><span data-stu-id="725fe-116">For more information, see [Run analytics to investigate faster](run-analytics-to-investigate-faster.md).</span></span>

## <a name="view-documents-in-evidence"></a><span data-ttu-id="725fe-117">Exibir documentos em evidência</span><span class="sxs-lookup"><span data-stu-id="725fe-117">View documents in evidence</span></span>

<span data-ttu-id="725fe-118">As investigações de dados (visualização) permitem exibir conteúdo em vários visualizadores diferentes, com cada visualizador com uma finalidade diferente.</span><span class="sxs-lookup"><span data-stu-id="725fe-118">Data Investigations (Preview) allows you to display content in several different viewers, with each viewer having a different purpose.</span></span> <span data-ttu-id="725fe-119">Esses visualizadores são:</span><span class="sxs-lookup"><span data-stu-id="725fe-119">These viewers are:</span></span>

- <span data-ttu-id="725fe-120">Metadados de arquivo</span><span class="sxs-lookup"><span data-stu-id="725fe-120">File metadata</span></span>
- <span data-ttu-id="725fe-121">Modo de exibição nativo</span><span class="sxs-lookup"><span data-stu-id="725fe-121">Native view</span></span>
- <span data-ttu-id="725fe-122">Exibição de texto</span><span class="sxs-lookup"><span data-stu-id="725fe-122">Text view</span></span>
- <span data-ttu-id="725fe-123">Modo de anotações</span><span class="sxs-lookup"><span data-stu-id="725fe-123">Annotate view</span></span>

<span data-ttu-id="725fe-124">Para acessar qualquer um desses visualizadores, basta selecionar um documento em um conjunto de evidências.</span><span class="sxs-lookup"><span data-stu-id="725fe-124">To access any of these viewers, just select a document in an evidence set.</span></span>

## <a name="file-metadata"></a><span data-ttu-id="725fe-125">Metadados de arquivo</span><span class="sxs-lookup"><span data-stu-id="725fe-125">File metadata</span></span>

<span data-ttu-id="725fe-126">Este modo de exibição exibe várias propriedades de metadados associadas ao documento selecionado.</span><span class="sxs-lookup"><span data-stu-id="725fe-126">This view displays various metadata properties associated with the selected document.</span></span> <span data-ttu-id="725fe-127">Você pode ativar e desativar este modo de exibição clicando em **metadados de arquivo**.</span><span class="sxs-lookup"><span data-stu-id="725fe-127">You can toggle this view on and off by clicking **File metadata**.</span></span> <span data-ttu-id="725fe-128">Ao revisar um documento, você pode exibir os metadados do arquivo e ainda alterar entre os diferentes visualizadores.</span><span class="sxs-lookup"><span data-stu-id="725fe-128">When reviewing a document, you can view the file metadata and still change between the different viewers.</span></span>

<span data-ttu-id="725fe-129">Veja um exemplo dos metadados de arquivo para um documento.</span><span class="sxs-lookup"><span data-stu-id="725fe-129">Here's an example of the file metadata for a document.</span></span> <span data-ttu-id="725fe-130">Para obter mais informações sobre os campos de metadados, consulte [Document Metadata Fields in data investigações (Preview)](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="725fe-130">For more information about the metadata fields, see [Document metadata fields in Data Investigations (Preview)](document-metadata-fields.md).</span></span>

![Painel metadados de arquivo](../media/Reviewimage2.png)

## <a name="native-view"></a><span data-ttu-id="725fe-132">Modo de exibição nativo</span><span class="sxs-lookup"><span data-stu-id="725fe-132">Native view</span></span>

<span data-ttu-id="725fe-133">O visualizador nativo exibe o modo de exibição mais preciso de um documento no formato nativo.</span><span class="sxs-lookup"><span data-stu-id="725fe-133">The Native viewer displays the most accurate view of a document in it's native format.</span></span> <span data-ttu-id="725fe-134">O modo de exibição nativo é suportado para centenas de tipos de arquivo e deve exibir documentos na experiência nativa verdadeiramente mais verdadeira possível.</span><span class="sxs-lookup"><span data-stu-id="725fe-134">Native view is supported for hundreds of file types and is meant to display documents in the truest native experience possible.</span></span> <span data-ttu-id="725fe-135">Para arquivos do Microsoft Office, o visualizador nativo usa a versão da Web dos aplicativos do Office.</span><span class="sxs-lookup"><span data-stu-id="725fe-135">For Microsoft Office files, the Native viewer uses the web version of Office apps.</span></span> <span data-ttu-id="725fe-136">Isso permite que você exiba conteúdo como comentários em diferentes documentos do Office, fórmulas e linhas/colunas ocultas no Excel e o modo de anotações no PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="725fe-136">This allows you to view content such as comments in different Office documents, formulas and hidden rows/columns in Excel, and the Notes view in PowerPoint.</span></span>

![<span data-ttu-id="725fe-137">Modo de exibição nativo</span><span class="sxs-lookup"><span data-stu-id="725fe-137">Native view</span></span>
](../media/Reviewimage3.png)

## <a name="text-view"></a><span data-ttu-id="725fe-138">Exibição de texto</span><span class="sxs-lookup"><span data-stu-id="725fe-138">Text view</span></span>

<span data-ttu-id="725fe-139">O Visualizador de texto fornece um modo de exibição do texto extraído de um arquivo.</span><span class="sxs-lookup"><span data-stu-id="725fe-139">The Text viewer provides a view of the extracted text of a file.</span></span> <span data-ttu-id="725fe-140">Ele ignora todas as imagens e formatação inseridas, mas esse modo de exibição é muito útil se você estiver tentando rapidamente revisar e entender o conteúdo em um documento.</span><span class="sxs-lookup"><span data-stu-id="725fe-140">It ignores any embedded images and formatting, but this view is very useful if you're trying to quickly review and understand the content in a document.</span></span> <span data-ttu-id="725fe-141">O modo de exibição de texto também inclui estes recursos:</span><span class="sxs-lookup"><span data-stu-id="725fe-141">Text view also includes these features:</span></span>

  - <span data-ttu-id="725fe-142">Um contador de linhas, que facilita a referência a partes específicas de um documento.</span><span class="sxs-lookup"><span data-stu-id="725fe-142">A line counter, which makes it easier to reference specific portions of a document.</span></span>

  - <span data-ttu-id="725fe-143">Visitas de pesquisa realçando que realçar termos no documento e no ScrollBar</span><span class="sxs-lookup"><span data-stu-id="725fe-143">Search hit highlighting that highlight terms in the document as well as on the scrollbar</span></span>

  - <span data-ttu-id="725fe-144">Um modo de exibição de comparação fornece um modo de exibição de comparação que realça as diferenças de texto ao exibir documentos usando o painel **próximo duplicatas** .</span><span class="sxs-lookup"><span data-stu-id="725fe-144">A diff view provides a comparison view that highlights the text differences when viewing documents using the **Near duplicates** panel.</span></span>

<span data-ttu-id="725fe-145">**Exemplo de contador de linha e realce de ocorrência de pesquisa em texto e ScrollBar**</span><span class="sxs-lookup"><span data-stu-id="725fe-145">**Example of line counter and search hit highlighting in text and scrollbar**</span></span>

![<span data-ttu-id="725fe-146">Exibição de texto</span><span class="sxs-lookup"><span data-stu-id="725fe-146">Text view</span></span>
](../media/Reviewimage4.png)

<span data-ttu-id="725fe-147">**Exemplo da exibição de comparação**</span><span class="sxs-lookup"><span data-stu-id="725fe-147">**Example of the diff view**</span></span>

![<span data-ttu-id="725fe-148">Exibição de comparação</span><span class="sxs-lookup"><span data-stu-id="725fe-148">Diff view</span></span>
](../media/Reviewimage5.png)

## <a name="annotate-view"></a><span data-ttu-id="725fe-149">Modo de anotações</span><span class="sxs-lookup"><span data-stu-id="725fe-149">Annotate view</span></span>

<span data-ttu-id="725fe-150">O modo de anotações fornece recursos que permitem que você aplique marcação em um documento durante o processo de revisão; Isso inclui as seguintes ferramentas:</span><span class="sxs-lookup"><span data-stu-id="725fe-150">The Annotate view provides features that allow you to apply markup on a document during the review process; this  includes these tools:</span></span>

  - <span data-ttu-id="725fe-151">**Redação de área** – você pode desenhar uma caixa opaca no documento que oculta conteúdo confidencial.</span><span class="sxs-lookup"><span data-stu-id="725fe-151">**Area redactions** – You can draw an opaque box on the document that hides sensitive content.</span></span>

  - <span data-ttu-id="725fe-152">**Lápis** – você pode desenhar em um documento para dar atenção a certas partes do conteúdo</span><span class="sxs-lookup"><span data-stu-id="725fe-152">**Pencil** – You can free-hand draw on a document to bring attention to certain portions of the content</span></span>

  - <span data-ttu-id="725fe-153">**Selecionar anotações** -você pode selecionar e excluir anotações em um documento.</span><span class="sxs-lookup"><span data-stu-id="725fe-153">**Select annotations** - You can select and delete annotations in a document.</span></span>

  - <span data-ttu-id="725fe-154">**Alternar transparência da anotação** – é possível alternar a transparência de anotações (entre opaco e semi-transparente) para que você possa exibir o conteúdo por trás da anotação.</span><span class="sxs-lookup"><span data-stu-id="725fe-154">**Toggle annotation transparency** – You can toggle the transparency of annotations (between opaque and semi-transparent)so you can view the content behind the annotation.</span></span> <span data-ttu-id="725fe-155">Isso inclui a alternância da transparência de anotações e redaçãos de lápis.</span><span class="sxs-lookup"><span data-stu-id="725fe-155">This includes toggling the transparency of pencil annotations and redactions.</span></span>

<span data-ttu-id="725fe-156">O modo de anotações também fornece a seguinte funcionalidade de navegação:</span><span class="sxs-lookup"><span data-stu-id="725fe-156">The Annotate view also provides the following navigation functionality:</span></span>

  - <span data-ttu-id="725fe-157">**Página anterior**, **próxima página**e **ir para** controles de navegação de página para usar para documentos de várias páginas.</span><span class="sxs-lookup"><span data-stu-id="725fe-157">**Previous page**, **Next page**, and **Go to page** - Navigation controls to use for multi-page documents.</span></span>

  - <span data-ttu-id="725fe-158">**Zoom** – aumenta ou diminui o tamanho dos documentos no modo de anotações.</span><span class="sxs-lookup"><span data-stu-id="725fe-158">**Zoom** – Increases or decreases the size of documents in Annotate view.</span></span>

  - <span data-ttu-id="725fe-159">**Girar** – girar documentos no sentido horário.</span><span class="sxs-lookup"><span data-stu-id="725fe-159">**Rotate** – Rotate documents clockwise.</span></span>

  - <span data-ttu-id="725fe-160">**Pesquisa** – pesquise palavras-chave em um documento e, em seguida, use os controles anteriores e próximos para exibir os acertos (que são realçados) no documento.</span><span class="sxs-lookup"><span data-stu-id="725fe-160">**Search** – Search for keywords in a document, and then use Previous and Next controls to view the hits (which are highlighted) within the document.</span></span>

<span data-ttu-id="725fe-161">**Exemplo de exibição de anotações**</span><span class="sxs-lookup"><span data-stu-id="725fe-161">**Example of Annotate view**</span></span>

![Modo de anotações](../media/Reviewimage1.png)

> [!NOTE]
> <span data-ttu-id="725fe-163">As anotações são aplicadas a uma cópia do documento que foi adicionado ao conjunto de evidências.</span><span class="sxs-lookup"><span data-stu-id="725fe-163">Annotations are applied to a copy of the document that was added to the evidence set.</span></span> <span data-ttu-id="725fe-164">Os documentos originais no serviço ativo não estão anotados.</span><span class="sxs-lookup"><span data-stu-id="725fe-164">The original documents in the live service aren't annotated.</span></span>
