---
title: Recomendações de segurança para contas prioritárias no Microsoft 365
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
- m365solution-overview
- m365solution-protecthve
description: Os administradores podem aprender a elevar as configurações de segurança e usar relatórios, alertas e investigações para contas prioritárias em suas organizações do Microsoft 365.
ms.openlocfilehash: 8a1d92ef12070a722a1b618bf51ab6d8130f49c0
ms.sourcegitcommit: 31be333178b934c519f419656f4c3a53e1beffdc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "49881790"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Recomendações de segurança para contas prioritárias no Microsoft 365

Nem todas as contas de usuário têm acesso às mesmas informações da empresa. Algumas contas têm acesso a informações confidenciais, como dados financeiros, informações de desenvolvimento de produtos, acesso de parceiros a sistemas de com build críticos e muito mais. Se comprometidas, as contas que têm acesso a informações altamente confidenciais representam uma ameaça grave. Chamamos esses tipos de contas de _prioridade de contas._ As contas de prioridade incluem (mas não estão limitadas a) CEOs, CISOs, CFOs, contas de administrador de infraestrutura, criar contas do sistema e muito mais.

Para invasores, ataques comuns de phishing que lançam uma rede aleatória para usuários comuns ou desconhecidos são ineficientes. Por outro lado, _os ataques de phishing_ ou _whaling_ que visam contas prioritárias são muito recompiletivas para invasores. Portanto, as contas de prioridade exigem proteção mais forte do que a comum para ajudar a evitar o comprometimento da conta.

O Microsoft 365 e o Microsoft Defender para Office 365 contêm vários recursos importantes que fornecem camadas adicionais de segurança para suas contas prioritárias. Este artigo descreve esses recursos e como usá-los.

![Resumo das recomendações de segurança no formato de ícone](../../media/security-recommendations-for-priority-users.png)

****

