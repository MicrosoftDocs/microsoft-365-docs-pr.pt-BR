---
title: Como funcionam os Links Seguros da ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: O recurso de links seguros oferece verificação de horário de clique de hiperlinks em documentos do Office e em mensagens de email. Leia este artigo para saber como os links seguros de ATP funcionam.
ms.openlocfilehash: b77ab718afdc4f68d8120e11fa5d1a321b66f32e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638005"
---
# <a name="how-atp-safe-links-works"></a><span data-ttu-id="31828-104">Como funcionam os Links Seguros da ATP</span><span class="sxs-lookup"><span data-stu-id="31828-104">How ATP Safe Links works</span></span>
> [!IMPORTANT] 
> <span data-ttu-id="31828-105">Para que os links seguros de ATP do Office 365 funcionem corretamente, todos os serviços precisam estar na mesma versão.</span><span class="sxs-lookup"><span data-stu-id="31828-105">For Office 365 ATP Safe Links to operate correctly, all of the services need to be at the same version.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="31828-106">Como os links seguros de ATP funcionam com URLs em email</span><span class="sxs-lookup"><span data-stu-id="31828-106">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="31828-107">Em um nível alto, veja como a proteção de [links de segurança ATP](atp-safe-links.md) funciona para URLs em email (hospedado no Office 365, não no local):</span><span class="sxs-lookup"><span data-stu-id="31828-107">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="31828-108">As pessoas recebem mensagens de email, algumas das quais contêm URLs.</span><span class="sxs-lookup"><span data-stu-id="31828-108">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="31828-109">Todos os emails passam pela proteção do Exchange Online, onde os filtros IP e de envelope, proteção contra malware baseado em assinatura, filtros antispam e antimalware são aplicados.</span><span class="sxs-lookup"><span data-stu-id="31828-109">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="31828-110">O email chega nas caixas de entrada de pessoas.</span><span class="sxs-lookup"><span data-stu-id="31828-110">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="31828-111">Um usuário entra no Office 365 e vai para a caixa de entrada de email.</span><span class="sxs-lookup"><span data-stu-id="31828-111">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="31828-112">O usuário abre uma mensagem de email e clica em uma URL na mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="31828-112">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="31828-113">O recurso de links seguros de ATP verifica imediatamente a URL antes de abrir o site.</span><span class="sxs-lookup"><span data-stu-id="31828-113">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="31828-114">A URL é identificada como bloqueada, mal-intencionada ou segura.</span><span class="sxs-lookup"><span data-stu-id="31828-114">The URL is identified as blocked, malicious, or safe.</span></span>
        
   - <span data-ttu-id="31828-115">Se a URL for um site incluído na [lista de URLs bloqueadas](set-up-a-custom-blocked-urls-list-wtih-atp.md)da organização, uma [página de aviso](atp-safe-links-warning-pages.md) será aberta.</span><span class="sxs-lookup"><span data-stu-id="31828-115">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="31828-116">Se a URL for um site que foi determinado como mal-intencionado, uma [página de aviso](atp-safe-links-warning-pages.md) será aberta.</span><span class="sxs-lookup"><span data-stu-id="31828-116">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
   - <span data-ttu-id="31828-117">Se a URL for para um arquivo baixável e as políticas de [links seguros ATP](set-up-atp-safe-links-policies.md) da sua organização estiverem configuradas para examinar esse conteúdo, o arquivo baixável será verificado.</span><span class="sxs-lookup"><span data-stu-id="31828-117">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="31828-118">Se a URL for considerada segura, o site abrirá.</span><span class="sxs-lookup"><span data-stu-id="31828-118">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="31828-119">Como links seguros de ATP funciona com URLs em documentos do Office</span><span class="sxs-lookup"><span data-stu-id="31828-119">How ATP Safe Links works with URLs in Office documents</span></span> 

<span data-ttu-id="31828-120">Em um nível alto, veja como a proteção de [links seguros ATP](atp-safe-links.md) funciona para URLs nos aplicativos do Microsoft 365 para aplicativos Enterprise ou Business Premium (versões atuais do Word, Excel e PowerPoint no Windows, Mac ou em um navegador, aplicativos do Office em dispositivos IOS ou Android, Visio no Windows, OneNote em um navegador):</span><span class="sxs-lookup"><span data-stu-id="31828-120">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Microsoft 365 Apps for enterprise or Business Premium applications (current versions of Word, Excel, and PowerPoint on Windows, Mac, or in a browser, Office apps on iOS or Android devices, Visio on Windows, OneNote in a browser):</span></span>
  
1. <span data-ttu-id="31828-121">As pessoas instalaram o Microsoft 365 aplicativos para empresas ou Business Premium em seus computadores, smartphones ou Tablet.</span><span class="sxs-lookup"><span data-stu-id="31828-121">People have installed Microsoft 365 Apps for enterprise or Business Premium on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="31828-122">(Ou, eles estão usando o Office em seu navegador.)</span><span class="sxs-lookup"><span data-stu-id="31828-122">(Or, they are using Office in their browser.)</span></span>
    
2. <span data-ttu-id="31828-123">Um usuário abre uma palavra, Excel, PowerPoint, OneNote (no navegador) ou Visio (no desktop) e entra no Office 365 Enterprise usando sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="31828-123">A user opens a Word, Excel, PowerPoint, OneNote (in the browser), or Visio (on desktop), and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="31828-124">O documento contém URLs.</span><span class="sxs-lookup"><span data-stu-id="31828-124">The document contains URLs.</span></span>
    
3. <span data-ttu-id="31828-125">Quando o usuário clica em uma URL no documento, o link é verificado pelo serviço de links seguros de ATP.</span><span class="sxs-lookup"><span data-stu-id="31828-125">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
   - <span data-ttu-id="31828-126">Se a URL for um site que está incluído na [lista de URLs bloqueados personalizada](set-up-a-custom-blocked-urls-list-wtih-atp.md)da organização, o usuário será levado para uma [página de aviso](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="31828-126">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="31828-127">Se a URL for um site que foi determinado como mal-intencionado, o usuário será levado para uma [página de aviso](atp-safe-links-warning-pages.md).</span><span class="sxs-lookup"><span data-stu-id="31828-127">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
   - <span data-ttu-id="31828-128">Se a URL for para um arquivo baixável e as [políticas de links seguros de ATP](set-up-atp-safe-links-policies.md) estiverem configuradas para examinar esses downloads, o arquivo baixável será verificado.</span><span class="sxs-lookup"><span data-stu-id="31828-128">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
   - <span data-ttu-id="31828-129">Se a URL for considerada segura, o usuário será levado para o site.</span><span class="sxs-lookup"><span data-stu-id="31828-129">If the URL is considered safe, the user is taken to the website.</span></span>
      
   - <span data-ttu-id="31828-130">Se a verificação de URL falhar, a proteção de links seguros não será disparada.</span><span class="sxs-lookup"><span data-stu-id="31828-130">If the URL check fails, Safe Links' protection will not trigger.</span></span> <span data-ttu-id="31828-131">Nos clientes de desktop, o usuário será avisado antes de prosseguir com o site.</span><span class="sxs-lookup"><span data-stu-id="31828-131">On the desktop clients, the user will be warned before proceeding through to the site.</span></span>
      
> [!NOTE]
> <span data-ttu-id="31828-132">Pode levar alguns segundos no início de cada sessão para verificar se o usuário tem links seguros de ATP para o Office habilitado.</span><span class="sxs-lookup"><span data-stu-id="31828-132">It may take several seconds at the beginning of each session to verify that the user has ATP Safe Links for Office enabled.</span></span> 
      
