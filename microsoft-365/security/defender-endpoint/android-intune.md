---
title: Implantar o Microsoft Defender ATP para Android com o Microsoft Intune
description: Descreve como implantar o Microsoft Defender ATP para Android com o Microsoft Intune
keywords: microsoft, defender, atp, android, installation, deploy, uninstallation,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e557f60346b2f68354df621b6e4812eac775d812
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165664"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-android-with-microsoft-intune"></a><span data-ttu-id="f4c25-104">Implantar o Microsoft Defender para Ponto de Extremidade para Android com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f4c25-104">Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f4c25-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f4c25-105">**Applies to:**</span></span>
- [<span data-ttu-id="f4c25-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="f4c25-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f4c25-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4c25-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f4c25-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="f4c25-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f4c25-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="f4c25-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="f4c25-110">Saiba como implantar o Defender para Ponto de Extremidade para Android em dispositivos inscritos no Portal da Empresa do Intune.</span><span class="sxs-lookup"><span data-stu-id="f4c25-110">Learn how to deploy Defender for Endpoint for Android on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="f4c25-111">Para obter mais informações sobre o registro do dispositivo Intune, consulte  [Registrar seu dispositivo](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal).</span><span class="sxs-lookup"><span data-stu-id="f4c25-111">For more information about Intune device enrollment, see  [Enroll your device](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="f4c25-112">**O Defender para Ponto de Extremidade para Android agora está disponível no [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="f4c25-112">**Defender for Endpoint for Android is now available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span></span> <br>
> <span data-ttu-id="f4c25-113">Você pode se conectar ao Google Play do Intune para implantar o aplicativo Defender para Ponto de Extremidade nos modos de entrolamento do Administrador de Dispositivos e Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f4c25-113">You can connect to Google Play from Intune to deploy Defender for Endpoint app across Device Administrator and Android Enterprise entrollment modes.</span></span>
<span data-ttu-id="f4c25-114">As atualizações para o aplicativo são automáticas por meio do Google Play.</span><span class="sxs-lookup"><span data-stu-id="f4c25-114">Updates to the app are automatic via Google Play.</span></span>

## <a name="deploy-on-device-administrator-enrolled-devices"></a><span data-ttu-id="f4c25-115">Implantar em dispositivos inscritos pelo Administrador de Dispositivos</span><span class="sxs-lookup"><span data-stu-id="f4c25-115">Deploy on Device Administrator enrolled devices</span></span>

<span data-ttu-id="f4c25-116">**Implantar o Defender para Ponto de Extremidade para Android no Portal da Empresa do Intune - Dispositivos inscritos pelo Administrador de Dispositivos**</span><span class="sxs-lookup"><span data-stu-id="f4c25-116">**Deploy Defender for Endpoint for Android on Intune Company Portal - Device Administrator enrolled devices**</span></span>

<span data-ttu-id="f4c25-117">Saiba como implantar o Defender para Ponto de Extremidade para Android no Portal da Empresa do Intune - Dispositivos inscritos pelo Administrador de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f4c25-117">Learn how to deploy Defender for Endpoint for Android on Intune Company Portal - Device Administrator enrolled devices.</span></span> 

### <a name="add-as-android-store-app"></a><span data-ttu-id="f4c25-118">Adicionar como aplicativo da Loja do Android</span><span class="sxs-lookup"><span data-stu-id="f4c25-118">Add as Android store app</span></span>

1. <span data-ttu-id="f4c25-119">No [Centro de administração do Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431) acesse  \> **Aplicativos Android Apps** Adicionar aplicativo da Loja \> **do \> Android** e **escolha Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-119">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add \> Android store app** and choose **Select**.</span></span>

   ![Imagem do Microsoft Endpoint Manager Admin Center add android store application](images/mda-addandroidstoreapp.png)

2. <span data-ttu-id="f4c25-121">Na página **Adicionar aplicativo** e na seção Informações *do* Aplicativo, insira:</span><span class="sxs-lookup"><span data-stu-id="f4c25-121">On the **Add app** page and in the *App Information* section enter:</span></span> 

   - <span data-ttu-id="f4c25-122">**Nome**</span><span class="sxs-lookup"><span data-stu-id="f4c25-122">**Name**</span></span> 
   - <span data-ttu-id="f4c25-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f4c25-123">**Description**</span></span>
   - <span data-ttu-id="f4c25-124">**Publisher** como Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f4c25-124">**Publisher** as Microsoft.</span></span>
   - <span data-ttu-id="f4c25-125">**URL da Loja de Aplicativos** https://play.google.com/store/apps/details?id=com.microsoft.scmx como (URL do Defender for Endpoint App Google Play Store)</span><span class="sxs-lookup"><span data-stu-id="f4c25-125">**App store URL** as https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint app Google Play Store URL)</span></span> 

   <span data-ttu-id="f4c25-126">Outros campos são opcionais.</span><span class="sxs-lookup"><span data-stu-id="f4c25-126">Other fields are optional.</span></span> <span data-ttu-id="f4c25-127">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-127">Select **Next**.</span></span>

   ![Imagem do Centro de Administração do Microsoft Endpoint Manager adicionar informações de aplicativo](images/mda-addappinfo.png)

3. <span data-ttu-id="f4c25-129">Na seção *Atribuições,* vá para a seção **Obrigatório** e selecione **Adicionar grupo.**</span><span class="sxs-lookup"><span data-stu-id="f4c25-129">In the *Assignments* section, go to the **Required** section and select **Add group.**</span></span> <span data-ttu-id="f4c25-130">Em seguida, você pode escolher os grupos de usuários que você gostaria de direcionar o Defender para o ponto de extremidade para aplicativo Android.</span><span class="sxs-lookup"><span data-stu-id="f4c25-130">You can then choose the user group(s) that you would like to target Defender for Endpoint for Android app.</span></span> <span data-ttu-id="f4c25-131">Escolha **Selecionar** e, em **seguida, Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-131">Choose **Select** and then **Next**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="f4c25-132">O grupo de usuários selecionado deve consistir em usuários inscritos do Intune.</span><span class="sxs-lookup"><span data-stu-id="f4c25-132">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]

    > ![Imagem dos grupos de usuários selecionados do Centro de Administração do Microsoft Endpoint Manager](images/363bf30f7d69a94db578e8af0ddd044b.png)

4. <span data-ttu-id="f4c25-134">Na seção **Review+Create,** verifique se todas as informações inseridas estão corretas e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-134">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

    <span data-ttu-id="f4c25-135">Em alguns instantes, o aplicativo Defender para Ponto de Extremidade seria criado com êxito, e uma notificação apareceria no canto superior direito da página.</span><span class="sxs-lookup"><span data-stu-id="f4c25-135">In a few moments, the Defender for Endpoint app would be created successfully, and a notification would show up at the top-right corner of the page.</span></span>

    ![Imagem da notificação do Centro de Administração do Microsoft Endpoint Manager do aplicativo de ponto de extremidade do defender](images/86cbe56f88bb6e93e9c63303397fc24f.png)

5. <span data-ttu-id="f4c25-137">Na página informações do aplicativo exibida, na seção **Monitor,** selecione **Status** de instalação do dispositivo para verificar se a instalação do dispositivo foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="f4c25-137">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4c25-138">![Imagem da instalação do dispositivo do Centro de Administração do Microsoft Endpoint Manager](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span><span class="sxs-lookup"><span data-stu-id="f4c25-138">![Image of Microsoft Endpoint Manager Admin Center device install](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span></span>

### <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="f4c25-139">Concluir a integração e verificar o status</span><span class="sxs-lookup"><span data-stu-id="f4c25-139">Complete onboarding and check status</span></span>

1. <span data-ttu-id="f4c25-140">Depois que o Defender for Endpoint para Android tiver sido instalado no dispositivo, você verá o ícone do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f4c25-140">Once Defender for Endpoint for Android has been installed on the device, you'll see the app icon.</span></span>

    ![Ícone em dispositivo móvel](images/7cf9311ad676ec5142002a4d0c2323ca.jpg)

2. <span data-ttu-id="f4c25-142">Toque no ícone de aplicativo do Microsoft Defender ATP e siga as instruções na tela para concluir a integração do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f4c25-142">Tap the Microsoft Defender ATP app icon and follow the on-screen instructions to complete onboarding the app.</span></span> <span data-ttu-id="f4c25-143">Os detalhes incluem a aceitação do usuário final das permissões do Android exigidas pelo Defender para Ponto de Extremidade para Android.</span><span class="sxs-lookup"><span data-stu-id="f4c25-143">The details include end-user acceptance of Android permissions required by Defender for Endpoint for Android.</span></span>

3. <span data-ttu-id="f4c25-144">Após a integração bem-sucedida, o dispositivo começará a aparecer na lista Dispositivos no Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="f4c25-144">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    ![Imagem do dispositivo no portal do Defender para Ponto de Extremidade](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="deploy-on-android-enterprise-enrolled-devices"></a><span data-ttu-id="f4c25-146">Implantar em dispositivos inscritos no Android Enterprise</span><span class="sxs-lookup"><span data-stu-id="f4c25-146">Deploy on Android Enterprise enrolled devices</span></span>

<span data-ttu-id="f4c25-147">O Defender para Ponto de Extremidade para Android dá suporte a dispositivos inscritos no Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="f4c25-147">Defender for Endpoint for Android supports Android Enterprise enrolled devices.</span></span>

<span data-ttu-id="f4c25-148">Para obter mais informações sobre as opções de registro com suporte do Intune, consulte [Opções de Inscrição](https://docs.microsoft.com/mem/intune/enrollment/android-enroll).</span><span class="sxs-lookup"><span data-stu-id="f4c25-148">For more information on the enrollment options supported by Intune, see [Enrollment Options](https://docs.microsoft.com/mem/intune/enrollment/android-enroll).</span></span>

<span data-ttu-id="f4c25-149">**Atualmente, dispositivos de propriedade pessoal com perfil de trabalho e registro de dispositivos de usuário totalmente gerenciados de propriedade corporativa são suportados para implantação.**</span><span class="sxs-lookup"><span data-stu-id="f4c25-149">**Currently, Personally owned devices with work profile and Corporate-owned fully managed user device enrollments are supported for deployment.**</span></span>

## <a name="add-microsoft-defender-for-endpoint-for-android-as-a-managed-google-play-app"></a><span data-ttu-id="f4c25-150">Adicionar o Microsoft Defender para Ponto de Extremidade para Android como um aplicativo gerenciado do Google Play</span><span class="sxs-lookup"><span data-stu-id="f4c25-150">Add Microsoft Defender for Endpoint for Android as a Managed Google Play app</span></span>

<span data-ttu-id="f4c25-151">Siga as etapas a seguir para adicionar o aplicativo Microsoft Defender para Ponto de Extremidade ao Google Play gerenciado.</span><span class="sxs-lookup"><span data-stu-id="f4c25-151">Follow the steps below to add Microsoft Defender for Endpoint app into your managed Google Play.</span></span>

1. <span data-ttu-id="f4c25-152">No [Centro de administração do Microsoft Endpoint Manager,](https://go.microsoft.com/fwlink/?linkid=2109431) acesse  \> **Aplicativos Android Apps** Adicionar e \>  selecione Aplicativo Gerenciado do **Google Play**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-152">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add** and select **Managed Google Play app**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4c25-153">![Imagem do Centro de administração do Microsoft Endpoint Manager gerenciado google play](images/579ff59f31f599414cedf63051628b2e.png)</span><span class="sxs-lookup"><span data-stu-id="f4c25-153">![Image of Microsoft Endpoint Manager admin center managed google play](images/579ff59f31f599414cedf63051628b2e.png)</span></span>

2. <span data-ttu-id="f4c25-154">Na página gerenciada do Google Play que é carregada posteriormente, vá até a caixa de pesquisa e procure o **Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="f4c25-154">On your managed Google Play page that loads subsequently, go to the search box and lookup **Microsoft Defender.**</span></span> <span data-ttu-id="f4c25-155">Sua pesquisa deve exibir o aplicativo Microsoft Defender para Ponto de Extremidade em seu Google Play Gerenciado.</span><span class="sxs-lookup"><span data-stu-id="f4c25-155">Your search should display the Microsoft Defender for Endpoint app in your Managed Google Play.</span></span> <span data-ttu-id="f4c25-156">Clique no aplicativo Microsoft Defender para Ponto de Extremidade no resultado da pesquisa aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f4c25-156">Click on the Microsoft Defender for Endpoint app from the Apps search result.</span></span>

    ![Imagem do Centro de administração do Microsoft Endpoint Manager Pesquisa de aplicativos](images/0f79cb37900b57c3e2bb0effad1c19cb.png)

3. <span data-ttu-id="f4c25-158">Na página Descrição do aplicativo que vem a seguir, você deve ser capaz de ver detalhes do aplicativo no Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="f4c25-158">In the App description page that comes up next, you should be able to see app details on Defender for Endpoint.</span></span> <span data-ttu-id="f4c25-159">Revise as informações na página e selecione **Aprovar**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-159">Review the information on the page and then select **Approve**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4c25-160">![Uma captura de tela de um Google Play Gerenciado](images/07e6d4119f265037e3b80a20a73b856f.png)</span><span class="sxs-lookup"><span data-stu-id="f4c25-160">![A screenshot of a Managed Google Play](images/07e6d4119f265037e3b80a20a73b856f.png)</span></span>

4. <span data-ttu-id="f4c25-161">Você será apresentado com as permissões que o Defender for Endpoint obtém para que ele funcione.</span><span class="sxs-lookup"><span data-stu-id="f4c25-161">You'll be presented with the permissions that Defender for Endpoint obtains for it to work.</span></span> <span data-ttu-id="f4c25-162">Revise-os e selecione **Aprovar**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-162">Review them and then select **Approve**.</span></span>

    ![Uma captura de tela da aprovação do aplicativo de visualização do Defender para Ponto de Extremidade](images/206b3d954f06cc58b3466fb7a0bd9f74.png)

5. <span data-ttu-id="f4c25-164">Você será apresentado com a página Configurações de Aprovação.</span><span class="sxs-lookup"><span data-stu-id="f4c25-164">You'll be presented with the Approval settings page.</span></span> <span data-ttu-id="f4c25-165">A página confirma sua preferência para lidar com novas permissões de aplicativo que o Defender para Ponto de Extremidade para Android pode solicitar.</span><span class="sxs-lookup"><span data-stu-id="f4c25-165">The page confirms your preference to handle new app permissions that Defender for Endpoint for Android might ask.</span></span> <span data-ttu-id="f4c25-166">Revise as opções e selecione sua opção preferida.</span><span class="sxs-lookup"><span data-stu-id="f4c25-166">Review the choices and select your preferred option.</span></span> <span data-ttu-id="f4c25-167">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-167">Select **Done**.</span></span>

    <span data-ttu-id="f4c25-168">Por padrão, o Google Play gerenciado seleciona *Manter aprovado quando o aplicativo solicita novas permissões*</span><span class="sxs-lookup"><span data-stu-id="f4c25-168">By default, managed Google Play selects *Keep approved when app requests new permissions*</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4c25-169">![Imagem da guia notificações](images/ffecfdda1c4df14148f1526c22cc0236.png)</span><span class="sxs-lookup"><span data-stu-id="f4c25-169">![Image of notifications tab](images/ffecfdda1c4df14148f1526c22cc0236.png)</span></span>

6. <span data-ttu-id="f4c25-170">Depois que a seleção de manipulação de permissões for feita, selecione **Sincronizar** para sincronizar o Microsoft Defender para o Ponto de Extremidade à sua lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f4c25-170">After the permissions handling selection is made, select **Sync** to sync Microsoft Defender for Endpoint to your apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4c25-171">![Imagem da página de sincronização](images/34e6b9a0dae125d085c84593140180ed.png)</span><span class="sxs-lookup"><span data-stu-id="f4c25-171">![Image of sync page](images/34e6b9a0dae125d085c84593140180ed.png)</span></span>

7. <span data-ttu-id="f4c25-172">A sincronização será concluída em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="f4c25-172">The sync will complete in a few minutes.</span></span>

    ![Imagem do aplicativo Android](images/9fc07ffc150171f169dc6e57fe6f1c74.png)

8. <span data-ttu-id="f4c25-174">Selecione o **botão Atualizar** na tela aplicativos Android e o Microsoft Defender ATP deve estar visível na lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f4c25-174">Select the **Refresh** button in the Android apps screen and Microsoft Defender ATP should be visible in the apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4c25-175">![Imagem da lista de aplicativos Android](images/fa4ac18a6333335db3775630b8e6b353.png)</span><span class="sxs-lookup"><span data-stu-id="f4c25-175">![Image of list of Android apps](images/fa4ac18a6333335db3775630b8e6b353.png)</span></span>

9. <span data-ttu-id="f4c25-176">O Defender for Endpoint dá suporte a políticas de configuração de aplicativo para dispositivos gerenciados por meio do Intune.</span><span class="sxs-lookup"><span data-stu-id="f4c25-176">Defender for Endpoint supports App configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="f4c25-177">Esse recurso pode ser aproveitado para autograntar as permissões aplicáveis do Android, para que o usuário final não precise aceitar essas permissões.</span><span class="sxs-lookup"><span data-stu-id="f4c25-177">This capability can be leveraged to autogrant applicable Android permission(s), so the end user does not need to accept these permission(s).</span></span>

    1. <span data-ttu-id="f4c25-178">Na página **Aplicativos,** vá para Política > Políticas de configuração de **aplicativos > Adicionar > dispositivos gerenciados.**</span><span class="sxs-lookup"><span data-stu-id="f4c25-178">In the **Apps** page, go to **Policy > App configuration policies > Add > Managed devices**.</span></span>

       ![Imagem do Centro de administração do Microsoft Endpoint Manager android managed devices](images/android-mem.png)

    1. <span data-ttu-id="f4c25-180">Na página **Criar política de configuração do** aplicativo, insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="f4c25-180">In the **Create app configuration policy** page, enter the following details:</span></span>
    
        - <span data-ttu-id="f4c25-181">Nome: Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="f4c25-181">Name: Microsoft Defender ATP.</span></span>
        - <span data-ttu-id="f4c25-182">Escolha **Android Enterprise** como plataforma.</span><span class="sxs-lookup"><span data-stu-id="f4c25-182">Choose **Android Enterprise** as platform.</span></span>
        - <span data-ttu-id="f4c25-183">Escolha **Perfil de Trabalho apenas** como Tipo de Perfil.</span><span class="sxs-lookup"><span data-stu-id="f4c25-183">Choose **Work Profile only** as Profile Type.</span></span>
        - <span data-ttu-id="f4c25-184">Clique **em Selecionar Aplicativo,** escolha **Microsoft Defender ATP,** selecione **OK** e, em **seguida, Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-184">Click **Select App**, choose **Microsoft Defender ATP**, select **OK** and then **Next**.</span></span>
    
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="f4c25-185">![Imagem da página criar política de configuração de aplicativo](images/android-create-app.png)</span><span class="sxs-lookup"><span data-stu-id="f4c25-185">![Image of create app configuration policy page](images/android-create-app.png)</span></span>

    1. <span data-ttu-id="f4c25-186">Na página **Configurações,** vá para a seção Permissões clique em Adicionar para exibir a lista de permissões com suporte.</span><span class="sxs-lookup"><span data-stu-id="f4c25-186">In the **Settings** page, go to the Permissions section click on Add to view the list of supported permissions.</span></span> <span data-ttu-id="f4c25-187">Na seção Adicionar Permissões, selecione as seguintes permissões:</span><span class="sxs-lookup"><span data-stu-id="f4c25-187">In the Add Permissions section, select the following permissions:</span></span>

       - <span data-ttu-id="f4c25-188">Armazenamento externo (leitura)</span><span class="sxs-lookup"><span data-stu-id="f4c25-188">External storage (read)</span></span>
       - <span data-ttu-id="f4c25-189">Armazenamento externo (gravação)</span><span class="sxs-lookup"><span data-stu-id="f4c25-189">External storage (write)</span></span>

       <span data-ttu-id="f4c25-190">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-190">Then select **OK**.</span></span>

       > [!div class="mx-imgBorder"]
      > <span data-ttu-id="f4c25-191">![Imagem da política de configuração do aplicativo de criação do android](images/android-create-app-config.png)</span><span class="sxs-lookup"><span data-stu-id="f4c25-191">![Image of android create app configuration policy](images/android-create-app-config.png)</span></span>

    1. <span data-ttu-id="f4c25-192">Agora você deve ver as permissões listadas e agora você pode autograntar ambos escolhendo a autogrant no **drop-down** estado de permissão e, em seguida, selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-192">You should now see both the permissions listed and now you can autogrant both by choosing autogrant in the **Permission state** drop-down and then select **Next**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="f4c25-193">![Imagem da concessão automática do android criar política de configuração de aplicativo](images/android-auto-grant.png)</span><span class="sxs-lookup"><span data-stu-id="f4c25-193">![Image of android auto grant create app configuration policy](images/android-auto-grant.png)</span></span>

    1. <span data-ttu-id="f4c25-194">Na página **Atribuições,** selecione o grupo de usuários ao qual essa política de configuração de aplicativo seria atribuída.</span><span class="sxs-lookup"><span data-stu-id="f4c25-194">In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="f4c25-195">Clique **em Selecionar grupos para incluir** e selecionar o grupo aplicável e, em seguida, selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-195">Click **Select groups to include** and selecting the applicable group and then selecting **Next**.</span></span>  <span data-ttu-id="f4c25-196">O grupo selecionado aqui geralmente é o mesmo grupo ao qual você atribuiria o Microsoft Defender para o aplicativo Do ponto de extremidade android.</span><span class="sxs-lookup"><span data-stu-id="f4c25-196">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="f4c25-197">![Imagem da política de configuração do aplicativo criar](images/android-select-group.png)</span><span class="sxs-lookup"><span data-stu-id="f4c25-197">![Image of the create app configuration policy](images/android-select-group.png)</span></span>
    

     1. <span data-ttu-id="f4c25-198">Na página **Revisar + Criar** que aparece em seguida, revise todas as informações e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-198">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <br>
    
        <span data-ttu-id="f4c25-199">A política de configuração do aplicativo para o Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.</span><span class="sxs-lookup"><span data-stu-id="f4c25-199">The app configuration policy for Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.</span></span>

        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="f4c25-200">![Imagem da revisão do android criar política de configuração de aplicativo](images/android-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="f4c25-200">![Image of android review create app config policy](images/android-review-create.png)</span></span>


10. <span data-ttu-id="f4c25-201">Selecione **o aplicativo Microsoft Defender ATP** na lista \> **Propriedades** \> **Atribuições** \> **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-201">Select **Microsoft Defender ATP** app in the list \> **Properties** \> **Assignments** \> **Edit**.</span></span>

    ![Imagem da lista de aplicativos](images/mda-properties.png)


11. <span data-ttu-id="f4c25-203">Atribua o aplicativo como *um aplicativo obrigatório* a um grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="f4c25-203">Assign the app as a *Required* app to a user group.</span></span> <span data-ttu-id="f4c25-204">Ele é instalado automaticamente no perfil *de trabalho* durante a próxima sincronização do dispositivo por meio do aplicativo Portal da Empresa.</span><span class="sxs-lookup"><span data-stu-id="f4c25-204">It is automatically installed in the *work profile* during the next sync of the device via Company Portal app.</span></span> <span data-ttu-id="f4c25-205">Essa atribuição pode ser feita navegando até a seção Obrigatório Adicionar  \> **grupo,** selecionando o grupo de usuários e clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-205">This assignment can be done by navigating to the *Required* section \> **Add group,** selecting the user group and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4c25-206">![Imagem da página editar aplicativo](images/ea06643280075f16265a596fb9a96042.png)</span><span class="sxs-lookup"><span data-stu-id="f4c25-206">![Image of edit application page](images/ea06643280075f16265a596fb9a96042.png)</span></span>


12. <span data-ttu-id="f4c25-207">Na página **Editar Aplicativo,** revise todas as informações inseridas acima.</span><span class="sxs-lookup"><span data-stu-id="f4c25-207">In the **Edit Application** page, review all the information that was entered above.</span></span> <span data-ttu-id="f4c25-208">Em seguida, **selecione Revisar + Salvar** e **salvar** novamente para iniciar a atribuição.</span><span class="sxs-lookup"><span data-stu-id="f4c25-208">Then select **Review + Save** and then **Save** again to commence assignment.</span></span>

### <a name="auto-setup-of-always-on-vpn"></a><span data-ttu-id="f4c25-209">Configuração automática da VPN always-on</span><span class="sxs-lookup"><span data-stu-id="f4c25-209">Auto Setup of Always-on VPN</span></span> 
<span data-ttu-id="f4c25-210">O Defender for Endpoint oferece suporte a políticas de configuração de dispositivo para dispositivos gerenciados por meio do Intune.</span><span class="sxs-lookup"><span data-stu-id="f4c25-210">Defender for Endpoint supports Device configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="f4c25-211">Esse recurso pode ser aproveitado para a configuração automática da **VPN Always-on** em dispositivos inscritos no Android Enterprise, para que o usuário final não precise configurar o serviço VPN durante a integração.</span><span class="sxs-lookup"><span data-stu-id="f4c25-211">This capability can be leveraged to **Auto setup of Always-on VPN** on Android Enterprise enrolled devices, so the end user does not need to set up VPN service while onboarding.</span></span>
1.  <span data-ttu-id="f4c25-212">Em **Dispositivos**, selecione **Perfis** de Configuração Criar Plataforma de Perfil Android Enterprise Selecionar Restrições de dispositivo em uma das seguintes  >    >    >   opções, com  base no tipo de registro do dispositivo</span><span class="sxs-lookup"><span data-stu-id="f4c25-212">On **Devices**, select **Configuration Profiles** > **Create Profile** > **Platform** > **Android Enterprise** Select **Device restrictions** under one of the following, based on your device enrollment type</span></span> 
- <span data-ttu-id="f4c25-213">**Perfil de trabalho totalmente gerenciado, dedicado e Corporate-Owned trabalho**</span><span class="sxs-lookup"><span data-stu-id="f4c25-213">**Fully Managed, Dedicated, and Corporate-Owned Work Profile**</span></span>
- <span data-ttu-id="f4c25-214">**Perfil de Trabalho de propriedade pessoal**</span><span class="sxs-lookup"><span data-stu-id="f4c25-214">**Personally owned Work Profile**</span></span>

<span data-ttu-id="f4c25-215">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-215">Select **Create**.</span></span>
 
   > ![Imagem do perfil de configuração de dispositivos Criar](images/1autosetupofvpn.png)
    
2. <span data-ttu-id="f4c25-217">**Configurações** Forneça um **Nome e** uma **Descrição** para identificar exclusivamente o perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="f4c25-217">**Configuration Settings** Provide a **Name** and a **Description** to uniquely identify the configuration profile.</span></span> 

   > ![Imagem do perfil de configuração de dispositivos Nome e Descrição](images/2autosetupofvpn.png)
   
 3. <span data-ttu-id="f4c25-219">Selecione **Conectividade e** configure VPN:</span><span class="sxs-lookup"><span data-stu-id="f4c25-219">Select **Connectivity** and configure VPN:</span></span>
- <span data-ttu-id="f4c25-220">**Habilita a Instalação de VPN always-on** de um cliente VPN no perfil de trabalho para se conectar e reconectar automaticamente à VPN sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="f4c25-220">Enable **Always-on VPN** Setup a VPN client in the work profile to automatically connect and reconnect to the VPN whenever possible.</span></span> <span data-ttu-id="f4c25-221">Somente um cliente VPN pode ser configurado para VPN sempre on em um determinado dispositivo, portanto, certifique-se de não ter mais de uma política VPN sempre on implantada em um único dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f4c25-221">Only one VPN client can be configured for always-on VPN on a given device, so be sure to have no more than one always-on VPN policy deployed to a single device.</span></span> 
- <span data-ttu-id="f4c25-222">Selecione **Personalizado na** lista suspenso do cliente VPN A VPN personalizada nesse caso é o Defender for Endpoint VPN, que é usado para fornecer o recurso de Proteção da Web.</span><span class="sxs-lookup"><span data-stu-id="f4c25-222">Select **Custom** in VPN client dropdown list Custom VPN in this case is Defender for Endpoint VPN which is used to provide the Web Protection feature.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="f4c25-223">O aplicativo Microsoft Defender ATP deve ser instalado no dispositivo do usuário, para funcionar da configuração automática dessa VPN.</span><span class="sxs-lookup"><span data-stu-id="f4c25-223">Microsoft Defender ATP app must be installed on user’s device, in order to functioning of auto setup of this VPN.</span></span>

- <span data-ttu-id="f4c25-224">Insira **a ID do** pacote do aplicativo Microsoft Defender ATP na Google Play Store.</span><span class="sxs-lookup"><span data-stu-id="f4c25-224">Enter **Package ID** of the Microsoft Defender ATP app in Google Play store.</span></span> <span data-ttu-id="f4c25-225">Para a URL do aplicativo https://play.google.com/store/apps/details?id=com.microsoft.scmx Defender, a ID do pacote **é com.microsoft.scmx**</span><span class="sxs-lookup"><span data-stu-id="f4c25-225">For the Defender app URL https://play.google.com/store/apps/details?id=com.microsoft.scmx, Package ID is **com.microsoft.scmx**</span></span>  
- <span data-ttu-id="f4c25-226">**Modo de bloqueio** Não configurado (Padrão)</span><span class="sxs-lookup"><span data-stu-id="f4c25-226">**Lockdown mode** Not configured (Default)</span></span> 

     ![Imagem do perfil de configuração de dispositivos habilita a VPN always-on](images/3autosetupofvpn.png)
   
4. <span data-ttu-id="f4c25-228">**Atribuição** Na página  **Atribuições,** selecione o grupo de usuários ao qual essa política de configuração de aplicativo   seria atribuída.</span><span class="sxs-lookup"><span data-stu-id="f4c25-228">**Assignment** In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="f4c25-229">Clique **em Selecionar grupos** para incluir e selecionar o grupo aplicável e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-229">Click **Select groups** to include and selecting the applicable group and then click **Next**.</span></span> <span data-ttu-id="f4c25-230">O grupo selecionado aqui geralmente é o mesmo grupo ao qual você atribuiria o Microsoft Defender para o aplicativo Do ponto de extremidade android.</span><span class="sxs-lookup"><span data-stu-id="f4c25-230">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

     ![Imagem do perfil de configuração de dispositivos Atribuição](images/4autosetupofvpn.png)

5. <span data-ttu-id="f4c25-232">Na página **Revisar + Criar** que aparece em seguida, revise todas as informações e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-232">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <span data-ttu-id="f4c25-233">O perfil de configuração do dispositivo agora é atribuído ao grupo de usuários selecionado.</span><span class="sxs-lookup"><span data-stu-id="f4c25-233">The device configuration profile is now assigned to the selected user group.</span></span>    

    ![Imagem do perfil de configuração de dispositivos Revisão e Criação](images/5autosetupofvpn.png)

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="f4c25-235">Concluir a integração e verificar o status</span><span class="sxs-lookup"><span data-stu-id="f4c25-235">Complete onboarding and check status</span></span>

1. <span data-ttu-id="f4c25-236">Confirme o status de instalação do Microsoft Defender para Ponto de Extremidade para Android clicando no **Status de Instalação do Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-236">Confirm the installation status of Microsoft Defender for Endpoint for Android by clicking on the **Device Install Status**.</span></span> <span data-ttu-id="f4c25-237">Verifique se o dispositivo é exibido aqui.</span><span class="sxs-lookup"><span data-stu-id="f4c25-237">Verify that the device is displayed here.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f4c25-238">![Imagem do status de instalação do dispositivo](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span><span class="sxs-lookup"><span data-stu-id="f4c25-238">![Image of device installation status](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span></span>


2. <span data-ttu-id="f4c25-239">No dispositivo, você pode validar o status de integração indo para o perfil **de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-239">On the device, you can validate the onboarding status by going to the **work profile**.</span></span> <span data-ttu-id="f4c25-240">Confirme se o Defender para Ponto de Extremidade está disponível e se você está inscrito nos dispositivos de **propriedade pessoal com o perfil de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="f4c25-240">Confirm that Defender for Endpoint is available and that you are enrolled to the **Personally owned devices with work profile**.</span></span>  <span data-ttu-id="f4c25-241">Se você estiver inscrito em um dispositivo de usuário totalmente gerenciado de propriedade **corporativa,** você terá um único perfil no dispositivo onde poderá confirmar se o Defender para Ponto de Extremidade está disponível.</span><span class="sxs-lookup"><span data-stu-id="f4c25-241">If you are enrolled to a **Corporate-owned, fully managed user device**, you will have a single profile on the device where you can confirm that Defender for Endpoint is available.</span></span>

    ![Imagem do aplicativo no dispositivo móvel](images/c2e647fc8fa31c4f2349c76f2497bc0e.png)

3. <span data-ttu-id="f4c25-243">Quando o aplicativo estiver instalado, abra o aplicativo e aceite as permissões e, em seguida, sua integração deve ser bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="f4c25-243">When the app is installed, open the app and accept the permissions and then your onboarding should be successful.</span></span>

    ![Imagem do dispositivo móvel com o aplicativo Microsoft Defender para Ponto de Extremidade](images/mda-devicesafe.png)

4. <span data-ttu-id="f4c25-245">Neste estágio, o dispositivo é bem-sucedido no Defender para Ponto de Extremidade para Android.</span><span class="sxs-lookup"><span data-stu-id="f4c25-245">At this stage the device is successfully onboarded onto Defender for Endpoint for Android.</span></span> <span data-ttu-id="f4c25-246">Você pode verificar isso no Centro de Segurança do [Microsoft Defender](https://securitycenter.microsoft.com) navegando até a página **Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="f4c25-246">You can verify this on the [Microsoft Defender Security Center](https://securitycenter.microsoft.com) by navigating to the **Devices** page.</span></span>

    ![Imagem do portal do Microsoft Defender para Ponto de Extremidade](images/9fe378a1dce0f143005c3aa53d8c4f51.png)


## <a name="related-topics"></a><span data-ttu-id="f4c25-248">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f4c25-248">Related topics</span></span>
- [<span data-ttu-id="f4c25-249">Visão geral do Microsoft Defender para Ponto de Extremidade para Android</span><span class="sxs-lookup"><span data-stu-id="f4c25-249">Overview of Microsoft Defender for Endpoint for Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="f4c25-250">Configurar o Microsoft Defender para o Ponto de Extremidade para recursos android</span><span class="sxs-lookup"><span data-stu-id="f4c25-250">Configure Microsoft Defender for Endpoint for Android features</span></span>](android-configure.md)
