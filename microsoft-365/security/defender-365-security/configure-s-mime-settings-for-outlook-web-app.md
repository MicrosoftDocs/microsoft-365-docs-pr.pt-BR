---
title: Configurar configurações de S/MIME - Exchange Online para Outlook na Web
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Uma breve descrição do que os administradores do Exchange Online precisam fazer para exibir e configurar as configurações S/MIME no Outlook na Web no Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6eacc6a264682474054d0d3546b831039bee9a0c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053687"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Configurar configurações de S/MIME no Exchange Online para Outlook na Web

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Como administrador do Exchange Online, você pode configurar o Outlook na Web (anteriormente conhecido como Outlook Web App) para permitir o envio e recebimento de mensagens protegidas por S/MIME. Use os cmdlets **Get-SmimeConfig** e **Set-SmimeConfig** para exibir e gerenciar esse recurso no PowerShell do Exchange Online. Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig) e [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Considerações sobre o novo Microsoft Edge (baseado em Chromium)

Para usar o S/MIME no Outlook na Web no novo navegador da Web do [Microsoft Edge,](https://www.microsoft.com/windows/microsoft-edge) você (ou outro administrador) deve definir e configurar a política de navegador do Microsoft Edge chamada **ExtensionInstallForcelist** para instalar a extensão do Microsoft S/MIME no novo Microsoft Edge. O valor da política é `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . E observe que a aplicação dessa política requer dispositivos ingressados no domínio ou ingressados no Azure AD, portanto, o uso do S/MIME no novo navegador do Microsoft Edge requer efetivamente dispositivos ingressados no domínio ou ingressados no Azure AD.

Para obter detalhes sobre a **política ExtensionInstallForcelist,** consulte [ExtensionInstallForcelist](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).

Esta etapa é um pré-requisito para usar o novo Microsoft Edge; ele não substitui o controle S/MIME instalado pelos usuários. Os usuários são solicitados a baixar e instalar o controle S/MIME no Outlook na Web durante o primeiro uso do S/MIME. Ou os usuários podem ir proativamente para **S/MIME** em suas configurações do Outlook na Web para obter o link de download do controle.

## <a name="considerations-for-chrome"></a>Considerações sobre o Chrome

Para usar o S/MIME no Outlook na Web no navegador da Web do Google Chrome, você (ou outro administrador) deve definir e configurar a política do Chromium chamada **ExtensionInstallForcelist** para instalar a extensão do Microsoft S/MIME no Chrome. O valor da política é `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . E observe que a aplicação dessa política requer computadores ingressados no domínio, portanto, usar S/MIME no Chrome requer efetivamente computadores ingressados no domínio.

Para obter detalhes sobre a **política ExtensionInstallForcelist,** consulte [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).

Esta etapa é um pré-requisito para usar o Chrome; ele não substitui o controle S/MIME instalado pelos usuários. Os usuários são solicitados a baixar e instalar o controle S/MIME no Outlook na Web durante o primeiro uso do S/MIME. Ou os usuários podem ir proativamente para **S/MIME** em suas configurações do Outlook na Web para obter o link de download do controle.

## <a name="for-more-information"></a>Para saber mais

[S/MIME para assinatura e criptografia de mensagens](s-mime-for-message-signing-and-encryption.md)