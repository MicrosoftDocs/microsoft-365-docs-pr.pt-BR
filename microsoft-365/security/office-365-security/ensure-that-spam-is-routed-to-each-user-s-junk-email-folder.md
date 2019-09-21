---
title: Garantir que o spam seja direcionado para a pasta Lixo Eletrônico de cada usuário
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/16/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a rotear spam para pastas de lixo eletrônico do usuário no Exchange Online Protection.
ms.openlocfilehash: dc37f2428e009f00a2d6d9dd15d5d2cd505f267a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072507"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Garantir que o spam seja direcionado para a pasta Lixo Eletrônico de cada usuário

> [!IMPORTANT]
> Este tópico aplica-se apenas aos clientes do proteção do Exchange Online (EOP) que hospedam caixas de correio no local em uma implantação híbrida. Os clientes do Exchange Online cujas caixas de correio são totalmente hospedadas no Office 365 não precisam executar esses comandos. 
  
A ação antispam padrão para clientes do EOP é mover as mensagens de spam para a pasta Lixo Eletrônico dos destinatários. Para que essa ação funcione com caixas de correio locais, você deve configurar as regras de fluxo de mensagens do Exchange (também conhecidas como regras de transporte) em seus servidores de borda ou Hub no local para detectar cabeçalhos de spam adicionados pelo EOP. Essas regras de fluxo de emails definem o nível de confiança de spam (SCL) usado pela propriedade SclJunkThreshold do cmdlet Set-OrganizationConfig para mover o spam para a pasta lixo eletrônico de cada caixa de correio. 
  
### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a>Para adicionar regras de fluxo de email para garantir que o spam seja movido para a pasta lixo eletrônico usando o Windows PowerShell

1. Acesse o Shell de Gerenciamento do Exchange para seu servidor do Exchange local. Para saber como abrir o Shell de Gerenciamento do Exchange em sua organização Exchange local, confira **Open the Shell**.
    
2. Execute o seguinte comando para encaminhar mensagens de spam filtradas por conteúdo para a pasta Lixo Eletrônico:
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    Em que _NameForRule_ é o nome da nova regra, por exemplo, JunkContentFilteredMail. 
    
3. Execute o seguinte comando para encaminhar mensagens marcadas como spam, antes da aplicação do filtro de conteúdo, para a pasta Lixo Eletrônico:
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    Em que _NameForRule_ é o nome da nova regra, por exemplo, JunkMailBeforeReachingContentFilter. 
    
4. Execute o seguinte comando para garantir que as mensagens de remetentes em uma lista de bloqueios na política de filtro de spam, como a lista de **bloqueios de remetente** , sejam encaminhadas para a pasta lixo eletrônico: 
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    Em que _NameForRule_ é o nome da nova regra, por exemplo, JunkMailInSenderBlockList. 
    
Se você não quiser usar a ação **mover mensagem para a pasta lixo eletrônico** , você pode escolher outra ação em suas políticas de filtro de conteúdo no centro de administração do Exchange. Para saber mais, confira [Configure your spam filter policies](configure-your-spam-filter-policies.md). Para obter mais informações sobre esses campos no cabeçalho da mensagem, consulte [anti-spam Message Headers](anti-spam-message-headers.md).
  

> [!TIP]
> Se você não quiser usar a ação **mover mensagem para a pasta lixo eletrônico** , você pode escolher outra ação em suas políticas de filtro de conteúdo no centro de administração do Exchange. Para saber mais, confira [Configure your spam filter policies](configure-your-spam-filter-policies.md). Para obter mais informações sobre esses campos no cabeçalho da mensagem, consulte [anti-spam Message Headers](anti-spam-message-headers.md).
> 
## <a name="see-also"></a>Confira também

[Cmdlet New-TransportRule](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)

