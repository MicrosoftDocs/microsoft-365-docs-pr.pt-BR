---
title: Visão geral do painel de segurança
f1.keywords:
- NOCSH
ms.author: siosulli
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Use o novo painel de segurança para analisar o status de proteção contra ameaças do Office 365 e exibir e agir em alertas de segurança.
ms.openlocfilehash: b49422621e70d597251cd342559e59ffa0e128f6
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877320"
---
# <a name="security-dashboard"></a>Painel de segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a>Funções básicas e como abrir o painel de segurança

O [centro de conformidade & segurança](../../compliance/go-to-the-securitycompliance-center.md) permite que sua organização gerencie a proteção e a conformidade dos dados. Supondo que você tenha as permissões necessárias, o painel de segurança permite que você revise o status da proteção contra ameaças, bem como o modo de exibição e agir nos alertas de segurança.

Assista ao vídeo para obter uma visão geral e leia este artigo para saber mais.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

Dependendo da assinatura que a sua organização inclui, o painel de segurança inclui vários widgets, como Resumo de gerenciamento de ameaças, status de proteção contra ameaças, detecções semanais globais de ameaças, malware e muito mais, conforme descrito nas seções a seguir.

Para exibir o painel de segurança, no [centro de conformidade & segurança](../../compliance/go-to-the-securitycompliance-center.md), vá para o painel **Gerenciamento de ameaças** \> **Dashboard**.

> [!NOTE]
> Você deve ser um administrador global, um administrador de segurança ou um leitor de segurança para exibir o painel de segurança. Alguns widgets exigem permissões adicionais para exibir. Para saber mais, confira [permissões no centro de conformidade de & de segurança](permissions-in-the-security-and-compliance-center.md).

## <a name="threat-management-summary"></a>Resumo de gerenciamento de ameaças

O widget Resumo de gerenciamento de ameaças informa rapidamente como sua organização foi protegida contra ameaças nos últimos sete (7) dias.

![Painel de segurança-widget Resumo de gerenciamento de ameaças](../../media/SecDash-ThreatMgmtSummary.png)

As informações que você verá no Resumo de gerenciamento de ameaças depende do que a assinatura inclui. A tabela a seguir descreve quais informações estão incluídas para o Office 365 E3 e o Office 365 e5.

|Office 365 E3|Office 365 E5|
|---|---|
|Mensagens de malware bloqueadas<br/>Mensagens de phishing bloqueadas<br>Mensagens relatadas por usuários<br><br><br><br>|Mensagens de malware bloqueadas<br>Mensagens de phishing bloqueadas<br>Mensagens relatadas por usuários<br>Malware de dia zero bloqueado<br>Mensagens de phishing avançadas detectadas<br>URLs mal-intencionadas bloqueadas|

Para exibir ou acessar o widget Resumo de gerenciamento de ameaças, você deve ter permissões para exibir os relatórios do defender for Office 365. Para saber mais, veja [quais permissões são necessárias para exibir os relatórios do defender for Office 365?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).

## <a name="threat-protection-status"></a>Status de proteção contra ameaças

O widget status de proteção contra ameaças mostra a eficácia da proteção contra ameaças com uma visão detalhada e de tendências de phishing e malware.

![Widget status de proteção contra ameaças](../../media/tpswidget.png)

Os detalhes dependem de sua assinatura do Microsoft 365 incluir o [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) com ou sem [o Microsoft Defender para Office 365](office-365-atp.md).

