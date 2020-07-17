---
title: Carregar dados que não sejam da Microsoft 365 em um conjunto de revisão
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
description: Saiba como importar dados que não são da Microsoft 365 para uma análise definida para análise em um caso de descoberta eletrônica avançada.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f9b506edc55da1916ae908eaa7ca619ba7300f87
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815458"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a><span data-ttu-id="f650d-103">Carregar dados que não sejam da Microsoft 365 em um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="f650d-103">Load non-Microsoft 365 data into a review set</span></span>

<span data-ttu-id="f650d-104">Nem todos os documentos que você precisa analisar na descoberta eletrônica avançada estão localizados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f650d-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Microsoft 365.</span></span> <span data-ttu-id="f650d-105">Com o recurso de importação de dados não-Microsoft 365 na descoberta eletrônica avançada, você pode carregar documentos que não estão localizados no Microsoft 365 em um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="f650d-105">With the non-Microsoft 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Microsoft 365 to a review set.</span></span> <span data-ttu-id="f650d-106">Este artigo mostra como trazer documentos que não são da Microsoft 365 para a descoberta eletrônica avançada para análise.</span><span class="sxs-lookup"><span data-stu-id="f650d-106">This article shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>

## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="f650d-107">Requisitos para carregar conteúdo não-Office 365</span><span class="sxs-lookup"><span data-stu-id="f650d-107">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="f650d-108">O uso do recurso de upload que não é da Microsoft 365 descrito neste artigo requer que você tenha o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f650d-108">Using the upload non-Microsoft 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="f650d-109">Todos os responsáveis que você deseja associar conteúdo que não seja da Microsoft 365 devem receber a licença apropriada.</span><span class="sxs-lookup"><span data-stu-id="f650d-109">All custodians that you want to associate non-Microsoft 365 content to must be assigned the appropriate license.</span></span> <span data-ttu-id="f650d-110">Para obter mais informações, consulte [introdução à descoberta eletrônica avançada](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span><span class="sxs-lookup"><span data-stu-id="f650d-110">For more information, see [Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span></span>

- <span data-ttu-id="f650d-111">Uma ocorrência de descoberta eletrônica avançada existente.</span><span class="sxs-lookup"><span data-stu-id="f650d-111">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="f650d-112">Os responsáveis devem ser adicionados ao caso antes que você possa carregar e associar os dados que não são da Microsoft 365 a eles.</span><span class="sxs-lookup"><span data-stu-id="f650d-112">Custodians must be added to the case before you can upload and associate the non-Microsoft 365 data to them.</span></span>

