---
title: Tabela EmailPostDeliveryEvents no esquema de busca avançada
description: Saiba mais sobre as ações de envio realizadas nos emails do Microsoft 365 na tabela EmailPostDeliveryEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça de ameaças da CyberSource, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, EmailPostDeliveryEvents, ID da mensagem de rede, remetente, destinatário, ID de anexo, nome do anexo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 88074de8792124557c65b5be074e3b02bfec2511
ms.sourcegitcommit: 445b249a6f0420b32e49742fd7744006c7090b2b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797881"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

A `EmailPostDeliveryEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre as ações de envio realizadas em mensagens de email processadas pelo Microsoft 365. Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos ( `ActionType` valores) suportados por uma tabela, use a [referência de esquema interna](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponível na central de segurança.

Para obter mais informações sobre mensagens de email individuais, você também pode usar o [`EmailEvents`](advanced-hunting-emailevents-table.md) , o [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) e as [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tabelas. Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `EventId` | string | Identificador exclusivo do evento |
| `NetworkMessageId` | string | Identificador exclusivo do email, gerado pelo Microsoft 365 |
| `InternetMessageId` | cadeia de caracteres | Identificador público do email definido pelo seu sistema de envio |
| `Action` | cadeia de caracteres | Ação tomada na entidade |
| `ActionType` | string | Tipo de atividade que disparou o evento: correção manual, "phishing ZAP, malware ZAP" |
| `ActionTrigger` | string | Indica se uma ação foi disparada por um administrador (manualmente ou por meio da aprovação de uma ação automática pendente) ou por algum mecanismo especial, como uma entrega de ZAP ou dinâmica |
| `ActionResult` | string | Resultado da ação |
| `RecipientEmailAddress` | string | Endereço de email do destinatário ou endereço de email do destinatário após a expansão da lista de distribuição |
| `DeliveryLocation` | cadeia de caracteres | Local onde o email foi entregue: Caixa de Entrada/Pasta, Local/Externo, Tratado como Lixo Eletrônico, Quarentena, Falha, Descartado, Itens excluídos |

## <a name="supported-event-types"></a>Tipos de eventos com suporte
Esta tabela captura eventos com os seguintes `ActionType` valores:

- **Correção manual** – um administrador executou uma ação manualmente em uma mensagem de email após sua entrega à caixa de correio do usuário. Isso inclui ações realizadas manualmente por meio do [Explorador de ameaças](../office-365-security/threat-explorer.md) ou aprovações de [ações de investigação e resposta (ar) automatizadas](mtp-autoir-actions.md).
- **Phish zap** – o [descarte automático de zero horas (zap)](../office-365-security/zero-hour-auto-purge.md) executou uma ação em um email de phishing após a entrega.
- **Malware zap** – o descarte automático de zero horas (zap) executou uma ação em uma mensagem de email encontrada contendo malware após a entrega.

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da caça avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Procure em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)