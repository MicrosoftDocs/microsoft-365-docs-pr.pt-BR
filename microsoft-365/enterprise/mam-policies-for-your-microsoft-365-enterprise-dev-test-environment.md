---
title: Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para adicionar políticas de conformidade de dispositivo do Intune ao seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 5b587bd702071f325310ebd9979cf611f20e3205
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279059"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="49ea4-103">Políticas de conformidade de dispositivo para seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="49ea4-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="49ea4-104">Com as instruções deste artigo, você adiciona uma política de conformidade de dispositivo do Intune ao seu ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="49ea4-104">With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.</span></span>

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="49ea4-106">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="49ea4-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="49ea4-107">Fase 1: criar seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="49ea4-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="49ea4-108">Se você só quiser configurar as políticas de MAM de forma leve com os requisitos mínimos, siga as instruções em [configuração básica leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="49ea4-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="49ea4-109">Se você quiser configurar as políticas de MAM em uma empresa simulada, siga as instruções em [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="49ea4-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="49ea4-110">Testar o licenciamento automatizado e a associação de grupo não requer o ambiente de teste corporativo simulado, que inclui uma intranet simulada conectada à Internet e a sincronização de diretórios para uma floresta dos serviços de domínio Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="49ea4-110">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="49ea4-111">Ele é fornecido aqui como uma opção para que você possa testar o licenciamento e a associação de grupo automatizados e experimentá-lo em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="49ea4-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="49ea4-112">Fase 2: criar uma política de conformidade de dispositivo para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="49ea4-112">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="49ea4-113">Nesta fase, você cria uma política de conformidade de dispositivo para dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="49ea4-113">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="49ea4-114">Vá para o portal do Office em[https://office.com](https://office.com)() e entre na sua assinatura de avaliação do Office 365 com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="49ea4-114">Go to the Office portal at ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="49ea4-115">Em uma nova guia do navegador, abra o portal do Azure em [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="49ea4-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="49ea4-116">Na guia portal do Azure no navegador, no painel de navegação, clique em **todos os serviços**, digite **Intune**e clique em **Intune**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-116">On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="49ea4-117">Se você vir uma mensagem de **Gerenciamento de dispositivo que ainda não tenha sido habilitada** na lâmina do **Microsoft Intune** , clique nela.</span><span class="sxs-lookup"><span data-stu-id="49ea4-117">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it.</span></span> <span data-ttu-id="49ea4-118">Na folha **autoridade de gerenciamento de dispositivo móvel** , clique em **autoridade MDM do Intune**e, em seguida, clique em **escolher**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-118">On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**.</span></span> <span data-ttu-id="49ea4-119">Atualize a guia do navegador.</span><span class="sxs-lookup"><span data-stu-id="49ea4-119">Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="49ea4-120">No painel de navegação à esquerda, clique em **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="49ea4-121">Na folha **grupos-todos os grupos** , clique em **+ novo grupo**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="49ea4-122">Na folha **grupo** , selecione **Office 365** para **tipo de grupo?**, digite **usuários do dispositivo gerenciados do Windows 10** em **nome**, selecione **atribuído** em **tipo de associação**e clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="49ea4-123">Feche a folha **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-123">Close the **Group** blade.</span></span>
    
11. <span data-ttu-id="49ea4-124">Feche a folha **grupos-todos os grupos** .</span><span class="sxs-lookup"><span data-stu-id="49ea4-124">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="49ea4-125">Na folha do **Microsoft Intune** , na lista **tarefas rápidas** , clique em **criar uma política de conformidade**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-125">On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="49ea4-126">Na folha **Perfis de Políticas de Conformidade**, clique em **Criar Política**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-126">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="49ea4-127">Na folha **criar política** , em **nome**, digite **Windows 10**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-127">On the **Create Policy** blade, in **Name**, type **Windows 10**.</span></span> <span data-ttu-id="49ea4-128">Em **plataforma**, selecione **Windows 10 e posterior**, clique em **OK** na folha de **política de conformidade do Windows 10** e, em seguida, clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-128">In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**.</span></span> <span data-ttu-id="49ea4-129">Feche a lâmina do **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="49ea4-129">Close the **Windows 10** blade.</span></span>
    
15. <span data-ttu-id="49ea4-130">Na folha **perfis de política de conformidade** , clique no nome da política do **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="49ea4-130">On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.</span></span>
    
16. <span data-ttu-id="49ea4-131">Na folha **Windows 10** , clique em **atribuições**e clique em **Selecionar grupos para incluir**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-131">On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.</span></span>
    
17. <span data-ttu-id="49ea4-132">Na folha **Selecionar grupos para incluir** , clique no grupo **usuários do dispositivo gerenciado do Windows 10** e clique em **selecionar**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-132">On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
18. <span data-ttu-id="49ea4-133">Clique em **salvar**e feche a folha **Windows 10-atribuições** .</span><span class="sxs-lookup"><span data-stu-id="49ea4-133">Click **Save**, and then close the **Windows 10 - Assignments** blade.</span></span>
    
19. <span data-ttu-id="49ea4-134">Feche a folha **Perfis de Políticas de Conformidade**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-134">Close the **Compliance Policy Profiles** blade.</span></span>
    
20. <span data-ttu-id="49ea4-135">Na folha do **Microsoft Intune** , clique em **aplicativos cliente** no painel de navegação à esquerda.</span><span class="sxs-lookup"><span data-stu-id="49ea4-135">On the **Microsoft Intune** blade, click **Client apps** in the left navigation.</span></span>
    
21. <span data-ttu-id="49ea4-136">Na folha **aplicativos cliente** , clique em **aplicativos**e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-136">On the **Client Apps** blade, click **Apps**, and then click **Add**.</span></span> 

22. <span data-ttu-id="49ea4-137">Na folha **Adicionar aplicativo** , selecione **tipo de aplicativo**e, em seguida, selecione **Windows 10** no **pacote do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-137">In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

23. <span data-ttu-id="49ea4-138">Clique em **Configurar pacote de aplicativos**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-138">Click **Configure App Suite**, and then click **OK**.</span></span>

24. <span data-ttu-id="49ea4-139">Clique em **informações do pacote de aplicativos**, digite aplicativos do **Office para Windows 10** no **nome do pacote**, **aplicativos do Office para Windows 10** descrição do **pacote**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-139">Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.</span></span>

25. <span data-ttu-id="49ea4-140">Clique **em configurações do pacote de aplicativos**, selecione **semestral** no **canal de atualização**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-140">Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.</span></span>

26. <span data-ttu-id="49ea4-141">Na folha **Adicionar aplicativo** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="49ea4-141">On the **Add app** blade, click **Add**.</span></span>

<span data-ttu-id="49ea4-142">Agora você tem uma política de conformidade de dispositivo para testar os aplicativos selecionados na política de conformidade de dispositivo do **Windows 10** e para os membros do grupo de **usuários de dispositivos gerenciados do Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="49ea4-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="49ea4-143">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="49ea4-143">Next step</span></span>

<span data-ttu-id="49ea4-144">Explore recursos de [Gerenciamento de dispositivos móveis](m365-enterprise-test-lab-guides.md#mobile-device-management) e recursos adicionais em seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="49ea4-144">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="49ea4-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="49ea4-145">See also</span></span>

<span data-ttu-id="49ea4-146">[Guias de laboratório de teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="49ea4-146">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="49ea4-147">Registrar dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="49ea4-147">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="49ea4-148">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="49ea4-148">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="49ea4-149">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="49ea4-149">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
