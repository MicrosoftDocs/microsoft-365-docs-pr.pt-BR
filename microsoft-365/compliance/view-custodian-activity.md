---
title: Exibir a atividade de auditoria custodiada
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
ms.assetid: ''
description: Use a ferramenta gerenciamento custodiante da Descoberta Avançada para acessar e pesquisar facilmente a atividade de custodiantes em seu caso.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f9e96d0b5dd3bf42dbba56a6e1be91014485ce98
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024761"
---
# <a name="view-custodian-audit-activity"></a>Exibir a atividade de auditoria custodiada

Precisa descobrir se um usuário visualizou um documento específico ou apagou um item de sua caixa de correio? A Descoberta Avançada agora está integrada à ferramenta de pesquisa de log de auditoria existente no Centro de Conformidade & e Segurança. Usando essa experiência incorporada, você pode usar a ferramenta Gerenciamento Custodian de Descoberta Eletrônica Avançada para facilitar a investigação acessando e pesquisando facilmente a atividade de custodiantes dentro de seu caso.

## <a name="get-permissions"></a>Obter permissões

É preciso atribuir a função Logs de Auditoria Somente para Exibição ou Logs de Auditoria do Exchange Online para pesquisar o log de auditoria. Por padrão, essas funções são atribuídas aos grupos de funções Gerenciamento de Conformidade e Gerenciamento de Organização na página Permissões do centro de administração do Exchange. Para dar a um usuário a capacidade de pesquisar o log de auditoria de Descobertas Avançadas com o nível mínimo de privilégios, você pode criar um grupo de função personalizado no Exchange Online, adicionar a função logs de auditoria ou logs de auditoria do View-Only e, em seguida, adicionar o usuário como membro do novo grupo de função. Para saber mais, confira Gerenciar Grupos de Funções do Exchange Online.

> [!IMPORTANT]
> Se você atribuir a um usuário View-Only a função Logs de Auditoria ou & Logs de Auditoria na página Permissões do Centro de Conformidade e Segurança, ele não poderá pesquisar o log de auditoria. Você deve atribuir as permissões no Exchange Online. Isso ocorre porque o cmdlet subjacente usado para pesquisar o log de auditoria é um cmdlet Exchange Online.

## <a name="step-1-search-the-audit-log-for-activities-performed-by-a-custodian"></a>Etapa 1: Pesquisar o log de auditoria para atividades executadas por um custodiante

1. Vá para  **a Descoberta > eDiscovery Avançada** e abra a ocorrência.
  
2. Clique na **guia** Fontes.
  
3. Na página **Custodiantes,** selecione um custodiante na lista e clique em Exibir atividade **custodiante** na página do flyout.

    A página de pesquisa de atividades custodiadas é exibida. Observe que o custodiante que você selecionou na etapa anterior é exibido na caixa de **lista** drop-down custodiante. Você pode selecionar diferentes custodiantes na caixa de lista, mas só pode pesquisar atividades por um custodiante por vez.

    ![Página de pesquisa de atividades custodiadas](../media/AeDCustodianActivities1.png)
   
4. Configure os seguintes critérios de pesquisa: 
      
   1. **Atividades** - Clique na lista drop-down para exibir as atividades que você pode pesquisar. Depois de executar a pesquisa, somente os registros de auditoria para as atividades selecionadas serão exibidos. Selecionar **Mostrar resultados para todas as atividades** exibirá os resultados de todas as atividades executadas pelo custodiatário que corresponderem aos outros critérios de pesquisa.

      ![Lista de atividades](../media/CustodianActivityAudit.PNG)
      
   1. **Data de início e data de** término - Selecione um intervalo de data e hora para exibir os eventos que ocorreram dentro desse período. Os últimos sete dias são selecionados por padrão. A data e a hora são apresentadas no formato UTC (Tempo Universal Coordenado). O intervalo máximo de datas que você pode especificar é um ano.
      
   1. **Custodiantes** - Clique nesta caixa e selecione um responsável específico para exibir os resultados da pesquisa. Os registros de auditoria para a atividade selecionada realizada pelos usuários selecionados nesta caixa são exibidos na lista de resultados.
      
5. Clique em ![Botão Pesquisar](../media/SearchButton.PNG)  para executar a pesquisa usando seus critérios de pesquisa. Os resultados da pesquisa são carregados e, depois de alguns instantes, são exibidos em Resultados na página de pesquisa Atividades Custodianes. 

## <a name="step-2-view-the-audit-log-search-results"></a>Etapa 2: Exibir os resultados da pesquisa do log de auditoria

Os resultados de uma pesquisa de log de auditoria são exibidos em Resultados na página de log de Auditoria Custodiada. Um máximo de 5.000 eventos (mais recentes) são exibidos em incrementos de 150 eventos. Para exibir mais eventos, use a barra de rolagem no painel Resultados ou pressione Shift+End para exibir os próximos 150 eventos.

