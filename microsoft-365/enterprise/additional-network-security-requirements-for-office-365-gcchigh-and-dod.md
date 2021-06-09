---
title: Requisitos adicionais de segurança de rede para Office 365 GCC Alta e DoD
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
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Resumo: Office 365 GCC Alta e DoD têm requisitos adicionais de segurança de rede'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687209"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="89731-103">Requisitos de segurança de rede adicionais para Office 365 GCC High e DOD</span><span class="sxs-lookup"><span data-stu-id="89731-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="89731-104">*Este artigo se aplica ao Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High e Microsoft 365 DOD.*</span><span class="sxs-lookup"><span data-stu-id="89731-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="89731-105">Office 365 GCC High e DOD são ambientes de nuvem seguros para atender às necessidades do Governo dos Estados Unidos e seus fornecedores e prestadores de serviços.</span><span class="sxs-lookup"><span data-stu-id="89731-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="89731-106">Esses ambientes de nuvem têm restrições de rede adicionais em quais pontos de extremidade externos os serviços têm permissão para acessar.</span><span class="sxs-lookup"><span data-stu-id="89731-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="89731-107">GCC Clientes altos e do DOD que planejam usar identidades federadas ou a co-existência híbrida podem exigir que a Microsoft permita acesso de entrada e/ou saída às implantações locais existentes.</span><span class="sxs-lookup"><span data-stu-id="89731-107">GCC High and DOD customers planning to use federated identities or hybrid co-existence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="89731-108">Exemplos dessas atividades incluem:</span><span class="sxs-lookup"><span data-stu-id="89731-108">Examples of these activities include:</span></span>

* <span data-ttu-id="89731-109">Uso de identidades federadas (com Serviços de Federação do Active Directory ou STS com suporte semelhante)</span><span class="sxs-lookup"><span data-stu-id="89731-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="89731-110">Coexistência híbrida com uma implantação local Exchange Server ou Skype for Business local</span><span class="sxs-lookup"><span data-stu-id="89731-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="89731-111">Migração do conteúdo do usuário existente de um sistema local</span><span class="sxs-lookup"><span data-stu-id="89731-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="89731-112">Para permitir que o serviço se comunique com  seus pontos de extremidade locais, você deve enviar um email para Office 365 engenharia para alterações na rede.</span><span class="sxs-lookup"><span data-stu-id="89731-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="89731-113">Todas as solicitações **têm** um SLA de três semanas e não podem ser aceleradas devido aos controles de segurança e conformidade necessários e pipelines de implantação.</span><span class="sxs-lookup"><span data-stu-id="89731-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="89731-114">Isso inclui solicitações de rede de integração iniciais, bem como quaisquer alterações depois que você tiver migrado para o serviço.</span><span class="sxs-lookup"><span data-stu-id="89731-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="89731-115">Certifique-se de que suas equipes de rede estão cientes dessa linha do tempo e inclua-a em seus ciclos de planejamento.</span><span class="sxs-lookup"><span data-stu-id="89731-115">Please ensure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="89731-116">Envie um email para Office 365 Government [lista branca](mailto:o365gwlt@microsoft.com) de rede com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="89731-116">Please send an email to [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="89731-117">**To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="89731-117">**To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="89731-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span><span class="sxs-lookup"><span data-stu-id="89731-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="89731-119">**Assunto de** email : Office 365 GCC Alta Solicitação de Rede - contoso.onmicrosoft.us (substitua por seu nome de locatário)</span><span class="sxs-lookup"><span data-stu-id="89731-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace this with your tenant name)</span></span>

<span data-ttu-id="89731-120">O corpo da mensagem deve incluir os seguintes dados:</span><span class="sxs-lookup"><span data-stu-id="89731-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="89731-121">Seu Microsoft Online Services de locatário (ou seja, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="89731-121">Your Microsoft Online Services tenant name (i.e. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="89731-122">Uma lista de distribuição de email com a que a Microsoft se comunicará para comunicações em trânsito relacionadas a alterações na rede e/ou acompanhamento de sub-redes inválidas</span><span class="sxs-lookup"><span data-stu-id="89731-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="89731-123">Indicar se você planeja usar Microsoft Teams uma co-existência híbrida com suas implantações locais</span><span class="sxs-lookup"><span data-stu-id="89731-123">Indicate whether you plan to use Microsoft Teams hybrid co-existence with your on-premises deployments</span></span>
* <span data-ttu-id="89731-124">Sistema de identidade federado acessível externamente URL (por exemplo, sts.contoso.com) e intervalo de endereços IP na notação CIDR (por exemplo, 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="89731-124">Federated identity system externally accessible URL (e.g. sts.contoso.com) and IP address range in CIDR notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="89731-125">URL da lista de certificados PKI local e intervalo de endereços IP na notação CIDR</span><span class="sxs-lookup"><span data-stu-id="89731-125">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="89731-126">Url acessível externamente e intervalo de endereços IP para Exchange Server implantação local na notação CIDR</span><span class="sxs-lookup"><span data-stu-id="89731-126">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="89731-127">Url acessível externamente e intervalo de endereços IP para Skype for Business implantação local na notação CIDR</span><span class="sxs-lookup"><span data-stu-id="89731-127">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="89731-128">Por motivos de segurança e conformidade, lembre-se das seguintes restrições em sua solicitação:</span><span class="sxs-lookup"><span data-stu-id="89731-128">For security and compliance reasons, please keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="89731-129">Há uma limitação de quatro sub-redes por locatário</span><span class="sxs-lookup"><span data-stu-id="89731-129">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="89731-130">As sub-redes devem estar na Notação CIDR (por exemplo, 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="89731-130">Subnets must be in CIDR Notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="89731-131">Os intervalos de sub-rede não podem ser maiores do que /24</span><span class="sxs-lookup"><span data-stu-id="89731-131">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="89731-132">Não **podemos acomodar** solicitações para permitir o acesso a serviços de nuvem comercial (serviços comerciais Office 365, Google G-Suite, Amazon Web Services, etc.)</span><span class="sxs-lookup"><span data-stu-id="89731-132">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="89731-133">Depois que sua solicitação for recebida e aprovada pela Microsoft, há um SLA de três semanas para implementação e não pode ser expedido.</span><span class="sxs-lookup"><span data-stu-id="89731-133">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="89731-134">Você receberá um reconhecimento inicial quando recebermos sua solicitação e um reconhecimento final depois que ela for concluída.</span><span class="sxs-lookup"><span data-stu-id="89731-134">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgement once it has been completed.</span></span>
