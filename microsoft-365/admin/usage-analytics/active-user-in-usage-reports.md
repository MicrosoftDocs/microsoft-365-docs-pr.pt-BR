---
title: Usuário ativo nos relatórios de uso do Microsoft 365
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: Saiba mais sobre um usuário ativo da análise de uso do Microsoft 365, relatórios de atividades e métricas de adoção.
ms.openlocfilehash: 0e2f5f5112593c142b4a7829977221c5542adf49
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237649"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Usuário ativo nos relatórios de uso do Microsoft 365

## <a name="active-user-in-usage-reports"></a>Usuário ativo em relatórios de uso

Um usuário ativo de produtos do Microsoft 365 para [análise de uso do microsoft 365](usage-analytics.md) e os [relatórios de atividades no centro de administração](../activity-reports/activity-reports.md) são definidos da seguinte maneira. 
  
|**Produto**|**Definição de um usuário ativo**|**Observações**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |Qualquer usuário que tenha lido ou enviado um email.  <br/> |Nenhuma informação do calendário é representada, isso será adicionado em uma próxima atualização.  <br/> |
|SharePoint Online  <br/> |Qualquer usuário que tenha interagido com um arquivo ao criar, modificar, visualizar, excluir, compartilhar interna ou externamente ou sincronizar para clientes em qualquer site ou que tenha visualizado uma página em qualquer site.  <br/> |A métrica de usuário ativa para o SharePoint Online no aplicativo de modelo de análise de uso do Microsoft 365 reflete apenas os usuários que fizeram atividade de arquivo em um site de equipe do SharePoint ou em um site de grupo. O aplicativo de modelo será atualizado para sincronizar a definição para o mesmo que nos relatórios de uso no centro de administração.  <br/> |
|OneDrive for Business  <br/> |Qualquer usuário que tenha interagido com um arquivo ao criar, modificar, visualizar, excluir, compartilhar interna ou externamente ou sincronizar para clientes.  <br/> ||
|Yammer  <br/> |Qualquer usuário que tenha lido, postado ou curtido uma mensagem no Yammer.  <br/> ||
|Skype for Business  <br/> |Qualquer usuário que tenha participado de uma sessão ponto a ponto (incluindo mensagens instantâneas, chamadas de áudio e vídeo, compartilhamento de aplicativos e transferências de arquivos) ou que organizou ou participou de uma conferência.  <br/> ||
|Office  <br/> |Qualquer usuário que ativou sua assinatura do Microsoft 365 Pro Plus, Visio pro ou Project pro em pelo menos um dispositivo.  <br/> ||
|Grupos do Microsoft 365  <br/> |Qualquer membro do grupo que tenha atividade da caixa de correio (se uma mensagem foi enviada para o grupo)  <br/> |Essa definição será aprimorada com atividade de arquivo de site de grupo e atividade de grupo do Yammer (atividade de arquivo no site de grupo e mensagens postadas no grupo do Yammer associadas ao grupo). Estes dados atualmente não estão disponíveis no aplicativo de modelo de análise de uso do Microsoft 365  <br/> |
|Microsoft Teams  <br/> |Qualquer usuário que participou de mensagens de chat, mensagens de chat privadas, chamadas, reuniões ou outras atividades. Outra atividade é definida como o número de outras atividades da equipe pelo usuário, algumas das quais incluem, e não estão limitadas a: preferência de mensagens, aplicativos, trabalho em arquivos, pesquisa, seguindo equipes e canal e favoriting-los.  <br/> ||
   
## <a name="adoption-metrics"></a>Métricas de adoção

A [análise de uso do Microsoft 365](usage-analytics.md) contém métricas adicionais de adoção relacionadas a usuários ativos para mostrar a adoção dos produtos com o passar do tempo. Essas métricas são válidas para o mês, ano e produto selecionado e são definidas da seguinte maneira. 
  
|**Indicador**|**Descrição**|
|:-----|:-----|
|EnabledUsers  <br/> |Número de usuários habilitados para usar o produto no mês.  <br/> |
|ActiveUsers  <br/> |Número de usuários ativos no mês.  <br/> |
|MoMReturningUsers  <br/> |Número de usuários ativos no mês que também estavam ativos no mês anterior.  <br/> |
|FirstTimeUsers  <br/> |Número de usuários ativos no mês em que o nunca usou o serviço antes.  <br/> |
|CumulativeActiveUsers  <br/> |Número de usuários ativos no mês mais qualquer mês anterior.  <br/> |
|ActiveUsers (%)  <br/> |Porcentagem de usuários, arredondados para o décimo mais próximo, ativo no mês, em comparação com o número de usuários habilitados nesse mês.  <br/> |
|MoMReturningUsers (%)  <br/> |Porcentagem de usuários, arredondados para o décimo mais próximo, ativo no mês que também estava ativo no mês anterior, em comparação com o número de usuários ativos.  <br/> |
   
MoMReturningUsers, FirstTimeUsers, &amp; CumulativeActiveUsers foram redefinidos começando no dia 1º de janeiro de 2018 com a inclusão do Microsoft Teams.
  
