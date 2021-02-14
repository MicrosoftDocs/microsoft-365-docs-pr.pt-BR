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
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a><span data-ttu-id="01f6f-103">Gerenciar grupos de sites do SharePoint Online com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="01f6f-103">Manage SharePoint Online site groups with PowerShell</span></span>

<span data-ttu-id="01f6f-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="01f6f-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="01f6f-105">Embora você possa usar o centro de administração do Microsoft 365, você também pode usar o PowerShell para Microsoft 365 para gerenciar seus grupos de sites do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="01f6f-105">Although you can use the Microsoft 365 admin center, you can also use PowerShell for Microsoft 365 to manage your SharePoint Online site groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="01f6f-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="01f6f-106">Before you begin</span></span>

<span data-ttu-id="01f6f-107">Os procedimentos neste artigo exigem que você se conecte ao SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="01f6f-107">The procedures in this article require you to connect to SharePoint Online.</span></span> <span data-ttu-id="01f6f-108">Para obter instruções, [confira Conectar-se ao PowerShell do SharePoint Online.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)</span><span class="sxs-lookup"><span data-stu-id="01f6f-108">For instructions, see [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).</span></span>

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a><span data-ttu-id="01f6f-109">Exibir o SharePoint Online com o PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01f6f-109">View SharePoint Online with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="01f6f-110">O Centro de administração do SharePoint Online tem alguns métodos fáceis de usar para gerenciar grupos de sites.</span><span class="sxs-lookup"><span data-stu-id="01f6f-110">The SharePoint Online admin center has some easy-to-use methods for managing site groups.</span></span> <span data-ttu-id="01f6f-111">Por exemplo, suponha que você queira olhar para os grupos e os membros do grupo para o `https://litwareinc.sharepoint.com/sites/finance` site.</span><span class="sxs-lookup"><span data-stu-id="01f6f-111">For example, suppose you want to look at the groups, and the group members, for the `https://litwareinc.sharepoint.com/sites/finance` site.</span></span> <span data-ttu-id="01f6f-112">Aqui está o que você precisa fazer para:</span><span class="sxs-lookup"><span data-stu-id="01f6f-112">Here's what you have to do to:</span></span>

1. <span data-ttu-id="01f6f-113">No centro de administração do SharePoint, clique **em Sites** ativos e clique na URL do site.</span><span class="sxs-lookup"><span data-stu-id="01f6f-113">From the SharePoint admin center, click **Active sites**, and then click the URL of the site.</span></span>
2. <span data-ttu-id="01f6f-114">Na página do site, clique no ícone Configurações (localizado no canto superior direito da página) e clique em **Permissões do site.** </span><span class="sxs-lookup"><span data-stu-id="01f6f-114">On the site page, click the **Settings** icon (located in the upper right-hand corner of the page), and then click **Site permissions**.</span></span>

<span data-ttu-id="01f6f-115">E, em seguida, repita o processo para o próximo site que você deseja examinar.</span><span class="sxs-lookup"><span data-stu-id="01f6f-115">And then repeat the process for the next site you want to look at.</span></span>

<span data-ttu-id="01f6f-116">Para obter uma lista dos grupos com o PowerShell para Microsoft 365, você pode usar os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="01f6f-116">To get a list of the groups with PowerShell for Microsoft 365, you can use the following commands:</span></span>

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

<span data-ttu-id="01f6f-117">Há duas maneiras de executar esse conjunto de comandos no prompt de comando do Shell de Gerenciamento do SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="01f6f-117">There are two ways to run this command set in the SharePoint Online Management Shell command prompt:</span></span>

- <span data-ttu-id="01f6f-118">Copie os comandos no Bloco de Notas (ou em outro editor de texto), modifique o valor da variável **$siteURL,** selecione os comandos e, em seguida, os copie no prompt de comando do Shell de Gerenciamento do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="01f6f-118">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, select the commands, and then paste them into the SharePoint Online Management Shell command prompt.</span></span> <span data-ttu-id="01f6f-119">Quando você fizer isso, o PowerShell será parada em um **>>** prompt.</span><span class="sxs-lookup"><span data-stu-id="01f6f-119">When you do, PowerShell will stop at a **>>** prompt.</span></span> <span data-ttu-id="01f6f-120">Pressione Enter para executar o `foreach` comando.</span><span class="sxs-lookup"><span data-stu-id="01f6f-120">Press Enter to execute the `foreach` command.</span></span><br/>
- <span data-ttu-id="01f6f-121">Copie os comandos no Bloco de Notas (ou em outro editor de texto), modifique o valor da variável **$siteURL** e salve esse arquivo de texto com um nome e a extensão .ps1 em uma pasta adequada.</span><span class="sxs-lookup"><span data-stu-id="01f6f-121">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, and then save this text file with a name and the .ps1 extension in a suitable folder.</span></span> <span data-ttu-id="01f6f-122">Em seguida, execute o script no prompt de comando do Shell de Gerenciamento do SharePoint Online especificando seu caminho e nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="01f6f-122">Next, run the script from the SharePoint Online Management Shell command prompt by specifying its path and file name.</span></span> <span data-ttu-id="01f6f-123">Este é um exemplo de comando:</span><span class="sxs-lookup"><span data-stu-id="01f6f-123">Here is an example command:</span></span>

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

<span data-ttu-id="01f6f-124">Em ambos os casos, você deve ver algo semelhante a isto:</span><span class="sxs-lookup"><span data-stu-id="01f6f-124">In both cases, you should see something similar to this:</span></span>

![Grupos de sites do SharePoint Online](../media/SPO-site-groups.png)

<span data-ttu-id="01f6f-126">Esses são todos os grupos que foram criados para o site `https://litwareinc.sharepoint.com/sites/finance` e todos os usuários atribuídos a esses grupos.</span><span class="sxs-lookup"><span data-stu-id="01f6f-126">These are all the groups that have been created for the site `https://litwareinc.sharepoint.com/sites/finance`, and all the users assigned to those groups.</span></span> <span data-ttu-id="01f6f-127">Os nomes dos grupos estão em amarelo para ajudá-lo a separar os nomes dos grupos dos membros.</span><span class="sxs-lookup"><span data-stu-id="01f6f-127">The group names are in yellow to help you separate group names from their members.</span></span>

<span data-ttu-id="01f6f-128">Como outro exemplo, aqui está um conjunto de comandos que lista os grupos e todas as associações de grupo para todos os seus sites do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="01f6f-128">As another example, here is a command set that lists the groups, and all the group memberships, for all of your SharePoint Online sites.</span></span>

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
    
## <a name="see-also"></a><span data-ttu-id="01f6f-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="01f6f-129">See also</span></span>

[<span data-ttu-id="01f6f-130">Conectar ao PowerShell do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="01f6f-130">Connect to SharePoint Online PowerShell</span></span>](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

[<span data-ttu-id="01f6f-131">Criar sites do SharePoint Online e adicionar usuários com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="01f6f-131">Create SharePoint Online sites and add users with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="01f6f-132">Gerenciar usuários e grupos do SharePoint Online com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="01f6f-132">Manage SharePoint Online users and groups with PowerShell</span></span>](manage-sharepoint-users-and-groups-with-powershell.md)

[<span data-ttu-id="01f6f-133">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="01f6f-133">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="01f6f-134">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="01f6f-134">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

