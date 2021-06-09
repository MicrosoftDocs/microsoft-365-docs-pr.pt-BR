---
title: Experiência do usuário em um ambiente multigeográfico
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Saiba mais sobre a experiência do usuário do SharePoint, OneDrive e Exchange em um ambiente multigeográfico para o Microsoft 365.
ms.openlocfilehash: 558e5a1f7ff2f6f5485a9f32d6e2b43b552b7f17
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749566"
---
# <a name="user-experience-in-a-multi-geo-environment"></a><span data-ttu-id="4243e-103">Experiência do usuário em um ambiente multigeográfico</span><span class="sxs-lookup"><span data-stu-id="4243e-103">User experience in a multi-geo environment</span></span>

<span data-ttu-id="4243e-104">Aqui está o que os usuários verão em uma configuração multigeográfica do OneDrive:</span><span class="sxs-lookup"><span data-stu-id="4243e-104">Here's what your users will see in a OneDrive Multi-Geo configuration:</span></span>

## <a name="exchange-mailbox"></a><span data-ttu-id="4243e-105">Caixa de correio do Exchange</span><span class="sxs-lookup"><span data-stu-id="4243e-105">Exchange mailbox</span></span>

<span data-ttu-id="4243e-106">A caixa de correio do Exchange do usuário é provisionada para o local de dados preferencial e é automaticamente reposicionada se o PDL muda.</span><span class="sxs-lookup"><span data-stu-id="4243e-106">A user's Exchange mailbox is provisioned to their preferred data location, and is automatically relocated if their PDL changes.</span></span> <span data-ttu-id="4243e-107">Os usuários podem usar o Outlook e o Outlook na web normalmente sem nenhuma alteração na experiência do usuário em um ambiente multigeográfico.</span><span class="sxs-lookup"><span data-stu-id="4243e-107">Users can use Outlook and Outlook on the web normally with no change in user experience in a multi-geo environment.</span></span>

## <a name="hub-sites"></a><span data-ttu-id="4243e-108">Sites do hub</span><span class="sxs-lookup"><span data-stu-id="4243e-108">Hub sites</span></span>

<span data-ttu-id="4243e-109">Sites do Hub do SharePoint aprimora a descoberta e a interação com o conteúdo para funcionários, ao criar uma representação consistente e completa de projetos, departamentos ou regiões.</span><span class="sxs-lookup"><span data-stu-id="4243e-109">SharePoint Hub sites enhances the discovery and engagement with content for employees, while creating a complete and consistent representation of projects, departments or regions.</span></span> <span data-ttu-id="4243e-110">Em um ambiente multigeográfico, sites de locais de satélite podem facilmente ser associadas com um site do hub independentemente da localização geográfica do site do hub.</span><span class="sxs-lookup"><span data-stu-id="4243e-110">In a multi-geo environment, sites from satellite locations can easily be associated with a hub site regardless the hub site's geo location.</span></span> <span data-ttu-id="4243e-111">Os usuários podem pesquisar e obter resultados em hub em uma experiência de pesquisa única, independentemente da localização geográfica dos sites.</span><span class="sxs-lookup"><span data-stu-id="4243e-111">Users can search and get results across the hub through a single search experience, regardless of the geo location of the sites.</span></span>

## <a name="microsoft-365-app-launcher"></a><span data-ttu-id="4243e-112">Inicializador de aplicativos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4243e-112">Microsoft 365 app launcher</span></span>

<span data-ttu-id="4243e-113">O inicializador de aplicativos é ciente da multigeografia e direcionará cada bloco para a localização geográfica apropriada da carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4243e-113">The app launcher is multi-geo aware and will direct each tile to the appropriate geo location of the workload.</span></span> <span data-ttu-id="4243e-114">Os blocos do SharePoint e OneDrive apontarão o usuário para a localização correspondente à localização geográfica provisionada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="4243e-114">The SharePoint and OneDrive tiles will point the user to the location corresponding to the user's provisioned geo location.</span></span> <span data-ttu-id="4243e-115">Isso significa que se o usuário tiver o OneDrive em uma localização central, o bloco do SharePoint apontará para SP Home na localização central, mas o site do grupo não será provisionado na localização correspondente ao PDL.</span><span class="sxs-lookup"><span data-stu-id="4243e-115">This means that is the user has a OneDrive in the central location, their SharePoint tile will point them to SP Home in the central location but their group site will be provisioned in the location corresponding to their PDL.</span></span> 

