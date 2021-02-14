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

Antes de habilitar o controle de aplicativos em seu ambiente, revise e entenda como a Área de Trabalho Gerenciada da [Microsoft](../service-description/app-control.md) o implementa e suas funções e responsabilidades.

A Área de Trabalho Gerenciada da Microsoft simplifica o controle de aplicativos ao cuidar dos aspectos mais desafiadores de obter uma política de base segura. Os administradores de IT ainda devem testar seus aplicativos no anel teste e revisar os logs em busca de avisos ou erros. Se um aplicativo precisar de uma isenção, você poderá fazer uma solicitação ou a Operação da Área de Trabalho Gerenciada da Microsoft poderá, dependendo de quem a detectar primeiro.

## <a name="initial-deployment-of-apps"></a>Implantação inicial de aplicativos

Quando você implanta aplicativos pela primeira vez, a Área de Trabalho Gerenciada da Microsoft precisa avaliar seu comportamento atual. As etapas exatas para ativar o controle de aplicativo dependem se os dispositivos já foram implantados em seu ambiente.

### <a name="devices-not-yet-in-use"></a>Dispositivos ainda não em uso

Se você ainda não tiver dispositivos em uso, abra um tíquete de serviço com as Operações de Área de Trabalho Gerenciada da Microsoft solicitando que a adoção do controle de aplicativo. As operações implantarão progressivamente políticas em grupos de implantação seguindo este cronograma:

|Grupo de implantação  |Tipo de política  |Tempo  |
|---------|---------|---------|
|Testar     |  Auditoria       |  Dia 0       |
|Primeiro     | Enforced        | 1º dia        |
|Rápida     | Enforced        |  2º dia       |
|Amplas     | Enforced        |  3º dia       |

Você sempre pode abrir outra solicitação de serviço para pausar ou reverter parte dessa implantação a qualquer momento durante a distribuição.

### <a name="devices-already-in-use"></a>Dispositivos já em uso

Se já tiver pelo menos um dispositivo de Área de Trabalho Gerenciada da Microsoft em uso, siga estas etapas:

1. Abra um tíquete de serviço com as Operações de Área de Trabalho Gerenciada da Microsoft solicitando que a adoção do controle do aplicativo. As operações implantarão uma [política de auditoria em](../service-description/app-control.md#audit-policy) todos os dispositivos.
2. [Teste seus aplicativos](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) para ver se algum seria bloqueado. Se um aplicativo seria bloqueado, abra uma [solicitação de signante.](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer) 
3. Depois de concluir o teste (independentemente dos resultados), notifique o Operations, notificando quaisquer solicitações pendentes do signante. As operações implantarão progressivamente políticas em grupos de implantação seguindo este cronograma:

|Grupo de implantação  |Tipo de política  |Tempo  |
|---------|---------|---------|
|Testar     |  Auditoria       |  Dia 0       |
|Primeiro     | Enforced        | 1º dia        |
|Rápida     | Enforced        |  Pausado, lançamento na solicitação       |
|Amplas     | Enforced        |  Pausado, lançamento na solicitação       |

Você sempre pode abrir outra solicitação de serviço para pausar ou reverter parte dessa implantação a qualquer momento durante a distribuição.



