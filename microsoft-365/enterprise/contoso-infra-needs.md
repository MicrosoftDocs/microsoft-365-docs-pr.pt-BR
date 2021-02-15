---
title: Infraestrutura de TI e necessidades comerciais da Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda a estrutura básica da infraestrutura de TI local da Contoso e como as necessidades comerciais da empresa são atendidas pelo Microsoft 365 para empresas.
ms.openlocfilehash: 72d502b5078a1e572eeba27832550af52907e209
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558401"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="8dc37-103">Infraestrutura de TI e necessidades comerciais da Contoso</span><span class="sxs-lookup"><span data-stu-id="8dc37-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="8dc37-104">A Contoso está em transição de uma infraestrutura de TI centralizada local para uma configuração inclusiva na nuvem que incorpora cargas de trabalho e aplicativos de produtividade pessoal baseados em nuvem.</span><span class="sxs-lookup"><span data-stu-id="8dc37-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="8dc37-105">Infraestrutura de TI existente da Contoso</span><span class="sxs-lookup"><span data-stu-id="8dc37-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="8dc37-106">A Contoso usa principalmente a infraestrutura de TI local centralizada, com datacenters de aplicativo na sede de Paris.</span><span class="sxs-lookup"><span data-stu-id="8dc37-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="8dc37-107">Aqui está o escritório da matriz com datacenters de aplicativos, uma DMZ e a Internet.</span><span class="sxs-lookup"><span data-stu-id="8dc37-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Infraestrutura de TI existente da Contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="8dc37-109">Os datacenters de aplicativo locais hospedam:</span><span class="sxs-lookup"><span data-stu-id="8dc37-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="8dc37-110">Aplicativos de linha de negócios personalizados que usam o SQL Server e outros bancos de dados do Linux.</span><span class="sxs-lookup"><span data-stu-id="8dc37-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="8dc37-111">Um conjunto de servidores herdados do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8dc37-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="8dc37-112">Servidores de organização e nível de equipe para armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="8dc37-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="8dc37-113">Além disso, cada escritório central regional tem suporte para um conjunto de servidores com um conjunto semelhante de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="8dc37-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="8dc37-114">Esses servidores estão sob o controle dos departamentos regionais de TI.</span><span class="sxs-lookup"><span data-stu-id="8dc37-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="8dc37-115">A capacidade de pesquisa entre os aplicativos e dados desses datacenters multigeográficos continua sendo um desafio.</span><span class="sxs-lookup"><span data-stu-id="8dc37-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="8dc37-116">Na DMZ da sede da Contoso, diferentes conjuntos de servidores fornecem:</span><span class="sxs-lookup"><span data-stu-id="8dc37-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="8dc37-117">Hospedagem para o site público da Contoso, do qual os clientes podem solicitar produtos, partes, suprimentos e serviço.</span><span class="sxs-lookup"><span data-stu-id="8dc37-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="8dc37-118">Hospedagem para a extranet do parceiro da Contoso para comunicação e colaboração do parceiro.</span><span class="sxs-lookup"><span data-stu-id="8dc37-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="8dc37-119">Acesso remoto baseado em rede privada virtual (VPN) à intranet da Contoso e proxy da Web para funcionários na sede de Paris.</span><span class="sxs-lookup"><span data-stu-id="8dc37-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="8dc37-120">Necessidades comerciais da Contoso</span><span class="sxs-lookup"><span data-stu-id="8dc37-120">Contoso business needs</span></span>

<span data-ttu-id="8dc37-121">As necessidades comerciais da Contoso se enquadram em cinco categorias principais:</span><span class="sxs-lookup"><span data-stu-id="8dc37-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="8dc37-122">**Produtividade**</span><span class="sxs-lookup"><span data-stu-id="8dc37-122">**Productivity**</span></span>

- <span data-ttu-id="8dc37-123">Facilitar a colaboração</span><span class="sxs-lookup"><span data-stu-id="8dc37-123">Make collaboration easier</span></span>

  <span data-ttu-id="8dc37-124">Substitua a colaboração baseada em compartilhamento de emails e arquivos por um modelo online que permita alterações em tempo real em documentos, reuniões online mais fáceis e threads de conversa capturados.</span><span class="sxs-lookup"><span data-stu-id="8dc37-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="8dc37-125">Aumentar a produtividade de trabalhadores remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="8dc37-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="8dc37-126">Com muitos funcionários trabalhando em casa ou em campo, substitua a solução VPN com gargalo pelo acesso de desempenho aos dados e recursos da Contoso na nuvem.</span><span class="sxs-lookup"><span data-stu-id="8dc37-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="8dc37-127">Aumentar a criatividade e a inovação</span><span class="sxs-lookup"><span data-stu-id="8dc37-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="8dc37-128">Aproveite os métodos mais recentes de aprendizado visual e desenvolvimento de ideias, incluindo tinta e visualização 3D.</span><span class="sxs-lookup"><span data-stu-id="8dc37-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="8dc37-129">**Segurança**</span><span class="sxs-lookup"><span data-stu-id="8dc37-129">**Security**</span></span>

