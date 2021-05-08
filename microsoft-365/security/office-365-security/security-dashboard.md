---
title: Visão geral do painel de segurança
f1.keywords:
- NOCSH
ms.author: siosulli
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Use o novo Painel de Segurança para analisar Office 365 Status da Proteção contra Ameaças e exibir e agir em alertas de segurança.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71c077853c8dbb68b78c8073f650bcb2df4d1b9a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246448"
---
# <a name="security-dashboard"></a>Painel de Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a>Funções básicas e como abrir o Painel de Segurança

O [Centro de Conformidade & segurança](../../compliance/microsoft-365-compliance-center.md) permite que sua organização gerencie a proteção e a conformidade de dados. Supondo que você tenha as permissões necessárias, o Painel de Segurança permite que você revise seu Status de Proteção contra Ameaças, bem como exibir e agir em alertas de segurança.

Assista ao vídeo para obter uma visão geral e leia este artigo para saber mais.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

Dependendo do que a assinatura da sua organização inclui, o Painel de Segurança inclui vários widgets, como Resumo de Gerenciamento de Ameaças, Status de Proteção contra Ameaças, Detecções Semanais Globais de Ameaças, Malware e muito mais, conforme descrito nas seções a seguir.

Para exibir o Painel de Segurança, no Centro de Conformidade & [segurança,](../../compliance/microsoft-365-compliance-center.md)vá para **Painel de gerenciamento de** \> **ameaças.**

> [!NOTE]
> Você deve ser um administrador global, um administrador de segurança ou um leitor de segurança para exibir o Painel de Segurança. Alguns widgets exigem permissões adicionais para exibição. Para saber mais, confira Permissões no Centro de [Conformidade & Segurança.](permissions-in-the-security-and-compliance-center.md)

## <a name="threat-management-summary"></a>Resumo do Gerenciamento de Ameaças

O widget Resumo do Gerenciamento de Ameaças informa rapidamente como sua organização foi protegida contra ameaças nos últimos sete (7) dias.

![Painel de Segurança - Widget resumo do gerenciamento de ameaças](../../media/SecDash-ThreatMgmtSummary.png)

As informações que você verá no Resumo de Gerenciamento de Ameaças dependem do que sua assinatura inclui. A tabela a seguir descreve quais informações são incluídas para Office 365 E3 e Office 365 E5.

|Office 365 E3|Office 365 E5|
|---|---|
|Mensagens de malware bloqueadas<br>Mensagens de phishing bloqueadas<br>Mensagens relatadas por usuários<br><br><br><br>|Mensagens de malware bloqueadas<br>Mensagens de phishing bloqueadas<br>Mensagens relatadas por usuários<br>Malware zero-day bloqueado<br>Mensagens de phishing avançadas detectadas<br>URLs mal-intencionadas bloqueadas|

Para exibir ou acessar o widget Resumo do Gerenciamento de Ameaças, você deve ter permissões para exibir o Defender para Office 365 relatórios. Para saber mais, confira [Quais permissões são necessárias para exibir o Defender para Office 365 relatórios?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).

## <a name="threat-protection-status"></a>Status da Proteção contra Ameaças

O widget Status da Proteção contra Ameaças mostra a eficácia da proteção contra ameaças com uma exibição detalhada e tendência de phishing e malware.

![Widget de status de proteção contra ameaças](../../media/tpswidget.png)

Os detalhes dependem se sua assinatura Microsoft 365 [](exchange-online-protection-overview.md) inclui Proteção do Exchange Online (EOP) com ou sem [o Microsoft Defender para Office 365](defender-for-office-365.md).

