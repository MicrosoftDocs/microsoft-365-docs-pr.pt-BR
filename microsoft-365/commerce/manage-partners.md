---
title: Gerenciar relacionamentos de parceiros
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
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
- PPM_jmueller
ms.reviewer: tugu
search.appverid:
- MET150
description: Saiba como trabalhar com provedores de soluções certificados pela Microsoft (parceiros) para comprar e gerenciar produtos e serviços para sua organização ou escola.
ms.date: 04/13/2021
ms.openlocfilehash: e225fa0c525d484e8c5a3887b82277a1da5861b0
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107563"
---
# <a name="manage-partner-relationships"></a><span data-ttu-id="82b57-103">Gerenciar relacionamentos de parceiros</span><span class="sxs-lookup"><span data-stu-id="82b57-103">Manage partner relationships</span></span>

<span data-ttu-id="82b57-104">Você pode trabalhar com provedores de soluções certificados pela Microsoft (parceiros) para comprar e gerenciar produtos e serviços para sua organização ou escola.</span><span class="sxs-lookup"><span data-stu-id="82b57-104">You can work with Microsoft-certified solution providers (partners) to purchase and manage products and services for your organization or school.</span></span> <span data-ttu-id="82b57-105">Há algumas etapas envolvidas na configuração das coisas.</span><span class="sxs-lookup"><span data-stu-id="82b57-105">There are a few steps involved in getting things set up.</span></span>

1. <span data-ttu-id="82b57-106">Os administradores encontram e contatem um parceiro usando o formulário em <a href="https://www.microsoft.com/solution-providers/home" target="_blank">https://www.microsoft.com/solution-providers/home</a> .</span><span class="sxs-lookup"><span data-stu-id="82b57-106">Admins find and contact a partner using the form at <a href="https://www.microsoft.com/solution-providers/home" target="_blank">https://www.microsoft.com/solution-providers/home</a>.</span></span>
2. <span data-ttu-id="82b57-107">Os parceiros enviam uma solicitação de email aos clientes para estabelecer uma relação de parceiro.</span><span class="sxs-lookup"><span data-stu-id="82b57-107">Partners send an email request to customers to establish a partner relationship.</span></span>
3. <span data-ttu-id="82b57-108">Os clientes aceitam o convite Microsoft 365 centro de administração e começam a trabalhar com o parceiro.</span><span class="sxs-lookup"><span data-stu-id="82b57-108">Customers accept the invitation in Microsoft 365 admin center and start working with the partner.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="82b57-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="82b57-109">Before you begin</span></span>

