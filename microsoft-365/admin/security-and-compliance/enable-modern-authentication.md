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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Saiba como definir as chaves do registro para habilitar a autenticação moderna para dispositivos que têm o Microsoft Office 2013 instalado.
ms.openlocfilehash: f1264affa5be93b19e564a0edea00bfb78f452f1
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237830"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Habilitar a Autenticação Moderna do Office 2013 em dispositivos Windows.

Para habilitar a autenticação moderna para qualquer dispositivo com Windows com o Office 2013 instalado, é necessário configurar chaves do Registro específicas.
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Habilitar a autenticação moderna para clientes do Office 2013

> [!NOTE]
> A autenticação moderna já está habilitada para clientes do Office 2016, você não precisa definir chaves do Registro para Office 2016. 
  
Para habilitar a autenticação moderna para os dispositivos com Windows (por exemplo em laptops e tablets), que têm o Microsoft Office 2013 instalado, você precisa definir as seguintes chaves do Registro. As teclas precisam ser definidas em cada dispositivo que você deseja habilitar para autenticação moderna:
  
|**Chave do Registro**|**Tipo**|**Valor** |
|:-------|:------:|--------:|
|Hkcu\software\microsoft\office\15.0 \common\identity\enableadal com  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
   
Depois que você tiver configurado as chaves do Registro, será possível configurar aplicativos de dispositivos do Office 2013 para usar [autenticação multifator (MFA)](set-up-multi-factor-authentication.md) com o Office 365 
  
Se você estiver conectado no momento a qualquer um dos aplicativos cliente, você precisará sair e entrar novamente para que a alteração entre em vigor. Caso contrário, o MRU e as configurações de roaming estarão indisponíveis até que a identidade de ADAL seja estabelecida.
  
## <a name="disable-modern-authentication-on-devices"></a>Desabilitar a autenticação moderna nos dispositivos

Para desabilitar a autenticação moderna em um dispositivo, defina as seguintes chaves do Registro no dispositivo:
  
|**Chave do Registro**|**Tipo**|**Valor**|
|:-------|:------:|--------:|
|Hkcu\software\microsoft\office\15.0 \common\identity\enableadal com |REG_DWORD|,0|
   
## <a name="related-articles"></a>Artigos relacionados
[Entrar no Office 2013 com um segundo método de verificação](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx)

  

