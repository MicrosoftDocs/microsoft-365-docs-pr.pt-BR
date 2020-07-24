---
title: Saiba mais sobre os registros
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Saiba mais sobre os registros para ajudá-lo na implementação de uma solução de gerenciamento de registros no Microsoft 365.
ms.openlocfilehash: 6cdf29493a3fd95b060c52d9f9587ee34748edde
ms.sourcegitcommit: a53af7a228bb1f58cb8128a69a19da49f9e28700
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2020
ms.locfileid: "45372516"
---
# <a name="learn-about-records"></a><span data-ttu-id="4c2ee-103">Saiba mais sobre os registros</span><span class="sxs-lookup"><span data-stu-id="4c2ee-103">Learn about records</span></span>

><span data-ttu-id="4c2ee-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="4c2ee-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="4c2ee-105">O gerenciamento de registros no Microsoft 365 ajuda a organização a cumprir políticas corporativas, e obrigações legais ou regulamentares, além de reduzir riscos e responsabilidades legais.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-105">Managing records in Microsoft 365 helps your organization comply with corporate policies and legal or regulatory obligations, while also reducing risk and legal liability.</span></span>

<span data-ttu-id="4c2ee-106">Quando o conteúdo é marcado como registro:</span><span class="sxs-lookup"><span data-stu-id="4c2ee-106">When content is marked as a record:</span></span>

