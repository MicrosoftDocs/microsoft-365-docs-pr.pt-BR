---
title: Gerenciar incidentes no Microsoft 365 Defender
description: Saiba como atribuir, atualizar o status,
keywords: incidentes, incidentes, análise, resposta, alertas, alertas correlacionados, atribuir, atualizar, status, gerenciar, classificação, microsoft, 365, m365
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
ms.openlocfilehash: 9cb3cc67c3992773897ea8178f261d25dcd87da0
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594140"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>Gerenciar incidentes no Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

O gerenciamento de incidentes é fundamental para garantir que as ameaças sejam contidas e abordadas.

Você gerencia incidentes de **incidentes & alertas** > Incidentes no início rápido do centro de segurança do Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)). Veja um exemplo.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Exemplo da fila de incidentes":::

Aqui estão as maneiras de gerenciar seus incidentes:

- [Editar o nome do incidente](#edit-the-incident-name)
- [Adicionar marcas de incidente](#add-incident-tags)
- [Atribuir o incidente a si mesmo](#assign-incidents)
- [Resolvê-los](#resolve-an-incident)
- [Definir sua classificação e determinação](#set-the-classification-and-determination)
- [Adicionar comentários](#add-comments)

Você pode gerenciar incidentes do **painel Gerenciar incidentes** para um incidente. Veja um exemplo.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="Exemplo do painel Gerenciar incidentes de um incidente":::

Você pode exibir esse painel no link **Gerenciar incidentes** no:

- Painel de propriedades de um incidente na fila de incidentes.
- **Página** de resumo de um incidente.

Nos casos em que você deseja mover alertas de um incidente para outro, você também pode fazê-lo a partir da guia **Alertas,** criando um incidente maior ou menor que inclui todos os alertas relevantes.

## <a name="edit-the-incident-name"></a>Editar o nome do incidente

Microsoft 365 O Defender atribui automaticamente um nome com base em atributos de alerta, como o número de pontos de extremidade afetados, usuários afetados, fontes de detecção ou categorias. Isso permite que você entenda rapidamente o escopo do incidente. Por exemplo: *incidente em vários estágios em vários pontos de extremidade relatados por várias fontes.*

Você pode editar o nome do incidente no campo **Nome do** incidente no **painel Gerenciar** incidentes.

> [!NOTE]
> Incidentes que existiam antes da adoção do recurso de nomenização automática de incidentes manterão seu nome.

## <a name="add-incident-tags"></a>Adicionar marcas de incidente

Você pode adicionar marcas personalizadas a um incidente, por exemplo, para sinalizar um grupo de incidentes com uma característica comum. Posteriormente, você pode filtrar a fila de incidentes para todos os incidentes que contenham uma marca específica.

Ao começar a digitar, você tem a opção de selecionar em uma lista de marcas selecionadas.

## <a name="assign-incidents"></a>Atribuir incidentes

Para atribuir um incidente, selecione **Atribuir a mim**. Isso atribui a propriedade do incidente e todos os alertas associados a ele à sua conta de usuário.

Você pode obter uma lista de incidentes atribuídos a você filtrando a fila de incidentes. 

1. Na fila de incidentes, selecione **Filtros**.
2. na seção **Atribuição de incidentes,** **desin selecione Selecionar tudo** e selecione Atribuído a **mim**.
3. Selecione **Aplicar** e feche o painel **Filtros.**

Em seguida, você pode salvar a URL resultante em seu navegador como um indicador para ver rapidamente a lista de incidentes atribuídos a você.

## <a name="resolve-an-incident"></a>Resolver um incidente

Se o incidente tiver sido resolvido, selecione **Resolver incidentes** para mover a alternância para a direita. Observe que a resolução de um incidente também resolve todos os alertas vinculados e ativos relacionados ao incidente.

Um incidente que não é resolvido é exibido como **Ativo**.

## <a name="set-the-classification-and-determination"></a>Definir a classificação e a determinação

A classificação de incidentes é se foi um alerta verdadeiro ou falso, que você configura no **campo Classificação.** 

Se foi um alerta verdadeiro, você também deve especificar que tipo de ameaça era com o campo **Determinação.** Especificar o tipo de ameaça ajuda sua equipe de segurança a ver padrões de ameaças e agir para defender sua organização deles. 

## <a name="add-comments"></a>Adicionar comentários

Você pode adicionar vários comentários a um incidente com o **campo Comentário.** Cada comentário é adicionado aos eventos históricos do incidente. Você pode ver os comentários e o histórico de um incidente no link **Comentários e** histórico na página **Resumo.**

## <a name="next-steps"></a>Próximas etapas

Para novos incidentes, inicie sua [investigação.](investigate-incidents.md)

Para incidentes no processo, continue sua [investigação.](investigate-incidents.md)

Para incidentes resolvidos, execute uma [revisão pós-incidente.](first-incident-post.md)

## <a name="see-also"></a>Confira também

- [Visão geral dos incidentes](incidents-overview.md)
- [Priorizar incidentes](incident-queue.md)
- [Investigar incidentes](investigate-incidents.md)
