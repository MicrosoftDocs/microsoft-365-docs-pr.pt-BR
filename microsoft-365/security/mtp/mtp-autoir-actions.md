---
title: Aprovar ou rejeitar ações pendentes após uma investigação automatizada
description: Use a Central de Ações para gerenciar ações relacionadas a investigações e respostas automáticas
keywords: ação, central, investigação e resposta automáticas, automação, investigação, resposta, correção
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.technology: m365d
ms.openlocfilehash: 3776dea4a5a24f4695a5c617325af14f1f03494f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930373"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a>Aprovar ou rejeitar ações pendentes após uma investigação automatizada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Quando uma investigação automatizada é executada, pode resultar em uma ou mais [ações de correção ](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) que exigem aprovação para prosseguir. Por exemplo, um cluster de mensagens de email pode precisar ser excluído, ou talvez seja necessário remover um arquivo em quarentena. É importante aprovar (ou rejeitar) ações pendentes o mais rápido possível, para que suas investigações automatizadas possam prosseguir e ser concluídas a tempo. 

> [!TIP]
> Se você acha que algo foi perdido ou detectado incorretamente pelos recursos de investigação e resposta automatizados no Microsoft 365 Defender, nos avise! Veja como relatar falsos positivos/negativos em recursos automatizados de investigação e resposta [(AIR) no Microsoft 365 Defender.](mtp-autoir-report-false-positives-negatives.md)

Ações pendentes podem ser revisadas e aprovadas usando a Central [de ações](#review-a-pending-action-in-the-action-center) ou a [exibição de detalhes da investigação.](#review-a-pending-action-in-the-investigation-details-view)

> [!NOTE]
> Você deve ter [permissões apropriadas](mtp-action-center.md#required-permissions-for-action-center-tasks) para aprovar ou rejeitar ações de correção. Para saber mais, confira Pré-requisitos para investigação e resposta [automatizadas no Microsoft 365 Defender.](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)

## <a name="review-a-pending-action-in-the-action-center"></a>Revisar uma ação pendente na Central de Ações

1. Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre. 

2. No painel de navegação, escolha **Central de Ações**. 

3. Em Central de Ações, na guia **Pendente**, selecione um item na lista. 

    - Se você selecionar um item na coluna **número da investigação**, a página detalhes da investigação será aberta. Nessa página, você pode checar os resultados da investigação e aprovar ou rejeitar a ação recomendada.
 
    - Se você selecionar uma linha na lista, um submenu será aberto, onde serão mostradas informações sobre esse item. <br/>![Aprovar ou rejeitar uma ação](../../media/air-actioncenter-itemselected.png)<br/>Use os links para exibir um alerta ou uma investigação associada e aprovar ou rejeitar a ação.

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>Revisar uma ação pendente na exibição dos detalhes da investigação

![Detalhes da investigação](../../media/mtp-air-investdetails.png)

1. Na página [detalhes da investigação](mtp-autoir-results.md), selecione a guia **Ações pendentes** (ou **Ações**). Os itens pendentes estarão listados aqui.

2. Selecione um item na lista e, em seguida, escolha **Aprovar** ou **Rejeitar**.

## <a name="undo-completed-actions"></a>Desfazer ações concluídas

Se você tiver determinado que um dispositivo ou um arquivo não é uma ameaça, poderá desfazer ações de correção que foram tomadas, se essas ações foram realizadas automaticamente ou manualmente. Na Central de ações, na guia **Histórico,** você pode desfazer qualquer uma das seguintes ações:  

| Origem da ação | Ações com suporte |
|:---|:---|
| - Investigação automatizada <br/>- Microsoft Defender Antivírus <br/>- Ações de resposta manual | - Isolar dispositivo <br/>- Restringir a execução de código <br/>- Colocar um arquivo em quarentena <br/>- Remover uma chave do Registro <br/>- Parar um serviço <br/>- Desabilitar um driver <br/>- Remover uma tarefa agendada |

### <a name="to-undo-a-remediation-action"></a>Para desfazer uma ação de correção

1. Vá para a Central de ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.

2. Na guia **Histórico,** selecione uma ação que você deseja desfazer.

3. No painel no lado direito da tela, selecione **Desfazer**.

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Para remover um arquivo da quarentena em vários dispositivos 

1. Vá para a Central de ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.

2. Na guia **Histórico,** selecione um arquivo que tenha o arquivo de quarentena do tipo **Ação.**

3. No painel no lado direito da tela, selecione Aplicar a **X mais instâncias** deste arquivo e selecione **Desfazer.**

## <a name="next-steps"></a>Próximas etapas

- [Exibir os detalhes e resultados de uma investigação automatizada](mtp-autoir-results.md)
- [Lidar com falsos positivos/negativos em recursos automatizados de investigação e resposta](mtp-autoir-report-false-positives-negatives.md)