- <span data-ttu-id="4c2ee-107">Restrições são colocadas nos itens em termos de quais [ações são permitidas ou bloqueadas](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span><span class="sxs-lookup"><span data-stu-id="4c2ee-107">Restrictions are placed on the items in terms of what [actions are allowed or blocked](#compare-restrictions-for-what-actions-are-allowed-or-blocked).</span></span>

- <span data-ttu-id="4c2ee-108">Atividades adicionais sobre o item são registradas.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-108">Additional activities about the item are logged.</span></span>

- <span data-ttu-id="4c2ee-109">Você tem prova de disposição quando os itens são excluídos no final do período de retenção.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-109">You have proof of disposition when the items are deleted at the end of their retention period.</span></span>

<span data-ttu-id="4c2ee-110">Você usa [rótulos de retenção](retention.md#retention-labels) para marcar conteúdos como registros.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-110">You use [retention labels](retention.md#retention-labels) to mark content as a record.</span></span> <span data-ttu-id="4c2ee-111">É possível publicar esses rótulos para que usuários e administradores possam aplicá-los manualmente ou automaticamente ao conteúdo que você deseja classificar como registro.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-111">You can either publish those labels so that users and administrators can manually apply them to content, or auto-apply those labels to content that you want to mark as a record.</span></span>

<span data-ttu-id="4c2ee-112">Usando rótulos de retenção para marcar o conteúdo como registro, você pode implementar uma estratégia única e consistente para gerenciar registros no ambiente do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-112">By using retention labels to mark content as records, you can implement a single and consistent strategy for managing records across your Microsoft 365 environment.</span></span>

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a><span data-ttu-id="4c2ee-113">Comparar restrições para quais ações são permitidas ou bloqueadas</span><span class="sxs-lookup"><span data-stu-id="4c2ee-113">Compare restrictions for what actions are allowed or blocked</span></span>

<span data-ttu-id="4c2ee-114">Use a tabela a seguir para identificar quais restrições são impostas ao conteúdo como resultado da aplicação de um rótulo de retenção padrão e rótulos de retenção que marcam o conteúdo como registro.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-114">Use the following table to identify what restrictions are placed on content as a result of applying a standard retention label, and retention labels that mark content as a record.</span></span> 

<span data-ttu-id="4c2ee-115">Um rótulo de retenção padrão tem a configuração de retenção de dados sem marcar o conteúdo como registro.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-115">A standard retention label has the configuration to retain data without marking content as a record.</span></span>

>[!NOTE] 
> <span data-ttu-id="4c2ee-116">Para garantir a integridade, a tabela inclui colunas para um registro bloqueado e desbloqueado, aplicável ao SharePoint e OneDrive, mas não ao Exchange.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-116">For completeness, the table includes columns for a locked and unlocked record, which is applicable to SharePoint and OneDrive, but not Exchange.</span></span> <span data-ttu-id="4c2ee-117">A capacidade de bloquear e desbloquear um registro usa o [controle de versão do registro](#record-versioning) que não tem suporte para itens do Exchange.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-117">The ability to lock and unlock a record uses [record versioning](#record-versioning) that isn't supported for Exchange items.</span></span> <span data-ttu-id="4c2ee-118">Portanto, para todos os itens do Exchange marcados como registro, o comportamento é mapeado para a coluna **Registro - bloqueado** e a coluna **Registro - desbloqueado** não é relevante.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-118">So for all Exchange items that are marked as a record, the behavior maps to the **Record - locked** column, and the **Record - unlocked column** is not relevant.</span></span>


|<span data-ttu-id="4c2ee-119">Action</span><span class="sxs-lookup"><span data-stu-id="4c2ee-119">Action</span></span>| <span data-ttu-id="4c2ee-120">Rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="4c2ee-120">Retention label</span></span> |<span data-ttu-id="4c2ee-121">Registro - bloqueado</span><span class="sxs-lookup"><span data-stu-id="4c2ee-121">Record - locked</span></span>| <span data-ttu-id="4c2ee-122">Registro - desbloqueado</span><span class="sxs-lookup"><span data-stu-id="4c2ee-122">Record - unlocked</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4c2ee-123">Editar conteúdo</span><span class="sxs-lookup"><span data-stu-id="4c2ee-123">Edit contents</span></span>|<span data-ttu-id="4c2ee-124">Permitido</span><span class="sxs-lookup"><span data-stu-id="4c2ee-124">Allowed</span></span> | <span data-ttu-id="4c2ee-125">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="4c2ee-125">**Blocked**</span></span> | <span data-ttu-id="4c2ee-126">Permitido</span><span class="sxs-lookup"><span data-stu-id="4c2ee-126">Allowed</span></span>|
|<span data-ttu-id="4c2ee-127">Editar propriedades, incluindo renomear</span><span class="sxs-lookup"><span data-stu-id="4c2ee-127">Edit properties, including rename</span></span>|<span data-ttu-id="4c2ee-128">Permitido</span><span class="sxs-lookup"><span data-stu-id="4c2ee-128">Allowed</span></span> |<span data-ttu-id="4c2ee-129">Permitido</span><span class="sxs-lookup"><span data-stu-id="4c2ee-129">Allowed</span></span> | <span data-ttu-id="4c2ee-130">Permitido</span><span class="sxs-lookup"><span data-stu-id="4c2ee-130">Allowed</span></span>|
|<span data-ttu-id="4c2ee-131">Excluir</span><span class="sxs-lookup"><span data-stu-id="4c2ee-131">Delete</span></span>|<span data-ttu-id="4c2ee-132">Permitido <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="4c2ee-132">Allowed <sup>1</sup></span></span> |<span data-ttu-id="4c2ee-133">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="4c2ee-133">**Blocked**</span></span> | <span data-ttu-id="4c2ee-134">**Bloqueado**</span><span class="sxs-lookup"><span data-stu-id="4c2ee-134">**Blocked**</span></span>|
|<span data-ttu-id="4c2ee-135">Copiar</span><span class="sxs-lookup"><span data-stu-id="4c2ee-135">Copy</span></span>|<span data-ttu-id="4c2ee-136">Permitido</span><span class="sxs-lookup"><span data-stu-id="4c2ee-136">Allowed</span></span> |<span data-ttu-id="4c2ee-137">Permitido</span><span class="sxs-lookup"><span data-stu-id="4c2ee-137">Allowed</span></span> | <span data-ttu-id="4c2ee-138">Permitido</span><span class="sxs-lookup"><span data-stu-id="4c2ee-138">Allowed</span></span>|
|<span data-ttu-id="4c2ee-139">Mover dentro do contêiner <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4c2ee-139">Move within container <sup>2</sup></span></span>|<span data-ttu-id="4c2ee-140">Permitido</span><span class="sxs-lookup"><span data-stu-id="4c2ee-140">Allowed</span></span> |<span data-ttu-id="4c2ee-141">Permitido</span><span class="sxs-lookup"><span data-stu-id="4c2ee-141">Allowed</span></span> | <span data-ttu-id="4c2ee-142">Permitido</span><span class="sxs-lookup"><span data-stu-id="4c2ee-142">Allowed</span></span>|
|<span data-ttu-id="4c2ee-143">Mover entre contêineres <sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="4c2ee-143">Move across containers <sup>2</sup></span></span>|<span data-ttu-id="4c2ee-144">Permitido</span><span class="sxs-lookup"><span data-stu-id="4c2ee-144">Allowed</span></span> |<span data-ttu-id="4c2ee-145">Permitido se nunca desbloqueado</span><span class="sxs-lookup"><span data-stu-id="4c2ee-145">Allowed if never unlocked</span></span> | <span data-ttu-id="4c2ee-146">Permitido</span><span class="sxs-lookup"><span data-stu-id="4c2ee-146">Allowed</span></span>|
|<span data-ttu-id="4c2ee-147">Abrir/Ler</span><span class="sxs-lookup"><span data-stu-id="4c2ee-147">Open/Read</span></span>|<span data-ttu-id="4c2ee-148">Permitido</span><span class="sxs-lookup"><span data-stu-id="4c2ee-148">Allowed</span></span> |<span data-ttu-id="4c2ee-149">Permitido</span><span class="sxs-lookup"><span data-stu-id="4c2ee-149">Allowed</span></span> | <span data-ttu-id="4c2ee-150">Permitido</span><span class="sxs-lookup"><span data-stu-id="4c2ee-150">Allowed</span></span>|
|<span data-ttu-id="4c2ee-151">Alterar rótulo</span><span class="sxs-lookup"><span data-stu-id="4c2ee-151">Change label</span></span>|<span data-ttu-id="4c2ee-152">Permitido</span><span class="sxs-lookup"><span data-stu-id="4c2ee-152">Allowed</span></span> |<span data-ttu-id="4c2ee-153">Permitido - somente administrador do contêiner</span><span class="sxs-lookup"><span data-stu-id="4c2ee-153">Allowed - container admin only</span></span> | <span data-ttu-id="4c2ee-154">Permitido - somente administrador do contêiner</span><span class="sxs-lookup"><span data-stu-id="4c2ee-154">Allowed - container admin only</span></span>|
|<span data-ttu-id="4c2ee-155">Remover rótulo</span><span class="sxs-lookup"><span data-stu-id="4c2ee-155">Remove label</span></span>|<span data-ttu-id="4c2ee-156">Permitido</span><span class="sxs-lookup"><span data-stu-id="4c2ee-156">Allowed</span></span> |<span data-ttu-id="4c2ee-157">Permitido - somente administrador do contêiner</span><span class="sxs-lookup"><span data-stu-id="4c2ee-157">Allowed - container admin only</span></span> | <span data-ttu-id="4c2ee-158">Permitido - somente administrador do contêiner</span><span class="sxs-lookup"><span data-stu-id="4c2ee-158">Allowed - container admin only</span></span>|

<span data-ttu-id="4c2ee-159">Notas de rodapé:</span><span class="sxs-lookup"><span data-stu-id="4c2ee-159">Footnotes:</span></span>

<span data-ttu-id="4c2ee-160"><sup>1</sup> Com suporte do OneDrive e Exchange, mantendo uma cópia em um local seguro, mas bloqueado pelo SharePoint.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-160"><sup>1</sup> Supported by OneDrive and Exchange by retaining a copy in a secured location, but blocked by SharePoint.</span></span>

<span data-ttu-id="4c2ee-161">Mensagem que um usuário vê se tentar excluir um documento rotulado no SharePoint:</span><span class="sxs-lookup"><span data-stu-id="4c2ee-161">Message a user sees if they try to delete a labeled document in SharePoint:</span></span>

![Mensagem informando que o item não foi excluído do SharePoint](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<span data-ttu-id="4c2ee-163"><sup>2</sup> Os contêineres incluem bibliotecas de documentos do SharePoint e caixas de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-163"><sup>2</sup> Containers include SharePoint document libraries and Exchange mailboxes.</span></span>


## <a name="using-retention-labels-to-declare-records"></a><span data-ttu-id="4c2ee-164">Usando rótulos de retenção para declarar registros</span><span class="sxs-lookup"><span data-stu-id="4c2ee-164">Using retention labels to declare records</span></span>

<span data-ttu-id="4c2ee-165">Ao criar um rótulo de retenção, você tem a opção de usá-lo para classificar o conteúdo como um registro:</span><span class="sxs-lookup"><span data-stu-id="4c2ee-165">When you create a retention label, you have the option to use the retention label to mark the content as a record:</span></span>

1. <span data-ttu-id="4c2ee-166">No centro de conformidade do Microsoft 365, vá para **Gerenciamento de Registros** \> **Plano de Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-166">In the Microsoft 365 compliance center, go to **Records Management** \> **File Plan**.</span></span> <span data-ttu-id="4c2ee-167">Na página **Planejamento de arquivos**, clique em **Criar um rótulo**.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-167">On the **File plan** page, select **Create a label**.</span></span>

2. <span data-ttu-id="4c2ee-168">Na página **Configurações de rótulo** no assistente, escolha a opção para classificar o conteúdo como registro.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-168">On the **Label settings** page in the wizard, choose the option to classify content as a record.</span></span>
    
   ![Clique em Usar rótulo para classificar o conteúdo como uma caixa de seleção de Registro](../media/recordversioning6.png)

3. <span data-ttu-id="4c2ee-170">Aplique o rótulo de retenção aos documentos do SharePoint ou OneDrive e emails do Exchange, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-170">Apply the retention label to SharePoint or OneDrive documents and Exchange emails, as needed.</span></span> <span data-ttu-id="4c2ee-171">Para obter instruções:</span><span class="sxs-lookup"><span data-stu-id="4c2ee-171">For instructions:</span></span>
    
    - [<span data-ttu-id="4c2ee-172">Criar rótulos de retenção e aplicá-los em aplicativos</span><span class="sxs-lookup"><span data-stu-id="4c2ee-172">Create retention labels and apply them in apps</span></span>](create-apply-retention-labels.md)
    
    - [<span data-ttu-id="4c2ee-173">Aplicar um rótulo de retenção automaticamente ao conteúdo</span><span class="sxs-lookup"><span data-stu-id="4c2ee-173">Apply a retention label to content automatically</span></span>](apply-retention-labels-automatically.md)

### <a name="applying-the-configured-retention-label-to-content"></a><span data-ttu-id="4c2ee-174">Aplicando o rótulo de retenção configurado ao conteúdo</span><span class="sxs-lookup"><span data-stu-id="4c2ee-174">Applying the configured retention label to content</span></span>

<span data-ttu-id="4c2ee-175">Quando os rótulos de retenção que marcam o conteúdo como registro são disponibilizados para os usuários aplicá-los nos aplicativos:</span><span class="sxs-lookup"><span data-stu-id="4c2ee-175">When retention labels that mark content as a record are made available for users to apply them in apps:</span></span>

- <span data-ttu-id="4c2ee-176">Para o Exchange, qualquer usuário com acesso de gravação à caixa de correio pode aplicar esses rótulos.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-176">For Exchange, any user with write-access to the mailbox can apply these labels.</span></span> 
- <span data-ttu-id="4c2ee-177">Para o SharePoint e OneDrive, qualquer usuário no grupo Membros padrão (o nível de permissão de Contribuição) pode aplicar esses rótulos.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-177">For SharePoint and OneDrive, any user in the default Members group (the Contribute permission level) can apply these labels.</span></span>

<span data-ttu-id="4c2ee-178">Exemplo de um documento marcado como registro usando um rótulo de retenção:</span><span class="sxs-lookup"><span data-stu-id="4c2ee-178">Example of a document marked as record by using a retention label:</span></span>

![Painel de detalhes do documento marcado como um registro](../media/recordversioning7.png)

## <a name="record-versioning"></a><span data-ttu-id="4c2ee-180">Controle de versão do registro</span><span class="sxs-lookup"><span data-stu-id="4c2ee-180">Record versioning</span></span>

<span data-ttu-id="4c2ee-181">A capacidade de marcar um documento como registro e restringir as ações que podem ser executadas no registro é uma meta essencial para qualquer solução de gerenciamento de registros.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-181">The ability to mark a document as a record and restrict actions that can be performed on the record is an essential goal for any records management solution.</span></span> <span data-ttu-id="4c2ee-182">No entanto, a colaboração também pode ser necessária para as pessoas criarem versões posteriores.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-182">However, collaboration might also be needed for people to create subsequent versions.</span></span>

<span data-ttu-id="4c2ee-183">Por exemplo, você pode marcar um contrato de vendas como registro, mas precisa atualizar o contrato com novos termos e marcar a versão mais recente como novo registro enquanto ainda mantém a versão do registro anterior.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-183">For example, you might mark a sales contract as a record, but then need to update the contract with new terms and mark the latest version as a new record while still retaining the previous record version.</span></span> <span data-ttu-id="4c2ee-184">Para esses tipos de cenários, o SharePoint e o OneDrive oferecem suporte ao *controle de versão do registro*.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-184">For these types of scenarios, SharePoint and OneDrive support *record versioning*.</span></span> <span data-ttu-id="4c2ee-185">As pastas do bloco de anotações do OneNote não oferecem suporte ao controle de versão do registro.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-185">OneNote notebook folders don't support record versioning.</span></span>

<span data-ttu-id="4c2ee-186">Para usar a versão do registro, primeiro rotule o documento e marque-o como registro.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-186">To use record versioning, first label the document and mark it as a record.</span></span> <span data-ttu-id="4c2ee-187">Nesse momento, uma propriedade do documento, chamada *Status do registro* será exibida ao lado do rótulo de retenção e o status inicial do registro será **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-187">At this point, a document property, called *Record status* is displayed next to the retention label, and the initial record status is **Locked**.</span></span> 

<span data-ttu-id="4c2ee-188">Agora, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4c2ee-188">You can now do the following things:</span></span>

  - <span data-ttu-id="4c2ee-189">**Editar e reter continuamente versões individuais do documento como registros, desbloqueando e bloqueando a propriedade de Status do registro.**</span><span class="sxs-lookup"><span data-stu-id="4c2ee-189">**Continually edit and retain individual versions of the document as records, by unlocking and locking the Record status property.**</span></span> <span data-ttu-id="4c2ee-190">Somente quando a propriedade **Status do registro** é definida como **Bloqueado** será mantida uma nova versão do registro.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-190">Only when the **Record status** property is set to **Locked** is a new version of the record retained.</span></span> <span data-ttu-id="4c2ee-191">Essa alternância entre bloqueado e desbloqueado reduz o risco de manter versões e cópias desnecessárias do documento.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-191">This toggle of locked and unlocked reduces the risk of retaining unnecessary versions and copies of the document.</span></span>

  - <span data-ttu-id="4c2ee-192">**Ter os registros armazenados automaticamente em um repositório de registros in-loco, localizado no conjunto de sites.**</span><span class="sxs-lookup"><span data-stu-id="4c2ee-192">**Have the records automatically stored in an in-place records repository located within the site collection.**</span></span> <span data-ttu-id="4c2ee-193">Cada conjunto de sites no SharePoint e no OneDrive preserva o conteúdo em sua biblioteca de Retenção para Preservação.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-193">Each site collection in SharePoint and OneDrive preserves content in its Preservation Hold library.</span></span> <span data-ttu-id="4c2ee-194">As versões de registro são armazenadas na pasta Registros nesta biblioteca.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-194">Record versions are stored in the Records folder in this library.</span></span>

  - <span data-ttu-id="4c2ee-195">**Manter um documento perene que contenha todas as versões.**</span><span class="sxs-lookup"><span data-stu-id="4c2ee-195">**Maintain an evergreen document that contains all versions.**</span></span> <span data-ttu-id="4c2ee-196">Por padrão, cada documento do SharePoint e do OneDrive têm um histórico de versão disponível no menu do item.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-196">By default, each SharePoint and OneDrive document has a version history available on the item menu.</span></span> <span data-ttu-id="4c2ee-197">Nesse histórico de versão, você pode ver facilmente quais versões são registros e exibir esses documentos.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-197">In this version history, you can easily see which versions are records and view those documents.</span></span>

<span data-ttu-id="4c2ee-198">O controle de versão do registro está disponível automaticamente para qualquer documento que tenha um rótulo de retenção que marque o item como registro.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-198">Record versioning is automatically available for any document that has a retention label that marks the item as a record.</span></span> <span data-ttu-id="4c2ee-199">Quando um usuário exibe as propriedades do documento usando o painel de detalhes, eles podem alternar o **Status do registro** de **Bloqueado** para **Desbloqueado**.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-199">When a user views the document properties by using the details pane, they can toggle the **Record status** from **Locked** to **Unlocked**.</span></span> <span data-ttu-id="4c2ee-200">Essa ação cria um registro na pasta Registros na Biblioteca de Retenção para Preservação, onde reside pelo restante do período de retenção.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-200">This action creates a record in the Records folder in the Preservation Hold library, where it resides for the remainder of its retention period.</span></span> 

<span data-ttu-id="4c2ee-201">Enquanto o documento está desbloqueado, qualquer usuário com permissões de edição padrão pode editar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-201">While the document is unlocked, any user with standard edit permissions can edit the file.</span></span> <span data-ttu-id="4c2ee-202">No entanto, os usuários não podem excluir o arquivo, porque ele continua sendo um registro.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-202">However, users can't delete the file, because it's still a record.</span></span> <span data-ttu-id="4c2ee-203">Quando a edição estiver concluída, o usuário poderá alternar o **Status do registro** de **Desbloqueado** para **Bloqueado**, o que impede novas edições enquanto estiver nesse status.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-203">When editing is complete, a  user can then toggle the **Record status** from **Unlocked** to **Locked**, which prevents further edits while in this status.</span></span>
<br/><br/>

![Propriedade do status do registro no documento marcado como um registro](../media/recordversioning8.png)

### <a name="locking-and-unlocking-a-record"></a><span data-ttu-id="4c2ee-205">Bloqueando e desbloqueando um registro</span><span class="sxs-lookup"><span data-stu-id="4c2ee-205">Locking and unlocking a record</span></span>

<span data-ttu-id="4c2ee-206">Depois que um rótulo de retenção que marca o conteúdo como registro é aplicado a um documento, qualquer usuário com permissões de Contribuição ou com um nível de permissão mais restrito pode desbloquear um registro ou bloquear um registro desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-206">After a retention label that marks content as a record is applied to a document, any user with Contribute permissions or a narrower permission level can unlock a record or lock an unlocked record.</span></span>
<br/><br/>

![O status do registro mostra que o documento de registro está desbloqueado](../media/recordversioning9.png)

<span data-ttu-id="4c2ee-208">Quando um usuário desbloqueia um registro, as seguintes ações ocorrem:</span><span class="sxs-lookup"><span data-stu-id="4c2ee-208">When a user unlocks a record, the following actions occur:</span></span>

1. <span data-ttu-id="4c2ee-209">Se o conjunto de sites atual não tiver uma biblioteca de Retenção para Preservação, ela será criada.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-209">If the current site collection doesn't have a Preservation Hold library, one is created.</span></span>

2. <span data-ttu-id="4c2ee-210">Se a biblioteca de Retenção para Preservação não tiver uma pasta Registros, ela será criada.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-210">If the Preservation Hold library doesn't have a Records folder, one is created.</span></span>

3. <span data-ttu-id="4c2ee-211">Uma ação de **Copiar para** copia a versão mais recente do documento para a pasta Registros.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-211">A **Copy to** action copies the latest version of the document to the Records folder.</span></span> <span data-ttu-id="4c2ee-212">A ação **Copiar para** inclui apenas a versão mais recente e nenhuma das versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-212">The **Copy to** action includes only the latest version and no prior versions.</span></span> <span data-ttu-id="4c2ee-213">Este documento copiado agora é considerado uma versão de registro do documento e o nome do arquivo tem o formato: \[Versão GUID Título\#\]</span><span class="sxs-lookup"><span data-stu-id="4c2ee-213">This copied document is now considered a record version of the document, and its file name has the format: \[Title GUID Version\#\]</span></span>

4. <span data-ttu-id="4c2ee-214">A cópia criada na pasta Registros é adicionada ao histórico da versão do documento original, e esta versão mostra a palavra **Registro** no campo de comentários.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-214">The copy created in the Records folder is added to the version history of the original document, and this version shows the word **Record** in the comments field.</span></span>

5. <span data-ttu-id="4c2ee-215">O documento original é uma nova versão que pode ser editada, mas não excluída.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-215">The original document is a new version that can be edited, but not deleted.</span></span> <span data-ttu-id="4c2ee-216">A coluna da biblioteca de documentos **Item é um Registro** ainda mostra o valor **Sim** porque o documento continua sendo um registro, mesmo que agora possa ser editado.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-216">The document library column **Item is a Record** still shows the **Yes** value because the document is still a record, even if it can now be edited.</span></span>

<span data-ttu-id="4c2ee-217">Quando um usuário bloqueia um registro, o documento original não poderá ser editado novamente.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-217">When a user locks a record, the original document again can't be edited.</span></span> <span data-ttu-id="4c2ee-218">Mas é a ação de desbloquear um registro que copia uma versão para a pasta Registros na biblioteca de Retenção para Preservação.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-218">But it is the action of unlocking a record that copies a version to the Records folder in the Preservation Hold library.</span></span>

### <a name="record-versions"></a><span data-ttu-id="4c2ee-219">Versões de registro</span><span class="sxs-lookup"><span data-stu-id="4c2ee-219">Record versions</span></span>

<span data-ttu-id="4c2ee-220">Sempre que um usuário desbloqueia um registro, a versão mais recente é copiada para a pasta Registros na biblioteca de Retenção para Preservação, e essa versão contém o valor de **Registro** no campo **Comentários** do histórico da versão.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-220">Each time a user unlocks a record, the latest version is copied to the Records folder in the Preservation Hold library, and that version contains the value of **Record** in the **Comments** field of the version history.</span></span>
<br/><br/>

![Registro mostrado na biblioteca de Retenção para Preservação](../media/recordversioning10.png)

<span data-ttu-id="4c2ee-222">Para exibir o histórico da versão, escolha um documento na biblioteca de documentos e clique em **Histórico da Versão** no menu do item.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-222">To view the version history, select a document in the document library and then click **Version history** in the item menu.</span></span>

### <a name="where-records-are-stored"></a><span data-ttu-id="4c2ee-223">Onde os registros são armazenados</span><span class="sxs-lookup"><span data-stu-id="4c2ee-223">Where records are stored</span></span>

<span data-ttu-id="4c2ee-224">Os registros são armazenados na pasta Registros na biblioteca de Retenção para Preservação no site de nível superior do conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-224">Records are stored in the Records folder in the Preservation Hold library in the top-level site in the site collection.</span></span> <span data-ttu-id="4c2ee-225">Na barra de navegação à esquerda no site de nível superior, escolha **Conteúdos do site** \> **Biblioteca de Retenção para Preservação**.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-225">In the left navigation on the top-level site, choose **Site contents** \> **Preservation Hold Library**.</span></span>
<br/><br/>

![Biblioteca de Retenção para Preservação](../media/recordversioning11.png)

<br/><br/>

![A pasta Registros na biblioteca de Retenção para Preservação](../media/recordversioning12.png)

<span data-ttu-id="4c2ee-228">A biblioteca de Retenção para Preservação está visível somente para administradores de conjuntos de sites.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-228">The Preservation Hold library is visible only to site collection admins.</span></span> <span data-ttu-id="4c2ee-229">Além disso, a biblioteca de Retenção para Preservação não existe por padrão.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-229">Also, the Preservation Hold library doesn't exist by default.</span></span> <span data-ttu-id="4c2ee-230">Ela é criada apenas quando o conteúdo sujeito a um rótulo ou política de retenção é excluído pela primeira vez do conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-230">It's created only when content subject to a retention label or retention policy is deleted for the first time in the site collection.</span></span>

### <a name="searching-the-audit-log-for-record-versioning-events"></a><span data-ttu-id="4c2ee-231">Pesquisando o log de auditoria para eventos de controle de versão do registro</span><span class="sxs-lookup"><span data-stu-id="4c2ee-231">Searching the audit log for record versioning events</span></span>

<span data-ttu-id="4c2ee-232">As ações de bloqueio e desbloqueio de registros são registradas no log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-232">The actions of locking and unlocking records are logged in the audit log.</span></span> <span data-ttu-id="4c2ee-233">Você pode pesquisar pelas atividades específicas **Status do registro alterado para bloqueado** e **Status do registro alterado para desbloqueado**, que estão localizadas na seção **Atividades de arquivo e página** na lista suspensa de **Atividades** na página de **Pesquisa de log de auditoria** no centro de conformidade e segurança.</span><span class="sxs-lookup"><span data-stu-id="4c2ee-233">You can search for the specific activities **Changed record status to locked** and **Changed record status to unlocked**, which are located in the **File and page activities** section in the **Activities** dropdown list on the **Audit log search** page in the security and compliance center.</span></span>
<br/><br/>

![Pesquisar o log de auditoria para eventos de controle de versão do registro](../media/recordversioning13.png)

<span data-ttu-id="4c2ee-235">Para obter mais informações sobre a pesquisa desses eventos, confira a seção "Atividades de arquivo e página" em [Pesquisar o log de auditoria no Centro de Conformidade e Segurança](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span><span class="sxs-lookup"><span data-stu-id="4c2ee-235">For more information about searching for these events, see the "File and page activities" section in [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4c2ee-236">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="4c2ee-236">Next steps</span></span>

<span data-ttu-id="4c2ee-237">Se você ainda não tiver rótulos de retenção para usar o gerenciamento de registros, confira [Introdução aos rótulos de retenção e políticas de retenção](get-started-with-retention.md).</span><span class="sxs-lookup"><span data-stu-id="4c2ee-237">If you don't yet have retention labels to use for records management, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="4c2ee-238">Para saber mais sobre a disposição de registros, confira [Disposição de conteúdo](disposition.md).</span><span class="sxs-lookup"><span data-stu-id="4c2ee-238">To learn about disposition of records, see [Disposing of content](disposition.md).</span></span>
