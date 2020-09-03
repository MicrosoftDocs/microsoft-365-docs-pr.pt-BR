---
title: Controles de acesso administrativo no Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- NOCSH
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Este artigo fornece uma visão geral dos controles de acesso administrativo e da categorização de dados no Microsoft 365.
ms.openlocfilehash: 817a5907566435d021fe78d89b5c9476c04318d0
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332587"
---
# <a name="administrative-access-controls-in-microsoft-365"></a><span data-ttu-id="cf65a-103">Controles de acesso administrativo no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf65a-103">Administrative access controls in Microsoft 365</span></span> 

<span data-ttu-id="cf65a-104">A Microsoft investiu pesadamente em sistemas e controles que automatizam a maioria das operações do Microsoft 365 enquanto limitava intencionalmente o acesso ao conteúdo do cliente pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf65a-104">Microsoft has invested heavily in systems and controls that automate most Microsoft 365 operations while intentionally limiting access to customer content by Microsoft.</span></span> <span data-ttu-id="cf65a-105">Os seres humanos governam o serviço e o software opera o serviço.</span><span class="sxs-lookup"><span data-stu-id="cf65a-105">Humans govern the service, and software operates the service.</span></span> <span data-ttu-id="cf65a-106">Isso permite que a Microsoft gerencie o Microsoft 365 em escala e gerencie os riscos de ameaças internas ao conteúdo do cliente.</span><span class="sxs-lookup"><span data-stu-id="cf65a-106">This enables Microsoft to manage Microsoft 365 at scale and manage the risks of internal threats to customer content.</span></span>

<span data-ttu-id="cf65a-107">Por padrão, os engenheiros da Microsoft têm nenhum privilégio administrativo de pé e zero acesso de pé ao conteúdo do cliente no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf65a-107">By default, Microsoft engineers have zero standing administrative privileges and zero standing access to customer content in Microsoft 365.</span></span> <span data-ttu-id="cf65a-108">Um engenheiro da Microsoft pode ter acesso limitado, auditado e protegido ao conteúdo de um cliente por um período limitado de tempo.</span><span class="sxs-lookup"><span data-stu-id="cf65a-108">A Microsoft engineer can have limited, audited, and secured access to a customer's content for a limited amount of time.</span></span> <span data-ttu-id="cf65a-109">O acesso é apenas quando necessário para operações de serviço e somente quando aprovado por um membro do gerenciamento sênior da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf65a-109">Access is only when necessary for service operations and only when approved by a member of Microsoft senior management.</span></span> <span data-ttu-id="cf65a-110">Para clientes licenciados de lockbox de clientes, o cliente fornece aprovação de acesso para seu conteúdo hospedado no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf65a-110">For Customer Lockbox licensed customers, the customer provides access approval to their content hosted on Microsoft 365.</span></span>

<span data-ttu-id="cf65a-111">A Microsoft fornece serviços online usando várias formas de entrega na nuvem:</span><span class="sxs-lookup"><span data-stu-id="cf65a-111">Microsoft provides online services using multiple forms of cloud delivery:</span></span>

