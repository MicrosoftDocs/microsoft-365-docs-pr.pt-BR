---
title: Preservar destinatários Cco e de grupos de distribuição expandidos para Descoberta Eletrônica
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/19/2017
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: eb8ddf15-0080-457e-9d83-e73e193da334
description: In-Place retenção, retenção de litígio e políticas de retenção do Microsoft 365 permitem preservar o conteúdo da caixa de correio para atender aos requisitos regulatórios de conformidade e Descoberta Eletrônico.
ms.openlocfilehash: c864a963bec7a7d342a8ad90b6edc57c88f5205b
ms.sourcegitcommit: 490a65d32b6d656c661c36a2cc8dda03bf6cba77
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588502"
---
# <a name="preserve-bcc-and-expanded-distribution-group-recipients-for-ediscovery"></a>Preservar destinatários Cco e de grupos de distribuição expandidos para Descoberta Eletrônica
  
In-Place Retenção de In-Place, Retenção de Litígio e políticas de retenção do [Microsoft 365](https://go.microsoft.com/fwlink/?LinkID=827811) & (criadas no Centro de Conformidade e Segurança) permitem que você preserve o conteúdo da caixa de correio para atender aos requisitos regulatórios de conformidade e Descoberta Eletrônico. Informações sobre destinatários diretamente endereçados nos campos Para e Cc de uma mensagem são incluídas em todas as mensagens por padrão. Mas sua organização pode exigir a capacidade de pesquisar e reproduzir detalhes sobre todos os destinatários de uma mensagem. Isso inclui:
  
- **Destinatários endereçados usando o campo Cc de uma mensagem:** Os destinatários Cc são armazenados na mensagem na caixa de correio do remetente, mas não incluídos nos títulos da mensagem entregue aos destinatários. 
    
- **Destinatários expandidos do grupo de distribuição:** Destinatários que recebem a mensagem porque são membros de um grupo de distribuição ao qual a mensagem foi endereçada, nos campos Para, Cc ou Cc. 
    
O Exchange Online e o Exchange Server 2013 (Atualização Cumulativa 7 e versões posteriores) retêm informações sobre destinatários do grupo de distribuição Cc e expandido. Você pode pesquisar essas informações usando uma pesquisa de Descoberta In-Place no Centro de administração do Exchange (EAC) ou uma Pesquisa de Conteúdo no Centro de Conformidade e & Segurança. 
  
## <a name="how-bcc-recipients-and-expanded-distribution-group-recipients-are-preserved"></a>Como os destinatários Cc e os destinatários do grupo de distribuição expandido são preservados

Conforme indicado anteriormente, as informações sobre destinatários de Cc'ed são armazenadas com a mensagem na caixa de correio do remetente. Essas informações são indexadas e estão disponíveis para pesquisas e isenções de Descobertas e Descobertas. 
  
As informações sobre destinatários de grupos de distribuição expandidos são armazenadas com a mensagem depois que você coloca uma caixa de correio em In-Place de litígio ou de litígio. No Office 365, essas informações também são armazenadas quando uma política de retenção do Microsoft 365 é aplicada a uma caixa de correio. A associação do grupo de distribuição é determinada no momento em que a mensagem é enviada. A lista de destinatários expandida armazenada com a mensagem não é impactada pelas alterações na associação do grupo depois que a mensagem é enviada. 
  
| Informações sobre... | É armazenado em... | É armazenado por padrão? | É acessível para... |
|:-----|:-----|:-----|:-----|
|Destinatários Para e Cc  <br/> |Propriedades da mensagem nas caixas de correio do remetente e dos destinatários.  <br/> |Sim  <br/> |Remetente, destinatários e responsáveis pela conformidade  <br/> |
|Destinatários Cc  <br/> |Propriedade da mensagem na caixa de correio do remetente.  <br/> |Sim  <br/> |Remetente e responsáveis pela conformidade  <br/> |
|Destinatários expandidos do grupo de distribuição  <br/> |Propriedades da mensagem na caixa de correio do remetente.  <br/> |Não. As informações do destinatário do grupo de distribuição expandido são armazenadas depois que uma caixa de correio é colocada In-Place retenção ou retenção de litígio ou atribuída a uma política de retenção do Microsoft 365.  <br/> |Oficiais de conformidade  <br/> |
   
## <a name="searching-for-messages-sent-to-bcc-and-expanded-distribution-group-recipients"></a>Pesquisar mensagens enviadas a destinatários do grupo de distribuição Cc e expandido

Ao pesquisar por mensagens enviadas a um destinatário, os resultados da pesquisa de Descoberta e agora incluem mensagens enviadas para um grupo de distribuição do que o destinatário é membro. A tabela a seguir mostra os cenários em que as mensagens enviadas para destinatários do grupo de distribuição Cc e expandido são retornadas nas pesquisas de Descobertas e Descobertas.
  
Cenário 1: John é membro do grupo US-Sales distribuição. Esta tabela mostra os resultados da pesquisa de Descoberta eDiscovery quando Bob envia uma mensagem para John direta ou indiretamente por meio de um grupo de distribuição.
  
| Quando você pesquisa na caixa de correio de Bob por mensagens enviadas... | E a mensagem é enviada com... | Os resultados incluem mensagem? |
|:-----|:-----|:-----|
|To:John  <br/> |John on TO  <br/> |Sim  <br/> |
|To:John  <br/> |US-Sales em TO  <br/> |Sim  <br/> |
|To:US-Sales  <br/> |US-Sales em TO  <br/> |Sim  <br/> |
|Cc:John  <br/> |John no CC  <br/> |Sim  <br/> |
|Cc:John  <br/> |US-Sales no CC  <br/> |Sim  <br/> |
|Cc:US-Sales  <br/> |US-Sales no CC  <br/> |Sim  <br/> |
   
Cenário 2: Bob envia um email para John (Para/Cc) e John (Cc direta ou indiretamente por meio de um grupo de distribuição). A tabela a seguir mostra os resultados da pesquisa de Descoberta eDiscovery.
  
| Quando você pesquisa... | Para mensagens enviadas... | Os resultados incluem mensagem? | Observações |
|:-----|:-----|:-----|:-----|
|Caixa de correio de Bob  <br/> |To/Cc:John  <br/> |Sim  <br/> |Apresenta uma indicação de que o Tomada foi Cc'ed.  <br/> |
|Caixa de correio de Bob  <br/> |Bcc:Jack  <br/> |Sim  <br/> |Apresenta uma indicação de que o Tomada foi Cc'ed.  <br/> |
|Caixa de correio de Bob  <br/> |Bcc:Jack (via grupo de distribuição)  <br/> |Sim  <br/> |A lista de membros do grupo de distribuição Cc'ed, expandida quando a mensagem foi enviada, fica visível na visualização, exportação e logs de pesquisa de Descobertas e Descobertas.  <br/> |
|Caixa de correio de John  <br/> |To/Cc:John  <br/> |Sim  <br/> |Nenhuma indicação de destinatários Cc.  <br/> |
|Caixa de correio de John  <br/> |Bcc:Jack (diretamente ou por meio do grupo de distribuição)  <br/> |Não  <br/> |As informações de Cc não são armazenadas na mensagem entregue aos destinatários. Você deve pesquisar a caixa de correio do remetente.  <br/> |
|Caixa de correio de Tomada  <br/> |Para/Cc:John (diretamente ou por meio do grupo de distribuição)  <br/> |Sim  <br/> |As informações para/Cc são incluídas na mensagem entregue a todos os destinatários.  <br/> |
|Caixa de correio de Tomada  <br/> |Bcc:Jack (diretamente ou por meio do grupo de distribuição)  <br/> |Não  <br/> |As informações de Cc não são armazenadas na mensagem entregue aos destinatários. Você deve pesquisar a caixa de correio do remetente.  <br/> |
   
## <a name="frequently-asked-questions"></a>Perguntas frequentes

 **P. Quando e onde as informações de destinatário Cc são armazenadas?**
  
R. As informações de destinatário Cc são preservadas por padrão na mensagem original na caixa de correio do remetente. Se o destinatário Cc for um grupo de distribuição, a associação do grupo de distribuição só será expandida se a caixa de correio do remetente estiver em espera ou atribuída a uma política de retenção do Microsoft 365.
  
 **P. Quando e onde a lista de destinatários do grupo de distribuição expandida é armazenada?**
  
R. A associação ao grupo é expandida no momento em que a mensagem é enviada. A lista de membros do grupo de distribuição expandido é armazenada na mensagem original na caixa de correio do remetente. A caixa de correio do remetente deve estar em In-Place retenção, retenção de litígio ou atribuída a uma política de retenção do Microsoft 365.
  
 **P. Os destinatários Para/Cc podem ver quais destinatários foram Cc'ed?**
  
R. Não. Essas informações não estão incluídas nos headers de mensagem e não estão visíveis para destinatários Para/Cc. O remetente pode ver o campo Cc armazenado na mensagem original armazenada em sua caixa de correio. Os agentes de conformidade podem ver essas informações ao pesquisar na caixa de correio do remetente.
  
 **P. Como posso garantir que os destinatários do grupo de distribuição expandido sejam sempre preservados?**
  
R. Para garantir que os membros do grupo de distribuição expandido sejam sempre preservados com uma [mensagem,](https://technet.microsoft.com/library/4c141604-3210-44cc-b98e-f3e0f15613b8.aspx) coloque todas as caixas de correio em espera ou crie uma política de retenção do Microsoft 365 em toda a organização. 
  
 **P. Quais tipos de grupos são suportados?**
  
R. Grupos de distribuição, grupos de segurança habilitados para email e grupos dinâmicos de distribuição são suportados. 
  
 **P. Há um limite no número de destinatários do grupo de distribuição que são expandidos e armazenados na mensagem?**
  
R. Até 10.000 membros de um grupo de distribuição são preservados.
  
 **P. Há suporte para grupos de distribuição aninhados?**
  
R. Sim, 25 níveis de grupos de distribuição aninhados são expandidos.
  
 **P. Onde as informações do destinatário do grupo de distribuição Cc e expandido estão visíveis?**
  
R. As informações de destinatários do grupo de distribuição Cc e expandido são visíveis para os responsáveis pela conformidade ao realizar uma pesquisa de Descoberta eDiscovery. Os destinatários do grupo de distribuição Cc e expandido são incluídos nos resultados da pesquisa copiados para uma caixa de correio de Descoberta ou exportados para um arquivo PST e no log de Descoberta Eletrônico incluído nos resultados da pesquisa. As informações de destinatário Cc também estão disponíveis na visualização de pesquisa.
  
 **P. O que acontece se um membro de um grupo de distribuição estiver oculto da GAL (lista de endereços global) da organização?**
  
R. Não há impacto. Se os destinatários estão ocultos da GAL, eles ainda são incluídos na lista de destinatários do grupo de distribuição expandido.
