---
title: Preparar um arquivo CSV para uma pesquisa de conteúdo de lista de ID
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
description: Use um arquivo CSV de uma pesquisa de Conteúdo existente para criar uma pesquisa de lista de ID que retorna itens de email específicos.
ms.openlocfilehash: 37a398d0896fcfd7b7282bda1f6a549ed9f53601
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311527"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a>Preparar um arquivo CSV para uma pesquisa de conteúdo de lista de ID

Você pode pesquisar mensagens de email de caixa de correio específicas e outros itens de caixa de correio usando uma lista de Exchange IDs. Para criar uma pesquisa de lista de IDs, você envia um arquivo de valores separados por vírgula (CSV) que identifica os itens específicos da caixa de correio a serem pesquisados. Para esse arquivo CSV, você usa o arquivo **Results.csv** ou o arquivo Items.csvnão **Items.csv** que são incluídos ao exportar os resultados da pesquisa de conteúdo ou exportar um relatório de pesquisa de conteúdo de uma pesquisa de Conteúdo existente. Em seguida, edite um desses arquivos para indicar os itens específicos a ser pesquisado, crie uma nova pesquisa de lista de ID e envie o arquivo CSV.

**Por que criar uma pesquisa de lista de ID?** Se você não conseguir determinar se um item está respondendo a uma solicitação de Descoberta E com base nos metadados nos arquivos Items.csvou **não** Results.csv, você pode usar **uma** pesquisa de lista de ID para encontrar, visualizar e exportar esse item para determinar se ele responde ao caso que você está investigando. As pesquisas de lista de ID geralmente são usadas para pesquisar e retornar um conjunto específico de itens não índicedos.

Aqui está uma visão geral rápida do processo para criar uma pesquisa de lista de ID.

1. Crie e execute uma nova pesquisa no Microsoft 365 de conformidade.

2. Exporte os resultados da pesquisa de conteúdo ou o relatório de pesquisa de conteúdo. Para saber mais, veja:

    - [Exportar resultados de Pesquisa de conteúdo](export-search-results.md)

    - [Exportar um relatório de Pesquisa de conteúdo](export-a-content-search-report.md)

