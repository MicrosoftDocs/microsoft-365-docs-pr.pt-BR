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
description: A Mobilidade Básica e a Segurança fazem parte dos planos Microsoft 365 básicos.
ms.openlocfilehash: b7b1d229e87a313a9567daed87f03452b1925a65
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904259"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Escolha entre Mobilidade Básica e Segurança ou Intune

[Microsoft Intune](/mem/intune/) é um produto autônomo incluído em determinados planos Microsoft 365, enquanto o Basic Mobility and Security faz parte dos planos Microsoft 365 básicos.

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Disponibilidade de Mobilidade Básica e Segurança e Intune

A Mobilidade Básica e a Segurança e o Intune estão incluídos em uma variedade de planos, descritos na tabela a seguir.

| Plano | Mobilidade e Segurança Básica | Microsoft Intune |
|:-----|:-----|:-----|
|Microsoft 365 Apps|Sim|Não|
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
|Enterprise Mobility + Security E5 |Não|Sim|

>[!NOTE]
>Você não pode começar a usar o Basic Mobility and Security se já estiver usando Microsoft Intune.

 Para obter detalhes, [consulte Microsoft 365 e Office 365 de serviço de plataforma.](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) 

## <a name="differences-in-capabilities"></a>Diferenças nos recursos

Microsoft Intune e a Mobilidade Básica e Segurança internas dão a você a capacidade de gerenciar dispositivos móveis em sua organização, mas há diferenças importantes na funcionalidade, descritas na tabela a seguir.

>[!NOTE]
>Você pode gerenciar usuários e seus dispositivos móveis usando o Intune e o Basic Mobility and Security na mesma organização Microsoft 365 Business Standard configurando o *Basic Mobility* and Security primeiro e adicionando Microsoft Intune . Isso permite que você escolha Mobilidade Básica e Segurança ou a solução do Intune mais rica em recursos. Atribua uma licença do Intune para habilitar os recursos do Intune.

| Área de recurso | Destaques de recursos | Mobilidade e Segurança Básica | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Tipos de dispositivo|Gerenciando diferentes plataformas do sistema operacional e variantes de modo de gerenciamento principais. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS, iPad sistema operacional|
|Conformidade do dispositivo|Definir e gerenciar políticas de segurança, como bloqueio de PIN de nível de dispositivo e detecção de jailbreak. |Limitações em dispositivos Android 9 e posteriores. Consulte [detalhes](capabilities.md). |Sim|
|Acesso condicional com base na conformidade do dispositivo |Impedir que dispositivos não compatíveis acessem emails corporativos e dados da nuvem. |Não há suporte no Windows 10.<br/>Limitado ao controle do acesso Exchange Online, SharePoint Online e Outlook. |Sim |
|Configuração do dispositivo  |Configurar configurações de dispositivo (por exemplo, desabilitar a câmera)|Conjunto limitado de configurações.|Sim|
|Conformidade do dispositivo  |Definir e gerenciar políticas de segurança, como bloqueio de PIN de nível de dispositivo e detecção de jailbreak. |Limitações em dispositivos Android 9 e posteriores. Consulte [detalhes](capabilities.md). |Sim|
|Perfis de email  |Provisione um perfil de email nativo no dispositivo. |Sim|Sim|
|Perfis WiFi |Provisione um perfil WiFi nativo no dispositivo. |Não|Sim|
|Perfis VPN |Provisione um perfil VPN nativo no dispositivo. |Não|Sim|
|Gerenciamento de aplicativos móveis  |Implante seus aplicativos internos de linha de negócios e de aplicativos para usuários. |Não|Sim|
|Proteção de aplicativo móvel  |Habilita os usuários a acessar com segurança informações corporativas usando os aplicativos móveis e de linha de negócios que eles conhecem, ao mesmo tempo em que garantem a segurança dos dados, ajudando a restringir ações como copiar, cortar, colar e salvar como, somente para os aplicativos gerenciados aprovados para dados corporativos. Office Funciona mesmo se os dispositivos não estão inscritos no Basic Mobility and Security. Consulte Proteger dados do aplicativo usando políticas de MAM. |Não|Sim|
|Navegador gerenciado  |Habilita a navegação na Web mais segura usando o aplicativo Edge. |Não|Sim|
|Programas de registro de toque zero (AutoPilot) |Registrar um grande número de dispositivos de propriedade corporativa, ao mesmo tempo que simplifica a configuração do usuário. |Não|Sim|
|||

Além dos recursos listados na tabela anterior, a Mobilidade Básica e Segurança e o Intune incluem um conjunto de ações remotas que enviam comandos para dispositivos pela Internet. Por exemplo, você pode remover Office dados do dispositivo de um funcionário enquanto deixa os dados pessoais in-locar (retirar), remover Office aplicativos do dispositivo de um funcionário (apagar) ou redefinir um dispositivo para suas configurações de fábrica (apagar completamente). 

As ações remotas básicas de Mobilidade e Segurança incluem a ressarção, limpeza e limpeza total. Para obter mais informações sobre ações básicas de Mobilidade e Segurança, consulte [recursos de Mobilidade Básica e Segurança.](capabilities.md)

Com o Intune, você tem o seguinte conjunto de ações:

-   Redefinição do piloto automático (Windows somente
-  [Rotação da chave bitlocker](/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Windows somente)
-  [Usar apagar, retirar ou desemrollar manualmente o dispositivo](/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Desabilitar o loc de ativação](/mem/intune/remote-actions/device-activation-lock-disable)   (somente iOS)
-  [Novo início](/mem/intune/remote-actions/device-fresh-start)   (Windows somente)
- [Verificação completa](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Windows 10 somente)
- [Localizar dispositivo](/mem/intune/remote-actions/device-locate)   (somente iOS)
- [Modo perdido](/mem/intune/remote-actions/device-lost-mode)   (somente iOS)- [Verificação rápida](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(Windows 10 somente)
- [Controle remoto para Android](/mem/intune/remote-actions/teamviewer-support)
- [Bloqueio remoto](/mem/intune/remote-actions/device-remote-lock)
- [Renomear dispositivo](/mem/intune/remote-actions/device-rename)
-  [Redefinir a reinicialização](/mem/intune/remote-actions/device-passcode-reset) [da](/mem/intune/remote-actions/device-restart)senha   (Windows somente)
-  Atualizar Windows Defender Inteligência de Segurança (Windows somente)
-  Windows 10 Redefinição de PIN (Windows somente)
-  [Enviar notificações personalizadas](/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad sistema operacional)
-  [Sincronizar dispositivo](/mem/intune/remote-actions/device-sync)

Para obter mais informações sobre as ações do Intune, [consulte Microsoft Intune documentação](/mem/intune/).