---
title: Compreender os perfis de cobrança
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
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
- Commerce
search.appverid:
- MET150
description: Saiba como os perfis de cobrança suportam faturas.
ms.openlocfilehash: 708096b624caa9c23a40df4842ccfce856db048d
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667769"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="3df73-103">Compreender os perfis de cobrança</span><span class="sxs-lookup"><span data-stu-id="3df73-103">Understand billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3df73-104">O centro de administração está mudando.</span><span class="sxs-lookup"><span data-stu-id="3df73-104">The admin center is changing.</span></span> <span data-ttu-id="3df73-105">Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="3df73-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="3df73-106">Para clientes comerciais que compram produtos e serviços da Microsoft, os perfis de cobrança permitem personalizar quais itens estão incluídos em sua fatura e como você paga suas faturas.</span><span class="sxs-lookup"><span data-stu-id="3df73-106">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="3df73-107">Os perfis de cobrança incluem as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="3df73-107">Billing profiles include the following information:</span></span>

- <span data-ttu-id="3df73-108">**Conta de cobrança** &ndash; Nome da conta de cobrança à que o perfil está relacionado</span><span class="sxs-lookup"><span data-stu-id="3df73-108">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="3df73-109">**Formas de pagamento** &ndash; Cartões de crédito ou débito, contas bancárias, cheques ou transferência eletrônica</span><span class="sxs-lookup"><span data-stu-id="3df73-109">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="3df73-110">**Informações de contato** &ndash; Endereço de cobrança e um nome de contato</span><span class="sxs-lookup"><span data-stu-id="3df73-110">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="3df73-111">**Configurações de fatura** &ndash; Moeda com base no país/região da conta de cobrança, um número de OL opcional e a opção para receber faturas como anexos de email</span><span class="sxs-lookup"><span data-stu-id="3df73-111">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="3df73-112">**Permissões** &ndash; Permissões que permitem alterar o perfil de cobrança, pagar faturas ou usar a forma de pagamento no perfil de cobrança para fazer compras</span><span class="sxs-lookup"><span data-stu-id="3df73-112">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="3df73-113">Use perfis de cobrança para controlar suas compras e personalizar sua fatura.</span><span class="sxs-lookup"><span data-stu-id="3df73-113">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="3df73-114">Uma fatura mensal é gerada para os produtos comprados com o perfil de cobrança.</span><span class="sxs-lookup"><span data-stu-id="3df73-114">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="3df73-115">Você pode personalizar a fatura, como atualizar o número do pedido de compra e a preferência da fatura de email.</span><span class="sxs-lookup"><span data-stu-id="3df73-115">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="3df73-116">Um perfil de cobrança é criado automaticamente para sua conta de cobrança durante a primeira compra.</span><span class="sxs-lookup"><span data-stu-id="3df73-116">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="3df73-117">Você pode criar perfis de cobrança na página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Perfis de</a> cobrança para configurar mais faturas.</span><span class="sxs-lookup"><span data-stu-id="3df73-117">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="3df73-118">Por exemplo, você pode usar perfis de cobrança diferentes ao fazer compras para cada departamento em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3df73-118">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="3df73-119">Na próxima data de cobrança, você receberá uma fatura para cada perfil de cobrança.</span><span class="sxs-lookup"><span data-stu-id="3df73-119">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="3df73-120">Funções de perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="3df73-120">Billing profile roles</span></span>

<span data-ttu-id="3df73-121">As funções nos perfis de cobrança têm permissões para controlar compras e exibir e gerenciar faturas.</span><span class="sxs-lookup"><span data-stu-id="3df73-121">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="3df73-122">Atribua essas funções a usuários que rastreiem, organizem e pagarão faturas, como membros da equipe de compras em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3df73-122">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="3df73-123">Função</span><span class="sxs-lookup"><span data-stu-id="3df73-123">Role</span></span>                          | <span data-ttu-id="3df73-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="3df73-124">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="3df73-125">Proprietário do perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="3df73-125">Billing profile owner</span></span>         | <span data-ttu-id="3df73-126">Gerenciar tudo para um perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="3df73-126">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="3df73-127">Colaborador de perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="3df73-127">Billing profile contributor</span></span>   | <span data-ttu-id="3df73-128">Gerenciar tudo, exceto permissões em um perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="3df73-128">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="3df73-129">Leitor de perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="3df73-129">Billing profile reader</span></span>        | <span data-ttu-id="3df73-130">Exibição somente leitura de tudo em um perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="3df73-130">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="3df73-131">Gerenciador de notas fiscais</span><span class="sxs-lookup"><span data-stu-id="3df73-131">Invoice manager</span></span>               | <span data-ttu-id="3df73-132">Exibir e pagar faturas e ter uma exibição somente leitura de tudo em um perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="3df73-132">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="3df73-133">Exibir perfis de cobrança</span><span class="sxs-lookup"><span data-stu-id="3df73-133">View billing profiles</span></span>

1. <span data-ttu-id="3df73-134">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Cobranças e pagamentos</a>.</span><span class="sxs-lookup"><span data-stu-id="3df73-134">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="3df73-135">Escolha **Perfis de** cobrança e escolha um perfil de cobrança na lista.</span><span class="sxs-lookup"><span data-stu-id="3df73-135">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="3df73-136">Na guia **Visão geral,** você pode editar detalhes do perfil de cobrança e ativar ou desativar o envio de uma fatura por email.</span><span class="sxs-lookup"><span data-stu-id="3df73-136">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="3df73-137">Na guia **Permissões,** você pode atribuir funções aos usuários para pagar faturas.</span><span class="sxs-lookup"><span data-stu-id="3df73-137">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="3df73-138">Na guia saldo de crédito do **Azure,** os clientes do Azure podem ver o histórico de saldos de transações dos créditos do Azure usados por esse perfil de cobrança.</span><span class="sxs-lookup"><span data-stu-id="3df73-138">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="3df73-139">Na guia créditos do **Azure,** os clientes do Azure podem ver uma lista de créditos do Azure associados a esse perfil de cobrança e suas datas de vencimento.</span><span class="sxs-lookup"><span data-stu-id="3df73-139">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3df73-140">Se você não tiver créditos do Azure, não verá o saldo de crédito do **Azure** ou as guias de créditos do **Azure.**</span><span class="sxs-lookup"><span data-stu-id="3df73-140">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="3df73-141">Precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="3df73-141">Need help?</span></span> <span data-ttu-id="3df73-142">Fale com o suporte.</span><span class="sxs-lookup"><span data-stu-id="3df73-142">Contact support.</span></span>

<span data-ttu-id="3df73-143">Se você tiver dúvidas ou precisar de ajuda com seus encargos do Azure, crie uma solicitação de suporte com o suporte <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">do Azure.</a></span><span class="sxs-lookup"><span data-stu-id="3df73-143">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="3df73-144">Se você tiver dúvidas ou precisar de ajuda com seu perfil de cobrança no Centro de administração do Microsoft 365, entre em contato com [o suporte para produtos comerciais.](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)</span><span class="sxs-lookup"><span data-stu-id="3df73-144">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
