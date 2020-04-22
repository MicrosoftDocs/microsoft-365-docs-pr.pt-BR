---
title: Saiba mais sobre as barreiras de informação
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Use as barreiras de informação para garantir a conformidade de comunicação usando o Microsoft Teams em sua organização.
ms.openlocfilehash: 344c2b6999a8fd890358a25b39ef3a37abc9ef58
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636099"
---
# <a name="information-barriers"></a><span data-ttu-id="c3092-103">Barreiras de informações</span><span class="sxs-lookup"><span data-stu-id="c3092-103">Information barriers</span></span>

## <a name="overview"></a><span data-ttu-id="c3092-104">Visão geral</span><span class="sxs-lookup"><span data-stu-id="c3092-104">Overview</span></span>

<!--

# Information barriers (click-through test)

## Overview



 [![Click-Through for Information Barriers](./media/information-barriers/clickthrough-information-barriers-thumbnail.png)](./media/information-barriers/clickthrough-information-barriers.pdf)


Click through an overview of Information Barriers: [PDF](./media/information-barriers/clickthrough-information-barriers.pdf) | [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/Click-Through-Test/microsoft-365/compliance/media/information-barriers/Clickthrough-Information-Barriers.pptx)

OLD: Move comment field here

 [![Click-Through for Information Barriers](./media/information-barriers/Clickthrough_InformationBarriers_Thumbnail.png)](./media/information-barriers/Clickthrough_InformationBarriers.pdf)

For the PowerPoint slide of this Click-Through, click [here](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/raw/Click-Through-Test/microsoft-365/compliance/media/information-barriers/InfoBarriersExample.pptx).

>[!Tip]
>Try this new [Click-Through on information barriers](media/information-barriers/Clickthrough_InformationBarriers.pdf) for a quick overview of the essential facts.
>

--> 


<span data-ttu-id="c3092-105">Os serviços de nuvem da Microsoft incluem recursos avançados de comunicação e colaboração.</span><span class="sxs-lookup"><span data-stu-id="c3092-105">Microsoft cloud services include powerful communication and collaboration capabilities.</span></span> <span data-ttu-id="c3092-106">Mas suponha que você deseja restringir as comunicações entre dois grupos para evitar um conflito de interesse de ocorrer em sua organização.</span><span class="sxs-lookup"><span data-stu-id="c3092-106">But suppose that you want to restrict communications between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="c3092-107">Ou, talvez você queira restringir as comunicações entre determinadas pessoas dentro da sua organização para proteger informações internas.</span><span class="sxs-lookup"><span data-stu-id="c3092-107">Or, perhaps you want to restrict communications between certain people inside your organization in order to safeguard internal information.</span></span> <span data-ttu-id="c3092-108">A Microsoft 365 permite a comunicação e a colaboração entre grupos e organizações, portanto, há uma maneira de restringir as comunicações entre grupos específicos de usuários quando necessário?</span><span class="sxs-lookup"><span data-stu-id="c3092-108">Microsoft 365 enables communication and collaboration across groups and organizations, so is there a way to restrict communications among specific groups of users when necessary?</span></span> <span data-ttu-id="c3092-109">Com as barreiras de informação, você pode!</span><span class="sxs-lookup"><span data-stu-id="c3092-109">With information barriers, you can!</span></span> 

