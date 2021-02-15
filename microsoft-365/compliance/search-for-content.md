---
title: Procurar conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.assetid: df2d1e0f-b476-42c9-aade-4a260b24f193
description: Use a ferramenta Descoberta eDiscover & y de Pesquisa de Conteúdo no Centro de Conformidade e Segurança para encontrar rapidamente emails em caixas de correio do Exchange, documentos em sites do SharePoint e locais do OneDrive e conversas de mensagens instantâneas no Skype for Business.
ms.openlocfilehash: 6a82846514b3510c4ff9f9b79eeff20b789ad0ad
ms.sourcegitcommit: 8ad481ed61cb6dabf8afb0fb04296666fa166450
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "49422850"
---
# <a name="search-for-content-using-the-content-search-tool"></a>Pesquisar conteúdo usando a ferramenta pesquisa de conteúdo

& Use a ferramenta Pesquisa de Conteúdo no Centro de Conformidade e Segurança para encontrar rapidamente emails em caixas de correio do Exchange, documentos em sites do SharePoint e locais do OneDrive e conversas de mensagens instantâneas no Skype for Business. Você pode usar a ferramenta de pesquisa de conteúdo para pesquisar emails, documentos e conversas de mensagens instantâneas em ferramentas de colaboração, como Microsoft Teams e Grupos do Microsoft 365.
  
## <a name="search-for-content"></a>Procurar conteúdo

A primeira etapa é começar a usar a ferramenta Pesquisa de Conteúdo para escolher locais de conteúdo para pesquisar e configurar uma consulta de palavra-chave para pesquisar itens específicos. Ou você pode simplesmente deixar a consulta em branco e retornar todos os itens nos locais de destino.
  
- [Criar e executar uma](content-search.md) pesquisa de conteúdo 

- [Criar consultas de pesquisa e usar condições para](keyword-queries-and-search-conditions.md) restringir sua pesquisa 

- [Configurar a filtragem de permissões de pesquisa](permissions-filtering-for-content-search.md) para que um gerente de Descoberta Eletrônico só possa pesquisar o subconjunto de caixas de correio ou sites em sua organização 

- [Executar uma pesquisa de lista de IDs](csv-file-for-an-id-list-content-search.md) para procurar mensagens de email específicas 

- [Pesquisar caixas de correio baseadas em nuvem ](search-cloud-based-mailboxes-for-on-premises-users.md) para usuários locais no Microsoft 365

- [Exibir estatísticas de palavra-chave](view-keyword-statistics-for-content-search.md) para os resultados de uma pesquisa e refinar a consulta, se necessário

- [Pesquisar dados de terceiros que](use-content-search-to-search-third-party-data-that-was-imported.md) sua organização importou para o Microsoft 365

- [Editar em massa](bulk-edit-content-searches.md) os locais de consulta e conteúdo para várias pesquisas

- [Repetir uma Pesquisa de Conteúdo para](retry-failed-content-search.md) resolver um erro de local de conteúdo

- [Preservar destinatários Cc](https://docs.microsoft.com/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) para que você possa pesquisá-los 

## <a name="perform-actions-on-content-you-find"></a>Executar ações no conteúdo que você encontrar

Depois de executar uma pesquisa e refiná-la conforme necessário, a próxima etapa é fazer algo com os resultados retornados pela pesquisa. Você pode exportar e baixar os resultados para o computador local ou, no caso de um ataque de email em sua organização, você pode excluir os resultados de uma pesquisa das caixas de correio do usuário.
  
- [Exportar os resultados de uma pesquisa de conteúdo](export-search-results.md) e baixá-los para o computador local 

- [Pesquisar e excluir mensagens de email,](search-for-and-delete-messages-in-your-organization.md) como mensagens que contendam vírus, anexos perigosos ou mensagens de phishing

- [Exportar um relatório](export-a-content-search-report.md) sobre os resultados de uma pesquisa de conteúdo, sem exportar os resultados reais 

## <a name="learn-more-about-content-search"></a>Saiba mais sobre a pesquisa de conteúdo

A Pesquisa de Conteúdo é fácil de usar, mas também é uma ferramenta poderosa. Nos bastidores, há muita coisa acontecendo. Quanto mais você conhecer e entender seu comportamento e suas limitações, mais bem-sucedido você o utilizará para as necessidades de pesquisa e investigação da sua organização. Saiba mais:
  
- [Itens parcialmente indexados no Exchange e no SharePoint](partially-indexed-items-in-content-search.md) e como incluí-los ou exclui-los quando você exporta e baixa os resultados da pesquisa

- [Investigar itens parcialmente indexados](investigating-partially-indexed-items-in-ediscovery.md) e determinar a exposição da sua organização a eles

- [Limites da ferramenta pesquisa de](limits-for-content-search.md)conteúdo , como o número máximo de pesquisas que você pode executar de uma só vez e o número máximo de locais de conteúdo que você pode incluir em uma única pesquisa

- [Resultados estimados e reais da pesquisa](differences-between-estimated-and-actual-ediscovery-search-results.md) e os motivos pelos quais pode haver diferenças entre eles quando você exporta e baixa os resultados da pesquisa

- [Des duplicação nos resultados da pesquisa](de-duplication-in-ediscovery-search-results.md) que você pode habilitar ao exportar mensagens de email que são os resultados de uma pesquisa

## <a name="use-scripts-for-advanced-scenarios"></a>Usar scripts para cenários avançados

Às vezes, você precisa executar tarefas de pesquisa de conteúdo mais avançadas, complexas e repetitivas. Nesses casos, é mais fácil e rápido usar comandos do PowerShell no Centro de Conformidade & Segurança. Para ajudar a facilitar isso, criamos vários scripts do PowerShell do Centro de Conformidade e Segurança para ajudá-lo & a concluir tarefas complexas relacionadas à pesquisa de conteúdo.
  
- [Pesquise](use-content-search-for-targeted-collections.md) pastas de site e caixa de correio específicas (chamada de *conjunto direcionado) quando você tem certeza de que os itens responsivos a um caso estão localizados nessa pasta

- [Pesquisar a caixa de correio e o local do OneDrive](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) para uma lista de usuários 

- [Criar, relatar e excluir várias pesquisas para](create-report-on-and-delete-multiple-content-searches.md) identificar e remover dados de pesquisa de forma rápida e eficiente 

- [Clone uma pesquisa de conteúdo](clone-a-content-search.md) e compare rapidamente os resultados de diferentes consultas de pesquisa de palavra-chave executados nos mesmos locais de conteúdo; ou use o script para economizar tempo sem precisar inserir um grande número de locais de conteúdo ao criar uma nova pesquisa
