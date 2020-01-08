---
title: Estatísticas de pesquisa
ms.author: markjjo
author: esclee
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: fe4d1c92230bcc4e6e1136eeb43c99cc6d8297ca
ms.sourcegitcommit: af7950d9674f0eab3aee03f9afccff9ca2f4709a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971290"
---
# <a name="search-statistics"></a>Estatísticas de pesquisa

Uma maneira de validar seus resultados de pesquisa é examinar as estatísticas em torno dos seus resultados para garantir que eles se alinhem às suas expectativas. Quando uma pesquisa é concluída, as estatísticas de alto nível são exibidas no submenu detalhes da pesquisa:
- Número e volume de itens recuperados pela pesquisa
- Número e volume de itens parcialmente indexados/não indexados que foram encontrados nos locais de pesquisa
- Número de caixas de correio e locais pesquisados.
Para exibir estatísticas mais detalhadas, clique em "Estatísticas" no submenu detalhes da pesquisa.

## <a name="summary"></a>Resumo

No modo de exibição Resumo, você pode ver os resultados da pesquisa dividido por tipo de local (por exemplo, Exchange). Para cada tipo de local, você pode ver:
- Número de locais que tinham itens que corresponderam às condições de pesquisa
- Número de itens desses locais que corresponderam às condições de pesquisa
- Volume total de itens que correspondem às condições de pesquisa.

## <a name="top-locations"></a>Principais locais

No modo de exibição de locais principais, você vê os locais individuais com mais correspondências. Para cada local, você verá:
- Nome do local (por exemplo, URL do SharePoint)
- Tipo de local
- Número de itens que corresponderam às condições de pesquisa
- Volume total de itens que correspondem às condições de pesquisa.

## <a name="queries"></a>Consultas

Se você tiver usado (c:s) linhas de palavra-chave ou de palavra-chave em sua consulta, poderá ver a divisão da consulta no modo de exibição de consultas por tipo de local. Para cada tipo de local, você verá:

- Parte: essa coluna terá a palavra "Primary" ou "keyword". "Primary" significa que a linha apresenta estatísticas em toda a consulta, enquanto "palavra-chave" significa um dos componentes de consulta.

- Consulta: o componente de consulta real ao qual a linha se refere. Se Part for "Primary", esta será a consulta inteira; se parte foi "palavra-chave", você verá um dos componentes de consulta aqui.
  
  - Quando você pesquisa todo o conteúdo de caixas de correio (não especificando nenhuma palavra-chave), a consulta real é (tamanho >= 0) para que todos os itens sejam retornados
  
  - Quando você pesquisa sites do SharePoint Online e do OneDrive for Business, os dois componentes a seguir são adicionados:
    
    - Não IsExternalContent: 1-exclui qualquer conteúdo de uma organização local do SharePoint
    
    - Não isOneNotePage: 1-exclui todos os arquivos do OneNote porque eles seriam duplicatas de qualquer documento que corresponda à consulta de pesquisa.

- Número de locais que tinham itens que corresponderam às condições de pesquisa.

- Número de itens desses locais que corresponderam às condições de pesquisa.

- Volume total de itens que correspondem às condições de pesquisa.