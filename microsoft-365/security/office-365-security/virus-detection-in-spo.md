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
description: Saiba mais sobre proteção antivírus no SharePoint Online.
ms.openlocfilehash: f22c2a3280148eb23f4ba53ff467a533186ed791
ms.sourcegitcommit: 3d17c1d6b80672719b1878e2f321f0de39595226
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887268"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="ff933-103">Detecção de vírus no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="ff933-103">Virus detection in SharePoint Online</span></span>

<span data-ttu-id="ff933-104">O Office 365 pode ajudar a proteger seu ambiente contra malware, detectando vírus em arquivos que os usuários carregam no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ff933-104">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="ff933-105">Os arquivos podem ser verificados em busca de vírus após serem carregados.</span><span class="sxs-lookup"><span data-stu-id="ff933-105">Files may be scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="ff933-106">Se um arquivo for infectado, uma propriedade será definida para que os usuários não possam baixar ou sincronizar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="ff933-106">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff933-107">Esses recursos de antivírus no SharePoint Online são uma maneira de conter vírus.</span><span class="sxs-lookup"><span data-stu-id="ff933-107">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="ff933-108">Eles não se destinam a um único ponto de defesa contra malware para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="ff933-108">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="ff933-109">Incentivamos todos os clientes a avaliar e implementar a proteção antimalware em várias camadas e aplicar as práticas recomendadas para proteger sua infraestrutura corporativa.</span><span class="sxs-lookup"><span data-stu-id="ff933-109">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="ff933-110">Para obter mais informações sobre estratégias e práticas recomendadas, consulte [Security Roadmap](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="ff933-110">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="ff933-111">O que acontece quando um arquivo infectado é carregado no SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="ff933-111">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="ff933-112">O Office 365 usa um mecanismo de detecção de vírus comum.</span><span class="sxs-lookup"><span data-stu-id="ff933-112">Office 365 uses a common virus detection engine.</span></span> <span data-ttu-id="ff933-113">O mecanismo é executado de forma assíncrona no SharePoint Online e examina alguns arquivos após serem carregados.</span><span class="sxs-lookup"><span data-stu-id="ff933-113">The engine runs asynchronously within SharePoint Online, and scans some files after they're uploaded.</span></span> <span data-ttu-id="ff933-114">Heurísticas são usadas para determinar quais arquivos são verificados.</span><span class="sxs-lookup"><span data-stu-id="ff933-114">Heuristics are used to determine which files are scanned.</span></span> <span data-ttu-id="ff933-115">Quando um arquivo é encontrado para conter um vírus, ele é sinalizado para que ele não possa ser baixado novamente.</span><span class="sxs-lookup"><span data-stu-id="ff933-115">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="ff933-116">Em abril de 2018, removemos o limite de 25 MB dos arquivos examinados.</span><span class="sxs-lookup"><span data-stu-id="ff933-116">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="ff933-117">Veja o que acontece:</span><span class="sxs-lookup"><span data-stu-id="ff933-117">Here's what happens:</span></span>

1. <span data-ttu-id="ff933-118">Um usuário carrega um arquivo para o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ff933-118">A user uploads a file to SharePoint Online.</span></span>

2. <span data-ttu-id="ff933-119">O SharePoint Online determina se o arquivo atende aos critérios de uma verificação.</span><span class="sxs-lookup"><span data-stu-id="ff933-119">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>

3. <span data-ttu-id="ff933-120">O mecanismo de detecção de vírus examina o arquivo.</span><span class="sxs-lookup"><span data-stu-id="ff933-120">The virus detection engine scans the file.</span></span>

4. <span data-ttu-id="ff933-121">Se for encontrado um vírus, o mecanismo de vírus definirá uma propriedade no arquivo indicando que ele está infectado.</span><span class="sxs-lookup"><span data-stu-id="ff933-121">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="ff933-122">O que acontece quando um usuário tenta baixar um arquivo infectado usando o navegador?</span><span class="sxs-lookup"><span data-stu-id="ff933-122">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="ff933-123">Se um arquivo estiver infectado, os usuários não poderão baixar o arquivo do SharePoint online usando o navegador.</span><span class="sxs-lookup"><span data-stu-id="ff933-123">If a file is infected, users can't download the file from SharePoint Online by using the browser.</span></span>

<span data-ttu-id="ff933-124">Veja o que acontece:</span><span class="sxs-lookup"><span data-stu-id="ff933-124">Here's what happens:</span></span>

1. <span data-ttu-id="ff933-125">Um usuário abre um navegador da Web e tenta baixar um arquivo infectado do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="ff933-125">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>

2. <span data-ttu-id="ff933-126">O usuário recebe um aviso de que um vírus foi detectado.</span><span class="sxs-lookup"><span data-stu-id="ff933-126">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="ff933-127">O usuário recebe a opção de baixar o arquivo e tentar limpá-lo usando seu próprio software antivírus.</span><span class="sxs-lookup"><span data-stu-id="ff933-127">The user is given the option to download the file and attempt to clean it using their own antivirus software.</span></span>

> [!NOTE]
> <span data-ttu-id="ff933-128">Você pode usar o parâmetro *DisallowInfectedFileDownload* no cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) no PowerShell do SharePoint Online para impedir que os usuários baixem um arquivo infectado, mesmo na janela de aviso de antivírus.</span><span class="sxs-lookup"><span data-stu-id="ff933-128">You can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading an infected file, even in the anti-virus warning window.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="ff933-129">O que acontece quando o cliente de sincronização do OneDrive tenta sincronizar um arquivo infectado?</span><span class="sxs-lookup"><span data-stu-id="ff933-129">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="ff933-130">Se os usuários sincronizam arquivos com o novo cliente de sincronização do OneDrive (OneDrive. exe) ou o cliente de sincronização anterior do OneDrive for Business (Groove. exe), se um arquivo contiver um vírus, o cliente de sincronização não o baixará.</span><span class="sxs-lookup"><span data-stu-id="ff933-130">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="ff933-131">O cliente de sincronização exibirá uma notificação informando que o arquivo não pode ser sincronizado.</span><span class="sxs-lookup"><span data-stu-id="ff933-131">The sync client will display a notification that the file can't be synced.</span></span>
