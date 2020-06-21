---
title: Habilitar a Autenticação Moderna do Office 2013 em dispositivos Windows.
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Saiba como definir as chaves do registro para habilitar a autenticação moderna para dispositivos que têm o Microsoft Office 2013 instalado.
ms.openlocfilehash: 8edcedefc04d5018b8b61022c26cbe027f7c24a9
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779960"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Habilitar a Autenticação Moderna do Office 2013 em dispositivos Windows.

Para habilitar a autenticação moderna para qualquer dispositivo com Windows com o Office 2013 instalado, é necessário configurar chaves do Registro específicas.
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Habilitar a autenticação moderna para clientes do Office 2013

> [!NOTE]
> A autenticação moderna já está habilitada para clientes do Office 2016, você não precisa definir chaves do Registro para Office 2016. 
  
To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:
  
|**Chave do Registro**|**Tipo**|**Valor** |
|:-------|:------:|--------:|
|Hkcu\software\microsoft\office\15.0 \common\identity\enableadal com  |REG_DWORD  |1   |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1  |
   
Depois de definir as chaves do registro, você pode definir os aplicativos do Office 2013 para usar a [autenticação multifator (MFA)](set-up-multi-factor-authentication.md) com o Microsoft 365. 
  
If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.
  
## <a name="disable-modern-authentication-on-devices"></a>Desabilitar a autenticação moderna nos dispositivos

Para desabilitar a autenticação moderna em um dispositivo, defina as seguintes chaves do Registro no dispositivo:
  
|**Chave do Registro**|**Tipo**|**Valor**|
|:-------|:------:|--------:|
|Hkcu\software\microsoft\office\15.0 \common\identity\enableadal com |REG_DWORD|,0|
   
## <a name="related-articles"></a>Artigos relacionados
[Entrar no Office 2013 com um segundo método de verificação](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

  

