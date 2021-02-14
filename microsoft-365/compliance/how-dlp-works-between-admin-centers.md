---
title: Como a DLP funciona com o Centro de Conformidade & segurança & de administração do Exchange
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
description: Saiba como a DLP no Centro de Conformidade e Segurança & funciona com regras de fluxo de emails e DLP (regras de transporte) no Centro de administração do Exchange.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 05e3c6342ab6d57c1f22de96e64a01df5fd15131
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036192"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a>Funcionamento da DLP entre o Centro de Conformidade e Segurança e o centro de administração do Exchange

No Office 365, você pode criar uma política de prevenção contra perda de dados (DLP) em dois centros de administração diferentes:
  
- No Centro **de Conformidade &** segurança, você pode criar uma única política DLP para ajudar a proteger o conteúdo no SharePoint, no OneDrive, no Exchange e agora no Microsoft Teams. Quando possível, recomendamos que você crie uma política DLP aqui. Para obter mais informações, [consulte DLP no Centro de Conformidade & segurança.](data-loss-prevention-policies.md)
    
- No Centro **de administração do Exchange,** você pode criar uma política de DLP para ajudar a proteger o conteúdo somente no Exchange. Essa política pode usar regras de fluxo de emails do Exchange (também conhecidas como regras de transporte), portanto, ela tem mais opções específicas para lidar com emails. Para obter mais informações, consulte [DLP no Centro de administração do Exchange.](https://go.microsoft.com/fwlink/?linkid=852311)
    
As polícias de DLP criadas nesses centros de administração funcionam lado a lado- este tópico explica como.
  
![Páginas DLP no Centro de Conformidade e Segurança e no Centro de administração do Exchange](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>Como a DLP no Centro de Conformidade e Segurança & funciona com regras de fluxo de emails e DLP no Centro de administração do Exchange

Depois de criar uma política de DLP no Centro de & Conformidade e Segurança, a política será implantada em todos os locais incluídos na política. Se a política incluir o Exchange Online, a política será sincronizada lá e imposta exatamente da mesma maneira que uma política de DLP criada no Centro de administração do Exchange. 
  
Se você criou políticas de DLP no Centro de administração do Exchange, essas políticas continuarão a funcionar lado a lado com quaisquer políticas de email criadas no Centro de Conformidade e Segurança &. Mas observe que as regras criadas no Centro de administração do Exchange têm precedência. Todas as regras de fluxo de emails do Exchange são processadas primeiro e, em seguida, as regras de DLP do Centro de Conformidade e Segurança & são processadas.
  
Isso significa que:
  
- As mensagens bloqueadas pelas regras de fluxo de emails do Exchange não serão examinadas pelas regras de DLP criadas no Centro de Conformidade e Segurança & Segurança.
    
- Se uma regra de fluxo de emails do Exchange modifica uma mensagem de uma maneira que a faz corresponder a uma política de DLP no Centro de Conformidade do & de Segurança, como adicionar usuários externos, as regras de DLP detectarão isso e aplicarão a política conforme necessário.
    
Observe também que as regras de fluxo de emails do Exchange que usam a ação "parar o processamento" não afetam o processamento de regras de D & LP no Centro de Conformidade e Segurança - elas ainda serão processadas.
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>Dicas de política no Centro de Conformidade & segurança versus o Centro de administração do Exchange

As dicas de política podem funcionar com políticas de DLP e regras de fluxo de emails criadas no Centro de administração do Exchange ou com políticas de DLP criadas no Centro de Conformidade e & Segurança, mas não em ambos. Isso porque essas políticas são armazenadas em locais diferentes, mas as dicas de política podem desenhar apenas de um único local.
  
Se você tiver configurado dicas de política no Centro de administração do Exchange &, todas as dicas de política que você configurar no Centro de Conformidade e Segurança não aparecerão para os usuários no Outlook na Web e no Outlook 2013 e posteriores até você desativar as dicas no Centro de administração do Exchange. Isso garante que suas regras atuais de fluxo de emails do Exchange continuarão a funcionar até que você opte por alternar para o Centro de Conformidade e & Segurança.
  
Observe que, embora as dicas de política possam ser extraidas apenas de um único local, as notificações por email são sempre enviadas, mesmo que você esteja usando políticas DLP no Centro de Conformidade e Segurança & e no Centro de administração do Exchange.
  