|Se sua assinatura incluir...|Você verá esses detalhes|
|---|---|
|EOP, mas não o Microsoft Defender para Office 365|Email mal-intencionado detectado e bloqueado pelo EOP.<p> Consulte [Threat Protection Status report (EOP)](view-email-security-reports.md#threat-protection-status-report).|
|Microsoft Defender para Office 365|Conteúdo mal-intencionado e emails mal-intencionados detectados e bloqueados pelo EOP e pelo Defender para Office 365 <p> Contagem agregada de mensagens de email exclusivas com conteúdo mal-intencionado bloqueado pelo mecanismo anti-malware, limpeza automática de hora [zero](zero-hour-auto-purge.md)e o Defender para recursos Office 365 (incluindo links de [Cofre](safe-links.md), [anexos Cofre](safe-attachments.md)e [anti-phishing](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)no Defender para Office 365 ). <p> Consulte [Relatório de status de proteção contra ameaças.](view-reports-for-mdo.md#threat-protection-status-report)|

Para exibir ou acessar o widget Status da Proteção contra Ameaças, você deve ter permissões para exibir o Defender para Office 365 relatórios. Para saber mais, confira [Quais permissões são necessárias para exibir o Defender para Office 365 relatórios?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="global-weekly-threat-detections"></a>Detecções Semanais Globais de Ameaças

O widget Detecções Semanais Globais de Ameaças mostra quantas ameaças foram detectadas em mensagens de email nos últimos sete (7) dias.

![Widget Global Weekly Threat Detections](../../media/globalweeklythreatdetections.png)

As métricas são calculadas conforme descrito na tabela a seguir:

|Indicador|Como ele é calculado|
|---|---|
|Mensagens examinadas|Número de mensagens de email digitalizada multiplicada pelo número de destinatários|
|Ameaças interrompidas|Número de mensagens de email identificadas como contendo malware multiplicado pelo número de destinatários|
|Bloqueado pelo [Defender para Office 365](defender-for-office-365.md)|Número de mensagens de email bloqueadas pelo Defender Office 365 multiplicado pelo número de destinatários|
|Removido após a entrega|Número de mensagens removidas pela [limpeza automática de hora zero](zero-hour-auto-purge.md) multiplicada pelo número de destinatários|

## <a name="malware"></a>Malware

Os widgets de malware mostram detalhes sobre tendências de malware e tipos de família de malware nos últimos sete (7) dias.

![Tendências de malware e tipos de família](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>Insights

Insights não apenas problemas de superfície que você deve revisar, eles também incluem recomendações e ações a considerar.

![Insights inteligentes](../../media/smartinsights.png)

Por exemplo, você pode ver que mensagens de email de phishing estão sendo entregues porque alguns usuários desabilitam suas opções de lixo eletrônico. Para saber mais sobre como funcionam as informações, consulte [Relatórios e percepções no Centro](reports-and-insights-in-security-and-compliance.md)de Conformidade & Segurança.

## <a name="threat-investigation-and-response"></a>Investigação e resposta a ameaças

Se a assinatura da sua organização incluir o Microsoft Defender para Office 365 [Plano 2](office-365-ti.md), seu Painel de Segurança terá uma seção que inclui ferramentas avançadas de investigação e resposta contra ameaças. Essas ferramentas [incluem recursos automatizados de investigação e resposta.](automated-investigation-response-office.md) A investigação e a resposta automatizadas podem ser úteis em cenários como o [endereçamento de contas de usuário comprometidas rapidamente.](address-compromised-users-quickly.md)

Para saber mais, consulte [Get started using Automated investigation and response (AIR) in Office 365](office-365-air.md).

## <a name="trends"></a>Tendências

Na parte inferior do Painel de Segurança está uma seção **Tendências,** que resume as tendências de fluxo de email para sua organização. Os relatórios fornecem informações sobre emails categorizados como spam, malware, tentativas de phishing e bons emails. Clique em um azulejo para exibir informações mais detalhadas no relatório.

![A seção Tendências resume as tendências de fluxo de email para a organização](../../media/trends.png)

E, se a assinatura da sua organização incluir o Defender para Office 365 [Plano 2](office-365-ti.md), você também terá um relatório de **alertas** de gerenciamento de ameaças recentes nesta seção que permite que sua equipe de segurança extiver e tomar medidas em alertas de segurança de alta prioridade.

Para exibir ou acessar o widget Email Enviado e Recebido, você deve ter permissões para exibir o Defender para Office 365 relatórios. Para saber mais, confira [Quais permissões são necessárias para exibir o Defender para Office 365 relatórios?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).

Para exibir ou acessar o widget Alertas de Gerenciamento de Ameaças Recentes, você deve ter permissões para exibir alertas. Para saber mais, confira [permissões do RBAC necessárias para exibir alertas](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts).

## <a name="related-topics"></a>Tópicos relacionados

[Exibir relatórios de segurança de email no Centro de Conformidade & Segurança](view-email-security-reports.md)

[Exibir relatórios do Microsoft Defender para Office 365](view-reports-for-mdo.md)

[Defender para Office 365](defender-for-office-365.md)

[Office 365 Resposta e investigação de ameaças](office-365-ti.md)