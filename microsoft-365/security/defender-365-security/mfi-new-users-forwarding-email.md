---
title: Visão geral sobre novos usuários encaminhando email
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Os administradores podem aprender como usar o novo usuário encaminhando informações de email no Centro de Conformidade e Segurança & para investigar quando os usuários em sua organização estão encaminhando mensagens para novos domínios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 807df82ca80e851554db7b8f373a5ca4af02a391
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053140"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>Novos usuários encaminhando informações de email no Centro de Conformidade & Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

É suspeito quando novas contas de usuário em sua organização começam a encaminhar mensagens de email para domínios externos.

Os **novos domínio & s** que [](https://protection.office.com) estão sendo encaminhados no Centro de Conformidade e Segurança notificam você quando usuários recém-criados em sua organização estão encaminhando mensagens para domínios externos. Essa condição pode indicar que contas de administrador comprometidas foram usadas para criar os novos usuários. Se você suspeitar que as contas foram comprometidas, consulte [Respondendo a uma conta de email comprometida.](responding-to-a-compromised-email-account.md)

Esse insight aparece somente quando o problema é detectado e aparece na página [Relatório de](view-mail-flow-reports.md#forwarding-report) Encaminhamento.

![Visão geral sobre novos usuários encaminhando email](../../media/mfi-new-users-forwarding-email.png)

Quando você clica no widget, um sobremenu aparece onde você pode encontrar mais [](#forwarding-modifications-report) detalhes sobre as mensagens encaminhadas, incluindo um link para o relatório de modificações de encaminhamento conforme descrito posteriormente neste artigo.

![Detalhes sobre o sobrevoo que aparece após clicar no insight De encaminhamento de email novos usuários](../../media/mfi-new-users-forwarding-email-details.png)

Você também pode acessar **essa** página de detalhes  quando selecionar o insight depois de clicar em Exibir tudo na área Principais & recomendações em (**Painel** de Relatórios \>  ou <https://protection.office.com/insightdashboard> ).

Você pode clicar no link Ver relatório associado  **ao** insight para acessar o relatório de modificações de encaminhamento conforme descrito na próxima seção.

## <a name="forwarding-modifications-report"></a>Relatório de modificações de encaminhamento

O **relatório de modificações de encaminhamento** mostra detalhes sobre mensagens que estão sendo encaminhadas automaticamente de senders em sua organização:

- Contas recém-criadas que estão encaminhando mensagens para domínios externos.
- Contas que estão encaminhando mensagens para domínios externos que nunca foram encaminhadas por outros senders em sua organização.

Esses tipos de mensagens encaminhadas podem representar um risco de segurança ou conformidade e podem indicar contas comprometidas.

O relatório contém dados de até 90 dias. Por padrão, o relatório mostra dados dos últimos 7 dias.

Este relatório não está disponível [](mail-flow-insights-v2.md) diretamente no painel de fluxo de emails ou no painel [Relatórios.](view-mail-flow-reports.md) Além de clicar no link **Ver relatório associado** ao insight no insight Novos usuários encaminhando informações de **email,** você pode acessar o relatório por:

- Clicando no **link Relatório de notificações** de encaminhamento nos detalhes dos novos domínios que estão sendo [encaminhados informações de email.](mfi-new-domains-being-forwarded-email.md)
- Abrindo <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .

### <a name="report-view-for-the-forwarding-modifications-report"></a>Exibição de relatório para o relatório de modificações de encaminhamento

Os gráficos a seguir estão disponíveis na exibição de relatório:

- **Mostrar dados para: Novos usuários de encaminhamento:**

  ![Nova exibição de usuários de encaminhamento no relatório de modificações de encaminhamento](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **Mostrar dados para: Novos domínios de encaminhamento:**

  ![Nova exibição de domínios encaminhados no relatório de modificações de encaminhamento](../../media/forwarding-modifications-report-new-forwarded-domains.png)

Se você clicar **em Filtros** em um exibição de relatório, poderá especificar um intervalo de datas com **Data de** Início e Data **de Término.**

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>Exibição de tabela de detalhes para o relatório de modificações de encaminhamento

Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:

- **Mostrar dados para: Novos usuários de encaminhamento:**

  - **Nome**: o endereço de email do remetente.
  - **Tipo de encaminhamento**
  - **Endereço do destinatário**
  - **Detalhes**
  - **Count**
  - **Primeira data de encaminhamento**

- **Mostrar dados para: Novos domínios de encaminhamento:**

  - **Nome**: O domínio de email do remetente.
  - **Tipo de encaminhamento**
  - **Endereço do destinatário**
  - **Detalhes**
  - **Count**
  - **Primeira data de encaminhamento**

Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá especificar um intervalo de datas com **Data de** início e data **de término.**

Se você selecionar uma linha da tabela, um **sobremenu de Detalhes** aparecerá com as seguintes informações:

- **Nome**: Este é o endereço de email do remetente (de Mostrar dados **para:** nova exibição de usuários de encaminhamento) ou o domínio de email do remetente (de Mostrar dados para: Novo exibição de **domínios** de encaminhamento).
- **Tipo de encaminhamento**
- **Recipient**
- **Detalhes**
- **Count**
- **Data de início**
- **Recomendação**: a partir daqui, você pode clicar no link para gerenciar o usuário no Centro de administração do Microsoft 365.

![Detalhes do sobrevoo da tabela de detalhes da exibição Novos usuários de encaminhamento no relatório de modificações de encaminhamento](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

Para voltar à exibição de relatórios, clique em **Exibir relatório**.

## <a name="related-topics"></a>Tópicos relacionados

Para obter informações sobre outras informações no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de Conformidade & [Segurança.](mail-flow-insights-v2.md)
