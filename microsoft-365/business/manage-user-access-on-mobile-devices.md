---
title: Gerenciar como os usuários acessam documentos do Office em dispositivos móveis
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4OfficeMobile
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Saiba mais sobre as políticas de proteção que permitem que você gerencie como os usuários acessam os aplicativos do Office e os arquivos de trabalho de dispositivos móveis.
ms.openlocfilehash: b2b828cf2e201360f12b8fadcb395e72958230f6
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471058"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a>Gerenciar como os usuários acessam documentos do Office em dispositivos móveis

Este artigo se aplica ao Microsoft 365 Business Premium.

As configurações de política que controlam como os usuários acessam arquivos do Office em dispositivos móveis são **Desativadas** por padrão. Recomendamos que você aceite os valores padrão durante a instalação para criar políticas de aplicativo para Android, iOS e Windows 10 que se apliquem a todos os usuários. Você pode criar mais políticas após concluir a instalação. 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>Configurações que controlam como os usuários acessam arquivos do Office em dispositivos móveis

As configurações a seguir estão disponíveis para gerenciar como os usuários acessam arquivos de trabalho do Office:
  
|||
|:-----|:-----|
|Setting  <br/> |Descrição  <br/> |
|Exigir um PIN ou uma impressão digital para acessar aplicativos do Office  <br/> |Se essa configuração **estiver** 1, os usuários deverão fornecer outra forma de autenticação, além de seu nome de usuário e senha, para que possam usar aplicativos do Office em seus dispositivos móveis.  <br/> |
|Redefinir o PIN quando houver muitas falhas de logon  <br/> |Para impedir que um usuário não autorizado adivinhe um PIN, o PIN será redefinido após determinado número de tentativas incorretas.  <br/> |
|Exigir que os usuários entrem novamente depois que os aplicativos do Office ficarem ociosos  <br/> |Esta configuração determina por quanto tempo um usuário pode ficar ocioso antes de ser solicitado a entrar novamente.  <br/> |
|Negar o acesso aos arquivos de trabalho em dispositivos com jailbreak ou com acesso raiz  <br/> |Os usuários inteligentes podem ter dispositivos com jailbreak ou com acesso raiz. Isso significa que o usuário pode modificar o sistema operacional, o que pode tornar o dispositivo mais suscetível a malware. Os dispositivos são bloqueados quando essa configuração está **Ativada**.  <br/> |
|Não permitir que os usuários copiem conteúdo de aplicativos do Office para aplicativos pessoais  <br/> |Quando a configuração **estiver 1,** o usuário não poderá copiar informações em um arquivo de trabalho para um arquivo pessoal. Se a **configuração** estiver desligada, o usuário poderá copiar informações de um arquivo de trabalho para um aplicativo pessoal ou uma conta pessoal.  <br/> |
   

