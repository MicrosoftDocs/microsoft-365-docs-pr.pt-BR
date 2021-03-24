---
title: Insights de fluxo de emails no painel de fluxo de emails
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Os administradores podem aprender sobre as informações e relatórios disponíveis no painel fluxo de emails no Centro de Conformidade & Segurança.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 39f7b43db62fd19f7500972a3016fdd8dd0875b6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054023"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>Fluxo de emails no Centro de Conformidade e Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Os administradores podem usar o painel de fluxo de email no Centro de Conformidade & segurança para descobrir tendências, ideias e tomar ações para corrigir problemas relacionados ao fluxo de emails em sua organização.

![O painel de fluxo de emails no Centro de Conformidade & Segurança](../../media/mail-flow-dashboard-v2.png)

As informações disponíveis são:

- [Visão geral sobre mensagens encaminhadas automaticamente](mfi-auto-forwarded-messages-report.md)

- [Corrigir o insight de loop de email](mfi-mail-loop-insight.md)<sup>1 possível</sup>

- [Correção do insight das regras de fluxo de emails lentos](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [Mapa de fluxo de email](mfi-mail-flow-map-report.md)

- [Novos domínios sendo encaminhados por email insight](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [Novos usuários encaminhando informações de email](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [Relatório de domínio não aceito](mfi-non-accepted-domain-report.md)

- [Relatório de falha na entrega](mfi-non-delivery-report.md)

- [Visão geral sobre fluxo de entrada e saída de emails](mfi-outbound-and-inbound-mail-flow.md)

- [Informações sobre filas](mfi-queue-alerts-and-queues.md)

- [Visão geral e relatório de clientes de autenticação SMTP](mfi-smtp-auth-clients-report.md)

- [Insight sobre o status do fluxo de mensagens dos principais domínios](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> Esse insight aparece na área **Recomendado para você** do painel de fluxo de email somente depois que o problema é detectado. Caso contrário, você não o verá.

<sup>2</sup> Esse insight não aparece no painel de fluxo [](view-mail-flow-reports.md#forwarding-report) de emails, mas fica visível na página Relatório de Encaminhamento após a detecção do problema. Caso contrário, você não o verá.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Permissões necessárias para exibir o painel de fluxo de emails

O painel de fluxo de emails está disponível para membros dos seguintes grupos de função:

- **Gerenciamento da** organização no Centro de Conformidade & segurança (administradores globais).

- **[Administrador do Exchange](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** no Azure Active Directory.

- **Administrador do MailFlow** no Centro de Conformidade & Segurança. Se a conta também não for membro dos grupos de função Gerenciamento da Organização ou Administrador do Exchange, considere os seguintes problemas:
  - O usuário deve entrar no Centro de Conformidade & segurança diretamente em <https://protection.office.com> .
  - O usuário só terá permissão somente leitura para o painel de fluxo de email.
  - O usuário não terá acesso ao centro de administração do Microsoft 365.

Para obter mais informações sobre permissões, consulte [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and Give users access to the Security & Compliance [Center](grant-access-to-the-security-and-compliance-center.md).

## <a name="where-to-find-the-mail-flow-dashboard"></a>Onde encontrar o painel de fluxo de emails

Abra o Centro de Conformidade & segurança em <https://protection.office.com> , **expanda Fluxo de emails** e selecione **Painel**.

Para ir diretamente para o painel de fluxo de emails, abra <https://protection.office.com/mailflow/dashboard> .