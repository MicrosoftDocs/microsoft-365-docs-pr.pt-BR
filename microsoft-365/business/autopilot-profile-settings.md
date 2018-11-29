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
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="c9f9f-104">Sobre as configurações de perfil do AutoPilot</span><span class="sxs-lookup"><span data-stu-id="c9f9f-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="c9f9f-105">Configurações de perfil do piloto automático</span><span class="sxs-lookup"><span data-stu-id="c9f9f-105">AutoPilot profile settings</span></span>

<span data-ttu-id="c9f9f-p102">Você pode controlar como o Windows obtém instalado nos dispositivos de usuário usando os perfis de piloto automático. Os perfis contêm as configurações a seguir.</span><span class="sxs-lookup"><span data-stu-id="c9f9f-p102">You can control how Windows gets installed on user devices by using the AutoPilot profiles. The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="c9f9f-108">**Piloto automático recursos padrão (obrigatório) que são configurados automaticamente:**</span><span class="sxs-lookup"><span data-stu-id="c9f9f-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="c9f9f-109">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="c9f9f-109">**Setting**</span></span>|<span data-ttu-id="c9f9f-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c9f9f-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9f9f-111">Ignorar o registro Cortana, OneDrive e OEM</span><span class="sxs-lookup"><span data-stu-id="c9f9f-111">Skip Cortana, OneDrive and OEM registration</span></span>  <br/> |<span data-ttu-id="c9f9f-p103">Ignora a instalação de aplicativos do consumidor como Cortana e OneDrive pessoal. Usuário do dispositivo pode instalar esses posterior, desde que ele seja um administrador local no dispositivo. O registro original do fabricante é ignorado porque o dispositivo será gerenciado pelas Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="c9f9f-p103">Skips the installation of consumer apps like Cortana and personal OneDrive. The device user can install these later as long as he or she is a local admin on the device. The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="c9f9f-115">Inscreva-se na experiência com a marca da sua empresa</span><span class="sxs-lookup"><span data-stu-id="c9f9f-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="c9f9f-116">Se sua empresa tiver um [Add sua empresa branding para Office 365 Sign In da página](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), o usuário do dispositivo receberá essa experiência ao fazer logon.</span><span class="sxs-lookup"><span data-stu-id="c9f9f-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="c9f9f-117">MDM inscrição automática com contas AAD configuradas.</span><span class="sxs-lookup"><span data-stu-id="c9f9f-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="c9f9f-118">A identidade do usuário será gerenciada pelo Windows Azure Active directory e os usuários entrará em Windows e o Office 365 com suas credenciais do Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="c9f9f-118">The user identity will be managed by Azure Active directory, and the users will sign into Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="c9f9f-119">**Configurações opcionais:**</span><span class="sxs-lookup"><span data-stu-id="c9f9f-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="c9f9f-120">**Configuração**</span><span class="sxs-lookup"><span data-stu-id="c9f9f-120">**Setting**</span></span>|<span data-ttu-id="c9f9f-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c9f9f-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9f9f-122">Ignorar as configurações de privacidade (desativado por padrão)</span><span class="sxs-lookup"><span data-stu-id="c9f9f-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="c9f9f-123">Se essa opção estiver definida como **On**, o usuário do dispositivo não verá o contrato de licença para o dispositivo e o Windows quando ele entra pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="c9f9f-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="c9f9f-124">Não permitir que o usuário se torne o administrador local</span><span class="sxs-lookup"><span data-stu-id="c9f9f-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="c9f9f-125">Se essa opção estiver definida como **On**, o usuário do dispositivo não poderão instalar quaisquer aplicativos pessoais, como Cortana.</span><span class="sxs-lookup"><span data-stu-id="c9f9f-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span>  <br/> |
   
