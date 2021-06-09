---
title: Implantar o Microsoft Defender para Ponto de Extremidade para Android com o Microsoft Intune
description: Descreve como implantar o Microsoft Defender para Ponto de Extremidade no Android com Microsoft Intune
keywords: microsoft, defender, Microsoft Defender for Endpoint, mde, android, installation, deploy, uninstallation,
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1935533ad924b7589bdfee6f3119fb667fb60b73
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841505"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-android-with-microsoft-intune"></a><span data-ttu-id="b9996-104">Implantar o Microsoft Defender para Ponto de Extremidade para Android com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b9996-104">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b9996-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="b9996-105">**Applies to:**</span></span>
- [<span data-ttu-id="b9996-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="b9996-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b9996-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b9996-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b9996-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="b9996-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b9996-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="b9996-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="b9996-110">Saiba como implantar o Defender para Ponto de Extremidade no Android Portal da Empresa do Intune dispositivos inscritos.</span><span class="sxs-lookup"><span data-stu-id="b9996-110">Learn how to deploy Defender for Endpoint on Android on Intune Company Portal enrolled devices.</span></span> <span data-ttu-id="b9996-111">Para obter mais informações sobre o registro do dispositivo Intune, consulte  [Registrar seu dispositivo](/mem/intune/user-help/enroll-device-android-company-portal).</span><span class="sxs-lookup"><span data-stu-id="b9996-111">For more information about Intune device enrollment, see  [Enroll your device](/mem/intune/user-help/enroll-device-android-company-portal).</span></span>

> [!NOTE]
> <span data-ttu-id="b9996-112">**O Defender para Ponto de Extremidade no Android agora está disponível no [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span><span class="sxs-lookup"><span data-stu-id="b9996-112">**Defender for Endpoint on Android is now available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx)**</span></span> <br>
> <span data-ttu-id="b9996-113">Você pode se conectar ao Google Play do Intune para implantar o aplicativo Defender para Ponto de Extremidade no Administrador de Dispositivos e Enterprise de entrolamento.</span><span class="sxs-lookup"><span data-stu-id="b9996-113">You can connect to Google Play from Intune to deploy Defender for Endpoint app across Device Administrator and Android Enterprise entrollment modes.</span></span>
<span data-ttu-id="b9996-114">As atualizações para o aplicativo são automáticas por meio do Google Play.</span><span class="sxs-lookup"><span data-stu-id="b9996-114">Updates to the app are automatic via Google Play.</span></span>

## <a name="deploy-on-device-administrator-enrolled-devices"></a><span data-ttu-id="b9996-115">Implantar em dispositivos inscritos pelo Administrador de Dispositivos</span><span class="sxs-lookup"><span data-stu-id="b9996-115">Deploy on Device Administrator enrolled devices</span></span>

<span data-ttu-id="b9996-116">**Implantar o Defender para Ponto de Extremidade no Android Portal da Empresa do Intune - Dispositivos inscritos pelo Administrador de Dispositivos**</span><span class="sxs-lookup"><span data-stu-id="b9996-116">**Deploy Defender for Endpoint on Android on Intune Company Portal - Device Administrator enrolled devices**</span></span>

<span data-ttu-id="b9996-117">Saiba como implantar o Defender para Ponto de Extremidade no Android Portal da Empresa do Intune - Dispositivos inscritos pelo Administrador de Dispositivos.</span><span class="sxs-lookup"><span data-stu-id="b9996-117">Learn how to deploy Defender for Endpoint on Android on Intune Company Portal - Device Administrator enrolled devices.</span></span> 

### <a name="add-as-android-store-app"></a><span data-ttu-id="b9996-118">Adicionar como aplicativo da Loja do Android</span><span class="sxs-lookup"><span data-stu-id="b9996-118">Add as Android store app</span></span>

1. <span data-ttu-id="b9996-119">No [Microsoft Endpoint Manager de administração,](https://go.microsoft.com/fwlink/?linkid=2109431) acesse **Aplicativos** Android Apps Adicionar aplicativo da Loja \>  \> **\> do Android** e escolha **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="b9996-119">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add \> Android store app** and choose **Select**.</span></span>

   ![Imagem do Microsoft Endpoint Manager Admin Center adicionar aplicativo da Loja do Android](images/mda-addandroidstoreapp.png)

2. <span data-ttu-id="b9996-121">Na página **Adicionar aplicativo** e na seção Informações *do* Aplicativo, insira:</span><span class="sxs-lookup"><span data-stu-id="b9996-121">On the **Add app** page and in the *App Information* section enter:</span></span> 

   - <span data-ttu-id="b9996-122">**Nome**</span><span class="sxs-lookup"><span data-stu-id="b9996-122">**Name**</span></span> 
   - <span data-ttu-id="b9996-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b9996-123">**Description**</span></span>
   - <span data-ttu-id="b9996-124">**Publisher** como Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b9996-124">**Publisher** as Microsoft.</span></span>
   - <span data-ttu-id="b9996-125">**URL da Loja de Aplicativos** https://play.google.com/store/apps/details?id=com.microsoft.scmx como (URL do Defender for Endpoint App Google Play Store)</span><span class="sxs-lookup"><span data-stu-id="b9996-125">**App store URL** as https://play.google.com/store/apps/details?id=com.microsoft.scmx (Defender for Endpoint app Google Play Store URL)</span></span> 

   <span data-ttu-id="b9996-126">Outros campos são opcionais.</span><span class="sxs-lookup"><span data-stu-id="b9996-126">Other fields are optional.</span></span> <span data-ttu-id="b9996-127">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b9996-127">Select **Next**.</span></span>

   ![Imagem do Microsoft Endpoint Manager Admin Center adicionar informações do aplicativo](images/mda-addappinfo.png)

3. <span data-ttu-id="b9996-129">Na seção *Atribuições,* vá para a seção **Obrigatório** e selecione **Adicionar grupo.**</span><span class="sxs-lookup"><span data-stu-id="b9996-129">In the *Assignments* section, go to the **Required** section and select **Add group.**</span></span> <span data-ttu-id="b9996-130">Em seguida, você pode escolher os grupos de usuários que você gostaria de direcionar o Defender para Ponto de Extremidade no aplicativo Android.</span><span class="sxs-lookup"><span data-stu-id="b9996-130">You can then choose the user group(s) that you would like to target Defender for Endpoint on Android app.</span></span> <span data-ttu-id="b9996-131">Escolha **Selecionar** e, em **seguida, Próximo**.</span><span class="sxs-lookup"><span data-stu-id="b9996-131">Choose **Select** and then **Next**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="b9996-132">O grupo de usuários selecionado deve consistir em usuários inscritos do Intune.</span><span class="sxs-lookup"><span data-stu-id="b9996-132">The selected user group should consist of Intune enrolled users.</span></span>

    > [!div class="mx-imgBorder"]

    > ![Imagem dos grupos de usuários selecionados Microsoft Endpoint Manager Centro de Administração](images/363bf30f7d69a94db578e8af0ddd044b.png)

4. <span data-ttu-id="b9996-134">Na seção **Review+Create,** verifique se todas as informações inseridas estão corretas e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="b9996-134">In the **Review+Create** section, verify that all the information entered is correct and then select **Create**.</span></span>

    <span data-ttu-id="b9996-135">Em alguns instantes, o aplicativo Defender para Ponto de Extremidade seria criado com êxito, e uma notificação apareceria no canto superior direito da página.</span><span class="sxs-lookup"><span data-stu-id="b9996-135">In a few moments, the Defender for Endpoint app would be created successfully, and a notification would show up at the top-right corner of the page.</span></span>

    ![Imagem da Microsoft Endpoint Manager do Centro de Administração do aplicativo de ponto de extremidade do defender](images/86cbe56f88bb6e93e9c63303397fc24f.png)

5. <span data-ttu-id="b9996-137">Na página informações do aplicativo exibida, na seção **Monitor,** selecione **Status** de instalação do dispositivo para verificar se a instalação do dispositivo foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="b9996-137">In the app information page that is displayed, in the **Monitor** section, select **Device install status** to verify that the device installation has completed successfully.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9996-138">![Imagem da instalação Microsoft Endpoint Manager do Centro de Administração](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span><span class="sxs-lookup"><span data-stu-id="b9996-138">![Image of Microsoft Endpoint Manager Admin Center device install](images/513cf5d59eaaef5d2b5bc122715b5844.png)</span></span>

### <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="b9996-139">Concluir a integração e verificar o status</span><span class="sxs-lookup"><span data-stu-id="b9996-139">Complete onboarding and check status</span></span>

1. <span data-ttu-id="b9996-140">Depois que o Defender for Endpoint no Android tiver sido instalado no dispositivo, você verá o ícone do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b9996-140">Once Defender for Endpoint on Android has been installed on the device, you'll see the app icon.</span></span>

    ![Ícone em dispositivo móvel](images/7cf9311ad676ec5142002a4d0c2323ca.jpg)

2. <span data-ttu-id="b9996-142">Toque no ícone de aplicativo do Microsoft Defender para Ponto de Extremidade e siga as instruções na tela para concluir a integração do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b9996-142">Tap the Microsoft Defender for Endpoint app icon and follow the on-screen instructions to complete onboarding the app.</span></span> <span data-ttu-id="b9996-143">Os detalhes incluem a aceitação do usuário final das permissões do Android exigidas pelo Defender para Ponto de Extremidade no Android.</span><span class="sxs-lookup"><span data-stu-id="b9996-143">The details include end-user acceptance of Android permissions required by Defender for Endpoint on Android.</span></span>

3. <span data-ttu-id="b9996-144">Após a integração bem-sucedida, o dispositivo começará a aparecer na lista Dispositivos Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b9996-144">Upon successful onboarding, the device will start showing up on the Devices list in Microsoft Defender Security Center.</span></span>

    ![Imagem do dispositivo no portal do Defender para Ponto de Extremidade](images/9fe378a1dce0f143005c3aa53d8c4f51.png)

## <a name="deploy-on-android-enterprise-enrolled-devices"></a><span data-ttu-id="b9996-146">Implantar em dispositivos Enterprise Android inscritos</span><span class="sxs-lookup"><span data-stu-id="b9996-146">Deploy on Android Enterprise enrolled devices</span></span>

<span data-ttu-id="b9996-147">O Defender para Ponto de Extremidade no Android dá suporte Enterprise dispositivos inscritos.</span><span class="sxs-lookup"><span data-stu-id="b9996-147">Defender for Endpoint on Android supports Android Enterprise enrolled devices.</span></span>

<span data-ttu-id="b9996-148">Para obter mais informações sobre as opções de registro com suporte do Intune, consulte [Opções de Inscrição](/mem/intune/enrollment/android-enroll).</span><span class="sxs-lookup"><span data-stu-id="b9996-148">For more information on the enrollment options supported by Intune, see [Enrollment Options](/mem/intune/enrollment/android-enroll).</span></span>

<span data-ttu-id="b9996-149">**Atualmente, dispositivos de propriedade pessoal com perfil de trabalho e registro de dispositivos de usuário totalmente gerenciados de propriedade corporativa são suportados para implantação.**</span><span class="sxs-lookup"><span data-stu-id="b9996-149">**Currently, Personally owned devices with work profile and Corporate-owned fully managed user device enrollments are supported for deployment.**</span></span>

## <a name="add-microsoft-defender-for-endpoint-on-android-as-a-managed-google-play-app"></a><span data-ttu-id="b9996-150">Adicionar o Microsoft Defender para Ponto de Extremidade no Android como um aplicativo gerenciado do Google Play</span><span class="sxs-lookup"><span data-stu-id="b9996-150">Add Microsoft Defender for Endpoint on Android as a Managed Google Play app</span></span>

<span data-ttu-id="b9996-151">Siga as etapas a seguir para adicionar o aplicativo Microsoft Defender para Ponto de Extremidade ao Google Play gerenciado.</span><span class="sxs-lookup"><span data-stu-id="b9996-151">Follow the steps below to add Microsoft Defender for Endpoint app into your managed Google Play.</span></span>

1. <span data-ttu-id="b9996-152">No [Microsoft Endpoint Manager de administração,](https://go.microsoft.com/fwlink/?linkid=2109431) vá para  \> **Aplicativos Android Apps** Adicionar e \>  selecione Aplicativo Gerenciado do **Google Play**.</span><span class="sxs-lookup"><span data-stu-id="b9996-152">In [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431) , go to **Apps** \> **Android Apps** \> **Add** and select **Managed Google Play app**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9996-153">![Imagem do Microsoft Endpoint Manager admin center gerenciado google play](images/579ff59f31f599414cedf63051628b2e.png)</span><span class="sxs-lookup"><span data-stu-id="b9996-153">![Image of Microsoft Endpoint Manager admin center managed google play](images/579ff59f31f599414cedf63051628b2e.png)</span></span>

2. <span data-ttu-id="b9996-154">Na página gerenciada do Google Play que é carregada posteriormente, vá até a caixa de pesquisa e procure o **Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="b9996-154">On your managed Google Play page that loads subsequently, go to the search box and lookup **Microsoft Defender.**</span></span> <span data-ttu-id="b9996-155">Sua pesquisa deve exibir o aplicativo Microsoft Defender para Ponto de Extremidade em seu Google Play Gerenciado.</span><span class="sxs-lookup"><span data-stu-id="b9996-155">Your search should display the Microsoft Defender for Endpoint app in your Managed Google Play.</span></span> <span data-ttu-id="b9996-156">Clique no aplicativo Microsoft Defender para Ponto de Extremidade no resultado da pesquisa aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b9996-156">Click on the Microsoft Defender for Endpoint app from the Apps search result.</span></span>

    ![Imagem da pesquisa Microsoft Endpoint Manager de aplicativos do centro de administração](images/0f79cb37900b57c3e2bb0effad1c19cb.png)

3. <span data-ttu-id="b9996-158">Na página Descrição do aplicativo que vem a seguir, você deve ser capaz de ver detalhes do aplicativo no Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="b9996-158">In the App description page that comes up next, you should be able to see app details on Defender for Endpoint.</span></span> <span data-ttu-id="b9996-159">Revise as informações na página e selecione **Aprovar**.</span><span class="sxs-lookup"><span data-stu-id="b9996-159">Review the information on the page and then select **Approve**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9996-160">![Uma captura de tela de um Google Play Gerenciado](images/07e6d4119f265037e3b80a20a73b856f.png)</span><span class="sxs-lookup"><span data-stu-id="b9996-160">![A screenshot of a Managed Google Play](images/07e6d4119f265037e3b80a20a73b856f.png)</span></span>

4. <span data-ttu-id="b9996-161">Você será apresentado com as permissões que o Defender for Endpoint obtém para que ele funcione.</span><span class="sxs-lookup"><span data-stu-id="b9996-161">You'll be presented with the permissions that Defender for Endpoint obtains for it to work.</span></span> <span data-ttu-id="b9996-162">Revise-os e selecione **Aprovar**.</span><span class="sxs-lookup"><span data-stu-id="b9996-162">Review them and then select **Approve**.</span></span>

    ![Uma captura de tela da aprovação do aplicativo de visualização do Defender para Ponto de Extremidade](images/206b3d954f06cc58b3466fb7a0bd9f74.png)

5. <span data-ttu-id="b9996-164">Você será apresentado com a página Configurações de Aprovação.</span><span class="sxs-lookup"><span data-stu-id="b9996-164">You'll be presented with the Approval settings page.</span></span> <span data-ttu-id="b9996-165">A página confirma sua preferência para lidar com novas permissões de aplicativo que o Defender para Ponto de Extremidade pode solicitar no Android.</span><span class="sxs-lookup"><span data-stu-id="b9996-165">The page confirms your preference to handle new app permissions that Defender for Endpoint on Android might ask.</span></span> <span data-ttu-id="b9996-166">Revise as opções e selecione sua opção preferida.</span><span class="sxs-lookup"><span data-stu-id="b9996-166">Review the choices and select your preferred option.</span></span> <span data-ttu-id="b9996-167">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="b9996-167">Select **Done**.</span></span>

    <span data-ttu-id="b9996-168">Por padrão, o Google Play gerenciado seleciona *Manter aprovado quando o aplicativo solicita novas permissões*</span><span class="sxs-lookup"><span data-stu-id="b9996-168">By default, managed Google Play selects *Keep approved when app requests new permissions*</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9996-169">![Imagem da guia notificações](images/ffecfdda1c4df14148f1526c22cc0236.png)</span><span class="sxs-lookup"><span data-stu-id="b9996-169">![Image of notifications tab](images/ffecfdda1c4df14148f1526c22cc0236.png)</span></span>

6. <span data-ttu-id="b9996-170">Depois que a seleção de manipulação de permissões for feita, selecione **Sincronizar** para sincronizar o Microsoft Defender para o Ponto de Extremidade à sua lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b9996-170">After the permissions handling selection is made, select **Sync** to sync Microsoft Defender for Endpoint to your apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9996-171">![Imagem da página de sincronização](images/34e6b9a0dae125d085c84593140180ed.png)</span><span class="sxs-lookup"><span data-stu-id="b9996-171">![Image of sync page](images/34e6b9a0dae125d085c84593140180ed.png)</span></span>

7. <span data-ttu-id="b9996-172">A sincronização será concluída em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="b9996-172">The sync will complete in a few minutes.</span></span>

    ![Imagem do aplicativo Android](images/9fc07ffc150171f169dc6e57fe6f1c74.png)

8. <span data-ttu-id="b9996-174">Selecione o **botão Atualizar** na tela aplicativos Android e o Microsoft Defender para Ponto de Extremidade deve estar visível na lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="b9996-174">Select the **Refresh** button in the Android apps screen and Microsoft Defender for Endpoint should be visible in the apps list.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9996-175">![Imagem da lista de aplicativos Android](images/fa4ac18a6333335db3775630b8e6b353.png)</span><span class="sxs-lookup"><span data-stu-id="b9996-175">![Image of list of Android apps](images/fa4ac18a6333335db3775630b8e6b353.png)</span></span>

9. <span data-ttu-id="b9996-176">O Defender for Endpoint dá suporte a políticas de configuração de aplicativo para dispositivos gerenciados por meio do Intune.</span><span class="sxs-lookup"><span data-stu-id="b9996-176">Defender for Endpoint supports App configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="b9996-177">Esse recurso pode ser aproveitado para autograntar as permissões aplicáveis do Android, para que o usuário final não precise aceitar essas permissões.</span><span class="sxs-lookup"><span data-stu-id="b9996-177">This capability can be leveraged to autogrant applicable Android permission(s), so the end user does not need to accept these permission(s).</span></span>

    1. <span data-ttu-id="b9996-178">Na página **Aplicativos,** vá para Política > Políticas de configuração de **aplicativos > Adicionar > dispositivos gerenciados.**</span><span class="sxs-lookup"><span data-stu-id="b9996-178">In the **Apps** page, go to **Policy > App configuration policies > Add > Managed devices**.</span></span>

       ![Imagem do centro de administração Microsoft Endpoint Manager android dispositivos gerenciados](images/android-mem.png)

    1. <span data-ttu-id="b9996-180">Na página **Criar política de configuração do** aplicativo, insira os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="b9996-180">In the **Create app configuration policy** page, enter the following details:</span></span>
    
        - <span data-ttu-id="b9996-181">Nome: Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="b9996-181">Name: Microsoft Defender for Endpoint.</span></span>
        - <span data-ttu-id="b9996-182">Escolha **Android Enterprise** como plataforma.</span><span class="sxs-lookup"><span data-stu-id="b9996-182">Choose **Android Enterprise** as platform.</span></span>
        - <span data-ttu-id="b9996-183">Escolha **Perfil de Trabalho apenas** como Tipo de Perfil.</span><span class="sxs-lookup"><span data-stu-id="b9996-183">Choose **Work Profile only** as Profile Type.</span></span>
        - <span data-ttu-id="b9996-184">Clique **em Selecionar Aplicativo,** escolha **Microsoft Defender ATP,** selecione **OK** e, em **seguida, Próximo**.</span><span class="sxs-lookup"><span data-stu-id="b9996-184">Click **Select App**, choose **Microsoft Defender ATP**, select **OK** and then **Next**.</span></span>
    
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="b9996-185">![Imagem da página criar política de configuração de aplicativo](images/android-create-app.png)</span><span class="sxs-lookup"><span data-stu-id="b9996-185">![Image of create app configuration policy page](images/android-create-app.png)</span></span>

    1. <span data-ttu-id="b9996-186">Na página **Configurações,** vá para a seção Permissões clique em Adicionar para exibir a lista de permissões com suporte.</span><span class="sxs-lookup"><span data-stu-id="b9996-186">In the **Settings** page, go to the Permissions section click on Add to view the list of supported permissions.</span></span> <span data-ttu-id="b9996-187">Na seção Adicionar Permissões, selecione as seguintes permissões:</span><span class="sxs-lookup"><span data-stu-id="b9996-187">In the Add Permissions section, select the following permissions:</span></span>

       - <span data-ttu-id="b9996-188">Armazenamento externo (leitura)</span><span class="sxs-lookup"><span data-stu-id="b9996-188">External storage (read)</span></span>
       - <span data-ttu-id="b9996-189">Armazenamento externo (gravação)</span><span class="sxs-lookup"><span data-stu-id="b9996-189">External storage (write)</span></span>

       <span data-ttu-id="b9996-190">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b9996-190">Then select **OK**.</span></span>

       > [!div class="mx-imgBorder"]
      > <span data-ttu-id="b9996-191">![Imagem da política de configuração do aplicativo de criação do android](images/android-create-app-config.png)</span><span class="sxs-lookup"><span data-stu-id="b9996-191">![Image of android create app configuration policy](images/android-create-app-config.png)</span></span>

    1. <span data-ttu-id="b9996-192">Agora você deve ver as permissões listadas e agora você pode autograntar ambos escolhendo a autogrant no **drop-down** estado de permissão e, em seguida, selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="b9996-192">You should now see both the permissions listed and now you can autogrant both by choosing autogrant in the **Permission state** drop-down and then select **Next**.</span></span>

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="b9996-193">![Imagem da concessão automática do android criar política de configuração de aplicativo](images/android-auto-grant.png)</span><span class="sxs-lookup"><span data-stu-id="b9996-193">![Image of android auto grant create app configuration policy](images/android-auto-grant.png)</span></span>

    1. <span data-ttu-id="b9996-194">Na página **Atribuições,** selecione o grupo de usuários ao qual essa política de configuração de aplicativo seria atribuída.</span><span class="sxs-lookup"><span data-stu-id="b9996-194">In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="b9996-195">Clique **em Selecionar grupos para incluir** e selecionar o grupo aplicável e, em seguida, selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="b9996-195">Click **Select groups to include** and selecting the applicable group and then selecting **Next**.</span></span>  <span data-ttu-id="b9996-196">O grupo selecionado aqui geralmente é o mesmo grupo ao qual você atribuiria o Microsoft Defender para o aplicativo Do ponto de extremidade android.</span><span class="sxs-lookup"><span data-stu-id="b9996-196">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="b9996-197">![Imagem da política de configuração do aplicativo criar](images/android-select-group.png)</span><span class="sxs-lookup"><span data-stu-id="b9996-197">![Image of the create app configuration policy](images/android-select-group.png)</span></span>
    

     1. <span data-ttu-id="b9996-198">Na página **Revisar + Criar** que aparece em seguida, revise todas as informações e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="b9996-198">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <br>
    
        <span data-ttu-id="b9996-199">A política de configuração do aplicativo para o Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.</span><span class="sxs-lookup"><span data-stu-id="b9996-199">The app configuration policy for Defender for Endpoint autogranting the storage permission is now assigned to the selected user group.</span></span>

        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="b9996-200">![Imagem da revisão do android criar política de configuração de aplicativo](images/android-review-create.png)</span><span class="sxs-lookup"><span data-stu-id="b9996-200">![Image of android review create app config policy](images/android-review-create.png)</span></span>


10. <span data-ttu-id="b9996-201">Selecione **Microsoft Defender ATP** aplicativo na lista Propriedades \>  \> **Atribuições** \> **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b9996-201">Select **Microsoft Defender ATP** app in the list \> **Properties** \> **Assignments** \> **Edit**.</span></span>

    ![Imagem da lista de aplicativos](images/mda-properties.png)


11. <span data-ttu-id="b9996-203">Atribua o aplicativo como *um aplicativo obrigatório* a um grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="b9996-203">Assign the app as a *Required* app to a user group.</span></span> <span data-ttu-id="b9996-204">Ele é instalado automaticamente no perfil *de* trabalho durante a próxima sincronização do dispositivo por meio Portal da Empresa app.</span><span class="sxs-lookup"><span data-stu-id="b9996-204">It is automatically installed in the *work profile* during the next sync of the device via Company Portal app.</span></span> <span data-ttu-id="b9996-205">Essa atribuição pode ser feita navegando até a seção Obrigatório Adicionar  \> **grupo,** selecionando o grupo de usuários e clique em **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="b9996-205">This assignment can be done by navigating to the *Required* section \> **Add group,** selecting the user group and click **Select**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9996-206">![Imagem da página editar aplicativo](images/ea06643280075f16265a596fb9a96042.png)</span><span class="sxs-lookup"><span data-stu-id="b9996-206">![Image of edit application page](images/ea06643280075f16265a596fb9a96042.png)</span></span>


12. <span data-ttu-id="b9996-207">Na página **Editar Aplicativo,** revise todas as informações inseridas acima.</span><span class="sxs-lookup"><span data-stu-id="b9996-207">In the **Edit Application** page, review all the information that was entered above.</span></span> <span data-ttu-id="b9996-208">Em seguida, **selecione Revisar + Salvar** e **salvar** novamente para iniciar a atribuição.</span><span class="sxs-lookup"><span data-stu-id="b9996-208">Then select **Review + Save** and then **Save** again to commence assignment.</span></span>

### <a name="auto-setup-of-always-on-vpn"></a><span data-ttu-id="b9996-209">Configuração automática da VPN always-on</span><span class="sxs-lookup"><span data-stu-id="b9996-209">Auto Setup of Always-on VPN</span></span> 
<span data-ttu-id="b9996-210">O Defender for Endpoint oferece suporte a políticas de configuração de dispositivo para dispositivos gerenciados por meio do Intune.</span><span class="sxs-lookup"><span data-stu-id="b9996-210">Defender for Endpoint supports Device configuration policies for managed devices via Intune.</span></span> <span data-ttu-id="b9996-211">Esse recurso pode ser aproveitado para a configuração automática da **VPN Always-on** em dispositivos Enterprise Android, para que o usuário final não precise configurar o serviço VPN durante a integração.</span><span class="sxs-lookup"><span data-stu-id="b9996-211">This capability can be leveraged to **Auto setup of Always-on VPN** on Android Enterprise enrolled devices, so the end user does not need to set up VPN service while onboarding.</span></span>
1.  <span data-ttu-id="b9996-212">Em **Dispositivos**, selecione **Perfis** de Configuração Criar Plataforma de Perfil Android Enterprise selecionar restrições de dispositivo em uma das seguintes  >    >    >   opções, com  base no tipo de registro do dispositivo</span><span class="sxs-lookup"><span data-stu-id="b9996-212">On **Devices**, select **Configuration Profiles** > **Create Profile** > **Platform** > **Android Enterprise** Select **Device restrictions** under one of the following, based on your device enrollment type</span></span> 
- <span data-ttu-id="b9996-213">**Perfil de trabalho totalmente gerenciado, dedicado e Corporate-Owned trabalho**</span><span class="sxs-lookup"><span data-stu-id="b9996-213">**Fully Managed, Dedicated, and Corporate-Owned Work Profile**</span></span>
- <span data-ttu-id="b9996-214">**Perfil de Trabalho de propriedade pessoal**</span><span class="sxs-lookup"><span data-stu-id="b9996-214">**Personally owned Work Profile**</span></span>

<span data-ttu-id="b9996-215">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="b9996-215">Select **Create**.</span></span>
 
   > ![Imagem do perfil de configuração de dispositivos Criar](images/1autosetupofvpn.png)
    
2. <span data-ttu-id="b9996-217">**Configuração Configurações** Forneça um **Nome e** uma **Descrição** para identificar exclusivamente o perfil de configuração.</span><span class="sxs-lookup"><span data-stu-id="b9996-217">**Configuration Settings** Provide a **Name** and a **Description** to uniquely identify the configuration profile.</span></span> 

   > ![Imagem do perfil de configuração de dispositivos Nome e Descrição](images/2autosetupofvpn.png)
   
 3. <span data-ttu-id="b9996-219">Selecione **Conectividade e** configure VPN:</span><span class="sxs-lookup"><span data-stu-id="b9996-219">Select **Connectivity** and configure VPN:</span></span>
- <span data-ttu-id="b9996-220">**Habilita a Instalação de VPN always-on** de um cliente VPN no perfil de trabalho para se conectar e reconectar automaticamente à VPN sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="b9996-220">Enable **Always-on VPN** Setup a VPN client in the work profile to automatically connect and reconnect to the VPN whenever possible.</span></span> <span data-ttu-id="b9996-221">Somente um cliente VPN pode ser configurado para VPN sempre on em um determinado dispositivo, portanto, certifique-se de não ter mais de uma política VPN sempre on implantada em um único dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b9996-221">Only one VPN client can be configured for always-on VPN on a given device, so be sure to have no more than one always-on VPN policy deployed to a single device.</span></span> 
- <span data-ttu-id="b9996-222">Selecione **Personalizado na** lista suspenso do cliente VPN A VPN personalizada nesse caso é o Defender for Endpoint VPN, que é usado para fornecer o recurso de Proteção da Web.</span><span class="sxs-lookup"><span data-stu-id="b9996-222">Select **Custom** in VPN client dropdown list Custom VPN in this case is Defender for Endpoint VPN which is used to provide the Web Protection feature.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="b9996-223">O aplicativo do Microsoft Defender para Ponto de Extremidade deve ser instalado no dispositivo do usuário, para funcionar da configuração automática dessa VPN.</span><span class="sxs-lookup"><span data-stu-id="b9996-223">Microsoft Defender for Endpoint app must be installed on user’s device, in order to functioning of auto setup of this VPN.</span></span>

- <span data-ttu-id="b9996-224">Insira **a ID do** pacote do aplicativo Microsoft Defender para Ponto de Extremidade na Google Play Store.</span><span class="sxs-lookup"><span data-stu-id="b9996-224">Enter **Package ID** of the Microsoft Defender for Endpoint app in Google Play store.</span></span> <span data-ttu-id="b9996-225">Para a URL do aplicativo https://play.google.com/store/apps/details?id=com.microsoft.scmx Defender, a ID do pacote **é com.microsoft.scmx**</span><span class="sxs-lookup"><span data-stu-id="b9996-225">For the Defender app URL https://play.google.com/store/apps/details?id=com.microsoft.scmx, Package ID is **com.microsoft.scmx**</span></span>  
- <span data-ttu-id="b9996-226">**Modo de bloqueio** Não configurado (Padrão)</span><span class="sxs-lookup"><span data-stu-id="b9996-226">**Lockdown mode** Not configured (Default)</span></span> 

     ![Imagem do perfil de configuração de dispositivos habilita a VPN always-on](images/3autosetupofvpn.png)
   
4. <span data-ttu-id="b9996-228">**Atribuição** Na página  **Atribuições,** selecione o grupo de usuários ao qual essa política de configuração de aplicativo   seria atribuída.</span><span class="sxs-lookup"><span data-stu-id="b9996-228">**Assignment** In the **Assignments** page, select the user group to which this app config policy would be assigned to.</span></span> <span data-ttu-id="b9996-229">Clique **em Selecionar grupos** para incluir e selecionar o grupo aplicável e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="b9996-229">Click **Select groups** to include and selecting the applicable group and then click **Next**.</span></span> <span data-ttu-id="b9996-230">O grupo selecionado aqui geralmente é o mesmo grupo ao qual você atribuiria o Microsoft Defender para o aplicativo Do ponto de extremidade android.</span><span class="sxs-lookup"><span data-stu-id="b9996-230">The group selected here is usually the same group to which you would assign Microsoft Defender for Endpoint Android app.</span></span> 

     ![Imagem do perfil de configuração de dispositivos Atribuição](images/4autosetupofvpn.png)

5. <span data-ttu-id="b9996-232">Na página **Revisar + Criar** que aparece em seguida, revise todas as informações e selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="b9996-232">In the **Review + Create** page that comes up next, review all the information and then select **Create**.</span></span> <span data-ttu-id="b9996-233">O perfil de configuração do dispositivo agora é atribuído ao grupo de usuários selecionado.</span><span class="sxs-lookup"><span data-stu-id="b9996-233">The device configuration profile is now assigned to the selected user group.</span></span>    

    ![Imagem do perfil de configuração de dispositivos Revisão e Criação](images/5autosetupofvpn.png)

## <a name="complete-onboarding-and-check-status"></a><span data-ttu-id="b9996-235">Concluir a integração e verificar o status</span><span class="sxs-lookup"><span data-stu-id="b9996-235">Complete onboarding and check status</span></span>

1. <span data-ttu-id="b9996-236">Confirme o status de instalação do Microsoft Defender para Ponto de Extremidade no Android clicando no **Status de Instalação do Dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="b9996-236">Confirm the installation status of Microsoft Defender for Endpoint on Android by clicking on the **Device Install Status**.</span></span> <span data-ttu-id="b9996-237">Verifique se o dispositivo é exibido aqui.</span><span class="sxs-lookup"><span data-stu-id="b9996-237">Verify that the device is displayed here.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="b9996-238">![Imagem do status de instalação do dispositivo](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span><span class="sxs-lookup"><span data-stu-id="b9996-238">![Image of device installation status](images/900c0197aa59f9b7abd762ab2b32e80c.png)</span></span>


2. <span data-ttu-id="b9996-239">No dispositivo, você pode validar o status de integração indo para o perfil **de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b9996-239">On the device, you can validate the onboarding status by going to the **work profile**.</span></span> <span data-ttu-id="b9996-240">Confirme se o Defender para Ponto de Extremidade está disponível e se você está inscrito nos dispositivos de **propriedade pessoal com o perfil de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b9996-240">Confirm that Defender for Endpoint is available and that you are enrolled to the **Personally owned devices with work profile**.</span></span>  <span data-ttu-id="b9996-241">Se você estiver inscrito em um dispositivo de usuário totalmente gerenciado de propriedade **corporativa,** você terá um único perfil no dispositivo onde poderá confirmar se o Defender para Ponto de Extremidade está disponível.</span><span class="sxs-lookup"><span data-stu-id="b9996-241">If you are enrolled to a **Corporate-owned, fully managed user device**, you will have a single profile on the device where you can confirm that Defender for Endpoint is available.</span></span>

    ![Imagem do aplicativo no dispositivo móvel](images/c2e647fc8fa31c4f2349c76f2497bc0e.png)

3. <span data-ttu-id="b9996-243">Quando o aplicativo estiver instalado, abra o aplicativo e aceite as permissões e, em seguida, sua integração deve ser bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="b9996-243">When the app is installed, open the app and accept the permissions and then your onboarding should be successful.</span></span>

    ![Imagem do dispositivo móvel com o aplicativo Microsoft Defender para Ponto de Extremidade](images/mda-devicesafe.png)

4. <span data-ttu-id="b9996-245">Neste estágio, o dispositivo é bem-sucedido no Defender para Ponto de Extremidade no Android.</span><span class="sxs-lookup"><span data-stu-id="b9996-245">At this stage the device is successfully onboarded onto Defender for Endpoint on Android.</span></span> <span data-ttu-id="b9996-246">Você pode verificar isso no [Central de Segurança do Microsoft Defender](https://securitycenter.microsoft.com) navegando até a página **Dispositivos.**</span><span class="sxs-lookup"><span data-stu-id="b9996-246">You can verify this on the [Microsoft Defender Security Center](https://securitycenter.microsoft.com) by navigating to the **Devices** page.</span></span>

    ![Imagem do portal do Microsoft Defender para Ponto de Extremidade](images/9fe378a1dce0f143005c3aa53d8c4f51.png)


## <a name="related-topics"></a><span data-ttu-id="b9996-248">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b9996-248">Related topics</span></span>
- [<span data-ttu-id="b9996-249">Visão geral do Microsoft Defender para Ponto de Extremidade para Android</span><span class="sxs-lookup"><span data-stu-id="b9996-249">Overview of Microsoft Defender for Endpoint on Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="b9996-250">Configurar o Microsoft Defender para Ponto de Extremidade para recursos do Android</span><span class="sxs-lookup"><span data-stu-id="b9996-250">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)
