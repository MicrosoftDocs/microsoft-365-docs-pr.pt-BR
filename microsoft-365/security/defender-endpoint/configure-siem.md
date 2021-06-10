---
title: Pull detections to your SIEM tools from Microsoft Defender for Endpoint
description: Saiba como usar a API REST e configurar as ferramentas de gerenciamento de eventos e informações de segurança com suporte para receber e puxar detecções.
keywords: configurar siem, ferramentas de gerenciamento de informações e eventos de segurança, splunk, arcsight, indicadores personalizados, api de repouso, definições de alerta, indicadores de comprometimento
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
ms.openlocfilehash: 97a64c8537ff2a6f9948ed6ed056b8aa7379ce69
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222330"
---
# <a name="pull-detections-to-your-siem-tools"></a>Pull detections to your SIEM tools

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a>Pull detections using security information and events management (SIEM) tools

>[!NOTE]
>- [O Alerta do Microsoft Defender para Ponto](alerts.md) de Extremidade é composto por uma ou mais detecções.
>- [O Microsoft Defender para Detecção de Ponto](api-portal-mapping.md) de Extremidade é composto do evento suspeito ocorrido no Dispositivo e seus detalhes de Alerta relacionados.
>-A API de alerta do Microsoft Defender for Endpoint é a API mais recente para consumo de alerta e contém uma lista detalhada de evidências relacionadas para cada alerta. Para obter mais informações, consulte [Métodos de alerta e propriedades](alerts.md) e [Alertas de lista.](get-alerts.md)

O Defender for Endpoint oferece suporte a ferramentas de gerenciamento de informações de segurança e de eventos (SIEM) para detectar detecções. O Defender for Endpoint expõe alertas por meio de um ponto de extremidade HTTPS hospedado no Azure. O ponto de extremidade pode ser configurado para puxar detecções do seu locatário empresarial no Azure Active Directory (AAD) usando o protocolo de autenticação OAuth 2.0 para um aplicativo AAD que representa o conector SIEM específico instalado em seu ambiente.

O Defender for Endpoint atualmente dá suporte às seguintes ferramentas de solução SIEM específicas por meio de um modelo de integração SIEM dedicado:

- IBM QRadar
- Micro Focus ArcSight

Outras soluções SIEM (como Splunk, RSA NetWitness) são suportadas por meio de um modelo de integração diferente com base na nova API de Alerta. Para obter mais informações, consulte a página [Aplicativo parceiro](https://securitycenter.microsoft.com/interoperability/partners) e selecione a seção Informações de Segurança e Análise para obter detalhes completos.

Para usar uma dessas ferramentas SIEM com suporte, você precisará:

- [Habilitar a integração do SIEM no Defender para Ponto de Extremidade](enable-siem-integration.md)
- Configure a ferramenta SIEM suportada:
     - [Configurar o Micro Focus ArcSight para puxar o Defender para detecções de ponto de extremidade](configure-arcsight.md)
     - Configurar IBM QRadar para puxar o Defender para detecções de ponto de extremidade Para obter mais informações, consulte [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).

Para obter mais informações sobre a lista de campos expostos na API de Detecção, consulte [Defender for Endpoint Detection fields](api-portal-mapping.md).
