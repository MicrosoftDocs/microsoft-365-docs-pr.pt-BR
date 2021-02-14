---
title: Gerenciar usuários e grupos do SharePoint Online com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- SPO_Content
- seo-marvel-apr2020
ms.assetid: d0d3877a-831f-4744-96b0-d8167f06cca2
description: Neste artigo, saiba como usar o PowerShell para Microsoft 365 para gerenciar usuários, grupos e sites do SharePoint Online.
ms.openlocfilehash: 5252ecc950e5f26d6ad60cd871910a67bf50f187
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687375"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a><span data-ttu-id="ce71a-103">Gerenciar usuários e grupos do SharePoint Online com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce71a-103">Manage SharePoint Online users and groups with PowerShell</span></span>

<span data-ttu-id="ce71a-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="ce71a-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ce71a-105">Se você for um administrador do SharePoint Online que trabalha com grandes listas de contas ou grupos de usuários e deseja uma maneira mais fácil de gerenciá-los, você pode usar o PowerShell para o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ce71a-105">If you are a SharePoint Online administrator who works with large lists of user accounts or groups and wants an easier way to manage them, you can use PowerShell for Microsoft 365.</span></span> 

<span data-ttu-id="ce71a-106">Antes de começar, os procedimentos neste tópico exigem que você se conecte ao SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ce71a-106">Before you begin, the procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="ce71a-107">Para obter instruções, [confira Conectar-se ao PowerShell do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="ce71a-107">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="get-a-list-of-sites-groups-and-users"></a><span data-ttu-id="ce71a-108">Obter uma lista de sites, grupos e usuários</span><span class="sxs-lookup"><span data-stu-id="ce71a-108">Get a list of sites, groups, and users</span></span>

<span data-ttu-id="ce71a-p102">Antes de começarmos a gerenciar usuários e grupos, você precisa obter listas de seus sites, grupos e usuários. Você pode usar essas informações para resolver o exemplo neste artigo.</span><span class="sxs-lookup"><span data-stu-id="ce71a-p102">Before we start to manage users and groups, you need to get lists of your sites, groups, and users. You can then use this information to work through the example in this article.</span></span>

<span data-ttu-id="ce71a-111">Obtenha uma lista dos sites em seu locatário com este comando:</span><span class="sxs-lookup"><span data-stu-id="ce71a-111">Get a list of the sites in your tenant with this command:</span></span>

```powershell
Get-SPOSite
```

<span data-ttu-id="ce71a-112">Obtenha uma lista dos grupos em seu locatário com este comando:</span><span class="sxs-lookup"><span data-stu-id="ce71a-112">Get a list of the groups in your tenant with this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

<span data-ttu-id="ce71a-113">Obtenha uma lista dos usuários em seu locatário com este comando:</span><span class="sxs-lookup"><span data-stu-id="ce71a-113">Get a list of the users in your tenant with this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a><span data-ttu-id="ce71a-114">Adicionar um usuário ao grupo de administradores ao site</span><span class="sxs-lookup"><span data-stu-id="ce71a-114">Add a user to the Site Collection Administrators group</span></span>

<span data-ttu-id="ce71a-115">Use o cmdlet para adicionar um usuário à lista de Administradores de Conjunto de Sites `Set-SPOUser` em um conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="ce71a-115">You use the `Set-SPOUser` cmdlet to add a user to the list of Site Collection Administrators on a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

<span data-ttu-id="ce71a-116">Para usar esses comandos, substitua tudo o que está entre aspas, incluindo os caracteres < e >, com os nomes corretos.</span><span class="sxs-lookup"><span data-stu-id="ce71a-116">To use these commands, replace everything within the quotes, including the < and > characters, with the correct names.</span></span>

<span data-ttu-id="ce71a-117">Por exemplo, esse conjunto de comandos adiciona Opal Carlos (nome de usuário opalc) à lista de Administradores de Conjunto de Sites no conjunto de sites ContosoTest no local contoso:</span><span class="sxs-lookup"><span data-stu-id="ce71a-117">For example, this set of commands adds Opal Castillo (user name opalc) to the list of Site Collection Administrators on the ContosoTest site collection in the Contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

