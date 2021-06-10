---
title: Referência de Prevenção contra Perda de Dados
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: low
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: material de referência de prevenção contra perda de dados
ms.openlocfilehash: 7e8494c0199d62951e7b5f01bb1b65e90e8584f2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878155"
---
# <a name="data-loss-prevention-reference"></a><span data-ttu-id="0f9c7-103">Referência de prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="0f9c7-103">Data loss prevention reference</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="0f9c7-104">Este é o tópico de referência não é mais o principal recurso para Microsoft 365 de prevenção contra perda de dados (DLP).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-104">This is reference topic is no longer the main resource for Microsoft 365 data loss prevention (DLP) information.</span></span> <span data-ttu-id="0f9c7-105">O conjunto de conteúdo DLP está sendo atualizado e reestruturado.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-105">The DLP content set is being updated and restructured.</span></span> <span data-ttu-id="0f9c7-106">Os tópicos abordados neste artigo mudarão para artigos novos e atualizados.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-106">The topics covered in this article will be moving to new, updated articles.</span></span> <span data-ttu-id="0f9c7-107">Para obter mais informações sobre DLP, consulte [Learn about data loss prevention](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-107">For more information about DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<!-- this topic needs to be split into smaller, more coherent ones. It is confusing as it is. -->
<!-- move this note to a more appropriate place, no topic should start with a note -->
> [!NOTE]
> <span data-ttu-id="0f9c7-108">Os recursos de prevenção contra perda de dados foram recentemente adicionados às mensagens de chat e de canal do Microsoft Teams para usuários licenciados para a Conformidade Avançada do Office 365, disponível como uma opção independente e está incluso na Conformidade do Office 365 E5 e no Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-108">Data loss prevention capabilities were recently added to Microsoft Teams chat and channel messages for users licensed for Office 365 Advanced Compliance, which is available as a standalone option and is included in Office 365 E5 and Microsoft 365 E5 Compliance.</span></span> <span data-ttu-id="0f9c7-109">Para saber mais sobre os requisitos de licenciamento, confira [Diretrizes do Licenciamento de Serviços no Nível de Locatário do Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).</span></span>



<!-- MOVED TO LEARN ABOUT To comply with business standards and industry regulations, organizations must protect sensitive information and prevent its inadvertent disclosure. Sensitive information can include financial data or personally identifiable information (PII) such as credit card numbers, social security numbers, or health records. With a data loss prevention (DLP) policy in the Office 365 Security &amp; Compliance Center, you can identify, monitor, and automatically protect sensitive information across Office 365.
  
With a DLP policy, you can:
  
- **Identify sensitive information across many locations, such as Exchange Online, SharePoint Online, OneDrive for Business, and Microsoft Teams.**
    
    For example, you can identify any document containing a credit card number that's stored in any OneDrive for Business site, or you can monitor just the OneDrive sites of specific people.
    
- **Prevent the accidental sharing of sensitive information**. 
    
    For example, you can identify any document or email containing a health record that's shared with people outside your organization, and then automatically block access to that document or block the email from being sent.
    
- **Monitor and protect sensitive information in the desktop versions of Excel, PowerPoint, and Word.**
    
    Just like in Exchange Online, SharePoint Online, and OneDrive for Business, these Office desktop programs include the same capabilities to identify sensitive information and apply DLP policies. DLP provides continuous monitoring when people share content in these Office programs.
    
- **Help users learn how to stay compliant without interrupting their workflow.**
    
    You can educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification. The same policy tips also appear in Outlook on the web, Outlook, Excel, PowerPoint, and Word.
    
- **View DLP alerts and reports showing content that matches your organization’s DLP policies.**
    
    To view alerts and metadata related to your DLP policies you can use the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md). You can also view policy match reports to assess how your organization is complying with a DLP policy. If a DLP policy allows users to override a policy tip and report a false positive, you can also view what users have reported

-->    
## <a name="create-and-manage-dlp-policies"></a><span data-ttu-id="0f9c7-110">Criar e gerenciar políticas DLP</span><span class="sxs-lookup"><span data-stu-id="0f9c7-110">Create and manage DLP policies</span></span>

<span data-ttu-id="0f9c7-111">Você cria e gerencia políticas DLP na página Prevenção Contra Perda de Dados no Centro de conformidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-111">You create and manage DLP policies on the Data loss prevention page in the Microsoft 365 Compliance center.</span></span>
  
![Página de Prevenção contra Perda de Dados no Centro de Conformidade &amp; Segurança do Office 365](../media/943fd01c-d7aa-43a9-846d-0561321a405e.png)
  
<!-- MOVED TO LEARN ABOUT ## What a DLP policy contains

A DLP policy contains a few basic things:
  
- Where to protect the content: **locations** such as Exchange Online, SharePoint Online, and OneDrive for Business sites, as well as Microsoft Teams chat and channel messages. 
    
- When and how to protect the content by enforcing **rules** comprised of: 
    
  - **Conditions** the content must match before the rule is enforced. For example, a rule might be configured to look only for content containing Social Security numbers that's been shared with people outside your organization. 
    
  - **Actions** that you want the rule to take automatically when content matching the conditions is found. For example, a rule might be configured to block access to a document and send both the user and compliance officer an email notification. -->
    
<span data-ttu-id="0f9c7-113">Você pode usar uma regra para atender a um requisito específico de proteção e depois usar uma política DLP para agrupar requisitos de proteção comuns, como todas as regras necessárias para manter a conformidade com uma regulamentação específica.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-113">You can use a rule to meet a specific protection requirement, and then use a DLP policy to group together common protection requirements, such as all of the rules needed to comply with a specific regulation.</span></span>
  
<span data-ttu-id="0f9c7-114">Por exemplo, você pode ter uma política DLP que ajuda a detectar a presença de informações sujeitas à lei americana HIPAA (Health Insurance Portability Accountability Act).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-114">For example, you might have a DLP policy that helps you detect the presence of information subject to the Health Insurance Portability and Accountability Act (HIPAA).</span></span> <span data-ttu-id="0f9c7-115">Essa política DLP pode ajudar a proteger dados HIPAA (objeto) em todos os sites do SharePoint Online e OneDrive for Business (local) ao encontrar qualquer documento com essas informações confidenciais que são compartilhadas com pessoas de fora da sua organização (condições) e, em seguida, bloquear o acesso ao documento e enviar uma notificação (ações).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-115">This DLP policy could help protect HIPAA data (the what) across all SharePoint Online sites and all OneDrive for Business sites (the where) by finding any document containing this sensitive information that's shared with people outside your organization (the conditions) and then blocking access to the document and sending a notification (the actions).</span></span> <span data-ttu-id="0f9c7-116">Esses requisitos são armazenados como regras individuais e agrupadas como uma política DLP para simplificar o gerenciamento e a geração de relatório.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-116">These requirements are stored as individual rules and grouped together as a DLP policy to simplify management and reporting.</span></span>
  
![O diagrama mostra que a política de DLP contém locais e regras](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)
  
<!-- MOVED TO LEARN ABOUT ### Locations

DLP policies are applied to sensitive items across Microsoft 365 locations and can be further scoped as detailed in this table.


|Location | Include/exclude by|
|---------|---------|
|Exchange email| distribution groups|
|SharePoint sites |sites |
|OneDrive accounts |accounts |
|Teams chat and channel messages |accounts |
|Windows 10 devices |user or group |
|Microsoft Cloud App Security |instance |
 -->

<span data-ttu-id="0f9c7-118">Se você optar por incluir grupos de distribuição específicos no Exchange, a política DLP será delimitada somente aos membros desse grupo.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-118">If you choose to include specific distribution groups in Exchange, the DLP policy will be scoped only to the members of that group.</span></span> <span data-ttu-id="0f9c7-119">Da mesma maneira, a exclusão de um grupo de distribuição excluirá todos os membros desse grupo de distribuição da avaliação de políticas.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-119">Similarly excluding a distribution group will exclude all the members of that distribution group from policy evaluation.</span></span> <span data-ttu-id="0f9c7-120">Você pode optar por criar uma política para os membros das listas de distribuição, grupos de distribuição dinâmicas e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-120">You can choose to scope a policy to the members of distribution lists, dynamic distribution groups, and security groups.</span></span> <span data-ttu-id="0f9c7-121">Uma política DLP pode conter, no máximo, 50 inclusões e exclusões.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-121">A DLP policy can contain no more than 50 such inclusions and exclusions.</span></span>

<span data-ttu-id="0f9c7-122">Se optar por incluir ou excluir sites específicos do SharePoint, uma política de DLP poderá conter até 100 inclusões e exclusões.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-122">If you choose to include or exclude specific SharePoint sites, a DLP policy can contain no more than 100 such inclusions and exclusions.</span></span> <span data-ttu-id="0f9c7-123">Embora esses limites existam, você pode excede-los ao ignorar uma política no âmbito da organização ou uma política que se aplica a locais inteiros.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-123">Although this limit exists, you can exceed this limit by applying either an org-wide policy or a policy that applies to entire locations.</span></span>

<span data-ttu-id="0f9c7-124">Se optar por incluir ou excluir contas ou grupos específicos do OneDrive, uma política DLP não poderá conter mais de 100 contas de usuários ou 50 grupos como inclusão ou exclusão.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-124">If you choose to include or exclude specific OneDrive accounts or groups, a DLP policy can contain no more than 100 user accounts or 50 groups as inclusion or exclusion.</span></span>

> [!NOTE]
> <span data-ttu-id="0f9c7-125">OneDrive de política de negócios usando contas de usuário ou grupos está em visualização pública.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-125">OneDrive for business policy scoping using user accounts or groups is in public preview.</span></span> 
  
### <a name="rules"></a><span data-ttu-id="0f9c7-126">Regras</span><span class="sxs-lookup"><span data-stu-id="0f9c7-126">Rules</span></span>

> [!NOTE]
> <span data-ttu-id="0f9c7-127">O comportamento padrão de uma política DLP, quando não há alerta configurado, não é o de alertar ou acionar.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-127">The default behavior of a DLP policy, when there is no alert configured, is not to alert or trigger.</span></span> <span data-ttu-id="0f9c7-128">Isso se aplica apenas aos tipos de informações padrão.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-128">This applies only to default information types.</span></span> <span data-ttu-id="0f9c7-129">Para tipos de informações personalizadas, o sistema alertará mesmo se não houver nenhuma ação definida na política.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-129">For custom information types, the system will alert even if there is no action defined in the policy.</span></span>

<span data-ttu-id="0f9c7-130">As regras aplicam os requisitos de negócios para o conteúdo da sua organização.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-130">Rules are what enforce your business requirements on your organization's content.</span></span> <span data-ttu-id="0f9c7-131">Uma política contém uma ou mais regras, e cada regra consiste em condições e ações.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-131">A policy contains one or more rules, and each rule consists of conditions and actions.</span></span> <span data-ttu-id="0f9c7-132">Para cada regra, quando as condições forem atendidas, as ações são executadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-132">For each rule, when the conditions are met, the actions are taken automatically.</span></span> <span data-ttu-id="0f9c7-133">As regras são executadas sequencialmente, começando pela prioridade mais alta em cada política.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-133">Rules are executed sequentially, starting with the highest-priority rule in each policy.</span></span>
  
