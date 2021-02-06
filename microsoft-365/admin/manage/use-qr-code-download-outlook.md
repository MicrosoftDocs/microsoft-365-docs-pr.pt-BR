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
ms.openlocfilehash: b9e433e0c7d3f5f3466924b318e242e5ac29181c
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122367"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Usar um código QR para entrar nos aplicativos móveis do Outlook

> [!IMPORTANT]
> Esse recurso do Microsoft 365 está em visualização pública. A visualização pública fornece acesso antecipado aos recursos do Microsoft 365.

Como administrador do Microsoft 365, você pode permitir que os usuários entrem no Outlook para Android ou no aplicativo iOS em seus dispositivos móveis sem precisar inserir o nome de usuário e a senha. Ao digitalizar um código QR, os usuários podem autenticar com segurança e entrar no Outlook Mobile.

No Outlook na Web ou em outros aplicativos da área de trabalho do Outlook, os usuários podem ver notificações informando que podem usar o Outlook em seus dispositivos móveis. Essas notificações podem ser gerenciadas pelo administrador usando o Exchange Powershell. Se os usuários optarem por enviar uma mensagem de texto SMS para baixar o aplicativo em seus dispositivos móveis, um código QR aparecerá em seus computadores. Eles poderão verificar o código QR para fazer logoff no Outlook em seu telefone ou tablet. Esse código QR é um token de curta duração que só pode ser resgatado uma vez.

> [!NOTE]
> Em alguns casos, os usuários terão que se autenticar outra vez em seus computadores para gerar o código QR.

## <a name="use-exchange-powershell"></a>Usar o Exchange PowerShell

Por padrão, essa experiência está 1.000. Para desabilitar esse recurso, siga as etapas abaixo.

1. [Conecte-se ao Exchange PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)
2. Usando o PowerShell, você pode desabilitar as notificações informando os usuários sobre os aplicativos móveis do Outlook. Isso também impedirá que o fluxo de login do código QR seja mostrado.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

Tópicos relacionados

[Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)
