---
title: Configurar marcas inteligentes na descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
ROBOTS: NOINDEX, NOFOLLOW
description: As marcas inteligentes permitem que você aplique os recursos de aprendizado da máquina ao revisar o conteúdo em uma ocorrência de descoberta eletrônica avançada. Use grupos de marcas inteligentes para exibir os resultados dos modelos de detecção de aprendizagem de máquina, como o modelo de privilégio de cliente advogado.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081078"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a>Configurar marcas inteligentes na descoberta eletrônica avançada

Os recursos do Machine Learning (ML) na descoberta eletrônica avançada podem ajudá-lo a tornar o processo de decisão mais eficiente ao revisar os documentos de caso em um conjunto de revisão. As marcas inteligentes são uma maneira de trazer os recursos de ML para onde as decisões são registradas: ao marcar documentos durante a revisão. Quando você cria um grupo de marcas inteligentes, as decisões que são o resultado do modelo ML que você associou ao grupo de marcas inteligentes são exibidas em linha com as marcas no grupo de marcas. Isso ajuda a ver as informações de resultados de ML em linha quando você está examinando documentos específicos.

## <a name="how-to-set-up-a-smart-tag-group"></a>Como configurar um grupo de marcas inteligentes

1. Em um conjunto de revisão, clique em **gerenciar análise definida** e, em seguida, clique em **gerenciar marcas**.

2. Clique em **Adicionar grupo de marcas** e selecione **Adicionar grupo de marcas inteligentes**.

3. Selecione o modelo ML que você deseja associar ao grupo de marcas.
    
   Isso cria um grupo de marcas e *n* marcas filhas, onde *N* é o número de saídas possíveis do modelo. Por exemplo, o [modelo de detecção de privilégio de cliente advogado](attorney-privilege-detection.md) tem duas saídas possíveis: 

   - **Positivo** – use para marcar documentos que contenham conteúdo privilegiado pelo cliente advogado.
   
   - **Negativo** – use para marcar documentos que não contenham conteúdo privilegiado pelo cliente advogado.
    
    Se você selecionar este modelo, um grupo de marcas com duas marcas filhas será criado (uma marca filha denominada **positiva** e a outra chamada **negativa**) para o conjunto de revisão. Neste exemplo, cada marca filha corresponde a uma das possíveis saídas do modelo de detecção de privilégio de cliente advogado.

4. Opcionalmente, você pode renomear o grupo de marcas e as marcas filhas. Por exemplo, você pode renomear a marca **positiva** como **privilegiada** e a marca **negativa** como **não privilegiada**.

## <a name="how-to-use-smart-tags"></a>Como usar marcas inteligentes

Ao revisar um documento, os resultados do modelo são exibidos ao lado da marca filha apropriada. Por exemplo, se você tiver um grupo de marcas inteligentes para detecção de privilégio de cliente de advogado e revisar um documento que é potencialmente privilegiado, o motivo para essa conclusão será exibido ao lado da marca apropriada. É importante observar que a marca não é automaticamente aplicada ao documento. O revisor toma a decisão de como marcar o documento.
