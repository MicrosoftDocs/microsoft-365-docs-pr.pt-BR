---
title: Criar sites do SharePoint Online e adicionar usuários com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
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
description: 'Resumo: use o PowerShell para criar novos sites do SharePoint Online e adicionar usuários e grupos a esses sites.'
ms.openlocfilehash: eb6c2817c8760ca222da8a7c2b14cbfcda4eb4b8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907613"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a><span data-ttu-id="8454f-103">Criar sites do SharePoint Online e adicionar usuários com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="8454f-103">Create SharePoint Online sites and add users with PowerShell</span></span>

<span data-ttu-id="8454f-104">*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="8454f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8454f-105">Quando você usa o PowerShell para o Microsoft 365 para criar sites do SharePoint Online e adicionar usuários, você pode executar tarefas de forma rápida e repetida muito mais rápida do que pode no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8454f-105">When you use PowerShell for Microsoft 365 to create SharePoint Online sites and add users, you can quickly and repeatedly perform tasks much faster than you can in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8454f-106">Você também pode executar tarefas que não são possíveis de executar no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8454f-106">You can also perform tasks that are not possible to perform in the Microsoft 365 admin center.</span></span> 

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="8454f-107">Conectar ao SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8454f-107">Connect to SharePoint Online</span></span>

<span data-ttu-id="8454f-108">Os procedimentos neste tópico exigem que você se conecte ao SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8454f-108">The procedures in this topic require you to connect to SharePoint Online.</span></span> <span data-ttu-id="8454f-109">Para obter instruções, [consulte Conectar-se ao PowerShell do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="8454f-109">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span></span>

## <a name="step-1-create-new-site-collections-using-powershell"></a><span data-ttu-id="8454f-110">Etapa 1: Criar novos conjunto de sites usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="8454f-110">Step 1: Create new site collections using PowerShell</span></span>

<span data-ttu-id="8454f-111">Crie vários sites usando o PowerShell e um arquivo .csv que você criar usando o código de exemplo fornecido e o Bloco de Notas.</span><span class="sxs-lookup"><span data-stu-id="8454f-111">Create multiple sites using PowerShell and a .csv file that you create using the example code provided and Notepad.</span></span> <span data-ttu-id="8454f-112">Para este procedimento, você substituirá as informações de espaço reservado mostradas em colchetes por suas próprias informações específicas do site e do locatário.</span><span class="sxs-lookup"><span data-stu-id="8454f-112">For this procedure, you’ll be replacing the placeholder information shown in brackets with your own site- and tenant-specific information.</span></span> <span data-ttu-id="8454f-113">Esse processo permite que você crie um único arquivo e execute um único comando do PowerShell que usa esse arquivo.</span><span class="sxs-lookup"><span data-stu-id="8454f-113">This process lets you create a single file and run a single PowerShell command that uses that file.</span></span> <span data-ttu-id="8454f-114">Isso torna as ações realizadas repetitivas e portáteis e elimina muitos, se não todos, erros que podem vir da digitação de comandos longos no Shell de Gerenciamento do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8454f-114">This makes the actions taken both repeatable and portable and eliminates many, if not all, errors that can come from typing long commands into the SharePoint Online Management Shell.</span></span> <span data-ttu-id="8454f-115">Há duas partes para este procedimento.</span><span class="sxs-lookup"><span data-stu-id="8454f-115">There are two parts to this procedure.</span></span> <span data-ttu-id="8454f-116">Primeiro, você criará um arquivo .csv e, em seguida, fará referência a esse arquivo .csv usando o PowerShell, que usará seu conteúdo para criar os sites.</span><span class="sxs-lookup"><span data-stu-id="8454f-116">First you’ll create a .csv file, and then you’ll reference that .csv file using PowerShell, which will use its contents to create the sites.</span></span>

<span data-ttu-id="8454f-117">O cmdlet do PowerShell importa o arquivo .csv e o canalização para um loop dentro dos colchetes curvados que lê a primeira linha do arquivo como headers de coluna.</span><span class="sxs-lookup"><span data-stu-id="8454f-117">The PowerShell cmdlet imports the .csv file and pipes it to a loop inside the curly brackets that reads the first line of the file as column headers.</span></span> <span data-ttu-id="8454f-118">O cmdlet do PowerShell, em seguida, itera pelos registros restantes, cria um novo conjunto de sites para cada registro e atribui propriedades do conjunto de sites de acordo com os headers da coluna.</span><span class="sxs-lookup"><span data-stu-id="8454f-118">The PowerShell cmdlet then iterates through the remaining records, creates a new site collection for each record, and assigns properties of the site collection according to the column headers.</span></span>

