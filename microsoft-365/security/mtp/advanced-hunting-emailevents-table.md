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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: eefd6848e5ae0ddb077db576d55aaf9555e33729
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898988"
---
# <a name="emailevents"></a>EmailEvents

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft



A tabela `EmailEvents` no esquema de [busca avançada](advanced-hunting-overview.md) contém informações sobre eventos que envolvem o processamento de emails na ATP do Office 365. Use esta referência para criar consultas que retornam informações desta tabela.

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
| `PhishDetectionMethod` | cadeia de caracteres | Método usado para detectar o email como phishing: Reputação da URL mal-intencionada, Detonação da URL de links seguros ATP, Filtro de phishing avançado, Filtro de phishing geral, Antifalsificação: dentro da organização, Antifalsificação: domínio externo, Representação de domínio, Representação de usuário, Representação de marca |
| `MalwareFilterVerdict` | cadeia de caracteres | Veredito da pilha de filtragem de email sobre se o email contém malware: Malware, Não malware |
| `MalwareDetectionMethod` | cadeia de caracteres | Método usado para detectar malware no email: Mecanismo antimalware, Reputação de arquivo, Anexos Seguros ATP |
| `FinalEmailAction` | cadeia de caracteres | Ação final executada no email com base no veredito de filtro, políticas e ações do usuário: Mover mensagem para pasta de lixo eletrônico, Adicionar cabeçalho X, Modificar assunto, Redirecionar mensagem, Excluir mensagem, Enviar para quarentena, Nenhuma ação tomada, Mensagem Cco |
| `FinalEmailActionPolicy` | cadeia de caracteres | Política de ação que entrou em vigor: Alta confiança do antispam, Antispam, Email em massa do antispam, Phishing do antispam, Representação do domínio de antiphishing, Representação do usuário de antiphishing, Falsificação do antiphishing, Representação do gráfico de Antiphishing, Antimalware, Anexos Seguros, Regras de Transporte Corporativo (ETR) |
| `FinalEmailActionPolicyGuid` | cadeia de caracteres | Identificador exclusivo da política que determinou a ação final do email |
| `AttachmentCount` | int | Número de anexos no email |
| `UrlCount` | int | Número de URLs inseridas no email |
| `EmailLanguage` | cadeia de caracteres | Idioma detectado do conteúdo do email |

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da caça avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Entender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
