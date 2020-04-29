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
ms.openlocfilehash: a3a175c3815c6750086526ec92d097fb7cbcefa3
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2020
ms.locfileid: "43922658"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-office-365"></a><span data-ttu-id="a44e5-103">Especificar uma caixa de correio para envios de spam e mensagens de phishing no Office 365</span><span class="sxs-lookup"><span data-stu-id="a44e5-103">Specify a mailbox for user submissions of spam and phishing messages in Office 365</span></span>

<span data-ttu-id="a44e5-104">Nas organizações do Office 365 com caixas de correio do Exchange Online, você pode especificar uma caixa de correio para receber mensagens que os usuários relatam como mal-intencionadas ou não mal intencionadas.</span><span class="sxs-lookup"><span data-stu-id="a44e5-104">In Office 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="a44e5-105">Quando os usuários enviam mensagens usando as várias opções de relatórios, você pode usar essa caixa de correio para interceptar mensagens (enviar somente para a caixa de correio personalizada) ou receber cópias de mensagens (enviar para a caixa de correio personalizada e Microsoft).</span><span class="sxs-lookup"><span data-stu-id="a44e5-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="a44e5-106">Este recurso funciona com as seguintes opções de relatório de mensagens:</span><span class="sxs-lookup"><span data-stu-id="a44e5-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="a44e5-107">O suplemento de mensagem de relatório</span><span class="sxs-lookup"><span data-stu-id="a44e5-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="a44e5-108">[Relatórios internos no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (anteriormente conhecido como Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="a44e5-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

