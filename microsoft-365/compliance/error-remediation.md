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
description: Saiba como usar a correção de erros para corrigir problemas de dados em investigações de dados (prévia) que podem impedir o processamento adequado de conteúdo.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c833ce9ae93f5395e06ee3dbde54ff4a8d5d4a00
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035113"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a><span data-ttu-id="4fbe9-103">Correção de erro ao processar dados de uma investigação</span><span class="sxs-lookup"><span data-stu-id="4fbe9-103">Error remediation when processing data for an investigation</span></span>

<span data-ttu-id="4fbe9-104">A correção de erros permite que os investigadores corrijam problemas de dados que impedem que investigações de dados (visualização) processem o conteúdo corretamente.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-104">Error remediation allows investigators the ability to rectify data issues that prevent Data Investigations (Preview) from properly processing the content.</span></span> <span data-ttu-id="4fbe9-105">Por exemplo, os arquivos protegidos por senha não podem ser processados, já que os arquivos são bloqueados ou criptografados.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-105">For example, files that are password protected cannot be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="4fbe9-106">Usando a correção de erros, os investigadores podem baixar arquivos com esses erros, remover a proteção por senha e carregar os arquivos corrigidos.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-106">Using error remediation, investigators can download files with such errors, remove the password protection, and upload the remediated files.</span></span>

<span data-ttu-id="4fbe9-107">Use o fluxo de trabalho a seguir para corrigir arquivos com erros em casos de investigações de dados (visualização).</span><span class="sxs-lookup"><span data-stu-id="4fbe9-107">Use the following workflow to remediate files with errors in Data Investigations (Preview) cases.</span></span>

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="4fbe9-108">Criando uma sessão de correção de erro para corrigir arquivos com erros de processamento</span><span class="sxs-lookup"><span data-stu-id="4fbe9-108">Creating an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="4fbe9-109">Se o assistente de correção de erros for fechado a qualquer momento durante o procedimento a seguir, você poderá retornar à sessão de correção de erro na guia **processamento** selecionando as **correções de erro** no menu suspenso **Exibir** .</span><span class="sxs-lookup"><span data-stu-id="4fbe9-109">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Error remediations** in the **View** drop down menu.</span></span>

1. <span data-ttu-id="4fbe9-110">Na guia **processamento** em uma investigação de dados, selecione **erros** no menu suspenso **Exibir** .</span><span class="sxs-lookup"><span data-stu-id="4fbe9-110">On the **Processing** tab in a data investigation, select **Errors** in the **View** dropdown menu.</span></span>

