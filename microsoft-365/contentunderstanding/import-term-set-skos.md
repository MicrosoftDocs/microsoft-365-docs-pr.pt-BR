---
title: Importar um conjunto de termos usando um formato baseado em SKOS
description: Saiba como importar um conjunto de termos usando um formato baseado em SKOS
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 318497b8b1815b281eff7d781820616c9be9d5ed
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321236"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="20aaa-103">Importar um conjunto de termos usando um formato baseado em SKOS</span><span class="sxs-lookup"><span data-stu-id="20aaa-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="20aaa-104">Você pode importar um conjunto de termos usando um formato baseado em SKOS.</span><span class="sxs-lookup"><span data-stu-id="20aaa-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="20aaa-105">Para obter detalhes sobre o formato, confira [referência do formato SKOS da taxonomia do SharePoint](skos-format-reference.md).</span><span class="sxs-lookup"><span data-stu-id="20aaa-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span>

<span data-ttu-id="20aaa-106">É recomendável manter seus arquivos de importação para menos de 20.000 termos.</span><span class="sxs-lookup"><span data-stu-id="20aaa-106">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="20aaa-107">Arquivos maiores podem aumentar o tempo necessário para a validação e a importação.</span><span class="sxs-lookup"><span data-stu-id="20aaa-107">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="20aaa-108">No Centro de administração do SharePoint, expanda **Serviços de conteúdo** e, em seguida, clique em **Repositório de termos**.</span><span class="sxs-lookup"><span data-stu-id="20aaa-108">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="20aaa-109">Selecione o grupo de termos do qual você deseja importar o conjunto de termos.</span><span class="sxs-lookup"><span data-stu-id="20aaa-109">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="20aaa-110">Na barra de comandos, clique em **Importar conjunto de termos**.</span><span class="sxs-lookup"><span data-stu-id="20aaa-110">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="20aaa-111">Se você quiser baixar um arquivo de exemplo para usar como modelo, clique em **sample-metadata.ttl** para obter um arquivo de exemplo que usa o formato baseado em SKOS.</span><span class="sxs-lookup"><span data-stu-id="20aaa-111">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="20aaa-112">Crie o arquivo de importação que contém os conjuntos de termos e termos que você deseja importar.</span><span class="sxs-lookup"><span data-stu-id="20aaa-112">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="20aaa-113">Em **Formato de arquivo**, selecione **SKOS (\*.ttl)**.</span><span class="sxs-lookup"><span data-stu-id="20aaa-113">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="20aaa-114">Clique em **Procurar**, navegue até o arquivo de importação e o adicione.</span><span class="sxs-lookup"><span data-stu-id="20aaa-114">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="20aaa-115">Clique em **Importar**.</span><span class="sxs-lookup"><span data-stu-id="20aaa-115">Click **Import**.</span></span> <span data-ttu-id="20aaa-116">Não feche o painel até que a importação seja concluída.</span><span class="sxs-lookup"><span data-stu-id="20aaa-116">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="20aaa-117">Na importação bem-sucedida do arquivo, uma mensagem de êxito será exibida, e o repositório de termos será atualizado, e você poderá navegar até os conjuntos de termos criados recentemente.</span><span class="sxs-lookup"><span data-stu-id="20aaa-117">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="20aaa-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="20aaa-118">See also</span></span>

[<span data-ttu-id="20aaa-119">Introdução a metadados gerenciados</span><span class="sxs-lookup"><span data-stu-id="20aaa-119">Introduction to managed metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata)

[<span data-ttu-id="20aaa-120">Visão geral da compreensão de documentos</span><span class="sxs-lookup"><span data-stu-id="20aaa-120">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="20aaa-121">Importar conjuntos de termos (nível do site)</span><span class="sxs-lookup"><span data-stu-id="20aaa-121">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)