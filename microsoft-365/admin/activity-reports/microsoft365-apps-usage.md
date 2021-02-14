---
title: Relatórios do Microsoft 365 no centro de administração - uso dos Aplicativos do Microsoft 365
ms.author: sirkkuw
author: sirkkuw
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
ms.openlocfilehash: 3230098336cd17236d754dbfea796c373ea98fe4
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948959"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>Relatórios do Microsoft 365 no centro de administração - uso dos Aplicativos do Microsoft 365

O painel Relatórios  do Microsoft 365 mostra a visão geral das atividades em todos os produtos em sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md).

 Por exemplo, você pode entender a atividade de cada usuário licenciado para usar os aplicativos do Microsoft 365 Apps observando suas atividades entre os aplicativos e como eles são utilizados em todas as plataformas.


 > [!NOTE]
 > Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou um administrador do Exchange, SharePoint ou Skype for Business para ver os relatórios.

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>Como obter o relatório de uso do Microsoft 365 Apps

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.

 2. No **drop-down Selecionar** um relatório, selecione o uso do **Office 365**   \>  **Microsoft 365 Apps.**

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>Interpretar o relatório de uso do Microsoft 365 Apps

Você pode ver a atividade dos Aplicativos do Microsoft 365 do usuário analisando os gráficos **Usuários** **e Plataformas.**

![Relatório de uso dos Aplicativos do Microsoft 365](../../media/proplususagenumbers.png)

|Item|Descrição|
 |:-----|:-----|
 |1. <br/> |O relatório de uso do **Microsoft 365 Apps** pode ser consultado sobre tendências dos últimos 7, 30, 90 ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela (7) mostrará dados por até 28 dias a partir da data atual (e não a data em que o relatório foi gerado). <br/> |
 |2. <br/> |Os dados em cada relatório geralmente abrangem até os últimos sete dias. <br/> |
 |3. <br/> |A **exibição** Usuários mostra a tendência no número de usuários ativos para cada aplicativo – Outlook, Word, Excel, PowerPoint, OneNote e Teams. "Usuários ativos" são aqueles que executam ações intencionais nesses aplicativos. <br/> |
 |4. <br/> |O **visualização Plataformas** mostra a tendência de usuários ativos em todos os aplicativos para cada plataforma – Windows, Mac, Web e Mobile. <br/> |
 |5.<br/>|No gráfico **Usuários,** o eixo Y é o número de usuários ativos exclusivos para o respectivo aplicativo. No gráfico **Plataformas,** o eixo Y é o   número de usuários exclusivos da respectiva plataforma. O eixo X em ambos os gráficos é a data em que um aplicativo foi usado em uma determinada plataforma.<br/>|
 6.<br/>|Você pode filtrar a série que vê no gráfico selecionando um item na legenda. Por exemplo, no gráfico **Usuários,** selecione Outlook, Word, Excel, PowerPoint, OneDrive ou Teams para ver apenas as informações relacionadas a cada um deles. Alterar essa seleção não altera as informações da tabela de grade abaixo dela.|
 |7.<br/>|A tabela mostra o detalhamento dos dados no nível do usuário. Você pode adicionar ou remover colunas da tabela. <br/><br/>**Nome** de usuário é o endereço de email do usuário que realizou a atividade no Microsoft Apps.<br><br/>**A última data de ativação (UTC)** é a última data em que o usuário ativou sua assinatura do Microsoft 365 Apps.<br/><br/>**A data da última atividade (UTC)** é a última data em que uma atividade intencional foi executada pelo usuário. Para ver a atividade que ocorreu em uma data específica, selecione a data diretamente no gráfico.<br/><br/>As colunas a seguir correspondem a cada aplicativo que identifica se o usuário estava ativo no aplicativo no período selecionado:<br> <br>**Outlook** <br>**Word** <br>**Excel**<br>**PowerPoint** <br>**OneNote**<br><br> As colunas a seguir correspondem a cada plataforma que identifica se o usuário estava ativo nessa plataforma para qualquer aplicativo (no Microsoft 365 Apps) no período selecionado:<br><br>**Outlook (Windows)**<br>**Outlook (Mac)**<br>**Outlook (Web)** <br>**Outlook (Dispositivos Móveis)**<br> **Word (Windows)**<br> **Word (Mac)**<br> **Word (Web)**<br> **Word (Móvel)**<br> **Excel (Windows)**<br> **Excel (Mac)**<br> **Excel (Web)**<br> **Excel (Dispositivos Móveis)**<br> **PowerPoint (Windows)**<br> **PowerPoint (Mac)**<br>**PowerPoint (Web)**<br> **PowerPoint (Dispositivos Móveis)**<br> **OneNote (Windows)**<br> **OneNote (Mac)**<br> **OneNote (Web)**<br>**OneNote (Dispositivos Móveis)**<br> **Teams (Windows)**<br> **Teams (Mac)**<br> **Teams (Web)**<br>**Teams (Dispositivos Móveis)** |
 |8.<br/>|Selecione o **ícone Gerenciar colunas** para adicionar ou remover colunas do relatório.|
 |9.<br/>|Você também pode exportar os dados do relatório para um arquivo .csv do Excel selecionando o link **Exportar.** Isso exporta dados para todos os usuários e permite que você faça agregação, classificação e filtragem simples para análise posterior. Se você tiver menos de 100 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 100 usuários, para filtrar e classificar, precisará exportar os dados.|
