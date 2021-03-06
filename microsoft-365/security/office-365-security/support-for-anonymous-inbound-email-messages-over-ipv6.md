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
description: O administrador pode aprender a configurar o suporte para emails de entrada anônimos de fontes IPv6 em Exchange Online e Proteção do Exchange Online.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80fdcc9dcfe3006ef8b21aa19856fe8c0ea3ff70
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300044"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Adicione suporte para email de entrada anônimo por IPv6 no Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 com caixas de correio Exchange Online e organizações de Proteção do Exchange Online (EOP) autônomas sem Exchange Online de correio suportam emails de entrada anônimos por meio do IPv6. O servidor de email IPv6 de origem deve atender a ambos os seguintes requisitos:

- O endereço IPv6 de origem deve ter um registro válido de busca de DNS reverso (PTR) que permita ao destino encontrar o nome de domínio do endereço IPv6.

- O remetente deve passar por verificação SPF (definida na [RFC 7208](https://tools.ietf.org/html/rfc7208)) ou [verificação DKIM](http://dkim.org/) (definida na [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).

Para que sua organização possa receber emails de entrada anônimos pelo IPv6, um administrador precisa entrar em contato com o suporte da Microsoft e solicitar. Para obter instruções sobre como abrir uma solicitação de suporte, consulte [Contact support for business products - Admin Help](../../business-video/get-help-support.md).

Depois que o suporte à mensagem IPv6 de entrada anônima for habilitado em sua organização, a mensagem passará pela filtragem normal de mensagens fornecida pelo serviço.

## <a name="troubleshooting"></a>Solução de problemas

- Se o servidor de email de origem não tiver um registro de pesquisa DNS reverso IPv6, as mensagens serão rejeitadas com o seguinte erro:

  > 450 4.7.25 O serviço indisponível, o envio do endereço IPv6 [2a01:111:f200:2004::240] deve ter o registro DNS reverso.

- Se o remetente não passar na validação SPF ou DKIM, as mensagens serão rejeitadas com o seguinte erro:

  > 450 4.7.26 Serviço indisponível, mensagem enviada por IPv6 [2a01:111:f200:2004::240] deve passar na validação SPF ou DKIM.

- Se você tentar receber mensagens IPv6 anônimas antes de ter optado, a mensagem será rejeitada com o seguinte erro:

  > 550 5.2.1 Serviço indisponível, [contoso.com] não aceita email por IPv6.

## <a name="related-topics"></a>Tópicos relacionados

[Suporte para validação de mensagens assinadas por DKIM](support-for-validation-of-dkim-signed-messages.md)
