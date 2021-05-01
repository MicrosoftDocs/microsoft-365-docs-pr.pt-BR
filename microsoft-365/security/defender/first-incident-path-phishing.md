---
title: Exemplo de um ataque de email de phishing
description: Passo a passo de uma análise de exemplo de um ataque de phishing.
keywords: incidentes, alertas, investigar, correlação, ataque, máquinas, dispositivos, usuários, identidades, identidade, caixa de correio, email, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fb3656a9d3f67d979c012d9cc316a10e65a72042
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114506"
---
# <a name="example-of-a-phishing-email-attack"></a>Exemplo de um ataque de email de phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**
- Microsoft 365 Defender

Microsoft 365 O Defender pode ajudar a detectar anexos mal-intencionados entregues por email. Como [](https://protection.office.com/) Office 365 Central de Conformidade e Segurança se integra ao Microsoft 365 Defender, os analistas de segurança podem ter visibilidade sobre as ameaças que vêm do Office 365, como por meio de anexos de email.

Por exemplo, um analista foi atribuído a um incidente de vários estágios.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="Exemplo de um incidente em vários estágios"::: 

Na guia **Alertas** do incidente, os alertas do Defender para Office 365 e Microsoft Cloud App Security são exibidos. O analista pode detalhar o Defender para Office 365 alertas selecionando os alertas de mensagens de email. Os detalhes do alerta são exibidos no painel lateral.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="Exemplo de um alerta de email":::
 
Ao rolar para baixo, mais informações são exibidas, mostrando os arquivos mal-intencionados e o usuário afetado.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="Exemplo de impacto de usuário e arquivo de um alerta de email":::
  
Selecionar **a página Abrir alerta** leva você ao alerta específico onde várias informações podem ser exibidas com mais detalhes selecionando o link. A mensagem de email real pode ser exibida selecionando **Exibir mensagens** no Explorer em direção à parte inferior do painel.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="Exemplo dos detalhes de um alerta"::: 

Isso leva o analista para a página Gerenciamento de Ameaças onde o assunto de email, Destinatário, Remetente e outras informações são exibidos. **O ZAP** **em Ações Especiais** informa ao analista que o recurso de limpeza automática de hora zero foi implementado. O ZAP detecta e remove automaticamente mensagens mal-intencionadas e de spam de caixas de correio em toda a organização. Para obter mais informações, consulte Zap (limpeza automática de hora [zero) no Exchange Online](../office-365-security/zero-hour-auto-purge.md).

Outras ações podem ser tomadas em mensagens específicas selecionando **Ações**. 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="Exemplo das outras ações podem ser tomadas em mensagens de email"::: 

## <a name="next-step"></a>Próxima etapa

Consulte o [caminho de investigação de ataque baseado](first-incident-path-identity.md) em identidade.

## <a name="see-also"></a>Confira também

- [Visão geral dos incidentes](incidents-overview.md)
- [Analisar os incidentes](investigate-incidents.md)
- [Gerenciar incidentes](manage-incidents.md)
