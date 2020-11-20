---
title: Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 for Enterprise
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para adicionar políticas de conformidade de dispositivo do Intune ao seu ambiente de teste do Microsoft 365 for Enterprise.
ms.openlocfilehash: d42c9a603ca581941cb5a8f30b9ecd9d6f780759
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367090"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d2ec3-103">Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="d2ec3-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d2ec3-104">*Este guia de laboratório de teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="d2ec3-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="d2ec3-105">Este artigo descreve como adicionar uma política de conformidade de dispositivo do Intune para dispositivos Windows 10 e aplicativos da Microsoft 365 para empresas ao seu ambiente de teste do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="d2ec3-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="d2ec3-106">A adição de uma política de conformidade de dispositivo do Intune envolve duas fases:</span><span class="sxs-lookup"><span data-stu-id="d2ec3-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="d2ec3-107">Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="d2ec3-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="d2ec3-108">Fase 2: criar uma política de conformidade de dispositivo para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="d2ec3-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="d2ec3-110">Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="d2ec3-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="d2ec3-111">Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="d2ec3-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="d2ec3-112">Se você quiser configurar as políticas de MAM de forma simples com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="d2ec3-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="d2ec3-113">Se você quiser configurar as políticas de MAM em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="d2ec3-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d2ec3-114">Testar o licenciamento automatizado e a associação de grupo não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="d2ec3-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="d2ec3-115">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="d2ec3-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="d2ec3-116">Fase 2: criar uma política de conformidade de dispositivo para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="d2ec3-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="d2ec3-117">Nesta fase, você cria uma política de conformidade de dispositivo para dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d2ec3-117">In this phase, you create a device compliance policy for Windows 10 devices.</span></span> <span data-ttu-id="d2ec3-118">Esta fase usa o Microsoft Intune e o [centro de administração do gerente de ponto de extremidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=2109431) para adicionar um grupo e criar uma política de conformidade.</span><span class="sxs-lookup"><span data-stu-id="d2ec3-118">This phase uses Microsoft Intune and the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) to add a group, and create a compliance policy.</span></span>

