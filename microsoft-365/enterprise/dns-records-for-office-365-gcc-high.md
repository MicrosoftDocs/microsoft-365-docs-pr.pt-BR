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
description: 'Resumo: registros DNS para Office 365 GCC Alta'
hideEdit: true
ms.openlocfilehash: 9edcda4616d50d05331db0e2d6c4d89967b02fdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687122"
---
# <a name="dns-records-for-office-365-gcc-high"></a><span data-ttu-id="2043e-103">Registros DNS para Office 365 GCC High</span><span class="sxs-lookup"><span data-stu-id="2043e-103">DNS records for Office 365 GCC High</span></span>

<span data-ttu-id="2043e-104">*Este artigo se aplica a Office 365 GCC Alta e Microsoft 365 GCC Alta*</span><span class="sxs-lookup"><span data-stu-id="2043e-104">*This article applies to Office 365 GCC High and Microsoft 365 GCC High*</span></span>

<span data-ttu-id="2043e-105">Como parte da integração Office 365 GCC Alta, você precisará adicionar seus domínios SMTP e SIP ao seu locatário de Serviços Online.</span><span class="sxs-lookup"><span data-stu-id="2043e-105">As part of onboarding to Office 365 GCC High, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="2043e-106">Você fará isso usando o cmdlet New-MsolDomain no Azure AD PowerShell ou usará o Portal do Governo do [Azure](https://portal.azure.us) para iniciar o processo de adição do domínio e da prova de propriedade.</span><span class="sxs-lookup"><span data-stu-id="2043e-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="2043e-107">Depois de ter seus domínios adicionados ao locatário e validados, use as seguintes diretrizes para adicionar os registros DNS apropriados para os serviços abaixo.</span><span class="sxs-lookup"><span data-stu-id="2043e-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="2043e-108">Talvez seja necessário modificar Exchange tabela abaixo para se ajustar às necessidades da sua organização em relação aos registros MX de entrada e quaisquer registros de Descoberta Automática existentes que você tenha.</span><span class="sxs-lookup"><span data-stu-id="2043e-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="2043e-109">É recomendável coordenar esses registros DNS com sua equipe de mensagens para evitar paralisações ou entregas incorretamente de emails.</span><span class="sxs-lookup"><span data-stu-id="2043e-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="2043e-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2043e-110">Exchange Online</span></span>

| <span data-ttu-id="2043e-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="2043e-111">Type</span></span> | <span data-ttu-id="2043e-112">Prioridade</span><span class="sxs-lookup"><span data-stu-id="2043e-112">Priority</span></span> | <span data-ttu-id="2043e-113">Nome do host</span><span class="sxs-lookup"><span data-stu-id="2043e-113">Host name</span></span> | <span data-ttu-id="2043e-114">Aponta para o endereço ou para o valor</span><span class="sxs-lookup"><span data-stu-id="2043e-114">Points to address or value</span></span> | <span data-ttu-id="2043e-115">TTL</span><span class="sxs-lookup"><span data-stu-id="2043e-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="2043e-116">MX</span><span class="sxs-lookup"><span data-stu-id="2043e-116">MX</span></span> | <span data-ttu-id="2043e-117">0</span><span class="sxs-lookup"><span data-stu-id="2043e-117">0</span></span> | @ | <span data-ttu-id="2043e-118">*tenant*.mail.protection.office365.us (consulte abaixo para obter detalhes adicionais)</span><span class="sxs-lookup"><span data-stu-id="2043e-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="2043e-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2043e-119">1 Hour</span></span> |
| <span data-ttu-id="2043e-120">TXT</span><span class="sxs-lookup"><span data-stu-id="2043e-120">TXT</span></span> | - | @ | <span data-ttu-id="2043e-121">v=spf1 include:spf.protection.office365.us -all</span><span class="sxs-lookup"><span data-stu-id="2043e-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="2043e-122">1 hora</span><span class="sxs-lookup"><span data-stu-id="2043e-122">1 Hour</span></span> |
| <span data-ttu-id="2043e-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="2043e-123">CNAME</span></span> | - | <span data-ttu-id="2043e-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="2043e-124">autodiscover</span></span> | <span data-ttu-id="2043e-125">autodiscover.office365.us</span><span class="sxs-lookup"><span data-stu-id="2043e-125">autodiscover.office365.us</span></span> | <span data-ttu-id="2043e-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2043e-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="2043e-127">Exchange Registro de Descoberta Automática</span><span class="sxs-lookup"><span data-stu-id="2043e-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="2043e-128">Se você tiver Exchange Server local, recomendamos deixar seu registro existente no local enquanto migra para Exchange Online e atualizar esse registro depois de concluir a migração.</span><span class="sxs-lookup"><span data-stu-id="2043e-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span> 

### <a name="exchange-online-mx-record"></a><span data-ttu-id="2043e-129">Exchange Online Registro MX</span><span class="sxs-lookup"><span data-stu-id="2043e-129">Exchange Online MX Record</span></span>

<span data-ttu-id="2043e-130">O valor do registro MX para seus domínios aceitos segue um formato padrão  conforme mencionado acima: *tenant*.mail.protection.office365.us, substituindo locatário pela primeira parte do nome de locatário padrão.</span><span class="sxs-lookup"><span data-stu-id="2043e-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="2043e-131">Por exemplo, se seu nome de locatário contoso.onmicrosoft.us, você usaria contoso.mail.protection.office365.us **como** o valor para seu registro MX.</span><span class="sxs-lookup"><span data-stu-id="2043e-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="2043e-132">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2043e-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="2043e-133">Registros CNAME</span><span class="sxs-lookup"><span data-stu-id="2043e-133">CNAME records</span></span>

| <span data-ttu-id="2043e-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="2043e-134">Type</span></span> | <span data-ttu-id="2043e-135">Nome do host</span><span class="sxs-lookup"><span data-stu-id="2043e-135">Host name</span></span> | <span data-ttu-id="2043e-136">Aponta para o endereço ou para o valor</span><span class="sxs-lookup"><span data-stu-id="2043e-136">Points to address or value</span></span> | <span data-ttu-id="2043e-137">TTL</span><span class="sxs-lookup"><span data-stu-id="2043e-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="2043e-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="2043e-138">CNAME</span></span> | <span data-ttu-id="2043e-139">sip</span><span class="sxs-lookup"><span data-stu-id="2043e-139">sip</span></span> | <span data-ttu-id="2043e-140">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="2043e-140">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="2043e-141">1 hora</span><span class="sxs-lookup"><span data-stu-id="2043e-141">1 Hour</span></span> |
| <span data-ttu-id="2043e-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="2043e-142">CNAME</span></span> | <span data-ttu-id="2043e-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="2043e-143">lyncdiscover</span></span> | <span data-ttu-id="2043e-144">webdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="2043e-144">webdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="2043e-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2043e-145">1 Hour</span></span> |

### <a name="srv-records"></a><span data-ttu-id="2043e-146">Registros SRV</span><span class="sxs-lookup"><span data-stu-id="2043e-146">SRV records</span></span>

| <span data-ttu-id="2043e-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="2043e-147">Type</span></span> | <span data-ttu-id="2043e-148">Serviço</span><span class="sxs-lookup"><span data-stu-id="2043e-148">Service</span></span> | <span data-ttu-id="2043e-149">Protocolo</span><span class="sxs-lookup"><span data-stu-id="2043e-149">Protocol</span></span> | <span data-ttu-id="2043e-150">Porta</span><span class="sxs-lookup"><span data-stu-id="2043e-150">Port</span></span> | <span data-ttu-id="2043e-151">Peso</span><span class="sxs-lookup"><span data-stu-id="2043e-151">Weight</span></span> | <span data-ttu-id="2043e-152">Prioridade</span><span class="sxs-lookup"><span data-stu-id="2043e-152">Priority</span></span> | <span data-ttu-id="2043e-153">Nome</span><span class="sxs-lookup"><span data-stu-id="2043e-153">Name</span></span> | <span data-ttu-id="2043e-154">Target</span><span class="sxs-lookup"><span data-stu-id="2043e-154">Target</span></span> | <span data-ttu-id="2043e-155">TTL</span><span class="sxs-lookup"><span data-stu-id="2043e-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="2043e-156">SRV</span><span class="sxs-lookup"><span data-stu-id="2043e-156">SRV</span></span> | <span data-ttu-id="2043e-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="2043e-157">\_sip</span></span> | <span data-ttu-id="2043e-158">\_tls</span><span class="sxs-lookup"><span data-stu-id="2043e-158">\_tls</span></span> | <span data-ttu-id="2043e-159">443</span><span class="sxs-lookup"><span data-stu-id="2043e-159">443</span></span> | <span data-ttu-id="2043e-160">1</span><span class="sxs-lookup"><span data-stu-id="2043e-160">1</span></span> | <span data-ttu-id="2043e-161">100</span><span class="sxs-lookup"><span data-stu-id="2043e-161">100</span></span> | @ | <span data-ttu-id="2043e-162">sipdir.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="2043e-162">sipdir.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="2043e-163">1 hora</span><span class="sxs-lookup"><span data-stu-id="2043e-163">1 Hour</span></span> |
| <span data-ttu-id="2043e-164">SRV</span><span class="sxs-lookup"><span data-stu-id="2043e-164">SRV</span></span> | <span data-ttu-id="2043e-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="2043e-165">\_sipfederationtls</span></span> | <span data-ttu-id="2043e-166">\_tcp</span><span class="sxs-lookup"><span data-stu-id="2043e-166">\_tcp</span></span> | <span data-ttu-id="2043e-167">5061</span><span class="sxs-lookup"><span data-stu-id="2043e-167">5061</span></span> | <span data-ttu-id="2043e-168">1</span><span class="sxs-lookup"><span data-stu-id="2043e-168">1</span></span> | <span data-ttu-id="2043e-169">100</span><span class="sxs-lookup"><span data-stu-id="2043e-169">100</span></span> | @ | <span data-ttu-id="2043e-170">sipfed.online.gov.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="2043e-170">sipfed.online.gov.skypeforbusiness.us</span></span> | <span data-ttu-id="2043e-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="2043e-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="2043e-172">Registros DNS adicionais</span><span class="sxs-lookup"><span data-stu-id="2043e-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2043e-173">Se você tiver um registro CNAME *msoid* existente em sua zona DNS, deverá **remover** o registro do DNS neste momento.</span><span class="sxs-lookup"><span data-stu-id="2043e-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="2043e-174">O registro msoid é incompatível com Microsoft 365 Enterprise Apps *(anteriormente Office 365 ProPlus)* e impedirá que a ativação seja bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="2043e-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
