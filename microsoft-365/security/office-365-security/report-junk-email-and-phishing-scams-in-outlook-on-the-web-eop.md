---
title: 'Relatar lixo eletrônico e esquemas de phishing no Outlook na Web '
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Os usuários do Microsoft 365 com caixas de correio do Exchange Online podem usar o Outlook na Web (Outlook Web App) para enviar mensagens de spam, não spam e phishing para a Microsoft para análise.
ms.openlocfilehash: 9fc17abafe219a450e0fb6e45438211ea03fb337
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2020
ms.locfileid: "43921475"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-office-365"></a><span data-ttu-id="2cb47-103">Relatar emails de lixo eletrônico e phishing no Outlook na Web no Office 365</span><span class="sxs-lookup"><span data-stu-id="2cb47-103">Report junk and phishing email in Outlook on the web in Office 365</span></span>

<span data-ttu-id="2cb47-104">Se você for um cliente do Microsoft 365 com caixas de correio do Exchange Online, você pode usar as opções de relatório internas no Outlook na Web (anteriormente conhecido como Outlook Web App) para enviar falsos positivos (emails em boas condições marcados como spam), falsos negativos (email incorreto) e mensagens de phishing para o Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="2cb47-104">If you're a Microsoft 365 customer with Exchange Online mailboxes, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2cb47-105">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="2cb47-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2cb47-106">Se você for um administrador em uma organização com caixas de correio do Exchange Online, recomendamos que você use o portal de envios no centro de conformidade do & de segurança.</span><span class="sxs-lookup"><span data-stu-id="2cb47-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="2cb47-107">Para obter mais informações, consulte [usar o envio do administrador para enviar spam, phishing, URLs e arquivos suspeitos à Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="2cb47-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="2cb47-108">Os administradores podem desabilitar ou habilitar a capacidade de os usuários reportarem mensagens para a Microsoft no Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="2cb47-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="2cb47-109">Para obter detalhes, consulte a seção [desabilitar ou habilitar relatórios de lixo eletrônico no Outlook na Web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="2cb47-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="2cb47-110">Você pode configurar mensagens relatadas para serem copiadas ou redirecionadas para uma caixa de correio que você especificar.</span><span class="sxs-lookup"><span data-stu-id="2cb47-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="2cb47-111">Para obter mais informações, consulte [especificar uma caixa de correio para envios de emails de spam e mensagens de phishing no Office 365](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="2cb47-111">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Office 365](user-submission.md).</span></span>