### <a name="create-a-csv-file"></a><span data-ttu-id="8454f-119">Criando um arquivo .csv</span><span class="sxs-lookup"><span data-stu-id="8454f-119">Create a .csv file</span></span>

> [!NOTE]
> <span data-ttu-id="8454f-120">O parâmetro de cota de recursos só funciona em sites clássicos.</span><span class="sxs-lookup"><span data-stu-id="8454f-120">The resource quota parameter works only on classic sites.</span></span> <span data-ttu-id="8454f-121">Se você usar esse parâmetro em um site moderno, poderá receber uma mensagem de aviso de que ele foi preterido.</span><span class="sxs-lookup"><span data-stu-id="8454f-121">If you use this parameter on a modern site, you may receive a warning message that it has been deprecated.</span></span> 

1. <span data-ttu-id="8454f-122">Abra o bloco de notas e cole o seguinte bloco de texto:</span><span class="sxs-lookup"><span data-stu-id="8454f-122">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/><span data-ttu-id="8454f-123">Onde *locatário* é o nome  do seu locatário e proprietário é o nome de usuário do usuário em seu locatário ao qual você deseja conceder a função de administrador principal do conjunto de sites.</span><span class="sxs-lookup"><span data-stu-id="8454f-123">Where *tenant* is the name of your tenant, and *owner* is the user name of the user on your tenant to whom you want to grant the role of primary site collection administrator.</span></span><br/><span data-ttu-id="8454f-124">(Você pode pressionar Ctrl+H ao usar o Bloco de Notas para substituir em massa mais rapidamente.)</span><span class="sxs-lookup"><span data-stu-id="8454f-124">(You can press Ctrl+H when you use Notepad to bulk replace faster.)</span></span><br/>

2. <span data-ttu-id="8454f-125">Salve o arquivo em sua área de trabalho como **SiteCollections.csv**.</span><span class="sxs-lookup"><span data-stu-id="8454f-125">Save the file on your desktop as **SiteCollections.csv**.</span></span><br/>

> [!TIP]
> <span data-ttu-id="8454f-126">Antes de usar esse ou qualquer outro arquivo de script .csv ou Windows PowerShell, é uma boa prática garantir que não haja caracteres extraneos ou não impressos.</span><span class="sxs-lookup"><span data-stu-id="8454f-126">Before you use this or any other .csv or Windows PowerShell script file, it's a good practice to make sure that there are no extraneous or nonprinting characters.</span></span> <span data-ttu-id="8454f-127">Abra o arquivo no Word, e na faixa de opções, clique no ícone do parágrafo  para mostrar caracteres não imprimíveis.</span><span class="sxs-lookup"><span data-stu-id="8454f-127">Open the file in Word, and in the ribbon, click the paragraph icon to show nonprinting characters.</span></span> <span data-ttu-id="8454f-128">Não deve haver caracteres estranhos não imprimíveis.</span><span class="sxs-lookup"><span data-stu-id="8454f-128">There should be no extraneous nonprinting characters.</span></span> <span data-ttu-id="8454f-129">Por exemplo, não deve haver marcas do parágrafo no final do arquivo.</span><span class="sxs-lookup"><span data-stu-id="8454f-129">For example, there should be no paragraph marks beyond the final one at the end of the file.</span></span>

### <a name="run-the-windows-powershell-command"></a><span data-ttu-id="8454f-130">Execute o comando do Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8454f-130">Run the Windows PowerShell command</span></span>

1. <span data-ttu-id="8454f-131">No prompt Windows PowerShell, digite ou copie e colar o seguinte comando e pressione Enter:</span><span class="sxs-lookup"><span data-stu-id="8454f-131">At the Windows PowerShell prompt, type or copy and paste the following command, and press Enter:</span></span><br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/><span data-ttu-id="8454f-132">Onde *MyAlias* é igual ao alias do usuário.</span><span class="sxs-lookup"><span data-stu-id="8454f-132">Where *MyAlias* equals your user alias.</span></span><br/>

2. <span data-ttu-id="8454f-133">Aguarde o prompt Windows PowerShell reaparecer.</span><span class="sxs-lookup"><span data-stu-id="8454f-133">Wait for the Windows PowerShell prompt to reappear.</span></span> <span data-ttu-id="8454f-134">Pode demorar um minuto ou dois.</span><span class="sxs-lookup"><span data-stu-id="8454f-134">It might take a minute or two.</span></span><br/>

