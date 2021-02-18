---
title: Definir configurações de S/MIME - Exchange Online para Outlook na Web
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
description: Uma breve descrição do que os administradores do Exchange Online precisam fazer para exibir e definir as configurações S/MIME no Outlook na Web no Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ccadfc46e42713601b115c18a119e48dcfdcbf4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290028"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Definir configurações de S/MIME no Exchange Online para Outlook na Web

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Como administrador do Exchange Online, você pode configurar o Outlook na Web (anteriormente conhecido como Outlook Web App) para permitir o envio e o recebimento de mensagens protegidas por S/MIME. Use os cmdlets **Get-SmimeConfig** e **Set-SmimeConfig** para exibir e gerenciar esse recurso no PowerShell do Exchange Online. Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) e [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>Considerações para o novo Microsoft Edge (baseado no Chromium)

Para usar S/MIME no Outlook na Web no novo navegador da Web [Microsoft Edge,](https://www.microsoft.com/windows/microsoft-edge) você (ou outro administrador) deve definir e configurar a política de navegador do Microsoft Edge chamada **ExtensionInstallForcelist** para instalar a extensão S/MIME da Microsoft no novo Microsoft Edge. O valor da política é `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . E observe que a aplicação dessa política requer dispositivos ingressados no domínio ou ingressados no Azure AD, portanto, o uso de S/MIME no novo navegador Microsoft Edge requer efetivamente dispositivos ingressados no domínio ou ingressados no Azure AD.

Para obter detalhes sobre a **política ExtensionInstallForcelist,** consulte [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).

Esta etapa é um pré-requisito para usar o novo Microsoft Edge; não substitui o controle S/MIME instalado pelos usuários. Os usuários são solicitados a baixar e instalar o controle S/MIME no Outlook na Web durante seu primeiro uso de S/MIME. Ou os usuários podem ir proativamente para **S/MIME** em suas configurações do Outlook na Web para obter o link de download do controle.

## <a name="considerations-for-chrome"></a>Considerações para o Chrome

Para usar S/MIME no Outlook na Web no navegador da Web Google Chrome, você (ou outro administrador) deve definir e configurar a política do Chromium chamada **ExtensionInstallForcelist** para instalar a extensão Microsoft S/MIME no Chrome. O valor da política é `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` . E observe que a aplicação dessa política requer computadores ingressados no domínio, portanto, usar S/MIME no Chrome efetivamente requer computadores ingressados no domínio.

Para obter detalhes sobre a **política ExtensionInstallForcelist,** consulte [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).

Esta etapa é um pré-requisito para usar o Chrome; não substitui o controle S/MIME instalado pelos usuários. Os usuários são solicitados a baixar e instalar o controle S/MIME no Outlook na Web durante seu primeiro uso de S/MIME. Ou os usuários podem ir proativamente para **S/MIME** em suas configurações do Outlook na Web para obter o link de download do controle.

## <a name="for-more-information"></a>Para obter mais informações

[S/MIME para assinatura e criptografia de mensagens](s-mime-for-message-signing-and-encryption.md)
