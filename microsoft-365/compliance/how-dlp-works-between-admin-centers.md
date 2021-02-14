---
title: Como a DLP funciona com o Centro de Conformidade & segurança & de administração do Exchange
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
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
description: Saiba como a DLP no Centro de Conformidade e Segurança & funciona com regras de fluxo de emails e DLP (regras de transporte) no Centro de administração do Exchange.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 05e3c6342ab6d57c1f22de96e64a01df5fd15131
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036192"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a><span data-ttu-id="bd58b-103">Funcionamento da DLP entre o Centro de Conformidade e Segurança e o centro de administração do Exchange</span><span class="sxs-lookup"><span data-stu-id="bd58b-103">How DLP works between the Security & Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="bd58b-104">No Office 365, você pode criar uma política de prevenção contra perda de dados (DLP) em dois centros de administração diferentes:</span><span class="sxs-lookup"><span data-stu-id="bd58b-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="bd58b-105">No Centro **de Conformidade &** segurança, você pode criar uma única política DLP para ajudar a proteger o conteúdo no SharePoint, no OneDrive, no Exchange e agora no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bd58b-105">In the **Security & Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, and now Microsoft Teams.</span></span> <span data-ttu-id="bd58b-106">Quando possível, recomendamos que você crie uma política DLP aqui.</span><span class="sxs-lookup"><span data-stu-id="bd58b-106">When possible, we recommend that you create a DLP policy here.</span></span> <span data-ttu-id="bd58b-107">Para obter mais informações, [consulte DLP no Centro de Conformidade & segurança.](data-loss-prevention-policies.md)</span><span class="sxs-lookup"><span data-stu-id="bd58b-107">For more information, see [DLP in the Security & Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="bd58b-108">No Centro **de administração do Exchange,** você pode criar uma política de DLP para ajudar a proteger o conteúdo somente no Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd58b-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="bd58b-109">Essa política pode usar regras de fluxo de emails do Exchange (também conhecidas como regras de transporte), portanto, ela tem mais opções específicas para lidar com emails.</span><span class="sxs-lookup"><span data-stu-id="bd58b-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="bd58b-110">Para obter mais informações, consulte [DLP no Centro de administração do Exchange.](https://go.microsoft.com/fwlink/?linkid=852311)</span><span class="sxs-lookup"><span data-stu-id="bd58b-110">For more information, see [DLP in the Exchange admin center](https://go.microsoft.com/fwlink/?linkid=852311).</span></span>
    
<span data-ttu-id="bd58b-111">As polícias de DLP criadas nesses centros de administração funcionam lado a lado- este tópico explica como.</span><span class="sxs-lookup"><span data-stu-id="bd58b-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![Páginas DLP no Centro de Conformidade e Segurança e no Centro de administração do Exchange](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="bd58b-113">Como a DLP no Centro de Conformidade e Segurança & funciona com regras de fluxo de emails e DLP no Centro de administração do Exchange</span><span class="sxs-lookup"><span data-stu-id="bd58b-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="bd58b-114">Depois de criar uma política de DLP no Centro de & Conformidade e Segurança, a política será implantada em todos os locais incluídos na política.</span><span class="sxs-lookup"><span data-stu-id="bd58b-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="bd58b-115">Se a política incluir o Exchange Online, a política será sincronizada lá e imposta exatamente da mesma maneira que uma política de DLP criada no Centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd58b-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="bd58b-116">Se você criou políticas de DLP no Centro de administração do Exchange, essas políticas continuarão a funcionar lado a lado com quaisquer políticas de email criadas no Centro de Conformidade e Segurança &.</span><span class="sxs-lookup"><span data-stu-id="bd58b-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="bd58b-117">Mas observe que as regras criadas no Centro de administração do Exchange têm precedência.</span><span class="sxs-lookup"><span data-stu-id="bd58b-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="bd58b-118">Todas as regras de fluxo de emails do Exchange são processadas primeiro e, em seguida, as regras de DLP do Centro de Conformidade e Segurança & são processadas.</span><span class="sxs-lookup"><span data-stu-id="bd58b-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="bd58b-119">Isso significa que:</span><span class="sxs-lookup"><span data-stu-id="bd58b-119">This means that:</span></span>
  
- <span data-ttu-id="bd58b-120">As mensagens bloqueadas pelas regras de fluxo de emails do Exchange não serão examinadas pelas regras de DLP criadas no Centro de Conformidade e Segurança & Segurança.</span><span class="sxs-lookup"><span data-stu-id="bd58b-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="bd58b-121">Se uma regra de fluxo de emails do Exchange modifica uma mensagem de uma maneira que a faz corresponder a uma política de DLP no Centro de Conformidade do & de Segurança, como adicionar usuários externos, as regras de DLP detectarão isso e aplicarão a política conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="bd58b-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="bd58b-122">Observe também que as regras de fluxo de emails do Exchange que usam a ação "parar o processamento" não afetam o processamento de regras de D & LP no Centro de Conformidade e Segurança - elas ainda serão processadas.</span><span class="sxs-lookup"><span data-stu-id="bd58b-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="bd58b-123">Dicas de política no Centro de Conformidade & segurança versus o Centro de administração do Exchange</span><span class="sxs-lookup"><span data-stu-id="bd58b-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="bd58b-124">As dicas de política podem funcionar com políticas de DLP e regras de fluxo de emails criadas no Centro de administração do Exchange ou com políticas de DLP criadas no Centro de Conformidade e & Segurança, mas não em ambos.</span><span class="sxs-lookup"><span data-stu-id="bd58b-124">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="bd58b-125">Isso porque essas políticas são armazenadas em locais diferentes, mas as dicas de política podem desenhar apenas de um único local.</span><span class="sxs-lookup"><span data-stu-id="bd58b-125">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="bd58b-126">Se você tiver configurado dicas de política no Centro de administração do Exchange &, todas as dicas de política que você configurar no Centro de Conformidade e Segurança não aparecerão para os usuários no Outlook na Web e no Outlook 2013 e posteriores até você desativar as dicas no Centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd58b-126">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="bd58b-127">Isso garante que suas regras atuais de fluxo de emails do Exchange continuarão a funcionar até que você opte por alternar para o Centro de Conformidade e & Segurança.</span><span class="sxs-lookup"><span data-stu-id="bd58b-127">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="bd58b-128">Observe que, embora as dicas de política possam ser extraidas apenas de um único local, as notificações por email são sempre enviadas, mesmo que você esteja usando políticas DLP no Centro de Conformidade e Segurança & e no Centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="bd58b-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
  

