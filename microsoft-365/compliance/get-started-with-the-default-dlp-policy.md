---
title: Introdução à política DLP padrão
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/10/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
description: Antes de criar a primeira política de DLP (prevenção contra perda de dados), a DLP está ajudando a proteger suas informações confidenciais com uma política padrão. Essa política padrão e sua recomendação (mostrado abaixo) ajudam a manter seu conteúdo confidencial seguro, notificando-o quando emails ou documentos contendo um número de cartão de crédito foram compartilhados com alguém de fora da sua organização.
ms.openlocfilehash: 687cfb50568310aa29f06da6bfbbc644d3edc853
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073100"
---
# <a name="get-started-with-the-default-dlp-policy"></a><span data-ttu-id="083e4-104">Introdução à política DLP padrão</span><span class="sxs-lookup"><span data-stu-id="083e4-104">Get started with the default DLP policy</span></span>

<span data-ttu-id="083e4-105">Antes de criar a primeira política de DLP (prevenção contra perda de dados), a DLP está ajudando a proteger suas informações confidenciais com uma política padrão.</span><span class="sxs-lookup"><span data-stu-id="083e4-105">Before you even create your first data loss prevention (DLP) policy, DLP is helping to protect your sensitive information with a default policy.</span></span> <span data-ttu-id="083e4-106">Essa política padrão e sua recomendação (mostrado abaixo) ajudam a manter seu conteúdo confidencial seguro, notificando-o quando emails ou documentos contendo um número de cartão de crédito foram compartilhados com alguém de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="083e4-106">This default policy and its recommendation (shown below) help keep your sensitive content secure by notifying you when email or documents containing a credit card number were shared with someone outside your organization.</span></span> <span data-ttu-id="083e4-107">Você verá essa recomendação na **Home** Page do centro de conformidade de &amp; segurança.</span><span class="sxs-lookup"><span data-stu-id="083e4-107">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="083e4-108">Você pode usar esse widget para exibir rapidamente quando e quantas informações confidenciais foram compartilhadas e, em seguida, refinar a política de DLP padrão em apenas um clique ou dois.</span><span class="sxs-lookup"><span data-stu-id="083e4-108">You can use this widget to quickly view when and how much sensitive information was shared, and then refine the default DLP policy in just a click or two.</span></span> <span data-ttu-id="083e4-109">Você também pode editar a política de DLP padrão a qualquer momento, pois ela é totalmente personalizável.</span><span class="sxs-lookup"><span data-stu-id="083e4-109">You can also edit the default DLP policy at any time because it's fully customizable.</span></span> <span data-ttu-id="083e4-110">Observe que, se você não vir a recomendação primeiro, tente clicar **+ mais** na parte inferior da seção **recomendada para você** .</span><span class="sxs-lookup"><span data-stu-id="083e4-110">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![Widget chamado proteger mais conteúdo compartilhado](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a><span data-ttu-id="083e4-112">Exibir o relatório e refinar a política de DLP padrão</span><span class="sxs-lookup"><span data-stu-id="083e4-112">View the report and refine the default DLP policy</span></span>

<span data-ttu-id="083e4-113">Quando o widget mostrar que os usuários compartilharam informações confidenciais com pessoas de fora da sua organização, escolha **refinar política de DLP** na parte inferior.</span><span class="sxs-lookup"><span data-stu-id="083e4-113">When the widget shows you that users have shared sensitive information with people outside your organization, choose **Refine DLP policy** at the bottom.</span></span> 
  
<span data-ttu-id="083e4-114">O relatório detalhado mostra quando e quanto conteúdo que contém os números do cartão de crédito foi compartilhado nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="083e4-114">The detailed report shows you when and how much content containing credit card numbers was shared in the past 30 days.</span></span> <span data-ttu-id="083e4-115">Observe que as correspondências de regra podem levar até 48 horas para serem exibidas no widget.</span><span class="sxs-lookup"><span data-stu-id="083e4-115">Note that rule matches can take up to 48 hours to show up in the widget.</span></span>
  
<span data-ttu-id="083e4-116">Para ajudar a proteger as informações confidenciais, a política de DLP padrão:</span><span class="sxs-lookup"><span data-stu-id="083e4-116">To help protect the sensitive information, the default DLP policy:</span></span>
  
- <span data-ttu-id="083e4-117">Detecta quando o conteúdo no Exchange, SharePoint e OneDrive que contém pelo menos um número de cartão de crédito é compartilhado com pessoas de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="083e4-117">Detects when content in Exchange, SharePoint, and OneDrive that contains at least one credit card number is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="083e4-118">Mostra uma dica de política e envia uma notificação por email aos usuários quando eles tentam compartilhar essas informações confidenciais com pessoas de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="083e4-118">Shows a policy tip and sends an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="083e4-119">Para obter mais informações sobre essas opções, consulte [enviar notificações por email e mostrar dicas de política para políticas de DLP](use-notifications-and-policy-tips.md).</span><span class="sxs-lookup"><span data-stu-id="083e4-119">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
- <span data-ttu-id="083e4-120">Gera relatórios de atividade detalhados para que você possa rastrear coisas como quem compartilhou o conteúdo com pessoas de fora da sua organização e quando eles faziam.</span><span class="sxs-lookup"><span data-stu-id="083e4-120">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="083e4-121">Você pode usar os [relatórios de DLP](view-the-dlp-reports.md) e [dados de log de auditoria](search-the-audit-log-in-security-and-compliance.md) (onde a **atividade** = **DLP**) para ver essas informações.</span><span class="sxs-lookup"><span data-stu-id="083e4-121">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="083e4-122">Para refinar rapidamente a política de DLP padrão, você pode optar por fazê-la:</span><span class="sxs-lookup"><span data-stu-id="083e4-122">To quickly refine the default DLP policy, you can choose to have it:</span></span>
  
