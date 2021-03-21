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
description: Use a Criptografia Avançada de Mensagens do Office 365 para estender sua segurança de email definindo uma data de expiração em emails por meio de um modelo de marca personalizada.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f936ffa62f31e47f51fc1bcb2765195b0ea809af
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927781"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Definir uma data de vencimento para o email criptografado pela Criptografia de Mensagem Avançada do Office 365

A Criptografia Avançada de Mensagens do Office 365 está incluída no [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), no Office 365 E5, no Microsoft 365 E5 (Preços de Funcionários sem fins lucrativos), no Office 365 Enterprise E5 (Preços de Funcionários sem fins lucrativos) e no Office 365 Education A5. Se sua organização tiver uma assinatura que não inclua a Criptografia Avançada de Mensagens do Office 365, você pode compra-lo com o complemento SKU de Conformidade do Microsoft 365 E5 para o Microsoft 365 E3, o Microsoft 365 E3 (Preços de Equipe sem fins lucrativos) ou o complemento SKU de Conformidade Avançada do Office 365 para o Microsoft 365 E3, o Microsoft 365 E3 (Preços da Equipe Sem Fins Lucrativos) ou o SKUs do Office 365.

Você pode usar a expiração de mensagens nos emails que seus usuários enviam para destinatários externos que usam o Portal OME para acessar emails criptografados. Você força os destinatários a usar o portal OME para exibir e responder a emails criptografados enviados por sua organização usando um modelo de marca personalizado que especifica uma data de expiração no Windows PowerShell.

Como administrador global do Office 365, ao aplicar sua marca da empresa para personalizar a aparência das mensagens de email da sua organização, você também pode especificar uma expiração para essas mensagens de email. Com a Criptografia Avançada de Mensagens do Office 365, você pode criar vários modelos para emails criptografados que se originam da sua organização. Usando um modelo, você pode controlar por quanto tempo os destinatários têm acesso aos emails enviados por seus usuários.

Quando um usuário final recebe emails com uma data de expiração definida, o usuário vê a data de expiração no email do wrapper. Se um usuário tentar abrir um email expirado, aparecerá um erro no portal OME.

Você só pode definir datas de expiração para emails para destinatários externos.

Com a Criptografia avançada de Mensagens do Office 365, sempre que você aplica a identidade visual personalizada, o Office 365 aplica o wrapper a emails que se ajustam à regra de fluxo de emails à qual você aplica o modelo. Além disso, você só poderá usar a expiração se usar a identidade visual personalizada.

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>Criar um modelo de identidade visual personalizado para forçar a expiração de email usando o PowerShell

1. [Conecte-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) com uma conta que tenha permissões globais de administrador em sua organização.

2. Execute o cmdlet New-OMEConfiguration.

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

Onde:

- `Identity` é o nome do modelo personalizado.

- `ExternalMailExpiryInDays` identifica o número de dias em que os destinatários podem manter emails antes de expirar. Você pode usar qualquer valor entre 1 e 730 dias.

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Mais informações sobre a Criptografia Avançada de Mensagens do Office 365

- [Criptografia de Mensagem Avançada do 365 Office](ome-advanced-message-encryption.md)

- [Revogar email criptografado pelo a Criptografia de Mensagem Avançada do Office 365](revoke-ome-encrypted-mail.md)

- [Descrição do serviço de conformidade e política de mensagem](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)