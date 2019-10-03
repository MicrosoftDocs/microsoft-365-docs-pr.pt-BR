---
title: Infraestrutura de TI e necessidades comerciais da Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda a estrutura básica da infraestrutura de TI local da Contoso e de que forma suas necessidades comerciais foram atendidas pelo Microsoft 365 Enterprise.
ms.openlocfilehash: d22763cede23d28c76a28c95a6e4772af81a996c
ms.sourcegitcommit: c6eab4a9f1b70e7ff0db6b2a1128a4db2591cbaf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37369582"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="581ce-103">Infraestrutura de TI e necessidades comerciais da Contoso</span><span class="sxs-lookup"><span data-stu-id="581ce-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="581ce-104">**Resumo:** Entenda a estrutura básica da infraestrutura de TI local da Contoso e de que forma suas necessidades comerciais foram atendidas pelo Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="581ce-104">**Summary:** Understand the basic structure of Contoso's on-premises IT infrastructure and how its business needs can be met by Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="581ce-105">A Contoso vem fazendo a transição de uma infraestrutura de TI centralizada local para uma infraestrutura incluindo nuvem que incorpora cargas de trabalho e aplicativos de produtividade pessoal baseados em nuvem.</span><span class="sxs-lookup"><span data-stu-id="581ce-105">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="581ce-106">Infraestrutura de TI da Contoso</span><span class="sxs-lookup"><span data-stu-id="581ce-106">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="581ce-107">A Contoso usa principalmente a infraestrutura de TI local centralizada, com datacenters de aplicativo na sede de Paris.</span><span class="sxs-lookup"><span data-stu-id="581ce-107">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="581ce-108">A Figura 1 mostra um escritório da sede com datacenters de aplicativo, uma DMZ e a Internet.</span><span class="sxs-lookup"><span data-stu-id="581ce-108">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![Infraestrutura de TI da Contoso](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="581ce-110">**Figura 1: Atual infraestrutura de TI da Contoso**</span><span class="sxs-lookup"><span data-stu-id="581ce-110">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="581ce-111">Os datacenters de aplicativo locais hospedam:</span><span class="sxs-lookup"><span data-stu-id="581ce-111">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="581ce-112">Linha personalizada de aplicativos de negócios que usam o SQL Server e outros bancos de dados do Linux.</span><span class="sxs-lookup"><span data-stu-id="581ce-112">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="581ce-113">Um conjunto de servidores herdados do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="581ce-113">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="581ce-114">Servidores de organização e nível de equipe para armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="581ce-114">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="581ce-115">Além disso, cada escritório central regional tem suporte para um conjunto de servidores com um conjunto semelhante de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="581ce-115">Additionally, each regional hub office that supports a set of servers with a similar set of applications. These servers are under the control of regional IT departments.</span></span> <span data-ttu-id="581ce-116">Esses servidores estão sob o controle dos departamentos regionais de TI.</span><span class="sxs-lookup"><span data-stu-id="581ce-116">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="581ce-117">A capacidade de pesquisa entre os aplicativos e dados desses datacenters multigeográficos continua sendo um desafio.</span><span class="sxs-lookup"><span data-stu-id="581ce-117">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="581ce-118">Na DMZ da sede da Contoso, diferentes conjuntos de servidores oferecem:</span><span class="sxs-lookup"><span data-stu-id="581ce-118">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="581ce-119">Hospedagem para o site público da Contoso, do qual os clientes podem solicitar produtos, peças, suprimentos ou serviço.</span><span class="sxs-lookup"><span data-stu-id="581ce-119">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="581ce-120">Hospedagem para a extranet do parceiro da Contoso para comunicação e colaboração do parceiro.</span><span class="sxs-lookup"><span data-stu-id="581ce-120">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="581ce-121">Acesso remoto baseado em rede privada virtual (VPN) à intranet da Contoso e proxy da Web para funcionários na sede de Paris.</span><span class="sxs-lookup"><span data-stu-id="581ce-121">VPN-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="581ce-122">Necessidades comerciais da Contoso</span><span class="sxs-lookup"><span data-stu-id="581ce-122">Contoso's business needs</span></span>

