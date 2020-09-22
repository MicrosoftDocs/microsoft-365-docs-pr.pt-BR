---
title: Detecção de vírus no SharePoint Online
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Saiba como o SharePoint Online detecta vírus em arquivos que os usuários carregam e impedem que os usuários baixem ou sincronizem os arquivos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8c65db566f165939d72429bcd61b7d0a880814e0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196506"
---
# <a name="virus-detection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="74f02-103">Detecção de vírus no SharePoint Online, no OneDrive e no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74f02-103">Virus detection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="74f02-104">O Microsoft 365 pode ajudar a proteger seu ambiente contra malware, detectando vírus em arquivos que os usuários carregam no SharePoint Online, no OneDrive e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="74f02-104">Microsoft 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="74f02-105">Os arquivos podem ser verificados em busca de vírus após serem carregados.</span><span class="sxs-lookup"><span data-stu-id="74f02-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="74f02-106">Se um arquivo for infectado, uma propriedade será definida para que os usuários não possam baixar ou sincronizar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="74f02-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74f02-107">Esses recursos de antivírus no SharePoint Online são uma maneira de conter vírus.</span><span class="sxs-lookup"><span data-stu-id="74f02-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="74f02-108">Eles não se destinam a um único ponto de defesa contra malware para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="74f02-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="74f02-109">Incentivamos todos os clientes a avaliar e implementar a proteção antimalware em várias camadas e aplicar as práticas recomendadas para proteger sua infraestrutura corporativa.</span><span class="sxs-lookup"><span data-stu-id="74f02-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="74f02-110">Para obter mais informações sobre estratégias e práticas recomendadas, consulte [Security Roadmap](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="74f02-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="74f02-111">O que acontece quando um arquivo infectado é carregado no SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="74f02-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="74f02-112">O Microsoft 365 usa um mecanismo de detecção de vírus comum.</span><span class="sxs-lookup"><span data-stu-id="74f02-112">Microsoft 365 uses a common virus detection engine.</span></span> <span data-ttu-id="74f02-113">O mecanismo é executado de forma assíncrona no SharePoint Online e examina alguns arquivos após serem carregados.</span><span class="sxs-lookup"><span data-stu-id="74f02-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="74f02-114">Heurísticas são usadas para determinar quais arquivos são verificados.</span><span class="sxs-lookup"><span data-stu-id="74f02-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="74f02-115">Quando um arquivo é encontrado para conter um vírus, ele é sinalizado para que ele não possa ser baixado novamente.</span><span class="sxs-lookup"><span data-stu-id="74f02-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="74f02-116">Em abril de 2018, removemos o limite de 25 MB dos arquivos examinados.</span><span class="sxs-lookup"><span data-stu-id="74f02-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="74f02-117">Veja o que acontece:</span><span class="sxs-lookup"><span data-stu-id="74f02-117">Here's what happens:</span></span>

1. <span data-ttu-id="74f02-118">Um usuário carrega um arquivo para o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="74f02-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="74f02-119">O SharePoint Online determina se o arquivo atende aos critérios de uma verificação.</span><span class="sxs-lookup"><span data-stu-id="74f02-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="74f02-120">O mecanismo de detecção de vírus examina o arquivo.</span><span class="sxs-lookup"><span data-stu-id="74f02-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="74f02-121">Se for encontrado um vírus, o mecanismo de vírus definirá uma propriedade no arquivo indicando que ele está infectado.</span><span class="sxs-lookup"><span data-stu-id="74f02-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="74f02-122">O que acontece quando um usuário tenta baixar um arquivo infectado usando o navegador?</span><span class="sxs-lookup"><span data-stu-id="74f02-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="74f02-123">Se um arquivo estiver infectado, os usuários não poderão baixar o arquivo do SharePoint online usando o navegador.</span><span class="sxs-lookup"><span data-stu-id="74f02-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="74f02-124">Veja o que acontece:</span><span class="sxs-lookup"><span data-stu-id="74f02-124">Here's what happens:</span></span>

1. <span data-ttu-id="74f02-125">Um usuário abre um navegador da Web e tenta baixar um arquivo infectado do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="74f02-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="74f02-126">O usuário recebe um aviso de que um vírus foi detectado.</span><span class="sxs-lookup"><span data-stu-id="74f02-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="74f02-127">O usuário recebe a opção de baixar o arquivo e tentar limpá-lo usando seu próprio software antivírus.</span><span class="sxs-lookup"><span data-stu-id="74f02-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
>
> <span data-ttu-id="74f02-128">Você pode usar o parâmetro *DisallowInfectedFileDownload* no cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) no PowerShell do SharePoint Online para impedir que os usuários baixem um arquivo infectado, mesmo na janela de aviso de antivírus.</span><span class="sxs-lookup"><span data-stu-id="74f02-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>
>
> <span data-ttu-id="74f02-129">Além disso, tenha em mente que, assim que você habilitar o parâmetro *DisallowInfectedFileDownload* , o acesso aos arquivos detectados/bloqueados é completamente bloqueado para usuários e administradores.</span><span class="sxs-lookup"><span data-stu-id="74f02-129">Also keep in mind, that as soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completly blocked for users and administrators.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="74f02-130">O que acontece quando o cliente de sincronização do OneDrive tenta sincronizar um arquivo infectado?</span><span class="sxs-lookup"><span data-stu-id="74f02-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="74f02-131">Se os usuários sincronizam arquivos com o novo cliente de sincronização do OneDrive (OneDrive.exe) ou com o cliente de sincronização anterior do OneDrive for Business (Groove.exe), se um arquivo contiver um vírus, o cliente de sincronização não o baixará.</span><span class="sxs-lookup"><span data-stu-id="74f02-131">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="74f02-132">O cliente de sincronização exibirá uma notificação informando que o arquivo não pode ser sincronizado.</span><span class="sxs-lookup"><span data-stu-id="74f02-132">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-office-365-atp"></a><span data-ttu-id="74f02-133">Recursos estendidos com o Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="74f02-133">Extended capabilities with Office 365 ATP</span></span>

<span data-ttu-id="74f02-134">Os clientes que habilitaram o Office 365 ATP para SharePoint, OneDrive e Microsoft Teams ativam a [ATP para SharePoint, onedrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) podem usar o centro de conformidade de & de segurança para gerenciar arquivos em quarentena para detecções AV e ATP.</span><span class="sxs-lookup"><span data-stu-id="74f02-134">Customers who enabled Office 365 ATP for Sharepoint, OneDrive, and Microsoft Teams [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) are able to use the Security & Compliance Center to manage quarantined files for AV and ATP detections.</span></span> <span data-ttu-id="74f02-135">[Somente ATP: Use o centro de conformidade de & de segurança para gerenciar arquivos em quarentena](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span><span class="sxs-lookup"><span data-stu-id="74f02-135">[ATP Only: Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="more-information"></a><span data-ttu-id="74f02-136">Mais informações</span><span class="sxs-lookup"><span data-stu-id="74f02-136">More information</span></span>

<span data-ttu-id="74f02-137">Confira [proteção contra ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) e [ative a ATP para SharePoint, onedrive e Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) para obter mais informações sobre como configurar o antivírus do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="74f02-137">See [Protect against threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide#requirements) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams?view=o365-worldwide) for more information on how to configure SharePoint Online antivirus.</span></span>


