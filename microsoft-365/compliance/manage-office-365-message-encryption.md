---
title: Gerenciar a Criptografia de Mensagens do Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Após concluir a configuração do Office 365 Message Encryption (OME), saiba como personalizar sua implantação de várias maneiras.
ms.openlocfilehash: 83fa620852ea9b2e0cd50d50b6715742658b7239
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815428"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="00e94-103">Gerenciar a Criptografia de Mensagens do Office 365</span><span class="sxs-lookup"><span data-stu-id="00e94-103">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="00e94-104">Após concluir a configuração do Office 365 Message Encryption (OME), você pode personalizar a configuração de sua implantação de várias maneiras.</span><span class="sxs-lookup"><span data-stu-id="00e94-104">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="00e94-105">Por exemplo, você pode configurar se deseja habilitar códigos de passagem única, exibir o botão **criptografar** no Outlook na Web e muito mais.</span><span class="sxs-lookup"><span data-stu-id="00e94-105">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="00e94-106">As tarefas deste artigo descrevem como.</span><span class="sxs-lookup"><span data-stu-id="00e94-106">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="00e94-107">Gerenciar se o Google, Yahoo e destinatários de contas da Microsoft podem usar essas contas para entrar no portal de criptografia de mensagens do Office 365</span><span class="sxs-lookup"><span data-stu-id="00e94-107">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="00e94-108">Ao configurar os novos recursos de criptografia de mensagens do Office 365, os usuários em sua organização podem enviar mensagens para destinatários fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="00e94-108">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your organization.</span></span> <span data-ttu-id="00e94-109">Se o destinatário usar uma *ID social* , como uma conta do Google, uma conta do Yahoo ou uma conta da Microsoft, o destinatário poderá entrar no portal do ome com uma ID social.</span><span class="sxs-lookup"><span data-stu-id="00e94-109">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="00e94-110">Se quiser, você pode optar por não permitir que os destinatários usem IDs sociais para entrar no portal do OME.</span><span class="sxs-lookup"><span data-stu-id="00e94-110">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="00e94-111">Para gerenciar se os destinatários podem usar IDs sociais para entrar no portal do OME</span><span class="sxs-lookup"><span data-stu-id="00e94-111">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="00e94-112">[Conecte-se ao Exchange Online usando o PowerShell remoto](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="00e94-112">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="00e94-113">Execute o cmdlet Set-OMEConfiguration com o parâmetro SocialIdSignIn da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="00e94-113">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="00e94-114">Por exemplo, para desabilitar as IDs sociais:</span><span class="sxs-lookup"><span data-stu-id="00e94-114">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="00e94-115">Para habilitar as IDs sociais:</span><span class="sxs-lookup"><span data-stu-id="00e94-115">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="00e94-116">Gerenciar o uso de códigos de passagem única para o portal de criptografia de mensagem do Office 365</span><span class="sxs-lookup"><span data-stu-id="00e94-116">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="00e94-117">Se o destinatário de uma mensagem criptografada pelo OME não usar o Outlook, independentemente da conta usada pelo destinatário, o destinatário receberá um link de exibição da Web de tempo limitado que permite que ele leia a mensagem.</span><span class="sxs-lookup"><span data-stu-id="00e94-117">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="00e94-118">Este link inclui um código de passagem única.</span><span class="sxs-lookup"><span data-stu-id="00e94-118">This link includes a one-time pass code.</span></span> <span data-ttu-id="00e94-119">Como administrador, você pode decidir se os destinatários podem usar códigos de passagem única para entrar no portal do OME.</span><span class="sxs-lookup"><span data-stu-id="00e94-119">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="00e94-120">Para gerenciar se o OME gera códigos de passagem única</span><span class="sxs-lookup"><span data-stu-id="00e94-120">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="00e94-121">Use uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização e inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="00e94-121">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="00e94-122">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="00e94-122">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="00e94-123">Execute o cmdlet Set-OMEConfiguration com o parâmetro OTPEnabled:</span><span class="sxs-lookup"><span data-stu-id="00e94-123">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="00e94-124">Por exemplo, para desabilitar códigos de passagem única:</span><span class="sxs-lookup"><span data-stu-id="00e94-124">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="00e94-125">Para habilitar códigos de passagem única:</span><span class="sxs-lookup"><span data-stu-id="00e94-125">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="00e94-126">Gerenciar a exibição do botão criptografar no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="00e94-126">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="00e94-127">Como administrador, você pode gerenciar se deseja exibir este botão para os usuários finais.</span><span class="sxs-lookup"><span data-stu-id="00e94-127">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="00e94-128">Para gerenciar se o botão criptografar aparece no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="00e94-128">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="00e94-129">Use uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização e inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="00e94-129">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="00e94-130">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="00e94-130">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="00e94-131">Execute o cmdlet Set-IRMConfiguration com o parâmetro-SimplifiedClientAccessEnabled:</span><span class="sxs-lookup"><span data-stu-id="00e94-131">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="00e94-132">Por exemplo, para desabilitar o botão **criptografar** :</span><span class="sxs-lookup"><span data-stu-id="00e94-132">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="00e94-133">Para habilitar o botão **criptografar** :</span><span class="sxs-lookup"><span data-stu-id="00e94-133">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="00e94-134">Habilitar a descriptografia do lado do serviço de mensagens de email para usuários do aplicativo iOS mail</span><span class="sxs-lookup"><span data-stu-id="00e94-134">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="00e94-135">O aplicativo de email iOS não pode descriptografar mensagens protegidas com a criptografia de mensagem do Office 365.</span><span class="sxs-lookup"><span data-stu-id="00e94-135">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="00e94-136">Como administrador do Microsoft 365, você pode aplicar a descriptografia do lado do serviço para mensagens entregues ao aplicativo de email iOS.</span><span class="sxs-lookup"><span data-stu-id="00e94-136">As a Microsoft 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="00e94-137">Quando você opta por usar a descriptografia do lado do serviço, o serviço envia uma cópia descriptografada da mensagem para o dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="00e94-137">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="00e94-138">O dispositivo cliente armazena uma cópia descriptografada da mensagem.</span><span class="sxs-lookup"><span data-stu-id="00e94-138">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="00e94-139">A mensagem também mantém informações sobre direitos de uso, mesmo que o aplicativo de email iOS não aplique direitos de uso do lado do cliente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="00e94-139">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="00e94-140">O usuário pode copiar ou imprimir a mensagem, mesmo que não tenha originalmente os direitos para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="00e94-140">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="00e94-141">No entanto, se o usuário tentar concluir uma ação que requer o servidor de email do Microsoft 365, como encaminhar a mensagem, o servidor não permitirá a ação se o usuário não tiver originalmente o uso do direito de fazer isso.</span><span class="sxs-lookup"><span data-stu-id="00e94-141">However, if the user attempts to complete an action that requires the Microsoft 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="00e94-142">No entanto, os usuários finais podem contornar a restrição de uso "não encaminhar" encaminhando a mensagem de uma conta diferente no aplicativo de email do iOS.</span><span class="sxs-lookup"><span data-stu-id="00e94-142">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="00e94-143">Independentemente de você configurar a descriptografia do lado do serviço de email, os anexos a mensagens criptografadas e protegidas por direitos não podem ser exibidos no aplicativo de email do iOS.</span><span class="sxs-lookup"><span data-stu-id="00e94-143">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="00e94-144">Se você optar por não permitir que as mensagens descriptografadas sejam enviadas aos usuários do aplicativo de email iOS, os usuários receberão uma mensagem afirmando que eles não têm direitos para exibir a mensagem.</span><span class="sxs-lookup"><span data-stu-id="00e94-144">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="00e94-145">Por padrão, a descriptografia do lado do serviço de mensagens de email não está habilitada.</span><span class="sxs-lookup"><span data-stu-id="00e94-145">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="00e94-146">Para obter mais informações e para uma visão da experiência do cliente, consulte [Exibir mensagens criptografadas no seu iPhone ou iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span><span class="sxs-lookup"><span data-stu-id="00e94-146">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="00e94-147">Para gerenciar se os usuários do aplicativo iOS podem exibir mensagens protegidas pela criptografia de mensagens do Office 365</span><span class="sxs-lookup"><span data-stu-id="00e94-147">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="00e94-148">Use uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização e inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="00e94-148">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="00e94-149">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="00e94-149">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="00e94-150">Execute o cmdlet Set-ActiveSyncOrganizations com o parâmetro AllowRMSSupportForUnenlightenedApps:</span><span class="sxs-lookup"><span data-stu-id="00e94-150">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="00e94-151">Por exemplo, para configurar o serviço para descriptografar mensagens antes que elas sejam enviadas para aplicativos não habilitados, como o aplicativo de email iOS:</span><span class="sxs-lookup"><span data-stu-id="00e94-151">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="00e94-152">Ou, para configurar o serviço para não enviar mensagens descriptografadas a aplicativos não habilitados:</span><span class="sxs-lookup"><span data-stu-id="00e94-152">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="00e94-153">As políticas de caixa de correio individuais (OWA/ActiveSync) substituem essas configurações (ou seja, se-IRMEnabled estiver definida como false dentro da respectiva diretiva de caixa de correio do OWA ou da diretiva de caixa de correio do ActiveSync, essas configurações não serão aplicadas).</span><span class="sxs-lookup"><span data-stu-id="00e94-153">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="00e94-154">Habilitar a descriptografia do lado do serviço de anexos de email para clientes de email de navegador da Web</span><span class="sxs-lookup"><span data-stu-id="00e94-154">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="00e94-155">Normalmente, quando você usa a criptografia de mensagem do Office 365, os anexos são criptografados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="00e94-155">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="00e94-156">Como administrador, você pode aplicar a descriptografia do lado do serviço para anexos de email que os usuários baixem de um navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="00e94-156">As an administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="00e94-157">Quando você usa a descriptografia do lado do serviço, o serviço envia uma cópia descriptografada do arquivo ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="00e94-157">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="00e94-158">A mensagem ainda está criptografada.</span><span class="sxs-lookup"><span data-stu-id="00e94-158">The message is still encrypted.</span></span> <span data-ttu-id="00e94-159">O anexo de email também mantém informações sobre direitos de uso, embora o navegador não aplique direitos de uso do lado do cliente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="00e94-159">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="00e94-160">O usuário pode copiar ou imprimir o anexo de email, mesmo que não tenha originalmente os direitos para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="00e94-160">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="00e94-161">No entanto, se o usuário tentar concluir uma ação que requer o servidor de email do Microsoft 365, como encaminhar o anexo, o servidor não permitirá a ação se o usuário não tiver originalmente o uso do direito de fazer isso.</span><span class="sxs-lookup"><span data-stu-id="00e94-161">However, if the user tries to complete an action that requires the Microsoft 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="00e94-162">Independentemente de você configurar a descriptografia do lado do serviço de anexos, os usuários não podem exibir nenhum anexo a emails protegidos e criptografados no aplicativo de email do iOS.</span><span class="sxs-lookup"><span data-stu-id="00e94-162">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="00e94-163">Se você optar por não permitir anexos de email descriptografados, que é o padrão, os usuários receberão uma mensagem afirmando que eles não têm direitos para exibir o anexo.</span><span class="sxs-lookup"><span data-stu-id="00e94-163">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="00e94-164">Para obter mais informações sobre como a Microsoft 365 implementa a criptografia de emails e anexos de email com a opção somente criptografia, consulte [opção somente criptografia para emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="00e94-164">For more information about how Microsoft 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="00e94-165">Para gerenciar se os anexos de email são descriptografados no download a partir de um navegador da Web</span><span class="sxs-lookup"><span data-stu-id="00e94-165">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="00e94-166">Use uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização e inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="00e94-166">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="00e94-167">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="00e94-167">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="00e94-168">Execute o cmdlet Set-IRMConfiguration com o parâmetro DecryptAttachmentForEncryptOnly:</span><span class="sxs-lookup"><span data-stu-id="00e94-168">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentForEncryptOnly parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   <span data-ttu-id="00e94-169">Por exemplo, para configurar o serviço para descriptografar anexos de email quando um usuário o baixa de um navegador da Web:</span><span class="sxs-lookup"><span data-stu-id="00e94-169">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   <span data-ttu-id="00e94-170">Para configurar o serviço para deixar anexos de email criptografados como estão no download:</span><span class="sxs-lookup"><span data-stu-id="00e94-170">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a><span data-ttu-id="00e94-171">Garantir que todos os destinatários externos usem o portal do OME para ler emails criptografados</span><span class="sxs-lookup"><span data-stu-id="00e94-171">Ensure all external recipients use the OME Portal to read encrypted mail</span></span>

