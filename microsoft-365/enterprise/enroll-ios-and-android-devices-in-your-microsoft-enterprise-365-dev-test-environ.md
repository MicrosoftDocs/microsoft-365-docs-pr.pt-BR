---
title: Registre dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Use este guia de laboratório de teste para registrar os dispositivos em seu ambiente de teste do Microsoft 365 e gerenciá-los remotamente.
ms.openlocfilehash: a78db19099ccacd1b2f62e8438d1749f28d22f52
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864816"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6b0b8-103">Registre dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6b0b8-103">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6b0b8-104">Seguindo as instruções fornecidas neste artigo, você poderá registrar e testar os recursos de gerenciamento de dispositivo móvel básica para dispositivos com Android e iOS em seu ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6b0b8-104">By following the instructions provided in this article, you'll be able to enroll and test basic mobile device management capabilities for iOS and Android devices in your Microsoft 365 Enterprise test environment.</span></span>

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="6b0b8-106">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6b0b8-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6b0b8-107">Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6b0b8-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6b0b8-108">Se você deseja registrar os dispositivos com Android e iOS de forma leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="6b0b8-108">If you just want to enroll iOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6b0b8-109">Se você deseja registrar iOS e dispositivos com Android em uma empresa simulado, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6b0b8-109">If you want to enroll iOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6b0b8-p101">Testando automatizada de licenciamento e a associação de grupo não requer o ambiente de teste de simulado empresarial, que inclui uma intranet simulada conectada à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar automatizada de licenciamento e a associação ao grupo e experimentar em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="6b0b8-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="6b0b8-112">Fase 2: Registrar seus dispositivos com Android e iOS</span><span class="sxs-lookup"><span data-stu-id="6b0b8-112">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="6b0b8-113">Primeiro, use as instruções em [instalar e acesse o aplicativo de Portal da empresa](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) para personalizar o aplicativo Microsoft Intune Portal da empresa para o seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="6b0b8-113">First, use the instructions in [Install and sign in to the Company Portal app](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) to customize the Microsoft Intune Company Portal app for your test environment.</span></span>

<span data-ttu-id="6b0b8-114">Em seguida, use as instruções em [Configurar o acesso aos seus recursos de empresa](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) para registrar um dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="6b0b8-114">Next, use the instructions in [Set up access to your company resources](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) to enroll an iOS device.</span></span>

<span data-ttu-id="6b0b8-115">Em seguida, use as instruções em [registrar seu dispositivo Android no Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) para registrar um dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="6b0b8-115">Next, use the instructions in [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) to enroll an Android device.</span></span>

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="6b0b8-116">Fase 3: Gerenciar seus dispositivos com Android e iOS remotamente</span><span class="sxs-lookup"><span data-stu-id="6b0b8-116">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="6b0b8-p102">Microsoft Intune fornece recursos de redefinição de bloqueio remoto e uma senha. Se alguém perder seus dispositivos, você pode bloquear o dispositivo remotamente. Se alguém esquecer sua senha, é possível redefini-lo remotamente.</span><span class="sxs-lookup"><span data-stu-id="6b0b8-p102">Microsoft Intune provides both remote lock and passcode reset capabilities. If someone loses their device, you can lock the device remotely. If someone forgets their passcode, you can reset it remotely.</span></span>
  
<span data-ttu-id="6b0b8-120">Para bloquear um dispositivo Android ou o iOS remotamente:</span><span class="sxs-lookup"><span data-stu-id="6b0b8-120">To lock an iOS or Android device remotely:</span></span>

1. <span data-ttu-id="6b0b8-121">Entrar no portal do Windows Azure em [https://portal.azure.com](https://portal.azure.com) com as credenciais da sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="6b0b8-121">Sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="6b0b8-122">Clique em **todos os serviços**, digite **Intune**e clique em **Intune**.</span><span class="sxs-lookup"><span data-stu-id="6b0b8-122">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="6b0b8-123">Clique em **dispositivos > todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="6b0b8-123">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="6b0b8-124">Na lista de dispositivos, clique em um iOS ou um dispositivo Android e, em seguida, clique na ação de **bloqueio remoto** .</span><span class="sxs-lookup"><span data-stu-id="6b0b8-124">In the list of devices, click an iOS or Android device, and then click the **Remote lock** action.</span></span>

    
<span data-ttu-id="6b0b8-125">Para redefinir a senha remotamente:</span><span class="sxs-lookup"><span data-stu-id="6b0b8-125">To reset the passcode remotely:</span></span>

1. <span data-ttu-id="6b0b8-126">Se necessário, entrar no portal do Windows Azure em [https://portal.azure.com](https://portal.azure.com) com as credenciais da sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="6b0b8-126">If needed, sign in to the Azure portal at [https://portal.azure.com](https://portal.azure.com) with the credentials of your global administrator account.</span></span>
2. <span data-ttu-id="6b0b8-127">Clique em **todos os serviços**, digite **Intune**e clique em **Intune**.</span><span class="sxs-lookup"><span data-stu-id="6b0b8-127">Click **All services**, type **Intune**, and then click **Intune**.</span></span>
3. <span data-ttu-id="6b0b8-128">Clique em **dispositivos > todos os dispositivos**.</span><span class="sxs-lookup"><span data-stu-id="6b0b8-128">Click **Devices > All devices**.</span></span>
4. <span data-ttu-id="6b0b8-p103">Da lista de dispositivos você gerenciar, clique em um iOS ou um dispositivo Android e escolha **… Mais**. Escolha a ação remota dispositivo **Remover a senha** .</span><span class="sxs-lookup"><span data-stu-id="6b0b8-p103">From the list of devices you manage, click an iOS or Android device, and choose **...More**. Then choose the **Remove passcode** device remote action.</span></span>

<span data-ttu-id="6b0b8-131">Experimentação adicionais, consulte [ações de dispositivo disponível](https://docs.microsoft.com/intune/device-management#available-device-actions).</span><span class="sxs-lookup"><span data-stu-id="6b0b8-131">For additional experimentation, see [Available device actions](https://docs.microsoft.com/intune/device-management#available-device-actions).</span></span>

    
## <a name="next-step"></a><span data-ttu-id="6b0b8-132">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="6b0b8-132">Next step</span></span>

<span data-ttu-id="6b0b8-133">Explore recursos adicionais de [gerenciamento de dispositivos móveis](m365-enterprise-test-lab-guides.md#mobile-device-management) e capacidades no seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="6b0b8-133">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b0b8-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="6b0b8-134">See Also</span></span>

[<span data-ttu-id="6b0b8-135">Guias do Laboratório de Teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6b0b8-135">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="6b0b8-136">Ambiente de teste de políticas de conformidade do dispositivo para a sua empresa de 365 da Microsoft</span><span class="sxs-lookup"><span data-stu-id="6b0b8-136">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="6b0b8-137">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6b0b8-137">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="6b0b8-138">Mobilidade corporativos + segurança (EMS)</span><span class="sxs-lookup"><span data-stu-id="6b0b8-138">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
