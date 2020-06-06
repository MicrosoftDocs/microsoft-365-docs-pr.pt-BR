---
title: Relatórios e rastreamento de mensagens
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá sobre relatórios e ferramentas de solução de problemas disponíveis para os administradores do Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: b33d343d9b7f02e32619031d3ecf72ad12f891fd
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588163"
---
# <a name="reporting-and-message-trace-in-eop"></a>Relatórios e rastreamento de mensagens no EOP

Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP oferece vários relatórios diferentes que podem ajudá-lo a determinar o status e a integridade gerais de sua organização. Existem também ferramentas que ajudam você a solucionar problemas com eventos específicos (tais como uma mensagem que não chega aos destinatários pretendidos), e relatórios de auditoria para ajudar nos requisitos de conformidade.

## <a name="usage-reports"></a>Relatórios de uso

**Atividade de grupos do microsoft 365**: exibir informações sobre o número de grupos do Microsoft 365 que são criados e usados.

**Atividade de email**: exibir informações sobre o número de mensagens enviadas, recebidas e lidas em toda sua organização e por usuários específicos.

**Uso do aplicativo de email**: exibir informações sobre os aplicativos de email usados. Isso inclui o número total de conexões para cada aplicativo, e as versões do Outlook que estão se conectando.

**Uso da caixa de correio**: exibir informações sobre o armazenamento usado, consumo de cota, contagem de itens e última atividade (atividade de envio ou leitura) para caixas de correio.

Veja os seguintes recursos para obter mais informações:

- [Relatórios do Microsoft 365 no centro de administração-Microsoft 365 grupos](https://docs.microsoft.com/microsoft-365/admin/activity-reports/office-365-groups)

- [Relatórios do Microsoft 365 no centro de administração-atividade de email](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-activity)

- [Relatórios do Microsoft 365 no centro de administração-uso de aplicativos de email](https://docs.microsoft.com/microsoft-365/admin/activity-reports/email-apps-usage)

- [Relatórios da Microsoft 365 no centro de administração-uso da caixa de correio](https://docs.microsoft.com/microsoft-365/admin/activity-reports/mailbox-usage)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Relatórios de segurança & conformidade no centro de administração do Microsoft 365

Esses relatórios aprimorados fornecem uma experiência de relatório interativa para administradores do EOP, que inclui informações de resumo e a capacidade de aprofundar para obter mais detalhes.

**Proteção avançada contra ameaças (ATP)**: exibir informações sobre links seguros e anexos seguros que fazem parte da ATP.

**EOP**: exibir informações sobre detecções de malware, email falsificado, detecções de spam e fluxo de emails para e da sua organização.

[Exibir relatórios para a proteção avançada contra ameaças do Office 365](view-reports-for-atp.md)

## <a name="custom-reports-using-microsoft-graph"></a>Relatórios personalizados usando o Microsoft Graph

Criar programaticamente relatórios disponíveis no centro de administração usando o Microsoft Graph. Para obter mais informações, consulte [Overview of Microsoft Graph](https://docs.microsoft.com/graph/overview) e [Working with Office 365 Usage reports in Microsoft Graph](https://docs.microsoft.com/graph/api/resources/report).

## <a name="message-trace"></a>Rastreamento de mensagens

Acompanhe as mensagens enviadas conforme elas circulam através di EOP. Você pode determinar se uma mensagem de email foi recebida, rejeitada, adiada ou entregue pelo serviço. Também mostra as ações feitas na mensagem antes de ela chegar em seu status final.

Você pode usar essa informação para responder com eficiência às perguntas dos seus usuários, solucionar problemas de fluxo de email, validar alterações de política e reduzir a necessidade de contatar o suporte técnico para obter assistência.

Consulte [rastreamento de mensagens no centro de conformidade & segurança](message-trace-scc.md).

## <a name="audit-logging"></a>Registro em log de auditoria

Rastreie alterações específica feitas pelos administradores na sua organização. Estes relatórios ajudam você a solucionar problemas de configuração ou a encontrar a causa de problemas relacionados à conformidade ou à segurança. Confira [relatórios de auditoria no EOP](auditing-reports-in-eop.md).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Disponibilidade e latência de dados de relatórios e rastreamento de mensagens

A tabela a seguir descreve quando dados de relatórios e rastreamento de mensagens do EOP estão disponíveis e por quanto tempo.

||||
|:-----|:-----|:-----|
|**Tipo de relatório**|**Dados disponíveis por (período retrospectivo)**|**Latência**|
|Relatórios de Resumo de proteção de email|90 dias|A agregação de dados de mensagens geralmente é concluída em 24 a 48 horas. Algumas pequenas alterações agregadas progressivas podem ocorrer por até 5 dias.|
|Relatórios de detalhes de proteção de email|90 dias|Para obter dados detalhados de um período menor que 7 dias, os dados deverão aparecer no prazo de 24 horas, mas a operação talvez não seja concluída em até 48 horas. Algumas pequenas alterações incrementais podem ocorrer por até 5 dias. <br/><br/> Para exibir relatórios detalhados de mensagens ocorridas em um período superior a sete dias, os resultados podem demorar umas poucas horas.|
|Dados de rastreamento de mensagem|90 dias|Ao rastrear mensagens ocorridas em um período menor que 7 dias, as mensagens devem aparecer no intervalo de 5 a 30 minutos.<br/><br/> Ao rastrear mensagens ocorridas em um período superior a 7 dias, os resultados podem demorar umas poucas horas.|
|

> [!NOTE]
> A disponibilidade e a latência dos dados é a mesma, seja ela solicitada por meio do centro de administração ou do PowerShell remoto.
