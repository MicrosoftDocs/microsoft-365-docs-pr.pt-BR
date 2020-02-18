---
title: Infraestrutura de TI e necessidades comerciais da Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 3cee0f3e6cd20b0d93038595cdab9270c8eb30aa
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42068378"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="9e33f-103">Infraestrutura de TI e necessidades comerciais da Contoso</span><span class="sxs-lookup"><span data-stu-id="9e33f-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="9e33f-104">A Contoso vem fazendo a transição de uma infraestrutura de TI centralizada local para uma infraestrutura incluindo nuvem que incorpora cargas de trabalho e aplicativos de produtividade pessoal baseados em nuvem.</span><span class="sxs-lookup"><span data-stu-id="9e33f-104">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="9e33f-105">Infraestrutura de TI da Contoso</span><span class="sxs-lookup"><span data-stu-id="9e33f-105">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="9e33f-106">A Contoso usa principalmente a infraestrutura de TI local centralizada, com datacenters de aplicativo na sede de Paris.</span><span class="sxs-lookup"><span data-stu-id="9e33f-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="9e33f-107">A Figura 1 mostra um escritório da sede com datacenters de aplicativo, uma DMZ e a Internet.</span><span class="sxs-lookup"><span data-stu-id="9e33f-107">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![Infraestrutura de TI da Contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="9e33f-109">**Figura 1: Atual infraestrutura de TI da Contoso**</span><span class="sxs-lookup"><span data-stu-id="9e33f-109">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="9e33f-110">Os datacenters de aplicativo locais hospedam:</span><span class="sxs-lookup"><span data-stu-id="9e33f-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="9e33f-111">Linha personalizada de aplicativos de negócios que usam o SQL Server e outros bancos de dados do Linux.</span><span class="sxs-lookup"><span data-stu-id="9e33f-111">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="9e33f-112">Um conjunto de servidores herdados do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9e33f-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="9e33f-113">Servidores de organização e nível de equipe para armazenamento de arquivos.</span><span class="sxs-lookup"><span data-stu-id="9e33f-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="9e33f-114">Além disso, cada escritório central regional tem suporte para um conjunto de servidores com um conjunto semelhante de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="9e33f-114">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="9e33f-115">Esses servidores estão sob o controle dos departamentos regionais de TI.</span><span class="sxs-lookup"><span data-stu-id="9e33f-115">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="9e33f-116">A capacidade de pesquisa entre os aplicativos e dados desses datacenters multigeográficos continua sendo um desafio.</span><span class="sxs-lookup"><span data-stu-id="9e33f-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="9e33f-117">Na DMZ da sede da Contoso, diferentes conjuntos de servidores oferecem:</span><span class="sxs-lookup"><span data-stu-id="9e33f-117">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="9e33f-118">Hospedagem para o site público da Contoso, do qual os clientes podem solicitar produtos, peças, suprimentos ou serviço.</span><span class="sxs-lookup"><span data-stu-id="9e33f-118">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="9e33f-119">Hospedagem para a extranet do parceiro da Contoso para comunicação e colaboração do parceiro.</span><span class="sxs-lookup"><span data-stu-id="9e33f-119">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="9e33f-120">Acesso remoto baseado em rede privada virtual (VPN) à intranet da Contoso e proxy da Web para funcionários na sede de Paris.</span><span class="sxs-lookup"><span data-stu-id="9e33f-120">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="9e33f-121">Necessidades comerciais da Contoso</span><span class="sxs-lookup"><span data-stu-id="9e33f-121">Contoso's business needs</span></span>

<span data-ttu-id="9e33f-122">As necessidades comerciais da Contoso são classificadas em cinco categorias principais.</span><span class="sxs-lookup"><span data-stu-id="9e33f-122">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="9e33f-123">Produtividade:</span><span class="sxs-lookup"><span data-stu-id="9e33f-123">Productivity:</span></span>

