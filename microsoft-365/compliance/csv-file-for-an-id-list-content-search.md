---
title: Preparar um arquivo CSV para uma pesquisa de conteúdo de lista de ID no Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
description: Use o arquivo Results. csv ou itens não indexados. csv de uma pesquisa de conteúdo existente para criar uma pesquisa de lista de ID que retorna mensagens de email específicas. Pesquisas de lista de ID normalmente são usadas para retornar itens de caixa de correio parcialmente indexados.
ms.openlocfilehash: caeb1874b113c601135531a1913bdcdda424a3d8
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806534"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search-in-office-365"></a>Preparar um arquivo CSV para uma pesquisa de conteúdo de lista de ID no Office 365

Você pode pesquisar mensagens de email de caixa de correio específicas e outros itens de caixa de correio usando uma lista de IDs do Exchange. Para criar uma pesquisa de lista de ID (formalmente chamada de pesquisa direcionada), você envia um arquivo CSV (valor separado por vírgula) que identifica os itens de caixa de correio específicos para pesquisa. Para este arquivo CSV, você usa o arquivo **Results. csv** ou o arquivo **Items. CSV não indexado** que são incluídos quando você exporta os resultados da pesquisa de conteúdo ou exporta um relatório de pesquisa de conteúdo de e a pesquisa de conteúdo existente. Em seguida, edite um desses arquivos para indicar os itens específicos que serão pesquisados e, em seguida, crie uma nova lista de ID pesquisa e envie o arquivo CSV.

Veja uma rápida visão geral do processo de criação de uma pesquisa de lista de ID.

1. Criar e executar uma pesquisa de conteúdo nova ou dirigida no centro de conformidade de & de segurança.

2. Exporte os resultados da pesquisa de conteúdo ou exporte o relatório de pesquisa de conteúdo. Para saber mais, confira:

    - [Exportar resultados de Pesquisa de Conteúdo](export-search-results.md)

    - [Exportar um relatório da Pesquisa de Conteúdo](export-a-content-search-report.md)

