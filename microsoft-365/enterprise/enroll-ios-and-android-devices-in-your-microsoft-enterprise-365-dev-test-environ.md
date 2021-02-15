---
title: Registrar dispositivos iOS/iPadOS e Android no ambiente de teste do Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Use este Guia de Laboratório de Teste para registrar dispositivos em seu ambiente de teste do Microsoft 365 e gerenciá-los remotamente.
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367078"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="6eba8-103">Registrar dispositivos iOS e Android no ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="6eba8-103">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="6eba8-104">*Este Guia de Laboratório de Teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="6eba8-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="6eba8-105">Este artigo descreve como registrar e testar os recursos básicos de gerenciamento de dispositivos móveis para dispositivos iOS/iPadOS e Android em seu ambiente de teste do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="6eba8-105">This article describes how to enroll and test basic mobile device management capabilities for iOS/iPadOS and Android devices in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="6eba8-106">O registro de dispositivos iOS/iPadOS e Android em seu ambiente de teste envolve três fases:</span><span class="sxs-lookup"><span data-stu-id="6eba8-106">Enrolling iOS/iPadOS and Android devices in your test environment involves three phases:</span></span>
- [<span data-ttu-id="6eba8-107">Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="6eba8-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="6eba8-108">Fase 2: Registrar seus dispositivos iOS/iPadOS e Android</span><span class="sxs-lookup"><span data-stu-id="6eba8-108">Phase 2: Enroll your iOS/iPadOS and Android devices</span></span>](#phase-2-enroll-your-ios-and-android-devices)
- [<span data-ttu-id="6eba8-109">Fase 3: Gerenciar seus dispositivos iOS/iPadOS e Android remotamente</span><span class="sxs-lookup"><span data-stu-id="6eba8-109">Phase 3: Manage your iOS/iPadOS and Android devices remotely</span></span>](#phase-3-manage-your-ios-and-android-devices-remotely)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="6eba8-111">Para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 para empresas, vá para a Pilha de Guias de Laboratório de Teste do [Microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)para empresas.</span><span class="sxs-lookup"><span data-stu-id="6eba8-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="6eba8-112">Fase 1: Criar seu ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="6eba8-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="6eba8-113">Se você quiser registrar dispositivos iOS/iPadOS e Android de maneira leve com os requisitos mínimos, siga as instruções na configuração [de base leve.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="6eba8-113">If you want to enroll iOS/iPadOS and Android devices in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="6eba8-114">Se você quiser registrar dispositivos iOS/iPadOS e Android em uma empresa simulada, siga as instruções na autenticação [de passagem.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="6eba8-114">If you want to enroll iOS/iPadOS and Android devices in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6eba8-115">O teste automatizado de licenciamento e associação de grupo não exige o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta do AD DS (Serviços de Domínio Active Directory).</span><span class="sxs-lookup"><span data-stu-id="6eba8-115">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="6eba8-116">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento automatizado e a associação de grupo, e você pode experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="6eba8-116">It's provided here as an option so that you can test automated licensing and group membership, and you can experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-enroll-your-ios-and-android-devices"></a><span data-ttu-id="6eba8-117">Fase 2: Registrar seus dispositivos iOS e Android</span><span class="sxs-lookup"><span data-stu-id="6eba8-117">Phase 2: Enroll your iOS and Android devices</span></span>

<span data-ttu-id="6eba8-118">Se você estiver considerando uma solução de gerenciamento de dispositivo móvel (MDM) para gerenciar seus dispositivos, poderá usar o Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="6eba8-118">If you're considering a mobile device management (MDM) solution to manage your devices, you can use Microsoft Intune.</span></span> <span data-ttu-id="6eba8-119">Ao trabalhar com qualquer provedor de MDM, incluindo o Intune, os dispositivos são "inscritos".</span><span class="sxs-lookup"><span data-stu-id="6eba8-119">When working with any MDM provider, including Intune, devices are "enrolled".</span></span> <span data-ttu-id="6eba8-120">Quando inscritos, eles recebem os recursos e as configurações que você define.</span><span class="sxs-lookup"><span data-stu-id="6eba8-120">When enrolled, they receive the features and settings you configure.</span></span> 

<span data-ttu-id="6eba8-121">No Intune, há algumas maneiras de registrar seus dispositivos iOS/iPadOS e Android.</span><span class="sxs-lookup"><span data-stu-id="6eba8-121">In Intune, there are a few ways to enroll your iOS/iPadOS and Android devices.</span></span> <span data-ttu-id="6eba8-122">Você pode escolher a opção de registro que funciona melhor para sua organização.</span><span class="sxs-lookup"><span data-stu-id="6eba8-122">You can choose the enrollment option that works best for your organization.</span></span> <span data-ttu-id="6eba8-123">Para obter mais informações e diretrizes, consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="6eba8-123">For more information and guidance, see the following articles:</span></span>

- [<span data-ttu-id="6eba8-124">Guia de implantação: registrar dispositivos iOS e iPadOS no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6eba8-124">Deployment guide: Enroll iOS and iPadOS devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [<span data-ttu-id="6eba8-125">Guia de implantação: registrar dispositivos Android no Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6eba8-125">Deployment guide: Enroll Android devices in Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-enrollment-android)

<span data-ttu-id="6eba8-126">Se você estiver pronto para usar o Intune para gerenciamento de dispositivos e quiser algumas orientações, as seguintes informações podem ajudar:</span><span class="sxs-lookup"><span data-stu-id="6eba8-126">If you're ready to use Intune for device management, and want some guidance, then the following information may help:</span></span>

- [<span data-ttu-id="6eba8-127">Visão geral do gerenciamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="6eba8-127">Device management overview</span></span>](/mem/intune/fundamentals/what-is-device-management)
- [<span data-ttu-id="6eba8-128">Tutorial: Passo a passo do Intune no Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="6eba8-128">Tutorial: Walkthrough Intune in Microsoft Endpoint Manager</span></span>](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [<span data-ttu-id="6eba8-129">Guia de implantação: configurar ou mover para o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6eba8-129">Deployment guide: Setup or move to Microsoft Intune</span></span>](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a><span data-ttu-id="6eba8-130">Fase 3: Gerenciar seus dispositivos iOS e Android remotamente</span><span class="sxs-lookup"><span data-stu-id="6eba8-130">Phase 3: Manage your iOS and Android devices remotely</span></span>

<span data-ttu-id="6eba8-131">O Microsoft Intune fornece o recurso de bloqueio remoto e redefinição de senha.</span><span class="sxs-lookup"><span data-stu-id="6eba8-131">Microsoft Intune provides remote lock and passcode reset feature.</span></span> <span data-ttu-id="6eba8-132">Se alguém perder o dispositivo, você poderá bloqueá-lo remotamente.</span><span class="sxs-lookup"><span data-stu-id="6eba8-132">If someone loses their device, you can remotely lock the device.</span></span> <span data-ttu-id="6eba8-133">Se alguém esquecer a senha, você poderá redefini-la remotamente.</span><span class="sxs-lookup"><span data-stu-id="6eba8-133">If someone forgets their passcode, you can remotely reset it.</span></span>

- <span data-ttu-id="6eba8-134">Para bloquear remotamente um dispositivo iOS/iPadOS ou Android, consulte Bloquear dispositivos [remotamente com o Intune.](/mem/intune/remote-actions/device-remote-lock)</span><span class="sxs-lookup"><span data-stu-id="6eba8-134">To remotely lock an iOS/iPadOS or Android device, see [Remotely lock devices with Intune](/mem/intune/remote-actions/device-remote-lock).</span></span>
- <span data-ttu-id="6eba8-135">Para redefinir remotamente a senha, consulte [Redefinir ou remover uma senha de dispositivo no Intune.](/mem/intune/remote-actions/device-passcode-reset)</span><span class="sxs-lookup"><span data-stu-id="6eba8-135">To remotely reset the passcode, see [Reset or remove a device passcode in Intune](/mem/intune/remote-actions/device-passcode-reset).</span></span>

<span data-ttu-id="6eba8-136">Para tarefas adicionais que você pode executar remotamente, consulte [as ações de dispositivo disponíveis.](/mem/intune/remote-actions/device-management#available-device-actions)</span><span class="sxs-lookup"><span data-stu-id="6eba8-136">For additional tasks you can run remotely, see [available device actions](/mem/intune/remote-actions/device-management#available-device-actions).</span></span>
    
## <a name="next-step"></a><span data-ttu-id="6eba8-137">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="6eba8-137">Next step</span></span>

<span data-ttu-id="6eba8-138">Explore recursos [adicionais de gerenciamento de](m365-enterprise-test-lab-guides.md#mobile-device-management) dispositivos móveis em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="6eba8-138">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="6eba8-139">Confira também</span><span class="sxs-lookup"><span data-stu-id="6eba8-139">See Also</span></span>

[<span data-ttu-id="6eba8-140">Guias do Laboratório de Teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="6eba8-140">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)
  
[<span data-ttu-id="6eba8-141">Políticas de conformidade do dispositivo para o ambiente de teste do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="6eba8-141">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[<span data-ttu-id="6eba8-142">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="6eba8-142">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)
