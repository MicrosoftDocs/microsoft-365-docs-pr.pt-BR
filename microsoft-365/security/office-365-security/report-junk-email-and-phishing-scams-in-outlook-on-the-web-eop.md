---
title: Relatar lixo eletrônico e email de phishing Outlook na Web
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
description: Os administradores podem aprender sobre as opções internas de relatório de lixo eletrônico, não lixo eletrônico e phishing no Outlook na Web (Outlook Web App) no Exchange Online e como desabilitar essas opções de relatórios para usuários.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788302"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="7d7cb-103">Relatar lixo eletrônico e phishing em Outlook na Web em Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7d7cb-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7d7cb-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="7d7cb-104">**Applies to**</span></span>
- [<span data-ttu-id="7d7cb-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7d7cb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="7d7cb-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="7d7cb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="7d7cb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7d7cb-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="7d7cb-108">Em organizações com caixas de correio em Exchange Online ou caixas [](../../enterprise/hybrid-modern-auth-overview.md)de correio locais usando autenticação moderna híbrida, você pode enviar falsos positivos (emails bons marcados como spam), falsos negativos (email ruim permitido) e mensagens de phishing para Proteção do Exchange Online (EOP). Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7d7cb-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7d7cb-109">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="7d7cb-109">What do you need to know before you begin?</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d7cb-110">Recomendamos o complemento Mensagem de Relatório ou o complemento Relatar Phishing para envios de usuários.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-110">We recommend the Report Message add-in or the Report Phishing add-in for user submissions.</span></span> <span data-ttu-id="7d7cb-111">Para obter mais informações, [consulte Enable the Report Message or the Report Phishing add-ins](./enable-the-report-message-add-in.md). Não recomendamos a experiência interna de relatório no Outlook porque ela não pode usar a [política de envio do usuário.](./user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="7d7cb-111">For more information, see [Enable the Report Message or the Report Phishing add-ins](./enable-the-report-message-add-in.md). We don't recommend the built-in reporting experience in Outlook because it can't use the [user submission policy](./user-submission.md).</span></span>

- <span data-ttu-id="7d7cb-112">Se você for um administrador em uma organização com Exchange Online caixas de correio, recomendamos que você use o portal Envios no Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-112">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="7d7cb-113">Para obter mais informações, [consulte Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="7d7cb-113">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="7d7cb-114">Os administradores podem desabilitar ou habilitar a capacidade de os usuários relatarem mensagens à Microsoft Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-114">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="7d7cb-115">Para obter detalhes, consulte [a seção Desabilitar ou](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) habilitar relatórios de lixo eletrônico Outlook na Web posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-115">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="7d7cb-116">Você pode configurar mensagens relatadas a serem copiadas ou redirecionadas para uma caixa de correio especificada.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="7d7cb-117">Para obter mais informações, consulte [Políticas de envios de usuário](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="7d7cb-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="7d7cb-118">Para obter mais informações sobre o relatório de mensagens para a Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="7d7cb-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="7d7cb-119">Desabilitar ou habilitar relatórios de lixo eletrônico Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="7d7cb-119">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="7d7cb-120">Por padrão, os usuários podem relatar falsos positivos de spam, falsos negativos e mensagens de phishing para a Microsoft para análise Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-120">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="7d7cb-121">Os administradores podem configurar Outlook nas políticas de caixa de correio da Web no Exchange Online PowerShell para impedir que os usuários reportem falsos positivos de spam e falsos negativos de spam para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-121">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="7d7cb-122">Não é possível desabilitar a capacidade de os usuários relatarem mensagens de phishing à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-122">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7d7cb-123">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="7d7cb-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7d7cb-124">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7d7cb-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="7d7cb-125">Você precisa ter permissões atribuídas Exchange Online antes de poder fazer os procedimentos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-125">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="7d7cb-126">Especificamente, você precisa das **funções Políticas** de Destinatário ou  Destinatários  de Email, que são **atribuídas** aos grupos de função Gerenciamento da Organização e Gerenciamento de Destinatários por padrão.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-126">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="7d7cb-127">Para obter mais informações sobre grupos de função Exchange Online, consulte Permissões no [Exchange Online](/exchange/permissions-exo/permissions-exo) e Modificar grupos de [função em Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="7d7cb-127">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="7d7cb-128">Cada organização tem uma política padrão chamada OwaMailboxPolicy-Default, mas você pode criar políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-128">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="7d7cb-129">Políticas personalizadas são aplicadas a usuários com escopo antes da política padrão.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-129">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="7d7cb-130">Para obter mais informações sobre Outlook nas políticas de caixa de correio da Web, consulte Outlook nas políticas de caixa de correio da [Web em Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span><span class="sxs-lookup"><span data-stu-id="7d7cb-130">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="7d7cb-131">Desabilitar relatórios de lixo eletrônico não remove a capacidade de marcar uma mensagem como lixo eletrônico ou não lixo eletrônico Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-131">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="7d7cb-132">Selecionar uma mensagem na pasta Lixo Eletrônico e clicar em Não lixo **eletrônico** Não lixo eletrônico ainda move a mensagem de \>  volta para a Caixa de Entrada.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-132">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="7d7cb-133">Selecionar uma mensagem em qualquer outra pasta de email e clicar em **Lixo** Eletrônico ainda move a mensagem \>  para a pasta Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-133">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="7d7cb-134">O que não está mais disponível é a opção de relatar a mensagem à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-134">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="7d7cb-135">Use Exchange Online PowerShell para desabilitar ou habilitar relatórios de lixo eletrônico Outlook na Web</span><span class="sxs-lookup"><span data-stu-id="7d7cb-135">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="7d7cb-136">Para encontrar suas informações Outlook nas políticas de caixa de correio da Web e o status do relatório de lixo eletrônico, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7d7cb-136">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="7d7cb-137">Para desabilitar ou habilitar relatórios de lixo eletrônico Outlook na Web, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="7d7cb-137">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="7d7cb-138">Este exemplo desabilita o relatório de lixo eletrônico na política padrão.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-138">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="7d7cb-139">Este exemplo habilita o relatório de lixo eletrônico na política personalizada denominada Gerentes da Contoso.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-139">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="7d7cb-140">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) e [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="7d7cb-140">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="7d7cb-141">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="7d7cb-141">How do you know this worked?</span></span>

<span data-ttu-id="7d7cb-142">Para verificar se você habilitar ou desabilitar com êxito o relatório de lixo eletrônico no Outlook na Web, use qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="7d7cb-142">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="7d7cb-143">No Exchange Online PowerShell, execute o seguinte comando e verifique o valor da propriedade **ReportJunkEmailEnabled:**</span><span class="sxs-lookup"><span data-stu-id="7d7cb-143">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="7d7cb-144">Abra a caixa de correio de um usuário afetado Outlook na Web,  selecione uma mensagem na Caixa de Entrada, clique em Lixo Eletrônico e verifique se o prompt para relatar a mensagem à Microsoft é ou não \>  exibido.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7d7cb-144">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="7d7cb-145">Abra a caixa de correio de um usuário afetado Outlook na Web, selecione  uma mensagem na pasta Lixo Eletrônico, clique em Lixo Eletrônico e verifique se o prompt para relatar a mensagem à Microsoft é ou não \>  exibido.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7d7cb-145">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="7d7cb-146"><sup>\*</sup> Os usuários podem ocultar o prompt para relatar a mensagem enquanto ainda relatam a mensagem.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-146"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="7d7cb-147">Para verificar essa configuração Outlook na Web:</span><span class="sxs-lookup"><span data-stu-id="7d7cb-147">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="7d7cb-148">Clique **Configurações** ![ Outlook no ícone configurações da Web ](../../media/owa-settings-icon.png) \> **Exibir todas as Outlook configurações** \> **Lixo eletrônico.**</span><span class="sxs-lookup"><span data-stu-id="7d7cb-148">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="7d7cb-149">Na seção **Relatórios,** verifique o valor: **Pergunte-me antes de enviar um relatório**.</span><span class="sxs-lookup"><span data-stu-id="7d7cb-149">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook configurações do Relatório de Lixo Eletrônico na Web](../../media/owa-junk-email-reporting-options.png)
