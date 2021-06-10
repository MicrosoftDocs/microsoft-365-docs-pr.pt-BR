---
title: Notas de versão de classificação de dados
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: normal
recommendations: false
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Notas de versão para a classificação de dados.
ms.openlocfilehash: bbce01555367c6151a7b16b551d5580ebcaf9d43
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086702"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="77afe-103">Notas de versão de classificação de dados</span><span class="sxs-lookup"><span data-stu-id="77afe-103">Data classification release notes</span></span>


## <a name="exchange-mailbox-count"></a><span data-ttu-id="77afe-104">Contagem de caixa de correio do Exchange</span><span class="sxs-lookup"><span data-stu-id="77afe-104">Exchange mailbox count</span></span>

<span data-ttu-id="77afe-105">Você observará que uma pequena dica de ferramenta é exibida quando você detalha as caixas de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="77afe-105">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="77afe-106">Isso é para destacar o fato de que a contagem agregada exibida para tipo de informações confidenciais, rótulo de confidencialidade e rótulo de retenção pode não corresponder exatamente ao número de itens que você encontrará dentro da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="77afe-106">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="77afe-107">Isso ocorre porque o detalhamento da pasta busca a visualização dinâmica de conteúdo, que é classificada, enquanto a contagem agregada é calculada.</span><span class="sxs-lookup"><span data-stu-id="77afe-107">This is because the drill-down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="77afe-108">Processamento de documentos criptografados</span><span class="sxs-lookup"><span data-stu-id="77afe-108">Rendering of encrypted documents</span></span>

<span data-ttu-id="77afe-109">Os arquivos do SharePoint, Exchange e OneDrive que estão criptografados não serão renderizados no explorador de conteúdos.</span><span class="sxs-lookup"><span data-stu-id="77afe-109">SharePoint, Exchange, and OneDrive files that are encrypted don't render in the content explorer.</span></span> <span data-ttu-id="77afe-110">Esse é um problema sensível que exige um equilíbrio entre a necessidade de ver o conteúdo do arquivo no Gerenciador de conteúdo e a necessidade de manter o conteúdo criptografado.</span><span class="sxs-lookup"><span data-stu-id="77afe-110">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="77afe-111">Com as permissões concedidas pelo **Visualizador de lista do Gerenciador de conteúdo** e **Visualizador de conteúdo do Gerenciador de conteúdo** grupos de funções, você verá uma exibição de lista dos arquivos, os metadados do arquivo e um link que você pode usar para acessar o conteúdo pelo cliente da Web.</span><span class="sxs-lookup"><span data-stu-id="77afe-111">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="77afe-112">Caracteres com suporte em nomes de rótulo de retenção na pesquisa do SharePoint</span><span class="sxs-lookup"><span data-stu-id="77afe-112">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="77afe-113">O SharePoint Search não oferece suporte a nomes de rótulo de retenção com `-`ou `_` neles.</span><span class="sxs-lookup"><span data-stu-id="77afe-113">SharePoint search doesn't support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="77afe-114">Por exemplo `Label-MIP` e `Label_MIP` não têm suporte.</span><span class="sxs-lookup"><span data-stu-id="77afe-114">For example, `Label-MIP` and `Label_MIP` aren't supported.</span></span> <span data-ttu-id="77afe-115">A pesquisa do SharePoint oferece suporte a esses caracteres em nomes de rótulos e informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="77afe-115">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="77afe-116">O OneDrive permanece no modo versão prévia</span><span class="sxs-lookup"><span data-stu-id="77afe-116">OneDrive remains in preview</span></span>

<span data-ttu-id="77afe-117">Ouvimos seus comentários sobre a integração do OneDrive durante nosso programa de versão prévia.</span><span class="sxs-lookup"><span data-stu-id="77afe-117">Thanks for your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="77afe-118">Enquanto percorrermos os detalhes, pode ser que você encontre dados/fluxos inconsistentes.</span><span class="sxs-lookup"><span data-stu-id="77afe-118">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="77afe-119">Continuaremos a exibir o OneDrive na visualização até que todas as correções estejam disponíveis.</span><span class="sxs-lookup"><span data-stu-id="77afe-119">We'll continue to showcase OneDrive in preview until all fixes are in place.</span></span> <span data-ttu-id="77afe-120">Agradecemos o seu apoio contínuo neste tema.</span><span class="sxs-lookup"><span data-stu-id="77afe-120">We appreciate your continued support.</span></span>


## <a name="see-also"></a><span data-ttu-id="77afe-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="77afe-121">See also</span></span>

- [<span data-ttu-id="77afe-122">Introdução à classificação de dados (visualização)</span><span class="sxs-lookup"><span data-stu-id="77afe-122">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="77afe-123">Exibir atividade do rótulo (visualização)</span><span class="sxs-lookup"><span data-stu-id="77afe-123">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="77afe-124">Exibir conteúdo rotulado (visualização)</span><span class="sxs-lookup"><span data-stu-id="77afe-124">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="77afe-125">Saiba mais sobre rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="77afe-125">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="77afe-126">Saiba mais sobre as políticas de retenção e os rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="77afe-126">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="77afe-127">Definições da entidade do tipo de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="77afe-127">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)