<span data-ttu-id="ce71a-118">Você pode copiar e colar esses comandos no Bloco de Notas, alterar os valores variáveis de $tenant, $site e $user para valores reais do seu ambiente e, em seguida, colar isso na janela do Shell de Gerenciamento do SharePoint Online para executar esses comandos.</span><span class="sxs-lookup"><span data-stu-id="ce71a-118">You can copy and paste these commands into Notepad, change the variable values for $tenant, $site, and $user to actual values from your environment, and then paste this into your SharePoint Online Management Shell window to run them.</span></span>

## <a name="add-a-user-to-other-site-collection-groups"></a><span data-ttu-id="ce71a-119">Adicionar um usuário a outros grupos de conjunto de sites</span><span class="sxs-lookup"><span data-stu-id="ce71a-119">Add a user to other site collection groups</span></span>

<span data-ttu-id="ce71a-120">Nesta tarefa, vamos usar o cmdlet para adicionar um usuário a um grupo `Add-SPOUser` do SharePoint em um conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="ce71a-120">In this task, we'll use the `Add-SPOUser` cmdlet to add a user to a SharePoint group on a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

<span data-ttu-id="ce71a-121">Por exemplo, vamos adicionar Paulo Araúfo (nome de usuário) ao grupo Auditores do conjunto de sites ContosoTest no conjunto de sites contoso:</span><span class="sxs-lookup"><span data-stu-id="ce71a-121">For example, let's add Glen Rife (user name glenr) to the Auditors group on the ContosoTest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a><span data-ttu-id="ce71a-122">Criar um grupo de conjunto de sites</span><span class="sxs-lookup"><span data-stu-id="ce71a-122">Create a site collection group</span></span>

<span data-ttu-id="ce71a-123">Use o `New-SPOSiteGroup` cmdlet para criar um novo grupo do SharePoint e adicioná-lo a um conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="ce71a-123">You use the `New-SPOSiteGroup` cmdlet to create a new SharePoint group and add it to a site collection.</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```
<span data-ttu-id="ce71a-124">Propriedades de grupo, como níveis de permissão, podem ser atualizadas posteriormente usando o `Set-SPOSiteGroup` cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ce71a-124">Group properties, such as permission levels, can be updated later by using the `Set-SPOSiteGroup` cmdlet.</span></span>

<span data-ttu-id="ce71a-125">Por exemplo, vamos adicionar o grupo Auditores com permissões Exibir Apenas ao conjunto de sites contosotest no local da contoso:</span><span class="sxs-lookup"><span data-stu-id="ce71a-125">For example, let's add the Auditors group with View Only permissions to the contosotest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a><span data-ttu-id="ce71a-126">Remover usuários de um grupo</span><span class="sxs-lookup"><span data-stu-id="ce71a-126">Remove users from a group</span></span>

<span data-ttu-id="ce71a-p103">Às vezes é preciso remover um usuário de um site ou até mesmo de todos os sites. Talvez o funcionário tenha sido transferido de uma divisão para outra ou tenha saído da empresa. Você pode facilmente fazer isso para um funcionário na interface do usuário. Mas isso não é tão fácil de fazer se você tiver que deslocar uma divisão inteira de um local para outro.</span><span class="sxs-lookup"><span data-stu-id="ce71a-p103">Sometimes you have to remove a user from a site or even all sites. Perhaps the employee moves from one division to another or leaves the company. You can do this for one employee easily in the UI, but this is not easily done when you have to move a complete division from one site to another.</span></span>

<span data-ttu-id="ce71a-130">No entanto, usando o Shell de Gerenciamento do SharePoint Online e os arquivos CSV, isso é rápido e fácil.</span><span class="sxs-lookup"><span data-stu-id="ce71a-130">However by using the SharePoint Online Management Shell and CSV files, this is fast and easy.</span></span> <span data-ttu-id="ce71a-131">Nesta tarefa, você usará o Windows PowerShell para remover um usuário de um grupo de segurança de um conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="ce71a-131">In this task, you'll use Windows PowerShell to remove a user from a site collection security group.</span></span> <span data-ttu-id="ce71a-132">Neste caso, você usará um arquivo CSV e removerá muitos usuários de sites diferentes.</span><span class="sxs-lookup"><span data-stu-id="ce71a-132">Then you'll use a CSV file and remove lots of users from different sites.</span></span> 

<span data-ttu-id="ce71a-133">Vamos usar o cmdlet 'Remove-SPOUser' para remover um único usuário do Microsoft 365 de um grupo de conjunto de sites apenas para que possamos ver a sintaxe do comando.</span><span class="sxs-lookup"><span data-stu-id="ce71a-133">We'll be using the 'Remove-SPOUser' cmdlet to remove a single Microsoft 365 user from a site collection group just so we can see the command syntax.</span></span> <span data-ttu-id="ce71a-134">A sintaxe é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="ce71a-134">Here is how the syntax looks:</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```
<span data-ttu-id="ce71a-135">Por exemplo, vamos remover o Bobby Overby do grupo Auditores do conjunto de sites no conjunto de sites contosotest no local contoso:</span><span class="sxs-lookup"><span data-stu-id="ce71a-135">For example, let's remove Bobby Overby from the site collection Auditors group in the contosotest site collection in the contoso tenancy:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

