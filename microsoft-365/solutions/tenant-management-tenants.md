---
title: Etapa 1. Seu Microsoft 365 para locatários corporativos
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Implante e gerencie locatários de Microsoft 365, com opções para locais multi-geo e móveis.
ms.openlocfilehash: 4d9bd685fce6fb2f11b8e17bebae6460e0c10bd2
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406379"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="574fa-104">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="574fa-104">Step 1.</span></span> <span data-ttu-id="574fa-105">Seu Microsoft 365 para locatários corporativos</span><span class="sxs-lookup"><span data-stu-id="574fa-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="574fa-106">Uma de suas primeiras decisões de locatários é quantas ter.</span><span class="sxs-lookup"><span data-stu-id="574fa-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="574fa-107">Cada Microsoft 365 locatário é distinto, exclusivo e separado de todos os outros Microsoft 365 locatários.</span><span class="sxs-lookup"><span data-stu-id="574fa-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="574fa-108">O locatário correspondente do Azure AD também é distinto, exclusivo e separado de todos os outros Microsoft 365 locatários.</span><span class="sxs-lookup"><span data-stu-id="574fa-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="574fa-109">Locatário único</span><span class="sxs-lookup"><span data-stu-id="574fa-109">Single tenant</span></span>
<span data-ttu-id="574fa-110">Ter um único locatário simplifica muitos aspectos do uso de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="574fa-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="574fa-111">Um único locatário significa um único locatário do Azure AD com um único conjunto de contas, grupos e políticas.</span><span class="sxs-lookup"><span data-stu-id="574fa-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="574fa-112">As permissões e o compartilhamento de recursos em toda a sua organização podem ser feitas por meio deste provedor de identidade central.</span><span class="sxs-lookup"><span data-stu-id="574fa-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="574fa-113">Um único locatário fornece a experiência de produtividade e colaboração mais rica em recursos e simplificada para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="574fa-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="574fa-114">Aqui está um exemplo mostrando o local padrão e o locatário do Azure AD de um Microsoft 365 locatário.</span><span class="sxs-lookup"><span data-stu-id="574fa-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![Um único Microsoft 365 locatário com seu locatário do Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="574fa-116">Vários locatários</span><span class="sxs-lookup"><span data-stu-id="574fa-116">Multiple tenants</span></span>

<span data-ttu-id="574fa-117">Há muitos motivos pelos quais sua organização pode ter vários locatários:</span><span class="sxs-lookup"><span data-stu-id="574fa-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="574fa-118">Isolamento administrativo</span><span class="sxs-lookup"><span data-stu-id="574fa-118">Administrative isolation</span></span>
- <span data-ttu-id="574fa-119">IT descentralizada</span><span class="sxs-lookup"><span data-stu-id="574fa-119">Decentralized IT</span></span>
- <span data-ttu-id="574fa-120">Decisões históricas</span><span class="sxs-lookup"><span data-stu-id="574fa-120">Historical decisions</span></span>
- <span data-ttu-id="574fa-121">Fusões, aquisições ou desinvestções</span><span class="sxs-lookup"><span data-stu-id="574fa-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="574fa-122">Limpar a separação de identidade visual para organizações de multinacionais</span><span class="sxs-lookup"><span data-stu-id="574fa-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="574fa-123">Locatários de pré-produção, teste ou área de trabalho</span><span class="sxs-lookup"><span data-stu-id="574fa-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="574fa-124">Aqui está um exemplo de uma organização que tem dois locatários (Locatário A e Locatário B) no mesmo datacenter padrão geo.</span><span class="sxs-lookup"><span data-stu-id="574fa-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="574fa-125">Cada locatário como um locatário separado do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="574fa-125">Each tenant as a separate Azure AD tenant.</span></span>

