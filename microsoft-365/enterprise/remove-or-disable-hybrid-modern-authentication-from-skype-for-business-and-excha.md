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
description: Este artigo explica como remover ou desabilitar a Autenticação Moderna Híbrida do Skype for Business e do Exchange.
ms.openlocfilehash: 70f62b9b2165464837aa1dea0e12854df116efe0
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547091"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Como remover ou desabilitar a autenticação moderna híbrida do Skype for Business e do Exchange

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Se você habilitar a HMA (Autenticação Moderna Híbrida) apenas para achar que ela não é adequada para seu ambiente atual, você pode desabilitar o HMA. Este artigo explica como.
  
## <a name="who-is-this-article-for"></a>Para quem é este artigo?

Se você habilitar a Autenticação Moderna no Skype for Business Online ou no local e/ou No Exchange Online ou local e tiver encontrado que precisa desabilitar o HMA, estas etapas são para você.

> [!IMPORTANT]
> Consulte o artigo " Topologias do[Skype for Business](https://technet.microsoft.com/library/mt803262.aspx)com suporte com Autenticação Moderna " se você estiver no Skype for Business Online ou no local, tiver um HMA de topologia mista e precisar ver as topologias com suporte antes de começar.
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>Como desabilitar a Autenticação Moderna Híbrida (Exchange)

1. **Exchange No local: abra** o Shell de Gerenciamento do Exchange e execute os seguintes comandos: 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange Online**: [Conectar-se ao Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) com o PowerShell Remoto. Execute o seguinte comando para transformar seu sinalizador  *OAuth2ClientProfileEnabled*  como "falso":

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>Como desabilitar a Autenticação Moderna Híbrida (Skype for Business)

1. **Skype for Business local: execute** os seguintes comandos no Shell de Gerenciamento do Skype for Business:

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype for Business Online**: [conectar-se ao Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) com o PowerShell Remoto. Execute o seguinte comando para desabilitar a Autenticação Moderna:

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[Link de volta para a visão geral da Autenticação Moderna](hybrid-modern-auth-overview.md) . 
  

