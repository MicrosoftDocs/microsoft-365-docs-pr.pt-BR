---
title: Tabela EmailAttachmentInfo no esquema de busca avançada
description: Saiba mais sobre informações de anexo de email na tabela EmailAttachmentInfo do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça de ameaças na rede, proteção contra ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, EmailAttachmentInfo, ID da mensagem de rede, remetente, destinatário, ID de anexo, nome do anexo, veredicto de malware
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 6d88303b34f78abc857e9aec749bf2f58090f43a
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667644"
---
# <a name="emailattachmentinfo"></a>EmailAttachmentInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender



A `EmailAttachmentInfo` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre anexos em emails processados pelo Microsoft Defender para Office 365. Use essa referência para criar consultas que retornam informações dessa tabela.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `AttachmentId` | string | Identificador exclusivo de anexo de email |
| `NetworkMessageId` | string | Identificador exclusivo do email, gerado pelo Microsoft 365 |
| `SenderFromAddress` | string | Endereço de email do remetente no cabeçalho DE, visível para os destinatários dos seus clientes de email |
| `RecipientEmailAddress` | string | Endereço de email do destinatário ou endereço de email do destinatário após a expansão da lista de distribuição |
| `FileName` | string | Nome do arquivo ao qual a ação gravada foi aplicada |
| `FileType` | string | Tipo de extensão do arquivo |
| `SHA256` | string | SHA-256 do arquivo ao qual a ação gravada foi aplicada. Esse campo geralmente não é preenchido; use a coluna SHA1 quando disponível. |
| `MalwareFilterVerdict` | string | Veredito da pilha de filtragem de email sobre se o email contém malware: Malware, Não malware |
| `MalwareDetectionMethod` | string | Método usado para detectar malware no mecanismo de email: Mecanismo Antimalware, reputação de arquivos e anexos seguros |
| `SenderDisplayName` | string | Nome do remetente exibido no catálogo de endereços, geralmente uma combinação de um determinado nome, inicial do meio e sobrenome ou sobrenome |
| `SenderObjectId` | string | Identificador exclusivo para a conta do remetente no Azure AD |
| `ThreatTypes` | string | Veredicto da pilha de filtragem de emails em se o email contém malware, phishing ou outras ameaças |
| `ThreatNames` | string | Nome de detecção para malware ou outras ameaças encontradas |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
