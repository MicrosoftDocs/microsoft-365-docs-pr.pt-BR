---
title: ATP para SharePoint, OneDrive e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Saiba mais sobre a proteção avançada contra ameaças do Office 365 para arquivos no SharePoint Online, OneDrive for Business e Microsoft Teams.
ms.openlocfilehash: 95557e99817f7e7d3fe678c1966e4e04fd3753d7
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350884"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="1e41b-103">ATP para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1e41b-103">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1e41b-104">ATP para SharePoint, OneDrive e Microsoft Teams no [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) fornece uma camada adicional de proteção para arquivos que já foram verificados no momento do carregamento pelo [mecanismo de detecção de vírus comum no Microsoft 365](virus-detection-in-spo.md).</span><span class="sxs-lookup"><span data-stu-id="1e41b-104">ATP for SharePoint, OneDrive, and Microsoft Teams in [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md) provides an additional layer of protection for files that have already been scanned at upload time by the [common virus detection engine in Microsoft 365](virus-detection-in-spo.md).</span></span> <span data-ttu-id="1e41b-105">ATP para SharePoint, OneDrive e Microsoft Teams ajuda a detectar e bloquear arquivos existentes identificados como mal-intencionados em sites de equipe e bibliotecas de documentos.</span><span class="sxs-lookup"><span data-stu-id="1e41b-105">ATP for SharePoint, OneDrive, and Microsoft Teams helps detect and block existing files that are identified as malicious in team sites and document libraries.</span></span>