- <span data-ttu-id="083e4-123">Envie um email de relatório de incidentes quando os usuários compartilharem essas informações confidenciais com pessoas de fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="083e4-123">Send you an incident report email when users share this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="083e4-124">Adicione outros usuários ao relatório de incidentes de email.</span><span class="sxs-lookup"><span data-stu-id="083e4-124">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="083e4-125">Bloquear o acesso ao conteúdo que contém as informações confidenciais, mas permitir que o usuário substitua e compartilhe ou envie se necessário.</span><span class="sxs-lookup"><span data-stu-id="083e4-125">Block access to the content containing the sensitive information, but allow the user to override and share or send if they need to.</span></span>
    
<span data-ttu-id="083e4-126">Para obter mais informações sobre relatórios de incidentes ou restringir o acesso, consulte [visão geral das políticas de prevenção contra perda de dados](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="083e4-126">For more information on incident reports or restricting access, see [Overview of data loss prevention policies](data-loss-prevention-policies.md).</span></span>
  
<span data-ttu-id="083e4-127">Se você quiser alterar essas opções mais tarde, poderá editar a política de DLP padrão a qualquer momento-consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="083e4-127">If you want to change these options later, you can edit the default DLP policy at any time - see the next section.</span></span>
  
![Configurações para widget chamado proteger mais conteúdo compartilhado](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a><span data-ttu-id="083e4-129">Editar a política de DLP padrão</span><span class="sxs-lookup"><span data-stu-id="083e4-129">Edit the default DLP policy</span></span>

<span data-ttu-id="083e4-130">Essa política é chamada de **política padrão de DLP do Office 365** e aparece sob **prevenção de perda de dados** na página &amp; **política** do centro de conformidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="083e4-130">This policy is named **Default Office 365 DLP policy** and appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="083e4-131">Essa política é totalmente personalizável, o mesmo que qualquer política de DLP que você criar a partir do zero.</span><span class="sxs-lookup"><span data-stu-id="083e4-131">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="083e4-132">Você também pode desativar ou excluir a política, para que os usuários não recebam mais dicas de política ou notificações por email.</span><span class="sxs-lookup"><span data-stu-id="083e4-132">You can also turn off or delete the policy, so that your users no longer receive policy tips or email notifications.</span></span>
  
![Política de DLP chamada política padrão de DLP do Office 365](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="083e4-134">Quando o widget não aparece</span><span class="sxs-lookup"><span data-stu-id="083e4-134">When the widget does and does not appear</span></span>

<span data-ttu-id="083e4-135">O widget chamado **proteger mais conteúdo compartilhado** aparece na seção **recomendado para você** da **Home** Page do centro de conformidade de &amp; segurança.</span><span class="sxs-lookup"><span data-stu-id="083e4-135">The widget named **Further protect shared content** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="083e4-136">Este widget aparece somente quando:</span><span class="sxs-lookup"><span data-stu-id="083e4-136">This widget appears only when:</span></span>
  
- <span data-ttu-id="083e4-137">Não há políticas de prevenção contra perda de dados no &amp; centro de conformidade de segurança ou no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="083e4-137">There are no data loss prevention policies in the Security &amp; Compliance Center or Exchange admin center.</span></span> <span data-ttu-id="083e4-138">Este widget tem o objetivo de ajudá-lo a começar a usar o DLP, portanto, ele não aparecerá se você já tiver políticas de DLP.</span><span class="sxs-lookup"><span data-stu-id="083e4-138">This widget is intended to help you get started with DLP, so it doesn't appear if you already have DLP policies.</span></span>
    
- <span data-ttu-id="083e4-139">O conteúdo que contém menos um cartão de crédito foi compartilhado com alguém de fora da sua organização nos últimos 30 dias.</span><span class="sxs-lookup"><span data-stu-id="083e4-139">Content containing least one credit card has been shared with someone outside your organization in the past 30 days.</span></span>
    
<span data-ttu-id="083e4-140">Observe que as correspondências de regras podem levar até 48 horas para estar disponível para o widget, portanto, depois que as informações confidenciais compartilhadas externamente forem detectadas, pode levar até dois dias para que a recomendação seja exibida.</span><span class="sxs-lookup"><span data-stu-id="083e4-140">Note that rule matches can take up to 48 hours to be available to the widget, so after sensitive information shared externally is detected, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="083e4-141">Por fim, depois de usar o widget para refinar a política de DLP padrão, o widget desaparecerá da **Home** Page.</span><span class="sxs-lookup"><span data-stu-id="083e4-141">Finally, after you use the widget to refine the default DLP policy, the widget disappears from the **Home** page.</span></span> 
  

