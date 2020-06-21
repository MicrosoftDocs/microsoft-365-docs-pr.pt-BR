---
title: ATP para SharePoint, OneDrive e Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 03/19/2019
ms.topic: article
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
ms.openlocfilehash: e4a711d6554ffcb8e291d5b2154120d078995e94
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815404"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="74c09-103">ATP para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74c09-103">ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a><span data-ttu-id="74c09-104">Visão geral do Office 365 ATP para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74c09-104">Overview of Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>

<span data-ttu-id="74c09-105">As pessoas costumam compartilhar arquivos e colaborar usando o SharePoint, o OneDrive e o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="74c09-105">People regularly share files and collaborate using SharePoint, OneDrive, and Microsoft Teams.</span></span> <span data-ttu-id="74c09-106">Com a [proteção avançada contra ameaças do Office 365](office-365-atp.md) (ATP), sua organização pode colaborar de forma mais segura.</span><span class="sxs-lookup"><span data-stu-id="74c09-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can collaborate in a safer manner.</span></span> <span data-ttu-id="74c09-107">A ATP ajuda a detectar e bloquear arquivos identificados como mal-intencionados em sites de equipe e bibliotecas de documentos.</span><span class="sxs-lookup"><span data-stu-id="74c09-107">ATP helps detect and block files that are identified as malicious in team sites and document libraries.</span></span>

## <a name="how-office-365-atp-operates"></a><span data-ttu-id="74c09-108">Como o Office 365 ATP Opera</span><span class="sxs-lookup"><span data-stu-id="74c09-108">How Office 365 ATP operates</span></span>

<span data-ttu-id="74c09-109">Quando um arquivo no SharePoint Online, OneDrive for Business e Microsoft Teams é identificado como mal-intencionado, a ATP se integra diretamente aos repositórios de arquivos para bloquear esse arquivo.</span><span class="sxs-lookup"><span data-stu-id="74c09-109">When a file in SharePoint Online, OneDrive for Business, and Microsoft Teams has been identified as malicious, ATP directly integrates with the file stores to lock that file.</span></span> <span data-ttu-id="74c09-110">A imagem a seguir mostra um exemplo de um arquivo mal-intencionado detectado em uma biblioteca.</span><span class="sxs-lookup"><span data-stu-id="74c09-110">The following image shows an example of a malicious file detected in a library.</span></span>

