---
title: Relatórios do Microsoft 365 no centro de administração-atividade do SharePoint
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- SPO160
- BSA160
ms.assetid: a91c958f-1279-499d-9959-12f0de08dc8f
description: Obter o relatório de uso de atividades do SharePoint para saber mais sobre a atividade de cada usuário do SharePoint, o número de arquivos compartilhados e o uso do armazenamento.
ms.openlocfilehash: df025d41a2c570761fd59e228eebb277c922e06e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42353422"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Relatórios do Microsoft 365 no centro de administração-atividade do SharePoint

Como um administrador do Microsoft 365, o painel **relatórios** mostra a visão geral das atividades em vários produtos da sua organização. Ele permite um detalhamento para que você possa obter informações mais granulares sobre as atividades específicas a cada produto. Confira os [relatórios de atividades no centro de administração do Microsoft 365](activity-reports.md).
  
Por exemplo, você pode entender a atividade de cada usuário licenciado para uso do SharePoint examinando sua interação com os arquivos. Isso também ajuda você a entender o nível de colaboração atual examinando o número de arquivos compartilhados.
  
> [!NOTE]
> Algumas funcionalidades são introduzidas gradualmente. Isso significa que esse recurso pode ainda não estar disponível ou pode parecer diferente em relação ao que descrevemos nos artigos da Ajuda. Não se preocupe, se você ainda não conseguir vê-lo, ele aparecerá em breve! 
  
Se você quiser entender a quantidade de atividade que está ocorrendo em cada site do SharePoint e o uso do armazenamento, veja o [Relatório de uso do site do SharePoint](sharepoint-site-usage.md).
  
> [!NOTE]
> Você deve ser um administrador global, leitor global ou leitor de relatórios no Microsoft 365 ou um administrador do Exchange, SharePoint ou Skype for Business para ver os relatórios. 
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>Como posso acessar o relatório de atividade do SharePoint?

1. No centro de administração do, vá para a página**Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>.

    
2. Na lista suspensa **selecionar um relatório** , selecione **atividade** **do SharePoint** \> .
  
## <a name="interpreting-the-sharepoint-activity-report"></a>Interpretar o relatório de atividades do SharePoint

Você pode examinar a atividade do SharePoint nos modos de exibição de **Arquivos** e **Usuários**.<br/> ![SharePoint Activity Report](../../media/96ee85af-f213-499b-9e2b-22912bd0b8c2.png)
  
|||
|:-----|:-----|
|1.  <br/> |O relatório **Atividade do SharePoint** pode ser consultado sobre tendências dos últimos 7, 30, 90 ou 180 dias. No entanto, se você selecionar um dia específico no relatório, a tabela (7) mostrará dados de até 28 dias a partir da data atual (não a data em que o relatório foi gerado).  <br/> |
|2.  <br/> |Os dados em cada relatório normalmente cobrem até as últimas 24 a 48 horas.  <br/> |
|3.  <br/> |O modo de exibição **Arquivos** ajuda você a entender os números exclusivos de usuários licenciados que realizam as interações de arquivo com os arquivos armazenados nos sites do SharePoint.  <br/> |
|4.  <br/> |O modo de exibição **Páginas** mostra o número de páginas exclusivas visitadas pelos usuários.  <br/> |
|5.  <br/> |O modo de exibição **Usuários** ajuda você a entender a tendência no número de usuários ativos. Um usuário é considerado ativo quando executa uma atividade de arquivo (salvar, sincronizar, modificar ou compartilhar) ou visita uma página dentro do período específico.  <br/> Observação: uma atividade de arquivo pode ocorrer várias vezes para um único arquivo, mas contará somente como um arquivo ativo. Por exemplo, você pode salvar e sincronizar o mesmo arquivo várias vezes durante um período especificado, mas isso contará somente como um único arquivo ativo e um único arquivo sincronizado nos dados           |
|6.  <br/> | No gráfico **Arquivos**, o eixo Y é a contagem de arquivos exclusivos que um usuário salvou, sincronizou, modificou ou compartilhou.  <br/>  No gráfico **Usuários**, o eixo Y é o número de usuários exclusivos que executaram uma interação de arquivo (salvar, sincronizar, modificar ou compartilhar) em um site.  <br/>  No gráfico **Páginas**, o eixo X é a contagem de páginas exclusivas que os usuários visitaram.  <br/>  O eixo X em todos os gráficos é o intervalo de datas selecionado para esse relatório específico.  <br/> |
|7.  <br/> |Você pode filtrar a série que vê no gráfico selecionando um item na legenda. Por exemplo, no gráfico **arquivos** , selecione **exibido ou editado**, **sincronizado**, **compartilhado internamente**ou **compartilhado externamente** para ver apenas as informações relacionadas a cada um. Ao alterar essa seleção, as informações da tabela não mudam.  <br/> |
|8.  <br/> | A tabela mostra o detalhamento das atividades no nível do site.  <br/>  <br/> **Username** é o endereço de email do usuário que realizou a atividade no site do SharePoint.  <br/> **Data da última atividade (UTC)** é a data mais recente de execução de uma atividade de arquivo ou de visita a uma página no intervalo de datas selecionado. Para ver a atividade que ocorreu em uma data específica, selecione a data diretamente no gráfico.  <br/> ![Selecionar uma data específica no gráfico](../../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png) <br/> Isso filtrará a tabela para exibir os dados de atividade de arquivo somente para os usuários que realizaram a atividade nesse dia específico.  <br/>  **Arquivos exibidos ou editados** é o número de arquivos carregados, baixados, modificados ou exibidos pelo usuário.  <br/>  **Arquivos sincronizados** é o número de arquivos que foram sincronizados a partir do dispositivo local de um usuário para o site do SharePoint.  <br/>  **Arquivos compartilhados internamente** é a quantidade de arquivos que foram compartilhados com usuários dentro da organização ou com usuários dentro de grupos (que podem incluir usuários externos).  <br/>  **Arquivos compartilhados externamente** é a quantidade de arquivos que foram compartilhados com os usuários de fora da organização.  <br/>  **Páginas visitadas** são visitas a páginas exclusivas pelo usuário.  <br/>  **Excluída** indica que a licença do usuário foi removida.  <br/>  **Observação:** A atividade de um usuário excluído ainda será exibida no relatório, contanto que ele ou ela tenha sido licenciado em algum momento durante o período de tempo selecionado. A coluna Excluído ajuda você a observar que o usuário pode não estar mais ativo, mas contribuiu com os dados no relatório.  <br/> **Data de exclusão** é a data na qual a licença do usuário foi removida.  <br/>  **Produto atribuído** são os produtos da Microsoft 365 que são licenciados para o usuário.  <br/> |
|9.  <br/> |Selecione o ícone ![ **gerenciar colunas** gerenciar colunas](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) para adicionar ou remover colunas do relatório.  <br/> |
|10.  <br/> |Você também pode exportar os dados do relatório para um arquivo. csv do Excel selecionando o link de **exportação** . Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2.000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados.  <br/> |
|||
   

