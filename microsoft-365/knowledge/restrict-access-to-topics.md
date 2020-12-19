---
title: Restringir o acesso aos tópicos
description: Como excluir tópicos para impedir que eles sejam descobertos.
author: efrene
ms.author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: b23d01585d9282132d9e55c74bb22bcdc6ca314a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698784"
---
# <a name="restrict-access-to-topics-in-topic-experiences"></a><span data-ttu-id="c094f-103">Restringir o acesso a tópicos em experiências de tópico</span><span class="sxs-lookup"><span data-stu-id="c094f-103">Restrict access to topics in Topic Experiences</span></span>

<span data-ttu-id="c094f-104">No tópico experiências, os participantes da sua organização podem querer garantir que tópicos específicos não sejam descobertos e expostos aos seus usuários licenciados.</span><span class="sxs-lookup"><span data-stu-id="c094f-104">In Topic Experiences, stakeholders in your organization may want to make sure that specific topics are not discovered and exposed to your licensed users.</span></span> <span data-ttu-id="c094f-105">Por exemplo, você pode estar trabalhando em um projeto que não deseja expor nenhuma informação sobre o.</span><span class="sxs-lookup"><span data-stu-id="c094f-105">For example, you may be working on a project that you don't want to expose any information about yet.</span></span> <span data-ttu-id="c094f-106">Embora as permissões do Office 365 em sites, os arquivos e outros recursos impeçam que o tópico que os usuários exibam informações confidenciais nos tópicos, há garantias adicionais que impedem que tópicos específicos sejam descobertos.</span><span class="sxs-lookup"><span data-stu-id="c094f-106">While Office 365 permissions on sites, files and other resources will prevent Topic Experiences users from viewing sensitive information in topics, there are additional safeguards to prevent specific topics from ever being discovered.</span></span>

<span data-ttu-id="c094f-107">Embora os administradores de conhecimento controlem as configurações de rede de conhecimento para evitar que os tópicos sejam descobertos, os gerentes de conhecimento e outros participantes precisam saber como isso é feito para que eles possam trabalhar de forma colaborativa.</span><span class="sxs-lookup"><span data-stu-id="c094f-107">While knowledge admins control the knowledge network settings to prevent topics from being discovered, knowledge managers and other stakeholders need to be know how this is done so that they can work collaboratively on this.</span></span>

> [!Important] 
> <span data-ttu-id="c094f-108">Este artigo descreve maneiras de impedir que os tópicos sejam identificados por meio do AI ou exibidos no seu ambiente como uma maior proteção de segurança.</span><span class="sxs-lookup"><span data-stu-id="c094f-108">This article describes ways to prevent topics from being identified through AI or viewed in your environment as an additional security safeguard.</span></span> <span data-ttu-id="c094f-109">É importante observar que, em experiências de tópico, os usuários não têm permissão para exibir nada em um tópico que eles não têm permissão para acessar através de permissões do Office 365.</span><span class="sxs-lookup"><span data-stu-id="c094f-109">It is important to note that in Topic Experiences, users are not allowed to view anything in a topic that they are not allowed to access through Office 365 permissions.</span></span> <span data-ttu-id="c094f-110">Mesmo que um usuário possa exibir um tópico, seus arquivos, sites e páginas que não têm as permissões do Office 365 para exibir não serão visíveis para eles.</span><span class="sxs-lookup"><span data-stu-id="c094f-110">Even if a users is able to view a topic, its files, sites, and pages they do not have Office 365 permissions to view will not be visible to them.</span></span> <span data-ttu-id="c094f-111">Certificar-se de que as permissões para arquivos confidenciais estão definidas corretamente deve ser a proteção de segurança principal.</span><span class="sxs-lookup"><span data-stu-id="c094f-111">Making sure that permissions to sensitive files are correctly set should be your primary security safeguard.</span></span>

## <a name="prevent-topics-from-being-identified"></a><span data-ttu-id="c094f-112">Impedir a identificação de tópicos</span><span class="sxs-lookup"><span data-stu-id="c094f-112">Prevent topics from being identified</span></span>

<span data-ttu-id="c094f-113">O administrador de conhecimento pode restringir o acesso a tópicos específicos, impedindo que eles sejam encontrados na indexação inicial.</span><span class="sxs-lookup"><span data-stu-id="c094f-113">Knowledge admin can restrict access to specific topics by preventing them from being found in initial indexing.</span></span> <span data-ttu-id="c094f-114">Há duas maneiras de fazer isso nas configurações de administração de rede de conhecimento no centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c094f-114">There are two ways to do this in the Knowledge Network admin settings in the Microsoft 365 admin center.</span></span>
 
