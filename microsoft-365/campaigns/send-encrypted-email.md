---
title: Enviar e-mail criptografado
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Saiba como enviar emails criptografados usando o Outlook.
ms.openlocfilehash: d17abccd645b4dfdf933906dc90175be51f95c9a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044211"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>Criptografe ou rotule emails confidenciais

Seus dados e informações de campanha são importantes e geralmente confidenciais. Ajude a proteger essas informações confidenciais usando rótulos de criptografia e sensibilidade para que você e seus destinatários de email tratem as informações com a sensibilidade necessária.

## <a name="best-practices"></a>Práticas recomendadas

Antes de enviar emails com informações confidenciais ou confidenciais, considere a possibilidade de ligar:

- **Criptografia:** Você pode criptografar seu email para proteger a privacidade das informações no email. Quando você criptografa uma mensagem de email, ela é convertida de texto sem texto sem texto simples aceitável em texto esférico em forma de texto esférico. Somente o destinatário que tem a chave privada que corresponde à chave pública usada para criptografar a mensagem pode descriptar a mensagem para leitura. No entanto, qualquer destinatário sem a chave privada correspondente vê texto indecifrável. O administrador pode definir regras para criptografar automaticamente mensagens que atendem a determinados critérios. Por exemplo, seu administrador pode criar uma regra que criptografa todas as mensagens enviadas fora da sua organização ou todas as mensagens que mencionam palavras ou frases específicas. Todas as regras de criptografia serão aplicadas automaticamente.
- **Rótulos de sensibilidade:** Sua campanha também pode configurar rótulos de sensibilidade que você pode aplicar aos seus arquivos e emails para mantê-los em conformidade com as políticas de proteção de informações da sua campanha. Quando você definir um rótulo, o rótulo persiste com seu email, mesmo quando enviado, por exemplo, aparecendo como um header para sua mensagem.

![Diagrama de um email com explicações para rótulos e criptografia](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a>Configuração

Se você quiser criptografar uma mensagem que não atender a uma regra pré-definida ou se o administrador não tiver definido nenhuma regra, poderá aplicar uma variedade de regras de criptografia diferentes antes de enviar a mensagem. To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need. Você também pode enviar uma mensagem criptografada selecionando o **botão** Proteger no Outlook na Web. For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).

## <a name="admin-settings"></a>Configurações do administrador

Você pode aprender tudo sobre como configurar a criptografia de email na [criptografia de email no Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)

### <a name="automatically-encrypt-email-messages"></a>Criptografar automaticamente mensagens de email

Os administradores podem criar regras de fluxo de emails para proteger automaticamente as mensagens de email enviadas e recebidas de sua campanha. Configurar regras para criptografar qualquer mensagem de email de saída e remover a criptografia de mensagens criptografadas provenientes de dentro da sua organização ou de respostas a mensagens criptografadas enviadas de sua organização.

Você cria regras de fluxo de emails para criptografar mensagens de email com os novos recursos de Criptografia de Mensagens do Office 365 (OME). Defina regras de fluxo de emails para acionar a criptografia de mensagens com os novos recursos do OME usando o Centro de Administração do Exchange (EAC). 

1. Em um navegador da Web, usando uma conta de trabalho ou de estudante que recebeu permissões de administrador global, entre.
2. Escolha o painel Administrador.
3. In the admin center, choose **Admin centers > Exchange**.

Para obter mais informações, consulte [Definir regras de fluxo de emails para criptografar mensagens de email.](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

### <a name="brand-your-encryption-messages"></a>Marca de suas mensagens de criptografia

Você também pode aplicar a identidade visual da campanha para personalizar a aparência e o texto nas mensagens de email. Para obter mais informações, [consulte Adicionar a marca da sua organização às suas mensagens criptografadas.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)
