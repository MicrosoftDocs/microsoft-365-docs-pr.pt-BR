---
title: Validar configurações de proteção do aplicativo em dispositivos Android ou iOS
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
description: Learn how to validate the Microsoft 365 Business app protection settings in your Android or iOS devices.
ms.openlocfilehash: 309dbf5bdba81bbf8ad0a9707c136a03c4a28586
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575519"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="a3b05-103">Validar configurações de proteção do aplicativo em dispositivos Android ou iOS</span><span class="sxs-lookup"><span data-stu-id="a3b05-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="a3b05-104">Siga as instruções nas seções a seguir para validar as configurações de proteção do aplicativo em dispositivos Android ou iOS.</span><span class="sxs-lookup"><span data-stu-id="a3b05-104">Follow the instructions in the following sections to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="android"></a><span data-ttu-id="a3b05-105">Android</span><span class="sxs-lookup"><span data-stu-id="a3b05-105">Android</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="a3b05-106">Verifique se as configurações de proteção do aplicativo estão funcionando nos dispositivos de usuário</span><span class="sxs-lookup"><span data-stu-id="a3b05-106">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="a3b05-107">Depois de [definir configurações de aplicativo para dispositivos Android](app-protection-settings-for-android-and-ios.md) para proteger aplicativos, você pode seguir estas etapas para validar o funcionamento das configurações escolhidas.</span><span class="sxs-lookup"><span data-stu-id="a3b05-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="a3b05-108">Em primeiro lugar, certifique-se de que a política se aplica ao aplicativo no qual você a validará.</span><span class="sxs-lookup"><span data-stu-id="a3b05-108">First, make sure that the policy applies to the app in which you are going to validate it.</span></span>
  
