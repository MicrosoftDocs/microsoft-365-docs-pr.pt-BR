---
title: Escolha o domínio a ser usado ao criar grupos do Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
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
description: 'Saiba como escolher o domínio a ser usado ao criar grupos do Microsoft 365 Configurando políticas de endereços de email usando o PowerShell. '
ms.openlocfilehash: 1bc8a160ffc368bc4c66a5ac17ffcb203dc678f5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630618"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a><span data-ttu-id="24d54-103">Escolha o domínio a ser usado ao criar grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="24d54-103">Choose the domain to use when creating Microsoft 365 groups</span></span>

 <span data-ttu-id="24d54-104">Algumas organizações usam domínios de email separados para segmentar diferentes partes do negócio.</span><span class="sxs-lookup"><span data-stu-id="24d54-104">Some organizations use separate email domains to segment different parts of their businesses.</span></span> <span data-ttu-id="24d54-105">Você pode especificar qual domínio deve ser usado quando os usuários criarem os grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24d54-105">You can specify which domain should be used when your users create Microsoft 365 groups.</span></span>
  
<span data-ttu-id="24d54-106">Se sua organização precisar que os usuários criem seus grupos em domínios diferentes do domínio aceito padrão de sua empresa, você poderá permitir isso Configurando políticas de endereço de email (EAPs) usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="24d54-106">If your organization needs users to create their groups in domains other than the default accepted domain of your business, you can allow this by configuring email address policies (EAPs) using PowerShell.</span></span>
  
