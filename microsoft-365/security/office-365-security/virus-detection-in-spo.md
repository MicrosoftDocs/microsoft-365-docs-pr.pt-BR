---
title: Detecção de vírus no SharePoint Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 01/14/2019
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
description: O Office 365 pode ajudar a proteger seu ambiente contra malware, detectando vírus em arquivos que os usuários carregam no SharePoint Online. Os arquivos são verificados em busca de vírus após serem carregados. Se um arquivo for infectado, uma propriedade será definida para que os usuários não possam baixar ou sincronizar o arquivo.
ms.openlocfilehash: 9776dd7791d8543e0fd401a3c21c95d9fbf60f09
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639821"
---
# <a name="virus-detection-in-sharepoint-online"></a><span data-ttu-id="5839b-105">Detecção de vírus no SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="5839b-105">Virus detection in SharePoint Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5839b-106">Para usar esse recurso, a proteção avançada contra ameaças do Office 365 (ATP) é necessária.</span><span class="sxs-lookup"><span data-stu-id="5839b-106">To use this feature, Office 365 Advanced Threat Protection (ATP) is required.</span></span> <span data-ttu-id="5839b-107">Para saber mais, confira [Office 365 ATP para SharePoint, OneDrive e Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams).</span><span class="sxs-lookup"><span data-stu-id="5839b-107">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams).</span></span>

