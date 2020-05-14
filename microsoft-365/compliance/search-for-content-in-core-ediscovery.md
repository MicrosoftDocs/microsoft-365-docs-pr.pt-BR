---
title: Pesquisar conteúdo em um caso de descoberta eletrônica principal
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Você pode pesquisar conteúdo que possa ser relevante para uma caixa de descoberta eletrônica principal.
ms.openlocfilehash: d17a9d16643ec9077e02b5438597237b80f09af5
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224618"
---
# <a name="search-for-content-in-a-core-ediscovery-case"></a>Pesquisar conteúdo em um caso de descoberta eletrônica principal

Depois que um caso de descoberta eletrônica principal é criado e as pessoas de interesse no caso são colocadas em espera, você pode criar e executar uma ou mais pesquisas de conteúdo relevante para o caso. As pesquisas associadas a um caso de descoberta eletrônica principal não estão listadas na página de **pesquisa de conteúdo** no centro de conformidade da Microsoft 365. Essas pesquisas são listadas na página **pesquisas** do caso principal do eDiscover as pesquisas estão associadas. Isso também significa que as pesquisas associadas a um caso podem ser acessadas apenas por membros de caso.

Para criar uma pesquisa de descoberta eletrônica principal:
  
1. Acesse [https://compliance.microsoft.com](https://compliance.microsoft.com) e entre usando as credenciais da conta de usuário que receberam as permissões de descoberta eletrônica apropriadas.

2. No painel de navegação esquerdo do centro de conformidade da Microsoft 365, clique em **Mostrar tudo**e, em seguida, clique em **descoberta eletrônica > Core**.

3. Na página de **descoberta eletrônica principal** , selecione o caso para o qual você deseja criar uma pesquisa associada e clique em **abrir caso**.

4. Na **Home** Page do caso, clique na guia **pesquisas** .
  
5. Na página de **pesquisa** , clique em **nova pesquisa**.

6. Na página **Nova pesquisa**, você pode adicionar palavras-chave e condições para criar a consulta de pesquisa. 

    ![Nova pesquisa](../media/0e9954e7-c0ea-4e05-820b-e4b81dc5f81d.png)
  
   a. Você pode especificar palavras-chave, propriedades de mensagem, como datas de envio e recebimento, ou propriedades do documento, como nomes de arquivo ou a data em que um documento foi alterado pela última vez. Você pode usar consultas mais complexas que usam um operador Boolean, como **e**, **ou**, **não**ou **Near**. Você também pode procurar informações confidenciais (por exemplo, números de seguridade social) em documentos ou pesquisar documentos que foram compartilhados externamente. Se você deixar a caixa de palavras-chave vazia, todo o conteúdo localizado nos locais de conteúdo especificado será incluído nos resultados da pesquisa.

   b. Você pode clicar na caixa de seleção **Mostrar lista de palavras-chave** e a palavra-chave tipo a em cada linha. Se você fizer isso, as palavras-chave em cada linha serão conectadas pelo operador **or** na consulta de pesquisa criada. Você pode inserir no máximo 20 palavras-chave na lista.

    ![Lista de palavras-chave](../media/29cceb5d-2817-4fc4-b91a-ced1c5824a17.png)
  
    Por que usar a lista de palavras-chave? Para obter estatísticas que mostram quantos itens correspondem a cada palavra-chave. Isso ajudará a identificar rapidamente quais palavras-chave são as mais recentes. Também poderá usar uma frase de palavra-chave (entre parênteses) em uma linha. Para obter mais informações sobre as estatísticas de pesquisa, confira [Exibir estatísticas da palavra-chave para Resultados de Pesquisa de Conteúdo](view-keyword-statistics-for-content-search.md).

    Para obter mais informações sobre como usar a lista de palavras-chave, consulte [criando uma consulta de pesquisa](content-search.md#building-a-search-query).

   c. Você pode clicar em **condições** e adicionar condições a uma consulta de pesquisa para restringir uma pesquisa e retornar um conjunto mais refinado de resultados. Cada condição adiciona uma cláusula à consulta de pesquisa KQL que é criada e executada quando você inicia a pesquisa. Uma condição é logicamente conectada à consulta de palavra-chave (especificada na caixa de palavra-chave) pelo operador **AND**. Isso significa que os itens precisam satisfazer tanto a consulta de palavra-chave quanto cada condição a ser incluído nos resultados. É assim que as condições ajudam a restringir os resultados.

    Para saber mais sobre como criar uma consulta de pesquisa e usar condições, confira [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).

7. Em **locais: locais em espera**, escolha os locais de conteúdo que você deseja pesquisar. Você pode pesquisar caixas de correio, sites e pastas públicas na mesma pesquisa.

    ![Locais, locais em espera](../media/d56398aa-0b20-4500-8e26-494eab92a99f.png)
  
    - **Todos os locais**. Selecione essa opção para pesquisar em todos os locais de conteúdo da sua organização. Ao selecionar essa opção, você pode optar por pesquisar todas as caixas de correio do Exchange (que inclui as caixas de correio de todos os grupos do Microsoft Teams, do Yammer e do Office 365), todos os sites do SharePoint e do OneDrive for Business (que inclui os sites de todos os grupos do Microsoft Teams, do Yammer e do Office 365) e todas as pastas públicas.
    
    - **Todos os locais em espera**. Selecione essa opção para pesquisar todos os locais de conteúdo que foram colocados em retenção de descoberta eletrônica no caso. Se o caso contiver várias isenções, os locais de conteúdo de todas as isenções serão pesquisados. Além disso, se um local de conteúdo foi colocado em um bloqueio baseado em consulta, somente os itens que estão em retenção serão pesquisados quando você executar a pesquisa de conteúdo que você está criando nesta etapa. Por exemplo, se um usuário foi colocado em um bloqueio de caso baseado em consulta que preserva os itens que foram enviados ou criados antes de uma data específica, somente esses itens seriam pesquisados. Isso é feito conectando-se à consulta de retenção de caso e à consulta de pesquisa de conteúdo por um operador **and** . Para saber mais, confira [locais de pesquisa em retenção de descoberta eletrônica](create-ediscovery-holds.md#search-locations-on-ediscovery-hold).
    
    - **Locais específicos**. Selecione essa opção para selecionar as caixas de correio e os sites que você deseja pesquisar. Quando você seleciona essa opção e clica em **Modificar**, uma lista de locais é exibida. Você pode optar por pesquisar qualquer um ou todos os usuários, grupos, equipes ou locais de sites. Você também pode pesquisar as pastas públicas em sua organização.
    
      ![Selecionar locais específicos](../media/97469b15-7be1-4aee-be27-f8343636152c.png)
  
     Se você selecionar essa opção e pesquisar qualquer local de conteúdo em espera, qualquer consulta de um bloqueio de caso baseado em consulta não será aplicada à consulta de pesquisa. Em outras palavras, todo o conteúdo é pesquisado, e não apenas o conteúdo que é preservado por um bloqueio de caso baseado em consulta.

8. Depois de selecionar os locais de conteúdo para pesquisa, clique em **concluído** e, em seguida, clique em **salvar**.

9. Na página **nova pesquisa** , clique em **salvar & executar** e digite um nome para a pesquisa. As pesquisas associadas a um caso de descoberta eletrônica principal devem ter nomes exclusivos na sua organização do Office 365.

10. Clique em **salvar** para salvar as configurações de pesquisa e iniciar a pesquisa.

  Após a conclusão da pesquisa, você poderá visualizar os resultados. Se necessário, clique em **Atualizar** na página **pesquisas** para exibir a pesquisa criada na lista.

11. Clique na pesquisa para exibir a página de menu suspenso, que contém estatísticas sobre a pesquisa e para executar outras tarefas, como exibir estatísticas de pesquisa e exportar os resultados da pesquisa.

## <a name="more-information-about-searching-content-locations"></a>Mais informações sobre como pesquisar locais de conteúdo

- Ao clicar em **escolher usuários, grupos ou equipes** para especificar as caixas de correio a serem pesquisadas, o seletor de caixa de correio exibido estará vazio. Isso foi desenvolvido para melhorar o desempenho. Para adicionar destinatários a essa lista, clique em **escolher usuários, grupos ou equipes**, digite um nome (no mínimo 3 caracteres) na caixa de pesquisa, marque a caixa de seleção ao lado do nome e clique em **escolher**.

- Você pode adicionar caixas de correio inativas, Microsoft Teams, grupos do Yammer, grupos do Office 365 e grupos de distribuição à lista de caixas de correio a serem pesquisadas. Não há suporte para grupos dinâmicos de distribuição. Se você adicionar o Microsoft Teams, os grupos do Yammer ou os grupos do Office 365, a caixa de correio de grupo ou equipe será pesquisada; as caixas de correio dos membros do grupo não são pesquisadas.

- Para adicionar **sites, clique em escolher sites**, clique em **escolher sites** novamente e digite a URL de cada site que você deseja pesquisar. Você também pode adicionar a URL para o site do SharePoint para uma equipe da Microsoft, um grupo do Yammer ou um grupo do Office 365.
