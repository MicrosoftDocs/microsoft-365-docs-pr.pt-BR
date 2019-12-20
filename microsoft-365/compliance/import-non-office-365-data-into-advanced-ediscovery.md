---
title: Importar conteúdo não-Office 365 para análise de descoberta eletrônica avançada
ms.author: chrfox
author: chrfox
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
description: Como as etapas para importar o conteúdo que não é armazenado no O365 em um blob do Azure para que ele possa ser analisado com o AeD
ms.openlocfilehash: aa14a54c20ac580c6412e8dc534ec44520abb3c8
ms.sourcegitcommit: 6ae69c40bafa6aef633789c3df0fa20590bdcf40
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "40823783"
---
# <a name="import-non-office-365-content-for-advanced-ediscovery-analysis"></a><span data-ttu-id="23b09-103">Importar conteúdo não-Office 365 para análise de descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="23b09-103">Import non-Office 365 content for Advanced eDiscovery analysis</span></span>

<span data-ttu-id="23b09-104">Nem todos os documentos que você pode precisar analisar com a descoberta eletrônica avançada do Office 365 residirão no Office 365.</span><span class="sxs-lookup"><span data-stu-id="23b09-104">Not all documents that you may need to analyze with Office 365 Advanced eDiscovery will live in Office 365.</span></span> <span data-ttu-id="23b09-105">Com o recurso de importação de conteúdo não-Office 365 na descoberta eletrônica avançada, é possível carregar documentos que não estão no Office 365 (exceto arquivos PST) em um caso vinculado, BLOB de armazenamento do Azure e analisá-los com a descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="23b09-105">With the Non-Office 365 content import feature in Advanced eDiscovery you can upload documents that don't live in Office 365 (except PST files) into a case linked, Azure storage blob and analyze them with Advanced eDiscovery.</span></span> <span data-ttu-id="23b09-106">Este procedimento mostra como trazer documentos não-Office 365 para a descoberta eletrônica avançada para análise.</span><span class="sxs-lookup"><span data-stu-id="23b09-106">This procedure shows you how to bring your non-Office 365 documents into Advanced eDiscovery for analysis.</span></span>
  
