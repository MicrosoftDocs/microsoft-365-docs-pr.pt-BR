---
title: Relatório de dispositivos vulneráveis - Gerenciamento de Ameaças e Vulnerabilidades
description: Um relatório mostrando tendências de dispositivos vulneráveis e estatísticas atuais. O objetivo é que você entenda o hálito e o escopo da exposição do dispositivo.
keywords: Microsoft Defender para dispositivos vulneráveis do Endpoint-tvm, Microsoft Defender para Ponto de Extremidade, tvm, reduzir a exposição de vulnerabilidades & ameaças, reduzir a ameaça e a vulnerabilidade, monitorar a configuração de segurança
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 355561936642b1fa38228bfa07ad59269c48d817
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245475"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a><span data-ttu-id="02ddc-105">Relatório de dispositivos vulneráveis - Gerenciamento de Ameaças e Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="02ddc-105">Vulnerable devices report - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="02ddc-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="02ddc-106">**Applies to:**</span></span>

- [<span data-ttu-id="02ddc-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="02ddc-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="02ddc-108">Ameaça e Gerenciamento de Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="02ddc-108">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="02ddc-109">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="02ddc-109">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="02ddc-110">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="02ddc-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="02ddc-111">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="02ddc-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="02ddc-112">O relatório mostra gráficos e gráficos de barras com tendências de dispositivos vulneráveis e estatísticas atuais.</span><span class="sxs-lookup"><span data-stu-id="02ddc-112">The report shows graphs and bar charts with vulnerable device trends and current statistics.</span></span> <span data-ttu-id="02ddc-113">O objetivo é que você entenda o hálito e o escopo da exposição do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="02ddc-113">The goal is for you to understand the breath and scope of your device exposure.</span></span>

<span data-ttu-id="02ddc-114">Acesse o relatório na Central de Segurança do Microsoft Defender acessando **Relatórios > dispositivos vulneráveis**</span><span class="sxs-lookup"><span data-stu-id="02ddc-114">Access the report in the Microsoft Defender Security Center by going to **Reports > Vulnerable devices**</span></span>

<span data-ttu-id="02ddc-115">Há duas colunas:</span><span class="sxs-lookup"><span data-stu-id="02ddc-115">There are two columns:</span></span>

- <span data-ttu-id="02ddc-116">Tendências (com o tempo).</span><span class="sxs-lookup"><span data-stu-id="02ddc-116">Trends (over time).</span></span> <span data-ttu-id="02ddc-117">Pode mostrar os últimos 30 dias, 3 meses, 6 meses ou um intervalo de datas personalizado.</span><span class="sxs-lookup"><span data-stu-id="02ddc-117">Can show the past 30 days, 3 months, 6 months, or a custom date range.</span></span>
- <span data-ttu-id="02ddc-118">Hoje (informações atuais)</span><span class="sxs-lookup"><span data-stu-id="02ddc-118">Today (current information)</span></span>

<span data-ttu-id="02ddc-119">**Filtro**: Você pode filtrar os dados por níveis de gravidade de vulnerabilidade, disponibilidade de exploração, idade da vulnerabilidade, plataforma do sistema operacional, Windows 10 versão ou grupo de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="02ddc-119">**Filter**: You can filter the data by vulnerability severity levels, exploit availability, vulnerability age, operating system platform, Windows 10 version, or device group.</span></span>

<span data-ttu-id="02ddc-120">**Detalhar**: se houver uma visão que você deseja explorar mais, selecione o gráfico de barras relevante para exibir uma lista filtrada de dispositivos na página Inventário de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="02ddc-120">**Drill down**: If there is an insight you want to explore further, select the relevant bar chart to view a filtered list of devices in the Device inventory page.</span></span> <span data-ttu-id="02ddc-121">A partir daí, você pode exportar a lista.</span><span class="sxs-lookup"><span data-stu-id="02ddc-121">From there, you can export the list.</span></span>

## <a name="severity-level-graphs"></a><span data-ttu-id="02ddc-122">Gráficos de nível de gravidade</span><span class="sxs-lookup"><span data-stu-id="02ddc-122">Severity level graphs</span></span>

<span data-ttu-id="02ddc-123">Cada dispositivo é contado apenas uma vez de acordo com a vulnerabilidade mais grave encontrada nesse dispositivo.</span><span class="sxs-lookup"><span data-stu-id="02ddc-123">Each device is counted only once according to the most severe vulnerability found on that device.</span></span>

![Um gráfico dos níveis de gravidade da vulnerabilidade do dispositivo atual e um gráfico mostrando níveis ao longo do tempo.](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a><span data-ttu-id="02ddc-125">Explorar gráficos de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="02ddc-125">Exploit availability graphs</span></span>

<span data-ttu-id="02ddc-126">Cada dispositivo é contado apenas uma vez com base no nível mais alto de exploração conhecida.</span><span class="sxs-lookup"><span data-stu-id="02ddc-126">Each device is counted only once based on the highest level of known exploit.</span></span>

![Um gráfico da disponibilidade de exploração de dispositivo atual e um gráfico mostrando disponibilidade ao longo do tempo.](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a><span data-ttu-id="02ddc-128">Gráficos de idade de vulnerabilidade</span><span class="sxs-lookup"><span data-stu-id="02ddc-128">Vulnerability age graphs</span></span>

<span data-ttu-id="02ddc-129">Cada dispositivo é contado apenas uma vez na data de publicação de vulnerabilidade mais antiga.</span><span class="sxs-lookup"><span data-stu-id="02ddc-129">Each device is counted only once under the oldest vulnerability publication date.</span></span> <span data-ttu-id="02ddc-130">As vulnerabilidades mais antigas têm mais chances de serem exploradas.</span><span class="sxs-lookup"><span data-stu-id="02ddc-130">Older vulnerabilities have a higher chance of being exploited.</span></span>

![Um gráfico da idade atual da vulnerabilidade do dispositivo e um gráfico mostrando a idade ao longo do tempo.](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a><span data-ttu-id="02ddc-132">Dispositivos vulneráveis por gráficos de plataforma do sistema operacional</span><span class="sxs-lookup"><span data-stu-id="02ddc-132">Vulnerable devices by operating system platform graphs</span></span>

<span data-ttu-id="02ddc-133">O número de dispositivos em cada sistema operacional que são expostos devido a vulnerabilidades de software.</span><span class="sxs-lookup"><span data-stu-id="02ddc-133">The number of devices on each operating system that are exposed due to software vulnerabilities.</span></span>

![Um gráfico de dispositivos vulneráveis atuais pela plataforma do sistema operacional e um gráfico mostrando dispositivos vulneráveis por plataformas do sistema operacional ao longo do tempo.](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a><span data-ttu-id="02ddc-135">Dispositivos vulneráveis Windows 10 gráficos de versão</span><span class="sxs-lookup"><span data-stu-id="02ddc-135">Vulnerable devices by Windows 10 version graphs</span></span>

<span data-ttu-id="02ddc-136">O número de dispositivos em cada Windows 10 que são expostos devido a aplicativos ou sistema operacional vulneráveis.</span><span class="sxs-lookup"><span data-stu-id="02ddc-136">The number of devices on each Windows 10 version that are exposed due to vulnerable applications or OS.</span></span>

![Um gráfico de dispositivos vulneráveis Windows 10 versão atual e um gráfico mostrando dispositivos vulneráveis por Windows 10 versão ao longo do tempo.](images/tvm-report-version.png)

## <a name="related-topics"></a><span data-ttu-id="02ddc-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="02ddc-138">Related topics</span></span>

- [<span data-ttu-id="02ddc-139">Visão geral Gerenciamento de Vulnerabilidades ameaça</span><span class="sxs-lookup"><span data-stu-id="02ddc-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="02ddc-140">Recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="02ddc-140">Security recommendations</span></span>](tvm-security-recommendation.md)