![Arquivos no OneDrive for Business com um detectado como mal-intencionado](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

<span data-ttu-id="74c09-112">Embora o arquivo bloqueado ainda esteja listado na biblioteca de documentos e aplicativos da Web, móveis ou da área de trabalho, o arquivo bloqueado não pode ser aberto, copiado, movido ou compartilhado.</span><span class="sxs-lookup"><span data-stu-id="74c09-112">Although the blocked file is still listed in the document library and web, mobile, or desktop applications, the blocked file cannot be opened, copied, moved, or shared.</span></span> <span data-ttu-id="74c09-113">No entanto, as pessoas podem excluir um arquivo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="74c09-113">People can, however, delete a blocked file.</span></span> <span data-ttu-id="74c09-114">Veja um exemplo do que parece com o dispositivo móvel de um usuário:</span><span class="sxs-lookup"><span data-stu-id="74c09-114">Here's an example of what that looks like on a user's mobile device:</span></span>

![Excluir um arquivo bloqueado do OneDrive for Business do aplicativo móvel do OneDrive](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

<span data-ttu-id="74c09-116">Dependendo de como o Microsoft 365 é configurado, as pessoas podem ou não ter a capacidade de baixar um arquivo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="74c09-116">Depending on how Microsoft 365 is configured, people might or might not have the ability to download a blocked file.</span></span> <span data-ttu-id="74c09-117">Veja a seguir como baixar um arquivo bloqueado no dispositivo móvel de um usuário:</span><span class="sxs-lookup"><span data-stu-id="74c09-117">Here's what downloading a blocked file looks like on a user's mobile device:</span></span>

![Baixar um arquivo bloqueado no OneDrive for Business](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

<span data-ttu-id="74c09-119">Para saber mais, confira [Office 365 ATP para SharePoint, OneDrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="74c09-119">To learn more, see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

## <a name="keep-these-points-in-mind"></a><span data-ttu-id="74c09-120">Mantenha esses pontos em mente</span><span class="sxs-lookup"><span data-stu-id="74c09-120">Keep these points in mind</span></span>

- <span data-ttu-id="74c09-121">A ATP não examinará todos os arquivos de um único arquivo no SharePoint Online, no OneDrive for Business ou no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="74c09-121">ATP will not scan every single file in SharePoint Online, OneDrive for Business, or Microsoft Teams.</span></span> <span data-ttu-id="74c09-122">Isso é por desígnio.</span><span class="sxs-lookup"><span data-stu-id="74c09-122">This is by design.</span></span> <span data-ttu-id="74c09-123">Os arquivos são verificados de forma assíncrona por meio de um processo que usa eventos de atividade de compartilhamento e convidados, juntamente com heurística inteligente e sinais de ameaça para identificar arquivos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="74c09-123">Files are scanned asynchronously, through a process that uses sharing and guest activity events along with smart heuristics and threat signals to identify malicious files.</span></span>

- <span data-ttu-id="74c09-124">Certifique-se de que seus sites do SharePoint estão configurados para usar a [experiência moderna](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span><span class="sxs-lookup"><span data-stu-id="74c09-124">Make sure your SharePoint sites are configured to use the [Modern experience](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience).</span></span> <span data-ttu-id="74c09-125">Quando um arquivo é identificado como mal-intencionado e bloqueado, as pessoas podem ver que isso ocorreu na experiência moderna, mas não no modo de exibição clássico.</span><span class="sxs-lookup"><span data-stu-id="74c09-125">When a file is identified as malicious and blocked, people can see that this has occurred in the Modern experience, but not the Classic view.</span></span> <span data-ttu-id="74c09-126">A proteção ATP aplica se a experiência moderna ou o modo de exibição clássico é usado; no entanto, os indicadores visuais que um arquivo está bloqueado estão presentes apenas na experiência moderna.</span><span class="sxs-lookup"><span data-stu-id="74c09-126">ATP protection applies whether the Modern experience or the Classic view is used; however, visual indicators that a file is blocked are present only in the Modern experience.</span></span>

- <span data-ttu-id="74c09-127">Arquivos identificados como mal-intencionados no SharePoint Online, no OneDrive for Business ou no Microsoft Teams aparecerão em [relatórios para a proteção avançada contra ameaças do Office 365](view-reports-for-atp.md) e no [Explorer (e detecções em tempo real)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="74c09-127">Files that are identified as malicious in SharePoint Online, OneDrive for Business, or Microsoft Teams will show up in [reports for Office 365 Advanced Threat Protection](view-reports-for-atp.md) and in [Explorer (and real-time detections)](threat-explorer.md).</span></span>

- <span data-ttu-id="74c09-128">A ATP faz parte da estratégia geral de proteção contra ameaças da sua organização, que inclui proteção antispam e antimalware, bem como links seguros e anexos seguros.</span><span class="sxs-lookup"><span data-stu-id="74c09-128">ATP is part of your organization's overall threat protection strategy, which includes anti-spam and anti-malware protection, as well as Safe Links and Safe Attachments.</span></span> <span data-ttu-id="74c09-129">Para saber mais, confira [proteger contra ameaças no Office 365](protect-against-threats.md).</span><span class="sxs-lookup"><span data-stu-id="74c09-129">To learn more, see [Protect against threats in Office 365](protect-against-threats.md).</span></span>

- <span data-ttu-id="74c09-130">Um administrador do SharePoint Online pode determinar se é para permitir que as pessoas baixem arquivos detectados como mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="74c09-130">A SharePoint Online administrator can determine whether to enable people to download files that are detected as malicious.</span></span> <span data-ttu-id="74c09-131">Isso é feito executando-se o cmdlet Set-SPOTenant do PowerShell usando um parâmetro DisallowInfectedFileDownload (consulte [ativar o Office 365 ATP para SharePoint, onedrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span><span class="sxs-lookup"><span data-stu-id="74c09-131">This is done by running the Set-SPOTenant PowerShell cmdlet using a DisallowInfectedFileDownload parameter (see [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md)).</span></span>

## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="74c09-132">Quarentena no ATP para SharePoint Online, OneDrive for Business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74c09-132">Quarantine in ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams</span></span>

 <span data-ttu-id="74c09-133">A partir do final de maio de 2018, os recursos de [quarentena](quarantine-email-messages.md) no centro de conformidade de segurança &amp; estão sendo estendidos para ATP para SharePoint Online, onedrive for Business e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="74c09-133">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="74c09-134">Quando um arquivo no SharePoint Online, no OneDrive for Business ou no Microsoft Teams é identificado como mal-intencionado, além de a ATP impedindo que o arquivo seja aberto ou compartilhado, esse arquivo é incluído em uma lista de itens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="74c09-134">When a file in SharePoint Online, OneDrive for Business, or Microsoft Teams is identified as malicious, in addition to ATP blocking the file from being opened or shared, that file is included in a list of quarantined items.</span></span> <span data-ttu-id="74c09-135">(Na segurança &amp; Centro de conformidade, vá para **Gerenciamento de ameaças** \> **revisar** \> **quarentena** e filtrar **arquivos**.)</span><span class="sxs-lookup"><span data-stu-id="74c09-135">(In the Security &amp; Compliance Center, go to **Threat management** \> **Review** \> **Quarantine** and filter for **Files**.)</span></span>

<span data-ttu-id="74c09-136">Se você fizer parte da equipe de segurança do Microsoft 365 for Business da sua organização e tiver as [permissões necessárias atribuídas no &amp; centro de conformidade de segurança](permissions-in-the-security-and-compliance-center.md), poderá baixar, liberar, relatar e excluir arquivos detectados como mal-intencionados por ATP da quarentena.</span><span class="sxs-lookup"><span data-stu-id="74c09-136">If you're part of your organization's Microsoft 365 for business security team and have the necessary [permissions assigned in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can download, release, report, and delete files that are detected as malicious by ATP from quarantine.</span></span>

- <span data-ttu-id="74c09-137">**Liberar e relatar** um arquivo Remove o bloco ATP no arquivo no respectivo site de equipe ou biblioteca de documentos do SharePoint, onedrive ou Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="74c09-137">**Releasing and reporting** a file removes the ATP block on the file in the respective team site or document library for SharePoint, OneDrive, or Microsoft Teams.</span></span> <span data-ttu-id="74c09-138">Os usuários podem abrir, compartilhar e baixar o arquivo.</span><span class="sxs-lookup"><span data-stu-id="74c09-138">Users are then able to open, share, and download the file.</span></span> <span data-ttu-id="74c09-139">E, quando a opção **Enviar relatório para a Microsoft** for selecionada, o arquivo será relatado como falso positivo para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="74c09-139">And, when the **Send report to Microsoft** option is selected, the file is reported as a false positive to Microsoft.</span></span>

- <span data-ttu-id="74c09-140">A **exclusão de um arquivo** remove o arquivo da quarentena; no entanto, o arquivo ainda está bloqueado para ser aberto ou compartilhado.</span><span class="sxs-lookup"><span data-stu-id="74c09-140">**Deleting a file** removes the file from quarantine; however, the file is still blocked from being opened or shared.</span></span> <span data-ttu-id="74c09-141">O arquivo também deve ser excluído em sua respectiva biblioteca de documentos ou site de equipe (SharePoint Online, OneDrive for Business ou Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="74c09-141">The file must also be deleted in its respective document library or team site (SharePoint Online, OneDrive for Business, or Microsoft Teams).</span></span>

- <span data-ttu-id="74c09-142">**Baixar um arquivo** permite que você baixe e analise o arquivo em busca de falsos positivos.</span><span class="sxs-lookup"><span data-stu-id="74c09-142">**Downloading a file** enables you to download and analyze the file for any false positives.</span></span>

## <a name="next-steps"></a><span data-ttu-id="74c09-143">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="74c09-143">Next steps</span></span>

 - [<span data-ttu-id="74c09-144">Ativar o Office 365 ATP para SharePoint, OneDrive e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74c09-144">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)

 - [<span data-ttu-id="74c09-145">Exibir informações sobre arquivos mal-intencionados detectados no SharePoint, no OneDrive ou no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="74c09-145">View information about malicious files detected in SharePoint, OneDrive, or Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)

