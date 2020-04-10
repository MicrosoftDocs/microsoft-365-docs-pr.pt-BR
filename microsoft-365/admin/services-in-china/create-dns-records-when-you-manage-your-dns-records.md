---
title: Criar registros DNS para o Office 365 ao gerenciar seus registros DNS
f1.keywords:
- CSH
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
- Adm_NonTOC
search.appverid:
- MET150
- GEA150
ms.assetid: 0669bf14-414d-4f51-8231-6b710ce7980b
ROBOTS: NOINDEX
description: 'Saiba como criar registros DNS para o Office 365 operado pela 21Vianet ao gerenciar seus registros DNS. '
monikerRange: o365-21vianet
ms.openlocfilehash: b81ab3442e7087c4b7ee9bb3b5e5c2160d724986
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43211992"
---
# <a name="create-dns-records-for-office-365-when-you-manage-your-dns-records"></a><span data-ttu-id="7a0a5-103">Criar registros DNS para o Office 365 ao gerenciar seus registros DNS</span><span class="sxs-lookup"><span data-stu-id="7a0a5-103">Create DNS records for Office 365 when you manage your DNS records</span></span>

<span data-ttu-id="7a0a5-104">Para obter instruções detalhadas sobre como criar registros DNS para o Office 365 operado pela 21Vianet, incluindo o registro MX necessário para roteamento de emails, consulte [Create DNS Records to a host de Hospedagem de DNS para o Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="7a0a5-104">For detailed instructions about how to create DNS records for Office 365 operated by 21Vianet, including the MX record required for mail routing, see [Create DNS records at any DNS hosting provider for Office 365](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span> 
  
  
<span data-ttu-id="7a0a5-105">Mais opções e algumas coisas que devem ser consideradas:</span><span class="sxs-lookup"><span data-stu-id="7a0a5-105">More options and some things to be aware of:</span></span>
      
-  <span data-ttu-id="7a0a5-106">Se você não conhece o provedor de host DNS ou o registrador de domínios para seu domínio, confira [Localizar seu registrador de domínio ou provedor de host DNS](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="7a0a5-106">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span> <span data-ttu-id="7a0a5-107">Para obter descrições sobre o que os registros DNS fazem, consulte [noções básicas sobre DNS](../get-help-with-domains/dns-basics.md).</span><span class="sxs-lookup"><span data-stu-id="7a0a5-107">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    
-  <span data-ttu-id="7a0a5-108">Alguns provedores de hospedagem DNS não permitem que você crie todos os tipos de registros necessários, o que causa [limitações de serviço quando o provedor de hospedagem não é compatível com SRV, CNAME, txt ou redirecionamento](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span><span class="sxs-lookup"><span data-stu-id="7a0a5-108">Some DNS hosting providers don't let you create all the required record types, which causes [Service limitations when your hosting provider does not support SRV, CNAME, TXT, or redirection](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> <span data-ttu-id="7a0a5-109">Se o provedor não oferecer suporte a registros SRV, TXT ou CNAME, recomendamos que você [transfira seu domínio](https://support.office.com/article/a6689b24-eeca-41f1-afe6-19917936b73c.aspx) para um [provedor que dê suporte a todos os tipos de registros necessários](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span><span class="sxs-lookup"><span data-stu-id="7a0a5-109">If your provider doesn't support SRV, TXT, or CNAME records, we recommend that you [transfer your domain](https://support.office.com/article/a6689b24-eeca-41f1-afe6-19917936b73c.aspx) to a [provider that supports all required record types](https://support.office.com/article/dfbb03e3-08c1-4c4e-b2f0-891665b29b77).</span></span> 
    
- <span data-ttu-id="7a0a5-110">Para ver quais registros DNS são necessários e localizar os valores a serem usados para cada registro, incluindo o registro MX para email, confira [coletar as informações necessárias para criar registros DNS do Office 365](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e).</span><span class="sxs-lookup"><span data-stu-id="7a0a5-110">To see which DNS records are required and find the values to use for each record, including the MX record for email, see [Gather the information you need to create Office 365 DNS records](https://support.office.com/article/ffcc06d2-b50d-4072-95bb-f59013770e0e).</span></span> <span data-ttu-id="7a0a5-111">Para obter descrições sobre o que os registros DNS fazem, consulte [noções básicas sobre DNS](../get-help-with-domains/dns-basics.md).</span><span class="sxs-lookup"><span data-stu-id="7a0a5-111">For descriptions of what the DNS records do, see [DNS basics](../get-help-with-domains/dns-basics.md).</span></span>
    

