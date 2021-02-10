---
title: Informações de fluxo de emails no painel Fluxo de emails
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Os administradores podem saber mais sobre as informações e relatórios disponíveis no painel Fluxo de emails no Centro de Conformidade & e Segurança.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b65e235e3446fa62bca1c9f8aef73f2387b1140b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167090"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>Fluxo de emails no Centro de Conformidade e Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Os administrador & es podem usar o painel fluxo de emails no Centro de Conformidade e Segurança para descobrir tendências, insights e tomar ações para corrigir problemas relacionados ao fluxo de emails em sua organização.

![O painel De fluxo de emails no Centro de Conformidade & segurança](../../media/mail-flow-dashboard-v2.png)

As informações disponíveis são:

- [Visão geral sobre mensagens encaminhadas automaticamente](mfi-auto-forwarded-messages-report.md)

- [Correção de possível visão de loop de email](mfi-mail-loop-insight.md)<sup>1</sup>

- [Visão 1 de correção de](mfi-slow-mail-flow-rules-insight.md)regras de fluxo de emails<sup>lentos</sup>

- [Mapa de fluxo de email](mfi-mail-flow-map-report.md)

- [Visão 2 dos novos domínios que estão sendo encaminhados](mfi-new-domains-being-forwarded-email.md)<sup></sup>

- [Novos usuários encaminhando informações de email](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [Relatório de domínio não aceito](mfi-non-accepted-domain-report.md)

- [Relatório de falha na entrega](mfi-non-delivery-report.md)

- [Visão geral sobre fluxo de entrada e saída de emails](mfi-outbound-and-inbound-mail-flow.md)

- [Informações sobre filas](mfi-queue-alerts-and-queues.md)

- [Visão geral e relatório de clientes de autenticação SMTP](mfi-smtp-auth-clients-report.md)

- [Insight sobre o status do fluxo de mensagens dos principais domínios](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> Esse insight aparece na área **Recomendado para você** do painel de fluxo de emails somente depois que o problema é detectado. Caso contrário, você não o verá.

<sup>2</sup> Esse insight não aparece no painel de fluxo [](view-mail-flow-reports.md#forwarding-report) de emails, mas fica visível na página relatório de encaminhamento depois que o problema é detectado. Caso contrário, você não o verá.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Permissões necessárias para exibir o painel de fluxo de emails

O painel Fluxo de emails está disponível para membros dos seguintes grupos de função:

- **Gerenciamento da** organização no Centro de Conformidade & Segurança (administradores globais).

- **[Administrador do Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** no Azure Active Directory.

- **Administrador do Fluxo de** Mensagens no Centro de Conformidade & Segurança. Se a conta não for membro dos grupos de função Gerenciamento da Organização ou Administrador do Exchange, considere os seguintes problemas:
  - O usuário deve entrar no Centro de Conformidade e Segurança & diretamente em <https://protection.office.com> .
  - O usuário só terá permissão somente leitura para o painel de fluxo de emails.
  - O usuário não terá acesso ao centro de administração do Microsoft 365.

Para obter mais informações sobre permissões, consulte Permissões no Centro de Conformidade e Segurança [&](permissions-in-the-security-and-compliance-center.md) e dê aos usuários acesso ao Centro de Conformidade & [segurança.](grant-access-to-the-security-and-compliance-center.md)

## <a name="where-to-find-the-mail-flow-dashboard"></a>Onde encontrar o painel fluxo de emails

Abra o Centro de Conformidade & segurança em <https://protection.office.com> , **expanda o fluxo** de emails e selecione **Painel**.

Para ir diretamente para o painel de fluxo de emails, abra <https://protection.office.com/mailflow/dashboard> .