<span data-ttu-id="ce71a-136">Vamos supor que queremos remover o Bobby de todos os grupos nos quais ele está.</span><span class="sxs-lookup"><span data-stu-id="ce71a-136">Suppose we wanted to remove Bobby from all the groups he is currently in.</span></span> <span data-ttu-id="ce71a-137">Procederemos do seguinte modo:</span><span class="sxs-lookup"><span data-stu-id="ce71a-137">Here is how we would do that:</span></span>

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> <span data-ttu-id="ce71a-138">Isso é apenas um exemplo.</span><span class="sxs-lookup"><span data-stu-id="ce71a-138">This is just an example.</span></span> <span data-ttu-id="ce71a-139">Você não deve executar esse comando, a menos que você realmente deseja remover um usuário de cada grupo, por exemplo, se o usuário deixar a empresa.</span><span class="sxs-lookup"><span data-stu-id="ce71a-139">You should not run this command unless you really have to remove a user from every group, for example if the user leaves the company.</span></span>

## <a name="automate-management-of-large-lists-of-users-and-groups"></a><span data-ttu-id="ce71a-140">Automatizar o gerenciamento de grandes listas de usuários e grupos</span><span class="sxs-lookup"><span data-stu-id="ce71a-140">Automate management of large lists of users and groups</span></span>

<span data-ttu-id="ce71a-141">Para adicionar um grande número de contas aos sites do SharePoint e dar permissões a eles, você pode usar o centro de administração do Microsoft 365, comandos individuais do PowerShell ou o PowerShell em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="ce71a-141">To add a large number of accounts to SharePoint sites and give them permissions, you can use the Microsoft 365 admin center, individual PowerShell commands, or PowerShell an a CSV file.</span></span> <span data-ttu-id="ce71a-142">Dessas escolhas, o arquivo CSV é a maneira mais rápida de automatizar esta tarefa.</span><span class="sxs-lookup"><span data-stu-id="ce71a-142">Of these choices, the CSV file is the fastest way to automate this task.</span></span>

<span data-ttu-id="ce71a-143">O processo básico é a criação de um arquivo CSV com cabeçalhos (colunas) que correspondem aos parâmetros que requerem um script do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ce71a-143">The basic process is to create a CSV file that has headers (columns) that correspond to the parameters that the Windows PowerShell script needs.</span></span> <span data-ttu-id="ce71a-144">Você pode facilmente criar essa lista no Excel e exportá-la como um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="ce71a-144">You can easily create such a list in Excel and then export it as a CSV file.</span></span> <span data-ttu-id="ce71a-145">Em seguida, você pode usar um script do Windows PowerShell para pesquisar nos registros (linhas) no arquivo CSV, adicionar usuários a grupos e os grupos para os sites.</span><span class="sxs-lookup"><span data-stu-id="ce71a-145">Then, you use a Windows PowerShell script to iterate through records (rows) in the CSV file, adding the users to groups and the groups to sites.</span></span> 

