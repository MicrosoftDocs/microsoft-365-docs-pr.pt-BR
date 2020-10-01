---
title: Proteção de vírus interna no SharePoint Online, no OneDrive e no Microsoft Teams
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
ms.openlocfilehash: 38d6111fe665e0af79cbd93f534b1058881ff76c
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327982"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="588b6-103">Proteção de vírus interna no SharePoint Online, no OneDrive e no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="588b6-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="588b6-104">O Microsoft 365 usa um mecanismo de detecção de vírus comum para verificar arquivos que os usuários carregam no SharePoint Online, no OneDrive e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="588b6-104">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="588b6-105">Essa proteção está incluída em todas as assinaturas que incluem o SharePoint Online, o OneDrive e o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="588b6-105">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="588b6-106">Os recursos de antivírus internos são uma maneira de ajudar a conter vírus.</span><span class="sxs-lookup"><span data-stu-id="588b6-106">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="588b6-107">Eles não se destinam a um único ponto de defesa contra malware para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="588b6-107">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="588b6-108">Incentivamos todos os clientes a investigar e implementar a proteção antimalware em várias camadas e aplicar as práticas recomendadas para proteger sua infraestrutura corporativa.</span><span class="sxs-lookup"><span data-stu-id="588b6-108">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="588b6-109">Para obter mais informações sobre estratégias e práticas recomendadas, consulte [Security Roadmap](security-roadmap.md).</span><span class="sxs-lookup"><span data-stu-id="588b6-109">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="588b6-110">O que acontece quando um arquivo infectado é carregado no SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="588b6-110">What happens when an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="588b6-111">O mecanismo de detecção de vírus do Microsoft 365 é executado de forma assíncrona no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="588b6-111">The Microsoft 365 virus detection engine runs asynchronously within SharePoint Online.</span></span> <span data-ttu-id="588b6-112">**Todos os arquivos não são verificados automaticamente no carregamento**.</span><span class="sxs-lookup"><span data-stu-id="588b6-112">**All files are not automatically scanned on upload**.</span></span> <span data-ttu-id="588b6-113">Heurística determina os arquivos a serem verificados.</span><span class="sxs-lookup"><span data-stu-id="588b6-113">Heuristics determine the files to scan.</span></span> <span data-ttu-id="588b6-114">Quando um arquivo é encontrado para conter um vírus, o arquivo é sinalizado para que ele não possa ser baixado novamente.</span><span class="sxs-lookup"><span data-stu-id="588b6-114">When a file is found to contain a virus, the file is flagged so it can't be downloaded again.</span></span> <span data-ttu-id="588b6-115">Em abril de 2018, removemos o limite de 25 MB dos arquivos examinados.</span><span class="sxs-lookup"><span data-stu-id="588b6-115">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="588b6-116">Veja o que acontece:</span><span class="sxs-lookup"><span data-stu-id="588b6-116">Here's what happens:</span></span>

1. <span data-ttu-id="588b6-117">Um usuário carrega um arquivo para o SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="588b6-117">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="588b6-118">O SharePoint Online determina se o arquivo atende aos critérios de uma verificação.</span><span class="sxs-lookup"><span data-stu-id="588b6-118">SharePoint Online determines whether the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="588b6-119">O mecanismo de detecção de vírus examina o arquivo.</span><span class="sxs-lookup"><span data-stu-id="588b6-119">The virus detection engine scans the file.</span></span>
4. <span data-ttu-id="588b6-120">Se for encontrado um vírus, o mecanismo de vírus definirá uma propriedade no arquivo indicando que ele está infectado.</span><span class="sxs-lookup"><span data-stu-id="588b6-120">If a virus is found, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="588b6-121">O que acontece quando um usuário tenta baixar um arquivo infectado usando o navegador?</span><span class="sxs-lookup"><span data-stu-id="588b6-121">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="588b6-122">Se um arquivo estiver infectado, os usuários não poderão baixar o arquivo do SharePoint online usando um navegador.</span><span class="sxs-lookup"><span data-stu-id="588b6-122">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="588b6-123">Veja o que acontece:</span><span class="sxs-lookup"><span data-stu-id="588b6-123">Here's what happens:</span></span>

1. <span data-ttu-id="588b6-124">Um usuário abre um navegador da Web e tenta baixar um arquivo infectado do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="588b6-124">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="588b6-125">O usuário recebe um aviso de que um vírus foi detectado.</span><span class="sxs-lookup"><span data-stu-id="588b6-125">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="588b6-126">Por padrão, o usuário recebe a opção de baixar o arquivo e tentar limpá-lo usando o software antivírus em seu próprio dispositivo.</span><span class="sxs-lookup"><span data-stu-id="588b6-126">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="588b6-127">Os administradores podem usar o parâmetro *DisallowInfectedFileDownload* no cmdlet [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) no PowerShell do SharePoint Online para impedir que os usuários baixem arquivos infectados, mesmo na janela de aviso de antivírus.</span><span class="sxs-lookup"><span data-stu-id="588b6-127">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="588b6-128">Para obter instruções, confira [usar o PowerShell do SharePoint Online para impedir que os usuários baixem arquivos mal-intencionados](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span><span class="sxs-lookup"><span data-stu-id="588b6-128">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="588b6-129">Assim que você habilita o parâmetro *DisallowInfectedFileDownload* , o acesso aos arquivos detectados/bloqueados é completamente bloqueado para usuários e administradores.</span><span class="sxs-lookup"><span data-stu-id="588b6-129">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="588b6-130">O que acontece quando o cliente de sincronização do OneDrive tenta sincronizar um arquivo infectado?</span><span class="sxs-lookup"><span data-stu-id="588b6-130">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="588b6-131">Os clientes de sincronização do OneDrive não baixarão arquivos que contenham vírus.</span><span class="sxs-lookup"><span data-stu-id="588b6-131">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="588b6-132">O cliente de sincronização exibirá uma notificação informando que o arquivo não pode ser sincronizado.</span><span class="sxs-lookup"><span data-stu-id="588b6-132">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-office-365-advanced-threat-protection"></a><span data-ttu-id="588b6-133">Recursos estendidos com a proteção avançada contra ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="588b6-133">Extended capabilities with Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="588b6-134">As organizações 365 da Microsoft que têm a [proteção avançada contra ameaças do Office 365 (ATP)](office-365-atp.md) incluídas na assinatura ou compradas como um complemento podem habilitar a ATP para SharePoint, onedrive e Microsoft Teams para relatórios e proteção avançados.</span><span class="sxs-lookup"><span data-stu-id="588b6-134">Microsoft 365 organizations that have [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) included in their subscription or purchased as an add-on can enable ATP for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="588b6-135">Para obter mais informações, consulte [ATP para SharePoint, onedrive e Microsoft Teams](atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="588b6-135">For more information, see [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

## <a name="more-information"></a><span data-ttu-id="588b6-136">Mais informações</span><span class="sxs-lookup"><span data-stu-id="588b6-136">More information</span></span>

<span data-ttu-id="588b6-137">Para obter mais informações sobre anti-vírus no SharePoint Online, no OneDrive e no Microsoft Teams, consulte [proteger contra ameaças](protect-against-threats.md) e [ativar a ATP para SharePoint, onedrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="588b6-137">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>
