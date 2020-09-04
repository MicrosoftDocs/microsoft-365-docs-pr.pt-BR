---
title: Relatórios de clientes de autenticação SMTP percepção e relatório no painel de fluxo de emails
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
description: Os administradores podem aprender a usar a percepção e o relatório de autenticação SMTP no painel de fluxo de emails no centro de conformidade de & de segurança para monitorar remetentes de email em sua organização que usam SMTP autenticado (autenticação SMTP) para enviar mensagens de email.
ms.openlocfilehash: 4123edcfa08e31217dcd6a29186492bc036fa7a0
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357429"
---
# <a name="smtp-auth-clients-insight-and-report-in-the-security--compliance-center"></a>Clientes de autenticação SMTP percepção e relatório no centro de conformidade e segurança &

Os **clientes de autenticação SMTP** se aprofundam no [painel de fluxo de emails](mail-flow-insights-v2.md) e no [relatório de clientes de autenticação SMTP](#smtp-auth-clients-report) associado no [centro de conformidade & de segurança](https://protection.office.com) realçar o uso do protocolo de envio de cliente de autenticação SMTP por usuários ou contas de sistema em sua organização. Este protocolo herdado (que usa o ponto de extremidade smtp.office365.com) só oferece autenticação básica e é suscetível a uso por contas comprometidas para enviar emails. A percepção e o relatório permitem verificar se há atividades incomuns para envios de email de autenticação SMTP. Ele também mostra os dados de uso de TLS para clientes ou dispositivos que usam a autenticação SMTP.

O widget indica o número de usuários ou contas de serviço que usaram o protocolo de autenticação SMTP nos últimos sete dias.

![Widget clientes de autenticação SMTP no painel de fluxo de emails no centro de conformidade & segurança](../../media/mfi-smtp-auth-clients-report-widget.png)

Se você clicar no número de mensagens no widget, um submenu de **clientes de autenticação SMTP** será exibido. O submenu fornece uma exibição agregada do uso e dos volumes de TLS para a última semana.

![Submenu de detalhes após clicar no widget clientes de autenticação SMTP no painel de fluxo de emails](../../media/mfi-smtp-auth-clients-report-details.png)

Você pode clicar no link **relatório de clientes de autenticação SMTP** para acessar o relatório de clientes de autenticação SMTP, conforme descrito na próxima seção.

## <a name="smtp-auth-clients-report"></a>Relatório de clientes de autenticação SMTP

### <a name="report-view-for-the-smtp-auth-clients-report"></a>Exibição de relatório para o relatório de clientes de autenticação SMTP

Por padrão, o relatório mostra os dados dos últimos 7 dias, mas os dados estão disponíveis nos últimos 90 dias.

A seção visão geral contém os seguintes gráficos:

- **Exibir dados por: enviando o volume**: por padrão, o gráfico mostra o número de mensagens de cliente de autenticação SMTP que foram enviadas de todos os domínios (**Mostrar dados de: todos os domínios do remetente** estão selecionados por padrão). Você pode filtrar os resultados em um domínio de remetente específico clicando em **Mostrar dados para** e selecionando o domínio do remetente na lista suspensa. Se você focalizar um ponto de dados específico (dia), o número de mensagens será exibido.

  ![Enviando o modo de exibição de volume no relatório de clientes de autenticação SMTP no centro de conformidade & segurança](../../media/mfi-smtp-auth-clients-report-sending-volume-view.png)

- **Exibir dados por: uso de TLS**: o gráfico mostra a porcentagem de uso de TLS para todas as mensagens de cliente de autenticação SMTP durante o período de tempo selecionado. Este gráfico permite identificar e executar ações sobre usuários e contas de sistema que ainda estão usando versões mais antigas do TLS.

  ![Modo de exibição de uso de TLS no relatório de clientes de autenticação SMTP no centro de conformidade & segurança](../../media/mfi-smtp-auth-clients-report-tls-usage-view.png)

Se você clicar em **filtros** em um modo de exibição de relatório, poderá especificar um intervalo de datas com **data de início** e data de **término**.

Clique em **solicitar relatório** para receber uma versão mais detalhada do relatório em uma mensagem de email. Você pode especificar o intervalo de datas e os destinatários que receberão o relatório.

### <a name="details-table-view-for-the-smtp-auth-clients-report"></a>Exibição da tabela de detalhes para o relatório de clientes de autenticação SMTP

Se você clicar em **Exibir tabela de detalhes**, as informações mostradas dependem do gráfico que você estava observando:

- **Exibir dados por: enviando volume**: as informações a seguir são mostradas em uma tabela:

  - **Endereço do remetente**.
  - **Contagem de mensagem**

  Se você selecionar uma linha, os mesmos detalhes serão mostrados em um submenu.

- **Exibir dados por: uso de TLS**: as seguintes informações são mostradas em uma tabela:

  - **Endereço do remetente**.
  - **TLS 1.0%**<sup>\*</sup>
  - **TLS 1.1%**<sup>\*</sup>
  - **TLS 1.2%**<sup>\*</sup>
  - **Contagem de mensagem**

  <sup>\*</sup> Esta coluna mostra a porcentagem e o número de mensagens do remetente.

Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.

Se você selecionar uma linha, os detalhes semelhantes serão mostrados em um submenu:

![Submenu de detalhes da tabela detalhes do modo de exibição uso de TLS no relatório de clientes de autenticação SMTP](../../media/mfi-smtp-auth-clients-report-tls-usage-view-view-details-table-details.png)

Clique em **solicitar relatório** para receber uma versão mais detalhada do relatório em uma mensagem de email. Você pode especificar o intervalo de datas e os destinatários que receberão o relatório.

Para voltar para o modo de exibição relatórios, clique em **Exibir relatório**.

## <a name="related-topics"></a>Tópicos relacionados

Para obter informações sobre outras ideias no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).