<span data-ttu-id="c3092-110">As barreiras de informação estão sendo lançadas agora, começando com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c3092-110">Information barriers are rolling out now, beginning with Microsoft Teams.</span></span> <span data-ttu-id="c3092-111">Supondo que sua [assinatura](#required-licenses-and-permissions) inclua barreiras de informação, um administrador de conformidade ou barreiras de informações pode definir políticas para permitir ou impedir a comunicação entre grupos de usuários no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c3092-111">Assuming your [subscription](#required-licenses-and-permissions) includes information barriers, a compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="c3092-112">As políticas de barreira de informações podem ser usadas para situações como estas:</span><span class="sxs-lookup"><span data-stu-id="c3092-112">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="c3092-113">O usuário no grupo de dia dos traders não deve se comunicar com a equipe de marketing</span><span class="sxs-lookup"><span data-stu-id="c3092-113">User in the day trader group should not communicate with the marketing team</span></span>
- <span data-ttu-id="c3092-114">O pessoal financeiro que trabalha em informações confidenciais da empresa não deve se comunicar com determinados grupos da organização</span><span class="sxs-lookup"><span data-stu-id="c3092-114">Finance personnel working on confidential company information should not communicate with certain groups within their organization</span></span>
- <span data-ttu-id="c3092-115">Uma equipe interna com o material de segredo comercial não deve ligar ou bater papo com pessoas de determinados grupos da organização</span><span class="sxs-lookup"><span data-stu-id="c3092-115">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="c3092-116">Uma equipe de pesquisa deve chamar ou bater papo online apenas com uma equipe de desenvolvimento de produtos</span><span class="sxs-lookup"><span data-stu-id="c3092-116">A research team should only call or chat online with a product development team</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3092-117">As barreiras de informação ***só dão suporte*** a restrições de duas vias.</span><span class="sxs-lookup"><span data-stu-id="c3092-117">Information barriers ***only supports*** two way restrictions.</span></span> <span data-ttu-id="c3092-118">Restrições unidirecionais, como marketing, podem se comunicar com o dia dos comerciantes, mas o dia dos comerciantes não podem se comunicar com o marketing ***não é suportado***.</span><span class="sxs-lookup"><span data-stu-id="c3092-118">One way restrictions, such as marketing can communicate with day traders, but day traders cannot communicate with marketing ***is not supported***.</span></span>

<span data-ttu-id="c3092-119">Para todos esses cenários de exemplo (e mais), as políticas de barreira de informações podem ser definidas para impedir ou permitir comunicações no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c3092-119">For all of these example scenarios (and more), information barrier policies can be defined to prevent or allow communications in Microsoft Teams.</span></span> <span data-ttu-id="c3092-120">Essas políticas podem impedir que as pessoas chamem ou chat com as que elas não deveriam ou permitir que as pessoas se comuniquem somente com grupos específicos no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c3092-120">Such policies can prevent people from calling or chatting with those they shouldn't, or enable people to communicate only with specific groups in Microsoft Teams.</span></span> <span data-ttu-id="c3092-121">Com as políticas de barreira de informações em vigor, sempre que os usuários que estão cobertos por essas políticas tentarem se comunicar com outras pessoas no Microsoft Teams, as verificações são realizadas para impedir (ou permitir) a comunicação (conforme definido pelas políticas de barreira de informações).</span><span class="sxs-lookup"><span data-stu-id="c3092-121">With information barrier policies in effect, whenever users who are covered by those policies attempt to communicate with others in Microsoft Teams, checks are done to prevent (or allow) communication (as defined by information barrier policies).</span></span> <span data-ttu-id="c3092-122">Para saber mais sobre a experiência do usuário com barreiras de informações, confira [barreiras de informações no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span><span class="sxs-lookup"><span data-stu-id="c3092-122">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c3092-123">Atualmente, as barreiras de informação não se aplicam às comunicações por email ou ao compartilhamento de arquivos por meio do SharePoint Online ou do OneDrive.</span><span class="sxs-lookup"><span data-stu-id="c3092-123">Currently, information barriers do not apply to email communications or to file sharing through SharePoint Online or OneDrive.</span></span> <span data-ttu-id="c3092-124">Além disso, as barreiras de informação são independentes dos [limites de conformidade](set-up-compliance-boundaries.md).</span><span class="sxs-lookup"><span data-stu-id="c3092-124">In addition, information barriers are independent from [compliance boundaries](set-up-compliance-boundaries.md).</span></span><p><span data-ttu-id="c3092-125">Antes de definir e aplicar as políticas de barreira de informações, certifique-se de que sua organização não tenha [diretivas de catálogo de endereços do Exchange](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) em vigor.</span><span class="sxs-lookup"><span data-stu-id="c3092-125">Before you define and apply information barrier policies, make sure your organization does not have [Exchange address book policies](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) in effect.</span></span> <span data-ttu-id="c3092-126">(As barreiras de informação são baseadas nas políticas do catálogo de endereços.)</span><span class="sxs-lookup"><span data-stu-id="c3092-126">(Information barriers are based on address book policies.)</span></span> 

## <a name="what-happens-with-information-barriers"></a><span data-ttu-id="c3092-127">O que acontece com as barreiras de informação</span><span class="sxs-lookup"><span data-stu-id="c3092-127">What happens with information barriers</span></span>

<span data-ttu-id="c3092-128">Quando as políticas de barreira de informações estão vigentes, as pessoas que não devem se comunicar com outros usuários específicos não poderão localizar, selecionar, bater papo ou chamar esses usuários.</span><span class="sxs-lookup"><span data-stu-id="c3092-128">When information barrier policies are in place, people who should not communicate with other specific users won't be able to find, select, chat, or call those users.</span></span> <span data-ttu-id="c3092-129">Com as barreiras de informação, os cheques estão vigentes para impedir a comunicação não autorizada.</span><span class="sxs-lookup"><span data-stu-id="c3092-129">With information barriers, checks are in place to prevent unauthorized communication.</span></span>

<span data-ttu-id="c3092-130">Inicialmente, as barreiras de informações se aplicam apenas a chat e canais do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c3092-130">Initially, information barriers apply to Microsoft Teams chats and channels only.</span></span> <span data-ttu-id="c3092-131">No Microsoft Teams, as políticas de barreira de informações determinam e impedem os seguintes tipos de comunicações não autorizadas:</span><span class="sxs-lookup"><span data-stu-id="c3092-131">In Microsoft Teams, information barrier policies determine and prevent the following kinds of unauthorized communications:</span></span>
- <span data-ttu-id="c3092-132">Procurando um usuário</span><span class="sxs-lookup"><span data-stu-id="c3092-132">Searching for a user</span></span>
- <span data-ttu-id="c3092-133">Adicionar um membro a uma equipe</span><span class="sxs-lookup"><span data-stu-id="c3092-133">Adding a member to a team</span></span>
- <span data-ttu-id="c3092-134">Iniciar uma sessão de chat com alguém</span><span class="sxs-lookup"><span data-stu-id="c3092-134">Starting a chat session with someone</span></span>
- <span data-ttu-id="c3092-135">Iniciar um chat de grupo</span><span class="sxs-lookup"><span data-stu-id="c3092-135">Starting a group chat</span></span>
- <span data-ttu-id="c3092-136">Convidar alguém para participar de uma reunião</span><span class="sxs-lookup"><span data-stu-id="c3092-136">Inviting someone to join a meeting</span></span>
- <span data-ttu-id="c3092-137">Compartilhar uma tela</span><span class="sxs-lookup"><span data-stu-id="c3092-137">Sharing a screen</span></span>
- <span data-ttu-id="c3092-138">Fazendo uma chamada</span><span class="sxs-lookup"><span data-stu-id="c3092-138">Placing a call</span></span> 

<span data-ttu-id="c3092-139">Se as pessoas envolvidas estiverem incluídas em uma política de barreira de informações para impedir a atividade, elas não poderão continuar.</span><span class="sxs-lookup"><span data-stu-id="c3092-139">If the people involved are included in an information barrier policy to prevent the activity, they will not be able to proceed.</span></span> <span data-ttu-id="c3092-140">Além disso, possivelmente, todos incluídos em uma política de barreira de informações podem ser impedidos de se comunicar com outras pessoas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c3092-140">In addition, potentially, everyone included in an information barrier policy can be blocked from communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="c3092-141">Quando as pessoas afetadas por políticas de barreira de informações fazem parte do mesmo bate-papo de grupo ou equipe, elas podem ser removidas dessas sessões de chat e a comunicação adicional com o grupo pode não ser permitida.</span><span class="sxs-lookup"><span data-stu-id="c3092-141">When people affected by information barrier policies are part of the same team or group chat, they might be removed from those chat sessions and further communication with the group might not be allowed.</span></span>

<span data-ttu-id="c3092-142">Para saber mais sobre a experiência do usuário com barreiras de informações, confira [barreiras de informações no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span><span class="sxs-lookup"><span data-stu-id="c3092-142">To learn more about the user experience with information barriers, see [information barriers in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="c3092-143">Licenças e permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="c3092-143">Required licenses and permissions</span></span>

<span data-ttu-id="c3092-144">As barreiras de informação estão sendo lançadas agora e estão incluídas em assinaturas, como:</span><span class="sxs-lookup"><span data-stu-id="c3092-144">Information barriers are rolling out now, and are included in subscriptions, such as:</span></span>

- <span data-ttu-id="c3092-145">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c3092-145">Microsoft 365 E5</span></span>
- <span data-ttu-id="c3092-146">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="c3092-146">Office 365 E5</span></span>
- <span data-ttu-id="c3092-147">Conformidade Avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="c3092-147">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="c3092-148">Conformidade e proteção de informações do Microsoft 365 e5</span><span class="sxs-lookup"><span data-stu-id="c3092-148">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="c3092-149">Para obter mais detalhes, consulte [soluções de conformidade](https://products.office.com/business/security-and-compliance/compliance-solutions).</span><span class="sxs-lookup"><span data-stu-id="c3092-149">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

<span data-ttu-id="c3092-150">Para [definir ou editar as políticas de barreira de informações](information-barriers-policies.md), você deve ter uma das seguintes funções:</span><span class="sxs-lookup"><span data-stu-id="c3092-150">To [define or edit information barrier policies](information-barriers-policies.md), you must be assigned one of the following roles:</span></span>

- <span data-ttu-id="c3092-151">Administrador global do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c3092-151">Microsoft 365 global administrator</span></span>
- <span data-ttu-id="c3092-152">Administrador global do Office 365</span><span class="sxs-lookup"><span data-stu-id="c3092-152">Office 365 global administrator</span></span>
- <span data-ttu-id="c3092-153">Administrador de conformidade</span><span class="sxs-lookup"><span data-stu-id="c3092-153">Compliance administrator</span></span>
- <span data-ttu-id="c3092-154">Gerenciamento de conformidade IB (esta é uma nova função!)</span><span class="sxs-lookup"><span data-stu-id="c3092-154">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="c3092-155">(Para saber mais sobre funções e permissões, confira [permissões no centro de conformidade & segurança do Office 365](../security/office-365-security/protect-against-threats.md).)</span><span class="sxs-lookup"><span data-stu-id="c3092-155">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](../security/office-365-security/protect-against-threats.md).)</span></span>

<span data-ttu-id="c3092-156">Você deve estar familiarizado com os cmdlets do PowerShell para definir, validar ou editar as políticas de barreira de informações.</span><span class="sxs-lookup"><span data-stu-id="c3092-156">You must be familiar with PowerShell cmdlets in order to define, validate, or edit information barrier policies.</span></span> <span data-ttu-id="c3092-157">Embora forneçamos vários exemplos de cmdlets do PowerShell no [artigo de instruções](information-barriers-policies.md), você precisará saber detalhes adicionais, como parâmetros, para sua organização.</span><span class="sxs-lookup"><span data-stu-id="c3092-157">Although we provide several examples of PowerShell cmdlets in the [how-to article](information-barriers-policies.md), you'll need to know additional details, such as parameters, for your organization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c3092-158">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="c3092-158">Next steps</span></span>

- [<span data-ttu-id="c3092-159">Saiba mais sobre as barreiras de informação no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3092-159">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

- [<span data-ttu-id="c3092-160">Ver os atributos que podem ser usados para políticas de barreira de informações</span><span class="sxs-lookup"><span data-stu-id="c3092-160">See the attributes that can be used for information barrier policies</span></span>](information-barriers-attributes.md)

- [<span data-ttu-id="c3092-161">Definir políticas para barreiras de informações</span><span class="sxs-lookup"><span data-stu-id="c3092-161">Define policies for information barriers</span></span>](information-barriers-policies.md)

- [<span data-ttu-id="c3092-162">Editar (ou remover) políticas de barreira de informações</span><span class="sxs-lookup"><span data-stu-id="c3092-162">Edit (or remove) information barrier policies</span></span>](information-barriers-edit-segments-policies.md) 