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
description: Saiba como importar dados que não são do Microsoft 365 para um conjunto de revisão para análise em um caso de Descoberta Avançada.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ad70207bdc015107a5aba074e2df06a42c0618b3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285857"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a><span data-ttu-id="2455a-103">Carregar dados que não são do Microsoft 365 em um conjunto de revisão</span><span class="sxs-lookup"><span data-stu-id="2455a-103">Load non-Microsoft 365 data into a review set</span></span>

<span data-ttu-id="2455a-104">Nem todos os documentos que você precisa analisar na Descoberta Avançada estão localizados no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2455a-104">Not all documents that you need to analyze in Advanced eDiscovery are located in Microsoft 365.</span></span> <span data-ttu-id="2455a-105">Com o recurso de importação de dados que não são do Microsoft 365 na Descoberta Avançada, você pode carregar documentos que não estão localizados no Microsoft 365 para um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="2455a-105">With the non-Microsoft 365 data import feature in Advanced eDiscovery, you can upload documents that aren't located in Microsoft 365 to a review set.</span></span> <span data-ttu-id="2455a-106">Este artigo mostra como trazer seus documentos que não são do Microsoft 365 para a Descoberta Avançada para análise.</span><span class="sxs-lookup"><span data-stu-id="2455a-106">This article shows you how to bring your non-Microsoft 365 documents into Advanced eDiscovery for analysis.</span></span>

## <a name="requirements-to-upload-non-office-365-content"></a><span data-ttu-id="2455a-107">Requisitos para carregar conteúdo que não seja do Office 365</span><span class="sxs-lookup"><span data-stu-id="2455a-107">Requirements to upload non-Office 365 content</span></span>

<span data-ttu-id="2455a-108">O uso do recurso de carregamento que não é do Microsoft 365 descrito neste artigo requer que você tenha o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2455a-108">Using the upload non-Microsoft 365 feature described in this article requires that you have the following:</span></span>

