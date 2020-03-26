---
title: Sites do SharePoint para dados altamente regulamentados
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- SPO_Content
ms.custom: ''
description: Crie um site de equipe do SharePoint seguro para armazenar seus arquivos mais valiosos e confidenciais.
ms.openlocfilehash: bc1a84fa7437d9b2979e10b352f8a422c457e8a0
ms.sourcegitcommit: 6adfcf042e64b21f09f2b8e072e8eba6d3479e31
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2020
ms.locfileid: "42951977"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a><span data-ttu-id="b0fb6-103">Sites do SharePoint para dados altamente regulamentados</span><span class="sxs-lookup"><span data-stu-id="b0fb6-103">SharePoint sites for highly regulated data</span></span>

<span data-ttu-id="b0fb6-104">*Este cenário aplica-se às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="b0fb6-104">*This scenario applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

<span data-ttu-id="b0fb6-p101">O Microsoft 365 Enterprise inclui um conjunto completo de serviços baseados em nuvem, para que você possa criar, armazenar, proteger e gerenciar seus dados altamente regulamentados armazenados em arquivos. Isso inclui dados que são:</span><span class="sxs-lookup"><span data-stu-id="b0fb6-p101">Microsoft 365 Enterprise includes a full suite of cloud-based services so that you can create, store, secure, and manage your highly regulated data stored in files. This includes data that is:</span></span>

- <span data-ttu-id="b0fb6-107">Sujeitos a regulamentações regionais.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-107">Subject to regional regulations.</span></span>
- <span data-ttu-id="b0fb6-108">Mais importantes de sua organização, como segredos comerciais, financeiros ou informações de recursos humanos e estratégias da organização.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-108">The most valuable data for your organization, such as trade secrets, financial or human resources information, and organization strategy.</span></span>

