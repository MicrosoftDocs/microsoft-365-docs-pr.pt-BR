---
title: Proteção contra vírus integrado no SharePoint Online, OneDrive e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: Saiba como o SharePoint Online detecta vírus em arquivos que os usuários carregam e impede que os usuários baixem ou sincronizem os arquivos.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dd38b196c106a36fb1a1bfc0a441620b1c5b8ba5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51202984"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a><span data-ttu-id="386ce-103">Proteção contra vírus integrado no SharePoint Online, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="386ce-103">Built-in virus protection in SharePoint Online, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="386ce-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="386ce-104">**Applies to**</span></span>
- [<span data-ttu-id="386ce-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="386ce-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="386ce-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="386ce-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="386ce-107">O Microsoft 365 usa um mecanismo de detecção de vírus comum para a verificação de arquivos que os usuários carregam no SharePoint Online, no OneDrive e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="386ce-107">Microsoft 365 uses a common virus detection engine for scanning files that users upload to SharePoint Online, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="386ce-108">Essa proteção está incluída em todas as assinaturas que incluem o SharePoint Online, o OneDrive e o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="386ce-108">This protection is included with all subscriptions that include SharePoint Online, OneDrive, and Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="386ce-109">Os recursos antivírus integrados são uma maneira de ajudar a conter vírus.</span><span class="sxs-lookup"><span data-stu-id="386ce-109">The built-in anti-virus capabilities are a way to help contain viruses.</span></span> <span data-ttu-id="386ce-110">Eles não são destinados como um único ponto de defesa contra malware para seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="386ce-110">They aren't intended as a single point of defense against malware for your environment.</span></span> <span data-ttu-id="386ce-111">Incentivamos todos os clientes a investigar e implementar a proteção anti-malware em várias camadas e aplicar práticas recomendadas para proteger sua infraestrutura corporativa.</span><span class="sxs-lookup"><span data-stu-id="386ce-111">We encourage all customers to investigate and implement anti-malware protection at various layers and apply best practices for securing their enterprise infrastructure.</span></span> <span data-ttu-id="386ce-112">Para obter mais informações sobre estratégias e práticas recomendadas, consulte [Roteiro de segurança.](security-roadmap.md)</span><span class="sxs-lookup"><span data-stu-id="386ce-112">For more information about strategies and best practices, see [Security roadmap](security-roadmap.md).</span></span>

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a><span data-ttu-id="386ce-113">O que acontece se um arquivo infectado for carregado no SharePoint Online?</span><span class="sxs-lookup"><span data-stu-id="386ce-113">What happens if an infected file is uploaded to SharePoint Online?</span></span>

<span data-ttu-id="386ce-114">O mecanismo de detecção de vírus do Microsoft 365 é executado de forma assíncrona (independente dos carregamentos de arquivos) no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="386ce-114">The Microsoft 365 virus detection engine runs asynchronously (independent from file uploads) within SharePoint Online.</span></span> <span data-ttu-id="386ce-115">**Todos os arquivos não são verificados automaticamente.**</span><span class="sxs-lookup"><span data-stu-id="386ce-115">**All files are not automatically scanned**.</span></span> <span data-ttu-id="386ce-116">A heurística determina os arquivos a examinar.</span><span class="sxs-lookup"><span data-stu-id="386ce-116">Heuristics determine the files to scan.</span></span> <span data-ttu-id="386ce-117">Quando um arquivo é encontrado para conter um vírus, o arquivo é sinalizado.</span><span class="sxs-lookup"><span data-stu-id="386ce-117">When a file is found to contain a virus, the file is flagged.</span></span> <span data-ttu-id="386ce-118">Em abril de 2018, removemos o limite de 25 MB para arquivos verificados.</span><span class="sxs-lookup"><span data-stu-id="386ce-118">In April 2018, we removed the 25 MB limit for scanned files.</span></span>

<span data-ttu-id="386ce-119">Veja o que acontece:</span><span class="sxs-lookup"><span data-stu-id="386ce-119">Here's what happens:</span></span>

1. <span data-ttu-id="386ce-120">Um usuário carrega um arquivo no SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="386ce-120">A user uploads a file to SharePoint Online.</span></span>
2. <span data-ttu-id="386ce-121">O SharePoint Online, como parte de seus processos de verificação de vírus, determina mais tarde se o arquivo atende aos critérios de uma verificação.</span><span class="sxs-lookup"><span data-stu-id="386ce-121">SharePoint Online, as part of its virus scanning processes, later determines if the file meets the criteria for a scan.</span></span>
3. <span data-ttu-id="386ce-122">Se o arquivo atender aos critérios de uma verificação, o mecanismo de detecção de vírus examinará o arquivo.</span><span class="sxs-lookup"><span data-stu-id="386ce-122">If the file meets the criteria for a scan, the virus detection engine scans the file.</span></span>
4. <span data-ttu-id="386ce-123">Se um vírus for encontrado no arquivo verificado, o mecanismo de vírus define uma propriedade no arquivo indicando que ele está infectado.</span><span class="sxs-lookup"><span data-stu-id="386ce-123">If a virus is found within the scanned file, the virus engine sets a property on the file indicating that it's infected.</span></span>

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a><span data-ttu-id="386ce-124">O que acontece quando um usuário tenta baixar um arquivo infectado usando o navegador?</span><span class="sxs-lookup"><span data-stu-id="386ce-124">What happens when a user tries to download an infected file by using the browser?</span></span>

<span data-ttu-id="386ce-125">Se um arquivo estiver infectado, os usuários não poderão baixar o arquivo do SharePoint Online usando um navegador.</span><span class="sxs-lookup"><span data-stu-id="386ce-125">If a file is infected, users can't download the file from SharePoint Online by using a browser.</span></span>

<span data-ttu-id="386ce-126">Veja o que acontece:</span><span class="sxs-lookup"><span data-stu-id="386ce-126">Here's what happens:</span></span>

1. <span data-ttu-id="386ce-127">Um usuário abre um navegador da Web e tenta baixar um arquivo infectado do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="386ce-127">A user opens a web browser and tries to download an infected file from SharePoint Online.</span></span>
2. <span data-ttu-id="386ce-128">O usuário recebe um aviso de que um vírus foi detectado.</span><span class="sxs-lookup"><span data-stu-id="386ce-128">The user is given a warning that a virus has been detected.</span></span> <span data-ttu-id="386ce-129">Por padrão, o usuário recebe a opção de baixar o arquivo e tentar limpá-lo usando o software antivírus em seu próprio dispositivo.</span><span class="sxs-lookup"><span data-stu-id="386ce-129">By default, the user is given the option to download the file and attempt to clean it using the anti-virus software on their own device.</span></span>

> [!NOTE]
>
> <span data-ttu-id="386ce-130">Os administradores podem usar o *parâmetro DisallowInfectedFileDownload* no cmdlet [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) no PowerShell do SharePoint Online para impedir que os usuários baixem arquivos infectados, mesmo na janela de aviso anti-vírus.</span><span class="sxs-lookup"><span data-stu-id="386ce-130">Admins can use the *DisallowInfectedFileDownload* parameter on the [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet in SharePoint Online PowerShell to prevent users from downloading infected files, even in the anti-virus warning window.</span></span> <span data-ttu-id="386ce-131">Para obter instruções, consulte Usar o PowerShell do [SharePoint Online para impedir que os usuários baixem arquivos mal-intencionados.](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)</span><span class="sxs-lookup"><span data-stu-id="386ce-131">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>
>
> <span data-ttu-id="386ce-132">Assim que você habilitar o *parâmetro DisallowInfectedFileDownload,* o acesso aos arquivos detectados/bloqueados será completamente bloqueado para usuários e administradores.</span><span class="sxs-lookup"><span data-stu-id="386ce-132">As soon as you enable the *DisallowInfectedFileDownload* parameter, access to the detected/blocked files is completely blocked for users and admins.</span></span>

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a><span data-ttu-id="386ce-133">O que acontece quando o cliente de sincronização do OneDrive tenta sincronizar um arquivo infectado?</span><span class="sxs-lookup"><span data-stu-id="386ce-133">What happens when the OneDrive sync client tries to sync an infected file?</span></span>

<span data-ttu-id="386ce-134">Os clientes de sincronização do OneDrive não baixarão arquivos que contêm vírus.</span><span class="sxs-lookup"><span data-stu-id="386ce-134">OneDrive sync clients will not download files that contain viruses.</span></span> <span data-ttu-id="386ce-135">O cliente de sincronização exibirá uma notificação de que o arquivo não pode ser sincronizado.</span><span class="sxs-lookup"><span data-stu-id="386ce-135">The sync client will display a notification that the file can't be synced.</span></span>

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a><span data-ttu-id="386ce-136">Recursos estendidos com o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="386ce-136">Extended capabilities with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="386ce-137">As organizações do Microsoft 365 que têm o [Microsoft Defender para Office 365](defender-for-office-365.md) incluído em sua assinatura ou comprados como complemento podem habilitar Anexos Seguros para SharePoint, OneDrive e Microsoft Teams para relatórios e proteção aprimorados.</span><span class="sxs-lookup"><span data-stu-id="386ce-137">Microsoft 365 organizations that have [Microsoft Defender for Office 365](defender-for-office-365.md) included in their subscription or purchased as an add-on can enable Safe Attachments for SharePoint, OneDrive, and Microsoft Teams for enhanced reporting and protection.</span></span> <span data-ttu-id="386ce-138">Para obter mais informações, consulte [Anexos Seguros para SharePoint, OneDrive e Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="386ce-138">For more information, see [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="386ce-139">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="386ce-139">Related Articles</span></span>

[<span data-ttu-id="386ce-140">Proteção contra malware e ransomware no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="386ce-140">Malware and ransomware protection in Microsoft 365</span></span>](/compliance/assurance/assurance-malware-and-ransomware-protection)

<span data-ttu-id="386ce-141">Para obter mais informações sobre antivírus no SharePoint Online, OneDrive e Microsoft Teams, consulte [Protect against](protect-against-threats.md) threats and Turn on [Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="386ce-141">For more information about anti-virus in SharePoint Online, OneDrive, and Microsoft Teams, see [Protect against threats](protect-against-threats.md) and [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>
