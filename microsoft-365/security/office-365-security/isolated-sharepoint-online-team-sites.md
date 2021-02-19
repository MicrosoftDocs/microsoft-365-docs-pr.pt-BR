---
title: Sites de equipe isolados do SharePoint Online
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: Saiba mais sobre os sites de equipe isolados do SharePoint Online, incluindo os usos, os requisitos e os recursos com os quais podem ser usados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 056c6f2a463d38dd27b26d484995280dddedf436
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286580"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="bfbd5-103">Sites de equipe isolados do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bfbd5-103">Isolated SharePoint Online team sites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="bfbd5-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="bfbd5-104">**Applies to**</span></span>
- [<span data-ttu-id="bfbd5-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bfbd5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="bfbd5-106">Microsoft Defender para Office 365 Plano 1</span><span class="sxs-lookup"><span data-stu-id="bfbd5-106">Microsoft Defender for Office 365 plan 1</span></span>](office-365-atp.md)
- <span data-ttu-id="bfbd5-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="bfbd5-107">SharePoint Online</span></span> 

 <span data-ttu-id="bfbd5-108">**Resumo:** conheça as utilizações dos sites de equipe do SharePoint Online isolados.</span><span class="sxs-lookup"><span data-stu-id="bfbd5-108">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="bfbd5-p101">Os sites de equipe do Microsoft Office SharePoint Online são uma maneira fácil de criar rapidamente um espaço para colaboração. Os usuários podem trabalhar juntos em notas, documentos, artigos, um calendário e outros recursos no Microsoft Office 365. Os sites de equipe do Microsoft Office SharePoint Online são baseados em um grupo do Microsoft 365 e têm um modelo de administração simplificado para permitir a colaboração aberta com um conjunto privado de membros do grupo ou toda a organização. Um site de equipe do Microsoft Office SharePoint Online padrão permite que os membros do grupo Microsoft 365 convidem outros usuários e controlem as configurações de permissões.</span><span class="sxs-lookup"><span data-stu-id="bfbd5-p101">SharePoint Online team sites are an easy way to quickly create a space for collaboration. Users can work together on notes, documents, articles, a calendar, and other resources in Microsoft Office 365. SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization. A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span></span>

<span data-ttu-id="bfbd5-113">No entanto, às vezes você precisará que o acesso ao site seja controlado por associações de grupo e níveis de permissão do Microsoft Office SharePoint Online gerenciados por administradores do Microsoft Office SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="bfbd5-113">However, you'll sometimes need site access to be controlled by group memberships, and SharePoint Online permission levels managed by SharePoint administrators.</span></span> <span data-ttu-id="bfbd5-114">Chamamos isso de site isolado, que é isolado para o conjunto de usuários que estão colaborando, visualizando o seu conteúdo ou administrando o site.</span><span class="sxs-lookup"><span data-stu-id="bfbd5-114">We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site.</span></span> <span data-ttu-id="bfbd5-115">Talvez você precise de um site isolado para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bfbd5-115">You might need an isolated site for the following:</span></span>

- <span data-ttu-id="bfbd5-116">Um projeto secreto em sua organização.</span><span class="sxs-lookup"><span data-stu-id="bfbd5-116">A secret project within your organization.</span></span>

- <span data-ttu-id="bfbd5-117">O local da propriedade intelectual altamente confidencial ou valiosa para sua organização.</span><span class="sxs-lookup"><span data-stu-id="bfbd5-117">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>

- <span data-ttu-id="bfbd5-118">Os recursos de uma ação judicial iniciada por sua organização ou à qual a empresa está sendo submetida.</span><span class="sxs-lookup"><span data-stu-id="bfbd5-118">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>

- <span data-ttu-id="bfbd5-119">Para compartilhar uma assinatura do Microsoft 365 entre várias organizações que possuem alguma sobreposição, mas, para a maioria delas, existem como entidades de negócios separadas.</span><span class="sxs-lookup"><span data-stu-id="bfbd5-119">To share a Microsoft 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>

<span data-ttu-id="bfbd5-120">Veja os requisitos de um site isolado:</span><span class="sxs-lookup"><span data-stu-id="bfbd5-120">Here are the requirements of an isolated site:</span></span>

- <span data-ttu-id="bfbd5-121">Apenas os administradores do SharePoint Online podem realizar a administração de sites, o que inclui a associação ao grupo para acessar o site e a configuração de permissões personalizadas.</span><span class="sxs-lookup"><span data-stu-id="bfbd5-121">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>

- <span data-ttu-id="bfbd5-122">Os membros do site não podem convidar outros membros para o site de equipe.</span><span class="sxs-lookup"><span data-stu-id="bfbd5-122">Members of the site cannot invite other members to the team site.</span></span>

- <span data-ttu-id="bfbd5-p103">Os usuários que não são membros do site isolado não podem solicitar acesso ao site e verão uma página da Web de acesso negado ao tentar acessar qualquer URL associada ao site.</span><span class="sxs-lookup"><span data-stu-id="bfbd5-p103">Users who are not members of the isolated site cannot request access to the site. They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>

<span data-ttu-id="bfbd5-p104">A desvantagem de exigir controle de acesso centralizado e permissões personalizadas pelos administradores do Microsoft Office SharePoint Online é que o site manterá-se isolado ao longo do tempo. Por exemplo, os membros atuais não poderão, intencionalmente ou acidentalmente, convidar ou configurar permissões personalizadas para outros usuários na assinatura do Microsoft 365 que não sejam membros do site.</span><span class="sxs-lookup"><span data-stu-id="bfbd5-p104">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time. For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span></span>

<span data-ttu-id="bfbd5-127">Um site isolado pode ser usado com outros recursos, como:</span><span class="sxs-lookup"><span data-stu-id="bfbd5-127">An isolated site can be used with other features, such as:</span></span>

- <span data-ttu-id="bfbd5-128">Gerenciamento de Direitos de Informação para garantir que os recursos do site permaneçam criptografados, mesmo que eles sejam baixados localmente e carregados em outro site que esteja disponível para toda a organização.</span><span class="sxs-lookup"><span data-stu-id="bfbd5-128">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>

- <span data-ttu-id="bfbd5-129">Prevenção contra a perda de dados para evitar que os usuários enviem os recursos do site, como arquivos, por email.</span><span class="sxs-lookup"><span data-stu-id="bfbd5-129">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bfbd5-130">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="bfbd5-130">Next steps</span></span>

<span data-ttu-id="bfbd5-131">Para experimentar um site de equipe do SharePoint Online isolado em uma assinatura de avaliação, confira as instruções passo a passo no [Site de equipe do SharePoint Online isolado no seu ambiente de desenvolvimento/teste](isolated-sharepoint-online-team-site-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="bfbd5-131">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>

<span data-ttu-id="bfbd5-132">Quando estiver pronto para implantar um site de equipe do SharePoint Online isolado na produção, confira as considerações de design passo a passo no [Projetar um site de equipe do SharePoint Online isolado](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="bfbd5-132">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="bfbd5-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="bfbd5-133">Related topics</span></span>

[<span data-ttu-id="bfbd5-134">Projetar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="bfbd5-134">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="bfbd5-135">Gerenciar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="bfbd5-135">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="bfbd5-136">Implantar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="bfbd5-136">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
