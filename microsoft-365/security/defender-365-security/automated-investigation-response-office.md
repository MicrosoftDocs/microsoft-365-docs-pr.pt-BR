---
title: Como funciona a investigação e a resposta automatizadas no Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
keywords: resposta a incidentes automatizados, investigação, correção, proteção contra ameaças
ms.date: 01/29/2021
description: Veja como funcionam os recursos automatizados de investigação e resposta no Microsoft Defender para Office 365
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e377927156e8c98d07f4527bca09e3764bed3f74
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053710"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Como funciona a investigação e a resposta automatizadas no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

À medida que os alertas de segurança são disparados, a equipe de operações de segurança deve procurar esses alertas e tomar medidas para proteger sua organização. Às vezes, as equipes de operações de segurança podem se sentir sobrecarregadas pelo volume de alertas disparados. Recursos automatizados de investigação e resposta (AIR) no Microsoft Defender para Office 365 podem ajudar.

O AIR permite que sua equipe de operações de segurança opere de forma mais eficiente e eficaz. Os recursos air incluem processos de investigação automatizados em resposta a ameaças conhecidas que existem atualmente. As ações de correção apropriadas aguardam aprovação, permitindo que sua equipe de operações de segurança responda a ameaças detectadas.

Este artigo descreve como o AIR funciona por meio de vários exemplos. Quando você estiver pronto para começar a usar o AIR, consulte [Investigar automaticamente e responder a ameaças](office-365-air.md).

- [Exemplo 1: uma mensagem de phishing relatada pelo usuário inicia um manual de investigação](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [Exemplo 2: um administrador de segurança dispara uma investigação do Explorador de Ameaças](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [Exemplo 3: uma equipe de operações de segurança integra o AIR com seu SIEM usando a API de Atividade de Gerenciamento do Office 365](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Exemplo: uma mensagem de phishing relatada pelo usuário inicia um manual de investigação

Suponha que um usuário em sua organização receba um email que ele acha que é uma tentativa de phishing. O usuário, treinado para relatar essas mensagens, usa o complemento Mensagem de [Relatório](enable-the-report-message-add-in.md) ou o complemento De relatório phishing para [enviá-lo](enable-the-report-phish-add-in.md) à Microsoft para análise. O envio também é enviado para seu sistema e fica visível no Explorer no exibição **Envios** (anteriormente chamado de exibição relatado **pelo** usuário). Além disso, a mensagem relatada pelo usuário agora dispara um alerta informacional baseado no sistema, que inicia automaticamente o playbook de investigação.

Durante a fase de investigação raiz, vários aspectos do email são avaliados. Esses aspectos incluem:

- Uma determinação sobre o tipo de ameaça que pode ser;
- Quem o enviou;
- De onde o email foi enviado (enviando infraestrutura);
- Se outras instâncias do email foram entregues ou bloqueadas;
- Uma avaliação de nossos analistas;
- Se o email está associado a campanhas conhecidas;
- e muito mais.

Depois que a investigação raiz for concluída, a playbook fornece uma lista de ações recomendadas a ser realizadas no email original e nas entidades associadas a ele.

Em seguida, várias etapas de investigação e busca de ameaças são executadas:

- Mensagens de email semelhantes são identificadas por meio de pesquisas de cluster de email.
- O sinal é compartilhado com outras plataformas, como [o Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).
- Uma determinação é feita sobre se os usuários clicaram em links mal-intencionados em mensagens de email suspeitas.
- Uma verificação é feita no Exchange Online Protection ([EOP](exchange-online-protection-overview.md)) e ([Microsoft Defender para Office 365](defender-for-office-365.md)) para ver se há outras mensagens semelhantes relatadas pelos usuários.
- Uma verificação é feita para ver se um usuário foi comprometido. Essa verificação aproveita sinais no Office 365, [no Microsoft Cloud App Security](/cloud-app-security)e no [Azure Active Directory,](/azure/active-directory)correlacionando quaisquer anomalias relacionadas à atividade do usuário.

Durante a fase de busca, riscos e ameaças são atribuídos a várias etapas de busca.

A correção é a fase final do playbook. Durante essa fase, as etapas de correção são tomadas, com base nas fases de investigação e busca.

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Exemplo: um administrador de segurança dispara uma investigação do Explorador de Ameaças

Além das investigações automatizadas disparadas por um alerta, a equipe de operações de segurança da sua organização pode disparar uma investigação automatizada de um ponto de vista no [Explorador de Ameaças.](threat-explorer.md)  Essa investigação também cria um alerta para que os Incidentes do Microsoft Defender e as ferramentas siem externas possam ver que essa investigação foi disparada.

Por exemplo, suponha que você está usando o **exibição Malware** no Explorer. Usando as guias abaixo do gráfico, selecione a **guia Email.** Se você selecionar um ou mais itens na lista, o **botão + Ações** será ativado.

![Explorer com mensagens selecionadas](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Usando o menu **Ações,** você pode selecionar **Disparar investigação**.

![Menu Ações para mensagens selecionadas](../../media/explorer-malwareview-selectedemails-actions.jpg)

Semelhante às playbooks disparadas por um alerta, as investigações automáticas disparadas de um modo de exibição no Explorer incluem uma investigação raiz, etapas para identificar e correlacionar ameaças e ações recomendadas para mitigar essas ameaças.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>Exemplo: uma equipe de operações de segurança integra o AIR com o SIEM usando a API de Atividade de Gerenciamento do Office 365

Os recursos air no Microsoft Defender para Office 365 incluem relatórios & [detalhes](air-view-investigation-results.md) que as equipes de operações de segurança podem usar para monitorar e lidar com ameaças. Mas você também pode integrar recursos AIR com outras soluções. Exemplos incluem um sistema de gerenciamento de informações de segurança e eventos (SIEM), um sistema de gerenciamento de caso ou uma solução de relatório personalizada. Esses tipos de integrações podem ser feitas usando a API de Atividade de Gerenciamento do [Office 365.](/office/office-365-management-api/office-365-management-activity-api-reference)

Por exemplo, recentemente, uma organização definiu uma maneira de sua equipe de operações de segurança exibir alertas de phishing relatados pelo usuário que já foram processados pelo AIR. Sua solução integra alertas relevantes com o servidor SIEM da organização e seu sistema de gerenciamento de caso. A solução reduz consideravelmente o número de falsos positivos para que sua equipe de operações de segurança possa concentrar seu tempo e esforço em ameaças reais. Para saber mais sobre essa solução personalizada, consulte Blog da Comunidade Técnica: Melhorar a eficácia do SOC com o Microsoft Defender para Office 365 e a API de Gerenciamento [do O365.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)

## <a name="next-steps"></a>Próximas etapas

- [Começar a usar o AIR](office-365-air.md)
- [Exibir ações de correção pendentes ou concluídas](air-review-approve-pending-completed-actions.md)