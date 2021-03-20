---
title: Pesquisas de conteúdo de edição em massa
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
search.appverid:
- MOE150
- MET150
ms.assetid: 39e4654a-9588-41f6-892b-c33ab57bfbe2
ms.custom:
- seo-marvel-apr2020
description: Use o Editor de Pesquisa em Massa no centro de segurança e conformidade para alterar rapidamente os locais de consulta e conteúdo para uma ou mais Pesquisas de Conteúdo.
ms.openlocfilehash: 9f4d84a2f9c99f544bbb402fc24ac2dcbf0864f8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918227"
---
# <a name="bulk-edit-content-searches"></a>Pesquisas de conteúdo de edição em massa

Você pode usar o Editor de Pesquisa em Massa na ferramenta Pesquisa de Conteúdo para editar várias pesquisas ao mesmo tempo. Usar essa ferramenta permite alterar rapidamente os locais de consulta e conteúdo para uma ou mais pesquisas. Em seguida, você pode reprisar as pesquisas e obter novos resultados de pesquisa estimados para as pesquisas revisadas. O editor também permite copiar e colar consultas e locais de conteúdo de um arquivo ou arquivo de texto do Microsoft Excel. Isso significa que você pode usar a ferramenta Estatísticas de Pesquisa para exibir as estatísticas de uma ou mais pesquisas, exportar as estatísticas para um arquivo CSV, onde você pode editar as consultas e locais de conteúdo no Excel. Em seguida, use o Editor de Pesquisa em Massa para adicionar as consultas revisadas e os locais de conteúdo às pesquisas. Depois de revisar uma ou mais pesquisas, você pode reiniciá-las e obter novos resultados estimados de pesquisa.
  
Para obter mais informações sobre como usar a ferramenta Estatísticas de Pesquisa, consulte Exibir estatísticas [de palavra-chave para resultados da Pesquisa de Conteúdo](view-keyword-statistics-for-content-search.md).
  
## <a name="use-the-bulk-search-editor-to-change-queries"></a>Usar o Editor de Pesquisa em Massa para alterar consultas

