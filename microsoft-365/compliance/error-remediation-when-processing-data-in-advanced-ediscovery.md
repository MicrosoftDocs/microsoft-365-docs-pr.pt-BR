---
title: Correção de erros durante o processamento de dados
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
ms.openlocfilehash: 02fa8870d6edb4e1a6616604ee0e98638b217237
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072762"
---
# <a name="error-remediation-when-processing-data"></a><span data-ttu-id="306e8-102">Correção de erros durante o processamento de dados</span><span class="sxs-lookup"><span data-stu-id="306e8-102">Error remediation when processing data</span></span>

<span data-ttu-id="306e8-103">A correção de erros permite que os administradores de descoberta eletrônica corrijam problemas de dados que impedem a descoberta eletrônica avançada do processamento adequado do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="306e8-103">Error remediation allows eDiscovery administrators the ability to rectify data issues that prevent Advanced eDiscovery from properly processing the content.</span></span> <span data-ttu-id="306e8-104">Por exemplo, os arquivos protegidos por senha não podem ser processados, já que os arquivos são bloqueados ou criptografados.</span><span class="sxs-lookup"><span data-stu-id="306e8-104">For example, files that are password protected can't be processed since the files are locked or encrypted.</span></span> <span data-ttu-id="306e8-105">Usando a correção de erros, os administradores de descoberta eletrônica podem baixar arquivos com esses erros, remover a proteção por senha e carregar os arquivos corrigidos.</span><span class="sxs-lookup"><span data-stu-id="306e8-105">Using error remediation, eDiscovery administrators can download files with such errors, remove the password protection, and then upload the remediated files.</span></span>

<span data-ttu-id="306e8-106">Use o fluxo de trabalho a seguir para corrigir arquivos com erros em casos de descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="306e8-106">Use the following workflow to remediate files with errors in Advanced eDiscovery cases.</span></span>

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a><span data-ttu-id="306e8-107">Criar uma sessão de correção de erro para corrigir arquivos com erros de processamento</span><span class="sxs-lookup"><span data-stu-id="306e8-107">Create an error remediation session to remediate files with processing errors</span></span>

>[!NOTE]
><span data-ttu-id="306e8-108">Se o assistente de correção de erros for fechado a qualquer momento durante o procedimento a seguir, você poderá retornar à sessão de correção de erro na guia **processamento** selecionando as **correções** no menu suspenso **Exibir** .</span><span class="sxs-lookup"><span data-stu-id="306e8-108">If the the error remediation wizard is closed at any time during the following procedure, you can return to the error remediation session from the **Processing** tab by selecting **Remediations** in the **View** drop-down menu.</span></span>

