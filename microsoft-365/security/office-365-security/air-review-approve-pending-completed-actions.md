---
title: Analisar e gerenciar ações de correção no Microsoft Defender para Office 365
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automated, investigation, response, remediation, threats, advanced, threat, protection
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Saiba mais sobre ações de correção em recursos automatizados de investigação e resposta no Microsoft Defender para Office 365 Plano 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: 8fc01ab0dd5178032ea7b101f5361c25bb10bbea
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028926"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Analisar e gerenciar ações de correção em Office 365

**Aplica-se a**
- [Plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)

À medida que investigações automatizadas no email & conteúdo  de colaboração resultam em vereditos, como Mal-intencionados ou *suspeitos,* determinadas ações de correção são criadas. No Microsoft Defender para Office 365, as ações de correção podem incluir:

- Exclusão suave de mensagens de email ou clusters
- Desligar o encaminhamento de email externo

Essas ações de correção não serão tomadas, a menos que e até que sua equipe de operações de segurança as aprove. Recomendamos revisar e aprovar todas as ações pendentes assim que possível para que suas investigações automatizadas concluam em tempo hábil. Em alguns casos, você pode reconsiderar as ações enviadas.  Você precisa fazer parte do Search & função de limpeza antes de realizar qualquer ação.


## <a name="approve-or-reject-pending-actions"></a>Aprovar (ou rejeitar) ações pendentes
Há quatro maneiras diferentes de encontrar e tomar ações de investigação automática:

- [Fila de incidentes](https://security.microsoft.com/incidents)
- [Central de ações](https://security.microsoft.com/action-center/pending)
- Investigação em si (acessada por meio de Incidente ou de um alerta)
- [Fila de investigações de investigação e correção](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a>Fila de incidentes
1. Vá para o centro [Microsoft 365 segurança e](https://security.microsoft.com) entre.
2. No painel de navegação, selecione **Incidentes & alertas > Incidentes**.
3. Selecione um nome de incidente para abrir sua página de resumo.
4. Selecione a **guia Evidência e Resposta.**
5. Selecione um item na lista. Seu painel lateral é aberto.
6. No painel lateral, tome ações de aprovação ou rejeição.

## <a name="investigation-queue"></a>Fila de investigação 
1. Vá para o centro [Microsoft 365 segurança e](https://security.microsoft.com) entre.
2. Navegue na página alertas/incidentes. 
3. Na página Investigação, vá para a guia **Ações pendentes.** 
4. Selecione um item na lista. Seu painel lateral é aberto.  
5. No painel lateral, tome ações de aprovação ou rejeição.

## <a name="action-center"></a>Central de ações
1. Vá para o centro [Microsoft 365 segurança e](https://security.microsoft.com) entre.
2. No painel de navegação, selecione **Centro de ações**.
3. Na guia **Pendente,** revise a lista de ações que estão aguardando aprovação.
   - Selecione **Abrir página de investigação** para exibir mais detalhes sobre a investigação.
   - Selecione **Aprovar** para iniciar uma ação pendente.
   - Selecione **Rejeitar** para impedir que uma ação pendente seja tomada.

## <a name="investigation-and-remediation-investigations-queue"></a>Fila de investigações de investigação e correção
1. Vá para o centro [Microsoft 365 segurança e](https://security.microsoft.com) entre.
2. Abra investigações pendentes. 
3. Na página Investigação, vá para a guia **Ações pendentes.**
4. Selecione um item na lista. Seu painel lateral é aberto.  
5. No painel lateral, tome ações de aprovação ou rejeição.

## <a name="change-or-undo-one-remediation-action"></a>Alterar ou desfazer uma ação de correção

Há duas maneiras diferentes de reconsiderar as ações enviadas:
   - Por meio do [centro de ações unificado](https://security.microsoft.com/action-center).
   - Embora o [centro de Office de ação](https://security.microsoft.com/threatincidents).
   
## <a name="change-or-undo-through-the-unified-action-center"></a>Alterar ou desfazer por meio do centro de ações unificado
1. Vá para o [centro de ações unificado](https://security.microsoft.com/action-center) e entre.
2. Na guia **Histórico,** selecione uma ação que você deseja alterar ou desfazer.
3. No painel no lado direito da tela, selecione a ação apropriada **(** mover para a caixa de **entrada,** mover para lixo **eletrônico,** mover para itens excluídos , **exclusão suave", ou **excluir** rígido ).

 ## <a name="change-or-undo-through-the-office-action-center"></a>Alterar ou desfazer através do centro de Office de ação 
1. Vá para o centro [de Office e](https://security.microsoft.com/threatincidents) entre.
2. Selecione a correção apropriada.
3. No painel lateral, clique na entrada envios de email e aguarde o carregamento da lista. 
4. Aguarde o botão Ação na parte superior para habilitar e selecione o botão Ação para alterar o tipo de ação. 
5. Isso criará as ações apropriadas.

## <a name="next-steps"></a>Próximas etapas

- [Usar o Explorador de Ameaças](threat-explorer.md) 
- [Ações de administrador /manual](remediate-malicious-email-delivered-office-365.md)
- [Como relatar falsos positivos/negativos em recursos automatizados de investigação e resposta](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Confira também

- [Exibir detalhes e resultados de uma investigação automatizada no Office 365](air-view-investigation-results.md)
