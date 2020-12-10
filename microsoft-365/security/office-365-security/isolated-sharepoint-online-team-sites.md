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
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 71250a04-fd2d-4c3c-a32b-b8a838b19a54
description: Saiba mais sobre os sites de equipe isolados do SharePoint Online, incluindo os usos, os requisitos e os recursos com os quais podem ser usados.
ms.openlocfilehash: e4e45c8adffcf86d56a71e5b9935e634f2de9254
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616447"
---
# <a name="isolated-sharepoint-online-team-sites"></a><span data-ttu-id="b4ae3-103">Sites de equipe isolados do SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b4ae3-103">Isolated SharePoint Online team sites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


 <span data-ttu-id="b4ae3-104">**Resumo:** conheça as utilizações dos sites de equipe do SharePoint Online isolados.</span><span class="sxs-lookup"><span data-stu-id="b4ae3-104">**Summary:** Learn about the uses for isolated SharePoint Online team sites.</span></span>

<span data-ttu-id="b4ae3-p101">Os sites de equipe do Microsoft Office SharePoint Online são uma maneira fácil de criar rapidamente um espaço para colaboração em anotações, documentos, artigos, um calendário e outros recursos do Microsoft Office 365. Os sites de equipe do Microsoft Office SharePoint Online são baseados em um grupo do Microsoft 365 e possuem um modelo de administração simplificado para permitir a colaboração aberta entre um determinado conjunto de membros do grupo ou toda a organização. Um site de equipe padrão do Microsoft Office SharePoint Online permite que os membros do grupo do Microsoft 365 convidem outros usuários e controlem as configurações de permissões.</span><span class="sxs-lookup"><span data-stu-id="b4ae3-p101">SharePoint Online team sites are an easy way to quickly create a space for collaboration of notes, documents, articles, a calendar, and other resources in Microsoft Office 365. SharePoint Online team sites are based on a Microsoft 365 group and have a simplified administration model to allow open collaboration with a private set of group members or the entire organization. A default SharePoint Online team site allows members of the Microsoft 365 group to invite other users and control permissions settings.</span></span>

<span data-ttu-id="b4ae3-p102">No entanto, em alguns casos, você quer criar um site de equipe do SharePoint Online para colaboração em locais onde as permissões desse site sejam controladas com maior rigidez por meio da associação ao grupo e níveis de permissão do SharePoint Online, que são gerenciados apenas por administradores do SharePoint. Chamamos isso de um site isolado, que é isolado do conjunto de usuários que estão colaborando, visualizando seu conteúdo ou administrando o site. Um site isolado pode ser necessário para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b4ae3-p102">However, in some cases, you want to create a SharePoint Online team site for collaboration where the permissions of that site are more tightly controlled through group membership and SharePoint Online permission levels, which are only managed by SharePoint administrators. We call this an isolated site, which is isolated to the set of users that are either collaborating, viewing its contents, or administering the site. You might need an isolated site for the following:</span></span>

- <span data-ttu-id="b4ae3-111">Um projeto secreto em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b4ae3-111">A secret project within your organization.</span></span>

- <span data-ttu-id="b4ae3-112">O local da propriedade intelectual altamente confidencial ou valiosa para sua organização.</span><span class="sxs-lookup"><span data-stu-id="b4ae3-112">The location for highly-sensitive or valuable intellectual property for your organization.</span></span>

- <span data-ttu-id="b4ae3-113">Os recursos de uma ação judicial iniciada por sua organização ou à qual a empresa está sendo submetida.</span><span class="sxs-lookup"><span data-stu-id="b4ae3-113">The resources for a legal action taken by your organization or that to which it is being subjected.</span></span>

- <span data-ttu-id="b4ae3-114">Para compartilhar uma assinatura do Microsoft 365 entre várias organizações que possuem alguma sobreposição, mas, para a maioria delas, existem como entidades de negócios separadas.</span><span class="sxs-lookup"><span data-stu-id="b4ae3-114">To share a Microsoft 365 subscription between multiple organizations that have some overlap, but for the most part exist as separate business entities.</span></span>

<span data-ttu-id="b4ae3-115">Veja os requisitos de um site isolado:</span><span class="sxs-lookup"><span data-stu-id="b4ae3-115">Here are the requirements of an isolated site:</span></span>