3. <span data-ttu-id="8454f-135">No prompt Windows PowerShell, digite ou copie e copie o seguinte cmdlet e pressione Enter:</span><span class="sxs-lookup"><span data-stu-id="8454f-135">At the Windows PowerShell prompt, type or copy and paste the following cmdlet, and press Enter:</span></span><br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. <span data-ttu-id="8454f-136">Observe os novos conjuntos de sites na lista.</span><span class="sxs-lookup"><span data-stu-id="8454f-136">Note the new site collections in the list.</span></span> <span data-ttu-id="8454f-137">Usando nosso arquivo CSV de exemplo, você verá os seguintes conjunto de sites: **TeamSite01**, **Blog01**, **Project01** e **Community01**</span><span class="sxs-lookup"><span data-stu-id="8454f-137">Using our example CSV file, you would see the following site collections: **TeamSite01**, **Blog01**, **Project01**, and **Community01**</span></span>

<span data-ttu-id="8454f-138">É isso.</span><span class="sxs-lookup"><span data-stu-id="8454f-138">That’s it.</span></span> <span data-ttu-id="8454f-139">Você criou vários conjunto de sites usando o arquivo .csv criado e um único comando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8454f-139">You’ve created multiple site collections using the .csv file you created and a single Windows PowerShell command.</span></span> <span data-ttu-id="8454f-140">Agora você está pronto para criar e alocar usuários nestes sites.</span><span class="sxs-lookup"><span data-stu-id="8454f-140">You’re now ready to create and assign users to these sites.</span></span>

## <a name="step-2-add-users-and-groups"></a><span data-ttu-id="8454f-141">Etapa 2: Adicionar usuários ou grupos</span><span class="sxs-lookup"><span data-stu-id="8454f-141">Step 2: Add users and groups</span></span>

<span data-ttu-id="8454f-p110">Agora você criará usuários e irá adicioná-los ao grupo do site. Então você usará um arquivo csv. para fazer o carregamento em massa de novos grupos e usuários.</span><span class="sxs-lookup"><span data-stu-id="8454f-p110">Now you’re going to create users and add them to a site collection group. You will then use a .csv file to bulk upload new groups and users.</span></span>

<span data-ttu-id="8454f-144">Os procedimentos a seguir continuam usando os sites de exemplo TeamSite01, Blog01, Project01 e Community01.</span><span class="sxs-lookup"><span data-stu-id="8454f-144">The following procedures continue using the example sites TeamSite01, Blog01, Project01, and Community01.</span></span>

### <a name="create-csv-and-ps1-files"></a><span data-ttu-id="8454f-145">Criando arquivos .csv e .ps1</span><span class="sxs-lookup"><span data-stu-id="8454f-145">Create .csv and .ps1 files</span></span>

1. <span data-ttu-id="8454f-146">Abra o bloco de notas e cole o seguinte bloco de texto:</span><span class="sxs-lookup"><span data-stu-id="8454f-146">Open Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Site,Group,PermissionLevels
https://tenant.sharepoint.com/sites/Community01,Contoso Project Leads,Full Control
https://tenant.sharepoint.com/sites/Community01,Contoso Auditors,View Only
https://tenant.sharepoint.com/sites/Community01,Contoso Designers,Design
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Team Leads,Full Control
https://tenant.sharepoint.com/sites/TeamSite01,XT1000 Advisors,Edit
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Designers,Design
https://tenant.sharepoint.com/sites/Blog01,Contoso Blog Editors,Edit
https://tenant.sharepoint.com/sites/Project01,Project Alpha Approvers,Full Control
```
<br/><span data-ttu-id="8454f-147">Onde *locatário* é igual ao nome do locatário.</span><span class="sxs-lookup"><span data-stu-id="8454f-147">Where *tenant* equals your tenant name.</span></span><br/>

2. <span data-ttu-id="8454f-148">Salve o arquivo na área de trabalho como **GroupsAndPermissions.csv**.</span><span class="sxs-lookup"><span data-stu-id="8454f-148">Save the file to your desktop as **GroupsAndPermissions.csv**.</span></span><br/>

3. <span data-ttu-id="8454f-149">Abra uma nova instância do bloco de notas e cole o seguinte bloco de texto:</span><span class="sxs-lookup"><span data-stu-id="8454f-149">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Group,LoginName,Site
Contoso Project Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Auditors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
Contoso Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Community01
XT1000 Team Leads,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
XT1000 Advisors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/TeamSite01
Contoso Blog Designers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Contoso Blog Editors,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Blog01
Project Alpha Approvers,username@tenant.onmicrosoft.com,https://tenant.sharepoint.com/sites/Project01
```
<br/><span data-ttu-id="8454f-150">Onde *o locatário* é igual ao nome do locatário e *o* nome de usuário é igual ao nome de usuário de um usuário existente.</span><span class="sxs-lookup"><span data-stu-id="8454f-150">Where *tenant* equals your tenant name, and *username* equals the user name of an existing user.</span></span><br/>