- <span data-ttu-id="8dc37-130">Gerenciamento de identidades e acesso</span><span class="sxs-lookup"><span data-stu-id="8dc37-130">Identity and access management</span></span>

  <span data-ttu-id="8dc37-131">Im enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span><span class="sxs-lookup"><span data-stu-id="8dc37-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="8dc37-132">Proteção contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="8dc37-132">Threat protection</span></span>

  <span data-ttu-id="8dc37-133">Proteção contra ameaças externas, incluindo emails e malware com base no sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="8dc37-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="8dc37-134">Proteção de informações</span><span class="sxs-lookup"><span data-stu-id="8dc37-134">Information protection</span></span>

  <span data-ttu-id="8dc37-135">Bloqueie o acesso e criptografe ativos digitais de alto valor, como dados de clientes, especificações de design e fabricação e informações de funcionários.</span><span class="sxs-lookup"><span data-stu-id="8dc37-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="8dc37-136">Gerenciamento de segurança</span><span class="sxs-lookup"><span data-stu-id="8dc37-136">Security management</span></span>

  <span data-ttu-id="8dc37-137">Monitore a postura de segurança e detecte e responda a ameaças em tempo real.</span><span class="sxs-lookup"><span data-stu-id="8dc37-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="8dc37-138">**Acesso remoto e móvel e parceiros de negócios**</span><span class="sxs-lookup"><span data-stu-id="8dc37-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="8dc37-139">Melhorar a segurança para funcionários remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="8dc37-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="8dc37-140">Implemente o BYOD (traga seu próprio dispositivo) e o gerenciamento de dispositivos de propriedade da empresa para garantir o acesso seguro, o comportamento correto do aplicativo e a proteção de dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="8dc37-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="8dc37-141">Reduzir a infraestrutura de acesso remoto para os trabalhadores</span><span class="sxs-lookup"><span data-stu-id="8dc37-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="8dc37-142">Reduza os custos de manutenção e suporte e melhore o desempenho da solução de acesso remoto movendo recursos comumente acessados para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="8dc37-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="8dc37-143">Fornecer conectividade melhor e sobrecarga mais baixa para transações B2B (business-to-susiness)</span><span class="sxs-lookup"><span data-stu-id="8dc37-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="8dc37-144">Substitua uma extranet de parceiros de idade e cara por uma solução baseada em nuvem que usa autenticação federada.</span><span class="sxs-lookup"><span data-stu-id="8dc37-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="8dc37-145">**Conformidade**</span><span class="sxs-lookup"><span data-stu-id="8dc37-145">**Compliance**</span></span>

- <span data-ttu-id="8dc37-146">Cumprir os requisitos regulamentares regionais</span><span class="sxs-lookup"><span data-stu-id="8dc37-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="8dc37-147">Garantir a conformidade com os regulamentos regionais e do setor para armazenamento de dados, criptografia, privacidade de dados e regulamentos de dados pessoais, como o Regulamento Geral sobre a Proteção de Dados (RGPD) para a União Europeia.</span><span class="sxs-lookup"><span data-stu-id="8dc37-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="8dc37-148">**Gerenciamento**</span><span class="sxs-lookup"><span data-stu-id="8dc37-148">**Management**</span></span>

