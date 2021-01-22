---
title: Tabela EmailPostDeliveryEvents no esquema de busca avançada
description: Saiba mais sobre ações pós-entrega realizadas nos emails do Microsoft 365 na tabela EmailPostDeliveryEvents do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, EmailPostDeliveryEvents, id da mensagem de rede, remetente, destinatário, id do anexo, nome do anexo, veredito de malware, veredito de phishing, contagem de anexos, contagem de links, contagem de URL
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d7920be05156320411f3907cbcdae88d315b5136
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929701"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

A tabela no esquema de busca avançada contém informações sobre ações pós-entrega realizadas em mensagens `EmailPostDeliveryEvents` de email processadas pelo Microsoft 365. [](advanced-hunting-overview.md) Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos (valores) com suporte em uma tabela, use a referência de esquema interna disponível na `ActionType` central de segurança. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)

Para obter mais informações sobre mensagens de email individuais, você também pode usar [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) o e as [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tabelas. Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `EventId` | string | Identificador exclusivo do evento |
| `NetworkMessageId` | string | Identificador exclusivo do email, gerado pelo Microsoft 365 |
| `InternetMessageId` | cadeia de caracteres | Identificador público do email definido pelo seu sistema de envio |
| `Action` | cadeia de caracteres | Ação tomada na entidade |
| `ActionType` | string | Tipo de atividade que disparou o evento: Correção manual, ZAP de phishing, ZAP de malware |
| `ActionTrigger` | string | Indica se uma ação foi disparada por um administrador (manualmente ou por meio da aprovação de uma ação automatizada pendente) ou por algum mecanismo especial, como uma ZAP ou entrega dinâmica |
| `ActionResult` | string | Resultado da ação |
| `RecipientEmailAddress` | string | Endereço de email do destinatário ou endereço de email do destinatário após a expansão da lista de distribuição |
| `DeliveryLocation` | cadeia de caracteres | Local onde o email foi entregue: Caixa de Entrada/Pasta, Local/Externo, Tratado como Lixo Eletrônico, Quarentena, Falha, Descartado, Itens excluídos |

## <a name="supported-event-types"></a>Tipos de eventos com suporte
Esta tabela captura eventos com os seguintes `ActionType` valores:

- **Correção manual** – Um administrador manualmente tomou medidas em uma mensagem de email depois que ela foi entregue à caixa de correio do usuário. Isso inclui ações realizadas manualmente por meio do [Explorador](../office-365-security/threat-explorer.md) de Ameaças ou aprovações de ações automatizadas de investigação [e resposta (AIR).](mtp-autoir-actions.md)
- **ZAP de phishing** [– A ZAP (Limpeza](../office-365-security/zero-hour-auto-purge.md) Automática Zero Hora) tomou medidas em um email de phishing após a entrega.
- **ZAP de malware** – A ZAP (Limpeza Automática Zero Hora) tomou medidas em uma mensagem de email encontrada contendo malware após a entrega.

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
