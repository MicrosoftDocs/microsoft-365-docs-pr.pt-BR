---
title: Enviar email criptografado
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
ms.openlocfilehash: e7028f69f4418ae0ff0183653c509fc9ad6171ac
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031226"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>Criptografar ou rotular seus emails confidenciais

Suas informações de dados e de campanha são importantes e freqüentemente confidenciais. Ajude a proteger essas informações confidenciais usando a criptografia e os rótulos de confidencialidade para que você e seus destinatários de email tratem as informações com a confidencialidade exigida.


## <a name="best-practices"></a>Práticas recomendadas

Antes de enviar emails com informações confidenciais ou confidenciais, considere ativar:

- **Criptografia:** Você pode criptografar seu email para proteger a privacidade das informações no email. Quando você criptografa uma mensagem de email, ela é convertida de texto sem formatação legível em texto Cypher embaralhado. Somente o destinatário que tem a chave privada que corresponde à chave pública usada para criptografar a mensagem pode decifrar a mensagem para leitura. No entanto, qualquer destinatário sem a chave privada correspondente vê o texto indecifrável. O administrador pode definir regras para criptografar automaticamente as mensagens que atendem a determinados critérios. Por exemplo, o administrador pode criar uma regra que criptografe todas as mensagens enviadas fora da sua organização ou todas as mensagens que mencionam palavras ou frases específicas. Qualquer regra de criptografia será aplicada automaticamente.
- **Rótulos de sensibilidade:** Sua campanha também pode configurar rótulos de confidencialidade que você pode aplicar aos seus arquivos e email para mantê-los em conformidade com as políticas de proteção de informações da sua campanha. Quando você define um rótulo, o rótulo persiste com seu email, mesmo quando ele é enviado por exemplo, aparecendo como um cabeçalho para sua mensagem.

![Diagrama de um email com textos explicativos para rótulos e criptografia](media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a>Configuração

Se você deseja criptografar uma mensagem que não atende a uma regra predefinida ou seu administrador não configurou nenhuma regra, você pode aplicar uma variedade de regras de criptografia diferentes antes de enviar a mensagem. Para enviar uma mensagem criptografada do Outlook 2013 ou 2016 ou do Outlook 2016 para Mac, selecione **opções > permissões**e, em seguida, selecione a opção de proteção necessária. Você também pode enviar uma mensagem criptografada selecionando o botão **proteger** no Outlook na Web. Para obter mais informações, consulte [enviar, exibir e responder a mensagens criptografadas no Outlook para PC](https://support.office.com/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-US&rs=en-US&ad=US).

## <a name="admin-settings"></a>Configurações de administrador

Você pode aprender tudo sobre como configurar a criptografia de email em [criptografia de email no Office 365](https://docs.microsoft.com/office365/securitycompliance/email-encryption).

### <a name="automatically-encrypt-email-messages"></a>Criptografar mensagens de email automaticamente

Os administradores podem criar regras de fluxo de email para proteger automaticamente as mensagens de email enviadas e recebidas de sua campanha. Configurar regras para criptografar qualquer mensagem de email de saída e remover a criptografia de mensagens criptografadas de dentro da sua organização ou de respostas para mensagens criptografadas enviadas da sua organização. 

Você cria regras de fluxo de email para criptografar mensagens de email com os novos recursos de criptografia de mensagens do Office 365 (OME). Definir regras de fluxo de email para acionar a criptografia de mensagens com os novos recursos do OME usando o centro de administração do Exchange (Eat). 

1. Em um navegador da Web, usando uma conta corporativa ou de estudante que recebeu permissões de administrador global, entre no Office 365. 
2. Escolha o bloco administrador. 
3. No centro de administração, escolha **centros de administração > Exchange**. 

Para obter mais informações, consulte [definir regras de fluxo de email para criptografar mensagens de email no Office 365](https://docs.microsoft.com/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email).

### <a name="brand-your-encryption-messages"></a>Marcar suas mensagens de criptografia

Você também pode aplicar a sua marca de campanha para personalizar a aparência e o texto nas mensagens de email. Para obter mais informações, consulte [Adicionar a marca da sua organização às mensagens criptografadas](https://docs.microsoft.com/office365/securitycompliance/email-encryption).

