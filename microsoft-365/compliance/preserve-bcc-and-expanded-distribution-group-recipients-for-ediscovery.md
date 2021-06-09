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
description: In-Place de retenção, retenção de litígio e Microsoft 365 de retenção permitem que você preserve o conteúdo da caixa de correio para atender aos requisitos de conformidade regulamentar e Descoberta Eletrônico.
ms.openlocfilehash: f00ed951fb68778b9c62ae874c2cca964bd6cb5c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927937"
---
# <a name="preserve-bcc-and-expanded-distribution-group-recipients-for-ediscovery"></a>Preservar destinatários Cco e de grupos de distribuição expandidos para Descoberta Eletrônica
  
In-Place de retenção, retenção de litígio e Microsoft 365 de retenção (criadas no Centro de Conformidade de Segurança &) permitem que você preserve o conteúdo da caixa de correio para atender [aos](./retention.md) requisitos de conformidade regulamentar e Descoberta Eletrônico. As informações sobre destinatários diretamente endereçadas nos campos Para e Cc de uma mensagem são incluídas em todas as mensagens por padrão. Mas sua organização pode exigir a capacidade de pesquisar e reproduzir detalhes sobre todos os destinatários de uma mensagem. Isso inclui:
  
- **Destinatários endereçados usando o campo Cc de uma mensagem:** Os destinatários Cc são armazenados na mensagem na caixa de correio do remetente, mas não incluídos nos headers da mensagem entregue aos destinatários. 
    
- **Destinatários do grupo de distribuição expandido:** Destinatários que recebem a mensagem porque são membros de um grupo de distribuição ao qual a mensagem foi endereçada, nos campos Para, Cc ou Cc. 
    
Exchange Online e Exchange Server 2013 (Atualização Cumulativa 7 e versões posteriores) retêm informações sobre destinatários do grupo de distribuição Cc e expandido. Você pode pesquisar essas informações usando uma pesquisa de Descoberta In-Place no Centro de administração do Exchange (EAC) ou uma Pesquisa de Conteúdo no Centro de Conformidade & Segurança. 
  
## <a name="how-bcc-recipients-and-expanded-distribution-group-recipients-are-preserved"></a>Como os destinatários Cc e os destinatários do grupo de distribuição expandido são preservados

Conforme declarado anteriormente, informações sobre destinatários Cc'ed são armazenadas com a mensagem na caixa de correio do remetente. Essas informações são indexadas e estão disponíveis para pesquisas e resdões de Descobertas EDiscovery. 
  
As informações sobre destinatários do grupo de distribuição expandido são armazenadas com a mensagem depois que você coloca uma caixa de correio em uma In-Place de responsabilidade ou de litígio. No Office 365, essas informações também são armazenadas quando uma política Microsoft 365 de retenção é aplicada a uma caixa de correio. A associação ao grupo de distribuição é determinada no momento em que a mensagem é enviada. A lista de destinatários expandidos armazenada com a mensagem não é impactada pelas alterações na associação ao grupo depois que a mensagem é enviada. 
  
| Informações sobre... | É armazenado em... | É armazenado por padrão? | É acessível a... |
|:-----|:-----|:-----|:-----|
|Destinatários Para e Cc  <br/> |Propriedades da mensagem nas caixas de correio do remetente e dos destinatários.  <br/> |Sim  <br/> |Remetente, destinatários e responsáveis pela conformidade  <br/> |
|Destinatários Cc  <br/> |Propriedade Message na caixa de correio do remetente.  <br/> |Sim  <br/> |Remetentes e responsáveis pela conformidade  <br/> |
|Destinatários do grupo de distribuição expandido  <br/> |Propriedades da mensagem na caixa de correio do remetente.  <br/> |Não. As informações de destinatário do grupo de distribuição expandida são armazenadas depois que uma caixa de correio é colocada In-Place retenção ou retenção de litígio ou atribuída a uma política de retenção Microsoft 365 de segurança.  <br/> |Oficiais de conformidade  <br/> |
   
## <a name="searching-for-messages-sent-to-bcc-and-expanded-distribution-group-recipients"></a>Procurando mensagens enviadas para destinatários do grupo de distribuição Cc e expandido

Ao pesquisar mensagens enviadas a um destinatário, os resultados da pesquisa de DescobertaSuficiária agora incluem mensagens enviadas a um grupo de distribuição do que o destinatário é membro. A tabela a seguir mostra os cenários em que as mensagens enviadas para o Cc e destinatários de grupos de distribuição expandidos são retornadas em pesquisas de Descobertas e Descobertas.
  
Cenário 1: John é membro do grupo US-Sales distribuição. Esta tabela mostra os resultados da pesquisa de Descobertas EDiscovery quando Bob envia uma mensagem para João direta ou indiretamente por meio de um grupo de distribuição.
  
| Quando você pesquisa na caixa de correio do Bob mensagens enviadas... | E a mensagem é enviada com... | Os resultados incluem mensagem? |
|:-----|:-----|:-----|
|To:John  <br/> |João no TO  <br/> |Sim  <br/> |
|To:John  <br/> |US-Sales em TO  <br/> |Sim  <br/> |
|To:US-Sales  <br/> |US-Sales em TO  <br/> |Sim  <br/> |
|Cc:John  <br/> |João no CC  <br/> |Sim  <br/> |
|Cc:John  <br/> |US-Sales no CC  <br/> |Sim  <br/> |
|Cc:US-Sales  <br/> |US-Sales no CC  <br/> |Sim  <br/> |
   
