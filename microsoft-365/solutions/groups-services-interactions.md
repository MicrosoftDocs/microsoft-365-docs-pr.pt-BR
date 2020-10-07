---
title: Interações de serviços de grupos
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Interações de serviços de grupos
ms.openlocfilehash: 235a897314a784ba3bb1ac50fe8bdfe9986a70d3
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377624"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="8bd54-103">Interações de serviços de grupos</span><span class="sxs-lookup"><span data-stu-id="8bd54-103">Groups services interactions</span></span>

<span data-ttu-id="8bd54-104">O Microsoft 365 grupos fornece uma malha comum para vários serviços e cargas de trabalho dentro da plataforma do Microsoft 365 para fornecer uma experiência de conexão para usuários finais.</span><span class="sxs-lookup"><span data-stu-id="8bd54-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="8bd54-105">Em seu núcleo, existe um grupo 365 da Microsoft para fornecer:</span><span class="sxs-lookup"><span data-stu-id="8bd54-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="8bd54-106">Uma maneira de gerenciar a associação (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="8bd54-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="8bd54-107">Um local para mensagens e conversas a serem realizadas (caixa de correio do Exchange, Microsoft Teams, Yammer)</span><span class="sxs-lookup"><span data-stu-id="8bd54-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="8bd54-108">Um local para os arquivos a serem armazenados (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="8bd54-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="8bd54-109">Um calendário para agendamento (Exchange)</span><span class="sxs-lookup"><span data-stu-id="8bd54-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="8bd54-110">Um bloco de anotações para capturar anotações (OneNote)</span><span class="sxs-lookup"><span data-stu-id="8bd54-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="8bd54-111">No ponto de criação de grupo, vários outros recursos também são provisionados, mas não ficam visíveis até serem acessados pela primeira vez do serviço:</span><span class="sxs-lookup"><span data-stu-id="8bd54-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="8bd54-112">Uma placa para gerenciar tarefas de grupo (Planner)</span><span class="sxs-lookup"><span data-stu-id="8bd54-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="8bd54-113">Um espaço de trabalho para relatórios (Power BI)</span><span class="sxs-lookup"><span data-stu-id="8bd54-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="8bd54-114">Uma área para vídeos compartilhados (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="8bd54-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="8bd54-115">Uma área para formulários compartilhados (formulários)</span><span class="sxs-lookup"><span data-stu-id="8bd54-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="8bd54-116">No Microsoft 365, outros serviços podem interagir com os grupos do Microsoft 365 para fornecer funcionalidade adicional e recursos para membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="8bd54-117">Estes são alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="8bd54-117">Examples of this include:</span></span>

- <span data-ttu-id="8bd54-118">Aplicativos de energia para aplicativos</span><span class="sxs-lookup"><span data-stu-id="8bd54-118">Power Apps for apps</span></span>
- <span data-ttu-id="8bd54-119">Automatização de energia para fluxos de trabalho</span><span class="sxs-lookup"><span data-stu-id="8bd54-119">Power Automate for workflows</span></span>
- <span data-ttu-id="8bd54-120">Projeto na Web e mapa para o gerenciamento de projetos baseado em cascata</span><span class="sxs-lookup"><span data-stu-id="8bd54-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="8bd54-121">Teams para conversas baseadas em canal</span><span class="sxs-lookup"><span data-stu-id="8bd54-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="8bd54-122">Yammer para comunidades de interesse</span><span class="sxs-lookup"><span data-stu-id="8bd54-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="8bd54-123">Interações do usuário com grupos</span><span class="sxs-lookup"><span data-stu-id="8bd54-123">User interactions with groups</span></span>

<span data-ttu-id="8bd54-124">Os grupos do Microsoft 365 podem ser criados e gerenciados de várias interfaces, tanto por administradores quanto por usuários finais.</span><span class="sxs-lookup"><span data-stu-id="8bd54-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="8bd54-125">Experiências administrativas</span><span class="sxs-lookup"><span data-stu-id="8bd54-125">Administrative experiences</span></span>

<span data-ttu-id="8bd54-126">Os administradores podem criar e gerenciar os grupos do Microsoft 365 de vários centros de administração de carga de trabalho, interfaces de linha de comando que oferecem suporte a scripts, bem como aplicativos criados por personalização que interagem com a API do Graph.</span><span class="sxs-lookup"><span data-stu-id="8bd54-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="8bd54-127">A única exceção é os grupos do Yammer, que devem ser criados de dentro da interface da Web do Yammer.</span><span class="sxs-lookup"><span data-stu-id="8bd54-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="8bd54-128">**Configurações relacionadas**</span><span class="sxs-lookup"><span data-stu-id="8bd54-128">**Related settings**</span></span>

<span data-ttu-id="8bd54-129">Entre as várias interfaces administrativas que podem gerenciar configurações de grupo existem várias sobreposições das quais você deve estar ciente.</span><span class="sxs-lookup"><span data-stu-id="8bd54-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="8bd54-130">**Centro de administração do Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="8bd54-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="8bd54-131">No centro de administração do Microsoft 365, o acesso de convidados aos grupos é habilitado por padrão, como é a capacidade de permitir que os proprietários adicionem convidados.</span><span class="sxs-lookup"><span data-stu-id="8bd54-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="8bd54-132">Não há outros controles no nível da organização disponíveis para grupos desse centro de administração.</span><span class="sxs-lookup"><span data-stu-id="8bd54-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="8bd54-133">**Centro de Administração do Microsoft Azure AD**</span><span class="sxs-lookup"><span data-stu-id="8bd54-133">**Azure AD admin center**</span></span>

<span data-ttu-id="8bd54-134">O centro de administração do Azure AD oferece controles que envolvem se os usuários podem criar grupos ou atribuir proprietários nos portais do Azure, bem como configurações de política de expiração e de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="8bd54-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="8bd54-135">O centro de administração também fornece várias medidas de controle de convite de convidados que vão além da do centro de administração do Microsoft 365, como a capacidade de limitar se os não proprietários também podem convidar convidados</span><span class="sxs-lookup"><span data-stu-id="8bd54-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="8bd54-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="8bd54-136">**SharePoint**</span></span>

<span data-ttu-id="8bd54-137">Os sites do SharePoint são criados com grupos de segurança de proprietário, membro e visitante, com as duas primeiras correspondências em suas contrapartes de grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bd54-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="8bd54-138">Embora a associação aos sites do SharePoint Online seja geralmente gerenciada pelo grupo associado da Microsoft 365, ela não é uma relação bidirecional.</span><span class="sxs-lookup"><span data-stu-id="8bd54-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="8bd54-139">As alterações de associação no nível de grupo do Microsoft 365 são refletidas no SharePoint, no entanto, se a associação for alterada no grupo do SharePoint, isso não será refletido no grupo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bd54-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="8bd54-140">Experiências do usuário</span><span class="sxs-lookup"><span data-stu-id="8bd54-140">User experiences</span></span>

<span data-ttu-id="8bd54-141">Os usuários finais podem criar grupos de vários serviços no Microsoft 365 e, em outros, eles só podem compartilhar com um grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="8bd54-142">Os seguintes serviços permitem a criação de grupos por usuários finais:</span><span class="sxs-lookup"><span data-stu-id="8bd54-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="8bd54-143">Projeto do Office Planner para o Web SharePoint Stream Microsoft Teams Yammer</span><span class="sxs-lookup"><span data-stu-id="8bd54-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="8bd54-144">**Restrição de criação de grupo**</span><span class="sxs-lookup"><span data-stu-id="8bd54-144">**Restriction of group creation**</span></span>

<span data-ttu-id="8bd54-145">Uma abordagem comum para controlar a proliferação de equipes é limitar quais usuários podem criá-los.</span><span class="sxs-lookup"><span data-stu-id="8bd54-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="8bd54-146">Isso só pode ser feito limitando a criação de grupos.</span><span class="sxs-lookup"><span data-stu-id="8bd54-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="8bd54-147">Isso afeta a capacidade de criar grupos de outros serviços onde eles podem ser necessários para o usuário final.</span><span class="sxs-lookup"><span data-stu-id="8bd54-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="8bd54-148">Os grupos do Microsoft 365 não oferecem suporte à capacidade de restringir a criação de grupos de alguns aplicativos ou serviços, permitindo que eles sejam de outras pessoas.</span><span class="sxs-lookup"><span data-stu-id="8bd54-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="8bd54-149">A experiência da restrição de criação de grupo varia entre aplicativos e serviços:</span><span class="sxs-lookup"><span data-stu-id="8bd54-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="8bd54-150">Aplicativo ou serviço</span><span class="sxs-lookup"><span data-stu-id="8bd54-150">App or service</span></span>|<span data-ttu-id="8bd54-151">Experiência</span><span class="sxs-lookup"><span data-stu-id="8bd54-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="8bd54-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="8bd54-152">Outlook</span></span>|<span data-ttu-id="8bd54-153">A opção **novo grupo** é removida do menu novo na página pessoas</span><span class="sxs-lookup"><span data-stu-id="8bd54-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="8bd54-154">Planner</span><span class="sxs-lookup"><span data-stu-id="8bd54-154">Planner</span></span>|<span data-ttu-id="8bd54-155">**Novo plano** explica que a criação do grupo foi desativada e oferece para adicionar o plano a um grupo existente</span><span class="sxs-lookup"><span data-stu-id="8bd54-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="8bd54-156">Projeto para a Web e o mapa</span><span class="sxs-lookup"><span data-stu-id="8bd54-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="8bd54-157">Menu **Criar grupo** explica que a criação do grupo é restrita e sugere o uso de um grupo existente.</span><span class="sxs-lookup"><span data-stu-id="8bd54-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="8bd54-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="8bd54-158">SharePoint</span></span>|<span data-ttu-id="8bd54-159">Ainda é possível criar um site de equipe que não esteja conectado a um grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="8bd54-160">Fluxo</span><span class="sxs-lookup"><span data-stu-id="8bd54-160">Stream</span></span>|<span data-ttu-id="8bd54-161">A opção **grupo** não aparece no **Menu criar**.</span><span class="sxs-lookup"><span data-stu-id="8bd54-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="8bd54-162">Teams</span><span class="sxs-lookup"><span data-stu-id="8bd54-162">Teams</span></span>|<span data-ttu-id="8bd54-163">O usuário não pode criar uma equipe com um novo grupo, mas ainda pode criar uma equipe que utiliza um grupo existente.</span><span class="sxs-lookup"><span data-stu-id="8bd54-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="8bd54-164">**Criar um botão de equipe** é substituído por **criar equipe de um grupo**.</span><span class="sxs-lookup"><span data-stu-id="8bd54-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="8bd54-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="8bd54-165">Yammer</span></span>|<span data-ttu-id="8bd54-166">**Criar uma** opção de grupo é removida da navegação de grupos principais/comunidades.</span><span class="sxs-lookup"><span data-stu-id="8bd54-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="8bd54-167">Interações de serviços com grupos</span><span class="sxs-lookup"><span data-stu-id="8bd54-167">Services interactions with groups</span></span>

<span data-ttu-id="8bd54-168">Confira os grupos no cartaz do Microsoft 365 para obter informações sobre diferentes tipos de grupos, como eles são criados e gerenciados e algumas recomendações de governança.</span><span class="sxs-lookup"><span data-stu-id="8bd54-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="8bd54-169">[![Imagem em miniatura de infográfico sobre os grupos](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="8bd54-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="8bd54-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="8bd54-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="8bd54-171">A tabela a seguir fornece uma visão geral das interações de grupos do Microsoft 365 com vários serviços:</span><span class="sxs-lookup"><span data-stu-id="8bd54-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="8bd54-172">Produto</span><span class="sxs-lookup"><span data-stu-id="8bd54-172">Product</span></span>|<span data-ttu-id="8bd54-173">Recursos</span><span class="sxs-lookup"><span data-stu-id="8bd54-173">Features</span></span>|<span data-ttu-id="8bd54-174">O serviço</span><span class="sxs-lookup"><span data-stu-id="8bd54-174">Does the service</span></span><br><span data-ttu-id="8bd54-175">existe sem um grupo?</span><span class="sxs-lookup"><span data-stu-id="8bd54-175">exist without a group?</span></span>|<span data-ttu-id="8bd54-176">O serviço pode</span><span class="sxs-lookup"><span data-stu-id="8bd54-176">Can the service</span></span><br><span data-ttu-id="8bd54-177">criar um grupo?</span><span class="sxs-lookup"><span data-stu-id="8bd54-177">create a group?</span></span>|<span data-ttu-id="8bd54-178">Exclui o</span><span class="sxs-lookup"><span data-stu-id="8bd54-178">Does deleting the</span></span><br><span data-ttu-id="8bd54-179">a instância exclui o grupo?</span><span class="sxs-lookup"><span data-stu-id="8bd54-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="8bd54-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="8bd54-180">Azure AD</span></span>|<span data-ttu-id="8bd54-181">Associação, controles de grupo, convidados</span><span class="sxs-lookup"><span data-stu-id="8bd54-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="8bd54-182">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-182">Yes</span></span>|<span data-ttu-id="8bd54-183">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-183">Yes</span></span>|<span data-ttu-id="8bd54-184">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-184">Yes</span></span>|
|<span data-ttu-id="8bd54-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="8bd54-185">Exchange</span></span>|<span data-ttu-id="8bd54-186">Calendário, caixa de correio</span><span class="sxs-lookup"><span data-stu-id="8bd54-186">Calendar, mailbox</span></span>|<span data-ttu-id="8bd54-187">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-187">Yes</span></span>|<span data-ttu-id="8bd54-188">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-188">Yes</span></span>|<span data-ttu-id="8bd54-189">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-189">Yes</span></span>|
|<span data-ttu-id="8bd54-190">Formulários</span><span class="sxs-lookup"><span data-stu-id="8bd54-190">Forms</span></span>|<span data-ttu-id="8bd54-191">Formulário</span><span class="sxs-lookup"><span data-stu-id="8bd54-191">Form</span></span>|<span data-ttu-id="8bd54-192">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-192">Yes</span></span>|<span data-ttu-id="8bd54-193">Não</span><span class="sxs-lookup"><span data-stu-id="8bd54-193">No</span></span>|<span data-ttu-id="8bd54-194">Não</span><span class="sxs-lookup"><span data-stu-id="8bd54-194">No</span></span>|
|<span data-ttu-id="8bd54-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="8bd54-195">OneNote</span></span>|<span data-ttu-id="8bd54-196">Bloco de anotações</span><span class="sxs-lookup"><span data-stu-id="8bd54-196">Notebook</span></span>|<span data-ttu-id="8bd54-197">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-197">Yes</span></span>|<span data-ttu-id="8bd54-198">Não</span><span class="sxs-lookup"><span data-stu-id="8bd54-198">No</span></span>|<span data-ttu-id="8bd54-199">Não</span><span class="sxs-lookup"><span data-stu-id="8bd54-199">No</span></span>|
|<span data-ttu-id="8bd54-200">Planner</span><span class="sxs-lookup"><span data-stu-id="8bd54-200">Planner</span></span>|<span data-ttu-id="8bd54-201">Quadro de tarefas</span><span class="sxs-lookup"><span data-stu-id="8bd54-201">Task board</span></span>|<span data-ttu-id="8bd54-202">Não</span><span class="sxs-lookup"><span data-stu-id="8bd54-202">No</span></span>|<span data-ttu-id="8bd54-203">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-203">Yes</span></span>|<span data-ttu-id="8bd54-204">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-204">Yes</span></span>|
|<span data-ttu-id="8bd54-205">Aplicativo de aplicativos de energia</span><span class="sxs-lookup"><span data-stu-id="8bd54-205">Power Apps app</span></span>|<span data-ttu-id="8bd54-206">App</span><span class="sxs-lookup"><span data-stu-id="8bd54-206">App</span></span>|<span data-ttu-id="8bd54-207">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-207">Yes</span></span>|<span data-ttu-id="8bd54-208">Não</span><span class="sxs-lookup"><span data-stu-id="8bd54-208">No</span></span>|<span data-ttu-id="8bd54-209">Não</span><span class="sxs-lookup"><span data-stu-id="8bd54-209">No</span></span>|
|<span data-ttu-id="8bd54-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="8bd54-210">Power Automate</span></span>|<span data-ttu-id="8bd54-211">Fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="8bd54-211">Workflow</span></span>|<span data-ttu-id="8bd54-212">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-212">Yes</span></span>|<span data-ttu-id="8bd54-213">Não</span><span class="sxs-lookup"><span data-stu-id="8bd54-213">No</span></span>|<span data-ttu-id="8bd54-214">Não</span><span class="sxs-lookup"><span data-stu-id="8bd54-214">No</span></span>|
|<span data-ttu-id="8bd54-215">Power BI (clássico)</span><span class="sxs-lookup"><span data-stu-id="8bd54-215">Power BI (classic)</span></span>|<span data-ttu-id="8bd54-216">Workspace</span><span class="sxs-lookup"><span data-stu-id="8bd54-216">Workspace</span></span>|<span data-ttu-id="8bd54-217">Não</span><span class="sxs-lookup"><span data-stu-id="8bd54-217">No</span></span>|<span data-ttu-id="8bd54-218">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-218">Yes</span></span>|<span data-ttu-id="8bd54-219">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-219">Yes</span></span>|
|<span data-ttu-id="8bd54-220">Power BI (novo)</span><span class="sxs-lookup"><span data-stu-id="8bd54-220">Power BI (new)</span></span>|<span data-ttu-id="8bd54-221">Workspace</span><span class="sxs-lookup"><span data-stu-id="8bd54-221">Workspace</span></span>|<span data-ttu-id="8bd54-222">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-222">Yes</span></span>|<span data-ttu-id="8bd54-223">Não</span><span class="sxs-lookup"><span data-stu-id="8bd54-223">No</span></span>|<span data-ttu-id="8bd54-224">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-224">Yes</span></span>|
|<span data-ttu-id="8bd54-225">Project para a Web</span><span class="sxs-lookup"><span data-stu-id="8bd54-225">Project for the web</span></span>|<span data-ttu-id="8bd54-226">Plano de projeto</span><span class="sxs-lookup"><span data-stu-id="8bd54-226">Project plan</span></span>|<span data-ttu-id="8bd54-227">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-227">Yes</span></span>|<span data-ttu-id="8bd54-228">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-228">Yes</span></span>|<span data-ttu-id="8bd54-229">Não</span><span class="sxs-lookup"><span data-stu-id="8bd54-229">No</span></span>|
|<span data-ttu-id="8bd54-230">Roteiro</span><span class="sxs-lookup"><span data-stu-id="8bd54-230">Roadmap</span></span>|<span data-ttu-id="8bd54-231">Roteiro</span><span class="sxs-lookup"><span data-stu-id="8bd54-231">Roadmap</span></span>|<span data-ttu-id="8bd54-232">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-232">Yes</span></span>|<span data-ttu-id="8bd54-233">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-233">Yes</span></span>|<span data-ttu-id="8bd54-234">Não</span><span class="sxs-lookup"><span data-stu-id="8bd54-234">No</span></span>|
|<span data-ttu-id="8bd54-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="8bd54-235">SharePoint</span></span>|<span data-ttu-id="8bd54-236">Site</span><span class="sxs-lookup"><span data-stu-id="8bd54-236">Site</span></span>|<span data-ttu-id="8bd54-237">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-237">Yes</span></span>|<span data-ttu-id="8bd54-238">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-238">Yes</span></span>|<span data-ttu-id="8bd54-239">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-239">Yes</span></span>|
|<span data-ttu-id="8bd54-240">Fluxo</span><span class="sxs-lookup"><span data-stu-id="8bd54-240">Stream</span></span>|<span data-ttu-id="8bd54-241">Canal, vídeo</span><span class="sxs-lookup"><span data-stu-id="8bd54-241">Channel, video</span></span>|<span data-ttu-id="8bd54-242">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-242">Yes</span></span>|<span data-ttu-id="8bd54-243">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-243">Yes</span></span>|<span data-ttu-id="8bd54-244">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-244">Yes</span></span>|
|<span data-ttu-id="8bd54-245">Teams</span><span class="sxs-lookup"><span data-stu-id="8bd54-245">Teams</span></span>|<span data-ttu-id="8bd54-246">Equipe</span><span class="sxs-lookup"><span data-stu-id="8bd54-246">Team</span></span>|<span data-ttu-id="8bd54-247">Não</span><span class="sxs-lookup"><span data-stu-id="8bd54-247">No</span></span>|<span data-ttu-id="8bd54-248">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-248">Yes</span></span>|<span data-ttu-id="8bd54-249">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-249">Yes</span></span>|
|<span data-ttu-id="8bd54-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="8bd54-250">Yammer</span></span>|<span data-ttu-id="8bd54-251">Group</span><span class="sxs-lookup"><span data-stu-id="8bd54-251">Group</span></span>|<span data-ttu-id="8bd54-252">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-252">Yes</span></span>|<span data-ttu-id="8bd54-253">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-253">Yes</span></span>|<span data-ttu-id="8bd54-254">Sim</span><span class="sxs-lookup"><span data-stu-id="8bd54-254">Yes</span></span>|

<span data-ttu-id="8bd54-255">Embora a tabela acima forneça uma visão geral de alto nível das interações de grupo com os serviços do Microsoft 365, há várias nuances e complexidades que você deve entender.</span><span class="sxs-lookup"><span data-stu-id="8bd54-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="8bd54-256">As seções a seguir levam uma análise mais detalhada das cargas de trabalho específicas e suas interações com grupos.</span><span class="sxs-lookup"><span data-stu-id="8bd54-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="8bd54-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="8bd54-257">Azure AD</span></span>

<span data-ttu-id="8bd54-258">O Azure AD fornece os recursos de gerenciamento de identidade subjacentes no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bd54-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="8bd54-259">**Principais recursos fornecidos a grupos**</span><span class="sxs-lookup"><span data-stu-id="8bd54-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="8bd54-260">Associação a um grupo</span><span class="sxs-lookup"><span data-stu-id="8bd54-260">Group membership</span></span>
- <span data-ttu-id="8bd54-261">Política de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="8bd54-261">Naming policy</span></span>
- <span data-ttu-id="8bd54-262">Política de expiração</span><span class="sxs-lookup"><span data-stu-id="8bd54-262">Expiration policy</span></span>
- <span data-ttu-id="8bd54-263">Convidados</span><span class="sxs-lookup"><span data-stu-id="8bd54-263">Guests</span></span>
- <span data-ttu-id="8bd54-264">Restrição de criação de grupo</span><span class="sxs-lookup"><span data-stu-id="8bd54-264">Restriction of Group creation</span></span>

<span data-ttu-id="8bd54-265">**O Azure AD pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="8bd54-266">Sim, os grupos do Microsoft 365 podem ser criados a partir do Azure AD através do portal da Web de administração, através do PowerShell ou da API do Graph.</span><span class="sxs-lookup"><span data-stu-id="8bd54-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="8bd54-267">**O Azure AD existe sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="8bd54-268">Sim, o Azure AD executa um grande número de serviços que não têm relação com grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bd54-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="8bd54-269">Cada grupo do Microsoft 365 é representado como um objeto no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8bd54-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="8bd54-270">**É possível haver várias instâncias do Azure AD por grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="8bd54-271">Não, há apenas uma instância do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="8bd54-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="8bd54-272">**O Azure Active Directory pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="8bd54-273">Sim, porque o Azure AD é a plataforma subjacente que fornece o serviço de associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="8bd54-274">**A associação do Azure AD pode ser alterada com um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="8bd54-275">Não, o Azure AD é a plataforma subjacente em que os grupos existem.</span><span class="sxs-lookup"><span data-stu-id="8bd54-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="8bd54-276">**Excluir a instância excluir o grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="8bd54-277">A exclusão do grupo no Azure AD excluirá os serviços associados ao grupo e o conteúdo relevantes.</span><span class="sxs-lookup"><span data-stu-id="8bd54-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="8bd54-278">Teams</span><span class="sxs-lookup"><span data-stu-id="8bd54-278">Teams</span></span>

<span data-ttu-id="8bd54-279">O Microsoft Teams é um espaço de trabalho centrado no chat destinado a aprimorar a colaboração, fornecendo uma interface singular para interagir com uma variedade de serviços da Microsoft e de terceiros.</span><span class="sxs-lookup"><span data-stu-id="8bd54-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="8bd54-280">Por padrão, quando uma equipe é criada, a caixa de correio e o calendário associados ao grupo do Microsoft 365 estão ocultos da lista de endereços global no Exchange, bem como do Outlook.</span><span class="sxs-lookup"><span data-stu-id="8bd54-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="8bd54-281">Isso pode ser substituído manualmente por um administrador se o usuário quiser usar o Outlook e o Teams no mesmo grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bd54-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="8bd54-282">**Principais recursos fornecidos a grupos**</span><span class="sxs-lookup"><span data-stu-id="8bd54-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="8bd54-283">Conversas</span><span class="sxs-lookup"><span data-stu-id="8bd54-283">Conversations</span></span>
- <span data-ttu-id="8bd54-284">& guias de canais</span><span class="sxs-lookup"><span data-stu-id="8bd54-284">Channels & tabs</span></span>
- <span data-ttu-id="8bd54-285">Reuniões</span><span class="sxs-lookup"><span data-stu-id="8bd54-285">Meetings</span></span>

<span data-ttu-id="8bd54-286">**O Microsoft Teams pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="8bd54-287">Sim, a criação de uma nova equipe criará um novo grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bd54-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="8bd54-288">Também é possível criar uma equipe para um grupo existente que atualmente não tenha um.</span><span class="sxs-lookup"><span data-stu-id="8bd54-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="8bd54-289">**As equipes existem sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="8bd54-290">Não, não é possível que uma equipe exista sem um grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="8bd54-291">**É possível haver várias equipes por grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="8bd54-292">Não, a relação entre uma equipe e um grupo é de 1:1.</span><span class="sxs-lookup"><span data-stu-id="8bd54-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="8bd54-293">**Uma equipe pode ser associada a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="8bd54-294">Não, a própria equipe só pode ser associada a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="8bd54-295">**A associação de uma equipe com um grupo é alterada?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="8bd54-296">Não, a equipe só pode estar associada ao grupo ao qual foi originalmente associada.</span><span class="sxs-lookup"><span data-stu-id="8bd54-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="8bd54-297">**Excluir a equipe excluirá o grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="8bd54-298">Sim, a exclusão da equipe no Microsoft Teams excluirá o grupo, os serviços associados ao grupo e o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="8bd54-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="8bd54-299">Exchange</span></span>

<span data-ttu-id="8bd54-300">O Exchange Online fornece mensagens, calendário, contato e funcionalidade associada.</span><span class="sxs-lookup"><span data-stu-id="8bd54-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="8bd54-301">No contexto de um grupo, somente um único recurso é associado – em oposição a uma instância de serviço inteira.</span><span class="sxs-lookup"><span data-stu-id="8bd54-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="8bd54-302">**Principais recursos fornecidos a grupos**</span><span class="sxs-lookup"><span data-stu-id="8bd54-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="8bd54-303">Caixa de correio e calendário</span><span class="sxs-lookup"><span data-stu-id="8bd54-303">Mailbox and calendar</span></span>
- <span data-ttu-id="8bd54-304">Capacidade de enviar todos os membros do grupo por email</span><span class="sxs-lookup"><span data-stu-id="8bd54-304">Ability to email all Group members</span></span>
- <span data-ttu-id="8bd54-305">Armazenamento de conversas de canal do teams para fins de descoberta eletrônica, comentários do Planner</span><span class="sxs-lookup"><span data-stu-id="8bd54-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="8bd54-306">**O Exchange pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="8bd54-307">Sim, é possível criar um grupo a partir do centro de administração do Exchange Online, bem como do Outlook.</span><span class="sxs-lookup"><span data-stu-id="8bd54-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="8bd54-308">Você também pode converter listas de distribuição do Exchange para grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bd54-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="8bd54-309">**O Exchange existe sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="8bd54-310">Sim, o Exchange Online fornece vários serviços, incluindo caixas de correio compartilhadas e calendários, sem qualquer associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="8bd54-311">**É possível haver várias instâncias de caixas de correio do Exchange ou calendários por grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="8bd54-312">Não, só pode haver uma única caixa de correio e calendário do Exchange Online para um grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="8bd54-313">**As caixas de correio e os calendários do Exchange podem ser associados a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="8bd54-314">Não, a caixa de correio e o calendário têm uma relação 1:1 com o grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="8bd54-315">É possível compartilhar a caixa de correio com outros usuários ou grupos, mas isso não estabelece nenhuma forma de associação de serviço.</span><span class="sxs-lookup"><span data-stu-id="8bd54-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="8bd54-316">**A associação da caixa de correio do Exchange ou do calendário é alterada?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="8bd54-317">Não, a caixa de correio e o calendário não podem ser alterados para um grupo diferente.</span><span class="sxs-lookup"><span data-stu-id="8bd54-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="8bd54-318">No entanto, o conteúdo pode ser movido de uma caixa de correio para outra no Outlook ou usando uma ferramenta de terceiros.</span><span class="sxs-lookup"><span data-stu-id="8bd54-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="8bd54-319">**A exclusão da caixa de correio exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="8bd54-320">Sim, a exclusão da caixa de correio no Exchange excluirá o grupo, bem como os serviços e o conteúdo associados ao grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="8bd54-321">Formulários</span><span class="sxs-lookup"><span data-stu-id="8bd54-321">Forms</span></span>

<span data-ttu-id="8bd54-322">Os formulários fornecem pesquisas e testes baseados na Web.</span><span class="sxs-lookup"><span data-stu-id="8bd54-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="8bd54-323">**Principais recursos fornecidos a grupos**</span><span class="sxs-lookup"><span data-stu-id="8bd54-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="8bd54-324">Propriedade de formulários</span><span class="sxs-lookup"><span data-stu-id="8bd54-324">Ownership of forms</span></span>

<span data-ttu-id="8bd54-325">**Os formulários podem criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="8bd54-326">Não, os formulários não podem criar um grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="8bd54-327">**Existem formulários sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="8bd54-328">Sim, pesquisas e testes podem ser criados diretamente na conta de um usuário final.</span><span class="sxs-lookup"><span data-stu-id="8bd54-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="8bd54-329">**Podem existir vários formulários por grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="8bd54-330">Sim, pode haver vários formulários associados a um grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="8bd54-331">**Os formulários podem ser associados a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="8bd54-332">Não, um formulário só pode ser associado a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="8bd54-333">**É possível que a associação de um formulário com um grupo seja alterada?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="8bd54-334">Não, depois que um formulário é associado a um grupo (criado diretamente no ou a propriedade transferida de um indivíduo), ele não pode ser movido para outro grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="8bd54-335">**Excluir o formulário excluir o grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="8bd54-336">Não, não é possível excluir um grupo da interface formulários, somente formulários individuais.</span><span class="sxs-lookup"><span data-stu-id="8bd54-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="8bd54-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="8bd54-337">OneNote</span></span>

<span data-ttu-id="8bd54-338">O OneNote é um aplicativo de bloco de anotações digital.</span><span class="sxs-lookup"><span data-stu-id="8bd54-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="8bd54-339">O bloco de anotações do OneNote criado com um grupo é um arquivo no site associado do SharePoint em vez de um serviço conectado ao grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="8bd54-340">**Principais recursos fornecidos a grupos**</span><span class="sxs-lookup"><span data-stu-id="8bd54-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="8bd54-341">Bloco de anotações compartilhado (armazenado na biblioteca do SharePoint associada ao grupo)</span><span class="sxs-lookup"><span data-stu-id="8bd54-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="8bd54-342">**O OneNote pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="8bd54-343">Não, o aplicativo OneNote não pode criar um grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="8bd54-344">**Os blocos de anotações do OneNote existem sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="8bd54-345">Sim, os blocos de anotações podem ser criados diretamente no OneDrive ou em outros locais compartilhados.</span><span class="sxs-lookup"><span data-stu-id="8bd54-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="8bd54-346">**É possível haver vários blocos de anotações do OneNote por grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="8bd54-347">Sim, um bloco de anotações é criado por padrão e outros podem ser adicionados, no entanto, qualquer link para o OneNote de serviços associados ao grupo sempre vai para o bloco de anotações padrão.</span><span class="sxs-lookup"><span data-stu-id="8bd54-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="8bd54-348">**Um bloco de anotações do OneNote pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="8bd54-349">Não, o bloco de anotações é armazenado na biblioteca de sites do SharePoint associada ao grupo e vinculado de várias interfaces.</span><span class="sxs-lookup"><span data-stu-id="8bd54-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="8bd54-350">No entanto, ele pode ser compartilhado com outros grupos da mesma forma que pode ser compartilhado com pessoas.</span><span class="sxs-lookup"><span data-stu-id="8bd54-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="8bd54-351">**É possível que a associação do bloco de anotações com um grupo seja alterada?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="8bd54-352">Não, o próprio bloco de anotações é associado ao grupo e pode ser acessado diretamente a partir de outros serviços conectados ao grupo, no entanto, o conteúdo pode ser movido de um bloco de anotações para outro no aplicativo do OneNote.</span><span class="sxs-lookup"><span data-stu-id="8bd54-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="8bd54-353">**Excluir o bloco de anotações excluirá o grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="8bd54-354">Não, no entanto, se o bloco de anotações do OneNote for excluído, poderão existir links desfeitos em alguns dos serviços associados ao grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="8bd54-355">Planner</span><span class="sxs-lookup"><span data-stu-id="8bd54-355">Planner</span></span>

<span data-ttu-id="8bd54-356">O Planner é um serviço de gerenciamento de tarefas de grupos leves.</span><span class="sxs-lookup"><span data-stu-id="8bd54-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="8bd54-357">**Principais recursos fornecidos a grupos**</span><span class="sxs-lookup"><span data-stu-id="8bd54-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="8bd54-358">Placa para gerenciar tarefas de grupo</span><span class="sxs-lookup"><span data-stu-id="8bd54-358">Board for managing group tasks</span></span>

<span data-ttu-id="8bd54-359">**O Planner pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="8bd54-360">Sim, a criação de um plano criará um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="8bd54-361">**Há um quadro do Planner sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="8bd54-362">Não, um plano deve ser associado a um grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="8bd54-363">**É possível haver vários planos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="8bd54-364">Sim, pode haver vários planos por grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="8bd54-365">**É possível associar um plano a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="8bd54-366">Não, um plano depende exclusivamente da Associação de grupo para determinar o acesso.</span><span class="sxs-lookup"><span data-stu-id="8bd54-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="8bd54-367">**A associação de um plano a um grupo é alterada?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="8bd54-368">Não, no entanto, copiar um plano cria um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="8bd54-369">Um grupo criado por qualquer outro aplicativo não será exibido no Planner automaticamente para um usuário.</span><span class="sxs-lookup"><span data-stu-id="8bd54-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="8bd54-370">Para acessar a placa inicialmente, ela precisará abri-la a partir de outra interface baseada em grupo, como o Outlook.</span><span class="sxs-lookup"><span data-stu-id="8bd54-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="8bd54-371">**Excluir o plano excluirá o grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="8bd54-372">Sim, a exclusão do plano excluirá o grupo e os serviços associados ao grupo e o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="8bd54-373">Aplicativos de energia</span><span class="sxs-lookup"><span data-stu-id="8bd54-373">Power Apps</span></span>

<span data-ttu-id="8bd54-374">Os aplicativos de energia fornecem uma tela para o desenvolvimento de aplicativos sem código.</span><span class="sxs-lookup"><span data-stu-id="8bd54-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="8bd54-375">**Principais recursos fornecidos a grupos**</span><span class="sxs-lookup"><span data-stu-id="8bd54-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="8bd54-376">Os aplicativos podem ser compartilhados com um grupo a ser executado e modificado</span><span class="sxs-lookup"><span data-stu-id="8bd54-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="8bd54-377">**Os aplicativos de energia podem criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="8bd54-378">Não, os aplicativos de energia não podem criar um grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bd54-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="8bd54-379">**Os aplicativos de energia existem sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="8bd54-380">Sim, os aplicativos podem ser criados em aplicativos de energia e residem na conta de criadores até serem compartilhados ou publicados.</span><span class="sxs-lookup"><span data-stu-id="8bd54-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="8bd54-381">**Podem existir vários aplicativos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="8bd54-382">Sim, pode haver vários aplicativos compartilhados com um grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="8bd54-383">**Os aplicativos podem ser associados a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="8bd54-384">Sim, um aplicativo pode ser compartilhado com vários grupos.</span><span class="sxs-lookup"><span data-stu-id="8bd54-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="8bd54-385">**A associação de um aplicativo com um grupo é alterada?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="8bd54-386">Sim, como a associação entre os aplicativos de energia e um grupo do Microsoft 365 é somente compartilhamento – o aplicativo ainda reside com o criador.</span><span class="sxs-lookup"><span data-stu-id="8bd54-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bd54-387">[Os grupos devem estar habilitados para segurança antes que os aplicativos possam ser compartilhados com eles](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="8bd54-387">[Groups must be security enabled before apps can be shared with them](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="8bd54-388">**Excluir o aplicativo excluirá o grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="8bd54-389">Não, os aplicativos não estão conectados ao grupo que não estão sendo compartilhados com eles.</span><span class="sxs-lookup"><span data-stu-id="8bd54-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="8bd54-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="8bd54-390">Power Automate</span></span>

<span data-ttu-id="8bd54-391">A automatização de energia (anteriormente conhecida como Microsoft Flow) fornece fluxos de trabalho e serviços de automação.</span><span class="sxs-lookup"><span data-stu-id="8bd54-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="8bd54-392">**Principais recursos fornecidos a grupos**</span><span class="sxs-lookup"><span data-stu-id="8bd54-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="8bd54-393">Os fluxos de trabalho podem ser compartilhados com um grupo a ser executado e modificado.</span><span class="sxs-lookup"><span data-stu-id="8bd54-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="8bd54-394">**A automatização pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="8bd54-395">Não, a automatização de energia não pode criar um grupo do Microsoft 365 no contexto de ser associado a um.</span><span class="sxs-lookup"><span data-stu-id="8bd54-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="8bd54-396">No entanto, é possível criar um fluxo que execute várias operações, como criar um grupo de segurança do Azure AD ou atualizar a associação de um grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bd54-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="8bd54-397">**Os fluxos existem sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="8bd54-398">Sim, os fluxos podem ser criados dentro da automatização de energia e residem dentro da conta de criadores até que seja compartilhado ou publicado.</span><span class="sxs-lookup"><span data-stu-id="8bd54-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="8bd54-399">**É possível haver vários fluxos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="8bd54-400">Sim, pode haver vários fluxos compartilhados com um grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="8bd54-401">**Um fluxo pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="8bd54-402">Sim, um fluxo pode ser compartilhado com vários grupos.</span><span class="sxs-lookup"><span data-stu-id="8bd54-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="8bd54-403">**É possível uma associação de fluxo com uma alteração de grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="8bd54-404">Sim, como a associação entre energia automatizada e um grupo do Microsoft 365 é somente compartilhamento: o fluxo ainda reside com o criador.</span><span class="sxs-lookup"><span data-stu-id="8bd54-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="8bd54-405">**Excluir um fluxo exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="8bd54-406">Não, como os aplicativos de energia, os fluxos não estão conectados ao grupo que não estão sendo compartilhados com eles.</span><span class="sxs-lookup"><span data-stu-id="8bd54-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="8bd54-407">Power BI (clássico)</span><span class="sxs-lookup"><span data-stu-id="8bd54-407">Power BI (classic)</span></span>

<span data-ttu-id="8bd54-408">O Power BI fornece painéis e relatórios orientados por dados interativos.</span><span class="sxs-lookup"><span data-stu-id="8bd54-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="8bd54-409">**Principais recursos fornecidos a grupos**</span><span class="sxs-lookup"><span data-stu-id="8bd54-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="8bd54-410">Relatórios de dados</span><span class="sxs-lookup"><span data-stu-id="8bd54-410">Data reporting</span></span>

<span data-ttu-id="8bd54-411">**O Power BI pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="8bd54-412">Sim, a criação de um espaço de trabalho clássico criará um grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bd54-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="8bd54-413">**Existe um espaço de trabalho clássico do Power BI sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="8bd54-414">Não, [um espaço de trabalho clássico no Power bi deve estar associado a um grupo](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span><span class="sxs-lookup"><span data-stu-id="8bd54-414">No, [a classic workspace in Power BI must be associated with a group](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="8bd54-415">**É possível haver vários espaços de trabalho do Power BI por grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="8bd54-416">Não, a relação entre um espaço de trabalho clássico e um grupo é de 1:1.</span><span class="sxs-lookup"><span data-stu-id="8bd54-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="8bd54-417">**Um espaço de trabalho pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="8bd54-418">Tecnicamente, enquanto o espaço de trabalho clássico é criado com o grupo, o conteúdo pode ser compartilhado fora do grupo com usuários e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="8bd54-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="8bd54-419">**A associação do espaço de trabalho com um grupo é alterada?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="8bd54-420">Não, o próprio espaço de trabalho clássico é associado ao grupo, no entanto, o conteúdo pode ser movido de um espaço de trabalho para outro dentro da interface do Power BI ou exportando o conteúdo localmente.</span><span class="sxs-lookup"><span data-stu-id="8bd54-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="8bd54-421">**A exclusão do espaço de trabalho exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="8bd54-422">Sim, a exclusão do espaço de trabalho no Power BI excluirá o conteúdo e os serviços associados ao grupo e ao grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="8bd54-423">Power BI (novo)</span><span class="sxs-lookup"><span data-stu-id="8bd54-423">Power BI (new)</span></span>

<span data-ttu-id="8bd54-424">O Power BI fornece painéis e relatórios orientados por dados interativos.</span><span class="sxs-lookup"><span data-stu-id="8bd54-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="8bd54-425">Durante a criação de um novo espaço de trabalho no Power BI não cria um grupo do Microsoft 365, a criação de um grupo por outro meio cria um novo espaço de trabalho (não clássico) no Power BI.</span><span class="sxs-lookup"><span data-stu-id="8bd54-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="8bd54-426">**Principais recursos fornecidos a grupos**</span><span class="sxs-lookup"><span data-stu-id="8bd54-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="8bd54-427">Relatórios de dados</span><span class="sxs-lookup"><span data-stu-id="8bd54-427">Data reporting</span></span>

<span data-ttu-id="8bd54-428">**O Power BI pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="8bd54-429">Não, não é possível criar um grupo do Microsoft 365 a partir da nova interface do Power BI.</span><span class="sxs-lookup"><span data-stu-id="8bd54-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="8bd54-430">**O novo espaço de trabalho do Power BI existe sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="8bd54-431">Sim, é possível ter relatórios e espaços de trabalho criados no Power BI que não estão associados aos grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bd54-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="8bd54-432">**É possível haver vários espaços de trabalho por grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="8bd54-433">Sim, [vários espaços de trabalho criados pelo Power bi podem ser compartilhados com um único grupo](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span><span class="sxs-lookup"><span data-stu-id="8bd54-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="8bd54-434">**Um espaço de trabalho pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="8bd54-435">Não, um espaço de trabalho criado pelo Power BI só pode ser associado a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="8bd54-436">**A associação de um espaço de trabalho com um grupo é alterada?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="8bd54-437">Sim e não.</span><span class="sxs-lookup"><span data-stu-id="8bd54-437">Yes and no.</span></span> <span data-ttu-id="8bd54-438">Um espaço de trabalho criado pelo Power BI só pode ser associado a um único grupo por vez, mas pode alterar a associação a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="8bd54-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="8bd54-439">Um espaço de trabalho criado no Power BI por um grupo é permanentemente associado a esse grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="8bd54-440">**A exclusão do espaço de trabalho exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="8bd54-441">Sim, a exclusão do espaço de trabalho no Power BI excluirá os serviços e o conteúdo associados ao grupo e ao grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="8bd54-442">Project para a Web</span><span class="sxs-lookup"><span data-stu-id="8bd54-442">Project for the web</span></span>

<span data-ttu-id="8bd54-443">O Project para a Web oferece a capacidade de criar planos de projeto, gráficos de Gantt e mapas.</span><span class="sxs-lookup"><span data-stu-id="8bd54-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="8bd54-444">Principais recursos fornecidos a grupos.</span><span class="sxs-lookup"><span data-stu-id="8bd54-444">Key features provided to groups.</span></span>

- <span data-ttu-id="8bd54-445">Planos de projeto</span><span class="sxs-lookup"><span data-stu-id="8bd54-445">Project plans</span></span>

<span data-ttu-id="8bd54-446">**O Project para a Web pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="8bd54-447">Sim, é possível criar um novo grupo do Microsoft 365 diretamente do Project para a Web.</span><span class="sxs-lookup"><span data-stu-id="8bd54-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="8bd54-448">**Os projetos existem sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="8bd54-449">Sim, os projetos podem existir sem serem associados a um grupo do Microsoft 365, mas a atribuição de tarefas requer Associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="8bd54-450">**É possível haver vários projetos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="8bd54-451">Sim, é possível conectar vários projetos em um único grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="8bd54-452">**O projeto pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="8bd54-453">Não, um projeto só pode ser associado a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="8bd54-454">**É possível que a associação de um projeto com um grupo seja alterada?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="8bd54-455">Não, depois que a associação com um grupo é estabelecida, ela não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="8bd54-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="8bd54-456">**Excluir o projeto excluirá o grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="8bd54-457">Não, a exclusão do projeto no Project para a Web não excluirá o grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="8bd54-458">Roteiro</span><span class="sxs-lookup"><span data-stu-id="8bd54-458">Roadmap</span></span>

<span data-ttu-id="8bd54-459">O roadmap oferece a capacidade de criar mapas de projeto com o Project para a Web e o Project online.</span><span class="sxs-lookup"><span data-stu-id="8bd54-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="8bd54-460">**Principais recursos fornecidos a grupos**</span><span class="sxs-lookup"><span data-stu-id="8bd54-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="8bd54-461">Roteiros do projeto</span><span class="sxs-lookup"><span data-stu-id="8bd54-461">Project roadmaps</span></span>

<span data-ttu-id="8bd54-462">**O roteiro pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="8bd54-463">Sim, é possível criar um novo grupo do Microsoft 365 diretamente do mapa.</span><span class="sxs-lookup"><span data-stu-id="8bd54-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="8bd54-464">**O roteiro existe sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="8bd54-465">Sim, os roteiros podem existir sem serem associados a um grupo do Microsoft 365, no entanto, compartilhar o mapa requer Associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="8bd54-466">**Podem existir vários roteiros por grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="8bd54-467">Sim, é possível conectar vários mapas a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="8bd54-468">**É possível associar um roteiro a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="8bd54-469">Não, um mapa só pode ser associado a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="8bd54-470">**A associação de um mapa a um grupo é alterada?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="8bd54-471">Não, depois que a associação com um grupo é estabelecida, ela não pode ser alterada.</span><span class="sxs-lookup"><span data-stu-id="8bd54-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="8bd54-472">**Excluir o roteiro excluirá o grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="8bd54-473">Não, a exclusão do roteiro não excluirá o grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="8bd54-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="8bd54-474">SharePoint</span></span>

<span data-ttu-id="8bd54-475">O SharePoint é uma plataforma de gerenciamento de conteúdo baseada na Web que oferece entre outras coisas, serviços de armazenamento para vários serviços da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bd54-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="8bd54-476">**Principais recursos fornecidos a grupos**</span><span class="sxs-lookup"><span data-stu-id="8bd54-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="8bd54-477">Biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="8bd54-477">Document library</span></span>
- <span data-ttu-id="8bd54-478">Biblioteca para armazenamento de bloco de anotações do OneNote</span><span class="sxs-lookup"><span data-stu-id="8bd54-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="8bd54-479">Armazenamento de arquivos wiki do teams</span><span class="sxs-lookup"><span data-stu-id="8bd54-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="8bd54-480">**O SharePoint pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="8bd54-481">Sim, a criação de um site de equipe no SharePoint criará um grupo do Microsoft 365 por padrão.</span><span class="sxs-lookup"><span data-stu-id="8bd54-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="8bd54-482">Também é possível criar um grupo e, opcionalmente, uma equipe para um site existente.</span><span class="sxs-lookup"><span data-stu-id="8bd54-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="8bd54-483">**Existem sites do SharePoint sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="8bd54-484">Sim, o SharePoint oferece vários serviços e sites não associados ao grupo, como sites de comunicação e de Hub.</span><span class="sxs-lookup"><span data-stu-id="8bd54-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="8bd54-485">**Podem existir vários sites por grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="8bd54-486">Não, só pode haver um único site por grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="8bd54-487">Os canais privados no Microsoft Teams usam sites adicionais que não estão conectados ao grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="8bd54-488">**Os sites podem ser associados a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="8bd54-489">Tecnicamente, mas enquanto um site é criado com um grupo, o conteúdo pode ser compartilhado com outros grupos.</span><span class="sxs-lookup"><span data-stu-id="8bd54-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="8bd54-490">**A associação de um site a um grupo é alterada?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="8bd54-491">Não, o próprio site é associado ao grupo, no entanto, o conteúdo pode ser movido de um site para outro dentro da interface do SharePoint, exportando o conteúdo localmente ou usando uma ferramenta de terceiros.</span><span class="sxs-lookup"><span data-stu-id="8bd54-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="8bd54-492">**Excluir o site exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="8bd54-493">Sim, a exclusão do site no SharePoint excluirá os serviços e o conteúdo associados ao grupo e ao grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="8bd54-494">Fluxo</span><span class="sxs-lookup"><span data-stu-id="8bd54-494">Stream</span></span>

<span data-ttu-id="8bd54-495">O Microsoft Stream é uma plataforma de hospedagem e compartilhamento de vídeo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="8bd54-496">**Principais recursos fornecidos a grupos**</span><span class="sxs-lookup"><span data-stu-id="8bd54-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="8bd54-497">Armazenamento de vídeo</span><span class="sxs-lookup"><span data-stu-id="8bd54-497">Video storage</span></span>
- <span data-ttu-id="8bd54-498">Gravação de reunião do teams</span><span class="sxs-lookup"><span data-stu-id="8bd54-498">Teams meeting recording</span></span>
- <span data-ttu-id="8bd54-499">Canais de vídeo</span><span class="sxs-lookup"><span data-stu-id="8bd54-499">Video channels</span></span>

<span data-ttu-id="8bd54-500">**O Stream pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="8bd54-501">Sim, é possível criar um novo grupo do Microsoft 365 diretamente do Stream.</span><span class="sxs-lookup"><span data-stu-id="8bd54-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="8bd54-502">**O fluxo existe sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="8bd54-503">Sim, os canais de vídeo e vídeos podem existir no Stream sem serem associados a um grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="8bd54-504">**Podem existir vários vídeos e canais por grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="8bd54-505">Sim, pode haver vários vídeos e canais em cada grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="8bd54-506">**É possível associar um vídeo ou canal a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="8bd54-507">Sim, enquanto um vídeo ou canal é criado com um grupo, ele pode ser compartilhado com outros grupos.</span><span class="sxs-lookup"><span data-stu-id="8bd54-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="8bd54-508">**A associação a um grupo pode ser alterada?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="8bd54-509">Sim e não; os vídeos no Stream são pertencentes ao carregador de reunião ou ao gravador original e, portanto, podem ser associados a qualquer grupo, mas os canais de vídeo só podem ser associados ao grupo em que foram originalmente criados.</span><span class="sxs-lookup"><span data-stu-id="8bd54-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="8bd54-510">**A exclusão de vídeos ou canais excluirá o grupo?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="8bd54-511">Não, a exclusão de vídeos ou canais não exclui o grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="8bd54-512">No entanto, excluir o próprio grupo no Stream excluirá os serviços associados ao grupo e o conteúdo, exceto os vídeos reais.</span><span class="sxs-lookup"><span data-stu-id="8bd54-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="8bd54-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="8bd54-513">Yammer</span></span>

<span data-ttu-id="8bd54-514">O Yammer é uma plataforma social corporativa projetada para promover o envolvimento da Comunidade dentro e entre organizações.</span><span class="sxs-lookup"><span data-stu-id="8bd54-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="8bd54-515">A criação de uma comunidade (anteriormente conhecida como "grupo") no Yammer cria uma caixa de correio, mas no momento não é usada.</span><span class="sxs-lookup"><span data-stu-id="8bd54-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="8bd54-516">Um grupo do Microsoft 365 associado ao Yammer não pode ser usado com uma equipe no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8bd54-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="8bd54-517">**Principais recursos fornecidos a grupos**</span><span class="sxs-lookup"><span data-stu-id="8bd54-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="8bd54-518">Área de conversa</span><span class="sxs-lookup"><span data-stu-id="8bd54-518">Conversation area</span></span>

<span data-ttu-id="8bd54-519">**O Yammer pode criar um grupo do Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="8bd54-520">Sim, a criação de um novo grupo no Yammer criará um novo grupo do Microsoft 365, se as plataformas estiverem conectadas e o usuário tiver a capacidade de criar um grupo.</span><span class="sxs-lookup"><span data-stu-id="8bd54-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="8bd54-521">Um grupo do Yammer com o Microsoft 365 Group associado não pode ser criado em qualquer interface ou serviço que não seja o próprio Yammer.</span><span class="sxs-lookup"><span data-stu-id="8bd54-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="8bd54-522">**Há um grupo do Yammer sem um grupo do Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="8bd54-523">Sim, é possível criar um grupo do Yammer sem um grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bd54-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="8bd54-524">Se a plataforma Yammer não estiver conectada a grupos do Microsoft 365 ou se os usuários não tiverem a capacidade de criar um grupo do Microsoft 365, os grupos do Yammer serão criados sem uma associação de grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bd54-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="8bd54-525">**É possível haver vários grupos do Yammer por grupo do Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="8bd54-526">Não, a relação entre um grupo do Yammer e um grupo do Microsoft 365 é 1:1.</span><span class="sxs-lookup"><span data-stu-id="8bd54-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="8bd54-527">**Um grupo do Yammer pode ser associado a vários grupos do Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="8bd54-528">Não, o grupo do Yammer só pode ser associado a um único grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8bd54-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="8bd54-529">É possível que as postagens sejam compartilhadas ou movidas para outros grupos do Yammer.</span><span class="sxs-lookup"><span data-stu-id="8bd54-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="8bd54-530">**A associação de um grupo do Yammer pode ser alterada com um grupo do Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="8bd54-531">Não, o grupo do Yammer só pode ser associado ao grupo do Microsoft 365 ao qual ele foi originalmente associado.</span><span class="sxs-lookup"><span data-stu-id="8bd54-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="8bd54-532">**Excluir o grupo do Yammer exclui o grupo do Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="8bd54-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="8bd54-533">Sim, a exclusão do grupo no Yammer excluirá o grupo da Microsoft e o conteúdo e serviços associados ao grupo relacionados.</span><span class="sxs-lookup"><span data-stu-id="8bd54-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

