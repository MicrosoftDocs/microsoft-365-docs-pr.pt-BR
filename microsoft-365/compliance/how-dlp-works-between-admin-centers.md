---
title: Funcionamento da DLP entre o Centro de Conformidade e Segurança e o centro de administração do Exchange
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
description: Saiba como a DLP no centro de conformidade & segurança funciona com a DLP e regras de fluxo de emails (regras de transporte) no centro de administração do Exchange.
ms.openlocfilehash: a491317727cce571f0f9e1c527557595f6adf7b5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596508"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a>Funcionamento da DLP entre o Centro de Conformidade e Segurança e o centro de administração do Exchange

No Office 365, você pode criar uma política de prevenção de perda de dados (DLP) em dois centros de administração diferentes:
  
- No **centro de conformidade & segurança**, você pode criar uma única política de DLP para ajudar a proteger o conteúdo no SharePoint, onedrive, Exchange e agora Microsoft Teams. Quando possível, recomendamos que você crie uma política de DLP aqui. Para obter mais informações, consulte [DLP no centro de conformidade de & de segurança](data-loss-prevention-policies.md).
    
- No **centro de administração do Exchange**, você pode criar uma política de DLP para ajudar a proteger o conteúdo somente no Exchange. Essa política pode usar regras de fluxo de emails do Exchange (também conhecidas como regras de transporte), portanto, ela tem mais opções específicas para lidar com emails. Para obter mais informações, consulte [DLP no centro de administração do Exchange](https://go.microsoft.com/fwlink/?linkid=852311).
    
As políticas de DLP criadas nesses centros de administração funcionam lado a lado – este tópico explica como.
  
![Páginas de DLP no centro de administração de segurança e conformidade do Exchange](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>Como a DLP no centro de conformidade & de segurança funciona com as regras de fluxo de email e DLP no centro de administração do Exchange

Depois de criar uma política de DLP no centro de conformidade e segurança &, a política é implantada em todos os locais incluídos na política. Se a política incluir o Exchange Online, a política será sincronizada e aplicada exatamente da mesma maneira que uma política de DLP criada no centro de administração do Exchange. 
  
Se você tiver criado políticas de DLP no centro de administração do Exchange, essas políticas continuarão a funcionar lado a lado com todas as políticas de email que você cria no centro de conformidade & segurança. Mas Observe que as regras criadas no centro de administração do Exchange têm precedência. Todas as regras de fluxo de mensagens do Exchange são processadas primeiro e, em seguida, as regras de DLP do centro de conformidade & segurança são processadas.
  
Isso significa que:
  
- As mensagens bloqueadas pelas regras de fluxo de mensagens do Exchange não serão verificadas pelas regras de DLP criadas no centro de conformidade de & de segurança.
    
- Se uma regra de fluxo de email do Exchange modifica uma mensagem de uma maneira que faz com que ela coincida com uma política de DLP no centro de conformidade de & de segurança, como adicionar usuários externos, as regras de DLP detectarão isso e imporão a política, conforme necessário.
    
Observe também que as regras de fluxo de email do Exchange que usam a ação "parar processamento" não afetam o processamento de regras de DLP no centro de conformidade de & de segurança, elas ainda serão processadas.
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>Dicas de política no centro de conformidade e segurança & vs. o centro de administração do Exchange

As dicas de política podem funcionar com políticas de DLP e regras de fluxo de emails criadas no centro de administração do Exchange ou com políticas de DLP criadas no centro de conformidade & segurança, mas não em ambos. Isso ocorre porque essas políticas são armazenadas em locais diferentes, mas as dicas de política podem desenhar apenas de um único local.
  
Se você configurou dicas de política no centro de administração do Exchange, qualquer dica de política configurada no centro de conformidade & segurança não aparecerá para os usuários no Outlook na Web e no Outlook 2013 e posterior até que você desative as dicas no centro de administração do Exchange. Isso garante que as regras atuais de fluxo de email do Exchange continuem a funcionar até que você opte por alternar para o centro de conformidade de & de segurança.
  
Observe que, embora as dicas de política possam desenhar apenas a partir de um único local, as notificações por email são sempre enviadas, mesmo que você esteja usando políticas de DLP no centro de conformidade do & de segurança e no centro de administração do Exchange.
  

