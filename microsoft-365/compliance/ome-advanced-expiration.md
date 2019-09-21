---
title: Definir uma data de expiração para email criptografado pela criptografia de mensagem avançada do Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: Com os recursos avançados de criptografia de mensagens do Office 365 na parte superior da criptografia de mensagens do Office 365 (OME), você pode estender sua segurança de email Configurando uma data de validade por emails por meio de um modelo personalizado com marca.
ms.openlocfilehash: 7c4ad1fb4a91bd62569edc5db9042dfbd2dbd9fe
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073445"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Definir uma data de expiração para email criptografado pela criptografia de mensagem avançada do Office 365

A criptografia de mensagem avançada do Office 365 está disponível na parte superior da criptografia de mensagem do Office 365 em determinadas assinaturas. A criptografia avançada de mensagens está incluída no [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), no Office 365 Enterprise E5 e no Office 365 Education a5. Se sua organização tiver uma assinatura do Office 365 que não inclua a criptografia de mensagem avançada do Office 365, você poderá comprar a criptografia de mensagem avançada como um complemento com a conformidade E5 do SKU de conformidade avançada.

Você pode usar a expiração de mensagens em emails enviados por seus usuários para destinatários externos que usam o portal do OME para acessar emails criptografados. Você força os destinatários a usar o portal do OME para exibir e responder a emails criptografados enviados pela sua organização usando um modelo personalizado com marca que especifica uma data de expiração no Windows PowerShell.

Como administrador global do O365, quando você aplica a marca da empresa para personalizar a aparência das mensagens de email da sua organização do Office 365, você também pode especificar uma expiração para essas mensagens de email. Com a criptografia de mensagem avançada do Office 365, você pode criar vários modelos para emails criptografados originados em sua organização. Usando um modelo, você pode controlar por quanto tempo os destinatários têm acesso a emails enviados por seus usuários.

Quando um usuário final recebe emails com uma data de expiração definida, o usuário vê a data de expiração no email de conteúdo adicional. Se um usuário tentar abrir um email expirado, um erro aparecerá no portal do OME.

Você só pode definir datas de expiração para emails para destinatários externos.

Com a criptografia de mensagem avançada do Office 365, sempre que você aplicar a identidade visual personalizada, o Office 365 aplica o wrapper a emails que se ajustam à regra de fluxo de emails para a qual você aplica o modelo. Além disso, você só poderá usar a expiração se usar identidade visual personalizada.

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>Criar um modelo de identidade visual personalizado para forçar a expiração de email usando o PowerShell

1. [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) com uma conta que tenha permissões de administrador global em sua organização do Office 365.

2. Execute o cmdlet New-OMEConfiguration.

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

Onde:

- `Identity`é o nome do modelo personalizado.

- `ExternalMailExpiryInDays`Identifica o número de dias que os destinatários podem manter os emails antes de expirarem. Você pode usar qualquer valor entre 1 a 730 dias.

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Mais informações sobre a criptografia de mensagem avançada do Office 365

- [Criptografia de mensagem avançada do Office 365](ome-advanced-message-encryption.md)

- [Revogar emails criptografados pela criptografia de mensagem avançada do Office 365](revoke-ome-encrypted-mail.md)

- [Descrição do serviço de conformidade e política de mensagens](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
