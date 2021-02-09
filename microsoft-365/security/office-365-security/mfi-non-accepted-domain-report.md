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
description: Os administradores podem aprender a usar o relatório de domínio não aceito no painel Fluxo de emails no Centro de Conformidade e Segurança para monitorar mensagens de sua organização local onde o domínio do remetente não está configurado no Microsoft 365. &
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 573fb0ba2bf7981b6eb7df4eec7c8c4e5d596cac
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150815"
---
# <a name="non-accepted-domain-report-in-the-security--compliance-center"></a>Relatório de domínio não aceito no Centro de Conformidade e Segurança & segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

O  relatório de domínio não [](mail-flow-insights-v2.md) aceito no painel Fluxo de emails no Centro de Conformidade e Segurança exibe informações sobre mensagens de sua organização de email local onde o domínio do remetente não está configurado como um domínio aceito em sua organização do Microsoft 365. [&](https://protection.office.com)

O Microsoft 365 pode acelerar essas mensagens se temos dados para provar que a intenção dessas mensagens é mal-intencionada. Portanto, é importante que você entenda o que está acontecendo e corrige o problema.

![Widget de domínio não aceito no painel Fluxo de emails no Centro de Conformidade e Segurança & Segurança](../../media/mfi-non-accepted-domain-report-widget.png)

## <a name="report-view-for-the-non-accepted-domain-report"></a>Exibição de relatório para o relatório de domínio não aceito

Clicar no gráfico no widget **de** domínio não aceito levará você ao relatório **de domínio não aceito.**

Por padrão, a atividade de todos os conectores afetados é mostrada. Se você clicar **em Mostrar dados** para , você pode selecionar um conector específico na lista suspenso.

Se você passar o mouse sobre um ponto de dados (dia) no gráfico, verá o número total de mensagens para o conector.

![Exibição de relatório no relatório de domínio não aceito](../../media/mfi-non-accepted-domain-report-overview-view.png)

## <a name="details-table-view-for-the-non-accepted-domain-report"></a>Exibição de tabela de detalhes para o relatório de domínio não aceito

Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:

- **Date**
- **Nome do conector de entrada**
- **Domínio do remetente**
- **Contagem de mensagem**
- **Mensagens de** exemplo: as IDs de mensagem de uma amostra de mensagens afetadas.

Se você clicar em **Filtros** em uma exibição de tabela de detalhes, poderá especificar um intervalo de datas com data **de** início **e data de término.**

Para enviar o relatório por email para um intervalo de datas específico para um ou mais destinatários, clique em **Solicitar download.**

Quando você seleciona uma linha na tabela, um flyout é exibido com as seguintes informações:

- **Date**
- **Nome do conector de entrada**
- **Domínio do remetente**
- **Contagem de mensagem**
- **Exemplos de** mensagens: você pode clicar **em Exibir mensagens de exemplo** para ver os resultados [do](message-trace-scc.md) rastreamento de mensagens para uma amostra das mensagens afetadas.

![Submenu de detalhes após selecionar uma linha no exibição de tabela Detalhes no relatório de domínio não aceito](../../media/mfi-non-accepted-domain-report-details-flyout.png)

Para voltar para a exibição de relatórios, clique em **Exibir relatório.**

## <a name="related-topics"></a>Tópicos relacionados

Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações sobre o fluxo de emails no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)
