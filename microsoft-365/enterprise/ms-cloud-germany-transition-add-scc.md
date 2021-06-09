---
title: Informações sobre a experiência de Descoberta e Durante a migração do Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
description: 'Resumo: etapas de migração de Descoberta EDiscovery para a migração do Microsoft Cloud Deutschland.'
ms.openlocfilehash: 0128c8563b2043e4ec41d2c5ab1b208bd3977511
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844245"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="dd175-103">Informações sobre a experiência de Descoberta e durante a migração do Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="dd175-103">Information about the eDiscovery experience during the migration from Microsoft Cloud Deutschland</span></span>
<span data-ttu-id="dd175-104">As seções a seguir fornecem informações adicionais sobre a experiência de Descoberta Online ao mudar do Microsoft Cloud Germany (Microsoft Cloud Deutschland) para Office 365 serviços na nova região do datacenter alemão.</span><span class="sxs-lookup"><span data-stu-id="dd175-104">The following sections provide additional information about the eDiscovery experience when moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="ediscovery-administration-until-phase-4"></a><span data-ttu-id="dd175-105">Administração de Descoberta e até a fase 4</span><span class="sxs-lookup"><span data-stu-id="dd175-105">eDiscovery administration until phase 4</span></span>
<span data-ttu-id="dd175-106">Até a fase 4, o Centro de Segurança e Conformidade estará totalmente disponível.</span><span class="sxs-lookup"><span data-stu-id="dd175-106">Until phase 4, the Security and Compliance Center will be fully available.</span></span> <span data-ttu-id="dd175-107">Todo o conteúdo ainda permanece no Microsoft Cloud Germany e é gerenciável pelo Centro de Conformidade e Segurança do Microsoft Cloud Germany ( https://protection.office.de/) .</span><span class="sxs-lookup"><span data-stu-id="dd175-107">All content still remains in the Microsoft Cloud Germany and is manageable by the Microsoft Cloud Germany Security and Compliance Center (https://protection.office.de/).</span></span>

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a><span data-ttu-id="dd175-108">Experiência de Descoberta e Entre a fase 4 até o final da fase 9</span><span class="sxs-lookup"><span data-stu-id="dd175-108">eDiscovery experience between phase 4 until the the end of phase 9</span></span>
<span data-ttu-id="dd175-109">Desde o início da fase 4 até a conclusão da fase 9, as pesquisas de Descoberta Virtual falharão ou retornarão 0 resultados para os locais do SharePoint Online, OneDrive for Business e Exchange Online que foram migrados.</span><span class="sxs-lookup"><span data-stu-id="dd175-109">From the beginning of phase 4 until phase 9 is completed, eDiscovery searches will fail or return 0 results for SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated.</span></span>

> [!NOTE]
> <span data-ttu-id="dd175-110">Durante [a](/microsoft-365/compliance/manage-legal-investigations)migração, os clientes podem continuar a criar casos, regiões, pesquisas e exportações no Centro de Conformidade & Segurança, incluindo [Pesquisa de Conteúdo.](/microsoft-365/compliance/search-for-content)</span><span class="sxs-lookup"><span data-stu-id="dd175-110">During migration, customers can continue to create cases, holds, searches, and exports in the [Security & Compliance Center](/microsoft-365/compliance/manage-legal-investigations), including [Content Search](/microsoft-365/compliance/search-for-content).</span></span> <span data-ttu-id="dd175-111">No entanto, pesquisas em SharePoint Online, OneDrive for Business e Exchange Online locais que foram migrados retornarão 0 resultados ou produzirão um erro.</span><span class="sxs-lookup"><span data-stu-id="dd175-111">However, searches against SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated will either return 0 results or produce an error.</span></span>

<span data-ttu-id="dd175-112">Caso uma pesquisa retorne zero resultados ou um erro durante a migração, faça a seguinte ação para SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="dd175-112">In the event that a search returns zero results or an error during migration, please take the following action for SharePoint Online:</span></span>

- <span data-ttu-id="dd175-113">Baixe sites diretamente do site SharePoint Online ou OneDrive for Business seguindo as instruções em Baixar arquivos e pastas do [OneDrive ou SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05).</span><span class="sxs-lookup"><span data-stu-id="dd175-113">Download sites directly from the SharePoint Online or OneDrive for Business site by following the instructions in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05).</span></span> <span data-ttu-id="dd175-114">Esse método exigirá SharePoint de administrador online ou permissões somente leitura no site.</span><span class="sxs-lookup"><span data-stu-id="dd175-114">This method will require SharePoint Online administrator permissions or read-only permissions on the site.</span></span>
- <span data-ttu-id="dd175-115">Se os limites são excedido, conforme explicado em Baixar arquivos e pastas do OneDrive ou [SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), os clientes poderão usar o cliente de sincronização do OneDrive for Business seguindo as diretrizes em [Sincronizar](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)arquivos SharePoint e Teams com seu computador.</span><span class="sxs-lookup"><span data-stu-id="dd175-115">If limits are exceeded, as explained in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), customers can use the OneDrive for Business sync client by following the guidance in [Sync SharePoint and Teams files with your computer](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88).</span></span>

- <span data-ttu-id="dd175-116">Para obter mais informações, [consulte Descoberta Eletrônica In-loco em Exchange Server](/Exchange/policy-and-compliance/ediscovery/ediscovery).</span><span class="sxs-lookup"><span data-stu-id="dd175-116">For more information, see  [In-Place eDiscovery in Exchange Server](/Exchange/policy-and-compliance/ediscovery/ediscovery).</span></span>


