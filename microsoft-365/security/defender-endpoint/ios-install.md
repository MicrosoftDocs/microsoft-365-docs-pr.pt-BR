---
title: Implantação baseada em aplicativo para Microsoft Defender ATP para iOS
ms.reviewer: ''
description: Descreve como implantar o Microsoft Defender ATP para iOS usando um aplicativo
keywords: microsoft, defender, atp, ios, app, installation, deploy, uninstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6cfd2953e752ed9c96f7f16a3ec7ea1fd8862ab2
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689732"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="9c76f-104">Implantar o Microsoft Defender para Ponto de Extremidade no iOS</span><span class="sxs-lookup"><span data-stu-id="9c76f-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9c76f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9c76f-105">**Applies to:**</span></span>
- [<span data-ttu-id="9c76f-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9c76f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9c76f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9c76f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9c76f-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="9c76f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9c76f-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="9c76f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="9c76f-110">Este tópico descreve a implantação do Defender para Ponto de Extremidade para iOS em dispositivos inscritos no Portal da Empresa do Intune.</span><span class="sxs-lookup"><span data-stu-id="9c76f-110">This topic describes deploying Defender for Endpoint for iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="9c76f-111">Para obter mais informações sobre o registro de dispositivo do Intune, consulte [Registrar dispositivos iOS/iPadOS no Intune](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll).</span><span class="sxs-lookup"><span data-stu-id="9c76f-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](https://docs.microsoft.com/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9c76f-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="9c76f-112">Before you begin</span></span>

- <span data-ttu-id="9c76f-113">Verifique se você tem acesso ao Centro de [administração do Gerenciador de Pontos de Extremidade da Microsoft.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="9c76f-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="9c76f-114">Certifique-se de que o registro do iOS seja feito para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="9c76f-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="9c76f-115">Os usuários precisam ter uma licença do Defender para Ponto de Extremidade atribuída para usar o Defender para Endpoint para iOS.</span><span class="sxs-lookup"><span data-stu-id="9c76f-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint for iOS.</span></span> <span data-ttu-id="9c76f-116">Consulte [Atribuir licenças aos usuários para](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) obter instruções sobre como atribuir licenças.</span><span class="sxs-lookup"><span data-stu-id="9c76f-116">Refer to [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="9c76f-117">O Microsoft Defender ATP (Microsoft Defender para Ponto de Extremidade) para iOS agora está disponível na [Apple App Store](https://aka.ms/mdatpiosappstore).</span><span class="sxs-lookup"><span data-stu-id="9c76f-117">Microsoft Defender ATP (Microsoft Defender for Endpoint) for iOS is now available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="9c76f-118">Etapas de implantação</span><span class="sxs-lookup"><span data-stu-id="9c76f-118">Deployment steps</span></span>

<span data-ttu-id="9c76f-119">Implante o Defender para Ponto de Extremidade para iOS por meio do Portal da Empresa do Intune.</span><span class="sxs-lookup"><span data-stu-id="9c76f-119">Deploy Defender for Endpoint for iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="9c76f-120">Adicionar aplicativo da loja do iOS</span><span class="sxs-lookup"><span data-stu-id="9c76f-120">Add iOS store app</span></span>

1. <span data-ttu-id="9c76f-121">No Centro de administração do Gerenciador de Pontos de Extremidade [da Microsoft,](https://go.microsoft.com/fwlink/?linkid=2109431)vá para **Aplicativos**  ->  **iOS/iPadOS** Adicionar aplicativo da loja  ->    ->  **do iOS** e clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="9c76f-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="9c76f-122">![Imagem do Centro de Administração do Microsoft Endpoint Manager1](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="9c76f-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="9c76f-123">Na página Adicionar aplicativo, clique em **Pesquisar na Loja de Aplicativos** e digite o Ponto de Extremidade do Microsoft **Defender** na barra de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9c76f-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="9c76f-124">Na seção resultados da pesquisa, clique em Ponto de *Extremidade do Microsoft Defender* e clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="9c76f-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="9c76f-125">Selecione **iOS 11.0 como** o sistema operacional Mínimo.</span><span class="sxs-lookup"><span data-stu-id="9c76f-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="9c76f-126">Revise o restante das informações sobre o aplicativo e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="9c76f-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="9c76f-127">Na seção *Atribuições,* vá para a seção **Obrigatório** e selecione **Adicionar grupo**.</span><span class="sxs-lookup"><span data-stu-id="9c76f-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="9c76f-128">Em seguida, você pode escolher os grupos de usuários que você gostaria de direcionar o Defender para Ponto de Extremidade para aplicativo iOS.</span><span class="sxs-lookup"><span data-stu-id="9c76f-128">You can then choose the user group(s) that you would like to target Defender for Endpoint for iOS app.</span></span> <span data-ttu-id="9c76f-129">Clique **em Selecionar** e, em **seguida, Em Seguida.**</span><span class="sxs-lookup"><span data-stu-id="9c76f-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9c76f-130">O grupo de usuários selecionado deve consistir em usuários inscritos do Intune.</span><span class="sxs-lookup"><span data-stu-id="9c76f-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="9c76f-131">![Imagem do Centro de Administração do Microsoft Endpoint Manager2](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="9c76f-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="9c76f-132">Na seção *Revisar + Criar,* verifique se todas as informações inseridas estão corretas e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="9c76f-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="9c76f-133">Em alguns instantes, o aplicativo Defender para Ponto de Extremidade deve ser criado com êxito, e uma notificação deve aparecer no canto superior direito da página.</span><span class="sxs-lookup"><span data-stu-id="9c76f-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="9c76f-134">Na página informações do aplicativo exibida, na seção **Monitor,** selecione **Status** de instalação do dispositivo para verificar se a instalação do dispositivo foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="9c76f-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="9c76f-135">![Imagem do Centro de Administração do Microsoft Endpoint Manager3](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="9c76f-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="9c76f-136">Concluir a integração e verificar o status</span><span class="sxs-lookup"><span data-stu-id="9c76f-136">Complete onboarding and check status</span></span>

1. <span data-ttu-id="9c76f-137">Depois que o Defender for Endpoint para iOS tiver sido instalado no dispositivo, você verá o ícone do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9c76f-137">Once Defender for Endpoint for iOS has been installed on the device, you  will see the app icon.</span></span>

    ![Uma captura de tela de um telefone inteligente Descrição gerada automaticamente](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="9c76f-139">Toque no ícone do aplicativo Defender para Ponto de Extremidade e siga as instruções na tela para concluir as etapas de integração.</span><span class="sxs-lookup"><span data-stu-id="9c76f-139">Tap the Defender for Endpoint app icon and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="9c76f-140">Os detalhes incluem a aceitação do usuário final das permissões do iOS exigidas pelo Defender para Ponto de Extremidade para iOS.</span><span class="sxs-lookup"><span data-stu-id="9c76f-140">The details include end-user acceptance of iOS permissions required by Defender for Endpoint for iOS.</span></span>

3. <span data-ttu-id="9c76f-141">Após a integração bem-sucedida, o dispositivo começará a aparecer na lista Dispositivos no Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="9c76f-141">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="9c76f-142">![Uma captura de tela de um telefone celular Descrição gerada automaticamente](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="9c76f-142">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="9c76f-143">Configurar o Microsoft Defender para Ponto de Extremidade para Modo Supervisionado</span><span class="sxs-lookup"><span data-stu-id="9c76f-143">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="9c76f-144">O Microsoft Defender for Endpoint no aplicativo iOS tem capacidade especializada em dispositivos iOS/iPadOS supervisionados, dado o aumento dos recursos de gerenciamento fornecidos pela plataforma nesses tipos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9c76f-144">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="9c76f-145">Para aproveitar esses recursos, o aplicativo Defender for Endpoint precisa saber se um dispositivo está no modo Supervisionado.</span><span class="sxs-lookup"><span data-stu-id="9c76f-145">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="9c76f-146">Configurar o modo Supervisionado por meio do Intune</span><span class="sxs-lookup"><span data-stu-id="9c76f-146">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="9c76f-147">O Intune permite configurar o aplicativo Defender para iOS por meio de uma política de Configuração de Aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9c76f-147">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9c76f-148">Esta política de configuração de aplicativo para dispositivos supervisionados é aplicável apenas a dispositivos gerenciados e deve ser direcionada para todos os dispositivos iOS gerenciados como uma prática prática prática.</span><span class="sxs-lookup"><span data-stu-id="9c76f-148">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="9c76f-149">Entre no Centro de administração do [Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431) e acesse Políticas de configuração do Aplicativo de   >  **Aplicativos**  >  **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9c76f-149">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="9c76f-150">Clique em **Dispositivos gerenciados**.</span><span class="sxs-lookup"><span data-stu-id="9c76f-150">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="9c76f-151">![Imagem do Centro de Administração do Microsoft Endpoint Manager4](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="9c76f-151">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="9c76f-152">Na página *Criar política de configuração de aplicativo,* forneça as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="9c76f-152">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="9c76f-153">Nome da política</span><span class="sxs-lookup"><span data-stu-id="9c76f-153">Policy Name</span></span>
    - <span data-ttu-id="9c76f-154">Plataforma: Selecione iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="9c76f-154">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="9c76f-155">Aplicativo direcionado: Selecione **o Microsoft Defender ATP** na lista</span><span class="sxs-lookup"><span data-stu-id="9c76f-155">Targeted app: Select **Microsoft Defender ATP** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="9c76f-156">![Imagem do Centro de Administração do Microsoft Endpoint Manager5](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="9c76f-156">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="9c76f-157">Na próxima tela, selecione **Usar designer de configuração** como o formato.</span><span class="sxs-lookup"><span data-stu-id="9c76f-157">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="9c76f-158">Especifique a seguinte propriedade:</span><span class="sxs-lookup"><span data-stu-id="9c76f-158">Specify the following property:</span></span>
    - <span data-ttu-id="9c76f-159">Chave de Configuração: supervisionada</span><span class="sxs-lookup"><span data-stu-id="9c76f-159">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="9c76f-160">Tipo de valor: Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9c76f-160">Value type: String</span></span>
    - <span data-ttu-id="9c76f-161">Valor da configuração: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="9c76f-161">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="9c76f-162">![Imagem do Centro de Administração do Microsoft Endpoint Manager6](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="9c76f-162">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="9c76f-163">Clique **em Próximo** para abrir a página Marcas de **escopo.**</span><span class="sxs-lookup"><span data-stu-id="9c76f-163">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="9c76f-164">As marcas de escopo são opcionais.</span><span class="sxs-lookup"><span data-stu-id="9c76f-164">Scope tags are optional.</span></span> <span data-ttu-id="9c76f-165">Clique em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="9c76f-165">Click **Next** to continue.</span></span>

1. <span data-ttu-id="9c76f-166">Na página **Atribuições,** selecione os grupos que receberão esse perfil.</span><span class="sxs-lookup"><span data-stu-id="9c76f-166">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="9c76f-167">Para esse cenário, é prática ideal direcionar Todos os **Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="9c76f-167">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="9c76f-168">Para obter mais informações sobre como atribuir perfis, consulte [Assign user and device profiles](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="9c76f-168">For more information on assigning profiles, see [Assign user and device profiles](https://docs.microsoft.com/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="9c76f-169">Ao implantar em grupos de usuários, um usuário deve entrar em um dispositivo antes da aplicação da política.</span><span class="sxs-lookup"><span data-stu-id="9c76f-169">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="9c76f-170">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9c76f-170">Click **Next**.</span></span>

1. <span data-ttu-id="9c76f-171">Na página **Revisar + criar,** quando terminar, escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="9c76f-171">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="9c76f-172">O novo perfil é exibido na lista de perfis de configuração.</span><span class="sxs-lookup"><span data-stu-id="9c76f-172">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="9c76f-173">Em seguida, para recursos avançados de anti-phishing, você pode implantar um perfil personalizado nos dispositivos iOS supervisionados.</span><span class="sxs-lookup"><span data-stu-id="9c76f-173">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="9c76f-174">Siga as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="9c76f-174">Follow the steps below:</span></span>
    - <span data-ttu-id="9c76f-175">Baixar o perfil de configuração de [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="9c76f-175">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="9c76f-176">Navegar até **dispositivos**  ->  **iOS/iPadOS** Perfis de  ->  **configuração**  ->  **Criar Perfil**</span><span class="sxs-lookup"><span data-stu-id="9c76f-176">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="9c76f-177">![Imagem do Centro de Administração do Microsoft Endpoint Manager7](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="9c76f-177">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="9c76f-178">Forneça um nome do perfil.</span><span class="sxs-lookup"><span data-stu-id="9c76f-178">Provide a name of the profile.</span></span> <span data-ttu-id="9c76f-179">Quando solicitado a importar um arquivo de perfil de configuração, selecione o que foi baixado acima.</span><span class="sxs-lookup"><span data-stu-id="9c76f-179">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="9c76f-180">Na seção **Atribuição,** selecione o grupo de dispositivos ao qual você deseja aplicar esse perfil.</span><span class="sxs-lookup"><span data-stu-id="9c76f-180">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="9c76f-181">Como prática prática, isso deve ser aplicado a todos os dispositivos iOS gerenciados.</span><span class="sxs-lookup"><span data-stu-id="9c76f-181">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="9c76f-182">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="9c76f-182">Click **Next**.</span></span>
    - <span data-ttu-id="9c76f-183">Na página **Revisar + criar,** quando terminar, escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="9c76f-183">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="9c76f-184">O novo perfil é exibido na lista de perfis de configuração.</span><span class="sxs-lookup"><span data-stu-id="9c76f-184">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9c76f-185">Próximas Etapas</span><span class="sxs-lookup"><span data-stu-id="9c76f-185">Next Steps</span></span>

[<span data-ttu-id="9c76f-186">Configurar o Defender para Ponto de Extremidade para recursos do iOS</span><span class="sxs-lookup"><span data-stu-id="9c76f-186">Configure Defender for Endpoint for iOS features</span></span>](ios-configure-features.md)
