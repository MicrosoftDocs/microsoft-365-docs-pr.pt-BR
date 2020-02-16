---
title: Correção de erro ao processar dados de uma investigação
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
description: ''
ms.openlocfilehash: 524378ecb7ec7cd8285e7d1ccda5667aa6081f30
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42074400"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a><span data-ttu-id="427d4-102">Correção de erro ao processar dados de uma investigação</span><span class="sxs-lookup"><span data-stu-id="427d4-102">Error remediation when processing data for an investigation</span></span>

<span data-ttu-id="427d4-103">A correção de erros permite que os investigadores corrijam problemas de dados que impedem que investigações de dados (visualização) processem o conteúdo corretamente.</span><span class="sxs-lookup"><span data-stu-id="427d4-103">Error remediation allows investigators the ability to rectify data issues that prevent Data Investigations (Preview) from properly processing the content.</span></span> <span data-ttu-id="427d4-104">Por exemplo, os arquivos protegidos por senha não podem ser processados, já que os arquivos são bloqueados ou criptografados.</span><span class="sxs-lookup"><span data-stu-id="427d4-104">For example, files that are password protected cannot be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="427d4-105">Usando a correção de erros, os investigadores podem baixar arquivos com esses erros, remover a proteção por senha e carregar os arquivos corrigidos.</span><span class="sxs-lookup"><span data-stu-id="427d4-105">Using error remediation, investigators can download files with such errors, remove the password protection, and upload the remediated files.</span></span>