4. <span data-ttu-id="8454f-151">Salve o arquivo na área de trabalho como **Users.csv**.</span><span class="sxs-lookup"><span data-stu-id="8454f-151">Save the file to your desktop as **Users.csv**.</span></span><br/>

5. <span data-ttu-id="8454f-152">Abra uma nova instância do bloco de notas e cole o seguinte bloco de texto:</span><span class="sxs-lookup"><span data-stu-id="8454f-152">Open a new instance of Notepad, and paste the following text block into it:</span></span><br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/><span data-ttu-id="8454f-153">Onde MyAlias é igual ao nome de usuário do usuário que está conectado no momento.</span><span class="sxs-lookup"><span data-stu-id="8454f-153">Where MyAlias equals the user name of the user that is currently logged on.</span></span><br/>

6. <span data-ttu-id="8454f-154">Salve o arquivo na área de trabalho como **UsersAndGroups.ps1**.</span><span class="sxs-lookup"><span data-stu-id="8454f-154">Save the file to your desktop as **UsersAndGroups.ps1**.</span></span> <span data-ttu-id="8454f-155">Este é um script Windows PowerShell simples.</span><span class="sxs-lookup"><span data-stu-id="8454f-155">This is a simple Windows PowerShell script.</span></span>

<span data-ttu-id="8454f-156">Agora você está pronto para executar o script UsersAndGroup.ps1 para adicionar usuários e grupos a vários conjuntos de sites.</span><span class="sxs-lookup"><span data-stu-id="8454f-156">You’re now ready to run the UsersAndGroup.ps1 script to add users and groups to multiple site collections.</span></span>

### <a name="run-usersandgroupsps1-script"></a><span data-ttu-id="8454f-157">Execute o script UsersAndGroups.ps1</span><span class="sxs-lookup"><span data-stu-id="8454f-157">Run UsersAndGroups.ps1 script</span></span>

1. <span data-ttu-id="8454f-158">Retorne ao shell de gerenciamento do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8454f-158">Return to the SharePoint Online Management Shell.</span></span><br/>
2. <span data-ttu-id="8454f-159">No prompt Windows PowerShell, digite ou copie e colar a seguinte linha e pressione Enter:</span><span class="sxs-lookup"><span data-stu-id="8454f-159">At the Windows PowerShell prompt, type or copy and paste the following line, and press Enter:</span></span><br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. <span data-ttu-id="8454f-160">No prompt de confirmação, pressione **Y**.</span><span class="sxs-lookup"><span data-stu-id="8454f-160">At the confirmation prompt, press **Y**.</span></span><br/>

4. <span data-ttu-id="8454f-161">No prompt Windows PowerShell, digite ou copie e copie o seguinte e pressione Enter:</span><span class="sxs-lookup"><span data-stu-id="8454f-161">At the Windows PowerShell prompt, type or copy and paste the following, and press Enter:</span></span><br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/><span data-ttu-id="8454f-162">Onde *MyAlias* é igual ao seu nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="8454f-162">Where *MyAlias* equals your user name.</span></span><br/>

5. <span data-ttu-id="8454f-p112">Aguarde a solicitação de retorno do prompt antes de prosseguir. Os grupos aparecerão de acordo com a criação dos mesmos. Então você verá a repetição da lista do grupo de acordo com os usuários que são agregados.</span><span class="sxs-lookup"><span data-stu-id="8454f-p112">Wait for the prompt to return before moving on. You will first see the groups appear as they are created. Then you will see the group list repeated as users are added.</span></span>

## <a name="see-also"></a><span data-ttu-id="8454f-166">Confira também</span><span class="sxs-lookup"><span data-stu-id="8454f-166">See also</span></span>

[<span data-ttu-id="8454f-167">Conectar ao PowerShell do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8454f-167">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="8454f-168">Gerenciar grupos de sites do SharePoint Online com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="8454f-168">Manage SharePoint Online site groups with PowerShell</span></span>](manage-sharepoint-site-groups-with-powershell.md)

[<span data-ttu-id="8454f-169">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="8454f-169">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8454f-170">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8454f-170">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)