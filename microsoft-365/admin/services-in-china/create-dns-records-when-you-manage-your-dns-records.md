---
title: Criar registros DNS para Office 365 ao gerenciar seus registros DNS
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: 'Aprenda a criar registros DNS para Office 365 operados pela 21Vianet quando gerenciar seus registros DNS. '
monikerRange: o365-21vianet
ms.openlocfilehash: 1eaa2bcc7263eaa12e53131246abd591006b0536
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914349"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="0d1de-103">Criar registros DNS para Office 365 ao gerenciar seus registros DNS</span><span class="sxs-lookup"><span data-stu-id="0d1de-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="0d1de-104">Para obter instruções detalhadas sobre como criar registros DNS para Office 365 operados pela 21Vianet, incluindo o registro MX necessário para roteamento de email, consulte Create DNS records at any [DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="0d1de-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="0d1de-105">Mais opções e algumas coisas a serem cientes:</span><span class="sxs-lookup"><span data-stu-id="0d1de-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="0d1de-106">Se você não conhece o provedor de host DNS ou o registrador de domínios para seu domínio, confira [Localizar seu registrador de domínio ou provedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="0d1de-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="0d1de-107">Para saber mais sobre o que os registros DNS fazem, consulte [noções básicas de DNS.](../get-help-with-domains/dns-basics.md)</span><span class="sxs-lookup"><span data-stu-id="0d1de-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="0d1de-108">Alguns provedores de hospedagem DNS não permitem que você crie todos os tipos de registro necessários, o que causa limitações de serviço quando seu provedor de hospedagem não dá suporte a [SRV, CNAME, TXT](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)ou redirecionamento .</span><span class="sxs-lookup"><span data-stu-id="0d1de-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="0d1de-109">Se o provedor não der suporte a registros SRV, TXT [](../get-help-with-domains/buy-a-domain-name.md) ou CNAME, recomendamos que você transfira seu domínio para um provedor que suporte todos os tipos [de registro necessários.](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)</span><span class="sxs-lookup"><span data-stu-id="0d1de-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](../get-help-with-domains/buy-a-domain-name.md) to a [provider that supports all required record types](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="0d1de-110">Para ver quais registros DNS são necessários e encontrar os valores a usar para cada registro, incluindo o registro MX para email, consulte Reunir as informações necessárias para criar Office 365 [registros DNS](../get-help-with-domains/information-for-dns-records.md).</span><span class="sxs-lookup"><span data-stu-id="0d1de-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](../get-help-with-domains/information-for-dns-records.md).</span></span> <span data-ttu-id="0d1de-111">Para saber mais sobre o que os registros DNS fazem, consulte [noções básicas de DNS.](../get-help-with-domains/dns-basics.md)</span><span class="sxs-lookup"><span data-stu-id="0d1de-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