<span data-ttu-id="ce71a-146">Por exemplo, vamos criar um arquivo CSV para definir um grupo de conjunto de sites, grupos e permissões.</span><span class="sxs-lookup"><span data-stu-id="ce71a-146">For example, let's create a CSV file to define a group of site collections, groups, and permissions.</span></span> <span data-ttu-id="ce71a-147">Em seguida, vamos criar um arquivo CSV para popular os grupos com os usuários.</span><span class="sxs-lookup"><span data-stu-id="ce71a-147">Next, we will create a CSV file to populate the groups with users.</span></span> <span data-ttu-id="ce71a-148">Finalmente, vamos criar e executar um script simples do Windows PowerShell que cria e preenche os grupos.</span><span class="sxs-lookup"><span data-stu-id="ce71a-148">Finally, we will create and run a simple Windows PowerShell script that creates and populates the groups.</span></span>

<span data-ttu-id="ce71a-149">O primeiro arquivo CSV adicionará um ou mais grupos para um ou mais conjuntos de sites e terá essa estrutura:</span><span class="sxs-lookup"><span data-stu-id="ce71a-149">The first CSV file will add one or more groups to one or more site collections and will have this structure:</span></span>

<span data-ttu-id="ce71a-150">Header:</span><span class="sxs-lookup"><span data-stu-id="ce71a-150">Header:</span></span>

```powershell
Site,Group,PermissionLevels
```

<span data-ttu-id="ce71a-151">Item:</span><span class="sxs-lookup"><span data-stu-id="ce71a-151">Item:</span></span>

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

<span data-ttu-id="ce71a-152">Aqui está o segundo arquivo:</span><span class="sxs-lookup"><span data-stu-id="ce71a-152">Here is an example file:</span></span>

```powershell
Site,Group,PermissionLevels
https://contoso.sharepoint.com/sites/contosotest,Contoso Project Leads,Full Control
https://contoso.sharepoint.com/sites/contosotest,Contoso Auditors,View Only
https://contoso.sharepoint.com/sites/contosotest,Contoso Designers,Design
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://contoso.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://contoso.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://contoso.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```

<span data-ttu-id="ce71a-153">O segundo arquivo CSV adicionará um ou mais usuários a um ou mais grupos e terá essa estrutura:</span><span class="sxs-lookup"><span data-stu-id="ce71a-153">The second CSV file will add one or more users to one or more groups and will have this structure:</span></span>

<span data-ttu-id="ce71a-154">Header:</span><span class="sxs-lookup"><span data-stu-id="ce71a-154">Header:</span></span>

```powershell
Group,LoginName,Site
```

<span data-ttu-id="ce71a-155">Item:</span><span class="sxs-lookup"><span data-stu-id="ce71a-155">Item:</span></span>

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

<span data-ttu-id="ce71a-156">Aqui está o segundo arquivo:</span><span class="sxs-lookup"><span data-stu-id="ce71a-156">Here is an example file:</span></span>

```powershell
Group,LoginName,Site
Contoso Project Leads,bobbyo@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Auditors,allieb@contoso.com,https://contoso.sharepoint.com/sites/contosotest
Contoso Designers,bonniek@contoso.com,https://contoso.sharepoint.com/sites/contosotest
XT1000 Team Leads,dorenap@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
XT1000 Advisors,garthf@contoso.com,https://contoso.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,janets@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Contoso Blog Editors,opalc@contoso.com,https://contoso.sharepoint.com/sites/Blog01
Project Alpha Approvers,robinc@contoso.com,https://contoso.sharepoint.com/sites/Project01
```

<span data-ttu-id="ce71a-157">Para a próxima etapa, você deverá salvar os dois arquivos CSV na sua unidade.</span><span class="sxs-lookup"><span data-stu-id="ce71a-157">For the next step, you must have the two CSV files saved to your drive.</span></span> <span data-ttu-id="ce71a-158">Aqui estão comandos de exemplo que usam arquivos CSV e para adicionar permissões e associação de grupo:</span><span class="sxs-lookup"><span data-stu-id="ce71a-158">Here are example commands that use both CSV files and to add permissions and group membership:</span></span>

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

