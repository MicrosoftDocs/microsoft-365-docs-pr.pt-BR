---
title: Resolver contas de usuário comprometidas com investigação e resposta automatizadas
keywords: AIR, autoIR, ATP, automatizado, investigação, resposta, correção, ameaças, avançado, ameaça, proteção, comprometido
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Saiba como acelerar o processo de detecção e endereçamento de contas de usuário comprometidas com recursos automatizados de investigação e resposta no Microsoft Defender para Office 365 Plano 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2159ab7ad7e13c4cd4c2c428317ee7d99f78158c
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2021
ms.locfileid: "50176058"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Resolver contas de usuário comprometidas com investigação e resposta automatizadas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


[O Microsoft Defender para Office 365 Plano 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) inclui poderosos recursos automatizados de investigação [e](office-365-air.md) resposta (AIR). Esses recursos podem economizar muito tempo e esforço para a equipe de operações de segurança lidando com ameaças. A Microsoft continua a melhorar os recursos de segurança. Recentemente, os recursos air foram aprimorados para incluir um playbook de segurança do usuário comprometido (atualmente em visualização). Leia este artigo para saber mais sobre o manual de segurança do usuário comprometido. E veja a postagem no blog Acelerar o tempo para detectar e responder ao comprometimento do usuário e limitar o escopo de violação com o [Microsoft Defender para Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) para obter detalhes adicionais.

![Investigação automatizada para um usuário comprometido](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

O manual de segurança do usuário comprometido permite que a equipe de segurança da sua organização:

- Acelerar a detecção de contas de usuário comprometidas;

- Limitar o escopo de uma violação quando uma conta for comprometida; e

- Responda aos usuários comprometidos com mais eficiência e eficiência.

## <a name="compromised-user-alerts"></a>Alertas de usuário comprometidos

Quando uma conta de usuário é comprometida, ocorrem comportamentos atípicos ou anômalos. Por exemplo, mensagens de phishing e spam podem ser enviadas internamente de uma conta de usuário confiável. O Defender para Office 365 pode detectar essas anomalias em padrões de email e atividade de colaboração no Office 365. Quando isso acontece, os alertas são disparados e o processo de mitigação de ameaças começa.

Por exemplo, aqui está um alerta que foi disparado por causa de emails suspeitos:

![Alerta acionado por causa de emails suspeitos](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

E aqui está um exemplo de um alerta que foi disparado quando um limite de envio foi atingido para um usuário:

![Alerta disparado pelo limite de envio atingido](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Investigar e responder a um usuário comprometido

Quando uma conta de usuário é comprometida, os alertas são disparados. E, em alguns casos, essa conta de usuário é bloqueada e impedida de enviar outras mensagens de email até que o problema seja resolvido pela equipe de operações de segurança da sua organização. Em outros casos, uma investigação automatizada começa, o que pode resultar em ações recomendadas que sua equipe de segurança deve tomar.

- [Exibir e investigar usuários restritos](#view-and-investigate-restricted-users)

- [Exibir detalhes sobre investigações automatizadas](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Você deve ter as permissões apropriadas para executar as tarefas a seguir. Consulte [Permissões necessárias para usar os recursos air](office-365-air.md#required-permissions-to-use-air-capabilities).

### <a name="view-and-investigate-restricted-users"></a>Exibir e investigar usuários restritos

Você tem algumas opções para navegar até uma lista de usuários restritos. Por exemplo, no Centro de Conformidade e Segurança &, você pode ir para **a** Revisão de Gerenciamento \> **de** Ameaças \> **Usuários Restritos.** O procedimento a seguir descreve a navegação usando o painel **Alertas,** que é uma boa maneira de ver vários tipos de alertas que podem ter sido disparados.

1. Acesse <https://protection.office.com> e entre.

2. No painel de navegação, escolha **Painel de** \> **Alertas.**

3. No widget **Outros alertas,** escolha **Usuários Restritos.**

   ![Widget Outros alertas](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   Isso abre a lista de usuários restritos.

   ![Usuários restritos no Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. Selecione uma conta de usuário na lista para exibir detalhes e tomar medidas, como [liberar o usuário restrito.](removing-user-from-restricted-users-portal-after-spam.md)

### <a name="view-details-about-automated-investigations"></a>Exibir detalhes sobre investigações automatizadas

Quando uma investigação automatizada tiver começado, você poderá ver seus detalhes e resultados no Centro de Conformidade & Segurança. Vá para **Investigações de Gerenciamento** \> **de** Ameaças e selecione uma investigação para exibir seus detalhes.

Para saber mais, consulte [Exibir detalhes de uma investigação.](air-view-investigation-results.md)

## <a name="keep-the-following-points-in-mind"></a>Lembre-se dos seguintes pontos

- **Fique por dentro dos seus alertas.** Como você sabe, quanto mais um comprometimento não for detectado, maior será o potencial de impacto e custo amplos para sua organização, clientes e parceiros. A detecção antecipada e a resposta em tempo hábil são fundamentais para reduzir as ameaças e, especialmente, quando a conta de um usuário é comprometida.

- **A automação auxilia, mas não substitui sua equipe de operações de segurança.** Os recursos automatizados de investigação e resposta podem detectar um usuário comprometido logo no início, mas sua equipe de operações de segurança provavelmente precisará se envolver e fazer alguma investigação e correção. Precisa de ajuda com isso? Consulte [Revisar e aprovar ações.](air-review-approve-pending-completed-actions.md)

- **Não confie em um alerta de logon suspeito como seu único indicador.** Quando uma conta de usuário é comprometida, ela pode ou não disparar um alerta de logon suspeito. Às vezes, é a série de atividades que ocorrem depois que uma conta é comprometida que dispara um alerta. Quer saber mais sobre alertas? Consulte [Políticas de alerta.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)

## <a name="next-steps"></a>Próximas etapas

- [Revise as permissões necessárias para usar os recursos air](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Encontrar e investigar emails mal-intencionados no Office 365](investigate-malicious-email-that-was-delivered.md)

- [Saiba mais sobre o AIR no Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Visite o mapa do Microsoft 365 para ver o que será lançando em breve](https://www.microsoft.com/microsoft-365/roadmap?filters=)
