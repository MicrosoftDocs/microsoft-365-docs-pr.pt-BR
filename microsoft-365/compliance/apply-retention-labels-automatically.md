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
ms.openlocfilehash: 088a521089d34e74865c94b3cd147b02f8d812cb
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47816946"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a><span data-ttu-id="3acf4-103">Aplicar automaticamente um rótulo de retenção para reter ou excluir conteúdo</span><span class="sxs-lookup"><span data-stu-id="3acf4-103">Automatically apply a retention label to retain or delete content</span></span>

><span data-ttu-id="3acf4-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="3acf4-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="3acf4-105">Um dos recursos mais poderosos dos [rótulos de retenção](retention.md) é a capacidade de aplicá-los automaticamente ao conteúdo que corresponde a determinadas condições.</span><span class="sxs-lookup"><span data-stu-id="3acf4-105">One of the most powerful features of [retention labels](retention.md) is the ability to apply them automatically to content that matches specified conditions.</span></span> <span data-ttu-id="3acf4-106">Nesse caso, as pessoas da sua organização não precisam aplicar os rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="3acf4-106">In this case, people in your organization don't need to apply the retention labels.</span></span> <span data-ttu-id="3acf4-107">O Microsoft 365 faz o trabalho para elas.</span><span class="sxs-lookup"><span data-stu-id="3acf4-107">Microsoft 365 does the work for them.</span></span>
  
<span data-ttu-id="3acf4-108">Os rótulos de retenção de aplicação automática são excelentes porque:</span><span class="sxs-lookup"><span data-stu-id="3acf4-108">Auto-applying retention labels are powerful because:</span></span>
  
- <span data-ttu-id="3acf4-109">Você não precisa treinar os usuários com relação a todas as classificações.</span><span class="sxs-lookup"><span data-stu-id="3acf4-109">You don't need to train your users on all of your classifications.</span></span>
    
- <span data-ttu-id="3acf4-110">Você não precisa depender dos usuários para classificar corretamente o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="3acf4-110">You don't need to rely on users to classify all content correctly.</span></span>
    
- <span data-ttu-id="3acf4-111">Os usuários não precisam mais conhecer as políticas de governança de dados; assim podem se concentrar no próprio trabalho.</span><span class="sxs-lookup"><span data-stu-id="3acf4-111">Users no longer need to know about data governance policies - they can focus on their work.</span></span>
    
