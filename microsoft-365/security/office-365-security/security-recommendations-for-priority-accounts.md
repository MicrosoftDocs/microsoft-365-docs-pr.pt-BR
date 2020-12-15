---
title: Recomendações de segurança para contas de prioridade no Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a elevar as configurações de segurança e a usar relatórios, alertas e investigações para contas de prioridade em suas organizações do Microsoft 365.
ms.openlocfilehash: aee238d2fb58d2772881d8d77f98959906943290
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668083"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Recomendações de segurança para contas de prioridade no Microsoft 365

O que você faria se recebeu uma mensagem urgente de um executivo em sua organização que solicitou algo? Você faria isso? A maioria das pessoas estaria em conformidade com a solicitação.

Para invasores, os ataques comuns de phishing que convertem uma rede aleatória para obter as credenciais de usuários aleatórios ou desconhecidos são ineficientes. Por outro lado, os ataques de _spear phishing_ ou _Whaling_ que direcionam os usuários em posições de poder ou de autoridade são muito mais recompensados para invasores. Se essas contas de prioridade estiverem comprometidas, o invasor poderá obter acesso a contas com recursos de administrador, financeiro, produto ou mesmo acesso físico dentro da organização.

O Microsoft 365 e o Microsoft defender para Office 365 contêm vários recursos diferentes que podem ajudá-lo a fornecer camadas adicionais de segurança para suas contas de prioridade. Os recursos disponíveis e como usá-los são discutidos neste artigo.

## <a name="increase-sign-in-security-for-priority-accounts"></a>Aumentar a segurança de entrada para contas de prioridade

As contas de prioridade exigem maior segurança de entrada. Você pode aumentar a segurança de entrada exigindo a autenticação multifator (MFA) e desabilitando os protocolos de autenticação herdados.

Para obter instruções, consulte a [etapa 1. Aumentar a segurança de entrada para funcionários remotos com a MFA](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in). Embora este artigo seja sobre funcionários remotos, os mesmos conceitos se aplicam a usuários de prioridade.

**Observações**:

- A autenticação básica está no processo de ser preterido no Exchange Online para serviços Web do Exchange (EWS), Exchange ActiveSync, POP3, IMAP4 e PowerShell remoto. Para obter detalhes, consulte esta [postagem de blog](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/).

- Você pode usar [políticas de autenticação](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) e [regras de acesso para cliente](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) no Exchange Online para bloquear autenticação básica e protocolos de autenticação herdados como POP3, IMAP4 e SMTP autenticado.

- Você pode desabilitar o acesso POP3 e IMAP4 em caixas de correio individuais. Você pode desabilitar o SMTP autenticado no nível organizacional e habilitá-lo em caixas de correio específicas que ainda exijam isso. Para obter instruções, consulte os seguintes tópicos:
  - [Habilitar ou desabilitar o acesso POP3 ou IMAP4 para um usuário](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [Habilitar ou desabilitar o envio SMTP de cliente autenticado (autenticação SMTP)](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>Usar políticas de segurança predefinidas restritas para contas de prioridade

Os usuários com prioridade exigem ações mais rigorosas para as várias proteções disponíveis no Exchange Online Protection (EOP) e no defender para Office 365.

Por exemplo, em vez de entregar mensagens que foram classificadas como spam para a pasta lixo eletrônico, você deve colocar essas mesmas mensagens em quarentena se elas forem destinadas às contas de prioridade.

Você pode implementar essa abordagem rigorosa para contas de prioridade usando o perfil estrito em políticas de segurança predefinidas.

As políticas de segurança predefinidas são um local conveniente e central para aplicar as configurações de política estrita recomendadas para todas as proteções do EOP e do defender para Office 365. Para obter mais informações, consulte [predefinições de políticas de segurança no EOP e Microsoft defender para Office 365](preset-security-policies.md).

Para obter detalhes sobre como as configurações de diretiva estritas diferem das configurações de política padrão e padrão, consulte [configurações recomendadas para o EOP e o Microsoft defender para Office 365 Security](recommended-settings-for-eop-and-office365-atp.md).

## <a name="user-tags"></a>Marcas de usuário

As marcas de usuário no Microsoft defender para Office 365 plano 2 (como parte do Microsoft 365 E5 ou uma assinatura complementar) são uma maneira de identificar e classificar rapidamente usuários ou grupos específicos de usuários em relatórios e investigações de incidentes.

**As contas de prioridade** é um tipo de marca de usuário interna (conhecido como uma _marca do sistema_) que você pode usar para identificar incidentes e alertas que envolvem contas de prioridade. Para obter mais informações sobre **contas de prioridade**, consulte [gerenciar e monitorar contas de prioridade](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).

Você também pode criar marcas personalizadas para identificar e classificar suas contas de prioridade. Para obter mais informações, consulte [User Tags](user-tags.md). Observe que você pode gerenciar **contas de prioridade** (marcas de sistema) na mesma interface que as marcas de usuário personalizadas.

## <a name="priority-accounts-in-reports-and-investigations-in-microsoft-365"></a>Contas de prioridade em relatórios e investigações no Microsoft 365

****

|Recurso|Descrição|
|---|---|
|Alertas|As marcas de usuário dos usuários afetados estão visíveis e disponíveis como filtros na página **exibir alertas** no centro de conformidade de & de segurança. Para obter mais informações, consulte [Viewing Alerts](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts).|
|Explorador de Ameaças <p> Detecções em tempo real|No **Explorador de ameaças** (Microsoft defender para Office 365 plano 2) ou **detecções em tempo real** (microsoft defender para Office 365 plano 1), as marcas de usuário são visíveis no modo de exibição grade de email e no submenu detalhes do email. Marcas de usuário também estão disponíveis como uma propriedade filtrável. Para obter mais informações, consulte  [marcas no Gerenciador de ameaças](threat-explorer.md#tags-in-threat-explorer).|
|Modos de Exibição de Campanha|As marcas de usuário são uma das muitas propriedades filtráveis nos modos de exibição de campanha no Microsoft defender para Office 365 plano 2. Para obter mais informações, consulte [Campaign views](campaigns.md).|
|Relatório de status de proteção contra ameaças|Em praticamente todas as tabelas de modos de exibição e detalhes no **relatório de status de proteção contra ameaças**, você pode filtrar os resultados por **contas de prioridade**. Para obter mais informações, consulte [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report).|
|Relatório de problemas de email para contas de prioridade|O relatório de **problemas de email para contas de prioridade** no centro de administração do Exchange (Eat) contém informações sobre mensagens não entregues e atrasadas para **contas de prioridade**. Para obter mais informações, consulte [e-mail issues for Priority accounts Report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).|
|

## <a name="see-also"></a>Também consulte

[Anunciando a proteção da conta de prioridade no Microsoft defender para Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