1. <span data-ttu-id="306e8-109">Na guia **processamento** da caixa de descoberta eletrônica avançada, selecione **erros** no menu suspenso **Exibir** e, em seguida, selecione um conjunto de revisão ou o caso inteiro no menu suspenso **escopo** .</span><span class="sxs-lookup"><span data-stu-id="306e8-109">On the **Processing** tab in the Advanced eDiscovery case, select **Errors** in the **View** drop-down menu and then select a review set or the entire case in the **Scope** drop-down menu.</span></span> <span data-ttu-id="306e8-110">Esta seção exibe todos os erros do caso ou erro de um conjunto de revisão específico.</span><span class="sxs-lookup"><span data-stu-id="306e8-110">This section displays all errors from the case or error from a specific review set.</span></span>

   ![Correção de erro](media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. <span data-ttu-id="306e8-112">Selecione os erros que você deseja corrigir clicando no botão de opção ao lado do tipo de erro ou tipo de arquivo.</span><span class="sxs-lookup"><span data-stu-id="306e8-112">Select the errors you want to remediate by clicking the radio button next to either the error type or file type.</span></span>  <span data-ttu-id="306e8-113">No exemplo a seguir, estamos corrigindo um arquivo protegido por senha.</span><span class="sxs-lookup"><span data-stu-id="306e8-113">In the following example, we're remediating a password protected file.</span></span>

3. <span data-ttu-id="306e8-114">Clique em **nova correção de erro**.</span><span class="sxs-lookup"><span data-stu-id="306e8-114">Click **New error remediation**.</span></span>

    <span data-ttu-id="306e8-115">O fluxo de trabalho de correção de erro é iniciado com um estágio de preparação em que os arquivos com erros são copiados para um local de armazenamento do Azure fornecido pela Microsoft para que você possa baixá-los para o computador local para correção.</span><span class="sxs-lookup"><span data-stu-id="306e8-115">The error remediation workflow starts with a preparation stage where the files with errors are copied to a Microsoft-provided Azure Storage location so that you can download them to your local computer to remediate.</span></span>

    ![Preparando correção de erro](media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. <span data-ttu-id="306e8-117">Após a conclusão da preparação, clique em **Avançar: baixar arquivos** para continuar com o download.</span><span class="sxs-lookup"><span data-stu-id="306e8-117">After the preparation is complete, click **Next: Download files** to proceed with download.</span></span>

    ![Baixar arquivos](media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. <span data-ttu-id="306e8-119">Para baixar arquivos, especifique o **caminho de destino para download**.</span><span class="sxs-lookup"><span data-stu-id="306e8-119">To download files, specify the **Destination path for download**.</span></span> <span data-ttu-id="306e8-120">Este é o caminho para a pasta pai no computador local em que o arquivo será baixado.</span><span class="sxs-lookup"><span data-stu-id="306e8-120">This is a path to the parent folder on your local computer where the file will be downloaded.</span></span>  <span data-ttu-id="306e8-121">O caminho padrão,%USERPROFILE%\Downloads\errors, aponta para a pasta downloads do usuário conectado.</span><span class="sxs-lookup"><span data-stu-id="306e8-121">The default path, %USERPROFILE%\Downloads\errors, points to the logged-in user's downloads folder.</span></span> <span data-ttu-id="306e8-122">Você pode alterar esse caminho, se desejado.</span><span class="sxs-lookup"><span data-stu-id="306e8-122">You can change this path if desired.</span></span> <span data-ttu-id="306e8-123">Se você alterar, recomendamos que você use um caminho de arquivo local para o melhor desempenho.</span><span class="sxs-lookup"><span data-stu-id="306e8-123">If you do change it, we recommend that you use a local file path for the best performance.</span></span> <span data-ttu-id="306e8-124">Não use um caminho de rede remoto.</span><span class="sxs-lookup"><span data-stu-id="306e8-124">Don't use a remote network path.</span></span> <span data-ttu-id="306e8-125">Por exemplo, você poderia usar o caminho **C:\Remediation**.</span><span class="sxs-lookup"><span data-stu-id="306e8-125">For example, you could use the path **C:\Remediation**.</span></span> 

   <span data-ttu-id="306e8-126">O caminho para a pasta pai é automaticamente adicionado ao comando AzCopy (como o valor do parâmetro **/dest** ).</span><span class="sxs-lookup"><span data-stu-id="306e8-126">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Dest** parameter).</span></span>

6. <span data-ttu-id="306e8-127">Copie o comando predefinido clicando em **copiar para área de transferência**.</span><span class="sxs-lookup"><span data-stu-id="306e8-127">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="306e8-128">Abra um prompt de comando do Windows, Cole o comando AzCopy e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="306e8-128">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span>  

    ![Preparar para correção de erros](media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)    

    > [!NOTE]
    > <span data-ttu-id="306e8-130">Você deve usar o AzCopy v 8.1 para usar com êxito o comando fornecido na página **baixar arquivos** .</span><span class="sxs-lookup"><span data-stu-id="306e8-130">You must use AzCopy v8.1 to successfully use the command that's provided on the **Download files** page.</span></span> <span data-ttu-id="306e8-131">Você também deve usar o AzCopy v 8.1 para carregar os arquivos na etapa 10.</span><span class="sxs-lookup"><span data-stu-id="306e8-131">You also must use AzCopy v8.1 to upload the files in step 10.</span></span> <span data-ttu-id="306e8-132">Para instalar esta versão do AzCopy, confira [transferir dados com o AzCopy v 8.1 no Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="306e8-132">To install this version of AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="306e8-133">Se o comando AzCopy fornecido falhar, confira [solucionar problemas de AzCopy na descoberta eletrônica avançada](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="306e8-133">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

    <span data-ttu-id="306e8-134">Os arquivos que você selecionou são baixados para o local que você especificou na etapa 5.</span><span class="sxs-lookup"><span data-stu-id="306e8-134">The files that you selected are downloaded to the location that you specified in step 5.</span></span> <span data-ttu-id="306e8-135">Na pasta pai (por exemplo, **C:\Remediation**), a seguinte estrutura de subpastas é criada automaticamente:</span><span class="sxs-lookup"><span data-stu-id="306e8-135">In the parent folder (for example, **C:\Remediation**), the following subfolder structure is automatically created:</span></span>

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - <span data-ttu-id="306e8-136">A *subpasta 1* é nomeada com a ID do caso ou do conjunto de revisão, dependendo do escopo selecionado na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="306e8-136">*Subfolder 1* is named with the ID for the case or the review set, depending on the scope that you selected in step 1.</span></span>

    - <span data-ttu-id="306e8-137">A *subpasta 2* é nomeada com a ID de arquivo do arquivo baixado</span><span class="sxs-lookup"><span data-stu-id="306e8-137">*Subfolder 2* is named with the file ID of the downloaded file</span></span>

    - <span data-ttu-id="306e8-138">O arquivo baixado está localizado na *subpasta 2* e também é chamado de ID de arquivo.</span><span class="sxs-lookup"><span data-stu-id="306e8-138">The downloaded file is located in *Subfolder 2* and is also named with the file ID.</span></span>

    <span data-ttu-id="306e8-139">Veja um exemplo do caminho da pasta e o nome do arquivo de erro que é criado quando os itens são baixados para a pasta pai **C:\Remediation** :</span><span class="sxs-lookup"><span data-stu-id="306e8-139">Here's an example of the folder path and error file name that's created when items are downloaded to the **C:\Remediation** parent folder:</span></span>

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    <span data-ttu-id="306e8-140">Se vários arquivos forem baixados, cada um é baixado para uma subpasta nomeada com a ID de arquivo.</span><span class="sxs-lookup"><span data-stu-id="306e8-140">If multiple files are downloaded, each one is downloaded to a subfolder that's named with the file ID.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="306e8-141">Ao carregar arquivos na etapa 9 e na etapa 10, os arquivos corrigidos devem ter o mesmo nome de arquivo e estar localizados na mesma estrutura de subpastas.</span><span class="sxs-lookup"><span data-stu-id="306e8-141">When you upload files in step 9 and step 10, the remediated files must have that same filename and be located in the same subfolder structure.</span></span> <span data-ttu-id="306e8-142">Os nomes de subpasta e de arquivo são usados para associar o arquivo corrigido ao arquivo de erro original.</span><span class="sxs-lookup"><span data-stu-id="306e8-142">The subfolder and file names are used to associated the remediated file with the original error file.</span></span> <span data-ttu-id="306e8-143">Se a estrutura de pastas ou os nomes de arquivo forem alterados, você receberá o `Cannot apply Error Remediation to the current Workingset`seguinte erro:.</span><span class="sxs-lookup"><span data-stu-id="306e8-143">If the folder structure or file names are changed, you'll receive the following error: `Cannot apply Error Remediation to the current Workingset`.</span></span> <span data-ttu-id="306e8-144">Para evitar problemas, recomendamos que você mantenha os arquivos corrigidos na mesma estrutura de pastas e subpastas pai.</span><span class="sxs-lookup"><span data-stu-id="306e8-144">To prevent any issues, we recommend that keep the remediated files in the same parent folder and subfolder structure.</span></span>

7. <span data-ttu-id="306e8-145">Depois de baixar os arquivos, você pode corrigi-los com uma ferramenta apropriada.</span><span class="sxs-lookup"><span data-stu-id="306e8-145">After downloading the files, you can remediate them with an appropriate tool.</span></span> <span data-ttu-id="306e8-146">Para arquivos protegidos por senha, há várias ferramentas de quebra de senha que você pode usar.</span><span class="sxs-lookup"><span data-stu-id="306e8-146">For password-protected files, there are several password cracking tools you can use.</span></span> <span data-ttu-id="306e8-147">Se você souber as senhas dos arquivos, poderá abri-las e remover a proteção por senha.</span><span class="sxs-lookup"><span data-stu-id="306e8-147">If you know the passwords for the files, you can open them and remove the password protection.</span></span>

8. <span data-ttu-id="306e8-148">Retorne à descoberta eletrônica avançada e o assistente de correção de erros e clique em **Avançar: carregar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="306e8-148">Return to Advanced eDiscovery and the error remediation wizard and then click **Next: Upload files**.</span></span>  <span data-ttu-id="306e8-149">Isso é movido para a próxima página onde você pode carregar os arquivos.</span><span class="sxs-lookup"><span data-stu-id="306e8-149">This moves to the next page where you can now upload the files.</span></span>

    ![Carregar arquivos](media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. <span data-ttu-id="306e8-151">Especifique a pasta pai onde os arquivos corrigidos estão localizados na caixa de texto **caminho para o local de arquivos** .</span><span class="sxs-lookup"><span data-stu-id="306e8-151">Specify the parent folder where the remediated files are located in the **Path to location of files** text box.</span></span> <span data-ttu-id="306e8-152">Novamente, a pasta pai deve ter a mesma estrutura de subpasta que foi criada quando você baixou os arquivos.</span><span class="sxs-lookup"><span data-stu-id="306e8-152">Again, the parent folder must have the same subfolder structure that was created when you downloaded the files.</span></span>

    <span data-ttu-id="306e8-153">O caminho para a pasta pai é automaticamente adicionado ao comando AzCopy (como o valor do parâmetro **/Source** ).</span><span class="sxs-lookup"><span data-stu-id="306e8-153">The path to the parent folder is automatically added to AzCopy command (as the value of the **/Source** parameter).</span></span>

10. <span data-ttu-id="306e8-154">Copie o comando predefinido clicando em **copiar para área de transferência**.</span><span class="sxs-lookup"><span data-stu-id="306e8-154">Copy the predefined command by clicking **Copy to clipboard**.</span></span> <span data-ttu-id="306e8-155">Abra um prompt de comando do Windows, Cole o comando AzCopy e pressione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="306e8-155">Open a Windows Command Prompt, paste the AzCopy command, and then press **Enter**.</span></span> <span data-ttu-id="306e8-156">carregar os arquivos.</span><span class="sxs-lookup"><span data-stu-id="306e8-156">upload the files.</span></span>

    ![ff2ff691-629f-4065-9b37-5333f937daf6. png](media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. <span data-ttu-id="306e8-158">Depois de executar o comando AzCopy, clique em **Avançar: processar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="306e8-158">After you run the AzCopy command, click **Next: Process files**.</span></span>

    <span data-ttu-id="306e8-159">Quando o processamento estiver concluído, você poderá ir para a revisão definir e exibir os arquivos corrigidos.</span><span class="sxs-lookup"><span data-stu-id="306e8-159">When processing is complete, you can go to review set and view the remediated files.</span></span> 

## <a name="what-happens-when-files-are-remediated"></a><span data-ttu-id="306e8-160">O que acontece quando os arquivos são corrigidos</span><span class="sxs-lookup"><span data-stu-id="306e8-160">What happens when files are remediated</span></span>

<span data-ttu-id="306e8-161">Quando os arquivos corrigidos são carregados, os metadados originais são preservados, exceto os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="306e8-161">When remediated files are uploaded, the original metadata is preserved except for the following fields:</span></span> 

- <span data-ttu-id="306e8-162">ExtractedTextSize</span><span class="sxs-lookup"><span data-stu-id="306e8-162">ExtractedTextSize</span></span>
- <span data-ttu-id="306e8-163">HasText</span><span class="sxs-lookup"><span data-stu-id="306e8-163">HasText</span></span>
- <span data-ttu-id="306e8-164">IsErrorRemediate</span><span class="sxs-lookup"><span data-stu-id="306e8-164">IsErrorRemediate</span></span>
- <span data-ttu-id="306e8-165">Loadid</span><span class="sxs-lookup"><span data-stu-id="306e8-165">LoadId</span></span>
- <span data-ttu-id="306e8-166">ProcessingErrorMessage</span><span class="sxs-lookup"><span data-stu-id="306e8-166">ProcessingErrorMessage</span></span>
- <span data-ttu-id="306e8-167">ProcessingStatus</span><span class="sxs-lookup"><span data-stu-id="306e8-167">ProcessingStatus</span></span>
- <span data-ttu-id="306e8-168">Texto</span><span class="sxs-lookup"><span data-stu-id="306e8-168">Text</span></span>
- <span data-ttu-id="306e8-169">WordCount</span><span class="sxs-lookup"><span data-stu-id="306e8-169">WordCount</span></span>
- <span data-ttu-id="306e8-170">WorkingsetId</span><span class="sxs-lookup"><span data-stu-id="306e8-170">WorkingsetId</span></span>

<span data-ttu-id="306e8-171">Para obter uma definição de todos os campos de metadados na descoberta eletrônica avançada, confira [campos de metadados do documento](document-metadata-fields.md).</span><span class="sxs-lookup"><span data-stu-id="306e8-171">For a definition of all metadata fields in Advanced eDiscovery, see [Document metadata fields](document-metadata-fields.md).</span></span>
