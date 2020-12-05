---
title: Escolha entre mobilidade básica e segurança e o Intune
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
description: A mobilidade básica e a segurança fazem parte dos planos do Microsoft 365.
ms.openlocfilehash: 75fef5bd70d7b8926d31b80f16952aa996bc625c
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580656"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>Escolha entre mobilidade básica e segurança ou Intune

[O Microsoft Intune](https://docs.microsoft.com/mem/intune/) é um produto autônomo incluído em determinados planos do Microsoft 365, enquanto a mobilidade básica e a segurança fazem parte dos planos do Microsoft 365. 

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>Disponibilidade de mobilidade básica e segurança e do Intune
 
A mobilidade básica e a segurança e o Intune estão incluídos em vários planos, descritos na tabela a seguir.

| Planejar | Mobilidade básica e segurança | Microsoft Intune |
|:-----|:-----|:-----|
|Aplicativos do Microsoft 365|Sim|Não|
|Microsoft 365 Business Basic|Sim|Não|
|Microsoft 365 Business Standard|Sim|Não|
|Office 365 E1 |Sim|Não|
|Office 365 E3 |Sim|Não|
|Office 365 E5 |Sim|Não|
|Microsoft 365 Business Premium |Sim|Sim|
|Microsoft 365 First-3 |Sim|Sim|
|Microsoft 365 Enterprise E3 |Sim|Sim|
|Microsoft 365 Enterprise E5 |Sim|Sim|
|Microsoft 365 Education a1 |Sim|Sim|
|Microsoft 365 Education A3 |Sim|Sim|
|Microsoft 365 Education A5 |Sim|Sim|
|Microsoft Intune |Não|Sim|
|Mobilidade corporativa & segurança E3 |Não|Sim|
|Enterprise Mobility & segurança e5 |Não|Sim|

>[!NOTE]
>Você não pode começar a usar mobilidade básica e segurança se já estiver usando o Microsoft Intune.

 Para obter detalhes, consulte [Microsoft 365 and Office 365 Platform Service Descriptions](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). 

## <a name="differences-in-capabilities"></a>Diferenças de recursos

O Microsoft Intune e a mobilidade básica e segurança interna dão a você a capacidade de gerenciar dispositivos móveis em sua organização, mas há importantes diferenças de capacidade, descritas na tabela a seguir.

>[!NOTE]
>Você pode gerenciar usuários e seus dispositivos móveis usando o Intune e mobilidade básica e segurança na mesma organização de Microsoft 365 Business Standard, *Configurando a mobilidade básica e segurança primeiro e, em seguida, adicionando o Microsoft Intune*. Isso permite que você escolha mobilidade básica e segurança ou a solução mais rica de recursos do Intune. Atribua uma licença do Intune para habilitar os recursos do Intune.

| Área de recurso | Destaques do recurso | Mobilidade básica e segurança | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|Tipos de dispositivo|Gerenciar plataformas de sistema operacional diferentes e variantes do modo de gerenciamento principal. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>Mac OS, iPad OS|
|Conformidade do dispositivo|Definir e gerenciar políticas de segurança, como bloqueio de PIN de nível de dispositivo e detecção de jailbreak. |Limitações no Android 9 e dispositivos posteriores. Veja [detalhes](capabilities.md). |Sim|
|Acesso condicional com base na conformidade do dispositivo |Impedir que dispositivos não compatíveis acessem emails e dados corporativos da nuvem. |Sem suporte no Windows 10.<br/>Limitado para controlar o acesso ao Exchange Online, SharePoint Online e Outlook. |Sim |
|Configuração do dispositivo  |Definir configurações de dispositivo (por exemplo, desabilitar a câmera)|Conjunto limitado de configurações.|Sim|Conformidade do dispositivo|Definir e gerenciar políticas de segurança, como bloqueio de PIN de nível de dispositivo e detecção de jailbreak. |Limitações no Android 9 e dispositivos posteriores. Veja [detalhes](capabilities.md). |Sim|
|Perfis de email  |Provisione um perfil de email nativo no dispositivo. |Sim|Sim|
|Perfis WiFi |Provisionar um perfil WiFi nativo no dispositivo. |Não|Sim|
|Perfis VPN |Provisionar um perfil VPN nativo no dispositivo. |Não|Sim|
|Gerenciamento de aplicativo MDM |Implantar seus aplicativos de linha de negócios internos e repositórios de aplicativos para usuários. |Não|Sim|
|MAM |Certifique-se de que os usuários possam acessar com segurança as informações corporativas usando o Office Mobile e os aplicativos de linha de negócios, ajudando a restringir ações como copiar, cortar, colar e salvar como, apenas para os aplicativos aprovados para dados corporativos. |Não|Sim|
|Navegador gerenciado  |Habilitar a navegação da Web mais segura usando o aplicativo de borda. |Não|Sim|
|Zero-piloto automático de programas de registro de toque) |Registrar grandes números de dispositivos pertencentes à empresa e simplificar a configuração do usuário. |Não|Sim|
|||

Além dos recursos listados na tabela anterior, a mobilidade básica e a segurança e o Intune incluem um conjunto de ações remotas que enviam comandos para dispositivos pela Internet. Por exemplo, você pode remover dados do Office do dispositivo de um funcionário enquanto deixa dados pessoais em vigor (desativação), remover aplicativos do Office do dispositivo de um funcionário (apagar) ou redefinir um dispositivo para suas configurações de fábrica (apagamento completo). 

Mobilidade básica e ações remotas de segurança incluem retirada, apagamento e apagamento completo. Para obter mais informações sobre mobilidade básica e ações de segurança, consulte [recursos de mobilidade básica e segurança](capabilities.md).

Com o Intune, você tem o seguinte conjunto de ações:

-   Redefinição de piloto automático (somente Windows
-  Rotação de chaves do [BitLocker](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Somente no Windows)
-  [Usar apagamento, desativação ou cancelamento manual do dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [Desabilitar a ativação do Loc](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   (somente iOS)
-  [Início recente](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Somente no Windows)
- [Verificação completa](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Somente Windows 10)
- [Localizar dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (somente iOS)
- [Modo perdido](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (somente iOS)- [verificação rápida](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(somente Windows 10)
- [Controle remoto para Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [Bloqueio remoto](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [Renomear dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  [Redefinir](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset) a [reinicialização](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   de senha (somente Windows)
-  Atualizar a inteligência de segurança do Windows Defender (somente Windows)
-  Redefinição de PIN do Windows 10 (somente Windows)
-  [Enviar notificações personalizadas](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)
-  [Sincronizar dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

Para obter mais informações sobre as ações do Intune, consulte a [documentação do Microsoft Intune](https://docs.microsoft.com/mem/intune/).
