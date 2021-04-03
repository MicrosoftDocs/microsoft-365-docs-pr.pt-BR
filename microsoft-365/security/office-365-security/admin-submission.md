---
title: Envios de administrador
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
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o portal Envios no Centro de Conformidade de Segurança & para enviar emails suspeitos, emails suspeitos de phishing, spam e outras mensagens potencialmente prejudiciais, URLs e arquivos para a Microsoft para verificação.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 96a5469b1093c71997747b2c4c3b49bc1964f72b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581065"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="6da3c-103">Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft</span><span class="sxs-lookup"><span data-stu-id="6da3c-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6da3c-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="6da3c-104">**Applies to**</span></span>
- [<span data-ttu-id="6da3c-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6da3c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6da3c-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="6da3c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="6da3c-107">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online, os administradores podem usar o portal Envios no Centro de Conformidade & Segurança para enviar mensagens de email, URLs e anexos à Microsoft para verificação.</span><span class="sxs-lookup"><span data-stu-id="6da3c-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="6da3c-108">Ao enviar uma mensagem de email, você receberá:</span><span class="sxs-lookup"><span data-stu-id="6da3c-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="6da3c-109">**Verificação de autenticação de** email : Detalhes sobre se a autenticação de email passou ou falhou quando ela foi entregue.</span><span class="sxs-lookup"><span data-stu-id="6da3c-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="6da3c-110">**Visitas de política**: informações sobre quaisquer políticas que possam ter permitido ou bloqueado o email de entrada em seu locatário, substituindo nossos vereditos de filtro de serviço.</span><span class="sxs-lookup"><span data-stu-id="6da3c-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="6da3c-111">**Reputação/detonação** de carga : Exame de quaisquer URLs e anexos na mensagem.</span><span class="sxs-lookup"><span data-stu-id="6da3c-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="6da3c-112">**Análise de notas**: Revisão feita por alunos de nível humano para confirmar se as mensagens são mal-intencionadas ou não.</span><span class="sxs-lookup"><span data-stu-id="6da3c-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6da3c-113">A análise de reputação/detonação e classificação de carga não é feita em todos os locatários.</span><span class="sxs-lookup"><span data-stu-id="6da3c-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="6da3c-114">As informações são impedidas de sair da organização quando os dados não devem sair do limite do locatário para fins de conformidade.</span><span class="sxs-lookup"><span data-stu-id="6da3c-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="6da3c-115">Para outras maneiras de enviar mensagens de email, URLs e anexos à Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="6da3c-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6da3c-116">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="6da3c-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6da3c-117">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="6da3c-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="6da3c-118">Para ir diretamente para a página **Envio,** use <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="6da3c-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="6da3c-119">Para enviar mensagens e arquivos para a Microsoft, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="6da3c-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="6da3c-120">**Gerenciamento da** organização **ou leitor de segurança** no Centro de Conformidade & [Segurança.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="6da3c-120">**Organization Management** or **Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="6da3c-121">**Gerenciamento de organização** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="6da3c-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="6da3c-122">Observe que a associação neste grupo de funções é necessária para Exibir [envios](#view-user-submissions-to-the-custom-mailbox) de usuário para a caixa de correio personalizada conforme descrito posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="6da3c-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="6da3c-123">Para obter mais informações sobre como os usuários podem enviar mensagens e arquivos para a Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="6da3c-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="6da3c-124">Relatar conteúdo suspeito à Microsoft</span><span class="sxs-lookup"><span data-stu-id="6da3c-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="6da3c-125">Na Central de Conformidade & segurança,  vá para Envios de gerenciamento de ameaças , verifique se você está na guia \>  **Envios de** administrador e clique em **Novo envio**.</span><span class="sxs-lookup"><span data-stu-id="6da3c-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="6da3c-126">Use Novo sub-sub-sub-texto de envio que aparece para enviar a mensagem, a URL ou o anexo, conforme descrito nas seções a seguir. </span><span class="sxs-lookup"><span data-stu-id="6da3c-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="6da3c-127">Enviar um email questionável à Microsoft</span><span class="sxs-lookup"><span data-stu-id="6da3c-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="6da3c-128">Na seção **Tipo de** objeto, selecione **Email**.</span><span class="sxs-lookup"><span data-stu-id="6da3c-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="6da3c-129">Na seção **Formato de envio,** use uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="6da3c-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="6da3c-130">**ID** da mensagem de rede : este é um valor GUID que está disponível no header **X-MS-Exchange-Organization-Network-Message-Id** na mensagem ou no header **X-MS-Office365-Filtering-Correlation-Id** em mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="6da3c-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="6da3c-131">**Arquivo**: clique **em Escolher arquivo**.</span><span class="sxs-lookup"><span data-stu-id="6da3c-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="6da3c-132">Na caixa de diálogo que é aberta, encontre e selecione o arquivo .eml ou .msg e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="6da3c-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6da3c-133">Os administradores com o Defender para o Office 365 Plano 1 ou o Plano 2 podem enviar mensagens com até 30 dias.</span><span class="sxs-lookup"><span data-stu-id="6da3c-133">Admins with Defender for Office 365 Plan 1 or Plan 2 are able to submit messages as old as 30 days.</span></span> <span data-ttu-id="6da3c-134">Outros administradores só poderão voltar 7 dias.</span><span class="sxs-lookup"><span data-stu-id="6da3c-134">Other admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="6da3c-135">Na seção **Destinatários,** especifique um ou mais destinatários com os quais você gostaria de executar uma verificação de política.</span><span class="sxs-lookup"><span data-stu-id="6da3c-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="6da3c-136">A verificação de política determinará se o email foi ignorado devido a políticas de usuário ou organização.</span><span class="sxs-lookup"><span data-stu-id="6da3c-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="6da3c-137">Na seção **Motivo do envio,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="6da3c-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="6da3c-138">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="6da3c-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="6da3c-139">**Deve ter sido bloqueado**: Selecione **Spam,** **Phishing** ou **Malware**.</span><span class="sxs-lookup"><span data-stu-id="6da3c-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="6da3c-140">Se você não tiver certeza, use seu melhor julgamento.</span><span class="sxs-lookup"><span data-stu-id="6da3c-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="6da3c-141">Quando terminar, clique no **botão Enviar.**</span><span class="sxs-lookup"><span data-stu-id="6da3c-141">When you're finished, click the **Submit** button.</span></span>

   ![Exemplo de envio de URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="6da3c-143">Enviar uma URL suspeita para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="6da3c-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="6da3c-144">Na seção **Tipo de** objeto, selecione **URL**.</span><span class="sxs-lookup"><span data-stu-id="6da3c-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="6da3c-145">Na caixa exibida, insira a URL completa (por exemplo, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="6da3c-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="6da3c-146">Na seção **Motivo do envio,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="6da3c-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="6da3c-147">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="6da3c-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="6da3c-148">**Deve ter sido bloqueado**: Selecione **Phishing** ou **Malware.**</span><span class="sxs-lookup"><span data-stu-id="6da3c-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="6da3c-149">Quando terminar, clique no **botão Enviar.**</span><span class="sxs-lookup"><span data-stu-id="6da3c-149">When you're finished, click the **Submit** button.</span></span>

   ![Exemplo de envio de email](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="6da3c-151">Enviar um arquivo suspeito à Microsoft</span><span class="sxs-lookup"><span data-stu-id="6da3c-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="6da3c-152">Na seção **Tipo de** objeto, selecione **Anexo**.</span><span class="sxs-lookup"><span data-stu-id="6da3c-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="6da3c-153">Clique **em Escolher Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="6da3c-153">Click **Choose File**.</span></span> <span data-ttu-id="6da3c-154">Na caixa de diálogo que é aberta, encontre e selecione o arquivo e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="6da3c-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="6da3c-155">Na seção **Motivo do envio,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="6da3c-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="6da3c-156">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="6da3c-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="6da3c-157">**Deve ter sido bloqueado**: **Malware** é a única opção e é selecionado automaticamente..</span><span class="sxs-lookup"><span data-stu-id="6da3c-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="6da3c-158">Quando terminar, clique no **botão Enviar.**</span><span class="sxs-lookup"><span data-stu-id="6da3c-158">When you're finished, click the **Submit** button.</span></span>

   ![Exemplo de envio de anexo](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a><span data-ttu-id="6da3c-160">Exibir itens enviados para análise</span><span class="sxs-lookup"><span data-stu-id="6da3c-160">View items Submitted for analysis</span></span>

<span data-ttu-id="6da3c-161">No Centro de Conformidade & segurança,  vá para \> **Envios** de gerenciamento de ameaças , verifique se você está na guia **Enviado para** análise</span><span class="sxs-lookup"><span data-stu-id="6da3c-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Submitted for analysis** tab</span></span>

<span data-ttu-id="6da3c-162">Na parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão) você pode filtrar pela **ID** do Envio (um valor GUID atribuído a cada envio) inserindo um valor na caixa e clicando em Atualizar botão ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="6da3c-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="6da3c-163">Update</span><span class="sxs-lookup"><span data-stu-id="6da3c-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="6da3c-164">Para alterar os critérios de filtro, clique no botão **ID do** Envio e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="6da3c-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="6da3c-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="6da3c-165">**Sender**</span></span>
- <span data-ttu-id="6da3c-166">**Assunto/URL/Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="6da3c-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="6da3c-167">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="6da3c-167">**Submitted by**</span></span>
- <span data-ttu-id="6da3c-168">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="6da3c-168">**Submission type**</span></span>
- <span data-ttu-id="6da3c-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="6da3c-169">**Status**</span></span>

![Opções de filtro para envios de administrador](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="6da3c-171">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **Dados de gráfico** ou **Tabela**.</span><span class="sxs-lookup"><span data-stu-id="6da3c-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="6da3c-172">Na caixa de diálogo exibida, salve o arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="6da3c-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="6da3c-173">Abaixo do gráfico, há três guias: **Email** (padrão), **URL** e **Anexo.**</span><span class="sxs-lookup"><span data-stu-id="6da3c-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="6da3c-174">Exibir envios de email do administrador</span><span class="sxs-lookup"><span data-stu-id="6da3c-174">View admin email submissions</span></span>

<span data-ttu-id="6da3c-175">Clique na **guia Email.**</span><span class="sxs-lookup"><span data-stu-id="6da3c-175">Click the **Email** tab.</span></span>

<span data-ttu-id="6da3c-176">Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:</span><span class="sxs-lookup"><span data-stu-id="6da3c-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6da3c-177">**Date**</span><span class="sxs-lookup"><span data-stu-id="6da3c-177">**Date**</span></span>
- <span data-ttu-id="6da3c-178">**ID do envio:** um valor GUID atribuído a cada envio.</span><span class="sxs-lookup"><span data-stu-id="6da3c-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="6da3c-179">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da3c-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6da3c-180">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da3c-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="6da3c-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="6da3c-181">**Sender**</span></span>
- <span data-ttu-id="6da3c-182">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da3c-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="6da3c-183">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="6da3c-183">**Submission type**</span></span>
- <span data-ttu-id="6da3c-184">**Motivo da entrega**</span><span class="sxs-lookup"><span data-stu-id="6da3c-184">**Delivery reason**</span></span>
- <span data-ttu-id="6da3c-185">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da3c-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="6da3c-186"><sup>\*</sup> Se você clicar nesse valor, informações detalhadas serão exibidas em um sobremenu.</span><span class="sxs-lookup"><span data-stu-id="6da3c-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="6da3c-187">Detalhes da verificação de envio de administrador</span><span class="sxs-lookup"><span data-stu-id="6da3c-187">Admin submission rescan details</span></span>

<span data-ttu-id="6da3c-188">As mensagens enviadas em envios de administrador são rescanned e os resultados mostrados no submenu de detalhes:</span><span class="sxs-lookup"><span data-stu-id="6da3c-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="6da3c-189">Se houve falha na autenticação do email do remetente no momento da entrega.</span><span class="sxs-lookup"><span data-stu-id="6da3c-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="6da3c-190">Informações sobre quaisquer acessos à política que possam ter afetado ou substituído o veredicto de uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="6da3c-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="6da3c-191">Resultados de detonação atuais para ver se os URLs ou arquivos contidos na mensagem eram maliciosos ou não.</span><span class="sxs-lookup"><span data-stu-id="6da3c-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="6da3c-192">Comentários dos alunos.</span><span class="sxs-lookup"><span data-stu-id="6da3c-192">Feedback from graders.</span></span>

<span data-ttu-id="6da3c-193">Se uma substituição for encontrada, a nova varredura deve ser concluída em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="6da3c-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="6da3c-194">Se não houve um problema na autenticação ou na entrega de email não foi afetado por uma substituição, os comentários dos alunos podem levar até um dia.</span><span class="sxs-lookup"><span data-stu-id="6da3c-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="6da3c-195">Exibir envios de URL do administrador</span><span class="sxs-lookup"><span data-stu-id="6da3c-195">View admin URL submissions</span></span>

<span data-ttu-id="6da3c-196">Clique na **guia URL.**</span><span class="sxs-lookup"><span data-stu-id="6da3c-196">Click the **URL** tab.</span></span>

<span data-ttu-id="6da3c-197">Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:</span><span class="sxs-lookup"><span data-stu-id="6da3c-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6da3c-198">**Date**</span><span class="sxs-lookup"><span data-stu-id="6da3c-198">**Date**</span></span>
- <span data-ttu-id="6da3c-199">**ID do envio**</span><span class="sxs-lookup"><span data-stu-id="6da3c-199">**Submission ID**</span></span>
- <span data-ttu-id="6da3c-200">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da3c-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6da3c-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da3c-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="6da3c-202">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="6da3c-202">**Submission type**</span></span>
- <span data-ttu-id="6da3c-203">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da3c-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="6da3c-204"><sup>\*</sup> Se você clicar nesse valor, informações detalhadas serão exibidas em um sobremenu.</span><span class="sxs-lookup"><span data-stu-id="6da3c-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="6da3c-205">Exibir envios de anexos de administrador</span><span class="sxs-lookup"><span data-stu-id="6da3c-205">View admin attachment submissions</span></span>

<span data-ttu-id="6da3c-206">Clique na **guia Anexos.**</span><span class="sxs-lookup"><span data-stu-id="6da3c-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="6da3c-207">Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:</span><span class="sxs-lookup"><span data-stu-id="6da3c-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6da3c-208">**Date**</span><span class="sxs-lookup"><span data-stu-id="6da3c-208">**Date**</span></span>
- <span data-ttu-id="6da3c-209">**ID do envio**</span><span class="sxs-lookup"><span data-stu-id="6da3c-209">**Submission ID**</span></span>
- <span data-ttu-id="6da3c-210">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da3c-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6da3c-211">**Nome do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da3c-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="6da3c-212">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="6da3c-212">**Submission type**</span></span>
- <span data-ttu-id="6da3c-213">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da3c-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="6da3c-214"><sup>\*</sup> Se você clicar nesse valor, informações detalhadas serão exibidas em um sobremenu.</span><span class="sxs-lookup"><span data-stu-id="6da3c-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="6da3c-215">Exibir envios de usuários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="6da3c-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="6da3c-216">Se você tiver implantado o [add-in](enable-the-report-message-add-in.md)Mensagem de Relatório, o complemento Relatar [Phishing](enable-the-report-phish-add-in.md)ou as pessoas usarem os relatórios **integrados** no Outlook na [Web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)você poderá ver o que os usuários estão relatando na guia Envios do usuário.</span><span class="sxs-lookup"><span data-stu-id="6da3c-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="6da3c-217">No Centro de Conformidade & segurança, vá para **Envios de gerenciamento** \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="6da3c-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="6da3c-218">Selecione a **guia Envios de usuário** e clique em Novo **envio**.</span><span class="sxs-lookup"><span data-stu-id="6da3c-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="6da3c-219">Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:</span><span class="sxs-lookup"><span data-stu-id="6da3c-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6da3c-220">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="6da3c-220">**Submitted on**</span></span>
- <span data-ttu-id="6da3c-221">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da3c-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6da3c-222">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da3c-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="6da3c-223">**Sender**</span><span class="sxs-lookup"><span data-stu-id="6da3c-223">**Sender**</span></span>
- <span data-ttu-id="6da3c-224">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da3c-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="6da3c-225">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="6da3c-225">**Submission type**</span></span>

<span data-ttu-id="6da3c-226"><sup>\*</sup> Se você clicar nesse valor, informações detalhadas serão exibidas em um sobremenu.</span><span class="sxs-lookup"><span data-stu-id="6da3c-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="6da3c-227">Na parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão) você pode filtrar por **Remetente** inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="6da3c-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="6da3c-228">Update</span><span class="sxs-lookup"><span data-stu-id="6da3c-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="6da3c-229">Para alterar os critérios de filtro, clique no botão **Remetente** e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="6da3c-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="6da3c-230">**Domínio do remetente**</span><span class="sxs-lookup"><span data-stu-id="6da3c-230">**Sender domain**</span></span>
- <span data-ttu-id="6da3c-231">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="6da3c-231">**Subject**</span></span>
- <span data-ttu-id="6da3c-232">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="6da3c-232">**Submitted by**</span></span>
- <span data-ttu-id="6da3c-233">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="6da3c-233">**Submission type**</span></span>
- <span data-ttu-id="6da3c-234">**IP do remetente**</span><span class="sxs-lookup"><span data-stu-id="6da3c-234">**Sender IP**</span></span>

![Opções de filtro para envios de usuários](../../media/user-submissions-filter-options.png)

<span data-ttu-id="6da3c-236">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **Dados de gráfico** ou **Tabela**.</span><span class="sxs-lookup"><span data-stu-id="6da3c-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="6da3c-237">Na caixa de diálogo exibida, salve o arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="6da3c-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="6da3c-238">Exibir envios de usuário para a caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="6da3c-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="6da3c-239">**Se** você configurou [uma caixa](user-submission.md) de correio personalizada para receber mensagens relatadas pelo usuário, você pode exibir e também enviar mensagens que foram entregues à caixa de correio de relatório.</span><span class="sxs-lookup"><span data-stu-id="6da3c-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="6da3c-240">No Centro de Conformidade & segurança, vá para **Envios de gerenciamento** \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="6da3c-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="6da3c-241">Selecione a **guia Caixa de correio** Personalizada.</span><span class="sxs-lookup"><span data-stu-id="6da3c-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="6da3c-242">Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:</span><span class="sxs-lookup"><span data-stu-id="6da3c-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="6da3c-243">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="6da3c-243">**Submitted on**</span></span>
- <span data-ttu-id="6da3c-244">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da3c-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="6da3c-245">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da3c-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="6da3c-246">**Sender**</span><span class="sxs-lookup"><span data-stu-id="6da3c-246">**Sender**</span></span>
- <span data-ttu-id="6da3c-247">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6da3c-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="6da3c-248">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="6da3c-248">**Submission type**</span></span>

<span data-ttu-id="6da3c-249">Na parte superior da página, você pode inserir uma data de  início, uma data de término e filtrar enviando inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="6da3c-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="6da3c-250">Update</span><span class="sxs-lookup"><span data-stu-id="6da3c-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="6da3c-251">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **Dados de gráfico** ou **Tabela**.</span><span class="sxs-lookup"><span data-stu-id="6da3c-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="6da3c-252">Na caixa de diálogo exibida, salve o arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="6da3c-252">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="6da3c-253">Se as organizações estão configuradas para enviar somente para a caixa de correio personalizada, as mensagens relatadas não serão enviadas para análise novamente e os resultados no portal de mensagens relatadas pelo usuário sempre estarão vazios.</span><span class="sxs-lookup"><span data-stu-id="6da3c-253">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="6da3c-254">Desfazer envios de usuário</span><span class="sxs-lookup"><span data-stu-id="6da3c-254">Undo user submissions</span></span>

<span data-ttu-id="6da3c-255">Depois que um usuário envia um email suspeito para a caixa de correio personalizada, o usuário e o administrador não têm uma opção para desfazer o envio.</span><span class="sxs-lookup"><span data-stu-id="6da3c-255">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="6da3c-256">Se o usuário quiser recuperar o email, ele estará disponível para recuperação nas pastas Itens Excluídos ou Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="6da3c-256">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="6da3c-257">Enviar mensagens para a Microsoft da caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="6da3c-257">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="6da3c-258">Se você configurou a caixa de correio personalizada para interceptar mensagens relatadas pelo usuário sem enviar as mensagens para a Microsoft, você poderá encontrar e enviar mensagens específicas para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="6da3c-258">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="6da3c-259">Isso move efetivamente um envio de usuário para um envio de administrador.</span><span class="sxs-lookup"><span data-stu-id="6da3c-259">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="6da3c-260">Na guia **Caixa de Correio** Personalizada, selecione uma mensagem na lista, clique no botão **Ação** e faça uma das seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="6da3c-260">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="6da3c-261">**Relatório limpo**</span><span class="sxs-lookup"><span data-stu-id="6da3c-261">**Report clean**</span></span>
- <span data-ttu-id="6da3c-262">**Relatar phishing**</span><span class="sxs-lookup"><span data-stu-id="6da3c-262">**Report phishing**</span></span>
- <span data-ttu-id="6da3c-263">**Relatar malware**</span><span class="sxs-lookup"><span data-stu-id="6da3c-263">**Report malware**</span></span>
- <span data-ttu-id="6da3c-264">**Relatar spam**</span><span class="sxs-lookup"><span data-stu-id="6da3c-264">**Report spam**</span></span>

![Opções no botão Ação](../../media/user-submission-custom-mailbox-action-button.png)
