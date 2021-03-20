---
title: Como a DLP funciona com o Centro de & de Conformidade & centro de administração do Exchange
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Saiba como a DLP no Centro de Conformidade & segurança funciona com regras de DLP e fluxo de emails (regras de transporte) no centro de administração do Exchange.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cd8a3eb0e7bb859ab9e10551fadd22cc7dcb2a39
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905933"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a>Funcionamento da DLP entre o Centro de Conformidade e Segurança e o centro de administração do Exchange

No Office 365, você pode criar uma política de prevenção contra perda de dados (DLP) em dois centros de administração diferentes:
  
- No Centro **de Conformidade &** segurança, você pode criar uma única política de DLP para ajudar a proteger o conteúdo no SharePoint, no OneDrive, no Exchange e agora no Microsoft Teams. Quando possível, recomendamos que você crie uma política DLP aqui. Para obter mais informações, consulte DLP no Centro de [Conformidade & Segurança.](data-loss-prevention-policies.md)
    
- No Centro **de administração do Exchange,** você pode criar uma política DLP para ajudar a proteger o conteúdo somente no Exchange. Essa política pode usar regras de fluxo de emails do Exchange (também conhecidas como regras de transporte), portanto, ela tem mais opções específicas para lidar com emails. Para obter mais informações, [consulte DLP no Centro de administração do Exchange](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).
    
As polícias de DLP criadas nesses centros de administração funcionam lado a lado - este tópico explica como.
  
![Páginas DLP no Centro de Segurança e Conformidade e centro de administração do Exchange](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>Como a DLP no Centro de Conformidade & segurança funciona com regras de DLP e fluxo de emails no centro de administração do Exchange

Depois de criar uma política de DLP no Centro de Conformidade & segurança, a política será implantada em todos os locais incluídos na política. Se a política incluir o Exchange Online, a política será sincronizada e imposta exatamente da mesma forma que uma política de DLP criada no Centro de administração do Exchange. 
  
Se você tiver criado políticas de DLP no Centro de administração do Exchange, essas políticas continuarão a funcionar lado a lado com quaisquer políticas de email criadas no Centro de Conformidade & Segurança. Mas observe que as regras criadas no Centro de administração do Exchange têm precedência. Todas as regras de fluxo de emails do Exchange são processadas primeiro e, em seguida, as regras de DLP do Centro de Conformidade & segurança são processadas.
  
Isso significa que:
  
- As mensagens bloqueadas pelas regras de fluxo de emails do Exchange não serão verificados pelas regras de DLP criadas no & Centro de Conformidade e Segurança.
    
- Se uma regra de fluxo de emails do Exchange modificar uma mensagem de uma maneira que a faz corresponder a uma política de DLP no Centro de Conformidade do & de Segurança , como adicionar usuários externos, as regras DLP detectarão isso e imporão a política conforme necessário.
    
Observe também que as regras de fluxo de emails do Exchange que usam a ação "parar o processamento" não afetam o processamento de regras de DLP no Centro de Conformidade & segurança - elas ainda serão processadas.
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>Dicas de política no Centro de Conformidade & segurança versus o Centro de administração do Exchange

As dicas de política podem funcionar com políticas de DLP e regras de fluxo de emails criadas no Centro de administração do Exchange ou com políticas de DLP criadas no Centro de Conformidade & Segurança, mas não ambos. Isso porque essas políticas são armazenadas em locais diferentes, mas as dicas de política só podem ser desenhar de um único local.
  
Se você configurou dicas de política no Centro de administração do Exchange &, todas as dicas de política que você configurar no Centro de Conformidade e Segurança não aparecerão para os usuários no Outlook na Web e no Outlook 2013 e posterior até que você desligue as dicas no Centro de administração do Exchange. Isso garante que suas regras atuais de fluxo de emails do Exchange continuem a funcionar até que você opte por alternar para o Centro de Conformidade & Segurança.
  
Observe que, embora as dicas de política possam desenhar apenas de um único local, as notificações por email sempre são enviadas, mesmo se você estiver usando políticas DLP no Centro de Conformidade e Segurança & e no Centro de administração do Exchange.