- <span data-ttu-id="b4ae3-116">Apenas os administradores do SharePoint Online podem realizar a administração de sites, o que inclui a associação ao grupo para acessar o site e a configuração de permissões personalizadas.</span><span class="sxs-lookup"><span data-stu-id="b4ae3-116">Only SharePoint Online administrators can perform site administration, which includes group membership for access to the site and configuring custom permissions.</span></span>

- <span data-ttu-id="b4ae3-117">Os membros do site não podem convidar outros membros para o site de equipe.</span><span class="sxs-lookup"><span data-stu-id="b4ae3-117">Members of the site cannot invite other members to the team site.</span></span>

- <span data-ttu-id="b4ae3-p103">Os usuários que não são membros do site isolado não podem solicitar acesso ao site e verão uma página da Web de acesso negado ao tentar acessar qualquer URL associada ao site.</span><span class="sxs-lookup"><span data-stu-id="b4ae3-p103">Users who are not members of the isolated site cannot request access to the site. They will receive an access denied web page when they attempt to access any URL associated with the site.</span></span>

<span data-ttu-id="b4ae3-p104">A desvantagem de exigir controle de acesso centralizado e permissões personalizadas pelos administradores do Microsoft Office SharePoint Online é que o site manterá-se isolado ao longo do tempo. Por exemplo, os membros atuais não poderão, intencionalmente ou acidentalmente, convidar ou configurar permissões personalizadas para outros usuários na assinatura do Microsoft 365 que não sejam membros do site.</span><span class="sxs-lookup"><span data-stu-id="b4ae3-p104">The tradeoff of requiring centralized access control and custom permissions by SharePoint Online administrators is that the site remains isolated over time. For example, current members cannot, either intentionally or accidentally, invite or configure custom permissions for other users within the Microsoft 365 subscription who should not be members of the site.</span></span>

<span data-ttu-id="b4ae3-122">Um site isolado pode ser usado com outros recursos, como:</span><span class="sxs-lookup"><span data-stu-id="b4ae3-122">An isolated site can be used with other features, such as:</span></span>

- <span data-ttu-id="b4ae3-123">Gerenciamento de Direitos de Informação para garantir que os recursos do site permaneçam criptografados, mesmo que eles sejam baixados localmente e carregados em outro site que esteja disponível para toda a organização.</span><span class="sxs-lookup"><span data-stu-id="b4ae3-123">Information Rights Management to ensure that the resources on the site remain encrypted, even if they are downloaded locally and uploaded to another site that is available to the entire organization.</span></span>

- <span data-ttu-id="b4ae3-124">Prevenção contra a perda de dados para evitar que os usuários enviem os recursos do site, como arquivos, por email.</span><span class="sxs-lookup"><span data-stu-id="b4ae3-124">Data loss prevention to prevent users from sending the resources of the site, such as files, in email.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b4ae3-125">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="b4ae3-125">Next steps</span></span>

<span data-ttu-id="b4ae3-126">Para experimentar um site de equipe do SharePoint Online isolado em uma assinatura de avaliação, confira as instruções passo a passo no [Site de equipe do SharePoint Online isolado no seu ambiente de desenvolvimento/teste](isolated-sharepoint-online-team-site-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="b4ae3-126">To try out an isolated SharePoint Online team site in a trial subscription, see the step-by-step instructions in [Isolated SharePoint Online team site dev/test environment](isolated-sharepoint-online-team-site-dev-test-environment.md).</span></span>

<span data-ttu-id="b4ae3-127">Quando estiver pronto para implantar um site de equipe do SharePoint Online isolado na produção, confira as considerações de design passo a passo no [Projetar um site de equipe do SharePoint Online isolado](design-an-isolated-sharepoint-online-team-site.md).</span><span class="sxs-lookup"><span data-stu-id="b4ae3-127">When you are ready to deploy an isolated SharePoint Online team site in production, see the step-by-step design considerations in [Design an isolated SharePoint Online team site](design-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b4ae3-128">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b4ae3-128">Related topics</span></span>

[<span data-ttu-id="b4ae3-129">Projetar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="b4ae3-129">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="b4ae3-130">Gerenciar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="b4ae3-130">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="b4ae3-131">Implantar um site de equipe do SharePoint Online isolado</span><span class="sxs-lookup"><span data-stu-id="b4ae3-131">Deploy an isolated SharePoint Online team site</span></span>](deploy-an-isolated-sharepoint-online-team-site.md)
