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
ms.openlocfilehash: 1dff52fe1bdab364e03bc42afc84c9b54696ccf5
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955528"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="99756-104">Ações de correção após uma investigação automatizada no Office 365</span><span class="sxs-lookup"><span data-stu-id="99756-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="99756-105">Ações de correção</span><span class="sxs-lookup"><span data-stu-id="99756-105">Remediation actions</span></span>

<span data-ttu-id="99756-106">[Recursos de investigação e resposta automatizados](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (Air) no [Office 365 proteção avançada contra ameaças](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) plano 2 inclui determinadas ações de correção.</span><span class="sxs-lookup"><span data-stu-id="99756-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 include certain remediation actions.</span></span> <span data-ttu-id="99756-107">Sempre que uma investigação automatizada estiver em execução ou concluída, você verá, em geral, uma ou mais ações de correção que exigem aprovação da equipe de operações de segurança para continuar.</span><span class="sxs-lookup"><span data-stu-id="99756-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> 

<span data-ttu-id="99756-108">A tabela a seguir resume as ações de correção que estão atualmente disponíveis no Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="99756-108">The following table summarizes the remediation actions that are currently available in Office 365 ATP.</span></span> 

|<span data-ttu-id="99756-109">Ação</span><span class="sxs-lookup"><span data-stu-id="99756-109">Action</span></span> | <span data-ttu-id="99756-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="99756-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="99756-111">Bloquear URL (hora do clique)</span><span class="sxs-lookup"><span data-stu-id="99756-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="99756-112">Protege contra mensagens de email e documentos que contenham URLs mal-intencionadas.</span><span class="sxs-lookup"><span data-stu-id="99756-112">Protects against email messages and documents that contain malicious URLs.</span></span> <span data-ttu-id="99756-113">Isso permite o bloqueio de links mal-intencionados e quaisquer páginas da Web relacionadas por meio de [links seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) quando o usuário clica em um link em um arquivo do Office existente ou em uma mensagem de email mais antiga.</span><span class="sxs-lookup"><span data-stu-id="99756-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="99756-114">Email de exclusão reversível</span><span class="sxs-lookup"><span data-stu-id="99756-114">Soft delete email</span></span>  |<span data-ttu-id="99756-115">Exclusão reversível de mensagens de email específicas da caixa de correio de um usuário.</span><span class="sxs-lookup"><span data-stu-id="99756-115">Soft delete specific email messages from a user's mailbox.</span></span> <br/><span data-ttu-id="99756-116">Uma mensagem excluída por software é movida para a pasta itens recuperáveis de um usuário e é mantida até que o período de retenção do item excluído expire.</span><span class="sxs-lookup"><span data-stu-id="99756-116">A soft-deleted message is moved to a user's Recoverable Items folder and is retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="99756-117">Clusters de emails de exclusão reversível</span><span class="sxs-lookup"><span data-stu-id="99756-117">Soft delete email clusters</span></span>  |<span data-ttu-id="99756-118">Exclusão reversível mensagens de email mal-intencionadas que correspondem a uma consulta de todas as caixas de correio dos usuários.</span><span class="sxs-lookup"><span data-stu-id="99756-118">Soft delete malicious email messages matching a query from all users' mailboxes.</span></span> <br/><span data-ttu-id="99756-119">As mensagens excluídas por software são movidas para a pasta itens recuperáveis dos usuários e são mantidas até que o período de retenção do item excluído expire.</span><span class="sxs-lookup"><span data-stu-id="99756-119">Soft-deleted messages are moved to users' Recoverable Items folder and are retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="99756-120">Desativar o encaminhamento de emails externo</span><span class="sxs-lookup"><span data-stu-id="99756-120">Turn off external mail forwarding</span></span> |<span data-ttu-id="99756-121">Remove uma regra de encaminhamento de uma caixa de correio de usuário final específica.</span><span class="sxs-lookup"><span data-stu-id="99756-121">Removes a forwarding rule from a specific end user's mailbox.</span></span>|

> [!NOTE]
> <span data-ttu-id="99756-122">No Office 365 ATP, nenhuma ação de correção é executada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="99756-122">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="99756-123">As ações de correção são executadas apenas após a aprovação da equipe de segurança da sua organização.</span><span class="sxs-lookup"><span data-stu-id="99756-123">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="99756-124">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="99756-124">Next steps</span></span>

- [<span data-ttu-id="99756-125">Exibir ações de correção pendentes ou concluídas após uma investigação automatizada no Office 365</span><span class="sxs-lookup"><span data-stu-id="99756-125">View pending or completed remediation actions following an automated investigation in Office 365</span></span>](air-review-approve-pending-completed-actions.md)

- [<span data-ttu-id="99756-126">Detalhes e resultados de uma investigação automatizada no Office 365</span><span class="sxs-lookup"><span data-stu-id="99756-126">Details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)

## <a name="related-articles"></a><span data-ttu-id="99756-127">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="99756-127">Related articles</span></span>

- [<span data-ttu-id="99756-128">Investigação automatizada no Microsoft defender proteção avançada contra ameaças</span><span class="sxs-lookup"><span data-stu-id="99756-128">Automated investigation in Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="99756-129">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="99756-129">Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)