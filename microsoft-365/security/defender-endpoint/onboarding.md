---
title: Integração ao serviço microsoft defender para ponto de extremidade
description: Saiba como integrar pontos de extremidade ao serviço do Microsoft Defender para Ponto de Extremidade
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: cc538c887397d5bbea78f63c8a8acd318ec7fe9f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689528"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a>Integração ao serviço microsoft defender para ponto de extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Saiba mais sobre as várias fases de implantação do Microsoft Defender para Ponto de Extremidade e como configurar os recursos dentro da solução. 

Implantar o Defender para Ponto de Extremidade é um processo de três fases:

| [![fase de implantação - preparar](images/phase-diagrams/prepare.png)](prepare-deployment.md)<br>[Fase 1: Preparar](prepare-deployment.md) | [![fase de implantação - instalação](images/phase-diagrams/setup.png)](production-deployment.md)<br>[Fase 2: Configurar](production-deployment.md) | ![fase de implantação - onboard](images/phase-diagrams/onboard.png)<br>Fase 3: Integrar |
| ----- | ----- | ----- |
| | |*Você está aqui!*|

No momento, você está na fase de integração.

Estas são as etapas que você precisa seguir para implantar o Defender para o Ponto de Extremidade:

- Etapa 1: Pontos de extremidade de integração para o serviço 
- Etapa 2: Configurar recursos 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Etapa 1: Pontos de extremidade de integração usando qualquer uma das ferramentas de gerenciamento com suporte
O [tópico Planejar implantação](deployment-strategy.md) descreve as etapas gerais que você precisa seguir para implantar o Defender para o Ponto de Extremidade.  


Assista a este vídeo para uma visão geral rápida do processo de integração e saiba mais sobre as ferramentas e métodos disponíveis.
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



Depois de identificar sua arquitetura, você precisará decidir qual método de implantação usar. A ferramenta de implantação escolhida influencia como você integra pontos de extremidade ao serviço. 

### <a name="onboarding-tool-options"></a>Opções da ferramenta de integração

A tabela a seguir lista as ferramentas disponíveis com base no ponto de extremidade que você precisa integrar.

| Ponto de extremidade     | Opções de ferramenta                       |
|--------------|------------------------------------------|
| **Windows**  |  [Script local (até 10 dispositivos)](configure-endpoints-script.md) <br>  [Política de grupo](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Mobile Device Manager](configure-endpoints-mdm.md) <br> [Gerenciador de Configuração do Microsoft Endpoint](configure-endpoints-sccm.md) <br> [Scripts VDI](configure-endpoints-vdi.md) <br> [Central de Segurança do Azure](configure-server-endpoints.md#integration-with-azure-security-center) |
| **macOS**    | [Scripts locais](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Gerenciamento de dispositivo móvel](mac-install-with-other-mdm.md) |
| **Servidor Linux** | [Script local](linux-install-manually.md) <br> [Puppet](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [Baseado em aplicativos](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a>Etapa 2: Configurar recursos
Após a integração dos pontos de extremidade, você configurará os vários recursos, como detecção e resposta do ponto de extremidade, proteção de próxima geração e redução de superfície de ataque. 


## <a name="example-deployments"></a>Exemplo de implantações
Neste guia de implantação, vamos orientá-lo usando duas ferramentas de implantação para pontos de extremidade de integração e como configurar recursos.

As ferramentas nas implantações de exemplo são:
- [Integração usando o Microsoft Endpoint Configuration Manager](onboarding-endpoint-configuration-manager.md)
- [Integração usando o Microsoft Endpoint Manager](onboarding-endpoint-manager.md)

Usando as ferramentas de implantação mencionadas acima, você será orientado a configurar os seguintes recursos do Defender para o Ponto de Extremidade:
- Configuração de resposta e detecção de ponto de extremidade
- Configuração de proteção de última geração
- Configuração de redução de superfície de ataque

## <a name="related-topics"></a>Tópicos relacionados
- [Integração usando o Microsoft Endpoint Configuration Manager](onboarding-endpoint-configuration-manager.md)
- [Integração usando o Microsoft Endpoint Manager](onboarding-endpoint-manager.md)
- [Documentos Seguros no Microsoft 365 E5](../office-365-security/safe-docs.md)