- <span data-ttu-id="f650d-113">Dados que não são da Microsoft 365 devem ser um tipo de arquivo com suporte da descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="f650d-113">Non-Microsoft 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="f650d-114">Para saber mais, confira [tipos de arquivo com suporte na descoberta eletrônica avançada](supported-filetypes-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="f650d-114">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="f650d-115">Todos os arquivos carregados em um conjunto de revisão devem estar localizados em pastas, onde cada pasta é associada a um determinado local.</span><span class="sxs-lookup"><span data-stu-id="f650d-115">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="f650d-116">Os nomes dessas pastas devem usar o seguinte formato de nome: *alias@domainname*.</span><span class="sxs-lookup"><span data-stu-id="f650d-116">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="f650d-117">O alias@domainname deve ser o alias e o domínio do Microsoft 365 do usuário.</span><span class="sxs-lookup"><span data-stu-id="f650d-117">The alias@domainname must be the user's Microsoft 365 alias and domain.</span></span> <span data-ttu-id="f650d-118">Você pode coletar todas as pastas de alias@domainname em uma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="f650d-118">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="f650d-119">A pasta raiz pode conter apenas as pastas alias@domainname.</span><span class="sxs-lookup"><span data-stu-id="f650d-119">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="f650d-120">Não há suporte para arquivos soltos na pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="f650d-120">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="f650d-121">A estrutura de pastas para os dados que não são da Microsoft 365 que você deseja carregar seria semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="f650d-121">The folder structure for the non-Microsoft 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="f650d-122">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f650d-122">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="f650d-123">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f650d-123">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="f650d-124">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="f650d-124">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="f650d-125">Onde abraham.mcmahon@contoso.com, jewell.gordon@contoso.com e staci.gonzalez@contoso.com são os endereços SMTP dos responsáveis no caso.</span><span class="sxs-lookup"><span data-stu-id="f650d-125">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Estrutura de pastas de carregamento de dados não-Microsoft 365](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="f650d-127">Uma conta atribuída ao grupo de função Gerenciador de descoberta eletrônica (e adicionada como administrador de descoberta eletrônica).</span><span class="sxs-lookup"><span data-stu-id="f650d-127">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="f650d-128">A ferramenta AzCopy v 8.1 instalada em um computador que tem acesso à estrutura de pasta de conteúdo não-Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f650d-128">The AzCopy v8.1 tool installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span> <span data-ttu-id="f650d-129">Para instalar o AzCopy, confira [transferir dados com o AzCopy v 8.1 no Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="f650d-129">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="f650d-130">Certifique-se de instalar o AzCopy no local padrão, que é **% ProgramFiles (x86)% \ Microsoft SDKs\Azure\AzCopy**.</span><span class="sxs-lookup"><span data-stu-id="f650d-130">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="f650d-131">Você deve usar o AzCopy v 8.1.</span><span class="sxs-lookup"><span data-stu-id="f650d-131">You must use AzCopy v8.1.</span></span> <span data-ttu-id="f650d-132">Outras versões do AzCopy podem não funcionar ao carregar dados que não sejam da Microsoft 365 na descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="f650d-132">Other versions of AzCopy may not work when loading non-Microsoft 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a><span data-ttu-id="f650d-133">Carregar conteúdo não-Microsoft 365 na descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="f650d-133">Upload non-Microsoft 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="f650d-134">Como um gerente de descoberta eletrônica ou administrador de descoberta eletrônica, abra descoberta eletrônica avançada e vá para o caso em que os dados não-Microsoft 365 serão carregados.</span><span class="sxs-lookup"><span data-stu-id="f650d-134">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, and go to the case that the non-Microsoft 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="f650d-135">Clique em **revisar conjuntos**e selecione o conjunto de revisão para carregar os dados que não são da Microsoft 365 para o.</span><span class="sxs-lookup"><span data-stu-id="f650d-135">Click **Review sets**, and then select the review set to upload the non-Microsoft 365 data to.</span></span>  <span data-ttu-id="f650d-136">Se você não tiver um conjunto de revisão, você pode criar um.</span><span class="sxs-lookup"><span data-stu-id="f650d-136">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="f650d-137">No conjunto de revisão, clique em **gerenciar o conjunto de revisão**e, em seguida, clique em **Exibir carregamentos** no bloco de **dados não-Microsoft 365** .</span><span class="sxs-lookup"><span data-stu-id="f650d-137">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Microsoft 365 data** tile.</span></span>

4. <span data-ttu-id="f650d-138">Clique em **carregar arquivos** para iniciar o assistente de importação de dados.</span><span class="sxs-lookup"><span data-stu-id="f650d-138">Click **Upload files** to start the data import wizard.</span></span>

   ![Carregar arquivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="f650d-140">A primeira etapa do assistente prepara um local de armazenamento do Azure seguro fornecido pela Microsoft para carregar os arquivos.</span><span class="sxs-lookup"><span data-stu-id="f650d-140">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="f650d-141">Quando a preparação estiver concluída, o botão **Avançar: carregar arquivos** se tornará ativo.</span><span class="sxs-lookup"><span data-stu-id="f650d-141">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Importação não-Microsoft 365: preparar](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="f650d-143">Clique em **Avançar: carregar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="f650d-143">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="f650d-144">Na página **carregar arquivos** , faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f650d-144">On the **Upload files** page, do the following:</span></span>

   ![Importação não-Microsoft 365: carregar arquivos](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="f650d-146">a.</span><span class="sxs-lookup"><span data-stu-id="f650d-146">a.</span></span> <span data-ttu-id="f650d-147">Na caixa **caminho para o local dos arquivos** , verifique ou digite o local da pasta raiz onde você armazenou os dados que não são da Microsoft 365 que você deseja carregar.</span><span class="sxs-lookup"><span data-stu-id="f650d-147">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Microsoft 365 data you want to upload.</span></span> <span data-ttu-id="f650d-148">Por exemplo, para o local dos arquivos de exemplo mostrados na **seção antes de começar**, digite **%USERPROFILE\Downloads\nonO365**.</span><span class="sxs-lookup"><span data-stu-id="f650d-148">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="f650d-149">Fornecer o local correto garante que o comando AzCopy exibido em caixa abaixo do caminho seja atualizado corretamente.</span><span class="sxs-lookup"><span data-stu-id="f650d-149">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="f650d-150">b.</span><span class="sxs-lookup"><span data-stu-id="f650d-150">b.</span></span> <span data-ttu-id="f650d-151">Clique em **copiar para área de transferência** para copiar o comando exibido na caixa.</span><span class="sxs-lookup"><span data-stu-id="f650d-151">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="f650d-152">Inicie um prompt de comando do Windows, Cole o comando copiado na etapa anterior e pressione **Enter** para iniciar o comando AzCopy.</span><span class="sxs-lookup"><span data-stu-id="f650d-152">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="f650d-153">Depois de iniciar o comando, os arquivos que não são da Microsoft 365 serão carregados no local de armazenamento do Azure que foi preparado na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="f650d-153">After you start the command, the non-Microsoft 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Importação não-Microsoft 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="f650d-155">Conforme mencionado anteriormente, você deve usar o AzCopy v 8.1 para usar com êxito o comando fornecido na página **carregar arquivos** .</span><span class="sxs-lookup"><span data-stu-id="f650d-155">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="f650d-156">Se o comando AzCopy fornecido falhar, confira [solucionar problemas de AzCopy na descoberta eletrônica avançada](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="f650d-156">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="f650d-157">Volte para o centro de conformidade & segurança e clique em **Avançar: processar arquivos** no assistente.</span><span class="sxs-lookup"><span data-stu-id="f650d-157">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="f650d-158">Isso inicia o processamento, extração de texto e indexação de arquivos que não são da Microsoft 365 que foram carregados no local de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="f650d-158">This initiates processing, text extraction, and indexing of the non-Microsoft 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="f650d-159">Acompanhe o progresso do processamento dos arquivos na página **arquivos de processo** ou na guia **trabalhos** , exibindo um trabalho chamado **adição de dados que não são da Microsoft 365 a um conjunto de revisão**.</span><span class="sxs-lookup"><span data-stu-id="f650d-159">Track the progress of processing the files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Microsoft 365 data to a review set**.</span></span>  <span data-ttu-id="f650d-160">Depois que o trabalho for concluído, os novos arquivos estarão disponíveis no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="f650d-160">After the job is finished, the new files will be available in the review set.</span></span>

   ![Importação não-Microsoft 365: processar arquivos](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="f650d-162">Depois que o processamento for concluído, você poderá fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="f650d-162">After the processing is finished, you can close the wizard.</span></span>
