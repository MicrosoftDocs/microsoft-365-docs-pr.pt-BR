---
title: Relatório de domínio não aceito no painel fluxo de emails
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
description: Os administradores podem aprender a usar o relatório de domínio não aceito no painel de fluxo de emails no Centro de Conformidade e Segurança para monitorar mensagens da sua organização local onde o domínio do remetente não está configurado no Microsoft 365. &
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fb33feb56bf2b52731c03273ce0c6444c333f348
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053138"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Relatório de domínio não aceito no Centro de Conformidade & Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

O  relatório de domínio não [](mail-flow-insights-v2.md) aceito no painel fluxo de emails no Centro de Conformidade e Segurança exibe informações sobre mensagens da sua organização de email local onde o domínio do remetente não está configurado como um domínio aceito em sua organização do Microsoft 365. [&](https://protection.office.com)

O Microsoft 365 pode acelerar essas mensagens se temos dados para provar que a intenção dessas mensagens é mal-intencionada. Portanto, é importante que você entenda o que está acontecendo e corrige o problema.

![Widget de domínio não aceito no painel de fluxo de emails no Centro de Conformidade & Segurança](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>Exibição de relatório para o relatório de domínio não aceito

Clicar no gráfico no widget **de** domínio não aceito o levará ao relatório **de domínio não aceito.**

Por padrão, a atividade para todos os conectores afetados é mostrada. Se você clicar **em Mostrar dados** para , você poderá selecionar um conector específico no menu suspenso.

Se você passar o mouse sobre um ponto de dados (dia) no gráfico, verá o número total de mensagens para o conector.

![Exibir relatório no relatório de domínio não aceito](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>Exibição de tabela de detalhes para o relatório de domínio não aceito

Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:

- **Date**
- **Nome do conector de entrada**
- **Domínio do remetente**
- **Contagem de mensagem**
- **Exemplo de mensagens**: As IDs de mensagem de uma amostra de mensagens afetadas.

Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá especificar um intervalo de datas com **Data de** início e data **de término.**

Para enviar o relatório por email para um intervalo de datas específico para um ou mais destinatários, clique em **Solicitar download**.

Quando você seleciona uma linha na tabela, um sobrevoo aparece com as seguintes informações:

- **Date**
- **Nome do conector de entrada**
- **Domínio do remetente**
- **Contagem de mensagem**
- **Exemplo de mensagens**: você pode clicar em **Exibir mensagens de exemplo** para ver os resultados do rastreamento de mensagens para um exemplo das mensagens afetadas. [](message-trace-scc.md)

![Submenu de detalhes após selecionar uma linha no exibição de tabela Detalhes no relatório de domínio não aceito](../../media/mfi-non-accepted-domain-report-details-flyout.png)

Para voltar à exibição de relatórios, clique em **Exibir relatório**.

## <a name="related-topics"></a>Tópicos relacionados

Para obter informações sobre outras informações no painel de fluxo de emails, consulte Informações de fluxo de email no Centro de Conformidade & [Segurança.](mail-flow-insights-v2.md)
