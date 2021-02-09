---
title: Tabela EmailAttachmentInfo no esquema de busca avançada
description: Saiba mais sobre informações de anexo de email na tabela EmailAttachmentInfo do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, EmailAttachmentInfo, id da mensagem de rede, remetente, destinatário, id do anexo, nome do anexo, veredito de malware
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: b810d7b15ef47a33a0675086219d2193cea00f2e
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145014"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender



A tabela no esquema de busca avançada contém informações sobre anexos em emails processados pelo `EmailAttachmentInfo` Microsoft Defender para Office 365. [](advanced-hunting-overview.md) Use essa referência para criar consultas que retornam informações dessa tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `NetworkMessageId` | string | Identificador exclusivo do email, gerado pelo Microsoft 365 |
| `SenderFromAddress` | string | Endereço de email do remetente no cabeçalho DE, visível para os destinatários dos seus clientes de email |
| `SenderDisplayName` | string | Nome do remetente exibido no livro de endereços, normalmente uma combinação de um nome ou nome determinado, uma inicial do meio e um sobrenome ou sobrenome |
| `SenderObjectId` | string | Identificador exclusivo da conta do remetente no Azure AD |
| `RecipientEmailAddress` | string | Endereço de email do destinatário ou endereço de email do destinatário após a expansão da lista de distribuição |
| `RecipientObjectId` | string | Identificador exclusivo do destinatário do email no Azure AD |
| `FileName` | string | Nome do arquivo ao qual a ação gravada foi aplicada |
| `FileType` | string | Tipo de extensão do arquivo |
| `SHA256` | string | SHA-256 do arquivo ao qual a ação gravada foi aplicada. Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível. |
| `MalwareFilterVerdict` | string | Veredito da pilha de filtragem de email sobre se o email contém malware: Malware, Não malware |
| `MalwareDetectionMethod` | string | Método usado para detectar malware no email: mecanismo antimalware, reputação do arquivo, Anexos seguros |
| `ThreatTypes` | string | Veredito da pilha de filtragem de email sobre se o email contém malware, phishing ou outras ameaças |
| `ThreatNames` | string | Nome da detecção de malware ou outras ameaças encontradas |
| `DetectionMethods` | string | Métodos usados para detectar malware, phishing ou outras ameaças encontradas no email |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp. |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
