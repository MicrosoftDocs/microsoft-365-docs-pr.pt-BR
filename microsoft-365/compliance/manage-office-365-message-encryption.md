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
description: Depois de terminar de configurar o Criptografia de Mensagens do Office 365 (OME), saiba como personalizar sua implantação de várias maneiras.
ms.openlocfilehash: a2b3dde44ea541deb41eeb9d55d5ed745fa6c719
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "52650979"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="f6416-103">Gerenciar a Criptografia de Mensagens do Office 365</span><span class="sxs-lookup"><span data-stu-id="f6416-103">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="f6416-104">Depois de terminar de configurar o Criptografia de Mensagens do Office 365 (OME), você pode personalizar a configuração da sua implantação de várias maneiras.</span><span class="sxs-lookup"><span data-stu-id="f6416-104">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="f6416-105">Por exemplo, você pode configurar se deve habilitar códigos de passagem única, exibir o botão **Criptografar** Outlook na Web e muito mais.</span><span class="sxs-lookup"><span data-stu-id="f6416-105">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="f6416-106">As tarefas deste artigo descrevem como.</span><span class="sxs-lookup"><span data-stu-id="f6416-106">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="f6416-107">Gerenciar se os destinatários da Conta do Google, do Yahoo e da Microsoft podem usar essas contas para entrar no Criptografia de Mensagens do Office 365 portal</span><span class="sxs-lookup"><span data-stu-id="f6416-107">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="f6416-108">Quando você configura os novos recursos de Criptografia de Mensagens do Office 365, os usuários em sua organização podem enviar mensagens para destinatários que estão fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f6416-108">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your organization.</span></span> <span data-ttu-id="f6416-109">Se o destinatário usar uma *ID social,* como uma conta do Google, uma conta do Yahoo ou uma conta da Microsoft, o destinatário poderá entrar no portal OME com uma ID social.</span><span class="sxs-lookup"><span data-stu-id="f6416-109">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="f6416-110">Se quiser, você pode optar por não permitir que os destinatários usem IDs sociais para entrar no portal OME.</span><span class="sxs-lookup"><span data-stu-id="f6416-110">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="f6416-111">Para gerenciar se os destinatários podem usar IDs sociais para entrar no portal OME</span><span class="sxs-lookup"><span data-stu-id="f6416-111">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="f6416-112">[Conexão usar Exchange Online PowerShell Remoto.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="f6416-112">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f6416-113">Execute o cmdlet Set-OMEConfiguration com o parâmetro SocialIdSignIn da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="f6416-113">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="f6416-114">Por exemplo, para desabilitar IDs sociais:</span><span class="sxs-lookup"><span data-stu-id="f6416-114">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="f6416-115">Para habilitar IDs sociais:</span><span class="sxs-lookup"><span data-stu-id="f6416-115">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="f6416-116">Gerenciar o uso de códigos de passagem única para o Criptografia de Mensagens do Office 365 portal</span><span class="sxs-lookup"><span data-stu-id="f6416-116">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="f6416-117">Se o destinatário de uma mensagem criptografada pelo OME não usar Outlook, independentemente da conta usada pelo destinatário, o destinatário receberá um link de exibição da Web de tempo limitado que permite que ele leia a mensagem.</span><span class="sxs-lookup"><span data-stu-id="f6416-117">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="f6416-118">Este link inclui um código de passagem única.</span><span class="sxs-lookup"><span data-stu-id="f6416-118">This link includes a one-time pass code.</span></span> <span data-ttu-id="f6416-119">Como administrador, você pode decidir se os destinatários podem usar códigos de passagem única para entrar no portal OME.</span><span class="sxs-lookup"><span data-stu-id="f6416-119">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="f6416-120">Para gerenciar se o OME gera códigos de passagem única</span><span class="sxs-lookup"><span data-stu-id="f6416-120">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="f6416-121">Use uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização e inicie uma sessão de Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f6416-121">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="f6416-122">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f6416-122">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f6416-123">Execute o cmdlet Set-OMEConfiguration com o parâmetro OTPEnabled:</span><span class="sxs-lookup"><span data-stu-id="f6416-123">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="f6416-124">Por exemplo, para desabilitar códigos de passagem única:</span><span class="sxs-lookup"><span data-stu-id="f6416-124">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="f6416-125">Para habilitar códigos de passagem única:</span><span class="sxs-lookup"><span data-stu-id="f6416-125">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="f6416-126">Gerenciar a exibição do botão Criptografar Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="f6416-126">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="f6416-127">Como administrador, você pode gerenciar se deve exibir esse botão para usuários finais.</span><span class="sxs-lookup"><span data-stu-id="f6416-127">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="f6416-128">Para gerenciar se o botão Criptografar aparece Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="f6416-128">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="f6416-129">Use uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização e inicie uma sessão de Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f6416-129">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="f6416-130">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f6416-130">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f6416-131">Execute o cmdlet Set-IRMConfiguration com o parâmetro -SimplifiedClientAccessEnabled:</span><span class="sxs-lookup"><span data-stu-id="f6416-131">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="f6416-132">Por exemplo, para desabilitar o **botão Criptografar:**</span><span class="sxs-lookup"><span data-stu-id="f6416-132">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="f6416-133">Para habilitar **o botão Criptografar:**</span><span class="sxs-lookup"><span data-stu-id="f6416-133">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="f6416-134">Habilitar a descriptografia do lado do serviço de mensagens de email para usuários de aplicativos de email iOS</span><span class="sxs-lookup"><span data-stu-id="f6416-134">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="f6416-135">O aplicativo de email do iOS não pode descriptografar mensagens protegidas com Criptografia de Mensagens do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f6416-135">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="f6416-136">Como administrador Microsoft 365, você pode aplicar a descriptografia do lado do serviço para mensagens entregues ao aplicativo de email do iOS.</span><span class="sxs-lookup"><span data-stu-id="f6416-136">As a Microsoft 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="f6416-137">Quando você optar por usar a descriptografia do lado do serviço, o serviço envia uma cópia descriptografada da mensagem para o dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="f6416-137">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="f6416-138">O dispositivo cliente armazena uma cópia descriptografada da mensagem.</span><span class="sxs-lookup"><span data-stu-id="f6416-138">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="f6416-139">A mensagem também mantém informações sobre direitos de uso, mesmo que o aplicativo de email do iOS não aplique direitos de uso do lado do cliente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="f6416-139">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="f6416-140">O usuário pode copiar ou imprimir a mensagem mesmo que ele não tenha originalmente os direitos de fazê-lo.</span><span class="sxs-lookup"><span data-stu-id="f6416-140">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="f6416-141">No entanto, se o usuário tentar concluir uma ação que exija o servidor de email Microsoft 365, como encaminhar a mensagem, o servidor não permitirá a ação se o usuário originalmente não tiver o direito de uso para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="f6416-141">However, if the user attempts to complete an action that requires the Microsoft 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="f6416-142">No entanto, os usuários finais podem trabalhar em torno da restrição de uso "Não Encaminhar" encaminhando a mensagem de uma conta diferente dentro do aplicativo de email do iOS.</span><span class="sxs-lookup"><span data-stu-id="f6416-142">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="f6416-143">Independentemente de você configurar a descriptografia do lado do serviço de email, os anexos aos emails criptografados e protegidos por direitos não podem ser exibidos no aplicativo de email do iOS.</span><span class="sxs-lookup"><span data-stu-id="f6416-143">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="f6416-144">Se você optar por não permitir que mensagens descriptografadas sejam enviadas para usuários de aplicativos de email do iOS, os usuários receberão uma mensagem informando que não têm os direitos de exibição da mensagem.</span><span class="sxs-lookup"><span data-stu-id="f6416-144">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="f6416-145">Por padrão, a descriptografia do lado do serviço de mensagens de email não está habilitada.</span><span class="sxs-lookup"><span data-stu-id="f6416-145">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="f6416-146">Para obter mais informações e para obter uma visão da experiência do cliente, consulte Exibir mensagens criptografadas em seu iPhone [ou iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span><span class="sxs-lookup"><span data-stu-id="f6416-146">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="f6416-147">Para gerenciar se os usuários de aplicativos de email do iOS podem exibir mensagens protegidas por Criptografia de Mensagens do Office 365</span><span class="sxs-lookup"><span data-stu-id="f6416-147">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="f6416-148">Use uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização e inicie uma sessão de Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f6416-148">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="f6416-149">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f6416-149">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f6416-150">Execute o cmdlet Set-ActiveSyncOrganizations com o parâmetro AllowRMSSupportForUnenlightenedApps:</span><span class="sxs-lookup"><span data-stu-id="f6416-150">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="f6416-151">Por exemplo, para configurar o serviço para descriptografar mensagens antes que elas são enviadas para aplicativos sem iluminação, como o aplicativo de email do iOS:</span><span class="sxs-lookup"><span data-stu-id="f6416-151">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="f6416-152">Ou, para configurar o serviço para não enviar mensagens descriptografadas para aplicativos não criptografados:</span><span class="sxs-lookup"><span data-stu-id="f6416-152">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="f6416-153">As políticas de caixa de correio individuais (OWA/ActiveSync) substituem essas configurações (ou seja, se -IRMEnabled estiver definido como False na respectiva política de Caixa de Correio do OWA ou na política de Caixa de Correio ActiveSync, essas configurações não serão aplicadas).</span><span class="sxs-lookup"><span data-stu-id="f6416-153">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="f6416-154">Habilitar a descriptografia do lado do serviço de anexos de email para clientes de email do navegador da Web</span><span class="sxs-lookup"><span data-stu-id="f6416-154">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="f6416-155">Normalmente, quando você usa Office 365 de mensagens, os anexos são criptografados automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f6416-155">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="f6416-156">Como administrador, você pode aplicar a descriptografia do lado do serviço para anexos de email que os usuários baixam de um navegador da Web.</span><span class="sxs-lookup"><span data-stu-id="f6416-156">As an administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="f6416-157">Quando você usa a descriptografia do lado do serviço, o serviço envia uma cópia descriptografada do arquivo para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="f6416-157">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="f6416-158">A mensagem ainda está criptografada.</span><span class="sxs-lookup"><span data-stu-id="f6416-158">The message is still encrypted.</span></span> <span data-ttu-id="f6416-159">O anexo de email também mantém informações sobre direitos de uso, mesmo que o navegador não aplique direitos de uso do lado do cliente ao usuário.</span><span class="sxs-lookup"><span data-stu-id="f6416-159">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="f6416-160">O usuário pode copiar ou imprimir o anexo de email mesmo que ele não tenha originalmente os direitos de fazê-lo.</span><span class="sxs-lookup"><span data-stu-id="f6416-160">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="f6416-161">No entanto, se o usuário tentar concluir uma ação que exija o servidor de email Microsoft 365, como encaminhar o anexo, o servidor não permitirá a ação se o usuário originalmente não tiver o direito de uso para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="f6416-161">However, if the user tries to complete an action that requires the Microsoft 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="f6416-162">Independentemente de você configurar a descriptografia do lado do serviço de anexos, os usuários não podem exibir anexos para email criptografado e protegido por direitos no aplicativo de email do iOS.</span><span class="sxs-lookup"><span data-stu-id="f6416-162">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="f6416-163">Se você optar por não permitir anexos de email descriptografados, que é o padrão, os usuários receberão uma mensagem informando que eles não têm direitos para exibir o anexo.</span><span class="sxs-lookup"><span data-stu-id="f6416-163">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="f6416-164">Para obter mais informações sobre como Microsoft 365 a criptografia para emails e anexos de email com a opção Encrypt-Only, consulte [Encrypt-Only option for emails.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="f6416-164">For more information about how Microsoft 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="f6416-165">Para gerenciar se os anexos de email são descriptografados no download de um navegador da Web</span><span class="sxs-lookup"><span data-stu-id="f6416-165">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="f6416-166">Use uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização e inicie uma sessão de Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f6416-166">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="f6416-167">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f6416-167">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f6416-168">Execute o cmdlet Set-IRMConfiguration com o parâmetro DecryptAttachmentForEncryptOnly:</span><span class="sxs-lookup"><span data-stu-id="f6416-168">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentForEncryptOnly parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   <span data-ttu-id="f6416-169">Por exemplo, para configurar o serviço para descriptografar anexos de email quando um usuário os baixa de um navegador da Web:</span><span class="sxs-lookup"><span data-stu-id="f6416-169">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   <span data-ttu-id="f6416-170">Para configurar o serviço para deixar anexos de email criptografados como estão ao baixar:</span><span class="sxs-lookup"><span data-stu-id="f6416-170">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a><span data-ttu-id="f6416-171">Certifique-se de que todos os destinatários externos usem o Portal OME para ler emails criptografados</span><span class="sxs-lookup"><span data-stu-id="f6416-171">Ensure all external recipients use the OME Portal to read encrypted mail</span></span>

