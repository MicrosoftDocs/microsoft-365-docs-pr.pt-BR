---
title: Estatísticas de pesquisa no Advance eDiscovery
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
description: Valide os resultados da pesquisa exibindo as estatísticas geradas depois que você executar uma pesquisa de coleção na Descoberta Avançada.
ms.openlocfilehash: 5b6cfdaffc7851a00035a4edcc9d490b229c455d
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750772"
---
# <a name="search-statistics-in-advanced-ediscovery"></a>Estatísticas de pesquisa na Descoberta Avançada

Uma maneira de validar os resultados da pesquisa é ver as estatísticas em torno dos resultados para garantir que eles se alinhem às suas expectativas. Quando uma pesquisa é concluída, as estatísticas de alto nível são mostradas no submenu de detalhes da pesquisa:

- Número e volume de itens recuperados pela pesquisa

- Número e volume de itens parcialmente indexados ou não indexados encontrados nos locais de pesquisa

- Número de caixas de correio e locais pesquisados.
Para exibir estatísticas mais detalhadas, clique em "Estatísticas" no flyout de detalhes da pesquisa.

## <a name="summary-view"></a>Exibição de resumo

Na exibição Resumo, você pode ver os resultados da pesquisa divididos por tipo de local (por exemplo, Exchange). Para cada tipo de local, você pode ver:

- Número de locais que tinham itens que corresponderam às condições de pesquisa

- Número de itens desses locais que corresponderam às condições de pesquisa

- Volume total de itens que corresponderam às condições de pesquisa.

## <a name="top-locations-view"></a>Exibição de locais principais

Na exibição Locais principais, você vê os locais individuais com mais combinações. Para cada local, você verá:

- Nome do local (por exemplo, URL do SharePoint)

- Tipo de local

- Número de itens que corresponderam às condições de pesquisa

- Volume total de itens que corresponderam às condições de pesquisa.

## <a name="queries-view"></a>Exibição de consultas

Se você tiver usado (c:s) palavras-chave ou linhas de palavra-chave em sua consulta, poderá ver o detalhamento de sua consulta no exibição Consultas por tipo de local. Para cada tipo de local, você verá:

- Parte: esta coluna terá a palavra "Primária" ou "Palavra-chave". "Principal" significa que a linha apresenta estatísticas em toda a consulta, enquanto "Palavra-chave" significa um dos componentes da consulta.

- Consulta: o componente de consulta real ao que a linha se refere. Se Parte for "Primária", será toda a consulta; se Part for "Palavra-chave", você verá um dos componentes de consulta aqui.
  
  - Quando você pesquisa todas as caixas de correio de conteúdo (sem especificar palavras-chave), a consulta real é (tamanho >= 0) para que todos os itens sejam retornados
  
  - Quando você pesquisa sites do SharePoint Online e do OneDrive for Business, os dois componentes a seguir são adicionados:
    
    - NOT IsExternalContent:1 - exclui qualquer conteúdo de uma organização local do SharePoint
    
    - NOT isOneNotePage: 1 - exclui todos os arquivos do OneNote porque eles seriam duplicatas de qualquer documento que corresponde à consulta de pesquisa.

- Número de locais que tinham itens que corresponderam às condições de pesquisa.

- Número de itens desses locais que corresponderam às condições de pesquisa.

- Volume total de itens que corresponderam às condições de pesquisa.
