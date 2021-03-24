---
title: Relatar lixo eletrônico e email de phishing no Outlook na Web
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender sobre as opções de relatório de lixo eletrônico, não lixo eletrônico e phishing no Outlook na Web (Outlook Web App) no Exchange Online e como desabilitar essas opções de relatórios para usuários.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77a1233b85ad213091ac84ac6f7e8eb93d9145af
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054127"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="36977-103">Relatar lixo eletrônico e email de phishing no Outlook na Web no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="36977-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="36977-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="36977-104">**Applies to**</span></span>
- [<span data-ttu-id="36977-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="36977-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="36977-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="36977-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="36977-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36977-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="36977-108">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online, você pode usar as opções internas de relatório no Outlook na Web (anteriormente conhecido como Outlook Web App) para enviar falsos positivos (emails bons marcados como spam), falsos negativos (email ruim permitido) e mensagens de phishing para o Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="36977-108">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="36977-109">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="36977-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="36977-110">Se você for um administrador em uma organização com caixas de correio do Exchange Online, recomendamos que você use o portal Envios no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="36977-110">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="36977-111">Para obter mais informações, [consulte Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="36977-111">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="36977-112">Os administradores podem desabilitar ou habilitar a capacidade de os usuários relatarem mensagens à Microsoft no Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="36977-112">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="36977-113">Para obter detalhes, consulte [a seção Desabilitar ou](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) habilitar relatórios de lixo eletrônico no Outlook na Web posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="36977-113">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="36977-114">Você pode configurar mensagens relatadas a serem copiadas ou redirecionadas para uma caixa de correio especificada.</span><span class="sxs-lookup"><span data-stu-id="36977-114">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="36977-115">Para obter mais informações, consulte [Políticas de envios de usuário](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="36977-115">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="36977-116">Para obter mais informações sobre o relatório de mensagens para a Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="36977-116">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="36977-117">Relatar mensagens de spam e phishing no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="36977-117">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="36977-118">Para mensagens na Caixa de Entrada ou em qualquer outra pasta de email, exceto Lixo Eletrônico, use um dos seguintes métodos para relatar mensagens de spam e phishing:</span><span class="sxs-lookup"><span data-stu-id="36977-118">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="36977-119">Selecione a mensagem, clique **em Lixo** Eletrônico na barra de ferramentas e selecione **Lixo Eletrônico** ou **Phishing**.</span><span class="sxs-lookup"><span data-stu-id="36977-119">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Relatar lixo eletrônico ou email de phishing da faixa de opções](../../media/owa-report-junk.png)

   - <span data-ttu-id="36977-121">Selecione uma ou mais mensagens, clique com o botão direito do mouse e selecione **Marcar como lixo eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="36977-121">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="36977-122">Na caixa de diálogo exibida, clique em **Relatório**.</span><span class="sxs-lookup"><span data-stu-id="36977-122">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="36977-123">Se você mudar de ideia, clique **em Não Relatar**.</span><span class="sxs-lookup"><span data-stu-id="36977-123">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="36977-124">Lixo eletrônico</span><span class="sxs-lookup"><span data-stu-id="36977-124">Junk</span></span>|<span data-ttu-id="36977-125">Phishing</span><span class="sxs-lookup"><span data-stu-id="36977-125">Phishing</span></span>|
   |:---:|:---:|
   |![Relatório como caixa de diálogo lixo eletrônico](../../media/owa-report-as-junk-dialog.png)|![Relatar como caixa de diálogo de phishing](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="36977-128">As mensagens selecionadas serão enviadas à Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="36977-128">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="36977-129">Para confirmar se as mensagens foram enviadas, abra sua pasta **Itens Enviados** para exibir as mensagens enviadas.</span><span class="sxs-lookup"><span data-stu-id="36977-129">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="36977-130">Relatar mensagens de não spam e phishing da pasta Lixo Eletrônico no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="36977-130">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="36977-131">Na pasta Lixo Eletrônico, use um dos seguintes métodos para relatar falsos positivos de spam ou mensagens de phishing:</span><span class="sxs-lookup"><span data-stu-id="36977-131">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="36977-132">Selecione a mensagem, clique em **Não Lixo** Eletrônico na barra de ferramentas e selecione **Não Lixo Eletrônico** ou **Phishing**.</span><span class="sxs-lookup"><span data-stu-id="36977-132">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Relatar não lixo eletrônico ou não enviar emails de phishing da faixa de opções](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="36977-134">Selecione uma ou mais mensagens, clique com o botão direito do mouse e selecione **Marcar como não lixo eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="36977-134">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="36977-135">Na caixa de diálogo exibida, leia as informações e clique em **Relatar**.</span><span class="sxs-lookup"><span data-stu-id="36977-135">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="36977-136">Se você mudar de ideia, clique **em Não Relatar**.</span><span class="sxs-lookup"><span data-stu-id="36977-136">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="36977-137">Não Lixo Eletrônico</span><span class="sxs-lookup"><span data-stu-id="36977-137">Not Junk</span></span>|<span data-ttu-id="36977-138">Phishing</span><span class="sxs-lookup"><span data-stu-id="36977-138">Phishing</span></span>|
   |:---:|:---:|
   |![Relatar como não caixa de diálogo lixo eletrônico](../../media/owa-report-as-not-junk-dialog.png)|![Relatar como caixa de diálogo de phishing](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="36977-141">As mensagens selecionadas serão enviadas à Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="36977-141">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="36977-142">Para confirmar se as mensagens foram enviadas, abra sua pasta **Itens Enviados** para exibir as mensagens enviadas.</span><span class="sxs-lookup"><span data-stu-id="36977-142">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="36977-143">Desabilitar ou habilitar relatórios de lixo eletrônico no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="36977-143">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="36977-144">Por padrão, os usuários podem relatar falsos positivos de spam, falsos negativos e mensagens de phishing para a Microsoft para análise no Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="36977-144">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="36977-145">Os administradores podem configurar as políticas de caixa de correio do Outlook na Web no PowerShell do Exchange Online para impedir que os usuários reportem falsos positivos de spam e falsos negativos de spam para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="36977-145">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="36977-146">Não é possível desabilitar a capacidade de os usuários relatarem mensagens de phishing à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="36977-146">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="36977-147">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="36977-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="36977-148">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="36977-148">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="36977-149">Você precisa ter permissões atribuídas no Exchange Online antes de poder fazer os procedimentos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="36977-149">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="36977-150">Especificamente, você precisa das **funções Políticas** de Destinatário ou  Destinatários  de Email, que são **atribuídas** aos grupos de função Gerenciamento da Organização e Gerenciamento de Destinatários por padrão.</span><span class="sxs-lookup"><span data-stu-id="36977-150">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="36977-151">Para obter mais informações sobre grupos de função no Exchange Online, consulte [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo) e Modificar grupos de função no Exchange [Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="36977-151">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="36977-152">Cada organização tem uma política padrão chamada OwaMailboxPolicy-Default, mas você pode criar políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="36977-152">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="36977-153">Políticas personalizadas são aplicadas a usuários com escopo antes da política padrão.</span><span class="sxs-lookup"><span data-stu-id="36977-153">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="36977-154">Para obter mais informações sobre as políticas de caixa de correio da Web do [Outlook,](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)consulte Outlook on the Web mailbox policies in Exchange Online .</span><span class="sxs-lookup"><span data-stu-id="36977-154">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="36977-155">Desabilitar relatórios de lixo eletrônico não remove a capacidade de marcar uma mensagem como lixo eletrônico ou não lixo eletrônico no Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="36977-155">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="36977-156">Selecionar uma mensagem na pasta Lixo Eletrônico e clicar em Não lixo **eletrônico** Não lixo eletrônico ainda move a mensagem de \>  volta para a Caixa de Entrada.</span><span class="sxs-lookup"><span data-stu-id="36977-156">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="36977-157">Selecionar uma mensagem em qualquer outra pasta de email e clicar em **Lixo** Eletrônico ainda move a mensagem \>  para a pasta Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="36977-157">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="36977-158">O que não está mais disponível é a opção de relatar a mensagem à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="36977-158">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="36977-159">Usar o PowerShell do Exchange Online para desabilitar ou habilitar relatórios de lixo eletrônico no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="36977-159">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="36977-160">Para encontrar seu Outlook existente nas políticas de caixa de correio da Web e o status do relatório de lixo eletrônico, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="36977-160">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="36977-161">Para desabilitar ou habilitar relatórios de lixo eletrônico no Outlook na Web, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="36977-161">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="36977-162">Este exemplo desabilita o relatório de lixo eletrônico na política padrão.</span><span class="sxs-lookup"><span data-stu-id="36977-162">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="36977-163">Este exemplo habilita o relatório de lixo eletrônico na política personalizada denominada Gerentes da Contoso.</span><span class="sxs-lookup"><span data-stu-id="36977-163">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="36977-164">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) e [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="36977-164">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="36977-165">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="36977-165">How do you know this worked?</span></span>

<span data-ttu-id="36977-166">Para verificar se você habilitar ou desabilitar com êxito o relatório de lixo eletrônico no Outlook na Web, use qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="36977-166">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="36977-167">No PowerShell do Exchange Online, execute o seguinte comando e verifique o valor da propriedade **ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="36977-167">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="36977-168">Abra a caixa de correio de um usuário afetado no Outlook  na Web, selecione uma mensagem na Caixa de Entrada, clique em Lixo Eletrônico e verifique se o prompt para relatar a mensagem à Microsoft é ou não \>  exibido.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="36977-168">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="36977-169">Abra a caixa de correio de um usuário afetado no Outlook na  Web, selecione uma mensagem na pasta Lixo Eletrônico, clique em Lixo Eletrônico e verifique se o prompt para relatar a mensagem à Microsoft é ou não \>  exibido.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="36977-169">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="36977-170"><sup>\*</sup> Os usuários podem ocultar o prompt para relatar a mensagem enquanto ainda relatam a mensagem.</span><span class="sxs-lookup"><span data-stu-id="36977-170"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="36977-171">Para verificar essa configuração no Outlook na Web:</span><span class="sxs-lookup"><span data-stu-id="36977-171">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="36977-172">Clique **em Configurações** ![ Do Outlook no ícone de configurações da Web ](../../media/owa-settings-icon.png) \> **Exibir todas as configurações do Outlook** \> **Lixo eletrônico.**</span><span class="sxs-lookup"><span data-stu-id="36977-172">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="36977-173">Na seção **Relatórios,** verifique o valor: **Pergunte-me antes de enviar um relatório**.</span><span class="sxs-lookup"><span data-stu-id="36977-173">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Configurações do Relatório de Lixo Eletrônico do Outlook na Web](../../media/owa-junk-email-reporting-options.png)