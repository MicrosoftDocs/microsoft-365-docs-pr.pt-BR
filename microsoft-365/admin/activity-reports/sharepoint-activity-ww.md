---
title: Relatórios do Microsoft 365 no centro de administração - Atividade do SharePoint
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Obter o relatório de uso da atividade do SharePoint para saber mais sobre a atividade de cada usuário do SharePoint, o número de arquivos compartilhados e a utilização de armazenamento.
ms.openlocfilehash: 1d4b288fed9e15139c92bc7e43795393d03ba2fb
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649730"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Relatórios do Microsoft 365 no centro de administração - Atividade do SharePoint

Como administrador do Microsoft 365, o painel **Relatórios** mostra a visão geral das atividades em vários produtos em sua organização. Ele permite um detalhamento para que você possa obter informações mais granulares sobre as atividades específicas a cada produto. Confira os relatórios [de atividades no centro de administração do Microsoft 365.](activity-reports.md)
  
Por exemplo, você pode entender a atividade de cada usuário licenciado para uso do SharePoint examinando sua interação com os arquivos. Isso também ajuda você a entender o nível de colaboração atual examinando o número de arquivos compartilhados.
  
> [!NOTE]
> Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou um administrador do Exchange, SharePoint, Teams Service, Teams Communications ou Skype for Business para ver os relatórios. 
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>Como posso acessar o relatório de atividade do SharePoint?

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>. 
2. Na home page do painel, clique no botão Exibir **mais** no cartão do SharePoint.
  
## <a name="interpret-the-sharepoint-activity-report"></a>Interpretar o relatório de atividades do SharePoint

Você pode exibir as atividades no relatório do SharePoint escolhendo a **guia** Atividade.<br/>![Relatórios do Microsoft 365 - Relatório de atividades do Microsoft SharePoint.](../../media/5a0a96f-0e4f-4fb9-8baa-3262275b3d1f.png)

Selecione **Escolher colunas** para adicionar ou remover colunas do relatório.  <br/> ![Relatório de atividades do SharePoint - escolher colunas](../../media/3c396cd1-9701-4712-8eaa-eb7bba702aa8.png)

Você também pode exportar os dados do relatório para um arquivo .csv do Excel selecionando o link **Exportar.** Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados. 
  
|Item|Descrição|
|:-----|:-----|
|**Indicador**|**Definição**|
|Nome de usuário  <br/> |O endereço de email do usuário que realizou a atividade no Site do SharePoint.  <br/> |
|Data da última atividade (UTC)  <br/> |A última data em que uma atividade de arquivo foi executada ou uma página foi visitada para o intervalo de datas selecionado. Para ver a atividade que ocorreu em uma data específica, selecione a data diretamente no gráfico.  <br/> |
|Arquivos exibidos ou editados  <br/> |O número de arquivos que o usuário carregou, baixou, modificou ou visualizou.   <br/> |
|Arquivos sincronizados  <br/> |O número de arquivos que foram sincronizados do dispositivo local de um usuário com o site do SharePoint. <br/> |
|Arquivos compartilhados internamente  <br/> | A contagem de arquivos que foram compartilhados com usuários dentro da organização ou com usuários dentro de grupos (que podem incluir usuários externos).  <br/> |
|Arquivos compartilhados externamente  <br/> |O número de arquivos que foram compartilhados com usuários de fora da organização. <br/>|
|Páginas visitadas  <br/> |As visitas a páginas exclusivas pelo usuário. <br/>|
|Deleted  <br/> | Isso indica que a licença do usuário foi removida.  <br/>  **OBSERVAÇÃO:** A atividade de um usuário excluído ainda será exibida no relatório, desde que ele tenha sido licenciado em algum momento durante o período de tempo selecionado. A coluna Excluído ajuda você a observar que o usuário pode não estar mais ativo, mas contribuiu com os dados no relatório.  <br/> |
|Data de exclusão  <br/> |A data em que a licença do usuário foi removida. <br/>|
|Produto atribuído  <br/> |Os produtos do Microsoft 365 que são licenciados para o usuário.|
|||