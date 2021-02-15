---
title: Criar registros DNS para o Office 365 ao gerenciar seus registros DNS
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
description: 'Saiba como criar registros DNS para o Office 365 operado pela 21Vianet quando gerenciar seus registros DNS. '
monikerRange: o365-21vianet
ms.openlocfilehash: 8f252ba47fbd72f5a628a23567addcc84604fb3c
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644814"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="d06a8-103">Criar registros DNS para o Office 365 ao gerenciar seus registros DNS</span><span class="sxs-lookup"><span data-stu-id="d06a8-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="d06a8-104">Para obter instruções detalhadas sobre como criar registros DNS para o Office 365 operado pela 21Vianet, incluindo o registro MX necessário para roteamento de email, consulte Criar registros DNS em qualquer provedor de hospedagem de DNS para [o Office 365.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="d06a8-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="d06a8-105">Mais opções e algumas coisas a serem cientes:</span><span class="sxs-lookup"><span data-stu-id="d06a8-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="d06a8-106">Se você não conhece o provedor de host DNS ou o registrador de domínios para seu domínio, confira [Localizar seu registrador de domínio ou provedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="d06a8-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="d06a8-107">Para descrições do que os registros DNS fazem, consulte [noções básicas de DNS.](../get-help-with-domains/dns-basics.md)</span><span class="sxs-lookup"><span data-stu-id="d06a8-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="d06a8-108">Alguns provedores de hospedagem DNS não permitem que você crie todos os tipos de registro necessários, o que causa limitações de serviço quando seu provedor de hospedagem não dá suporte a [SRV, CNAME, TXT ou redirecionamento.](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)</span><span class="sxs-lookup"><span data-stu-id="d06a8-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="d06a8-109">Se seu provedor não der suporte a registros SRV, TXT [](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) ou CNAME, recomendamos transferir seu domínio para um provedor que suporte todos os tipos de [registros necessários.](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77)</span><span class="sxs-lookup"><span data-stu-id="d06a8-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/buy-a-domain-name) to a [provider that supports all required record types](https://support.microsoft.com/office/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="d06a8-110">Para ver quais registros DNS são necessários e encontrar os valores a usar para cada registro, incluindo o registro MX para email, confira Coletar as informações necessárias para criar registros DNS do [Office 365.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records)</span><span class="sxs-lookup"><span data-stu-id="d06a8-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/information-for-dns-records).</span></span> <span data-ttu-id="d06a8-111">Para descrições do que os registros DNS fazem, consulte [noções básicas de DNS.](../get-help-with-domains/dns-basics.md)</span><span class="sxs-lookup"><span data-stu-id="d06a8-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    