<span data-ttu-id="5839b-108">O Office 365 pode ajudar a proteger seu ambiente contra malware, detectando vírus em arquivos que os usuários carregam no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5839b-108">Office 365 can help protect your environment from malware by detecting viruses in files that users upload to SharePoint Online.</span></span> <span data-ttu-id="5839b-109">Os arquivos são verificados em busca de vírus após serem carregados.</span><span class="sxs-lookup"><span data-stu-id="5839b-109">Files are scanned for viruses after they are uploaded.</span></span> <span data-ttu-id="5839b-110">Se um arquivo for infectado, uma propriedade será definida para que os usuários não possam baixar ou sincronizar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="5839b-110">If a file is found to be infected, a property is set so that users can't download or sync the file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5839b-111">Esses recursos de antivírus no SharePoint Online são uma maneira de conter vírus.</span><span class="sxs-lookup"><span data-stu-id="5839b-111">These antivirus capabilities in SharePoint Online are a way to contain viruses.</span></span> <span data-ttu-id="5839b-112">Eles não se destinam a um único ponto de defesa contra malware para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="5839b-112">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="5839b-113">Incentivamos todos os clientes a avaliar e implementar a proteção antimalware em várias camadas e aplicar as práticas recomendadas para proteger sua infraestrutura corporativa.</span><span class="sxs-lookup"><span data-stu-id="5839b-113">We encourage all customers to assess and implement antimalware protection at various layers and apply best practices for securing your enterprise infrastructure.</span></span> <span data-ttu-id="5839b-114">Para obter mais informações sobre estratégias e práticas recomendadas, consulte [Security Roadmap](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="5839b-114">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span> 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="5839b-115">O que acontece quando um arquivo infectado é carregado no SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="5839b-115">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="5839b-116">O Office 365 usa um mecanismo de detecção de vírus comum.</span><span class="sxs-lookup"><span data-stu-id="5839b-116">Office 365 uses a common virus detection engine.</span></span> <span data-ttu-id="5839b-117">O mecanismo é executado de forma assíncrona no SharePoint Online e verifica os arquivos após serem carregados.</span><span class="sxs-lookup"><span data-stu-id="5839b-117">The engine runs asynchronously within SharePoint Online, and scans files after they're uploaded.</span></span> <span data-ttu-id="5839b-118">Quando um arquivo é encontrado para conter um vírus, ele é sinalizado para que ele não possa ser baixado novamente.</span><span class="sxs-lookup"><span data-stu-id="5839b-118">When a file is found to contain a virus, it's flagged so that it can't be downloaded again.</span></span> <span data-ttu-id="5839b-119">Em abril de 2018, removemos o limite de 25 MB dos arquivos examinados.</span><span class="sxs-lookup"><span data-stu-id="5839b-119">In April 2018, we removed the 25 MB limit for scanned files.</span></span>
  
<span data-ttu-id="5839b-120">Veja o que acontece:</span><span class="sxs-lookup"><span data-stu-id="5839b-120">Here's what happens:</span></span>
  
1. <span data-ttu-id="5839b-121">Um usuário carrega um arquivo para o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5839b-121">A user uploads a file to SharePoint Online.</span></span>
    
2. <span data-ttu-id="5839b-122">O mecanismo de detecção de vírus examina o arquivo.</span><span class="sxs-lookup"><span data-stu-id="5839b-122">The virus detection engine scans the file.</span></span>
    
3. <span data-ttu-id="5839b-123">Se for encontrado um vírus, o mecanismo de vírus definirá uma propriedade no arquivo indicando que ele está infectado.</span><span class="sxs-lookup"><span data-stu-id="5839b-123">If a virus is found, the virus engine sets a property on the file indicating that it is infected.</span></span>
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="5839b-124">O que acontece quando um usuário tenta baixar um arquivo infectado usando o navegador?</span><span class="sxs-lookup"><span data-stu-id="5839b-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="5839b-125">Se um arquivo estiver infectado por um vírus, os usuários não poderão baixar o arquivo do SharePoint online usando o navegador.</span><span class="sxs-lookup"><span data-stu-id="5839b-125">If a file is infected with a virus, users can't download the file from SharePoint Online by using the browser.</span></span>
  
<span data-ttu-id="5839b-126">Veja o que acontece:</span><span class="sxs-lookup"><span data-stu-id="5839b-126">Here's what happens:</span></span>
  
1. <span data-ttu-id="5839b-127">Um usuário abre um navegador da Web e tenta baixar um arquivo infectado do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="5839b-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
    
2. <span data-ttu-id="5839b-128">O usuário recebe um aviso de que um vírus foi detectado.</span><span class="sxs-lookup"><span data-stu-id="5839b-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="5839b-129">O usuário recebe a opção de baixar o arquivo e tentar limpá-lo usando seu próprio software de vírus.</span><span class="sxs-lookup"><span data-stu-id="5839b-129">The user is given the option to download the file and attempt to clean it using their own virus software.</span></span>

> [!NOTE]
> <span data-ttu-id="5839b-130">Você pode usar o cmdlet Set-SPOTenant com o parâmetro **DisallowInfectedFileDownload** para não permitir que os usuários baixem um arquivo detectado, mesmo na janela de aviso de antivírus.</span><span class="sxs-lookup"><span data-stu-id="5839b-130">You can use the Set-SPOTenant cmdlet with the **DisallowInfectedFileDownload** parameter to not allow users to download a detected file, even in the anti-virus warning window.</span></span> <span data-ttu-id="5839b-131">Confira [DisallowInfectedFileDownload]https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)(.</span><span class="sxs-lookup"><span data-stu-id="5839b-131">See [DisallowInfectedFileDownload] (https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).</span></span>
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="5839b-132">O que acontece quando o cliente de sincronização do OneDrive tenta sincronizar um arquivo infectado?</span><span class="sxs-lookup"><span data-stu-id="5839b-132">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="5839b-133">Se os usuários sincronizam arquivos com o novo cliente de sincronização do OneDrive (OneDrive. exe) ou o cliente de sincronização anterior do OneDrive for Business (Groove. exe), se um arquivo contiver um vírus, o cliente de sincronização não o baixará.</span><span class="sxs-lookup"><span data-stu-id="5839b-133">Whether users sync files with the new OneDrive sync client (OneDrive.exe) or the previous OneDrive for Business sync client (Groove.exe), if a file contains a virus, the sync client won't download it.</span></span> <span data-ttu-id="5839b-134">O cliente de sincronização exibirá uma notificação informando que o arquivo não pode ser sincronizado.</span><span class="sxs-lookup"><span data-stu-id="5839b-134">The sync client will display a notification that the file can't be synced.</span></span>
  

