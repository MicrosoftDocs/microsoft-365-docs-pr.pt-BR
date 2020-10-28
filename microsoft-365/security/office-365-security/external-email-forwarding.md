---
title: Configurando e controlando o encaminhamento de emails externos, encaminhamento automático, acesso de 5.7.520 negado, desabilitar o encaminhamento externo, o administrador desabilitou o encaminhamento externo, política antispam de saída
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: dff2ea4e144f8f8fcc0f42732141e110effe7e9e
ms.sourcegitcommit: 45c0afcf958069c5c1b31f9b6c762d8dd806e1e9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48774088"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Controlar o encaminhamento de email externo automático no Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Como administrador, você pode ter requisitos da empresa para restringir ou controlar mensagens encaminhadas automaticamente para destinatários externos (destinatários fora da sua organização). O encaminhamento de emails pode ser útil, mas também pode representar um risco de segurança devido à possível divulgação de informações. Os invasores podem usar essas informações para atacar sua organização ou seus parceiros.

Os seguintes tipos de encaminhamento automático estão disponíveis no Microsoft 365:

- Os usuários podem configurar [regras de caixa de entrada](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) para encaminhar mensagens automaticamente para remetentes externos (deliberadamente ou como resultado de uma conta comprometida).

- Os administradores podem configurar o [encaminhamento de caixa de correio](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (também conhecido como encaminhamento SMTP) para encaminhar mensagens automaticamente para destinatários externos.

Você pode usar as políticas de filtro de spam de saída para controlar o encaminhamento automático para destinatários externos. Três configurações estão disponíveis:

- **Automático** : o encaminhamento externo automático está bloqueado. O encaminhamento automático de mensagens interno continuará funcionando. Esta é a configuração padrão.

- **Ativado** : o encaminhamento externo automático é permitido e não é restrito.

- **Off** : o encaminhamento externo automático está desabilitado e resultará em uma notificação de falha na entrega (também conhecida como NDR ou mensagem de devolução) para o remetente.

Para obter instruções sobre como definir essas configurações, consulte [Configure Outbound spam Filtering in EOP](configure-the-outbound-spam-policy.md).

> [!NOTE]
> 
> - Desabilitar o encaminhamento automático também desabilitará as regras de caixa de entrada que redirecionam mensagens para endereços externos.
> 
>   O Office 365 não permite o encaminhamento externo automático por regras de caixa de entrada ou configuração de caixa de correio, que fornece uma política padrão segura. No entanto, o administrador pode modificar essas configurações para todos ou alguns usuários da organização. Criar [políticas de spam de saída](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true#use-the-security--compliance-center-to-create-outbound-spam-policies) e modificar a seção de encaminhamento automático para controlar o encaminhamento automático de emails por usuários para remetentes externos. Isso pode ser aplicado posteriormente aos remetentes internos aos quais a política se aplica. O encaminhamento de mensagens entre usuários internos não é afetado por tal modificação.
> 
> - Você pode ver informações sobre os usuários que estão encaminhando mensagens automaticamente para destinatários externos no [relatório de mensagens de encaminhamento automático](mfi-auto-forwarded-messages-report.md).

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>Como as configurações da política de filtro de spam de saída funcionam com outros controles de encaminhamento automáticos de email

Como administrador, você já deve ter configurado outros controles para permitir ou bloquear o encaminhamento automático de emails. Por exemplo:

- [Domínios remotos](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) para permitir ou bloquear o encaminhamento automático de emails para alguns ou todos os domínios externos.

- Condições e ações nas [regras de fluxo de emails](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) do Exchange (também conhecidas como regras de transporte) para detectar e bloquear automaticamente mensagens encaminhadas para destinatários externos.

As regras de domínio remoto e de fluxo de emails são independentes das configurações nas políticas de filtro de spam de saída. Por exemplo:

- Você permite o encaminhamento automático para um domínio remoto, mas bloqueia o encaminhamento automático em políticas de filtro de spam de saída. Neste exemplo, as mensagens encaminhadas automaticamente são bloqueadas.

- Você permite o encaminhamento automático em políticas de filtro de spam de saída, mas usa regras de fluxo de emails ou configurações de domínio remoto para bloquear emails encaminhados automaticamente. Neste exemplo, as regras de fluxo de email ou as configurações de domínio remoto bloquearão mensagens automaticamente encaminhadas.

Essa independência de recurso permite que você (por exemplo) permita o encaminhamento automático em políticas de filtro de spam de saída, mas use domínios remotos para controlar os domínios externos aos quais os usuários podem encaminhar mensagens.

## <a name="the-blocked-email-forwarding-message"></a>A mensagem de encaminhamento de email bloqueado

Quando uma mensagem é detectada como encaminhada automaticamente e a política organizacional *bloqueia* essa atividade, a mensagem é retornada ao remetente em uma notificação de falha na entrega que contém as seguintes informações:

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
