---
title: Carregar dados que não são do Microsoft 365 em um conjunto de revisão
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Saiba como importar dados não Microsoft 365 para um conjunto de revisão para análise em um Advanced eDiscovery caso.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d9f705080ad5a769032581a1517b2daee8e822b2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903497"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a><span data-ttu-id="95f7d-103">Carregar dados que não são do Microsoft 365 em um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="95f7d-103">Load non-Microsoft 365 data into a review set</span></span>

<span data-ttu-id="95f7d-104">Nem todos os documentos que você precisa analisar no Advanced eDiscovery estão localizados em Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="95f7d-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Microsoft 365.</span></span> <span data-ttu-id="95f7d-105">Com o recurso de importação de dados que não são do Microsoft 365 na Descoberta Eletrônica Avançada, você pode carregar documentos que não estão localizados no Microsoft 365 para um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="95f7d-105">With the non-Microsoft 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Microsoft 365 to a review set.</span></span> <span data-ttu-id="95f7d-106">Este artigo mostra como trazer seus documentos que não Microsoft 365 para Advanced eDiscovery para análise.</span><span class="sxs-lookup"><span data-stu-id="95f7d-106">This article shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>

## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="95f7d-107">Requisitos para carregar conteúdo não Office 365 conteúdo</span><span class="sxs-lookup"><span data-stu-id="95f7d-107">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="95f7d-108">O uso do recurso de Microsoft 365 de carregamento descrito neste artigo exige que você tenha o seguinte:</span><span class="sxs-lookup"><span data-stu-id="95f7d-108">Using the upload non-Microsoft 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="95f7d-109">Todos os custodiantes aos Microsoft 365 devem ter a licença apropriada.</span><span class="sxs-lookup"><span data-stu-id="95f7d-109">All custodians that you want to associate non-Microsoft 365 content to must be assigned the appropriate license.</span></span> <span data-ttu-id="95f7d-110">Para obter mais informações, [consulte Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span><span class="sxs-lookup"><span data-stu-id="95f7d-110">For more information, see [Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span></span>

- <span data-ttu-id="95f7d-111">Um caso Advanced eDiscovery existente.</span><span class="sxs-lookup"><span data-stu-id="95f7d-111">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="95f7d-112">Os custodiantes devem ser adicionados ao caso antes que você possa carregar e associar os dados que não Microsoft 365 a eles.</span><span class="sxs-lookup"><span data-stu-id="95f7d-112">Custodians must be added to the case before you can upload and associate the non-Microsoft 365 data to them.</span></span>

- <span data-ttu-id="95f7d-113">Dados que não são do Microsoft 365 devem ser de um tipo de arquivo com suporte à Descoberta Eletrônica Avançada.</span><span class="sxs-lookup"><span data-stu-id="95f7d-113">Non-Microsoft 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="95f7d-114">Para saber mais, confira [Tipos de arquivo com suporte na Descoberta Eletrônica Avançada](supported-filetypes-ediscovery20.md).</span><span class="sxs-lookup"><span data-stu-id="95f7d-114">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="95f7d-115">Todos os arquivos carregados para um conjunto de revisão devem estar localizados em pastas onde cada pasta está associada a um guardião específico.</span><span class="sxs-lookup"><span data-stu-id="95f7d-115">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="95f7d-116">Os nomes dessas pastas devem usar o seguinte formato de nomeação: *alias@domainname*.</span><span class="sxs-lookup"><span data-stu-id="95f7d-116">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="95f7d-117">O alias@domainname deve ser o alias e domínio do Microsoft 365 do usuário.</span><span class="sxs-lookup"><span data-stu-id="95f7d-117">The alias@domainname must be the user's Microsoft 365 alias and domain.</span></span> <span data-ttu-id="95f7d-118">Você pode coletar todas as alias@domainname em uma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="95f7d-118">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="95f7d-119">A pasta raiz só pode conter as alias@domainname pastas.</span><span class="sxs-lookup"><span data-stu-id="95f7d-119">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="95f7d-120">Arquivos soltos na pasta raiz não são suportados.</span><span class="sxs-lookup"><span data-stu-id="95f7d-120">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="95f7d-121">A estrutura de pastas para os dados Microsoft 365 que você deseja carregar seria semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="95f7d-121">The folder structure for the non-Microsoft 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="95f7d-122">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="95f7d-122">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="95f7d-123">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="95f7d-123">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="95f7d-124">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="95f7d-124">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="95f7d-125">Onde abraham.mcmahon@contoso.com, jewell.gordon@contoso.com e staci.gonzalez@contoso.com são os endereços SMTP dos custodiantes no caso.</span><span class="sxs-lookup"><span data-stu-id="95f7d-125">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Estrutura de pasta de carregamento de dados não Microsoft 365 de dados](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="95f7d-127">Uma conta atribuída ao grupo de funções do Gerenciador de Descobertas e Descobertas (e adicionada como Administrador de Descoberta Digital).</span><span class="sxs-lookup"><span data-stu-id="95f7d-127">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="95f7d-128">A ferramenta do AzCopy v8.1 instalada em um computador que tem acesso à estrutura de pasta de Microsoft 365 de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="95f7d-128">The AzCopy v8.1 tool installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span> <span data-ttu-id="95f7d-129">Para instalar o AzCopy, consulte [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="95f7d-129">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="95f7d-130">Instale o AzCopy no local padrão, que é **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span><span class="sxs-lookup"><span data-stu-id="95f7d-130">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="95f7d-131">Você deve usar o AzCopy v8.1.</span><span class="sxs-lookup"><span data-stu-id="95f7d-131">You must use AzCopy v8.1.</span></span> <span data-ttu-id="95f7d-132">Outras versões do AzCopy podem não funcionar ao carregar dados não Microsoft 365 no Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="95f7d-132">Other versions of AzCopy may not work when loading non-Microsoft 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a><span data-ttu-id="95f7d-133">Upload conteúdo não Microsoft 365 no Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="95f7d-133">Upload non-Microsoft 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="95f7d-134">Como Gerente de Descoberta Microsoft 365 Ou Administrador de Descobertas Advanced eDiscovery, abra o Advanced eDiscovery e vá para o caso em que os dados que não Microsoft 365 serão carregados.</span><span class="sxs-lookup"><span data-stu-id="95f7d-134">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, and go to the case that the non-Microsoft 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="95f7d-135">Clique **em Revisar conjuntos** e selecione o conjunto de revisão para carregar os dados que não Microsoft 365 dados.</span><span class="sxs-lookup"><span data-stu-id="95f7d-135">Click **Review sets**, and then select the review set to upload the non-Microsoft 365 data to.</span></span>  <span data-ttu-id="95f7d-136">Se você não tiver um conjunto de revisão, poderá criar um.</span><span class="sxs-lookup"><span data-stu-id="95f7d-136">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="95f7d-137">No conjunto de revisão, clique em **Gerenciar conjunto de revisão**, em seguida, clique em **Exibir carregamentos** no bloco **Dados que não são do Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="95f7d-137">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Microsoft 365 data** tile.</span></span>

