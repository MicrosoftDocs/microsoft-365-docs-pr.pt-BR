---
title: Políticas MAM para o ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para adicionar o ambiente de teste de políticas de gerenciamento (MAM) de aplicativo móvel do Intune para sua empresa de 365 da Microsoft.
ms.openlocfilehash: f00379a5e70dce5e07c031a7647b27041d3fa9d1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865308"
---
# <a name="mam-policies-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c0897-103">Políticas MAM para o ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c0897-103">MAM policies for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c0897-104">Com as instruções deste artigo, você adicionar o ambiente de teste de políticas de gerenciamento (MAM) de aplicativo móvel do Intune para sua empresa de 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c0897-104">With the instructions in this article, you add Intune mobile application management (MAM) policies to your Microsoft 365 Enterprise test environment.</span></span>

![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="c0897-106">Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c0897-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c0897-107">Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c0897-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c0897-108">Se você deseja configurar políticas MAM de forma leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="c0897-108">If you just want to configure MAM policies in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="c0897-109">Se você deseja configurar políticas MAM em uma empresa simulada, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="c0897-109">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c0897-p101">Testando automatizada de licenciamento e a associação de grupo não requer o ambiente de teste de simulado empresarial, que inclui uma intranet simulada conectada à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar automatizada de licenciamento e a associação ao grupo e experimentar em um ambiente que representa uma organização típica.</span><span class="sxs-lookup"><span data-stu-id="c0897-p101">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
>  

## <a name="phase-2-create-and-deploy-mam-policies-for-ios-and-android-devices"></a><span data-ttu-id="c0897-112">Fase 2: Criar e implantar políticas de MAM para dispositivos iOS e Android</span><span class="sxs-lookup"><span data-stu-id="c0897-112">Phase 2: Create and deploy MAM policies for iOS and Android devices</span></span>

<span data-ttu-id="c0897-113">Nesta fase, você criará e implantará duas políticas de MAM diferentes: uma para dispositivos iOS e outra para dispositivos Android.</span><span class="sxs-lookup"><span data-stu-id="c0897-113">In this phase, you create and deploy two different MAM policies: one for iOS devices and one for Android devices.</span></span>
  
1. <span data-ttu-id="c0897-114">Vá para o portal do Office 365 em ([https://portal.office.com](https://portal.office.com)) e se conectar à sua assinatura de avaliação do Office 365 com sua conta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="c0897-114">Go to the Office 365 portal at ([https://portal.office.com](https://portal.office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
2. <span data-ttu-id="c0897-115">Em uma nova guia do navegador, abra o portal do Windows Azure em [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="c0897-115">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>

3. <span data-ttu-id="c0897-116">Na guia Azure portal no Internet Explorer, no painel de navegação, clique em **todos os serviços**, digite **Intune**e, em seguida, clique em **Intune**.</span><span class="sxs-lookup"><span data-stu-id="c0897-116">On the Azure portal tab in Internet Explorer, in the navigation pane, click **All services**, type **Intune**, and then click **Intune**.</span></span>
    
4. <span data-ttu-id="c0897-p102">Se você vir uma mensagem que **você não ativou o gerenciamento de dispositivos ainda** no **Microsoft Intune** blade, clique nele. No blade **autoridade de gerenciamento de dispositivos móveis** , clique em **Intune MDM autoridade**e, em seguida, clique em **Escolher**. Atualize o seu guia de navegador.</span><span class="sxs-lookup"><span data-stu-id="c0897-p102">If you see a **You haven't enabled device management yet** message on the **Microsoft Intune** blade, click it. On the **Mobile Device Management authority** blade, click **Intune MDM Authority**, and then click **Choose**. Refresh your browser tab.</span></span>
    
5. <span data-ttu-id="c0897-120">No painel de navegação à esquerda, clique em **Grupos**.</span><span class="sxs-lookup"><span data-stu-id="c0897-120">In the left navigation pane, click **Groups**.</span></span>
    
6. <span data-ttu-id="c0897-121">No blade **grupos-All grupos** , clique em **+ novo grupo**.</span><span class="sxs-lookup"><span data-stu-id="c0897-121">On the **Groups-All groups** blade, click **+ New Group**.</span></span>
    
7. <span data-ttu-id="c0897-122">No **grupo** blade, selecione **Office 365** para **tipo de grupo?**, digite **gerenciados iOS usuários de dispositivo** em **nome**, selecione **atribuído** no **tipo de associação**e, em seguida, clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="c0897-122">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed iOS device users** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span> 
    
8. <span data-ttu-id="c0897-123">Feche a folha **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="c0897-123">Close the **Group** blade.</span></span>
    
9. <span data-ttu-id="c0897-124">No blade **grupos-All grupos** , clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c0897-124">On the **Groups-All groups** blade, click **Add**.</span></span>
    
10. <span data-ttu-id="c0897-125">No **grupo** blade, selecione **Office 365** para **tipo de grupo?**, digite **gerenciados Android usuário de dispositivo** em **nome**, selecione **atribuído** no **tipo de associação**e, em seguida, clique em **criar**.</span><span class="sxs-lookup"><span data-stu-id="c0897-125">On the **Group** blade, select **Office 365** for **Group type?**, type **Managed Android device user** in **Name**, select **Assigned** in **Membership type**,  and then click **Create**.</span></span>
    
11. <span data-ttu-id="c0897-126">Feche o blade **grupos grupos a todos** .</span><span class="sxs-lookup"><span data-stu-id="c0897-126">Close the **Groups-All groups** blade.</span></span>
    
12. <span data-ttu-id="c0897-127">Na folha **Intune**, na lista **Tarefas rápidas**, clique em **Crie uma política de conformidade**.</span><span class="sxs-lookup"><span data-stu-id="c0897-127">On the **Intune** blade, in the **Quick tasks** list, click **Create a compliance policy**.</span></span>
    
13. <span data-ttu-id="c0897-128">Na folha **Perfis de Políticas de Conformidade**, clique em **Criar Política**.</span><span class="sxs-lookup"><span data-stu-id="c0897-128">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
14. <span data-ttu-id="c0897-p103">Na folha **Criar Política**, em **Nome**, digite **iOS**. Em **Plataforma**, selecione **iOS**, clique em **OK** na folha **Política de conformidade do iOS** e depois clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="c0897-p103">On the **Create Policy** blade, in **Name**, type **iOS**. In **Platform**, select **iOS**, click **OK** on the **iOS compliance policy** blade, and then click **Create**.</span></span>
    
15. <span data-ttu-id="c0897-131">Na folha **Perfis de Políticas de Conformidade**, clique em **Criar Política**.</span><span class="sxs-lookup"><span data-stu-id="c0897-131">On the **Compliance Policy Profiles** blade, click **Create Policy**.</span></span>
    
16. <span data-ttu-id="c0897-p104">Na folha **Criar Política**, em **Nome**, digite **Android**. Em **Plataforma**, selecione **Android**, clique em **OK** na folha **Política de conformidade do Android** e depois clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="c0897-p104">On the **Create Policy** blade, in **Name**, type **Android**. In **Platform**, select **Android**, click **OK** on the **Android compliance policy** blade, and then click **Create**.</span></span>
    
17. <span data-ttu-id="c0897-134">Na folha **Perfis de Políticas de Conformidade**, clique no nome da política **Android**.</span><span class="sxs-lookup"><span data-stu-id="c0897-134">On the **Compliance Policy Profiles** blade, click the **Android** policy name.</span></span>
    
18. <span data-ttu-id="c0897-135">Na navegação à esquerda da folha **Android - Propriedades**, clique em **Atribuições** e depois em **Grupos selecionados**.</span><span class="sxs-lookup"><span data-stu-id="c0897-135">In the left navigation of the **Android - Properties** blade, click **Assignments**, and then click **Select groups**.</span></span>
    
19. <span data-ttu-id="c0897-136">Na folha **Grupos selecionados**, clique no grupo **Usuários de dispositivos Android gerenciados** e depois clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="c0897-136">On the **Select groups** blade, click the **Managed Android device users** group, and then click **Select**.</span></span>
    
20. <span data-ttu-id="c0897-137">Clique em **Salvar**e feche o blade **Android - atribuições** .</span><span class="sxs-lookup"><span data-stu-id="c0897-137">Click **Save**, and then close the **Android - Assignments** blade.</span></span>
    
21. <span data-ttu-id="c0897-138">Na folha **Perfis de Políticas de Conformidade**, clique no nome da política **iOS**.</span><span class="sxs-lookup"><span data-stu-id="c0897-138">On the **Compliance Policy Profiles** blade, click the **iOS** policy name.</span></span>
    
22. <span data-ttu-id="c0897-139">Na navegação à esquerda da folha **iOS - Propriedades**, clique em **Atribuições** e depois em **Grupos selecionados**.</span><span class="sxs-lookup"><span data-stu-id="c0897-139">In the left navigation of the **iOS - Properties** blade, click **Assignments**, and then click **Select groups**.</span></span>
    
23. <span data-ttu-id="c0897-140">Na folha **Grupos selecionados**, clique no grupo **Usuários de dispositivos iOS gerenciados** e depois clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="c0897-140">On the **Select groups** blade, click the **Managed iOS device users** group, and then click **Select**.</span></span>
    
24. <span data-ttu-id="c0897-141">Clique em **Salvar**e feche o blade **iOS - atribuições** .</span><span class="sxs-lookup"><span data-stu-id="c0897-141">Click **Save**, and then close the **iOS - Assignments** blade.</span></span>
    
25. <span data-ttu-id="c0897-142">Feche a folha **Perfis de Políticas de Conformidade**.</span><span class="sxs-lookup"><span data-stu-id="c0897-142">Close the **Compliance Policy Profiles** blade.</span></span>
    
26. <span data-ttu-id="c0897-143">Na folha **Intune**, clique em **Gerenciar aplicativos** na navegação à esquerda.</span><span class="sxs-lookup"><span data-stu-id="c0897-143">On the **Intune** blade, click **Manage apps** in the left navigation.</span></span>
    
27. <span data-ttu-id="c0897-144">Na folha **Aplicativos Móveis**, clique em **Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="c0897-144">On the **Mobile Apps** blade, click **Apps**.</span></span>
    
28. <span data-ttu-id="c0897-145">Na lista de aplicativos, clique em **PowerPoint**, </span><span class="sxs-lookup"><span data-stu-id="c0897-145">In the list of apps, click **PowerPoint**,</span></span> 
    
29. <span data-ttu-id="c0897-p105">Na folha **Visão Geral do PowerPoint**, clique em **Atribuições > Selecionar grupos > Dispositivos iOS gerenciados > Selecionar**. Em **Tipo**, selecione **Disponível** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c0897-p105">On the **PowerPoint Overview** blade, click **Assignments > Select groups > Managed iOS devices > Select**. In **Type**, select **Available**, and then click **Save**.</span></span>
    
30. <span data-ttu-id="c0897-148">Repita a etapa 29 para os seguintes aplicativos:</span><span class="sxs-lookup"><span data-stu-id="c0897-148">Repeat step 29 for the following apps:</span></span>
    
    - <span data-ttu-id="c0897-149">Outlook para Android</span><span class="sxs-lookup"><span data-stu-id="c0897-149">Outlook for Android</span></span>
    
    - <span data-ttu-id="c0897-150">Word para iOS</span><span class="sxs-lookup"><span data-stu-id="c0897-150">Word for iOS</span></span>
    
    - <span data-ttu-id="c0897-151">Excel para iOS</span><span class="sxs-lookup"><span data-stu-id="c0897-151">Excel for iOS</span></span>
    
    - <span data-ttu-id="c0897-152">Outlook para iOS</span><span class="sxs-lookup"><span data-stu-id="c0897-152">Outlook for iOS</span></span>
    
    - <span data-ttu-id="c0897-153">Microsoft Dynamics CRM no iPad para iOS</span><span class="sxs-lookup"><span data-stu-id="c0897-153">Microsoft Dynamics CRM on iPad for iOS</span></span>
    
    - <span data-ttu-id="c0897-154">Microsoft Dynamics CRM no iPhone para iOS</span><span class="sxs-lookup"><span data-stu-id="c0897-154">Microsoft Dynamics CRM on iPhone for iOS</span></span>
    
    - <span data-ttu-id="c0897-155">Dynamics CRM para Telefones para Android</span><span class="sxs-lookup"><span data-stu-id="c0897-155">Dynamics CRM for Phones for Android</span></span>
    
    - <span data-ttu-id="c0897-156">Dynamics CRM para Tablets para Android</span><span class="sxs-lookup"><span data-stu-id="c0897-156">Dynamics CRM for Tablets for Android</span></span>
    
    - <span data-ttu-id="c0897-157">Excel para Android</span><span class="sxs-lookup"><span data-stu-id="c0897-157">Excel for Android</span></span>
    
    - <span data-ttu-id="c0897-158">Word para Android</span><span class="sxs-lookup"><span data-stu-id="c0897-158">Word for Android</span></span>
    
    - <span data-ttu-id="c0897-159">OneNote para iOS</span><span class="sxs-lookup"><span data-stu-id="c0897-159">OneNote for iOS</span></span>
    
31. <span data-ttu-id="c0897-160">Feche a folha **Aplicativos Móveis - Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="c0897-160">Close the **Mobile Apps - Apps** blade.</span></span>
    
32. <span data-ttu-id="c0897-161">Na folha **Aplicativos Móveis**, clique em **Políticas de Proteção de Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="c0897-161">On the **Mobile Apps** blade, click **App Protection Policies**.</span></span>
    
33. <span data-ttu-id="c0897-162">Na folha **Políticas de Proteção de Aplicativo**, clique em **Adicionar uma política**.</span><span class="sxs-lookup"><span data-stu-id="c0897-162">On the **App Protection Policies** blade, click **Add a policy**.</span></span>
    
34. <span data-ttu-id="c0897-163">Na folha **Adicionar uma política**, digite **iOS** e clique em **Selecionar aplicativos necessários**.</span><span class="sxs-lookup"><span data-stu-id="c0897-163">On the **Add a policy** blade, type **iOS**, and then click **Select required apps**.</span></span>
    
35. <span data-ttu-id="c0897-164">Na folha **Aplicativos**, clique em **PowerPoint**, **Microsoft Dynamics CRM no iPhone**, **Excel**, **Microsoft Dynamics CRM no iPhone**, **Word**, **OneNote** e **Outlook** e depois clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="c0897-164">On the **Apps** blade, click **PowerPoint**, **Microsoft Dynamics CRM on iPhone**, **Excel**, **Microsoft Dynamics CRM on iPhone**, **Word**, **OneNote**, and **Outlook**, and then click **Select**.</span></span>
    
36. <span data-ttu-id="c0897-165">Na folha **Adicionar uma política**, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="c0897-165">On the **Add a policy** blade, click **Create**.</span></span>
    
37. <span data-ttu-id="c0897-166">Na folha **Políticas de Proteção de Aplicativo**, clique em **Adicionar uma política**.</span><span class="sxs-lookup"><span data-stu-id="c0897-166">On the **App Protection Policies** blade, click **Add a policy**.</span></span>
    
38. <span data-ttu-id="c0897-167">Na folha **Adicionar uma política**, digite **Android**, selecione **Android** em **Plataforma** e clique em **Selecionar aplicativos necessários**.</span><span class="sxs-lookup"><span data-stu-id="c0897-167">On the **Add a policy** blade, type **Android**, select **Android** in **Platform**, and then click **Select required apps**.</span></span>
    
39. <span data-ttu-id="c0897-168">Na folha **Aplicativos**, clique em **PowerPoint**, **Dynamics CRM para tablets**, **Excel**, **Word**, **Outlook** e **Dynamics CRM para telefones**. Em seguida, clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="c0897-168">On the **Apps** blade, click **PowerPoint**, **Dynamics CRM for tablets**, **Excel**, **Word**, **Outlook**, and **Dynamics CRM for phones**, and then click **Select**.</span></span>
    
40. <span data-ttu-id="c0897-169">Na folha **Adicionar uma política**, clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="c0897-169">On the **Add a policy** blade, click **Create**.</span></span>
    
<span data-ttu-id="c0897-170">Agora, você tem duas políticas de MAM, uma para dispositivos iOS e outra para dispositivos Android, e está pronto para trabalhar com configurações de teste para os aplicativos selecionados.</span><span class="sxs-lookup"><span data-stu-id="c0897-170">You now have two MAM policies, one for iOS devices and one for Android devices, and are ready to experiment with testing settings for the selected apps.</span></span> 
  
## <a name="next-step"></a><span data-ttu-id="c0897-171">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="c0897-171">Next step</span></span>

<span data-ttu-id="c0897-172">Explore recursos adicionais de [gerenciamento de dispositivos móveis](m365-enterprise-test-lab-guides.md#mobile-device-management) e capacidades no seu ambiente de teste.</span><span class="sxs-lookup"><span data-stu-id="c0897-172">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0897-173">Confira também</span><span class="sxs-lookup"><span data-stu-id="c0897-173">See also</span></span>

<span data-ttu-id="c0897-174">[Guias de laboratório de teste do Microsoft Enterprise 365](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="c0897-174">[Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="c0897-175">Registre dispositivos iOS e Android em seu ambiente de teste do Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c0897-175">Enroll iOS and Android devices in your Microsoft 365 Enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="c0897-176">Implantar o Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c0897-176">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="c0897-177">Mobilidade corporativos + segurança (EMS)</span><span class="sxs-lookup"><span data-stu-id="c0897-177">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
