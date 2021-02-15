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
description: Como ativar ou desativar o recurso de pesquisa de log de auditoria no Centro de Conformidade e Segurança & para habilitar ou desabilitar a capacidade dos administradores de pesquisar o log de auditoria.
ms.openlocfilehash: 1f3da9671b9e5287d715a438a11b0a0eef164584
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976324"
---
# <a name="turn-audit-log-search-on-or-off"></a>Ativar ou desativar a pesquisa de log de auditoria

O log de Auditoria é ativado por padrão para organizações empresariais Microsoft 365 e Office 365. Isto inclui organizações com assinaturas E3/G3 ou E5/G5. Quando a pesquisa de log de auditoria no centro de conformidade está 2010, a atividade de usuários e administradores da sua organização é registrada no log de auditoria e retida por 90 dias e até um ano, dependendo da licença atribuída aos usuários. No entanto, sua organização pode ter motivos para não desejar registrar e reter dados de log de auditoria. Nesses casos, um administrador global pode optar por desativar a auditoria no Microsoft 365.

> [!IMPORTANT]
> Se você desativar a pesquisa de log de auditoria no Microsoft 365, não poderá usar a API da Atividade de Gerenciamento do Office 365 ou o Azure Sentinel para acessar os dados de auditoria da sua organização. Ao desligar a pesquisa de log de auditoria seguindo as etapas deste artigo, significa que nenhum resultado será retornado quando você pesquisar o log de auditoria usando o Centro de Conformidade do & de Segurança ou quando executar o cmdlet **Search-UnifiedAuditLog** no PowerShell do Exchange Online. Isso também significa que os logs de auditoria não estarão disponíveis por meio da API da Atividade de Gerenciamento do Office 365 ou do Azure Sentinel.
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a>Antes de ativar ou desativar a pesquisa de log de auditoria

- Você precisa ter a função Logs de Auditoria no Exchange Online para ativar ou desativar a pesquisa de log de auditoria em sua organização do Microsoft 365. Por padrão, essa função é atribuída aos grupos de função Gerenciamento de Conformidade e Gerenciamento da Organização na página **Permissões** do Centro de administração do Exchange. Os administradores globais no Microsoft 365 são membros do grupo de funções Gerenciamento da Organização no Exchange Online. 
    
    > [!NOTE]
    > Os usuários devem ter permissões no Exchange Online para ativar ou desativar a pesquisa de log de auditoria. Se você atribuir aos usuários  a função & Logs de Auditoria na página Permissões, no Centro de Conformidade e Segurança, eles não poderão ativar ou desativar a pesquisa de log de auditoria. Isso porque o cmdlet subjacente é um cmdlet do PowerShell do Exchange Online. 
    
- Para obter instruções passo a passo sobre como pesquisar o log de auditoria, consulte Pesquisar o log de auditoria no Centro de Conformidade e [& Segurança.](search-the-audit-log-in-security-and-compliance.md) Para saber mais sobre a API da Atividade de Gerenciamento do Microsoft 365, confira Começar a trabalhar com APIs de Gerenciamento do [Microsoft 365.](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)

- Para verificar se a pesquisa de log de auditoria está ativada, você pode executar o seguinte comando em Exchange Online PowerShell:

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    O valor da  `True` propriedade  _UnifiedAuditLogIngestionEnabled_ indica que a pesquisa de log de auditoria está acessível. 
    
## <a name="turn-on-audit-log-search"></a>Ativar a pesquisa de log de auditoria

Se a pesquisa de log de auditoria não estiver ativar a sua organização, você poderá agará-la no centro de conformidade ou usando o PowerShell do Exchange Online. Pode levar várias horas depois de ativar a pesquisa de log de auditoria antes de poder retornar resultados ao pesquisar o log de auditoria.
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a>Usar o centro de conformidade para ativar a pesquisa de log de auditoria

1. [Vá para o centro de conformidade](https://protection.office.com) e entre.

2. No centro de conformidade, vá para a **pesquisa**  >  **de log de Auditoria de Pesquisa.**

   Se a pesquisa de log de auditoria não estiver tiva para sua organização, uma faixa será exibida dizendo que a auditoria deve ser responsabilidade para registrar a atividade de usuários e administradores.

3. Clique **em Ativar auditoria.**

    ![Clique em Ativar auditoria](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    A faixa é atualizada para dizer que o log de auditoria está sendo preparado e que você pode pesquisar atividades de usuários e administradores em algumas horas.

### <a name="use-powershell-to-turn-on-audit-log-search"></a>Usar o PowerShell para ativar a pesquisa de log de auditoria

1. [Conectar-se ao PowerShell do Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. Execute o seguinte comando do PowerShell para ativar a pesquisa de log de auditoria no Office 365.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Uma mensagem é exibida dizendo que pode levar até 60 minutos para que a alteração entre em vigor.
  
## <a name="turn-off-audit-log-search"></a>Desativar a pesquisa de log de auditoria

Você precisa usar o PowerShell do Exchange Online para desativar a pesquisa de log de auditoria.
  
1. [Conectar-se ao PowerShell do Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. Execute o seguinte comando do PowerShell para desativar a pesquisa de log de auditoria.

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Após algum tempo, verifique se a pesquisa de log de auditoria está desativada (desabilitada). Há duas maneiras de fazer isso:

    - No PowerShell do Exchange Online, execute o seguinte comando:

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      O valor da  `False` propriedade  _UnifiedAuditLogIngestionEnabled_ indica que a pesquisa de log de auditoria está desligada. 

    - No centro [de conformidade,](https://protection.office.com)vá para a **pesquisa de** log de Auditoria \> **de Pesquisa.**

      Uma faixa é exibida dizendo que a auditoria deve ser tiva para registrar a atividade do usuário e do administrador.
