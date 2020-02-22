---
title: Endereçar contas de usuário comprometidas com investigação e resposta automatizadas no Office 365 proteção avançada contra ameaças
keywords: AIR, autoIR, ATP, automatizado, investigação, resposta, correção, ameaças, avançado, ameaça, proteção, comprometido
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
ms.date: 02/20/2020
description: Saiba como acelerar o processo de detecção e endereçamento de contas de usuário comprometidas com recursos de investigação e resposta automatizados no Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 7dfa1db02e777e3fdb546ebf948ebc297f1caad5
ms.sourcegitcommit: 8876c216954b94adce9cdf493c49bd5a10190a3a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42228557"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Endereçar contas de usuário comprometidas com investigação e resposta automatizadas

O [plano avançado de proteção contra ameaças do Office 365](office-365-atp.md#office-365-atp-plan-1-and-plan-2) inclui recursos avançados de [investigação e resposta](office-365-air.md) (Air). Esses recursos podem economizar sua equipe de operações de segurança muito tempo e esforço lidando com ameaças. A Microsoft continua a melhorar os recursos de segurança. Recentemente, os recursos de ar foram aprimorados para incluir um guia de segurança de usuário comprometido (atualmente em versão prévia). Leia este artigo para saber mais sobre o guia de segurança de usuário comprometido. E veja a velocidade da postagem do blog [para detectar e responder ao escopo do usuário e limitar o escopo de violação com o Office 365 ATP](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) para obter mais detalhes.

![Investigação automatizada para um usuário comprometido](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

O guia de segurança do usuário comprometido permite que a equipe de segurança da sua organização:

- Acelerar a detecção de contas de usuário comprometidas;

- Limitar o escopo de uma violação quando uma conta for comprometida; e 

- Responder aos usuários comprometidos de forma mais eficaz e eficiente.

## <a name="compromised-user-alerts"></a>Alertas de usuário comprometidos

Quando uma conta de usuário está comprometida, ocorrem comportamentos atypical ou anômalas. Por exemplo, mensagens de phishing e spam podem ser enviadas internamente por uma conta de usuário confiável. O Office 365 proteção avançada contra ameaças pode detectar essas anomalias em padrões de email e atividades de colaboração no Office 365. Quando isso acontecer, os alertas serão acionados e o processo de mitigação de ameaças começará.

Por exemplo, aqui está um alerta que foi acionado devido a um envio de emails suspeitos:

![Alerta acionado devido a envio de emails suspeitos](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

E aqui está um exemplo de um alerta que foi disparado quando um limite de envio foi atingido para um usuário:

![Alerta iniciado pelo limite de envio alcançado](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Investigar e responder a um usuário comprometido

Quando uma conta de usuário é comprometida, os alertas são acionados. E, em alguns casos, essa conta de usuário é bloqueada e impedida de enviar outras mensagens de email até que o problema seja resolvido pela equipe de operações de segurança da sua organização. Em outros casos, uma investigação automatizada começa, o que pode resultar em ações recomendadas que a equipe de segurança deve executar.

- [Exibir e investigar usuários restritos](#view-and-investigate-restricted-users)

- [Exibir detalhes sobre investigações automatizadas](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Você deve ter as permissões apropriadas para executar as tarefas a seguir. Confira [as permissões necessárias para usar os recursos de ar](office-365-air.md#required-permissions-to-use-air-capabilities).

### <a name="view-and-investigate-restricted-users"></a>Exibir e investigar usuários restritos

Você tem algumas opções para navegar para uma lista de usuários restritos. Por exemplo, no centro de conformidade & segurança do Office 365, você pode ir **para gerenciamento** > de ameaças**examinar** > **usuários restritos**. O procedimento a seguir descreve a navegação usando o painel de **alertas** , que é uma boa maneira de ver vários tipos de alertas que podem ter sido acionados.

1. Vá para [https://protection.office.com](https://protection.office.com) e entre.

2. No painel de navegação, escolha **** > **painel**de alerta.

3. No widget **outros alertas** , escolha **usuários restritos**.<br/>
   ![Widget outros alertas](/microsoft-365/media/office365atp-otheralertswidget.jpg)<br/>
   Isso abre a lista de usuários restritos.<br/>![Usuários restritos no Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg) 

4. Selecione uma conta de usuário na lista para exibir detalhes e executar ação, como [liberar o usuário restrito](removing-user-from-restricted-users-portal-after-spam.md). 

### <a name="view-details-about-automated-investigations"></a>Exibir detalhes sobre investigações automatizadas

Quando uma investigação automatizada começou, você poderá ver seus detalhes e resultados no centro de conformidade & segurança do Office 365. Vá para **** > **investigações**de gerenciamento de ameaças e selecione uma investigação para exibir seus detalhes.

Para saber mais, confira [Exibir detalhes de uma investigação](air-view-investigation-results.md#view-details-of-an-investigation).

## <a name="keep-the-following-points-in-mind"></a>Tenha em mente os seguintes pontos

- **Fique em cima dos alertas**. Como você sabe, quanto mais tempo um compromisso não for detectado, maior será o potencial de impacto e custo amplos para sua organização, clientes e parceiros. A detecção antecipada e a resposta oportuna são fundamentais para reduzir as ameaças e, especialmente, quando a conta de um usuário é comprometida. 

- **A automação auxilia, mas não substitui, sua equipe de operações de segurança**. Os recursos de investigação e resposta automatizados podem detectar um usuário comprometido logo no início, mas sua equipe de operações de segurança provavelmente precisará participar e realizar algumas investigações e remediação. Precisa de ajuda para isso? Consulte [revisar e aprovar ações](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions).

- **Não confie em um alerta de login suspeito como seu único indicador**. Quando uma conta de usuário é comprometida, ela pode ou não disparar um alerta de login suspeito. Às vezes, é a série de atividades que ocorrem após o comprometimento de uma conta que dispara um alerta. Quer saber mais sobre os alertas? Consulte [políticas de alerta](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).

## <a name="next-steps"></a>Próximas etapas

- [Revise as permissões necessárias para usar os recursos de ar](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Encontre e investigue emails mal-intencionados no Office 365](investigate-malicious-email-that-was-delivered.md)

- [Saiba mais sobre o AIR no Microsoft defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Visite o mapa do Microsoft 365 para ver o que está chegando em breve e distribuir](https://www.microsoft.com/microsoft-365/roadmap?filters=)