3. Edite o arquivo **Results. csv** ou os **itens não indexados. csv** e identifique os itens de caixa de correio específicos que você deseja incluir na pesquisa de lista de ID. Consulte as [instruções](#prepare-the-csv-file-for-an-id-list-search) para preparar um arquivo CSV para uma pesquisa de lista de ID.

4. Crie uma nova pesquisa de lista de ID (consulte as [instruções](#create-an-id-list-search)) e envie o arquivo CSV que você preparou. A consulta de pesquisa criada só pesquisará os itens selecionados no arquivo CSV.

> [!NOTE]
> Pesquisas de lista de ID têm suporte apenas para itens de caixa de correio. Você não pode pesquisar documentos do SharePoint e do OneDrive em uma pesquisa de lista de ID.

 **Por que criar uma pesquisa de lista de ID?** Se você não conseguir determinar se um item está respondendo a uma solicitação de descoberta eletrônica com base nos metadados nos arquivos **Results. csv** ou **Items. CSV não indexados** , você pode usar uma pesquisa de lista de ID para localizar, Visualizar e exportar esse item para determinar se ele está respondendo ao caso que você está investigando. Pesquisas de lista de ID normalmente são usadas para pesquisar e retornar um conjunto específico de itens não indexados.

## <a name="prepare-the-csv-file-for-an-id-list-search"></a>Preparar o arquivo CSV para uma pesquisa de lista de ID

Depois de exportar os resultados de pesquisa ou o relatório de uma pesquisa de conteúdo, você pode executar as seguintes etapas para preparar o arquivo CSV para uma pesquisa de lista de ID. Este arquivo CSV identificará todos os itens na pesquisa de lista de ID.

Observe que você pode usar um arquivo CSV de uma pesquisa que incluiu sites do SharePoint e contas do OneDrive, mas *só* pode selecionar itens de caixa de correio para uma pesquisa de lista de ID. Se você selecionar um documento no SharePoint ou no OneDrive, o arquivo CSV apresentará falha na validação quando você criar uma pesquisa de lista de ID.

1. Abra o arquivo **Results. csv** ou **itens não indexados. csv** no Excel.

2. Na coluna **selecionado** , digite **Sim** na célula que corresponde ao item que você deseja pesquisar. Repita essa etapa para cada item que você deseja pesquisar.

    > [!IMPORTANT]
    > Quando você abre o arquivo CSV no Excel, o formato de dados da coluna **ID do documento** é alterado para **geral**. Isso resulta na exibição da ID do documento para um item em notação científica. Por exemplo, a ID de documento de "481037338205" é exibida como "4.81037 E + 11" você tem que executar as próximas etapas para alterar o formato de dados da coluna **ID do documento** para **número** para restaurar o formato correto para a ID do documento. Se você não fizer isso, a pesquisa de lista de ID que usa o arquivo CSV falhará.

3. Clique com o botão direito do mouse na coluna **ID do documento** inteiro e selecione **Formatar células**.

4. Na caixa **categoria** , clique em **número**.

5. Altere o número de casas decimais para **0**e, em seguida, clique em **OK** para salvar suas alterações. Observe que os valores na coluna ID do documento são alterados para números.

    Veja um exemplo do arquivo CSV que está pronto para ser enviado para uma pesquisa de conteúdo de lista de ID.

    ![Exemplo de um arquivo CSV para uma pesquisa de conteúdo direcionada](media/8371b8cb-1638-496e-9be1-fe1565757d67.png)

6. Salve o arquivo CSV ou use **salvar como** para salvar o arquivo com outro nome de arquivo. Em ambos os casos, certifique-se de salvar o arquivo com o formato CSV.

## <a name="create-an-id-list-search"></a>Criar uma pesquisa de lista de ID

A próxima etapa é criar uma nova pesquisa de conteúdo de lista de ID e enviar o arquivo CSV que você preparou na etapa anterior.

> [!IMPORTANT]
> Você deve criar uma pesquisa de lista de ID que não tenha mais de dois dias após a exportação dos resultados ou do relatório de uma pesquisa de conteúdo. Se os resultados da pesquisa ou o relatório onde exportados há mais de 2 dias, você deve exportar novamente os resultados da pesquisa ou o relatório para gerar arquivos CSV atualizados. Em seguida, você pode preparar um dos arquivos CSV atualizados e usá-lo para criar uma pesquisa de lista de ID.

1. No centro de conformidade & segurança, vá para **** \> **pesquisa de conteúdo**de pesquisa.

2. Na página de **pesquisa** , clique na seta ao lado ![de adicionar](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) ícone **nova pesquisa**e, em seguida, clique em **Pesquisar por lista de ID**.

    ![Clique em Pesquisar pela lista de IDs na nova lista suspensa de pesquisa](media/e65f9942-09b2-4127-865e-e64029a590df.png)

3. No submenu de **lista Pesquisar por ID** , nomeie a pesquisa (e, opcionalmente, descreva-a) e clique em **procurar** e selecione o arquivo CSV que você preparou na etapa anterior.

    O Office 365 tenta validar o arquivo CSV. Se a validação não for bem sucedida, será exibida uma mensagem de erro que poderá ajudá-lo a solucionar os erros de validação. O arquivo CSV deve ser validado com êxito para criar uma pesquisa de lista de ID.

4. Depois que o arquivo CSV for validado com êxito, clique em **Pesquisar** para criar a pesquisa de lista de ID.

    Veja um exemplo dos resultados estimados da pesquisa e a consulta que é gerada para uma pesquisa de lista de ID.

    ![Consulta de pesquisa para uma pesquisa de conteúdo direcionada no painel de detalhes](media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)

    Observe que o número de itens estimados exibidos em estatísticas para a pesquisa de ID deve corresponder ao número de itens que você selecionou no arquivo CSV.

5. Visualize ou exporte os itens retornados pela pesquisa da lista de ID.

> [!NOTE]
> Se você mover uma caixa de correio depois de criar uma pesquisa de lista de ID, a consulta para a pesquisa não retornará os itens especificados. Isso ocorre porque a propriedade **DocumentID** para itens da caixa de correio é alterada quando uma caixa de correio é movida. Na rara instância, quando uma caixa de correio é movida depois de criar uma pesquisa de lista de ID, você deve criar uma nova pesquisa de conteúdo (ou atualizar os resultados da pesquisa para a pesquisa de conteúdo existente) e exportar os resultados da pesquisa ou o relatório para gerar arquivos CSV atualizados que podem ser usados  para criar uma nova pesquisa de lista de ID.
