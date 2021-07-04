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
ms.openlocfilehash: 383536a6ad5ac5742cf1e38081a9be984ce4806b
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289074"
---
# <a name="manage-sharepoint-online-site-groups-with-powershell"></a><span data-ttu-id="8cd77-103">Gerenciar SharePoint sites online com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="8cd77-103">Manage SharePoint Online site groups with PowerShell</span></span>

<span data-ttu-id="8cd77-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="8cd77-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8cd77-105">Embora você possa usar o Centro de administração do Microsoft 365, você também pode usar o PowerShell para Microsoft 365 gerenciar seus grupos de sites SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8cd77-105">Although you can use the Microsoft 365 admin center, you can also use PowerShell for Microsoft 365 to manage your SharePoint Online site groups.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8cd77-106">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="8cd77-106">Before you begin</span></span>

<span data-ttu-id="8cd77-107">Os procedimentos neste artigo exigem que você se conecte ao SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8cd77-107">The procedures in this article require you to connect to SharePoint Online.</span></span> <span data-ttu-id="8cd77-108">Para obter instruções, [consulte Conexão para SharePoint PowerShell Online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span><span class="sxs-lookup"><span data-stu-id="8cd77-108">For instructions, see [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

## <a name="view-sharepoint-online-with-powershell-for-microsoft-365"></a><span data-ttu-id="8cd77-109">Exibir SharePoint Online com o PowerShell para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8cd77-109">View SharePoint Online with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="8cd77-110">O SharePoint de administração online tem alguns métodos fáceis de usar para gerenciar grupos de sites.</span><span class="sxs-lookup"><span data-stu-id="8cd77-110">The SharePoint Online admin center has some easy-to-use methods for managing site groups.</span></span> <span data-ttu-id="8cd77-111">Por exemplo, suponha que você queira ver os grupos e os membros do grupo para o `https://litwareinc.sharepoint.com/sites/finance` site.</span><span class="sxs-lookup"><span data-stu-id="8cd77-111">For example, suppose you want to look at the groups, and the group members, for the `https://litwareinc.sharepoint.com/sites/finance` site.</span></span> <span data-ttu-id="8cd77-112">Veja o que você precisa fazer para:</span><span class="sxs-lookup"><span data-stu-id="8cd77-112">Here's what you have to do to:</span></span>

1. <span data-ttu-id="8cd77-113">No centro SharePoint de administração, clique em **Sites** ativos e clique na URL do site.</span><span class="sxs-lookup"><span data-stu-id="8cd77-113">From the SharePoint admin center, click **Active sites**, and then click the URL of the site.</span></span>
2. <span data-ttu-id="8cd77-114">Na página do site, clique no ícone Configurações **(localizado** no canto superior direito da página) e clique em **Permissões de site**.</span><span class="sxs-lookup"><span data-stu-id="8cd77-114">On the site page, click the **Settings** icon (located in the upper right-hand corner of the page), and then click **Site permissions**.</span></span>

<span data-ttu-id="8cd77-115">E, em seguida, repita o processo para o próximo site que você deseja examinar.</span><span class="sxs-lookup"><span data-stu-id="8cd77-115">And then repeat the process for the next site you want to look at.</span></span>

<span data-ttu-id="8cd77-116">Para obter uma lista dos grupos com o PowerShell para Microsoft 365, você pode usar os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="8cd77-116">To get a list of the groups with PowerShell for Microsoft 365, you can use the following commands:</span></span>

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

<span data-ttu-id="8cd77-117">Há duas maneiras de executar esse conjunto de comandos no prompt de comando SharePoint Shell de Gerenciamento Online:</span><span class="sxs-lookup"><span data-stu-id="8cd77-117">There are two ways to run this command set in the SharePoint Online Management Shell command prompt:</span></span>

