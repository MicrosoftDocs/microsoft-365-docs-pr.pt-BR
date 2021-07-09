---
title: Validar configurações de proteção de aplicativos em dispositivos Android ou iOS
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Saiba como validar as configurações Microsoft 365 Business Premium proteção do aplicativo em seus dispositivos Android ou iOS.
ms.openlocfilehash: 43e74b548711550090021c39096b1647cee9e039
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339321"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a><span data-ttu-id="44e87-103">Validar configurações de proteção de aplicativos em dispositivos Android ou iOS</span><span class="sxs-lookup"><span data-stu-id="44e87-103">Validate app protection settings on Android or iOS devices</span></span>

<span data-ttu-id="44e87-104">Siga as instruções nas seções a seguir para validar as configurações de proteção de aplicativos em dispositivos Android ou iOS.</span><span class="sxs-lookup"><span data-stu-id="44e87-104">Follow the instructions in the following sections to validate app protection settings on Android or iOS devices.</span></span>
  
## <a name="android"></a><span data-ttu-id="44e87-105">Android</span><span class="sxs-lookup"><span data-stu-id="44e87-105">Android</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="44e87-106">Verifique se as configurações de proteção do aplicativo estão funcionando em dispositivos de usuário</span><span class="sxs-lookup"><span data-stu-id="44e87-106">Check that the app protection settings are working on user devices</span></span>

