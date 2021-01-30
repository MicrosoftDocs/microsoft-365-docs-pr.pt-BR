---
title: Escolha entre Mobilidade Básica e Segurança e Intune
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: A Mobilidade Básica e a Segurança fazem parte dos planos do Microsoft 365.
ms.openlocfilehash: ec3ffa8879bf14ab3116bbbbf5cf2a1a3fd7c6e6
ms.sourcegitcommit: ea8a096df5acedecdce1780969f2b189c3fadf73
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50053796"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Escolher entre Mobilidade Básica e Segurança ou Intune

[O Microsoft Intune](https://docs.microsoft.com/mem/intune/) é um produto autônomo incluído em determinados planos do Microsoft 365, enquanto o Basic Mobility and Security faz parte dos planos do Microsoft 365.

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Disponibilidade de Mobilidade Básica e Segurança e Intune

Mobilidade Básica e Segurança e Intune estão incluídos em uma variedade de planos, descritos na tabela a seguir.

| Planejar | Mobilidade e Segurança Básica | Microsoft Intune |
|:-----|:-----|:-----|
|Aplicativos do Microsoft 365|Sim|Não|
|Microsoft 365 Business Basic|Sim|Não|
|Microsoft 365 Business Standard|Sim|Não|
|Office 365 E1 |Sim|Não|
|Office 365 E3 |Sim|Não|
|Office 365 E5 |Sim|Não|
|Microsoft 365 Business Premium |Sim|Sim|
|Microsoft 365 Firstline 3 |Sim|Sim|
|Microsoft 365 Enterprise E3 |Sim|Sim|
|Microsoft 365 Enterprise E5 |Sim|Sim|
|Microsoft 365 Education A1 |Sim|Sim|
|Microsoft 365 Education A3 |Sim|Sim|
|Microsoft 365 Education A5 |Sim|Sim|
|Microsoft Intune |Não|Sim|
|Enterprise Mobility & Security E3 |Não|Sim|
|Enterprise Mobility & Security E5 |Não|Sim|

>[!NOTE]
>Você não pode começar a usar a Mobilidade Básica e Segurança se já estiver usando o Microsoft Intune.

 Para obter detalhes, confira as descrições dos serviços da plataforma [Microsoft 365 e Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) 

## <a name="differences-in-capabilities"></a>Diferenças em recursos

O Microsoft Intune e a Mobilidade Básica e a Segurança básicas permitem gerenciar dispositivos móveis em sua organização, mas há diferenças importantes na funcionalidade, descritas na tabela a seguir.

>[!NOTE]
>Você pode gerenciar usuários e seus dispositivos móveis usando o Intune e o Basic Mobility and Security na mesma organização do Microsoft 365 Business Standard configurando o Basic Mobility and Security primeiro e, em seguida, adicionando *o Microsoft Intune.* Isso permite que você escolha Mobilidade Básica e Segurança ou a solução mais rica em recursos do Intune. Atribua uma licença do Intune para habilitar os recursos do Intune.

| Área de recurso | Destaques de recursos | Mobilidade e Segurança Básica | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Tipos de dispositivo|Gerenciando diferentes plataformas do sistema operacional e variantes de modo de gerenciamento principais. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS, iPad OS|
|Conformidade do dispositivo|Definir e gerenciar políticas de segurança, como bloqueio de PIN no nível do dispositivo e detecção de jailbreak. |Limitações no Android 9 e em dispositivos posteriores. Veja [detalhes.](capabilities.md) |Sim|
|Acesso condicional com base na conformidade do dispositivo |Impedir que dispositivos não compatíveis acessem emails corporativos e dados da nuvem. |Não é suportado no Windows 10.<br/>Limitado a controlar o acesso ao Exchange Online, Ao SharePoint Online e ao Outlook. |Sim |
|Configuração do dispositivo  |Definir configurações do dispositivo (por exemplo, desabilitar a câmera)|Conjunto limitado de configurações.|Sim|
|Conformidade do dispositivo  |Definir e gerenciar políticas de segurança, como bloqueio de PIN no nível do dispositivo e detecção de jailbreak. |Limitações no Android 9 e em dispositivos posteriores. Veja [detalhes.](capabilities.md) |Sim|
|Perfis de email  |Provisione um perfil de email nativo no dispositivo. |Sim|Sim|
|Perfis WiFi |Provisione um perfil de WiFi nativo no dispositivo. |Não|Sim|
|Perfis VPN |Provisione um perfil vpn nativo no dispositivo. |Não|Sim|
|Gerenciamento básico de aplicativos de Mobilidade e Segurança  |Implante seus aplicativos de linha de negócios internos e de lojas de aplicativos para os usuários. |Não|Sim|
|Proteção de aplicativo móvel  |Permita que os usuários acessem com segurança as informações corporativas usando os aplicativos móveis e de linha de negócios do Office que eles conhecem, garantindo a segurança dos dados, ajudando a restringir ações como copiar, recortar, colar e salvar como, apenas para os aplicativos gerenciados aprovados para dados corporativos. Funciona mesmo se os dispositivos não estão inscritos no Basic Mobility and Security. Consulte Proteger dados de aplicativo usando políticas de MAM. |Não|Sim|
|Navegador gerenciado  |Habilita a navegação na Web mais segura usando o aplicativo Edge. |Não|Sim|
|Programas de registro zero por toque autopilot) |Registrar um grande número de dispositivos de propriedade corporativa, simplificando a configuração do usuário. |Não|Sim|
|||

Além dos recursos listados na tabela anterior, a Mobilidade Básica e Segurança e o Intune incluem um conjunto de ações remotas que enviam comandos para dispositivos pela Internet. Por exemplo, você pode remover dados do Office do dispositivo de um funcionário enquanto deixa os dados pessoais no lugar (retirar), remover os aplicativos do Office do dispositivo de um funcionário (apagar) ou redefinir um dispositivo para suas configurações de fábrica (apagaamento completo). 

As ações remotas básicas de Mobilidade e Segurança incluem a reter, apagar e apagar completamente. Para obter mais informações sobre ações básicas de mobilidade e segurança, consulte [as funcionalidades de Mobilidade e Segurança Básica.](capabilities.md)

Com o Intune, você tem o seguinte conjunto de ações:

-   Redefinição do Autopilot (somente Windows
-  [Rotação da chave do](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   Bitlocker (Somente Windows)
-  [Usar apagar, retirar ou desemrollar manualmente o dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Desabilitar loc de ativação](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   (somente iOS)
-  [Novo começo](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Somente Windows)
- [Verificação completa](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Somente Windows 10)
- [Localizar dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (somente iOS)
- [Modo perdido](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (somente iOS)- [Verificação rápida](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(somente Windows 10)
- [Controle remoto para Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [Bloqueio remoto](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [Renomear dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  [Redefinir a senha](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset) [reiniciar](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (somente Windows)
-  Atualizar o Windows Defender Security Intelligence (somente Windows)
-  Redefinição de PIN do Windows 10 (somente Windows)
-  [Enviar notificações personalizadas](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)
-  [Sincronizar dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

Para obter mais informações sobre ações do Intune, consulte a [documentação do Microsoft Intune.](https://docs.microsoft.com/mem/intune/)
