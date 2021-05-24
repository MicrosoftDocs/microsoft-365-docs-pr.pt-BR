---
title: Implantação baseada em aplicativo para o Microsoft Defender para Ponto de Extremidade no iOS
ms.reviewer: ''
description: Descreve como implantar o Microsoft Defender para Ponto de Extremidade no iOS usando um aplicativo
keywords: microsoft, defender, Microsoft Defender for Endpoint, ios, app, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: 6f2b9a1365a27bb7397aea51dcd5bc9e2631afe2
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624700"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="dde15-104">Implantar o Microsoft Defender para Ponto de Extremidade no iOS</span><span class="sxs-lookup"><span data-stu-id="dde15-104">Deploy Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="dde15-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="dde15-105">**Applies to:**</span></span>
- [<span data-ttu-id="dde15-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="dde15-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dde15-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dde15-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="dde15-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="dde15-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="dde15-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="dde15-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="dde15-110">Este tópico descreve a implantação do Defender para Ponto de Extremidade no iOS em Portal da Empresa do Intune dispositivos inscritos.</span><span class="sxs-lookup"><span data-stu-id="dde15-110">This topic describes deploying Defender for Endpoint on iOS on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="dde15-111">Para obter mais informações sobre o registro de dispositivo do Intune, consulte [Registrar dispositivos iOS/iPadOS no Intune](/mem/intune/enrollment/ios-enroll).</span><span class="sxs-lookup"><span data-stu-id="dde15-111">For more information about Intune device enrollment, see [Enroll iOS/iPadOS devices in Intune](/mem/intune/enrollment/ios-enroll).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="dde15-112">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="dde15-112">Before you begin</span></span>

- <span data-ttu-id="dde15-113">Verifique se você tem acesso ao Centro de [administração do Gerenciador de Pontos de Extremidade da Microsoft.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="dde15-113">Ensure you have access to [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>

- <span data-ttu-id="dde15-114">Certifique-se de que o registro do iOS seja feito para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="dde15-114">Ensure iOS enrollment is done for your users.</span></span> <span data-ttu-id="dde15-115">Os usuários precisam ter uma licença do Defender para Ponto de Extremidade atribuída para usar o Defender para o Ponto de Extremidade no iOS.</span><span class="sxs-lookup"><span data-stu-id="dde15-115">Users need to have a Defender for Endpoint license assigned in order to use Defender for Endpoint on iOS.</span></span> <span data-ttu-id="dde15-116">Consulte [Atribuir licenças aos usuários para](/azure/active-directory/users-groups-roles/licensing-groups-assign) obter instruções sobre como atribuir licenças.</span><span class="sxs-lookup"><span data-stu-id="dde15-116">Refer to [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign) for instructions on how to assign licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="dde15-117">O Microsoft Defender para Ponto de Extremidade no iOS agora está disponível na [Apple App Store](https://aka.ms/mdatpiosappstore).</span><span class="sxs-lookup"><span data-stu-id="dde15-117">Microsoft Defender for Endpoint on iOS is now available in the [Apple App Store](https://aka.ms/mdatpiosappstore).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="dde15-118">Etapas de implantação</span><span class="sxs-lookup"><span data-stu-id="dde15-118">Deployment steps</span></span>

<span data-ttu-id="dde15-119">Implante o Defender para Ponto de Extremidade no iOS por meio Portal da Empresa do Intune.</span><span class="sxs-lookup"><span data-stu-id="dde15-119">Deploy Defender for Endpoint on iOS via Intune Company Portal.</span></span>

### <a name="add-ios-store-app"></a><span data-ttu-id="dde15-120">Adicionar aplicativo da loja do iOS</span><span class="sxs-lookup"><span data-stu-id="dde15-120">Add iOS store app</span></span>

1. <span data-ttu-id="dde15-121">No Centro de administração do Gerenciador de Pontos de Extremidade [da Microsoft,](https://go.microsoft.com/fwlink/?linkid=2109431)vá para **Aplicativos**  ->  **iOS/iPadOS** Adicionar aplicativo da loja  ->    ->  **do iOS** e clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="dde15-121">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Apps** -> **iOS/iPadOS** -> **Add** -> **iOS store app** and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="dde15-122">![Imagem do Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span><span class="sxs-lookup"><span data-stu-id="dde15-122">![Image of Microsoft Endpoint Manager Admin Center1](images/ios-deploy-1.png)</span></span>

1. <span data-ttu-id="dde15-123">Na página Adicionar aplicativo, clique em **Pesquisar na Loja de Aplicativos** e digite o Ponto de Extremidade do Microsoft **Defender** na barra de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="dde15-123">On the Add app page, click on **Search the App Store** and type **Microsoft Defender Endpoint** in the search bar.</span></span> <span data-ttu-id="dde15-124">Na seção resultados da pesquisa, clique em Ponto de *Extremidade do Microsoft Defender* e clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="dde15-124">In the search results section, click on *Microsoft Defender Endpoint* and click **Select**.</span></span>

1. <span data-ttu-id="dde15-125">Selecione **iOS 11.0 como** o sistema operacional Mínimo.</span><span class="sxs-lookup"><span data-stu-id="dde15-125">Select **iOS 11.0** as the Minimum operating system.</span></span> <span data-ttu-id="dde15-126">Revise o restante das informações sobre o aplicativo e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="dde15-126">Review the rest of information about the app and click **Next**.</span></span>

1. <span data-ttu-id="dde15-127">Na seção *Atribuições,* vá para a seção **Obrigatório** e selecione **Adicionar grupo**.</span><span class="sxs-lookup"><span data-stu-id="dde15-127">In the *Assignments* section, go to the **Required** section and select **Add group**.</span></span> <span data-ttu-id="dde15-128">Em seguida, você pode escolher os grupos de usuários que você gostaria de direcionar o Defender para Ponto de Extremidade no aplicativo iOS.</span><span class="sxs-lookup"><span data-stu-id="dde15-128">You can then choose the user group(s) that you would like to target Defender for Endpoint on iOS app.</span></span> <span data-ttu-id="dde15-129">Clique **em Selecionar** e, em **seguida, Em Seguida.**</span><span class="sxs-lookup"><span data-stu-id="dde15-129">Click **Select** and then **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dde15-130">O grupo de usuários selecionado deve consistir em usuários inscritos do Intune.</span><span class="sxs-lookup"><span data-stu-id="dde15-130">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="dde15-131">![Imagem do Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span><span class="sxs-lookup"><span data-stu-id="dde15-131">![Image of Microsoft Endpoint Manager Admin Center2](images/ios-deploy-2.png)</span></span>

1. <span data-ttu-id="dde15-132">Na seção *Revisar + Criar,* verifique se todas as informações inseridas estão corretas e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="dde15-132">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span> <span data-ttu-id="dde15-133">Em alguns instantes, o aplicativo Defender para Ponto de Extremidade deve ser criado com êxito, e uma notificação deve aparecer no canto superior direito da página.</span><span class="sxs-lookup"><span data-stu-id="dde15-133">In a few moments, the Defender for Endpoint app should be created successfully, and a notification should show up at the top-right corner of the page.</span></span>

1. <span data-ttu-id="dde15-134">Na página informações do aplicativo exibida, na seção **Monitor,** selecione **Status** de instalação do dispositivo para verificar se a instalação do dispositivo foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="dde15-134">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="dde15-135">![Imagem do Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span><span class="sxs-lookup"><span data-stu-id="dde15-135">![Image of Microsoft Endpoint Manager Admin Center3](images/ios-deploy-3.png)</span></span>

## <a name="auto-onboarding-of-vpn-profile-simplified-onboarding"></a><span data-ttu-id="dde15-136">Integração automática do perfil VPN (Integração Simplificada)</span><span class="sxs-lookup"><span data-stu-id="dde15-136">Auto-Onboarding of VPN profile (Simplified Onboarding)</span></span>

> [!NOTE]
> <span data-ttu-id="dde15-137">A integração automática do perfil VPN está atualmente em visualização e as etapas mencionadas nesta seção podem ser substancialmente modificadas antes de serem lançadas comercialmente.</span><span class="sxs-lookup"><span data-stu-id="dde15-137">Auto-onboarding of VPN profile is currently in preview and the steps mentioned in this section may be substantially modified before it's commercially released.</span></span>

<span data-ttu-id="dde15-138">Os administradores podem configurar automaticamente a configuração do perfil vpn.</span><span class="sxs-lookup"><span data-stu-id="dde15-138">Admins can configure auto-setup of VPN profile.</span></span> <span data-ttu-id="dde15-139">Isso configurará automaticamente o perfil VPN do Defender para Ponto de Extremidade sem que o usuário faça isso durante a integração.</span><span class="sxs-lookup"><span data-stu-id="dde15-139">This will automatically setup the Defender for Endpoint VPN profile without having the user to do so while onboarding.</span></span> <span data-ttu-id="dde15-140">Observe que a VPN é usada para fornecer o recurso de Proteção da Web.</span><span class="sxs-lookup"><span data-stu-id="dde15-140">Note that VPN is used in order to provide the Web Protection feature.</span></span> <span data-ttu-id="dde15-141">Esta não é uma VPN regular e é uma VPN local/auto-loop que não faz o tráfego fora do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="dde15-141">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

1. <span data-ttu-id="dde15-142">No Centro de administração do Gerenciador de Pontos de Extremidade [da Microsoft,](https://go.microsoft.com/fwlink/?linkid=2109431)vá para   ->  **Perfis de Configuração** de  ->  **Dispositivos Criar Perfil**.</span><span class="sxs-lookup"><span data-stu-id="dde15-142">In [Microsoft Endpoint manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), go to **Devices** -> **Configuration Profiles** -> **Create Profile**.</span></span>
1. <span data-ttu-id="dde15-143">Escolha **Plataforma como** **iOS/iPadOS** e **Tipo de perfil** como **VPN**.</span><span class="sxs-lookup"><span data-stu-id="dde15-143">Choose **Platform** as **iOS/iPadOS** and **Profile type** as **VPN**.</span></span> <span data-ttu-id="dde15-144">Clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="dde15-144">Click **Create**.</span></span>
1. <span data-ttu-id="dde15-145">Digite um nome para o perfil e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="dde15-145">Type a name for the profile and click **Next**.</span></span>
1. <span data-ttu-id="dde15-146">Selecione **VPN personalizada** para Tipo de Conexão e, na seção VPN **Base,** insira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="dde15-146">Select **Custom VPN** for Connection Type and in the **Base VPN** section, enter the following:</span></span>
    - <span data-ttu-id="dde15-147">Nome da conexão = Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="dde15-147">Connection Name = Microsoft Defender for Endpoint</span></span>
    - <span data-ttu-id="dde15-148">Endereço do servidor VPN = 127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="dde15-148">VPN server address = 127.0.0.1</span></span>
    - <span data-ttu-id="dde15-149">Método Auth = "Nome de usuário e senha"</span><span class="sxs-lookup"><span data-stu-id="dde15-149">Auth method = "Username and password"</span></span>
    - <span data-ttu-id="dde15-150">Túnel Dividido = Desabilitar</span><span class="sxs-lookup"><span data-stu-id="dde15-150">Split Tunneling = Disable</span></span>
    - <span data-ttu-id="dde15-151">Identificador vpn = com.microsoft.scmx</span><span class="sxs-lookup"><span data-stu-id="dde15-151">VPN identifier = com.microsoft.scmx</span></span>
    - <span data-ttu-id="dde15-152">Nos pares de valores-chave, insira a **chave AutoOnboard** e despeça o valor como **True**.</span><span class="sxs-lookup"><span data-stu-id="dde15-152">In the key-value pairs, enter the key **AutoOnboard** and set the value to **True**.</span></span>
    - <span data-ttu-id="dde15-153">Tipo de VPN automática = VPN sob demanda</span><span class="sxs-lookup"><span data-stu-id="dde15-153">Type of Automatic VPN = On-demand VPN</span></span>
    - <span data-ttu-id="dde15-154">Clique **em Adicionar** regras sob **demanda** e selecione Quero fazer o seguinte = Estabelecer **VPN**, quero restringir a = Todos os **domínios**.</span><span class="sxs-lookup"><span data-stu-id="dde15-154">Click **Add** for **On Demand Rules** and select **I want to do the following = Establish VPN**, **I want to restrict to = All domains**.</span></span>

    ![Uma captura de tela da configuração de perfil vpn](images/ios-deploy-8.png)

1. <span data-ttu-id="dde15-156">Clique em Próximo e atribua o perfil a usuários direcionados.</span><span class="sxs-lookup"><span data-stu-id="dde15-156">Click Next and assign the profile to targeted users.</span></span>
1. <span data-ttu-id="dde15-157">Na seção *Revisar + Criar,* verifique se todas as informações inseridas estão corretas e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="dde15-157">In the *Review + Create* section, verify that all the information entered is correct and then select **Create**.</span></span>

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="dde15-158">Concluir a integração e verificar o status</span><span class="sxs-lookup"><span data-stu-id="dde15-158">Complete onboarding and check status</span></span>

1. <span data-ttu-id="dde15-159">Depois que o Defender for Endpoint no iOS tiver sido instalado no dispositivo, você verá o ícone do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dde15-159">Once Defender for Endpoint on iOS has been installed on the device, you  will see the app icon.</span></span>

    ![Uma captura de tela de um telefone inteligente Descrição gerada automaticamente](images/41627a709700c324849bf7e13510c516.png)

2. <span data-ttu-id="dde15-161">Toque no ícone do aplicativo Defender para Ponto de Extremidade e siga as instruções na tela para concluir as etapas de integração.</span><span class="sxs-lookup"><span data-stu-id="dde15-161">Tap the Defender for Endpoint app icon and follow the on-screen instructions to complete the onboarding steps.</span></span> <span data-ttu-id="dde15-162">Os detalhes incluem a aceitação do usuário final das permissões do iOS exigidas pelo Defender para Ponto de Extremidade no iOS.</span><span class="sxs-lookup"><span data-stu-id="dde15-162">The details include end-user acceptance of iOS permissions required by Defender for Endpoint on iOS.</span></span>

3. <span data-ttu-id="dde15-163">Após a integração bem-sucedida, o dispositivo começará a aparecer na lista Dispositivos Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="dde15-163">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="dde15-164">![Uma captura de tela de um telefone celular Descrição gerada automaticamente](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span><span class="sxs-lookup"><span data-stu-id="dde15-164">![A screenshot of a cell phone Description automatically generated](images/e07f270419f7b1e5ee6744f8b38ddeaf.png)</span></span>

## <a name="configure-microsoft-defender-for-endpoint-for-supervised-mode"></a><span data-ttu-id="dde15-165">Configurar o Microsoft Defender para Ponto de Extremidade para Modo Supervisionado</span><span class="sxs-lookup"><span data-stu-id="dde15-165">Configure Microsoft Defender for Endpoint for Supervised Mode</span></span>

<span data-ttu-id="dde15-166">O Microsoft Defender for Endpoint no aplicativo iOS tem capacidade especializada em dispositivos iOS/iPadOS supervisionados, dado o aumento dos recursos de gerenciamento fornecidos pela plataforma nesses tipos de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="dde15-166">The Microsoft Defender for Endpoint on iOS app has specialized ability on supervised iOS/iPadOS devices, given the increased management capabilities provided by the platform on these types of devices.</span></span> <span data-ttu-id="dde15-167">Para aproveitar esses recursos, o aplicativo Defender for Endpoint precisa saber se um dispositivo está no modo Supervisionado.</span><span class="sxs-lookup"><span data-stu-id="dde15-167">To take advantage of these capabilities, the Defender for Endpoint app needs to know if a device is in Supervised Mode.</span></span>

### <a name="configure-supervised-mode-via-intune"></a><span data-ttu-id="dde15-168">Configurar o modo Supervisionado por meio do Intune</span><span class="sxs-lookup"><span data-stu-id="dde15-168">Configure Supervised Mode via Intune</span></span>

<span data-ttu-id="dde15-169">O Intune permite configurar o aplicativo Defender para iOS por meio de uma política de Configuração de Aplicativo.</span><span class="sxs-lookup"><span data-stu-id="dde15-169">Intune allows you to configure the Defender for iOS app through an App Configuration policy.</span></span>

   > [!NOTE]
   > <span data-ttu-id="dde15-170">Esta política de configuração de aplicativo para dispositivos supervisionados é aplicável apenas a dispositivos gerenciados e deve ser direcionada para todos os dispositivos iOS gerenciados como uma prática prática prática.</span><span class="sxs-lookup"><span data-stu-id="dde15-170">This app configuration policy for supervised devices is applicable only to managed devices and should be targeted for all managed iOS devices as a best practice.</span></span>

1. <span data-ttu-id="dde15-171">Entre no centro de administração [Microsoft Endpoint Manager e](https://go.microsoft.com/fwlink/?linkid=2109431) vá para Políticas de configuração do Aplicativo de   >  **Aplicativos**  >  **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="dde15-171">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) and go to **Apps** > **App configuration policies** > **Add**.</span></span> <span data-ttu-id="dde15-172">Clique em **Dispositivos gerenciados**.</span><span class="sxs-lookup"><span data-stu-id="dde15-172">Click on **Managed devices**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="dde15-173">![Imagem do Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span><span class="sxs-lookup"><span data-stu-id="dde15-173">![Image of Microsoft Endpoint Manager Admin Center4](images/ios-deploy-4.png)</span></span>

1. <span data-ttu-id="dde15-174">Na página *Criar política de configuração de aplicativo,* forneça as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="dde15-174">In the *Create app configuration policy* page, provide the following information:</span></span>
    - <span data-ttu-id="dde15-175">Nome da política</span><span class="sxs-lookup"><span data-stu-id="dde15-175">Policy Name</span></span>
    - <span data-ttu-id="dde15-176">Plataforma: Selecione iOS/iPadOS</span><span class="sxs-lookup"><span data-stu-id="dde15-176">Platform: Select iOS/iPadOS</span></span>
    - <span data-ttu-id="dde15-177">Aplicativo direcionado: selecione **Microsoft Defender ATP** na lista</span><span class="sxs-lookup"><span data-stu-id="dde15-177">Targeted app: Select **Microsoft Defender ATP** from the list</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="dde15-178">![Imagem do Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span><span class="sxs-lookup"><span data-stu-id="dde15-178">![Image of Microsoft Endpoint Manager Admin Center5](images/ios-deploy-5.png)</span></span>

1. <span data-ttu-id="dde15-179">Na próxima tela, selecione **Usar designer de configuração** como o formato.</span><span class="sxs-lookup"><span data-stu-id="dde15-179">In the next screen, select **Use configuration designer** as the format.</span></span> <span data-ttu-id="dde15-180">Especifique a seguinte propriedade:</span><span class="sxs-lookup"><span data-stu-id="dde15-180">Specify the following property:</span></span>
    - <span data-ttu-id="dde15-181">Chave de Configuração: supervisionada</span><span class="sxs-lookup"><span data-stu-id="dde15-181">Configuration Key: issupervised</span></span>
    - <span data-ttu-id="dde15-182">Tipo de valor: Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="dde15-182">Value type: String</span></span>
    - <span data-ttu-id="dde15-183">Valor da configuração: {{issupervised}}</span><span class="sxs-lookup"><span data-stu-id="dde15-183">Configuration Value: {{issupervised}}</span></span>
    
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="dde15-184">![Imagem do Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span><span class="sxs-lookup"><span data-stu-id="dde15-184">![Image of Microsoft Endpoint Manager Admin Center6](images/ios-deploy-6.png)</span></span>

1. <span data-ttu-id="dde15-185">Clique **em Próximo** para abrir a página Marcas de **escopo.**</span><span class="sxs-lookup"><span data-stu-id="dde15-185">Click **Next** to open the **Scope tags** page.</span></span> <span data-ttu-id="dde15-186">As marcas de escopo são opcionais.</span><span class="sxs-lookup"><span data-stu-id="dde15-186">Scope tags are optional.</span></span> <span data-ttu-id="dde15-187">Clique em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="dde15-187">Click **Next** to continue.</span></span>

1. <span data-ttu-id="dde15-188">Na página **Atribuições,** selecione os grupos que receberão esse perfil.</span><span class="sxs-lookup"><span data-stu-id="dde15-188">On the **Assignments** page, select the groups that will receive this profile.</span></span> <span data-ttu-id="dde15-189">Para esse cenário, é prática ideal direcionar Todos os **Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="dde15-189">For this scenario, it is best practice to target **All Devices**.</span></span> <span data-ttu-id="dde15-190">Para obter mais informações sobre como atribuir perfis, consulte [Assign user and device profiles](/mem/intune/configuration/device-profile-assign).</span><span class="sxs-lookup"><span data-stu-id="dde15-190">For more information on assigning profiles, see [Assign user and device profiles](/mem/intune/configuration/device-profile-assign).</span></span>

   <span data-ttu-id="dde15-191">Ao implantar em grupos de usuários, um usuário deve entrar em um dispositivo antes da aplicação da política.</span><span class="sxs-lookup"><span data-stu-id="dde15-191">When deploying to user groups, a user must sign in to a device before the policy applies.</span></span>

   <span data-ttu-id="dde15-192">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dde15-192">Click **Next**.</span></span>

1. <span data-ttu-id="dde15-193">Na página **Revisar + criar,** quando terminar, escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="dde15-193">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="dde15-194">O novo perfil é exibido na lista de perfis de configuração.</span><span class="sxs-lookup"><span data-stu-id="dde15-194">The new profile is displayed in the list of configuration profiles.</span></span>

1. <span data-ttu-id="dde15-195">Em seguida, para recursos avançados de anti-phishing, você pode implantar um perfil personalizado nos dispositivos iOS supervisionados.</span><span class="sxs-lookup"><span data-stu-id="dde15-195">Next, for enhanced Anti-phishing capabilities, you can deploy a custom profile on the supervised iOS devices.</span></span> <span data-ttu-id="dde15-196">Siga as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="dde15-196">Follow the steps below:</span></span>
    - <span data-ttu-id="dde15-197">Baixar o perfil de configuração de [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span><span class="sxs-lookup"><span data-stu-id="dde15-197">Download the config profile from [https://aka.ms/mdatpiossupervisedprofile](https://aka.ms/mdatpiossupervisedprofile)</span></span>
    - <span data-ttu-id="dde15-198">Navegar até **dispositivos**  ->  **iOS/iPadOS** Perfis de  ->  **configuração**  ->  **Criar Perfil**</span><span class="sxs-lookup"><span data-stu-id="dde15-198">Navigate to **Devices** -> **iOS/iPadOS** -> **Configuration profiles** -> **Create Profile**</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="dde15-199">![Imagem do Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span><span class="sxs-lookup"><span data-stu-id="dde15-199">![Image of Microsoft Endpoint Manager Admin Center7](images/ios-deploy-7.png)</span></span>

    - <span data-ttu-id="dde15-200">Forneça um nome do perfil.</span><span class="sxs-lookup"><span data-stu-id="dde15-200">Provide a name of the profile.</span></span> <span data-ttu-id="dde15-201">Quando solicitado a importar um arquivo de perfil de configuração, selecione o que foi baixado acima.</span><span class="sxs-lookup"><span data-stu-id="dde15-201">When prompted to import a Configuration profile file, select the one downloaded above.</span></span>
    - <span data-ttu-id="dde15-202">Na seção **Atribuição,** selecione o grupo de dispositivos ao qual você deseja aplicar esse perfil.</span><span class="sxs-lookup"><span data-stu-id="dde15-202">In the **Assignment** section, select the device group to which you want to apply this profile.</span></span> <span data-ttu-id="dde15-203">Como prática prática, isso deve ser aplicado a todos os dispositivos iOS gerenciados.</span><span class="sxs-lookup"><span data-stu-id="dde15-203">As a best practice, this should be applied to all managed iOS devices.</span></span> <span data-ttu-id="dde15-204">Clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dde15-204">Click **Next**.</span></span>
    - <span data-ttu-id="dde15-205">Na página **Revisar + criar,** quando terminar, escolha **Criar**.</span><span class="sxs-lookup"><span data-stu-id="dde15-205">On the **Review + create** page, when you're done, choose **Create**.</span></span> <span data-ttu-id="dde15-206">O novo perfil é exibido na lista de perfis de configuração.</span><span class="sxs-lookup"><span data-stu-id="dde15-206">The new profile is displayed in the list of configuration profiles.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dde15-207">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="dde15-207">Next Steps</span></span>

[<span data-ttu-id="dde15-208">Configurar o Defender para Ponto de Extremidade em recursos do iOS</span><span class="sxs-lookup"><span data-stu-id="dde15-208">Configure Defender for Endpoint on iOS features</span></span>](ios-configure-features.md)