![Vários Microsoft 365 locatários com seus próprios locatários do Azure AD](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="574fa-127">Quando você tem vários locatários, há restrições e considerações adicionais ao gere-los e fornecer serviços aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="574fa-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="574fa-128">Colaboração entre locatários</span><span class="sxs-lookup"><span data-stu-id="574fa-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="574fa-129">Se você quiser que seus usuários colaborem com mais eficiência em diferentes locatários Microsoft 365 de forma segura, as opções de colaboração entre locatários incluem o uso de um local central para arquivos e conversas, o compartilhamento de calendários, o uso de IM, chamadas de áudio/vídeo para comunicação e a garantia de acesso a recursos e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="574fa-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="574fa-130">Para obter mais informações, [consulte Microsoft 365 colaboração entre locatários.](../enterprise/microsoft-365-inter-tenant-collaboration.md)</span><span class="sxs-lookup"><span data-stu-id="574fa-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="574fa-131">Migração de caixa de correio entre locatários (visualização)</span><span class="sxs-lookup"><span data-stu-id="574fa-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="574fa-132">Antes da migração de caixa de correio entre locatários (em visualização), ao mover Exchange Online caixas de correio entre locatários, você precisa deslocar completamente uma caixa de correio de usuário de seu locatário atual (o locatário de origem) para o local e, em seguida, abordá-las para um novo locatário (o locatário de destino).</span><span class="sxs-lookup"><span data-stu-id="574fa-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="574fa-133">Com o novo recurso de migração de caixa de correio entre locatários, os administradores de locatários em locatários de origem e de destino podem mover caixas de correio entre os locatários com dependências mínimas de infraestrutura em seus sistemas locais.</span><span class="sxs-lookup"><span data-stu-id="574fa-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="574fa-134">Isso remove a necessidade de retirada e integração de caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="574fa-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="574fa-135">Aqui estão dois locatários de exemplo e suas caixas de correio antes da migração de caixa de correio entre locatários.</span><span class="sxs-lookup"><span data-stu-id="574fa-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![Vários Microsoft 365 locatários e suas caixas de correio](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="574fa-137">Nesta ilustração, dois locatários separados têm seus próprios domínios e um conjunto de Exchange caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="574fa-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="574fa-138">Aqui está o locatário de destino (Locatário A) após a migração de caixa de correio entre locatários.</span><span class="sxs-lookup"><span data-stu-id="574fa-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![O locatário de destino após a migração de caixa de correio entre locatários](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="574fa-140">Nesta ilustração, um único locatário tem domínios e ambos os conjuntos Exchange caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="574fa-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="574fa-141">Para obter mais informações, consulte Migração de caixa [de correio entre locatários](../enterprise/cross-tenant-mailbox-migration.md).</span><span class="sxs-lookup"><span data-stu-id="574fa-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="574fa-142">Migrações de locatário-para-locatário</span><span class="sxs-lookup"><span data-stu-id="574fa-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="574fa-143">Há várias abordagens de arquitetura para fusões, aquisições, desinvestres e outros cenários que podem levar você a migrar um locatário Microsoft 365 existente para um novo locatário.</span><span class="sxs-lookup"><span data-stu-id="574fa-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="574fa-144">Para obter orientações detalhadas, consulte Microsoft 365 migrações de locatário [para locatário.](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)</span><span class="sxs-lookup"><span data-stu-id="574fa-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="574fa-145">Multi-Geo para um locatário</span><span class="sxs-lookup"><span data-stu-id="574fa-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="574fa-146">Com Microsoft 365 multigeogeo, você pode provisionar e armazenar dados em repouso nos outros locais geo do datacenter que você escolheu para atender aos requisitos de residência de dados e, ao mesmo tempo, desbloquear sua versão global de experiências de produtividade modernas para seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="574fa-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="574fa-147">Em um ambiente Multi-Geo, seu locatário Microsoft 365 consiste em um local padrão ou central onde sua assinatura Microsoft 365 foi originalmente criada e um ou mais locais de satélite.</span><span class="sxs-lookup"><span data-stu-id="574fa-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="574fa-148">Em um locatário multi-geo, as informações sobre localizações geográficas, grupos e informações do usuário são dominadas em um locatário global do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="574fa-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="574fa-149">Como as informações do locatário são dominadas centralmente e sincronizadas em cada localização geográfica, as experiências de colaboração envolvendo qualquer pessoa da sua empresa são compartilhadas entre os locais.</span><span class="sxs-lookup"><span data-stu-id="574fa-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="574fa-150">Aqui está um exemplo de uma organização que tem sua localização padrão na Europa e um local de satélite na América do Norte.</span><span class="sxs-lookup"><span data-stu-id="574fa-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="574fa-151">Ambos os locais compartilham o mesmo locatário global do Azure AD para o locatário único Microsoft 365 locatário.</span><span class="sxs-lookup"><span data-stu-id="574fa-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![Exemplo de um locatário de Microsoft 365 multi-geo](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="574fa-153">Para mais informações, consulte [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="574fa-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="574fa-154">Mover dados principais para um novo datacenter geo</span><span class="sxs-lookup"><span data-stu-id="574fa-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="574fa-155">A Microsoft continua a abrir novos geos do datacenter para Microsoft 365 serviços.</span><span class="sxs-lookup"><span data-stu-id="574fa-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="574fa-156">Esses novos geos do datacenter adicionam capacidade e recursos de computação para dar suporte à nossa demanda e ao crescimento de uso do cliente em andamento.</span><span class="sxs-lookup"><span data-stu-id="574fa-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="574fa-157">Além disso, os novos geos do datacenter oferecem residência de dados no geo para dados principais do cliente.</span><span class="sxs-lookup"><span data-stu-id="574fa-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="574fa-158">Embora abrir um novo datacenter geo não impacte você e seus dados principais armazenados em um datacenter já existente, a Microsoft permite que você solicite uma migração antecipada dos dados principais do cliente da sua organização em repouso para um novo datacenter geo.</span><span class="sxs-lookup"><span data-stu-id="574fa-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="574fa-159">Aqui está um exemplo no qual um locatário de Microsoft 365 foi movido do datacenter da União Europeia (UE) geo para aquele localizado no Reino Unido (Reino Unido).</span><span class="sxs-lookup"><span data-stu-id="574fa-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![Exemplo de mover um locatário Microsoft 365 entre os geos do datacenter](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="574fa-161">Para obter mais informações, consulte [Movendo os dados principais para novas Microsoft 365 de datacenter](../enterprise/moving-data-to-new-datacenter-geos.md).</span><span class="sxs-lookup"><span data-stu-id="574fa-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="574fa-162">Produtos e licenças para um locatário</span><span class="sxs-lookup"><span data-stu-id="574fa-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="574fa-163">Seu Microsoft 365 locatário é criado quando você compra seu primeiro produto, como Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="574fa-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="574fa-164">Junto com o produto estão licenças, que são cobradas uma taxa mensal ou anual.</span><span class="sxs-lookup"><span data-stu-id="574fa-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="574fa-165">Em seguida, um administrador atribui uma licença disponível de um de seus produtos a uma conta de usuário, diretamente ou por meio da associação ao grupo.</span><span class="sxs-lookup"><span data-stu-id="574fa-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="574fa-166">Dependendo das necessidades comerciais da sua organização, você pode ter um conjunto de produtos, cada um com seu próprio pool de licenças.</span><span class="sxs-lookup"><span data-stu-id="574fa-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="574fa-167">Determinar o conjunto de produtos e o número de licenças para cada um requer algum planejamento para:</span><span class="sxs-lookup"><span data-stu-id="574fa-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="574fa-168">Verifique se você tem licenças suficientes para as contas de usuário que precisam de recursos avançados.</span><span class="sxs-lookup"><span data-stu-id="574fa-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="574fa-169">Impedir que você se esvaia de licenças ou ter muitas licenças não atribuídas, com base em alterações no pessoal em sua organização.</span><span class="sxs-lookup"><span data-stu-id="574fa-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="574fa-170">Resultados da Etapa 1</span><span class="sxs-lookup"><span data-stu-id="574fa-170">Results of Step 1</span></span>

<span data-ttu-id="574fa-171">Para sua Microsoft 365 para locatários corporativos, você determinou:</span><span class="sxs-lookup"><span data-stu-id="574fa-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="574fa-172">Quantos locatários você tem ou precisa.</span><span class="sxs-lookup"><span data-stu-id="574fa-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="574fa-173">Para cada locatário, quais produtos e licenças devem ser comprados.</span><span class="sxs-lookup"><span data-stu-id="574fa-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="574fa-174">Se um locatário precisa ser Multi-Geo para atender aos requisitos de residência de dados.</span><span class="sxs-lookup"><span data-stu-id="574fa-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="574fa-175">Se você precisa configurar a colaboração entre locatários.</span><span class="sxs-lookup"><span data-stu-id="574fa-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="574fa-176">Se você precisa migrar um locatário para outro.</span><span class="sxs-lookup"><span data-stu-id="574fa-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="574fa-177">Se você precisa mover os dados principais de um datacenter geo para um novo.</span><span class="sxs-lookup"><span data-stu-id="574fa-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="574fa-178">Aqui está um exemplo de um novo locatário.</span><span class="sxs-lookup"><span data-stu-id="574fa-178">Here is an example of a new tenant.</span></span>

![Exemplo de um novo locatário](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="574fa-180">Nesta ilustração, o locatário tem:</span><span class="sxs-lookup"><span data-stu-id="574fa-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="574fa-181">Um local padrão correspondente a um Microsoft 365 de datacenter.</span><span class="sxs-lookup"><span data-stu-id="574fa-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="574fa-182">Um conjunto de produtos e licenças.</span><span class="sxs-lookup"><span data-stu-id="574fa-182">A set of products and licenses.</span></span>
- <span data-ttu-id="574fa-183">O conjunto de aplicativos de produtividade na nuvem, alguns dos quais são específicos para produtos.</span><span class="sxs-lookup"><span data-stu-id="574fa-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="574fa-184">Um locatário do Azure AD que contém contas de administrador global e um nome de domínio DNS inicial.</span><span class="sxs-lookup"><span data-stu-id="574fa-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="574fa-185">Conforme passamos pelas etapas adicionais dessa solução, criaremos essa figura.</span><span class="sxs-lookup"><span data-stu-id="574fa-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="574fa-186">Manutenção contínua para locatários</span><span class="sxs-lookup"><span data-stu-id="574fa-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="574fa-187">Em uma base contínua, talvez seja necessário:</span><span class="sxs-lookup"><span data-stu-id="574fa-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="574fa-188">Adicione um novo locatário.</span><span class="sxs-lookup"><span data-stu-id="574fa-188">Add a new tenant.</span></span>
- <span data-ttu-id="574fa-189">Adicione novos produtos a um locatário com um número inicial de licenças.</span><span class="sxs-lookup"><span data-stu-id="574fa-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="574fa-190">Altere o conjunto de licenças de um produto em um locatário para ajustar para alterar os requisitos da equipe.</span><span class="sxs-lookup"><span data-stu-id="574fa-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="574fa-191">Mova seus dados principais de um locatário para uma nova localização geográfica do datacenter.</span><span class="sxs-lookup"><span data-stu-id="574fa-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="574fa-192">Adicione Multi-Geo para requisitos de residência de dados.</span><span class="sxs-lookup"><span data-stu-id="574fa-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="574fa-193">Configurar a colaboração entre locatários.</span><span class="sxs-lookup"><span data-stu-id="574fa-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="574fa-194">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="574fa-194">Next step</span></span>

<span data-ttu-id="574fa-195">[![Etapa 2. Otimizar seu locatário para acesso à rede](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="574fa-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="574fa-196">Continue com [a rede](tenant-management-networking.md) para fornecer rede ideal de seus funcionários para Microsoft 365 de nuvem.</span><span class="sxs-lookup"><span data-stu-id="574fa-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>
