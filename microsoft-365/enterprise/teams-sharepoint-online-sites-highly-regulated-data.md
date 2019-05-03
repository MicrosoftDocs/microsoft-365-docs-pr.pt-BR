---
title: Sites do Microsoft Teams e do SharePoint Online para dados altamente controlados
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/03/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Crie um site de equipe seguro do SharePoint Online um uma equipe do Microsoft Teams para armazenar seus ativos digitais mais importantes e confidenciais.
ms.openlocfilehash: d80be334f692f905ec70ae43f851d2b73801f4a0
ms.sourcegitcommit: dbcc32218489ab256b7eb343290fcccb9bc04e36
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/02/2019
ms.locfileid: "33553320"
---
# <a name="microsoft-teams-and-sharepoint-online-sites-for-highly-regulated-data"></a><span data-ttu-id="64732-103">Sites do Microsoft Teams e do SharePoint Online para dados altamente controlados</span><span class="sxs-lookup"><span data-stu-id="64732-103">Microsoft Teams and SharePoint Online sites for highly regulated data</span></span>

<span data-ttu-id="64732-104">*Este cenário aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="64732-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="64732-p101">O Microsoft 365 Enterprise inclui um conjunto completo de serviços em nuvem para que você possa criar, armazenar e proteger seus dados altamente regulados. Isso inclui os dados:</span><span class="sxs-lookup"><span data-stu-id="64732-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data. This includes data that is:</span></span>

- <span data-ttu-id="64732-107">Sujeitos a regulamentações regionais.</span><span class="sxs-lookup"><span data-stu-id="64732-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="64732-108">Mais importantes de sua organização, como segredos comerciais, financeiros ou informações de recursos humanos e estratégias da organização.</span><span class="sxs-lookup"><span data-stu-id="64732-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

<span data-ttu-id="64732-109">Uma solução Microsoft 365 Enterprise baseada na nuvem, que atende a essa necessidade comercial, requer que você:</span><span class="sxs-lookup"><span data-stu-id="64732-109">A Microsoft 365 Enterprise cloud-based solution that meets this business need requires that you:</span></span>

- <span data-ttu-id="64732-110">Armazene ativos digitais (documentos, apresentações de slides, planilhas etc.) em um site de equipe do SharePoint Online ou na guia **Arquivos** de uma equipe Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="64732-110">Store digital assets (documents, slide decks, spreadsheets, etc.) in a SharePoint Online team site or in the **Files** tab of a Microsoft Teams team.</span></span>
- <span data-ttu-id="64732-111">Bloqueie o site ou a equipe para impedir:</span><span class="sxs-lookup"><span data-stu-id="64732-111">Lock down the site or team to prevent:</span></span>
   - <span data-ttu-id="64732-112">O acesso a apenas um conjunto específico de contas de usuário por meio de associações de grupo, que inclui aqueles que podem acessar o site de equipe do SharePoint Online, qual o nível de permissão e quem pode administrá-lo.</span><span class="sxs-lookup"><span data-stu-id="64732-112">Access to only a specific set of user accounts through group membership, which includes those who can access the SharePoint Online team site and at what level of permission, and those who can administer it.</span></span>
   - <span data-ttu-id="64732-113">Que membros do site concedam acesso a outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="64732-113">Members of the site from granting access to others.</span></span>
   - <span data-ttu-id="64732-114">Que aqueles que não sejam membros do site solicitem acesso a ele.</span><span class="sxs-lookup"><span data-stu-id="64732-114">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="64732-115">Configurar um rótulo de retenção do Office 365 para seus sites ou equipes do SharePoint Online como uma maneira padrão de definir políticas de retenção nos documentos no site ou na equipe.</span><span class="sxs-lookup"><span data-stu-id="64732-115">Configure an Office 365 retention label for your SharePoint Online sites or teams as a default way to define retention policies on the documents in the site or team.</span></span>
