---
title: Infraestrutura de TI e necessidades comerciais da Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda a infraestrutura básica da infraestrutura de TI local da Contoso e de que forma suas necessidades comerciais podem ser atendidas pelo Microsoft 365 Enterprise.
ms.openlocfilehash: bd259f367cdf3417e32671457f248029c853b6f8
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283669"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="c382e-103">Infraestrutura de TI e necessidades comerciais da Contoso</span><span class="sxs-lookup"><span data-stu-id="c382e-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="c382e-104">**Resumo:** entenda a infraestrutura básica da infraestrutura de TI local da Contoso e de que forma suas necessidades comerciais podem ser atendidas pelo Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c382e-104">**Summary:** Understand the basic structure of Contoso's on-premises IT infrastructure and how its business needs can be met by Microsoft 365 Enterprise.</span></span>


<span data-ttu-id="c382e-105">A Contoso vem fazendo a transição de uma infraestrutura de TI centralizada local para uma infraestrutura incluindo nuvem que incorpora cargas de trabalho e aplicativos de produtividade pessoal baseados em nuvem.</span><span class="sxs-lookup"><span data-stu-id="c382e-105">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="c382e-106">Infraestrutura de TI da Contoso</span><span class="sxs-lookup"><span data-stu-id="c382e-106">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="c382e-107">A Contoso usa principalmente a infraestrutura de TI local centralizada, com datacenters de aplicativo na sede de Paris.</span><span class="sxs-lookup"><span data-stu-id="c382e-107">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="c382e-108">A Figura 1 mostra um escritório da sede com datacenters de aplicativo, uma DMZ e a Internet.</span><span class="sxs-lookup"><span data-stu-id="c382e-108">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![](./media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="c382e-109">**Figura 1: Atual infraestrutura de TI da Contoso**</span><span class="sxs-lookup"><span data-stu-id="c382e-109">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="c382e-110">Os datacenters de aplicativo locais hospedam:</span><span class="sxs-lookup"><span data-stu-id="c382e-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="c382e-111">Linha personalizada de aplicativos de negócios que usam o SQL Server e outros bancos de dados do Linux.</span><span class="sxs-lookup"><span data-stu-id="c382e-111">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="c382e-112">Um conjunto de servidores herdados do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c382e-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="c382e-113">Servidores de organização e nível de equipe para armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="c382e-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="c382e-p101">Além disso, cada escritório de hub regional dá suporte a um conjunto de servidores com um conjunto semelhante de aplicativos. Esses servidores estão sob o controle dos departamentos de TI regionais.</span><span class="sxs-lookup"><span data-stu-id="c382e-p101">Additionally, each regional hub office that supports a set of servers with a similar set of applications. These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="c382e-116">A capacidade de pesquisa entre os aplicativos e dados desses datacenters multigeográficos continua sendo um desafio.</span><span class="sxs-lookup"><span data-stu-id="c382e-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="c382e-117">Na DMZ da sede da Contoso, diferentes conjuntos de servidores oferecem:</span><span class="sxs-lookup"><span data-stu-id="c382e-117">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="c382e-118">Acesso remoto baseado em VPN à intranet da Contoso e proxy Web para os funcionários na sede de Paris.</span><span class="sxs-lookup"><span data-stu-id="c382e-118">VPN-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>
- <span data-ttu-id="c382e-119">Hospedagem para o site público da Contoso, do qual os clientes podem solicitar produtos, peças, suprimentos ou serviço.</span><span class="sxs-lookup"><span data-stu-id="c382e-119">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="c382e-120">Hospedagem para a extranet do parceiro da Contoso para comunicação e colaboração do parceiro.</span><span class="sxs-lookup"><span data-stu-id="c382e-120">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="c382e-121">Necessidades comerciais da Contoso</span><span class="sxs-lookup"><span data-stu-id="c382e-121">Contoso's business needs</span></span>

<span data-ttu-id="c382e-122">As necessidades comerciais da Contoso são classificadas em cinco categorias principais.</span><span class="sxs-lookup"><span data-stu-id="c382e-122">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="c382e-123">Produtividade:</span><span class="sxs-lookup"><span data-stu-id="c382e-123">Productivity:</span></span>

- <span data-ttu-id="c382e-124">Facilitar a colaboração</span><span class="sxs-lookup"><span data-stu-id="c382e-124">Make collaboration easier</span></span>

  <span data-ttu-id="c382e-125">Substitua a colaboração baseada em compartilhamento de emails e arquivos por um modelo online que permita alterações em tempo real em documentos, reuniões online simplificadas e threads de conversa capturados.</span><span class="sxs-lookup"><span data-stu-id="c382e-125">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="c382e-126">Aumentar a produtividade de trabalhadores remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="c382e-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="c382e-127">Com muitos funcionários trabalhando em casa ou em campo, substitua a solução de VPN com gargalo pelo acesso de alto desempenho aos dados e recursos da Contoso na nuvem.</span><span class="sxs-lookup"><span data-stu-id="c382e-127">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="c382e-128">Aumentar a criatividade e a inovação</span><span class="sxs-lookup"><span data-stu-id="c382e-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="c382e-129">Aproveite os métodos mais recentes de aprendizado visual e desenvolvimento de ideias, incluindo tinta e visualização 3D.</span><span class="sxs-lookup"><span data-stu-id="c382e-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="c382e-130">Segurança:</span><span class="sxs-lookup"><span data-stu-id="c382e-130">Security:</span></span>

- <span data-ttu-id="c382e-131">Gerenciamento de identidades e acesso</span><span class="sxs-lookup"><span data-stu-id="c382e-131">Identity and access management</span></span>

  <span data-ttu-id="c382e-132">Implemente a autenticação multifator e outras formas de autenticação e proteja as credenciais das contas de usuário e administrador.</span><span class="sxs-lookup"><span data-stu-id="c382e-132">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="c382e-133">Proteção contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="c382e-133">Threat protection</span></span>

  <span data-ttu-id="c382e-134">Proteção contra ameaças externas, incluindo emails e malware com base no sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="c382e-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="c382e-135">Proteção de Informações</span><span class="sxs-lookup"><span data-stu-id="c382e-135">Information protection</span></span>

  <span data-ttu-id="c382e-136">Bloqueie o acesso e criptografe ativos digitais de alto valor, como dados de clientes, especificações de design e informações sobre funcionários.</span><span class="sxs-lookup"><span data-stu-id="c382e-136">Lock down access to and encrypt high-value digital assets, such as customer data, design specifications, and employee information.</span></span>

- <span data-ttu-id="c382e-137">Gerenciamento de segurança</span><span class="sxs-lookup"><span data-stu-id="c382e-137">Security management</span></span>

  <span data-ttu-id="c382e-138">Monitore a postura de segurança e detecte e responda a ameaças em tempo real.</span><span class="sxs-lookup"><span data-stu-id="c382e-138">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="c382e-139">Acesso remoto e móvel e parceiros de negócios:</span><span class="sxs-lookup"><span data-stu-id="c382e-139">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="c382e-140">Aumentar a segurança de trabalhadores remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="c382e-140">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="c382e-141">Estabeleça o BYOD (Traga seu próprio dispositivo) e o gerenciamento de dispositivos da empresa para garantir o acesso seguro, o comportamento correto do aplicativo e a proteção de dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="c382e-141">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="c382e-142">Reduzir a infraestrutura de acesso remoto para os trabalhadores</span><span class="sxs-lookup"><span data-stu-id="c382e-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="c382e-143">Reduza os custos de manutenção e suporte e melhore o desempenho da solução de acesso remoto, movendo recursos comumente acessados para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="c382e-143">Reduce maintenance and support costs and improve performance for remote access solution by moving resources commonly accessed to the cloud.</span></span>

- <span data-ttu-id="c382e-144">Fornecer conectividade aprimorada e sobrecarga mais baixa para transações B2B (entre empresas)</span><span class="sxs-lookup"><span data-stu-id="c382e-144">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="c382e-145">Substitua a extranet antiga e dispendiosa do parceiro por uma solução baseada em nuvem que use autenticação federada.</span><span class="sxs-lookup"><span data-stu-id="c382e-145">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="c382e-146">Conformidade:</span><span class="sxs-lookup"><span data-stu-id="c382e-146">Compliance:</span></span>

- <span data-ttu-id="c382e-147">Cumprir os requisitos regulamentares regionais</span><span class="sxs-lookup"><span data-stu-id="c382e-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="c382e-148">Entre e permaneça em conformidade com os regulamentos regionais e do setor de armazenamento de dados, criptografia, privacidade de dados e regulamentos de dados pessoais, como o Regulamento Geral sobre a Proteção de Dados (RGPD) da União Europeia.</span><span class="sxs-lookup"><span data-stu-id="c382e-148">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="c382e-149">Gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="c382e-149">Management:</span></span>

- <span data-ttu-id="c382e-150">Reduzir a sobrecarga de TI para gerenciar software executado em PCs e dispositivos de clientes</span><span class="sxs-lookup"><span data-stu-id="c382e-150">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="c382e-151">Automatize a instalação de atualizações no sistema operacional Windows e no Microsoft Office em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="c382e-151">Automate the installation of updates to the Windows operating system and Microsoft Office across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="c382e-152">Mapear as necessidades comerciais da Contoso para o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c382e-152">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c382e-153">O departamento de TI da Contoso determinou o seguinte mapeamento das necessidades comerciais para os recursos do Microsoft 365 Enterprise E5 antes da implantação:</span><span class="sxs-lookup"><span data-stu-id="c382e-153">Contoso's IT department determined the following mapping of business needs to Microsoft 365 Enterprise E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="c382e-154">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="c382e-154">**Category**</span></span> | <span data-ttu-id="c382e-155">**Necessidade comercial**</span><span class="sxs-lookup"><span data-stu-id="c382e-155">**Business need**</span></span> | <span data-ttu-id="c382e-156">**Recursos e produtos do Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="c382e-156">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="c382e-157">Produtividade</span><span class="sxs-lookup"><span data-stu-id="c382e-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="c382e-158">Facilitar a colaboração</span><span class="sxs-lookup"><span data-stu-id="c382e-158">Make collaboration easier</span></span> | <span data-ttu-id="c382e-159">Teams, SharePoint Online, Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c382e-159">Teams, SharePoint Online, Skype for Business Online</span></span> |
|  | <span data-ttu-id="c382e-160">Aumentar a produtividade de trabalhadores remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="c382e-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="c382e-161">Dados baseados em nuvem e cargas de trabalho do Office 365</span><span class="sxs-lookup"><span data-stu-id="c382e-161">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="c382e-162">Aumentar a criatividade e a inovação</span><span class="sxs-lookup"><span data-stu-id="c382e-162">Increase creativity and innovation</span></span> | <span data-ttu-id="c382e-163">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c382e-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="c382e-164">Segurança</span><span class="sxs-lookup"><span data-stu-id="c382e-164">Security</span></span> |  |  |
|  | <span data-ttu-id="c382e-165">Gerenciamento de identidades e acesso</span><span class="sxs-lookup"><span data-stu-id="c382e-165">Identity & access management</span></span> | <span data-ttu-id="c382e-166">Contas de administrador globais dedicadas com autenticação multifator e Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="c382e-166">Dedicated global administrator accounts with Multi-factor authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="c382e-167">Autenticação multifator para todas as contas de usuários</span><span class="sxs-lookup"><span data-stu-id="c382e-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="c382e-168">Acesso condicional</span><span class="sxs-lookup"><span data-stu-id="c382e-168">Conditional access</span></span> <BR> <span data-ttu-id="c382e-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="c382e-169">Windows Hello</span></span> <BR> <span data-ttu-id="c382e-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="c382e-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="c382e-171">Proteção contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="c382e-171">Threat protection</span></span> | <span data-ttu-id="c382e-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="c382e-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="c382e-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="c382e-173">Windows Defender</span></span> <BR> <span data-ttu-id="c382e-174">Proteção Avançada contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="c382e-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="c382e-175">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="c382e-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="c382e-176">Investigação e resposta a ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="c382e-176">Office 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="c382e-177">Proteção de informações</span><span class="sxs-lookup"><span data-stu-id="c382e-177">Information protection</span></span> | <span data-ttu-id="c382e-178">Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="c382e-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="c382e-179">Prevenção contra Perda de Dados do Office 365</span><span class="sxs-lookup"><span data-stu-id="c382e-179">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="c382e-180">Proteção de Informações do Windows</span><span class="sxs-lookup"><span data-stu-id="c382e-180">Windows Information Protection</span></span> <BR> <span data-ttu-id="c382e-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="c382e-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="c382e-182">Office 365 Cloud App Security (CAS)</span><span class="sxs-lookup"><span data-stu-id="c382e-182">Office 365 Cloud App Security (CAS)</span></span> <BR> <span data-ttu-id="c382e-183">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c382e-183">Microsoft Intune</span></span> |
|  | <span data-ttu-id="c382e-184">Gerenciamento de segurança</span><span class="sxs-lookup"><span data-stu-id="c382e-184">Security management</span></span> | <span data-ttu-id="c382e-185">Central de Segurança do Azure</span><span class="sxs-lookup"><span data-stu-id="c382e-185">Azure Security Center</span></span>  <BR> <span data-ttu-id="c382e-186">Central de Segurança do Windows Defender</span><span class="sxs-lookup"><span data-stu-id="c382e-186">Windows Defender Security Center</span></span> |
| <span data-ttu-id="c382e-187">Acesso remoto e móvel e parceiros de negócios</span><span class="sxs-lookup"><span data-stu-id="c382e-187">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="c382e-188">Aumentar a segurança de trabalhadores remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="c382e-188">Better security for remote and mobile workers</span></span> | <span data-ttu-id="c382e-189">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c382e-189">Microsoft Intune</span></span> |
|  | <span data-ttu-id="c382e-190">Reduzir a infraestrutura de acesso remoto para os trabalhadores</span><span class="sxs-lookup"><span data-stu-id="c382e-190">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="c382e-191">Dados baseados em nuvem e cargas de trabalho do Office 365</span><span class="sxs-lookup"><span data-stu-id="c382e-191">Office 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="c382e-192">Fornecer conectividade aprimorada e sobrecarga mais baixa para transações B2B</span><span class="sxs-lookup"><span data-stu-id="c382e-192">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="c382e-193">Autenticação federada e recursos baseados em nuvem</span><span class="sxs-lookup"><span data-stu-id="c382e-193">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="c382e-194">Conformidade</span><span class="sxs-lookup"><span data-stu-id="c382e-194">Compliance</span></span> |  |  |
|  | <span data-ttu-id="c382e-195">Cumprir os requisitos regulamentares regionais</span><span class="sxs-lookup"><span data-stu-id="c382e-195">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="c382e-196">Recursos de RGPD no Office 365</span><span class="sxs-lookup"><span data-stu-id="c382e-196">GDPR features in Office 365</span></span> |
| <span data-ttu-id="c382e-197">Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="c382e-197">Management</span></span> |  |  |
|  | <span data-ttu-id="c382e-198">Reduzir a sobrecarga da TI para instalar as atualizações do cliente</span><span class="sxs-lookup"><span data-stu-id="c382e-198">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="c382e-199">Anéis de implantação</span><span class="sxs-lookup"><span data-stu-id="c382e-199">Deployment rings</span></span> <BR> <span data-ttu-id="c382e-200">Atualização local do Windows 10 e Autopilot</span><span class="sxs-lookup"><span data-stu-id="c382e-200">Windows 10 upgrade in place and Autopilot</span></span> <BR> <span data-ttu-id="c382e-201">Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="c382e-201">Office 365 ProPlus</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="c382e-202">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="c382e-202">Next step</span></span>

<span data-ttu-id="c382e-203">[Saiba mais](contoso-networking.md) sobre a rede local da Contoso Corporation e como ela foi otimizada para latência e acesso aos recursos baseados em nuvem do Microsoft 365 em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="c382e-203">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="c382e-204">Confira também</span><span class="sxs-lookup"><span data-stu-id="c382e-204">See also</span></span>

[<span data-ttu-id="c382e-205">Guia de implantação</span><span class="sxs-lookup"><span data-stu-id="c382e-205">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="c382e-206">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="c382e-206">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
