---
title: Pesquisar conteúdo em um caso principal de Descoberta eDiscovery
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
description: Pesquise por conteúdo que possa ser relevante para um caso de Descoberta Principal de Descoberta e.
ms.openlocfilehash: 8d2e2a20135312a8f111a071abbe77b03b8e8363
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311767"
---
# <a name="search-for-content-in-a-core-ediscovery-case"></a>Pesquisar conteúdo em um caso core de Descoberta eDiscovery

Depois que um caso core de Descoberta eDiscovery é criado e as pessoas de interesse no caso são colocadas em espera, você pode criar e executar uma ou mais pesquisas de conteúdo relevante para o caso. As pesquisas associadas a um caso de Descoberta Básica  de Descoberta e não estão listadas na página de pesquisa de conteúdo no centro de conformidade Microsoft 365. Essas pesquisas estão listadas na página **Pesquisas** da ocorrência principal de Descoberta eDiscover à que as pesquisas estão associadas. Isso também significa que as pesquisas associadas a um caso só podem ser acessadas por membros da ocorrência.

Para criar uma pesquisa principal de Descoberta eDiscovery:
  
1. Acesse e entre usando as credenciais da conta de usuário que recebeu as permissões de <https://compliance.microsoft.com> Descoberta eDiscovery apropriadas e é membro do caso.

2. No painel de navegação esquerdo do centro de conformidade Microsoft 365, clique em **Mostrar** tudo e clique em **Descoberta > Core**.

3. Na página **Descoberta Principal da Descoberta** e, em seguida, selecione o caso que você deseja criar uma pesquisa associada e clique em Abrir **caso**.

4. Na **home** page do caso, clique na guia **Pesquisas** e clique em **Nova pesquisa**.

   ![Clique em Nova pesquisa para criar uma pesquisa principal de Descoberta EDiscovery](../media/CoreeDiscoverySearch1.png)

   > [!NOTE]
   > A **opção Pesquisar por ID** permite que você pesquise mensagens de email específicas e outros itens de caixa de correio usando uma lista de Exchange IDs. Para criar uma pesquisa de lista de IDs, você envia um arquivo de valores separados por vírgula (CSV) que identifica os itens específicos da caixa de correio a serem pesquisados. Para obter instruções, confira [Preparar um arquivo CSV para uma pesquisa de lista de IDs](csv-file-for-an-id-list-content-search.md).

5. No assistente **Nova pesquisa,** digite um nome para a pesquisa e uma descrição opcional que ajuda a identificar a pesquisa. O nome da pesquisa deve ser exclusivo em sua organização.

6. Na página **Locais,** escolha os locais de conteúdo que você deseja pesquisar. Você pode pesquisar caixas de correio, sites e pastas públicas.

    ![Escolher os locais de conteúdo para colocar em espera](../media/ContentSearchLocations.png)
  
   1. **Exchange caixas de** correio : de  definir a alternância como On e clique em Escolher usuários, grupos ou **equipes** para especificar as caixas de correio que devem ser colocadas em espera. Use a caixa de pesquisa para encontrar caixas de correio de usuário e grupos de distribuição (para colocar uma responsabilidade nas caixas de correio dos membros do grupo) para colocar em espera. Você também pode pesquisar a caixa de correio associada a uma Equipe da Microsoft (para mensagens de canal), Office 365 Group e Yammer Group. Para obter mais informações sobre os dados do aplicativo armazenados em caixas de correio, consulte Conteúdo armazenado em caixas de [correio para Descoberta Eletrônico.](what-is-stored-in-exo-mailbox.md)

   2. **SharePoint :** de definir a alternância como On e clique em Escolher **sites** para especificar SharePoint sites e OneDrive contas para colocar em espera.  Digite a URL de cada site que você deseja colocar em retenção. Você também pode adicionar a URL do site SharePoint para uma Equipe da Microsoft, Office 365 Group ou Yammer Group.
  
   3. **Exchange pastas públicas**: de definir a alternância como **On** para colocar todas as pastas públicas em sua Exchange Online organização em espera. Não é possível escolher pastas públicas específicas para colocar em espera. Deixe o botão de alternância desligado se você não quiser colocar uma espera em pastas públicas.
  
   4. Mantenha essa caixa de seleção selecionada para pesquisar Teams conteúdo para usuários locais. Por exemplo, se você pesquisar todas as caixas de correio Exchange na organização e essa caixa de seleção estiver selecionada, o armazenamento baseado em nuvem usado para armazenar dados de chat Teams para usuários locais será incluído no escopo da pesquisa. Para obter mais informações, confira [Pesquisar dados de bate-papo do Teams para usuários locais](search-cloud-based-mailboxes-for-on-premises-users.md).