<span data-ttu-id="3acf4-112">Você pode aplicar rótulos de retenção ao conteúdo automaticamente quando esse conteúdo contiver informações confidenciais, palavras-chave, propriedades pesquisáveis ou uma correspondência para [classificadores treináveis](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="3acf4-112">You can apply retention labels to content automatically when that content contains sensitive information, keywords or searchable properties, or a match for [trainable classifiers](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="3acf4-113">Os processos para aplicar automaticamente um rótulo de retenção com base nessas condições:</span><span class="sxs-lookup"><span data-stu-id="3acf4-113">The processes to automatically apply a retention label based on these conditions:</span></span>

![Diagrama de funções e tarefas para aplicação automática de rótulos](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

<span data-ttu-id="3acf4-115">Use as instruções a seguir para as duas etapas de administrador.</span><span class="sxs-lookup"><span data-stu-id="3acf4-115">Use the following instructions for the two admin steps.</span></span>

> [!NOTE]
> <span data-ttu-id="3acf4-116">As políticas automáticas usam o rotulamento do lado do serviço com condições para aplicar automaticamente os rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="3acf4-116">Auto-policies use service-side labeling with conditions to automatically apply retention labels.</span></span> <span data-ttu-id="3acf4-117">Você também pode aplicar um rótulo de retenção automaticamente a uma política de rótulo ao fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="3acf4-117">You can also automatically apply a retention label with a label policy when you do the following:</span></span> 
>
> - <span data-ttu-id="3acf4-118">Aplicar um rótulo de retenção padrão a uma biblioteca do Microsoft Office SharePoint Online, uma pasta ou um conjunto de documentos para que o conteúdo não rotulado no contêiner seja rotulado automaticamente</span><span class="sxs-lookup"><span data-stu-id="3acf4-118">Apply a default retention label to a SharePoint library, folder, or document set so that unlabeled content in that container is automatically labeled</span></span>
>- <span data-ttu-id="3acf4-119">Aplicar automaticamente um rótulo de retenção ao email usando regras</span><span class="sxs-lookup"><span data-stu-id="3acf4-119">Automatically applying a retention label to email by using rules</span></span>
>
> <span data-ttu-id="3acf4-120">Nesses cenários, confira [Criar e aplicar rótulos de retenção em aplicativos](create-apply-retention-labels.md).</span><span class="sxs-lookup"><span data-stu-id="3acf4-120">For these scenarios, see [Create and apply retention labels in apps](create-apply-retention-labels.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="3acf4-121">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="3acf4-121">Before you begin</span></span>

<span data-ttu-id="3acf4-122">O administrador global da sua organização tem permissões completas para criar e editar os rótulos de retenção e suas políticas.</span><span class="sxs-lookup"><span data-stu-id="3acf4-122">The global admin for your organization has full permissions to create and edit retention labels and their policies.</span></span> <span data-ttu-id="3acf4-123">Se você não estiver entrando como um administrador global, confira [Permissões necessárias para criar e gerenciar políticas e rótulos de retenção](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="3acf4-123">If you aren't signing in as a global admin, see [Permissions required to create and manage retention policies and retention labels](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).</span></span>

## <a name="how-to-auto-apply-a-retention-label"></a><span data-ttu-id="3acf4-124">Como aplicar automaticamente um rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="3acf4-124">How to auto-apply a retention label</span></span>

<span data-ttu-id="3acf4-125">Primeiro, crie seu rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="3acf4-125">First, create your retention label.</span></span> <span data-ttu-id="3acf4-126">Em seguida, crie uma política automática para aplicar esse rótulo.</span><span class="sxs-lookup"><span data-stu-id="3acf4-126">Then create an auto-policy to apply that label.</span></span> <span data-ttu-id="3acf4-127">Se você já tiver criado seu rótulo de retenção, vá para [Criar uma política automática](#step-2-create-an-auto-apply-policy).</span><span class="sxs-lookup"><span data-stu-id="3acf4-127">If you have already created your retention label, skip to [creating an auto-policy](#step-2-create-an-auto-apply-policy).</span></span>

<span data-ttu-id="3acf4-128">As instruções de navegação dependem se você estiver usando o [gerenciamento de relatórios](records-management.md) ou não.</span><span class="sxs-lookup"><span data-stu-id="3acf4-128">Navigation instructions depend on whether you're using [records management](records-management.md) or not.</span></span> <span data-ttu-id="3acf4-129">São fornecidas instruções para ambos os cenários.</span><span class="sxs-lookup"><span data-stu-id="3acf4-129">Instructions are provided for both scenarios.</span></span>

### <a name="step-1-create-a-retention-label"></a><span data-ttu-id="3acf4-130">Etapa 1: Criar uma política de retenção</span><span class="sxs-lookup"><span data-stu-id="3acf4-130">Step 1: Create a retention label</span></span>

1. <span data-ttu-id="3acf4-131">No [Centro de conformidade do Microsoft 365 ](https://compliance.microsoft.com/), navegue até um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="3acf4-131">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="3acf4-132">Se você estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="3acf4-132">If you are using records management:</span></span>
        - <span data-ttu-id="3acf4-133">**Soluções** > **Gerenciamento de Registros** >  guia **Plano de Arquivos** > **+ Criar um Rótulo** > **Rótulo de Retenção**</span><span class="sxs-lookup"><span data-stu-id="3acf4-133">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="3acf4-134">Se você não estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="3acf4-134">If you are not using records management:</span></span>
       - <span data-ttu-id="3acf4-135">**Soluções** > **Governança de Informações** >  guia **Rótulos** > + **Criar um Rótulo**</span><span class="sxs-lookup"><span data-stu-id="3acf4-135">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="3acf4-136">Não vê a opção imediatamente?</span><span class="sxs-lookup"><span data-stu-id="3acf4-136">Don't immediately see your option?</span></span> <span data-ttu-id="3acf4-137">Primeiro, selecione **Mostrar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="3acf4-137">First select **Show all**.</span></span> 

2. <span data-ttu-id="3acf4-138">Siga as instruções do assistente.</span><span class="sxs-lookup"><span data-stu-id="3acf4-138">Follow the prompts in the wizard.</span></span> <span data-ttu-id="3acf4-139">Se você estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="3acf4-139">If you are using records management:</span></span>
    
    - <span data-ttu-id="3acf4-140">Para saber mais sobre os descritores de plano de arquivo, confira [Usar o plano de arquivo para gerenciar os rótulos de retenção](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="3acf4-140">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="3acf4-141">Para usar o rótulo de retenção para declarar um [registro](records-management.md#records), habilite a opção **Marcar itens como um registro**.</span><span class="sxs-lookup"><span data-stu-id="3acf4-141">To use the retention label to declare a [record](records-management.md#records), enable the option **Mark items as a record**.</span></span>

3. <span data-ttu-id="3acf4-142">Depois de criar o rótulo, você verá as opções para publicar a etiqueta, aplicar automaticamente a etiqueta, ou apenas salvar o rótulo: Selecione **Aplicar o rótulo automaticamente a um tipo específico de conteúdo** e, em seguida, selecione **concluído** para iniciar o assistente criar rotulagem automática, que o levará diretamente para a etapa 2 do procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="3acf4-142">After you have created the label and you see the options to publish the label, auto-apply the label, or just save the label: Select **Auto-apply this label to a specific type of content**, and then select **Done** to start the Create auto-labeling wizard that takes you directly to step 2 in the following procedure.</span></span>

<span data-ttu-id="3acf4-143">Para editar um rótulo existente, selecione-o e, em seguida, selecione **Editar rótulo** para iniciar o Assistente do editor de retenção que permite alterar as descrições de rótulo e quaisquer [configurações qualificadas](#updating-retention-labels-and-their-policies) na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="3acf4-143">To edit an existing label, select it, and then select the **Edit label** option to start the Edit retention wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="step-2-create-an-auto-apply-policy"></a><span data-ttu-id="3acf4-144">Etapa 2: Criar uma política de aplicação automática</span><span class="sxs-lookup"><span data-stu-id="3acf4-144">Step 2: Create an auto-apply policy</span></span>

<span data-ttu-id="3acf4-145">Ao criar uma política de aplicação automática, selecione um rótulo de retenção a ser aplicado automaticamente ao conteúdo com base nas condições que você especificar.</span><span class="sxs-lookup"><span data-stu-id="3acf4-145">When you create an auto-apply policy, you select a retention label to automatically apply to content, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="3acf4-146">No [Centro de Conformidade do Microsoft 365 ](https://compliance.microsoft.com/), navegue até um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="3acf4-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="3acf4-147">Se você estiver usando o gerenciamento de registros: **Governança de Informações**:</span><span class="sxs-lookup"><span data-stu-id="3acf4-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="3acf4-148">**Soluções** > **Gerenciamento de Registros** guia  > **Políticas de Rótulo** > **Aplicar rótulo automaticamente**</span><span class="sxs-lookup"><span data-stu-id="3acf4-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    - <span data-ttu-id="3acf4-149">Se você não estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="3acf4-149">If you are not using records management:</span></span>
        - <span data-ttu-id="3acf4-150">**Soluções** > **Governança de Informações** >  guia **Políticas de Rótulo** > **Aplicar rótulo automaticamente**</span><span class="sxs-lookup"><span data-stu-id="3acf4-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply a label**</span></span>
    
    <span data-ttu-id="3acf4-151">Não vê a opção imediatamente?</span><span class="sxs-lookup"><span data-stu-id="3acf4-151">Don't immediately see your option?</span></span> <span data-ttu-id="3acf4-152">Primeiro, selecione **Mostrar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="3acf4-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="3acf4-153">Siga os avisos no assistente Criar rotulação automática.</span><span class="sxs-lookup"><span data-stu-id="3acf4-153">Follow the prompts in the Create auto-labeling wizard.</span></span>
    
    <span data-ttu-id="3acf4-154">Para saber mais sobre como configurar condições que aplicam automaticamente o rótulo de retenção, confira o [Configurar condições para a aplicação automática de rótulos de retenção](#configuring-conditions-for-auto-apply-retention-labels) nesta página.</span><span class="sxs-lookup"><span data-stu-id="3acf4-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="3acf4-155">Para obter informações sobre os locais suportados pelos rótulos de retenção, confira a seção[Rótulos e locais de retenção](retention.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="3acf4-155">For information about the locations supported by retention labels, see the [Retention labels and locations](retention.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="3acf4-156">Para editar uma política de aplicação automática existente, selecione-a para iniciar o assistente para editar política de retenção que permite alterar o rótulo de retenção selecionado e quaisquer [configurações elegíveis](#updating-retention-labels-and-their-policies) da etapa 2.</span><span class="sxs-lookup"><span data-stu-id="3acf4-156">To edit an existing auto-apply policy, select it to start the Edit retention policy wizard that lets you change the selected retention label and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span>


### <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="3acf4-157">Configurar condições para a aplicação automática de rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="3acf4-157">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="3acf4-158">Você pode aplicar os rótulos de retenção automaticamente ao conteúdo quando esse conteúdo apresentar:</span><span class="sxs-lookup"><span data-stu-id="3acf4-158">You can apply retention labels to content automatically when that content contains:</span></span>

- [<span data-ttu-id="3acf4-159">Tipos específicos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="3acf4-159">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [<span data-ttu-id="3acf4-160">Palavras-chave específicas ou Propriedades pesquisáveis que correspondem a uma consulta criada</span><span class="sxs-lookup"><span data-stu-id="3acf4-160">Specific keywords or searchable properties that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="3acf4-161">Uma correspondência de classificadores treináveis</span><span class="sxs-lookup"><span data-stu-id="3acf4-161">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="3acf4-162">Aplicar automaticamente rótulos a conteúdo com tipos específicos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="3acf4-162">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="3acf4-163">Ao criar rótulos de retenção de aplicação automática para informações confidenciais, você vê a mesma lista de modelos de política que quando cria uma política de prevenção contra perda de dados (DLP).</span><span class="sxs-lookup"><span data-stu-id="3acf4-163">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="3acf4-164">Cada modelo de política é pré-configurado para procurar tipos específicos de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="3acf4-164">Each template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="3acf4-165">Por exemplo, o modelo mostrado aqui procura os números dos EUA ITIN, SSN e passaporte da categoria **Privacidade** e **Modelo de dados de Informações de Identificação Pessoal (PII) dos EUA**:</span><span class="sxs-lookup"><span data-stu-id="3acf4-165">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers from the **Privacy** category, and **U.S Personally Identifiable Information (PII) Data template**:</span></span>

![Modelos de política com tipos de informações confidenciais](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

<span data-ttu-id="3acf4-167">Para obter mais informações sobre os tipos de informações confidenciais, confira [Definições da entidade de tipo de informações confidenciais](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="3acf4-167">To learn more about the sensitivity information types, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>

<span data-ttu-id="3acf4-168">Após selecionar um modelo de política, você pode adicionar ou remover quaisquer tipos de informações confidenciais e pode alterar a contagem de instâncias e a precisão da correspondência.</span><span class="sxs-lookup"><span data-stu-id="3acf4-168">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy.</span></span> <span data-ttu-id="3acf4-169">Na captura de tela de exemplo mostrada a seguir, um rótulo de retenção será automaticamente aplicado apenas quando:</span><span class="sxs-lookup"><span data-stu-id="3acf4-169">In the example screenshot shown next, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="3acf4-170">O tipo de informações confidenciais detectadas tiver uma precisão de correspondência (ou um nível de confiança) de pelo menos 75.</span><span class="sxs-lookup"><span data-stu-id="3acf4-170">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75.</span></span> <span data-ttu-id="3acf4-171">Muitos tipos de informações confidenciais são definidos com vários padrões, em que um padrão com maior precisão de correspondência requer mais evidências para ser encontrado (como palavras-chave, datas ou endereços), enquanto um padrão com precisão de correspondência inferior requer menos evidências.</span><span class="sxs-lookup"><span data-stu-id="3acf4-171">Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence.</span></span> <span data-ttu-id="3acf4-172">Quanto menor for a precisão de correspondência **min**, mais fácil será que o conteúdo corresponda à condição.</span><span class="sxs-lookup"><span data-stu-id="3acf4-172">The lower the **min** match accuracy, the easier it is for content to match the condition.</span></span>

- <span data-ttu-id="3acf4-173">O conteúdo contém entre uma e nove instâncias de qualquer um destes três tipos de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="3acf4-173">The content contains between 1 and 9 instances of any of these three sensitive information types.</span></span> <span data-ttu-id="3acf4-174">Você pode excluir o valor **a** para que ele se transforme em **Qualquer**.</span><span class="sxs-lookup"><span data-stu-id="3acf4-174">You can delete the **to** value so that it changes to **Any**.</span></span>

<span data-ttu-id="3acf4-175">Para obter mais informações sobre essas opções, confira as diretrizes a seguir na documentação da DLP [Regras de ajuste para torná-las mais fáceis ou difíceis de corresponder aos](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="3acf4-175">For more information about these options, see the following guidance from the DLP documentation [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Opções para identificar tipos de informações confidenciais](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="3acf4-177">Aplicar rótulos automaticamente a conteúdos com palavras-chave ou propriedades pesquisáveis</span><span class="sxs-lookup"><span data-stu-id="3acf4-177">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="3acf4-p113">Você pode aplicar automaticamente os rótulos ao conteúdo usando uma consulta que inclui palavras ou frases específicas, ou valores de propriedades pesquisáveis. Você pode refinar a consulta usando os operadores de pesquisa AND, OR e NOT.</span><span class="sxs-lookup"><span data-stu-id="3acf4-p113">You can auto-apply labels to content by using a query that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators such as AND, OR, and NOT.</span></span>

![Editor de consultas](../media/new-retention-query-editor.png)

<span data-ttu-id="3acf4-181">Para obter mais informações sobre a sintaxe de consulta que usa a Linguagem de Consulta de Palavra-chave (KQL), consulte [Referência de sintaxe da Linguagem de Consulta de Palavra-chave (KQL) no MSDN](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span><span class="sxs-lookup"><span data-stu-id="3acf4-181">For more information about the query syntax that uses Keyword Query Language (KQL), see [Keyword Query Language (KQL) syntax reference](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).</span></span>

<span data-ttu-id="3acf4-182">Observe que os rótulos baseados em consulta usam o índice de pesquisa para identificar conteúdo.</span><span class="sxs-lookup"><span data-stu-id="3acf4-182">Query-based labels use the search index to identify content.</span></span> <span data-ttu-id="3acf4-183">Para obter mais informações sobre as propriedades pesquisáveis que você pode usar, consulte:</span><span class="sxs-lookup"><span data-stu-id="3acf4-183">For more information about the searchable properties that you can use, see:</span></span>

- [<span data-ttu-id="3acf4-184">Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="3acf4-184">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="3acf4-185">Visão geral de propriedades rastreadas e gerenciadas no SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="3acf4-185">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

> [!NOTE]
> <span data-ttu-id="3acf4-186">Embora as propriedades gerenciadas do SharePoint ofereçam suporte a aliases, não os use quando configurar seus rótulos de retenção.</span><span class="sxs-lookup"><span data-stu-id="3acf4-186">Although SharePoint managed properties support aliases, don't use these when you configure your retention labels.</span></span> <span data-ttu-id="3acf4-187">Especifique sempre o nome real da propriedade gerenciada, por exemplo, RefinableString01.</span><span class="sxs-lookup"><span data-stu-id="3acf4-187">Always specify the actual name of the managed property, for example, "RefinableString01".</span></span>

<span data-ttu-id="3acf4-188">Consultas de exemplos:</span><span class="sxs-lookup"><span data-stu-id="3acf4-188">Examples queries:</span></span>

| <span data-ttu-id="3acf4-189">Workload</span><span class="sxs-lookup"><span data-stu-id="3acf4-189">Workload</span></span> | <span data-ttu-id="3acf4-190">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3acf4-190">Example</span></span> |
|:-----|:-----|
|<span data-ttu-id="3acf4-191">Exchange</span><span class="sxs-lookup"><span data-stu-id="3acf4-191">Exchange</span></span>   | `subject:"Quarterly Financials"` |
|<span data-ttu-id="3acf4-192">Exchange</span><span class="sxs-lookup"><span data-stu-id="3acf4-192">Exchange</span></span>   | `recipients:garthf@contoso.com` |
|<span data-ttu-id="3acf4-193">Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3acf4-193">SharePoint</span></span> | `contenttype:contract` |
|<span data-ttu-id="3acf4-194">Microsoft Office SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3acf4-194">SharePoint</span></span> | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract`|

#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="3acf4-195">Aplicar rótulos automaticamente ao conteúdo usando classificadores treináveis</span><span class="sxs-lookup"><span data-stu-id="3acf4-195">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="3acf4-196">Ao escolher a opção de um classificador treinado, você pode selecionar um dos classificadores internos ou um classificador personalizado.</span><span class="sxs-lookup"><span data-stu-id="3acf4-196">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="3acf4-197">Os classificadores internos incluem **Currículos**, **SourceCode**, **Assédio Direcionado**, **Profanação** e **Ameaças**:</span><span class="sxs-lookup"><span data-stu-id="3acf4-197">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Escolha classificador treinável](../media/retention-label-classifers.png)

> [!CAUTION]
> <span data-ttu-id="3acf4-199">Vamos substituir o classificador interno **Idioma Ofensivo** porque ele tem uma grande quantidade de falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="3acf4-199">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="3acf4-200">Não use esse classificador interno e se você estiver usando-o no momento, você deve migrar seus processos de negócios para fora dele.</span><span class="sxs-lookup"><span data-stu-id="3acf4-200">Don't use this built-in classifier and if you are currently using it, you should move your business processes off it.</span></span> <span data-ttu-id="3acf4-201">É recomendável usar os classificadores internos **Assédio Direcionado**, **Profanidade**e **Ameaças**.</span><span class="sxs-lookup"><span data-stu-id="3acf4-201">We recommend using the **Targeted Harassment**, **Profanity**, and **Threat** built-in classifiers instead.</span></span>

<span data-ttu-id="3acf4-202">Para aplicar um rótulo automaticamente usando essa opção, os sites e as caixas de correio do SharePoint devem conter pelo menos 10 MB de dados.</span><span class="sxs-lookup"><span data-stu-id="3acf4-202">To automatically apply a label by using this option, SharePoint sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="3acf4-203">Para obter mais informações sobre os classificadores treináveis, confira [Introdução aos classificadores treináveis (visualização)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="3acf4-203">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="3acf4-204">Para um exemplo de configuração, consulte [Como preparar e usar um classificador interno](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span><span class="sxs-lookup"><span data-stu-id="3acf4-204">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="3acf4-205">Quanto tempo demora para os rótulos de retenção entrarem em vigor</span><span class="sxs-lookup"><span data-stu-id="3acf4-205">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="3acf4-206">Quando você aplica rótulos de retenção automaticamente, pode levar até sete dias para que os rótulos de retenção sejam aplicados a todo o conteúdo existente que corresponde às condições.</span><span class="sxs-lookup"><span data-stu-id="3acf4-206">When you auto-apply retention labels, it can take up to seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Diagrama de quando a aplicação automática de rótulos entra em vigor](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="3acf4-208">Atualizar os rótulos de retenção e suas políticas</span><span class="sxs-lookup"><span data-stu-id="3acf4-208">Updating retention labels and their policies</span></span>

<span data-ttu-id="3acf4-209">Se você editar um rótulo de retenção ou política de aplicação automática e o rótulo de retenção já estiver aplicado ao conteúdo, as configurações atualizadas serão aplicadas automaticamente a esse conteúdo, além do conteúdo recentemente rotulado.</span><span class="sxs-lookup"><span data-stu-id="3acf4-209">When you edit a retention label or auto-apply policy, and the retention label is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="3acf4-210">Algumas configurações não podem ser alteradas depois que o rótulo ou política é criado e salvo, que incluem:</span><span class="sxs-lookup"><span data-stu-id="3acf4-210">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="3acf4-211">As configurações de retenção, exceto o período de retenção, a menos que você tenha configurado o rótulo para reter ou excluir o conteúdo com base em quando ele foi criado.</span><span class="sxs-lookup"><span data-stu-id="3acf4-211">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="3acf4-212">A opção para marcar os itens como um registro.</span><span class="sxs-lookup"><span data-stu-id="3acf4-212">The option to mark items as a record.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3acf4-213">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="3acf4-213">Next steps</span></span>

<span data-ttu-id="3acf4-214">Confira [Usar rótulos de retenção para gerenciar o ciclo de vida dos documentos armazenados no SharePoint](auto-apply-retention-labels-scenario.md) para um exemplo de cenário que usa uma política de aplicação automática com propriedades gerenciadas no SharePoint, e retenção baseada em evento para iniciar o período de retenção.</span><span class="sxs-lookup"><span data-stu-id="3acf4-214">See [Use retention labels to manage the lifecycle of documents stored in SharePoint](auto-apply-retention-labels-scenario.md) for an example scenario that uses an auto-apply policy with managed properties in SharePoint, and event-based retention to start the retention period.</span></span>
