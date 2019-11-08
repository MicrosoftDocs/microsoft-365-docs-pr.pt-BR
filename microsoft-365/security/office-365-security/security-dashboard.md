---
title: Visão geral do painel de segurança
ms.author: deniseb
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
description: Use o novo painel de segurança para analisar o status de proteção contra ameaças do Office 365 e exibir e agir em alertas de segurança.
ms.openlocfilehash: 8ce6e21bcc25853e641ee20126ffd38c785e76f7
ms.sourcegitcommit: b424ea039c5915975f3efce8793bfc8dd2fdf906
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38033932"
---
# <a name="security-dashboard"></a>Painel de segurança

## <a name="overview"></a>Visão geral

O [Centro &amp; de conformidade de segurança](../../compliance/go-to-the-securitycompliance-center.md) permite que sua organização gerencie a proteção e a conformidade dos dados. Supondo que você tenha as permissões necessárias, o painel de segurança permite que você revise o status da proteção contra ameaças, bem como o modo de exibição e agir nos alertas de segurança. 
  
Assista ao vídeo para obter uma visão geral e leia este artigo para saber mais.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]
  
Dependendo da sua assinatura do Office 365 da sua organização, o painel de segurança inclui vários widgets, como Resumo de gerenciamento de ameaças, status da proteção contra ameaças, detecções semanais globais de ameaças, malware e muito mais, conforme descrito no seções a seguir.
  
Para exibir o painel de segurança, no [centro de conformidade &amp; de segurança do Office 365](../../compliance/go-to-the-securitycompliance-center.md), vá para o **painel** **Gerenciamento** \> de ameaças.
  
> [!NOTE]
> Você deve ser um administrador global do Office 365, um administrador de segurança ou um leitor de segurança para exibir o painel de segurança. Alguns widgets exigem permissões adicionais para exibir. Para saber mais, confira [permissões no centro de conformidade &amp; de segurança do Office 365](permissions-in-the-security-and-compliance-center.md). 
  
## <a name="threat-management-summary"></a>Resumo de gerenciamento de ameaças

O widget Resumo de gerenciamento de ameaças informa rapidamente como sua organização foi protegida contra ameaças nos últimos sete (7) dias.

![Painel de segurança-widget Resumo de gerenciamento de ameaças](../media/SecDash-ThreatMgmtSummary.png)

As informações que você verá no Resumo de gerenciamento de ameaças depende do que a assinatura inclui. A tabela a seguir descreve quais informações estão incluídas para o Office 365 E3 e o Office 365 e5.


|Office 365 E3  |Office 365 E5  |
|---------|---------|
|Mensagens de malware bloqueadas<br/>Mensagens de phishing bloqueadas<br>Mensagens relatadas por usuários<br><br><br><br> |Mensagens de malware bloqueadas<br>Mensagens de phishing bloqueadas<br>Mensagens relatadas por usuários<br>Malware de dia zero bloqueado<br>Mensagens de phishing avançadas detectadas<br>URLs mal-intencionadas bloqueadas |

Para exibir ou acessar o widget Resumo de gerenciamento de ameaças, você deve ter permissões para exibir relatórios de proteção avançada contra ameaças. Para saber mais, veja [quais permissões são necessárias para exibir os relatórios ATP?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports). 

## <a name="threat-protection-status"></a>Status de proteção contra ameaças

O widget status de proteção contra ameaças mostra a eficácia da proteção contra ameaças com uma visão detalhada e de tendências de phishing e malware. 

![Widget status de proteção contra ameaças](../media/tpswidget.png)

Os detalhes dependem de sua assinatura do Office 365 incluir o [Exchange Online Protection](exchange-online-protection-eop.md) (EOP) com ou sem o [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP).


