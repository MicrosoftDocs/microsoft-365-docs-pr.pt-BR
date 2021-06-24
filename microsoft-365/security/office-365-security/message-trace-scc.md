---
title: Rastreamento de mensagens no Microsoft 365 Defender portal
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem usar o link de rastreamento de mensagens no portal Microsoft 365 Defender para descobrir o que aconteceu com as mensagens.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108110"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a>Rastreamento de mensagens no Microsoft 365 Defender portal

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

O rastreamento de mensagens no portal Microsoft 365 Defender segue mensagens de email à medida que elas viajam pela sua Exchange Online organização. Você pode determinar se uma mensagem foi recebida, rejeitada, adiada ou entregue pelo serviço. Também mostra as ações feitas na mensagem antes de ela chegar em seu status final.

Você pode usar as informações do rastreamento de mensagens para responder com eficiência às perguntas do usuário sobre o que aconteceu com as mensagens, solucionar problemas de fluxo de emails e validar alterações de política.

> [!NOTE]
> O rastreamento de mensagens no portal Microsoft 365 Defender é apenas uma passagem para rastreamento de mensagem no centro de administração Exchange de mensagens. Para obter mais informações, consulte [Rastreamento de mensagens no centro de administração Exchange moderno.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Você precisa ser membro dos grupos de função Gerenciamento da **Organização,** Gerenciamento de **Conformidade** ou Help **Desk** **Exchange Online** usar rastreamento de mensagens. Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Observações**: a associação à função Azure Active Directory correspondente no Centro de administração do Microsoft 365 fornece  aos usuários as permissões e permissões necessárias para outros recursos no Microsoft 365. Para obter mais informações, confira [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

- O número máximo de mensagens exibidas nos resultados de um rastreamento de mensagem depende do tipo de relatório selecionado (consulte a seção Escolher tipo [de](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) relatório para obter detalhes). O cmdlet [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) no Exchange Online PowerShell ou no EOP PowerShell autônomo retorna todas as mensagens nos resultados.

## <a name="open-message-trace"></a>Abrir rastreamento de mensagens

No portal Microsoft 365 Defender ( <https://security.microsoft.com> ), acesse **Email & colaboração Exchange** rastreamento de \> **mensagens.** Ou, para ir diretamente para a página de rastreamento de mensagens, use <https://admin.exchange.microsoft.com/#/messagetrace> .

Neste ponto, o rastreamento de mensagens no EAC é aberto. Para obter mais informações, consulte [Rastreamento de mensagens no centro de administração Exchange moderno.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)
