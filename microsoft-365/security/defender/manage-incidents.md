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
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 2d2bf18c6cacb377e710f34b74ec8f83bb77d3b1
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760057"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>Gerenciar incidentes no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

O gerenciamento de incidentes é fundamental para garantir que as ameaças sejam contidas e abordadas.

Você gerencia incidentes de **incidentes & alertas** > incidentes no início rápido do centro de segurança do Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)). Veja um exemplo.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Exemplo da fila de incidentes":::

Aqui estão as maneiras de gerenciar seus incidentes:

- Alterar o nome do incidente
- Adicione marcas de incidente.
- Atribuir o incidente a uma conta de usuário
- Resolvê-los 
- Definir sua classificação e determinação
- Adicione comentários.

Você pode gerenciar incidentes do **painel Gerenciar incidentes** para um incidente. Veja um exemplo.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Exemplo do painel Gerenciar incidentes de um incidente":::

Você pode exibir esse painel no link **Gerenciar incidentes** no:

- Painel de propriedades de um incidente na fila de incidentes.
- **Página** de resumo de um incidente.

Em casos em que, ao investigar, você gostaria de mover alertas de um incidente para outro, você também pode fazer isso da guia **Alertas,** criando um incidente maior ou menor que inclui todos os alertas relevantes.

## <a name="edit-the-incident-name"></a>Editar o nome do incidente

Os incidentes são atribuídos automaticamente a um nome com base em atributos de alerta, como o número de pontos de extremidade afetados, usuários afetados, fontes de detecção ou categorias. Isso permite que você entenda rapidamente o escopo do incidente. Por exemplo: *incidente em vários estágios em vários pontos de extremidade relatados por várias fontes.*

Você pode editar o nome do incidente no campo **Nome do** incidente no **painel Gerenciar** incidentes.

> [!NOTE]
> Incidentes que existiam antes da adoção do recurso de nomenização automática de incidentes manterão seu nome.

## <a name="add-incident-tags"></a>Adicionar marcas de incidente

Você pode adicionar marcas personalizadas a um incidente, por exemplo, para sinalizar um grupo de incidentes com uma característica comum. Posteriormente, você pode filtrar a fila de incidentes para todos os incidentes que contenham uma marca específica.

Ao começar a digitar, você tem a opção de selecionar em uma lista de marcas selecionadas.

## <a name="assign-incidents"></a>Atribuir incidentes

Se um incidente ainda não tiver sido atribuído, você poderá selecionar **Atribuir e** especificar a conta de usuário. Isso atribui a propriedade do incidente e todos os alertas associados a ele.

## <a name="resolve-incident"></a>Resolver incidente

Se o incidente tiver sido resolvido, selecione **Resolver incidentes** para mover a alternância para a direita. Observe que a resolução de um incidente também resolve todos os alertas vinculados e ativos relacionados ao incidente.

Um incidente que não é resolvido é exibido como **Ativo**.

## <a name="set-the-classification-and-determination"></a>Definir a classificação e a determinação

A classificação de incidentes é se foi um alerta verdadeiro ou falso, que você configura no **campo Classificação.** 

Se foi um alerta verdadeiro, você também deve especificar que tipo de ameaça era com o campo **Determinação.** Especificar o tipo de ameaça ajuda sua equipe de segurança a ver padrões de ameaças e agir para defender sua organização deles. 

## <a name="add-comments"></a>Adicionar comentários

Você pode adicionar vários comentários a um incidente com o **campo Comentário.** Cada comentário é adicionado aos eventos históricos do incidente. Você pode ver os comentários e o histórico de um incidente no link **Comentários e** histórico na página **Resumo.**
