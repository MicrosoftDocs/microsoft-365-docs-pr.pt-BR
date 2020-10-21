---
title: Infraestrutura de ti e necessidades de negócios da contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda a estrutura básica da infraestrutura de ti local da Contoso e como as necessidades de negócios da empresa são atendidas pela Microsoft 365 para empresas.
ms.openlocfilehash: bc2b34254da01a3d49085082ab8ee8632df2d434
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637170"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="5cd25-103">Infraestrutura de ti e necessidades de negócios da contoso</span><span class="sxs-lookup"><span data-stu-id="5cd25-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="5cd25-104">A Contoso está fazendo a transição de uma infraestrutura de ti centralizada e local para uma configuração inclusiva de nuvem que incorpora cargas de trabalho e aplicativos de produtividade pessoal baseados em nuvem.</span><span class="sxs-lookup"><span data-stu-id="5cd25-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="5cd25-105">Infraestrutura existente de ti da contoso</span><span class="sxs-lookup"><span data-stu-id="5cd25-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="5cd25-106">A Contoso usa principalmente a infraestrutura de TI local centralizada, com datacenters de aplicativo na sede de Paris.</span><span class="sxs-lookup"><span data-stu-id="5cd25-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="5cd25-107">A Figura 1 mostra o escritório da sede com datacenters de aplicativo, uma DMZ e a Internet.</span><span class="sxs-lookup"><span data-stu-id="5cd25-107">Figure 1 shows the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Infraestrutura existente de ti da contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="5cd25-109">**Figura 1: infraestrutura de ti existente da contoso**</span><span class="sxs-lookup"><span data-stu-id="5cd25-109">**Figure 1: Existing Contoso IT infrastructure**</span></span>
 
<span data-ttu-id="5cd25-110">Os datacenters de aplicativo locais hospedam:</span><span class="sxs-lookup"><span data-stu-id="5cd25-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="5cd25-111">Aplicativos de linha de negócios personalizados que usam o SQL Server e outros bancos de dados Linux.</span><span class="sxs-lookup"><span data-stu-id="5cd25-111">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="5cd25-112">Um conjunto de servidores herdados do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5cd25-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="5cd25-113">Servidores de organização e nível de equipe para armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="5cd25-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="5cd25-114">Além disso, cada escritório central regional tem suporte para um conjunto de servidores com um conjunto semelhante de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="5cd25-114">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="5cd25-115">Esses servidores estão sob o controle dos departamentos regionais de TI.</span><span class="sxs-lookup"><span data-stu-id="5cd25-115">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="5cd25-116">A capacidade de pesquisa entre os aplicativos e dados desses datacenters multigeográficos continua sendo um desafio.</span><span class="sxs-lookup"><span data-stu-id="5cd25-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="5cd25-117">Na matriz da Contoso DMZ, diferentes conjuntos de servidores fornecem:</span><span class="sxs-lookup"><span data-stu-id="5cd25-117">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="5cd25-118">Hospedagem para o site público da Contoso, de onde os clientes podem solicitar produtos, peças, suprimentos e serviços.</span><span class="sxs-lookup"><span data-stu-id="5cd25-118">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="5cd25-119">Hospedagem para a extranet do parceiro da Contoso para comunicação e colaboração do parceiro.</span><span class="sxs-lookup"><span data-stu-id="5cd25-119">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="5cd25-120">Acesso remoto baseado em rede privada virtual (VPN) à intranet da Contoso e proxy da Web para funcionários na sede de Paris.</span><span class="sxs-lookup"><span data-stu-id="5cd25-120">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="5cd25-121">Necessidades comerciais da contoso</span><span class="sxs-lookup"><span data-stu-id="5cd25-121">Contoso business needs</span></span>

