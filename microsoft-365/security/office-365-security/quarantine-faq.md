---
title: Perguntas Frequentes sobre a Quarentena
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/16/2017
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Este tópico fornece as perguntas frequentes e respectivas respostas sobre a quarentena hospedada.
ms.openlocfilehash: 393542596eacd26a4f64237f666fabfe236dceed
ms.sourcegitcommit: 9db133b110956bff2942bc903a4484247fc7020a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37510528"
---
# <a name="quarantine-faq"></a>Perguntas Frequentes sobre a Quarentena

Este tópico fornece as perguntas frequentes e respectivas respostas sobre a quarentena hospedada. As respostas se aplicam aos clientes do Microsoft Exchange Online e do Proteção do Exchange Online.
  
 **P. como gerenciar mensagens em quarentena em quarentena?**
  
Você precisa usar o centro de &amp; conformidade de segurança para exibir e trabalhar com mensagens que foram enviadas à quarentena porque elas contêm malware. Para obter mais informações, consulte [Quarantine Email messages in Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).
  
 **P. Como configuro o serviço para enviar mensagens de spam para a quarentena?**
  
R. Por padrão, mensagens filtradas por conteúdo são enviadas para a pasta Lixo Eletrônico dos destinatários. No entanto, os administradores podem configurar suas políticas de filtro de conteúdo para enviar mensagens de spam para a quarentena. Para obter mais informações sobre as diferentes ações que podem ser executadas em mensagens filtradas por conteúdo, consulte [Configure Your spam filter Policies](configure-your-spam-filter-policies.md).
  
 **P. O serviço tem administrador e gerenciamento de usuário final de mensagens de spam em quarentena?**
  
R. Como administrador, você pode pesquisar e exibir detalhes sobre todas as mensagens de email em quarentena no Centro de Administração do Exchange (EAC). Depois de localizar a mensagem, você pode liberá-la para usuários específicos e, opcionalmente, relatá-la como falso positivo (não é lixo eletrônico) à Equipe de Análise de Spam da Microsoft. Para obter mais informações, consulte [Localizar e liberar mensagens em quarentena como um administrador](find-and-release-quarantined-messages-as-an-administrator.md).
  
Como usuário final, você pode gerenciar suas próprias mensagens em quarentena de spam via: 
  
- A interface de usuário de quarentena de spam. Para obter mais informações, consulte [Find and Release Quarantined Messages (End Users)](http://technet.microsoft.com/library/e439b560-827a-4807-abd3-6b861c1ff786.aspx).
        
 **P. Como posso conceder acesso à quarentena de spam para os usuários finais?**
  
R. Para acessar a quarentena de spam de usuário final, os usuários finais devem ter uma ID de usuário e senha válidas para o Office 365. Os clientes do EOP que protegem caixas de correio locais devem ser usuários de email válidos criados via sincronização de diretórios ou pelo EAC. Para obter mais informações sobre o gerenciamento de usuários, os administradores do EOP podem consultar [gerenciar usuários de email no EOP](manage-mail-users-in-eop.md). Para clientes autônomos do EOP, recomendamos usar a sincronização de diretórios e habilitar o Bloqueio de Borda Baseado em Diretórios; para obter mais informações, consulte [Usar Bloqueio de Borda Baseado em Diretório para Rejeitar Mensagens Enviadas a Destinatários Inválidos](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).
  
 **P. É possível enviar qualquer outra mensagem, além de spam, para a quarentena?**
  
A. Sim. As mensagens que correspondem a uma regra de fluxo de emails (também conhecida como regra de transporte) junto com as mensagens identificadas como Phish também podem ser enviadas para a quarentena do administrador, se essa for a ação configurada. A quarentena de usuário final destina-se apenas a spam.
  
 **P. Por quanto tempo as mensagens são mantidas na quarentena?**
  
R. Por padrão, as mensagens de spam em quarentena são mantidas em quarentena por 30 dias, enquanto as mensagens em quarentena que correspondem a uma regra de fluxo de emails são mantidas em quarentena por até 30 dias, com base no período de retenção definido em sua política de filtro de conteúdo padrão. Após esse período de tempo, as mensagens serão excluídas e não podem ser recuperadas. O período de retenção para mensagens em quarentena que correspondem a uma regra de fluxo de emails não é configurável. No entanto, o período de retenção para mensagens de spam em quarentena pode ser reduzido através da configuração **Reter spam por (dias)** nas suas políticas de filtro de conteúdo. Para saber mais, confira [Configure your spam filter policies](configure-your-spam-filter-policies.md).
  
 **P. Posso liberar ou relatar mais de uma mensagem em quarentena por vez?**
  
R. Sim, até 100 mensagens podem ser liberadas de uma só vez no portal de quarentena. Além disso, os administradores podem criar um script do Windows PowerShell remoto para realizar essa tarefa. Use o cmdlet [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) para procurar por mensagens, e o cmdlet [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) para liberá-las. 
  
 **P. Coringas são aceitos durante a pesquisa de mensagens em quarentena? Posso pesquisar mensagens em quarentena em um domínio específico?**
  
R. Não há suporte para curingas durante a especificação de critérios de pesquisa no Centro de Administração do Exchange. Por exemplo, ao pesquisar um remetente, especifique o endereço de email completo.
  
Usando o Windows PowerShell remoto, os administradores podem especificar o cmdlet [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) para pesquisar por mensagens em quarentena em um domínio específico (por exemplo, contoso.com): 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```

Os resultados podem ser passados para o cmdlet [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx). Inclua o parâmetro -ReleaseToAll para liberar a mensagem para todos os destinatários. Depois de liberada, a mensagem não poderá ser liberada novamente. 
  
```
Get-QuarantineMessage | ? {$_.Senderaddress -like "*@contoso.com"}
```


