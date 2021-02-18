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
description: Os administradores podem aprender a usar os novos usuários que encaminham informações de & email no Centro de Conformidade e Segurança para investigar quando os usuários em sua organização estão encaminhando mensagens para novos domínios.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9706951df480d07f4a6311e99cab5c9f404e999e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290816"
---
# <a name="new-users-forwarding-email-insight-in-the-security--compliance-center"></a>Novos usuários encaminhando informações de email no Centro de Conformidade e & Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

É suspeito quando novas contas de usuário em sua organização começam a encaminhar mensagens de email para domínios externos.

Os **novos domínios** que estão sendo encaminhado [& s](https://protection.office.com) no Centro de Conformidade e Segurança notifica você quando usuários recém-criados em sua organização estão encaminhando mensagens para domínios externos. Essa condição pode indicar que contas de administrador comprometidas foram usadas para criar novos usuários. Se você suspeitar que as contas foram comprometidas, confira [Responder a uma conta de email comprometida.](responding-to-a-compromised-email-account.md)

Esse insight só aparece quando o problema é detectado e aparece na página [de relatório de encaminhamento.](view-mail-flow-reports.md#forwarding-report)

![Visão geral sobre novos usuários encaminhando email](../../media/mfi-new-users-forwarding-email.png)

Quando você clica no widget, um flyout é exibido, onde você pode encontrar [](#forwarding-modifications-report) mais detalhes sobre as mensagens encaminhadas, incluindo um link para o relatório de modificações de encaminhamento, conforme descrito mais adiante neste artigo.

![Detalhes do flyout que aparece depois de clicar no insight de novos usuários que encaminham emails](../../media/mfi-new-users-forwarding-email-details.png)

Você também pode acessar **essa** página de detalhes  ao selecionar as informações depois de clicar em Exibir tudo na área De informações principais & recomendações (**Painel** de Relatórios \>  ou <https://protection.office.com/insightdashboard> ).

Você pode clicar no link **Ver relatório associado ao** insight para ir para o relatório de modificações de encaminhamento conforme descrito na próxima seção. 

## <a name="forwarding-modifications-report"></a>Relatório de modificações de encaminhamento

O **relatório de modificações de encaminhamento** mostra detalhes sobre as mensagens que estão sendo encaminhadas automaticamente dos envios em sua organização:

- Contas recém-criadas que estão encaminhando mensagens para domínios externos.
- Contas que estão encaminhando mensagens para domínios externos que nunca foram encaminhadas por outros senders em sua organização.

Esses tipos de mensagens encaminhadas podem representar um risco de segurança ou conformidade e podem indicar contas comprometidas.

O relatório contém dados por até 90 dias. Por padrão, o relatório mostra dados dos últimos 7 dias.

Esse relatório não está diretamente disponível no painel de fluxo de [emails](mail-flow-insights-v2.md) ou no painel [Relatórios.](view-mail-flow-reports.md) Além de clicar no link Ver **relatório associado** ao insight no insight de novos usuários que encaminham informações de **email,** você pode acessar o relatório ao:

- Clicking the **Forwarding notifications report** link in the details of the [New domains being forwarded email insight](mfi-new-domains-being-forwarded-email.md).
- Abertura <https://protection.office.com/reportv2?id=MailFlowNewForwarding> .

### <a name="report-view-for-the-forwarding-modifications-report"></a>Exibição de relatório para o relatório de modificações de encaminhamento

Os gráficos a seguir estão disponíveis na exibição de relatório:

- **Mostrar dados para: Novos usuários de encaminhamento:**

  ![New forwarding users view in the Forwarding modifications report](../../media/forwarding-modifications-report-new-forwarding-users.png)

- **Mostrar dados para: Novos domínios de encaminhamento:**

  ![New forwarded domains view in the Forwarding modifications report](../../media/forwarding-modifications-report-new-forwarded-domains.png)

Se você clicar em **Filtros** em uma exibição de relatório, poderá especificar um intervalo de datas com data **de** início **e data de término.**

### <a name="details-table-view-for-the-forwarding-modifications-report"></a>Visão de tabela de detalhes para o relatório de modificações de encaminhamento

Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:

- **Mostrar dados para: Novos usuários de encaminhamento:**

  - **Nome**: o endereço de email do remetente.
  - **Tipo de encaminhamento**
  - **Endereço do destinatário**
  - **Detalhes**
  - **Count**
  - **Primeira data de encaminhamento**

- **Mostrar dados para: Novos domínios de encaminhamento:**

  - **Nome**: o domínio de email do remetente.
  - **Tipo de encaminhamento**
  - **Endereço do destinatário**
  - **Detalhes**
  - **Count**
  - **Primeira data de encaminhamento**

Se você clicar em **Filtros** em uma exibição de tabela de detalhes, poderá especificar um intervalo de datas com data de **início** **e data de término.**

Se você selecionar uma linha da tabela, um flyout **Detalhes** aparecerá com as seguintes informações:

- **Nome:** este é o endereço de email do remetente (de Mostrar dados **para:** exibição novos usuários de encaminhamento) ou o domínio de email do remetente (de Mostrar dados para: exibição de novos **domínios** de encaminhamento).
- **Tipo de encaminhamento**
- **Recipiente**
- **Detalhes**
- **Count**
- **Data de início**
- **Recomendação:** a partir daqui, você pode clicar no link para gerenciar o usuário no centro de administração do Microsoft 365.

![Detalhes do flyout da tabela de detalhes da exibição Novos usuários de encaminhamento no relatório de modificações de encaminhamento](../../media/mfi-forwarding-modifications-report-new-forwarding-users-view-details-table-details.png)

Para voltar para a exibição de relatórios, clique em **Exibir relatório.**

## <a name="related-topics"></a>Tópicos relacionados

Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações sobre o fluxo de emails no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)
