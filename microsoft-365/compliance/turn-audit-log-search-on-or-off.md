---
title: Ativar ou desativar a pesquisa de log de auditoria
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
description: Como ativar ou desativar o recurso de pesquisa de log de auditoria no Centro de Conformidade & segurança para habilitar ou desabilitar a capacidade dos administradores de pesquisar o log de auditoria.
ms.openlocfilehash: aecd1d47592b9a5e2f134b1d9db9ff203b815b18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919277"
---
# <a name="turn-audit-log-search-on-or-off"></a>Ativar ou desativar a pesquisa de log de auditoria

O log de Auditoria é ativado por padrão para organizações empresariais Microsoft 365 e Office 365. Isto inclui organizações com assinaturas E3/G3 ou E5/G5. Quando a pesquisa de log de auditoria no centro de conformidade é ativeda, a atividade do usuário e do administrador da sua organização é registrada no log de auditoria e mantida por 90 dias e até um ano, dependendo da licença atribuída aos usuários. No entanto, sua organização pode ter motivos para não querer registrar e reter dados de log de auditoria. Nesses casos, um administrador global pode decidir desativar a auditoria no Microsoft 365.

> [!IMPORTANT]
> Se você desativar a pesquisa de log de auditoria no Microsoft 365, não poderá usar a API de Atividade de Gerenciamento do Office 365 ou o Azure Sentinel para acessar dados de auditoria para sua organização. Desligar a pesquisa de log de auditoria seguindo as etapas deste artigo significa que nenhum resultado será retornado quando você pesquisar o log de auditoria usando o Centro de Conformidade do & de Segurança ou quando você executar o cmdlet **Search-UnifiedAuditLog** no PowerShell do Exchange Online. Isso também significa que os logs de auditoria não estarão disponíveis por meio da API de Atividade de Gerenciamento do Office 365 ou do Azure Sentinel.
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a>Antes de ativar ou desativar a pesquisa de log de auditoria

- Você precisa ter a função Logs de Auditoria no Exchange Online para ativar ou desativar a pesquisa de log de auditoria em sua organização do Microsoft 365. Por padrão, essa função é atribuída aos grupos de  função Gerenciamento de Conformidade e Gerenciamento de Organização na página Permissões no Centro de administração do Exchange. Os administradores globais no Microsoft 365 são membros do grupo de função Gerenciamento da Organização no Exchange Online. 
    
    > [!NOTE]
    > Os usuários devem ter permissões atribuídas no Exchange Online para ativar ou desativar a pesquisa de log de auditoria. Se você atribuir aos usuários  a função & Logs de Auditoria na página Permissões no Centro de Conformidade e Segurança, eles não poderão ativar ou desativar a pesquisa de log de auditoria. Isso porque o cmdlet subjacente é um cmdlet do PowerShell do Exchange Online. 
    
- Para obter instruções passo a passo sobre como pesquisar o log de auditoria, consulte Pesquisar o log de auditoria no Centro de Conformidade & [Segurança.](search-the-audit-log-in-security-and-compliance.md) Para obter mais informações sobre a API de Atividade de Gerenciamento do Microsoft 365, consulte [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).

- Para verificar se a pesquisa de log de auditoria está ativada, você pode executar o seguinte comando em Exchange Online PowerShell:

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    O valor da  `True` propriedade  _UnifiedAuditLogIngestionEnabled_ indica que a pesquisa de log de auditoria está ativa. 
    
## <a name="turn-on-audit-log-search"></a>Ativar a pesquisa de log de auditoria

Se a pesquisa de log de auditoria não estiver 100% 100% 100% 2016, você poderá a ativar no centro de conformidade ou usando o PowerShell do Exchange Online. Pode levar várias horas depois de ativar a pesquisa de log de auditoria antes de poder retornar resultados ao pesquisar o log de auditoria.
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a>Usar o centro de conformidade para ativar a pesquisa de log de auditoria

1. [Vá para o centro de conformidade](https://protection.office.com) e entre.

2. No centro de conformidade, vá para **Pesquisa**  >  **pesquisa de log de auditoria.**

   Se a pesquisa de log de auditoria não estiver 100% 100%, será exibida uma faixa dizendo que a auditoria precisa ser 1ada para registrar a atividade do usuário e do administrador.

3. Clique **em Ativar auditoria**.

    ![Clique em Ativar auditoria](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    O banner é atualizado para dizer que o log de auditoria está sendo preparado e que você pode pesquisar atividades de usuário e administrador em algumas horas.

### <a name="use-powershell-to-turn-on-audit-log-search"></a>Usar o PowerShell para ativar a pesquisa de log de auditoria

1. [Conectar-se ao PowerShell do Exchange Online ](/powershell/exchange/connect-to-exchange-online-powershell)

2. Execute o seguinte comando do PowerShell para ativar a pesquisa de log de auditoria no Office 365.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Uma mensagem é exibida dizendo que pode levar até 60 minutos para que a alteração entre em vigor.
  
## <a name="turn-off-audit-log-search"></a>Desativar a pesquisa de log de auditoria

Você precisa usar o PowerShell do Exchange Online para desativar a pesquisa de log de auditoria.
  
1. [Conectar-se ao PowerShell do Exchange Online ](/powershell/exchange/connect-to-exchange-online-powershell)

2. Execute o seguinte comando do PowerShell para desativar a pesquisa de log de auditoria.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Depois de um tempo, verifique se a pesquisa de log de auditoria está desativada (desabilitada). Há duas maneiras de fazer isso:

    - No PowerShell do Exchange Online, execute o seguinte comando:

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      O valor da  `False` propriedade  _UnifiedAuditLogIngestionEnabled_ indica que a pesquisa de log de auditoria está desligada. 

    - No centro [de conformidade,](https://protection.office.com)vá para **Pesquisa** \> **pesquisa de log de auditoria.**

      Uma faixa é exibida dizendo que a auditoria precisa ser 1ada para registrar a atividade do usuário e do administrador.