---
title: Estatísticas de pesquisa em Descoberta Antecipada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Valide seus resultados de pesquisa exibindo as estatísticas geradas após executar uma pesquisa de coleção em Advanced eDiscovery.
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750772"
---
# <a name="search-statistics-in-advanced-ediscovery"></a>Estatísticas de pesquisa em Advanced eDiscovery

Uma maneira de validar os resultados da pesquisa é olhar para as estatísticas em torno dos resultados para garantir que eles se alinham às suas expectativas. Quando uma pesquisa é concluída, estatísticas de alto nível são mostradas no submenu de detalhes da pesquisa:

- Número e volume de itens recuperados pela pesquisa

- Número e volume de itens parcialmente indexados ou não indexados encontrados nos locais de pesquisa

- Número de caixas de correio e locais pesquisados.
Para exibir estatísticas mais detalhadas, clique em "Estatísticas" no sobremenu de detalhes da pesquisa.

## <a name="summary-view"></a>Exibição de resumo

Na exibição Resumo, você pode ver os resultados da pesquisa divididos por tipo de local (por exemplo, Exchange). Para cada tipo de local, você pode ver:

- Número de locais que tinham itens que corresponderam às condições de pesquisa

- Número de itens desses locais que corresponderam às condições de pesquisa

- Volume total de itens que corresponderam às condições de pesquisa.

## <a name="top-locations-view"></a>Exibição de locais principais

Na exibição Locais Principais, você vê os locais individuais com mais combinações. Para cada local, você verá:

- Nome do local (por exemplo, SharePoint URL)

- Tipo de local

- Número de itens que corresponderam às condições de pesquisa

- Volume total de itens que corresponderam às condições de pesquisa.

## <a name="queries-view"></a>Exibição consultas

Se você tiver usado (c:s) palavras-chave ou linhas de palavra-chave em sua consulta, poderá ver a divisão da consulta no exibição Consultas por tipo de local. Para cada tipo de local, você verá:

- Parte: esta coluna terá a palavra "Primária" ou "Palavra-chave". "Primária" significa que a linha apresenta estatísticas em toda a consulta, enquanto "Palavra-chave" significa um dos componentes de consulta.

- Consulta: o componente de consulta real ao que a linha se refere. Se Part for "Primary", essa será a consulta inteira; se Part era "Keyword", você verá um dos componentes de consulta aqui.
  
  - Quando você pesquisa todos os conteúdos em caixas de correio (sem especificar palavras-chave), a consulta real é (tamanho >= 0) para que todos os itens sejam retornados
  
  - Quando você pesquisa SharePoint online e OneDrive for Business sites, os dois componentes a seguir são adicionados:
    
    - NOT IsExternalContent:1 - exclui qualquer conteúdo de uma organização SharePoint local
    
    - NOT isOneNotePage: 1 - exclui todos os arquivos OneNote porque eles seriam duplicatas de qualquer documento que correspondesse à consulta de pesquisa.

- Número de locais que tinham itens que corresponderam às condições de pesquisa.

- Número de itens desses locais que corresponderam às condições de pesquisa.

- Volume total de itens que corresponderam às condições de pesquisa.
