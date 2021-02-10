---
title: Nível de confiança de spam
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre o nível de confiança de spam (SCL) que se aplica a mensagens no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e4fc20b7d7db5b85b5bdde02ab720fa26af2a4b5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167150"
---
# <a name="spam-confidence-level-scl-in-eop"></a>Nível de confiança de spam (SCL) no EOP

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, as mensagens de entrada passam pela filtragem de spam no EOP e são atribuídas a uma pontuação de spam. Essa pontuação é mapeada para um SCL (nível de confiança de spam) individual que é adicionado à mensagem em um X-header. Um SCL mais alto indica que é mais provável que uma mensagem seja spam. O EOP toma medidas na mensagem com base no SCL.

O que significa o SCL e as ações padrão que são realizadas nas mensagens são descritas na tabela a seguir. Para obter mais informações sobre ações que você pode tomar em mensagens com base no veredito de filtragem de spam, consulte Configurar políticas [anti-spam no EOP.](configure-your-spam-filter-policies.md)

****

|SCL|Definição|Ação padrão|
|:---:|---|---|
|-1|A mensagem ignorou a filtragem de spam. Por exemplo, a mensagem é de um remetente seguro, foi enviada para um destinatário seguro ou é de um servidor de origem de email na Lista de I Ip Permitir. Para obter mais informações, [consulte Criar listas de remetentes seguros no EOP.](create-safe-sender-lists-in-office-365.md)|Entregar a mensagem para a caixa de entrada do destinatário.|
|0, 1|A filtragem de spam determinou que a mensagem não era spam.|Entregar a mensagem para a caixa de entrada do destinatário.|
|5, 6|A filtragem de spam marcou a mensagem como **Spam**|Entregar a mensagem na pasta Lixo Eletrônico do destinatário.|
|9 |A filtragem de spam marcou a mensagem como **spam de alta confiança**|Entregar a mensagem na pasta Lixo Eletrônico do destinatário.|
|

Você notará que os SCL 2, 3, 4, 7 e 8 não são usados pela filtragem de spam.

Você pode usar regras de fluxo de emails (também conhecidas como regras de transporte) para carimbar o SCL nas mensagens. Se você usar uma regra de fluxo de emails para definir o SCL, os valores 5 ou 6 acionarão a ação de filtragem de spam para **Spam** e os valores 7, 8 ou 9 dispararão a ação de filtragem de spam para **spam** de alta confiança. Para obter mais informações, consulte Usar regras de fluxo de emails para definir o nível de confiança de [spam (SCL) em mensagens.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

Semelhante ao SCL, o nível de reclamação em massa (BCL) identifica emails em massa ruins (também conhecido como _email cinza)._ Um BCL mais alto indica que uma mensagem de email em massa tem mais chances de gerar reclamações (e, portanto, mais chances que seja spam). Você configura o limite de BCL em políticas anti-spam. Para obter mais informações, consulte Configurar políticas [anti-spam](configure-your-spam-filter-policies.md)no EOP , nível de reclamação em massa [(BCL) no EOP)](bulk-complaint-level-values.md)e Qual é a diferença entre lixo eletrônico e email em [massa?](what-s-the-difference-between-junk-email-and-bulk-email.md).

****

![O ícone curto do LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Novo para o Microsoft 365?** Descubra cursos em vídeo **gratuitos para administradores do Microsoft 365** e profissionais de TI, oferecidos pelo LinkedIn Learning.
