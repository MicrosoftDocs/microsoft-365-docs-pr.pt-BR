---
title: Criar uma política de exclusão de documentos
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
ms.assetid: 41b2ed73-eb8d-4429-945e-a8197894585a
description: As organizações frequentemente são obrigadas a manter documentos por um determinado período devido a regulamentações de conformidade, legais ou outras. No entanto, reter os documentos por mais tempo do que o necessário poderá expor a organização a riscos legais.
ms.openlocfilehash: 5550f65e5b2ecb5dca775e1d851548913b8e8517
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632256"
---
# <a name="create-a-document-deletion-policy"></a><span data-ttu-id="ebdb4-104">Criar uma política de exclusão de documentos</span><span class="sxs-lookup"><span data-stu-id="ebdb4-104">Create a document deletion policy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebdb4-105">Em frente, recomendamos que você use uma política de retenção ou rótulos de retenção criados no centro de conformidade da Microsoft 365, no centro de segurança &amp; da Microsoft 365 ou no centro de conformidade de segurança em vez de uma política de exclusão de documentos.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-105">Moving forward, we recommend that you use a retention policy or retention labels created in the Microsoft 365 compliance center, Microsoft 365 security center, or Security &amp; Compliance Center instead of a document deletion policy.</span></span> <span data-ttu-id="ebdb4-106">As políticas de exclusão de documentos continuarão a funcionar lado a lado com políticas de retenção, mas se você precisar reter ou excluir conteúdo em qualquer lugar no Office 365, recomendamos que você use uma política de retenção.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-106">Document deletion policies will continue to work side by side with retention policies, but if you need to retain or delete content anywhere in Office 365, we recommend that you use a retention policy.</span></span> <span data-ttu-id="ebdb4-107">Para obter mais informações, consulte [usar uma política de retenção em vez desses recursos](retention-policies.md#use-a-retention-policy-instead-of-these-features).</span><span class="sxs-lookup"><span data-stu-id="ebdb4-107">For more information, see [Use a retention policy instead of these features](retention-policies.md#use-a-retention-policy-instead-of-these-features).</span></span> 
  
<span data-ttu-id="ebdb4-p103">As organizações frequentemente são obrigadas a manter documentos por um determinado período devido a regulamentações de conformidade, legais ou outras. No entanto, reter os documentos por mais tempo do que o necessário poderá expor a organização a riscos legais.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-p103">Organizations are often required to retain documents for a certain period of time due to compliance, legal, or other regulations. However, retaining documents for longer than required can expose the organization to legal risk.</span></span>
  
<span data-ttu-id="ebdb4-110">Com uma política de exclusão de documentos, você pode reduzir o risco de forma proativa, excluindo documentos em um site após um período específico de tempo — por exemplo, você pode excluir documentos nos sites dos usuários do OneDrive for Business cinco anos depois que os documentos foram criados.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-110">With a document deletion policy, you can proactively reduce risk by deleting documents in a site after a specific period of time—for example, you can delete documents in users' OneDrive for Business sites five years after the documents were created.</span></span> 
  
<span data-ttu-id="ebdb4-p104">Depois de criar uma política de exclusão de documentos, você poderá atribuí-la a um modelo de conjunto de sites, de forma que a política esteja disponível para todos os conjuntos de sites criados a partir desse modelo. Você pode ainda atribuir uma política a um conjunto específico de sites, que substitui qualquer política que possa ter sido atribuída ao modelo para esse conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-p104">After you create a document deletion policy, you can assign it to a site collection template, so that the policy is available to all site collections created from that template. You can also assign a policy to a specific a site collection, which overrides any policies that may have been assigned to the template for that site collection.</span></span>
  
