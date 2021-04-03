---
title: Usuário ativo nos relatórios de uso do Microsoft 365
ms.author: efrene
author: efrene
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
ms.openlocfilehash: 21663722d1a3850389db2ad79321daf363d314c6
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579069"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Usuário ativo nos relatórios de uso do Microsoft 365

## <a name="active-user-in-usage-reports"></a>Usuário ativo em relatórios de uso

Um usuário ativo dos produtos microsoft 365 para análise de uso do [Microsoft 365](usage-analytics.md) e os Relatórios de Atividades no centro de administração [é](../activity-reports/activity-reports.md) definido da seguinte forma. 
  
|**Produto**|**Definição de um usuário ativo**|**Observações**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |Qualquer usuário que tenha executado qualquer uma das seguintes ações: Marcar como leitura, enviar mensagens, criar compromissos, enviar solicitações de reunião, aceitar (como provisão) ou recusar solicitações de reunião, cancelar reuniões.  <br/> |Nenhuma informação do calendário é representada, isso será adicionado em uma próxima atualização.  <br/> |
|SharePoint Online  <br/> |Qualquer usuário que tenha interagido com um arquivo ao criar, modificar, visualizar, excluir, compartilhar interna ou externamente ou sincronizar para clientes em qualquer site ou que tenha visualizado uma página em qualquer site.  <br/> |A métrica de usuário ativa do SharePoint Online no aplicativo de modelo de Análise de Uso do Microsoft 365 só reflete os usuários que fizeram atividade de arquivo em um site da Equipe do SharePoint ou em um site de Grupo. O aplicativo de modelo será atualizado para sincronizar a definição com a mesma que nos relatórios de uso no centro de administração.  <br/> |
|OneDrive for Business  <br/> |Qualquer usuário que tenha interagido com um arquivo ao criar, modificar, visualizar, excluir, compartilhar interna ou externamente ou sincronizar para clientes.  <br/> ||
|Yammer  <br/> |Qualquer usuário que tenha lido, postado ou curtido uma mensagem no Yammer.  <br/> ||
|Skype for Business  <br/> |Qualquer usuário que tenha participado de uma sessão ponto a ponto (incluindo mensagens instantâneas, chamadas de áudio e vídeo, compartilhamento de aplicativos e transferências de arquivos) ou que organizou ou participou de uma conferência.  <br/> ||
|Office  <br/> |Qualquer usuário que tenha ativado sua assinatura do Microsoft 365 Pro Plus, Visio Pro ou Project Pro em pelo menos um dispositivo.  <br/> ||
|Grupos do Microsoft 365  <br/> |Qualquer membro do grupo que tenha atividade da caixa de correio (se uma mensagem foi enviada para o grupo)  <br/> |Essa definição será aprimorada com a atividade de arquivo de site de grupo e atividade de grupo do Yammer (atividade de arquivo no site do grupo e mensagem postada no grupo do Yammer associada ao grupo).) Esses dados não estão disponíveis no aplicativo de modelo análise de uso do Microsoft 365  <br/> |
|Microsoft Teams  <br/> |Qualquer usuário que tenha participado de mensagens de chat, mensagens de chat privadas, chamadas, reuniões ou outras atividades. Outras atividades são definidas como o número de outras atividades de equipe pelo usuário, algumas das quais incluem e não se limitam a: gostar de mensagens, aplicativos, trabalhar em arquivos, pesquisar, acompanhar equipes e canal e favoreça-los.  <br/> ||
   
## <a name="adoption-metrics"></a>Métricas de Adoção

A análise de uso do [Microsoft 365](usage-analytics.md) contém métricas de adoção adicionais relacionadas a usuários ativos para mostrar a adoção dos produtos ao longo do tempo. Essas métricas são válidas para o mês, ano e produto selecionado e são definidas da seguinte forma. 
  
|**Indicador**|**Descrição**|
|:-----|:-----|
|EnabledUsers  <br/> |Número de usuários habilitados para usar o produto no mês.  <br/> |
|ActiveUsers  <br/> |Número de usuários ativos no mês.  <br/> |
|MoMReturningUsers  <br/> |Número de usuários ativos no mês que também estavam ativos no mês anterior.  <br/> |
|FirstTimeUsers  <br/> |Número de usuários ativos no mês que nunca tinham usado o serviço antes.  <br/> |
|CumulativeActiveUsers  <br/> |Número de usuários ativos no mês mais qualquer mês anterior.  <br/> |
|ActiveUsers(%)  <br/> |Porcentagem de usuários, arredondado para o décimo mais próximo, ativo no mês em comparação com o número de usuários habilitados nesse mês.  <br/> |
|MoMReturningUsers(%)  <br/> |Porcentagem de usuários, arredondado para o décimo mais próximo, ativo no mês que também estava ativo no mês anterior em comparação com o número de usuários ativos.  <br/> |
   
MoMReturningUsers, FirstTimeUsers, CumulativeActiveUsers foram redefinidos a partir de 1º de janeiro de 2018 com a inclusão &amp; do Microsoft Teams.
  
