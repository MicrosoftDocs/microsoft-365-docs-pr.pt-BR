---
title: Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 Enterprise
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
description: Use este guia de laboratório de teste para adicionar políticas de conformidade de dispositivo do Intune ao seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 8a746f99e16444527c44267eddbaec9f5e5156eb
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40801626"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c1fbf-103">Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c1fbf-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c1fbf-104">*Este Guia de Laboratório de Testes pode ser usado apenas em ambientes de teste do Microsoft 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c1fbf-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="c1fbf-105">Com as instruções deste artigo, você adiciona uma política de conformidade de dispositivo do Intune para dispositivos Windows 10 e Office 365 ProPlus ao seu ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-105">With the instructions in this article, you add an Intune device compliance policy for Windows 10 devices and Office 365 ProPlus to your Microsoft 365 Enterprise test environment.</span></span>

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="c1fbf-107">Clique [aqui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c1fbf-108">Fase 1: Criar o ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c1fbf-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c1fbf-109">Se você só quiser configurar as políticas de MAM de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="c1fbf-109">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="c1fbf-110">Se você quiser configurar as políticas de MAM em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="c1fbf-110">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c1fbf-111">Testar o licenciamento automatizado e a associação de grupo não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="c1fbf-111">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="c1fbf-112">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="c1fbf-113">Fase 2: criar uma política de conformidade de dispositivo para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="c1fbf-113">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="c1fbf-114">Nesta fase, você cria uma política de conformidade de dispositivo para dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-114">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="c1fbf-115">Vá para o portal do Office 365 em[https://portal.office.com](https://portal.office.com)() e entre na sua assinatura de laboratório de teste do Office 365 com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-115">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="c1fbf-116">Em uma nova guia do navegador, abra o portal do Azure em [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="c1fbf-116">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="c1fbf-117">Na guia portal do Azure no navegador, digite **Intune** na caixa de pesquisa e clique em **Intune**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-117">From the Azure portal tab in your browser, type **Intune** in the search box, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="c1fbf-118">Se você vir uma mensagem de **Gerenciamento de dispositivo ainda não habilitada** no painel do **Microsoft Intune** , clique nela.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-118">If you see a **You haven't enabled device management yet** message In the **Microsoft Intune** pane, click it.</span></span> <span data-ttu-id="c1fbf-119">No painel **autoridade de gerenciamento de dispositivo móvel** , clique em **autoridade MDM do Intune**e, em seguida, clique em **escolher**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-119">In the **Mobile Device Management authority** pane, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="c1fbf-120">Atualize a guia do navegador.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-120">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="c1fbf-121">No painel de navegação à esquerda, clique em **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-121">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="c1fbf-122">No painel **grupos-todos os grupos** , clique em **+ novo grupo**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-122">In the **Groups-All groups** pane, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="c1fbf-123">No painel de **grupo** , selecione **Office 365** ou **segurança** para **tipo de grupo?**, digite **usuários do dispositivo gerenciados do Windows 10** em **nome**, selecione **atribuído** em **tipo de associação**e clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-123">In the **Group** pane, select **Office 365** or **Security** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="c1fbf-124">Clique em **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-124">Click **Microsoft Intune**.</span></span> <span data-ttu-id="c1fbf-125">No painel do **Microsoft Intune** , na lista **tarefas rápidas** , clique em **criar uma política de conformidade**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-125">In the **Microsoft Intune** pane, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
9. <span data-ttu-id="c1fbf-126">No painel **perfis de política de conformidade** , clique em **criar política**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-126">In the **Compliance Policy Profiles** pane, click **Create Policy**.</span></span>
    
10. <span data-ttu-id="c1fbf-127">No painel **criar política** , em **nome**, digite **Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-127">In the **Create Policy** pane, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="c1fbf-128">Em **plataforma**, selecione **Windows 10 e posterior**, clique em **OK** no painel de **política de conformidade do Windows 10** e, em seguida, clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-128">In **Platform**, select **Windows 10 and later**, click **OK** In the **Windows 10 compliance policy** pane, and then click **Create**.</span></span> 
    
11. <span data-ttu-id="c1fbf-129">Clique em **perfis de política de conformidade**e, em seguida, clique no nome da política do **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="c1fbf-129">Click **Compliance Policy Profiles**, and then click the **Windows 10** policy name.</span></span>
    
12. <span data-ttu-id="c1fbf-130">No painel do **Windows 10** , clique em **atribuições**e, em seguida, clique em **Selecionar grupos para incluir**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-130">In the **Windows 10** pane, click **Assignments**, and then click **Select groups to include**.</span></span>
    
13. <span data-ttu-id="c1fbf-131">No painel **Selecionar grupos para incluir** , clique no grupo **usuários do dispositivo gerenciado do Windows 10** e clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-131">In the **Select groups to include** pane, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
14. <span data-ttu-id="c1fbf-132">Clique em **salvar**, clique em **Microsoft Intune-visão geral**e, em seguida, clique em **aplicativos cliente** no painel de navegação à esquerda.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-132">Click **Save**, click **Microsoft Intune-Overview**, and then click **Client apps** in the left navigation.</span></span>
    
15. <span data-ttu-id="c1fbf-133">No painel **aplicativos cliente** , clique em **aplicativos**e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-133">In the **Client Apps** pane, click **Apps**, and then click **Add**.</span></span> 

16. <span data-ttu-id="c1fbf-134">No painel **Adicionar aplicativo** , selecione **tipo de aplicativo**e, em seguida, selecione **Windows 10** no **pacote do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-134">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

17. <span data-ttu-id="c1fbf-135">No painel **Adicionar aplicativo** , selecione **informações do pacote de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-135">In the **Add App** pane, select **App Suite Information**.</span></span>
 
18. <span data-ttu-id="c1fbf-136">No painel de **informações do App Suite** , digite **Office 365 ProPlus** em **nome** e **Descrição**do pacote.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-136">In the **App Suite Information** pane, type **Office 365 ProPlus** in both **Suite Name** and **Suite Description**.</span></span>
<span data-ttu-id="c1fbf-137">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-137">Click OK.</span></span>

19. <span data-ttu-id="c1fbf-138">No painel **Adicionar aplicativo** , selecione **Configurar pacote de aplicativos**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-138">In the **Add App** pane, select **Configure App Suite**, and then click **OK**.</span></span>

20. <span data-ttu-id="c1fbf-139">No painel **Adicionar aplicativo** , selecione **configurações de pacote de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-139">In the **Add App** pane, select **App Suite Settings**.</span></span>

21. <span data-ttu-id="c1fbf-140">Em **canal de atualização**, selecione **semestral**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-140">For **Update Channel**, select **Semi-Annual**, and then click **OK**.</span></span>

22. <span data-ttu-id="c1fbf-141">No painel **Adicionar aplicativo** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-141">In the **Add app** pane, click **Add**.</span></span>

<span data-ttu-id="c1fbf-142">Agora você tem uma política de conformidade de dispositivo para testar os aplicativos selecionados na política de conformidade de dispositivo do **Windows 10** e para os membros do grupo de **usuários de dispositivos gerenciados do Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="c1fbf-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="c1fbf-143">Observe que a seleção do Office 365 como o tipo de grupo criará recursos adicionais.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-143">Please note that selecting Office 365 as the group type will create additional resources.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="c1fbf-144">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="c1fbf-144">Next step</span></span>

<span data-ttu-id="c1fbf-145">Explore recursos de [Gerenciamento de dispositivos móveis](m365-enterprise-test-lab-guides.md#mobile-device-management) e recursos adicionais em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="c1fbf-145">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1fbf-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="c1fbf-146">See also</span></span>

<span data-ttu-id="c1fbf-147">[Guias de laboratório de teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="c1fbf-147">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="c1fbf-148">Registrar dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c1fbf-148">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="c1fbf-149">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c1fbf-149">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="c1fbf-150">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="c1fbf-150">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
