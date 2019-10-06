---
title: Sites do SharePoint para dados altamente regulamentados
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/04/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Crie um site de equipe do SharePoint seguro para armazenar seus arquivos mais valiosos e confidenciais.
ms.openlocfilehash: dc604870826075cee645dd466b82f908e1571339
ms.sourcegitcommit: e1ffb98ac8159d1dc814930fe388d3e37cbdc7e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/05/2019
ms.locfileid: "37403170"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="60ac1-103">Sites do SharePoint para dados altamente regulamentados</span><span class="sxs-lookup"><span data-stu-id="60ac1-103">Microsoft Teams and SharePoint Online sites for highly regulated data</span></span>

<span data-ttu-id="60ac1-104">*Este cenário aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="60ac1-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="60ac1-p101">O Microsoft 365 Enterprise inclui um pacote completo de serviços baseados em nuvem, para que você possa criar, armazenar e proteger seus dados altamente regulamentados armazenados em arquivos. Isso inclui dados que são:</span><span class="sxs-lookup"><span data-stu-id="60ac1-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, and secure your highly regulated data. This includes data that is:</span></span>

- <span data-ttu-id="60ac1-107">Sujeitos a regulamentações regionais.</span><span class="sxs-lookup"><span data-stu-id="60ac1-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="60ac1-108">Mais importantes de sua organização, como segredos comerciais, financeiros ou informações de recursos humanos e estratégias da organização.</span><span class="sxs-lookup"><span data-stu-id="60ac1-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

<span data-ttu-id="60ac1-109">Um cenário da Microsoft 365 Enterprise baseada na nuvem, que atende a essa necessidade comercial, requer que você:</span><span class="sxs-lookup"><span data-stu-id="60ac1-109">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="60ac1-110">Armazene arquivos (documentos, apresentações de slides, planilhas, etc.) em um site de equipe do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="60ac1-110">Store digital assets (documents, slide decks, spreadsheets, etc.) in a SharePoint Online team site or in the Files tab of a Microsoft Teams team.</span></span>
- <span data-ttu-id="60ac1-111">Bloqueie o site para impedir:</span><span class="sxs-lookup"><span data-stu-id="60ac1-111">Lock down the site or team to prevent:</span></span>
  - <span data-ttu-id="60ac1-112">Acesso a usuários que não são membros do grupo do Office 365 para o site.</span><span class="sxs-lookup"><span data-stu-id="60ac1-112">Access to users who are not members of the Office 365 group for the site.</span></span>
  - <span data-ttu-id="60ac1-113">Que membros do site concedam acesso a outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="60ac1-113">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="60ac1-114">Que aqueles que não sejam membros do site solicitem acesso a ele.</span><span class="sxs-lookup"><span data-stu-id="60ac1-114">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="60ac1-115">Configure um rótulo de retenção do Office 365 para seus sites do SharePoint como uma maneira padrão de impedir que os usuários enviem arquivos fora da organização.</span><span class="sxs-lookup"><span data-stu-id="60ac1-115">Configure an Office 365 retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="60ac1-116">Criptografe os arquivos mais confidenciais do site com criptografia que acompanha o arquivo.</span><span class="sxs-lookup"><span data-stu-id="60ac1-116">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="60ac1-117">Adicione permissões aos arquivos mais confidenciais para que, mesmo que sejam compartilhados fora do site, a abertura do arquivo ainda exija as credenciais válidas de uma conta de usuário que tenha a permissão.</span><span class="sxs-lookup"><span data-stu-id="60ac1-117">Add permissions to the most sensitive digital assets so that if even if they get shared outside of the site, opening the asset still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="60ac1-118">A tabela a seguir mapeia os requisitos desse cenário para um recurso do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="60ac1-118">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="60ac1-119">**Requisito**</span><span class="sxs-lookup"><span data-stu-id="60ac1-119">**Requirement**</span></span> | <span data-ttu-id="60ac1-120">**Recurso do Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="60ac1-120">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="60ac1-121">Armazenar arquivos </span><span class="sxs-lookup"><span data-stu-id="60ac1-121">4. Store files online</span></span> | <span data-ttu-id="60ac1-122">Sites de equipe do SharePoint</span><span class="sxs-lookup"><span data-stu-id="60ac1-122">Sensitive SharePoint Online team sites</span></span> |