|Se sua assinatura incluir... |Você verá estes detalhes |
|---------|---------|
|EOP mas não Office 365 ATP     |Email mal-intencionado detectado e bloqueado pelo EOP<br> Consulte [relatório de status de proteção contra ameaças (EOP)](../../compliance/view-email-security-reports.md#threat-protection-status-report).| 
|Office 365 ATP |Conteúdo mal-intencionado e email mal-intencionado detectados e bloqueados pelo EOP e pelo Office 365 ATP<br>Contagem agregada de mensagens de email exclusivas com conteúdo mal-intencionado bloqueado pelo Mecanismo Antimalware, [limpeza automática de zero horas](zero-hour-auto-purge.md)e recursos ATP (incluindo [links seguros](atp-safe-links.md), [anexos seguros](atp-safe-attachments.md)e [anti-phishing](atp-anti-phishing.md)).<br>Consulte [relatório de status de proteção contra ameaças (ATP)](view-reports-for-atp.md#threat-protection-status-report). | 

Para exibir ou acessar o widget status de proteção contra ameaças, você deve ter permissões para exibir relatórios de proteção avançada contra ameaças. Para saber mais, veja [quais permissões são necessárias para exibir os relatórios ATP?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports). 

## <a name="global-weekly-threat-detections"></a>Detecções semanais globais de ameaças
 
O widget global Weekly detecções de ameaças mostra quantas ameaças foram detectadas nas mensagens de email nos últimos sete (7) dias.

![Widget global semanal de detecções de ameaças](../media/globalweeklythreatdetections.png)

As métricas são calculadas conforme descrito na tabela a seguir:

|Indicador  |Como é calculado  |
|---------|---------|
|Mensagens verificadas |Número de mensagens de email verificadas multiplicadas pelo número de destinatários |
|Ameaças interrompidas  |Número de mensagens de email identificadas como contendo malware multiplicado pelo número de destinatários |
|Bloqueado por [ATP](office-365-atp.md) |Número de mensagens de email bloqueadas por ATP multiplicado pelo número de destinatários |
|Removido após a entrega |Número de mensagens removidas por [limpeza automática de zero hora](zero-hour-auto-purge.md) multiplicado pelo número de destinatários |

## <a name="malware"></a>Malware

Os widgets de malware mostram detalhes sobre tendências de malware e tipos de família de malware nos últimos sete (7) dias.

![Tendências de malware e tipos de família](../media/malwarewidgetatpe5.png)
 
## <a name="insights"></a>Informações

Insights não apenas os principais problemas de superfície que você deve examinar, também incluem recomendações e ações a serem consideradas. 

![Ideias inteligentes](../media/smartinsights.png)

Por exemplo, você pode ver que as mensagens de email de phishing estão sendo entregues, pois alguns usuários desabilitaram suas opções de lixo eletrônico. Para saber mais sobre como as ideias funcionam, confira [relatórios e insights no centro de conformidade de &amp; segurança do Office 365](reports-and-insights-in-security-and-compliance.md).
  
## <a name="threat-investigation-and-response"></a>Investigação e resposta a ameaças

Se a assinatura de sua organização incluir o [plano de proteção avançada contra ameaças do Office 365](office-365-ti.md), o painel de segurança tem uma seção que inclui investigação avançada de ameaças e ferramentas de resposta. A equipe de segurança da sua organização pode usar as informações desta seção para entender campanhas emergentes, investigar ameaças e gerenciar incidentes. 
  
![A inteligência de ameaças ajuda você a entender ataques direcionados a sua organização](../media/threatintelwidget.png)
  
  
## <a name="trends"></a>Tendências

Próximo à parte inferior do painel de segurança está uma seção de **tendências** , que resume as tendências de fluxo de emails da sua organização. Os relatórios fornecem informações sobre emails categorizados como spam, malware, tentativas de phishing e bons emails. Clique em um bloco para exibir informações mais detalhadas no relatório. 
  
![A seção tendências resume as tendências de fluxo de emails da organização](../media/trends.png)
  
E, se a assinatura do Office 365 da sua organização incluir o [office 365 Advanced Threat Protection Plan 2](office-365-ti.md), você também terá um relatório **recente de alertas de gerenciamento de ameaças** nesta seção que permite que sua equipe de segurança exiba e execute ações sobre alertas de segurança de alta prioridade. 

Para exibir ou acessar o widget email enviado e recebido, você deve ter permissões para exibir relatórios de proteção avançada contra ameaças. Para saber mais, veja [quais permissões são necessárias para exibir os relatórios ATP?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports). 

Para exibir ou acessar o widget alertas de gerenciamento de ameaças recentes, você deve ter permissões para exibir alertas. Para saber mais, veja [permissões RBAC necessárias para exibir alertas](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts).
  
## <a name="related-topics"></a>Tópicos relacionados

[Exibir relatórios de segurança de email no &amp; centro de conformidade de segurança](../../compliance/view-email-security-reports.md)
  
[Exibir relatórios para a proteção avançada contra ameaças do Office 365](view-reports-for-atp.md)
  
[Proteção Avançada contra Ameaças do Office 365](office-365-atp.md)
  
[Investigação e resposta contra ameaças do Office 365](office-365-ti.md)
  

