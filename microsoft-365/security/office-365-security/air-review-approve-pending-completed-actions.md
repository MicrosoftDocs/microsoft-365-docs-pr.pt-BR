---
title: Revisar e gerenciar ações de correção no Microsoft Defender para Office 365
keywords: AIR, autoIR, ATP, automatizado, investigação, resposta, correção, ameaças, avançado, ameaça, proteção
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
ms.date: 01/29/2021
ms.openlocfilehash: 3fb77fa41ff3e9af995cf80b9f4024aa92a51212
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2021
ms.locfileid: "50176010"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Revisar e gerenciar ações de correção no Office 365

Como investigações automatizadas em emails & conteúdo de colaboração  resultam em vereditos, como Mal-intencionados ou *suspeitos,* determinadas ações de correção são criadas. No Microsoft Defender para Office 365, as ações de correção podem incluir:
- Bloqueando uma URL (hora do clique)
- Exclusão suave de mensagens de email ou clusters
- Quarentena de emails ou anexos de email
- Como desligar o encaminhamento de email externo

Essas ações de correção não serão tomadas, a menos e até que sua equipe de operações de segurança as aprove. Recomendamos analisar e aprovar todas as ações pendentes assim que possível para que suas investigações automatizadas seja concluídas em tempo hábil. Em alguns casos, você pode desfazer uma ação de correção.

**Aplica-se a**
- [Microsoft Defender para Office 365 plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="approve-or-reject-pending-actions"></a>Aprovar (ou rejeitar) ações pendentes

1. Vá para a central de segurança do Microsoft 365 [https://security.microsoft.com](https://security.microsoft.com) ) e entre.
2. No painel de navegação, selecione Central **de ações.**
3. Na guia **Pendente,** revise a lista de ações que estão aguardando aprovação.
4. Selecione um item na lista. Seu painel de sobrevoo é aberto. 
5. Revise as informações no painel do flyout e, em seguida, tome uma das seguintes etapas:
   - Selecione **a página Abrir investigação** para exibir mais detalhes sobre a investigação.
   - Selecione **Aprovar** para iniciar uma ação pendente.
   - Selecione **Rejeitar** para impedir que uma ação pendente seja tomada.

## <a name="undo-one-remediation-action"></a>Desfazer uma ação de correção

1. Vá para a Central de ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.
2. Na guia **Histórico,** selecione uma ação que você deseja desfazer.
3. No painel no lado direito da tela, selecione **Desfazer**.

## <a name="undo-multiple-remediation-actions"></a>Desfazer várias ações de correção

1. Vá para a Central de ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.
2. Na guia **Histórico,** selecione as ações que você deseja desfazer. Certifique-se de selecionar itens que tenham o mesmo tipo de ação. Um painel de sobrevoo é aberto.
3. No painel do flyout, selecione Desfazer.

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Para remover um arquivo da quarentena em vários dispositivos

1. Vá para a Central de ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.
2. Na guia **Histórico,** selecione um arquivo que tenha o arquivo de quarentena do tipo **Ação.**
3. No painel no lado direito da tela, selecione Aplicar a **X mais instâncias** deste arquivo e selecione **Desfazer.**

## <a name="next-steps"></a>Próximas etapas

- [Usar o Explorador de Ameaças](threat-explorer.md)
- [Como relatar falsos positivos/negativos em recursos automatizados de investigação e resposta](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Confira também

- [Exibir detalhes e resultados de uma investigação automatizada no Office 365](air-view-investigation-results.md)