<span data-ttu-id="5cd25-122">As necessidades corporativas da Contoso se enquadram em cinco categorias principais:</span><span class="sxs-lookup"><span data-stu-id="5cd25-122">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="5cd25-123">**Produtividade**</span><span class="sxs-lookup"><span data-stu-id="5cd25-123">**Productivity**</span></span>

- <span data-ttu-id="5cd25-124">Facilitar a colaboração</span><span class="sxs-lookup"><span data-stu-id="5cd25-124">Make collaboration easier</span></span>

  <span data-ttu-id="5cd25-125">Substitua o email e a colaboração baseada em compartilhamento de arquivos por um modelo online que permita alterações em tempo real em documentos, reuniões online mais fáceis e threads de conversa capturados.</span><span class="sxs-lookup"><span data-stu-id="5cd25-125">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="5cd25-126">Aumentar a produtividade de trabalhadores remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="5cd25-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="5cd25-127">Com muitos funcionários trabalhando de casa ou no campo, substitua a solução de VPN com gargalo por acesso de desempenho a dados e recursos da Contoso na nuvem.</span><span class="sxs-lookup"><span data-stu-id="5cd25-127">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="5cd25-128">Aumentar a criatividade e a inovação</span><span class="sxs-lookup"><span data-stu-id="5cd25-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="5cd25-129">Aproveite os métodos mais recentes de aprendizado visual e desenvolvimento de ideias, incluindo tinta e visualização 3D.</span><span class="sxs-lookup"><span data-stu-id="5cd25-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="5cd25-130">**Segurança**</span><span class="sxs-lookup"><span data-stu-id="5cd25-130">**Security**</span></span>

- <span data-ttu-id="5cd25-131">Gerenciamento de identidades e acesso</span><span class="sxs-lookup"><span data-stu-id="5cd25-131">Identity and access management</span></span>

  <span data-ttu-id="5cd25-132">Impor multifator e outras formas de autenticação e proteger credenciais de conta de administrador e de usuário.</span><span class="sxs-lookup"><span data-stu-id="5cd25-132">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="5cd25-133">Proteção contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="5cd25-133">Threat protection</span></span>

  <span data-ttu-id="5cd25-134">Proteção contra ameaças externas, incluindo emails e malware com base no sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="5cd25-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="5cd25-135">Proteção de informações</span><span class="sxs-lookup"><span data-stu-id="5cd25-135">Information protection</span></span>

  <span data-ttu-id="5cd25-136">Bloqueie o acesso e criptografe ativos digitais de alto valor, como dados de clientes, especificações de design e fabricação e informações de funcionários.</span><span class="sxs-lookup"><span data-stu-id="5cd25-136">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="5cd25-137">Gerenciamento de segurança</span><span class="sxs-lookup"><span data-stu-id="5cd25-137">Security management</span></span>

  <span data-ttu-id="5cd25-138">Monitorar a postura de segurança e detectar e responder a ameaças em tempo real.</span><span class="sxs-lookup"><span data-stu-id="5cd25-138">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="5cd25-139">**Acesso remoto e móvel e parceiros de negócios**</span><span class="sxs-lookup"><span data-stu-id="5cd25-139">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="5cd25-140">Melhorar a segurança de funcionários remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="5cd25-140">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="5cd25-141">Implemente o seu próprio dispositivo (BYOD) e o gerenciamento de dispositivos pertencentes à empresa para garantir acesso seguro, comportamento de aplicativo correto e proteção de dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="5cd25-141">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="5cd25-142">Reduzir a infraestrutura de acesso remoto para os trabalhadores</span><span class="sxs-lookup"><span data-stu-id="5cd25-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="5cd25-143">Reduza os custos de manutenção e suporte e aprimore o desempenho da solução de acesso remoto movendo recursos comumente acessados para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="5cd25-143">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="5cd25-144">Fornecer conectividade melhor e sobrecarga mais baixa para transações B2B (Business-to-susiness)</span><span class="sxs-lookup"><span data-stu-id="5cd25-144">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="5cd25-145">Substitua uma extranet de envelhecimento e de parceiro caro por uma solução baseada em nuvem que usa autenticação federada.</span><span class="sxs-lookup"><span data-stu-id="5cd25-145">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="5cd25-146">**Conformidade**</span><span class="sxs-lookup"><span data-stu-id="5cd25-146">**Compliance**</span></span>

