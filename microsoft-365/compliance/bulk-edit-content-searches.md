---
title: Edição em massa de pesquisas de conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/29/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 39e4654a-9588-41f6-892b-c33ab57bfbe2
description: Use o editor de pesquisa em massa no centro de segurança e conformidade no Office 365 ou no Microsoft 365 para alterar rapidamente os locais de consulta e conteúdo para uma ou mais pesquisas de conteúdo.
ms.openlocfilehash: 40d3a6c04a57f368a4f53ae0bbc543b049b26d52
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596268"
---
# <a name="bulk-edit-content-searches"></a>Edição em massa de pesquisas de conteúdo

Você pode usar o editor de pesquisa em massa na ferramenta de pesquisa de conteúdo para editar várias pesquisas ao mesmo tempo. O uso dessa ferramenta permite que você altere rapidamente os locais de consulta e conteúdo para uma ou mais pesquisas. Em seguida, você pode executar novamente as pesquisas e obter os novos resultados de pesquisa estimados para as pesquisas revisadas. O editor também permite copiar e colar as consultas e os locais de conteúdo de um arquivo do Microsoft Excel ou arquivo de texto. Isso significa que você pode usar a ferramenta de estatísticas de pesquisa para exibir as estatísticas de uma ou mais pesquisas, exportar as estatísticas para um arquivo CSV, onde é possível editar as consultas e os locais de conteúdo no Excel. Em seguida, use o editor de pesquisa em massa para adicionar as consultas revisadas e os locais de conteúdo às pesquisas. Após revisar uma ou mais pesquisas, você pode reiniciá-las e obter novos resultados de pesquisa estimados.
  
Para obter mais informações sobre como usar a ferramenta de estatísticas de pesquisa, consulte [exibir estatísticas de palavra-chave para resultados de pesquisa de conteúdo](view-keyword-statistics-for-content-search.md).
  
## <a name="use-the-bulk-search-editor-to-change-queries"></a>Usar o editor de pesquisa em massa para alterar consultas

