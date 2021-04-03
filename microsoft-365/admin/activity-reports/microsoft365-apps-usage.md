---
title: Relatórios do Microsoft 365 no centro de administração - uso do Microsoft 365 Apps
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
description: Saiba como obter um relatório de uso do Microsoft 365 Apps usando o painel Relatórios do Microsoft 365 no centro de administração do Microsoft 365.
ms.openlocfilehash: 362697ba8dd40a12107e1b2d9ad6ef1bededda7d
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579573"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>Relatórios do Microsoft 365 no centro de administração - uso do Microsoft 365 Apps

O painel Relatórios  do Microsoft 365 mostra a visão geral da atividade em todos os produtos em sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md).

 Por exemplo, você pode entender a atividade de cada usuário licenciado para usar aplicativos do Microsoft 365 Apps observando suas atividades nos aplicativos e como elas são usadas em plataformas.


 > [!NOTE]
 > Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou administrador do Exchange, SharePoint ou Skype for Business para ver relatórios.

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>Como chegar ao relatório de uso do Microsoft 365 Apps

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.

 2. No **drop-down Selecionar um** relatório, selecione Uso do **Office 365**   \>  **Microsoft 365 Apps** .

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>Interpretar o relatório de uso do Microsoft 365 Apps

Você pode obter uma exibição na atividade do Microsoft 365 Apps do usuário, olhando para os gráficos **Usuários** **e Plataforma.**

![Relatório de uso do Microsoft 365 Apps](../../media/proplususagenumbers.png)

|Item|Descrição|
 |:-----|:-----|
 |1. <br/> |O relatório de uso do **Microsoft 365 Apps** pode ser exibido para tendências nos últimos 7 dias, 30, 90 dias ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela (7) mostrará dados por até 28 dias a partir da data atual (e não a data em que o relatório foi gerado). <br/> |
 |2. <br/> |Os dados em cada relatório geralmente abrangem até os últimos sete dias. <br/> |
 |3. <br/> |A **exibição** Usuários mostra a tendência no número de usuários ativos para cada aplicativo – Outlook, Word, Excel, PowerPoint, OneNote e Teams. "Usuários ativos" são aqueles que executam ações intencionais dentro desses aplicativos. <br/> |
 |4. <br/> |A **exibição Plataformas** mostra a tendência de usuários ativos em todos os aplicativos para cada plataforma – Windows, Mac, Web e Mobile. <br/> |
 |5.<br/>|No gráfico **Usuários,** o eixo Y é o número de usuários ativos exclusivos para o aplicativo respectivo. No gráfico **Plataformas,**   o eixo Y é o número de usuários exclusivos para a respectiva plataforma. O eixo X em ambos os gráficos é a data na qual um aplicativo foi usado em uma determinada plataforma.<br/>|
 6.<br/>|Você pode filtrar a série que você vê no gráfico selecionando um item na legenda. Por exemplo, no gráfico **Usuários,** selecione Outlook, Word, Excel, PowerPoint, OneDrive ou Teams para ver apenas as informações relacionadas a cada um. Alterar essa seleção não altera as informações na tabela de grade abaixo dela.|
 |7.<br/>|A tabela mostra o detalhamento dos dados no nível do usuário. Você pode adicionar ou remover colunas da tabela. <br/><br/>**Username** é o endereço de email do usuário que realizou a atividade no Microsoft Apps.<br><br/>**A última data de ativação (UTC)** é a data mais recente em que o usuário ativou sua assinatura do Microsoft 365 Apps.<br/><br/>**A última data de atividade (UTC)** é a data mais recente em que uma atividade intencional foi executada pelo usuário. Para ver a atividade que ocorreu em uma data específica, selecione a data diretamente no gráfico.<br/><br/>As colunas a seguir correspondem a cada aplicativo que identifica se o usuário estava ativo nesse aplicativo no período selecionado:<br> <br>**Outlook** <br>**Word** <br>**Excel**<br>**PowerPoint** <br>**OneNote**<br><br> As colunas a seguir correspondem a cada plataforma que identifica se o usuário estava ativo nessa plataforma para qualquer aplicativo (dentro do Microsoft 365 Apps) no período selecionado:<br><br>**Outlook (Windows)**<br>**Outlook (Mac)**<br>**Outlook (Web)** <br>**Outlook (Mobile)**<br> **Word (Windows)**<br> **Word (Mac)**<br> **Word (Web)**<br> **Word (Mobile)**<br> **Excel (Windows)**<br> **Excel (Mac)**<br> **Excel (Web)**<br> **Excel (Mobile)**<br> **PowerPoint (Windows)**<br> **PowerPoint (Mac)**<br>**PowerPoint (Web)**<br> **PowerPoint (Mobile)**<br> **OneNote (Windows)**<br> **OneNote (Mac)**<br> **OneNote (Web)**<br>**OneNote (Mobile)**<br> **Teams (Windows)**<br> **Teams (Mac)**<br> **Teams (Web)**<br>**Teams (Mobile)** |
 |8.<br/>|Selecione o **ícone Gerenciar colunas** para adicionar ou remover colunas do relatório.|
 |9.<br/>|Você também pode exportar os dados do relatório para um arquivo .csv do Excel selecionando o link **Exportar.** Isso exporta dados para todos os usuários e permite que você faça agregação, classificação e filtragem simples para análise posterior. Se você tiver menos de 100 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 100 usuários, para filtrar e classificar, será necessário exportar os dados.|