|Tarefa|Todos os planos do Office 365 Enterprise|Microsoft 365 E3|Microsoft 365 E5|
|---|:---:|:---:|:---:|
|[Aumentar a segurança de login para contas prioritárias](#increase-sign-in-security-for-priority-accounts)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Usar políticas de segurança predefinidas Estritas para contas prioritárias](#use-strict-preset-security-policies-for-priority-accounts)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Aplicar marcas de usuário a contas prioritárias](#apply-user-tags-to-priority-accounts)|||![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Monitorar contas de prioridade em alertas, relatórios e detecções](#monitor-priority-accounts-in-alerts-reports-and-detections)|||![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Treinar usuários](#train-users)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Incluído](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|

## <a name="increase-sign-in-security-for-priority-accounts"></a>Aumentar a segurança de login para contas prioritárias

As contas de prioridade exigem maior segurança de login. Você pode aumentar a segurança de login deles exigindo a autenticação multifatofa (MFA) e desabilitando protocolos de autenticação herdados.

Para obter instruções, consulte [a Etapa 1. Aumente a segurança de login para funcionários remotos com MFA.](https://docs.microsoft.com/microsoft-365/solutions/empower-people-to-work-remotely-secure-sign-in) Embora este artigo seja sobre funcionários remotos, os mesmos conceitos se aplicam aos usuários prioritários.

**Observação:** recomendamos que você desabilite globalmente os protocolos de autenticação herdados para todos os usuários com prioridade, conforme descrito no artigo anterior. Se seus requisitos de negócios impedirem isso, o Exchange Online oferecerá os seguintes controles para ajudar a limitar o escopo de protocolos de autenticação herdados:

- Você pode [](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) usar [](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) políticas de autenticação e Regras de Acesso para Cliente no Exchange Online para bloquear ou permitir protocolos de autenticação básica e herdados, como POP3, IMAP4 e SMTP autenticado para usuários específicos.

- Você pode desabilitar o acesso POP3 e IMAP4 em caixas de correio individuais. Você pode desabilitar o SMTP autenticado no nível organizacional e habilita-lo em caixas de correio específicas que ainda exigem isso. Para obter instruções, consulte os seguintes tópicos:
  - [Habilitar ou desabilitar o acesso POP3 ou IMAP4 para um usuário](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [Habilitar ou desabilitar o envio SMTP do cliente autenticado (SMTP AUTH)](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

Também vale a pena notar que a autenticação Básica está sendo preterida no Exchange Online para Serviços Web do Exchange (EWS), Exchange ActiveSync, POP3, IMAP4 e PowerShell remoto. Para obter detalhes, confira esta [postagem de blog.](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/)

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>Usar políticas de segurança predefinidas Estritas para contas prioritárias

Os usuários prioritários exigem ações mais rigorosas para as várias proteções disponíveis no Exchange Online Protection (EOP) e no Defender para Office 365.

Por exemplo, em vez de entregar mensagens que foram classificadas como spam para a pasta Lixo Eletrônico, você deve colocar essas mesmas mensagens em quarentena se elas se destinam a contas prioritárias.

Você pode implementar essa abordagem rigorosa para contas prioritárias usando o perfil Estrito em políticas de segurança predefinidas.

As políticas de segurança predefinidas são um local conveniente e central para aplicar nossas configurações de política Estrita recomendadas para todas as proteções no EOP e no Defender para Office 365. Para obter mais informações, consulte [Políticas de segurança predefinidas no EOP e no Microsoft Defender para Office 365.](preset-security-policies.md)

Para obter detalhes sobre como as configurações de política Estrito diferem das configurações de política padrão e padrão, consulte Configurações recomendadas para o EOP e [o Microsoft Defender para segurança do Office 365.](recommended-settings-for-eop-and-office365-atp.md)

## <a name="apply-user-tags-to-priority-accounts"></a>Aplicar marcas de usuário a contas prioritárias

As marcas de usuário no Microsoft Defender para Office 365 Plano 2 (como parte do Microsoft 365 E5 ou uma assinatura de complemento) são uma maneira de identificar e classificar rapidamente usuários ou grupos de usuários específicos em relatórios e investigações de incidentes.

**Contas de** prioridade é um tipo de marca de usuário interna (conhecida como marca do _sistema)_ que você pode usar para identificar incidentes e alertas que envolvem contas de prioridade. Para obter mais informações sobre **contas de prioridade,** [consulte Gerenciar e monitorar contas de prioridade.](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts)

Você também pode criar marcas personalizadas para identificar e classificar ainda mais suas contas de prioridade. Para obter mais informações, consulte [Marcas de usuário.](user-tags.md) Observe que você pode gerenciar **contas de prioridade** (marcas do sistema) na mesma interface que as marcas de usuário personalizadas.

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>Monitorar contas de prioridade em alertas, relatórios e detecções

Depois de proteger e marcar os usuários com prioridade, você pode usar os relatórios, alertas e investigações disponíveis no EOP e no Defender para Office 365 para identificar rapidamente incidentes ou detecções que envolvem contas de prioridade. Os recursos que suportam marcas de usuário são descritos na tabela a seguir.

<br>

****

|Recurso|Descrição|
|---|---|
|Alertas|As marcas de usuário dos usuários afetados estão visíveis e disponíveis como filtros na página Exibir **alertas** no Centro de Conformidade & Segurança. Para obter mais informações, consulte [Exibindo alertas.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#viewing-alerts)|
|Explorador de Ameaças <p> Detecções em tempo real|No **Explorador** de Ameaças (Microsoft Defender para Office 365 Plano 2) ou detecções em tempo **real** (Microsoft Defender para Office 365 Plano 1), as marcas de usuário ficam visíveis na exibição de grade Email e no submenu Detalhes do email. As marcas de usuário também estão disponíveis como uma propriedade filtável. Para obter mais informações, consulte [Marcas no Explorador de Ameaças.](threat-explorer.md#tags-in-threat-explorer)|
|Modos de Exibição de Campanha|As marcas de usuário são uma das muitas propriedades filtáveis em Exibições de Campanha no Microsoft Defender para Office 365 Plano 2. Para obter mais informações, consulte [Exibições de Campanha.](campaigns.md)|
|Relatório de status de proteção contra ameaças|Em praticamente todas as exibições e tabelas de detalhes no relatório de **status** de Proteção contra Ameaças, você pode filtrar os resultados por contas **de prioridade.** Para obter mais informações, consulte [o relatório de status de proteção contra ameaças.](view-email-security-reports.md#threat-protection-status-report)|
|Email issues for priority accounts report|Os **problemas de email para** o relatório de contas de prioridade no Centro de administração do Exchange (EAC) contém informações sobre mensagens não entregues e atrasadas para contas de **prioridade.** Para obter mais informações, consulte [Email issues for priority accounts report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).|
|

## <a name="train-users"></a>Treinar usuários

O treinamento de usuários com contas prioritárias pode ajudar a salvar esses usuários e sua equipe de operações de segurança por muito tempo e frustração. Os usuários experientes têm menos probabilidade de abrir anexos ou clicar em links em mensagens de email questionáveis, e é mais provável que eles evitem sites suspeitos.

O Manual da Campanha de [Segurança Cibernética](https://www.belfercenter.org/CyberPlaybook) da Escola Demão fornece excelentes diretrizes para estabelecer uma forte cultura de reconhecimento de segurança em sua organização, incluindo treinamento para os usuários identificarem ataques de phishing.

O Microsoft 365 fornece os seguintes recursos para ajudar a informar os usuários em sua organização:

<br>

****

|Conceito|Recursos|Descrição|
|---|---|---|
|Microsoft 365|[Caminhos de aprendizagem personalizáveis](https://docs.microsoft.com/office365/customlearning/)|Esses recursos podem ajudá-lo a reunir treinamentos para usuários em sua organização.|
|Segurança do Microsoft 365|[Módulo de aprendizagem: proteja sua organização com segurança interna e inteligente do Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365)|Este módulo permite descrever como os recursos de segurança do Microsoft 365 funcionam juntos e articular os benefícios desses recursos de segurança.|
|Autenticação multifator|[Verificação em duas etapas: Qual é a página de verificação adicional?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time)|Este artigo ajuda os usuários finais a entender o que é a autenticação multifatare e por que ela está sendo usada em sua organização.|
|Treinamento de simulação de ataque|[Começar a usar o treinamento de simulação de ataque](attack-simulation-training-get-started.md)|O treinamento de simulação de ataque no Microsoft Defender para Office 365 Plano 2 permite que o administrador configure, iniciar e rastrear ataques simulados de phishing contra grupos específicos de usuários.|

Além disso, a Microsoft recomenda que os usuários tomem as ações descritas neste artigo: proteger sua conta e dispositivos [contra hackers e malware.](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6) Essas ações incluem:

- Usando senhas fortes
- Protegendo dispositivos
- Habilitando recursos de segurança em computadores Com Windows 10 e Mac (para dispositivos não-operacionais)

## <a name="see-also"></a>Confira também

[Anunciando a Proteção de Conta Com Prioridade no Microsoft Defender para Office 365](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