7. Na página **Definir suas condições de pesquisa,** digite uma consulta de palavra-chave e adicione condições à consulta de pesquisa, se necessário.

   ![Configurar a consulta de pesquisa](../media/ContentSearchQuery.png)

   1. Especifique palavras-chave, propriedades de mensagem, como datas enviadas e recebidas, ou propriedades de documento, como nomes de arquivo ou a data em que um documento foi alterado pela última vez. Faça consultas mais complexas que usam um operador Booleano, **E**, **OU**, **NÃO** e **PRÓXIMO**. Se você deixar a caixa de palavra-chave vazia, todo o conteúdo localizado nos locais de conteúdo especificado será incluído nos resultados da pesquisa. Para obter mais informações, consulte [Consultas de palavra-chave e condições de pesquisa para eDiscovery](keyword-queries-and-search-conditions.md).

   2. Como alternativa, você pode clicar na caixa de seleção **Mostrar lista de palavras-chave** e digitar uma palavra-chave em cada linha. Ao fazer isso, as palavras-chave em cada linha serão conectadas por um operador lógico (**c:s**) com funcionalidade semelhante ao operador **OU** na consulta de pesquisa criada.

      Por que usar a lista de palavras-chave? Para obter estatísticas que mostram quantos itens correspondem a cada palavra-chave. Isso ajudará a identificar rapidamente quais palavras-chave são as mais recentes. Também poderá usar uma frase de palavra-chave (entre parênteses) em uma linha. Para obter mais informações sobre a lista de palavras-chave e estatísticas de pesquisa, consulte Obter estatísticas de palavra-chave [para pesquisas](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).

      > [!NOTE]
      > Para ajudar a reduzir problemas causados por listas de palavras-chave grandes, você está limitado a no máximo 20 linhas na lista de palavras-chave.

   3. Você pode adicionar condições de pesquisa para restringir uma pesquisa e retornar um conjunto mais refinado de resultados. Cada condição adiciona uma cláusula à consulta de pesquisa que é criada e executada quando você inicia a pesquisa. Uma condição é logicamente conectada à consulta de palavra-chave (especificada na caixa de palavra-chave) por um operador lógico (**c:c**) parecido com a funcionalidade do operador **E**. Isso significa que os itens precisam atender à consulta de palavras-chave e uma ou mais condições para serem incluídas nos resultados. É assim que as condições ajudam a restringir os resultados. Para obter uma lista e uma descrição das condições que podem ser usadas em uma consulta de pesquisa, confira a seção [Condições de pesquisa](keyword-queries-and-search-conditions.md#search-conditions).

8. Revise as configurações de pesquisa (e edite se necessário) e envie a pesquisa para in-locar.

Após a conclusão da pesquisa, você poderá visualizar os resultados. Se necessário, clique **em Atualizar** na **página Pesquisas** para exibir a pesquisa criada.

## <a name="more-information-about-searching-content-locations"></a>Mais informações sobre a pesquisa de locais de conteúdo

- Quando você clica **em Escolher usuários, grupos** ou equipes para especificar caixas de correio para pesquisar, o seletor de caixa de correio exibido está vazio. Isso foi desenvolvido para melhorar o desempenho. Para adicionar destinatários a essa lista, clique em Escolher **usuários,** grupos ou equipes , digite um nome (no mínimo três caracteres) na caixa de pesquisa, marque a caixa de seleção ao lado do nome e clique em **Escolher**.

- Você pode adicionar caixas de correio inativas, Microsoft Teams, grupos Yammer, grupos de Office 365 e grupos de distribuição à lista de caixas de correio a ser pesquisada. Não há suporte para grupos dinâmicos de distribuição. Se você adicionar Microsoft Teams, Yammer grupos ou Office 365 grupos, a caixa de correio do grupo ou da equipe será pesquisada; as caixas de correio dos membros do grupo não são pesquisadas.

- Para adicionar sites à pesquisa, acione a alternância e clique **em Escolher sites**. Digite a URL para cada site que você deseja pesquisar. Você também pode adicionar a URL do site SharePoint para uma Equipe da Microsoft, um grupo Yammer ou um grupo Office 365.
