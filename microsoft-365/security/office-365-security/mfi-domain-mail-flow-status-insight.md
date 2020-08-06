---
title: Visão geral do status do fluxo de email de domínio superior no painel de fluxo de emails
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar a visão superior do status do fluxo de emails do domínio no painel de fluxo de emails no centro de conformidade de & de segurança para solucionar problemas de fluxo de emails relacionados a registros MX em seus domínios de email.
ms.openlocfilehash: 6366e3aee0ab50096f1396776397c80fabc8aaf2
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577734"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Visão geral do status do fluxo de email de domínio superior no centro de conformidade e segurança &

A **parte superior do status do fluxo de emails do domínio** no [painel de fluxo de emails](mail-flow-insights-v2.md) do centro de conformidade & segurança oferece o status atual dos domínios da sua organização em termos de fluxo de emails. Essa percepção ajuda a identificar e solucionar problemas de domínios que estão enfrentando problemas de ***impacto de fluxo de emails*** (por exemplo, não é possível receber emails externos), especialmente expirações de domínio ou domínios com registros MX incorretos.

![Widget status de fluxo de domínio superior no painel de fluxo de emails no centro de conformidade & segurança](../../media/mfi-top-domain-mail-flow-status-widget.png)

Quando você clica em **Exibir detalhes** no widget, um submenu de **status de domínio** aparece mostrando mais detalhes para o status de cada domínio:

- **Domínio**
- **Registro MX anterior**
- **Registro MX atual**
- **Status de recebimento de email**
- **Status do domínio**: uma marca de seleção verde indica o registro MX atual (no momento em que você clicou no widget) corresponde ao valor que temos no registro e que o domínio recebeu emails nas últimas duas horas.

  Um X vermelho indica que o registro MX foi alterado e que o domínio não recebeu nenhum email durante as últimas 6 horas. Isso provavelmente indica que o domínio expirou ou que o registro MX foi atualizado incorretamente. Verifique com o seu registrador de domínio ou serviço de hospedagem DNS para ver se o domínio expirou ou se o registro MX do domínio está incorreto.

Você pode clicar em **Exibir mais** para ver as mesmas informações para mais domínios.

![Submenu de detalhes da visão superior do status do fluxo de emails do domínio](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a>Tópicos relacionados

Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).