Cenário 2: Bob envia um email para João (To/Cc) e Jack (Cc diretamente ou indiretamente por meio de um grupo de distribuição). A tabela a seguir mostra os resultados da pesquisa de Descobertas EDiscovery.
  
| Quando você pesquisa... | Para mensagens enviadas... | Os resultados incluem mensagem? | Observações |
|:-----|:-----|:-----|:-----|
|Caixa de correio de Bob  <br/> |To/Cc:John  <br/> |Sim  <br/> |Apresenta uma indicação de que Jack foi Cc'ed.  <br/> |
|Caixa de correio de Bob  <br/> |Bcc:Jack  <br/> |Sim  <br/> |Apresenta uma indicação de que Jack foi Cc'ed.  <br/> |
|Caixa de correio de Bob  <br/> |Bcc:Jack (via grupo de distribuição)  <br/> |Sim  <br/> |A lista de membros do grupo de distribuição Cc'ed, expandida quando a mensagem foi enviada, fica visível na visualização, exportação e logs de pesquisa de Descoberta e Descoberta.  <br/> |
|Caixa de correio de John  <br/> |To/Cc:John  <br/> |Sim  <br/> |Nenhuma indicação de destinatários Cc.  <br/> |
|Caixa de correio de John  <br/> |Bcc:Jack (diretamente ou por meio do grupo de distribuição)  <br/> |Não  <br/> |As informações do Cc não são armazenadas na mensagem entregue aos destinatários. Você deve pesquisar a caixa de correio do remetente.  <br/> |
|Caixa de correio de Jack  <br/> |To/Cc:John (diretamente ou por meio do grupo de distribuição)  <br/> |Sim  <br/> |As informações de To/Cc são incluídas na mensagem entregue a todos os destinatários.  <br/> |
|Caixa de correio de Jack  <br/> |Bcc:Jack (diretamente ou por meio do grupo de distribuição)  <br/> |Não  <br/> |As informações do Cc não são armazenadas na mensagem entregue aos destinatários. Você deve pesquisar a caixa de correio do remetente.  <br/> |
   
## <a name="frequently-asked-questions"></a>Perguntas frequentes

 **P. Quando e onde as informações de destinatário Cc são armazenadas?**
  
R. As informações do destinatário Cc são preservadas por padrão na mensagem original na caixa de correio do remetente. Se o destinatário Cc for um grupo de distribuição, a associação ao grupo de distribuição só será expandida se a caixa de correio do remetente estiver em retenção ou atribuída a uma política de retenção de Microsoft 365.
  
 **P. Quando e onde a lista de destinatários do grupo de distribuição expandida é armazenada?**
  
R. A associação ao grupo é expandida no momento em que a mensagem é enviada. A lista de membros do grupo de distribuição expandida é armazenada na mensagem original na caixa de correio do remetente. A caixa de correio do remetente deve estar In-Place retenção, retenção de litígio ou atribuída a uma política de Microsoft 365 de retenção.
  
 **P. Os destinatários To/Cc podem ver quais destinatários foram Cc'ed?**
  
R. Não. Essas informações não estão incluídas nos headers de mensagens e não estão visíveis para destinatários To/Cc. O remetente pode ver o campo Cc armazenado na mensagem original armazenada em sua caixa de correio. Os responsáveis pela conformidade podem ver essas informações ao pesquisar a caixa de correio do remetente.
  
 **P. Como posso garantir que destinatários de grupos de distribuição expandidos sejam sempre preservados?**
  
R. Para garantir que os membros do grupo de distribuição expandido sejam sempre preservados com uma [mensagem,](/Exchange/policy-and-compliance/holds/place-all-mailboxes-on-hold) coloque todas as caixas de correio em espera ou crie uma política de retenção Microsoft 365 toda a organização. 
  
 **P. Quais tipos de grupos são suportados?**
  
R. Há suporte para grupos de distribuição, grupos de segurança habilitados para email e grupos dinâmicos de distribuição. 
  
 **P. Há um limite no número de destinatários do grupo de distribuição que são expandidos e armazenados na mensagem?**
  
R. Até 10.000 membros de um grupo de distribuição são preservados.
  
 **P. Há suporte para grupos de distribuição aninhados?**
  
R. Sim, 25 níveis de grupos de distribuição aninhados são expandidos.
  
 **P. Onde as informações do destinatário do grupo de distribuição Cc e expandida estão visíveis?**
  
R. Informações de destinatários do grupo de distribuição expandida e cc são visíveis para os responsáveis pela conformidade ao executar uma pesquisa de Descoberta e Descoberta. Os destinatários do grupo de distribuição Cc e expandido são incluídos nos resultados da pesquisa copiados para uma caixa de correio de Descoberta ou exportados para um arquivo PST e no log de Descoberta Eletrônico incluído nos resultados da pesquisa. As informações do destinatário Cc também estão disponíveis na visualização de pesquisa.
  
 **P. O que acontece se um membro de um grupo de distribuição estiver oculto da GAL (lista de endereços global) da organização?**
  
R. Não há impacto. Se os destinatários estão ocultos da GAL, eles ainda estão incluídos na lista de destinatários do grupo de distribuição expandido.