---
title: Aplicar ou remover uma política de exclusão de documentos de um site
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
description: Com frequência, as organizações estão sujeitas a regulamentações de conformidade, legais ou outras que exigem que elas retenham documentos por um determinado período. No entanto, reter os documentos por mais tempo do que o necessário poderá expor a organização a riscos legais. Por esse motivo, sua organização pode ter criado uma política de exclusão de documentos para seu site. Por exemplo, pode ser necessário que documentos comerciais gerais sejam excluídos cinco anos após sua criação.
ms.openlocfilehash: 67bbe3339b492e5199799a21e5b3b249a3a98c08
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596068"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="cdf3b-105">Aplicar ou remover uma política de exclusão de documentos de um site</span><span class="sxs-lookup"><span data-stu-id="cdf3b-105">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="cdf3b-106">As organizações geralmente estão sujeitas às normas de conformidade, jurídica ou outras que exigem a retenção de documentos por um determinado período de tempo.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-106">Organizations are often subject to compliance, legal, or other regulations that require them to retain documents for a certain period of time.</span></span> <span data-ttu-id="cdf3b-107">No entanto, reter os documentos por mais tempo do que o necessário poderá expor a organização a riscos legais.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-107">However, retaining documents for longer than required can expose the organization to legal risk.</span></span> <span data-ttu-id="cdf3b-108">Por esse motivo, sua organização pode ter criado uma política de exclusão de documentos para&mdash;seu site, por exemplo, documentos de negócios gerais podem ser excluídos cinco anos após terem sido criados.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-108">For this reason, your organization may have created a document deletion policy for your site&mdash;for example, general business documents might be required to be deleted five years after they were created.</span></span>
  
<span data-ttu-id="cdf3b-109">Dependendo da sua organização, uma política de exclusão de documentos pode ser:</span><span class="sxs-lookup"><span data-stu-id="cdf3b-109">Depending on your organization, a document deletion policy might be:</span></span>
  
- <span data-ttu-id="cdf3b-110">**Obrigatório** Um proprietário de site não pode recusar uma política obrigatória, que é automaticamente aplicada ao site.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-110">**Mandatory** A site owner can't opt out of a mandatory policy, which is automatically applied to the site.</span></span> 
    
- <span data-ttu-id="cdf3b-111">**Padrão** Uma política padrão é automaticamente aplicada a um site, mas o proprietário do site pode:</span><span class="sxs-lookup"><span data-stu-id="cdf3b-111">**Default** A default policy is automatically applied to a site, but a site owner can:</span></span> 
    
  - <span data-ttu-id="cdf3b-112">Escolher outra política, se disponível.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-112">Choose another policy if available.</span></span>
    
  - <span data-ttu-id="cdf3b-113">Cancele a política completamente se não for relevante para o conteúdo do site.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-113">Opt out of the policy entirely if it isn't relevant to the content in the site.</span></span>
    
- <span data-ttu-id="cdf3b-114">**Nem obrigatória nem padrão** Neste caso, nenhuma política será automaticamente aplicada ao site, e o proprietário do site precisará tomar ação para aplicar uma.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-114">**Neither mandatory nor default** In this case, no policy is automatically applied to the site, and the site owner needs to take action to apply one.</span></span> 
    
<span data-ttu-id="cdf3b-115">Uma política de exclusão de documentos pode conter mais de&mdash;uma regra por exemplo, uma regra pode dizer excluir documentos um ano após eles terem sido criados, mas outra regra pode dizer excluir documentos um ano após a última modificação.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-115">A document deletion policy may contain more than one rule&mdash;for example, one rule might say delete documents one year after they were created, but another rule might say delete documents one year after they were last modified.</span></span> <span data-ttu-id="cdf3b-116">Se uma política contiver mais de uma regra, você poderá selecionar a regra que melhor se aplique ao seu site.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-116">If a policy contains more than one rule, you can select the rule that best applies to your site.</span></span> <span data-ttu-id="cdf3b-117">A regra de exclusão será aplicada a todas as bibliotecas no site.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-117">The delete rule will be applied to all libraries within the site.</span></span> <span data-ttu-id="cdf3b-118">Somente uma política e uma regra poderão estar ativas em um site ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-118">Only one policy and one rule can be active in a site at one time.</span></span> <span data-ttu-id="cdf3b-119">Como uma política, uma regra pode ser definida como padrão, para que ela seja aplicada automaticamente quando a política é aplicada.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-119">Like a policy, a rule can be set as default, so that it's applied automatically when the policy is applied.</span></span>
  
