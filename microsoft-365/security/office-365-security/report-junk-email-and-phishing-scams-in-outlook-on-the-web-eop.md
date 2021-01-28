---
title: Relatar lixo eletrônico e phishing no Outlook na Web
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
description: Os administradores podem aprender sobre as opções internas de relatório de lixo eletrônico, não lixo eletrônico e phishing no Outlook na Web (Outlook Web App) no Exchange Online e como desabilitar essas opções de relatório para usuários.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0af57aceed608ae80e72e3ae18724925c1168e26
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029205"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="c3c36-103">Relatar lixo eletrônico e phishing no Outlook na Web no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c3c36-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c3c36-104">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online, você pode usar as opções internas de relatório no Outlook na Web (anteriormente conhecido como Outlook Web App) para enviar falsos positivos (emails bons marcados como spam), falsos negativos (emails falsos permitidos) e mensagens de phishing para o Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="c3c36-104">In Microsoft 365 organizations with mailboxes in Exchange Online, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c3c36-105">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="c3c36-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c3c36-106">Se você for um administrador em uma organização com caixas de correio do Exchange Online, recomendamos usar o portal de Envios no Centro de Conformidade e Segurança & Segurança.</span><span class="sxs-lookup"><span data-stu-id="c3c36-106">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="c3c36-107">Para obter mais informações, consulte Usar o Envio de Administrador [para enviar spam, phishing, URLs e arquivos suspeitos para a Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="c3c36-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="c3c36-108">Os administradores podem desabilitar ou habilitar a capacidade dos usuários de relatar mensagens à Microsoft no Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="c3c36-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="c3c36-109">Para obter detalhes, consulte [a seção Desabilitar](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) ou habilitar o relatório de lixo eletrônico no Outlook na Web posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c3c36-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="c3c36-110">Você pode configurar mensagens relatadas para serem copiadas ou redirecionadas para uma caixa de correio que você especificar.</span><span class="sxs-lookup"><span data-stu-id="c3c36-110">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="c3c36-111">Para obter mais informações, consulte [Políticas de envios de usuário.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="c3c36-111">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="c3c36-112">Para obter mais informações sobre como relatar mensagens à Microsoft, consulte [Mensagens e arquivos de relatório para a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="c3c36-112">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="c3c36-113">Relatar mensagens de spam e phishing no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="c3c36-113">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="c3c36-114">Para mensagens na Caixa de Entrada ou em qualquer outra pasta de email, exceto Lixo Eletrônico, use um dos métodos a seguir para relatar mensagens de spam e phishing:</span><span class="sxs-lookup"><span data-stu-id="c3c36-114">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="c3c36-115">Selecione a mensagem, clique **em Lixo** Eletrônico na barra de ferramentas e selecione **Lixo Eletrônico** ou **Phishing.**</span><span class="sxs-lookup"><span data-stu-id="c3c36-115">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Relatar lixo eletrônico ou email de phishing da faixa de opções](../../media/owa-report-junk.png)

   - <span data-ttu-id="c3c36-117">Selecione uma ou mais mensagens, clique com o botão direito do mouse e selecione **Marcar como lixo eletrônico.**</span><span class="sxs-lookup"><span data-stu-id="c3c36-117">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="c3c36-118">Na caixa de diálogo exibida, clique em **Relatório.**</span><span class="sxs-lookup"><span data-stu-id="c3c36-118">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="c3c36-119">Se você mudar de ideia, clique **em Não Relatar.**</span><span class="sxs-lookup"><span data-stu-id="c3c36-119">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="c3c36-120">Lixo eletrônico</span><span class="sxs-lookup"><span data-stu-id="c3c36-120">Junk</span></span>|<span data-ttu-id="c3c36-121">Phishing</span><span class="sxs-lookup"><span data-stu-id="c3c36-121">Phishing</span></span>|
   |:---:|:---:|
   |![Relatar como caixa de diálogo lixo eletrônico](../../media/owa-report-as-junk-dialog.png)|![Relatar como caixa de diálogo de phishing](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="c3c36-124">As mensagens selecionadas serão enviadas à Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="c3c36-124">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="c3c36-125">Para confirmar se as mensagens foram enviadas, abra sua pasta **Itens Enviados** para exibir as mensagens enviadas.</span><span class="sxs-lookup"><span data-stu-id="c3c36-125">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="c3c36-126">Relatar mensagens de não spam e phishing da pasta Lixo Eletrônico no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="c3c36-126">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="c3c36-127">Na pasta Lixo Eletrônico, use um dos métodos a seguir para relatar falsos positivos de spam ou mensagens de phishing:</span><span class="sxs-lookup"><span data-stu-id="c3c36-127">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="c3c36-128">Selecione a mensagem, clique **em Não é Lixo** Eletrônico na barra de ferramentas e selecione Não é Lixo **Eletrônico** ou **Phishing.**</span><span class="sxs-lookup"><span data-stu-id="c3c36-128">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Relatar não lixo eletrônico ou não phishing na faixa de opções](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="c3c36-130">Selecione uma ou mais mensagens, clique com o botão direito do mouse e selecione **Marcar como não sendo lixo eletrônico.**</span><span class="sxs-lookup"><span data-stu-id="c3c36-130">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="c3c36-131">Na caixa de diálogo exibida, leia as informações e clique em **Relatório.**</span><span class="sxs-lookup"><span data-stu-id="c3c36-131">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="c3c36-132">Se você mudar de ideia, clique **em Não Relatar.**</span><span class="sxs-lookup"><span data-stu-id="c3c36-132">If you change your mind, click **Don't Report**.</span></span>

   |<span data-ttu-id="c3c36-133">Não é Lixo Eletrônico</span><span class="sxs-lookup"><span data-stu-id="c3c36-133">Not Junk</span></span>|<span data-ttu-id="c3c36-134">Phishing</span><span class="sxs-lookup"><span data-stu-id="c3c36-134">Phishing</span></span>|
   |:---:|:---:|
   |![Relatar como não é uma caixa de diálogo de lixo eletrônico](../../media/owa-report-as-not-junk-dialog.png)|![Relatar como caixa de diálogo de phishing](../../media/owa-report-as-phishing-dialog.png)|

3. <span data-ttu-id="c3c36-137">As mensagens selecionadas serão enviadas à Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="c3c36-137">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="c3c36-138">Para confirmar se as mensagens foram enviadas, abra sua pasta **Itens Enviados** para exibir as mensagens enviadas.</span><span class="sxs-lookup"><span data-stu-id="c3c36-138">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="c3c36-139">Desabilitar ou habilitar relatórios de lixo eletrônico no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="c3c36-139">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="c3c36-140">Por padrão, os usuários podem relatar falsos positivos de spam, falsos negativos e mensagens de phishing à Microsoft para análise no Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="c3c36-140">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="c3c36-141">Os administradores podem configurar as políticas de caixa de correio do Outlook na Web no PowerShell do Exchange Online para impedir que os usuários reportem falsos positivos e falsos negativos de spam para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c3c36-141">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="c3c36-142">Não é possível desabilitar a capacidade dos usuários relatarem mensagens de phishing à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c3c36-142">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c3c36-143">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="c3c36-143">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c3c36-144">Para se conectar ao Windows PowerShell do Exchange Online, confira [Conectar ao Windows PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c3c36-144">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="c3c36-145">Você precisa ter permissões no Exchange Online para poder fazer os procedimentos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c3c36-145">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="c3c36-146">Especificamente, você precisa das **funções Políticas** de Destinatário ou  Destinatários  de Email, que são **atribuídas** aos grupos de função Gerenciamento da Organização e Gerenciamento de Destinatários por padrão.</span><span class="sxs-lookup"><span data-stu-id="c3c36-146">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="c3c36-147">Para obter mais informações sobre grupos de função no Exchange Online, consulte Permissões no [Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) e modificar grupos de função no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="c3c36-147">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="c3c36-148">Cada organização tem uma política padrão chamada OwaMailboxPolicy-Default, mas você pode criar políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="c3c36-148">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="c3c36-149">As políticas personalizadas são aplicadas a usuários com escopo antes da política padrão.</span><span class="sxs-lookup"><span data-stu-id="c3c36-149">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="c3c36-150">Para saber mais sobre as políticas de caixa de correio do Outlook na Web, confira as políticas de caixa de correio do Outlook na [Web no Exchange Online.](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)</span><span class="sxs-lookup"><span data-stu-id="c3c36-150">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="c3c36-151">Desabilitar o relatório de lixo eletrônico não remove a capacidade de marcar uma mensagem como lixo eletrônico ou não no Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="c3c36-151">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="c3c36-152">Selecionar uma mensagem na pasta Lixo eletrônico e clicar em **Não** é lixo eletrônico Ainda move a mensagem de volta para a \>  Caixa de Entrada.</span><span class="sxs-lookup"><span data-stu-id="c3c36-152">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="c3c36-153">Selecionar uma mensagem em qualquer outra pasta de email e clicar em **Lixo** Eletrônico ainda move a mensagem \>  para a pasta Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="c3c36-153">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="c3c36-154">O que não está mais disponível é a opção de relatar a mensagem à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c3c36-154">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="c3c36-155">Usar o PowerShell do Exchange Online para desabilitar ou habilitar relatórios de lixo eletrônico no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="c3c36-155">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="c3c36-156">Para encontrar as políticas de caixa de correio existentes do Outlook na Web e o status do relatório de lixo eletrônico, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c3c36-156">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="c3c36-157">Para desabilitar ou habilitar o relatório de lixo eletrônico no Outlook na Web, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c3c36-157">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="c3c36-158">Este exemplo desabilita o relatório de lixo eletrônico na política padrão.</span><span class="sxs-lookup"><span data-stu-id="c3c36-158">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="c3c36-159">Este exemplo habilita o relatório de lixo eletrônico na política personalizada denominada Gerentes da Contoso.</span><span class="sxs-lookup"><span data-stu-id="c3c36-159">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="c3c36-160">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) e [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="c3c36-160">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c3c36-161">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="c3c36-161">How do you know this worked?</span></span>

<span data-ttu-id="c3c36-162">Para verificar se você habilitar ou desabilitar com êxito os relatórios de lixo eletrônico no Outlook na Web, use uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c3c36-162">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="c3c36-163">No PowerShell do Exchange Online, execute o seguinte comando e verifique o valor da propriedade **ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="c3c36-163">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="c3c36-164">Abra a caixa de correio de um usuário afetado no Outlook  na Web, selecione uma mensagem na Caixa de Entrada, clique em Lixo Eletrônico e verifique se o prompt para relatar a mensagem à Microsoft é ou não \>  exibido.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c3c36-164">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="c3c36-165">Abra a caixa de correio de um usuário afetado no Outlook na  Web, selecione uma mensagem na pasta Lixo Eletrônico, clique em Lixo Eletrônico e verifique se o prompt para relatar a mensagem à Microsoft é ou não \>  exibido.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c3c36-165">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="c3c36-166"><sup>\*</sup> Os usuários podem ocultar o prompt para relatar a mensagem enquanto ainda relatam a mensagem.</span><span class="sxs-lookup"><span data-stu-id="c3c36-166"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="c3c36-167">Para verificar essa configuração no Outlook na Web:</span><span class="sxs-lookup"><span data-stu-id="c3c36-167">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="c3c36-168">Click **Settings** ![ Outlook on the web settings icon View all Outlook ](../../media/owa-settings-icon.png) \> **settings** Junk \> **email**.</span><span class="sxs-lookup"><span data-stu-id="c3c36-168">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="c3c36-169">Na seção **Relatórios,** verifique o valor: **Pergunte-me antes de enviar um relatório.**</span><span class="sxs-lookup"><span data-stu-id="c3c36-169">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Configurações de Relatório de Lixo Eletrônico do Outlook na Web](../../media/owa-junk-email-reporting-options.png)
