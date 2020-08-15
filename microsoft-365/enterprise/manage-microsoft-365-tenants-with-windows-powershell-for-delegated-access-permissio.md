---
title: Gerenciar locatários do Microsoft 365 com o Windows PowerShell para parceiros DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f92d5116-5b66-4150-ad20-1452fc3dd712
description: Neste artigo, saiba como usar o PowerShell para a Microsoft 365 para gerenciar o locações do cliente.
ms.openlocfilehash: 14290f04159e3ba0ce46971d204b71d3bb1600d9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687047"
---
# <a name="manage-microsoft-365-tenants-with-windows-powershell-for-delegated-access-permissions-dap-partners"></a><span data-ttu-id="d64bd-103">Gerenciar locatários do Microsoft 365 com o Windows PowerShell para parceiros com permissões de acesso delegado (DAP)</span><span class="sxs-lookup"><span data-stu-id="d64bd-103">Manage Microsoft 365 tenants with Windows PowerShell for Delegated Access Permissions (DAP) partners</span></span>

<span data-ttu-id="d64bd-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d64bd-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d64bd-105">O Windows PowerShell permite que os parceiros de distribuição e provedor de soluções em nuvem (CSP) administrem e reportem facilmente as configurações de locação do cliente que não estão disponíveis no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d64bd-105">Windows PowerShell allows Syndication and Cloud Solution Provider (CSP) partners to easily administer and report on customer tenancy settings that are not available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="d64bd-106">Observe que as permissões "Administrar em Nome de" (AOBO) são necessárias para a conta de administrador do parceiro para se conectar às locações dos clientes.</span><span class="sxs-lookup"><span data-stu-id="d64bd-106">Note that Administer on Behalf Of (AOBO) permissions are required for the partner administrator account to connect to its customer tenancies.</span></span>
  
