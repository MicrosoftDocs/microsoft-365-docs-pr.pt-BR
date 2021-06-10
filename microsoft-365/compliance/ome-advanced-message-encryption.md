---
title: Criptografia avançada de mensagens
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/16/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: A Criptografia Avançada de Mensagens ajuda as organizações a cumprir suas obrigações de conformidade, permitindo que os administradores faça ainda mais com mensagens protegidas.
ms.openlocfilehash: 8c650c47c1853102e4e2d142040e49724ef707e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923951"
---
# <a name="advanced-message-encryption"></a>Criptografia avançada de mensagens

Criptografia de Mensagem Avançada do Office 365 está incluído no [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Preços de Funcionários sem fins lucrativos), Office 365 Enterprise E5 (Preços de Funcionários sem fins lucrativos) e Office 365 Education A5. Se a sua organização tiver uma assinatura que não inclua o Criptografia de Mensagem Avançada do Office 365, você poderá compre-lo com o complemento SKU do Microsoft 365 E5 Compliance para Microsoft 365 E3, Microsoft 365 E3 (Preços de Funcionários sem fins lucrativos) ou o complemento SKU do Conformidade Avançada do Office 365 para Microsoft 365 E3, Microsoft 365 E3 (Preços de Funcionários sem fins lucrativos), Office 365 SKUs ou informações do Microsoft 365 E5/A5 Complemento SKU de Proteção e Governança para Microsoft 365 A3/E3.

A Criptografia Avançada de Mensagens ajuda os clientes a cumprir obrigações de conformidade que exigem controles mais flexíveis sobre destinatários externos e seu acesso a emails criptografados. Com a Criptografia avançada de Mensagens Office 365, você pode controlar emails confidenciais compartilhados fora da organização com políticas automáticas. Você configura essas políticas para identificar tipos de informações confidenciais, como PII, Finanças ou IDs de Saúde, ou pode usar palavras-chave para aprimorar a proteção. Depois de configurar as políticas, você emparelha as políticas com modelos de email personalizados de marca e, em seguida, adiciona uma data de expiração para controle extra de emails que se ajustam à política. Além disso, os administradores podem controlar ainda mais os emails criptografados acessados externamente por meio de um portal da Web seguro revogando o acesso ao email a qualquer momento.

Você só pode revogar e definir uma data de expiração para emails enviados a destinatários externos.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Começar a Criptografia de Mensagem Avançada do Office 365

Os artigos a seguir descrevem como você configura e usa a Criptografia Avançada de Mensagens.

Sua organização deve ter uma assinatura que inclua Criptografia de Mensagem Avançada do Office 365. Para obter informações detalhadas sobre assinaturas com suporte, consulte a descrição do serviço de conformidade e [política de mensagem.](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)

Se você ainda não tiver Criptografia de Mensagens do Office 365 configuração, consulte [Configurar novos recursos Criptografia de Mensagens do Office 365.](set-up-new-message-encryption-capabilities.md)

Com a Criptografia Avançada de Mensagens, você não está limitado a um único modelo de identidade visual. Em vez disso, você pode criar e usar vários modelos de identidade visual. Para obter informações, [consulte Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).

[Definir uma data de expiração para email criptografado por Criptografia de Mensagem Avançada do Office 365](ome-advanced-expiration.md). Controlar emails confidenciais compartilhados fora da organização com políticas automáticas que aprimoram a proteção expirando o acesso por meio de um portal web seguro para emails criptografados.

[Revogar emails criptografados por Criptografia de Mensagem Avançada do Office 365](revoke-ome-encrypted-mail.md). Controle emails confidenciais compartilhados fora da organização e aprimora a proteção revogando o acesso por meio de um portal da Web seguro para emails criptografados.  

Com Criptografia de Mensagem Avançada do Office 365, sempre que você aplicar um modelo de identidade visual personalizado, a Microsoft aplica um wrapper a emails que se ajustam à regra de fluxo de emails à qual você aplica o modelo. Você só pode revogar mensagens e aplicar datas de expiração a mensagens que os usuários recebem por meio do portal. Em outras palavras, o email que tem um modelo de identidade visual personalizado aplicado. Para obter mais informações e um exemplo, consulte as diretrizes em Garantir que todos os [destinatários externos usem o Portal OME para ler emails criptografados.](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail)