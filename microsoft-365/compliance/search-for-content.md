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
description: Use a ferramenta Descoberta e Descoberta De Pesquisa de Conteúdo no Centro de Conformidade & Segurança para encontrar rapidamente emails em caixas de correio do Exchange, documentos em sites SharePoint e locais OneDrive e conversas de mensagens instantâneas no Skype for Business.
ms.openlocfilehash: 80234a512d13deda29a61073bec62990d135f30e
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333681"
---
# <a name="search-for-content-using-the-content-search-tool"></a>Pesquisar conteúdo usando a ferramenta pesquisa de conteúdo

Use a ferramenta Pesquisa de Conteúdo no Centro de Conformidade & Segurança para encontrar rapidamente emails em caixas de correio do Exchange, documentos em sites SharePoint e locais OneDrive e conversas de mensagens instantâneas no Skype for Business. Você pode usar a ferramenta de pesquisa de conteúdo para pesquisar emails, documentos e conversas de mensagens instantâneas em ferramentas de colaboração, como Microsoft Teams e Microsoft 365 Grupos.
  
## <a name="search-for-content"></a>Procurar conteúdo

A primeira etapa é começar a usar a ferramenta Pesquisa de Conteúdo para escolher locais de conteúdo para pesquisar e configurar uma consulta de palavra-chave para pesquisar itens específicos. Ou você pode deixar a consulta em branco e retornar todos os itens nos locais de destino.
  
- [Criar e executar](content-search.md) uma pesquisa de conteúdo

- [Referência de recurso] para pesquisa de conteúdo (content-search-reference.md)

- [Criar consultas de pesquisa e usar condições para](keyword-queries-and-search-conditions.md) restringir sua pesquisa 

- [Configurar a filtragem de permissões de pesquisa](permissions-filtering-for-content-search.md) para que um gerente de Descoberta Eletrônico só possa pesquisar o subconjunto de caixas de correio ou sites em sua organização 

- [Execute uma pesquisa de lista de ID para](csv-file-for-an-id-list-content-search.md) pesquisar mensagens de email específicas 

- [Pesquisar caixas de correio baseadas](search-cloud-based-mailboxes-for-on-premises-users.md) em nuvem para usuários locais em Microsoft 365

- [Exibir estatísticas de palavra-chave](view-keyword-statistics-for-content-search.md) para os resultados de uma pesquisa e refinar a consulta, se necessário

- [Pesquise dados de](use-content-search-to-search-third-party-data-that-was-imported.md) terceiros que sua organização importou para Microsoft 365

- [Editar em massa](bulk-edit-content-searches.md) os locais de consulta e conteúdo para várias pesquisas

- [Repetir uma Pesquisa de Conteúdo para](retry-failed-content-search.md) resolver um erro de local de conteúdo

- [Preservar destinatários Cc](/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) para que você possa pesquisá-los 

## <a name="perform-actions-on-content-you-find"></a>Executar ações no conteúdo que você encontra

Depois de executar uma pesquisa e refiná-la conforme necessário, a próxima etapa é fazer algo com os resultados retornados pela pesquisa. Você pode exportar e baixar os resultados para seu computador local ou, no caso de um ataque de email em sua organização, você pode excluir os resultados de uma pesquisa de caixas de correio de usuário.
  
- [Exportar os resultados de uma pesquisa de conteúdo](export-search-results.md) e baixá-los para o computador local 

- [Pesquise e exclua](search-for-and-delete-messages-in-your-organization.md) mensagens de email , como mensagens que contendam vírus, anexos perigosos ou mensagens de phishing

- [Exportar um relatório](export-a-content-search-report.md) sobre os resultados de uma pesquisa de conteúdo, sem exportar os resultados reais 

## <a name="learn-more-about-content-search"></a>Saiba mais sobre pesquisa de conteúdo

A Pesquisa de Conteúdo é fácil de usar, mas também é uma ferramenta poderosa. Nos bastidores, há muita coisa acontecendo. Quanto mais você conhecer e entender seu comportamento e suas limitações, mais bem-sucedido você o estará usando para as necessidades de pesquisa e investigação da sua organização. Saiba mais:
  
- [Itens parcialmente indexados em](partially-indexed-items-in-content-search.md) Exchange e SharePoint e como incluí-los ou excluir quando você exporta e baixa resultados de pesquisa

- [Investigar itens parcialmente indexados](investigating-partially-indexed-items-in-ediscovery.md) e determinar a exposição da sua organização a eles

- [Limites da](limits-for-content-search.md)ferramenta pesquisa de conteúdo , como o número máximo de pesquisas que você pode executar de uma vez e o número máximo de locais de conteúdo que você pode incluir em uma única pesquisa

- [Resultados de pesquisa estimados e reais](differences-between-estimated-and-actual-ediscovery-search-results.md) e os motivos pelos quais pode haver diferenças entre eles quando você exporta e baixa resultados da pesquisa

- [Des duplicação nos resultados de](de-duplication-in-ediscovery-search-results.md) pesquisa que você pode habilitar ao exportar mensagens de email que são os resultados de uma pesquisa

## <a name="use-scripts-for-advanced-scenarios"></a>Usar scripts para cenários avançados

Às vezes, você precisa executar tarefas de pesquisa de conteúdo mais avançadas, complexas e repetitivas. Nesses casos, é mais fácil e rápido usar comandos do PowerShell no Centro de Conformidade & Segurança. Para ajudar a facilitar isso, criamos vários scripts do Centro de Conformidade e Segurança do PowerShell para ajudá-lo & a concluir tarefas complexas relacionadas à pesquisa de conteúdo.
  
- [Pesquise](use-content-search-for-targeted-collections.md) pastas de site e de caixa de correio específicas (chamadas de coleção *targeted) quando você tem certeza de que os itens que respondem a uma ocorrência estão localizados nessa pasta

- [Pesquisar a caixa de correio e OneDrive local](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) para uma lista de usuários 

- [Criar, relatar e excluir várias pesquisas para](create-report-on-and-delete-multiple-content-searches.md) identificar e eliminar dados de pesquisa de forma rápida e eficiente 

- [Clone uma pesquisa de conteúdo](clone-a-content-search.md) e compare rapidamente os resultados de diferentes consultas de pesquisa de palavra-chave executados nos mesmos locais de conteúdo; ou use o script para economizar tempo sem precisar inserir um grande número de locais de conteúdo ao criar uma nova pesquisa