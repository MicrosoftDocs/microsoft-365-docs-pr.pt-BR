---
title: Visão de status de fluxo de email de domínio superior no painel fluxo de emails
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
description: Os administrador & es podem aprender a usar a visão de status de fluxo de email de domínio superior no painel de fluxo de emails no Centro de Conformidade e segurança para solucionar problemas de fluxo de emails relacionados aos registros MX.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 850e72fa0ad7a3f41450a1d0a2c02dd3df4a0cb5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053152"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a>Principais informações sobre o status do fluxo de emails de domínio no Centro de Conformidade & Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

A **visão de status** de [](mail-flow-insights-v2.md) fluxo de [&](https://protection.office.com) email de domínio superior no painel fluxo de email no Centro de Conformidade e Segurança fornece o status atual de fluxo de emails para sua organização.

Esse insight ajuda você a identificar e solucionar problemas de domínios que estão enfrentando problemas ***de fluxo de*** emails. Por exemplo, o domínio não pode receber emails externos porque o domínio expirou ou o domínio tem um registro MX incorreto.

![Widget de status de fluxo de domínio superior no painel fluxo de email no Centro de Conformidade & Segurança](../../media/mfi-top-domain-mail-flow-status-widget.png)

Quando você clica **em Exibir detalhes** no widget, um **flyout de status** de domínio é exibido que mostra mais detalhes sobre o status de cada domínio:

- **Domínio**
- **Registro MX anterior**
- **Registro MX atual**
- **Status de recebimento de email**
- **Status do** domínio : uma marca de verificação verde indica que o registro MX atual (no momento em que você clicou no widget) corresponde ao valor que temos no registro e o domínio recebeu emails durante as últimas duas horas.

  Um X vermelho indica que o registro MX foi alterado e o domínio não recebeu nenhum email durante as últimas 6 horas. Isso provavelmente indica que seu domínio expirou ou que o registro MX foi atualizado incorretamente. Verifique com seu registrador de domínio ou serviço de hospedagem DNS para ver se o domínio expirou ou se o registro MX do domínio está incorreto.

Você pode clicar **em Exibir mais** para ver as mesmas informações para mais domínios.

![Detalhes do flyout na visão de status de fluxo de email de domínio superior](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a>Confira também

Para obter informações sobre outras informações no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de Conformidade & [Segurança.](mail-flow-insights-v2.md)
