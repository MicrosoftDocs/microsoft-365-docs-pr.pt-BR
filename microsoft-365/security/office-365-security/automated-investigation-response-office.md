---
title: Investigação e resposta automatizadas (AIR) no Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Obtenha uma visão geral dos recursos de investigação e resposta automatizados no Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 436d70934e32f8609d35532188ac71cbd590c345
ms.sourcegitcommit: 8876c216954b94adce9cdf493c49bd5a10190a3a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42228577"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a>Investigação e resposta automatizadas (AIR) no Office 365

Como os alertas de segurança são disparados, a equipe de operações de segurança pode examinar os alertas e realizar etapas para proteger sua organização. Às vezes, as equipes de operações de segurança podem se sentir sobrecarregadas pelo volume de alertas disparados. Os recursos de investigação e resposta automatizada (AIR) no Office 365 podem ajudar. O AIR permite que sua equipe de operações de segurança opere de forma mais eficiente e eficaz. Os recursos de ar incluem processos de investigação automatizados em resposta a ameaças bem conhecidas que existem atualmente. Ações de correção apropriadas aguardam aprovação, permitindo que sua equipe de operações de segurança responda a ameaças detectadas. 

Este artigo fornece uma visão geral do AIR e de seus componentes. Quando estiver pronto para começar a usar o AIR, confira [investigar automaticamente e responder a ameaças no Office 365](office-365-air.md).

> [!TIP]
> Você tem o Microsoft 365 E5 ou Microsoft 365 E3 juntamente com Proteção contra Identidade e Ameaças? Considere tentar [Proteção contra ameaças da Microsoft](../mtp/microsoft-threat-protection.md).

## <a name="at-a-high-level"></a>Em um nível alto

