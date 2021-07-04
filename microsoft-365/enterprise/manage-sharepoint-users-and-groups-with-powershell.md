---
title: Gerenciar SharePoint e grupos online com o PowerShell
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
description: Neste artigo, saiba como usar o PowerShell para Microsoft 365 gerenciar SharePoint online, grupos e sites.
ms.openlocfilehash: 823c5fdc9af178a2e8ea8f0ca4c63fbfa4673dd8
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289050"
---
# <a name="manage-sharepoint-online-users-and-groups-with-powershell"></a>Gerenciar SharePoint e grupos online com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Se você é um administrador SharePoint Online que trabalha com listas grandes de contas de usuário ou grupos e deseja uma maneira mais fácil de gerenciá-las, você pode usar o PowerShell para Microsoft 365.

Antes de começar, os procedimentos neste tópico exigem que você se conecte ao SharePoint Online. Para obter instruções, [consulte Conexão para SharePoint PowerShell Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

## <a name="get-a-list-of-sites-groups-and-users"></a>Obter uma lista de sites, grupos e usuários

Antes de começarmos a gerenciar usuários e grupos, você precisa obter listas de seus sites, grupos e usuários. Você pode usar essas informações para resolver o exemplo neste artigo.

Obtenha uma lista dos sites em seu locatário com este comando:

```powershell
Get-SPOSite
```

Obtenha uma lista dos grupos em seu locatário com este comando:

```powershell
Get-SPOSite | ForEach {Get-SPOSiteGroup -Site $_.Url} | Format-Table
```

Obtenha uma lista dos usuários em seu locatário com este comando:

```powershell
Get-SPOSite | ForEach {Get-SPOUser -Site $_.Url}
```

## <a name="add-a-user-to-the-site-collection-administrators-group"></a>Adicionar um usuário ao grupo de administradores ao site

Use o `Set-SPOUser` cmdlet para adicionar um usuário à lista de Administradores do Conjunto de Sites em um conjunto de sites.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
 ```

Para usar esses comandos, substitua tudo entre aspas, incluindo os caracteres < e >, com os nomes corretos.

Por exemplo, esse conjunto de comandos adiciona Opal Castillo (opalc nome de usuário) à lista de Administradores do Conjunto de Sites no conjunto de sites ContosoTest no local da Contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "opalc"
Set-SPOUser -Site https://$tenant.sharepoint.com/sites/$site -LoginName $user@$tenant.com -IsSiteCollectionAdmin $true
```

Você pode copiar e colar esses comandos em Bloco de notas, alterar os valores variáveis do $tenant, $site e $user para valores reais do seu ambiente e, em seguida, colar isso na janela do Shell de Gerenciamento do SharePoint Online para executar eles.

## <a name="add-a-user-to-other-site-collection-groups"></a>Adicionar um usuário a outros grupos de conjunto de sites

Nesta tarefa, vamos usar o cmdlet para adicionar um usuário a um grupo SharePoint `Add-SPOUser` em um conjunto de sites.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site

```

Por exemplo, vamos adicionar Glen Rife (nome de usuário glenr) ao grupo Auditores no conjunto de sites ContosoTest no local da contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "glenr"
$group = "Auditors"
Add-SPOUser -Group $group -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="create-a-site-collection-group"></a>Criar um grupo de conjunto de sites

Use o cmdlet para criar um novo grupo `New-SPOSiteGroup` SharePoint e adicioná-lo a um conjunto de sites.

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$group = "<group name name, such as Auditors>"
$level = "<permission level, such as View Only>"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

As propriedades de grupo, como níveis de permissão, podem ser atualizadas posteriormente usando `Set-SPOSiteGroup` o cmdlet.

Por exemplo, vamos adicionar o grupo Auditores com permissões Exibir Somente ao conjunto de sites contosotest no local da contosoncy:

```powershell
$tenant = "contoso"
$site = "contosotest"
$group = "Auditors"
$level = "View Only"
New-SPOSiteGroup -Group $group -PermissionLevels $level -Site https://$tenant.sharepoint.com/sites/$site
```

## <a name="remove-users-from-a-group"></a>Remover usuários de um grupo

Às vezes é preciso remover um usuário de um site ou até mesmo de todos os sites. Talvez o funcionário tenha sido transferido de uma divisão para outra ou tenha saído da empresa. Você pode facilmente fazer isso para um funcionário na interface do usuário. Mas isso não é tão fácil de fazer se você tiver que deslocar uma divisão inteira de um local para outro.

No entanto, usando os SharePoint Shell de Gerenciamento Online e arquivos CSV, isso é rápido e fácil. Nesta tarefa, você usará o Windows PowerShell para remover um usuário de um grupo de segurança de um conjunto de sites. Neste caso, você usará um arquivo CSV e removerá muitos usuários de sites diferentes.

Vamos usar o cmdlet 'Remove-SPOUser' para remover um único usuário Microsoft 365 de um grupo de conjunto de sites apenas para que possamos ver a sintaxe de comando. A sintaxe é a seguinte:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
$user = "<user account name, such as opalc>"
$group = "<group name name, such as Auditors>"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

Por exemplo, vamos remover o Bobby Overby do grupo auditores do conjunto de sites no conjunto de sites contosotest no local de espera contoso:

```powershell
$tenant = "contoso"
$site = "contosotest"
$user = "bobbyo"
$group = "Auditors"
Remove-SPOUser -LoginName $user@$tenant.com -Site https://$tenant.sharepoint.com/sites/$site -Group $group
```

Vamos supor que queremos remover o Bobby de todos os grupos nos quais ele está. Procederemos do seguinte modo:

```powershell
$tenant = "contoso"
$user = "bobbyo"
Get-SPOSite | ForEach {Get-SPOSiteGroup –Site $_.Url} | ForEach {Remove-SPOUser -LoginName $user@$tenant.com -Site &_.Url}
```

> [!WARNING]
> Este é apenas um exemplo. Você não deve executar esse comando, a menos que você realmente deseja remover um usuário de cada grupo, por exemplo, se o usuário deixar a empresa.

## <a name="automate-management-of-large-lists-of-users-and-groups"></a>Automatizar o gerenciamento de grandes listas de usuários e grupos

Para adicionar um grande número de contas SharePoint sites e dar permissões a eles, você pode usar os comandos Centro de administração do Microsoft 365, individuais do PowerShell ou o PowerShell, um arquivo CSV. Dessas escolhas, o arquivo CSV é a maneira mais rápida de automatizar esta tarefa.

O processo básico é a criação de um arquivo CSV com cabeçalhos (colunas) que correspondem aos parâmetros que requerem um script do Windows PowerShell. Você pode facilmente criar essa lista no Excel e exportá-la como um arquivo CSV. Em seguida, você pode usar um script do Windows PowerShell para pesquisar nos registros (linhas) no arquivo CSV, adicionar usuários a grupos e os grupos para os sites.

Por exemplo, vamos criar um arquivo CSV para definir um grupo de conjunto de sites, grupos e permissões. Em seguida, vamos criar um arquivo CSV para popular os grupos com os usuários. Finalmente, vamos criar e executar um script simples do Windows PowerShell que cria e preenche os grupos.

O primeiro arquivo CSV adicionará um ou mais grupos para um ou mais conjuntos de sites e terá essa estrutura:

Header:

```powershell
Site,Group,PermissionLevels
```

Item:

```powershell
https://tenant.sharepoint.com/sites/site,group,level
```

Aqui está o segundo arquivo:

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

O segundo arquivo CSV adicionará um ou mais usuários a um ou mais grupos e terá essa estrutura:

Header:

```powershell
Group,LoginName,Site
```

Item:

```powershell
group,login,https://tenant.sharepoint.com/sites/site
```

Aqui está o segundo arquivo:

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

Para a próxima etapa, você deverá salvar os dois arquivos CSV na sua unidade. Aqui estão os comandos de exemplo que usam arquivos CSV e para adicionar permissões e associação de grupo:

```powershell
Import-Csv C:\O365Admin\GroupsAndPermissions.csv | ForEach {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\O365Admin\Users.csv | ForEach {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```

O script importa o conteúdo do arquivo CSV e usa os valores nas colunas para preencher os parâmetros dos comandos **New-SPOSiteGroup** e **Add-SPOUser.** No nosso exemplo, estamos salvando isso na pastaO365Admin na unidade C, mas você pode salvá-la onde quiser.

Agora, vamos remover um monte de pessoas para vários grupos em sites diferentes usando o mesmo arquivo CSV. Este é um exemplo de comando:

```powershell
Import-Csv C:\O365Admin\Users.csv | ForEach {Remove-SPOUser -LoginName $_.LoginName -Site $_.Site -Group $_.Group}
```

## <a name="generate-user-reports"></a>Gerar relatórios de usuário

Você pode querer obter um relatório simples para alguns sites e exibir os usuários destes sites, o seu nível de permissão e outras propriedades. A sintaxe é a seguinte:

```powershell
$tenant = "<tenant name, such as litwareinc for litwareinc.com>"
$site = "<site name>"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | select * | Format-table -Wrap -AutoSize | Out-File c\UsersReport.txt -Force -Width 360 -Append
```

Você poderá usar os dados destes três sites e registrá-los em um arquivo de texto na sua unidade local. Observe que o parâmetro –Append agregará novo conteúdo a um arquivo já existente.

Por exemplo, vamos executar um relatório nos sites ContosoTest, TeamSite01 e Project01 do locatário Contoso1:

```powershell
$tenant = "contoso"
$site = "contosotest"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "TeamSite01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site |Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
$site = "Project01"
Get-SPOUser -Site https://$tenant.sharepoint.com/sites/$site | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Observe que tivemos que alterar apenas a variável **$site.** A **$tenant** mantém seu valor por todas as três executações do comando.

Mas e se você quiser fazer isso em todos os sites? Você poderá fazer isso sem ter que digitar todos os sites usando este comando:

```powershell
Get-SPOSite | ForEach {Get-SPOUser –Site $_.Url} | Format-Table -Wrap -AutoSize | Out-File c:\UsersReport.txt -Force -Width 360 -Append
```

Este relatório é muito simples, e você pode adicionar mais códigos para criar relatórios ou relatórios que incluem informações mais detalhadas e mais precisas. Mas isso deve dar uma ideia de como usar o Shell de Gerenciamento SharePoint Online para gerenciar usuários no ambiente SharePoint Online.

## <a name="see-also"></a>Confira também

[Conectar ao PowerShell do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[Gerenciar o SharePoint Online com o PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)

[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)
