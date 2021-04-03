---
title: Relatórios do Microsoft 365 no centro de administração - Atividade de formulários
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: Saiba como obter um relatório de atividades do Microsoft Forms usando o painel relatórios do Microsoft 365 no centro de administração do Microsoft 365.
ms.openlocfilehash: ce1109c6d6d626079794085b4dc742829841d06e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579669"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>Relatórios do Microsoft 365 no centro de administração - Atividade de formulários

O painel Relatórios  do Microsoft 365 mostra a visão geral da atividade em todos os produtos em sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md).
  
Por exemplo, você pode entender a atividade de cada usuário licenciado para usar o Microsoft Forms analisando sua interação com formulários. Ele também ajuda você a entender o nível de colaboração que está acontecendo, observando o número de formulários criados e formulários aos quais o usuário respondeu.
  
> [!NOTE]
> Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou um administrador do Exchange, SharePoint, Teams Service, Teams Communications ou Skype for Business para ver relatórios. 

## <a name="how-to-get-to-the-forms-activity-report"></a>Como chegar ao relatório de atividades do Forms

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.

    
2. No **drop-down Selecionar um** relatório, selecione **Atividade Formulários** \> .

## <a name="interpret-the-forms-activity-report"></a>Interpretar o relatório de atividades de formulários

Você pode obter uma exibição na atividade de formulários do usuário, analisando os gráficos **Atividade** **e Usuários.** 

![Relatório de atividades de formulários](../../media/adminformsactivity.png)

|Item|Descrição|
|:-----|:-----|
|1.  <br/> |O **relatório de** atividades forms pode ser exibido para tendências nos últimos 7 dias, 30, 90 ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela (7) mostrará dados por até 28 dias a partir da data atual (e não a data em que o relatório foi gerado).  <br/> |
|2.  <br/> |Os dados em cada relatório geralmente abrangem até as últimas 24 a 48 horas.  <br/> |
|3.  <br/> |A **exibição Usuários** ajuda você a entender a tendência no número de usuários de formulários ativos. Um usuário é considerado ativo se tiver executado uma atividade em torno de um formulário (criar, editar, exibir etc.) ou responder a um formulário dentro do período de tempo específico.  <br/> |
|4.  <br/> |O **exibição** Atividade ajuda você a entender a tendência no número de usuários ativos. Um usuário é considerado ativo quando executa uma atividade de arquivo (salvar, sincronizar, modificar ou compartilhar) ou visita uma página dentro do período específico.<br/> OBSERVAÇÃO: Uma atividade pode ocorrer várias vezes para um único formulário, mas contará apenas como um formulário ativo. Por exemplo, você pode criar um formulário e continuar editando o mesmo formulário várias vezes em um período de tempo especificado, mas ele contará apenas como um único formulário. No entanto, se um usuário enviou várias respostas para o mesmo formulário, cada resposta ainda seria uma resposta individual e, portanto, seria contada várias vezes. <br/> |
|5.<br/>|No gráfico **Usuários,** o eixo Y é o número de usuários exclusivos. Eixo X é a data em que os usuários exclusivos estão ativos. As legendas são:<br/><br/>**Designers** significa que o usuário criou ou editou um formulário.<br/>**Os respondentes** significam que o usuário enviou respostas a um formulário.<br/> **Total de** usuários significa qualquer pessoa na empresa que tenha sido designer ou respondente.<br/><br/> No gráfico **Atividade,** o eixo Y é a contagem de formas ou respostas exclusivas. Eixo X é a data em que ocorreu a atividade de formulário ou resposta. As legendas são:<br/><br/>**Os formulários** criados são a contagem de formulários exclusivos que os usuários criaram.<br/> **Respostas assinadas a** contagem de respostas assinadas pelos usuários na organização receberam.<br/> **Respostas anônimas** é a contagem de respostas anônimas que os usuários da organização receberam.<br/><br/>|
|6.<br/>|Você pode filtrar a série que você vê no gráfico selecionando um item na legenda. Por exemplo, no gráfico Usuários, selecione designers, respondentes ou usuários totais para ver apenas as informações relacionadas a cada um. Alterar essa seleção não altera as informações na tabela de grade abaixo dela.|
|7.<br/>|A tabela mostra uma divisão das atividades no nível por usuário. As legendas são:<br/><br/>**Username** é o endereço de email do usuário que realizou a atividade no Microsoft Forms.<br/>**A última data de atividade (UTC)** é a data mais recente em que uma atividade de formulário foi executada pelo usuário para o intervalo de datas selecionado. Para ver a atividade que ocorreu em uma data específica, selecione a data diretamente no gráfico.<br/><br/>Isso filtrará a tabela para exibir dados de atividade de arquivo somente para usuários que realizaram a atividade nesse dia específico.<br/><br/>**Número de formulários criados** é o número de formulários que o usuário criou.<br/> **O número de formulários respondidos** é o número de formulários aos que o usuário enviou respostas.|
|8.<br/>|Selecione o **ícone Gerenciar colunas** para adicionar ou remover colunas do relatório.|
|9.<br/>|Você também pode exportar os dados do relatório para um arquivo .csv do Excel selecionando o link **Exportar.** Isso exporta dados para todos os usuários e permite que você faça agregação, classificação e filtragem simples para análise posterior. Se você tiver menos de 100 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 100 usuários, para filtrar e classificar, será necessário exportar os dados.|