1. Vá para [https://protection.office.com](https://protection.office.com)e selecione pesquisa de **** \> **conteúdo**de pesquisa.
    
2. Na lista de pesquisas, selecione uma ou mais pesquisas e, em seguida, selecione o botão ![](media/1ddb3d18-2f00-4a7b-98a6-817ca5ec7014.png)editor de pesquisa em massa do **Editor de pesquisa em massa** .
    
    ![Selecionar uma ou mais pesquisas e selecionar editor de pesquisa em massa](media/600c9716-89a2-4451-b111-fa7cfaad2006.png)
  
    As informações a seguir são exibidas na página **consultas** do editor de pesquisa em massa. 
    
    ![A página do editor de pesquisa em massa exibe as consultas para as pesquisas selecionadas](media/189659af-cc78-4479-b0bc-a93decad2f6c.png)
  
    a. A coluna de **pesquisa** exibe o nome da pesquisa de conteúdo. Conforme mencionado anteriormente, você pode editar a consulta para várias pesquisas. 
    
    b. A coluna **consulta** exibe a consulta para a pesquisa de conteúdo listada na coluna **pesquisa** . Se a consulta foi criada usando o recurso de lista de palavras-chave, as palavras-chave são separadas pelo `(c:s)`texto * * **. Isso indica que as palavras-chave estão conectadas pelo operador **or** . Além disso, se a consulta incluir condições, as palavras-chave e as condições serão separadas pelo texto * * `(c:c)` **. Isso indica que as palavras-chave (ou fases da palavra-chave) estão conectadas às condições pelo operador **and** . Por exemplo, na captura de tela anterior da ContosoSearch1 de pesquisa, a consulta KQL que é equivalente `customer (c:s) pricing(c:c)(date=2000-01-01..2016-09-30)` a seria `(customer OR pricing) AND (date=2002-01-01..2016-09-30)`.
    
3. Para editar uma consulta, selecione na célula da consulta que você deseja alterar e siga um destes procedimentos. A célula é borda por uma caixa azul quando você a seleciona.
    
   - Digite a nova consulta na célula. Não é possível editar uma parte da consulta. Você precisa digitar a consulta inteira.
    
      Ou
    
    - Colar uma nova consulta na célula. Isso pressupõe que você tenha copiado o texto da consulta de um arquivo, como um arquivo de texto ou um arquivo do Excel.
    
4. Após editar uma ou mais consultas na página **consultas** , selecione **salvar**.
    
    A consulta revisada é exibida na coluna de **consulta** para a pesquisa selecionada. 
    
5. Selecione **fechar** para fechar o editor de pesquisa em massa. 
    
6. Na página **pesquisa de conteúdo** , selecione a pesquisa que você editou e selecione **Iniciar** pesquisa para reiniciar a pesquisa usando a consulta revisada. 
    
Veja algumas dicas para editar consultas usando o editor de pesquisa em massa:
  
- Copie a consulta existente (usando **Ctrl C** ) para um arquivo de texto. Edite a consulta no arquivo de texto e, em seguida, copie a consulta revisada e Cole (usando **Ctrl V** ) novamente na célula da página **consultas** . 
    
- Você também pode copiar consultas de outros aplicativos (como o Microsoft Word ou o Microsoft Excel). No entanto, você pode adicionar inadvertidamente caracteres não suportados a uma consulta usando o editor de pesquisa em massa. A melhor maneira de evitar que os caracteres não suportados seja apenas digitar a consulta em uma célula na página **consultas** . Ou você pode copiar uma consulta do Word ou Excel e colá-la no arquivo em um editor de texto sem formatação, como o bloco de notas da Microsoft. Em seguida, salve o arquivo de texto e selecione **ANSI** na lista suspensa **codificação** . Isso remove qualquer formatação e caracteres sem suporte. Em seguida, você pode copiar e colar a consulta do arquivo de texto para a página **consultas** . 
    
  
## <a name="use-the-bulk-search-editor-to-change-content-locations"></a>Usar o editor de pesquisa em massa para alterar locais de conteúdo

1. No editor de pesquisa em massa para uma ou mais pesquisas selecionadas, selecione **habilitar editor de local em massa**e, em seguida, selecione o link **locais** que é exibido na página. 
    
    As informações a seguir são exibidas na página **locais** do editor de pesquisa em massa. 
    
    ![Selecione habilitar editor de local em massa e, em seguida, selecione locais para adicionar ou remover locais de conteúdo](media/a5a468ce-bd63-4c53-bc37-ff64cf769e59.png)
  
    a. **Caixas de correio para pesquisa** Esta seção exibe uma coluna para cada pesquisa de conteúdo selecionada e uma linha para cada caixa de correio incluída na pesquisa. Uma marca de seleção indica que a caixa de correio está incluída na pesquisa. Você pode adicionar caixas de correio a uma pesquisa digitando o endereço de email da caixa de correio em uma linha em branco e, em seguida, marcando a caixa de seleção para a pesquisa de conteúdo à qual deseja adicioná-lo. Ou você pode remover uma caixa de correio de uma pesquisa desmarcando a caixa de seleção.
    
    b. **Sites do SharePoint para pesquisa** Esta seção exibe uma linha para cada site do SharePoint e do OneDrive que está incluído em cada pesquisa de conteúdo selecionada. Uma marca de seleção indica que o site está incluído na pesquisa. Você pode adicionar sites a uma pesquisa digitando a URL do site em uma linha em branco e, em seguida, marcando a caixa de seleção para a pesquisa de conteúdo à qual deseja adicioná-lo. Ou você pode remover um site de uma pesquisa desmarcando a caixa de seleção.
    
    c. **Outras opções de pesquisa** Esta seção indica se itens não indexados e pastas públicas estão incluídos na pesquisa. Para incluí-los, certifique-se de que a caixa de seleção está marcada. Para removê-los, desmarque a caixa de seleção.
    
2. Após editar uma ou mais seções na página **locais** , selecione **salvar**.
    
    Os locais de conteúdo revisados são exibidos na seção apropriada para as pesquisas selecionadas.
    
3. Selecione **fechar** para fechar o editor de pesquisa em massa. 
    
4. Na página **pesquisa de conteúdo** , selecione a pesquisa que você editou e selecione **Iniciar** pesquisa para reiniciar a pesquisa usando os locais de conteúdo revisado. 
    
Veja algumas dicas para editar locais de conteúdo usando o editor de pesquisa em massa:
  
- Você pode editar pesquisas de conteúdo para pesquisar todas as caixas de correio ou sites na organização digitando **todos** em uma linha em branco na seção **caixas de correio para pesquisar** ou **sites do SharePoint para pesquisar** e, em seguida, marcando a caixa de seleção. 
    
- Você pode adicionar vários locais de conteúdo a uma ou mais pesquisas copiando várias linhas de um arquivo de texto ou de um arquivo do Excel e, em seguida, colando-as em uma seção na página **locais** . Após adicionar novos locais, certifique-se de marcar a caixa de seleção para cada pesquisa à qual deseja adicionar o local. 
    
    > [!TIP]
    > Para gerar uma lista de endereços de email para todos os usuários em sua organização, execute o comando PowerShell na etapa 2 na [etapa 2: gerar uma lista de usuários](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md#step-2-generate-a-list-of-users). Ou siga as etapas em [obter uma lista de todas as URLs do onedrive de usuários em sua organização](https://docs.microsoft.com/onedrive/list-onedrive-urls) para gerar uma lista de todos os sites do onedrive for Business em sua organização. Observe que você terá que acrescentar a URL para o domínio meusite da sua organização (por exemplo, https://contoso-my.sharepoint.com) para os sites do onedrive for Business criados pelo script. Depois de ter uma lista de endereços de email ou sites do OneDrive for Business, você pode copiá-los e colá-los na página **locais** no editor de pesquisa em massa. 
  
- Depois de selecionar **salvar** para salvar as alterações no editor de pesquisa em massa, o endereço de email para caixas de correio adicionadas a uma pesquisa será validado. Se o endereço de email não existir, será exibida uma mensagem de erro dizendo que a caixa de correio não pode ser localizada. As URLs para sites não são validadas. 
  

