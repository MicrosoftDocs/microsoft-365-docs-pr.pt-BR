---
title: Sinalizadores de eventos de linha do tempo do dispositivo do Microsoft Defender for Endpoint
description: Usar os sinalizadores de eventos de linha do tempo do dispositivo do Microsoft Defender para Endpoint para
keywords: Linha do tempo do dispositivo Defender para Ponto de Extremidade, sinalizadores de eventos
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a34efc171d3bb3aa1fcf33e0f56700149885ac2e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165148"
---
# <a name="microsoft-defender-for-endpoint-device-timeline-event-flags"></a>Sinalizadores de eventos de linha do tempo do dispositivo do Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Sinalizadores de evento na linha do tempo do dispositivo Defender para Ponto de Extremidade ajudam você a filtrar e organizar eventos específicos quando você está investigando possíveis ataques.

A linha do tempo do dispositivo Defender para Ponto de Extremidade fornece uma exibição cronológica dos eventos e alertas associados observados em um dispositivo. Esta lista de eventos fornece visibilidade total sobre quaisquer eventos, arquivos e endereços IP observados no dispositivo. Às vezes, a lista pode ser longa. Os sinalizadores de eventos da linha do tempo do dispositivo ajudam você a rastrear eventos que podem estar relacionados. 

Depois de passar por uma linha do tempo do dispositivo, você pode classificar, filtrar e exportar os eventos específicos sinalizados.

Ao navegar pela linha do tempo do dispositivo, você pode pesquisar e filtrar eventos específicos. Você pode definir sinalizadores de evento por: 

- Realçando os eventos mais importantes 
- Marcando eventos que exigem imersão profunda 
- Criando uma linha do tempo de violação limpa



## <a name="flag-an-event"></a>Sinalizar um evento
1. Encontre o evento que você deseja sinalizar
2. Clique no ícone de sinalizador na coluna Sinalizador. 
![Imagem do sinalizador de linha do tempo do dispositivo](images/device-flags.png)

## <a name="view-flagged-events"></a>Exibir eventos sinalizados  
1. Na seção **Filtros da Linha do Tempo,** habilita **eventos sinalizados**.
2. Clique em **Aplicar**. Somente eventos sinalizados são exibidos.
Você pode aplicar filtros adicionais clicando na barra de tempo. Isso só mostrará eventos antes do evento sinalizado.  
![Imagem do sinalizador de linha do tempo do dispositivo com filtro em](images/device-flag-filter.png)
