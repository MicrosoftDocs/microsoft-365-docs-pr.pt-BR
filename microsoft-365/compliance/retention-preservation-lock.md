---
title: Use o Bloqueio de Preservação para restringir as alterações para políticas de retenção e políticas de rótulo de retenção
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Use o Bloqueio de Preservação com políticas de retenção e políticas de rótulo de retenção para ajudá-lo a atender aos requisitos normativos e proteger contra administradores não autorizados.
ms.openlocfilehash: 9890c73495bd14ea7264f3314f6313254ef1bf6b
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49612983"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a><span data-ttu-id="bb61d-103">Use o Bloqueio de Preservação para restringir as alterações para políticas de retenção e políticas de rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="bb61d-103">Use Preservation Lock to restrict changes to retention policies and retention label policies</span></span>

><span data-ttu-id="bb61d-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="bb61d-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="bb61d-105">O Bloqueio de Preservação trava uma política de retenção ou uma política de rótulo de retenção para que ninguém, incluindo um administrador global, possa desativar a política, excluir a política ou torná-la menos restritiva.</span><span class="sxs-lookup"><span data-stu-id="bb61d-105">Preservation Lock locks a retention policy or retention label policy so that no one—including a global admin—can turn off the policy, delete the policy, or make it less restrictive.</span></span> <span data-ttu-id="bb61d-106">Essa configuração pode ser necessária para atender aos requisitos regulatórios e ajudar a proteger contra administradores não autorizados.</span><span class="sxs-lookup"><span data-stu-id="bb61d-106">This configuration might be needed for regulatory requirements and can help safeguard against rogue administrators.</span></span>

<span data-ttu-id="bb61d-107">Quando uma política de retenção está bloqueada:</span><span class="sxs-lookup"><span data-stu-id="bb61d-107">When a retention policy is locked:</span></span>

- <span data-ttu-id="bb61d-108">Ninguém pode desabilitar a política ou excluí-la</span><span class="sxs-lookup"><span data-stu-id="bb61d-108">No one can disable the policy or delete it</span></span>
- <span data-ttu-id="bb61d-109">Locais podem ser adicionados, mas não removidos</span><span class="sxs-lookup"><span data-stu-id="bb61d-109">Locations can be added but not removed</span></span>
- <span data-ttu-id="bb61d-110">Você pode estender o período de retenção, mas não reduzi-lo</span><span class="sxs-lookup"><span data-stu-id="bb61d-110">You can extend the retention period but not decrease it</span></span>

<span data-ttu-id="bb61d-111">Quando uma política de rótulo de retenção está bloqueada:</span><span class="sxs-lookup"><span data-stu-id="bb61d-111">When a retention label policy is locked:</span></span>

- <span data-ttu-id="bb61d-112">Ninguém pode desabilitar a política ou excluí-la</span><span class="sxs-lookup"><span data-stu-id="bb61d-112">No one can disable the policy or delete it</span></span>
- <span data-ttu-id="bb61d-113">Locais podem ser adicionados, mas não removidos</span><span class="sxs-lookup"><span data-stu-id="bb61d-113">Locations can be added but not removed</span></span>
- <span data-ttu-id="bb61d-114">Rótulos podem ser adicionados, mas não removidos</span><span class="sxs-lookup"><span data-stu-id="bb61d-114">Labels can be added but not removed</span></span>

<span data-ttu-id="bb61d-115">Em resumo, uma política de retenção bloqueada pode ser aumentada ou estendida, mas não poderá ser reduzida ou desativada.</span><span class="sxs-lookup"><span data-stu-id="bb61d-115">In summary, a locked policy can be increased or extended, but it can't be reduced or turned off.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb61d-116">Antes de bloquear uma política de retenção, é fundamental que você entenda o impacto e confirme se ela é necessária para a sua organização atender aos requisitos normativos.</span><span class="sxs-lookup"><span data-stu-id="bb61d-116">Before you lock a retention policy or retention label policy, it's critical that you understand the impact and confirm whether it's required for your organization.</span></span> <span data-ttu-id="bb61d-117">Por exemplo, pode ser necessário atender aos requisitos normativos.</span><span class="sxs-lookup"><span data-stu-id="bb61d-117">For example, it might be needed to meet regulatory requirements.</span></span> <span data-ttu-id="bb61d-118">Os administradores não poderão desabilitar ou excluir uma política de retenção após a aplicação do bloqueio de preservação.</span><span class="sxs-lookup"><span data-stu-id="bb61d-118">Administrators won't be able to disable or delete these policies after the preservation lock is applied.</span></span>

