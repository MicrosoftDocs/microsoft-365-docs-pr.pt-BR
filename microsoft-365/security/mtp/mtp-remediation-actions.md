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
ms.openlocfilehash: 65ace4bda091b3e000d25a984b706f26fe9c8696
ms.sourcegitcommit: 48b69caf6550e68cb14472ea8cfc76b53e7ae9c6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42225479"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a><span data-ttu-id="3a6a4-104">Ações de correção em recursos de investigação e resposta automatizados no Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3a6a4-104">Remediation actions in automated investigation and response capabilities in Microsoft Threat Protection</span></span>

<span data-ttu-id="3a6a4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="3a6a4-105">**Applies to:**</span></span>
- <span data-ttu-id="3a6a4-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="3a6a4-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="3a6a4-107">Os recursos de investigação e resposta automatizados na proteção contra ameaças da Microsoft incluem determinadas ações de correção.</span><span class="sxs-lookup"><span data-stu-id="3a6a4-107">Automated investigation and response capabilities in Microsoft Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="3a6a4-108">Alguns tipos de ações de correção são executadas em dispositivos, também chamados de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="3a6a4-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="3a6a4-109">Outras ações de correção são executadas no conteúdo do email.</span><span class="sxs-lookup"><span data-stu-id="3a6a4-109">Other remediation actions are taken on email content.</span></span>

<span data-ttu-id="3a6a4-110">A tabela a seguir resume as ações de correção que atualmente têm suporte na proteção contra ameaças da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="3a6a4-110">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="3a6a4-111">Ações de correção de pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="3a6a4-111">Endpoints remediation actions</span></span>  |<span data-ttu-id="3a6a4-112">Ações de correção de email</span><span class="sxs-lookup"><span data-stu-id="3a6a4-112">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="3a6a4-113">Arquivo de quarentena</span><span class="sxs-lookup"><span data-stu-id="3a6a4-113">Quarantine file</span></span><br/><span data-ttu-id="3a6a4-114">Remover chave do registro</span><span class="sxs-lookup"><span data-stu-id="3a6a4-114">Remove registry key</span></span><br/><span data-ttu-id="3a6a4-115">Finalizar processo</span><span class="sxs-lookup"><span data-stu-id="3a6a4-115">Kill process</span></span> <br/><span data-ttu-id="3a6a4-116">Parar serviço</span><span class="sxs-lookup"><span data-stu-id="3a6a4-116">Stop service</span></span> <br/><span data-ttu-id="3a6a4-117">Desabilitar o driver</span><span class="sxs-lookup"><span data-stu-id="3a6a4-117">Disable driver</span></span> <br/><span data-ttu-id="3a6a4-118">Remover tarefa agendada</span><span class="sxs-lookup"><span data-stu-id="3a6a4-118">Remove scheduled task</span></span>      |<span data-ttu-id="3a6a4-119">Exclusão reversível de mensagens de emails ou clusters</span><span class="sxs-lookup"><span data-stu-id="3a6a4-119">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="3a6a4-120">Bloquear URL (hora do clique)</span><span class="sxs-lookup"><span data-stu-id="3a6a4-120">Block URL (time-of-click)</span></span><br/><span data-ttu-id="3a6a4-121">Desativar o encaminhamento de emails externo</span><span class="sxs-lookup"><span data-stu-id="3a6a4-121">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="3a6a4-122">Ações de correção, se estão aguardando aprovação ou já estão concluídas, podem ser exibidas na [central de ações](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="3a6a4-122">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="next-steps"></a><span data-ttu-id="3a6a4-123">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="3a6a4-123">Next steps</span></span>

- [<span data-ttu-id="3a6a4-124">Aprovar ou rejeitar ações relacionadas a investigações e respostas automatizadas</span><span class="sxs-lookup"><span data-stu-id="3a6a4-124">Approve or reject actions related to automated investigation and response</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="3a6a4-125">Saiba mais sobre a Central de Ações</span><span class="sxs-lookup"><span data-stu-id="3a6a4-125">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
