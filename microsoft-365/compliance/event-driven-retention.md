---
title: Iniciar a retenção quando um evento ocorrer
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
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
ms.custom:
- seo-marvel-apr2020
- seo-marvel-may2020
- seo-marvel-jun2020
description: Normalmente parte de uma solução de gerenciamento de registros, em que você pode configurar um rótulo de retenção para iniciar o período de retenção com base em um evento identificado.
ms.openlocfilehash: 7286e65be2313f5716bfc59399c1755cadb9f6d6
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778521"
---
# <a name="start-retention-when-an-event-occurs"></a><span data-ttu-id="114a3-103">Iniciar a retenção quando um evento ocorrer</span><span class="sxs-lookup"><span data-stu-id="114a3-103">Start retention when an event occurs</span></span>

><span data-ttu-id="114a3-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="114a3-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="114a3-p101">Quando você retém o conteúdo, o período de retenção normalmente é baseado na idade desse conteúdo. Por exemplo, você pode reter documentos por sete anos após terem sido criados e excluí-los após esse prazo. Porém, se você configurar os [rótulos de retenção](labels.md), poderá também basear um período de retenção no momento em que um tipo específico de evento ocorre. O evento desencadeia o início do período de retenção e as ações de retenção do rótulo passam a ser aplicadas a todo o conteúdo que tiver esse rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="114a3-p101">When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](labels.md), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="114a3-109">Exemplos de uso da retenção impulsionada por eventos:</span><span class="sxs-lookup"><span data-stu-id="114a3-109">Examples for using event-driven retention:</span></span>
  
- <span data-ttu-id="114a3-110">**Funcionários que estão saindo da organização** Suponha que os registros de funcionários devam ser retidos por 10 anos após a data em que o funcionário saiu da organização.</span><span class="sxs-lookup"><span data-stu-id="114a3-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="114a3-111">Decorrido o prazo de 10 anos, todos os documentos relacionados à contratação, desempenho e demissão desse funcionário precisam ser descartados.</span><span class="sxs-lookup"><span data-stu-id="114a3-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="114a3-112">O evento que desencadeia o período de retenção de 10 anos é a saída do funcionário da organização.</span><span class="sxs-lookup"><span data-stu-id="114a3-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="114a3-113">**Vencimento de um contrato** Suponha que todos os registros relativos a contratos devam ser retidos por 10 anos após a data de vencimento do contrato.</span><span class="sxs-lookup"><span data-stu-id="114a3-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="114a3-114">O evento que desencadeia o período de retenção de cinco anos é o vencimento do contrato.</span><span class="sxs-lookup"><span data-stu-id="114a3-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="114a3-p104">**Vida útil do produto** Talvez sua organização tenha exigências de retenção relacionadas à última data de produção de produtos para determinados conteúdos, como especificações técnicas. Nesse caso, a última data de produção é o evento que dispara o período de retenção.</span><span class="sxs-lookup"><span data-stu-id="114a3-p104">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="114a3-p105">Normalmente, a retenção controlada por eventos é usada como parte de um processo de gerenciamento de registros. Isso significa que:</span><span class="sxs-lookup"><span data-stu-id="114a3-p105">Event-driven retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="114a3-119">Os rótulos com base em eventos geralmente classificam o conteúdo como um registro, como parte de uma solução de gerenciamento de registros.</span><span class="sxs-lookup"><span data-stu-id="114a3-119">Labels based on events also usually classify content as a record, as a part of a records management solution.</span></span> <span data-ttu-id="114a3-120">Para obter mais informações, confira o artigo [Saiba mais sobre registros](records-management.md).</span><span class="sxs-lookup"><span data-stu-id="114a3-120">For more information, see [Learn about records management](records-management.md).</span></span>

- <span data-ttu-id="114a3-121">Um documento classificado como registro cujo evento desencadeador ainda não ocorreu é retido por prazo indeterminado (os registros não podem ser excluídos permanentemente), até que um evento desencadeie seu período de retenção.</span><span class="sxs-lookup"><span data-stu-id="114a3-121">A document that's been classified as a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="114a3-122">Os rótulos de retenção baseados em eventos costumam desencadear uma análise de descarte no final do período de retenção, de modo que um gerente de registros possa analisar e descartar o conteúdo manualmente.</span><span class="sxs-lookup"><span data-stu-id="114a3-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="114a3-123">Para obter mais informações, confira o artigo [Disposição e descarte de conteúdo](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="114a3-123">For more information, see [Disposition of content](disposition.md).</span></span>
    

