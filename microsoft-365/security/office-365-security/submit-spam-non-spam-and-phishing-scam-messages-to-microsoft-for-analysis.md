---
title: Enviar mensagens de spam, não spam e esquema de phishing à Microsoft para análise
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'Você e seus usuários podem enviar mensagens de spam falsas negativas e falsos positivos para a Microsoft para análise. '
ms.openlocfilehash: 7b53f74be78bc1203189815c6a7adf3337decd21
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2020
ms.locfileid: "42856864"
---
# <a name="submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis"></a>Enviar mensagens de spam, não spam e esquema de phishing à Microsoft para análise

Pode ser frustrante quando os usuários da sua organização recebem mensagens de lixo eletrônico (spam) ou de phishing scam em suas respectivas caixa de entrada ou se não recebem uma mensagem de email legítima porque estão marcados como lixo eletrônico. Estamos constantemente ajustando os nossos filtros de spam para serem mais precisos. Você e seus usuários podem ajudar nesse processo enviando mensagens de spam falso negativo e falso positivo para a Microsoft para análise. Um "falso negativo" é uma mensagem de spam que deveria ter sido, mas não foi identificada como spam. Um "falso positivo" é uma mensagem de email legítima que foi identificada incorretamente como spam.

> [!NOTE]
> Devido ao alto volume de envios que recebemos, talvez não seja possível atender a todas as solicitações para análise.

Os administradores podem enviar emails, URLs e anexos para a Microsoft para análise. Consulte [envios de administradores no Office 365 ATP](admin-submission.md).

## <a name="submit-junk-or-phishing-messages-that-passed-through-the-spam-filters"></a>Enviar mensagens de lixo eletrônico ou phishing que passaram pelos filtros de spam

Se você receber uma mensagem que passou pelos filtros de spam que devem ser classificados como lixo eletrônico ou golpes de phishing, você pode enviar a mensagem "falso negativo" para a análise de spam da Microsoft e as equipes de análise de phishing da Microsoft, conforme apropriado. Os analistas revisarão a mensagem e a adicionarão aos filtros de todo o serviço se atenderem aos critérios de classificação.

Para obter mais configurações de spam que se apliquem a toda a organização, consulte [Bloquear email spam com o filtro de spam do Office 365 para evitar problemas falsos negativos](reduce-spam-email.md). Este artigo contém dicas para ajudar a evitar falsos negativos.

Você pode enviar mensagens de lixo eletrônico das seguintes maneiras:

- Para Outlook e Outlook nos usuários da Web, use o suplemento de mensagem de relatório para o Microsoft Outlook. Para obter informações sobre como instalar e usar essa ferramenta, consulte [habilitar o suplemento de mensagem de relatório](enable-the-report-message-add-in.md).

- Você também pode usar o email para enviar mensagens à Microsoft que devem ser classificadas como spam ou golpes de phishing, conforme descrito no procedimento a seguir.

### <a name="use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft"></a>Usar o email para enviar mensagens de lixo eletrônico (spam) ou golpes de phishing para a Microsoft

Para enviar uma mensagem de spam ou golpe de phishing à Microsoft:

1. Criar uma mensagem de email em branco.

2. Endereçar a mensagem para a equipe da Microsoft que revisa mensagens, da seguinte maneira:

   - Para mensagens de lixo eletrônico: junk@office365.microsoft.com

   - Para mensagens de golpes de phishing: phish@office365.microsoft.com

3. Copie e cole a mensagem de spam ou golpe de phishing na nova mensagem como um anexo.

   > [!NOTE]
   > • Você pode anexar várias mensagens na nova mensagem. Certifique-se de que todas as mensagens são do mesmo tipo: mensagens golpes de phishing ou mensagens de lixo eletrônico. <br/><br/>• Deixe o corpo da nova mensagem vazio. <br/><br/>• Use formatos. msg (formato padrão do Outlook) ou. eml (o Outlook no formato da Web padrão) para as mensagens anexadas.

4. Clique em **Enviar**.

## <a name="submit-messages-that-were-tagged-as-junk-but-should-have-been-allowed-through"></a>Envie mensagens que foram marcadas como lixo eletrônico, mas deveriam ter sido permitidas

Se uma mensagem foi identificada incorretamente como lixo eletrônico, você pode enviar a mensagem "falso positivo" para a equipe de análise de spam da Microsoft. Os analistas irão avaliar e analisar a mensagem. Dependendo dos resultados da análise, as regras de filtro de conteúdo de spam de todo o serviço podem ser ajustadas para permitir a mensagem.
  
Os administradores podem revisar mais informações de configuração de spam que se aplicam a uma organização inteira. Veja [como ajudar a garantir que uma mensagem não seja marcada como spam](prevent-email-from-being-marked-as-spam.md). Essas informações são úteis se você tiver controle de nível de administrador e quiser impedir falsos positivos.
  
Você pode enviar mensagens que não são spam das seguintes maneiras:

