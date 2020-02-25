---
title: Ações de correção no Office 365 investigação e resposta automatizadas
keywords: AIR, autoIR, ATP, automatizado, investigação, resposta, correção, ameaças, avançado, ameaça, proteção
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Saiba mais sobre as ações de correção em recursos de investigação e resposta automatizados no Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 433813ed1a801117a88da696392030db5091b54b
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42261048"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="7cb6c-104">Ações de correção após uma investigação automatizada no Office 365</span><span class="sxs-lookup"><span data-stu-id="7cb6c-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="7cb6c-105">Ações de correção</span><span class="sxs-lookup"><span data-stu-id="7cb6c-105">Remediation actions</span></span>

<span data-ttu-id="7cb6c-106">Os [recursos de investigação e resposta automatizados](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) na proteção avançada contra ameaças do Office 365 incluem determinadas ações de correção.</span><span class="sxs-lookup"><span data-stu-id="7cb6c-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) in Office 365 Advanced Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="7cb6c-107">Sempre que uma investigação automatizada estiver em execução ou concluída, você verá, em geral, uma ou mais ações de correção que exigem aprovação da equipe de operações de segurança para continuar.</span><span class="sxs-lookup"><span data-stu-id="7cb6c-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> <span data-ttu-id="7cb6c-108">A tabela a seguir resume as ações de correção disponíveis atualmente na proteção avançada contra ameaças do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7cb6c-108">The following table summarizes remediation actions currently available in Office 365 Advanced Threat Protection.</span></span> 

|<span data-ttu-id="7cb6c-109">Ação</span><span class="sxs-lookup"><span data-stu-id="7cb6c-109">Action</span></span> | <span data-ttu-id="7cb6c-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="7cb6c-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="7cb6c-111">Bloquear URL (hora do clique)</span><span class="sxs-lookup"><span data-stu-id="7cb6c-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="7cb6c-112">Proteger contra emails e documentos que contenham URLs mal-intencionadas.</span><span class="sxs-lookup"><span data-stu-id="7cb6c-112">Protect against emails and documents that contain malicious URLs.</span></span> <span data-ttu-id="7cb6c-113">Isso permite o bloqueio de links mal-intencionados e quaisquer páginas da Web relacionadas por meio de [links seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) quando o usuário clica em um link em um arquivo do Office existente ou em uma mensagem de email mais antiga.</span><span class="sxs-lookup"><span data-stu-id="7cb6c-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="7cb6c-114">Email de exclusão reversível</span><span class="sxs-lookup"><span data-stu-id="7cb6c-114">Soft delete email</span></span>  |<span data-ttu-id="7cb6c-115">Exclusão reversível de mensagens de email específicas da caixa de correio de um usuário</span><span class="sxs-lookup"><span data-stu-id="7cb6c-115">Soft delete specific email messages from a user's mailbox</span></span>|
|<span data-ttu-id="7cb6c-116">Clusters de emails de exclusão reversível</span><span class="sxs-lookup"><span data-stu-id="7cb6c-116">Soft delete email clusters</span></span>  |<span data-ttu-id="7cb6c-117">Exclusão reversível de mensagens de email mal-intencionadas que correspondem a uma consulta de todas as caixas de correio dos usuários</span><span class="sxs-lookup"><span data-stu-id="7cb6c-117">Soft delete malicious email messages matching a query from all users' mailboxes</span></span>|
|<span data-ttu-id="7cb6c-118">Desativar o encaminhamento de emails externo</span><span class="sxs-lookup"><span data-stu-id="7cb6c-118">Turn off external mail forwarding</span></span> |<span data-ttu-id="7cb6c-119">Remove a regra de encaminhamento de uma caixa de correio de usuário final específica</span><span class="sxs-lookup"><span data-stu-id="7cb6c-119">Removes forwarding rule from a specific end user's mailbox</span></span>|

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="7cb6c-120">Aprovar (ou rejeitar) ações pendentes</span><span class="sxs-lookup"><span data-stu-id="7cb6c-120">Approve (or reject) pending actions</span></span>

![Página de ação de investigações aéreas](../../media/air-investigationactionspage.png)

<span data-ttu-id="7cb6c-122">Ao exibir os [detalhes de uma investigação](air-view-investigation-results.md), você pode aprovar ou rejeitar qualquer ação de correção pendente.</span><span class="sxs-lookup"><span data-stu-id="7cb6c-122">While viewing the [details of an investigation](air-view-investigation-results.md), you can approve or reject any pending remediation actions.</span></span> <span data-ttu-id="7cb6c-123">É recomendável fazer isso assim que possível para que suas investigações automatizadas sejam concluídas.</span><span class="sxs-lookup"><span data-stu-id="7cb6c-123">We recommend doing this as soon as possible so that your automated investigations complete.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7cb6c-124">As permissões apropriadas são necessárias para aprovar ou rejeitar ações de correção.</span><span class="sxs-lookup"><span data-stu-id="7cb6c-124">Appropriate permissions are required to approve or reject remediation actions.</span></span> <span data-ttu-id="7cb6c-125">Confira [as permissões necessárias para usar os recursos de ar](office-365-air.md#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="7cb6c-125">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

1. <span data-ttu-id="7cb6c-126">Selecione a guia **ações** .</span><span class="sxs-lookup"><span data-stu-id="7cb6c-126">Select the **Actions** tab.</span></span>

2. <span data-ttu-id="7cb6c-127">Selecione um item na lista.</span><span class="sxs-lookup"><span data-stu-id="7cb6c-127">Select an item in the list.</span></span> <span data-ttu-id="7cb6c-128">(Isso ativa os botões aprovar e rejeitar).</span><span class="sxs-lookup"><span data-stu-id="7cb6c-128">(This activates the Approve and Reject buttons.)</span></span>

3. <span data-ttu-id="7cb6c-129">Revise as informações disponíveis para o (s) item (ns) que você selecionou e, em seguida, aprove ou rejeite a (s) ação (ões).</span><span class="sxs-lookup"><span data-stu-id="7cb6c-129">Review available information for the item(s) you selected, and then either approve or reject the action(s).</span></span> 
 - <span data-ttu-id="7cb6c-130">**Aprovar** permite que a correção seja iniciada.</span><span class="sxs-lookup"><span data-stu-id="7cb6c-130">**Approve** allows remediation to begin.</span></span>
 - <span data-ttu-id="7cb6c-131">**Rejeitar** não realiza mais nenhuma ação</span><span class="sxs-lookup"><span data-stu-id="7cb6c-131">**Reject** takes no further action</span></span>

## <a name="next-steps"></a><span data-ttu-id="7cb6c-132">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="7cb6c-132">Next steps</span></span>

- [<span data-ttu-id="7cb6c-133">Saiba mais sobre o guia de segurança de usuário comprometido</span><span class="sxs-lookup"><span data-stu-id="7cb6c-133">Learn about the compromised user security playbook</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/address-compromised-users-quickly)

- [<span data-ttu-id="7cb6c-134">Exibir seus relatórios de ATP</span><span class="sxs-lookup"><span data-stu-id="7cb6c-134">View your ATP reports</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)