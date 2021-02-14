---
title: Sobre as configurações de perfil do AutoPilot
f1.keywords:
- NOCSH
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Os perfis do AutoPilot ajudam a controlar como o Windows é instalado em dispositivos do usuário. Os perfis contêm configurações padrão e opcionais, como ignorar a instalação da Cortana.
ms.openlocfilehash: 100de5e9548f901008d3ae154ac5a237ef265ffb
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401025"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="406c2-104">Sobre as configurações de perfil do AutoPilot</span><span class="sxs-lookup"><span data-stu-id="406c2-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="406c2-105">Configurações de perfil do AutoPilot</span><span class="sxs-lookup"><span data-stu-id="406c2-105">AutoPilot profile settings</span></span>

<span data-ttu-id="406c2-106">Você pode usar perfis do AutoPilot para controlar como o Windows é instalado em dispositivos do usuário.</span><span class="sxs-lookup"><span data-stu-id="406c2-106">You can use AutoPilot profiles to control how Windows is installed on user devices.</span></span> <span data-ttu-id="406c2-107">Os perfis contêm as configurações a seguir.</span><span class="sxs-lookup"><span data-stu-id="406c2-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="406c2-108">**Recursos padrão do AutoPilot (obrigatórios) que são definidos automaticamente:**</span><span class="sxs-lookup"><span data-stu-id="406c2-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="406c2-109">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="406c2-109">**Setting**</span></span>|<span data-ttu-id="406c2-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="406c2-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="406c2-111">Ignorar o registro da Cortana, do OneDrive e do OEM</span><span class="sxs-lookup"><span data-stu-id="406c2-111">Skip Cortana, OneDrive, and OEM registration</span></span>  <br/> |<span data-ttu-id="406c2-112">Ignora a instalação de aplicativos de consumidor, como a Cortana e o OneDrive pessoal.</span><span class="sxs-lookup"><span data-stu-id="406c2-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="406c2-113">O usuário do dispositivo pode instalá-los mais tarde, desde que o usuário seja um administrador local no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="406c2-113">The device user can install these later as long as the user is a local admin on the device.</span></span> <span data-ttu-id="406c2-114">O registro do fabricante original é ignorado porque o dispositivo será gerenciado pelo Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="406c2-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="406c2-115">Experiência de login com a marca da empresa</span><span class="sxs-lookup"><span data-stu-id="406c2-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="406c2-116">Se sua empresa tiver uma identidade visual Adicionar sua empresa à página de entrada do [Microsoft 365,](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page)o usuário do dispositivo receberá essa experiência ao entrar.</span><span class="sxs-lookup"><span data-stu-id="406c2-116">If your company has a [Add your company branding to Microsoft 365 Sign In page](https://docs.microsoft.com/microsoft-365/admin/setup/customize-sign-in-page), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="406c2-117">Registro automático do MDM com contas configuradas do AAD.</span><span class="sxs-lookup"><span data-stu-id="406c2-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="406c2-118">A identidade do usuário será gerenciada pelo Azure Active Directory e os usuários entrarão no Windows e no Microsoft 365 com suas credenciais do Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="406c2-118">The user identity will be managed by Azure Active Directory, and users will sign in to Windows and Microsoft 365 with their Microsoft 365 Business Premium credentials.</span></span>  <br/> |
   
 <span data-ttu-id="406c2-119">**Configurações opcionais:**</span><span class="sxs-lookup"><span data-stu-id="406c2-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="406c2-120">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="406c2-120">**Setting**</span></span>|<span data-ttu-id="406c2-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="406c2-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="406c2-122">Ignorar configurações de privacidade (Desligado por padrão)</span><span class="sxs-lookup"><span data-stu-id="406c2-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="406c2-123">Se essa opção estiver definida como **1,** o usuário do dispositivo não verá o contrato de licença do dispositivo e do Windows quando entrar pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="406c2-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="406c2-124">Não permitir que o usuário se torne o administrador local</span><span class="sxs-lookup"><span data-stu-id="406c2-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="406c2-125">Se essa opção estiver definida como **1,** o usuário do dispositivo não poderá instalar aplicativos pessoais, como a Cortana.</span><span class="sxs-lookup"><span data-stu-id="406c2-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span><br/> |
   
