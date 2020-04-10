---
title: Configurar seu domínio (instruções específicas do host)
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
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: ae950c9e-e8d9-4108-b0cb-449156998580
description: Saiba como gerenciar seus próprios registros DNS ou permitir que o Office 365 gerencie seus registros DNS para você.
ms.custom: okr_smb
ms.openlocfilehash: 7a5bcf6bb39497a37cbec4e2cd9b7efad0fc6724
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210351"
---
# <a name="set-up-your-domain-host-specific-instructions"></a><span data-ttu-id="e91ee-103">Configurar seu domínio (instruções específicas do host)</span><span class="sxs-lookup"><span data-stu-id="e91ee-103">Set up your domain (host-specific instructions)</span></span>

<span data-ttu-id="e91ee-104">Para começar a usar um domínio personalizado (contoso.com) com o Office 365, você precisa verificar seu domínio e configurar os registros DNS do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="e91ee-104">To start using a custom domain (contoso.com) with Office 365, you need to verify your domain and configure your domain's DNS records.</span></span> 
  
<span data-ttu-id="e91ee-105">Você pode adicionar e gerenciar registros DNS usando as ferramentas administrativas no seu host de domínio ou fornecer o Office 365 controle de seus registros de domínio e os configurarei para você.</span><span class="sxs-lookup"><span data-stu-id="e91ee-105">You can add and manage DNS records using the administrative tools at your domain host, or give Office 365 control of your domain records and we'll set them up for you.</span></span>
  
