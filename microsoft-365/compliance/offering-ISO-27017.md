---
title: Código de Conduta ISO/IEC 27017:2015 para Controles de Segurança de Informações
description: Os serviços de nuvem da Microsoft implementaram esse Código de Conduta para Controles de Segurança de Informações.
keywords: Microsoft 365, conformidade, ofertas
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 1f44c46046fc107e8059cebda3388fcd775bd31e
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44065686"
---
# <a name="isoiec-270172015-code-of-practice-for-information-security-controls"></a><span data-ttu-id="b03e6-104">Código de Conduta ISO/IEC 27017:2015 para Controles de Segurança de Informações</span><span class="sxs-lookup"><span data-stu-id="b03e6-104">ISO/IEC 27017:2015 Code of Practice for Information Security Controls</span></span>

## <a name="iso-iec-27017-overview"></a><span data-ttu-id="b03e6-105">Visão geral da ISO/IEC 27017</span><span class="sxs-lookup"><span data-stu-id="b03e6-105">ISO-IEC 27017 Overview</span></span>

<span data-ttu-id="b03e6-106">O código de conduta ISO/IEC 27017:2015 foi criado para as empresas usarem como referência para a seleção de controles de segurança de informações de serviços de nuvem ao implementarem um sistema de gerenciamento de segurança de informações de computação em nuvem com base na ISO/IEC 27002:2013.</span><span class="sxs-lookup"><span data-stu-id="b03e6-106">The ISO/IEC 27017:2015 code of practice is designed for organizations to use as a reference for selecting cloud services information security controls when implementing a cloud computing information security management system based on ISO/IEC 27002:2013.</span></span> <span data-ttu-id="b03e6-107">Ele também pode ser usado por provedores de serviços de nuvem como um documento de orientação para a implementação de controles de proteção geralmente aceitos.</span><span class="sxs-lookup"><span data-stu-id="b03e6-107">It can also be used by cloud service providers as a guidance document for implementing commonly accepted protection controls.</span></span>

<span data-ttu-id="b03e6-108">Esse padrão internacional fornece orientações adicionais de implementação específicas para a nuvem com base na ISO/IEC 27002 e oferece controles adicionais para lidar com ameaças e riscos de segurança de informações específicos da nuvem referentes às cláusulas 5 a 18 da ISO/IEC 27002: 2013 para controles, orientação de implementação e outras informações.</span><span class="sxs-lookup"><span data-stu-id="b03e6-108">This international standard provides additional cloud-specific implementation guidance based on ISO/IEC 27002, and provides additional controls to address cloud-specific information security threats and risks referring to clauses 5–18 in ISO/IEC 27002: 2013 for controls, implementation guidance, and other information.</span></span> <span data-ttu-id="b03e6-109">Especificamente, esse padrão fornece orientações sobre 37 controles na ISO/IEC 27002 e também apresenta 7 controles novos que não estão duplicados na ISO/IEC 27002.</span><span class="sxs-lookup"><span data-stu-id="b03e6-109">Specifically, this standard provides guidance on 37 controls in ISO/IEC 27002, and it also features seven new controls that are not duplicated in ISO/IEC 27002.</span></span> <span data-ttu-id="b03e6-110">Esses novos controles abordam as seguintes áreas importantes:</span><span class="sxs-lookup"><span data-stu-id="b03e6-110">These new controls address the following important areas:</span></span>

- <span data-ttu-id="b03e6-111">Funções e responsabilidades compartilhadas em um ambiente de computação em nuvem</span><span class="sxs-lookup"><span data-stu-id="b03e6-111">Shared roles and responsibilities within a cloud computing environment</span></span>
- <span data-ttu-id="b03e6-112">Remoção e devolução de ativos de clientes no serviço de nuvem ao término do contrato</span><span class="sxs-lookup"><span data-stu-id="b03e6-112">Removal and return of cloud service customer assets upon contract termination</span></span>
- <span data-ttu-id="b03e6-113">Proteção e separação do ambiente virtual de um cliente dos de outros clientes</span><span class="sxs-lookup"><span data-stu-id="b03e6-113">Protection and separation of a customer’s virtual environment from that of other customers</span></span>
- <span data-ttu-id="b03e6-114">Requisitos para fortalecimento das máquinas virtuais para atender a necessidades comerciais</span><span class="sxs-lookup"><span data-stu-id="b03e6-114">Virtual machine hardening requirements to meet business needs</span></span>
- <span data-ttu-id="b03e6-115">Procedimentos para operações administrativas de um ambiente de computação em nuvem</span><span class="sxs-lookup"><span data-stu-id="b03e6-115">Procedures for administrative operations of a cloud computing environment</span></span>
- <span data-ttu-id="b03e6-116">Capacitação dos clientes para monitorar atividades relevantes em um ambiente de computação em nuvem</span><span class="sxs-lookup"><span data-stu-id="b03e6-116">Enabling customers to monitor relevant activities within a cloud computing environment</span></span>
- <span data-ttu-id="b03e6-117">Alinhamento do gerenciamento da segurança para redes virtuais e físicas</span><span class="sxs-lookup"><span data-stu-id="b03e6-117">Alignment of security management for virtual and physical networks</span></span>

