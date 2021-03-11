---
title: Tabela EmailPostDeliveryEvents no esquema de busca avançado
description: Saiba mais sobre ações pós-entrega realizadas em emails do Microsoft 365 na tabela EmailPostDeliveryEvents do esquema de busca avançado
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, EmailPostDeliveryEvents, id de mensagem de rede, remetente, destinatário, id de anexo, nome do anexo, veredito de malware, veredito de phishing, contagem de anexos, contagem de links, contagem de url
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
ms.openlocfilehash: 6e12ddfc402f1bd420f57369cc6d54f2e670d710
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50712373"
---
# <a name="emailpostdeliveryevents"></a>EmailPostDeliveryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

A tabela no esquema de busca avançado contém informações sobre ações pós-entrega realizadas em mensagens de email processadas `EmailPostDeliveryEvents` pelo Microsoft [](advanced-hunting-overview.md) 365. Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos ( valores) suportados por uma tabela, use a referência de `ActionType` esquema interna disponível no centro de segurança.

Para obter mais informações sobre mensagens de email individuais, você também pode usar [`EmailEvents`](advanced-hunting-emailevents-table.md) o , e as [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tabelas. Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `NetworkMessageId` | cadeia de caracteres | Identificador exclusivo do email, gerado pelo Microsoft 365 |
| `InternetMessageId` | cadeia de caracteres | Identificador público do email definido pelo seu sistema de envio |
| `Action` | cadeia de caracteres | Ação realizada na entidade |
| `ActionType` | cadeia de caracteres | Tipo de atividade que disparou o evento: Correção manual, PHISH ZAP, MALWARE ZAP |
| `ActionTrigger` | cadeia de caracteres | Indica se uma ação foi disparada por um administrador (manualmente ou por meio da aprovação de uma ação automatizada pendente) ou por algum mecanismo especial, como um ZAP ou Entrega Dinâmica |
| `ActionResult` | cadeia de caracteres | Resultado da ação |
| `RecipientEmailAddress` | cadeia de caracteres | Endereço de email do destinatário ou endereço de email do destinatário após a expansão da lista de distribuição |
| `DeliveryLocation` | cadeia de caracteres | Local onde o email foi entregue: Caixa de Entrada/Pasta, Local/Externo, Tratado como Lixo Eletrônico, Quarentena, Falha, Descartado, Itens excluídos |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp. |

## <a name="supported-event-types"></a>Tipos de eventos com suporte
Esta tabela captura eventos com os seguintes `ActionType` valores:

- **Correção manual** – Um administrador tomou medidas manualmente em uma mensagem de email depois que ela foi entregue à caixa de correio do usuário. Isso inclui ações realizadas manualmente por meio do [Explorador](../office-365-security/threat-explorer.md) de Ameaças ou aprovações de ações automatizadas de investigação e resposta [(AIR).](mtp-autoir-actions.md)
- **Phish ZAP** – [O ZAP (limpeza automática](../office-365-security/zero-hour-auto-purge.md) de hora zero) entrou em ação em um email de phishing após a entrega.
- **MALWARE ZAP** – O ZAP (limpeza automática de hora zero) entrou em ação em uma mensagem de email encontrada contendo malware após a entrega.

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
