---
title: Validar configurações de proteção do aplicativo em dispositivos Android ou iOS
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Saiba como validar as configurações de proteção de aplicativo do Microsoft 365 Business Premium em seus dispositivos Android ou iOS.
ms.openlocfilehash: d25a23bc8eb56e05bd74f7bf4658ee9e18dc41f8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635715"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="41a3a-103">Validar configurações de proteção do aplicativo em dispositivos Android ou iOS</span><span class="sxs-lookup"><span data-stu-id="41a3a-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="41a3a-104">Siga as instruções nas seções a seguir para validar as configurações de proteção do aplicativo em dispositivos Android ou iOS.</span><span class="sxs-lookup"><span data-stu-id="41a3a-104">Follow the instructions in the following sections to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="android"></a><span data-ttu-id="41a3a-105">Android</span><span class="sxs-lookup"><span data-stu-id="41a3a-105">Android</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="41a3a-106">Verifique se as configurações de proteção do aplicativo estão funcionando em dispositivos de usuário</span><span class="sxs-lookup"><span data-stu-id="41a3a-106">Check that the app protection settings are working on user devices</span></span>

<span data-ttu-id="41a3a-107">Depois de [definir configurações de aplicativo para dispositivos Android](app-protection-settings-for-android-and-ios.md) para proteger aplicativos, você pode seguir estas etapas para validar o funcionamento das configurações escolhidas.</span><span class="sxs-lookup"><span data-stu-id="41a3a-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="41a3a-108">Primeiro, certifique-se de que a política se aplica ao aplicativo no qual você irá validá-lo.</span><span class="sxs-lookup"><span data-stu-id="41a3a-108">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="41a3a-109">No [centro de administração](https://portal.office.com)do Microsoft 365 Business Premium, vá para **política de edição**de **políticas** \> .</span><span class="sxs-lookup"><span data-stu-id="41a3a-109">In the Microsoft 365 Business Premium [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="41a3a-110">Escolha **política de aplicativo para Android** para as configurações que você criou na instalação ou outra política que você criou e verifique se ela é imposta para o Outlook, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="41a3a-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook, for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="41a3a-112">Validar Exigir um PIN ou uma impressão digital para acessar aplicativos do Office</span><span class="sxs-lookup"><span data-stu-id="41a3a-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="41a3a-113">No painel **Editar política**, escolha **Editar** ao lado de **Controle de acesso a documentos do Office**, expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e verifique se a opção **Exigir um PIN ou uma impressão digital para acessar os aplicativos do Office** está definida como **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="41a3a-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Certifique-se de que a solicitação exigir um PIN ou uma impressão digital para acessar os aplicativos do Office está definida como ativado.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="41a3a-115">No dispositivo Android do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business Premium do usuário.</span><span class="sxs-lookup"><span data-stu-id="41a3a-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="41a3a-116">Você também será solicitado a inserir um PIN ou usar uma impressão digital.</span><span class="sxs-lookup"><span data-stu-id="41a3a-116">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="41a3a-118">Validar Redefinir PIN após algumas tentativas fracassadas</span><span class="sxs-lookup"><span data-stu-id="41a3a-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="41a3a-119">No painel **Editar política** , escolha **Editar** ao lado de **controle de acesso a documentos do Office**, expanda **gerenciar como os usuários acessam arquivos do Office em dispositivos móveis**e certifique-se de que a **redefinição do Pin após o número de tentativas com falha** esteja definida como um número.</span><span class="sxs-lookup"><span data-stu-id="41a3a-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="41a3a-120">Por padrão, isso é 5.</span><span class="sxs-lookup"><span data-stu-id="41a3a-120">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="41a3a-121">No dispositivo Android do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business Premium do usuário.</span><span class="sxs-lookup"><span data-stu-id="41a3a-121">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="41a3a-122">Insira um PIN incorreto o número de vezes especificado pela política.</span><span class="sxs-lookup"><span data-stu-id="41a3a-122">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="41a3a-123">Você verá um aviso indicando que o **limite de tentativas de PIN foi atingido** para redefinir o PIN.</span><span class="sxs-lookup"><span data-stu-id="41a3a-123">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="41a3a-125">Pressione **Redefinir PIN**.</span><span class="sxs-lookup"><span data-stu-id="41a3a-125">Press **Reset PIN**.</span></span> <span data-ttu-id="41a3a-126">Você será solicitado a entrar com as credenciais do Microsoft 365 Business Premium do usuário e, em seguida, precisa definir um novo PIN.</span><span class="sxs-lookup"><span data-stu-id="41a3a-126">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="41a3a-127">Validar Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="41a3a-127">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="41a3a-128">No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="41a3a-128">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="41a3a-130">No dispositivo Android do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business Premium do usuário e insira um PIN, se solicitado.</span><span class="sxs-lookup"><span data-stu-id="41a3a-130">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="41a3a-131">Abra um email que contenha um anexo e toque no ícone de seta para baixo ao lado das informações do anexo.</span><span class="sxs-lookup"><span data-stu-id="41a3a-131">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="41a3a-133">Você verá **não é possível salvar no dispositivo** na parte inferior da tela.</span><span class="sxs-lookup"><span data-stu-id="41a3a-133">You'll see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="41a3a-135">A opção para salvar no OneDrive for Business não está habilitada para o Android neste momento, portanto, só é possível ver que salvar localmente está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="41a3a-135">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="41a3a-136">Validar Solicitar que o usuário entre novamente se os aplicativos do Office ficarem ociosos por um período especificado</span><span class="sxs-lookup"><span data-stu-id="41a3a-136">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="41a3a-137">No painel **Editar política** , escolha **Editar** ao lado de **controle de acesso a documentos do Office**, expanda **gerenciar como os usuários acessam arquivos do Office em dispositivos móveis**e certifique-se de que **exijam que os usuários entrem novamente depois que os aplicativos do Office ficarem ociosos por** estão definidos como alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="41a3a-137">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="41a3a-138">Por padrão, isso é 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="41a3a-138">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="41a3a-139">No dispositivo Android do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business Premium do usuário e insira um PIN, se solicitado.</span><span class="sxs-lookup"><span data-stu-id="41a3a-139">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="41a3a-p105">Agora você deverá ver a caixa de entrada do Outlook. Deixe o dispositivo Android ocioso sem tocar nele por pelo menos 30 minutos (ou por um período diferente superior ao especificado na política). O dispositivo provavelmente ficará escuro.</span><span class="sxs-lookup"><span data-stu-id="41a3a-p105">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="41a3a-143">Acesse o Outlook no dispositivo Android novamente.</span><span class="sxs-lookup"><span data-stu-id="41a3a-143">Access Outlook on the Android device again.</span></span>
    
