---
title: Diretiva 2 de serviços de pagamento e autenticação sólida de cliente para clientes comerciais
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration <!-- need to figure out what this value should be -->
localization_priority: Normal
ms.collection:
- commerce <!-- probably need to change this -->
ms.custom: ''
search.appverid:
- MET150
description: A partir de 14 de setembro de 2019, os bancos nos 31 países da área econômica européia são necessários para verificar a identidade da pessoa que fez uma compra online antes que o pagamento possa ser processado.
keywords: política de serviços de pagamento 2, autenticação de cliente forte, autenticação multifator
ms.openlocfilehash: c5047198a87b895a9e4cb7ffd0fb438980ee2d6c
ms.sourcegitcommit: a7edd3840226e67e82126bb9dee423b3458fef4d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2019
ms.locfileid: "36994062"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a><span data-ttu-id="f1a06-104">Diretiva 2 de serviços de pagamento e autenticação sólida de cliente para clientes comerciais</span><span class="sxs-lookup"><span data-stu-id="f1a06-104">Payment Services Directive 2 and Strong Customer Authentication for commercial customers</span></span>

<span data-ttu-id="f1a06-105">A partir de 14 de setembro de 2019, os bancos nos 31 países da área econômica européia são necessários para verificar a identidade da pessoa que fez uma compra online antes que o pagamento possa ser processado.</span><span class="sxs-lookup"><span data-stu-id="f1a06-105">Starting on September 14, 2019, banks in the 31 countries of the European Economic Area are required to verify the identity of the person making an online purchase before the payment can be processed.</span></span> <span data-ttu-id="f1a06-106">Essa verificação requer a autenticação multifator para ajudar a garantir que suas compras online estejam seguras e protegidas.</span><span class="sxs-lookup"><span data-stu-id="f1a06-106">This verification requires multi-factor authentication to help ensure your online purchases are secure and protected.</span></span> <span data-ttu-id="f1a06-107">A data deste requisito de verificação será atrasada para alguns países.</span><span class="sxs-lookup"><span data-stu-id="f1a06-107">The date for this verification requirement will be delayed for some countries.</span></span> 

<span data-ttu-id="f1a06-108">Para obter mais informações, consulte [perguntas frequentes sobre a política de serviços de pagamento 2 e autenticação de clientes fortes da Microsoft](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span><span class="sxs-lookup"><span data-stu-id="f1a06-108">For more information, see [Microsoft FAQ about Payment Services Directive 2 and Strong Customer Authentication](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span></span>

## <a name="when-is-multi-factor-authentication-required"></a><span data-ttu-id="f1a06-109">Quando é necessária a autenticação multifator?</span><span class="sxs-lookup"><span data-stu-id="f1a06-109">When is multi-factor authentication required?</span></span>

<span data-ttu-id="f1a06-110">Atualmente, os requisitos de verificação dessa diretiva usando a autenticação multifator só se aplicam aos clientes que usam cartões de crédito de bancos nos 31 países da área econômica européia.</span><span class="sxs-lookup"><span data-stu-id="f1a06-110">Currently, verification requirements for this directive using multi-factor authentication only apply to customers using credit cards from banks in the 31 countries of the European Economic Area.</span></span> <span data-ttu-id="f1a06-111">Às vezes, os clientes serão solicitados por causa de uma ação que eles levaram e, às vezes, são solicitados por causa de eventos com suas assinaturas ou serviços existentes.</span><span class="sxs-lookup"><span data-stu-id="f1a06-111">Sometimes customers will be prompted because of an action that they took, and sometimes they are prompted because of events with their existing subscriptions or services.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="f1a06-112">Ações do cliente</span><span class="sxs-lookup"><span data-stu-id="f1a06-112">Customer Actions</span></span>

<span data-ttu-id="f1a06-113">Seu banco pode exigir a verificação por meio da autenticação multifator.</span><span class="sxs-lookup"><span data-stu-id="f1a06-113">Your bank may require verification through multi-factor authentication.</span></span> <span data-ttu-id="f1a06-114">Alguns exemplos incluem:</span><span class="sxs-lookup"><span data-stu-id="f1a06-114">Some examples include:</span></span>
- <span data-ttu-id="f1a06-115">Inscrevendo-se em uma nova assinatura</span><span class="sxs-lookup"><span data-stu-id="f1a06-115">Signing up for a new subscription</span></span>
- <span data-ttu-id="f1a06-116">Adicionando licenças a uma assinatura</span><span class="sxs-lookup"><span data-stu-id="f1a06-116">Adding licenses to a subscription</span></span>
- <span data-ttu-id="f1a06-117">Adicionando ou substituindo o cartão de crédito usado para pagar uma assinatura ou serviço</span><span class="sxs-lookup"><span data-stu-id="f1a06-117">Adding or replacing the credit card used to pay for a subscription or service</span></span>
- <span data-ttu-id="f1a06-118">Adicionar ou substituir um cartão de crédito em um perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="f1a06-118">Adding or replacing a credit card on a billing profile</span></span>
- <span data-ttu-id="f1a06-119">Comprar aplicativos</span><span class="sxs-lookup"><span data-stu-id="f1a06-119">Buying apps</span></span>

### <a name="subscription-lifecycle-events"></a><span data-ttu-id="f1a06-120">Eventos de ciclo de vida de assinatura</span><span class="sxs-lookup"><span data-stu-id="f1a06-120">Subscription lifecycle events</span></span>

<span data-ttu-id="f1a06-121">Os encargos para pagamentos recorrentes podem falhar.</span><span class="sxs-lookup"><span data-stu-id="f1a06-121">Charges for recurring payments might fail.</span></span> <span data-ttu-id="f1a06-122">Se isso ocorrer, você receberá um email com instruções para seguir.</span><span class="sxs-lookup"><span data-stu-id="f1a06-122">If they do, you’ll receive an email with instructions to follow.</span></span> <span data-ttu-id="f1a06-123">Você será solicitado a responder à solicitação de verificação e fazer o pagamento atual.</span><span class="sxs-lookup"><span data-stu-id="f1a06-123">You’ll be prompted to respond to the verification request and make your current payment.</span></span>

## <a name="need-more-help"></a><span data-ttu-id="f1a06-124">Precisa de mais ajuda?</span><span class="sxs-lookup"><span data-stu-id="f1a06-124">Need more help?</span></span>

<span data-ttu-id="f1a06-125">Sua instituição financeira é o melhor contato para estes cenários:</span><span class="sxs-lookup"><span data-stu-id="f1a06-125">Your financial institution is the best contact for these scenarios:</span></span>
- <span data-ttu-id="f1a06-126">Você não recebeu um código de verificação.</span><span class="sxs-lookup"><span data-stu-id="f1a06-126">You didn't receive a verification code.</span></span>  
- <span data-ttu-id="f1a06-127">O processo de verificação não funcionou após você ter enviado o código de verificação.</span><span class="sxs-lookup"><span data-stu-id="f1a06-127">The verification process didn't work after you submitted the verification code.</span></span>
- <span data-ttu-id="f1a06-128">Você não tem certeza se as informações de contato do cartão de crédito estão corretas.</span><span class="sxs-lookup"><span data-stu-id="f1a06-128">You're not sure if the contact info for your credit card is correct.</span></span>