## <a name="microsoft-and-isoiec-27017"></a><span data-ttu-id="b03e6-118">Microsoft e ISO/IEC 27017</span><span class="sxs-lookup"><span data-stu-id="b03e6-118">Microsoft and ISO/IEC 27017</span></span>

<span data-ttu-id="b03e6-119">A ISO/IEC 27017 é única no que diz respeito a fornecer orientações para provedores e clientes de serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="b03e6-119">ISO/IEC 27017 is unique in providing guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="b03e6-120">Ele também fornece aos clientes de serviços de nuvem informações práticas sobre o que devem esperar dos provedores de serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="b03e6-120">It also provides cloud service customers with practical information on what they should expect from cloud service providers.</span></span> <span data-ttu-id="b03e6-121">Os clientes podem se beneficiar diretamente da ISO/IEC 27017, garantindo que entendam as responsabilidades compartilhadas na nuvem.</span><span class="sxs-lookup"><span data-stu-id="b03e6-121">Customers can benefit directly from ISO/IEC 27017 by ensuring they understand the shared responsibilities in the cloud.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="b03e6-122">Serviços de nuvem no Escopo da Microsoft </span><span class="sxs-lookup"><span data-stu-id="b03e6-122">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="b03e6-123">Azure, Azure Governamental e Azure Alemanha</span><span class="sxs-lookup"><span data-stu-id="b03e6-123">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="b03e6-124">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b03e6-124">Cloud App Security</span></span>
- [<span data-ttu-id="b03e6-125">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="b03e6-125">Dynamics 365</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="b03e6-126">Genomics</span><span class="sxs-lookup"><span data-stu-id="b03e6-126">Genomics</span></span>
- <span data-ttu-id="b03e6-127">Graph</span><span class="sxs-lookup"><span data-stu-id="b03e6-127">Graph</span></span>
- <span data-ttu-id="b03e6-128">Intune</span><span class="sxs-lookup"><span data-stu-id="b03e6-128">Intune</span></span>
- <span data-ttu-id="b03e6-129">Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b03e6-129">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="b03e6-130">Serviço de nuvem do Microsoft Flow como serviço autônomo ou incluído em um plano ou pacote do Office 365 ou do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="b03e6-130">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="b03e6-131">Office 365, Office 365 U.S. Government e Office 365 U.S. Government Defense e Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="b03e6-131">Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense, and Office 365 Germany</span></span>
- <span data-ttu-id="b03e6-132">Serviço de nuvem do PowerApps como um serviço autônomo ou incluído em um plano ou pacote do Office 365 ou do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="b03e6-132">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="b03e6-133">Serviço de nuvem do Power BI como um serviço autônomo ou incluído em um plano ou pacote do Office 365</span><span class="sxs-lookup"><span data-stu-id="b03e6-133">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="b03e6-134">Confira uma [lista detalhada](https://go.microsoft.com/fwlink/p/?linkid=2077751) de serviços abrangidos pelo Office 365</span><span class="sxs-lookup"><span data-stu-id="b03e6-134">See a [detailed list](https://go.microsoft.com/fwlink/p/?linkid=2077751) of covered services in Office 365</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="b03e6-135">Auditorias, relatórios e certificados</span><span class="sxs-lookup"><span data-stu-id="b03e6-135">Audits, reports, and certificates</span></span>

<span data-ttu-id="b03e6-136">Os serviços de nuvem da Microsoft são auditados uma vez ao ano de acordo com o código de conduta da ISO/IEC 27017:2015 como parte do processo de certificação da ISO/IEC 27001:2013.</span><span class="sxs-lookup"><span data-stu-id="b03e6-136">Microsoft cloud services are audited once a year for the ISO/IEC 27017:2015 code of practice as part of the certification process for ISO/IEC 27001:2013.</span></span>

- [<span data-ttu-id="b03e6-137">Certificado ISO 27017 do Azure</span><span class="sxs-lookup"><span data-stu-id="b03e6-137">Azure ISO 27017 Certificate</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078005)
- [<span data-ttu-id="b03e6-138">Relatório de avaliação da ISO 27017 do Azure</span><span class="sxs-lookup"><span data-stu-id="b03e6-138">Azure ISO 27017 Assessment report</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078010)
- [<span data-ttu-id="b03e6-139">Declaração de Aplicabilidade da ISO 27017 do Azure</span><span class="sxs-lookup"><span data-stu-id="b03e6-139">Azure ISO 27017 Statement of Applicability</span></span>](https://aka.ms/azureiso27017StatementofApplicability)
- [<span data-ttu-id="b03e6-140">Relatório de Avaliação de Auditoria da ISO 27001, 27018 e 27017 do Office 365</span><span class="sxs-lookup"><span data-stu-id="b03e6-140">Office 365 ISO 27001, 27018, and 27017 Audit Assessment Report</span></span>](https://aka.ms/o365isoreport)

## <a name="frequently-asked-questions"></a><span data-ttu-id="b03e6-141">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="b03e6-141">Frequently asked questions</span></span>

<span data-ttu-id="b03e6-142">A quem esse padrão se aplica?</span><span class="sxs-lookup"><span data-stu-id="b03e6-142">To whom does the standard apply?</span></span>

<span data-ttu-id="b03e6-143">Este código de conduta fornece controles e orientações de implementação tanto para provedores quanto para clientes de serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="b03e6-143">This code of practice provides controls and implementation guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="b03e6-144">Ele é estruturado em um formato semelhante ao da ISO/IEC 27002:2013.</span><span class="sxs-lookup"><span data-stu-id="b03e6-144">It is structured in a format similar to ISO/IEC 27002:2013.</span></span>

<span data-ttu-id="b03e6-145">**Onde posso ver as informações de conformidade da Microsoft com a ISO/IEC 27017:2015?**</span><span class="sxs-lookup"><span data-stu-id="b03e6-145">**Where can I view Microsoft’s compliance information for ISO/IEC 27017:2015?**</span></span>

<span data-ttu-id="b03e6-146">Você pode baixar o [certificado ISO/IEC 27017:2015](https://aka.ms/azureiso27017) do Azure, Intune e Power BI.</span><span class="sxs-lookup"><span data-stu-id="b03e6-146">You can download the [ISO/IEC 27017:2015 certificate](https://aka.ms/azureiso27017) for Azure, Intune, and Power BI.</span></span>

<span data-ttu-id="b03e6-147">**Posso usar a conformidade dos serviços da Microsoft com a ISO/IEC 27017 no processo de certificação da minha organização?**</span><span class="sxs-lookup"><span data-stu-id="b03e6-147">**Can I use the ISO/IEC 27017 compliance of Microsoft services in my organization’s certification process?**</span></span>

<span data-ttu-id="b03e6-148">Sim.</span><span class="sxs-lookup"><span data-stu-id="b03e6-148">Yes.</span></span> <span data-ttu-id="b03e6-149">Se a sua empresa estiver buscando uma certificação para implementações realizadas em qualquer serviço de nuvem empresarial no escopo da Microsoft, você poderá usar as respectivas certificações da Microsoft em sua avaliação de conformidade.</span><span class="sxs-lookup"><span data-stu-id="b03e6-149">If your business is seeking certification for implementations deployed on any Microsoft in-scope enterprise cloud services, you can use Microsoft’s relevant certifications in your compliance assessment.</span></span> <span data-ttu-id="b03e6-150">Contudo, você é responsável por contratar um avaliador para analisar a conformidade de sua implementação e pelos controles e processos dentro de sua organização.</span><span class="sxs-lookup"><span data-stu-id="b03e6-150">However, you are responsible for engaging an assessor to evaluate your implementation for compliance, and for the controls and processes within your own organization.</span></span>

<span data-ttu-id="b03e6-151">**Como posso obter cópias dos relatórios de auditoria aplicáveis?**</span><span class="sxs-lookup"><span data-stu-id="b03e6-151">**How can I get copies of the applicable audit reports?**</span></span>

<span data-ttu-id="b03e6-152">O [Portal de Confiança do Serviço](https://aka.ms/stphelp) fornece relatórios de auditoria de terceiros independentes e outros documentos relacionadas.</span><span class="sxs-lookup"><span data-stu-id="b03e6-152">The [Service Trust Portal](https://aka.ms/stphelp) provides independent, third-party audit reports and other related documentation.</span></span> <span data-ttu-id="b03e6-153">Você pode usar o portal para baixar e analisar essa documentação para obter assistência com seus próprios requisitos regulatórios.</span><span class="sxs-lookup"><span data-stu-id="b03e6-153">You can use the portal to download and review this documentation for assistance with your own regulatory requirements.</span></span>

## <a name="resources"></a><span data-ttu-id="b03e6-154">Recursos</span><span class="sxs-lookup"><span data-stu-id="b03e6-154">Resources</span></span>

- [<span data-ttu-id="b03e6-155">Código de conduta ISO/IEC 27017:2015</span><span class="sxs-lookup"><span data-stu-id="b03e6-155">ISO/IEC 27017:2015 code of practice</span></span>](https://www.iso.org/iso/iso_catalogue/catalogue_tc/catalogue_detail.htm?csnumber=43757)
- [<span data-ttu-id="b03e6-156">Termos do Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="b03e6-156">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="b03e6-157">Conformidade na Central de Confiabilidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="b03e6-157">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