- <span data-ttu-id="64732-116">Impedir usuários de enviar arquivos para fora da organização.</span><span class="sxs-lookup"><span data-stu-id="64732-116">Block users from sending files outside the organization.</span></span>
- <span data-ttu-id="64732-117">Criptografe os ativos digitais mais importantes do site ou da equipe.</span><span class="sxs-lookup"><span data-stu-id="64732-117">Encrypt the most sensitive digital assets of the site or team.</span></span>
- <span data-ttu-id="64732-118">Adicione permissões aos ativos digitais mais importantes para que, mesmo que sejam compartilhados fora do site, só seja possível abri-lo com as credenciais válidas de uma conta de usuário que tenha a permissão.</span><span class="sxs-lookup"><span data-stu-id="64732-118">Add permissions to the most sensitive digital assets so that if even if they get shared outside of the site, opening the asset still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="64732-119">A tabela a seguir mapeia os requisitos dessa solução para um recurso do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="64732-119">The following table maps the requirements of this solution to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="64732-120">**Requisito**</span><span class="sxs-lookup"><span data-stu-id="64732-120">**Requirement**</span></span> | <span data-ttu-id="64732-121">**Recurso do Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="64732-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="64732-122">Armazenar ativos digitais</span><span class="sxs-lookup"><span data-stu-id="64732-122">Store digital assets</span></span> | <span data-ttu-id="64732-123">Sites e equipes do SharePoint Online no Office 365</span><span class="sxs-lookup"><span data-stu-id="64732-123">SharePoint Online team sites and teams in Office 365</span></span> |
| <span data-ttu-id="64732-124">Bloquear o site</span><span class="sxs-lookup"><span data-stu-id="64732-124">Lock down the site</span></span> | <span data-ttu-id="64732-125">Permissões do site de equipe do SharePoint Online e grupos do Azure AD</span><span class="sxs-lookup"><span data-stu-id="64732-125">Azure AD groups and SharePoint Online team site permissions</span></span> |
| <span data-ttu-id="64732-126">Rotular os ativos digitais do site</span><span class="sxs-lookup"><span data-stu-id="64732-126">Label the digital assets of the site</span></span> | <span data-ttu-id="64732-127">Rótulos de retenção do Office 365</span><span class="sxs-lookup"><span data-stu-id="64732-127">Office 365 retention labels</span></span> |
| <span data-ttu-id="64732-128">Bloquear usuários ao enviar arquivos para fora da organização.</span><span class="sxs-lookup"><span data-stu-id="64732-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="64732-129">Políticas de Prevenção Contra Perda de Dados (DLP) no Office 365</span><span class="sxs-lookup"><span data-stu-id="64732-129">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="64732-130">Criptografar todos os ativos digitais do site</span><span class="sxs-lookup"><span data-stu-id="64732-130">Encrypt all of the digital assets of the site</span></span> | <span data-ttu-id="64732-131">Sub-rótulos de Proteção de Informações do Azure no Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="64732-131">Azure Information Protection sub-labels in Enterprise Mobility + Security (EMS)</span></span> |
| <span data-ttu-id="64732-132">Adicionar permissões aos ativos digitais do site</span><span class="sxs-lookup"><span data-stu-id="64732-132">Add permissions to the digital assets of the site</span></span> | <span data-ttu-id="64732-133">Sub-rótulos da Proteção de Informações do Azure no EMS</span><span class="sxs-lookup"><span data-stu-id="64732-133">Azure Information Protection sub-labels in EMS</span></span> |
|||

<span data-ttu-id="64732-134">Esta solução exige que você já tenha implantado:</span><span class="sxs-lookup"><span data-stu-id="64732-134">This solution requires that you have already deployed:</span></span>

- <span data-ttu-id="64732-135">A fase de [identidade](identity-infrastructure.md) e as etapas 1 e 2 da fase de [proteção de informações](infoprotect-infrastructure.md) da infraestrutura de base.</span><span class="sxs-lookup"><span data-stu-id="64732-135">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="64732-136">Para dados altamente regulados nos sites de equipe do SharePoint Online, o [SharePoint Online](sharepoint-online-onedrive-workload.md).</span><span class="sxs-lookup"><span data-stu-id="64732-136">For highly regulated data in SharePoint Online team sites, [SharePoint Online](sharepoint-online-onedrive-workload.md).</span></span>
- <span data-ttu-id="64732-137">Para dados altamente regulados nas equipes do Microsoft Teams, o [Microsoft Teams](teams-workload.md).</span><span class="sxs-lookup"><span data-stu-id="64732-137">For highly regulated data in Microsoft Teams teams, [Microsoft Teams](teams-workload.md).</span></span>

