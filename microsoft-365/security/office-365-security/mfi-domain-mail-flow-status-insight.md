---
title: Visão geral do status do fluxo de email de domínio superior no painel de fluxo de emails
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar a visão superior do status do fluxo de emails do domínio no painel de fluxo de emails no centro de conformidade de & de segurança para solucionar problemas de fluxo de emails relacionados a seus registros MX.
ms.openlocfilehash: 0d750ab4dbe5875796118086fae1d9119dc486f0
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920579"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Visão geral do status do fluxo de email de domínio superior no centro de conformidade e segurança &

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


A **parte superior do status do fluxo de emails do domínio** no [painel de fluxo de emails](mail-flow-insights-v2.md) no [centro de conformidade do & de segurança](https://protection.office.com) oferece o status atual do fluxo de emails da sua organização.

Essa percepção ajuda a identificar e solucionar problemas de domínios que estão experimentando * problemas de *_fluxo de emails_*. Por exemplo, o domínio não pode receber emails externos porque o domínio expirou ou o domínio tem um registro MX incorreto.

![Widget status de fluxo de domínio superior no painel de fluxo de emails no centro de conformidade & segurança](../../media/mfi-top-domain-mail-flow-status-widget.png)

Quando você clica em _ *Exibir detalhes* * no widget, um submenu de **status de domínio** aparece mostrando mais detalhes para o status de cada domínio:

- **Domínio**
- **Registro MX anterior**
- **Registro MX atual**
- **Status de recebimento de email**
- **Status do domínio** : uma marca de seleção verde indica o registro MX atual (no momento em que você clicou no widget) corresponde ao valor que temos no registro e o domínio recebeu emails nas últimas duas horas.

  Um X vermelho indica que o registro MX foi alterado e o domínio não recebeu nenhum email durante as últimas 6 horas. Isso provavelmente indica que o domínio expirou ou que o registro MX foi atualizado incorretamente. Verifique com o seu registrador de domínio ou serviço de hospedagem DNS para ver se o domínio expirou ou se o registro MX do domínio está incorreto.

Você pode clicar em **Exibir mais** para ver as mesmas informações para mais domínios.

![Submenu de detalhes da visão superior do status do fluxo de emails do domínio](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>Confira também

Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).
