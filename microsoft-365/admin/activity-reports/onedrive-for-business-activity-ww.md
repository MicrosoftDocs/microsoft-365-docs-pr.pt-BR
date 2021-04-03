---
title: Relatórios do Microsoft 365 no centro de administração - Atividade do OneDrive for Business
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: Receba o relatório de uso do OneDrive para sua organização e conheça a atividade de cada usuário do OneDrive, o número de arquivos compartilhados e a utilização de armazenamento.
ms.openlocfilehash: 7b6173b3a86187e4612aaaa51bafbfbe965a6cfa
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579525"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Relatórios do Microsoft 365 no centro de administração - Atividade do OneDrive for Business

O painel Relatórios  do Microsoft 365 mostra a visão geral da atividade em todos os produtos em sua organização. Ele permite a você detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md).
  
Por exemplo, você pode entender a atividade de cada usuário licenciado para uso do OneDrive examinando sua interação com os arquivos no OneDrive. Isso também ajuda você a entender o nível de colaboração atual examinando o número de arquivos compartilhados.
  
> [!NOTE]
> Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou um administrador do Exchange, SharePoint, Teams Service, Teams Communications ou Skype for Business para ver relatórios.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Como posso obter o relatório de atividades do OneDrive?

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>. 
2. Na página inicial do painel, clique no botão **Exibir mais** no cartão OneDrive.
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>Interpretar o relatório de atividades do OneDrive for Business

Você pode exibir as atividades no relatório do OneDrive escolhendo a **guia Atividade.**<br/>![Relatórios do Microsoft 365 - Relatório de atividades do Microsoft OneDrive.](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

Selecione **Escolher colunas** para adicionar ou remover colunas do relatório.  <br/> ![Relatório de atividades do OneDrive - escolha colunas](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

Você também pode exportar os dados do relatório para um arquivo .csv do Excel selecionando o link **Exportar.** Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados. 
  
|Item|Descrição|
|:-----|:-----|
|**Indicador**|**Definição**|
|Nome de usuário  <br/> |O nome de usuário do proprietário da conta do OneDrive.  <br/> |
|Data da última atividade (UTC)  <br/> |A data mais recente em que uma atividade de arquivo foi executada na conta do OneDrive para o intervalo de datas selecionado. . Para ver a atividade que ocorreu em uma data específica, selecione a data diretamente no gráfico.  <br/> |
|Arquivos exibidos ou editados  <br/> |O número de arquivos que o usuário carregou, baixou, modificou ou exibiu.   <br/> |
|Arquivos sincronizados  <br/> |O número de arquivos que foram sincronizados do dispositivo local de um usuário para a conta do OneDrive. <br/> |
|Arquivos compartilhados internamente  <br/> | O número de arquivos que foram compartilhados com usuários dentro da organização ou com usuários dentro de grupos (que podem incluir usuários externos).  <br/> |
|Arquivos compartilhados externamente  <br/> |O número de arquivos que foram compartilhados com usuários fora da organização. <br/>|
|Deleted  <br/> | Isso indica que a licença do usuário foi removida.  <br/> OBSERVAÇÃO: A atividade de um usuário excluído ainda será exibida em um relatório desde que ele tenha sido licenciado em algum momento durante o período de tempo selecionado. A coluna **Excluído** ajuda você a observar que o usuário pode não estar mais ativo, mas contribuiu com os dados no relatório.  <br/> |
|Data excluída  <br/> |A data em que a licença do usuário foi removida. <br/>|
|Produto atribuído  <br/> |Os produtos do Microsoft 365 licenciados para o usuário.|
|||