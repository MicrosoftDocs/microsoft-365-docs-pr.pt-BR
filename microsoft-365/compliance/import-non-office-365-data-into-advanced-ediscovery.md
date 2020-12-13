---
title: Importar conteúdo não-Microsoft 365 para análise de descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Como as etapas para importar o conteúdo que não está armazenado no Microsoft 365 em um blob do Azure para que ele possa ser analisado com o AeD
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 03220e6baf16662ad8dfa970ef4d7077d08b0826
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662896"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a><span data-ttu-id="33ba3-103">Importar conteúdo não-Microsoft 365 para análise de descoberta eletrônica avançada (clássico)</span><span class="sxs-lookup"><span data-stu-id="33ba3-103">Import non-Microsoft 365 content for Advanced eDiscovery (classic) analysis</span></span>

<span data-ttu-id="33ba3-104">Nem todos os documentos que você pode precisar analisar com a descoberta eletrônica avançada residirão no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33ba3-104">Not all documents that you may need to analyze with Advanced eDiscovery will live in Microsoft 365.</span></span> <span data-ttu-id="33ba3-105">Com o recurso de importação de conteúdo não-Microsoft 365 na descoberta eletrônica avançada, é possível carregar documentos que não estão no Microsoft 365 (exceto arquivos PST) em um caso vinculado, BLOB de armazenamento do Azure e analisá-los com a descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="33ba3-105">With the Non-Microsoft 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Microsoft 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery.</span></span> <span data-ttu-id="33ba3-106">Este procedimento mostra como trazer documentos que não são da Microsoft 365 para a descoberta eletrônica avançada para análise.</span><span class="sxs-lookup"><span data-stu-id="33ba3-106">This procedure shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="33ba3-p102">A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="33ba3-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="33ba3-109">Você pode adquirir uma assinatura de complemento de armazenamento de dados de descoberta eletrônica avançada para seu conteúdo que não seja da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33ba3-109">You can purchase an Advanced eDiscovery data storage add-on subscription for your non-Microsoft 365 content.</span></span> <span data-ttu-id="33ba3-110">Isso está disponível exclusivamente para conteúdo que deve ser analisado com a descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="33ba3-110">This is exclusively available for content that is to be analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="33ba3-111">Siga as etapas em [comprar ou editar um complemento para o Microsoft 365 for Business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) e adquirir o complemento avançado de armazenamento de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="33ba3-111">Follow the steps in [Buy or edit an add-on for Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) and purchase the Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="33ba3-112">Requisitos para carregar conteúdo não-Office 365</span><span class="sxs-lookup"><span data-stu-id="33ba3-112">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="33ba3-113">O uso do recurso de upload que não é do Office 365 conforme descrito neste procedimento exige que você tenha:</span><span class="sxs-lookup"><span data-stu-id="33ba3-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="33ba3-114">Um Office 365 E3 com um complemento de conformidade avançada ou uma assinatura e5.</span><span class="sxs-lookup"><span data-stu-id="33ba3-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription.</span></span>
    
- <span data-ttu-id="33ba3-115">Todos os responsáveis cujo conteúdo que não seja do Office 365 será carregado precisarão ter E3 com o complemento de conformidade avançada ou com licenças e5.</span><span class="sxs-lookup"><span data-stu-id="33ba3-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses.</span></span>
    
- <span data-ttu-id="33ba3-116">Uma ocorrência de descoberta eletrônica existente.</span><span class="sxs-lookup"><span data-stu-id="33ba3-116">An existing eDiscovery case.</span></span>
    
- <span data-ttu-id="33ba3-117">Todos os arquivos para carregamento são coletados em pastas onde há uma pasta por responsáveis e o nome das pastas está nesse formato  *alias@domainname*  .</span><span class="sxs-lookup"><span data-stu-id="33ba3-117">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  .</span></span> <span data-ttu-id="33ba3-118">O  *alias@domainname*  deve ser Users alias e Domain do Office 365.</span><span class="sxs-lookup"><span data-stu-id="33ba3-118">The  *alias@domainname*  must be users Office 365 alias and domain.</span></span> <span data-ttu-id="33ba3-119">Você pode coletar todas as pastas de  *alias@domainname*  em uma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="33ba3-119">You can collect all the  *alias@domainname*  folders into a root folder.</span></span> <span data-ttu-id="33ba3-120">A pasta raiz pode conter apenas as pastas  *alias@domainname*  , não deve haver arquivos soltos na pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="33ba3-120">The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder.</span></span>
    
