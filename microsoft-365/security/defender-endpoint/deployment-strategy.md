---
title: Planejar sua implantação do Microsoft Defender para Ponto de Extremidade
description: Selecione a melhor estratégia de implantação do Microsoft Defender para Ponto de Extremidade para seu ambiente
keywords: deploy, plan, deployment strategy, cloud native, management, on prem, evaluation, onboarding, local, group policy, gp, endpoint manager, mem
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cd670e72bbb4ec0abacd4ed053a9ea9af12608b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163570"
---
# <a name="plan-your-microsoft-defender-for-endpoint-deployment"></a>Planejar sua implantação do Microsoft Defender para Ponto de Extremidade 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 


Planeje a implantação do Microsoft Defender para o Ponto de Extremidade para que você possa maximizar os recursos de segurança dentro do pacote e proteger melhor sua empresa contra ameaças cibernéticas.


Essa solução fornece orientações sobre como identificar sua arquitetura de ambiente, selecionar o tipo de ferramenta de implantação que melhor atende às suas necessidades e orientações sobre como configurar recursos.


![Imagem do fluxo de implantação](images/deployment-guide-plan.png)


## <a name="step-1-identify-architecture"></a>Etapa 1: Identificar arquitetura
Entendemos que todos os ambientes corporativos são exclusivos, portanto, fornecemos várias opções para dar a você a flexibilidade de escolher como implantar o serviço.

Dependendo do ambiente, algumas ferramentas são mais adequadas para determinadas arquiteturas. 

Use o material a seguir para selecionar o Defender para a arquitetura do Ponto de Extremidade apropriado que melhor acompanha sua organização.

| Item | Descrição |
|:-----|:-----|
|[![Imagem em miniatura da estratégia de implantação do Defender para Ponto de Extremidade](images/mdatp-deployment-strategy.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)<br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  \| [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) | O material arquitetônico ajuda a planejar a implantação para as seguintes arquiteturas: <ul><li> Nuvem nativa </li><li> Cogerenciamento </li><li> No local</li><li>Avaliação e integração local</li>



## <a name="step-2-select-deployment-method"></a>Etapa 2: selecionar o método de implantação
O Defender para Ponto de Extremidade oferece suporte a uma variedade de pontos de extremidade que você pode integrar ao serviço. 

A tabela a seguir lista os pontos de extremidade com suporte e a ferramenta de implantação correspondente que você pode usar para que você possa planejar a implantação adequadamente.

| Ponto de extremidade     | Ferramenta de implantação                       |
|--------------|------------------------------------------|
| **Windows**  |  [Script local (até 10 dispositivos)](configure-endpoints-script.md) <br>  [Política de grupo](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Gerenciador de Dispositivos Móveis](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [Scripts VDI](configure-endpoints-vdi.md)   |
| **macOS**    | [Script local](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Gerenciamento de dispositivo móvel](mac-install-with-other-mdm.md) |
| **Servidor Linux** | [Script local](linux-install-manually.md) <br> [Puppet](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [Baseado em aplicativos](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 



## <a name="step-3-configure-capabilities"></a>Etapa 3: Configurar recursos
Após a integração dos pontos de extremidade, configure os recursos de segurança no Defender para Ponto de Extremidade para que você possa maximizar a proteção de segurança robusta disponível no pacote. Os recursos incluem:

- Detecção de ponto de extremidade e resposta
- Proteção de próxima geração
- Redução de superfície de ataque


  
## <a name="related-topics"></a>Tópicos relacionados
- [Fases da implementação](deployment-phases.md)