<span data-ttu-id="64732-138">As fases a seguir o orientam pelo design, configuração e geração de adoção dos sites e equipes do SharePoint Online para dados altamente regulados.</span><span class="sxs-lookup"><span data-stu-id="64732-138">The following phases step you through the design, configuration, and driving adoption for SharePoint Online sites and teams for highly regulated data.</span></span>

<span data-ttu-id="64732-139">Para ver como a Contoso Corporation, uma organização multinacional fictícia representativa, projetou um site do SharePoint Online para suas equipes de pesquisa, consulte esta [configuração de exemplo](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span><span class="sxs-lookup"><span data-stu-id="64732-139">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint Online site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>

>[!Note]
><span data-ttu-id="64732-p102">Uma equipe para dados altamente regulados requer que você primeiro crie um site de equipe do SharePoint Online para dados altamente regulados. Em seguida, você cria uma nova equipe que usa o grupo do Office 365 do site de equipe do SharePoint Online. Consulte a Fase 2, Etapa 4 para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="64732-p102">A team for highly regulated data requires that you first create a SharePoint Online team site for highly regulated data. You then create a new team that uses the Office 365 group of the SharePoint Online team site. See Phase 2, Step 4 for more information.</span></span>
>

## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="64732-143">Pré-requisitos de acesso ao dispositivo e identidade</span><span class="sxs-lookup"><span data-stu-id="64732-143">Identity and device access prerequisites</span></span>

<span data-ttu-id="64732-144">Para proteger o acesso à equipe ou ao site do SharePoint Online, assegure-se de ter configurado [políticas de identidade e de acesso ao dispositivo](identity-access-policies.md) e as [políticas de acesso recomendadas do SharePoint Online](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="64732-144">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="64732-145">Fase 1: Design</span><span class="sxs-lookup"><span data-stu-id="64732-145">Phase 1: Design</span></span>

<span data-ttu-id="64732-p103">Para criar um site ou uma equipe do SharePoint Online para dados altamente regulados, primeiro você precisa identificar a finalidade dele. Por exemplo, o departamento de pesquisa e desenvolvimento e uma organização de manufatura precisa de um site do SharePoint Online para armazenar especificações atuais de design de produtos existentes e um local para colaborar em novos produtos. Apenas os membros do departamento de Pesquisa e Desenvolvimento e determinados executivos poderão acessar o site.</span><span class="sxs-lookup"><span data-stu-id="64732-p103">To create a SharePoint Online site or team for highly regulated data, you must first identify its purpose. For example, the research and development department of a manufacturing organization needs a SharePoint Online site to store current design specifications for existing products and a place to collaborate on new products. Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="64732-149">Essa finalidade gerará a determinação de itens essenciais de configuração como:</span><span class="sxs-lookup"><span data-stu-id="64732-149">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="64732-150">O conjunto de grupos do SharePoint e os conjuntos de permissão do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="64732-150">The set of SharePoint Online permission sets and SharePoint groups</span></span>
- <span data-ttu-id="64732-151">O conjunto de grupos de acesso, grupos de segurança do Azure AD e seus membros para adicionar aos grupos do SharePoint</span><span class="sxs-lookup"><span data-stu-id="64732-151">The set of access groups, the Azure AD security groups and their members to add to the SharePoint groups</span></span>
- <span data-ttu-id="64732-152">O rótulo de retenção do Office 365 a ser atribuído ao site e o conjunto de políticas DLP para o rótulo</span><span class="sxs-lookup"><span data-stu-id="64732-152">The Office 365 retention label to assign to the site and the set of DLP policies for the label</span></span>
- <span data-ttu-id="64732-153">As configurações do sub-rótulo de Proteção de Informações do Azure que os usuários aplicam a ativos digitais altamente confidenciais armazenados no site</span><span class="sxs-lookup"><span data-stu-id="64732-153">The settings of an Azure Information Protection sub-label that users apply to highly sensitive digital assets stored in the site</span></span>

<span data-ttu-id="64732-154">Quando determinado, você usa essas configurações para configurar o site na Fase 2.</span><span class="sxs-lookup"><span data-stu-id="64732-154">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-an-isolated-sharepoint-online-site"></a><span data-ttu-id="64732-155">Etapa 1: Um site isolado do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="64732-155">Step 1: An isolated SharePoint Online site</span></span>

<span data-ttu-id="64732-p104">A versão bloqueada de um site de equipe do SharePoint Online é conhecida como um site isolado. Ao contrário das configurações padrão de sites de equipe privados, sites isolados são configurados para evitar:</span><span class="sxs-lookup"><span data-stu-id="64732-p104">The locked-down version of a SharePoint Online team site is known as an isolated site. Unlike the default settings of private team sites, isolated sites are configured to prevent:</span></span>

- <span data-ttu-id="64732-158">O acesso daqueles que não são membros de grupos especificados.</span><span class="sxs-lookup"><span data-stu-id="64732-158">Access to those who are not members of specified groups.</span></span>
- <span data-ttu-id="64732-159">A solicitação de acesso.</span><span class="sxs-lookup"><span data-stu-id="64732-159">The requesting of access.</span></span>
- <span data-ttu-id="64732-160">A concessão não autorizada de acesso por membros atuais de grupos especificados.</span><span class="sxs-lookup"><span data-stu-id="64732-160">The unauthorized granting of access by current members of specified groups.</span></span>
- <span data-ttu-id="64732-161">Administração do site pelos membros de grupo de acesso.</span><span class="sxs-lookup"><span data-stu-id="64732-161">Administration of the site by access group members.</span></span>

<span data-ttu-id="64732-162">A segurança dos sites de equipe do SharePoint Online que contêm ativos altamente regulados não muda, a não ser que seja alterada por um administrador do SharePoint para o site.</span><span class="sxs-lookup"><span data-stu-id="64732-162">The security of SharePoint Online team sites that contain highly regulated assets do not change unless done by a SharePoint administrator for the site.</span></span>

<span data-ttu-id="64732-163">Consulte [Projetar um site de equipe isolado do SharePoint Online](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site) para obter detalhes para determinar o conjunto de níveis de permissão, grupos do SharePoint, grupos de acesso e membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="64732-163">See [Design an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site) for the details to determine the set of permission levels, SharePoint groups, access groups, and group members.</span></span>

### <a name="step-2-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="64732-164">Etapa 2: rótulos de retenção do Office 365 e políticas DLP</span><span class="sxs-lookup"><span data-stu-id="64732-164">Step 2: Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="64732-165">Quando aplicados a um site de equipe do SharePoint Online, os rótulos de retenção do Office 365 oferecem um método padrão para classificar todos os ativos digitais armazenados no site.</span><span class="sxs-lookup"><span data-stu-id="64732-165">When applied to a SharePoint Online team site, Office 365 retention labels provide a default method of classifying all digital assets stored on the site.</span></span>
 
<span data-ttu-id="64732-166">Nos sites do SharePoint Online para dados altamente controlados, você precisa determinar qual rótulo de retenção do Office 365 será usado.</span><span class="sxs-lookup"><span data-stu-id="64732-166">For SharePoint Online sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="64732-167">Para considerações de design dos rótulos do Office 365, consulte [Rótulos e classificação do Office 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="64732-167">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="64732-p105">Para proteger informações confidenciais e evitar a divulgação acidental ou intencional, use as políticas DLP. Para obter mais informações, consulte esta [visão geral](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span><span class="sxs-lookup"><span data-stu-id="64732-p105">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="64732-170">Para sites do SharePoint para dados altamente controlados, você deve configurar uma política DLP do rótulo de retenção do Office 365 atribuído ao site para bloquear usuários quando eles tentam compartilhar ativos digitais com usuários externos.</span><span class="sxs-lookup"><span data-stu-id="64732-170">For SharePoint Online sites for highly regulated data, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share digital assets with external users.</span></span> 

### <a name="step-3-your-azure-information-protection-sub-label"></a><span data-ttu-id="64732-171">Etapa 3: seu sub-rótulo de Proteção de Informações do Azure</span><span class="sxs-lookup"><span data-stu-id="64732-171">Step 3: Your Azure Information Protection sub-label</span></span>

<span data-ttu-id="64732-p106">Para fornecer um conjunto de permissões e a criptografia para seus ativos digitais mais importantes, os usuários devem aplicar um rótulo de Proteção de Informações do Azure usando o cliente de Proteção de Informações do Azure. Para usar rótulos de Proteção de Informações do Azure em sites do SharePoint Online para dados altamente regulamentados, você deve configurar um sub-rótulo de Proteção de Informações do Azure em uma política com escopo.</span><span class="sxs-lookup"><span data-stu-id="64732-p106">To provide encryption and a set of permissions to your most sensitive digital assets, users must apply an Azure Information Protection label using the Azure Information Protection client. To use Azure Information Protection labels for SharePoint Online sites for highly regulated data, you must configure an Azure Information Protection sub-label in a scoped policy.</span></span> 

<span data-ttu-id="64732-p107">Um sub-rótulo existe em um rótulo existente. Por exemplo, você pode criar um sub-rótulo Pesquisa e Desenvolvimento no rótulo Altamente Confidencial. Uma política com escopo é uma que se aplica apenas a um subconjunto de usuários. Nos sites do SharePoint Online para dados altamente regulamentados, o escopo é o conjunto de usuários que são membros dos grupos de acesso do site.</span><span class="sxs-lookup"><span data-stu-id="64732-p107">A sub-label exists under an existing label. For example, you can create a Research & Development sub-label under the Highly Confidential label. A scoped policy is one that applies only to a subset of users. For SharePoint Online sites for highly regulated data, the scope is the set of users that are members of the access groups for the site.</span></span>

<span data-ttu-id="64732-p108">As configurações do sub-rótulo aplicado acompanham o ativo. Mesmo que ele seja baixado e compartilhado fora do site, apenas as contas de usuário autenticadas com permissões poderão abri-lo.</span><span class="sxs-lookup"><span data-stu-id="64732-p108">The settings of the applied sub-label travel with the asset. Even if it is downloaded and shared outside the site, only authenticated user accounts that have permissions can open it.</span></span>

### <a name="design-results"></a><span data-ttu-id="64732-180">Resultados de design</span><span class="sxs-lookup"><span data-stu-id="64732-180">Design results</span></span>

<span data-ttu-id="64732-181">Você determinou o seguinte:</span><span class="sxs-lookup"><span data-stu-id="64732-181">You have determined the following:</span></span>

- <span data-ttu-id="64732-182">O conjunto de grupos e níveis de permissão do SharePoint</span><span class="sxs-lookup"><span data-stu-id="64732-182">The set of SharePoint groups and permission levels</span></span>
- <span data-ttu-id="64732-183">O conjunto de grupos de acesso e os membros deles em cada nível de permissão</span><span class="sxs-lookup"><span data-stu-id="64732-183">The set of access groups and their members for each permission level</span></span>
- <span data-ttu-id="64732-184">O rótulo de retenção apropriado do Office 365 e a política DLP que está associada ao rótulo</span><span class="sxs-lookup"><span data-stu-id="64732-184">The appropriate Office 365 label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="64732-185">As configurações do sub-rótulo Proteção de Informações do Azure que incluem criptografia e permissões</span><span class="sxs-lookup"><span data-stu-id="64732-185">The settings of the Azure Information Protection sub-label that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="64732-186">Fase 2: Configurar</span><span class="sxs-lookup"><span data-stu-id="64732-186">Phase 2: Configure</span></span>

<span data-ttu-id="64732-187">Nesta fase, você usa as configurações determinadas na Fase 1 e as implementa para criar um site do SharePoint Online para dados altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="64732-187">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint Online site for highly regulated data.</span></span>

### <a name="step-1-create-and-configure-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="64732-188">Etapa 1: criar e configurar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="64732-188">Step 1: Create and configure an isolated SharePoint Online team site</span></span>

<span data-ttu-id="64732-189">Use as instruções em [Implantar um site de equipe do SharePoint Online isolado](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site) para:</span><span class="sxs-lookup"><span data-stu-id="64732-189">Use the instructions in [Deploy an isolated SharePoint Online team site](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site) to:</span></span>

- <span data-ttu-id="64732-190">Crie e preencha os grupos de acesso para cada nível de permissão do SharePoint usado no site.</span><span class="sxs-lookup"><span data-stu-id="64732-190">Create and populate the access groups for each SharePoint permission level used on the site.</span></span>
- <span data-ttu-id="64732-191">Crie e configure o site de equipe isolado.</span><span class="sxs-lookup"><span data-stu-id="64732-191">Create and configure the isolated team site.</span></span>

### <a name="step-2-configure-the-site-for-an-office-365-retention-label-dlp-policy"></a><span data-ttu-id="64732-192">Etapa 2: configurar o site para uma política DLP de um rótulo de retenção do Office 365</span><span class="sxs-lookup"><span data-stu-id="64732-192">Step 2: Configure the site for an Office 365 retention label DLP policy</span></span>

<span data-ttu-id="64732-193">Use as instruções em [Proteger arquivos do SharePoint Online com DLP e rótulos do Office 365](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) para:</span><span class="sxs-lookup"><span data-stu-id="64732-193">Use the instructions in [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

- <span data-ttu-id="64732-194">Identificar ou criar o rótulo de retenção do Office 365 e aplicá-lo ao seu site isolado do SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="64732-194">Identify or create the Office 365 retention label and apply it to your isolated SharePoint Online site.</span></span>
- <span data-ttu-id="64732-195">Crie e configure a política DLP que bloqueia os usuários quando eles tentam compartilhar um ativo digital em seu site do SharePoint Online fora da organização.</span><span class="sxs-lookup"><span data-stu-id="64732-195">Create and configure the DLP policy that blocks users when they attempt to share a digital asset on your SharePoint Online site outside the organization.</span></span>

### <a name="step-3-create-an-azure-information-protection-sub-label-for-the-site"></a><span data-ttu-id="64732-196">Etapa 3: criar um sub-rótulo de Proteção de Informações do Azure no site</span><span class="sxs-lookup"><span data-stu-id="64732-196">Step 3: Create an Azure Information Protection sub-label for the site</span></span>

<span data-ttu-id="64732-197">Use as instruções em [Proteger arquivos do SharePoint Online com Proteção de Informações do Azure](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection) para:</span><span class="sxs-lookup"><span data-stu-id="64732-197">Use the instructions in [Protect SharePoint Online files with Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection) to:</span></span> 

- <span data-ttu-id="64732-198">Crie e configure um sub-rótulo Proteção de Informações do Azure em uma política com escopo.</span><span class="sxs-lookup"><span data-stu-id="64732-198">Create and configure an Azure Information Protection sub-label in a scoped policy.</span></span>
- <span data-ttu-id="64732-199">Implante do cliente de Proteção de Informações do Azure nos computadores de usuário.</span><span class="sxs-lookup"><span data-stu-id="64732-199">Deploy the Azure Information Protection client to user computers.</span></span>

### <a name="step-4-optional-create-a-team-for-the-highly-regulated-data"></a><span data-ttu-id="64732-200">Etapa 4 (opcional): criar e configurar uma equipe para dados altamente regulamentados</span><span class="sxs-lookup"><span data-stu-id="64732-200">Step 4 (optional): Create a team for the highly regulated data</span></span>

<span data-ttu-id="64732-p109">Se desejar uma equipe para dados altamente regulamentados, você primeiro cria um site do SharePoint Online para dados altamente regulamentados. Quando cria o site de equipe privado inicial do SharePoint Online, você especifica um nome de grupo do Office 365.</span><span class="sxs-lookup"><span data-stu-id="64732-p109">If you want a team for highly regulated data, you first create a SharePoint Online site for highly regulated data. When you create the initial private SharePoint Online team site, you specify an Office 365 group name.</span></span>

<span data-ttu-id="64732-203">Depois que o site do SharePoint Online altamente regulamentado estiver configurado, use estas etapas para convertê-lo em uma equipe para dados altamente regulamentados:</span><span class="sxs-lookup"><span data-stu-id="64732-203">After the SharePoint Online site for highly regulated data is fully configured, use these steps to convert it into a team for highly regulated data:</span></span>

1. <span data-ttu-id="64732-204">Entrar no Office 365.</span><span class="sxs-lookup"><span data-stu-id="64732-204">Sign in to Office 365.</span></span>
2. <span data-ttu-id="64732-205">Na guia **Microsoft Office Home**, clique em **Teams**.</span><span class="sxs-lookup"><span data-stu-id="64732-205">From the **Microsoft Office Home** tab, click **Teams**.</span></span>
3. <span data-ttu-id="64732-206">Na guia **Microsoft Teams**, no painel **Ingressar ou criar uma equipe**, clique em **Criar equipe**.</span><span class="sxs-lookup"><span data-stu-id="64732-206">From the **Microsoft Teams** tab, in the **Join or create a team** pane, click **Create team**.</span></span>
4. <span data-ttu-id="64732-207">No painel **Criar sua equipe**, clique em **Criar uma equipe de um grupo existente do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="64732-207">In the **Create your team** pane, click **Create a team from an existing Office 365 group**.</span></span>
5. <span data-ttu-id="64732-208">Na lista dos grupos do Office 365, selecione o nome do grupo do Office 365 que corresponde ao site do SharePoint Online para dados altamente regulamentados e clique em **Escolher equipe**.</span><span class="sxs-lookup"><span data-stu-id="64732-208">In the list of Office 365 groups, select the name of the Office 365 group corresponding to the SharePoint Online site for highly regulated data, and then click **Choose team**.</span></span>

<span data-ttu-id="64732-p110">A guia **Arquivos** da nova equipe lista o conteúdo da pasta **Geral** da área **Documentos** do site do SharePoint Online correspondente. Para ver o resto dos recursos do site do SharePoint Online da equipe, clique nas reticências e clique em **Abrir no SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="64732-p110">The **Files** tab of the new team lists the contents of the **General** folder of the **Documents** area of the corresponding SharePoint Online site. To see the rest of the resources of the SharePoint Online site for the team, click the ellipsis, and then click **Open in SharePoint**.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="64732-211">Resultados da configuração</span><span class="sxs-lookup"><span data-stu-id="64732-211">Configuration results</span></span>

<span data-ttu-id="64732-212">Você configurou o seguinte:</span><span class="sxs-lookup"><span data-stu-id="64732-212">You have configured the following:</span></span>

- <span data-ttu-id="64732-213">Um site isolado do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="64732-213">A SharePoint Online isolated site</span></span>
- <span data-ttu-id="64732-214">Um rótulo de retenção do Office 365 atribuído ao site isolado do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="64732-214">An Office 365 retention label assigned to the SharePoint Online isolated site</span></span>
- <span data-ttu-id="64732-215">Uma política DLP para o rótulo de retenção do Office 365</span><span class="sxs-lookup"><span data-stu-id="64732-215">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="64732-216">Um sub-rótulo de Proteção de Informações do Azure de uma política com escopo que os usuários podem aplicar aos ativos digitais mais confidenciais armazenados no site e aplica as permissões</span><span class="sxs-lookup"><span data-stu-id="64732-216">An Azure Information Protection sub-label of a scoped policy that users can apply to the most sensitive digital assets stored in the site that encrypts the asset and enforces permissions</span></span>
- <span data-ttu-id="64732-217">Se necessário, uma equipe de dados altamente regulamentados com base no site do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="64732-217">If needed, a team for highly regulated data based on the SharePoint Online site</span></span>

## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="64732-218">Fase 3: Gerar adoção do usuário</span><span class="sxs-lookup"><span data-stu-id="64732-218">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="64732-p111">Um site ou uma equipe do SharePoint Online para dados altamente regulamentados podem proteger os dados apenas se eles sejam constantemente usados para armazenamento e acesso dos ativos digitais confidenciais. Essa é a fase mais difícil, já que ela depende da mudança de comportamento dos usuários.</span><span class="sxs-lookup"><span data-stu-id="64732-p111">A SharePoint Online site or team for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive digital assets. This is the hardest phase because it relies on users changing their ways.</span></span> 

<span data-ttu-id="64732-221">Por exemplo, os executivos que estão acostumados a armazenar arquivos confidenciais em unidades USB ou em soluções de armazenamento pessoais na nuvem agora os armazenarão exclusivamente em um site ou equipe do SharePoint Online para dados altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="64732-221">For example, executives that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint Online site or team for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="64732-222">Etapa 1: Treinar os usuários</span><span class="sxs-lookup"><span data-stu-id="64732-222">Step 1: Train your users</span></span>

<span data-ttu-id="64732-223">Depois de concluir a configuração, treine o conjunto de usuários que são membros dos grupos de acesso do site:</span><span class="sxs-lookup"><span data-stu-id="64732-223">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="64732-224">Sobre a importância de usar o novo site ou equipe para proteger ativos importantes e as consequências de um vazamento de dados altamente regulamentados, como ramificações legais, multas regulamentares, ransomware ou perda de vantagem competitiva.</span><span class="sxs-lookup"><span data-stu-id="64732-224">On the importance of using the new site or team to protect valuable assets and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="64732-225">Como acessar o site e os ativos dele.</span><span class="sxs-lookup"><span data-stu-id="64732-225">How to access the site and its assets.</span></span>
- <span data-ttu-id="64732-226">Como criar novos arquivos no site e carregar novos arquivos armazenados localmente.</span><span class="sxs-lookup"><span data-stu-id="64732-226">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="64732-227">Como a política DLP bloqueia o compartilhamento de arquivos externamente por parte do usuário.</span><span class="sxs-lookup"><span data-stu-id="64732-227">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="64732-228">Como usar o cliente de Proteção de Informações do Azure para rotular os ativos digitais mais confidenciais com o sub-rótulo configurado.</span><span class="sxs-lookup"><span data-stu-id="64732-228">How to use the Azure Information Protection client to label the most sensitive digital assets with the configured sub-label.</span></span>
- <span data-ttu-id="64732-229">Como o sub-rótulo de Proteção de Informações do Azure protege um ativo mesmo quando ele vaza para fora do site ou da equipe.</span><span class="sxs-lookup"><span data-stu-id="64732-229">How the Azure Information Protection sub-label protects an asset even when it is leaked off the site or team.</span></span>

<span data-ttu-id="64732-230">Este treinamento deve incluir exercícios práticos para que os usuários possam experimentar essas operações e os resultados.</span><span class="sxs-lookup"><span data-stu-id="64732-230">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="64732-231">Etapa 2: conduzir análises periódicas de utilização e arquivos</span><span class="sxs-lookup"><span data-stu-id="64732-231">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="64732-232">Nas semanas após o treinamento, o administrador do SharePoint do site ou da equipe do SharePoint Online pode:</span><span class="sxs-lookup"><span data-stu-id="64732-232">In the weeks after training, the SharePoint administrator for the SharePoint Online site or team can:</span></span>

- <span data-ttu-id="64732-233">Analise a utilização do site ou da equipe e comparar com as expectativas de utilização.</span><span class="sxs-lookup"><span data-stu-id="64732-233">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="64732-234">Verifique se os arquivos altamente confidenciais foram rotulados corretamente com o sub-rótulo Proteção de Informações do Azure.</span><span class="sxs-lookup"><span data-stu-id="64732-234">Verify that highly sensitive files have been properly labeled with the Azure Information Protection sub-label.</span></span>

<span data-ttu-id="64732-235">Repita o treinamento dos usuários conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="64732-235">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="64732-236">Resultados de adoção do usuário</span><span class="sxs-lookup"><span data-stu-id="64732-236">User adoption results</span></span>

<span data-ttu-id="64732-237">Ativos digitais confidenciais são armazenados exclusivamente nos sites ou equipes do SharePoint Online para dados altamente regulamentados e os ativos mais importantes têm o sub-rótulo de Proteção de Informações do Azure aplicado.</span><span class="sxs-lookup"><span data-stu-id="64732-237">Sensitive digital assets are stored exclusively on SharePoint Online sites or teams for highly regulated data and that the most sensitive assets have the configured Azure Information Protection sub-label applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="64732-238">Confira também</span><span class="sxs-lookup"><span data-stu-id="64732-238">See also</span></span>

[<span data-ttu-id="64732-239">Guia de implantação</span><span class="sxs-lookup"><span data-stu-id="64732-239">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="64732-240">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="64732-240">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="64732-241">Proteger os sites do SharePoint Online em um ambiente de desenvolvimento/teste</span><span class="sxs-lookup"><span data-stu-id="64732-241">Secure SharePoint Online sites in a dev/test environment</span></span>](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-in-a-dev-test-environment)