- <span data-ttu-id="8dc37-149">Menos sobrecarga de IT para gerenciar software em execução em PCs e dispositivos cliente</span><span class="sxs-lookup"><span data-stu-id="8dc37-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="8dc37-150">Automatize a instalação de atualizações no sistema operacional Windows e no Microsoft 365 Apps para empresas em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="8dc37-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="8dc37-151">Mapear as necessidades comerciais da Contoso para o Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="8dc37-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="8dc37-152">O departamento de IT da Contoso determinou o seguinte mapeamento das necessidades comerciais para os recursos do Microsoft 365 E5 antes da implantação:</span><span class="sxs-lookup"><span data-stu-id="8dc37-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="8dc37-153">Categoria</span><span class="sxs-lookup"><span data-stu-id="8dc37-153">Category</span></span> | <span data-ttu-id="8dc37-154">Necessidade comercial</span><span class="sxs-lookup"><span data-stu-id="8dc37-154">Business need</span></span> | <span data-ttu-id="8dc37-155">Produtos ou recursos do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="8dc37-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="8dc37-156">Produtividade</span><span class="sxs-lookup"><span data-stu-id="8dc37-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="8dc37-157">Facilitar a colaboração</span><span class="sxs-lookup"><span data-stu-id="8dc37-157">Make collaboration easier</span></span> | <span data-ttu-id="8dc37-158">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="8dc37-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="8dc37-159">Aumentar a produtividade de trabalhadores remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="8dc37-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="8dc37-160">Cargas de trabalho do Microsoft 365 e dados baseados em nuvem</span><span class="sxs-lookup"><span data-stu-id="8dc37-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="8dc37-161">Aumentar a criatividade e a inovação</span><span class="sxs-lookup"><span data-stu-id="8dc37-161">Increase creativity and innovation</span></span> | <span data-ttu-id="8dc37-162">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="8dc37-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="8dc37-163">Segurança</span><span class="sxs-lookup"><span data-stu-id="8dc37-163">Security</span></span> |  |  |
|  | <span data-ttu-id="8dc37-164">Gerenciamento de identidades e acesso</span><span class="sxs-lookup"><span data-stu-id="8dc37-164">Identity & access management</span></span> | <span data-ttu-id="8dc37-165">Contas dedicadas de administrador global com Azure AD Multi-Factor Authentication (MFA) e PIM (Azure AD Privileged Identity Management)</span><span class="sxs-lookup"><span data-stu-id="8dc37-165">Dedicated global administrator accounts with Azure AD Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="8dc37-166">Autenticação Multifator para todas as contas de usuário</span><span class="sxs-lookup"><span data-stu-id="8dc37-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="8dc37-167">Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="8dc37-167">Conditional Access</span></span> <BR> <span data-ttu-id="8dc37-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="8dc37-168">Windows Hello</span></span> <BR> <span data-ttu-id="8dc37-169">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="8dc37-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="8dc37-170">Proteção contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="8dc37-170">Threat protection</span></span> | <span data-ttu-id="8dc37-171">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="8dc37-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="8dc37-172">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="8dc37-172">Windows Defender</span></span> <BR> <span data-ttu-id="8dc37-173">O que é o Defender para Office 365?</span><span class="sxs-lookup"><span data-stu-id="8dc37-173">Defender for Office 365</span></span> <BR> <span data-ttu-id="8dc37-174">Obter o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="8dc37-174">Microsoft Defender for Office 365</span></span> <BR> <span data-ttu-id="8dc37-175">Investigação e resposta a ameaças do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8dc37-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="8dc37-176">Proteção de informações</span><span class="sxs-lookup"><span data-stu-id="8dc37-176">Information protection</span></span> | <span data-ttu-id="8dc37-177">Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="8dc37-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="8dc37-178">Prevenção de Perda de Dados (DLP)</span><span class="sxs-lookup"><span data-stu-id="8dc37-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="8dc37-179">Proteção de Informações do Windows (WIP)</span><span class="sxs-lookup"><span data-stu-id="8dc37-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="8dc37-180">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8dc37-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="8dc37-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8dc37-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="8dc37-182">Gerenciamento de segurança</span><span class="sxs-lookup"><span data-stu-id="8dc37-182">Security management</span></span> | <span data-ttu-id="8dc37-183">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="8dc37-183">Azure Defender</span></span>  <BR> <span data-ttu-id="8dc37-184">Central de Segurança do Windows Defender</span><span class="sxs-lookup"><span data-stu-id="8dc37-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="8dc37-185">Acesso remoto e móvel e parceiros de negócios</span><span class="sxs-lookup"><span data-stu-id="8dc37-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="8dc37-186">Aumentar a segurança de trabalhadores remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="8dc37-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="8dc37-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8dc37-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="8dc37-188">Reduzir a infraestrutura de acesso remoto para os trabalhadores</span><span class="sxs-lookup"><span data-stu-id="8dc37-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="8dc37-189">Cargas de trabalho do Microsoft 365 e dados baseados em nuvem</span><span class="sxs-lookup"><span data-stu-id="8dc37-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="8dc37-190">Melhorar a conectividade e reduzir a sobrecarga para transações B2B</span><span class="sxs-lookup"><span data-stu-id="8dc37-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="8dc37-191">Autenticação federada e recursos baseados em nuvem</span><span class="sxs-lookup"><span data-stu-id="8dc37-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="8dc37-192">Conformidade</span><span class="sxs-lookup"><span data-stu-id="8dc37-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="8dc37-193">Cumprir os requisitos regulamentares regionais</span><span class="sxs-lookup"><span data-stu-id="8dc37-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="8dc37-194">Recursos de RGPD no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8dc37-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="8dc37-195">Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="8dc37-195">Management</span></span> |  |  |
|  | <span data-ttu-id="8dc37-196">Menos sobrecarga de IT para instalar atualizações do cliente</span><span class="sxs-lookup"><span data-stu-id="8dc37-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="8dc37-197">Atualizações do Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8dc37-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="8dc37-198">Atualizações de Aplicativos do Microsoft 365 Apps para empresas</span><span class="sxs-lookup"><span data-stu-id="8dc37-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="8dc37-199">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="8dc37-199">Next step</span></span>

<span data-ttu-id="8dc37-200">Saiba mais sobre a rede local da Contoso Corporation e como ela foi otimizada para acesso e latência aos recursos [baseados](contoso-networking.md) em nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8dc37-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="8dc37-201">Confira também</span><span class="sxs-lookup"><span data-stu-id="8dc37-201">See also</span></span>

[<span data-ttu-id="8dc37-202">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="8dc37-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="8dc37-203">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="8dc37-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
