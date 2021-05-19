---
title: Obter treinamento especializado em busca avançada
description: Treinamento gratuito e orientação de especialistas em busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, idioma, treinamento, cenários, básico para avançado, vídeos, passo a passo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 0b816956442408c9a61f662827f1fd45d9b6511f
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538850"
---
# <a name="get-expert-training-on-advanced-hunting"></a>Obter treinamento especializado em busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender
- Microsoft Defender para Ponto de Extremidade

Aumente o conhecimento da busca avançada rapidamente com _o Controle_ do adversário , uma série de webcast para novos analistas de segurança e caçadores de ameaças experientes. A série orienta você pelos conceitos básicos até criar suas próprias consultas sofisticadas. Comece com o primeiro vídeo sobre fundamentos ou pule para vídeos mais avançados que se adequam ao seu nível de experiência.

| Título | Descrição | Relógio | Consultas | 
|--|--|--|--|
| Episódio 1: conceitos básicos de KQL | Este episódio aborda as noções básicas de busca avançada no Microsoft 365 Defender. Saiba mais sobre os dados avançados de busca disponíveis e a sintaxe básica de KQL e operadores. | [YouTube](https://youtu.be/0D9TkGjeJwM?t=351) (54:14) | [Arquivo de texto](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%201%20-%20KQL%20Fundamentals.txt) |
| Episódio 2: Joins | Continue aprendendo sobre dados na busca avançada e como unir tabelas. Saiba mais `inner` sobre , , e `outer` `unique` `semi` insumente e entenda as nuances da junção padrão do Kusto. `innerunique` | [YouTube](https://youtu.be/LMrO6K5TWOU?t=297) (53:33) | [Arquivo de texto](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%202%20-%20Joins.txt) |
| Episódio 3: Resumindo, pivotando e visualizando dados | Agora que você aprendeu a filtrar, manipular e ingressar dados, é hora de resumir, quantificar, girar e visualizar. Este episódio discute o operador `summarize` e vários cálculos, enquanto apresenta tabelas adicionais no esquema. Você também aprenderá a transformar conjuntos de dados em gráficos que podem ajudá-lo a extrair informações. | [YouTube](https://youtu.be/UKnk9U1NH6Y?t=296) (48:52) | [Arquivo de texto](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%203%20-%20Summarizing%2C%20Pivoting%2C%20and%20Joining.txt) |
| Episódio 4: Vamos procurar! Aplicando KQL ao controle de incidentes | Neste episódio, você aprenderá a controlar algumas atividades de invasor. Usamos nossa compreensão aprimorada de Kusto e busca avançada para rastrear um ataque. Saiba os truques reais usados no campo, incluindo os ABCs de segurança cibernética e como aplicá-los à resposta a incidentes. | [YouTube](https://youtu.be/2EUxOc_LNd8?t=291) (59:36) | [Arquivo de texto](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/TrackingTheAdversary/Episode%204%20-%20Lets%20Hunt.txt) 


Obter mais treinamento especializado com *L33TSP3AK:* busca avançada no Microsoft 365 Defender , uma série de webcast para analistas que procuram expandir seus conhecimentos técnicos e habilidades práticas na realização de investigações de segurança usando a busca avançada no Microsoft 365 Defender. 

| Título | Descrição | Relógio | Consultas | 
|--|--|--|--|
| Episódio 1  | Neste episódio, você aprenderá diferentes práticas recomendadas na execução de consultas avançadas de busca. Entre os tópicos abordados estão: como otimizar suas consultas, usar a busca avançada por ransomware, manipular o JSON como um tipo dinâmico e trabalhar com operadores de dados externos. | [YouTube](https://www.youtube.com/watch?v=nMGbK-ALaVg&feature=youtu.be) (56:34) | [Arquivo de texto](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/l33tSpeak/Performance%2C%20Json%20and%20dynamics%20operator%2C%20external%20data.txt) |
| Episódio 2 | Neste episódio, você aprenderá a investigar e responder a locais de logon suspeitos ou incomuns e exfiltração de dados por meio de regras de encaminhamento de caixa de entrada. Sebastien Molendijk, Gerente sênior de Programas para CxE de Segurança na Nuvem, compartilha como usar a busca avançada para investigar incidentes em vários estágios com Microsoft Cloud App Security dados. | [YouTube](https://www.youtube.com/watch?v=QaUxdtNfbd8) (57:07) | [Arquivo de texto](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/blob/master/Webcasts/l33tSpeak/MCAS%20-%20The%20Hunt.txt)


## <a name="how-to-use-the-csl-file"></a>Como usar o arquivo CSL
Antes de iniciar um episódio, acesse o arquivo [de](https://github.com/microsoft/Microsoft-365-Defender-Hunting-Queries/tree/master/Webcasts) texto correspondente no GitHub e copie seu conteúdo para o editor de consulta de busca avançada. Ao assistir a um episódio, você pode usar o conteúdo copiado para seguir o alto-falante e executar consultas. 

O trecho a seguir de um arquivo de texto que contém as consultas mostra um conjunto abrangente de orientações marcadas como comentários com `//` .

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

O mesmo arquivo de texto inclui consultas antes e depois dos comentários, conforme mostrado abaixo. Para executar uma consulta específica com várias consultas no [editor,](advanced-hunting-query-language.md#work-with-multiple-queries-in-the-editor)mova o cursor para essa consulta e selecione **Executar consulta**.   

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

CloudAppEvents
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