- <span data-ttu-id="33ba3-121">Uma conta que seja um Gerenciador de descoberta eletrônica ou administrador de descoberta eletrônica.</span><span class="sxs-lookup"><span data-stu-id="33ba3-121">An account that is either an eDiscovery Manager or eDiscovery Administrator.</span></span>
    
- <span data-ttu-id="33ba3-122">[Ferramentas de armazenamento do Microsoft Azure](https://aka.ms/downloadazcopy) instaladas em um computador que tem acesso à estrutura de pasta de conteúdo não-Office 365.</span><span class="sxs-lookup"><span data-stu-id="33ba3-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="33ba3-123">Carregar conteúdo que não seja do Office 365 na descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="33ba3-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>


1. <span data-ttu-id="33ba3-124">Como um Gerenciador de descoberta eletrônica ou administrador de descoberta eletrônica, abra o **eDiscovery** e abra o caso em que os dados não-Office 365 serão carregados.</span><span class="sxs-lookup"><span data-stu-id="33ba3-124">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to.</span></span> <span data-ttu-id="33ba3-125">Se você precisar criar uma ocorrência, consulte [gerenciar casos de descoberta eletrônica no &amp; centro de conformidade de segurança](ediscovery-cases.md).</span><span class="sxs-lookup"><span data-stu-id="33ba3-125">If you need to create a case, see [Manage eDiscovery cases in the Security &amp; Compliance Center](ediscovery-cases.md).</span></span>
    
2. <span data-ttu-id="33ba3-126">Clique em **alternar para descoberta eletrônica avançada**.</span><span class="sxs-lookup"><span data-stu-id="33ba3-126">Click **Switch to Advanced eDiscovery**.</span></span>

3. <span data-ttu-id="33ba3-127">Selecione **conjuntos de revisão** no menu.</span><span class="sxs-lookup"><span data-stu-id="33ba3-127">Select **Review Sets** from the menu.</span></span>

4. <span data-ttu-id="33ba3-128">Selecione um conjunto de revisão existente ou escolha **Adicionar conjunto de revisão**.</span><span class="sxs-lookup"><span data-stu-id="33ba3-128">Select an existing Review Set or choose **Add Review Set**.</span></span>

5. <span data-ttu-id="33ba3-129">Selecione **gerenciar conjunto de revisão**.</span><span class="sxs-lookup"><span data-stu-id="33ba3-129">Select **Manage review set**.</span></span>

6. <span data-ttu-id="33ba3-130">No cartão de dados não-Office 365, selecione **Exibir uploads**.</span><span class="sxs-lookup"><span data-stu-id="33ba3-130">In the Non-Office 365 data card, select **View Uploads**.</span></span>

7. <span data-ttu-id="33ba3-131">Escolha **carregar arquivos** para iniciar o assistente de carregamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="33ba3-131">Choose **Upload files** to start the file upload wizard.</span></span>

8. <span data-ttu-id="33ba3-132">A primeira guia é **1. Preparar etapa**.</span><span class="sxs-lookup"><span data-stu-id="33ba3-132">The first tab is **1. Prepare step**.</span></span> <span data-ttu-id="33ba3-133">Selecione **Avançar: carregar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="33ba3-133">Select **Next: Upload files**.</span></span>

9. <span data-ttu-id="33ba3-134">No **2. Guia carregar arquivos** você será solicitado a baixar AzCopy.exe se ainda não tiver feito isso e, em seguida, fornecer o caminho para o local do arquivo.</span><span class="sxs-lookup"><span data-stu-id="33ba3-134">On the **2. Upload files** tab you will be prompted to download AzCopy.exe if you have not done so already, and then to provide the path to the file location.</span></span> <span data-ttu-id="33ba3-135">Por exemplo, fornecerá `C:\Upload`  o comando para executar AzCopy.exe.</span><span class="sxs-lookup"><span data-stu-id="33ba3-135">For example, `C:\Upload`  will give you the command to execute AzCopy.exe.</span></span> <span data-ttu-id="33ba3-136">Usando o `C:\Upload` , você verá:</span><span class="sxs-lookup"><span data-stu-id="33ba3-136">Using `C:\Upload`, you will see:</span></span>

   `"%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy\AzCopy.exe" /Source:"c:\upload" /Dest:"https://spnam03salinkexternal003.blob.core.windows.net/16d13440-a6a4-4bc5-a82b-10ac9cfe9d7c-1601401811-externalstore?sv=2017-07-29&sr=c&si=ExternalStore63%7C0&sig=9Dq5v20TwkxByYDHhIEx%2FHSLlmlqUjY0njkJyTO0zGA%3D" /s`
  
10. <span data-ttu-id="33ba3-137">Abra uma janela de prompt de comando e execute o comando AzCopy.exe para importar os dados para o Azure.</span><span class="sxs-lookup"><span data-stu-id="33ba3-137">Open a command prompt window and execute the AzCopy.exe command to import the data into Azure.</span></span> <span data-ttu-id="33ba3-138">Depois de carregar todos os dados, selecione **Avançar: processar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="33ba3-138">Once it has loaded all of the data, select **Next: Process files**.</span></span>

11. <span data-ttu-id="33ba3-139">A próxima guia é **3. Processe arquivos** em que você verá os responsáveis que têm dados associados a eles e também mostrará o progresso dos dados que estão sendo importados.</span><span class="sxs-lookup"><span data-stu-id="33ba3-139">The next tab is **3. Process files** where you will see the custodians that have data associated with them and will also show you the progress of the data being imported.</span></span>
        
    <span data-ttu-id="33ba3-140">Para obter mais informações sobre a sintaxe Azcopy, consulte [transferir dados com o Azcopy no Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="33ba3-140">For more information on Azcopy syntax, see [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span> 
    
    <span data-ttu-id="33ba3-141">Para obter mais detalhes sobre o processamento avançado de descoberta eletrônica, consulte [executar o módulo de processo e carregar dados na descoberta eletrônica avançada (clássico)](run-the-process-module-and-load-data-in-advanced-ediscovery.md).</span><span class="sxs-lookup"><span data-stu-id="33ba3-141">For more details on Advanced eDiscovery Processing, see [Run the Process module and load data in Advanced eDiscovery (classic)](run-the-process-module-and-load-data-in-advanced-ediscovery.md).</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="33ba3-142">Deve haver uma pasta raiz por usuário e o nome da pasta deve estar no formato <b>alias@domainname</b>  .</span><span class="sxs-lookup"><span data-stu-id="33ba3-142">There must be one root folder per user and the folder name must be in the <b>alias@domainname</b>  format.</span></span> 
   
    > [!IMPORTANT]
    > <span data-ttu-id="33ba3-143">Depois que o contêiner for processado com êxito na descoberta eletrônica avançada, você não poderá mais adicionar novo conteúdo ao armazenamento SAS no Azure.</span><span class="sxs-lookup"><span data-stu-id="33ba3-143">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure.</span></span> <span data-ttu-id="33ba3-144">Se você coletar conteúdo adicional e quiser adicioná-lo ao caso da análise de descoberta eletrônica avançada, você deve criar um novo contêiner de **dados que não seja do Office 365** e repetir este procedimento.</span><span class="sxs-lookup"><span data-stu-id="33ba3-144">If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="33ba3-145">Se o contêiner  *não for processado com êxito devido a problemas de nomenclatura de pasta*  e você corrigir os problemas, ainda será necessário criar um novo contêiner e reconectar e carregar novamente usando os procedimentos deste artigo.</span><span class="sxs-lookup"><span data-stu-id="33ba3-145">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span>