<span data-ttu-id="0f9c7-134">Uma regra também fornece opções para notificar os usuários (com dicas de política e notificações por email) e os administradores (com relatórios de incidentes por email) cujo conteúdo correspondeu à regra.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-134">A rule also provides options to notify users (with policy tips and email notifications) and admins (with email incident reports) that content has matched the rule.</span></span>
  
<span data-ttu-id="0f9c7-135">Veja a seguir os componentes de uma regra, cada um explicado abaixo.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-135">Here are the components of a rule, each explained below.</span></span>
  
![Seções do editor regras DLP](../media/1859d504-b9c2-45ed-961b-a0092251acc2.png)
  
#### <a name="conditions"></a><span data-ttu-id="0f9c7-137">Condições</span><span class="sxs-lookup"><span data-stu-id="0f9c7-137">Conditions</span></span>

<span data-ttu-id="0f9c7-138">As condições são importantes porque elas determinam que tipos de informações confidenciais está procurando e quando uma ação deve ser executada.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-138">Conditions are important because they determine what types of information you're looking for, and when to take an action.</span></span> <span data-ttu-id="0f9c7-139">Por exemplo, você pode optar por ignorar o conteúdo com números de passaporte, a menos que o conteúdo contenha mais de 10 números e seja compartilhado com pessoas de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-139">For example, you might choose to ignore content containing passport numbers unless the content contains more than 10 such numbers and is shared with people outside your organization.</span></span>
  
<span data-ttu-id="0f9c7-140">As condições se concentram no **conteúdo**, como quais tipos de informações confidenciais está procurando e também no **contexto**, como com quem o documento é compartilhado.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-140">Conditions focus on the **content**, such as what types of sensitive information you're looking for, and also on the **context**, such as who the document is shared with.</span></span> <span data-ttu-id="0f9c7-141">Você pode usar condições para atribuir ações diferentes a diferentes níveis de risco.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-141">You can use conditions to assign different actions to different risk levels.</span></span> <span data-ttu-id="0f9c7-142">Por exemplo, o conteúdo confidencial compartilhado internamente pode diminuir o risco e exigir menos ações do que o conteúdo confidencial compartilhado com pessoas de fora da organização.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-142">For example, sensitive content shared internally might be lower risk and require fewer actions than sensitive content shared with people outside the organization.</span></span> 
  
![Lista que mostra as condições DLP disponíveis](../media/0fa43f90-d007-4506-ae93-43e8424fe103.png)
  
<span data-ttu-id="0f9c7-144">As condições disponíveis agora podem determinar se:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-144">The conditions now available can determine if:</span></span>
  
- <span data-ttu-id="0f9c7-145">O conteúdo contém um tipo de informação confidencial.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-145">Content contains a type of sensitive information.</span></span>
    
