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
description: Os administradores podem aprender a usar o portal de envios no centro de conformidade de & de segurança para enviar emails suspeitos, emails de phishing, spam e outras mensagens, URLs e arquivos potencialmente nocivos para a Microsoft para verificação.
ms.openlocfilehash: 0c01afff2e9e5a656099192f3867bb3a6f1cee23
ms.sourcegitcommit: 7e003ee0a06f61bfb9f80441c3479fa3148afafe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "49568585"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="7471d-103">Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft</span><span class="sxs-lookup"><span data-stu-id="7471d-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7471d-104">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online, os administradores podem usar o portal de envios no centro de conformidade de & de segurança para enviar mensagens de email, URLs e anexos para a Microsoft para verificação.</span><span class="sxs-lookup"><span data-stu-id="7471d-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="7471d-105">Ao enviar um email, você receberá informações sobre qualquer política que possa ter permitido o email de entrada em seu locatário, bem como o exame de qualquer URL e anexo no email.</span><span class="sxs-lookup"><span data-stu-id="7471d-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="7471d-106">As políticas que podem ter permitido um email incluem a lista de remetentes confiáveis de um usuário individual, bem como políticas de nível de locatário, como regras de fluxo de emails do Exchange (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="7471d-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="7471d-107">Para obter outras maneiras de enviar mensagens de email, URLs e anexos para a Microsoft, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="7471d-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7471d-108">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="7471d-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7471d-109">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="7471d-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7471d-110">Para ir diretamente para a página de **envio** , use <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="7471d-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="7471d-111">Para enviar mensagens e arquivos para a Microsoft, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="7471d-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="7471d-112">**Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7471d-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="7471d-113">**Gerenciamento de organização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="7471d-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="7471d-114">Observe que a associação ao grupo de funções é necessária para [Exibir envios de usuários para a caixa de correio personalizada](#view-user-submissions-to-the-custom-mailbox) , conforme descrito mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="7471d-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="7471d-115">Para obter mais informações sobre como os usuários podem enviar mensagens e arquivos para a Microsoft, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="7471d-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="7471d-116">Relatar conteúdo suspeito para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="7471d-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="7471d-117">No centro de conformidade & segurança, vá para **Threat management** \> **envios** de gerenciamento de ameaças, verifique se você está na guia **envios de administrador** e clique em **novo envio**.</span><span class="sxs-lookup"><span data-stu-id="7471d-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="7471d-118">Use um novo submenu de **envio** que parece enviar a mensagem, a URL ou o anexo, conforme descrito nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="7471d-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="7471d-119">Enviar um email questionável à Microsoft</span><span class="sxs-lookup"><span data-stu-id="7471d-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="7471d-120">Na seção **tipo de objeto** , selecione **email**.</span><span class="sxs-lookup"><span data-stu-id="7471d-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="7471d-121">Na seção **formato de envio** , use uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="7471d-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="7471d-122">**ID de mensagem de rede**: Este é um valor de GUID que está disponível no cabeçalho **x-MS-Exchange-Organization-Network-Message-ID** na mensagem ou no cabeçalho **x-MS-Office365-Filtering-ID** em mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="7471d-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="7471d-123">**Arquivo**: clique em **escolher arquivo**.</span><span class="sxs-lookup"><span data-stu-id="7471d-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="7471d-124">Na caixa de diálogo que é aberta, localize e selecione o arquivo. eml ou. msg e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="7471d-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7471d-125">Os administradores com o defender para Office 365 plano 1 ou o plano 2 podem enviar mensagens com o antigo a 30 dias.</span><span class="sxs-lookup"><span data-stu-id="7471d-125">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="7471d-126">Outros administradores poderão voltar 7 dias.</span><span class="sxs-lookup"><span data-stu-id="7471d-126">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="7471d-127">Na seção **destinatários** , especifique um ou mais destinatários em relação à qual você gostaria de executar uma verificação de política.</span><span class="sxs-lookup"><span data-stu-id="7471d-127">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="7471d-128">A verificação de política determinará se o email ignorará a verificação por causa de políticas de usuário ou organização.</span><span class="sxs-lookup"><span data-stu-id="7471d-128">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="7471d-129">Na seção **motivo da envio** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="7471d-129">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="7471d-130">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="7471d-130">**Should not have been blocked**</span></span>

   - <span data-ttu-id="7471d-131">**Deveriam ter sido bloqueados**: selecione **spam**, **phishing** ou **malware**.</span><span class="sxs-lookup"><span data-stu-id="7471d-131">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="7471d-132">Se você não tiver certeza, use a melhor avaliação.</span><span class="sxs-lookup"><span data-stu-id="7471d-132">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="7471d-133">Quando tiver concluído, clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="7471d-133">When you're finished, click the **Submit** button.</span></span>

![Exemplo de envio de URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="7471d-135">Enviar uma URL suspeita para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="7471d-135">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="7471d-136">Na seção **tipo de objeto** , selecione **URL**.</span><span class="sxs-lookup"><span data-stu-id="7471d-136">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="7471d-137">Na caixa exibida, digite a URL completa (por exemplo, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="7471d-137">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="7471d-138">Na seção **motivo da envio** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="7471d-138">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="7471d-139">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="7471d-139">**Should not have been blocked**</span></span>

   - <span data-ttu-id="7471d-140">**Deveria ter sido bloqueado**: selecione **phishing** ou **malware**.</span><span class="sxs-lookup"><span data-stu-id="7471d-140">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="7471d-141">Quando tiver concluído, clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="7471d-141">When you're finished, click the **Submit** button.</span></span>

![Exemplo de envio de email](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="7471d-143">Enviar um arquivo suspeito para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="7471d-143">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="7471d-144">Na seção **tipo de objeto** , selecione **anexo**.</span><span class="sxs-lookup"><span data-stu-id="7471d-144">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="7471d-145">Clique em **escolher arquivo**.</span><span class="sxs-lookup"><span data-stu-id="7471d-145">Click **Choose File**.</span></span> <span data-ttu-id="7471d-146">Na caixa de diálogo que é aberta, localize e selecione o arquivo e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="7471d-146">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="7471d-147">Na seção **motivo da envio** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="7471d-147">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="7471d-148">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="7471d-148">**Should not have been blocked**</span></span>

   - <span data-ttu-id="7471d-149">**Deveria ter sido bloqueado**: o **malware** é a única opção e é selecionado automaticamente..</span><span class="sxs-lookup"><span data-stu-id="7471d-149">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="7471d-150">Quando tiver concluído, clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="7471d-150">When you're finished, click the **Submit** button.</span></span>

![Exemplo de envio de anexos](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="7471d-152">Exibir envios de administradores</span><span class="sxs-lookup"><span data-stu-id="7471d-152">View admin submissions</span></span>

<span data-ttu-id="7471d-153">No centro de conformidade & segurança, vá para **Threat management** \> **envios** de gerenciamento de ameaças, verifique se você está na guia **envios de administrador** e clique em **novo envio**.</span><span class="sxs-lookup"><span data-stu-id="7471d-153">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="7471d-154">Próximo à parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão), você pode filtrar por **ID de envio** (um valor de GUID que é atribuído a cada envio) inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="7471d-154">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="7471d-155">Update</span><span class="sxs-lookup"><span data-stu-id="7471d-155">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="7471d-156">Para alterar os critérios de filtro, clique no botão **ID de envio** e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="7471d-156">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="7471d-157">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7471d-157">**Sender**</span></span>
- <span data-ttu-id="7471d-158">**Assunto/URL/nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="7471d-158">**Subject/URL/File name**</span></span>
- <span data-ttu-id="7471d-159">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="7471d-159">**Submitted by**</span></span>
- <span data-ttu-id="7471d-160">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="7471d-160">**Submission type**</span></span>
- <span data-ttu-id="7471d-161">**Status**</span><span class="sxs-lookup"><span data-stu-id="7471d-161">**Status**</span></span>

![Opções de filtro para envios de administradores](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="7471d-163">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **dados do gráfico** ou **tabela**.</span><span class="sxs-lookup"><span data-stu-id="7471d-163">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="7471d-164">Na caixa de diálogo exibida, salve o arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="7471d-164">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="7471d-165">Abaixo do gráfico, há três guias: **email** (padrão), **URL** e **anexo**.</span><span class="sxs-lookup"><span data-stu-id="7471d-165">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="7471d-166">Exibir envios de email de administração</span><span class="sxs-lookup"><span data-stu-id="7471d-166">View admin email submissions</span></span>

<span data-ttu-id="7471d-167">Clique na guia **email** .</span><span class="sxs-lookup"><span data-stu-id="7471d-167">Click the **Email** tab.</span></span>

<span data-ttu-id="7471d-168">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="7471d-168">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7471d-169">**Date**</span><span class="sxs-lookup"><span data-stu-id="7471d-169">**Date**</span></span>
- <span data-ttu-id="7471d-170">**ID de envio**: um valor de GUID que é atribuído a cada envio.</span><span class="sxs-lookup"><span data-stu-id="7471d-170">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="7471d-171">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7471d-171">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7471d-172">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7471d-172">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="7471d-173">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7471d-173">**Sender**</span></span>
- <span data-ttu-id="7471d-174">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7471d-174">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="7471d-175">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="7471d-175">**Submission type**</span></span>
- <span data-ttu-id="7471d-176">**Motivo da entrega**</span><span class="sxs-lookup"><span data-stu-id="7471d-176">**Delivery reason**</span></span>
- <span data-ttu-id="7471d-177">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7471d-177">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="7471d-178"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="7471d-178"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="7471d-179">Detalhes do novo envio de administrador</span><span class="sxs-lookup"><span data-stu-id="7471d-179">Admin submission rescan details</span></span>

<span data-ttu-id="7471d-180">As mensagens enviadas nos envios de administradores são verificadas novamente e os resultados são exibidos no submenu detalhes:</span><span class="sxs-lookup"><span data-stu-id="7471d-180">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="7471d-181">Se houve uma falha na autenticação de email do remetente no momento da entrega.</span><span class="sxs-lookup"><span data-stu-id="7471d-181">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="7471d-182">Informações sobre qualquer ocorrência de política que possa ter afetado ou substituído o veredicto de uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="7471d-182">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="7471d-183">Resultados atuais do acionamento para ver se as URLs ou os arquivos contidos na mensagem foram mal-intencionados ou não.</span><span class="sxs-lookup"><span data-stu-id="7471d-183">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="7471d-184">Comentários de conséries.</span><span class="sxs-lookup"><span data-stu-id="7471d-184">Feedback from graders.</span></span>

<span data-ttu-id="7471d-185">Se uma substituição foi encontrada, a verificação deve ser concluída em vários minutos.</span><span class="sxs-lookup"><span data-stu-id="7471d-185">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="7471d-186">Se não houvesse um problema na entrega ou na autenticação de emails não ter sido afetada por uma substituição, os comentários dos comquemres podem levar até um dia.</span><span class="sxs-lookup"><span data-stu-id="7471d-186">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="7471d-187">Exibir envios de URL de administração</span><span class="sxs-lookup"><span data-stu-id="7471d-187">View admin URL submissions</span></span>

<span data-ttu-id="7471d-188">Clique na guia **URL** .</span><span class="sxs-lookup"><span data-stu-id="7471d-188">Click the **URL** tab.</span></span>

<span data-ttu-id="7471d-189">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="7471d-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7471d-190">**Date**</span><span class="sxs-lookup"><span data-stu-id="7471d-190">**Date**</span></span>
- <span data-ttu-id="7471d-191">**ID de envio**</span><span class="sxs-lookup"><span data-stu-id="7471d-191">**Submission ID**</span></span>
- <span data-ttu-id="7471d-192">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7471d-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7471d-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7471d-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="7471d-194">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="7471d-194">**Submission type**</span></span>
- <span data-ttu-id="7471d-195">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7471d-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="7471d-196"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="7471d-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="7471d-197">Exibir envios de anexo de administrador</span><span class="sxs-lookup"><span data-stu-id="7471d-197">View admin attachment submissions</span></span>

<span data-ttu-id="7471d-198">Clique na guia **anexos** .</span><span class="sxs-lookup"><span data-stu-id="7471d-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="7471d-199">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="7471d-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7471d-200">**Date**</span><span class="sxs-lookup"><span data-stu-id="7471d-200">**Date**</span></span>
- <span data-ttu-id="7471d-201">**ID de envio**</span><span class="sxs-lookup"><span data-stu-id="7471d-201">**Submission ID**</span></span>
- <span data-ttu-id="7471d-202">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7471d-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7471d-203">**Nome do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7471d-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="7471d-204">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="7471d-204">**Submission type**</span></span>
- <span data-ttu-id="7471d-205">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7471d-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="7471d-206"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="7471d-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="7471d-207">Exibir envios de usuários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="7471d-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="7471d-208">Se você tiver implantado o [suplemento de mensagem de relatório](enable-the-report-message-add-in.md)ou se as pessoas usarem [relatórios internos no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), você poderá ver quais usuários estão relatando na guia **envios** de usuários.</span><span class="sxs-lookup"><span data-stu-id="7471d-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="7471d-209">No centro de conformidade & segurança, vá para **Threat management** \> **envios** de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="7471d-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="7471d-210">Selecione a guia envios de **usuário** e clique em **novo envio**.</span><span class="sxs-lookup"><span data-stu-id="7471d-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="7471d-211">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="7471d-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7471d-212">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="7471d-212">**Submitted on**</span></span>
- <span data-ttu-id="7471d-213">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7471d-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7471d-214">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7471d-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="7471d-215">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7471d-215">**Sender**</span></span>
- <span data-ttu-id="7471d-216">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7471d-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="7471d-217">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="7471d-217">**Submission type**</span></span>

<span data-ttu-id="7471d-218"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="7471d-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="7471d-219">Próximo à parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão), você pode filtrar por **remetente** inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="7471d-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="7471d-220">Update</span><span class="sxs-lookup"><span data-stu-id="7471d-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="7471d-221">Para alterar os critérios de filtro, clique no botão **remetente** e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="7471d-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="7471d-222">**Domínio do remetente**</span><span class="sxs-lookup"><span data-stu-id="7471d-222">**Sender domain**</span></span>
- <span data-ttu-id="7471d-223">**Subject**</span><span class="sxs-lookup"><span data-stu-id="7471d-223">**Subject**</span></span>
- <span data-ttu-id="7471d-224">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="7471d-224">**Submitted by**</span></span>
- <span data-ttu-id="7471d-225">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="7471d-225">**Submission type**</span></span>
- <span data-ttu-id="7471d-226">**IP do remetente**</span><span class="sxs-lookup"><span data-stu-id="7471d-226">**Sender IP**</span></span>

![Opções de filtro para envios de usuários](../../media/user-submissions-filter-options.png)

<span data-ttu-id="7471d-228">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **dados do gráfico** ou **tabela**.</span><span class="sxs-lookup"><span data-stu-id="7471d-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="7471d-229">Na caixa de diálogo exibida, salve o arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="7471d-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="7471d-230">Exibir envios de usuários para a caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="7471d-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="7471d-231">**Se** você [configurou uma caixa de correio personalizada](user-submission.md) para receber mensagens relatadas pelo usuário, você pode exibir e também enviar mensagens que foram entregues à caixa de correio de relatório.</span><span class="sxs-lookup"><span data-stu-id="7471d-231">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="7471d-232">No centro de conformidade & segurança, vá para **Threat management** \> **envios** de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="7471d-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="7471d-233">Selecione a guia **caixa de correio personalizada** .</span><span class="sxs-lookup"><span data-stu-id="7471d-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="7471d-234">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="7471d-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="7471d-235">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="7471d-235">**Submitted on**</span></span>
- <span data-ttu-id="7471d-236">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7471d-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="7471d-237">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7471d-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="7471d-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="7471d-238">**Sender**</span></span>
- <span data-ttu-id="7471d-239">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="7471d-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="7471d-240">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="7471d-240">**Submission type**</span></span>

<span data-ttu-id="7471d-241">Próximo à parte superior da página, você pode inserir uma data de início, uma data de término e filtrar por **enviado** , inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="7471d-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="7471d-242">Update</span><span class="sxs-lookup"><span data-stu-id="7471d-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="7471d-243">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **dados do gráfico** ou **tabela**.</span><span class="sxs-lookup"><span data-stu-id="7471d-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="7471d-244">Na caixa de diálogo exibida, salve o arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="7471d-244">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="7471d-245">Desfazer envios de usuários</span><span class="sxs-lookup"><span data-stu-id="7471d-245">Undo user submissions</span></span>

<span data-ttu-id="7471d-246">Quando um usuário envia um email suspeito para a caixa de correio personalizada, o usuário e o administrador não têm uma opção para desfazer o envio.</span><span class="sxs-lookup"><span data-stu-id="7471d-246">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="7471d-247">Se o usuário quiser recuperar o email, ele estará disponível para recuperação nas pastas itens excluídos ou lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7471d-247">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="7471d-248">Enviar mensagens para a Microsoft a partir da caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="7471d-248">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="7471d-249">Se você tiver configurado a caixa de correio personalizada para interceptar mensagens relatadas pelo usuário sem enviar as mensagens à Microsoft, poderá encontrar e enviar mensagens específicas para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="7471d-249">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="7471d-250">Isso move efetivamente um envio de usuário para um envio de administrador.</span><span class="sxs-lookup"><span data-stu-id="7471d-250">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="7471d-251">Na guia **caixa de correio personalizada** , selecione uma mensagem na lista, clique no botão de **ação** e faça uma das seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="7471d-251">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="7471d-252">**Limpeza de relatório**</span><span class="sxs-lookup"><span data-stu-id="7471d-252">**Report clean**</span></span>
- <span data-ttu-id="7471d-253">**Relatar phishing**</span><span class="sxs-lookup"><span data-stu-id="7471d-253">**Report phishing**</span></span>
- <span data-ttu-id="7471d-254">**Relatar malware**</span><span class="sxs-lookup"><span data-stu-id="7471d-254">**Report malware**</span></span>
- <span data-ttu-id="7471d-255">**Relatar spam**</span><span class="sxs-lookup"><span data-stu-id="7471d-255">**Report spam**</span></span>

![Opções no botão de ação](../../media/user-submission-custom-mailbox-action-button.png)
