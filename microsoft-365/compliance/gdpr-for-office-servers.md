---
title: RGPD para servidores do Office
description: Saiba mais sobre como atender aos requisitos de RGPD em servidores locais do Office.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.openlocfilehash: e18db2e5c180bd896e82d98506e8a65831550bce
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073229"
---
# <a name="gdpr-for-office-on-premises-servers"></a><span data-ttu-id="ede0d-103">RGPD para servidores locais do Office</span><span class="sxs-lookup"><span data-stu-id="ede0d-103">GDPR for Office on-premises Servers</span></span>

<span data-ttu-id="ede0d-p101">O RGPD (Regulamento Geral sobre a Proteção de Dados) apresenta os requisitos para as organizações protegerem dados pessoais adequadamente e atender adequadamente às solicitações de titulares de dados. Esta série de artigos fornece abordagens recomendadas para cargas de trabalho locais:</span><span class="sxs-lookup"><span data-stu-id="ede0d-p101">The General Data Protection Regulation (GDPR) introduces requirements for organizations to protect personal data and respond appropriately to data subject requests. This series of articles provides recommended approaches for on-premises workloads:</span></span>

-   [<span data-ttu-id="ede0d-106">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="ede0d-106">SharePoint Server</span></span>](gdpr-for-sharepoint-server.md)

