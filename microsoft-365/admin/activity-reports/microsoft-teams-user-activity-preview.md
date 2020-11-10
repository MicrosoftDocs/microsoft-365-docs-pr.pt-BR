---
title: Relatórios do Microsoft 365 no centro de administração-atividade de usuário do Microsoft Teams
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Saiba como obter o relatório de atividades do usuário do Microsoft Teams e obtenha informações sobre a atividade do teams em sua organização.
ms.openlocfilehash: b85f073a2916b646a5a03e62913de44b410ca058
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988465"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Relatórios do Microsoft 365 no centro de administração-atividade de usuário do Microsoft Teams

O painel de **relatórios** do Microsoft 365 mostra a visão geral das atividades em todos os produtos de sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md). No relatório de atividade de usuários do Microsoft Teams, você pode obter informações sobre a atividade do Microsoft Teams em sua organização.
  
> [!NOTE]
> Você deve ser um administrador global, um leitor global ou um leitor de relatórios no Microsoft 365 ou um administrador do Exchange, do SharePoint, do teams ou do Skype for Business para ver os relatórios.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Como gerar o relatório de atividade de usuários do Microsoft Teams

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.
2. Na página inicial do painel, clique no botão **Exibir mais** no cartão de atividades do Microsoft Teams.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretar o relatório de atividade de usuários do Microsoft Teams

Você pode exibir a atividade do usuário no relatório do teams escolhendo a guia **atividade do usuário** . <br/>![Microsoft 365 Reports-atividade de usuário do Microsoft Teams.](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

Selecione **escolher colunas** para adicionar ou remover colunas do relatório.  <br/> ![Teams user activity report - choose columns](../../media/a1513028-cf09-4186-93a6-8a203cd22475.png)

Você também pode exportar os dados do relatório para um arquivo. csv do Excel selecionando o link de **exportação** . Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados. O formato exportado para hora de **áudio** , tempo de **vídeo** e **tempo de compartilhamento de tela** segue o formato de duração ISO8601.

|Item|Descrição|
|:-----|:-----|
|**Indicador**|**Definição**|
|Nome de usuário  <br/> |O endereço de email do usuário. Você pode exibir o endereço de email real ou tornar este campo anônimo.   <br/> |
|Mensagens de canal   <br/> |O número de mensagens exclusivas que o usuário publicou em um chat de equipe durante o período de tempo especificado.  <br/> |
|Mensagens de chat   <br/> |O número de mensagens exclusivas que o usuário publicou em um chat privado durante o período de tempo especificado.  <br/> |
|Total de reuniões   <br/> |O número de reuniões online nas quais o usuário participou durante o período de tempo especificado.  <br/> |
|chamadas 1:1   <br/> | O número de chamadas 1:1 que o usuário participou durante o período de tempo especificado.  <br/> |
|Data da última atividade (UTC)  <br/> |A última data em que o usuário participou em uma atividade do Microsoft Teams.<br/> |
|Reuniões participos do adhoc   <br/> | O número de reuniões não agendadas no calendário em que o usuário participou durante o período de tempo especificado.  <br/> |
|As reuniões organizadas como AdHoc <br/> |O número de reuniões não agendadas no calendário que o usuário organizou durante o período de tempo especificado. <br/>|
|Reuniões organizadas agendadas  <br/> |O número de reuniões agendadas que um usuário organizou durante o período de tempo especificado.  <br/> |
|É licenciado |Selecionado se o usuário está licenciado para usar o Microsoft Teams.|
|Outra atividade|O usuário está ativo, mas realizou outras atividades do que os tipos de ação expostos oferecidos no relatório (enviando ou respondendo a mensagens de canal e mensagens de chat, agendando ou participando de 1:1 chamadas e reuniões). Exemplos de ações são quando um usuário altera o status do teams ou a mensagem de status do teams ou abre uma postagem de mensagem de canal, mas não responde. |
|||