---
title: Registros DNS para Office 365 DoD
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
description: 'Resumo: registros DNS do Office 365 DoD'
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687133"
---
# <a name="dns-records-for-office-365-dod"></a><span data-ttu-id="cafd6-103">Registros DNS para Office 365 DoD</span><span class="sxs-lookup"><span data-stu-id="cafd6-103">DNS records for Office 365 DoD</span></span>

<span data-ttu-id="cafd6-104">*Este artigo se aplica ao Office 365 DoD e ao Microsoft 365 DoD*</span><span class="sxs-lookup"><span data-stu-id="cafd6-104">*This article applies to Office 365 DoD and Microsoft 365 DoD*</span></span>

<span data-ttu-id="cafd6-105">Como parte da integração ao Office 365 DoD, você precisará adicionar seus domínios SMTP e SIP ao seu locatário de Serviços Online.</span><span class="sxs-lookup"><span data-stu-id="cafd6-105">As part of onboarding to Office 365 DoD, you will need to add your SMTP and SIP domains to your Online Services tenant.</span></span>  <span data-ttu-id="cafd6-106">Você fará isso usando o cmdlet New-MsolDomain no Azure AD PowerShell ou use o Portal do [Azure Governamental](https://portal.azure.us) para iniciar o processo de adição do domínio e a aprovação da propriedade.</span><span class="sxs-lookup"><span data-stu-id="cafd6-106">You’ll do this using the New-MsolDomain cmdlet in Azure AD PowerShell or use the [Azure Government Portal](https://portal.azure.us) to start the process of adding the domain and proving ownership.</span></span>

<span data-ttu-id="cafd6-107">Depois que você tiver seus domínios adicionados ao seu locatário e validados, use as orientações a seguir para adicionar os registros DNS apropriados para os serviços abaixo.</span><span class="sxs-lookup"><span data-stu-id="cafd6-107">Once you have your domains added to your tenant and validated, use the following guidance to add the appropriate DNS records for the services below.</span></span>  <span data-ttu-id="cafd6-108">Talvez seja necessário modificar a tabela abaixo para se ajustar às necessidades da sua organização em relação aos registros MX de entrada e quaisquer registros de Descoberta Automática do Exchange existentes que você tenha no local.</span><span class="sxs-lookup"><span data-stu-id="cafd6-108">You may need to modify the below table to fit your organization’s needs with respect to the inbound MX record(s) and any existing Exchange Autodiscover record(s) you have in place.</span></span>  <span data-ttu-id="cafd6-109">É recomendável coordenar esses registros DNS com sua equipe de mensagens para evitar paralisações ou entregas incorretamente de email.</span><span class="sxs-lookup"><span data-stu-id="cafd6-109">We strongly recommend coordinating these DNS records with your messaging team to avoid any outages or mis-delivery of email.</span></span>

## <a name="exchange-online"></a><span data-ttu-id="cafd6-110">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cafd6-110">Exchange Online</span></span>

| <span data-ttu-id="cafd6-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="cafd6-111">Type</span></span> | <span data-ttu-id="cafd6-112">Prioridade</span><span class="sxs-lookup"><span data-stu-id="cafd6-112">Priority</span></span> | <span data-ttu-id="cafd6-113">Nome do host</span><span class="sxs-lookup"><span data-stu-id="cafd6-113">Host name</span></span> | <span data-ttu-id="cafd6-114">Pontos de endereço ou valor</span><span class="sxs-lookup"><span data-stu-id="cafd6-114">Points to address or value</span></span> | <span data-ttu-id="cafd6-115">TTL</span><span class="sxs-lookup"><span data-stu-id="cafd6-115">TTL</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="cafd6-116">MX</span><span class="sxs-lookup"><span data-stu-id="cafd6-116">MX</span></span> | <span data-ttu-id="cafd6-117">0</span><span class="sxs-lookup"><span data-stu-id="cafd6-117">0</span></span> | @ | <span data-ttu-id="cafd6-118">*tenant*.mail.protection.office365.us (veja abaixo para obter detalhes adicionais)</span><span class="sxs-lookup"><span data-stu-id="cafd6-118">*tenant*.mail.protection.office365.us (see below for additional details)</span></span> | <span data-ttu-id="cafd6-119">1 Hour</span><span class="sxs-lookup"><span data-stu-id="cafd6-119">1 Hour</span></span> |
| <span data-ttu-id="cafd6-120">TXT</span><span class="sxs-lookup"><span data-stu-id="cafd6-120">TXT</span></span> | - | @ | <span data-ttu-id="cafd6-121">v=spf1 include:spf.protection.office365.us -all</span><span class="sxs-lookup"><span data-stu-id="cafd6-121">v=spf1 include:spf.protection.office365.us -all</span></span> | <span data-ttu-id="cafd6-122">1 hora</span><span class="sxs-lookup"><span data-stu-id="cafd6-122">1 Hour</span></span> |
| <span data-ttu-id="cafd6-123">CNAME</span><span class="sxs-lookup"><span data-stu-id="cafd6-123">CNAME</span></span> | - | <span data-ttu-id="cafd6-124">autodiscover</span><span class="sxs-lookup"><span data-stu-id="cafd6-124">autodiscover</span></span> | <span data-ttu-id="cafd6-125">autodiscover-dod.office365.us</span><span class="sxs-lookup"><span data-stu-id="cafd6-125">autodiscover-dod.office365.us</span></span> | <span data-ttu-id="cafd6-126">1 Hour</span><span class="sxs-lookup"><span data-stu-id="cafd6-126">1 Hour</span></span> |

### <a name="exchange-autodiscover-record"></a><span data-ttu-id="cafd6-127">Registro de Descoberta Automática do Exchange</span><span class="sxs-lookup"><span data-stu-id="cafd6-127">Exchange Autodiscover record</span></span>

<span data-ttu-id="cafd6-128">Se você tiver o Exchange Server local, recomendamos que você mantenha seu registro existente enquanto migra para o Exchange Online e atualize esse registro depois de concluir a migração.</span><span class="sxs-lookup"><span data-stu-id="cafd6-128">If you have Exchange Server on-premises, we recommend leaving your existing record in place while you migrate to Exchange Online, and update that record once you have completed your migration.</span></span>

### <a name="exchange-online-mx-record"></a><span data-ttu-id="cafd6-129">Registro MX do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cafd6-129">Exchange Online MX Record</span></span>

<span data-ttu-id="cafd6-130">O valor do registro MX para seus domínios aceitos segue um formato padrão  conforme mencionado acima: *tenant*.mail.protection.office365.us, substituindo o locatário pela primeira parte do nome de locatário padrão.</span><span class="sxs-lookup"><span data-stu-id="cafd6-130">The MX record value for your accepted domains follows a standard format as noted above: *tenant*.mail.protection.office365.us, replacing *tenant* with the first part of your default tenant name.</span></span>

<span data-ttu-id="cafd6-131">Por exemplo, se o nome do contoso.onmicrosoft.us for  contoso.onmicrosoft.us, você usaria contoso.mail.protection.office365.us como o valor do seu registro MX.</span><span class="sxs-lookup"><span data-stu-id="cafd6-131">For example, if your tenant name is contoso.onmicrosoft.us, you’d use **contoso.mail.protection.office365.us** as the value for your MX record.</span></span>

## <a name="skype-for-business-online"></a><span data-ttu-id="cafd6-132">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="cafd6-132">Skype for Business Online</span></span>

### <a name="cname-records"></a><span data-ttu-id="cafd6-133">Registros CNAME</span><span class="sxs-lookup"><span data-stu-id="cafd6-133">CNAME records</span></span>

| <span data-ttu-id="cafd6-134">Tipo</span><span class="sxs-lookup"><span data-stu-id="cafd6-134">Type</span></span> | <span data-ttu-id="cafd6-135">Nome do host</span><span class="sxs-lookup"><span data-stu-id="cafd6-135">Host name</span></span> | <span data-ttu-id="cafd6-136">Pontos de endereço ou valor</span><span class="sxs-lookup"><span data-stu-id="cafd6-136">Points to address or value</span></span> | <span data-ttu-id="cafd6-137">TTL</span><span class="sxs-lookup"><span data-stu-id="cafd6-137">TTL</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="cafd6-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="cafd6-138">CNAME</span></span> | <span data-ttu-id="cafd6-139">sip</span><span class="sxs-lookup"><span data-stu-id="cafd6-139">sip</span></span> | <span data-ttu-id="cafd6-140">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="cafd6-140">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="cafd6-141">1 hora</span><span class="sxs-lookup"><span data-stu-id="cafd6-141">1 Hour</span></span> |
| <span data-ttu-id="cafd6-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="cafd6-142">CNAME</span></span> | <span data-ttu-id="cafd6-143">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cafd6-143">lyncdiscover</span></span> | <span data-ttu-id="cafd6-144">webdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="cafd6-144">webdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="cafd6-145">1 Hour</span><span class="sxs-lookup"><span data-stu-id="cafd6-145">1 Hour</span></span> | 

### <a name="srv-records"></a><span data-ttu-id="cafd6-146">Registros SRV</span><span class="sxs-lookup"><span data-stu-id="cafd6-146">SRV records</span></span>

| <span data-ttu-id="cafd6-147">Tipo</span><span class="sxs-lookup"><span data-stu-id="cafd6-147">Type</span></span> | <span data-ttu-id="cafd6-148">Serviço</span><span class="sxs-lookup"><span data-stu-id="cafd6-148">Service</span></span> | <span data-ttu-id="cafd6-149">Protocolo</span><span class="sxs-lookup"><span data-stu-id="cafd6-149">Protocol</span></span> | <span data-ttu-id="cafd6-150">Porta</span><span class="sxs-lookup"><span data-stu-id="cafd6-150">Port</span></span> | <span data-ttu-id="cafd6-151">Peso</span><span class="sxs-lookup"><span data-stu-id="cafd6-151">Weight</span></span> | <span data-ttu-id="cafd6-152">Priority</span><span class="sxs-lookup"><span data-stu-id="cafd6-152">Priority</span></span> | <span data-ttu-id="cafd6-153">Nome</span><span class="sxs-lookup"><span data-stu-id="cafd6-153">Name</span></span> | <span data-ttu-id="cafd6-154">Target</span><span class="sxs-lookup"><span data-stu-id="cafd6-154">Target</span></span> | <span data-ttu-id="cafd6-155">TTL</span><span class="sxs-lookup"><span data-stu-id="cafd6-155">TTL</span></span> |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| <span data-ttu-id="cafd6-156">SRV</span><span class="sxs-lookup"><span data-stu-id="cafd6-156">SRV</span></span> | <span data-ttu-id="cafd6-157">\_sip</span><span class="sxs-lookup"><span data-stu-id="cafd6-157">\_sip</span></span> | <span data-ttu-id="cafd6-158">\_tls</span><span class="sxs-lookup"><span data-stu-id="cafd6-158">\_tls</span></span> | <span data-ttu-id="cafd6-159">443</span><span class="sxs-lookup"><span data-stu-id="cafd6-159">443</span></span> | <span data-ttu-id="cafd6-160">1 </span><span class="sxs-lookup"><span data-stu-id="cafd6-160">1</span></span> | <span data-ttu-id="cafd6-161">100</span><span class="sxs-lookup"><span data-stu-id="cafd6-161">100</span></span> | @ | <span data-ttu-id="cafd6-162">sipdir.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="cafd6-162">sipdir.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="cafd6-163">1 hora</span><span class="sxs-lookup"><span data-stu-id="cafd6-163">1 Hour</span></span> |
| <span data-ttu-id="cafd6-164">SRV</span><span class="sxs-lookup"><span data-stu-id="cafd6-164">SRV</span></span> | <span data-ttu-id="cafd6-165">\_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="cafd6-165">\_sipfederationtls</span></span> | <span data-ttu-id="cafd6-166">\_tcp</span><span class="sxs-lookup"><span data-stu-id="cafd6-166">\_tcp</span></span> | <span data-ttu-id="cafd6-167">5061</span><span class="sxs-lookup"><span data-stu-id="cafd6-167">5061</span></span> | <span data-ttu-id="cafd6-168">1 </span><span class="sxs-lookup"><span data-stu-id="cafd6-168">1</span></span> | <span data-ttu-id="cafd6-169">100</span><span class="sxs-lookup"><span data-stu-id="cafd6-169">100</span></span> | @ | <span data-ttu-id="cafd6-170">sipfed.online.dod.skypeforbusiness.us</span><span class="sxs-lookup"><span data-stu-id="cafd6-170">sipfed.online.dod.skypeforbusiness.us</span></span> | <span data-ttu-id="cafd6-171">1 Hour</span><span class="sxs-lookup"><span data-stu-id="cafd6-171">1 Hour</span></span> |

## <a name="additional-dns-records"></a><span data-ttu-id="cafd6-172">Registros DNS adicionais</span><span class="sxs-lookup"><span data-stu-id="cafd6-172">Additional DNS records</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cafd6-173">Se você tiver um registro CNAME *msoid* existente  na zona DNS, deverá remover o registro do DNS no momento.</span><span class="sxs-lookup"><span data-stu-id="cafd6-173">If you have an existing *msoid* CNAME record in your DNS zone, you must **remove** the record from DNS at this time.</span></span>  <span data-ttu-id="cafd6-174">O registro msoid é incompatível com o Microsoft 365 Enterprise Apps *(antigo Office 365 ProPlus)* e impedirá o êxito da ativação.</span><span class="sxs-lookup"><span data-stu-id="cafd6-174">The msoid record is incompatible with Microsoft 365 Enterprise Apps *(formerly Office 365 ProPlus)* and will prevent activation from succeeding.</span></span>
