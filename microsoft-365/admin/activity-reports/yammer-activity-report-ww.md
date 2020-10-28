---
title: Relatórios do Microsoft 365 no centro de administração-relatório de atividades do Yammer
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
description: Obtenha o relatório de atividades do Yammer e saiba mais sobre o número de usuários que usam o Yammer para postar, como ou ler uma mensagem.
ms.openlocfilehash: fc6bf252892cc9b3f30cdcf464cd44cfc83c4f75
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779287"
---
# <a name="microsoft-365-reports-in-the-admin-center---yammer-activity-report"></a>Relatórios do Microsoft 365 no centro de administração-relatório de atividades do Yammer

Como o Microsoft 365 admin, o painel **relatórios** mostra dados sobre o uso dos produtos dentro da sua organização. Confira [os relatórios de atividade no centro de administração](activity-reports.md). Com o **Relatório de atividades do Yammer** , você vai entender o nível de interação da sua organização com o Yammer examinando o número de usuários exclusivos usando o Yammer para postar, curtir ou ler uma mensagem e a quantidade de atividade gerada em toda a organização. 
  
> [!NOTE]
> Você deve ser um administrador global, um leitor global ou um leitor de relatórios no Microsoft 365 ou um administrador do Exchange, do SharePoint, do teams ou do Skype for Business para ver os relatórios.  
 
## <a name="how-do-i-get-to-the-yammer-activity-report"></a>Como obter o relatório de atividades do Yammer?

1. No centro de administração do, vá para a página **Relatórios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Uso</a>. 
2. Na página inicial do painel, clique no botão **Exibir mais** no cartão do Yammer.

  
## <a name="interpret-the-yammer-activity-report"></a>Interpretar o relatório de atividades do Yammer

Você pode exibir as atividades no relatório do Yammer escolhendo a guia **atividade** .<br/>![Relatórios da Microsoft 365-relatório de atividades do Microsoft Yammer.](../../media/9b251183-c2b3-430c-ab2d-58bf11e7e3ae.png)

Selecione **escolher colunas** para adicionar ou remover colunas do relatório.  <br/> ![Relatório de atividades do Yammer-escolher colunas](../../media/7ef6351d-f7e9-4504-913d-2c2df9062bf6.png)

Você também pode exportar os dados do relatório para um arquivo. csv do Excel selecionando o link de **exportação** . Isso exporta os dados de todos os usuários e permite que você realize uma classificação e filtragem simples para mais análise. Se você tiver menos de 2000 usuários, poderá classificar e filtrar dentro da tabela no próprio relatório. Se você tiver mais de 2000 usuários, para filtrar e classificar, você precisa exportar os dados. 
  
|Item|Descrição|
|:-----|:-----|
|**Indicador**|**Definição**|
|Nome de usuário  <br/> |O endereço de email do usuário. Você pode exibir o endereço de email real ou tornar este campo anônimo. Esta grade mostra os usuários que fizeram logon no Yammer usando a conta do Microsoft 365 ou que fizeram logon na rede usando o single sign-on. <br/> |
|Nome de exibição  <br/> |O nome completo do usuário. Você pode exibir o endereço de email real ou tornar este campo anônimo.  <br/> |
|Estado do usuário  <br/> |Um dos três valores: Activated, Deleted ou Suspended. Esses relatórios mostram os dados de usuários ativos, suspensos e excluídos. Eles não refletem os usuários pendentes, pois os usuários pendentes não podem publicar, ler ou curtir uma mensagem.  <br/> |
|Data de alteração de estado (UTC)  <br/> |A data em que o estado do usuário foi alterado no Yammer.  <br/> |
|Data da última atividade (UTC)  <br/> | A última data em que o usuário postou, leu ou gostou de uma mensagem.  <br/> |
|Postados  <br/> |O número de mensagens que o usuário postou durante o período de tempo especificado. <br/>|
|Leitura  <br/> |O número de conversas que o usuário leu durante o período de tempo especificado.  <br/> |
|Curtidos  <br/> |O número de mensagens que o usuário gostou durante o período de tempo especificado.  <br/>|
|Produto atribuído  <br/> |Os produtos atribuídos a esse usuário.|
|||