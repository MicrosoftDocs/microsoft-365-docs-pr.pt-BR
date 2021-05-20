---
title: Visualizar os resultados de uma pesquisa de Descoberta eletrônica
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Visualizar um exemplo dos resultados retornados por uma Pesquisa de conteúdo ou uma pesquisa de Descoberta eletrônica Principal no Centro de Conformidade do Microsoft 365.
ms.openlocfilehash: a89c8c9ed2500b4e2a859c75be3da177203d1406
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538575"
---
# <a name="preview-ediscovery-search-results"></a>Visualização de resultados de pesquisa da Descoberta Eletrônica

Depois de executar uma pesquisa de Conteúdo ou uma pesquisa associada a um caso de Descoberta eletrônica principal, você pode visualizar uma amostra dos resultados retornados pela pesquisa. A visualização de itens retornados pela consulta de pesquisa pode ajudá-lo a determinar se a pesquisa está retornando os resultados que você espera ou se você precisa alterar a consulta de pesquisa e realizar a pesquisa outra vez.

Para visualizar um exemplo de resultados retornados por uma pesquisa:

1. No Centro de Conformidade do Microsoft 365, vá para a página de Pesquisa de conteúdo ou um caso de Descoberta eletrônica principal.

2. Selecione a pesquisa para exibir a página de sobrevoo.

3. Na parte inferior da página de sobrevoo, clique em **Revisar exemplo**.

   ![Clique em Revisar exemplo na página flyout para exibir os resultados](../media/PreviewSearchResults1.png)

   É exibida uma página contendo um exemplo dos resultados da pesquisa.

4. Selecione um item para exibir seu conteúdo no painel de leitura.

   ![Exibir itens no painel de leitura](../media/PreviewSearchResults2.png)

   Na captura de tela anterior, observe que as palavras-chave da consulta de pesquisa são realçadas quando você visualiza itens.

## <a name="how-the-search-result-samples-are-selected"></a>Como são selecionados os exemplos dos resultados da pesquisa

No máximo 1.000 itens selecionados aleatoriamente estão disponíveis para visualização. Além de serem selecionados aleatoriamente, os itens disponíveis para visualização também devem atender aos seguintes critérios:

- É possível visualizar no máximo 100 itens de um único local de conteúdo (uma caixa de correio ou um site). Isso significa que é possível que menos de 1.000 itens possam estar disponíveis para visualização. Por exemplo, se você pesquisar quatro caixas de correio e a pesquisa retornar 1.500 itens estimados, apenas 400 estarão disponíveis para visualização porque somente 100 itens de cada caixa de correio podem ser visualizados.

- Para itens de caixa de correio, apenas as mensagens de email estão disponíveis para visualização. Itens como tarefas, itens de calendário e contatos não podem ser visualizados.

- Para itens de site, somente os documentos estão disponíveis para visualização. Itens como pastas, listas ou anexos de listas não podem ser visualizados.

## <a name="file-types-supported-when-previewing-search-results"></a>Tipos de arquivos com suporte durante a visualização de resultados da pesquisa

É possível visualizar os tipos de arquivo com suporte no painel de visualização. Se não há suporte para um tipo de arquivo, você precisa baixar uma cópia do arquivo no computador local (clicando em **Baixar o item original**). Para páginas da Web .aspx, a URL da página está incluída, mas pode ser que não haja permissões para acessar a página. Itens não indexados não estão disponíveis para visualização.

Os seguintes tipos de arquivo têm suporte e podem ser visualizados no painel de resultados da pesquisa.
  
- .txt, .html, .mhtml

- .eml

- .doc, .docx, .docm

- .pptm, .pptx

- .pdf

Além disso, os seguintes tipos de contêiner de arquivos possuem suporte. Você pode exibir a lista de arquivos no contêiner no painel de visualização.
  
- .zip

- .gzip