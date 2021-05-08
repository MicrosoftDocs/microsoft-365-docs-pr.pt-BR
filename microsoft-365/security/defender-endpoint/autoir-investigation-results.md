---
title: Exibir os detalhes e resultados de uma investigação automatizada
description: Durante e após uma investigação automática, você pode exibir os resultados e as principais descobertas
keywords: automatização, investigação, resultados, análise, detalhes, correção, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: c593dfe384649b1599d5c0bab8fa6a8204d105dc
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274827"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a>Exibir os detalhes e resultados de uma investigação automatizada

**Aplica-se a:**
- Microsoft Defender para Ponto de Extremidade

Com o Microsoft Defender para [](automated-investigations.md) Ponto de Extremidade, quando uma investigação automatizada é executado, os detalhes sobre essa investigação ficam disponíveis durante e após o processo de investigação automatizado. Se você tiver as permissões necessárias, poderá exibir esses detalhes na exibição de detalhes da investigação. A exibição de detalhes da investigação fornece o status atualizado e a capacidade de aprovar as ações pendentes. 

## <a name="new-unified-investigation-page"></a>(NEW!) Página de investigação unificada

A página de investigação foi atualizada recentemente para incluir informações em seus dispositivos, email e conteúdo de colaboração. A nova página de investigação unificada define um idioma comum e fornece uma experiência unificada para investigações automáticas no [Microsoft Defender para Ponto](microsoft-defender-endpoint.md) de Extremidade e no Microsoft [Defender](/microsoft-365/security/office-365-security/office-365-atp)para Office 365 . 

> [!TIP]
> Para saber mais sobre o que está mudando, consulte [(NEW!) Página de investigação unificada](/microsoft-365/security/mtp/mtp-autoir-results).

## <a name="open-the-investigation-details-view"></a>Abrir a exibição de detalhes da investigação

Você pode abrir a exibição de detalhes da investigação usando um destes métodos:
- [Selecionar um item na central de Ações](#select-an-item-in-the-action-center)
- [Selecionar uma investigação em uma página de detalhes do incidente](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Selecionar um item na central de Ações

O Centro de Ações [aprimorado](auto-investigation-action-center.md) reúne ações [de correção](manage-auto-investigation.md#remediation-actions) em seus dispositivos, email & conteúdo de colaboração e identidades. As ações listadas incluem ações de correção que foram realizadas automaticamente ou manualmente. No Centro de ações, você pode exibir ações que estão aguardando aprovação e ações que já foram aprovadas ou concluídas. Você também pode navegar até mais detalhes, como uma página de investigação.

1. Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre. 
2. No painel de navegação, escolha **Central de ações**. 
3. Na guia **Pendente** ou **Histórico**, selecione um item. Seu painel de sobrevoo é aberto.
4. Revise as informações no painel de sobrevoos e, em seguida, dê uma das seguintes etapas:
   - Selecione **Abrir página de investigação** para exibir mais detalhes sobre a investigação.
   - Selecione **Aprovar** para iniciar uma ação pendente.
   - Selecione **Rejeitar** para impedir que uma ação pendente seja tomada.
   - Selecione **Ir procurar** para entrar em Busca [Avançada](advanced-hunting-overview.md).

### <a name="open-an-investigation-from-an-incident-details-page"></a>Abrir uma investigação em uma página de detalhes do incidente

Use uma página de detalhes do incidente para exibir informações detalhadas sobre um incidente, incluindo os alertas que foram disparados com informações sobre os dispositivos afetados, contas de usuários ou caixas de correio.

1. Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre. 
2. No painel de navegação, escolha **Incidentes &**  >  **alertas Incidentes**. 
3. Selecione um item na lista e escolha **Abrir página de incidentes**.
4. Selecione a **guia Investigações** e selecione uma investigação na lista. Seu painel de sobrevoo é aberto.
5. Selecione **Abrir página de investigação**. 

## <a name="investigation-details"></a>Detalhes da investigação

Use o modo de exibição de detalhes da investigação para ver as atividades antigas, atuais e pendentes referentes a uma investigação. A exibição de detalhes de investigação se parece com a seguinte imagem:

Na exibição de detalhes da investigação, você pode ver as informações nas guias **Gráfico de Investigação**, **Alertas**, **Dispositivos**, **Identidades**, **Principais descobertas**, **Entidades**,**Log** e **Ações pendentes**, descritas na tabela a seguir.

> [!NOTE]
> As guias específicas que você vê em uma página de detalhes da investigação dependem do que sua assinatura inclui. Por exemplo, se sua assinatura não incluir o Microsoft Defender para Office 365 Plano 2, você não verá uma guia **Caixas de** Correio.

| Guia | Descrição |
|:--------|:--------|
| **Gráficos de investigação**   | Oferece uma representação visual da investigação. Descreve entidades e lista as ameaças encontradas, juntamente com os alertas, e se as ações estão aguardando aprovação.<br/>Você pode selecionar um item no gráfico para exibir mais detalhes. Por exemplo, selecionar **o ícone**  Evidência o leva à guia Evidências, onde você pode ver entidades detectadas e seus vereditos. |
| **Alertas**    | Lista os alertas associados à investigação. Os alertas podem vir de recursos de proteção contra ameaças no dispositivo de um usuário, em Office aplicativos, Cloud App Security e outros recursos Microsoft 365 Defender.|
| **Dispositivos** | Lista os dispositivos incluídos na investigação juntamente com seu nível de correção. (Os níveis de correção correspondem ao nível [de automação para grupos de dispositivos](automation-levels.md).) |
| **Caixas de correio** |Lista caixas de correio que são impactadas por ameaças detectadas.  |
| **Usuários**  | Lista contas de usuário que são impactadas por ameaças detectadas. |
| **Evidências** | Lista partes de evidências levantadas por alertas/investigações. Inclui vereditos (*Mal-intencionados,* *suspeitos* ou *nenhuma ameaça encontrada*) e status de correção. |
| **Entities**  | Fornece detalhes sobre cada entidade analisada, incluindo um veredito para cada tipo de entidade (*Mal-intencionado,* *suspeito* ou *nenhuma ameaça encontrada*).|
|**Log**    | Fornece uma exibição cronológica e detalhada de todas as ações de investigação realizadas após a acionamento de um alerta.|
| **Ações pendentes** | Lista os itens que exigem aprovação para prosseguir. Vá para a Central de Ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) para aprovar ações pendentes. |

## <a name="see-also"></a>Confira também

- [Revisar ações de correção após uma investigação automatizada](manage-auto-investigation.md)
- [Exibir e organizar a fila do Microsoft Defender para Incidentes de Ponto de Extremidade](view-incidents-queue.md)