---
title: Relatório de domínio não aceito no painel de fluxo de emails
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o relatório de domínio não aceito no painel de fluxo de emails no centro de conformidade de & de segurança para monitorar mensagens de sua organização local onde o domínio do remetente não está configurado no Microsoft 365.
ms.openlocfilehash: d05489ec4a6d670fc89b5d943b3e7061506b6fe8
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48199320"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Relatório de domínio não aceito no centro de conformidade e segurança &

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


O relatório de **domínio não aceito** no [painel de fluxo de emails](mail-flow-insights-v2.md) no [centro de conformidade & segurança](https://protection.office.com) exibe informações sobre as mensagens da sua organização de email local onde o domínio do remetente não está configurado como um domínio aceito na sua organização do Microsoft 365.

O Microsoft 365 pode reduzir essas mensagens se houver dados que comprovam que a intenção dessas mensagens é mal-intencionada. Portanto, é importante entender o que está acontecendo e corrigir o problema.

![Widget domínio não aceito no painel de fluxo de emails no centro de conformidade de & de segurança](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>Exibição de relatório para o relatório de domínio não aceito

Ao clicar no gráfico no widget **domínio não aceito** , você será direcionado para o relatório de **domínio não aceito** .

Por padrão, a atividade de todos os conectores afetados é mostrada. Se você clicar em **Mostrar dados para**, poderá selecionar um conector específico na lista suspensa.

Se você passar o mouse sobre um ponto de dados (dia) no gráfico, verá o número total de mensagens do conector.

![Exibição de relatório no relatório de domínio não aceito](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>Exibição da tabela de detalhes para o relatório de domínio não aceito

Se você clicar em **Exibir tabela de detalhes** em um modo de exibição de relatório, as seguintes informações serão exibidas:

- **Date**
- **Nome do conector de entrada**
- **Domínio do remetente**
- **Contagem de mensagem**
- **Mensagens de exemplo**: as IDs de mensagem de uma amostra de mensagens afetadas.

Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.

Para enviar por email o relatório para um intervalo de datas específico para um ou mais destinatários, clique em **solicitar download**.

Quando você seleciona uma linha na tabela, um submenu aparece com as seguintes informações:

- **Date**
- **Nome do conector de entrada**
- **Domínio do remetente**
- **Contagem de mensagem**
- **Exemplos de mensagens**: você pode clicar em **Exibir mensagens de amostra** para ver os resultados de [rastreamento](message-trace-scc.md) de mensagens para um exemplo de mensagens afetadas.

![Submenu de detalhes depois de selecionar uma linha no modo de exibição de tabela detalhes no relatório de domínio não aceito](../../media/mfi-non-accepted-domain-report-details-flyout.png)

Para voltar para o modo de exibição relatórios, clique em **Exibir relatório**.

## <a name="related-topics"></a>Tópicos relacionados

Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).