<span data-ttu-id="581ce-123">As necessidades comerciais da Contoso são classificadas em cinco categorias principais.</span><span class="sxs-lookup"><span data-stu-id="581ce-123">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="581ce-124">Produtividade:</span><span class="sxs-lookup"><span data-stu-id="581ce-124">Productivity:</span></span>

- <span data-ttu-id="581ce-125">Facilitar a colaboração</span><span class="sxs-lookup"><span data-stu-id="581ce-125">Make collaboration easier</span></span>

  <span data-ttu-id="581ce-126">Substitua a colaboração baseada em compartilhamento de emails e arquivos por um modelo online que permita alterações em tempo real em documentos, reuniões online simplificadas e threads de conversa capturados.</span><span class="sxs-lookup"><span data-stu-id="581ce-126">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="581ce-127">Aumentar a produtividade de trabalhadores remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="581ce-127">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="581ce-128">Com muitos funcionários trabalhando em casa ou em campo, substitua a solução de VPN com gargalo pelo acesso de alto desempenho aos dados e recursos da Contoso na nuvem.</span><span class="sxs-lookup"><span data-stu-id="581ce-128">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="581ce-129">Aumentar a criatividade e a inovação</span><span class="sxs-lookup"><span data-stu-id="581ce-129">Increase creativity and innovation</span></span>

  <span data-ttu-id="581ce-130">Aproveite os métodos mais recentes de aprendizado visual e desenvolvimento de ideias, incluindo tinta e visualização 3D.</span><span class="sxs-lookup"><span data-stu-id="581ce-130">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="581ce-131">Segurança:</span><span class="sxs-lookup"><span data-stu-id="581ce-131">Security:</span></span>

- <span data-ttu-id="581ce-132">Gerenciamento de identidades e acesso</span><span class="sxs-lookup"><span data-stu-id="581ce-132">Identity and access management</span></span>

  <span data-ttu-id="581ce-133">Implemente a autenticação multifator e outras formas de autenticação e proteja as credenciais das contas de usuário e administrador.</span><span class="sxs-lookup"><span data-stu-id="581ce-133">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="581ce-134">Proteção contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="581ce-134">Threat protection</span></span>

  <span data-ttu-id="581ce-135">Proteção contra ameaças externas, incluindo emails e malware com base no sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="581ce-135">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="581ce-136">Proteção de informações</span><span class="sxs-lookup"><span data-stu-id="581ce-136">Information protection</span></span>

  <span data-ttu-id="581ce-137">Bloqueie o acesso e criptografe ativos digitais de alto valor, como dados de clientes, especificações de design e fabricação e informações de funcionários.</span><span class="sxs-lookup"><span data-stu-id="581ce-137">Lock down access to and encrypt high-value digital assets, such as customer data, design specifications, and employee information.</span></span>

- <span data-ttu-id="581ce-138">Gerenciamento de segurança</span><span class="sxs-lookup"><span data-stu-id="581ce-138">Security management</span></span>

  <span data-ttu-id="581ce-139">Monitore a postura de segurança e detecte e responda a ameaças em tempo real.</span><span class="sxs-lookup"><span data-stu-id="581ce-139">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="581ce-140">Acesso remoto e móvel e parceiros de negócios:</span><span class="sxs-lookup"><span data-stu-id="581ce-140">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="581ce-141">Aumentar a segurança de trabalhadores remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="581ce-141">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="581ce-142">Estabeleça o BYOD (Traga seu próprio dispositivo) e o gerenciamento de dispositivos da empresa para garantir o acesso seguro, o comportamento correto do aplicativo e a proteção de dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="581ce-142">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="581ce-143">Reduzir a infraestrutura de acesso remoto para os trabalhadores</span><span class="sxs-lookup"><span data-stu-id="581ce-143">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="581ce-144">Reduza os custos de manutenção e suporte e melhore o desempenho da solução de acesso remoto, movendo recursos comumente acessados para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="581ce-144">Reduce maintenance and support costs and improve performance for remote access solution by moving resources commonly accessed to the cloud.</span></span>

