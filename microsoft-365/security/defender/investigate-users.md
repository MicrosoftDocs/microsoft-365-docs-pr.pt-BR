---
title: Investigar usuários no Centro de segurança do Microsoft 365
description: investigar usuários no centro de segurança do Microsoft 365
keywords: segurança, malware, Microsoft 365, M365, central de segurança, monitor, relatório, identidades, dados, dispositivos, aplicativos
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
ms.openlocfilehash: 68fc924ee14932ebdf92ef76306ba00e352b6030
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861246"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a>Investigar usuários no Centro de segurança do Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aplica-se a:**

- Microsoft 365 Defender

Parte da investigação de incidentes pode incluir contas de usuário. Comece com a **guia Usuários** para um incidente de **Incidentes & alertas >** incidente *>* **Usuários**. 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Exemplo de uma página Usuários para um incidente":::

Para obter um resumo rápido de uma conta de usuário para o incidente, selecione a marca de seleção ao lado do nome da conta de usuário. Veja um exemplo.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="Exemplo do painel de resumo da conta de usuário para um incidente no centro de segurança do Microsoft 365":::

A partir daqui, você pode selecionar **Ir para a página do usuário** para ver os detalhes de uma conta de usuário. Veja um exemplo.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="Exemplo da página da conta de usuário para um incidente no centro de segurança do Microsoft 365":::

Você também pode ver esta página selecionando o nome da conta de usuário na lista na **página Usuários.**

A página de usuário do Centro de Segurança do Microsoft 365 combina informações do Microsoft Defender para Ponto de Extremidade, do Microsoft Defender para Identidade e do Microsoft Cloud App Security (dependendo das licenças que você tiver). 

Esta página mostra informações específicas do risco de segurança de uma conta de usuário. Isso inclui uma pontuação que ajuda a avaliar riscos e eventos recentes e alertas que contribuíram para o risco geral do usuário.

Nesta página, você pode fazer essas ações adicionais: 

- Marcar a conta de usuário como comprometida
- Exigir que o usuário entre novamente
- Suspender a conta de usuário
- Consulte as configurações da conta de usuário do Azure Active Directory (Azure AD)
- Exibir os arquivos pertencentes à conta de usuário
- Exibir arquivos compartilhados com esse usuário. 

Veja um exemplo.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Exemplo das ações em uma conta de usuário para um incidente no centro de segurança do Microsoft 365":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral dos incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Gerenciar incidentes](manage-incidents.md)