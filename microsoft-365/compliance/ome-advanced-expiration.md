---
title: Definir uma data de vencimento para o email criptografado pela Criptografia de Mensagem Avançada do Office 365
f1.keywords:
- NOCSH
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
description: Use a criptografia de mensagem avançada do Office 365 para estender sua segurança de email Configurando uma data de expiração em emails por meio de um modelo personalizado com marca.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bbd018e55592e5b17149edf1a4dc0907c0184417
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769161"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Definir uma data de vencimento para o email criptografado pela Criptografia de Mensagem Avançada do Office 365

O Office 365 Advanced Message Encryption está incluído no [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 e5, Microsoft 365 E5 (precificação de pessoas sem fins lucrativos), Office 365 Enterprise E5 (precificação de pessoas sem fins lucrativos) e Office 365 Education a5. Se sua organização tem uma assinatura que não inclui a criptografia de mensagem avançada do Office 365, você pode comprá-la com o complemento de SKU de conformidade da Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (preço de equipe sem fins lucrativos) ou o complemento avançado de SKU de conformidade avançada do Office para a Microsoft 365 E3, Microsoft 365 E3

Você pode usar a expiração de mensagens em emails enviados por seus usuários para destinatários externos que usam o portal do OME para acessar emails criptografados. Você força os destinatários a usar o portal do OME para exibir e responder a emails criptografados enviados pela sua organização usando um modelo personalizado com marca que especifica uma data de expiração no Windows PowerShell.

Como administrador global do Office 365, ao aplicar a marca da empresa para personalizar a aparência das mensagens de email da sua organização, você também pode especificar uma expiração para essas mensagens de email. Com a criptografia de mensagem avançada do Office 365, você pode criar vários modelos para emails criptografados originados em sua organização. Usando um modelo, você pode controlar por quanto tempo os destinatários têm acesso a emails enviados por seus usuários.

Quando um usuário final recebe emails com uma data de expiração definida, o usuário vê a data de expiração no email de conteúdo adicional. Se um usuário tentar abrir um email expirado, um erro aparecerá no portal do OME.

Você só pode definir datas de expiração para emails para destinatários externos.

Com a criptografia de mensagem avançada do Office 365, sempre que você aplicar a identidade visual personalizada, o Office 365 aplica o wrapper a emails que se ajustam à regra de fluxo de emails para a qual você aplica o modelo. Além disso, você só poderá usar a expiração se usar identidade visual personalizada.

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>Criar um modelo de identidade visual personalizado para forçar a expiração de email usando o PowerShell

1. [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) com uma conta que tenha permissões de administrador global em sua organização.

2. Execute o cmdlet New-OMEConfiguration.

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

Onde:

- `Identity` é o nome do modelo personalizado.

- `ExternalMailExpiryInDays` Identifica o número de dias que os destinatários podem manter os emails antes de expirarem. Você pode usar qualquer valor entre 1 a 730 dias.

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Mais informações sobre a criptografia de mensagem avançada do Office 365

- [Criptografia de Mensagem Avançada do 365 Office](ome-advanced-message-encryption.md)

- [Revogar email criptografado pelo a Criptografia de Mensagem Avançada do Office 365](revoke-ome-encrypted-mail.md)

- [Descrição do serviço de conformidade e política de mensagens](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
