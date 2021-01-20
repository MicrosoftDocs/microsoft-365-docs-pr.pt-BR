---
title: Etapa 1. Seus locatários do Microsoft 365 para empresas
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
ms.custom:
- Ent_Solutions
description: Implante e gerencie um ou vários locatários do Microsoft 365, com opções para localizações multi-geográficas e móveis.
ms.openlocfilehash: 567a2cb46e715ec560bf973a33ab83cfa63d403b
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908440"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="af76e-104">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="af76e-104">Step 1.</span></span> <span data-ttu-id="af76e-105">Seus locatários do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="af76e-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="af76e-106">Uma de suas primeiras decisões de locatário é quantas ter.</span><span class="sxs-lookup"><span data-stu-id="af76e-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="af76e-107">Cada locatário do Microsoft 365 é distinto, exclusivo e separado de todos os outros locatários do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="af76e-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="af76e-108">O locatário correspondente do Azure AD também é distinto, exclusivo e separado de todos os outros locatários do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="af76e-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="af76e-109">Locatário único</span><span class="sxs-lookup"><span data-stu-id="af76e-109">Single tenant</span></span>
<span data-ttu-id="af76e-110">Ter um único locatário simplifica muitos aspectos do uso do Microsoft 365 pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="af76e-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="af76e-111">Um único locatário significa um único locatário do Azure AD com um único conjunto de contas, grupos e políticas.</span><span class="sxs-lookup"><span data-stu-id="af76e-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="af76e-112">Permissões e compartilhamento de recursos em toda a organização podem ser feitas por meio deste provedor de identidade central.</span><span class="sxs-lookup"><span data-stu-id="af76e-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="af76e-113">Um único locatário oferece a melhor experiência de colaboração e produtividade de recursos e simplificada para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="af76e-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="af76e-114">Veja um exemplo mostrando o local padrão e o locatário do Azure AD de um locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="af76e-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![Um único locatário do Microsoft 365 com seu locatário do Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="af76e-116">Vários locatários</span><span class="sxs-lookup"><span data-stu-id="af76e-116">Multiple tenants</span></span>

<span data-ttu-id="af76e-117">Há muitos motivos para sua organização ter vários locatários:</span><span class="sxs-lookup"><span data-stu-id="af76e-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="af76e-118">Isolamento administrativo</span><span class="sxs-lookup"><span data-stu-id="af76e-118">Administrative isolation</span></span>
- <span data-ttu-id="af76e-119">IT descentralizado</span><span class="sxs-lookup"><span data-stu-id="af76e-119">Decentralized IT</span></span>
- <span data-ttu-id="af76e-120">Decisões históricas</span><span class="sxs-lookup"><span data-stu-id="af76e-120">Historical decisions</span></span>
- <span data-ttu-id="af76e-121">Fusões, aquisições ou destitures</span><span class="sxs-lookup"><span data-stu-id="af76e-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="af76e-122">Separação clara da identidade visual para organizações de conglomerados</span><span class="sxs-lookup"><span data-stu-id="af76e-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="af76e-123">Locatários de pré-produção, teste ou área de trabalho</span><span class="sxs-lookup"><span data-stu-id="af76e-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="af76e-124">Aqui está um exemplo de uma organização que tem dois locatários (Locatário A e Locatário B) na mesma área geográfica de datacenter padrão.</span><span class="sxs-lookup"><span data-stu-id="af76e-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="af76e-125">Cada locatário como um locatário separado do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="af76e-125">Each tenant as a separate Azure AD tenant.</span></span>