- <span data-ttu-id="5cd25-147">Cumprir os requisitos regulamentares regionais</span><span class="sxs-lookup"><span data-stu-id="5cd25-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="5cd25-148">Garantir a conformidade com normas do setor e regionais para o armazenamento de dados, criptografia, privacidade de dados e regulamentações de dados pessoais, como a regulamentação geral de proteção de dados (RGPD) para a União Européia.</span><span class="sxs-lookup"><span data-stu-id="5cd25-148">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="5cd25-149">**Gerenciamento**</span><span class="sxs-lookup"><span data-stu-id="5cd25-149">**Management**</span></span>

- <span data-ttu-id="5cd25-150">Reduzir a sobrecarga de ti para gerenciar o software executado em computadores clientes e dispositivos</span><span class="sxs-lookup"><span data-stu-id="5cd25-150">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="5cd25-151">Automatizar a instalação de atualizações no sistema operacional Windows e nos aplicativos do Microsoft 365 para empresas em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="5cd25-151">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="5cd25-152">Mapear as necessidades de negócios da Contoso para a Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5cd25-152">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="5cd25-153">O departamento de ti da Contoso determinou o seguinte mapeamento das necessidades de negócios para os recursos do Microsoft 365 E5 antes da implantação:</span><span class="sxs-lookup"><span data-stu-id="5cd25-153">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="5cd25-154">Categoria</span><span class="sxs-lookup"><span data-stu-id="5cd25-154">Category</span></span> | <span data-ttu-id="5cd25-155">Necessidade comercial</span><span class="sxs-lookup"><span data-stu-id="5cd25-155">Business need</span></span> | <span data-ttu-id="5cd25-156">Microsoft 365 para produtos ou recursos corporativos</span><span class="sxs-lookup"><span data-stu-id="5cd25-156">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="5cd25-157">Produtividade</span><span class="sxs-lookup"><span data-stu-id="5cd25-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="5cd25-158">Facilitar a colaboração</span><span class="sxs-lookup"><span data-stu-id="5cd25-158">Make collaboration easier</span></span> | <span data-ttu-id="5cd25-159">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="5cd25-159">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="5cd25-160">Aumentar a produtividade de trabalhadores remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="5cd25-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="5cd25-161">Cargas de trabalho do Microsoft 365 e dados baseados em nuvem</span><span class="sxs-lookup"><span data-stu-id="5cd25-161">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="5cd25-162">Aumentar a criatividade e a inovação</span><span class="sxs-lookup"><span data-stu-id="5cd25-162">Increase creativity and innovation</span></span> | <span data-ttu-id="5cd25-163">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="5cd25-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="5cd25-164">Segurança</span><span class="sxs-lookup"><span data-stu-id="5cd25-164">Security</span></span> |  |  |
|  | <span data-ttu-id="5cd25-165">Gerenciamento de identidades e acesso</span><span class="sxs-lookup"><span data-stu-id="5cd25-165">Identity & access management</span></span> | <span data-ttu-id="5cd25-166">Contas de administrador global dedicadas com a MFA (autenticação multifator do Azure) e o gerenciamento de identidades (PIM) do Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="5cd25-166">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure Active Directory Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="5cd25-167">Autenticação Multifator para todas as contas de usuário</span><span class="sxs-lookup"><span data-stu-id="5cd25-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="5cd25-168">Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="5cd25-168">Conditional Access</span></span> <BR> <span data-ttu-id="5cd25-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="5cd25-169">Windows Hello</span></span> <BR> <span data-ttu-id="5cd25-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="5cd25-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="5cd25-171">Proteção contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="5cd25-171">Threat protection</span></span> | <span data-ttu-id="5cd25-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="5cd25-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="5cd25-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="5cd25-173">Windows Defender</span></span> <BR> <span data-ttu-id="5cd25-174">Proteção Avançada contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="5cd25-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="5cd25-175">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="5cd25-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="5cd25-176">Investigação e resposta de ameaças da Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5cd25-176">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="5cd25-177">Proteção de informações</span><span class="sxs-lookup"><span data-stu-id="5cd25-177">Information protection</span></span> | <span data-ttu-id="5cd25-178">Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="5cd25-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="5cd25-179">Prevenção de Perda de Dados (DLP)</span><span class="sxs-lookup"><span data-stu-id="5cd25-179">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="5cd25-180">Proteção de Informações do Windows (WIP)</span><span class="sxs-lookup"><span data-stu-id="5cd25-180">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="5cd25-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="5cd25-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="5cd25-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5cd25-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="5cd25-183">Gerenciamento de segurança</span><span class="sxs-lookup"><span data-stu-id="5cd25-183">Security management</span></span> | <span data-ttu-id="5cd25-184">Central de Segurança do Azure</span><span class="sxs-lookup"><span data-stu-id="5cd25-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="5cd25-185">Central de Segurança do Windows Defender</span><span class="sxs-lookup"><span data-stu-id="5cd25-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="5cd25-186">Acesso remoto e móvel e parceiros de negócios</span><span class="sxs-lookup"><span data-stu-id="5cd25-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="5cd25-187">Aumentar a segurança de trabalhadores remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="5cd25-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="5cd25-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5cd25-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="5cd25-189">Reduzir a infraestrutura de acesso remoto para os trabalhadores</span><span class="sxs-lookup"><span data-stu-id="5cd25-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="5cd25-190">Cargas de trabalho do Microsoft 365 e dados baseados em nuvem</span><span class="sxs-lookup"><span data-stu-id="5cd25-190">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="5cd25-191">Melhorar a conectividade e reduzir a sobrecarga de transações B2B</span><span class="sxs-lookup"><span data-stu-id="5cd25-191">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="5cd25-192">Autenticação federada e recursos baseados em nuvem</span><span class="sxs-lookup"><span data-stu-id="5cd25-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="5cd25-193">Conformidade</span><span class="sxs-lookup"><span data-stu-id="5cd25-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="5cd25-194">Cumprir os requisitos regulamentares regionais</span><span class="sxs-lookup"><span data-stu-id="5cd25-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="5cd25-195">Recursos do RGPD no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5cd25-195">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="5cd25-196">Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="5cd25-196">Management</span></span> |  |  |
|  | <span data-ttu-id="5cd25-197">Reduzir a sobrecarga de ti para instalar as atualizações do cliente</span><span class="sxs-lookup"><span data-stu-id="5cd25-197">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="5cd25-198">Anéis de implantação</span><span class="sxs-lookup"><span data-stu-id="5cd25-198">Deployment rings</span></span> <BR> <span data-ttu-id="5cd25-199">Atualizações do Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5cd25-199">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="5cd25-200">Atualizações de Aplicativos do Microsoft 365 Apps para empresas</span><span class="sxs-lookup"><span data-stu-id="5cd25-200">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="5cd25-201">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="5cd25-201">Next step</span></span>

<span data-ttu-id="5cd25-202">[Saiba mais](contoso-networking.md) sobre a rede local da Contoso Corporation e como ela foi otimizada para acesso e latência a recursos baseados em nuvem da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5cd25-202">[Learn](contoso-networking.md) about the Contoso Corporation on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="5cd25-203">Confira também</span><span class="sxs-lookup"><span data-stu-id="5cd25-203">See also</span></span>

[<span data-ttu-id="5cd25-204">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="5cd25-204">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5cd25-205">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="5cd25-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