## <a name="office-applications"></a><span data-ttu-id="4243e-116">Aplicativos do Office</span><span class="sxs-lookup"><span data-stu-id="4243e-116">Office applications</span></span>

<span data-ttu-id="4243e-117">Os aplicativos do Office como o Word, o Excel e o PowerPoint detectarão automaticamente a localização geográfica correta do OneDrive for Business para todos os usuários ao entrarem.</span><span class="sxs-lookup"><span data-stu-id="4243e-117">Office applications such as Word, Excel, and PowerPoint will automatically detect the correct OneDrive for Business geo-location for each user when they log in.</span></span> <span data-ttu-id="4243e-118">Os usuários não precisa inserir a URL geográfica específica dos sites do SharePoint ou OneDrive.</span><span class="sxs-lookup"><span data-stu-id="4243e-118">Users do not need to enter the geo-specific URL for their OneDrive or SharePoint sites.</span></span>

## <a name="onedrive-for-business-sync-client"></a><span data-ttu-id="4243e-119">Cliente de sincronização do OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="4243e-119">OneDrive for Business Sync Client</span></span>

<span data-ttu-id="4243e-120">O cliente de sincronização do OneDrive for Business (versão 17.3.6943.0625 e posteriores) detectará automaticamente a localização geográfica correta do OneDrive for Business para o usuário.</span><span class="sxs-lookup"><span data-stu-id="4243e-120">The OneDrive for Business Sync Client (version 17.3.6943.0625 and later) will automatically detect the correct OneDrive for Business geo location for the user.</span></span> <span data-ttu-id="4243e-121">O suporte ao cliente de sincronização inclui a capacidade de sincronizar sites baseados em grupos, independentemente de sua localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="4243e-121">Sync client support includes the ability to sync groups-based sites regardless of their geo location.</span></span> <span data-ttu-id="4243e-122">Observe que para o cliente de sincronização do Groove não há suporte para multigeográfico.</span><span class="sxs-lookup"><span data-stu-id="4243e-122">Note that the Groove sync client is not supported for multi-geo.</span></span> 

## <a name="onedrive-for-business-location"></a><span data-ttu-id="4243e-123">Localização do OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="4243e-123">OneDrive for Business location</span></span>

<span data-ttu-id="4243e-p106">Os usuários terão o OneDrive for Business provisionado em sua localização dados preferida. Se um usuário navegar para uma URL do OneDrive com uma localização geográfica incorreta (por exemplo, um indicador de uma localização geográfica anterior), eles serão redirecionados automaticamente para o OneDrive na localização geográfica adequada.</span><span class="sxs-lookup"><span data-stu-id="4243e-p106">Users will have their OneDrive for Business provisioned in their preferred data location. If a user navigates to a OneDrive URL that contains an incorrect geo location (such as a bookmark from a previous geo location), they are automatically redirected to the OneDrive in the appropriate geo location.</span></span>

## <a name="onedrive-ios-and-android"></a><span data-ttu-id="4243e-126">OneDrive para iOS e Android</span><span class="sxs-lookup"><span data-stu-id="4243e-126">OneDrive iOS and Android</span></span> 

<span data-ttu-id="4243e-p107">Os aplicativos móveis do OneDrive para iOS e Android mostrarão os seus arquivos do OneDrive e arquivos compartilhados com você, independentemente da localização geográfica deles. A pesquisa dos aplicativos móveis do OneDrive mostrará resultados relevantes de todas as localizações geográficas. Baixe a versão mais recente desses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="4243e-p107">The OneDrive iOS and Android mobile apps will show you your OneDrive files and files shared with you regardless of their geo location. Search from the OneDrive mobile apps will show relevant results from all geo locations. Please download the latest version of these apps.</span></span>

<span data-ttu-id="4243e-130">Confira mais informações em [Usar o OneDrive para iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) e [Usar o OneDrive para Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36).</span><span class="sxs-lookup"><span data-stu-id="4243e-130">See Use [OneDrive on iOS](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) and [Use OneDrive for Android](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36) for more information.</span></span>

## <a name="onedrive-mobile-client"></a><span data-ttu-id="4243e-131">Cliente móvel do OneDrive</span><span class="sxs-lookup"><span data-stu-id="4243e-131">OneDrive Mobile Client</span></span> 

