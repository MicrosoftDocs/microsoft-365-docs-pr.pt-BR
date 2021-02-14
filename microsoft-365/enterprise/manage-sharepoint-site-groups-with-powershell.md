---
title: Gerenciar grupos de sites do SharePoint Online com o PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/17/2019
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
description: Neste artigo, encontre procedimentos para usar o PowerShell para Microsoft 365 para gerenciar grupos de sites do SharePoint Online.
ms.openlocfilehash: fa9aff769ff84f8567c45b20c7b6c8a078b4a70c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687378"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a>Gerenciar grupos de sites do SharePoint Online com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Embora você possa usar o centro de administração do Microsoft 365, você também pode usar o PowerShell para Microsoft 365 para gerenciar seus grupos de sites do SharePoint Online.

## <a name="before-you-begin"></a>Antes de começar

Os procedimentos neste artigo exigem que você se conecte ao SharePoint Online. Para obter instruções, [confira Conectar-se ao PowerShell do SharePoint Online.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a>Exibir o SharePoint Online com o PowerShell para Microsoft 365

O Centro de administração do SharePoint Online tem alguns métodos fáceis de usar para gerenciar grupos de sites. Por exemplo, suponha que você queira olhar para os grupos e os membros do grupo para o `https://litwareinc.sharepoint.com/sites/finance` site. Aqui está o que você precisa fazer para:

1. No centro de administração do SharePoint, clique **em Sites** ativos e clique na URL do site.
2. Na página do site, clique no ícone Configurações (localizado no canto superior direito da página) e clique em **Permissões do site.** 

E, em seguida, repita o processo para o próximo site que você deseja examinar.

Para obter uma lista dos grupos com o PowerShell para Microsoft 365, você pode usar os seguintes comandos:

```powershell
$siteURL = "https://litwareinc.sharepoint.com/sites/finance"
$x = Get-SPOSiteGroup -Site $siteURL
foreach ($y in $x)
    {
        Write-Host $y.Title -ForegroundColor "Yellow"
        Get-SPOSiteGroup -Site $siteURL -Group $y.Title | Select-Object -ExpandProperty Users
        Write-Host
    }
```

Há duas maneiras de executar esse conjunto de comandos no prompt de comando do Shell de Gerenciamento do SharePoint Online:

- Copie os comandos no Bloco de Notas (ou em outro editor de texto), modifique o valor da variável **$siteURL,** selecione os comandos e, em seguida, os copie no prompt de comando do Shell de Gerenciamento do SharePoint Online. Quando você fizer isso, o PowerShell será parada em um **>>** prompt. Pressione Enter para executar o `foreach` comando.<br/>
- Copie os comandos no Bloco de Notas (ou em outro editor de texto), modifique o valor da variável **$siteURL** e salve esse arquivo de texto com um nome e a extensão .ps1 em uma pasta adequada. Em seguida, execute o script no prompt de comando do Shell de Gerenciamento do SharePoint Online especificando seu caminho e nome de arquivo. Este é um exemplo de comando:

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

Em ambos os casos, você deve ver algo semelhante a isto:

![Grupos de sites do SharePoint Online](../media/SPO-site-groups.png)

Esses são todos os grupos que foram criados para o site `https://litwareinc.sharepoint.com/sites/finance` e todos os usuários atribuídos a esses grupos. Os nomes dos grupos estão em amarelo para ajudá-lo a separar os nomes dos grupos dos membros.

Como outro exemplo, aqui está um conjunto de comandos que lista os grupos e todas as associações de grupo para todos os seus sites do SharePoint Online.

```powershell
$x = Get-SPOSite
foreach ($y in $x)
    {
        Write-Host $y.Url -ForegroundColor "Yellow"
        $z = Get-SPOSiteGroup -Site $y.Url
        foreach ($a in $z)
            {
                 $b = Get-SPOSiteGroup -Site $y.Url -Group $a.Title 
                 Write-Host $b.Title -ForegroundColor "Cyan"
                 $b | Select-Object -ExpandProperty Users
                 Write-Host
            }
    }
```
    
## <a name="see-also"></a>Confira também

[Conectar ao PowerShell do SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Criar sites do SharePoint Online e adicionar usuários com o PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Gerenciar usuários e grupos do SharePoint Online com o PowerShell](manage-sharepoint-users-and-groups-with-powershell.md)

[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)

