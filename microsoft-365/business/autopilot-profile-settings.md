---
title: Sobre as configurações de perfil do AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Perfis de piloto automático ajudarão-lo a controlar como o Windows obtém instalado nos dispositivos do usuário. Os perfis contêm padrão e configurações opcionais, como ignorar Cortana instalação.
ms.openlocfilehash: 5440286f1363780c87ab60514584c4addfeea0b2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864705"
---
# <a name="about-autopilot-profile-settings"></a>Sobre as configurações de perfil do AutoPilot

## <a name="autopilot-profile-settings"></a>Configurações de perfil do piloto automático

Você pode controlar como o Windows obtém instalado nos dispositivos de usuário usando os perfis de piloto automático. Os perfis contêm as configurações a seguir.
  
 **Piloto automático recursos padrão (obrigatório) que são configurados automaticamente:**
  
|**Configuração**|**Descrição**|
|:-----|:-----|
|Ignorar o registro Cortana, OneDrive e OEM  <br/> |Ignora a instalação de aplicativos do consumidor como Cortana e OneDrive pessoal. Usuário do dispositivo pode instalar esses posterior, desde que ele seja um administrador local no dispositivo. O registro original do fabricante é ignorado porque o dispositivo será gerenciado pelas Microsoft 365 Business.  <br/> |
|Inscreva-se na experiência com a marca da sua empresa  <br/> |Se sua empresa tiver um [Add sua empresa branding para Office 365 Sign In da página](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), o usuário do dispositivo receberá essa experiência ao fazer logon.  <br/> |
|MDM inscrição automática com contas AAD configuradas.  <br/> |A identidade do usuário será gerenciada pelo Windows Azure Active directory e os usuários entrará em Windows e o Office 365 com suas credenciais do Microsoft 365 Business.  <br/> |
   
 **Configurações opcionais:**
  
|**Configuração**|**Descrição**|
|:-----|:-----|
|Ignorar as configurações de privacidade (desativado por padrão)  <br/> |Se essa opção estiver definida como **On**, o usuário do dispositivo não verá o contrato de licença para o dispositivo e o Windows quando ele entra pela primeira vez.  <br/> |
|Não permitir que o usuário se torne o administrador local  <br/> |Se essa opção estiver definida como **On**, o usuário do dispositivo não poderão instalar quaisquer aplicativos pessoais, como Cortana.  <br/> |
   
