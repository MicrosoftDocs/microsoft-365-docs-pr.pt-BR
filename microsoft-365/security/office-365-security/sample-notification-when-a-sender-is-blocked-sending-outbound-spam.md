---
title: Notificação de exemplo quando um remetente é bloqueado enviando spam de saída
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
ms.collection:
- M365-security-compliance
description: 'Quando um remetente é bloqueado do serviço devido ao envio de spam de saída, o administrador de domínio especificado ao configurar a política de spam de saída receberá um email de notificação semelhante ao seguinte:'
ms.openlocfilehash: badcd34bc35c8cc3cdd1cd06edefb87c6818e2e3
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073755"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a><span data-ttu-id="b4197-103">Notificação de exemplo quando um remetente é bloqueado enviando spam de saída</span><span class="sxs-lookup"><span data-stu-id="b4197-103">Sample notification when a sender is blocked sending outbound spam</span></span>

<span data-ttu-id="b4197-104">Quando um remetente é bloqueado do serviço devido ao envio de spam de saída, o administrador de domínio especificado ao [Configurar a política de spam de saída](configure-the-outbound-spam-policy.md) receberá um email de notificação semelhante ao seguinte:</span><span class="sxs-lookup"><span data-stu-id="b4197-104">When a sender is blocked from the service due to sending outbound spam, the domain admin specified when you [Configure the outbound spam policy](configure-the-outbound-spam-policy.md) will receive a notification email similar to the following:</span></span> 
  
 <span data-ttu-id="b4197-105">**Endereço do remetente:** spamalerts@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="b4197-105">**Sender address:** spamalerts@microsoft.com</span></span> 
  
 <span data-ttu-id="b4197-106">**Assunto:** Notificação de spam de \<saída- *nome* \> da conta bloqueado do envio de email de saída    </span><span class="sxs-lookup"><span data-stu-id="b4197-106">**Subject:** Outbound spam notification - \<  *account name*  \> blocked from sending outbound mail</span></span> 
  
 <span data-ttu-id="b4197-107">**Corpo:** Esta é uma resposta automática do sistema de análise de spam do Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="b4197-107">**Body:** This is an automated reply from the Exchange Online Protection Spam Analysis System.</span></span> 
  
<span data-ttu-id="b4197-108">Você está sendo contatado porque detectamos altos volumes de email marcados como spam ou outro comportamento suspeito originado da sua organização.</span><span class="sxs-lookup"><span data-stu-id="b4197-108">You are being contacted because we have detected high volumes of email marked as spam, or other suspicious behavior, originating from your organization.</span></span> <span data-ttu-id="b4197-109">As contas de email a seguir foram impedidas de enviar email (eles ainda podem receber emails):</span><span class="sxs-lookup"><span data-stu-id="b4197-109">The following email accounts have been blocked from sending email (they can still receive email):</span></span>
  
<span data-ttu-id="b4197-110">\<*nome da conta*  \></span><span class="sxs-lookup"><span data-stu-id="b4197-110">\< *account name*  \></span></span> 
  
<span data-ttu-id="b4197-111">É provável que essa conta de email tenha sido comprometida.</span><span class="sxs-lookup"><span data-stu-id="b4197-111">It is likely that this email account has been compromised.</span></span> <span data-ttu-id="b4197-112">Siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b4197-112">Please follow these steps:</span></span>
  
1. <span data-ttu-id="b4197-113">Resolva este problema ao seu lado:</span><span class="sxs-lookup"><span data-stu-id="b4197-113">Resolve this issue on your side by:</span></span>
    
  - <span data-ttu-id="b4197-114">Alterar a senha da conta.</span><span class="sxs-lookup"><span data-stu-id="b4197-114">Changing the password of the account.</span></span>
    
  - <span data-ttu-id="b4197-115">Determinando como a conta foi comprometida.</span><span class="sxs-lookup"><span data-stu-id="b4197-115">Determining how the account was compromised.</span></span>
    
  - <span data-ttu-id="b4197-116">Tomar precauções para garantir que essa vulnerabilidade não será explorada novamente.</span><span class="sxs-lookup"><span data-stu-id="b4197-116">Taking precautions to ensure that this vulnerability will not be exploited again.</span></span>
    
  - <span data-ttu-id="b4197-117">Confirmando que a fila de saída de emails foi limpa de todas as mensagens transgressores.</span><span class="sxs-lookup"><span data-stu-id="b4197-117">Confirming that your outbound mail queue has been cleared of all offending messages.</span></span>
    
2. <span data-ttu-id="b4197-118">Entre em contato com o suporte da Microsoft usando seu canal de contato normal.</span><span class="sxs-lookup"><span data-stu-id="b4197-118">Contact Microsoft support by using your regular contact channel.</span></span>
    
3. <span data-ttu-id="b4197-119">Explique que você tem um usuário que é bloqueado pelo envio de emails e que o problema foi tratado.</span><span class="sxs-lookup"><span data-stu-id="b4197-119">Explain that you have a user that is blocked from sending mail and that the problem has been dealt with.</span></span>
    
4. <span data-ttu-id="b4197-120">O agente criará um tíquete de suporte com as informações que você fornecer e o escalonará para ter o endereço de email ou o domínio desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="b4197-120">The agent will create a support ticket with the information that you provide and escalate it to have the email address or domain unblocked.</span></span>
    
5. <span data-ttu-id="b4197-121">Depois que o endereço tiver sido desbloqueado e não tiver outros problemas, você será contatado e alertado para o desbloqueio.</span><span class="sxs-lookup"><span data-stu-id="b4197-121">After the address has been unblocked, and pending no other issues, you will be contacted and alerted to the unblocking.</span></span>
    
<span data-ttu-id="b4197-122">Obrigado por nos ajudar a controlar emails indesejados.</span><span class="sxs-lookup"><span data-stu-id="b4197-122">Thank you for assisting us in controlling unwanted email.</span></span>
  
<span data-ttu-id="b4197-123">Proteção do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b4197-123">Exchange Online Protection.</span></span>
  
<span data-ttu-id="b4197-124">\*\*Observação: não responda a este email à medida que ele é enviado de um endereço não monitorado\*\*</span><span class="sxs-lookup"><span data-stu-id="b4197-124">\*\*NOTE - Please do not respond to this email as it is sent from an unmonitored address\*\*</span></span>
  
> [!TIP]
> <span data-ttu-id="b4197-125">Você também pode entrar em contato com o suporte via opções documentadas em [ajuda e suporte para o EOP](help-and-support-for-eop.md).</span><span class="sxs-lookup"><span data-stu-id="b4197-125">You can also contact support via the options documented at [Help and support for EOP](help-and-support-for-eop.md).</span></span> 
  