| <span data-ttu-id="60ac1-123">Bloquear o site</span><span class="sxs-lookup"><span data-stu-id="60ac1-123">Lock down the site</span></span> | <span data-ttu-id="60ac1-124">Grupos do Azure Active Directory (Azure AD) e permissões de site de equipe do SharePoint</span><span class="sxs-lookup"><span data-stu-id="60ac1-124">Azure Active Directory (Azure AD) groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="60ac1-125">Rotular os arquivos do site</span><span class="sxs-lookup"><span data-stu-id="60ac1-125">Label the digital assets of the site</span></span> | <span data-ttu-id="60ac1-126">Rótulos de retenção do Office 365</span><span class="sxs-lookup"><span data-stu-id="60ac1-126">Office 365 retention labels</span></span> |
| <span data-ttu-id="60ac1-127">Bloquear usuários ao enviar arquivos para fora da organização.</span><span class="sxs-lookup"><span data-stu-id="60ac1-127">Block users when sending files outside the organization</span></span> | <span data-ttu-id="60ac1-128">Políticas de Prevenção Contra Perda de Dados (DLP) no Office 365</span><span class="sxs-lookup"><span data-stu-id="60ac1-128">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="60ac1-129">Criptografar todos os arquivos do site</span><span class="sxs-lookup"><span data-stu-id="60ac1-129">Encrypt all of the digital assets of the site</span></span> | <span data-ttu-id="60ac1-130">Sub-rótulos de confidencialidade do Office 365</span><span class="sxs-lookup"><span data-stu-id="60ac1-130">Office 365 sensitivity sublabels</span></span> |
| <span data-ttu-id="60ac1-131">Adicionar permissões aos arquivos do site</span><span class="sxs-lookup"><span data-stu-id="60ac1-131">Add permissions to the digital assets of the site</span></span> | <span data-ttu-id="60ac1-132">Sub-rótulos de confidencialidade do Office 365</span><span class="sxs-lookup"><span data-stu-id="60ac1-132">Office 365 sensitivity sublabels</span></span> |
|||

<span data-ttu-id="60ac1-133">Estas são as configurações para um site do SharePoint seguro.</span><span class="sxs-lookup"><span data-stu-id="60ac1-133">Here is the configuration for a SharePoint Online site.</span></span>

