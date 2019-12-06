---
title: Evitar caracteres inválidos nas regras e política de filtro de spam
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/24/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Fornece ajuda para os administradores que têm caracteres inválidos na configuração antispam e estão em problemas ao tentar usar o centro de conformidade &amp; de segurança.
ms.openlocfilehash: 5e6fa97a3f325b6fc6fdc449ba4a61282f67b644
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39866713"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a>Evitar caracteres inválidos em suas regras de filtro de spam e política de filtro de spam 

Anteriormente, os administradores do Office 365 configuram e configuraram regras de filtro de spam e a política de filtro de spam usando o centro de administração do Exchange (Eat). Agora, use o centro de &amp; conformidade de segurança para gerenciar a configuração antispam. Os seguintes caracteres foram suportados no Eat, mas não têm suporte para uso no centro de &amp; conformidade de segurança.  

**Caracteres inválidos:**
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

Se suas regras de filtro de spam ou sua política de filtro de spam contiver qualquer um dos caracteres inválidos, você poderá encontrar qualquer um ou todos esses problemas:
- Você pode não conseguir encontrar a política ou as regras no centro de &amp; conformidade de segurança.
- Você pode receber erros ao tentar obter as regras ou política usando o Windows PowerShell.
- Você pode achar que a política ou as configurações não são executadas ou executadas conforme o esperado.

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a>Remover os caracteres inválidos da política e regras de filtro de spam

Depois de identificar a política e as regras que contêm caracteres inválidos, você pode alterar os nomes usando os cmdlets do Windows PowerShell. 

1. [Conecte-se ao Exchange Online usando o PowerShell remoto](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).
    
2. Para alterar o nome da política de filtro de spam, execute o cmdlet Set-HostedContentFilterPolicy da seguinte maneira:
    
    ```powershell
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. Para alterar o nome de uma regra de filtro de spam, execute o cmdlet Set-HostedContentFilterRule da seguinte maneira:
    
    ```powershell
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a>Para saber mais

[Gerenciamento de ameaças no centro &amp; de conformidade de segurança](protect-against-threats.md)
  
[Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy)

[Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule)
