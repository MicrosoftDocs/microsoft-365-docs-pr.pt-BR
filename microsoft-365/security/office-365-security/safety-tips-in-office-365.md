---
title: Dicas de segurança para mensagens de email
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: Saiba mais sobre como o EOP e Office 365 proteger você com prevenção de spam, phishing e malware adicionando uma dica de segurança à parte superior dos emails.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 659a83c73b4fef9097aa317332c9951d53b09a33
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994980"
---
# <a name="safety-tips-in-email-messages"></a>Dicas de segurança para mensagens de email

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Proteção do Exchange Online (EOP) e Microsoft 365 proteger você com prevenção contra spam, phishing e malware. Hoje, alguns desses ataques são tão bem elaborados que parecem legítimos. O envio de mensagens para a pasta Lixo Eletrônico nem sempre é suficiente. Agora, quando você verifica seu email no Outlook ou Outlook na Web ou em qualquer cliente de email, o EOP verifica automaticamente o remetente e adiciona um dica de segurança na parte superior do email.

As dicas de Outlook não dependem de qual versão do Outlook você está usando porque o dica de segurança está aberto e inserido diretamente no corpo da mensagem. Isso significa que o dica de segurança aparecerá em qualquer cliente de email que você esteja usando. Ele é feito no nível do filtro de email e não é renderizado no nível do cliente de email, portanto, além de aparecer em qualquer versão do Outlook, ele também aparece em qualquer cliente de email.

A dica de segurança , uma mensagem codificada por cores, avisará você sobre mensagens potencialmente prejudiciais. A maioria das mensagens em sua caixa de entrada não terá um dica de segurança. Você só os verá quando o EOP e Microsoft 365 tiver informações necessárias para ajudar a evitar ataques de spam, phishing e malware. Se as dicas de segurança aparecerem na caixa de entrada, você poderá usar os exemplos a seguir para saber mais sobre cada tipo de dica de segurança.

- Email suspeito (vermelho dica de segurança).

    ![Captura de tela que mostra um dica de segurança.](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    Uma mensagem dica de segurança em um email significa que a mensagem recebida contém algo suspeito, como um esquema de phishing. Recomendamos que você exclua esse tipo de mensagem de email da sua caixa de entrada sem abri-la.

- Cofre email (dica de segurança).

    ![Captura de tela que mostra um dica de segurança.](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    Além das mensagens não seguras, também vamos falar sobre mensagens válidas de senders em que confiamos com uma dica de segurança. Uma dica de segurança verde em um email significa que verificamos o remetente da mensagem e verificamos se ela é segura. A Microsoft mantém essa lista de envios confiáveis que inclui organizações financeiras e outras que são frequentemente falsas ou personificadas.

## <a name="working-with-safety-tips"></a>Trabalhar com dicas de segurança

Os administradores podem ativar ou desativar dicas de segurança em políticas anti-spam. Para obter mais informações, consulte [Configure as políticas de anti-spam no Office 365](configure-your-spam-filter-policies.md).

Se você não concordar com como o EOP categorizou uma mensagem (ou seja, a mensagem não é spam ou deveria ter sido marcada como spam), você pode enviar as mensagens à Microsoft para análise para ajudar a melhorar sua experiência. Para obter instruções, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md). Você também pode clicar no link Comentários no dica de segurança enviar comentários diretamente à Microsoft para nos ajudar a melhorar.
