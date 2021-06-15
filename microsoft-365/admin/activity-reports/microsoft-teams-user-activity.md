---
title: Microsoft 365 de centro de administração - Microsoft Teams atividade do usuário
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
- MST160
- MET150
- MOE150
ms.assetid: 07f67fc4-c0a4-4d3f-ad20-f40c7f6db524
description: Saiba como obter o relatório Microsoft Teams atividade do usuário e obter informações sobre a atividade Teams em sua organização.
ms.openlocfilehash: c824a0ce285a085c9ae8b7326647ad4bcdf5f013
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924262"
---
# <a name="microsoft-365-admin-center-reports---microsoft-teams-user-activity"></a>Microsoft 365 de centro de administração - Microsoft Teams atividade do usuário

O painel Microsoft 365 **relatórios** mostra a visão geral da atividade em todos os produtos em sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md). No relatório de atividade de usuários do Microsoft Teams, você pode obter informações sobre a atividade do Microsoft Teams em sua organização.
  
> [!NOTE]
> Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou um Exchange, SharePoint, serviço Teams, comunicações Teams ou Skype for Business para ver relatórios.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Como gerar o relatório de atividade de usuários do Microsoft Teams

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.

    
2. No **drop-down Selecionar** um relatório, **selecione** Microsoft Teams Atividade do \> **usuário**.
  
## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretar o relatório de atividade de usuários do Microsoft Teams

Você pode observar a atividade de usuários do Microsoft Teams examinando os gráficos **Atividade** e **Usuários**.<br/>![Microsoft 365 relatórios - Microsoft Teams de usuário.](../../media/40359f81-25f7-416d-bb1e-37289133ef6b.png)
  
|Item|Descrição|
|:-----|:-----|
|1.  <br/> |O relatório **Atividade de usuários do Microsoft Teams** pode ser consultado sobre tendências dos últimos 7, 30, 90 ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela (7) mostrará dados por até 28 dias a partir da data atual (e não a data em que o relatório foi gerado).  <br/> |
|2.  <br/> |Os dados em cada relatório geralmente abrangem até as últimas 24 a 48 horas.  <br/> |
|3.  <br/> |Para garantir a qualidade dos dados, realizamos verificações diárias de validação de dados nos últimos cinco dias e preencheremos quaisquer lacunas detectadas. Você pode observar diferenças nos dados históricos durante o processo.  <br/> |
|4.  <br/> |O modo de exibição **Atividade** mostra o número de atividades do Microsoft Teams por tipo de atividade. Os tipos de atividade são número de mensagens de chat da equipe, mensagens de chat particular, chamadas ou reuniões.  <br/> |
|5.  <br/> |Os modo de exibição **Usuários** mostra o número de usuários por tipo de atividade. Os tipos de atividade são número de mensagens de chat da equipe, mensagens de chat particular, chamadas ou reuniões.  <br/> |
|6.  <br/> | No gráfico **Atividade,** o eixo Y é a contagem de atividade especificada.  <br/>  No gráfico **Arquivos,** o eixo Y é o número de usuários que participam de chats de equipe, chats privados, chamadas ou reuniões.  <br/>  O eixo X nos gráficos é o intervalo de datas selecionado para o relatório específico.  <br/> |
|7.  <br/> |Você pode filtrar a série que você vê no gráfico selecionando um item na legenda. Por exemplo, no gráfico **Atividade,** selecione Mensagens de **canal,** mensagens de **chat,** chamadas ou **reuniões** para ver apenas as informações relacionadas a cada uma delas. Ao alterar essa seleção, as informações da tabela não mudam.  <br/> ![Filtrar os gráficos Microsoft Teams de atividade](../../media/c819c4ea-6e9a-4411-a0dd-9f800d64ce38.png)|
|8.  <br/> | A lista de grupos mostrada é determinada pelo conjunto de todos os grupos que existiram (que não foram excluídos) no mais amplo período de relatório (180 dias). A contagem de atividades variará de acordo com a seleção de data.  <br/> OBSERVAÇÃO: Talvez você não veja todos os itens na lista abaixo nas colunas até adicioná-los.<br/>**Nome de usuário** é o endereço de email do usuário. Você pode exibir o endereço de email real ou tornar este campo anônimo.  <br/> **Data da última atividade (UTC)** se refere à data da última atividade que o usuário participou em uma atividade do Microsoft Teams.  <br/> **Mensagens do canal** é o número de mensagens exclusivas que o usuário publicou em um chat de equipe durante o período de tempo especificado.  <br/> **Mensagens de chat** é o número de mensagens exclusivas que o usuário publicou em um chat particular durante o período de tempo especificado.  <br/> **Chamadas** é o número de chamadas das quais o usuário participou durante o período especificado.  <br/> **Reuniões** é o número de reuniões online das quais o usuário participou durante o período especificado.  <br/> **Outra atividade** é o número de outras atividades da equipe por usuário.  <br/> **Excluídos** indica se a equipe foi excluída. Se a equipe foi excluída, mas teve atividade no período do relatório, ela é exibida na grade com a exclusão definida como true.  <br/> **Data de exclusão** é a data em que a equipe foi excluída.  <br/> **Produto atribuído** é a lista de produtos atribuídos ao usuário.  <br/>  Se as políticas da sua organização impedirem a exibição de relatórios em que as informações do usuário são identificáveis, você pode alterar a configuração de privacidade de todos esses relatórios. Confira a seção Como ocultar detalhes do nível **do usuário?** na seção Relatórios de [Atividades no Microsoft 365 de administração.](activity-reports.md)  <br/> |
|9.  <br/> |Selecione **Colunas** para adicionar ou remover colunas do relatório.  <br/> ![Teams user activity report - choose columns](../../media/eb5fbcee-e371-4d36-a0c6-fa54732311ec.png)|
|10.  <br/> |Você também pode exportar os dados do relatório para um arquivo Excel .csv selecionando o link **Exportar.** Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados.  <br/> |
|||
   

