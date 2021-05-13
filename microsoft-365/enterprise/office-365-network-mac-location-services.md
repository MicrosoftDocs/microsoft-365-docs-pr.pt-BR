---
title: Microsoft 365 Serviços de Localização de Conectividade de Rede
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Serviços de Localização de Conectividade de Rede
ms.openlocfilehash: ed78d7ba48cd9666ce1aae1af5478e3b7536e1e1
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470443"
---
# <a name="microsoft-365-network-connectivity-location-services"></a>Microsoft 365 Serviços de Localização de Conectividade de Rede

O Microsoft 365 Admin Center agora mostra as recomendações de desempenho e insights de rede , que são **métricas** de desempenho ao vivo coletadas do seu locatário Microsoft 365 de rede. Essas métricas só podem ser exibidas por usuários administrativos em seu locatário. A conectividade de rede organizacional é projetada por local de escritório por meio de um local de saída de rede para a Internet. Microsoft 365 de cliente usa essa rota e, em seguida, pela Internet para servidores de porta da frente do serviço microsoft. Identificar locais de escritório é fundamental para poder mostrar essas percepções de rede.

## <a name="location-in-network-measurements"></a>Local nas medições de rede

O administrador de uma organização pode optar por que o local seja incluído nas medições de rede usadas por esse recurso. Isso permite a descoberta automática da cidade onde cada escritório está localizado. As informações de local não são precisas e são ofuscados a 300m e categorizados por cidade. No momento em que o local é capturado em um dispositivo Windows, o dispositivo mostrará um ícone **local em** uso na bandeja de ferramentas. Os administradores podem querer notificar os usuários sobre a aparência desse ícone. Com esse processamento, o local é tratado como o local do escritório da organização e não o local de uma pessoa ou um dispositivo. As percepções de rede podem ser mostradas nessas cidades de localização de escritório descobertas. Se você quiser maior precisão nas recomendações, insira endereços de local específicos do escritório. Em vez disso, as percepções de rede serão agregadas a esses locais. Office locais não podem ser agregados com mais de 300 metros.

## <a name="location-in-the-microsoft-365-admin-center"></a>Local no Centro Microsoft 365 Admin

No centro de Microsoft 365 de administração, Bing controles de mapa são usados para mostrar onde estão os locais do escritório da organização. Os controles também mostram a topologia de perímetro de rede para um local de escritório selecionado. Quando um administrador adiciona detalhes de endereço específicos para locais do office, Bing Mapas também é usado para sugerir endereços para facilitar a entrada de dados.

## <a name="terms-of-use"></a>Termos de Uso

Qualquer conteúdo fornecido por Bing Mapas, incluindo códigos geocódigos, só pode ser usado dentro do produto por meio do qual o conteúdo é fornecido. O uso do cliente do recurso serviços de localização do Centro de Administração do Microsoft 365, alimentado pelo Bing Mapas, é regido pelos Termos de Uso do _Bing Mapas End-User_ disponíveis em e pela Declaração de Privacidade da <https://go.microsoft.com/?linkid=9710837> [Microsoft.](https://go.microsoft.com/fwlink/?LinkID=248686)

Esse recurso, fornecido por Bing Mapas, também é suportado por **TomTom**. Mais informações sobre os produtos e serviços da TomTom podem ser encontradas em [https://www.tomtom.com/legal](https://www.tomtom.com/legal) .

## <a name="related-topics"></a>Tópicos relacionados

[Conectividade de rede no Microsoft 365 Admin Center (visualização)](office-365-network-mac-perf-overview.md)

[Microsoft 365 de desempenho da rede (visualização)](office-365-network-mac-perf-insights.md)

[Microsoft 365 de rede (visualização)](office-365-network-mac-perf-score.md)

[Microsoft 365 de conectividade no centro de Microsoft 365 de administração (visualização)](office-365-network-mac-perf-onboarding-tool.md)
