---
title: Atividades pós-migração para a migração do Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumo: atividades pós-migração depois de mudar do Microsoft Cloud Germany (Microsoft Cloud Deutschland) para Office 365 serviços na nova região do datacenter alemão.'
ms.openlocfilehash: 3659ce8ffa3424c3521c8f8954be88c7d53d0a51
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930410"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="08030-103">Atividades pós-migração para a migração do Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="08030-103">Post-migration activities for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="08030-104">As seções a seguir fornecem atividades pós-migração para vários serviços depois de migrar do Microsoft Cloud Germany (Microsoft Cloud Deutschland) para Office 365 serviços na nova região do datacenter alemão.</span><span class="sxs-lookup"><span data-stu-id="08030-104">The following sections provide post-migration activities for multiple services after moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="08030-105">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="08030-105">Azure AD</span></span>
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a><span data-ttu-id="08030-106">Autenticação federada do Azure AD com o AD FS</span><span class="sxs-lookup"><span data-stu-id="08030-106">Azure AD federated authentication with AD FS</span></span>
<span data-ttu-id="08030-107">**Aplica-se a:** Todos os clientes que usam autenticação federada com o AD FS</span><span class="sxs-lookup"><span data-stu-id="08030-107">**Applies to:** All customers using federated authentication with AD FS</span></span>

| <span data-ttu-id="08030-108">Step(s)</span><span class="sxs-lookup"><span data-stu-id="08030-108">Step(s)</span></span> | <span data-ttu-id="08030-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="08030-109">Description</span></span> | <span data-ttu-id="08030-110">Impacto</span><span class="sxs-lookup"><span data-stu-id="08030-110">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="08030-111">Remova as confianças de terceiros confiável do Microsoft Cloud Deutschland AD FS.</span><span class="sxs-lookup"><span data-stu-id="08030-111">Remove relying party trusts from Microsoft Cloud Deutschland AD FS.</span></span> | <span data-ttu-id="08030-112">Após a conclusão do corte no Azure AD, a organização está usando totalmente os serviços Office 365 e não está mais conectada ao Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="08030-112">After the cut-over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland.</span></span> <span data-ttu-id="08030-113">Neste ponto, o cliente precisa remover a confiança da parte confiável para os pontos de extremidade do Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="08030-113">At this point, the customer needs to remove the relying party trust to the Microsoft Cloud Deutschland endpoints.</span></span> <span data-ttu-id="08030-114">Isso só pode ser feito quando nenhum dos aplicativos do cliente aponta para os pontos de extremidade do Microsoft Cloud Deutschland quando o Azure AD é aproveitado como um Provedor de Identidade (IdP).</span><span class="sxs-lookup"><span data-stu-id="08030-114">This can only be done when none of the customer's applications points to Microsoft Cloud Deutschland endpoints when Azure AD is leveraged as an Identity Provider (IdP).</span></span> | <span data-ttu-id="08030-115">Organizações de Autenticação Federada</span><span class="sxs-lookup"><span data-stu-id="08030-115">Federated Authentication organizations</span></span> | 
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a><span data-ttu-id="08030-116">Aprovações de grupo</span><span class="sxs-lookup"><span data-stu-id="08030-116">Group approvals</span></span>
<span data-ttu-id="08030-117">**Aplica-se a:** Usuários finais cujas solicitações de aprovação de grupo do Azure AD não foram aprovadas nos últimos 30 dias antes da migração</span><span class="sxs-lookup"><span data-stu-id="08030-117">**Applies to:** End-users whose Azure AD group approval requests weren't approved in the last 30 days before migration</span></span> 

| <span data-ttu-id="08030-118">Step(s)</span><span class="sxs-lookup"><span data-stu-id="08030-118">Step(s)</span></span> | <span data-ttu-id="08030-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="08030-119">Description</span></span> | <span data-ttu-id="08030-120">Impacto</span><span class="sxs-lookup"><span data-stu-id="08030-120">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="08030-121">As solicitações para ingressar em um grupo do Azure AD nos últimos 30 dias antes da migração precisarão ser solicitadas novamente se a solicitação original não tiver sido aprovada.</span><span class="sxs-lookup"><span data-stu-id="08030-121">Requests to join an Azure AD group in the last 30 days before migration will need to be requested again if the original request wasn't approved.</span></span> | <span data-ttu-id="08030-122">Os clientes do usuário final precisarão usar o painel do Access para enviar uma solicitação para ingressar em um grupo do Azure AD novamente se essas solicitações não foram aprovadas nos últimos 30 dias antes da migração.</span><span class="sxs-lookup"><span data-stu-id="08030-122">End-user customers will need to use the Access panel to submit a request to join an Azure AD group again if those requests weren't approved in the last 30 days before the migration.</span></span> |  <span data-ttu-id="08030-123">Como usuário final:</span><span class="sxs-lookup"><span data-stu-id="08030-123">As an end-user:</span></span> <ol><li><span data-ttu-id="08030-124">Navegue até [o painel do Access](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span><span class="sxs-lookup"><span data-stu-id="08030-124">Navigate to [Access panel](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span></span></li><li><span data-ttu-id="08030-125">Encontre um grupo do Azure AD para o qual a aprovação de associação estava pendente durante os 30 dias antes da migração.</span><span class="sxs-lookup"><span data-stu-id="08030-125">Find an Azure AD group for which membership approval was pending during the 30 days before migration.</span></span></li><li><span data-ttu-id="08030-126">Solicitação para ingressar no grupo do Azure AD novamente.</span><span class="sxs-lookup"><span data-stu-id="08030-126">Request to join the Azure AD group again.</span></span></li></ol> <span data-ttu-id="08030-127">As solicitações para ingressar em um grupo que estão ativos menos de 30 dias antes da migração não podem ser aprovadas, a menos que sejam solicitadas novamente após a migração.</span><span class="sxs-lookup"><span data-stu-id="08030-127">Requests to join a group that are active less than 30 days before migration cannot be approved, unless they're requested again after migration.</span></span> |
||||

