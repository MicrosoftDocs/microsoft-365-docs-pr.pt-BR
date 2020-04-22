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
description: Você pode ativar o recurso de pesquisa de log de auditoria no centro de conformidade de & de segurança. Se você mudar de ideia, poderá desativar se estiver desligado a qualquer momento. Quando a pesquisa de log de auditoria está desativada, os administradores não podem pesquisar o log de auditoria do Microsoft 365 para atividades de usuário e administrador em sua organização.
ms.openlocfilehash: 6b5ea41ff9f40291e54f8cc9f6660d0f86367994
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633416"
---
# <a name="turn-audit-log-search-on-or-off"></a>Ativar ou desativar a pesquisa de log de auditoria

Você (ou outro administrador) deve ativar o log de auditoria antes de começar a pesquisar o log de auditoria. Quando a pesquisa de log de auditoria no centro de conformidade do & de segurança está ativada, a atividade do usuário e do administrador de sua organização é registrada no log de auditoria e mantida por 90 dias, e até um ano, dependendo da licença atribuída aos usuários. No entanto, sua organização pode ter motivos para não querer gravar e reter dados de log de auditoria. Nesses casos, um administrador global pode decidir desativar a auditoria no Microsoft 365.

> [!IMPORTANT]
> Se você desativar a pesquisa de log de auditoria no Microsoft 365, não será possível usar a API da atividade de gerenciamento do Office 365 ou o Azure Sentinel para acessar os dados de auditoria da sua organização. Desativando a pesquisa de log de auditoria seguindo as etapas deste artigo significa que nenhum resultado será retornado quando você pesquisar o log de auditoria usando o centro de conformidade de & de segurança ou quando executar o cmdlet **Search-UnifiedAuditLog** no PowerShell do Exchange Online. Isso também significa que os logs de auditoria não estarão disponíveis por meio da API de atividade de gerenciamento do Office 365 ou do Azure Sentinel.
  
## <a name="before-you-begin"></a>Antes de começar

- Você precisa receber a função de logs de auditoria no Exchange Online para ativar ou desativar a pesquisa de log de auditoria na sua organização do Microsoft 365. Por padrão, essa função é atribuída aos grupos de função gerenciamento de conformidade e gerenciamento da organização na página **permissões** no centro de administração do Exchange. Os administradores globais no Microsoft 365 são membros do grupo de funções Gerenciamento da organização no Exchange Online. 
    
    > [!NOTE]
    > Os usuários precisam receber permissões no Exchange Online para ativar ou desativar a pesquisa de log de auditoria. Se você atribuir aos usuários a função logs de auditoria na página **permissões** no centro de conformidade & segurança, não será possível ativar ou desativar a pesquisa de log de auditoria. Isso ocorre porque o cmdlet subjacente é um cmdlet do Exchange Online. 
    
- Para obter instruções passo a passo sobre como pesquisar o log de auditoria, consulte [Pesquisar o log de auditoria no centro de conformidade do & de segurança](search-the-audit-log-in-security-and-compliance.md). Para obter mais informações sobre a API de atividade de gerenciamento do Microsoft 365, confira [introdução às APIs de gerenciamento do microsoft 365](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).
    
## <a name="turn-on-audit-log-search"></a>Ativar pesquisa de log de auditoria

Você pode usar o centro de conformidade & segurança ou o PowerShell para ativar a pesquisa de log de auditoria no Microsoft 365. Pode levar várias horas após você ativar a pesquisa de log de auditoria antes de poder retornar os resultados ao pesquisar o log de auditoria. Você precisa receber a função de logs de auditoria no Exchange Online para ativar a pesquisa de log de auditoria.
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a>Usar o centro de conformidade de & de segurança para ativar a pesquisa de log de auditoria

1. No centro de conformidade & segurança, vá para pesquisa de **log de auditoria**de **pesquisa** \> .
    
   Uma faixa é exibida informando que a auditoria deve ser ativada para registrar a atividade do usuário e do administrador.

2. Clique em **ativar a auditoria**.
    
    ![Clique em ativar auditoria](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    A faixa é atualizada para dizer que o log de auditoria está sendo preparado e que você pode pesquisar a atividade de usuário e administrador em algumas horas.
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a>Usar o PowerShell para ativar a pesquisa de log de auditoria

1. [Conectar-se ao PowerShell do Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. Execute o seguinte comando do PowerShell para ativar a pesquisa de log de auditoria no Office 365.
    
    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    Uma mensagem é exibida dizendo que pode levar até 60 minutos para que a alteração entre em vigor.
  
## <a name="turn-off-audit-log-search"></a>Desativar pesquisa de log de auditoria

Você precisa usar o PowerShell remoto conectado à sua organização do Exchange Online para desativar a pesquisa de log de auditoria. Semelhante à ativação da pesquisa de log de auditoria, você precisa ter atribuído a função de logs de auditoria no Exchange Online para desativar a pesquisa de log de auditoria.
  
1. [Conectar-se ao PowerShell do Exchange Online ](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. Execute o seguinte comando do PowerShell para desativar a pesquisa de log de auditoria no Office 365.
    
    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. Após um tempo, verifique se a pesquisa de log de auditoria está desativada (desabilitada). Há duas maneiras de fazer isso:
    
    - No PowerShell, execute o seguinte comando:

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      O valor da `False` propriedade _UnifiedAuditLogIngestionEnabled_ indica que a pesquisa de log de auditoria está desativada. 
    
    - No centro de conformidade & segurança, vá para pesquisa de **log de auditoria**de **pesquisa** \> .
    
      Uma faixa é exibida dizendo que a auditoria deve ser ativada para registrar a atividade de usuário e administrador.