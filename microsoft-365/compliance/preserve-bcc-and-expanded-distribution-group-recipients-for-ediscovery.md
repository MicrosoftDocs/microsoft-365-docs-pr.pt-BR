---
title: Preservar destinatários Cco e de grupos de distribuição expandidos para Descoberta Eletrônica
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/19/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: eb8ddf15-0080-457e-9d83-e73e193da334
description: Bloqueio in-loco, retenção de litígio e políticas de retenção do Microsoft 365 permitem preservar o conteúdo da caixa de correio para atender aos requisitos de conformidade normativa e eDiscovery.
ms.openlocfilehash: 07959edc89aa9d3335b9af501743eae4a11a6aa1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634859"
---
# <a name="preserve-bcc-and-expanded-distribution-group-recipients-for-ediscovery"></a>Preservar destinatários Cco e de grupos de distribuição expandidos para Descoberta Eletrônica
  
Bloqueio in-loco, retenção de litígio e [políticas de retenção do Microsoft 365](https://go.microsoft.com/fwlink/?LinkID=827811) (criadas no centro de conformidade & segurança) permitem preservar o conteúdo da caixa de correio para atender aos requisitos de conformidade normativa e eDiscovery. As informações sobre os destinatários endereçados diretamente nos campos para e CC de uma mensagem são incluídas em todas as mensagens por padrão, mas sua organização pode exigir a capacidade de Pesquisar e reproduzir detalhes sobre todos os destinatários de uma mensagem. Isso inclui: 
  
- **Destinatários endereçados usando o campo Cco de uma mensagem:** Os destinatários Cco são armazenados na mensagem da caixa de correio do remetente, mas não estão incluídos nos cabeçalhos da mensagem entregue aos destinatários. 
    
- **Destinatários de grupos de distribuição expandidos:** Destinatários que recebem a mensagem porque são membros de um grupo de distribuição para o qual a mensagem foi tratada, nos campos para, CC ou Cco. 
    
Exchange Online e Exchange Server 2013 (atualização cumulativa 7 e versões posteriores) retêm informações sobre Cco e destinatários expandidos do grupo de distribuição. Você pode pesquisar essas informações usando uma pesquisa de descoberta eletrônica in-loco no centro de administração do Exchange (Eat) ou uma pesquisa de conteúdo no centro de conformidade de & de segurança. 
  
## <a name="how-bcc-recipients-and-expanded-distribution-group-recipients-are-preserved"></a>Como os destinatários Cco e os destinatários de grupos de distribuição expandidos são preservados

Conforme mencionado anteriormente, as informações sobre os destinatários do estava são armazenadas com a mensagem na caixa de correio do remetente. Essas informações são indexadas e disponibilizadas para pesquisas e isenções de descoberta eletrônica. 
  
As informações sobre destinatários expandidos do grupo de distribuição são armazenadas com a mensagem após você colocar uma caixa de correio em bloqueio in-loco ou retenção de litígio. No Office 365, essas informações também são armazenadas quando uma política de retenção da Microsoft 365 é aplicada a uma caixa de correio. A associação do grupo de distribuição é determinada no momento em que a mensagem é enviada. A lista de destinatários expandidos armazenada com a mensagem não é afetada por alterações na associação do grupo depois que a mensagem é enviada. 
  
|**Informações sobre...**|**É armazenado em...**|**É armazenado por padrão?**|**Está acessível para...**|
|:-----|:-----|:-----|:-----|
|Destinatários para e CC  <br/> |Propriedades da mensagem nas caixas de correio do remetente e dos destinatários.  <br/> |Sim  <br/> |Remetente, destinatários e gerentes de conformidade  <br/> |
|Destinatários Cco  <br/> |Propriedade Message na caixa de correio do remetente.  <br/> |Sim  <br/> |Órgãos de remetente e conformidade  <br/> |
|Destinatários de grupos de distribuição expandidos  <br/> |Propriedades da mensagem na caixa de correio do remetente.  <br/> |Não. As informações de destinatário do grupo de distribuição expandido são armazenadas depois que uma caixa de correio é colocada em bloqueio in-loco ou retenção de litígio, ou atribuída a uma política de retenção do Microsoft 365.  <br/> |Oficiais de conformidade  <br/> |
   
## <a name="searching-for-messages-sent-to-bcc-and-expanded-distribution-group-recipients"></a>Pesquisando mensagens enviadas para destinatários Cco e de grupo de distribuição expandido

Ao pesquisar mensagens enviadas a um destinatário, os resultados da pesquisa de descoberta eletrônica agora incluem mensagens enviadas a um grupo de distribuição do qual o destinatário é membro. A tabela a seguir mostra os cenários em que as mensagens enviadas para os destinatários de grupo de distribuição Cco e expandido são retornadas nas pesquisas de descoberta eletrônica.
  
Cenário 1: John é um membro do grupo de distribuição US-Sales. Esta tabela mostra os resultados da pesquisa de descoberta eletrônica quando Bob envia uma mensagem para John direta ou indiretamente por meio de um grupo de distribuição.
  
|**Quando você pesquisa a caixa de correio de Bob para mensagens enviadas...**|**E a mensagem é enviada com...**|**Os resultados incluem a mensagem?**|
|:-----|:-----|:-----|
|Para: João  <br/> |John no a  <br/> |Sim  <br/> |
|Para: João  <br/> |US-vendas para o  <br/> |Sim  <br/> |
|Para: US-vendas  <br/> |US-vendas para o  <br/> |Sim  <br/> |
|CC: John  <br/> |John no CC  <br/> |Sim  <br/> |
|CC: John  <br/> |US-vendas no CC  <br/> |Sim  <br/> |
|CC: US-vendas  <br/> |US-vendas no CC  <br/> |Sim  <br/> |
   
Cenário 2: Bob envia um email para John (para/CC) e Jack (Cco diretamente ou indiretamente por meio de um grupo de distribuição). A tabela abaixo mostra os resultados da pesquisa de descoberta eletrônica.
  
|**Quando você pesquisa...**|**Para mensagens enviadas...**|**Os resultados incluem a mensagem?**|**Anotações**|
|:-----|:-----|:-----|:-----|
|Caixa de correio de Bob  <br/> |Para/CC: João  <br/> |Sim  <br/> |Apresenta uma indicação de que o Jack foi estava.  <br/> |
|Caixa de correio de Bob  <br/> |CCO: Jack  <br/> |Sim  <br/> |Apresenta uma indicação de que o Jack foi estava.  <br/> |
|Caixa de correio de Bob  <br/> |BCC: Jack (via grupo de distribuição)  <br/> |Sim  <br/> |Lista de membros do grupo de distribuição estava, expandida quando a mensagem foi enviada, está visível em visualização, exportação e logs da pesquisa de descoberta eletrônica.  <br/> |
|Caixa de correio de John  <br/> |Para/CC: João  <br/> |Sim  <br/> |Nenhuma indicação de destinatários Cco.  <br/> |
|Caixa de correio de John  <br/> |BCC: Jack (diretamente ou via grupo de distribuição)  <br/> |Não  <br/> |As informações de Cco não são armazenadas na mensagem entregue aos destinatários. Você deve pesquisar a caixa de correio do remetente.  <br/> |
|Caixa de correio da tomada  <br/> |Para/CC: João (diretamente ou via grupo de distribuição)  <br/> |Sim  <br/> |As informações para/CC estão incluídas na mensagem entregue a todos os destinatários.  <br/> |
|Caixa de correio da tomada  <br/> |BCC: Jack (diretamente ou via grupo de distribuição)  <br/> |Não  <br/> |As informações de Cco não são armazenadas na mensagem entregue aos destinatários. Você deve pesquisar a caixa de correio do remetente.  <br/> |
   
## <a name="frequently-asked-questions"></a>Perguntas frequentes

 **P. quando e onde as informações de destinatário Cco são armazenadas?**
  
R. As informações de destinatário Cco são preservadas por padrão na mensagem original na caixa de correio do remetente. Se o destinatário Cco for um grupo de distribuição, a associação de grupo de distribuição só será expandida se a caixa de correio do remetente estiver em espera ou atribuída a uma política de retenção do Microsoft 365.
  
 **P. quando e onde a lista de destinatários de grupos de distribuição expandidos está armazenada?**
  
R. A associação de grupo é expandida no momento em que a mensagem é enviada. A lista de membros do grupo de distribuição expandida é armazenada na mensagem original na caixa de correio do remetente. A caixa de correio do remetente deve estar em bloqueio in-loco, retenção de litígio ou atribuído a uma política de retenção do Microsoft 365.
  
 **P. os destinatários para/CC podem ver quais destinatários foram estava?**
  
R. Não. Essas informações não estão incluídas em cabeçalhos de mensagem e não são visíveis para destinatários para/CC. O remetente pode ver o campo Cco armazenado na mensagem original armazenada na caixa de correio. Os gerentes de conformidade podem ver essas informações ao pesquisar a caixa de correio do remetente.
  
 **P. como garantir que os destinatários de grupos de distribuição expandidos sejam sempre preservados?**
  
R. Para garantir que os membros do grupo de distribuição expandido sejam sempre preservados com uma mensagem, [Coloque todas as caixas de correio em espera](https://technet.microsoft.com/library/4c141604-3210-44cc-b98e-f3e0f15613b8.aspx) ou crie uma política de retenção do Microsoft 365 em toda a organização. 
  
 **P. para quais tipos de grupos há suporte?**
  
R. Há suporte para grupos de distribuição, grupos de segurança habilitados para email e grupos de distribuição dinâmicos. 
  
 **P. há um limite no número de destinatários do grupo de distribuição que são expandidos e armazenados na mensagem?**
  
R. Até 10.000 membros de um grupo de distribuição é preservado.
  
 **P. há suporte para grupos de distribuição aninhados?**
  
R. Sim, 25 níveis de grupos de distribuição aninhados são expandidos.
  
 **P. onde as informações de destinatário do grupo de distribuição Cco e expandidas estão visíveis?**
  
R. As informações de destinatários de grupos de distribuição Cco e expandidas são visíveis aos responsáveis pela conformidade ao realizar uma pesquisa de descoberta eletrônica. Os destinatários de grupos de distribuição Cco e expandidos são incluídos nos resultados de pesquisa copiados para uma caixa de correio de descoberta ou exportados para um arquivo PST e no log de descoberta eletrônica incluído nos resultados da pesquisa. As informações de destinatário Cco também estão disponíveis na visualização de pesquisa.
  
 **P. o que acontece se um membro de um grupo de distribuição estiver oculto da GAL (lista de endereços global) da organização?**
  
R. Não há impacto. Se os destinatários estiverem ocultos da GAL, eles ainda serão incluídos na lista de destinatários para o grupo de distribuição expandido.
