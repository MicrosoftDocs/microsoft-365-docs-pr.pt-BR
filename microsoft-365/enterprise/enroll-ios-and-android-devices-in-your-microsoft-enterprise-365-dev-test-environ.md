---
title: Registrar dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Use este guia de laboratório de teste para registrar dispositivos no seu ambiente de teste do Microsoft 365 e gerenciá-los remotamente.
ms.openlocfilehash: 0dde7acd10ad78327adb4862346639e05a276b4e
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981992"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="daf4e-103">Registrar dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="daf4e-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="daf4e-104">Seguindo as instruções fornecidas neste artigo, você poderá registrar e testar recursos básicos de gerenciamento de dispositivos móveis para dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="daf4e-104">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Guias de laboratório de teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="daf4e-106">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="daf4e-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="daf4e-107">Fase 1: criar seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="daf4e-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="daf4e-108">Se você só quiser inscrever dispositivos iOS e Android de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="daf4e-108">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="daf4e-109">Se você deseja registrar dispositivos iOS e Android em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="daf4e-109">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="daf4e-110">Testar o licenciamento automatizado e a associação de grupo não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="daf4e-110">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="daf4e-111">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="daf4e-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="daf4e-112">Fase 2: registrar seus dispositivos iOS e Android</span><span class="sxs-lookup"><span data-stu-id="daf4e-112">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="daf4e-113">Primeiro, use as instruções em [instalar e entre no aplicativo do portal da empresa](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) para personalizar o aplicativo portal da empresa do Microsoft Intune para seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="daf4e-113">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="daf4e-114">Em seguida, use as instruções em [Configurar o acesso aos recursos da sua empresa](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) para registrar um dispositivo IOS.</span><span class="sxs-lookup"><span data-stu-id="daf4e-114">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="daf4e-115">Em seguida, use as instruções em [registrar seu dispositivo Android no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) para registrar um dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="daf4e-115">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="daf4e-116">Fase 3: gerenciar seus dispositivos iOS e Android remotamente</span><span class="sxs-lookup"><span data-stu-id="daf4e-116">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="daf4e-117">O Microsoft Intune fornece recursos de bloqueio e redefinição de senha remotos.</span><span class="sxs-lookup"><span data-stu-id="daf4e-117">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span> <span data-ttu-id="daf4e-118">Se alguém perder um dispositivo, você poderá bloqueá-lo remotamente.</span><span class="sxs-lookup"><span data-stu-id="daf4e-118">If someone loses their device, you can lock the device remotely.</span></span> <span data-ttu-id="daf4e-119">Se alguém esquecer sua senha, você poderá redefini-la remotamente.</span><span class="sxs-lookup"><span data-stu-id="daf4e-119">If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="daf4e-120">Para bloquear um dispositivo iOS ou Android remotamente:</span><span class="sxs-lookup"><span data-stu-id="daf4e-120">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="daf4e-121">Entre no portal do Azure [https://portal.azure.com](https://portal.azure.com) com as credenciais de sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="daf4e-121">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="daf4e-122">Clique em **todos os serviços**, digite **Intune**e clique em **Intune**.</span><span class="sxs-lookup"><span data-stu-id="daf4e-122">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="daf4e-123">Clique em **dispositivos > todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="daf4e-123">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="daf4e-124">Na lista de dispositivos, clique em um dispositivo iOS ou Android e, em seguida, clique na ação de **bloqueio remoto** .</span><span class="sxs-lookup"><span data-stu-id="daf4e-124">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="daf4e-125">Para redefinir a senha remotamente:</span><span class="sxs-lookup"><span data-stu-id="daf4e-125">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="daf4e-126">Se necessário, entre no portal do Azure [https://portal.azure.com](https://portal.azure.com) com as credenciais de sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="daf4e-126">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="daf4e-127">Clique em **todos os serviços**, digite **Intune**e clique em **Intune**.</span><span class="sxs-lookup"><span data-stu-id="daf4e-127">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="daf4e-128">Clique em **dispositivos > todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="daf4e-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="daf4e-129">Na lista de dispositivos que você gerencia, clique em um dispositivo iOS ou Android e escolha **... Mais**.</span><span class="sxs-lookup"><span data-stu-id="daf4e-129">From the list of devices you manage, click an iOS or Android device, and choose **...More**.</span></span> <span data-ttu-id="daf4e-130">Em seguida, escolha a ação de remover dispositivo de **senha** remoto.</span><span class="sxs-lookup"><span data-stu-id="daf4e-130">Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="daf4e-131">Para experimentação adicional, confira [ações de dispositivo disponíveis](https://docs.microsoft.com/intune/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="daf4e-131">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="daf4e-132">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="daf4e-132">Next step</span></span>

<span data-ttu-id="daf4e-133">Explore recursos de [Gerenciamento de dispositivos móveis](m365-enterprise-test-lab-guides.md#mobile-device-management) e recursos adicionais em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="daf4e-133">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="daf4e-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="daf4e-134">See Also</span></span>

[<span data-ttu-id="daf4e-135">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="daf4e-135">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="daf4e-136">Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="daf4e-136">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="daf4e-137">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="daf4e-137">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

