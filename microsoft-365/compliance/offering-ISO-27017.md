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
ms.openlocfilehash: 6bd989a5600252ee60ada4eb4e3d1414ef3853d5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602238"
---
# <a name="isoiec-270172015-code-of-practice-for-information-security-controls"></a><span data-ttu-id="0e047-104">Código de Conduta ISO/IEC 27017:2015 para Controles de Segurança de Informações</span><span class="sxs-lookup"><span data-stu-id="0e047-104">ISO/IEC 27017:2015 Code of Practice for Information Security Controls</span></span>

## <a name="iso-iec-27017-overview"></a><span data-ttu-id="0e047-105">Visão geral da ISO/IEC 27017</span><span class="sxs-lookup"><span data-stu-id="0e047-105">ISO-IEC 27017 Overview</span></span>

<span data-ttu-id="0e047-106">O código de conduta ISO/IEC 27017:2015 foi criado para as empresas usarem como referência para a seleção de controles de segurança de informações de serviços de nuvem ao implementarem um sistema de gerenciamento de segurança de informações de computação em nuvem com base na ISO/IEC 27002:2013.</span><span class="sxs-lookup"><span data-stu-id="0e047-106">The ISO/IEC 27017:2015 code of practice is designed for organizations to use as a reference for selecting cloud services information security controls when implementing a cloud computing information security management system based on ISO/IEC 27002:2013.</span></span> <span data-ttu-id="0e047-107">Ele também pode ser usado por provedores de serviços de nuvem como um documento de orientação para a implementação de controles de proteção geralmente aceitos.</span><span class="sxs-lookup"><span data-stu-id="0e047-107">It can also be used by cloud service providers as a guidance document for implementing commonly accepted protection controls.</span></span>

<span data-ttu-id="0e047-108">Esse padrão internacional fornece orientações adicionais de implementação específicas para a nuvem com base na ISO/IEC 27002 e oferece controles adicionais para lidar com ameaças e riscos de segurança de informações específicos da nuvem referentes às cláusulas 5 a 18 da ISO/IEC 27002: 2013 para controles, orientação de implementação e outras informações.</span><span class="sxs-lookup"><span data-stu-id="0e047-108">This international standard provides additional cloud-specific implementation guidance based on ISO/IEC 27002, and provides additional controls to address cloud-specific information security threats and risks referring to clauses 5–18 in ISO/IEC 27002: 2013 for controls, implementation guidance, and other information.</span></span> <span data-ttu-id="0e047-109">Especificamente, esse padrão fornece orientações sobre 37 controles na ISO/IEC 27002 e também apresenta 7 controles novos que não estão duplicados na ISO/IEC 27002.</span><span class="sxs-lookup"><span data-stu-id="0e047-109">Specifically, this standard provides guidance on 37 controls in ISO/IEC 27002, and it also features seven new controls that are not duplicated in ISO/IEC 27002.</span></span> <span data-ttu-id="0e047-110">Esses novos controles abordam as seguintes áreas importantes:</span><span class="sxs-lookup"><span data-stu-id="0e047-110">These new controls address the following important areas:</span></span>

- <span data-ttu-id="0e047-111">Funções e responsabilidades compartilhadas em um ambiente de computação em nuvem</span><span class="sxs-lookup"><span data-stu-id="0e047-111">Shared roles and responsibilities within a cloud computing environment</span></span>
- <span data-ttu-id="0e047-112">Remoção e devolução de ativos de clientes no serviço de nuvem ao término do contrato</span><span class="sxs-lookup"><span data-stu-id="0e047-112">Removal and return of cloud service customer assets upon contract termination</span></span>
- <span data-ttu-id="0e047-113">Proteção e separação do ambiente virtual de um cliente dos de outros clientes</span><span class="sxs-lookup"><span data-stu-id="0e047-113">Protection and separation of a customer’s virtual environment from that of other customers</span></span>
- <span data-ttu-id="0e047-114">Requisitos para fortalecimento das máquinas virtuais para atender a necessidades comerciais</span><span class="sxs-lookup"><span data-stu-id="0e047-114">Virtual machine hardening requirements to meet business needs</span></span>
- <span data-ttu-id="0e047-115">Procedimentos para operações administrativas de um ambiente de computação em nuvem</span><span class="sxs-lookup"><span data-stu-id="0e047-115">Procedures for administrative operations of a cloud computing environment</span></span>
- <span data-ttu-id="0e047-116">Capacitação dos clientes para monitorar atividades relevantes em um ambiente de computação em nuvem</span><span class="sxs-lookup"><span data-stu-id="0e047-116">Enabling customers to monitor relevant activities within a cloud computing environment</span></span>
- <span data-ttu-id="0e047-117">Alinhamento do gerenciamento da segurança para redes virtuais e físicas</span><span class="sxs-lookup"><span data-stu-id="0e047-117">Alignment of security management for virtual and physical networks</span></span>

## <a name="microsoft-and-isoiec-27017"></a><span data-ttu-id="0e047-118">Microsoft e ISO/IEC 27017</span><span class="sxs-lookup"><span data-stu-id="0e047-118">Microsoft and ISO/IEC 27017</span></span>

