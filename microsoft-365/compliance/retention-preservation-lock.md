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
ms.openlocfilehash: 6f6cfc5bef9b93af08fcc9b703b29facb9a7c576
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920682"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a><span data-ttu-id="516ed-103">Use o Bloqueio de Preservação para restringir as alterações para políticas de retenção e políticas de rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="516ed-103">Use Preservation Lock to restrict changes to retention policies and retention label policies</span></span>

><span data-ttu-id="516ed-104">*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="516ed-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="516ed-105">O Bloqueio de Preservação trava uma política de retenção ou uma política de rótulo de retenção para que ninguém, incluindo um administrador global, possa desativar a política, excluir a política ou torná-la menos restritiva.</span><span class="sxs-lookup"><span data-stu-id="516ed-105">Preservation Lock locks a retention policy or retention label policy so that no one—including a global admin—can turn off the policy, delete the policy, or make it less restrictive.</span></span> <span data-ttu-id="516ed-106">Essa configuração pode ser necessária para atender aos requisitos regulatórios e ajudar a proteger contra administradores não autorizados.</span><span class="sxs-lookup"><span data-stu-id="516ed-106">This configuration might be needed for regulatory requirements and can help safeguard against rogue administrators.</span></span>

<span data-ttu-id="516ed-107">Quando uma política de retenção estiver bloqueada:</span><span class="sxs-lookup"><span data-stu-id="516ed-107">When a policy for retention is locked:</span></span>

- <span data-ttu-id="516ed-108">Ninguém pode desligá-lo</span><span class="sxs-lookup"><span data-stu-id="516ed-108">No one can turn it off</span></span>
- <span data-ttu-id="516ed-109">Locais podem ser adicionados, mas não removidos</span><span class="sxs-lookup"><span data-stu-id="516ed-109">Locations can be added but not removed</span></span>
- <span data-ttu-id="516ed-110">Você pode estender um período de retenção, mas não reduzi-lo</span><span class="sxs-lookup"><span data-stu-id="516ed-110">You can extend a retention period but not decrease it</span></span>

<span data-ttu-id="516ed-111">Em resumo, uma política de retenção bloqueada pode ser aumentada ou estendida, mas não poderá ser reduzida ou desativada.</span><span class="sxs-lookup"><span data-stu-id="516ed-111">In summary, a locked policy can be increased or extended, but it can't be reduced or turned off.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="516ed-112">Antes de bloquear uma política de retenção, é fundamental que você entenda o impacto e confirme se ela é necessária para a sua organização atender aos requisitos normativos.</span><span class="sxs-lookup"><span data-stu-id="516ed-112">Before you lock a retention policy or retention label policy, it's critical that you understand the impact and confirm whether it's required for your organization.</span></span> <span data-ttu-id="516ed-113">Por exemplo, pode ser necessário atender aos requisitos normativos.</span><span class="sxs-lookup"><span data-stu-id="516ed-113">For example, it might be needed to meet regulatory requirements.</span></span> <span data-ttu-id="516ed-114">Os administradores não poderão desabilitar ou excluir uma política de retenção após a aplicação do bloqueio de preservação.</span><span class="sxs-lookup"><span data-stu-id="516ed-114">Administrators won't be able to disable or delete these policies after the preservation lock is applied.</span></span>

