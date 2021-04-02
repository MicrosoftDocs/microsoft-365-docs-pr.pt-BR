---
title: Proteger sua organização contra ameaças da Web
description: Saiba mais sobre a proteção da Web no Microsoft Defender ATP e como ela pode proteger sua organização.
keywords: proteção da Web, proteção contra ameaças da Web, navegação na Web, segurança, phishing, malware, exploração, sites, proteção de rede, Edge, Internet Explorer, Chrome, Firefox, navegador da Web
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: aeeea02ca1ef2d37623e9ab434b162237c2f4946
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499903"
---
# <a name="protect-your-organization-against-web-threats"></a>Proteger sua organização contra ameaças da Web

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

A proteção contra ameaças da Web faz parte da [proteção da Web](web-protection-overview.md) no Defender for Endpoint. Ele usa [a proteção de rede](network-protection.md) para proteger seus dispositivos contra ameaças da Web. Ao integrar-se ao Microsoft Edge e aos navegadores populares de terceiros, como o Chrome e o Firefox, a proteção contra ameaças da Web interrompe as ameaças da Web sem um proxy da Web e pode proteger dispositivos enquanto eles estão fora ou no local. A proteção contra ameaças da Web interrompe o acesso a sites de phishing, vetores de malware, sites de exploração, sites não falsos ou de baixa reputação, bem como sites bloqueados em sua lista de indicadores [personalizados.](manage-indicators.md)

>[!Note]
>Pode levar até uma hora para que os dispositivos recebam novos indicadores personalizados.

## <a name="prerequisites"></a>Pré-requisitos
A proteção da Web usa a proteção de rede para fornecer segurança de navegação na Web no Microsoft Edge e em navegadores da Web de terceiros.

Para ativar a proteção de rede em seus dispositivos:
- Edite a linha de base de segurança do Defender para Ponto de Extremidade em Proteção de Rede **& Web** para habilitar a proteção de rede antes de implantá-la ou reimplantá-la. [Saiba mais sobre como revisar e atribuir a linha de base de segurança do Defender for Endpoint](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- Adeque a proteção de rede usando a configuração de dispositivo do Intune, SCCM, Política de Grupo ou sua solução MDM. [Leia mais sobre a habilitação da proteção de rede](enable-network-protection.md)  

>[!Note]
>Se você definir a proteção de rede como **Somente Auditoria,** o bloqueio ficará indisponível. Além disso, você poderá detectar e registrar tentativas de log para acessar sites mal-intencionados e indesejados apenas no Microsoft Edge.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral da proteção da Web](web-protection-overview.md)
- [Proteção contra ameaças da Web](web-threat-protection.md)
- [Monitorar a segurança da Web](web-protection-monitoring.md)
- [Responder a ameaças da Web](web-protection-response.md)
- [Proteção de rede](network-protection.md)
