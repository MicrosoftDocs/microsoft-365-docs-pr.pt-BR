---
title: Criar, publicar ou aplicar automaticamente rótulos de retenção
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
description: Instruções para criar, publicar e aplicar automaticamente rótulos de retenção para reter o que você precisa, excluir o que não é necessário e declarar um item como um registro no seu ambiente do Office 365.
ms.openlocfilehash: a3ba321c9eae91bf701646a45271d3edcbc8dccc
ms.sourcegitcommit: c696852da06d057dba4f5147bbf46521910de3ab
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44545953"
---
# <a name="create-publish-and-auto-apply-retention-labels"></a><span data-ttu-id="375c8-103">Criar, publicar ou aplicar automaticamente rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="375c8-103">Create, publish, and auto-apply retention labels</span></span>

><span data-ttu-id="375c8-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="375c8-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="375c8-105">Use as informações a seguir para ajudá-lo a criar [rótulos de retenção](labels.md) e, em seguida, aplicá-los automaticamente a documentos e emails, ou publicá-los para que os usuários possam aplicá-los manualmente.</span><span class="sxs-lookup"><span data-stu-id="375c8-105">Use the following information to help you create [retention labels](labels.md), and then automatically apply them to documents and emails, or publish them so that users can manually apply them.</span></span>

<span data-ttu-id="375c8-106">Os rótulos de retenção ajudam a reter o que você precisa e excluir o que não é necessário.</span><span class="sxs-lookup"><span data-stu-id="375c8-106">Retention labels help you retain what you need and delete what you don't.</span></span> <span data-ttu-id="375c8-107">Eles também são usados para declarar um item como um registro como parte de uma solução de [gerenciamento de registros](records-management.md) para seus dados do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="375c8-107">They are also used to declare an item as a record as part of a [records management](records-management.md) solution for your Microsoft 365 data.</span></span>

<span data-ttu-id="375c8-108">Onde você cria e configura seus rótulos de retenção depende se você está usando o gerenciamento de registros ou não.</span><span class="sxs-lookup"><span data-stu-id="375c8-108">Where you create and configure your retention labels depend on whether you're using records management or not.</span></span> <span data-ttu-id="375c8-109">São fornecidas instruções para ambos os cenários.</span><span class="sxs-lookup"><span data-stu-id="375c8-109">Instructions are provided for both scenarios.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="375c8-110">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="375c8-110">Before you begin</span></span>

<span data-ttu-id="375c8-111">Os membros da sua equipe de conformidade que criarão rótulos de retenção precisam de permissões para o Centro de Conformidade e Segurança do &amp;.</span><span class="sxs-lookup"><span data-stu-id="375c8-111">Members of your compliance team who will create retention labels need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="375c8-112">Por padrão, o administrador do locatário tem acesso a esse local e pode conceder, aos agentes de conformidade e a outras pessoas, acesso ao Centro de Conformidade e Segurança do &amp;, sem lhes dar todas as permissões de um administrador de locatários. Para fazer isso, recomendamos que você acesse a página **Permissões** do Centro de Conformidade e Segurança do &amp;, edite o grupo de função **Administrador de Conformidade** e adicione membros a esse grupo de função.</span><span class="sxs-lookup"><span data-stu-id="375c8-112">By default, your tenant admin has access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a tenant admin. To do this, we recommend that you go to the **Permissions** page of the Security &amp; Compliance Center, edit the **Compliance Administrator** role group, and add members to that role group.</span></span> 
  
