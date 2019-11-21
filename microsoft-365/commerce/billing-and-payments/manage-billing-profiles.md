---
title: Gerenciar perfis de cobrança
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Saiba como os perfis de cobrança dão suporte a faturas.
keywords: Perfil de cobrança, faturas, encargos, encargos gerenciados
ms.openlocfilehash: 4b46709cf877ea8689f72b66d5ac357272e4737d
ms.sourcegitcommit: 7713e777731025c165e9e936198609503ade5665
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2019
ms.locfileid: "38753540"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="9720e-104">Gerenciar perfis de cobrança</span><span class="sxs-lookup"><span data-stu-id="9720e-104">Manage billing profiles</span></span>
<span data-ttu-id="9720e-105">Para clientes comerciais que compram produtos e serviços da Microsoft, os perfis de cobrança permitem que você personalize quais itens estão incluídos na fatura e como você paga suas faturas.</span><span class="sxs-lookup"><span data-stu-id="9720e-105">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="9720e-106">Os perfis de cobrança incluem as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="9720e-106">Billing profiles include the following information:</span></span>

- <span data-ttu-id="9720e-107">Nome da **conta** &ndash; de cobrança da conta de cobrança à qual o perfil está relacionado</span><span class="sxs-lookup"><span data-stu-id="9720e-107">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="9720e-108">**Métodos** &ndash; de pagamento cartões de crédito ou débito, contas bancárias, cheque ou transferência de fio</span><span class="sxs-lookup"><span data-stu-id="9720e-108">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="9720e-109">Endereço de cobrança de **informações** &ndash; de contato e um nome de contato</span><span class="sxs-lookup"><span data-stu-id="9720e-109">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="9720e-110">Moeda **das configurações** &ndash; de fatura com base no país da conta de cobrança, um número de OC opcional e a opção de receber faturas como anexos de email</span><span class="sxs-lookup"><span data-stu-id="9720e-110">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="9720e-111">Permissões permissões que permitem alterar o perfil de cobrança, pagar contas ou usar a forma de pagamento no perfil de cobrança para fazer compras \*\*\*\* &ndash;</span><span class="sxs-lookup"><span data-stu-id="9720e-111">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="9720e-112">Use perfis de cobrança para controlar suas compras e personalizar sua fatura.</span><span class="sxs-lookup"><span data-stu-id="9720e-112">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="9720e-113">Uma fatura mensal é gerada para os produtos comprados com o perfil de cobrança.</span><span class="sxs-lookup"><span data-stu-id="9720e-113">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="9720e-114">Você pode personalizar a fatura, como atualizar o número da ordem de compra e a preferência de fatura de email.</span><span class="sxs-lookup"><span data-stu-id="9720e-114">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="9720e-115">Um perfil de cobrança é criado automaticamente para a sua conta de cobrança durante a primeira compra.</span><span class="sxs-lookup"><span data-stu-id="9720e-115">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="9720e-116">Você pode criar perfis de cobrança na página <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">perfis de cobrança</a> para configurar mais faturas.</span><span class="sxs-lookup"><span data-stu-id="9720e-116">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="9720e-117">Por exemplo, você pode usar diferentes perfis de cobrança quando fizer compras para cada departamento da sua organização.</span><span class="sxs-lookup"><span data-stu-id="9720e-117">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="9720e-118">Na próxima data de cobrança, você receberá uma fatura para cada perfil de cobrança.</span><span class="sxs-lookup"><span data-stu-id="9720e-118">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="9720e-119">Funções de perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="9720e-119">Billing profile roles</span></span>

<span data-ttu-id="9720e-120">As funções em perfis de cobrança têm permissões para controlar compras e exibir e gerenciar faturas.</span><span class="sxs-lookup"><span data-stu-id="9720e-120">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="9720e-121">Atribua essas funções aos usuários que rastreiam, organizam e pagam faturas, como os membros da equipe de compras em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9720e-121">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="9720e-122">Função</span><span class="sxs-lookup"><span data-stu-id="9720e-122">Role</span></span>                          | <span data-ttu-id="9720e-123">Descrição</span><span class="sxs-lookup"><span data-stu-id="9720e-123">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="9720e-124">Proprietário do perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="9720e-124">Billing profile owner</span></span>         | <span data-ttu-id="9720e-125">Gerenciar tudo para um perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="9720e-125">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="9720e-126">Contribuidor de perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="9720e-126">Billing profile contributor</span></span>   | <span data-ttu-id="9720e-127">Gerenciar tudo exceto permissões em um perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="9720e-127">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="9720e-128">Leitor de perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="9720e-128">Billing profile reader</span></span>        | <span data-ttu-id="9720e-129">Modo de exibição somente leitura de tudo em um perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="9720e-129">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="9720e-130">Gerenciador de faturas</span><span class="sxs-lookup"><span data-stu-id="9720e-130">Invoice manager</span></span>               | <span data-ttu-id="9720e-131">Exibir e pagar contas, e ter um modo de exibição somente leitura de tudo em um perfil de cobrança</span><span class="sxs-lookup"><span data-stu-id="9720e-131">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="9720e-132">Exibir perfis de cobrança</span><span class="sxs-lookup"><span data-stu-id="9720e-132">View billing profiles</span></span>

1. <span data-ttu-id="9720e-133">No centro de administração, vá para a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Faturas e pagamentos</a>.</span><span class="sxs-lookup"><span data-stu-id="9720e-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="9720e-134">Escolha **perfis de cobrança**e, em seguida, escolha um perfil de cobrança na lista.</span><span class="sxs-lookup"><span data-stu-id="9720e-134">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="9720e-135">Na guia **visão geral** , você pode editar detalhes do perfil de cobrança e ativar ou desativar o envio de uma fatura por email.</span><span class="sxs-lookup"><span data-stu-id="9720e-135">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="9720e-136">Na guia **permissões** , você pode atribuir funções aos usuários para pagar faturas.</span><span class="sxs-lookup"><span data-stu-id="9720e-136">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="9720e-137">Na guia **saldo de crédito do Azure** , os clientes do Azure podem ver o histórico de equilíbrio de transações para os créditos do Azure usados por esse perfil de cobrança.</span><span class="sxs-lookup"><span data-stu-id="9720e-137">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="9720e-138">Na guia **do Azure créditos** , os clientes do Azure podem ver uma lista de créditos do Azure associados a esse perfil de cobrança e suas datas de expiração.</span><span class="sxs-lookup"><span data-stu-id="9720e-138">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9720e-139">Se você não tiver créditos do Azure, não verá as guias **saldo de crédito do Azure** ou **créditos do Azure** .</span><span class="sxs-lookup"><span data-stu-id="9720e-139">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="9720e-140">Precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="9720e-140">Need help?</span></span> <span data-ttu-id="9720e-141">Fale com o suporte.</span><span class="sxs-lookup"><span data-stu-id="9720e-141">Contact support.</span></span>

<span data-ttu-id="9720e-142">Se você tiver dúvidas ou precisar de ajuda com seus encargos do Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">crie uma solicitação de suporte com o suporte do Azure</a>.</span><span class="sxs-lookup"><span data-stu-id="9720e-142">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="9720e-143">Se você tiver dúvidas ou precisar de ajuda com seu perfil de cobrança no centro de administração do Microsoft 365, [entre em contato com o suporte para produtos de negócios](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="9720e-143">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>