3. Edite **o arquivoResults.csv** ou **o** arquivo Items.csve identifique os itens de caixa de correio específicos para incluir na pesquisa de lista de ID. Consulte as [instruções](#prepare-the-csv-file-for-an-id-list-search) para preparar um arquivo CSV para uma pesquisa de lista de ID.

4. Crie uma nova pesquisa de lista de ID (consulte as [instruções](#create-an-id-list-search)) e envie o arquivo CSV que você preparou. A consulta de pesquisa criada procurará apenas os itens selecionados no arquivo CSV.

> [!NOTE]
> As pesquisas de lista de ID são suportadas apenas para itens de caixa de correio. Não é possível pesquisar SharePoint documentos OneDrive em uma pesquisa de lista de ID.

## <a name="prepare-the-csv-file-for-an-id-list-search"></a>Preparar o arquivo CSV para uma pesquisa de lista de ID

Depois de exportar os resultados da pesquisa ou o relatório de uma pesquisa, execute as etapas a seguir para preparar o arquivo CSV para uma pesquisa de lista de ID. Esse arquivo CSV identifica cada item na pesquisa de lista de ID.

Você pode usar um arquivo CSV de uma pesquisa que incluiu SharePoint sites e OneDrive contas, mas você só pode selecionar itens de caixa de correio para uma pesquisa de lista de ID. Se você selecionar um documento em SharePoint ou OneDrive, o arquivo CSV falhará na validação ao criar uma pesquisa de lista de ID.

1. Abra o **Results.csv** **ou o arquivo Items.csvnão Excel.**

2. Na coluna **Selecionado,** digite **Sim** na célula que corresponde ao item que você deseja pesquisar. Repita esta etapa para cada item que você deseja pesquisar.

    > [!IMPORTANT]
    > Quando você abre o arquivo CSV no Excel, o formato de dados da coluna **ID** do Documento pode ter sido alterado para **Geral**. Isso resulta na exibição da ID do documento de um item em notação científica. Por exemplo, a ID do documento de "481037338205" é exibida como "4.81037E+11". Se isso acontecer, você terá que executar as próximas etapas para alterar o formato de dados da coluna **ID** do Documento para **Número** para restaurar o formato correto para a ID do documento. Se você não fizer isso, a pesquisa de lista de ID que usa o arquivo CSV falhará.

3. Clique com o botão direito do mouse em toda a **coluna ID** do Documento e selecione **Formatar Células**.

4. Na caixa **Categoria,** clique em **Número**.

5. Altere o número de casas decimais **para 0** e clique em **OK** para salvar suas alterações. Observe que os valores na coluna ID do documento são alterados para números.

    Aqui está um exemplo de um arquivo CSV que está pronto para ser enviado para uma pesquisa de conteúdo de lista de ID.

    ![Exemplo de um arquivo CSV para uma pesquisa de conteúdo direcionada](../media/SearchIDListCSVFile.png)

6. Salve o arquivo CSV ou use **Salvar como** para salvar o arquivo com nome de arquivo diferente. Em ambos os casos, salve o arquivo com o formato CSV.

## <a name="create-an-id-list-search"></a>Criar uma pesquisa de lista de ID

A próxima etapa é criar uma nova pesquisa de lista de ID e enviar o arquivo CSV que você preparou na etapa anterior.

> [!IMPORTANT]
> Você deve criar uma pesquisa de lista de ID não mais do que 2 dias após exportar os resultados ou relatório da pesquisa. Se os resultados da pesquisa ou o relatório de onde foi exportado há mais de 2 dias, você deve exportar os resultados da pesquisa ou o relatório para gerar arquivos CSV atualizados. Em seguida, você pode preparar um dos arquivos CSV atualizados e usá-lo para criar uma pesquisa de lista de ID.

1. Acesse <https://compliance.microsoft.com> e entre.

2. No painel de navegação esquerdo do Centro de Conformidade do Microsoft 365, clique em **Mostrar tudo** e, a seguir, clique em **Pesquisa de conteúdo**.

3. Na página **Pesquisa de** conteúdo, clique em Pesquisar por Lista **de IDs.**

4. No flyout **Search by ID List,** nomeia a pesquisa (e, opcionalmente, a descreverá) e clique em Procurar e selecione o arquivo CSV que você preparou na etapa anterior. 

    Microsoft 365 tenta validar o arquivo CSV. Se a validação não tiver êxito, será exibida uma mensagem de erro que pode ajudá-lo a solucionar os erros de validação. O arquivo CSV precisa ser validado com êxito para criar uma pesquisa de lista de ID.

5. Depois que o arquivo CSV for validado com êxito, clique em **Pesquisar** para criar a pesquisa de lista de ID.

    Veja um exemplo da página de sobrevoo de uma pesquisa de lista de ID que mostra a consulta gerada e o número estimado de resultados da pesquisa.

    ![Consulta de pesquisa para pesquisa de lista de ID](../media/SearchIDListFlyout.png)

    O número de itens estimados exibidos em estatísticas para a pesquisa de ID deve corresponder ao número de itens selecionados no arquivo CSV.

6. Visualizar ou exportar os itens retornados pela pesquisa de lista de ID.

## <a name="more-information"></a>Mais informações

Se você mover uma caixa de correio após a criação de uma pesquisa de lista de ID, a consulta para a pesquisa não retornará os itens especificados. Isso acontece porque a propriedade **DocumentId para** itens de caixa de correio é alterada quando uma caixa de correio é movida. Na rara instância em que uma caixa de correio é movida após a criação de uma pesquisa de lista de ID, você deve criar uma nova pesquisa de Conteúdo (ou atualizar os resultados da pesquisa para uma pesquisa existente) e, em seguida, exportar os resultados da pesquisa ou relatório para gerar arquivos CSV atualizados que podem ser usados para criar uma nova pesquisa de lista de ID.
