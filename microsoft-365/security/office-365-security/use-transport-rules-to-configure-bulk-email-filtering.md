---
title: Usar regras de fluxo de email para configurar a filtragem de email em massa no Exchange Online Protection
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a usar regras de fluxo de email no Exchange Online Protection para filtragem de email em massa.
ms.openlocfilehash: e354bb137e114a7d11bff97be0c1109becb54f84
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073558"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a>Usar regras de fluxo de email para configurar a filtragem de email em massa no Exchange Online Protection

Você pode definir filtros de conteúdo para toda a empresa para spam e email em massa usando as políticas padrão de filtro de conteúdo de spam. Confira [configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md) e [set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) em como definir as políticas de filtro de conteúdo. 
  
Se você quiser mais opções para filtrar mensagens em massa, você pode criar regras de fluxo de emails (também conhecidas como regras de transporte) para procurar padrões de texto ou frases freqüentemente encontradas em emails em massa. Qualquer mensagem que contenha essas características será marcada como spam. O uso dessas regras pode ajudar a reduzir a quantidade de emails em massa indesejados que sua organização recebe.

> [!IMPORTANT]
> Antes de criar as regras de fluxo de emails documentadas neste tópico, recomendamos que você leia primeiro [qual é a diferença entre lixo eletrônico e email em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md) e [valores de nível de reclamação em massa](bulk-complaint-level-values.md).<br> Os seguintes procedimentos marcam uma mensagem como spam para toda a sua organização. No entanto, você pode adicionar outra condição para aplicar essas regras somente a destinatários específicos em sua organização. Dessa forma, as configurações agressivas de filtragem de email em massa podem ser aplicadas a alguns usuários altamente direcionados, enquanto o restante de seus usuários (que recebem principalmente o email em massa que eles se inscreveram) não são afetados. 
  
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a>Criar uma regra de fluxo de emails para filtrar mensagens de email em massa com base em padrões de texto

1. No Centro de administração do Exchange (EAC), acesse **Fluxo de emails** \> **Regras**.
    
2. Clique em **Adicionar** ![ícone](../media/ITPro-EAC-AddIcon.gif) de adição e selecione **criar uma nova regra**.
    
3. Especifique um nome para a regra.
    
4. Clique em **Mais opções**. Em **aplicar esta regra se**, selecione **o assunto ou o** \> **assunto ou o corpo corresponde a esses padrões de texto**.
    
5. Na caixa de diálogo **especificar palavras ou expressões**, adicione, uma de cada vez, as seguintes expressões regulares que são normalmente encontradas em emails em massa e clique em **ok** quando tiver concluído: 
    
   - `If you are unable to view the content of this email\, please`
    
   - `\>(safe )?unsubscribe( here)?\</a\>`
    
   - `If you do not wish to receive further communications like this\, please`
    
   - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
    
   - `To stop receiving these+emails\:http\://`
    
   - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
    
   - `no longer (wish )?(to )?(be sent|receive) w+ email`
    
   - `If you are unable to view the content of this email\, please click here`
    
   - `To ensure you receive (your daily deals|our e-?mails)\, add`
    
   - `If you no longer wish to receive these emails`
    
   - `to change your (subscription preferences|preferences or unsubscribe)`
    
   - `click (here to|the) unsubscribe`
    
   A lista acima não é um conjunto completo de expressões regulares encontradas em emails em massa; é possível adicionar ou remover mais, conforme necessário. Entretanto, é um bom ponto de partida.<br>A pesquisa por palavras ou padrões de texto no assunto ou em outros campos de cabeçalho da mensagem ocorre *depois* que a mensagem foi decodificada a partir do método de codificação de transferência de conteúdo MIME usado para transmitir a mensagem binária entre os servidores SMTP no texto ASCII. Não é possível usar condições ou exceções para buscar os valores codificados brutos (tipicamente com base64) dos campos de cabeçalho assunto ou outros nas mensagens. 
    
6. Em **Execute a ação a seguir**, selecione **Modificar as propriedades da mensagem** \> **definir o SCL (nível de confiança de spam)**.
    