<span data-ttu-id="114a3-124">Um rótulo com base em um evento tem os mesmos recursos que qualquer rótulo no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="114a3-124">A label based on an event has the same capabilities as any retention label in Microsoft  365.</span></span> <span data-ttu-id="114a3-125">Para obter mais informações, consulte [Saiba mais sobre políticas e rótulos de retenção](retention.md).</span><span class="sxs-lookup"><span data-stu-id="114a3-125">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="114a3-126">Compreender a relação entre tipos de eventos, rótulos, eventos e IDs de ativos</span><span class="sxs-lookup"><span data-stu-id="114a3-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="114a3-127">Para usar a retenção controlada por eventos com êxito, é importante compreender a relação entre tipos de evento, rótulos, eventos e IDs de ativo, conforme ilustrado nos diagramas e explicações a seguir:</span><span class="sxs-lookup"><span data-stu-id="114a3-127">To successfully use event-driven retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![Diagrama de tipo de evento, rótulos, eventos e IDs de ativos](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Diagrama de tipo de evento, rótulos, eventos e IDs de ativos](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="114a3-130">Você cria rótulos de retenção para diferentes tipos de conteúdo e depois os associa a um tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="114a3-130">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="114a3-131">Por exemplo, os rótulos de retenção para diferentes tipos de arquivos e registros de produtos são associados a um tipo de evento denominado Vida útil do produto, pois esses registros devem ser retidos por 10 anos a partir do momento em que o produto atinge o final de sua vida útil.</span><span class="sxs-lookup"><span data-stu-id="114a3-131">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="114a3-132">Os usuários (normalmente gerenciadores de registros) aplicam esses rótulos de retenção ao conteúdo e (para documentos do SharePoint e OneDrive) inserem uma ID de ativo para cada item.</span><span class="sxs-lookup"><span data-stu-id="114a3-132">Users (typically records managers) apply those retention labels to content and (for SharePoint and OneDrive documents) enter an asset ID for each item.</span></span> <span data-ttu-id="114a3-133">Nesse exemplo, a ID do ativo é um nome ou código de produto usado pela organização.</span><span class="sxs-lookup"><span data-stu-id="114a3-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="114a3-134">Assim, os registros de cada produto recebem um rótulo de retenção e cada registro tem uma propriedade que contém uma ID de ativo.</span><span class="sxs-lookup"><span data-stu-id="114a3-134">Thus, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="114a3-135">O diagrama representa **todo o conteúdo** de todos os registros de produtos em uma organização e cada item tem a ID do ativo do produto cujo registro ele pertence.</span><span class="sxs-lookup"><span data-stu-id="114a3-135">The diagram represents **all of the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="114a3-p111">A Vida Útil do Produto é o tipo de evento; um produto específico chegando ao fim de sua vida útil é um evento. Quando ocorre um evento desse tipo — nesse caso, quando um produto chega ao final de sua vida útil —, você cria um evento que especifica o seguinte:</span><span class="sxs-lookup"><span data-stu-id="114a3-p111">Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs—in this case, when a product reaches its end of life—you create an event that specifies:</span></span>
    
   - <span data-ttu-id="114a3-138">Uma ID de ativo (para documentos do SharePoint e do OneDrive)</span><span class="sxs-lookup"><span data-stu-id="114a3-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
   - <span data-ttu-id="114a3-p112">Palavras-chave (para itens do Exchange). Neste exemplo, a organização usa um código de produto em mensagens que contêm registros de produto, assim, a palavra-chave para itens do Exchange é igual à ID de ativos de documentos do SharePoint e do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="114a3-p112">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
   - <span data-ttu-id="114a3-p113">A data de ocorrência do evento. Essa data é utilizada como o início do período de retenção. Essa data pode ser a atual, do passado ou futura.</span><span class="sxs-lookup"><span data-stu-id="114a3-p113">The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.</span></span>

4. <span data-ttu-id="114a3-144">Depois de criar um evento, a data dele é sincronizada com todo o conteúdo que tem um rótulo desse tipo de evento e que contém a ID ou palavra-chave especificada do ativo.</span><span class="sxs-lookup"><span data-stu-id="114a3-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="114a3-145">Como ocorre com qualquer rótulo de retenção, essa sincronização poderá demorar até sete dias.</span><span class="sxs-lookup"><span data-stu-id="114a3-145">Like any retention label, this synchronization can take up to seven days.</span></span> <span data-ttu-id="114a3-146">No diagrama anterior, todos os itens marcados com um círculo vermelho têm o período de retenção desencadeado por esse evento.</span><span class="sxs-lookup"><span data-stu-id="114a3-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="114a3-147">Em outras palavras, quando esse produto chega ao fim da vida útil, esse evento ativa o período de retenção dos registros desse produto.</span><span class="sxs-lookup"><span data-stu-id="114a3-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>

<span data-ttu-id="114a3-148">É importante entender que se você não especificar uma ID de ativos ou palavras-chave para um evento, **todo o conteúdo** com um rótulo desse tipo de evento terá um período de retenção desencadeado pelo evento.</span><span class="sxs-lookup"><span data-stu-id="114a3-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="114a3-149">Isso significa que, no diagrama anterior, todo o conteúdo começaria a ser retido.</span><span class="sxs-lookup"><span data-stu-id="114a3-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="114a3-150">Isso pode não ser o que você pretende.</span><span class="sxs-lookup"><span data-stu-id="114a3-150">This might not be what you intend.</span></span> 

<span data-ttu-id="114a3-151">Por fim, lembre-se de que cada rótulo de retenção tem suas próprias configurações de retenção.</span><span class="sxs-lookup"><span data-stu-id="114a3-151">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="114a3-152">Neste exemplo, todos eles especificam dez anos, mas é possível que um evento ative rótulos de retenção onde cada rótulo tem um período de retenção diferente.</span><span class="sxs-lookup"><span data-stu-id="114a3-152">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="114a3-153">Como configurar a retenção controlada por eventos</span><span class="sxs-lookup"><span data-stu-id="114a3-153">How to set up event-driven retention</span></span>

<span data-ttu-id="114a3-154">Aqui está o fluxo de trabalho de alto nível para a retenção controlada por eventos:</span><span class="sxs-lookup"><span data-stu-id="114a3-154">High-level workflow for event-driven retention:</span></span>
  
