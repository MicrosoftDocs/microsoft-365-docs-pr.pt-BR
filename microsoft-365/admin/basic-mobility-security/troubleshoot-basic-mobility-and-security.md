---
title: Solucionar problemas de mobilidade básica e segurança
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
description: Tente estas etapas para rastrear problemas básicos de segurança e mobilidade
ms.openlocfilehash: a199252c04796d5aa8c4d82a2411ccd6317f6f60
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336708"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="4f4f4-103">Solucionar problemas de mobilidade básica e segurança</span><span class="sxs-lookup"><span data-stu-id="4f4f4-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="4f4f4-104">Se você estiver executando problemas ao tentar registrar um dispositivo em mobilidade básica e segurança, tente as etapas aqui para rastrear o problema.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="4f4f4-105">Se as etapas gerais não corrigirem o problema, consulte uma das seções posteriores com etapas específicas para o tipo de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="4f4f4-106">Etapas para tentar primeiro</span><span class="sxs-lookup"><span data-stu-id="4f4f4-106">Steps to try first</span></span>

<span data-ttu-id="4f4f4-107">Para começar, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4f4f4-107">To start, check the following:</span></span>

- <span data-ttu-id="4f4f4-108">Certifique-se de que o dispositivo ainda não esteja inscrito com outro provedor de gerenciamento de dispositivo móvel, como o Intune.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>
    
- <span data-ttu-id="4f4f4-109">Certifique-se de que o dispositivo está definido para a data e hora corretas.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-109">Make sure that the device is set to the correct date and time.</span></span>
    
- <span data-ttu-id="4f4f4-110">Alterne para uma rede WIFI ou de celular diferente no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-110">Switch to a different WIFI or cellular network on the device.</span></span>
    
- <span data-ttu-id="4f4f4-111">Para dispositivos Android ou iOS, desinstale e reinstale o aplicativo portal da empresa do Intune no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="4f4f4-112">telefone iOS ou Tablet</span><span class="sxs-lookup"><span data-stu-id="4f4f4-112">iOS phone or tablet</span></span>

- <span data-ttu-id="4f4f4-113">Verifique se você configurou um certificado APNs.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="4f4f4-114">Para obter mais informações, consulte [criar um certificado APNs para dispositivos IOS](create-an-apns-certificate-for-ios-devices.md).</span><span class="sxs-lookup"><span data-stu-id="4f4f4-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>
    
- <span data-ttu-id="4f4f4-115">Em **configurações**   >  **gerais**de   >  **perfil (ou gerenciamento de dispositivos)**, certifique-se de que um perfil de gerenciamento ainda não esteja instalado.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="4f4f4-116">Se estiver, remova-o.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-116">If it is, remove it.</span></span>
    
- <span data-ttu-id="4f4f4-117">Se você vir a mensagem de erro, "o dispositivo não pôde registrar", entre no Microsoft 365 e certifique-se de que uma licença que inclui o Exchange Online tenha sido atribuída ao usuário que está conectado ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="4f4f4-118">Se você vir a mensagem de erro, "perfil falhou ao instalar", tente uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="4f4f4-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>
    
    - <span data-ttu-id="4f4f4-119">Verifique se o Safari é o navegador padrão no dispositivo e se os cookies não estão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>
    
    - <span data-ttu-id="4f4f4-120">Reinicialize o dispositivo e navegue até portal.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="4f4f4-121">Entre com sua ID de usuário e senha do Microsoft 365 e tente instalar o perfil manualmente.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>    

## <a name="windows-rt"></a><span data-ttu-id="4f4f4-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="4f4f4-122">Windows RT</span></span>

- <span data-ttu-id="4f4f4-123">Verifique se o seu domínio está configurado no Microsoft 365 para trabalhar com mobilidade básica e segurança.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="4f4f4-124">Para obter mais informações, consulte [Configurar mobilidade básica e segurança](set-up-basic-mobility-and-security.md).</span><span class="sxs-lookup"><span data-stu-id="4f4f4-124">For more info, see [Set up Basic Mobility and Security](set-up-basic-mobility-and-security.md).</span></span>
    
- <span data-ttu-id="4f4f4-125">Certifique-se de que o usuário está escolhendo **ativar em**   vez de escolher **ingressar**.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>    

## <a name="windows-10-pc"></a><span data-ttu-id="4f4f4-126">PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="4f4f4-126">Windows 10 PC</span></span>

- <span data-ttu-id="4f4f4-127">Verifique se o seu domínio está configurado no Microsoft 365 para trabalhar com mobilidade básica e segurança.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="4f4f4-128">Para obter mais informações, consulte [Configurar mobilidade básica e segurança](set-up-basic-mobility-and-security.md).</span><span class="sxs-lookup"><span data-stu-id="4f4f4-128">For more info, see [Set up Basic Mobility and Security](set-up-basic-mobility-and-security.md).</span></span>
    
- <span data-ttu-id="4f4f4-129">A menos que você tenha o Azure Active Directory Premium, certifique-se de que o usuário está escolhendo **registrar somente o gerenciamento de dispositivos**   , em vez de escolher **conectar**.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="4f4f4-130">Telefone Android ou Tablet</span><span class="sxs-lookup"><span data-stu-id="4f4f4-130">Android phone or tablet</span></span>

- <span data-ttu-id="4f4f4-131">Verifique se o dispositivo está executando o Android 4,4 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-131">Make sure the device is running Android 4.4 or later.</span></span>
    
- <span data-ttu-id="4f4f4-132">Verifique se o Chrome está atualizado e se está definido como o navegador padrão.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>
    
- <span data-ttu-id="4f4f4-133">Se você vir a mensagem de erro "não foi possível registrar este dispositivo", entre no Microsoft 365 e certifique-se de que uma licença que inclui o Exchange Online tenha sido atribuída ao usuário que está conectado ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="4f4f4-134">Verifique a área de notificação no dispositivo para ver se as ações de usuário final necessárias estão pendentes e, se estiverem, concluem as ações.</span><span class="sxs-lookup"><span data-stu-id="4f4f4-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>