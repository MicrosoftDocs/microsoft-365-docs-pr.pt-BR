---
title: Instalar e usar o suplemento relatório de lixo eletrônico para o Microsoft Outlook
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
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Saiba como instalar e usar o suplemento relatório de lixo eletrônico da Microsoft para relatar mensagens de spam, não spam e phishing à Microsoft.
ms.openlocfilehash: e39fb2f4ecba806c2d26d989fbbe6ddec137adc1
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033863"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook-in-office-365"></a><span data-ttu-id="f2ce9-103">Instalar e usar o suplemento relatório de lixo eletrônico para o Microsoft Outlook no Office 365</span><span class="sxs-lookup"><span data-stu-id="f2ce9-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook in Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="f2ce9-104">Se você não estiver usando o suplemento relatório de lixo eletrônico, recomendamos o [suplemento mensagem de relatório](enable-the-report-message-add-in.md) .</span><span class="sxs-lookup"><span data-stu-id="f2ce9-104">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) instead.</span></span>

<span data-ttu-id="f2ce9-105">O suplemento relatório de lixo eletrônico do Microsoft Outlook permite que os usuários enviem falsos positivos (bons emails marcados como spam), falsos negativos (emails inválidos) e mensagens de phishing para o Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="f2ce9-105">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Exchange Online Protection (EOP).</span></span> <span data-ttu-id="f2ce9-106">Se sua organização não usa o EOP, seu envio de relatório de lixo eletrônico não afetará a filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-106">If your organization doesn't use EOP, your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="f2ce9-107">Este tópico explica como instalar e usar o suplemento relatório de lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-107">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f2ce9-108">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="f2ce9-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f2ce9-109">Para instalar o suplemento relatório de lixo eletrônico, confira a seção [instalar o suplemento relatório de lixo eletrônico](#install-the-junk-email-reporting-add-in) mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-109">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this topic.</span></span>

- <span data-ttu-id="f2ce9-110">O suplemento relatório de lixo eletrônico funciona com as seguintes versões do Outlook:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-110">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="f2ce9-111">Outlook 2013 ou posterior</span><span class="sxs-lookup"><span data-stu-id="f2ce9-111">Outlook 2013 or later</span></span>
  - <span data-ttu-id="f2ce9-112">Outlook incluído no Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="f2ce9-112">Outlook included with Office 365 ProPlus</span></span>

