---
title: Obter dispositivos conectados ao Microsoft Defender para Ponto de Extremidade
description: Acompanhe a integração de dispositivos gerenciados pelo Intune ao Microsoft Defender para Ponto de Extremidade e aumente a taxa de integração.
keywords: onboard, Gerenciamento do Intune, MDATP, WDATP, Microsoft Defender, Windows Defender, proteção avançada contra ameaças, gerenciamento de configuração
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
ms.technology: mde
ms.openlocfilehash: 5e20c424f15561c8b6f0544b80aca6e30c56409d
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893324"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a>Obter dispositivos conectados ao Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

Cada dispositivo integrado adiciona um sensor de resposta e detecção de ponto de extremidade adicional (EDR) e aumenta a visibilidade sobre a atividade de violação em sua rede. A integração também garante que um dispositivo possa ser verificado se há componentes vulneráveis, bem como problemas de configuração de segurança e pode receber ações críticas de correção durante ataques.

Antes de rastrear e gerenciar a integração de dispositivos:
- [Registrar seus dispositivos no gerenciamento do Intune](configure-machines.md#enroll-devices-to-intune-management)
- [Verifique se você tem as permissões necessárias](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a>Descobrir e rastrear dispositivos desprotegidos

O **cartão onboarding** fornece uma visão geral de alto nível da sua taxa de integração comparando o número de dispositivos Windows 10 que realmente integraram com o Defender para Ponto de Extremidade em relação ao número total de dispositivos Windows 10 gerenciados pelo Intune.

![Cartão de integração de gerenciamento de configuração de dispositivo](images/secconmgmt_onboarding_card.png)<br>
*Cartão mostrando dispositivos conectados em comparação com o número total de dispositivos Windows 10 gerenciados pelo Intune*

>[!NOTE]
>Se você usou o Security Center Configuration Manager, o script de integração ou outros métodos de integração que não usam perfis do Intune, poderá encontrar discrepâncias de dados. Para resolver essas discrepâncias, crie um perfil de configuração do Intune correspondente para a integração do Defender para Ponto de Extremidade e atribua esse perfil aos seus dispositivos.

## <a name="onboard-more-devices-with-intune-profiles"></a>Integrar mais dispositivos com perfis do Intune

O Defender para Ponto de Extremidade fornece várias opções convenientes para a [integração de dispositivos Windows 10.](onboard-configure.md) No entanto, para dispositivos gerenciados pelo Intune, você pode aproveitar os perfis do Intune para implantar convenientemente o sensor Defender para Ponto de Extremidade para selecionar dispositivos, integrando efetivamente esses dispositivos ao serviço.

No cartão **De integração,** selecione **Onboard more devices** to create and assign a profile on Intune. O link leva você para a página de conformidade do dispositivo no Intune, que fornece uma visão geral semelhante do seu estado de integração.

![Página de conformidade de dispositivos do Microsoft Defender ATP no gerenciamento de dispositivos do Intune](images/secconmgmt_onboarding_1deviceconfprofile.png)<br>
   *Página de conformidade de dispositivos do Microsoft Defender ATP no gerenciamento de dispositivos do Intune*

>[!TIP]
>Como alternativa, você pode navegar até a página de conformidade de integração do Defender for Endpoint no portal do [Microsoft Azure](https://portal.azure.com/) a partir de Todos os serviços **> Intune > Conformidade** de dispositivo > Microsoft Defender ATP .

>[!NOTE]
> Se você quiser exibir os dados de dispositivo mais atualizados, clique em Lista de dispositivos sem sensor **ATP**.

Na página de conformidade do dispositivo, crie um perfil de configuração especificamente para a implantação do sensor Defender para Ponto de Extremidade e atribua esse perfil aos dispositivos que você deseja integrar. Para fazer isso, você pode:

- Selecione **Criar um perfil de configuração de dispositivo para configurar o sensor ATP** para começar com um perfil de configuração de dispositivo predefinido.
- Crie o perfil de configuração do dispositivo do zero.

Para obter mais informações, [leia sobre como usar perfis de configuração](https://docs.microsoft.com/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile)de dispositivo do Intune para integração de dispositivos no Defender for Endpoint .

>Deseja experimentar o Microsoft Defender ATP? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a>Tópicos relacionados
- [Verificar se os dispositivos estão configurados corretamente](configure-machines.md)
- [Aumentar a conformidade com a linha de base de segurança do Defender para Ponto de Extremidade](configure-machines-security-baseline.md)
- [Otimizar a implantação e as detecções de regras ASR](configure-machines-asr.md)
