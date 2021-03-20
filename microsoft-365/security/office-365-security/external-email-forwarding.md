---
title: Configurando e controlando o encaminhamento de email externo, encaminhamento automático, Acesso Negado 5.7.520, desabilitação do encaminhamento externo, Seu administrador desabilitou o encaminhamento externo, a política anti-spam de saída
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4614fc9661c892457800b70e2f04f577b418b417
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910769"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Controlar o encaminhamento automático de email externo no Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Como administrador, você pode ter requisitos da empresa para restringir ou controlar mensagens encaminhadas automaticamente para destinatários externos (destinatários fora da sua organização). O encaminhamento de email pode ser útil, mas também pode representar um risco de segurança devido à divulgação potencial de informações. Os invasores podem usar essas informações para atacar sua organização ou parceiros.


Os seguintes tipos de encaminhamento automático estão disponíveis no Microsoft 365:

- Os usuários podem configurar [regras de Caixa de](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) Entrada para encaminhar automaticamente mensagens para os envios externos (deliberadamente ou como resultado de uma conta comprometida).

- Os administradores podem configurar o [encaminhamento de caixa](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) de correio (também conhecido como encaminhamento _SMTP_) para encaminhar automaticamente mensagens para destinatários externos. O administrador pode escolher se deve simplesmente encaminhar mensagens ou manter cópias de mensagens encaminhadas na caixa de correio.

Você pode usar políticas de filtro de spam de saída para controlar o encaminhamento automático para destinatários externos. Três configurações estão disponíveis:

- **Automático**: o encaminhamento externo automático está bloqueado. O encaminhamento automático interno das mensagens continuará a funcionar. Esta é a configuração padrão.
- **On**: O encaminhamento externo automático é permitido e não restrito.
- **Desativado**: o encaminhamento externo automático está desabilitado e resultará em um relatório de não entrega (também conhecido como NDR ou mensagem de rejeição) para o remetente.

Para obter instruções sobre como configurar essas configurações, consulte [Configure outbound spam filtering in EOP](configure-the-outbound-spam-policy.md).

> [!NOTE]
>
> - Desabilitar o encaminhamento automático desabilita quaisquer regras de Caixa de Entrada (usuários) ou encaminhamento de caixa de correio (administradores) que redirecionam mensagens para endereços externos.
>
> - O encaminhamento automático de mensagens entre usuários internos não é afetado pelas configurações nas políticas de filtro de spam de saída.
>
> - Você pode ver informações sobre usuários que estão encaminhando mensagens automaticamente para destinatários externos no relatório mensagens [encaminhadas automaticamente.](mfi-auto-forwarded-messages-report.md)

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>Como as configurações de política de filtro de spam de saída funcionam com outros controles automáticos de encaminhamento de email

Como administrador, você pode já ter configurado outros controles para permitir ou bloquear o encaminhamento automático de email. Por exemplo:

- [Domínios remotos](/exchange/mail-flow-best-practices/remote-domains/remote-domains) para permitir ou bloquear o encaminhamento automático de email para alguns ou todos os domínios externos.

- Condições e ações nas regras de fluxo de [emails](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) do Exchange (também conhecidas como regras de transporte) para detectar e bloquear mensagens encaminhadas automaticamente para destinatários externos.

As configurações de domínio remoto e as regras de fluxo de email são independentes das configurações nas políticas de filtro de spam de saída. Por exemplo:

- Você permite o encaminhamento automático para um domínio remoto, mas bloqueia o encaminhamento automático em políticas de filtro de spam de saída. Neste exemplo, as mensagens encaminhadas automaticamente são bloqueadas.

- Você permite o encaminhamento automático em políticas de filtro de spam de saída, mas usa regras de fluxo de emails ou configurações de domínio remoto para bloquear emails encaminhados automaticamente. Neste exemplo, as regras de fluxo de emails ou as configurações de domínio remoto bloquearão automaticamente as mensagens encaminhadas.

Essa independência de recursos permite que você (por exemplo) permita o encaminhamento automático em políticas de filtro de spam de saída, mas use domínios remotos para controlar os domínios externos para os que os usuários podem encaminhar mensagens.

## <a name="blocked-email-forwarding-messages"></a>Mensagens de encaminhamento de email bloqueadas

Quando uma mensagem é detectada como encaminhada automaticamente  e a política de filtro de [spam](configure-the-outbound-spam-policy.md) de saída bloqueia essa atividade, a mensagem é retornada ao remetente em uma NDR que contém as seguintes informações:

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`