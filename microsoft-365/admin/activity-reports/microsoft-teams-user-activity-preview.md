---
title: Relatórios do Microsoft 365 no centro de administração - atividade do usuário do Microsoft Teams
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
description: Saiba como obter o relatório de atividades do usuário do Microsoft Teams e obter informações sobre a atividade do Teams em sua organização.
ms.openlocfilehash: e8e4ab6fd78fb290243d8fdc780b5a7a14ca2ee0
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233405"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Relatórios do Microsoft 365 no centro de administração - atividade do usuário do Microsoft Teams

O painel Relatórios  do Microsoft 365 mostra a visão geral das atividades em todos os produtos em sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md). No relatório de atividade de usuários do Microsoft Teams, você pode obter informações sobre a atividade do Microsoft Teams em sua organização.
  
> [!NOTE]
> Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou um administrador do Exchange, SharePoint, Teams Service, Teams Communications ou Skype for Business para ver os relatórios.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Como gerar o relatório de atividade de usuários do Microsoft Teams

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.
2. Na home page do painel, clique no botão Exibir **mais** no cartão de atividades do Microsoft Teams.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Interpretar o relatório de atividade de usuários do Microsoft Teams

Você pode exibir a atividade do usuário no relatório do Teams escolhendo a **guia Atividade do** usuário. <br/>![Relatórios do Microsoft 365 - Atividade do usuário do Microsoft Teams.](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

Selecione **Escolher colunas** para adicionar ou remover colunas do relatório.  <br/> ![Teams user activity report - choose columns](../../media/a1513028-cf09-4186-93a6-8a203cd22475.png)

Você também pode exportar os dados do relatório para um arquivo .csv do Excel selecionando o link **Exportar.** Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados. O formato exportado para **tempo de áudio,** **tempo de vídeo** e tempo de **compartilhamento** de tela segue o formato de duração ISO8601.

O relatório **Atividade de usuários do Microsoft Teams** pode ser consultado sobre tendências dos últimos 7, 30, 90 ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela (7) mostrará dados por até 28 dias a partir da data atual (e não a data em que o relatório foi gerado).

Para garantir a qualidade dos dados, realizamos verificações diárias de validação de dados nos últimos três dias e preencheremos as lacunas detectadas. Você pode notar diferenças nos dados históricos durante o processo.

|Item|Descrição|
|:-----|:-----|
|**Indicador**|**Definição**|
|Nome de usuário  <br/> |O endereço de email do usuário. Você pode exibir o endereço de email real ou tornar este campo anônimo.   <br/> |
|Mensagens de canal   <br/> |O número de mensagens exclusivas que o usuário publicou em um chat da equipe durante o período de tempo especificado.  <br/> |
|Mensagens de chat   <br/> |O número de mensagens exclusivas que o usuário publicou em um chat privado durante o período de tempo especificado.  <br/> |
|Total de reuniões   <br/> |O número de reuniões online em que o usuário participou durante o período de tempo especificado.  <br/> |
|Chamadas 1:1   <br/> | O número de chamadas 1:1 das que o usuário participou durante o período de tempo especificado.  <br/> |
|Data da última atividade (UTC)  <br/> |A última data em que o usuário participou de uma atividade do Microsoft Teams.<br/> |
|Reuniões participadas adhoc   <br/> | O número de reuniões não agendadas no calendário em que o usuário participou durante o período de tempo especificado.  <br/> |
|Reuniões organizadas adhoc <br/> |O número de reuniões não agendadas no calendário que o usuário organizou durante o período de tempo especificado. <br/>|
|Reuniões organizadas agendadas  <br/> |O número de reuniões agendadas que um usuário organizou durante o período de tempo especificado.  <br/> |
|É licenciado |Selecionado se o usuário estiver licenciado para usar o Teams.|
|Outras atividades|O Usuário está ativo, mas realizou outras atividades além dos tipos de ação expostos oferecidos no relatório (enviar ou responder mensagens de canal e mensagens de chat, agendar ou participar de chamadas e reuniões 1:1). Exemplos de ações são quando um usuário altera o status do Teams ou a mensagem de status do Teams ou abre uma postagem de Mensagem de Canal, mas não responde. |
|||