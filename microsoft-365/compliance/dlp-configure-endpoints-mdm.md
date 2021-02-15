---
title: Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Use as ferramentas de Gerenciamento de Dispositivo Móvel para implantar o pacote de configuração em dispositivos para que eles sejam integrados ao serviço.
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769392"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel

**Aplica-se a:**

- [Prevenção contra perda de dados de ponto de extremidade (DLP) do Microsoft 365](/microsoft-365/compliance/endpoint-dlp-learn-about)

Você pode usar soluções de gerenciamento de dispositivo móvel (MDM) para configurar dispositivos. A prevenção contra perda de dados de ponto de extremidade do Microsoft 365 dá suporte a MDMs OMA-URIs criar políticas para gerenciar dispositivos.


## <a name="before-you-begin"></a>Antes de começar
Se você estiver usando o Microsoft Intune, deverá ter o MDM do dispositivo inscrito. Caso contrário, as configurações não serão aplicadas com êxito. 

Para obter mais informações sobre a habilitação do MDM com o Microsoft Intune, consulte [Registro de dispositivo (Microsoft Intune).](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)

## <a name="onboard-devices-using-microsoft-intune"></a>Dispositivos onboard usando o Microsoft Intune

Siga as instruções do [Intune.](https://docs.microsoft.com/intune/advanced-threat-protection)

> [!NOTE]
> - A **política status de saúde para dispositivos onboarded** usa propriedades somente leitura e não pode ser remediada.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Fazer o offboard e monitorar dispositivos usando ferramentas de Gerenciamento de Dispositivo Móvel

Por motivos de segurança, o pacote usado para dispositivos offboard expirará 30 dias após a data em que foi baixado. Os pacotes de reexenciamento expirados enviados para um dispositivo serão rejeitados. Ao baixar um pacote de descarregamento, você será notificado sobre a data de vencimento dos pacotes e ele também será incluído no nome do pacote.

> [!NOTE]
> As políticas de integração e de transferência não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.

1. Obter o pacote de redação do Centro [de Conformidade da Microsoft.](https://compliance.microsoft.com/)

2. No painel de navegação, selecione **Configurações**  >  **integração do dispositivo** à  >  **rebordagem.**

3. No campo **do método de implantação,** selecione Gerenciamento de **Dispositivo Móvel/Microsoft Intune.**
    
4. Clique **em Baixar pacote** e salve o arquivo .zip.

5. Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que possa ser acessado pelos administradores de rede que implantarão o pacote. Você deve ter um arquivo *chamado DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.

6. Use a política de configuração personalizada do Microsoft Intune para implantar as seguintes configurações OMA-URI com suporte.

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      Tipo de data: Cadeia de caracteres      
      Valor: [Copiar e colar o valor do conteúdo do arquivo DeviceCompliance_valid_until_YYYY-MM-DD.offboarding]

Para obter mais informações sobre as configurações de política do Microsoft Intune, consulte as configurações de política do [Windows 10 no Microsoft Intune.](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)

> [!NOTE]
> O **Status de Saúde para dispositivos** de fora da área usa propriedades somente leitura e não pode ser remediado.

> [!IMPORTANT]
> A reação faz com que o dispositivo pare de enviar dados do sensor para o portal, mas os dados do dispositivo, incluindo a referência a todos os alertas que ele recebeu, serão retidos por até seis meses.

## <a name="related-topics"></a>Tópicos relacionados
- [Integração de dispositivos Windows 10 usando Política de Grupo](dlp-configure-endpoints-gp.md)
- [Integração de dispositivos Windows 10 usando o Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Integrar dispositivos Windows 10 usando um script local](dlp-configure-endpoints-script.md)
- [Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)](dlp-configure-endpoints-vdi.md)
- [Solucionar problemas de integração da Proteção Avançada contra Ameaças do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
