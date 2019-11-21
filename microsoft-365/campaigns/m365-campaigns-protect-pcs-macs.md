---
title: Proteger PCs e Macs não gerenciados do Windows 10
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Proteger contra phishing e outros ataques com o Microsoft 365 para campanhas.
ms.openlocfilehash: 93bb36f115ee5f83e07ac9623c852fec4dbf205f
ms.sourcegitcommit: 7713e777731025c165e9e936198609503ade5665
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2019
ms.locfileid: "38753620"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Proteger PCs e Macs não gerenciados do Windows 10

Você pode gerenciar computadores com o Windows 10 e Macs, registrando-os no Microsoft Intune, o que permite garantir que eles estejam íntegros e seguros antes de acessar dados em seu ambiente. No entanto, muitas campanhas e pequenas empresas incluem funcionários que trazem seus próprios dispositivos (BYOD), que não serão gerenciados pela organização. Para esses PCs e Macs não gerenciados, use este artigo para garantir que os recursos de segurança mínimos sejam configurados. 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 Business username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Proteger um computador que executa o Windows 10 ou um Mac

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365 Business, or a Mac, the Microsoft 365 Business protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Se o seu computador com o Windows 10 ou Mac não for gerenciado pela sua organização, certifique-se de configurar esses recursos de segurança.

## <a name="windows-10tabwindows10"></a>[Windows 10](#tab/Windows10)
**Ativar a criptografia do dispositivo**<p>

A criptografia do dispositivo está disponível em uma ampla variedade de dispositivos Windows e ajuda a proteger seus dados criptografando-os. Se você ativar a criptografia de dispositivo, apenas pessoas autorizadas poderão acessar o dispositivo e os dados. Consulte [ativar a criptografia de dispositivo](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) para obter instruções.

 Se a criptografia do dispositivo não estiver disponível em seu dispositivo, você poderá ativar a [criptografia BitLocker](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) padrão. (O BitLocker não está disponível no Windows 10 Home Edition.) 


**Proteger seu dispositivo com a segurança do Windows**<p>
Se você tiver o Windows 10, obterá a proteção antivírus mais recente com a segurança do Windows. Quando você inicia o Windows 10 pela primeira vez, a segurança do Windows está ativada e ajudando ativamente a proteger seu computador examinando malware (software mal-intencionado), vírus e ameaças de segurança. A segurança do Windows usa a proteção em tempo real para verificar tudo o que você baixa ou executa no seu computador.

O Windows Update baixa as atualizações da segurança do Windows automaticamente para ajudar a manter seu computador seguro e protegê-lo contra ameaças.

Se você tiver uma versão anterior do Windows e estiver usando o Microsoft Security Essentials, é uma boa ideia mudar para a segurança do Windows. Para obter mais informações, consulte [ajudar a proteger meu dispositivo com a segurança do Windows](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).

**Ativar o Firewall do Windows**<p>
Você deve sempre executar o Firewall do Windows mesmo se tiver outro firewall ativado. Desativar o Firewall do Windows pode tornar seu dispositivo (e sua rede, se você tiver um) mais vulnerável a acesso não autorizado. Consulte [Ativar ou desativar o Firewall do Windows](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) para obter instruções

## <a name="mactabmac"></a>[Mac](#tab/Mac)
**Usar o FileVault para criptografar seu disco Mac**<p>
A criptografia de disco protege os dados quando os dispositivos são perdidos ou roubados. FileVault a criptografia de disco completo ajuda a impedir o acesso não autorizado às informações no seu disco de inicialização. Consulte [usar FileVault para criptografar o disco de inicialização no Mac](https://support.apple.com/HT204837) para obter instruções.

**Proteger o Mac contra malware**<p>
A Microsoft recomenda que você instale e use um software antivírus confiável no seu Mac. Consulte o seguinte artigo para obter uma lista de opções: [Best Mac antivirus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).

Você também pode reduzir o risco de malware usando software apenas de fontes confiáveis. As configurações nas preferências de segurança & privacidade permitem que você especifique as fontes do software instalado no seu Mac. Para obter mais informações, consulte [proteger seu Mac contra malware](https://support.apple.com/kb/PH25087).

**Ativar proteção de firewall**<p>
Use as configurações de firewall para proteger seu Mac do contato indesejado iniciado por outros computadores quando você estiver conectado à Internet ou a uma rede. Sem essa proteção, seu Mac pode estar mais vulnerável a acesso não autorizado. Consulte [sobre o Firewall do aplicativo](https://support.apple.com/HT201642) para obter instruções.
