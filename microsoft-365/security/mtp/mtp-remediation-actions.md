---
title: Ações de correção em recursos de investigação e resposta automatizados no Microsoft Threat Protection
description: Obter uma visão geral dos recursos de investigação e resposta automatizados na Proteção contra Ameaça da Microsoft
keywords: automatizado, investigação, alerta, gatilho, ação, correção
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 73bb90a0537df8e6f23e4e0e50a748aebda3a487
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175895"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a><span data-ttu-id="cc704-104">Ações de correção em recursos de investigação e resposta automatizados no Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="cc704-104">Remediation actions in automated investigation and response capabilities in Microsoft Threat Protection</span></span>

<span data-ttu-id="cc704-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="cc704-105">**Applies to:**</span></span>
- <span data-ttu-id="cc704-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="cc704-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="cc704-107">Os recursos de investigação e resposta automatizados na proteção contra ameaças da Microsoft incluem determinadas ações de correção.</span><span class="sxs-lookup"><span data-stu-id="cc704-107">Automated investigation and response capabilities in Microsoft Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="cc704-108">Alguns tipos de ações de correção são executadas em dispositivos, também chamados de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="cc704-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="cc704-109">Outras ações de correção são executadas no conteúdo do email.</span><span class="sxs-lookup"><span data-stu-id="cc704-109">Other remediation actions are taken on email content.</span></span>

<span data-ttu-id="cc704-110">A tabela a seguir resume as ações de correção que atualmente têm suporte na proteção contra ameaças da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="cc704-110">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="cc704-111">Ações de correção de pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="cc704-111">Endpoints remediation actions</span></span>  |<span data-ttu-id="cc704-112">Ações de correção de email</span><span class="sxs-lookup"><span data-stu-id="cc704-112">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="cc704-113">Arquivo de quarentena</span><span class="sxs-lookup"><span data-stu-id="cc704-113">Quarantine file</span></span><br/><span data-ttu-id="cc704-114">Remover chave do registro</span><span class="sxs-lookup"><span data-stu-id="cc704-114">Remove registry key</span></span><br/><span data-ttu-id="cc704-115">Finalizar processo</span><span class="sxs-lookup"><span data-stu-id="cc704-115">Kill process</span></span> <br/><span data-ttu-id="cc704-116">Parar serviço</span><span class="sxs-lookup"><span data-stu-id="cc704-116">Stop service</span></span> <br/><span data-ttu-id="cc704-117">Remover chave do registro</span><span class="sxs-lookup"><span data-stu-id="cc704-117">Remove registry key</span></span> <br/><span data-ttu-id="cc704-118">Desabilitar o driver</span><span class="sxs-lookup"><span data-stu-id="cc704-118">Disable driver</span></span> <br/><span data-ttu-id="cc704-119">Remover tarefa agendada</span><span class="sxs-lookup"><span data-stu-id="cc704-119">Remove scheduled task</span></span>      |<span data-ttu-id="cc704-120">Exclusão reversível de mensagens de emails ou clusters</span><span class="sxs-lookup"><span data-stu-id="cc704-120">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="cc704-121">Bloquear URL (hora do clique)</span><span class="sxs-lookup"><span data-stu-id="cc704-121">Block URL (time-of-click)</span></span><br/><span data-ttu-id="cc704-122">Desativar o encaminhamento de emails externo</span><span class="sxs-lookup"><span data-stu-id="cc704-122">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="cc704-123">Ações de correção, se estão aguardando aprovação ou já estão concluídas, podem ser exibidas na [central de ações](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="cc704-123">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="next-steps"></a><span data-ttu-id="cc704-124">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="cc704-124">Next steps</span></span>

- [<span data-ttu-id="cc704-125">Aprovar ou rejeitar ações relacionadas a investigações e respostas automatizadas</span><span class="sxs-lookup"><span data-stu-id="cc704-125">Approve or reject actions related to automated investigation and response</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="cc704-126">Saiba mais sobre a Central de Ações</span><span class="sxs-lookup"><span data-stu-id="cc704-126">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
