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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Saiba mais sobre as políticas de proteção que permitem gerenciar como os usuários acessam aplicativos do Office e arquivos de trabalho de dispositivos móveis.
ms.openlocfilehash: 870706103a6c05e2e193c80f7a586eab529bb1e7
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561491"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="2c67b-103">Gerenciar como os usuários acessam documentos do Office em dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="2c67b-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="2c67b-104">As configurações de política que controlam como os usuários acessam arquivos do Office em dispositivos móveis são **Desativadas** por padrão.</span><span class="sxs-lookup"><span data-stu-id="2c67b-104">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="2c67b-105">Recomendamos que você aceite os valores padrão durante a instalação para criar políticas de aplicativo para Android, iOS e Windows 10 que se apliquem a todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="2c67b-105">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="2c67b-106">Você pode criar mais políticas após concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="2c67b-106">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="2c67b-107">Configurações que controlam como os usuários acessam arquivos do Office em dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="2c67b-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="2c67b-108">As configurações a seguir estão disponíveis para gerenciar como os usuários acessam arquivos de trabalho do Office:</span><span class="sxs-lookup"><span data-stu-id="2c67b-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2c67b-109">Configuração</span><span class="sxs-lookup"><span data-stu-id="2c67b-109">Setting</span></span>  <br/> |<span data-ttu-id="2c67b-110">Descrição</span><span class="sxs-lookup"><span data-stu-id="2c67b-110">Description</span></span>  <br/> |
|<span data-ttu-id="2c67b-111">Exigir um PIN ou uma impressão digital para acessar aplicativos do Office</span><span class="sxs-lookup"><span data-stu-id="2c67b-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="2c67b-112">Se essa configuração estiver **ativada**, os usuários devem fornecer outra forma de autenticação, além de seu nome de usuário e senha, antes de poderem usar os aplicativos do Office em seus dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="2c67b-112">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="2c67b-113">Redefinir o PIN quando houver muitas falhas de logon</span><span class="sxs-lookup"><span data-stu-id="2c67b-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="2c67b-114">Para impedir que um usuário não autorizado adivinhe um PIN, o PIN será redefinido após determinado número de tentativas incorretas.</span><span class="sxs-lookup"><span data-stu-id="2c67b-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="2c67b-115">Exigir que os usuários entrem novamente depois que os aplicativos do Office ficarem ociosos</span><span class="sxs-lookup"><span data-stu-id="2c67b-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="2c67b-116">Essa configuração determina quanto tempo um usuário pode ficar ocioso antes que seja solicitado a entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="2c67b-116">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="2c67b-117">Negar o acesso aos arquivos de trabalho em dispositivos com jailbreak ou com acesso raiz</span><span class="sxs-lookup"><span data-stu-id="2c67b-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="2c67b-118">Os usuários inteligentes podem ter dispositivos com jailbreak ou com acesso raiz.</span><span class="sxs-lookup"><span data-stu-id="2c67b-118">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="2c67b-119">Isso significa que o usuário pode modificar o sistema operacional, o que pode tornar o dispositivo mais suscetível a malware.</span><span class="sxs-lookup"><span data-stu-id="2c67b-119">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="2c67b-120">Os dispositivos são bloqueados quando essa configuração está **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="2c67b-120">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="2c67b-121">Não permitir que os usuários copiem conteúdo de aplicativos do Office para aplicativos pessoais</span><span class="sxs-lookup"><span data-stu-id="2c67b-121">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="2c67b-122">Quando a configuração está **ativada**, o usuário não pode copiar informações de um arquivo de trabalho para um arquivo pessoal.</span><span class="sxs-lookup"><span data-stu-id="2c67b-122">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="2c67b-123">Se a configuração estiver **desativada**, o usuário pode copiar informações de um arquivo de trabalho para um aplicativo pessoal ou uma conta pessoal.</span><span class="sxs-lookup"><span data-stu-id="2c67b-123">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

