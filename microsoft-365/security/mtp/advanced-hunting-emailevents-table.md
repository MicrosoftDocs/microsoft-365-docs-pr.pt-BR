---
title: Tabela EmailEvents no esquema de busca avançada
description: Saiba mais sobre eventos associados aos emails do Microsoft 365 na tabela EmailEvents do esquema de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, referência de esquema, kusto, tabela, coluna, tipo de dados, descrição, EmailEvents, id de mensagem de rede, remetente, destinatário, id de anexo, nome do anexo, veredito de malware, veredito de phishing, contagem de anexos, contagem de links, contagem de url
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
ms.openlocfilehash: a0892e03e0ac4c6fc6bcda1b7b159ce403a7ce2e
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461602"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

A tabela no esquema de busca avançada contém informações sobre eventos envolvendo o processamento de emails no `EmailEvents` Microsoft Defender para Office 365. [](advanced-hunting-overview.md) Use essa referência para criar consultas que retornam informações dessa tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos ( valores) suportados por uma tabela, use a referência de `ActionType` [esquema](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) interna disponível no centro de segurança.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `NetworkMessageId` | string | Identificador exclusivo do email, gerado pelo Microsoft 365 |
| `InternetMessageId` | cadeia de caracteres | Identificador público do email definido pelo seu sistema de envio |
| `SenderMailFromAddress` | cadeia de caracteres | Endereço de email do remetente no cabeçalho EMAIL DE, também conhecido como remetente do envelope ou endereço do caminho de retorno |
| `SenderFromAddress` | cadeia de caracteres | Endereço de email do remetente no cabeçalho DE, visível para os destinatários dos seus clientes de email |
| `SenderDisplayName` | string | Nome do remetente exibido no livro de endereços, normalmente uma combinação de um nome ou nome determinado, uma inicial do meio e um sobrenome ou sobrenome |
| `SenderObjectId` | string |Identificador exclusivo da conta do remetente no Azure AD |
| `SenderMailFromDomain` | cadeia de caracteres | Domínio do remetente no cabeçalho EMAIL DE, também conhecido como remetente do envelope ou endereço do caminho de retorno |
| `SenderFromDomain` | cadeia de caracteres | Domínio do remetente no cabeçalho DE, visível para os destinatários dos seus clientes de email |
| `SenderIPv4` | cadeia de caracteres | Endereço IPv4 do último servidor de email detectado que retransmitiu a mensagem |
| `SenderIPv6` | cadeia de caracteres | Endereço IPv6 do último servidor de email detectado que retransmitiu a mensagem |
| `RecipientEmailAddress` | cadeia de caracteres | Endereço de email do destinatário ou endereço de email do destinatário após a expansão da lista de distribuição |
| `RecipientObjectId` | string | Identificador exclusivo para o destinatário de email no Azure AD |
| `Subject` | cadeia de caracteres | Assunto do email |
| `EmailClusterId` | cadeia de caracteres | Identificador do grupo de emails semelhantes clusterizados com base na análise heurística de seu conteúdo |
| `EmailDirection` | cadeia de caracteres | Direção do email em relação à rede: entrada, saída, dentro da organização |
| `DeliveryAction` | cadeia de caracteres | Ação de entrega do email: Entregue, Lixo Eletrônico, Bloqueado ou Substituído |
| `DeliveryLocation` | cadeia de caracteres | Local onde o email foi entregue: Caixa de Entrada/Pasta, Local/Externo, Tratado como Lixo Eletrônico, Quarentena, Falha, Descartado, Itens excluídos |
| `ThreatTypes` | cadeia de caracteres | Veredito da pilha de filtragem de email sobre se o email contém malware, phishing ou outras ameaças |
| `ThreatNames` | string |Nome da detecção de malware ou outras ameaças encontradas |
| `DetectionMethods` | string | Métodos usados para detectar malware, phishing ou outras ameaças encontradas no email |
| `ConfidenceLevel` | string | Lista de níveis de confiança de qualquer veredito de spam ou phishing. Para spam, esta coluna mostra o nível de confiança de spam (SCL), indicando se o email foi ignorado (-1), considerado não spam (0,1), considerado spam com confiança moderada (5,6) ou considerado spam com alta confiança (9). Para phishing, esta coluna exibe se o nível de confiança é "Alto" ou "Baixo". |
| `EmailAction` | cadeia de caracteres | Ação final executada no email com base no veredito de filtro, políticas e ações do usuário: Mover mensagem para pasta de lixo eletrônico, Adicionar cabeçalho X, Modificar assunto, Redirecionar mensagem, Excluir mensagem, Enviar para quarentena, Nenhuma ação tomada, Mensagem Cco |
| `EmailActionPolicy` | cadeia de caracteres | Política de ação que entrou em vigor: Alta confiança do antispam, Antispam, Email em massa do antispam, Phishing do antispam, Representação do domínio de antiphishing, Representação do usuário de antiphishing, Falsificação do antiphishing, Representação do gráfico de Antiphishing, Antimalware, Anexos Seguros, Regras de Transporte Corporativo (ETR) |
| `EmailActionPolicyGuid` | cadeia de caracteres | Identificador exclusivo da política que determinou a ação final do email |
| `AttachmentCount` | int | Número de anexos no email |
| `UrlCount` | int | Número de URLs inseridas no email |
| `EmailLanguage` | cadeia de caracteres | Idioma detectado do conteúdo do email |
| `Connectors` | string | Instruções personalizadas que definem o fluxo de email organizacional e como o email foi roteado |
| `OrgLevelAction` | string | Ação realizada no email em resposta a uma política definida no nível organizacional |
| `OrgLevelPolicy` | string | Política organizacional que disparou a ação realizada no email |
| `UserLevelAction` | string | Ação realizada no email em resposta a correspondências com uma política de caixa de correio definida pelo destinatário |
| `UserLevelPolicy` | string | Política de caixa de correio do usuário final que disparou a ação realizada no email |
| `ReportId` | long | Identificador de evento baseado em um contador de repetição. Para identificar eventos exclusivos, essa coluna deve ser usada em conjunto com as colunas DeviceName e Timestamp. |

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
