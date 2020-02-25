---
title: Escolha o domínio para usar ao criar Grupos do Office 365
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: 'Saiba como escolher o domínio a ser usado ao criar grupos do Office 365 Configurando políticas de endereços de email usando o PowerShell. '
ms.openlocfilehash: 55fc99cd201e66166e7da164777cfba2f763609c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237065"
---
# <a name="choose-the-domain-to-use-when-creating-office-365-groups"></a><span data-ttu-id="e9822-103">Escolha o domínio para usar ao criar Grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="e9822-103">Choose the domain to use when creating Office 365 Groups</span></span>

 <span data-ttu-id="e9822-p101">Algumas organizações usam domínios de email separados para segmentar diferentes partes do negócio. Você pode especificar qual domínio deve ser usado quando os usuários criarem grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e9822-p101">Some organizations use separate email domains to segment different parts of their businesses. You can specify which domain should be used when your users create Office 365 groups.</span></span>
  
<span data-ttu-id="e9822-106">Se sua organização precisar que os usuários criem seus grupos em domínios diferentes do domínio aceito padrão de sua empresa, você poderá permitir isso Configurando políticas de endereço de email (EAPs) usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9822-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>
  
<span data-ttu-id="e9822-107">Antes de poder executar os cmdlets do PowerShell, baixe e instale um módulo que permita que você converse com sua organização do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e9822-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your Office 365 organization.</span></span> <span data-ttu-id="e9822-108">Confira [conectar-se ao Exchange Online usando o PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span><span class="sxs-lookup"><span data-stu-id="e9822-108">Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>
  
## <a name="example-scenarios"></a><span data-ttu-id="e9822-109">Exemplos de cenários</span><span class="sxs-lookup"><span data-stu-id="e9822-109">Example scenarios</span></span>

<span data-ttu-id="e9822-110">Digamos que o domínio principal de sua empresa seja o Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e9822-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="e9822-111">Mas o domínio aceito por padrão da sua organização é service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e9822-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="e9822-112">Isso significa que os grupos serão criados no service.contoso.com (por exemplo, jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="e9822-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="e9822-113">Digamos que você também tenha subdomínios configurados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e9822-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="e9822-114">Você também deseja que os grupos sejam criados nesses domínios:</span><span class="sxs-lookup"><span data-stu-id="e9822-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="e9822-115">students.contoso.com para estudantes</span><span class="sxs-lookup"><span data-stu-id="e9822-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="e9822-116">faculty.contoso.com para membros docentes</span><span class="sxs-lookup"><span data-stu-id="e9822-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="e9822-117">Os dois cenários a seguir explicam como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="e9822-117">The following two scenarios explain how you would accomplish this.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e9822-118">Quando você tem vários EAPs, eles são avaliados na ordem de prioridade.</span><span class="sxs-lookup"><span data-stu-id="e9822-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="e9822-119">O valor 1 significa a prioridade mais alta.</span><span class="sxs-lookup"><span data-stu-id="e9822-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="e9822-120">Após a correspondência de um EAP, nenhum EAP adicional é avaliado e os endereços que são marcados no grupo são de acordo com o EAP correspondente.</span><span class="sxs-lookup"><span data-stu-id="e9822-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="e9822-121">> se nenhum EAPs corresponder aos critérios especificados, o grupo será provisionado no domínio padrão aceito da organização.</span><span class="sxs-lookup"><span data-stu-id="e9822-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="e9822-122">Confira [gerenciar domínios aceitos no Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) para obter detalhes sobre como adicionar um domínio aceito.</span><span class="sxs-lookup"><span data-stu-id="e9822-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span> 
  
### <a name="scenario-1"></a><span data-ttu-id="e9822-123">Cenário 1</span><span class="sxs-lookup"><span data-stu-id="e9822-123">Scenario 1</span></span>

<span data-ttu-id="e9822-124">O exemplo a seguir mostra como provisionar todos os grupos do Office 365 em sua organização no domínio groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e9822-124">The following example shows you how to provision all Office 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="e9822-125">Cenário 2</span><span class="sxs-lookup"><span data-stu-id="e9822-125">Scenario 2</span></span>

<span data-ttu-id="e9822-126">Digamos que você deseja controlar quais subdomínios os grupos do Office 365 são criados.</span><span class="sxs-lookup"><span data-stu-id="e9822-126">Let's say you want to control what sub-domains Office 365 groups are created in.</span></span> <span data-ttu-id="e9822-127">Você quer:</span><span class="sxs-lookup"><span data-stu-id="e9822-127">You want:</span></span>
  
- <span data-ttu-id="e9822-128">Grupos criados por alunos (usuários que tenham o **Departamento** configurado para **estudantes**) no domínio students.Groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e9822-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="e9822-129">Use este comando:</span><span class="sxs-lookup"><span data-stu-id="e9822-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="e9822-130">Grupos criados por membros professores (usuários que têm o **Departamento** definido como **docente ou endereço de email contém Faculty.contoso.com)**) no domínio Faculty.Groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e9822-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="e9822-131">Use este comando:</span><span class="sxs-lookup"><span data-stu-id="e9822-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="e9822-132">Todos os outros usuários no domínio groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="e9822-132">All other users in the groups.contoso.com domain.</span></span> <span data-ttu-id="e9822-133">Use este comando:</span><span class="sxs-lookup"><span data-stu-id="e9822-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="e9822-134">Alterar políticas de endereço de email</span><span class="sxs-lookup"><span data-stu-id="e9822-134">Change email address policies</span></span>

<span data-ttu-id="e9822-135">Para alterar a prioridade ou os modelos de endereço de email para um EAP existente, use o cmdlet Set-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="e9822-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="e9822-136">Alterar um EAP não tem impacto nos grupos que já foram provisionados.</span><span class="sxs-lookup"><span data-stu-id="e9822-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="e9822-137">Excluir políticas de endereço de email</span><span class="sxs-lookup"><span data-stu-id="e9822-137">Delete email address policies</span></span>

<span data-ttu-id="e9822-138">Para excluir um EAP, use o cmdlet Remove-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="e9822-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="e9822-139">Alterar um EAP não tem impacto nos grupos que já foram provisionados.</span><span class="sxs-lookup"><span data-stu-id="e9822-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="e9822-140">Requisitos híbridos</span><span class="sxs-lookup"><span data-stu-id="e9822-140">Hybrid requirements</span></span>

<span data-ttu-id="e9822-141">Se sua organização estiver configurada em um cenário híbrido, confira [configurar grupos do Office 365 com o Exchange híbrido local](https://go.microsoft.com/fwlink/p/?LinkId=785430) para garantir que sua organização atenda aos requisitos para a criação de grupos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="e9822-141">If your organization is configured in a hybrid scenario, check out [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/p/?LinkId=785430) to make sure your organization meets the requirements for creating Office 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="e9822-142">Informações adicionais sobre como usar grupos de políticas de endereço de email:</span><span class="sxs-lookup"><span data-stu-id="e9822-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="e9822-143">Há mais algumas coisas que você precisa saber:</span><span class="sxs-lookup"><span data-stu-id="e9822-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="e9822-144">O modo como os grupos rápidos são criados depende do número de EAPs configurados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="e9822-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="e9822-145">Administradores e usuários também podem modificar domínios quando criarem grupos.</span><span class="sxs-lookup"><span data-stu-id="e9822-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="e9822-146">O grupo de usuários é determinado usando as consultas padrão (Propriedades do usuário) que já estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="e9822-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="e9822-147">Confira [as propriedades filtráveis para o parâmetro-RecipientFilter](https://go.microsoft.com/fwlink/p/?LinkId=785918) para pproperties filtráveis com suporte.</span><span class="sxs-lookup"><span data-stu-id="e9822-147">Check out [Filterable properties for the -RecipientFilter parameter](https://go.microsoft.com/fwlink/p/?LinkId=785918) for supported filterable pproperties.</span></span> 
    
- <span data-ttu-id="e9822-148">Se você não configurar nenhum EAPs para grupos, o domínio aceito padrão será selecionado para criação de grupo.</span><span class="sxs-lookup"><span data-stu-id="e9822-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="e9822-149">Se você remover um domínio aceito, deverá atualizar o EAPs primeiro, caso contrário, o provisionamento de grupo será afetado.</span><span class="sxs-lookup"><span data-stu-id="e9822-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="e9822-150">É possível configurar um limite máximo de 100 políticas de endereço de email para uma organização.</span><span class="sxs-lookup"><span data-stu-id="e9822-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="e9822-151">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="e9822-151">Related articles</span></span>

[<span data-ttu-id="e9822-152">Criar um grupo do Office 365 no centro de administração</span><span class="sxs-lookup"><span data-stu-id="e9822-152">Create an Office 365 group in the admin center</span></span>](create-groups.md)
