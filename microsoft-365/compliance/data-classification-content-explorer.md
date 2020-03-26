---
title: Introdução ao Gerenciador de conteúdo (visualização)
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 91246a701e1c5a030f4c9c53e25e56c137e7569b
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929403"
---
# <a name="get-started-with-content-explorer-preview"></a><span data-ttu-id="24e1b-103">Introdução ao Gerenciador de conteúdo (visualização)</span><span class="sxs-lookup"><span data-stu-id="24e1b-103">Get started with content explorer (preview)</span></span>

<span data-ttu-id="24e1b-104">O explorador de conteúdo de classificação de dados permite que os itens que foram resumidos na página visão geral sejam exibidos nativamente.</span><span class="sxs-lookup"><span data-stu-id="24e1b-104">The data classification content explorer allows you to natively view the items that were summarized on the overview page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="24e1b-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="24e1b-105">Prerequisites</span></span>

<span data-ttu-id="24e1b-106">Toda conta que acessa e usa o explorador de atividades deve ter uma licença atribuída a partir de uma destas assinaturas:</span><span class="sxs-lookup"><span data-stu-id="24e1b-106">Every account that accesses and uses activity explorer must have a license assigned to it from one of these subscriptions:</span></span>

- <span data-ttu-id="24e1b-107">Microsoft 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="24e1b-107">Microsoft 365 (E5)</span></span>
- <span data-ttu-id="24e1b-108">Office 365 (E5)</span><span class="sxs-lookup"><span data-stu-id="24e1b-108">Office 365 (E5)</span></span>
- <span data-ttu-id="24e1b-109">Complemento de Conformidade Avançada (E5)</span><span class="sxs-lookup"><span data-stu-id="24e1b-109">Advanced Compliance (E5) add-on</span></span>
- <span data-ttu-id="24e1b-110">Complemento Avançado de Inteligência contra Ameaças (E5)</span><span class="sxs-lookup"><span data-stu-id="24e1b-110">Advanced Threat Intelligence (E5) add-on</span></span>

## <a name="content-explorer"></a><span data-ttu-id="24e1b-111">Explorador de conteúdo</span><span class="sxs-lookup"><span data-stu-id="24e1b-111">Content explorer</span></span>

<span data-ttu-id="24e1b-112">O Explorador de conteúdo mostra uma imagem instantânea atual dos itens que têm um rótulo de confidencialidade, um rótulo de retenção ou foram classificados como um tipo de informação confidencial em sua organização.</span><span class="sxs-lookup"><span data-stu-id="24e1b-112">Content explorer shows a current snapshot of the items that have a sensitivity label, a retention label or have been classified as a sensitive information type in your organization.</span></span>

### <a name="sensitive-information-types"></a><span data-ttu-id="24e1b-113">Tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="24e1b-113">Sensitive information types</span></span>

