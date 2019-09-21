---
title: Configurar as definições S/MIME no Exchange Online para Outlook na Web
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
ms.openlocfilehash: 6e390e377369dc0de73d5e063a6a21fd549c3bef
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073726"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Configurar as definições S/MIME no Exchange Online para Outlook na Web

Como administrador do Exchange Online, você pode configurar o Outlook na Web (anteriormente conhecido como Outlook Web App) para permitir o envio e recebimento de mensagens protegidas por S/MIME. Use os cmdlets **Get-SmimeConfig** e **set-SmimeConfig** para exibir e gerenciar esse recurso no PowerShell do Exchange Online. Para se conectar ao Exchange Online PowerShell, confira [Conectar ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SmimeConfig](http://technet.microsoft.com/library/4b29fa89-0840-4fe9-8885-019fcef2e02b.aspx) e [set-SmimeConfig](http://technet.microsoft.com/library/de357ce0-8143-4c36-8032-026292fc63f0.aspx).

## <a name="considerations-for-chrome"></a>Considerações para o Chrome

Para usar S/MIME no Outlook na Web no navegador Google Chrome, você (ou outro administrador) deve definir e configurar a política do Chromium chamada **ExtensionInstallForcelist** para instalar a extensão S/MIME da Microsoft no Chrome. O valor da política `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`é. E observe que a aplicação dessa política exige computadores associados ao domínio, portanto, usar S/MIME no Chrome requer computadores associados ao domínio.

Para obter detalhes sobre a política **ExtensionInstallForcelist** , consulte [ExtensionInstallForcelist](http://dev.chromium.org/administrators/policy-list-3#ExtensionInstallForcelist).

Esta etapa é um pré-requisito para usar o Chrome; Ele não substitui o controle S/MIME instalado pelos usuários. Os usuários são solicitados a baixar e instalar o controle S/MIME no Outlook na Web durante o primeiro uso de S/MIME. Ou, os usuários podem ir proativamente para o **S/MIME** em suas configurações do Outlook na Web para obter o link de download do controle.

## <a name="for-more-information"></a>Para saber mais

[S/MIME para assinatura e criptografia de mensagens](s-mime-for-message-signing-and-encryption.md)
