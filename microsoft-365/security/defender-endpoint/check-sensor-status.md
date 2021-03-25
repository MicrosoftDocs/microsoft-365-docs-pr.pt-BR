---
title: Verificar o estado de saúde do sensor no Microsoft Defender ATP
description: Verifique a saúde do sensor em dispositivos para identificar quais estão configurados de forma mal configurada, inativas ou não estão relatando dados do sensor.
keywords: sensor, a saúde do sensor, configurada inativa, sem dados do sensor, dados do sensor, comunicações prejudicadas, comunicação
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 21313463519383f4bf052465a0d907d2df293ec8
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165268"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a>Verificar o estado de saúde do sensor no Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-checksensor-abovefoldlink)

O **painel Dispositivos com problemas** de sensor é encontrado no painel Operações de Segurança. Esse tile fornece informações sobre a capacidade do dispositivo individual de fornecer dados do sensor e se comunicar com o serviço Defender para Ponto de Extremidade. Ele relata quantos dispositivos exigem atenção e ajuda você a identificar dispositivos problemáticos e a tomar medidas para corrigir problemas conhecidos.

Há dois indicadores de status no azulejo que fornecem informações sobre o número de dispositivos que não estão relatando corretamente para o serviço:
- **Configuração incorretamente** - Esses dispositivos podem estar relatando parcialmente dados do sensor para o serviço Defender para Ponto de Extremidade e podem ter erros de configuração que precisam ser corrigidos.
- **Inativos** - Dispositivos que pararam de relatar para o serviço Defender para Ponto de Extremidade por mais de sete dias no mês passado.

Clicar em qualquer um dos grupos direciona você para a lista **Dispositivos**, filtrada de acordo com sua escolha.

![Screenshot of Devices with sensor issues tile](images/atp-devices-with-sensor-issues-tile.png)

Na **lista Dispositivos,** você pode filtrar a lista de estado de saúde pelo seguinte status:
- **Ativo** - Dispositivos que estão relatando ativamente para o serviço Defender para Ponto de Extremidade.
- **Configuração incorretamente** - Esses dispositivos podem estar relatando parcialmente dados do sensor para o serviço Defender para Ponto de Extremidade, mas têm erros de configuração que precisam ser corrigidos. Dispositivos mal configurados podem ter um ou uma combinação dos seguintes problemas:
  - **Sem dados do sensor** - Os dispositivos pararam de enviar dados do sensor. Alertas limitados podem ser disparados do dispositivo.
  - **Comunicações prejudicadas** - A capacidade de se comunicar com o dispositivo está prejudicada. O envio de arquivos para análise profunda, bloqueio de arquivos, isolamento do dispositivo da rede e outras ações que exigem comunicação com o dispositivo pode não funcionar.
- **Inativo -** Dispositivos que pararam de relatar para o serviço Defender para Ponto de Extremidade.

Você também pode baixar a lista inteira no formato CSV usando o **recurso Exportar.** Para obter mais informações sobre filtros, [consulte Exibir e organizar a lista Dispositivos](machines-view-overview.md).

>[!NOTE]
>Exporte a lista no formato CSV para exibir os dados não filtrados. O arquivo CSV incluirá todos os dispositivos na organização, independentemente de qualquer filtragem aplicada no próprio exibição e pode levar um tempo significativo para ser baixado, dependendo do tamanho da sua organização.

![Captura de tela da página de lista Dispositivos](images/atp-devices-list-page.png)

Você pode exibir os detalhes do dispositivo quando clicar em um dispositivo mal configurado ou inativo.

## <a name="related-topic"></a>Tópicos relacionados
- [Corrigir sensores não salubres no Defender para Ponto de Extremidade](fix-unhealthy-sensors.md)