<span data-ttu-id="516ed-115">Configure o Bloqueio de Preservação após criar uma [política de retenção](create-retention-policies.md) ou uma política de rótulo de retenção que você [publicar](create-apply-retention-labels.md) ou [aplicar automaticamente](apply-retention-labels-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="516ed-115">Configure Preservation Lock after you've created a [retention policy](create-retention-policies.md), or a retention label policy that you [publish](create-apply-retention-labels.md) or [auto-apply](apply-retention-labels-automatically.md).</span></span> 

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a><span data-ttu-id="516ed-116">Como bloquear uma política de retenção ou uma política de rótulo de retenção</span><span class="sxs-lookup"><span data-stu-id="516ed-116">How to lock a retention policy or retention label policy</span></span>

<span data-ttu-id="516ed-117">Você deve usar o Windows PowerShell se precisar usar o Bloqueio de Preservação.</span><span class="sxs-lookup"><span data-stu-id="516ed-117">You must use PowerShell if you need to use Preservation Lock.</span></span> <span data-ttu-id="516ed-118">Como os administradores não podem desabilitar ou excluir uma política de retenção após a aplicação de um bloqueio de preservação, a habilitação desse recurso não está disponível na interface do usuário para proteger contra configurações acidentais.</span><span class="sxs-lookup"><span data-stu-id="516ed-118">Because administrators can't disable or delete a policy for retention after this lock is applied, enabling this feature is not available in the UI to safeguard against accidental configuration.</span></span>

<span data-ttu-id="516ed-119">Todas as políticas de retenção, com qualquer configuração, oferecem suporte ao Bloqueio de Preservação.</span><span class="sxs-lookup"><span data-stu-id="516ed-119">All policies for retention and with any configuration support Preservation Lock.</span></span>

1. <span data-ttu-id="516ed-120">[Conectar-se ao PowerShell do Centro de Conformidade e Segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="516ed-120">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="516ed-121">Localize o nome da política que você deseja bloquear, executando o [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy).</span><span class="sxs-lookup"><span data-stu-id="516ed-121">Find the name of the policy that you want to lock by running [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy).</span></span> <span data-ttu-id="516ed-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="516ed-122">For example:</span></span>
    
   ![Lista de políticas de retenção no PowerShell](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. <span data-ttu-id="516ed-124">Para colocar um Bloqueio de Preservação na sua política, execute o cmdlet [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) com o nome da política e o parâmetro *RestrictiveRetention* definido como verdadeiro:</span><span class="sxs-lookup"><span data-stu-id="516ed-124">To place a Preservation Lock on your policy, run the [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet with the name of the policy, and the *RestrictiveRetention* parameter set to true:</span></span>
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    <span data-ttu-id="516ed-125">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="516ed-125">For example:</span></span>
    
    ![Parâmetro RestrictiveRetention no PowerShell](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     <span data-ttu-id="516ed-127">Quando solicitado, leia e reconheça as restrições que vêm com esta configuração digitando **S** :</span><span class="sxs-lookup"><span data-stu-id="516ed-127">When prompted, read and acknowledge the restrictions that come with this configuration by entering **Y** :</span></span>
    
   ![Solicitar confirmação que deseja bloquear uma política de retenção no PowerShell](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="516ed-129">O Bloqueio de Preservação agora está localizado na política de retenção.</span><span class="sxs-lookup"><span data-stu-id="516ed-129">A Preservation Lock is now placed on the policy.</span></span> <span data-ttu-id="516ed-130">Para confirmar, execute o `Get-RetentionCompliancePolicy` novamente, mas especifique o nome da política de retenção e exiba os parâmetros da política:</span><span class="sxs-lookup"><span data-stu-id="516ed-130">To confirm, run `Get-RetentionCompliancePolicy` again, but specify the policy name and display the policy parameters:</span></span>

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

<span data-ttu-id="516ed-131">Você deverá ver que o **RestrictiveRetention** está definido como **Verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="516ed-131">You should see **RestrictiveRetention** is set to **True**.</span></span> <span data-ttu-id="516ed-132">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="516ed-132">For example:</span></span>

![Bloquear a política com todos os parâmetros mostrados no PowerShell](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a><span data-ttu-id="516ed-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="516ed-134">See also</span></span>

[<span data-ttu-id="516ed-135">Recursos para ajudá-lo a atender aos requisitos normativos para o controle de informações e o gerenciamento de registros</span><span class="sxs-lookup"><span data-stu-id="516ed-135">Resources to help you meet regulatory requirements for information governance and records management</span></span>](retention-regulatory-requirements.md)