- <span data-ttu-id="8cd77-118">Copie os comandos em Bloco de notas (ou em outro editor de texto), modifique o valor da variável **$siteURL,** selecione os comandos e, em seguida, os colará no prompt de comando do Shell de Gerenciamento SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8cd77-118">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, select the commands, and then paste them into the SharePoint Online Management Shell command prompt.</span></span> <span data-ttu-id="8cd77-119">Quando fizer isso, o PowerShell irá parar em um **>>** prompt.</span><span class="sxs-lookup"><span data-stu-id="8cd77-119">When you do, PowerShell will stop at a **>>** prompt.</span></span> <span data-ttu-id="8cd77-120">Pressione Enter para executar o `foreach` comando.</span><span class="sxs-lookup"><span data-stu-id="8cd77-120">Press Enter to execute the `foreach` command.</span></span><br/>
- <span data-ttu-id="8cd77-121">Copie os comandos para Bloco de notas (ou outro editor de texto), modifique o valor da variável **$siteURL** e salve esse arquivo de texto com um nome e a extensão .ps1 em uma pasta adequada.</span><span class="sxs-lookup"><span data-stu-id="8cd77-121">Copy the commands into Notepad (or another text editor), modify the value of the **$siteURL** variable, and then save this text file with a name and the .ps1 extension in a suitable folder.</span></span> <span data-ttu-id="8cd77-122">Em seguida, execute o script no prompt de comando SharePoint Shell de Gerenciamento Online especificando seu caminho e nome de arquivo.</span><span class="sxs-lookup"><span data-stu-id="8cd77-122">Next, run the script from the SharePoint Online Management Shell command prompt by specifying its path and file name.</span></span> <span data-ttu-id="8cd77-123">Este é um exemplo de comando:</span><span class="sxs-lookup"><span data-stu-id="8cd77-123">Here is an example command:</span></span>

```powershell
C:\Scripts\SiteGroupsAndUsers.ps1
```

<span data-ttu-id="8cd77-124">Em ambos os casos, você deve ver algo semelhante a isso:</span><span class="sxs-lookup"><span data-stu-id="8cd77-124">In both cases, you should see something similar to this:</span></span>

![SharePoint Grupos de sites online](../media/SPO-site-groups.png)

<span data-ttu-id="8cd77-126">Esses são todos os grupos que foram criados para o site e todos os `https://litwareinc.sharepoint.com/sites/finance` usuários atribuídos a esses grupos.</span><span class="sxs-lookup"><span data-stu-id="8cd77-126">These are all the groups that have been created for the site `https://litwareinc.sharepoint.com/sites/finance`, and all the users assigned to those groups.</span></span> <span data-ttu-id="8cd77-127">Os nomes de grupo estão em amarelo para ajudá-lo a separar nomes de grupo de seus membros.</span><span class="sxs-lookup"><span data-stu-id="8cd77-127">The group names are in yellow to help you separate group names from their members.</span></span>

<span data-ttu-id="8cd77-128">Como outro exemplo, aqui está um conjunto de comandos que lista os grupos e todas as associações de grupo para todos os seus sites SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="8cd77-128">As another example, here is a command set that lists the groups, and all the group memberships, for all of your SharePoint Online sites.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8cd77-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="8cd77-129">See also</span></span>

[<span data-ttu-id="8cd77-130">Conectar ao PowerShell do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="8cd77-130">Connect to SharePoint Online PowerShell</span></span>](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)

[<span data-ttu-id="8cd77-131">Criar SharePoint online e adicionar usuários com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="8cd77-131">Create SharePoint Online sites and add users with PowerShell</span></span>](create-sharepoint-sites-and-add-users-with-powershell.md)

[<span data-ttu-id="8cd77-132">Gerenciar SharePoint e grupos online com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="8cd77-132">Manage SharePoint Online users and groups with PowerShell</span></span>](manage-sharepoint-users-and-groups-with-powershell.md)

[<span data-ttu-id="8cd77-133">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="8cd77-133">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)

[<span data-ttu-id="8cd77-134">Introdução ao PowerShell para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8cd77-134">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
