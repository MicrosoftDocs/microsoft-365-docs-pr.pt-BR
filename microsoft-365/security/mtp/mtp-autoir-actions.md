---
title: Aprovar ou rejeitar ações pendentes após a investigação automática
description: Use a Central de Ações para gerenciar ações relacionadas a investigações e respostas automáticas
keywords: ação, central, investigação e resposta automáticas, automação, investigação, resposta, correção
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 5c690d07af285b5232d383bb89071c3b64343772
ms.sourcegitcommit: 0c9c28a87201c7470716216d99175356fb3d1a47
ms.translationtype: MT + HT Review
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2019
ms.locfileid: "39910761"
---
# <a name="approve-or-reject-pending-actions-from-automated-investigations"></a>Aprovar ou rejeitar ações pendentes após a investigações automáticas

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!include[Prerelease information](prerelease.md)]

Quando uma investigação automatizada é executada, pode resultar em uma ou mais [ações de correção ](mtp-action-center.md#remediation-actions) que exigem aprovação para prosseguir. Por exemplo, um cluster de mensagens de email pode precisar ser excluído, ou talvez seja necessário remover um arquivo em quarentena. É importante aprovar (ou rejeitar) ações pendentes o mais rápido possível, para que suas investigações automatizadas possam prosseguir e ser concluídas a tempo. 

Ações pendentes podem ser revisadas e aprovadas usando um dos vários métodos abaixo:
- [Usando a Central de Ações](#review-a-pending-action-in-the-action-center)
- [Usando o modo de exibição detalhes da investigação](#review-a-pending-action-in-the-investigation-details-view)

> [!NOTE]
> Você deve ter [permissões apropriadas](mtp-action-center.md#required-permissions-for-action-center-tasks) para aprovar ou rejeitar ações de correção.

## <a name="review-a-pending-action-in-the-action-center"></a>Revisar uma ação pendente na Central de Ações

1. Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre. 

2. No painel de navegação, escolha **Central de Ações**. 

3. Em Central de Ações, na guia **Pendente**, selecione um item na lista. 

    - Se você selecionar um item na coluna**número da investigação **, a página detalhes da investigação será aberta. Nessa página, você pode checar os resultados da investigação e aprovar ou rejeitar a ação recomendada.
 
    - Se você selecionar uma linha na lista, um submenu será aberto, onde serão mostradas informações sobre esse item. <br/>![Aprovar ou rejeitar uma ação](../images/air-actioncenter-itemselected.png)<br/>Use os links para exibir um alerta ou uma investigação associada e aprovar ou rejeitar a ação.

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>Revisar uma ação pendente na exibição dos detalhes da investigação

![Detalhes da investigação](../images/mtp-air-investdetails.png)

1. Na página [detalhes da investigação](mtp-autoir-results.md), selecione a guia **Ações pendentes** (ou **Ações**). Os itens pendentes estarão listados aqui.

2. Selecione um item na lista e, em seguida, escolha **Aprovar** ou **Rejeitar**.

## <a name="next-steps"></a>Próximas etapas

- [Saiba mais sobre a Central de Ações](mtp-action-center.md)
- [Saiba mais sobre incidentes](incidents-overview.md)
- [Saiba mais sobre a caça avançada](advanced-hunting-overview.md)
