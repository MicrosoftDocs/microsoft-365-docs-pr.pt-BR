---
title: Gerenciar como os usuários acessam documentos do Office em dispositivos móveis
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Saiba mais sobre as políticas de proteção que podem ajudar a proteger o acesso a aplicativos do Office de dispositivos móveis.
ms.openlocfilehash: cade979635dd5d4a618537d544a7a76ef64a2963
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071521"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="66a2d-103">Gerenciar como os usuários acessam documentos do Office em dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="66a2d-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="66a2d-p101">As configurações de política que controlam como os usuários acessam arquivos do Office em dispositivos móveis são **Desativadas** por padrão. Recomendamos aceitar os valores padrão durante a instalação para criar políticas de aplicativo para Android, iOS e Windows 10 que se apliquem a todos os usuários. Você pode criar mais políticas após concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="66a2d-p101">Policy settings that control how users access Office files from their mobile devices are **Off** by default. We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users. You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="66a2d-107">Configurações que controlam como os usuários acessam arquivos do Office em dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="66a2d-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="66a2d-108">As configurações a seguir estão disponíveis para gerenciar como os usuários acessam arquivos de trabalho do Office:</span><span class="sxs-lookup"><span data-stu-id="66a2d-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="66a2d-109">Setting</span><span class="sxs-lookup"><span data-stu-id="66a2d-109">Setting</span></span>  <br/> |<span data-ttu-id="66a2d-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="66a2d-110">Description</span></span>  <br/> |
|<span data-ttu-id="66a2d-111">Exigir um PIN ou uma impressão digital para acessar aplicativos do Office</span><span class="sxs-lookup"><span data-stu-id="66a2d-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="66a2d-112">Se essa configuração estiver **Ativada**, os usuários precisarão fornecer outra forma de autenticação, além de seu nome de usuário e senha, para poderem usar os aplicativos do Office em seus dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="66a2d-112">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="66a2d-113">Redefinir o PIN quando houver muitas falhas de logon</span><span class="sxs-lookup"><span data-stu-id="66a2d-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="66a2d-114">Para impedir que um usuário não autorizado adivinhe um PIN, o PIN será redefinido após determinado número de tentativas incorretas.</span><span class="sxs-lookup"><span data-stu-id="66a2d-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="66a2d-115">Exigir que os usuários entrem novamente depois que os aplicativos do Office ficarem ociosos</span><span class="sxs-lookup"><span data-stu-id="66a2d-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="66a2d-116">Esta configuração determina quanto tempo o usuário pode ficar ocioso antes de ser solicitado a entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="66a2d-116">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="66a2d-117">Negar o acesso aos arquivos de trabalho em dispositivos com jailbreak ou com acesso raiz</span><span class="sxs-lookup"><span data-stu-id="66a2d-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="66a2d-p102">Os usuários inteligentes podem ter dispositivos com jailbreak ou com acesso raiz. Isso significa que o usuário pode modificar o sistema operacional, deixando o dispositivo mais sujeito a malware. Os dispositivos são bloqueados quando essa configuração está **Ativada**.  </span><span class="sxs-lookup"><span data-stu-id="66a2d-p102">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="66a2d-121">Não permitir que os usuários copiem conteúdo de aplicativos do Office para aplicativos pessoais</span><span class="sxs-lookup"><span data-stu-id="66a2d-121">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="66a2d-122">Quando a configuração está **ativada**, o usuário não pode copiar informações de um arquivo de trabalho para um arquivo pessoal.</span><span class="sxs-lookup"><span data-stu-id="66a2d-122">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="66a2d-123">Se a configuração estiver \*\*\*\* desativada, o usuário pode copiar informações de um arquivo de trabalho para um aplicativo pessoal ou uma conta pessoal.</span><span class="sxs-lookup"><span data-stu-id="66a2d-123">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

