---
title: Tabela EmailAttachmentInfo no esquema de busca avançada
description: Saiba mais sobre informações de anexo de email na tabela EmailAttachmentInfo do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, EmailAttachmentInfo, id da mensagem de rede, remetente, destinatário, id do anexo, nome do anexo, veredito do malware
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 9f6a4aa68826133bee0437116b2fbf3fde4e7e00
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910714"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!include[Prerelease information](prerelease.md)]

A tabela `EmailAttachmentInfo` no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre anexos em emails e anexos processados na ATP do Office 365. Use essa referência para criar consultas que retornam informações dessa tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `EventTime` | datetime | A data e a hora em que o evento foi gravado |
| `AttachmentId` | string | Identificador exclusivo de anexo de email |
| `NetworkMessageId` | string | Identificador exclusivo do email, gerado pelo Office 365 |
| `SenderFromAddress` | string | Endereço de email do remetente no cabeçalho DE, visível para os destinatários dos seus clientes de email |
| `RecipientEmailAddress` | string | Endereço de email do destinatário ou endereço de email do destinatário após a expansão da lista de distribuição |
| `FileName` | string | Nome do arquivo ao qual a ação gravada foi aplicada |
| `FileType` | string | Tipo de extensão do arquivo |
| `SHA256` | string | SHA-256 do arquivo ao qual a ação gravada foi aplicada. Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível. |
| `MalwareFilterVerdict` | string | Veredito da pilha de filtragem de email sobre se o email contém malware: Malware, Não malware |
| `MalwareDetectionMethod` | string | Método usado para detectar malware no email: Mecanismo antimalware, Reputação de arquivo, Anexos Seguros ATP |

## <a name="related-topics"></a>Tópicos relacionados
- [Buscar proativamente por ameaças](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)