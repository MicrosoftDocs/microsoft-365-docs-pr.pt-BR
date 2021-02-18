---
title: Adicionar suporte para mensagens anônimas de email de entrada por IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: O administrador pode aprender a configurar o suporte para emails de entrada anônimos de fontes IPv6 no Exchange Online e no Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63c9434fbd1f69c0cbd3145717b712857eb17e28
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290268"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Adicionar suporte para email de entrada anônimo sobre IPv6 no Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

As organizações do Microsoft 365 com caixas de correio do Exchange Online e organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online suportam emails de entrada anônimos por IPv6. O servidor de email IPv6 de origem deve atender a ambos os seguintes requisitos:

- O endereço IPv6 de origem deve ter um registro de busca de DNS reverso (PTR) válido que permita que o destino encontre o nome de domínio do endereço IPv6.

- O remetente deve passar por verificação SPF (definida na [RFC 7208](https://tools.ietf.org/html/rfc7208)) ou [verificação DKIM](http://dkim.org/) (definida na [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).

Para que sua organização possa receber emails de entrada anônimos por IPv6, um administrador precisa entrar em contato com o suporte da Microsoft e solicitar. Para obter instruções sobre como abrir uma solicitação de suporte, consulte Contatar o suporte para produtos comerciais [- Ajuda para Administradores.](../../admin/contact-support-for-business-products.md)

Depois que o suporte a mensagens IPv6 de entrada anônimas for habilitado em sua organização, a mensagem passará pela filtragem de mensagens normal fornecida pelo serviço.

## <a name="troubleshooting"></a>Solução de problemas

- Se o servidor de email de origem não tiver um registro de pesquisa de DNS reverso IPv6, as mensagens serão rejeitadas com o seguinte erro:

  > 450 4.7.25 Serviço indisponível, o envio do endereço IPv6 [2a01:111:f200:2004::240] deve ter um registro DNS reverso.

- Se o remetente não passar na validação SPF ou DKIM, as mensagens serão rejeitadas com o seguinte erro:

  > 450 4.7.26 Serviço indisponível, a mensagem enviada por IPv6 [2a01:111:f200:2004::240] deve passar na validação SPF ou DKIM.

- Se você tentar receber mensagens IPv6 anônimas antes de optar por ela, a mensagem será rejeitada com o seguinte erro:

  > 550 5.2.1 Serviço indisponível, [contoso.com] não aceita email sobre IPv6.

## <a name="related-topics"></a>Tópicos relacionados

[Suporte para validação de mensagens assinadas por DKIM](support-for-validation-of-dkim-signed-messages.md)
