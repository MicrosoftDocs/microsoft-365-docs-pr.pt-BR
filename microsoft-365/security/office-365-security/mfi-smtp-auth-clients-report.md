---
title: Relatório de clientes de autenticação SMTP
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
description: Os administradores podem saber mais sobre o relatório de clientes de autenticação SMTP no painel de fluxo de emails no centro de conformidade do & de segurança.
ms.openlocfilehash: a273da9e0ebe7987a22669c54f3ebfe103e5933c
ms.sourcegitcommit: 84d88a857e82b1a8a0d466057a2e330e8b1692e4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37306025"
---
# <a name="smtp-auth-clients-report"></a>Relatório de clientes de autenticação SMTP

O relatório de **clientes de autenticação SMTP** realça o uso do protocolo de envio de cliente de autenticação SMTP por usuários ou contas de sistema em sua organização. Este protocolo herdado (que usa o ponto de extremidade smtp.office365.com) só oferece autenticação básica e é suscetível a uso por contas comprometidas para enviar emails.  Este relatório permite verificar atividades incomuns. Ele também mostra os dados de uso de TLS para clientes ou dispositivos que usam a autenticação SMTP.

O widget que é mostrado no painel de fluxo de emails indica o número de usuários ou contas de serviço que usaram o protocolo de autenticação SMTP nos últimos sete dias.

![O relatório de clientes de autenticação SMTP no painel de fluxo de emails no centro de conformidade & segurança](../media/smtp-auth-clients-report-selected.png)

Clicar no widget abre um submenu que fornece uma exibição agregada do uso e dos volumes de TLS para a última semana.

![O submenu no relatório de clientes de autenticação SMTP](../media/smtp-auth-clients-flyout.png)

Ao clicar no link de **relatório de clientes de autenticação SMTP** , você verá dois dados dinâmicos principais e dois modos de exibição de dados. Os dados dinâmicos são o **volume de envio** e o **uso de TLS**. Os modos de exibição de dados são o gráfico e a tabela de detalhes.

O modo de exibição de **volume de envio** mostra o número de mensagens que foram enviadas usando a autenticação SMTP no intervalo de tempo especificado. Você pode ajustar o intervalo clicando em **filtros**. O gráfico é organizado por domínio de remetente. Você pode ver dados separados para cada domínio selecionando o domínio na lista suspensa **Mostrar dados para** .

![Enviando o volume no relatório de clientes de autenticação SMTP](../media/smtp-auth-clients-report-sending-volume.png)

Você pode exibir informações detalhadas sobre os remetentes e suas contagens de mensagens clicando em **Exibir detalhes tabela**. Para retornar ao gráfico, clique em **Exibir relatório**.

![Tabela de detalhes para o envio de volume no relatório de clientes de autenticação SMTP](../media/smtp-auth-clients-report-details-sending-volume.png)

A tabela dinâmica de **uso de TLS** é importante devido à futura substituição de TLS 1.0 e TLS 1.1 no Office 365. Muitos dispositivos e aplicativos herdados não poderão enviar emails se eles só forem capazes de usar o TLS 1.0 com autenticação SMTP. Essa tabela dinâmica permite que você identifique e execute ações sobre usuários e contas de sistema que ainda estão usando versões mais antigas do TLS.

![Uso de TLS no relatório de clientes de autenticação SMTP](../media/smtp-auth-clients-report-tls-usage.png)

Você pode exibir informações detalhadas sobre os remetentes, as versões do TLS que estão usando a autenticação SMTP e suas contagens de mensagens clicando em **Exibir detalhes tabela**. Para retornar ao gráfico, clique em **Exibir relatório**.

Você também pode baixar uma versão mais detalhada do relatório clicando em solicitação de relatório.

![Tabela de detalhes para uso de TLS no relatório de clientes de autenticação SMTP](../media/smtp-auth-clients-report-details-tls-usage.png)

## <a name="see-also"></a>Confira também

Para obter mais informações sobre outros insights de fluxo de email no painel de fluxo de emails, consulte [Mail Flow insights no centro de conformidade de & de segurança](mail-flow-insights-v2.md).
