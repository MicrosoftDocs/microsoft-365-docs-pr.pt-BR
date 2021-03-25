---
title: Exibir e organizar a lista de dispositivos do Microsoft Defender ATP
description: Saiba mais sobre os recursos disponíveis que você pode usar na lista Dispositivos, como classificação, filtragem e exportação da lista para aprimorar as investigações.
keywords: sort, filter, export, csv, device name, domain, last seen, internal IP, health state, active alerts, active malware detections, threat category, review alerts, network, connection, malware, type, password stealer, ransomware, exploit, threat, general malware, unwanted software
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
ms.technology: mde
ms.openlocfilehash: 9068983b5f61305b1f3da4d076e99e71974e8df4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185666"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a>Exibir e organizar a lista do Microsoft Defender for Endpoint Devices

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


A **lista Dispositivos** mostra uma lista dos dispositivos em sua rede onde os alertas foram gerados. Por padrão, a fila exibe dispositivos vistos nos últimos 30 dias.  

Rapidamente, você verá informações como domínio, nível de risco, plataforma do sistema operacional e outros detalhes para facilitar a identificação dos dispositivos mais em risco.

Há várias opções que você pode escolher para personalizar a exibição de lista de dispositivos. Na navegação superior, você pode:

- Adicionar ou remover colunas
- Exportar a lista inteira no formato CSV
- Selecione o número de itens a mostrar por página
- Aplicar filtros

Durante o processo de integração, a lista **Dispositivos** é gradualmente preenchida com dispositivos à medida que eles começam a relatar dados do sensor. Use esse modo de exibição para acompanhar seus pontos de extremidade integrados conforme eles estão online ou baixar a lista de pontos de extremidade completa como um arquivo CSV para análise offline.

>[!NOTE]
> Se você exportar a lista de dispositivos, ela conterá todos os dispositivos em sua organização. Pode levar um tempo significativo para baixar, dependendo do tamanho da sua organização. Exportar a lista no formato CSV exibe os dados de forma não filtrada. O arquivo CSV incluirá todos os dispositivos na organização, independentemente de qualquer filtragem aplicada no próprio exibição.

![Imagem da lista de dispositivos com lista de dispositivos](images/device-list.png)

## <a name="sort-and-filter-the-device-list"></a>Classificar e filtrar a lista de dispositivos

Você pode aplicar os filtros a seguir para limitar a lista de alertas e obter uma exibição mais focada.

### <a name="risk-level"></a>Nível de risco

O nível de risco reflete a avaliação geral de risco do dispositivo com base em uma combinação de fatores, incluindo os tipos e a gravidade dos alertas ativos no dispositivo. Resolver alertas ativos, aprovar atividades de correção e suprimir alertas subsequentes pode diminuir o nível de risco.

### <a name="exposure-level"></a>Nível de exposição

O nível de exposição reflete a exposição atual do dispositivo com base no impacto acumulado de suas recomendações de segurança pendentes. Os níveis possíveis são baixos, médios e altos. Baixa exposição significa que seus dispositivos são menos vulneráveis de exploração.

Se o nível de exposição diz "Sem dados disponíveis", há alguns motivos pelos quais isso pode ser o caso:

- O dispositivo parou de relatar por mais de 30 dias – nesse caso, ele é considerado inativo e a exposição não é calculada
- Sistema operacional do dispositivo sem suporte - consulte [requisitos mínimos para o Microsoft Defender para Ponto de Extremidade](minimum-requirements.md)
- Dispositivo com agente estalado (muito improvável)

### <a name="os-platform"></a>Plataforma do sistema operacional

Selecione apenas as plataformas do sistema operacional que você está interessado em investigar.

### <a name="health-state"></a>Estado de integridade

Filtrar pelos seguintes estados de saúde do dispositivo:

- **Ativo** – Dispositivos que estão relatando ativamente dados do sensor para o serviço.
- **Inativo –** Dispositivos que pararam completamente de enviar sinais por mais de 7 dias.
- **Configuração inconfigurada** – Dispositivos que têm comunicações prejudicadas com o serviço ou não conseguem enviar dados do sensor. Dispositivos mal configurados ainda podem ser classificados para:
  - Sem dados do sensor
  - Comunicações prejudicadas

  Para obter mais informações sobre como resolver problemas em dispositivos mal configurados, consulte [Fix unhealthy sensors](fix-unhealthy-sensors.md).

### <a name="antivirus-status"></a>Status do antivírus

Filtrar dispositivos pelo status do antivírus. Aplica-se apenas a dispositivos Windows 10 ativos.

- **Desabilitado** - & proteção contra ameaças está desativada.
- **Not reporting** - Proteção contra & vírus não está relatando.
- **Não atualizado** - a proteção contra & contra vírus não está atualizada.

Para obter mais informações, [consulte View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).

### <a name="threat-mitigation-status"></a>Status de mitigação de ameaças

Para exibir dispositivos que podem ser afetados por uma determinada ameaça, selecione a ameaça no menu suspenso e selecione qual aspecto de vulnerabilidade precisa ser atenuado.

Para saber mais sobre determinadas ameaças, consulte [Análise de ameaças.](threat-analytics.md) Para obter informações de mitigação, consulte [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).

### <a name="windows-10-version"></a>Versão do Windows 10

Selecione apenas as versões do Windows 10 que você está interessado em investigar.

### <a name="tags--groups"></a>Marcas & Grupos

Filtre a lista com base no agrupamento e marcação que você adicionou a dispositivos individuais. Consulte [Criar e gerenciar marcas de dispositivo](machine-tags.md) e Criar e gerenciar grupos de [dispositivos.](machine-groups.md)

## <a name="related-topics"></a>Tópicos relacionados

- [Investigar dispositivos na lista do Microsoft Defender for Endpoint Devices](investigate-machines.md)
