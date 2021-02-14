---
title: Preparar um arquivo CSV para uma lista de IDs de Pesquisa de Conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
description: Use arquivos CSV de uma Pesquisa de Conteúdo existente para criar uma pesquisa de lista de IDs que retorna mensagens de email específicas.
ms.openlocfilehash: 7b63a78d34306cf3afcef49276e584bc816c107f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817970"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a>Preparar um arquivo CSV para uma lista de IDs de Pesquisa de Conteúdo

Você pode pesquisar mensagens de email de caixa de correio específicas e outros itens de caixa de correio usando uma lista de IDs do Exchange. Para criar uma pesquisa de lista de IDs (chamada formalmente de pesquisa direcionada), envie um arquivo de valores separados por vírgula (CSV) que identifique os itens de caixa de correio específicos a ser pesquisado. Para esse arquivo CSV, você usa o arquivo **Results.csv** ou o arquivo **Items.csv** não Items.csvque são incluídos quando você exporta os resultados da Pesquisa de Conteúdo ou exporta um relatório de Pesquisa de Conteúdo da Pesquisa de Conteúdo e da Pesquisa de Conteúdo existente. Em seguida, edite um desses arquivos para indicar os itens específicos a ser pesquisado e, em seguida, crie uma nova pesquisa de lista de IDs e envie o arquivo CSV.

Aqui está uma rápida visão geral do processo de criação de uma pesquisa de lista de IDs.

1. Crie e execute uma Pesquisa de Conteúdo nova ou guiada no Centro de Conformidade & Segurança.

2. Exporte os resultados da pesquisa de conteúdo ou exporte o relatório de pesquisa de conteúdo. Para saber mais, confira:

    - [Exportar resultados de Pesquisa de Conteúdo](export-search-results.md)

    - [Exportar um relatório da Pesquisa de Conteúdo](export-a-content-search-report.md)