<span data-ttu-id="e91ee-106">Selecione o seu host de domínio abaixo para obter as etapas exatas.</span><span class="sxs-lookup"><span data-stu-id="e91ee-106">Select your domain host below for the exact steps.</span></span> <span data-ttu-id="e91ee-107">Se você não tiver certeza de quem é seu host, confira [localizar seu registrador de domínio](find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="e91ee-107">If you're not sure who your host is, see [Find your domain registrar](find-your-domain-registrar.md).</span></span>
  

## <a name="let-office-365-manage-your-dns-records"></a><span data-ttu-id="e91ee-108">Permitir que o Office 365 gerencie seus registros DNS</span><span class="sxs-lookup"><span data-stu-id="e91ee-108">Let Office 365 manage your DNS records</span></span>

||
|---|---|
|[<span data-ttu-id="e91ee-109">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="e91ee-109">1&1 IONOS</span></span>](../dns/change-nameservers-at-1-1-internet.md) |
|[<span data-ttu-id="e91ee-110">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="e91ee-110">Amazon Web Services (AWS)</span></span>](../dns/change-nameservers-at-aws.md) |
 [<span data-ttu-id="e91ee-111">Bluehost</span><span class="sxs-lookup"><span data-stu-id="e91ee-111">Bluehost</span></span>](../dns/change-nameservers-at-bluehost.md)|
|[<span data-ttu-id="e91ee-112">Domínios do Google</span><span class="sxs-lookup"><span data-stu-id="e91ee-112">Google   Domains</span></span>](../dns/change-nameservers-at-google-domains.md) |
|[<span data-ttu-id="e91ee-113">Hostgator</span><span class="sxs-lookup"><span data-stu-id="e91ee-113">Hostgator   </span></span>](../dns/change-nameservers-at-hostgator.md)  |  
|[<span data-ttu-id="e91ee-114">MyDomain</span><span class="sxs-lookup"><span data-stu-id="e91ee-114">MyDomain</span></span>](../dns/change-nameservers-at-mydomain.md) | 
|[<span data-ttu-id="e91ee-115">Namecheap</span><span class="sxs-lookup"><span data-stu-id="e91ee-115">Namecheap</span></span>](../dns/change-nameservers-at-namecheap.md)|
|[<span data-ttu-id="e91ee-116">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="e91ee-116">Network Solutions</span></span>](../dns/change-nameservers-at-network-solutions.md) |  

<span data-ttu-id="e91ee-117">Ou saiba como [alterar os nameservers para configurar o Office 365 com qualquer registrador de domínio](change-nameservers-at-any-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="e91ee-117">Or, learn how to [change nameservers to set up Office 365 with any domain registrar](change-nameservers-at-any-domain-registrar.md).</span></span>

## <a name="manage-your-own-dns-records"></a><span data-ttu-id="e91ee-118">Gerenciar seus próprios registros DNS</span><span class="sxs-lookup"><span data-stu-id="e91ee-118">Manage your own DNS records</span></span>

|                           |                          |
|---------------------------|--------------------------|
| [<span data-ttu-id="e91ee-119">1&1 IONOS</span><span class="sxs-lookup"><span data-stu-id="e91ee-119">1&1 IONOS</span></span>](../dns/create-dns-records-at-1-1-internet.md) | [<span data-ttu-id="e91ee-120">Foco</span><span class="sxs-lookup"><span data-stu-id="e91ee-120">Hover</span></span>](../dns/create-dns-records-at-hover.md) |
| [<span data-ttu-id="e91ee-121">123-reg.co.uk</span><span class="sxs-lookup"><span data-stu-id="e91ee-121">123-reg.co.uk</span></span>](../dns/create-dns-records-at-123-reg-co-uk.md) | [<span data-ttu-id="e91ee-122">Gerenciado pelo Google (eNom)</span><span class="sxs-lookup"><span data-stu-id="e91ee-122">Managed   by Google (eNom)</span></span>](../dns/create-dns-records-for-domain-managed-by-google-enom.md)|
| [<span data-ttu-id="e91ee-123">Amazon Web Services (AWS)</span><span class="sxs-lookup"><span data-stu-id="e91ee-123">Amazon Web Services (AWS)</span></span>](../dns/create-dns-records-at-aws.md) | [<span data-ttu-id="e91ee-124">MyDomain</span><span class="sxs-lookup"><span data-stu-id="e91ee-124">MyDomain</span></span>](../dns/create-dns-records-at-mydomain.md) |
| [<span data-ttu-id="e91ee-125">Zonas de DNS do Azure</span><span class="sxs-lookup"><span data-stu-id="e91ee-125">Azure DNS zones</span></span>](../dns/create-dns-records-for-azure-dns-zones.md) | [<span data-ttu-id="e91ee-126">name.com</span><span class="sxs-lookup"><span data-stu-id="e91ee-126">name.com</span></span>](../dns/create-dns-records-at-name-com.md) |
| [<span data-ttu-id="e91ee-127">Bluehost</span><span class="sxs-lookup"><span data-stu-id="e91ee-127">Bluehost</span></span>](../dns/create-dns-records-at-bluehost.md) | [<span data-ttu-id="e91ee-128">Namecheap</span><span class="sxs-lookup"><span data-stu-id="e91ee-128">Namecheap</span></span>](../dns/create-dns-records-at-namecheap.md)|
| [<span data-ttu-id="e91ee-129">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="e91ee-129">Cloudflare</span></span>](../dns/create-dns-records-at-cloudflare.md)| [<span data-ttu-id="e91ee-130">Names.co.uk</span><span class="sxs-lookup"><span data-stu-id="e91ee-130">Names.co.uk</span></span>](../dns/create-dns-records-at-names-co-uk.md) |
|  [<span data-ttu-id="e91ee-131">Crazy Domains</span><span class="sxs-lookup"><span data-stu-id="e91ee-131">Crazy Domains</span></span>](../dns/create-dns-records-at-crazy-domains.md)| [<span data-ttu-id="e91ee-132">Netregistry</span><span class="sxs-lookup"><span data-stu-id="e91ee-132">Netregistry</span></span>](../dns/create-dns-records-at-netregistry.md) |
|[<span data-ttu-id="e91ee-133">DNSMadeEasy</span><span class="sxs-lookup"><span data-stu-id="e91ee-133">DNSMadeEasy</span></span>](../dns/create-dns-records-at-dnsmadeeasy.md) | [<span data-ttu-id="e91ee-134">Soluções de rede</span><span class="sxs-lookup"><span data-stu-id="e91ee-134">Network   Solutions</span></span>](../dns/create-dns-records-at-network-solutions.md) |
|[<span data-ttu-id="e91ee-135">Dreamhost</span><span class="sxs-lookup"><span data-stu-id="e91ee-135">Dreamhost</span></span>](../dns/create-dns-records-at-dreamhost.md)  | [<span data-ttu-id="e91ee-136">OVH</span><span class="sxs-lookup"><span data-stu-id="e91ee-136">OVH</span></span>](../dns/create-dns-records-at-ovh.md) |
|  [<span data-ttu-id="e91ee-137">Dyn.com</span><span class="sxs-lookup"><span data-stu-id="e91ee-137">Dyn.com</span></span>](../dns/create-dns-records-at-dyn-com.md) | [<span data-ttu-id="e91ee-138">Register.com</span><span class="sxs-lookup"><span data-stu-id="e91ee-138">Register.com</span></span>](../dns/create-dns-records-at-register-com.md) |
| [<span data-ttu-id="e91ee-139">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="e91ee-139">eNomCentral</span></span>](../dns/create-dns-records-at-enomcentral.md)| [<span data-ttu-id="e91ee-140">Register365 para o Office 365</span><span class="sxs-lookup"><span data-stu-id="e91ee-140">Register365 for Office 365</span></span>](../dns/create-dns-records-at-register365.md)  |
| [<span data-ttu-id="e91ee-141">Freenom</span><span class="sxs-lookup"><span data-stu-id="e91ee-141">Freenom</span></span>](../dns/create-dns-records-at-freenom.md) | [<span data-ttu-id="e91ee-142">web.com</span><span class="sxs-lookup"><span data-stu-id="e91ee-142"> web.com </span></span>](../dns/create-dns-records-at-web-com.md)|
|[<span data-ttu-id="e91ee-143">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="e91ee-143">GoDaddy</span></span>](../dns/create-dns-records-at-godaddy.md)|[<span data-ttu-id="e91ee-144">DNS baseado no Windows</span><span class="sxs-lookup"><span data-stu-id="e91ee-144"> Windows-based DNS</span></span>](../dns/create-dns-records-using-windows-based-dns.md)   |
| [<span data-ttu-id="e91ee-145">Google Domains</span><span class="sxs-lookup"><span data-stu-id="e91ee-145">Google Domains</span></span>](../dns/create-dns-records-at-google-domains.md) |[<span data-ttu-id="e91ee-146">Wix</span><span class="sxs-lookup"><span data-stu-id="e91ee-146">Wix</span></span>](../dns/create-dns-records-at-wix.md) |
|[<span data-ttu-id="e91ee-147">Hostgator</span><span class="sxs-lookup"><span data-stu-id="e91ee-147">Hostgator</span></span>](../dns/create-dns-records-at-hostgator.md)  | [<span data-ttu-id="e91ee-148">Toolbar   Pequenas empresas</span><span class="sxs-lookup"><span data-stu-id="e91ee-148">Yahoo!   Small Business</span></span>](../dns/create-dns-records-at-yahoo-small-business.md)  |

[<span data-ttu-id="e91ee-149">Preciso de instruções gerais, porque o host de meu domínio não está na lista.</span><span class="sxs-lookup"><span data-stu-id="e91ee-149">I need general instructions, because my domain host isn't on this list. </span></span>](create-dns-records-at-any-dns-hosting-provider.md)
   