<span data-ttu-id="00e94-172">Você pode usar modelos de identidade visual personalizados para forçar os destinatários a receber emails de conteúdo adicional que os direcionam a ler emails criptografados no portal do OME, em vez de usar o Outlook ou o Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="00e94-172">You can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="00e94-173">Você pode querer fazer isso se você usar deseja ter maior controle sobre como os destinatários usam o email que eles recebem.</span><span class="sxs-lookup"><span data-stu-id="00e94-173">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="00e94-174">Por exemplo, se os destinatários externos exibem email no portal da Web, você pode definir uma data de expiração para o email e pode revogar o email.</span><span class="sxs-lookup"><span data-stu-id="00e94-174">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="00e94-175">Esses recursos só são compatíveis com o portal do OME.</span><span class="sxs-lookup"><span data-stu-id="00e94-175">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="00e94-176">Você pode usar a opção criptografar e a opção não encaminhar ao criar regras de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="00e94-176">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a><span data-ttu-id="00e94-177">Usar um modelo personalizado para forçar todos os destinatários externos a usar o portal do OME e emails criptografados</span><span class="sxs-lookup"><span data-stu-id="00e94-177">Use a custom template to force all external recipients to use the OME Portal and for encrypted email</span></span>

1. <span data-ttu-id="00e94-178">Use uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização e inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="00e94-178">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="00e94-179">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="00e94-179">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="00e94-180">Execute o cmdlet New-TransportRule:</span><span class="sxs-lookup"><span data-stu-id="00e94-180">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="00e94-181">em que:</span><span class="sxs-lookup"><span data-stu-id="00e94-181">where:</span></span>

   - <span data-ttu-id="00e94-182">`mail flow rule name`é o nome que você deseja usar para a nova regra de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="00e94-182">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="00e94-183">`option name`é `Encrypt` ou `Do Not Forward` .</span><span class="sxs-lookup"><span data-stu-id="00e94-183">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="00e94-184">`template name`é o nome que você deu ao modelo de identidade visual personalizado, por exemplo `OME Configuration` .</span><span class="sxs-lookup"><span data-stu-id="00e94-184">`template name` is the name you gave the custom branding template, for example `OME Configuration`.</span></span>

   <span data-ttu-id="00e94-185">Para criptografar todos os emails externos com o modelo "configuração do OME" e aplicar a opção somente criptografia:</span><span class="sxs-lookup"><span data-stu-id="00e94-185">To encrypt all external email with the "OME Configuration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   <span data-ttu-id="00e94-186">Para criptografar todos os emails externos com o modelo "configuração do OME" e aplicar a opção não encaminhar:</span><span class="sxs-lookup"><span data-stu-id="00e94-186">To encrypt all external email with the "OME Configuration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="00e94-187">Personalizar a aparência de mensagens de email e o portal do OME</span><span class="sxs-lookup"><span data-stu-id="00e94-187">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="00e94-188">Para obter informações detalhadas sobre como você pode personalizar o OME para sua organização, confira [Adicionar a marca da sua organização às mensagens criptografadas](add-your-organization-brand-to-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="00e94-188">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="00e94-189">Desabilitar os novos recursos do OME</span><span class="sxs-lookup"><span data-stu-id="00e94-189">Disable the new capabilities for OME</span></span>

<span data-ttu-id="00e94-190">Esperamos que ele não venha, mas se você precisar, desabilitar os novos recursos do OME é muito simples.</span><span class="sxs-lookup"><span data-stu-id="00e94-190">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="00e94-191">Primeiro, você precisará remover as regras de fluxo de emails que criou que usam os novos recursos do OME.</span><span class="sxs-lookup"><span data-stu-id="00e94-191">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="00e94-192">Para obter informações sobre como remover regras de fluxo de email, consulte [Manage Mail Flow Rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="00e94-192">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="00e94-193">Em seguida, conclua estas etapas no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="00e94-193">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="00e94-194">Para desabilitar os novos recursos do OME</span><span class="sxs-lookup"><span data-stu-id="00e94-194">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="00e94-195">Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="00e94-195">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="00e94-196">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="00e94-196">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="00e94-197">Se você habilitou o botão **criptografar** no Outlook na Web, desabilite-o executando o cmdlet Set-IRMConfiguration com o parâmetro SimplifiedClientAccessEnabled.</span><span class="sxs-lookup"><span data-stu-id="00e94-197">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="00e94-198">Caso contrário, pule esta etapa.</span><span class="sxs-lookup"><span data-stu-id="00e94-198">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="00e94-199">Desabilite os novos recursos do OME executando o cmdlet Set-IRMConfiguration com o parâmetro AzureRMSLicensingEnabled definido como false:</span><span class="sxs-lookup"><span data-stu-id="00e94-199">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
