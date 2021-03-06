---
title: Introdução à política DLP padrão
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/10/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: e0ada764-6422-4b44-9472-513bed04837b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Saiba como usar o relatório para refinar a política de prevenção de perda de dados (DLP) padrão da sua organização.
ms.openlocfilehash: 4530e570f0ce593a7d2cb62acc28dfa4e1658df0
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114079"
---
# <a name="get-started-with-the-default-dlp-policy"></a>Introdução à política DLP padrão

Antes mesmo de criar sua primeira política de prevenção contra perda de dados (DLP), a DLP está ajudando a proteger suas informações confidenciais com uma política padrão. Essa política padrão e sua recomendação (mostradas abaixo) ajudam a manter seu conteúdo sensível seguro notificando você quando emails ou documentos que contêm um número de cartão de crédito foram compartilhados com alguém de fora da sua organização. Você verá essa recomendação na home **page** do Centro de Conformidade &amp; e Segurança. 
  
Você pode usar esse widget para exibir rapidamente quando e quantas informações confidenciais foram compartilhadas e refinar a política de DLP padrão em apenas um ou dois cliques. Você também pode editar a política DLP padrão a qualquer momento porque ela é totalmente personalizável. Observe que, se você não vir a recomendação no início, tente clicar em **+More** na parte inferior da **seção Recomendado para** você. 
  
![Widget nomeado Proteger ainda mais o conteúdo compartilhado](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>Exibir o relatório e refinar a política DLP padrão

Quando o widget mostrar que os usuários compartilharam informações confidenciais com pessoas de fora da sua organização, escolha **Refinar política DLP** na parte inferior. 
  
O relatório detalhado mostra quando e quanto conteúdo contendo números de cartão de crédito foi compartilhado nos últimos 30 dias. Observe que as combinações de regra podem levar até 48 horas para aparecer no widget.
  
Para ajudar a proteger as informações confidenciais, a política DLP padrão:
  
- Detecta quando o conteúdo em Exchange, SharePoint e OneDrive que contém pelo menos um número de cartão de crédito é compartilhado com pessoas de fora da sua organização.
    
- Mostra uma dica de política e envia uma notificação de email para os usuários quando tentam compartilhar essas informações confidenciais com pessoas de fora da sua organização. Para obter mais informações sobre essas opções, consulte [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).
    
- Gera relatórios de atividades detalhados para que você possa rastrear coisas como quem compartilhou o conteúdo com pessoas de fora da sua organização e quando eles fizeram isso. Você pode usar os relatórios [DLP e](view-the-dlp-reports.md) [os](search-the-audit-log-in-security-and-compliance.md) dados de log de auditoria (onde **a** DLP de atividade ) para ver essas  =  informações.
    
Para refinar rapidamente a política de DLP padrão, você pode optar por ter:
  
- Envie um email de relatório de incidentes quando os usuários compartilharem essas informações confidenciais com pessoas de fora da organização.
    
- Adicione outros usuários ao relatório de incidentes de email.
    
- Bloqueie o acesso ao conteúdo que contém as informações confidenciais, mas permita que o usuário substitua e compartilhe ou envie se precisar.
    
Para obter mais informações sobre relatórios de incidentes ou restrição de acesso, consulte [Referência de prevenção contra perda de dados](data-loss-prevention-policies.md).
  
Se você quiser alterar essas opções mais tarde, você pode editar a política DLP padrão a qualquer momento - consulte a próxima seção.
  
![Configurações para widget chamado Proteger ainda mais o conteúdo compartilhado](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>Editar a política DLP padrão

Essa política é chamada de política  **de DLP** padrão e aparece em Prevenção contra perda de dados na página **Política** do Centro de Conformidade e &amp; Segurança. 
  
Essa política é totalmente personalizável, igual a qualquer política de DLP que você mesmo cria do zero. Você também pode desativar ou excluir a política, para que seus usuários não recebam mais dicas de política ou notificações por email.
  
![Política DLP chamada política DLP padrão](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Quando o widget faz e não aparece

O widget chamado **Proteger ainda mais o conteúdo** compartilhado aparece na seção Recomendado para **você** da **home** page do Centro de Conformidade &amp; de Segurança. 
  
Esse widget só aparece quando:
  
- Não há políticas de prevenção contra perda de dados no Centro de Conformidade de Segurança &amp; ou Exchange de administração. Esse widget destina-se a ajudá-lo a começar com a DLP, para que ele não apareça se você já tiver políticas de DLP.
    
- O conteúdo que contém pelo menos um cartão de crédito foi compartilhado com alguém de fora da sua organização nos últimos 30 dias.
    
Observe que as combinações de regra podem levar até 48 horas para estar disponíveis para o widget, portanto, depois que informações confidenciais compartilhadas externamente são detectadas, pode levar até dois dias para que a recomendação apareça.
  
Por fim, depois de usar o widget para refinar a política de DLP padrão, o widget desaparece da **Home** page. 
  

