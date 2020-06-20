---
title: Introdução às recomendações de política DLP
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/7/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
ms.custom:
- seo-marvel-apr2020
description: Saiba como criar e editar a política de prevenção de perda de dados (DLP) recomendada para sua organização.
ms.openlocfilehash: 9588eabe5dbe2b1e60eaeb6a45eb95cc327383aa
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817630"
---
# <a name="get-started-with-dlp-policy-recommendations"></a>Introdução às recomendações de política DLP

Essa recomendação orientada por informações ajuda sua organização a manter o conteúdo confidencial seguro quando ele é armazenado e compartilhado no Microsoft 365, informando quando há uma lacuna possível na cobertura da política de DLP. Você verá essa recomendação na **Home** Page do centro de conformidade de segurança &amp; , se seus documentos contiverem qualquer um dos cinco tipos de informações confidenciais mais comuns, mas não estiverem protegidos por uma política de prevenção de perda de dados (DLP). 
  
Você pode usar esse widget para criar rapidamente uma política de DLP personalizada com apenas um clique ou dois, e depois de criar essa política de DLP, ela é totalmente personalizável. Observe que, se você não vir a recomendação primeiro, tente clicar **+ mais** na parte inferior da seção **recomendada para você** . 
  
![Widget chamado informações confidenciais desprotegidas](../media/91bc04d2-6eff-4294-8b73-b2d56d26ffc4.png)
  
## <a name="create-the-recommended-dlp-policy"></a>Criar a política de DLP recomendada

Quando o widget mostrar informações confidenciais desprotegidas, escolha **introdução** no final para criar rapidamente uma política de DLP. 
  
Para ajudar a proteger as informações confidenciais, esta política de DLP:
  
- Detecta quando o conteúdo no Exchange, SharePoint e OneDrive que contém um dos tipos desprotegidos de informações confidenciais é compartilhado com pessoas de fora da organização.
    
- Gera relatórios de atividade detalhados para que você possa rastrear coisas como quem compartilhou o conteúdo com pessoas de fora da sua organização e quando eles faziam. Você pode usar os [relatórios de DLP](view-the-dlp-reports.md) e [dados de log de auditoria](search-the-audit-log-in-security-and-compliance.md) (onde a **atividade**  =  **DLP**) para ver essas informações.
    
Você também pode optar por ter a política de DLP:
  
- Envie um email de relatório de incidentes quando os usuários compartilharem muitas dessas informações confidenciais com pessoas de fora da sua organização.
    
- Adicione outros usuários ao relatório de incidentes de email.
    
- Mostrar uma dica de política e enviar uma notificação por email aos usuários quando eles tentarem compartilhar essas informações confidenciais com pessoas de fora da organização. Para obter mais informações sobre essas opções, consulte [enviar notificações por email e mostrar dicas de política para políticas de DLP](use-notifications-and-policy-tips.md).
    
Se você quiser alterar essas opções mais tarde, poderá editar a política de DLP após sua criação. Por exemplo, você pode tornar a política mais restritiva até mesmo impedindo que as pessoas compartilhem conteúdo que contém informações confidenciais no primeiro lugar-Confira a próxima seção.
  
![Configurações do widget chamado informações confidenciais desprotegidas](../media/b6106cbd-1bed-4582-aaef-b678de470c9b.png)
  
## <a name="edit-the-recommended-dlp-policy"></a>Editar a política DLP recomendada

Após usar o widget para criar uma política de DLP, a política aparecerá em **prevenção de perda de dados** na página **política** do &amp; centro de conformidade de segurança. 
  
Por padrão, a política é chamada de **política recomendada pelo sistema para compartilhar informações confidenciais**. Essa política é totalmente personalizável, o mesmo que qualquer política de DLP que você criar a partir do zero. Por exemplo, se você optou por não ativar relatórios de incidentes e dicas de política ao usar o widget, sempre é possível editar a política e ativar essas opções a qualquer momento.
  
![Política recomendada de sistema para compartilhamento de informações confidenciais](../media/2fc49f25-ec25-4433-add4-d60f73888f13.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a>Quando o widget não aparece

O widget chamado **informações confidenciais desprotegidas** aparece na seção **recomendada para você** da **Home** Page do centro de conformidade de segurança &amp; . 
  
Este widget aparece somente quando:
  
- Novos documentos que contêm qualquer um dos cinco tipos mais comuns de informações confidenciais são detectados no SharePoint ou no OneDrive nos últimos 30 dias.
    
- Que as informações confidenciais ainda não estão protegidas por uma política de DLP existente.
    
Diferentemente das políticas de DLP que estão examinando constantemente seus dados, essa recomendação verifica intervalos em sua cobertura de política de DLP aproximadamente a cada 48 horas, portanto, após o carregamento do novo conteúdo, pode levar até dois dias para que a recomendação seja exibida.
  
Por fim, depois de usar o widget para criar uma política de DLP recomendada, o widget desaparecerá da **Home** Page. 
  