![Diagrama de fluxo de trabalho para configurar a retenção controlada por eventos](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="114a3-156">Confira [Usar rótulos de retenção para gerenciar o ciclo de vida de documentos armazenados no SharePoint](auto-apply-retention-labels-scenario.md) para um cenário detalhado sobre como usar as propriedades gerenciadas no SharePoint para aplicar automaticamente os rótulos de retenção e implementar a retenção voltada para o evento.</span><span class="sxs-lookup"><span data-stu-id="114a3-156">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="114a3-157">Etapa 1: criar um rótulo cujo período de retenção seja baseado em um evento</span><span class="sxs-lookup"><span data-stu-id="114a3-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="114a3-158">Para criar e configurar seu rótulo de retenção, use as instruções do artigo [Criar e configurar os rótulos de retenção](create-retention-labels.md#create-and-configure-retention-labels). Ao ativar a retenção, escolha a opção de reter ou excluir o conteúdo com base em um evento.</span><span class="sxs-lookup"><span data-stu-id="114a3-158">To create and configure your retention label, use the instructions from [Create and configure retention labels](create-retention-labels.md#create-and-configure-retention-labels) and when you turn on retention, choose the option to retain or delete the content based on an event.</span></span> <span data-ttu-id="114a3-159">Essa opção significa que as configurações de retenção somente entrarão em vigor quando você chegar à Etapa 5, em que um evento será criado na página **Eventos**.</span><span class="sxs-lookup"><span data-stu-id="114a3-159">This setting means that the retention settings won't go into effect until Step 5, when you create an event on the **Events** page.</span></span> 
  
<span data-ttu-id="114a3-160">De modo geral, a retenção impulsionada por eventos é utilizada para conteúdos que são classificados como registros. Aproveite essa oportunidade e verifique se você também precisa selecionar a opção de marcar um conteúdo como um registro.</span><span class="sxs-lookup"><span data-stu-id="114a3-160">Event-driven retention is typically used for content that's classified as a record, so this is a good time to check whether you also need to select the option that marks content as a record.</span></span>
  
<span data-ttu-id="114a3-161">A retenção impulsionada por eventos requer configurações de retenção que:</span><span class="sxs-lookup"><span data-stu-id="114a3-161">Event-driven retention requires retention settings that:</span></span>
  
- <span data-ttu-id="114a3-162">Retêm o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="114a3-162">Retain the content.</span></span>
    
- <span data-ttu-id="114a3-163">Excluem o conteúdo automaticamente, ou acionam uma revisão de disposição ao final do período de retenção.</span><span class="sxs-lookup"><span data-stu-id="114a3-163">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
    
![Opção para basear um rótulo em um evento](../media/a4902281-5196-4194-9737-f30231d95861.png)

### <a name="step-2-choose-an-event-type-for-that-label"></a><span data-ttu-id="114a3-165">Etapa 2: Escolher um tipo de evento para esse rótulo</span><span class="sxs-lookup"><span data-stu-id="114a3-165">Step 2: Choose an event type for that label</span></span>

<span data-ttu-id="114a3-166">Nas configurações do rótulo, depois de escolher a opção de basear o rótulo em um **evento** você verá a opção **Escolher um tipo de evento**.</span><span class="sxs-lookup"><span data-stu-id="114a3-166">In the label settings, after you choose the option to base the label on an **event**, you'll see the option to **Choose an event type**.</span></span> <span data-ttu-id="114a3-167">Um tipo de evento é uma descrição geral de um evento que você quer associar a um rótulo.</span><span class="sxs-lookup"><span data-stu-id="114a3-167">An event type is simply a general description of an event that you want to associate a label with.</span></span>
  
<span data-ttu-id="114a3-168">Por exemplo, se você criar um tipo de evento chamado Vida útil do produto, criará os rótulos baseados em eventos com nomes que descrevem a quais tipos de conteúdo você deseja aplicar os rótulos, como "Arquivos de desenvolvimento de produto" ou "Registros de decisões comerciais sobre o produto".</span><span class="sxs-lookup"><span data-stu-id="114a3-168">For example, if you create an event type named Product Lifetime, you'll create event-based retention labels with names that describe what types of content you want the labels to be applied to, such as "Product development files" or "Product business decision records".</span></span>

<span data-ttu-id="114a3-169">Selecione um dos tipos de eventos internos ou crie o seu próprio e selecione-o.</span><span class="sxs-lookup"><span data-stu-id="114a3-169">Select one of the built-in event types, or create your own and then select it.</span></span>

<span data-ttu-id="114a3-170">Após escolher um tipo de evento e salvar o rótulo de retenção, o tipo de evento não poderá mais ser alterado.</span><span class="sxs-lookup"><span data-stu-id="114a3-170">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>
  
![Opções para criar ou escolher um tipo de evento](../media/8b7afe79-72cb-462e-81d4-b5ddbe899dbc.png)
  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="114a3-172">Etapa 3: publicar ou aplicar automaticamente os rótulos de retenção com base em eventos</span><span class="sxs-lookup"><span data-stu-id="114a3-172">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="114a3-173">Assim como qualquer rótulo, você precisa publicar ou aplicar automaticamente um rótulo com base em eventos, para que ele seja aplicado manual ou automaticamente ao conteúdo:</span><span class="sxs-lookup"><span data-stu-id="114a3-173">Just like any retention label, you need to publish or auto-apply an event-based label, for it to be manually or automatically applied to content:</span></span>
- [<span data-ttu-id="114a3-174">Criar rótulos de retenção e aplicá-los em aplicativos</span><span class="sxs-lookup"><span data-stu-id="114a3-174">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="114a3-175">Aplicar um rótulo de retenção automaticamente ao conteúdo</span><span class="sxs-lookup"><span data-stu-id="114a3-175">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)


> [!NOTE]
> <span data-ttu-id="114a3-176">Se você selecionar um rótulo de retenção voltada para a aba **Plano de Arquivo** > **de Gerenciamento de Arquivos** ou **Rótulos de Dados de Governança** > \*\*\*\*, o botão **aplicar rótulo automaticamente** não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="114a3-176">If you select an event-based retention label from **Records Management** > **File plan** tab or **Data governance** > **Labels** tab, the **Auto-apply a label** button is not available.</span></span>
> 
> <span data-ttu-id="114a3-177">Em vez disso, use a **Aplicar um rótulo automaticamente**, acima da lista de rótulos ou políticas, de um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="114a3-177">Instead of this button, use the **Auto-apply a label** option above the list of labels or policies from one of the following locations:</span></span>
> - <span data-ttu-id="114a3-178">Aba de políticas de**Gerenciamento de registros** > \*\*de Rótulo \*\*</span><span class="sxs-lookup"><span data-stu-id="114a3-178">**Records management** > **Label policies** tab</span></span>
> - <span data-ttu-id="114a3-179">Aba de Rótulos de\*\*Governança de dados \*\* > \*\*\*\* ou aba de **políticas**</span><span class="sxs-lookup"><span data-stu-id="114a3-179">**Data governance** > **Labels** tab or **Label policies** tab</span></span>


![Opções para publicar ou aplicar automaticamente um rótulo](..\media\compliance-information-governance-publish-labels.png)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="114a3-181">Etapa 4: Inserir uma ID de ativo</span><span class="sxs-lookup"><span data-stu-id="114a3-181">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="114a3-182">Depois que um rótulo baseado em eventos é aplicado ao conteúdo, você pode inserir uma ID de ativos para cada item.</span><span class="sxs-lookup"><span data-stu-id="114a3-182">After an event-based label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="114a3-183">Por exemplo, sua organização pode usar:</span><span class="sxs-lookup"><span data-stu-id="114a3-183">For example, your organization might use:</span></span>
  
- <span data-ttu-id="114a3-184">Códigos de produto que você pode usar para reter o conteúdo apenas de um produto específico.</span><span class="sxs-lookup"><span data-stu-id="114a3-184">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="114a3-185">Códigos de projeto que você pode usar para reter o conteúdo apenas de um projeto específico.</span><span class="sxs-lookup"><span data-stu-id="114a3-185">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="114a3-186">IDs de funcionário que você pode usar para reter o conteúdo apenas de uma pessoa específica.</span><span class="sxs-lookup"><span data-stu-id="114a3-186">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="114a3-187">A ID de Ativo é, simplesmente, mais uma propriedade do documento que está disponível no SharePoint e no OneDrive.</span><span class="sxs-lookup"><span data-stu-id="114a3-187">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="114a3-188">Sua organização já pode usar outras propriedades e IDs do documento para classificar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="114a3-188">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="114a3-189">Nesse caso, você também pode usar essas propriedades e valores ao criar um evento — consulte a Etapa 6 a seguir.</span><span class="sxs-lookup"><span data-stu-id="114a3-189">If so, you can also use those properties and values when you create an event—see step 6 that follows.</span></span> <span data-ttu-id="114a3-190">O ponto importante é que você deve usar alguma combinação de *propriedade:valor* nas propriedades do documento para associar esse item a um tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="114a3-190">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![Caixa de texto para inserir uma ID de ativo](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="114a3-192">Etapa 5: Criar um evento</span><span class="sxs-lookup"><span data-stu-id="114a3-192">Step 5: Create an event</span></span>

<span data-ttu-id="114a3-193">Quando uma instância específica desse tipo de evento ocorre — como, por exemplo, o fim da vida útil de um produto — vá para a página **Eventos de gerenciamento** > **de registros** no centro de conformidade do Microsoft 365 e crie um evento.</span><span class="sxs-lookup"><span data-stu-id="114a3-193">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center and create an event.</span></span> <span data-ttu-id="114a3-194">Você precisa desencadear um evento por meio de sua criação.</span><span class="sxs-lookup"><span data-stu-id="114a3-194">You trigger an event by creating it.</span></span>
  
### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="114a3-195">Etapa 6: Escolher o mesmo tipo de evento usado pelo rótulo na Etapa 2</span><span class="sxs-lookup"><span data-stu-id="114a3-195">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="114a3-196">Ao criar o evento, escolha o mesmo tipo de evento usado pelo rótulo de retenção na Etapa 2 — por exemplo, a Vida Útil do Produto.</span><span class="sxs-lookup"><span data-stu-id="114a3-196">When you create the event, choose the same event type used by the retention label in step 2—for example, Product Lifetime.</span></span> <span data-ttu-id="114a3-197">Somente o conteúdo com os rótulos de retenção aplicados a esse tipo de evento terá o período de retenção ativado.</span><span class="sxs-lookup"><span data-stu-id="114a3-197">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>
  
![Opção em Configurações de evento para escolher um tipo de evento](../media/11663591-5628-419e-9537-61eb8f5c741f.png)
  
### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="114a3-199">Etapa 7: Inserir palavras-chave ou IDs de ativo</span><span class="sxs-lookup"><span data-stu-id="114a3-199">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="114a3-200">Agora você restringe o escopo do conteúdo especificando IDs de ativos para o conteúdo do SharePoint e OneDrive ou palavras-chave para o conteúdo do Exchange.</span><span class="sxs-lookup"><span data-stu-id="114a3-200">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content, or keywords for Exchange content.</span></span> <span data-ttu-id="114a3-201">Para IDs de ativos, a retenção será aplicada apenas no conteúdo com o par especificado *propriedade:valor*.</span><span class="sxs-lookup"><span data-stu-id="114a3-201">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="114a3-202">Se uma ID de ativos não for inserida, todo o conteúdo com rótulos desse tipo de evento obtém a mesma data de retenção aplicada a ele.</span><span class="sxs-lookup"><span data-stu-id="114a3-202">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="114a3-203">Por exemplo: se estiver usando a propriedade ID de ativo, digite `ComplianceAssetID:<value>` na caixa para IDs de ativos mostrada abaixo.</span><span class="sxs-lookup"><span data-stu-id="114a3-203">For example: If you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="114a3-204">Sua organização pode ter aplicado outras propriedades e IDs aos documentos relacionados a esse tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="114a3-204">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="114a3-205">Por exemplo, se for preciso detectar os registros de um produto específico, a ID pode ser uma combinação entre sua propriedade personalizada ProductID e o valor "XYZ".</span><span class="sxs-lookup"><span data-stu-id="114a3-205">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="114a3-206">Nesse caso, você digitaria `ProductID:XYZ` na caixa para as IDs de Ativos mostradas na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="114a3-206">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>
  
<span data-ttu-id="114a3-207">Para itens do Exchange, use palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="114a3-207">For Exchange items, use keywords.</span></span> <span data-ttu-id="114a3-208">Você pode usar a consulta usando operadores de pesquisa como E, OU e NÃO.</span><span class="sxs-lookup"><span data-stu-id="114a3-208">You can use a query by using search operators such as AND, OR, and NOT.</span></span> <span data-ttu-id="114a3-209">Para saber mais, veja [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="114a3-209">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="114a3-210">Por fim, escolha a data em que o evento ocorreu; essa data é usada como o início do período de retenção.</span><span class="sxs-lookup"><span data-stu-id="114a3-210">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="114a3-211">Depois de criar um evento, essa data do evento é sincronizada para todo o conteúdo com um rótulo desse tipo de evento, ID do ativo e palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="114a3-211">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="114a3-212">Como ocorre com qualquer rótulo de retenção, essa sincronização poderá demorar até sete dias.</span><span class="sxs-lookup"><span data-stu-id="114a3-212">As with any retention label, this synchronization can take up to seven days.</span></span>
  
![Página Configurações de Eventos](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="114a3-214">Após a criação de um evento, as configurações de retenção entrarão em vigor para o conteúdo que já estiver rotulado e indexado.</span><span class="sxs-lookup"><span data-stu-id="114a3-214">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="114a3-215">Se o rótulo de retenção for adicionado a um novo conteúdo após o evento ter sido criado, você precisará criar um novo evento com os mesmos dados.</span><span class="sxs-lookup"><span data-stu-id="114a3-215">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="114a3-216">A exclusão de um evento não cancela as configurações de retenção que já estão em vigor para o conteúdo já rotulado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="114a3-216">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="114a3-217">Para este fim, crie um novo evento com os mesmos dados, mas deixe a data em branco.</span><span class="sxs-lookup"><span data-stu-id="114a3-217">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="114a3-218">Usar a Pesquisa de Conteúdo para localizar todo o conteúdo com um rótulo ou ID de ativo específicos</span><span class="sxs-lookup"><span data-stu-id="114a3-218">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="114a3-219">Após a atribuição dos rótulos de retenção ao conteúdo, você pode usar a pesquisa de conteúdo para localizar todo o conteúdo classificado com um rótulo de retenção específico ou que contenha uma ID de ativo específica:</span><span class="sxs-lookup"><span data-stu-id="114a3-219">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="114a3-220">Para localizar todo o conteúdo com um rótulo de retenção específico, escolha a condição **Rótulo de retenção** e, em seguida, digite o nome completo do rótulo ou parte dele e use um caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="114a3-220">To find all content with a specific retention label, choose the **Retention label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="114a3-221">Para localizar todo o conteúdo com uma ID de ativo específica, digite a propriedade **ComplianceAssetID** e um valor, usando o formato `ComplianceAssetID:<value>`.</span><span class="sxs-lookup"><span data-stu-id="114a3-221">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="114a3-222">Para saber mais, veja [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="114a3-222">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="permissions"></a><span data-ttu-id="114a3-223">Permissões</span><span class="sxs-lookup"><span data-stu-id="114a3-223">Permissions</span></span>

<span data-ttu-id="114a3-p129">Para acessar a página **Eventos**, os revisores devem ser membros de um grupo com a função **Gerenciamento de disposição** e a função **Logs de auditoria somente para exibição**. Recomendamos criar um novo grupo de funções denominado Revisores de disposição, adicionar essas duas funções a esse grupo e incluir membros ao grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="114a3-p129">To get access to the **Events** page, reviewers must be members of a role group with the **Disposition Management** role and the **View-Only Audit Logs** role. We recommend creating a new role group called Disposition Reviewers, adding these two roles to that role group, and then adding members to the role group.</span></span> 
  
<span data-ttu-id="114a3-226">Para saber mais, consulte [Dar aos usuários acesso ao Centro de Conformidade e Segurança do Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="114a3-226">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="114a3-227">Automatizar eventos usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="114a3-227">Automate events by using PowerShell</span></span>

<span data-ttu-id="114a3-228">É possível usar um script do PowerShell para automatizar a retenção baseada em eventos a partir de aplicativos da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="114a3-228">You can use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="114a3-229">Os cmdlets do PowerShell disponíveis para retenção baseada em eventos:</span><span class="sxs-lookup"><span data-stu-id="114a3-229">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="114a3-230">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="114a3-230">Get-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873002)
    
- [<span data-ttu-id="114a3-231">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="114a3-231">New-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873004)
    
- [<span data-ttu-id="114a3-232">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="114a3-232">Remove-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873005)
    
- [<span data-ttu-id="114a3-233">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="114a3-233">Set-ComplianceRetentionEventType</span></span>](https://go.microsoft.com/fwlink/?linkid=873006)
    
- [<span data-ttu-id="114a3-234">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="114a3-234">Get-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873001)
    
- [<span data-ttu-id="114a3-235">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="114a3-235">New-ComplianceRetentionEvent</span></span>](https://go.microsoft.com/fwlink/?linkid=873003)
    

## <a name="automate-events-by-using-a-rest-api"></a><span data-ttu-id="114a3-236">Automatizar eventos usando uma API REST</span><span class="sxs-lookup"><span data-stu-id="114a3-236">Automate events by using a REST API</span></span>

<span data-ttu-id="114a3-237">É possível usar uma API REST para criar automaticamente os eventos que acionam o início do período de retenção.</span><span class="sxs-lookup"><span data-stu-id="114a3-237">You can use a REST API to automatically create the events that trigger the start of the retention time.</span></span>

<span data-ttu-id="114a3-238">Uma API REST é um ponto de extremidade de manutenção que respalda conjuntos de operações (métodos) HTTP que, por seu lado, fornecem acesso para criar/recuperar/atualizar/excluir os recursos de manutenção.</span><span class="sxs-lookup"><span data-stu-id="114a3-238">A REST API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="114a3-239">Para saber mais, confira o artigo [Componentes de uma solicitação/resposta API REST](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="114a3-239">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="114a3-240">Quando você usa uma API REST do Microsoft 365, é possível criar eventos usando os métodos POST e GET.</span><span class="sxs-lookup"><span data-stu-id="114a3-240">By using the Microsoft 365 REST API, events can be created and retrieved using the POST and GET methods.</span></span>

<span data-ttu-id="114a3-241">Existem duas opções para se usar uma API REST:</span><span class="sxs-lookup"><span data-stu-id="114a3-241">There are two options for using the REST API:</span></span>

- <span data-ttu-id="114a3-242">O **Microsoft Power Automate ou um aplicativo semelhante** para acionar automaticamente a ocorrência de um evento. </span><span class="sxs-lookup"><span data-stu-id="114a3-242">**Microsoft Power Automate or a similar application** to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="114a3-243">O Microsoft Power Automate é um orquestrador utilizado para a conexão com outros sistemas, então não é necessário escrever uma solução personalizada.</span><span class="sxs-lookup"><span data-stu-id="114a3-243">Microsoft Power Automate is an orchestrator for connecting to other systems, so you don't need to write a custom solution.</span></span> <span data-ttu-id="114a3-244">Para obter mais informações, consulte o [site do Power Automate](https://flow.microsoft.com/pt-BR/).</span><span class="sxs-lookup"><span data-stu-id="114a3-244">For more information, see the [Power Automate website](https://flow.microsoft.com/pt-BR/).</span></span>

- <span data-ttu-id="114a3-245">O **PowerShell ou um cliente HTTP para chamar uma API REST** e criar eventos usando o PowerShell (versão 6 ou superior), que faz parte de uma solução personalizada.</span><span class="sxs-lookup"><span data-stu-id="114a3-245">**PowerShell or an HTTP client to call the REST API** to create events by using PowerShell (version 6 or later), which is part of a custom solution.</span></span>

<span data-ttu-id="114a3-246">Antes de usar a API REST como um administrador global, confirme o URL que deverá ser usado para chamar o evento de retenção.</span><span class="sxs-lookup"><span data-stu-id="114a3-246">Before you use the REST API, as a global administrator, confirm the URL to use for the retention event call.</span></span> <span data-ttu-id="114a3-247">Para este fim, execute uma chamada de evento de retenção GET usando o URL da API REST: </span><span class="sxs-lookup"><span data-stu-id="114a3-247">To do this, run a GET retention event call by using the REST API URL:</span></span>

```console
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

<span data-ttu-id="114a3-248">Verifique o código de resposta.</span><span class="sxs-lookup"><span data-stu-id="114a3-248">Check the response code.</span></span> <span data-ttu-id="114a3-249">Se for 302, obtenha o URL redirecionado a partir da propriedade Localização no cabeçalho da resposta e use esse URL ao invés de `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` nas instruções que se seguem.</span><span class="sxs-lookup"><span data-stu-id="114a3-249">If it's 302, get the redirected URL from the Location property of the response header and use that URL instead of `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in the instructions that follow.</span></span>

<span data-ttu-id="114a3-250">Os eventos que são criados automaticamente podem ser confirmados ao serem visualizados no Centro de Conformidade do Microsoft 365 > **Gerenciamento de registros** >  **Eventos**.</span><span class="sxs-lookup"><span data-stu-id="114a3-250">The events that get automatically created can be confirmed by viewing them in the Microsoft 365 compliance center > **Records management** >  **Events**.</span></span>

### <a name="use-microsoft-power-automate-to-create-the-event"></a><span data-ttu-id="114a3-251">Usar o Microsoft Power Automate para criar um evento</span><span class="sxs-lookup"><span data-stu-id="114a3-251">Use Microsoft Power Automate to create the event</span></span>

<span data-ttu-id="114a3-252">Criar um fluxo que cria um evento usando uma API REST do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="114a3-252">Create a flow that creates an event using the Microsoft 365 REST API:</span></span>

![Usando o Flow para criar um evento](../media/automate-event-driven-retention-flow-1.png)

![Usando um fluxo para chamar a API REST](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a><span data-ttu-id="114a3-255">Criar um evento</span><span class="sxs-lookup"><span data-stu-id="114a3-255">Create an event</span></span>

<span data-ttu-id="114a3-256">Exemplo de código para chamar a API REST:</span><span class="sxs-lookup"><span data-stu-id="114a3-256">Sample code to call the REST API:</span></span>

- <span data-ttu-id="114a3-257">**Método**: POSTAR</span><span class="sxs-lookup"><span data-stu-id="114a3-257">**Method**: POST</span></span>
- <span data-ttu-id="114a3-258">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="114a3-258">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="114a3-259">**Cabeçalhos**: Chave = content-type, valor = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="114a3-259">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="114a3-260">**Corpo**:</span><span class="sxs-lookup"><span data-stu-id="114a3-260">**Body**:</span></span>
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
    
- <span data-ttu-id="114a3-261">**Autenticação**: Básica</span><span class="sxs-lookup"><span data-stu-id="114a3-261">**Authentication**: Basic</span></span>
- <span data-ttu-id="114a3-262">**Nome de usuário**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="114a3-262">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="114a3-263">**Senha**: "Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="114a3-263">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="114a3-264">Parâmetros disponíveis</span><span class="sxs-lookup"><span data-stu-id="114a3-264">Available parameters</span></span>


|<span data-ttu-id="114a3-265">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="114a3-265">Parameters</span></span>|<span data-ttu-id="114a3-266">Descrição</span><span class="sxs-lookup"><span data-stu-id="114a3-266">Description</span></span>|<span data-ttu-id="114a3-267">Observações</span><span class="sxs-lookup"><span data-stu-id="114a3-267">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="114a3-268"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="114a3-268"><d:Name></d:Name></span></span>|<span data-ttu-id="114a3-269">Fornece um nome exclusivo para o evento,</span><span class="sxs-lookup"><span data-stu-id="114a3-269">Provide a unique name for the event,</span></span>|<span data-ttu-id="114a3-270">Não pode conter espaços à direita nem os seguintes caracteres: % \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="114a3-270">Cannot contain trailing spaces or the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="114a3-271">, : ;</span><span class="sxs-lookup"><span data-stu-id="114a3-271">, : ;</span></span>|
|<span data-ttu-id="114a3-272"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="114a3-272"><d:EventType></d:EventType></span></span>|<span data-ttu-id="114a3-273">Insere o nome do tipo de evento (ou GUID).</span><span class="sxs-lookup"><span data-stu-id="114a3-273">Enter event type name (or Guid),</span></span>|<span data-ttu-id="114a3-274">Exemplo: “Demissão de um funcionário”.</span><span class="sxs-lookup"><span data-stu-id="114a3-274">Example: "Employee termination".</span></span> <span data-ttu-id="114a3-275">O tipo de evento precisa estar associado a um rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="114a3-275">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="114a3-276"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="114a3-276"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="114a3-277">Insere "ComplianceAssetId:" + a ID do funcionário</span><span class="sxs-lookup"><span data-stu-id="114a3-277">Enter "ComplianceAssetId:" + employee ID</span></span>|<span data-ttu-id="114a3-278">Example: "ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="114a3-278">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="114a3-279"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="114a3-279"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="114a3-280">Data e hora do evento</span><span class="sxs-lookup"><span data-stu-id="114a3-280">Event Date and Time</span></span>|<span data-ttu-id="114a3-281">Formato: yyyy-MM-ddTHH:mm:ssZ. Exemplo: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="114a3-281">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

###### <a name="response-codes"></a><span data-ttu-id="114a3-282">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="114a3-282">Response codes</span></span>

| <span data-ttu-id="114a3-283">Código da resposta</span><span class="sxs-lookup"><span data-stu-id="114a3-283">Response Code</span></span> | <span data-ttu-id="114a3-284">Descrição</span><span class="sxs-lookup"><span data-stu-id="114a3-284">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="114a3-285">302</span><span class="sxs-lookup"><span data-stu-id="114a3-285">302</span></span>               | <span data-ttu-id="114a3-286">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="114a3-286">Redirect</span></span>              |
| <span data-ttu-id="114a3-287">201</span><span class="sxs-lookup"><span data-stu-id="114a3-287">201</span></span>               | <span data-ttu-id="114a3-288">Criado em</span><span class="sxs-lookup"><span data-stu-id="114a3-288">Created</span></span>               |
| <span data-ttu-id="114a3-289">403</span><span class="sxs-lookup"><span data-stu-id="114a3-289">403</span></span>               | <span data-ttu-id="114a3-290">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="114a3-290">Authorization Failed</span></span>  |
| <span data-ttu-id="114a3-291">401</span><span class="sxs-lookup"><span data-stu-id="114a3-291">401</span></span>               | <span data-ttu-id="114a3-292">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="114a3-292">Authentication Failed</span></span> |

##### <a name="get-events-based-on-a-time-range"></a><span data-ttu-id="114a3-293">Obter eventos com base em um intervalo de tempo</span><span class="sxs-lookup"><span data-stu-id="114a3-293">Get events based on a time range</span></span>

- <span data-ttu-id="114a3-294">**Método**: GET</span><span class="sxs-lookup"><span data-stu-id="114a3-294">**Method**: GET</span></span>

- <span data-ttu-id="114a3-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="114a3-295">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="114a3-296">**Cabeçalhos**: Chave = content-type, valor = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="114a3-296">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="114a3-297">**Autenticação**: Básica</span><span class="sxs-lookup"><span data-stu-id="114a3-297">**Authentication**: Basic</span></span>

- <span data-ttu-id="114a3-298">**Nome de usuário**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="114a3-298">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="114a3-299">**Senha**: "Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="114a3-299">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="114a3-300">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="114a3-300">Response codes</span></span>

| <span data-ttu-id="114a3-301">Código da resposta</span><span class="sxs-lookup"><span data-stu-id="114a3-301">Response Code</span></span> | <span data-ttu-id="114a3-302">Descrição</span><span class="sxs-lookup"><span data-stu-id="114a3-302">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="114a3-303">200</span><span class="sxs-lookup"><span data-stu-id="114a3-303">200</span></span>               | <span data-ttu-id="114a3-304">OK. Uma lista de eventos em atom+xml</span><span class="sxs-lookup"><span data-stu-id="114a3-304">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="114a3-305">404</span><span class="sxs-lookup"><span data-stu-id="114a3-305">404</span></span>               | <span data-ttu-id="114a3-306">Não encontrado</span><span class="sxs-lookup"><span data-stu-id="114a3-306">Not found</span></span>                         |
| <span data-ttu-id="114a3-307">302</span><span class="sxs-lookup"><span data-stu-id="114a3-307">302</span></span>               | <span data-ttu-id="114a3-308">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="114a3-308">Redirect</span></span>                          |
| <span data-ttu-id="114a3-309">401</span><span class="sxs-lookup"><span data-stu-id="114a3-309">401</span></span>               | <span data-ttu-id="114a3-310">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="114a3-310">Authorization Failed</span></span>              |
| <span data-ttu-id="114a3-311">403</span><span class="sxs-lookup"><span data-stu-id="114a3-311">403</span></span>               | <span data-ttu-id="114a3-312">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="114a3-312">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="114a3-313">Obter um evento por ID</span><span class="sxs-lookup"><span data-stu-id="114a3-313">Get an event by ID</span></span>

- <span data-ttu-id="114a3-314">**Método**: GET</span><span class="sxs-lookup"><span data-stu-id="114a3-314">**Method**: GET</span></span>

- <span data-ttu-id="114a3-315">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="114a3-315">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="114a3-316">**Cabeçalhos**: Chave = content-type, valor = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="114a3-316">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="114a3-317">**Autenticação**: Básica</span><span class="sxs-lookup"><span data-stu-id="114a3-317">**Authentication**: Basic</span></span>

- <span data-ttu-id="114a3-318">**Nome de usuário**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="114a3-318">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="114a3-319">**Senha**: "Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="114a3-319">**Password**: "Compliancepassword"</span></span>

###### <a name="response-codes"></a><span data-ttu-id="114a3-320">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="114a3-320">Response codes</span></span>

| <span data-ttu-id="114a3-321">Código da resposta</span><span class="sxs-lookup"><span data-stu-id="114a3-321">Response Code</span></span> | <span data-ttu-id="114a3-322">Descrição</span><span class="sxs-lookup"><span data-stu-id="114a3-322">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="114a3-323">200</span><span class="sxs-lookup"><span data-stu-id="114a3-323">200</span></span>               | <span data-ttu-id="114a3-324">OK. O corpo da resposta contém o evento em atom+xml.</span><span class="sxs-lookup"><span data-stu-id="114a3-324">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="114a3-325">404</span><span class="sxs-lookup"><span data-stu-id="114a3-325">404</span></span>               | <span data-ttu-id="114a3-326">Não encontrado</span><span class="sxs-lookup"><span data-stu-id="114a3-326">Not found</span></span>                                            |
| <span data-ttu-id="114a3-327">302</span><span class="sxs-lookup"><span data-stu-id="114a3-327">302</span></span>               | <span data-ttu-id="114a3-328">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="114a3-328">Redirect</span></span>                                             |
| <span data-ttu-id="114a3-329">401</span><span class="sxs-lookup"><span data-stu-id="114a3-329">401</span></span>               | <span data-ttu-id="114a3-330">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="114a3-330">Authorization Failed</span></span>                                 |
| <span data-ttu-id="114a3-331">403</span><span class="sxs-lookup"><span data-stu-id="114a3-331">403</span></span>               | <span data-ttu-id="114a3-332">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="114a3-332">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="114a3-333">Obter um evento por nome</span><span class="sxs-lookup"><span data-stu-id="114a3-333">Get an event by name</span></span>

- <span data-ttu-id="114a3-334">**Método**: GET</span><span class="sxs-lookup"><span data-stu-id="114a3-334">**Method**: GET</span></span>

- <span data-ttu-id="114a3-335">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="114a3-335">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="114a3-336">**Cabeçalhos**: Chave = content-type, valor = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="114a3-336">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="114a3-337">**Autenticação**: Básica</span><span class="sxs-lookup"><span data-stu-id="114a3-337">**Authentication**: Basic</span></span>

- <span data-ttu-id="114a3-338">**Nome de usuário**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="114a3-338">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="114a3-339">**Senha**: "Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="114a3-339">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="114a3-340">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="114a3-340">Response codes</span></span>

| <span data-ttu-id="114a3-341">Código da resposta</span><span class="sxs-lookup"><span data-stu-id="114a3-341">Response Code</span></span> | <span data-ttu-id="114a3-342">Descrição</span><span class="sxs-lookup"><span data-stu-id="114a3-342">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="114a3-343">200</span><span class="sxs-lookup"><span data-stu-id="114a3-343">200</span></span>               | <span data-ttu-id="114a3-344">OK. O corpo da resposta contém o evento em atom+xml.</span><span class="sxs-lookup"><span data-stu-id="114a3-344">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="114a3-345">404</span><span class="sxs-lookup"><span data-stu-id="114a3-345">404</span></span>               | <span data-ttu-id="114a3-346">Não encontrado</span><span class="sxs-lookup"><span data-stu-id="114a3-346">Not found</span></span>                                            |
| <span data-ttu-id="114a3-347">302</span><span class="sxs-lookup"><span data-stu-id="114a3-347">302</span></span>               | <span data-ttu-id="114a3-348">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="114a3-348">Redirect</span></span>                                             |
| <span data-ttu-id="114a3-349">401</span><span class="sxs-lookup"><span data-stu-id="114a3-349">401</span></span>               | <span data-ttu-id="114a3-350">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="114a3-350">Authorization Failed</span></span>                                 |
| <span data-ttu-id="114a3-351">403</span><span class="sxs-lookup"><span data-stu-id="114a3-351">403</span></span>               | <span data-ttu-id="114a3-352">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="114a3-352">Authentication Failed</span></span>                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a><span data-ttu-id="114a3-353">Usar o PowerShell ou qualquer cliente HTTP para criar o evento</span><span class="sxs-lookup"><span data-stu-id="114a3-353">Use PowerShell or any HTTP client to create the event</span></span>

<span data-ttu-id="114a3-354">O PowerShell precisa estar na versão 6 ou superior.</span><span class="sxs-lookup"><span data-stu-id="114a3-354">PowerShell must be version 6 or later.</span></span>

<span data-ttu-id="114a3-355">Em uma sessão do PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="114a3-355">In a PowerShell session, run the following script:</span></span>

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```

