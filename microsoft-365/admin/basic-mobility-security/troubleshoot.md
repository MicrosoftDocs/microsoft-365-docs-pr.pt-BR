---
title: Solucionar problemas básicos de mobilidade e segurança
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Experimente estas etapas para rastrear problemas básicos de mobilidade e segurança
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876847"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="969b2-103">Solucionar problemas básicos de mobilidade e segurança</span><span class="sxs-lookup"><span data-stu-id="969b2-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="969b2-104">Se você estiver com problemas ao tentar registrar um dispositivo no Basic Mobility and Security, tente as etapas aqui para rastrear o problema.</span><span class="sxs-lookup"><span data-stu-id="969b2-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="969b2-105">Se as etapas gerais não corrigirem o problema, consulte uma das seções posteriores com etapas específicas para o tipo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="969b2-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="969b2-106">Etapas para tentar primeiro</span><span class="sxs-lookup"><span data-stu-id="969b2-106">Steps to try first</span></span>

<span data-ttu-id="969b2-107">Para iniciar, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="969b2-107">To start, check the following:</span></span>

- <span data-ttu-id="969b2-108">Certifique-se de que o dispositivo ainda não está inscrito em outro provedor de gerenciamento de dispositivo móvel, como o Intune.</span><span class="sxs-lookup"><span data-stu-id="969b2-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>

- <span data-ttu-id="969b2-109">Certifique-se de que o dispositivo está definido como a data e a hora corretas.</span><span class="sxs-lookup"><span data-stu-id="969b2-109">Make sure that the device is set to the correct date and time.</span></span>

- <span data-ttu-id="969b2-110">Alternar para uma rede WIFI ou celular diferente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="969b2-110">Switch to a different WIFI or cellular network on the device.</span></span>

- <span data-ttu-id="969b2-111">Para dispositivos Android ou iOS, desinstale e reinstale o aplicativo Portal da Empresa do Intune no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="969b2-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="969b2-112">Telefone ou tablet iOS</span><span class="sxs-lookup"><span data-stu-id="969b2-112">iOS phone or tablet</span></span>

- <span data-ttu-id="969b2-113">Certifique-se de configurar um certificado APNs.</span><span class="sxs-lookup"><span data-stu-id="969b2-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="969b2-114">Para obter mais informações, [consulte Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span><span class="sxs-lookup"><span data-stu-id="969b2-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>

- <span data-ttu-id="969b2-115">Em **Configurações** Perfil Geral (ou Gerenciamento de   >  \*\*\*\*   >  **Dispositivos),** certifique-se de que um Perfil de Gerenciamento ainda não está instalado.</span><span class="sxs-lookup"><span data-stu-id="969b2-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="969b2-116">Se estiver, remova-o.</span><span class="sxs-lookup"><span data-stu-id="969b2-116">If it is, remove it.</span></span>

- <span data-ttu-id="969b2-117">Se você vir a mensagem de erro, "Device failed to enroll", entre no Microsoft 365 e certifique-se de que uma licença que inclui Exchange Online tenha sido atribuída ao usuário que está conectado ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="969b2-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="969b2-118">Se você vir a mensagem de erro, "Perfil não foi instalado", tente um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="969b2-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>

    - <span data-ttu-id="969b2-119">Certifique-se de que o Safari seja o navegador padrão no dispositivo e se os cookies não estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="969b2-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>

    - <span data-ttu-id="969b2-120">Reinicie o dispositivo e navegue até portal.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="969b2-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="969b2-121">Entre com sua ID Microsoft 365 usuário e senha e tente instalar o perfil manualmente.</span><span class="sxs-lookup"><span data-stu-id="969b2-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>

## <a name="windows-rt"></a><span data-ttu-id="969b2-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="969b2-122">Windows RT</span></span>

- <span data-ttu-id="969b2-123">Certifique-se de que seu domínio está Microsoft 365 para trabalhar com Mobilidade Básica e Segurança.</span><span class="sxs-lookup"><span data-stu-id="969b2-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="969b2-124">Para obter mais informações, [consulte Set up Basic Mobility and Security](set-up.md).</span><span class="sxs-lookup"><span data-stu-id="969b2-124">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="969b2-125">Certifique-se de que o usuário está escolhendo **Ativar em** vez de   escolher **Ingressar**.</span><span class="sxs-lookup"><span data-stu-id="969b2-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>

## <a name="windows-10-pc"></a><span data-ttu-id="969b2-126">Windows 10 PC</span><span class="sxs-lookup"><span data-stu-id="969b2-126">Windows 10 PC</span></span>

- <span data-ttu-id="969b2-127">Certifique-se de que seu domínio está Microsoft 365 para trabalhar com Mobilidade Básica e Segurança.</span><span class="sxs-lookup"><span data-stu-id="969b2-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="969b2-128">Para obter mais informações, [consulte Set up Basic Mobility and Security](set-up.md).</span><span class="sxs-lookup"><span data-stu-id="969b2-128">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="969b2-129">A menos que você Azure Active Directory Premium, certifique-se de que o usuário esteja escolhendo Registrar-se no Gerenciamento de **Dispositivos** apenas em vez de   escolher **Conexão**.</span><span class="sxs-lookup"><span data-stu-id="969b2-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="969b2-130">Telefone ou tablet Android</span><span class="sxs-lookup"><span data-stu-id="969b2-130">Android phone or tablet</span></span>

- <span data-ttu-id="969b2-131">Certifique-se de que o dispositivo está executando o Android 4.4 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="969b2-131">Make sure the device is running Android 4.4 or later.</span></span>

- <span data-ttu-id="969b2-132">Certifique-se de que o Chrome está atualizado e está definido como o navegador padrão.</span><span class="sxs-lookup"><span data-stu-id="969b2-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>

- <span data-ttu-id="969b2-133">Se você vir a mensagem de erro "Não foi possível registrar esse dispositivo", entre no Microsoft 365 e certifique-se de que uma licença que inclui Exchange Online tenha sido atribuída ao usuário que está conectado ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="969b2-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="969b2-134">Verifique a Área de Notificação no dispositivo para ver se alguma ação necessária do usuário final está pendente e, se estiver, conclua as ações.</span><span class="sxs-lookup"><span data-stu-id="969b2-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>