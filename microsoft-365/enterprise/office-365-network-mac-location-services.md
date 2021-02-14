---
title: Serviços de Localização de Conectividade de Rede do Microsoft 365 (visualização)
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
description: Serviços de Localização de Conectividade de Rede do Microsoft 365 (visualização)
ms.openlocfilehash: f2ab872f67eca70ab2791d3ad6fe1396b009cc18
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200776"
---
# <a name="microsoft-365-network-connectivity-location-services-preview"></a>Serviços de Localização de Conectividade de Rede do Microsoft 365 (visualização)

O Centro de Administração do Microsoft 365 agora mostra as Informações da Rede e as recomendações de desempenho, que são métricas de desempenho ao vivo coletadas do locatário do Microsoft 365 e disponíveis para exibição somente por usuários **administrativos** em seu locatário. A conectividade de rede organizacional é projetada por local de escritório por meio de um local de saída de rede para a Internet. A conectividade do cliente microsoft 365 usa essa rota e, em seguida, pela Internet para os servidores de front-door de serviço da Microsoft. Identificar locais de escritório é fundamental para poder mostrar essas informações de rede.

## <a name="location-in-network-measurements"></a>Localização em medições de rede

O administrador da organização pode optar por incluir o local nas medições de rede usadas por esse recurso. Isso permite a descoberta automática da cidade onde cada escritório está localizado. As informações de localização não são precisas e são ofuscados a 300 m e categorizados por cidade. No momento em que a localização for capturada em um dispositivo Windows, ele mostrará um ícone de Local **Em** Uso na bandeja da ferramenta e os administradores poderão querer notificar os usuários sobre isso. Com esse processamento, o local é tratado como o local do escritório da organização e não o local de uma pessoa ou dispositivo. As informações de rede podem ser mostradas nessas cidades de localização de escritório descobertas. Se desejar uma maior precisão das recomendações, um administrador pode inserir endereços de localização específicos do escritório e as informações de rede serão agregadas a eles. Os locais do Office não podem ser agregados mais de 300 metros.

## <a name="location-in-the-microsoft-365-admin-center"></a>Local no Centro de administração do Microsoft 365

No Centro de administração do Microsoft 365, os controles de mapa do Bing são usados para mostrar onde estão os locais de escritório da organização e mostrar a topologia de perímetro de rede para um local de escritório selecionado. Quando um administrador adiciona detalhes de endereço específicos para locais de escritório, o Bing Maps também é usado para sugerir endereços para facilitar a entrada de dados.

## <a name="terms-of-use"></a>Termos de Uso

Qualquer conteúdo fornecido por meio do Bing Maps, incluindo geocódigos, só pode ser usado dentro do produto por meio do qual o conteúdo é fornecido. O uso do cliente do recurso Serviços de Localização do Centro de Administração do Microsoft 365, da plataforma Bing Maps, é regido pelos Termos de Uso do Usuário Final do _Bing Mapas_ disponíveis e pela Política de Privacidade da <https://go.microsoft.com/?linkid=9710837> _Microsoft_ disponível em <https://go.microsoft.com/fwlink/?LinkID=248686.>

Esse recurso, fornecido por meio do Bing Maps, também é suportado pelas **Tecnologias Aqui.** Como o Bing Maps aproveita os serviços de localização fornecidos pelas Tecnologias Aqui é regido pelos Termos de Serviço _aqui tecnologias_ disponíveis em <https://legal.here.com/en-gb/terms> .

## <a name="related-topics"></a>Tópicos relacionados

[Conectividade de rede no Centro de administração do Microsoft 365 (visualização)](office-365-network-mac-perf-overview.md)

[Percepções de desempenho de rede do Microsoft 365 (visualização)](office-365-network-mac-perf-insights.md)

[Avaliação de rede do Microsoft 365 (visualização)](office-365-network-mac-perf-score.md)

[Teste de conectividade do Microsoft 365 no Centro de Administração do M365 (visualização)](office-365-network-mac-perf-onboarding-tool.md)
