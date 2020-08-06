---
title: Novos domínios sendo encaminhados informações sobre email
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Os administradores podem aprender a usar os novos domínios que estão sendo encaminhados para o centro de administração do Exchange para investigar quando os usuários de sua organização estão encaminhando mensagens para domínios externos que nunca foram encaminhadas para o.
ms.openlocfilehash: 81a596d48696f28d62d68594f27081435487d17f
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578353"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Novos domínios que estão sendo encaminhados informações de email no centro de conformidade e segurança &

Embora você possa ter motivos comerciais válidos para encaminhar mensagens de email para destinatários externos em domínios específicos, é suspeito quando os usuários em sua organização começam a encaminhar mensagens para domínios externos, e ninguém já encaminharia mensagens para esses domínios antes (novos domínios). Essa condição pode indicar que as contas de usuário estão comprometidas. Se você suspeitar que as contas foram comprometidas, confira [responder a uma conta de email comprometida](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).

Os **novos domínios que estão sendo encaminhados** informações de email notifica você quando os usuários da sua organização estão encaminhando mensagens para novos domínios.

Essa percepção aparece somente quando o problema é detectado e aparece na página de [relatório de encaminhamento](view-mail-flow-reports.md#forwarding-report) .

![Novos domínios sendo encaminhados informações sobre email](../../media/mfi-new-domains-being-forwarded.png)

Quando você clica no widget, um submenu aparece onde você pode encontrar mais detalhes sobre as mensagens encaminhadas, incluindo um link de volta para o [relatório de encaminhamento](view-mail-flow-reports.md#forwarding-report).

![Submenu de detalhes que aparece depois de clicar nos novos domínios que estão sendo encaminhados informações de email](../../media/mfi-new-domains-being-forwarded-details.png)

Você também pode acessar essa página de detalhes ao selecionar a percepção depois de clicar em **Exibir tudo** na área de **recomendações de & principais** em (painel de**relatórios** \> **Dashboard** ou <https://protection.office.com/insightdashboard> ).

Para impedir o encaminhamento automático de mensagens para domínios externos, configure um domínio remoto para alguns ou todos os domínios externos. Para obter mais informações, consulte [gerenciar domínios remotos no Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).

## <a name="related-topics"></a>Tópicos relacionados

Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).
