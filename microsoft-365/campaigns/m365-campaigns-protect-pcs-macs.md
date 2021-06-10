---
title: Proteja PCs e Macs com Windows 10 não gerenciados
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Proteja dispositivos não triputados ou traga seus próprios dispositivos (BYOD) com Microsoft 365.
ms.openlocfilehash: 430f5446f86c26cb1f0fd1c7f34613cddec473b2
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398248"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Proteja PCs e Macs com Windows 10 não gerenciados

Você pode gerenciar Windows 10 computadores e Macs registrando-os no Microsoft Intune, o que permite garantir que eles são saudáveis e seguros antes de acessar dados em seu ambiente. No entanto, muitas campanhas e pequenas empresas incluem funcionários que trazem seus próprios dispositivos (BYOD), que não serão gerenciados pela organização. Para esses computadores e Macs não gerenciamento, use este artigo para garantir que os recursos mínimos de segurança sejam configurados.

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Proteger um computador executando Windows 10 ou um Mac

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Se o computador Windows 10 ou Mac não for gerenciado pela sua organização, configure esses recursos de segurança.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**Ativar criptografia de dispositivo**<p>

A criptografia de dispositivo está disponível em uma ampla variedade de dispositivos Windows e ajuda a proteger seus dados criptografando-os. Se você ativar a criptografia de dispositivo, somente indivíduos autorizados poderão acessar seus dados e dispositivos. Consulte [ativar a criptografia de dispositivo](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) para obter instruções.

 Se a criptografia de dispositivo não estiver disponível em seu dispositivo, você poderá ativar a criptografia [BitLocker padrão.](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) (BitLocker não está disponível na Windows 10 Home edition.) 

**Proteja seu dispositivo com Segurança do Windows**<p>
Se você tiver Windows 10, você obterá a proteção antivírus mais recente com Segurança do Windows. Quando você inicia o Windows 10 pela primeira vez, o Segurança do Windows está ativa e ativamente ajudando a proteger seu computador, procurando malware (software mal-intencionado), vírus e ameaças à segurança. Segurança do Windows usa proteção em tempo real para verificar tudo o que você baixa ou executado em seu computador.

O Windows Update baixa atualizações da Segurança do Windows automaticamente para ajudar a manter seu computador seguro e protegido contra ameaças.

Se você tiver uma versão anterior do Windows e estiver usando Microsoft Security Essentials, é uma boa ideia mudar para Segurança do Windows. Para obter mais informações, consulte [Help protect my device with Segurança do Windows](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security).

**Ativar Windows Firewall**<p>
Você sempre deve executar Windows Firewall mesmo se tiver outro firewall ativado. Desligar o Windows Firewall pode tornar seu dispositivo (e sua rede, se você tiver um) mais vulnerável a acesso não autorizado. Consulte [Ativar Windows Firewall para](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) obter instruções.

## <a name="mac"></a>[Mac](#tab/Mac)

**Usar FileVault para criptografar seu disco Mac**<p>
A criptografia de disco protege os dados quando os dispositivos são perdidos ou roubados. A criptografia de disco completo FileVault ajuda a impedir o acesso não autorizado às informações no disco de inicialização. Consulte [use FileVault para criptografar o disco de inicialização em seu Mac](https://support.apple.com/HT204837) para obter instruções.

**Proteger seu mac contra malware**<p>
A Microsoft recomenda que você instale e use software antivírus confiável em seu Mac. Consulte o artigo a seguir para ver uma lista de opções: [Melhor Mac antivírus 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/).

Você também pode reduzir o risco de malware usando software apenas de fontes confiáveis. As configurações em Segurança & Privacidade permitem que você especifique as fontes de software instaladas em seu Mac. Para obter mais informações, consulte [protect your Mac from malware](https://support.apple.com/kb/PH25087).

**Ativar a proteção de firewall**<p>
Use configurações de firewall para proteger seu Mac contra contatos indesejados iniciados por outros computadores quando você estiver conectado à Internet ou a uma rede. Sem essa proteção, seu Mac pode ficar mais vulnerável ao acesso não autorizado. Consulte [o firewall do aplicativo](https://support.apple.com/HT201642) para obter instruções.