<span data-ttu-id="cdf3b-p104">Por fim, as políticas de exclusão de documentos são herdadas. Quando você seleciona uma política ou uma regra para seu site, essa seleção é herdada por todos os subsites, embora o proprietário de um subsite possa interromper a herança ao selecionar uma política ou regra diferente. Quando você selecionar uma política ou uma regra, considere o conteúdo de qualquer subsite abaixo de seu site.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-p104">Finally, document deletion policies are inherited. When you select a policy or rule for your site, that selection is inherited by all subsites, although an owner of a subsite can break inheritance by selecting a different policy or rule. When you select a policy or rule, consider the content of any subsites below your site.</span></span>
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a><span data-ttu-id="cdf3b-123">Exibir as políticas de exclusão de documentos disponíveis em um conjunto de sites</span><span class="sxs-lookup"><span data-stu-id="cdf3b-123">View the document deletion policies available in a site collection</span></span>

<span data-ttu-id="cdf3b-p105">Sua organização pode atribuir políticas diferentes a conjuntos de sites diferentes. No nível do conjunto de sites, o proprietário de um conjunto de sites pode exibir todas as políticas de exclusão de documentos disponíveis para aquele conjunto de sites. As políticas pode ter sido disponibilizadas para o modelo de conjunto de sites (e, portanto, para todos os conjuntos de sites criados a partir desse modelo) ou para este conjunto de sites específico.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-p105">Your organization may assign different policies to different site collections. At the site collection level, an owner of a site collection can view all of the document deletion policies that are available to that site collection. The policies may have been made available to the site collection template (and therefore all site collections created from this template) or to this specific site collection.</span></span>
  
1. <span data-ttu-id="cdf3b-127">No site de nível superior no conjunto de sites, no canto superior direito, escolha **configurações** [ícone de engrenagem] \> **configurações de site**.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-127">In the top-level site in the site collection, in the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="cdf3b-128">Em **políticas de exclusão de documentos**da administração \> do conjunto de **sites** .</span><span class="sxs-lookup"><span data-stu-id="cdf3b-128">Under **Site Collection Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cdf3b-129">O link **políticas de exclusão de documentos** não aparecerá, a menos que as políticas tenham sido atribuídas ao conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-129">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="cdf3b-130">Além disso, o link não aparece imediatamente após as políticas terem sido atribuídas ao site, pode levar até 24 horas a partir do momento em que as políticas são atribuídas quando o link de **políticas de exclusão de documentos** é exibido.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-130">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="cdf3b-131">Nesta página, você pode exibir:</span><span class="sxs-lookup"><span data-stu-id="cdf3b-131">On this page you can view:</span></span>
    
  - <span data-ttu-id="cdf3b-p107">As políticas atribuídas no momento e as regras associadas. Selecione uma política para exibir as regras no painel direito.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-p107">The currently assigned policies and the associated rules. Select a policy to view the rules in the right pane.</span></span>
    
  - <span data-ttu-id="cdf3b-134">A política padrão, se houver, exibe **Sim** na coluna **Padrão**.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-134">The default policy, if any, displays **Yes** in the **Default** column.</span></span> 
    
  - <span data-ttu-id="cdf3b-135">Uma mensagem será exibida abaixo da lista caso a política tenha sido atribuída como **Obrigatória**.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-135">A message is displayed below the list if the policy has been assigned as **Mandatory**.</span></span>
    
<span data-ttu-id="cdf3b-p108">Essa lista é somente para exibição, para que o proprietário de conjunto de sites veja todas as políticas e regras disponíveis. Para aplicar uma política, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-p108">This list is view only, for the site collection owner to see all of the available policies and rules. To apply a policy, see the next section.</span></span>
  
