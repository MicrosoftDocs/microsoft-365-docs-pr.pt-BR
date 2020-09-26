---
title: Carregar dados que não sejam da Microsoft 365 em evidências
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
description: Saiba como usar o recurso de importação de conteúdo não-Office 365 para carregar documentos que não sejam do Office 365 em evidências em uma investigação de dados.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: b6d8c2f65a1fa3a43fa2ac4bf3821cc6c1fac514
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285367"
---
# <a name="load-non-microsoft-365-data-into-evidence"></a><span data-ttu-id="57f62-103">Carregar dados que não sejam da Microsoft 365 em evidências</span><span class="sxs-lookup"><span data-stu-id="57f62-103">Load non-Microsoft 365 data into evidence</span></span>

<span data-ttu-id="57f62-104">Nem todos os documentos que você pode precisar analisar em uma investigação de dados estarão localizados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="57f62-104">Not all documents that you may need to analyze in a data investigation will be located in Microsoft 365.</span></span> <span data-ttu-id="57f62-105">Com o recurso de importação de conteúdo não-Microsoft 365, você pode carregar documentos que não estão no Microsoft 365 em evidência para que eles possam ser analisados em uma investigação de dados.</span><span class="sxs-lookup"><span data-stu-id="57f62-105">With the Non-Microsoft 365 content import feature you can upload documents that don't live in Microsoft 365 into evidence so they can be analyzed in a data investigation.</span></span>

## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="57f62-106">Requisitos para carregar conteúdo não-Office 365</span><span class="sxs-lookup"><span data-stu-id="57f62-106">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="57f62-107">O uso do recurso carregar não Microsoft 365, conforme descrito neste procedimento, requer que você tenha:</span><span class="sxs-lookup"><span data-stu-id="57f62-107">Using the upload Non-Microsoft 365 feature as described in this procedure requires that you have:</span></span>

- <span data-ttu-id="57f62-108">Uma assinatura do Microsoft 365 ou do Office 365 e5.</span><span class="sxs-lookup"><span data-stu-id="57f62-108">A Microsoft 365 or Office 365 E5 subscription.</span></span>

- <span data-ttu-id="57f62-109">Todas as pessoas de interesse cujo conteúdo que não seja da Microsoft 365 serão carregadas deverão ter a licença complementar E5 ou E5 apropriada.</span><span class="sxs-lookup"><span data-stu-id="57f62-109">All people of interest whose non-Microsoft 365 content will be uploaded must have the appropriate E5 or E5 add-on license.</span></span>

- <span data-ttu-id="57f62-110">Uma ocorrência de descoberta eletrônica existente.</span><span class="sxs-lookup"><span data-stu-id="57f62-110">An existing eDiscovery case.</span></span>

- <span data-ttu-id="57f62-111">Todos os arquivos para carregamento são coletados em pastas onde há uma pasta por responsáveis e o nome das pastas está nesse formato *alias@domainname*.</span><span class="sxs-lookup"><span data-stu-id="57f62-111">All the files for uploading gathered into folders where there is one folder per custodian and the folders' name is in this format *alias@domainname*.</span></span> <span data-ttu-id="57f62-112">O *alias@domainname* deve ser o alias e o domínio do usuário.</span><span class="sxs-lookup"><span data-stu-id="57f62-112">The *alias@domainname* must be user's alias and domain.</span></span> <span data-ttu-id="57f62-113">Você pode coletar todas as pastas de *alias@domainname* em uma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="57f62-113">You can collect all the *alias@domainname* folders into a root folder.</span></span> <span data-ttu-id="57f62-114">A pasta raiz pode conter apenas as pastas *alias@domainname* , não deve haver arquivos soltos na pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="57f62-114">The root folder can only contain the *alias@domainname* folders, there must be no loose files in the root folder.</span></span>

- <span data-ttu-id="57f62-115">Uma conta que seja um Gerenciador de descoberta eletrônica ou ferramentas de armazenamento do Microsoft Azure administrador instaladas em um computador que tenha acesso à estrutura de pasta de conteúdo não-Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="57f62-115">An account that is either an eDiscovery Manager or eDiscovery Administrator Microsoft Azure Storage Tools installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span>

