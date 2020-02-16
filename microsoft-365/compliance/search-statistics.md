---
title: Estatísticas de pesquisa
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
ms.openlocfilehash: 7c59b36e3594d653f188742890ea849e2595a648
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081359"
---
# <a name="search-statistics"></a>Estatísticas de pesquisa

Uma maneira eficaz de validar seus resultados de pesquisa ao investigar um incidente de dados é exibir as estatísticas sobre seus resultados de pesquisa para garantir que eles se alinhem às suas expectativas. Quando uma pesquisa de conclusão é executada, as seguintes estatísticas de alto nível são exibidas em **status** na página do submenu detalhes da pesquisa:

![Pesquisar statisics na página de submenu detalhes da pesquisa](../media/SearchDetailsFlyout.png)

- O número estimado e o tamanho dos itens que correspondem aos critérios de pesquisa.

- O número e o tamanho de itens parcialmente indexados (também chamados de *itens não indexados*) que não são pesquisáveis, mas que foram encontrados nos locais de conteúdo que foram incluídos na pesquisa.

- O número de caixas de correio e sites que foram pesquisados.

Para exibir estatísticas mais detalhadas, clique em **estatísticas** na página do submenu detalhes da pesquisa. Na página **Estatísticas de pesquisa** , você pode exibir o resumo da pesquisa, o local principal que continha itens que corresponderam aos resultados da pesquisa e estatísticas detalhadas sobre a consulta de pesquisa.

![Lista suspensa de estatísticas de pesquisa](../media/SearchStatisticsDropDownList.png)

## <a name="summary"></a>Resumo

No modo de exibição de **Resumo** , você pode ver os resultados da pesquisa divididos por tipo de local (por exemplo, locais incluem caixas de correio do Exchange e sites do SharePoint). As informações a seguir são exibidas para cada tipo de local:

- O número de locais que tinham itens que corresponderam aos critérios de pesquisa.

- O número total de itens de cada tipo de local que corresponde aos critérios de pesquisa.

- O tamanho total dos itens de cada tipo de local que corresponde aos critérios de pesquisa.

## <a name="top-locations"></a>Principais locais

No modo de exibição **locais principais** , você vê os locais de conteúdo individuais com a maioria dos itens que corresponderam aos critérios de pesquisa. Para cada local de conteúdo, são exibidas as seguintes informações:

- O nome do local; o endereço de email para caixas de correio e a URL para sites do SharePoint

- O tipo de local

- Número de itens que correspondem aos critérios de pesquisa

- O tamanho total de todos os itens que correspondem aos critérios de pesquisa.

## <a name="queries"></a>Consultas

No modo de exibição **consultas** , você pode ver estatísticas detalhadas para cada componente da consulta de pesquisa. Se você usou a lista de palavras-chave na consulta de pesquisa, poderá exibir as estatísticas aprimoradas no modo de exibição **consultas** que mostram quantos itens correspondem a cada palavra-chave ou frase de palavra-chave. Isso pode ajudá-lo a identificar rapidamente quais partes da consulta são as mais (e menos) eficientes. 

As informações a seguir são exibidas no modo de exibição de **consultas** :

 - **Tipo de local** -o tipo de local de conteúdo para as estatísticas exibidas na linha.

- **Parte** -esta coluna exibirá um dos seguintes valores: **Primary** ou **keyword**. **Principal** significa que a linha apresenta estatísticas em toda a consulta; **Palavra-chave** significa que as estatísticas na linha são para um dos componentes de consulta.

- **Condition** -o componente de consulta real da consulta de pesquisa à qual a linha se refere. Se o valor na coluna **parte** for **principal**, as estatísticas para a consulta de pesquisa inteira serão exibidas; Se o valor for **keyword**, as estatísticas do componente da consulta mostrada na coluna de **consulta** serão exibidas. Por exemplo, se a lista de palavras-chave foi usada, as estatísticas uma das palavras-chave são exibidas.

  Veja algumas outras coisas que você precisa saber sobre as estatísticas exibidas na coluna **consultas** :
  
  - Quando você procura todo o conteúdo nas caixas de correio (não especificando nenhuma palavra-chave), a consulta real é **(tamanho >= 0)** para que todos os itens sejam retornados
  
  - Quando você pesquisa sites do SharePoint e do OneDrive, os dois componentes a seguir são adicionados à consulta de pesquisa:
    
    **Não IsExternalContent: 1** -isso exclui qualquer conteúdo de uma organização local do SharePoint
    
    **Não isOneNotePage: 1** -isso exclui todos os arquivos do OneNote porque eles seriam duplicatas de qualquer documento que corresponda à consulta de pesquisa.

- **Locais na pesquisa** O número de locais de conteúdo que tinham itens que corresponderam à consulta de pesquisa da parte/condição exibida na linha. Observe que as caixas de correio de arquivo morto são contadas como um local separado, caso contenham itens que correspondam aos critérios de pesquisa.

- **Items** -o número total de itens que correspondem aos critérios de pesquisa para a parte/condição exibida na linha.

- **Size** -o número total de itens que correspondem aos critérios de pesquisa para a parte/condição exibida na linha.

