---
title: Email de visão geral sobre novos domínios encaminhados
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Os administradores podem aprender a usar os novos domínios que estão sendo encaminhados para a percepção de email no painel de fluxo de emails no centro de conformidade de & de segurança para investigar quando seus usuários estão encaminhando mensagens para domínios externos que nunca foram encaminhadas para o.
ms.openlocfilehash: a72ffd001ea22972d9dc6c00af8a4dd7881386b7
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356938"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Novos domínios que estão sendo encaminhados informações de email no centro de conformidade e segurança &

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Há motivos comerciais válidos para encaminhar mensagens de email para destinatários externos em domínios específicos. No entanto, é suspeito quando os usuários em sua organização começam a encaminhar mensagens para um domínio em que ninguém em sua organização tenha encaminhado mensagens para (um novo domínio).

Essa condição pode indicar que as contas de usuário estão comprometidas. Se você suspeitar que as contas foram comprometidas, confira [responder a uma conta de email comprometida](responding-to-a-compromised-email-account.md).

Os **novos domínios que estão sendo encaminhados** informações de email no [centro de conformidade e segurança &](https://protection.office.com) o notifica quando os usuários de sua organização estão encaminhando mensagens para novos domínios.

Essa percepção aparece somente quando o problema é detectado e aparece na página de [relatório de encaminhamento](view-mail-flow-reports.md#forwarding-report) .

![Email de visão geral sobre novos domínios encaminhados](../../media/mfi-new-domains-being-forwarded.png)

Quando você clica no widget, um submenu aparece onde você pode encontrar mais detalhes sobre as mensagens encaminhadas, incluindo um link de volta para o [relatório de encaminhamento](view-mail-flow-reports.md#forwarding-report).

![Submenu de detalhes que aparece depois de clicar nos novos domínios que estão sendo encaminhados informações de email](../../media/mfi-new-domains-being-forwarded-details.png)

Você também pode acessar essa página de detalhes ao selecionar a percepção depois de clicar em **Exibir tudo** na área de **recomendações de & principais** em (painel de **relatórios** \> **Dashboard** ou <https://protection.office.com/insightdashboard> ).

Para impedir o encaminhamento automático de mensagens para domínios externos, configure um domínio remoto para alguns ou todos os domínios externos. Para obter mais informações, consulte [gerenciar domínios remotos no Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).

## <a name="related-topics"></a>Tópicos relacionados

Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).
