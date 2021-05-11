---
title: Criar e executar uma pesquisa de conteúdo no Centro de Conformidade do Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
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
description: Use a ferramenta de Pesquisa de Conteúdo no centro de conformidade da Microsoft para pesquisar conteúdo em diferentes serviços do Microsoft 365.
ms.openlocfilehash: a058c07d080962723e9f6bc7a150cbfb5074e7db
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311648"
---
# <a name="create-a-content-search"></a>Criar uma pesquisa de conteúdo

Você pode usar a ferramenta de Descoberta eletrônica de Pesquisa de Conteúdo no Centro de conformidade do Microsoft 365 para pesquisar conteúdos in-loco como e-mails, documentos e conversas de mensagens instantâneas em sua organização. Use esta ferramenta para pesquisar conteúdo nestas fontes de dados do Microsoft 365:
  
- Caixas de correio do Exchange Online.

- Sites do SharePoint Online e contas do OneDrive for Business

- Microsoft Teams

- Grupos do Microsoft 365

- Grupos do Yammer

Após a execução de uma Pesquisa de Conteúdo, o número de locais de conteúdo e um número estimado de resultados de pesquisa serão exibidos no perfil de pesquisa. As estatísticas podem ser visualizadas prontamente, como os locais de conteúdo que têm mais itens que correspondem à consulta de pesquisa. Ao executar uma pesquisa, elas poderão ser visualizadas ou exportadas para um computador local.

## <a name="create-and-run-a-search"></a>Criar e executar uma pesquisa

Para ter acesso à página da **Pesquisa de conteúdo** no Centro de conformidade do Microsoft 365 e poder executar pesquisas, visualizar e exportar resultados de pesquisa, um administrador, um responsável pela conformidade ou um gerente de descoberta eletrônica deve ser membro do grupo de função gerente de Descoberta eletrônica do Centro de Conformidade e Segurança. Para obter mais informações, confira [Atribuir permissões de Descoberta eletrônica](assign-ediscovery-permissions.md).
  
1. Vá para <https://compliance.microsoft.com> e entre usando as credenciais de uma conta que tenha sido atribuída às permissões apropriadas.

2. No painel de navegação esquerdo do Centro de Conformidade do Microsoft 365, clique em **Mostrar tudo** e, a seguir, clique em **Pesquisa de conteúdo**.

3. Na página **Pesquisa de conteúdo**, clique em **Nova pesquisa**.

   > [!NOTE]
   > A opção **Pesquisar por lista de IDs** permite que você pesquise mensagens de e-mail específicas e outros itens de caixa de correio usando uma lista de IDs do Exchange. Para criar uma pesquisa de lista de IDs, você envia um arquivo de valores separados por vírgula (CSV) que identifica os itens específicos da caixa de correio a serem pesquisados. Para obter instruções, confira [Preparar um arquivo CSV para uma pesquisa de lista de IDs](csv-file-for-an-id-list-content-search.md).

4. Digite um nome para a pesquisa, uma descrição opcional que ajude a identificar a pesquisa. O nome da pesquisa deve ser exclusivo na organização.

5. Na página **Locais**, escolha os locais de conteúdo que você deseja pesquisar. Você pode pesquisar em caixas de correio, sites e pastas públicas.

    ![Escolher os locais de conteúdo para colocar em espera](../media/ContentSearchLocations.png)
  
   1. **Caixas de correio do Exchange**: configure o botão de alternância como **Ativado** e, em seguida, clique em **Escolher usuários, grupos ou equipes** para especificar as caixas de correio a colocar em espera. Use a caixa de pesquisa para localizar caixas de correio de usuário e grupos de distribuição (para colocar em retenção as caixas de correio de membros do grupo) e colocar em espera. Você também pode pesquisar a caixa de correio associada a uma Equipe da Microsoft (para mensagens de canal), um grupo do Office 365 e um Grupo do Yammer. Para saber mais sobre os dados do aplicativo armazenados em caixas de correio, consulte [Conteúdo armazenado nas caixas de correio para Descoberta eletrônica](what-is-stored-in-exo-mailbox.md).

   2. **Sites do SharePoint**: configure o botão de alternância como **Ativado** e, em seguida, clique em **Escolher sites** para especificar sites do SharePoint e contas do OneDrive para colocar em espera. Digite a URL de cada site que você deseja colocar em espera. Você também pode adicionar a URL do site do SharePoint para uma Equipe da Microsoft, grupo do Office 365 ou grupo do Yammer.
  
   3. **Pastas públicas do Exchange**: configure o botão de alternância como **Ativado** para colocar todas as pastas públicas em sua organização do Exchange Online em espera. Você não pode escolher pastas públicas específicas para colocar em espera. Deixe o botão de alternância desligado se você não quiser colocar pastas públicas em espera.
  
   4. Mantenha esta caixa de seleção marcada para procurar conteúdo do Teams para usuários locais. Por exemplo, se você pesquisar todas as caixas de correio do Exchange na organização e também selecionar esta caixa de seleção, o armazenamento baseado em nuvem usado para armazenar os dados de bate-papo do Teams para usuários locais será incluído no escopo da pesquisa. Para obter mais informações, confira [Pesquisar dados de bate-papo do Teams para usuários locais](search-cloud-based-mailboxes-for-on-premises-users.md).

