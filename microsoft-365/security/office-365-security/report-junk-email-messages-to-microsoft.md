---
title: Relatar mensagens de spam, não spam e phishing para a Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender sobre as diferentes maneiras de relatar mensagens e arquivos bons e ruins à Microsoft para análise.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7b062c9529364e9fe26133fd1c039affcb8b7011
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689068"
---
# <a name="report-messages-and-files-to-microsoft"></a>Relatar mensagens e arquivos à Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Em organizações Microsoft 365 com caixas de correio em organizações Exchange Online ou autônomas do Proteção do Exchange Online (EOP) sem caixas de correio Exchange Online, usuários e administradores têm vários métodos diferentes para relatar mensagens de email e arquivos à Microsoft.

<br>

****

|Método|Descrição|
|---|---|
|[Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft](admin-submission.md)|O método de relatório recomendado para administradores em organizações com Exchange Online caixas de correio (não disponíveis no EOP autônomo).|
|[Habilitar a Mensagem de Relatório ou os complementos de Phishing de Relatório](enable-the-report-message-add-in.md)|Funciona com Outlook e Outlook na Web (anteriormente conhecido como Outlook Web App). <p> Dependendo da sua assinatura, as mensagens relatadas pelos usuários com os complementos estão disponíveis no [portal Envios](admin-submission.md)de Administrador, resultados de investigação e resposta [automatizadas (AIR),](air-view-investigation-results.md)no relatório de mensagens relatadas pelo usuário [e](view-email-security-reports.md#user-reported-messages-report)no [Explorador](threat-explorer-views.md#email--submissions)de Ameaças. <p> Você pode configurar mensagens relatadas a serem copiadas ou redirecionadas para uma caixa de correio especificada. Para obter mais informações, consulte [Políticas de envios de usuário](user-submission.md).
|[Relatar falsos positivos e falsos negativos no Outlook](report-false-positives-and-false-negatives.md)|Envie falsos positivos (bons emails bloqueados ou enviados para a pasta lixo eletrônico) e falsos negativos (emails indesejados ou phishing que foram entregues à caixa de entrada) para Proteção do Exchange Online (EOP) usando o recurso Mensagem de Relatório.|
|[Enviar mensagens manualmente à Microsoft para análise](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Envie mensagens anexadas manualmente para endereços de email específicos da Microsoft para spam, não spam e phishing.|
|[Usar as regras de fluxo de correio para ver o que os usuários estão relatando à Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|Saiba como criar uma regra de fluxo de emails (também conhecida como regra de transporte) que o notifica quando os usuários relatam mensagens à Microsoft para análise.|
|[Enviar malware e não malware à Microsoft para análise](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Use o Inteligência de Segurança da Microsoft site para enviar anexos e outros arquivos.|
|

Se as mensagens de spam ou phishing foram colocadas em quarentena em vez de entregues, os usuários poderão relatar as mensagens à Microsoft do portal de quarentena no Centro de Conformidade & Segurança. Para obter detalhes, [consulte Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).

> [!NOTE]
> Os dados de envios para a Microsoft residem no limite Office 365 conformidade nos data centers norte-americanos. Os dados são revisados por analistas na equipe de engenharia para ajudar a melhorar a eficácia dos filtros.
