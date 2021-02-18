---
title: Email de visão geral sobre novos domínios encaminhados
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Os administradores podem aprender a usar os novos domínios que estão sendo encaminhados no painel fluxo de emails no Centro de Conformidade e Segurança para investigar quando seus usuários estão encaminhando mensagens para domínio & s externos para os quais nunca foram encaminhados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fd026b31b7cb678ff1f091579c67a3958b159c09
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289456"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a>Visão dos novos domínios que estão sendo encaminhados no Centro de Conformidade e Segurança & segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Há razões comerciais válidas para encaminhar mensagens de email para destinatários externos em domínios específicos. No entanto, é suspeito quando os usuários em sua organização começam a encaminhar mensagens para um domínio para o qual ninguém em sua organização encaminhou mensagens (um novo domínio).

Essa condição pode indicar que as contas de usuário estão comprometidas. Se você suspeitar que as contas foram comprometidas, confira [Responder a uma conta de email comprometida.](responding-to-a-compromised-email-account.md)

Os **novos domínios que** estão sendo encaminhados no Centro de Conformidade e Segurança & [notifica](https://protection.office.com) quando os usuários em sua organização estão encaminhando mensagens para novos domínios.

Esse insight só aparece quando o problema é detectado e aparece na página [de relatório de encaminhamento.](view-mail-flow-reports.md#forwarding-report)

![Email de visão geral sobre novos domínios encaminhados](../../media/mfi-new-domains-being-forwarded.png)

Quando você clica no widget, um flyout é exibido, onde você pode encontrar mais detalhes sobre as mensagens encaminhadas, incluindo um link de volta para o relatório [de encaminhamento.](view-mail-flow-reports.md#forwarding-report)

![Detalhes do flyout que aparece depois de clicar no insight de email novos domínios que estão sendo encaminhados](../../media/mfi-new-domains-being-forwarded-details.png)

Você também pode acessar **essa** página de detalhes  ao selecionar as informações depois de clicar em Exibir tudo na área De informações principais & recomendações (**Painel** de Relatórios \>  ou <https://protection.office.com/insightdashboard> ).

Para impedir o encaminhamento automático de mensagens para domínios externos, configure um domínio remoto para alguns ou todos os domínios externos. Para obter mais informações, [consulte Gerenciar domínios remotos no Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)

## <a name="related-topics"></a>Tópicos relacionados

Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)
