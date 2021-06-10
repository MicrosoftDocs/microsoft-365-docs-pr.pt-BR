---
title: Usar rótulos de confidencialidade para priorizar a resposta a incidentes
description: Saiba como usar rótulos de sensibilidade para priorizar e investigar incidentes
keywords: informações, proteção, dados, perda, prevenção,rótulos, dlp, incidente, investigação, investigação
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: bff490edcc79bc8f96e65c8b27586ca8b54e5bce
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186120"
---
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a>Usar rótulos de confidencialidade para priorizar a resposta a incidentes  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


Um típico ciclo de vida de ameaças persistentes avançada envolve a exfiltração de dados. Em um incidente de segurança, é importante ter a capacidade de priorizar investigações em que arquivos confidenciais podem ser comprometidos para que dados corporativos e informações sejam protegidos.

O Defender for Endpoint ajuda a simplificar a priorização de incidentes de segurança com o uso de rótulos de sensibilidade. Os rótulos de confidencialidade identificam rapidamente incidentes que podem envolver dispositivos com informações confidenciais, como informações confidenciais. 

## <a name="investigate-incidents-that-involve-sensitive-data"></a>Investigar incidentes que envolvem dados confidenciais
Saiba como usar rótulos de sensibilidade de dados para priorizar a investigação de incidentes.

>[!NOTE]
>Os rótulos são detectados Windows 10 versão 1809 ou posterior.

1. Em Central de Segurança do Microsoft Defender, selecione **Incidentes**. 

2. Role para a direita para ver a **coluna De sensibilidade de** dados. Esta coluna reflete rótulos de sensibilidade que foram observados em dispositivos relacionados aos incidentes, fornecendo uma indicação de se arquivos confidenciais podem ser afetados pelo incidente.

    ![Imagem da coluna de sensibilidade de dados](images/data-sensitivity-column.png)

    Você também pode filtrar com base na **sensibilidade de dados** 

    ![Imagem do filtro de sensibilidade de dados](images/data-sensitivity-filter.png)

3. Abra a página de incidentes para investigar mais.

    ![Imagem dos detalhes da página de incidentes](images/incident-page.png)

4. Selecione a **guia Dispositivos** para identificar dispositivos que armazenaram arquivos com rótulos de sensibilidade.

    ![Imagem da guia dispositivo](images/investigate-devices-tab.png)
   

5. Selecione os dispositivos que armazenam dados confidenciais e pesquise pela linha do tempo para identificar quais arquivos podem ser afetados e, em seguida, tome as medidas apropriadas para garantir que os dados sejam protegidos. 

   Você pode restringir os eventos mostrados na linha do tempo do dispositivo pesquisando rótulos de sensibilidade de dados. Isso mostrará apenas eventos associados a arquivos que tenham dito o nome do rótulo.

    ![Imagem da linha do tempo do dispositivo com resultados de pesquisa limitados com base no rótulo](images/machine-timeline-labels.png)


>[!TIP]
>Esses pontos de dados também são expostos por meio dos 'DeviceFileEvents' na busca avançada, permitindo que consultas avançadas e detecção de agendamento leve em consideração rótulos de confidencialidade e status de proteção de arquivo. 