<span data-ttu-id="bb61d-119">Configure o Bloqueio de Preservação após criar uma [política de retenção](create-retention-policies.md) ou uma política de rótulo de retenção que você [publicar](create-apply-retention-labels.md) ou [aplicar automaticamente](apply-retention-labels-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="bb61d-119">Configure Preservation Lock after you've created a [retention policy](create-retention-policies.md), or a retention label policy that you [publish](create-apply-retention-labels.md) or [auto-apply](apply-retention-labels-automatically.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="bb61d-120">O bloqueio de uma política de rótulo não impede que um administrador reduza o período de retenção em um rótulo que esteja incluído na política de bloqueio.</span><span class="sxs-lookup"><span data-stu-id="bb61d-120">Locking a label policy doesn't prevent an administrator from reducing the retention period in a label that is included in the locked policy.</span></span> <span data-ttu-id="bb61d-121">Esse requisito, com outras restrições, pode ser atendido ao configurar um rótulo para marcar itens como um [registro regulatório](records-management.md#records).</span><span class="sxs-lookup"><span data-stu-id="bb61d-121">That requirement, with other restrictions, can be met when you configure a label to mark items as a [regulatory record](records-management.md#records).</span></span>

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a><span data-ttu-id="bb61d-122">Como bloquear uma política de retenção ou uma política de rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="bb61d-122">How to lock a retention policy or retention label policy</span></span>

<span data-ttu-id="bb61d-123">Você deve usar o Windows PowerShell se precisar usar o Bloqueio de Preservação.</span><span class="sxs-lookup"><span data-stu-id="bb61d-123">You must use PowerShell if you need to use Preservation Lock.</span></span> <span data-ttu-id="bb61d-124">Como os administradores não podem desabilitar ou excluir uma política de retenção após a aplicação de um bloqueio de preservação, a habilitação desse recurso não está disponível na interface do usuário para proteger contra configurações acidentais.</span><span class="sxs-lookup"><span data-stu-id="bb61d-124">Because administrators can't disable or delete a policy for retention after this lock is applied, enabling this feature is not available in the UI to safeguard against accidental configuration.</span></span>

<span data-ttu-id="bb61d-125">Todas as políticas de retenção, com qualquer configuração, oferecem suporte ao Bloqueio de Preservação.</span><span class="sxs-lookup"><span data-stu-id="bb61d-125">All policies for retention and with any configuration support Preservation Lock.</span></span>

1. <span data-ttu-id="bb61d-126">[Conectar-se ao PowerShell do Centro de Conformidade e Segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="bb61d-126">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="bb61d-127">Localize o nome da política que você deseja bloquear, executando o [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy).</span><span class="sxs-lookup"><span data-stu-id="bb61d-127">Find the name of the policy that you want to lock by running [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy).</span></span> <span data-ttu-id="bb61d-128">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bb61d-128">For example:</span></span>
    
   ![Lista de políticas de retenção no PowerShell](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. <span data-ttu-id="bb61d-130">Para colocar um Bloqueio de Preservação na sua política, execute o cmdlet [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) com o nome da política e o parâmetro *RestrictiveRetention* definido como verdadeiro:</span><span class="sxs-lookup"><span data-stu-id="bb61d-130">To place a Preservation Lock on your policy, run the [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet with the name of the policy, and the *RestrictiveRetention* parameter set to true:</span></span>
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    <span data-ttu-id="bb61d-131">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bb61d-131">For example:</span></span>
    
    ![Parâmetro RestrictiveRetention no PowerShell](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     <span data-ttu-id="bb61d-133">Quando solicitado, leia e reconheça as restrições que vêm com esta configuração digitando **S**:</span><span class="sxs-lookup"><span data-stu-id="bb61d-133">When prompted, read and acknowledge the restrictions that come with this configuration by entering **Y**:</span></span>
    
   ![Solicitar confirmação que deseja bloquear uma política de retenção no PowerShell](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="bb61d-135">O Bloqueio de Preservação agora está localizado na política de retenção.</span><span class="sxs-lookup"><span data-stu-id="bb61d-135">A Preservation Lock is now placed on the policy.</span></span> <span data-ttu-id="bb61d-136">Para confirmar, execute o `Get-RetentionCompliancePolicy` novamente, mas especifique o nome da política de retenção e exiba os parâmetros da política:</span><span class="sxs-lookup"><span data-stu-id="bb61d-136">To confirm, run `Get-RetentionCompliancePolicy` again, but specify the policy name and display the policy parameters:</span></span>

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

<span data-ttu-id="bb61d-137">Você deverá ver que o **RestrictiveRetention** está definido como **Verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="bb61d-137">You should see **RestrictiveRetention** is set to **True**.</span></span> <span data-ttu-id="bb61d-138">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bb61d-138">For example:</span></span>

![Bloquear a política com todos os parâmetros mostrados no PowerShell](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a><span data-ttu-id="bb61d-140">Confira também</span><span class="sxs-lookup"><span data-stu-id="bb61d-140">See also</span></span>

[<span data-ttu-id="bb61d-141">Recursos para ajudá-lo a atender aos requisitos normativos para o controle de informações e o gerenciamento de registros</span><span class="sxs-lookup"><span data-stu-id="bb61d-141">Resources to help you meet regulatory requirements for information governance and records management</span></span>](retention-regulatory-requirements.md)
