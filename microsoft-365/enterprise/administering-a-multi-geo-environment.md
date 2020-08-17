---
title: Administrar um ambiente multigeográfico
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Os administradores podem aprender a administrar o SharePoint e os serviços do OneDrive em um ambiente multigeográfico.
ms.openlocfilehash: 1b6d2cb1cb9511677f717f0e58553abc4473e1ad
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686916"
---
# <a name="administering-a-multi-geo-environment"></a><span data-ttu-id="c1b4e-103">Administrar um ambiente multigeográfico</span><span class="sxs-lookup"><span data-stu-id="c1b4e-103">Administering a multi-geo environment</span></span>

<span data-ttu-id="c1b4e-104">A seguir, veja como os serviços do Microsoft 365 funcionam em um ambiente com várias regiões geográficas.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-104">Here's a look at how Microsoft 365 services work in a multi-geo environment.</span></span>

## <a name="audit-log-search"></a><span data-ttu-id="c1b4e-105">Pesquisa de log de auditoria</span><span class="sxs-lookup"><span data-stu-id="c1b4e-105">Audit log search</span></span>

<span data-ttu-id="c1b4e-106">Um [Log de auditoria](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c) unificado para todas as localizações por satélite está disponível na página de pesquisa do log de auditoria do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-106">A unified [Audit log](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c) for all your satellite locations is available from the Microsoft 365 audit log search page.</span></span> <span data-ttu-id="c1b4e-107">Você pode ver todas as entradas do log de auditoria nas localizações geográficas, por exemplo, atividades dos usuários das localizações NAM e EUR serão exibidos em um modo de exibição de organograma e você poderá aplicar os filtros existentes para ver atividades de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-107">You can see all the audit log entries from across geo locations, for example, NAM & EUR users' activities will show up in one org view and then you can apply existing filters to see specific user's activities.</span></span>

## <a name="bcs-secure-store-apps"></a><span data-ttu-id="c1b4e-108">BCS, Repositório Seguro, Aplicativos</span><span class="sxs-lookup"><span data-stu-id="c1b4e-108">BCS, Secure Store, Apps</span></span>

<span data-ttu-id="c1b4e-109">A BCS, o Repositório Seguro e os Aplicativos têm instâncias geográficas em cada localização satélite e portanto, o administrador do SharePoint Online deve gerenciar e configurar esses serviços separadamente para cada localização satélite.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-109">BCS, Secure Store, and Apps all have separate instances in each satellite location, therefore the SharePoint Online administrator should manage and configure these services separately from each satellite location.</span></span>

## <a name="ediscovery"></a><span data-ttu-id="c1b4e-110">Descoberta eletrônica</span><span class="sxs-lookup"><span data-stu-id="c1b4e-110">eDiscovery</span></span> 