<span data-ttu-id="1e41b-106">ATP para SharePoint, OneDrive e Microsoft Teams não está habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="1e41b-106">ATP for SharePoint, OneDrive, and Microsoft Teams is not enabled by default.</span></span> <span data-ttu-id="1e41b-107">Para ativá-la, confira [Ativar ATP para SharePoint, onedrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1e41b-107">To turn it on, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a><span data-ttu-id="1e41b-108">Como a ATP para SharePoint, OneDrive e Microsoft Teams funciona</span><span class="sxs-lookup"><span data-stu-id="1e41b-108">How ATP for SharePoint, OneDrive, and Microsoft Teams works</span></span>

<span data-ttu-id="1e41b-109">Quando a ATP para SharePoint, OneDrive e Microsoft Teams está habilitada e identifica um arquivo como mal-intencionado, o arquivo é bloqueado usando a integração direta com os repositórios de arquivos.</span><span class="sxs-lookup"><span data-stu-id="1e41b-109">When ATP for SharePoint, OneDrive, and Microsoft Teams is enabled and identifies a file as malicious, the file is locked using direct integration with the file stores.</span></span> <span data-ttu-id="1e41b-110">A imagem a seguir mostra um exemplo de um arquivo mal-intencionado detectado em uma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="1e41b-110">The following image shows an example of a malicious file detected in a library.</span></span>

![Arquivos no OneDrive for Business com um detectado como mal-intencionado](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="1e41b-112">Embora o arquivo bloqueado ainda esteja listado na biblioteca de documentos e em aplicativos Web, móveis ou de área de trabalho, as pessoas não podem abrir, copiar, mover ou compartilhar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="1e41b-112">Although the blocked file is still listed in the document library and in web, mobile, or desktop applications, people can't open, copy, move, or share the file.</span></span> <span data-ttu-id="1e41b-113">Mas eles podem excluir o arquivo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="1e41b-113">But they can delete the blocked file.</span></span>

<span data-ttu-id="1e41b-114">Veja um exemplo da aparência de um arquivo bloqueado em um dispositivo móvel:</span><span class="sxs-lookup"><span data-stu-id="1e41b-114">Here's an example of what a blocked file looks like on a mobile device:</span></span>

![Excluir um arquivo bloqueado do OneDrive for Business do aplicativo móvel do OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="1e41b-116">Por padrão, as pessoas podem baixar um arquivo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="1e41b-116">By default, people can download a blocked file.</span></span> <span data-ttu-id="1e41b-117">Veja como baixar um arquivo bloqueado em um dispositivo móvel:</span><span class="sxs-lookup"><span data-stu-id="1e41b-117">Here's what downloading a blocked file looks like on a mobile device:</span></span>

![Baixar um arquivo bloqueado no OneDrive for Business](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="1e41b-119">Os administradores do SharePoint Online podem impedir que as pessoas baixem arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="1e41b-119">SharePoint Online admins can prevent people from downloading malicious files.</span></span> <span data-ttu-id="1e41b-120">Para obter instruções, confira [usar o PowerShell do SharePoint Online para impedir que os usuários baixem arquivos mal-intencionados](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span><span class="sxs-lookup"><span data-stu-id="1e41b-120">For instructions, see [Use SharePoint Online PowerShell to prevent users from downloading malicious files](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).</span></span>

<span data-ttu-id="1e41b-121">Para saber mais sobre a experiência do usuário quando um arquivo foi detectado como mal-intencionado, confira [o que fazer quando um arquivo mal-intencionado é encontrado no SharePoint Online, no onedrive ou no Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span><span class="sxs-lookup"><span data-stu-id="1e41b-121">To learn more about the user experience when a file has been detected as malicious, see [What to do when a malicious file is found in SharePoint Online, OneDrive, or Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).</span></span>

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="1e41b-122">Exibir informações sobre arquivos mal-intencionados detectados pela ATP para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1e41b-122">View information about malicious files detected by ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="1e41b-123">Arquivos identificados como mal-intencionados por ATP aparecerão em [relatórios para a proteção avançada contra ameaças do Office 365](view-reports-for-atp.md) e no [Explorer (e detecções em tempo real)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="1e41b-123">Files that are identified as malicious by ATP will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

<span data-ttu-id="1e41b-124">A partir de maio de 2018, quando um arquivo é identificado como mal-intencionado por ATP, o arquivo também está disponível em quarentena.</span><span class="sxs-lookup"><span data-stu-id="1e41b-124">As of May 2018, when a file is identified as malicious by ATP, the file is also available in quarantine.</span></span> <span data-ttu-id="1e41b-125">Para obter mais informações, consulte [usar o centro de conformidade de & de segurança para gerenciar arquivos em quarentena](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span><span class="sxs-lookup"><span data-stu-id="1e41b-125">For more information, see [Use the Security & Compliance Center to manage quarantined files](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="1e41b-126">Mantenha esses pontos em mente</span><span class="sxs-lookup"><span data-stu-id="1e41b-126">Keep these points in mind</span></span>

- <span data-ttu-id="1e41b-127">A ATP não examinará todos os arquivos de um único arquivo no SharePoint Online, no OneDrive for Business ou no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1e41b-127">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="1e41b-128">Este é o comportamento padrão do produto.</span><span class="sxs-lookup"><span data-stu-id="1e41b-128">This is by design.</span></span> <span data-ttu-id="1e41b-129">Os arquivos são verificados de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="1e41b-129">Files are scanned asynchronously.</span></span> <span data-ttu-id="1e41b-130">O processo usa eventos de atividade de compartilhamento e convidados junto com heurística inteligente e sinais de ameaça para identificar arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="1e41b-130">The process uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="1e41b-131">Certifique-se de que seus sites do SharePoint estão configurados para usar a [experiência moderna](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span><span class="sxs-lookup"><span data-stu-id="1e41b-131">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="1e41b-132">A proteção ATP aplica se a experiência moderna ou o modo de exibição clássico é usado; no entanto, os indicadores visuais que um arquivo está bloqueado estão disponíveis apenas na experiência moderna.</span><span class="sxs-lookup"><span data-stu-id="1e41b-132">ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are available only in the Modern experience.</span></span>

- <span data-ttu-id="1e41b-133">ATP para SharePoint, OneDrive e Microsoft Teams é parte da estratégia geral de proteção contra ameaças da sua organização, que inclui proteção antispam e antimalware no Exchange Online Protection (EOP), bem como links seguros e anexos seguros no Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="1e41b-133">ATP for SharePoint, OneDrive, and Microsoft Teams is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection in Exchange Online Protection (EOP), as well as Safe Links and Safe Attachments in Office 365 ATP.</span></span> <span data-ttu-id="1e41b-134">Para saber mais, confira [proteger contra ameaças no Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="1e41b-134">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>