7. Na caixa de diálogo **especificar SCL**, defina o SCL como **5**, **6** ou **9** e clique em **ok**.
    
   Configurar o SCL como 5 ou 6 executa a ação **Spam**; configurar o SCL como 9 executa a ação **Spam de alta confiança**, conforme definido na política de filtro de conteúdo. O serviço executará a ação definida na política de filtro de conteúdo. A ação padrão é entregar a mensagem para a pasta lixo eletrônico dos destinatários, mas ações diferentes podem ser configuradas conforme descrito em [configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md).
    
   Se sua ação configurada for colocar em quarentena a mensagem em vez de enviá-la para a pasta lixo eletrônico dos destinatários, a mensagem será enviada para a quarentena do administrador como uma correspondência de regra de fluxo de email e não estará disponível na quarentena de spam do usuário final ou via usuário final notificações de spam. 
  
   Para saber mais sobre os valores de SCL do serviço, veja [Níveis de confiança de spam](spam-confidence-levels.md).
    
8. Salve a regra.
    
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a>Criar uma regra de fluxo de emails para filtrar mensagens de email em massa com base em frases

1. No EAC, vá para **Fluxo de emails** \> **Regras**.
    
2. Clique em **Adicionar** ![ícone](../media/ITPro-EAC-AddIcon.gif) de adição e selecione **criar uma nova regra**.
    
3. Especifique um nome para a regra.
    
4. Clique em **Mais opções**. Em **aplicar esta regra se**, selecione **o assunto ou o** \> **assunto ou o corpo da mensagem inclui qualquer uma destas palavras**.
    
5. Na caixa de diálogo **especificar palavras ou expressões**, adicione, uma de cada vez, as seguintes frases comuns encontradas em emails em massa e clique em **ok** quando tiver concluído: 
    
   - `to change your preferences or unsubscribe`
    
   - `Modify email preferences or unsubscribe`
    
   - `This is a promotional email`
    
   - `You are receiving this email because you requested a subscription`
    
   - `click here to unsubscribe`
    
   - `You have received this email because you are subscribed`
    
   - `If you no longer wish to receive our email newsletter`
    
   - `to unsubscribe from this newsletter`
    
   - `If you have trouble viewing this email`
    
   - `This is an advertisement`
    
   - `you would like to unsubscribe or change your`
    
   - `view this email as a webpage`
    
   - `You are receiving this email because you are subscribed`
    
   Essa lista não é um conjunto exaustivo de frases encontradas em emails em massa; é possível adicionar ou remover mais, conforme necessário. Entretanto, é um bom ponto de partida.
    
6. Em **Execute a ação a seguir**, selecione **Modificar as propriedades da mensagem** \> **definir o SCL (nível de confiança de spam)**.
    
7. Na caixa de diálogo **especificar SCL**, defina o SCL como **5**, **6** ou **9** e clique em **ok**.
    
   Configurar o SCL como 5 ou 6 executa a ação **Spam**; configurar o SCL como 9 executa a ação **Spam de alta confiança**, conforme definido na política de filtro de conteúdo. O serviço executará a ação definida na política de filtro de conteúdo. A ação padrão é entregar a mensagem para a pasta lixo eletrônico dos destinatários, mas ações diferentes podem ser configuradas conforme descrito em [configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md).
    
   Se sua ação configurada for colocar em quarentena a mensagem em vez de enviá-la para a pasta lixo eletrônico dos destinatários, a mensagem será enviada para a quarentena do administrador como uma correspondência de regra de fluxo de email e não estará disponível na quarentena de spam do usuário final ou via usuário final notificações de spam. 
  
   Para saber mais sobre os valores de SCL do serviço, veja [Níveis de confiança de spam](spam-confidence-levels.md).

8. Salve a regra.

## <a name="for-more-information"></a>Para obter mais informações

[Qual é a diferença entre lixo eletrônico e email em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md)

[Valores de nível de reclamação em massa](bulk-complaint-level-values.md)

[Configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md)

[Opções avançadas de filtragem de spam](advanced-spam-filtering-asf-options.md)