![Vários locatários do Microsoft 365 com seus próprios locatários do Azure AD](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="af76e-127">Quando você tem vários locatários, há restrições e considerações adicionais ao gere-los e fornecer serviços aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="af76e-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="af76e-128">Colaboração entre locatários</span><span class="sxs-lookup"><span data-stu-id="af76e-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="af76e-129">Se você quiser que os usuários colaborem com mais eficiência em diferentes locatários do Microsoft 365 de maneira segura, as opções de colaboração entre locatários incluem o uso de um local central para arquivos e conversas, o compartilhamento de calendários, o uso de mensagens de IM, chamadas de áudio/vídeo para comunicação e a segurança do acesso a recursos e aplicativos.</span><span class="sxs-lookup"><span data-stu-id="af76e-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="af76e-130">Para saber mais, confira a colaboração entre locatários do [Microsoft 365.](../enterprise/microsoft-365-inter-tenant-collaboration.md)</span><span class="sxs-lookup"><span data-stu-id="af76e-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="af76e-131">Migração de caixa de correio entre locatários (visualização)</span><span class="sxs-lookup"><span data-stu-id="af76e-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="af76e-132">Antes da migração de caixa de correio entre locatários (na visualização), ao mover as caixas de correio do Exchange Online entre locatários, você precisa desemlocar completamente uma caixa de correio de usuário de seu locatário atual (o locatário de origem) para o local e, em seguida, abordá-las a um novo locatário (o locatário de destino).</span><span class="sxs-lookup"><span data-stu-id="af76e-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="af76e-133">Com o novo recurso de migração de caixa de correio entre locatários, os administradores de locatários nos locatários de origem e de destino podem mover caixas de correio entre os locatários com dependências mínimas de infraestrutura em seus sistemas locais.</span><span class="sxs-lookup"><span data-stu-id="af76e-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="af76e-134">Isso elimina a necessidade de remoção e integração de caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="af76e-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="af76e-135">Aqui estão dois locatários de exemplo e suas caixas de correio antes da migração de caixa de correio entre locatários.</span><span class="sxs-lookup"><span data-stu-id="af76e-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![Vários locatários do Microsoft 365 e suas caixas de correio](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="af76e-137">Nesta ilustração, dois locatários separados têm seus próprios domínios e conjunto de caixas de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="af76e-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="af76e-138">Aqui está o locatário de destino (Locatário A) após a migração de caixa de correio entre locatários.</span><span class="sxs-lookup"><span data-stu-id="af76e-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![O locatário de destino após a migração de caixa de correio entre locatários](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="af76e-140">Nesta ilustração, um único locatário tem domínios e ambos os conjuntos de caixas de correio do Exchange.</span><span class="sxs-lookup"><span data-stu-id="af76e-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="af76e-141">Para obter mais informações, consulte [Migração de caixa de correio entre locatários.](../enterprise/cross-tenant-mailbox-migration.md)</span><span class="sxs-lookup"><span data-stu-id="af76e-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="af76e-142">Migrações de locatário-para-locatário</span><span class="sxs-lookup"><span data-stu-id="af76e-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="af76e-143">Há várias abordagens arquitetônicas para fusões, aquisições, desaquetes e outros cenários que podem levar você a migrar um locatário existente do Microsoft 365 para um novo locatário.</span><span class="sxs-lookup"><span data-stu-id="af76e-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="af76e-144">Para obter orientações detalhadas, confira migrações de locatário para locatário do [Microsoft 365.](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)</span><span class="sxs-lookup"><span data-stu-id="af76e-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="af76e-145">Multi-Geo para um locatário</span><span class="sxs-lookup"><span data-stu-id="af76e-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="af76e-146">Com o Microsoft 365 Multi-Geo, você pode provisionar e armazenar dados em repouso em outras localizações geográficas do datacenter que escolheu para atender aos requisitos de residência de dados e, ao mesmo tempo, desbloquear sua lançamento global de experiências modernas de produtividade para seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="af76e-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="af76e-147">Em um ambiente multi-geo, seu locatário do Microsoft 365 consiste em um local padrão ou central onde sua assinatura do Microsoft 365 foi originalmente criada e um ou mais locais de satélite.</span><span class="sxs-lookup"><span data-stu-id="af76e-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="af76e-148">Em um locatário multi-geo, as informações sobre localizações geográficas, grupos e informações do usuário são mestre em um locatário global do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="af76e-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="af76e-149">Como as informações do locatário são centralmente e sincronizadas em cada localização geográfica, as experiências de colaboração envolvendo qualquer pessoa da sua empresa são compartilhadas entre os locais.</span><span class="sxs-lookup"><span data-stu-id="af76e-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="af76e-150">Aqui está um exemplo de uma organização que tem sua localização padrão na Europa e uma localização satélite na América do Norte.</span><span class="sxs-lookup"><span data-stu-id="af76e-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="af76e-151">Ambos os locais compartilham o mesmo locatário global do Azure AD para o único locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="af76e-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![Exemplo de um locatário multi-geo do Microsoft 365](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="af76e-153">Para mais informações, consulte [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="af76e-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="af76e-154">Movendo os dados principais para uma nova área geográfica de datacenter</span><span class="sxs-lookup"><span data-stu-id="af76e-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="af76e-155">A Microsoft continua a abrir novas áreas geográficas de datacenter para os serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="af76e-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="af76e-156">Essas novas áreas geográficas de datacenter adicionam capacidade e recursos de computação para dar suporte à demanda contínua do cliente e ao crescimento do uso.</span><span class="sxs-lookup"><span data-stu-id="af76e-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="af76e-157">Além disso, as novas áreas geográficas do datacenter oferecem residência de dados na área geográfica para dados principais do cliente.</span><span class="sxs-lookup"><span data-stu-id="af76e-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="af76e-158">Embora abrir uma nova área geográfica de datacenter não a impacte e seus dados principais armazenados em uma área geográfica de datacenter já existente, a Microsoft permite que você solicite uma migração antecipada dos principais dados do cliente da sua organização em repouso para uma nova área geográfica de datacenter.</span><span class="sxs-lookup"><span data-stu-id="af76e-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="af76e-159">Aqui está um exemplo em que um locatário do Microsoft 365 foi movido do datacenter da União Europeia (UE) para aquele localizado no Reino Unido (REINO UNIDO).</span><span class="sxs-lookup"><span data-stu-id="af76e-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![Exemplo de movimentação de um locatário do Microsoft 365 entre a área geográfica do datacenter](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="af76e-161">Para saber mais, confira Movendo os dados principais para a nova área geográfica do [datacenter do Microsoft 365.](../enterprise/moving-data-to-new-datacenter-geos.md)</span><span class="sxs-lookup"><span data-stu-id="af76e-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="af76e-162">Produtos e licenças para um locatário</span><span class="sxs-lookup"><span data-stu-id="af76e-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="af76e-163">O locatário do Microsoft 365 é criado quando você compra seu primeiro produto, como o Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="af76e-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="af76e-164">Junto com o produto estão licenças, que são cobradas uma taxa mensal ou anual.</span><span class="sxs-lookup"><span data-stu-id="af76e-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="af76e-165">Em seguida, um administrador atribui uma licença disponível de um de seus produtos a uma conta de usuário, diretamente ou por meio da associação a um grupo.</span><span class="sxs-lookup"><span data-stu-id="af76e-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="af76e-166">Dependendo das necessidades comerciais da sua organização, você pode ter um conjunto de produtos, cada um com seu próprio pool de licenças.</span><span class="sxs-lookup"><span data-stu-id="af76e-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="af76e-167">Determinar o conjunto de produtos e o número de licenças para cada um requer algum planejamento para:</span><span class="sxs-lookup"><span data-stu-id="af76e-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="af76e-168">Verifique se você tem licenças suficientes para as contas de usuário que precisam de recursos avançados.</span><span class="sxs-lookup"><span data-stu-id="af76e-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="af76e-169">Impedir que você ficar sem licenças ou ter muitas licenças não atribuídas, com base nas alterações no pessoal da sua organização.</span><span class="sxs-lookup"><span data-stu-id="af76e-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="af76e-170">Resultados da Etapa 1</span><span class="sxs-lookup"><span data-stu-id="af76e-170">Results of Step 1</span></span>

<span data-ttu-id="af76e-171">Para os locatários do Microsoft 365 para empresas, você determinou:</span><span class="sxs-lookup"><span data-stu-id="af76e-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="af76e-172">Quantos locatários você tem ou precisa.</span><span class="sxs-lookup"><span data-stu-id="af76e-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="af76e-173">Para cada locatário, quais produtos e licenças devem ser comprados.</span><span class="sxs-lookup"><span data-stu-id="af76e-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="af76e-174">Se um locatário precisa ser multi-geo para atender aos requisitos de residência de dados.</span><span class="sxs-lookup"><span data-stu-id="af76e-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="af76e-175">Se você precisa configurar a colaboração entre locatários.</span><span class="sxs-lookup"><span data-stu-id="af76e-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="af76e-176">Se você precisa migrar um locatário para outro.</span><span class="sxs-lookup"><span data-stu-id="af76e-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="af76e-177">Se você precisa mover os dados principais de uma área geográfica de datacenter para uma nova.</span><span class="sxs-lookup"><span data-stu-id="af76e-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="af76e-178">Aqui está um exemplo de um novo locatário.</span><span class="sxs-lookup"><span data-stu-id="af76e-178">Here is an example of a new tenant.</span></span>

![Exemplo de um novo locatário](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="af76e-180">Nesta ilustração, o locatário tem:</span><span class="sxs-lookup"><span data-stu-id="af76e-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="af76e-181">Um local padrão correspondente a um datacenter do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="af76e-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="af76e-182">Um conjunto de produtos e licenças.</span><span class="sxs-lookup"><span data-stu-id="af76e-182">A set of products and licenses.</span></span>
- <span data-ttu-id="af76e-183">O conjunto de aplicativos de produtividade na nuvem, alguns dos quais são específicos de produtos.</span><span class="sxs-lookup"><span data-stu-id="af76e-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="af76e-184">Um locatário do Azure AD que contém contas de administrador global e um nome de domínio DNS inicial.</span><span class="sxs-lookup"><span data-stu-id="af76e-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="af76e-185">À medida que avançarmos pelas etapas adicionais desta solução, criaremos essa figura.</span><span class="sxs-lookup"><span data-stu-id="af76e-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="af76e-186">Manutenção contínua para locatários</span><span class="sxs-lookup"><span data-stu-id="af76e-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="af76e-187">Em uma base contínua, talvez seja necessário:</span><span class="sxs-lookup"><span data-stu-id="af76e-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="af76e-188">Adicione um novo locatário.</span><span class="sxs-lookup"><span data-stu-id="af76e-188">Add a new tenant.</span></span>
- <span data-ttu-id="af76e-189">Adicione novos produtos a um locatário com um número inicial de licenças.</span><span class="sxs-lookup"><span data-stu-id="af76e-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="af76e-190">Altere o conjunto de licenças de um produto em um locatário para ajustar para alterar os requisitos da equipe.</span><span class="sxs-lookup"><span data-stu-id="af76e-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="af76e-191">Mova seus dados principais de um locatário para uma nova localização geográfica do datacenter.</span><span class="sxs-lookup"><span data-stu-id="af76e-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="af76e-192">Adicione multi-geo para requisitos de residência de dados.</span><span class="sxs-lookup"><span data-stu-id="af76e-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="af76e-193">Configurar a colaboração entre locatários.</span><span class="sxs-lookup"><span data-stu-id="af76e-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="af76e-194">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="af76e-194">Next step</span></span>

<span data-ttu-id="af76e-195">[![Etapa 2. Otimizar seu locatário para rede para acesso](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="af76e-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="af76e-196">Continue com [a rede](tenant-management-networking.md) para fornecer rede ideal de seus funcionários para os serviços de nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="af76e-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>
