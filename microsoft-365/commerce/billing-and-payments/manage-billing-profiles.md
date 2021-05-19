---
title: Compreender os perfis de cobrança
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
search.appverid: MET150
description: Saiba como os perfis de cobrança suportam faturas.
ms.date: 04/02/2021
ms.openlocfilehash: e66efe12e05d2aaf286b689c955f17c8401144f1
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537326"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="9bb2d-103">Compreender os perfis de cobrança</span><span class="sxs-lookup"><span data-stu-id="9bb2d-103">Understand billing profiles</span></span>

<span data-ttu-id="9bb2d-104">Um perfil de cobrança contém um método de pagamento, informações de cobrança e outras configurações de fatura, como o número do pedido de compra e a preferência da fatura de email.</span><span class="sxs-lookup"><span data-stu-id="9bb2d-104">A billing profile contains a payment method, Bill-to information, and other invoice settings, such as purchase order number and email invoice preference.</span></span> <span data-ttu-id="9bb2d-105">Você usa um perfil de cobrança para pagar os produtos que você compra da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9bb2d-105">You use a billing profile to pay for the products that you buy from Microsoft.</span></span> <span data-ttu-id="9bb2d-106">Um perfil de cobrança é criado automaticamente quando um usuário faz uma compra self-service.</span><span class="sxs-lookup"><span data-stu-id="9bb2d-106">A billing profile is automatically created when a user makes a self-service purchase.</span></span> <span data-ttu-id="9bb2d-107">Cada perfil de cobrança é faturado separadamente.</span><span class="sxs-lookup"><span data-stu-id="9bb2d-107">Each billing profile is invoiced separately.</span></span>

> [!NOTE]
>
> <span data-ttu-id="9bb2d-108">Os perfis de cobrança não estão disponíveis para clientes que compram  produtos e serviços da Microsoft.com ou na página Serviços de Compra do centro de administração Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9bb2d-108">Billing profiles are not available to customers who buy products and services from Microsoft.com or on the **Purchase services** page of the Microsoft 365 admin center.</span></span>

## <a name="what-are-billing-profile-roles"></a><span data-ttu-id="9bb2d-109">O que são funções de perfil de cobrança?</span><span class="sxs-lookup"><span data-stu-id="9bb2d-109">What are billing profile roles?</span></span>

<span data-ttu-id="9bb2d-110">Funções nos perfis de cobrança têm permissões para controlar compras e exibir e gerenciar faturas.</span><span class="sxs-lookup"><span data-stu-id="9bb2d-110">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="9bb2d-111">Atribua essas funções aos usuários que rastreiam, organizam e pagam faturas.</span><span class="sxs-lookup"><span data-stu-id="9bb2d-111">Assign these roles to users who track, organize, and pay invoices.</span></span> <span data-ttu-id="9bb2d-112">Por exemplo, membros da equipe de compras em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9bb2d-112">For example, members of the procurement team in your organization.</span></span>

| <span data-ttu-id="9bb2d-113">Função</span><span class="sxs-lookup"><span data-stu-id="9bb2d-113">Role</span></span>                         | <span data-ttu-id="9bb2d-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="9bb2d-114">Description</span></span>                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| <span data-ttu-id="9bb2d-115">Proprietário do perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="9bb2d-115">Billing profile owner</span></span>        | <span data-ttu-id="9bb2d-116">Gerenciar tudo para um perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="9bb2d-116">Manage everything for a billing profile</span></span>                                          |
| <span data-ttu-id="9bb2d-117">Colaborador de perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="9bb2d-117">Billing profile contributor</span></span>  | <span data-ttu-id="9bb2d-118">Gerenciar tudo, exceto permissões em um perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="9bb2d-118">Manage everything except permissions in a billing profile</span></span>                        |
| <span data-ttu-id="9bb2d-119">Leitor de perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="9bb2d-119">Billing profile reader</span></span>       | <span data-ttu-id="9bb2d-120">Exibição somente leitura de tudo em um perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="9bb2d-120">Read-only view of everything in a billing profile</span></span>                                |
| <span data-ttu-id="9bb2d-121">Gerenciador de faturas</span><span class="sxs-lookup"><span data-stu-id="9bb2d-121">Invoice manager</span></span>              | <span data-ttu-id="9bb2d-122">Exibir e pagar contas e tem uma exibição somente leitura de tudo em um perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="9bb2d-122">View and pay bills, and has a read-only view of everything in a billing profile</span></span>  |

## <a name="view-my-billing-profiles"></a><span data-ttu-id="9bb2d-123">Exibir meus perfis de cobrança</span><span class="sxs-lookup"><span data-stu-id="9bb2d-123">View my billing profiles</span></span>

> [!NOTE]
>
> <span data-ttu-id="9bb2d-124">Se você seguir estas etapas e a lista de perfis de cobrança estiver vazia, isso significa que você não tem um perfil de cobrança e não pode usar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="9bb2d-124">If you follow these steps and the billing profiles list is empty, it means that you don’t have a billing profile, and can’t use this feature.</span></span>

