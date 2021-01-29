---
title: Proteger computadores e Macs windows 10 não-manados
f1.keywords:
- NOCSH
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
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Proteja os dispositivos não-manados ou traga seus próprios dispositivos (BYOD) com o Microsoft 365.
ms.openlocfilehash: 5c27b29b5bb4fb445655e671d8c654ad8e9abc6b
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044379"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>Proteger computadores e Macs windows 10 não-manados

Você pode gerenciar computadores e Macs Com o Windows 10 registrando-os no Microsoft Intune, o que permite garantir que eles estão seguros e saudável antes de acessar os dados em seu ambiente. No entanto, muitas campanhas e pequenas empresas incluem funcionários que trazem seus próprios dispositivos (BYOD), que não serão gerenciados pela organização. Para esses PCs e Macs não gerenciamento, use este artigo para garantir que os recursos mínimos de segurança sejam configurados.

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Proteger um computador que executa o Windows 10 ou um Mac

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365, or a Mac, the Microsoft 365 protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
Se o seu PC ou Mac do Windows 10 não for gerenciado pela sua organização, certifique-se de configurar esses recursos de segurança.

## <a name="windows-10"></a>[Windows 10](#tab/Windows10)

**Ativar a criptografia de dispositivo**<p>

A criptografia de dispositivo está disponível em uma ampla variedade de dispositivos Windows e ajuda a proteger seus dados criptografando-os. Se você ativar a criptografia de dispositivo, somente pessoas autorizadas poderão acessar seu dispositivo e dados. Veja [como ativar a criptografia de dispositivo](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) para obter instruções.

 Se a criptografia de dispositivo não estiver disponível em seu dispositivo, você poderá ativar a criptografia [BitLocker padrão.](https://support.microsoft.com/help/4028713/windows-10-turn-on-device-encryption) (O BitLocker não está disponível no Windows 10 Home Edition.) 

**Proteger seu dispositivo com segurança do Windows**<p>
Se você tiver o Windows 10, obterá a proteção antivírus mais recente com a Segurança do Windows. Quando você inicia o Windows 10 pela primeira vez, a Segurança do Windows está ativa e ajudando ativamente a proteger seu computador, procurando malware (software mal-intencionado), vírus e ameaças à segurança. A Segurança do Windows usa proteção em tempo real para verificar tudo o que você baixa ou executado em seu computador.

O Windows Update baixa atualizações da Segurança do Windows automaticamente para ajudar a manter seu computador seguro e protegido contra ameaças.

Se você tiver uma versão anterior do Windows e estiver usando o Microsoft Security Essentials, é uma boa ideia mudar para a Segurança do Windows. Para obter mais informações, consulte [Ajuda para proteger meu dispositivo com a Segurança do Windows.](https://support.microsoft.com/help/17464/windows-10-help-protect-my-device-with-windows-security)

**Ativar o Firewall do Windows**<p>
Você sempre deve executar o Firewall do Windows mesmo se tiver outro firewall ativado. Desligar o Firewall do Windows pode tornar seu dispositivo (e sua rede, se você tiver um) mais vulnerável a acesso não autorizado. Consulte [Ativar ou desativar o Firewall do Windows para](https://support.microsoft.com/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) obter instruções

## <a name="mac"></a>[Mac](#tab/Mac)

**Usar FileVault para criptografar seu disco Mac**<p>
A criptografia de disco protege os dados quando os dispositivos são perdidos ou roubados. A criptografia de disco completo FileVault ajuda a impedir o acesso não autorizado às informações no disco de inicialização. Consulte [usar FileVault para criptografar o disco de inicialização em seu Mac para](https://support.apple.com/HT204837) obter instruções.

**Proteger seu mac contra malware**<p>
A Microsoft recomenda que você instale e use software antivírus confiável no Mac. Confira o artigo a seguir para ver uma lista de opções: [Melhor Mac antivírus 2019. ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)

Você também pode reduzir o risco de malware usando software apenas de fontes confiáveis. As configurações em Segurança & privacidade permitem que você especifique as fontes de software instaladas em seu Mac. Para obter mais informações, confira [proteger seu Mac contra malware.](https://support.apple.com/kb/PH25087)

**Ativar a proteção de firewall**<p>
Use as configurações de firewall para proteger seu Mac contra contatos indesejados iniciados por outros computadores quando você estiver conectado à Internet ou a uma rede. Sem essa proteção, seu Mac pode estar mais vulnerável a acesso não autorizado. Consulte [o firewall do aplicativo](https://support.apple.com/HT201642) para obter instruções.