<span data-ttu-id="f6416-172">Você pode usar modelos de identidade visual personalizados para forçar os destinatários a receberem um email de wrapper que os direciona para ler emails criptografados no Portal OME em vez de usar Outlook ou Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="f6416-172">You can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="f6416-173">Talvez você queira fazer isso se quiser ter um controle maior sobre como os destinatários usam o email recebido.</span><span class="sxs-lookup"><span data-stu-id="f6416-173">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="f6416-174">Por exemplo, se destinatários externos exibirem emails no portal da Web, você poderá definir uma data de expiração para o email e revogar o email.</span><span class="sxs-lookup"><span data-stu-id="f6416-174">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="f6416-175">Esses recursos só são suportados por meio do Portal OME.</span><span class="sxs-lookup"><span data-stu-id="f6416-175">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="f6416-176">Você pode usar a opção Criptografar e a opção Não Encaminhar ao criar as regras de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="f6416-176">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a><span data-ttu-id="f6416-177">Use um modelo personalizado para forçar todos os destinatários externos a usar o Portal OME e para emails criptografados</span><span class="sxs-lookup"><span data-stu-id="f6416-177">Use a custom template to force all external recipients to use the OME Portal and for encrypted email</span></span>

1. <span data-ttu-id="f6416-178">Use uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização e inicie uma sessão de Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f6416-178">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="f6416-179">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f6416-179">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f6416-180">Execute o cmdlet New-TransportRule:</span><span class="sxs-lookup"><span data-stu-id="f6416-180">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="f6416-181">em que:</span><span class="sxs-lookup"><span data-stu-id="f6416-181">where:</span></span>

   - <span data-ttu-id="f6416-182">`mail flow rule name` é o nome que você deseja usar para a nova regra de fluxo de emails.</span><span class="sxs-lookup"><span data-stu-id="f6416-182">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="f6416-183">`option name` é ou `Encrypt` `Do Not Forward` .</span><span class="sxs-lookup"><span data-stu-id="f6416-183">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="f6416-184">`template name` é o nome que você deu ao modelo de identidade visual personalizado, por exemplo `OME Configuration` .</span><span class="sxs-lookup"><span data-stu-id="f6416-184">`template name` is the name you gave the custom branding template, for example `OME Configuration`.</span></span>

   <span data-ttu-id="f6416-185">Para criptografar todos os emails externos com o modelo "Configuração OME" e aplicar a Encrypt-Only opção:</span><span class="sxs-lookup"><span data-stu-id="f6416-185">To encrypt all external email with the "OME Configuration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   <span data-ttu-id="f6416-186">Para criptografar todos os emails externos com o modelo "Configuração OME" e aplicar a opção Não Encaminhar:</span><span class="sxs-lookup"><span data-stu-id="f6416-186">To encrypt all external email with the "OME Configuration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="f6416-187">Personalizar a aparência de mensagens de email e o portal OME</span><span class="sxs-lookup"><span data-stu-id="f6416-187">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="f6416-188">Para obter informações detalhadas sobre como personalizar o OME para sua organização, consulte Add your [organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="f6416-188">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="f6416-189">Desabilitar os novos recursos para OME</span><span class="sxs-lookup"><span data-stu-id="f6416-189">Disable the new capabilities for OME</span></span>

<span data-ttu-id="f6416-190">Esperamos que isso não seja possível, mas, se você precisar, desabilitar os novos recursos para OME é muito simples.</span><span class="sxs-lookup"><span data-stu-id="f6416-190">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="f6416-191">Primeiro, você precisará remover todas as regras de fluxo de emails criadas que usem os novos recursos OME.</span><span class="sxs-lookup"><span data-stu-id="f6416-191">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="f6416-192">Para obter informações sobre como remover regras de fluxo de emails, consulte [Manage mail flow rules](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="f6416-192">For information about removing mail flow rules, see [Manage mail flow rules](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span> <span data-ttu-id="f6416-193">Em seguida, conclua estas etapas Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6416-193">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="f6416-194">Para desabilitar os novos recursos do OME</span><span class="sxs-lookup"><span data-stu-id="f6416-194">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="f6416-195">Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, inicie uma sessão de Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f6416-195">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="f6416-196">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f6416-196">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="f6416-197">Se você habilitar o botão **Criptografar** Outlook na Web, desabilite-o executando o cmdlet Set-IRMConfiguration com o parâmetro SimplifiedClientAccessEnabled.</span><span class="sxs-lookup"><span data-stu-id="f6416-197">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="f6416-198">Caso contrário, ignore esta etapa.</span><span class="sxs-lookup"><span data-stu-id="f6416-198">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="f6416-199">Desabilite os novos recursos para OME executando o cmdlet Set-IRMConfiguration com o parâmetro AzureRMSLicensingEnabled definido como false:</span><span class="sxs-lookup"><span data-stu-id="f6416-199">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
