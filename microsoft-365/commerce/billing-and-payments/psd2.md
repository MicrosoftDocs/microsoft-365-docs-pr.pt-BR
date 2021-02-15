---
title: Diretiva de Serviços de Pagamento 2 e Autenticação Forte do Cliente para clientes comerciais
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: A partir de 14 de setembro de 2019, os bancos dos 31 países da Área Econômica Europeia precisam verificar a identidade da pessoa que fez uma compra online antes que o pagamento possa ser processado."
keywords: diretiva de serviços de pagamento 2, autenticação forte do cliente, autenticação multifa factor
ms.openlocfilehash: d6564a8c6d31bd0758f1084e7ee9b6857aed034e
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906604"
---
# <a name="payment-services-directive-2-and-strong-customer-authentication-for-commercial-customers"></a><span data-ttu-id="2bc3a-104">Diretiva de Serviços de Pagamento 2 e Autenticação Forte do Cliente para clientes comerciais</span><span class="sxs-lookup"><span data-stu-id="2bc3a-104">Payment Services Directive 2 and Strong Customer Authentication for commercial customers</span></span>

<span data-ttu-id="2bc3a-105">A partir de 14 de setembro de 2019, os bancos dos 31 países da Área Econômica Europeia precisam verificar a identidade da pessoa que está fazendo uma compra online antes que o pagamento possa ser processado.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-105">As of September 14, 2019, banks in the 31 countries of the European Economic Area are required to verify the identity of the person making an online purchase before the payment can be processed.</span></span> <span data-ttu-id="2bc3a-106">Essa verificação requer autenticação multifa factor para ajudar a garantir que suas compras online sejam seguras e protegidas.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-106">This verification requires multi-factor authentication to help ensure your online purchases are secure and protected.</span></span> <span data-ttu-id="2bc3a-107">A data para esse requisito de verificação será atrasada para alguns países.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-107">The date for this verification requirement will be delayed for some countries.</span></span>

<span data-ttu-id="2bc3a-108">Para obter mais informações, consulte Perguntas frequentes da Microsoft sobre a Diretiva [de Serviços de Pagamento 2 e a Autenticação Forte do Cliente.](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication)</span><span class="sxs-lookup"><span data-stu-id="2bc3a-108">For more information, see [Microsoft FAQ about Payment Services Directive 2 and Strong Customer Authentication](https://support.microsoft.com/help/4517854/microsoft-account-open-banking-customer-authentication).</span></span>

## <a name="when-is-multi-factor-authentication-required"></a><span data-ttu-id="2bc3a-109">Quando a autenticação multifa factor é necessária?</span><span class="sxs-lookup"><span data-stu-id="2bc3a-109">When is multi-factor authentication required?</span></span>

<span data-ttu-id="2bc3a-110">Atualmente, os requisitos de verificação para essa diretiva usando a autenticação multifaionária só se aplicam aos clientes que usam cartões de crédito de bancos nos 31 países da Área Econômica Europeia.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-110">Currently, verification requirements for this directive using multi-factor authentication only apply to customers using credit cards from banks in the 31 countries of the European Economic Area.</span></span> <span data-ttu-id="2bc3a-111">Às vezes, os clientes serão solicitados por causa de uma ação que eles fizeram e, às vezes, são solicitados devido a eventos com suas assinaturas ou serviços existentes.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-111">Sometimes customers will be prompted because of an action that they took, and sometimes they are prompted because of events with their existing subscriptions or services.</span></span>

### <a name="customer-actions"></a><span data-ttu-id="2bc3a-112">Ações do cliente</span><span class="sxs-lookup"><span data-stu-id="2bc3a-112">Customer Actions</span></span>

<span data-ttu-id="2bc3a-113">Seu banco pode exigir verificação por meio da autenticação multifa factor.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-113">Your bank may require verification through multi-factor authentication.</span></span> <span data-ttu-id="2bc3a-114">Alguns exemplos incluem:</span><span class="sxs-lookup"><span data-stu-id="2bc3a-114">Some examples include:</span></span>
- <span data-ttu-id="2bc3a-115">Inscrever-se para uma nova assinatura</span><span class="sxs-lookup"><span data-stu-id="2bc3a-115">Signing up for a new subscription</span></span>
- <span data-ttu-id="2bc3a-116">Adicionando licenças a uma assinatura</span><span class="sxs-lookup"><span data-stu-id="2bc3a-116">Adding licenses to a subscription</span></span>
- <span data-ttu-id="2bc3a-117">Adicionar ou substituir o cartão de crédito usado para pagar uma assinatura ou serviço</span><span class="sxs-lookup"><span data-stu-id="2bc3a-117">Adding or replacing the credit card used to pay for a subscription or service</span></span>
- <span data-ttu-id="2bc3a-118">Adicionar ou substituir um cartão de crédito em um perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="2bc3a-118">Adding or replacing a credit card on a billing profile</span></span>
- <span data-ttu-id="2bc3a-119">Comprar aplicativos</span><span class="sxs-lookup"><span data-stu-id="2bc3a-119">Buying apps</span></span>

### <a name="subscription-lifecycle-events"></a><span data-ttu-id="2bc3a-120">Eventos do ciclo de vida da assinatura</span><span class="sxs-lookup"><span data-stu-id="2bc3a-120">Subscription lifecycle events</span></span>

<span data-ttu-id="2bc3a-121">Os encargos por pagamentos recorrentes podem falhar.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-121">Charges for recurring payments might fail.</span></span> <span data-ttu-id="2bc3a-122">Se o fizerem, você receberá um email com instruções a seguir.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-122">If they do, you’ll receive an email with instructions to follow.</span></span> <span data-ttu-id="2bc3a-123">Você será solicitado a responder à solicitação de verificação e fazer o pagamento atual.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-123">You’ll be prompted to respond to the verification request and make your current payment.</span></span>

## <a name="need-more-help"></a><span data-ttu-id="2bc3a-124">Precisa de mais ajuda?</span><span class="sxs-lookup"><span data-stu-id="2bc3a-124">Need more help?</span></span>

<span data-ttu-id="2bc3a-125">Sua instituição financeira é o melhor contato para esses cenários:</span><span class="sxs-lookup"><span data-stu-id="2bc3a-125">Your financial institution is the best contact for these scenarios:</span></span>
- <span data-ttu-id="2bc3a-126">Você não recebeu um código de verificação.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-126">You didn't receive a verification code.</span></span>  
- <span data-ttu-id="2bc3a-127">O processo de verificação não funcionou depois que você enviou o código de verificação.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-127">The verification process didn't work after you submitted the verification code.</span></span>
- <span data-ttu-id="2bc3a-128">Você não tem certeza se as informações de contato do seu cartão de crédito estão corretas.</span><span class="sxs-lookup"><span data-stu-id="2bc3a-128">You're not sure if the contact info for your credit card is correct.</span></span>
