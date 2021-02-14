---
title: Usuário ativo nos relatórios de uso do Microsoft 365
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
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: Saiba mais sobre um usuário ativo da análise de uso do Microsoft 365, relatórios de atividades e métricas de adoção.
ms.openlocfilehash: b4834d96b2f762d77f0d27309cf8c71a782b0dcd
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402877"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Usuário ativo nos relatórios de uso do Microsoft 365

## <a name="active-user-in-usage-reports"></a>Usuário ativo em relatórios de uso

Um usuário ativo dos produtos Microsoft 365 para análise [](../activity-reports/activity-reports.md) de uso do [Microsoft 365](usage-analytics.md) e os Relatórios de Atividades no centro de administração é definido da seguinte forma. 
  
|**Produto**|**Definição de um usuário ativo**|**Observações**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |Qualquer usuário que tenha lido ou enviado um email.  <br/> |Nenhuma informação do calendário é representada, isso será adicionado em uma próxima atualização.  <br/> |
|SharePoint Online  <br/> |Qualquer usuário que tenha interagido com um arquivo ao criar, modificar, visualizar, excluir, compartilhar interna ou externamente ou sincronizar para clientes em qualquer site ou que tenha visualizado uma página em qualquer site.  <br/> |A métrica de usuário ativa para o SharePoint Online no aplicativo de modelo de Análise de Uso do Microsoft 365 só reflete os usuários que fizeram atividade de arquivo em um site de equipe do SharePoint ou em um site de grupo. O aplicativo de modelo será atualizado para sincronizar a definição com a mesma dos relatórios de uso no centro de administração.  <br/> |
|OneDrive for Business  <br/> |Qualquer usuário que tenha interagido com um arquivo ao criar, modificar, visualizar, excluir, compartilhar interna ou externamente ou sincronizar para clientes.  <br/> ||
|Yammer  <br/> |Qualquer usuário que tenha lido, postado ou curtido uma mensagem no Yammer.  <br/> ||
|Skype for Business  <br/> |Qualquer usuário que tenha participado de uma sessão ponto a ponto (incluindo mensagens instantâneas, chamadas de áudio e vídeo, compartilhamento de aplicativos e transferências de arquivos) ou que organizou ou participou de uma conferência.  <br/> ||
|Office  <br/> |Qualquer usuário que tenha ativado sua assinatura do Microsoft 365 Pro Plus, Visio Pro ou Project Pro em pelo menos um dispositivo.  <br/> ||
|Grupos do Microsoft 365  <br/> |Qualquer membro do grupo que tenha atividade da caixa de correio (se uma mensagem foi enviada para o grupo)  <br/> |Essa definição será aprimorada com a atividade do arquivo de site de grupo e a atividade de grupo do Yammer (atividade de arquivo no site do grupo e mensagem postada no grupo do Yammer associado ao grupo). No momento, esses dados não estão disponíveis no aplicativo de modelo análise de uso do Microsoft 365  <br/> |
|Microsoft Teams  <br/> |Qualquer usuário que tenha participado de mensagens de chat, mensagens de chat privadas, chamadas, reuniões ou outras atividades. Outras atividades são definidas como o número de outras atividades da equipe pelo usuário, algumas das quais incluem, e não se limitam a: curtir mensagens, aplicativos, trabalhar em arquivos, pesquisar, seguir equipes e canal e favoritá-las.  <br/> ||
   
## <a name="adoption-metrics"></a>Métricas de adoção

A análise de uso do [Microsoft 365](usage-analytics.md) contém métricas adicionais de adoção relacionadas aos usuários ativos para mostrar a adoção dos produtos ao longo do tempo. Essas métricas são válidas para o mês, ano e produto selecionado e são definidas da seguinte forma. 
  
|**Indicador**|**Descrição**|
|:-----|:-----|
|EnabledUsers  <br/> |Número de usuários habilitados para usar o produto no mês.  <br/> |
|ActiveUsers  <br/> |Número de usuários ativos no mês.  <br/> |
|MoMReturningUsers  <br/> |Número de usuários ativos no mês que também estavam ativos no mês anterior.  <br/> |
|FirstTimeUsers  <br/> |Número de usuários ativos no mês que nunca usaram o serviço antes.  <br/> |
|CumulativeActiveUsers  <br/> |Número de usuários ativos no mês mais qualquer mês anterior.  <br/> |
|ActiveUsers(%)  <br/> |Porcentagem de usuários, arredondado para o décimo mais próximo, ativo no mês em comparação com o número de usuários habilitados nesse mês.  <br/> |
|MoMReturningUsers(%)  <br/> |Porcentagem de usuários, arredondado para o décimo mais próximo, ativo no mês que também estavam ativos no mês anterior em comparação com o número de usuários ativos.  <br/> |
   
MoMReturningUsers, FirstTimeUsers, CumulativeActiveUsers foram redefinidos a partir de 1º de janeiro de 2018 com a inclusão do &amp; Microsoft Teams.
  
