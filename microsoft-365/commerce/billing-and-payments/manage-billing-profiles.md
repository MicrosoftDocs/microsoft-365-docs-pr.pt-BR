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
ms.openlocfilehash: 36d762e50627763b7856ed1fe6c109e8da2b4789
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332025"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="25c57-103">Compreender os perfis de cobrança</span><span class="sxs-lookup"><span data-stu-id="25c57-103">Understand billing profiles</span></span>

<span data-ttu-id="25c57-104">Para clientes comerciais que compram produtos e serviços da Microsoft, os perfis de cobrança permitem personalizar quais itens estão incluídos em sua fatura e como você paga suas faturas.</span><span class="sxs-lookup"><span data-stu-id="25c57-104">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="25c57-105">Os perfis de cobrança incluem as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="25c57-105">Billing profiles include the following information:</span></span>

- <span data-ttu-id="25c57-106">**Conta de cobrança** &ndash; Nome da conta de cobrança à que o perfil está relacionado</span><span class="sxs-lookup"><span data-stu-id="25c57-106">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="25c57-107">**Métodos de pagamento** &ndash; Cartões de crédito ou débito, contas bancárias, verificação ou transferência bancária</span><span class="sxs-lookup"><span data-stu-id="25c57-107">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="25c57-108">**Informações de contato** &ndash; Endereço de cobrança e um nome de contato</span><span class="sxs-lookup"><span data-stu-id="25c57-108">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="25c57-109">**Configurações de fatura** &ndash; Moeda com base no país da conta de cobrança, um número DE opcional e a opção de receber faturas como anexos de email</span><span class="sxs-lookup"><span data-stu-id="25c57-109">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="25c57-110">**Permissões** &ndash; Permissões que permitem alterar o perfil de cobrança, pagar contas ou usar o método de pagamento no perfil de cobrança para fazer compras</span><span class="sxs-lookup"><span data-stu-id="25c57-110">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="25c57-111">Use perfis de cobrança para controlar suas compras e personalizar sua fatura.</span><span class="sxs-lookup"><span data-stu-id="25c57-111">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="25c57-112">Uma fatura mensal é gerada para os produtos comprados com o perfil de cobrança.</span><span class="sxs-lookup"><span data-stu-id="25c57-112">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="25c57-113">Você pode personalizar a fatura, como atualizar o número do pedido de compra e a preferência da fatura de email.</span><span class="sxs-lookup"><span data-stu-id="25c57-113">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="25c57-114">Um perfil de cobrança é criado automaticamente para sua conta de cobrança durante sua primeira compra.</span><span class="sxs-lookup"><span data-stu-id="25c57-114">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="25c57-115">Você pode criar perfis de cobrança na página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Perfis de</a> Cobrança para configurar mais faturas.</span><span class="sxs-lookup"><span data-stu-id="25c57-115">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="25c57-116">Por exemplo, você pode usar perfis de cobrança diferentes ao fazer compras para cada departamento em sua organização.</span><span class="sxs-lookup"><span data-stu-id="25c57-116">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="25c57-117">Na próxima data de cobrança, você receberá uma fatura para cada perfil de cobrança.</span><span class="sxs-lookup"><span data-stu-id="25c57-117">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="25c57-118">Funções de perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="25c57-118">Billing profile roles</span></span>

<span data-ttu-id="25c57-119">Funções nos perfis de cobrança têm permissões para controlar compras e exibir e gerenciar faturas.</span><span class="sxs-lookup"><span data-stu-id="25c57-119">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="25c57-120">Atribua essas funções aos usuários que rastreiam, organizam e pagam faturas, como membros da equipe de compras em sua organização.</span><span class="sxs-lookup"><span data-stu-id="25c57-120">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="25c57-121">Função</span><span class="sxs-lookup"><span data-stu-id="25c57-121">Role</span></span>                         | <span data-ttu-id="25c57-122">Descrição</span><span class="sxs-lookup"><span data-stu-id="25c57-122">Description</span></span>                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| <span data-ttu-id="25c57-123">Proprietário do perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="25c57-123">Billing profile owner</span></span>        | <span data-ttu-id="25c57-124">Gerenciar tudo para um perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="25c57-124">Manage everything for a billing profile</span></span>                                          |
| <span data-ttu-id="25c57-125">Colaborador de perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="25c57-125">Billing profile contributor</span></span>  | <span data-ttu-id="25c57-126">Gerenciar tudo, exceto permissões em um perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="25c57-126">Manage everything except permissions in a billing profile</span></span>                        |
| <span data-ttu-id="25c57-127">Leitor de perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="25c57-127">Billing profile reader</span></span>       | <span data-ttu-id="25c57-128">Exibição somente leitura de tudo em um perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="25c57-128">Read-only view of everything in a billing profile</span></span>                                |
| <span data-ttu-id="25c57-129">Gerenciador de faturas</span><span class="sxs-lookup"><span data-stu-id="25c57-129">Invoice manager</span></span>              | <span data-ttu-id="25c57-130">Exibir e pagar contas e tem uma exibição somente leitura de tudo em um perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="25c57-130">View and pay bills, and has a read-only view of everything in a billing profile</span></span>  |

## <a name="view-billing-profiles"></a><span data-ttu-id="25c57-131">Exibir perfis de cobrança</span><span class="sxs-lookup"><span data-stu-id="25c57-131">View billing profiles</span></span>

1. <span data-ttu-id="25c57-132">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Faturas e pagamentos</a>.</span><span class="sxs-lookup"><span data-stu-id="25c57-132">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="25c57-133">Escolha **Perfis de** cobrança e escolha um perfil de cobrança na lista.</span><span class="sxs-lookup"><span data-stu-id="25c57-133">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="25c57-134">Na guia **Visão** geral, você pode editar detalhes do perfil de cobrança e ativar ou desativar o envio de uma fatura por email.</span><span class="sxs-lookup"><span data-stu-id="25c57-134">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>
    - <span data-ttu-id="25c57-135">Na guia **Permissões,** você pode atribuir funções aos usuários para pagar faturas.</span><span class="sxs-lookup"><span data-stu-id="25c57-135">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>
    - <span data-ttu-id="25c57-136">Na guia saldo de crédito do **Azure,** os clientes do Azure podem ver o histórico do saldo de transações dos créditos do Azure usados por esse perfil de cobrança.</span><span class="sxs-lookup"><span data-stu-id="25c57-136">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>
    - <span data-ttu-id="25c57-137">Na guia Créditos do **Azure,** os clientes do Azure podem ver uma lista de créditos do Azure associados a esse perfil de cobrança e suas datas de expiração.</span><span class="sxs-lookup"><span data-stu-id="25c57-137">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="25c57-138">Se você não tiver créditos do Azure, não verá o saldo de crédito do **Azure** ou as guias de créditos do **Azure.**</span><span class="sxs-lookup"><span data-stu-id="25c57-138">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="25c57-139">Precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="25c57-139">Need help?</span></span> <span data-ttu-id="25c57-140">Contatar o suporte</span><span class="sxs-lookup"><span data-stu-id="25c57-140">Contact support</span></span>

<span data-ttu-id="25c57-141">Se você tiver dúvidas ou precisar de ajuda com suas cobranças do Azure, crie uma solicitação de suporte <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">com o suporte do Azure.</a></span><span class="sxs-lookup"><span data-stu-id="25c57-141">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="25c57-142">Se você tiver dúvidas ou precisar de ajuda com seu perfil de cobrança no Centro de administração do Microsoft 365, [contate o suporte para produtos comerciais.](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="25c57-142">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](../../business-video/get-help-support.md).</span></span>
