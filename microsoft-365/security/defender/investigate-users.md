---
title: Investigue usuários no Microsoft 365 Defender
description: Investigue os usuários por um incidente no centro de segurança Microsoft 365.
keywords: segurança, malware, Microsoft 365, M365, centro de segurança, monitor, relatório, identidades, dados, dispositivos, aplicativos, incidente, análise, resposta
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 72eb111da2f342b78aa6161c7334a7252314b4a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572796"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>Investigue usuários no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

Parte de sua investigação de incidentes pode incluir contas de usuários. Comece com a guia **Usuários** para um incidente de **Incidentes & alertas >** *incidente* **> Usuários**. 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Exemplo de página de usuários para um incidente":::

Para obter um resumo rápido de uma conta de usuário para o incidente, selecione a marca de verificação ao lado do nome da conta de usuário. Veja um exemplo.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Exemplo do painel de resumo da conta de usuário para um incidente no centro de segurança Microsoft 365":::

> [!NOTE]
> A página do Usuário mostra Azure Active Directory organização (Azure AD) bem como grupos, ajudando você a entender os grupos e permissões associados a um usuário.

Nesta página de voo, você pode revisar informações sobre ameaças do usuário, incluindo quaisquer incidentes atuais, alertas ativos e nível de risco, bem como exposição ao usuário, contas, dispositivos e muito mais.

Além disso, você pode agir diretamente no centro de segurança Microsoft 365 para atender um usuário comprometido, confirmando que o usuário está comprometido ou exigindo que ele faça login novamente.

A partir daqui, você pode selecionar **Ir para a página do usuário** para ver os detalhes de uma conta de usuário. Veja um exemplo.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Exemplo da página da conta de usuário para um incidente no centro de segurança Microsoft 365":::

Você também pode ver esta página selecionando o nome da conta de usuário da lista na página **Usuários.**

A página do usuário do centro de segurança Microsoft 365 combina informações do Microsoft Defender para Endpoint, Microsoft Defender for Identity e Microsoft Cloud App Security (dependendo das licenças que você tem). 

Esta página mostra informações específicas para o risco de segurança de uma conta de usuário. Isso inclui uma pontuação que ajuda a avaliar riscos e eventos recentes e alertas que contribuíram para o risco geral do usuário.

A partir desta página, você pode fazer essas ações adicionais: 

- Marque a conta de usuário como comprometida
- Exija que o usuário faça login novamente
- Suspender a conta do usuário
- Veja as configurações da conta de usuário Azure Active Directory (Azure AD)
- Exibir os arquivos de propriedade da conta do usuário
- Exibir arquivos compartilhados com este usuário. 

Veja um exemplo.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Exemplo das ações em uma conta de usuário para um incidente no centro de segurança Microsoft 365":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a>Próximas etapas

Conforme necessário para incidentes em andamento, continue sua [investigação.](investigate-incidents.md)

## <a name="see-also"></a>Confira também

- [Visão geral dos incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Gerenciar incidentes](manage-incidents.md)