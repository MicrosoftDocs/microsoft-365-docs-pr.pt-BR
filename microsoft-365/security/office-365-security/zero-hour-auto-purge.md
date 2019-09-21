---
title: Limpeza automática zero hora – proteção contra spam e malware
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/11/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: A limpeza automática de zero horas (ZAP) é um recurso de proteção de email que detecta mensagens com spam ou malware que já foram entregues às caixas de entrada dos seus usuários e renderiza o conteúdo mal-intencionado inofensivo. Como o ZAP faz isso depende do tipo de conteúdo mal-intencionado detectado.
ms.openlocfilehash: f43826614def99f8807d8777f128d5bc66f7b46a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073346"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>Limpeza automática zero hora – proteção contra spam e malware

## <a name="overview"></a>Visão geral

A limpeza automática de zero horas (ZAP) é um recurso de proteção de email que detecta mensagens com phishing, spam ou malware que já foram entregues às caixas de entrada dos seus usuários e renderiza o conteúdo mal-intencionado inofensivo. Como o ZAP depende do tipo de conteúdo mal-intencionado detectado; os emails podem ser zapped devido a conteúdo, URLs ou anexos de email.
  
O ZAP está disponível com a proteção do Exchange Online padrão incluída em qualquer assinatura do Office 365 que contenha caixas de correio do Exchange Online.

O ZAP é ativado por padrão, mas as seguintes condições devem ser atendidas:
  
- A **ação de spam** é definida para **mover a mensagem para a pasta lixo eletrônico**. Você também pode criar uma nova política de filtro de spam que se aplique somente a um conjunto de usuários se não quiser que todas as caixas de correio sejam filtradas por ZAP.

- Os usuários mantiveram suas configurações de lixo eletrônico padrão e não desativaram a proteção de lixo eletrônico. (Consulte [alterar o nível de proteção no filtro de lixo eletrônico](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) para obter detalhes sobre as opções do usuário no Outlook.)
  
## <a name="how-zap-works"></a>Como o ZAP funciona

O Office 365 atualiza as assinaturas de malware e mecanismo antispam em tempo real diariamente. No entanto, os usuários ainda podem obter mensagens mal-intencionadas entregues às suas caixas de entrada por vários motivos, incluindo se o conteúdo é enarmado depois de ser entregue aos usuários. O ZAP aborda isso ao monitorar atualizações continuamente nas assinaturas de spam e malware do Office 365. ZAP pode localizar e remover mensagens entregues anteriormente que já estão nas caixas de entrada dos usuários.

A ação ZAP é transparente para o usuário da caixa de correio; Eles não são notificados quando uma mensagem de email é movida. A mensagem não deve ser mais antiga que 2 dias.
  
