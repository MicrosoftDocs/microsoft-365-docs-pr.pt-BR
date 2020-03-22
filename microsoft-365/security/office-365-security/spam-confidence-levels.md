---
title: Nível de confiança de spam
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender sobre como o nível de confiança de spam (SCL) determina a probabilidade ou improvável de uma mensagem ser spam, e as ações padrão que a filtragem de spam realiza em mensagens com base no SCL.
ms.openlocfilehash: b8f194f9aecc31896fb816433e71d1b26de708f7
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893689"
---
# <a name="spam-confidence-level-scl-in-office-365"></a>SCL (nível de confiança de spam) no Office 365

Quando o Office 365 (Exchange Online ou proteção do Exchange Online autônoma (EOP) sem caixas de correio do Exchange Online) recebe uma mensagem de email de entrada, a mensagem passa por filtragem de spam e recebe uma pontuação de spam. Essa pontuação é mapeada para um nível de confiança de spam (SCL) individual que é adicionado à mensagem em um cabeçalho X. Um SCL maior indica que uma mensagem é mais provável de ser spam. O serviço executa a ação na mensagem com base no SCL.

O que o SCL significa e as ações padrão executadas nas mensagens são descritas na tabela a seguir. Para obter mais informações sobre as ações que podem ser executadas em mensagens com base no veredicto de filtragem de spam, consulte [Configure anti-spam Policies in Office 365](configure-your-spam-filter-policies.md).

||||
|:---:|---|---|
|**SCL**|**Definição**|**Ação padrão**|
|-1|A mensagem ignorou a filtragem de spam. Por exemplo, a mensagem é de um remetente seguro, foi enviada a um destinatário seguro ou é de um servidor de origem de email na lista de IPs permitidos. Para obter mais informações, consulte [criar listas de remetentes seguros no Office 365](create-safe-sender-lists-in-office-365.md).|Entregar a mensagem para a caixa de entrada do destinatário.|
|0, 1|A filtragem de spam determinou que a mensagem não era spam.|Entregar a mensagem para a caixa de entrada do destinatário.|
|5, 6|Filtragem de spam marcou a mensagem como **spam**|Entregar a mensagem na pasta Lixo Eletrônico do destinatário.|
|9 |Filtragem de spam marcou a mensagem como **spam de alta confiança**|Entregar a mensagem na pasta Lixo Eletrônico do destinatário.|
|

Você notará que SCL 2, 3, 4, 7 e 8 não são usados pela filtragem de spam.

Você pode usar regras de fluxo de emails (também conhecidas como regras de transporte) para carimbar o SCL nas mensagens. Se você usar uma regra de fluxo de emails para definir o SCL, os valores 5 ou 6 disparam a ação de filtragem de spam para **spam**, e os valores 7, 8 ou 9 disparam a ação de filtragem de spam para **spam de alta confiança**. Para obter mais informações, consulte [usar regras de fluxo de emails para definir o nível de confiança de spam (SCL) em mensagens](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

Semelhante ao SCL, o nível de reclamação em massa (BCL) identifica emails em massa inválidos (também conhecidos como _emails cinza_). Uma BCL maior indica que uma mensagem de email em massa é mais provável de gerar queixas (e, portanto, é mais provável de spam). Você configura o limite de BCL em políticas antispam. Para obter mais informações, consulte [Configure anti-spam Policies in office 365](configure-your-spam-filter-policies.md), [BCL (nível de reclamação em massa) no Office 365)](bulk-complaint-level-values.md)e [qual é a diferença entre lixo eletrônico e email em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md).

||
|:-----|
|![O ícone pequeno do LinkedIn Learning](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Começando a usar o Office 365?**         Descubra cursos em vídeo gratuitos para **Office 365 admins and IT pros**, oferecidos pelo LinkedIn Learning.|
