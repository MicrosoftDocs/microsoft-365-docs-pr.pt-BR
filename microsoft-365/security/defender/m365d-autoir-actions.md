---
title: Exibir e gerenciar ações no Centro de Ações
description: Usar o Centro de Ações para exibir e gerenciar ações de correção
keywords: ação, central, investigação e resposta automáticas, automação, investigação, resposta, correção
search.appverid: met150
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
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: e3e842f812c5675334cc25fa35544165129db2b4
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245883"
---
# <a name="view-and-manage-actions-in-the-action-center"></a>Exibir e gerenciar ações no Centro de Ações

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Os recursos de proteção contra ameaças no Microsoft 365 Defender podem resultar em determinadas ações de correção. Aqui estão alguns exemplos:
- [Investigações automatizadas](m365d-autoir.md) podem resultar em ações de correção que são realizadas automaticamente ou aguardam aprovação.
- Antivírus, antimalware e outros recursos de proteção contra ameaças podem resultar em ações de correção, como bloquear um arquivo, URL ou processo ou enviar um artefato para a quarentena.
- Sua equipe de operações de segurança pode realizar [](advanced-hunting-overview.md) ações de correção manualmente, como durante a busca avançada ou durante a investigação de [alertas](investigate-alerts.md) [ou incidentes.](investigate-incidents.md)

> [!NOTE]
> Você deve ter [permissões apropriadas](m365d-action-center.md#required-permissions-for-action-center-tasks) para aprovar ou rejeitar ações de correção. Para obter mais informações, consulte [Prerequisites for automated investigation and response in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).

## <a name="review-pending-actions-in-the-action-center"></a>Revisar ações pendentes no Centro de Ações

É importante aprovar (ou rejeitar) ações pendentes o mais rápido possível, para que suas investigações automatizadas possam prosseguir e ser concluídas a tempo. 

![Aprovar ou rejeitar uma ação](../../media/air-actioncenter-itemselected.png)

1. Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre. 

2. No painel de navegação, escolha **Central de Ações**. 

3. Em Central de Ações, na guia **Pendente**, selecione um item na lista. Seu painel de sobrevoo é aberto.

4. Revise as informações no painel de sobrevoos e, em seguida, dê uma das seguintes etapas:
   - Selecione **Abrir página de investigação** para exibir mais detalhes sobre a investigação.
   - Selecione **Aprovar** para iniciar uma ação pendente.
   - Selecione **Rejeitar** para impedir que uma ação pendente seja tomada.
   - Selecione **Ir procurar** para entrar em Busca [Avançada](advanced-hunting-overview.md). 

## <a name="undo-completed-actions"></a>Desfazer ações concluídas

Se você tiver determinado que um dispositivo ou um arquivo não é uma ameaça, poderá desfazer as ações de correção que foram tomadas, se essas ações foram tomadas automaticamente ou manualmente. Na central de ações, na guia **Histórico,** você pode desfazer qualquer uma das seguintes ações:  

| Origem da ação | Ações com suporte |
|:---|:---|
| - Investigação automatizada <br/>- Microsoft Defender Antivírus <br/>- Ações de resposta manual | - Isolar dispositivo <br/>- Restringir a execução de código <br/>- Colocar em quarentena um arquivo <br/>- Remover uma chave do Registro <br/>- Interromper um serviço <br/>- Desabilitar um driver <br/>- Remover uma tarefa agendada |

### <a name="undo-one-remediation-action"></a>Desfazer uma ação de correção

1. Vá para a Central de Ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.

2. Na guia **Histórico,** selecione uma ação que você deseja desfazer.

3. No painel no lado direito da tela, selecione **Desfazer**.

### <a name="undo-multiple-remediation-actions"></a>Desfazer várias ações de correção

1. Vá para a Central de Ações ( https://security.microsoft.com/action-center) e entre.

2. Na guia **Histórico,** selecione as ações que você deseja desfazer. Certifique-se de selecionar itens que tenham o mesmo tipo de Ação. Um painel de sobrevoo é aberto.

3. No painel de sobrevoos, selecione **Desfazer**.

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Para remover um arquivo da quarentena em vários dispositivos 

1. Vá para a Central de Ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.

2. Na guia **Histórico,** selecione um arquivo que tenha o arquivo De quarentena tipo **ação.**

3. No painel no lado direito da tela, selecione Aplicar a X mais **instâncias** deste arquivo e selecione **Desfazer**.

## <a name="next-steps"></a>Próximas etapas

- [Exibir os detalhes e resultados de uma investigação automatizada](m365d-autoir-results.md)
- [Saiba como lidar com falsos positivos/negativos (se você receber um)](m365d-autoir-report-false-positives-negatives.md)