- <span data-ttu-id="2cb47-112">Para obter mais informações sobre como relatar mensagens à Microsoft, consulte [relatar mensagens e arquivos para a Microsoft no Office 365](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="2cb47-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="2cb47-113">Relatar mensagens de spam e phishing no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="2cb47-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="2cb47-114">Para mensagens na caixa de entrada ou em qualquer outra pasta de email, exceto lixo eletrônico, use um dos seguintes métodos para relatar mensagens de spam e phishing:</span><span class="sxs-lookup"><span data-stu-id="2cb47-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="2cb47-115">Selecione a mensagem, clique em **lixo eletrônico** na barra de ferramentas e selecione **lixo eletrônico** ou **phishing**.</span><span class="sxs-lookup"><span data-stu-id="2cb47-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Relatar emails de lixo eletrônico ou phishing da faixa de opções](../../media/owa-report-junk.png)

   - <span data-ttu-id="2cb47-117">Selecione uma ou mais mensagens, clique com o botão direito do mouse e selecione **Marcar como lixo eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="2cb47-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="2cb47-118">Na caixa de diálogo exibida, clique em **relatório**.</span><span class="sxs-lookup"><span data-stu-id="2cb47-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="2cb47-119">Se você mudar de ideia, clique em **não relatar**.</span><span class="sxs-lookup"><span data-stu-id="2cb47-119">If you change your mind, click **Don't Report**.</span></span>

   ![Caixa de diálogo relatar como lixo eletrônico](../../media/owa-report-as-junk-dialog.png)

   ![Caixa de diálogo relatar como phishing](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="2cb47-122">As mensagens selecionadas serão enviadas para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="2cb47-122">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="2cb47-123">Para confirmar se as mensagens foram enviadas, abra sua pasta **Itens Enviados** para exibir as mensagens enviadas.</span><span class="sxs-lookup"><span data-stu-id="2cb47-123">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="2cb47-124">Relatar mensagens que não são spam e phishing da pasta lixo eletrônico no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="2cb47-124">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="2cb47-125">Na pasta lixo eletrônico, use um dos seguintes métodos para relatar falsos positivos de spam ou mensagens de phishing:</span><span class="sxs-lookup"><span data-stu-id="2cb47-125">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="2cb47-126">Selecione a mensagem, clique em **não lixo eletrônico** na barra de ferramentas e selecione **não lixo eletrônico** ou **phishing**.</span><span class="sxs-lookup"><span data-stu-id="2cb47-126">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Relatar emails de lixo eletrônico ou phishing da faixa de opções](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="2cb47-128">Selecione uma ou mais mensagens, clique com o botão direito do mouse e selecione **Marcar como não sendo lixo eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="2cb47-128">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="2cb47-129">Na caixa de diálogo exibida, leia as informações e clique em **relatório**.</span><span class="sxs-lookup"><span data-stu-id="2cb47-129">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="2cb47-130">Se você mudar de ideia, clique em **não relatar**.</span><span class="sxs-lookup"><span data-stu-id="2cb47-130">If you change your mind, click **Don't Report**.</span></span>

   ![Relatar como não sendo lixo eletrônico](../../media/owa-report-as-not-junk-dialog.png)

   ![Caixa de diálogo relatar como phishing](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="2cb47-133">As mensagens selecionadas serão enviadas para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="2cb47-133">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="2cb47-134">Para confirmar se as mensagens foram enviadas, abra sua pasta **Itens Enviados** para exibir as mensagens enviadas.</span><span class="sxs-lookup"><span data-stu-id="2cb47-134">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="2cb47-135">Desabilitar ou habilitar os relatórios de lixo eletrônico no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="2cb47-135">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="2cb47-136">Por padrão, os usuários podem relatar falsos positivos de spam, falsos negativos e mensagens de phishing para a Microsoft para análise no Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="2cb47-136">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="2cb47-137">Os administradores podem configurar o Outlook nas políticas de caixa de correio da Web no PowerShell do Exchange Online para impedir que os usuários reportem falsos positivos e falsos negativos de spam para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2cb47-137">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="2cb47-138">Não é possível desabilitar a capacidade de os usuários reportarem mensagens de phishing para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2cb47-138">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2cb47-139">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="2cb47-139">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2cb47-140">Para se conectar ao Exchange Online PowerShell, consulte [Conectar ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2cb47-140">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="2cb47-141">Você precisa receber permissões para executar esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="2cb47-141">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="2cb47-142">Especificamente, você precisa das funções de **Recipient** ou de **destinatários de email** no Exchange Online, que são atribuídas aos grupos de funções de gerenciamento de **destinatários** e de **Gerenciamento da organização** por padrão.</span><span class="sxs-lookup"><span data-stu-id="2cb47-142">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="2cb47-143">Para obter mais informações sobre grupos de função no Exchange Online, consulte [modificar grupos de função no Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="2cb47-143">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="2cb47-144">Cada organização tem uma política padrão chamada OwaMailboxPolicy-padrão, mas você pode criar políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="2cb47-144">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="2cb47-145">Políticas personalizadas são aplicadas a usuários com escopo antes da política padrão.</span><span class="sxs-lookup"><span data-stu-id="2cb47-145">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="2cb47-146">Para obter mais informações sobre o Outlook nas políticas de caixa de correio da Web, consulte [Outlook na Web políticas de caixa de correio no Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span><span class="sxs-lookup"><span data-stu-id="2cb47-146">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="2cb47-147">Desabilitar o relatório de lixo eletrônico não remove a capacidade de marcar uma mensagem como lixo eletrônico ou não lixo eletrônico no Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="2cb47-147">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="2cb47-148">Selecionar uma mensagem na pasta lixo eletrônico e clicar em **não é lixo** \> eletrônico ainda **não** move a mensagem de volta para a caixa de entrada.</span><span class="sxs-lookup"><span data-stu-id="2cb47-148">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="2cb47-149">Selecionar uma mensagem em qualquer outra pasta de email e clicar em **lixo** \> **eletrônico ainda move** a mensagem para a pasta lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="2cb47-149">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="2cb47-150">O que não está mais disponível é a opção de relatar a mensagem à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2cb47-150">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="2cb47-151">Usar o PowerShell do Exchange Online para desabilitar ou habilitar relatórios de lixo eletrônico no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="2cb47-151">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="2cb47-152">Para localizar suas políticas de caixa de correio do Outlook na Web e o status do relatório de lixo eletrônico, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2cb47-152">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="2cb47-153">Para desabilitar ou habilitar os relatórios de lixo eletrônico no Outlook na Web, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="2cb47-153">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="2cb47-154">Este exemplo desabilita os relatórios de lixo eletrônico na política padrão.</span><span class="sxs-lookup"><span data-stu-id="2cb47-154">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="2cb47-155">Este exemplo habilita o envio de relatórios de lixo eletrônico na política personalizada chamada gerentes da contoso.</span><span class="sxs-lookup"><span data-stu-id="2cb47-155">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="2cb47-156">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) e [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="2cb47-156">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="2cb47-157">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="2cb47-157">How do you know this worked?</span></span>

<span data-ttu-id="2cb47-158">Para verificar se você habilitou ou desabilitou com êxito os relatórios de lixo eletrônico no Outlook na Web, use uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="2cb47-158">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="2cb47-159">No PowerShell do Exchange Online, execute o seguinte comando e verifique o valor da propriedade **ReportJunkEmailEnabled** :</span><span class="sxs-lookup"><span data-stu-id="2cb47-159">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="2cb47-160">Abra a caixa de correio de um usuário afetado no Outlook na Web, selecione uma mensagem na caixa de entrada, clique em **lixo** \> **eletrônico** e verifique se o aviso para relatar a mensagem à Microsoft é ou não é exibido.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cb47-160">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="2cb47-161">Abra a caixa de correio de um usuário afetado no Outlook na Web, selecione uma mensagem na pasta lixo eletrônico, clique em **lixo** \> **eletrônico e verifique** se o aviso para relatar a mensagem à Microsoft é ou não é exibido.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="2cb47-161">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="2cb47-162"><sup>\*</sup>Os usuários podem ocultar a solicitação para relatar a mensagem enquanto estiver relatando a mensagem.</span><span class="sxs-lookup"><span data-stu-id="2cb47-162"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="2cb47-163">Para verificar essa configuração no Outlook na Web:</span><span class="sxs-lookup"><span data-stu-id="2cb47-163">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="2cb47-164">Clique **em configurações** ![do Outlook no ícone](../../media/owa-settings-icon.png) \> configurações da Web **Exibir todas as configurações** \> do Outlook **lixo eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="2cb47-164">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="2cb47-165">Na seção **relatório** , verifique o valor: **perguntar antes de enviar um relatório**.</span><span class="sxs-lookup"><span data-stu-id="2cb47-165">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Configurações de relatório de lixo eletrônico do Outlook na Web](../../media/owa-junk-email-reporting-options.png)
