---
title: Office 365 ATP links seguros para equipes, safelinks, links seguros, bloquear links mal-intencionados, Office 365 ATP, links seguros de equipes, impedir que os usuários cliquem em links defeituosos, links mal-intencionados
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Agora o Microsoft Teams terá acesso a links seguros no momento do clique. Se você estiver usando chats 1-em-1, entre grupos ou em canais e guias, se você tiver uma assinatura do Office 365 ATP, terá a capacidade de habilitar e usar esse recurso de segurança.
ms.openlocfilehash: ba7ef2ae63b788ec94fbbb15c3c00312177a59d5
ms.sourcegitcommit: cf07dfccec476ac2526a6171ec6b6365686f759f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341563"
---
<!--06/21/2019-->

# <a name="office-365-safe-links-in-teams"></a><span data-ttu-id="55844-104">Links seguros do Office 365 no Teams</span><span class="sxs-lookup"><span data-stu-id="55844-104">Office 365 Safe Links in Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="55844-105">Este recurso está em **Visualização pública** para clientes no programa de adoção de tecnologia do Microsoft Teams (toque) a partir de 28 de fevereiro de 2020.</span><span class="sxs-lookup"><span data-stu-id="55844-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="55844-106">Esta nota será removida do artigo quando links seguros para o Microsoft Teams estiver mais amplamente disponível.</span><span class="sxs-lookup"><span data-stu-id="55844-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="55844-107">O Microsoft Teams, um aplicativo baseado em nuvem do Office 365 para gerenciar seu trabalho, já usa anexos seguros (para o Office 365), mas agora terá acesso a links seguros no momento do clique.</span><span class="sxs-lookup"><span data-stu-id="55844-107">Microsoft Teams, an Office 365 Cloud-based application for managing your work, already uses safe attachments (for Office 365), but it will now have access to safe links at the time of your click.</span></span> <span data-ttu-id="55844-108">Se você estiver usando chats 1-em-1, entre grupos ou em canais e guias, se você tiver uma assinatura do Office 365 ATP, terá a capacidade de habilitar e usar essa medida de segurança.</span><span class="sxs-lookup"><span data-stu-id="55844-108">Whether you’re using chats 1-on-1 Chats, between Groups, or in Channels, and Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span>

<span data-ttu-id="55844-109">Veja como funciona:</span><span class="sxs-lookup"><span data-stu-id="55844-109">Here’s how it works:</span></span> 

1. <span data-ttu-id="55844-110">Quando você iniciar o aplicativo Teams, o Office 365 verificará se o usuário pertence a uma organização que tem o Office 365 ATP e que o usuário faz parte de uma política de links seguros ativa com sua proteção habilitada para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="55844-110">When you start the Teams application, Office 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="55844-111">Se os itens acima forem verdadeiros, as URLs serão validadas no momento do clique em chats, chats de grupo, canais e em guias para esse usuário.</span><span class="sxs-lookup"><span data-stu-id="55844-111">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>
 
## <a name="what-will-users-experience"></a><span data-ttu-id="55844-112">O que os usuários irão experimentar?</span><span class="sxs-lookup"><span data-stu-id="55844-112">What will users experience?</span></span> 

<span data-ttu-id="55844-113">Todos os usuários protegidos terão essa experiência com URLs perigosas:</span><span class="sxs-lookup"><span data-stu-id="55844-113">All protected users will have this experience with hazardous URLs:</span></span> 

- <span data-ttu-id="55844-114">Se o link tiver sido clicado de uma conversa de equipes, de um chat de grupo ou de canais, uma página será renderizada no navegador padrão.</span><span class="sxs-lookup"><span data-stu-id="55844-114">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="55844-115">Se o link tiver sido clicado em uma guia fixada, a página aparecerá na GUI do Microsoft Teams dentro dessa guia e a opção de abrir no navegador será desabilitada para fins de segurança.</span><span class="sxs-lookup"><span data-stu-id="55844-115">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="55844-116">Este usuário será impedido de prosseguir para o site da URL.</span><span class="sxs-lookup"><span data-stu-id="55844-116">This user will be blocked from proceeding to the URL’s site.</span></span>

<span data-ttu-id="55844-117">Se o usuário que enviou o link não estiver protegido pelo Office 365 ATP, ele ou ela estará livre para clicar na URL em seu computador e resolver o problema.</span><span class="sxs-lookup"><span data-stu-id="55844-117">If the user who sent the link isn’t protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="55844-118">Isso torna mais importante para os administradores do Office 365 saber quem estão seus usuários protegidos e se devem estar.</span><span class="sxs-lookup"><span data-stu-id="55844-118">This makes it doubly important for Office 365 Administrators to be aware of who their protected users are and should be.</span></span>

![Uma página de links seguros para o Teams relatando um link mal-intencionado e bloqueando o trânsito para a página.](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="55844-120">Clicar no *botão voltar* nesta página no Microsoft Teams irá fechá-lo (ou pode resultar em uma página em branco que os usuários possam fechar).</span><span class="sxs-lookup"><span data-stu-id="55844-120">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="55844-121">No entanto, clicar no link novamente resultará na reavaliação da reputação do site para que essa página reapareça.</span><span class="sxs-lookup"><span data-stu-id="55844-121">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
><span data-ttu-id="55844-122">Alguns administradores do Office 365 habilitarão a mensagem de **continuar assim mesmo** na página de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="55844-122">Some Office 365 Admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="55844-123">No entanto, se o recurso links seguros medir a reputação de um site e encontrá-lo, nenhum outro clique deve ser realizada.</span><span class="sxs-lookup"><span data-stu-id="55844-123">However, if safe links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="55844-124">Não é recomendável que os usuários ignorem medidas de segurança.</span><span class="sxs-lookup"><span data-stu-id="55844-124">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="55844-125">Considere isso em suas considerações antes de habilitar a continuação de qualquer modo.</span><span class="sxs-lookup"><span data-stu-id="55844-125">Please weigh this into your considerations before enabling Continue Anyway.</span></span> 

