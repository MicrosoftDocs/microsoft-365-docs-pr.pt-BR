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
ms.openlocfilehash: ee828b6852440f5be07fdf34df2fb6a11253ae1c
ms.sourcegitcommit: 8998f70d3f7bd673f93f8d1cf12ce981b1b771c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51034242"
---
# <a name="start-retention-when-an-event-occurs"></a><span data-ttu-id="9b5e0-103">Iniciar a retenção quando um evento ocorrer</span><span class="sxs-lookup"><span data-stu-id="9b5e0-103">Start retention when an event occurs</span></span>

><span data-ttu-id="9b5e0-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="9b5e0-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="9b5e0-p101">Quando você retém o conteúdo, o período de retenção normalmente é baseado na idade desse conteúdo. Por exemplo, você pode reter documentos por sete anos após terem sido criados e excluí-los após esse prazo. Porém, se você configurar os [rótulos de retenção](retention.md#retention-labels), poderá também basear um período de retenção no momento em que um tipo específico de evento ocorre. O evento desencadeia o início do período de retenção e as ações de retenção do rótulo passam a ser aplicadas a todo o conteúdo que tiver esse rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-p101">When you retain content, the retention period is often based on the age of the content. For example, you might retain documents for seven years after they're created and then delete them. But when you configure [retention labels](retention.md#retention-labels), you can also base a retention period on when a specific type of event occurs. The event triggers the start of the retention period, and all content with a retention label applied for that type of event get the label's retention actions enforced on them.</span></span>
  
<span data-ttu-id="9b5e0-109">Exemplos de uso da retenção baseada por eventos:</span><span class="sxs-lookup"><span data-stu-id="9b5e0-109">Examples for using event-based retention:</span></span>
  
- <span data-ttu-id="9b5e0-110">**Funcionários que estão saindo da organização** Suponha que os registros de funcionários devam ser retidos por 10 anos após a data em que o funcionário saiu da organização.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-110">**Employees leaving the organization** Suppose that employee records must be retained for 10 years from the time an employee leaves the organization.</span></span> <span data-ttu-id="9b5e0-111">Decorrido o prazo de 10 anos, todos os documentos relacionados à contratação, desempenho e demissão desse funcionário precisam ser descartados.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-111">After 10 years elapse, all documents related to the hiring, performance, and termination of that employee must be disposed.</span></span> <span data-ttu-id="9b5e0-112">O evento que desencadeia o período de retenção de 10 anos é a saída do funcionário da organização.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-112">The event that triggers the 10-year retention period is the employee leaving the organization.</span></span> 
    
- <span data-ttu-id="9b5e0-113">**Vencimento de um contrato** Suponha que todos os registros relativos a contratos devam ser retidos por 10 anos após a data de vencimento do contrato.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-113">**Contract expiration** Suppose that all records related to contracts must be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="9b5e0-114">O evento que desencadeia o período de retenção de cinco anos é o vencimento do contrato.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-114">The event that triggers the five-year retention period is the expiration of the contract.</span></span> 
    
- <span data-ttu-id="9b5e0-p104">**Vida útil do produto** Talvez sua organização tenha exigências de retenção relacionadas à última data de produção de produtos para determinados conteúdos, como especificações técnicas. Nesse caso, a última data de produção é o evento que dispara o período de retenção.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-p104">**Product lifetime** Your organization might have retention requirements related to the last manufacturing date of products for content such as technical specifications. In this case, the last manufacturing date is the event that triggers the retention period.</span></span> 
    
<span data-ttu-id="9b5e0-p105">A retenção baseada em eventos geralmente é usada como parte de um processo de gerenciamento de registros. Isso significa que:</span><span class="sxs-lookup"><span data-stu-id="9b5e0-p105">Event-based retention is typically used as part of a records-management process. This means that:</span></span>
  
- <span data-ttu-id="9b5e0-119">Os rótulos com base em eventos geralmente classificam o conteúdo como um registro, como parte de uma solução de gerenciamento de registros.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-119">Retention labels based on events also usually mark items as a record, as a part of a records management solution.</span></span> <span data-ttu-id="9b5e0-120">Para obter mais informações, confira o artigo [Saiba mais sobre registros](records-management.md).</span><span class="sxs-lookup"><span data-stu-id="9b5e0-120">For more information, see [Learn about records management](records-management.md).</span></span>

- <span data-ttu-id="9b5e0-121">Um documento declarado como um registro, mas cujo gatilho de evento ainda não aconteceu, é retido indefinidamente (registros não podem ser excluídos permanentemente), até que um evento dispare o período de retenção desse documento.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-121">A document that's been declared a record but whose event trigger has not yet happened is retained indefinitely (records can't be permanently deleted), until an event triggers that document's retention period.</span></span>
    
- <span data-ttu-id="9b5e0-122">Os rótulos de retenção baseados em eventos costumam desencadear uma análise de descarte no final do período de retenção, de modo que um gerente de registros possa analisar e descartar o conteúdo manualmente.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-122">Retention labels based on events usually trigger a disposition review at the end of the retention period, so that a records manager can manually review and dispose of the content.</span></span> <span data-ttu-id="9b5e0-123">Para obter mais informações, confira o artigo [Disposição e descarte de conteúdo](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="9b5e0-123">For more information, see [Disposition of content](disposition.md).</span></span>
    

<span data-ttu-id="9b5e0-124">Os recursos dos rótulos de retenção baseados em um evento são os mesmos que os de quaisquer outros rótulos de retenção do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-124">A retention label based on an event has the same capabilities as any retention label in Microsoft 365.</span></span> <span data-ttu-id="9b5e0-125">Para obter mais informações, consulte [saiba mais sobre políticas e rótulos de retenção](retention.md).</span><span class="sxs-lookup"><span data-stu-id="9b5e0-125">For more information, see [Learn about retention policies and retention labels](retention.md).</span></span>

## <a name="understanding-the-relationship-between-event-types-labels-events-and-asset-ids"></a><span data-ttu-id="9b5e0-126">Compreender a relação entre tipos de eventos, rótulos, eventos e IDs de ativos</span><span class="sxs-lookup"><span data-stu-id="9b5e0-126">Understanding the relationship between event types, labels, events, and asset IDs</span></span>

<span data-ttu-id="9b5e0-127">Para usar a retenção controlada por eventos com êxito, é importante compreender a relação entre tipos de evento, rótulos de retenção, eventos e IDs de ativo, conforme ilustrado nos diagramas e explicações a seguir:</span><span class="sxs-lookup"><span data-stu-id="9b5e0-127">To successfully use event-based retention, it's important to understand the relationship between event types, retention labels, events, and asset IDs as illustrated in the diagrams and the explanation that follows:</span></span> 
  
![Diagrama 1 de 2: Tipo de evento, rótulos, eventos e IDs de ativos](../media/a5141a6b-61ca-4a60-9ab0-24e6bb45bbdb.png)
  
![Diagrama 2 de 2: Tipo de evento, rótulos, eventos e IDs de ativos](../media/ce89a91f-49aa-4b5a-933c-ac3a13dccd5d.png)
  
1. <span data-ttu-id="9b5e0-130">Você cria rótulos de retenção para diferentes tipos de conteúdo e depois os associa a um tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-130">You create retention labels for different types of content and then associate them with a type of event.</span></span> <span data-ttu-id="9b5e0-131">Por exemplo, os rótulos de retenção para diferentes tipos de arquivos e registros de produtos são associados a um tipo de evento denominado Vida útil do produto, pois esses registros devem ser retidos por 10 anos a partir do momento em que o produto atinge o final de sua vida útil.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-131">For example, retention labels for different types of product files and records are associated with an event type named Product Lifetime because those records must be retained for 10 years from the time the product reaches its end of life.</span></span>
    
2. <span data-ttu-id="9b5e0-132">Os usuários (normalmente gerenciadores de registros) aplicam esses rótulos de retenção ao conteúdo e (para documentos do SharePoint e OneDrive) inserem uma ID de ativo para cada item.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-132">Users (typically records managers) apply those retention labels to content and (for documents in SharePoint and OneDrive) enter an asset ID for each item.</span></span> <span data-ttu-id="9b5e0-133">Nesse exemplo, a ID do ativo é um nome ou código de produto usado pela organização.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-133">In this example, the asset ID is a product name or code used by the organization.</span></span> <span data-ttu-id="9b5e0-134">Assim, os registros de cada produto recebem um rótulo de retenção e cada registro tem uma propriedade que contém uma ID de ativo.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-134">Then, each product's records are assigned a retention label, and each record has a property that contains an asset ID.</span></span> <span data-ttu-id="9b5e0-135">O diagrama representa **todo o conteúdo** de todos os registros de produtos em uma organização e cada item tem a ID do ativo do produto cujo registro ele pertence.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-135">The diagram represents **all the content** for all product records in an organization, and each item bears the asset ID of the product whose record it is.</span></span> 
    
3. <span data-ttu-id="9b5e0-p111">A Vida Útil do Produto é o tipo de evento; um produto específico chegando ao fim de sua vida útil é um evento. Quando ocorre um evento desse tipo — nesse caso, quando um produto chega ao final de sua vida útil —, você cria um evento que especifica o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9b5e0-p111">Product Lifetime is the event type; a specific product reaching end of life is an event. When an event of that event type occurs—in this case, when a product reaches its end of life—you create an event that specifies:</span></span>
    
   - <span data-ttu-id="9b5e0-138">Uma ID de ativo (para documentos do SharePoint e do OneDrive)</span><span class="sxs-lookup"><span data-stu-id="9b5e0-138">An asset ID (for SharePoint and OneDrive documents)</span></span>
    
   - <span data-ttu-id="9b5e0-p112">Palavras-chave (para itens do Exchange). Neste exemplo, a organização usa um código de produto em mensagens que contêm registros de produto, assim, a palavra-chave para itens do Exchange é igual à ID de ativos de documentos do SharePoint e do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-p112">Keywords (for Exchange items). In this example, the organization uses a product code in messages containing product records, so the keyword for Exchange items is functionally the same as the asset ID for SharePoint and OneDrive documents.</span></span>
    
   - <span data-ttu-id="9b5e0-p113">A data de ocorrência do evento. Essa data é utilizada como o início do período de retenção. Essa data pode ser a atual, do passado ou futura.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-p113">The date when the event occurred. This date is used as the start of the retention period. This date can be the current, a past, or a future date.</span></span>

4. <span data-ttu-id="9b5e0-144">Depois de criar um evento, a data dele é sincronizada com todo o conteúdo que tem um rótulo desse tipo de evento e que contém a ID ou palavra-chave especificada do ativo.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-144">After you create an event, that event date is synchronized to all the content that has a retention label of that event type and that contains the specified asset ID or keyword.</span></span> <span data-ttu-id="9b5e0-145">Como ocorre com qualquer rótulo de retenção, essa sincronização poderá demorar até sete dias.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-145">Like any retention label, this synchronization can take up to seven days.</span></span> <span data-ttu-id="9b5e0-146">No diagrama anterior, todos os itens marcados com um círculo vermelho têm o período de retenção desencadeado por esse evento.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-146">In the previous diagram, all the items circled in red have their retention period triggered by this event.</span></span> <span data-ttu-id="9b5e0-147">Em outras palavras, quando esse produto chega ao fim da vida útil, esse evento ativa o período de retenção dos registros desse produto.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-147">In other words, when this product reaches its end of life, that event triggers the retention period for that product's records.</span></span>

<span data-ttu-id="9b5e0-148">É importante entender que, se você não especificar uma ID de ativo ou palavras-chave para um evento, **todo o conteúdo** com um rótulo de retenção desse tipo de evento terá um período de retenção ativado pelo evento.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-148">It's important to understand that if you don't specify an asset ID or keywords for an event, **all content** with a retention label of that event type will have its retention period triggered by the event.</span></span> <span data-ttu-id="9b5e0-149">Isso significa que, no diagrama anterior, todo o conteúdo começaria a ser retido.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-149">This means that in the previous diagram, all content would start being retained.</span></span> <span data-ttu-id="9b5e0-150">Isso pode não ser o que você pretende.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-150">This might not be what you intend.</span></span>

<span data-ttu-id="9b5e0-151">Por fim, lembre-se de que cada rótulo de retenção tem suas próprias configurações de retenção.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-151">Finally, remember that each retention label has its own retention settings.</span></span> <span data-ttu-id="9b5e0-152">Neste exemplo, todos eles especificam dez anos, mas é possível que um evento ative rótulos de retenção onde cada rótulo tem um período de retenção diferente.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-152">In this example, they all specify 10 years, but it's possible for an event to trigger retention labels where each label has a different retention period.</span></span>
  
## <a name="how-to-set-up-event-driven-retention"></a><span data-ttu-id="9b5e0-153">Como configurar a retenção controlada por eventos</span><span class="sxs-lookup"><span data-stu-id="9b5e0-153">How to set up event-driven retention</span></span>

<span data-ttu-id="9b5e0-154">Aqui está o fluxo de trabalho de alto nível para a retenção controlada por eventos:</span><span class="sxs-lookup"><span data-stu-id="9b5e0-154">High-level workflow for event-driven retention:</span></span>
  
![Diagrama de fluxo de trabalho para configurar a retenção controlada por eventos](../media/event-based-retention-process.png)
  
> [!TIP]
> <span data-ttu-id="9b5e0-156">Confira [Usar rótulos de retenção para gerenciar o ciclo de vida de documentos armazenados no SharePoint](auto-apply-retention-labels-scenario.md) para um cenário detalhado sobre como usar as propriedades gerenciadas no SharePoint para aplicar automaticamente os rótulos de retenção e implementar a retenção voltada para o evento.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-156">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>

### <a name="step-1-create-a-label-whose-retention-period-is-based-on-an-event"></a><span data-ttu-id="9b5e0-157">Etapa 1: criar um rótulo cujo período de retenção seja baseado em um evento</span><span class="sxs-lookup"><span data-stu-id="9b5e0-157">Step 1: Create a label whose retention period is based on an event</span></span>

<span data-ttu-id="9b5e0-158">Para criar e configurar seu rótulo de retenção, Confira as instruções em [Criar e configurar rótulos de retenção](./create-apply-retention-labels.md#step-1-create-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="9b5e0-158">To create and configure your retention label, see the instructions for [Create retention labels](./create-apply-retention-labels.md#step-1-create-retention-labels).</span></span> <span data-ttu-id="9b5e0-159">Mas especificamente para a retenção baseada em eventos, na página **Definir as configurações de retenção** do assistente Criar etiqueta de retenção, depois de **Iniciar o período de retenção com base em**, selecione um dos tipos de eventos padrão na lista suspensa ou crie o seu próprio selecionando **Criar novo tipo de evento**:</span><span class="sxs-lookup"><span data-stu-id="9b5e0-159">But specific to event-based retention, on the **Define retention settings** page of the Create retention label wizard, after **Start the retention period based on**, select one of the default event types from the dropdown list, or create your own by selecting **Create new event type**:</span></span>

![Criar um novo tipo de evento para um rótulo de retenção](../media/SPRetention6.png)

<span data-ttu-id="9b5e0-161">Um tipo de evento é uma descrição geral de um evento que você quer associar a um rótulo.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-161">An event type is simply a general description of an event that you want to associate with a retention label.</span></span>

<span data-ttu-id="9b5e0-162">Os tipos de evento padrão têm o **(tipo de evento)** depois do nome na lista suspensa, para facilitar a identificação, além disso, você também pode ver e criar o tipo de evento na aba **Gerenciamento de registros** > **Eventos** > **Gerenciar tipos de eventos**.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-162">The default event types have **(event type)** after their name in the dropdown list for easier identification, and you can also see and create event type from the **Records management** > **Events** tab > **Manage event types**.</span></span>

<span data-ttu-id="9b5e0-163">A retenção impulsionada por eventos requer configurações de retenção que:</span><span class="sxs-lookup"><span data-stu-id="9b5e0-163">Event-based retention requires retention settings that:</span></span>
  
- <span data-ttu-id="9b5e0-164">Retêm o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-164">Retain the content.</span></span>
    
- <span data-ttu-id="9b5e0-165">Excluem o conteúdo automaticamente, ou acionam uma revisão de disposição ao final do período de retenção.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-165">Delete the content automatically or trigger a disposition review at the end of the retention period.</span></span>
  
<span data-ttu-id="9b5e0-166">A retenção baseada em eventos geralmente é usada para o conteúdo declarado como um registro, portanto, esse é um bom momento para verificar se você também precisa selecionar a opção que marca o conteúdo como um [registro](records-management.md#records).</span><span class="sxs-lookup"><span data-stu-id="9b5e0-166">Event-based retention is typically used for content that's declared a record, so this is a good time to check whether you also need to select the option that marks content as a [record](records-management.md#records).</span></span>

<span data-ttu-id="9b5e0-167">Se você estiver usando um tipo de evento existente, em vez de criar um novo tipo de evento, vá para a etapa 3.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-167">If you're using an existing event type rather than creating a new event type, skip to step 3.</span></span>

> [!NOTE]
> <span data-ttu-id="9b5e0-168">Após escolher um tipo de evento e salvar o rótulo de retenção, o tipo de evento não poderá mais ser alterado.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-168">After you choose an event type and save the retention label, the event type cannot be changed.</span></span>

### <a name="step-2-create-a-new-event-type-for-your-label"></a><span data-ttu-id="9b5e0-169">Etapa 2: Criar um novo tipo de evento para um rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="9b5e0-169">Step 2: Create a new event type for your label</span></span>

<span data-ttu-id="9b5e0-170">Para as configurações de retenção, se você tiver selecionado **Criar novo tipo de evento**, insira um nome e uma descrição para o seu tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-170">For the retention settings, if you selected **Create new event type**, enter a name and description for your event type.</span></span> <span data-ttu-id="9b5e0-171">Em seguida, selecione **Próximo**, **Enviar**, e **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-171">Then select **Next**, **Submit**, and **Done**.</span></span>

<span data-ttu-id="9b5e0-172">De volta à página **Definir configurações de retenção**, para **Iniciar o período de retenção com base em**, use a lista suspensa para selecionar o tipo de evento que você criou.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-172">Back on the **Define retention settings** page, for **Start the retention period based on**, use the dropdown list to select the event type that you created.</span></span>

  
### <a name="step-3-publish-or-auto-apply-the-event-based-retention-labels"></a><span data-ttu-id="9b5e0-173">Etapa 3: publicar ou aplicar automaticamente os rótulos de retenção com base em eventos</span><span class="sxs-lookup"><span data-stu-id="9b5e0-173">Step 3: Publish or auto-apply the event-based retention labels</span></span>

<span data-ttu-id="9b5e0-174">Assim como qualquer rótulo, você precisa publicar ou aplicar automaticamente um rótulo com base em eventos, para que ele seja aplicado manual ou automaticamente ao conteúdo:</span><span class="sxs-lookup"><span data-stu-id="9b5e0-174">Just like any retention label, you need to publish or auto-apply an event-based label, for it to be manually or automatically applied to content:</span></span>
- [<span data-ttu-id="9b5e0-175">Criar rótulos de retenção e aplicá-los em aplicativos</span><span class="sxs-lookup"><span data-stu-id="9b5e0-175">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
- [<span data-ttu-id="9b5e0-176">Aplicar um rótulo de retenção automaticamente ao conteúdo</span><span class="sxs-lookup"><span data-stu-id="9b5e0-176">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="step-4-enter-an-asset-id"></a><span data-ttu-id="9b5e0-177">Etapa 4: Inserir uma ID de ativo</span><span class="sxs-lookup"><span data-stu-id="9b5e0-177">Step 4: Enter an asset ID</span></span>

<span data-ttu-id="9b5e0-178">Depois que um rótulo baseado em eventos é aplicado ao conteúdo, você pode inserir uma ID de ativos para cada item.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-178">After an event-based label is applied to content, you can enter an asset ID for each item.</span></span> <span data-ttu-id="9b5e0-179">Por exemplo, sua organização pode usar:</span><span class="sxs-lookup"><span data-stu-id="9b5e0-179">For example, your organization might use:</span></span>
  
- <span data-ttu-id="9b5e0-180">Códigos de produto que você pode usar para reter o conteúdo apenas de um produto específico.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-180">Product codes that you can use to retain content for only a specific product.</span></span>
    
- <span data-ttu-id="9b5e0-181">Códigos de projeto que você pode usar para reter o conteúdo apenas de um projeto específico.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-181">Project codes that you can use to retain content for only a specific project.</span></span>
    
- <span data-ttu-id="9b5e0-182">IDs de funcionário que você pode usar para reter o conteúdo apenas de uma pessoa específica.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-182">Employee IDs that you can use to retain content for only a specific person.</span></span>
    
<span data-ttu-id="9b5e0-183">A ID de Ativo é, simplesmente, mais uma propriedade do documento que está disponível no SharePoint e no OneDrive.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-183">Asset ID is simply another document property that's available in SharePoint and OneDrive.</span></span> <span data-ttu-id="9b5e0-184">Sua organização já pode usar outras propriedades e IDs do documento para classificar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-184">Your organization might already use other document properties and IDs to classify content.</span></span> <span data-ttu-id="9b5e0-185">Nesse caso, você também pode usar essas propriedades e valores ao criar um evento — consulte a Etapa 6 a seguir.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-185">If so, you can also use those properties and values when you create an event—see step 6 that follows.</span></span> <span data-ttu-id="9b5e0-186">O ponto importante é que você deve usar alguma combinação de *propriedade:valor* nas propriedades do documento para associar esse item a um tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-186">The important point is that you must use some *property:value* combination in the document properties to associate that item with an event type.</span></span>
  
![Caixa de texto para inserir uma ID de ativo](../media/6d31628e-7162-4370-a8d7-de704aafa350.png)
  
### <a name="step-5-create-an-event"></a><span data-ttu-id="9b5e0-188">Etapa 5: Criar um evento</span><span class="sxs-lookup"><span data-stu-id="9b5e0-188">Step 5: Create an event</span></span>

<span data-ttu-id="9b5e0-189">Quando uma instância específica desse tipo de evento ocorre — como, por exemplo, o fim da vida útil de um produto — vá para a página **Eventos de gerenciamento** > **de registros** no Centro de conformidade do Microsoft 365 e selecion **+ Criar** para criar um evento.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-189">When a particular instance of that event type occurs, such as a product reaches its end of life, go to the **Records management** > **Events** page in the Microsoft 365 compliance center, and select **+ Create** to create an event.</span></span> <span data-ttu-id="9b5e0-190">Para acionar o evento, crie-o aqui.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-190">You trigger the event by creating it, here.</span></span>

![Criar um evento para disparar o início da retenção de rótulos de retenção com base em eventos](../media/create-event-records-management.png)

<span data-ttu-id="9b5e0-192">Até 1 milhão eventos têm suporte por locatário.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-192">Up to one million events are supported per tenant.</span></span>

### <a name="step-6-choose-the-same-event-type-used-by-the-label-in-step-2"></a><span data-ttu-id="9b5e0-193">Etapa 6: Escolher o mesmo tipo de evento usado pelo rótulo na Etapa 2</span><span class="sxs-lookup"><span data-stu-id="9b5e0-193">Step 6: Choose the same event type used by the label in step 2</span></span>

<span data-ttu-id="9b5e0-194">Ao criar o evento, escolha o mesmo tipo de evento usado pelo rótulo de retenção na Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-194">When you create the event, choose the same event type specified in the retention label settings in step 2.</span></span> <span data-ttu-id="9b5e0-195">Por exemplo, se você selecionou **Vida útil do produto** como seu tipo de evento para as configurações de rótulo, selecione **Vida útil do produto** quando criar o evento.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-195">For example, if you selected **Product Lifetime** as your event type for the label settings, select **Product Lifetime** when you create the event.</span></span> <span data-ttu-id="9b5e0-196">Somente o conteúdo com os rótulos de retenção aplicados a esse tipo de evento terá o período de retenção ativado.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-196">Only content with retention labels applied to it of that event type will have its retention period triggered.</span></span>

![Opção em Configurações de evento para escolher um tipo de evento](../media/choose-event-type-records-management.png)

<span data-ttu-id="9b5e0-198">Como alternativa, se você precisar criar um evento para vários rótulos de retenção com diferentes tipos de evento, marque a opção **Escolher Rótulos Existentes**.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-198">Alternatively, if you need to create an event for multiple retention labels that have different event types, select the **Choose Existing Labels** option.</span></span> <span data-ttu-id="9b5e0-199">Em seguida, selecione os rótulos que estão configurados para os tipos de eventos que você deseja associar a esse evento.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-199">Then, select the labels that are configured for the event types you want to associate with this event.</span></span>

### <a name="step-7-enter-keywords-or-an-asset-id"></a><span data-ttu-id="9b5e0-200">Etapa 7: Inserir palavras-chave ou IDs de ativo</span><span class="sxs-lookup"><span data-stu-id="9b5e0-200">Step 7: Enter keywords or an asset ID</span></span>

<span data-ttu-id="9b5e0-201">Agora você restringe o escopo do conteúdo especificando IDs de ativos para o conteúdo do SharePoint e OneDrive ou palavras-chave para o conteúdo do Exchange.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-201">Now you narrow the scope of the content by specifying asset IDs for SharePoint and OneDrive content, or keywords for Exchange content.</span></span> <span data-ttu-id="9b5e0-202">Para IDs de ativos, a retenção será aplicada apenas no conteúdo com o par especificado *propriedade:valor*.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-202">For asset IDs, retention will be enforced only on content with the specified *property:value* pair.</span></span> <span data-ttu-id="9b5e0-203">Se uma ID de ativos não for inserida, todo o conteúdo com rótulos desse tipo de evento obtém a mesma data de retenção aplicada a ele.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-203">If an asset ID is not entered, all content with labels of that event type get the same retention date applied to them.</span></span>

<span data-ttu-id="9b5e0-204">Por exemplo: se estiver usando a propriedade ID de ativo, digite `ComplianceAssetID:<value>` na caixa para IDs de ativos mostrada abaixo.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-204">For example: If you're using the Asset ID property, enter `ComplianceAssetID:<value>` in the box for asset IDs shown below.</span></span>
  
<span data-ttu-id="9b5e0-205">Sua organização pode ter aplicado outras propriedades e IDs aos documentos relacionados a esse tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-205">Your organization might have applied other properties and IDs to the documents related to this event type.</span></span> <span data-ttu-id="9b5e0-206">Por exemplo, se for preciso detectar os registros de um produto específico, a ID pode ser uma combinação entre sua propriedade personalizada ProductID e o valor "XYZ".</span><span class="sxs-lookup"><span data-stu-id="9b5e0-206">For example, if you need to detect a specific product's records, the ID might be a combination of your custom property ProductID and the value "XYZ".</span></span> <span data-ttu-id="9b5e0-207">Nesse caso, você digitaria `ProductID:XYZ` na caixa para as IDs de Ativos mostradas na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-207">In this case, you'd enter `ProductID:XYZ` in the box for asset IDs shown in the following picture.</span></span>
  
<span data-ttu-id="9b5e0-208">Para itens do Exchange, use palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-208">For Exchange items, use keywords.</span></span> <span data-ttu-id="9b5e0-209">Você pode usar a consulta usando operadores de pesquisa como E, OU e NÃO.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-209">You can use a query by using search operators such as AND, OR, and NOT.</span></span> <span data-ttu-id="9b5e0-210">Para saber mais, veja [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="9b5e0-210">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
<span data-ttu-id="9b5e0-211">Por fim, escolha a data em que o evento ocorreu; essa data é usada como o início do período de retenção.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-211">Finally, choose the date when the event occurred; this date is used as the start of the retention period.</span></span> <span data-ttu-id="9b5e0-212">Depois de criar um evento, essa data do evento é sincronizada para todo o conteúdo com um rótulo desse tipo de evento, ID do ativo e palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-212">After you create an event, that event date is synchronized to all the content with a retention label of that event type, asset ID, and keywords.</span></span> <span data-ttu-id="9b5e0-213">Como ocorre com qualquer rótulo de retenção, essa sincronização poderá demorar até sete dias.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-213">As with any retention label, this synchronization can take up to seven days.</span></span>
  
![Página Configurações de Eventos](../media/40d3c9db-f624-49a5-b38a-d16bcce20231.png)

<span data-ttu-id="9b5e0-215">Após a criação de um evento, as configurações de retenção entrarão em vigor para o conteúdo que já estiver rotulado e indexado.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-215">After creating an event, the retention settings take effect for the content that's already labeled and indexed.</span></span> <span data-ttu-id="9b5e0-216">Se o rótulo de retenção for adicionado a um novo conteúdo após o evento ter sido criado, você precisará criar um novo evento com os mesmos dados.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-216">If the retention label is added to new content after the event is created, you must create a new event with the same details.</span></span>

<span data-ttu-id="9b5e0-217">A exclusão de um evento não cancela as configurações de retenção que já estão em vigor para o conteúdo já rotulado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-217">Deleting an event doesn't cancel the retention settings that are now in effect for the content that's already labeled.</span></span> <span data-ttu-id="9b5e0-218">Para este fim, crie um novo evento com os mesmos dados, mas deixe a data em branco.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-218">To do that, create a new event with the same details, but leave the date blank.</span></span> 

## <a name="use-content-search-to-find-all-content-with-a-specific-label-or-asset-id"></a><span data-ttu-id="9b5e0-219">Usar a Pesquisa de Conteúdo para localizar todo o conteúdo com um rótulo ou ID de ativo específicos</span><span class="sxs-lookup"><span data-stu-id="9b5e0-219">Use Content Search to find all content with a specific label or asset ID</span></span>

<span data-ttu-id="9b5e0-220">Após a atribuição dos rótulos de retenção ao conteúdo, você pode usar a pesquisa de conteúdo para localizar todo o conteúdo classificado com um rótulo de retenção específico ou que contenha uma ID de ativo específica:</span><span class="sxs-lookup"><span data-stu-id="9b5e0-220">After retention labels are assigned to content, you can use content search to find all content that's classified with a specific retention label or that contains a specific asset ID:</span></span>
  
- <span data-ttu-id="9b5e0-221">Para localizar todo o conteúdo com um rótulo de retenção específico, escolha a condição **Rótulo de retenção** e, em seguida, digite o nome completo do rótulo ou parte dele e use um caractere curinga.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-221">To find all content with a specific retention label, choose the **Retention label** condition, and then enter the complete label name or part of the label name and use a wildcard.</span></span> 
    
- <span data-ttu-id="9b5e0-222">Para localizar todo o conteúdo com uma ID de ativo específica, digite a propriedade **ComplianceAssetID** e um valor, usando o formato `ComplianceAssetID:<value>`.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-222">To find all content with a specific asset ID, enter the **ComplianceAssetID** property and a value, using the format `ComplianceAssetID:<value>`.</span></span> 
    
<span data-ttu-id="9b5e0-223">Para saber mais, veja [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md).</span><span class="sxs-lookup"><span data-stu-id="9b5e0-223">For more information, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>

## <a name="automate-events-by-using-powershell"></a><span data-ttu-id="9b5e0-224">Automatizar eventos usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b5e0-224">Automate events by using PowerShell</span></span>

<span data-ttu-id="9b5e0-225">É possível usar um script do PowerShell para automatizar a retenção baseada em eventos a partir de aplicativos da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-225">You can use a PowerShell script to automate event-based retention from your business applications.</span></span> <span data-ttu-id="9b5e0-226">Os cmdlets do PowerShell disponíveis para retenção baseada em eventos:</span><span class="sxs-lookup"><span data-stu-id="9b5e0-226">The PowerShell cmdlets available for event-based retention:</span></span>
  
- [<span data-ttu-id="9b5e0-227">Get-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="9b5e0-227">Get-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/get-complianceretentioneventtype)
    
- [<span data-ttu-id="9b5e0-228">New-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="9b5e0-228">New-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/new-complianceretentioneventtype)
    
- [<span data-ttu-id="9b5e0-229">Remove-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="9b5e0-229">Remove-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/remove-complianceretentioneventtype)
    
- [<span data-ttu-id="9b5e0-230">Set-ComplianceRetentionEventType</span><span class="sxs-lookup"><span data-stu-id="9b5e0-230">Set-ComplianceRetentionEventType</span></span>](/powershell/module/exchange/set-complianceretentioneventtype)
    
- [<span data-ttu-id="9b5e0-231">Get-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="9b5e0-231">Get-ComplianceRetentionEvent</span></span>](/powershell/module/exchange/get-complianceretentionevent)
    
- [<span data-ttu-id="9b5e0-232">New-ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="9b5e0-232">New-ComplianceRetentionEvent</span></span>](/powershell/module/exchange/new-complianceretentionevent)
    

## <a name="automate-events-by-using-a-rest-api"></a><span data-ttu-id="9b5e0-233">Automatizar eventos usando uma API REST</span><span class="sxs-lookup"><span data-stu-id="9b5e0-233">Automate events by using a REST API</span></span>

<span data-ttu-id="9b5e0-234">É possível usar uma API REST para criar automaticamente os eventos que acionam o início do período de retenção.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-234">You can use a REST API to automatically create the events that trigger the start of the retention time.</span></span>

<span data-ttu-id="9b5e0-235">Uma API REST é um ponto de extremidade de manutenção que respalda conjuntos de operações (métodos) HTTP que, por seu lado, fornecem acesso para criar/recuperar/atualizar/excluir os recursos de manutenção.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-235">A REST API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="9b5e0-236">Para saber mais, confira o artigo [Componentes de uma solicitação/resposta API REST](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span><span class="sxs-lookup"><span data-stu-id="9b5e0-236">For more information, see [Components of a REST API request/response](/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="9b5e0-237">Quando você usa uma API REST do Microsoft 365, é possível criar eventos usando os métodos POST e GET.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-237">By using the Microsoft 365 REST API, events can be created and retrieved using the POST and GET methods.</span></span>

<span data-ttu-id="9b5e0-238">Existem duas opções para se usar uma API REST:</span><span class="sxs-lookup"><span data-stu-id="9b5e0-238">There are two options for using the REST API:</span></span>

- <span data-ttu-id="9b5e0-239">O **Microsoft Power Automate ou um aplicativo semelhante** para acionar automaticamente a ocorrência de um evento. </span><span class="sxs-lookup"><span data-stu-id="9b5e0-239">**Microsoft Power Automate or a similar application** to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="9b5e0-240">O Microsoft Power Automate é um orquestrador utilizado para a conexão com outros sistemas, então não é necessário escrever uma solução personalizada.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-240">Microsoft Power Automate is an orchestrator for connecting to other systems, so you don't need to write a custom solution.</span></span> <span data-ttu-id="9b5e0-241">Para obter mais informações, consulte o [site do Power Automate](https://flow.microsoft.com/pt-BR/).</span><span class="sxs-lookup"><span data-stu-id="9b5e0-241">For more information, see the [Power Automate website](https://flow.microsoft.com/pt-BR/).</span></span>

- <span data-ttu-id="9b5e0-242">O **PowerShell ou um cliente HTTP para chamar uma API REST** e criar eventos usando o PowerShell (versão 6 ou superior), que faz parte de uma solução personalizada.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-242">**PowerShell or an HTTP client to call the REST API** to create events by using PowerShell (version 6 or later), which is part of a custom solution.</span></span>

<span data-ttu-id="9b5e0-243">Antes de usar a API REST como um administrador global, confirme o URL que deverá ser usado para chamar o evento de retenção.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-243">Before you use the REST API, as a global administrator, confirm the URL to use for the retention event call.</span></span> <span data-ttu-id="9b5e0-244">Para este fim, execute uma chamada de evento de retenção GET usando o URL da API REST: </span><span class="sxs-lookup"><span data-stu-id="9b5e0-244">To do this, run a GET retention event call by using the REST API URL:</span></span>

```http
https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent
```

<span data-ttu-id="9b5e0-245">Verifique o código de resposta.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-245">Check the response code.</span></span> <span data-ttu-id="9b5e0-246">Se for 302, obtenha o URL redirecionado a partir da propriedade Localização no cabeçalho da resposta e use esse URL ao invés de `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` nas instruções que se seguem.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-246">If it's 302, get the redirected URL from the Location property of the response header and use that URL instead of `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent` in the instructions that follow.</span></span>

<span data-ttu-id="9b5e0-247">Os eventos que são criados automaticamente podem ser confirmados ao serem visualizados no Centro de Conformidade do Microsoft 365 > **Gerenciamento de registros** >  **Eventos**.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-247">The events that get automatically created can be confirmed by viewing them in the Microsoft 365 compliance center > **Records management** >  **Events**.</span></span>

### <a name="use-microsoft-power-automate-to-create-the-event"></a><span data-ttu-id="9b5e0-248">Usar o Microsoft Power Automate para criar um evento</span><span class="sxs-lookup"><span data-stu-id="9b5e0-248">Use Microsoft Power Automate to create the event</span></span>

<span data-ttu-id="9b5e0-249">Criar um fluxo que cria um evento usando uma API REST do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="9b5e0-249">Create a flow that creates an event using the Microsoft 365 REST API:</span></span>

![Usando o Flow para criar um evento](../media/automate-event-driven-retention-flow-1.png)

![Usando um fluxo para chamar a API REST](../media/automate-event-driven-retention-flow-2.png)

#### <a name="create-an-event"></a><span data-ttu-id="9b5e0-252">Criar um evento</span><span class="sxs-lookup"><span data-stu-id="9b5e0-252">Create an event</span></span>

<span data-ttu-id="9b5e0-253">Exemplo de código para chamar a API REST:</span><span class="sxs-lookup"><span data-stu-id="9b5e0-253">Sample code to call the REST API:</span></span>

- <span data-ttu-id="9b5e0-254">**Método**: POSTAR</span><span class="sxs-lookup"><span data-stu-id="9b5e0-254">**Method**: POST</span></span>
- <span data-ttu-id="9b5e0-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="9b5e0-255">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>
- <span data-ttu-id="9b5e0-256">**Cabeçalhos**: Chave = content-type, valor = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="9b5e0-256">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="9b5e0-257">**Corpo**:</span><span class="sxs-lookup"><span data-stu-id="9b5e0-257">**Body**:</span></span>
    
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
    
- <span data-ttu-id="9b5e0-258">**Autenticação**: Básica</span><span class="sxs-lookup"><span data-stu-id="9b5e0-258">**Authentication**: Basic</span></span>
- <span data-ttu-id="9b5e0-259">**Nome de usuário**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="9b5e0-259">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="9b5e0-260">**Senha**: "Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="9b5e0-260">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="9b5e0-261">Parâmetros disponíveis</span><span class="sxs-lookup"><span data-stu-id="9b5e0-261">Available parameters</span></span>


|<span data-ttu-id="9b5e0-262">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="9b5e0-262">Parameters</span></span>|<span data-ttu-id="9b5e0-263">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b5e0-263">Description</span></span>|<span data-ttu-id="9b5e0-264">Observações</span><span class="sxs-lookup"><span data-stu-id="9b5e0-264">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="9b5e0-265"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="9b5e0-265"><d:Name></d:Name></span></span>|<span data-ttu-id="9b5e0-266">Fornece um nome exclusivo para o evento,</span><span class="sxs-lookup"><span data-stu-id="9b5e0-266">Provide a unique name for the event,</span></span>|<span data-ttu-id="9b5e0-267">Não pode conter espaços à direita nem os seguintes caracteres: % \* \ & < \> \| # ?</span><span class="sxs-lookup"><span data-stu-id="9b5e0-267">Cannot contain trailing spaces or the following characters: % \* \ & < \> \| # ?</span></span> <span data-ttu-id="9b5e0-268">, : ;</span><span class="sxs-lookup"><span data-stu-id="9b5e0-268">, : ;</span></span>|
|<span data-ttu-id="9b5e0-269"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="9b5e0-269"><d:EventType></d:EventType></span></span>|<span data-ttu-id="9b5e0-270">Insere o nome do tipo de evento (ou GUID).</span><span class="sxs-lookup"><span data-stu-id="9b5e0-270">Enter event type name (or Guid),</span></span>|<span data-ttu-id="9b5e0-271">Exemplo: “Demissão de um funcionário”.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-271">Example: "Employee termination".</span></span> <span data-ttu-id="9b5e0-272">O tipo de evento precisa estar associado a um rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-272">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="9b5e0-273"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="9b5e0-273"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="9b5e0-274">Insere "ComplianceAssetId:" + a ID do funcionário</span><span class="sxs-lookup"><span data-stu-id="9b5e0-274">Enter "ComplianceAssetId:" + employee ID</span></span>|<span data-ttu-id="9b5e0-275">Example: "ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="9b5e0-275">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="9b5e0-276"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="9b5e0-276"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="9b5e0-277">Data e hora do evento</span><span class="sxs-lookup"><span data-stu-id="9b5e0-277">Event Date and Time</span></span>|<span data-ttu-id="9b5e0-278">Formato: yyyy-MM-ddTHH:mm:ssZ. Exemplo: 2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="9b5e0-278">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

###### <a name="response-codes"></a><span data-ttu-id="9b5e0-279">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="9b5e0-279">Response codes</span></span>

| <span data-ttu-id="9b5e0-280">Código da resposta</span><span class="sxs-lookup"><span data-stu-id="9b5e0-280">Response Code</span></span> | <span data-ttu-id="9b5e0-281">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b5e0-281">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="9b5e0-282">302</span><span class="sxs-lookup"><span data-stu-id="9b5e0-282">302</span></span>               | <span data-ttu-id="9b5e0-283">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="9b5e0-283">Redirect</span></span>              |
| <span data-ttu-id="9b5e0-284">201</span><span class="sxs-lookup"><span data-stu-id="9b5e0-284">201</span></span>               | <span data-ttu-id="9b5e0-285">Criado em</span><span class="sxs-lookup"><span data-stu-id="9b5e0-285">Created</span></span>               |
| <span data-ttu-id="9b5e0-286">403</span><span class="sxs-lookup"><span data-stu-id="9b5e0-286">403</span></span>               | <span data-ttu-id="9b5e0-287">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="9b5e0-287">Authorization Failed</span></span>  |
| <span data-ttu-id="9b5e0-288">401</span><span class="sxs-lookup"><span data-stu-id="9b5e0-288">401</span></span>               | <span data-ttu-id="9b5e0-289">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="9b5e0-289">Authentication Failed</span></span> |

##### <a name="get-events-based-on-a-time-range"></a><span data-ttu-id="9b5e0-290">Obter eventos com base em um intervalo de tempo</span><span class="sxs-lookup"><span data-stu-id="9b5e0-290">Get events based on a time range</span></span>

- <span data-ttu-id="9b5e0-291">**Método**: GET</span><span class="sxs-lookup"><span data-stu-id="9b5e0-291">**Method**: GET</span></span>

- <span data-ttu-id="9b5e0-292">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span><span class="sxs-lookup"><span data-stu-id="9b5e0-292">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`</span></span>

- <span data-ttu-id="9b5e0-293">**Cabeçalhos**: Chave = content-type, valor = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="9b5e0-293">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="9b5e0-294">**Autenticação**: Básica</span><span class="sxs-lookup"><span data-stu-id="9b5e0-294">**Authentication**: Basic</span></span>

- <span data-ttu-id="9b5e0-295">**Nome de usuário**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="9b5e0-295">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="9b5e0-296">**Senha**: "Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="9b5e0-296">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="9b5e0-297">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="9b5e0-297">Response codes</span></span>

| <span data-ttu-id="9b5e0-298">Código da resposta</span><span class="sxs-lookup"><span data-stu-id="9b5e0-298">Response Code</span></span> | <span data-ttu-id="9b5e0-299">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b5e0-299">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="9b5e0-300">200</span><span class="sxs-lookup"><span data-stu-id="9b5e0-300">200</span></span>               | <span data-ttu-id="9b5e0-301">OK. Uma lista de eventos em atom+xml</span><span class="sxs-lookup"><span data-stu-id="9b5e0-301">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="9b5e0-302">404</span><span class="sxs-lookup"><span data-stu-id="9b5e0-302">404</span></span>               | <span data-ttu-id="9b5e0-303">Não encontrado</span><span class="sxs-lookup"><span data-stu-id="9b5e0-303">Not found</span></span>                         |
| <span data-ttu-id="9b5e0-304">302</span><span class="sxs-lookup"><span data-stu-id="9b5e0-304">302</span></span>               | <span data-ttu-id="9b5e0-305">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="9b5e0-305">Redirect</span></span>                          |
| <span data-ttu-id="9b5e0-306">401</span><span class="sxs-lookup"><span data-stu-id="9b5e0-306">401</span></span>               | <span data-ttu-id="9b5e0-307">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="9b5e0-307">Authorization Failed</span></span>              |
| <span data-ttu-id="9b5e0-308">403</span><span class="sxs-lookup"><span data-stu-id="9b5e0-308">403</span></span>               | <span data-ttu-id="9b5e0-309">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="9b5e0-309">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="9b5e0-310">Obter um evento por ID</span><span class="sxs-lookup"><span data-stu-id="9b5e0-310">Get an event by ID</span></span>

- <span data-ttu-id="9b5e0-311">**Método**: GET</span><span class="sxs-lookup"><span data-stu-id="9b5e0-311">**Method**: GET</span></span>

- <span data-ttu-id="9b5e0-312">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span><span class="sxs-lookup"><span data-stu-id="9b5e0-312">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`</span></span>

- <span data-ttu-id="9b5e0-313">**Cabeçalhos**: Chave = content-type, valor = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="9b5e0-313">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="9b5e0-314">**Autenticação**: Básica</span><span class="sxs-lookup"><span data-stu-id="9b5e0-314">**Authentication**: Basic</span></span>

- <span data-ttu-id="9b5e0-315">**Nome de usuário**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="9b5e0-315">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="9b5e0-316">**Senha**: "Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="9b5e0-316">**Password**: "Compliancepassword"</span></span>

###### <a name="response-codes"></a><span data-ttu-id="9b5e0-317">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="9b5e0-317">Response codes</span></span>

| <span data-ttu-id="9b5e0-318">Código da resposta</span><span class="sxs-lookup"><span data-stu-id="9b5e0-318">Response Code</span></span> | <span data-ttu-id="9b5e0-319">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b5e0-319">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="9b5e0-320">200</span><span class="sxs-lookup"><span data-stu-id="9b5e0-320">200</span></span>               | <span data-ttu-id="9b5e0-321">OK. O corpo da resposta contém o evento em atom+xml.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-321">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="9b5e0-322">404</span><span class="sxs-lookup"><span data-stu-id="9b5e0-322">404</span></span>               | <span data-ttu-id="9b5e0-323">Não encontrado</span><span class="sxs-lookup"><span data-stu-id="9b5e0-323">Not found</span></span>                                            |
| <span data-ttu-id="9b5e0-324">302</span><span class="sxs-lookup"><span data-stu-id="9b5e0-324">302</span></span>               | <span data-ttu-id="9b5e0-325">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="9b5e0-325">Redirect</span></span>                                             |
| <span data-ttu-id="9b5e0-326">401</span><span class="sxs-lookup"><span data-stu-id="9b5e0-326">401</span></span>               | <span data-ttu-id="9b5e0-327">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="9b5e0-327">Authorization Failed</span></span>                                 |
| <span data-ttu-id="9b5e0-328">403</span><span class="sxs-lookup"><span data-stu-id="9b5e0-328">403</span></span>               | <span data-ttu-id="9b5e0-329">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="9b5e0-329">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="9b5e0-330">Obter um evento por nome</span><span class="sxs-lookup"><span data-stu-id="9b5e0-330">Get an event by name</span></span>

- <span data-ttu-id="9b5e0-331">**Método**: GET</span><span class="sxs-lookup"><span data-stu-id="9b5e0-331">**Method**: GET</span></span>

- <span data-ttu-id="9b5e0-332">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span><span class="sxs-lookup"><span data-stu-id="9b5e0-332">**URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`</span></span>

- <span data-ttu-id="9b5e0-333">**Cabeçalhos**: Chave = content-type, valor = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="9b5e0-333">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>

- <span data-ttu-id="9b5e0-334">**Autenticação**: Básica</span><span class="sxs-lookup"><span data-stu-id="9b5e0-334">**Authentication**: Basic</span></span>

- <span data-ttu-id="9b5e0-335">**Nome de usuário**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="9b5e0-335">**Username**: "Complianceuser"</span></span>

- <span data-ttu-id="9b5e0-336">**Senha**: "Senhadeconformidade"</span><span class="sxs-lookup"><span data-stu-id="9b5e0-336">**Password**: "Compliancepassword"</span></span>


###### <a name="response-codes"></a><span data-ttu-id="9b5e0-337">Códigos de resposta</span><span class="sxs-lookup"><span data-stu-id="9b5e0-337">Response codes</span></span>

| <span data-ttu-id="9b5e0-338">Código da resposta</span><span class="sxs-lookup"><span data-stu-id="9b5e0-338">Response Code</span></span> | <span data-ttu-id="9b5e0-339">Descrição</span><span class="sxs-lookup"><span data-stu-id="9b5e0-339">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="9b5e0-340">200</span><span class="sxs-lookup"><span data-stu-id="9b5e0-340">200</span></span>               | <span data-ttu-id="9b5e0-341">OK. O corpo da resposta contém o evento em atom+xml.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-341">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="9b5e0-342">404</span><span class="sxs-lookup"><span data-stu-id="9b5e0-342">404</span></span>               | <span data-ttu-id="9b5e0-343">Não encontrado</span><span class="sxs-lookup"><span data-stu-id="9b5e0-343">Not found</span></span>                                            |
| <span data-ttu-id="9b5e0-344">302</span><span class="sxs-lookup"><span data-stu-id="9b5e0-344">302</span></span>               | <span data-ttu-id="9b5e0-345">Redirecionamento</span><span class="sxs-lookup"><span data-stu-id="9b5e0-345">Redirect</span></span>                                             |
| <span data-ttu-id="9b5e0-346">401</span><span class="sxs-lookup"><span data-stu-id="9b5e0-346">401</span></span>               | <span data-ttu-id="9b5e0-347">Falha na autorização</span><span class="sxs-lookup"><span data-stu-id="9b5e0-347">Authorization Failed</span></span>                                 |
| <span data-ttu-id="9b5e0-348">403</span><span class="sxs-lookup"><span data-stu-id="9b5e0-348">403</span></span>               | <span data-ttu-id="9b5e0-349">Falha na autenticação</span><span class="sxs-lookup"><span data-stu-id="9b5e0-349">Authentication Failed</span></span>                                |

### <a name="use-powershell-or-any-http-client-to-create-the-event"></a><span data-ttu-id="9b5e0-350">Usar o PowerShell ou qualquer cliente HTTP para criar o evento</span><span class="sxs-lookup"><span data-stu-id="9b5e0-350">Use PowerShell or any HTTP client to create the event</span></span>

<span data-ttu-id="9b5e0-351">O PowerShell precisa estar na versão 6 ou superior.</span><span class="sxs-lookup"><span data-stu-id="9b5e0-351">PowerShell must be version 6 or later.</span></span>

<span data-ttu-id="9b5e0-352">Em uma sessão do PowerShell, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="9b5e0-352">In a PowerShell session, run the following script:</span></span>

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