![Os sites do SharePoint para um cenário de dados altamente regulamentados](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="60ac1-135">Este cenário exige que você já tenha implantado:</span><span class="sxs-lookup"><span data-stu-id="60ac1-135">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="60ac1-136">A fase de [identidade](identity-infrastructure.md) e as etapas 1 e 2 da fase de [proteção de informações](infoprotect-infrastructure.md) da infraestrutura de base.</span><span class="sxs-lookup"><span data-stu-id="60ac1-136">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="60ac1-137">[SharePoint](sharepoint-online-onedrive-workload.md).</span><span class="sxs-lookup"><span data-stu-id="60ac1-137">SharePoint</span></span>

<span data-ttu-id="60ac1-138">As fases a seguir o ajudarão a projetar, configurar e direcionar a adoção de sites do SharePoint para dados altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="60ac1-138">The following phases step you through designing, configuring, and driving adoption for SharePoint Online sites and teams for highly regulated data.</span></span>

<span data-ttu-id="60ac1-139">Para ver como a Contoso Corporation, uma organização multinacional fictícia, porém representativa, projetou um site do SharePoint para suas equipes de pesquisa, confira esta [configuração de exemplo](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span><span class="sxs-lookup"><span data-stu-id="60ac1-139">To see how the Contoso Corporation, a fictional but representative multi-national organization, designed a SharePoint Online site for its research teams, see this [example configuration](contoso-sharepoint-online-site-for-highly-confidential-assets.md).</span></span>

## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="60ac1-140">Pré-requisitos de acesso ao dispositivo e identidade</span><span class="sxs-lookup"><span data-stu-id="60ac1-140">Identity and device access prerequisites</span></span>

<span data-ttu-id="60ac1-141">Para proteger o acesso ao site do SharePoint, assegure-se de ter configurado [políticas de identidade e de acesso ao dispositivo](identity-access-policies.md) e as [políticas de acesso recomendadas do SharePoint](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="60ac1-141">To protect access to the team or SharePoint Online site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint Online access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="60ac1-142">Fase 1: Design</span><span class="sxs-lookup"><span data-stu-id="60ac1-142">Phase 1: Design</span></span>

<span data-ttu-id="60ac1-143">Para criar um site do SharePoint para dados altamente regulamentados, você deve primeiro identificar sua finalidade.</span><span class="sxs-lookup"><span data-stu-id="60ac1-143">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="60ac1-144">Por exemplo, o departamento de pesquisa e desenvolvimento de uma organização de manufatura precisa de um site do SharePoint para armazenar especificações de design atuais de produtos existentes e um local para colaborar em novos produtos.</span><span class="sxs-lookup"><span data-stu-id="60ac1-144">To create a SharePoint Online site or team for highly regulated data, you must first identify its purpose. For example, the research and development department of a manufacturing organization needs a SharePoint Online site to store current design specifications for existing products and a place to collaborate on new products. Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span> <span data-ttu-id="60ac1-145">Somente os membros do departamento de Pesquisa e Desenvolvimento e os executivos selecionados terão permissão para acessar o site.</span><span class="sxs-lookup"><span data-stu-id="60ac1-145">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="60ac1-146">Essa finalidade gerará a determinação de itens essenciais de configuração como:</span><span class="sxs-lookup"><span data-stu-id="60ac1-146">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="60ac1-147">O rótulo de retenção do Office 365 para atribuir à parte Documentos do site e às políticas de DLP para o rótulo</span><span class="sxs-lookup"><span data-stu-id="60ac1-147">The Office 365 retention label to assign to the site and the set of DLP policies for the label</span></span>
- <span data-ttu-id="60ac1-148">As configurações de um sub-rótulo de confidencialidade do Office 365 que os usuários aplicam a arquivos altamente confidenciais armazenados no site</span><span class="sxs-lookup"><span data-stu-id="60ac1-148">The settings of an Office 365 sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="60ac1-149">Quando determinado, você usa essas configurações para configurar o site na Fase 2.</span><span class="sxs-lookup"><span data-stu-id="60ac1-149">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="60ac1-150">Etapa 1 rótulos de retenção do Office 365 e políticas DLP</span><span class="sxs-lookup"><span data-stu-id="60ac1-150">Step 2: Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="60ac1-151">Quando aplicada à parte de Documentos de um site de equipe do SharePoint, os rótulos de retenção do Office 365 fornecem um método padrão de classificação de todos os arquivos armazenados no site.</span><span class="sxs-lookup"><span data-stu-id="60ac1-151">When applied to a SharePoint Online team site, Office 365 retention labels provide a default method of classifying all digital assets stored on the site.</span></span>
 
<span data-ttu-id="60ac1-152">Nos sites do SharePoint para dados altamente controlados, você precisa determinar qual rótulo de retenção do Office 365 será usado.</span><span class="sxs-lookup"><span data-stu-id="60ac1-152">For SharePoint Online sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="60ac1-153">Para considerações de design dos rótulos do Office 365, consulte [Rótulos e classificação do Office 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="60ac1-153">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="60ac1-p103">Para proteger informações confidenciais e evitar a divulgação acidental ou intencional, use as políticas DLP. Para obter mais informações, consulte esta [visão geral](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span><span class="sxs-lookup"><span data-stu-id="60ac1-p103">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="60ac1-156">Para sites do SharePoint, você deve configurar uma política DLP do rótulo de retenção do Office 365 atribuído ao site para bloquear usuários quando eles tentam compartilhar arquivos com usuários externos.</span><span class="sxs-lookup"><span data-stu-id="60ac1-156">For SharePoint Online sites for highly regulated data, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share digital assets with external users.</span></span> 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a><span data-ttu-id="60ac1-157">Etapa 2: Sub-rótulo de confidencialidade do Office 365</span><span class="sxs-lookup"><span data-stu-id="60ac1-157">Step 2: Your Office 365 sensitivity sublabel</span></span>

<span data-ttu-id="60ac1-158">Para fornecer criptografia e um conjunto de permissões para seus arquivos mais confidenciais, os usuários devem aplicar um sub-rótulo de confidencialidade do Office 365.</span><span class="sxs-lookup"><span data-stu-id="60ac1-158">To provide encryption and a set of permissions to your most sensitive files, users must apply an Office 365 sensitivity sublabel.</span></span>

<span data-ttu-id="60ac1-159">Existe uma sub-rótulo em um rótulo existente.</span><span class="sxs-lookup"><span data-stu-id="60ac1-159">A sublabel exists under an existing label.</span></span> <span data-ttu-id="60ac1-160">Por exemplo, você pode criar um sub-rótulo de Pesquisa e Desenvolvimento no rótulo Altamente Regulamentado.</span><span class="sxs-lookup"><span data-stu-id="60ac1-160">For example, you can create a Research & Development sublabel under the Highly Regulated label.</span></span> <span data-ttu-id="60ac1-161">Para sites do SharePoint para dados altamente regulamentados, configure as permissões para que somente os membros do site possam abrir e alterar o arquivo ao qual o sub-rótulo está anexado.</span><span class="sxs-lookup"><span data-stu-id="60ac1-161">For SharePoint sites for highly regulated data, you configure the permissions so that only site members can open and change the file to which the sublabel is attached.</span></span>

<span data-ttu-id="60ac1-162">As configurações do sub-rótulo aplicado acompanham o arquivo.</span><span class="sxs-lookup"><span data-stu-id="60ac1-162">The settings of the applied sublabel travel with the file.</span></span> <span data-ttu-id="60ac1-163">Mesmo que ele tenha sido vazado fora do site, somente as contas de usuário autenticado que têm permissões poderão abri-lo.</span><span class="sxs-lookup"><span data-stu-id="60ac1-163">The settings of the applied sub-label travel with the asset. Even if it is downloaded and shared outside the site, only authenticated user accounts that have permissions can open it.</span></span>


### <a name="design-results"></a><span data-ttu-id="60ac1-164">Resultados de design</span><span class="sxs-lookup"><span data-stu-id="60ac1-164">Design results</span></span>

<span data-ttu-id="60ac1-165">Você determinou o seguinte:</span><span class="sxs-lookup"><span data-stu-id="60ac1-165">You have determined the following:</span></span>

- <span data-ttu-id="60ac1-166">O rótulo de retenção apropriado do Office 365 e a política DLP que está associada ao rótulo</span><span class="sxs-lookup"><span data-stu-id="60ac1-166">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="60ac1-167">As configurações do sub-rótulo de confidencialidade do Office 365 que inclui criptografia e permissões</span><span class="sxs-lookup"><span data-stu-id="60ac1-167">The settings of the Office 365 sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="60ac1-168">Fase 2: Configurar</span><span class="sxs-lookup"><span data-stu-id="60ac1-168">Phase 2: Configure</span></span>

<span data-ttu-id="60ac1-169">Nesta fase, você usa as configurações determinadas na Fase 1 e as implementa para criar um site do SharePoint para dados altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="60ac1-169">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint Online site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a><span data-ttu-id="60ac1-170">Etapa 1: Criar um site de equipe do SharePoint privado com proprietários e membros do grupo do Office 365 correspondente</span><span class="sxs-lookup"><span data-stu-id="60ac1-170">Step 1: Create a private SharePoint team site with owners and members of the corresponding Office 365 group</span></span>

<span data-ttu-id="60ac1-171">Siga [essas instruções]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) para criar um site de equipe do SharePoint privado.</span><span class="sxs-lookup"><span data-stu-id="60ac1-171">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="60ac1-172">Etapa 2: Configurar permissões adicionais para o site de equipe do SharePoint</span><span class="sxs-lookup"><span data-stu-id="60ac1-172">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="60ac1-173">No site do SharePoint, defina estas configurações de permissão.</span><span class="sxs-lookup"><span data-stu-id="60ac1-173">From the SharePoint site, configure these permission settings.</span></span>

1.  <span data-ttu-id="60ac1-174">Na barra de ferramentas, clique no ícone Configurações e, em seguida, clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="60ac1-174">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2.  <span data-ttu-id="60ac1-175">No painel **Permissões do site**, clique em **Configurações de permissões avançadas**.</span><span class="sxs-lookup"><span data-stu-id="60ac1-175">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
3.  <span data-ttu-id="60ac1-176">Na nova guia **Permissões** do navegador, clique em **Configurações de Solicitação de Acesso**.</span><span class="sxs-lookup"><span data-stu-id="60ac1-176">On the new **Permissions** tab of your browser, click **Access Request Settings**.</span></span>
4.  <span data-ttu-id="60ac1-177">Na caixa de diálogo **Configurações de Solicitações de Acesso**, desmarque **Permitir que os membros compartilhem o site e arquivos e pastas individuais** e **Permitir solicitações de acesso** (para que todas as três caixas de seleção sejam desmarcadas) e, depois, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="60ac1-177">In the **Access Requests Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow access requests** (so that all three check boxes are cleared), and then click **OK**.</span></span>

<span data-ttu-id="60ac1-178">Com essas configurações, a capacidade de membros do grupo de sites compartilharem o site com outros membros ou de não membros solicitarem acesso ao site é desativada.</span><span class="sxs-lookup"><span data-stu-id="60ac1-178">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="60ac1-179">Etapa 3: Configurar o site para um rótulo de retenção do Office 365</span><span class="sxs-lookup"><span data-stu-id="60ac1-179">Step 2: Configure the site for an Office 365 retention label</span></span>

<span data-ttu-id="60ac1-180">Use as instruções em [Proteger arquivos do SharePoint com rótulos do Office 365 e DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) para:</span><span class="sxs-lookup"><span data-stu-id="60ac1-180">Use the instructions in [Protect SharePoint Online files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="60ac1-181">Crie e publique um rótulo de retenção para dados altamente regulamentados (se necessário).</span><span class="sxs-lookup"><span data-stu-id="60ac1-181">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="60ac1-182">Configure o site para o rótulo de retenção criado na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="60ac1-182">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="60ac1-183">Crie uma política DLP para dados altamente regulamentados que usam o rótulo de retenção criado na etapa 2 e impede que os usuários enviem arquivos fora da organização</span><span class="sxs-lookup"><span data-stu-id="60ac1-183">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="60ac1-184">Etapa 4: Criar um sub-rótulo de confidencialidade do Office 365 para o site</span><span class="sxs-lookup"><span data-stu-id="60ac1-184">Step 4: Create an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="60ac1-185">Ao contrário de um rótulo de confidencialidade para dados altamente regulamentados que qualquer pessoa pode aplicar a qualquer arquivo, um site seguro precisa de seu próprio sub-rótulo, para que os arquivos com o sub-rótulo atribuído:</span><span class="sxs-lookup"><span data-stu-id="60ac1-185">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="60ac1-186">São criptografadas e a criptografia acompanha o arquivo.</span><span class="sxs-lookup"><span data-stu-id="60ac1-186">Are encrypted and the encryption travels with the file.</span></span>
-   <span data-ttu-id="60ac1-187">Contenham permissões personalizadas para que somente os membros do grupo de sites possam abri-lo.</span><span class="sxs-lookup"><span data-stu-id="60ac1-187">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="60ac1-188">Para atingir esse nível adicional de segurança para os arquivos armazenados no site, você deve configurar um novo rótulo de confidencialidade, que é um sub-rótulo do rótulo geral para arquivos altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="60ac1-188">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label that is a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="60ac1-189">Somente os membros do grupo do site poderão vê-lo na lista de sub-rótulos do rótulo altamente regulamentado.</span><span class="sxs-lookup"><span data-stu-id="60ac1-189">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="60ac1-190">Use as instruções [aqui](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para configurar um sub-rótulo da etiqueta que você está usando para arquivos altamente regulamentados com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="60ac1-190">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="60ac1-191">O nome do sub-rótulo contém o nome do site para facilitar a associação ao atribuir o sub-rótulo a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="60ac1-191">The name of the sublabel contains the name of the site for easy association when assign the sublabel to a file.</span></span>
- <span data-ttu-id="60ac1-192">A criptografia está ativada.</span><span class="sxs-lookup"><span data-stu-id="60ac1-192">Encryption is enabled.</span></span>
- <span data-ttu-id="60ac1-193">O grupo de sites tem permissões de Coautoria.</span><span class="sxs-lookup"><span data-stu-id="60ac1-193">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="60ac1-194">Resultados da configuração</span><span class="sxs-lookup"><span data-stu-id="60ac1-194">Configuration results</span></span>

<span data-ttu-id="60ac1-195">Você configurou o seguinte:</span><span class="sxs-lookup"><span data-stu-id="60ac1-195">You have configured the following:</span></span>

- <span data-ttu-id="60ac1-196">Configurações de permissão mais restritivas no site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="60ac1-196">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="60ac1-197">Um rótulo de retenção do Office 365 atribuído à parte de Documentos do site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="60ac1-197">An Office 365 retention label assigned to the SharePoint Online isolated site</span></span>
- <span data-ttu-id="60ac1-198">Uma política DLP para o rótulo de retenção do Office 365</span><span class="sxs-lookup"><span data-stu-id="60ac1-198">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="60ac1-199">Um sub-rótulo de confidencialidade do Office 365 que os usuários podem aplicar aos arquivos mais confidenciais armazenados no site que criptografa o arquivo e permite apenas o acesso de Coautor aos membros do grupo de sites da equipe</span><span class="sxs-lookup"><span data-stu-id="60ac1-199">An Office 365 sensitivity sublabel that users can apply to the most sensitive files stored in the site that encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="60ac1-200">Esta é a configuração resultante.</span><span class="sxs-lookup"><span data-stu-id="60ac1-200">Here is the resulting configuration.</span></span>

![Os sites do SharePoint para um cenário de dados altamente regulamentados](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)


<span data-ttu-id="60ac1-202">Este é um exemplo de um usuário que aplicou o sub-rótulo de confidencialidade a um arquivo armazenado no site.</span><span class="sxs-lookup"><span data-stu-id="60ac1-202">Here is an example of a user that has applied the sensitivity sublabel to a file stored in the site.</span></span>

![Os sites do SharePoint para um cenário de dados altamente regulamentados](./media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="60ac1-204">Fase 3: Gerar adoção do usuário</span><span class="sxs-lookup"><span data-stu-id="60ac1-204">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="60ac1-205">Um site do SharePoint para dados altamente regulamentados só poderá proteger os dados se for usado de maneira consistente para o armazenamento e o acesso a arquivos confidenciais.</span><span class="sxs-lookup"><span data-stu-id="60ac1-205">A SharePoint Online site or team for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive digital assets. This is the hardest phase because it relies on users changing their ways.</span></span> <span data-ttu-id="60ac1-206">Esta é a fase mais difícil porque depende dos usuários de mudar seus hábitos e preferências.</span><span class="sxs-lookup"><span data-stu-id="60ac1-206">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="60ac1-207">Por exemplo, os funcionários que estão acostumados a armazenar arquivos confidenciais em unidades USB ou em soluções de armazenamento pessoal baseadas em nuvem agora precisam armazená-los exclusivamente em um site do SharePoint para obter dados altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="60ac1-207">For example, executives that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint Online site or team for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="60ac1-208">Etapa 1: treinar os usuários</span><span class="sxs-lookup"><span data-stu-id="60ac1-208">Step 1: Train your users</span></span>

<span data-ttu-id="60ac1-209">Depois de concluir a configuração, treine o conjunto de usuários que são membros dos grupos de acesso do site:</span><span class="sxs-lookup"><span data-stu-id="60ac1-209">After completing your configuration, train the set of users who are members of the site access groups:</span></span>

- <span data-ttu-id="60ac1-210">Sobre a importância de usar o novo site para proteger arquivos valiosos e as consequências de um vazamento de dados altamente regulamentados, como ramificações legais, multas regulatórias, ransomware ou perda de vantagem competitiva.</span><span class="sxs-lookup"><span data-stu-id="60ac1-210">On the importance of using the new site or team to protect valuable assets and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="60ac1-211">Como acessar o site e seus arquivos.</span><span class="sxs-lookup"><span data-stu-id="60ac1-211">How to access the site and its assets.</span></span>
- <span data-ttu-id="60ac1-212">Como criar novos arquivos no site e carregar novos arquivos armazenados localmente.</span><span class="sxs-lookup"><span data-stu-id="60ac1-212">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="60ac1-213">Como a política DLP bloqueia o compartilhamento de arquivos externamente por parte do usuário.</span><span class="sxs-lookup"><span data-stu-id="60ac1-213">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="60ac1-214">Como rotular os arquivos mais confidenciais com o sub-rótulo para o site.</span><span class="sxs-lookup"><span data-stu-id="60ac1-214">How to label the most sensitive files with the sublabel for the site.</span></span>
- <span data-ttu-id="60ac1-215">Como o sub-rótulo protege um arquivo, mesmo quando vazado do site.</span><span class="sxs-lookup"><span data-stu-id="60ac1-215">How the sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="60ac1-216">Este treinamento deve incluir exercícios práticos para que os usuários possam experimentar essas operações e os resultados.</span><span class="sxs-lookup"><span data-stu-id="60ac1-216">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="60ac1-217">Etapa 2: conduzir análises periódicas de utilização e arquivos</span><span class="sxs-lookup"><span data-stu-id="60ac1-217">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="60ac1-218">Nas semanas após o treinamento, o administrador do SharePoint para o site do SharePoint pode:</span><span class="sxs-lookup"><span data-stu-id="60ac1-218">In the weeks after training, the SharePoint administrator for the SharePoint Online site or team can:</span></span>

- <span data-ttu-id="60ac1-219">Analisar o uso do site e compará-lo a expectativas de uso.</span><span class="sxs-lookup"><span data-stu-id="60ac1-219">Analyze usage for the site or team and compare it with usage expectations.</span></span>
- <span data-ttu-id="60ac1-220">Verificar se os arquivos altamente confidenciais foram rotulados corretamente com o sub-rótulo de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="60ac1-220">Verify that sensitive or highly regulated files have been properly labeled with the appropriate sensitivity label.</span></span>

<span data-ttu-id="60ac1-221">Repita o treinamento dos usuários conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="60ac1-221">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="60ac1-222">Resultados de adoção do usuário</span><span class="sxs-lookup"><span data-stu-id="60ac1-222">User adoption results</span></span>

<span data-ttu-id="60ac1-223">Os arquivos altamente regulamentados são armazenados exclusivamente em sites do SharePoint para dados altamente regulamentados e os arquivos mais confidenciais têm o sub-rótulo de confidencialidade para o site aplicado.</span><span class="sxs-lookup"><span data-stu-id="60ac1-223">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="60ac1-224">Como a Contoso Corporation implantou o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="60ac1-224">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="60ac1-225">Contoso Corporation é uma corporação fictícia mas representante global do conglomerado de produção com sede em Paris, França.</span><span class="sxs-lookup"><span data-stu-id="60ac1-225">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris, France.</span></span> <span data-ttu-id="60ac1-226">Veja como Contoso projetou, configurou e, em seguida, orientou a adoção de um [site do SharePoint seguro](contoso-sharepoint-online-site-for-highly-confidential-assets.md) para suas equipes de pesquisa em Paris, Moscou, Nova York, Pequim e Bengaluru (Bangalore).</span><span class="sxs-lookup"><span data-stu-id="60ac1-226">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint Online site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="60ac1-227">Confira também</span><span class="sxs-lookup"><span data-stu-id="60ac1-227">See also</span></span>

[<span data-ttu-id="60ac1-228">Guia de implantação</span><span class="sxs-lookup"><span data-stu-id="60ac1-228">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="60ac1-229">Guias de laboratório de teste</span><span class="sxs-lookup"><span data-stu-id="60ac1-229">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