- <span data-ttu-id="c094f-115">[Selecione sites do SharePoint a serem excluídos da descoberta de tópicos](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): você pode usar essa configuração para impedir que sites específicos do SharePoint sejam rastreados para tópicos.</span><span class="sxs-lookup"><span data-stu-id="c094f-115">[Select SharePoint sites to exclude from topic discovery](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#select-sharepoint-topic-sources): You can use this setting to prevent specific SharePoint sites from being crawled for topics.</span></span>
- <span data-ttu-id="c094f-116">[Excluir tópicos por nome](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): os administradores podem usar essa configuração para impedir que tópicos específicos sejam descobertos pelo nome.</span><span class="sxs-lookup"><span data-stu-id="c094f-116">[Exclude topics by name](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery#exclude-topics-by-name): Admins can use this setting to prevent specific topics from being discovered by name.</span></span> <span data-ttu-id="c094f-117">Nas configurações de administração da rede de conhecimento, um administrador pode carregar uma lista de tópicos a serem excluídos em um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="c094f-117">In the Knowledge Network admin settings, an admin can upload a list of topics to be excluded in a CSV file.</span></span> <span data-ttu-id="c094f-118">Você pode excluir os tópicos que têm correspondências exatas ou parciais de um nome de tópico.</span><span class="sxs-lookup"><span data-stu-id="c094f-118">You can exclude topics that have exact or partial matches of a topic name.</span></span>

## <a name="prevent-topics-from-being-viewed-by-specific-users"></a><span data-ttu-id="c094f-119">Impedir que os tópicos sejam exibidos por usuários específicos</span><span class="sxs-lookup"><span data-stu-id="c094f-119">Prevent topics from being viewed by specific users</span></span>

<span data-ttu-id="c094f-120">Os administradores de conhecimento também podem [selecionar quem pode exibir tópicos em sua organização](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span><span class="sxs-lookup"><span data-stu-id="c094f-120">Knowledge admins can also [select who can view topics in your organization](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules).</span></span> <span data-ttu-id="c094f-121">Essa configuração permite que você Selecione quais usuários licenciados podem exibir todos os tópicos.</span><span class="sxs-lookup"><span data-stu-id="c094f-121">This setting lets you select which licensed users can view all topics.</span></span> <span data-ttu-id="c094f-122">Por exemplo, em um ambiente piloto, talvez você queira permitir que apenas um pequeno grupo de usuários possa exibir tópicos.</span><span class="sxs-lookup"><span data-stu-id="c094f-122">For example, in a pilot environment, you may want to only allow a small group of users to be able to view topics.</span></span>

## <a name="remove-topics-from-being-viewed"></a><span data-ttu-id="c094f-123">Remover tópicos da exibição</span><span class="sxs-lookup"><span data-stu-id="c094f-123">Remove topics from being viewed</span></span>

<span data-ttu-id="c094f-124">Os gerentes de conhecimento podem optar por [Remover tópicos](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) para que os usuários não possam mais vê-los.</span><span class="sxs-lookup"><span data-stu-id="c094f-124">Knowledge managers can choose to [remove topics](https://docs.microsoft.com/microsoft-365/knowledge/manage-topics) so that users can no longer see them.</span></span> <span data-ttu-id="c094f-125">Na página **gerenciar tópicos** no **Centro** de tópicos, os gerentes de conhecimento podem optar por rejeitar tópicos específicos para impedir que eles sejam exibidos.</span><span class="sxs-lookup"><span data-stu-id="c094f-125">On the **Manage topics** page in the **Topic center**, knowledge managers can choose to reject specific topics to prevent them from being viewed.</span></span> <span data-ttu-id="c094f-126">Os tópicos podem ser removidos independentemente de estarem em um estado sugerido ou confirmado.</span><span class="sxs-lookup"><span data-stu-id="c094f-126">Topics can be removed regardless if they are in a suggested or confirmed state.</span></span>

<span data-ttu-id="c094f-127">Os tópicos removidos posteriormente podem ser adicionados novamente como tópicos exibíveis, se necessário.</span><span class="sxs-lookup"><span data-stu-id="c094f-127">Removed topics can later be added back as viewable topics if needed.</span></span> 


## <a name="see-also"></a><span data-ttu-id="c094f-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="c094f-128">See also</span></span>



  