1. <span data-ttu-id="a3b05-109">No [centro de administração](https://portal.office.com) do Microsoft 365 Business, acesse **Políticas** \> **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="a3b05-109">In the Microsoft 365 Business [admin center](https://portal.office.com) go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="a3b05-110">Escolha **Política de aplicativo para Android** para verificar as configurações que você criou na instalação ou outra política que você tenha criado e verifique se ela é aplicada, por exemplo, no Outlook.</span><span class="sxs-lookup"><span data-stu-id="a3b05-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it is enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="a3b05-112">Validar Exigir um PIN ou uma impressão digital para acessar aplicativos do Office</span><span class="sxs-lookup"><span data-stu-id="a3b05-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="a3b05-113">No painel **Editar política**, escolha **Editar** ao lado de **Controle de acesso a documentos do Office**, expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e verifique se a opção **Exigir um PIN ou uma impressão digital para acessar os aplicativos do Office** está definida como **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="a3b05-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="a3b05-115">No dispositivo Android do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário.</span><span class="sxs-lookup"><span data-stu-id="a3b05-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="a3b05-116">Você também deverá digitar um PIN ou usar uma impressão digital.</span><span class="sxs-lookup"><span data-stu-id="a3b05-116">You will also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="a3b05-118">Validar Redefinir PIN após algumas tentativas fracassadas</span><span class="sxs-lookup"><span data-stu-id="a3b05-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="a3b05-119">No painel **Editar política**, escolha **Editar** ao lado de **Controle de acesso a documentos do Office**, expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e verifique se a opção **Redefinir PIN após algumas tentativas fracassadas** está definida com algum número; o padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="a3b05-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number - this is 5 by default.</span></span> 
  
1. <span data-ttu-id="a3b05-120">No dispositivo Android do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário.</span><span class="sxs-lookup"><span data-stu-id="a3b05-120">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="a3b05-p101">Insira um PIN incorreto o número de vezes especificado pela política. Você verá um aviso informando **Limite de tentativa do PIN alcançado** para redefinir o PIN.</span><span class="sxs-lookup"><span data-stu-id="a3b05-p101">Enter an incorrect PIN as many times as specified by the policy. You will see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="a3b05-p102">Pressione **Redefinir PIN**. Você será solicitado a entrar com as credenciais do Microsoft 365 Business do usuário e configurar um novo PIN.</span><span class="sxs-lookup"><span data-stu-id="a3b05-p102">Press **Reset PIN**. You will be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="a3b05-126">Validar Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="a3b05-126">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="a3b05-127">No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="a3b05-127">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="a3b05-129">No dispositivo Android do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário e insira um PIN se necessário.</span><span class="sxs-lookup"><span data-stu-id="a3b05-129">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="a3b05-130">Abra um email que contenha um anexo e toque no ícone de seta para baixo ao lado das informações do anexo.</span><span class="sxs-lookup"><span data-stu-id="a3b05-130">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="a3b05-132">Você verá **Não é possível salvar no dispositivo** na parte inferior da tela.</span><span class="sxs-lookup"><span data-stu-id="a3b05-132">You will see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="a3b05-134">A opção para salvar no OneDrive for Business não está habilitada para o Android neste momento, portanto, só é possível ver que salvar localmente está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="a3b05-134">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="a3b05-135">Validar Solicitar que o usuário entre novamente se os aplicativos do Office ficarem ociosos por um período especificado</span><span class="sxs-lookup"><span data-stu-id="a3b05-135">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="a3b05-136">No painel **Editar política**, escolha **Editar** ao lado de **Controle de acesso a documentos do Office**, expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e verifique se a opção **Solicitar que o usuário entre novamente se os aplicativos do Office ficarem ociosos por um período especificado** está definida com algum número de minutos; o padrão é 30.</span><span class="sxs-lookup"><span data-stu-id="a3b05-136">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes - this is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="a3b05-137">No dispositivo Android do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário e insira um PIN se necessário.</span><span class="sxs-lookup"><span data-stu-id="a3b05-137">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="a3b05-p103">Agora você deverá ver a caixa de entrada do Outlook. Deixe o dispositivo Android ocioso sem tocar nele por pelo menos 30 minutos (ou por um período diferente superior ao especificado na política). O dispositivo provavelmente ficará escuro.</span><span class="sxs-lookup"><span data-stu-id="a3b05-p103">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="a3b05-141">Acesse novamente o Outlook no dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="a3b05-141">Re-access Outlook on the Android device.</span></span>
    
4. <span data-ttu-id="a3b05-142">Você será solicitado a inserir seu PIN para poder acessar o Outlook novamente.</span><span class="sxs-lookup"><span data-stu-id="a3b05-142">You will be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="a3b05-143">Validar Proteger arquivos de trabalho com criptografia</span><span class="sxs-lookup"><span data-stu-id="a3b05-143">Validate Protect work files with encryption</span></span>

<span data-ttu-id="a3b05-144">No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Proteger arquivos de trabalho com criptografia** está definida como **Ativada** e a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Desativada**.</span><span class="sxs-lookup"><span data-stu-id="a3b05-144">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="a3b05-145">No dispositivo Android do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário e insira um PIN se necessário.</span><span class="sxs-lookup"><span data-stu-id="a3b05-145">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="a3b05-146">Abra um email que contenha alguns arquivos de imagem em anexo.</span><span class="sxs-lookup"><span data-stu-id="a3b05-146">Open an email which contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="a3b05-147">Toque no ícone de seta para baixo ao lado das informações do anexo para salvá-lo.</span><span class="sxs-lookup"><span data-stu-id="a3b05-147">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="a3b05-p104">Você poderá ser solicitado a permitir que o Outlook acesse arquivos, mídia e fotos em seu dispositivo. Toque em **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="a3b05-p104">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="a3b05-151">Na parte inferior da tela, escolha **Salvar no Dispositivo** e, em seguida, abra o aplicativo **Galeria**.</span><span class="sxs-lookup"><span data-stu-id="a3b05-151">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="a3b05-p105">Você deverá ver uma foto criptografada (ou mais, caso tenha salvado vários anexos de arquivos de imagem) na lista. Ela poderá aparecer na lista Imagens como um quadrado cinza com um ponto de exclamação branco dentro de um círculo branco no centro do quadrado cinza.</span><span class="sxs-lookup"><span data-stu-id="a3b05-p105">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a><span data-ttu-id="a3b05-155">iOS</span><span class="sxs-lookup"><span data-stu-id="a3b05-155">iOS</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="a3b05-156">Verifique se as configurações de proteção do aplicativo estão funcionando nos dispositivos de usuário</span><span class="sxs-lookup"><span data-stu-id="a3b05-156">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="a3b05-157">Depois de [definir configurações de aplicativo para dispositivos iOS](app-protection-settings-for-android-and-ios.md) para proteger aplicativos, você pode seguir estas etapas para validar o funcionamento das configurações escolhidas.</span><span class="sxs-lookup"><span data-stu-id="a3b05-157">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="a3b05-158">Em primeiro lugar, certifique-se de que a política se aplica ao aplicativo no qual você a validará.</span><span class="sxs-lookup"><span data-stu-id="a3b05-158">First, make sure that the policy applies to the app in which you are going to validate it.</span></span>
  
1. <span data-ttu-id="a3b05-159">No [centro de administração](https://portal.office.com) do Microsoft 365 Business, acesse **Políticas** \> **Editar política**.</span><span class="sxs-lookup"><span data-stu-id="a3b05-159">In the Microsoft 365 Business [admin center](https://portal.office.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="a3b05-160">Escolha **Política de aplicativo para iOS** para verificar as configurações que você criou na instalação ou outra política que você tenha criado e verifique se ela é aplicada, por exemplo, no Outlook.</span><span class="sxs-lookup"><span data-stu-id="a3b05-160">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it is enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="a3b05-162">Validar Exigir um PIN para acessar aplicativos do Office</span><span class="sxs-lookup"><span data-stu-id="a3b05-162">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="a3b05-163">No painel **Editar política**, escolha **Editar** ao lado de **Controle de acesso a documentos do Office**, expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e verifique se a opção **Exigir um PIN ou uma impressão digital para acessar os aplicativos do Office** está definida como **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="a3b05-163">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Make sure that the Require a PIN or fingerprint to acces Office apps is set to On.](media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="a3b05-165">No dispositivo iOS do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário.</span><span class="sxs-lookup"><span data-stu-id="a3b05-165">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="a3b05-166">Você também deverá digitar um PIN ou usar uma impressão digital.</span><span class="sxs-lookup"><span data-stu-id="a3b05-166">You will also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="a3b05-168">Validar Redefinir PIN após algumas tentativas fracassadas</span><span class="sxs-lookup"><span data-stu-id="a3b05-168">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="a3b05-169">No painel **Editar política**, escolha **Editar** ao lado de **Controle de acesso a documentos do Office**, expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e verifique se a opção **Redefinir PIN após algumas tentativas fracassadas** está definida com algum número; o padrão é 5.</span><span class="sxs-lookup"><span data-stu-id="a3b05-169">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number - this is 5 by default.</span></span> 
  
1. <span data-ttu-id="a3b05-170">No dispositivo iOS do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário.</span><span class="sxs-lookup"><span data-stu-id="a3b05-170">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials.</span></span>
    
2. <span data-ttu-id="a3b05-p106">Insira um PIN incorreto o número de vezes especificado pela política. Você verá um aviso informando **Limite de tentativa do PIN alcançado** para redefinir o PIN.</span><span class="sxs-lookup"><span data-stu-id="a3b05-p106">Enter an incorrect PIN as many times as specified by the policy. You will see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="a3b05-p107">Pressione **OK**. Você será solicitado a entrar com as credenciais do Microsoft 365 Business do usuário e configurar um novo PIN.</span><span class="sxs-lookup"><span data-stu-id="a3b05-p107">Press **OK**. You will be prompted to sign in with the user's Microsoft 365 Business credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="a3b05-176">Validar Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="a3b05-176">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="a3b05-177">No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="a3b05-177">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="a3b05-179">No dispositivo iOS do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário e insira um PIN se necessário.</span><span class="sxs-lookup"><span data-stu-id="a3b05-179">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="a3b05-180">Abra um email que contenha um anexo, abra o anexo e escolha **Salvar** na parte inferior da tela.</span><span class="sxs-lookup"><span data-stu-id="a3b05-180">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="a3b05-p108">Você só verá uma opção para o OneDrive for Business. Caso contrário, toque em **Adicionar Conta** e escolha **OneDrive for Business** na tela **Adicionar Conta de Armazenamento**. Forneça o Microsoft 365 Business do usuário final para entrar quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="a3b05-p108">You should only see an option for OneDrive for Business. If not If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen. Provide the end user's Microsoft 365 Business to sign in when prompted.</span></span> 
    
    <span data-ttu-id="a3b05-185">Toque em **Salvar** e selecione **OneDrive for Business**.</span><span class="sxs-lookup"><span data-stu-id="a3b05-185">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="a3b05-186">Validar Solicitar que o usuário entre novamente se os aplicativos do Office ficarem ociosos por um período especificado</span><span class="sxs-lookup"><span data-stu-id="a3b05-186">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="a3b05-187">No painel **Editar política**, escolha **Editar** ao lado de **Controle de acesso a documentos do Office**, expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e verifique se a opção **Solicitar que o usuário entre novamente se os aplicativos do Office ficarem ociosos por um período especificado** está definida com algum número de minutos; o padrão é 30.</span><span class="sxs-lookup"><span data-stu-id="a3b05-187">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes - this is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="a3b05-188">No dispositivo iOS do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário e insira um PIN se necessário.</span><span class="sxs-lookup"><span data-stu-id="a3b05-188">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="a3b05-p109">Agora você deverá ver a caixa de entrada do Outlook. Deixe o dispositivo iOS sem tocar nele por pelo menos 30 minutos (ou por um período diferente superior ao especificado na política). O dispositivo provavelmente ficará escuro.</span><span class="sxs-lookup"><span data-stu-id="a3b05-p109">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="a3b05-192">Acesse novamente o Outlook no dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="a3b05-192">Re-access Outlook on the iOS device.</span></span>
    
4. <span data-ttu-id="a3b05-193">Você será solicitado a inserir seu PIN para poder acessar o Outlook novamente.</span><span class="sxs-lookup"><span data-stu-id="a3b05-193">You will be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="a3b05-194">Validar Proteger arquivos de trabalho com criptografia</span><span class="sxs-lookup"><span data-stu-id="a3b05-194">Validate Protect work files with encryption</span></span>

<span data-ttu-id="a3b05-195">No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Proteger arquivos de trabalho com criptografia** está definida como **Ativada** e a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Desativada**.</span><span class="sxs-lookup"><span data-stu-id="a3b05-195">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="a3b05-196">No dispositivo iOS do usuário, abra o Outlook e entre com as credenciais do Microsoft 365 Business do usuário e insira um PIN se necessário.</span><span class="sxs-lookup"><span data-stu-id="a3b05-196">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="a3b05-197">Abra um email que contenha alguns arquivos de imagem em anexo.</span><span class="sxs-lookup"><span data-stu-id="a3b05-197">Open an email which contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="a3b05-198">Toque no anexo e, em seguida, toque na opção **Salvar** abaixo dele.</span><span class="sxs-lookup"><span data-stu-id="a3b05-198">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="a3b05-p110">Abra o aplicativo **Fotos** na tela inicial. Você deverá ver uma foto criptografada (ou mais, caso tenha salvado vários anexos de arquivos de imagem) salva, mas criptografada.</span><span class="sxs-lookup"><span data-stu-id="a3b05-p110">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