> [!NOTE]
> <span data-ttu-id="23b09-p102">A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="23b09-p102">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="23b09-109">Você pode adquirir uma assinatura de complemento de armazenamento de dados de descoberta eletrônica avançada do Office 365 para seu conteúdo que não seja do Office 365.</span><span class="sxs-lookup"><span data-stu-id="23b09-109">You can purchase an Office 365 Advanced eDiscovery data storage add-on subscription for your non-Office 365 content.</span></span> <span data-ttu-id="23b09-110">Isso está disponível exclusivamente para conteúdo que deve ser analisado com a descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="23b09-110">This is exclusively available for content that is to be analyzed with Advanced eDiscovery.</span></span> <span data-ttu-id="23b09-111">Siga as etapas em [comprar ou editar e adicionar para o Office 365 for Business](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) e adquirir o complemento de armazenamento de descoberta eletrônica avançada do Office 365.</span><span class="sxs-lookup"><span data-stu-id="23b09-111">Follow the steps in [Buy or edit and add-on for Office 365 for business](https://support.office.com/article/Buy-or-edit-an-add-on-for-Office-365-for-business-4e7b57d6-b93b-457d-aecd-0ea58bff07a6) and purchase the Office 365 Advanced eDiscovery storage add-on.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="23b09-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="23b09-112">Before you begin</span></span>

<span data-ttu-id="23b09-113">O uso do recurso de upload que não é do Office 365 conforme descrito neste procedimento exige que você tenha:</span><span class="sxs-lookup"><span data-stu-id="23b09-113">Using the upload Non-Office 365 feature as described in this procedure requires that you have:</span></span>
  
- <span data-ttu-id="23b09-114">Um Office 365 E3 com um complemento de conformidade avançada ou uma assinatura e5</span><span class="sxs-lookup"><span data-stu-id="23b09-114">An Office 365 E3 with Advanced Compliance add-on or E5 subscription</span></span>
    
- <span data-ttu-id="23b09-115">Todos os responsáveis cujo conteúdo que não seja do Office 365 será carregado deverá ter E3 com o complemento avançado de conformidade ou licenças e5</span><span class="sxs-lookup"><span data-stu-id="23b09-115">All custodians whose non-Office 365 content will be uploaded must have E3 with Advanced Compliance add-on or E5 licenses</span></span>
    
- <span data-ttu-id="23b09-116">Uma ocorrência de descoberta eletrônica existente</span><span class="sxs-lookup"><span data-stu-id="23b09-116">An existing eDiscovery case</span></span>
    
- <span data-ttu-id="23b09-117">Todos os arquivos para carregamento são coletados em pastas onde há uma pasta por responsáveis e o nome das pastas está nesse formato *alias@domainname* .</span><span class="sxs-lookup"><span data-stu-id="23b09-117">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format  *alias@domainname*  .</span></span> <span data-ttu-id="23b09-118">O *alias@domainname* deve ser Users alias e Domain do Office 365.</span><span class="sxs-lookup"><span data-stu-id="23b09-118">The  *alias@domainname*  must be users Office 365 alias and domain.</span></span> <span data-ttu-id="23b09-119">Você pode coletar todas as pastas de *alias@domainname* em uma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="23b09-119">You can collect all the  *alias@domainname*  folders into a root folder.</span></span> <span data-ttu-id="23b09-120">A pasta raiz pode conter apenas as pastas *alias@domainname* , não deve haver arquivos soltos na pasta raiz</span><span class="sxs-lookup"><span data-stu-id="23b09-120">The root folder can only contain the  *alias@domainname*  folders, there must be no loose files in the root folder</span></span> 
    
- <span data-ttu-id="23b09-121">Uma conta que seja um Gerenciador de descoberta eletrônica ou administrador de descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="23b09-121">An account that is either an eDiscovery Manager or eDiscovery Administrator</span></span>
    
- <span data-ttu-id="23b09-122">[Ferramentas de armazenamento do Microsoft Azure](https://aka.ms/downloadazcopy) instaladas em um computador que tem acesso à estrutura de pasta de conteúdo não-Office 365.</span><span class="sxs-lookup"><span data-stu-id="23b09-122">[Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) installed on a computer that has access to the non-Office 365 content folder structure.</span></span> 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a><span data-ttu-id="23b09-123">Carregar conteúdo que não seja do Office 365 na descoberta eletrônica avançada</span><span class="sxs-lookup"><span data-stu-id="23b09-123">Upload non-Office 365 content into Advanced eDiscovery</span></span>


1. <span data-ttu-id="23b09-124">Como um Gerenciador de descoberta eletrônica ou administrador de descoberta eletrônica, abra o **eDiscovery**e abra o caso em que os dados não-Office 365 serão carregados.</span><span class="sxs-lookup"><span data-stu-id="23b09-124">As an eDiscovery Manager or eDiscovery Administrator, open **eDiscovery**, and open the case that the non-Office 365 data will be uploaded to.</span></span> <span data-ttu-id="23b09-125">Se você precisar criar uma ocorrência, consulte [gerenciar casos de descoberta eletrônica no centro de conformidade &amp; de segurança do Office 365](ediscovery-cases.md)</span><span class="sxs-lookup"><span data-stu-id="23b09-125">If you need to create a case, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md)</span></span>
    
2. <span data-ttu-id="23b09-126">Clique em **alternar para descoberta eletrônica avançada**</span><span class="sxs-lookup"><span data-stu-id="23b09-126">Click **Switch to Advanced eDiscovery**</span></span>
    
3. <span data-ttu-id="23b09-127">Em **tipo de origem** , selecione **dados não-Office 365**.</span><span class="sxs-lookup"><span data-stu-id="23b09-127">Under **Source type** select **Non-Office 365 data**.</span></span>
    
4. <span data-ttu-id="23b09-128">Clique em **Adicionar contêiner**.</span><span class="sxs-lookup"><span data-stu-id="23b09-128">Click **Add container**.</span></span> <span data-ttu-id="23b09-129">Nomeie o contêiner e adicione uma descrição.</span><span class="sxs-lookup"><span data-stu-id="23b09-129">Name the container and add a description.</span></span>
    
5. <span data-ttu-id="23b09-130">Selecione o contêiner recém-adicionado na lista de contêineres e copie a URL que aparece no painel de detalhes do contêiner e, em seguida, feche o painel</span><span class="sxs-lookup"><span data-stu-id="23b09-130">Select the newly added container from the container list and copy the URL that appears in the container details pane and then close the pane</span></span>
    
6. <span data-ttu-id="23b09-131">Abra um prompt de comando como administrador e altere o diretório para a pasta em que você tem o AzCopy instalado..</span><span class="sxs-lookup"><span data-stu-id="23b09-131">Open a command prompt as an administrator and change directory to folder where you have AzCopy installed..</span></span>
    
7. <span data-ttu-id="23b09-132">Construa a linha de comando AzCopy para carregar os arquivos da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="23b09-132">Construct the AzCopy command line to upload the files like this:</span></span>
    
    <span data-ttu-id="23b09-133">AzCopy/Source: " *caminho completo para a pasta raiz na máquina local* "/dest: " *URL do contêiner até mas não incluindo o?*</span><span class="sxs-lookup"><span data-stu-id="23b09-133">AzCopy /Source:" *full path to root folder on local machine*  " /Dest:"  *container URL up to but not including the ?*</span></span>  <span data-ttu-id="23b09-134">"/DestSAS:" *restante da URL do contêiner do? ao final* "/S.</span><span class="sxs-lookup"><span data-stu-id="23b09-134">" /DestSAS:"  *remainder of the container url from the ? to the end*  " /S.</span></span> 
    
    <span data-ttu-id="23b09-135">Por exemplo, usando estes valores:</span><span class="sxs-lookup"><span data-stu-id="23b09-135">For example, using these values:</span></span> 
    
  - <span data-ttu-id="23b09-136">pasta raiz-dados de C:\Collected</span><span class="sxs-lookup"><span data-stu-id="23b09-136">root folder - C:\Collected Data</span></span> 
    
  - <span data-ttu-id="23b09-137">URL do contêiner https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp-; Sr =&amp;c si = NonOfficeData15%&amp;7C0 SIG = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA% 3D</span><span class="sxs-lookup"><span data-stu-id="23b09-137">container url - https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D</span></span>
    
    <span data-ttu-id="23b09-138">a sintaxe da linha de comando do AzCopy seria:</span><span class="sxs-lookup"><span data-stu-id="23b09-138">the AzCopy command line syntax would be:</span></span>
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    <span data-ttu-id="23b09-139">Para obter mais informações sobre a sintaxe do Azcopy, consulte [transferir dados com o Azcopy no Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span><span class="sxs-lookup"><span data-stu-id="23b09-139">For more information on Azcopy syntax see, [Transfer data with the AzCopy on Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) .</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="23b09-140">Deve haver uma pasta raiz por usuário e o nome da pasta deve estar no formato *alias@domainname* .</span><span class="sxs-lookup"><span data-stu-id="23b09-140">There must be one root folder per user and the folder name must be in the  *alias@domainname*  format.</span></span> 
  
8. <span data-ttu-id="23b09-141">Depois que as pastas terminarem o carregamento, volte para a descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="23b09-141">Once the folders have finished uploading, switch back to Advanced eDiscovery.</span></span> <span data-ttu-id="23b09-142">O conteúdo das pastas carregadas agora está pronto para ser processado na descoberta eletrônica avançada.</span><span class="sxs-lookup"><span data-stu-id="23b09-142">The content in the folders you uploaded is now ready to be processed in Advanced eDiscovery.</span></span> <span data-ttu-id="23b09-143">Selecione o contêiner e clique no botão processo.</span><span class="sxs-lookup"><span data-stu-id="23b09-143">Select the container and click the Process button.</span></span> <span data-ttu-id="23b09-144">Para obter mais detalhes sobre o processamento de descoberta eletrônica avançado, confira [executar o módulo de processo e carregar dados na descoberta eletrônica avançada do Office 365](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span><span class="sxs-lookup"><span data-stu-id="23b09-144">For more details on Advanced eDiscovery Processing see, [Run the Process module and load data in Office 365 Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="23b09-145">Depois que o contêiner for processado com êxito na descoberta eletrônica avançada, você não poderá mais adicionar novo conteúdo ao armazenamento SAS no Azure.</span><span class="sxs-lookup"><span data-stu-id="23b09-145">Once the container is successfully processed in Advanced eDiscovery, you will no longer be able to add new content to the SAS storage in Azure.</span></span> <span data-ttu-id="23b09-146">Se você coletar conteúdo adicional e quiser adicioná-lo ao caso da análise de descoberta eletrônica avançada, você deve criar um novo contêiner de **dados que não seja do Office 365** e repetir este procedimento.</span><span class="sxs-lookup"><span data-stu-id="23b09-146">If you collect additional content and you want to add it to the case for Advanced eDiscovery analysis, you must create a new **Non-Office 365 data** container and repeat this procedure.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="23b09-147">Se o contêiner *não for processado com êxito devido a problemas de nomenclatura de pasta* e você corrigir os problemas, ainda será necessário criar um novo contêiner e reconectar e carregar novamente usando os procedimentos deste artigo.</span><span class="sxs-lookup"><span data-stu-id="23b09-147">If the container  *does not process successfully due to folder naming issues*  and you then fix the issues, you will still have to create a new container and the reconnect and upload again using the procedures in this article.</span></span>