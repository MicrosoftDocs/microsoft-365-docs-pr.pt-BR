---
title: Gerenciar SharePoint sites online com o PowerShell
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
description: Neste artigo, encontre procedimentos para usar o PowerShell para Microsoft 365 gerenciar grupos de sites SharePoint Online.
ms.openlocfilehash: bcc7a00a6114a6fa2ba8aa02520267bd03a0abf5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909533"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a>Gerenciar SharePoint sites online com o PowerShell

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Embora você possa usar o Microsoft 365 de administração, você também pode usar o PowerShell para Microsoft 365 gerenciar seus grupos de sites SharePoint Online.

## <a name="before-you-begin"></a>Antes de começar

Os procedimentos neste artigo exigem que você se conecte ao SharePoint Online. Para obter instruções, [consulte Conexão para SharePoint PowerShell Online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a>Exibir SharePoint Online com o PowerShell para Microsoft 365

O SharePoint de administração online tem alguns métodos fáceis de usar para gerenciar grupos de sites. Por exemplo, suponha que você queira ver os grupos e os membros do grupo para o `https://litwareinc.sharepoint.com/sites/finance` site. Veja o que você precisa fazer para:

1. No centro SharePoint de administração, clique em **Sites** ativos e clique na URL do site.
2. Na página do site, clique no ícone Configurações **(localizado** no canto superior direito da página) e clique em **Permissões de site**.

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

Há duas maneiras de executar esse conjunto de comandos no prompt de comando SharePoint Shell de Gerenciamento Online:

- Copie os comandos em Bloco de notas (ou em outro editor de texto), modifique o valor da variável **$siteURL,** selecione os comandos e, em seguida, os colará no prompt de comando do Shell de Gerenciamento SharePoint Online. Quando fizer isso, o PowerShell irá parar em um **>>** prompt. Pressione Enter para executar o `foreach` comando.<br/>
- Copie os comandos para Bloco de notas (ou outro editor de texto), modifique o valor da variável **$siteURL** e salve esse arquivo de texto com um nome e a extensão .ps1 em uma pasta adequada. Em seguida, execute o script no prompt de comando SharePoint Shell de Gerenciamento Online especificando seu caminho e nome de arquivo. Este é um exemplo de comando:

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

Em ambos os casos, você deve ver algo semelhante a isso:

![SharePoint Grupos de sites online](../media/SPO-site-groups.png)

Esses são todos os grupos que foram criados para o site e todos os `https://litwareinc.sharepoint.com/sites/finance` usuários atribuídos a esses grupos. Os nomes de grupo estão em amarelo para ajudá-lo a separar nomes de grupo de seus membros.

Como outro exemplo, aqui está um conjunto de comandos que lista os grupos e todas as associações de grupo para todos os seus sites SharePoint Online.

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

[Conectar ao PowerShell do SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[Criar SharePoint online e adicionar usuários com o PowerShell](create-sharepoint-sites-and-add-users-with-powershell.md)

[Gerenciar SharePoint e grupos online com o PowerShell](manage-sharepoint-users-and-groups-with-powershell.md)

[Gerenciar o Microsoft 365 com o PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Introdução ao PowerShell para o Microsoft 365](getting-started-with-microsoft-365-powershell.md)