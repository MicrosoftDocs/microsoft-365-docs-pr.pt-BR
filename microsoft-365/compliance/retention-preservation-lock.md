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
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a>Use o Bloqueio de Preservação para restringir as alterações para políticas de retenção e políticas de rótulo de retenção

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

O Bloqueio de Preservação trava uma política de retenção ou uma política de rótulo de retenção para que ninguém, incluindo um administrador global, possa desativar a política, excluir a política ou torná-la menos restritiva. Essa configuração pode ser necessária para atender aos requisitos regulatórios e ajudar a proteger contra administradores não autorizados.

Quando uma política de retenção estiver bloqueada:

- Ninguém pode desligá-lo
- Locais podem ser adicionados, mas não removidos
- Você pode estender um período de retenção, mas não reduzi-lo

Em resumo, uma política de retenção bloqueada pode ser aumentada ou estendida, mas não poderá ser reduzida ou desativada.
  
> [!IMPORTANT]
> Antes de bloquear uma política de retenção, é fundamental que você entenda o impacto e confirme se ela é necessária para a sua organização atender aos requisitos normativos. Por exemplo, pode ser necessário atender aos requisitos normativos. Os administradores não poderão desabilitar ou excluir uma política de retenção após a aplicação do bloqueio de preservação.

Configure o Bloqueio de Preservação após criar uma [política de retenção](create-retention-policies.md) ou uma política de rótulo de retenção que você [publicar](create-apply-retention-labels.md) ou [aplicar automaticamente](apply-retention-labels-automatically.md). 

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a>Como bloquear uma política de retenção ou uma política de rótulo de retenção

Você deve usar o Windows PowerShell se precisar usar o Bloqueio de Preservação. Como os administradores não podem desabilitar ou excluir uma política de retenção após a aplicação de um bloqueio de preservação, a habilitação desse recurso não está disponível na interface do usuário para proteger contra configurações acidentais.

Todas as políticas de retenção, com qualquer configuração, oferecem suporte ao Bloqueio de Preservação.

1. [Conectar-se ao PowerShell do Centro de Conformidade e Segurança](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Localize o nome da política que você deseja bloquear, executando o [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy). Por exemplo:
    
   ![Lista de políticas de retenção no PowerShell](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. Para colocar um Bloqueio de Preservação na sua política, execute o cmdlet [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) com o nome da política e o parâmetro *RestrictiveRetention* definido como verdadeiro:
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    Por exemplo:
    
    ![Parâmetro RestrictiveRetention no PowerShell](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     Quando solicitado, leia e reconheça as restrições que vêm com esta configuração digitando **S** :
    
   ![Solicitar confirmação que deseja bloquear uma política de retenção no PowerShell](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

O Bloqueio de Preservação agora está localizado na política de retenção. Para confirmar, execute o `Get-RetentionCompliancePolicy` novamente, mas especifique o nome da política de retenção e exiba os parâmetros da política:

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

Você deverá ver que o **RestrictiveRetention** está definido como **Verdadeiro**. Por exemplo:

![Bloquear a política com todos os parâmetros mostrados no PowerShell](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a>Confira também

[Recursos para ajudá-lo a atender aos requisitos normativos para o controle de informações e o gerenciamento de registros](retention-regulatory-requirements.md)
