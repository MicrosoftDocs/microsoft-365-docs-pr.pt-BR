---
title: Configurar as definições S/MIME no Exchange Online para Outlook na Web
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Uma breve descrição do que os administradores do Exchange Online precisam fazer para exibir e configurar as configurações S/MIME no Outlook na Web no Exchange Online.
ms.openlocfilehash: 354b247c2b0e0e610e6cb0626f4a404b582db717
ms.sourcegitcommit: c2a36b16e354e20db5fd6275175ca856eae55bfc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "41960317"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Configurar as definições S/MIME no Exchange Online para Outlook na Web

Como administrador do Exchange Online, você pode configurar o Outlook na Web (anteriormente conhecido como Outlook Web App) para permitir o envio e recebimento de mensagens protegidas por S/MIME. Use os cmdlets **Get-SmimeConfig** e **set-SmimeConfig** para exibir e gerenciar esse recurso no PowerShell do Exchange Online. Para se conectar ao Exchange Online PowerShell, confira [Conectar ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig) e [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Considerações para o novo Microsoft Edge (baseado em Chromium)

Para usar S/MIME no Outlook na Web no novo navegador da Web do [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) , você (ou outro administrador) deve definir e configurar a política de navegador do Microsoft Edge chamada **ExtensionInstallForcelist** para instalar a extensão S/MIME da Microsoft em novo Microsoft Edge. O valor da política `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`é. E observe que a aplicação dessa política requer computadores associados a um domínio, portanto, usar S/MIME no novo navegador do Microsoft Edge requer efetivamente computadores associados ao domínio.

Para obter detalhes sobre a política **ExtensionInstallForcelist** , consulte [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).

Esta etapa é um pré-requisito para usar o novo Microsoft Edge; Ele não substitui o controle S/MIME instalado pelos usuários. Os usuários são solicitados a baixar e instalar o controle S/MIME no Outlook na Web durante o primeiro uso de S/MIME. Ou, os usuários podem ir proativamente para o **S/MIME** em suas configurações do Outlook na Web para obter o link de download do controle.

## <a name="considerations-for-chrome"></a>Considerações para o Chrome

Para usar S/MIME no Outlook na Web no navegador Google Chrome, você (ou outro administrador) deve definir e configurar a política do Chromium chamada **ExtensionInstallForcelist** para instalar a extensão S/MIME da Microsoft no Chrome. O valor da política `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`é. E observe que a aplicação dessa política exige computadores associados ao domínio, portanto, usar S/MIME no Chrome requer computadores associados ao domínio.

Para obter detalhes sobre a política **ExtensionInstallForcelist** , consulte [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).

Esta etapa é um pré-requisito para usar o Chrome; Ele não substitui o controle S/MIME instalado pelos usuários. Os usuários são solicitados a baixar e instalar o controle S/MIME no Outlook na Web durante o primeiro uso de S/MIME. Ou, os usuários podem ir proativamente para o **S/MIME** em suas configurações do Outlook na Web para obter o link de download do controle.

## <a name="for-more-information"></a>Para saber mais

[S/MIME para assinatura e criptografia de mensagens](s-mime-for-message-signing-and-encryption.md)
