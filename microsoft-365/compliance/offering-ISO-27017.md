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
ms.openlocfilehash: 329bb7c4662d6449d69c6dca9ad489bdd70a0d3f
ms.sourcegitcommit: daad5f2f1994a812c2b9c78e7dd148d10c51f61d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2020
ms.locfileid: "44254224"
---
# <a name="isoiec-270172015-code-of-practice-for-information-security-controls"></a><span data-ttu-id="8f3ca-104">Código de Conduta ISO/IEC 27017:2015 para Controles de Segurança de Informações</span><span class="sxs-lookup"><span data-stu-id="8f3ca-104">ISO/IEC 27017:2015 Code of Practice for Information Security Controls</span></span>

## <a name="iso-iec-27017-overview"></a><span data-ttu-id="8f3ca-105">Visão geral da ISO/IEC 27017</span><span class="sxs-lookup"><span data-stu-id="8f3ca-105">ISO-IEC 27017 Overview</span></span>

<span data-ttu-id="8f3ca-106">O código de conduta ISO/IEC 27017:2015 foi criado para as empresas usarem como referência para a seleção de controles de segurança de informações de serviços de nuvem ao implementarem um sistema de gerenciamento de segurança de informações de computação em nuvem com base na ISO/IEC 27002:2013.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-106">The ISO/IEC 27017:2015 code of practice is designed for organizations to use as a reference for selecting cloud services information security controls when implementing a cloud computing information security management system based on ISO/IEC 27002:2013.</span></span> <span data-ttu-id="8f3ca-107">Ele também pode ser usado por provedores de serviços de nuvem como um documento de orientação para a implementação de controles de proteção geralmente aceitos.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-107">It can also be used by cloud service providers as a guidance document for implementing commonly accepted protection controls.</span></span>

<span data-ttu-id="8f3ca-108">Esse padrão internacional fornece orientações adicionais de implementação específicas para a nuvem com base na ISO/IEC 27002 e oferece controles adicionais para lidar com ameaças e riscos de segurança de informações específicos da nuvem referentes às cláusulas 5 a 18 da ISO/IEC 27002: 2013 para controles, orientação de implementação e outras informações.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-108">This international standard provides additional cloud-specific implementation guidance based on ISO/IEC 27002, and provides additional controls to address cloud-specific information security threats and risks referring to clauses 5–18 in ISO/IEC 27002: 2013 for controls, implementation guidance, and other information.</span></span> <span data-ttu-id="8f3ca-109">Especificamente, esse padrão fornece orientações sobre 37 controles na ISO/IEC 27002 e também apresenta 7 controles novos que não estão duplicados na ISO/IEC 27002.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-109">Specifically, this standard provides guidance on 37 controls in ISO/IEC 27002, and it also features seven new controls that are not duplicated in ISO/IEC 27002.</span></span> <span data-ttu-id="8f3ca-110">Esses novos controles abordam as seguintes áreas importantes:</span><span class="sxs-lookup"><span data-stu-id="8f3ca-110">These new controls address the following important areas:</span></span>

- <span data-ttu-id="8f3ca-111">Funções e responsabilidades compartilhadas em um ambiente de computação em nuvem</span><span class="sxs-lookup"><span data-stu-id="8f3ca-111">Shared roles and responsibilities within a cloud computing environment</span></span>
- <span data-ttu-id="8f3ca-112">Remoção e devolução de ativos de clientes no serviço de nuvem ao término do contrato</span><span class="sxs-lookup"><span data-stu-id="8f3ca-112">Removal and return of cloud service customer assets upon contract termination</span></span>
- <span data-ttu-id="8f3ca-113">Proteção e separação do ambiente virtual de um cliente dos ambientes de outros clientes</span><span class="sxs-lookup"><span data-stu-id="8f3ca-113">Protection and separation of a customer’s virtual environment from environments of other customers</span></span>
- <span data-ttu-id="8f3ca-114">Requisitos para fortalecimento das máquinas virtuais para atender a necessidades comerciais</span><span class="sxs-lookup"><span data-stu-id="8f3ca-114">Virtual machine hardening requirements to meet business needs</span></span>
- <span data-ttu-id="8f3ca-115">Procedimentos para operações administrativas de um ambiente de computação em nuvem</span><span class="sxs-lookup"><span data-stu-id="8f3ca-115">Procedures for administrative operations of a cloud computing environment</span></span>
- <span data-ttu-id="8f3ca-116">Capacitação dos clientes para monitorar atividades relevantes em um ambiente de computação em nuvem</span><span class="sxs-lookup"><span data-stu-id="8f3ca-116">Enabling customers to monitor relevant activities within a cloud computing environment</span></span>
- <span data-ttu-id="8f3ca-117">Alinhamento do gerenciamento da segurança para redes virtuais e físicas</span><span class="sxs-lookup"><span data-stu-id="8f3ca-117">Alignment of security management for virtual and physical networks</span></span>