- <span data-ttu-id="57f62-116">Instale o AzCopy, que você pode fazer da introdução [ao AzCopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="57f62-116">Install AzCopy, which you can do from [Get started with AzCopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span>

## <a name="upload-non-microsoft-365-content-in-to-a-data-investigation"></a><span data-ttu-id="57f62-117">Carregar conteúdo não-Microsoft 365 em uma investigação de dados</span><span class="sxs-lookup"><span data-stu-id="57f62-117">Upload non-Microsoft 365 content in to a data investigation</span></span>

1. <span data-ttu-id="57f62-118">Abra as **investigações de dados** e vá para a investigação de que os dados que não são da Microsoft 365 serão carregados.</span><span class="sxs-lookup"><span data-stu-id="57f62-118">Open **Data Investigations** and go to the investigation that the non-Microsoft 365 data will be uploaded to.</span></span>  <span data-ttu-id="57f62-119">Clique na guia **evidência** e selecione o conjunto de evidências para o qual você deseja carregar os dados.</span><span class="sxs-lookup"><span data-stu-id="57f62-119">Click the **Evidence** tab, then select the evidence set you wish to load the data to.</span></span>  <span data-ttu-id="57f62-120">Se você ainda não criou um conjunto de evidências, é possível fazer isso agora.</span><span class="sxs-lookup"><span data-stu-id="57f62-120">If you have not already created an evidence set, you can do so now.</span></span>  <span data-ttu-id="57f62-121">Por fim, clique em **gerenciar evidências** e, em seguida, **Exibir uploads** na seção de dados</span><span class="sxs-lookup"><span data-stu-id="57f62-121">Finally, click **Manage evidence** then **View uploads** in the data section</span></span>

2. <span data-ttu-id="57f62-122">Clique no botão **carregar arquivos** para iniciar o assistente de importação de dados não-Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="57f62-122">Click the **Upload files** button to start the Non-Microsoft 365 data import wizard.</span></span>

![Carregar arquivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

3. <span data-ttu-id="57f62-124">A primeira etapa no assistente simplesmente prepara um blob do Azure seguro para os arquivos a serem carregados.</span><span class="sxs-lookup"><span data-stu-id="57f62-124">The first step in the wizard simply prepares a secure Azure blob for the files to be uploaded.</span></span>  <span data-ttu-id="57f62-125">Após a conclusão da preparação, clique no botão **próximo: carregar arquivos** .</span><span class="sxs-lookup"><span data-stu-id="57f62-125">After the preparation is complete, click the **Next: Upload files** button.</span></span>

![Preparar a importação de dados não-Microsoft 365](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
4. <span data-ttu-id="57f62-127">Na etapa **carregar arquivos** , especifique o **caminho para o local dos arquivos**, onde os dados que não são da Microsoft 365 que você planeja importar estão localizados.</span><span class="sxs-lookup"><span data-stu-id="57f62-127">In the **Upload files** step, specify the **Path to location of files**, this is where the Non-Microsoft 365 data you plan on importing is located.</span></span>  <span data-ttu-id="57f62-128">Definir o local correto garante que o comando AzCopy seja atualizado corretamente.</span><span class="sxs-lookup"><span data-stu-id="57f62-128">Setting the correct location ensures the AzCopy command is properly updated.</span></span>

> [!NOTE]
> <span data-ttu-id="57f62-129">Se você ainda não tiver instalado o AzCopy, poderá fazer isso daqui: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span><span class="sxs-lookup"><span data-stu-id="57f62-129">If you have not already installed AzCopy, you can do this from here: https://docs.microsoft.com/azure/storage/common/storage-use-azcopy</span></span>

5. <span data-ttu-id="57f62-130">Copie o comando predefinido clicando no link **copiar para a área de transferência** .</span><span class="sxs-lookup"><span data-stu-id="57f62-130">Copy the predefined command by clicking the **Copy to clipboard** link.</span></span> <span data-ttu-id="57f62-131">Inicie um prompt de comando do Windows, Cole o comando e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="57f62-131">Start a windows command prompt, paste the command and press enter.</span></span>  <span data-ttu-id="57f62-132">Os arquivos serão carregados para o armazenamento de blob do Azure seguro para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="57f62-132">The files will be uploaded to the secure Azure blob storage for the next step.</span></span>

![Carregar arquivos para importação de dados não-Microsoft 365](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

![Usar o AzCopy para importar dados que não são da Microsoft 365](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

6. <span data-ttu-id="57f62-135">Por fim, volte para a segurança & conformidade e clique no botão **próximo: processar arquivos** .</span><span class="sxs-lookup"><span data-stu-id="57f62-135">Finally, return back to the Security & Compliance and click the **Next: Process files** button.</span></span>  <span data-ttu-id="57f62-136">Isso inicia o processamento, extração de texto e indexação de arquivos carregados.</span><span class="sxs-lookup"><span data-stu-id="57f62-136">This initiates processing, text extraction, and indexing of the uploaded files.</span></span>  <span data-ttu-id="57f62-137">Você pode acompanhar o progresso do processamento aqui ou na guia **trabalhos** .  Após a conclusão, os novos arquivos estarão disponíveis no conjunto de evidências.</span><span class="sxs-lookup"><span data-stu-id="57f62-137">You can track the progress of processing here or in the **Jobs** tab.  Once completed, the new files are available in the evidence set.</span></span>  <span data-ttu-id="57f62-138">Após a conclusão do processamento, você pode ignorar o assistente.</span><span class="sxs-lookup"><span data-stu-id="57f62-138">After processing is complete, you can dismiss the wizard.</span></span>

![Arquivos de processo de importação não-Microsoft 365](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

