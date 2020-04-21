---
title: Adicionar suporte para mensagens anônimas de e-mail de entrada por IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: O administrador pode saber como configurar o suporte para emails de entrada anônimos de fontes IPv6 no Exchange Online e no Exchange Online Protection.
ms.openlocfilehash: 86de431f8f46af1c5ddae8ecc91f326c6e3280e6
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631212"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Adicionar suporte para email de entrada anônimo por IPv6 no Microsoft 365

As organizações do Microsoft 365 com caixas de correio do Exchange Online e proteção autônoma do Exchange Online (EOP) sem caixas de correio do Exchange Online dão suporte a emails de entrada anônimos por IPv6. O servidor de email IPv6 de origem deve cumprir os seguintes requisitos:

- O endereço IPv6 de origem deve ter um registro de pesquisa de DNS reverso válido que permite que o destino encontre o nome de domínio do endereço IPv6.

- O remetente deve passar por verificação SPF (definida na [RFC 7208](https://tools.ietf.org/html/rfc7208)) ou [verificação DKIM](https://dkim.org/) (definida na [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).

Antes que sua organização possa receber emails de entrada anônimos por IPv6, um administrador precisa entrar em contato com o suporte da Microsoft e solicitá-lo. Para obter instruções sobre como abrir uma solicitação de suporte, consulte [contatar o suporte para produtos de negócios-ajuda para administradores](../../admin/contact-support-for-business-products.md).

Depois que o suporte à mensagem IPv6 de entrada anônima estiver habilitado em sua organização, a mensagem passará pela filtragem de mensagens normal fornecida pelo serviço.

## <a name="troubleshooting"></a>Solução de problemas

- Se o servidor de email de origem não tiver um registro de pesquisa de DNS reverso IPv6, as mensagens serão rejeitadas com o seguinte erro:

  > 450 o serviço 4.7.25 não está disponível, enviando endereço IPv6 [2a01:111: F200: de 2004:: 240] deve ter um registro DNS reverso.

- Se o remetente não passar pela validação SPF ou DKIM, as mensagens serão rejeitadas com o seguinte erro:

  > 450 4.7.26 serviço não disponível, a mensagem enviada por IPv6 [2a01:111: F200:2004:: 240] deve passar pela validação SPF ou DKIM.

- Se você tentar receber mensagens IPv6 anônimas antes de optar por você, a mensagem será rejeitada com o seguinte erro:

  > 550 o serviço 5.2.1 não está disponível, [contoso.com] não aceita emails sobre IPv6.

## <a name="for-more-information"></a>Para obter mais informações

[Suporte para validação de mensagens assinadas por DKIM](support-for-validation-of-dkim-signed-messages.md)