![Exibição das políticas de exclusão de documentos atribuídas a um conjunto de sites](media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a><span data-ttu-id="cdf3b-139">Aplicar ou remover uma política de exclusão de documentos de um site</span><span class="sxs-lookup"><span data-stu-id="cdf3b-139">Apply or remove a document deletion policy for a site</span></span>

<span data-ttu-id="cdf3b-140">Como proprietário do site ou proprietário de conjunto de sites, sua organização pode ter criado políticas que você poderá aplicar a seu site ou recusar inteiramente.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-140">As a site owner or site collection owner, your organization may have created policies that you can either apply to your site or opt out of entirely.</span></span>
  
1. <span data-ttu-id="cdf3b-141">No canto superior direito, escolha **configurações** [ícone de engrenagem] \> **configurações de site**.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-141">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="cdf3b-142">Em **políticas de exclusão de documentos**da administração \> do **site** .</span><span class="sxs-lookup"><span data-stu-id="cdf3b-142">Under **Site Administration** \> **Document Deletion Policies**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cdf3b-143">O link **políticas de exclusão de documentos** não aparecerá, a menos que as políticas tenham sido atribuídas ao conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-143">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="cdf3b-144">Além disso, o link não aparece imediatamente após as políticas terem sido atribuídas ao site, pode levar até 24 horas a partir do momento em que as políticas são atribuídas quando o link de **políticas de exclusão de documentos** é exibido.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-144">Also, the link doesn't appear immediately after policies have been assigned to the site — it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
3. <span data-ttu-id="cdf3b-145">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="cdf3b-145">Do one of the following:</span></span>
    
  - <span data-ttu-id="cdf3b-146">**Para aplicar uma política** Selecionar uma política \> selecione uma regra nessa política \> **salvar**.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-146">**To apply a policy** Select a policy \> select a rule in that policy \> **Save**.</span></span>
    
    <span data-ttu-id="cdf3b-p110">Somente uma política e uma regra poderão estar ativas em um site ao mesmo tempo. Sua organização pode oferecer várias opções de políticas e de regras ou somente uma política ou uma regra.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-p110">Only one policy and one rule can be active in a site at one time. Your organization may provide several policies and rules to choose from, or only one policy or rule.</span></span>
    
    ![Selecionar opção de política](media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - <span data-ttu-id="cdf3b-150">**Para recusar uma política** Escolha **recusar: no note excluir** \> **salvar**.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-150">**To opt out of a policy** Choose **Opt-Out: Do Note Delete** \> **Save**.</span></span>
    
    <span data-ttu-id="cdf3b-151">Como proprietário do site, você pode recusar uma política de exclusão de documentos se determinar que a política não se aplica ao conteúdo do seu site.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-151">As a site owner, you can opt out of a document deletion policy if you determine that the policy isn't applicable to the content in your site.</span></span> <span data-ttu-id="cdf3b-152">No entanto, não é possível recusar uma política que tenha sido marcada como **obrigatória**.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-152">However, you can't opt out of a policy that has been marked as **Mandatory**.</span></span>
    
    ![Opção recusar](media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a><span data-ttu-id="cdf3b-154">As políticas de exclusão de documentos substituem outras políticas</span><span class="sxs-lookup"><span data-stu-id="cdf3b-154">Document deletion policies override other policies</span></span>

<span data-ttu-id="cdf3b-155">Um site pode usar outras políticas de retenção e exclusão de conteúdo:</span><span class="sxs-lookup"><span data-stu-id="cdf3b-155">A site may use other policies for retaining and deleting content:</span></span>
  
- <span data-ttu-id="cdf3b-156">Políticas de tipo de conteúdo para o conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-156">Content type policies for the site collection.</span></span>
    
- <span data-ttu-id="cdf3b-157">Políticas de gerenciamento de informações para uma lista ou biblioteca.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-157">Information management policies for a list or library.</span></span>
    
<span data-ttu-id="cdf3b-158">Se você aplicar uma política de exclusão de documentos a um site que já use políticas de tipo de conteúdo ou políticas de gerenciamento de informações para uma lista ou biblioteca, essas políticas serão ignoradas enquanto a política de exclusão de documentos estiver em vigor.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-158">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect.</span></span> <span data-ttu-id="cdf3b-159">Se outras políticas forem ignoradas, você verá a mensagem "o conteúdo deste site usa políticas de exclusão de documentos".</span><span class="sxs-lookup"><span data-stu-id="cdf3b-159">If other policies are ignored, you'll see the message "Content on this site uses Document Deletion Policies".</span></span>
  
<span data-ttu-id="cdf3b-160">Isso significa que você deve planejar para que um site use somente políticas destinadas a conteúdo estruturado (políticas de gerenciamento de informações e políticas de tipo de conteúdo) ou a conteúdo não estruturado (políticas de exclusão de documentos), e não ambas.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-160">This means you should plan for a site to use only policies meant for structured content (information management policies and content type policies) or unstructured content (document deletion policies), not both.</span></span> <span data-ttu-id="cdf3b-161">Se você optar por uma política de exclusão de documentos, o aviso não será exibido e outros tipos de políticas continuarão a funcionar.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-161">If you opt out of a document deletion policy, the warning won't be displayed and other types of policies will continue to work.</span></span>
  
<span data-ttu-id="cdf3b-162">As políticas de site não são afetadas por políticas de exclusão de documentos.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-162">Site policies are not affected by document deletion policies.</span></span>
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a><span data-ttu-id="cdf3b-163">Determinar se as políticas de tipo de conteúdo estão sendo ignoradas</span><span class="sxs-lookup"><span data-stu-id="cdf3b-163">Determine if content type policies are being ignored</span></span>

<span data-ttu-id="cdf3b-164">Se o seu site estava usando políticas de tipo de conteúdo e agora você vê essa mensagem, essas políticas não estarão mais em vigor.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-164">If your site was using content type policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="cdf3b-165">Para restaurar as políticas de tipo de conteúdo, você pode remover a política de exclusão de documentos do seu site, conforme descrito anteriormente, se houver uma opção de recusa disponível.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-165">To restore the content type policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="cdf3b-166">Se não houver opção para recusar, a política de exclusão de documentos será obrigatória e você precisará entrar em contato com o responsável pela conformidade em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-166">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
1. <span data-ttu-id="cdf3b-167">No canto superior direito, escolha **configurações** [ícone de engrenagem] \> **configurações de site**.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-167">In the upper-right corner, choose **Settings** [gear icon] \> **Site Settings**.</span></span>
    
2. <span data-ttu-id="cdf3b-168">Em **modelos de política de tipo de conteúdo**da administração \> do **site** .</span><span class="sxs-lookup"><span data-stu-id="cdf3b-168">Under **Site Administration** \> **Content Type Policy Templates**.</span></span>
    
    ![Aviso no site em que as políticas de exclusão de documentos estão sendo usadas](media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a><span data-ttu-id="cdf3b-170">Determinar se as políticas de gerenciamento de informações estão sendo ignoradas</span><span class="sxs-lookup"><span data-stu-id="cdf3b-170">Determine if information management policies are being ignored</span></span>

<span data-ttu-id="cdf3b-171">Se o seu site estava usando políticas de gerenciamento de informações e agora você vê essa mensagem, essas políticas não estarão mais em vigor.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-171">If your site was using information management policies and you now see this message, those policies are no longer in effect.</span></span> <span data-ttu-id="cdf3b-172">Para restaurar as políticas de gerenciamento de informações, você pode remover a política de exclusão de documentos do seu site, conforme descrito anteriormente, se houver uma opção de recusa disponível.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-172">To restore the information management policies, you can remove the document deletion policy from your site, as described earlier, if there's an opt-out option available.</span></span> <span data-ttu-id="cdf3b-173">Se não houver opção para recusar, a política de exclusão de documentos será obrigatória e você precisará entrar em contato com o responsável pela conformidade em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-173">If there's no option to opt out, the document deletion policy is mandatory, and you need to contact the compliance officer in your organization.</span></span>
  
- <span data-ttu-id="cdf3b-174">Para uma lista ou biblioteca, nas **configurações** \> da \> biblioteca de \> guias da **biblioteca** de faixa de **opções em configurações de política de gerenciamento de informações** **de gerenciamento** \> e permissões.</span><span class="sxs-lookup"><span data-stu-id="cdf3b-174">For a list or library, on the Ribbon \> **Library** tab \> **Library Settings** \> under **Permissions and Management** \> **Information Management Policy Settings**.</span></span>
    
    ![Aviso no site em que as políticas de exclusão de documentos estão sendo usadas](media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a><span data-ttu-id="cdf3b-176">Confira também</span><span class="sxs-lookup"><span data-stu-id="cdf3b-176">See also</span></span>

[<span data-ttu-id="cdf3b-177">Visão geral das políticas de exclusão de documento</span><span class="sxs-lookup"><span data-stu-id="cdf3b-177">Overview of document deletion policies</span></span>](document-deletion-policies.md)
  
[<span data-ttu-id="cdf3b-178">Criar uma política de exclusão de documentos</span><span class="sxs-lookup"><span data-stu-id="cdf3b-178">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)

