---
title: Ferramentas e métodos de integração para computadores Windows 10
description: Integração de dispositivos Windows 10 para que eles possam enviar dados do sensor para o sensor do Microsoft Defender ATP
keywords: Integração de dispositivos Windows 10, política de grupo, gerenciador de configuração de ponto de extremidade, gerenciamento de dispositivo móvel, script local, gp, sccm, mdm, intune
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1831d8927e761827f9bbcee84551433b68e3c6cc
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165532"
---
# <a name="onboarding-tools-and-methods-for-windows-10-devices"></a>Ferramentas e métodos de integração para computadores Windows 10

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Prevenção contra perda de dados do Microsoft 365 Endpoint (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Os dispositivos em sua organização devem ser configurados para que o serviço Defender for Endpoint possa obter dados do sensor deles. Há vários métodos e ferramentas de implantação que você pode usar para configurar os dispositivos em sua organização.

As seguintes ferramentas de implantação e métodos são suportados:

- Política de Grupo
- Microsoft Endpoint Configuration Manager
- Gerenciamento de dispositivo móvel (incluindo o Microsoft Intune)
- Script local

## <a name="in-this-section"></a>Nesta seção
Tópico | Descrição
:---|:---
[Integração de dispositivos Windows 10 usando a Política de Grupo](configure-endpoints-gp.md) | Use a Política de Grupo para implantar o pacote de configuração em dispositivos.
[Integração de dispositivos Windows usando o Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) | Você pode usar o Microsoft Endpoint Manager (branch atual) versão 1606 ou o Microsoft Endpoint Manager (branch atual) versão 1602 ou anterior para implantar o pacote de configuração em dispositivos.
[Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel](configure-endpoints-mdm.md) | Use as ferramentas de Gerenciamento de Dispositivo Móvel ou o Microsoft Intune para implantar o pacote de configuração no dispositivo.
[Integrar dispositivos Windows 10 usando um script local](configure-endpoints-script.md) | Saiba como usar o script local para implantar o pacote de configuração nos pontos de extremidade.
[Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)](configure-endpoints-vdi.md) | Saiba como usar o pacote de configuração para configurar dispositivos VDI.


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpoints-belowfoldlink)