As listas de permissões, [as regras de fluxo de emails](https://go.microsoft.com/fwlink/p/?LinkId=722755) (também conhecidas como regras de transporte) e as regras de usuário final ou filtros adicionais têm precedência sobre o zap.

### <a name="malware-zap"></a>ZAP de malware

Para malware recém detectado, o ZAP remove anexos de mensagens de email, deixando o corpo da mensagem na caixa de correio do usuário. Os anexos são removidos independentemente do status de leitura do email.

O malware ZAP é habilitado por padrão na política de malware. Você pode desabilitar o ZAP de malware usando o parâmetro *ZapEnabled* no cmdlet [set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) no PowerShell do Exchange Online ou do Exchange Online Protection.

### <a name="phish-zap"></a>Phish de phishing

Para email que é identificado como Phish após a entrega, o ZAP realiza a ação de acordo com a política de spam pela qual o usuário é coberto. Se a ação de phishing de política estiver definida para executar uma ação em um email (redirecionar, excluir, quarentena, mover para lixo eletrônico), ZAP moverá a mensagem para a pasta lixo eletrônico da caixa de entrada do usuário, independentemente do status de leitura do email. Se a ação de phishing de política não estiver definida como executar ação (Adicionar cabeçalho X, modificar assunto, sem ação), ZAP não executará ações no email. Saiba mais sobre como [configurar suas políticas de filtro de spam](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) aqui.

O phishing ZAP está habilitado por padrão na política de spam. Você pode desabilitar o Phish ZAP usando o parâmetro *ZapEnabled* no cmdlet [set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) no PowerShell do Exchange Online ou do Exchange Online Protection.

### <a name="spam-zap"></a>ZAP de spam

Para email que é identificado como spam após a entrega, o ZAP realiza a ação de acordo com a política de spam pela qual o usuário é coberto. Se a ação de spam de política estiver definida como executar uma ação em um email (redirecionar, excluir, quarentena, mover para lixo eletrônico), ZAP moverá a mensagem para a pasta lixo eletrônico da caixa de entrada do usuário, se a mensagem for não lida. Se a ação de spam de política não estiver definida como executar ação (Adicionar cabeçalho X, modificar assunto, sem ação), ZAP não executará ações no email. Saiba mais sobre como [configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md) aqui.

O ZAP de spam está habilitado por padrão na política de spam. Você pode desabilitar o ZAP de spam usando o parâmetro *ZapEnabled* do cmdlet [set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) no PowerShell do Exchange Online ou do Exchange Online Protection.

> [!NOTE]
> O parâmetro *ZapEnabled* no cmdlet **set-HostedContentFilterPolicy** desabilita ou habilita a impressão ZAP e o spam zap para a política. Você não pode habilitar ou desabilitar o zap de phishing e o spam ZAP dentro da mesma política.

## <a name="how-to-see-if-zap-moved-your-message"></a>Como ver se ZAP moveu a mensagem

Para determinar se o ZAP moveu a mensagem, você pode usar o [relatório de status de proteção contra ameaças](../../compliance/view-email-security-reports.md#threat-protection-status-report) ou o [Explorador de ameaças (e detecções em tempo real)](threat-explorer.md).

## <a name="disable-zap"></a>Desabilitar ZAP

Para se conectar ao Exchange Online PowerShell, confira [Conectar ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554). Para se conectar ao PowerShell do Exchange Online Protection, confira [conectar-se ao PowerShell do Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=627290).

### <a name="disable-malware-zap"></a>Desabilitar o malware ZAP * *

Este exemplo desabilita o ZAP na política de filtro de malware chamada "Test".

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).

### <a name="disable-phish-zap-and-spam-zap"></a>Desabilitar o phishing ZAP e o spam ZAP

Este exemplo desabilita o phishing ZAP e o spam ZAP na política de filtro de conteúdo chamada "Test".

```Powershell
Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758).

## <a name="faq"></a>Perguntas frequentes

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>O que acontece se uma mensagem legítima for movida para a pasta lixo eletrônico?
  
Você deve seguir o processo de relatório normal para [falsos positivos](../../compliance/prevent-email-from-being-marked-as-spam.md). A única razão pela qual a mensagem seria movida da caixa de entrada para a pasta lixo eletrônico seria porque o serviço determinou que a mensagem era spam ou mal-intencionada.
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>E se eu usar a quarentena do Office 365 em vez da pasta lixo eletrônico?
  
ZAP não move mensagens para a quarentena da caixa de entrada neste momento.
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>E se eu tiver uma regra de fluxo de emails personalizada (regra bloquear/permitir)?
  
Regras criadas por administradores (regras de fluxo de emails) ou regras de bloqueio e permissão têm precedência. Essas mensagens são excluídas dos critérios de recurso para que o fluxo de email siga a ação de regra (regra bloquear/permitir).

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a>E se uma mensagem for movida para outra pasta (por exemplo, regra de caixa de entrada)?

ZAP ainda funciona nesse caso, a menos que a mensagem tenha sido excluída ou esteja em lixo eletrônico.

## <a name="related-topics"></a>Tópicos Relacionados

[Proteção anti-spam de emails do Office 365](anti-spam-protection.md)
  
[Bloquear spam de email com o filtro de spam do Office 365 para evitar problemas de falsos negativos](reduce-spam-email.md)