![Página inicial do Centro de Políticas de Exclusão de Documentos](../media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="policy-templates"></a><span data-ttu-id="ebdb4-114">Modelos de política</span><span class="sxs-lookup"><span data-stu-id="ebdb4-114">Policy templates</span></span>

<span data-ttu-id="ebdb4-p105">Você pode criar uma política de exclusão do documento do zero ou pode usar uma das políticas de amostra. A Central de Política de Conformidade inclui políticas de amostra que você pode usar como estão, ou como ponto de partida e, em seguida, renomeá-las ou modificá-las.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-p105">You can create a document deletion policy from scratch, or you can use one of the sample policies. The Compliance Policy Center includes sample policies that you can use as is, or you can use them as a starting point and then rename or modify them.</span></span>
  
![Amostra de políticas de exclusão de documentos](../media/IP-Sample-deletion-policies.png)
  
## <a name="examples-of-how-to-use-document-deletion-policies"></a><span data-ttu-id="ebdb4-118">Exemplos</span><span class="sxs-lookup"><span data-stu-id="ebdb4-118">Examples of how to use document deletion policies</span></span>

<span data-ttu-id="ebdb4-119">Um conjunto de sites ou um modelo de conjunto de sites pode conter uma ou mais políticas associadas a ele, e cada uma dessas políticas pode conter uma ou mais regras.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-119">A site collection or a site collection template can have one more policies assigned to it, and each of those policies can have one or more rules.</span></span> <span data-ttu-id="ebdb4-120">No entanto, pode haver apenas uma política ativa por site e pode haver apenas uma regra de exclusão ativa a qualquer momento para as bibliotecas no site.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-120">However, there can be only one policy that's active per site, and there can be only one deletion rule that's active at any time for the libraries within the site.</span></span>
  
![Diagrama mostrando a relação entre as políticas](../media/IP-Two-policies-four-rules.png)
  
<span data-ttu-id="ebdb4-122">Além disso, você pode selecionar uma política como obrigatória ou padrão, e poderá selecionar uma regra de exclusão como uma regra padrão:</span><span class="sxs-lookup"><span data-stu-id="ebdb4-122">In addition, you can select a policy as mandatory or default, and you can select a deletion rule as a default rule:</span></span> 
  
- <span data-ttu-id="ebdb4-123">**Política obrigatória** Quando uma política é marcada como obrigatória, apenas uma política pode ser atribuída ao conjunto de sites ou modelo.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-123">**Mandatory policy**When a policy is marked as mandatory, only one policy can be assigned to the site collection or template.</span></span> <span data-ttu-id="ebdb4-124">A política deverá ser marcada como padrão e será aplicada a todos os sites.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-124">The policy must be marked as default and will be applied to all sites.</span></span> <span data-ttu-id="ebdb4-125">Os proprietários do site não podem recusar a política.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-125">Site owners cannot opt out of the policy.</span></span>
    
- <span data-ttu-id="ebdb4-126">**Política padrão** Quando uma política é definida como padrão, a política é ativa automaticamente em todos os sites aos quais ela é atribuída sem nenhuma ação necessária para o proprietário do site.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-126">**Default policy**When a policy is set as default, the policy is automatically active in all sites that it's assigned to with no action required by site owner.</span></span>
    
- <span data-ttu-id="ebdb4-127">**Regra padrão** Quando uma regra de exclusão é definida como padrão, ela é automaticamente aplicada a todas as bibliotecas nos sites que usam a política.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-127">**Default rule**When a deletion rule is set as default, it is automatically applied to all libraries in the sites that use the policy.</span></span>
    
<span data-ttu-id="ebdb4-128">Os exemplos a seguir explicam quando você pode querer usar uma política obrigatória ou políticas e regras padrão.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-128">The following examples explain when you might want to use a mandatory policy or default policies and rules.</span></span>
  
### <a name="example-1-apply-a-single-policy-with-a-single-rule-to-a-site-collection-template"></a><span data-ttu-id="ebdb4-129">Exemplo 1: aplicar uma política única com uma regra única a um modelo de conjunto de sites</span><span class="sxs-lookup"><span data-stu-id="ebdb4-129">Example 1: Apply a single policy with a single rule to a site collection template</span></span>

<span data-ttu-id="ebdb4-p108">Talvez você queira impor uma política de exclusão de documentos a uma ampla variedade de conteúdos não estruturados, como todos os sites do OneDrive for Business ou todos os sites de equipe. Se quiser garantir que uma única política de exclusão de documentos esteja ativa em todos os sites criados a partir de um modelo de conjunto de sites, você pode:</span><span class="sxs-lookup"><span data-stu-id="ebdb4-p108">You may want to enforce a document deletion policy across a broad range of unstructured content, such as all OneDrive for Business sites or all team sites. If you want to ensure that a single document deletion policy is active in all sites created from a site collection template, you can:</span></span>
  
1. <span data-ttu-id="ebdb4-132">Criar uma única política com uma rúnica regra de exclusão padrão.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-132">Create a single policy with a single default deletion rule.</span></span>
    
2. <span data-ttu-id="ebdb4-133">Definir a política como obrigatória e padrão.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-133">Set the policy as mandatory and default.</span></span>
    
3. <span data-ttu-id="ebdb4-134">Atribuir a política a um modelo de conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-134">Assign the policy to a site collection template.</span></span>
    
<span data-ttu-id="ebdb4-p109">Neste exemplo, a regra de exclusão padrão será aplicada a todas as bibliotecas em todos os conjuntos de sites criados a partir do modelo, e os proprietários do site não poderão recusar a política. Essa é a maneira mais simples de impor de forma ampla e rígida uma política de exclusão de documentos.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-p109">In this example, the default deletion rule will be applied to all libraries in all site collections created from the template, and site owners cannot opt out of the policy. This is the simplest way to broadly and rigidly enforce a document deletion policy.</span></span>
  
![Diagrama mostrando uma única política obrigatória](../media/IP-Example-1-doc-deletion-policies.png)
  
### <a name="example-2-apply-a-single-policy-with-several-rules-to-a-site-collection-template"></a><span data-ttu-id="ebdb4-138">Exemplo 2: aplicar uma única política com várias regras a um modelo de conjunto de sites</span><span class="sxs-lookup"><span data-stu-id="ebdb4-138">Example 2: Apply a single policy with several rules to a site collection template</span></span>

<span data-ttu-id="ebdb4-p110">Os proprietários de site sabem melhor qual é o tipo de conteúdo de seus sites e, portanto, talvez você opte por permitir que os proprietários selecionem a regra de exclusão que se aplique melhor ao site deles. Talvez também queira permitir que os proprietários do site recusem completamente uma política.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-p110">Site owners often know best what type of content their site contains, so you may choose to allow site owners to select the deletion rule that best applies to their site. You may also want to allow site owners to opt out of a policy entirely.</span></span>
  
<span data-ttu-id="ebdb4-p111">Ao mesmo tempo, você ainda pode criar e gerenciar centralmente as políticas. Também é possível selecionar uma política e uma regra como o padrão, de forma que uma política esteja sempre em vigor até o proprietário do site escolha uma diferente ou a recuse. Se desejar fornecer essa flexibilidade a proprietários do site, você pode:</span><span class="sxs-lookup"><span data-stu-id="ebdb4-p111">At the same time, you can still centrally create and manage the policies. You can also select one policy and rule as the default, so that a policy is always in effect until the site owner chooses a different one or opts out. If you want to provide such flexibility to site owners, you can:</span></span>
  
1. <span data-ttu-id="ebdb4-143">Criar uma única política com várias regras de exclusão e definir uma regra como padrão.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-143">Create a single policy with several deletion rules, and set one rule as the default.</span></span>
    
2. <span data-ttu-id="ebdb4-144">Definir a política como a política padrão.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-144">Set the policy as the default policy.</span></span>
    
3. <span data-ttu-id="ebdb4-145">Atribuir a política a um modelo de conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-145">Assign the policy to a site collection template.</span></span>
    
<span data-ttu-id="ebdb4-146">Os proprietários do site podem selecionar uma das regras de exclusão alternativas, recusar a política ou fazer nada e ficarem sujeitos à política e à regra padrão.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-146">Site owners can select one of the alternate deletion rules, opt out of the policy, or do nothing and be subject to the default policy and rule.</span></span>
  
![Diagrama mostrando uma única política com diversas regras](../media/IP-Example-2-doc-deletion-policies.png)
  
### <a name="example-3-apply-several-policies-with-one-or-more-rules-to-a-site-collection"></a><span data-ttu-id="ebdb4-148">Exemplo 3: aplicar várias políticas com uma ou mais regras para um conjunto de sites</span><span class="sxs-lookup"><span data-stu-id="ebdb4-148">Example 3: Apply several policies with one or more rules to a site collection</span></span>

<span data-ttu-id="ebdb4-p112">Este exemplo oferece a flexibilidade máxima a proprietários de sites, porque eles terão várias opções de políticas e, após a seleção de uma política, terão opções de várias regras. Uma política e uma regra estão definidas como padrão, de forma que uma política esteja sempre em vigor até que o proprietário do site escolha uma diferente ou a recuse. Observe que se você não definir uma política e uma regra como o padrão, então nenhuma política ou regra estará ativa para as bibliotecas de documentos no site até que o proprietário do site tome uma ação para selecioná-las e aplicá-las.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-p112">This example provides the maximum flexibility to site owners because they can choose from several policies, and after selecting a policy they can often choose from several rules. One policy and rule are set as default, so that a policy is always in effect until the site owner chooses a different one or opts out. Note that if you do not set a policy and rule as the default, then no policies or rules will be active for the document libraries in the site until the site owner takes action to select and apply them.</span></span>
  
<span data-ttu-id="ebdb4-p113">Ao contrário dos dois exemplos anteriores, essas políticas são atribuídas a um conjunto de sites específico e não ao modelo de conjunto de sites. Isso significa que as políticas poderão ser ajustadas mais especificamente para o conteúdo de um conjunto de sites específico.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-p113">Unlike the previous two examples, these policies are assigned to a specific site collection — not the site collection template. This means the policies can be more specifically tailored for the content in a specific site collection.</span></span>
  
<span data-ttu-id="ebdb4-p114">Regras e políticas são herdadas. Os proprietários do site podem selecionar uma política e uma regra para seu site, e todos os subsites herdarão a política do site principal. Entretanto, um proprietário de um subsite poderá interromper a herança selecionando uma política e uma regra diferentes que, por sua vez, será aplicada a todos os subsites até a herança ser interrompida novamente.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-p114">Policies and rules are inherited. Site owners can select a policy and rule for their site, and all subsites inherit the policy from the parent. However, an owner of a subsite can break inheritance by selecting a different policy and rule, which in turn applies to all subsites until inheritance is broken again.</span></span>
  
<span data-ttu-id="ebdb4-156">Para configurar este cenário, você pode:</span><span class="sxs-lookup"><span data-stu-id="ebdb4-156">To set up this scenario, you can:</span></span>
  
1. <span data-ttu-id="ebdb4-157">Criar várias políticas que contenham uma ou mais regras cada uma.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-157">Create several policies that each contains one or more rules.</span></span>
    
2. <span data-ttu-id="ebdb4-158">Definir uma política e uma regra como o padrão.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-158">Set a policy and rule as the default.</span></span>
    
3. <span data-ttu-id="ebdb4-159">Atribuir as políticas a um conjunto de sites específico.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-159">Assign the policies to a specific site collection.</span></span>
    
<span data-ttu-id="ebdb4-160">Além disso, as políticas e regras são ajustadas a um conjunto de sites específico, onde proprietários do site podem interromper a herança selecionando a política e a regra que melhor se aplique ao site.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-160">In addition, the policies and rules are tailored to a specific site collection, where site owners can break inheritance by selecting the policy and rule that best applies to their site.</span></span>
  
![Diagrama mostrando diversas políticas e regras](../media/IP-Example-3-doc-deletion-policies.png)
  
## <a name="create-a-document-deletion-policy"></a><span data-ttu-id="ebdb4-162">Criar uma política de exclusão de documentos</span><span class="sxs-lookup"><span data-stu-id="ebdb4-162">Create a document deletion policy</span></span>

1. <span data-ttu-id="ebdb4-163">No centro de conformidade &amp; do Office 365Security, navegue até **retenção**de **Gerenciamento** \> de dados.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-163">In the Office 365Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="ebdb4-164">Em **excluir**, clique em **gerenciar políticas de exclusão de documentos do SharePoint Online e do onedrive for Business**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-164">Under **Delete**, click **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="ebdb4-165">O Centro de Política de Exclusão de Documentos é exibido em uma nova guia do navegador.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-165">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
    <span data-ttu-id="ebdb4-166">Na primeira vez que você navegar do centro &amp; de conformidade de segurança para a central de políticas de exclusão de documentos, a central de políticas será criada automaticamente para você.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-166">The first time you navigate from the Security &amp; Compliance Center to the Document Deletion Policy Center, the policy center is automatically created for you.</span></span> <span data-ttu-id="ebdb4-167">Como alternativa, você pode criar manualmente a central de políticas [criando o conjunto de sites](https://go.microsoft.com/fwlink/p/?LinkID=404342) e escolhendo **central de políticas de conformidade** na guia **empresa** .</span><span class="sxs-lookup"><span data-stu-id="ebdb4-167">Alternatively, you can manually create the policy center by [creating the site collection](https://go.microsoft.com/fwlink/p/?LinkID=404342) and choosing **Compliance Policy Center** on the **Enterprise** tab.</span></span> 
    
2. <span data-ttu-id="ebdb4-168">Escolha **políticas de exclusão**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-168">Choose **Deletion Policies**.</span></span>
    
    ![Opção Políticas de Exclusão](../media/IP-Deletion-Policies-option.png)
  
3. <span data-ttu-id="ebdb4-170">Escolha **novo item**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-170">Choose **new item**.</span></span>
    
4. <span data-ttu-id="ebdb4-p117">Insira um nome de política e uma descrição. Os proprietários do site podem estar selecionando uma política para o site deles com base nesse nome e descrição, portanto inclua informações suficientes para que eles escolham a política correta.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-p117">Enter a policy name and description. Site owners may be selecting a policy for their site based on this name and description, so include enough information for them to choose the correct policy.</span></span>
    
5. <span data-ttu-id="ebdb4-173">Para criar uma regra, escolha **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-173">To create a rule, choose **New**.</span></span>
    
6. <span data-ttu-id="ebdb4-174">Insira um nome e escolha estas opções:</span><span class="sxs-lookup"><span data-stu-id="ebdb4-174">Enter a name and choose the following options:</span></span>
    
  - <span data-ttu-id="ebdb4-175">Escolha se a regra excluirá permanentemente documentos ou os excluirá para a Lixeira.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-175">Choose whether the rule will permanently delete documents or delete them to the Recycle Bin.</span></span> <span data-ttu-id="ebdb4-176">A Lixeira oferece um segundo nível de segurança antes que um item seja permanentemente excluído de um site.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-176">The Recycle Bin provides a second-stage safety net before an item is permanently deleted from a site.</span></span> <span data-ttu-id="ebdb4-177">Para obter mais informações sobre a lixeira, confira [esvaziar a lixeira ou restaurar seus arquivos](https://go.microsoft.com/fwlink/p/?LinkID=404348).</span><span class="sxs-lookup"><span data-stu-id="ebdb4-177">For more information about the Recycle Bin, see [Empty the Recycle Bin or restore your files](https://go.microsoft.com/fwlink/p/?LinkID=404348).</span></span>
    
  - <span data-ttu-id="ebdb4-178">Escolha se a data de exclusão será calculada a partir da data em que um documento foi criado ou modificado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-178">Choose whether the deletion date is calculated from the date when a document was created or last modified.</span></span>
    
  - <span data-ttu-id="ebdb4-179">Insira um número de dias, meses ou anos como o período após o qual um documento será excluído.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-179">Enter a number of days, months, or years as the time period after which a document will be deleted.</span></span>
    
  - <span data-ttu-id="ebdb4-p119">Escolha se a regra será uma regra padrão. A primeira regra criada será automaticamente definida como a regra padrão. Uma regra padrão será automaticamente aplicada a todas as bibliotecas nos sites que usam a política.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-p119">Choose whether the rule is a default rule. The first rule that you create is automatically set as the default rule. A default rule is automatically applied to all libraries in the sites that use the policy.</span></span>
    
![Nova página de regra de exclusão](../media/IP-New-deletion-rule.png)
  
7. <span data-ttu-id="ebdb4-184">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-184">Click **Save**.</span></span>
    
8. <span data-ttu-id="ebdb4-p120">Crie regras adicionais se quiser que proprietários do site sejam capazes de escolher regras diferentes para aplicarem ao site deles. A regra padrão, se houver, será aplicada se o proprietário do site não executar nenhuma ação.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-p120">Create additional rules if you want site owners to be able to choose different rules to apply to their site. The default rule, if any, will be applied if the site owner takes no action.</span></span>
    
9. <span data-ttu-id="ebdb4-187">Para remover uma regra de uma política, selecione a regra, clique em **excluir**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-187">To remove a rule from a policy, select the rule, click **Delete**, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ebdb4-188">Se você excluir uma regra e a política não contiver uma regra padrão, nenhuma regra será aplicada a essa política, em outras palavras, nenhum documento será excluído.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-188">If you delete a rule, and the policy does not contain a default rule, then no rule will be in effect for that policy—in other words, no documents will be deleted.</span></span> 
  
![Confirmar remoção de regra de mensagem de política](../media/IP-Remove-rule-from-policy-message.png)
  
## <a name="assign-the-document-deletion-policy-to-a-site-collection-template"></a><span data-ttu-id="ebdb4-190">Atribuir a política de exclusão de documentos a um modelo de conjunto de sites</span><span class="sxs-lookup"><span data-stu-id="ebdb4-190">Assign the document deletion policy to a site collection template</span></span>

<span data-ttu-id="ebdb4-191">Atribuindo uma política a um modelo de conjunto de sites, você disponibiliza a política para todos os conjuntos de sites criados a partir desse modelo, incluindo conjuntos de sites existentes e conjuntos de sites criados no futuro.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-191">By assigning a policy to a site collection template, you make the policy available to all site collections created from that template, including both existing site collections and site collections created in the future.</span></span>
  
<span data-ttu-id="ebdb4-192">É importante entender que o período de tempo especificado para uma política de exclusão de documentos significa o tempo desde que o documento foi criado ou modificado, não o tempo desde que a política foi atribuída.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-192">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned.</span></span> <span data-ttu-id="ebdb4-193">Quando você atribui uma política pela primeira vez, todos os documentos no site são avaliados, e são excluídos se atenderem aos critérios.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-193">When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted.</span></span> <span data-ttu-id="ebdb4-194">Isto se aplica a todos os documentos existentes, e não somente aos novos documentos criados desde que a política foi atribuída.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-194">This applies to all existing documents, not just new documents created since the policy was assigned.</span></span>
  
1. <span data-ttu-id="ebdb4-195">No centro de &amp; conformidade de segurança, navegue até **retenção**de **Gerenciamento** \> de dados.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-195">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="ebdb4-196">Em **excluir**, clique em **gerenciar políticas de exclusão de documentos do SharePoint Online e do onedrive for Business**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-196">Under **Delete**, click **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="ebdb4-197">O Centro de Política de Exclusão de Documento é exibido em uma nova guia do navegador.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-197">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="ebdb4-198">Escolha **Atribuições de políticas para modelos**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-198">Choose **Policy Assignments for Templates**.</span></span>
    
    ![Atribuição de Políticas para opção de Modelos](../media/IP-Policy-Assignments-for-Templates-option.png)
  
3. <span data-ttu-id="ebdb4-200">Escolha **novo item**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-200">Choose **new item**.</span></span>
    
4. <span data-ttu-id="ebdb4-201">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="ebdb4-201">Do one of the following:</span></span>
    
  - <span data-ttu-id="ebdb4-202">Para atribuir a política a um modelo de conjunto de sites, como o modelo Site da Equipe, selecione **Atribuir ao modelo de conjunto de sites** e escolha o modelo de conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-202">To assign the policy to a site collection template such as the Team Site template, select **Assign to site collection template**, and then select the site collection template.</span></span>
    
  - <span data-ttu-id="ebdb4-203">Para atribuir a política à unidade de negócios de um dos usuários, escolha **atribuir ao modelo do onedrive for Business**, realçado abaixo.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-203">To assign the policy to users' One Drive for Business, choose **Assign to OneDrive for Business Template**, highlighted below.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ebdb4-204">Quando você atribuir uma política a um modelo de conjunto de sites, essa política estará disponível a conjuntos de sites existentes criados a partir desse modelo e para conjuntos de sites criados no futuro.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-204">When you assign a policy to a site collection template, that policy will be available both to existing site collections created from that template and to site collections created in the future.</span></span> 
  
![Escolha uma página modelo exibindo a opção do OneDrive](../media/IP-Choose-a-template.png)
  
5. <span data-ttu-id="ebdb4-206">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-206">Click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ebdb4-207">Cada modelo pode ter apenas um conjunto de políticas atribuído a ele.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-207">Each template can have only one set of policies assigned to it.</span></span> <span data-ttu-id="ebdb4-208">Se você vir um erro dizendo que este modelo já tem políticas atribuídas a ele, escolha **Cancelar** \> **atribuir ao conjunto de sites** no painel \> de navegação à esquerda selecione um conjunto de sites para exibir e gerenciar o conjunto de políticas que já estão atribuídas.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-208">If you see an error saying that this template already has policies assigned to it, choose **Cancel** \> **Assign to Site Collection** in the left navigation \> select a site collection to view and manage the set of policies that are already assigned.</span></span> 
  
6. <span data-ttu-id="ebdb4-209">Escolha **Gerenciar políticas atribuídas**, selecione as políticas que deseja atribuir e escolha se uma política será a padrão.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-209">Choose **Manage Assigned Policies**, select the policies that you want to assign, and then choose whether one policy is the default policy.</span></span> <span data-ttu-id="ebdb4-210">Quando você definir uma política padrão, todos os sites atribuídos automaticamente à política terão a política ativa sem que seja exigida uma ação do proprietário do site.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-210">When you set a default policy, all sites assigned to the policy automatically have the policy active with no action required by site owner.</span></span>
    
    ![Adicione e gerencie páginas de políticas](../media/IP-Add-and-manage-policies-page.png)
  
7. <span data-ttu-id="ebdb4-212">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-212">Click **Save**.</span></span>
    
8. <span data-ttu-id="ebdb4-p125">Se quiser impor a política a todos os sites sem permitir que os proprietários do site a recusem, escolha **Marcar política como obrigatória**. Quando uma política for marcada como obrigatória, somente uma única política poderá ser atribuída ao modelo de conjunto de sites. A política também deve ser marcada como padrão.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-p125">If you want to enforce the policy on all sites without allowing site owners to opt out, choose **Mark Policy as Mandatory**. When you make a policy mandatory, only that single policy can be assigned to the site collection template. The policy must also be marked as default.</span></span>
    
    <span data-ttu-id="ebdb4-216">Se essa opção estiver esmaecida, escolha **Gerenciar políticas atribuídas** e verifique se pelo menos uma política foi atribuída e definida como padrão.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-216">If this option is grayed out, choose **Manage Assigned Policies** and make sure that at least one policy is assigned and set as default.</span></span> 
    
9. <span data-ttu-id="ebdb4-217">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-217">Click **Save**.</span></span>
    
## <a name="assign-the-document-deletion-policy-to-a-site-collection"></a><span data-ttu-id="ebdb4-218">Atribuir a política de exclusão de documentos a um conjunto de sites</span><span class="sxs-lookup"><span data-stu-id="ebdb4-218">Assign the document deletion policy to a site collection</span></span>

<span data-ttu-id="ebdb4-p126">Ao atribuir uma política a um conjunto de sites específico, você disponibilizará a política somente àquele conjunto de sites específico. Isso significa que você poderá ajustar melhor as políticas ao conteúdo no conjunto de sites. Além disso, políticas atribuídas a um conjunto de sites específico substituirão todas as políticas atribuídas ao modelo para aquele conjunto de sites. Por exemplo, uma política atribuída ao conjunto de sites Departamento de Vendas (criado a partir do modelo Site da Equipe) substituirá qualquer política atribuída ao modelo Site da Equipe.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-p126">By assigning a policy to a specific site collection, you make the policy available only to that specific site collection. This means you can tailor policies more closely to the content in the site collection. Also, policies assigned to a specific site collection will override any policies that are assigned to the template for that site collection. For example, a policy assigned to the Sales Department site collection (created from the Team Site template) will override any policies assigned to the Team Site template.</span></span>
  
<span data-ttu-id="ebdb4-223">É importante entender que o período de tempo especificado para uma política de exclusão de documentos significa o tempo desde que o documento foi criado ou modificado, não o tempo desde que a política foi atribuída.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-223">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned.</span></span> <span data-ttu-id="ebdb4-224">Quando você atribui uma política pela primeira vez, todos os documentos no site são avaliados, e são excluídos se atenderem aos critérios.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-224">When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted.</span></span> <span data-ttu-id="ebdb4-225">Isto se aplica a todos os documentos existentes, e não somente aos novos documentos criados desde que a política foi atribuída.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-225">This applies to all existing documents, not just new documents created since the policy was assigned.</span></span>
  
1. <span data-ttu-id="ebdb4-226">No centro de &amp; conformidade de segurança, navegue até **retenção**de **Gerenciamento** \> de dados.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-226">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="ebdb4-227">Em **excluir**, escolha **gerenciar políticas de exclusão de documentos do SharePoint Online e do onedrive for Business**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-227">Under **Delete**, choose **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="ebdb4-228">O Centro de Política de Exclusão de Documentos é exibido em uma nova guia do navegador.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-228">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="ebdb4-229">Escolha **Atribuições de políticas para conjuntos de sites**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-229">Choose **Policy Assignments for Site Collections**.</span></span>
    
    ![Atribuições de Políticas para opções de Conjuntos de Sites](../media/IP-Policy-Assignments-for-Site-Collections-option.png)
  
3. <span data-ttu-id="ebdb4-231">Escolha **novo item**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-231">Choose **new item**.</span></span>
    
4. <span data-ttu-id="ebdb4-232">Escolha **escolher um conjunto de sites**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-232">Choose **Choose a site collection**.</span></span> <span data-ttu-id="ebdb4-233">Procure o conjunto de sites por nome ou URL, selecione o conjunto de sites e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-233">Search for the site collection by name or URL, select the site collection and click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ebdb4-234">Cada conjunto de sites pode ter apenas um conjunto de políticas atribuído a ele.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-234">Each site collection can have only one set of policies assigned to it.</span></span> <span data-ttu-id="ebdb4-235">Se você vir um erro dizendo que este conjunto de sites já tem políticas atribuídas a ele, escolha **Cancelar** \> **atribuir ao conjunto de sites** e selecione um conjunto de sites para exibir e gerenciar o conjunto de políticas que já estão atribuídas.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-235">If you see an error saying that this site collection already has policies assigned to it, choose **Cancel** \> **Assign to Site Collection** and select a site collection to view and manage the set of policies that are already assigned.</span></span> 
  
![Escolha uma página de conjuntos de sites](../media/IP-Choose-a-site-collection-page.png)
  
5. <span data-ttu-id="ebdb4-237">Escolha **Gerenciar políticas atribuídas**, selecione as políticas que deseja atribuir e escolha se uma política será a padrão.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-237">Choose **Manage Assigned Policies**, select the policies that you want to assign, and then choose whether one policy is the default policy.</span></span> <span data-ttu-id="ebdb4-238">Quando você definir uma política padrão, todos os sites atribuídos automaticamente à política terão a política ativa sem que seja exigida uma ação do proprietário do site.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-238">When you set a default policy, all sites assigned to the policy automatically have the policy active with no action required by site owner.</span></span>
    
    ![Adicione e gerencie páginas de políticas](../media/IP-Add-and-manage-policies-page.png)
  
6. <span data-ttu-id="ebdb4-240">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-240">Click **Save**.</span></span>
    
7. <span data-ttu-id="ebdb4-p132">Se quiser impor a política a todos os sites sem permitir que os proprietários do site a recusem, escolha **Marcar política como obrigatória**. Quando uma política for marcada como obrigatória, somente uma única política poderá ser atribuída ao conjunto de sites. A política também deve ser marcada como padrão.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-p132">If you want to enforce the policy on all sites without allowing site owners to opt out, choose **Mark Policy as Mandatory**. When you make a policy mandatory, only that single policy can be assigned to the site collection. The policy must also be marked as default.</span></span>
    
    <span data-ttu-id="ebdb4-244">Se essa opção estiver esmaecida, escolha **Gerenciar políticas atribuídas** e verifique se pelo menos uma política foi atribuída e definida como padrão.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-244">If this option is grayed out, choose **Manage Assigned Policies** and make sure that at least one policy is assigned and set as default.</span></span> 
    
8. <span data-ttu-id="ebdb4-245">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-245">Click **Save**.</span></span>
    
## <a name="delete-a-policy-assignment"></a><span data-ttu-id="ebdb4-246">Excluir uma atribuição de política</span><span class="sxs-lookup"><span data-stu-id="ebdb4-246">Delete a policy assignment</span></span>

<span data-ttu-id="ebdb4-247">Quando você excluir uma atribuição, as políticas atribuídas não se aplicarão mais a qualquer site do conjunto de sites ou do modelo de conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-247">When you delete an assignment, the assigned policies will no longer apply to any sites in the site collection or site collection template.</span></span>
  
1. <span data-ttu-id="ebdb4-248">No centro de &amp; conformidade de segurança, navegue até **retenção**de **Gerenciamento** \> de dados.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-248">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**.</span></span> <span data-ttu-id="ebdb4-249">Em **excluir**, escolha **gerenciar políticas de exclusão de documentos do SharePoint Online e do onedrive for Business**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-249">Under **Delete**, choose **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="ebdb4-250">O Centro de Política de Exclusão de Documento é exibido em uma nova guia do navegador.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-250">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="ebdb4-251">Escolha uma destas opções **Atribuições de políticas para modelos** ou **Atribuições de políticas para conjuntos de sites**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-251">Choose either **Policy Assignments for Templates** or **Policy Assignments for Site Collections**.</span></span>
    
3. <span data-ttu-id="ebdb4-252">Selecione o item de atribuição e clique em **Excluir item**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-252">Select the assignment item and click **Delete Item**.</span></span>
    
    ![Exclua o comando Item para atribuição de política](../media/IP-Delete-policy-assignment.png)
  
## <a name="delete-a-policy"></a><span data-ttu-id="ebdb4-254">Excluir uma política</span><span class="sxs-lookup"><span data-stu-id="ebdb4-254">Delete a policy</span></span>

<span data-ttu-id="ebdb4-255">Não é possível excluir uma política que está sendo usada.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-255">You can't delete a policy that's in use.</span></span> <span data-ttu-id="ebdb4-256">Antes de poder excluir uma política, primeiro é necessário excluir todas as atribuições de conjuntos de sites e modelos de conjunto de sites que incluam essa política: consulte a seção anterior.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-256">Before you can delete a policy, you first need to delete all assignments to site collections and site collection templates that include that policy—see the previous section.</span></span>
  
1. <span data-ttu-id="ebdb4-257">&amp; No centro \> de conformidade de segurança, escolha **retenção** de gerenciamento \> \> de **dados** , no painel de navegação à esquerda, em **excluir** \> **gerenciar políticas de exclusão de documentos para o SharePoint Online e o onedrive for Business**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-257">In the Security &amp; Compliance Center \> choose **Data management** \> **Retention** in the left navigation \> under **Delete** \> **Manage document deletion policies for SharePoint Online and OneDrive for Business**.</span></span> <span data-ttu-id="ebdb4-258">O Centro de Política de Exclusão de Documentos é exibido em uma nova guia do navegador.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-258">The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="ebdb4-259">Escolha \* \* políticas de exclusão \* \*.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-259">Choose \*\* Deletion Policies \*\*.</span></span>
    
    ![Opção Políticas de Exclusão](../media/IP-Deletion-Policies-option.png)
  
3. <span data-ttu-id="ebdb4-261">Selecione a política.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-261">Select the policy.</span></span>
    
4. <span data-ttu-id="ebdb4-262">Na guia \> **Items** \> itens da faixa de opções, **remova a política**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-262">On the Ribbon \> **Items** tab \> **Remove Policy**.</span></span>
    
    ![Botão Remover Política na Faixa de Opções](../media/IP-Remove-Policy-button-on-Ribbon.png)
  
5. <span data-ttu-id="ebdb4-264">Se a política estiver em uso, será perguntado se você deseja remover a política de todos os conjuntos de sites em que ele está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-264">If the policy is in use, you'll be asked if you want to remove the policy from all of the site collections where it's being used.</span></span> <span data-ttu-id="ebdb4-265">Se tiver certeza, escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="ebdb4-265">If you're sure, choose **OK**.</span></span>
    
    ![Exclua a mensagem de confirmação de política](../media/IP-Delete-policy-confirmation.png)
  
## <a name="see-also"></a><span data-ttu-id="ebdb4-267">Confira também</span><span class="sxs-lookup"><span data-stu-id="ebdb4-267">See also</span></span>

[<span data-ttu-id="ebdb4-268">Visão geral das políticas de exclusão de documento</span><span class="sxs-lookup"><span data-stu-id="ebdb4-268">Overview of document deletion policies</span></span>](document-deletion-policies.md)

[<span data-ttu-id="ebdb4-269">Aplicar ou remover uma política de exclusão de documentos de um site</span><span class="sxs-lookup"><span data-stu-id="ebdb4-269">Apply or remove a document deletion policy for a site</span></span>](apply-or-remove-a-document-deletion-policy-for-a-site.md)
 

