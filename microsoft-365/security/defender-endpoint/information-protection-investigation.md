---
title: Usar rótulos de sensibilidade para priorizar a resposta a incidentes
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
# <a name="use-sensitivity-labels-to-prioritize-incident-response"></a><span data-ttu-id="b9f41-104">Usar rótulos de sensibilidade para priorizar a resposta a incidentes</span><span class="sxs-lookup"><span data-stu-id="b9f41-104">Use sensitivity labels to prioritize incident response</span></span>  

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b9f41-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b9f41-105">**Applies to:**</span></span>
- [<span data-ttu-id="b9f41-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="b9f41-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b9f41-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9f41-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b9f41-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="b9f41-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b9f41-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="b9f41-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="b9f41-110">Um típico ciclo de vida de ameaças persistentes avançada envolve a exfiltração de dados.</span><span class="sxs-lookup"><span data-stu-id="b9f41-110">A typical advanced persistent threat lifecycle involves data exfiltration.</span></span> <span data-ttu-id="b9f41-111">Em um incidente de segurança, é importante ter a capacidade de priorizar investigações em que arquivos confidenciais podem ser comprometidos para que dados corporativos e informações sejam protegidos.</span><span class="sxs-lookup"><span data-stu-id="b9f41-111">In a security incident, it's important to have the ability to prioritize investigations where sensitive files may be jeopardy so that corporate data and information are protected.</span></span>

<span data-ttu-id="b9f41-112">O Defender for Endpoint ajuda a simplificar a priorização de incidentes de segurança com o uso de rótulos de sensibilidade.</span><span class="sxs-lookup"><span data-stu-id="b9f41-112">Defender for Endpoint helps to make the prioritization of security incidents much simpler with the use of sensitivity labels.</span></span> <span data-ttu-id="b9f41-113">Os rótulos de confidencialidade identificam rapidamente incidentes que podem envolver dispositivos com informações confidenciais, como informações confidenciais.</span><span class="sxs-lookup"><span data-stu-id="b9f41-113">Sensitivity labels quickly identify incidents that may involve devices with sensitive information such as confidential information.</span></span> 

## <a name="investigate-incidents-that-involve-sensitive-data"></a><span data-ttu-id="b9f41-114">Investigar incidentes que envolvem dados confidenciais</span><span class="sxs-lookup"><span data-stu-id="b9f41-114">Investigate incidents that involve sensitive data</span></span>
<span data-ttu-id="b9f41-115">Saiba como usar rótulos de sensibilidade de dados para priorizar a investigação de incidentes.</span><span class="sxs-lookup"><span data-stu-id="b9f41-115">Learn how to use data sensitivity labels to prioritize incident investigation.</span></span>

>[!NOTE]
><span data-ttu-id="b9f41-116">Os rótulos são detectados para o Windows 10, versão 1809 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="b9f41-116">Labels are detected for Windows 10, version 1809 or later.</span></span>

1. <span data-ttu-id="b9f41-117">No Centro de Segurança do Microsoft Defender, selecione **Incidentes**.</span><span class="sxs-lookup"><span data-stu-id="b9f41-117">In Microsoft Defender Security Center, select **Incidents**.</span></span> 

2. <span data-ttu-id="b9f41-118">Role para a direita para ver a **coluna De sensibilidade de** dados.</span><span class="sxs-lookup"><span data-stu-id="b9f41-118">Scroll to the right to see the **Data sensitivity** column.</span></span> <span data-ttu-id="b9f41-119">Esta coluna reflete rótulos de sensibilidade que foram observados em dispositivos relacionados aos incidentes, fornecendo uma indicação de se arquivos confidenciais podem ser afetados pelo incidente.</span><span class="sxs-lookup"><span data-stu-id="b9f41-119">This column reflects sensitivity labels that have been observed on devices related to the incidents providing an indication of whether sensitive files may be impacted by the incident.</span></span>

    ![Imagem da coluna de sensibilidade de dados](images/data-sensitivity-column.png)

    <span data-ttu-id="b9f41-121">Você também pode filtrar com base na **sensibilidade de dados**</span><span class="sxs-lookup"><span data-stu-id="b9f41-121">You can also filter based on **Data sensitivity**</span></span> 

    ![Imagem do filtro de sensibilidade de dados](images/data-sensitivity-filter.png)

3. <span data-ttu-id="b9f41-123">Abra a página de incidentes para investigar mais.</span><span class="sxs-lookup"><span data-stu-id="b9f41-123">Open the incident page to further investigate.</span></span>

    ![Imagem dos detalhes da página de incidentes](images/incident-page.png)

4. <span data-ttu-id="b9f41-125">Selecione a **guia Dispositivos** para identificar dispositivos que armazenaram arquivos com rótulos de sensibilidade.</span><span class="sxs-lookup"><span data-stu-id="b9f41-125">Select the **Devices** tab to identify devices storing files with sensitivity labels.</span></span>

    ![Imagem da guia dispositivo](images/investigate-devices-tab.png)
   

5. <span data-ttu-id="b9f41-127">Selecione os dispositivos que armazenam dados confidenciais e pesquise pela linha do tempo para identificar quais arquivos podem ser afetados e, em seguida, tome as medidas apropriadas para garantir que os dados sejam protegidos.</span><span class="sxs-lookup"><span data-stu-id="b9f41-127">Select the devices that store sensitive data and search through the timeline to identify which files may be impacted then take appropriate action to ensure that data is protected.</span></span> 

   <span data-ttu-id="b9f41-128">Você pode restringir os eventos mostrados na linha do tempo do dispositivo pesquisando rótulos de sensibilidade de dados.</span><span class="sxs-lookup"><span data-stu-id="b9f41-128">You can narrow down the events shown on the device timeline by searching for data sensitivity labels.</span></span> <span data-ttu-id="b9f41-129">Isso mostrará apenas eventos associados a arquivos que tenham dito o nome do rótulo.</span><span class="sxs-lookup"><span data-stu-id="b9f41-129">Doing this will show only events associated with files that have said label name.</span></span>

    ![Imagem da linha do tempo do dispositivo com resultados de pesquisa limitados com base no rótulo](images/machine-timeline-labels.png)


>[!TIP]
><span data-ttu-id="b9f41-131">Esses pontos de dados também são expostos por meio dos 'DeviceFileEvents' na busca avançada, permitindo que consultas avançadas e detecção de agendamento leve em consideração rótulos de confidencialidade e status de proteção de arquivo.</span><span class="sxs-lookup"><span data-stu-id="b9f41-131">These data points are also exposed through the ‘DeviceFileEvents’ in advanced hunting, allowing advanced queries and schedule detection to take into account sensitivity labels and file protection status.</span></span> 