<span data-ttu-id="24d54-107">Antes de poder executar os cmdlets do PowerShell, baixe e instale um módulo que permita que você converse com sua organização.</span><span class="sxs-lookup"><span data-stu-id="24d54-107">Before you can run the PowerShell cmdlets, download and install a module that will let you talk to your organization.</span></span> <span data-ttu-id="24d54-108">Confira [conectar-se ao Exchange Online usando o PowerShell remoto](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span><span class="sxs-lookup"><span data-stu-id="24d54-108">Check out [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).</span></span>
  
## <a name="example-scenarios"></a><span data-ttu-id="24d54-109">Exemplos de cenários</span><span class="sxs-lookup"><span data-stu-id="24d54-109">Example scenarios</span></span>

<span data-ttu-id="24d54-110">Digamos que o domínio principal de sua empresa seja o Contoso.com.</span><span class="sxs-lookup"><span data-stu-id="24d54-110">Let's say your business's main domain is Contoso.com.</span></span> <span data-ttu-id="24d54-111">Mas o domínio aceito por padrão da sua organização é service.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="24d54-111">But your organization's default accepted domain is service.contoso.com.</span></span> <span data-ttu-id="24d54-112">Isso significa que os grupos serão criados no service.contoso.com (por exemplo, jimsteam@service.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="24d54-112">This means groups will be created in service.contoso.com (for example, jimsteam@service.contoso.com).</span></span>
  
<span data-ttu-id="24d54-113">Digamos que você também tenha subdomínios configurados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="24d54-113">Let's say you also have sub-domains configured in your organization.</span></span> <span data-ttu-id="24d54-114">Você também deseja que os grupos sejam criados nesses domínios:</span><span class="sxs-lookup"><span data-stu-id="24d54-114">You want groups to be created in these domains, too:</span></span>
  
- <span data-ttu-id="24d54-115">students.contoso.com para estudantes</span><span class="sxs-lookup"><span data-stu-id="24d54-115">students.contoso.com for students</span></span>
    
- <span data-ttu-id="24d54-116">faculty.contoso.com para membros docentes</span><span class="sxs-lookup"><span data-stu-id="24d54-116">faculty.contoso.com for faculty members</span></span>
    
<span data-ttu-id="24d54-117">Os dois cenários a seguir explicam como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="24d54-117">The following two scenarios explain how you would accomplish this.</span></span>
  
> [!NOTE]
> <span data-ttu-id="24d54-118">Quando você tem vários EAPs, eles são avaliados na ordem de prioridade.</span><span class="sxs-lookup"><span data-stu-id="24d54-118">When you have mulitple EAPs, they are evaluated in the order of priority.</span></span> <span data-ttu-id="24d54-119">O valor 1 significa a prioridade mais alta.</span><span class="sxs-lookup"><span data-stu-id="24d54-119">A value of 1 means the highest priority.</span></span> <span data-ttu-id="24d54-120">Após a correspondência de um EAP, nenhum EAP adicional é avaliado e os endereços que são marcados no grupo são de acordo com o EAP correspondente.</span><span class="sxs-lookup"><span data-stu-id="24d54-120">Once an EAP matches, no further EAP is evaluated and addresses that gets stamped on the group are as per the matched EAP.</span></span> <span data-ttu-id="24d54-121">> se nenhum EAPs corresponder aos critérios especificados, o grupo será provisionado no domínio padrão aceito da organização.</span><span class="sxs-lookup"><span data-stu-id="24d54-121">> If no EAPs match the specified criteria, then the group gets provisioned in the organization's default accepted domain.</span></span> <span data-ttu-id="24d54-122">Confira [gerenciar domínios aceitos no Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) para obter detalhes sobre como adicionar um domínio aceito.</span><span class="sxs-lookup"><span data-stu-id="24d54-122">Check out [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) for details on how to add an accepted domain.</span></span> 
  
### <a name="scenario-1"></a><span data-ttu-id="24d54-123">Cenário 1</span><span class="sxs-lookup"><span data-stu-id="24d54-123">Scenario 1</span></span>

<span data-ttu-id="24d54-124">O exemplo a seguir mostra como provisionar todos os grupos da Microsoft 365 em sua organização no domínio groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="24d54-124">The following example shows you how to provision all Microsoft 365 groups in your organization in the groups.contoso.com domain.</span></span>
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a><span data-ttu-id="24d54-125">Cenário 2</span><span class="sxs-lookup"><span data-stu-id="24d54-125">Scenario 2</span></span>

<span data-ttu-id="24d54-126">Digamos que você deseja controlar quais subdomínios os grupos da Microsoft 365 são criados.</span><span class="sxs-lookup"><span data-stu-id="24d54-126">Let's say you want to control what sub-domains Microsoft 365 groups are created in.</span></span> <span data-ttu-id="24d54-127">Você quer:</span><span class="sxs-lookup"><span data-stu-id="24d54-127">You want:</span></span>
  
- <span data-ttu-id="24d54-128">Grupos criados por alunos (usuários que tenham o **Departamento** configurado para **estudantes**) no domínio students.Groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="24d54-128">Groups created by students (users which have **Department** set to **Students**) in the students.groups.contoso.com domain.</span></span> <span data-ttu-id="24d54-129">Use este comando:</span><span class="sxs-lookup"><span data-stu-id="24d54-129">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- <span data-ttu-id="24d54-130">Grupos criados por membros professores (usuários que têm o **Departamento** definido como **docente ou endereço de email contém Faculty.contoso.com)**) no domínio Faculty.Groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="24d54-130">Groups created by faculty members (users which have **Department** set to **Faculty or email address contains faculty.contoso.com)**) in the faculty.groups.contoso.com domain.</span></span> <span data-ttu-id="24d54-131">Use este comando:</span><span class="sxs-lookup"><span data-stu-id="24d54-131">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- <span data-ttu-id="24d54-132">Todos os outros usuários no domínio groups.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="24d54-132">All other users in the groups.contoso.com domain.</span></span> <span data-ttu-id="24d54-133">Use este comando:</span><span class="sxs-lookup"><span data-stu-id="24d54-133">Use this command:</span></span>
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a><span data-ttu-id="24d54-134">Alterar políticas de endereço de email</span><span class="sxs-lookup"><span data-stu-id="24d54-134">Change email address policies</span></span>

<span data-ttu-id="24d54-135">Para alterar a prioridade ou os modelos de endereço de email para um EAP existente, use o cmdlet Set-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="24d54-135">To change the priority or email address templates for an existing EAP, use the Set-EmailAddressPolicy cmdlet.</span></span>
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

<span data-ttu-id="24d54-136">Alterar um EAP não tem impacto nos grupos que já foram provisionados.</span><span class="sxs-lookup"><span data-stu-id="24d54-136">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="delete-email-address-policies"></a><span data-ttu-id="24d54-137">Excluir políticas de endereço de email</span><span class="sxs-lookup"><span data-stu-id="24d54-137">Delete email address policies</span></span>

