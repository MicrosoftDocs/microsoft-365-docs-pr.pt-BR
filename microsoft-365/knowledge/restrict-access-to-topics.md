---
title: Restringir o acesso a tópicos em Tópicos do Microsoft Viva
description: Como excluir tópicos para impedi-los de serem descobertos.
author: efrene
ms.author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: d6dfb2f7f432a40c5b6e96a9437f50ba47e23387
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500876"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a><span data-ttu-id="69be5-103">Restringir o acesso a tópicos em Tópicos do Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="69be5-103">Restrict access to topics in Microsoft Viva Topics</span></span>

<span data-ttu-id="69be5-104">No Microsoft Viva, os participantes da sua organização podem querer garantir que tópicos específicos não sejam descobertos e expostos aos usuários licenciados.</span><span class="sxs-lookup"><span data-stu-id="69be5-104">In Microsoft Viva, stakeholders in your organization may want to make sure that specific topics aren't discovered and exposed to your licensed users.</span></span> <span data-ttu-id="69be5-105">Por exemplo, você pode estar trabalhando em um projeto que ainda não deseja expor informações.</span><span class="sxs-lookup"><span data-stu-id="69be5-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="69be5-106">Embora as permissões do Office 365 em sites, arquivos e outros recursos impeçam que os usuários de Experiências de Tópicos visualizam informações confidenciais em tópicos, há proteções adicionais para impedir que tópicos específicos sejam descobertos.</span><span class="sxs-lookup"><span data-stu-id="69be5-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="69be5-107">Embora os administradores de conhecimento controlem as configurações para impedir que os tópicos são descobertos, os gerentes de conhecimento e outras partes interessadas precisam saber como isso é feito para que eles possam trabalhar de forma colaborativa.</span><span class="sxs-lookup"><span data-stu-id="69be5-107">While knowledge admins control the settings to prevent topics from being discovered, knowledge managers and other stakeholders need to know how it is done so that they can work collaboratively.</span></span>

> [!Important] 
> <span data-ttu-id="69be5-108">Este artigo descreve maneiras de impedir que os tópicos sejam identificados por meio da IA ou exibidos em seu ambiente como uma proteção de segurança adicional.</span><span class="sxs-lookup"><span data-stu-id="69be5-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="69be5-109">É importante observar que, em Tópicos do Viva, os usuários não têm permissão para exibir nada em um tópico que não tenham permissão para acessar por meio de permissões do Office 365.</span><span class="sxs-lookup"><span data-stu-id="69be5-109">It is important to note that in Viva Topics, users aren't allowed to view anything in a topic that they aren't allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="69be5-110">Mesmo que um usuário seja capaz de exibir um tópico, seus arquivos, sites e páginas que eles não têm permissões do Office 365 para exibir não estarão visíveis para eles.</span><span class="sxs-lookup"><span data-stu-id="69be5-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="69be5-111">Garantir que as permissões para arquivos confidenciais sejam definidas corretamente devem ser sua proteção de segurança principal.</span><span class="sxs-lookup"><span data-stu-id="69be5-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="69be5-112">Impedir que os tópicos sejam identificados</span><span class="sxs-lookup"><span data-stu-id="69be5-112">Prevent topics from being identified</span></span>

<span data-ttu-id="69be5-113">O administrador de conhecimento pode restringir o acesso a tópicos específicos impedindo-os de serem encontrados na indexação inicial.</span><span class="sxs-lookup"><span data-stu-id="69be5-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="69be5-114">Há duas maneiras de fazer essa tarefa nas configurações de administrador do Viva Topics no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="69be5-114">There are two ways to do this task in the Viva Topics admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="69be5-115">[Selecione sites do SharePoint a serem excluídos da](./topic-experiences-discovery.md#select-sharepoint-topic-sources)descoberta de tópicos : você pode usar essa configuração para impedir que sites específicos do SharePoint seja rastreado para tópicos.</span><span class="sxs-lookup"><span data-stu-id="69be5-115">[Select SharePoint sites to exclude from topic discovery](./topic-experiences-discovery.md#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="69be5-116">[Excluir tópicos pelo nome:](./topic-experiences-discovery.md#exclude-topics-by-name)os administradores podem usar essa configuração para impedir que tópicos específicos sejam descobertos pelo nome.</span><span class="sxs-lookup"><span data-stu-id="69be5-116">[Exclude topics by name](./topic-experiences-discovery.md#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="69be5-117">Nas configurações de administrador do Viva Topics, um administrador pode carregar uma lista de tópicos a serem excluídos em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="69be5-117">In the Viva Topics admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="69be5-118">Você pode excluir tópicos que tenham combinações exatas ou parciais de um nome de tópico.</span><span class="sxs-lookup"><span data-stu-id="69be5-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="69be5-119">Impedir que os tópicos são exibidos por usuários específicos</span><span class="sxs-lookup"><span data-stu-id="69be5-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="69be5-120">Os administradores de conhecimento também podem [selecionar quem pode exibir tópicos em sua organização.](./topic-experiences-knowledge-rules.md)</span><span class="sxs-lookup"><span data-stu-id="69be5-120">Knowledge admins can also [select who can view topics in your organization](./topic-experiences-knowledge-rules.md).</span></span> <span data-ttu-id="69be5-121">Essa configuração permite selecionar quais usuários licenciados podem exibir todos os tópicos.</span><span class="sxs-lookup"><span data-stu-id="69be5-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="69be5-122">Por exemplo, em um ambiente piloto, talvez você queira permitir que um pequeno grupo de usuários possa exibir tópicos.</span><span class="sxs-lookup"><span data-stu-id="69be5-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="69be5-123">Remover tópicos de serem exibidos</span><span class="sxs-lookup"><span data-stu-id="69be5-123">Remove topics from being viewed</span></span>

<span data-ttu-id="69be5-124">Os gerentes de conhecimento podem [optar por remover tópicos](./manage-topics.md) para que os usuários não possam mais vê-los.</span><span class="sxs-lookup"><span data-stu-id="69be5-124">Knowledge managers can choose to [remove topics](./manage-topics.md) so that users can no longer see them.</span></span> <span data-ttu-id="69be5-125">Na página **Gerenciar tópicos** na Central de Tópicos, os gerentes de conhecimento podem optar por rejeitar tópicos específicos para impedir que eles são exibidos.</span><span class="sxs-lookup"><span data-stu-id="69be5-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="69be5-126">Os tópicos podem ser removidos independentemente se eles estão em um estado sugerido ou confirmado.</span><span class="sxs-lookup"><span data-stu-id="69be5-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="69be5-127">Os tópicos removidos podem ser adicionados posteriormente como tópicos exibiveis, se necessário.</span><span class="sxs-lookup"><span data-stu-id="69be5-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="69be5-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="69be5-128">See also</span></span>



