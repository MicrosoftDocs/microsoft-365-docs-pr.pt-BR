---
title: ZAP (Limpeza Automática Zero Hora)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre como a ZAP (limpeza automática zero hora) pode mover retroativamente as mensagens entregues em uma caixa de correio do Exchange Online para a pasta Lixo Eletrônico ou quarentena que são retroativamente encontradas como spam ou phishing.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5fd41cf45ad2a49d74684ae3e20dded5c1b8f034
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287300"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>ZAP (Limpeza Automática Zero Hora) no Exchange Online

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a>Recursos básicos da ZAP

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online, a ZAP (Limpeza Automática Zero Hora) é um recurso de proteção de email que detecta e limpa retroativamente mensagens mal-intencionadas de phishing, spam ou malware que já foram entregues às caixas de correio do Exchange Online.

A ZAP não funciona em ambientes autônomos do Exchange Online Protection (EOP) que protegem caixas de correio locais do Exchange.

## <a name="how-zap-works"></a>Como a ZAP funciona

As assinaturas de spam e malware são atualizadas no serviço em tempo real diariamente. No entanto, os usuários ainda podem receber mensagens mal-intencionadas por vários motivos, incluindo se o conteúdo é endossado após ser entregue aos usuários. A ZAP resolve esse problema monitorando continuamente as atualizações das assinaturas de spam e malware no serviço. A ZAP pode encontrar e remover mensagens que já estão na caixa de correio de um usuário.

A ação zap é perfeita para o usuário; eles não serão notificados se uma mensagem for detectada e movida.

[Listas de remetentes seguros,](create-safe-sender-lists-in-office-365.md)regras de fluxo de emails (também conhecidas como regras de transporte), regras de Caixa de Entrada ou filtros adicionais têm precedência sobre a ZAP. Semelhante ao que acontece no fluxo de emails, isso significa que, mesmo que o serviço determine que a mensagem entregue precisa da ZAP, a mensagem não é agida devido à configuração de remententes seguros. Esse é outro motivo para ter cuidado com a configuração de mensagens para ignorar a filtragem.

### <a name="malware-zap"></a>Malware ZAP

Para **mensagens lidas ou não lidas** que contêm malware após a entrega, a ZAP coloca em quarentena a mensagem que contém o anexo de malware. Somente os administradores podem exibir e gerenciar mensagens de malware da quarentena.

A ZAP de malware é habilitada por padrão em políticas anti-malware. Para obter mais informações, [consulte Configurar políticas anti-malware no EOP.](configure-anti-malware-policies.md)

### <a name="phish-zap"></a>ZAP de phishing

Para  mensagens lidas ou não lidas que são identificadas como phishing após a entrega, o resultado da ZAP depende da ação configurada para um veredito de filtragem de email de **phishing** na política anti-spam aplicável. As ações de veredito de filtragem disponíveis para phishing e seus possíveis resultados da ZAP são descritas na lista a seguir:

- **Adicione X-Header**, **coloque a linha de assunto com texto:** a ZAP não faz nada com a mensagem.

