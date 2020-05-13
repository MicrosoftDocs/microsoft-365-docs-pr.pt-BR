---
title: Limpeza automática de zero horas (ZAP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
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
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem saber mais sobre como a limpeza automática de zero horas (ZAP) pode mover retroativamente as mensagens entregues em uma caixa de correio do Exchange Online para a pasta de lixo eletrônico ou quarentena que estão retroativamente de spam ou phishing.
ms.openlocfilehash: 643063139f5d65b0271fd14ee5a2d1ca1f42ad1a
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208435"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Limpeza automática de zero horas (ZAP) no Exchange Online

## <a name="overview"></a>Visão Geral

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online, a limpeza automática de zero horas (ZAP) é um recurso de proteção de email que detecta retroativamente e neutralizes mensagens de phishing, spam ou malware mal-intencionadas que já foram entregues às caixas de correio do Exchange Online.

ZAP não funciona em ambientes autônomos do Exchange Online Protection (EOP) que protegem caixas de correio locais do Exchange.

## <a name="how-zap-works"></a>Como o ZAP funciona

As assinaturas de spam e malware são atualizadas no tempo real do serviço em uma base diária. No entanto, os usuários ainda podem receber mensagens mal-intencionadas por vários motivos, incluindo se o conteúdo é enarmado depois de ser entregue aos usuários. O ZAP aborda esse problema ao monitorar continuamente as atualizações para as assinaturas de spam e malware no serviço. ZAP pode localizar e remover mensagens que já estão na caixa de correio de um usuário.

A ação ZAP é direta para o usuário; Eles não são notificados quando uma mensagem é detectada e movida.

[Listas de remetentes seguros](create-safe-sender-lists-in-office-365.md), regras de fluxo de emails (também conhecidas como regras de transporte), regras de caixa de entrada ou filtros adicionais têm precedência sobre o zap. Semelhante ao que acontece no fluxo de email, isso significa que, mesmo se o serviço determinar que a mensagem entregue precisa de ZAP, a mensagem não é acionada por causa da configuração de remetentes confiáveis. Essa é outra razão para ter cuidado com a configuração de mensagens para ignorar a filtragem.

### <a name="malware-zap"></a>ZAP de malware

Para **mensagens de leitura ou não lidas** que são encontradas para conter malware após a entrega, zap coloca em quarentena a mensagem que contém o anexo de malware. Somente os administradores podem exibir e gerenciar mensagens de malware da quarentena.

O malware ZAP é habilitado por padrão em políticas antimalware. Para obter mais informações, consulte [Configure anti-malware Policies in EOP](configure-anti-malware-policies.md).

### <a name="phish-zap"></a>Phish de phishing

Para **mensagens de leitura ou não lidas** que são identificadas como Phish após a entrega, o resultado de zap depende da ação que é configurada para um veredicto de filtragem de **email de phishing** na política antispam aplicável. As ações de filtragem de veredicto disponíveis para o Phish e seus possíveis resultados de ZAP são descritos na lista a seguir:

- **Adicionar cabeçalho X**, **preceder a linha de assunto com o texto**: zap não realiza nenhuma ação na mensagem.

- **Mover mensagem para o lixo eletrônico**: zap move a mensagem para a pasta lixo eletrônico, contanto que a regra de lixo eletrônico esteja habilitada na caixa de correio (habilitada por padrão). Para obter mais informações, consulte [Configurar definições de lixo eletrônico em caixas de correio do Exchange Online no Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Redirecionar mensagem para endereço de email**, **Excluir mensagem**, **mensagem de quarentena**: zap coloca a mensagem em quarentena.

Por padrão, o phishing ZAP está habilitado em políticas antispam, e a ação padrão para o filtro de filtragem de **email de phishing** veredicto é uma **mensagem em quarentena**, o que significa que o Phish zap coloca a mensagem por padrão.

Para obter mais informações sobre a configuração do filtro de spam verdicts, consulte [Configure anti-spam Policies in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="spam-zap"></a>ZAP de spam

Para **mensagens não lidas** identificadas como spam após a entrega, o resultado de zap depende da ação configurada para o veredicto de filtragem de **spam** na política antispam aplicável. As ações de filtragem de veredicto para spam e seus possíveis resultados de ZAP são descritas na lista a seguir:

- **Adicionar cabeçalho X**, **preceder a linha de assunto com o texto**: zap não realiza nenhuma ação na mensagem.

- **Mover mensagem para o lixo eletrônico**: zap move a mensagem para a pasta lixo eletrônico, contanto que a regra de lixo eletrônico esteja habilitada na caixa de correio (habilitada por padrão). Para obter mais informações, consulte [Configurar definições de lixo eletrônico em caixas de correio do Exchange Online no Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md).

- **Redirecionar mensagem para endereço de email**, **Excluir mensagem**, **mensagem de quarentena**: zap coloca a mensagem em quarentena. Os usuários finais podem exibir e gerenciar suas próprias mensagens em quarentena de spam.

Por padrão, o lixo de spam está habilitado em políticas antispam, e a ação padrão para o veredicto de filtragem de **spam** é **mover a mensagem para a pasta lixo eletrônico**, o que significa que o lixo de spam move as mensagens **não lidas** para a pasta lixo eletrônico por padrão.

Para obter mais informações sobre a configuração do filtro de spam verdicts, consulte [Configure anti-spam Policies in Microsoft 365](configure-your-spam-filter-policies.md).

### <a name="zap-considerations-for-office-365-advanced-threat-protection-office-365-atp"></a>Considerações de ZAP para a proteção avançada contra ameaças do Office 365 (Office 365 ATP)

ZAP não colocará em quarentena qualquer mensagem que esteja no processo de varredura [dinâmica da entrega](dynamic-delivery-and-previewing.md) , ou em que a filtragem de malware já tenha substituído o anexo com o arquivo **Text. txt de alerta de malware** . Se um sinal de phishing ou spam for recebido para esses tipos de mensagens, e a veredicto de filtragem na política antispam estiver definida para executar alguma ação na mensagem (mover para lixo eletrônico, redirecionar, excluir, quarentena), ZAP será o padrão para uma ação mover para lixo eletrônico.

## <a name="how-to-see-if-zap-moved-your-message"></a>Como ver se ZAP moveu a mensagem

Para determinar se o ZAP moveu a mensagem, você pode usar o [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report) ou o [Explorador de ameaças (e detecções em tempo real)](threat-explorer.md). Observe que, como uma ação do sistema, ZAP não é registrado nos logs de auditoria de caixa de correio do Exchange.

## <a name="zap-faq"></a>FAQ DE ZAP

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>O que acontece se uma mensagem legítima for movida para a pasta lixo eletrônico?

Você deve seguir o processo de relatório normal para [falsos positivos](report-junk-email-messages-to-microsoft.md). A única razão pela qual a mensagem seria movida da caixa de entrada para a pasta lixo eletrônico seria porque o serviço determinou que a mensagem era spam ou mal-intencionada.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>E se eu usar a pasta quarentena em vez da pasta lixo eletrônico?

O ZAP executará uma ação em uma mensagem com base na configuração de suas políticas antispam, conforme descrito anteriormente neste tópico.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>E se eu estiver usando remetentes confiáveis, regras de fluxo de email ou listas de remetentes permitidos/bloqueados?

Remetentes confiáveis, regras de fluxo de emails ou bloqueio e permitir configurações organizacionais têm precedência. Essas mensagens são excluídas de ZAP, pois o serviço está fazendo o que você configurou para fazer. Essa é outra razão para ter cuidado com a configuração de mensagens para ignorar a filtragem.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>E se uma mensagem for movida para outra pasta (por exemplo, regras de caixa de entrada)?

ZAP ainda funciona desde que a mensagem não tenha sido excluída, ou desde que a mesma ação, ou mais forte, ainda não tenha sido aplicada. Por exemplo, se a política de phishing estiver definida como quarentena e o usuário ou administrador já tiver desenviado o email, a quarentena executará uma ação para colocar em quarentena o arquivo.

### <a name="does-zap-change-the-message-header"></a>O ZAP altera o cabeçalho da mensagem?

Uma ação ZAP não faz qualquer alteração no cabeçalho da mensagem.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Como o ZAP afeta caixas de correio em espera?

ZAP não colocará em quarentena as mensagens de caixas de correio em espera. ZAP pode mover mensagens para a pasta lixo eletrônico com base na ação configurada para um spam ou veredicto de phishing em políticas antispam.

Para obter mais informações sobre isenções no Exchange Online, consulte [bloqueio in-loco e retenção de litígio no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds).
