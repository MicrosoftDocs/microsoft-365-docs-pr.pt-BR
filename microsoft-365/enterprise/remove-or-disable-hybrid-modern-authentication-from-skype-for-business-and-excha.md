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
description: Este artigo explica como remover ou desabilitar a Autenticação Moderna Híbrida Skype for Business e Exchange.
ms.openlocfilehash: 9442ef3e19d0835bfd59f27ec425e36fd7dfcf7a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927283"
---
# <a name="removing-or-disabling-hybrid-modern-authentication-from-skype-for-business-and-exchange"></a>Como remover ou desabilitar a autenticação moderna híbrida do Skype for Business e do Exchange

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Se você habilitar a HMA (Autenticação Moderna Híbrida) apenas para descobrir que ela não é adequada para seu ambiente atual, você pode desabilitar o HMA. Este artigo explica como.
  
## <a name="who-is-this-article-for"></a>Who este artigo é para?

Se você habilitar a Autenticação Moderna no Skype for Business Online ou local e/ou Exchange Online ou local e descobriu que precisa desabilitar o HMA, estas etapas são para você.

> [!IMPORTANT]
> Consulte o artigo '[Skype for Business topologias](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)com suporte com Autenticação Moderna ' se você estiver no Skype for Business Online ou local, tenha um HMA de topologia mista e precise ver topologias com suporte antes de começar.
  
## <a name="how-to-disable-hybrid-modern-authentication-exchange"></a>Como desabilitar a Autenticação Moderna Híbrida (Exchange)

1. **Exchange local**: abra o Shell de Gerenciamento Exchange e execute os seguintes comandos: 

```powershell
Set-OrganizationConfig -OAuth2ClientProfileEnabled $false
Set-AuthServer -Identity evoSTS -IsDefaultAuthorizationEndpoint $false
```

2. **Exchange Online**: [Conexão para Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) com o PowerShell Remoto. Execute o seguinte comando para transformar seu sinalizador  *OAuth2ClientProfileEnabled*  como "false":

```powershell    
Set-OrganizationConfig -OAuth2ClientProfileEnabled:$false
```
    
## <a name="how-to-disable-hybrid-modern-authentication-skype-for-business"></a>Como desabilitar a Autenticação Moderna Híbrida (Skype for Business)

1. **Skype for Business local**: Execute os seguintes comandos no Shell de Gerenciamento Skype for Business Gerenciamento:

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity ""
```

2. **Skype for Business Online**: Conexão [para Skype for Business Online](manage-skype-for-business-online-with-microsoft-365-powershell.md) com o PowerShell Remoto. Execute o seguinte comando para desabilitar a Autenticação Moderna:

```powershell    
Set-CsOAuthConfiguration -ClientAdalAuthOverride Disallowed
```

[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md) . 
