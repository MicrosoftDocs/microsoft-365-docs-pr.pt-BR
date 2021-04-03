---
title: Uso do dispositivo do Microsoft Teams
f1.keywords:
- NOCSH
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
ms.assetid: 917b3e1d-203e-4439-8539-634e80196687
description: Obtenha informações sobre os aplicativos do Microsoft Teams usados em sua organização ao obter o relatório de uso de aplicativos do Microsoft Teams a partir dos Relatórios do Microsoft 365.
ms.openlocfilehash: 453b5767a6da1361ba8121fa2d49d9db8224aa68
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579621"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>Relatórios do Microsoft 365 no centro de administração - Uso de dispositivos do Microsoft Teams

O painel Relatórios  do Microsoft 365 mostra a visão geral da atividade em todos os produtos em sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md). No relatório de uso do aplicativo Microsoft Teams, você encontra informações sobre os aplicativos do Microsoft Teams em uso na sua organização.
  
> [!NOTE]
> Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou um administrador do Exchange, SharePoint, Teams Service, Teams Communications ou Skype for Business para ver relatórios.  
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Como gerar o relatório de uso do aplicativo Microsoft Teams

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.

    
2. No **drop-down Selecionar um** relatório, selecione Uso de **dispositivo do Microsoft Teams** \> .
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Interpretar o relatório de uso do aplicativo Microsoft Teams

Você pode ver detalhes de uso do aplicativo do Microsoft Teams examinando os gráficos **Usuários** e **Distribuição**. 
  
![Relatórios do Microsoft 365 - Uso de aplicativos do Microsoft Teams](../../media/de35c4de-76b4-4109-a806-66774665499b.png)
  
|Item|Descrição|
|:-----|:-----|
|1.  <br/> |O relatório **Uso de dispositivo do Microsoft Teams** pode ser consultado sobre tendências dos últimos 7, 30, 90 ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela (7) mostrará dados por até 28 dias a partir da data atual (e não a data em que o relatório foi gerado).  <br/> |
|2.  <br/> |Os dados em cada relatório geralmente abrangem até as últimas 24 a 48 horas.  <br/> |
|3.  <br/> |O modo de exibição **Usuários** mostra o número de usuários exclusivos diariamente por aplicativo.  <br/> |
|4.  <br/> |O modo de exibição **Distribuição** mostra o número de usuários exclusivos por aplicativo no intervalo de tempo selecionado.  <br/> |
|5.  <br/> | No gráfico **Usuários**, o eixo Y representa o número de usuários por aplicativo.  <br/>  No gráfico **Distribuição**, o eixo Y representa o número de usuários que estão usando o aplicativo especificado.  <br/>  O eixo X nos gráficos representa o intervalo de datas selecionado para esse relatório específico.  <br/> |
|6.  <br/> |Você pode filtrar a série que você vê no gráfico selecionando um item na legenda. Por exemplo, no gráfico **Usuários,** selecione **Windows,** **Mac,** **Chamadas,** **Web,** **Telefone Android** ou **telefone Windows** para ver apenas as informações relacionadas a cada um deles. Ao alterar essa seleção, as informações da tabela não mudam.  <br/> ![Você pode filtrar gráficos de uso de aplicativos do Microsoft Teams selecionando o tipo de aplicativo.](../../media/64ee1cb1-ca80-4964-8234-7fc671135c3d.png)|
|7.  <br/> | A lista de grupos mostrada é determinada pelo conjunto de todos os grupos que existiram (que não foram excluídos) no mais amplo período de relatório (180 dias). A contagem de atividades variará de acordo com a seleção de data.  <br/> OBSERVAÇÃO: Talvez você não veja todos os itens na lista abaixo nas colunas até adicioná-los.<br/> **Nome de usuário** é o endereço de email do usuário. Você pode exibir o endereço de email real ou tornar este campo anônimo.  <br/> **Data da última atividade (UTC)** se refere à data da última atividade que o usuário participou em uma atividade do Microsoft Teams em um aplicativo.  <br/> **Excluídos** indica se a equipe foi excluída. Se a equipe foi excluída, mas teve atividade no período do relatório, ela é exibida na grade com a exclusão definida como true.  <br/> **Data de exclusão** é a data em que a equipe foi excluída.  <br/> **Windows** estará selecionado se o usuário estava ativo no aplicativo Windows durante o intervalo de tempo especificado.  <br/> **Mac** estará selecionado se o usuário estava ativo em um aplicativo Mac durante o intervalo de tempo especificado.  <br/> **Web** estará selecionado se o usuário estava ativo em um aplicativo Web durante o intervalo de tempo especificado.  <br/> **iOS** estará selecionado se o usuário estava ativo em um aplicativo iOS durante o intervalo de tempo especificado.  <br/> **Telefone Android** estará selecionado se o usuário estava ativo em um aplicativo para telefone Android durante o intervalo de tempo especificado.  <br/> **Telefone Windows** estará selecionado se o usuário estava ativo em um aplicativo para Windows Phone durante o intervalo de tempo especificado.  <br/>  Se as políticas da organização impedem a exibição de relatórios em que as informações do usuário podem ser identificadas, você pode alterar as configurações de privacidade para todos esses relatórios. Confira a seção Como ocultar detalhes do nível **do usuário?** na seção Relatórios de Atividades no centro de administração [do Microsoft 365.](activity-reports.md)  <br/> |
|8.  <br/> |Selecione **Colunas** para adicionar ou remover colunas do relatório.  <br/> ![Teams uapp usage report - choose columns](../../media/333f3077-696d-4829-b0a7-1046b3822222.png)|
|9.  <br/> |Você também pode exportar os dados do relatório para um arquivo .csv do Excel, selecionando o link **Exportar.** Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados.  <br/> |
|||
   
  