- <span data-ttu-id="0f9c7-146">O conteúdo contém um rótulo.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-146">Content contains a label.</span></span> <span data-ttu-id="0f9c7-147">Para saber mais, confira a seção a seguir [Usar um rótulo de retenção como condição em uma política de DLP](#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-147">For more information, see the below section [Using a retention label as a condition in a DLP policy](#using-a-retention-label-as-a-condition-in-a-dlp-policy).</span></span>
    
- <span data-ttu-id="0f9c7-148">O conteúdo é compartilhado com pessoas de fora ou de dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-148">Content is shared with people outside or inside your organization.</span></span>

  > [!NOTE]
  > <span data-ttu-id="0f9c7-149">Os usuários que têm contas não convidadas no Active Directory ou no locatário do Azure Active Directory de uma organização são considerados como pessoas dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-149">Users who have non-guest accounts in a host organization's Active Directory or Azure Active Directory tenant are considered as people inside the organization.</span></span>
    
#### <a name="types-of-sensitive-information"></a><span data-ttu-id="0f9c7-150">Tipos de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="0f9c7-150">Types of sensitive information</span></span>

<span data-ttu-id="0f9c7-151">Uma política DLP ajuda a proteger informações confidenciais, que são definidas como um **tipo de informações confidenciais**.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-151">A DLP policy can help protect sensitive information, which is defined as a **sensitive information type**.</span></span> <span data-ttu-id="0f9c7-152">O Microsoft 365 inclui definições para vários tipos comuns de informações confidenciais em diferentes regiões que estão prontos para uso, como um número de cartão de crédito, números de contas bancárias, números de carteiras de identidade e números de passaporte.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-152">Microsoft 365 includes definitions for many common sensitive information types across many different regions that are ready for you to use, such as a credit card number, bank account numbers, national ID numbers, and passport numbers.</span></span> 
  
![Lista de tipos de informações confidenciais disponíveis](../media/3eaa9911-bc94-44be-902f-363dbf3b07fe.png)
  
<span data-ttu-id="0f9c7-154">Quando uma política DLP procura por um tipo de informação confidencial, como um número de cartão de crédito, ela não procura simplesmente por um número de 16 dígitos.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-154">When a DLP policy looks for a sensitive information type such as a credit card number, it doesn't simply look for a 16-digit number.</span></span> <span data-ttu-id="0f9c7-155">Cada tipo de informação confidencial é definido e detectado usando uma combinação de:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-155">Each sensitive information type is defined and detected by using a combination of:</span></span>
  
- <span data-ttu-id="0f9c7-156">Palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-156">Keywords.</span></span>
    
- <span data-ttu-id="0f9c7-157">Funções internas para validar as somas de verificação ou a composição.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-157">Internal functions to validate checksums or composition.</span></span>
    
- <span data-ttu-id="0f9c7-158">Avaliação de expressões regulares para localizar correspondências padrão.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-158">Evaluation of regular expressions to find pattern matches.</span></span>
    
- <span data-ttu-id="0f9c7-159">Análise de outros conteúdos.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-159">Other content examination.</span></span>
    
<span data-ttu-id="0f9c7-160">Isso ajuda a detecção de DLP a alcançar um alto grau de precisão, reduzindo o número de falsos positivos que pode interromper o trabalho das pessoas.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-160">This helps DLP detection achieve a high degree of accuracy while reducing the number of false positives that can interrupt peoples' work.</span></span>
  
#### <a name="actions"></a><span data-ttu-id="0f9c7-161">Ações</span><span class="sxs-lookup"><span data-stu-id="0f9c7-161">Actions</span></span>

<span data-ttu-id="0f9c7-162">Quando o conteúdo corresponde a uma condição em uma regra, você pode aplicar ações para proteger automaticamente o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-162">When content matches a condition in a rule, you can apply actions to automatically protect the content.</span></span>
  
![Lista de ações DLP disponíveis](../media/8aef17fc-1e99-4ac7-adfc-0f2c9c1a0697.png)
  
<span data-ttu-id="0f9c7-164">Com as ações agora disponíveis, você pode:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-164">With the actions now available, you can:</span></span>
  
- <span data-ttu-id="0f9c7-165">**Restringir o acesso ao conteúdo** Dependendo das suas necessidades, você pode restringir o acesso ao conteúdo de três maneiras:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-165">**Restrict access to the content** Depending on your need, you can restrict access to content in three ways:</span></span>

  1. <span data-ttu-id="0f9c7-166">Restringir o acesso ao conteúdo para todos.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-166">Restrict access to content for everyone.</span></span>
  2. <span data-ttu-id="0f9c7-167">Restringir o acesso ao conteúdo para pessoas de fora da organização.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-167">Restrict access to content for people outside the organization.</span></span>
  3. <span data-ttu-id="0f9c7-168">Restringir o acesso a "Qualquer pessoa com o link".</span><span class="sxs-lookup"><span data-stu-id="0f9c7-168">Restrict access to "Anyone with the link."</span></span>

  <span data-ttu-id="0f9c7-169">Para conteúdo de site, significa que as permissões para o documento são restritas a todos, exceto o administrador principal do conjunto de sites, o proprietário do documento e a pessoa que modificou o documento pela última vez.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-169">For site content, this means that permissions for the document are restricted for everyone except the primary site collection administrator, document owner, and person who last modified the document.</span></span> <span data-ttu-id="0f9c7-170">Essas pessoas podem remover as informações confidenciais do documento ou executar outras ações corretivas.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-170">These people can remove the sensitive information from the document or take other remedial action.</span></span> <span data-ttu-id="0f9c7-171">Quando o documento estiver em conformidade, as permissões originais serão restauradas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-171">When the document is in compliance, the original permissions are automatically restored.</span></span> <span data-ttu-id="0f9c7-172">Quando o acesso a um documento é bloqueado, o documento é exibido com um ícone de dica de política especial na biblioteca do site.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-172">When access to a document is blocked, the document appears with a special policy tip icon in the library on the site.</span></span> 
    
  ![A dica de política mostrando acesso ao documento está bloqueada](../media/b6cefed3-d212-43d7-8534-4b92b26ebd50.png)
  
  <span data-ttu-id="0f9c7-174">Para conteúdo de email, essa ação bloqueia o envio da mensagem.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-174">For email content, this action blocks the message from being sent.</span></span> <span data-ttu-id="0f9c7-175">Dependendo de como a regra DLP estiver configurada, o remetente verá uma notificação de falha na entrega (se a regra usar uma notificação) ou uma dica de política e/ou notificação por email.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-175">Depending on how the DLP rule is configured, the sender sees an NDR or (if the rule uses a notification) a policy tip and/or email notification.</span></span>
    
  ![Aviso de que destinatários não autorizados devem ser removidos da mensagem](../media/302f9994-912d-41e7-861f-8a4539b3c285.png)
  
#### <a name="user-notifications-and-user-overrides"></a><span data-ttu-id="0f9c7-177">Notificações e substituições do usuário</span><span class="sxs-lookup"><span data-stu-id="0f9c7-177">User notifications and user overrides</span></span>

<span data-ttu-id="0f9c7-178">Você pode usar notificações e substituições para instruir usuários sobre políticas de DLP e ajudá-los a permanecer em conformidade sem bloquear seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-178">You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work.</span></span> <span data-ttu-id="0f9c7-179">Por exemplo, se um usuário tentar compartilhar um documento que contém informações confidenciais, uma política de DLP pode enviar uma notificação por email e mostrar uma dica de política no contexto da biblioteca de documentos que permite substituir a política se ele tivere uma justificativa de negócios.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-179">For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.</span></span>
  
![Seções de notificações e substituições do usuário do editor de regras DLP](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)
  
<span data-ttu-id="0f9c7-181">O email pode notificar a pessoa que enviou, compartilhou ou modificou o conteúdo por último e, no caso de conteúdo de sites, o administrador principal do conjunto de sites e o proprietário do documento.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-181">The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner.</span></span> <span data-ttu-id="0f9c7-182">Além disso, você pode adicionar ou remover quem quiser na notificação por email.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-182">In addition, you can add or remove whomever you choose from the email notification.</span></span>
  
<span data-ttu-id="0f9c7-183">Além de enviar uma notificação por email, uma notificação do usuário exibe uma dica de política:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-183">In addition to sending an email notification, a user notification displays a policy tip:</span></span>
  
- <span data-ttu-id="0f9c7-184">No Outlook e no Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-184">In Outlook and Outlook on the web.</span></span>
    
- <span data-ttu-id="0f9c7-185">Para o documento no SharePoint ou no site do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-185">For the document on a SharePoint Online or OneDrive for Business site.</span></span>
    
- <span data-ttu-id="0f9c7-186">No Excel, PowerPoint, e Word, quando o documento está armazenado em um site incluído em uma política DLP.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-186">In Excel, PowerPoint, and Word, when the document is stored on a site included in a DLP policy.</span></span>
    
<span data-ttu-id="0f9c7-187">A notificação de email e a dica de política explicam a razão do conflito do conteúdo com uma política DLP.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-187">The email notification and policy tip explain why content conflicts with a DLP policy.</span></span> <span data-ttu-id="0f9c7-188">Se você escolher, a notificação por email e a dica de política podem permitir que usuários substituam uma regra ao relatar um falso positivo ou fornecer uma justificativa de negócios.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-188">If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification.</span></span> <span data-ttu-id="0f9c7-189">Isso pode ajudar você a treinar os usuários sobre as políticas de DLP e aplicá-las sem impedir que as pessoas façam seu trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-189">This can help you educate users about your DLP policies and enforce them without preventing people from doing their work.</span></span> <span data-ttu-id="0f9c7-190">Informações sobre substituições e falsos positivos também são registradas para relatório (veja abaixo sobre os relatórios de DLP) e incluídas nos relatórios de incidentes (próxima seção), para que o responsável pela conformidade possa analisar regularmente essas informações.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-190">Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.</span></span>
  
<span data-ttu-id="0f9c7-191">Esta é a aparência de uma dica de política em uma conta do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-191">Here's what a policy tip looks like in a OneDrive for Business account.</span></span>
  
![Dica de política para um documento em uma conta do OneDrive](../media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 <span data-ttu-id="0f9c7-193">Para saber mais sobre as notificações de usuário e as dicas de política em políticas DLP, confira [Usar notificações e dicas de política](use-notifications-and-policy-tips.md).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-193">To learn more about user notifications and policy tips in DLP policies, see [Use notifications and policy tips](use-notifications-and-policy-tips.md).</span></span>

#### <a name="alerts-and-incident-reports"></a><span data-ttu-id="0f9c7-194">Relatórios de alertas e Incidentes</span><span class="sxs-lookup"><span data-stu-id="0f9c7-194">Alerts and Incident reports</span></span>

<span data-ttu-id="0f9c7-195">Quando uma regra é correspondida, você pode enviar um email de alerta ao responsável pela conformidade (ou a qualquer pessoa(s) que você escolher) com os detalhes do alerta.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-195">When a rule is matched, you can send an alert email to your compliance officer ( or any person(s) you choose) with details of the alert.</span></span> <span data-ttu-id="0f9c7-196">O email de alerta carregará um link do [Painel de Gerenciamento de Alertas DLP](dlp-configure-view-alerts-policies.md) que o responsável pela conformidade pode acessar para exibir os detalhes do alerta e eventos.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-196">This alert email will carry a link of the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md) which the compliance officer can go to view the details of alert and events.</span></span> <span data-ttu-id="0f9c7-197">O painel contém detalhes do evento que acionou o alerta junto com detalhes da política DLP combinada e o conteúdo confidencial detectado.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-197">The dashboard contains details of the event that triggered the alert along with details of the DLP policy matched and the sensitive content detected.</span></span>

<span data-ttu-id="0f9c7-198">Além disso, também pode ser enviado um relatório de incidentes com detalhes do evento.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-198">In addition, you can also send an incident report with details of the event.</span></span> <span data-ttu-id="0f9c7-199">Esse relatório inclui informações sobre o item que foi correspondido, o conteúdo real que correspondeu à regra e o nome da pessoa que modificou o conteúdo por último.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-199">This report includes information about the item that was matched, the actual content that matched the rule, and the name of the person who last modified the content.</span></span> <span data-ttu-id="0f9c7-200">Para mensagens de email, o relatório também inclui a mensagem original como anexo que corresponde a uma política DLP.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-200">For email messages, the report also includes as an attachment the original message that matches a DLP policy.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0f9c7-201">![Página para configurar relatórios de incidente](../media/Alerts-and-incident-report.png)</span><span class="sxs-lookup"><span data-stu-id="0f9c7-201">![Page for configuring incident reports](../media/Alerts-and-incident-report.png)</span></span>

<span data-ttu-id="0f9c7-202">O DLP verifica os e-mails de forma diferente da dos itens do SharePoint Online ou do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-202">DLP scans email differently from items in SharePoint Online or OneDrive for Business.</span></span> <span data-ttu-id="0f9c7-203">No Microsoft Office SharePoint Online e no Microsoft OneDrive for Business, a DLP verifica os itens existentes e também os novos e gera um alerta e relatório de incidentes sempre que uma correspondência é encontrada.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-203">In SharePoint Online and OneDrive for Business, DLP scans existing items as well as new ones and generates an alert and incident report whenever a match is found.</span></span> <span data-ttu-id="0f9c7-204">No Exchange Online, a DLP verifica apenas novas mensagens de email e gera um relatório se houver uma correspondência de política.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-204">In Exchange Online, DLP only scans new email messages and generates a report if there is a policy match.</span></span> <span data-ttu-id="0f9c7-205">O DLP ***não*** verifica ou combina os itens de e-mail existentes anteriormente que são armazenados em uma caixa de correio ou arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-205">DLP ***does not*** scan or match previously existing email items that are stored in a mailbox or archive.</span></span>
  
## <a name="grouping-and-logical-operators"></a><span data-ttu-id="0f9c7-206">Agrupamento e operadores lógicos</span><span class="sxs-lookup"><span data-stu-id="0f9c7-206">Grouping and logical operators</span></span>

<span data-ttu-id="0f9c7-207">Muitas vezes, sua política DLP tem um requisito direto, como identificar todo o conteúdo que contém um número de CPF.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-207">Often your DLP policy has a straightforward requirement, such as to identify all content that contains a U.S. Social Security Number.</span></span> <span data-ttu-id="0f9c7-208">No entanto, em outras situações, talvez seja necessário que sua política DLP identifique dados definidos de forma mais flexível.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-208">However, in other scenarios, your DLP policy might need to identify more loosely defined data.</span></span>
  
<span data-ttu-id="0f9c7-209">Por exemplo, para identificar conteúdo sujeito à HIPAA (Lei de Seguro de Saúde) dos EUA, você precisa procurar:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-209">For example, to identify content subject to the U.S. Health Insurance Act (HIPAA), you need to look for:</span></span>
  
- <span data-ttu-id="0f9c7-210">Conteúdo que apresente tipos específicos de informações confidenciais, como um Número de Seguro Social dos EUA ou Número da DEA (Agência de Combate às Drogas dos EUA).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-210">Content that contains specific types of sensitive information, such as a U.S. Social Security Number or Drug Enforcement Agency (DEA) Number.</span></span>
    
    <span data-ttu-id="0f9c7-211">E</span><span class="sxs-lookup"><span data-stu-id="0f9c7-211">AND</span></span>
    
- <span data-ttu-id="0f9c7-212">Conteúdo que é mais difícil de identificar, como comunicações sobre cuidados de um paciente ou descrições de serviços médicos fornecidos.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-212">Content that's more difficult to identify, such as communications about a patient's care or descriptions of medical services provided.</span></span> <span data-ttu-id="0f9c7-213">Identificar esse conteúdo requer a combinação de palavras-chave de listas de palavras-chave muito extensas, como a Classificação Internacional de Doenças (ICD-9-CM ou ICD-10-CM).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-213">Identifying this content requires matching keywords from very large keyword lists, such as the International Classification of Diseases (ICD-9-CM or ICD-10-CM).</span></span>
    
<span data-ttu-id="0f9c7-214">Você pode identificar facilmente esses dados definidos de forma mais flexível usando agrupamentos e operadores lógicos (E, OU).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-214">You can easily identify such loosely defined data by using grouping and logical operators (AND, OR).</span></span> <span data-ttu-id="0f9c7-215">Ao criar uma política DLP, você pode:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-215">When you create a DLP policy, you can:</span></span>
  
- <span data-ttu-id="0f9c7-216">Agrupar tipos de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-216">Group sensitive information types.</span></span>
    
- <span data-ttu-id="0f9c7-217">Escolher o operador lógico entre os tipos de informações confidenciais dentro de um grupo e entre os próprios grupos.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-217">Choose the logical operator between the sensitive information types within a group and between the groups themselves.</span></span>
    
### <a name="choosing-the-operator-within-a-group"></a><span data-ttu-id="0f9c7-218">Escolher o operador dentro de um grupo</span><span class="sxs-lookup"><span data-stu-id="0f9c7-218">Choosing the operator within a group</span></span>

<span data-ttu-id="0f9c7-219">Dentro de um grupo, você pode escolher se uma ou todas as condições desse grupo devem ser atendidas para que o conteúdo corresponda à regra.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-219">Within a group, you can choose whether any or all of the conditions in that group must be satisfied for the content to match the rule.</span></span>
  
![Grupo que mostra os operadores dentro do grupo](../media/6a12f1e8-112d-48ee-9a73-82b3dd0542e7.png)
  
### <a name="adding-a-group"></a><span data-ttu-id="0f9c7-221">Adicionar um grupo</span><span class="sxs-lookup"><span data-stu-id="0f9c7-221">Adding a group</span></span>

<span data-ttu-id="0f9c7-222">Você pode adicionar rapidamente um grupo, que pode ter suas próprias condições e operador dentro desse grupo.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-222">You can quickly add a group, which can have its own conditions and operator within that group.</span></span>
  
![Botão Adicionar Grupo](../media/5f72f292-d1f3-4f11-a911-a9f71e10abf6.png)
  
### <a name="choosing-the-operator-between-groups"></a><span data-ttu-id="0f9c7-224">Escolher o operador entre grupos</span><span class="sxs-lookup"><span data-stu-id="0f9c7-224">Choosing the operator between groups</span></span>

<span data-ttu-id="0f9c7-225">Entre grupos, você pode escolher se as condições em apenas um grupo ou todos os grupos devem ser atendidas para que o conteúdo corresponda à regra.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-225">Between groups, you can choose whether the conditions in just one group or all of the groups must be satisfied for the content to match the rule.</span></span>
  
<span data-ttu-id="0f9c7-226">Por exemplo, a política interna **HIPAA (Lei de Seguro de Saúde) dos EUA** tem uma regra que usa um operador **E** entre os grupos para que identifique o conteúdo que apresente:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-226">For example, the built-in **U.S. HIPAA** policy has a rule that uses an **AND** operator between the groups so that it identifies content that contains:</span></span> 
  
- <span data-ttu-id="0f9c7-227">do grupo **Identificadores PII** (pelo menos um número de CPF **OU** número da Agência de Combate às Drogas)</span><span class="sxs-lookup"><span data-stu-id="0f9c7-227">from the group **PII Identifiers** (at least one SSN number **OR** DEA number)</span></span> 
    
    <span data-ttu-id="0f9c7-228">**E**</span><span class="sxs-lookup"><span data-stu-id="0f9c7-228">**AND**</span></span>
    
- <span data-ttu-id="0f9c7-229">do grupo **Termos Médicos** (pelo menos uma palavra-chave do ICD-9-CM **OU** do ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="0f9c7-229">from the group **Medical Terms** (at least one ICD-9-CM keyword **OR** ICD-10-CM keyword)</span></span> 
    
![Grupos que mostram o operador entre grupos](../media/354aa77f-569c-4847-9dfe-605ee2bb28d1.png)
  
## <a name="the-priority-by-which-rules-are-processed"></a><span data-ttu-id="0f9c7-231">A prioridade em que as regras são processadas</span><span class="sxs-lookup"><span data-stu-id="0f9c7-231">The priority by which rules are processed</span></span>

<span data-ttu-id="0f9c7-232">Quando você cria regras em uma política, cada regra recebe uma prioridade na ordem em que ela é criada, ou seja, a regra criada primeiro tem a primeira prioridade, a regra criada em segundo lugar tem a segunda prioridade e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-232">When you create rules in a policy, each rule is assigned a priority in the order in which it's created — meaning, the rule created first has first priority, the rule created second has second priority, and so on.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0f9c7-233">![Regras na ordem de prioridade](../media/dlp-rules-in-priority-order.png)</span><span class="sxs-lookup"><span data-stu-id="0f9c7-233">![Rules in priority order](../media/dlp-rules-in-priority-order.png)</span></span>
  
<span data-ttu-id="0f9c7-234">Após configurar mais de uma política DLP, você pode alterar a prioridade de uma ou mais políticas.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-234">After you have set up more than one DLP policy, you can change the priority of one or more policies.</span></span> <span data-ttu-id="0f9c7-235">Para fazer isso, selecione uma política, clique em **Editar política** e use a lista **Prioridade** para especificar a prioridade.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-235">To do that, select a policy, choose **Edit policy**, and use the **Priority** list to specify its priority.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0f9c7-236">![Definir prioridade de uma política](../media/dlp-set-policy-priority.png)</span><span class="sxs-lookup"><span data-stu-id="0f9c7-236">![Set priority for a policy](../media/dlp-set-policy-priority.png)</span></span>

<span data-ttu-id="0f9c7-237">Quando o conteúdo é avaliado em relação às regras, estas são processadas na ordem de prioridade.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-237">When content is evaluated against rules, the rules are processed in priority order.</span></span> <span data-ttu-id="0f9c7-238">Se o conteúdo corresponde a várias regras, as regras são processadas na ordem de prioridade, e a ação mais restritiva será aplicada.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-238">If content matches multiple rules, the rules are processed in priority order and the most restrictive action is enforced.</span></span> <span data-ttu-id="0f9c7-239">Por exemplo, se o conteúdo corresponder a todas as regras a seguir, a Regra 3 será aplicada porque tem a prioridade mais alta, é a regra mais restritiva:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-239">For example, if content matches all of the following rules, Rule 3 is enforced because it's the highest priority, most restrictive rule:</span></span>
  
- <span data-ttu-id="0f9c7-240">Regra 1: apenas notifica os usuários</span><span class="sxs-lookup"><span data-stu-id="0f9c7-240">Rule 1: only notifies users</span></span>
    
- <span data-ttu-id="0f9c7-241">Regra 2: notifica os usuários, restringe o acesso e permite o usuário substituir</span><span class="sxs-lookup"><span data-stu-id="0f9c7-241">Rule 2: notifies users, restricts access, and allows user overrides</span></span>
    
- <span data-ttu-id="0f9c7-242">Regra 3: notifica os usuários, restringe o acesso e não permite o usuário substituir</span><span class="sxs-lookup"><span data-stu-id="0f9c7-242">Rule 3: notifies users, restricts access, and does not allow user overrides</span></span>
    
- <span data-ttu-id="0f9c7-243">Regra 4: apenas notifica os usuários</span><span class="sxs-lookup"><span data-stu-id="0f9c7-243">Rule 4: only notifies users</span></span>
    
- <span data-ttu-id="0f9c7-244">Regra 5: restringe o acesso</span><span class="sxs-lookup"><span data-stu-id="0f9c7-244">Rule 5: restricts access</span></span>
    
- <span data-ttu-id="0f9c7-245">Regra 6: notifica os usuários, restringe o acesso e não permite o usuário substituir</span><span class="sxs-lookup"><span data-stu-id="0f9c7-245">Rule 6: notifies users, restricts access, and does not allow user overrides</span></span>
    
<span data-ttu-id="0f9c7-246">Nesse exemplo, observe que as correspondências para todas as regras são registradas nos logs de auditoria e exibidas nos relatórios de DLP, embora apenas a regra mais restritiva seja aplicada.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-246">In this example, note that matches for all of the rules are recorded in the audit logs and shown in the DLP reports, even though only the most restrictive rule is enforced.</span></span>
  
<span data-ttu-id="0f9c7-247">Referente às dicas de política, observe que:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-247">Regarding policy tips, note that:</span></span>
  
- <span data-ttu-id="0f9c7-248">Apenas a dica de política da prioridade mais alta e restritiva será exibida.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-248">Only the policy tip from the highest priority, most restrictive rule will be shown.</span></span> <span data-ttu-id="0f9c7-249">Por exemplo, uma dica de política de uma regra que bloqueia o acesso ao conteúdo será mostrada em detrimento de uma dica de política de uma regra que simplesmente envia uma notificação.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-249">For example, a policy tip from a rule that blocks access to content will be shown over a policy tip from a rule that simply sends a notification.</span></span> <span data-ttu-id="0f9c7-250">Isso impede que as pessoas vejam uma cascata de dicas de política.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-250">This prevents people from seeing a cascade of policy tips.</span></span>
    
- <span data-ttu-id="0f9c7-251">Se as dicas de política na regra mais restritiva permitir que as pessoas substituam a regra, substituir essa regra também substitui quaisquer outras regras que o conteúdo correspondeu.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-251">If the policy tips in the most restrictive rule allow people to override the rule, then overriding this rule also overrides any other rules that the content matched.</span></span>
    
## <a name="tuning-rules-to-make-them-easier-or-harder-to-match"></a><span data-ttu-id="0f9c7-252">Ajustar as regras para que a correspondência seja mais fácil ou mais difícil</span><span class="sxs-lookup"><span data-stu-id="0f9c7-252">Tuning rules to make them easier or harder to match</span></span>

<span data-ttu-id="0f9c7-253">Após criar e ativar as políticas de DLP, algumas vezes ocorre esses problemas:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-253">After people create and turn on their DLP policies, they sometimes run into these issues:</span></span>
  
- <span data-ttu-id="0f9c7-254">Grande parte do conteúdo que **não é** confidencial corresponde com as regras, ou seja, há muitos falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-254">Too much content that **is not** sensitive information matches the rules — in other words, too many false positives.</span></span> 
    
- <span data-ttu-id="0f9c7-255">Pequena parte do conteúdo que **tem** informações confidenciais corresponde com as regras.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-255">Too little content that **is** sensitive information matches the rules.</span></span> <span data-ttu-id="0f9c7-256">Em outras palavras, as ações de proteção não estão sendo aplicadas nas informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-256">In other words, the protective actions aren't being enforced on the sensitive information.</span></span> 
    
<span data-ttu-id="0f9c7-257">Para resolver esses problemas, você pode regular suas regras ajustando a contagem de instância e a precisão da correspondência para dificultar ou facilitar a correspondência do conteúdo às regras.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-257">To address these issues, you can tune your rules by adjusting the instance count and match accuracy to make it harder or easier for content to match the rules.</span></span> <span data-ttu-id="0f9c7-258">Cada tipo de informação confidencial usado em uma regra tem uma contagem de instância e uma precisão de correspondência.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-258">Each sensitive information type used in a rule has both an instance count and match accuracy.</span></span>
  
### <a name="instance-count"></a><span data-ttu-id="0f9c7-259">Contagem de instâncias</span><span class="sxs-lookup"><span data-stu-id="0f9c7-259">Instance count</span></span>

<span data-ttu-id="0f9c7-260">A contagem de instâncias se refere à quantidade de ocorrências de um tipo específico de informação confidencial que deve estar presente para que o conteúdo corresponda à regra.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-260">Instance count means simply how many occurrences of a specific type of sensitive information must be present for content to match the rule.</span></span> <span data-ttu-id="0f9c7-261">Por exemplo, o conteúdo corresponde com a regra mostrada abaixo se entre 1 e 9 passaportes únicos</span><span class="sxs-lookup"><span data-stu-id="0f9c7-261">For example, content matches the rule shown below if between 1 and 9 unique U.S. or U.K.</span></span> <span data-ttu-id="0f9c7-262">dos EUA ou UE são identificados.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-262">passport numbers are identified.</span></span>

> [!NOTE]
> <span data-ttu-id="0f9c7-263">A contagem de instâncias inclui apenas correspondências **exclusivas** para palavras-chave e tipos de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-263">The instance count includes only **unique** matches for sensitive information types and keywords.</span></span> <span data-ttu-id="0f9c7-264">Por exemplo, se um email contém 10 ocorrências do mesmo número de cartão de crédito, as 10 ocorrências são contadas como uma única instância de um número de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-264">For example, if an email contains 10 occurrences of the same credit card number, those 10 occurrences count as a single instance of a credit card number.</span></span>
  
<span data-ttu-id="0f9c7-265">Para usar a contagem de instâncias para ajustar as regras, a orientação é simples:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-265">To use instance count to tune rules, the guidance is straightforward:</span></span>
  
- <span data-ttu-id="0f9c7-266">Para tornar a regra mais fácil para a correspondência, diminua a contagem **mín** e/ou aumente a contagem **máx**.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-266">To make the rule easier to match, decrease the **min** count and/or increase the **max** count.</span></span> <span data-ttu-id="0f9c7-267">Também é possível definir o **máx** para **qualquer** excluindo o valor numérico.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-267">You can also set **max** to **any** by deleting the numerical value.</span></span> 
    
- <span data-ttu-id="0f9c7-268">Para tornar a regra mais difícil para a correspondência, aumente a contagem **mín**.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-268">To make the rule harder to match, increase the **min** count.</span></span> 
    
<span data-ttu-id="0f9c7-269">Normalmente, você usa menos ações restritivas, como o envio de notificações ao usuário, em uma regra com uma contagem de instâncias inferior (por exemplo, 1-9).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-269">Typically, you use less restrictive actions, such as sending user notifications, in a rule with a lower instance count (for example, 1-9).</span></span> <span data-ttu-id="0f9c7-270">E usa ações mais restritivas, como restringir o acesso ao conteúdo sem permitir que o usuário faça substituição, em uma regra com uma contagem de instância superior (por exemplo, 10 – qualquer).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-270">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with a higher instance count (for example, 10-any).</span></span>
  
![Contagens de instância no editor de regra](../media/e7ea3c12-72c5-4bb3-9590-c924c665e84d.png)
  
### <a name="match-accuracy"></a><span data-ttu-id="0f9c7-272">Precisão de correspondência</span><span class="sxs-lookup"><span data-stu-id="0f9c7-272">Match accuracy</span></span>

<span data-ttu-id="0f9c7-273">Conforme descrito acima, o tipo de informação confidencial é definido e detectado usando uma combinação de diferentes tipos de evidências.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-273">As described above, a sensitive information type is defined and detected by using a combination of different types of evidence.</span></span> <span data-ttu-id="0f9c7-274">Em geral, um tipo de informação confidencial é definido por várias dessas combinações, chamadas padrões.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-274">Commonly, a sensitive information type is defined by multiple such combinations, called patterns.</span></span> <span data-ttu-id="0f9c7-275">Um padrão que requer menos evidências tem uma precisão de correspondência inferior (ou nível de confiança), enquanto um padrão que exige mais evidências tem uma maior precisão de correspondência (ou nível de confiança).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-275">A pattern that requires less evidence has a lower match accuracy (or confidence level), while a pattern that requires more evidence has a higher match accuracy (or confidence level).</span></span> <span data-ttu-id="0f9c7-276">Para saber mais sobre os padrões reais e os níveis de confiança usados por todos os tipos de informações confidenciais, consulte [Definições da entidade do tipo de informações confidenciais](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-276">To learn more about the actual patterns and confidence levels used by every sensitive information type, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md).</span></span>
  
<span data-ttu-id="0f9c7-277">Por exemplo, o tipo de informação confidencial chamado Número de Cartão de Crédito é definido por dois padrões:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-277">For example, the sensitive information type named Credit Card Number is defined by two patterns:</span></span>
  
- <span data-ttu-id="0f9c7-278">Um padrão com confiança de 65% que exige:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-278">A pattern with 65% confidence that requires:</span></span>
    
  - <span data-ttu-id="0f9c7-279">Um número no formato de um número de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-279">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="0f9c7-280">Um número que passa na soma de verificação.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-280">A number that passes the checksum.</span></span>
    
- <span data-ttu-id="0f9c7-281">Um padrão com confiança de 85% que exige:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-281">A pattern with 85% confidence that requires:</span></span>
    
  - <span data-ttu-id="0f9c7-282">Um número no formato de um número de cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-282">A number in the format of a credit card number.</span></span>
    
  - <span data-ttu-id="0f9c7-283">Um número que passa na soma de verificação.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-283">A number that passes the checksum.</span></span>
    
  - <span data-ttu-id="0f9c7-284">Uma palavra-chave ou uma data de validade no formato certo.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-284">A keyword or an expiration date in the right format.</span></span>
    
<span data-ttu-id="0f9c7-285">Você pode usar esses níveis de confiança (ou precisão de correspondência) em suas regras.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-285">You can use these confidence levels (or match accuracy) in your rules.</span></span> <span data-ttu-id="0f9c7-286">Normalmente, você usa menos ações restritivas, como o envio de notificações ao usuário, em uma regra com uma precisão de correspondência inferior.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-286">Typically, you use less restrictive actions, such as sending user notifications, in a rule with lower match accuracy.</span></span> <span data-ttu-id="0f9c7-287">E usa ações mais restritivas, como restringir o acesso ao conteúdo sem permitir que o usuário faça uma substituição, em uma regra com uma precisão de correspondência superior.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-287">And you use more restrictive actions, such as restricting access to content without allowing user overrides, in a rule with higher match accuracy.</span></span>
  
<span data-ttu-id="0f9c7-288">É importante compreender que quando um tipo específico de informação confidencial, como um número de cartão de crédito, é identificado no conteúdo, somente um único nível de confiança é retornado:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-288">It's important to understand that when a specific type of sensitive information, such as a credit card number, is identified in content, only a single confidence level is returned:</span></span>
  
- <span data-ttu-id="0f9c7-289">Se todas as correspondências forem para um único padrão, o nível de confiança para aquele padrão será retornado.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-289">If all of the matches are for a single pattern, the confidence level for that pattern is returned.</span></span>
    
- <span data-ttu-id="0f9c7-290">Se houver correspondências para mais de um padrão (ou seja, há correspondências com dois níveis de confiança diferentes), o nível de confiança maior do que qualquer um dos padrões únicos sozinhos será retornado.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-290">If there are matches for more than one pattern (that is, there are matches with two different confidence levels), a confidence level higher than any of the single patterns alone is returned.</span></span> <span data-ttu-id="0f9c7-291">Esta é a parte desafiadora.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-291">This is the tricky part.</span></span> <span data-ttu-id="0f9c7-292">Por exemplo, para um cartão de crédito, se os padrões de 65% e 85% forem atendidos, o nível de confiança retornado para aquele tipo de informação confidencial será maior que 90%, pois quanto mais evidências, mais confiança.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-292">For example, for a credit card, if both the 65% and 85% patterns are matched, the confidence level returned for that sensitive information type is greater than 90% because more evidence means more confidence.</span></span>
    
<span data-ttu-id="0f9c7-293">Portanto, se você quiser criar duas regras mutuamente exclusivas para cartões de crédito, uma para a precisão de correspondência de 65% e outro para a precisão de correspondência de 85%, os intervalos para a precisão de correspondência serão parecidos com isto:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-293">So if you want to create two mutually exclusive rules for credit cards, one for the 65% match accuracy and one for the 85% match accuracy, the ranges for match accuracy would look like this.</span></span> <span data-ttu-id="0f9c7-294">A primeira regra pega apenas as correspondências ao padrão de 65%.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-294">The first rule picks up only matches of the 65% pattern.</span></span> <span data-ttu-id="0f9c7-295">A segunda regra pega as correspondências com **pelo menos uma** correspondência de 85% e **pode ter** outras correspondências de confiança inferiores.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-295">The second rule picks up matches with **at least one** 85% match and **can potentially have** other lower-confidence matches.</span></span> 
  
![Duas regras com intervalos diferentes para precisão de correspondência](../media/21bdfe36-7a91-4347-8098-11809a92f9a4.png)
  
<span data-ttu-id="0f9c7-297">Por essas razões, a orientação para a criação de regras com diferentes precisões de correspondência é:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-297">For these reasons, the guidance for creating rules with different match accuracies is:</span></span>
  
- <span data-ttu-id="0f9c7-298">O menor nível de confiança normalmente usa o mesmo valor para **mín** e **máx** (não um intervalo).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-298">The lowest confidence level typically uses the same value for **min** and **max** (not a range).</span></span> 
    
- <span data-ttu-id="0f9c7-299">O nível mais alto de confiança é um intervalo entre o valor logo acima do nível de confiança inferior a 100.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-299">The highest confidence level is typically a range from just above the lower confidence level to 100.</span></span>
    
- <span data-ttu-id="0f9c7-300">Qualquer nível de confiança intermediário normalmente varia de um valor logo acima do nível de confiança inferior para um valor logo abaixo do nível de confiança superior.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-300">Any in-between confidence levels typically range from just above the lower confidence level to just below the higher confidence level.</span></span>
    
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="0f9c7-301">Usar um rótulo de retenção como condição em uma política DLP</span><span class="sxs-lookup"><span data-stu-id="0f9c7-301">Using a retention label as a condition in a DLP policy</span></span>

<span data-ttu-id="0f9c7-302">Ao usar um [rótulo de retenção](retention.md#retention-labels) criado e publicado anteriormente como condição em uma política DLP, há algumas coisas a serem observadas:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-302">When you use a previously created and published [retention label](retention.md#retention-labels) as a condition in a DLP policy, there are some things to be aware of:</span></span>

- <span data-ttu-id="0f9c7-303">O rótulo de retenção deve ser criado e publicado antes de tentar usá-lo como condição em uma política DLP.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-303">The retention label must be created and published before you attempt to use it as a condition in a DLP policy.</span></span>
- <span data-ttu-id="0f9c7-304">Os rótulos de retenção publicados podem levar de um a sete dias para sincronização. Para obter mais informações, confira [Quando os rótulos de retenção se tornam disponíveis para aplicar](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) para rótulos de retenção publicados em uma política de retenção e [Quanto tempo leva para os rótulos de retenção entrarem em vigor](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect) para os rótulos de retenção que são publicados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-304">Published retention labels can take from one to seven days to sync. For more information, see [When retention labels become available to apply](create-apply-retention-labels.md#when-retention-labels-become-available-to-apply) for retention labels published in a retention policy, and [How long it takes for retention labels to take effect](apply-retention-labels-automatically.md#how-long-it-takes-for-retention-labels-to-take-effect) for retention labels that are auto-published.</span></span>
- <span data-ttu-id="0f9c7-305">O uso de um rótulo de retenção em uma política \*\*só tem suporte para itens do Microsoft Office SharePoint Online e OneDrive\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-305">Using a retention label in a policy \*\*is only supported for items in SharePoint and OneDrive\*\*\*.</span></span>

  ![Rótulos como uma condição](../media/5b1752b4-a129-4a88-b010-8dcf8a38bb09.png)

  <span data-ttu-id="0f9c7-307">Talvez você queira usar um rótulo de retenção em uma política DLP se tiver itens que estão sob retenção e descarte, e também aplicar outros controles a eles, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-307">You might want to use a retention label in a DLP policy if you have items that are under retention and disposition, and you also want to apply other controls to them, for example:</span></span>

  - <span data-ttu-id="0f9c7-308">Você publicou um rótulo de retenção denominado **ano fiscal 2018**, que quando aplicado aos documentos fiscais de 2018 armazenados no SharePoint, os retém por dez anos e só após esse prazo os descarta.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-308">You published a retention label named **tax year 2018**, which when applied to tax documents from 2018 that are stored in SharePoint retains them for 10 years then disposes of them.</span></span> <span data-ttu-id="0f9c7-309">Use também uma política DLP para impedir que itens sejam compartilhados fora da organização.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-309">You also don't want those items being shared outside your organization, which you can do with a DLP policy.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="0f9c7-310">Você receberá a seguinte mensagem de erro se especificar um rótulo de retenção como uma condição em uma política DLP e também incluir o Exchange e/ou Teams como um local: **"não há suporte para a proteção de conteúdo rotulado em mensagens de email e equipes. Remova a etiqueta a seguir ou desative o Exchange e o Teams como um local."**</span><span class="sxs-lookup"><span data-stu-id="0f9c7-310">You'll get this error if you specify a retention label as a condition in a DLP policy and you also include Exchange and/or Teams as a location: **"Protecting labeled content in email and teams messages isn't supported. Either remove the label below or turn off Exchange and Teams as a location."**</span></span> <span data-ttu-id="0f9c7-311">Isso ocorre porque o transporte do Exchange não avalia os metadados do rótulo durante o envio e a entrega da mensagem.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-311">This is because Exchange transport does not evaluate the label metadata during message submission and delivery.</span></span> 

### <a name="using-a-sensitivity-label-as-a-condition-in-a-dlp-policy"></a><span data-ttu-id="0f9c7-312">Usar um rótulo de confidencialidade como condição em uma política DLP</span><span class="sxs-lookup"><span data-stu-id="0f9c7-312">Using a sensitivity label as a condition in a DLP policy</span></span>

<span data-ttu-id="0f9c7-313">[Saiba mais](./dlp-sensitivity-label-as-condition.md) sobre como usar o rótulo de sensibilidade como condição nas políticas de DLP.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-313">[Learn more](./dlp-sensitivity-label-as-condition.md) about using Sensitivity label as a condition in DLP policies.</span></span>
  
### <a name="how-this-feature-relates-to-other-features"></a><span data-ttu-id="0f9c7-314">Como esse recurso se relaciona a outros recursos</span><span class="sxs-lookup"><span data-stu-id="0f9c7-314">How this feature relates to other features</span></span>

<span data-ttu-id="0f9c7-315">Diversos recursos podem ser aplicados ao conteúdo com informações confidenciais:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-315">Several features can be applied to content containing sensitive information:</span></span>
  
- <span data-ttu-id="0f9c7-316">Um [rótulo de retenção e uma política de retenção](retention.md) podem impor ações de **retenção** nesse conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-316">A [retention label and a retention policy](retention.md) can both enforce **retention** actions on this content.</span></span> 
    
- <span data-ttu-id="0f9c7-317">Uma política de DLP pode impor ações de **proteção** nesse conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-317">A DLP policy can enforce **protection** actions on this content.</span></span> <span data-ttu-id="0f9c7-318">E antes de aplicar essas ações, uma política de DLP pode exigir que outras condições sejam atendidas além do conteúdo que contém um rótulo.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-318">And before enforcing these actions, a DLP policy can require other conditions to be met in addition to the content containing a label.</span></span> 
    
![Diagrama de recursos que podem ser aplicados a informações confidenciais](../media/dd410f97-a3a3-455c-a1e9-7ed8ae6893d6.png)
  
<span data-ttu-id="0f9c7-320">Observe que uma política de DLP tem um recurso de detecção mais avançado do que um rótulo ou política de retenção aplicada a informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-320">Note that a DLP policy has a richer detection capability than a label or retention policy applied to sensitive information.</span></span> <span data-ttu-id="0f9c7-321">Uma política de DLP pode impor ações de proteção ao conteúdo que contiver informações confidenciais e se as informações confidenciais forem removidas do conteúdo, essas ações de proteção serão desfeitas da próxima vez que o conteúdo for verificado.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-321">A DLP policy can enforce protective actions on content containing sensitive information, and if the sensitive information is removed from the content, those protective actions are undone the next time the content's scanned.</span></span> <span data-ttu-id="0f9c7-322">Mas se uma política ou rótulo de retenção for aplicado ao conteúdo com informações confidenciais, essa será uma ação única que não será desfeita, mesmo se as informações confidenciais forem removidas.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-322">But if a retention policy or label is applied to content containing sensitive information, that's a one-time action that won't be undone even if the sensitive information is removed.</span></span>
  
<span data-ttu-id="0f9c7-323">Usando um rótulo como uma condição em uma política de DLP, você pode aplicar ações de retenção e proteção no conteúdo com esse rótulo.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-323">By using a label as a condition in a DLP policy, you can enforce both retention and protection actions on content with that label.</span></span> <span data-ttu-id="0f9c7-324">Pense no conteúdo com um rótulo exatamente como um conteúdo com informações confidenciais – tanto um rótulo quanto um tipo de informação confidencial são propriedades usadas para classificar o conteúdo, para poder impor ações para esse conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-324">You can think of content containing a label exactly like content containing sensitive information - both a label and a sensitive information type are properties used to classify content, so that you can enforce actions on that content.</span></span>
  
![Diagrama de política de DLP usando rótulo como uma condição](../media/4538fd8f-fb74-4743-bc22-a5de33adfebb.png)
  
## <a name="simple-settings-vs-advanced-settings"></a><span data-ttu-id="0f9c7-326">Configurações simples versus configurações avançadas</span><span class="sxs-lookup"><span data-stu-id="0f9c7-326">Simple settings vs. advanced settings</span></span>

<span data-ttu-id="0f9c7-327">Ao criar uma política DLP, decida entre configurações simples ou avançadas:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-327">When you create a DLP policy, you'll choose between simple or advanced settings:</span></span>
  
- <span data-ttu-id="0f9c7-328">**Configurações simples** facilitam a criação do tipo mais comum de política DLP sem usar o editor de regras para criar ou modificar regras.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-328">**Simple settings** make it easy to create the most common type of DLP policy without using the rule editor to create or modify rules.</span></span> 
    
- <span data-ttu-id="0f9c7-329">**Configurações avançadas** usam o editor de regras para oferecer controle completo sobre cada configuração para a sua política DLP.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-329">**Advanced settings** use the rule editor to give you complete control over every setting for your DLP policy.</span></span> 
    
<span data-ttu-id="0f9c7-330">As configurações simples e as avançadas funcionam exatamente da mesma forma, aplicando regras compostas por condições e ações. A única diferença e que, com as configurações simples, você não ver o editor de regras.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-330">Don't worry, under the covers, simple settings and advanced settings work exactly the same, by enforcing rules comprised of conditions and actions—only with simple settings, you don't see the rule editor.</span></span> <span data-ttu-id="0f9c7-331">Trata-se de uma maneira rápida de criar uma política DLP.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-331">It's a quick way to create a DLP policy.</span></span>
  
### <a name="simple-settings"></a><span data-ttu-id="0f9c7-332">Configurações simples</span><span class="sxs-lookup"><span data-stu-id="0f9c7-332">Simple settings</span></span>

<span data-ttu-id="0f9c7-333">Sem dúvida, o cenário mais comum de DLP é criar uma política para ajudar a evitar que um conteúdo com informações confidenciais seja compartilhado com pessoas fora da sua organização e realizar uma ação corretiva automática, como restringir quem pode acessar o conteúdo, enviar notificações ao usuário final ou ao administrador e auditar o evento para investigação posterior.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-333">By far, the most common DLP scenario is creating a policy to help protect content containing sensitive information from being shared with people outside your organization, and taking an automatic remediating action such as restricting who can access the content, sending end-user or admin notifications, and auditing the event for later investigation.</span></span> <span data-ttu-id="0f9c7-334">As pessoas usam a DLP para ajudar a evitar a divulgação acidental de informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-334">People use DLP to help prevent the inadvertent disclosure of sensitive information.</span></span>
  
<span data-ttu-id="0f9c7-335">Para simplificar essa meta, ao criar uma política DLP, você pode escolher **Usar configurações simples**.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-335">To simplify achieving this goal, when you create a DLP policy, you can choose **Use simple settings**.</span></span> <span data-ttu-id="0f9c7-336">Essas configurações fornecem todos os elementos necessários para implementar a política DLP mais comum, sem precisar acessar o editor de regras.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-336">These settings provide everything you need to implement the most common DLP policy, without having to go into the rule editor.</span></span>
  
![Opções de DLP para configurações simples e avançadas](../media/33c93824-ead5-43b6-9c3e-fd1630c92a7d.png)
  
### <a name="advanced-settings"></a><span data-ttu-id="0f9c7-338">Configurações avançadas</span><span class="sxs-lookup"><span data-stu-id="0f9c7-338">Advanced settings</span></span>

<span data-ttu-id="0f9c7-339">Se você precisa criar políticas DLP mais personalizadas, pode escolher **Usar configurações avançadas**.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-339">If you need to create more customized DLP policies, you can choose **Use advanced settings**.</span></span>
  
<span data-ttu-id="0f9c7-340">As configurações avançadas apresentam o editor de regras, no qual você tem controle total sobre todas as opções possíveis, incluindo a contagem de instâncias e a precisão de correspondência (nível de confiança) de cada regra.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-340">The advanced settings present you with the rule editor, where you have full control over every possible option, including the instance count and match accuracy (confidence level) for each rule.</span></span>
  
<span data-ttu-id="0f9c7-341">Para acessar rapidamente uma seção, clique em um item na navegação superior do editor de regras para ir até essa seção abaixo.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-341">To jump to a section quickly, click an item in the top navigation of the rule editor to go to that section below.</span></span>
  
![Menu de navegação superior do editor de regras DLP](../media/c527b97f-ca53-4c79-ad19-1a63be8a8ecc.png)
  
## <a name="dlp-policy-templates"></a><span data-ttu-id="0f9c7-343">Modelos de política DLP</span><span class="sxs-lookup"><span data-stu-id="0f9c7-343">DLP policy templates</span></span>

<span data-ttu-id="0f9c7-344">A primeira etapa na criação de uma política DLP é escolher quais informações serão protegidas.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-344">The first step in creating a DLP policy is choosing what information to protect.</span></span> <span data-ttu-id="0f9c7-345">A partir de um modelo DLP, você economiza o trabalho de criar um novo conjunto de regras do zero e descobrir quais tipos de informações devem ser incluídas por padrão.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-345">By starting with a DLP template, you save the work of building a new set of rules from scratch, and figuring out which types of information should be included by default.</span></span> <span data-ttu-id="0f9c7-346">Em seguida, você pode adicionar ou modificar esses requisitos para ajustar a regra para atender aos requisitos específicos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-346">You can then add to or modify these requirements to fine tune the rule to meet your organization's specific requirements.</span></span>
  
<span data-ttu-id="0f9c7-347">Um modelo de política DLP pré-configurado pode ajudar a detectar tipos específicos de informações confidenciais, como dados de HIPAA, dados de PCI-DSS, dados da Lei Gramm-Leach-Bliley ou até informações de identificação pessoal (PII) específicas de localidade.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-347">A preconfigured DLP policy template can help you detect specific types of sensitive information, such as HIPAA data, PCI-DSS data, Gramm-Leach-Bliley Act data, or even locale-specific personally identifiable information (P.I.).</span></span> <span data-ttu-id="0f9c7-348">Para facilitar a localização e a proteção de tipos comuns de informações confidenciais, os modelos de política incluídos no Microsoft 365 já contêm os tipos mais comuns de informações confidenciais necessários para você começar.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-348">To make it easy for you to find and protect common types of sensitive information, the policy templates included in Microsoft 365 already contain the most common sensitive information types necessary for you to get started.</span></span>
  
![Lista de modelos para políticas de prevenção contra perda de dados com o foco no modelo para a Lei Patriota dos EUA](../media/791b2403-430b-4987-8643-cc20abbd8148.png)
  
<span data-ttu-id="0f9c7-350">Sua organização também pode ter suas próprias exigências específicas e, nesse caso, você pode criar uma política DLP do zero, escolhendo a opção **Política personalizada**.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-350">Your organization may also have its own specific requirements, in which case you can create a DLP policy from scratch by choosing the **Custom policy** option.</span></span> <span data-ttu-id="0f9c7-351">Uma política personalizada é vazia e não contém regras pré-criadas.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-351">A custom policy is empty and contains no premade rules.</span></span> 
  
<!-- ## Roll out DLP policies gradually with test mode

rehomed to Plan for DLP

When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them. For example, you don't want a new DLP policy to unintentionally block access to thousands of documents that people require access to in order to get their work done.
  
If you're creating DLP policies with a large potential impact, we recommend following this sequence:
  
1. **Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact. You can use DLP reports to view the number, location, type, and severity of policy matches. Based on the results, you can fine tune the rules as needed. In test mode, DLP policies will not impact the productivity of people working in your organization. 
    
2. **Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the rules that are going to be applied. At this stage, you can also ask users to report false positives so that you can further refine the rules. 
    
3. **Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected. Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend. 

    ![Options for using test mode and turning on policy](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    You can turn off a DLP policy at any time, which affects all rules in the policy. However, each rule can also be turned off individually by toggling its status in the rule editor.

    ![Options for turning off a rule in a policy](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    You can also change the priority of multiple rules in a policy. To do that, open a policy for editing. In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.

    > [!div class="mx-imgBorder"]
    > ![Set rule priority](../media/dlp-set-rule-priority.png)-->
  
## <a name="dlp-reports"></a><span data-ttu-id="0f9c7-352">Relatórios DLP</span><span class="sxs-lookup"><span data-stu-id="0f9c7-352">DLP reports</span></span>

<span data-ttu-id="0f9c7-353">Após criar e ativar as políticas de DLP, verifique se elas estão funcionando conforme esperado e se estão ajudando a manter a conformidade.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-353">After you create and turn on your DLP policies, you'll want to verify that they're working as you intended and helping you stay compliant.</span></span> <span data-ttu-id="0f9c7-354">Com os relatórios de DLP, você pode exibir rapidamente o número de correspondências de regra e política de DLP ao longo do tempo e o número de falsos positivos e substituições.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-354">With DLP reports, you can quickly view the number of DLP policy and rule matches over time, and the number of false positives and overrides.</span></span> <span data-ttu-id="0f9c7-355">Para cada relatório, você pode filtrar as correspondências por local, intervalo de tempo e até mesmo restringi-lo a uma diretiva, regra ou ação específica.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-355">For each report, you can filter those matches by location, time frame, and even narrow it down to a specific policy, rule, or action.</span></span>
  
<span data-ttu-id="0f9c7-356">Com os relatórios de DLP, você pode obter ideias de negócios e:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-356">With the DLP reports, you can get business insights and:</span></span>
  
- <span data-ttu-id="0f9c7-357">Se concentrar em períodos de tempo específicos e entender os motivos para picos e tendências.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-357">Focus on specific time periods and understand the reasons for spikes and trends.</span></span>
    
- <span data-ttu-id="0f9c7-358">Descobrir os processos de negócios que violam as políticas de conformidade da sua organização.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-358">Discover business processes that violate your organization's compliance policies.</span></span>
    
- <span data-ttu-id="0f9c7-359">Compreender qualquer impacto nos negócios das políticas de DLP.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-359">Understand any business impact of the DLP policies.</span></span>
    
<span data-ttu-id="0f9c7-360">Além disso, você pode usar os relatórios de DLP para ajustar suas políticas de DLP conforme as executar.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-360">In addition, you can use the DLP reports to fine tune your DLP policies as you run them.</span></span>
  
![Painel de Relatórios no Centro de Conformidade e Segurança](../media/6d741252-a0ce-4429-95ba-6c857ecc9a7e.png)
  
## <a name="how-dlp-policies-work"></a><span data-ttu-id="0f9c7-362">Como funcionam as políticas de DLP</span><span class="sxs-lookup"><span data-stu-id="0f9c7-362">How DLP policies work</span></span>

<span data-ttu-id="0f9c7-p149">A DLP detecta informações confidenciais usando análise profunda de conteúdo (não apenas uma simples verificação de texto). Essa análise profunda de conteúdo usa correspondências de palavra-chave, correspondências de dicionário, a avaliação de expressões regulares, funções internas e outros métodos para detectar conteúdos que violam as políticas de DLP. Possivelmente, apenas uma pequena porcentagem dos seus dados é considerada confidencial. Uma política de DLP pode identificar, monitorar e proteger automaticamente apenas esses dados, sem impedir ou afetar as pessoas que trabalham com o restante do seu conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-p149">DLP detects sensitive information by using deep content analysis (not just a simple text scan). This deep content analysis uses keyword matches, dictionary matches, the evaluation of regular expressions, internal functions, and other methods to detect content that matches your DLP policies. Potentially only a small percentage of your data is considered sensitive. A DLP policy can identify, monitor, and automatically protect just that data, without impeding or affecting people who work with the rest of your content.</span></span>
  
### <a name="policies-are-synced"></a><span data-ttu-id="0f9c7-367">As políticas são sincronizadas</span><span class="sxs-lookup"><span data-stu-id="0f9c7-367">Policies are synced</span></span>

<span data-ttu-id="0f9c7-368">Após criar uma política de DLP no Centro de Segurança &amp; Conformidade, ela é armazenada em um repositório central de políticas e sincronizada com várias fontes de conteúdo, incluindo:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-368">After you create a DLP policy in the Security &amp; Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="0f9c7-369">Exchange Online, e de lá para o Outlook na Web e o Outlook.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-369">Exchange Online, and from there to Outlook on the web and Outlook.</span></span>
    
- <span data-ttu-id="0f9c7-370">Sites do OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-370">OneDrive for Business sites.</span></span>
    
- <span data-ttu-id="0f9c7-371">Sites do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-371">SharePoint Online sites.</span></span>
    
- <span data-ttu-id="0f9c7-372">Programas da área de trabalho do Office (Excel, PowerPoint e Word)</span><span class="sxs-lookup"><span data-stu-id="0f9c7-372">Office desktop programs (Excel, PowerPoint, and Word).</span></span>

- <span data-ttu-id="0f9c7-373">Mensagens de canais e de chats do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-373">Microsoft Teams channels and chat messages.</span></span>
    
<span data-ttu-id="0f9c7-374">Após a sincronização da política com os locais corretos, ela começa avaliar o conteúdo e aplicar as ações.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-374">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>
<!-- what is the time delay for first deployment of a policy and what is the sync schedule? -->
  
### <a name="policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites"></a><span data-ttu-id="0f9c7-375">Avaliação da política em sites do OneDrive for Business e do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="0f9c7-375">Policy evaluation in OneDrive for Business and SharePoint Online sites</span></span>

<span data-ttu-id="0f9c7-376">Em todos os seus sites do SharePoint Online e sites do OneDrive for Business, os documentos estão em constante mudança — eles estão continuamente sendo criados, editados, compartilhados, movidos e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-376">Across all of your SharePoint Online sites and OneDrive for Business sites, documents are constantly changing — they're continually being created, edited, shared, and so on.</span></span> <span data-ttu-id="0f9c7-377">Isso significa que os documentos podem conflitar ou ficar em conformidade com uma política de DLP a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-377">This means documents can conflict or become compliant with a DLP policy at any time.</span></span> <span data-ttu-id="0f9c7-378">Por exemplo, uma pessoa pode carregar um documento que não contém nenhuma informação confidencial para seus sites de equipe, mas, posteriormente, outra pessoa pode editar o mesmo documento e adicionar informações confidenciais a ele.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-378">For example, a person can upload a document that contains no sensitive information to their team site, but later, a different person can edit the same document and add sensitive information to it.</span></span>
  
<span data-ttu-id="0f9c7-p151">Por esse motivo, as políticas de DLP verificam documentos em busca de correspondências de política com frequência em segundo plano. Você pode considerar isso uma avaliação assíncrona da política.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-p151">For this reason, DLP policies check documents for policy matches frequently in the background. You can think of this as asynchronous policy evaluation. </span></span><!-- what is the frequency? looks like it is tied to the search crawl schedule -->
  
#### <a name="how-it-works"></a><span data-ttu-id="0f9c7-381">Como funciona</span><span class="sxs-lookup"><span data-stu-id="0f9c7-381">How it works</span></span>
 
<span data-ttu-id="0f9c7-382">À medida em que as pessoas adicionam ou alteram documentos em seus sites, o mecanismo de pesquisa examina o conteúdo, para que você possa pesquisá-lo posteriormente.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-382">As people add or change documents in their sites, the search engine scans the content, so that you can search for it later.</span></span> <span data-ttu-id="0f9c7-383">Enquanto isso, o conteúdo também será verificado quanto às informações confidenciais e para verificar se ele é compartilhado.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-383">While this is happening, the content's also scanned for sensitive information and to check if it's shared.</span></span> <span data-ttu-id="0f9c7-384">Todas as informações confidenciais encontradas serão armazenadas de forma segura no índice de pesquisa, de modo que somente a equipe de conformidade possa acessá-la, mas não usuários comuns.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-384">Any sensitive information that's found is stored securely in the search index, so that only the compliance team can access it, but not typical users.</span></span> <span data-ttu-id="0f9c7-385">Cada política de DLP ativada é executada em segundo plano (de forma assíncrona), verificando a pesquisa frequentemente por qualquer conteúdo que corresponda a uma política e aplicando ações para protegê-lo contra perdas acidentais.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-385">Each DLP policy that you've turned on runs in the background (asynchronously), checking search frequently for any content that matches a policy, and applying actions to protect it from inadvertent leaks.</span></span>
  
![Diagrama mostrando como a política DLP avalia o conteúdo de forma assíncrona](../media/bdf73099-039a-4909-ae89-ac12c41992ba.png)
  
<!-- conflict with a DLP policy is bad wording --><span data-ttu-id="0f9c7-p153"> Por fim, os documentos podem conflitar uma política de DLP, mas eles também podem ficar em conformidade com ela. Por exemplo, se uma pessoa adicionar números de cartão de crédito a um documento, isso poderá fazer com que uma política de DLP bloqueie o acesso ao documento automaticamente. Mas, se a pessoa remover, mais tarde, as informações confidenciais, a ação (neste caso, bloqueio) será desfeita na próxima vez que se avaliar se o documento está de acordo com a política.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-p153"> Finally, documents can conflict with a DLP policy, but they can also become compliant with a DLP policy. For example, if a person adds credit card numbers to a document, it might cause a DLP policy to block access to the document automatically. But if the person later removes the sensitive information, the action (in this case, blocking) is automatically undone the next time the document is evaluated against the policy.</span></span>
  
<span data-ttu-id="0f9c7-390">A DLP avalia qualquer conteúdo que pode ser indexado.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-390">DLP evaluates any content that can be indexed.</span></span> <span data-ttu-id="0f9c7-391">Para saber mais sobre os tipos de arquivo que são rastreados por padrão, confira [Extensões de nomes de arquivos rastreados e tipos de arquivos padrão analisados no SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-391">For more information on what file types are crawled by default, see [Default crawled file name extensions and parsed file types in SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types).</span></span>

> [!NOTE]
> <span data-ttu-id="0f9c7-392">Para evitar que os documentos sejam compartilhados antes que as políticas DLP tivessem a oportunidade de analisá-los, o compartilhamento de novos arquivos no SharePoint pode ser bloqueado até que seu conteúdo seja indexado.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-392">In order to prevent documents from being shared before DLP policies had the opportunity to analyze them, sharing of new files in SharePoint can be blocked until its content has been indexed.</span></span> <span data-ttu-id="0f9c7-393">Confira [Marcar novos arquivos como confidenciais por padrão](/sharepoint/sensitive-by-default) para obter informações detalhadas.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-393">See, [Mark new files as sensitive by default](/sharepoint/sensitive-by-default) for detailed information.</span></span> 
  
### <a name="policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web"></a><span data-ttu-id="0f9c7-394">Avaliação de políticas no Exchange Online, Outlook e Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="0f9c7-394">Policy evaluation in Exchange Online, Outlook, and Outlook on the web</span></span>

<span data-ttu-id="0f9c7-395">Ao criar uma política DLP que inclui o Exchange Online como um local, a política foi sincronizada no Centro de Conformidade &amp; Segurança do Office 365 para o Exchange Online e, em seguida, do Exchange Online para o Outlook na Web e no Outlook.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-395">When you create a DLP policy that includes Exchange Online as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to Exchange Online, and then from Exchange Online to Outlook on the web and Outlook.</span></span>
  
<span data-ttu-id="0f9c7-396">Quando uma mensagem está sendo redigida no Outlook, o usuário pode ver dicas de política à medida que o conteúdo sendo criado é avaliado em relação às políticas DLP.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-396">When a message is being composed in Outlook, the user can see policy tips as the content being created is evaluated against DLP policies.</span></span> <span data-ttu-id="0f9c7-397">Após uma mensagem ser enviada, ela é avaliada em relação às políticas DLP como parte normal do fluxo de emails, juntamente com regras de fluxo de emails do Exchange e as políticas DLP criadas no Centro de Administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-397">And after a message is sent, it's evaluated against DLP policies as a normal part of mail flow, along with Exchange mail flow rules (also known as transport rules) and DLP policies created in the Exchange admin center.</span></span> <span data-ttu-id="0f9c7-398">As políticas DLP examinam tanto a mensagem quanto os anexos.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-398">DLP policies scan both the message and any attachments.</span></span>
  
### <a name="policy-evaluation-in-the-office-desktop-programs"></a><span data-ttu-id="0f9c7-399">Avaliação de política nos programas da área de trabalho do Office</span><span class="sxs-lookup"><span data-stu-id="0f9c7-399">Policy evaluation in the Office desktop programs</span></span>

<!-- same capability to identify sensitive information line conflates sensitive information types and such -->
<span data-ttu-id="0f9c7-400">Excel, PowerPoint e Word incluem os mesmos recursos para identificar informações confidenciais e aplicar políticas de DLP como o SharePoint Online e o OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-400">Excel, PowerPoint, and Word include the same capability to identify sensitive information and apply DLP policies as SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="0f9c7-401">Esses programas do Office sincronizam suas políticas DLP diretamente do repositório central de políticas e, em seguida, avaliam continuamente o conteúdo em relação às políticas DLP quando as pessoas trabalham com documentos abertos de um site incluso em uma política DLP.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-401">These Office programs sync their DLP policies directly from the central policy store, and then continuously evaluate the content against the DLP policies when people work with documents opened from a site that's included in a DLP policy.</span></span>
  
<span data-ttu-id="0f9c7-402">A avaliação das políticas DLP no Office foi desenvolvida para não afetar o desempenho dos programas ou a produtividade de pessoas que trabalham no conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-402">DLP policy evaluation in Office is designed not to affect the performance of the programs or the productivity of people working on content.</span></span> <span data-ttu-id="0f9c7-403">Se estiverem trabalhando em um documento grande ou o computador do usuário estiver ocupado, pode demorar alguns segundos para uma dica de política ser exibida.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-403">If they're working on a large document, or the user's computer is busy, it might take a few seconds for a policy tip to appear.</span></span>

### <a name="policy-evaluation-in-microsoft-teams"></a><span data-ttu-id="0f9c7-404">Avaliação de políticas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0f9c7-404">Policy evaluation in Microsoft Teams</span></span>
 <!--what do you mean that it's synched to user accounts?  I thought DLP policies were applied to locations not users like sensitivity labels are  -->

<span data-ttu-id="0f9c7-405">Ao criar uma política DLP que inclui o Microsoft Teams como um local, a política foi sincronizada no centro de Conformidade &amp; Segurança do Office 365 para contas de usuários e mensagens de chat e de canais do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-405">When you create a DLP policy that includes Microsoft Teams as a location, the policy's synced from the Office 365 Security &amp; Compliance Center to user accounts and Microsoft Teams channels and chat messages.</span></span> <span data-ttu-id="0f9c7-406">Dependendo da configuração das políticas DLP, quando alguém tentar compartilhar informações confidenciais em uma mensagem de chat ou canal do Microsoft Teams, a mensagem pode ser bloqueada ou revogada.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-406">Depending on how DLP policies are configured, when someone attempts to share sensitive information in a Microsoft Teams chat or channel message, the message can be blocked or revoked.</span></span> <span data-ttu-id="0f9c7-407">Os documentos com informações confidenciais e que são compartilhados com convidados (usuários externos) não abrirão para esses usuários.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-407">And, documents that contain sensitive information and that are shared with guests (external users) won't open for those users.</span></span> <span data-ttu-id="0f9c7-408">Para saber mais, confira [Prevenção contra perda de dados no Microsoft Teams](dlp-microsoft-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-408">To learn more, see [Data loss prevention and Microsoft Teams](dlp-microsoft-teams.md).</span></span>
 
## <a name="permissions"></a><span data-ttu-id="0f9c7-409">Permissões</span><span class="sxs-lookup"><span data-stu-id="0f9c7-409">Permissions</span></span>

<span data-ttu-id="0f9c7-410">Por padrão, administradores globais, administradores de segurança e administradores de Conformidade terão acesso para criar e aplicar uma política DLP.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-410">By default, Global admins, Security admins, and Compliance admins will have access to create and apply a DLP policy.</span></span> <span data-ttu-id="0f9c7-411">Outros membros da sua equipe de conformidade que criarão políticas de DLP precisam de permissões para o Centro &amp; de Conformidade de Segurança.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-411">Other Members of your compliance team who will create DLP policies need permissions to the Security &amp; Compliance Center.</span></span> <span data-ttu-id="0f9c7-412">Por padrão, o administrador do Locatário terá acesso a esse local e poderá dar aos responsáveis pela conformidade e outras pessoas acesso ao Centro de Conformidade de Segurança, sem dar a eles todas as permissões de um administrador &amp; de locatários. Para fazer isso, recomendamos que você:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-412">By default, your Tenant admin will have access to this location and can give compliance officers and other people access to the Security &amp; Compliance Center, without giving them all of the permissions of a Tenant admin. To do this, we recommend that you:</span></span>
  
1. <span data-ttu-id="0f9c7-413">Crie um grupo no Microsoft 365 e adicione os responsáveis pela conformidade.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-413">Create a group in Microsoft 365 and add compliance officers to it.</span></span>
    
2. <span data-ttu-id="0f9c7-414">Criar um grupo de funções na página **Permissões** do Centro de Conformidade &amp; Segurança.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-414">Create a role group on the **Permissions** page of the Security &amp; Compliance Center.</span></span> 

3. <span data-ttu-id="0f9c7-415">Ao criar o grupo de função, use a seção **Escolher funções** para adicionar a seguinte função ao Grupo de função: **Gerenciamento de conformidade DLP**.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-415">While creating the role group, use the **Choose Roles** section to add the following role to the Role Group: **DLP Compliance Management**.</span></span>
    
4. <span data-ttu-id="0f9c7-416">Use a seção **Escolher membros** para adicionar o grupo Microsoft 365 que você criou anteriormente ao grupo de função.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-416">Use the **Choose Members** section to add the Microsoft 365 group you created before to the role group.</span></span>

<span data-ttu-id="0f9c7-417">Você também pode criar um grupo de função com privilégios de somente exibição às Políticas DLP e aos Relatórios DLP, concedendo a função **Gerenciamento de conformidade DLP somente exibição**.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-417">You can also create a role group with view-only privileges to the DLP policies and DLP reports by granting the **View-Only DLP Compliance Management** role.</span></span>

<span data-ttu-id="0f9c7-418">Para saber mais, consulte [Conceder aos usuários acesso ao Centro de Conformidade e Segurança do Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-418">For more information, see [Give users access to the Office 365 Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).</span></span>
  
<span data-ttu-id="0f9c7-p161">Essas permissões são necessárias somente para criar e aplicar uma política de DLP. A imposição da política não exige acesso ao conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-p161">These permissions are required only to create and apply a DLP policy. Policy enforcement does not require access to the content.</span></span>
  
## <a name="find-the-dlp-cmdlets"></a><span data-ttu-id="0f9c7-421">Encontre os cmdlets da DLP</span><span class="sxs-lookup"><span data-stu-id="0f9c7-421">Find the DLP cmdlets</span></span>

<span data-ttu-id="0f9c7-422">Para usar a maioria dos cmdlets do Centro de Conformidade &amp; Segurança, você precisa:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-422">To use most of the cmdlets for the Security &amp; Compliance Center, you need to:</span></span>
  
1. <span data-ttu-id="0f9c7-423">[Conectar-se ao Centro de Conformidade &amp; e Segurança do Office 365 usando o PowerShell Remoto](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-423">[Connect to the Office 365 Security &amp; Compliance Center using remote PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>
    
2. <span data-ttu-id="0f9c7-424">Usar qualquer um destes [policy-and-compliance-dlp cmdlets](/powershell/module/exchange/export-dlppolicycollection).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-424">Use any of these [policy-and-compliance-dlp cmdlets](/powershell/module/exchange/export-dlppolicycollection).</span></span>
    
<span data-ttu-id="0f9c7-425">No entanto, os relatórios DLP precisam extrair dados do Microsoft 365, incluindo o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-425">However, DLP reports need pull data from across Microsoft 365, including Exchange Online.</span></span> <span data-ttu-id="0f9c7-426">Por esse motivo, **os cmdlets para os relatórios DLP estão disponíveis no Exchange Online Powershell, e não no Centro de Conformidade &amp; Segurança do Powershell**.</span><span class="sxs-lookup"><span data-stu-id="0f9c7-426">For this reason, **the cmdlets for the DLP reports are available in Exchange Online Powershell -- not in Security &amp; Compliance Center Powershell**.</span></span> <span data-ttu-id="0f9c7-427">Portanto, para usar os cmdlets para os relatórios DLP, você precisa:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-427">Therefore, to use the cmdlets for the DLP reports, you need to:</span></span>
  
1. <span data-ttu-id="0f9c7-428">[Conecte-se ao Exchange Online usando o PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="0f9c7-428">[Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
    
2. <span data-ttu-id="0f9c7-429">Usar qualquer um destes cmdlets para os relatórios DLP:</span><span class="sxs-lookup"><span data-stu-id="0f9c7-429">Use any of these cmdlets for the DLP reports:</span></span>
    
    - [<span data-ttu-id="0f9c7-430">Get-DlpDetectionsReport</span><span class="sxs-lookup"><span data-stu-id="0f9c7-430">Get-DlpDetectionsReport</span></span>](/powershell/module/exchange/Get-DlpDetectionsReport)

    - [<span data-ttu-id="0f9c7-431">Get-DlpDetailReport</span><span class="sxs-lookup"><span data-stu-id="0f9c7-431">Get-DlpDetailReport</span></span>](/powershell/module/exchange/Get-DlpDetailReport)
    
## <a name="more-information"></a><span data-ttu-id="0f9c7-432">Mais informações</span><span class="sxs-lookup"><span data-stu-id="0f9c7-432">More information</span></span>

- [<span data-ttu-id="0f9c7-433">Criar uma política DLP a partir de um modelo</span><span class="sxs-lookup"><span data-stu-id="0f9c7-433">Create a DLP policy from a template</span></span>](create-a-dlp-policy-from-a-template.md)
    
- [<span data-ttu-id="0f9c7-434">Enviar notificações e exibir dicas de políticas para as políticas DLP</span><span class="sxs-lookup"><span data-stu-id="0f9c7-434">Send notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
    
- [<span data-ttu-id="0f9c7-435">Criar uma política DLP para proteger documentos com FCI ou outras propriedades</span><span class="sxs-lookup"><span data-stu-id="0f9c7-435">Create a DLP policy to protect documents with FCI or other properties</span></span>](protect-documents-that-have-fci-or-other-properties.md)
    
- [<span data-ttu-id="0f9c7-436">O que os modelos de política DLP incluem</span><span class="sxs-lookup"><span data-stu-id="0f9c7-436">What the DLP policy templates include</span></span>](what-the-dlp-policy-templates-include.md)
    
- [<span data-ttu-id="0f9c7-437">Definições da entidade do tipo de informações confidenciais</span><span class="sxs-lookup"><span data-stu-id="0f9c7-437">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
    
- [<span data-ttu-id="0f9c7-438">O que as funções DLP procuram</span><span class="sxs-lookup"><span data-stu-id="0f9c7-438">What the DLP functions look for</span></span>](what-the-dlp-functions-look-for.md)
    
- [<span data-ttu-id="0f9c7-439">Criar um tipo de informação confidencial personalizado</span><span class="sxs-lookup"><span data-stu-id="0f9c7-439">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