<span data-ttu-id="c1b4e-111">Por padrão, um Administrador ou Gerente de Descoberta Eletrônica de um locatário multigeográfico só poderá realizar a descoberta eletrônica na localização central desse locatário.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-111">By default, an eDiscovery Manager or Administrator of a multi-geo tenant will be able to conduct eDiscovery only in the central location of that tenant.</span></span> <span data-ttu-id="c1b4e-112">O administrador global do Office 365 deve atribuir permissões de gerente de Descoberta Eletrônica para permitir que outras pessoas possam realizá-la e atribuir o parâmetro "Região" no Filtro de Segurança e Conformidade deles, para especificar a região como uma localização no satélite para a realização da Descoberta. Caso contrário, a Descoberta Eletrônica não será realizada para nenhuma localização no satélite.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-112">The Office 365 global administrator must assign eDiscovery Manager permissions to allow others to perform eDiscovery and assign a "Region" parameter in their applicable Compliance Security Filter to specify the region for conducting eDiscovery as satellite location, otherwise no eDiscovery will be carried out for the satellite location.</span></span> <span data-ttu-id="c1b4e-113">Para configurar o Filtro de Segurança de Conformidade para uma Região, consulte [Configurar a Descoberta Eletrônica Multigeográfica do Office 365](multi-geo-ediscovery-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="c1b4e-113">To configure the Compliance Security Filter for a Region, see [Configure Office 365 Multi-Geo eDiscovery](multi-geo-ediscovery-configuration.md).</span></span>

## <a name="exchange-mailboxes"></a><span data-ttu-id="c1b4e-114">Caixas de correio do Exchange</span><span class="sxs-lookup"><span data-stu-id="c1b4e-114">Exchange mailboxes</span></span>

<span data-ttu-id="c1b4e-115">As caixas de correio dos usuários do Exchange são movidas automaticamente se sua PDL for alterado.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-115">Users' Exchange mailboxes are moved automatically if their PDL is changed.</span></span> <span data-ttu-id="c1b4e-116">Quando uma nova caixa de correio é criada, ela está provisionada ao PDL do usuário ou à localização central se nenhum valor foi definido para o PDL do usuário.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-116">When a new mailbox is created, it is provisioned to the user's PDL or to the central location if no value has been set for the user's PDL.</span></span>

## <a name="information-protection-ip-data-loss-prevention-dlp-policy"></a><span data-ttu-id="c1b4e-117">Política de Prevenção contra Perda de Dados (DLP) e Proteção da Informação (IP). </span><span class="sxs-lookup"><span data-stu-id="c1b4e-117">Information Protection (IP) Data Loss Prevention (DLP) Policy</span></span>

<span data-ttu-id="c1b4e-118">Você pode definir sua política DLP IP para o OneDrive for Business, SharePoint e Exchange no centro de Segurança e Conformidade políticas de definição de escopo, conforme necessário, para todo locatário ou para os usuários aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-118">You can set your IP DLP policies for OneDrive for Business, SharePoint, and Exchange in the Security and Compliance center, scoping policies as needed to the whole tenant or to applicable users.</span></span> <span data-ttu-id="c1b4e-119">Por exemplo: se você quiser selecionar uma política para um usuário em uma localização via satélite, selecione para aplicar a política para o OneDrive específico e insira a url do OneDrive do usuário.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-119">For example: If you wish to select a policy for a user in a satellite location, select to apply the policy to a specific OneDrive and enter the user's OneDrive url.</span></span> <span data-ttu-id="c1b4e-120">Confira [Visão geral das políticas de prevenção contra perda de dados](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) para instruções gerais ao criar políticas DLP.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-120">See [Overview of data loss prevention policies](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) for general guidance in creating DLP policies.</span></span>

<span data-ttu-id="c1b4e-121">As políticas de DLP são sincronizadas automaticamente de acordo com a aplicabilidade delas a cada localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-121">The DLP policies are automatically synchronized based on their applicability to each geo location.</span></span>

<span data-ttu-id="c1b4e-122">A implementação de políticas de Prevenção contra Perda de Dados e Proteção da Informação para todos os usuários em uma localização geográfica não é uma opção disponível na IU. Em vez disso, é preciso selecionar as contas em que se deseja aplicar a política ou aplicá-la de modo global a todas as contas.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-122">Implementing Information Protection and Data Loss prevention policies to all users in a geo location is not an option available in the UI, instead you must select the applicable accounts for the policy or apply the policy globally to all accounts.</span></span>

## <a name="microsoft-flow"></a><span data-ttu-id="c1b4e-123">Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="c1b4e-123">Microsoft Flow</span></span>

<span data-ttu-id="c1b4e-124">Fluxos criados para localização via satélite usarão o ponto de extremidade localizado na localização geográfica padrão do locatário.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-124">Flows created for the satellite location will use the end point located in the default geo location for the tenant.</span></span>  <span data-ttu-id="c1b4e-125">Microsoft Flow não é um serviço Multigeográfico.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-125">Microsoft Flow is not a Multi-Geo service.</span></span> 

## <a name="microsoft-powerapps"></a><span data-ttu-id="c1b4e-126">Microsoft PowerApps</span><span class="sxs-lookup"><span data-stu-id="c1b4e-126">Microsoft PowerApps</span></span>

<span data-ttu-id="c1b4e-127">PowerApps criados para localização via satélite usarão o ponto de extremidade localizado na localização central do locatário.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-127">PowerApps created for the satellite location will use the end point located in the central location for the tenant.</span></span> <span data-ttu-id="c1b4e-128">Microsoft PowerApps não é um serviço Multigeográfico.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-128">Microsoft PowerApps is not a Multi-Geo service.</span></span> 

## <a name="onedrive-administrator-experience"></a><span data-ttu-id="c1b4e-129">Experiência de Administrador do OneDrive</span><span class="sxs-lookup"><span data-stu-id="c1b4e-129">OneDrive Administrator Experience</span></span>

<span data-ttu-id="c1b4e-p107">O [Centro de Administração do OneDrive](https://admin.onedrive.com) tem uma guia de **localizações geográficas** na navegação à esquerda, que apresenta um mapa com os locais onde é possível exibir e gerenciar suas localizações geográficas. Use essa página para adicionar ou excluir as localizações geográficas de seu locatário.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-p107">The [OneDrive admin center](https://admin.onedrive.com) has a **Geo locations** tab in the left navigation which features a geo locations map where you can view and manage your geo locations. Use this page to add or delete geo locations for your tenant.</span></span>

## <a name="security-and-compliance-admin-center"></a><span data-ttu-id="c1b4e-132">Centro de Administração de Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="c1b4e-132">Security and Compliance Admin Center</span></span>

<span data-ttu-id="c1b4e-133">Há um centro de conformidade central para um locatário multigeográfico: [Centro de conformidade e segurança do Microsoft 365](https://protection.office.com/?rfr=AdminCenter\#/homepage).</span><span class="sxs-lookup"><span data-stu-id="c1b4e-133">There is one central compliance center for a multi-geo tenant: [Microsoft 365 Security & Compliance Center](https://protection.office.com/?rfr=AdminCenter\#/homepage).</span></span>

## <a name="sharepoint-storage-quota"></a><span data-ttu-id="c1b4e-134">Cota de armazenamento do SharePoint</span><span class="sxs-lookup"><span data-stu-id="c1b4e-134">SharePoint storage quota</span></span>

<span data-ttu-id="c1b4e-135">Por padrão, todas as localizações geográficas de um ambiente multigeográfico compartilham a cota de armazenamento disponível do locatário.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-135">By default, all geo locations of a multi-geo environment share the available tenant storage quota.</span></span>  <span data-ttu-id="c1b4e-136">Também é possível gerenciar a cota de armazenamento alocando uma cota específica de uma localização geográfica específica.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-136">You can also manage the storage quota by allocating a specific quota for a particular geo location.</span></span> <span data-ttu-id="c1b4e-137">Para saber mais, confira [Cotas de armazenamento do SharePoint em ambientes de multigeográfico](sharepoint-multi-geo-storage-quota.md).</span><span class="sxs-lookup"><span data-stu-id="c1b4e-137">For more information, see [SharePoint storage quotas in multi-geo environments](sharepoint-multi-geo-storage-quota.md).</span></span>

## <a name="sharing"></a><span data-ttu-id="c1b4e-138">Compartilhamento</span><span class="sxs-lookup"><span data-stu-id="c1b4e-138">Sharing</span></span>

<span data-ttu-id="c1b4e-139">Os administradores podem configurar e gerenciar políticas de compartilhamento para cada localização.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-139">Administrators can set and manage sharing policies for each of their locations.</span></span> <span data-ttu-id="c1b4e-140">Os sites do OneDrive e do SharePoint em cada localização geográfica aceita apenas as configurações de compartilhamen específica da área geográfica correspondente.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-140">The OneDrive and SharePoint sites in each geo location will honor only the corresponding geo specific sharing settings.</span></span> <span data-ttu-id="c1b4e-141">(Por exemplo, você pode permitir o [compartilhamento externo](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) para a localização central, mas não a localização via satélite ou vice-versa.) Observe que as configurações de compartilhamento não permitem configurar limitações de compartilhamento entre localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-141">(For example, you can allow [external sharing](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) for your central location, but not for your satellite location or vice versa.) Note that the sharing settings do not allow configuring sharing limitations between geo locations.</span></span>

## <a name="taxonomy"></a><span data-ttu-id="c1b4e-142">Taxonomia</span><span class="sxs-lookup"><span data-stu-id="c1b4e-142">Taxonomy</span></span>

<span data-ttu-id="c1b4e-143">Oferecemos suporte para uma visão completa [taxonomia](https://docs.microsoft.com/sharepoint/managed-metadata) para metadados gerenciados por empresas em localizações geográficas com o mestre hospedado na localização central da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-143">We support a unified [taxonomy](https://docs.microsoft.com/sharepoint/managed-metadata) for enterprise managed metadata across geo locations, with the master being hosted in the central location for your company.</span></span> <span data-ttu-id="c1b4e-144">Recomendamos que você gerencie sua taxonomia global de uma localização central e apenas adicione termos específicos de localização para a Taxonomia da localização via satélite.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-144">We recommend that you manage your global taxonomy from the central location and only add location-specific terms to the satellite location's Taxonomy.</span></span> <span data-ttu-id="c1b4e-145">Termos de taxonomia global serão sincronizadas para as ocalizações via satélite.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-145">Global taxonomy terms will synchronize to the satellite locations.</span></span>

<span data-ttu-id="c1b4e-146">Confira [Gerenciar metadados em um locatário multigeográfico](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-managedmetadata) para saber mais e para obter instruções do desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-146">See [Manage metadata in a multi-geo tenant](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-managedmetadata) for additional details and for developer guidance.</span></span>

## <a name="user-profile-application"></a><span data-ttu-id="c1b4e-147">Aplicativo de Perfil de Usuário</span><span class="sxs-lookup"><span data-stu-id="c1b4e-147">User Profile Application</span></span>

<span data-ttu-id="c1b4e-148">Há um [aplicativo de perfil de usuário](https://docs.microsoft.com/sharepoint/manage-user-profiles) em cada localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-148">There is a [user profile application](https://docs.microsoft.com/sharepoint/manage-user-profiles) in each geo location.</span></span> <span data-ttu-id="c1b4e-149">As informações de perfil de cada usuário estão hospedadas na localização geográfica dele e ficam disponíveis para o administrador daquela localização.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-149">Each user's profile information is hosted in their geo location and available to the administrator for that geo location.</span></span>

<span data-ttu-id="c1b4e-150">Se houver propriedades de perfil personalizadas, recomendamos que você use o mesmo esquema de perfil nas localizações e popule as propriedades personalizadas em cada uma delas ou nas que forem necessárias. </span><span class="sxs-lookup"><span data-stu-id="c1b4e-150">If you have custom profile properties, then we recommend that you use the same profile schema across geographies and populate your custom profile properties either in all geo locations or where needed.</span></span> <span data-ttu-id="c1b4e-151">Para obter instruções sobre como preencher dados de perfil de usuário de forma programática, confira a [API de Atualização de Perfil de Usuário em Massa](https://docs.microsoft.com/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online).</span><span class="sxs-lookup"><span data-stu-id="c1b4e-151">For guidance regarding how to populate user profile data programmatically, please refer to the [Bulk User Profile Update API](https://docs.microsoft.com/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online).</span></span>

<span data-ttu-id="c1b4e-152">Confira [Trabalhar com perfis de usuários em um locatário multigeográfico](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-userprofileexperience) para saber mais e para obter instruções do desenvolvedor.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-152">See [Work with user profiles in a multi-geo tenant](https://docs.microsoft.com/sharepoint/dev/solution-guidance/multigeo-userprofileexperience) for additional details and for developer guidance.</span></span>

## <a name="video-portal"></a><span data-ttu-id="c1b4e-153">Portal de Vídeo</span><span class="sxs-lookup"><span data-stu-id="c1b4e-153">Video Portal</span></span>

<span data-ttu-id="c1b4e-154">Em um locatário multigeográfico, o Portal de Vídeo do O365 só é disponibilizado para a localização geográfica padrão e todos os usuários serão redirecionados para essa url portal central.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-154">In a multi-geo tenant, the O365 Video Portal is served only from default geo and all users will be redirected to that central portal url.</span></span> <span data-ttu-id="c1b4e-155">Dessa forma, os Serviços de Mídia Remoto (RMS) para essa região serão usados, da seguinte forma, com base em uma localização central.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-155">Hence, the Remote Media Service (RMS) for that region will be used, as follows based on your central location.</span></span>

<span data-ttu-id="c1b4e-156">Atualmente, este aplicativo está disponível nas seguintes regiões:</span><span class="sxs-lookup"><span data-stu-id="c1b4e-156">Stream is currently available in the following regions:</span></span>

- <span data-ttu-id="c1b4e-157">América do Norte, hospedada nos Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="c1b4e-157">North America, hosted in the United States</span></span> 
- <span data-ttu-id="c1b4e-158">Europa</span><span class="sxs-lookup"><span data-stu-id="c1b4e-158">Europe</span></span>
- <span data-ttu-id="c1b4e-159">Pacífico Asiático</span><span class="sxs-lookup"><span data-stu-id="c1b4e-159">Asia Pacific</span></span>

<span data-ttu-id="c1b4e-160">Porém, atualmente, o Stream ainda não está disponível nas seguintes regiões com suporte para o Microsoft 365 Video, portanto, para essas instâncias locais, usaremos o RMS que está na região suportada mais próxima.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-160">However, Stream is not yet available in the following regions that are currently supported for Microsoft 365 Video, therefore for these local instances, we will use the RMS that is in the closest supported region.</span></span>

- <span data-ttu-id="c1b4e-161">Austrália</span><span class="sxs-lookup"><span data-stu-id="c1b4e-161">Australia</span></span>
- <span data-ttu-id="c1b4e-162">Canadá</span><span class="sxs-lookup"><span data-stu-id="c1b4e-162">Canada</span></span>
- <span data-ttu-id="c1b4e-163">Índia</span><span class="sxs-lookup"><span data-stu-id="c1b4e-163">India</span></span>
- <span data-ttu-id="c1b4e-164">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="c1b4e-164">United Kingdom</span></span>

## <a name="yammer"></a><span data-ttu-id="c1b4e-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="c1b4e-165">Yammer</span></span>

<span data-ttu-id="c1b4e-166">O Yammer não é uma carga de trabalho multigeográfica.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-166">Yammer is not a Multi-Geo workload.</span></span> <span data-ttu-id="c1b4e-167">Os threads do Yammer armazenados no Yammer serão colocados no local central do locatário.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-167">Yammer threads stored in Yammer will be placed in the tenant’s central location.</span></span> <span data-ttu-id="c1b4e-168">O Yammer está implantando uma alteração de armazenamento de arquivos que armazenará arquivos do Yammer no SharePoint.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-168">Yammer is rolling out a file storage change which will store Yammer files within SharePoint.</span></span> <span data-ttu-id="c1b4e-169">Os arquivos do Yammer armazenados no SharePoint serão colocados no site do SharePoint associado ao grupo do Yammer.</span><span class="sxs-lookup"><span data-stu-id="c1b4e-169">Yammer files stored in SharePoint will be placed the SharePoint site associated with the Yammer group.</span></span> <span data-ttu-id="c1b4e-170">Os sites de grupo do SharePoint são baseados na lógica da PDL, conforme descrito em [sites e grupos do SharePoint](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups).</span><span class="sxs-lookup"><span data-stu-id="c1b4e-170">SharePoint group sites are based on PDL logic as outlined in [SharePoint Sites and Groups](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups).</span></span>