<span data-ttu-id="0e047-119">A ISO/IEC 27017 é única no que diz respeito a fornecer orientações para provedores e clientes de serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="0e047-119">ISO/IEC 27017 is unique in providing guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="0e047-120">Ele também fornece aos clientes de serviços de nuvem informações práticas sobre o que devem esperar dos provedores de serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="0e047-120">It also provides cloud service customers with practical information on what they should expect from cloud service providers.</span></span> <span data-ttu-id="0e047-121">Os clientes podem se beneficiar diretamente da ISO/IEC 27017, garantindo que entendam as responsabilidades compartilhadas na nuvem.</span><span class="sxs-lookup"><span data-stu-id="0e047-121">Customers can benefit directly from ISO/IEC 27017 by ensuring they understand the shared responsibilities in the cloud.</span></span>

<span data-ttu-id="0e047-122">Saiba mais sobre os benefícios da ISO/IEC 27017 no Microsoft Cloud: [Baixe o informativo da ISO/IEC 27017: Código de Conduta para Controles de Segurança de Informações](https://aka.ms/iso27017-backgrounder)</span><span class="sxs-lookup"><span data-stu-id="0e047-122">Learn about the benefits of ISO/IEC 27017 on the Microsoft Cloud: [Download the ISO/IEC 27017: Code of Practice for Information Security Controls](https://aka.ms/iso27017-backgrounder)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="0e047-123">Serviços em nuvem no escopo da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0e047-123">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="0e047-124">Azure, Azure Governamental e Azure Alemanha</span><span class="sxs-lookup"><span data-stu-id="0e047-124">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="0e047-125">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="0e047-125">Cloud App Security</span></span>
- [<span data-ttu-id="0e047-126">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="0e047-126">Dynamics 365</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="0e047-127">Genomics</span><span class="sxs-lookup"><span data-stu-id="0e047-127">Genomics</span></span>
- <span data-ttu-id="0e047-128">Graph</span><span class="sxs-lookup"><span data-stu-id="0e047-128">Graph</span></span>
- <span data-ttu-id="0e047-129">Intune</span><span class="sxs-lookup"><span data-stu-id="0e047-129">Intune</span></span>
- <span data-ttu-id="0e047-130">Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0e047-130">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="0e047-131">Serviço de nuvem do Microsoft Flow como serviço autônomo ou incluído em um plano ou pacote do Office 365 ou do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="0e047-131">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="0e047-132">Office 365, Office 365 U.S. Government e Office 365 U.S. Government Defense e Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="0e047-132">Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense, and Office 365 Germany</span></span>
- <span data-ttu-id="0e047-133">Serviço de nuvem do PowerApps como um serviço autônomo ou incluído em um plano ou pacote do Office 365 ou do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="0e047-133">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="0e047-134">Serviço de nuvem do Power BI como um serviço autônomo ou incluído em um plano ou pacote do Office 365</span><span class="sxs-lookup"><span data-stu-id="0e047-134">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="0e047-135">Confira uma [lista detalhada](https://go.microsoft.com/fwlink/p/?linkid=2077751) de serviços abrangidos pelo Office 365</span><span class="sxs-lookup"><span data-stu-id="0e047-135">See a [detailed list](https://go.microsoft.com/fwlink/p/?linkid=2077751) of covered services in Office 365</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="0e047-136">Auditorias, relatórios e certificados</span><span class="sxs-lookup"><span data-stu-id="0e047-136">Audits, reports, and certificates</span></span>

<span data-ttu-id="0e047-137">Os serviços de nuvem da Microsoft são auditados uma vez ao ano de acordo com o código de conduta da ISO/IEC 27017:2015 como parte do processo de certificação da ISO/IEC 27001:2013.</span><span class="sxs-lookup"><span data-stu-id="0e047-137">Microsoft cloud services are audited once a year for the ISO/IEC 27017:2015 code of practice as part of the certification process for ISO/IEC 27001:2013.</span></span>

- [<span data-ttu-id="0e047-138">Certificado ISO 27017 do Azure</span><span class="sxs-lookup"><span data-stu-id="0e047-138">Azure ISO 27017 Certificate</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078005)
- [<span data-ttu-id="0e047-139">Relatório de avaliação da ISO 27017 do Azure</span><span class="sxs-lookup"><span data-stu-id="0e047-139">Azure ISO 27017 Assessment report</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078010)
- [<span data-ttu-id="0e047-140">Declaração de Aplicabilidade da ISO 27017 do Azure</span><span class="sxs-lookup"><span data-stu-id="0e047-140">Azure ISO 27017 Statement of Applicability</span></span>](https://aka.ms/AzureISO27017StatementofApplicability)
- [<span data-ttu-id="0e047-141">Relatório de Avaliação de Auditoria da ISO 27001, 27018 e 27017 do Office 365</span><span class="sxs-lookup"><span data-stu-id="0e047-141">Office 365 ISO 27001, 27018, and 27017 Audit Assessment Report</span></span>](https://aka.ms/o365isoreport)

## <a name="frequently-asked-questions"></a><span data-ttu-id="0e047-142">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="0e047-142">Frequently asked questions</span></span>

<span data-ttu-id="0e047-143">A quem esse padrão se aplica?</span><span class="sxs-lookup"><span data-stu-id="0e047-143">To whom does the standard apply?</span></span>

<span data-ttu-id="0e047-144">Este código de conduta fornece controles e orientações de implementação tanto para provedores quanto para clientes de serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="0e047-144">This code of practice provides controls and implementation guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="0e047-145">Ele é estruturado em um formato semelhante ao da ISO/IEC 27002:2013.</span><span class="sxs-lookup"><span data-stu-id="0e047-145">It is structured in a format similar to ISO/IEC 27002:2013.</span></span>

<span data-ttu-id="0e047-146">**Onde posso ver as informações de conformidade da Microsoft com a ISO/IEC 27017:2015?**</span><span class="sxs-lookup"><span data-stu-id="0e047-146">**Where can I view Microsoft’s compliance information for ISO/IEC 27017:2015?**</span></span>

<span data-ttu-id="0e047-147">Você pode baixar o [certificado ISO/IEC 27017:2015](https://aka.ms/azureiso27017) do Azure, Intune e Power BI.</span><span class="sxs-lookup"><span data-stu-id="0e047-147">You can download the [ISO/IEC 27017:2015 certificate](https://aka.ms/azureiso27017) for Azure, Intune, and Power BI.</span></span>

<span data-ttu-id="0e047-148">**Posso usar a conformidade dos serviços da Microsoft com a ISO/IEC 27017 no processo de certificação da minha organização?**</span><span class="sxs-lookup"><span data-stu-id="0e047-148">**Can I use the ISO/IEC 27017 compliance of Microsoft services in my organization’s certification process?**</span></span>

<span data-ttu-id="0e047-149">Sim.</span><span class="sxs-lookup"><span data-stu-id="0e047-149">Yes.</span></span> <span data-ttu-id="0e047-150">Se a sua empresa estiver buscando uma certificação para implementações realizadas em qualquer serviço de nuvem empresarial no escopo da Microsoft, você poderá usar as respectivas certificações da Microsoft em sua avaliação de conformidade.</span><span class="sxs-lookup"><span data-stu-id="0e047-150">If your business is seeking certification for implementations deployed on any Microsoft in-scope enterprise cloud services, you can use Microsoft’s relevant certifications in your compliance assessment.</span></span> <span data-ttu-id="0e047-151">Contudo, você é responsável por contratar um avaliador para analisar a conformidade de sua implementação e pelos controles e processos dentro de sua organização.</span><span class="sxs-lookup"><span data-stu-id="0e047-151">However, you are responsible for engaging an assessor to evaluate your implementation for compliance, and for the controls and processes within your own organization.</span></span>

<span data-ttu-id="0e047-152">**Como posso obter cópias dos relatórios de auditoria aplicáveis?**</span><span class="sxs-lookup"><span data-stu-id="0e047-152">**How can I get copies of the applicable audit reports?**</span></span>

<span data-ttu-id="0e047-153">O [Portal de Confiança do Serviço](https://aka.ms/stphelp) fornece relatórios de auditoria de terceiros independentes e outros documentos relacionadas.</span><span class="sxs-lookup"><span data-stu-id="0e047-153">The [Service Trust Portal](https://aka.ms/stphelp) provides independent, third-party audit reports and other related documentation.</span></span> <span data-ttu-id="0e047-154">Você pode usar o portal para baixar e analisar essa documentação para obter assistência com seus próprios requisitos regulatórios.</span><span class="sxs-lookup"><span data-stu-id="0e047-154">You can use the portal to download and review this documentation for assistance with your own regulatory requirements.</span></span>

## <a name="resources"></a><span data-ttu-id="0e047-155">Recursos</span><span class="sxs-lookup"><span data-stu-id="0e047-155">Resources</span></span>

- [<span data-ttu-id="0e047-156">Código de conduta ISO/IEC 27017:2015</span><span class="sxs-lookup"><span data-stu-id="0e047-156">ISO/IEC 27017:2015 code of practice</span></span>](https://www.iso.org/iso/iso_catalogue/catalogue_tc/catalogue_detail.htm?csnumber=43757)
- [<span data-ttu-id="0e047-157">Termos do Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="0e047-157">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="0e047-158">Conformidade na Central de Confiabilidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0e047-158">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="0e047-159">Baixar informações de oferta</span><span class="sxs-lookup"><span data-stu-id="0e047-159">Download the offering backgrounder</span></span>

<span data-ttu-id="0e047-160">Precisa do documento informativo desta oferta?</span><span class="sxs-lookup"><span data-stu-id="0e047-160">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="0e047-161">Baixe o [PDF](https://download.microsoft.com/download/7/7/9/7799D02B-A97A-48E0-A057-C19DD543BB24/ISO-IEC-27017_backgrounder.pdf).</span><span class="sxs-lookup"><span data-stu-id="0e047-161">Download the [PDF](https://download.microsoft.com/download/7/7/9/7799D02B-A97A-48E0-A057-C19DD543BB24/ISO-IEC-27017_backgrounder.pdf).</span></span>