- <span data-ttu-id="cf65a-112">**Nuvens públicas:** Inclui versões de vários locatários do Microsoft 365, Azure e outros serviços hospedados na América do Norte, América do Sul, Europa, Ásia, Austrália, etc.</span><span class="sxs-lookup"><span data-stu-id="cf65a-112">**Public clouds:** Includes multi-tenant versions of Microsoft 365, Azure, and other services hosted in North America, South America, Europe, Asia, Australia, etc.</span></span>
- <span data-ttu-id="cf65a-113">**Nuvens nacionais:** Inclui todas as nuvens soberana e operadas por terceiros fora dos Estados Unidos (exceto aqueles observados anteriormente), como o Microsoft 365 na China (operado pela 21Vianet) e a Microsoft 365 na Alemanha (operada pela Microsoft, mas em um modelo no qual um data de confiança de dados em alemão, alemães Telekom, controla e monitora o acesso da Microsoft aos dados e sistemas de clientes que contêm dados</span><span class="sxs-lookup"><span data-stu-id="cf65a-113">**National clouds:** Includes all sovereign and third party-operated clouds outside of the United States (except ones noted previously), such as Microsoft 365 in China (operated by 21Vianet), and Microsoft 365 in Germany (operated by Microsoft, but under a model in which a German data trustee, Deutsche Telekom, controls and monitors Microsoft's access to customer data and systems that contain customer data).</span></span>
- <span data-ttu-id="cf65a-114">**Nuvens governamentais:** Inclui os serviços do Microsoft 365 e do Azure que estão disponíveis para os clientes do governo dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="cf65a-114">**Government clouds:** Includes Microsoft 365 and Azure services that are available to United States government customers.</span></span>

<span data-ttu-id="cf65a-115">Para os fins deste artigo, os serviços do Microsoft 365 incluem:</span><span class="sxs-lookup"><span data-stu-id="cf65a-115">For purposes of this article, Microsoft 365 services include:</span></span>

- [<span data-ttu-id="cf65a-116">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cf65a-116">Exchange Online</span></span>](https://docs.microsoft.com/Exchange/exchange-online)
- [<span data-ttu-id="cf65a-117">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cf65a-117">Exchange Online Protection</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)
- [<span data-ttu-id="cf65a-118">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cf65a-118">SharePoint Online</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-online)
- [<span data-ttu-id="cf65a-119">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="cf65a-119">OneDrive for Business</span></span>](https://docs.microsoft.com/OneDrive/onedrive)
- [<span data-ttu-id="cf65a-120">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="cf65a-120">Skype for Business</span></span>](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)
- [<span data-ttu-id="cf65a-121">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cf65a-121">Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
- [<span data-ttu-id="cf65a-122">Yammer</span><span class="sxs-lookup"><span data-stu-id="cf65a-122">Yammer</span></span>](https://docs.microsoft.com/yammer/yammer-landing-page)

## <a name="microsoft-365-access-controls"></a><span data-ttu-id="cf65a-123">Controles de acesso do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cf65a-123">Microsoft 365 access controls</span></span>

<span data-ttu-id="cf65a-124">Para fins de controle de acesso, a Microsoft categoriza os dados do Microsoft 365 como dados do cliente ou outros tipos de dados.</span><span class="sxs-lookup"><span data-stu-id="cf65a-124">For access control purposes, Microsoft categorizes Microsoft 365 data as customer data or other types of data.</span></span>

### <a name="customer-data"></a><span data-ttu-id="cf65a-125">Dados do cliente</span><span class="sxs-lookup"><span data-stu-id="cf65a-125">Customer data</span></span>

<span data-ttu-id="cf65a-126">Os dados do cliente são todos os dados fornecidos por ou em nome de um cliente ao usar os serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf65a-126">Customer data is all data provided by or on behalf of a customer when using Microsoft 365 services.</span></span> <span data-ttu-id="cf65a-127">Este é o conteúdo do cliente criado diretamente ou carregado pelos usuários do Microsoft 365, incluindo:</span><span class="sxs-lookup"><span data-stu-id="cf65a-127">This is customer content directly created or uploaded by Microsoft 365 users, including:</span></span>

- <span data-ttu-id="cf65a-128">Emails</span><span class="sxs-lookup"><span data-stu-id="cf65a-128">Emails</span></span>
- <span data-ttu-id="cf65a-129">Conteúdo do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="cf65a-129">SharePoint Online content</span></span>
- <span data-ttu-id="cf65a-130">Mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="cf65a-130">Instant messages</span></span>
- <span data-ttu-id="cf65a-131">Itens de calendário</span><span class="sxs-lookup"><span data-stu-id="cf65a-131">Calendar items</span></span>
- <span data-ttu-id="cf65a-132">Documentos</span><span class="sxs-lookup"><span data-stu-id="cf65a-132">Documents</span></span>
- <span data-ttu-id="cf65a-133">Contatos</span><span class="sxs-lookup"><span data-stu-id="cf65a-133">Contacts</span></span>
- <span data-ttu-id="cf65a-134">Informações de identificação do usuário final (EUII) (dados exclusivos de um usuário ou que são vinculados a um usuário individual, mas não incluem conteúdo do cliente)</span><span class="sxs-lookup"><span data-stu-id="cf65a-134">End-user identifiable information (EUII) (data that is unique to a user or that is linkable to an individual user but does not include customer content)</span></span>

### <a name="other-types-of-data"></a><span data-ttu-id="cf65a-135">Outros tipos de dados</span><span class="sxs-lookup"><span data-stu-id="cf65a-135">Other types of data</span></span>

<span data-ttu-id="cf65a-136">Outros tipos de dados incluem:</span><span class="sxs-lookup"><span data-stu-id="cf65a-136">Other types of data include:</span></span>

- <span data-ttu-id="cf65a-137">**Dados da conta:** Inclui dados administrativos (informações fornecidas por administradores ao inscrever-se ou comprar serviços) e dados de pagamento (informações sobre instrumentos de pagamento, como detalhes do cartão de crédito).</span><span class="sxs-lookup"><span data-stu-id="cf65a-137">**Account data:** Includes administrative data (information provided by administrators when they sign-up or purchase services), and payment data (information about payment instruments, such as credit card details).</span></span>
- <span data-ttu-id="cf65a-138">**Informações de identificação corporativa:** Inclui dados usados para identificar um locatário, dados de uso e não vinculáveis a um usuário individual ou incluído no conteúdo do cliente.</span><span class="sxs-lookup"><span data-stu-id="cf65a-138">**Organizationally identifiable information:** Includes data used to identify a tenant, usage data, and not linkable to an individual user or included in customer content.</span></span>
- <span data-ttu-id="cf65a-139">**Metadados do sistema:** Inclui logs de serviço que contêm definições de configuração, status do sistema, endereços IP da Microsoft e informações técnicas sobre inscrições e locatários.</span><span class="sxs-lookup"><span data-stu-id="cf65a-139">**System metadata:** Includes service logs that contain configuration settings, system status, Microsoft IP addresses, and technical information about subscriptions and tenants.</span></span>

<span data-ttu-id="cf65a-140">A Microsoft estabeleceu mecanismos de controle de acesso para garantir que ninguém tenha acesso não aprovado aos dados do cliente ou aos dados de controle de acesso.</span><span class="sxs-lookup"><span data-stu-id="cf65a-140">Microsoft has established access control mechanisms to ensure that no one has unapproved access to Customer Data or access control data.</span></span> <span data-ttu-id="cf65a-141">Os dados de controle de acesso gerenciam o acesso a outros tipos de dados ou funções dentro do ambiente, incluindo acesso ao conteúdo do cliente ou EUII, senhas da Microsoft, certificados de segurança e outros dados relacionados à autenticação.</span><span class="sxs-lookup"><span data-stu-id="cf65a-141">Access control data manages access to other types of data or functions within the environment, including access to customer content or EUII, Microsoft passwords, security certificates, and other authentication-related data.</span></span> <span data-ttu-id="cf65a-142">Os mecanismos de controle de acesso também protegem contra acesso físico, lógico ou remoto não aprovado ao ambiente de produção do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf65a-142">Access control mechanisms also guard against unapproved physical, logical, or remote access to the Microsoft 365 production environment.</span></span>

<span data-ttu-id="cf65a-143">Há três categorias de controles de acesso usados pela Microsoft para a operação do Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="cf65a-143">There are three categories of access controls used by Microsoft for operating Microsoft 365:</span></span>

- <span data-ttu-id="cf65a-144">Controles de isolamento</span><span class="sxs-lookup"><span data-stu-id="cf65a-144">Isolation controls</span></span>
- <span data-ttu-id="cf65a-145">Controles de pessoal</span><span class="sxs-lookup"><span data-stu-id="cf65a-145">Personnel controls</span></span>
- <span data-ttu-id="cf65a-146">Controles de tecnologia</span><span class="sxs-lookup"><span data-stu-id="cf65a-146">Technology controls</span></span>

<span data-ttu-id="cf65a-147">Quando combinadas, esses controles ajudam a evitar e detectar ações mal-intencionadas no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cf65a-147">When combined, these controls help prevent and detect malicious actions in Microsoft 365.</span></span> <span data-ttu-id="cf65a-148">Além dos controles de isolamento, pessoal e tecnologia usados pela Microsoft, há uma quarta categoria de controles: as implementadas por clientes.</span><span class="sxs-lookup"><span data-stu-id="cf65a-148">In addition to the isolation, personnel, and technology controls used by Microsoft, there is a fourth category of controls: those implemented by customers.</span></span>

<span data-ttu-id="cf65a-149">O Microsoft 365 permite que você gerencie dados da mesma forma que os dados são gerenciados em ambientes locais.</span><span class="sxs-lookup"><span data-stu-id="cf65a-149">Microsoft 365 allows you to manage data the same way data is managed in on-premises environments.</span></span> <span data-ttu-id="cf65a-150">A pessoa que se inscreve na organização do Microsoft 365 se torna automaticamente um administrador global.</span><span class="sxs-lookup"><span data-stu-id="cf65a-150">The person who signs up an organization for Microsoft 365 automatically becomes a global administrator.</span></span> <span data-ttu-id="cf65a-151">O administrador global tem acesso a todos os recursos nos portais de gerenciamento e pode:</span><span class="sxs-lookup"><span data-stu-id="cf65a-151">The global admin has access to all features in management portals and can:</span></span>

- <span data-ttu-id="cf65a-152">Criar ou editar usuários</span><span class="sxs-lookup"><span data-stu-id="cf65a-152">Create or edit users</span></span>
- <span data-ttu-id="cf65a-153">Atribuir funções de administrador a outras pessoas</span><span class="sxs-lookup"><span data-stu-id="cf65a-153">Assign admin roles to others</span></span>
- <span data-ttu-id="cf65a-154">Redefinir senhas de usuário</span><span class="sxs-lookup"><span data-stu-id="cf65a-154">Reset user passwords</span></span>
- <span data-ttu-id="cf65a-155">Gerenciar licenças de usuário</span><span class="sxs-lookup"><span data-stu-id="cf65a-155">Manage user licenses</span></span>
- <span data-ttu-id="cf65a-156">Gerenciar domínios</span><span class="sxs-lookup"><span data-stu-id="cf65a-156">Manage domains</span></span>
- <span data-ttu-id="cf65a-157">Aprovar solicitações de lockbox do cliente</span><span class="sxs-lookup"><span data-stu-id="cf65a-157">Approve Customer Lockbox requests</span></span>

<span data-ttu-id="cf65a-158">Recomendamos que cada organização configure pelo menos duas contas de administrador.</span><span class="sxs-lookup"><span data-stu-id="cf65a-158">We recommend that each organization configure at least two admin accounts.</span></span> <span data-ttu-id="cf65a-159">Para organizações de grande porte, recomendamos contas de administração especializadas que atendam a diferentes funções.</span><span class="sxs-lookup"><span data-stu-id="cf65a-159">For large enterprise organizations, we recommend specialized admin accounts that serve different functions.</span></span>

<span data-ttu-id="cf65a-160">Para obter informações sobre como atribuir permissões e funções de administrador, consulte [assign admin Roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) e [about admin Roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="cf65a-160">For information about assigning admin roles and permissions, see [Assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) and [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="related-links"></a><span data-ttu-id="cf65a-161">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="cf65a-161">Related Links</span></span>

- [<span data-ttu-id="cf65a-162">Controles de isolamento</span><span class="sxs-lookup"><span data-stu-id="cf65a-162">Isolation Controls</span></span>](microsoft-365-isolation-controls.md)
- [<span data-ttu-id="cf65a-163">Controles de pessoal</span><span class="sxs-lookup"><span data-stu-id="cf65a-163">Personnel Controls</span></span>](microsoft-365-personnel-controls.md)
- [<span data-ttu-id="cf65a-164">Controles de tecnologia</span><span class="sxs-lookup"><span data-stu-id="cf65a-164">Technology Controls</span></span>](microsoft-365-technology-controls.md)
- [<span data-ttu-id="cf65a-165">Monitorando e auditando controles de acesso </span><span class="sxs-lookup"><span data-stu-id="cf65a-165">Monitoring and Auditing Access Controls</span></span>](microsoft-365-monitoring-and-auditing-access-controls.md)
- [<span data-ttu-id="cf65a-166">Controles de acesso do Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="cf65a-166">Yammer Enterprise Access Controls</span></span>](microsoft-365-yammer-enterprise-access-controls.md)
