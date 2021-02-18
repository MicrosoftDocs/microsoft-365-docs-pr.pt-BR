---
title: Visão geral do status do fluxo de emails do domínio no painel Fluxo de emails
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o insight de & status de fluxo de emails de domínio superior no painel Fluxo de emails no Centro de Conformidade e Segurança para solucionar problemas de fluxo de emails relacionados a seus registros MX.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9ecda78047384a581a1043d0049b8dd25fadbe27
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290616"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Principais informações sobre o status do fluxo de emails do domínio no Centro de Conformidade e & Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Os principais insights de status [](mail-flow-insights-v2.md) **do** fluxo de emails do domínio no painel Fluxo de emails [no](https://protection.office.com) Centro de Conformidade e Segurança & o status atual do fluxo de emails da sua organização.

Esse insight ajuda a identificar e solucionar problemas de domínios que estão enfrentando ***problemas de fluxo de*** emails. Por exemplo, o domínio não pode receber emails externos porque o domínio expirou ou o domínio tem um registro MX incorreto.

![Principal widget de status de fluxo de domínio no painel Fluxo de emails no Centro de Conformidade e Segurança & Segurança](../../media/mfi-top-domain-mail-flow-status-widget.png)

Quando você clica **em Exibir detalhes** no widget, um **flyout de status** do Domínio é exibido, que mostra mais detalhes sobre o status de cada domínio:

- **Domínio**
- **Registro MX anterior**
- **Registro MX atual**
- **Status de recebimento de email**
- **Status** do domínio: Uma marca de seleção verde indica que o registro MX atual (no momento em que você clicou no widget) corresponde ao valor que temos no registro, e o domínio recebeu emails durante as últimas duas horas.

  Um X vermelho indica que o registro MX foi alterado e que o domínio não recebeu emails durante as últimas 6 horas. Isso provavelmente indica que seu domínio expirou ou que o registro MX foi atualizado incorretamente. Verifique com seu registrador de domínio ou serviço de hospedagem DNS para ver se o domínio expirou ou se o registro MX do domínio está incorreto.

Você pode clicar **em Exibir mais** para ver as mesmas informações para mais domínios.

![Detalhes do flyout no insight de status de fluxo de emails do domínio superior](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>Confira também

Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)
