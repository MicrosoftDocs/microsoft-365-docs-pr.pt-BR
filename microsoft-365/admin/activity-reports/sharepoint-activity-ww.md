---
title: Microsoft 365 Relatórios no centro de administração - SharePoint atividade
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
description: Obter o SharePoint de uso da atividade para saber sobre a atividade de cada usuário SharePoint, o número de arquivos compartilhados e a utilização de armazenamento.
ms.openlocfilehash: f049a67e8444654e05cfe3dc72a8d4fe39792cb2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244075"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Microsoft 365 Relatórios no centro de administração - SharePoint atividade

Como administrador Microsoft 365, o painel **Relatórios** mostra a visão geral da atividade em vários produtos em sua organização. Ele permite um detalhamento para que você possa obter informações mais granulares sobre as atividades específicas a cada produto. Confira os relatórios [de atividades no Microsoft 365 de administração.](activity-reports.md)
  
Por exemplo, você pode entender a atividade de cada usuário licenciado para uso do SharePoint examinando sua interação com os arquivos. Isso também ajuda você a entender o nível de colaboração atual examinando o número de arquivos compartilhados.
  
> [!NOTE]
> Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou um Exchange, SharePoint, serviço Teams, comunicações Teams ou Skype for Business para ver relatórios. 
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>Como posso acessar o relatório de atividade do SharePoint?

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>. 
2. Na página inicial do painel, clique no botão **Exibir mais** no cartão SharePoint.
  
## <a name="interpret-the-sharepoint-activity-report"></a>Interpretar o relatório SharePoint atividade

Você pode exibir as atividades no relatório de SharePoint escolhendo a **guia** Atividade.<br/>![Microsoft 365 relatórios - Relatório de atividades SharePoint Microsoft.](../../media/5a0a96f-0e4f-4fb9-8baa-3262275b3d1f.png)

Selecione **Escolher colunas** para adicionar ou remover colunas do relatório.  <br/> ![SharePoint relatório de atividades - escolha colunas](../../media/3c396cd1-9701-4712-8eaa-eb7bba702aa8.png)

Você também pode exportar os dados do relatório para um arquivo Excel .csv selecionando o link **Exportar.** Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados. 
  
|Item|Descrição|
|:-----|:-----|
|**Indicador**|**Definição**|
|Nome de usuário  <br/> |O endereço de email do usuário que realizou a atividade no SharePoint Site.  <br/> |
|Data da última atividade (UTC)  <br/> |A data mais recente em que uma atividade de arquivo foi executada ou uma página foi visitada para o intervalo de datas selecionado. Para ver a atividade que ocorreu em uma data específica, selecione a data diretamente no gráfico.  <br/> |
|Arquivos exibidos ou editados  <br/> |O número de arquivos que o usuário carregou, baixou, modificou ou exibiu.   <br/> |
|Arquivos sincronizados  <br/> |O número de arquivos que foram sincronizados do dispositivo local de um usuário para o SharePoint site. <br/> |
|Arquivos compartilhados internamente  <br/> | A contagem de arquivos que foram compartilhados com usuários dentro da organização ou com usuários dentro de grupos (que podem incluir usuários externos).  <br/> |
|Arquivos compartilhados externamente  <br/> |O número de arquivos que foram compartilhados com usuários fora da organização. <br/>|
|Páginas visitadas  <br/> |As visitas a páginas exclusivas pelo usuário. <br/>|
|Deleted  <br/> | Isso indica que a licença do usuário foi removida.  <br/>  **OBSERVAÇÃO:** A atividade de um usuário excluído ainda será exibida no relatório desde que ele tenha sido licenciado em algum momento durante o período de tempo selecionado. A coluna Excluído ajuda você a observar que o usuário pode não estar mais ativo, mas contribuiu com os dados no relatório.  <br/> |
|Data excluída  <br/> |A data em que a licença do usuário foi removida. <br/>|
|Produto atribuído  <br/> |Os Microsoft 365 que são licenciados para o usuário.|
|||