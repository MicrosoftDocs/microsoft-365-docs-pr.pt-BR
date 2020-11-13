---
title: Relatar mensagens de spam, não spam e phishing à Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender sobre as diferentes maneiras de relatar mensagens e arquivos bons e ruins para a Microsoft para análise.
ms.openlocfilehash: 379393919274662554522e21e98637105bc82287
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49020898"
---
# <a name="report-messages-and-files-to-microsoft"></a>Relatar mensagens e arquivos à Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, tanto usuários quanto administradores têm vários métodos diferentes para relatar mensagens e arquivos de email à Microsoft.

****

|Método|Descrição|
|---|---|
|[Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft](admin-submission.md)|O método de relatório recomendado para administradores em organizações com caixas de correio do Exchange Online (não está disponível em EOP autônomos).|
|[Habilitar o suplemento de Mensagem de Relatório](enable-the-report-message-add-in.md)|Funciona com o Outlook, o Outlook para Mac e o Outlook na Web (anteriormente conhecido como Outlook Web App) e é o suplemento recomendado. <p> Dependendo da sua assinatura, as mensagens que os usuários relataram com o suplemento estão disponíveis no [portal de envios do administrador](admin-submission.md), [resultados de investigação e resposta automatizados (Air)](air-view-investigation-results.md), o [relatório de mensagens relatadas pelo usuário](view-email-security-reports.md#user-reported-messages-report)e o [Explorador de ameaças](threat-explorer-views.md#email--submissions). <p> Você pode configurar mensagens relatadas para serem copiadas ou redirecionadas para uma caixa de correio que você especificar. Para obter mais informações, consulte [políticas de envios de usuários](user-submission.md).|
|[Instalar e usar o suplemento relatório de lixo eletrônico para o Microsoft Outlook](junk-email-reporting-add-in-for-microsoft-outlook.md)|O só funciona no Outlook.|
|[Relatar emails de lixo eletrônico e phishing no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Use os recursos internos do Outlook na Web para organizações com caixas de correio do Exchange Online (não estão disponíveis em EOP autônomos). <p> Mensagens que o relatório de usuários estão disponíveis no [portal de envios de administradores](admin-submission.md). <p> Você pode configurar mensagens relatadas para serem copiadas ou redirecionadas para uma caixa de correio que você especificar. Para obter mais informações, consulte [políticas de envios de usuários](user-submission.md).|
|[Relatar emails de lixo eletrônico e phishing no Outlook para iOS e Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|Use os recursos internos do Outlook para iOS um Android para organizações com caixas de correio do Exchange Online (não está disponível em EOP autônomos). <p> Mensagens que o relatório de usuários estão disponíveis no [portal de envios de administradores](admin-submission.md). <p> Você pode configurar mensagens relatadas para serem copiadas ou redirecionadas para uma caixa de correio que você especificar. Para obter mais informações, consulte [políticas de envios de usuários](user-submission.md).|
|[Enviar mensagens manualmente para a Microsoft para análise](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Enviar manualmente mensagens anexadas para endereços de email específicos da Microsoft para spam, não spam e phishing.|
|[Usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Saiba como criar uma regra de fluxo de emails (também conhecida como regra de transporte) que o notifica quando os usuários relatam mensagens para a Microsoft para análise.
|||
|[Enviar malware e não malware para a Microsoft para análise](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Use o site do Microsoft Security Intelligence para enviar anexos e outros arquivos.|

Se as mensagens de spam ou phishing foram colocadas em quarentena em vez de entregues, os usuários podem relatar as mensagens para a Microsoft do portal de quarentena no centro de conformidade do & de segurança. Para obter detalhes, consulte [Localizar e liberar mensagens em quarentena como um usuário no Microsoft 365](find-and-release-quarantined-messages-as-a-user.md).