6. Na página **Definir as condições da pesquisa**, digite uma consulta de palavra-chave e adicione condições à consulta de pesquisa, se necessário.

   ![Configurar a consulta de pesquisa](../media/ContentSearchQuery.png)

   1. Você pode especificar palavras-chave, propriedades de mensagem como datas enviadas e recebidas, ou ainda, propriedades do documento como nomes de arquivos ou a data em que um documento foi alterado pela última vez. Faça consultas mais complexas que usam um operador Booleano, como **E**, **OU**, **NÃO** e **PRÓXIMO**. Se você deixar a caixa de palavra-chave vazia, todo o conteúdo localizado nos locais de conteúdo especificado será incluído nos resultados da pesquisa. Para saber mais, veja [Consultas de palavra-chave e condições de pesquisa para Descoberta eletrônica](keyword-queries-and-search-conditions.md).

   2. Como alternativa, você pode clicar na caixa de seleção **Mostrar lista de palavras-chave** e digitar uma palavra-chave em cada linha. Ao fazer isso, as palavras-chave em cada linha serão conectadas por um operador lógico (**c:s**) com funcionalidade semelhante ao operador **OU** na consulta de pesquisa criada.

      Por que usar a lista de palavras-chave? Para obter estatísticas que mostram quantos itens correspondem a cada palavra-chave. Isso ajudará a identificar rapidamente quais palavras-chave são as mais recentes. Também poderá usar uma frase de palavra-chave (entre parênteses) em uma linha. Para saber mais sobre a lista de palavras-chave e as estatísticas de pesquisa, confira [Obter estatísticas de palavra-chave para pesquisas](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches).

      > [!NOTE]
      > Para ajudar a reduzir problemas causados por listas de palavras-chave muito extensas, agora você está limitado a um máximo de 20 linhas na lista de palavras-chave.

   3. Você pode adicionar condições a uma consulta de pesquisa para restringir a pesquisa e produzir um conjunto de resultados mais refinado. Cada condição adiciona uma cláusula à consulta de pesquisa que é criada e executada quando você inicia a pesquisa. Uma condição é logicamente conectada à consulta de palavra-chave (especificada na caixa de palavra-chave) por um operador lógico (**c:c**) parecido com a funcionalidade do operador **E**. Isso significa que os itens precisam atender à consulta de palavras-chave e uma ou mais condições para serem incluídas nos resultados. É assim que as condições ajudam a restringir os resultados. Para obter uma lista e uma descrição das condições que podem ser usadas em uma consulta de pesquisa, confira a seção [Condições de pesquisa](keyword-queries-and-search-conditions.md#search-conditions).

7. Revise as configurações de pesquisa (e edite, se necessário) e envie a pesquisa para iniciá-la.
  
Para acessar a pesquisa de conteúdo novamente ou acessar outras pesquisas de conteúdo listadas na página **Pesquisa de conteúdo**, selecione a pesquisa e clique em **Abrir**.
  
## <a name="next-steps"></a>Próximas etapas

Aqui está uma lista das próximas etapas a serem seguidas por você criar e executar uma Pesquisa de conteúdo.

- [Visualização de resultados de pesquisa](preview-ediscovery-search-results.md)

- [Exibir as estatísticas para resultados da pesquisa](view-keyword-statistics-for-content-search.md)

- [Exportar resultados de pesquisa](export-search-results.md)

- [Exportar um relatório de pesquisa](export-a-content-search-report.md)