<span data-ttu-id="44e87-107">Depois de [definir configurações de aplicativo para dispositivos Android](app-protection-settings-for-android-and-ios.md) para proteger aplicativos, você pode seguir estas etapas para validar o funcionamento das configurações escolhidas.</span><span class="sxs-lookup"><span data-stu-id="44e87-107">After you [set app configurations for Android devices](app-protection-settings-for-android-and-ios.md) to protect the apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="44e87-108">Primeiro, certifique-se de que a política se aplique ao aplicativo no qual você irá validá-la.</span><span class="sxs-lookup"><span data-stu-id="44e87-108">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="44e87-109">No centro de Microsoft 365 Business Premium [de administração,](https://admin.microsoft.com)vá para **Política Editar** \> **política**.</span><span class="sxs-lookup"><span data-stu-id="44e87-109">In the Microsoft 365 Business Premium [admin center](https://admin.microsoft.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="44e87-110">Escolha **Política de aplicativo** para Android para as configurações criadas na instalação ou outra política que você criou e verifique se ela é imposta para Outlook, por exemplo.</span><span class="sxs-lookup"><span data-stu-id="44e87-110">Choose **Application policy for Android** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook, for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a><span data-ttu-id="44e87-112">Validar Exigir um PIN ou uma impressão digital para acessar aplicativos do Office</span><span class="sxs-lookup"><span data-stu-id="44e87-112">Validate Require a PIN or a fingerprint to access Office apps</span></span>

<span data-ttu-id="44e87-113">No painel **Editar política**, escolha **Editar** ao lado de **Controle de acesso a documentos do Office**, expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e verifique se a opção **Exigir um PIN ou uma impressão digital para acessar os aplicativos do Office** está definida como **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="44e87-113">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Certifique-se de que a opção Exigir um PIN ou impressão digital para acessar Office aplicativos está definida como On.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="44e87-115">No dispositivo Android do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário.</span><span class="sxs-lookup"><span data-stu-id="44e87-115">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="44e87-116">Você também será solicitado a inserir um PIN ou usar uma impressão digital.</span><span class="sxs-lookup"><span data-stu-id="44e87-116">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your Android device to access Office apps.](../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="44e87-118">Validar Redefinir PIN após algumas tentativas fracassadas</span><span class="sxs-lookup"><span data-stu-id="44e87-118">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="44e87-119">No painel **Editar** política, escolha **Editar** ao lado do controle de acesso **Office** documentos, expanda **Gerenciar como** os usuários acessam arquivos Office em dispositivos móveis e certifique-se de que **Redefinir PIN** após o número de tentativas com falha seja definido como algum número.</span><span class="sxs-lookup"><span data-stu-id="44e87-119">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="44e87-120">Isso é 5 por padrão.</span><span class="sxs-lookup"><span data-stu-id="44e87-120">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="44e87-121">No dispositivo Android do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário.</span><span class="sxs-lookup"><span data-stu-id="44e87-121">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="44e87-122">Insira um PIN incorreto o número de vezes especificado pela política.</span><span class="sxs-lookup"><span data-stu-id="44e87-122">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="44e87-123">Você verá um prompt informando limite de tentativa **de PIN atingido** para redefinir o PIN.</span><span class="sxs-lookup"><span data-stu-id="44e87-123">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. <span data-ttu-id="44e87-125">Pressione **Redefinir PIN**.</span><span class="sxs-lookup"><span data-stu-id="44e87-125">Press **Reset PIN**.</span></span> <span data-ttu-id="44e87-126">Você será solicitado a entrar com as credenciais de Microsoft 365 Business Premium do usuário e, em seguida, será necessário definir um novo PIN.</span><span class="sxs-lookup"><span data-stu-id="44e87-126">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="44e87-127">Validar Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="44e87-127">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="44e87-128">No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="44e87-128">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="44e87-130">No dispositivo Android do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário e insira um PIN, se solicitado.</span><span class="sxs-lookup"><span data-stu-id="44e87-130">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="44e87-131">Abra um email que contenha um anexo e toque no ícone de seta para baixo ao lado das informações do anexo.</span><span class="sxs-lookup"><span data-stu-id="44e87-131">Open an email that contains an attachment and tap the down arrow icon next to the attachment's information.</span></span>
    
    ![Tap the down arrow next to an attachment to try to save it.](../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    <span data-ttu-id="44e87-133">Você verá Não **é possível salvar no dispositivo** na parte inferior da tela.</span><span class="sxs-lookup"><span data-stu-id="44e87-133">You'll see **Cannot save to device** on the bottom of the screen.</span></span> 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > <span data-ttu-id="44e87-135">A opção para salvar no OneDrive for Business não está habilitada para o Android neste momento, portanto, só é possível ver que salvar localmente está bloqueado.</span><span class="sxs-lookup"><span data-stu-id="44e87-135">Saving to OneDrive for Business is not enabled for Android at this time, so you can only see that saving locally is blocked.</span></span> 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="44e87-136">Validar Solicitar que o usuário entre novamente se os aplicativos do Office ficarem ociosos por um período especificado</span><span class="sxs-lookup"><span data-stu-id="44e87-136">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="44e87-137">No  painel Editar política, escolha **Editar** ao lado do controle de acesso **Office** documentos, expanda Gerenciar como  os usuários acessam arquivos **Office** em dispositivos móveis e certifique-se de exigir que os usuários entre novamente depois que os aplicativos Office estão ociosos por algum número de minutos.</span><span class="sxs-lookup"><span data-stu-id="44e87-137">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="44e87-138">Por padrão, são 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="44e87-138">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="44e87-139">No dispositivo Android do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário e insira um PIN, se solicitado.</span><span class="sxs-lookup"><span data-stu-id="44e87-139">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="44e87-p105">Agora você deverá ver a caixa de entrada do Outlook. Deixe o dispositivo Android ocioso sem tocar nele por pelo menos 30 minutos (ou por um período diferente superior ao especificado na política). O dispositivo provavelmente ficará escuro.</span><span class="sxs-lookup"><span data-stu-id="44e87-p105">You should now see Outlook's inbox. Let the Android device idle untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="44e87-143">Acesse Outlook no dispositivo Android novamente.</span><span class="sxs-lookup"><span data-stu-id="44e87-143">Access Outlook on the Android device again.</span></span>
    
4. <span data-ttu-id="44e87-144">Você será solicitado a inserir seu PIN antes de poder acessar Outlook novamente.</span><span class="sxs-lookup"><span data-stu-id="44e87-144">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="44e87-145">Validar Proteger arquivos de trabalho com criptografia</span><span class="sxs-lookup"><span data-stu-id="44e87-145">Validate Protect work files with encryption</span></span>

<span data-ttu-id="44e87-146">No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Proteger arquivos de trabalho com criptografia** está definida como **Ativada** e a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Desativada**.</span><span class="sxs-lookup"><span data-stu-id="44e87-146">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="44e87-147">No dispositivo Android do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário e insira um PIN, se solicitado.</span><span class="sxs-lookup"><span data-stu-id="44e87-147">In the user's Android device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="44e87-148">Abra um email que contém alguns anexos de arquivo de imagem.</span><span class="sxs-lookup"><span data-stu-id="44e87-148">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="44e87-149">Toque no ícone de seta para baixo ao lado das informações do anexo para salvá-lo.</span><span class="sxs-lookup"><span data-stu-id="44e87-149">Tap the down arrow icon next to the attachment's info to save it.</span></span>
    
    ![Tap the down arrow to save the figure file to the Android device.](../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. <span data-ttu-id="44e87-p106">Você poderá ser solicitado a permitir que o Outlook acesse arquivos, mídia e fotos em seu dispositivo. Toque em **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="44e87-p106">You may be prompted to allow Outlook to access photos, media, and files on your device. Tap **Allow**.</span></span>
    
5. <span data-ttu-id="44e87-153">Na parte inferior da tela, escolha **Salvar no Dispositivo** e, em seguida, abra o aplicativo **Galeria**.</span><span class="sxs-lookup"><span data-stu-id="44e87-153">At the bottom of the screen, choose to **Save to Device** and then open the **Gallery** app.</span></span> 
    
6. <span data-ttu-id="44e87-p107">Você deverá ver uma foto criptografada (ou mais, caso tenha salvado vários anexos de arquivos de imagem) na lista. Ela poderá aparecer na lista Imagens como um quadrado cinza com um ponto de exclamação branco dentro de um círculo branco no centro do quadrado cinza.</span><span class="sxs-lookup"><span data-stu-id="44e87-p107">You should see an encrypted photo (or more, if you saved multiple image file attachments) in the list. It may appear in the Pictures list as a gray square with a white exclamation point within a white circle in the center of the gray square.</span></span>
    
    ![An encrypted image file in the Gallery app.](../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a><span data-ttu-id="44e87-157">iOS</span><span class="sxs-lookup"><span data-stu-id="44e87-157">iOS</span></span>
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a><span data-ttu-id="44e87-158">Verifique se as configurações de proteção do aplicativo estão funcionando nos dispositivos de usuário</span><span class="sxs-lookup"><span data-stu-id="44e87-158">Check that the App protection settings are working on user devices</span></span>

<span data-ttu-id="44e87-159">Depois de [definir configurações de aplicativo para dispositivos iOS](app-protection-settings-for-android-and-ios.md) para proteger aplicativos, você pode seguir estas etapas para validar o funcionamento das configurações escolhidas.</span><span class="sxs-lookup"><span data-stu-id="44e87-159">After you [set app configurations for iOS devices](app-protection-settings-for-android-and-ios.md) to protect apps, you can follow these steps to validate that the settings you chose work.</span></span> 
  
<span data-ttu-id="44e87-160">Primeiro, certifique-se de que a política se aplique ao aplicativo no qual você irá validá-la.</span><span class="sxs-lookup"><span data-stu-id="44e87-160">First, make sure that the policy applies to the app in which you're going to validate it.</span></span>
  
1. <span data-ttu-id="44e87-161">No centro de Microsoft 365 Business Premium [de administração,](https://admin.microsoft.com)vá para **Política Editar** \> **política**.</span><span class="sxs-lookup"><span data-stu-id="44e87-161">In the Microsoft 365 Business Premium [admin center](https://admin.microsoft.com), go to **Policies** \> **Edit policy**.</span></span>
    
2. <span data-ttu-id="44e87-162">Escolha **Política de aplicativo para iOS** para as configurações criadas na instalação ou outra política que você criou e verifique se ela é imposta para Outlook por exemplo.</span><span class="sxs-lookup"><span data-stu-id="44e87-162">Choose **Application policy for iOS** for the settings you created at setup, or another policy you created, and verify that it's enforced for Outlook for example.</span></span> 
    
    ![Shows all the apps for which this policy protects files.](../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a><span data-ttu-id="44e87-164">Validar Exigir um PIN para acessar aplicativos do Office</span><span class="sxs-lookup"><span data-stu-id="44e87-164">Validate Require a PIN to access Office apps</span></span>

<span data-ttu-id="44e87-165">No painel **Editar política**, escolha **Editar** ao lado de **Controle de acesso a documentos do Office**, expanda **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e verifique se a opção **Exigir um PIN ou uma impressão digital para acessar os aplicativos do Office** está definida como **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="44e87-165">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require a PIN or fingerprint to access Office apps** is set to **On**.</span></span>
  
![Certifique-se de que a opção Exigir um PIN ou impressão digital para acessar Office aplicativos está definida como On.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. <span data-ttu-id="44e87-167">No dispositivo iOS do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário.</span><span class="sxs-lookup"><span data-stu-id="44e87-167">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="44e87-168">Você também será solicitado a inserir um PIN ou usar uma impressão digital.</span><span class="sxs-lookup"><span data-stu-id="44e87-168">You'll also be prompted to enter a PIN or use a fingerprint.</span></span>
    
    ![Enter a PIN on your IOS device to access Office apps.](../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a><span data-ttu-id="44e87-170">Validar Redefinir PIN após algumas tentativas fracassadas</span><span class="sxs-lookup"><span data-stu-id="44e87-170">Validate Reset PIN after number of failed attempts</span></span>

<span data-ttu-id="44e87-171">No painel **Editar** política, escolha **Editar** ao lado do controle de acesso **Office** documentos, expanda **Gerenciar como** os usuários acessam arquivos Office em dispositivos móveis e certifique-se de que **Redefinir PIN** após o número de tentativas com falha seja definido como algum número.</span><span class="sxs-lookup"><span data-stu-id="44e87-171">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Reset PIN after number of failed attempts** is set to some number.</span></span> <span data-ttu-id="44e87-172">Isso é 5 por padrão.</span><span class="sxs-lookup"><span data-stu-id="44e87-172">This is 5 by default.</span></span> 
  
1. <span data-ttu-id="44e87-173">No dispositivo iOS do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário.</span><span class="sxs-lookup"><span data-stu-id="44e87-173">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials.</span></span>
    
2. <span data-ttu-id="44e87-174">Insira um PIN incorreto o número de vezes especificado pela política.</span><span class="sxs-lookup"><span data-stu-id="44e87-174">Enter an incorrect PIN as many times as specified by the policy.</span></span> <span data-ttu-id="44e87-175">Você verá um prompt informando limite de tentativa **de PIN atingido** para redefinir o PIN.</span><span class="sxs-lookup"><span data-stu-id="44e87-175">You'll see a prompt that states **PIN Attempt Limit Reached** to reset the PIN.</span></span> 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. <span data-ttu-id="44e87-177">Pressione **OK**.</span><span class="sxs-lookup"><span data-stu-id="44e87-177">Press **OK**.</span></span> <span data-ttu-id="44e87-178">Você será solicitado a entrar com as credenciais de Microsoft 365 Business Premium do usuário e, em seguida, será necessário definir um novo PIN.</span><span class="sxs-lookup"><span data-stu-id="44e87-178">You'll be prompted to sign in with the user's Microsoft 365 Business Premium credentials, and then required to set a new PIN.</span></span>
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a><span data-ttu-id="44e87-179">Validar Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="44e87-179">Validate Force users to save all work files to OneDrive for Business</span></span>

<span data-ttu-id="44e87-180">No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="44e87-180">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Force users to save all work files to OneDrive for Business** is set to **On**.</span></span>
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. <span data-ttu-id="44e87-182">No dispositivo iOS do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário e insira um PIN, se solicitado.</span><span class="sxs-lookup"><span data-stu-id="44e87-182">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="44e87-183">Abra um email que contenha um anexo, abra o anexo e escolha **Salvar** na parte inferior da tela.</span><span class="sxs-lookup"><span data-stu-id="44e87-183">Open an email that contains an attachment, open the attachment and choose **Save** on the bottom of the screen.</span></span> 
    
    ![Tap the Save option after you open an attachment to try to save it.](../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. <span data-ttu-id="44e87-185">Você só verá uma opção para o OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="44e87-185">You should only see an option for OneDrive for Business.</span></span> <span data-ttu-id="44e87-186">Se não, toque **em Adicionar Conta** e selecione **OneDrive for Business** na tela **Adicionar Armazenamento** Conta.</span><span class="sxs-lookup"><span data-stu-id="44e87-186">If not, tap **Add Account** and select **OneDrive for Business** from the **Add Storage Account** screen.</span></span> <span data-ttu-id="44e87-187">Forneça ao usuário final Microsoft 365 Business Premium entrar quando solicitado.</span><span class="sxs-lookup"><span data-stu-id="44e87-187">Provide the end user's Microsoft 365 Business Premium to sign in when prompted.</span></span> 
    
    <span data-ttu-id="44e87-188">Toque em **Salvar** e selecione **OneDrive for Business**.</span><span class="sxs-lookup"><span data-stu-id="44e87-188">Tap **Save** and select **OneDrive for Business**.</span></span>
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a><span data-ttu-id="44e87-189">Validar Solicitar que o usuário entre novamente se os aplicativos do Office ficarem ociosos por um período especificado</span><span class="sxs-lookup"><span data-stu-id="44e87-189">Validate Require user to sign in again if Office apps have been idle for a specified time</span></span>

<span data-ttu-id="44e87-190">No  painel Editar política, escolha **Editar** ao lado do controle de acesso **Office** documentos, expanda Gerenciar como  os usuários acessam arquivos **Office** em dispositivos móveis e certifique-se de exigir que os usuários entre novamente depois que os aplicativos Office estão ociosos por algum número de minutos.</span><span class="sxs-lookup"><span data-stu-id="44e87-190">In the **Edit policy** pane, choose **Edit** next to **Office documents access control**, expand **Manage how users access Office files on mobile devices**, and make sure that **Require users to sign in again after Office apps have been idle for** is set to some number of minutes.</span></span> <span data-ttu-id="44e87-191">Por padrão, são 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="44e87-191">This is 30 minutes by default.</span></span> 
  
1. <span data-ttu-id="44e87-192">No dispositivo iOS do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário e insira um PIN, se solicitado.</span><span class="sxs-lookup"><span data-stu-id="44e87-192">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="44e87-p113">Agora você deverá ver a caixa de entrada do Outlook. Deixe o dispositivo iOS sem tocar nele por pelo menos 30 minutos (ou por um período diferente superior ao especificado na política). O dispositivo provavelmente ficará escuro.</span><span class="sxs-lookup"><span data-stu-id="44e87-p113">You should now see Outlook's inbox. Let the iOS device untouched for at least 30 minutes (or some other amount of time, longer than what you specified in the policy). The device will likely dim.</span></span>
    
3. <span data-ttu-id="44e87-196">Acesse Outlook no dispositivo iOS novamente.</span><span class="sxs-lookup"><span data-stu-id="44e87-196">Access Outlook on the iOS device again.</span></span>
    
4. <span data-ttu-id="44e87-197">Você será solicitado a inserir seu PIN antes de poder acessar Outlook novamente.</span><span class="sxs-lookup"><span data-stu-id="44e87-197">You'll be prompted to enter your PIN before you can access Outlook again.</span></span>
    
### <a name="validate-protect-work-files-with-encryption"></a><span data-ttu-id="44e87-198">Validar Proteger arquivos de trabalho com criptografia</span><span class="sxs-lookup"><span data-stu-id="44e87-198">Validate Protect work files with encryption</span></span>

<span data-ttu-id="44e87-199">No painel **Editar política**, escolha **Editar** ao lado de **Proteção contra dispositivos perdidos ou roubados**, expanda **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e verifique se a opção **Proteger arquivos de trabalho com criptografia** está definida como **Ativada** e a opção **Forçar os usuários a salvarem todos os arquivos de trabalho no OneDrive for Business** está definida como **Desativada**.</span><span class="sxs-lookup"><span data-stu-id="44e87-199">In the **Edit policy** pane, choose **Edit** next to **Protection against lost or stolen devices**, expand **Protect work files when devices are lost or stolen**, and make sure that **Protect work files with encryption** is set to **On**, and **Force users to save all work files to OneDrive for Business** is set to **Off**.</span></span>
  
1. <span data-ttu-id="44e87-200">No dispositivo iOS do usuário, abra Outlook e entre com as credenciais de Microsoft 365 Business Premium do usuário e insira um PIN, se solicitado.</span><span class="sxs-lookup"><span data-stu-id="44e87-200">In the user's iOS device, open Outlook and sign in with the user's Microsoft 365 Business Premium credentials, and enter a PIN if requested.</span></span>
    
2. <span data-ttu-id="44e87-201">Abra um email que contém alguns anexos de arquivo de imagem.</span><span class="sxs-lookup"><span data-stu-id="44e87-201">Open an email that contains a few image file attachments.</span></span>
    
3. <span data-ttu-id="44e87-202">Toque no anexo e, em seguida, toque na opção **Salvar** abaixo dele.</span><span class="sxs-lookup"><span data-stu-id="44e87-202">Tap the attachment and then tap the **Save** option under it.</span></span> 
    
4. <span data-ttu-id="44e87-p114">Abra o aplicativo **Fotos** na tela inicial. Você deverá ver uma foto criptografada (ou mais, caso tenha salvado vários anexos de arquivos de imagem) salva, mas criptografada.</span><span class="sxs-lookup"><span data-stu-id="44e87-p114">Open **Photos** app from the home screen. You should see an encrypted photo (or more, if you saved multiple image file attachments) saved, but encrypted.</span></span> 
    
---