<span data-ttu-id="375c8-113">Para saber mais, consulte [Dar aos usuários acesso ao &amp;Centro de Conformidade](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md) e Segurança do Office 365.</span><span class="sxs-lookup"><span data-stu-id="375c8-113">For more information, see [Give users access to the Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="375c8-p104">Essas permissões só serão necessárias para criar e aplicar rótulos de retenção. A imposição da política não exige acesso ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="375c8-p104">These permissions are required only to create and apply retention labels and a label policy. Policy enforcement does not require access to the content.</span></span>

## <a name="create-and-configure-retention-labels"></a><span data-ttu-id="375c8-116">Criar e configurar rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="375c8-116">Create and configure retention labels</span></span>

1. <span data-ttu-id="375c8-117">No [Centro de Conformidade do Microsoft 365 ](https://compliance.microsoft.com/), navegue até um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="375c8-117">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="375c8-118">Se você estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="375c8-118">If you are using records management:</span></span>
        - <span data-ttu-id="375c8-119">**Soluções** > **Gerenciamento de Registros** >  guia **Plano de Arquivos** > **+ Criar um Rótulo** > **Rótulo de Retenção**</span><span class="sxs-lookup"><span data-stu-id="375c8-119">**Solutions** > **Records management** > **File plan** tab > **+ Create a label** > **Retention label**</span></span>
        
    - <span data-ttu-id="375c8-120">Se você não estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="375c8-120">If you are not using records management:</span></span>
       - <span data-ttu-id="375c8-121">**Soluções** > **Governança de Informações** >  guia **Rótulos** > + **Criar um Rótulo**</span><span class="sxs-lookup"><span data-stu-id="375c8-121">**Solutions** > **Information governance** > **Labels** tab > + **Create a label**</span></span>
    
    <span data-ttu-id="375c8-122">Não vê a opção imediatamente?</span><span class="sxs-lookup"><span data-stu-id="375c8-122">Don't immediately see your option?</span></span> <span data-ttu-id="375c8-123">Primeiro, selecione **Mostrar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="375c8-123">First select **Show all**.</span></span> 

2. <span data-ttu-id="375c8-124">Siga as instruções do assistente.</span><span class="sxs-lookup"><span data-stu-id="375c8-124">Follow the prompts in the wizard.</span></span> <span data-ttu-id="375c8-125">Se você estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="375c8-125">If you are using records management:</span></span>
    
    - <span data-ttu-id="375c8-126">Para saber mais sobre os descritores de plano de arquivo, confira [Usar o plano de arquivo para gerenciar os rótulos de retenção](file-plan-manager.md)</span><span class="sxs-lookup"><span data-stu-id="375c8-126">For information about the file plan descriptors, see [Use file plan to manage retention labels](file-plan-manager.md)</span></span>
    
    - <span data-ttu-id="375c8-127">Para usar o rótulo de retenção para declarar conteúdo como um registro, ative a caixa de seleção **Usar rótulo para classificar o conteúdo como um "Registro"**.</span><span class="sxs-lookup"><span data-stu-id="375c8-127">To use the retention label to declare content as a record, enable the checkbox **Use label to classify content as a "Record"**.</span></span>

3. <span data-ttu-id="375c8-128">Repita essas etapas para criar mais rótulos.</span><span class="sxs-lookup"><span data-stu-id="375c8-128">Repeat these steps to create more labels.</span></span>

<span data-ttu-id="375c8-129">Para editar um rótulo existente, selecione-o e, em seguida, selecione **Editar rótulo** para começar o mesmo assistente que permite alterar as descrições de rótulo e as [configurações qualificadas](#updating-retention-labels-and-their-policies) na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="375c8-129">To edit an existing label, select it, and then select **Edit label** to start the same wizard that lets you change the label descriptions and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="375c8-130">Como alternativa, selecione qualquer uma das opções **Editar** para ir diretamente para a página relevante e fazer sua atualização.</span><span class="sxs-lookup"><span data-stu-id="375c8-130">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>

## <a name="publish-retention-labels-by-creating-a-retention-label-policy"></a><span data-ttu-id="375c8-131">Publicar rótulos de retenção criando uma política de rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="375c8-131">Publish retention labels by creating a retention label policy</span></span>

<span data-ttu-id="375c8-132">Publique seus rótulos de retenção, para que possam ser aplicados manualmente pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="375c8-132">Publish retention labels so that they can be manually applied by users.</span></span>

1. <span data-ttu-id="375c8-133">No [Centro de Conformidade do Microsoft 365 ](https://compliance.microsoft.com/), navegue até um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="375c8-133">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="375c8-134">Se você estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="375c8-134">If you are using records management:</span></span>
        - <span data-ttu-id="375c8-135">**Soluções** > **Gerenciamento de Registros** > > guia **Políticas de Rótulo** > **Publicar Rótulos**</span><span class="sxs-lookup"><span data-stu-id="375c8-135">**Solutions** > **Records management** > > **Label policies** tab > **Publish labels**</span></span>
    
    - <span data-ttu-id="375c8-136">Se você não estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="375c8-136">If you are not using records management:</span></span>
        - <span data-ttu-id="375c8-137">**Soluções** > **Governança de Informações** >  guia **Políticas de Rótulo** > **Publicar Rótulos**</span><span class="sxs-lookup"><span data-stu-id="375c8-137">**Solutions** > **Information governance** > **Label policies** tab > **Publish labels**</span></span>
    
    <span data-ttu-id="375c8-138">Não vê a opção imediatamente?</span><span class="sxs-lookup"><span data-stu-id="375c8-138">Don't immediately see your option?</span></span> <span data-ttu-id="375c8-139">Primeiro, selecione **Mostrar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="375c8-139">First select **Show all**.</span></span> 

2. <span data-ttu-id="375c8-140">Siga as instruções do assistente.</span><span class="sxs-lookup"><span data-stu-id="375c8-140">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="375c8-141">Para obter informações sobre os locais suportados pelos rótulos de retenção, confira a seção[Rótulos e locais de retenção](labels.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="375c8-141">For information about the locations supported by retention labels, see the [Retention labels and locations](labels.md#retention-label-policies-and-locations) section.</span></span> 

<span data-ttu-id="375c8-142">Para editar uma política de rótulo de retenção existente, selecione-a e, em seguida, selecione **Editar política** para começar o mesmo assistente que permite alterar as descrições da política e as [configurações qualificadas](#updating-retention-labels-and-their-policies) na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="375c8-142">To edit an existing retention label policy, select it, and then select **Edit policy** to start the same wizard that lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="375c8-143">Como alternativa, selecione qualquer uma das opções **Editar** para ir diretamente para a página relevante e fazer sua atualização.</span><span class="sxs-lookup"><span data-stu-id="375c8-143">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>

## <a name="auto-apply-a-retention-label"></a><span data-ttu-id="375c8-144">Aplicação automática de um rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="375c8-144">Auto-apply a retention label</span></span>

<span data-ttu-id="375c8-145">Aplique automaticamente um rótulo de retenção, com base nas condições que você especificar.</span><span class="sxs-lookup"><span data-stu-id="375c8-145">Auto-apply a retention label, based on the conditions that you specify.</span></span>

1. <span data-ttu-id="375c8-146">No [Centro de Conformidade do Microsoft 365 ](https://compliance.microsoft.com/), navegue até um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="375c8-146">In the [Microsoft 365 compliance center](https://compliance.microsoft.com/), navigate to one of the following locations:</span></span>
    
    - <span data-ttu-id="375c8-147">Se você estiver usando o gerenciamento de registros: **Governança de Informações**:</span><span class="sxs-lookup"><span data-stu-id="375c8-147">If you are using records management: **Information governance**:</span></span>
        - <span data-ttu-id="375c8-148">**Soluções** > **Gerenciamento de Registros** >  guia **Políticas de Rótulo** > **Aplicar rótulo automaticamente**</span><span class="sxs-lookup"><span data-stu-id="375c8-148">**Solutions** > **Records management** > **Label policies** tab > **Auto-apply label**</span></span>
    
    - <span data-ttu-id="375c8-149">Se você não estiver usando o gerenciamento de registros:</span><span class="sxs-lookup"><span data-stu-id="375c8-149">If you are not using records management:</span></span>
        - <span data-ttu-id="375c8-150">**Soluções** > **Governança de Informações** >  guia **Políticas de Rótulo** > **Aplicar rótulo automaticamente**</span><span class="sxs-lookup"><span data-stu-id="375c8-150">**Solutions** > **Information governance** > **Label policies** tab > **Auto-apply label**</span></span>
    
    <span data-ttu-id="375c8-151">Não vê a opção imediatamente?</span><span class="sxs-lookup"><span data-stu-id="375c8-151">Don't immediately see your option?</span></span> <span data-ttu-id="375c8-152">Primeiro, selecione **Mostrar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="375c8-152">First select **Show all**.</span></span> 

2. <span data-ttu-id="375c8-153">Siga as instruções do assistente.</span><span class="sxs-lookup"><span data-stu-id="375c8-153">Follow the prompts in the wizard.</span></span>
    
    <span data-ttu-id="375c8-154">Para saber mais sobre como configurar condições que aplicam automaticamente o rótulo de retenção, confira o [Configurar condições para a aplicação automática de rótulos de retenção](#configuring-conditions-for-auto-apply-retention-labels) nesta página.</span><span class="sxs-lookup"><span data-stu-id="375c8-154">For information about configuring the conditions that automatically apply the retention label, see the [Configuring conditions for auto-apply retention labels](#configuring-conditions-for-auto-apply-retention-labels) section on this page.</span></span>
    
    <span data-ttu-id="375c8-155">Para obter informações sobre os locais suportados pelos rótulos de retenção, confira a seção[Rótulos e locais de retenção](labels.md#retention-label-policies-and-locations).</span><span class="sxs-lookup"><span data-stu-id="375c8-155">For information about the locations supported by retention labels, see the [Retention labels and locations](labels.md#retention-label-policies-and-locations) section.</span></span>

<span data-ttu-id="375c8-156">Para editar uma política de rótulo de aplicação automática existente, selecione-a e, em seguida, selecione **Editar política** para começar o mesmo assistente que permite alterar as descrições da política e as [configurações qualificadas](#updating-retention-labels-and-their-policies) na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="375c8-156">To edit an existing auto-apply label policy, select it, and then select **Edit policy** to start the same wizard that lets you change the policy description and any [eligible settings](#updating-retention-labels-and-their-policies) from step 2.</span></span> <span data-ttu-id="375c8-157">Como alternativa, selecione qualquer uma das opções **Editar** para ir diretamente para a página relevante e fazer sua atualização.</span><span class="sxs-lookup"><span data-stu-id="375c8-157">Alternatively, select any of the available **Edit** options to go directly to the relevant page to make your update.</span></span>


## <a name="configuring-conditions-for-auto-apply-retention-labels"></a><span data-ttu-id="375c8-158">Configurar condições para a aplicação automática de rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="375c8-158">Configuring conditions for auto-apply retention labels</span></span>

<span data-ttu-id="375c8-159">Você pode aplicar os rótulos de retenção automaticamente ao conteúdo quando esse conteúdo apresentar:</span><span class="sxs-lookup"><span data-stu-id="375c8-159">You can apply retention labels to content automatically when that content contains:</span></span>
  
- [<span data-ttu-id="375c8-160">Tipos específicos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="375c8-160">Specific types of sensitive information</span></span>](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)
    
- [<span data-ttu-id="375c8-161">Palavras-chave específicas que correspondem a uma consulta criada por você</span><span class="sxs-lookup"><span data-stu-id="375c8-161">Specific keywords that match a query you create</span></span>](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [<span data-ttu-id="375c8-162">Uma correspondência de classificadores treináveis</span><span class="sxs-lookup"><span data-stu-id="375c8-162">A match for trainable classifiers</span></span>](#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![Escolha a página de condição para aplicação automática de rótulo](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

<span data-ttu-id="375c8-164">Pode levar até sete dias para que os rótulos de retenção sejam aplicados automaticamente a todo o conteúdo que corresponde às condições que você configurou.</span><span class="sxs-lookup"><span data-stu-id="375c8-164">It can take up to seven days for auto-apply retention labels to be applied to all content that matches the conditions you've configured.</span></span>

### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a><span data-ttu-id="375c8-165">Aplicar automaticamente rótulos a conteúdo com tipos específicos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="375c8-165">Auto-apply labels to content with specific types of sensitive information</span></span>

<span data-ttu-id="375c8-166">Ao criar rótulos de retenção de aplicação automática para informações confidenciais, você vê a mesma lista de modelos de política que quando cria uma política de prevenção contra perda de dados (DLP).</span><span class="sxs-lookup"><span data-stu-id="375c8-166">When you create auto-apply retention labels for sensitive information, you see the same list of policy templates as when you create a data loss prevention (DLP) policy.</span></span> <span data-ttu-id="375c8-167">Cada modelo de política é pré-configurado para procurar tipos específicos de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="375c8-167">Each policy template is preconfigured to look for specific types of sensitive information.</span></span> <span data-ttu-id="375c8-168">Por exemplo, o modelo mostrado aqui procura os números do ITIN (Número de Identificação de Contribuinte Individual) dos EUA, SSN (CPF) e passaporte.</span><span class="sxs-lookup"><span data-stu-id="375c8-168">For example, the template shown here looks for U.S. ITIN, SSN, and passport numbers.</span></span> <span data-ttu-id="375c8-169">Para saber mais sobre DLP, confira [Visão geral das políticas de prevenção contra perda de dados](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="375c8-169">To learn more about DLP, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
![Modelos de política com tipos de informações confidenciais](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
<span data-ttu-id="375c8-p113">Depois de selecionar um modelo de política, você pode adicionar ou remover quaisquer tipos de informações confidenciais, e pode alterar a contagem de instâncias e a precisão de correspondência. No exemplo mostrado aqui, um rótulo de retenção será aplicado automaticamente apenas quando:</span><span class="sxs-lookup"><span data-stu-id="375c8-p113">After you select a policy template, you can add or remove any types of sensitive information, and you can change the instance count and match accuracy. In the example shown here, a retention label will be auto-applied only when:</span></span>
  
- <span data-ttu-id="375c8-p114">O conteúdo tiver entre uma e nove instâncias de qualquer um destes três tipos de informações confidenciais. Você pode excluir o valor **max** para que mude para **any**.</span><span class="sxs-lookup"><span data-stu-id="375c8-p114">The content contains between 1 and 9 instances of any of these three sensitive information types. You can delete the **max** value so that it changes to **any**.</span></span>
    
- <span data-ttu-id="375c8-p115">O tipo de informação confidencial detectado tiver uma precisão de correspondência (ou nível de confiança) de pelo menos 75. Muitos tipos de informações confidenciais são definidos com vários padrões, em que um padrão de precisão de correspondência superior exige mais evidências para ser encontrado (como palavras-chave, datas ou endereços), enquanto um padrão de precisão de correspondência inferior exige menos evidências. Resumindo, quanto menor a precisão de correspondência **min**, mais fácil será para o conteúdo atender à condição.</span><span class="sxs-lookup"><span data-stu-id="375c8-p115">The type of sensitive information that's detected has a match accuracy (or confidence level) of at least 75. Many sensitive information types are defined with multiple patterns, where a pattern with a higher match accuracy requires more evidence to be found (such as keywords, dates, or addresses), while a pattern with a lower match accuracy requires less evidence. Simply put, the lower the **min** match accuracy, the easier it is for content to match the condition.</span></span> 
    
<span data-ttu-id="375c8-178">Para saber mais sobre essas opções, confira [Como ajustar as regras para facilitar ou dificultar a correspondência](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span><span class="sxs-lookup"><span data-stu-id="375c8-178">For more information on these options, see [Tuning rules to make them easier or harder to match](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).</span></span>
    
![Opções para identificar tipos de informações confidenciais](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a><span data-ttu-id="375c8-180">Aplicar rótulos automaticamente a conteúdos com palavras-chave ou propriedades pesquisáveis</span><span class="sxs-lookup"><span data-stu-id="375c8-180">Auto-apply labels to content with keywords or searchable properties</span></span>

<span data-ttu-id="375c8-p116">Você pode aplicar automaticamente os rótulos ao conteúdo que atenda a certas condições. As condições disponíveis agora dão suporte à aplicação de um rótulo a conteúdos que incluem palavras ou frases específicas, ou valores de propriedades pesquisáveis. Você pode refinar a consulta usando os operadores de pesquisa AND, OR e NOT.</span><span class="sxs-lookup"><span data-stu-id="375c8-p116">You can auto-apply labels to content that satisfies certain conditions. The conditions now available support applying a label to content that contains specific words, phrases, or values of searchable properties. You can refine your query by using search operators like AND, OR, and NOT.</span></span>

<span data-ttu-id="375c8-184">Para saber mais sobre sintaxe de consulta, confira:</span><span class="sxs-lookup"><span data-stu-id="375c8-184">For more information on query syntax, see:</span></span>

- [<span data-ttu-id="375c8-185">Referência de sintaxe da Linguagem de Consulta de Palavra-chave (KQL)</span><span class="sxs-lookup"><span data-stu-id="375c8-185">Keyword Query Language (KQL) syntax reference</span></span>](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

<span data-ttu-id="375c8-p117">Rótulos baseados em consultas usam o índice de pesquisa para identificar conteúdos. Para saber mais sobre propriedades pesquisáveis válidas, confira:</span><span class="sxs-lookup"><span data-stu-id="375c8-p117">Query-based labels use the search index to identify content. For more information on valid searchable properties, see:</span></span>

- [<span data-ttu-id="375c8-188">Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="375c8-188">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)
- [<span data-ttu-id="375c8-189">Visão geral de propriedades rastreadas e gerenciadas no SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="375c8-189">Overview of crawled and managed properties in SharePoint Server</span></span>](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

<span data-ttu-id="375c8-190">Consultas de exemplos:</span><span class="sxs-lookup"><span data-stu-id="375c8-190">Examples queries:</span></span>

- <span data-ttu-id="375c8-191">Exchange</span><span class="sxs-lookup"><span data-stu-id="375c8-191">Exchange</span></span>
    - <span data-ttu-id="375c8-192">assunto:"Finanças trimestrais"</span><span class="sxs-lookup"><span data-stu-id="375c8-192">subject:"Quarterly Financials"</span></span>
    - <span data-ttu-id="375c8-193">destinatários:garthf</span><span class="sxs-lookup"><span data-stu-id="375c8-193">recipients:garthf</span></span><!--nolink--><span data-ttu-id="375c8-194">@contoso.com</span><span class="sxs-lookup"><span data-stu-id="375c8-194">@contoso.com</span></span>
- <span data-ttu-id="375c8-195">SharePoint e OneDrive</span><span class="sxs-lookup"><span data-stu-id="375c8-195">SharePoint and OneDrive</span></span>
    - <span data-ttu-id="375c8-196">contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="375c8-196">contenttype:contract</span></span>
    - <span data-ttu-id="375c8-197">site:https</span><span class="sxs-lookup"><span data-stu-id="375c8-197">site:https</span></span><!--nolink--><span data-ttu-id="375c8-198">://contoso.sharepoint.com/sites/teams/procurement E contenttype:contract</span><span class="sxs-lookup"><span data-stu-id="375c8-198">://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract</span></span>

![Editor de consultas](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a><span data-ttu-id="375c8-200">Aplicar rótulos automaticamente ao conteúdo usando classificadores treináveis</span><span class="sxs-lookup"><span data-stu-id="375c8-200">Auto-apply labels to content by using trainable classifiers</span></span>

<span data-ttu-id="375c8-201">Ao escolher a opção de um classificador treinado, você pode selecionar um dos classificadores internos ou um classificador personalizado.</span><span class="sxs-lookup"><span data-stu-id="375c8-201">When you choose the option for a trainable classifier, you can select one of the built-in classifiers, or a custom classifier.</span></span> <span data-ttu-id="375c8-202">Os classificadores internos incluem **Currículos**, **SourceCode**, **Assédio Direcionado**, **Profanação** e **Ameaças**:</span><span class="sxs-lookup"><span data-stu-id="375c8-202">The built-in classifiers include **Resumes**, **SourceCode**, **Targeted Harassment**, **Profanity**, and **Threat**:</span></span>

![Escolha classificador treinável](../media/retention-label-classifers.png)

<span data-ttu-id="375c8-204">Para aplicar um rótulo automaticamente usando essa opção, as caixas de correio e sites do SharePoint Online devem ter pelo menos 10 MB de dados.</span><span class="sxs-lookup"><span data-stu-id="375c8-204">To automatically apply a label by using this option, SharePoint Online sites and mailboxes must have at least 10 MB of data.</span></span>

<span data-ttu-id="375c8-205">Para obter mais informações sobre os classificadores treináveis, confira [Introdução aos classificadores treináveis (visualização)](classifier-getting-started-with.md).</span><span class="sxs-lookup"><span data-stu-id="375c8-205">For more information about trainable classifiers, see [Getting started with trainable classifiers (preview)](classifier-getting-started-with.md).</span></span>

<span data-ttu-id="375c8-206">Para um exemplo de configuração, consulte [Como preparar e usar um classificador interno](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span><span class="sxs-lookup"><span data-stu-id="375c8-206">For an example configuration, see [How to prepare for and use a built-in classifier](classifier-using-a-ready-to-use-classifier.md#how-to-verify-that-a-built-in-classifier-will-meet-your-needs).</span></span>

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a><span data-ttu-id="375c8-207">Quanto tempo demora para os rótulos de retenção entrarem em vigor</span><span class="sxs-lookup"><span data-stu-id="375c8-207">How long it takes for retention labels to take effect</span></span>

<span data-ttu-id="375c8-208">Quando você publica ou aplica rótulos de retenção automaticamente, eles não entram em vigor imediatamente:</span><span class="sxs-lookup"><span data-stu-id="375c8-208">When you publish or auto-apply retention labels, they don't take effect immediately:</span></span>
  
1. <span data-ttu-id="375c8-209">Primeiro, a política de rótulos precisa ser sincronizada desde o centro de administração até os locais na política.</span><span class="sxs-lookup"><span data-stu-id="375c8-209">First the label policy needs to be synced from the admin center to the locations in the policy.</span></span>
    
2. <span data-ttu-id="375c8-210">Em seguida, o local pode precisar de tempo para disponibilizar rótulos de retenção publicados para os usuários finais ou para aplicar rótulos automaticamente ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="375c8-210">Then the location might require time to make published retention labels available to end users or time to auto-apply labels to content.</span></span> <span data-ttu-id="375c8-211">Quanto tempo isso leva depende do local e do tipo de rótulo de retenção.</span><span class="sxs-lookup"><span data-stu-id="375c8-211">How long this takes depends on the location and type of retention label.</span></span>
    
### <a name="published-retention-labels"></a><span data-ttu-id="375c8-212">Rótulos de retenção publicados</span><span class="sxs-lookup"><span data-stu-id="375c8-212">Published retention labels</span></span>

<span data-ttu-id="375c8-p120">Se você publicar rótulos de retenção no SharePoint ou no OneDrive, talvez demore um dia para que esses rótulos de retenção apareçam para os usuários finais. Além disso, se você publicar os rótulos de retenção no Exchange, talvez demore 7 dias para que eles apareçam para os usuários finais, e a caixa de correio deles deve conter pelo menos 10 MB de dados.</span><span class="sxs-lookup"><span data-stu-id="375c8-p120">If you publish retention labels to SharePoint or OneDrive, it can take one day for those retention labels to appear for end users. In addition, if you publish retention labels to Exchange, it can take 7 days for those retention labels to appear for end users, and the mailbox needs to contain at least 10 MB of data.</span></span>
  
![Diagrama de quando os rótulos manuais entram em vigor](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a><span data-ttu-id="375c8-216">Aplicação automática de rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="375c8-216">Auto-apply retention labels</span></span>

<span data-ttu-id="375c8-217">Se você aplicar automaticamente rótulos de retenção a conteúdos que se encaixem em condições específicas, poderá levar sete dias para que os rótulos de retenção sejam aplicados a todo o conteúdo existente que se encaixe nas condições.</span><span class="sxs-lookup"><span data-stu-id="375c8-217">If you auto-apply retention labels to content matching specific conditions, it can take seven days for the retention labels to be applied to all existing content that matches the conditions.</span></span>
  
![Diagrama de quando a aplicação automática de rótulos entra em vigor](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a><span data-ttu-id="375c8-219">Como verificar o status dos rótulos de retenção publicados no Exchange</span><span class="sxs-lookup"><span data-stu-id="375c8-219">How to check on the status of retention labels published to Exchange</span></span>

<span data-ttu-id="375c8-220">No Exchange Online, os rótulos são disponibilizados para os usuários finais por um processo que é executado a cada sete dias.</span><span class="sxs-lookup"><span data-stu-id="375c8-220">In Exchange Online, retention labels are made available to end users by a process that runs every seven days.</span></span> <span data-ttu-id="375c8-221">Usando o Powershell, você pode ver quando esse processo foi executado pela última vez e, assim, determinar quando ele será executado novamente.</span><span class="sxs-lookup"><span data-stu-id="375c8-221">By using Powershell, you can see when this process last ran and therefore identify when it will run again.</span></span>
  
1. <span data-ttu-id="375c8-222">[Conectar-se ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span><span class="sxs-lookup"><span data-stu-id="375c8-222">[Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=799773).</span></span>
    
2. <span data-ttu-id="375c8-223">Execute estes comandos.</span><span class="sxs-lookup"><span data-stu-id="375c8-223">Run these commands.</span></span>
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
   ```

<span data-ttu-id="375c8-224">Nos resultados, a propriedade `ELCLastSuccessTimeStamp` (UTC) mostra quando o sistema processou sua caixa de correio pela última vez.</span><span class="sxs-lookup"><span data-stu-id="375c8-224">In the results, the `ELCLastSuccessTimeStamp` (UTC) property shows when the system last processed your mailbox.</span></span> <span data-ttu-id="375c8-225">Se isso não tiver acontecido desde a hora em que você criou a política, os rótulos não serão exibidos.</span><span class="sxs-lookup"><span data-stu-id="375c8-225">If it has not happened since the time you created the policy, the labels are not going to appear.</span></span> <span data-ttu-id="375c8-226">Para forçar o processamento, execute o  `Start-ManagedFolderAssistant -Identity <user>`.</span><span class="sxs-lookup"><span data-stu-id="375c8-226">To force processing, run  `Start-ManagedFolderAssistant -Identity <user>`.</span></span>
    
<span data-ttu-id="375c8-227">Se os rótulos não estiverem aparecendo no Outlook na Web, e você achar que deveriam aparecer, limpe o cache do navegador (CTRL + F5).</span><span class="sxs-lookup"><span data-stu-id="375c8-227">If labels aren't appearing in Outlook on the web and you think they should be, make sure to clear the cache in your browser (CTRL+F5).</span></span>
    

## <a name="updating-retention-labels-and-their-policies"></a><span data-ttu-id="375c8-228">Atualizar rótulos de retenção e suas políticas</span><span class="sxs-lookup"><span data-stu-id="375c8-228">Updating retention labels and their policies</span></span>

<span data-ttu-id="375c8-229">Se você editar um rótulo de retenção, política de rótulo de retenção ou política de aplicação automática e o rótulo de retenção já estiver aplicado ao conteúdo, as configurações atualizadas serão aplicadas automaticamente a esse conteúdo, além do conteúdo recentemente rotulado.</span><span class="sxs-lookup"><span data-stu-id="375c8-229">When you edit a retention label, retention label policy, or auto-apply policy, and the retention label or policy is already applied to content, your updated settings will automatically be applied to this content in addition to content that's newly identified.</span></span>

<span data-ttu-id="375c8-230">Algumas configurações não podem ser alteradas depois que o rótulo ou política é criado e salvo, que incluem:</span><span class="sxs-lookup"><span data-stu-id="375c8-230">Some settings can't be changed after the label or policy is created and saved, which include:</span></span>
- <span data-ttu-id="375c8-231">As configurações de retenção, exceto o período de retenção, a menos que você tenha configurado o rótulo para reter ou excluir o conteúdo com base em quando ele foi criado.</span><span class="sxs-lookup"><span data-stu-id="375c8-231">The retention settings except the retention period, unless you've configured the label to retain or delete the content based on when it was created.</span></span>
- <span data-ttu-id="375c8-232">A opção para classificar como um registro.</span><span class="sxs-lookup"><span data-stu-id="375c8-232">The option to classify as a record.</span></span>

## <a name="find-the-powershell-cmdlets-for-retention-labels"></a><span data-ttu-id="375c8-233">Localizar os cmdlets do Windows PowerShell para rótulos de retenção</span><span class="sxs-lookup"><span data-stu-id="375c8-233">Find the PowerShell cmdlets for retention labels</span></span>

<span data-ttu-id="375c8-234">Para usar os cmdlets de rótulos de retenção:</span><span class="sxs-lookup"><span data-stu-id="375c8-234">To use the retention label cmdlets:</span></span>
  
1. [<span data-ttu-id="375c8-235">Conecte-se ao PowerShell do Centro de Conformidade e Segurança do Office 365</span><span class="sxs-lookup"><span data-stu-id="375c8-235">Connect to the Office 365 Security & Compliance Center Powershell</span></span>](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. <span data-ttu-id="375c8-236">Use esses cmdlets do Centro de Conformidade e Segurança do Office 365</span><span class="sxs-lookup"><span data-stu-id="375c8-236">Use these Office 365 Security & Compliance Center cmdlets:</span></span>
    
    - [<span data-ttu-id="375c8-237">Get-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="375c8-237">Get-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetag)
    
    - [<span data-ttu-id="375c8-238">New-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="375c8-238">New-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancetag)
    
    - [<span data-ttu-id="375c8-239">Remove-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="375c8-239">Remove-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-compliancetag)
    
    - [<span data-ttu-id="375c8-240">Set-ComplianceTag</span><span class="sxs-lookup"><span data-stu-id="375c8-240">Set-ComplianceTag</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancetag)
    
    - [<span data-ttu-id="375c8-241">Enable-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="375c8-241">Enable-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/enable-compliancetagstorage)
    
    - [<span data-ttu-id="375c8-242">Get-ComplianceTagStorage</span><span class="sxs-lookup"><span data-stu-id="375c8-242">Get-ComplianceTagStorage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancetagstorage)
    
    - [<span data-ttu-id="375c8-243">Get-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="375c8-243">Get-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy)
    
    - [<span data-ttu-id="375c8-244">New-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="375c8-244">New-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancepolicy)
    
    - [<span data-ttu-id="375c8-245">Remove-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="375c8-245">Remove-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancepolicy)
    
    - [<span data-ttu-id="375c8-246">Set-RetentionCompliancePolicy</span><span class="sxs-lookup"><span data-stu-id="375c8-246">Set-RetentionCompliancePolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy)
    
    - [<span data-ttu-id="375c8-247">Get-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="375c8-247">Get-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancerule)
    
    - [<span data-ttu-id="375c8-248">New-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="375c8-248">New-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule)
    
    - [<span data-ttu-id="375c8-249">Remove-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="375c8-249">Remove-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/remove-retentioncompliancerule)
    
    - [<span data-ttu-id="375c8-250">Set-RetentionComplianceRule</span><span class="sxs-lookup"><span data-stu-id="375c8-250">Set-RetentionComplianceRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule)
