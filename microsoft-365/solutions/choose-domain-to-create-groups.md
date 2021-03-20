---
title: Escolha o domínio a ser usado ao criar grupos do Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: Aprenda a escolher o domínio a ser usado ao criar grupos do Microsoft 365 configurando políticas de endereço de email usando o PowerShell.
ms.openlocfilehash: 4908d5bd58ca6d0fbb50151983ddb459f0732284
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904679"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="2e6ae-103">Escolha o domínio a ser usado ao criar grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2e6ae-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

<span data-ttu-id="2e6ae-104">Algumas organizações usam domínios de email separados para segmentar diferentes partes do negócio.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="2e6ae-105">Você pode especificar qual domínio deve ser usado quando seus usuários criarem grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="2e6ae-106">Se sua organização precisar que os usuários criem seus grupos em domínios diferentes do domínio aceito padrão da sua empresa, você poderá permitir isso configurando as políticas de endereço de email (EAPs) usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>

<span data-ttu-id="2e6ae-107">Antes de executar os cmdlets do PowerShell, baixe e instale um módulo que permitirá que você fale com sua organização.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="2e6ae-108">Confira [Conectar-se ao Exchange Online usando o PowerShell remoto.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="2e6ae-108">Check out [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="2e6ae-109">Exemplos de cenários</span><span class="sxs-lookup"><span data-stu-id="2e6ae-109">Example scenarios</span></span>

<span data-ttu-id="2e6ae-110">Digamos que o domínio principal da sua empresa seja Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="2e6ae-111">Mas o domínio aceito padrão da sua organização é service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="2e6ae-112">Isso significa que os grupos serão criados service.contoso.com (por exemplo, jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2e6ae-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="2e6ae-113">Digamos que você também tenha sub-domínios configurados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="2e6ae-114">Você também deseja que grupos sejam criados nesses domínios:</span><span class="sxs-lookup"><span data-stu-id="2e6ae-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="2e6ae-115">students.contoso.com para alunos</span><span class="sxs-lookup"><span data-stu-id="2e6ae-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="2e6ae-116">faculty.contoso.com para membros do corpo docente</span><span class="sxs-lookup"><span data-stu-id="2e6ae-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="2e6ae-117">Os dois cenários a seguir explicam como você faria isso.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-117">The following two scenarios explain how you would accomplish this.</span></span>

> [!NOTE]
> <span data-ttu-id="2e6ae-118">Quando você tem EAPs mulitple, eles são avaliados na ordem de prioridade.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="2e6ae-119">Um valor 1 significa a prioridade mais alta.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="2e6ae-120">Depois que um EAP corresponder, nenhum EAP posterior é avaliado e os endereços que são carimbados no grupo são conforme o EAP coincidente.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="2e6ae-121">> Se nenhum EAPs corresponder aos critérios especificados, o grupo será provisionado no domínio aceito padrão da organização.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="2e6ae-122">Confira [Gerenciar domínios aceitos no Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) para obter detalhes sobre como adicionar um domínio aceito.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-122">Check out [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) for details on how to add an accepted domain.</span></span>
  
### <a name="scenario-1"></a><span data-ttu-id="2e6ae-123">Cenário 1</span><span class="sxs-lookup"><span data-stu-id="2e6ae-123">Scenario 1</span></span>

<span data-ttu-id="2e6ae-124">O exemplo a seguir mostra como provisionar todos os grupos do Microsoft 365 em sua organização no groups.contoso.com domínio.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="2e6ae-125">Cenário 2</span><span class="sxs-lookup"><span data-stu-id="2e6ae-125">Scenario 2</span></span>

<span data-ttu-id="2e6ae-126">Digamos que você queira controlar em quais sub-domínios os grupos do Microsoft 365 são criados.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="2e6ae-127">Você quer:</span><span class="sxs-lookup"><span data-stu-id="2e6ae-127">You want:</span></span>
  
- <span data-ttu-id="2e6ae-128">Grupos criados por alunos (usuários que têm **o Departamento** definido como **Alunos**) no students.groups.contoso.com domínio.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="2e6ae-129">Use este comando:</span><span class="sxs-lookup"><span data-stu-id="2e6ae-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="2e6ae-130">Grupos criados por membros do  corpo docente (usuários que têm Departamento definido como Docente ou endereço de email contém **faculty.contoso.com)**) no domínio faculty.groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="2e6ae-131">Use este comando:</span><span class="sxs-lookup"><span data-stu-id="2e6ae-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="2e6ae-132">Os grupos criados por qualquer outra pessoa são criados no groups.contoso.com domínio.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-132">Groups created by anyone else are created in the groups.contoso.com domain.</span></span> <span data-ttu-id="2e6ae-133">Use este comando:</span><span class="sxs-lookup"><span data-stu-id="2e6ae-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="2e6ae-134">Alterar políticas de endereço de email</span><span class="sxs-lookup"><span data-stu-id="2e6ae-134">Change email address policies</span></span>

<span data-ttu-id="2e6ae-135">Para alterar a prioridade ou os modelos de endereço de email de um EAP existente, use o cmdlet Set-EmailAddressPolicy de email.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="2e6ae-136">Alterar um EAP não afeta os grupos que já foram provisionados.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="2e6ae-137">Excluir políticas de endereço de email</span><span class="sxs-lookup"><span data-stu-id="2e6ae-137">Delete email address policies</span></span>

<span data-ttu-id="2e6ae-138">Para excluir um EAP, use o Remove-EmailAddressPolicy cmdlet.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="2e6ae-139">Alterar um EAP não afeta os grupos que já foram provisionados.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="2e6ae-140">Requisitos híbridos</span><span class="sxs-lookup"><span data-stu-id="2e6ae-140">Hybrid requirements</span></span>

<span data-ttu-id="2e6ae-141">Se sua organização estiver configurada em um cenário híbrido, confira Configurar grupos do [Microsoft 365](/exchange/hybrid-deployment/set-up-microsoft-365-groups) com o Exchange híbrido local para garantir que sua organização atenda aos requisitos para criar grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="2e6ae-142">Informações adicionais sobre como usar grupos de políticas de endereço de email:</span><span class="sxs-lookup"><span data-stu-id="2e6ae-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="2e6ae-143">Há mais algumas coisas a saber:</span><span class="sxs-lookup"><span data-stu-id="2e6ae-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="2e6ae-144">A rapidez com que os grupos são criados depende do número de EAPs configurados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="2e6ae-145">Os administradores e usuários também podem modificar domínios quando criam grupos.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="2e6ae-146">O grupo de usuários é determinado usando as consultas padrão (propriedades do usuário) que já estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="2e6ae-147">Confira Propriedades [filtáveis para o parâmetro -RecipientFilter](/powershell/exchange/recipientfilter-properties) para propriedades filtáveis com suporte.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-147">Check out [Filterable properties for the -RecipientFilter parameter](/powershell/exchange/recipientfilter-properties) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="2e6ae-148">Se você não configurar nenhum EAPs para grupos, o domínio aceito padrão será selecionado para criação de grupo.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="2e6ae-149">Se você remover um domínio aceito, atualize os EAPs primeiro, caso contrário, o provisionamento de grupo será afetado.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="2e6ae-150">Um limite máximo de 100 políticas de endereço de email pode ser configurado para uma organização.</span><span class="sxs-lookup"><span data-stu-id="2e6ae-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="2e6ae-151">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="2e6ae-151">Related articles</span></span>

[<span data-ttu-id="2e6ae-152">Planejamento de governança de colaboração passo a passo</span><span class="sxs-lookup"><span data-stu-id="2e6ae-152">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="2e6ae-153">Criar seu plano de governança de colaboração</span><span class="sxs-lookup"><span data-stu-id="2e6ae-153">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="2e6ae-154">Criar um grupo do Microsoft 365 no centro de administração</span><span class="sxs-lookup"><span data-stu-id="2e6ae-154">Create an Microsoft 365 group in the admin center</span></span>](../admin/create-groups/create-groups.md)