<span data-ttu-id="4243e-132">O Cliente Móvel do OneDrive é multigeográfico ciente e exibirá conteúdo e resultados pertinentes de todas as localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="4243e-132">The OneDrive Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="search"></a><span data-ttu-id="4243e-133">Pesquisa</span><span class="sxs-lookup"><span data-stu-id="4243e-133">Search</span></span>

<span data-ttu-id="4243e-p108">Cada localização geográfica tem o seu próprio índice de pesquisa e Centro de pesquisa. Quando um usuário faz uma pesquisa, a consulta é enviada a todas as localizações geográficas e os resultados retornados são mesclados e, depois, classificados de modo que o usuário obtenha resultados unificados. Os usuários obtêm resultados de todas as localizações geográfica independentemente da sua própria localização. Leia informações específicas em [Configurar a pesquisa do OneDrive for Business com Funcionalidade Multigeográfica](configure-search-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="4243e-p108">Each geo location has its own search index and Search Center. When a user searches, the query is sent to all the geo locations, and the returned results are merged and then ranked so the user gets unified results. Users get results from all geo locations regardless of their own geo location. See [Configure Search for OneDrive for Business Multi-Geo](configure-search-for-multi-geo.md) for specifics.</span></span>

<span data-ttu-id="4243e-138">Há suporte para os seguintes clientes de pesquisa:</span><span class="sxs-lookup"><span data-stu-id="4243e-138">The following search clients are supported:</span></span>

-   <span data-ttu-id="4243e-139">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="4243e-139">OneDrive for Business</span></span>

-   <span data-ttu-id="4243e-140">Delve</span><span class="sxs-lookup"><span data-stu-id="4243e-140">Delve</span></span>

-   <span data-ttu-id="4243e-141">Página inicial do SharePoint</span><span class="sxs-lookup"><span data-stu-id="4243e-141">SharePoint Home</span></span>

-   <span data-ttu-id="4243e-142">O Centro de Pesquisa</span><span class="sxs-lookup"><span data-stu-id="4243e-142">The Search Center</span></span>

-   <span data-ttu-id="4243e-143">Aplicativos de pesquisa personalizada que usam a API de pesquisa do SharePoint</span><span class="sxs-lookup"><span data-stu-id="4243e-143">Custom search applications that use the SharePoint Search API</span></span>

## <a name="sharepoint-home"></a><span data-ttu-id="4243e-144">Página inicial do SharePoint</span><span class="sxs-lookup"><span data-stu-id="4243e-144">SharePoint Home</span></span> 

<span data-ttu-id="4243e-145">No SharePoint Multigeográfico a página inicial do SharePoint está hospedada no local onde o usuário reside de acordo com a localização do OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="4243e-145">In SharePoint Multi-Geo your SharePoint home is hosted in the location where the user resides as determined by their OneDrive for business location.</span></span> <span data-ttu-id="4243e-146">Por exemplo: se o usuário tiver seu próprio OneDrive hospedado em um local de satélite na Europa, a página inicial do SharePoint será renderizada na Europa.</span><span class="sxs-lookup"><span data-stu-id="4243e-146">For example: if the user has their OneDrive hosted in an European satellite location, their SharePoint Home will be rendered from Europe.</span></span> <span data-ttu-id="4243e-147">A página inicial do SharePoint inclui todo o conteúdo relevante para o usuário independentemente de sua localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="4243e-147">SharePoint home includes all content relevant to the user regardless of its geo location.</span></span> 

<span data-ttu-id="4243e-148">**Sites Seguidos, Notícias de Sites, Sites Recentes, Sites Frequentes e Sites sugeridos**</span><span class="sxs-lookup"><span data-stu-id="4243e-148">**Followed Sites, News from Sites, Recent Sites, Frequent Sites, and Suggested sites**</span></span>

<span data-ttu-id="4243e-149">Todos os componentes aparecerão para o usuário independentemente da localização geográfica onde o conteúdo estiver hospedado, desde que o usuário tenha permissões para esse conteúdo.</span><span class="sxs-lookup"><span data-stu-id="4243e-149">All of these components will show up for the user regardless of the geo location where the content is hosted, so long as the user has permissions to said content.</span></span> 

<span data-ttu-id="4243e-150">**Links de Recursos**</span><span class="sxs-lookup"><span data-stu-id="4243e-150">**Features Links**</span></span>

<span data-ttu-id="4243e-151">Os administradores podem configurar links de Recursos na página inicial do SharePoint de acordo com cada localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="4243e-151">Admins may configure Featured links in SharePoint home as appropriate to each geo location.</span></span> <span data-ttu-id="4243e-152">Isso permite que o administrador disponha na pagina inicial SP os links apropriados para os usuários na região.</span><span class="sxs-lookup"><span data-stu-id="4243e-152">This allows the admin to feature in the SP Home for each region the links that are appropriate for users in the region.</span></span> 

## <a name="sharepoint-mobile-client"></a><span data-ttu-id="4243e-153">Cliente móvel do SharePoint</span><span class="sxs-lookup"><span data-stu-id="4243e-153">SharePoint Mobile Client</span></span> 

<span data-ttu-id="4243e-154">O Cliente Móvel do SharePoint é multigeográfico ciente e exibirá o conteúdo e resultados pertinentes de todas as localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="4243e-154">The SharePoint Mobile Client is multi-geo aware and will display pertinent content and results from all geo locations.</span></span>

## <a name="sharing"></a><span data-ttu-id="4243e-155">Compartilhamento</span><span class="sxs-lookup"><span data-stu-id="4243e-155">Sharing</span></span>

<span data-ttu-id="4243e-156">A experiência do Seletor de Pessoas mostra todos os usuários independentemente da localização geográfica.</span><span class="sxs-lookup"><span data-stu-id="4243e-156">The People Picker experience shows all users regardless of their geo location.</span></span> <span data-ttu-id="4243e-157">Isso permite que um usuário compartilhe com outro usuário em sua mesma localização geográfica ou em outras localizações geográficas do locatário.</span><span class="sxs-lookup"><span data-stu-id="4243e-157">This allows a user to share with another user in their same geo or in any other of your tenant's geo locations.</span></span> <span data-ttu-id="4243e-158">O conteúdo de localizações geográficas diferentes será exibidos em **Compartilhado comigo** no OneDrive for Business do usuário e pode ser acessado com uma experiência de logon única independentemente de qual localização geográfica estiver hospedado.</span><span class="sxs-lookup"><span data-stu-id="4243e-158">Content from different geo locations will show up in the **Shared with Me** view in the user's OneDrive for Business and can be accessed with Single Sign-On experience regardless of which geo location it is hosted in.</span></span>

## <a name="teams-experience"></a><span data-ttu-id="4243e-159">Experiência do Teams</span><span class="sxs-lookup"><span data-stu-id="4243e-159">Teams Experience</span></span>

<span data-ttu-id="4243e-160">O Teams é multigeográfico ciente.</span><span class="sxs-lookup"><span data-stu-id="4243e-160">Teams is multi-geo aware.</span></span> <span data-ttu-id="4243e-161">Arquivos do OneDrive e arquivos visualizados recentemente são mostrados independentemente da localização geográfica do usuário.</span><span class="sxs-lookup"><span data-stu-id="4243e-161">OneDrive files and recently viewed files are shown regardless of the user's geo location.</span></span> <span data-ttu-id="4243e-162">@ menções funcionam com usuários de todas as localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="4243e-162">@ mentions work with users from all geo-locations.</span></span>

## <a name="user-profiles"></a><span data-ttu-id="4243e-163">Perfis de usuário</span><span class="sxs-lookup"><span data-stu-id="4243e-163">User profiles</span></span>

<span data-ttu-id="4243e-p113">As informações de perfil de usuário são controladas na localização geográfica do usuário. Ao selecionar um usuário, você será direcionado para a localização geográfica adequada do usuário, onde você verá os detalhes do perfil completos dele.</span><span class="sxs-lookup"><span data-stu-id="4243e-p113">User profile information is mastered in the user's geo location. When selecting a user, you will be directed to the appropriate geo location for the user, where you will see their full profile details.</span></span>

<span data-ttu-id="4243e-166">Se o Delve estiver desativado, você verá a experiência de perfil clássica no SharePoint, que não reconhece diferentes localizações geográficas.</span><span class="sxs-lookup"><span data-stu-id="4243e-166">If Delve is turned off, you will see the classic profile experience in SharePoint, which is not multi-geo aware.</span></span>


