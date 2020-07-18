---
title: Introdução ao controle de aplicativos
description: ''
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 12df7b074019ea47f2e293b71c6b0b25fe46f66f
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170679"
---
# <a name="get-started-with-app-control"></a>Introdução ao controle de aplicativos

Antes de habilitar o controle de aplicativos em seu ambiente, leia e entenda [como a área de trabalho gerenciada da Microsoft implementa](../service-description/app-control.md) e suas funções e responsabilidades.

O Microsoft Managed desktop simplifica o controle de aplicativos ao cuidar dos aspectos mais desafiadores de obter uma política de base segura. Seus administradores de ti ainda devem testar seus aplicativos no anel de teste e examinar os logs em busca de erros ou avisos. Se um aplicativo precisar de uma isenção, você poderá arquivar uma solicitação, ou a operação de área de trabalho gerenciada da Microsoft poderá, dependendo de quem a detecta primeiro.

## <a name="initial-deployment-of-apps"></a>Implantação inicial de aplicativos

Quando você implanta aplicativos pela primeira vez, o Microsoft Managed desktop precisa avaliar seu comportamento atual. As etapas exatas para habilitar o controle de aplicativos dependem se os dispositivos já foram implantados em seu ambiente.

### <a name="devices-already-in-use"></a>Dispositivos já em uso

Se já tiver pelo menos um dispositivo de área de trabalho gerenciado da Microsoft em uso, siga estas etapas:

1. Abra um tíquete de serviço com operações de área de trabalho gerenciada da Microsoft solicitando que nós ativamos o controle de aplicativos. As operações irão implantar uma [política de auditoria](../service-description/app-control.md#audit-policy) para todos os dispositivos.
2. [Teste seus aplicativos](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) para ver se qualquer um será bloqueado. Se um aplicativo for bloqueado, abra uma [solicitação de signatário](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer). 
3. Após concluir o teste (seja qual for o resultado), notifique as operações, observando todas as solicitações de signatário pendentes. As operações implantarão progressivamente políticas em grupos de implantação seguindo esta programação:

|Grupo de implantação  |Tipo de política  |Tempo  |
|---------|---------|---------|
|Testar     |  Auditoria       |  Dia 0       |
|Primeiro     | Enforced        | 1º dia        |
|Rápida     | Enforced        |  3º dia       |
|Amplas     | Enforced        |  Day 7       |

Você sempre pode abrir outra solicitação de serviço para pausar ou reverter parte dessa implantação a qualquer momento durante a distribuição.

### <a name="devices-not-yet-in-use"></a>Dispositivos que ainda não estão em uso

Se você ainda não tiver dispositivos em uso, abra um tíquete de serviço com operações de área de trabalho gerenciada da Microsoft solicitando que o controle de aplicativos seja ativado. As operações implantarão progressivamente políticas em grupos de implantação seguindo esta programação:

|Grupo de implantação  |Tipo de política  |Tempo  |
|---------|---------|---------|
|Testar     |  Auditoria       |  Dia 0       |
|Primeiro     | Enforced        | 1º dia        |
|Rápida     | Enforced        |  3º dia       |
|Amplas     | Enforced        |  Day 7       |

Você sempre pode abrir outra solicitação de serviço para pausar ou reverter parte dessa implantação a qualquer momento durante a distribuição.

