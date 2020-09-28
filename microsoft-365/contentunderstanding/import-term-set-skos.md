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
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: aaed88463f690853672780b48a8ee3857a956847
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295724"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a><span data-ttu-id="309d8-103">Importar um conjunto de termos usando um formato baseado em SKOS</span><span class="sxs-lookup"><span data-stu-id="309d8-103">Import a term set using a SKOS-based format</span></span>

<span data-ttu-id="309d8-104">Você pode importar um conjunto de termos usando um formato baseado em SKOS.</span><span class="sxs-lookup"><span data-stu-id="309d8-104">You can import a term set using a SKOS-based format.</span></span> <span data-ttu-id="309d8-105">Para obter detalhes sobre o formato, consulte [referência de formato skos de taxonomia do SharePoint](skos-format-reference.md).</span><span class="sxs-lookup"><span data-stu-id="309d8-105">For details about the format, see [SharePoint taxonomy SKOS format reference](skos-format-reference.md).</span></span>

<span data-ttu-id="309d8-106">Recomendamos manter seus arquivos de importação para menos de 20.000 termos.</span><span class="sxs-lookup"><span data-stu-id="309d8-106">We recommend keeping your import files to less than 20,000 terms.</span></span> <span data-ttu-id="309d8-107">Arquivos maiores podem aumentar o tempo gasto para validação e importação.</span><span class="sxs-lookup"><span data-stu-id="309d8-107">Larger files can increase the time taken for validation and import.</span></span>

1. <span data-ttu-id="309d8-108">No centro de administração do SharePoint, expanda **serviços de conteúdo**e clique em **repositório de termos**.</span><span class="sxs-lookup"><span data-stu-id="309d8-108">In the SharePoint admin center, expand **Content services**, and then click **Term store**.</span></span>

2. <span data-ttu-id="309d8-109">Selecione o grupo de termos em que você deseja importar o conjunto de termos.</span><span class="sxs-lookup"><span data-stu-id="309d8-109">Select the term group where you want to import the term set.</span></span>

3. <span data-ttu-id="309d8-110">Na barra de comandos, clique em **Importar conjunto de termos**.</span><span class="sxs-lookup"><span data-stu-id="309d8-110">In the command bar, click **Import term set**.</span></span>
 
4.  <span data-ttu-id="309d8-111">Se você deseja baixar um arquivo de exemplo para usar como modelo, clique em **Sample-Metadata. TTL** para obter um arquivo de exemplo que usa o formato baseado em skos.</span><span class="sxs-lookup"><span data-stu-id="309d8-111">If you want to download a sample file to use as a template, click **sample-metadata.ttl** to get a sample file that uses the SKOS-based format.</span></span>
 
5.  <span data-ttu-id="309d8-112">Crie o arquivo de importação que contém os conjuntos de termos & termos que você deseja importar.</span><span class="sxs-lookup"><span data-stu-id="309d8-112">Create the import file that contains the term sets & terms you wish to import.</span></span>

6.  <span data-ttu-id="309d8-113">Em **formato de arquivo**, selecione **skos (\*. TTL)**.</span><span class="sxs-lookup"><span data-stu-id="309d8-113">Under **File format**, select **SKOS (\*.ttl)**.</span></span>

7.  <span data-ttu-id="309d8-114">Clique em **procurar** e navegue até e adicione o arquivo de importação.</span><span class="sxs-lookup"><span data-stu-id="309d8-114">Click **Browse** and navigate to and add your import file.</span></span>

8.  <span data-ttu-id="309d8-115">Clique em \*\*Importar \*\*.</span><span class="sxs-lookup"><span data-stu-id="309d8-115">Click **Import**.</span></span> <span data-ttu-id="309d8-116">Não feche o painel até que a importação seja concluída.</span><span class="sxs-lookup"><span data-stu-id="309d8-116">Do not close the panel until the import completes.</span></span>

<span data-ttu-id="309d8-117">Após a importação bem-sucedida do arquivo, será exibida uma mensagem de êxito, e o repositório de termos será atualizado e você poderá navegar até os conjuntos de termos recém-criados.</span><span class="sxs-lookup"><span data-stu-id="309d8-117">On successful import of the file, a success message will be displayed, and the term store will refresh and you can navigate to the newly created term sets.</span></span>

## <a name="see-also"></a><span data-ttu-id="309d8-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="309d8-118">See also</span></span>

[<span data-ttu-id="309d8-119">Introdução a metadados gerenciados</span><span class="sxs-lookup"><span data-stu-id="309d8-119">Introduction to managed metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata)

[<span data-ttu-id="309d8-120">Visão geral da compreensão do documento</span><span class="sxs-lookup"><span data-stu-id="309d8-120">Document understanding overview</span></span>](document-understanding-overview.md)

[<span data-ttu-id="309d8-121">Importar conjuntos de termos (nível de site)</span><span class="sxs-lookup"><span data-stu-id="309d8-121">Import term sets (site level)</span></span>](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)