- <span data-ttu-id="581ce-145">Fornecer conectividade aprimorada e sobrecarga mais baixa para transações B2B (entre empresas)</span><span class="sxs-lookup"><span data-stu-id="581ce-145">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="581ce-146">Substitua a extranet antiga e dispendiosa do parceiro por uma solução baseada em nuvem que use autenticação federada.</span><span class="sxs-lookup"><span data-stu-id="581ce-146">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="581ce-147">Conformidade:</span><span class="sxs-lookup"><span data-stu-id="581ce-147">Compliance:</span></span>

- <span data-ttu-id="581ce-148">Cumprir os requisitos regulamentares regionais</span><span class="sxs-lookup"><span data-stu-id="581ce-148">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="581ce-149">Entre e permaneça em conformidade com os regulamentos regionais e do setor de armazenamento de dados, criptografia, privacidade de dados e regulamentos de dados pessoais, como o Regulamento Geral sobre a Proteção de Dados (RGPD) da União Europeia.</span><span class="sxs-lookup"><span data-stu-id="581ce-149">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="581ce-150">Gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="581ce-150">Management:</span></span>

- <span data-ttu-id="581ce-151">Reduzir a sobrecarga de TI para gerenciar software executado em PCs e dispositivos de clientes</span><span class="sxs-lookup"><span data-stu-id="581ce-151">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="581ce-152">Automatize a instalação de atualizações no sistema operacional Windows e no Microsoft Office ProPlus em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="581ce-152">Automate the installation of updates to the Windows operating system and Microsoft Office across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="581ce-153">Mapear as necessidades comerciais da Contoso para o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="581ce-153">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="581ce-154">O departamento de TI da Contoso determinou o seguinte mapeamento das necessidades comerciais para os recursos do Microsoft 365 Enterprise E5 antes da implantação:</span><span class="sxs-lookup"><span data-stu-id="581ce-154">Contoso's IT department determined the following mapping of business needs to Microsoft 365 Enterprise E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="581ce-155">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="581ce-155">**Category**</span></span> | <span data-ttu-id="581ce-156">**Necessidade comercial**</span><span class="sxs-lookup"><span data-stu-id="581ce-156">**Business need**</span></span> | <span data-ttu-id="581ce-157">**Recursos e produtos do Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="581ce-157">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="581ce-158">Produtividade</span><span class="sxs-lookup"><span data-stu-id="581ce-158">Productivity</span></span> |  |  |
|  | <span data-ttu-id="581ce-159">Facilitar a colaboração</span><span class="sxs-lookup"><span data-stu-id="581ce-159">Make collaboration easier</span></span> | <span data-ttu-id="581ce-160">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="581ce-160">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="581ce-161">Aumentar a produtividade de trabalhadores remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="581ce-161">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="581ce-162">Cargas de trabalho do Microsoft 365 e dados baseados em nuvem</span><span class="sxs-lookup"><span data-stu-id="581ce-162">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="581ce-163">Aumentar a criatividade e a inovação</span><span class="sxs-lookup"><span data-stu-id="581ce-163">Increase creativity and innovation</span></span> | <span data-ttu-id="581ce-164">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="581ce-164">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="581ce-165">Segurança</span><span class="sxs-lookup"><span data-stu-id="581ce-165">Security</span></span> |  |  |
|  | <span data-ttu-id="581ce-166">Gerenciamento de identidades e acesso</span><span class="sxs-lookup"><span data-stu-id="581ce-166">Identity & access management</span></span> | <span data-ttu-id="581ce-167">Contas de administrador globais dedicadas com Autenticação Multifator do Azure e Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="581ce-167">Dedicated global administrator accounts with Multi-factor authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="581ce-168">Autenticação Multifator para todas as contas de usuário</span><span class="sxs-lookup"><span data-stu-id="581ce-168">MFA for all user accounts</span></span> <BR> <span data-ttu-id="581ce-169">Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="581ce-169">Conditional access</span></span> <BR> <span data-ttu-id="581ce-170">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="581ce-170">Windows Hello</span></span> <BR> <span data-ttu-id="581ce-171">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="581ce-171">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="581ce-172">Proteção contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="581ce-172">Threat protection</span></span> | <span data-ttu-id="581ce-173">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="581ce-173">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="581ce-174">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="581ce-174">Windows Defender</span></span> <BR> <span data-ttu-id="581ce-175">Proteção Avançada contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="581ce-175">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="581ce-176">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="581ce-176">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="581ce-177">Investigação e resposta a ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="581ce-177">Office 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="581ce-178">Proteção de informações</span><span class="sxs-lookup"><span data-stu-id="581ce-178">Information protection</span></span> | <span data-ttu-id="581ce-179">Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="581ce-179">Azure Information Protection</span></span> <BR> <span data-ttu-id="581ce-180">Prevenção contra Perda de Dados do Office 365</span><span class="sxs-lookup"><span data-stu-id="581ce-180">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="581ce-181">Proteção de Informações do Windows (WIP)</span><span class="sxs-lookup"><span data-stu-id="581ce-181">Windows Information Protection DataRecoveryCertificate</span></span> <BR> <span data-ttu-id="581ce-182">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="581ce-182">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="581ce-183">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="581ce-183">Microsoft Intune</span></span> |
|  | <span data-ttu-id="581ce-184">Gerenciamento de segurança</span><span class="sxs-lookup"><span data-stu-id="581ce-184">Security management</span></span> | <span data-ttu-id="581ce-185">Central de Segurança do Azure</span><span class="sxs-lookup"><span data-stu-id="581ce-185">Azure Security Center</span></span>  <BR> <span data-ttu-id="581ce-186">Central de Segurança do Windows Defender</span><span class="sxs-lookup"><span data-stu-id="581ce-186">Windows Defender Security Center</span></span> |
| <span data-ttu-id="581ce-187">Acesso remoto e móvel e parceiros de negócios</span><span class="sxs-lookup"><span data-stu-id="581ce-187">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="581ce-188">Aumentar a segurança de trabalhadores remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="581ce-188">Better security for remote and mobile workers</span></span> | <span data-ttu-id="581ce-189">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="581ce-189">Microsoft Intune</span></span> |
|  | <span data-ttu-id="581ce-190">Reduzir a infraestrutura de acesso remoto para os trabalhadores</span><span class="sxs-lookup"><span data-stu-id="581ce-190">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="581ce-191">Cargas de trabalho do Microsoft 365 e dados baseados em nuvem</span><span class="sxs-lookup"><span data-stu-id="581ce-191">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="581ce-192">Fornecer conectividade aprimorada e sobrecarga mais baixa para transações B2B</span><span class="sxs-lookup"><span data-stu-id="581ce-192">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="581ce-193">Autenticação federada e recursos baseados em nuvem</span><span class="sxs-lookup"><span data-stu-id="581ce-193">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="581ce-194">Conformidade</span><span class="sxs-lookup"><span data-stu-id="581ce-194">Compliance</span></span> |  |  |
|  | <span data-ttu-id="581ce-195">Cumprir os requisitos regulamentares regionais</span><span class="sxs-lookup"><span data-stu-id="581ce-195">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="581ce-196">Recursos de RGPD no Office 365</span><span class="sxs-lookup"><span data-stu-id="581ce-196">GDPR features in Office 365</span></span> |
| <span data-ttu-id="581ce-197">Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="581ce-197">Management</span></span> |  |  |
|  | <span data-ttu-id="581ce-198">Reduzir a sobrecarga da TI para instalar as atualizações do cliente</span><span class="sxs-lookup"><span data-stu-id="581ce-198">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="581ce-199">Anéis de implantação</span><span class="sxs-lookup"><span data-stu-id="581ce-199">Deployment rings</span></span> <BR> <span data-ttu-id="581ce-200">Atualizações do Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="581ce-200">Windows 10 Enterprise</span></span> <BR> <span data-ttu-id="581ce-201">Atualizações do Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="581ce-201">Office 365 ProPlus</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="581ce-202">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="581ce-202">Next step</span></span>

<span data-ttu-id="581ce-203">[Saiba mais](contoso-networking.md) sobre a rede local da Contoso Corporation e como ela foi otimizada para acesso e latência aos recursos baseados na nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="581ce-203">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="581ce-204">Confira também</span><span class="sxs-lookup"><span data-stu-id="581ce-204">See also</span></span>

[<span data-ttu-id="581ce-205">Guia de implantação</span><span class="sxs-lookup"><span data-stu-id="581ce-205">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="581ce-206">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="581ce-206">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
