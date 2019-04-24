---
title: Sobre as configurações de perfil do AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Os perfis do autoPilot ajudam a controlar como o Windows é instalado nos dispositivos do usuário. Os perfis contêm configurações padrão e opcionais, como ignorar a instalação da corTana.
ms.openlocfilehash: d43a15e5f3dc83596b5c23dd0ceb416b24810298
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276932"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="7c368-104">Sobre as configurações de perfil do AutoPilot</span><span class="sxs-lookup"><span data-stu-id="7c368-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="7c368-105">Configurações de perfil do autoPilot</span><span class="sxs-lookup"><span data-stu-id="7c368-105">AutoPilot profile settings</span></span>

<span data-ttu-id="7c368-106">Você pode controlar como o Windows é instalado nos dispositivos de usuário usando os perfis do autoPilot.</span><span class="sxs-lookup"><span data-stu-id="7c368-106">You can control how Windows gets installed on user devices by using the AutoPilot profiles.</span></span> <span data-ttu-id="7c368-107">Os perfis contêm as configurações a seguir.</span><span class="sxs-lookup"><span data-stu-id="7c368-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="7c368-108">**Recursos padrão do autoPilot (obrigatório) que são definidos automaticamente:**</span><span class="sxs-lookup"><span data-stu-id="7c368-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="7c368-109">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="7c368-109">**Setting**</span></span>|<span data-ttu-id="7c368-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="7c368-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7c368-111">Ignorar o registro da corTana, OneDrive e OEM</span><span class="sxs-lookup"><span data-stu-id="7c368-111">Skip Cortana, OneDrive and OEM registration</span></span>  <br/> |<span data-ttu-id="7c368-112">Ignora a instalação de aplicativos de consumidor como a corTana e o OneDrive pessoal.</span><span class="sxs-lookup"><span data-stu-id="7c368-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="7c368-113">O usuário do dispositivo poderá instalá-los mais tarde, contanto que ele seja um administrador local no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7c368-113">The device user can install these later as long as he or she is a local admin on the device.</span></span> <span data-ttu-id="7c368-114">O registro do fabricante original é ignorado porque o dispositivo será gerenciado pelo Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="7c368-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="7c368-115">Experiência de entrada com a marca da sua empresa</span><span class="sxs-lookup"><span data-stu-id="7c368-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="7c368-116">Se sua empresa tiver uma [marca adicionar sua empresa à página de entrada do Office 365](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), o usuário do dispositivo receberá essa experiência ao entrar.</span><span class="sxs-lookup"><span data-stu-id="7c368-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="7c368-117">Registro automático do MDM com contas do AAD configuradas.</span><span class="sxs-lookup"><span data-stu-id="7c368-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="7c368-118">A identidade do usuário será gerenciada pelo Azure Active Directory e os usuários entrarão no Windows e no Office 365 com suas credenciais de negócios do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7c368-118">The user identity will be managed by Azure Active directory, and the users will sign into Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="7c368-119">**Configurações opcionais:**</span><span class="sxs-lookup"><span data-stu-id="7c368-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="7c368-120">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="7c368-120">**Setting**</span></span>|<span data-ttu-id="7c368-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="7c368-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7c368-122">Ignorar as configurações de privacidade (desativado por padrão)</span><span class="sxs-lookup"><span data-stu-id="7c368-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="7c368-123">Se essa opção estiver definida como **ativada**, o usuário do dispositivo não verá o contrato de licença para o dispositivo e o Windows quando ele se inscrever pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="7c368-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="7c368-124">Não permitir que o usuário se torne o administrador local</span><span class="sxs-lookup"><span data-stu-id="7c368-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="7c368-125">Se essa opção estiver definida como **ativada**, o usuário do dispositivo não poderá instalar nenhum aplicativo pessoal, como a Cortana.</span><span class="sxs-lookup"><span data-stu-id="7c368-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span>  <br/> |
   
