---
title: Tabela EmailEvents no esquema de busca avançada
description: Saiba mais sobre os eventos associados aos emails do Microsoft 365 na tabela EmailEvents do esquema de busca avançada
keywords: caça avançada, busca de ameaças, caça de ameaças da CyberSource, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, referência de esquema, Kusto, tabela, coluna, tipo de dados, descrição, EmailEvents, ID da mensagem de rede, remetente, destinatário, ID de anexo, nome do anexo
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 00fcc6514679868066ef88b0c9bc4a485d032528
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667632"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender



A `EmailEvents` tabela no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre eventos envolvendo o processamento de emails no Microsoft Defender para Office 365. Use esta referência para criar consultas que retornam informações desta tabela.

>[!TIP]
> Para obter informações detalhadas sobre os tipos de eventos ( `ActionType` valores) suportados por uma tabela, use a [referência de esquema interna](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) disponível na central de segurança.

Para obter informações sobre outras tabelas no esquema de busca avançada, [confira a referência de busca avançada](advanced-hunting-schema-tables.md).

| Nome da coluna | Tipo de dados | Descrição |
|-------------|-----------|-------------|
| `Timestamp` | datetime | A data e a hora em que o evento foi gravado |
| `EmailId` | cadeia de caracteres | Identificador de email e destinatário exclusivos |
| `NetworkMessageId` | cadeia de caracteres | Identificador exclusivo do email, gerado pelo Microsoft 365 |
| `InternetMessageId` | cadeia de caracteres | Identificador público do email definido pelo seu sistema de envio |
| `SenderMailFromAddress` | cadeia de caracteres | Endereço de email do remetente no cabeçalho EMAIL DE, também conhecido como remetente do envelope ou endereço do caminho de retorno |
| `SenderFromAddress` | cadeia de caracteres | Endereço de email do remetente no cabeçalho DE, visível para os destinatários dos seus clientes de email |
| `SenderMailFromDomain` | cadeia de caracteres | Domínio do remetente no cabeçalho EMAIL DE, também conhecido como remetente do envelope ou endereço do caminho de retorno |
| `SenderFromDomain` | cadeia de caracteres | Domínio do remetente no cabeçalho DE, visível para os destinatários dos seus clientes de email |
| `SenderIPv4` | cadeia de caracteres | Endereço IPv4 do último servidor de email detectado que retransmitiu a mensagem |
| `SenderIPv6` | cadeia de caracteres | Endereço IPv6 do último servidor de email detectado que retransmitiu a mensagem |
| `RecipientEmailAddress` | cadeia de caracteres | Endereço de email do destinatário ou endereço de email do destinatário após a expansão da lista de distribuição |
| `Subject` | cadeia de caracteres | Assunto do email |
| `EmailClusterId` | cadeia de caracteres | Identificador do grupo de emails semelhantes clusterizados com base na análise heurística de seu conteúdo |
| `EmailDirection` | cadeia de caracteres | Direção do email em relação à rede: entrada, saída, dentro da organização |
| `DeliveryAction` | cadeia de caracteres | Ação de entrega do email: Entregue, Lixo Eletrônico, Bloqueado ou Substituído |
| `DeliveryLocation` | cadeia de caracteres | Local onde o email foi entregue: Caixa de Entrada/Pasta, Local/Externo, Tratado como Lixo Eletrônico, Quarentena, Falha, Descartado, Itens excluídos |
| `PhishFilterVerdict` | cadeia de caracteres | Veredito da pilha de filtragem de email sobre se o email é phishing: Phishing ou Não Phishing |
| `PhishDetectionMethod` | cadeia de caracteres | Método usado para detectar o email como phishing: reputação de URL mal-intencionado, URL de links seguros acionamento, filtro de phishing avançado, filtro de phishing geral, antifalsificação: intra-org, antifalsificação: domínio externo, representação de domínio, representação de usuário, representação de marca |
| `MalwareFilterVerdict` | string | Veredito da pilha de filtragem de email sobre se o email contém malware: Malware, Não malware |
| `MalwareDetectionMethod` | string | Método usado para detectar malware no mecanismo de email: Mecanismo Antimalware, reputação de arquivos e anexos seguros |
| `FinalEmailAction` | cadeia de caracteres | Ação final executada no email com base no veredito de filtro, políticas e ações do usuário: Mover mensagem para pasta de lixo eletrônico, Adicionar cabeçalho X, Modificar assunto, Redirecionar mensagem, Excluir mensagem, Enviar para quarentena, Nenhuma ação tomada, Mensagem Cco |
| `FinalEmailActionPolicy` | cadeia de caracteres | Política de ação que entrou em vigor: Alta confiança do antispam, Antispam, Email em massa do antispam, Phishing do antispam, Representação do domínio de antiphishing, Representação do usuário de antiphishing, Falsificação do antiphishing, Representação do gráfico de Antiphishing, Antimalware, Anexos Seguros, Regras de Transporte Corporativo (ETR) |
| `FinalEmailActionPolicyGuid` | cadeia de caracteres | Identificador exclusivo da política que determinou a ação final do email |
| `AttachmentCount` | int | Número de anexos no email |
| `UrlCount` | int | Número de URLs inseridas no email |
| `EmailLanguage` | cadeia de caracteres | Idioma detectado do conteúdo do email |
| `OrgLevelAction` | string | Ação tomada no email em resposta a correspondências com uma política definida no nível organizacional |
| `OrgLevelPolicy` | string | Política organizacional que disparou a ação tomada no email |
| `UserLevelAction` | string | Ação tomada no email em resposta a correspondências com uma política de caixa de correio definida pelo destinatário |
| `UserLevelPolicy` | string | Política de caixa de correio de usuário final que disparou a ação executada no email |
| `Connectors` | string | Instruções personalizadas que definem o fluxo de emails organizacionais e como o email foi roteado |
| `SenderDisplayName` | string | Nome do remetente exibido no catálogo de endereços, geralmente uma combinação de um determinado nome, inicial do meio e sobrenome ou sobrenome |
| `SenderObjectId` | string |Identificador exclusivo para a conta do remetente no Azure AD |
| `ThreatTypes` | string | Veredicto da pilha de filtragem de emails em se o email contém malware, phishing ou outras ameaças |
| `ThreatNames` | string |Nome de detecção para malware ou outras ameaças encontradas |
| `DetectionMethods` | string | Métodos usados para detectar malware, phishing ou outras ameaças encontradas no email |


## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