4. <span data-ttu-id="95f7d-138">Clique em **Carregar arquivos** para iniciar o assistente de importação de dados.</span><span class="sxs-lookup"><span data-stu-id="95f7d-138">Click **Upload files** to start the data import wizard.</span></span>

   ![Carregar arquivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="95f7d-140">A primeira etapa no assistente prepara um local de Armazenamento do Microsoft Azure seguro fornecido pela Microsoft para carregar os arquivos.</span><span class="sxs-lookup"><span data-stu-id="95f7d-140">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="95f7d-141">Quando a preparação for concluída, o botão **Próximo: Carregar arquivos** será ativado.</span><span class="sxs-lookup"><span data-stu-id="95f7d-141">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Importação não Microsoft 365: Preparar](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="95f7d-143">Clique em **Próximo: Carregar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="95f7d-143">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="95f7d-144">Na página **Upload arquivos,** faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="95f7d-144">On the **Upload files** page, do the following:</span></span>

   ![Não Microsoft 365 Importar: Upload arquivos](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="95f7d-146">a.</span><span class="sxs-lookup"><span data-stu-id="95f7d-146">a.</span></span> <span data-ttu-id="95f7d-147">Na caixa **Caminho para a localização** dos arquivos, verifique ou digite o local da pasta raiz onde você armazenou os dados que não Microsoft 365 que deseja carregar.</span><span class="sxs-lookup"><span data-stu-id="95f7d-147">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Microsoft 365 data you want to upload.</span></span> <span data-ttu-id="95f7d-148">Por exemplo, para o local dos arquivos de exemplo mostrados na seção Antes de **começar,** digite **%USERPROFILE\Downloads\nonO365**.</span><span class="sxs-lookup"><span data-stu-id="95f7d-148">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="95f7d-149">Fornecer o local correto garante que o comando do AzCopy exibido na caixa sob o caminho seja atualizado corretamente.</span><span class="sxs-lookup"><span data-stu-id="95f7d-149">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="95f7d-150">b.</span><span class="sxs-lookup"><span data-stu-id="95f7d-150">b.</span></span> <span data-ttu-id="95f7d-151">Clique **em Copiar para área de** transferência para copiar o comando exibido na caixa.</span><span class="sxs-lookup"><span data-stu-id="95f7d-151">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="95f7d-152">Inicie um Windows de comando, cole o comando que copiou na etapa anterior e pressione **Enter** para iniciar o comando do AzCopy.</span><span class="sxs-lookup"><span data-stu-id="95f7d-152">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="95f7d-153">Depois de iniciar o comando, os arquivos que não Microsoft 365 serão carregados no local de Armazenamento do Azure que foi preparado na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="95f7d-153">After you start the command, the non-Microsoft 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Importação não Microsoft 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="95f7d-155">Como mencionado anteriormente, você deve usar o AzCopy v8.1 para usar com êxito o comando fornecido na página arquivos **Upload** de segurança.</span><span class="sxs-lookup"><span data-stu-id="95f7d-155">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="95f7d-156">Se o comando AzCopy fornecido falhar, consulte [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span><span class="sxs-lookup"><span data-stu-id="95f7d-156">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="95f7d-157">Volte para o Centro de Conformidade & segurança e clique em **Next: Process files** in the wizard.</span><span class="sxs-lookup"><span data-stu-id="95f7d-157">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="95f7d-158">Isso inicia o processamento, a extração de texto e indexação dos arquivos que não são do Microsoft 365 que foram carregados no local de Armazenamento do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="95f7d-158">This initiates processing, text extraction, and indexing of the non-Microsoft 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="95f7d-159">Acompanhe o progresso do processamento  dos arquivos na  página Arquivos de processo ou na guia Trabalhos exibindo um trabalho chamado Adicionando dados não Microsoft 365 a um conjunto **de revisão.**</span><span class="sxs-lookup"><span data-stu-id="95f7d-159">Track the progress of processing the files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Microsoft 365 data to a review set**.</span></span>  <span data-ttu-id="95f7d-160">Depois que o trabalho for concluído, os novos arquivos estarão disponíveis no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="95f7d-160">After the job is finished, the new files will be available in the review set.</span></span>

   ![Não importação Microsoft 365: processar arquivos](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="95f7d-162">Depois que o processamento for concluído, feche o assistente.</span><span class="sxs-lookup"><span data-stu-id="95f7d-162">After the processing is finished, you can close the wizard.</span></span>