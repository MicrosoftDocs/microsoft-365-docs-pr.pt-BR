---
title: Instalar e usar o complemento Relatório de Lixo Eletrônico para o Microsoft Outlook
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Saiba como instalar e usar o complemento Relatório de Lixo Eletrônico da Microsoft para relatar mensagens de spam, não spam e phishing para a Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 171bdc43e565a0890cddcd1e48208b49774a5315
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167342"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="8209c-103">Instalar e usar o complemento Relatório de Lixo Eletrônico para o Microsoft Outlook</span><span class="sxs-lookup"><span data-stu-id="8209c-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="8209c-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="8209c-104">**Applies to**</span></span>
- [<span data-ttu-id="8209c-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8209c-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="8209c-106">Microsoft Defender para Office 365 plano 1 e plano 2</span><span class="sxs-lookup"><span data-stu-id="8209c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="8209c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8209c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!NOTE]
> <span data-ttu-id="8209c-108">Se você não estiver usando o complemento Relatório de Lixo Eletrônico [](enable-the-report-message-add-in.md) no momento, recomendamos o complemento Mensagem de Relatório ou o complemento [De Phishing de](enable-the-report-phish-add-in.md) Relatório.</span><span class="sxs-lookup"><span data-stu-id="8209c-108">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) instead.</span></span> <span data-ttu-id="8209c-109">Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="8209c-109">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="8209c-110">O Complemento Relatório de Lixo Eletrônico do Microsoft Outlook permite que os usuários enviem falsos positivos (emails bons marcados como spam), falsos negativos (emails falsos permitidos) e mensagens de phishing para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8209c-110">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="8209c-111">Se sua organização não usa a Proteção do Exchange Online (por exemplo, serviços locais do Exchange ou de email que não seja o Exchange Online), seu envio de relatório de lixo eletrônico não afetará a filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="8209c-111">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="8209c-112">Este tópico explica como instalar e usar o complemento Relatório de Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="8209c-112">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8209c-113">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="8209c-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8209c-114">Para instalar o complemento Relatório de Lixo Eletrônico, consulte a seção Instalar o complemento Relatório de Lixo [Eletrônico](#install-the-junk-email-reporting-add-in) posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="8209c-114">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this article.</span></span>

- <span data-ttu-id="8209c-115">O complemento Relatório de Lixo Eletrônico funciona com as seguintes versões do Outlook:</span><span class="sxs-lookup"><span data-stu-id="8209c-115">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="8209c-116">Outlook 2013 ou posterior</span><span class="sxs-lookup"><span data-stu-id="8209c-116">Outlook 2013 or later</span></span>
  - <span data-ttu-id="8209c-117">Outlook incluído no Microsoft 365 Apps para empresas</span><span class="sxs-lookup"><span data-stu-id="8209c-117">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="8209c-118">Para obter mais informações sobre como relatar mensagens à Microsoft, consulte [Mensagens e arquivos de relatório para a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="8209c-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="8209c-119">Usar o complemento Relatório de Lixo Eletrônico para relatar mensagens de spam e phishing</span><span class="sxs-lookup"><span data-stu-id="8209c-119">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="8209c-120">Para mensagens na Caixa de Entrada ou em qualquer outra pasta de email, exceto Lixo Eletrônico, use um dos métodos a seguir para relatar mensagens de spam e phishing:</span><span class="sxs-lookup"><span data-stu-id="8209c-120">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="8209c-121">Selecione a mensagem ou abra a mensagem.</span><span class="sxs-lookup"><span data-stu-id="8209c-121">Select the message or open the message.</span></span> <span data-ttu-id="8209c-122">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select Report **as Junk** or Report **as Phishing**.</span><span class="sxs-lookup"><span data-stu-id="8209c-122">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Relatar lixo eletrônico ou email de phishing da faixa de opções](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="8209c-124">Clique com o botão direito do mouse na mensagem, selecione **Lixo** Eletrônico e selecione **Relatar como Lixo Eletrônico** ou Relatório como **Phishing.**</span><span class="sxs-lookup"><span data-stu-id="8209c-124">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Relatar lixo eletrônico ou email de phishing com o clique com o botão direito do mouse](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="8209c-126">Selecione várias mensagens, clique com o botão direito do mouse e selecione **Relatar como Lixo Eletrônico** ou Relatar como **Phishing.**</span><span class="sxs-lookup"><span data-stu-id="8209c-126">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Relatar várias mensagens de lixo eletrônico ou phishing clicando com o botão direito do mouse](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="8209c-128">Na caixa de diálogo exibida, leia as informações e clique em **Relatório.**</span><span class="sxs-lookup"><span data-stu-id="8209c-128">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="8209c-129">Se você mudar de ideia, clique **em Não Relatar.**</span><span class="sxs-lookup"><span data-stu-id="8209c-129">If you change your mind, click **Don't Report**.</span></span>

   ![Relatar como caixa de diálogo lixo eletrônico](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Relatar como caixa de diálogo de phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="8209c-132">As mensagens selecionadas serão enviadas à Microsoft para análise e:</span><span class="sxs-lookup"><span data-stu-id="8209c-132">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="8209c-133">Movido para a pasta Lixo Eletrônico se tiver sido relatado como spam.</span><span class="sxs-lookup"><span data-stu-id="8209c-133">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="8209c-134">Excluído se tiver sido relatado como phishing.</span><span class="sxs-lookup"><span data-stu-id="8209c-134">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="8209c-135">Para confirmar se as mensagens foram enviadas, abra sua pasta **Itens Enviados** para exibir as mensagens enviadas.</span><span class="sxs-lookup"><span data-stu-id="8209c-135">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="8209c-136">Usar o complemento Relatório de Lixo Eletrônico para relatar mensagens de não spam e phishing da pasta Lixo Eletrônico</span><span class="sxs-lookup"><span data-stu-id="8209c-136">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="8209c-137">Na pasta Lixo Eletrônico, use qualquer um dos métodos a seguir para relatar falsos positivos de spam ou mensagens de phishing:</span><span class="sxs-lookup"><span data-stu-id="8209c-137">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="8209c-138">Selecione a mensagem ou abra a mensagem.</span><span class="sxs-lookup"><span data-stu-id="8209c-138">Select the message or open the message.</span></span> <span data-ttu-id="8209c-139">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select Report as **Not Junk** or Report **as Phishing**.</span><span class="sxs-lookup"><span data-stu-id="8209c-139">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Relatar não lixo eletrônico ou email de phishing da faixa de opções na pasta Lixo Eletrônico](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="8209c-141">Clique com o botão direito do mouse na mensagem, clique em **Lixo** Eletrônico e selecione **Relatar como** Não é Lixo Eletrônico ou Relatar **como Phishing.**</span><span class="sxs-lookup"><span data-stu-id="8209c-141">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Relatar não lixo eletrônico ou email de phishing clicando com o botão direito do mouse na pasta Lixo Eletrônico](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="8209c-143">Selecione várias mensagens, clique com o botão direito do mouse e selecione **Relatar como** Não é Lixo Eletrônico ou Relatar **como Phishing.**</span><span class="sxs-lookup"><span data-stu-id="8209c-143">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Relatar várias mensagens de email que não são de lixo eletrônico ou phishing clicando com o botão direito do mouse na pasta Lixo Eletrônico](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="8209c-145">Na caixa de diálogo exibida, leia as informações e clique em **Relatório.**</span><span class="sxs-lookup"><span data-stu-id="8209c-145">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="8209c-146">Se você mudar de ideia, clique **em Não Relatar.**</span><span class="sxs-lookup"><span data-stu-id="8209c-146">If you change your mind, click **Don't Report**.</span></span>

   ![Relatar como não é uma caixa de diálogo de lixo eletrônico](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Relatar como caixa de diálogo de phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="8209c-149">As mensagens selecionadas serão enviadas à Microsoft para análise e:</span><span class="sxs-lookup"><span data-stu-id="8209c-149">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="8209c-150">Movido para a pasta Lixo Eletrônico se tiver sido relatado como spam.</span><span class="sxs-lookup"><span data-stu-id="8209c-150">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="8209c-151">Excluído se tiver sido relatado como phishing.</span><span class="sxs-lookup"><span data-stu-id="8209c-151">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="8209c-152">Para confirmar se as mensagens foram enviadas, abra sua pasta **Itens Enviados** para exibir as mensagens enviadas.</span><span class="sxs-lookup"><span data-stu-id="8209c-152">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="8209c-153">Instalar o complemento Relatório de Lixo Eletrônico</span><span class="sxs-lookup"><span data-stu-id="8209c-153">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="8209c-154">Você precisa ter privilégios de administrador no computador em que está instalando o complemento.</span><span class="sxs-lookup"><span data-stu-id="8209c-154">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="8209c-155">Acesse e baixe o arquivo .msi apropriado para sua versão do Office em um local fácil <https://www.microsoft.com/download/details.aspx?id=18275> de encontrar:</span><span class="sxs-lookup"><span data-stu-id="8209c-155">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="8209c-156">**32 bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="8209c-156">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="8209c-157">**64 bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="8209c-157">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="8209c-158">Para o Outlook 2013 ou posterior, o único pré-requisito é o Microsoft .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="8209c-158">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="8209c-159">No Windows 10, você não instala o .NET Framework 2.0 a partir de um download.</span><span class="sxs-lookup"><span data-stu-id="8209c-159">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="8209c-160">Instalar o Complemento Relatório de Lixo Eletrônico usando o Assistente de Configuração</span><span class="sxs-lookup"><span data-stu-id="8209c-160">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="8209c-161">Feche o Outlook no computador.</span><span class="sxs-lookup"><span data-stu-id="8209c-161">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="8209c-162">No Windows 10, verifique se o .NET Framework 2.0 está habilitado.</span><span class="sxs-lookup"><span data-stu-id="8209c-162">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="8209c-163">Para obter instruções, [consulte Habilitar o .NET Framework 3.5 no Painel de Controle.](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)</span><span class="sxs-lookup"><span data-stu-id="8209c-163">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="8209c-164">Localize o arquivo .msi baixado e clique duas vezes nele.</span><span class="sxs-lookup"><span data-stu-id="8209c-164">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="8209c-165">Na página **Bem-vindo à Configuração do Suplemento Relatório de Lixo Eletrônico para Microsoft** e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="8209c-165">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="8209c-166">Revise o contrato de licença, clique **em Aceitar os termos** do Contrato de Licença se concordar com os termos e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="8209c-166">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="8209c-167">Quando o assistente for concluído, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="8209c-167">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="8209c-168">Inicie o Outlook.</span><span class="sxs-lookup"><span data-stu-id="8209c-168">Start Outlook.</span></span>

<span data-ttu-id="8209c-p109">Procure o botão **Lixo Eletrônico** na faixa de opções do Outlook. Agora, você pode relatar mensagens de lixo eletrônico à Microsoft selecionando-as na sua Caixa de Entrada e clicando no botão **Relatar Lixo Eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="8209c-p109">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="8209c-p110">Selecione a seta para baixo ao lado de **Lixo Eletrônico** para obter mais opções, como **Relatar como Phishing** se você quiser relatar emails de esquemas de phishing para a Microsoft. Na pasta Lixo Eletrônico, você também pode selecionar, **Relatar como não sendo lixo eletrônico** se um email tiver sido identificado incorretamente como lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="8209c-p110">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="8209c-173">Instalar o Suplemento Relatório de Lixo Eletrônico usando Modo Silencioso</span><span class="sxs-lookup"><span data-stu-id="8209c-173">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="8209c-174">Feche o Outlook no computador.</span><span class="sxs-lookup"><span data-stu-id="8209c-174">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="8209c-175">No Windows 10, instale o .NET Framework 2.0 executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="8209c-175">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="8209c-176">Para instalar o add-in sem nenhuma interação do usuário, abra um Prompt de Comando e use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="8209c-176">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="8209c-177">`MaxMessageSelection` especifica o número máximo de mensagens que você pode selecionar para um único envio.</span><span class="sxs-lookup"><span data-stu-id="8209c-177">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="8209c-178">Os valores válidos são de 1 a 50.</span><span class="sxs-lookup"><span data-stu-id="8209c-178">Valid values are from 1 to 50.</span></span> <span data-ttu-id="8209c-179">O valor padrão é 15.</span><span class="sxs-lookup"><span data-stu-id="8209c-179">The default value is 15.</span></span>

   - <span data-ttu-id="8209c-180">`BccEmailAddress` especifica destinatários Cc adicionais que receberão uma cópia de todos os envios de usuário.</span><span class="sxs-lookup"><span data-stu-id="8209c-180">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="8209c-181">O valor padrão está em branco (nenhum destinatário Cc adicional).</span><span class="sxs-lookup"><span data-stu-id="8209c-181">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="8209c-182">Este exemplo instala a versão de 64 bits do complemento a partir do caminho especificado com as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="8209c-182">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="8209c-183">Este exemplo instala a versão de 32 bits do complemento a partir do caminho especificado com as seguintes configurações adicionais:</span><span class="sxs-lookup"><span data-stu-id="8209c-183">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="8209c-184">Até 20 mensagens podem ser selecionadas em um único envio.</span><span class="sxs-lookup"><span data-stu-id="8209c-184">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="8209c-185">junkreports@contoso.com e hollyd@treyresearch.net receber cópias Cc de todos os envios.</span><span class="sxs-lookup"><span data-stu-id="8209c-185">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="8209c-186">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="8209c-186">How do you know this worked?</span></span>

<span data-ttu-id="8209c-187">Para verificar se você instalou com êxito o Complemento Relatório de Lixo Eletrônico, faça as seguintes etapas no Outlook:</span><span class="sxs-lookup"><span data-stu-id="8209c-187">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="8209c-188">Selecione a mensagem ou abra a mensagem.</span><span class="sxs-lookup"><span data-stu-id="8209c-188">Select the message or open the message.</span></span> <span data-ttu-id="8209c-189">Na guia **Página** Home ou **Mensagem** na faixa de opções, clique em **Lixo** Eletrônico e verifique se as seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="8209c-189">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="8209c-190">**Relatar como Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="8209c-190">**Report as Junk**</span></span>
  - <span data-ttu-id="8209c-191">**Relatar como Phishing**</span><span class="sxs-lookup"><span data-stu-id="8209c-191">**Report as Phishing**</span></span>
  - <span data-ttu-id="8209c-192">**Opções de relatório de lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="8209c-192">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="8209c-193">**Relatar a Ajuda do Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="8209c-193">**Report Junk Online Help**</span></span>

  ![Relatar lixo eletrônico ou email de phishing da faixa de opções](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="8209c-195">Clique com o botão direito do mouse na mensagem, selecione **Lixo** Eletrônico e verifique se as seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="8209c-195">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="8209c-196">**Relatar como Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="8209c-196">**Report as Junk**</span></span>
  - <span data-ttu-id="8209c-197">**Relatar como Phishing**</span><span class="sxs-lookup"><span data-stu-id="8209c-197">**Report as Phishing**</span></span>
  - <span data-ttu-id="8209c-198">**Opções de relatório de lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="8209c-198">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="8209c-199">**Relatar a Ajuda do Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="8209c-199">**Report Junk Online Help**</span></span>

  ![Relatar lixo eletrônico ou email de phishing com o clique com o botão direito do mouse](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="8209c-201">Selecione várias mensagens, clique com o botão direito do mouse e verifique se as seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="8209c-201">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="8209c-202">**Relatar como Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="8209c-202">**Report as Junk**</span></span>
  - <span data-ttu-id="8209c-203">**Relatar como Phishing**</span><span class="sxs-lookup"><span data-stu-id="8209c-203">**Report as Phishing**</span></span>

  ![Relatar várias mensagens de lixo eletrônico ou phishing clicando com o botão direito do mouse](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="8209c-205">Faça as ações anteriores na pasta Lixo  **Eletrônico e** verifique se as opções anteriores de relatório de lixo eletrônico agora não são **lixo eletrônico.**</span><span class="sxs-lookup"><span data-stu-id="8209c-205">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Relatar não lixo eletrônico ou email de phishing da faixa de opções na pasta Lixo Eletrônico](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Relatar não lixo eletrônico ou email de phishing clicando com o botão direito do mouse na pasta Lixo Eletrônico](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Relatar várias mensagens de email que não são de lixo eletrônico ou phishing clicando com o botão direito do mouse na pasta Lixo Eletrônico](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="8209c-209">Desinstalar o Suplemento Relatório de Lixo Eletrônico</span><span class="sxs-lookup"><span data-stu-id="8209c-209">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="8209c-210">Depois de fechar o Outlook, use qualquer um dos procedimentos a seguir para desinstalar o Add-in de Relatório de Lixo Eletrônico:</span><span class="sxs-lookup"><span data-stu-id="8209c-210">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="8209c-211">**Painel de Controle:** pressione a tecla Windows + R. Na caixa **de diálogo Executar** que é aberta, insira e clique em `control appwiz.cpl` **OK**.</span><span class="sxs-lookup"><span data-stu-id="8209c-211">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="8209c-212">Encontre e selecione **o Microsoft Junk Email Reporting Add-in** na lista e clique em **Desinstalar.**</span><span class="sxs-lookup"><span data-stu-id="8209c-212">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="8209c-213">**Pacote do Windows Installer:** encontre ou baixe o arquivo .msi apropriado e clique duas vezes nele.</span><span class="sxs-lookup"><span data-stu-id="8209c-213">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="8209c-214">**32 bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="8209c-214">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="8209c-215">**64 bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="8209c-215">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="8209c-216">Na caixa de diálogo exibida, selecione Remover o **Microsoft Junk Email Reporting Add-in para Outlook** e clique em **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="8209c-216">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="8209c-217">**Modo Silencioso:** encontre ou baixe o arquivo .msi apropriado.</span><span class="sxs-lookup"><span data-stu-id="8209c-217">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="8209c-218">Em uma janela de Prompt de Comando, substitua pelo local do arquivo \<PathToFile\> .msi e execute um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="8209c-218">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="8209c-219">**32 bits:**</span><span class="sxs-lookup"><span data-stu-id="8209c-219">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="8209c-220">**64 bits:**</span><span class="sxs-lookup"><span data-stu-id="8209c-220">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="8209c-221">Quando você abre o Outlook após a desinstalação, as opções de relatório de lixo eletrônico, não lixo eletrônico e phishing devem ter sido desinstaladas.</span><span class="sxs-lookup"><span data-stu-id="8209c-221">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="8209c-222">Solução de problemas do complemento Relatório de Lixo Eletrônico</span><span class="sxs-lookup"><span data-stu-id="8209c-222">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="8209c-223">Ocasionalmente, você pode ter problemas com o Outlook depois de adicionar o Complemento Relatório de Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="8209c-223">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="8209c-224">Esta seção descreve os problemas que você pode encontrar, juntamente com dicas para resolver esses problemas.</span><span class="sxs-lookup"><span data-stu-id="8209c-224">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="8209c-225">Solução de problemas para usuários</span><span class="sxs-lookup"><span data-stu-id="8209c-225">Troubleshooting for users</span></span>

<span data-ttu-id="8209c-226">Você tem um ou mais dos seguintes problemas:</span><span class="sxs-lookup"><span data-stu-id="8209c-226">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="8209c-227">Nada acontece quando você clica em **Relatar Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="8209c-227">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="8209c-228">O Outlook para de responder depois que você selecionar uma mensagem de email</span><span class="sxs-lookup"><span data-stu-id="8209c-228">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="8209c-229">O lixo eletrônico relatado não pode ser entregue devido a uma resposta "não entregue"</span><span class="sxs-lookup"><span data-stu-id="8209c-229">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="8209c-230">Para corrigir esse problema, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8209c-230">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="8209c-231">Feche e reinicie o Outlook.</span><span class="sxs-lookup"><span data-stu-id="8209c-231">Close and restart Outlook.</span></span>
2. <span data-ttu-id="8209c-232">Crie e envie uma mensagem de teste e verifique se o destinatário recebeu a mensagem.</span><span class="sxs-lookup"><span data-stu-id="8209c-232">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="8209c-233">Se o problema persistir, contate o administrador.</span><span class="sxs-lookup"><span data-stu-id="8209c-233">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="8209c-234">Para outros métodos que você pode usar para enviar mensagens à Microsoft, confira [Mensagens e arquivos de relatório para a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="8209c-234">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="8209c-235">Solução de problemas para administradores</span><span class="sxs-lookup"><span data-stu-id="8209c-235">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="8209c-236">Problema: uma mensagem de erro é exibida continuamente solicitando que os usuários contatem o administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="8209c-236">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="8209c-237">Verifique ou de definida `LoggingLevel` a chave do Registro com o valor "Verbose":</span><span class="sxs-lookup"><span data-stu-id="8209c-237">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="8209c-238">**Outlook de 32 bits no Windows de 32 bits:**</span><span class="sxs-lookup"><span data-stu-id="8209c-238">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="8209c-239">**Outlook de 32 bits no Windows de 64 bits:**</span><span class="sxs-lookup"><span data-stu-id="8209c-239">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="8209c-240">**Outlook de 64 bits:**</span><span class="sxs-lookup"><span data-stu-id="8209c-240">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="8209c-241">Reinicie o Outlook e peça aos usuários para relatar quando eles veem a mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="8209c-241">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="8209c-242">Colete as informações de log encontradas no seguinte local:</span><span class="sxs-lookup"><span data-stu-id="8209c-242">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="8209c-243">Entre em contato com o suporte técnico do Exchange Online Protection e forneça as informações de log.</span><span class="sxs-lookup"><span data-stu-id="8209c-243">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="8209c-244">Problema: os usuários selecionaram não receber uma solicitação de confirmação ao relatarem as mensagens e agora querem o prompt de volta</span><span class="sxs-lookup"><span data-stu-id="8209c-244">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="8209c-245">Crie a `ConfirmReportJunk` chave do Registro com o valor "True":</span><span class="sxs-lookup"><span data-stu-id="8209c-245">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="8209c-246">Reinicie o Outlook.</span><span class="sxs-lookup"><span data-stu-id="8209c-246">Restart Outlook.</span></span>