<span data-ttu-id="24d54-138">Para excluir um EAP, use o cmdlet Remove-EmailAddressPolicy.</span><span class="sxs-lookup"><span data-stu-id="24d54-138">To delete an EAP, use the Remove-EmailAddressPolicy cmdlet.</span></span>
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

<span data-ttu-id="24d54-139">Alterar um EAP não tem impacto nos grupos que já foram provisionados.</span><span class="sxs-lookup"><span data-stu-id="24d54-139">Changing an EAP has no impact on the groups that have already been provisioned.</span></span>
  
## <a name="hybrid-requirements"></a><span data-ttu-id="24d54-140">Requisitos híbridos</span><span class="sxs-lookup"><span data-stu-id="24d54-140">Hybrid requirements</span></span>

<span data-ttu-id="24d54-141">Se sua organização estiver configurada em um cenário híbrido, confira [configurar os grupos do Microsoft 365 com o Exchange híbrido local](https://go.microsoft.com/fwlink/p/?LinkId=785430) para garantir que sua organização atenda aos requisitos para a criação de grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24d54-141">If your organization is configured in a hybrid scenario, check out [Configure Microsoft 365 groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/p/?LinkId=785430) to make sure your organization meets the requirements for creating Microsoft 365 groups.</span></span> 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a><span data-ttu-id="24d54-142">Informações adicionais sobre como usar grupos de políticas de endereço de email:</span><span class="sxs-lookup"><span data-stu-id="24d54-142">Additional info about using email address policies groups:</span></span>

<span data-ttu-id="24d54-143">Há mais algumas coisas que você precisa saber:</span><span class="sxs-lookup"><span data-stu-id="24d54-143">There are a few more things to know:</span></span>
  
- <span data-ttu-id="24d54-144">O modo como os grupos rápidos são criados depende do número de EAPs configurados em sua organização.</span><span class="sxs-lookup"><span data-stu-id="24d54-144">How fast groups are created depends on the number of EAPs configured in your organization.</span></span>
    
- <span data-ttu-id="24d54-145">Administradores e usuários também podem modificar domínios quando criarem grupos.</span><span class="sxs-lookup"><span data-stu-id="24d54-145">Admins and users can also modify domains when they create groups.</span></span>
    
- <span data-ttu-id="24d54-146">O grupo de usuários é determinado usando as consultas padrão (Propriedades do usuário) que já estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="24d54-146">Group of users is determined using the standard queries (User properties) that are already available.</span></span> <span data-ttu-id="24d54-147">Confira [as propriedades filtráveis para o parâmetro-RecipientFilter](https://go.microsoft.com/fwlink/p/?LinkId=785918) para obter as propriedades filtráveis suportadas.</span><span class="sxs-lookup"><span data-stu-id="24d54-147">Check out [Filterable properties for the -RecipientFilter parameter](https://go.microsoft.com/fwlink/p/?LinkId=785918) for supported filterable properties.</span></span> 
    
- <span data-ttu-id="24d54-148">Se você não configurar nenhum EAPs para grupos, o domínio aceito padrão será selecionado para criação de grupo.</span><span class="sxs-lookup"><span data-stu-id="24d54-148">If you don't configure any EAPs for groups, then the default accepted domain is selected for group creation.</span></span>
    
- <span data-ttu-id="24d54-149">Se você remover um domínio aceito, deverá atualizar o EAPs primeiro, caso contrário, o provisionamento de grupo será afetado.</span><span class="sxs-lookup"><span data-stu-id="24d54-149">If you remove an accepted domain, you should update the EAPs first, otherwise, group provisioning will be impacted.</span></span>
    
- <span data-ttu-id="24d54-150">É possível configurar um limite máximo de 100 políticas de endereço de email para uma organização.</span><span class="sxs-lookup"><span data-stu-id="24d54-150">A maximum limit of 100 email address policies can be configured for an organization.</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="24d54-151">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="24d54-151">Related articles</span></span>

[<span data-ttu-id="24d54-152">Criar um grupo do Microsoft 365 no centro de administração</span><span class="sxs-lookup"><span data-stu-id="24d54-152">Create an Microsoft 365 group in the admin center</span></span>](create-groups.md)
