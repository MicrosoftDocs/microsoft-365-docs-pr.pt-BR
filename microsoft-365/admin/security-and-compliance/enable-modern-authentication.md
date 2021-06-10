---
title: Habilitar a Autenticação Moderna do Office 2013 em dispositivos Windows.
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Aprenda a definir chaves do Registro para habilitar a autenticação moderna para dispositivos que Microsoft Office 2013 instalados.
ms.openlocfilehash: 917ecd5c668ea43b0627ba2361f951ebc5e19725
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635685"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Habilitar a Autenticação Moderna do Office 2013 em dispositivos Windows.

Para habilitar a autenticação moderna para qualquer dispositivo com Windows com o Office 2013 instalado, é necessário configurar chaves do Registro específicas.
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Habilitar a autenticação moderna para clientes do Office 2013

> [!NOTE]
> A autenticação moderna já está habilitada para clientes do Office 2016, você não precisa definir chaves do Registro para Office 2016. 
  
Para habilitar a autenticação moderna para os dispositivos com Windows (por exemplo em laptops e tablets), que têm o Microsoft Office 2013 instalado, você precisa definir as seguintes chaves do Registro. As teclas precisam ser definidas em cada dispositivo que você deseja habilitar para autenticação moderna:
  
|**Chave do Registro**|**Tipo**|**Valor** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
   
Depois de definir as chaves do Registro, você pode definir Office aplicativos de dispositivos 2013 para usar a [autenticação multifator (MFA)](set-up-multi-factor-authentication.md) com Microsoft 365. 
  
Se você estiver conectado no momento a qualquer um dos aplicativos cliente, você precisará sair e entrar novamente para que a alteração entre em vigor. Caso contrário, o MRU e as configurações de roaming estarão indisponíveis até que a identidade de ADAL seja estabelecida.
  
## <a name="disable-modern-authentication-on-devices"></a>Desabilitar a autenticação moderna nos dispositivos

Para desabilitar a autenticação moderna em um dispositivo, defina as seguintes chaves do Registro no dispositivo:
  
|**Chave do Registro**|**Tipo**|**Valor**|
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL |REG_DWORD|0|
   
## <a name="related-content"></a>Conteúdo relacionado

[Entre no Office 2013 com um segundo método de verificação](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb) (artigo)\
Outlook solicita senha e [não usa Autenticação](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled) Moderna para se conectar ao Office 365 (artigo)

