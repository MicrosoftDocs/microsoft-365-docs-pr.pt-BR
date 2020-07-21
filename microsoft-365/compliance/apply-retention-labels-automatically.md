---
title: Aplicar automaticamente um rótulo de retenção para reter ou excluir conteúdo
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
description: Criar e publicar automaticamente os rótulos de retenção para que você possa aplicar automaticamente os rótulos para reter o que precisa e excluir o que não
ms.openlocfilehash: eb29a846f6a7352eec02683c70dad1b0a423bdfa
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45127560"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="c14f5-103">Aplicar automaticamente um rótulo de retenção para reter ou excluir conteúdo</span><span class="sxs-lookup"><span data-stu-id="c14f5-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="c14f5-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="c14f5-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="c14f5-105">Um dos recursos mais poderosos dos [rótulos de retenção](retention.md) é a capacidade de aplicá-los automaticamente ao conteúdo que corresponde a determinadas condições.</span><span class="sxs-lookup"><span data-stu-id="c14f5-105">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="c14f5-106">Nesse caso, as pessoas da sua organização não precisam aplicar os rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="c14f5-106">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="c14f5-107">O Microsoft 365 faz o trabalho para elas.</span><span class="sxs-lookup"><span data-stu-id="c14f5-107">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="c14f5-108">Os rótulos de retenção de aplicação automática são excelentes porque:</span><span class="sxs-lookup"><span data-stu-id="c14f5-108">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="c14f5-109">Você não precisa treinar os usuários com relação a todas as classificações.</span><span class="sxs-lookup"><span data-stu-id="c14f5-109">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="c14f5-110">Você não precisa depender dos usuários para classificar corretamente o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="c14f5-110">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="c14f5-111">Os usuários não precisam mais conhecer as políticas de governança de dados; assim podem se concentrar no próprio trabalho.</span><span class="sxs-lookup"><span data-stu-id="c14f5-111">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="c14f5-112">Você pode aplicar rótulos de retenção ao conteúdo automaticamente quando esse conteúdo contiver informações confidenciais, palavras-chave ou uma correspondência para [classificadores treináveis](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="c14f5-112">You can apply retention labels to content automatically when that content contains sensitive information, keywords, or a match for [trainable classifiers](classifier-getting-started-with.md).</span></span>
    
<span data-ttu-id="c14f5-113">Os processos para aplicar automaticamente um rótulo de retenção com base nessas condições:</span><span class="sxs-lookup"><span data-stu-id="c14f5-113">The processes to automatically apply a retention label based on these conditions:</span></span>

![Diagrama de funções e tarefas para aplicação automática de rótulos](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="c14f5-115">Use as instruções a seguir para as duas etapas de administrador.</span><span class="sxs-lookup"><span data-stu-id="c14f5-115">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="c14f5-116">As políticas automáticas usam o rotulamento do lado do serviço com condições para aplicar automaticamente os rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="c14f5-116">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="c14f5-117">Você também pode aplicar um rótulo de retenção automaticamente a uma política de rótulo ao fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c14f5-117">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="c14f5-118">Aplicar um rótulo de retenção padrão a uma biblioteca do Microsoft Office SharePoint Online, uma pasta ou um conjunto de documentos para que o conteúdo não rotulado no contêiner seja rotulado automaticamente</span><span class="sxs-lookup"><span data-stu-id="c14f5-118">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="c14f5-119">Aplicar automaticamente um rótulo de retenção ao email usando regras</span><span class="sxs-lookup"><span data-stu-id="c14f5-119">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="c14f5-120">Nesses cenários, confira [Criar e aplicar rótulos de retenção em aplicativos](create-apply-retention-labels.md).</span><span class="sxs-lookup"><span data-stu-id="c14f5-120">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c14f5-121">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="c14f5-121">Before you begin</span></span>

<span data-ttu-id="c14f5-122">O administrador global da sua organização tem permissões completas para criar e editar os rótulos de retenção e suas políticas.</span><span class="sxs-lookup"><span data-stu-id="c14f5-122">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="c14f5-123">Se você não estiver entrando como um administrador global, confira [Permissões necessárias para criar e gerenciar políticas e rótulos de retenção](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="c14f5-123">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="c14f5-124">Como aplicar automaticamente um rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="c14f5-124">How to auto-apply a retention label</span></span>

<span data-ttu-id="c14f5-125">Primeiro, crie seu rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="c14f5-125">First, create your retention label.</span></span> <span data-ttu-id="c14f5-126">Em seguida, crie uma política automática para aplicar esse rótulo.</span><span class="sxs-lookup"><span data-stu-id="c14f5-126">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="c14f5-127">Se você já tiver criado seu rótulo de retenção, vá para [Criar uma política automática](#step-2-create-an-auto-apply-policy).</span><span class="sxs-lookup"><span data-stu-id="c14f5-127">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="c14f5-128">As instruções de navegação dependem se você estiver usando o [gerenciamento de relatórios](records-management.md) ou não.</span><span class="sxs-lookup"><span data-stu-id="c14f5-128">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="c14f5-129">São fornecidas instruções para ambos os cenários.</span><span class="sxs-lookup"><span data-stu-id="c14f5-129">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="c14f5-130">Etapa 1: Criar uma política de retenção</span><span class="sxs-lookup"><span data-stu-id="c14f5-130">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="c14f5-131">No [Centro de conformidade do Microsoft 365 ](https://compliance.microsoft.com/), navegue até um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="c14f5-131">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="c14f5-132">Se você estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="c14f5-132">If you are using records management:</span></span>
        - <span data-ttu-id="c14f5-133">**Soluções** > **Gerenciamento de Registros** >  guia **Plano de Arquivos** > **+ Criar um Rótulo** > **Rótulo de Retenção**</span><span class="sxs-lookup"><span data-stu-id="c14f5-133">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="c14f5-134">Se você não estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="c14f5-134">If you are not using records management:</span></span>
       - <span data-ttu-id="c14f5-135">**Soluções** > **Governança de Informações** >  guia **Rótulos** > + **Criar um Rótulo**</span><span class="sxs-lookup"><span data-stu-id="c14f5-135">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="c14f5-136">Não vê a opção imediatamente?</span><span class="sxs-lookup"><span data-stu-id="c14f5-136">Don't immediately see your option?</span></span> <span data-ttu-id="c14f5-137">Primeiro, selecione **Mostrar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="c14f5-137">First select **Show all**.</span></span> 

2. <span data-ttu-id="c14f5-138">Siga as instruções do assistente.</span><span class="sxs-lookup"><span data-stu-id="c14f5-138">Follow the prompts in the wizard.</span></span> <span data-ttu-id="c14f5-139">Se você estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="c14f5-139">If you are using records management:</span></span>
    
    - <span data-ttu-id="c14f5-140">Para saber mais sobre os descritores de plano de arquivo, confira [Usar o plano de arquivo para gerenciar os rótulos de retenção](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="c14f5-140">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="c14f5-141">Para usar o rótulo de retenção para declarar conteúdo como um registro, ative a caixa de seleção **Usar rótulo para classificar o conteúdo como um "Registro"**.</span><span class="sxs-lookup"><span data-stu-id="c14f5-141">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

<span data-ttu-id="c14f5-142">Para editar um rótulo existente, selecione-o e, em seguida, selecione **Editar rótulo** para começar o mesmo assistente que permite alterar as descrições de rótulo e as [configurações qualificadas](#updating-retention-labels-and-their-policies) na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="c14f5-142">To edit an existing label, select it, and then select **Edit label** to start the same wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="c14f5-143">Como alternativa, selecione qualquer uma das opções **Editar** disponíveis para ir diretamente para a página relevante e fazer sua atualização.</span><span class="sxs-lookup"><span data-stu-id="c14f5-143">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="c14f5-144">Etapa 2: Criar uma política de aplicação automática</span><span class="sxs-lookup"><span data-stu-id="c14f5-144">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="c14f5-145">Ao criar uma política de aplicação automática, selecione um rótulo de retenção a ser aplicado automaticamente ao conteúdo com base nas condições que você especificar.</span><span class="sxs-lookup"><span data-stu-id="c14f5-145">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="c14f5-146">No [Centro de Conformidade do Microsoft 365 ](https://compliance.microsoft.com/), navegue até um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="c14f5-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="c14f5-147">Se você estiver usando o gerenciamento de registros: **Governança de Informações**:</span><span class="sxs-lookup"><span data-stu-id="c14f5-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="c14f5-148">**Soluções** > **Gerenciamento de Registros** >  guia **Políticas de Rótulo** > **Aplicar rótulo automaticamente**</span><span class="sxs-lookup"><span data-stu-id="c14f5-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="c14f5-149">Se você não estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="c14f5-149">If you are not using records management:</span></span>
        - <span data-ttu-id="c14f5-150">**Soluções** > **Governança de Informações** >  guia **Políticas de Rótulo** > **Aplicar rótulo automaticamente**</span><span class="sxs-lookup"><span data-stu-id="c14f5-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="c14f5-151">Não vê a opção imediatamente?</span><span class="sxs-lookup"><span data-stu-id="c14f5-151">Don't immediately see your option?</span></span> <span data-ttu-id="c14f5-152">Primeiro, selecione **Mostrar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="c14f5-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="c14f5-153">Siga as instruções do assistente.</span><span class="sxs-lookup"><span data-stu-id="c14f5-153">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="c14f5-154">Para saber mais sobre como configurar condições que aplicam automaticamente o rótulo de retenção, confira o [Configurar condições para a aplicação automática de rótulos de retenção](#configuring-conditions-for-auto-apply-retention-labels) nesta página.</span><span class="sxs-lookup"><span data-stu-id="c14f5-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="c14f5-155">Para obter informações sobre os locais suportados pelos rótulos de retenção, confira a seção[Rótulos e locais de retenção](retention.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="c14f5-155">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="c14f5-156">Para editar uma política de rótulo de aplicação automática existente, selecione-a e, em seguida, selecione **Editar política** para começar o mesmo assistente que permite alterar as descrições da política e as [configurações qualificadas](#updating-retention-labels-and-their-policies) na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="c14f5-156">To edit an existing auto-apply label policy, select it, and then select **Edit policy** to start the same wizard that lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="c14f5-157">Como alternativa, selecione qualquer uma das opções **Editar** para ir diretamente para a página relevante e fazer sua atualização.</span><span class="sxs-lookup"><span data-stu-id="c14f5-157">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>

### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="c14f5-158">Configurar condições para a aplicação automática de rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="c14f5-158">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="c14f5-159">Você pode aplicar os rótulos de retenção automaticamente ao conteúdo quando esse conteúdo apresentar:</span><span class="sxs-lookup"><span data-stu-id="c14f5-159">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="c14f5-160">Tipos específicos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="c14f5-160">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="c14f5-161">Palavras-chave específicas que correspondem a uma consulta criada por você</span><span class="sxs-lookup"><span data-stu-id="c14f5-161">Specific keywords that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="c14f5-162">Uma correspondência de classificadores treináveis</span><span class="sxs-lookup"><span data-stu-id="c14f5-162">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="c14f5-163">Aplicar automaticamente rótulos a conteúdo com tipos específicos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="c14f5-163">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="c14f5-164">Ao criar rótulos de retenção de aplicação automática para informações confidenciais, você vê a mesma lista de modelos de política que quando cria uma política de prevenção contra perda de dados (DLP).</span><span class="sxs-lookup"><span data-stu-id="c14f5-164">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="c14f5-165">Cada modelo de política é pré-configurado para procurar tipos específicos de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="c14f5-165">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="c14f5-166">Por exemplo, o modelo mostrado aqui procura os números do ITIN (Número de Identificação de Contribuinte Individual) dos EUA, SSN (CPF) e passaporte.</span><span class="sxs-lookup"><span data-stu-id="c14f5-166">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="c14f5-167">Para saber mais sobre DLP, confira [Visão geral das políticas de prevenção contra perda de dados](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c14f5-167">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![Modelos de política com tipos de informações confidenciais](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="c14f5-p112">Depois de selecionar um modelo de política, você pode adicionar ou remover quaisquer tipos de informações confidenciais, e pode alterar a contagem de instâncias e a precisão de correspondência. No exemplo mostrado aqui, um rótulo de retenção será aplicado automaticamente apenas quando:</span><span class="sxs-lookup"><span data-stu-id="c14f5-p112">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="c14f5-p113">O conteúdo tiver entre uma e nove instâncias de qualquer um destes três tipos de informações confidenciais. Você pode excluir o valor **max** para que mude para **any**.</span><span class="sxs-lookup"><span data-stu-id="c14f5-p113">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="c14f5-173">O tipo de informações confidenciais detectadas tiver uma precisão de correspondência (ou um nível de confiança) de pelo menos 75.</span><span class="sxs-lookup"><span data-stu-id="c14f5-173">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="c14f5-174">Muitos tipos de informações confidenciais são definidos com vários padrões, em que um padrão com maior precisão de correspondência requer mais evidências para ser encontrado (como palavras-chave, datas ou endereços), enquanto um padrão com precisão de correspondência inferior requer menos evidências.</span><span class="sxs-lookup"><span data-stu-id="c14f5-174">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="c14f5-175">Quanto menor for a precisão de correspondência **min**, mais fácil será que o conteúdo corresponda à condição.</span><span class="sxs-lookup"><span data-stu-id="c14f5-175">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="c14f5-176">Para saber mais sobre essas opções, confira [Como ajustar as regras para facilitar ou dificultar a correspondência](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="c14f5-176">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Opções para identificar tipos de informações confidenciais](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="c14f5-178">Aplicar rótulos automaticamente a conteúdos com palavras-chave ou propriedades pesquisáveis</span><span class="sxs-lookup"><span data-stu-id="c14f5-178">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="c14f5-p115">Você pode aplicar automaticamente os rótulos ao conteúdo que atenda a certas condições. As condições disponíveis agora dão suporte à aplicação de um rótulo a conteúdos que incluem palavras ou frases específicas, ou valores de propriedades pesquisáveis. Você pode refinar a consulta usando os operadores de pesquisa AND, OR e NOT.</span><span class="sxs-lookup"><span data-stu-id="c14f5-p115">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="c14f5-182">Para saber mais sobre sintaxe de consulta, confira:</span><span class="sxs-lookup"><span data-stu-id="c14f5-182">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="c14f5-183">Referência de sintaxe da Linguagem de Consulta de Palavra-chave (KQL)</span><span class="sxs-lookup"><span data-stu-id="c14f5-183">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="c14f5-p116">Rótulos baseados em consultas usam o índice de pesquisa para identificar conteúdos. Para saber mais sobre propriedades pesquisáveis válidas, confira:</span><span class="sxs-lookup"><span data-stu-id="c14f5-p116">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="c14f5-186">Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="c14f5-186">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="c14f5-187">Visão geral de propriedades rastreadas e gerenciadas no SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="c14f5-187">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="c14f5-188">Consultas de exemplos:</span><span class="sxs-lookup"><span data-stu-id="c14f5-188">Examples queries:</span></span>

- <span data-ttu-id="c14f5-189">Exchange</span><span class="sxs-lookup"><span data-stu-id="c14f5-189">Exchange</span></span>
    - <span data-ttu-id="c14f5-190">assunto:"Finanças trimestrais"</span><span class="sxs-lookup"><span data-stu-id="c14f5-190">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="c14f5-191">destinatários:garthf</span><span class="sxs-lookup"><span data-stu-id="c14f5-191">recipients:garthf</span></span><!--nolink--><span data-ttu-id="c14f5-192">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c14f5-192">@contoso.com</span></span>
- <span data-ttu-id="c14f5-193">SharePoint e OneDrive</span><span class="sxs-lookup"><span data-stu-id="c14f5-193">SharePoint and OneDrive</span></span>
    - <span data-ttu-id="c14f5-194">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="c14f5-194">contenttype:contract</span></span>
    - <span data-ttu-id="c14f5-195">site:https</span><span class="sxs-lookup"><span data-stu-id="c14f5-195">site:https</span></span><!--nolink--><span data-ttu-id="c14f5-196">://contoso.sharepoint.com/sites/teams/procurement E contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="c14f5-196">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![Editor de consultas](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="c14f5-198">Aplicar rótulos automaticamente ao conteúdo usando classificadores treináveis</span><span class="sxs-lookup"><span data-stu-id="c14f5-198">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="c14f5-199">Ao escolher a opção de um classificador treinado, você pode selecionar um dos classificadores internos ou um classificador personalizado.</span><span class="sxs-lookup"><span data-stu-id="c14f5-199">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="c14f5-200">Os classificadores internos incluem **Currículos**, **SourceCode**, **Assédio Direcionado**, **Profanação** e **Ameaças**:</span><span class="sxs-lookup"><span data-stu-id="c14f5-200">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Escolha classificador treinável](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="c14f5-202">Vamos substituir o classificador interno **Idioma Ofensivo** porque ele tem uma grande quantidade de falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="c14f5-202">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="c14f5-203">Não use esse classificador interno e se você estiver usando-o no momento, você deve migrar seus processos de negócios para fora dele.</span><span class="sxs-lookup"><span data-stu-id="c14f5-203">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="c14f5-204">É recomendável usar os classificadores internos **Assédio Direcionado**, **Profanidade**e **Ameaças**.</span><span class="sxs-lookup"><span data-stu-id="c14f5-204">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="c14f5-205">Para aplicar um rótulo automaticamente usando essa opção, as caixas de correio e sites do SharePoint Online devem ter pelo menos 10 MB de dados.</span><span class="sxs-lookup"><span data-stu-id="c14f5-205">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="c14f5-206">Para obter mais informações sobre os classificadores treináveis, confira [Introdução aos classificadores treináveis (visualização)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="c14f5-206">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="c14f5-207">Para um exemplo de configuração, consulte [Como preparar e usar um classificador interno](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span><span class="sxs-lookup"><span data-stu-id="c14f5-207">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="c14f5-208">Quanto tempo demora para os rótulos de retenção entrarem em vigor</span><span class="sxs-lookup"><span data-stu-id="c14f5-208">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="c14f5-209">Quando você aplica rótulos de retenção automaticamente, pode levar até sete dias para que os rótulos de retenção sejam aplicados a todo o conteúdo existente que corresponde às condições.</span><span class="sxs-lookup"><span data-stu-id="c14f5-209">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Diagrama de quando a aplicação automática de rótulos entra em vigor](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="c14f5-211">Atualizar os rótulos de retenção e suas políticas</span><span class="sxs-lookup"><span data-stu-id="c14f5-211">Updating retention labels and their policies</span></span>

<span data-ttu-id="c14f5-212">Se você editar um rótulo de retenção ou política de aplicação automática e o rótulo de retenção já estiver aplicado ao conteúdo, as configurações atualizadas serão aplicadas automaticamente a esse conteúdo, além do conteúdo recentemente rotulado.</span><span class="sxs-lookup"><span data-stu-id="c14f5-212">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="c14f5-213">Algumas configurações não podem ser alteradas depois que o rótulo ou política é criado e salvo, que incluem:</span><span class="sxs-lookup"><span data-stu-id="c14f5-213">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="c14f5-214">As configurações de retenção, exceto o período de retenção, a menos que você tenha configurado o rótulo para reter ou excluir o conteúdo com base em quando ele foi criado.</span><span class="sxs-lookup"><span data-stu-id="c14f5-214">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="c14f5-215">A opção para classificar como um registro.</span><span class="sxs-lookup"><span data-stu-id="c14f5-215">The option to classify as a record.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c14f5-216">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="c14f5-216">Next steps</span></span>

<span data-ttu-id="c14f5-217">Considere o uso de rótulos de retenção com outra forma de automação, [retenção orientada por eventos](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="c14f5-217">Consider using retention labels with another form of automation, [event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="c14f5-218">Quando você usa essa configuração, o início da retenção é acionado por um evento identificado por você.</span><span class="sxs-lookup"><span data-stu-id="c14f5-218">When you use this configuration, the start of retention is triggered by an event that you identify.</span></span> <span data-ttu-id="c14f5-219">Você pode usar a retenção orientada por eventos com uma política de aplicação automática ou uma política de rótulo.</span><span class="sxs-lookup"><span data-stu-id="c14f5-219">You can use event-driven retention with an auto-policy or a label policy.</span></span>

<span data-ttu-id="c14f5-220">Confira [Gerenciar o ciclo de vida dos documentos do SharePoint com rótulos de retenção](auto-apply-retention-labels-scenario.md) para obter um cenário detalhado sobre como usar as propriedades gerenciadas no SharePoint para aplicar automaticamente os rótulos de retenção e implementar a retenção voltada para o evento.</span><span class="sxs-lookup"><span data-stu-id="c14f5-220">See [Manage the lifecycle of SharePoint documents with retention labels](auto-apply-retention-labels-scenario.md) for a detailed scenario about using managed properties in SharePoint to auto-apply retention labels and implement event-driven retention.</span></span>