|Se sua assinatura incluir...|Você verá estes detalhes|
|---|---|
|EOP mas não o Microsoft defender para Office 365|Email mal-intencionado detectado e bloqueado pelo EOP.<br><br> Consulte [relatório de status de proteção contra ameaças (EOP)](view-email-security-reports.md#threat-protection-status-report).|
|Microsoft Defender para Office 365|Conteúdo mal-intencionado e email mal-intencionado detectados e bloqueados pelo EOP e defender para Office 365<br><br>Contagem agregada de mensagens de email exclusivas com conteúdo mal-intencionado bloqueado pelo Mecanismo Antimalware, [limpeza automática de zero horas](zero-hour-auto-purge.md)e recursos do defender para Office 365 (incluindo [links seguros](atp-safe-links.md), [anexos seguros](atp-safe-attachments.md)e [anti-phishing no defender para Office 365](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).<br><br>Consulte [relatório de status de proteção contra ameaças](view-reports-for-atp.md#threat-protection-status-report).|

Para exibir ou acessar o widget status de proteção contra ameaças, você deve ter permissões para exibir os relatórios do defender for Office 365. Para saber mais, veja [quais permissões são necessárias para exibir os relatórios do defender for Office 365?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="global-weekly-threat-detections"></a>Detecções semanais globais de ameaças

O widget global Weekly detecções de ameaças mostra quantas ameaças foram detectadas nas mensagens de email nos últimos sete (7) dias.

![Widget global semanal de detecções de ameaças](../../media/globalweeklythreatdetections.png)

As métricas são calculadas conforme descrito na tabela a seguir:

|Indicador|Como é calculado|
|---|---|
|Mensagens verificadas|Número de mensagens de email verificadas multiplicadas pelo número de destinatários|
|Ameaças interrompidas|Número de mensagens de email identificadas como contendo malware multiplicado pelo número de destinatários|
|Bloqueado pelo [defender para Office 365 ](office-365-atp.md)|Número de mensagens de email bloqueadas pelo defender para Office 365 multiplicadas pelo número de destinatários|
|Removido após a entrega|Número de mensagens removidas por [limpeza automática de zero hora](zero-hour-auto-purge.md) multiplicado pelo número de destinatários|

## <a name="malware"></a>Malware

Os widgets de malware mostram detalhes sobre tendências de malware e tipos de família de malware nos últimos sete (7) dias.

![Tendências de malware e tipos de família](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>Informações

Insights não apenas os principais problemas de superfície que você deve examinar, também incluem recomendações e ações a serem consideradas.

![Ideias inteligentes](../../media/smartinsights.png)

Por exemplo, você pode ver que as mensagens de email de phishing estão sendo entregues, pois alguns usuários desabilitaram suas opções de lixo eletrônico. Para saber mais sobre como as ideias funcionam, confira [relatórios e insights no centro de conformidade do & de segurança](reports-and-insights-in-security-and-compliance.md).

## <a name="threat-investigation-and-response"></a>Investigação e resposta a ameaças

Se a assinatura de sua organização incluir o  [Microsoft defender para Office 365 plano 2](office-365-ti.md), o painel de segurança tem uma seção que inclui a investigação avançada de ameaças e ferramentas de resposta. Essas ferramentas incluem [investigação automatizada e recursos de resposta](automated-investigation-response-office.md). A investigação e a resposta automatizadas podem ser úteis em cenários como [endereçar contas de usuário comprometidas rapidamente](address-compromised-users-quickly.md).

Para saber mais, confira [introdução ao uso de investigação e resposta automatizadas (Air) no Office 365](office-365-air.md).

## <a name="trends"></a>Tendências

Próximo à parte inferior do painel de segurança está uma seção de **tendências** , que resume as tendências de fluxo de emails da sua organização. Os relatórios fornecem informações sobre emails categorizados como spam, malware, tentativas de phishing e bons emails. Clique em um bloco para exibir informações mais detalhadas no relatório.

![A seção tendências resume as tendências de fluxo de emails da organização](../../media/trends.png)

E, se a assinatura de sua organização incluir o [defender para Office 365 plano 2](office-365-ti.md), você também terá um relatório **recente de alertas de gerenciamento de ameaças** nesta seção que permite que sua equipe de segurança exiba e execute ações em alertas de segurança de alta prioridade.

Para exibir ou acessar o widget email enviado e recebido, você deve ter permissões para exibir os relatórios do defender for Office 365. Para saber mais, veja [quais permissões são necessárias para exibir os relatórios do defender for Office 365?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports).

Para exibir ou acessar o widget alertas de gerenciamento de ameaças recentes, você deve ter permissões para exibir alertas. Para saber mais, veja [permissões RBAC necessárias para exibir alertas](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts).

## <a name="related-topics"></a>Tópicos relacionados

[Exibir relatórios de segurança de email no centro de conformidade & segurança](view-email-security-reports.md)

[Exibir relatórios do Microsoft defender para Office 365](view-reports-for-atp.md)

[Defender para Office 365](office-365-atp.md)

[Investigação e resposta contra ameaças do Office 365](office-365-ti.md)
