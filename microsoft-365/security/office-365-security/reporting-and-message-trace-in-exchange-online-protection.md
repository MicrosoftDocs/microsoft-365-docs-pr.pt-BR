---
title: Relatórios e rastreamento de mensagens
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá sobre relatórios e ferramentas de solução de problemas disponíveis para administradores Microsoft Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 079e2b359f28b0b6bc3d7eac86e69060c65ea250
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841433"
---
# <a name="reporting-and-message-trace-in-eop"></a>Rastreamento de relatórios e mensagens no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Em organizações Microsoft 365 com caixas de correio em organizações Exchange Online ou autônomas do Proteção do Exchange Online (EOP) sem caixas de correio Exchange Online, o EOP oferece muitos relatórios diferentes que podem ajudá-lo a determinar o status geral e a saúde da sua organização. Existem também ferramentas que ajudam você a solucionar problemas com eventos específicos (tais como uma mensagem que não chega aos destinatários pretendidos), e relatórios de auditoria para ajudar nos requisitos de conformidade.

## <a name="usage-reports"></a>Relatórios de uso

**Microsoft 365 de grupos**: Exibir informações sobre o número de grupos Microsoft 365 que são criados e usados.

**Atividade de email**: Exibir informações sobre o número de mensagens enviadas, recebidas e lidas em toda a organização e por usuários específicos.

**Uso do aplicativo de** email : Exibir informações sobre os aplicativos de email usados. Isso inclui o número total de conexões para cada aplicativo, e as versões do Outlook que estão se conectando.

**Uso da** caixa de correio : Exibir informações sobre armazenamento usado, consumo de cota, contagem de itens e última atividade (atividade de envio ou leitura) para caixas de correio.

Veja os seguintes recursos para obter mais informações:

- [Microsoft 365 Relatórios no centro de administração - Microsoft 365 grupos](../../admin/activity-reports/office-365-groups.md)
- [Microsoft 365 Relatórios no centro de administração - Atividade de email](../../admin/activity-reports/email-activity.md)
- [Microsoft 365 Relatórios no centro de administração - Uso de aplicativos de email](../../admin/activity-reports/email-apps-usage.md)
- [Microsoft 365 Relatórios no centro de administração - Uso da caixa de correio](../../admin/activity-reports/mailbox-usage.md)

## <a name="security--compliance-reports-in-the-microsoft-365-admin-center"></a>Relatórios & de conformidade de segurança no Microsoft 365 de administração

Esses relatórios aprimorados fornecem uma experiência interativa de relatórios para os administradores do EOP, que inclui informações resumidas e a capacidade de detalhar para obter mais detalhes.

**Defender for Office 365**: Exibir informações sobre Cofre Links e Cofre anexos que fazem parte do Microsoft Defender para Office 365.

**EOP**: Exibir informações sobre detecções de malware, emails empoados, detecções de spam e fluxo de emails de e para sua organização.

[Exibir relatórios do Defender para Office 365](view-reports-for-mdo.md)

## <a name="custom-reports-using-microsoft-graph"></a>Relatórios personalizados usando o Microsoft Graph

Crie relatórios programaticamente disponíveis no centro de administração usando o Microsoft Graph. Para obter mais informações, consulte [Overview of Microsoft Graph](/graph/overview) and Working with Office 365 usage reports in Microsoft [Graph](/graph/api/resources/report).

## <a name="message-trace"></a>Rastreamento de mensagens

Acompanhe as mensagens enviadas conforme elas circulam através di EOP. Você pode determinar se uma mensagem de email foi recebida, rejeitada, adiada ou entregue pelo serviço. Também mostra as ações feitas na mensagem antes de ela chegar em seu status final.

Você pode usar essa informação para responder com eficiência às perguntas dos seus usuários, solucionar problemas de fluxo de email, validar alterações de política e reduzir a necessidade de contatar o suporte técnico para obter assistência.

Consulte [Rastreamento de mensagens no Centro de Conformidade & segurança.](message-trace-scc.md)

## <a name="audit-logging"></a>Registro em log de auditoria

Rastreie alterações específica feitas pelos administradores na sua organização. Estes relatórios ajudam você a solucionar problemas de configuração ou a encontrar a causa de problemas relacionados à conformidade ou à segurança. Consulte [Relatórios de auditoria em Exchange Online](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports).

## <a name="reporting-and-message-trace-data-availability-and-latency"></a>Disponibilidade e latência de dados de relatórios e rastreamento de mensagens

A tabela a seguir descreve quando dados de relatórios e rastreamento de mensagens do EOP estão disponíveis e por quanto tempo.

****

|Tipo de relatório|Dados disponíveis por (período retrospectivo)|Latência|
|---|---|---|
|Relatórios de resumo de proteção de email|90 dias|A agregação de dados de mensagens geralmente é concluída em 24 a 48 horas. Algumas pequenas alterações agregadas progressivas podem ocorrer por até 5 dias.|
|Relatórios detalhados de proteção de email|90 dias|Para obter dados detalhados de um período menor que 7 dias, os dados deverão aparecer no prazo de 24 horas, mas a operação talvez não seja concluída em até 48 horas. Algumas pequenas alterações incrementais podem ocorrer por até 5 dias. <p> Para exibir relatórios detalhados de mensagens ocorridas em um período superior a sete dias, os resultados podem demorar umas poucas horas.|
|Dados de rastreamento de mensagem|90 dias|Ao rastrear mensagens ocorridas em um período menor que 7 dias, as mensagens devem aparecer no intervalo de 5 a 30 minutos.<p> Ao rastrear mensagens ocorridas em um período superior a 7 dias, os resultados podem demorar umas poucas horas.|
|

> [!NOTE]
> A disponibilidade e a latência de dados são as mesmas solicitadas por meio do centro de administração ou do PowerShell remoto.