Os resultados contêm as seguintes informações sobre cada evento retornado pela pesquisa.
- **Data:**: A data e a hora (no formato UTC) de ocorrência do evento.

- **Endereço IP**: O endereço IP do dispositivo que foi usado quando a atividade foi registrada. O endereço IP é exibido em um formato de endereço IPv4 ou IPv6.

- **Usuário**: O usuário (ou a conta de serviço) que realizou a ação que disparou o evento.

- **Atividade**: A atividade realizada pelo usuário. Esse valor corresponde às atividades que você selecionou na lista suspensa Atividades. Para um evento do log de auditoria de administradores do Exchange, o valor nessa coluna é um cmdlet do Exchange.

- **Item**: O objeto que foi criado ou modificado como resultado da atividade correspondente. Por exemplo, o arquivo que foi exibido ou modificado ou a conta do usuário que foi atualizada. Nem todas as atividades têm um valor nesta coluna.

- **Detalhe:** detalhes adicionais sobre uma atividade. Novamente, nem todas as atividades terão um valor.

## <a name="step-3-filter-the-search-results"></a>Etapa 3: Filtrar os resultados da pesquisa

Além de classificar, você também pode filtrar os resultados de uma pesquisa de log de auditoria. Isso pode ajudá-lo a filtrar rapidamente os resultados de um usuário ou atividade específico. 

Para filtrar os resultados:

 1. Criar e executar uma pesquisa de log de auditoria.
  
2. Quando os resultados forem exibidos, clique em **Filtrar resultados**.
 
3. Caixas de palavras-chave são exibidas em cada cabeçalho de coluna.
  
4. Clique em uma das caixas sob um cabeçalho de coluna e digite uma palavra ou frase, dependendo da coluna na qual você está filtrando. Os resultados serão reajustados dinamicamente para exibir os eventos que correspondem ao seu filtro.
  
5. Para limpar um filtro, clique no **X** na caixa de filtro ou clique em **Ocultar filtragem.**

## <a name="export-the-search-results-to-a-file"></a>Exportar os resultados da pesquisa para um arquivo

Você pode exportar os resultados de uma pesquisa de log de auditoria para um arquivo de valores separados por vírgula (CSV) no computador local. Você pode abrir esse arquivo no Microsoft Excel e usar recursos como pesquisa, classificação, filtragem e divisão de uma única coluna (que contém células de vários valores) em várias colunas.

1. Execute uma pesquisa de logs de auditoria e, em seguida, reveja os critérios de pesquisa até ter os resultados desejados.
  
2. Clique em Exportar resultados e selecione uma das seguintes opções:

    - **Salve os resultados carregados:** Escolha essa opção para exportar somente as  entradas exibidas em Resultados na página de pesquisa **do log de Auditoria** Custodiada. O arquivo CSV baixado contém as mesmas colunas (e dados) exibidos na página (Data, Usuário, Atividade, Item e Detalhes). Uma coluna adicional (intitulada **Mais)** está incluída no arquivo CSV que contém mais informações da entrada do log de auditoria. Como você está exportando os mesmos resultados que estão carregados (e visíveis) na página Pesquisa de log de auditoria, no máximo 5.000 entradas são exportadas.
        
    - **Baixe todos os resultados:** Escolha essa opção para exportar todas as entradas do log de auditoria que atendem aos critérios de pesquisa. Para um grande conjunto de resultados de pesquisa, escolha essa opção para baixar todas as entradas do log de auditoria, além dos 5.000 resultados que podem ser exibidos na página de pesquisa do **log** de Auditoria Custodiante. Essa opção baixará os dados brutos do log de auditoria para um arquivo CSV e conterá informações adicionais da entrada do log de auditoria em uma coluna chamada AuditData. O download do arquivo poderá ser mais demorado se você escolher essa opção de exportação, pois o arquivo pode ser muito maior do que o baixado com a outra opção.
    
      > [!IMPORTANT]
      > É possível baixar no máximo 50 mil entradas para um arquivo CSV de uma única pesquisa de logs de auditoria. Se 50 mil entradas forem baixadas para o arquivo CSV, você poderá supor que existem provavelmente mais de 50 mil eventos que corresponderam aos critérios de pesquisa. Para exportar mais do que esse limite, tente usar um intervalo de datas para reduzir o número de entradas do log de auditoria. Talvez seja necessário executar várias pesquisas com intervalos de datas menores para exportar mais de 50 mil entradas.
        

3. Depois de selecionar uma opção de exportação, uma mensagem será exibida na parte inferior da janela solicitando que você abra o arquivo CSV, salve-o na pasta Downloads ou salve-o em uma pasta específica

Para obter mais informações sobre como exibir, filtrar ou exportar resultados de pesquisa de log de auditoria, consulte Pesquisar o log de auditoria no Centro de Conformidade & [Segurança.](search-the-audit-log-in-security-and-compliance.md)
