---
title: Gerenciar como os usuários acessam documentos do Office em dispositivos móveis
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Saiba mais sobre políticas de proteção que permitem gerenciar como os usuários acessam Office aplicativos e arquivos de trabalho de dispositivos móveis.
ms.openlocfilehash: a48aa241c9e70cf087da3f1701e859dae7238024
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578378"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="c9667-103">Gerenciar como os usuários acessam documentos do Office em dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="c9667-103">Manage how users access Office documents on mobile devices</span></span>

<span data-ttu-id="c9667-104">Este artigo se aplica a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="c9667-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="c9667-105">As configurações de política que controlam como os usuários acessam arquivos do Office em dispositivos móveis são **Desativadas** por padrão.</span><span class="sxs-lookup"><span data-stu-id="c9667-105">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="c9667-106">Recomendamos que você aceite os valores padrão durante a instalação para criar políticas de aplicativo para Android, iOS e Windows 10 que se aplicam a todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="c9667-106">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="c9667-107">Você pode criar mais políticas após concluir a instalação.</span><span class="sxs-lookup"><span data-stu-id="c9667-107">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="c9667-108">Configurações que controlam como os usuários acessam arquivos do Office em dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="c9667-108">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="c9667-109">As configurações a seguir estão disponíveis para gerenciar como os usuários acessam arquivos de trabalho do Office:</span><span class="sxs-lookup"><span data-stu-id="c9667-109">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c9667-110">Configuração</span><span class="sxs-lookup"><span data-stu-id="c9667-110">Setting</span></span>  <br/> |<span data-ttu-id="c9667-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="c9667-111">Description</span></span>  <br/> |
|<span data-ttu-id="c9667-112">Exigir um PIN ou uma impressão digital para acessar aplicativos do Office</span><span class="sxs-lookup"><span data-stu-id="c9667-112">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="c9667-113">Se essa configuração for **On**, os usuários devem fornecer outra forma de autenticação, além de seu nome de usuário e senha, para que possam usar Office aplicativos em seu dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="c9667-113">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="c9667-114">Redefinir o PIN quando houver muitas falhas de logon</span><span class="sxs-lookup"><span data-stu-id="c9667-114">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="c9667-115">Para impedir que um usuário não autorizado adivinhe um PIN, o PIN será redefinido após determinado número de tentativas incorretas.</span><span class="sxs-lookup"><span data-stu-id="c9667-115">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="c9667-116">Exigir que os usuários entrem novamente depois que os aplicativos do Office ficarem ociosos</span><span class="sxs-lookup"><span data-stu-id="c9667-116">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="c9667-117">Essa configuração determina por quanto tempo um usuário pode ficar ocioso antes de ser solicitado a entrar novamente.</span><span class="sxs-lookup"><span data-stu-id="c9667-117">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="c9667-118">Negar o acesso aos arquivos de trabalho em dispositivos com jailbreak ou com acesso raiz</span><span class="sxs-lookup"><span data-stu-id="c9667-118">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="c9667-119">Os usuários inteligentes podem ter dispositivos com jailbreak ou com acesso raiz.</span><span class="sxs-lookup"><span data-stu-id="c9667-119">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="c9667-120">Isso significa que o usuário pode modificar o sistema operacional, o que pode tornar o dispositivo mais suscetível a malware.</span><span class="sxs-lookup"><span data-stu-id="c9667-120">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="c9667-121">Os dispositivos são bloqueados quando essa configuração está **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="c9667-121">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="c9667-122">Não permita que os usuários copiem conteúdo de aplicativos Office aplicativos pessoais</span><span class="sxs-lookup"><span data-stu-id="c9667-122">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="c9667-123">Quando a configuração estiver **Em**, o usuário não poderá copiar informações em um arquivo de trabalho para um arquivo pessoal.</span><span class="sxs-lookup"><span data-stu-id="c9667-123">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="c9667-124">Se a configuração for **Off**, o usuário poderá copiar informações de um arquivo de trabalho para um aplicativo pessoal ou conta pessoal.</span><span class="sxs-lookup"><span data-stu-id="c9667-124">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

