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
description: 'Resumo: Use o PowerShell para criar novos sites do SharePoint Online e, em seguida, adicione usuários e grupos a esses sites.'
ms.openlocfilehash: 28a51cc39fe838f6c7f9c50e9d750d28e5d830c4
ms.sourcegitcommit: 24ccb910ffac4d065c512a57c5decd9dd19ef4c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/19/2020
ms.locfileid: "48594913"
---
# <a name="create-sharepoint-online-sites-and-add-users-with-powershell"></a>Criar sites do SharePoint Online e adicionar usuários com o PowerShell

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Ao usar o PowerShell para a Microsoft 365 para criar sites do SharePoint Online e adicionar usuários, você pode rapidamente e repetidamente realizar tarefas com mais rapidez do que no centro de administração do Microsoft 365. Você também pode executar tarefas que não são possíveis de realizar no centro de administração do Microsoft 365. 

## <a name="connect-to-sharepoint-online"></a>Conectar ao SharePoint Online

Os procedimentos neste tópico exigem que você se conecte ao SharePoint Online. Para obter instruções, consulte [conectar-se ao PowerShell do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

## <a name="step-1-create-new-site-collections-using-powershell"></a>Etapa 1: criar novos conjuntos de sites usando o PowerShell

Crie vários sites usando o PowerShell e um arquivo. csv que você cria usando o código de exemplo fornecido e o bloco de notas. Para este procedimento, você substituirá as informações do espaço reservado mostradas entre colchetes com suas próprias informações específicas do site e do locatário. Esse processo permite que você crie um único arquivo e execute um único comando do PowerShell que usa esse arquivo. Isso faz com que as ações sejam refeitas e portáveis e elimina muitas, se não todos os, erros que podem vir da digitação de comandos Long no Shell de gerenciamento do SharePoint Online. Há duas partes nesse procedimento. Primeiro, você criará um arquivo. csv e, em seguida, fará referência a esse arquivo. CSV usando o PowerShell, que usará seu conteúdo para criar os sites.

O cmdlet do PowerShell importa o arquivo. csv e o canaliza para um loop dentro das chaves que lê a primeira linha do arquivo como cabeçalhos de coluna. Em seguida, o cmdlet do PowerShell itera através dos registros restantes, cria um novo conjunto de sites para cada registro e atribui as propriedades do conjunto de sites de acordo com os cabeçalhos da coluna.

### <a name="create-a-csv-file"></a>Criando um arquivo .csv

> [!NOTE]
> O parâmetro de cota de recursos funciona somente em sites clássicos. Se você usar esse parâmetro em um site moderno, poderá receber uma mensagem de aviso informando que ela foi preterida. 

1. Abra o bloco de notas e cole o seguinte bloco de texto:<br/>

```powershell
Owner,StorageQuota,Url,ResourceQuota,Template,TimeZoneID,Name
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/TeamSite01,25,EHS#1,10,Contoso Team Site
owner@tenant.onmicrosoft.com,100,https://tenant.sharepoint.com/sites/Blog01,25,BLOG#0,10,Contoso Blog
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Project01,25,PROJECTSITE#0,10,Project Alpha
owner@tenant.onmicrosoft.com,150,https://tenant.sharepoint.com/sites/Community01,25,COMMUNITY#0,10,Community Site
```
<br/>Onde *locatário* é o nome do seu locatário e *proprietário* é o nome de usuário do usuário em seu locatário para o qual você deseja conceder a função de administrador do conjunto de sites principal.<br/>(Você pode pressionar CTRL + H ao usar o bloco de notas para substituir em massa mais rápido.)<br/>

2. Salve o arquivo na área de trabalho como **SiteCollections.csv**.<br/>

> [!TIP]
> Antes de usar este ou qualquer outro arquivo de script. csv ou do Windows PowerShell, é uma boa prática garantir que não haja caracteres estranhos ou não imprimíveis. Abra o arquivo no Word, e na faixa de opções, clique no ícone do parágrafo  para mostrar caracteres não imprimíveis. Não deve haver caracteres estranhos não imprimíveis. Por exemplo, não deve haver marcas do parágrafo no final do arquivo.

### <a name="run-the-windows-powershell-command"></a>Execute o comando do Windows PowerShell:

1. No prompt do Windows PowerShell, digite ou copie e cole o seguinte comando e pressione ENTER:<br/>
```powershell
Import-Csv C:\users\MyAlias\desktop\SiteCollections.csv | ForEach-Object {New-SPOSite -Owner $_.Owner -StorageQuota $_.StorageQuota -Url $_.Url -NoWait -ResourceQuota $_.ResourceQuota -Template $_.Template -TimeZoneID $_.TimeZoneID -Title $_.Name}
```
<br/>Em que *myalias* é igual ao seu alias de usuário.<br/>

2. Aguarde até que o prompt do Windows PowerShell reapareça. Pode demorar um minuto ou dois.<br/>

3. No prompt do Windows PowerShell, digite ou copie e cole o seguinte cmdlet e pressione ENTER:<br/>

```powershell
Get-SPOSite -Detailed | Format-Table -AutoSize
```
<br/>

4. Observe os novos conjuntos de sites na lista. Usando nosso arquivo CSV de exemplo, você verá os seguintes conjuntos de sites: **TeamSite01**, **Blog01**, **Project01**e **Community01**

É isso. Você criou vários conjuntos de sites usando o arquivo. csv criado e um único comando do Windows PowerShell. Agora você está pronto para criar e alocar usuários nestes sites.

## <a name="step-2-add-users-and-groups"></a>Etapa 2: Adicionar usuários ou grupos

Agora você criará usuários e irá adicioná-los ao grupo do site. Então você usará um arquivo csv. para fazer o carregamento em massa de novos grupos e usuários.

Os seguintes procedimentos continuam a usar os sites de exemplo TeamSite01, Blog01, Project01 e Community01.

### <a name="create-csv-and-ps1-files"></a>Criando arquivos .csv e .ps1

1. Abra o bloco de notas e cole o seguinte bloco de texto:<br/>

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
<br/>Onde *locatário* é igual ao nome do locatário.<br/>

2. Salve o arquivo em sua área de trabalho como **GroupsAndPermissions.csv**.<br/>

3. Abra uma nova instância do bloco de notas e cole o seguinte bloco de texto:<br/>

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
<br/>Onde *locatário* é igual ao nome do locatário e *username* é igual ao nome de usuário de um usuário existente.<br/>

4. Salve o arquivo em sua área de trabalho como **Users.csv**.<br/>

5. Abra uma nova instância do bloco de notas e cole o seguinte bloco de texto:<br/>

```powershell
Import-Csv C:\users\MyAlias\desktop\GroupsAndPermissions.csv | ForEach-Object {New-SPOSiteGroup -Group $_.Group -PermissionLevels $_.PermissionLevels -Site $_.Site}
Import-Csv C:\users\MyAlias\desktop\Users.csv | where {Add-SPOUser -Group $_.Group –LoginName $_.LoginName -Site $_.Site}
```
<br/>Em que myalias é igual ao nome de usuário do usuário que está conectado no momento.<br/>

6. Salve o arquivo em sua área de trabalho como **UsersAndGroups.ps1**. Este é um script simples do Windows PowerShell.

Agora você está pronto para executar o script UsersAndGroup.ps1 para adicionar usuários e grupos a vários conjuntos de sites.

### <a name="run-usersandgroupsps1-script"></a>Execute o script UsersAndGroups.ps1

1. Retorne ao shell de gerenciamento do SharePoint Online<br/>
2. No prompt do Windows PowerShell, digite ou copie e cole a seguinte linha e pressione ENTER:<br/>
```powershell
Set-ExecutionPolicy Bypass
```
<br/>

3. No prompt de confirmação, pressione **s**.<br/>

4. No prompt do Windows PowerShell, digite ou copie e cole o seguinte e pressione ENTER:<br/>

```powershell
c:\users\MyAlias\desktop\UsersAndGroups.ps1
```
<br/>Em que *myalias* é igual ao nome de usuário.<br/>

5. Aguarde a solicitação de retorno do prompt antes de prosseguir. Os grupos aparecerão de acordo com a criação dos mesmos. Então você verá a repetição da lista do grupo de acordo com os usuários que são agregados.

## <a name="see-also"></a>Confira também

[Conectar ao PowerShell do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Gerenciar grupos de sites do SharePoint Online com o PowerShell](manage-sharepoint-site-groups-with-powershell.md)

[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)