À medida que os alertas são disparados, os guias de segurança entram em vigor. Dependendo da situação, um processo de [investigação automatizado](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) pode começar. Durante e após uma investigação automatizada, [ações de correção](air-remediation-actions.md) são recomendadas. Nenhuma ação é executada automaticamente no Office 365 proteção avançada contra ameaças. Sua equipe de operações de segurança é revisada e, em seguida, [aprova ou rejeita cada ação de correção](air-remediation-actions.md#approve-or-reject-pending-actions)e, quando isso é feito, cada investigação é concluída. Todas essas atividades são rastreadas e visíveis no centro de conformidade & segurança do Office 365 (consulte [Exibir detalhes de uma investigação](air-view-investigation-results.md#view-details-of-an-investigation)).

As seções a seguir fornecem mais detalhes sobre alertas, guias de segurança e exemplos de ar em ação.

## <a name="alerts"></a>Alertas

Os [alertas](../../compliance/alert-policies.md#viewing-alerts) representam disparadores de fluxos de trabalho da equipe de operações de segurança para resposta a incidentes. Priorizar o conjunto certo de alertas para investigação e, ao mesmo tempo, garantir que nenhuma ameaça seja difícil. Quando as investigações nos alertas são realizadas manualmente, as equipes de operações de segurança devem procurar e correlacionar entidades (como conteúdo, dispositivos e usuários) em risco de ameaças. Essas tarefas e fluxos de trabalho podem ser muito demorados e envolver várias ferramentas e sistemas. Com o AIR, a investigação e a resposta dos eventos de segurança do Office 365 são automatizados por ter os principais alertas de segurança e gerenciamento de ameaças disparam guias de resposta de segurança automaticamente. 

Atualmente para o AIR, os alertas gerados a partir dos seguintes tipos de políticas de alerta são investigados automaticamente:  

- Um clique em URL potencialmente mal-intencionado foi detectado
- Email relatado pelo usuário como Phish *
- Mensagens de email contendo malware removidos após a entrega *
- Mensagens de email que contêm URLs de phishing removidos após a entrega *
- Padrões de envio de emails suspeitos detectados #
- Usuário impedido de enviar email #

> [!NOTE]
> Os alertas marcados com um asterisco (*) recebem uma severidade *informativa* nas respectivas políticas de alerta no centro de conformidade com segurança &, com notificações por email desativadas. As notificações por email podem ser ativadas por meio da [configuração da política de alerta](../../compliance/alert-policies.md#alert-policy-settings). Os alertas marcados com um hash (#) são geralmente alertas associados aos guias de visualização pública.

Para exibir alertas, no centro de conformidade & segurança, escolha **alertas** > **exibir alertas**. Selecione um alerta para exibir seus detalhes e, em seguida, use o link **Exibir investigação** para ir para a [investigação](air-view-investigation-results.md#investigation-graph)correspondente.  

> [!NOTE]
> Os alertas informativos ficam ocultos no modo de exibição de alerta por padrão. Para vê-los, altere a filtragem de alerta para incluir alertas informativos.

Se sua organização gerencia seus alertas de segurança por meio de um sistema de gerenciamento de alerta, sistema de gerenciamento de serviços ou informações de segurança e sistema de gerenciamento de eventos (SIEM), você pode enviar alertas do Office 365 para esse sistema por meio de uma notificação por email ou por meio da [API de atividade de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). As notificações de alerta de investigação via email ou API incluem links para acessar os alertas no centro de conformidade & segurança, permitindo que o administrador de segurança atribuído Navegue rapidamente para a investigação.

![Alertas que se vinculam a investigações](../../media/air-alerts-page-details.png) 

## <a name="security-playbooks"></a>Guias de segurança

Os guias de segurança são políticas de back-end que estão no coração de automação no Office Advanced Threat Protection e proteção contra ameaças da Microsoft. Os guias estratégicos de segurança fornecidos no AIR são baseados em cenários comuns de segurança do mundo real e desenvolvidos com base nos comentários das equipes de operações de segurança. Um guia de segurança é iniciado automaticamente quando alertas específicos são disparados em sua organização. Depois que o alerta é acionado, o manual associado é executado pelo sistema de investigação e resposta automatizada (AIR). As etapas de investigação por meio da análise do alerta com base no manual de alerta específico, em todos os metadados associados (incluindo mensagens de email, usuários, assuntos, remetentes, etc.). Com base nas conclusões do guia estratégico, o AIR recomenda um conjunto de ações que a equipe de segurança de sua organização pode executar para controlar e reduzir a ameaça. 

Os guias de segurança que você receberá com o AIR são projetados para lidar com as ameaças mais frequentes que as organizações encontram atualmente com o email. Eles são baseados na entrada de operações de segurança e em equipes de resposta a incidentes, incluindo aqueles que ajudam a defender o Microsoft e os ativos de nossos clientes.

### <a name="security-playbooks-are-rolling-out-in-phases"></a>Os guias de segurança estão distribuindo em fases

Como parte do AIR, os guias de segurança são implantados em fases. Agora, a fase 1 está disponível e inclui vários guias estratégicos que fornecem recomendações para ações que os administradores de segurança podem revisar e aprovar:
- Mensagem de phishing relatada pelo usuário
- URL clique em alterar veredicto
- Malware detectado após a entrega (malware ZAP)
- O phishing detectou o post-Delivery ZAP (Phish ZAP)

A fase 1 também inclui suporte para investigações de email disparadas pelo administrador (usando o [Explorador de ameaças](threat-explorer.md)).

A fase 2 agora está em andamento com os seguintes guias estratégicos na **Visualização pública**, fornecendo recomendações para ações e administradores de segurança do auxiliar em problemas de investigação:
- Usuário relatado como comprometido (visualização pública)

Os guias estratégicos serão lançados à medida que forem concluídos. Visite o [mapa do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) para ver o que mais está planejado e disponível em breve.

### <a name="playbooks-include-investigation-and-recommendations"></a>Os guias estratégicos incluem investigação e recomendações

No AIR, cada guia estratégico de segurança inclui: 
- uma investigação raiz de entidades de email (arquivos, URLs, destinatários, endereços IP, etc.)
- busca detalhada de emails semelhantes recebidos pela organização 
- etapas seguidas para identificar e correlacionar outras ameaças potenciais e 
- ações de correção de ameaças recomendadas.

Cada etapa de alto nível inclui várias subetapas executadas para fornecer uma resposta detalhada, detalhada e exaustiva às ameaças.

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Exemplo: uma mensagem de phishing relatada pelo usuário inicia um guia estratégico de investigação

Quando um usuário em sua organização envia uma mensagem de email e o relata à Microsoft usando o [suplemento de mensagem de relatório para o Outlook ou o Outlook Web App](enable-the-report-message-add-in.md), o relatório também é enviado para o seu sistema e fica visível no Explorer no modo de exibição relatado pelo usuário. Essa mensagem relatada pelo usuário agora dispara um alerta informativo baseado no sistema, que inicia automaticamente o guia estratégico de investigação.

Durante a fase de investigação de raiz, vários aspectos do email são avaliados. Entre eles:
- Uma determinação sobre o tipo de ameaça que ela pode ser;
- Quem o enviou;
- De onde o email foi enviado (infraestrutura de envio);
- Se outras instâncias do email foram entregues ou bloqueadas;
- Uma avaliação de nossos analistas;
- Se o email está associado a qualquer campanha conhecida;
- e muito mais.

Depois que a investigação raiz estiver concluída, o guia estratégico fornecerá uma lista de ações recomendadas a serem executadas no email original e entidades associadas a ela.
  
Em seguida, várias etapas de investigação e busca de ameaças são executadas:

- Mensagens de email semelhantes são identificadas por pesquisas de clusters de email.
- O sinal é compartilhado com outras plataformas, como [o Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).
- É possível determinar se qualquer usuário clicou por links mal-intencionados em mensagens de email suspeitas.
- Uma verificação é feita no Office 365 proteção do Exchange Online ([EOP](exchange-online-protection-eop.md)) e no Office 365 Advanced Threat Protection ([ATP](office-365-atp.md)) para ver se há outras mensagens semelhantes relatadas pelos usuários.
- Uma verificação é feita para ver se um usuário foi comprometido. Esta verificação utiliza sinais no Office 365, no [Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security)e no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlacionando qualquer anomalia relacionada à atividade do usuário. 

Durante a fase de caça, riscos e ameaças são atribuídos a várias etapas de busca. 

Correção é a fase final do guia estratégico. Durante esta fase, as etapas de correção são tomadas, com base nas fases de investigação e busca. 

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Exemplo: um administrador de segurança dispara uma investigação do explorador de ameaças

Além de investigações automáticas disparadas por um alerta, a equipe de operações de segurança da sua organização pode acionar uma investigação automática de um modo de exibição no [Explorador de ameaças](threat-explorer.md).

Por exemplo, suponha que você está exibindo dados no Explorer sobre mensagens relatadas pelo usuário. Você pode selecionar um item na lista de resultados e, em seguida, clicar em **investigar** no menu Ação (supondo que você tenha permissões de correção apropriadas).

![Mensagens relatadas pelo usuário no Explorer com o botão investigar](../../media/Explorer-UserReported-Investigate.png)

Como outro exemplo, suponha que você esteja exibindo dados sobre mensagens de email detectadas como contendo malware e que há várias mensagens de email detectadas como contendo malware. Você pode selecionar a guia **email** , selecionar uma ou mais mensagens de email e, em seguida, no menu **ações** , selecionar **investigar**. 

![Iniciando uma investigação de malware no Explorer](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Semelhante aos guias estratégicos acionados por um alerta, as investigações automáticas disparadas de um modo de exibição no Explorer incluem uma investigação raiz, etapas para identificar e correlacionar ameaças e ações recomendadas para atenuar essas ameaças.

## <a name="next-steps"></a>Próximas etapas

- [Introdução ao uso do AIR no Office 365](office-365-air.md)

- [Visite o mapa do Microsoft 365 para ver o que está chegando em breve e distribuir](https://www.microsoft.com/microsoft-365/roadmap?filters=)

