---
title: Relatórios do Microsoft 365 no centro de administração-Microsoft 365 grupos
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: Obtenha um relatório do Microsoft 365 groups para saber mais sobre os grupos e suas atividades.
ms.openlocfilehash: 4a89f09f89e399905d0cb6927eca76c1242dfc62
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611862"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>Relatórios do Microsoft 365 no centro de administração-Microsoft 365 grupos

O painel de **relatórios** do Microsoft 365 mostra a visão geral das atividades em todos os produtos de sua organização. Ele possibilita detalhar até relatórios de um produto específico para que você tenha informações mais precisas sobre as atividades em cada produto. Confira o tópico [Visão geral de relatórios](activity-reports.md). No relatório de grupos do Microsoft 365, você pode obter informações sobre a atividade dos grupos em sua organização e ver quantos grupos estão sendo criados e usados.
  
> [!NOTE]
> Você deve ser um administrador global, um leitor global ou um leitor de relatórios no Microsoft 365 ou um administrador do Exchange, do SharePoint, do teams ou do Skype for Business para ver os relatórios.  
  
## <a name="how-to-get-to-the-groups-report"></a>Como obter o relatório de grupos

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>. 
2. Na página inicial do painel, clique no botão **Exibir mais** nos usuários ativos-Microsoft 365 Apps ou no Active Users-Microsoft 365 Services Card para acessar a página de relatório do Office 365.
  
## <a name="interpret-the-groups-report"></a>Interpretar o relatório de grupos

Você pode exibir as ativações no relatório do Office 365 escolhendo a guia **atividade de grupos** .<br/>![Relatórios da Microsoft 365-atividade de grupos do Microsoft Office 365.](../../media/ab90e30b-8938-4110-ab3d-ee472a4cfe21.png)

Selecione **escolher colunas** para adicionar ou remover colunas do relatório.  <br/> ![Relatório de atividades de grupos do Office 365-escolher colunas](../../media/1600556a-f5f1-47d9-b325-cd77c78f4004.png)

Você também pode exportar os dados do relatório para um arquivo. csv do Excel selecionando o link de **exportação** . Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados. 

|Item|Descrição|
|:-----|:-----|
|**Indicador**|**Definição**|
|Nome do grupo  <br/> |O nome do grupo.  <br/> |
|Deleted  <br/> |O número de grupos excluídos. Se o grupo for excluído, mas tiver atividades no período do relatório, elas serão exibidas na grade com esse sinalizador definido como true.  <br/> |
|Proprietário do grupo  <br/> |O nome do proprietário do grupo.  <br/> |
|Data da última atividade (UTC)  <br/> |A última data em que uma mensagem foi recebida pelo grupo. Esta é a última data em que uma atividade aconteceu em uma conversa por email, Yammer ou Site.  <br/> |
|Tipo  <br/> |O tipo de grupo. Pode ser um grupo público ou particular.  <br/> |
|Emails recebidos no Exchange  <br/> |O número de mensagens recebidas pelo grupo.|
|Emails no Exchange (total)  <br/> |O número total de itens na caixa de correio do grupo.  <br/> |
|Armazenamento de caixa de correio usado para o Exchange (MB)  <br/> |O armazenamento usado pela caixa de correio do grupo. <br/>|
|Arquivos do SharePoint (total)  <br/> |O número de arquivos armazenados nos sites de grupo do SharePoint.  <br/> |
|Arquivos do SharePoint (ativo)  <br/> |O número de arquivos no site de grupo do SharePoint que foram acionados (exibidos ou modificados, sincronizados, compartilhados internamente ou externamente) durante o período do relatório.  <br/> |
|Total de armazenamento do site usado para o SharePoint (MB)  <br/> |O volume de armazenamento em MB usado durante o período do relatório.  <br/> |
|Mensagens no Yammer (postadas)  <br/> |O número de mensagens postadas no grupo do Yammer durante o período do relatório.  <br/> |
|Mensagens no Yammer (leitura)  <br/> |O número de conversas lidas no grupo do Yammer durante o período do relatório.  <br/> |
|Mensagens no Yammer (curtidas)  <br/> |O número de mensagens curtidas no grupo do Yammer durante o período do relatório.  <br/> |
|Members  <br/> |O número de membros no grupo.  <br/> |
|Membros externos |O número de usuários externos no grupo.|
|||