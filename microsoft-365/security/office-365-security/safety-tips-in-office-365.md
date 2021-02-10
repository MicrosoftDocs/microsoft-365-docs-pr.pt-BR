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
description: Saiba mais sobre como o EOP e o Office 365 protegem você contra spam, phishing e prevenção de malware adicionando uma dica de segurança na parte superior dos emails.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c37eba07b306ff47e14640e494e468b63b358726
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166610"
---
# <a name="safety-tips-in-email-messages"></a>Dicas de segurança para mensagens de email

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

O Exchange Online Protection (EOP) e o Microsoft 365 protegem você com spam, phishing e prevenção contra malware. Hoje, alguns desses ataques são tão bem elaborados que parecem legítimos. Enviar mensagens para a pasta Lixo Eletrônico nem sempre é suficiente. Agora, quando você verifica seu email no Outlook ou no Outlook na Web ou em qualquer cliente de email, o EOP verifica automaticamente o remetente e adiciona uma dica de segurança na parte superior do email.

As dicas de segurança no Outlook não dependem da versão do Outlook que você está usando porque a dica de segurança está quebrada e inserida diretamente no corpo da mensagem. Isso significa que a dica de segurança será aparecer em qualquer cliente de email que você estiver usando. Isso é feito no nível do filtro de email e não é renderizado no nível do cliente de email, portanto, ele não só aparece em qualquer versão do Outlook, como também aparece em qualquer cliente de email.

A dica de segurança ( uma mensagem codificada por cores ) avisará você sobre mensagens potencialmente prejudiciais. A maioria das mensagens em sua caixa de entrada não terá uma dica de segurança. Você só os verá quando o EOP e o Microsoft 365 têm informações necessárias para ajudar a evitar ataques de spam, phishing e malware. Se as dicas de segurança aparecerem na sua caixa de entrada, você poderá usar os exemplos a seguir para saber mais sobre cada tipo de dica de segurança.

- Email suspeito (dica de segurança vermelha).

    ![Captura de tela que mostra uma dica de segurança vermelha.](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    Uma dica de segurança vermelha em um email significa que a mensagem recebida contém algo suspeito, como uma tentativa de phishing. Recomendamos que você exclua esse tipo de mensagem de email da sua caixa de entrada sem abri-la.

- Email seguro (dica de segurança verde).

    ![Captura de tela que mostra uma dica de segurança verde.](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    Além das mensagens não seguras, também contaremos a você sobre mensagens válidas dos envios que confiamos com uma dica de segurança verde. Uma dica de segurança verde em um email significa que verificamos o remetente da mensagem e verificamos se ela é segura. A Microsoft mantém essa lista de envios confiáveis, que inclui organizações financeiras e outras que são frequentemente falsas ou personificadas.

## <a name="working-with-safety-tips"></a>Trabalhar com dicas de segurança

As dicas de segurança estão sempre habilitadas para o Outlook na Web, mesmo que nem todas as mensagens recebam uma. Os administradores podem desativar as dicas de segurança para outros clientes de email, como o Outlook. Para obter mais informações, consulte [Configure as políticas de anti-spam no Office 365](configure-your-spam-filter-policies.md).

Se você não concordar com como o EOP categorizou uma mensagem (ou seja, a mensagem não é spam ou deveria ter sido marcada como spam), você pode enviar as mensagens à Microsoft para análise para ajudar a melhorar sua experiência. Para obter instruções, confira [Relatar mensagens e arquivos para a Microsoft.](report-junk-email-messages-to-microsoft.md) Você também pode clicar no link Comentários na dica de segurança para enviar comentários diretamente à Microsoft para nos ajudar a melhorar.