-   [<span data-ttu-id="ede0d-107">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ede0d-107">Exchange Server</span></span>](gdpr-for-exchange-server.md)

-   [<span data-ttu-id="ede0d-108">Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ede0d-108">Skype for Business Server</span></span>](gdpr-for-skype-for-business-server.md)

-   [<span data-ttu-id="ede0d-109">Project Server</span><span class="sxs-lookup"><span data-stu-id="ede0d-109">Project Server</span></span>](gdpr-for-project-server.md)

-   [<span data-ttu-id="ede0d-110">Servidor do Office Web Apps e Servidor do Office Online</span><span class="sxs-lookup"><span data-stu-id="ede0d-110">Office Web Apps Server and Office Online Server</span></span>](gdpr-for-office-online-server.md)

-   [<span data-ttu-id="ede0d-111">Compartilhamentos de arquivos locais</span><span class="sxs-lookup"><span data-stu-id="ede0d-111">On-premises file shares</span></span>](gdpr-for-on-premises-file-shares.md)

<span data-ttu-id="ede0d-112">Para obter mais informações sobre o RGPD e como a Microsoft pode ajudar você, confira a [Central de Confiabilidade da Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="ede0d-112">For more information about the GDPR and how Microsoft can help you, see the [Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx).</span></span>

<span data-ttu-id="ede0d-p102">Antes de trabalhar com dados locais, consulte suas equipes de conformidade e jurídica para buscar orientações e saber mais sobre os esquemas e as abordagens existentes de classificação para trabalhar com dados pessoais. A Microsoft fornece recomendações para desenvolver e estender esquemas de classificação no Microsoft GDPR Data Discovery Toolkit em [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>). Esse kit de ferramentas também descreve abordagens para mover dados locais para a nuvem, onde você pode usar recursos de governança de dados mais sofisticados, se desejar. Os artigos nesta seção fornecem recomendações para os dados destinados a permanecerem no local.</span><span class="sxs-lookup"><span data-stu-id="ede0d-p102">Before doing any work with on-premises data, consult with your legal and compliance teams to seek guidance and to learn about existing classification schemas and approaches to working with personal data. Microsoft provides recommendations for developing and extending classifications schemas in the Microsoft GDPR Data Discovery Toolkit at [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>). This toolkit also describes approaches for moving on-premises data to the cloud where you can use more sophisticated data governance capabilities, if this is desired. The articles in this section provide recommendations for data that is intended to remain on premises.</span></span>

<span data-ttu-id="ede0d-p103">A ilustração a seguir lista os recursos recomendados para usar em cada uma dessas cargas de trabalho para descobrir, classificar, proteger e monitorar dados pessoais. Confira os artigos desta seção para saber mais.</span><span class="sxs-lookup"><span data-stu-id="ede0d-p103">The following illustration lists recommended capabilities to use across each of these workloads to discover, classify, protect, and monitor personal data. See the articles in this section for more information.</span></span>

![](../media/gdpr-for-office-servers-image1.png)

## <a name="illustration-description"></a><span data-ttu-id="ede0d-119">Descrição da ilustração</span><span class="sxs-lookup"><span data-stu-id="ede0d-119">Illustration description</span></span>

<span data-ttu-id="ede0d-120">Para aprimorar a acessibilidade, a tabela a seguir fornece os mesmos exemplos da ilustração.</span><span class="sxs-lookup"><span data-stu-id="ede0d-120">For accessibility, the following table provides the same examples in the illustration.</span></span>

|             |<span data-ttu-id="ede0d-121">Compartilhamentos de arquivos do Windows Server</span><span class="sxs-lookup"><span data-stu-id="ede0d-121">Windows Server file shares</span></span>|<span data-ttu-id="ede0d-122">SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="ede0d-122">SharePoint Server</span></span>|<span data-ttu-id="ede0d-123">Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ede0d-123">Exchange Server</span></span>|<span data-ttu-id="ede0d-124">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ede0d-124">Skype for Business</span></span>|<span data-ttu-id="ede0d-125">Project Server</span><span class="sxs-lookup"><span data-stu-id="ede0d-125">Project Server</span></span>|
|:------------|:-------------------------|:----------------|:--------------|:-----------------|:-------------|
|<span data-ttu-id="ede0d-126">Descobrir</span><span class="sxs-lookup"><span data-stu-id="ede0d-126">Discover</span></span>|<span data-ttu-id="ede0d-127">Verificador da Proteção de Informações do Azure\*</span><span class="sxs-lookup"><span data-stu-id="ede0d-127">Azure Information Protection scanner\*</span></span>|<span data-ttu-id="ede0d-128">Centro de Pesquisa ou Descoberta Eletrônica (depois que os dados forem classificados); verificador da Proteção de Informações do Azure\*</span><span class="sxs-lookup"><span data-stu-id="ede0d-128">Search Center or eDiscovery (after data is classified); Azure Information Protection scanner\*</span></span>|<span data-ttu-id="ede0d-129">Portal de Descoberta Eletrônica do Exchange</span><span class="sxs-lookup"><span data-stu-id="ede0d-129">Exchange eDiscovery Portal</span></span>|<span data-ttu-id="ede0d-130">Portal de Descoberta Eletrônica do Exchange</span><span class="sxs-lookup"><span data-stu-id="ede0d-130">Exchange eDiscovery portal</span></span>|<span data-ttu-id="ede0d-131">Scripts SQL para descobrir e exportar</span><span class="sxs-lookup"><span data-stu-id="ede0d-131">SQL scripts for discovery and exporting</span></span>|
|<span data-ttu-id="ede0d-132">Classificar</span><span class="sxs-lookup"><span data-stu-id="ede0d-132">Classify</span></span>|<span data-ttu-id="ede0d-133">Verificador da Proteção de Informações do Azure\*; tipos de informações confidenciais do Office 365</span><span class="sxs-lookup"><span data-stu-id="ede0d-133">Azure Information Protection scanner\*; Office 365 sensitive information types</span></span>|<span data-ttu-id="ede0d-134">Verificador da Proteção de Informações do Azure\*; tipos de informações confidenciais do Office 365</span><span class="sxs-lookup"><span data-stu-id="ede0d-134">Azure Information Protection scanner\*; Office 365 sensitive information types</span></span>|<span data-ttu-id="ede0d-135">Marcas e políticas de retenção do Exchange</span><span class="sxs-lookup"><span data-stu-id="ede0d-135">Exchange retention tags and retention policies</span></span>|<span data-ttu-id="ede0d-136">Marcas e políticas de retenção do Exchange</span><span class="sxs-lookup"><span data-stu-id="ede0d-136">Exchange retention tags and retention policies</span></span>||
|<span data-ttu-id="ede0d-137">Proteger</span><span class="sxs-lookup"><span data-stu-id="ede0d-137">Protect</span></span>||<span data-ttu-id="ede0d-138">Regras de prevenção contra perda de dados do Exchange Server; proteção de IRM para bibliotecas de permissões</span><span class="sxs-lookup"><span data-stu-id="ede0d-138">Exchange Server data loss prevention rules; Permissions, IRM-protection for libraries</span></span>|<span data-ttu-id="ede0d-139">Regras de prevenção contra perda de dados do Exchange Server; integração de IRM com o Exchange Server</span><span class="sxs-lookup"><span data-stu-id="ede0d-139">Exchange Server data loss prevention rules; IRM integration with Exchange Server</span></span>|||
|<span data-ttu-id="ede0d-140">Monitorar</span><span class="sxs-lookup"><span data-stu-id="ede0d-140">Monitor</span></span>|<span data-ttu-id="ede0d-141">Integrar logs com ferramentas SIEM</span><span class="sxs-lookup"><span data-stu-id="ede0d-141">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="ede0d-142">Integrar logs com ferramentas SIEM</span><span class="sxs-lookup"><span data-stu-id="ede0d-142">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="ede0d-143">Integrar logs com ferramentas SIEM</span><span class="sxs-lookup"><span data-stu-id="ede0d-143">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="ede0d-144">Integrar logs com ferramentas SIEM</span><span class="sxs-lookup"><span data-stu-id="ede0d-144">Integrate logs with SIEM tools</span></span>|<span data-ttu-id="ede0d-145">Integrar logs com ferramentas SIEM</span><span class="sxs-lookup"><span data-stu-id="ede0d-145">Integrate logs with SIEM tools</span></span>|

<span data-ttu-id="ede0d-p104">\*A proteção criptografa os arquivos. Consequentemente, o SharePoint Server não consegue encontrar os tipos de informações confidenciais nesses arquivos.</span><span class="sxs-lookup"><span data-stu-id="ede0d-p104">\*Note that protection encrypts the file. Consequently, SharePoint Server can’t find the sensitive information types in protected files.</span></span>
