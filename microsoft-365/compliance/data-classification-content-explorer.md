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
ms.openlocfilehash: 9e9ad76d2bdd7f74368121346f7e04d1208803ff
ms.sourcegitcommit: 99d759d5c4e7d81266c3ebc087eaa37486cc0bc1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2019
ms.locfileid: "39818853"
---
# <a name="using-data-classification-content-explorer-preview"></a><span data-ttu-id="a1818-103">Usando o explorador de conteúdo de classificação de dados (visualização)</span><span class="sxs-lookup"><span data-stu-id="a1818-103">Using data classification content explorer (preview)</span></span>

<span data-ttu-id="a1818-104">O explorador de conteúdo de classificação de dados permite que os itens que foram resumidos na página visão geral sejam exibidos nativamente.</span><span class="sxs-lookup"><span data-stu-id="a1818-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="content-explorer"></a><span data-ttu-id="a1818-105">Explorador de conteúdo</span><span class="sxs-lookup"><span data-stu-id="a1818-105">Content explorer</span></span>

<span data-ttu-id="a1818-106">O Explorador de conteúdo mostra uma imagem instantânea atual dos itens que têm um rótulo de confidencialidade, um rótulo de retenção ou foram classificados como um tipo de informação confidencial em sua organização.</span><span class="sxs-lookup"><span data-stu-id="a1818-106">Content explorer is a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="a1818-107">Tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="a1818-107">Sensitive information types</span></span>

<span data-ttu-id="a1818-108">Uma **política DLP** ajuda a proteger informações confidenciais, que são definidas como um [tipo de informações confidenciais](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a1818-108">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="a1818-109">O Microsoft 365 inclui [definições para vários tipos de informações confidenciais comuns](what-the-sensitive-information-types-look-for.md) em diferentes regiões, prontas para você usar.</span><span class="sxs-lookup"><span data-stu-id="a1818-109">Office 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> <span data-ttu-id="a1818-110">Por exemplo, um número de cartão de crédito, números de contas bancárias, números de ID nacionais e números de serviço Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="a1818-110">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="a1818-111">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="a1818-111">Sensitivity labels</span></span>

<span data-ttu-id="a1818-112">Um [rótulo de confidencialidade](sensitivity-labels.md) é simplesmente uma marca que indica o valor do item para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="a1818-112">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="a1818-113">Ele pode ser aplicado manualmente ou automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a1818-113">It can be applied manually, or automatically.</span></span> <span data-ttu-id="a1818-114">Uma vez aplicado, ele é incorporado ao documento e o acompanhará em todos os lugares.</span><span class="sxs-lookup"><span data-stu-id="a1818-114">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="a1818-115">Um rótulo de confidencialidade habilita vários comportamentos de proteção, como uma marca d' água obrigatória ou a criptografia.</span><span class="sxs-lookup"><span data-stu-id="a1818-115">the presence of the tag enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="a1818-116">Com a proteção de ponto de extremidade habilitada, você pode até mesmo impedir que um item saia de seu controle organizacional.</span><span class="sxs-lookup"><span data-stu-id="a1818-116">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

### <a name="retention-labels"></a><span data-ttu-id="a1818-117">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="a1818-117">Retention labels</span></span>

<span data-ttu-id="a1818-118">Um [rótulo de retenção](labels.md) permite definir por quanto tempo um item rotulado será mantido e as etapas a serem seguidas antes de excluí-lo.</span><span class="sxs-lookup"><span data-stu-id="a1818-118">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="a1818-119">Ele pode ser aplicado manualmente ou automaticamente através de políticas.</span><span class="sxs-lookup"><span data-stu-id="a1818-119">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="a1818-120">Eles podem ajudar a sua organização a se manter em conformidade com as determinações regulamentares e legais.</span><span class="sxs-lookup"><span data-stu-id="a1818-120">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

![captura de tela do explorador de conteúdo](media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="a1818-122">Permissões</span><span class="sxs-lookup"><span data-stu-id="a1818-122">Permissions</span></span>

<span data-ttu-id="a1818-123">Há duas funções que concedem acesso ao Explorador de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="a1818-123">There are two roles that grant access to Content explorer:</span></span>

- <span data-ttu-id="a1818-124">**Visualizador de Listas do Explorador de Conteúdo**: a associação nesta função permite que você veja cada item e seu local.</span><span class="sxs-lookup"><span data-stu-id="a1818-124">**Content Explorer List viewer**: Membership in this role allows you to see each item and its location.</span></span>

- <span data-ttu-id="a1818-125">**Visualizador de Conteúdos do Explorador de Conteúdo**: a associação nesta função permite exibir o conteúdo de cada item na lista.</span><span class="sxs-lookup"><span data-stu-id="a1818-125">**Content Explorer Content viewer**: Membership in this role allows you to view the contents of each item in the list.</span></span>

<span data-ttu-id="a1818-126">A conta que você usa para acessar o Explorador de conteúdo deve estar em uma ou em ambas as funções.</span><span class="sxs-lookup"><span data-stu-id="a1818-126">The account you use to access Content explorer must be in one or both of the roles.</span></span> <span data-ttu-id="a1818-127">Essas são funções independentes e não cumulativas.</span><span class="sxs-lookup"><span data-stu-id="a1818-127">These are independent roles and are not cumulative.</span></span> <span data-ttu-id="a1818-128">Por exemplo, se você deseja conceder a uma conta a capacidade de exibir apenas os itens e seus locais, conceda direitos ao visualizador de Listas do Explorador de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a1818-128">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="a1818-129">Se você deseja que a mesma conta também possa exibir o conteúdo dos itens da lista, conceda também direitos ao visualizador de Conteúdos do Explorador de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a1818-129">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="a1818-130">Como usar o explorador de conteúdo</span><span class="sxs-lookup"><span data-stu-id="a1818-130">How to use content explorer</span></span>

1. <span data-ttu-id="a1818-131">Abra o **centro de conformidade do Microsoft 365**  > **Classificação de dados** > \*\* Explorador de conteúdo\*\*.</span><span class="sxs-lookup"><span data-stu-id="a1818-131">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="a1818-132">Se souber o nome do rótulo ou o tipo de informação confidencial, digite-o na caixa Pesquisar.</span><span class="sxs-lookup"><span data-stu-id="a1818-132">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="a1818-133">Como alternativa, você pode procurar o item expandindo o tipo de rótulo e selecionando o rótulo da lista; um dos itens da parte de rótulo de retenção da lista é mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="a1818-133">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="a1818-134">Selecione um local em **Todas as localizações** e faça uma busca detalhada na estrutura de pastas para o item.</span><span class="sxs-lookup"><span data-stu-id="a1818-134">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="a1818-135">Clique duas vezes para abrir o item nativamente no explorador de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="a1818-135">Double click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1818-136">Confira também</span><span class="sxs-lookup"><span data-stu-id="a1818-136">See also</span></span>

- [<span data-ttu-id="a1818-137">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="a1818-137">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="a1818-138">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="a1818-138">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="a1818-139">O que os tipos de informação confidencial procuram</span><span class="sxs-lookup"><span data-stu-id="a1818-139">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="a1818-140">Visão geral de políticas de retenção</span><span class="sxs-lookup"><span data-stu-id="a1818-140">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="a1818-141">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="a1818-141">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