<span data-ttu-id="ce71a-159">O script importa o conteúdo do arquivo CSV e usa os valores nas colunas para popular os parâmetros dos comandos **New-SPOSiteGroup** e **Add-SPOUser.**</span><span class="sxs-lookup"><span data-stu-id="ce71a-159">The script imports the CSV file contents and uses the values in the columns to populate the parameters of the **New-SPOSiteGroup** and **Add-SPOUser** commands.</span></span> <span data-ttu-id="ce71a-160">No nosso exemplo, estamos salvando isso na pastaO365Admin na unidade C, mas você pode salvá-la onde quiser.</span><span class="sxs-lookup"><span data-stu-id="ce71a-160">In our example, we are saving this to theO365Admin folder on drive C, but you can save it wherever you want.</span></span>

<span data-ttu-id="ce71a-161">Agora, vamos remover várias pessoas de vários grupos em sites diferentes usando o mesmo arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="ce71a-161">Now, let's remove a bunch of people for several groups in different sites using the same CSV file.</span></span> <span data-ttu-id="ce71a-162">Este é um exemplo de comando:</span><span class="sxs-lookup"><span data-stu-id="ce71a-162">Here is an example command:</span></span>

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a><span data-ttu-id="ce71a-163">Gerar relatórios de usuário</span><span class="sxs-lookup"><span data-stu-id="ce71a-163">Generate user reports</span></span>

<span data-ttu-id="ce71a-p114">Você pode querer obter um relatório simples para alguns sites e exibir os usuários destes sites, o seu nível de permissão e outras propriedades. A sintaxe é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="ce71a-p114">You might want to get a simple report for a few sites and display the users for those sites, their permission level, and other properties. This is how the syntax looks:</span></span>

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="ce71a-166">Você poderá usar os dados destes três sites e registrá-los em um arquivo de texto na sua unidade local.</span><span class="sxs-lookup"><span data-stu-id="ce71a-166">This will grab the data for these three sites and write them to a text file on your local drive.</span></span> <span data-ttu-id="ce71a-167">Observe que o parâmetro –Append agregará novo conteúdo a um arquivo já existente.</span><span class="sxs-lookup"><span data-stu-id="ce71a-167">Note that the parameter –Append will add new content to an existing file.</span></span>

<span data-ttu-id="ce71a-168">Por exemplo, vamos executar um relatório nos sites ContosoTest, TeamSite01 e Project01 do locatário Contoso1:</span><span class="sxs-lookup"><span data-stu-id="ce71a-168">For example, let's run a report on the ContosoTest, TeamSite01, and Project01 sites for the Contoso1 tenant:</span></span>

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="ce71a-169">Observe que tivemos que alterar apenas a variável **$site** variável.</span><span class="sxs-lookup"><span data-stu-id="ce71a-169">Note that we had to change only the **$site** variable.</span></span> <span data-ttu-id="ce71a-170">A **$tenant** variável mantém seu valor em todas as três executações do comando.</span><span class="sxs-lookup"><span data-stu-id="ce71a-170">The **$tenant** variable keeps its value through all three runs of the command.</span></span>

<span data-ttu-id="ce71a-p117">Mas e se você quiser fazer isso em todos os sites? Você poderá fazer isso sem ter que digitar todos os sites usando este comando:</span><span class="sxs-lookup"><span data-stu-id="ce71a-p117">However, what if you wanted to do this for every site? You can do this without having to type all those websites by using this command:</span></span>

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

<span data-ttu-id="ce71a-173">Este relatório é muito simples, e você pode adicionar mais códigos para criar relatórios ou relatórios que incluem informações mais detalhadas e mais precisas.</span><span class="sxs-lookup"><span data-stu-id="ce71a-173">This report is fairly simple, and you can add more code to create more specific reports or reports that include more detailed information.</span></span> <span data-ttu-id="ce71a-174">Mas isso deve dar uma ideia de como usar o Shell de Gerenciamento do SharePoint Online para gerenciar usuários no ambiente do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ce71a-174">But this should give you an idea of how to use the SharePoint Online Management Shell to manage users in the SharePoint Online environment.</span></span>
   
## <a name="see-also"></a><span data-ttu-id="ce71a-175">Confira também</span><span class="sxs-lookup"><span data-stu-id="ce71a-175">See also</span></span>

[<span data-ttu-id="ce71a-176">Conectar ao PowerShell do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ce71a-176">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="ce71a-177">Gerenciar o SharePoint Online com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce71a-177">Manage SharePoint Online with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="ce71a-178">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce71a-178">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="ce71a-179">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ce71a-179">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