## <a name="custom-dns-updates"></a><span data-ttu-id="08030-128">Atualizações DNS personalizadas</span><span class="sxs-lookup"><span data-stu-id="08030-128">Custom DNS updates</span></span>
<span data-ttu-id="08030-129">**Aplica-se a:**  Todos os clientes gerenciando suas próprias zonas DNS</span><span class="sxs-lookup"><span data-stu-id="08030-129">**Applies to:**  All customer managing their own DNS zones</span></span>

| <span data-ttu-id="08030-130">Step(s)</span><span class="sxs-lookup"><span data-stu-id="08030-130">Step(s)</span></span> | <span data-ttu-id="08030-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="08030-131">Description</span></span> | <span data-ttu-id="08030-132">Impacto</span><span class="sxs-lookup"><span data-stu-id="08030-132">Impact</span></span> |
|:------|:-------|:-------|
| <span data-ttu-id="08030-133">Atualize os serviços DNS locais para Office 365 de serviços.</span><span class="sxs-lookup"><span data-stu-id="08030-133">Update on-premises DNS services for Office 365 services endpoints.</span></span> | <span data-ttu-id="08030-134">As entradas DNS gerenciadas pelo cliente que apontam para o Microsoft Cloud Deutschland precisam ser atualizadas para apontar para os pontos de extremidade Office 365 serviços globais.</span><span class="sxs-lookup"><span data-stu-id="08030-134">Customer-managed DNS entries that point to Microsoft Cloud Deutschland need to be updated to point to the Office 365 Global services endpoints.</span></span> <span data-ttu-id="08030-135">Consulte [Domínios no centro de](https://admin.microsoft.com/Adminportal/Home#/Domains) administração Microsoft 365 e aplique as alterações em sua configuração DNS.</span><span class="sxs-lookup"><span data-stu-id="08030-135">Please refer to [Domains in the Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home#/Domains) and apply the changes in your DNS configuration.</span></span> | <span data-ttu-id="08030-136">A falha ao fazer isso pode resultar em falha do serviço ou de clientes de software.</span><span class="sxs-lookup"><span data-stu-id="08030-136">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||

## <a name="third-party-services"></a><span data-ttu-id="08030-137">Serviços de terceiros</span><span class="sxs-lookup"><span data-stu-id="08030-137">Third-party services</span></span>
<span data-ttu-id="08030-138">**Aplica-se a:** Clientes que usam serviços de terceiros para Office 365 pontos de extremidade de serviços</span><span class="sxs-lookup"><span data-stu-id="08030-138">**Applies to:** Customers using third-party services for Office 365 services endpoints</span></span>

| <span data-ttu-id="08030-139">Step(s)</span><span class="sxs-lookup"><span data-stu-id="08030-139">Step(s)</span></span> | <span data-ttu-id="08030-140">Descrição</span><span class="sxs-lookup"><span data-stu-id="08030-140">Description</span></span> | <span data-ttu-id="08030-141">Impacto</span><span class="sxs-lookup"><span data-stu-id="08030-141">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="08030-142">Atualize parceiros e serviços de terceiros para Office 365 de serviços.</span><span class="sxs-lookup"><span data-stu-id="08030-142">Update partners and third-party services for Office 365 services endpoints.</span></span> | <ul><li><span data-ttu-id="08030-143">Os serviços e parceiros de terceiros que apontam para Office 365 Alemanha precisam ser atualizados para apontar para os pontos de extremidade Office 365 serviços.</span><span class="sxs-lookup"><span data-stu-id="08030-143">Third-party services and partners that point to Office 365 Germany need to be updated to point to the Office 365 services endpoints.</span></span> <span data-ttu-id="08030-144">Exemplo: registre-se de novo, em alinhamento com seus fornecedores e parceiros, a versão do aplicativo de galeria de aplicativos, se disponível.</span><span class="sxs-lookup"><span data-stu-id="08030-144">Example: Re-register, in alignment with your vendors and partners, the gallery app version of applications, if available.</span></span> </li><li><span data-ttu-id="08030-145">Aponte todos os aplicativos personalizados que aproveitam Graph API de `graph.microsoft.de` `graph.microsoft.com` para .</span><span class="sxs-lookup"><span data-stu-id="08030-145">Point all custom applications that leverage Graph API from `graph.microsoft.de` to `graph.microsoft.com`.</span></span> <span data-ttu-id="08030-146">Outras APIs com pontos de extremidade alterados também precisam ser atualizadas, se usadas.</span><span class="sxs-lookup"><span data-stu-id="08030-146">Other APIs with changed endpoints also need to be updated, if leveraged.</span></span> </li><li><span data-ttu-id="08030-147">Altere todos os aplicativos corporativos não de primeira parte para redirecionar para os pontos de extremidade em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="08030-147">Change all non-first-party enterprise applications to redirect to the worldwide endpoints.</span></span> </li></ul>| <span data-ttu-id="08030-148">Ação necessária.</span><span class="sxs-lookup"><span data-stu-id="08030-148">Required action.</span></span> <span data-ttu-id="08030-149">A falha ao fazer isso pode resultar em falha do serviço ou de clientes de software.</span><span class="sxs-lookup"><span data-stu-id="08030-149">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||