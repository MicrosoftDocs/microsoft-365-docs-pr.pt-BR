---
title: Como a investigação e a resposta automatizadas funcionam no Microsoft defender para Office 365
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
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: resposta de incidentes automatizado, investigação, correção, proteção contra ameaças
ms.date: 11/05/2020
description: Veja como os recursos de investigação e resposta automatizados funcionam no Microsoft defender para Office 365
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: bbc51201f9d96744ed5bc236516158a75f7af272
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615223"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Como a investigação e a resposta automatizadas funcionam no Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Como os alertas de segurança são disparados, a equipe de operações de segurança pode examinar os alertas e realizar etapas para proteger sua organização. Às vezes, as equipes de operações de segurança podem se sentir sobrecarregadas pelo volume de alertas disparados. Os recursos de investigação e resposta automatizada (AIR) no Microsoft defender para Office 365 podem ajudar.

O AIR permite que sua equipe de operações de segurança opere de forma mais eficiente e eficaz. Os recursos de ar incluem processos de investigação automatizados em resposta a ameaças já conhecidas que existem atualmente. Ações de correção apropriadas aguardam aprovação, permitindo que sua equipe de operações de segurança responda a ameaças detectadas.

Este artigo descreve como o AIR funciona através de vários exemplos. Quando estiver pronto para começar a usar o AIR, confira [investigar automaticamente e responder a ameaças](office-365-air.md).

- [Exemplo 1: uma mensagem de phishing relatada pelo usuário inicia um guia estratégico de investigação](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [Exemplo 2: um administrador de segurança dispara uma investigação do explorador de ameaças](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [Exemplo 3: uma equipe de operações de segurança integra o ar com seu SIEM usando a API de atividade de gerenciamento do Office 365](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Exemplo: uma mensagem de phishing relatada pelo usuário inicia um guia estratégico de investigação

Suponha que um usuário em sua organização receba um email que eles pensam ser uma tentativa de phishing. O usuário, treinado para relatar essas mensagens, usa o [suplemento de mensagem de relatório](enable-the-report-message-add-in.md) para enviá-la à Microsoft para análise. O envio também é enviado ao seu sistema e fica visível no Explorer, no modo de exibição de **envios** (conhecido anteriormente como modo de exibição **relatado pelo usuário** ). Além disso, a mensagem relatada pelo usuário agora dispara um alerta informativo baseado no sistema, que inicia automaticamente o manual de investigação.

Durante a fase de investigação de raiz, vários aspectos do email são avaliados. Esses aspectos incluem:

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
- O sinal é compartilhado com outras plataformas, como [o Microsoft defender para ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).
- É possível determinar se qualquer usuário clicou por links mal-intencionados em mensagens de email suspeitas.
- Uma verificação é feita na proteção do Exchange Online ([EOP](exchange-online-protection-overview.md)) e ([Microsoft Defender para Office 365](office-365-atp.md)) para ver se há outras mensagens semelhantes relatadas pelos usuários.
- Uma verificação é feita para ver se um usuário foi comprometido. Esta verificação utiliza sinais no Office 365, no [Microsoft Cloud app Security](https://docs.microsoft.com/cloud-app-security)e no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory), correlacionando qualquer anomalia relacionada à atividade do usuário.

Durante a fase de caça, riscos e ameaças são atribuídos a várias etapas de busca.

Correção é a fase final do guia estratégico. Durante esta fase, as etapas de correção são tomadas, com base nas fases de investigação e busca.

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Exemplo: um administrador de segurança dispara uma investigação do explorador de ameaças

Além de investigações automatizadas disparadas por um alerta, a equipe de operações de segurança da sua organização pode acionar uma investigação automatizada a partir de um modo de exibição no [Explorador de ameaças](threat-explorer.md).  Essa investigação também cria um alerta, de modo que os incidentes do Microsoft defender e as ferramentas externas do SIEM podem ver que essa investigação foi acionada.

Por exemplo, suponha que você esteja usando o modo de exibição de **malware** no Explorer. Usando as guias abaixo do gráfico, você seleciona a guia **email** . Se você selecionar um ou mais itens na lista, o botão **+ Actions** será ativado.

![Explorer com mensagens selecionadas](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Usando o menu **ações** , você pode selecionar **disparador de investigação**.

![Menu de ações para mensagens selecionadas](../../media/explorer-malwareview-selectedemails-actions.jpg)

Semelhante aos guias estratégicos acionados por um alerta, as investigações automáticas disparadas de um modo de exibição no Explorer incluem uma investigação raiz, etapas para identificar e correlacionar ameaças e ações recomendadas para atenuar essas ameaças.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>Exemplo: uma equipe de operações de segurança integra o ar com seu SIEM usando a API de atividade de gerenciamento do Office 365

Recursos de ar no Microsoft defender para Office 365 incluem [relatórios & detalhes](air-view-investigation-results.md) que as equipes de operações de segurança podem usar para monitorar e lidar com ameaças. Mas você também pode integrar recursos de ar com outras soluções. Os exemplos incluem um sistema de gerenciamento de eventos e informações de segurança (SIEM), um sistema de gerenciamento de casos ou uma solução de relatórios personalizada. Esses tipos de integrações podem ser feitos usando a [API de atividade de gerenciamento do Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).

Por exemplo, recentemente, uma organização configurou uma maneira de sua equipe de operações de segurança exibir alertas de phishing relatados pelo usuário que já foram processados pelo AIR. Sua solução integra alertas relevantes com o servidor SIEM da organização e seu sistema de gerenciamento de casos. A solução reduz muito o número de falsos positivos para que a equipe de operações de segurança possa concentrar seu tempo e esforço em ameaças reais. Para saber mais sobre essa solução personalizada, consulte [blog da comunidade técnica: aprimore a eficácia do seu SoC com o Microsoft defender para Office 365 e a API de gerenciamento do O365](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

## <a name="next-steps"></a>Próximas etapas

- [Introdução ao uso do AIR](office-365-air.md)

- [Visite o mapa do Microsoft 365 para ver o que está planejado e liberando em breve](https://www.microsoft.com/microsoft-365/roadmap?filters=)

- [Saiba mais sobre os recursos de investigação e resposta automatizados no Microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
