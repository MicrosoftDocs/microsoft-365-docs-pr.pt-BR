---
title: Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel
description: Use ferramentas de Gerenciamento de Dispositivo Móvel para implantar o pacote de configuração em dispositivos para que eles sejam integrados ao serviço.
keywords: onboard devices using mdm, device management, onboard Microsoft Defender for Endpoint devices, mdm
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
ms.openlocfilehash: 45aa406212fe39f088f58bf311b1aed3fed16498
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843429"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

Você pode usar soluções de gerenciamento de dispositivo móvel (MDM) para configurar dispositivos. O Defender for Endpoint dá suporte a MDMs fornecendo OMA-URIs para criar políticas para gerenciar dispositivos.

Para obter mais informações sobre como usar o CSP do Defender para Ponto de Extremidade, consulte o arquivo [DDF do WindowsAdvancedThreatProtection](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) e o arquivo [DDF do WindowsAdvancedThreatProtection.](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)

## <a name="before-you-begin"></a>Antes de começar
Se você estiver usando Microsoft Intune, deverá ter o MDM do dispositivo inscrito. Caso contrário, as configurações não serão aplicadas com êxito. 

Para obter mais informações sobre a habilitação do MDM com Microsoft Intune, consulte Registro de [dispositivo (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).

## <a name="onboard-devices-using-microsoft-intune"></a>Dispositivos de integração usando Microsoft Intune

[![Imagem do PDF mostrando dispositivos de integração para o Defender para Ponto de Extremidade usando Microsoft Intune ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)

Confira o [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) ou [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) para ver os vários caminhos na implantação do Defender para o Ponto de Extremidade. 

Siga as instruções do [Intune](/intune/advanced-threat-protection).

Para obter mais informações sobre como usar o CSP do Defender para Ponto de Extremidade, consulte o arquivo [DDF do WindowsAdvancedThreatProtection](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) e o arquivo [DDF do WindowsAdvancedThreatProtection.](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)


> [!NOTE]
> - A **política Status da Saúde para dispositivos conectados** usa propriedades somente leitura e não pode ser remediada.
> - A configuração da frequência de relatório de dados de diagnóstico só está disponível para dispositivos Windows 10 versão 1703.


>[!TIP]
> Após a integração do dispositivo, você pode optar por executar um teste de detecção para verificar se um dispositivo está corretamente conectado ao serviço. Para obter mais informações, [consulte Execute a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).


Confira o [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) ou [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) para ver os vários caminhos na implantação do Microsoft Defender para Ponto de Extremidade.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Offboard e monitore dispositivos usando ferramentas de Gerenciamento de Dispositivo Móvel
Por motivos de segurança, o pacote usado para dispositivos offboard expirará 30 dias após a data em que foi baixado. Os pacotes de offboard expirados enviados para um dispositivo serão rejeitados. Ao baixar um pacote de offboard, você será notificado sobre a data de expiração dos pacotes e ele também será incluído no nome do pacote.

> [!NOTE]
> As políticas de integração e de offboard não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.

1. Obter o pacote de offboard de [Central de Segurança do Microsoft Defender](https://securitycenter.windows.com/):

   1. No painel de navegação, selecione **Configurações**  >  **Offboarding**.

   1. Selecione Windows 10 como o sistema operacional.

   1. No campo **Método de implantação,** selecione **Gerenciamento de Dispositivo Móvel /Microsoft Intune**.
    
   1. Clique **em Baixar pacote** e salve o .zip arquivo.

2. Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelos administradores de rede que implantarão o pacote. Você deve ter um arquivo chamado *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.

3. Use a Microsoft Intune de configuração personalizada para implantar as seguintes configurações OMA-URI com suporte.

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding<br/>
      Tipo de data: Cadeia de caracteres<br/>
      Valor: [Copiar e colar o valor do conteúdo do arquivo WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding]

Para obter mais informações sobre Microsoft Intune configurações de política, consulte Windows 10 [configurações](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)de política em Microsoft Intune .


> [!NOTE]
> A **política Status da Saúde para dispositivos** fora do quadro usa propriedades somente leitura e não pode ser remediada.

> [!IMPORTANT]
> O offboard faz com que o dispositivo pare de enviar dados do sensor para o portal, mas os dados do dispositivo, incluindo a referência a todos os alertas que ele teve, serão mantidos por até 6 meses.

## <a name="related-topics"></a>Tópicos relacionados
- [Integração Windows 10 usando a Política de Grupo](configure-endpoints-gp.md)
- [Integração Windows 10 dispositivos usando Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md)
- [Integrar dispositivos Windows 10 usando um script local](configure-endpoints-script.md)
- [Dispositivos integrados de VDI (Virtual Desktop Infrastructure) não persistente](configure-endpoints-vdi.md)
- [Executar um teste de detecção em um dispositivo recém-integrado do Microsoft Defender para Ponto de Extremidade](run-detection-test.md)
- [Solucionar problemas de integração do Microsoft Defender para pontos de extremidade](troubleshoot-onboarding.md)
