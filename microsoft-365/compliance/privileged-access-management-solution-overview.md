---
title: Gerenciamento de acesso privilegiado no Microsoft 365
description: Saiba como configurar recursos de risco interno em Microsoft 365.
keywords: Microsoft 365, risco interno, conformidade
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
- m365solution-scenario
ms.openlocfilehash: a5cd9d62670b35f7093a3d38cf9e499df407de97
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423804"
---
# <a name="privileged-access-management-in-microsoft-365"></a><span data-ttu-id="b7e0b-104">Gerenciamento de acesso privilegiado no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b7e0b-104">Privileged access management in Microsoft 365</span></span>

<span data-ttu-id="b7e0b-105">Ter acesso permanente por alguns usuários a informações confidenciais ou configurações críticas de rede no Microsoft Exchange Online é um caminho em potencial para contas comprometidas ou atividades de ameaças internas.</span><span class="sxs-lookup"><span data-stu-id="b7e0b-105">Having standing access by some users to sensitive information or critical network configuration settings in Microsoft Exchange Online is a potential pathway for compromised accounts or internal threat activities.</span></span> <span data-ttu-id="b7e0b-106">O gerenciamento de acesso privilegiado ajuda a proteger sua organização contra violações e ajuda a atender às práticas recomendadas de conformidade, limitando o acesso permanente a dados confidenciais ou acesso a configurações críticas.</span><span class="sxs-lookup"><span data-stu-id="b7e0b-106">Privileged access management helps protect your organization from breaches and helps to meet compliance best practices by limiting standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="b7e0b-107">Em vez de os administradores terem acesso constante, regras de acesso just-in-time são implementadas para tarefas que precisam de permissões elevadas.</span><span class="sxs-lookup"><span data-stu-id="b7e0b-107">Instead of administrators having constant access, just-in-time access rules are implemented for tasks that need elevated permissions.</span></span> <span data-ttu-id="b7e0b-108">A habilitação do gerenciamento de acesso privilegiado para Exchange Online no Microsoft 365 permite que sua organização opere com privilégios de posição zero e forneça uma camada de defesa contra vulnerabilidades de acesso administrativo permanentes.</span><span class="sxs-lookup"><span data-stu-id="b7e0b-108">Enabling privileged access management for Exchange Online in Microsoft 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

## <a name="configure-privileged-access-management-for-microsoft-365"></a><span data-ttu-id="b7e0b-109">Configurar o gerenciamento de acesso privilegiado para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b7e0b-109">Configure privileged access management for Microsoft 365</span></span>

<span data-ttu-id="b7e0b-110">Use as etapas a seguir para configurar o gerenciamento de acesso privilegiado para sua organização:</span><span class="sxs-lookup"><span data-stu-id="b7e0b-110">Use the following steps to configure privileged access management for your organization:</span></span>

![Etapas de gerenciamento de acesso privilegiado da solução de risco do Insider](../media/ir-solution-pam-steps.png)

1. <span data-ttu-id="b7e0b-112">Saiba mais sobre [o gerenciamento de acesso](privileged-access-management-overview.md) privilegiado Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b7e0b-112">Learn about [privileged access management](privileged-access-management-overview.md) in Microsoft 365</span></span>
2. <span data-ttu-id="b7e0b-113">Criar um [grupo do aprovador](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span><span class="sxs-lookup"><span data-stu-id="b7e0b-113">Create an [approver's group](privileged-access-management-configuration.md#step-1-create-an-approvers-group)</span></span>
3. <span data-ttu-id="b7e0b-114">[Habilitar o gerenciamento de acesso privilegiado](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span><span class="sxs-lookup"><span data-stu-id="b7e0b-114">Enable [privileged access management](privileged-access-management-configuration.md#step-2-enable-privileged-access)</span></span>
4. <span data-ttu-id="b7e0b-115">Criar uma [política de acesso](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span><span class="sxs-lookup"><span data-stu-id="b7e0b-115">Create an [access policy](privileged-access-management-configuration.md#step-3-create-an-access-policy)</span></span>
5. <span data-ttu-id="b7e0b-116">Enviar/aprovar [solicitações de acesso privilegiado](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span><span class="sxs-lookup"><span data-stu-id="b7e0b-116">Submit/approve [privileged access requests](privileged-access-management-configuration.md#step-4-submitapprove-privileged-access-requests)</span></span>

## <a name="more-information-about-privileged-access-management"></a><span data-ttu-id="b7e0b-117">Mais informações sobre o gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="b7e0b-117">More information about privileged access management</span></span>

- [<span data-ttu-id="b7e0b-118">Perguntas frequentes sobre o gerenciamento de acesso privilegiado</span><span class="sxs-lookup"><span data-stu-id="b7e0b-118">Frequently asked questions about privileged access management</span></span>](privileged-access-management-overview.md#frequently-asked-questions)