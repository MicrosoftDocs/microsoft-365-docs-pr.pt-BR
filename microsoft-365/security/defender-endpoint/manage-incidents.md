---
title: Gerenciar o Microsoft Defender para incidentes de ponto de extremidade
description: Gerencie incidentes atribuindo-o, atualizando seu status ou definindo sua classificação.
keywords: incidentes, gerenciar, atribuir, status, classificação, alerta verdadeiro, alerta falso
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c86b53abf54788740c8c78cb0ecf9251b10ea8f7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842333"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a>Gerenciar o Microsoft Defender para incidentes de ponto de extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

O gerenciamento de incidentes é uma parte importante de cada operação de segurança cibernética. Você pode gerenciar incidentes selecionando um incidente na fila **incidentes ou** no painel de gerenciamento **de incidentes.** 


Selecionar um incidente na fila **Incidentes** traz o **painel** gerenciamento de incidentes onde você pode abrir a página de incidentes para obter detalhes.


![Imagem do painel de gerenciamento de incidentes](images/atp-incidents-mgt-pane-updated.png)

Você pode atribuir incidentes a si mesmo, alterar o status e a classificação, renomear ou comentar sobre eles para acompanhar seu progresso.

> [!TIP]
> Para obter visibilidade adicional rapidamente, os nomes de incidentes são gerados automaticamente com base em atributos de alerta, como o número de pontos de extremidade afetados, usuários afetados, fontes de detecção ou categorias. Isso permite que você entenda rapidamente o escopo do incidente.
>
> Por exemplo: *incidente em vários estágios em vários pontos de extremidade relatados por várias fontes.*
>
> Incidentes que existiam antes da adoção da nomenização automática de incidentes manterão seus nomes.
>


![Imagem da página de detalhes do incidente](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a>Atribuir incidentes
Se um incidente ainda não tiver sido atribuído, selecione Atribuir a **mim** para atribuir o incidente a si mesmo. Ao fazer isso, você assume a propriedade não apenas do incidente, como também de todos os alertas associados a ele.

## <a name="set-status-and-classification"></a>Definir o status e a classificação
### <a name="incident-status"></a>Status do incidente
Você pode categorizar os incidentes (como **Ativo** ou **Resolvido**) alterando o status deles durante sua investigação. Isso ajuda você a organizar e a gerenciar a maneira como sua equipe é capaz de responder a incidentes.

Por exemplo, seu analista soC pode revisar os incidentes **ativos** urgentes do dia e decidir atribuí-los a si mesmo para investigação.

Como alternativa, seu analista soC pode definir o incidente como **Resolvido** se o incidente tiver sido resolvido. 

### <a name="classification"></a>Classificação
Você pode optar por não definir uma classificação ou decidir especificar se um incidente é verdadeiro ou falso. Isso ajuda a equipe a ver padrões e a aprender com eles.

### <a name="add-comments"></a>Adicionar comentários
Você pode adicionar comentários e exibir eventos históricos sobre um incidente para ver as alterações feitas anteriormente.

Sempre que uma alteração ou um comentário forem feitos em um alerta, eles são registrados na seção Comentários e histórico.

Os comentários adicionados aparecem instantaneamente no painel.



## <a name="related-topics"></a>Tópicos relacionados
- [Fila de incidentes](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Exibir e organizar a Fila de incidentes](view-incidents-queue.md)
- [Investigar incidentes](investigate-incidents.md)
