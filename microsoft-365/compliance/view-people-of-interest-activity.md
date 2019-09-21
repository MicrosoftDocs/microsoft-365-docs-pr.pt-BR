---
title: Exibir a atividade de auditoria de pessoas de interesse
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
description: ''
ms.openlocfilehash: a0521921af086aef49ae81b178f9df1ffcff09a1
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073285"
---
# <a name="view-the-audit-activity-of-people-of-interest"></a>Exibir a atividade de auditoria de pessoas de interesse

Precisa localizar se um usuário exibir um documento específico ou limpar um item de sua caixa de correio? As investigações de dados (visualização) agora estão integradas à ferramenta de pesquisa de log de auditoria existente no centro de conformidade do & de segurança. Usando essa experiência incorporada, você pode usar as investigações de dados (visualização) pessoas da ferramenta de gerenciamento de interesse para facilitar sua investigação, acessando e procurando facilmente a atividade para pessoas de interesse em sua investigação.

## <a name="before-you-begin"></a>Antes de começar

Você precisa receber a função de logs de auditoria somente para exibição ou logs de auditoria no Exchange Online para pesquisar o log de auditoria do Office 365. Por padrão, essas funções são atribuídas aos grupos de função gerenciamento de conformidade e gerenciamento da organização na página permissões no centro de administração do Exchange. Para conceder ao usuário a capacidade de Pesquisar o log de auditoria de investigações de dados (visualização) com o nível mínimo de privilégios, você pode criar um grupo de função personalizado no Exchange Online, adicionar os logs de auditoria somente para exibição ou a função logs de auditoria e, em seguida, adicionar o usuário como membro da nova função gr oup. Para obter mais informações, consulte Manage role groups in Exchange Online.

> [!IMPORTANT]
> Se você atribuir a um usuário a função logs de auditoria somente para exibição ou logs de auditoria na página permissões no centro de conformidade de & de segurança, elas não poderão pesquisar o log de auditoria do Office 365. Você precisa atribuir as permissões no Exchange Online. Isso ocorre porque o cmdlet subjacente usado para pesquisar o log de auditoria é um cmdlet do Exchange Online.

## <a name="step-1-create-an-data-investigations-preview-audit-log-search"></a>Etapa 1: criar uma pesquisa de investigação de dados (visualização) pesquisa de log de auditoria

   1. Selecione uma investigação existente no **centro de conformidade de & de segurança > investigações de dados (versão prévia)**.
   
   2. Navegue até a guia **pessoas de interesse** e selecione uma pessoa.
   
   3. Depois de selecionar uma pessoa, clique em **Exibir atividade** no painel de detalhes.
   
   4. Configure os seguintes critérios de pesquisa:
      
      a. **Atividades** -clique na lista suspensa para exibir as atividades que você pode pesquisar. Depois de executar a pesquisa, somente os registros de auditoria das atividades selecionadas são exibidos. Selecionar **Mostrar resultados de todas as atividades** exibirá os resultados de todas as atividades que atendem aos outros critérios de pesquisa.
      
      b. **Data de início e data de término** -selecione um intervalo de data e hora para exibir os eventos que ocorreram dentro desse período. Os últimos sete dias são selecionados por padrão. A data e a hora são apresentadas no formato UTC (tempo Universal Coordenado). O intervalo de datas máximo que você pode especificar é um ano.
      
      c. **Pessoas de interesse** -clique nesta caixa e selecione um ou mais responsáveis para exibir os resultados da pesquisa. Os registros de auditoria da atividade selecionada executada pelos usuários selecionados nesta caixa são exibidos na lista de resultados.
    
    1. Clique em **Pesquisar** para executar a pesquisa usando seus critérios de pesquisa. Os resultados da pesquisa são carregados e após alguns momentos em que são exibidos em resultados na página de pesquisa pessoas de interesse. 

## <a name="step-2-view-the-audit-log-search-results"></a>Etapa 2: exibir os resultados da pesquisa de log de auditoria

Os resultados de uma pesquisa de log de auditoria são exibidos em resultados na página de log de auditoria pessoas de interesse. Um máximo de 5.000 (mais recentes) eventos são exibidos em incrementos de 150 eventos. Para exibir mais eventos, você pode usar a barra de rolagem no painel de resultados ou pode pressionar Shift + End para exibir os próximos 150 eventos.

Os resultados contêm as seguintes informações sobre cada evento retornado pela pesquisa.
- **Date**: a data e hora (no formato UTC) quando o evento ocorreu.