## <a name="microsoft-and-isoiec-27017"></a><span data-ttu-id="8f3ca-118">Microsoft e ISO/IEC 27017</span><span class="sxs-lookup"><span data-stu-id="8f3ca-118">Microsoft and ISO/IEC 27017</span></span>

<span data-ttu-id="8f3ca-119">A ISO/IEC 27017 é única no que diz respeito a fornecer orientações para provedores e clientes de serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-119">ISO/IEC 27017 is unique in providing guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="8f3ca-120">Ele também fornece aos clientes de serviços de nuvem informações práticas sobre o que devem esperar dos provedores de serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-120">It also provides cloud service customers with practical information on what they should expect from cloud service providers.</span></span> <span data-ttu-id="8f3ca-121">Os clientes podem se beneficiar diretamente da ISO/IEC 27017, garantindo que entendam as responsabilidades compartilhadas na nuvem.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-121">Customers can benefit directly from ISO/IEC 27017 by ensuring they understand the shared responsibilities in the cloud.</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="8f3ca-122">Serviços de nuvem no Escopo da Microsoft </span><span class="sxs-lookup"><span data-stu-id="8f3ca-122">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="8f3ca-123">Azure, Azure Governamental e Azure Alemanha</span><span class="sxs-lookup"><span data-stu-id="8f3ca-123">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="8f3ca-124">Segurança no aplicativo na nuvem da Microsoft</span><span class="sxs-lookup"><span data-stu-id="8f3ca-124">Microsoft Cloud App Security</span></span>
- [<span data-ttu-id="8f3ca-125">Dynamics 365, Dynamics 365 e Dynamics 365 Germany</span><span class="sxs-lookup"><span data-stu-id="8f3ca-125">Dynamics 365, Dynamics 365, and Dynamics 365 Germany</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="8f3ca-126">Proteção avançada contra ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="8f3ca-126">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="8f3ca-127">Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="8f3ca-127">Microsoft Graph</span></span>
- <span data-ttu-id="8f3ca-128">Bot do Microsoft Healthcare</span><span class="sxs-lookup"><span data-stu-id="8f3ca-128">Microsoft Healthcare Bot</span></span>
- <span data-ttu-id="8f3ca-129">Intune</span><span class="sxs-lookup"><span data-stu-id="8f3ca-129">Intune</span></span>
- <span data-ttu-id="8f3ca-130">Área de Trabalho Gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="8f3ca-130">Microsoft Managed Desktop</span></span>
- <span data-ttu-id="8f3ca-131">Serviço de nuvem do Power Automate (anteriormente Microsoft Flow) como um serviço autônomo ou incluído em um plano ou pacote do Office 365 ou Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8f3ca-131">Power Automate (formerly Microsoft Flow) cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="8f3ca-132">Office 365, Office 365 U.S. Government e Office 365 U.S. Government Defense e Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="8f3ca-132">Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense, and Office 365 Germany</span></span>
- <span data-ttu-id="8f3ca-133">Serviço de nuvem do PowerApps como um serviço autônomo ou incluído em um plano ou pacote do Office 365 ou do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8f3ca-133">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="8f3ca-134">Serviço de nuvem do Power BI como um serviço autônomo ou incluído em um plano ou pacote do Office 365</span><span class="sxs-lookup"><span data-stu-id="8f3ca-134">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="8f3ca-135">Power BI incorporado</span><span class="sxs-lookup"><span data-stu-id="8f3ca-135">Power BI Embedded</span></span>
- <span data-ttu-id="8f3ca-136">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="8f3ca-136">Microsoft Stream</span></span>
- <span data-ttu-id="8f3ca-137">Confira uma [lista detalhada](https://go.microsoft.com/fwlink/p/?linkid=2077751) de serviços abrangidos pelo Office 365</span><span class="sxs-lookup"><span data-stu-id="8f3ca-137">See a [detailed list](https://go.microsoft.com/fwlink/p/?linkid=2077751) of covered services in Office 365</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="8f3ca-138">Auditorias, relatórios e certificados</span><span class="sxs-lookup"><span data-stu-id="8f3ca-138">Audits, reports, and certificates</span></span>

<span data-ttu-id="8f3ca-139">Os serviços de nuvem da Microsoft são auditados uma vez ao ano de acordo com o código de conduta da ISO/IEC 27017:2015 como parte do processo de certificação da ISO/IEC 27001:2013.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-139">Microsoft cloud services are audited once a year for the ISO/IEC 27017:2015 code of practice as part of the certification process for ISO/IEC 27001:2013.</span></span>

- [<span data-ttu-id="8f3ca-140">Certificado ISO 27017 do Azure</span><span class="sxs-lookup"><span data-stu-id="8f3ca-140">Azure ISO 27017 Certificate</span></span>](https://aka.ms/azureiso27017cert)
- [<span data-ttu-id="8f3ca-141">Relatório de avaliação da ISO 27017 do Azure</span><span class="sxs-lookup"><span data-stu-id="8f3ca-141">Azure ISO 27017 Assessment report</span></span>](https://aka.ms/azureiso27017report)
- [<span data-ttu-id="8f3ca-142">Office 365: Relatório da avaliação de auditoria do ISO 27001, 27018, ISO 27017 e 27017</span><span class="sxs-lookup"><span data-stu-id="8f3ca-142">Office 365: ISO 27001, 27018, and 27017 Audit Assessment Report</span></span>](https://aka.ms/o365isoreport)

## <a name="frequently-asked-questions"></a><span data-ttu-id="8f3ca-143">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="8f3ca-143">Frequently asked questions</span></span>

<span data-ttu-id="8f3ca-144">A quem esse padrão se aplica?</span><span class="sxs-lookup"><span data-stu-id="8f3ca-144">To whom does the standard apply?</span></span>

<span data-ttu-id="8f3ca-145">Este código de conduta fornece controles e orientações de implementação tanto para provedores quanto para clientes de serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-145">This code of practice provides controls and implementation guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="8f3ca-146">Ele é estruturado em um formato semelhante ao da ISO/IEC 27002:2013.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-146">It is structured in a format similar to ISO/IEC 27002:2013.</span></span>

<span data-ttu-id="8f3ca-147">**Onde posso ver as informações de conformidade da Microsoft com a ISO/IEC 27017:2015?**</span><span class="sxs-lookup"><span data-stu-id="8f3ca-147">**Where can I view Microsoft’s compliance information for ISO/IEC 27017:2015?**</span></span>

<span data-ttu-id="8f3ca-148">Você pode baixar o [certificado ISO/IEC 27017:2015](https://aka.ms/azureiso27017) do Azure, Intune e Power BI.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-148">You can download the [ISO/IEC 27017:2015 certificate](https://aka.ms/azureiso27017) for Azure, Intune, and Power BI.</span></span>

<span data-ttu-id="8f3ca-149">**Posso usar a conformidade dos serviços da Microsoft com a ISO/IEC 27017 no processo de certificação da minha organização?**</span><span class="sxs-lookup"><span data-stu-id="8f3ca-149">**Can I use the ISO/IEC 27017 compliance of Microsoft services in my organization’s certification process?**</span></span>

<span data-ttu-id="8f3ca-150">Sim.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-150">Yes.</span></span> <span data-ttu-id="8f3ca-151">Se a sua empresa estiver buscando uma certificação para implementações realizadas em qualquer serviço de nuvem empresarial no escopo da Microsoft, você poderá usar as respectivas certificações da Microsoft em sua avaliação de conformidade.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-151">If your business is seeking certification for implementations deployed on any Microsoft in-scope enterprise cloud services, you can use Microsoft’s relevant certifications in your compliance assessment.</span></span> <span data-ttu-id="8f3ca-152">Contudo, você é responsável por contratar um avaliador para analisar a conformidade de sua implementação e pelos controles e processos dentro de sua organização.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-152">However, you are responsible for engaging an assessor to evaluate your implementation for compliance, and for the controls and processes within your own organization.</span></span>

<span data-ttu-id="8f3ca-153">**Como posso obter cópias dos relatórios de auditoria aplicáveis?**</span><span class="sxs-lookup"><span data-stu-id="8f3ca-153">**How can I get copies of the applicable audit reports?**</span></span>

<span data-ttu-id="8f3ca-154">O [Portal de Confiança do Serviço](https://aka.ms/stphelp) fornece relatórios de auditoria de terceiros independentes e outros documentos relacionadas.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-154">The [Service Trust Portal](https://aka.ms/stphelp) provides independent, third-party audit reports and other related documentation.</span></span> <span data-ttu-id="8f3ca-155">Você pode usar o portal para baixar e analisar essa documentação para obter assistência com seus próprios requisitos regulatórios.</span><span class="sxs-lookup"><span data-stu-id="8f3ca-155">You can use the portal to download and review this documentation for assistance with your own regulatory requirements.</span></span>

## <a name="resources"></a><span data-ttu-id="8f3ca-156">Recursos</span><span class="sxs-lookup"><span data-stu-id="8f3ca-156">Resources</span></span>

- [<span data-ttu-id="8f3ca-157">Código de conduta ISO/IEC 27017:2015</span><span class="sxs-lookup"><span data-stu-id="8f3ca-157">ISO/IEC 27017:2015 code of practice</span></span>](https://www.iso.org/iso/iso_catalogue/catalogue_tc/catalogue_detail.htm?csnumber=43757)
- [<span data-ttu-id="8f3ca-158">Termos do Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="8f3ca-158">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="8f3ca-159">Conformidade na Central de Confiabilidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="8f3ca-159">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)
