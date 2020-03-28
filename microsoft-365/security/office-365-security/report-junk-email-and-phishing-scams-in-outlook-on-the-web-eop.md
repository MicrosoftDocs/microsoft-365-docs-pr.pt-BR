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
description: Os usuários do Office 365 com caixas de correio do Exchange Online podem usar o Outlook na Web (Outlook Web App) para enviar mensagens de spam, não spam e phishing para a Microsoft para análise.
ms.openlocfilehash: c6aba9a701b23be4bbbe508825a55c6438461928
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033669"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-office-365"></a><span data-ttu-id="75fd3-103">Relatar emails de lixo eletrônico e phishing no Outlook na Web no Office 365</span><span class="sxs-lookup"><span data-stu-id="75fd3-103">Report junk and phishing email in Outlook on the web in Office 365</span></span>

<span data-ttu-id="75fd3-104">Se você for um cliente do Office 365 com caixas de correio do Exchange Online, você pode usar as opções de relatório internas no Outlook na Web (anteriormente conhecido como Outlook Web App) para enviar falsos positivos (emails em boas condições marcados como spam), falsos negativos (emails inválidos) e mensagens de phishing para o Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="75fd3-104">If you're an Office 365 customer with Exchange Online mailboxes, you can use the built-in reporting options in Outlook on the web (formerly known as Outlook Web App) to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="75fd3-105">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="75fd3-105">What do you need to know before you begin?</span></span>

- <span data-ttu-id="75fd3-106">Se você for um administrador em uma organização do Office 365 com caixas de correio do Exchange Online, recomendamos que você use o portal de envios no centro de conformidade & segurança do Office 365.</span><span class="sxs-lookup"><span data-stu-id="75fd3-106">If you're an admin in an Office 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="75fd3-107">Para obter mais informações, consulte [usar o envio do administrador para enviar spam, phishing, URLs e arquivos suspeitos à Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="75fd3-107">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="75fd3-108">Os administradores podem desabilitar ou habilitar a capacidade de os usuários reportarem mensagens para a Microsoft no Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="75fd3-108">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="75fd3-109">Para obter detalhes, consulte a seção [desabilitar ou habilitar relatórios de lixo eletrônico no Outlook na Web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="75fd3-109">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this topic.</span></span>