4. <span data-ttu-id="41a3a-144">Você será solicitado a inserir seu PIN antes de poder acessar o Outlook novamente.</span><span class="sxs-lookup"><span data-stu-id="41a3a-144">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="41a3a-145">Validar Proteger arquivos de trabalho com criptografia</span><span class="sxs-lookup"><span data-stu-id="41a3a-145">Validate Protect work files with encryption</span></span>

<span data-ttu-id="41a3a-146">No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Proteger arquivos de trabalho com criptografia** está definida como **Ativada** e a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Desativada**.</span><span class="sxs-lookup"><span data-stu-id="41a3a-146">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="41a3a-147">No dispositivo Android do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business Premium do usuário e insira um PIN, se solicitado.</span><span class="sxs-lookup"><span data-stu-id="41a3a-147">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="41a3a-148">Abra um email que contenha alguns anexos de arquivo de imagem.</span><span class="sxs-lookup"><span data-stu-id="41a3a-148">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="41a3a-149">Toque no ícone de seta para baixo ao lado das informações do anexo para salvá-lo.</span><span class="sxs-lookup"><span data-stu-id="41a3a-149">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="41a3a-p106">Você poderá ser solicitado a permitir que o Outlook acesse arquivos, mídia e fotos em seu dispositivo. Toque em **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="41a3a-p106">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="41a3a-153">Na parte inferior da tela, escolha **Salvar no Dispositivo** e, em seguida, abra o aplicativo **Galeria**.</span><span class="sxs-lookup"><span data-stu-id="41a3a-153">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="41a3a-p107">Você deverá ver uma foto criptografada (ou mais, caso tenha salvado vários anexos de arquivos de imagem) na lista. Ela poderá aparecer na lista Imagens como um quadrado cinza com um ponto de exclamação branco dentro de um círculo branco no centro do quadrado cinza.</span><span class="sxs-lookup"><span data-stu-id="41a3a-p107">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a><span data-ttu-id="41a3a-157">iOS</span><span class="sxs-lookup"><span data-stu-id="41a3a-157">iOS</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="41a3a-158">Verifique se as configurações de proteção do aplicativo estão funcionando nos dispositivos de usuário</span><span class="sxs-lookup"><span data-stu-id="41a3a-158">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="41a3a-159">Depois de [definir configurações de aplicativo para dispositivos iOS](app-protection-settings-for-android-and-ios.md) para proteger aplicativos, você pode seguir estas etapas para validar o funcionamento das configurações escolhidas.</span><span class="sxs-lookup"><span data-stu-id="41a3a-159">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="41a3a-160">Primeiro, certifique-se de que a política se aplica ao aplicativo no qual você irá validá-lo.</span><span class="sxs-lookup"><span data-stu-id="41a3a-160">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="41a3a-161">No [centro de administração](https://portal.office.com)do Microsoft 365 Business Premium, vá para **política de edição**de **políticas** \> .</span><span class="sxs-lookup"><span data-stu-id="41a3a-161">In the Microsoft 365 Business Premium [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="41a3a-162">Escolha **política de aplicativo para IOS** para as configurações que você criou na instalação ou outra política que você criou e verifique se ela é imposta para o Outlook por exemplo.</span><span class="sxs-lookup"><span data-stu-id="41a3a-162">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="41a3a-164">Validar Exigir um PIN para acessar aplicativos do Office</span><span class="sxs-lookup"><span data-stu-id="41a3a-164">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="41a3a-165">No painel **Editar política**, escolha **Editar** ao lado de **Controle de acesso a documentos do Office**, expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e verifique se a opção **Exigir um PIN ou uma impressão digital para acessar os aplicativos do Office** está definida como **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="41a3a-165">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Certifique-se de que a solicitação exigir um PIN ou uma impressão digital para acessar os aplicativos do Office está definida como ativado.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="41a3a-167">No dispositivo iOS do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business Premium do usuário.</span><span class="sxs-lookup"><span data-stu-id="41a3a-167">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="41a3a-168">Você também será solicitado a inserir um PIN ou usar uma impressão digital.</span><span class="sxs-lookup"><span data-stu-id="41a3a-168">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="41a3a-170">Validar Redefinir PIN após algumas tentativas fracassadas</span><span class="sxs-lookup"><span data-stu-id="41a3a-170">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="41a3a-171">No painel **Editar política** , escolha **Editar** ao lado de **controle de acesso a documentos do Office**, expanda **gerenciar como os usuários acessam arquivos do Office em dispositivos móveis**e certifique-se de que a **redefinição do Pin após o número de tentativas com falha** esteja definida como um número.</span><span class="sxs-lookup"><span data-stu-id="41a3a-171">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="41a3a-172">Por padrão, isso é 5.</span><span class="sxs-lookup"><span data-stu-id="41a3a-172">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="41a3a-173">No dispositivo iOS do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business Premium do usuário.</span><span class="sxs-lookup"><span data-stu-id="41a3a-173">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="41a3a-174">Insira um PIN incorreto o número de vezes especificado pela política.</span><span class="sxs-lookup"><span data-stu-id="41a3a-174">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="41a3a-175">Você verá um aviso indicando que o **limite de tentativas de PIN foi atingido** para redefinir o PIN.</span><span class="sxs-lookup"><span data-stu-id="41a3a-175">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="41a3a-177">Pressione **OK**.</span><span class="sxs-lookup"><span data-stu-id="41a3a-177">Press **OK**.</span></span> <span data-ttu-id="41a3a-178">Você será solicitado a entrar com as credenciais do Microsoft 365 Business Premium do usuário e, em seguida, precisa definir um novo PIN.</span><span class="sxs-lookup"><span data-stu-id="41a3a-178">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="41a3a-179">Validar Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="41a3a-179">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="41a3a-180">No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="41a3a-180">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="41a3a-182">No dispositivo iOS do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business Premium do usuário e insira um PIN, se solicitado.</span><span class="sxs-lookup"><span data-stu-id="41a3a-182">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="41a3a-183">Abra um email que contenha um anexo, abra o anexo e escolha **Salvar** na parte inferior da tela.</span><span class="sxs-lookup"><span data-stu-id="41a3a-183">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="41a3a-185">Você só verá uma opção para o OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="41a3a-185">You should only see an option for OneDrive for Business.</span></span> <span data-ttu-id="41a3a-186">Caso contrário, toque em **adicionar conta** e selecione **onedrive for Business** na tela **adicionar conta de armazenamento** .</span><span class="sxs-lookup"><span data-stu-id="41a3a-186">If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen.</span></span> <span data-ttu-id="41a3a-187">Forneça ao usuário final o Microsoft 365 Business Premium para entrar quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="41a3a-187">Provide the end user's Microsoft 365 Business Premium to sign in when prompted.</span></span> 
    
    <span data-ttu-id="41a3a-188">Toque em **Salvar** e selecione **OneDrive for Business**.</span><span class="sxs-lookup"><span data-stu-id="41a3a-188">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="41a3a-189">Validar Solicitar que o usuário entre novamente se os aplicativos do Office ficarem ociosos por um período especificado</span><span class="sxs-lookup"><span data-stu-id="41a3a-189">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="41a3a-190">No painel **Editar política** , escolha **Editar** ao lado de **controle de acesso a documentos do Office**, expanda **gerenciar como os usuários acessam arquivos do Office em dispositivos móveis**e certifique-se de que **exijam que os usuários entrem novamente depois que os aplicativos do Office ficarem ociosos por** estão definidos como alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="41a3a-190">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="41a3a-191">Por padrão, isso é 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="41a3a-191">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="41a3a-192">No dispositivo iOS do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business Premium do usuário e insira um PIN, se solicitado.</span><span class="sxs-lookup"><span data-stu-id="41a3a-192">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="41a3a-p113">Agora você deverá ver a caixa de entrada do Outlook. Deixe o dispositivo iOS sem tocar nele por pelo menos 30 minutos (ou por um período diferente superior ao especificado na política). O dispositivo provavelmente ficará escuro.</span><span class="sxs-lookup"><span data-stu-id="41a3a-p113">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="41a3a-196">Acessar o Outlook no dispositivo iOS novamente.</span><span class="sxs-lookup"><span data-stu-id="41a3a-196">Access Outlook on the iOS device again.</span></span>
    
4. <span data-ttu-id="41a3a-197">Você será solicitado a inserir seu PIN antes de poder acessar o Outlook novamente.</span><span class="sxs-lookup"><span data-stu-id="41a3a-197">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="41a3a-198">Validar Proteger arquivos de trabalho com criptografia</span><span class="sxs-lookup"><span data-stu-id="41a3a-198">Validate Protect work files with encryption</span></span>

<span data-ttu-id="41a3a-199">No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Proteger arquivos de trabalho com criptografia** está definida como **Ativada** e a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Desativada**.</span><span class="sxs-lookup"><span data-stu-id="41a3a-199">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="41a3a-200">No dispositivo iOS do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business Premium do usuário e insira um PIN, se solicitado.</span><span class="sxs-lookup"><span data-stu-id="41a3a-200">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="41a3a-201">Abra um email que contenha alguns anexos de arquivo de imagem.</span><span class="sxs-lookup"><span data-stu-id="41a3a-201">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="41a3a-202">Toque no anexo e, em seguida, toque na opção **Salvar** abaixo dele.</span><span class="sxs-lookup"><span data-stu-id="41a3a-202">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="41a3a-p114">Abra o aplicativo **Fotos** na tela inicial. Você deverá ver uma foto criptografada (ou mais, caso tenha salvado vários anexos de arquivos de imagem) salva, mas criptografada.</span><span class="sxs-lookup"><span data-stu-id="41a3a-p114">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

