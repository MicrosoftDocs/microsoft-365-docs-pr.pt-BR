---
title: Insights de fluxo de email no painel de fluxo de emails
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: beb6acaa-6016-4d54-ba7e-3d6d035e2b46
description: Os administradores podem saber mais sobre as ideias e os relatórios disponíveis no painel de fluxo de emails no centro de conformidade do & de segurança.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 06e9449553d008bc383ae6f2b6098f9598cad43c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826560"
---
# <a name="mail-flow-insights-in-the-security--compliance-center"></a>Fluxo de emails no Centro de Conformidade e Segurança

Os administradores podem usar o painel de fluxo de emails no centro de conformidade de & de segurança para descobrir tendências, insights e realizar ações para corrigir problemas relacionados ao fluxo de emails em sua organização.

![O painel de fluxo de emails no centro de conformidade & segurança](../../media/mail-flow-dashboard-v2.png)

As informações disponíveis são:

- [Visão geral sobre mensagens encaminhadas automaticamente](mfi-auto-forwarded-messages-report.md)

- [Corrigir possíveis informações de loop de email](mfi-mail-loop-insight.md)<sup>1</sup>

- [Corrigir as regras de fluxo de email lentos informações](mfi-slow-mail-flow-rules-insight.md)<sup>1</sup>

- [Mapa de fluxo de email](mfi-mail-flow-map-report.md)

- [Novos domínios sendo encaminhados informações sobre email](mfi-new-domains-being-forwarded-email.md)<sup>2</sup>

- [Novos usuários encaminhando informações de email](mfi-new-users-forwarding-email.md)<sup>2</sup>

- [Relatório de domínio não aceito](mfi-non-accepted-domain-report.md)

- [Relatório de falha na entrega](mfi-non-delivery-report.md)

- [Visão geral sobre fluxo de entrada e saída de emails](mfi-outbound-and-inbound-mail-flow.md)

- [Visão geral sobre filas](mfi-queue-alerts-and-queues.md)

- [Visão geral e relatório de clientes de autenticação SMTP](mfi-smtp-auth-clients-report.md)

- [Insight sobre o status do fluxo de mensagens dos principais domínios](mfi-domain-mail-flow-status-insight.md)

<sup>1</sup> essa percepção aparecerá na área **recomendada para você** no painel de fluxo de emails somente depois que o problema for detectado. Caso contrário, você não o verá.

<sup>2</sup> essa percepção não aparece no painel de fluxo de emails, mas fica visível na página de [relatório de encaminhamento](view-mail-flow-reports.md#forwarding-report) depois que o problema é detectado. Caso contrário, você não o verá.

## <a name="permissions-required-to-view-the-mail-flow-dashboard"></a>Permissões necessárias para exibir o painel de fluxo de emails

O painel de fluxo de emails está disponível para membros dos seguintes grupos de rotas:

- **Gerenciamento de organização** no centro de conformidade e segurança & (administradores globais).

- **[Administrador do Exchange](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** no Azure AD.

- **Fluxo administrador** no centro de conformidade & segurança: se um membro desse grupo de função não for membro dos grupos de função administrador global ou administrador do Exchange, observe os seguintes problemas e requisitos:

  - O usuário deve fazer logon no centro de conformidade & segurança diretamente em <https://protection.office.com> .
  - O usuário só terá permissão somente leitura para o painel de fluxo de emails.
  - O usuário não terá acesso ao centro de administração do Microsoft 365.

Para obter mais informações sobre permissões no centro de conformidade & segurança, consulte [permissões no centro de conformidade de & de segurança](permissions-in-the-security-and-compliance-center.md) e [forneça aos usuários acesso ao centro de conformidade do & de segurança](grant-access-to-the-security-and-compliance-center.md).

## <a name="where-to-find-the-mail-flow-dashboard"></a>Onde encontrar o painel de fluxo de emails

Abra o centro de conformidade do & de segurança em <https://protection.office.com> , expanda **fluxo de email**e selecione **painel**.

Para ir diretamente para o painel de fluxo de emails, abra <https://protection.office.com/mailflow/dashboard> .
