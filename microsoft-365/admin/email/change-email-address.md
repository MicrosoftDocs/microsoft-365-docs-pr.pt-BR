---
title: Mudar seu endereço de email para usar seu domínio personalizado
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: 'Altere seu endereço de email inicial para um endereço de email amigável, como o tom@fourthcoffee.com. Para fazer isso, você precisa comprar um nome de domínio e adicioná-lo ao Office 365. '
ms.openlocfilehash: dc0ab64003b48eec50bf34e60d8a6df463b4fe89
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212028"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a><span data-ttu-id="108ad-104">Mudar seu endereço de email para usar seu domínio personalizado</span><span class="sxs-lookup"><span data-stu-id="108ad-104">Change your email address to use your custom domain</span></span>

 <span data-ttu-id="108ad-105">**Caso não encontre o conteúdo que está procurando, [verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="108ad-105">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
::: moniker range="o365-worldwide"

<span data-ttu-id="108ad-p102">Seu endereço de email inicial no Office 365 inclui .onmicrosoft.com, como pedro@fourthcoffee.onmicrosoft.com. Você pode alterá-lo para um endereço mais fácil de memorizar, como pedro@fourthcoffee.com. Você primeiro precisará do seu próprio nome de domínio, como fourthcoffee.com. Se você já possui um, excelente! Caso contrário, você pode aprender como [comprar um de um registrador de domínios](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="108ad-p102">Your initial email address in Office 365 includes .onmicrosoft.com, like tom@fourthcoffee.onmicrosoft.com. You can change it to a friendlier address like tom@fourthcoffee.com. You'll need your own domain name, like fourthcoffee.com first. If you already have one, great! If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="108ad-111">Seu endereço de email inicial no Office 365 Alemanha inclui. onmicrosoft.de, como tom@fourthcoffee.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="108ad-111">Your initial email address in Office 365 Germany includes .onmicrosoft.de, like tom@fourthcoffee.onmicrosoft.de.</span></span> <span data-ttu-id="108ad-112">Você pode alterá-lo para um endereço mais amigável, como o tom@fourthcoffee.de.</span><span class="sxs-lookup"><span data-stu-id="108ad-112">You can change it to a friendlier address like tom@fourthcoffee.de.</span></span> <span data-ttu-id="108ad-113">Você precisará de seu próprio nome de domínio, como fourthcoffee.de primeiro.</span><span class="sxs-lookup"><span data-stu-id="108ad-113">You'll need your own domain name, like fourthcoffee.de first.</span></span> <span data-ttu-id="108ad-114">Se você já possui um, excelente!</span><span class="sxs-lookup"><span data-stu-id="108ad-114">If you already have one, great!</span></span> <span data-ttu-id="108ad-115">Caso contrário, você pode aprender como [comprar um de um registrador de domínios](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="108ad-115">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="108ad-116">Seu endereço de email inicial no Office 365 operado pela 21Vianet inclui o partner.onmschina.cn, como o tom@fourthcoffee.partner.onmschina.cn.</span><span class="sxs-lookup"><span data-stu-id="108ad-116">Your initial email address in Office 365 operated by 21Vianet includes partner.onmschina.cn, like tom@fourthcoffee.partner.onmschina.cn.</span></span> <span data-ttu-id="108ad-117">Você pode alterá-lo para um endereço mais amigável, como o tom@fourthcoffee.cn.</span><span class="sxs-lookup"><span data-stu-id="108ad-117">You can change it to a friendlier address like tom@fourthcoffee.cn.</span></span> <span data-ttu-id="108ad-118">Você precisará de seu próprio nome de domínio, como fourthcoffee.cn primeiro.</span><span class="sxs-lookup"><span data-stu-id="108ad-118">You'll need your own domain name, like fourthcoffee.cn first.</span></span> <span data-ttu-id="108ad-119">Se você já possui um, excelente!</span><span class="sxs-lookup"><span data-stu-id="108ad-119">If you already have one, great!</span></span> <span data-ttu-id="108ad-120">Caso contrário, você pode aprender como [comprar um de um registrador de domínios](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="108ad-120">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

<span data-ttu-id="108ad-p105">Quando você altera o email do domínio para chegar ao Office 365, atualizando o registro MX do domínio durante a configuração, TODOS os emails enviados a esse domínio passarão a ser enviados ao Office 365. Verifique se você adicionou usuários e criou caixas de correio no Office 365 para todos que têm um email no seu domínio ANTES de alterar o registro MX. Não quer migrar o email de todas as pessoas no domínio para o Office 365? É possível realizar etapas para [administrar o Office 365 com somente alguns endereços de email](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).</span><span class="sxs-lookup"><span data-stu-id="108ad-p105">When you change your domain's email to come to Office 365, by updating your domain's MX record during setup, ALL email sent to that domain will start coming to Office 365. Make sure you've added users and created mailboxes in Office 365 for everyone who has email on your domain BEFORE you change the MX record. Don't want to move email for everyone on your domain to Office 365? You can take steps to [pilot Office 365 with just a few email addresses instead](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).</span></span>
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a><span data-ttu-id="108ad-125">Alterar seu endereço de email para usar seu domínio personalizado usando o centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="108ad-125">Change your email address to use your custom domain using the Microsoft 365 admin center</span></span>

<span data-ttu-id="108ad-126">Você deve ter uma conta de administrador global para executar estas etapas.</span><span class="sxs-lookup"><span data-stu-id="108ad-126">You must have a global admin account to perform these steps.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="108ad-127">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="108ad-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <span data-ttu-id="108ad-128">Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="108ad-128">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span> 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="108ad-129">Vá para o centro de administração <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>em.</span><span class="sxs-lookup"><span data-stu-id="108ad-129">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>.</span></span> 

::: moniker-end 

2. <span data-ttu-id="108ad-130">Vá para a página **Configurar** > **domínios** .</span><span class="sxs-lookup"><span data-stu-id="108ad-130">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="108ad-131">Na página **domínios** , selecione **Adicionar domínio**.</span><span class="sxs-lookup"><span data-stu-id="108ad-131">On the **Domains** page, select **Add domain**.</span></span>
    
4. <span data-ttu-id="108ad-132">Siga as etapas para confirmar que você é proprietário do domínio e alterar seu endereço de email.</span><span class="sxs-lookup"><span data-stu-id="108ad-132">Follow the steps to confirm that you own your domain and to change your email address.</span></span>
    
<span data-ttu-id="108ad-133">Você receberá instruções sobre como configurar tudo corretamente para o seu domínio no Office 365.</span><span class="sxs-lookup"><span data-stu-id="108ad-133">You'll be guided to get everything set up correctly with your domain in Office 365.</span></span>

> [!NOTE]
> <span data-ttu-id="108ad-134">Se você não estiver usando uma licença do Exchange, não será possível usar o domínio para enviar ou receber emails do locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="108ad-134">If you are not using an Exchange license, you cannot use the domain to send or receive emails from the Office 365 tenant.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="108ad-135">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="108ad-135">Related articles</span></span>

[<span data-ttu-id="108ad-136">Comprar um domínio personalizado pelo Office 365</span><span class="sxs-lookup"><span data-stu-id="108ad-136">Buy a custom domain using Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)
 