## <a name="ediscovery-administration-after-phase-9"></a><span data-ttu-id="dd175-117">Administração de Descobertas EDiscovery após a fase 9</span><span class="sxs-lookup"><span data-stu-id="dd175-117">eDiscovery administration after phase 9</span></span>

<span data-ttu-id="dd175-118">**Aplica-se a:** Todos os clientes que usam a Descoberta Bancária</span><span class="sxs-lookup"><span data-stu-id="dd175-118">**Applies to:** All customers using eDiscovery</span></span>

<span data-ttu-id="dd175-119">Na fase 9, as etapas finais para mover para a nova região do datacenter alemão serão concluídas.</span><span class="sxs-lookup"><span data-stu-id="dd175-119">In phase 9, the final steps for moving to the new German datacenter region will be completed.</span></span> <span data-ttu-id="dd175-120">Nesta fase, todos os componentes de serviço restantes serão migrados.</span><span class="sxs-lookup"><span data-stu-id="dd175-120">In this phase, all remaining service components will be migrated.</span></span>
<span data-ttu-id="dd175-121">Após a fase 9, o uso do Centro de Segurança e Conformidade no Microsoft Cloud Germany (protection.office.de) não é mais suportado.</span><span class="sxs-lookup"><span data-stu-id="dd175-121">After phase 9, using the Security and Compliance Center in Microsoft Cloud Germany (protection.office.de) is no longer supported.</span></span> <span data-ttu-id="dd175-122">Em vez disso, use o novo [Centro de Segurança](https://security.microsoft.com/) ou Centro de [Conformidade.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="dd175-122">Please use the new [Security Center](https://security.microsoft.com/) or [Compliance Center](https://compliance.microsoft.com/) instead.</span></span> <span data-ttu-id="dd175-123">Todos os dados foram migrados para os novos portais de administração.</span><span class="sxs-lookup"><span data-stu-id="dd175-123">All data have been migrated to the new admin portals.</span></span>

| <span data-ttu-id="dd175-124">Step(s)</span><span class="sxs-lookup"><span data-stu-id="dd175-124">Step(s)</span></span> | <span data-ttu-id="dd175-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="dd175-125">Description</span></span> | <span data-ttu-id="dd175-126">Impacto</span><span class="sxs-lookup"><span data-stu-id="dd175-126">Impact</span></span> |
|:-------|:-------|:-------|
|  <span data-ttu-id="dd175-127">Todos SharePoint online, OneDrive for Business e Exchange Online locais foram migrados juntamente com o Centro de Conformidade e Segurança (SCC).</span><span class="sxs-lookup"><span data-stu-id="dd175-127">All SharePoint Online, OneDrive for Business, and Exchange Online locations have been migrated along with the Security and Compliance Center (SCC).</span></span> | <span data-ttu-id="dd175-128">Todas as atividades de Descoberta Externa devem ser executados do locatário em todo o mundo.</span><span class="sxs-lookup"><span data-stu-id="dd175-128">All eDiscovery activity should be run from the worldwide tenant.</span></span> <span data-ttu-id="dd175-129">As pesquisas agora terão 100% de êxito.</span><span class="sxs-lookup"><span data-stu-id="dd175-129">Searches will now be 100% successful.</span></span> <span data-ttu-id="dd175-130">Quaisquer falhas ou erros devem seguir os canais de suporte normais.</span><span class="sxs-lookup"><span data-stu-id="dd175-130">Any failures or errors should follow normal support channels.</span></span> | <span data-ttu-id="dd175-131">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dd175-131">None</span></span> |
||||

### <a name="ediscovery-retention-policy"></a><span data-ttu-id="dd175-132">Política de Retenção de Descoberta Externa</span><span class="sxs-lookup"><span data-stu-id="dd175-132">eDiscovery Retention Policy</span></span>
<span data-ttu-id="dd175-133">**Aplica-se a:**  Todos os clientes que aplicaram uma política de retenção como parte das etapas de pré-migração</span><span class="sxs-lookup"><span data-stu-id="dd175-133">**Applies to:**  All customers who applied a retention policy as part of the pre-migration steps</span></span>

| <span data-ttu-id="dd175-134">Step(s)</span><span class="sxs-lookup"><span data-stu-id="dd175-134">Step(s)</span></span> | <span data-ttu-id="dd175-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="dd175-135">Description</span></span> | <span data-ttu-id="dd175-136">Impacto</span><span class="sxs-lookup"><span data-stu-id="dd175-136">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="dd175-137">Remover políticas de retenção em toda a organização que foram criadas durante etapas de pré-migração</span><span class="sxs-lookup"><span data-stu-id="dd175-137">Remove organization-wide retention policies that were created during pre-migration steps</span></span> | <span data-ttu-id="dd175-138">Os clientes podem remover as políticas de retenção em toda a organização que foram criadas durante o trabalho de pré-migração dos clientes.</span><span class="sxs-lookup"><span data-stu-id="dd175-138">Customers can remove the organization-wide retention policies that were created during the customers' pre-migration work.</span></span> | <span data-ttu-id="dd175-139">Nenhum</span><span class="sxs-lookup"><span data-stu-id="dd175-139">None</span></span> |
||||
