---
title: Definir uma data de vencimento para o email criptografado, a Criptografia de Mensagem Avançada do Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Com os recursos avançados de criptografia de mensagens do Office 365 na parte superior da criptografia de mensagens do Office 365 (OME), você pode estender sua segurança de email Configurando uma data de validade por emails por meio de um modelo personalizado com marca.
ms.openlocfilehash: 59e014a69214c8085ad248ad1c1a0c21142abd47
ms.sourcegitcommit: 27a7a373ca77375fdab0690a899135fad16c3cf5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435535"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Definir uma data de vencimento para o email criptografado, a Criptografia de Mensagem Avançada do Office 365

O Office 365 Advanced Message Encryption está incluído no [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 e5, Microsoft 365 E5 (precificação de pessoas sem fins lucrativos), Office 365 Enterprise E5 (precificação de pessoas sem fins lucrativos) e Office 365 Education a5. Se sua organização tem uma assinatura que não inclui a criptografia de mensagem avançada do Office 365, você pode comprá-la com o complemento de SKU de conformidade da Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (precificação de pessoas sem fins lucrativos) ou o Office 365 Advanced Complemento de SKU de conformidade para o Microsoft 365 E3, Microsoft 365 E3 (preço de equipe sem fins lucrativos) ou SKUs do Office 365.

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

- [Criptografia de Mensagem Avançada do 365 Office](ome-advanced-message-encryption.md)

- [Revogar email criptografado pelo a Criptografia de Mensagem Avançada do Office 365](revoke-ome-encrypted-mail.md)

- [Descrição do serviço de conformidade e política de mensagens](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
