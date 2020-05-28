---
title: Resolver problemas com caixas de correio compartilhadas
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Tente estas soluções se você tiver problemas com caixas de correio compartilhadas.
ms.openlocfilehash: 5d6de9ac66b11f0e50b259cdca0b1bb50b8326ee
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400011"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="af792-103">Resolver problemas com caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="af792-103">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="af792-104">Se você vir mensagens de erro ao criar ou usar uma caixa de correio compartilhada, tente estas soluções possíveis.</span><span class="sxs-lookup"><span data-stu-id="af792-104">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="af792-105">Erro ao criar caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="af792-105">Error when creating shared mailboxes</span></span>
<span data-ttu-id="af792-106"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="af792-106"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="af792-107">Se você vir a mensagem de erro, **o endereço de proxy "SMTP: <nome da caixa de correio compartilhada \> " já estiver sendo usado pelos endereços proxy ou legacyExchangeDN de " \<name> ". Escolha outro endereço de proxy**, significa que você está tentando dar um nome à caixa de correio compartilhada que já está em uso.</span><span class="sxs-lookup"><span data-stu-id="af792-107">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="af792-108">Por exemplo, digamos que você deseja nomear as caixas de correio compartilhadas como info@dominio1 e info@dominio2.</span><span class="sxs-lookup"><span data-stu-id="af792-108">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="af792-109">Há duas maneiras de fazer isso:</span><span class="sxs-lookup"><span data-stu-id="af792-109">There are two ways to do this:</span></span>

  - <span data-ttu-id="af792-110">Use o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af792-110">Use Windows PowerShell.</span></span> <span data-ttu-id="af792-111">Confira esta postagem de blog para obter instruções: [criar caixas de correio compartilhadas com o mesmo alias em domínios diferentes](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="af792-111">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="af792-112">Nomeie a segunda caixa de correio compartilhada algo diferente do início para contornar o erro.</span><span class="sxs-lookup"><span data-stu-id="af792-112">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="af792-113">Em seguida, no centro de administração, renomeie a caixa de correio compartilhada para o que você deseja.</span><span class="sxs-lookup"><span data-stu-id="af792-113">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="af792-114">Erro sobre não ter permissões de envio ao usar uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="af792-114">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="af792-115">Se você criou uma caixa de correio compartilhada e, em seguida, tenta enviar uma mensagem dela, você pode fazer isso:</span><span class="sxs-lookup"><span data-stu-id="af792-115">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="af792-116">**Não foi possível enviar esta mensagem. Você não tem permissão para enviar a mensagem em nome do usuário especificado.**</span><span class="sxs-lookup"><span data-stu-id="af792-116">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="af792-117">Esta mensagem é exibida quando o Microsoft 365 está enfrentando um problema de latência de replicação.</span><span class="sxs-lookup"><span data-stu-id="af792-117">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="af792-118">Ela deve desaparecer em uma hora ou assim, quando as informações sobre sua nova caixa de correio compartilhada (ou usuário adicionado) são replicadas em todos os nossos data centers.</span><span class="sxs-lookup"><span data-stu-id="af792-118">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="af792-119">Aguarde uma hora e tente novamente enviar uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="af792-119">Wait an hour and then try again to send a message.</span></span>

## <a name="related-articles"></a><span data-ttu-id="af792-120">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="af792-120">Related articles</span></span>

[<span data-ttu-id="af792-121">Sobre as caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="af792-121">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="af792-122">Criar uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="af792-122">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="af792-123">Configurar uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="af792-123">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

<span data-ttu-id="af792-124">[Converter uma caixa de correio do usuário em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="af792-124">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md)</span></span>

[<span data-ttu-id="af792-125">Remover uma licença de uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="af792-125">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)


    

