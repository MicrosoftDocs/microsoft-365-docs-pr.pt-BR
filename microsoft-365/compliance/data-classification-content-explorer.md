---
title: Usando o explorador de conteúdo de classificação de dados (visualização)
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
description: O explorador de conteúdo permite que se veja nativamente os itens rotulados.
ms.openlocfilehash: 6f062901acbf149f6fc56c266d10b370ed0c1112
ms.sourcegitcommit: 8ca97fa879ae4ea44468be629d6c32b429efeeec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2019
ms.locfileid: "39268415"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="42415-103">Usando o explorador de conteúdo de classificação de dados (visualização)</span><span class="sxs-lookup"><span data-stu-id="42415-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="42415-104">O explorador de conteúdo de classificação de dados permite que os itens que foram resumidos na página visão geral sejam exibidos nativamente.</span><span class="sxs-lookup"><span data-stu-id="42415-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="42415-105">Explorador de conteúdo</span><span class="sxs-lookup"><span data-stu-id="42415-105">Content explorer</span></span>

<span data-ttu-id="42415-106">O Explorador de conteúdo é uma representação atual dos itens que têm um rótulo de confidencialidade, um rótulo de retenção ou foram classificados como um tipo de informação confidencial em sua organização.</span><span class="sxs-lookup"><span data-stu-id="42415-106">Content explorer is a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

![captura de tela do explorador de conteúdo](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="42415-108">Permissões</span><span class="sxs-lookup"><span data-stu-id="42415-108">Permissions</span></span>

<span data-ttu-id="42415-109">Há duas funções que concedem acesso ao Explorador de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="42415-109">There are two roles that grant access to Content explorer:</span></span>

- <span data-ttu-id="42415-110">**Visualizador de Listas do Explorador de Conteúdo**: a associação nesta função permite que você veja cada item e seu local.</span><span class="sxs-lookup"><span data-stu-id="42415-110">**Content Explorer List viewer**: Membership in this role allows you to see each item and its location.</span></span>

- <span data-ttu-id="42415-111">**Visualizador de Conteúdos do Explorador de Conteúdo**: a associação nesta função permite exibir o conteúdo de cada item na lista.</span><span class="sxs-lookup"><span data-stu-id="42415-111">**Content Explorer Content viewer**: Membership in this role allows you to view the contents of each item in the list.</span></span>

<span data-ttu-id="42415-112">A conta que você usa para acessar o Explorador de conteúdo deve estar em uma ou em ambas as funções.</span><span class="sxs-lookup"><span data-stu-id="42415-112">The account you use to access Content explorer must be in one or both of the roles.</span></span> <span data-ttu-id="42415-113">Essas são funções independentes e não cumulativas.</span><span class="sxs-lookup"><span data-stu-id="42415-113">These are independent roles and are not cumulative.</span></span> <span data-ttu-id="42415-114">Por exemplo, se você deseja conceder a uma conta a capacidade de exibir apenas os itens e seus locais, conceda direitos ao visualizador de Listas do Explorador de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="42415-114">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="42415-115">Se você deseja que a mesma conta também possa exibir o conteúdo dos itens da lista, conceda também direitos ao visualizador de Conteúdos do Explorador de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="42415-115">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="42415-116">Como usar o explorador de conteúdo</span><span class="sxs-lookup"><span data-stu-id="42415-116">How to use content explorer</span></span>

1. <span data-ttu-id="42415-117">Abra o **centro de conformidade do Microsoft 365**  > **Classificação de dados** > \*\* Explorador de conteúdo\*\*.</span><span class="sxs-lookup"><span data-stu-id="42415-117">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="42415-118">Se souber o nome do rótulo ou o tipo de informação confidencial, digite-o na caixa Pesquisar.</span><span class="sxs-lookup"><span data-stu-id="42415-118">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="42415-119">Como alternativa, você pode procurar o item expandindo o tipo de rótulo e selecionando o rótulo da lista; um dos itens da parte de rótulo de retenção da lista é mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="42415-119">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="42415-120">Selecione um local em **Todas as localizações** e faça uma busca detalhada na estrutura de pastas para o item.</span><span class="sxs-lookup"><span data-stu-id="42415-120">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="42415-121">Clique duas vezes para abrir o item nativamente no explorador de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="42415-121">Double click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="42415-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="42415-122">See also</span></span>

- [<span data-ttu-id="42415-123">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="42415-123">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="42415-124">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="42415-124">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="42415-125">O que os tipos de informação confidencial procuram</span><span class="sxs-lookup"><span data-stu-id="42415-125">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="42415-126">Visão geral de políticas de retenção</span><span class="sxs-lookup"><span data-stu-id="42415-126">Overview of retention policies</span></span>](retention-policies.md)
