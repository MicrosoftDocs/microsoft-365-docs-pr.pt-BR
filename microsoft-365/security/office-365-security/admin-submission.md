---
title: Envios de administrador
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o portal de Envios no Centro de Conformidade e Segurança & para enviar emails suspeitos, emails suspeitos de phishing, spam e outras mensagens potencialmente prejudiciais, URLs e arquivos à Microsoft para verificação.
ms.openlocfilehash: 432a245530d7906ae8babbc54176480d36315351
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864943"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="05141-103">Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft</span><span class="sxs-lookup"><span data-stu-id="05141-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="05141-104">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online, os administradores podem usar o portal de Envios no Centro de Conformidade & e Segurança para enviar mensagens de email, URLs e anexos à Microsoft para verificação.</span><span class="sxs-lookup"><span data-stu-id="05141-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="05141-105">Ao enviar um email, você receberá informações sobre todas as políticas que possam ter permitido o email de entrada em seu locatário, bem como a análise de quaisquer URLs e anexos no email.</span><span class="sxs-lookup"><span data-stu-id="05141-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="05141-106">As políticas que podem ter permitido um email incluem a lista de remetentes seguros de um usuário individual, bem como políticas de nível de locatário, como regras de fluxo de emails do Exchange (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="05141-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="05141-107">Para outras maneiras de enviar mensagens de email, URLs e anexos à Microsoft, consulte Mensagens e arquivos [de relatório para a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="05141-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="05141-108">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="05141-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="05141-109">Você abrir o Centro de conformidade e segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="05141-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="05141-110">Para ir diretamente para a página **de** Envio, use <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="05141-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="05141-111">Para enviar mensagens e arquivos à Microsoft, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="05141-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="05141-112">**Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="05141-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="05141-113">**Gerenciamento de organização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="05141-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="05141-114">Observe que a associação nesse grupo de função é necessária para exibir [envios](#view-user-submissions-to-the-custom-mailbox) de usuário para a caixa de correio personalizada, conforme descrito posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="05141-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="05141-115">Para obter mais informações sobre como os usuários podem enviar mensagens e arquivos à Microsoft, consulte [Mensagens e arquivos de relatório para a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="05141-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="05141-116">Relatar conteúdo suspeito à Microsoft</span><span class="sxs-lookup"><span data-stu-id="05141-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="05141-117">No Centro de Conformidade & segurança,  vá para Envios de gerenciamento de ameaças, verifique se você está na guia Envios de Administrador e clique em \>  **Novo envio.** </span><span class="sxs-lookup"><span data-stu-id="05141-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="05141-118">Use **o sub80** de envio novo que aparece para enviar a mensagem, a URL ou o anexo, conforme descrito nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="05141-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="05141-119">Enviar um email questionável para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="05141-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="05141-120">Na seção **Tipo de objeto,** selecione **Email**.</span><span class="sxs-lookup"><span data-stu-id="05141-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="05141-121">Na seção **Formato de** envio, use uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="05141-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="05141-122">**ID** da mensagem de rede: este é um valor guid que está disponível no header **X-MS-Exchange-Organization-Network-Message-Id** na mensagem ou no header **X-MS-Office365-Filtering-Correlation-Id** em mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="05141-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="05141-123">**Arquivo:** clique **em Escolher arquivo.**</span><span class="sxs-lookup"><span data-stu-id="05141-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="05141-124">Na caixa de diálogo que abre, encontre e selecione o arquivo .eml ou .msg e clique em **Abrir.**</span><span class="sxs-lookup"><span data-stu-id="05141-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="05141-125">Os administradores com o Defender para Office 365 Plano 1 ou Plano 2 podem enviar mensagens com até 30 dias.</span><span class="sxs-lookup"><span data-stu-id="05141-125">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="05141-126">Outros administradores só poderão voltar 7 dias.</span><span class="sxs-lookup"><span data-stu-id="05141-126">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="05141-127">Na seção **Destinatários,** especifique um ou mais destinatários para os quais você gostaria de executar uma verificação de política.</span><span class="sxs-lookup"><span data-stu-id="05141-127">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="05141-128">A verificação de política determinará se o email burlou a verificação devido às políticas do usuário ou da organização.</span><span class="sxs-lookup"><span data-stu-id="05141-128">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="05141-129">Na seção **Motivo do envio,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="05141-129">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="05141-130">**Não deveria ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="05141-130">**Should not have been blocked**</span></span>

   - <span data-ttu-id="05141-131">**Deve ter sido bloqueado:** Selecionar **Spam,** **Phishing** ou **Malware.**</span><span class="sxs-lookup"><span data-stu-id="05141-131">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="05141-132">Se você não tiver certeza, use seu melhor bom senso.</span><span class="sxs-lookup"><span data-stu-id="05141-132">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="05141-133">Quando terminar, clique no **botão** Enviar.</span><span class="sxs-lookup"><span data-stu-id="05141-133">When you're finished, click the **Submit** button.</span></span>

![Exemplo de envio de URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="05141-135">Enviar uma URL suspeita para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="05141-135">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="05141-136">Na seção **Tipo de objeto,** selecione **URL**.</span><span class="sxs-lookup"><span data-stu-id="05141-136">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="05141-137">Na caixa exibida, insira a URL completa (por exemplo, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="05141-137">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="05141-138">Na seção **Motivo do envio,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="05141-138">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="05141-139">**Não deveria ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="05141-139">**Should not have been blocked**</span></span>

   - <span data-ttu-id="05141-140">**Deve ter sido bloqueado:** Selecionar **Phishing** ou **Malware.**</span><span class="sxs-lookup"><span data-stu-id="05141-140">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="05141-141">Quando terminar, clique no **botão** Enviar.</span><span class="sxs-lookup"><span data-stu-id="05141-141">When you're finished, click the **Submit** button.</span></span>

![Exemplo de envio de email](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="05141-143">Enviar um arquivo suspeito para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="05141-143">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="05141-144">Na seção **Tipo de objeto,** selecione **Anexo**.</span><span class="sxs-lookup"><span data-stu-id="05141-144">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="05141-145">Clique **em Escolher Arquivo.**</span><span class="sxs-lookup"><span data-stu-id="05141-145">Click **Choose File**.</span></span> <span data-ttu-id="05141-146">Na caixa de diálogo que é aberta, encontre e selecione o arquivo e clique em **Abrir.**</span><span class="sxs-lookup"><span data-stu-id="05141-146">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="05141-147">Na seção **Motivo do envio,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="05141-147">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="05141-148">**Não deveria ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="05141-148">**Should not have been blocked**</span></span>

   - <span data-ttu-id="05141-149">**Deve ter sido bloqueado:** **o malware** é a única opção e é selecionado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="05141-149">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="05141-150">Quando terminar, clique no **botão** Enviar.</span><span class="sxs-lookup"><span data-stu-id="05141-150">When you're finished, click the **Submit** button.</span></span>

![Exemplo de envio de anexo](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="05141-152">Exibir envios de administrador</span><span class="sxs-lookup"><span data-stu-id="05141-152">View admin submissions</span></span>

<span data-ttu-id="05141-153">No Centro de Conformidade & segurança,  vá para Envios de gerenciamento de ameaças, verifique se você está na guia Envios de Administrador e clique em \>  **Novo envio.** </span><span class="sxs-lookup"><span data-stu-id="05141-153">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="05141-154">Na parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão) filtrar pela **ID** de Envio (um valor GUID atribuído a cada envio) inserindo um valor na caixa e clicando no botão ![ ](../../media/scc-quarantine-refresh.png) Atualizar.</span><span class="sxs-lookup"><span data-stu-id="05141-154">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="05141-155">Update</span><span class="sxs-lookup"><span data-stu-id="05141-155">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="05141-156">Para alterar os critérios de filtro, clique no **botão ID de** Envio e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="05141-156">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="05141-157">**Sender**</span><span class="sxs-lookup"><span data-stu-id="05141-157">**Sender**</span></span>
- <span data-ttu-id="05141-158">**Assunto/URL/Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="05141-158">**Subject/URL/File name**</span></span>
- <span data-ttu-id="05141-159">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="05141-159">**Submitted by**</span></span>
- <span data-ttu-id="05141-160">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="05141-160">**Submission type**</span></span>
- <span data-ttu-id="05141-161">**Status**</span><span class="sxs-lookup"><span data-stu-id="05141-161">**Status**</span></span>

![Opções de filtro para envios de administrador](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="05141-163">Para exportar os resultados, clique **em Exportar** próximo à parte superior da página e selecione **Chart data** ou **Table**.</span><span class="sxs-lookup"><span data-stu-id="05141-163">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="05141-164">Na caixa de diálogo exibida, salve o arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="05141-164">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="05141-165">Abaixo do gráfico, há três guias: **Email** (padrão), **URL** e **Anexo.**</span><span class="sxs-lookup"><span data-stu-id="05141-165">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="05141-166">Exibir envios de email de administrador</span><span class="sxs-lookup"><span data-stu-id="05141-166">View admin email submissions</span></span>

<span data-ttu-id="05141-167">Clique na **guia Email.**</span><span class="sxs-lookup"><span data-stu-id="05141-167">Click the **Email** tab.</span></span>

<span data-ttu-id="05141-168">Você pode clicar **no botão Opções de** coluna na parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="05141-168">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="05141-169">**Date**</span><span class="sxs-lookup"><span data-stu-id="05141-169">**Date**</span></span>
- <span data-ttu-id="05141-170">**ID de** envio: um valor GUID atribuído a cada envio.</span><span class="sxs-lookup"><span data-stu-id="05141-170">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="05141-171">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05141-171">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="05141-172">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05141-172">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="05141-173">**Sender**</span><span class="sxs-lookup"><span data-stu-id="05141-173">**Sender**</span></span>
- <span data-ttu-id="05141-174">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05141-174">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="05141-175">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="05141-175">**Submission type**</span></span>
- <span data-ttu-id="05141-176">**Motivo da entrega**</span><span class="sxs-lookup"><span data-stu-id="05141-176">**Delivery reason**</span></span>
- <span data-ttu-id="05141-177">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05141-177">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="05141-178"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um flyout.</span><span class="sxs-lookup"><span data-stu-id="05141-178"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="05141-179">Detalhes de verificação de envio de administrador</span><span class="sxs-lookup"><span data-stu-id="05141-179">Admin submission rescan details</span></span>

<span data-ttu-id="05141-180">As mensagens enviadas nos envios de administrador são novamente exibidas e os resultados são mostrados no submenu de detalhes:</span><span class="sxs-lookup"><span data-stu-id="05141-180">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="05141-181">Se houve uma falha na autenticação de email do remetente no momento da entrega.</span><span class="sxs-lookup"><span data-stu-id="05141-181">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="05141-182">Informações sobre quaisquer acertos de política que poderiam ter afetado ou substituído o veredito de uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="05141-182">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="05141-183">Resultados de detonação atuais para ver se as URLs ou arquivos contidos na mensagem são mal-intencionados ou não.</span><span class="sxs-lookup"><span data-stu-id="05141-183">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="05141-184">Comentários dos alunos.</span><span class="sxs-lookup"><span data-stu-id="05141-184">Feedback from graders.</span></span>

<span data-ttu-id="05141-185">Se uma substituição foi encontrada, a verificação novamente deve ser concluída em vários minutos.</span><span class="sxs-lookup"><span data-stu-id="05141-185">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="05141-186">Se não houve um problema na autenticação ou na entrega de email não tiver sido afetado por uma substituição, o feedback dos alunos pode levar até um dia.</span><span class="sxs-lookup"><span data-stu-id="05141-186">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="05141-187">Exibir envios de URL de administrador</span><span class="sxs-lookup"><span data-stu-id="05141-187">View admin URL submissions</span></span>

<span data-ttu-id="05141-188">Clique na **guia URL.**</span><span class="sxs-lookup"><span data-stu-id="05141-188">Click the **URL** tab.</span></span>

<span data-ttu-id="05141-189">Você pode clicar **no botão Opções de** coluna na parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="05141-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="05141-190">**Date**</span><span class="sxs-lookup"><span data-stu-id="05141-190">**Date**</span></span>
- <span data-ttu-id="05141-191">**ID de envio**</span><span class="sxs-lookup"><span data-stu-id="05141-191">**Submission ID**</span></span>
- <span data-ttu-id="05141-192">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05141-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="05141-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05141-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="05141-194">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="05141-194">**Submission type**</span></span>
- <span data-ttu-id="05141-195">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05141-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="05141-196"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um flyout.</span><span class="sxs-lookup"><span data-stu-id="05141-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="05141-197">Exibir envios de anexo de administrador</span><span class="sxs-lookup"><span data-stu-id="05141-197">View admin attachment submissions</span></span>

<span data-ttu-id="05141-198">Clique na **guia Anexos.**</span><span class="sxs-lookup"><span data-stu-id="05141-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="05141-199">Você pode clicar **no botão Opções de** coluna na parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="05141-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="05141-200">**Date**</span><span class="sxs-lookup"><span data-stu-id="05141-200">**Date**</span></span>
- <span data-ttu-id="05141-201">**ID de envio**</span><span class="sxs-lookup"><span data-stu-id="05141-201">**Submission ID**</span></span>
- <span data-ttu-id="05141-202">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05141-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="05141-203">**Nome do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05141-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="05141-204">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="05141-204">**Submission type**</span></span>
- <span data-ttu-id="05141-205">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05141-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="05141-206"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um flyout.</span><span class="sxs-lookup"><span data-stu-id="05141-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="05141-207">Exibir envios de usuário para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="05141-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="05141-208">Se você implantou o complemento Mensagem de [Relatório,](enable-the-report-message-add-in.md)o relatório [de phishing](enable-the-report-phish-add-in.md)ou as pessoas usam os relatórios integrados no [Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), você pode ver o que os usuários estão relatando na guia **Envios** de usuário.</span><span class="sxs-lookup"><span data-stu-id="05141-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="05141-209">No Centro de Conformidade & segurança, vá para Envios **de gerenciamento** \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="05141-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="05141-210">Selecione a **guia Envios de** usuário e clique em **Novo envio.**</span><span class="sxs-lookup"><span data-stu-id="05141-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="05141-211">Você pode clicar **no botão Opções de** coluna na parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="05141-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="05141-212">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="05141-212">**Submitted on**</span></span>
- <span data-ttu-id="05141-213">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05141-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="05141-214">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05141-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="05141-215">**Sender**</span><span class="sxs-lookup"><span data-stu-id="05141-215">**Sender**</span></span>
- <span data-ttu-id="05141-216">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05141-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="05141-217">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="05141-217">**Submission type**</span></span>

<span data-ttu-id="05141-218"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um flyout.</span><span class="sxs-lookup"><span data-stu-id="05141-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="05141-219">Na parte superior da página, você pode inserir uma data de início, uma  data de término e (por padrão) filtrar por Remetente inserindo um valor na caixa e clicando no botão ![ ](../../media/scc-quarantine-refresh.png) Atualizar.</span><span class="sxs-lookup"><span data-stu-id="05141-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="05141-220">Update</span><span class="sxs-lookup"><span data-stu-id="05141-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="05141-221">Para alterar os critérios de filtro, clique **no botão** Remetente e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="05141-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="05141-222">**Domínio do remetente**</span><span class="sxs-lookup"><span data-stu-id="05141-222">**Sender domain**</span></span>
- <span data-ttu-id="05141-223">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="05141-223">**Subject**</span></span>
- <span data-ttu-id="05141-224">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="05141-224">**Submitted by**</span></span>
- <span data-ttu-id="05141-225">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="05141-225">**Submission type**</span></span>
- <span data-ttu-id="05141-226">**IP do remetente**</span><span class="sxs-lookup"><span data-stu-id="05141-226">**Sender IP**</span></span>

![Opções de filtro para envios de usuário](../../media/user-submissions-filter-options.png)

<span data-ttu-id="05141-228">Para exportar os resultados, clique **em Exportar** próximo à parte superior da página e selecione **Chart data** ou **Table**.</span><span class="sxs-lookup"><span data-stu-id="05141-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="05141-229">Na caixa de diálogo exibida, salve o arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="05141-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="05141-230">Exibir envios de usuário para a caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="05141-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="05141-231">**Se** você configurou [uma caixa de](user-submission.md) correio personalizada para receber mensagens relatadas pelo usuário, você pode exibir e também enviar mensagens que foram entregues à caixa de correio de relatório.</span><span class="sxs-lookup"><span data-stu-id="05141-231">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="05141-232">No Centro de Conformidade & segurança, vá para Envios **de gerenciamento** \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="05141-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="05141-233">Selecione a **guia Caixa de Correio** Personalizada.</span><span class="sxs-lookup"><span data-stu-id="05141-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="05141-234">Você pode clicar **no botão Opções de** coluna na parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="05141-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="05141-235">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="05141-235">**Submitted on**</span></span>
- <span data-ttu-id="05141-236">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05141-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="05141-237">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05141-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="05141-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="05141-238">**Sender**</span></span>
- <span data-ttu-id="05141-239">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05141-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="05141-240">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="05141-240">**Submission type**</span></span>

<span data-ttu-id="05141-241">Na parte superior da página, você pode inserir uma data de início, uma data de término e pode filtrar por **Submitted** inserindo um valor na caixa e clicando no botão ![ ](../../media/scc-quarantine-refresh.png) Atualizar.</span><span class="sxs-lookup"><span data-stu-id="05141-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="05141-242">Update</span><span class="sxs-lookup"><span data-stu-id="05141-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="05141-243">Para exportar os resultados, clique **em Exportar** próximo à parte superior da página e selecione **Chart data** ou **Table**.</span><span class="sxs-lookup"><span data-stu-id="05141-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="05141-244">Na caixa de diálogo exibida, salve o arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="05141-244">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="05141-245">Desfazer envios de usuário</span><span class="sxs-lookup"><span data-stu-id="05141-245">Undo user submissions</span></span>

<span data-ttu-id="05141-246">Depois que um usuário envia um email suspeito para a caixa de correio personalizada, o usuário e o administrador não têm a opção de desfazer o envio.</span><span class="sxs-lookup"><span data-stu-id="05141-246">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="05141-247">Se o usuário quiser recuperar o email, ele estará disponível para recuperação nas pastas Itens Excluídos ou Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="05141-247">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="05141-248">Enviar mensagens para a Microsoft da caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="05141-248">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="05141-249">Se você configurou a caixa de correio personalizada para interceptar mensagens relatadas pelo usuário sem enviar as mensagens para a Microsoft, você pode encontrar e enviar mensagens específicas para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="05141-249">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="05141-250">Isso efetivamente move um envio de usuário para um envio de administrador.</span><span class="sxs-lookup"><span data-stu-id="05141-250">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="05141-251">Na guia **Caixa de Correio** Personalizada, selecione  uma mensagem na lista, clique no botão Ação e faça uma das seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="05141-251">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="05141-252">**Relatório limpo**</span><span class="sxs-lookup"><span data-stu-id="05141-252">**Report clean**</span></span>
- <span data-ttu-id="05141-253">**Relatar phishing**</span><span class="sxs-lookup"><span data-stu-id="05141-253">**Report phishing**</span></span>
- <span data-ttu-id="05141-254">**Relatar malware**</span><span class="sxs-lookup"><span data-stu-id="05141-254">**Report malware**</span></span>
- <span data-ttu-id="05141-255">**Relatar spam**</span><span class="sxs-lookup"><span data-stu-id="05141-255">**Report spam**</span></span>

![Opções no botão Ação](../../media/user-submission-custom-mailbox-action-button.png)
