---
title: Grupos de interações de serviços
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
description: Grupos de interações de serviços
ms.openlocfilehash: 6d5681b11cdbd837f784b6c8364cce23f964b167
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613221"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="3cde0-103">Grupos de interações de serviços</span><span class="sxs-lookup"><span data-stu-id="3cde0-103">Groups services interactions</span></span>

<span data-ttu-id="3cde0-104">Os Grupos do Microsoft 365 oferecem uma malha comum para vários serviços e cargas de trabalho dentro da plataforma Microsoft 365 para oferecer uma experiência conectada aos usuários finais.</span><span class="sxs-lookup"><span data-stu-id="3cde0-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="3cde0-105">Em seu núcleo, existe um grupo do Microsoft 365 para fornecer:</span><span class="sxs-lookup"><span data-stu-id="3cde0-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="3cde0-106">Uma maneira de gerenciar a associação (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="3cde0-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="3cde0-107">Um local para mensagens e conversas ocorrerem (caixa de correio do Exchange, Microsoft Teams, Yammer)</span><span class="sxs-lookup"><span data-stu-id="3cde0-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="3cde0-108">Um local para arquivos a serem armazenados (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="3cde0-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="3cde0-109">Um calendário para agendamento (Exchange)</span><span class="sxs-lookup"><span data-stu-id="3cde0-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="3cde0-110">Um bloco de anotações para captura de anotações (OneNote)</span><span class="sxs-lookup"><span data-stu-id="3cde0-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="3cde0-111">No ponto de criação do grupo, vários outros recursos também são provisionados, mas não ficam visíveis até que sejam acessados pela primeira vez do serviço:</span><span class="sxs-lookup"><span data-stu-id="3cde0-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="3cde0-112">Um quadro para gerenciar tarefas de grupo (Planner)</span><span class="sxs-lookup"><span data-stu-id="3cde0-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="3cde0-113">Um espaço de trabalho para relatórios (Power BI)</span><span class="sxs-lookup"><span data-stu-id="3cde0-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="3cde0-114">Uma área para vídeos compartilhados (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="3cde0-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="3cde0-115">Uma área para formulários compartilhados (Formulários)</span><span class="sxs-lookup"><span data-stu-id="3cde0-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="3cde0-116">No Microsoft 365, outros serviços podem interagir com grupos do Microsoft 365 para oferecer funcionalidades e funcionalidades adicionais aos membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="3cde0-117">Exemplos disso incluem:</span><span class="sxs-lookup"><span data-stu-id="3cde0-117">Examples of this include:</span></span>

- <span data-ttu-id="3cde0-118">Power Apps para aplicativos</span><span class="sxs-lookup"><span data-stu-id="3cde0-118">Power Apps for apps</span></span>
- <span data-ttu-id="3cde0-119">Power Automate para fluxos de trabalho</span><span class="sxs-lookup"><span data-stu-id="3cde0-119">Power Automate for workflows</span></span>
- <span data-ttu-id="3cde0-120">Projeto na Web e Roteiro para gerenciamento de projetos baseados em cascata</span><span class="sxs-lookup"><span data-stu-id="3cde0-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="3cde0-121">Teams para conversas baseadas em canal</span><span class="sxs-lookup"><span data-stu-id="3cde0-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="3cde0-122">Yammer para comunidades de interesse</span><span class="sxs-lookup"><span data-stu-id="3cde0-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="3cde0-123">Interações do usuário com grupos</span><span class="sxs-lookup"><span data-stu-id="3cde0-123">User interactions with groups</span></span>

<span data-ttu-id="3cde0-124">Os Grupos do Microsoft 365 podem ser criados e gerenciados a partir de uma variedade de interfaces, tanto por administradores quanto por usuários finais.</span><span class="sxs-lookup"><span data-stu-id="3cde0-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="3cde0-125">Experiências administrativas</span><span class="sxs-lookup"><span data-stu-id="3cde0-125">Administrative experiences</span></span>

<span data-ttu-id="3cde0-126">Os administradores podem criar e gerenciar grupos do Microsoft 365 em vários centros de administração de carga de trabalho, interfaces de linha de comando que suportam scripts, bem como aplicativos personalizados que interagem com a API do Graph.</span><span class="sxs-lookup"><span data-stu-id="3cde0-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="3cde0-127">A única exceção a isso são os grupos do Yammer, que devem ser criados a partir da interface da Web do Yammer.</span><span class="sxs-lookup"><span data-stu-id="3cde0-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="3cde0-128">**Configurações relacionadas**</span><span class="sxs-lookup"><span data-stu-id="3cde0-128">**Related settings**</span></span>

<span data-ttu-id="3cde0-129">Entre as várias interfaces administrativas que podem gerenciar configurações de grupo existem várias sobreposições das quais você deve estar ciente.</span><span class="sxs-lookup"><span data-stu-id="3cde0-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="3cde0-130">**Centro de administração do Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="3cde0-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="3cde0-131">No Centro de administração do Microsoft 365, o acesso de convidados aos Grupos é habilitado por padrão, assim como a capacidade de permitir que os proprietários adicionem convidados.</span><span class="sxs-lookup"><span data-stu-id="3cde0-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="3cde0-132">Não há mais controles no nível da organização disponíveis para Grupos deste centro de administração.</span><span class="sxs-lookup"><span data-stu-id="3cde0-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="3cde0-133">**Centro de Administração do Microsoft Azure AD**</span><span class="sxs-lookup"><span data-stu-id="3cde0-133">**Azure AD admin center**</span></span>

<span data-ttu-id="3cde0-134">O centro de administração do Azure AD oferece controles sobre se os usuários podem criar Grupos ou atribuir proprietários em portais do Azure, bem como configurações de política de expiração e nomeação.</span><span class="sxs-lookup"><span data-stu-id="3cde0-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="3cde0-135">O centro de administração também fornece várias medidas de controle de convite para convidado que vão além do centro de administração do Microsoft 365, como a capacidade de limitar se não proprietários também podem convidar convidados</span><span class="sxs-lookup"><span data-stu-id="3cde0-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="3cde0-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="3cde0-136">**SharePoint**</span></span>

<span data-ttu-id="3cde0-137">Os sites do SharePoint são criados com grupos de segurança proprietário, membro e visitante, com os dois primeiros correspondendo aos seus equivalentes do Grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cde0-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="3cde0-138">Embora a associação a sites do SharePoint Online seja geralmente gerenciada pelo Grupo do Microsoft 365 associado, não é uma relação bidirecional.</span><span class="sxs-lookup"><span data-stu-id="3cde0-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="3cde0-139">Quaisquer alterações na associação no nível de grupo do Microsoft 365 são refletidas no SharePoint, no entanto, se a associação for alterada no grupo do SharePoint, isso não será refletido no grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cde0-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="3cde0-140">Experiências do usuário</span><span class="sxs-lookup"><span data-stu-id="3cde0-140">User experiences</span></span>

<span data-ttu-id="3cde0-141">Os usuários finais podem criar grupos de vários dos serviços no Microsoft 365 e, em outros, eles só podem compartilhar com um grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="3cde0-142">Os seguintes serviços permitem a criação de grupos por usuários finais:</span><span class="sxs-lookup"><span data-stu-id="3cde0-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="3cde0-143">Outlook Planner Project para a Web SharePoint Stream Microsoft Teams Yammer</span><span class="sxs-lookup"><span data-stu-id="3cde0-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="3cde0-144">**Restrição de criação de grupo**</span><span class="sxs-lookup"><span data-stu-id="3cde0-144">**Restriction of group creation**</span></span>

<span data-ttu-id="3cde0-145">Uma abordagem comum para controlar a expansão de equipes é limitar quais usuários podem criar.</span><span class="sxs-lookup"><span data-stu-id="3cde0-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="3cde0-146">Isso só pode ser feito limitando a criação de grupos.</span><span class="sxs-lookup"><span data-stu-id="3cde0-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="3cde0-147">Isso afeta a capacidade de criar grupos de outros serviços onde isso pode ser necessário para o usuário final.</span><span class="sxs-lookup"><span data-stu-id="3cde0-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="3cde0-148">Os Grupos do Microsoft 365 não suportam a capacidade de restringir a criação de grupos de alguns aplicativos ou serviços, permitindo-os de outros.</span><span class="sxs-lookup"><span data-stu-id="3cde0-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="3cde0-149">A experiência de restrição de criação de grupo varia entre aplicativos e serviços:</span><span class="sxs-lookup"><span data-stu-id="3cde0-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="3cde0-150">Aplicativo ou serviço</span><span class="sxs-lookup"><span data-stu-id="3cde0-150">App or service</span></span>|<span data-ttu-id="3cde0-151">Experiência</span><span class="sxs-lookup"><span data-stu-id="3cde0-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="3cde0-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="3cde0-152">Outlook</span></span>|<span data-ttu-id="3cde0-153">**A nova opção** de grupo foi removida do menu Novo na página Pessoas</span><span class="sxs-lookup"><span data-stu-id="3cde0-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="3cde0-154">Planner</span><span class="sxs-lookup"><span data-stu-id="3cde0-154">Planner</span></span>|<span data-ttu-id="3cde0-155">**O novo** plano explica que a criação do grupo foi desligada e oferece a opção de adicionar o plano a um grupo existente</span><span class="sxs-lookup"><span data-stu-id="3cde0-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="3cde0-156">Project para a Web e Roteiro</span><span class="sxs-lookup"><span data-stu-id="3cde0-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="3cde0-157">**O** menu Criar grupo explica que a criação de grupo é restrita e sugere o uso de um grupo existente.</span><span class="sxs-lookup"><span data-stu-id="3cde0-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="3cde0-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="3cde0-158">SharePoint</span></span>|<span data-ttu-id="3cde0-159">Ainda é possível criar um site de equipe que não está conectado a um grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="3cde0-160">Stream</span><span class="sxs-lookup"><span data-stu-id="3cde0-160">Stream</span></span>|<span data-ttu-id="3cde0-161">**A** opção de grupo não aparece no **menu Criar.**</span><span class="sxs-lookup"><span data-stu-id="3cde0-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="3cde0-162">Teams</span><span class="sxs-lookup"><span data-stu-id="3cde0-162">Teams</span></span>|<span data-ttu-id="3cde0-163">O usuário não pode criar uma equipe com um novo grupo, mas ainda pode criar uma equipe que utilize um grupo existente.</span><span class="sxs-lookup"><span data-stu-id="3cde0-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="3cde0-164">**Criar um botão** de equipe é substituído por **Criar equipe de um grupo.**</span><span class="sxs-lookup"><span data-stu-id="3cde0-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="3cde0-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="3cde0-165">Yammer</span></span>|<span data-ttu-id="3cde0-166">**A opção Criar um** grupo foi removida da navegação principal Grupos/Comunidades.</span><span class="sxs-lookup"><span data-stu-id="3cde0-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="3cde0-167">Interações de serviços com grupos</span><span class="sxs-lookup"><span data-stu-id="3cde0-167">Services interactions with groups</span></span>

<span data-ttu-id="3cde0-168">Confira o cartaz Grupos no Microsoft 365 para obter informações sobre diferentes tipos de grupos, como eles são criados e gerenciados e algumas recomendações de governança.</span><span class="sxs-lookup"><span data-stu-id="3cde0-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="3cde0-169">[![Imagem em miniatura de infográfico sobre os grupos](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="3cde0-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="3cde0-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="3cde0-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="3cde0-171">A tabela a seguir fornece uma visão geral das interações dos Grupos do Microsoft 365 com vários serviços:</span><span class="sxs-lookup"><span data-stu-id="3cde0-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="3cde0-172">Produto</span><span class="sxs-lookup"><span data-stu-id="3cde0-172">Product</span></span>|<span data-ttu-id="3cde0-173">Recursos</span><span class="sxs-lookup"><span data-stu-id="3cde0-173">Features</span></span>|<span data-ttu-id="3cde0-174">Faz o serviço?</span><span class="sxs-lookup"><span data-stu-id="3cde0-174">Does the service</span></span><br><span data-ttu-id="3cde0-175">existir sem um grupo?</span><span class="sxs-lookup"><span data-stu-id="3cde0-175">exist without a group?</span></span>|<span data-ttu-id="3cde0-176">O serviço pode</span><span class="sxs-lookup"><span data-stu-id="3cde0-176">Can the service</span></span><br><span data-ttu-id="3cde0-177">criar um grupo?</span><span class="sxs-lookup"><span data-stu-id="3cde0-177">create a group?</span></span>|<span data-ttu-id="3cde0-178">Exclui o</span><span class="sxs-lookup"><span data-stu-id="3cde0-178">Does deleting the</span></span><br><span data-ttu-id="3cde0-179">exclua o grupo?</span><span class="sxs-lookup"><span data-stu-id="3cde0-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="3cde0-180">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3cde0-180">Azure AD</span></span>|<span data-ttu-id="3cde0-181">Associação, controles de grupo, Convidados</span><span class="sxs-lookup"><span data-stu-id="3cde0-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="3cde0-182">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-182">Yes</span></span>|<span data-ttu-id="3cde0-183">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-183">Yes</span></span>|<span data-ttu-id="3cde0-184">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-184">Yes</span></span>|
|<span data-ttu-id="3cde0-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="3cde0-185">Exchange</span></span>|<span data-ttu-id="3cde0-186">Calendário, caixa de correio</span><span class="sxs-lookup"><span data-stu-id="3cde0-186">Calendar, mailbox</span></span>|<span data-ttu-id="3cde0-187">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-187">Yes</span></span>|<span data-ttu-id="3cde0-188">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-188">Yes</span></span>|<span data-ttu-id="3cde0-189">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-189">Yes</span></span>|
|<span data-ttu-id="3cde0-190">Forms</span><span class="sxs-lookup"><span data-stu-id="3cde0-190">Forms</span></span>|<span data-ttu-id="3cde0-191">Formulário</span><span class="sxs-lookup"><span data-stu-id="3cde0-191">Form</span></span>|<span data-ttu-id="3cde0-192">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-192">Yes</span></span>|<span data-ttu-id="3cde0-193">Não</span><span class="sxs-lookup"><span data-stu-id="3cde0-193">No</span></span>|<span data-ttu-id="3cde0-194">Não</span><span class="sxs-lookup"><span data-stu-id="3cde0-194">No</span></span>|
|<span data-ttu-id="3cde0-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="3cde0-195">OneNote</span></span>|<span data-ttu-id="3cde0-196">Bloco de anotações</span><span class="sxs-lookup"><span data-stu-id="3cde0-196">Notebook</span></span>|<span data-ttu-id="3cde0-197">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-197">Yes</span></span>|<span data-ttu-id="3cde0-198">Não</span><span class="sxs-lookup"><span data-stu-id="3cde0-198">No</span></span>|<span data-ttu-id="3cde0-199">Não</span><span class="sxs-lookup"><span data-stu-id="3cde0-199">No</span></span>|
|<span data-ttu-id="3cde0-200">Planner</span><span class="sxs-lookup"><span data-stu-id="3cde0-200">Planner</span></span>|<span data-ttu-id="3cde0-201">Quadro de tarefas</span><span class="sxs-lookup"><span data-stu-id="3cde0-201">Task board</span></span>|<span data-ttu-id="3cde0-202">Não</span><span class="sxs-lookup"><span data-stu-id="3cde0-202">No</span></span>|<span data-ttu-id="3cde0-203">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-203">Yes</span></span>|<span data-ttu-id="3cde0-204">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-204">Yes</span></span>|
|<span data-ttu-id="3cde0-205">Aplicativo Power Apps</span><span class="sxs-lookup"><span data-stu-id="3cde0-205">Power Apps app</span></span>|<span data-ttu-id="3cde0-206">App</span><span class="sxs-lookup"><span data-stu-id="3cde0-206">App</span></span>|<span data-ttu-id="3cde0-207">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-207">Yes</span></span>|<span data-ttu-id="3cde0-208">Não</span><span class="sxs-lookup"><span data-stu-id="3cde0-208">No</span></span>|<span data-ttu-id="3cde0-209">Não</span><span class="sxs-lookup"><span data-stu-id="3cde0-209">No</span></span>|
|<span data-ttu-id="3cde0-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="3cde0-210">Power Automate</span></span>|<span data-ttu-id="3cde0-211">Fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="3cde0-211">Workflow</span></span>|<span data-ttu-id="3cde0-212">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-212">Yes</span></span>|<span data-ttu-id="3cde0-213">Não</span><span class="sxs-lookup"><span data-stu-id="3cde0-213">No</span></span>|<span data-ttu-id="3cde0-214">Não</span><span class="sxs-lookup"><span data-stu-id="3cde0-214">No</span></span>|
|<span data-ttu-id="3cde0-215">Power BI (clássico)</span><span class="sxs-lookup"><span data-stu-id="3cde0-215">Power BI (classic)</span></span>|<span data-ttu-id="3cde0-216">Workspace</span><span class="sxs-lookup"><span data-stu-id="3cde0-216">Workspace</span></span>|<span data-ttu-id="3cde0-217">Não</span><span class="sxs-lookup"><span data-stu-id="3cde0-217">No</span></span>|<span data-ttu-id="3cde0-218">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-218">Yes</span></span>|<span data-ttu-id="3cde0-219">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-219">Yes</span></span>|
|<span data-ttu-id="3cde0-220">Power BI (novo)</span><span class="sxs-lookup"><span data-stu-id="3cde0-220">Power BI (new)</span></span>|<span data-ttu-id="3cde0-221">Workspace</span><span class="sxs-lookup"><span data-stu-id="3cde0-221">Workspace</span></span>|<span data-ttu-id="3cde0-222">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-222">Yes</span></span>|<span data-ttu-id="3cde0-223">Não</span><span class="sxs-lookup"><span data-stu-id="3cde0-223">No</span></span>|<span data-ttu-id="3cde0-224">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-224">Yes</span></span>|
|<span data-ttu-id="3cde0-225">Project para a Web</span><span class="sxs-lookup"><span data-stu-id="3cde0-225">Project for the web</span></span>|<span data-ttu-id="3cde0-226">Plano do projeto</span><span class="sxs-lookup"><span data-stu-id="3cde0-226">Project plan</span></span>|<span data-ttu-id="3cde0-227">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-227">Yes</span></span>|<span data-ttu-id="3cde0-228">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-228">Yes</span></span>|<span data-ttu-id="3cde0-229">Não</span><span class="sxs-lookup"><span data-stu-id="3cde0-229">No</span></span>|
|<span data-ttu-id="3cde0-230">Roteiro</span><span class="sxs-lookup"><span data-stu-id="3cde0-230">Roadmap</span></span>|<span data-ttu-id="3cde0-231">Roteiro</span><span class="sxs-lookup"><span data-stu-id="3cde0-231">Roadmap</span></span>|<span data-ttu-id="3cde0-232">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-232">Yes</span></span>|<span data-ttu-id="3cde0-233">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-233">Yes</span></span>|<span data-ttu-id="3cde0-234">Não</span><span class="sxs-lookup"><span data-stu-id="3cde0-234">No</span></span>|
|<span data-ttu-id="3cde0-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="3cde0-235">SharePoint</span></span>|<span data-ttu-id="3cde0-236">Site</span><span class="sxs-lookup"><span data-stu-id="3cde0-236">Site</span></span>|<span data-ttu-id="3cde0-237">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-237">Yes</span></span>|<span data-ttu-id="3cde0-238">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-238">Yes</span></span>|<span data-ttu-id="3cde0-239">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-239">Yes</span></span>|
|<span data-ttu-id="3cde0-240">Stream</span><span class="sxs-lookup"><span data-stu-id="3cde0-240">Stream</span></span>|<span data-ttu-id="3cde0-241">Canal, vídeo</span><span class="sxs-lookup"><span data-stu-id="3cde0-241">Channel, video</span></span>|<span data-ttu-id="3cde0-242">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-242">Yes</span></span>|<span data-ttu-id="3cde0-243">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-243">Yes</span></span>|<span data-ttu-id="3cde0-244">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-244">Yes</span></span>|
|<span data-ttu-id="3cde0-245">Teams</span><span class="sxs-lookup"><span data-stu-id="3cde0-245">Teams</span></span>|<span data-ttu-id="3cde0-246">Equipe</span><span class="sxs-lookup"><span data-stu-id="3cde0-246">Team</span></span>|<span data-ttu-id="3cde0-247">Não</span><span class="sxs-lookup"><span data-stu-id="3cde0-247">No</span></span>|<span data-ttu-id="3cde0-248">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-248">Yes</span></span>|<span data-ttu-id="3cde0-249">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-249">Yes</span></span>|
|<span data-ttu-id="3cde0-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="3cde0-250">Yammer</span></span>|<span data-ttu-id="3cde0-251">Group</span><span class="sxs-lookup"><span data-stu-id="3cde0-251">Group</span></span>|<span data-ttu-id="3cde0-252">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-252">Yes</span></span>|<span data-ttu-id="3cde0-253">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-253">Yes</span></span>|<span data-ttu-id="3cde0-254">Sim</span><span class="sxs-lookup"><span data-stu-id="3cde0-254">Yes</span></span>|

<span data-ttu-id="3cde0-255">Embora a tabela acima fornece uma visão geral de alto nível das interações de grupo com os serviços do Microsoft 365, há várias nuances e complexidades que você deve entender.</span><span class="sxs-lookup"><span data-stu-id="3cde0-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="3cde0-256">As seções a seguir abordam melhor as cargas de trabalho específicas e suas interações com grupos.</span><span class="sxs-lookup"><span data-stu-id="3cde0-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="3cde0-257">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3cde0-257">Azure AD</span></span>

<span data-ttu-id="3cde0-258">O Azure AD fornece os recursos subjacentes de gerenciamento de identidade no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cde0-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="3cde0-259">**Principais recursos fornecidos aos Grupos**</span><span class="sxs-lookup"><span data-stu-id="3cde0-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3cde0-260">Associação a um grupo</span><span class="sxs-lookup"><span data-stu-id="3cde0-260">Group membership</span></span>
- <span data-ttu-id="3cde0-261">Política de nomeação</span><span class="sxs-lookup"><span data-stu-id="3cde0-261">Naming policy</span></span>
- <span data-ttu-id="3cde0-262">Política de expiração</span><span class="sxs-lookup"><span data-stu-id="3cde0-262">Expiration policy</span></span>
- <span data-ttu-id="3cde0-263">Convidados</span><span class="sxs-lookup"><span data-stu-id="3cde0-263">Guests</span></span>
- <span data-ttu-id="3cde0-264">Restrição de criação de grupo</span><span class="sxs-lookup"><span data-stu-id="3cde0-264">Restriction of Group creation</span></span>

<span data-ttu-id="3cde0-265">**O Azure AD pode criar um Grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="3cde0-266">Sim, os Grupos do Microsoft 365 podem ser criados a partir do Azure AD por meio do portal da Web de administração, por meio do PowerShell ou da API do Graph.</span><span class="sxs-lookup"><span data-stu-id="3cde0-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="3cde0-267">**O Azure AD existe sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="3cde0-268">Sim, o Azure AD executa um grande número de serviços que não têm relação com os Grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cde0-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="3cde0-269">Cada grupo do Microsoft 365 é representado como um objeto no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3cde0-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="3cde0-270">**Pode haver várias instâncias do Azure AD por Grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="3cde0-271">Não, há apenas uma instância do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3cde0-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="3cde0-272">**O Azure AD pode ser associado a vários Grupos?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="3cde0-273">Sim, porque o Azure AD é a plataforma subjacente que fornece o serviço de associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="3cde0-274">**A associação do Azure AD com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="3cde0-275">Não, o Azure AD é a plataforma subjacente onde existem grupos.</span><span class="sxs-lookup"><span data-stu-id="3cde0-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="3cde0-276">**A exclusão da instância exclui o Grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="3cde0-277">Excluir o grupo no Azure AD excluirá conteúdo e serviços relevantes associados ao grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="3cde0-278">Teams</span><span class="sxs-lookup"><span data-stu-id="3cde0-278">Teams</span></span>

<span data-ttu-id="3cde0-279">O Teams é um espaço de trabalho centralizado em chat destinado a aprimorar a colaboração, fornecendo uma interface singular para interagir com uma variedade de serviços da Microsoft e de terceiros.</span><span class="sxs-lookup"><span data-stu-id="3cde0-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="3cde0-280">Por padrão, quando uma equipe é criada, a caixa de correio e o calendário associados ao grupo do Microsoft 365 ficam ocultos na Lista de Endereços Global no Exchange, bem como no Outlook.</span><span class="sxs-lookup"><span data-stu-id="3cde0-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="3cde0-281">Isso pode ser substituído manualmente por um administrador se o usuário quiser usar o Outlook e o Teams no mesmo grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cde0-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="3cde0-282">**Principais recursos fornecidos aos Grupos**</span><span class="sxs-lookup"><span data-stu-id="3cde0-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3cde0-283">Conversas</span><span class="sxs-lookup"><span data-stu-id="3cde0-283">Conversations</span></span>
- <span data-ttu-id="3cde0-284">Canais & guias</span><span class="sxs-lookup"><span data-stu-id="3cde0-284">Channels & tabs</span></span>
- <span data-ttu-id="3cde0-285">Reuniões</span><span class="sxs-lookup"><span data-stu-id="3cde0-285">Meetings</span></span>

<span data-ttu-id="3cde0-286">**O Teams pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="3cde0-287">Sim, criar uma nova equipe criará um novo grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cde0-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="3cde0-288">Também é possível criar uma equipe para um grupo existente que não tenha uma no momento.</span><span class="sxs-lookup"><span data-stu-id="3cde0-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="3cde0-289">**As equipes existem sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="3cde0-290">Não, não é possível que uma equipe exista sem um Grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="3cde0-291">**Pode haver várias equipes por grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="3cde0-292">Não, a relação entre uma equipe e um grupo é 1:1.</span><span class="sxs-lookup"><span data-stu-id="3cde0-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="3cde0-293">**Uma equipe pode ser associada a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="3cde0-294">Não, a própria equipe só pode ser associada a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="3cde0-295">**A associação de uma equipe com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="3cde0-296">Não, a equipe só pode ser associada ao grupo ao qual estava originalmente associado.</span><span class="sxs-lookup"><span data-stu-id="3cde0-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="3cde0-297">**A exclusão da equipe exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="3cde0-298">Sim, excluir a equipe do Microsoft Teams excluirá o grupo, os serviços associados ao grupo e o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="3cde0-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="3cde0-299">Exchange</span></span>

<span data-ttu-id="3cde0-300">O Exchange Online fornece mensagens, calendário, contatos e funcionalidades associadas.</span><span class="sxs-lookup"><span data-stu-id="3cde0-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="3cde0-301">No contexto de um Grupo, apenas um único recurso está associado, em vez de uma instância de serviço inteira.</span><span class="sxs-lookup"><span data-stu-id="3cde0-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="3cde0-302">**Principais recursos fornecidos aos Grupos**</span><span class="sxs-lookup"><span data-stu-id="3cde0-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3cde0-303">Caixa de correio e calendário</span><span class="sxs-lookup"><span data-stu-id="3cde0-303">Mailbox and calendar</span></span>
- <span data-ttu-id="3cde0-304">Capacidade de enviar emails para todos os membros do Grupo</span><span class="sxs-lookup"><span data-stu-id="3cde0-304">Ability to email all Group members</span></span>
- <span data-ttu-id="3cde0-305">Armazenamento de conversas de canal do Teams para fins de Descoberta e, comentários do Planner</span><span class="sxs-lookup"><span data-stu-id="3cde0-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="3cde0-306">**O Exchange pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="3cde0-307">Sim, é possível criar um grupo no Centro de administração do Exchange Online, bem como no Outlook.</span><span class="sxs-lookup"><span data-stu-id="3cde0-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="3cde0-308">Você também pode converter listas de distribuição do Exchange em grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cde0-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="3cde0-309">**O Exchange existe sem um Grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="3cde0-310">Sim, o Exchange Online fornece vários serviços, incluindo caixas de correio e calendários compartilhados, sem qualquer associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="3cde0-311">**Pode haver várias instâncias de caixas de correio ou calendários do Exchange por grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="3cde0-312">Não, só pode haver uma única caixa de correio e calendário do Exchange Online para um grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="3cde0-313">**Caixas de correio e calendários do Exchange podem ser associados a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="3cde0-314">Não, a caixa de correio e o calendário têm uma relação 1:1 com o grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="3cde0-315">É possível compartilhar a caixa de correio com outros usuários ou grupos, no entanto, isso não estabelece nenhuma forma de associação de serviço.</span><span class="sxs-lookup"><span data-stu-id="3cde0-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="3cde0-316">**A associação da caixa de correio ou do calendário do Exchange com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="3cde0-317">Não, a caixa de correio e o calendário não podem ser alterados para um grupo diferente.</span><span class="sxs-lookup"><span data-stu-id="3cde0-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="3cde0-318">No entanto, o conteúdo pode ser movido de uma caixa de correio para outra no Outlook ou usando uma ferramenta de terceiros.</span><span class="sxs-lookup"><span data-stu-id="3cde0-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="3cde0-319">**A exclusão da caixa de correio exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="3cde0-320">Sim, excluir a caixa de correio no Exchange excluirá o grupo, bem como os serviços e o conteúdo associados ao grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="3cde0-321">Forms</span><span class="sxs-lookup"><span data-stu-id="3cde0-321">Forms</span></span>

<span data-ttu-id="3cde0-322">Forms provides web-based surveys and quizzes.</span><span class="sxs-lookup"><span data-stu-id="3cde0-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="3cde0-323">**Principais recursos fornecidos aos grupos**</span><span class="sxs-lookup"><span data-stu-id="3cde0-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="3cde0-324">Propriedade de formulários</span><span class="sxs-lookup"><span data-stu-id="3cde0-324">Ownership of forms</span></span>

<span data-ttu-id="3cde0-325">**O Forms pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="3cde0-326">Não, o Forms não pode criar um grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="3cde0-327">**Existem formulários sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="3cde0-328">Sim, pesquisas e testes podem ser criados diretamente na conta de um usuário final.</span><span class="sxs-lookup"><span data-stu-id="3cde0-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="3cde0-329">**Pode haver vários formulários por grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="3cde0-330">Sim, pode haver vários formulários associados a um grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="3cde0-331">**Os formulários podem ser associados a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="3cde0-332">Não, um formulário só pode ser associado a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="3cde0-333">**A associação de um formulário com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="3cde0-334">Não, uma vez que um formulário é associado a um grupo (criado diretamente dentro ou pela propriedade transferida de um indivíduo), ele não pode ser movido para outro grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="3cde0-335">**A exclusão do formulário exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="3cde0-336">Não, não é possível excluir um grupo da interface formulários, somente formulários individuais.</span><span class="sxs-lookup"><span data-stu-id="3cde0-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="3cde0-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="3cde0-337">OneNote</span></span>

<span data-ttu-id="3cde0-338">O OneNote é um aplicativo de bloco de anotações digital.</span><span class="sxs-lookup"><span data-stu-id="3cde0-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="3cde0-339">O bloco de anotações do OneNote criado com um grupo é um arquivo no site do SharePoint associado, em vez de um serviço conectado ao grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="3cde0-340">**Principais recursos fornecidos aos grupos**</span><span class="sxs-lookup"><span data-stu-id="3cde0-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="3cde0-341">Bloco de anotações compartilhado (armazenado na biblioteca do SharePoint associada ao grupo)</span><span class="sxs-lookup"><span data-stu-id="3cde0-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="3cde0-342">**O OneNote pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="3cde0-343">Não, o aplicativo OneNote não pode criar um grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="3cde0-344">**Os blocos de anotações do OneNote existem sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="3cde0-345">Sim, os blocos de anotações podem ser criados diretamente no OneDrive ou em outros locais compartilhados.</span><span class="sxs-lookup"><span data-stu-id="3cde0-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="3cde0-346">**Pode haver vários blocos de anotações do OneNote por grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="3cde0-347">Sim, um bloco de anotações é criado por padrão e outros podem ser adicionados, no entanto, qualquer link para o OneNote de serviços associados ao grupo sempre irá para o bloco de anotações padrão.</span><span class="sxs-lookup"><span data-stu-id="3cde0-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="3cde0-348">**Um bloco de anotações do OneNote pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="3cde0-349">Não, o bloco de anotações é armazenado na biblioteca de sites do SharePoint associada ao grupo e vinculado a partir de várias interfaces.</span><span class="sxs-lookup"><span data-stu-id="3cde0-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="3cde0-350">No entanto, ele pode ser compartilhado com outros grupos da mesma maneira que pode ser compartilhado com indivíduos.</span><span class="sxs-lookup"><span data-stu-id="3cde0-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="3cde0-351">**A associação do bloco de anotações com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="3cde0-352">Não, o próprio bloco de anotações é associado ao grupo e pode ser acessado diretamente de outros serviços conectados ao grupo, no entanto, o conteúdo pode ser movido de um bloco de anotações para outro dentro do aplicativo OneNote.</span><span class="sxs-lookup"><span data-stu-id="3cde0-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="3cde0-353">**Excluir o bloco de anotações exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="3cde0-354">No entanto, se o bloco de anotações do OneNote for excluído, talvez haja links desfeitos em alguns dos serviços associados ao grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="3cde0-355">Planner</span><span class="sxs-lookup"><span data-stu-id="3cde0-355">Planner</span></span>

<span data-ttu-id="3cde0-356">O Planner é um serviço leve de gerenciamento de tarefas de grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="3cde0-357">**Principais recursos fornecidos aos grupos**</span><span class="sxs-lookup"><span data-stu-id="3cde0-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="3cde0-358">Quadro para gerenciar tarefas de grupo</span><span class="sxs-lookup"><span data-stu-id="3cde0-358">Board for managing group tasks</span></span>

<span data-ttu-id="3cde0-359">**O Planner pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="3cde0-360">Sim, a criação de um plano criará um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="3cde0-361">**Existe um quadro do Planner sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="3cde0-362">Não, um plano deve ser associado a um grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="3cde0-363">**Pode haver vários planos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="3cde0-364">Sim, pode haver vários planos por grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="3cde0-365">**Um plano pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="3cde0-366">Não, um plano depende apenas da associação do grupo para determinar o acesso.</span><span class="sxs-lookup"><span data-stu-id="3cde0-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="3cde0-367">**A associação de um plano com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="3cde0-368">Não, no entanto, copiar um plano cria um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="3cde0-369">Um Grupo criado por qualquer outro aplicativo não será automaticamente aparecer no Planner para um usuário.</span><span class="sxs-lookup"><span data-stu-id="3cde0-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="3cde0-370">Para acessar o quadro inicialmente, será necessário abri-lo a partir de outra interface baseada em grupo, como o Outlook.</span><span class="sxs-lookup"><span data-stu-id="3cde0-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="3cde0-371">**A exclusão do plano exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="3cde0-372">Sim, a exclusão do plano excluirá o grupo e os serviços e o conteúdo associados ao grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="3cde0-373">Power Apps</span><span class="sxs-lookup"><span data-stu-id="3cde0-373">Power Apps</span></span>

<span data-ttu-id="3cde0-374">O Power Apps fornece uma tela para o desenvolvimento de aplicativos sem código.</span><span class="sxs-lookup"><span data-stu-id="3cde0-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="3cde0-375">**Principais recursos fornecidos aos Grupos**</span><span class="sxs-lookup"><span data-stu-id="3cde0-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3cde0-376">Os aplicativos podem ser compartilhados com um grupo para serem executados e modificados</span><span class="sxs-lookup"><span data-stu-id="3cde0-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="3cde0-377">**O Power Apps pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="3cde0-378">Não, o Power Apps não pode criar um grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cde0-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="3cde0-379">**O Power Apps existe sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="3cde0-380">Sim, os aplicativos podem ser criados no Power Apps e residir na conta de criadores até serem compartilhados ou publicados.</span><span class="sxs-lookup"><span data-stu-id="3cde0-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="3cde0-381">**Pode haver vários aplicativos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="3cde0-382">Sim, pode haver vários aplicativos compartilhados com um grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="3cde0-383">**Os aplicativos podem ser associados a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="3cde0-384">Sim, um aplicativo pode ser compartilhado com vários grupos.</span><span class="sxs-lookup"><span data-stu-id="3cde0-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="3cde0-385">**A associação de um aplicativo com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="3cde0-386">Sim, como a associação entre o Power Apps e um grupo do Microsoft 365 está compartilhando apenas – o aplicativo ainda reside com o criador.</span><span class="sxs-lookup"><span data-stu-id="3cde0-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3cde0-387">[Os grupos devem estar habilitados para que os aplicativos possam ser compartilhados com eles.](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)</span><span class="sxs-lookup"><span data-stu-id="3cde0-387">[Groups must be security enabled before apps can be shared with them](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="3cde0-388">**A exclusão do aplicativo exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="3cde0-389">Não, os aplicativos não estão conectados ao grupo além de serem compartilhados com eles.</span><span class="sxs-lookup"><span data-stu-id="3cde0-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="3cde0-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="3cde0-390">Power Automate</span></span>

<span data-ttu-id="3cde0-391">O Power Automate (anteriormente conhecido como Microsoft Flow) fornece fluxos de trabalho e serviços de automação.</span><span class="sxs-lookup"><span data-stu-id="3cde0-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="3cde0-392">**Principais recursos fornecidos aos grupos**</span><span class="sxs-lookup"><span data-stu-id="3cde0-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="3cde0-393">Os fluxos de trabalho podem ser compartilhados com um grupo a ser executado e modificado.</span><span class="sxs-lookup"><span data-stu-id="3cde0-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="3cde0-394">**O Power Automate pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="3cde0-395">Não, o Power Automate não pode criar um grupo do Microsoft 365 no contexto de estar associado a um.</span><span class="sxs-lookup"><span data-stu-id="3cde0-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="3cde0-396">No entanto, é possível criar um fluxo que execute várias operações, como criar um grupo de segurança do Azure AD ou atualizar a associação de um grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cde0-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="3cde0-397">**Existem fluxos sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="3cde0-398">Sim, os fluxos podem ser criados no Power Automate e residir na conta de criadores até serem compartilhados ou publicados.</span><span class="sxs-lookup"><span data-stu-id="3cde0-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="3cde0-399">**Pode haver vários fluxos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="3cde0-400">Sim, pode haver vários fluxos compartilhados com um grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="3cde0-401">**Um fluxo pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="3cde0-402">Sim, um fluxo pode ser compartilhado com vários grupos.</span><span class="sxs-lookup"><span data-stu-id="3cde0-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="3cde0-403">**A associação de um fluxo com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="3cde0-404">Sim, como a associação entre o Power Automate e um grupo do Microsoft 365 está compartilhando apenas – o fluxo ainda reside com o criador.</span><span class="sxs-lookup"><span data-stu-id="3cde0-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="3cde0-405">**Excluir um fluxo exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="3cde0-406">Não, como os Aplicativos Do Power, os fluxos não estão conectados ao grupo além de serem compartilhados com eles.</span><span class="sxs-lookup"><span data-stu-id="3cde0-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="3cde0-407">Power BI (clássico)</span><span class="sxs-lookup"><span data-stu-id="3cde0-407">Power BI (classic)</span></span>

<span data-ttu-id="3cde0-408">O Power BI fornece painéis e relatórios interativos orientados a dados.</span><span class="sxs-lookup"><span data-stu-id="3cde0-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="3cde0-409">**Principais recursos fornecidos aos grupos**</span><span class="sxs-lookup"><span data-stu-id="3cde0-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="3cde0-410">Relatórios de dados</span><span class="sxs-lookup"><span data-stu-id="3cde0-410">Data reporting</span></span>

<span data-ttu-id="3cde0-411">**O Power BI pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="3cde0-412">Sim, criar um espaço de trabalho clássico criará um grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cde0-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="3cde0-413">**Existe um espaço de trabalho clássico do Power BI sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="3cde0-414">Não, [um espaço de trabalho clássico no Power BI deve ser associado a um grupo.](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace)</span><span class="sxs-lookup"><span data-stu-id="3cde0-414">No, [a classic workspace in Power BI must be associated with a group](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="3cde0-415">**Pode haver vários espaços de trabalho do Power BI por grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="3cde0-416">Não, a relação entre um espaço de trabalho clássico e um grupo é de 1:1.</span><span class="sxs-lookup"><span data-stu-id="3cde0-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="3cde0-417">**Um espaço de trabalho pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="3cde0-418">Tecnicamente não, enquanto o espaço de trabalho clássico é criado com o grupo, o conteúdo pode ser compartilhado fora do Grupo com usuários e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="3cde0-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="3cde0-419">**A associação do espaço de trabalho com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="3cde0-420">Não, o espaço de trabalho clássico em si está associado ao Grupo, no entanto, o conteúdo pode ser movido de um espaço de trabalho para outro dentro da interface do Power BI ou exportando conteúdo localmente.</span><span class="sxs-lookup"><span data-stu-id="3cde0-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="3cde0-421">**A exclusão do espaço de trabalho exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="3cde0-422">Sim, excluir o espaço de trabalho no Power BI excluirá serviços e conteúdo associados a grupos e grupos.</span><span class="sxs-lookup"><span data-stu-id="3cde0-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="3cde0-423">Power BI (novo)</span><span class="sxs-lookup"><span data-stu-id="3cde0-423">Power BI (new)</span></span>

<span data-ttu-id="3cde0-424">O Power BI fornece painéis e relatórios interativos orientados a dados.</span><span class="sxs-lookup"><span data-stu-id="3cde0-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="3cde0-425">Ao criar um novo espaço de trabalho no Power BI não cria um Grupo do Microsoft 365, criar um grupo por qualquer outro meio cria um novo espaço de trabalho (não clássico) no Power BI.</span><span class="sxs-lookup"><span data-stu-id="3cde0-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="3cde0-426">**Principais recursos fornecidos aos grupos**</span><span class="sxs-lookup"><span data-stu-id="3cde0-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="3cde0-427">Relatórios de dados</span><span class="sxs-lookup"><span data-stu-id="3cde0-427">Data reporting</span></span>

<span data-ttu-id="3cde0-428">**O Power BI pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="3cde0-429">Não, não é possível criar um grupo do Microsoft 365 a partir da nova interface do Power BI.</span><span class="sxs-lookup"><span data-stu-id="3cde0-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="3cde0-430">**O novo espaço de trabalho do Power BI existe sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="3cde0-431">Sim, é possível ter relatórios e espaços de trabalho criados no Power BI que não estão associados aos grupos do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cde0-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="3cde0-432">**Pode haver vários espaços de trabalho por grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="3cde0-433">Sim, [vários espaços de trabalho criados pelo Power BI podem ser compartilhados com um único grupo.](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)</span><span class="sxs-lookup"><span data-stu-id="3cde0-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="3cde0-434">**Um espaço de trabalho pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="3cde0-435">Não, um espaço de trabalho criado pelo Power BI só pode ser associado a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="3cde0-436">**A associação de um espaço de trabalho com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="3cde0-437">Sim e não.</span><span class="sxs-lookup"><span data-stu-id="3cde0-437">Yes and no.</span></span> <span data-ttu-id="3cde0-438">Um espaço de trabalho criado pelo Power BI só pode ser associado a um único grupo de cada vez, mas pode alterar a associação a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="3cde0-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="3cde0-439">Um espaço de trabalho criado no Power BI por um grupo é associado permanentemente a esse grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="3cde0-440">**A exclusão do espaço de trabalho exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="3cde0-441">Sim, excluir o espaço de trabalho no Power BI excluirá o grupo e os serviços e conteúdo associados ao grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="3cde0-442">Project para a Web</span><span class="sxs-lookup"><span data-stu-id="3cde0-442">Project for the web</span></span>

<span data-ttu-id="3cde0-443">O Project para a Web oferece a capacidade de criar planos de projeto, gráficos de Gantt e mapas.</span><span class="sxs-lookup"><span data-stu-id="3cde0-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="3cde0-444">Principais recursos fornecidos aos grupos.</span><span class="sxs-lookup"><span data-stu-id="3cde0-444">Key features provided to groups.</span></span>

- <span data-ttu-id="3cde0-445">Planos do Project</span><span class="sxs-lookup"><span data-stu-id="3cde0-445">Project plans</span></span>

<span data-ttu-id="3cde0-446">**O Project para a Web pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="3cde0-447">Sim, é possível criar um novo grupo do Microsoft 365 diretamente do Project para a Web.</span><span class="sxs-lookup"><span data-stu-id="3cde0-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="3cde0-448">**Os projetos existem sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="3cde0-449">Sim, os projetos podem existir sem serem associados a um grupo do Microsoft 365, no entanto, a atribuição de tarefas requer associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="3cde0-450">**Pode haver vários projetos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="3cde0-451">Sim, é possível conectar vários projetos em um único grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="3cde0-452">**O projeto pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="3cde0-453">Não, um projeto só pode ser associado a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="3cde0-454">**A associação de um projeto com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="3cde0-455">Não, depois que a associação com um grupo é estabelecida, ela não pode mudar.</span><span class="sxs-lookup"><span data-stu-id="3cde0-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="3cde0-456">**A exclusão do projeto exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="3cde0-457">Não, excluir o projeto no Project para a Web não excluirá o grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="3cde0-458">Roteiro</span><span class="sxs-lookup"><span data-stu-id="3cde0-458">Roadmap</span></span>

<span data-ttu-id="3cde0-459">O mapa fornece a capacidade de criar roteiros de projeto com o Project para a Web e o Project Online.</span><span class="sxs-lookup"><span data-stu-id="3cde0-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="3cde0-460">**Principais recursos fornecidos aos Grupos**</span><span class="sxs-lookup"><span data-stu-id="3cde0-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3cde0-461">Mapas do projeto</span><span class="sxs-lookup"><span data-stu-id="3cde0-461">Project roadmaps</span></span>

<span data-ttu-id="3cde0-462">**O Roadmap pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="3cde0-463">Sim, é possível criar um novo grupo do Microsoft 365 diretamente do roteiro.</span><span class="sxs-lookup"><span data-stu-id="3cde0-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="3cde0-464">**O Roteiro existe sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="3cde0-465">Sim, os mapas podem existir sem estarem associados a um grupo do Microsoft 365, no entanto, compartilhar o mapa requer associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="3cde0-466">**Pode haver vários mapas por grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="3cde0-467">Sim, é possível conectar vários mapas a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="3cde0-468">**Um mapa pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="3cde0-469">Não, um mapa só pode ser associado a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="3cde0-470">**A associação de um mapa com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="3cde0-471">Não, depois que a associação com um grupo é estabelecida, ela não pode mudar.</span><span class="sxs-lookup"><span data-stu-id="3cde0-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="3cde0-472">**Excluir o mapa exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="3cde0-473">Não, excluir o mapa não excluirá o grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="3cde0-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="3cde0-474">SharePoint</span></span>

<span data-ttu-id="3cde0-475">O SharePoint é uma plataforma de gerenciamento de conteúdo baseada na Web que fornece, entre outras coisas, serviços de armazenamento para vários serviços do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cde0-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="3cde0-476">**Principais recursos fornecidos aos Grupos**</span><span class="sxs-lookup"><span data-stu-id="3cde0-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3cde0-477">Biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="3cde0-477">Document library</span></span>
- <span data-ttu-id="3cde0-478">Biblioteca para armazenamento do bloco de anotações do OneNote</span><span class="sxs-lookup"><span data-stu-id="3cde0-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="3cde0-479">Armazenamento de arquivos wiki do Teams</span><span class="sxs-lookup"><span data-stu-id="3cde0-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="3cde0-480">**O SharePoint pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="3cde0-481">Sim, criar um site de equipe no SharePoint criará um grupo do Microsoft 365 por padrão.</span><span class="sxs-lookup"><span data-stu-id="3cde0-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="3cde0-482">Também é possível criar um grupo e, opcionalmente, uma equipe para um site existente.</span><span class="sxs-lookup"><span data-stu-id="3cde0-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="3cde0-483">**Os sites do SharePoint existem sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="3cde0-484">Sim, o SharePoint oferece vários serviços e sites não associados ao grupo, como sites de comunicação e hub.</span><span class="sxs-lookup"><span data-stu-id="3cde0-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="3cde0-485">**Pode haver vários sites por grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="3cde0-486">Não, só pode haver um único site por grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="3cde0-487">Os canais privados no Teams usam sites adicionais que não estão conectados ao grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="3cde0-488">**Os sites podem ser associados a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="3cde0-489">Tecnicamente não, mas enquanto um site é criado com um grupo, o conteúdo pode ser compartilhado com outros grupos.</span><span class="sxs-lookup"><span data-stu-id="3cde0-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="3cde0-490">**A associação de um site com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="3cde0-491">Não, o próprio site está associado ao grupo, no entanto, o conteúdo pode ser movido de um site para outro dentro da interface do SharePoint, exportando o conteúdo localmente ou usando uma ferramenta de terceiros.</span><span class="sxs-lookup"><span data-stu-id="3cde0-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="3cde0-492">**A exclusão do site exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="3cde0-493">Sim, excluir o site no SharePoint excluirá conteúdo e serviços associados a grupos e grupos.</span><span class="sxs-lookup"><span data-stu-id="3cde0-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="3cde0-494">Stream</span><span class="sxs-lookup"><span data-stu-id="3cde0-494">Stream</span></span>

<span data-ttu-id="3cde0-495">O Microsoft Stream é uma plataforma de hospedagem e compartilhamento de vídeo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="3cde0-496">**Principais recursos fornecidos aos Grupos**</span><span class="sxs-lookup"><span data-stu-id="3cde0-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3cde0-497">Armazenamento de vídeo</span><span class="sxs-lookup"><span data-stu-id="3cde0-497">Video storage</span></span>
- <span data-ttu-id="3cde0-498">Gravação de reunião do Teams</span><span class="sxs-lookup"><span data-stu-id="3cde0-498">Teams meeting recording</span></span>
- <span data-ttu-id="3cde0-499">Canais de vídeo</span><span class="sxs-lookup"><span data-stu-id="3cde0-499">Video channels</span></span>

<span data-ttu-id="3cde0-500">**O Stream pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="3cde0-501">Sim, é possível criar um novo grupo do Microsoft 365 diretamente do Stream.</span><span class="sxs-lookup"><span data-stu-id="3cde0-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="3cde0-502">**O Stream existe sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="3cde0-503">Sim, canais de vídeo e vídeos podem existir no Stream sem estarem associados a um grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="3cde0-504">**Pode haver vários vídeos e canais por Grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="3cde0-505">Sim, pode haver vários vídeos e canais em cada grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="3cde0-506">**Um vídeo ou canal pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="3cde0-507">Sim, enquanto um vídeo ou canal é criado com um grupo, ele pode ser compartilhado com outros grupos.</span><span class="sxs-lookup"><span data-stu-id="3cde0-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="3cde0-508">**A associação com um Grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="3cde0-509">Sim e não; vídeos no Stream pertencem ao uploader original ou gravador de reunião e, portanto, podem ser associados a qualquer grupo, no entanto, os canais de vídeo só podem ser associados ao grupo em que foram originalmente criados.</span><span class="sxs-lookup"><span data-stu-id="3cde0-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="3cde0-510">**A exclusão de vídeos ou canais exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="3cde0-511">Não, excluir vídeos ou canais não exclui o grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="3cde0-512">No entanto, excluir o próprio grupo no Stream excluirá serviços e conteúdo associados ao grupo, exceto para os vídeos reais.</span><span class="sxs-lookup"><span data-stu-id="3cde0-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="3cde0-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="3cde0-513">Yammer</span></span>

<span data-ttu-id="3cde0-514">O Yammer é uma plataforma social corporativa projetada para promover o envolvimento da comunidade dentro e entre organizações.</span><span class="sxs-lookup"><span data-stu-id="3cde0-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="3cde0-515">Criar uma comunidade (anteriormente conhecida como "grupo") no Yammer cria uma caixa de correio, mas no momento isso não é usado.</span><span class="sxs-lookup"><span data-stu-id="3cde0-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="3cde0-516">Um grupo do Microsoft 365 associado ao Yammer não pode ser usado com uma equipe no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3cde0-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="3cde0-517">**Principais recursos fornecidos aos Grupos**</span><span class="sxs-lookup"><span data-stu-id="3cde0-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="3cde0-518">Área de conversa</span><span class="sxs-lookup"><span data-stu-id="3cde0-518">Conversation area</span></span>

<span data-ttu-id="3cde0-519">**O Yammer pode criar um grupo do Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="3cde0-520">Sim, criar um novo grupo no Yammer criará um novo grupo do Microsoft 365, se as plataformas estão conectadas e o usuário tem a capacidade de criar um grupo.</span><span class="sxs-lookup"><span data-stu-id="3cde0-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="3cde0-521">Um grupo do Yammer com um grupo associado do Microsoft 365 não pode ser criado em qualquer interface ou serviço que não seja o próprio Yammer.</span><span class="sxs-lookup"><span data-stu-id="3cde0-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="3cde0-522">**Existe um grupo do Yammer sem um grupo do Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="3cde0-523">Sim, é possível criar um grupo do Yammer sem um grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cde0-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="3cde0-524">Se a plataforma Yammer não estiver conectada aos grupos do Microsoft 365 ou se os usuários não têm a capacidade de criar um grupo do Microsoft 365, os grupos do Yammer são criados sem uma associação de grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cde0-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="3cde0-525">**Pode haver vários grupos do Yammer por grupo do Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="3cde0-526">Não, a relação entre um grupo do Yammer e um grupo do Microsoft 365 é 1:1.</span><span class="sxs-lookup"><span data-stu-id="3cde0-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="3cde0-527">**Um grupo do Yammer pode ser associado a vários grupos do Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="3cde0-528">Não, o grupo do Yammer só pode ser associado a um único grupo do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cde0-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="3cde0-529">É possível que postagens sejam compartilhadas ou movidas para outros grupos do Yammer.</span><span class="sxs-lookup"><span data-stu-id="3cde0-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="3cde0-530">**A associação de um grupo do Yammer com um grupo do Microsoft 365 pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="3cde0-531">Não, o grupo do Yammer só pode ser associado ao grupo do Microsoft 365 ao qual estava originalmente associado.</span><span class="sxs-lookup"><span data-stu-id="3cde0-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="3cde0-532">**Excluir o grupo do Yammer exclui o grupo do Microsoft 365?**</span><span class="sxs-lookup"><span data-stu-id="3cde0-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="3cde0-533">Sim, excluir o grupo no Yammer excluirá conteúdo e serviços relacionados ao grupo e ao grupo da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3cde0-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3cde0-534">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3cde0-534">Related topics</span></span>

[<span data-ttu-id="3cde0-535">Planejamento de governança de colaboração passo a passo</span><span class="sxs-lookup"><span data-stu-id="3cde0-535">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="3cde0-536">Criar seu plano de governança de colaboração</span><span class="sxs-lookup"><span data-stu-id="3cde0-536">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