- <span data-ttu-id="75fd3-110">Para obter mais informações sobre como relatar mensagens à Microsoft, consulte [relatar mensagens e arquivos para a Microsoft no Office 365](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="75fd3-110">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a><span data-ttu-id="75fd3-111">Relatar mensagens de spam e phishing no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="75fd3-111">Report spam and phishing messages in Outlook on the web</span></span>

1. <span data-ttu-id="75fd3-112">Para mensagens na caixa de entrada ou em qualquer outra pasta de email, exceto lixo eletrônico, use um dos seguintes métodos para relatar mensagens de spam e phishing:</span><span class="sxs-lookup"><span data-stu-id="75fd3-112">For messages in the Inbox or any other email folder except Junk Email, use either of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="75fd3-113">Selecione a mensagem, clique em **lixo eletrônico** na barra de ferramentas e selecione **lixo eletrônico** ou **phishing**.</span><span class="sxs-lookup"><span data-stu-id="75fd3-113">Select the message, click **Junk** on the toolbar, and then select **Junk** or **Phishing**.</span></span>

     ![Relatar emails de lixo eletrônico ou phishing da faixa de opções](../../media/owa-report-junk.png)

   - <span data-ttu-id="75fd3-115">Selecione uma ou mais mensagens, clique com o botão direito do mouse e selecione **Marcar como lixo eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="75fd3-115">Select one or more messages, right-click, and then select **Mark as junk**.</span></span>

2. <span data-ttu-id="75fd3-116">Na caixa de diálogo exibida, clique em **relatório**.</span><span class="sxs-lookup"><span data-stu-id="75fd3-116">In the dialog that appears, click **Report**.</span></span> <span data-ttu-id="75fd3-117">Se você mudar de ideia, clique em **não relatar**.</span><span class="sxs-lookup"><span data-stu-id="75fd3-117">If you change your mind, click **Don't Report**.</span></span>

   ![Caixa de diálogo relatar como lixo eletrônico](../../media/owa-report-as-junk-dialog.png)

   ![Caixa de diálogo relatar como phishing](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="75fd3-120">As mensagens selecionadas serão enviadas para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="75fd3-120">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="75fd3-121">Para confirmar se as mensagens foram enviadas, abra sua pasta **Itens Enviados** para exibir as mensagens enviadas.</span><span class="sxs-lookup"><span data-stu-id="75fd3-121">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a><span data-ttu-id="75fd3-122">Relatar mensagens que não são spam e phishing da pasta lixo eletrônico no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="75fd3-122">Report non-spam and phishing messages from the Junk Email folder in Outlook on the web</span></span>

1. <span data-ttu-id="75fd3-123">Na pasta lixo eletrônico, use um dos seguintes métodos para relatar falsos positivos de spam ou mensagens de phishing:</span><span class="sxs-lookup"><span data-stu-id="75fd3-123">In the Junk Email folder, use either of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="75fd3-124">Selecione a mensagem, clique em **não lixo eletrônico** na barra de ferramentas e selecione **não lixo eletrônico** ou **phishing**.</span><span class="sxs-lookup"><span data-stu-id="75fd3-124">Select the message, click **Not Junk** on the toolbar, and then select **Not Junk** or **Phishing**.</span></span>

     ![Relatar emails de lixo eletrônico ou phishing da faixa de opções](../../media/owa-report-not-junk.png)

   - <span data-ttu-id="75fd3-126">Selecione uma ou mais mensagens, clique com o botão direito do mouse e selecione **Marcar como não sendo lixo eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="75fd3-126">Select one or more messages, right-click, and then select **Mark as not junk**.</span></span>

2. <span data-ttu-id="75fd3-127">Na caixa de diálogo exibida, leia as informações e clique em **relatório**.</span><span class="sxs-lookup"><span data-stu-id="75fd3-127">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="75fd3-128">Se você mudar de ideia, clique em **não relatar**.</span><span class="sxs-lookup"><span data-stu-id="75fd3-128">If you change your mind, click **Don't Report**.</span></span>

   ![Relatar como não sendo lixo eletrônico](../../media/owa-report-as-not-junk-dialog.png)

   ![Caixa de diálogo relatar como phishing](../../media/owa-report-as-phishing-dialog.png)

3. <span data-ttu-id="75fd3-131">As mensagens selecionadas serão enviadas para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="75fd3-131">The selected messages will be sent to Microsoft for analysis.</span></span> <span data-ttu-id="75fd3-132">Para confirmar se as mensagens foram enviadas, abra sua pasta **Itens Enviados** para exibir as mensagens enviadas.</span><span class="sxs-lookup"><span data-stu-id="75fd3-132">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="75fd3-133">Desabilitar ou habilitar os relatórios de lixo eletrônico no Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="75fd3-133">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="75fd3-134">Por padrão, os usuários podem relatar falsos positivos de spam, falsos negativos e mensagens de phishing para a Microsoft para análise no Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="75fd3-134">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="75fd3-135">Os administradores podem usar as políticas de caixa de correio da Web do Outlook no Exchange Online para desabilitar ou habilitar essa capacidade, mas somente no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="75fd3-135">Admins can use Outlook on the web mailbox policies in Exchange Online to disable or enable this ability, but only in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="75fd3-136">Para se conectar ao Exchange Online PowerShell, consulte [Conectar ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="75fd3-136">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="75fd3-137">Você precisa receber permissões para executar esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="75fd3-137">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="75fd3-138">Especificamente, você precisa das funções de **Recipient** ou de **destinatários de email** no Exchange Online, que são atribuídas aos grupos de funções de gerenciamento de **destinatários** e de **Gerenciamento da organização** por padrão.</span><span class="sxs-lookup"><span data-stu-id="75fd3-138">Specifically you need the **Recipient Policies** or **Mail Recipients** roles in Exchange Online, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="75fd3-139">Para obter mais informações sobre grupos de função no Exchange Online, consulte [modificar grupos de função no Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="75fd3-139">For more information about role groups in Exchange Online, see [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="75fd3-140">Cada organização tem uma política padrão chamada OwaMailboxPolicy-padrão, mas você pode criar políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="75fd3-140">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="75fd3-141">Políticas personalizadas são aplicadas a usuários com escopo antes da política padrão.</span><span class="sxs-lookup"><span data-stu-id="75fd3-141">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="75fd3-142">Para obter mais informações sobre o Outlook nas políticas de caixa de correio da Web, consulte [Outlook na Web políticas de caixa de correio no Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span><span class="sxs-lookup"><span data-stu-id="75fd3-142">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

1. <span data-ttu-id="75fd3-143">Para localizar suas políticas de caixa de correio do Outlook na Web e o status do relatório de lixo eletrônico, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="75fd3-143">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="75fd3-144">Para desabilitar ou habilitar os relatórios de lixo eletrônico no Outlook na Web, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="75fd3-144">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="75fd3-145">Este exemplo desabilita os relatórios de lixo eletrônico na política padrão.</span><span class="sxs-lookup"><span data-stu-id="75fd3-145">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="75fd3-146">Este exemplo habilitou o relatório de lixo eletrônico na política personalizada chamada gerentes da contoso.</span><span class="sxs-lookup"><span data-stu-id="75fd3-146">This example enabled junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="75fd3-147">Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) e [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="75fd3-147">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="75fd3-148">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="75fd3-148">How do you know this worked?</span></span>

<span data-ttu-id="75fd3-149">Para verificar se você habilitou ou desabilitou com êxito os relatórios de lixo eletrônico no Outlook na Web, use uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="75fd3-149">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="75fd3-150">No PowerShell do Exchange Online, execute o seguinte comando e verifique o valor da propriedade **ReportJunkEmailEnabled** :</span><span class="sxs-lookup"><span data-stu-id="75fd3-150">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="75fd3-151">Abra a caixa de correio de um usuário afetado no Outlook na Web e verifique se as opções para relatar mensagens de lixo eletrônico, não lixo eletrônico e phishing estão disponíveis ou não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="75fd3-151">Open an affected user's mailbox in Outlook on the web, and verify the options to report junk, not junk, and phishing messages are available or not available.</span></span> <span data-ttu-id="75fd3-152">Observe que o usuário ainda pode marcar mensagens como lixo eletrônico, phishing e não lixo eletrônico, mas o usuário não pode relatá-las para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75fd3-152">Note that the user can still mark messages as junk, phishing, and not junk, but the user can't report them to Microsoft.</span></span>