- Se você usar a ação **mover mensagem para a pasta lixo eletrônico** ao configurar seus filtros de conteúdo (essa é a ação padrão), os usuários poderão liberar mensagens falsas falsas em seus Outlook ou Outlook na Web pasta lixo eletrônico (anteriormente conhecida como Outlook Web App).

  - Os usuários do Outlook podem liberar mensagens falsas, usando a opção de menu **não é lixo eletrônico** clique. No entanto, eles devem enviar a mensagem para a Microsoft por email, conforme mostrado no procedimento neste artigo.

  - Os usuários do Outlook na Web podem liberar mensagens falsas e enviá-las para a Microsoft para análise usando a ação **Marcar como não é lixo eletrônico** . Para obter mais informações sobre como fazer isso, confira [relatar spam e golpes de phishing no Outlook na Web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md).

- Se você usar a ação **mensagem em quarentena** em vez da ação **mover mensagem para a pasta lixo eletrônico** ao configurar seus filtros de conteúdo:

  - Os administradores podem liberar a mensagens em quarentena e relatá-las como falsos positivos no Centro de Administração do Exchange. Para obter mais informações, consulte [gerenciar mensagens em quarentena e arquivos como um administrador no Office 365](manage-quarantined-messages-and-files.md).

  - Os usuários podem liberar suas próprias mensagens em quarentena de spam e relatá-las como falsos positivos por meio dos seguintes canais:

  - Interface do usuário do EAC (Centro de administração do Exchange). Para obter mais informações, consulte [Find and Release Quarantined Messages (End Users)](find-and-release-quarantined-messages-as-a-user.md).

  - Mensagens de notificação de spam de usuário final (se estiverem habilitadas pelo administrador).

- Também é possível usar o email para enviar à Microsoft as mensagens que não deveriam ser classificadas como spam. Ao fazer isso, certifique-se de usar as etapas do procedimento a seguir.

### <a name="use-email-to-submit-false-positive-messages"></a>Envie por email as mensagens de falsos positivos

Use o mesmo procedimento descrito na seção [usar email para enviar lixo eletrônico (spam) ou mensagens de golpes de phishing para a Microsoft](#use-email-to-submit-junk-spam-or-phishing-scam-messages-to-microsoft) , mas envie a mensagem para o not_junk@office365.microsoft.com.

## <a name="spam-evaluation-and-rules-deployment"></a>Avaliação de spam e implantação de regras

A equipe de análise de spam examina as mensagens enviadas e ajusta os filtros de spam para evitar o lixo eletrônico futuro. Como resultado, os filtros de spam do Office 365 areconstantly refinados. Todos os itens apresentados são avaliados ao nível de toda a rede. Envios falsos positivos são examinados e avaliados para possível ajuste de regra para permitir mensagens futuras por meio de filtros de spam. Portanto, notificar o serviço de falsos positivos e também falsos negativos (spam não filtrado) é vantajoso para você e todos os clientes que usam a rede global. A equipe de spam analisa indicadores em cada mensagem enviada, como o seguinte:

- Endereço De

- Endereço IP do envio

- Palavras-chave

- Frases

- Frequência da transmissão

- Outras tendências e padrões

Depois de examinar essas informações, a equipe de spam pode fazer alterações nas camadas de filtragem de spam do serviço. Para obter mais informações sobre a equipe de spam, você pode assistir ao seguinte vídeo somente em inglês:

[Vídeo da equipe de spam do Microsoft Exchange](https://youtu.be/-TpX_-GMC7o?hd=1)

A avaliação de spam é um processo contínuo que se aplica independentemente do idioma ou conjunto de caracteres de origem. Como uma mensagem de spam pode ser vaga ou mesmo falta de texto no corpo da mensagem ou assunto, a equipe de spam se baseia em outras características da mensagem para executar a filtragem. Isso significa que, após a equipe de spam marcar uma determinada mensagem como spam e fazer as alterações necessárias na sua base de regra, essa mensagem ficará bloqueada no futuro até que suas características sejam modificadas o suficiente para evitar os nossos filtros. Novas regras de spam são implantadas de forma contínua. Os intervalos de tempo para regras em envios individuais variam de acordo com a quantidade e a qualidade dos envios. Como as novas regras de spam são definidas globalmente para todos os clientes, nem todos os envios de spam individuais resultarão em uma nova regra de spam.

## <a name="for-more-information"></a>Para obter mais informações

[Proteção antispam e antimalware](anti-spam-and-anti-malware-protection.md)
  
[Como ajudar a garantir que uma mensagem não é marcada como spam](prevent-email-from-being-marked-as-spam.md)
  
[Bloquear spam de email com o filtro de spam do Office 365 para evitar problemas de falsos negativos](reduce-spam-email.md)
  

[Bloquear spam de email com o filtro de spam do Office 365 para evitar problemas de falsos negativos](reduce-spam-email.md)