- <span data-ttu-id="9e33f-124">Facilitar a colaboração</span><span class="sxs-lookup"><span data-stu-id="9e33f-124">Make collaboration easier</span></span>

  <span data-ttu-id="9e33f-125">Substitua a colaboração baseada em compartilhamento de emails e arquivos por um modelo online que permita alterações em tempo real em documentos, reuniões online simplificadas e threads de conversa capturados.</span><span class="sxs-lookup"><span data-stu-id="9e33f-125">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="9e33f-126">Aumentar a produtividade de trabalhadores remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="9e33f-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="9e33f-127">Com muitos funcionários trabalhando em casa ou em campo, substitua a solução de VPN com gargalo pelo acesso de alto desempenho aos dados e recursos da Contoso na nuvem.</span><span class="sxs-lookup"><span data-stu-id="9e33f-127">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="9e33f-128">Aumentar a criatividade e a inovação</span><span class="sxs-lookup"><span data-stu-id="9e33f-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="9e33f-129">Aproveite os métodos mais recentes de aprendizado visual e desenvolvimento de ideias, incluindo tinta e visualização 3D.</span><span class="sxs-lookup"><span data-stu-id="9e33f-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="9e33f-130">Segurança:</span><span class="sxs-lookup"><span data-stu-id="9e33f-130">Security:</span></span>

- <span data-ttu-id="9e33f-131">Gerenciamento de identidades e acesso</span><span class="sxs-lookup"><span data-stu-id="9e33f-131">Identity and access management</span></span>

  <span data-ttu-id="9e33f-132">Implemente a autenticação multifator e outras formas de autenticação e proteja as credenciais das contas de usuário e administrador.</span><span class="sxs-lookup"><span data-stu-id="9e33f-132">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="9e33f-133">Proteção contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="9e33f-133">Threat protection</span></span>

  <span data-ttu-id="9e33f-134">Proteção contra ameaças externas, incluindo emails e malware com base no sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="9e33f-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="9e33f-135">Proteção de informações</span><span class="sxs-lookup"><span data-stu-id="9e33f-135">Information protection</span></span>

  <span data-ttu-id="9e33f-136">Bloqueie o acesso e criptografe ativos digitais de alto valor, como dados de clientes, especificações de design e fabricação e informações de funcionários.</span><span class="sxs-lookup"><span data-stu-id="9e33f-136">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="9e33f-137">Gerenciamento de segurança</span><span class="sxs-lookup"><span data-stu-id="9e33f-137">Security management</span></span>

  <span data-ttu-id="9e33f-138">Monitore a postura de segurança e detecte e responda a ameaças em tempo real.</span><span class="sxs-lookup"><span data-stu-id="9e33f-138">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="9e33f-139">Acesso remoto e móvel e parceiros de negócios:</span><span class="sxs-lookup"><span data-stu-id="9e33f-139">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="9e33f-140">Aumentar a segurança de trabalhadores remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="9e33f-140">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="9e33f-141">Estabeleça o BYOD (Traga seu próprio dispositivo) e o gerenciamento de dispositivos da empresa para garantir o acesso seguro, o comportamento correto do aplicativo e a proteção de dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="9e33f-141">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="9e33f-142">Reduzir a infraestrutura de acesso remoto para os trabalhadores</span><span class="sxs-lookup"><span data-stu-id="9e33f-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="9e33f-143">Reduza os custos de manutenção e suporte e melhore o desempenho da solução de acesso remoto, movendo recursos comumente acessados para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="9e33f-143">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly-accessed resources to the cloud.</span></span>

- <span data-ttu-id="9e33f-144">Fornecer conectividade aprimorada e sobrecarga mais baixa para transações B2B (entre empresas)</span><span class="sxs-lookup"><span data-stu-id="9e33f-144">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="9e33f-145">Substitua a extranet antiga e dispendiosa do parceiro por uma solução baseada em nuvem que use autenticação federada.</span><span class="sxs-lookup"><span data-stu-id="9e33f-145">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="9e33f-146">Conformidade:</span><span class="sxs-lookup"><span data-stu-id="9e33f-146">Compliance:</span></span>

