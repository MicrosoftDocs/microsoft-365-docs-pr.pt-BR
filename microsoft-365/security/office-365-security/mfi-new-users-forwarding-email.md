---
title: Visão geral sobre novos usuários encaminhando email
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: exchange-online
localization_priority: Normal
ms.assetid: ''
description: Os administradores podem aprender a usar os novos usuários que estão encaminhando informações de email no centro de conformidade de & de segurança para investigar quando os usuários de sua organização estão encaminhando mensagens para novos domínios.
ms.openlocfilehash: af66a84efbd4c0b8f1ccdacf4b71d1caca1c3929
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877520"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>Novos usuários encaminhando informações de email no centro de conformidade e segurança &

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


É suspeito quando novas contas de usuário em sua organização começam a encaminhar mensagens de email para domínios externos de repente.

Os **novos domínios que estão sendo encaminhados** informações de email no [centro de conformidade e segurança &](https://protection.office.com) notifica você quando os usuários recém-criados em sua organização estão encaminhando mensagens para domínios externos. Essa condição pode indicar que contas de administrador comprometidas foram usadas para criar novos usuários. Se você suspeitar que as contas foram comprometidas, confira [responder a uma conta de email comprometida](https://docs.microsoft.com/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account).

Essa percepção aparece somente quando o problema é detectado e aparece na página de [relatório de encaminhamento](view-mail-flow-reports.md#forwarding-report) .

![Visão geral sobre novos usuários encaminhando email](../../media/mfi-new-users-forwarding-email.png)

Quando você clica no widget, um submenu aparece onde você pode encontrar mais detalhes sobre as mensagens encaminhadas, incluindo um link para o [relatório de alterações de encaminhamento](#forwarding-modifications-report) conforme descrito posteriormente neste tópico.

![Submenu de detalhes que aparece depois de clicar nos novos usuários encaminhando informações sobre o envio de email](../../media/mfi-new-users-forwarding-email-details.png)

Você também pode acessar essa página de detalhes ao selecionar a percepção depois de clicar em **Exibir tudo** na área de **recomendações de & principais** em (painel de **relatórios** \> **Dashboard** ou <https://protection.office.com/insightdashboard> ).

Você pode clicar no link **Confira o relatório associado com a percepção** para acessar o **relatório de alterações de encaminhamento** conforme descrito na próxima seção.

## <a name="forwarding-modifications-report"></a>Relatório de reencaminhamento de modificações

O **relatório de alterações de encaminhamento** mostra detalhes sobre as mensagens que estão sendo encaminhadas automaticamente de remetentes em sua organização:

- Contas recém-criadas que estão encaminhando mensagens para domínios externos.
- As contas que estão encaminhando mensagens para domínios externos que nunca foram encaminhadas para outros remetentes em sua organização.

Esses tipos de mensagens encaminhadas podem representar um risco de segurança ou de conformidade e podem indicar contas comprometidas.

O relatório contém dados de até 90 dias. Por padrão, o relatório mostra os dados dos últimos 7 dias.

Este relatório não está disponível diretamente no [painel de fluxo de emails](mail-flow-insights-v2.md) ou no [painel relatórios](view-mail-flow-reports.md). Além de clicar no link **Ver relatório associado com a percepção** no **envio de emails de encaminhamento de novos usuários** , você recebe o relatório por:

- Clicando no link de **relatório de notificações de encaminhamento** , nos detalhes dos [novos domínios que estão sendo encaminhados informações de email](mfi-new-domains-being-forwarded-email.md).
- Abrir <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .

### <a name="report-view-for-the-forwarding-modifications-report"></a>Exibição de relatório para o relatório de alterações de encaminhamento

Os gráficos a seguir estão disponíveis no modo de exibição de relatório:

- **Mostrar dados de: novos usuários de encaminhamento** :

  ![Novo modo de exibição de usuários de encaminhamento no relatório de alterações de encaminhamento](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **Mostrar dados para: novos domínios de encaminhamento** :

  ![Exibição de novos domínios encaminhados no relatório de alterações de encaminhamento](../../media/forwarding-modifications-report-new-forwarded-domains.png)

Se você clicar em **filtros** em um modo de exibição de relatório, poderá especificar um intervalo de datas com **data de início** e data de **término**.

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>Exibição da tabela de detalhes para o relatório de alterações de encaminhamento

Se você clicar em **Exibir tabela de detalhes** , as informações mostradas dependem do gráfico que você estava observando:

- **Mostrar dados de: novos usuários de encaminhamento** :

  - **Name** : o endereço de email do remetente.
  - **Tipo de encaminhamento**
  - **Endereço do destinatário**
  - **Detalhes**
  - **Count**
  - **Primeira data de encaminhamento**

- **Mostrar dados para: novos domínios de encaminhamento** :

  - **Name** : o domínio de email do remetente.
  - **Tipo de encaminhamento**
  - **Endereço do destinatário**
  - **Detalhes**
  - **Count**
  - **Primeira data de encaminhamento**

Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.

Se você selecionar uma linha da tabela, um submenu de **detalhes** aparecerá com as seguintes informações:

- **Nome** : Este é o endereço de email do remetente (da exibição **Mostrar dados para: novos usuários de encaminhamento** ) ou o domínio de email do remetente (do **Mostrar dados para: novo** modo de exibição de domínios de encaminhamento).
- **Tipo de encaminhamento**
- **Recipient**
- **Detalhes**
- **Count**
- **Data de início**
- **Recomendação** : aqui, você pode clicar no link para gerenciar o usuário no centro de administração do Microsoft 365.

![Submenu de detalhes da tabela detalhes do novo modo de exibição de usuários de encaminhamento no relatório de alterações de encaminhamento](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

Para voltar para o modo de exibição relatórios, clique em **Exibir relatório**.

## <a name="related-topics"></a>Tópicos relacionados

Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).
