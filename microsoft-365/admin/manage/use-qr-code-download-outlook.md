---
title: Usar um código QR para entrar nos aplicativos móveis do Outlook
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
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: Saiba como usar um código QR para autenticar e baixar o Outlook Mobile.
ms.openlocfilehash: bc8ab14d3c1c0621e84d0c95ad7448c6c50825d6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914961"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Usar um código QR para entrar nos aplicativos móveis do Outlook

> [!IMPORTANT]
> Esse recurso só está disponível para organizações que tenham a versão direcionada no centro de administração do Microsoft 365. Para ativar a versão direcionada e saber mais sobre como ela funciona, consulte Configurar as opções de versão [Padrão ou Direcionada.](release-options-in-office-365.md) Vamos expandir para mais organizações nas próximas semanas por meio da visualização pública. A visualização pública fornece acesso antecipado aos recursos do Microsoft 365.

Como administrador do Microsoft 365, você pode permitir que seus usuários entrem no Outlook para Android ou aplicativo iOS em seus dispositivos móveis sem precisar inserir seu nome de usuário e senha. Ao digitalizar um código QR, os usuários podem autenticar com segurança e entrar no Outlook mobile.

No Outlook na Web ou em outros aplicativos do Outlook da área de trabalho, os usuários podem ver notificações informando que podem usar o Outlook em seu dispositivo móvel. Essas notificações podem ser gerenciadas pelo administrador usando o Exchange Powershell. Se os usuários optarem por enviar uma mensagem de texto SMS para baixar o aplicativo em seu dispositivo móvel, um código QR aparecerá em seu computador. Eles poderão verificar o código QR para fazer logoff no Outlook em seu telefone ou tablet. Esse código QR é um token de vida curta que só pode ser resgatado uma vez.

> [!NOTE]
> Em alguns casos, os usuários terão que se autenticar no computador para gerar o código QR.

## <a name="use-exchange-powershell"></a>Usar o Exchange PowerShell

Esse recurso não está habilitado por padrão. Para desabilitar esse recurso, siga as etapas abaixo.

1. [Conecte-se ao Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).
2. Usando o PowerShell, você pode desabilitar as notificações informando seus usuários sobre os aplicativos móveis do Outlook. Isso também impedirá que o fluxo de login do código QR seja mostrado.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

Tópicos relacionados

[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)