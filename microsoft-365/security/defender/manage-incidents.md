---
title: Gerenciar incidentes no Microsoft 365 Defender
description: Saiba como atribuir, atualizar o status,
keywords: incidente, incidentes, alertas, alertas correlacionados, atribuir, atualizar, status, gerenciar, classificação, microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 4e216f841c8728b1cabd98a931e7326f53344a74
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053503"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>Gerenciar incidentes no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender



Gerenciar incidentes é fundamental para garantir que as ameaças sejam contidas e tratadas. No Microsoft 365 Defender, você tem acesso ao gerenciamento de incidentes em dispositivos, usuários e caixas de correio. 


Você pode gerenciar incidentes selecionando um deles da **fila de incidentes**. 

Você pode editar o nome de um incidente, resolvê-lo e definir sua classificação e determinação. Você também pode atribuir o incidente a si mesmo e adicionar marcas e comentários.

Em casos em que, durante uma investigação, você deseje migrar os alertas de um incidente para outro, você também pode fazer isso na guia Alertas, criando, assim, um incidente maior ou menor que inclua todos os alertas relevantes.

## <a name="edit-incident-name"></a>Editar o nome do incidente
Os incidentes são atribuídos automaticamente a um nome com base em atributos de alerta, como o número de pontos de extremidade afetados, usuários afetados, fontes de detecção ou categorias. Isso permite que você entenda rapidamente o escopo do incidente.

Por exemplo: *incidente em vários estágios em vários pontos de extremidade relatados por várias fontes.*

Você pode modificar o nome do incidente para um melhor alinhamento à sua convenção de nomenclatura preferencial.

> [!NOTE]
> Incidentes que existiam antes da adoção do recurso de nomenização automática de incidentes manterão seu nome.



## <a name="assign-incidents"></a>Atribuir incidentes
Caso um incidente ainda não tenha sido atribuído, você poderá selecionar **Atribuir a mim** para atribuir o incidente a si mesmo. Ao fazer isso, você assume a propriedade não apenas do incidente, como também de todos os alertas associados a ele.

## <a name="set-status-and-classification"></a>Definir o status e a classificação
### <a name="incident-status"></a>Status do incidente
Você pode categorizar os incidentes (como **Ativo** ou **Resolvido**) alterando o status deles durante sua investigação. Isso ajuda você a organizar e a gerenciar a maneira como sua equipe é capaz de responder a incidentes.

Por exemplo, seu analista de SOC pode analisar os incidentes **Ativos** urgentes do dia e decidir atribuí-los a si mesmo para investigação.

Como alternativa, seu analista de SOC pode definir o incidente como **Resolvido** caso ele já tenha sido solucionado. Ao resolver um incidente, todos os alertas que fazem parte do incidente e que ainda estão abertos serão fechados automaticamente. 

### <a name="classification-and-determination"></a>Classificação e determinação
Você pode optar por não definir uma classificação ou decidir especificar se um incidente é verdadeiro ou falso. Isso ajuda a equipe a ver padrões e a aprender com eles. 

## <a name="add-comments"></a>Adicionar comentários
Você pode adicionar comentários e exibir eventos históricos sobre um incidente para ver as alterações feitas anteriormente.

Sempre que uma alteração ou um comentário forem feitos em um alerta, eles são registrados na seção Comentários e histórico.

Os comentários adicionados aparecem instantaneamente no painel.

## <a name="add-incident-tags"></a>Adicionar marcas de incidente
Você pode adicionar marcas personalizadas a um incidente, por exemplo, para sinalizar um grupo de incidentes com características semelhantes. Posteriormente, você pode filtrar a fila incidentes, buscando todos os incidentes que contenham uma marca específica.
