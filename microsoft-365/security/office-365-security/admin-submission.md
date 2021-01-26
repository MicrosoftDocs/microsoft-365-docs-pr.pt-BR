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
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o portal de Envios no Centro de Conformidade e Segurança & para enviar emails suspeitos, emails suspeitos de phishing, spam e outras mensagens potencialmente prejudiciais, URLs e arquivos à Microsoft para verificação.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 879a13e7c059495e653b79c424b227fe9f35a498
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2021
ms.locfileid: "49976598"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="bec2c-103">Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft</span><span class="sxs-lookup"><span data-stu-id="bec2c-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="bec2c-104">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online, os administradores podem usar o portal de Envios no Centro de Conformidade & e Segurança para enviar mensagens de email, URLs e anexos à Microsoft para verificação.</span><span class="sxs-lookup"><span data-stu-id="bec2c-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="bec2c-105">Ao enviar uma mensagem de email, você receberá:</span><span class="sxs-lookup"><span data-stu-id="bec2c-105">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="bec2c-106">**Verificação de autenticação de** email: Detalhes sobre se a autenticação de email passou ou falhou quando foi entregue.</span><span class="sxs-lookup"><span data-stu-id="bec2c-106">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="bec2c-107">**Visitas à** política: informações sobre quaisquer políticas que possam ter permitido ou bloqueado o email de entrada em seu locatário, substituindo nossos vereditos de filtro de serviço.</span><span class="sxs-lookup"><span data-stu-id="bec2c-107">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="bec2c-108">**Reputação/detonação da** carga: exame de quaisquer URLs e anexos na mensagem.</span><span class="sxs-lookup"><span data-stu-id="bec2c-108">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="bec2c-109">**Análise de nota:** revisão feita por notas humanas para confirmar se as mensagens são mal-intencionadas ou não.</span><span class="sxs-lookup"><span data-stu-id="bec2c-109">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bec2c-110">A reputação/a detonação da carga e a análise de classificação não são feitas em todos os locatários.</span><span class="sxs-lookup"><span data-stu-id="bec2c-110">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="bec2c-111">As informações são impedidas de sair da organização quando os dados não deveriam sair do limite do locatário para fins de conformidade.</span><span class="sxs-lookup"><span data-stu-id="bec2c-111">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="bec2c-112">Para outras maneiras de enviar mensagens de email, URLs e anexos à Microsoft, consulte Mensagens e arquivos [de relatório para a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="bec2c-112">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bec2c-113">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="bec2c-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="bec2c-114">Você abrir o Centro de conformidade e segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="bec2c-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="bec2c-115">Para ir diretamente para a página **de** Envio, use <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="bec2c-115">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="bec2c-116">Para enviar mensagens e arquivos à Microsoft, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="bec2c-116">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="bec2c-117">**Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="bec2c-117">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="bec2c-118">**Gerenciamento de organização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="bec2c-118">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="bec2c-119">Observe que a associação nesse grupo de função é necessária para exibir [envios](#view-user-submissions-to-the-custom-mailbox) de usuário para a caixa de correio personalizada, conforme descrito posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="bec2c-119">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="bec2c-120">Para obter mais informações sobre como os usuários podem enviar mensagens e arquivos à Microsoft, consulte [Mensagens e arquivos de relatório para a Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="bec2c-120">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="bec2c-121">Relatar conteúdo suspeito à Microsoft</span><span class="sxs-lookup"><span data-stu-id="bec2c-121">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="bec2c-122">No Centro de Conformidade & segurança,  vá para Envios de gerenciamento de ameaças, verifique se você está na guia Envios de Administrador e clique em \>  **Novo envio.** </span><span class="sxs-lookup"><span data-stu-id="bec2c-122">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="bec2c-123">Use **o sub80** de envio novo que aparece para enviar a mensagem, a URL ou o anexo, conforme descrito nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="bec2c-123">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="bec2c-124">Enviar um email questionável para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="bec2c-124">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="bec2c-125">Na seção **Tipo de objeto,** selecione **Email**.</span><span class="sxs-lookup"><span data-stu-id="bec2c-125">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="bec2c-126">Na seção **Formato de** envio, use uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="bec2c-126">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="bec2c-127">**ID** da mensagem de rede: este é um valor guid que está disponível no header **X-MS-Exchange-Organization-Network-Message-Id** na mensagem ou no header **X-MS-Office365-Filtering-Correlation-Id** em mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="bec2c-127">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="bec2c-128">**Arquivo:** clique **em Escolher arquivo.**</span><span class="sxs-lookup"><span data-stu-id="bec2c-128">**File**: Click **Choose file**.</span></span> <span data-ttu-id="bec2c-129">Na caixa de diálogo que abre, encontre e selecione o arquivo .eml ou .msg e clique em **Abrir.**</span><span class="sxs-lookup"><span data-stu-id="bec2c-129">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bec2c-130">Os administradores com o Defender para Office 365 Plano 1 ou Plano 2 podem enviar mensagens com até 30 dias.</span><span class="sxs-lookup"><span data-stu-id="bec2c-130">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="bec2c-131">Outros administradores só poderão voltar 7 dias.</span><span class="sxs-lookup"><span data-stu-id="bec2c-131">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="bec2c-132">Na seção **Destinatários,** especifique um ou mais destinatários para os quais você gostaria de executar uma verificação de política.</span><span class="sxs-lookup"><span data-stu-id="bec2c-132">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="bec2c-133">A verificação de política determinará se o email burlou a verificação devido a políticas de usuário ou organização.</span><span class="sxs-lookup"><span data-stu-id="bec2c-133">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="bec2c-134">Na seção **Motivo do envio,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="bec2c-134">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="bec2c-135">**Não deveria ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="bec2c-135">**Should not have been blocked**</span></span>

   - <span data-ttu-id="bec2c-136">**Deve ter sido bloqueado:** Selecionar **Spam,** **Phishing** ou **Malware.**</span><span class="sxs-lookup"><span data-stu-id="bec2c-136">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="bec2c-137">Se você não tiver certeza, use seu melhor bom senso.</span><span class="sxs-lookup"><span data-stu-id="bec2c-137">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="bec2c-138">Quando terminar, clique no **botão** Enviar.</span><span class="sxs-lookup"><span data-stu-id="bec2c-138">When you're finished, click the **Submit** button.</span></span>

   ![Exemplo de envio de URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="bec2c-140">Enviar uma URL suspeita para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="bec2c-140">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="bec2c-141">Na seção **Tipo de objeto,** selecione **URL**.</span><span class="sxs-lookup"><span data-stu-id="bec2c-141">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="bec2c-142">Na caixa exibida, insira a URL completa (por exemplo, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="bec2c-142">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="bec2c-143">Na seção **Motivo do envio,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="bec2c-143">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="bec2c-144">**Não deveria ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="bec2c-144">**Should not have been blocked**</span></span>

   - <span data-ttu-id="bec2c-145">**Deve ter sido bloqueado:** Selecionar **Phishing** ou **Malware.**</span><span class="sxs-lookup"><span data-stu-id="bec2c-145">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="bec2c-146">Quando terminar, clique no **botão** Enviar.</span><span class="sxs-lookup"><span data-stu-id="bec2c-146">When you're finished, click the **Submit** button.</span></span>

   ![Exemplo de envio de email](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="bec2c-148">Enviar um arquivo suspeito para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="bec2c-148">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="bec2c-149">Na seção **Tipo de objeto,** selecione **Anexo**.</span><span class="sxs-lookup"><span data-stu-id="bec2c-149">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="bec2c-150">Clique **em Escolher Arquivo.**</span><span class="sxs-lookup"><span data-stu-id="bec2c-150">Click **Choose File**.</span></span> <span data-ttu-id="bec2c-151">Na caixa de diálogo que é aberta, encontre e selecione o arquivo e clique em **Abrir.**</span><span class="sxs-lookup"><span data-stu-id="bec2c-151">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="bec2c-152">Na seção **Motivo do envio,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="bec2c-152">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="bec2c-153">**Não deveria ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="bec2c-153">**Should not have been blocked**</span></span>

   - <span data-ttu-id="bec2c-154">**Deve ter sido bloqueado:** **o malware** é a única opção e é selecionado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bec2c-154">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="bec2c-155">Quando terminar, clique no **botão** Enviar.</span><span class="sxs-lookup"><span data-stu-id="bec2c-155">When you're finished, click the **Submit** button.</span></span>

   ![Exemplo de envio de anexo](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="bec2c-157">Exibir envios de administrador</span><span class="sxs-lookup"><span data-stu-id="bec2c-157">View admin submissions</span></span>

<span data-ttu-id="bec2c-158">No Centro de Conformidade & segurança,  vá para Envios de gerenciamento de ameaças, verifique se você está na guia Envios de Administrador e clique em \>  **Novo envio.** </span><span class="sxs-lookup"><span data-stu-id="bec2c-158">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="bec2c-159">Na parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão) filtrar pela **ID** de Envio (um valor GUID atribuído a cada envio) inserindo um valor na caixa e clicando no botão ![ ](../../media/scc-quarantine-refresh.png) Atualizar.</span><span class="sxs-lookup"><span data-stu-id="bec2c-159">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="bec2c-160">Update</span><span class="sxs-lookup"><span data-stu-id="bec2c-160">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="bec2c-161">Para alterar os critérios de filtro, clique no **botão ID de** Envio e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="bec2c-161">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="bec2c-162">**Sender**</span><span class="sxs-lookup"><span data-stu-id="bec2c-162">**Sender**</span></span>
- <span data-ttu-id="bec2c-163">**Assunto/URL/Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="bec2c-163">**Subject/URL/File name**</span></span>
- <span data-ttu-id="bec2c-164">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="bec2c-164">**Submitted by**</span></span>
- <span data-ttu-id="bec2c-165">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="bec2c-165">**Submission type**</span></span>
- <span data-ttu-id="bec2c-166">**Status**</span><span class="sxs-lookup"><span data-stu-id="bec2c-166">**Status**</span></span>

![Opções de filtro para envios de administrador](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="bec2c-168">Para exportar os resultados, clique **em Exportar** próximo à parte superior da página e selecione **Chart data** ou **Table**.</span><span class="sxs-lookup"><span data-stu-id="bec2c-168">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="bec2c-169">Na caixa de diálogo exibida, salve o arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="bec2c-169">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="bec2c-170">Abaixo do gráfico, há três guias: **Email** (padrão), **URL** e **Anexo.**</span><span class="sxs-lookup"><span data-stu-id="bec2c-170">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="bec2c-171">Exibir envios de email de administrador</span><span class="sxs-lookup"><span data-stu-id="bec2c-171">View admin email submissions</span></span>

<span data-ttu-id="bec2c-172">Clique na **guia Email.**</span><span class="sxs-lookup"><span data-stu-id="bec2c-172">Click the **Email** tab.</span></span>

<span data-ttu-id="bec2c-173">Você pode clicar **no botão Opções de** coluna na parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="bec2c-173">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="bec2c-174">**Date**</span><span class="sxs-lookup"><span data-stu-id="bec2c-174">**Date**</span></span>
- <span data-ttu-id="bec2c-175">**ID de** envio: um valor GUID atribuído a cada envio.</span><span class="sxs-lookup"><span data-stu-id="bec2c-175">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="bec2c-176">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bec2c-176">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="bec2c-177">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bec2c-177">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="bec2c-178">**Sender**</span><span class="sxs-lookup"><span data-stu-id="bec2c-178">**Sender**</span></span>
- <span data-ttu-id="bec2c-179">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bec2c-179">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="bec2c-180">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="bec2c-180">**Submission type**</span></span>
- <span data-ttu-id="bec2c-181">**Motivo da entrega**</span><span class="sxs-lookup"><span data-stu-id="bec2c-181">**Delivery reason**</span></span>
- <span data-ttu-id="bec2c-182">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bec2c-182">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="bec2c-183"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um flyout.</span><span class="sxs-lookup"><span data-stu-id="bec2c-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="bec2c-184">Detalhes de verificação de envio de administrador</span><span class="sxs-lookup"><span data-stu-id="bec2c-184">Admin submission rescan details</span></span>

<span data-ttu-id="bec2c-185">As mensagens enviadas nos envios de administrador são novamente exibidas e os resultados são mostrados no submenu de detalhes:</span><span class="sxs-lookup"><span data-stu-id="bec2c-185">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="bec2c-186">Se houve uma falha na autenticação de email do remetente no momento da entrega.</span><span class="sxs-lookup"><span data-stu-id="bec2c-186">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="bec2c-187">Informações sobre quaisquer acertos de política que poderiam ter afetado ou substituído o veredito de uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="bec2c-187">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="bec2c-188">Resultados de detonação atuais para ver se as URLs ou arquivos contidos na mensagem são mal-intencionados ou não.</span><span class="sxs-lookup"><span data-stu-id="bec2c-188">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="bec2c-189">Comentários dos alunos.</span><span class="sxs-lookup"><span data-stu-id="bec2c-189">Feedback from graders.</span></span>

<span data-ttu-id="bec2c-190">Se uma substituição foi encontrada, a verificação novamente deve ser concluída em vários minutos.</span><span class="sxs-lookup"><span data-stu-id="bec2c-190">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="bec2c-191">Se não houve um problema na autenticação ou na entrega de email não tiver sido afetado por uma substituição, o feedback dos alunos pode levar até um dia.</span><span class="sxs-lookup"><span data-stu-id="bec2c-191">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="bec2c-192">Exibir envios de URL de administrador</span><span class="sxs-lookup"><span data-stu-id="bec2c-192">View admin URL submissions</span></span>

<span data-ttu-id="bec2c-193">Clique na **guia URL.**</span><span class="sxs-lookup"><span data-stu-id="bec2c-193">Click the **URL** tab.</span></span>

<span data-ttu-id="bec2c-194">Você pode clicar **no botão Opções de** coluna na parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="bec2c-194">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="bec2c-195">**Date**</span><span class="sxs-lookup"><span data-stu-id="bec2c-195">**Date**</span></span>
- <span data-ttu-id="bec2c-196">**ID de envio**</span><span class="sxs-lookup"><span data-stu-id="bec2c-196">**Submission ID**</span></span>
- <span data-ttu-id="bec2c-197">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bec2c-197">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="bec2c-198">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bec2c-198">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="bec2c-199">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="bec2c-199">**Submission type**</span></span>
- <span data-ttu-id="bec2c-200">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bec2c-200">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="bec2c-201"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um flyout.</span><span class="sxs-lookup"><span data-stu-id="bec2c-201"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="bec2c-202">Exibir envios de anexo de administrador</span><span class="sxs-lookup"><span data-stu-id="bec2c-202">View admin attachment submissions</span></span>

<span data-ttu-id="bec2c-203">Clique na **guia Anexos.**</span><span class="sxs-lookup"><span data-stu-id="bec2c-203">Click the **Attachments** tab.</span></span>

<span data-ttu-id="bec2c-204">Você pode clicar **no botão Opções de** coluna na parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="bec2c-204">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="bec2c-205">**Date**</span><span class="sxs-lookup"><span data-stu-id="bec2c-205">**Date**</span></span>
- <span data-ttu-id="bec2c-206">**ID de envio**</span><span class="sxs-lookup"><span data-stu-id="bec2c-206">**Submission ID**</span></span>
- <span data-ttu-id="bec2c-207">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bec2c-207">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="bec2c-208">**Nome do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bec2c-208">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="bec2c-209">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="bec2c-209">**Submission type**</span></span>
- <span data-ttu-id="bec2c-210">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bec2c-210">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="bec2c-211"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um flyout.</span><span class="sxs-lookup"><span data-stu-id="bec2c-211"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="bec2c-212">Exibir envios de usuário para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="bec2c-212">View user submissions to Microsoft</span></span>

<span data-ttu-id="bec2c-213">Se você implantou o complemento Mensagem de [Relatório,](enable-the-report-message-add-in.md)o relatório [de phishing](enable-the-report-phish-add-in.md)ou as pessoas usam os relatórios integrados no [Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), você pode ver o que os usuários estão relatando na guia **Envios** de usuário.</span><span class="sxs-lookup"><span data-stu-id="bec2c-213">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="bec2c-214">No Centro de Conformidade & segurança, vá para Envios **de gerenciamento** \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="bec2c-214">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="bec2c-215">Selecione a **guia Envios de** usuário e clique em **Novo envio.**</span><span class="sxs-lookup"><span data-stu-id="bec2c-215">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="bec2c-216">Você pode clicar **no botão Opções de** coluna na parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="bec2c-216">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="bec2c-217">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="bec2c-217">**Submitted on**</span></span>
- <span data-ttu-id="bec2c-218">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bec2c-218">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="bec2c-219">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bec2c-219">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="bec2c-220">**Sender**</span><span class="sxs-lookup"><span data-stu-id="bec2c-220">**Sender**</span></span>
- <span data-ttu-id="bec2c-221">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bec2c-221">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="bec2c-222">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="bec2c-222">**Submission type**</span></span>

<span data-ttu-id="bec2c-223"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um flyout.</span><span class="sxs-lookup"><span data-stu-id="bec2c-223"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="bec2c-224">Na parte superior da página, você pode inserir uma data de início, uma  data de término e (por padrão) filtrar por Remetente inserindo um valor na caixa e clicando no botão ![ ](../../media/scc-quarantine-refresh.png) Atualizar.</span><span class="sxs-lookup"><span data-stu-id="bec2c-224">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="bec2c-225">Update</span><span class="sxs-lookup"><span data-stu-id="bec2c-225">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="bec2c-226">Para alterar os critérios de filtro, clique **no botão** Remetente e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="bec2c-226">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="bec2c-227">**Domínio do remetente**</span><span class="sxs-lookup"><span data-stu-id="bec2c-227">**Sender domain**</span></span>
- <span data-ttu-id="bec2c-228">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="bec2c-228">**Subject**</span></span>
- <span data-ttu-id="bec2c-229">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="bec2c-229">**Submitted by**</span></span>
- <span data-ttu-id="bec2c-230">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="bec2c-230">**Submission type**</span></span>
- <span data-ttu-id="bec2c-231">**IP do remetente**</span><span class="sxs-lookup"><span data-stu-id="bec2c-231">**Sender IP**</span></span>

![Opções de filtro para envios de usuário](../../media/user-submissions-filter-options.png)

<span data-ttu-id="bec2c-233">Para exportar os resultados, clique **em Exportar** próximo à parte superior da página e selecione **Chart data** ou **Table**.</span><span class="sxs-lookup"><span data-stu-id="bec2c-233">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="bec2c-234">Na caixa de diálogo exibida, salve o arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="bec2c-234">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="bec2c-235">Exibir envios de usuário para a caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="bec2c-235">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="bec2c-236">**Se** você configurou [uma caixa de](user-submission.md) correio personalizada para receber mensagens relatadas pelo usuário, você pode exibir e também enviar mensagens que foram entregues à caixa de correio de relatório.</span><span class="sxs-lookup"><span data-stu-id="bec2c-236">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="bec2c-237">No Centro de Conformidade & segurança, vá para Envios **de gerenciamento** \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="bec2c-237">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="bec2c-238">Selecione a **guia Caixa de Correio** Personalizada.</span><span class="sxs-lookup"><span data-stu-id="bec2c-238">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="bec2c-239">Você pode clicar **no botão Opções de** coluna na parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="bec2c-239">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="bec2c-240">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="bec2c-240">**Submitted on**</span></span>
- <span data-ttu-id="bec2c-241">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bec2c-241">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="bec2c-242">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bec2c-242">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="bec2c-243">**Sender**</span><span class="sxs-lookup"><span data-stu-id="bec2c-243">**Sender**</span></span>
- <span data-ttu-id="bec2c-244">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="bec2c-244">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="bec2c-245">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="bec2c-245">**Submission type**</span></span>

<span data-ttu-id="bec2c-246">Na parte superior da página, você pode inserir uma data de início, uma data de término e pode filtrar por **Submitted** inserindo um valor na caixa e clicando no botão ![ ](../../media/scc-quarantine-refresh.png) Atualizar.</span><span class="sxs-lookup"><span data-stu-id="bec2c-246">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="bec2c-247">Update</span><span class="sxs-lookup"><span data-stu-id="bec2c-247">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="bec2c-248">Para exportar os resultados, clique **em Exportar** próximo à parte superior da página e selecione **Chart data** ou **Table**.</span><span class="sxs-lookup"><span data-stu-id="bec2c-248">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="bec2c-249">Na caixa de diálogo exibida, salve o arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="bec2c-249">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="bec2c-250">Desfazer envios de usuário</span><span class="sxs-lookup"><span data-stu-id="bec2c-250">Undo user submissions</span></span>

<span data-ttu-id="bec2c-251">Depois que um usuário envia um email suspeito para a caixa de correio personalizada, o usuário e o administrador não têm a opção de desfazer o envio.</span><span class="sxs-lookup"><span data-stu-id="bec2c-251">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="bec2c-252">Se o usuário quiser recuperar o email, ele estará disponível para recuperação nas pastas Itens Excluídos ou Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="bec2c-252">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="bec2c-253">Enviar mensagens para a Microsoft da caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="bec2c-253">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="bec2c-254">Se você configurou a caixa de correio personalizada para interceptar mensagens relatadas pelo usuário sem enviar as mensagens para a Microsoft, poderá encontrar e enviar mensagens específicas à Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="bec2c-254">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="bec2c-255">Isso efetivamente move um envio de usuário para um envio de administrador.</span><span class="sxs-lookup"><span data-stu-id="bec2c-255">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="bec2c-256">Na guia **Caixa de Correio** Personalizada, selecione  uma mensagem na lista, clique no botão Ação e faça uma das seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="bec2c-256">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="bec2c-257">**Relatório limpo**</span><span class="sxs-lookup"><span data-stu-id="bec2c-257">**Report clean**</span></span>
- <span data-ttu-id="bec2c-258">**Relatar phishing**</span><span class="sxs-lookup"><span data-stu-id="bec2c-258">**Report phishing**</span></span>
- <span data-ttu-id="bec2c-259">**Relatar malware**</span><span class="sxs-lookup"><span data-stu-id="bec2c-259">**Report malware**</span></span>
- <span data-ttu-id="bec2c-260">**Relatar spam**</span><span class="sxs-lookup"><span data-stu-id="bec2c-260">**Report spam**</span></span>

![Opções no botão Ação](../../media/user-submission-custom-mailbox-action-button.png)