1. Vá para [https://protection.office.com](https://protection.office.com) e, em seguida, selecione **Pesquisar** \> **Conteúdo de pesquisa**.
    
2. Na lista de pesquisas, selecione uma ou mais pesquisas e selecione Editor de Pesquisa em Massa **Editor** de Pesquisa em ![ ](../media/1ddb3d18-2f00-4a7b-98a6-817ca5ec7014.png) Massa.
    
    ![Selecione uma ou mais pesquisas e selecione Editor de pesquisa em massa](../media/600c9716-89a2-4451-b111-fa7cfaad2006.png)
  
    As informações a seguir são exibidas na página **Consultas** do Editor de Pesquisa em Massa. 
    
    ![A página editor de pesquisa em massa exibe as consultas das pesquisas selecionadas](../media/189659af-cc78-4479-b0bc-a93decad2f6c.png)
  
    a. A **coluna** Pesquisa exibe o nome da Pesquisa de Conteúdo. Como mencionado anteriormente, você pode editar a consulta para várias pesquisas. 
    
    b. A **coluna Consulta** exibe a consulta para a Pesquisa de Conteúdo listada na coluna **Pesquisa.** Se a consulta foi criada usando o recurso de lista de palavras-chave, as palavras-chave serão separadas pelo texto ** `(c:s)` **. Isso indica que as palavras-chave estão conectadas pelo **operador OR.** Além disso, se `(c:c)` a consulta incluir condições, as palavras-chave** e as condições serão separadas pelo texto ** . Isso indica que as palavras-chave (ou fases de palavra-chave) estão conectadas às condições do **operador AND.** Por exemplo, na captura de tela anterior da pesquisa ContosoSearch1, a consulta KQL equivalente a  `customer (c:s) pricing(c:c)(date=2000-01-01..2016-09-30)`  `(customer OR pricing) AND (date=2002-01-01..2016-09-30)` seria .
    
3. Para editar uma consulta, selecione na célula da consulta que você deseja alterar e fazer uma das seguintes coisas. A célula é bordada por uma caixa azul quando você a seleciona.
    
   - Digite a nova consulta na célula. Não é possível editar uma parte da consulta. Você precisa digitar a consulta inteira.
    
      Ou
    
    - Colar uma nova consulta na célula. Isso supõe que você copiou o texto de consulta de um arquivo, como um arquivo de texto ou um arquivo do Excel.
    
4. Depois de editar uma ou mais consultas na página **Consultas,** selecione **Salvar**.
    
    A consulta revisada é exibida na coluna **Consulta** da pesquisa selecionada. 
    
5. Selecione **Fechar** para fechar o Editor de Pesquisa em Massa. 
    
6. Na página **Pesquisa de** conteúdo, selecione a pesquisa editada e selecione **Iniciar** pesquisa para reiniciar a pesquisa usando a consulta revisada. 
    
Aqui estão algumas dicas para editar consultas usando o Editor de Pesquisa em Massa:
  
- Copie a consulta existente (usando **Ctrl C** ) para um arquivo de texto. Edite a consulta no arquivo de texto e copie a consulta revisada e a colar (usando **Ctrl V** ) de volta para a célula na página **Consultas.** 
    
- Você também pode copiar consultas de outros aplicativos (como o Microsoft Word ou o Microsoft Excel). No entanto, você pode adicionar inadvertidamente caracteres sem suporte a uma consulta usando o Editor de Pesquisa em Massa. A melhor maneira de evitar caracteres sem suporte é apenas digitar a consulta em uma célula na página **Consultas.** Ou você pode copiar uma consulta do Word ou excel e, em seguida, colar em um arquivo em um editor de texto simples, como o Bloco de Notas da Microsoft. Em seguida, salve o arquivo de  texto e selecione **ANSI** na lista drop-down de Codificação. Isso remove qualquer formatação e caracteres sem suporte. Em seguida, você pode copiar e colar a consulta do arquivo de texto para **a página Consultas.** 
    
  
## <a name="use-the-bulk-search-editor-to-change-content-locations"></a>Usar o Editor de Pesquisa em Massa para alterar locais de conteúdo

1. No Editor de Pesquisa em Massa para uma ou mais pesquisas selecionadas, selecione Habilitar editor de localização em massa **e** selecione o link **Locais** exibido na página. 
    
    As informações a seguir são exibidas na página **Locais** do Editor de Pesquisa em Massa. 
    
    ![Selecione Habilitar editor de localização em massa e selecione Locais para adicionar ou remover locais de conteúdo](../media/a5a468ce-bd63-4c53-bc37-ff64cf769e59.png)
  
    a. **Caixas de correio para pesquisa** Esta seção exibe uma coluna para cada Pesquisa de Conteúdo selecionada e uma linha para cada caixa de correio incluída na pesquisa. Uma marca de seleção indica que a caixa de correio está incluída na pesquisa. Você pode adicionar caixas de correio a uma pesquisa digitando o endereço de email da caixa de correio em uma linha em branco e selecionando a caixa de seleção para a Pesquisa de Conteúdo à que você deseja adicioná-la. Ou você pode remover uma caixa de correio de uma pesquisa limpando a caixa de seleção.
    
    b. **Sites do SharePoint para pesquisa** Esta seção exibe uma linha para cada site do SharePoint e do OneDrive incluído em cada Pesquisa de Conteúdo selecionada. Uma marca de verificação indica que o site está incluído na pesquisa. Você pode adicionar sites a uma pesquisa digitando a URL do site em uma linha em branco e selecionando a caixa de seleção para a Pesquisa de Conteúdo à que você deseja adicioná-la. Ou você pode remover um site de uma pesquisa limpando a caixa de seleção.
    
    c. **Outras opções de pesquisa** Esta seção indica se itens não indexados e pastas públicas estão incluídos na pesquisa. Para incluí-los, verifique se a caixa de seleção está selecionada. Para removê-los, desempure a caixa de seleção.
    
2. Depois de editar uma ou mais seções na página **Locais,** selecione **Salvar**.
    
    Os locais de conteúdo revisados são exibidos na seção apropriada para as pesquisas selecionadas.
    
3. Selecione **Fechar** para fechar o Editor de Pesquisa em Massa. 
    
4. Na página **Pesquisa de** conteúdo, selecione a pesquisa editada e selecione **Iniciar** pesquisa para reiniciar a pesquisa usando os locais de conteúdo revisados. 
    
Aqui estão algumas dicas para editar locais de conteúdo usando o Editor de Pesquisa em Massa:
  
- Você pode editar Pesquisas de Conteúdo para pesquisar todas as caixas de correio  ou sites na organização digitando **Tudo** em branco nas Caixas de Correio para pesquisar ou sites do **SharePoint** na seção de pesquisa e, em seguida, selecionando a caixa de seleção. 
    
- Você pode adicionar vários locais de conteúdo a uma ou mais pesquisas copiando várias linhas de um arquivo de texto ou de um arquivo do Excel e, em seguida, colar em uma seção na página **Locais.** Depois de adicionar novos locais, marque a caixa de seleção para cada pesquisa à que deseja adicionar o local. 
    
    > [!TIP]
    > Para gerar uma lista de endereços de email para todos os usuários em sua organização, execute o comando do PowerShell na Etapa 2 na Etapa [2: Gerar](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md#step-2-generate-a-list-of-users)uma lista de usuários . Ou siga as etapas em Obter uma lista de todas as [URLs](/onedrive/list-onedrive-urls) do OneDrive de usuário em sua organização para gerar uma lista de todos os sites do OneDrive for Business em sua organização. Observe que você terá que anexar a URL para o domínio MySite da sua organização (por exemplo, para os sites do OneDrive for Business criados https://contoso-my.sharepoint.com) pelo script. Depois de ter uma lista de endereços de email ou sites do OneDrive for Business, você pode copiá-los e colar na página **Locais** no Editor de Pesquisa em Massa. 
  
- Depois de selecionar **Salvar para** salvar alterações no Editor de Pesquisa em Massa, o endereço de email das caixas de correio que você adicionou a uma pesquisa será validado. Se o endereço de email não existir, uma mensagem de erro será exibida dizendo que a caixa de correio não pode ser localizada. URLs para sites não são validadas. 