<span data-ttu-id="a44e5-109">Você também pode configurar ferramentas de relatório de mensagens de terceiros para encaminhar mensagens para a caixa de correio que você especificar.</span><span class="sxs-lookup"><span data-stu-id="a44e5-109">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="a44e5-110">O fornecimento de mensagens relatadas pelo usuário para uma caixa de correio personalizada em vez de diretamente para a Microsoft permite que os administradores reportem mensagens de forma seletiva e manual para a Microsoft usando o [envio do administrador](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="a44e5-110">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a44e5-111">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="a44e5-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a44e5-112">Você abrir o Centro de conformidade e segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="a44e5-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a44e5-113">Para ir diretamente para a página **envios de usuários** , use <https://protection.office.com/userSubmissionsReportMessage>.</span><span class="sxs-lookup"><span data-stu-id="a44e5-113">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="a44e5-114">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a44e5-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a44e5-115">Para se conectar ao PowerShell da Proteção do Exchange Online autônoma, confira [Conectar ao PowerShell da Proteção do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="a44e5-115">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a44e5-116">Você precisa receber permissões para executar esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="a44e5-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="a44e5-117">Para configurar a caixa de correio para envios de usuários, você precisa ser membro dos grupos de função de **Gerenciamento da organização** ou de **administrador de segurança** .</span><span class="sxs-lookup"><span data-stu-id="a44e5-117">To configure the mailbox for user submissions, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="a44e5-118">Para obter mais informações sobre grupos de funções no Centro de Conformidade e Segurança, confira [Permissões no Centro de conformidade e Segurança do Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a44e5-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="a44e5-119">Usar o centro de conformidade de & de segurança para configurar a caixa de correio de envios de usuários</span><span class="sxs-lookup"><span data-stu-id="a44e5-119">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="a44e5-120">No centro de conformidade & segurança, vá para **envios do usuário**da **política** \> de **Gerenciamento** \> de ameaças.</span><span class="sxs-lookup"><span data-stu-id="a44e5-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="a44e5-121">Na página **envios de usuários** que aparece, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="a44e5-121">In the **User submissions** page that appears, select one of the following options:</span></span>

   - <span data-ttu-id="a44e5-122">**Habilitar o recurso de mensagem de relatório para o Outlook (recomendado)**: Selecione essa opção se você usar o suplemento de mensagem de relatório ou os relatórios internos no Outlook na Web e, em seguida, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a44e5-122">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     - <span data-ttu-id="a44e5-123">**Personalizar a mensagem de confirmação do usuário final**: clique neste link.</span><span class="sxs-lookup"><span data-stu-id="a44e5-123">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="a44e5-124">No submenu **Personalizar mensagem de confirmação** que aparece, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a44e5-124">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

       - <span data-ttu-id="a44e5-125">**Antes do envio**: nas caixas de **mensagem** **título** e confirmação, insira o texto descritivo que os usuários veem antes de reportar uma mensagem usando o suplemento de mensagem de relatório.</span><span class="sxs-lookup"><span data-stu-id="a44e5-125">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="a44e5-126">Você pode usar a variável% Type% para incluir o tipo de envio (lixo eletrônico, não lixo eletrônico, Phish, etc.).</span><span class="sxs-lookup"><span data-stu-id="a44e5-126">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

         <span data-ttu-id="a44e5-127">Conforme observado, o texto a seguir também é adicionado à notificação:</span><span class="sxs-lookup"><span data-stu-id="a44e5-127">As noted, the following text is also added to the notification:</span></span>

         > <span data-ttu-id="a44e5-128">Seu email será enviado como é para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="a44e5-128">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="a44e5-129">Alguns emails podem conter informações pessoais ou confidenciais.</span><span class="sxs-lookup"><span data-stu-id="a44e5-129">Some emails might contain personal or sensitive information.</span></span>

       - <span data-ttu-id="a44e5-130">**Após o envio**: ![clique em](../../media/scc-expand-icon.png)ícone de expansão.</span><span class="sxs-lookup"><span data-stu-id="a44e5-130">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="a44e5-131">Nas caixas de mensagem **título** e **confirmação** , insira o texto descritivo que os usuários veem depois de reportar uma mensagem usando o suplemento de mensagem de relatório.</span><span class="sxs-lookup"><span data-stu-id="a44e5-131">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="a44e5-132">Você pode usar a variável% Type% para incluir o tipo de envio.</span><span class="sxs-lookup"><span data-stu-id="a44e5-132">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="a44e5-133">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a44e5-133">When you're finished, click **Save**.</span></span> <span data-ttu-id="a44e5-134">Para limpar esses valores, clique em **restaurar** novamente na página **envios de usuários** .</span><span class="sxs-lookup"><span data-stu-id="a44e5-134">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

   - <span data-ttu-id="a44e5-135">**Enviar as mensagens relatadas para**: faça uma das seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="a44e5-135">**Send the reported messages to**: Make one of the following selections:</span></span>

     - <span data-ttu-id="a44e5-136">**Microsoft (recomendado)**: a caixa de correio de envios do usuário não é usada (todas as mensagens relatadas vão para a Microsoft).</span><span class="sxs-lookup"><span data-stu-id="a44e5-136">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

     - <span data-ttu-id="a44e5-137">**Microsoft e uma caixa de correio personalizada**: na caixa exibida, insira o endereço de email de uma caixa de correio do Exchange Online existente.</span><span class="sxs-lookup"><span data-stu-id="a44e5-137">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span>

     - <span data-ttu-id="a44e5-138">Caixa de **correio personalizada**: na caixa exibida, insira o endereço de email de uma caixa de correio do Exchange Online existente.</span><span class="sxs-lookup"><span data-stu-id="a44e5-138">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span>

     <span data-ttu-id="a44e5-139">Quando tiver concluído, clique em **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a44e5-139">When you're finished, click **Confirm**.</span></span>

     ![Enviar mensagens relatadas para a Microsoft e uma caixa de correio personalizada](../../media/user-submission-enable-outlook-report-message.png)

   - <span data-ttu-id="a44e5-141">**Desabilitar o recurso de mensagem de relatório para Outlook**: Selecione essa opção se você usar ferramentas de relatório de terceiros em vez do suplemento de mensagem de relatório ou os relatórios internos no Outlook na Web e, em seguida, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a44e5-141">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     <span data-ttu-id="a44e5-142">Selecione **usar esta caixa de correio personalizada para receber os envios relatados pelo usuário**.</span><span class="sxs-lookup"><span data-stu-id="a44e5-142">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="a44e5-143">Na caixa exibida, insira o endereço de email de uma caixa de correio existente ou o endereço de email da caixa de correio que você deseja criar.</span><span class="sxs-lookup"><span data-stu-id="a44e5-143">In the box that appears, enter the email address of an existing mailbox, or the email address of the mailbox that you want to create.</span></span>

     <span data-ttu-id="a44e5-144">Quando tiver concluído, clique em **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="a44e5-144">When you're finished, click **Confirm**.</span></span>

     ![Enviar mensagens relatadas para uma caixa de correio personalizada usando ferramentas de terceiros](../../media/user-submission-disable-outlook-report-message.png)