- **Mover mensagem para** Lixo Eletrônico: a ZAP move a mensagem para a pasta Lixo Eletrônico, desde que a regra de lixo eletrônico seja habilitada na caixa de correio (ela é habilitada por padrão). Para obter mais informações, consulte [Definir configurações de lixo eletrônico em caixas de correio do Exchange Online no Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Redirecionar mensagem para endereço de email**, Excluir **mensagem**, Mensagem **de quarentena:** ZAP coloca a mensagem em quarentena.

Por padrão, a ZAP de phishing está habilitada em políticas anti-spam, e a ação padrão para o veredito de filtragem de email de phishing é a mensagem de **quarentena,** o que significa que a ZAP de **phishing** coloca a mensagem em quarentena por padrão.

Para obter mais informações sobre como configurar vereditos de filtragem de spam, consulte Configurar políticas [anti-spam no Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="spam-zap"></a>Spam ZAP

Para **mensagens não** lidas identificadas como spam após a entrega, o resultado da ZAP depende da ação configurada para o veredito de filtragem de **spam** na política anti-spam aplicável. As ações de veredito de filtragem disponíveis para spam e seus possíveis resultados da ZAP são descritas na lista a seguir:

- **Adicione X-Header**, **coloque a linha de assunto com texto:** a ZAP não faz nada com a mensagem.

- **Mover mensagem para** Lixo Eletrônico: a ZAP move a mensagem para a pasta Lixo Eletrônico, desde que a regra de lixo eletrônico seja habilitada na caixa de correio (ela é habilitada por padrão). Para obter mais informações, consulte [Definir configurações de lixo eletrônico em caixas de correio do Exchange Online no Microsoft 365.](configure-junk-email-settings-on-exo-mailboxes.md)

- **Redirecionar mensagem para endereço de email**, Excluir **mensagem**, Mensagem **de quarentena:** ZAP coloca a mensagem em quarentena. Os usuários finais podem exibir e gerenciar suas próprias mensagens em quarentena de spam.

Por padrão, a ZAP de spam é habilitada em políticas anti-spam, e a ação padrão  para o veredito de filtragem de **spam** é Mover mensagem para a pasta Lixo **Eletrônico,** o que significa que a ZAP de spam move as mensagens não lidas para a pasta Lixo Eletrônico por padrão.

Para obter mais informações sobre como configurar vereditos de filtragem de spam, consulte Configurar políticas [anti-spam no Microsoft 365.](configure-your-spam-filter-policies.md)

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a>Considerações da ZAP para o Microsoft Defender para Office 365

A ZAP não colocará em quarentena [](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) qualquer mensagem que está no processo de verificação de Entrega Dinâmica em Anexos Seguros ou em que a filtragem de malware do EOP já substituiu o anexo pelo arquivo de Text.txtalerta **de malware.** Se um sinal de phishing ou spam for recebido para esses tipos de mensagens e o veredito de filtragem na política anti-spam estiver definido para tomar alguma providência na mensagem (Mover para Lixo Eletrônico, Redirecionar, Excluir ou Quarentena), a ZAP assumirá como padrão uma ação "Mover para Lixo Eletrônico".

## <a name="how-to-see-if-zap-moved-your-message"></a>Como ver se a ZAP moveu sua mensagem

Para determinar se a ZAP moveu sua mensagem, você pode usar o relatório [de Status](view-email-security-reports.md#threat-protection-status-report) de Proteção contra Ameaças ou o Explorador de Ameaças [(e detecções](threat-explorer.md)em tempo real). Observe que, como uma ação do sistema, a ZAP não é registrada nos logs de auditoria de caixa de correio do Exchange.

## <a name="zap-faq"></a>Perguntas frequentes sobre a ZAP

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>O que acontece se uma mensagem legítima for movida para a pasta Lixo Eletrônico?

Você deve seguir o processo de relatório normal [para falsos positivos.](report-junk-email-messages-to-microsoft.md) A única razão pela qual a mensagem seria movida da Caixa de Entrada para a pasta Lixo Eletrônico seria porque o serviço determinou que a mensagem era spam ou mal-intencionada.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>E se eu usar a pasta Quarentena em vez da pasta Lixo Eletrônico?

A ZAP tomará medidas em uma mensagem com base na configuração de suas políticas anti-spam, conforme descrito anteriormente neste artigo.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>E se eu estiver usando remetentes seguros, regras de fluxo de emails ou listas de remetentes permitidos/bloqueados?

Os envios seguros, as regras de fluxo de emails ou o bloqueio e permitem que as configurações organizacionais precedam. Essas mensagens são excluídas da ZAP, pois o serviço está fazendo o que você configurou para fazer. Esse é outro motivo para ter cuidado com a configuração de mensagens para ignorar a filtragem.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>E se uma mensagem for movida para outra pasta (por exemplo, regras da Caixa de Entrada)?

A ZAP ainda funciona desde que a mensagem não tenha sido excluída, ou desde que a mesma ação, ou mais forte, ainda não tenha sido aplicada. Por exemplo, se a política anti-phishing estiver definida como quarentena e a mensagem já estiver no Lixo Eletrônico, a ZAP tomará medidas para colocar a mensagem em quarentena.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Como a ZAP afeta as caixas de correio em espera?

A ZAP não colocará em quarentena as mensagens de caixas de correio em espera. A ZAP pode mover mensagens para a pasta Lixo Eletrônico com base na ação configurada para um veredito de spam ou phishing em políticas anti-spam.

Para obter mais informações sobre retém no Exchange Online, consulte [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).
