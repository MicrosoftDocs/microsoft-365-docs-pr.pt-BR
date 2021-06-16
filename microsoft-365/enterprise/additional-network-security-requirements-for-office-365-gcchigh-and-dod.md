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
ms.openlocfilehash: f4c03d364e84d89a1b12e4d858ab46eb3be6ae5e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926554"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="228d6-103">Requisitos de segurança de rede adicionais para Office 365 GCC High e DOD</span><span class="sxs-lookup"><span data-stu-id="228d6-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="228d6-104">*Este artigo se aplica ao Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High e Microsoft 365 DOD.*</span><span class="sxs-lookup"><span data-stu-id="228d6-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="228d6-105">Office 365 GCC High e DOD são ambientes de nuvem seguros para atender às necessidades do Governo dos Estados Unidos e seus fornecedores e prestadores de serviços.</span><span class="sxs-lookup"><span data-stu-id="228d6-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="228d6-106">Esses ambientes de nuvem têm restrições de rede adicionais em quais pontos de extremidade externos os serviços têm permissão para acessar.</span><span class="sxs-lookup"><span data-stu-id="228d6-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="228d6-107">GCC Clientes altos e do DOD que planejam usar identidades federadas ou coexistência híbrida podem exigir que a Microsoft permita acesso de entrada e/ou saída às implantações locais existentes.</span><span class="sxs-lookup"><span data-stu-id="228d6-107">GCC High and DOD customers planning to use federated identities or hybrid coexistence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="228d6-108">Exemplos dessas atividades incluem:</span><span class="sxs-lookup"><span data-stu-id="228d6-108">Examples of these activities include:</span></span>

* <span data-ttu-id="228d6-109">Uso de identidades federadas (com Serviços de Federação do Active Directory ou STS com suporte semelhante)</span><span class="sxs-lookup"><span data-stu-id="228d6-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="228d6-110">Coexistência híbrida com uma implantação local Exchange Server ou Skype for Business local</span><span class="sxs-lookup"><span data-stu-id="228d6-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="228d6-111">Migração do conteúdo do usuário existente de um sistema local</span><span class="sxs-lookup"><span data-stu-id="228d6-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="228d6-112">Para permitir que o serviço se comunique com  seus pontos de extremidade locais, você deve enviar um email para Office 365 engenharia para alterações na rede.</span><span class="sxs-lookup"><span data-stu-id="228d6-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="228d6-113">Todas as solicitações **têm** um SLA de três semanas e não podem ser aceleradas devido aos controles de segurança e conformidade necessários e pipelines de implantação.</span><span class="sxs-lookup"><span data-stu-id="228d6-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="228d6-114">Isso inclui solicitações de rede de integração iniciais, bem como quaisquer alterações depois que você tiver migrado para o serviço.</span><span class="sxs-lookup"><span data-stu-id="228d6-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="228d6-115">Certifique-se de que suas equipes de rede estão cientes dessa linha do tempo e inclua-a em seus ciclos de planejamento.</span><span class="sxs-lookup"><span data-stu-id="228d6-115">Make sure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="228d6-116">Envie um email para Office 365 Government Allow-List [solicitações](mailto:o365gwlt@microsoft.com) com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="228d6-116">Send an email to [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="228d6-117">**Para**: [Office 365 Government Allow-List solicitações](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="228d6-117">**To**: [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="228d6-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span><span class="sxs-lookup"><span data-stu-id="228d6-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="228d6-119">**Assunto de** email : Office 365 GCC Alta Solicitação de Rede - contoso.onmicrosoft.us (substitua pelo nome do locatário)</span><span class="sxs-lookup"><span data-stu-id="228d6-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace with your tenant name)</span></span>

<span data-ttu-id="228d6-120">O corpo da mensagem deve incluir os seguintes dados:</span><span class="sxs-lookup"><span data-stu-id="228d6-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="228d6-121">Seu Microsoft Online Services de locatário (por exemplo, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="228d6-121">Your Microsoft Online Services tenant name (for example, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="228d6-122">Uma lista de distribuição de email com a que a Microsoft se comunicará para comunicações em trânsito relacionadas a alterações na rede e/ou acompanhamento de sub-redes inválidas</span><span class="sxs-lookup"><span data-stu-id="228d6-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="228d6-123">Indicar se você planeja usar Microsoft Teams coexistência híbrida com suas implantações locais</span><span class="sxs-lookup"><span data-stu-id="228d6-123">Indicate whether you plan to use Microsoft Teams hybrid coexistence with your on-premises deployments</span></span>
* <span data-ttu-id="228d6-124">Sistema de identidade federado acessível externamente URL (por exemplo, sts.contoso.com) e intervalo de endereços IP na notação CIDR (por exemplo, .</span><span class="sxs-lookup"><span data-stu-id="228d6-124">Federated identity system externally accessible URL (for example, sts.contoso.com) and IP address range in CIDR notation (for example,.</span></span> <span data-ttu-id="228d6-125">10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="228d6-125">10.1.1.0/28)</span></span>
* <span data-ttu-id="228d6-126">URL da lista de certificados PKI local e intervalo de endereços IP na notação CIDR</span><span class="sxs-lookup"><span data-stu-id="228d6-126">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="228d6-127">Url acessível externamente e intervalo de endereços IP para Exchange Server implantação local na notação CIDR</span><span class="sxs-lookup"><span data-stu-id="228d6-127">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="228d6-128">Url acessível externamente e intervalo de endereços IP para Skype for Business implantação local na notação CIDR</span><span class="sxs-lookup"><span data-stu-id="228d6-128">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="228d6-129">Por motivos de segurança e conformidade, tenha em mente as seguintes restrições em sua solicitação:</span><span class="sxs-lookup"><span data-stu-id="228d6-129">For security and compliance reasons, keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="228d6-130">Há uma limitação de quatro sub-redes por locatário</span><span class="sxs-lookup"><span data-stu-id="228d6-130">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="228d6-131">As sub-redes devem estar na Notação CIDR (por exemplo, 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="228d6-131">Subnets must be in CIDR Notation (for example, 10.1.1.0/28)</span></span>
* <span data-ttu-id="228d6-132">Os intervalos de sub-rede não podem ser maiores do que /24</span><span class="sxs-lookup"><span data-stu-id="228d6-132">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="228d6-133">Não **podemos acomodar** solicitações para permitir o acesso a serviços de nuvem comercial (serviços comerciais Office 365, Google G-Suite, Amazon Web Services, etc.)</span><span class="sxs-lookup"><span data-stu-id="228d6-133">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="228d6-134">Depois que sua solicitação for recebida e aprovada pela Microsoft, há um SLA de três semanas para implementação e não pode ser expedido.</span><span class="sxs-lookup"><span data-stu-id="228d6-134">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="228d6-135">Você receberá um reconhecimento inicial quando recebermos sua solicitação e um reconhecimento final depois que ela for concluída.</span><span class="sxs-lookup"><span data-stu-id="228d6-135">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgment once it has been completed.</span></span>
