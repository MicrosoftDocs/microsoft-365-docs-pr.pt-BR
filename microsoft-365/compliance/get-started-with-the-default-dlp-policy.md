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
description: Saiba como usar o relatório para refinar a política de DLP (prevenção de perda de dados) padrão da sua organização.
ms.openlocfilehash: 7c8f0460f9cd02ee3d26197965f5ea74737ac833
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817610"
---
# <a name="get-started-with-the-default-dlp-policy"></a>Introdução à política DLP padrão

Antes de criar a primeira política de DLP (prevenção contra perda de dados), a DLP está ajudando a proteger suas informações confidenciais com uma política padrão. Essa política padrão e sua recomendação (mostrado abaixo) ajudam a manter seu conteúdo confidencial seguro, notificando-o quando emails ou documentos contendo um número de cartão de crédito foram compartilhados com alguém de fora da sua organização. Você verá essa recomendação na **Home** Page do centro de conformidade de segurança &amp; . 
  
Você pode usar esse widget para exibir rapidamente quando e quantas informações confidenciais foram compartilhadas e, em seguida, refinar a política de DLP padrão em apenas um clique ou dois. Você também pode editar a política de DLP padrão a qualquer momento, pois ela é totalmente personalizável. Observe que, se você não vir a recomendação primeiro, tente clicar **+ mais** na parte inferior da seção **recomendada para você** . 
  
![Widget chamado proteger mais conteúdo compartilhado](../media/2bae6dbc-cc92-4f35-b54c-c36e60226b5b.png)
  
## <a name="view-the-report-and-refine-the-default-dlp-policy"></a>Exibir o relatório e refinar a política de DLP padrão

Quando o widget mostrar que os usuários compartilharam informações confidenciais com pessoas de fora da sua organização, escolha **refinar política de DLP** na parte inferior. 
  
O relatório detalhado mostra quando e quanto conteúdo que contém os números do cartão de crédito foi compartilhado nos últimos 30 dias. Observe que as correspondências de regra podem levar até 48 horas para serem exibidas no widget.
  
Para ajudar a proteger as informações confidenciais, a política de DLP padrão:
  
- Detecta quando o conteúdo no Exchange, SharePoint e OneDrive que contém pelo menos um número de cartão de crédito é compartilhado com pessoas de fora da sua organização.
    
- Mostra uma dica de política e envia uma notificação por email aos usuários quando eles tentam compartilhar essas informações confidenciais com pessoas de fora da sua organização. Para obter mais informações sobre essas opções, consulte [enviar notificações por email e mostrar dicas de política para políticas de DLP](use-notifications-and-policy-tips.md).
    
- Gera relatórios de atividade detalhados para que você possa rastrear coisas como quem compartilhou o conteúdo com pessoas de fora da sua organização e quando eles faziam. Você pode usar os [relatórios de DLP](view-the-dlp-reports.md) e [dados de log de auditoria](search-the-audit-log-in-security-and-compliance.md) (onde a **atividade**  =  **DLP**) para ver essas informações.
    
Para refinar rapidamente a política de DLP padrão, você pode optar por fazê-la:
  
- Envie um email de relatório de incidentes quando os usuários compartilharem essas informações confidenciais com pessoas de fora da sua organização.
    
- Adicione outros usuários ao relatório de incidentes de email.
    
- Bloquear o acesso ao conteúdo que contém as informações confidenciais, mas permitir que o usuário substitua e compartilhe ou envie se necessário.
    
Para obter mais informações sobre relatórios de incidentes ou restringir o acesso, consulte [visão geral das políticas de prevenção contra perda de dados](data-loss-prevention-policies.md).
  
Se você quiser alterar essas opções mais tarde, poderá editar a política de DLP padrão a qualquer momento-consulte a próxima seção.
  
![Configurações para widget chamado proteger mais conteúdo compartilhado](../media/dad30a84-2715-4c0a-a5c5-44d85492363e.png)
  
## <a name="edit-the-default-dlp-policy"></a>Editar a política de DLP padrão

Essa política é chamada de **política de DLP padrão** e aparece sob **prevenção de perda de dados** na página **política** do centro de conformidade de segurança &amp; . 
  
Essa política é totalmente personalizável, o mesmo que qualquer política de DLP que você criar a partir do zero. Você também pode desativar ou excluir a política, para que os usuários não recebam mais dicas de política ou notificações por email.
  
![Política de DLP chamada política de DLP padrão](../media/260731e8-4d57-4c98-abec-07b052ec48d5.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Quando o widget não aparece

O widget chamado **proteger mais conteúdo compartilhado** aparece na seção **recomendado para você** da **Home** Page do centro de conformidade de segurança &amp; . 
  
Este widget aparece somente quando:
  
- Não há políticas de prevenção contra perda de dados no &amp; centro de conformidade de segurança ou no centro de administração do Exchange. Este widget tem o objetivo de ajudá-lo a começar a usar o DLP, portanto, ele não aparecerá se você já tiver políticas de DLP.
    
- O conteúdo que contém menos um cartão de crédito foi compartilhado com alguém de fora da sua organização nos últimos 30 dias.
    
Observe que as correspondências de regras podem levar até 48 horas para estar disponível para o widget, portanto, depois que as informações confidenciais compartilhadas externamente forem detectadas, pode levar até dois dias para que a recomendação seja exibida.
  
Por fim, depois de usar o widget para refinar a política de DLP padrão, o widget desaparecerá da **Home** Page. 
  

