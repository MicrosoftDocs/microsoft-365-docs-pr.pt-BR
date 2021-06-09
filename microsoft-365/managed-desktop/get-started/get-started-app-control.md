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
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430454"
---
# <a name="get-started-with-app-control"></a>Introdução ao controle de aplicativos

Antes de habilitar o controle de aplicativos em seu ambiente, não deixe de analisar e entender como Área de Trabalho Gerenciada da Microsoft o implementa e suas funções e responsabilidades. [](../service-description/app-control.md)

Área de Trabalho Gerenciada da Microsoft simplifica o controle de aplicativos, tomando conta dos aspectos mais desafiadores da obtenção de uma política de base segura. Os administradores de IT ainda devem testar seus aplicativos no anel de teste e revisar os logs em busca de avisos ou erros. Se um aplicativo precisar de uma isenção, você poderá arquivar uma solicitação, ou Área de Trabalho Gerenciada da Microsoft operação pode, dependendo de quem detectá-la primeiro.

## <a name="initial-deployment-of-apps"></a>Implantação inicial de aplicativos

Quando você implanta aplicativos pela primeira vez, Área de Trabalho Gerenciada da Microsoft precisa avaliar seu comportamento atual. As etapas exatas para habilenciar o controle de aplicativo dependem se os dispositivos já foram implantados em seu ambiente.

### <a name="devices-not-yet-in-use"></a>Dispositivos ainda não em uso

Se você ainda não tiver dispositivos em uso, abra um tíquete de serviço com Área de Trabalho Gerenciada da Microsoft Operações solicitando que abrimos o controle do aplicativo. As operações implantarão progressivamente políticas em grupos de implantação seguindo este cronograma:

|Grupo de implantação  |Tipo de política  |Tempo  |
|---------|---------|---------|
|Testar     |  Auditoria       |  Dia 0       |
|Primeiro     | Enforced        | 1º dia        |
|Rápida     | Enforced        |  2º dia       |
|Amplas     | Enforced        |  3º dia       |

Você sempre pode abrir outra solicitação de serviço para pausar ou reverter parte dessa implantação a qualquer momento durante a distribuição.

### <a name="devices-already-in-use"></a>Dispositivos já em uso

Se já tiver pelo menos um Área de Trabalho Gerenciada da Microsoft em uso, siga estas etapas:

1. Abra um tíquete de serviço com Área de Trabalho Gerenciada da Microsoft Operações solicitando que abrimos o controle do aplicativo. As operações implantarão uma [política de Auditoria](../service-description/app-control.md#audit-policy) em todos os dispositivos.
2. [Teste seus aplicativos](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) para ver se algum seria bloqueado. Se um aplicativo for bloqueado, abra uma [solicitação de signante](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer). 
3. Depois de concluir o teste (independentemente dos resultados), notifique Operações, notificando quaisquer solicitações pendentes do signator. As operações implantarão progressivamente políticas em grupos de implantação seguindo este cronograma:

|Grupo de implantação  |Tipo de política  |Tempo  |
|---------|---------|---------|
|Testar     |  Auditoria       |  Dia 0       |
|Primeiro     | Enforced        | 1º dia        |
|Rápida     | Enforced        |  Pausado, lançamento na solicitação       |
|Amplas     | Enforced        |  Pausado, lançamento na solicitação       |

Você sempre pode abrir outra solicitação de serviço para pausar ou reverter parte dessa implantação a qualquer momento durante a distribuição.



