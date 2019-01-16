---
title: Ambiente de teste de políticas de conformidade do dispositivo para a sua empresa de 365 da Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para adicionar o ambiente de teste de políticas de conformidade do dispositivo Intune para sua empresa de 365 da Microsoft.
ms.openlocfilehash: 1d957c5cdc888251224bbca43fe82ab0a15e7a93
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865308"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="554a0-103">Ambiente de teste de políticas de conformidade do dispositivo para a sua empresa de 365 da Microsoft</span><span class="sxs-lookup"><span data-stu-id="554a0-103">Device compliance policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="554a0-104">Com as instruções deste artigo, você pode adicionar uma política de conformidade do dispositivo Intune ao seu ambiente de teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="554a0-104">With the instructions in this article, you add an Intune device compliance policy to your Microsoft 365 Enterprise test environment.</span></span>

![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="554a0-106">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="554a0-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="554a0-107">Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="554a0-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="554a0-108">Se você deseja configurar políticas MAM de forma leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="554a0-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="554a0-109">Se você deseja configurar políticas MAM em uma empresa simulada, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="554a0-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="554a0-p101">Testando automatizada de licenciamento e a associação de grupo não requer o ambiente de teste de simulado empresarial, que inclui uma intranet simulada conectada à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar automatizada de licenciamento e a associação ao grupo e experimentar em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="554a0-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="554a0-112">Fase 2: Criar uma política de conformidade do dispositivo para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="554a0-112">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="554a0-113">Nesta fase, você deve criar uma política de conformidade do dispositivo para dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="554a0-113">In this phase, you create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="554a0-114">Vá para o portal do Office em ([https://office.com](https://office.com)) e se conectar à sua assinatura de avaliação do Office 365 com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="554a0-114">Go to the Office portal at ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="554a0-115">Em uma nova guia do navegador, abra o portal do Windows Azure em [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="554a0-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="554a0-116">Na guia portal Azure no seu navegador, no painel de navegação, clique em **todos os serviços**, digite **Intune**e, em seguida, clique em **Intune**.</span><span class="sxs-lookup"><span data-stu-id="554a0-116">On the Azure portal tab in your browser, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="554a0-p102">Se você vir uma mensagem que **você não ativou o gerenciamento de dispositivos ainda** no **Microsoft Intune** blade, clique nele. No blade **autoridade de gerenciamento de dispositivos móveis** , clique em **Intune MDM autoridade**e, em seguida, clique em **Escolher**. Atualize o seu guia de navegador.</span><span class="sxs-lookup"><span data-stu-id="554a0-p102">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="554a0-120">No painel de navegação à esquerda, clique em **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="554a0-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="554a0-121">No blade **grupos-All grupos** , clique em **+ novo grupo**.</span><span class="sxs-lookup"><span data-stu-id="554a0-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="554a0-122">No **grupo** blade, selecione **Office 365** para **tipo de grupo?**, digite **gerenciados Windows 10 usuários de dispositivo** em **nome**, selecione **atribuído** no **tipo de associação**e, em seguida, clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="554a0-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="554a0-123">Feche a folha **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="554a0-123">Close the **Group** blade.</span></span>
    
11. <span data-ttu-id="554a0-124">Feche o blade **grupos grupos a todos** .</span><span class="sxs-lookup"><span data-stu-id="554a0-124">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="554a0-125">No **Microsoft Intune** blade, na lista de **Tarefas rápidas** , clique em **criar uma política de conformidade**.</span><span class="sxs-lookup"><span data-stu-id="554a0-125">On the **Microsoft Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="554a0-126">Na folha **Perfis de Políticas de Conformidade**, clique em **Criar Política**.</span><span class="sxs-lookup"><span data-stu-id="554a0-126">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="554a0-p103">No blade **Criar política** , em **nome**, digite **Windows 10**. Na **plataforma**, selecione **Windows 10 e posterior**, clique **Okey** no blade **política de conformidade do Windows 10** e, em seguida, clique em **criar**. Feche o blade **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="554a0-p103">On the **Create Policy** blade, in **Name**, type **Windows 10**. In **Platform**, select **Windows 10 and later**, click **OK** on the **Windows 10 compliance policy** blade, and then click **Create**. Close the **Windows 10** blade.</span></span>
    
15. <span data-ttu-id="554a0-130">No blade **Perfis de política de conformidade** , clique no nome de política do **Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="554a0-130">On the **Compliance Policy Profiles** blade, click the **Windows 10** policy name.</span></span>
    
16. <span data-ttu-id="554a0-131">No **Windows 10** blade, clique em **atribuições**e clique em **Selecionar grupos a serem incluídos**.</span><span class="sxs-lookup"><span data-stu-id="554a0-131">On the **Windows 10** blade, click **Assignments**, and then click **Select groups to include**.</span></span>
    
17. <span data-ttu-id="554a0-132">No blade **Selecionar grupos a serem incluídos** , clique no grupo de **usuários de dispositivos gerenciados Windows 10** e, em seguida, clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="554a0-132">On the **Select groups to include** blade, click the **Managed Windows 10 device users** group, and then click **Select**.</span></span>
    
18. <span data-ttu-id="554a0-133">Clique em **Salvar**e feche o blade **Windows 10 - atribuições** .</span><span class="sxs-lookup"><span data-stu-id="554a0-133">Click **Save**, and then close the **Windows 10 - Assignments** blade.</span></span>
    
19. <span data-ttu-id="554a0-134">Feche a folha **Perfis de Políticas de Conformidade**.</span><span class="sxs-lookup"><span data-stu-id="554a0-134">Close the **Compliance Policy Profiles** blade.</span></span>
    
20. <span data-ttu-id="554a0-135">No **Microsoft Intune** blade, clique em **aplicativos cliente** no painel de navegação à esquerda.</span><span class="sxs-lookup"><span data-stu-id="554a0-135">On the **Microsoft Intune** blade, click **Client apps** in the left navigation.</span></span>
    
21. <span data-ttu-id="554a0-136">No blade **Aplicativos de cliente** , clique em **aplicativos**e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="554a0-136">On the **Client Apps** blade, click **Apps**, and then click **Add**.</span></span> 

22. <span data-ttu-id="554a0-137">No blade **app adicionar** , selecione **o tipo de aplicativo**e selecione **10 do Windows** em um **Pacote do Office 365**.</span><span class="sxs-lookup"><span data-stu-id="554a0-137">In the **Add app** blade, select **App type**, and then select **Windows 10** under **Office 365 Suite**.</span></span>

23. <span data-ttu-id="554a0-138">Clique em **Configurar pacote de aplicativo**e, em seguida, clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="554a0-138">Click **Configure App Suite**, and then click **OK**.</span></span>

24. <span data-ttu-id="554a0-139">Clique em **Informações do pacote de aplicativo**, digite **Office Apps for Windows 10** em **Nome do pacote**, **aplicativos do Office para o Windows 10** na **Descrição do pacote**e clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="554a0-139">Click **App Suite Information**, type **Office Apps for Windows 10** in **Suite Name**, **Office Apps for Windows 10** in **Suite Description**, and then click **OK**.</span></span>

25. <span data-ttu-id="554a0-140">Clique em **Configurações de pacote do App**, selecione **delimitadas anual** no **canal de atualização**e, em seguida, clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="554a0-140">Click **App Suite Settings**, select **Semi-Annual** in **Update channel**, and then click **OK**.</span></span>

26. <span data-ttu-id="554a0-141">No blade **Add app** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="554a0-141">On the **Add app** blade, click **Add**.</span></span>

<span data-ttu-id="554a0-142">Agora você tem uma política de conformidade do dispositivo para testar os aplicativos selecionados na política de conformidade do dispositivo do **Windows 10** e para membros do grupo **usuários de dispositivos gerenciados Windows 10** .</span><span class="sxs-lookup"><span data-stu-id="554a0-142">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="554a0-143">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="554a0-143">Next step</span></span>

<span data-ttu-id="554a0-144">Explore recursos adicionais de [gerenciamento de dispositivos móveis](m365-enterprise-test-lab-guides.md#mobile-device-management) e capacidades no seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="554a0-144">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="554a0-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="554a0-145">See also</span></span>

<span data-ttu-id="554a0-146">[Guias de laboratório de teste do Microsoft Enterprise 365](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="554a0-146">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="554a0-147">Registre dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="554a0-147">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="554a0-148">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="554a0-148">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="554a0-149">Mobilidade corporativos + segurança (EMS)</span><span class="sxs-lookup"><span data-stu-id="554a0-149">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
