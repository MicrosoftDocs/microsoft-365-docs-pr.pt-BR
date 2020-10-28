---
title: Dispositivos do Windows 10 integrados usando ferramentas de gerenciamento de dispositivos móveis
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
description: Use as ferramentas de gerenciamento de dispositivo móvel para implantar o pacote de configuração nos dispositivos para que eles sejam incluídos no serviço.
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769392"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>Dispositivos do Windows 10 integrados usando ferramentas de gerenciamento de dispositivos móveis

**Aplica-se a:**

- [Prevenção de perda de dados do Microsoft 365 EndPoint (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

Você pode usar soluções de gerenciamento de dispositivo móvel (MDM) para configurar dispositivos. OMA-URIs a prevenção de perda de dados de ponto de extremidade do Microsoft 365 oferece suporte ao MDMs para a criação de políticas para gerenciar dispositivos.


## <a name="before-you-begin"></a>Antes de começar
Se você estiver usando o Microsoft Intune, deverá ter o dispositivo MDM cadastrado. Caso contrário, as configurações não serão aplicadas com êxito. 

Para obter mais informações sobre como habilitar o MDM com o Microsoft Intune, consulte [Device Enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).

## <a name="onboard-devices-using-microsoft-intune"></a>Dispositivos integrados usando o Microsoft Intune

Siga as instruções do [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).

> [!NOTE]
> - A política **status de integridade para dispositivos integrados** usa propriedades somente leitura e não pode ser corrigida.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>Externamente e monitorar dispositivos usando ferramentas de gerenciamento de dispositivo móvel

Por motivos de segurança, o pacote usado para os dispositivos do externamente expirará 30 dias após a data em que foi baixado. Os pacotes de remoção expirados enviados para um dispositivo serão rejeitados. Ao baixar um pacote de remoção, você será notificado sobre a data de expiração dos pacotes e ele também será incluído no nome do pacote.

> [!NOTE]
> As políticas de integração e remoção não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.

1. Obtenha o pacote de remoção do [centro de conformidade da Microsoft](https://compliance.microsoft.com/).

2. No painel de navegação, selecione remoção de configuração de dispositivo de **configurações**  >  **Device onboarding**  >  **Offboarding** .

3. No campo **método de implantação** , selecione **Gerenciamento de dispositivo móvel/Microsoft Intune** .
    
4. Clique em **baixar pacote** e salve o arquivo. zip.

5. Extraia o conteúdo do arquivo. zip para um local compartilhado e somente leitura que possa ser acessado pelos administradores de rede que implantarão o pacote. Você deve ter um arquivo chamado *DeviceCompliance_valid_until_YYYY-mm-dd. imremoção* .

6. Use a política de configuração personalizada do Microsoft Intune para implantar as seguintes configurações de OMA-URI suportadas.

      OMA-URI:./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      Tipo de data: cadeia de caracteres      
      Valor: [copiar e colar o valor do conteúdo do arquivo DeviceCompliance_valid_until_YYYY-MM-DD. remoção]

Para obter mais informações sobre as configurações de política do Microsoft Intune, consulte [as configurações de política do Windows 10 no Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).

> [!NOTE]
> A política **status de integridade para dispositivos offboarded** usa propriedades somente leitura e não pode ser corrigida.

> [!IMPORTANT]
> A remoção faz com que o dispositivo pare de enviar dados de sensor para o portal, mas os dados do dispositivo, incluindo referência a qualquer alerta que tenha tido, serão mantidos por até seis meses.

## <a name="related-topics"></a>Tópicos relacionados
- [Dispositivos Windows 10 integrados usando a política de grupo](dlp-configure-endpoints-gp.md)
- [Dispositivos Windows 10 integrados usando o Microsoft Endpoint Configuration Manager](dlp-configure-endpoints-sccm.md)
- [Dispositivos integrados do Windows 10 usando um script local](dlp-configure-endpoints-script.md)
- [Dispositivos não persistentes de infraestrutura de área de trabalho virtual (VDI)](dlp-configure-endpoints-vdi.md)
- [Solucionar problemas de integração com a proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
