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
ms.openlocfilehash: d0b91808aa9008f467f66b8200f2c05a120fbcd9
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107225"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="5f1b3-103">Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft</span><span class="sxs-lookup"><span data-stu-id="5f1b3-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5f1b3-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-104">**Applies to**</span></span>
- [<span data-ttu-id="5f1b3-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5f1b3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5f1b3-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="5f1b3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="5f1b3-107">Em Microsoft 365 organizações com caixas de correio no Exchange Online, os administradores podem usar o portal Envios no Centro de Conformidade & Segurança para enviar mensagens de email, URLs e anexos à Microsoft para verificação.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="5f1b3-108">Ao enviar uma mensagem de email, você receberá:</span><span class="sxs-lookup"><span data-stu-id="5f1b3-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="5f1b3-109">**Verificação de autenticação de** email : Detalhes sobre se a autenticação de email passou ou falhou quando ela foi entregue.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="5f1b3-110">**Visitas de política**: informações sobre quaisquer políticas que possam ter permitido ou bloqueado o email de entrada em seu locatário, substituindo nossos vereditos de filtro de serviço.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="5f1b3-111">**Reputação/detonação** de carga : Exame de quaisquer URLs e anexos na mensagem.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="5f1b3-112">**Análise de notas**: Revisão feita por alunos de nível humano para confirmar se as mensagens são mal-intencionadas ou não.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f1b3-113">A análise de reputação/detonação e classificação de carga não é feita em todos os locatários.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="5f1b3-114">As informações são impedidas de sair da organização quando os dados não devem sair do limite do locatário para fins de conformidade.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="5f1b3-115">Para outras maneiras de enviar mensagens de email, URLs e anexos à Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="5f1b3-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5f1b3-116">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="5f1b3-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5f1b3-117">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-117">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="5f1b3-118">Para ir diretamente para a página **Envio,** use <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="5f1b3-118">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="5f1b3-119">Para enviar mensagens e arquivos para a Microsoft, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="5f1b3-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="5f1b3-120">**Gerenciamento da** organização **ou leitor de segurança** no Centro de Conformidade & [Segurança.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="5f1b3-120">**Organization Management** or **Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="5f1b3-121">**Gerenciamento de organização** em [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="5f1b3-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="5f1b3-122">Observe que a associação neste grupo de funções é necessária para Exibir [envios](#view-user-submissions-to-the-custom-mailbox) de usuário para a caixa de correio personalizada conforme descrito posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="5f1b3-123">Para obter mais informações sobre como os usuários podem enviar mensagens e arquivos para a Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="5f1b3-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="5f1b3-124">Relatar conteúdo suspeito à Microsoft</span><span class="sxs-lookup"><span data-stu-id="5f1b3-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="5f1b3-125">Na Central de Conformidade & segurança,  vá para Envios de gerenciamento de ameaças , verifique se você está na guia \>  **Envios de** administrador e clique em **Novo envio**.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-125">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="5f1b3-126">Use Novo sub-sub-sub-texto de envio que aparece para enviar a mensagem, a URL ou o anexo, conforme descrito nas seções a seguir. </span><span class="sxs-lookup"><span data-stu-id="5f1b3-126">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="5f1b3-127">Enviar um email questionável à Microsoft</span><span class="sxs-lookup"><span data-stu-id="5f1b3-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="5f1b3-128">Na seção **Tipo de** objeto, selecione **Email**.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-128">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="5f1b3-129">Na seção **Formato de envio,** use uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="5f1b3-129">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="5f1b3-130">**ID** da mensagem de rede : este é um valor GUID que está disponível no header **X-MS-Exchange-Organization-Network-Message-Id** na mensagem ou no header **X-MS-Office365-Filtering-Correlation-Id** em mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-130">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message, or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="5f1b3-131">**Arquivo**: clique **em Escolher arquivo**.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-131">**File**: Click **Choose file**.</span></span> <span data-ttu-id="5f1b3-132">Na caixa de diálogo que é aberta, encontre e selecione o arquivo .eml ou .msg e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5f1b3-133">A capacidade de enviar mensagens com até 30 dias foi temporariamente suspensa para o Defender Office 365 clientes.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="5f1b3-134">Os administradores só poderão voltar 7 dias.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-134">Admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="5f1b3-135">Na seção **Destinatários,** especifique um ou mais destinatários com os quais você gostaria de executar uma verificação de política.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-135">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="5f1b3-136">A verificação de política determinará se o email foi ignorado devido a políticas de usuário ou organização.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="5f1b3-137">Na seção **Motivo do envio,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="5f1b3-137">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="5f1b3-138">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="5f1b3-139">**Deve ter sido bloqueado**: Selecione **Spam,** **Phishing** ou **Malware**.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="5f1b3-140">Se você não tiver certeza, use seu melhor julgamento.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="5f1b3-141">Quando terminar, clique no **botão Enviar.**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-141">When you're finished, click the **Submit** button.</span></span>

   ![Novo exemplo de envio de URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="5f1b3-143">Enviar uma URL suspeita para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="5f1b3-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="5f1b3-144">Na seção **Tipo de** objeto, selecione **URL**.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-144">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="5f1b3-145">Na caixa exibida, insira a URL completa (por exemplo, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="5f1b3-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="5f1b3-146">Na seção **Motivo do envio,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="5f1b3-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="5f1b3-147">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="5f1b3-148">**Deve ter sido bloqueado**: Selecione **Phishing** ou **Malware.**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="5f1b3-149">Quando terminar, clique no **botão Enviar.**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-149">When you're finished, click the **Submit** button.</span></span>

   ![Novo exemplo de envio de email](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="5f1b3-151">Enviar um arquivo suspeito à Microsoft</span><span class="sxs-lookup"><span data-stu-id="5f1b3-151">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="5f1b3-152">Na seção **Tipo de** objeto, selecione **Anexo**.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-152">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="5f1b3-153">Clique **em Escolher Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-153">Click **Choose File**.</span></span> <span data-ttu-id="5f1b3-154">Na caixa de diálogo que é aberta, encontre e selecione o arquivo e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="5f1b3-155">Na seção **Motivo do envio,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="5f1b3-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="5f1b3-156">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="5f1b3-157">**Deve ter sido bloqueado**: **Malware** é a única opção e é selecionado automaticamente..</span><span class="sxs-lookup"><span data-stu-id="5f1b3-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="5f1b3-158">Quando terminar, clique no **botão Enviar.**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-158">When you're finished, click the **Submit** button.</span></span>

   ![Novo exemplo de envio de anexo](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a><span data-ttu-id="5f1b3-160">Exibir itens enviados para análise</span><span class="sxs-lookup"><span data-stu-id="5f1b3-160">View items Submitted for analysis</span></span>

<span data-ttu-id="5f1b3-161">No Centro de Conformidade & segurança,  vá para \> **Envios** de gerenciamento de ameaças , verifique se você está na guia **Enviado para** análise</span><span class="sxs-lookup"><span data-stu-id="5f1b3-161">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Submitted for analysis** tab</span></span>

<span data-ttu-id="5f1b3-162">Na parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão) você pode filtrar pela **ID** do Envio (um valor GUID atribuído a cada envio) inserindo um valor na caixa e clicando em Atualizar botão ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="5f1b3-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="5f1b3-163">Update</span><span class="sxs-lookup"><span data-stu-id="5f1b3-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="5f1b3-164">Para alterar os critérios de filtro, clique no botão **ID do** Envio e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5f1b3-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="5f1b3-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-165">**Sender**</span></span>
- <span data-ttu-id="5f1b3-166">**Assunto/URL/Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="5f1b3-167">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-167">**Submitted by**</span></span>
- <span data-ttu-id="5f1b3-168">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-168">**Submission type**</span></span>
- <span data-ttu-id="5f1b3-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-169">**Status**</span></span>

![Novas opções de Filtro para envios de administrador](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="5f1b3-171">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **Dados de gráfico** ou **Tabela**.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="5f1b3-172">Na caixa de diálogo exibida, salve o arquivo .csv arquivo.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="5f1b3-173">Abaixo do gráfico, há três guias: **Email** (padrão), **URL** e **Anexo.**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="5f1b3-174">Exibir envios de email do administrador</span><span class="sxs-lookup"><span data-stu-id="5f1b3-174">View admin email submissions</span></span>

<span data-ttu-id="5f1b3-175">Clique na **guia Email.**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-175">Click the **Email** tab.</span></span>

<span data-ttu-id="5f1b3-176">Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:</span><span class="sxs-lookup"><span data-stu-id="5f1b3-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5f1b3-177">**Date**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-177">**Date**</span></span>
- <span data-ttu-id="5f1b3-178">**ID do envio:** um valor GUID atribuído a cada envio.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="5f1b3-179">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f1b3-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5f1b3-180">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f1b3-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="5f1b3-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-181">**Sender**</span></span>
- <span data-ttu-id="5f1b3-182">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f1b3-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="5f1b3-183">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-183">**Submission type**</span></span>
- <span data-ttu-id="5f1b3-184">**Motivo da entrega**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-184">**Delivery reason**</span></span>
- <span data-ttu-id="5f1b3-185">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f1b3-185">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="5f1b3-186"><sup>\*</sup> Se você clicar nesse valor, informações detalhadas serão exibidas em um sobremenu.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="5f1b3-187">Detalhes da verificação de envio de administrador</span><span class="sxs-lookup"><span data-stu-id="5f1b3-187">Admin submission rescan details</span></span>

<span data-ttu-id="5f1b3-188">As mensagens enviadas em envios de administrador são rescanned e os resultados mostrados no submenu de detalhes:</span><span class="sxs-lookup"><span data-stu-id="5f1b3-188">Messages that are submitted in admin submissions are rescanned and results shown in the details flyout:</span></span>

- <span data-ttu-id="5f1b3-189">Se houve falha na autenticação do email do remetente no momento da entrega.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-189">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="5f1b3-190">Informações sobre quaisquer acessos à política que possam ter afetado ou substituído o veredicto de uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-190">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="5f1b3-191">Resultados de detonação atuais para ver se os URLs ou arquivos contidos na mensagem eram maliciosos ou não.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-191">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="5f1b3-192">Comentários dos alunos.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-192">Feedback from graders.</span></span>

<span data-ttu-id="5f1b3-193">Se uma substituição for encontrada, a nova varredura deve ser concluída em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-193">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="5f1b3-194">Se não houve um problema na autenticação ou na entrega de email não foi afetado por uma substituição, os comentários dos alunos podem levar até um dia.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-194">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="5f1b3-195">Exibir envios de URL do administrador</span><span class="sxs-lookup"><span data-stu-id="5f1b3-195">View admin URL submissions</span></span>

<span data-ttu-id="5f1b3-196">Clique na **guia URL.**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-196">Click the **URL** tab.</span></span>

<span data-ttu-id="5f1b3-197">Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:</span><span class="sxs-lookup"><span data-stu-id="5f1b3-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5f1b3-198">**Date**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-198">**Date**</span></span>
- <span data-ttu-id="5f1b3-199">**ID do envio**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-199">**Submission ID**</span></span>
- <span data-ttu-id="5f1b3-200">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f1b3-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5f1b3-201">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f1b3-201">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="5f1b3-202">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-202">**Submission type**</span></span>
- <span data-ttu-id="5f1b3-203">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f1b3-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="5f1b3-204"><sup>\*</sup> Se você clicar nesse valor, informações detalhadas serão exibidas em um sobremenu.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="5f1b3-205">Exibir envios de anexos de administrador</span><span class="sxs-lookup"><span data-stu-id="5f1b3-205">View admin attachment submissions</span></span>

<span data-ttu-id="5f1b3-206">Clique na **guia Anexos.**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-206">Click the **Attachments** tab.</span></span>

<span data-ttu-id="5f1b3-207">Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:</span><span class="sxs-lookup"><span data-stu-id="5f1b3-207">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5f1b3-208">**Date**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-208">**Date**</span></span>
- <span data-ttu-id="5f1b3-209">**ID do envio**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-209">**Submission ID**</span></span>
- <span data-ttu-id="5f1b3-210">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f1b3-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5f1b3-211">**Nome do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f1b3-211">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="5f1b3-212">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-212">**Submission type**</span></span>
- <span data-ttu-id="5f1b3-213">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f1b3-213">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="5f1b3-214"><sup>\*</sup> Se você clicar nesse valor, informações detalhadas serão exibidas em um sobremenu.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-214"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="5f1b3-215">Exibir envios de usuários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="5f1b3-215">View user submissions to Microsoft</span></span>

<span data-ttu-id="5f1b3-216">Se você tiver implantado o [add-in](enable-the-report-message-add-in.md)De Mensagem de Relatório, o complemento Relatar [Phishing](enable-the-report-phish-add-in.md)ou as pessoas usarem o relatório integrado no Outlook na [Web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)você poderá ver o que os usuários estão relatando na guia **Envios do** usuário.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-216">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="5f1b3-217">No Centro de Conformidade & segurança, vá para **Envios de gerenciamento** \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-217">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="5f1b3-218">Selecione a **guia Envios de usuário** e clique em Novo **envio**.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-218">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="5f1b3-219">Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:</span><span class="sxs-lookup"><span data-stu-id="5f1b3-219">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5f1b3-220">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-220">**Submitted on**</span></span>
- <span data-ttu-id="5f1b3-221">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f1b3-221">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5f1b3-222">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f1b3-222">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="5f1b3-223">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-223">**Sender**</span></span>
- <span data-ttu-id="5f1b3-224">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f1b3-224">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="5f1b3-225">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-225">**Submission type**</span></span>

<span data-ttu-id="5f1b3-226"><sup>\*</sup> Se você clicar nesse valor, informações detalhadas serão exibidas em um sobremenu.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-226"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="5f1b3-227">Na parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão) você pode filtrar por **Remetente** inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="5f1b3-227">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="5f1b3-228">Update</span><span class="sxs-lookup"><span data-stu-id="5f1b3-228">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="5f1b3-229">Para alterar os critérios de filtro, clique no botão **Remetente** e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5f1b3-229">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="5f1b3-230">**Domínio do remetente**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-230">**Sender domain**</span></span>
- <span data-ttu-id="5f1b3-231">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-231">**Subject**</span></span>
- <span data-ttu-id="5f1b3-232">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-232">**Submitted by**</span></span>
- <span data-ttu-id="5f1b3-233">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-233">**Submission type**</span></span>
- <span data-ttu-id="5f1b3-234">**IP do remetente**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-234">**Sender IP**</span></span>

![Novas opções de Filtro para envios de usuários](../../media/user-submissions-filter-options.png)

<span data-ttu-id="5f1b3-236">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **Dados de gráfico** ou **Tabela**.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-236">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="5f1b3-237">Na caixa de diálogo exibida, salve o arquivo .csv arquivo.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-237">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="5f1b3-238">Exibir envios de usuário para a caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="5f1b3-238">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="5f1b3-239">**Se** você configurou [uma caixa](user-submission.md) de correio personalizada para receber mensagens relatadas pelo usuário, você pode exibir e também enviar mensagens que foram entregues à caixa de correio de relatório.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-239">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="5f1b3-240">No Centro de Conformidade & segurança, vá para **Envios de gerenciamento** \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-240">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="5f1b3-241">Selecione a **guia Caixa de correio** Personalizada.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-241">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="5f1b3-242">Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:</span><span class="sxs-lookup"><span data-stu-id="5f1b3-242">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="5f1b3-243">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-243">**Submitted on**</span></span>
- <span data-ttu-id="5f1b3-244">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f1b3-244">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="5f1b3-245">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f1b3-245">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="5f1b3-246">**Sender**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-246">**Sender**</span></span>
- <span data-ttu-id="5f1b3-247">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5f1b3-247">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="5f1b3-248">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-248">**Submission type**</span></span>

<span data-ttu-id="5f1b3-249">Na parte superior da página, você pode inserir uma data de  início, uma data de término e filtrar enviando inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="5f1b3-249">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="5f1b3-250">Update</span><span class="sxs-lookup"><span data-stu-id="5f1b3-250">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="5f1b3-251">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **Dados de gráfico** ou **Tabela**.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-251">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="5f1b3-252">Na caixa de diálogo exibida, salve o arquivo .csv arquivo.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-252">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="5f1b3-253">Se as organizações estão configuradas para enviar somente para a caixa de correio personalizada, as mensagens relatadas não serão enviadas para análise novamente e os resultados no portal de mensagens relatadas pelo usuário sempre estarão vazios.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-253">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="5f1b3-254">Desfazer envios de usuário</span><span class="sxs-lookup"><span data-stu-id="5f1b3-254">Undo user submissions</span></span>

<span data-ttu-id="5f1b3-255">Depois que um usuário envia um email suspeito para a caixa de correio personalizada, o usuário e o administrador não têm uma opção para desfazer o envio.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-255">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="5f1b3-256">Se o usuário quiser recuperar o email, ele estará disponível para recuperação nas pastas Itens Excluídos ou Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-256">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="5f1b3-257">Enviar mensagens para a Microsoft da caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="5f1b3-257">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="5f1b3-258">Se você configurou a caixa de correio personalizada para interceptar mensagens relatadas pelo usuário sem enviar as mensagens para a Microsoft, você poderá encontrar e enviar mensagens específicas para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-258">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="5f1b3-259">Isso move efetivamente um envio de usuário para um envio de administrador.</span><span class="sxs-lookup"><span data-stu-id="5f1b3-259">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="5f1b3-260">Na guia **Mensagens relatadas pelo** usuário, selecione uma mensagem na lista, clique no botão **Ação** e faça uma das seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="5f1b3-260">On the **User reported messages** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="5f1b3-261">**Relatório limpo**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-261">**Report clean**</span></span>
- <span data-ttu-id="5f1b3-262">**Relatar phishing**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-262">**Report phishing**</span></span>
- <span data-ttu-id="5f1b3-263">**Relatar malware**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-263">**Report malware**</span></span>
- <span data-ttu-id="5f1b3-264">**Relatar spam**</span><span class="sxs-lookup"><span data-stu-id="5f1b3-264">**Report spam**</span></span>

![Novas opções no botão Ação](../../media/user-submission-custom-mailbox-action-button.png)