>[!Note]
> <span data-ttu-id="b0fb6-109">Um cenário semelhante usando o Microsoft Teams esta [aqui](secure-teams-highly-regulated-data-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="b0fb6-109">A similar scenario using Microsoft Teams is [here](secure-teams-highly-regulated-data-scenario.md).</span></span>
>

<span data-ttu-id="b0fb6-110">Um cenário da Microsoft 365 Enterprise baseada na nuvem, que atende a essa necessidade comercial, requer que você:</span><span class="sxs-lookup"><span data-stu-id="b0fb6-110">A Microsoft 365 Enterprise cloud-based scenario that meets this business need requires that you:</span></span>

- <span data-ttu-id="b0fb6-111">Armazene arquivos (documentos, apresentações de slides, planilhas, etc.) em um site de equipe do SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-111">Store files (documents, slide decks, spreadsheets, etc.) in a SharePoint team site.</span></span>
- <span data-ttu-id="b0fb6-112">Bloqueie o site para impedir:</span><span class="sxs-lookup"><span data-stu-id="b0fb6-112">Lock down the site to prevent:</span></span>
  - <span data-ttu-id="b0fb6-113">Acesso a usuários que não são membros do grupo do Office 365 para o site.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-113">Access to users who are not members of the Office 365 group for the site.</span></span>
  - <span data-ttu-id="b0fb6-114">Que membros do site concedam acesso a outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-114">Members of the site from granting access to others.</span></span>
  - <span data-ttu-id="b0fb6-115">Que aqueles que não sejam membros do site solicitem acesso a ele.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-115">Non-members of the site from requesting access to the site.</span></span>
- <span data-ttu-id="b0fb6-116">Configure um rótulo de retenção do Office 365 para seus sites do SharePoint como uma maneira padrão de impedir que os usuários enviem arquivos fora da organização.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-116">Configure an Office 365 retention label for your SharePoint sites as a default way to block users from sending files outside the organization.</span></span>
- <span data-ttu-id="b0fb6-117">Criptografe os arquivos mais confidenciais do site com criptografia que acompanha o arquivo.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-117">Encrypt the most sensitive files of the site with encryption that travels with the file.</span></span>
- <span data-ttu-id="b0fb6-118">Adicione permissões aos arquivos mais confidenciais para que, mesmo que sejam compartilhados fora do site, a abertura do arquivo ainda exija as credenciais válidas de uma conta de usuário que tenha a permissão.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-118">Add permissions to the most sensitive files so that if even if they get shared outside of the site, opening the file still requires the valid credentials of a user account that has permission.</span></span>

<span data-ttu-id="b0fb6-119">A tabela a seguir mapeia os requisitos desse cenário para um recurso do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-119">The following table maps the requirements of this scenario to a feature of Microsoft 365 Enterprise.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="b0fb6-120">**Requisito**</span><span class="sxs-lookup"><span data-stu-id="b0fb6-120">**Requirement**</span></span> | <span data-ttu-id="b0fb6-121">**Recurso do Microsoft 365 Enterprise**</span><span class="sxs-lookup"><span data-stu-id="b0fb6-121">**Microsoft 365 Enterprise feature**</span></span> |
| <span data-ttu-id="b0fb6-122">Armazenar arquivos </span><span class="sxs-lookup"><span data-stu-id="b0fb6-122">Store files</span></span> | <span data-ttu-id="b0fb6-123">Sites de equipe do SharePoint</span><span class="sxs-lookup"><span data-stu-id="b0fb6-123">SharePoint team sites</span></span> |
| <span data-ttu-id="b0fb6-124">Bloquear o site</span><span class="sxs-lookup"><span data-stu-id="b0fb6-124">Lock down the site</span></span> | <span data-ttu-id="b0fb6-125">Grupos do Office 365 e permissões de site de equipe do SharePoint</span><span class="sxs-lookup"><span data-stu-id="b0fb6-125">Office 365 groups and SharePoint team site permissions</span></span> |
| <span data-ttu-id="b0fb6-126">Rotular os arquivos do site</span><span class="sxs-lookup"><span data-stu-id="b0fb6-126">Label the files of the site</span></span> | <span data-ttu-id="b0fb6-127">Rótulos de retenção do Office 365</span><span class="sxs-lookup"><span data-stu-id="b0fb6-127">Office 365 retention labels</span></span> |
| <span data-ttu-id="b0fb6-128">Bloquear usuários ao enviar arquivos para fora da organização.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-128">Block users when sending files outside the organization</span></span> | <span data-ttu-id="b0fb6-129">Políticas de Prevenção Contra Perda de Dados (DLP) no Office 365</span><span class="sxs-lookup"><span data-stu-id="b0fb6-129">Data Loss Prevention (DLP) policies in Office 365</span></span> |
| <span data-ttu-id="b0fb6-130">Criptografar todos os arquivos do site</span><span class="sxs-lookup"><span data-stu-id="b0fb6-130">Encrypt all of the files of the site</span></span> | <span data-ttu-id="b0fb6-131">Rótulos ou sub-rótulos de confidencialidade do Office 365</span><span class="sxs-lookup"><span data-stu-id="b0fb6-131">Office 365 sensitivity labels or sublabels</span></span> |
| <span data-ttu-id="b0fb6-132">Adicionar permissões aos arquivos do site</span><span class="sxs-lookup"><span data-stu-id="b0fb6-132">Add permissions to the files of the site</span></span> | <span data-ttu-id="b0fb6-133">Rótulos ou sub-rótulos de confidencialidade do Office 365</span><span class="sxs-lookup"><span data-stu-id="b0fb6-133">Office 365 sensitivity labels or sublabels</span></span> |
|||

<span data-ttu-id="b0fb6-134">Aqui está um exemplo de configuração para um site do SharePoint seguro.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-134">Here is an example configuration for a secure SharePoint site.</span></span>

![Os sites do SharePoint para um cenário de dados altamente regulamentados](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="b0fb6-136">Este cenário exige que você já tenha implantado:</span><span class="sxs-lookup"><span data-stu-id="b0fb6-136">This scenario requires that you have already deployed:</span></span>

- <span data-ttu-id="b0fb6-137">A fase de [identidade](identity-infrastructure.md) e as etapas 1 e 2 da fase de [proteção de informações](infoprotect-infrastructure.md) da infraestrutura de base.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-137">The [Identity](identity-infrastructure.md) phase and steps 1 and 2 of the [Information protection](infoprotect-infrastructure.md) phase of the foundation infrastructure.</span></span> 
- <span data-ttu-id="b0fb6-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span><span class="sxs-lookup"><span data-stu-id="b0fb6-138">[SharePoint](sharepoint-online-onedrive-workload.md).</span></span>

<span data-ttu-id="b0fb6-139">As fases a seguir o ajudarão a projetar, configurar e direcionar a adoção de sites do SharePoint para dados altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-139">The following phases step you through designing, configuring, and driving adoption for SharePoint sites for highly regulated data.</span></span>

<a name="poster"></a> <span data-ttu-id="b0fb6-140">Confira um resumo de uma página desse cenário no [pôster de sites do SharePoint para dados altamente regulamentados](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf).</span><span class="sxs-lookup"><span data-stu-id="b0fb6-140">For a 1-page summary of this scenario, see the [SharePoint sites for highly regulated data poster](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf).</span></span>

<span data-ttu-id="b0fb6-141">[![Pôster de sites do SharePoint para dados altamente regulamentados](../media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)</span><span class="sxs-lookup"><span data-stu-id="b0fb6-141">[![SharePoint sites for highly regulated data poster](../media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)</span></span>

<span data-ttu-id="b0fb6-142">Você também pode baixar este pôster nos formatos [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf) ou [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx) e imprimir em papel carta, oficial ou tabloide (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="b0fb6-142">You can also download this poster in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf) or [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx) formats and print it on letter, legal, or tabloid (11 x 17)-sized paper.</span></span>


## <a name="identity-and-device-access-prerequisites"></a><span data-ttu-id="b0fb6-143">Pré-requisitos de acesso ao dispositivo e identidade</span><span class="sxs-lookup"><span data-stu-id="b0fb6-143">Identity and device access prerequisites</span></span>

<span data-ttu-id="b0fb6-144">Para proteger o acesso ao site do SharePoint, assegure-se de ter configurado [políticas de identidade e de acesso ao dispositivo](identity-access-policies.md) e as [políticas de acesso recomendadas do SharePoint](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b0fb6-144">To protect access to the SharePoint site, ensure that you have configured [identity and device access policies](identity-access-policies.md) and the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

## <a name="phase-1-design"></a><span data-ttu-id="b0fb6-145">Fase 1: Design</span><span class="sxs-lookup"><span data-stu-id="b0fb6-145">Phase 1: Design</span></span>

<span data-ttu-id="b0fb6-146">Para criar um site do SharePoint para dados altamente regulamentados, você deve primeiro identificar sua finalidade.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-146">To create a SharePoint site for highly regulated data, you must first identify its purpose.</span></span> <span data-ttu-id="b0fb6-147">Por exemplo, o departamento de pesquisa e desenvolvimento de uma organização de manufatura precisa de um site do SharePoint para armazenar especificações de design atuais de produtos existentes e um local para colaborar em novos produtos.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-147">For example, the research and development department of a manufacturing organization needs a SharePoint site to store current design specifications for existing products and a place to collaborate on new products.</span></span> <span data-ttu-id="b0fb6-148">Somente os membros do departamento de Pesquisa e Desenvolvimento e os executivos selecionados terão permissão para acessar o site.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-148">Only members of the Research & Development department and selected executives will be allowed to access the site.</span></span>

<span data-ttu-id="b0fb6-149">Essa finalidade gerará a determinação de itens essenciais de configuração como:</span><span class="sxs-lookup"><span data-stu-id="b0fb6-149">That purpose will drive the determination of essential configuration items such as:</span></span>

- <span data-ttu-id="b0fb6-150">O rótulo de retenção do Office 365 para atribuir à parte Documentos do site e às políticas de DLP para o rótulo</span><span class="sxs-lookup"><span data-stu-id="b0fb6-150">The Office 365 retention label to assign to the Documents portion of the site and DLP policies for the label</span></span>
- <span data-ttu-id="b0fb6-151">As configurações de um sub-rótulo de confidencialidade do Office 365 que os usuários aplicam a arquivos altamente confidenciais armazenados no site</span><span class="sxs-lookup"><span data-stu-id="b0fb6-151">The settings of an Office 365 sensitivity sublabel that users apply to highly sensitive files stored in the site</span></span>

<span data-ttu-id="b0fb6-152">Quando determinado, você usa essas configurações para configurar o site na Fase 2.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-152">Once determined, you use these settings to configure the site in Phase 2.</span></span> 

### <a name="step-1-office-365-retention-labels-and-dlp-policies"></a><span data-ttu-id="b0fb6-153">Etapa 1 rótulos de retenção do Office 365 e políticas DLP</span><span class="sxs-lookup"><span data-stu-id="b0fb6-153">Step 1 Office 365 retention labels and DLP policies</span></span>

<span data-ttu-id="b0fb6-154">Quando aplicada à parte de Documentos de um site de equipe do SharePoint, os rótulos de retenção do Office 365 fornecem um método padrão de classificação de todos os arquivos armazenados no site.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-154">When applied to the Documents portion of a SharePoint team site, Office 365 retention labels provide a default method of classifying all files stored on the site.</span></span>
 
<span data-ttu-id="b0fb6-155">Nos sites do SharePoint para dados altamente controlados, você precisa determinar qual rótulo de retenção do Office 365 será usado.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-155">For SharePoint sites for highly regulated data, you need to determine which Office 365 retention label to use.</span></span>

<span data-ttu-id="b0fb6-156">Para considerações de design dos rótulos do Office 365, consulte [Rótulos e classificação do Office 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span><span class="sxs-lookup"><span data-stu-id="b0fb6-156">For the design considerations of Office 365 labels, see [Office 365 classification and labels](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).</span></span>

<span data-ttu-id="b0fb6-p103">Para proteger informações confidenciais e evitar a divulgação acidental ou intencional, use as políticas DLP. Para obter mais informações, consulte esta [visão geral](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span><span class="sxs-lookup"><span data-stu-id="b0fb6-p103">To protect sensitive information and prevent its accidental or intentional disclosure, you use DLP policies. For more information, see this [overview](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).</span></span>

<span data-ttu-id="b0fb6-159">Para sites do SharePoint, você deve configurar uma política DLP do rótulo de retenção do Office 365 atribuído ao site para bloquear usuários quando eles tentam compartilhar arquivos com usuários externos.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-159">For SharePoint sites, you must configure a DLP policy for the Office 365 retention label assigned to the site to block users when they attempt to share files with external users.</span></span> 

### <a name="step-2-your-office-365-sensitivity-sublabel"></a><span data-ttu-id="b0fb6-160">Etapa 2: Sub-rótulo de confidencialidade do Office 365</span><span class="sxs-lookup"><span data-stu-id="b0fb6-160">Step 2: Your Office 365 sensitivity sublabel</span></span>

<span data-ttu-id="b0fb6-161">Para fornecer criptografia e um conjunto de permissões aos seus arquivos mais confidenciais, os usuários devem aplicar um rótulo ou sub-rótulo de confidencialidade do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-161">To provide encryption and a set of permissions to your most sensitive files, users must apply an Office 365 sensitivity label or sublabel.</span></span> <span data-ttu-id="b0fb6-162">Existe uma sub-rótulo em um rótulo existente.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-162">A sublabel exists under an existing label.</span></span> 

<span data-ttu-id="b0fb6-163">Use um rótulo de confidencialidade quando precisar de um pequeno número de rótulos para de uso global e equipes privadas individuais.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-163">Use a sensitivity label when you need is a small number of labels for both global use and individual private teams.</span></span> <span data-ttu-id="b0fb6-164">Use um sub-rótulo de confidencialidade quando você tiver um grande número de rótulos ou quiser organizar rótulos para sites seguros em seu rótulo altamente regulamentado.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-164">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for secure sites the under your highly regulated label.</span></span> 

<span data-ttu-id="b0fb6-165">As configurações do rótulo ou sub-rótulo aplicado acompanham o arquivo.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-165">The settings of the applied label or sublabel travel with the file.</span></span> <span data-ttu-id="b0fb6-166">Mesmo que ele tenha sido vazado fora do site, somente as contas de usuário autenticado que têm permissões poderão abri-lo.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-166">Even if it is leaked outside the site, only authenticated user accounts that have permissions can open it.</span></span>

### <a name="design-results"></a><span data-ttu-id="b0fb6-167">Resultados de design</span><span class="sxs-lookup"><span data-stu-id="b0fb6-167">Design results</span></span>

<span data-ttu-id="b0fb6-168">Você determinou o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b0fb6-168">You have determined the following:</span></span>

- <span data-ttu-id="b0fb6-169">O rótulo de retenção apropriado do Office 365 e a política DLP que está associada ao rótulo</span><span class="sxs-lookup"><span data-stu-id="b0fb6-169">The appropriate Office 365 retention label and the DLP policy that is associated with the label</span></span>
- <span data-ttu-id="b0fb6-170">As configurações do sub-rótulo de confidencialidade do Office 365 que inclui criptografia e permissões</span><span class="sxs-lookup"><span data-stu-id="b0fb6-170">The settings of the Office 365 sensitivity sublabel that include encryption and permissions</span></span>

## <a name="phase-2-configure"></a><span data-ttu-id="b0fb6-171">Fase 2: Configurar</span><span class="sxs-lookup"><span data-stu-id="b0fb6-171">Phase 2: Configure</span></span>

<span data-ttu-id="b0fb6-172">Nesta fase, você usa as configurações determinadas na Fase 1 e as implementa para criar um site do SharePoint para dados altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-172">In this phase, you take the settings determined in Phase 1 and implement them to create a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-office-365-group"></a><span data-ttu-id="b0fb6-173">Etapa 1: Criar um site de equipe do SharePoint privado com proprietários e membros do grupo do Office 365 correspondente</span><span class="sxs-lookup"><span data-stu-id="b0fb6-173">Step 1: Create a private SharePoint team site with owners and members of the corresponding Office 365 group</span></span>

<span data-ttu-id="b0fb6-174">Siga [essas instruções]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) para criar um site de equipe do SharePoint privado.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-174">Follow [these instructions]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) to create a private SharePoint team site.</span></span>

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a><span data-ttu-id="b0fb6-175">Etapa 2: Configurar permissões adicionais para o site de equipe do SharePoint</span><span class="sxs-lookup"><span data-stu-id="b0fb6-175">Step 2: Configure additional permissions settings for the SharePoint team site</span></span>

<span data-ttu-id="b0fb6-176">No site do SharePoint, defina estas configurações de permissão.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-176">From the SharePoint site, configure these permission settings.</span></span>

1. <span data-ttu-id="b0fb6-177">Na barra de ferramentas, clique no ícone Configurações e, em seguida, clique em **Permissões do site**.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-177">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
2. <span data-ttu-id="b0fb6-178">No painel **Permissões do site**, em **Configurações de Compartilhamento**, clique em **Alterar configurações de compartilhamento**.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-178">In the **Site permissions** pane, under **Sharing Settings**, click **Change sharing settings**.</span></span>
3. <span data-ttu-id="b0fb6-179">Em **Permissões de compartilhamento**, **Somente proprietários do site podem compartilhar arquivos, pastas e o site**.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-179">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**.</span></span>
4. <span data-ttu-id="b0fb6-180">Desative **Permitir solicitações de acesso** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-180">Turn off **Allow access requests**, and then click **Save**.</span></span>

<span data-ttu-id="b0fb6-181">Com essas configurações, a capacidade de membros do grupo de sites compartilharem o site com outros membros ou de não membros solicitarem acesso ao site é desativada.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-181">With these settings, the ability for site group members to share the site with other members or for non-members to request access to the site is disabled.</span></span>

### <a name="step-3-configure-the-site-for-an-office-365-retention-label"></a><span data-ttu-id="b0fb6-182">Etapa 3: Configurar o site para um rótulo de retenção do Office 365</span><span class="sxs-lookup"><span data-stu-id="b0fb6-182">Step 3: Configure the site for an Office 365 retention label</span></span>

<span data-ttu-id="b0fb6-183">Use as instruções em [Proteger arquivos do SharePoint com rótulos do Office 365 e DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) para:</span><span class="sxs-lookup"><span data-stu-id="b0fb6-183">Use the instructions in [Protect SharePoint files with Office 365 labels and DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) to:</span></span>

1. <span data-ttu-id="b0fb6-184">Crie e publique um rótulo de retenção para dados altamente regulamentados (se necessário).</span><span class="sxs-lookup"><span data-stu-id="b0fb6-184">Create and publish a retention label for highly regulated data (if needed).</span></span>
2. <span data-ttu-id="b0fb6-185">Configure o site para o rótulo de retenção criado na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-185">Configure the site for the retention label created in step 1.</span></span>
3. <span data-ttu-id="b0fb6-186">Crie uma política DLP para dados altamente regulamentados que usam o rótulo de retenção criado na etapa 2 e impede que os usuários enviem arquivos fora da organização</span><span class="sxs-lookup"><span data-stu-id="b0fb6-186">Create a DLP policy for highly regulated data that uses the retention label created in step 2 and blocks users from sending files outside the organization</span></span>

#### <a name="step-4-create-an-office-365-sensitivity-sublabel-for-the-site"></a><span data-ttu-id="b0fb6-187">Etapa 4: Criar um sub-rótulo de confidencialidade do Office 365 para o site</span><span class="sxs-lookup"><span data-stu-id="b0fb6-187">Step 4: Create an Office 365 sensitivity sublabel for the site</span></span>

<span data-ttu-id="b0fb6-188">Ao contrário de um rótulo de confidencialidade para dados altamente regulamentados que qualquer pessoa pode aplicar a qualquer arquivo, um site seguro precisa de seu próprio sub-rótulo, para que os arquivos com o sub-rótulo atribuído:</span><span class="sxs-lookup"><span data-stu-id="b0fb6-188">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure site needs its own sublabel so that files with the sublabel assigned:</span></span>

- <span data-ttu-id="b0fb6-189">São criptografadas e a criptografia acompanha o arquivo.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-189">Are encrypted and the encryption travels with the file.</span></span>
- <span data-ttu-id="b0fb6-190">Contenham permissões personalizadas para que somente os membros do grupo de sites possam abri-lo.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-190">Contain custom permissions so that only members of the site group can open it.</span></span>

<span data-ttu-id="b0fb6-191">Para atingir esse nível adicional de segurança para os arquivos armazenados no site, você deve configurar um novo rótulo de confidencialidade ou um sub-rótulo do rótulo geral para arquivos altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-191">To accomplish this additional level of security for files stored in the site, you must configure a new sensitivity label or a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="b0fb6-192">Somente os membros do grupo do site poderão vê-lo na lista de sub-rótulos do rótulo altamente regulamentado.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-192">Only group members for the site will see it in the list of sublabels for the highly regulated label.</span></span>

<span data-ttu-id="b0fb6-193">Use as instruções [aqui](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para configurar um rótulo ou um sub-rótulo do rótulo que você está usando para arquivos altamente regulamentados com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b0fb6-193">Use the instructions [here](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a label or a sublabel of the label you are using for highly regulated files with the following settings:</span></span>

- <span data-ttu-id="b0fb6-194">O nome do rótulo ou sub-rótulo contém o nome do site para facilitar a associação ao atribuir o rótulo ou o sub-rótulo a um arquivo.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-194">The name of the label or sublabel contains the name of the site for easy association when assigning the label or sublabel to a file.</span></span>
- <span data-ttu-id="b0fb6-195">A criptografia está ativada.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-195">Encryption is enabled.</span></span>
- <span data-ttu-id="b0fb6-196">O grupo de sites tem permissões de Coautoria.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-196">The site group has Co-Author permissions.</span></span>

### <a name="configuration-results"></a><span data-ttu-id="b0fb6-197">Resultados da configuração</span><span class="sxs-lookup"><span data-stu-id="b0fb6-197">Configuration results</span></span>

<span data-ttu-id="b0fb6-198">Você configurou o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b0fb6-198">You have configured the following:</span></span>

- <span data-ttu-id="b0fb6-199">Configurações de permissão mais restritivas no site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="b0fb6-199">More restrictive permission settings on the SharePoint site</span></span>
- <span data-ttu-id="b0fb6-200">Um rótulo de retenção do Office 365 atribuído à parte de Documentos do site do SharePoint</span><span class="sxs-lookup"><span data-stu-id="b0fb6-200">An Office 365 retention label assigned to the Documents portion of the SharePoint site</span></span>
- <span data-ttu-id="b0fb6-201">Uma política DLP para o rótulo de retenção do Office 365</span><span class="sxs-lookup"><span data-stu-id="b0fb6-201">A DLP policy for the Office 365 retention label</span></span>
- <span data-ttu-id="b0fb6-202">Um rótulo ou sub-rótulo de confidencialidade do Office 365 que os usuários podem aplicar aos arquivos mais confidenciais armazenados no site, que criptografam o arquivo e permitem apenas o acesso de coautor aos membros do grupo de sites de equipe</span><span class="sxs-lookup"><span data-stu-id="b0fb6-202">An Office 365 sensitivity label or sublabel that users can apply to the most sensitive files stored in the site, which encrypts the file and only allows Co-Author access for members of the team site group</span></span> 

<span data-ttu-id="b0fb6-203">Aqui está a configuração resultante que usa um sub-rótulo do rótulo altamente regulamentado.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-203">Here is the resulting configuration that uses a sublabel of the Highly regulated label.</span></span>

![Os sites do SharePoint para um cenário de dados altamente regulamentados](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

<span data-ttu-id="b0fb6-205">Aqui está um exemplo de usuário que aplicou o sub-rótulo em um arquivo armazenado no site.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-205">Here is an example of a user that has applied the sublabel to a file stored in the site.</span></span>

![Os sites do SharePoint para um cenário de dados altamente regulamentados](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a><span data-ttu-id="b0fb6-207">Fase 3: Gerar adoção do usuário</span><span class="sxs-lookup"><span data-stu-id="b0fb6-207">Phase 3: Drive user adoption</span></span>

<span data-ttu-id="b0fb6-208">Um site do SharePoint para dados altamente regulamentados só poderá proteger os dados se for usado de maneira consistente para o armazenamento e o acesso a arquivos confidenciais.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-208">A SharePoint site for highly regulated data can only protect that data if it is consistently used for storage and access of sensitive files.</span></span> <span data-ttu-id="b0fb6-209">Esta é a fase mais difícil porque depende dos usuários de mudar seus hábitos e preferências.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-209">This is the hardest phase because it relies on users changing their habits and preferences.</span></span> 

<span data-ttu-id="b0fb6-210">Por exemplo, os funcionários que estão acostumados a armazenar arquivos confidenciais em unidades USB ou em soluções de armazenamento pessoal baseadas em nuvem agora precisam armazená-los exclusivamente em um site do SharePoint para obter dados altamente regulamentados.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-210">For example, employees that are used to storing sensitive files on USB drives or on personal cloud-based storage solutions will now have to store them exclusively in a SharePoint site for highly regulated data.</span></span>

### <a name="step-1-train-your-users"></a><span data-ttu-id="b0fb6-211">Etapa 1: treinar os usuários</span><span class="sxs-lookup"><span data-stu-id="b0fb6-211">Step 1: Train your users</span></span>

<span data-ttu-id="b0fb6-212">Depois de concluir sua configuração, treine o conjunto de usuários que são membros do site:</span><span class="sxs-lookup"><span data-stu-id="b0fb6-212">After completing your configuration, train the set of users who are members of the site:</span></span>

- <span data-ttu-id="b0fb6-213">Sobre a importância de usar o novo site para proteger arquivos valiosos e as consequências de um vazamento de dados altamente regulamentados, como ramificações legais, multas regulatórias, ransomware ou perda de vantagem competitiva.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-213">On the importance of using the new site to protect valuable files and the consequences of a highly regulated data leak, such as legal ramifications, regulatory fines, ransomware, or loss of competitive advantage.</span></span>
- <span data-ttu-id="b0fb6-214">Como acessar o site e seus arquivos.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-214">How to access the site and its files.</span></span>
- <span data-ttu-id="b0fb6-215">Como criar novos arquivos no site e carregar novos arquivos armazenados localmente.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-215">How to create new files on the site and upload new files stored locally.</span></span>
- <span data-ttu-id="b0fb6-216">Como a política DLP bloqueia o compartilhamento de arquivos externamente por parte do usuário.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-216">How the DLP policy blocks them from sharing files externally.</span></span>
- <span data-ttu-id="b0fb6-217">Como rotular os arquivos mais sensíveis com o rótulo ou sub-rótulo do site.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-217">How to label the most sensitive files with the label or sublabel for the site.</span></span>
- <span data-ttu-id="b0fb6-218">Como o rótulo ou o sub-rótulo protege um arquivo, mesmo quando vazado do site.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-218">How the label or sublabel protects a file even when it is leaked off the site.</span></span>

<span data-ttu-id="b0fb6-219">Este treinamento deve incluir exercícios práticos para que os usuários possam experimentar essas operações e os resultados.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-219">This training should include hands-on exercises so that the users can experience these operations and their results.</span></span>

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a><span data-ttu-id="b0fb6-220">Etapa 2: conduzir análises periódicas de utilização e arquivos</span><span class="sxs-lookup"><span data-stu-id="b0fb6-220">Step 2: Conduct periodic reviews of usage and files</span></span>

<span data-ttu-id="b0fb6-221">Nas semanas após o treinamento, o administrador do SharePoint para o site do SharePoint pode:</span><span class="sxs-lookup"><span data-stu-id="b0fb6-221">In the weeks after training, the SharePoint administrator for the SharePoint site can:</span></span>

- <span data-ttu-id="b0fb6-222">Analisar o uso do site e compará-lo a expectativas de uso.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-222">Analyze usage for the site and compare it with usage expectations.</span></span>
- <span data-ttu-id="b0fb6-223">Verificar se os arquivos altamente confidenciais foram rotulados corretamente com o rótulo ou o sub-rótulo de confidencialidade.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-223">Verify that highly sensitive files have been properly labeled with the sensitivity label or sublabel.</span></span>

  <span data-ttu-id="b0fb6-224">Você pode ver quais arquivos têm um rótulo atribuído exibindo uma pasta no SharePoint Online e adicionando a coluna **Confidencialidade**através da opção **Mostrar/ocultar colunas** em **Adicionar coluna**.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-224">You can see which files have a label assigned by viewing a folder in SharePoint and adding the **Sensitivity** column through the **Show/hide columns** option of **Add column**.</span></span>


<span data-ttu-id="b0fb6-225">Repita o treinamento dos usuários conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-225">Retrain your users as needed.</span></span>

### <a name="user-adoption-results"></a><span data-ttu-id="b0fb6-226">Resultados de adoção do usuário</span><span class="sxs-lookup"><span data-stu-id="b0fb6-226">User adoption results</span></span>

<span data-ttu-id="b0fb6-227">Arquivos altamente regulamentados são armazenados exclusivamente em sites do SharePoint para dados altamente regulamentados e os arquivos mais confidenciais possuem o rótulo ou sub-rótulo de confidencialidade do site aplicado.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-227">Highly regulated files are stored exclusively on SharePoint sites for highly regulated data and the most sensitive files have the sensitivity label or sublabel for the site applied.</span></span>

## <a name="how-the-contoso-corporation-used-a-sharepoint-site-for-highly-regulated-data"></a><span data-ttu-id="b0fb6-228">Como a Contoso Corporation usou um site do SharePoint para dados altamente regulamentados</span><span class="sxs-lookup"><span data-stu-id="b0fb6-228">How the Contoso Corporation used a SharePoint site for highly regulated data</span></span>

<span data-ttu-id="b0fb6-229">A Contoso Corporation é um conglomerado de fabricação global fictício, mas representativo.</span><span class="sxs-lookup"><span data-stu-id="b0fb6-229">The Contoso Corporation is a fictional but representative global manufacturing conglomerate.</span></span> <span data-ttu-id="b0fb6-230">Veja como Contoso projetou, configurou e, em seguida, orientou a adoção de um [site do SharePoint seguro](contoso-sharepoint-online-site-for-highly-confidential-assets.md) para suas equipes de pesquisa em Paris, Moscou, Nova York, Pequim e Bengaluru (Bangalore).</span><span class="sxs-lookup"><span data-stu-id="b0fb6-230">See how Contoso designed, configured, and then drove the adoption of a [secure SharePoint site](contoso-sharepoint-online-site-for-highly-confidential-assets.md) for their research teams in Paris, Moscow, New York, Beijing, and Bangalore.</span></span> 

## <a name="see-also"></a><span data-ttu-id="b0fb6-231">Confira também</span><span class="sxs-lookup"><span data-stu-id="b0fb6-231">See also</span></span>

[<span data-ttu-id="b0fb6-232">Microsoft Teams para dados altamente regulamentados</span><span class="sxs-lookup"><span data-stu-id="b0fb6-232">Teams for highly regulated data</span></span>](secure-teams-highly-regulated-data-scenario.md)

[<span data-ttu-id="b0fb6-233">Cargas de trabalho e cenários do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b0fb6-233">Microsoft 365 Enterprise workloads and scenarios</span></span>](deploy-workloads.md)

<span data-ttu-id="b0fb6-234">[Biblioteca de produtividade do Microsoft 365](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="b0fb6-234">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>

[<span data-ttu-id="b0fb6-235">Guia de implantação</span><span class="sxs-lookup"><span data-stu-id="b0fb6-235">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)
