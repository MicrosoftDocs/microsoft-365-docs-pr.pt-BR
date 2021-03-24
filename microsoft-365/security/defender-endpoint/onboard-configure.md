---
title: Integração de dispositivos para o serviço Microsoft Defender ATP
description: Onboard Windows 10 devices, servers, non-Windows devices and learn how to run a detection test.
keywords: integração, microsoft defender para integração de ponto de extremidade, integração do windows atp, sccm, política de grupo, mdm, script local, teste de detecção
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
ms.openlocfilehash: 1deb8a0e00785705937d4cf6de71a030d3d9c971
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052621"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a>Integração de dispositivos para o serviço do Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Você precisará ir até a seção de integração do portal do Defender para Ponto de Extremidade para integrar qualquer um dos dispositivos com suporte. Dependendo do dispositivo, você será orientado com as etapas apropriadas e forneceu opções de ferramenta de gerenciamento e implantação adequadas para o dispositivo. 

Em geral, para integração de dispositivos ao serviço:

- Verifique se o dispositivo atende aos requisitos [mínimos](minimum-requirements.md)
- Dependendo do dispositivo, siga as etapas de configuração fornecidas na seção de integração do portal Defender para Ponto de Extremidade
- Use a ferramenta de gerenciamento apropriada e o método de implantação para seus dispositivos
- Execute um teste de detecção para verificar se os dispositivos estão corretamente conectados e relatando ao serviço

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a>Opções da ferramenta de integração
A tabela a seguir lista as ferramentas disponíveis com base no ponto de extremidade que você precisa integrar.

| Ponto de extremidade     | Opções de ferramenta                       |
|--------------|------------------------------------------|
| **Windows**  |  [Script local (até 10 dispositivos)](configure-endpoints-script.md) <br>  [Política de grupo](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Mobile Device Manager](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Scripts VDI](configure-endpoints-vdi.md)   |
| **macOS**    | [Scripts locais](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Gerenciamento de dispositivo móvel](mac-install-with-other-mdm.md) |
| **Servidor Linux** | [Script local](linux-install-manually.md) <br> [Puppet](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [Baseado em aplicativos](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 




## <a name="in-this-section"></a>Nesta seção
Tópico | Descrição
:---|:---
[Integração de versões anteriores do Windows](onboard-downlevel.md)| Integração de dispositivos Windows 7 e Windows 8.1 para Defender para Ponto de Extremidade. 
[Integração de dispositivos Windows 10](configure-endpoints.md) | Você precisará integrar dispositivos para que ele se reporte ao serviço Defender para Ponto de Extremidade. Saiba mais sobre as ferramentas e métodos que você pode usar para configurar dispositivos em sua empresa.
[Servidores de integração](configure-server-endpoints.md) |  Integrando o Windows Server 2008 R2 SP1, o Windows Server 2012 R2, o Windows Server 2016, o Windows Server (SAC) versão 1803 e posterior, o Windows Server 2019 e posterior e a edição principal do Windows Server 2019 para o Defender para Ponto de Extremidade.
[Integração de dispositivos que não são windows](configure-endpoints-non-windows.md) | O Defender for Endpoint fornece uma experiência centralizada de operações de segurança para o Windows, bem como para plataformas que não são do Windows. Você poderá ver alertas de vários sistemas operacionais com suporte (SO) no Centro de Segurança do Microsoft Defender e proteger melhor a rede da sua organização. Essa experiência aproveita os dados do sensor de produtos de segurança de terceiros. 
[Executar um teste de detecção em um dispositivo recém-conectado](run-detection-test.md) | Execute um script em um dispositivo recém-conectado para verificar se ele está relatando corretamente para o serviço Defender para Ponto de Extremidade.
[Configurar configurações de proxy e Internet](configure-proxy-internet.md)| Habilita a comunicação com o serviço de nuvem do Defender para Ponto de Extremidade configurando as configurações de conectividade proxy e Internet.
[Solucionar problemas de integração](troubleshoot-onboarding.md) | Saiba mais sobre como resolver problemas que podem surgir durante a integração.

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