1. <span data-ttu-id="9bb2d-125">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Faturas e pagamentos</a>.</span><span class="sxs-lookup"><span data-stu-id="9bb2d-125">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="9bb2d-126">Selecione a **guia Perfil de cobrança** e selecione um perfil de cobrança na lista.</span><span class="sxs-lookup"><span data-stu-id="9bb2d-126">Select the **Billing profile** tab, then select a billing profile from the list.</span></span>

<span data-ttu-id="9bb2d-127">Cada perfil de cobrança inclui as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="9bb2d-127">Each billing profile includes the following information:</span></span>

- <span data-ttu-id="9bb2d-128">**Nome e status do perfil de cobrança** &ndash; O nome exclusivo do perfil de cobrança e se o perfil de cobrança está ativo ou desabilitado para compra.</span><span class="sxs-lookup"><span data-stu-id="9bb2d-128">**Billing profile name and status** &ndash; The unique name of the billing profile, and whether the billing profile is active or disabled for purchasing.</span></span>
- <span data-ttu-id="9bb2d-129">**Configurações de fatura** &ndash; Conversor de Moedas com base no país da conta de cobrança, informações sobre a frequência e a data da fatura, a opção de receber faturas como anexos de email e um campo opcional de número de PO</span><span class="sxs-lookup"><span data-stu-id="9bb2d-129">**Invoice settings** &ndash; Currency based on the country of the billing account, information about invoice frequency and date, the option to receive invoices as email attachments, and an optional PO number field</span></span>
- <span data-ttu-id="9bb2d-130">**Métodos de pagamento** &ndash; Mostra o método de pagamento principal e de backup, se for o caso, para o perfil</span><span class="sxs-lookup"><span data-stu-id="9bb2d-130">**Payment methods** &ndash; Shows the primary and backup payment method, if any, for the profile</span></span>
- <span data-ttu-id="9bb2d-131">**Conta de cobrança** &ndash; Nome da conta de cobrança à que o perfil está relacionado.</span><span class="sxs-lookup"><span data-stu-id="9bb2d-131">**Billing account** &ndash; Name of the billing account the profile is related to.</span></span> <span data-ttu-id="9bb2d-132">Para obter mais informações sobre contas de cobrança, consulte [Understand billing accounts](../manage-billing-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="9bb2d-132">For more information about billing accounts, see [Understand billing accounts](../manage-billing-accounts.md).</span></span>
- <span data-ttu-id="9bb2d-133">**Informações de contato** &ndash; Endereço de cobrança, nome de contato e endereço de email</span><span class="sxs-lookup"><span data-stu-id="9bb2d-133">**Contact information** &ndash; Billing address and contact name and email address</span></span>
- <span data-ttu-id="9bb2d-134">**Funções de perfil de cobrança** &ndash; Uma lista de pessoas que são atribuídas a uma das funções de perfil de cobrança para fazer coisas para esse perfil.</span><span class="sxs-lookup"><span data-stu-id="9bb2d-134">**Billing profile roles** &ndash; A list of people who are assigned one of the billing profile roles to do things for that profile.</span></span> <span data-ttu-id="9bb2d-135">Por exemplo, pagar contas, adicionar um número de PO ou substituir o método de pagamento usado para fazer compras.</span><span class="sxs-lookup"><span data-stu-id="9bb2d-135">For example, pay bills, add a PO number, or replace the payment method that is used to make purchases.</span></span>

> [!NOTE]
>
> <span data-ttu-id="9bb2d-136">Você só pode atribuir funções de perfil de cobrança aos usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9bb2d-136">You can only assign billing profile roles to users in your organization.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="9bb2d-137">Precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="9bb2d-137">Need help?</span></span> <span data-ttu-id="9bb2d-138">Contatar o suporte</span><span class="sxs-lookup"><span data-stu-id="9bb2d-138">Contact support</span></span>

<span data-ttu-id="9bb2d-139">Se você tiver dúvidas ou precisar de ajuda com suas cobranças do Azure, crie uma solicitação de suporte <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">com o suporte do Azure.</a></span><span class="sxs-lookup"><span data-stu-id="9bb2d-139">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="9bb2d-140">Se você tiver dúvidas ou precisar de ajuda com seu perfil de cobrança no Microsoft 365 de administração, [contate o suporte](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="9bb2d-140">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support](../../business-video/get-help-support.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="9bb2d-141">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="9bb2d-141">Related content</span></span>

<span data-ttu-id="9bb2d-142">[Como pagar sua assinatura com um perfil de cobrança](pay-for-subscription-billing-profile.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="9bb2d-142">[How to pay for your subscription with a billing profile](pay-for-subscription-billing-profile.md) (article)</span></span>\
<span data-ttu-id="9bb2d-143">[Compreender contas de cobrança](../manage-billing-accounts.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="9bb2d-143">[Understand billing accounts](../manage-billing-accounts.md) (article)</span></span>\
<span data-ttu-id="9bb2d-144">[Gerenciar métodos de pagamento](manage-payment-methods.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="9bb2d-144">[Manage payment methods](manage-payment-methods.md) (article)</span></span>
