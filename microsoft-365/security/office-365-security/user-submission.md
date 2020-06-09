---
title: Especificar uma caixa de correio para envios de spam e mensagens de phishing
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
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a configurar uma caixa de correio para coletar spam e emails de phishing relatados pelos usuários.
ms.openlocfilehash: 0f3c7f160e26b8befcbbe8096c07e9eb6fecb533
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613427"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="f3442-103">Especificar uma caixa de correio para envios de spam e mensagens de phishing no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f3442-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="f3442-104">Nas organizações do Microsoft 365 com caixas de correio do Exchange Online, você pode especificar uma caixa de correio para receber mensagens que os usuários relatam como mal-intencionadas ou não mal intencionadas.</span><span class="sxs-lookup"><span data-stu-id="f3442-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="f3442-105">Quando os usuários enviam mensagens usando as várias opções de relatórios, você pode usar essa caixa de correio para interceptar mensagens (enviar somente para a caixa de correio personalizada) ou receber cópias de mensagens (enviar para a caixa de correio personalizada e Microsoft).</span><span class="sxs-lookup"><span data-stu-id="f3442-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="f3442-106">Este recurso funciona com as seguintes opções de relatório de mensagens:</span><span class="sxs-lookup"><span data-stu-id="f3442-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="f3442-107">O suplemento de mensagem de relatório</span><span class="sxs-lookup"><span data-stu-id="f3442-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="f3442-108">[Relatórios internos no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (anteriormente conhecido como Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="f3442-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

  > [!NOTE]
  > <span data-ttu-id="f3442-109">Se o relatório tiver sido [desabilitado no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), habilitar os envios de usuários aqui substituirá essa configuração e permitirá que os usuários reportem mensagens no Outlook na Web novamente.</span><span class="sxs-lookup"><span data-stu-id="f3442-109">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="f3442-110">Você também pode configurar ferramentas de relatório de mensagens de terceiros para encaminhar mensagens para a caixa de correio que você especificar.</span><span class="sxs-lookup"><span data-stu-id="f3442-110">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="f3442-111">O fornecimento de mensagens relatadas pelo usuário para uma caixa de correio personalizada em vez de diretamente para a Microsoft permite que os administradores reportem mensagens de forma seletiva e manual para a Microsoft usando o [envio do administrador](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f3442-111">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f3442-112">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="f3442-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f3442-113">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f3442-113">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="f3442-114">Para ir diretamente para a página **envios de usuários** , use <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="f3442-114">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="f3442-115">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f3442-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f3442-116">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="f3442-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f3442-117">Você precisa receber permissões para executar esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="f3442-117">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="f3442-118">Para configurar a caixa de correio para envios de usuários, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de **administrador de segurança** .</span><span class="sxs-lookup"><span data-stu-id="f3442-118">To configure the mailbox for user submissions, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="f3442-119">Para obter mais informações sobre grupos de funções no Centro de Conformidade e Segurança, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f3442-119">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="f3442-120">Usar o centro de conformidade de & de segurança para configurar a caixa de correio de envios de usuários</span><span class="sxs-lookup"><span data-stu-id="f3442-120">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="f3442-121">No centro de conformidade & segurança, vá para **Threat management** \> **Policy** \> **envios do usuário**da política de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="f3442-121">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="f3442-122">Na página **envios de usuários** que aparece, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="f3442-122">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="f3442-123">a.</span><span class="sxs-lookup"><span data-stu-id="f3442-123">a.</span></span> <span data-ttu-id="f3442-124">**Habilitar o recurso de mensagem de relatório para o Outlook (recomendado)**: Selecione essa opção se você usar o suplemento de mensagem de relatório ou os relatórios internos no Outlook na Web e, em seguida, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="f3442-124">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="f3442-125">**Personalizar a mensagem de confirmação do usuário final**: clique neste link.</span><span class="sxs-lookup"><span data-stu-id="f3442-125">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="f3442-126">No submenu **Personalizar mensagem de confirmação** que aparece, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="f3442-126">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="f3442-127">**Antes do envio**: nas caixas de **mensagem** **título** e confirmação, insira o texto descritivo que os usuários veem antes de reportar uma mensagem usando o suplemento de mensagem de relatório.</span><span class="sxs-lookup"><span data-stu-id="f3442-127">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="f3442-128">Você pode usar a variável% Type% para incluir o tipo de envio (lixo eletrônico, não lixo eletrônico, Phish, etc.).</span><span class="sxs-lookup"><span data-stu-id="f3442-128">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="f3442-129">Conforme observado, se você selecionar uma opção que envia as mensagens relatadas à Microsoft, o texto a seguir também será adicionado à notificação:</span><span class="sxs-lookup"><span data-stu-id="f3442-129">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="f3442-130">Seu email será enviado como é para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="f3442-130">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="f3442-131">Alguns emails podem conter informações pessoais ou confidenciais.</span><span class="sxs-lookup"><span data-stu-id="f3442-131">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="f3442-132">**Após o envio**: clique em ![ ícone de expansão ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="f3442-132">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="f3442-133">Nas caixas de mensagem **título** e **confirmação** , insira o texto descritivo que os usuários veem depois de reportar uma mensagem usando o suplemento de mensagem de relatório.</span><span class="sxs-lookup"><span data-stu-id="f3442-133">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="f3442-134">Você pode usar a variável% Type% para incluir o tipo de envio.</span><span class="sxs-lookup"><span data-stu-id="f3442-134">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="f3442-135">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f3442-135">When you're finished, click **Save**.</span></span> <span data-ttu-id="f3442-136">Para limpar esses valores, clique em **restaurar** novamente na página **envios de usuários** .</span><span class="sxs-lookup"><span data-stu-id="f3442-136">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="f3442-137">**Enviar as mensagens relatadas para**: faça uma das seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="f3442-137">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="f3442-138">**Microsoft (recomendado)**: a caixa de correio de envios do usuário não é usada (todas as mensagens relatadas vão para a Microsoft).</span><span class="sxs-lookup"><span data-stu-id="f3442-138">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="f3442-139">**Microsoft e uma caixa de correio personalizada**: na caixa exibida, insira o endereço de email de uma caixa de correio do Exchange Online existente.</span><span class="sxs-lookup"><span data-stu-id="f3442-139">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="f3442-140">Os grupos de distribuição não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f3442-140">Distribution groups are not allowed.</span></span> <span data-ttu-id="f3442-141">Os envios de usuários vão para a Microsoft para análise e para a caixa de correio personalizada da equipe de administração ou de operações de segurança a serem analisadas.</span><span class="sxs-lookup"><span data-stu-id="f3442-141">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="f3442-142">Caixa de **correio personalizada**: na caixa exibida, insira o endereço de email de uma caixa de correio do Exchange Online existente.</span><span class="sxs-lookup"><span data-stu-id="f3442-142">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="f3442-143">Os grupos de distribuição não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="f3442-143">Distribution groups are not allowed.</span></span> <span data-ttu-id="f3442-144">Use essa opção se quiser que a mensagem apenas vá para a equipe de operações de segurança ou de administração para análise primeiro.</span><span class="sxs-lookup"><span data-stu-id="f3442-144">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="f3442-145">As mensagens não irão para a Microsoft, a menos que o administrador a encaminhe.</span><span class="sxs-lookup"><span data-stu-id="f3442-145">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="f3442-146">As organizações governamentais dos EUA (GCC, GCC-H e DoD) só podem configurar a **caixa de correio personalizada**.</span><span class="sxs-lookup"><span data-stu-id="f3442-146">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="f3442-147">As outras duas opções estão desativadas.</span><span class="sxs-lookup"><span data-stu-id="f3442-147">The other two options are disabled.</span></span> 

      <span data-ttu-id="f3442-148">Quando tiver concluído, clique em **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f3442-148">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="f3442-149">Se você [desabilitou o envio de relatórios de lixo eletrônico no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) usando o Outlook nas políticas de caixa de correio da Web, mas configurar qualquer uma das configurações anteriores para relatar mensagens à Microsoft, os usuários poderão relatar mensagens para a Microsoft no Outlook na Web usando o suplemento de mensagem de relatório.</span><span class="sxs-lookup"><span data-stu-id="f3442-149">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="f3442-150">**Desabilitar o recurso de mensagem de relatório para Outlook**: Selecione essa opção se você usar ferramentas de relatório de terceiros em vez do suplemento de mensagem de relatório ou os relatórios internos no Outlook na Web e, em seguida, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="f3442-150">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="f3442-151">Selecione **usar esta caixa de correio personalizada para receber os envios relatados pelo usuário**.</span><span class="sxs-lookup"><span data-stu-id="f3442-151">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="f3442-152">Na caixa exibida, insira o endereço de email de uma caixa de correio existente que já está no Office 365.</span><span class="sxs-lookup"><span data-stu-id="f3442-152">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="f3442-153">Deve ser uma caixa de correio existente no Exchange Online que possa receber emails.</span><span class="sxs-lookup"><span data-stu-id="f3442-153">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="f3442-154">Quando tiver concluído, clique em **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f3442-154">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="f3442-155">Formato de envio de mensagens</span><span class="sxs-lookup"><span data-stu-id="f3442-155">Message submission format</span></span>

<span data-ttu-id="f3442-156">As mensagens enviadas para caixas de correio personalizadas precisam seguir um formato de email de envio específico.</span><span class="sxs-lookup"><span data-stu-id="f3442-156">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="f3442-157">O assunto (título do envelope) do envio deve estar neste formato:</span><span class="sxs-lookup"><span data-stu-id="f3442-157">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessgeId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="f3442-158">SafetyAPIAction é um dos seguintes valores inteiros:</span><span class="sxs-lookup"><span data-stu-id="f3442-158">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="f3442-159">1: lixo eletrônico</span><span class="sxs-lookup"><span data-stu-id="f3442-159">1: Junk</span></span>
- <span data-ttu-id="f3442-160">2: não é lixo eletrônico</span><span class="sxs-lookup"><span data-stu-id="f3442-160">2: NotJunk</span></span>
- <span data-ttu-id="f3442-161">3: Phish</span><span class="sxs-lookup"><span data-stu-id="f3442-161">3: Phish</span></span>

<span data-ttu-id="f3442-162">No exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="f3442-162">In the following example:</span></span>

- <span data-ttu-id="f3442-163">A mensagem está sendo relatada como phishing.</span><span class="sxs-lookup"><span data-stu-id="f3442-163">The message is being reported as Phish.</span></span>
- <span data-ttu-id="f3442-164">A ID da mensagem de rede é 49871234-6dc6-43e8-ABCD-08d797f20abe.</span><span class="sxs-lookup"><span data-stu-id="f3442-164">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="f3442-165">O IP do remetente é 167.220.232.101.</span><span class="sxs-lookup"><span data-stu-id="f3442-165">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="f3442-166">O endereço de é test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f3442-166">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="f3442-167">A linha de assunto da mensagem é "testar envio de phishing"</span><span class="sxs-lookup"><span data-stu-id="f3442-167">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="f3442-168">As mensagens que não seguem esse formato não serão exibidas corretamente no portal de envios.</span><span class="sxs-lookup"><span data-stu-id="f3442-168">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