3. Edite **oResults.csv** ou  o arquivo Items.csve identifique os itens de caixa de correio específicos que você deseja incluir na pesquisa de lista de IDs. Consulte as [instruções](#prepare-the-csv-file-for-an-id-list-search) para preparar um arquivo CSV para uma pesquisa de lista de IDs.

4. Crie uma nova pesquisa de lista de IDs (veja as [instruções)](#create-an-id-list-search)e envie o arquivo CSV que você preparou. A consulta de pesquisa criada pesquisa apenas os itens selecionados no arquivo CSV.

> [!NOTE]
> As pesquisas de lista de IDs só têm suporte para itens de caixa de correio. Você não pode pesquisar documentos do SharePoint e do OneDrive em uma pesquisa de lista de IDs.

 **Por que criar uma pesquisa de lista de IDs?** Se você não puder determinar se um item está respondendo a uma solicitação de Descoberta eDiscovery com base nos metadados nos arquivos **Results.csv** ou **não** Items.csv, você pode usar uma pesquisa de lista de IDs para encontrar, visualizar e exportar esse item para determinar se ele responde ao caso que você está investigando. As pesquisas de lista de IDs são normalmente usadas para pesquisar e retornar um conjunto específico de itens não índicedos.

## <a name="prepare-the-csv-file-for-an-id-list-search"></a>Preparar o arquivo CSV para uma pesquisa de lista de IDs

Depois de exportar os resultados da pesquisa ou o relatório para uma pesquisa de conteúdo, você pode executar as seguintes etapas para preparar o arquivo CSV para uma pesquisa de lista de IDs. Esse arquivo CSV identificará cada item na pesquisa da lista de IDs.

Observe que você pode usar um arquivo CSV de uma pesquisa que incluiu  sites do SharePoint e contas do OneDrive, mas pode selecionar apenas itens de caixa de correio para uma pesquisa de lista de IDs. Se você selecionar um documento no SharePoint ou no OneDrive, o arquivo CSV falhará na validação ao criar uma pesquisa de lista de IDs.

1. Abra o **Results.csv** arquivo de Items.csv **não Items.csv** no Excel.

2. Na coluna **Selecionado,** digite **Sim** na célula que corresponde ao item que você deseja pesquisar. Repita essa etapa para cada item que você deseja pesquisar.

    > [!IMPORTANT]
    > Quando você abre o arquivo CSV no Excel, o formato de dados para a coluna **ID do** Documento é alterado para **Geral.** Isso resulta na exibição da ID do documento de um item em notação científica. Por exemplo, a ID do documento "481037338205" é exibida como "4.81037E+11". Você precisa executar as  próximas etapas para alterar o formato de dados da coluna **ID** do Documento para Número para restaurar o formato correto para a ID do documento. Se você não fizer isso, a pesquisa da lista de IDs que usa o arquivo CSV falhará.

3. Clique com o botão direito do mouse na coluna **ID do** Documento inteira e selecione **Formatar Células.**

4. Na caixa **Categoria,** clique em **Número.**

5. Altere o número de casas decimais para **0** e clique em **OK** para salvar suas alterações. Observe que os valores na coluna ID do Documento são alterados para números.

    Veja um exemplo de um arquivo CSV que está pronto para ser enviado para uma pesquisa de conteúdo de lista de IDs.

    ![Exemplo de um arquivo CSV para uma pesquisa de conteúdo direcionada](../media/8371b8cb-1638-496e-9be1-fe1565757d67.png)

6. Salve o arquivo CSV ou use **Salvar como** para salvar o arquivo com um nome de arquivo diferente. Em ambos os casos, certifique-se de salvar o arquivo com o formato CSV.

## <a name="create-an-id-list-search"></a>Criar uma pesquisa de lista de IDs

A próxima etapa é criar uma nova Lista de IDs de Pesquisa de Conteúdo e enviar o arquivo CSV que você preparou na etapa anterior.

> [!IMPORTANT]
> Você deve criar uma pesquisa de lista de IDs no mais de 2 dias após exportar os resultados ou relatório de uma Pesquisa de Conteúdo. Se os resultados da pesquisa ou relatório onde foi exportado há mais de 2 dias, exporte os resultados da pesquisa ou relatório para gerar arquivos CSV atualizados. Em seguida, você pode preparar um dos arquivos CSV atualizados e usá-lo para criar uma pesquisa de lista de IDs.

1. No Centro de Conformidade & segurança, vá **para** Pesquisa \> **de Conteúdo de Pesquisa.**

2. Na página **Pesquisar,** clique na seta ao lado do ícone Adicionar Nova pesquisa e clique em ![ Pesquisar por Lista de ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif)  **IDs.**

    ![Click Search by ID List from the New search dropdown list](../media/e65f9942-09b2-4127-865e-e64029a590df.png)

3. No flyout Pesquisar por **Lista de IDs,** nomee a  pesquisa (e, opcionalmente, descreva-a) e clique em Procurar e selecione o arquivo CSV preparado na etapa anterior.

    O Microsoft 365 tenta validar o arquivo CSV. Se a validação não for bem-sucedida, será exibida uma mensagem de erro que pode ajudá-lo a solucionar os erros de validação. O arquivo CSV deve ser validado com êxito para criar uma pesquisa de lista de IDs.

4. Depois que o arquivo CSV for validado com êxito, clique em **Pesquisar** para criar a pesquisa da lista de IDs.

    Veja um exemplo dos resultados estimados da pesquisa e da consulta gerada para uma pesquisa de lista de IDs.

    ![Consulta de pesquisa para uma pesquisa de conteúdo direcionado no painel de detalhes](../media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)

    Observe que o número de itens estimados exibidos nas estatísticas da pesquisa de ID deve corresponder ao número de itens selecionados no arquivo CSV.

5. Visualize ou exporte os itens retornados pela pesquisa de lista de IDs.

> [!NOTE]
> Se você mover uma caixa de correio após criar uma pesquisa de lista de IDs, a consulta para a pesquisa não retornará os itens especificados. Isso acontece porque a propriedade **DocumentId** dos itens da caixa de correio é alterada quando uma caixa de correio é movida. Na rara instância em que uma caixa de correio é movida depois de criar uma pesquisa de lista de IDs, você deve criar uma nova pesquisa de conteúdo (ou atualizar os resultados da pesquisa para a pesquisa de conteúdo existente) e exportar os resultados da pesquisa ou relatório para gerar arquivos CSV atualizados que podem ser usados para criar uma nova pesquisa de lista de IDs.
