---
title: Insight e relatório de clientes de Auth SMTP no painel de fluxo de emails
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
description: Os administradores podem aprender a usar o insight e o relatório de autenticação SMTP no painel de fluxo de emails no Centro de Conformidade & e Segurança para monitorar os envios de email em sua organização que usam SMTP autenticado (SMTP AUTH) para enviar mensagens de email.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: afceb767f6ebfeed96deb6362e05bb088b548c3d
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029157"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>Insight e relatório de clientes de Auth SMTP no Centro de Conformidade e & Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Os insights dos clientes de **Auth SMTP** no painel de fluxo de emails e no relatório de clientes de [Auth SMTP](#smtp-auth-clients-report) associados no Centro de Conformidade [do &](https://protection.office.com) de Segurança destacam o uso do protocolo de envio de cliente SMTP AUTH por usuários ou contas do sistema em sua organização. [](mail-flow-insights-v2.md) Esse protocolo herdado (que usa o ponto de extremidade smtp.office365.com) só oferece autenticação Básica e é suscetível a ser usado por contas comprometidas para enviar emails. O insight e o relatório permitem que você verifique se há atividades incomuns para envios de email SMTP AUTH. Ele também mostra os dados de uso do TLS para clientes ou dispositivos que usam SMTP AUTH.

O widget indica o número de usuários ou contas de serviço que usaram o protocolo de Auth SMTP nos últimos 7 dias.

![Widget de clientes de Auth SMTP no painel Fluxo de emails no Centro de Conformidade e Segurança & Segurança](../../media/mfi-smtp-auth-clients-report-widget.png)

Se você clicar no número de mensagens no widget, um flyout de clientes **de Auth SMTP** será exibido. O flyout fornece uma exibição agregada do uso e volumes do TLS da última semana.

![Detalhes do flyout depois de clicar no widget de clientes de Auth SMTP no painel de fluxo de emails](../../media/mfi-smtp-auth-clients-report-details.png)

Você pode clicar no link de relatório de clientes de **Auth SMTP** para ir para o relatório de clientes de Auth SMTP, conforme descrito na próxima seção.

## <a name="smtp-auth-clients-report"></a>Relatório de clientes de autenticação SMTP

### <a name="report-view-for-the-smtp-auth-clients-report"></a>Exibição de relatório para o relatório de clientes de Auth SMTP

Por padrão, o relatório mostra dados dos últimos 7 dias, mas os dados estão disponíveis para os últimos 90 dias.

A seção visão geral contém os seguintes gráficos:

- Exibir dados por: Volume de **envio:** Por padrão, o gráfico mostra o número de mensagens de cliente de Auth SMTP que foram enviadas de todos os domínios ( Mostrar dados para: Todos os domínios de remetentes são **selecionados** por padrão). Você pode filtrar os resultados para um  domínio de remetente específico clicando em Mostrar dados e selecionando o domínio do remetente na lista suspenso. Se você passar o mouse sobre um ponto de dados específico (dia), o número de mensagens será mostrado.

  ![Exibição de volume de envio no relatório de clientes de Auth SMTP no Centro de Conformidade & Segurança](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **Exibir dados por: Uso de TLS:** o gráfico mostra a porcentagem de uso de TLS para todas as mensagens de cliente de Auth SMTP durante o período de tempo selecionado. Este gráfico permite identificar e tomar medidas em usuários e contas do sistema que ainda usam versões mais antigas do TLS.

  ![Exibição de uso do TLS no relatório de clientes de Auth SMTP no Centro de Conformidade & Segurança](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

Se você clicar em **Filtros** em uma exibição de relatório, poderá especificar um intervalo de datas com data **de** início **e data de término.**

Clique **em Solicitar relatório** para receber uma versão mais detalhada do relatório em uma mensagem de email. Você pode especificar o intervalo de datas e os destinatários para receber o relatório.

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>Visão de tabela de detalhes do relatório de clientes de Auth SMTP

Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:

- **Exibir dados por: Volume de envio:** as seguintes informações são mostradas em uma tabela:

  - **Endereço do remetente**.
  - **Contagem de mensagem**

  Se você selecionar uma linha, os mesmos detalhes serão mostrados em um flyout.

- **Exibir dados por: Uso do TLS:** as seguintes informações são mostradas em uma tabela:

  - **Endereço do remetente**.
  - **TLS1,0%**<sup>\*</sup>
  - **TLS1,1%**<sup>\*</sup>
  - **TLS1,2%**<sup>\*</sup>
  - **Contagem de mensagem**

  <sup>\*</sup> Esta coluna mostra a porcentagem e o número de mensagens do remetente.

Se você clicar em **Filtros** em uma exibição de tabela de detalhes, poderá especificar um intervalo de datas com data **de** início **e data de término.**

Se você selecionar uma linha, detalhes semelhantes serão mostrados em um flyout:

![Detalhes do flyout da tabela de detalhes do ponto de vista de uso do TLS no relatório de clientes de Auth SMTP](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

Clique **em Solicitar relatório** para receber uma versão mais detalhada do relatório em uma mensagem de email. Você pode especificar o intervalo de datas e os destinatários para receber o relatório.

Para voltar para a exibição de relatórios, clique em **Exibir relatório.**

## <a name="related-topics"></a>Tópicos relacionados

Para obter informações sobre outros insights no painel de fluxo de emails, consulte Informações sobre o fluxo de emails no Centro de [Conformidade e & Segurança.](mail-flow-insights-v2.md)
