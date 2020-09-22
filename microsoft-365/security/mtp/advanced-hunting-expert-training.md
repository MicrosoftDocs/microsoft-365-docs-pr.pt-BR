---
title: Obter treinamento especializado em busca avançada
description: Treinamento gratuito e orientações de especialistas de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, idioma, treinamento, cenários, básico para avançado, vídeos, passo a passo
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
ms.openlocfilehash: 7db1854534964928b622a7c2f47d07654472f048
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197960"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Obter treinamento especializado em busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

Aumente seu conhecimento de busca avançada rapidamente com _o acompanhamento do adversário_, uma série de webcasts para novos analistas de segurança e hunterss de ameaça. A série orienta você pelas noções básicas, de forma a criar suas próprias consultas sofisticadas. Comece com o primeiro vídeo em conceitos básicos ou vá para vídeos mais avançados que se encontram seu nível de experiência.


| Título | Descrição | Relógio | Consultas | 
|--|--|--|--|
| Episódio 1: conceitos básicos do KQL | Este episódio cobre as noções básicas de busca avançada na proteção contra ameaças da Microsoft. Saiba mais sobre dados de busca avançada disponíveis e sintaxe e operadores básicos de KQL. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [Arquivo CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| Episódio 2: junções | Continue aprendendo sobre dados em busca avançada e como ingressar em tabelas. Saiba mais sobre `inner` ,, `outer` `unique` e `semi` junções, e entenda as nuances da junção Kusto padrão `innerunique` . | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [Arquivo CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| Episódio 3: Resumindo, dinamizando e visualizando dados | Agora que você aprendeu a filtrar, manipular e participar de dados, é hora de resumir, quantificar, dinamizar e Visualizar. Este episódio discute o `summarize` operador e vários cálculos, enquanto introduz tabelas adicionais no esquema. Você também aprenderá a transformar conjuntos de tabelas em gráficos que podem ajudá-lo a extrair idéias. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [Arquivo CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| Episódio 4: Vamos procurar! Aplicando KQL ao rastreamento de incidentes | Neste episódio, você aprende a rastrear alguma atividade de atacante. Usamos nossa compreensão aprimorada do Kusto e busca avançada para rastrear um ataque. Aprenda os truques reais usados no campo, incluindo o ABCs de cybersecurity e como aplicá-los à resposta de incidentes. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [Arquivo CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl)

## <a name="how-to-use-the-csl-file"></a>Como usar o arquivo CSL
Antes de iniciar um episódio, acesse o [arquivo de CSL Kusto correspondente no GitHub](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) e copie seu conteúdo para o editor de consulta de busca avançada. Ao assistir a um episódio, você pode usar o conteúdo copiado para acompanhar o alto-falante e executar as consultas. 

O trecho a seguir de um arquivo CSL mostra um conjunto abrangente de orientações marcadas como comentários com o `//` .

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Defender ATP
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

O mesmo arquivo CSL inclui consultas antes e depois dos comentários, como mostrado abaixo. Para executar uma consulta específica com [várias consultas no editor](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor), mova o cursor para a consulta e selecione **Executar consulta**.   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Defender ATP
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp

AppFileEvents
| take 100
| sort by Timestamp desc
```
     
## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Conhecer a linguagem de consulta de busca avançada](advanced-hunting-query-language.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Procure em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
