---
title: Resolver contas de usuário comprometidas com investigação e resposta automatizadas
keywords: AIR, autoIR, Microsoft Defender para Ponto de Extremidade, automatizado, investigação, resposta, correção, ameaças, avançado, ameaça, proteção, comprometido
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
ms.date: 06/10/2021
description: Saiba como acelerar o processo de detecção e endereçamento de contas de usuário comprometidas com recursos automatizados de investigação e resposta no Microsoft Defender para Office 365 Plano 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fd1ad6f52114340153f3958441bfb9500db67215
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108566"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Resolver contas de usuário comprometidas com investigação e resposta automatizadas

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


[O Microsoft Defender para Office 365 Plano 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) inclui poderosos recursos automatizados de investigação [e](office-365-air.md) resposta (AIR). Esses recursos podem economizar muito tempo e esforço com a equipe de operações de segurança lidando com ameaças. A Microsoft continua a melhorar os recursos de segurança. Recentemente, os recursos AIR foram aprimorados para incluir um playbook de segurança do usuário comprometido (atualmente na visualização). Leia este artigo para saber mais sobre o playbook de segurança do usuário comprometido. E consulte a postagem do blog [Acelere](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) o tempo para detectar e responder ao comprometimento do usuário e limitar o escopo de violação com o Microsoft Defender Office 365 para obter detalhes adicionais.

![Investigação automatizada para um usuário comprometido](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

O playbook de segurança do usuário comprometido permite que a equipe de segurança da sua organização:

- Acelerar a detecção de contas de usuário comprometidas;
- Limitar o escopo de uma violação quando uma conta for comprometida; e
- Responder aos usuários comprometidos de forma mais eficaz e eficiente.

## <a name="compromised-user-alerts"></a>Alertas de usuário comprometidos

Quando uma conta de usuário é comprometida, ocorrem comportamentos atípicos ou anômalos. Por exemplo, mensagens de phishing e spam podem ser enviadas internamente de uma conta de usuário confiável. O Defender para Office 365 pode detectar essas anomalias nos padrões de email e na atividade de colaboração dentro Office 365. Quando isso acontece, os alertas são disparados e o processo de mitigação de ameaças começa.

Por exemplo, aqui está um alerta que foi disparado devido ao envio de emails suspeitos:

![Alerta disparado por causa do envio de emails suspeitos](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

E aqui está um exemplo de um alerta que foi disparado quando um limite de envio foi atingido para um usuário:

![Alerta disparado pelo limite de envio atingido](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Investigar e responder a um usuário comprometido

Quando uma conta de usuário é comprometida, os alertas são disparados. E, em alguns casos, essa conta de usuário é bloqueada e impedida de enviar outras mensagens de email até que o problema seja resolvido pela equipe de operações de segurança da sua organização. Em outros casos, uma investigação automatizada começa, o que pode resultar em ações recomendadas que sua equipe de segurança deve tomar.

- [Exibir e investigar usuários restritos](#view-and-investigate-restricted-users)

- [Exibir detalhes sobre investigações automatizadas](#view-details-about-automated-investigations)

> [!IMPORTANT]
> Você deve ter permissões apropriadas para executar as seguintes tarefas. Consulte [Permissões necessárias para usar recursos AIR.](office-365-air.md#required-permissions-to-use-air-capabilities)

### <a name="view-and-investigate-restricted-users"></a>Exibir e investigar usuários restritos

Você tem algumas opções para navegar até uma lista de usuários restritos. Por exemplo, no portal Microsoft 365 Defender, você pode ir para **Email & colaboração** \> **Revisar** \> **Usuários Restritos.** O procedimento a seguir descreve a navegação usando o painel **Alertas,** que é uma boa maneira de ver vários tipos de alertas que podem ter sido disparados.

1. Abra o Microsoft 365 Defender portal ( ) e vá para <https://security.microsoft.com> **Incidentes &** \> **alertas**. Ou, para ir diretamente para a página **Alertas,** use <https://security.microsoft.com/alerts> .

2. Na página **Alertas,** filtre os resultados por período de tempo e a política chamada **Usuário restringida de enviar emails**.

   ![A página Alertas no portal Microsoft 365 Defender filtrada para usuários restritos](../../media/m365-sc-alerts-page-with-restricted-user.png)

3. Se você selecionar a entrada clicando no nome, um Usuário restrito de enviar página de **email** será aberto com detalhes adicionais para revisar. Ao lado do **botão Gerenciar** alerta, você pode clicar em Mais opções ícone Mais opções e, em seguida, selecione Exibir detalhes de usuário restritos para ir para a página Usuários restritos, onde você pode liberar o usuário ![ ](../../media/m365-cc-sc-more-actions-icon.png)  [restrito](removing-user-from-restricted-users-portal-after-spam.md).  

   ![O usuário impedido de enviar página de email do Centro de Alertas](../../media/m365-sc-alerts-user-restricted-from-sending-email-page.png)

### <a name="view-details-about-automated-investigations"></a>Exibir detalhes sobre investigações automatizadas

Quando uma investigação automatizada é iniciada, você pode ver seus detalhes e resultados no Centro de Conformidade & Segurança. Vá para **Investigações de gerenciamento** \> **de** ameaças e selecione uma investigação para exibir seus detalhes.

Para saber mais, confira [Exibir detalhes de uma investigação](air-view-investigation-results.md).

## <a name="keep-the-following-points-in-mind"></a>Lembre-se dos seguintes pontos

- **Fique por dentro de seus alertas.** Como você sabe, quanto mais um comprometimento for detectado, maior será o potencial de impacto e custo generalizados para sua organização, clientes e parceiros. A detecção antecipada e a resposta em tempo hábil são fundamentais para reduzir as ameaças e, especialmente quando a conta de um usuário é comprometida.

- **A automação ajuda, mas não substitui, sua equipe de operações de segurança.** Os recursos automatizados de investigação e resposta podem detectar um usuário comprometido no início, mas sua equipe de operações de segurança provavelmente precisará se envolver e fazer alguma investigação e correção. Precisa de ajuda com isso? Consulte [Revisar e aprovar ações.](air-review-approve-pending-completed-actions.md)

- **Não confie em um alerta de logon suspeito como seu único indicador**. Quando uma conta de usuário é comprometida, ela pode ou não disparar um alerta de logon suspeito. Às vezes, é a série de atividades que ocorrem depois que uma conta é comprometida que dispara um alerta. Quer saber mais sobre alertas? Consulte [Políticas de alerta](../../compliance/alert-policies.md).

## <a name="next-steps"></a>Próximas etapas

- [Revise as permissões necessárias para usar recursos AIR](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Encontre e investigue emails mal-intencionados Office 365](investigate-malicious-email-that-was-delivered.md)

- [Saiba mais sobre AIR no Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Visite o Microsoft 365 mapa do Microsoft 365 para ver o que está por vir em breve e a ser implantada](https://www.microsoft.com/microsoft-365/roadmap?filters=)