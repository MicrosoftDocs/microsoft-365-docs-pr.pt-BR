---
title: Experimente o Microsoft Defender ATP por meio de ataques simulados
description: Execute as simulações de cenário de ataque fornecidas para experimentar como o Microsoft Defender ATP pode detectar, investigar e responder a violações.
keywords: wdatp, teste, cenário, ataque, simulação, simulado, diy, Microsoft Defender para Ponto de Extremidade
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: 25538e1866db8f4a7bff24ac336005bf2e1ce78b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053598"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>Experimente o Microsoft Defender para Ponto de Extremidade por meio de ataques simulados 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- Saiba mais sobre os aprimoramentos mais recentes no Microsoft Defender ATP: [Novidades no Defender para Ponto de Extremidade?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).
>- O Defender for Endpoint demonstrou recursos de detecção e ótica líderes do setor na avaliação recente do MITRE. Leitura: [Insights do MITRE ATT&avaliação baseada em CK.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)

Talvez você queira experimentar o Defender para Ponto de Extremidade antes de entrar em mais de alguns dispositivos no serviço. Para fazer isso, você pode executar simulações de ataque controladas em alguns dispositivos de teste. Depois de executar os ataques simulados, você pode revisar como o Defender for Endpoint superfície atividade mal-intencionada e explorar como ele habilita uma resposta eficiente.

## <a name="before-you-begin"></a>Antes de começar

Para executar qualquer uma das simulações fornecidas, você precisa de pelo menos [um dispositivo integrado.](onboard-configure.md) 

Leia o documento passo a passo fornecido com cada cenário de ataque. Cada documento inclui requisitos de sistema operacional e aplicativo, bem como instruções detalhadas específicas para um cenário de ataque.

## <a name="run-a-simulation"></a>Executar uma simulação

1. Em   >  **Simulações de Ajuda & tutoriais**, selecione qual dos cenários de ataque disponíveis você gostaria de simular:

   - **Cenário 1: o documento solta o backdoor** - simula a entrega de um documento de adução de engenharia social. O documento inicia um backdoor especialmente criado que dá controle aos invasores.

   - **Cenário 2: script** do PowerShell em ataque sem arquivo - simula um ataque sem arquivo que depende do PowerShell, mostrando a redução de superfície de ataque e a detecção de aprendizado de dispositivo de atividade de memória mal-intencionada.
    
   - **Cenário 3:** Resposta automatizada a incidentes - dispara investigação automatizada, que busca e correção automática de artefatos de violação para dimensionar sua capacidade de resposta a incidentes.

2. Baixe e leia o documento passo a passo correspondente fornecido com o cenário selecionado.

3. Baixe o arquivo de simulação ou copie o script de simulação navegando para **Simulações** de Ajuda  >  **& tutoriais.** Você pode optar por baixar o arquivo ou o script no dispositivo de teste, mas ele não é obrigatório.

4. Execute o arquivo de simulação ou o script no dispositivo de teste conforme instruído no documento passo a passo.

> [!NOTE]
> Arquivos de simulação ou scripts imitam a atividade de ataque, mas são realmente benignos e não prejudicarão ou comprometerão o dispositivo de teste.
> 
> 
> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a>Tópicos relacionados

- [Dispositivos de integração](onboard-configure.md)
- [Integração de dispositivos Windows 10](configure-endpoints.md)