<span data-ttu-id="24e1b-114">Uma **política DLP** ajuda a proteger informações confidenciais, que são definidas como um [tipo de informações confidenciais](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="24e1b-114">A [DLP policy](data-loss-prevention-policies.md) can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="24e1b-115">O Microsoft 365 inclui [definições para vários tipos de informações confidenciais comuns](what-the-sensitive-information-types-look-for.md) em diferentes regiões, prontas para você usar.</span><span class="sxs-lookup"><span data-stu-id="24e1b-115">Microsoft 365 includes [definitions for many common sensitive information types](what-the-sensitive-information-types-look-for.md) across many different regions that are ready for you to use.</span></span> <span data-ttu-id="24e1b-116">Por exemplo, um número de cartão de crédito, números de contas bancárias, números de ID nacionais e números de serviço Windows Live ID.</span><span class="sxs-lookup"><span data-stu-id="24e1b-116">For example, a credit card number, bank account numbers, national ID numbers, and Windows Live ID service numbers.</span></span>

### <a name="sensitivity-labels"></a><span data-ttu-id="24e1b-117">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="24e1b-117">Sensitivity labels</span></span>

<span data-ttu-id="24e1b-118">Um [rótulo de confidencialidade](sensitivity-labels.md) é simplesmente uma marca que indica o valor do item para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="24e1b-118">A [sensitivity label](sensitivity-labels.md) is simply a tag that indicates the value of the item to your organization.</span></span> <span data-ttu-id="24e1b-119">Ele pode ser aplicado manualmente ou automaticamente.</span><span class="sxs-lookup"><span data-stu-id="24e1b-119">It can be applied manually, or automatically.</span></span> <span data-ttu-id="24e1b-120">Uma vez aplicado, ele é incorporado ao documento e o acompanhará em todos os lugares.</span><span class="sxs-lookup"><span data-stu-id="24e1b-120">Once applied it gets embedded in the document and will follow it everywhere it goes.</span></span> <span data-ttu-id="24e1b-121">Um rótulo de confidencialidade habilita vários comportamentos de proteção, como uma marca d' água obrigatória ou a criptografia.</span><span class="sxs-lookup"><span data-stu-id="24e1b-121">A sensitivity label enables various protective behaviors, such as mandatory watermarking or encryption.</span></span> <span data-ttu-id="24e1b-122">Com a proteção de ponto de extremidade habilitada, você pode até mesmo impedir que um item saia de seu controle organizacional.</span><span class="sxs-lookup"><span data-stu-id="24e1b-122">With end point protection enabled you can even prevent an item from leaving your organizational control.</span></span>

<span data-ttu-id="24e1b-123">Os rótulos de confidencialidade devem ser habilitados para arquivos que estão no SharePoint e no OneDrive para que os dados correspondentes apareçam na página de classificação de dados.</span><span class="sxs-lookup"><span data-stu-id="24e1b-123">Sensitivity labels must be enabled for files that are in SharePoint and OneDrive in order for the corresponding data to surface in the data classification page.</span></span> <span data-ttu-id="24e1b-124">Para saber mais, confira [Habilitar rótulos de confidencialidade para arquivos do Office no SharePoint e no OneDrive (visualização pública)](sensitivity-labels-sharepoint-onedrive-files.md)</span><span class="sxs-lookup"><span data-stu-id="24e1b-124">For more information, see [Enable sensitivity labels for Office files in SharePoint and OneDrive (public preview)](sensitivity-labels-sharepoint-onedrive-files.md).</span></span>

### <a name="retention-labels"></a><span data-ttu-id="24e1b-125">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="24e1b-125">Retention labels</span></span>

<span data-ttu-id="24e1b-126">Um [rótulo de retenção](labels.md) permite definir por quanto tempo um item rotulado será mantido e as etapas a serem seguidas antes de excluí-lo.</span><span class="sxs-lookup"><span data-stu-id="24e1b-126">A [retention label](labels.md) allows you to define how long a labeled item is kept and the steps to be taken prior to deleting it.</span></span> <span data-ttu-id="24e1b-127">Ele pode ser aplicado manualmente ou automaticamente através de políticas.</span><span class="sxs-lookup"><span data-stu-id="24e1b-127">They are applied manually or automatically via policies.</span></span> <span data-ttu-id="24e1b-128">Eles podem ajudar a sua organização a se manter em conformidade com as determinações regulamentares e legais.</span><span class="sxs-lookup"><span data-stu-id="24e1b-128">They can play a role in helping your organization stay in compliance with legal and regulatory requirements.</span></span>

![captura de tela do explorador de conteúdo](../media/data-classification-content-explorer-1.png)

### <a name="permissions"></a><span data-ttu-id="24e1b-130">Permissões</span><span class="sxs-lookup"><span data-stu-id="24e1b-130">Permissions</span></span>

<span data-ttu-id="24e1b-131">Há duas funções que concedem acesso ao Explorador de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="24e1b-131">There are two roles that grant access to content explorer:</span></span>

- <span data-ttu-id="24e1b-132">**Visualizador de Listas do Explorador de Conteúdo**: a associação neste grupo de função permite que você veja cada item e seu local.</span><span class="sxs-lookup"><span data-stu-id="24e1b-132">**Content Explorer List viewer**: Membership in this role group allows you to see each item and its location.</span></span> <span data-ttu-id="24e1b-133">A função `data classification list viewer` foi predefinida para esse grupo de função.</span><span class="sxs-lookup"><span data-stu-id="24e1b-133">The `data classification list viewer` role has been pre-assigned to this role group.</span></span>

- <span data-ttu-id="24e1b-134">**Visualizador de Conteúdos do Explorador de Conteúdo**: a associação neste grupo de função permite exibir o conteúdo de cada item na lista.</span><span class="sxs-lookup"><span data-stu-id="24e1b-134">**Content Explorer Content viewer**: Membership in this role group allows you to view the contents of each item in the list.</span></span> <span data-ttu-id="24e1b-135">A função `data classification content viewer` foi predefinida para esse grupo de função.</span><span class="sxs-lookup"><span data-stu-id="24e1b-135">The `data classification content viewer` role has been pre-assigned to this role group.</span></span>

<span data-ttu-id="24e1b-136">A conta que você usa para acessar o Explorador de conteúdo deve estar em uma ou em ambas os grupos de funções.</span><span class="sxs-lookup"><span data-stu-id="24e1b-136">The account you use to access content explorer must be in one or both of the role groups.</span></span> <span data-ttu-id="24e1b-137">Esses são grupos de funções independentes e não são cumulativos.</span><span class="sxs-lookup"><span data-stu-id="24e1b-137">These are independent role groups and are not cumulative.</span></span> <span data-ttu-id="24e1b-138">Por exemplo, se você deseja conceder a uma conta a capacidade de exibir apenas os itens e seus locais, conceda direitos ao visualizador de Listas do Explorador de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="24e1b-138">For example, if you want to grant an account the ability to view the items and their locations only, grant Content Explorer List viewer rights.</span></span> <span data-ttu-id="24e1b-139">Se você deseja que a mesma conta também possa exibir o conteúdo dos itens da lista, conceda também direitos ao visualizador de Conteúdos do Explorador de Conteúdo.</span><span class="sxs-lookup"><span data-stu-id="24e1b-139">If you want that same account to also be able to view the contents of the items in the list, grant Content Explorer Content viewer rights as well.</span></span>

<span data-ttu-id="24e1b-140">Você também pode atribuir uma ou ambas as funções a um grupo de funções personalizada para ajustar o acesso ao Gerenciador de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="24e1b-140">You can also assign either or both of the roles to a custom role group to tailor access to content explorer.</span></span>

<span data-ttu-id="24e1b-141">Um administrador global, um administrador de conformidade ou um administrador de dados pode atribuir o Visualizador de lista do Gerenciador de conteúdo  necessário e Visualizador de conteúdo do Gerenciador de conteúdo a associação do grupo de função.</span><span class="sxs-lookup"><span data-stu-id="24e1b-141">A Global admin, Compliance admin, or Data admin can assign the necessary Content Explorer List Viewer, and Content Explorer Content Viewer role group membership.</span></span>

### <a name="how-to-use-content-explorer"></a><span data-ttu-id="24e1b-142">Como usar o explorador de conteúdo</span><span class="sxs-lookup"><span data-stu-id="24e1b-142">How to use content explorer</span></span>

1. <span data-ttu-id="24e1b-143">Abra o **centro de conformidade do Microsoft 365**  > **Classificação de dados** > \*\* Explorador de conteúdo\*\*.</span><span class="sxs-lookup"><span data-stu-id="24e1b-143">Open **Microsoft 365 compliance center**  > **Data classification** > **Content explorer**.</span></span>
2. <span data-ttu-id="24e1b-144">Se souber o nome do rótulo ou o tipo de informação confidencial, digite-o na caixa Pesquisar.</span><span class="sxs-lookup"><span data-stu-id="24e1b-144">If you know the name of the label, or the sensitive information type, you can type that into the search box.</span></span>
3. <span data-ttu-id="24e1b-145">Como alternativa, você pode procurar o item expandindo o tipo de rótulo e selecionando o rótulo da lista; um dos itens da parte de rótulo de retenção da lista é mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="24e1b-145">Alternately, you can browse for the item by expanding the label type and selecting the label from the list, an item from the retention label portion of the list is show below.</span></span>
4. <span data-ttu-id="24e1b-146">Selecione um local em **Todas as localizações** e faça uma busca detalhada na estrutura de pastas para o item.</span><span class="sxs-lookup"><span data-stu-id="24e1b-146">Select a location under **All locations** and drill down the folder structure to the item.</span></span>
5. <span data-ttu-id="24e1b-147">Clique duas vezes para abrir o item nativamente no explorador de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="24e1b-147">Double-click to open the item natively in content explorer.</span></span>

## <a name="see-also"></a><span data-ttu-id="24e1b-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="24e1b-148">See also</span></span>

- [<span data-ttu-id="24e1b-149">Rótulos de confidencialidade</span><span class="sxs-lookup"><span data-stu-id="24e1b-149">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="24e1b-150">Rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="24e1b-150">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="24e1b-151">O que os tipos de informação confidencial procuram</span><span class="sxs-lookup"><span data-stu-id="24e1b-151">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)
- [<span data-ttu-id="24e1b-152">Visão geral de políticas de retenção</span><span class="sxs-lookup"><span data-stu-id="24e1b-152">Overview of retention policies</span></span>](retention-policies.md)
- [<span data-ttu-id="24e1b-153">Visão geral da prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="24e1b-153">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
