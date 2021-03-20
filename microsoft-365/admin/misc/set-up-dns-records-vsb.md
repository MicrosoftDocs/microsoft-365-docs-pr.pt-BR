---
title: Conectar seu domínio ao Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Aprenda a verificar seu domínio e criar registros DNS com o Microsoft 365.
ms.custom:
- AdminSurgePortfolio
ms.openlocfilehash: 506ee887edbc59956aee11059a7085bc4b22624e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914589"
---
# <a name="connect-your-domain-to-microsoft-365"></a>Conectar seu domínio ao Microsoft 365

> [!NOTE]
> Se você não adicionar um domínio, as pessoas da sua organização usarão o domínio onmicrosoft.com para os endereços de email deles até que você o faça. É importante adicionar seu domínio antes de adicionar usuários, para que você não precise configurá-los duas vezes.

[Verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml) se você não encontrar o que está procurando abaixo.

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Adicione um registro MX para que o email do domínio vá para a Microsoft.

Você obterá informações sobre o registro MX no assistente de configuração de domínio do centro de administração.

No site do provedor de hospedagem, crie um novo registro MX.
Verifique se os campos estão definidos para os seguintes valores:

- Tipo de Registro: `MX`
- Prioridade: definir para o maior valor disponível, geralmente `0`.
- Nome do Host: `@`
- Pontos de endereçamento: copie o valor do centro de administração e cole-o aqui.
- TTL: `3600‎` (ou seu provedor padrão)

Salve o registro e remova todos os outros registros MX.

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a>Adicionar um registro CNAME para conectar os usuários às suas caixas de correio
Você obterá informações sobre os registros CNAME no assistente de configuração de domínio do centro de administração.

No site do seu provedor de hospedagem, adicione o registro CNAME a seguir. Verifique se os campos estão definidos para os seguintes valores para cada:

- Tipo de Registro: `CNAME (Alias)`
- Host: cole os valores copiados do centro de administração aqui.
- Pontos de endereçamento: copie o valor do centro de administração e cole-o aqui.
- TTL: `3600‎` (ou seu provedor padrão)

## <a name="add-a-txt-record-to-help-prevent-spam"></a>Adicionar o registro TXT à SPF para ajudar a evitar spam de e-mail
**Antes de começar:** se você já possui um registro SPF para seu domínio, não crie um novo para o Microsoft 365. Em vez disso, adicione os valores necessários do Microsoft 365 ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.

No site do seu host DNS, edite o registro SPF existente ou crie um.
Verifique se os campos estão definidos para os seguintes valores:

- Tipo de Registro: `TXT (Text)`
- Host: `@`
- Valor do TXT: `v=spf1 include:spf.protection.outlook.com -all`
- TTL: `3600‎` (ou seu provedor padrão)

Salve o registro.

Valide seu registro SPF usando uma destas [ferramentas de validação de SPF](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).

O SPF foi projetado para ajudar a evitar a falsificação, mas há técnicas de falsificação contra as quais o SPF não pode protegê-lo. Para se proteger contra isso, depois de configurar o SPF, você também deve configurar o DKIM e o DMARC para o Microsoft 365.

Para começar, consulte [Usar DKIM para validar emails de saída enviados do seu domínio no Microsoft 365](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) e [Usar DMARC para validar emails no Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).

Por fim, volte para o assistente de configuração de domínio do centro de administração para concluir a configuração.