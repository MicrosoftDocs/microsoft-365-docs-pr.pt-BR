---
title: Obter treinamento especializado em busca avançada
description: Treinamento gratuito e orientação de especialistas em busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, idioma, treinamento, cenários, básico para avançado, vídeos, passo a passo
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
ms.openlocfilehash: aba0a6ab2c82c038eda8e66890c0c95303dea947
ms.sourcegitcommit: ea8a096df5acedecdce1780969f2b189c3fadf73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50053830"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Obter treinamento especializado em busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Aumente seu conhecimento da busca avançada rapidamente com o acompanhamento do _adversário,_ uma série de webcasts para novos analistas de segurança e busca experientes por ameaças. A série orienta você pelas noções básicas para criar suas próprias consultas sofisticadas. Comece com o primeiro vídeo sobre conceitos básicos ou pule para vídeos mais avançados que se adequam ao seu nível de experiência.


| Título | Descrição | Relógio | Consultas | 
|--|--|--|--|
| Episódio 1: Conceitos básicos de KQL | Este episódio aborda as noções básicas da busca avançada no Microsoft 365 Defender. Saiba mais sobre os dados de busca avançada disponíveis e a sintaxe e os operadores KQL básicos. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [Arquivo CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.csl) |
| Episódio 2: Junções | Continue a aprender sobre os dados na busca avançada e como unir tabelas. Saiba mais `inner` sobre , , e `outer` `unique` `semi` junções, e entenda as nuances da junção padrão `innerunique` kusto. | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [Arquivo CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.csl) |
| Episódio 3: Resumo, pivô e visualização de dados | Agora que você aprendeu a filtrar, manipular e ingressar dados, é hora de resumir, quantificar, girar e visualizar. Este episódio discute o operador `summarize` e vários cálculos, enquanto apresenta tabelas adicionais no esquema. Você também aprenderá a transformar conjuntos de dados em gráficos que podem ajudá-lo a extrair informações. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [Arquivo CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.csl) |
| Episódio 4: Vamos procurar! Aplicando KQL ao rastreamento de incidentes | Neste episódio, você aprende a acompanhar algumas atividades do invasor. Usamos nosso entendimento aprimorado do Kusto e da busca avançada para rastrear um ataque. Aprenda truques reais usados no campo, incluindo as ABCs de segurança cibernética e como aplicá-los à resposta a incidentes. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [Arquivo CSL](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.csl) 


Receba mais treinamento especializado com *L33TSP3AK:* busca avançada no Microsoft 365 Defender , uma série de webcasts para analistas que procuram expandir seus conhecimentos técnicos e habilidades práticas na realização de investigações de segurança usando a busca avançada no Microsoft 365 Defender. 

| Título | Descrição | Relógio | Consultas | 
|--|--|--|--|
| Episódio 1  | Neste episódio, você aprenderá diferentes práticas recomendadas para executar consultas de busca avançada. Entre os tópicos abordados estão: como otimizar suas consultas, usar a busca avançada por ransomware, lidar com JSON como um tipo dinâmico e trabalhar com operadores de dados externos. | [YouTube](https://www.youtube.com/watch?v=nMGbK-ALaVg&feature=youtu.be) (56:34) | [Arquivo CSL](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/l33tSpeak/Performance%2C%20Json%20and%20dynamics%20operator%2C%20external%20data.csl)


## <a name="how-to-use-the-csl-file"></a>Como usar o arquivo CSL
Antes de começar um episódio, acesse o arquivo [CSL do Kusto](https://github.com/microsoft/Microsoft-threat-protection-Hunting-Queries/tree/master/Webcasts/TrackingTheAdversary) correspondente no GitHub e copie seu conteúdo para o editor de consulta de busca avançada. Enquanto assistir a um episódio, você pode usar o conteúdo copiado para seguir o orador e executar consultas. 

O trecho a seguir de um arquivo CSL mostra um conjunto abrangente de diretrizes marcadas como comentários com `//` .

```kusto
// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
// Contains
// - Account information associated with the logon
// - The device which the account logged onto
// - The process which performed the logon
// - Network information (for network logons)
// - Timestamp
```

O mesmo arquivo CSL inclui consultas antes e depois dos comentários, conforme mostrado abaixo. Para executar uma consulta específica com várias consultas no [editor,](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)mova o cursor para essa consulta e selecione **Executar consulta**.   

```kusto
DeviceLogonEvents
| count

// DeviceLogonEvents
// A table containing a row for each logon a device enrolled in Microsoft Defender for Endpoint
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
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