- <span data-ttu-id="f2ce9-113">Para obter mais informações sobre como relatar mensagens à Microsoft, consulte [relatar mensagens e arquivos para a Microsoft no Office 365](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="f2ce9-113">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft in Office 365](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="f2ce9-114">Usar o suplemento relatório de lixo eletrônico para relatar mensagens de spam e phishing</span><span class="sxs-lookup"><span data-stu-id="f2ce9-114">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="f2ce9-115">Para mensagens na caixa de entrada ou em qualquer outra pasta de email, exceto lixo eletrônico, use qualquer um dos seguintes métodos para relatar mensagens de spam e phishing:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-115">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="f2ce9-116">Selecione a mensagem ou abra a mensagem.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-116">Select the message or open the message.</span></span> <span data-ttu-id="f2ce9-117">Na guia **página inicial** ou **mensagem** na faixa de opções, clique em **lixo eletrônico**e selecione **relatar como lixo eletrônico** ou **relatório como phishing**.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-117">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Relatar emails de lixo eletrônico ou phishing da faixa de opções](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="f2ce9-119">Clique com o botão direito do mouse na mensagem, selecione **lixo eletrônico**e, em seguida, selecione **relatar como lixo eletrônico** ou **relatório como phishing**.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-119">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Relatar emails de lixo eletrônico ou phishing do clique com o botão direito](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="f2ce9-121">Selecione várias mensagens, clique com o botão direito do mouse e selecione **relatar como lixo eletrônico** ou **relatório como phishing**.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-121">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Relatar várias mensagens de email de spam ou phishing do clique com o botão direito](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="f2ce9-123">Na caixa de diálogo exibida, leia as informações e clique em **relatório**.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-123">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="f2ce9-124">Se você mudar de ideia, clique em **não relatar**.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-124">If you change your mind, click **Don't Report**.</span></span>

   ![Caixa de diálogo relatar como lixo eletrônico](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Caixa de diálogo relatar como phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="f2ce9-p104">As mensagens selecionadas serão enviadas à Microsoft para análise e movidas para a pasta Lixo Eletrônico. Para confirmar se as mensagens foram enviadas, abra sua pasta **Itens Enviados** para exibir as mensagens enviadas.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-p104">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder. To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="f2ce9-129">Use o suplemento relatório de lixo eletrônico para relatar mensagens que não são spam e phishing da pasta lixo eletrônico</span><span class="sxs-lookup"><span data-stu-id="f2ce9-129">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="f2ce9-130">Na pasta lixo eletrônico, use qualquer um dos seguintes métodos para relatar falsos positivos de spam ou mensagens de phishing:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-130">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="f2ce9-131">Selecione a mensagem ou abra a mensagem.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-131">Select the message or open the message.</span></span> <span data-ttu-id="f2ce9-132">Na guia **página inicial** ou de **mensagem** na faixa de opções, clique em **não lixo eletrônico**e selecione **relatar como não lixo eletrônico** ou **relatar como phishing**.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-132">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Relatar não é lixo eletrônico ou email de phishing da faixa de opções na pasta lixo eletrônico](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="f2ce9-134">Clique com o botão direito do mouse na mensagem, clique em **lixo eletrônico**e selecione **relatar como não lixo eletrônico** ou **relatar como phishing**.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-134">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Relatar emails não spam ou phishing do clique com o botão direito na pasta lixo eletrônico](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="f2ce9-136">Selecione várias mensagens, clique com o botão direito do mouse e selecione **relatar como não é lixo eletrônico** ou **relatar como phishing**.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-136">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Relatar várias mensagens de email de não lixo eletrônico ou phishing do clique com o botão direito na pasta lixo eletrônico](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="f2ce9-138">Na caixa de diálogo exibida, leia as informações e clique em **relatório**.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-138">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="f2ce9-139">Se você mudar de ideia, clique em **não relatar**.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-139">If you change your mind, click **Don't Report**.</span></span>

   ![Relatar como não sendo lixo eletrônico](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Caixa de diálogo relatar como phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="f2ce9-p107">As mensagens selecionadas serão enviadas à Microsoft para análise e movidas para a pasta Lixo Eletrônico. Para confirmar se as mensagens foram enviadas, abra sua pasta **Itens Enviados** para exibir as mensagens enviadas.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-p107">The selected messages will be sent to Microsoft for analysis and moved to the Junk Email folder. To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="f2ce9-144">Instalar o suplemento relatório de lixo eletrônico</span><span class="sxs-lookup"><span data-stu-id="f2ce9-144">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="f2ce9-145">Você precisa ter privilégios de administrador no computador no qual você está instalando o suplemento.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-145">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="f2ce9-146">Vá para <https://www.microsoft.com/download/details.aspx?id=18275> e baixe o arquivo. msi apropriado para sua versão do Office para um local que seja fácil de encontrar:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-146">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="f2ce9-147">**32**bits:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="f2ce9-147">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="f2ce9-148">**64**bits:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="f2ce9-148">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="f2ce9-149">Para o Outlook 2013 ou posterior, o único pré-requisito é o Microsoft .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-149">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="f2ce9-150">No Windows 10, você não instala o .NET Framework 2,0 a partir de um download.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-150">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="f2ce9-151">Instalar o suplemento de relatório de lixo eletrônico usando o assistente de configuração</span><span class="sxs-lookup"><span data-stu-id="f2ce9-151">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="f2ce9-152">Feche o Outlook no computador.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-152">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="f2ce9-153">No Windows 10, verifique se o .NET Framework 2,0 está habilitado.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-153">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="f2ce9-154">Para obter instruções, consulte [habilitar o .NET Framework 3,5 no painel de controle](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span><span class="sxs-lookup"><span data-stu-id="f2ce9-154">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="f2ce9-155">Localize o arquivo. msi que você baixou e clique duas vezes nele.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-155">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="f2ce9-156">Na página **Bem-vindo à Configuração do Suplemento Relatório de Lixo Eletrônico para Microsoft** e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-156">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="f2ce9-157">Revise o contrato de licença, clique em **aceito os termos do contrato de licença** se você concordar com os termos e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-157">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="f2ce9-158">Quando o assistente for concluído, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-158">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="f2ce9-159">Inicie o Outlook.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-159">Start Outlook.</span></span>

<span data-ttu-id="f2ce9-p110">Procure o botão **Lixo Eletrônico** na faixa de opções do Outlook. Agora, você pode relatar mensagens de lixo eletrônico à Microsoft selecionando-as na sua Caixa de Entrada e clicando no botão **Relatar Lixo Eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-p110">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="f2ce9-p111">Selecione a seta para baixo ao lado de **Lixo Eletrônico** para obter mais opções, como **Relatar como Phishing** se você quiser relatar emails de esquemas de phishing para a Microsoft. Na pasta Lixo Eletrônico, você também pode selecionar, **Relatar como não sendo lixo eletrônico** se um email tiver sido identificado incorretamente como lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-p111">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="f2ce9-164">Instalar o Suplemento Relatório de Lixo Eletrônico usando Modo Silencioso</span><span class="sxs-lookup"><span data-stu-id="f2ce9-164">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="f2ce9-165">Feche o Outlook no computador.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-165">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="f2ce9-166">No Windows 10, instale o .NET Framework 2,0 executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-166">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="f2ce9-167">Para instalar o suplemento sem qualquer interação do usuário, abra um prompt de comando e use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-167">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="f2ce9-168">`MaxMessageSelection`Especifica o número máximo de mensagens que você pode selecionar para um único envio.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-168">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="f2ce9-169">Os valores válidos vão de 1 a 50.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-169">Valid values are from 1 to 50.</span></span> <span data-ttu-id="f2ce9-170">O valor padrão é 15.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-170">The default value is 15.</span></span>

   - <span data-ttu-id="f2ce9-171">`BccEmailAddress`Especifica destinatários Cco adicionais que receberão uma cópia de todos os envios de usuários.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-171">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="f2ce9-172">O valor padrão é Blank (nenhum destinatário adicional Cco).</span><span class="sxs-lookup"><span data-stu-id="f2ce9-172">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="f2ce9-173">Este exemplo instala a versão de 64 bits do suplemento do caminho especificado com as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-173">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="f2ce9-174">Este exemplo instala a versão de 32 bits do suplemento do caminho especificado com as seguintes configurações adicionais:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-174">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="f2ce9-175">Até 20 mensagens podem ser selecionadas em um único envio.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-175">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="f2ce9-176">junkreports@contoso.com e hollyd@treyresearch.net recebem cópias Cco de todos os envios.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-176">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f2ce9-177">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="f2ce9-177">How do you know this worked?</span></span>

<span data-ttu-id="f2ce9-178">Para verificar se você instalou com êxito o suplemento relatório de lixo eletrônico, execute qualquer uma das seguintes etapas no Outlook:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-178">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="f2ce9-179">Selecione a mensagem ou abra a mensagem.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-179">Select the message or open the message.</span></span> <span data-ttu-id="f2ce9-180">Na guia **página inicial** ou de **mensagem** na faixa de opções, clique em **lixo eletrônico**e verifique se as seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-180">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="f2ce9-181">**Relatar como lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="f2ce9-181">**Report as Junk**</span></span>
  - <span data-ttu-id="f2ce9-182">**Relatar como phishing**</span><span class="sxs-lookup"><span data-stu-id="f2ce9-182">**Report as Phishing**</span></span>
  - <span data-ttu-id="f2ce9-183">**Opções de relatório de lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="f2ce9-183">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="f2ce9-184">**Relatar a ajuda online do lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="f2ce9-184">**Report Junk Online Help**</span></span>

  ![Relatar emails de lixo eletrônico ou phishing da faixa de opções](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="f2ce9-186">Clique com o botão direito do mouse na mensagem, selecione **lixo eletrônico**e verifique se as seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-186">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="f2ce9-187">**Relatar como lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="f2ce9-187">**Report as Junk**</span></span>
  - <span data-ttu-id="f2ce9-188">**Relatar como phishing**</span><span class="sxs-lookup"><span data-stu-id="f2ce9-188">**Report as Phishing**</span></span>
  - <span data-ttu-id="f2ce9-189">**Opções de relatório de lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="f2ce9-189">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="f2ce9-190">**Relatar a ajuda online do lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="f2ce9-190">**Report Junk Online Help**</span></span>

  ![Relatar emails de lixo eletrônico ou phishing do clique com o botão direito](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="f2ce9-192">Selecione várias mensagens, clique com o botão direito do mouse e verifique se as seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-192">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="f2ce9-193">**Relatar como lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="f2ce9-193">**Report as Junk**</span></span>
  - <span data-ttu-id="f2ce9-194">**Relatar como phishing**</span><span class="sxs-lookup"><span data-stu-id="f2ce9-194">**Report as Phishing**</span></span>

  ![Relatar várias mensagens de email de spam ou phishing do clique com o botão direito](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="f2ce9-196">Execute as ações anteriores na pasta **lixo eletrônico** e verifique se as opções anteriores de relatório de **lixo eletrônico** **não são lixo eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-196">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Relatar não é lixo eletrônico ou email de phishing da faixa de opções na pasta lixo eletrônico](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Relatar emails não spam ou phishing do clique com o botão direito na pasta lixo eletrônico](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Relatar várias mensagens de email de não lixo eletrônico ou phishing do clique com o botão direito na pasta lixo eletrônico](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="f2ce9-200">Desinstalar o Suplemento Relatório de Lixo Eletrônico</span><span class="sxs-lookup"><span data-stu-id="f2ce9-200">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="f2ce9-201">Após fechar o Outlook, use qualquer um dos seguintes procedimentos para desinstalar o suplemento relatório de lixo eletrônico:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-201">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="f2ce9-202">**Painel de controle**: Pressione a tecla Windows + R. Na caixa de diálogo **executar** que é aberta `control appwiz.cpl` , insira e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-202">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="f2ce9-203">Localize e selecione o **suplemento relatório de lixo eletrônico da Microsoft** na lista e clique em **desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-203">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="f2ce9-204">**Pacote do Windows Installer**: encontre ou baixe o arquivo. msi apropriado e clique duas vezes nele.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-204">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="f2ce9-205">**32**bits:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="f2ce9-205">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="f2ce9-206">**64**bits:`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="f2ce9-206">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="f2ce9-207">Na caixa de diálogo exibida, selecione **remover suplemento relatório de lixo eletrônico da Microsoft para Outlook** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-207">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="f2ce9-208">**Modo silencioso**: encontre ou baixe o arquivo. msi apropriado.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-208">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="f2ce9-209">Em uma janela de prompt de comando \<,\> substitua PathToFile pelo local do arquivo. msi e execute um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-209">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="f2ce9-210">**32**bits:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-210">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="f2ce9-211">**64**bits:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-211">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="f2ce9-212">Quando você abre o Outlook após a desinstalação, as opções de relatório de lixo eletrônico, não lixo eletrônico e phishing devem ser despercebidas.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-212">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="f2ce9-213">Solucionando problemas do suplemento relatório de lixo eletrônico</span><span class="sxs-lookup"><span data-stu-id="f2ce9-213">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="f2ce9-214">Ocasionalmente, você pode enfrentar problemas com o Outlook após adicionar o suplemento de relatório de lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-214">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="f2ce9-215">Esta seção descreve os problemas que você pode encontrar, juntamente com as dicas para resolver esses problemas.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-215">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="f2ce9-216">Solucionando problemas de usuários</span><span class="sxs-lookup"><span data-stu-id="f2ce9-216">Troubleshooting for users</span></span>

<span data-ttu-id="f2ce9-217">Você enfrenta um ou mais dos seguintes problemas:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-217">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="f2ce9-218">Nada acontece quando você clica em **Relatar Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="f2ce9-218">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="f2ce9-219">O Outlook para de responder depois que você selecionar uma mensagem de email</span><span class="sxs-lookup"><span data-stu-id="f2ce9-219">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="f2ce9-220">O lixo eletrônico relatado não pode ser entregue devido a uma resposta "não entregue"</span><span class="sxs-lookup"><span data-stu-id="f2ce9-220">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="f2ce9-221">Para corrigir esse problema, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-221">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="f2ce9-222">Feche e reinicie o Outlook.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-222">Close and restart Outlook.</span></span>
2. <span data-ttu-id="f2ce9-223">Criar e enviar uma mensagem de teste e verificar se o destinatário recebeu a mensagem.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-223">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="f2ce9-224">Se o problema persistir, entre em contato com seu administrador.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-224">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="f2ce9-225">Para outros métodos que você pode usar para enviar mensagens à Microsoft, confira [mensagens de relatório e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="f2ce9-225">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="f2ce9-226">Solucionando problemas de administradores</span><span class="sxs-lookup"><span data-stu-id="f2ce9-226">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="f2ce9-227">Problema: uma mensagem de erro é exibida continuamente solicitando que os usuários entrem em contato com o administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="f2ce9-227">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="f2ce9-228">Verifique ou defina a `LoggingLevel` chave do registro com o valor "Verbose":</span><span class="sxs-lookup"><span data-stu-id="f2ce9-228">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="f2ce9-229">o **Outlook de 32 bits em Windows de 32 bits**:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-229">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="f2ce9-230">o **Outlook de 32 bits em Windows de 64 bits**:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-230">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="f2ce9-231">**64-bit Outlook**:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-231">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="f2ce9-232">Reinicie o Outlook e peça aos usuários para reportá-los quando eles verão a mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-232">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="f2ce9-233">Colete as informações de log encontradas no seguinte local:</span><span class="sxs-lookup"><span data-stu-id="f2ce9-233">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="f2ce9-234">Entre em contato com o suporte técnico do Exchange Online Protection e forneça as informações de log.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-234">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="f2ce9-235">Problema: os usuários optaram por não receber um prompt de confirmação ao relatar mensagens e agora eles querem retornar o prompt</span><span class="sxs-lookup"><span data-stu-id="f2ce9-235">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="f2ce9-236">Crie a `ConfirmReportJunk`chave do registro wih o valor "true":</span><span class="sxs-lookup"><span data-stu-id="f2ce9-236">Create the `ConfirmReportJunk`registry key wih the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="f2ce9-237">Reinicie o Outlook.</span><span class="sxs-lookup"><span data-stu-id="f2ce9-237">Restart Outlook.</span></span>
