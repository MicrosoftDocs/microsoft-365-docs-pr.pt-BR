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
description: Use a ferramenta descoberta eletrônica de pesquisa de conteúdo no centro de conformidade de & de segurança para localizar rapidamente emails em caixas de correio do Exchange, documentos em sites do SharePoint e locais do OneDrive e conversas de mensagens instantâneas no Skype for Business.
ms.openlocfilehash: 6a82846514b3510c4ff9f9b79eeff20b789ad0ad
ms.sourcegitcommit: 8ad481ed61cb6dabf8afb0fb04296666fa166450
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "49422850"
---
# <a name="search-for-content-using-the-content-search-tool"></a>Pesquisar conteúdo usando a ferramenta de pesquisa de conteúdo

Use a ferramenta de pesquisa de conteúdo no centro de conformidade de & de segurança para localizar rapidamente emails em caixas de correio do Exchange, documentos em sites do SharePoint e do OneDrive e conversas de mensagens instantâneas no Skype for Business. Você pode usar a ferramenta de pesquisa de conteúdo para pesquisar emails, documentos e conversas de mensagens instantâneas em ferramentas de colaboração, como Microsoft Teams e Microsoft 365 groups.
  
## <a name="search-for-content"></a>Procurar conteúdo

A primeira etapa é começar a usar a ferramenta de pesquisa de conteúdo para escolher os locais de conteúdo para pesquisar e configurar uma consulta de palavra-chave para procurar itens específicos. Ou você pode simplesmente deixar a consulta em branco e retornar todos os itens nos locais de destino.
  
- [Criar e executar](content-search.md) uma pesquisa de conteúdo 

- [Criar consultas de pesquisa e usar condições](keyword-queries-and-search-conditions.md) para restringir a pesquisa 

- [Configurar a filtragem de permissões de pesquisa](permissions-filtering-for-content-search.md) para que um gerente de descoberta eletrônica possa Pesquisar apenas o subconjunto de sites ou caixas de correio em sua organização 

- [Executar uma pesquisa de lista de ID](csv-file-for-an-id-list-content-search.md) para pesquisar mensagens de email específicas 

- [Pesquisar caixas de correio baseadas em nuvem ](search-cloud-based-mailboxes-for-on-premises-users.md) para usuários locais no Microsoft 365

- [Exibir estatísticas de palavras-chave](view-keyword-statistics-for-content-search.md) para os resultados de uma pesquisa e depois refinar a consulta, se necessário

- [Pesquisar dados de terceiros](use-content-search-to-search-third-party-data-that-was-imported.md) que sua organização tenha importado para o Microsoft 365

- [Editar em massa](bulk-edit-content-searches.md) os locais de consulta e conteúdo para várias pesquisas

- [Repetir uma pesquisa de conteúdo](retry-failed-content-search.md) para resolver um erro de localização de conteúdo

- [Preservar destinatários Cco](https://docs.microsoft.com/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) para que você possa procurá-los 

## <a name="perform-actions-on-content-you-find"></a>Executar ações no conteúdo que você encontrar

Após executar uma pesquisa e refiná-la conforme necessário, a próxima etapa é fazer algo com os resultados retornados pela pesquisa. Você pode exportar e baixar os resultados para o seu computador local ou no caso de um ataque de email em sua organização, você pode excluir os resultados de uma pesquisa de caixas de correio do usuário.
  
- [Exportar os resultados de uma pesquisa de conteúdo](export-search-results.md) e baixá-los no computador local 

- [Procurar e excluir mensagens de email](search-for-and-delete-messages-in-your-organization.md) , como mensagens que contenham vírus, anexos perigosos ou mensagens de phishing

- [Exportar um relatório](export-a-content-search-report.md) sobre os resultados de uma pesquisa de conteúdo, sem exportar os resultados reais 

## <a name="learn-more-about-content-search"></a>Saiba mais sobre a pesquisa de conteúdo

A pesquisa de conteúdo é fácil de usar, mas também é uma poderosa ferramenta. Por trás das cenas, há muito em andamento. Quanto mais você souber sobre ele e entender seu comportamento e suas limitações, mais bem-sucedida você o usará para as necessidades de pesquisa e investigação da sua organização. Saiba mais:
  
- [Itens parcialmente indexados no Exchange e no SharePoint](partially-indexed-items-in-content-search.md) e como incluí-los ou excluí-los ao exportar e baixar os resultados da pesquisa

- [Investigar itens parcialmente indexados](investigating-partially-indexed-items-in-ediscovery.md) e determinar a exposição da sua organização a eles

- Os [limites da ferramenta de pesquisa de conteúdo](limits-for-content-search.md), como o número máximo de pesquisas que podem ser executadas ao mesmo tempo e o número máximo de locais de conteúdo que podem ser incluídos em uma única pesquisa

- [Resultados de pesquisa estimados e reais](differences-between-estimated-and-actual-ediscovery-search-results.md) e os motivos pelos quais pode haver diferenças entre eles ao exportar e baixar os resultados da pesquisa

- [Desduplicação nos resultados de pesquisa](de-duplication-in-ediscovery-search-results.md) que você pode habilitar ao exportar mensagens de email que são os resultados de uma pesquisa

## <a name="use-scripts-for-advanced-scenarios"></a>Usar scripts para cenários avançados

Às vezes, você precisa executar tarefas de pesquisa de conteúdo mais avançadas, complexas e repetitivas. Nesses casos, é mais fácil e rápido usar os comandos do PowerShell no centro de conformidade do & de segurança. Para ajudá-lo a simplificar isso, criamos vários scripts do PowerShell do centro de conformidade & central de segurança para ajudá-lo a concluir tarefas relacionadas à pesquisa de conteúdo complexo.
  
- [Pesquisar caixas de correio e pastas de site específicas](use-content-search-for-targeted-collections.md) (chamadas de uma coleção de destino) quando você tiver certeza de que os itens que respondem a um caso estão localizados nessa pasta

- [Pesquisar a caixa de correio e o local do onedrive](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) para obter uma lista de usuários 

- [Criar, relatar e excluir várias pesquisas](create-report-on-and-delete-multiple-content-searches.md) para identificar e analisar de forma rápida e eficiente os dados de pesquisa 

- [Clonar uma pesquisa de conteúdo](clone-a-content-search.md) e comparar rapidamente os resultados das diferentes consultas de pesquisa de palavras-chave executadas nos mesmos locais de conteúdo; ou use o script para economizar tempo não precisa reinserir um grande número de locais de conteúdo ao criar uma nova pesquisa
