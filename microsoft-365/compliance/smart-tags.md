---
title: Configurar marcas inteligentes em Advanced eDiscovery
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
description: As marcas inteligentes permitem que você aplique os recursos de aprendizado de máquina ao analisar o conteúdo em um Advanced eDiscovery caso. Use grupos de marca inteligente para exibir os resultados de modelos de detecção de aprendizado de máquina, como o modelo de privilégio advogado-cliente.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42081078"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a>Configurar marcas inteligentes em Advanced eDiscovery

Os recursos de aprendizado de máquina (ML) no Advanced eDiscovery podem ajudá-lo a tornar o processo de decisão mais eficiente ao analisar documentos de caso em um conjunto de revisão. As marcas inteligentes são uma maneira de trazer os recursos ML para onde as decisões são registradas: ao marcar documentos durante a revisão. Quando você cria um grupo de marcas inteligentes, as decisões que são o resultado do modelo ML que você associou ao grupo de marcas inteligentes são exibidas em linha com as marcas no grupo de marcas. Isso ajuda a ver ML informações de resultados em linha quando você está revendo documentos específicos.

## <a name="how-to-set-up-a-smart-tag-group"></a>Como configurar um grupo de marca inteligente

1. Em um conjunto de revisão, clique em **Gerenciar conjunto de revisão** e clique em Gerenciar **marcas**.

2. Clique **em Adicionar grupo de marca** e selecione Adicionar grupo de marca **inteligente**.

3. Selecione o ML modelo que você deseja associar ao grupo de marca.
    
   Isso cria um grupo de marcas e *marcas filho N,* *onde N* é o número de possíveis saídas do modelo. Por exemplo, o modelo de detecção de [privilégio advogado-cliente](attorney-privilege-detection.md) tem duas saídas possíveis: 

   - **Positivo** – Use para marcar documentos que contenham conteúdo privilegiado de cliente-advogado.
   
   - **Negativo** – Use para marcar documentos que não contenham conteúdo privilegiado advogado-cliente.
    
    Se você selecionar esse modelo, um grupo de marcas com duas marcas filho será criado (uma marca filha chamada **Positive** e a outra denominada **Negative**) para o conjunto de revisão. Neste exemplo, cada marca filho corresponde a uma das possíveis saídas do modelo de detecção de privilégio advogado-cliente.

4. Opcionalmente, você pode renomear o grupo de marcas e as marcas filho. Por exemplo, você pode renomear **a marca Positiva** como **Privileged** e a marca **Negativa** como **Não privilegiado**.

## <a name="how-to-use-smart-tags"></a>Como usar marcas inteligentes

Ao revisar um documento, os resultados do modelo são exibidos ao lado da marca filha apropriada. Por exemplo, se você tiver um grupo de marca inteligente para detecção de privilégio advogado-cliente e revisar um documento potencialmente privilegiado, o motivo dessa conclusão será exibido ao lado da marca apropriada. É importante observar que a marca não é aplicada automaticamente ao documento. O revistor toma a decisão sobre como marcar o documento.
