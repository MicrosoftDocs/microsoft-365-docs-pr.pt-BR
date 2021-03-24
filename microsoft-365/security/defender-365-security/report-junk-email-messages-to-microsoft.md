---
title: Relatar mensagens de spam, não spam e phishing para a Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
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
ms.openlocfilehash: 64b5708194d7597b8a2b1a84b51f2196415e56ea
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053631"
---
# <a name="report-messages-and-files-to-microsoft"></a>Relatar mensagens e arquivos à Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, usuários e administradores têm vários métodos diferentes para relatar mensagens de email e arquivos à Microsoft.

****

|Método|Descrição|
|---|---|
|[Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft](admin-submission.md)|O método de relatório recomendado para administradores em organizações com caixas de correio do Exchange Online (não disponíveis no EOP autônomo).|
|[Habilitar o suplemento de Mensagem de Relatório](enable-the-report-message-add-in.md)|Funciona com o Outlook e o Outlook na Web (anteriormente conhecido como Outlook Web App). <p> Dependendo da sua assinatura, as mensagens relatadas pelos usuários com o complemento estão disponíveis no [portal Envios](admin-submission.md)de Administrador, resultados de investigação e resposta [automatizadas (AIR),](air-view-investigation-results.md)no relatório de mensagens relatadas pelo usuário [e](view-email-security-reports.md#user-reported-messages-report)no [Explorador](threat-explorer-views.md#email--submissions)de Ameaças. <p> Você pode configurar mensagens relatadas a serem copiadas ou redirecionadas para uma caixa de correio especificada. Para obter mais informações, consulte [Políticas de envios de usuário](user-submission.md).
|[Habilite o suplemento Relatório de Phishing](enable-the-report-phish-add-in.md)|Funciona com o Outlook e o Outlook na Web (anteriormente conhecido como Outlook Web App). <p> Dependendo da sua assinatura, as mensagens relatadas pelos usuários com o complemento estão disponíveis no [portal Envios](admin-submission.md)de Administrador, resultados de investigação e resposta [automatizadas (AIR),](air-view-investigation-results.md)no relatório de mensagens relatadas pelo usuário [e](view-email-security-reports.md#user-reported-messages-report)no [Explorador](threat-explorer-views.md#email--submissions)de Ameaças. <p> Você pode configurar mensagens relatadas a serem copiadas ou redirecionadas para uma caixa de correio especificada. Para obter mais informações, consulte [Políticas de envios de usuário](user-submission.md).|
|[Instalar e usar o complemento Relatório de Lixo Eletrônico para o Microsoft Outlook](junk-email-reporting-add-in-for-microsoft-outlook.md)|Só funciona no Outlook.|
|[Relatar lixo eletrônico e email de phishing no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Use os recursos integrados no Outlook na Web para organizações com caixas de correio do Exchange Online (não disponíveis no EOP autônomo). <p> As mensagens relatadas pelos usuários estão disponíveis [no portal Envios de Administrador.](admin-submission.md) <p> Você pode configurar mensagens relatadas a serem copiadas ou redirecionadas para uma caixa de correio especificada. Para obter mais informações, consulte [Políticas de envios de usuário](user-submission.md).|
|[Relatar lixo eletrônico e email de phishing no Outlook para iOS e Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|Use os recursos integrados no Outlook para iOS e Android para organizações com caixas de correio do Exchange Online (não disponíveis no EOP autônomo). <p> As mensagens relatadas pelos usuários estão disponíveis [no portal Envios de Administrador.](admin-submission.md) <p> Você pode configurar mensagens relatadas a serem copiadas ou redirecionadas para uma caixa de correio especificada. Para obter mais informações, consulte [Políticas de envios de usuário](user-submission.md).|
|[Enviar mensagens manualmente à Microsoft para análise](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Envie mensagens anexadas manualmente para endereços de email específicos da Microsoft para spam, não spam e phishing.|
|[Usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Saiba como criar uma regra de fluxo de emails (também conhecida como regra de transporte) que o notifica quando os usuários relatam mensagens à Microsoft para análise.|
|[Enviar malware e não malware à Microsoft para análise](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Use o site do Microsoft Security Intelligence para enviar anexos e outros arquivos.|

Se as mensagens de spam ou phishing foram colocadas em quarentena em vez de entregues, os usuários poderão relatar as mensagens à Microsoft do portal de quarentena no Centro de Conformidade & Segurança. Para obter detalhes, [consulte Find and release quarantined messages as a user in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).

> [!NOTE]
> Os dados de envios para a Microsoft residem no limite de conformidade do Office 365 em data centers da América do Norte. Os dados são revisados por analistas na equipe de engenharia para ajudar a melhorar a eficácia dos filtros.
