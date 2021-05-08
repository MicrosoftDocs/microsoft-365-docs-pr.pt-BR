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
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a>Relatório de dispositivos vulneráveis - Gerenciamento de Ameaças e Vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Ameaça e Gerenciamento de Vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

O relatório mostra gráficos e gráficos de barras com tendências de dispositivos vulneráveis e estatísticas atuais. O objetivo é que você entenda o hálito e o escopo da exposição do dispositivo.

Acesse o relatório na Central de Segurança do Microsoft Defender acessando **Relatórios > dispositivos vulneráveis**

Há duas colunas:

- Tendências (com o tempo). Pode mostrar os últimos 30 dias, 3 meses, 6 meses ou um intervalo de datas personalizado.
- Hoje (informações atuais)

**Filtro**: Você pode filtrar os dados por níveis de gravidade de vulnerabilidade, disponibilidade de exploração, idade da vulnerabilidade, plataforma do sistema operacional, Windows 10 versão ou grupo de dispositivos.

**Detalhar**: se houver uma visão que você deseja explorar mais, selecione o gráfico de barras relevante para exibir uma lista filtrada de dispositivos na página Inventário de dispositivos. A partir daí, você pode exportar a lista.

## <a name="severity-level-graphs"></a>Gráficos de nível de gravidade

Cada dispositivo é contado apenas uma vez de acordo com a vulnerabilidade mais grave encontrada nesse dispositivo.

![Um gráfico dos níveis de gravidade da vulnerabilidade do dispositivo atual e um gráfico mostrando níveis ao longo do tempo.](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a>Explorar gráficos de disponibilidade

Cada dispositivo é contado apenas uma vez com base no nível mais alto de exploração conhecida.

![Um gráfico da disponibilidade de exploração de dispositivo atual e um gráfico mostrando disponibilidade ao longo do tempo.](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a>Gráficos de idade de vulnerabilidade

Cada dispositivo é contado apenas uma vez na data de publicação de vulnerabilidade mais antiga. As vulnerabilidades mais antigas têm mais chances de serem exploradas.

![Um gráfico da idade atual da vulnerabilidade do dispositivo e um gráfico mostrando a idade ao longo do tempo.](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a>Dispositivos vulneráveis por gráficos de plataforma do sistema operacional

O número de dispositivos em cada sistema operacional que são expostos devido a vulnerabilidades de software.

![Um gráfico de dispositivos vulneráveis atuais pela plataforma do sistema operacional e um gráfico mostrando dispositivos vulneráveis por plataformas do sistema operacional ao longo do tempo.](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a>Dispositivos vulneráveis Windows 10 gráficos de versão

O número de dispositivos em cada Windows 10 que são expostos devido a aplicativos ou sistema operacional vulneráveis.

![Um gráfico de dispositivos vulneráveis Windows 10 versão atual e um gráfico mostrando dispositivos vulneráveis por Windows 10 versão ao longo do tempo.](images/tvm-report-version.png)

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral Gerenciamento de Vulnerabilidades ameaça](next-gen-threat-and-vuln-mgt.md)
- [Recomendações de segurança](tvm-security-recommendation.md)