<span data-ttu-id="82b57-110">Você deve ser um administrador Global ou Cobrança para fazer essas etapas.</span><span class="sxs-lookup"><span data-stu-id="82b57-110">You must be either a Global or Billing admin to do these steps.</span></span> <span data-ttu-id="82b57-111">Para obter mais informações, confira o artigo [Sobre funções de administrador](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="82b57-111">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-can-a-partner-do-for-my-organization-or-school"></a><span data-ttu-id="82b57-112">O que um parceiro pode fazer para minha organização ou escola?</span><span class="sxs-lookup"><span data-stu-id="82b57-112">What can a partner do for my organization or school?</span></span>

<span data-ttu-id="82b57-113">Há várias maneiras de um parceiro trabalhar com você.</span><span class="sxs-lookup"><span data-stu-id="82b57-113">There are several ways that a partner can work with you.</span></span> <span data-ttu-id="82b57-114">Com base nas suas necessidades comerciais afirmadas, eles escolhem um desses tipos quando enviam sua solicitação para trabalhar com você.</span><span class="sxs-lookup"><span data-stu-id="82b57-114">Based on your stated business needs, they choose one of these types when they send their request to work with you.</span></span>

| <span data-ttu-id="82b57-115">Tipo de parceiro</span><span class="sxs-lookup"><span data-stu-id="82b57-115">Partner type</span></span> | <span data-ttu-id="82b57-116">Descrição</span><span class="sxs-lookup"><span data-stu-id="82b57-116">Description</span></span> |
| ------ | ------------------- |
| <span data-ttu-id="82b57-117">Revendedor</span><span class="sxs-lookup"><span data-stu-id="82b57-117">Reseller</span></span> | <span data-ttu-id="82b57-118">Parceiros que vendem produtos Microsoft para sua organização ou escola.</span><span class="sxs-lookup"><span data-stu-id="82b57-118">Partners that sell Microsoft products to your organization or school.</span></span> |
| <span data-ttu-id="82b57-119">Administrador delegado</span><span class="sxs-lookup"><span data-stu-id="82b57-119">Delegated administrator</span></span> | <span data-ttu-id="82b57-120">Parceiros que gerenciam produtos e serviços para sua organização ou escola.</span><span class="sxs-lookup"><span data-stu-id="82b57-120">Partners that manage products and services for your organization or school.</span></span> <span data-ttu-id="82b57-121">No Azure Active Directory (AD), o parceiro é um Administrador Global para seu locatário.</span><span class="sxs-lookup"><span data-stu-id="82b57-121">In Azure Active Directory (AD), the partner is a Global Administrator for your tenant.</span></span> <span data-ttu-id="82b57-122">Essa função permite que eles gerenciem serviços como criar contas de usuário, atribuir e gerenciar licenças e redefinições de senha.</span><span class="sxs-lookup"><span data-stu-id="82b57-122">This role lets them manage services like creating user accounts, assigning and managing licenses, and password resets.</span></span> |
| <span data-ttu-id="82b57-123">Revendedor & administrador delegado</span><span class="sxs-lookup"><span data-stu-id="82b57-123">Reseller & delegated administrator</span></span> | <span data-ttu-id="82b57-124">Parceiros que vendem e gerenciam produtos e serviços da Microsoft para sua organização ou escola.</span><span class="sxs-lookup"><span data-stu-id="82b57-124">Partners that sell and manage Microsoft products and services to your organization or school.</span></span> |
| <span data-ttu-id="82b57-125">Parceiro</span><span class="sxs-lookup"><span data-stu-id="82b57-125">Partner</span></span> | <span data-ttu-id="82b57-126">Você dá uma conta de usuário ao seu parceiro em seu locatário e eles trabalham com outras serviços Microsoft em seu nome.</span><span class="sxs-lookup"><span data-stu-id="82b57-126">You give your partner a user account in your tenant, and they work with other Microsoft services on your behalf.</span></span> |
| <span data-ttu-id="82b57-127">Advisor</span><span class="sxs-lookup"><span data-stu-id="82b57-127">Advisor</span></span> | <span data-ttu-id="82b57-128">Os parceiros podem redefinir senhas e lidar com incidentes de suporte para você.</span><span class="sxs-lookup"><span data-stu-id="82b57-128">Partners can reset passwords and handle support incidents for you.</span></span> |
| <span data-ttu-id="82b57-129">Parceiro MPSA (Contrato de Serviços & Serviços da Microsoft)</span><span class="sxs-lookup"><span data-stu-id="82b57-129">Microsoft Products & Services Agreement (MPSA) partner</span></span> | <span data-ttu-id="82b57-130">Se você tiver trabalhado com vários parceiros por meio do programa MPSA, poderá permitir que eles vejam compras feitas uns pelos outros.</span><span class="sxs-lookup"><span data-stu-id="82b57-130">If you've worked with multiple partners through the MPSA program, you can allow them to see purchases made by each other.</span></span> |
| <span data-ttu-id="82b57-131">Parceiro lob (linha de negócios)</span><span class="sxs-lookup"><span data-stu-id="82b57-131">Line-of-business (LOB) partner</span></span> | <span data-ttu-id="82b57-132">Os parceiros podem desenvolver, enviar e gerenciar aplicativos LOB específicos para sua organização ou escola.</span><span class="sxs-lookup"><span data-stu-id="82b57-132">Partners can develop, submit, and manage LOB apps specific for your organization or school.</span></span> |

## <a name="find-a-partner"></a><span data-ttu-id="82b57-133">Encontrar um parceiro</span><span class="sxs-lookup"><span data-stu-id="82b57-133">Find a partner</span></span>

1. <span data-ttu-id="82b57-134">Acesse <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a>.</span><span class="sxs-lookup"><span data-stu-id="82b57-134">Go to <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a>.</span></span>
2. <span data-ttu-id="82b57-135">Insira seu local, escolha o tamanho da sua organização, adicione palavras-chave para o tipo de serviços necessários e selecione **Ir**.</span><span class="sxs-lookup"><span data-stu-id="82b57-135">Enter your location, choose your organization size, add keywords for the type of services you need, then select **Go**.</span></span>
3. <span data-ttu-id="82b57-136">Escolha um ou mais parceiros e selecione **Contatar provedores selecionados.**</span><span class="sxs-lookup"><span data-stu-id="82b57-136">Choose one or more partners, then select **Contact selected providers**.</span></span>
4. <span data-ttu-id="82b57-137">Preencha o formulário para descrever suas necessidades de negócios e selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="82b57-137">Complete the form to describe your business needs, then select **Send**.</span></span>

<span data-ttu-id="82b57-138">O parceiro contata você e oferece a você a chance de saber mais sobre eles.</span><span class="sxs-lookup"><span data-stu-id="82b57-138">The partner contacts you and gives you a chance to learn more about them.</span></span> <span data-ttu-id="82b57-139">Se você decidir trabalhar com eles, eles enviarão um convite por email para estabelecer uma relação de parceiro.</span><span class="sxs-lookup"><span data-stu-id="82b57-139">If you decide to work with them, they send you an email invitation to establish a partner relationship.</span></span>

## <a name="review-and-accept-a-partner-relationship-and-microsoft-customer-agreement"></a><span data-ttu-id="82b57-140">Revisar e aceitar um relacionamento de parceiros e o Contrato de Cliente da Microsoft</span><span class="sxs-lookup"><span data-stu-id="82b57-140">Review and accept a partner relationship and Microsoft Customer Agreement</span></span>

<span data-ttu-id="82b57-141">Depois de encontrar um parceiro e decidir trabalhar com eles, eles enviam um convite por email.</span><span class="sxs-lookup"><span data-stu-id="82b57-141">After you find a partner and decide to work with them, they send you an email invitation.</span></span>

1. <span data-ttu-id="82b57-142">No email, selecione o link para ir para o Microsoft 365 de administração.</span><span class="sxs-lookup"><span data-stu-id="82b57-142">In the email, select the link to go to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="82b57-143">Na página **Aceitar contrato & autorizar** o parceiro, selecione o link para o Contrato de **Cliente da Microsoft** e leia o documento.</span><span class="sxs-lookup"><span data-stu-id="82b57-143">On the **Accept agreement & authorize partner** page, select the link for the **Microsoft Customer Agreement**, and read the document.</span></span>
3. <span data-ttu-id="82b57-144">Marque a caixa para confirmar que você leu o contrato.</span><span class="sxs-lookup"><span data-stu-id="82b57-144">Check the box to acknowledge that you read the agreement.</span></span>
4. <span data-ttu-id="82b57-145">Selecione **Aceitar & Autorizar**.</span><span class="sxs-lookup"><span data-stu-id="82b57-145">Select **Accept & Authorize**.</span></span>
5. <span data-ttu-id="82b57-146">A lista de parceiros com os que você está trabalhando é exibida.</span><span class="sxs-lookup"><span data-stu-id="82b57-146">The list of partners that you’re working with is displayed.</span></span> <span data-ttu-id="82b57-147">Selecione qualquer parceiro para ver detalhes.</span><span class="sxs-lookup"><span data-stu-id="82b57-147">Select any partner to see details.</span></span>

## <a name="review-and-accept-a-microsoft-customer-agreement"></a><span data-ttu-id="82b57-148">Revisar e aceitar um Contrato de Cliente da Microsoft</span><span class="sxs-lookup"><span data-stu-id="82b57-148">Review and accept a Microsoft Customer Agreement</span></span>

<span data-ttu-id="82b57-149">Se você já tiver um parceiro, mas ainda não tiver assinado um Contrato de Cliente da Microsoft, deverá aceitar o contrato antes que eles possam fazer compras ou gerenciar suas assinaturas em seu nome.</span><span class="sxs-lookup"><span data-stu-id="82b57-149">If you already have a partner but haven’t yet signed a Microsoft Customer Agreement, you must accept the agreement before they can make purchases or manage your subscriptions on your behalf.</span></span>

1. <span data-ttu-id="82b57-150">Se você receber um email de seu parceiro, selecione o link para ir para o centro de administração Microsoft 365 ou vá para a página <a href="https://go.microsoft.com/fwlink/?linkid=2116573" target="_blank">Aceitar contrato.</a></span><span class="sxs-lookup"><span data-stu-id="82b57-150">If you receive an email from your partner, select the link to go to the Microsoft 365 admin center, or go to the <a href="https://go.microsoft.com/fwlink/?linkid=2116573" target="_blank">Accept agreement</a> page.</span></span>
2. <span data-ttu-id="82b57-151">Selecione o link para o **Contrato de Cliente da Microsoft** e leia o documento.</span><span class="sxs-lookup"><span data-stu-id="82b57-151">Select the link for the **Microsoft Customer Agreement** and read the document.</span></span>
3. <span data-ttu-id="82b57-152">Marque a caixa para confirmar que você leu o contrato.</span><span class="sxs-lookup"><span data-stu-id="82b57-152">Check the box to acknowledge that you read the agreement.</span></span>
4. <span data-ttu-id="82b57-153">Selecione **Aceitar**.</span><span class="sxs-lookup"><span data-stu-id="82b57-153">Select **Accept**.</span></span>
5. <span data-ttu-id="82b57-154">A lista de parceiros com os que você está trabalhando é exibida.</span><span class="sxs-lookup"><span data-stu-id="82b57-154">The list of partners that you’re working with is displayed.</span></span> <span data-ttu-id="82b57-155">Selecione qualquer parceiro para ver detalhes.</span><span class="sxs-lookup"><span data-stu-id="82b57-155">Select any partner to see details.</span></span>

## <a name="remove-partner-admin-roles"></a><span data-ttu-id="82b57-156">Remover funções de administrador de parceiro</span><span class="sxs-lookup"><span data-stu-id="82b57-156">Remove partner admin roles</span></span>

<span data-ttu-id="82b57-157">Dependendo da solicitação feita pelo parceiro, ao aceitar o convite, você concorda em dar a eles funções de administrador Global e Helpdesk.</span><span class="sxs-lookup"><span data-stu-id="82b57-157">Depending on the request made by the partner, when you accept the invitation, you agree to give them Global and Helpdesk admin roles.</span></span> <span data-ttu-id="82b57-158">Quando você dá essas funções de administrador a um parceiro, automaticamente concede a eles privilégios de administrador delegados no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="82b57-158">When you give these admin roles to a partner, you automatically grant them delegated admin privileges in Azure AD.</span></span> <span data-ttu-id="82b57-159">Para saber mais, confira [Privilégios de administrador delegados no Azure AD](/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad).</span><span class="sxs-lookup"><span data-stu-id="82b57-159">To learn more, see [Delegated admin privileges in Azure AD](/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad).</span></span>

<span data-ttu-id="82b57-160">Se você não quiser dar as funções de administrador ao parceiro, cancele o convite em vez de aceitá-lo.</span><span class="sxs-lookup"><span data-stu-id="82b57-160">If you don't want to give the admin roles to the partner, cancel the invitation instead of accepting it.</span></span>

<span data-ttu-id="82b57-161">Você pode remover funções de administrador de um parceiro a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="82b57-161">You can remove admin roles from a partner at any time.</span></span> <span data-ttu-id="82b57-162">Remover as funções de administrador não remove a relação de parceiro.</span><span class="sxs-lookup"><span data-stu-id="82b57-162">Removing the admin roles doesn’t remove the partner relationship.</span></span> <span data-ttu-id="82b57-163">Eles ainda podem trabalhar com você em uma capacidade diferente, como um Revendedor.</span><span class="sxs-lookup"><span data-stu-id="82b57-163">They can still work with you in a different capacity, such as a Reseller.</span></span> <span data-ttu-id="82b57-164">Se você decidir que não deseja mais trabalhar com um parceiro, entre em contato com seu parceiro para encerrar o relacionamento.</span><span class="sxs-lookup"><span data-stu-id="82b57-164">If you decide that you don’t want to work with a partner anymore, contact your partner to end the relationship.</span></span>

1. <span data-ttu-id="82b57-165">No centro de administração, vá para a página relações **Configurações**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">parceiros.</a></span><span class="sxs-lookup"><span data-stu-id="82b57-165">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partner relationships</a> page.</span></span>
2. <span data-ttu-id="82b57-166">Na página **Relações de parceiros,** selecione a linha que contém o nome do parceiro que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="82b57-166">On the **Partner relationships** page, select the row that contains the name of the partner that you want to remove.</span></span>
3. <span data-ttu-id="82b57-167">Selecione a linha que contém o nome do parceiro.</span><span class="sxs-lookup"><span data-stu-id="82b57-167">Select the row that contains the name of the partner.</span></span>
4. <span data-ttu-id="82b57-168">Na página do parceiro, selecione **Remover funções**.</span><span class="sxs-lookup"><span data-stu-id="82b57-168">On the partner page, select **Remove roles**.</span></span>
5. <span data-ttu-id="82b57-169">Na caixa **de diálogo Remover funções?** , selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="82b57-169">In the **Remove roles?** dialog box, select **Yes**.</span></span>
