---
title: Ativar ou desativar a auditoria
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
ms.custom: seo-marvel-apr2020
description: Como ativar ou desativar o recurso de pesquisa de log de auditoria no centro de conformidade do Microsoft 365 para habilitar ou desabilitar a capacidade dos administradores de pesquisar o log de auditoria.
ms.openlocfilehash: 091331a40a2ab6bf3c05bb289d49f63ab2dd2794
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657724"
---
# <a name="turn-auditing-on-or-off"></a>Ativar ou desativar a auditoria

O log de Auditoria é ativado por padrão para organizações empresariais Microsoft 365 e Office 365. Isto inclui organizações com assinaturas E3/G3 ou E5/G5. Quando a auditoria no centro de conformidade é ativeda, a atividade do usuário e do administrador da sua organização é registrada no log de auditoria e mantida por 90 dias e até um ano, dependendo da licença atribuída aos usuários. No entanto, sua organização pode ter motivos para não querer registrar e reter dados de log de auditoria. Nesses casos, um administrador global pode decidir desativar a auditoria no Microsoft 365.

> [!IMPORTANT]
> Se você desativar a auditoria no Microsoft 365, não poderá usar a API de Atividade de Gerenciamento Office 365 ou o Azure Sentinel para acessar dados de auditoria para sua organização. Desligar a auditoria seguindo as etapas deste artigo significa que nenhum resultado será retornado quando você pesquisar o log de auditoria usando o Centro de Conformidade do & de Segurança ou quando você executar o cmdlet **Search-UnifiedAuditLog** no Exchange Online PowerShell. Isso também significa que os logs de auditoria não estarão disponíveis por meio da API de Atividade de Gerenciamento Office 365 ou do Azure Sentinel.
  
## <a name="before-you-turn-auditing-on-or-off"></a>Antes de ativar ou desativar a auditoria

- Você precisa ter a função Logs de Auditoria Exchange Online ativar ou desativar a auditoria em sua Microsoft 365. Por padrão, essa função é atribuída aos grupos de  função Gerenciamento de Conformidade e Gerenciamento de Organização na página Permissões no Exchange de administração. Os administradores globais no Microsoft 365 são membros do grupo de função Gerenciamento da Organização no Exchange Online. 

    > [!NOTE]
    > Os usuários devem ter permissões atribuídas Exchange Online ativar ou desativar a auditoria. Se você atribuir aos usuários  a função Logs de Auditoria na página Permissões no Centro de Conformidade & Segurança, eles não poderão ativar ou desativar a auditoria. Isso porque o cmdlet subjacente é um cmdlet Exchange Online PowerShell. 

- Para obter instruções passo a passo sobre como pesquisar o log de auditoria, consulte Pesquisar o log de auditoria no Centro de Conformidade & [Segurança.](search-the-audit-log-in-security-and-compliance.md) Para obter mais informações sobre a API Microsoft 365 Atividade de Gerenciamento, consulte [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).

- Para verificar se a auditoria está 100%, você pode executar o seguinte comando Exchange Online PowerShell:

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    O valor da  `True` propriedade  _UnifiedAuditLogIngestionEnabled_ indica que a auditoria está ativa. 

## <a name="turn-on-auditing"></a>Ativar a auditoria

Se a auditoria não estiver Exchange Online PowerShell. Pode levar várias horas após ativar a auditoria antes de poder retornar resultados ao pesquisar o log de auditoria.
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a>Usar o centro de conformidade para ativar a auditoria

1. Acesse <https://compliance.microsoft.com> e entre.

2. No painel de navegação esquerdo do centro de conformidade Microsoft 365, clique em **Mostrar tudo** e clique em **Auditoria**.

   Se a auditoria não estiver 100% 100%, um banner será exibido solicitando que você inicie a gravação da atividade de usuário e administrador.

   ![Banner na página auditoria](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)

3. Clique no **banner Iniciar gravação do usuário e da atividade do** administrador.

   Pode levar até 60 minutos para que a alteração entre em vigor.

### <a name="use-powershell-to-turn-on-auditing"></a>Usar o PowerShell para ativar a auditoria

1. [Conectar-se ao PowerShell do Exchange Online ](/powershell/exchange/connect-to-exchange-online-powershell)

2. Execute o seguinte comando do PowerShell para ativar a auditoria no Office 365.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Uma mensagem é exibida dizendo que pode levar até 60 minutos para que a alteração entre em vigor.
  
## <a name="turn-off-auditing"></a>Desativar a auditoria

Você precisa usar o Exchange Online PowerShell para desativar a auditoria.
  
1. [Conectar-se ao PowerShell do Exchange Online ](/powershell/exchange/connect-to-exchange-online-powershell)

2. Execute o seguinte comando do PowerShell para desativar a auditoria.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Depois de um tempo, verifique se a auditoria está desativada (desabilitada). Há duas maneiras de fazer isso:

    - No Exchange Online PowerShell, execute o seguinte comando:

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      O valor da  `False`  _propriedade UnifiedAuditLogIngestionEnabled_ indica que a auditoria está desligada.

    - Vá para a **página Auditoria** no centro Microsoft 365 conformidade.

      Se a auditoria não estiver 100% 100%, um banner será exibido solicitando que você inicie a gravação da atividade de usuário e administrador.