<span data-ttu-id="d64bd-107">Os Parceiros com Permissão de Acesso Delegada (DAP) são parceiros da Agregação e dos Provedores de Soluções em Nuvem (CSP).</span><span class="sxs-lookup"><span data-stu-id="d64bd-107">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="d64bd-108">Muitas vezes, eles são provedores de rede ou de telecomunicações para outras empresas.</span><span class="sxs-lookup"><span data-stu-id="d64bd-108">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="d64bd-109">Eles agrupam assinaturas do Microsoft 365 em suas ofertas de serviço para seus clientes.</span><span class="sxs-lookup"><span data-stu-id="d64bd-109">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="d64bd-110">Ao vender uma assinatura do Microsoft 365, elas recebem automaticamente as permissões de administração em nome de (AOBO) para o cliente locações, para que possam administrar e relatar o locações do cliente.</span><span class="sxs-lookup"><span data-stu-id="d64bd-110">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d64bd-111">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="d64bd-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="d64bd-112">Os procedimentos neste tópico exigem que você se conecte para [se conectar ao Microsoft 365 com o PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="d64bd-112">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>
  
<span data-ttu-id="d64bd-113">Você também precisa ter as credenciais de administrador de locatários do parceiro.</span><span class="sxs-lookup"><span data-stu-id="d64bd-113">You also need your partner tenant administrator credentials.</span></span>
  
## <a name="what-do-you-want-to-do"></a><span data-ttu-id="d64bd-114">O que você deseja fazer?</span><span class="sxs-lookup"><span data-stu-id="d64bd-114">What do you want to do?</span></span>

### <a name="list-all-tenant-ids"></a><span data-ttu-id="d64bd-115">Listar todas as IDs de Locatários</span><span class="sxs-lookup"><span data-stu-id="d64bd-115">List all tenant IDs</span></span>

> [!NOTE]
> <span data-ttu-id="d64bd-p103">Caso tenha mais de 500 locatários, analise a sintaxe do cmdlet com o  _-All_ ou o _-MaxResultsParameter_. Isso se aplica aos outros cmdlets que podem proporcionar uma grande saída, como o **Get-MsolUser**.</span><span class="sxs-lookup"><span data-stu-id="d64bd-p103">If you have more than 500 tenants, scope the cmdlet syntax with either  _-All_ or _-MaxResultsParameter_. This applies to other cmdlets that can give a large output, such as **Get-MsolUser**.</span></span>
  
<span data-ttu-id="d64bd-118">Para listar todas as IDs de Locatários do cliente às quais você tem acesso, execute este comando.</span><span class="sxs-lookup"><span data-stu-id="d64bd-118">To list all customer tenant Ids that you have access to, run this command.</span></span>
  
```
Get-MsolPartnerContract -All | Select-Object TenantId
```

<span data-ttu-id="d64bd-119">Uma lista de todos os locatários do cliente será exibida pela **TenantId**.</span><span class="sxs-lookup"><span data-stu-id="d64bd-119">This will display a listing of all your customer tenants by **TenantId**.</span></span>

>[!Note]
><span data-ttu-id="d64bd-120">O PowerShell Core não é compatível com o módulo do Microsoft Azure Active Directory para módulo e cmdlets do Windows PowerShell com **MSol** no nome.</span><span class="sxs-lookup"><span data-stu-id="d64bd-120">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="d64bd-121">Para continuar usando esses cmdlets, você deve executá-los a partir do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d64bd-121">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>
  
### <a name="get-a-tenant-id-by-using-the-domain-name"></a><span data-ttu-id="d64bd-122">Obter uma ID de Locatário usando o nome de domínio</span><span class="sxs-lookup"><span data-stu-id="d64bd-122">Get a tenant ID by using the domain name</span></span>

<span data-ttu-id="d64bd-p105">Para obter a **TenantId** de um locatário específico do cliente por nome de domínio, execute este comando. Substitua _<domainname.onmicrosoft.com>_ pelo nome de domínio real do locatário do cliente desejado.</span><span class="sxs-lookup"><span data-stu-id="d64bd-p105">To get the **TenantId** for a specific customer tenant by domain name, run this command. Replace _<domainname.onmicrosoft.com>_ with the actual domain name of the customer tenant that you want.</span></span>
  
```
Get-MsolPartnerContract -DomainName <domainname.onmicrosoft.com> | Select-Object TenantId
```

### <a name="list-all-domains-for-a-tenant"></a><span data-ttu-id="d64bd-125">Listar todos os domínios de um locatário</span><span class="sxs-lookup"><span data-stu-id="d64bd-125">List all domains for a tenant</span></span>

<span data-ttu-id="d64bd-p106">Para obter todos os domínios de qualquer locatário de um cliente, execute este comando. Substitua o  _<customer TenantId value>_ pelo valor real.</span><span class="sxs-lookup"><span data-stu-id="d64bd-p106">To get all domains for any one customer tenant, run this command. Replace  _<customer TenantId value>_ with the actual value.</span></span>
  
```
Get-MsolDomain -TenantId <customer TenantId value>
```

<span data-ttu-id="d64bd-128">Se você registrou domínios adicionais, serão retornados todos os domínios associados à **TenantId** do cliente.</span><span class="sxs-lookup"><span data-stu-id="d64bd-128">If you have registered additional domains, this will return all domains associated with the customer **TenantId**.</span></span>
  
### <a name="get-a-mapping-of-all-tenants-and-registered-domains"></a><span data-ttu-id="d64bd-129">Obter um mapeamento de todos os locatários e domínios registrados</span><span class="sxs-lookup"><span data-stu-id="d64bd-129">Get a mapping of all tenants and registered domains</span></span>

<span data-ttu-id="d64bd-130">Os comandos anteriores do PowerShell para Microsoft 365 mostraram como recuperar IDs de locatários ou domínios, mas não ambos ao mesmo tempo, sem nenhum mapeamento claro entre eles.</span><span class="sxs-lookup"><span data-stu-id="d64bd-130">The previous PowerShell for Microsoft 365 commands showed you how to retrieve either tenant IDs or domains but not both at the same time, and with no clear mapping between them all.</span></span> <span data-ttu-id="d64bd-131">Esse comando gera uma lista de todas as IDs de Locatários do cliente e os respectivos domínios.</span><span class="sxs-lookup"><span data-stu-id="d64bd-131">This command generates a listing of all your customer tenant IDs and their domains.</span></span>
  
```
$Tenants = Get-MsolPartnerContract -All; $Tenants | foreach {$Domains = $_.TenantId; Get-MsolDomain -TenantId $Domains | fl @{Label="TenantId";Expression={$Domains}},name}
```

### <a name="get-all-users-for-a-tenant"></a><span data-ttu-id="d64bd-132">Obter todos os usuários de um locatário</span><span class="sxs-lookup"><span data-stu-id="d64bd-132">Get all users for a tenant</span></span>

<span data-ttu-id="d64bd-p108">Os comandos **UserPrincipalName**, o **DisplayName** e o status **isLicensed** serão exibidos para todos os usuários de um determinado locatário. Substitua o _<customer TenantId value>_ pelo valor real.</span><span class="sxs-lookup"><span data-stu-id="d64bd-p108">This will display the **UserPrincipalName**, the **DisplayName**, and the **isLicensed** status for all users for a particular tenant. Replace _<customer TenantId value>_ with the actual value.</span></span>
  
```
Get-MsolUser -TenantID <customer TenantId value>
```

### <a name="get-all-details-about-a-user"></a><span data-ttu-id="d64bd-135">Obter todos os detalhes sobre um usuário</span><span class="sxs-lookup"><span data-stu-id="d64bd-135">Get all details about a user</span></span>

<span data-ttu-id="d64bd-p109">Caso pretenda conferir todas as propriedades de um usuário específico, execute este comando. Substitua _<customer TenantId value>_ e _<user principal name value>_ pelos valores reais.</span><span class="sxs-lookup"><span data-stu-id="d64bd-p109">If you want to see all the properties of a particular user, run this command. Replace  _<customer TenantId value>_ and _<user principal name value>_ with the actual values.</span></span>
  
```
Get-MsolUser -TenantId <customer TenantId value> -UserPrincipalName <user principal name value>
```

### <a name="add-users-set-options-and-assign-licenses"></a><span data-ttu-id="d64bd-138">Adicionar usuários, definir opções e atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="d64bd-138">Add users, set options, and assign licenses</span></span>

<span data-ttu-id="d64bd-139">A criação, configuração e licenciamento em massa de usuários do Microsoft 365 é particularmente eficiente usando o PowerShell para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d64bd-139">The bulk creation, configuration, and licensing of Microsoft 365 users is particularly efficient by using PowerShell for Microsoft 365.</span></span> <span data-ttu-id="d64bd-140">Neste processo de duas etapas, você primeiro cria entradas para todos os usuários que deseja adicionar em um arquivo de valores separados por vírgula (CSV) e, em seguida, importa esse arquivo usando o PowerShell para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d64bd-140">In this two-step process, you first create entries for all the users you want to add in a comma-separated value (CSV) file and then import that file by using PowerShell for Microsoft 365.</span></span> 
  
#### <a name="create-a-csv-file"></a><span data-ttu-id="d64bd-141">Criar um arquivo CSV</span><span class="sxs-lookup"><span data-stu-id="d64bd-141">Create a CSV file</span></span>

<span data-ttu-id="d64bd-142">Crie um arquivo CSV usando este formato:</span><span class="sxs-lookup"><span data-stu-id="d64bd-142">Create a CSV file by using this format:</span></span>
  
-  `UserPrincipalName,FirstName,LastName,DisplayName,Password,TenantId,UsageLocation,LicenseAssignment`
    
<span data-ttu-id="d64bd-143">em que:</span><span class="sxs-lookup"><span data-stu-id="d64bd-143">where:</span></span>
  
- <span data-ttu-id="d64bd-p111">**UsageLocation**: O valor para isso é o código de país/região ISO de duas letras do usuário. Os códigos de país/região podem ser visualizados na[Plataforma de Navegação Online ISO](https://go.microsoft.com/fwlink/p/?LinkId=532703). Por exemplo, o código para os Estados Unidos é US e o código para o Brasil é BR.</span><span class="sxs-lookup"><span data-stu-id="d64bd-p111">**UsageLocation**: The value for this is the two-letter ISO country/region code of the user. The country/region codes can be looked up at the[ISO Online Browsing Platform](https://go.microsoft.com/fwlink/p/?LinkId=532703). For example, the code for the United States is US, and the code for Brazil is BR.</span></span> 
    
- <span data-ttu-id="d64bd-p112">**LicenseAssignment**: O valor para isso tem o seguinte formato: `syndication-account:<PROVISIONING_ID>`. Por exemplo, se você está atribuindo licenças para usuários do O365_Business_Premium, o valor de **LicenseAssignment** tem a seguinte aparência: **syndication-account:O365_Business_Premium**. Você vai encontrar as PROVISIONING_IDs no portal do parceiro de distribuição ao qual tem acesso como um parceiro de agregação ou um CSP.</span><span class="sxs-lookup"><span data-stu-id="d64bd-p112">**LicenseAssignment**: The value for this uses this format: `syndication-account:<PROVISIONING_ID>`. For example, if you are assigning customer tenant users O365_Business_Premium licenses, the **LicenseAssignment** value looks like this: **syndication-account:O365_Business_Premium**. You will find the PROVISIONING_IDs in the Syndication Partner Portal that you have access to as a Syndication or CSP partner.</span></span>
    
#### <a name="import-the-csv-file-and-create-the-users"></a><span data-ttu-id="d64bd-150">Importar o arquivo CSV e criar os usuários</span><span class="sxs-lookup"><span data-stu-id="d64bd-150">Import the CSV file and create the users</span></span>

<span data-ttu-id="d64bd-p113">Depois de criar o arquivo CSV, execute este comando para criar contas de usuários com senhas que não perdem a validade. Essas senhas atribuem a licença especificada e os usuários devem alterá-la no primeiro logon. Não deixe de substituir o nome correto do arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="d64bd-p113">After you have your CSV file created, run this command to create user accounts with non-expiring passwords that the user must change at first sign-in and that assigns the license you specify. Be sure to substitute the correct CSV file name.</span></span>
  
```
Import-Csv .\FILENAME.CSV | foreach {New-MsolUser -UserPrincipalName $_.UserPrincipalName -DisplayName $_.DisplayName -FirstName $_.FirstName -LastName $_.LastName -Password $_.Password -UsageLocation $_.UsageLocation -LicenseAssignment $_.LicenseAssignment -ForceChangePassword:$true -PasswordNeverExpires:$true -TenantId $_.TenantId}
```

## <a name="see-also"></a><span data-ttu-id="d64bd-153">Confira também</span><span class="sxs-lookup"><span data-stu-id="d64bd-153">See also</span></span>

#### 

[<span data-ttu-id="d64bd-154">Ajuda para parceiros</span><span class="sxs-lookup"><span data-stu-id="d64bd-154">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=533477)