1. <span data-ttu-id="d2ec3-119">Vá para o [centro de administração do microsoft 365](https://admin.microsoft.com)e entre na sua assinatura de laboratório de teste do Microsoft 365 com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="d2ec3-119">Go to the [Microsoft 365 admin center](https://admin.microsoft.com), and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span> <span data-ttu-id="d2ec3-120">Selecione o centro de administração do **Gerenciador de pontos de extremidade** .</span><span class="sxs-lookup"><span data-stu-id="d2ec3-120">Select the **Endpoint Manager** admin center.</span></span> <span data-ttu-id="d2ec3-121">O [centro de administração do Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) é aberto.</span><span class="sxs-lookup"><span data-stu-id="d2ec3-121">The [Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) opens.</span></span>

    <span data-ttu-id="d2ec3-122">Se uma mensagem semelhante à **que você ainda não habilitou o gerenciamento de dispositivos** for exibida, selecione o Intune como autoridade de MDM.</span><span class="sxs-lookup"><span data-stu-id="d2ec3-122">If a message similar to **You haven't enabled device management yet** message is shown, then select Intune as the MDM authority.</span></span> <span data-ttu-id="d2ec3-123">Para obter as etapas específicas, consulte [set the Mobile Device Management Authority](/mem/intune/fundamentals/mdm-authority-set).</span><span class="sxs-lookup"><span data-stu-id="d2ec3-123">For the specific steps, see [Set the mobile device management authority](/mem/intune/fundamentals/mdm-authority-set).</span></span>

    <span data-ttu-id="d2ec3-124">O centro de administração do Endpoint Manager enfoca o gerenciamento de dispositivos e o gerenciamento de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="d2ec3-124">The Endpoint Manager admin center focuses on device management and app management.</span></span> <span data-ttu-id="d2ec3-125">Para obter um tour desse centro de administração, consulte [tutorial: passo a passo do Intune no Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span><span class="sxs-lookup"><span data-stu-id="d2ec3-125">For a tour of this admin center, see [Tutorial: Walkthrough Intune in Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager).</span></span>

2. <span data-ttu-id="d2ec3-126">Em **grupos**, adicione um novo **Microsoft 365** ou grupo de **segurança** chamado **usuários gerenciados do dispositivo Windows 10**, com um tipo de associação **atribuído** .</span><span class="sxs-lookup"><span data-stu-id="d2ec3-126">In **Groups**, add a new **Microsoft 365** or **Security** group named **Managed Windows 10 device users**, with an **Assigned** membership type.</span></span> <span data-ttu-id="d2ec3-127">Nas próximas etapas, você atribuirá sua política de conformidade a esse grupo.</span><span class="sxs-lookup"><span data-stu-id="d2ec3-127">In the next steps, you'll assign your compliance policy to this group.</span></span> 

    <span data-ttu-id="d2ec3-128">Para obter as etapas específicas e informações sobre o **Microsoft 365** ou grupos de **segurança** , consulte [Add groups to organizar Users and Devices](/mem/intune/fundamentals/groups-add).</span><span class="sxs-lookup"><span data-stu-id="d2ec3-128">For the specific steps, and for information on **Microsoft 365** or **Security** groups, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

3. <span data-ttu-id="d2ec3-129">Em **dispositivos**, crie uma política de conformidade do Windows 10.</span><span class="sxs-lookup"><span data-stu-id="d2ec3-129">In **Devices**, create a Windows 10 compliance policy.</span></span> <span data-ttu-id="d2ec3-130">Atribua essa política ao grupo de **usuários do dispositivo do Windows 10 gerenciado** que você criou.</span><span class="sxs-lookup"><span data-stu-id="d2ec3-130">Assign this policy to the **Managed Windows 10 device users** group you created.</span></span>

    <span data-ttu-id="d2ec3-131">Em sua política, você pode bloquear senhas simples, exigir um firewall, exigir que o serviço Microsoft Defender Antimalware esteja em execução e muito mais.</span><span class="sxs-lookup"><span data-stu-id="d2ec3-131">In your policy, you can block simple passwords, require a firewall, require the Microsoft Defender Antimalware service be running, and more.</span></span> <span data-ttu-id="d2ec3-132">Uma política de conformidade normalmente inclui as configurações básicas ou o mínimo que cada dispositivo deve ter.</span><span class="sxs-lookup"><span data-stu-id="d2ec3-132">A compliance policy typically includes the base settings, or bare minimum that every device should have.</span></span>

    <span data-ttu-id="d2ec3-133">Para obter as etapas específicas e obter informações sobre as configurações de conformidade disponíveis que você pode configurar, consulte [usar políticas de conformidade para definir regras para dispositivos que você gerencia](/mem/intune/protect/device-compliance-get-started).</span><span class="sxs-lookup"><span data-stu-id="d2ec3-133">For the specific steps, and for information on the available compliance settings you can configure, see [Use compliance policies to set rules for devices you manage](/mem/intune/protect/device-compliance-get-started).</span></span>

<span data-ttu-id="d2ec3-134">Quando terminar, você tem uma política de conformidade de dispositivo para testar Membros no grupo de **usuários de dispositivos gerenciados do Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="d2ec3-134">When finished, you have a device compliance policy for testing members in the **Managed Windows 10 device users** group.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="d2ec3-135">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="d2ec3-135">Next step</span></span>

<span data-ttu-id="d2ec3-136">Explore recursos de [Gerenciamento de dispositivos móveis](m365-enterprise-test-lab-guides.md#mobile-device-management) e recursos adicionais em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="d2ec3-136">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2ec3-137">Também consulte</span><span class="sxs-lookup"><span data-stu-id="d2ec3-137">See also</span></span>

<span data-ttu-id="d2ec3-138">[Guias de laboratório de teste do Microsoft 365 for Enterprise](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="d2ec3-138">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="d2ec3-139">Registrar dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="d2ec3-139">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="d2ec3-140">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="d2ec3-140">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="d2ec3-141">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="d2ec3-141">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
