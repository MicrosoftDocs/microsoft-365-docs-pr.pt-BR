---
title: Dicas de segurança para mensagens de email
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/6/2016
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- BCS160
ms.assetid: fb4f8e49-0468-4be2-8fa6-99501f1ad9d5
ms.collection:
- M365-security-compliance
description: Apresenta dicas de segurança para mensagens de email filtradas pelo EOP e pelo filtro de spam.
ms.openlocfilehash: 7171f5855e295ffac931862c86db011c9f38a4c6
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634299"
---
# <a name="safety-tips-in-email-messages"></a>Dicas de segurança para mensagens de email

O Exchange Online Protection (EOP) e o Microsoft 365 protegem você com spam, phishing e prevenção contra malware. Hoje, alguns desses ataques são tão bem criados que parecem legítimos. Enviar mensagens para a pasta lixo eletrônico nem sempre é suficiente. Agora, quando você verificar seu email no Outlook ou no Outlook na Web, o EOP verifica automaticamente o remetente e adiciona uma dica de segurança à parte superior do email.

A dica de segurança — uma mensagem codificada por cores — avisará você sobre mensagens potencialmente prejudiciais. A maioria das mensagens em sua caixa de entrada não terá uma dica de segurança. Você só as verá quando o EOP e o Microsoft 365 tiverem informações necessárias para ajudar a evitar spam, phishing e ataques de malware. Se as dicas de segurança aparecerem em sua caixa de entrada, você poderá usar os exemplos a seguir para saber mais sobre cada tipo de dica de segurança.

- Email suspeito (dica de segurança vermelha).

    ![Captura de tela que mostra uma dica de segurança vermelha.](../../media/5078a0be-e556-44a1-b169-09d780d26898.png)

    Uma dica de segurança vermelha em um email significa que a mensagem recebida contém algo suspeito, como um golpe de phishing. Recomendamos que você exclua esse tipo de mensagem de email da caixa de entrada sem abri-la.

- Spam (dica de segurança amarela).

    ![Captura de tela que mostra uma dica de segurança amarela.](../../media/793c9265-ea44-48fd-a98f-804fadd4163b.png)

    Uma dica de segurança amarela em um email significa que a mensagem foi marcada como spam. Se você não reconhece e confia no remetente da mensagem, não baixe nenhum anexo ou imagem e não clique em nenhum link da mensagem. No Outlook na Web, você pode clicar em **não é spam** na barra amarela de um item de lixo eletrônico para mover a mensagem para sua caixa de entrada. Se a dica de segurança amarela aparecer em uma mensagem que foi entregue na caixa de entrada, é provável que você tenha desabilitado a movimentação de spam para a pasta lixo eletrônico.

- Email seguro (dica de segurança verde).

    ![Captura de tela que mostra uma dica de segurança verde.](../../media/acbc11d0-f626-4848-9fbf-66eeeda3f803.png)

    Além de mensagens não seguras, também Informaremos sobre mensagens válidas de remetentes que confiamos com uma dica de segurança verde. Uma dica de segurança verde em um email significa que verificamos o remetente da mensagem e verificamos se ela é segura. A Microsoft mantém esta lista de remetentes confiáveis que inclui organizações financeiras e outras que são freqüentemente falsificadas ou representadas.

- Emails não filtrados (dica de segurança cinza).

    ![Captura de tela que mostra uma dica de segurança cinza.](../../media/c4d0cf8f-08e9-4c84-beee-1d9e0b022e0a.png)

    Também avisaremos quando ignoramos a verificação de um email porque ele é proveniente de um remetente em sua lista de remetentes confiáveis ou se existe uma regra de fluxo de emails para ignorar a filtragem.

    A dica de segurança cinza também aparece quando imagens externas são bloqueadas, ou seja, a mensagem está na sua caixa de entrada e não parece ser spam, mas contém imagens externas que você não optou por baixar.

## <a name="working-with-safety-tips"></a>Trabalhar com dicas de segurança

As dicas de segurança sempre são habilitadas para o Outlook na Web, mesmo que nem todas as mensagens recebam um. Os administradores podem desativar as dicas de segurança para outros clientes de email, como o Outlook. Para obter mais informações, consulte [Configure as políticas de anti-spam no Office 365](configure-your-spam-filter-policies.md).

Se você discordar do modo como o EOP categorizou uma mensagem (ou seja, a mensagem não é spam ou deveria ter sido marcada como spam), você pode enviar as mensagens para a Microsoft para a análise para ajudar a melhorar sua experiência. Para obter instruções, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md). Você também pode clicar no link de comentários na dica de segurança para enviar comentários diretamente para a Microsoft para nos ajudar a melhorar.
