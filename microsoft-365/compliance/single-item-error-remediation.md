---
title: Correção de erros de item único
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
description: Você pode corrigir um erro de processamento em um documento em um conjunto de revisão em Advanced eDiscovery sem ter que seguir o processo de correção de erro em massa.
ms.openlocfilehash: 8e5d8d00f507dc5792a1beda018d4c76632b82f7
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751578"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a><span data-ttu-id="d938f-103">Correção de erro de item único Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="d938f-103">Single item error remediation in Advanced eDiscovery</span></span>

<span data-ttu-id="d938f-104">A correção de erros Advanced eDiscovery aos usuários a capacidade de corrigir problemas de dados que impedem Advanced eDiscovery o processamento correto do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="d938f-104">Error remediation gives Advanced eDiscovery users the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="d938f-105">Por exemplo, os arquivos protegidos por senha não podem ser processados porque esses arquivos são bloqueados ou criptografados.</span><span class="sxs-lookup"><span data-stu-id="d938f-105">For example, files that are password protected can't be processed because those files are locked or encrypted.</span></span> <span data-ttu-id="d938f-106">Anteriormente, você só poderia corrigir erros em massa usando [esse fluxo de trabalho](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="d938f-106">Previously, you could only remediate errors in bulk by using [this workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="d938f-107">Mas, às vezes, não faz sentido corrigir erros em vários arquivos quando você não tem certeza se algum desses arquivos está respondendo ao caso que você está investigando.</span><span class="sxs-lookup"><span data-stu-id="d938f-107">But sometimes, it doesn't make sense to remediate errors in multiple files when you’re unsure if any of those files are responsive to the case you’re investigating.</span></span> <span data-ttu-id="d938f-108">Também pode não fazer sentido corrigir erros antes de você ter a chance de revisar os metadados de arquivo (como o local do arquivo ou quem tinha acesso) para ajudá-lo a tomar decisões in-locar sobre a capacidade de resposta.</span><span class="sxs-lookup"><span data-stu-id="d938f-108">It also might not make sense to remediate errors before you’ve had a chance to review the file metadata (such as file location or who had access) to help you make up-front decisions about responsiveness.</span></span> <span data-ttu-id="d938f-109">Um novo recurso chamado correção de erro de *item* único oferece aos gerentes de Descobertas Digitais a capacidade de exibir os metadados dos arquivos com um erro de processamento e, se necessário, corrigir o erro diretamente no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="d938f-109">A new feature called *single item error remediation* gives eDiscovery managers the ability to view the metadata of files with a processing error and if necessary remediate the error directly in the review set.</span></span> <span data-ttu-id="d938f-110">O artigo discute como identificar, ignorar e corrigir arquivos com erros de processamento em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="d938f-110">The article discusses how to identify, ignore, and remediate files with processing errors in a review set.</span></span>

## <a name="identify-documents-with-errors"></a><span data-ttu-id="d938f-111">Identificar documentos com erros</span><span class="sxs-lookup"><span data-stu-id="d938f-111">Identify documents with errors</span></span>

<span data-ttu-id="d938f-112">Documentos com erros de processamento em um conjunto de revisão agora são identificados (com uma faixa).</span><span class="sxs-lookup"><span data-stu-id="d938f-112">Documents with processing errors in a review set are now identified (with a banner).</span></span> <span data-ttu-id="d938f-113">Você pode corrigir ou ignorar o erro.</span><span class="sxs-lookup"><span data-stu-id="d938f-113">You can remediate or ignore the error.</span></span> <span data-ttu-id="d938f-114">A captura de tela a seguir mostra a faixa de erro de processamento de um documento do Word em um conjunto de revisão protegido por senha.</span><span class="sxs-lookup"><span data-stu-id="d938f-114">The following screenshot shows the processing error banner for a Word document in a review set that is password-protected.</span></span> <span data-ttu-id="d938f-115">Observe também que você pode exibir os metadados de arquivo de documentos com erros de processamento.</span><span class="sxs-lookup"><span data-stu-id="d938f-115">Also notice that you can view the file metadata of documents with processing errors.</span></span>

![Banner exibido para documento com erro de processamento](../media/SIERimage1.png)

<span data-ttu-id="d938f-117">Você também pode pesquisar documentos que tenham erros de processamento usando a condição de **status** processamento ao consultar os documentos em um conjunto [de revisão](review-set-search.md).</span><span class="sxs-lookup"><span data-stu-id="d938f-117">You can also search for documents that have processing errors by using the **Processing status** condition when [querying the documents in a review set](review-set-search.md).</span></span>

![Use a condição de status de processamento para pesquisar documentos de erro](../media/SIERimage2.png)

### <a name="ignore-errors"></a><span data-ttu-id="d938f-119">Ignorar erros</span><span class="sxs-lookup"><span data-stu-id="d938f-119">Ignore errors</span></span>

