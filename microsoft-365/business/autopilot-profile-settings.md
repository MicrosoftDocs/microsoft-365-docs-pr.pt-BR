---
title: Sobre as configurações de perfil do AutoPilot
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Os perfis do AutoPilot ajudam a controlar como o Windows é instalado nos dispositivos do usuário. Os perfis contêm configurações padrão e opcionais, como ignorar a instalação da Cortana.
ms.openlocfilehash: 912a24e3d458986a4bcf7dcf903f80211996aca2
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38321776"
---
# <a name="about-autopilot-profile-settings"></a>Sobre as configurações de perfil do AutoPilot

## <a name="autopilot-profile-settings"></a>Configurações de perfil do AutoPilot

Você pode usar perfis do AutoPilot para controlar como o Windows é instalado nos dispositivos do usuário. Os perfis contêm as configurações a seguir.
  
 **Recursos padrão do AutoPilot (obrigatório) que são definidos automaticamente:**
  
|**Configuração**|**Descrição**|
|:-----|:-----|
|Ignorar o registro de Cortana, OneDrive e OEM  <br/> |Ignora a instalação de aplicativos de consumidor como a Cortana e o OneDrive pessoal. O usuário do dispositivo poderá instalá-los mais tarde, contanto que o usuário seja um administrador local no dispositivo. O registro do fabricante original é ignorado porque o dispositivo será gerenciado pelo Microsoft 365 Business.  <br/> |
|Experiência de entrada com a marca da sua empresa  <br/> |Se sua empresa tiver uma [marca adicionar sua empresa à página de entrada do Office 365](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), o usuário do dispositivo receberá essa experiência ao entrar.  <br/> |
|Registro automático do MDM com contas do AAD configuradas.  <br/> |A identidade do usuário será gerenciada pelo Azure Active Directory e os usuários entrarão no Windows e no Office 365 com suas credenciais de negócios do Microsoft 365.  <br/> |
   
 **Configurações opcionais:**
  
|**Configuração**|**Descrição**|
|:-----|:-----|
|Ignorar as configurações de privacidade (desativado por padrão)  <br/> |Se essa opção estiver definida como **ativada**, o usuário do dispositivo não verá o contrato de licença para o dispositivo e o Windows quando ele se inscrever pela primeira vez.  <br/> |
|Não permitir que o usuário se torne o administrador local  <br/> |Se essa opção estiver definida como **ativada**, o usuário do dispositivo não poderá instalar nenhum aplicativo pessoal, como a Cortana.<br/> |
   
