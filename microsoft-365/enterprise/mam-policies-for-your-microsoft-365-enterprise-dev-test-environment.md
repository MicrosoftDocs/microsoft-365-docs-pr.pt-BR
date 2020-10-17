---
title: Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 for Enterprise
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para adicionar políticas de conformidade de dispositivo do Intune ao seu ambiente de teste do Microsoft 365 for Enterprise.
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487407"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="87b23-103">Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="87b23-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="87b23-104">*Este guia de laboratório de teste só pode ser usado para o Microsoft 365 para ambientes de teste corporativos.*</span><span class="sxs-lookup"><span data-stu-id="87b23-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="87b23-105">Este artigo descreve como adicionar uma política de conformidade de dispositivo do Intune para dispositivos Windows 10 e aplicativos da Microsoft 365 para empresas ao seu ambiente de teste do Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="87b23-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="87b23-106">A adição de uma política de conformidade de dispositivo do Intune envolve duas fases:</span><span class="sxs-lookup"><span data-stu-id="87b23-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="87b23-107">Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="87b23-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="87b23-108">Fase 2: criar uma política de conformidade de dispositivo para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="87b23-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Guias de Laboratório de Teste do Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="87b23-110">Para obter um mapa Visual para todos os artigos da pilha do guia do laboratório de teste do Microsoft 365 for Enterprise, vá para a [pilha do guia do laboratório de teste da microsoft 365 para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="87b23-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="87b23-111">Fase 1: desenvolver seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="87b23-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="87b23-112">Se você quiser configurar as políticas de MAM de forma simples com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="87b23-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="87b23-113">Se você quiser configurar as políticas de MAM em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="87b23-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="87b23-114">Testar o licenciamento automatizado e a associação de grupo não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="87b23-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="87b23-115">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="87b23-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="87b23-116">Fase 2: criar uma política de conformidade de dispositivo para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="87b23-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="87b23-117">Nesta fase, crie uma política de conformidade de dispositivo para dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="87b23-117">In this phase, create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="87b23-118">Vá para o [centro de administração do microsoft 365](https://admin.microsoft.com) e entre na sua assinatura de laboratório de teste do Microsoft 365 com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="87b23-118">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
1. <span data-ttu-id="87b23-119">Em uma nova guia do navegador, abra o portal do Azure em [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="87b23-119">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
1. <span data-ttu-id="87b23-120">Na caixa de pesquisa do portal do Azure, insira o **Intune**e, em seguida, selecione **Intune**.</span><span class="sxs-lookup"><span data-stu-id="87b23-120">In the search box of the Azure portal, enter **Intune**, and then select **Intune**.</span></span>
1. <span data-ttu-id="87b23-121">Se você vir uma mensagem de **Gerenciamento de dispositivo ainda não habilitada** no painel do **Microsoft Intune** , selecione-a.</span><span class="sxs-lookup"><span data-stu-id="87b23-121">If you see a **You haven't enabled device management yet** message in the **Microsoft Intune** pane, select it.</span></span> <span data-ttu-id="87b23-122">No painel **autoridade de gerenciamento de dispositivo móvel** , selecione **autoridade MDM do Intune**e selecione **escolher**.</span><span class="sxs-lookup"><span data-stu-id="87b23-122">In the **Mobile Device Management authority** pane, select **Intune MDM Authority**, and then select **Choose**.</span></span>
1. <span data-ttu-id="87b23-123">Atualize a guia do navegador.</span><span class="sxs-lookup"><span data-stu-id="87b23-123">Refresh your browser tab.</span></span>
1. <span data-ttu-id="87b23-124">No painel de navegação esquerdo, selecione **grupos**.</span><span class="sxs-lookup"><span data-stu-id="87b23-124">In the left navigation pane, select **Groups**.</span></span>
1. <span data-ttu-id="87b23-125">No painel **grupos-todos os grupos** , selecione **+ novo grupo**.</span><span class="sxs-lookup"><span data-stu-id="87b23-125">In the **Groups-All groups** pane, select **+ New Group**.</span></span>
1. <span data-ttu-id="87b23-126">No painel de **grupo** , selecione **Microsoft 365** ou **segurança** para **tipo de grupo?**, insira **usuários do dispositivo gerenciados do Windows 10** em **nome**, selecione **atribuído** em **tipo de associação**e, em seguida, selecione **criar**.</span><span class="sxs-lookup"><span data-stu-id="87b23-126">In the **Group** pane, select **Microsoft 365** or **Security** for **Group type?**, enter **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then select **Create**.</span></span>
1. <span data-ttu-id="87b23-127">Selecione **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="87b23-127">Select **Microsoft Intune**.</span></span>
1. <span data-ttu-id="87b23-128">No painel do **Microsoft Intune** , na lista **tarefas rápidas** , selecione **criar uma política de conformidade**.</span><span class="sxs-lookup"><span data-stu-id="87b23-128">In the **Microsoft Intune** pane, in the **Quick tasks** list, select **Create a compliance policy**.</span></span>
1. <span data-ttu-id="87b23-129">No painel **perfis de política de conformidade** , selecione **criar política**.</span><span class="sxs-lookup"><span data-stu-id="87b23-129">In the **Compliance Policy Profiles** pane, select **Create Policy**.</span></span>
1. <span data-ttu-id="87b23-130">No painel **criar política** , em **nome**, digite **Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="87b23-130">In the **Create Policy** pane, in **Name**, enter **Windows 10**.</span></span> <span data-ttu-id="87b23-131">Em **plataforma**, selecione **Windows 10 e posterior**, selecione **OK** no painel **política de conformidade do Windows 10** e, em seguida, selecione **criar**.</span><span class="sxs-lookup"><span data-stu-id="87b23-131">In **Platform**, select **Windows 10 and later**, select **OK** in the **Windows 10 compliance policy** pane, and then select **Create**.</span></span>
1. <span data-ttu-id="87b23-132">Selecione **perfis de política de conformidade**e, em seguida, selecione o nome da política do **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="87b23-132">Select **Compliance Policy Profiles**, and then select the **Windows 10** policy name.</span></span>
1. <span data-ttu-id="87b23-133">No painel do **Windows 10** , selecione **atribuições**e selecione **grupos para incluir**.</span><span class="sxs-lookup"><span data-stu-id="87b23-133">In the **Windows 10** pane, select **Assignments**, and then select **Select groups to include**.</span></span>
1. <span data-ttu-id="87b23-134">No painel **Selecionar grupos para incluir** , selecione o grupo **usuários do dispositivo gerenciado do Windows 10** e selecione **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="87b23-134">In the **Select groups to include** pane, select the **Managed Windows 10 device users** group, and then select **Select**.</span></span>
1. <span data-ttu-id="87b23-135">Selecione **salvar**, selecione **Microsoft Intune-visão geral**e, em seguida, selecione **aplicativos cliente** no painel de navegação à esquerda.</span><span class="sxs-lookup"><span data-stu-id="87b23-135">Select **Save**, select **Microsoft Intune-Overview**, and then select **Client apps** in the left navigation.</span></span>
1. <span data-ttu-id="87b23-136">No painel **aplicativos cliente** , selecione **aplicativos**e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="87b23-136">In the **Client Apps** pane, select **Apps**, and then select **Add**.</span></span>
1. <span data-ttu-id="87b23-137">No painel **Adicionar aplicativo** , selecione **tipo de aplicativo**e, em seguida, selecione **Windows 10** no **Microsoft 365 Suite**.</span><span class="sxs-lookup"><span data-stu-id="87b23-137">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Microsoft 365 Suite**.</span></span>
1. <span data-ttu-id="87b23-138">No painel **Adicionar aplicativo** , selecione **informações do pacote de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="87b23-138">In the **Add App** pane, select **App Suite Information**.</span></span>
1. <span data-ttu-id="87b23-139">No painel de **informações do pacote de aplicativos** , digite **Microsoft 365 aplicativos para empresas** em **nome do pacote** e **Descrição do pacote**e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="87b23-139">In the **App Suite Information** pane, enter **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**, and then select **OK**.</span></span>
1. <span data-ttu-id="87b23-140">No painel **Adicionar aplicativo** , selecione **Configurar pacote de aplicativos**e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="87b23-140">In the **Add App** pane, select **Configure App Suite**, and then select **OK**.</span></span>
1. <span data-ttu-id="87b23-141">No painel **Adicionar aplicativo** , selecione **configurações de pacote de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="87b23-141">In the **Add App** pane, select **App Suite Settings**.</span></span>
1. <span data-ttu-id="87b23-142">Em **canal de atualização**, selecione **Enterprise semestral**e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="87b23-142">For **Update Channel**, select **Semi-Annual Enterprise**, and then select **OK**.</span></span>
1. <span data-ttu-id="87b23-143">No painel **Adicionar aplicativo** , selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="87b23-143">In the **Add app** pane, select **Add**.</span></span>

<span data-ttu-id="87b23-144">Agora você tem uma política de conformidade de dispositivo para testar os aplicativos selecionados na política de conformidade de dispositivo do **Windows 10** e para os membros do grupo de **usuários de dispositivos gerenciados do Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="87b23-144">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="87b23-145">Observe que a seleção do **Microsoft 365** como o tipo de grupo cria recursos adicionais.</span><span class="sxs-lookup"><span data-stu-id="87b23-145">Please note that selecting **Microsoft 365** as the group type creates additional resources.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="87b23-146">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="87b23-146">Next step</span></span>

<span data-ttu-id="87b23-147">Explore recursos de [Gerenciamento de dispositivos móveis](m365-enterprise-test-lab-guides.md#mobile-device-management) e recursos adicionais em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="87b23-147">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="87b23-148">Confira também</span><span class="sxs-lookup"><span data-stu-id="87b23-148">See also</span></span>

<span data-ttu-id="87b23-149">[Guias de laboratório de teste do Microsoft 365 for Enterprise](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="87b23-149">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="87b23-150">Registrar dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="87b23-150">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="87b23-151">Visão geral do Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="87b23-151">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="87b23-152">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="87b23-152">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
