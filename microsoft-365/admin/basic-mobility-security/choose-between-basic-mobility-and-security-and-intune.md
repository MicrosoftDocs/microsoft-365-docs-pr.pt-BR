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
ms.openlocfilehash: df52d500c945275b62170ab16260f0c019340f73
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429921"
---
# <a name="choose-between-basic-mobility-and-security-and-intune"></a>Escolha entre mobilidade básica e segurança e o Intune

O Microsoft Intune é um produto autônomo incluído em determinados planos do Microsoft 365, enquanto a mobilidade básica & segurança faz parte dos planos do Microsoft 365. Ambos estão incluídos em vários planos, descritos na tabela a seguir.

|**Planejar**|**Mobilidade básica e segurança**|**Microsoft Intune**|
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
|Microsoft 365 Eductation a1 |Sim|Sim|
|Microsoft 365 Education A3 |Sim|Sim|
|Microsoft 365 Education A5 |Sim|Sim|
|Microsoft Intune |Não|Sim|
|Mobilidade corporativa & segurança E3 |Não|Sim|
|Enterprise Mobility & segurança e5 |Não|Sim|

>[!NOTE]
>Você não pode começar a usar mobilidade básica e segurança se já estiver usando o Microsoft Intune.

## <a name="differences-in-capabilities"></a>Diferenças de recursos

O Microsoft Intune e a mobilidade básica e segurança interna dão a você a capacidade de gerenciar dispositivos móveis em sua organização, mas há importantes diferenças de capacidade, descritas na tabela a seguir.

>[!NOTE]
>Você pode gerenciar usuários e seus dispositivos móveis usando o Intune e mobilidade básica e segurança na mesma organização de Microsoft 365 Business Standard, configurando a mobilidade básica e segurança primeiro e, em seguida, adicionando o Microsoft Intune. Isso permite que você escolha se você gerencia os dispositivos de um usuário com mobilidade básica e segurança ou a solução mais rica de recursos do Intune. No modo, a atribuição de licença determina a qual serviço o dispositivo está inscrito. Atribua uma licença do Intune para habilitar os recursos somente do Intune.

|**Área de recursos**|**Destaques do recurso**|**Mobilidade básica e segurança**|**Microsoft Intune**|
|:-----|:-----|:-----|:-----|
|Tipos de dispositivo|Diferentes plataformas de so e variantes do modo de gerenciamento principal. |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>Mac OS<br/>sistema operacional iPad|
|Conformidade do dispositivo|Definir e gerenciar políticas de segurança, como bloqueio de PIN de nível de dispositivo e detecção de jailbreak. |Limitações no Android 9 e dispositivos posteriores. Para obter detalhes, consulte [recursos de mobilidade básica e segurança](capabilities.md).|Sim|
|Acesso condicional com base na conformidade do dispositivo |Impedir que dispositivos não compatíveis acessem emails e dados corporativos da nuvem. |– Sem suporte no Windows 10.<br/>– Limitado para controlar o acesso ao Exchange Online, SharePoint Online e serviços do Outlook. |Não|
|Configuração do dispositivo  |Definir configurações de dispositivo (por exemplo, desabilitar a câmera). |Conjunto limitado de configurações.Para obter detalhes, consulte [recursos de mobilidade básica e segurança](capabilities.md). |Sim|
|Ações remotas  |Enviar comandos para dispositivos pela Internet. Por exemplo, remova os dados do Office do dispositivo de um funcionário enquanto deixa dados pessoais em vigor (desativação). |Desativar<br/>Revelar<br/>Excluir|– Redefinição de piloto automático (somente Windows)<br/>- Rotação de chaves do [BitLocker](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Somente no Windows)<br/>- [Exclui](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)<br/>- [Desabilitar a ativação do Loc](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   (somente iOS)<br/>- [Início recente](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Somente no Windows)<br/>- [Verificação completa](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Somente Windows 10)<br/>- [Localizar dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (somente iOS)<br/>- [Modo perdido](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (somente iOS)<br/>- [Verificação rápida](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(somente Windows 10)<br/>- [Controle remoto para Android](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)<br/>- [Bloqueio remoto](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)<br/>- [Renomear dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)<br/>- [Redefinir senha](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset)<br/>- [Reiniciar](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)   (Somente no Windows)<br/>- [Ative](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#retire)<br/>– Atualizar a inteligência de segurança do Windows Defender (somente Windows)<br/>– Redefinição de PIN do Windows 10 (somente Windows)<br/>- [Revelar](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#wipe)<br/>- [Enviar notificações personalizadas](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)<br/>- [Sincronizar dispositivo](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)|
|Perfis de email  |Provisione um perfil de email nativo no dispositivo. |Sim|Sim|
|Perfis WIFI |Provisionar um perfil WIFI nativo no dispositivo. |Não|Sim|
|Perfis VPN |Provisionar um perfil VPN nativo no dispositivo. |Não|Sim|
|Gerenciamento de aplicativo MDM  |Implantar seus aplicativos de linha de negócios internos e repositórios de aplicativos para usuários. |Não|Sim|
|Proteção de aplicativos móveis  |Permita que seus usuários acessem com segurança as informações corporativas usando o Office Mobile e os aplicativos de linha de negócios que eles conhecem, ao mesmo tempo em que garantem a segurança de dados, ajudando a restringir ações como copiar, recortar, colar e salvar como, somente para os aplicativos gerenciados aprovados para dados corporativos. Funciona mesmo que os dispositivos não estejam registrados no MDM. Consulte proteger dados de aplicativo usando políticas MAM. |Não|Sim|
|Navegador gerenciado  |Habilitar a navegação da Web mais segura usando o aplicativo de borda. |Não|Sim|
|Programas de registro de toque zero |Registrar grandes números de dispositivos de propriedade corporativa e simplificar a configuração do usuário. |Não|Sim|
