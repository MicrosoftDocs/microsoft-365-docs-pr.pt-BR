---
title: Registros DNS para Office 365 GCC High
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Resumo: registros DNS para o Office 365 GCC High'
hideEdit: true
ms.openlocfilehash: 9edcda4616d50d05331db0e2d6c4d89967b02fdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687122"
---
# <a name="dns-records-for-office-365-gcc-high"></a><span data-ttu-id="7bb21-103">Registros DNS para Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="7bb21-103">DNS records for Office 365 GCC High</span></span>

<span data-ttu-id="7bb21-104">*Este artigo se aplica ao Office 365 GCC High e ao Microsoft 365 GCC High*</span><span class="sxs-lookup"><span data-stu-id="7bb21-104">*This article applies to Office 365 GCC High and Microsoft 365 GCC High*</span></span>

<span data-ttu-id="7bb21-105">Como parte da integração com o Office 365 GCC High, você precisará adicionar seus domínios SMTP e SIP ao seu locatário de serviços online.</span><span class="sxs-lookup"><span data-stu-id="7bb21-105">As part of onboarding to Office 365 GCC High, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="7bb21-106">Você fará isso usando o cmdlet New-MsolDomain no PowerShell do Azure AD ou usar o [portal do Azure governamental](https://portal.azure.us) para iniciar o processo de adicionar o domínio e provar a propriedade.</span><span class="sxs-lookup"><span data-stu-id="7bb21-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="7bb21-107">Depois que você tiver seus domínios adicionados ao seu locatário e validado, use as orientações a seguir para adicionar os registros DNS apropriados para os serviços abaixo.</span><span class="sxs-lookup"><span data-stu-id="7bb21-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="7bb21-108">Talvez seja necessário modificar a tabela abaixo para se adequar às necessidades da sua organização em relação ao (s) registro (s) MX de entrada e a qualquer registro de descoberta automática do Exchange existente.</span><span class="sxs-lookup"><span data-stu-id="7bb21-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="7bb21-109">É altamente recomendável coordenar esses registros DNS com sua equipe de mensagens para evitar qualquer interrupção ou entrega incorreta de emails.</span><span class="sxs-lookup"><span data-stu-id="7bb21-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="7bb21-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7bb21-110">Exchange Online</span></span>

| <span data-ttu-id="7bb21-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="7bb21-111">Type</span></span> | <span data-ttu-id="7bb21-112">Prioridade</span><span class="sxs-lookup"><span data-stu-id="7bb21-112">Priority</span></span> | <span data-ttu-id="7bb21-113">Nome do host</span><span class="sxs-lookup"><span data-stu-id="7bb21-113">Host name</span></span> | <span data-ttu-id="7bb21-114">Aponta para o endereço ou o valor</span><span class="sxs-lookup"><span data-stu-id="7bb21-114">Points to address or value</span></span> | <span data-ttu-id="7bb21-115">TTL</span><span class="sxs-lookup"><span data-stu-id="7bb21-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="7bb21-116">MX</span><span class="sxs-lookup"><span data-stu-id="7bb21-116">MX</span></span> | <span data-ttu-id="7bb21-117">,0</span><span class="sxs-lookup"><span data-stu-id="7bb21-117">0</span></span> | @ | <span data-ttu-id="7bb21-118">*Tenant*. mail.Protection.office365.us (veja a seguir os detalhes adicionais)</span><span class="sxs-lookup"><span data-stu-id="7bb21-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="7bb21-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="7bb21-119">1 Hour</span></span> |
| <span data-ttu-id="7bb21-120">TXT</span><span class="sxs-lookup"><span data-stu-id="7bb21-120">TXT</span></span> | - | @ | <span data-ttu-id="7bb21-121">v = spf1 inclui include. Protection. office365. us-all</span><span class="sxs-lookup"><span data-stu-id="7bb21-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="7bb21-122">1 hora</span><span class="sxs-lookup"><span data-stu-id="7bb21-122">1 Hour</span></span> |
| <span data-ttu-id="7bb21-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="7bb21-123">CNAME</span></span> | - | <span data-ttu-id="7bb21-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="7bb21-124">autodiscover</span></span> | <span data-ttu-id="7bb21-125">autodiscover.office365.us</span><span class="sxs-lookup"><span data-stu-id="7bb21-125">autodiscover.office365.us</span></span> | <span data-ttu-id="7bb21-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="7bb21-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="7bb21-127">Registro de descoberta automática do Exchange</span><span class="sxs-lookup"><span data-stu-id="7bb21-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="7bb21-128">Se você tiver o Exchange Server local, recomendamos que você saia do registro existente enquanto migra para o Exchange Online e atualize esse registro depois de concluir a migração.</span><span class="sxs-lookup"><span data-stu-id="7bb21-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span> 

### <a name="exchange-online-mx-record"></a><span data-ttu-id="7bb21-129">Registro MX do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7bb21-129">Exchange Online MX Record</span></span>

<span data-ttu-id="7bb21-130">O valor do registro MX para seus domínios aceitos segue um formato padrão, conforme observado acima: *Tenant*. mail.Protection.office365.us, substituindo o *locatário* pela primeira parte do nome do locatário padrão.</span><span class="sxs-lookup"><span data-stu-id="7bb21-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="7bb21-131">Por exemplo, se o nome do seu locatário for contoso.onmicrosoft.us, você usaria **contoso.mail.Protection.office365.us** como o valor para o seu registro MX.</span><span class="sxs-lookup"><span data-stu-id="7bb21-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="7bb21-132">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7bb21-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="7bb21-133">Registros CNAME</span><span class="sxs-lookup"><span data-stu-id="7bb21-133">CNAME records</span></span>

| <span data-ttu-id="7bb21-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="7bb21-134">Type</span></span> | <span data-ttu-id="7bb21-135">Nome do host</span><span class="sxs-lookup"><span data-stu-id="7bb21-135">Host name</span></span> | <span data-ttu-id="7bb21-136">Aponta para o endereço ou o valor</span><span class="sxs-lookup"><span data-stu-id="7bb21-136">Points to address or value</span></span> | <span data-ttu-id="7bb21-137">TTL</span><span class="sxs-lookup"><span data-stu-id="7bb21-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="7bb21-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="7bb21-138">CNAME</span></span> | <span data-ttu-id="7bb21-139">sip</span><span class="sxs-lookup"><span data-stu-id="7bb21-139">sip</span></span> | <span data-ttu-id="7bb21-140">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="7bb21-140">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="7bb21-141">1 hora</span><span class="sxs-lookup"><span data-stu-id="7bb21-141">1 Hour</span></span> |
| <span data-ttu-id="7bb21-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="7bb21-142">CNAME</span></span> | <span data-ttu-id="7bb21-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7bb21-143">lyncdiscover</span></span> | <span data-ttu-id="7bb21-144">webdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="7bb21-144">webdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="7bb21-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="7bb21-145">1 Hour</span></span> |

### <a name="srv-records"></a><span data-ttu-id="7bb21-146">Registros SRV</span><span class="sxs-lookup"><span data-stu-id="7bb21-146">SRV records</span></span>

| <span data-ttu-id="7bb21-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="7bb21-147">Type</span></span> | <span data-ttu-id="7bb21-148">Serviço</span><span class="sxs-lookup"><span data-stu-id="7bb21-148">Service</span></span> | <span data-ttu-id="7bb21-149">Protocolo</span><span class="sxs-lookup"><span data-stu-id="7bb21-149">Protocol</span></span> | <span data-ttu-id="7bb21-150">Porta</span><span class="sxs-lookup"><span data-stu-id="7bb21-150">Port</span></span> | <span data-ttu-id="7bb21-151">Peso</span><span class="sxs-lookup"><span data-stu-id="7bb21-151">Weight</span></span> | <span data-ttu-id="7bb21-152">Priority</span><span class="sxs-lookup"><span data-stu-id="7bb21-152">Priority</span></span> | <span data-ttu-id="7bb21-153">Nome</span><span class="sxs-lookup"><span data-stu-id="7bb21-153">Name</span></span> | <span data-ttu-id="7bb21-154">Target</span><span class="sxs-lookup"><span data-stu-id="7bb21-154">Target</span></span> | <span data-ttu-id="7bb21-155">TTL</span><span class="sxs-lookup"><span data-stu-id="7bb21-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="7bb21-156">SRV</span><span class="sxs-lookup"><span data-stu-id="7bb21-156">SRV</span></span> | <span data-ttu-id="7bb21-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="7bb21-157">\_sip</span></span> | <span data-ttu-id="7bb21-158">\_TLS</span><span class="sxs-lookup"><span data-stu-id="7bb21-158">\_tls</span></span> | <span data-ttu-id="7bb21-159">443</span><span class="sxs-lookup"><span data-stu-id="7bb21-159">443</span></span> | <span data-ttu-id="7bb21-160">1</span><span class="sxs-lookup"><span data-stu-id="7bb21-160">1</span></span> | <span data-ttu-id="7bb21-161">100</span><span class="sxs-lookup"><span data-stu-id="7bb21-161">100</span></span> | @ | <span data-ttu-id="7bb21-162">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="7bb21-162">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="7bb21-163">1 hora</span><span class="sxs-lookup"><span data-stu-id="7bb21-163">1 Hour</span></span> |
| <span data-ttu-id="7bb21-164">SRV</span><span class="sxs-lookup"><span data-stu-id="7bb21-164">SRV</span></span> | <span data-ttu-id="7bb21-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="7bb21-165">\_sipfederationtls</span></span> | <span data-ttu-id="7bb21-166">\_TCP</span><span class="sxs-lookup"><span data-stu-id="7bb21-166">\_tcp</span></span> | <span data-ttu-id="7bb21-167">5061</span><span class="sxs-lookup"><span data-stu-id="7bb21-167">5061</span></span> | <span data-ttu-id="7bb21-168">1</span><span class="sxs-lookup"><span data-stu-id="7bb21-168">1</span></span> | <span data-ttu-id="7bb21-169">100</span><span class="sxs-lookup"><span data-stu-id="7bb21-169">100</span></span> | @ | <span data-ttu-id="7bb21-170">sipfed.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="7bb21-170">sipfed.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="7bb21-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="7bb21-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="7bb21-172">Registros DNS adicionais</span><span class="sxs-lookup"><span data-stu-id="7bb21-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7bb21-173">Se você tiver um registro CNAME *msoID* existente na sua zona DNS, você deve **remover** o registro do DNS neste momento.</span><span class="sxs-lookup"><span data-stu-id="7bb21-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="7bb21-174">O registro msoID é incompatível com aplicativos corporativos da Microsoft 365 *(anteriormente chamado Office 365 ProPlus)* e impedirá a ativação do sucesso.</span><span class="sxs-lookup"><span data-stu-id="7bb21-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