<span data-ttu-id="d938f-120">Você pode ignorar um erro de processamento clicando em **Ignorar** na faixa de erro de processamento.</span><span class="sxs-lookup"><span data-stu-id="d938f-120">You can ignore a processing error by clicking **Ignore** in the processing error banner.</span></span> <span data-ttu-id="d938f-121">Quando você ignora um erro, o documento é removido do fluxo de trabalho de correção de erros [em massa.](error-remediation-when-processing-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="d938f-121">When you ignore an error, the document is removed from the [bulk error remediation workflow](error-remediation-when-processing-data-in-advanced-ediscovery.md).</span></span> <span data-ttu-id="d938f-122">Depois que um erro é ignorado, o banner do documento muda de cor e indica que o erro de processamento foi ignorado.</span><span class="sxs-lookup"><span data-stu-id="d938f-122">After an error is ignored, the document banner changes color and indicates that the processing error was ignored.</span></span> <span data-ttu-id="d938f-123">A qualquer momento, você pode reverter a decisão de ignorar o erro clicando em **Reverter**.</span><span class="sxs-lookup"><span data-stu-id="d938f-123">At any time, you can revert the decision to ignore the error by clicking **Revert**.</span></span>

![Clique em Ignorar para ignorar o erro de processamento](../media/SIERimage3.png)

<span data-ttu-id="d938f-125">Você também pode pesquisar todos os documentos que tiveram um erro de processamento ignorado usando a condição Erros de processamento *ignorados* ao consultar documentos em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="d938f-125">You can also search for all documents that had a processing error that was ignored by using the *Ignored processing errors* condition when querying documents in a review set.</span></span>

![Use a condição De erros de processamento ignorados para pesquisar documentos de erro ignorados](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a><span data-ttu-id="d938f-127">Corrigir um documento com erros</span><span class="sxs-lookup"><span data-stu-id="d938f-127">Remediate a document with errors</span></span>

<span data-ttu-id="d938f-128">Às vezes, talvez seja necessário corrigir um erro de processamento em documentos (removendo uma senha, descriptografando um arquivo criptografado ou recuperando um documento corrompido) e, em seguida, adicione o documento remediado ao conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="d938f-128">Sometimes you may be required to remediate a processing error in documents (by removing a password, decrypting an encrypted file, or recovering a corrupted document) and then add the remediated document to the review set.</span></span> <span data-ttu-id="d938f-129">Isso permite que você revise e exporte o documento de erro juntamente com os outros documentos no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="d938f-129">This allows you to review and export the error document together with the other documents in the review set.</span></span> 

<span data-ttu-id="d938f-130">Para correção de um único documento, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="d938f-130">To remediate a single document, follow these steps:</span></span>

1. <span data-ttu-id="d938f-131">Clique **em Baixar** Baixar  >  **original** para baixar uma cópia do arquivo em um computador local.</span><span class="sxs-lookup"><span data-stu-id="d938f-131">Click **Download** > **Download original** to download a copy of the file to a local computer.</span></span>

   ![Baixar o documento com o erro de processamento](../media/SIERimage5.png)

2. <span data-ttu-id="d938f-133">Corrigir o erro no arquivo offline.</span><span class="sxs-lookup"><span data-stu-id="d938f-133">Remediate the error in the file offline.</span></span> <span data-ttu-id="d938f-134">Para arquivos criptografados, isso exigiria software de descriptografia, para remover a proteção de senha, fornecer a senha e salvar o arquivo ou usar um quebrador de senha.</span><span class="sxs-lookup"><span data-stu-id="d938f-134">For encrypted files, that would require decryption software, to remove password protection, either provide the password and save the file or use a password cracker.</span></span> <span data-ttu-id="d938f-135">Depois de remediar o arquivo, vá para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="d938f-135">After you remediate the file, go to the next step.</span></span>

3. <span data-ttu-id="d938f-136">No conjunto de revisão, selecione o arquivo com o erro de processamento que você correu e clique em **Correção**.</span><span class="sxs-lookup"><span data-stu-id="d938f-136">In the review set, select the file with the processing error that you remediated, and then  click **Remediation**.</span></span>

   ![Clique em Correção na faixa do documento com erro de processamento](../media/SIERimage6.png)


4. <span data-ttu-id="d938f-138">Clique **em** Procurar , vá para o local do arquivo remediado em seu computador local e selecione o arquivo.</span><span class="sxs-lookup"><span data-stu-id="d938f-138">Click **Browse**, go to the location of the remediated file on your local computer, and then select the file.</span></span>

   ![Clique em Procurar e selecione o arquivo remediado em seu computador local](../media/SIERimage7.png)

    <span data-ttu-id="d938f-140">Depois de selecionar o arquivo remediado, ele é carregado automaticamente para o conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="d938f-140">After selecting the remediated file, it is automatically uploaded to the review set.</span></span> <span data-ttu-id="d938f-141">Você pode rastrear o status de processamento do arquivo.</span><span class="sxs-lookup"><span data-stu-id="d938f-141">You can track the processing status of the file.</span></span>

    ![O status do processo de correção é exibido](../media/SIERimage8.png)

   <span data-ttu-id="d938f-143">Depois que o processamento for concluído, você poderá exibir o documento remediado.</span><span class="sxs-lookup"><span data-stu-id="d938f-143">After processing is completed, you can view the remediated document.</span></span>

    ![Você pode exibir o arquivo remediado no formato nativo no conjunto de revisão](../media/SIERimage9.png)

<span data-ttu-id="d938f-145">Para obter mais informações sobre o que acontece quando um documento é remediado, consulte O que acontece quando os arquivos [são remediados](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated).</span><span class="sxs-lookup"><span data-stu-id="d938f-145">For more information about what happens when a document is remediated, see [What happens when files are remediated](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated).</span></span>

## <a name="search-for-remediated-documents"></a><span data-ttu-id="d938f-146">Pesquisar documentos remediados</span><span class="sxs-lookup"><span data-stu-id="d938f-146">Search for remediated documents</span></span>

<span data-ttu-id="d938f-147">Você pode pesquisar todos os documentos em um conjunto de revisão que foram remediados usando a condição **Keywords** e especificando o seguinte par de propriedades:valor: **IsFromErrorRemediation:true**.</span><span class="sxs-lookup"><span data-stu-id="d938f-147">You can search for all documents in a review set that were remediated by using the **Keywords** condition and specifying the following property:value pair: **IsFromErrorRemediation:true**.</span></span> <span data-ttu-id="d938f-148">Essa propriedade também está disponível no arquivo de carga de exportação quando você exporta documentos de um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="d938f-148">This property is also available in the export load file when you export documents from a review set.</span></span>
