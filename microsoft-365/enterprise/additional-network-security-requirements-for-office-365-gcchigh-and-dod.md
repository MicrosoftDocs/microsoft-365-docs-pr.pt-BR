---
title: Requisitos adicionais de segurança de rede para o Office 365 GCC High e DoD
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
description: 'Resumo: o Office 365 GCC High e o DoD têm requisitos de segurança de rede adicionais'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687209"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="1cd8b-103">Requisitos adicionais de segurança de rede para o Office 365 GCC High e DOD</span><span class="sxs-lookup"><span data-stu-id="1cd8b-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="1cd8b-104">*Este artigo se aplica ao Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High e Microsoft 365 DOD.*</span><span class="sxs-lookup"><span data-stu-id="1cd8b-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="1cd8b-105">O Office 365 GCC High e o DOD são ambientes de nuvem seguros para atender às necessidades do governo dos Estados Unidos e de seus fornecedores e prestadores de atendimento.</span><span class="sxs-lookup"><span data-stu-id="1cd8b-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="1cd8b-106">Esses ambientes de nuvem têm restrições de rede adicionais nas quais os pontos de extremidade externos podem acessar os serviços.</span><span class="sxs-lookup"><span data-stu-id="1cd8b-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="1cd8b-107">Os clientes do GCC High e do DOD que planejam usar identidades federadas ou a coexistência híbrida podem exigir que a Microsoft permita o acesso de entrada e saída às suas implantações locais existentes.</span><span class="sxs-lookup"><span data-stu-id="1cd8b-107">GCC High and DOD customers planning to use federated identities or hybrid co-existence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="1cd8b-108">Exemplos dessas atividades incluem:</span><span class="sxs-lookup"><span data-stu-id="1cd8b-108">Examples of these activities include:</span></span>

* <span data-ttu-id="1cd8b-109">Uso de identidades federadas (com os serviços de Federação do Active Directory ou STS com suporte semelhante)</span><span class="sxs-lookup"><span data-stu-id="1cd8b-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="1cd8b-110">Coexistência híbrida com uma implantação local do Exchange Server ou do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1cd8b-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="1cd8b-111">Migração de conteúdo de usuário existente de um sistema local</span><span class="sxs-lookup"><span data-stu-id="1cd8b-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="1cd8b-112">Para permitir que o serviço se comunique com seus pontos de extremidade locais, você **deve** enviar um email para o Office 365 Engineering for Network Changes.</span><span class="sxs-lookup"><span data-stu-id="1cd8b-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="1cd8b-113">Todas as solicitações têm um SLA de **três semanas** e não podem ser expedidas devido aos controles de conformidade e segurança necessários e a pipelines de implantação.</span><span class="sxs-lookup"><span data-stu-id="1cd8b-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="1cd8b-114">Isso inclui solicitações de rede de integração inicial, bem como qualquer alteração após você ter migrado para o serviço.</span><span class="sxs-lookup"><span data-stu-id="1cd8b-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="1cd8b-115">Certifique-se de que suas equipes de rede estejam cientes dessa linha do tempo e inclua-as nos ciclos de planejamento.</span><span class="sxs-lookup"><span data-stu-id="1cd8b-115">Please ensure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="1cd8b-116">Envie um email para a [lista branca de rede governamental do Office 365](mailto:o365gwlt@microsoft.com) com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="1cd8b-116">Please send an email to [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="1cd8b-117">**Para**: [lista branca de rede governamental do Office 365](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="1cd8b-117">**To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="1cd8b-118">**De**: um administrador de locatários-o email de envio **deve** corresponder a um contato de administrador global em seu locatário</span><span class="sxs-lookup"><span data-stu-id="1cd8b-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="1cd8b-119">**Assunto do email**: solicitação de rede alta do Office 365 GCC-contoso.onmicrosoft.us (substitua isso pelo nome do seu locatário)</span><span class="sxs-lookup"><span data-stu-id="1cd8b-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace this with your tenant name)</span></span>

<span data-ttu-id="1cd8b-120">O corpo da mensagem deve incluir os seguintes dados:</span><span class="sxs-lookup"><span data-stu-id="1cd8b-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="1cd8b-121">Seu nome de locatário do Microsoft Online Services (ou seja, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="1cd8b-121">Your Microsoft Online Services tenant name (i.e. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="1cd8b-122">Uma lista de distribuição de email com a qual a Microsoft se comunicará para comunicações em andamento relacionadas a alterações de rede e/ou acompanhamento de sub-redes inválidas</span><span class="sxs-lookup"><span data-stu-id="1cd8b-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="1cd8b-123">Indicar se você planeja usar a coexistência híbrida do Microsoft Teams com suas implantações locais</span><span class="sxs-lookup"><span data-stu-id="1cd8b-123">Indicate whether you plan to use Microsoft Teams hybrid co-existence with your on-premises deployments</span></span>
* <span data-ttu-id="1cd8b-124">URL acessível externamente do sistema de identidade federada (por exemplo, sts.contoso.com) e intervalo de endereços IP em notação CIDR (por exemplo, 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="1cd8b-124">Federated identity system externally accessible URL (e.g. sts.contoso.com) and IP address range in CIDR notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="1cd8b-125">URL da lista de certificados revogados de PKI local e intervalo de endereços IP na notação CIDR</span><span class="sxs-lookup"><span data-stu-id="1cd8b-125">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="1cd8b-126">URL e intervalo de endereços IP acessíveis externamente para a implantação local do Exchange Server na notação CIDR</span><span class="sxs-lookup"><span data-stu-id="1cd8b-126">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="1cd8b-127">URL e intervalo de endereços IP acessíveis externamente para a implantação local do Skype for Business em notação CIDR</span><span class="sxs-lookup"><span data-stu-id="1cd8b-127">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="1cd8b-128">Por motivos de segurança e conformidade, tenha em mente as seguintes restrições em sua solicitação:</span><span class="sxs-lookup"><span data-stu-id="1cd8b-128">For security and compliance reasons, please keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="1cd8b-129">Há quatro limitações de sub-rede por locatário</span><span class="sxs-lookup"><span data-stu-id="1cd8b-129">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="1cd8b-130">As sub-redes devem estar na notação CIDR (por exemplo, 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="1cd8b-130">Subnets must be in CIDR Notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="1cd8b-131">Os intervalos de sub-rede não podem ser maiores que/24</span><span class="sxs-lookup"><span data-stu-id="1cd8b-131">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="1cd8b-132">**Não é possível** acomodar solicitações para permitir o acesso aos serviços de nuvem comercial (comercial 365, Google G-Suite, serviços da Amazon, etc.)</span><span class="sxs-lookup"><span data-stu-id="1cd8b-132">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="1cd8b-133">Após a solicitação ser recebida e aprovada pela Microsoft, há um SLA de três semanas para implementação e não pode ser acelerado.</span><span class="sxs-lookup"><span data-stu-id="1cd8b-133">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="1cd8b-134">Você receberá uma confirmação inicial quando recebermos sua solicitação e uma confirmação final após a conclusão.</span><span class="sxs-lookup"><span data-stu-id="1cd8b-134">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgement once it has been completed.</span></span>
