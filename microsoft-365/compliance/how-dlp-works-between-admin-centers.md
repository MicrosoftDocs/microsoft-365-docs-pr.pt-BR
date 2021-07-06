---
title: Como a DLP funciona com o Centro de & de Conformidade & Exchange centro de administração
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Saiba como a DLP no Centro de Conformidade & segurança funciona com regras de DLP e fluxo de emails (regras de transporte) no centro de administração Exchange de email.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a7cd4eaafbd334c8886e0e6aa72d8c0e4c53a81e
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300047"
---
# <a name="how-dlp-works-between-the-microsoft-365-compliance-center-and-exchange-admin-center"></a><span data-ttu-id="5507b-103">Como a DLP funciona entre o Centro Microsoft 365 de Conformidade e o Exchange de administração</span><span class="sxs-lookup"><span data-stu-id="5507b-103">How DLP works between the Microsoft 365 Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="5507b-104">Em Microsoft 365, você pode criar uma política de prevenção contra perda de dados (DLP) em dois centros de administração diferentes:</span><span class="sxs-lookup"><span data-stu-id="5507b-104">In Microsoft 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="5507b-105">No Centro de Conformidade do **Microsoft 365**, você pode criar uma única política de DLP para ajudar a proteger o conteúdo em SharePoint, OneDrive, Exchange, Teams e agora Dispositivos de Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="5507b-105">In the **Microsoft 365 Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, Teams, and now Endpoint Devices.</span></span> <span data-ttu-id="5507b-106">Recomendamos que você crie uma política DLP aqui.</span><span class="sxs-lookup"><span data-stu-id="5507b-106">We recommend that you create a DLP policy here.</span></span> <span data-ttu-id="5507b-107">Para obter mais informações, consulte [Referência de Prevenção contra Perda de Dados](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5507b-107">For more information, see [Data Loss Prevention reference](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="5507b-108">No centro **Exchange de** administração, você pode criar uma política de DLP para ajudar a proteger o conteúdo somente Exchange.</span><span class="sxs-lookup"><span data-stu-id="5507b-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="5507b-109">Essa política pode usar Exchange de fluxo de emails (também conhecidas como regras de transporte), portanto, ela tem mais opções específicas para lidar com emails.</span><span class="sxs-lookup"><span data-stu-id="5507b-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="5507b-110">Para obter mais informações, [consulte DLP no Exchange de administração](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).</span><span class="sxs-lookup"><span data-stu-id="5507b-110">For more information, see [DLP in the Exchange admin center](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).</span></span>
    
<span data-ttu-id="5507b-111">As polícias de DLP criadas nesses centros de administração funcionam lado a lado - este tópico explica como.</span><span class="sxs-lookup"><span data-stu-id="5507b-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![Páginas DLP no Centro de Conformidade e Segurança e Exchange de administração](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="5507b-113">Como a DLP no Centro de Conformidade & segurança funciona com regras de fluxo de email e DLP no centro de administração Exchange de email</span><span class="sxs-lookup"><span data-stu-id="5507b-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="5507b-114">Depois de criar uma política de DLP no Centro de Conformidade & segurança, a política será implantada em todos os locais incluídos na política.</span><span class="sxs-lookup"><span data-stu-id="5507b-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="5507b-115">Se a política incluir Exchange Online, a política será sincronizada e imposta exatamente da mesma forma que uma política de DLP criada no centro de administração Exchange.</span><span class="sxs-lookup"><span data-stu-id="5507b-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="5507b-116">Se você tiver criado políticas de DLP no centro de administração do Exchange, essas políticas continuarão a funcionar lado a lado com quaisquer políticas de email criadas no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="5507b-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="5507b-117">Mas observe que as regras criadas no Exchange de administração têm precedência.</span><span class="sxs-lookup"><span data-stu-id="5507b-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="5507b-118">Todas Exchange de fluxo de emails são processadas primeiro e, em seguida, as regras de DLP do Centro de Conformidade & segurança são processadas.</span><span class="sxs-lookup"><span data-stu-id="5507b-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="5507b-119">Isso significa que:</span><span class="sxs-lookup"><span data-stu-id="5507b-119">This means that:</span></span>
  
- <span data-ttu-id="5507b-120">As mensagens bloqueadas por Exchange de fluxo de emails não serão examinadas por regras de DLP criadas no & Centro de Conformidade e Segurança.</span><span class="sxs-lookup"><span data-stu-id="5507b-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>

- <span data-ttu-id="5507b-121">As mensagens que estão em quarentena Exchange regras de fluxo de emails ou quaisquer outros filtros são executados antes que a DLP não seja digitalizada pela DLP.</span><span class="sxs-lookup"><span data-stu-id="5507b-121">Messages that are quarantined by Exchange mail flow rules or any other filters run before DLP will not be scanned by DLP.</span></span>
    
- <span data-ttu-id="5507b-122">Se uma regra Exchange de fluxo de emails modifica uma mensagem de forma que a faz corresponder a uma política de DLP no Centro de Conformidade do & de Segurança , como adicionar usuários externos, as regras de DLP detectarão isso e imporão a política conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="5507b-122">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="5507b-123">Observe também que Exchange regras de fluxo de emails que usam a ação "parar o processamento" não afetam o processamento de regras de DLP no Centro de Conformidade & segurança - elas ainda serão processadas.</span><span class="sxs-lookup"><span data-stu-id="5507b-123">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="5507b-124">Dicas de política no Centro de Conformidade & segurança versus o Exchange de administração</span><span class="sxs-lookup"><span data-stu-id="5507b-124">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="5507b-125">As dicas de política podem funcionar com políticas de DLP e regras de fluxo de emails criadas no centro de administração do Exchange ou com políticas de DLP criadas no Centro de Conformidade & Segurança, mas não ambos.</span><span class="sxs-lookup"><span data-stu-id="5507b-125">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="5507b-126">Isso porque essas políticas são armazenadas em locais diferentes, mas as dicas de política só podem ser desenhar de um único local.</span><span class="sxs-lookup"><span data-stu-id="5507b-126">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="5507b-127">Se você configurou dicas de política no centro de administração do Exchange, todas as dicas de política que você configurar no Centro de Conformidade do & de Segurança não aparecerão para os usuários no Outlook na Web e no Outlook 2013 e posterior até que você desligue as dicas no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="5507b-127">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="5507b-128">Isso garante que as regras atuais Exchange fluxo de emails continuem a funcionar até que você opte por alternar para o Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="5507b-128">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="5507b-129">Observe que, embora as dicas de política possam desenhar apenas de um único local, as notificações de email sempre são enviadas, mesmo se você estiver usando políticas DLP no Centro de Conformidade e Segurança & e no centro de administração Exchange.</span><span class="sxs-lookup"><span data-stu-id="5507b-129">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
