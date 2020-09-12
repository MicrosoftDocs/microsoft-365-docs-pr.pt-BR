---
title: Como remover ou desabilitar a autenticação moderna híbrida do Skype for Business e do Exchange
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/3/2017
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 5a91b9e3-1508-475b-93e0-710fa5d5cd2d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: Este artigo explica como remover ou desabilitar a autenticação moderna híbrida do Skype for Business e do Exchange.
ms.openlocfilehash: 70f62b9b2165464837aa1dea0e12854df116efe0
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547091"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Como remover ou desabilitar a autenticação moderna híbrida do Skype for Business e do Exchange

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Se você habilitou a autenticação moderna híbrida (HMA) apenas para encontrá-la inadequada ao seu ambiente atual, é possível desabilitar a HMA. Este artigo explica como.
  
## <a name="who-is-this-article-for"></a>Quem é este artigo?

Se você habilitou a autenticação moderna no Skype for Business online ou no local e/ou no Exchange Online ou no local e descobriu que precisa desabilitar a HMA, estas etapas são para você.

> [!IMPORTANT]
> Consulte o artigo "[topologias do Skype for Business com suporte com autenticação moderna](https://technet.microsoft.com/library/mt803262.aspx)" se você estiver no Skype for Business online ou no local, tenha uma HMA de topologia mista e precise examinar as topologias com suporte antes de começar.
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>Como desabilitar a autenticação moderna híbrida (Exchange)

1. **Exchange local**: Abra o Shell de gerenciamento do Exchange e execute os seguintes comandos: 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange Online**: [Conecte-se ao Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) com o PowerShell remoto. Execute o comando a seguir para transformar o sinalizador  *OAuth2ClientProfileEnabled*  como ' false ':

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>Como desabilitar a autenticação moderna híbrida (Skype for Business)

1. **Skype for Business local**: execute os seguintes comandos no Shell de gerenciamento do Skype for Business:

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype for Business online**: [conectar-se ao Skype for Business online](manage-skype-for-business-online-with-microsoft-365-powershell.md) com o PowerShell remoto. Execute o seguinte comando para desabilitar a autenticação moderna:

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[Link de volta para a visão geral da autenticação moderna](hybrid-modern-auth-overview.md) . 
  