2. <span data-ttu-id="4fbe9-111">Selecione os erros que você deseja corrigir clicando no botão de opção ao lado do tipo de erro ou tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-111">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="4fbe9-112">No exemplo a seguir, estamos corrigindo um arquivo protegido por senha.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-112">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="4fbe9-113">Clique em **+ nova correção de erro**.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-113">Click **+ New error remediation**.</span></span>

    ![Correção de erro](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    <span data-ttu-id="4fbe9-115">A sessão de correção de erro começa, começando com um estágio de preparação onde os arquivos com erros são copiados para um local seguro do Azure para que eles possam ser baixados.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-115">The error remediation session begins, starting with a preparation stage where the files with errors are copied to a secure Azure location so that they can be downloaded.</span></span>

    ![Preparando correção de erro](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="4fbe9-117">Após a conclusão da preparação, clique em **Avançar: baixar arquivos** para continuar com o download.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-117">After the preparation is completed, click **Next: Download files** to proceed with download.</span></span>

    ![Baixar arquivos](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="4fbe9-119">Para baixar arquivos, especifique o **caminho de destino para download**.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-119">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="4fbe9-120">Este é um caminho no computador local onde o arquivo deve ser baixado.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-120">This is a path on your local computer where the file should be downloaded.</span></span>  <span data-ttu-id="4fbe9-121">O caminho padrão,%USERPROFILE%\Downloads\errors, aponta para a pasta downloads do usuário conectado; Isso pode ser alterado conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-121">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder; this can be changed as needed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="4fbe9-122">Recomendamos que você use um caminho de arquivo local em vez de um caminho de rede remoto para obter o desempenho ideal.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-122">We recommend that you use a local file path instead of a remote network path for optimal performance.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4fbe9-123">Se você ainda não instalou o AzCopy, você pode instalá-lo daqui:https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="4fbe9-123">If you haven't installed AzCopy, you can install it from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

6. <span data-ttu-id="4fbe9-124">Copie o comando predefinido clicando em **copiar para área de transferência**.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-124">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="4fbe9-125">Inicie um prompt de comando do Windows, Cole o comando e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-125">Start a windows command prompt, paste the command, and then press **Enter**.</span></span>  

    <span data-ttu-id="4fbe9-126">Os arquivos serão baixados.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-126">The files will be downloaded.</span></span>

    ![Preparando correção de erro](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > <span data-ttu-id="4fbe9-128">Se você tiver problemas para executar este comando, confira [solucionar problemas de AzCopy na descoberta eletrônica avançada](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="4fbe9-128">If you have issues running this command, see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

7. <span data-ttu-id="4fbe9-129">Depois de baixar os arquivos, você pode corrigi-los com uma ferramenta apropriada.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-129">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="4fbe9-130">Para arquivos protegidos por senha, há várias ferramentas de quebra de senha que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-130">For password protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="4fbe9-131">Se você souber as senhas dos arquivos, poderá abri-las e remover a proteção por senha.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-131">If you know the passwords for the files, you can open them and remove the password protection.</span></span>
    
   > [!NOTE]
    > <span data-ttu-id="4fbe9-132">É importante que você mantenha a estrutura de diretório e os nomes de arquivo dos arquivos corrigidos.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-132">It's important that you retain the directory structure and file names of the remediated files.</span></span> <span data-ttu-id="4fbe9-133">Os nomes de caminho dos arquivos e pastas baixados possibilitam a Associação dos arquivos corrigidos aos arquivos originais.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-133">The path names of the downloaded files and folders make it possible to associate the remediated files with the original files.</span></span>  <span data-ttu-id="4fbe9-134">Se a estrutura de diretório ou os nomes de arquivo forem alterados, você receberá o `Cannot apply Error Remediation to the current Evidenceset`seguinte erro:.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-134">If the directory structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Evidenceset`.</span></span>

8. <span data-ttu-id="4fbe9-135">Agora, retorne a investigações de dados (visualização) e clique em **Avançar: carregar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-135">Now, return to Data Investigations (Preview) and click **Next: Upload files**.</span></span>  <span data-ttu-id="4fbe9-136">Isso passará para a próxima etapa, onde você pode agora carregar os arquivos.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-136">This will move to the next step where you can now upload the files.</span></span>

    ![Carregar arquivos](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="4fbe9-138">Especifique o local dos arquivos corrigidos na caixa de texto **caminho para o local de arquivos** e clique em **copiar para área de transferência**.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-138">Specify the location of the remediated files in the **Path to location of files** text box, then click **Copy to clipboard**.</span></span>

10. <span data-ttu-id="4fbe9-139">Cole o comando em um prompt de comando do Windows e pressione **Enter** para carregar os arquivos.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-139">Paste the command into a Windows Command Prompt and press **Enter** to upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6. png](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="4fbe9-141">Por fim, retorne a investigações de dados (visualização) e clique em **Avançar: processar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-141">Finally, return to Data Investigations (Preview) and click **Next: Process files**.</span></span>

12. <span data-ttu-id="4fbe9-142">Quando o processamento estiver concluído.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-142">When processing is complete.</span></span>  <span data-ttu-id="4fbe9-143">Você pode retornar ao conjunto de trabalho e ver o arquivo corrigido.</span><span class="sxs-lookup"><span data-stu-id="4fbe9-143">You can return to the working set and see the remediated file.</span></span>

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="4fbe9-144">O que acontece quando os arquivos são corrigidos</span><span class="sxs-lookup"><span data-stu-id="4fbe9-144">What happens when files are remediated</span></span>

<span data-ttu-id="4fbe9-145">Quando os arquivos corrigidos são carregados, os metadados originais são preservados, exceto os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="4fbe9-145">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="4fbe9-146">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="4fbe9-146">ExtractedTextSize</span></span>
- <span data-ttu-id="4fbe9-147">HasText</span><span class="sxs-lookup"><span data-stu-id="4fbe9-147">HasText</span></span>
- <span data-ttu-id="4fbe9-148">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="4fbe9-148">IsErrorRemediate</span></span>
- <span data-ttu-id="4fbe9-149">Loadid</span><span class="sxs-lookup"><span data-stu-id="4fbe9-149">LoadId</span></span>
- <span data-ttu-id="4fbe9-150">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="4fbe9-150">ProcessingErrorMessage</span></span>
- <span data-ttu-id="4fbe9-151">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="4fbe9-151">ProcessingStatus</span></span>
- <span data-ttu-id="4fbe9-152">Texto</span><span class="sxs-lookup"><span data-stu-id="4fbe9-152">Text</span></span>
- <span data-ttu-id="4fbe9-153">WordCount</span><span class="sxs-lookup"><span data-stu-id="4fbe9-153">WordCount</span></span>
- <span data-ttu-id="4fbe9-154">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="4fbe9-154">WorkingsetId</span></span>

<span data-ttu-id="4fbe9-155">Para obter uma definição de todos os campos de metadados do documento em investigações de dados (visualização), confira [campos de metadados do documento](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="4fbe9-155">For a definition of all document metadata fields in Data Investigations (Preview), see [Document metadata fields](document-metadata-fields.md).</span></span>
