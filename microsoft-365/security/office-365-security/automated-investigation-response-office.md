---
title: Como funciona a investigação e resposta automatizadas no Microsoft Defender para Office 365
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
keywords: resposta automatizada a incidentes, investigação, correção, proteção contra ameaças
ms.date: 01/29/2021
description: Veja como funcionam os recursos automatizados de investigação e resposta no Microsoft Defender para Office 365
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a5a1384208141a42459c009952f89d18498cc21e
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287920"
---
# <a name="how-automated-investigation-and-response-works-in-microsoft-defender-for-office-365"></a>Como funciona a investigação e resposta automatizadas no Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

À medida que os alertas de segurança são disparados, fica a sua equipe de operações de segurança procurar esses alertas e tomar medidas para proteger sua organização. Às vezes, as equipes de operações de segurança podem se sentir sobrecarregadas pelo volume de alertas disparados. Recursos automatizados de investigação e resposta (AIR) no Microsoft Defender para Office 365 podem ajudar.

O AIR permite que sua equipe de operações de segurança opere de forma mais eficiente e eficaz. Os recursos air incluem processos de investigação automatizada em resposta a ameaças conhecidas que existem atualmente. As ações de correção apropriadas aguardam aprovação, permitindo que sua equipe de operações de segurança responda a ameaças detectadas.

Este artigo descreve como o AIR funciona por meio de vários exemplos. Quando você estiver pronto para começar a usar o AIR, consulte [Investigar e responder a ameaças automaticamente.](office-365-air.md)

- [Exemplo 1: Uma mensagem de phishing relatada pelo usuário inicia um manual de investigação](#example-a-user-reported-phish-message-launches-an-investigation-playbook)
- [Exemplo 2: Um administrador de segurança dispara uma investigação do Explorador de Ameaças](#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)
- [Exemplo 3: Uma equipe de operações de segurança integra o AIR ao SIEM usando a API da Atividade de Gerenciamento do Office 365](#example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api)

## <a name="example-a-user-reported-phish-message-launches-an-investigation-playbook"></a>Exemplo: uma mensagem de phishing relatada pelo usuário inicia um manual de investigação

Suponha que um usuário em sua organização receba um email que ele acha que é uma tentativa de phishing. O usuário, treinado para relatar essas mensagens, usa o complemento Mensagem de Relatório ou o complemento [De Phishing](enable-the-report-phish-add-in.md) de Relatório para [enviá-lo](enable-the-report-message-add-in.md) à Microsoft para análise. O envio também é enviado para o sistema e fica visível no Explorer na exibição **Envios** (anteriormente conhecido como exibição relatada **pelo** usuário). Além disso, a mensagem relatada pelo usuário agora dispara um alerta informativo baseado no sistema, que inicia automaticamente o manual de investigação.

Durante a fase de investigação raiz, vários aspectos do email são avaliados. Esses aspectos incluem:

- Uma determinação sobre qual tipo de ameaça ela pode ser;
- Quem a enviou;
- De onde o email foi enviado (infraestrutura de envio);
- Se outras instâncias do email foram entregues ou bloqueadas;
- Uma avaliação de nossos analistas;
- Se o email está associado a campanhas conhecidas;
- e muito mais.

Após a conclusão da investigação raiz, o manual fornece uma lista de ações recomendadas a ser tomada no email original e nas entidades associadas a ela.

Em seguida, várias etapas de investigação e busca de ameaças são executadas:

- Mensagens de email semelhantes são identificadas por meio de pesquisas de cluster de email.
- O sinal é compartilhado com outras plataformas, como [o Microsoft Defender para Ponto de Extremidade.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- Uma determinação é feita sobre se algum usuário clicou em links mal-intencionados em mensagens de email suspeitas.
- Uma verificação é feita no Exchange Online Protection[(EOP)](exchange-online-protection-overview.md)e ([Microsoft Defender para Office 365](office-365-atp.md)) para ver se há outras mensagens semelhantes relatadas pelos usuários.
- Uma verificação é feita para ver se um usuário foi comprometido. Essa verificação utiliza sinais no Office 365, no [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)e no [Azure Active Directory,](https://docs.microsoft.com/azure/active-directory)correlacionando quaisquer anomalias relacionadas à atividade do usuário.

Durante a fase de busca, os riscos e as ameaças são atribuídos a várias etapas de busca.

A correção é a fase final do playbook. Durante essa fase, as etapas de correção são realizadas, com base nas fases de investigação e busca.

## <a name="example-a-security-administrator-triggers-an-investigation-from-threat-explorer"></a>Exemplo: um administrador de segurança dispara uma investigação do Explorador de Ameaças

Além de investigações automatizadas que são acionadas por um alerta, a equipe de operações de segurança da sua organização pode disparar uma investigação automatizada de uma exibição no [Explorador de Ameaças.](threat-explorer.md)  Essa investigação também cria um alerta para que os Incidentes do Microsoft Defender e as ferramentas SIEM externas possam ver que essa investigação foi disparada.

Por exemplo, suponha que você está usando o exibição **malware** no Explorer. Usando as guias abaixo do gráfico, selecione a **guia Email.** Se você selecionar um ou mais itens na lista, o **botão + Ações** será ativado.

![Explorer com mensagens selecionadas](../../media/Explorer-Malware-Email-ActionsInvestigate.png)

Usando o menu **Ações,** você pode selecionar Investigação **de gatilho.**

![Menu Ações para mensagens selecionadas](../../media/explorer-malwareview-selectedemails-actions.jpg)

Semelhante aos playbooks disparados por um alerta, as investigações automáticas que são acionadas a partir de uma exibição no Explorer incluem uma investigação raiz, etapas para identificar e correlacionar ameaças e ações recomendadas para atenuar essas ameaças.

## <a name="example-a-security-operations-team-integrates-air-with-their-siem-using-the-office-365-management-activity-api"></a>Exemplo: uma equipe de operações de segurança integra o AIR ao SIEM usando a API da Atividade de Gerenciamento do Office 365

Os recursos air no Microsoft Defender para Office 365 incluem relatórios [&](air-view-investigation-results.md) detalhes que as equipes de operações de segurança podem usar para monitorar e resolver ameaças. Mas você também pode integrar recursos air com outras soluções. Exemplos incluem um sistema de gerenciamento de eventos e informações de segurança (SIEM), um sistema de gerenciamento de caso ou uma solução de relatório personalizada. Esses tipos de integrações podem ser feitos usando a API da Atividade de Gerenciamento do [Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)

Por exemplo, recentemente, uma organização configura uma maneira de sua equipe de operações de segurança exibir alertas de phishing relatados pelo usuário que já foram processados pelo AIR. Sua solução integra alertas relevantes ao servidor SIEM da organização e seu sistema de gerenciamento de caso. A solução reduz consideravelmente o número de falsos positivos para que sua equipe de operações de segurança possa concentrar seu tempo e esforço em ameaças reais. Para saber mais sobre essa solução personalizada, confira o blog tech community: melhorar a eficácia do seu SOC com o Microsoft Defender para Office 365 e a API de gerenciamento [do O365.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)

## <a name="next-steps"></a>Próximas etapas

- [Começar a usar o AIR](office-365-air.md)
- [Exibir ações de correção pendentes ou concluídas](air-review-approve-pending-completed-actions.md)
