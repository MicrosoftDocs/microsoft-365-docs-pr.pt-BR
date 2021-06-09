---
title: Resolver problemas com caixas de correio compartilhadas
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Você pode receber erros ao configurar caixas de correio compartilhadas. Experimente essas soluções se você tiver problemas com caixas de correio compartilhadas.
ms.openlocfilehash: 89cdfbe29ab035b1eb6c3a0183629eef59d67477
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706125"
---
# <a name="resolve-issues-with-shared-mailboxes"></a><span data-ttu-id="ba3df-104">Resolver problemas com caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="ba3df-104">Resolve issues with shared mailboxes</span></span>

<span data-ttu-id="ba3df-105">Se você vir mensagens de erro ao criar ou usar uma caixa de correio compartilhada, experimente essas soluções possíveis.</span><span class="sxs-lookup"><span data-stu-id="ba3df-105">If you see error messages when creating or using a shared mailbox, try these possible solutions.</span></span> 

## <a name="error-when-creating-shared-mailboxes"></a><span data-ttu-id="ba3df-106">Erro ao criar caixas de correio compartilhadas</span><span class="sxs-lookup"><span data-stu-id="ba3df-106">Error when creating shared mailboxes</span></span>
<span data-ttu-id="ba3df-107"><a name="bkmk_Fix"> </a></span><span class="sxs-lookup"><span data-stu-id="ba3df-107"><a name="bkmk_Fix"> </a></span></span>

<span data-ttu-id="ba3df-108">Se você vir a mensagem de erro, o endereço proxy "smtp:<nome de caixa de correio compartilhado " já está sendo usado pelos endereços proxy ou **\> LegacyExchangeDN de " \<name> ". Escolha outro endereço proxy**, isso significa que você está tentando dar à caixa de correio compartilhada um nome que já esteja em uso.</span><span class="sxs-lookup"><span data-stu-id="ba3df-108">If you see the error message, **The proxy address "smtp:<shared mailbox name\>" is already being used by the proxy addresses or LegacyExchangeDN of "\<name>". Please choose another proxy address**, it means you're trying to give the shared mailbox a name that's already in use.</span></span> <span data-ttu-id="ba3df-109">Por exemplo, digamos que você deseja nomear as caixas de correio compartilhadas como info@dominio1 e info@dominio2.</span><span class="sxs-lookup"><span data-stu-id="ba3df-109">For example, let's say you want shared mailboxes named info@domain1 and info@domain2.</span></span> <span data-ttu-id="ba3df-110">Há duas maneiras de fazer isso:</span><span class="sxs-lookup"><span data-stu-id="ba3df-110">There are two ways to do this:</span></span>

  - <span data-ttu-id="ba3df-111">Use o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ba3df-111">Use Windows PowerShell.</span></span> <span data-ttu-id="ba3df-112">Consulte esta postagem de blog para obter instruções: [Criar caixas de correio compartilhadas com o mesmo alias em domínios diferentes](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="ba3df-112">See this blog post for instructions: [Create Shared Mailboxes with Same Alias at Different Domains](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)</span></span>
    
  - <span data-ttu-id="ba3df-113">Nomeia a segunda caixa de correio compartilhada algo diferente do início para dar a volta ao erro.</span><span class="sxs-lookup"><span data-stu-id="ba3df-113">Name the second shared mailbox something different from the start to get around the error.</span></span> <span data-ttu-id="ba3df-114">Em seguida, no centro de administração, renomeie a caixa de correio compartilhada para o que você deseja que ela seja.</span><span class="sxs-lookup"><span data-stu-id="ba3df-114">Then in the admin center, rename the shared mailbox to what you want it to be.</span></span>

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a><span data-ttu-id="ba3df-115">Erro sobre não ter permissões de envio ao usar uma caixa de correio compartilhada</span><span class="sxs-lookup"><span data-stu-id="ba3df-115">Error about not having send permissions when using a shared mailbox</span></span>

<span data-ttu-id="ba3df-116">Se você criou uma caixa de correio compartilhada e, em seguida, tentar enviar uma mensagem dela, você pode obter isso:</span><span class="sxs-lookup"><span data-stu-id="ba3df-116">If you created a shared mailbox and then try to send a message from it, you might get this:</span></span>

<span data-ttu-id="ba3df-117">**Esta mensagem não pôde ser enviada. Você não tem permissão para enviar a mensagem em nome do usuário especificado.**</span><span class="sxs-lookup"><span data-stu-id="ba3df-117">**This message could not be sent. You do not have the permission to send the message on behalf of the specified user.**</span></span>

<span data-ttu-id="ba3df-118">Essa mensagem aparece quando Microsoft 365 está enfrentando um problema de latência de replicação.</span><span class="sxs-lookup"><span data-stu-id="ba3df-118">This message appears when Microsoft 365 is experiencing a replication latency issue.</span></span> <span data-ttu-id="ba3df-119">Ele deve desaparecer em uma hora ou mais, quando as informações sobre sua nova caixa de correio compartilhada (ou usuário adicionado) são replicadas em todos os nossos data centers.</span><span class="sxs-lookup"><span data-stu-id="ba3df-119">It should go away in an hour or so, when the information about your new shared mailbox (or added user) is replicated across all of our data centers.</span></span> <span data-ttu-id="ba3df-120">Aguarde uma hora e tente novamente enviar uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="ba3df-120">Wait an hour and then try again to send a message.</span></span>

## <a name="related-content"></a><span data-ttu-id="ba3df-121">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="ba3df-121">Related content</span></span>

<span data-ttu-id="ba3df-122">[Sobre as caixas de correio compartilhadas](about-shared-mailboxes.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="ba3df-122">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="ba3df-123">[Criar uma caixa de correio compartilhada](create-a-shared-mailbox.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="ba3df-123">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="ba3df-124">[Configurar uma caixa de correio compartilhada](configure-a-shared-mailbox.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="ba3df-124">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="ba3df-125">[Converter uma caixa de correio do usuário em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="ba3df-125">[Convert a user mailbox to a shared mailbox](convert-user-mailbox-to-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="ba3df-126">[Remover uma licença de uma caixa de correio compartilhada](remove-license-from-shared-mailbox.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="ba3df-126">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>


    

