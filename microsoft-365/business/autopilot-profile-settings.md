---
title: Sobre as configurações de perfil do AutoPilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Os perfis do AutoPilot ajudam a controlar como o Windows é instalado em dispositivos de usuário. Os perfis contêm configurações padrão e opcionais, como ignorar a instalação da Cortana.
ms.openlocfilehash: 86f8718131f0a0b93e18e65e39e02e7d65aded1a
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578498"
---
# <a name="about-autopilot-profile-settings"></a>Sobre as configurações de perfil do AutoPilot

## <a name="autopilot-profile-settings"></a>Configurações de perfil do AutoPilot

Você pode usar perfis do AutoPilot para controlar como o Windows é instalado em dispositivos de usuário. Os perfis contêm as configurações a seguir.
  
 **Recursos padrão do AutoPilot (necessários) que são definidos automaticamente:**
  
|**Configuração**|**Descrição**|
|:-----|:-----|
|Ignorar o registro da Cortana, do OneDrive e do OEM  <br/> |Ignora a instalação de aplicativos de consumidor como a Cortana e o OneDrive pessoal. O usuário do dispositivo pode instalá-los posteriormente, desde que o usuário seja um administrador local no dispositivo. O registro original do fabricante é ignorado porque o dispositivo será gerenciado pelo Microsoft 365 Business Premium.  <br/> |
|Experiência de login com sua marca da empresa  <br/> |Se sua empresa tiver uma página Adicionar a identidade visual da sua empresa à página De entrada do [Microsoft 365](../admin/setup/customize-sign-in-page.md), o usuário do dispositivo terá essa experiência ao entrar.  <br/> |
|Registro automático do MDM com contas AAD configuradas.  <br/> |A identidade do usuário será gerenciada pelo Azure Active Directory e os usuários entrarão no Windows e no Microsoft 365 com suas credenciais do Microsoft 365 Business Premium.  <br/> |
   
 **Configurações opcionais:**
  
|**Configuração**|**Descrição**|
|:-----|:-----|
|Ignorar configurações de privacidade (Desligado por padrão)  <br/> |Se essa opção estiver definida como **On**, o usuário do dispositivo não verá o contrato de licença do dispositivo e do Windows quando entrar pela primeira vez.  <br/> |
|Não permita que o usuário se torne o administrador local  <br/> |Se essa opção estiver definida como **On**, o usuário do dispositivo não poderá instalar aplicativos pessoais, como a Cortana.<br/> |
