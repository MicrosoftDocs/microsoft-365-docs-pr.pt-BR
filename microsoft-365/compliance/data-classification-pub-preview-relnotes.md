---
title: Notas de versão de classificação de dados
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Notas de versão para a classificação de dados.
ms.openlocfilehash: 71d8e8e4fffddc4c9373a2bdd37d4509337ec231
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127136"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="d24ff-103">Notas de versão de classificação de dados</span><span class="sxs-lookup"><span data-stu-id="d24ff-103">Data classification release notes</span></span>

<span data-ttu-id="d24ff-104">Examine estas notas de versão para ter a melhor experiência com a classificação de dados.</span><span class="sxs-lookup"><span data-stu-id="d24ff-104">Please review these release notes so that you have the best experience with data classification.</span></span>

## <a name="exchange-mailbox-count"></a><span data-ttu-id="d24ff-105">Contagem de caixa de correio do Exchange</span><span class="sxs-lookup"><span data-stu-id="d24ff-105">Exchange mailbox count</span></span>

<span data-ttu-id="d24ff-106">Você observará que uma pequena dica de ferramenta é exibida quando você detalha as caixas de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="d24ff-106">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="d24ff-107">Isso é para destacar o fato de que a contagem agregada exibida para tipo de informações confidenciais, rótulo de confidencialidade e rótulo de retenção pode não corresponder exatamente ao número de itens que você encontrará dentro da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="d24ff-107">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="d24ff-108">Isso ocorre porque o detalhamento da pasta busca a visualização dinâmica de conteúdo, que é classificada, enquanto a contagem agregada é calculada.</span><span class="sxs-lookup"><span data-stu-id="d24ff-108">This is because the drill down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="d24ff-109">Processamento de documentos criptografados</span><span class="sxs-lookup"><span data-stu-id="d24ff-109">Rendering of encrypted documents</span></span>

<span data-ttu-id="d24ff-110">Os arquivos do SharePoint, Exchange e OneDrive que estão criptografados não serão renderizados no Gerenciador de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="d24ff-110">SharePoint, Exchange, and OneDrive files that are encrypted will not render in the content explorer.</span></span> <span data-ttu-id="d24ff-111">Esse é um problema sensível que exige um equilíbrio entre a necessidade de ver o conteúdo do arquivo no Gerenciador de conteúdo e a necessidade de manter o conteúdo criptografado.</span><span class="sxs-lookup"><span data-stu-id="d24ff-111">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="d24ff-112">Com as permissões concedidas pelo \*\*Visualizador de lista do Gerenciador de conteúdo \*\*e **Visualizador de conteúdo do Gerenciador de conteúdo** grupos de funções, você verá uma exibição de lista dos arquivos, os metadados do arquivo e um link que você pode usar para acessar o conteúdo pelo cliente da Web.</span><span class="sxs-lookup"><span data-stu-id="d24ff-112">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="d24ff-113">Caracteres com suporte em nomes de rótulo de retenção na pesquisa do SharePoint</span><span class="sxs-lookup"><span data-stu-id="d24ff-113">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="d24ff-114">O SharePoint Search não oferece suporte a nomes de rótulo de retenção com `-`ou `_` neles.</span><span class="sxs-lookup"><span data-stu-id="d24ff-114">SharePoint search does not support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="d24ff-115">Por exemplo `Label-MIP` e `Label_MIP` não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="d24ff-115">For example `Label-MIP` and `Label_MIP` are not supported.</span></span> <span data-ttu-id="d24ff-116">A pesquisa do SharePoint oferece suporte a esses caracteres em nomes de rótulos e informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="d24ff-116">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="d24ff-117">O OneDrive permanece no modo versão prévia</span><span class="sxs-lookup"><span data-stu-id="d24ff-117">OneDrive remains in preview</span></span>

<span data-ttu-id="d24ff-118">Ouvimos seus comentários sobre a integração do OneDrive durante nosso programa de versão prévia.</span><span class="sxs-lookup"><span data-stu-id="d24ff-118">We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="d24ff-119">Enquanto percorrermos os detalhes, pode ser que você encontre dados/fluxos inconsistentes.</span><span class="sxs-lookup"><span data-stu-id="d24ff-119">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="d24ff-120">Continuaremos a exibir o OneDrive na visualização até que todas as correções estejam disponíveis.</span><span class="sxs-lookup"><span data-stu-id="d24ff-120">We will continue to showcase OneDrive in preview till all fixes are in place.</span></span> <span data-ttu-id="d24ff-121">Agradecemos o seu apoio contínuo neste tema.</span><span class="sxs-lookup"><span data-stu-id="d24ff-121">We appreciate your continued support on this.</span></span>


## <a name="see-also"></a><span data-ttu-id="d24ff-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="d24ff-122">See also</span></span>

- [<span data-ttu-id="d24ff-123">Introdução à classificação de dados (visualização)</span><span class="sxs-lookup"><span data-stu-id="d24ff-123">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="d24ff-124">Exibir atividade do rótulo (visualização)</span><span class="sxs-lookup"><span data-stu-id="d24ff-124">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="d24ff-125">Exibir conteúdo rotulado (visualização)</span><span class="sxs-lookup"><span data-stu-id="d24ff-125">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="d24ff-126">Saiba mais sobre rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="d24ff-126">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="d24ff-127">Saiba mais sobre as políticas de retenção e os rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="d24ff-127">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="d24ff-128">Definições da entidade do tipo de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="d24ff-128">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)