- <span data-ttu-id="9e33f-147">Cumprir os requisitos regulamentares regionais</span><span class="sxs-lookup"><span data-stu-id="9e33f-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="9e33f-148">Entre e permaneça em conformidade com os regulamentos regionais e do setor de armazenamento de dados, criptografia, privacidade de dados e regulamentos de dados pessoais, como o Regulamento Geral sobre a Proteção de Dados (RGPD) da União Europeia.</span><span class="sxs-lookup"><span data-stu-id="9e33f-148">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="9e33f-149">Gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="9e33f-149">Management:</span></span>

- <span data-ttu-id="9e33f-150">Reduzir a sobrecarga de TI para gerenciar software executado em PCs e dispositivos de clientes</span><span class="sxs-lookup"><span data-stu-id="9e33f-150">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="9e33f-151">Automatize a instalação de atualizações no sistema operacional Windows e no Microsoft Office ProPlus em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="9e33f-151">Automate the installation of updates to the Windows operating system and Microsoft Office ProPlus across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-enterprise"></a><span data-ttu-id="9e33f-152">Mapear as necessidades comerciais da Contoso para o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9e33f-152">Mapping Contoso's business needs to Microsoft 365 Enterprise</span></span>

<span data-ttu-id="9e33f-153">O departamento de TI da Contoso determinou o seguinte mapeamento das necessidades comerciais dos recursos do Microsoft 365 E5 antes da implantação:</span><span class="sxs-lookup"><span data-stu-id="9e33f-153">Contoso's IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="9e33f-154">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="9e33f-154">**Category**</span></span> | <span data-ttu-id="9e33f-155">**Necessidade comercial**</span><span class="sxs-lookup"><span data-stu-id="9e33f-155">**Business need**</span></span> | <span data-ttu-id="9e33f-156">**Recursos e produtos do Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="9e33f-156">**Microsoft 365 Enterprise products or features**</span></span> |
| <span data-ttu-id="9e33f-157">Produtividade</span><span class="sxs-lookup"><span data-stu-id="9e33f-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="9e33f-158">Facilitar a colaboração</span><span class="sxs-lookup"><span data-stu-id="9e33f-158">Make collaboration easier</span></span> | <span data-ttu-id="9e33f-159">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="9e33f-159">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="9e33f-160">Aumentar a produtividade de trabalhadores remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="9e33f-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="9e33f-161">Cargas de trabalho do Microsoft 365 e dados baseados em nuvem</span><span class="sxs-lookup"><span data-stu-id="9e33f-161">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="9e33f-162">Aumentar a criatividade e a inovação</span><span class="sxs-lookup"><span data-stu-id="9e33f-162">Increase creativity and innovation</span></span> | <span data-ttu-id="9e33f-163">Windows Ink, Cortana at Work, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="9e33f-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="9e33f-164">Segurança</span><span class="sxs-lookup"><span data-stu-id="9e33f-164">Security</span></span> |  |  |
|  | <span data-ttu-id="9e33f-165">Gerenciamento de identidades e acesso</span><span class="sxs-lookup"><span data-stu-id="9e33f-165">Identity & access management</span></span> | <span data-ttu-id="9e33f-166">Contas de administrador globais dedicadas com Autenticação Multifator do Azure e Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="9e33f-166">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="9e33f-167">Autenticação Multifator para todas as contas de usuário</span><span class="sxs-lookup"><span data-stu-id="9e33f-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="9e33f-168">Acesso Condicional</span><span class="sxs-lookup"><span data-stu-id="9e33f-168">Conditional Access</span></span> <BR> <span data-ttu-id="9e33f-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="9e33f-169">Windows Hello</span></span> <BR> <span data-ttu-id="9e33f-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="9e33f-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="9e33f-171">Proteção contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="9e33f-171">Threat protection</span></span> | <span data-ttu-id="9e33f-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="9e33f-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="9e33f-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="9e33f-173">Windows Defender</span></span> <BR> <span data-ttu-id="9e33f-174">Proteção Avançada contra Ameaças</span><span class="sxs-lookup"><span data-stu-id="9e33f-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="9e33f-175">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="9e33f-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="9e33f-176">Investigação e resposta a ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="9e33f-176">Office 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="9e33f-177">Proteção de informações</span><span class="sxs-lookup"><span data-stu-id="9e33f-177">Information protection</span></span> | <span data-ttu-id="9e33f-178">Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="9e33f-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="9e33f-179">Prevenção contra Perda de Dados do Office 365</span><span class="sxs-lookup"><span data-stu-id="9e33f-179">Office 365 Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="9e33f-180">Proteção de Informações do Windows (WIP)</span><span class="sxs-lookup"><span data-stu-id="9e33f-180">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="9e33f-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="9e33f-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="9e33f-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9e33f-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="9e33f-183">Gerenciamento de segurança</span><span class="sxs-lookup"><span data-stu-id="9e33f-183">Security management</span></span> | <span data-ttu-id="9e33f-184">Central de Segurança do Azure</span><span class="sxs-lookup"><span data-stu-id="9e33f-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="9e33f-185">Central de Segurança do Windows Defender</span><span class="sxs-lookup"><span data-stu-id="9e33f-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="9e33f-186">Acesso remoto e móvel e parceiros de negócios</span><span class="sxs-lookup"><span data-stu-id="9e33f-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="9e33f-187">Aumentar a segurança de trabalhadores remotos e móveis</span><span class="sxs-lookup"><span data-stu-id="9e33f-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="9e33f-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9e33f-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="9e33f-189">Reduzir a infraestrutura de acesso remoto para os trabalhadores</span><span class="sxs-lookup"><span data-stu-id="9e33f-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="9e33f-190">Cargas de trabalho do Microsoft 365 e dados baseados em nuvem</span><span class="sxs-lookup"><span data-stu-id="9e33f-190">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="9e33f-191">Fornecer conectividade aprimorada e sobrecarga mais baixa para transações B2B</span><span class="sxs-lookup"><span data-stu-id="9e33f-191">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="9e33f-192">Autenticação federada e recursos baseados em nuvem</span><span class="sxs-lookup"><span data-stu-id="9e33f-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="9e33f-193">Conformidade</span><span class="sxs-lookup"><span data-stu-id="9e33f-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="9e33f-194">Cumprir os requisitos regulamentares regionais</span><span class="sxs-lookup"><span data-stu-id="9e33f-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="9e33f-195">Recursos de RGPD no Office 365</span><span class="sxs-lookup"><span data-stu-id="9e33f-195">GDPR features in Office 365</span></span> |
| <span data-ttu-id="9e33f-196">Gerenciamento</span><span class="sxs-lookup"><span data-stu-id="9e33f-196">Management</span></span> |  |  |
|  | <span data-ttu-id="9e33f-197">Reduzir a sobrecarga da TI para instalar as atualizações do cliente</span><span class="sxs-lookup"><span data-stu-id="9e33f-197">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="9e33f-198">Anéis de implantação</span><span class="sxs-lookup"><span data-stu-id="9e33f-198">Deployment rings</span></span> <BR> <span data-ttu-id="9e33f-199">Atualizações do Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="9e33f-199">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="9e33f-200">Atualizações do Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="9e33f-200">Office 365 ProPlus updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="9e33f-201">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="9e33f-201">Next step</span></span>

<span data-ttu-id="9e33f-202">[Saiba mais](contoso-networking.md) sobre a rede local da Contoso Corporation e como ela foi otimizada para acesso e latência aos recursos baseados na nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9e33f-202">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e33f-203">Confira também</span><span class="sxs-lookup"><span data-stu-id="9e33f-203">See also</span></span>

[<span data-ttu-id="9e33f-204">Guia de implantação</span><span class="sxs-lookup"><span data-stu-id="9e33f-204">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="9e33f-205">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="9e33f-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
