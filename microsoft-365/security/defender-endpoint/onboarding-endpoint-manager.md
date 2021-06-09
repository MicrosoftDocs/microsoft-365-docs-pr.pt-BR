---
title: Integração usando o Microsoft Endpoint Manager
description: Saiba como fazer a integração com o Microsoft Defender para Ponto de Extremidade usando Microsoft Endpoint Manager
keywords: onboarding, configuration, deploy, deployment, endpoint manager, Microsoft Defender for Endpoint, collection creation, endpoint detection response, next generation protection, attack surface reduction, microsoft endpoint manager
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f3442528f6d9239219f0b4638f75758a055717de
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842633"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a><span data-ttu-id="27a89-104">Integração usando o Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="27a89-104">Onboarding using Microsoft Endpoint Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="27a89-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="27a89-105">**Applies to:**</span></span>
- [<span data-ttu-id="27a89-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="27a89-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="27a89-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27a89-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="27a89-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="27a89-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="27a89-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="27a89-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="27a89-110">Este artigo faz parte do guia implantação e age como um exemplo de método de integração.</span><span class="sxs-lookup"><span data-stu-id="27a89-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="27a89-111">No tópico [Planejamento,](deployment-strategy.md) havia vários métodos fornecidos para os dispositivos de integração ao serviço.</span><span class="sxs-lookup"><span data-stu-id="27a89-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="27a89-112">Este tópico aborda a arquitetura nativa da nuvem.</span><span class="sxs-lookup"><span data-stu-id="27a89-112">This topic covers the cloud-native architecture.</span></span> 

<span data-ttu-id="27a89-113">![Imagem da arquitetura nativa da nuvem ](images/cloud-native-architecture.png)
 *Diagrama de arquiteturas de ambiente*</span><span class="sxs-lookup"><span data-stu-id="27a89-113">![Image of cloud-native architecture](images/cloud-native-architecture.png)
*Diagram of environment architectures*</span></span>

<span data-ttu-id="27a89-114">Embora o Defender para Ponto de Extremidade suporte à integração de vários pontos de extremidade e ferramentas, este artigo não os abrange.</span><span class="sxs-lookup"><span data-stu-id="27a89-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="27a89-115">Para obter informações sobre a integração geral usando outras ferramentas e métodos de implantação com suporte, consulte [Onboarding overview](onboarding.md).</span><span class="sxs-lookup"><span data-stu-id="27a89-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>


<span data-ttu-id="27a89-116">[Microsoft Endpoint Manager](/mem/endpoint-manager-overview) é uma plataforma de solução que unifica vários serviços.</span><span class="sxs-lookup"><span data-stu-id="27a89-116">[Microsoft Endpoint Manager](/mem/endpoint-manager-overview) is a solution platform that unifies several services.</span></span> <span data-ttu-id="27a89-117">Ele inclui [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) para gerenciamento de dispositivos baseados em nuvem.</span><span class="sxs-lookup"><span data-stu-id="27a89-117">It includes [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) for cloud-based device management.</span></span>


<span data-ttu-id="27a89-118">Este tópico orienta os usuários em:</span><span class="sxs-lookup"><span data-stu-id="27a89-118">This topic guides users in:</span></span>
- <span data-ttu-id="27a89-119">Etapa 1: Integrando dispositivos ao serviço criando um grupo no Microsoft Endpoint Manager (MEM) para atribuir configurações em</span><span class="sxs-lookup"><span data-stu-id="27a89-119">Step 1: Onboarding devices to the service by creating a group in Microsoft Endpoint Manager (MEM) to assign configurations on</span></span>
- <span data-ttu-id="27a89-120">Etapa 2: Configurar o Defender para recursos de ponto de extremidade usando Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="27a89-120">Step 2: Configuring Defender for Endpoint capabilities using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="27a89-121">Essas diretrizes de integração orientarão você pelas seguintes etapas básicas que você precisa seguir ao usar Microsoft Endpoint Manager:</span><span class="sxs-lookup"><span data-stu-id="27a89-121">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Manager:</span></span>

-   [<span data-ttu-id="27a89-122">Identificar dispositivos de destino ou usuários</span><span class="sxs-lookup"><span data-stu-id="27a89-122">Identifying target devices or users</span></span>](#identify-target-devices-or-users)

    -   <span data-ttu-id="27a89-123">Criando um Azure Active Directory (Usuário ou Dispositivo)</span><span class="sxs-lookup"><span data-stu-id="27a89-123">Creating an Azure Active Directory group (User or Device)</span></span>

-   [<span data-ttu-id="27a89-124">Criando um Perfil de Configuração</span><span class="sxs-lookup"><span data-stu-id="27a89-124">Creating a Configuration Profile</span></span>](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)

    -   <span data-ttu-id="27a89-125">Em Microsoft Endpoint Manager, vamos orientá-lo na criação de uma política separada para cada recurso.</span><span class="sxs-lookup"><span data-stu-id="27a89-125">In Microsoft Endpoint Manager, we'll guide you in creating a separate policy for each capability.</span></span>





## <a name="resources"></a><span data-ttu-id="27a89-126">Recursos</span><span class="sxs-lookup"><span data-stu-id="27a89-126">Resources</span></span>


<span data-ttu-id="27a89-127">Aqui estão os links necessários para o restante do processo:</span><span class="sxs-lookup"><span data-stu-id="27a89-127">Here are the links you'll need for the rest of the process:</span></span>

-   [<span data-ttu-id="27a89-128">Portal de MEM</span><span class="sxs-lookup"><span data-stu-id="27a89-128">MEM portal</span></span>](https://aka.ms/memac)

-   [<span data-ttu-id="27a89-129">Central de Segurança</span><span class="sxs-lookup"><span data-stu-id="27a89-129">Security Center</span></span>](https://securitycenter.windows.com/)

-   [<span data-ttu-id="27a89-130">Linhas de base de segurança do Intune</span><span class="sxs-lookup"><span data-stu-id="27a89-130">Intune Security baselines</span></span>](/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

<span data-ttu-id="27a89-131">Para obter mais informações Microsoft Endpoint Manager, confira estes recursos:</span><span class="sxs-lookup"><span data-stu-id="27a89-131">For more information about Microsoft Endpoint Manager, check out these resources:</span></span>
- [<span data-ttu-id="27a89-132">Microsoft Endpoint Manager página</span><span class="sxs-lookup"><span data-stu-id="27a89-132">Microsoft Endpoint Manager page</span></span>](/mem/)
- [<span data-ttu-id="27a89-133">Postagem de blog sobre convergência do Intune e ConfigMgr</span><span class="sxs-lookup"><span data-stu-id="27a89-133">Blog post on convergence of Intune and ConfigMgr</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [<span data-ttu-id="27a89-134">Vídeo de introdução no MEM</span><span class="sxs-lookup"><span data-stu-id="27a89-134">Introduction video on MEM</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a><span data-ttu-id="27a89-135">Etapa 1: Integrando dispositivos criando um grupo no MEM para atribuir configurações em</span><span class="sxs-lookup"><span data-stu-id="27a89-135">Step 1: Onboard devices by creating a group in MEM to assign configurations on</span></span>
### <a name="identify-target-devices-or-users"></a><span data-ttu-id="27a89-136">Identificar dispositivos de destino ou usuários</span><span class="sxs-lookup"><span data-stu-id="27a89-136">Identify target devices or users</span></span>
<span data-ttu-id="27a89-137">Nesta seção, criaremos um grupo de teste para atribuir suas configurações.</span><span class="sxs-lookup"><span data-stu-id="27a89-137">In this section, we will create a test group to assign your configurations on.</span></span>

>[!NOTE]
><span data-ttu-id="27a89-138">O Intune usa Azure Active Directory grupos (Azure AD) para gerenciar dispositivos e usuários.</span><span class="sxs-lookup"><span data-stu-id="27a89-138">Intune uses Azure Active Directory (Azure AD) groups to manage devices and users.</span></span> <span data-ttu-id="27a89-139">Como administrador do Intune, você pode configurar grupos para atender às suas necessidades organizacionais.</span><span class="sxs-lookup"><span data-stu-id="27a89-139">As an Intune admin, you can set up groups to suit your organizational needs.</span></span><br>
<span data-ttu-id="27a89-140">Para obter mais informações, [consulte Adicionar grupos para organizar usuários e dispositivos](/mem/intune/fundamentals/groups-add).</span><span class="sxs-lookup"><span data-stu-id="27a89-140">For more information, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-a-group"></a><span data-ttu-id="27a89-141">Criar um grupo</span><span class="sxs-lookup"><span data-stu-id="27a89-141">Create a group</span></span>

1.  <span data-ttu-id="27a89-142">Abra o portal MEM.</span><span class="sxs-lookup"><span data-stu-id="27a89-142">Open the MEM portal.</span></span>

2.  <span data-ttu-id="27a89-143">Abra **Grupos > Novo Grupo**.</span><span class="sxs-lookup"><span data-stu-id="27a89-143">Open **Groups > New Group**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-144">![Imagem do Microsoft Endpoint Manager portal1](images/66f724598d9c3319cba27f79dd4617a4.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-144">![Image of Microsoft Endpoint Manager portal1](images/66f724598d9c3319cba27f79dd4617a4.png)</span></span>

3.  <span data-ttu-id="27a89-145">Insira detalhes e crie um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="27a89-145">Enter details and create a new group.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-146">![Imagem do Microsoft Endpoint Manager portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-146">![Image of Microsoft Endpoint Manager portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span></span>

4.  <span data-ttu-id="27a89-147">Adicione seu usuário de teste ou dispositivo.</span><span class="sxs-lookup"><span data-stu-id="27a89-147">Add your test user or device.</span></span>

5.  <span data-ttu-id="27a89-148">No painel **Grupos > Todos os** grupos, abra seu novo grupo.</span><span class="sxs-lookup"><span data-stu-id="27a89-148">From the **Groups > All groups** pane, open your new group.</span></span>

6.  <span data-ttu-id="27a89-149">Selecione  **Membros > Adicionar membros**.</span><span class="sxs-lookup"><span data-stu-id="27a89-149">Select  **Members > Add members**.</span></span>

7.  <span data-ttu-id="27a89-150">Encontre seu usuário de teste ou dispositivo e selecione-o.</span><span class="sxs-lookup"><span data-stu-id="27a89-150">Find your test user or device and select it.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-151">![Imagem do Microsoft Endpoint Manager portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-151">![Image of Microsoft Endpoint Manager portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span></span>

8.  <span data-ttu-id="27a89-152">Seu grupo de teste agora tem um membro para testar.</span><span class="sxs-lookup"><span data-stu-id="27a89-152">Your testing group now has a member to test.</span></span>

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="27a89-153">Etapa 2: Criar políticas de configuração para configurar o Microsoft Defender para recursos do Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="27a89-153">Step 2: Create configuration policies to configure Microsoft Defender for Endpoint capabilities</span></span>
<span data-ttu-id="27a89-154">Na seção a seguir, você criará várias políticas de configuração.</span><span class="sxs-lookup"><span data-stu-id="27a89-154">In the following section, you'll create a number of configuration policies.</span></span>

<span data-ttu-id="27a89-155">Em primeiro lugar, uma política de configuração para selecionar quais grupos de usuários ou dispositivos serão integrados ao Defender para Ponto de Extremidade:</span><span class="sxs-lookup"><span data-stu-id="27a89-155">First is a configuration policy to select which groups of users or devices will be onboarded to Defender for Endpoint:</span></span>

- [<span data-ttu-id="27a89-156">Detecção de ponto de extremidade e resposta</span><span class="sxs-lookup"><span data-stu-id="27a89-156">Endpoint detection and response</span></span>](#endpoint-detection-and-response) 

<span data-ttu-id="27a89-157">Em seguida, você continuará criando vários tipos diferentes de políticas de segurança do ponto de extremidade:</span><span class="sxs-lookup"><span data-stu-id="27a89-157">Then you will continue by creating several different types of endpoint security policies:</span></span>

- [<span data-ttu-id="27a89-158">Proteção de última geração</span><span class="sxs-lookup"><span data-stu-id="27a89-158">Next-generation protection</span></span>](#next-generation-protection)
- [<span data-ttu-id="27a89-159">Redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="27a89-159">Attack surface reduction</span></span>](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="27a89-160">Detecção de ponto de extremidade e resposta</span><span class="sxs-lookup"><span data-stu-id="27a89-160">Endpoint detection and response</span></span>

1.  <span data-ttu-id="27a89-161">Abra o portal MEM.</span><span class="sxs-lookup"><span data-stu-id="27a89-161">Open the MEM portal.</span></span>

2.  <span data-ttu-id="27a89-162">Navegue **até Endpoint security > Endpoint detection and response**.</span><span class="sxs-lookup"><span data-stu-id="27a89-162">Navigate to **Endpoint security > Endpoint detection and response**.</span></span> <span data-ttu-id="27a89-163">Clique em **Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="27a89-163">Click on **Create Profile**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-164">![Imagem do Microsoft Endpoint Manager portal4](images/58dcd48811147feb4ddc17212b7fe840.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-164">![Image of Microsoft Endpoint Manager portal4](images/58dcd48811147feb4ddc17212b7fe840.png)</span></span>

3.  <span data-ttu-id="27a89-165">Em **Plataforma, selecione Windows 10 e Posterior, Perfil - Detecção** e resposta do ponto de extremidade > Criar .</span><span class="sxs-lookup"><span data-stu-id="27a89-165">Under **Platform, select Windows 10 and Later, Profile - Endpoint detection and response > Create**.</span></span>

4.  <span data-ttu-id="27a89-166">Insira um nome e uma descrição e selecione  **Next**.</span><span class="sxs-lookup"><span data-stu-id="27a89-166">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-167">![Imagem do Microsoft Endpoint Manager portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-167">![Image of Microsoft Endpoint Manager portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span></span>

5.  <span data-ttu-id="27a89-168">Selecione configurações conforme necessário e selecione  **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="27a89-168">Select settings as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-169">![Imagem do Microsoft Endpoint Manager portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-169">![Image of Microsoft Endpoint Manager portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="27a89-170">Nesse caso, isso foi preenchido automaticamente, pois o Defender para Ponto de Extremidade já foi integrado ao Intune.</span><span class="sxs-lookup"><span data-stu-id="27a89-170">In this instance, this has been auto populated as Defender for Endpoint has already been integrated with Intune.</span></span> <span data-ttu-id="27a89-171">Para obter mais informações sobre a integração, consulte [Enable Microsoft Defender for Endpoint in Intune](/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).</span><span class="sxs-lookup"><span data-stu-id="27a89-171">For more information on the integration, see [Enable Microsoft Defender for Endpoint in Intune](/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).</span></span>
    > 
    > <span data-ttu-id="27a89-172">A imagem a seguir é um exemplo do que você verá quando o Microsoft Defender for Endpoint não estiver integrado ao Intune:</span><span class="sxs-lookup"><span data-stu-id="27a89-172">The following image is an example of what you'll see when Microsoft Defender for Endpoint is NOT integrated with Intune:</span></span>
    >
    > ![Imagem do Microsoft Endpoint Manager portal7](images/2466460812371ffae2d19a10c347d6f4.png)

6.  <span data-ttu-id="27a89-174">Adicione marcas de escopo, se necessário, em seguida, selecione  **Next**.</span><span class="sxs-lookup"><span data-stu-id="27a89-174">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-175">![Imagem do Microsoft Endpoint Manager portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-175">![Image of Microsoft Endpoint Manager portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span></span>

7.  <span data-ttu-id="27a89-176">Adicione grupo de teste clicando em **Selecionar grupos para incluir** e escolher seu grupo e selecione  **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="27a89-176">Add test group by clicking on **Select groups to include** and choose your group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-177">![Imagem do Microsoft Endpoint Manager portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-177">![Image of Microsoft Endpoint Manager portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span></span>

8.  <span data-ttu-id="27a89-178">Revise e aceite e selecione  **Criar**.</span><span class="sxs-lookup"><span data-stu-id="27a89-178">Review and accept, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-179">![Imagem do Microsoft Endpoint Manager portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-179">![Image of Microsoft Endpoint Manager portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span></span>

9.  <span data-ttu-id="27a89-180">Você pode exibir sua política concluída.</span><span class="sxs-lookup"><span data-stu-id="27a89-180">You can view your completed policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-181">![Imagem do Microsoft Endpoint Manager portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-181">![Image of Microsoft Endpoint Manager portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="27a89-182">Proteção de próxima geração</span><span class="sxs-lookup"><span data-stu-id="27a89-182">Next-generation protection</span></span>

1.  <span data-ttu-id="27a89-183">Abra o portal MEM.</span><span class="sxs-lookup"><span data-stu-id="27a89-183">Open the MEM portal.</span></span>

2.  <span data-ttu-id="27a89-184">Navegue **até Endpoint security > Antivírus > Criar Política**.</span><span class="sxs-lookup"><span data-stu-id="27a89-184">Navigate to **Endpoint security > Antivirus > Create Policy**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-185">![Imagem do Microsoft Endpoint Manager portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-185">![Image of Microsoft Endpoint Manager portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span></span>

3.  <span data-ttu-id="27a89-186">Selecione **Plataforma - Windows 10 e Posterior - Windows e Perfil - Microsoft Defender Antivírus > Criar**.</span><span class="sxs-lookup"><span data-stu-id="27a89-186">Select **Platform - Windows 10 and Later - Windows and Profile – Microsoft Defender Antivirus > Create**.</span></span>

4.  <span data-ttu-id="27a89-187">Insira o nome e a descrição e selecione  **Next**.</span><span class="sxs-lookup"><span data-stu-id="27a89-187">Enter name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-188">![Imagem do Microsoft Endpoint Manager portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-188">![Image of Microsoft Endpoint Manager portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span></span>

5.  <span data-ttu-id="27a89-189">Na página **Configuração configurações**: de definir as configurações necessárias para Microsoft Defender Antivírus (Proteção na Nuvem, Exclusões, Real-Time Proteção e Correção).</span><span class="sxs-lookup"><span data-stu-id="27a89-189">In the **Configuration settings page**: Set the configurations you require for Microsoft Defender Antivirus (Cloud Protection, Exclusions, Real-Time Protection, and Remediation).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-190">![Imagem do Microsoft Endpoint Manager portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-190">![Image of Microsoft Endpoint Manager portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span></span>

6.  <span data-ttu-id="27a89-191">Adicione marcas de escopo, se necessário, em seguida, selecione  **Next**.</span><span class="sxs-lookup"><span data-stu-id="27a89-191">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-192">![Imagem do Microsoft Endpoint Manager portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-192">![Image of Microsoft Endpoint Manager portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span></span>

7.  <span data-ttu-id="27a89-193">Selecione grupos para incluir, atribua ao grupo de teste e selecione  **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="27a89-193">Select groups to include, assign to your test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-194">![Imagem do Microsoft Endpoint Manager portal16](images/48318a51adee06bff3908e8ad4944dc9.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-194">![Image of Microsoft Endpoint Manager portal16](images/48318a51adee06bff3908e8ad4944dc9.png)</span></span>

8.  <span data-ttu-id="27a89-195">Revise e crie e selecione  **Criar**.</span><span class="sxs-lookup"><span data-stu-id="27a89-195">Review and create, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-196">![Imagem do Microsoft Endpoint Manager portal17](images/dfdadab79112d61bd3693d957084b0ec.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-196">![Image of Microsoft Endpoint Manager portal17](images/dfdadab79112d61bd3693d957084b0ec.png)</span></span>

9.  <span data-ttu-id="27a89-197">Você verá a política de configuração criada.</span><span class="sxs-lookup"><span data-stu-id="27a89-197">You'll see the configuration policy you created.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-198">![Imagem do Microsoft Endpoint Manager portal18](images/38180219e632d6e4ec7bd25a46398da8.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-198">![Image of Microsoft Endpoint Manager portal18](images/38180219e632d6e4ec7bd25a46398da8.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="27a89-199">Redução de Superfície de Ataque – Regras de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="27a89-199">Attack Surface Reduction – Attack surface reduction rules</span></span>

1.  <span data-ttu-id="27a89-200">Abra o portal MEM.</span><span class="sxs-lookup"><span data-stu-id="27a89-200">Open the MEM portal.</span></span>

2.  <span data-ttu-id="27a89-201">Navegue **até Endpoint security > Redução de superfície de ataque**.</span><span class="sxs-lookup"><span data-stu-id="27a89-201">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="27a89-202">Selecione  **Criar Política**.</span><span class="sxs-lookup"><span data-stu-id="27a89-202">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="27a89-203">Selecione Plataforma - Windows 10 e Posterior - Perfil - Regras de **redução de superfície de ataque > Criar**.</span><span class="sxs-lookup"><span data-stu-id="27a89-203">Select **Platform - Windows 10 and Later – Profile - Attack surface reduction rules > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-204">![Imagem do Microsoft Endpoint Manager portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-204">![Image of Microsoft Endpoint Manager portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span></span>

5.  <span data-ttu-id="27a89-205">Insira um nome e uma descrição e selecione  **Next**.</span><span class="sxs-lookup"><span data-stu-id="27a89-205">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-206">![Imagem do Microsoft Endpoint Manager portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-206">![Image of Microsoft Endpoint Manager portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span></span>

6.  <span data-ttu-id="27a89-207">Na página **Configuração de configuração:** de definir as configurações necessárias para regras de redução de superfície de ataque e selecione  **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="27a89-207">In the **Configuration settings page**: Set the configurations you require for Attack surface reduction rules, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="27a89-208">Configuraremos todas as regras de redução de superfície de ataque para Auditoria.</span><span class="sxs-lookup"><span data-stu-id="27a89-208">We will be configuring all of the Attack surface reduction rules to Audit.</span></span>
    > 
    > <span data-ttu-id="27a89-209">Para obter mais informações, consulte [Regras de redução de superfície de ataque](attack-surface-reduction.md).</span><span class="sxs-lookup"><span data-stu-id="27a89-209">For more information, see [Attack surface reduction rules](attack-surface-reduction.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-210">![Imagem do Microsoft Endpoint Manager portal21](images/dd0c00efe615a64a4a368f54257777d0.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-210">![Image of Microsoft Endpoint Manager portal21](images/dd0c00efe615a64a4a368f54257777d0.png)</span></span>

7.  <span data-ttu-id="27a89-211">Adicione Marcas de Escopo conforme necessário e selecione  **Next**.</span><span class="sxs-lookup"><span data-stu-id="27a89-211">Add Scope Tags as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-212">![Imagem do Microsoft Endpoint Manager portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-212">![Image of Microsoft Endpoint Manager portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="27a89-213">Selecione grupos para incluir e atribuir ao grupo de teste e selecione  **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="27a89-213">Select groups to include and assign to test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-214">![Imagem do Microsoft Endpoint Manager portal23](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-214">![Image of Microsoft Endpoint Manager portal23](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9. <span data-ttu-id="27a89-215">Revise os detalhes e selecione  **Criar**.</span><span class="sxs-lookup"><span data-stu-id="27a89-215">Review the details, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-216">![Imagem do Microsoft Endpoint Manager portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-216">![Image of Microsoft Endpoint Manager portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span></span>

10. <span data-ttu-id="27a89-217">Exibir a política.</span><span class="sxs-lookup"><span data-stu-id="27a89-217">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-218">![Imagem do Microsoft Endpoint Manager portal25](images/7a631d17cc42500dacad4e995823ffef.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-218">![Image of Microsoft Endpoint Manager portal25](images/7a631d17cc42500dacad4e995823ffef.png)</span></span>

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="27a89-219">Redução de superfície de ataque – Proteção da Web</span><span class="sxs-lookup"><span data-stu-id="27a89-219">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="27a89-220">Abra o portal MEM.</span><span class="sxs-lookup"><span data-stu-id="27a89-220">Open the MEM portal.</span></span>

2.  <span data-ttu-id="27a89-221">Navegue **até Endpoint security > Redução de superfície de ataque**.</span><span class="sxs-lookup"><span data-stu-id="27a89-221">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="27a89-222">Selecione  **Criar Política**.</span><span class="sxs-lookup"><span data-stu-id="27a89-222">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="27a89-223">Selecione **Windows 10 e Posterior – Proteção da Web > Criar**.</span><span class="sxs-lookup"><span data-stu-id="27a89-223">Select **Windows 10 and Later – Web protection > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-224">![Imagem do Microsoft Endpoint Manager portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-224">![Image of Microsoft Endpoint Manager portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span></span>

5.  <span data-ttu-id="27a89-225">Insira um nome e uma descrição e selecione  **Next**.</span><span class="sxs-lookup"><span data-stu-id="27a89-225">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-226">![Imagem do Microsoft Endpoint Manager portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-226">![Image of Microsoft Endpoint Manager portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span></span>

6.  <span data-ttu-id="27a89-227">Na página **Configuração configurações:** de definir as configurações necessárias para a Proteção da Web e selecione  **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="27a89-227">In the **Configuration settings page**: Set the configurations you require for Web Protection, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="27a89-228">Estamos configurando a Proteção da Web para Bloquear.</span><span class="sxs-lookup"><span data-stu-id="27a89-228">We are configuring Web Protection to Block.</span></span>
    > 
    > <span data-ttu-id="27a89-229">Para obter mais informações, consulte [Web Protection](web-protection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="27a89-229">For more information, see [Web Protection](web-protection-overview.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-230">![Imagem do Microsoft Endpoint Manager portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-230">![Image of Microsoft Endpoint Manager portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span></span>

7.  <span data-ttu-id="27a89-231">Adicione **marcas de escopo conforme necessário > Next**.</span><span class="sxs-lookup"><span data-stu-id="27a89-231">Add **Scope Tags as required > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-232">![Imagem do Microsoft Endpoint Manager portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-232">![Image of Microsoft Endpoint Manager portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="27a89-233">Selecione **Atribuir ao grupo de teste > Próximo**.</span><span class="sxs-lookup"><span data-stu-id="27a89-233">Select **Assign to test group > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-234">![Imagem do Microsoft Endpoint Manager portal30](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-234">![Image of Microsoft Endpoint Manager portal30](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9.  <span data-ttu-id="27a89-235">Selecione **Revisar e Criar > Criar**.</span><span class="sxs-lookup"><span data-stu-id="27a89-235">Select **Review and Create > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-236">![Imagem do Microsoft Endpoint Manager portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-236">![Image of Microsoft Endpoint Manager portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span></span>

10. <span data-ttu-id="27a89-237">Exibir a política.</span><span class="sxs-lookup"><span data-stu-id="27a89-237">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-238">![Imagem do Microsoft Endpoint Manager portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-238">![Image of Microsoft Endpoint Manager portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span></span>

## <a name="validate-configuration-settings"></a><span data-ttu-id="27a89-239">Validar configurações</span><span class="sxs-lookup"><span data-stu-id="27a89-239">Validate configuration settings</span></span>


### <a name="confirm-policies-have-been-applied"></a><span data-ttu-id="27a89-240">Confirmar políticas foram aplicadas</span><span class="sxs-lookup"><span data-stu-id="27a89-240">Confirm Policies have been applied</span></span>


<span data-ttu-id="27a89-241">Depois que a política de configuração tiver sido atribuída, levará algum tempo para ser aplicada.</span><span class="sxs-lookup"><span data-stu-id="27a89-241">Once the Configuration policy has been assigned, it will take some time to apply.</span></span>

<span data-ttu-id="27a89-242">Para obter informações sobre o tempo, consulte [Informações de configuração do Intune.](/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned)</span><span class="sxs-lookup"><span data-stu-id="27a89-242">For information on timing, see [Intune configuration information](/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).</span></span>

<span data-ttu-id="27a89-243">Para confirmar se a política de configuração foi aplicada ao dispositivo de teste, siga o processo a seguir para cada política de configuração.</span><span class="sxs-lookup"><span data-stu-id="27a89-243">To confirm that the configuration policy has been applied to your test device, follow the following process for each configuration policy.</span></span>

1.  <span data-ttu-id="27a89-244">Abra o portal do MEM e navegue até a política relevante, conforme mostrado nas etapas acima.</span><span class="sxs-lookup"><span data-stu-id="27a89-244">Open the MEM portal and navigate to the relevant policy as shown in the steps above.</span></span> <span data-ttu-id="27a89-245">O exemplo a seguir mostra as configurações de proteção de próxima geração.</span><span class="sxs-lookup"><span data-stu-id="27a89-245">The following example shows the next generation protection settings.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-246">[![Imagem do Microsoft Endpoint Manager portal33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="27a89-246">[ ![Image of Microsoft Endpoint Manager portal33](images/43ab6aa74471ee2977e154a4a5ef2d39.png) ](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span></span>

2.  <span data-ttu-id="27a89-247">Selecione a **Política de Configuração** para exibir o status da política.</span><span class="sxs-lookup"><span data-stu-id="27a89-247">Select  the **Configuration Policy** to view the policy status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-248">[![Imagem do Microsoft Endpoint Manager portal34 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="27a89-248">[ ![Image of Microsoft Endpoint Manager portal34](images/55ecaca0e4a022f0e29d45aeed724e6c.png) ](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span></span>

3.  <span data-ttu-id="27a89-249">Selecione  **Status do Dispositivo** para ver o status.</span><span class="sxs-lookup"><span data-stu-id="27a89-249">Select  **Device Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-250">[![Imagem do Microsoft Endpoint Manager portal35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="27a89-250">[ ![Image of Microsoft Endpoint Manager portal35](images/18a50df62cc38749000dbfb48e9a4c9b.png) ](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span></span>

4.  <span data-ttu-id="27a89-251">Selecione  **Status do Usuário** para ver o status.</span><span class="sxs-lookup"><span data-stu-id="27a89-251">Select  **User Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-252">[![Imagem do Microsoft Endpoint Manager portal36 ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="27a89-252">[ ![Image of Microsoft Endpoint Manager portal36](images/4e965749ff71178af8873bc91f9fe525.png) ](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span></span>

5.  <span data-ttu-id="27a89-253">Selecione  **Status por configuração** para ver o status.</span><span class="sxs-lookup"><span data-stu-id="27a89-253">Select  **Per-setting status** to see the status.</span></span>

    >[!TIP]
    ><span data-ttu-id="27a89-254">Essa exibição é muito útil para identificar as configurações que conflitam com outra política.</span><span class="sxs-lookup"><span data-stu-id="27a89-254">This view is very useful to identify any settings that conflict with another policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-255">[![Imagem do Microsoft Endpoint Manager portal37 ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="27a89-255">[ ![Image of Microsoft Endpoint Manager portal37](images/42acc69d0128ed09804010bdbdf0a43c.png) ](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span></span>

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="27a89-256">Detecção de ponto de extremidade e resposta</span><span class="sxs-lookup"><span data-stu-id="27a89-256">Endpoint detection and response</span></span>


1.  <span data-ttu-id="27a89-257">Antes de aplicar a configuração, o serviço Defender para Endpoint Protection não deve ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="27a89-257">Before applying the configuration, the Defender for Endpoint Protection service should not be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-258">[![Painel Imagem dos Serviços1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="27a89-258">[ ![Image of Services panel1](images/b418a232a12b3d0a65fc98248dbb0e31.png) ](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span></span>

2.  <span data-ttu-id="27a89-259">Depois que a configuração for aplicada, o Defender for Endpoint Protection Service deve ser iniciado.</span><span class="sxs-lookup"><span data-stu-id="27a89-259">After the configuration has been applied, the Defender for Endpoint Protection Service should be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-260">[![Painel Imagem dos Serviços2 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="27a89-260">[ ![Image of Services panel2](images/a621b699899f1b41db211170074ea59e.png) ](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span></span>

3.  <span data-ttu-id="27a89-261">Depois que os serviços são executados no dispositivo, o dispositivo aparece Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="27a89-261">After the services are running on the device, the device appears in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-262">[![Imagem de Central de Segurança do Microsoft Defender ](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="27a89-262">[ ![Image of Microsoft Defender Security Center](images/df0c64001b9219cfbd10f8f81a273190.png) ](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="27a89-263">Proteção de próxima geração</span><span class="sxs-lookup"><span data-stu-id="27a89-263">Next-generation protection</span></span>

1.  <span data-ttu-id="27a89-264">Antes de aplicar a política em um dispositivo de teste, você deve ser capaz de gerenciar manualmente as configurações, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="27a89-264">Before applying the policy on a test device, you should be able to manually manage the settings as shown below.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-265">![Imagem da configuração page1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-265">![Image of setting page1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span></span>

2.  <span data-ttu-id="27a89-266">Depois que a política tiver sido aplicada, você não poderá gerenciar manualmente as configurações.</span><span class="sxs-lookup"><span data-stu-id="27a89-266">After the policy has been applied, you should not be able to manually manage the settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="27a89-267">Na imagem a **seguir, a proteção** a ser exibida na nuvem e Ativar a proteção em **tempo real** estão sendo mostradas como gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="27a89-267">In the following image **Turn on cloud-delivered protection** and **Turn on real-time protection** are being shown as managed.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="27a89-268">![Imagem da configuração page2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span><span class="sxs-lookup"><span data-stu-id="27a89-268">![Image of setting page2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="27a89-269">Redução de Superfície de Ataque – Regras de redução de superfície de ataque</span><span class="sxs-lookup"><span data-stu-id="27a89-269">Attack Surface Reduction – Attack surface reduction rules</span></span>


1.  <span data-ttu-id="27a89-270">Antes de aplicar a política em um dispositivo de teste, penite uma Janela do PowerShell e digite `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="27a89-270">Before applying the policy on a test device, pen a PowerShell Window and type `Get-MpPreference`.</span></span>

2.  <span data-ttu-id="27a89-271">Isso deve responder com as seguintes linhas sem conteúdo:</span><span class="sxs-lookup"><span data-stu-id="27a89-271">This should respond with the following lines with no content:</span></span>

    > <span data-ttu-id="27a89-272">AttackSurfaceReductionOnlyExclusions:</span><span class="sxs-lookup"><span data-stu-id="27a89-272">AttackSurfaceReductionOnlyExclusions:</span></span>
    > 
    > <span data-ttu-id="27a89-273">AttackSurfaceReductionRules_Actions:</span><span class="sxs-lookup"><span data-stu-id="27a89-273">AttackSurfaceReductionRules_Actions:</span></span>
    > 
    > <span data-ttu-id="27a89-274">AttackSurfaceReductionRules_Ids:</span><span class="sxs-lookup"><span data-stu-id="27a89-274">AttackSurfaceReductionRules_Ids:</span></span>

    ![Imagem da linha de comando1](images/cb0260d4b2636814e37eee427211fe71.png)

3.  <span data-ttu-id="27a89-276">Depois de aplicar a política em um dispositivo de teste, abra um powershell Windows e digite `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="27a89-276">After applying the policy on a test device, open a PowerShell Windows and type `Get-MpPreference`.</span></span>

4.  <span data-ttu-id="27a89-277">Isso deve responder com as seguintes linhas com conteúdo, conforme mostrado abaixo:</span><span class="sxs-lookup"><span data-stu-id="27a89-277">This should respond with the following lines with content as shown below:</span></span>

    ![Imagem da linha de comando2](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="27a89-279">Redução de superfície de ataque – Proteção da Web</span><span class="sxs-lookup"><span data-stu-id="27a89-279">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="27a89-280">No dispositivo de teste, abra um powershell Windows e digite `(Get-MpPreference).EnableNetworkProtection` .</span><span class="sxs-lookup"><span data-stu-id="27a89-280">On the test device, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

2.  <span data-ttu-id="27a89-281">Isso deve responder com um 0 conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="27a89-281">This should respond with a 0 as shown below.</span></span>

    ![Imagem da linha de comando3](images/196a8e194ac99d84221f405d0f684f8c.png)

3.  <span data-ttu-id="27a89-283">Depois de aplicar a política, abra um powershell Windows e digite `(Get-MpPreference).EnableNetworkProtection` .</span><span class="sxs-lookup"><span data-stu-id="27a89-283">After applying the policy, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

4.  <span data-ttu-id="27a89-284">Isso deve responder com um 1, conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="27a89-284">This should respond with a 1 as shown below.</span></span>

    ![Imagem da linha de comando4](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
