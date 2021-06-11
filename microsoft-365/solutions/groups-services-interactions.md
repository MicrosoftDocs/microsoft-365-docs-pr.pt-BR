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
recommendations: false
description: Interações de serviços de grupos
ms.openlocfilehash: f9b0d7ca61d55e3d23aa94577fc8257073b26675
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539198"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="33249-103">Interações de serviços de grupos</span><span class="sxs-lookup"><span data-stu-id="33249-103">Groups services interactions</span></span>

<span data-ttu-id="33249-104">Microsoft 365 Os grupos oferecem um fabric comum para vários serviços e cargas de trabalho na plataforma Microsoft 365 para oferecer uma experiência conectada aos usuários finais.</span><span class="sxs-lookup"><span data-stu-id="33249-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="33249-105">No seu núcleo, existe um Microsoft 365 para fornecer:</span><span class="sxs-lookup"><span data-stu-id="33249-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="33249-106">Uma maneira de gerenciar a associação (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="33249-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="33249-107">Um local para mensagens e conversas ocorrerem (Exchange caixa de correio, Microsoft Teams, Yammer)</span><span class="sxs-lookup"><span data-stu-id="33249-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="33249-108">Um local para que os arquivos sejam armazenados (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="33249-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="33249-109">Um calendário para agendamento (Exchange)</span><span class="sxs-lookup"><span data-stu-id="33249-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="33249-110">Um bloco de anotações para captura de anotações (OneNote)</span><span class="sxs-lookup"><span data-stu-id="33249-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="33249-111">No ponto de criação do grupo, vários outros recursos também são provisionados, no entanto, eles não ficam visíveis até que sejam acessados pela primeira vez a partir do serviço:</span><span class="sxs-lookup"><span data-stu-id="33249-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="33249-112">Um quadro para gerenciar tarefas de grupo (Planner)</span><span class="sxs-lookup"><span data-stu-id="33249-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="33249-113">Um espaço de trabalho para relatórios (Power BI)</span><span class="sxs-lookup"><span data-stu-id="33249-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="33249-114">Uma área para vídeos compartilhados (Microsoft Stream)</span><span class="sxs-lookup"><span data-stu-id="33249-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="33249-115">Uma área para formulários compartilhados (Formulários)</span><span class="sxs-lookup"><span data-stu-id="33249-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="33249-116">Em Microsoft 365, outros serviços são capazes de interagir com grupos Microsoft 365 para oferecer funcionalidades e recursos adicionais aos membros do grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="33249-117">Exemplos disso incluem:</span><span class="sxs-lookup"><span data-stu-id="33249-117">Examples of this include:</span></span>

- <span data-ttu-id="33249-118">Power Apps aplicativos</span><span class="sxs-lookup"><span data-stu-id="33249-118">Power Apps for apps</span></span>
- <span data-ttu-id="33249-119">Power Automate fluxos de trabalho</span><span class="sxs-lookup"><span data-stu-id="33249-119">Power Automate for workflows</span></span>
- <span data-ttu-id="33249-120">Project na Web e roteiro para gerenciamento de projeto baseado em cascata</span><span class="sxs-lookup"><span data-stu-id="33249-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="33249-121">Teams conversas baseadas em canal</span><span class="sxs-lookup"><span data-stu-id="33249-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="33249-122">Yammer para comunidades de interesse</span><span class="sxs-lookup"><span data-stu-id="33249-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="33249-123">Interações do usuário com grupos</span><span class="sxs-lookup"><span data-stu-id="33249-123">User interactions with groups</span></span>

<span data-ttu-id="33249-124">Microsoft 365 Os grupos podem ser criados e gerenciados a partir de uma variedade de interfaces, tanto pelos administradores quanto pelos usuários finais.</span><span class="sxs-lookup"><span data-stu-id="33249-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="33249-125">Experiências administrativas</span><span class="sxs-lookup"><span data-stu-id="33249-125">Administrative experiences</span></span>

<span data-ttu-id="33249-126">Os administradores podem criar e gerenciar grupos de Microsoft 365 de vários centros de administração de carga de trabalho, interfaces de linha de comando que suportam scripts, bem como aplicativos personalizados que interagem com a API Graph.</span><span class="sxs-lookup"><span data-stu-id="33249-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="33249-127">A única exceção a isso é Yammer grupos – que devem ser criados a partir da interface Yammer Web.</span><span class="sxs-lookup"><span data-stu-id="33249-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="33249-128">**Configurações relacionadas**</span><span class="sxs-lookup"><span data-stu-id="33249-128">**Related settings**</span></span>

<span data-ttu-id="33249-129">Entre as várias interfaces administrativas que podem gerenciar as configurações de grupo existem várias sobreposições que você deve estar ciente.</span><span class="sxs-lookup"><span data-stu-id="33249-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="33249-130">**Centro de administração do Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="33249-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="33249-131">No centro Microsoft 365 de administração, o acesso de convidados a Grupos é habilitado por padrão, assim como a capacidade de permitir que os proprietários adicionem convidados.</span><span class="sxs-lookup"><span data-stu-id="33249-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="33249-132">Não há mais controles no nível da organização disponíveis para grupos deste centro de administração.</span><span class="sxs-lookup"><span data-stu-id="33249-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="33249-133">**Centro de Administração do Microsoft Azure AD**</span><span class="sxs-lookup"><span data-stu-id="33249-133">**Azure AD admin center**</span></span>

<span data-ttu-id="33249-134">O centro de administração do Azure AD oferece controles sobre se os usuários podem criar Grupos ou atribuir proprietários em portais do Azure, bem como definições de política de expiração e nomenização.</span><span class="sxs-lookup"><span data-stu-id="33249-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="33249-135">O centro de administração também fornece várias medidas de controle de convite para convidados que vão além da do centro de administração Microsoft 365, como a capacidade de limitar se não proprietários também podem convidar convidados</span><span class="sxs-lookup"><span data-stu-id="33249-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="33249-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="33249-136">**SharePoint**</span></span>

<span data-ttu-id="33249-137">SharePoint sites são criados com grupos de segurança proprietário, membro e visitante, com os dois primeiros correspondentes aos seus Microsoft 365 do Grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="33249-138">Embora a associação SharePoint sites online seja geralmente gerenciada pelo grupo Microsoft 365 associado, não é uma relação bidirecional.</span><span class="sxs-lookup"><span data-stu-id="33249-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="33249-139">Quaisquer alterações na associação no nível Microsoft 365 grupo são refletidas no SharePoint, no entanto, se a associação for alterada no grupo SharePoint, isso não será refletido no grupo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33249-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="33249-140">Experiências do usuário</span><span class="sxs-lookup"><span data-stu-id="33249-140">User experiences</span></span>

<span data-ttu-id="33249-141">Os usuários finais podem criar grupos de vários dos serviços dentro Microsoft 365 e, em outros, eles só podem compartilhar com um grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="33249-142">Os seguintes serviços permitem a criação de grupos por usuários finais:</span><span class="sxs-lookup"><span data-stu-id="33249-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="33249-143">Outlook Planner Project para a web SharePoint Stream Microsoft Teams Yammer</span><span class="sxs-lookup"><span data-stu-id="33249-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="33249-144">**Restrição da criação de grupo**</span><span class="sxs-lookup"><span data-stu-id="33249-144">**Restriction of group creation**</span></span>

<span data-ttu-id="33249-145">Uma abordagem comum para controlar a expansão de equipes é limitar quais usuários podem criar.</span><span class="sxs-lookup"><span data-stu-id="33249-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="33249-146">Isso só pode ser feito limitando a criação de grupos.</span><span class="sxs-lookup"><span data-stu-id="33249-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="33249-147">Isso afeta a capacidade de criar grupos de outros serviços onde isso pode ser necessário para o usuário final.</span><span class="sxs-lookup"><span data-stu-id="33249-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="33249-148">Microsoft 365 Os grupos não suportam a capacidade de restringir a criação de grupos de alguns aplicativos ou serviços, permitindo-o de outros.</span><span class="sxs-lookup"><span data-stu-id="33249-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="33249-149">A experiência da restrição de criação de grupo varia entre aplicativos e serviços:</span><span class="sxs-lookup"><span data-stu-id="33249-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="33249-150">Aplicativo ou serviço</span><span class="sxs-lookup"><span data-stu-id="33249-150">App or service</span></span>|<span data-ttu-id="33249-151">Experiência</span><span class="sxs-lookup"><span data-stu-id="33249-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="33249-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="33249-152">Outlook</span></span>|<span data-ttu-id="33249-153">**Nova opção** de grupo é removida do novo menu na página pessoas</span><span class="sxs-lookup"><span data-stu-id="33249-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="33249-154">Planner</span><span class="sxs-lookup"><span data-stu-id="33249-154">Planner</span></span>|<span data-ttu-id="33249-155">**Novo plano** explica que a criação de grupo foi desligada e oferece para adicionar o plano a um grupo existente</span><span class="sxs-lookup"><span data-stu-id="33249-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="33249-156">Project para a Web e o Roteiro</span><span class="sxs-lookup"><span data-stu-id="33249-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="33249-157">**O menu** Criar grupo explica que a criação de grupo é restrita e sugere o uso de um grupo existente.</span><span class="sxs-lookup"><span data-stu-id="33249-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="33249-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="33249-158">SharePoint</span></span>|<span data-ttu-id="33249-159">Ainda é possível criar um site de equipe que não esteja conectado a um grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="33249-160">Stream</span><span class="sxs-lookup"><span data-stu-id="33249-160">Stream</span></span>|<span data-ttu-id="33249-161">**A** opção Group não aparece no **menu Criar**.</span><span class="sxs-lookup"><span data-stu-id="33249-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="33249-162">Teams</span><span class="sxs-lookup"><span data-stu-id="33249-162">Teams</span></span>|<span data-ttu-id="33249-163">O usuário não pode criar uma equipe com um novo grupo, mas ainda pode criar uma equipe que utilize um grupo existente.</span><span class="sxs-lookup"><span data-stu-id="33249-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="33249-164">**Criar um botão de** equipe é substituído por **Criar equipe de um grupo**.</span><span class="sxs-lookup"><span data-stu-id="33249-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="33249-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="33249-165">Yammer</span></span>|<span data-ttu-id="33249-166">**A opção Criar um** grupo é removida da navegação principal Grupos/Comunidades.</span><span class="sxs-lookup"><span data-stu-id="33249-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="33249-167">Interações de serviços com grupos</span><span class="sxs-lookup"><span data-stu-id="33249-167">Services interactions with groups</span></span>

<span data-ttu-id="33249-168">Consulte o cartaz Grupos no Microsoft 365 para obter informações sobre diferentes tipos de grupos, como eles são criados e gerenciados e algumas recomendações de governança.</span><span class="sxs-lookup"><span data-stu-id="33249-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="33249-169">[![Imagem em miniatura de infográfico sobre os grupos](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="33249-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="33249-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="33249-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="33249-171">A tabela a seguir fornece uma visão geral das Microsoft 365 grupos interações com vários serviços:</span><span class="sxs-lookup"><span data-stu-id="33249-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="33249-172">Produto</span><span class="sxs-lookup"><span data-stu-id="33249-172">Product</span></span>|<span data-ttu-id="33249-173">Recursos</span><span class="sxs-lookup"><span data-stu-id="33249-173">Features</span></span>|<span data-ttu-id="33249-174">O serviço</span><span class="sxs-lookup"><span data-stu-id="33249-174">Does the service</span></span><br><span data-ttu-id="33249-175">existir sem um grupo?</span><span class="sxs-lookup"><span data-stu-id="33249-175">exist without a group?</span></span>|<span data-ttu-id="33249-176">O serviço pode</span><span class="sxs-lookup"><span data-stu-id="33249-176">Can the service</span></span><br><span data-ttu-id="33249-177">criar um grupo?</span><span class="sxs-lookup"><span data-stu-id="33249-177">create a group?</span></span>|<span data-ttu-id="33249-178">Exclui o</span><span class="sxs-lookup"><span data-stu-id="33249-178">Does deleting the</span></span><br><span data-ttu-id="33249-179">exclua o grupo?</span><span class="sxs-lookup"><span data-stu-id="33249-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="33249-180">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="33249-180">Azure AD</span></span>|<span data-ttu-id="33249-181">Associação, controles de grupo, Convidados</span><span class="sxs-lookup"><span data-stu-id="33249-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="33249-182">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-182">Yes</span></span>|<span data-ttu-id="33249-183">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-183">Yes</span></span>|<span data-ttu-id="33249-184">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-184">Yes</span></span>|
|<span data-ttu-id="33249-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="33249-185">Exchange</span></span>|<span data-ttu-id="33249-186">Calendário, caixa de correio</span><span class="sxs-lookup"><span data-stu-id="33249-186">Calendar, mailbox</span></span>|<span data-ttu-id="33249-187">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-187">Yes</span></span>|<span data-ttu-id="33249-188">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-188">Yes</span></span>|<span data-ttu-id="33249-189">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-189">Yes</span></span>|
|<span data-ttu-id="33249-190">Formulários</span><span class="sxs-lookup"><span data-stu-id="33249-190">Forms</span></span>|<span data-ttu-id="33249-191">Formulário</span><span class="sxs-lookup"><span data-stu-id="33249-191">Form</span></span>|<span data-ttu-id="33249-192">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-192">Yes</span></span>|<span data-ttu-id="33249-193">Não</span><span class="sxs-lookup"><span data-stu-id="33249-193">No</span></span>|<span data-ttu-id="33249-194">Não</span><span class="sxs-lookup"><span data-stu-id="33249-194">No</span></span>|
|<span data-ttu-id="33249-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="33249-195">OneNote</span></span>|<span data-ttu-id="33249-196">Notebook</span><span class="sxs-lookup"><span data-stu-id="33249-196">Notebook</span></span>|<span data-ttu-id="33249-197">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-197">Yes</span></span>|<span data-ttu-id="33249-198">Não</span><span class="sxs-lookup"><span data-stu-id="33249-198">No</span></span>|<span data-ttu-id="33249-199">Não</span><span class="sxs-lookup"><span data-stu-id="33249-199">No</span></span>|
|<span data-ttu-id="33249-200">Planner</span><span class="sxs-lookup"><span data-stu-id="33249-200">Planner</span></span>|<span data-ttu-id="33249-201">Quadro de Tarefas</span><span class="sxs-lookup"><span data-stu-id="33249-201">Task board</span></span>|<span data-ttu-id="33249-202">Não</span><span class="sxs-lookup"><span data-stu-id="33249-202">No</span></span>|<span data-ttu-id="33249-203">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-203">Yes</span></span>|<span data-ttu-id="33249-204">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-204">Yes</span></span>|
|<span data-ttu-id="33249-205">Power Apps app</span><span class="sxs-lookup"><span data-stu-id="33249-205">Power Apps app</span></span>|<span data-ttu-id="33249-206">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="33249-206">App</span></span>|<span data-ttu-id="33249-207">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-207">Yes</span></span>|<span data-ttu-id="33249-208">Não</span><span class="sxs-lookup"><span data-stu-id="33249-208">No</span></span>|<span data-ttu-id="33249-209">Não</span><span class="sxs-lookup"><span data-stu-id="33249-209">No</span></span>|
|<span data-ttu-id="33249-210">Power Automate</span><span class="sxs-lookup"><span data-stu-id="33249-210">Power Automate</span></span>|<span data-ttu-id="33249-211">Fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="33249-211">Workflow</span></span>|<span data-ttu-id="33249-212">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-212">Yes</span></span>|<span data-ttu-id="33249-213">Não</span><span class="sxs-lookup"><span data-stu-id="33249-213">No</span></span>|<span data-ttu-id="33249-214">Não</span><span class="sxs-lookup"><span data-stu-id="33249-214">No</span></span>|
|<span data-ttu-id="33249-215">Power BI (clássico)</span><span class="sxs-lookup"><span data-stu-id="33249-215">Power BI (classic)</span></span>|<span data-ttu-id="33249-216">Espaço de trabalho</span><span class="sxs-lookup"><span data-stu-id="33249-216">Workspace</span></span>|<span data-ttu-id="33249-217">Não</span><span class="sxs-lookup"><span data-stu-id="33249-217">No</span></span>|<span data-ttu-id="33249-218">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-218">Yes</span></span>|<span data-ttu-id="33249-219">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-219">Yes</span></span>|
|<span data-ttu-id="33249-220">Power BI (novo)</span><span class="sxs-lookup"><span data-stu-id="33249-220">Power BI (new)</span></span>|<span data-ttu-id="33249-221">Espaço de trabalho</span><span class="sxs-lookup"><span data-stu-id="33249-221">Workspace</span></span>|<span data-ttu-id="33249-222">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-222">Yes</span></span>|<span data-ttu-id="33249-223">Não</span><span class="sxs-lookup"><span data-stu-id="33249-223">No</span></span>|<span data-ttu-id="33249-224">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-224">Yes</span></span>|
|<span data-ttu-id="33249-225">Project para a Web</span><span class="sxs-lookup"><span data-stu-id="33249-225">Project for the web</span></span>|<span data-ttu-id="33249-226">Project plano</span><span class="sxs-lookup"><span data-stu-id="33249-226">Project plan</span></span>|<span data-ttu-id="33249-227">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-227">Yes</span></span>|<span data-ttu-id="33249-228">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-228">Yes</span></span>|<span data-ttu-id="33249-229">Não</span><span class="sxs-lookup"><span data-stu-id="33249-229">No</span></span>|
|<span data-ttu-id="33249-230">Roteiro</span><span class="sxs-lookup"><span data-stu-id="33249-230">Roadmap</span></span>|<span data-ttu-id="33249-231">Roteiro</span><span class="sxs-lookup"><span data-stu-id="33249-231">Roadmap</span></span>|<span data-ttu-id="33249-232">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-232">Yes</span></span>|<span data-ttu-id="33249-233">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-233">Yes</span></span>|<span data-ttu-id="33249-234">Não</span><span class="sxs-lookup"><span data-stu-id="33249-234">No</span></span>|
|<span data-ttu-id="33249-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="33249-235">SharePoint</span></span>|<span data-ttu-id="33249-236">Site</span><span class="sxs-lookup"><span data-stu-id="33249-236">Site</span></span>|<span data-ttu-id="33249-237">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-237">Yes</span></span>|<span data-ttu-id="33249-238">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-238">Yes</span></span>|<span data-ttu-id="33249-239">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-239">Yes</span></span>|
|<span data-ttu-id="33249-240">Stream</span><span class="sxs-lookup"><span data-stu-id="33249-240">Stream</span></span>|<span data-ttu-id="33249-241">Canal, vídeo</span><span class="sxs-lookup"><span data-stu-id="33249-241">Channel, video</span></span>|<span data-ttu-id="33249-242">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-242">Yes</span></span>|<span data-ttu-id="33249-243">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-243">Yes</span></span>|<span data-ttu-id="33249-244">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-244">Yes</span></span>|
|<span data-ttu-id="33249-245">Teams</span><span class="sxs-lookup"><span data-stu-id="33249-245">Teams</span></span>|<span data-ttu-id="33249-246">Equipe</span><span class="sxs-lookup"><span data-stu-id="33249-246">Team</span></span>|<span data-ttu-id="33249-247">Não</span><span class="sxs-lookup"><span data-stu-id="33249-247">No</span></span>|<span data-ttu-id="33249-248">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-248">Yes</span></span>|<span data-ttu-id="33249-249">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-249">Yes</span></span>|
|<span data-ttu-id="33249-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="33249-250">Yammer</span></span>|<span data-ttu-id="33249-251">Group</span><span class="sxs-lookup"><span data-stu-id="33249-251">Group</span></span>|<span data-ttu-id="33249-252">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-252">Yes</span></span>|<span data-ttu-id="33249-253">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-253">Yes</span></span>|<span data-ttu-id="33249-254">Sim</span><span class="sxs-lookup"><span data-stu-id="33249-254">Yes</span></span>|

<span data-ttu-id="33249-255">Embora a tabela acima fornece uma visão geral de alto nível das interações de grupo com os serviços Microsoft 365, há várias nuances e complexidades que você deve entender.</span><span class="sxs-lookup"><span data-stu-id="33249-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="33249-256">As seções a seguir abordam mais detalhadamente as cargas de trabalho específicas e suas interações com grupos.</span><span class="sxs-lookup"><span data-stu-id="33249-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="33249-257">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="33249-257">Azure AD</span></span>

<span data-ttu-id="33249-258">O Azure AD fornece os recursos de gerenciamento de identidade subjacentes em Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33249-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="33249-259">**Principais recursos fornecidos para grupos**</span><span class="sxs-lookup"><span data-stu-id="33249-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="33249-260">Associação a um grupo</span><span class="sxs-lookup"><span data-stu-id="33249-260">Group membership</span></span>
- <span data-ttu-id="33249-261">Política de nomenrção</span><span class="sxs-lookup"><span data-stu-id="33249-261">Naming policy</span></span>
- <span data-ttu-id="33249-262">Política de expiração</span><span class="sxs-lookup"><span data-stu-id="33249-262">Expiration policy</span></span>
- <span data-ttu-id="33249-263">Convidados</span><span class="sxs-lookup"><span data-stu-id="33249-263">Guests</span></span>
- <span data-ttu-id="33249-264">Restrição da criação de grupo</span><span class="sxs-lookup"><span data-stu-id="33249-264">Restriction of Group creation</span></span>

<span data-ttu-id="33249-265">**O Azure AD pode criar um Grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="33249-266">Sim, Microsoft 365 grupos podem ser criados a partir do Azure AD por meio do portal da Web de administração, por meio do PowerShell ou Graph API.</span><span class="sxs-lookup"><span data-stu-id="33249-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="33249-267">**O Azure AD existe sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="33249-268">Sim, o Azure AD executa um grande número de serviços que não têm relação com Microsoft 365 Grupos.</span><span class="sxs-lookup"><span data-stu-id="33249-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="33249-269">Cada Microsoft 365 grupo é representado como um objeto no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="33249-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="33249-270">**Pode haver várias instâncias do Azure AD por Grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="33249-271">Não, há apenas uma instância do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="33249-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="33249-272">**O Azure AD pode ser associado a vários Grupos?**</span><span class="sxs-lookup"><span data-stu-id="33249-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="33249-273">Sim, porque o Azure AD é a plataforma subjacente que fornece o serviço de associação ao grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="33249-274">**A associação do Azure AD com uma mudança de grupo pode ser mudada?**</span><span class="sxs-lookup"><span data-stu-id="33249-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="33249-275">Não, o Azure AD é a plataforma subjacente onde os grupos existem.</span><span class="sxs-lookup"><span data-stu-id="33249-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="33249-276">**Excluir a instância exclui o Grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="33249-277">Excluir o grupo no Azure AD excluirá conteúdo e serviços associados a grupos relevantes.</span><span class="sxs-lookup"><span data-stu-id="33249-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="33249-278">Teams</span><span class="sxs-lookup"><span data-stu-id="33249-278">Teams</span></span>

<span data-ttu-id="33249-279">Teams é um espaço de trabalho centralizado em chat destinado a aprimorar a colaboração, fornecendo uma interface singular para interagir com uma variedade de serviços da Microsoft e de terceiros.</span><span class="sxs-lookup"><span data-stu-id="33249-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="33249-280">Por padrão, quando uma equipe é criada, a caixa de correio e o calendário associados ao grupo Microsoft 365 são ocultos da Lista de Endereços Global no Exchange, bem como Outlook.</span><span class="sxs-lookup"><span data-stu-id="33249-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="33249-281">Isso pode ser substituído manualmente por um administrador se o usuário quiser usar o Outlook e Teams no mesmo grupo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33249-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="33249-282">**Principais recursos fornecidos para grupos**</span><span class="sxs-lookup"><span data-stu-id="33249-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="33249-283">Conversas</span><span class="sxs-lookup"><span data-stu-id="33249-283">Conversations</span></span>
- <span data-ttu-id="33249-284">Canais & guias</span><span class="sxs-lookup"><span data-stu-id="33249-284">Channels & tabs</span></span>
- <span data-ttu-id="33249-285">Reuniões</span><span class="sxs-lookup"><span data-stu-id="33249-285">Meetings</span></span>

<span data-ttu-id="33249-286">**Pode Teams criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="33249-287">Sim, criar uma nova equipe criará um novo Microsoft 365 grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="33249-288">Também é possível criar uma equipe para um grupo existente que não tenha uma.</span><span class="sxs-lookup"><span data-stu-id="33249-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="33249-289">**As equipes existem sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="33249-290">Não, não é possível que uma equipe exista sem um Grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="33249-291">**Pode haver várias equipes por grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="33249-292">Não, a relação entre uma equipe e um grupo é 1:1.</span><span class="sxs-lookup"><span data-stu-id="33249-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="33249-293">**Uma equipe pode ser associada a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="33249-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="33249-294">Não, a própria equipe só pode ser associada a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="33249-295">**A associação de uma equipe com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="33249-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="33249-296">Não, a equipe só pode ser associada ao grupo ao qual foi originalmente associada.</span><span class="sxs-lookup"><span data-stu-id="33249-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="33249-297">**Excluir a equipe exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="33249-298">Sim, excluir a equipe no Microsoft Teams excluirá o grupo, os serviços associados ao grupo e o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="33249-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="33249-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="33249-299">Exchange</span></span>

<span data-ttu-id="33249-300">Exchange Online fornece mensagens, calendário, contatos e funcionalidades associadas.</span><span class="sxs-lookup"><span data-stu-id="33249-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="33249-301">No contexto de um Grupo, apenas um único recurso está associado – em vez de uma instância de serviço inteira.</span><span class="sxs-lookup"><span data-stu-id="33249-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="33249-302">**Principais recursos fornecidos para grupos**</span><span class="sxs-lookup"><span data-stu-id="33249-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="33249-303">Caixa de correio e calendário</span><span class="sxs-lookup"><span data-stu-id="33249-303">Mailbox and calendar</span></span>
- <span data-ttu-id="33249-304">Capacidade de enviar emails a todos os membros do Grupo</span><span class="sxs-lookup"><span data-stu-id="33249-304">Ability to email all Group members</span></span>
- <span data-ttu-id="33249-305">Armazenamento de conversas Teams canal para fins de Descoberta eDiscovery, comentários do Planner</span><span class="sxs-lookup"><span data-stu-id="33249-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="33249-306">**Pode Exchange criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="33249-307">Sim, é possível criar um grupo a partir do Exchange Online de administração, bem como de Outlook.</span><span class="sxs-lookup"><span data-stu-id="33249-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="33249-308">Você também pode converter Exchange listas de distribuição em Microsoft 365 grupos.</span><span class="sxs-lookup"><span data-stu-id="33249-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="33249-309">**O Exchange existe sem um Grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="33249-310">Sim, Exchange Online fornece vários serviços, incluindo caixas de correio compartilhadas e calendários, sem nenhuma associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="33249-311">**Pode haver várias instâncias de caixas de correio Exchange ou calendários por grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="33249-312">Não, só pode haver uma única caixa de correio Exchange Online e calendário para um grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="33249-313">**Pode Exchange caixas de correio e calendários sejam associados a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="33249-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="33249-314">Não, a caixa de correio e o calendário têm uma relação 1:1 com o grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="33249-315">É possível compartilhar a caixa de correio com outros usuários ou grupos, no entanto, isso não estabelece nenhuma forma de associação de serviço.</span><span class="sxs-lookup"><span data-stu-id="33249-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="33249-316">**A caixa Exchange caixa de correio ou a associação do calendário com uma alteração de grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="33249-317">Não, a caixa de correio e o calendário não podem ser alterados para um grupo diferente.</span><span class="sxs-lookup"><span data-stu-id="33249-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="33249-318">No entanto, o conteúdo pode ser movido de uma caixa de correio para outra dentro Outlook ou usando uma ferramenta de terceiros.</span><span class="sxs-lookup"><span data-stu-id="33249-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="33249-319">**Excluir a caixa de correio exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="33249-320">Sim, excluir a caixa de correio no Exchange excluirá o grupo, bem como os serviços e conteúdo associados ao grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="33249-321">Formulários</span><span class="sxs-lookup"><span data-stu-id="33249-321">Forms</span></span>

<span data-ttu-id="33249-322">Os formulários fornece pesquisas baseadas na Web e testes.</span><span class="sxs-lookup"><span data-stu-id="33249-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="33249-323">**Principais recursos fornecidos aos grupos**</span><span class="sxs-lookup"><span data-stu-id="33249-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="33249-324">Propriedade de formulários</span><span class="sxs-lookup"><span data-stu-id="33249-324">Ownership of forms</span></span>

<span data-ttu-id="33249-325">**Os formulários podem criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="33249-326">Não, o Forms não pode criar um grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="33249-327">**Os formulários existem sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="33249-328">Sim, pesquisas e testes podem ser criados diretamente na conta de um usuário final.</span><span class="sxs-lookup"><span data-stu-id="33249-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="33249-329">**Pode haver vários formulários por grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="33249-330">Sim, pode haver vários formulários associados a um grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="33249-331">**Os formulários podem ser associados a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="33249-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="33249-332">Não, um formulário só pode ser associado a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="33249-333">**A associação de um formulário com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="33249-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="33249-334">Não, uma vez que um formulário é associado a um grupo (criado diretamente dentro ou a propriedade transferida de um indivíduo) ele não pode ser movido para outro grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="33249-335">**Excluir o formulário exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="33249-336">Não, não é possível excluir um grupo da interface Forms, apenas formulários individuais.</span><span class="sxs-lookup"><span data-stu-id="33249-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="33249-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="33249-337">OneNote</span></span>

<span data-ttu-id="33249-338">OneNote é um aplicativo de bloco de anotações digital.</span><span class="sxs-lookup"><span data-stu-id="33249-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="33249-339">O OneNote bloco de anotações criado com um grupo é um arquivo no site SharePoint em vez de um serviço conectado a um grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="33249-340">**Principais recursos fornecidos aos grupos**</span><span class="sxs-lookup"><span data-stu-id="33249-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="33249-341">Bloco de anotações compartilhado (armazenado na biblioteca de SharePoint associada ao grupo)</span><span class="sxs-lookup"><span data-stu-id="33249-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="33249-342">**Pode OneNote criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="33249-343">Não, o OneNote não pode criar um grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="33249-344">**Os OneNote blocos de anotações existem sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="33249-345">Sim, os blocos de anotações podem ser criados diretamente OneDrive ou em outros locais compartilhados.</span><span class="sxs-lookup"><span data-stu-id="33249-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="33249-346">**Pode haver vários blocos OneNote blocos de anotações por grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="33249-347">Sim, um bloco de anotações é criado por padrão e outros podem ser adicionados, no entanto, qualquer link para OneNote de serviços associados ao grupo sempre irá para o bloco de anotações padrão.</span><span class="sxs-lookup"><span data-stu-id="33249-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="33249-348">**Um bloco OneNote bloco de anotações pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="33249-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="33249-349">Não, o bloco de anotações é armazenado na biblioteca de sites associada SharePoint grupo e vinculado de várias interfaces.</span><span class="sxs-lookup"><span data-stu-id="33249-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="33249-350">No entanto, ele pode ser compartilhado com outros Grupos da mesma maneira que pode ser compartilhado com indivíduos.</span><span class="sxs-lookup"><span data-stu-id="33249-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="33249-351">**A associação do bloco de anotações com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="33249-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="33249-352">Não, o bloco de anotações em si está associado ao grupo e pode ser acessado diretamente de outros serviços conectados ao grupo, no entanto, o conteúdo pode ser movido de um bloco de anotações para outro dentro do aplicativo OneNote.</span><span class="sxs-lookup"><span data-stu-id="33249-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="33249-353">**Excluir o bloco de anotações exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="33249-354">No entanto, se o bloco OneNote bloco de anotações for excluído, talvez haja links quebrados em alguns dos serviços associados ao grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="33249-355">Planner</span><span class="sxs-lookup"><span data-stu-id="33249-355">Planner</span></span>

<span data-ttu-id="33249-356">O Planner é um serviço leve de gerenciamento de tarefas de grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="33249-357">**Principais recursos fornecidos aos grupos**</span><span class="sxs-lookup"><span data-stu-id="33249-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="33249-358">Quadro para gerenciar tarefas de grupo</span><span class="sxs-lookup"><span data-stu-id="33249-358">Board for managing group tasks</span></span>

<span data-ttu-id="33249-359">**O Planner pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="33249-360">Sim, a criação de um plano criará um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="33249-361">**Existe um quadro do Planner sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="33249-362">Não, um plano deve ser associado a um grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="33249-363">**Pode haver vários planos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="33249-364">Sim, pode haver vários planos por grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="33249-365">**Um plano pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="33249-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="33249-366">Não, um plano depende somente da associação ao grupo para determinar o acesso.</span><span class="sxs-lookup"><span data-stu-id="33249-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="33249-367">**A associação de um plano com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="33249-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="33249-368">Não, no entanto, copiar um plano cria um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="33249-369">Um Grupo criado por qualquer outro aplicativo não será automaticamente aparecer no Planner para um usuário.</span><span class="sxs-lookup"><span data-stu-id="33249-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="33249-370">Para acessar a placa inicialmente, eles precisarão abri-lo a partir de outra interface baseada em grupo, como Outlook.</span><span class="sxs-lookup"><span data-stu-id="33249-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="33249-371">**Excluir o plano exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="33249-372">Sim, a exclusão do plano excluirá o conteúdo e os serviços associados ao grupo e ao grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="33249-373">Aplicativos de energia</span><span class="sxs-lookup"><span data-stu-id="33249-373">Power Apps</span></span>

<span data-ttu-id="33249-374">Power Apps fornece uma tela para desenvolvimento de aplicativos sem código.</span><span class="sxs-lookup"><span data-stu-id="33249-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="33249-375">**Principais recursos fornecidos para grupos**</span><span class="sxs-lookup"><span data-stu-id="33249-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="33249-376">Os aplicativos podem ser compartilhados com um grupo a ser executado e modificado</span><span class="sxs-lookup"><span data-stu-id="33249-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="33249-377">**Pode Power Apps criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="33249-378">Não, Power Apps não pode criar um Microsoft 365 grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="33249-379">**O Power Apps existe sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="33249-380">Sim, os aplicativos podem ser criados Power Apps e residir na conta de criadores até serem compartilhados ou publicados.</span><span class="sxs-lookup"><span data-stu-id="33249-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="33249-381">**Pode haver vários aplicativos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="33249-382">Sim, pode haver vários aplicativos compartilhados com um grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="33249-383">**Os aplicativos podem ser associados a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="33249-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="33249-384">Sim, um aplicativo pode ser compartilhado com vários grupos.</span><span class="sxs-lookup"><span data-stu-id="33249-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="33249-385">**A associação de um aplicativo com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="33249-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="33249-386">Sim, como a associação entre Power Apps e um grupo Microsoft 365 está compartilhando somente – o aplicativo ainda reside com o criador.</span><span class="sxs-lookup"><span data-stu-id="33249-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33249-387">[Os grupos devem estar habilitados para que os aplicativos possam ser compartilhados com eles.](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)</span><span class="sxs-lookup"><span data-stu-id="33249-387">[Groups must be security enabled before apps can be shared with them](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="33249-388">**Excluir o aplicativo exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="33249-389">Não, os aplicativos não estão conectados ao grupo além de serem compartilhados com eles.</span><span class="sxs-lookup"><span data-stu-id="33249-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="33249-390">Power Automate</span><span class="sxs-lookup"><span data-stu-id="33249-390">Power Automate</span></span>

<span data-ttu-id="33249-391">Power Automate (anteriormente conhecido como Microsoft Flow) fornece fluxos de trabalho e serviços de automação.</span><span class="sxs-lookup"><span data-stu-id="33249-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="33249-392">**Principais recursos fornecidos aos grupos**</span><span class="sxs-lookup"><span data-stu-id="33249-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="33249-393">Fluxos de trabalho podem ser compartilhados com um grupo a ser executado e modificado.</span><span class="sxs-lookup"><span data-stu-id="33249-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="33249-394">**Pode Power Automate criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="33249-395">Não, Power Automate não pode criar um grupo Microsoft 365 no contexto de estar associado a um.</span><span class="sxs-lookup"><span data-stu-id="33249-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="33249-396">No entanto, é possível criar um fluxo que execute várias operações, como criar um grupo de segurança do Azure AD ou atualizar a associação de um grupo Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33249-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="33249-397">**Existem fluxos sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="33249-398">Sim, os fluxos podem ser criados dentro Power Automate e residir na conta de criadores até serem compartilhados ou publicados.</span><span class="sxs-lookup"><span data-stu-id="33249-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="33249-399">**Pode haver vários fluxos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="33249-400">Sim, pode haver vários fluxos compartilhados com um grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="33249-401">**Um fluxo pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="33249-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="33249-402">Sim, um fluxo pode ser compartilhado com vários grupos.</span><span class="sxs-lookup"><span data-stu-id="33249-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="33249-403">**A associação de um fluxo com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="33249-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="33249-404">Sim, como a associação entre Power Automate e um grupo Microsoft 365 está compartilhando somente – o fluxo ainda reside com o criador.</span><span class="sxs-lookup"><span data-stu-id="33249-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="33249-405">**Excluir um fluxo exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="33249-406">Não, como Power Apps, os fluxos não estão conectados ao grupo além de serem compartilhados com eles.</span><span class="sxs-lookup"><span data-stu-id="33249-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="33249-407">Power BI (clássico)</span><span class="sxs-lookup"><span data-stu-id="33249-407">Power BI (classic)</span></span>

<span data-ttu-id="33249-408">Power BI fornece painéis e relatórios interativos orientados por dados.</span><span class="sxs-lookup"><span data-stu-id="33249-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="33249-409">**Principais recursos fornecidos aos grupos**</span><span class="sxs-lookup"><span data-stu-id="33249-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="33249-410">Relatório de dados</span><span class="sxs-lookup"><span data-stu-id="33249-410">Data reporting</span></span>

<span data-ttu-id="33249-411">**Pode Power BI criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="33249-412">Sim, criar um espaço de trabalho clássico criará um Microsoft 365 grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="33249-413">**Existe um Power BI de trabalho clássico sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="33249-414">Não, [um espaço de trabalho clássico no Power BI deve ser associado a um grupo](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span><span class="sxs-lookup"><span data-stu-id="33249-414">No, [a classic workspace in Power BI must be associated with a group](/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="33249-415">**Pode haver vários Power BI de trabalho por grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="33249-416">Não, a relação entre um espaço de trabalho clássico e um grupo é 1:1.</span><span class="sxs-lookup"><span data-stu-id="33249-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="33249-417">**Um espaço de trabalho pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="33249-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="33249-418">Tecnicamente não, enquanto o espaço de trabalho clássico é criado com o grupo, o conteúdo pode ser compartilhado fora do Grupo com usuários e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="33249-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="33249-419">**A associação do espaço de trabalho com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="33249-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="33249-420">Não, o espaço de trabalho clássico em si está associado ao Grupo, no entanto, o conteúdo pode ser movido de um espaço de trabalho para outro dentro da interface Power BI ou exportando conteúdo localmente.</span><span class="sxs-lookup"><span data-stu-id="33249-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="33249-421">**Excluir o espaço de trabalho exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="33249-422">Sim, excluir o espaço de trabalho no Power BI excluirá serviços e conteúdo associados a grupos e grupos.</span><span class="sxs-lookup"><span data-stu-id="33249-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="33249-423">Power BI (novo)</span><span class="sxs-lookup"><span data-stu-id="33249-423">Power BI (new)</span></span>

<span data-ttu-id="33249-424">Power BI fornece painéis e relatórios interativos orientados por dados.</span><span class="sxs-lookup"><span data-stu-id="33249-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="33249-425">Ao criar um novo espaço de trabalho no Power BI não cria um grupo Microsoft 365, criar um grupo por qualquer outro meio cria um novo espaço de trabalho (não clássico) no Power BI.</span><span class="sxs-lookup"><span data-stu-id="33249-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="33249-426">**Principais recursos fornecidos aos grupos**</span><span class="sxs-lookup"><span data-stu-id="33249-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="33249-427">Relatório de dados</span><span class="sxs-lookup"><span data-stu-id="33249-427">Data reporting</span></span>

<span data-ttu-id="33249-428">**Pode Power BI criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="33249-429">Não, não é possível criar um grupo Microsoft 365 a partir da nova Power BI interface.</span><span class="sxs-lookup"><span data-stu-id="33249-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="33249-430">**O novo Power BI de trabalho existe sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="33249-431">Sim, é possível ter relatórios e espaços de trabalho criados em Power BI que não estão associados Microsoft 365 grupos.</span><span class="sxs-lookup"><span data-stu-id="33249-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="33249-432">**Pode haver vários espaços de trabalho por grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="33249-433">Sim, [vários espaços de trabalho criados por Power BI podem ser compartilhados com um único grupo](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span><span class="sxs-lookup"><span data-stu-id="33249-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="33249-434">**Um espaço de trabalho pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="33249-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="33249-435">Não, um espaço de trabalho criado por Power BI pode ser associado apenas a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="33249-436">**A associação de um espaço de trabalho com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="33249-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="33249-437">Sim e não.</span><span class="sxs-lookup"><span data-stu-id="33249-437">Yes and no.</span></span> <span data-ttu-id="33249-438">Um espaço de trabalho criado por Power BI pode ser associado apenas a um único grupo por vez, mas pode alterar a associação a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="33249-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="33249-439">Um espaço de trabalho criado Power BI por um grupo está permanentemente associado a esse grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="33249-440">**Excluir o espaço de trabalho exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="33249-441">Sim, excluir o espaço de trabalho no Power BI excluirá o grupo e os serviços e conteúdo associados ao grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="33249-442">Project para a Web</span><span class="sxs-lookup"><span data-stu-id="33249-442">Project for the web</span></span>

<span data-ttu-id="33249-443">Project para a Web oferece a capacidade de criar planos de projeto, gráficos de Gantt e mapas.</span><span class="sxs-lookup"><span data-stu-id="33249-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="33249-444">Principais recursos fornecidos aos grupos.</span><span class="sxs-lookup"><span data-stu-id="33249-444">Key features provided to groups.</span></span>

- <span data-ttu-id="33249-445">Project planos</span><span class="sxs-lookup"><span data-stu-id="33249-445">Project plans</span></span>

<span data-ttu-id="33249-446">**Pode Project para a Web criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="33249-447">Sim, é possível criar um novo grupo Microsoft 365 diretamente do Project para a Web.</span><span class="sxs-lookup"><span data-stu-id="33249-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="33249-448">**Os projetos existem sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="33249-449">Sim, os projetos podem existir sem serem associados a um grupo Microsoft 365, no entanto, a atribuição de tarefas requer associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="33249-450">**Pode haver vários projetos por grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="33249-451">Sim, é possível conectar vários projetos em um único grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="33249-452">**O projeto pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="33249-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="33249-453">Não, um projeto só pode ser associado a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="33249-454">**A associação de um projeto com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="33249-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="33249-455">Não, depois que a associação com um grupo é estabelecida, ela não pode mudar.</span><span class="sxs-lookup"><span data-stu-id="33249-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="33249-456">**Excluir o projeto exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="33249-457">Não, excluir o projeto no Project para a Web não excluirá o grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="33249-458">Roteiro</span><span class="sxs-lookup"><span data-stu-id="33249-458">Roadmap</span></span>

<span data-ttu-id="33249-459">O roteiro oferece a capacidade de criar roteiros de projeto com Project para a Web e Project Online.</span><span class="sxs-lookup"><span data-stu-id="33249-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="33249-460">**Principais recursos fornecidos para grupos**</span><span class="sxs-lookup"><span data-stu-id="33249-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="33249-461">Project mapas</span><span class="sxs-lookup"><span data-stu-id="33249-461">Project roadmaps</span></span>

<span data-ttu-id="33249-462">**O Roteiro pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="33249-463">Sim, é possível criar um novo grupo Microsoft 365 diretamente a partir do roteiro.</span><span class="sxs-lookup"><span data-stu-id="33249-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="33249-464">**O Roteiro existe sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="33249-465">Sim, os roteiros podem existir sem serem associados a um grupo Microsoft 365, no entanto, o compartilhamento do roteiro requer associação de grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="33249-466">**Pode haver vários roteiros por grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="33249-467">Sim, é possível conectar vários roteiros a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="33249-468">**Um roteiro pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="33249-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="33249-469">Não, um roteiro só pode ser associado a um único grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="33249-470">**A associação de um roteiro com uma mudança de grupo pode ser feita?**</span><span class="sxs-lookup"><span data-stu-id="33249-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="33249-471">Não, depois que a associação com um grupo é estabelecida, ela não pode mudar.</span><span class="sxs-lookup"><span data-stu-id="33249-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="33249-472">**Excluir o roteiro exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="33249-473">Não, excluir o roteiro não excluirá o grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="33249-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="33249-474">SharePoint</span></span>

<span data-ttu-id="33249-475">SharePoint é uma plataforma de gerenciamento de conteúdo baseada na Web que fornece, entre outras coisas, serviços de armazenamento para vários Microsoft 365 serviços.</span><span class="sxs-lookup"><span data-stu-id="33249-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="33249-476">**Principais recursos fornecidos para grupos**</span><span class="sxs-lookup"><span data-stu-id="33249-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="33249-477">Biblioteca de documentos</span><span class="sxs-lookup"><span data-stu-id="33249-477">Document library</span></span>
- <span data-ttu-id="33249-478">Biblioteca para armazenamento de OneNote bloco de anotações</span><span class="sxs-lookup"><span data-stu-id="33249-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="33249-479">Armazenamento de arquivos wiki Teams wiki</span><span class="sxs-lookup"><span data-stu-id="33249-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="33249-480">**Pode SharePoint criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="33249-481">Sim, criar um site de equipe no SharePoint criará um grupo Microsoft 365 por padrão.</span><span class="sxs-lookup"><span data-stu-id="33249-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="33249-482">Também é possível criar um grupo e, opcionalmente, uma equipe para um site existente.</span><span class="sxs-lookup"><span data-stu-id="33249-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="33249-483">**Os SharePoint existem sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="33249-484">Sim, SharePoint oferece vários serviços e sites não associados a grupos, como sites de comunicação e hub.</span><span class="sxs-lookup"><span data-stu-id="33249-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="33249-485">**Pode haver vários sites por grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="33249-486">Não, só pode haver um único site por grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="33249-487">Canais privados no Teams usam sites adicionais que não estão conectados ao grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="33249-488">**Os sites podem ser associados a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="33249-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="33249-489">Tecnicamente não, mas embora um site seja criado com um grupo, o conteúdo pode ser compartilhado com outros grupos.</span><span class="sxs-lookup"><span data-stu-id="33249-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="33249-490">**A associação de um site com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="33249-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="33249-491">Não, o site em si está associado ao grupo, no entanto, o conteúdo pode ser movido de um site para outro dentro da interface SharePoint, exportando conteúdo localmente ou usando uma ferramenta de terceiros.</span><span class="sxs-lookup"><span data-stu-id="33249-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="33249-492">**A exclusão do site exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="33249-493">Sim, excluir o site no SharePoint excluirá serviços e conteúdo associados a grupos e grupos.</span><span class="sxs-lookup"><span data-stu-id="33249-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="33249-494">Stream</span><span class="sxs-lookup"><span data-stu-id="33249-494">Stream</span></span>

<span data-ttu-id="33249-495">O Microsoft Stream é uma plataforma de hospedagem e compartilhamento de vídeo.</span><span class="sxs-lookup"><span data-stu-id="33249-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="33249-496">**Principais recursos fornecidos para grupos**</span><span class="sxs-lookup"><span data-stu-id="33249-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="33249-497">Armazenamento de vídeo</span><span class="sxs-lookup"><span data-stu-id="33249-497">Video storage</span></span>
- <span data-ttu-id="33249-498">Teams de reunião</span><span class="sxs-lookup"><span data-stu-id="33249-498">Teams meeting recording</span></span>
- <span data-ttu-id="33249-499">Canais de vídeo</span><span class="sxs-lookup"><span data-stu-id="33249-499">Video channels</span></span>

<span data-ttu-id="33249-500">**O Stream pode criar um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="33249-501">Sim, é possível criar um novo grupo Microsoft 365 diretamente do Stream.</span><span class="sxs-lookup"><span data-stu-id="33249-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="33249-502">**O Stream existe sem um grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="33249-503">Sim, canais de vídeo e vídeos podem existir no Stream sem serem associados a um grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="33249-504">**Pode haver vários vídeos e canais por Grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="33249-505">Sim, pode haver vários vídeos e canais em cada grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="33249-506">**Um vídeo ou canal pode ser associado a vários grupos?**</span><span class="sxs-lookup"><span data-stu-id="33249-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="33249-507">Sim, enquanto um vídeo ou canal é criado com um grupo, ele pode ser compartilhado com outros grupos.</span><span class="sxs-lookup"><span data-stu-id="33249-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="33249-508">**Sua associação com um grupo pode mudar?**</span><span class="sxs-lookup"><span data-stu-id="33249-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="33249-509">Sim e não; os vídeos no Stream são de propriedade do uploader original ou do gravador de reunião e, portanto, podem ser associados a qualquer grupo, no entanto, os canais de vídeo só podem ser associados ao grupo em que foram criados originalmente.</span><span class="sxs-lookup"><span data-stu-id="33249-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="33249-510">**A exclusão de vídeos ou canais exclui o grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="33249-511">Não, excluir vídeos ou canais não exclui o grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="33249-512">No entanto, a exclusão do próprio grupo no Stream excluirá os serviços e conteúdo associados ao grupo, exceto os vídeos reais.</span><span class="sxs-lookup"><span data-stu-id="33249-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="33249-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="33249-513">Yammer</span></span>

<span data-ttu-id="33249-514">Yammer é uma plataforma social corporativa projetada para promover o envolvimento da comunidade dentro e entre organizações.</span><span class="sxs-lookup"><span data-stu-id="33249-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="33249-515">Criar uma comunidade (anteriormente conhecido como "grupo") no Yammer cria uma caixa de correio, mas, no momento, isso não é usado.</span><span class="sxs-lookup"><span data-stu-id="33249-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="33249-516">Um Microsoft 365 que está associado ao Yammer não pode ser usado com uma equipe em Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="33249-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="33249-517">**Principais recursos fornecidos para grupos**</span><span class="sxs-lookup"><span data-stu-id="33249-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="33249-518">Área de conversa</span><span class="sxs-lookup"><span data-stu-id="33249-518">Conversation area</span></span>

<span data-ttu-id="33249-519">**Pode Yammer criar um Microsoft 365 grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="33249-520">Sim, criar um novo grupo no Yammer criará um novo grupo Microsoft 365, se as plataformas estão conectadas e o usuário tem a capacidade de criar um grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="33249-521">Um Yammer grupo de Microsoft 365 associado não pode ser criado em qualquer interface ou serviço que não Yammer em si.</span><span class="sxs-lookup"><span data-stu-id="33249-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="33249-522">**Existe um Yammer sem um grupo Microsoft 365 grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="33249-523">Sim, é possível criar um grupo Yammer sem um Microsoft 365 grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="33249-524">Se a plataforma Yammer não estiver conectada a grupos Microsoft 365 ou os usuários não têm a capacidade de criar um grupo Microsoft 365, os grupos Yammer são criados sem uma associação Microsoft 365 grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="33249-525">**Pode haver vários grupos Yammer grupos por Microsoft 365 grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="33249-526">Não, a relação entre um grupo Yammer e um grupo Microsoft 365 é 1:1.</span><span class="sxs-lookup"><span data-stu-id="33249-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="33249-527">**Um grupo Yammer pode ser associado a vários grupos Microsoft 365 grupos?**</span><span class="sxs-lookup"><span data-stu-id="33249-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="33249-528">Não, o Yammer grupo só pode ser associado a um único grupo Microsoft 365 grupo.</span><span class="sxs-lookup"><span data-stu-id="33249-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="33249-529">É possível que as postagens sejam compartilhadas ou movidas para outros Yammer grupos.</span><span class="sxs-lookup"><span data-stu-id="33249-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="33249-530">**Pode uma Yammer de um grupo com uma Microsoft 365 de grupo mudar?**</span><span class="sxs-lookup"><span data-stu-id="33249-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="33249-531">Não, o Yammer grupo só pode ser associado ao grupo Microsoft 365 ao qual foi originalmente associado.</span><span class="sxs-lookup"><span data-stu-id="33249-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="33249-532">**A exclusão do grupo Yammer exclui o grupo Microsoft 365 grupo?**</span><span class="sxs-lookup"><span data-stu-id="33249-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="33249-533">Sim, excluir o grupo no Yammer excluirá conteúdo e serviços e serviços associados a grupos relacionados à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="33249-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

## <a name="related-topics"></a><span data-ttu-id="33249-534">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="33249-534">Related topics</span></span>

[<span data-ttu-id="33249-535">Planejamento de governança de colaboração passo a passo</span><span class="sxs-lookup"><span data-stu-id="33249-535">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="33249-536">Criar seu plano de governança de colaboração</span><span class="sxs-lookup"><span data-stu-id="33249-536">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)