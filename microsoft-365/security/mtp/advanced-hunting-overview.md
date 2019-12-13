---
title: Visão geral sobre a busca avançada na Proteção contra Ameaças da Microsoft
description: Saiba mais sobre as consultas avançadas de buscas no Microsoft 365 e sobre como usá-las para encontrar ameaças e deficiências na rede de forma proativa
keywords: busca avançada, busca de ameaças, busca por ameaças cyber, pesquisa, consulta, telemetria, detecções personalizadas, esquema, data explorer, microsoft 365, Proteção contra Ameaças da Microsoft
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
ms.openlocfilehash: 03cd648a178d63b2b964e0136c105068f4d1c6ca
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910723"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-threat-protection"></a>Faça buscas proativas por ameaças com a busca avançada da Proteção contra Ameaças da Microsoft

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!include[Prerelease information](prerelease.md)]

A busca avançada é uma ferramenta de busca de ameaças baseada em consultas que permite explorar até 30 dias de dados brutos. Você pode inspecionar proativamente os eventos na sua rede para localizar indicadores e entidades interessantes. O acesso flexível aos dados facilita a busca irrestrita por ameaças potenciais e conhecidas.

No Centro de segurança do Microsoft 365, a busca avançada é compatível com consultas que examinam dados no Microsoft Defender ATP, abrangendo dados de dispositivos integrados e o Office 365 ATP, fornecendo dados de emails. Para usar a busca avançada, é necessário [habilitar a Proteção contra Ameaças da Microsoft](mtp-enable.md).

## <a name="get-started-with-advanced-hunting"></a>Introdução à busca avançada

Recomendamos que você execute várias etapas para começar a trabalhar rapidamente com a busca avançada.

| Meta de aprendizagem | Descrição | Recurso |
|--|--|--|
| **Ver qual seria a linguagem** | A busca avançada se baseia na [linguagem de consulta Kusto](https://docs.microsoft.com/azure/kusto/query/), que oferece suporte à mesma sintaxe e operadores. Comece a aprender a linguagem de consulta executando a primeira consulta. | [Visão geral sobre a linguagem de consulta](advanced-hunting-query-language.md) |
| **Compreender o esquema** | Obtenha uma compreensão de alto nível das tabelas no esquema e em suas colunas. Isso ajuda a determinar onde procurar dados e como construir suas consultas. | [Referência de esquema](advanced-hunting-schema-tables.md) |
| **Usar consultas predefinidas** | Explore coleções de consultas predefinidas que abrangem diferentes cenários de exploração de ameaças. | [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
| **Otimizar consultas** | Saiba como criar consultas eficientes e que combinem dados de emails e dispositivos. | [Práticas recomendadas de consulta](advanced-hunting-shared-queries.md), [Busca em dispositivos e emails](advanced-hunting-best-practices.md)

## <a name="get-help-as-you-write-queries"></a>Obter ajuda durante a criação de consultas
Aproveite as funcionalidades a seguir para escrever rapidamente as consultas:
- **Sugestão automática** — conforme você faz a consulta, a busca avançada fornece sugestões. 
- **Referência de esquema** — inclui a lista de tabelas e suas colunas ao lado da área de trabalho. Para saber mais, passe o mouse sobre um item. Clique duas vezes em um item para inseri-lo no editor de consultas.

## <a name="drilldown-from-query-results"></a>Detalhamento dos resultados da consulta
Para ver em seus resultados de consulta mais informações sobre entidades, como máquinas, arquivos, usuários, endereços IP e URLs, simplesmente clique no identificador de entidade. Isso abre uma página de perfil detalhada para a entidade selecionada no Central de Segurança do Microsoft Defender.

## <a name="tweak-your-queries-from-the-results"></a>Ajustar consultas a partir dos resultados
Clique com o botão direito do mouse em um valor no conjunto de resultados para aprimorar rapidamente a consulta. Você pode usar as opções para:

- Procurar explicitamente pelo valor selecionado (`==`)
- Excluir o valor selecionado da consulta (`!=`)
- Obter operadores mais avançados para adicionar o valor à sua consulta, como `contains`, `starts with` e `ends with` 

![Imagem do conjunto de resultados da busca avançada do Microsoft Defender ATP](../images/advanced-hunting-results-filter.png)

## <a name="filter-the-query-results"></a>Filtrar os resultados da consulta
Os filtros exibidos à direita fornecem um resumo do conjunto de resultados. Cada coluna tem sua própria seção, que lista os valores distintos encontrados para essa coluna e o número de instâncias.

Refine a consulta selecionando os botões "+" ou "-" nos valores que você deseja incluir ou excluir e selecione **Executar consulta**.

![Imagem do filtro de busca avançada](../images/advanced-hunting-filter.png)

Depois de aplicar o filtro para modificar e executar a consulta, os resultados serão atualizados de acordo.

## <a name="related-topics"></a>Tópicos relacionados
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Usar consultas compartilhadas](advanced-hunting-shared-queries.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)