<span data-ttu-id="427d4-106">Use o fluxo de trabalho a seguir para corrigir arquivos com erros em casos de investigações de dados (visualização).</span><span class="sxs-lookup"><span data-stu-id="427d4-106">Use the following workflow to remediate files with errors in Data Investigations (Preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="427d4-107">Criando uma sessão de correção de erro para corrigir arquivos com erros de processamento</span><span class="sxs-lookup"><span data-stu-id="427d4-107">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="427d4-108">Se o assistente de correção de erros for fechado a qualquer momento durante o procedimento a seguir, você poderá retornar à sessão de correção de erro na guia **processamento** selecionando as **correções de erro** no menu suspenso **Exibir** .</span><span class="sxs-lookup"><span data-stu-id="427d4-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="427d4-109">Na guia **processamento** em uma investigação de dados, selecione **erros** no menu suspenso **Exibir** .</span><span class="sxs-lookup"><span data-stu-id="427d4-109">On the **Processing** tab in a data investigation, select **Errors** in the **View** dropdown menu.</span></span>

2. <span data-ttu-id="427d4-110">Selecione os erros que você deseja corrigir clicando no botão de opção ao lado do tipo de erro ou tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="427d4-110">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="427d4-111">No exemplo a seguir, estamos corrigindo um arquivo protegido por senha.</span><span class="sxs-lookup"><span data-stu-id="427d4-111">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="427d4-112">Clique em **+ nova correção de erro**.</span><span class="sxs-lookup"><span data-stu-id="427d4-112">Click **+ New error remediation**.</span></span>

    ![Correção de erro](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="427d4-114">A sessão de correção de erro começa, começando com um estágio de preparação onde os arquivos com erros são copiados para um local seguro do Azure para que eles possam ser baixados.</span><span class="sxs-lookup"><span data-stu-id="427d4-114">The error remediation session begins, starting with a preparation stage where the files with errors are copied to a secure Azure location so that they can be downloaded.</span></span>

    ![Preparando correção de erro](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="427d4-116">Após a conclusão da preparação, clique em **Avançar: baixar arquivos** para continuar com o download.</span><span class="sxs-lookup"><span data-stu-id="427d4-116">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![Baixar arquivos](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="427d4-118">Para baixar arquivos, especifique o **caminho de destino para download**.</span><span class="sxs-lookup"><span data-stu-id="427d4-118">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="427d4-119">Este é um caminho no computador local onde o arquivo deve ser baixado.</span><span class="sxs-lookup"><span data-stu-id="427d4-119">This is a path on your local computer where the file should be downloaded.</span></span>  <span data-ttu-id="427d4-120">O caminho padrão,%USERPROFILE%\Downloads\errors, aponta para a pasta downloads do usuário conectado; Isso pode ser alterado conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="427d4-120">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="427d4-121">Recomendamos que você use um caminho de arquivo local em vez de um caminho de rede remoto para obter o desempenho ideal.</span><span class="sxs-lookup"><span data-stu-id="427d4-121">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="427d4-122">Se você ainda não instalou o AzCopy, você pode instalá-lo daqui:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="427d4-122">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="427d4-123">Copie o comando predefinido clicando em **copiar para área de transferência**.</span><span class="sxs-lookup"><span data-stu-id="427d4-123">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="427d4-124">Inicie um prompt de comando do Windows, Cole o comando e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="427d4-124">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="427d4-125">Os arquivos serão baixados.</span><span class="sxs-lookup"><span data-stu-id="427d4-125">The files will be downloaded.</span></span>

    ![Preparando correção de erro](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="427d4-127">Se você tiver problemas para executar este comando, confira [solucionar problemas de AzCopy na descoberta eletrônica avançada](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="427d4-127">If you have issues running this command, see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

7. <span data-ttu-id="427d4-128">Depois de baixar os arquivos, você pode corrigi-los com uma ferramenta apropriada.</span><span class="sxs-lookup"><span data-stu-id="427d4-128">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="427d4-129">Para arquivos protegidos por senha, há várias ferramentas de quebra de senha que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="427d4-129">For password protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="427d4-130">Se você souber as senhas dos arquivos, poderá abri-las e remover a proteção por senha.</span><span class="sxs-lookup"><span data-stu-id="427d4-130">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    
   > [!NOTE]
    > <span data-ttu-id="427d4-131">É importante que você mantenha a estrutura de diretório e os nomes de arquivo dos arquivos corrigidos.</span><span class="sxs-lookup"><span data-stu-id="427d4-131">It's important that you retain the directory structure and file names of the remediated files.</span></span> <span data-ttu-id="427d4-132">Os nomes de caminho dos arquivos e pastas baixados possibilitam a Associação dos arquivos corrigidos aos arquivos originais.</span><span class="sxs-lookup"><span data-stu-id="427d4-132">The path names of the downloaded files and folders make it possible to associate the remediated files with the original files.</span></span>  <span data-ttu-id="427d4-133">Se a estrutura de diretório ou os nomes de arquivo forem alterados, você receberá o `Cannot apply Error Remediation to the current Evidenceset`seguinte erro:.</span><span class="sxs-lookup"><span data-stu-id="427d4-133">If the directory structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Evidenceset`.</span></span>

8. <span data-ttu-id="427d4-134">Agora, retorne a investigações de dados (visualização) e clique em **Avançar: carregar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="427d4-134">Now, return to Data Investigations (Preview) and click **Next: Upload files**.</span></span>  <span data-ttu-id="427d4-135">Isso passará para a próxima etapa, onde você pode agora carregar os arquivos.</span><span class="sxs-lookup"><span data-stu-id="427d4-135">This will move to the next step where you can now upload the files.</span></span>

    ![Carregar arquivos](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="427d4-137">Especifique o local dos arquivos corrigidos na caixa de texto **caminho para o local de arquivos** e clique em **copiar para área de transferência**.</span><span class="sxs-lookup"><span data-stu-id="427d4-137">Specify the location of the remediated files in the **Path to location of files** text box, then click **Copy to clipboard**.</span></span>

10. <span data-ttu-id="427d4-138">Cole o comando em um prompt de comando do Windows e pressione **Enter** para carregar os arquivos.</span><span class="sxs-lookup"><span data-stu-id="427d4-138">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6. png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="427d4-140">Por fim, retorne a investigações de dados (visualização) e clique em **Avançar: processar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="427d4-140">Finally, return to Data Investigations (Preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="427d4-141">Quando o processamento estiver concluído.</span><span class="sxs-lookup"><span data-stu-id="427d4-141">When processing is complete.</span></span>  <span data-ttu-id="427d4-142">Você pode retornar ao conjunto de trabalho e ver o arquivo corrigido.</span><span class="sxs-lookup"><span data-stu-id="427d4-142">You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="427d4-143">O que acontece quando os arquivos são corrigidos</span><span class="sxs-lookup"><span data-stu-id="427d4-143">What happens when files are remediated</span></span>

<span data-ttu-id="427d4-144">Quando os arquivos corrigidos são carregados, os metadados originais são preservados, exceto os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="427d4-144">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="427d4-145">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="427d4-145">ExtractedTextSize</span></span>
- <span data-ttu-id="427d4-146">HasText</span><span class="sxs-lookup"><span data-stu-id="427d4-146">HasText</span></span>
- <span data-ttu-id="427d4-147">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="427d4-147">IsErrorRemediate</span></span>
- <span data-ttu-id="427d4-148">Loadid</span><span class="sxs-lookup"><span data-stu-id="427d4-148">LoadId</span></span>
- <span data-ttu-id="427d4-149">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="427d4-149">ProcessingErrorMessage</span></span>
- <span data-ttu-id="427d4-150">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="427d4-150">ProcessingStatus</span></span>
- <span data-ttu-id="427d4-151">Texto</span><span class="sxs-lookup"><span data-stu-id="427d4-151">Text</span></span>
- <span data-ttu-id="427d4-152">WordCount</span><span class="sxs-lookup"><span data-stu-id="427d4-152">WordCount</span></span>
- <span data-ttu-id="427d4-153">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="427d4-153">WorkingsetId</span></span>

<span data-ttu-id="427d4-154">Para obter uma definição de todos os campos de metadados do documento em investigações de dados (visualização), confira [campos de metadados do documento](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="427d4-154">For a definition of all document metadata fields in Data Investigations (Preview), see [Document metadata fields](document-metadata-fields.md).</span></span>
