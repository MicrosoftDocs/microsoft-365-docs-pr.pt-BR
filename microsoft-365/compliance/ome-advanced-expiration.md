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
description: Use a Criptografia de Mensagens Avançada do Office 365 para estender a segurança de email definindo uma data de expiração em emails por meio de um modelo de marca personalizada.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bbd018e55592e5b17149edf1a4dc0907c0184417
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769161"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Definir uma data de vencimento para o email criptografado pela Criptografia de Mensagem Avançada do Office 365

A Criptografia Avançada de Mensagens do Office 365 está incluída no [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)office 365 E5, Microsoft 365 E5 (preços de funcionários sem fins lucrativos), Office 365 Enterprise E5 (preços de funcionários sem fins lucrativos) e Office 365 Education A5. Se sua organização tiver uma assinatura que não inclua a Criptografia de Mensagem Avançada do Office 365, Você pode adéqua-lo com o complemento de SKU de Conformidade do Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (preços de funcionários sem fins lucrativos) ou o complemento SKU de Conformidade Avançada do Office 365 para Microsoft 365 E3, Microsoft 365 E3 (Preços de Funcionários sem Fins Lucrativos) ou SKUs do Office 365.

Você pode usar a expiração de mensagens em emails que seus usuários enviam a destinatários externos que usam o Portal OME para acessar emails criptografados. Você força os destinatários a usar o portal do OME para exibir e responder a emails criptografados enviados por sua organização usando um modelo de marca personalizado que especifica uma data de expiração no Windows PowerShell.

Como administrador global do Office 365, quando você aplica a marca da empresa para personalizar a aparência das mensagens de email da sua organização, também pode especificar uma expiração para essas mensagens de email. Com a Criptografia de Mensagens Avançada do Office 365, você pode criar vários modelos para emails criptografados provenientes da sua organização. Usando um modelo, você pode controlar por quanto tempo os destinatários têm acesso aos emails enviados por seus usuários.

Quando um usuário final recebe emails com uma data de expiração definida, o usuário vê a data de expiração no email do wrapper. Se um usuário tentar abrir um email expirado, um erro aparecerá no portal do OME.

Você só pode definir datas de expiração para emails para destinatários externos.

Com a Criptografia avançada de mensagens do Office 365, sempre que você aplica identidade visual personalizada, o Office 365 aplica o wrapper ao email que se ajusta à regra de fluxo de emails à qual você aplica o modelo. Além disso, você só poderá usar a expiração se usar identidade visual personalizada.

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>Criar um modelo de identidade visual personalizado para forçar a expiração de email usando o PowerShell

1. [Conecte-se ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) com uma conta que tenha permissões de administrador global em sua organização.

2. Execute o New-OMEConfiguration cmdlet.

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

Onde:

- `Identity` é o nome do modelo personalizado.

- `ExternalMailExpiryInDays` identifica o número de dias que os destinatários podem manter os emails antes que eles expirem. É possível usar qualquer valor entre 1 e 730 dias.

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Mais informações sobre a Criptografia de Mensagens Avançada do Office 365

- [Criptografia de Mensagem Avançada do 365 Office](ome-advanced-message-encryption.md)

- [Revogar email criptografado pelo a Criptografia de Mensagem Avançada do Office 365](revoke-ome-encrypted-mail.md)

- [Descrição do serviço de conformidade e política de mensagens](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
