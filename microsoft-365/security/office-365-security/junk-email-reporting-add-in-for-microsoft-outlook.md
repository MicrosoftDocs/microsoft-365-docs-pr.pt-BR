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
ms.openlocfilehash: e120ceec355ffc135e00e13a89a0f29085946a3b
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203011"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a><span data-ttu-id="c4aa5-103">Instalar e usar o complemento Relatório de Lixo Eletrônico para o Microsoft Outlook</span><span class="sxs-lookup"><span data-stu-id="c4aa5-103">Install and use the Junk Email Reporting add-in for Microsoft Outlook</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c4aa5-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="c4aa5-104">**Applies to**</span></span>
- [<span data-ttu-id="c4aa5-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c4aa5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c4aa5-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="c4aa5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c4aa5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c4aa5-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="c4aa5-108">Se você não estiver usando o add-in Relatório de Lixo [](enable-the-report-message-add-in.md) Eletrônico no momento, recomendamos o complemento Mensagem de Relatório ou o complemento Relatar [Phishing.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="c4aa5-108">If you aren't currently using the Junk E-mail Reporting add-in, we recommend the [Report Message add-in](enable-the-report-message-add-in.md) or the [Report Phishing add-in](enable-the-report-phish-add-in.md) instead.</span></span> <span data-ttu-id="c4aa5-109">Para mais informações, confira [Relatar mensagens e arquivos à Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="c4aa5-109">For more information, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="c4aa5-110">O Junk Email Reporting Add-in para a Microsoft Outlook permite que os usuários enviem falsos positivos (bons emails marcados como spam), falsos negativos (email ruim permitido) e mensagens de phishing para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-110">The Junk Email Reporting Add-in for Microsoft Outlook allows users to submit false positives (good email marked as spam), false negatives (bad email allowed) and phishing messages to Microsoft.</span></span> <span data-ttu-id="c4aa5-111">Se sua organização não usar Proteção do Exchange Online (por exemplo, serviços de email ou Exchange locais que não Exchange Online), o envio do relatório de lixo eletrônico não afetará sua filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-111">If your organization doesn't use Exchange Online Protection (for example, on-premises Exchange or email services other than Exchange Online), your junk email report submission will not affect your spam filtering.</span></span>

<span data-ttu-id="c4aa5-112">Este tópico explica como instalar e usar o complemento Relatório de Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-112">This topic explains how to install and use the Junk Email Reporting add-in.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c4aa5-113">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="c4aa5-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c4aa5-114">Para instalar o complemento Relatório de Lixo Eletrônico, consulte a seção Instalar o [complemento](#install-the-junk-email-reporting-add-in) Relatório de Lixo Eletrônico posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-114">To install the Junk Email Reporting add-in, see the [Install the Junk Email Reporting add-in](#install-the-junk-email-reporting-add-in) section later in this article.</span></span>

- <span data-ttu-id="c4aa5-115">O complemento Relatório de Lixo Eletrônico funciona com as seguintes versões do Outlook:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-115">The Junk Email Reporting add-in works with the following versions of Outlook:</span></span>

  - <span data-ttu-id="c4aa5-116">Outlook 2013 ou posterior</span><span class="sxs-lookup"><span data-stu-id="c4aa5-116">Outlook 2013 or later</span></span>
  - <span data-ttu-id="c4aa5-117">Outlook incluído no Microsoft 365 Apps para Grandes Empresas</span><span class="sxs-lookup"><span data-stu-id="c4aa5-117">Outlook included with Microsoft 365 Apps for enterprise</span></span>

- <span data-ttu-id="c4aa5-118">Para obter mais informações sobre o relatório de mensagens para a Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="c4aa5-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a><span data-ttu-id="c4aa5-119">Use o complemento Relatório de Lixo Eletrônico para relatar mensagens de spam e phishing</span><span class="sxs-lookup"><span data-stu-id="c4aa5-119">Use the Junk Email Reporting add-in to report spam and phishing messages</span></span>

1. <span data-ttu-id="c4aa5-120">Para mensagens na Caixa de Entrada ou em qualquer outra pasta de email, exceto Lixo Eletrônico, use qualquer um dos seguintes métodos para relatar mensagens de spam e phishing:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-120">For messages in the Inbox or any other email folder except Junk Email, use any of the following methods to report spam and phishing messages:</span></span>

   - <span data-ttu-id="c4aa5-121">Selecione a mensagem ou abra a mensagem.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-121">Select the message or open the message.</span></span> <span data-ttu-id="c4aa5-122">Na guia **Home** ou **Message** na faixa de opções, clique em **Lixo** Eletrônico e, em seguida, selecione Relatório como **Lixo** Eletrônico ou Relatório **como Phishing**.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-122">In the **Home** or **Message** tab in the ribbon, click **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Relatar lixo eletrônico ou email de phishing da faixa de opções](../../media/junk-email-reporting-ribbon.png)

   - <span data-ttu-id="c4aa5-124">Clique com o botão direito do mouse na mensagem, selecione **Lixo** Eletrônico e, em seguida, selecione **Relatório como Lixo** Eletrônico ou Relatório como **Phishing**.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-124">Right-click on the message, select **Junk**, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Relatar lixo eletrônico ou email de phishing com o botão direito do mouse](../../media/junk-email-reporting-right-click.png)

   - <span data-ttu-id="c4aa5-126">Selecione várias mensagens, clique com o botão direito do mouse e selecione **Relatório como Lixo** Eletrônico ou Relatório como **Phishing**.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-126">Select multiple messages, right-click, and then select **Report as Junk** or **Report as Phishing**.</span></span>

     ![Relatar várias mensagens de email de lixo eletrônico ou phishing com o botão direito do mouse](../../media/junk-email-reporting-right-click-multiple.png)

2. <span data-ttu-id="c4aa5-128">Na caixa de diálogo exibida, leia as informações e clique em **Relatar**.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-128">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="c4aa5-129">Se você mudar de ideia, clique **em Não Relatar**.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-129">If you change your mind, click **Don't Report**.</span></span>

   ![Relatório como caixa de diálogo lixo eletrônico](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Relatar como caixa de diálogo de phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="c4aa5-132">As mensagens selecionadas serão enviadas à Microsoft para análise e:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-132">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="c4aa5-133">Movido para a pasta Lixo Eletrônico se tiver sido relatado como spam.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-133">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="c4aa5-134">Excluído se tiver sido relatado como phishing.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-134">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="c4aa5-135">Para confirmar se as mensagens foram enviadas, abra sua pasta **Itens Enviados** para exibir as mensagens enviadas.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-135">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a><span data-ttu-id="c4aa5-136">Use o complemento Relatório de Lixo Eletrônico para relatar mensagens de não spam e phishing da pasta Lixo Eletrônico</span><span class="sxs-lookup"><span data-stu-id="c4aa5-136">Use the Junk Email Reporting add-in to report non-spam and phishing messages from the Junk Email folder</span></span>

1. <span data-ttu-id="c4aa5-137">Na pasta Lixo Eletrônico, use qualquer um dos seguintes métodos para relatar falsos positivos de spam ou mensagens de phishing:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-137">In the Junk Email folder, use any of the following methods to report spam false positives or phishing messages:</span></span>

   - <span data-ttu-id="c4aa5-138">Selecione a mensagem ou abra a mensagem.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-138">Select the message or open the message.</span></span> <span data-ttu-id="c4aa5-139">Na guia **Home** ou **Message** na faixa de opções, clique em **Não Lixo** Eletrônico e selecione **Relatório como** Não Lixo Eletrônico ou Relatório **como Phishing**.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-139">In the **Home** or **Message** tab in the ribbon, click **Not Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Relatar não lixo eletrônico ou email de phishing da faixa de opções na pasta Lixo Eletrônico](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - <span data-ttu-id="c4aa5-141">Clique com o botão direito do mouse na mensagem, clique em **Lixo** Eletrônico e selecione **Relatório como Não** Lixo Eletrônico ou Relatório como **Phishing**.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-141">Right-click on the message, click **Junk**, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Relatar não lixo eletrônico ou email de phishing com o botão direito do mouse na pasta Lixo Eletrônico](../../media/junk-email-reporting-junk-folder-right-click.png)

   - <span data-ttu-id="c4aa5-143">Selecione várias mensagens, clique com o botão direito do mouse e selecione **Relatório como Não** Lixo Eletrônico ou Relatório como **Phishing**.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-143">Select multiple messages, right-click, and then select **Report as Not Junk** or **Report as Phishing**.</span></span>

     ![Relatar várias mensagens de email não lixo eletrônico ou phishing com o botão direito do mouse na pasta Lixo Eletrônico](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. <span data-ttu-id="c4aa5-145">Na caixa de diálogo exibida, leia as informações e clique em **Relatar**.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-145">In the dialog that appears, read the information and click **Report**.</span></span> <span data-ttu-id="c4aa5-146">Se você mudar de ideia, clique **em Não Relatar**.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-146">If you change your mind, click **Don't Report**.</span></span>

   ![Relatar como não caixa de diálogo lixo eletrônico](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Relatar como caixa de diálogo de phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. <span data-ttu-id="c4aa5-149">As mensagens selecionadas serão enviadas à Microsoft para análise e:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-149">The selected messages will be sent to Microsoft for analysis and:</span></span>

   - <span data-ttu-id="c4aa5-150">Movido para a pasta Lixo Eletrônico se tiver sido relatado como spam.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-150">Moved to the Junk Email folder if it was reported as spam.</span></span>
   - <span data-ttu-id="c4aa5-151">Excluído se tiver sido relatado como phishing.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-151">Deleted if it was reported as phishing.</span></span>

   <span data-ttu-id="c4aa5-152">Para confirmar se as mensagens foram enviadas, abra sua pasta **Itens Enviados** para exibir as mensagens enviadas.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-152">To confirm that the messages have been submitted, open your **Sent Items** folder to view the submitted messages.</span></span>

## <a name="install-the-junk-email-reporting-add-in"></a><span data-ttu-id="c4aa5-153">Instalar o complemento Relatório de Lixo Eletrônico</span><span class="sxs-lookup"><span data-stu-id="c4aa5-153">Install the Junk Email Reporting add-in</span></span>

- <span data-ttu-id="c4aa5-154">Você precisa ter privilégios de administrador no computador onde você está instalando o complemento.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-154">You need to have administrator privileges on the computer where you're installing the add-in.</span></span>

- <span data-ttu-id="c4aa5-155">Acesse e baixe o arquivo de .msi apropriado para sua versão do Office para um <https://www.microsoft.com/download/details.aspx?id=18275> local fácil de encontrar:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-155">Go to <https://www.microsoft.com/download/details.aspx?id=18275> and download the appropriate .msi file for your version of Office to a location that's easy to find:</span></span>

  - <span data-ttu-id="c4aa5-156">**32 bits**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="c4aa5-156">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>
  - <span data-ttu-id="c4aa5-157">**64 bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="c4aa5-157">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

- <span data-ttu-id="c4aa5-158">Para Outlook 2013 ou posterior, o único pré-requisito é o Microsoft .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-158">For Outlook 2013 or later, the only prerequisite is the Microsoft .NET Framework 2.0.</span></span> <span data-ttu-id="c4aa5-159">Em Windows 10, você não instala o .NET Framework 2.0 de um download.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-159">In Windows 10, you don't install the .NET Framework 2.0 from a download.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a><span data-ttu-id="c4aa5-160">Instalar o Complemento de Relatório de Lixo Eletrônico usando o assistente de Instalação</span><span class="sxs-lookup"><span data-stu-id="c4aa5-160">Install the Junk Email Reporting Add-in using the Setup wizard</span></span>

1. <span data-ttu-id="c4aa5-161">Feche o Outlook no computador.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-161">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="c4aa5-162">Em Windows 10, verifique se o .NET Framework 2.0 está habilitado.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-162">In Windows 10, verify the .NET Framework 2.0 is enabled.</span></span> <span data-ttu-id="c4aa5-163">Para obter instruções, [consulte Enable the .NET Framework 3.5 in Control Panel](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span><span class="sxs-lookup"><span data-stu-id="c4aa5-163">For instructions, see [Enable the .NET Framework 3.5 in Control Panel](/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel).</span></span>

3. <span data-ttu-id="c4aa5-164">Localize o .msi arquivo que você baixou e clique duas vezes nele.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-164">Locate the .msi file you downloaded and double-click on it.</span></span>

4. <span data-ttu-id="c4aa5-165">Na página **Bem-vindo à Configuração do Suplemento Relatório de Lixo Eletrônico para Microsoft** e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-165">On the **Welcome to Microsoft Junk Email Reporting Add-in Setup** page, click **Next**.</span></span>

5. <span data-ttu-id="c4aa5-166">Revise o contrato de licença, clique em **Aceito os** termos no Contrato de Licença se você concordar com os termos e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-166">Review the license agreement, click **I accept the terms in the License Agreement** if you agree to the terms, and then click **Next**.</span></span>

6. <span data-ttu-id="c4aa5-167">Quando o assistente for concluído, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-167">When the wizard is complete, click **Finish**.</span></span>

<span data-ttu-id="c4aa5-168">Inicie o Outlook.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-168">Start Outlook.</span></span>

<span data-ttu-id="c4aa5-p109">Procure o botão **Lixo Eletrônico** na faixa de opções do Outlook. Agora, você pode relatar mensagens de lixo eletrônico à Microsoft selecionando-as na sua Caixa de Entrada e clicando no botão **Relatar Lixo Eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-p109">Look for the **Junk** button on your Outlook ribbon. You can now report junk email messages to Microsoft by selecting the junk email messages in your Inbox and clicking the **Report Junk** button.</span></span>

<span data-ttu-id="c4aa5-p110">Selecione a seta para baixo ao lado de **Lixo Eletrônico** para obter mais opções, como **Relatar como Phishing** se você quiser relatar emails de esquemas de phishing para a Microsoft. Na pasta Lixo Eletrônico, você também pode selecionar, **Relatar como não sendo lixo eletrônico** se um email tiver sido identificado incorretamente como lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-p110">Choose the down arrow next to **Junk** for more options such as **Report as Phishing** if you want to report phishing scam emails to Microsoft. In your junk mail folder, you can also select, **Report not junk** if an email was incorrectly identified as junk mail.</span></span>

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a><span data-ttu-id="c4aa5-173">Instalar o Suplemento Relatório de Lixo Eletrônico usando Modo Silencioso</span><span class="sxs-lookup"><span data-stu-id="c4aa5-173">Install the Junk Email Reporting Add-In using Silent Mode</span></span>

1. <span data-ttu-id="c4aa5-174">Feche o Outlook no computador.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-174">On your computer, close Outlook.</span></span>

2. <span data-ttu-id="c4aa5-175">Em Windows 10, instale o .NET Framework 2.0 executando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-175">In Windows 10, install the .NET Framework 2.0 by running the following command:</span></span>

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. <span data-ttu-id="c4aa5-176">Para instalar o add-in sem nenhuma interação do usuário, abra um Prompt de Comando e use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-176">To install the add-in without any user interaction, open a Command Prompt and use the following syntax:</span></span>

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - <span data-ttu-id="c4aa5-177">`MaxMessageSelection` especifica o número máximo de mensagens que você pode selecionar para um único envio.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-177">`MaxMessageSelection` specifies the maximum number of messages that you can select for a single submission.</span></span> <span data-ttu-id="c4aa5-178">Os valores válidos são de 1 a 50.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-178">Valid values are from 1 to 50.</span></span> <span data-ttu-id="c4aa5-179">O valor padrão é 15.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-179">The default value is 15.</span></span>

   - <span data-ttu-id="c4aa5-180">`BccEmailAddress` especifica destinatários Cc adicionais que receberão uma cópia de todos os envios do usuário.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-180">`BccEmailAddress` specifies additional Bcc recipients who will receive a copy of all user submissions.</span></span> <span data-ttu-id="c4aa5-181">O valor padrão está em branco (nenhum destinatário Cc adicional).</span><span class="sxs-lookup"><span data-stu-id="c4aa5-181">The default value is blank (no additional Bcc recipients).</span></span>

   <span data-ttu-id="c4aa5-182">Este exemplo instala a versão de 64 bits do complemento do caminho especificado com as configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-182">This example installs the 64-bit version of the add-in from the specified path with the default settings.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   <span data-ttu-id="c4aa5-183">Este exemplo instala a versão de 32 bits do complemento do caminho especificado com as seguintes configurações adicionais:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-183">This example installs the 32-bit version of the add-in from the specified path with the following additional settings:</span></span>

   - <span data-ttu-id="c4aa5-184">Até 20 mensagens podem ser selecionadas em um único envio.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-184">Up to 20 messages can be selected in a single submission.</span></span>
   - <span data-ttu-id="c4aa5-185">junkreports@contoso.com e hollyd@treyresearch.net receber cópias Cc de todos os envios.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-185">junkreports@contoso.com and hollyd@treyresearch.net receive Bcc copies of all submissions.</span></span>

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c4aa5-186">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="c4aa5-186">How do you know this worked?</span></span>

<span data-ttu-id="c4aa5-187">Para verificar se você instalou com êxito o Complemento de Relatório de Lixo Eletrônico, faça as seguintes etapas no Outlook:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-187">To verify that you've successfully installed the Junk Email Reporting Add-in, do the any of the following steps in Outlook:</span></span>

- <span data-ttu-id="c4aa5-188">Selecione a mensagem ou abra a mensagem.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-188">Select the message or open the message.</span></span> <span data-ttu-id="c4aa5-189">Na guia **Home** ou **Message** na faixa de opções, clique em **Lixo** Eletrônico e verifique se as seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-189">In the **Home** or **Message** tab in the ribbon, click **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="c4aa5-190">**Relatório como Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="c4aa5-190">**Report as Junk**</span></span>
  - <span data-ttu-id="c4aa5-191">**Relatório como Phishing**</span><span class="sxs-lookup"><span data-stu-id="c4aa5-191">**Report as Phishing**</span></span>
  - <span data-ttu-id="c4aa5-192">**Opções de relatório de lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="c4aa5-192">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="c4aa5-193">**Relatar Ajuda de Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="c4aa5-193">**Report Junk Online Help**</span></span>

  ![Relatar lixo eletrônico ou email de phishing da faixa de opções](../../media/junk-email-reporting-ribbon.png)

- <span data-ttu-id="c4aa5-195">Clique com o botão direito do mouse na mensagem, selecione **Lixo** Eletrônico e verifique se as seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-195">Right-click on the message, select **Junk**, and verify that the following options are available:</span></span>

  - <span data-ttu-id="c4aa5-196">**Relatório como Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="c4aa5-196">**Report as Junk**</span></span>
  - <span data-ttu-id="c4aa5-197">**Relatório como Phishing**</span><span class="sxs-lookup"><span data-stu-id="c4aa5-197">**Report as Phishing**</span></span>
  - <span data-ttu-id="c4aa5-198">**Opções de relatório de lixo eletrônico**</span><span class="sxs-lookup"><span data-stu-id="c4aa5-198">**Junk Reporting Options**</span></span>
  - <span data-ttu-id="c4aa5-199">**Relatar Ajuda de Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="c4aa5-199">**Report Junk Online Help**</span></span>

  ![Relatar lixo eletrônico ou email de phishing com o botão direito do mouse](../../media/junk-email-reporting-right-click.png)

- <span data-ttu-id="c4aa5-201">Selecione várias mensagens, clique com o botão direito do mouse e verifique se as seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-201">Select multiple messages, right click, and verify that the following options are available:</span></span>

  - <span data-ttu-id="c4aa5-202">**Relatório como Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="c4aa5-202">**Report as Junk**</span></span>
  - <span data-ttu-id="c4aa5-203">**Relatório como Phishing**</span><span class="sxs-lookup"><span data-stu-id="c4aa5-203">**Report as Phishing**</span></span>

  ![Relatar várias mensagens de email de lixo eletrônico ou phishing com o botão direito do mouse](../../media/junk-email-reporting-right-click-multiple.png)

- <span data-ttu-id="c4aa5-205">Faça as ações anteriores na pasta **Lixo Eletrônico** e verifique se as opções **anteriores** de relatório de lixo eletrônico agora não são **lixo eletrônico.**</span><span class="sxs-lookup"><span data-stu-id="c4aa5-205">Do the previous actions in the **Junk Email** folder and verify the previous **Junk** reporting options are now **Not Junk**.</span></span>

  ![Relatar não lixo eletrônico ou email de phishing da faixa de opções na pasta Lixo Eletrônico](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Relatar não lixo eletrônico ou email de phishing com o botão direito do mouse na pasta Lixo Eletrônico](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Relatar várias mensagens de email não lixo eletrônico ou phishing com o botão direito do mouse na pasta Lixo Eletrônico](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a><span data-ttu-id="c4aa5-209">Desinstalar o Suplemento Relatório de Lixo Eletrônico</span><span class="sxs-lookup"><span data-stu-id="c4aa5-209">Uninstall the Junk Email Reporting Add-in</span></span>

<span data-ttu-id="c4aa5-210">Depois de fechar Outlook, use qualquer um dos procedimentos a seguir para desinstalar o Complemento de Relatório de Lixo Eletrônico:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-210">After you close Outlook, use any of the following procedures to uninstall the Junk Email Reporting Add-in:</span></span>

- <span data-ttu-id="c4aa5-211">**Painel de Controle**: pressione a tecla Windows + R. Na caixa **de diálogo Executar** que é aberta, digite e clique em `control appwiz.cpl` **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-211">**Control Panel**: Press the Windows key + R. In the **Run** dialog that opens, enter `control appwiz.cpl` and then click **OK**.</span></span>

  <span data-ttu-id="c4aa5-212">Encontre e selecione **o Microsoft Junk Email Reporting Add-in** na lista e clique em **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-212">Find and select **Microsoft Junk Email Reporting Add-in** in the list, and then click **Uninstall**.</span></span>

- <span data-ttu-id="c4aa5-213">**Windows pacote do Instalador**: localmente ou baixe o arquivo .msi apropriado e clique duas vezes nele.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-213">**Windows Installer package**: Find or download the appropriate .msi file, and double-click on it.</span></span>

  - <span data-ttu-id="c4aa5-214">**32 bits**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="c4aa5-214">**32-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`</span></span>

  - <span data-ttu-id="c4aa5-215">**64 bits:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span><span class="sxs-lookup"><span data-stu-id="c4aa5-215">**64-bit**: `Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`</span></span>

  <span data-ttu-id="c4aa5-216">Na caixa de diálogo exibida, selecione Remover o Microsoft **Junk Email Reporting Add-in para** Outlook e clique em **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-216">In the dialog that appears, select **Remove Microsoft Junk Email Reporting Add-in for Outlook** and then click **Next**.</span></span>

- <span data-ttu-id="c4aa5-217">**Modo Silencioso**: localmente ou baixe o arquivo .msi apropriado.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-217">**Silent Mode**: Find or download the appropriate .msi file.</span></span> <span data-ttu-id="c4aa5-218">Em uma janela prompt de comando, substitua pelo local do arquivo \<PathToFile\> .msi e execute um dos seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-218">In a Command Prompt window, replace \<PathToFile\> with the location of the .msi file, and run one of the following commands:</span></span>

  - <span data-ttu-id="c4aa5-219">**32 bits**:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-219">**32-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - <span data-ttu-id="c4aa5-220">**64 bits:**</span><span class="sxs-lookup"><span data-stu-id="c4aa5-220">**64-bit**:</span></span>

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

<span data-ttu-id="c4aa5-221">Quando você abre Outlook após a desinstalação, as opções de relatório de lixo eletrônico, não lixo eletrônico e phishing devem ser desinstaladas.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-221">When you open Outlook after the uninstall, the junk, not junk, and phishing reporting options should be gone.</span></span>

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a><span data-ttu-id="c4aa5-222">Solução de problemas do complemento Relatório de Lixo Eletrônico</span><span class="sxs-lookup"><span data-stu-id="c4aa5-222">Troubleshooting the Junk Email Reporting add-in</span></span>

<span data-ttu-id="c4aa5-223">Ocasionalmente, você pode ter problemas com Outlook depois de adicionar o Junk Email Reporting Add-In.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-223">Occasionally, you might experience trouble with Outlook after adding the Junk Email Reporting Add-In.</span></span> <span data-ttu-id="c4aa5-224">Esta seção descreve problemas que você pode encontrar, juntamente com dicas para resolver esses problemas.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-224">This section describes problems that you might encounter, along with tips for resolving these issues.</span></span>

### <a name="troubleshooting-for-users"></a><span data-ttu-id="c4aa5-225">Solução de problemas para usuários</span><span class="sxs-lookup"><span data-stu-id="c4aa5-225">Troubleshooting for users</span></span>

<span data-ttu-id="c4aa5-226">Você tem um ou mais dos seguintes problemas:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-226">You experience one or more of the following problems:</span></span>

- <span data-ttu-id="c4aa5-227">Nada acontece quando você clica em **Relatar Lixo Eletrônico**</span><span class="sxs-lookup"><span data-stu-id="c4aa5-227">Nothing happens when you click **Report Junk**</span></span>
- <span data-ttu-id="c4aa5-228">O Outlook para de responder depois que você selecionar uma mensagem de email</span><span class="sxs-lookup"><span data-stu-id="c4aa5-228">Outlook stops responding after you select an email message</span></span>
- <span data-ttu-id="c4aa5-229">O lixo eletrônico relatado não pode ser entregue devido a uma resposta "não entregue"</span><span class="sxs-lookup"><span data-stu-id="c4aa5-229">Reported junk mail cannot be delivered due to an "undeliverable" reply</span></span>

<span data-ttu-id="c4aa5-230">Para corrigir esse problema, faça as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-230">To fix this problem, do the following steps:</span></span>

1. <span data-ttu-id="c4aa5-231">Feche e reinicie Outlook.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-231">Close and restart Outlook.</span></span>
2. <span data-ttu-id="c4aa5-232">Crie e envie uma mensagem de teste e verifique se o destinatário recebeu a mensagem.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-232">Create and send a test message, and verify that the recipient received the message.</span></span>
3. <span data-ttu-id="c4aa5-233">Se o problema persistir, contate o administrador.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-233">If the problem persists, contact your admin.</span></span>

<span data-ttu-id="c4aa5-234">Para outros métodos que você pode usar para enviar mensagens à Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="c4aa5-234">For other methods that you can use to submit messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

### <a name="troubleshooting-for-admins"></a><span data-ttu-id="c4aa5-235">Solução de problemas para administradores</span><span class="sxs-lookup"><span data-stu-id="c4aa5-235">Troubleshooting for admins</span></span>

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a><span data-ttu-id="c4aa5-236">Problema: uma mensagem de erro é exibida continuamente que solicita que os usuários contatem o administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="c4aa5-236">Problem: An error message continually appears that asks users to contact their system administrator</span></span>

1. <span data-ttu-id="c4aa5-237">Verificar ou definir `LoggingLevel` a chave do Registro como o valor "Verbose":</span><span class="sxs-lookup"><span data-stu-id="c4aa5-237">Verify or set the `LoggingLevel` registry key to the value "Verbose":</span></span>

   - <span data-ttu-id="c4aa5-238">**32 bits Outlook em 32 bits Windows**:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-238">**32-bit Outlook on 32-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="c4aa5-239">**32 bits Outlook em 64 bits Windows**:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-239">**32-bit Outlook on 64-bit Windows**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - <span data-ttu-id="c4aa5-240">**64 bits Outlook**:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-240">**64-bit Outlook**:</span></span>

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. <span data-ttu-id="c4aa5-241">Reinicie Outlook e peça aos usuários para relatarem quando eles virem a mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-241">Restart Outlook and ask users to report back when they see the error message.</span></span>

3. <span data-ttu-id="c4aa5-242">Colete as informações de log encontradas no seguinte local:</span><span class="sxs-lookup"><span data-stu-id="c4aa5-242">Collect the log information found at the following location:</span></span>

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. <span data-ttu-id="c4aa5-243">Entre em contato com o suporte técnico do Exchange Online Protection e forneça as informações de log.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-243">Contact Exchange Online Protection Technical Support and provide them with the log information.</span></span>

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a><span data-ttu-id="c4aa5-244">Problema: os usuários selecionados para não receber um prompt de confirmação quando relatam mensagens e agora querem o prompt de volta</span><span class="sxs-lookup"><span data-stu-id="c4aa5-244">Problem: Users selected not to receive a confirmation prompt when they report messages, and now they want the prompt back</span></span>

1. <span data-ttu-id="c4aa5-245">Crie a `ConfirmReportJunk` chave do Registro com o valor "True":</span><span class="sxs-lookup"><span data-stu-id="c4aa5-245">Create the `ConfirmReportJunk`registry key with the value "True":</span></span>

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. <span data-ttu-id="c4aa5-246">Reinicie o Outlook.</span><span class="sxs-lookup"><span data-stu-id="c4aa5-246">Restart Outlook.</span></span>