- <span data-ttu-id="2455a-109">Todos os custodiantes que você deseja associar ao conteúdo que não seja do Microsoft 365 devem ter a licença apropriada.</span><span class="sxs-lookup"><span data-stu-id="2455a-109">All custodians that you want to associate non-Microsoft 365 content to must be assigned the appropriate license.</span></span> <span data-ttu-id="2455a-110">Para obter mais informações, [consulte Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span><span class="sxs-lookup"><span data-stu-id="2455a-110">For more information, see [Get started with Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).</span></span>

- <span data-ttu-id="2455a-111">Uma ocorrência de Descoberta Avançada existente.</span><span class="sxs-lookup"><span data-stu-id="2455a-111">An existing Advanced eDiscovery case.</span></span>

- <span data-ttu-id="2455a-112">Custodiantes devem ser adicionados à ocorrência para que você possa carregar e associar os dados que não são do Microsoft 365 a eles.</span><span class="sxs-lookup"><span data-stu-id="2455a-112">Custodians must be added to the case before you can upload and associate the non-Microsoft 365 data to them.</span></span>

- <span data-ttu-id="2455a-113">Os dados que não são do Microsoft 365 devem ser um tipo de arquivo suportado pela Descoberta Avançada.</span><span class="sxs-lookup"><span data-stu-id="2455a-113">Non-Microsoft 365 data must be a file type that's supported by Advanced eDiscovery.</span></span> <span data-ttu-id="2455a-114">Para obter mais informações, [consulte Tipos de arquivo com suporte na Descoberta Descoberta Avançada.](supported-filetypes-ediscovery20.md)</span><span class="sxs-lookup"><span data-stu-id="2455a-114">For more information, see [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).</span></span>

- <span data-ttu-id="2455a-115">Todos os arquivos carregados em um conjunto de revisão devem estar localizados em pastas, onde cada pasta está associada a um custodiante específico.</span><span class="sxs-lookup"><span data-stu-id="2455a-115">All files that are uploaded to a review set must be located in folders, where each folder is associated with a specific custodian.</span></span> <span data-ttu-id="2455a-116">Os nomes dessas pastas devem usar o seguinte formato de nomeação: *alias@domainname*.</span><span class="sxs-lookup"><span data-stu-id="2455a-116">The names for these folders must use the following naming format: *alias@domainname*.</span></span> <span data-ttu-id="2455a-117">O alias@domainname deve ser o alias e o domínio do Microsoft 365 do usuário.</span><span class="sxs-lookup"><span data-stu-id="2455a-117">The alias@domainname must be the user's Microsoft 365 alias and domain.</span></span> <span data-ttu-id="2455a-118">Você pode coletar todas as alias@domainname em uma pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="2455a-118">You can collect all the alias@domainname folders in a root folder.</span></span> <span data-ttu-id="2455a-119">A pasta raiz só pode conter as alias@domainname pastas.</span><span class="sxs-lookup"><span data-stu-id="2455a-119">The root folder can only contain the alias@domainname folders.</span></span> <span data-ttu-id="2455a-120">Arquivos soltos na pasta raiz não são suportados.</span><span class="sxs-lookup"><span data-stu-id="2455a-120">Loose files in the root folder aren't supported.</span></span>

   <span data-ttu-id="2455a-121">A estrutura de pastas para os dados que não são do Microsoft 365 que você deseja carregar seria semelhante ao exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="2455a-121">The folder structure for the non-Microsoft 365 data that you want to upload would be similar to the following example:</span></span>

   - <span data-ttu-id="2455a-122">c:\nonO365\abraham.mcmahon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2455a-122">c:\nonO365\abraham.mcmahon@contoso.com</span></span>
   - <span data-ttu-id="2455a-123">c:\nonO365\jewell.gordon@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2455a-123">c:\nonO365\jewell.gordon@contoso.com</span></span>
   - <span data-ttu-id="2455a-124">c:\nonO365\staci.gonzalez@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2455a-124">c:\nonO365\staci.gonzalez@contoso.com</span></span>

   <span data-ttu-id="2455a-125">Onde abraham.mcmahon@contoso.com, jewell.gordon@contoso.com e staci.gonzalez@contoso.com são os endereços SMTP dos custodiantes no caso.</span><span class="sxs-lookup"><span data-stu-id="2455a-125">Where abraham.mcmahon@contoso.com, jewell.gordon@contoso.com, and staci.gonzalez@contoso.com are the SMTP addresses of custodians in the case.</span></span>

   ![Estrutura de pastas de carregamento de dados que não são do Microsoft 365](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- <span data-ttu-id="2455a-127">Uma conta que é atribuída ao grupo de função Gerente de Descobertas e Descobertas (e adicionada como Administrador de Descobertas e Descobertas).</span><span class="sxs-lookup"><span data-stu-id="2455a-127">An account that is assigned to the eDiscovery Manager role group (and added as eDiscovery Administrator).</span></span>

- <span data-ttu-id="2455a-128">A ferramenta AzCopy v8.1 instalada em um computador que tem acesso à estrutura de pastas de conteúdo que não são do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2455a-128">The AzCopy v8.1 tool installed on a computer that has access to the non-Microsoft 365 content folder structure.</span></span> <span data-ttu-id="2455a-129">Para instalar o AzCopy, consulte [Transferir dados com o AzCopy v8.1 no Windows.](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)</span><span class="sxs-lookup"><span data-stu-id="2455a-129">To install AzCopy, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="2455a-130">Certifique-se de instalar o AzCopy no local padrão, que é **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span><span class="sxs-lookup"><span data-stu-id="2455a-130">Be sure to install AzCopy in the default location, which is **%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy**.</span></span> <span data-ttu-id="2455a-131">Você deve usar o AzCopy v8.1.</span><span class="sxs-lookup"><span data-stu-id="2455a-131">You must use AzCopy v8.1.</span></span> <span data-ttu-id="2455a-132">Outras versões do AzCopy podem não funcionar ao carregar dados que não são do Microsoft 365 na Descoberta Eletrônica Avançada.</span><span class="sxs-lookup"><span data-stu-id="2455a-132">Other versions of AzCopy may not work when loading non-Microsoft 365 data in Advanced eDiscovery.</span></span>


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a><span data-ttu-id="2455a-133">Carregar conteúdo que não seja do Microsoft 365 para a Descoberta Avançada</span><span class="sxs-lookup"><span data-stu-id="2455a-133">Upload non-Microsoft 365 content into Advanced eDiscovery</span></span>

1. <span data-ttu-id="2455a-134">Como Gerente de Descobertas es ou Administrador de Descobertas e Descobertas, abra a Descoberta Avançada e vá para o caso em que os dados que não são do Microsoft 365 serão carregados.</span><span class="sxs-lookup"><span data-stu-id="2455a-134">As an eDiscovery Manager or eDiscovery Administrator, open Advanced eDiscovery, and go to the case that the non-Microsoft 365 data will be uploaded to.</span></span>  

2. <span data-ttu-id="2455a-135">Clique **em Conjuntos de** revisão e selecione o conjunto de revisão para carregar os dados que não são do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2455a-135">Click **Review sets**, and then select the review set to upload the non-Microsoft 365 data to.</span></span>  <span data-ttu-id="2455a-136">Se você não tiver um conjunto de revisão, poderá criar um.</span><span class="sxs-lookup"><span data-stu-id="2455a-136">If you don't have a review set, you can create one.</span></span> 
 
3. <span data-ttu-id="2455a-137">No conjunto de revisão, clique em **Gerenciar conjunto** de revisão e, em seguida, clique em Exibir **carregamentos** no lado dos dados que não são do **Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="2455a-137">In the review set, click **Manage review set**, and then click **View uploads** on the **Non-Microsoft 365 data** tile.</span></span>

4. <span data-ttu-id="2455a-138">Clique **em Carregar arquivos** para iniciar o assistente de importação de dados.</span><span class="sxs-lookup"><span data-stu-id="2455a-138">Click **Upload files** to start the data import wizard.</span></span>

   ![Carregar arquivos](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   <span data-ttu-id="2455a-140">A primeira etapa do assistente prepara um local seguro de Armazenamento do Azure fornecido pela Microsoft para carregar os arquivos.</span><span class="sxs-lookup"><span data-stu-id="2455a-140">The first step in the wizard prepares a secure Microsoft-provided Azure Storage location to upload the files to.</span></span>  <span data-ttu-id="2455a-141">Quando a preparação for concluída, o **botão Próximo: Carregar arquivos** se tornará ativo.</span><span class="sxs-lookup"><span data-stu-id="2455a-141">When the preparation is completed, the **Next: Upload files** button becomes active.</span></span>

   ![Importação que não seja do Microsoft 365: Preparar](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. <span data-ttu-id="2455a-143">Clique **em Próximo: Carregar arquivos.**</span><span class="sxs-lookup"><span data-stu-id="2455a-143">Click **Next: Upload files**.</span></span>

6. <span data-ttu-id="2455a-144">Na página **Carregar arquivos,** faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2455a-144">On the **Upload files** page, do the following:</span></span>

   ![Importação que não é do Microsoft 365: Carregar arquivos](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   <span data-ttu-id="2455a-146">a.</span><span class="sxs-lookup"><span data-stu-id="2455a-146">a.</span></span> <span data-ttu-id="2455a-147">Na caixa **Caminho para o** local dos arquivos, verifique ou digite o local da pasta raiz onde você armazenou os dados que não são do Microsoft 365 que deseja carregar.</span><span class="sxs-lookup"><span data-stu-id="2455a-147">In the **Path to location of files** box, verify or type the location of the root folder where you've stored the non-Microsoft 365 data you want to upload.</span></span> <span data-ttu-id="2455a-148">Por exemplo, para o local dos arquivos de exemplo mostrados na seção Antes de **começar,** digite **%USERPROFILE\Downloads\nonO365**.</span><span class="sxs-lookup"><span data-stu-id="2455a-148">For example, for the location of the example files shown in the **Before you begin section**, you would type **%USERPROFILE\Downloads\nonO365**.</span></span> <span data-ttu-id="2455a-149">Fornecer o local correto garante que o comando AzCopy exibido na caixa abaixo do caminho seja atualizado corretamente.</span><span class="sxs-lookup"><span data-stu-id="2455a-149">Providing the correct location ensures the AzCopy command displayed in box under the path is properly updated.</span></span>

   <span data-ttu-id="2455a-150">b.</span><span class="sxs-lookup"><span data-stu-id="2455a-150">b.</span></span> <span data-ttu-id="2455a-151">Clique **em Copiar para área** de transferência para copiar o comando exibido na caixa.</span><span class="sxs-lookup"><span data-stu-id="2455a-151">Click **Copy to clipboard** to copy the command that is displayed in the box.</span></span>

7. <span data-ttu-id="2455a-152">Inicie um prompt de comando do Windows, copie o comando que você copiou na etapa anterior e pressione **Enter** para iniciar o comando AzCopy.</span><span class="sxs-lookup"><span data-stu-id="2455a-152">Start a Windows command prompt, paste the command that you copied in the previous step, and then press **Enter** to start the AzCopy command.</span></span>  <span data-ttu-id="2455a-153">Depois de iniciar o comando, os arquivos que não são do Microsoft 365 serão carregados no local de armazenamento do Azure preparado na etapa 4.</span><span class="sxs-lookup"><span data-stu-id="2455a-153">After you start the command, the non-Microsoft 365 files will be uploaded to the Azure Storage location that was prepared in step 4.</span></span>

   ![Importação que não seja do Microsoft 365: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > <span data-ttu-id="2455a-155">Conforme mencionado anteriormente, você deve usar o AzCopy v8.1 para usar com êxito o comando fornecido na página **Carregar arquivos.**</span><span class="sxs-lookup"><span data-stu-id="2455a-155">As previously stated, you must use AzCopy v8.1 to successfully use the command that's provided on the **Upload files** page.</span></span> <span data-ttu-id="2455a-156">Se o comando AzCopy fornecido falhar, consulte [Solucionar problemas do AzCopy na Descoberta Eletrônica Avançada.](troubleshooting-azcopy.md)</span><span class="sxs-lookup"><span data-stu-id="2455a-156">If the supplied AzCopy command fails, please see [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).</span></span>

8. <span data-ttu-id="2455a-157">Volte para o Centro de Conformidade & segurança e clique em **Próximo: Processar arquivos** no assistente.</span><span class="sxs-lookup"><span data-stu-id="2455a-157">Go back to the Security & Compliance Center, and click **Next: Process files** in the wizard.</span></span>  <span data-ttu-id="2455a-158">Isso inicia o processamento, a extração de texto e a indexação dos arquivos que não são do Microsoft 365 que foram carregados para o local de armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="2455a-158">This initiates processing, text extraction, and indexing of the non-Microsoft 365 files that were uploaded to the Azure Storage location.</span></span>  

9. <span data-ttu-id="2455a-159">Acompanhe o progresso do processamento  dos arquivos na  página Arquivos de processo ou na guia Trabalhos exibindo um trabalho chamado Adicionando dados que não são do **Microsoft 365 a** um conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="2455a-159">Track the progress of processing the files on the **Process files** page or on the **Jobs** tab by viewing a job named **Adding non-Microsoft 365 data to a review set**.</span></span>  <span data-ttu-id="2455a-160">Depois que o trabalho for concluído, os novos arquivos estarão disponíveis no conjunto de revisão.</span><span class="sxs-lookup"><span data-stu-id="2455a-160">After the job is finished, the new files will be available in the review set.</span></span>

   ![Importação que não seja do Microsoft 365: Processar arquivos](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. <span data-ttu-id="2455a-162">Depois que o processamento for concluído, você poderá fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="2455a-162">After the processing is finished, you can close the wizard.</span></span>
