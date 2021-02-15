---
title: Restringir o acesso a tópicos nos tópicos do Microsoft Viva
description: Como excluir tópicos para impedir que eles são descobertos.
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
- m365initiative-topics
localization_priority: None
ms.openlocfilehash: 6b3d2a4b6cbfc67623cea58b73681b7af7cc4889
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107153"
---
# <a name="restrict-access-to-topics-in-microsoft-viva-topics"></a><span data-ttu-id="b6d26-103">Restringir o acesso a tópicos nos tópicos do Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="b6d26-103">Restrict access to topics in Microsoft Viva Topics</span></span>

<span data-ttu-id="b6d26-104">No Microsoft Viva, os participantes em sua organização podem querer garantir que tópicos específicos não sejam descobertos e expostos aos usuários licenciados.</span><span class="sxs-lookup"><span data-stu-id="b6d26-104">In Microsoft Viva, stakeholders in your organization may want to make sure that specific topics aren't discovered and exposed to your licensed users.</span></span> <span data-ttu-id="b6d26-105">Por exemplo, você pode estar trabalhando em um projeto sobre o que ainda não deseja expor.</span><span class="sxs-lookup"><span data-stu-id="b6d26-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="b6d26-106">Embora as permissões do Office 365 em sites, arquivos e outros recursos impeçam que os usuários de Experiências de Tópicos vejam informações confidenciais em tópicos, há proteções adicionais para impedir que tópicos específicos sejam descobertos.</span><span class="sxs-lookup"><span data-stu-id="b6d26-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="b6d26-107">Embora os administradores de conhecimento controlem as configurações da rede de conhecimento para impedir que os tópicos são descobertos, os gerentes de conhecimento e outros participantes precisam saber como isso é feito para que possam trabalhar de forma colaborativa.</span><span class="sxs-lookup"><span data-stu-id="b6d26-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to know how it is done so that they can work collaboratively.</span></span>

> [!Important] 
> <span data-ttu-id="b6d26-108">Este artigo descreve maneiras de impedir que os tópicos sejam identificados por meio de IA ou exibidos em seu ambiente como uma proteção de segurança adicional.</span><span class="sxs-lookup"><span data-stu-id="b6d26-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="b6d26-109">É importante observar que, nos Tópicos do Viva, os usuários não têm permissão para exibir nada em um tópico que eles não têm permissão para acessar por meio das permissões do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b6d26-109">It is important to note that in Viva Topics, users aren't allowed to view anything in a topic that they aren't allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="b6d26-110">Mesmo que um usuário possa exibir um tópico, seus arquivos, sites e páginas que não têm permissões do Office 365 para exibir não estarão visíveis para eles.</span><span class="sxs-lookup"><span data-stu-id="b6d26-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="b6d26-111">Garantir que as permissões para arquivos confidenciais sejam definidas corretamente deve ser sua proteção de segurança principal.</span><span class="sxs-lookup"><span data-stu-id="b6d26-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="b6d26-112">Impedir que tópicos sejam identificados</span><span class="sxs-lookup"><span data-stu-id="b6d26-112">Prevent topics from being identified</span></span>

<span data-ttu-id="b6d26-113">O administrador de conhecimento pode restringir o acesso a tópicos específicos impedindo que eles são encontrados na indexação inicial.</span><span class="sxs-lookup"><span data-stu-id="b6d26-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="b6d26-114">Há duas maneiras de fazer essa tarefa nas configurações de administrador da Rede de Conhecimento no Centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b6d26-114">There are two ways to do this task in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="b6d26-115">[Selecione sites do SharePoint a serem excluídos da](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources)descoberta de tópicos: você pode usar essa configuração para impedir que sites específicos do SharePoint seja rastreados para tópicos.</span><span class="sxs-lookup"><span data-stu-id="b6d26-115">[Select SharePoint sites to exclude from topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="b6d26-116">[Excluir tópicos por nome:](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name)os administradores podem usar essa configuração para impedir que tópicos específicos sejam descobertos por nome.</span><span class="sxs-lookup"><span data-stu-id="b6d26-116">[Exclude topics by name](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="b6d26-117">Nas configurações de administração da Rede de Conhecimento, um administrador pode carregar uma lista de tópicos a serem excluídos em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="b6d26-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="b6d26-118">Você pode excluir tópicos que tenham uma combinação exata ou parcial de um nome de tópico.</span><span class="sxs-lookup"><span data-stu-id="b6d26-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="b6d26-119">Impedir que tópicos são exibidos por usuários específicos</span><span class="sxs-lookup"><span data-stu-id="b6d26-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="b6d26-120">Os administradores de conhecimento [também podem selecionar quem pode exibir tópicos em sua organização.](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)</span><span class="sxs-lookup"><span data-stu-id="b6d26-120">Knowledge admins can also [select who can view topics in your organization](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span></span> <span data-ttu-id="b6d26-121">Essa configuração permite selecionar quais usuários licenciados podem exibir todos os tópicos.</span><span class="sxs-lookup"><span data-stu-id="b6d26-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="b6d26-122">Por exemplo, em um ambiente piloto, talvez você queira permitir que apenas um pequeno grupo de usuários seja capaz de exibir tópicos.</span><span class="sxs-lookup"><span data-stu-id="b6d26-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="b6d26-123">Remover tópicos da exibição</span><span class="sxs-lookup"><span data-stu-id="b6d26-123">Remove topics from being viewed</span></span>

<span data-ttu-id="b6d26-124">Os gerentes de conhecimento [podem optar por remover tópicos](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) para que os usuários não possam mais vê-los.</span><span class="sxs-lookup"><span data-stu-id="b6d26-124">Knowledge managers can choose to [remove topics](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) so that users can no longer see them.</span></span> <span data-ttu-id="b6d26-125">Na página Gerenciar tópicos no Centro de **Tópicos,** os gerentes de conhecimento podem optar por rejeitar tópicos específicos para impedir que eles seja exibidos.</span><span class="sxs-lookup"><span data-stu-id="b6d26-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="b6d26-126">Os tópicos podem ser removidos independentemente de eles estar em um estado sugerido ou confirmado.</span><span class="sxs-lookup"><span data-stu-id="b6d26-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="b6d26-127">Os tópicos removidos podem ser adicionados posteriormente como tópicos que podem ser visualizados, se necessário.</span><span class="sxs-lookup"><span data-stu-id="b6d26-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="b6d26-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="b6d26-128">See also</span></span>



  