- **Endereço IP**: o endereço IP do dispositivo que foi usado quando a atividade foi registrada. O endereço IP é exibido em um formato de endereço IPv4 ou IPv6.

- **Usuário**: o usuário (ou conta de serviço) que executou a ação que disparou o evento.

- **Atividade**: a atividade realizada pelo usuário. Esse valor corresponde às atividades que você selecionou na lista suspensa atividades. Para um evento do log de auditoria do administrador do Exchange, o valor desta coluna é um cmdlet do Exchange.

- **Item**: o objeto que foi criado ou modificado como resultado da atividade correspondente. Por exemplo, o arquivo que foi exibido ou modificado ou a conta de usuário que foi atualizada. Nem todas as atividades têm um valor nesta coluna.

- **Detalhe**: detalhes adicionais sobre uma atividade. Novamente, nem todas as atividades terão um valor.

## <a name="step-3-filter-the-search-results"></a>Etapa 3: filtrar os resultados da pesquisa

Além da classificação, você também pode filtrar os resultados de uma pesquisa de log de auditoria. Isso pode ajudá-lo a filtrar rapidamente os resultados de um usuário ou atividade específico. 

Para filtrar os resultados:

 1. Criar e executar uma pesquisa de log de auditoria.
  
2. Quando os resultados forem exibidos, clique em **filtrar resultados**.
 
3. As caixas de palavras-chave são exibidas sob cada cabeçalho de coluna.
  
4. Clique em uma das caixas sob um cabeçalho de coluna e digite uma palavra ou frase, dependendo da coluna que você está filtrando. Os resultados serão reajustados dinamicamente para exibir os eventos que correspondam ao seu filtro.
  
5. Para limpar um filtro, clique no **X** na caixa filtro ou clique em **ocultar filtragem**.

## <a name="export-the-search-results-to-a-file"></a>Exportar os resultados da pesquisa para um arquivo

Você pode exportar os resultados de uma pesquisa de log de auditoria para um arquivo CSV (valor separado por vírgula) no computador local. Você pode abrir esse arquivo no Microsoft Excel e usar recursos como pesquisa, classificação, filtragem e divisão de uma única coluna (que contém células de vários valores) em várias colunas.

1. Execute uma pesquisa de log de auditoria e revise os critérios de pesquisa até que você tenha os resultados desejados.
  
2. Clique em exportar resultados e selecione uma das seguintes opções:

    - **Salvar resultados carregados:** Escolha essa opção para exportar apenas as entradas que são exibidas em **resultados** na página **pesquisa de log de auditoria de interesse** . O arquivo CSV baixado contém as mesmas colunas (e dados) exibidas na página (data, usuário, atividade, item e detalhes). Uma coluna adicional (intitulada **mais**) é incluída no arquivo CSV que contém mais informações da entrada do log de auditoria. Como você está exportando os mesmos resultados que são carregados (e exibíveis) na página pesquisa de log de auditoria, um máximo de 5.000 entradas são exportadas.
        
    - **Baixar todos os resultados:** Escolha essa opção para exportar todas as entradas do log de auditoria do Office 365 que atendam aos critérios de pesquisa. Para obter um grande conjunto de resultados de pesquisa, escolha essa opção para baixar todas as entradas do log de auditoria, além dos resultados 5.000 que podem ser exibidos na página **de pesquisa de log de auditoria de interesse** . Essa opção baixará os dados brutos do log de auditoria para um arquivo CSV e conterá informações adicionais da entrada do log de auditoria em uma coluna chamada AuditData. Pode levar mais tempo para baixar o arquivo se você escolher essa opção de exportação porque o arquivo pode ser muito maior do que o baixado, se você escolher a outra opção.
    
      > [!IMPORTANT]
      > Você pode baixar um máximo de 50.000 entradas para um arquivo CSV de uma única pesquisa de log de auditoria. Se as entradas 50.000 forem baixadas para o arquivo CSV, provavelmente você poderá supor que há mais de 50.000 eventos que atingiram os critérios de pesquisa. Para exportar mais do que esse limite, tente usar um intervalo de datas para reduzir o número de entradas de log de auditoria. Você pode ter que executar várias pesquisas com intervalos de datas menores para exportar mais de 50.000 entradas.
        

3. Após selecionar uma opção de exportação, uma mensagem é exibida na parte inferior da janela que solicita que você abra o arquivo CSV, salve-o na pasta downloads ou salve-o em uma pasta específica

Para obter mais informações sobre a exibição, filtragem ou exportação de resultados de pesquisa de log de auditoria, consulte [Search the Audit Log In The Office 365](search-the-audit-log-in-security-and-compliance.md).