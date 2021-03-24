---
title: Anexos seguros para SharePoint, OneDrive e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Saiba mais sobre o Microsoft Defender para Office 365 para arquivos no SharePoint Online, No OneDrive for Business e no Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80e30a52ef77dad32450bdfecc5010752b199b37
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053155"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="af2ba-103">Anexos seguros para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af2ba-103">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="af2ba-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="af2ba-104">**Applies to**</span></span>
- [<span data-ttu-id="af2ba-105">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="af2ba-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="af2ba-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af2ba-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="af2ba-107">Anexos seguros para SharePoint, OneDrive e Microsoft Teams no [Microsoft Defender para Office 365](whats-new-in-defender-for-office-365.md) fornece uma camada adicional de proteção para arquivos que já foram verificados no momento do carregamento pelo mecanismo de detecção de vírus comum no Microsoft [365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="af2ba-107">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="af2ba-108">Os Anexos Seguros para SharePoint, OneDrive e Microsoft Teams ajudam a detectar e bloquear arquivos existentes identificados como mal-intencionados em sites de equipe e bibliotecas de documentos.</span><span class="sxs-lookup"><span data-stu-id="af2ba-108">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="af2ba-109">Anexos seguros para SharePoint, OneDrive e Microsoft Teams não estão habilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="af2ba-109">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="af2ba-110">Para a ativar, consulte Ativar Anexos Seguros [para SharePoint, OneDrive e Microsoft Teams.](turn-on-mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="af2ba-110">To turn it on, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="af2ba-111">Como funcionam os anexos seguros do SharePoint, do OneDrive e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af2ba-111">How Safe Attachments for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="af2ba-112">Quando anexos seguros para SharePoint, OneDrive e Microsoft Teams estão habilitados e identificam um arquivo como mal-intencionado, o arquivo é bloqueado usando a integração direta com os armazenamentos de arquivos.</span><span class="sxs-lookup"><span data-stu-id="af2ba-112">When Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="af2ba-113">A imagem a seguir mostra um exemplo de um arquivo mal-intencionado detectado em uma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="af2ba-113">The following image shows an example of a malicious file detected in a library.</span></span>

![Arquivos no OneDrive for Business com um detectado como mal-intencionado](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="af2ba-115">Embora o arquivo bloqueado ainda esteja listado na biblioteca de documentos e em aplicativos web, móveis ou desktop, as pessoas não podem abrir, copiar, mover ou compartilhar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="af2ba-115">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="af2ba-116">Mas eles podem excluir o arquivo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="af2ba-116">But they can delete the blocked file.</span></span>

<span data-ttu-id="af2ba-117">Veja um exemplo da aparência de um arquivo bloqueado em um dispositivo móvel:</span><span class="sxs-lookup"><span data-stu-id="af2ba-117">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Excluir um arquivo bloqueado do OneDrive for Business do aplicativo móvel do OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="af2ba-119">Por padrão, as pessoas podem baixar um arquivo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="af2ba-119">By default, people can download a blocked file.</span></span> <span data-ttu-id="af2ba-120">Veja a aparência de baixar um arquivo bloqueado em um dispositivo móvel:</span><span class="sxs-lookup"><span data-stu-id="af2ba-120">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![Baixar um arquivo bloqueado no OneDrive for Business](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="af2ba-122">Os administradores do SharePoint Online podem impedir que as pessoas baixem arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="af2ba-122">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="af2ba-123">Para obter instruções, consulte Usar o PowerShell do [SharePoint Online para impedir que os usuários baixem arquivos mal-intencionados.](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)</span><span class="sxs-lookup"><span data-stu-id="af2ba-123">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="af2ba-124">Para saber mais sobre a experiência do usuário quando um arquivo foi detectado como mal-intencionado, consulte O que fazer quando um arquivo mal-intencionado é encontrado no [SharePoint Online, no OneDrive ou no Microsoft Teams.](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)</span><span class="sxs-lookup"><span data-stu-id="af2ba-124">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="af2ba-125">Exibir informações sobre arquivos mal-intencionados detectados por Anexos Seguros para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af2ba-125">View information about malicious files detected by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="af2ba-126">Arquivos identificados como mal-intencionados pelo Microsoft Defender para Office 365 aparecerão em relatórios para [o Microsoft Defender para Office 365](view-reports-for-mdo.md) e no Explorer (e detecções em tempo [real)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="af2ba-126">Files that are identified as malicious by Microsoft Defender for Office 365 will show up in [reports for Microsoft Defender for Office 365](view-reports-for-mdo.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="af2ba-127">A partir de maio de 2018, quando um arquivo é identificado como mal-intencionado pelo Microsoft Defender para Office 365, o arquivo também está disponível em quarentena.</span><span class="sxs-lookup"><span data-stu-id="af2ba-127">As of May 2018, when a file is identified as malicious by Microsoft Defender for Office 365, the file is also available in quarantine.</span></span> <span data-ttu-id="af2ba-128">Para obter mais informações, [consulte Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).</span><span class="sxs-lookup"><span data-stu-id="af2ba-128">For more information, see [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="af2ba-129">Lembre-se desses pontos</span><span class="sxs-lookup"><span data-stu-id="af2ba-129">Keep these points in mind</span></span>

- <span data-ttu-id="af2ba-130">O Defender para Office 365 não examinará todos os arquivos no SharePoint Online, no OneDrive for Business ou no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="af2ba-130">Defender for Office 365 will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="af2ba-131">Este é o comportamento padrão do produto.</span><span class="sxs-lookup"><span data-stu-id="af2ba-131">This is by design.</span></span> <span data-ttu-id="af2ba-132">Os arquivos são verificados de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="af2ba-132">Files are scanned asynchronously.</span></span> <span data-ttu-id="af2ba-133">O processo usa eventos de compartilhamento e atividades de convidados, juntamente com heurísticas inteligentes e sinais de ameaça para identificar arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="af2ba-133">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="af2ba-134">Certifique-se de que seus sites do SharePoint estão configurados para usar a [experiência moderna](/sharepoint/guide-to-sharepoint-modern-experience).</span><span class="sxs-lookup"><span data-stu-id="af2ba-134">Make sure your SharePoint sites are configured to use the [Modern experience](/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="af2ba-135">A proteção do Defender para o Office 365 se aplica se a experiência moderna ou a exibição clássica é usada; no entanto, os indicadores visuais de que um arquivo está bloqueado estão disponíveis apenas na experiência moderna.</span><span class="sxs-lookup"><span data-stu-id="af2ba-135">Defender for Office 365 protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="af2ba-136">Os Anexos Seguros para SharePoint, OneDrive e Microsoft Teams fazem parte da estratégia geral de proteção contra ameaças da sua organização, que inclui proteção anti-spam e anti-malware no Exchange Online Protection (EOP), bem como Links Seguros e Anexos Seguros no Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="af2ba-136">Safe Attachments for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="af2ba-137">Para saber mais, confira [Proteger contra ameaças no Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="af2ba-137">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>