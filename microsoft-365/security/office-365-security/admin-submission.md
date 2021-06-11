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
description: Os administradores podem aprender a usar o portal envios no centro de segurança do Microsoft 365 para enviar emails suspeitos, emails suspeitos de phishing, spam e outras mensagens potencialmente prejudiciais, URLs e anexos de email à Microsoft para análise de novo.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6de6a018a96407a5690249bea15e90c2f5a0d1ed
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878683"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="9dce6-103">Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft</span><span class="sxs-lookup"><span data-stu-id="9dce6-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="9dce6-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="9dce6-104">**Applies to**</span></span>
- [<span data-ttu-id="9dce6-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9dce6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="9dce6-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="9dce6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="9dce6-107">Em Microsoft 365 organizações com caixas de correio no Exchange Online, os administradores podem usar o portal Envios no Centro de Conformidade & Segurança para enviar mensagens de email, URLs e anexos à Microsoft para verificação.</span><span class="sxs-lookup"><span data-stu-id="9dce6-107">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="9dce6-108">Ao enviar uma mensagem de email, você receberá:</span><span class="sxs-lookup"><span data-stu-id="9dce6-108">When you submit an email message, you will get:</span></span>

1. <span data-ttu-id="9dce6-109">**Verificação de autenticação de** email : Detalhes sobre se a autenticação de email passou ou falhou quando ela foi entregue.</span><span class="sxs-lookup"><span data-stu-id="9dce6-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
2. <span data-ttu-id="9dce6-110">**Visitas de política**: informações sobre quaisquer políticas que possam ter permitido ou bloqueado o email de entrada em seu locatário, substituindo nossos vereditos de filtro de serviço.</span><span class="sxs-lookup"><span data-stu-id="9dce6-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
3. <span data-ttu-id="9dce6-111">**Reputação/detonação** de carga : Exame de quaisquer URLs e anexos na mensagem.</span><span class="sxs-lookup"><span data-stu-id="9dce6-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
4. <span data-ttu-id="9dce6-112">**Análise de notas**: Revisão feita por alunos de nível humano para confirmar se as mensagens são mal-intencionadas ou não.</span><span class="sxs-lookup"><span data-stu-id="9dce6-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9dce6-113">A análise de reputação/detonação e classificação de carga não é feita em todos os locatários.</span><span class="sxs-lookup"><span data-stu-id="9dce6-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="9dce6-114">As informações são impedidas de sair da organização quando os dados não devem sair do limite do locatário para fins de conformidade.</span><span class="sxs-lookup"><span data-stu-id="9dce6-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="9dce6-115">Para outras maneiras de enviar mensagens de email, URLs e anexos à Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="9dce6-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="9dce6-116">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="9dce6-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="9dce6-117">Você abre o Microsoft 365 de segurança em <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="9dce6-117">You open the Microsoft 365 security center at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="9dce6-118">Para ir diretamente para a página **Envios,** use <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="9dce6-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="9dce6-119">Para enviar mensagens e arquivos para a Microsoft, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="9dce6-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="9dce6-120">**Gerenciamento da** organização **ou leitor de segurança** no Microsoft 365 de [segurança.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="9dce6-120">**Organization Management** or **Security Reader** in the [Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>

  - <span data-ttu-id="9dce6-121">**Gerenciamento de organização** em [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="9dce6-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="9dce6-122">Observe que a associação neste grupo de funções é necessária para Exibir [envios](#view-user-submissions-to-the-custom-mailbox) de usuário para a caixa de correio personalizada conforme descrito posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="9dce6-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this article.</span></span>

- <span data-ttu-id="9dce6-123">Para obter mais informações sobre como os usuários podem enviar mensagens e arquivos para a Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="9dce6-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="9dce6-124">Relatar conteúdo suspeito à Microsoft</span><span class="sxs-lookup"><span data-stu-id="9dce6-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="9dce6-125">No centro Microsoft 365 [segurança](../defender/overview-security-center.md), vá para **Envios** e verifique  se você está na guia Enviado para análise e clique em Enviar para **a Microsoft para revisão**.</span><span class="sxs-lookup"><span data-stu-id="9dce6-125">In the [Microsoft 365 security center](../defender/overview-security-center.md), go to **Submissions** and verify that you're on the **Submitted for analysis** tab, and then click **Submit to Microsoft for review**.</span></span>

2. <span data-ttu-id="9dce6-126">Use o sub-sub-texto Enviar para **a Microsoft** para revisão que parece enviar a mensagem, a URL ou o anexo de email, conforme descrito nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="9dce6-126">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="9dce6-127">Enviar um email questionável à Microsoft</span><span class="sxs-lookup"><span data-stu-id="9dce6-127">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="9dce6-128">Na seção **Selecionar o tipo de envio,** selecione **Email**.</span><span class="sxs-lookup"><span data-stu-id="9dce6-128">In the **Select the submission type** section, select **Email**.</span></span> <span data-ttu-id="9dce6-129">Na seção **Adicionar a ID da** mensagem de rede ou carregar o arquivo de email, use uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="9dce6-129">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>

   - <span data-ttu-id="9dce6-130">Adicionar a **ID** da mensagem de rede de email : Este é um valor GUID que está disponível no header **X-MS-Exchange-Organization-Network-Message-Id** na mensagem ou no **header X-MS-Office365-Filtering-Correlation-Id** em mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="9dce6-130">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>

   - <span data-ttu-id="9dce6-131">**Upload arquivo de email**: Clique **em Procurar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="9dce6-131">**Upload the email file**: Click **Browse files**.</span></span> <span data-ttu-id="9dce6-132">Na caixa de diálogo que é aberta, encontre e selecione o arquivo .eml ou .msg e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="9dce6-132">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9dce6-133">A capacidade de enviar mensagens com até 30 dias foi temporariamente suspensa para o Defender Office 365 clientes.</span><span class="sxs-lookup"><span data-stu-id="9dce6-133">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="9dce6-134">Os administradores só poderão voltar 7 dias.</span><span class="sxs-lookup"><span data-stu-id="9dce6-134">Admins will only be able to go back 7 days.</span></span>

2. <span data-ttu-id="9dce6-135">Na seção **Escolher um destinatário que tinha** um problema, especifique o destinatário com o qual você gostaria de executar uma verificação de política.</span><span class="sxs-lookup"><span data-stu-id="9dce6-135">In the **Choose a recipient who had an issue** section, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="9dce6-136">A verificação de política determinará se o email foi ignorado devido a políticas de usuário ou organização.</span><span class="sxs-lookup"><span data-stu-id="9dce6-136">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="9dce6-137">Na seção **Selecionar um motivo para enviar à Microsoft,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="9dce6-137">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>

   - <span data-ttu-id="9dce6-138">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="9dce6-138">**Should not have been blocked**</span></span>

   - <span data-ttu-id="9dce6-139">**Deve ter sido bloqueado**: Selecione **Spam,** **Phishing** ou **Malware**.</span><span class="sxs-lookup"><span data-stu-id="9dce6-139">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="9dce6-140">Se você não tiver certeza, use seu melhor julgamento.</span><span class="sxs-lookup"><span data-stu-id="9dce6-140">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="9dce6-141">Quando terminar, clique no **botão Enviar.**</span><span class="sxs-lookup"><span data-stu-id="9dce6-141">When you're finished, click the **Submit** button.</span></span>

   ![Novo exemplo de envio de URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="9dce6-143">Enviar uma URL suspeita para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="9dce6-143">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="9dce6-144">Na seção **Selecionar o tipo de envio,** selecione **URL**.</span><span class="sxs-lookup"><span data-stu-id="9dce6-144">In the **Select the submission type** section, select **URL**.</span></span> <span data-ttu-id="9dce6-145">Na caixa exibida, insira a URL completa (por exemplo, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="9dce6-145">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="9dce6-146">Na seção **Motivo do envio,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="9dce6-146">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="9dce6-147">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="9dce6-147">**Should not have been blocked**</span></span>

   - <span data-ttu-id="9dce6-148">**Deve ter sido bloqueado**: Selecione **Phishing** ou **Malware.**</span><span class="sxs-lookup"><span data-stu-id="9dce6-148">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="9dce6-149">Quando terminar, clique no **botão Enviar.**</span><span class="sxs-lookup"><span data-stu-id="9dce6-149">When you're finished, click the **Submit** button.</span></span>

   ![Novo exemplo de envio de email](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="9dce6-151">Enviar um anexo de email suspeito à Microsoft</span><span class="sxs-lookup"><span data-stu-id="9dce6-151">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="9dce6-152">Na seção **Selecionar o tipo de envio,** selecione Anexo de **email**.</span><span class="sxs-lookup"><span data-stu-id="9dce6-152">In the **Select the submission type** section, select **Email attachment**.</span></span>

2. <span data-ttu-id="9dce6-153">Clique **em Escolher Arquivo**.</span><span class="sxs-lookup"><span data-stu-id="9dce6-153">Click **Choose File**.</span></span> <span data-ttu-id="9dce6-154">Na caixa de diálogo que é aberta, encontre e selecione o arquivo e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="9dce6-154">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="9dce6-155">Na seção **Motivo do envio,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="9dce6-155">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="9dce6-156">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="9dce6-156">**Should not have been blocked**</span></span>

   - <span data-ttu-id="9dce6-157">**Deve ter sido bloqueado**: **Malware** é a única opção e é selecionado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="9dce6-157">**Should have been blocked**: **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="9dce6-158">Quando terminar, clique no **botão Enviar.**</span><span class="sxs-lookup"><span data-stu-id="9dce6-158">When you're finished, click the **Submit** button.</span></span>

   ![Novo exemplo de envio de anexo](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a><span data-ttu-id="9dce6-160">Exibir itens enviados para análise</span><span class="sxs-lookup"><span data-stu-id="9dce6-160">View items Submitted for analysis</span></span>

<span data-ttu-id="9dce6-161">No centro Microsoft 365 segurança, vá para **Envios** e verifique se você está na guia **Enviado para análise**</span><span class="sxs-lookup"><span data-stu-id="9dce6-161">In the Microsoft 365 security center, go to **Submissions**, and verify that you're on the **Submitted for analysis** tab</span></span>

<span data-ttu-id="9dce6-162">Na barra de comandos no meio da página, você pode inserir uma data de início, uma data de término e (por padrão) você pode filtrar por **ID** de Envio (um valor GUID atribuído a cada envio) inserindo um valor na caixa e clicando em Atualizar botão ![ ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="9dce6-162">In the command bar in the middle of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="9dce6-163">Update</span><span class="sxs-lookup"><span data-stu-id="9dce6-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="9dce6-164">Para alterar os critérios de filtro, clique no botão **Filtro** e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9dce6-164">To change the filter criteria, click the **Filter** button and choose one of the following values:</span></span>

- <span data-ttu-id="9dce6-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="9dce6-165">**Sender**</span></span>
- <span data-ttu-id="9dce6-166">**Assunto/URL/Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="9dce6-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="9dce6-167">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="9dce6-167">**Submitted by**</span></span>
- <span data-ttu-id="9dce6-168">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="9dce6-168">**Submission type**</span></span>
- <span data-ttu-id="9dce6-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="9dce6-169">**Status**</span></span>

![Novas opções de Filtro para envios de administrador](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="9dce6-171">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **Dados de gráfico** ou **Tabela**.</span><span class="sxs-lookup"><span data-stu-id="9dce6-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="9dce6-172">Na caixa de diálogo exibida, salve o arquivo .csv arquivo.</span><span class="sxs-lookup"><span data-stu-id="9dce6-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="9dce6-173">Abaixo do gráfico, há três guias: **Email** (padrão), **URL** e **Anexo de email.**</span><span class="sxs-lookup"><span data-stu-id="9dce6-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Email attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="9dce6-174">Exibir envios de email do administrador</span><span class="sxs-lookup"><span data-stu-id="9dce6-174">View admin email submissions</span></span>

<span data-ttu-id="9dce6-175">Você pode clicar no **botão Personalizar colunas** perto da parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="9dce6-175">You can click the **Customize columns** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9dce6-176">**Date**</span><span class="sxs-lookup"><span data-stu-id="9dce6-176">**Date**</span></span>
- <span data-ttu-id="9dce6-177">**ID do envio:** um valor GUID atribuído a cada envio.</span><span class="sxs-lookup"><span data-stu-id="9dce6-177">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="9dce6-178">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9dce6-178">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9dce6-179">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9dce6-179">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="9dce6-180">**Sender**</span><span class="sxs-lookup"><span data-stu-id="9dce6-180">**Sender**</span></span>
- <span data-ttu-id="9dce6-181">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9dce6-181">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="9dce6-182">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="9dce6-182">**Submission type**</span></span>
- <span data-ttu-id="9dce6-183">**Motivo da entrega**</span><span class="sxs-lookup"><span data-stu-id="9dce6-183">**Delivery reason**</span></span>
- <span data-ttu-id="9dce6-184">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9dce6-184">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="9dce6-185"><sup>\*</sup> Se você clicar nesse valor, informações detalhadas serão exibidas em um sobremenu.</span><span class="sxs-lookup"><span data-stu-id="9dce6-185"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

#### <a name="admin-submission-rescan-details"></a><span data-ttu-id="9dce6-186">Detalhes da verificação de envio de administrador</span><span class="sxs-lookup"><span data-stu-id="9dce6-186">Admin submission rescan details</span></span>

<span data-ttu-id="9dce6-187">As mensagens enviadas em envios de administrador são exibidas novamente e os resultados mostrados no submenu de detalhes de envios:</span><span class="sxs-lookup"><span data-stu-id="9dce6-187">Messages that are submitted in admin submissions are rescanned and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="9dce6-188">Se houve falha na autenticação do email do remetente no momento da entrega.</span><span class="sxs-lookup"><span data-stu-id="9dce6-188">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="9dce6-189">Informações sobre quaisquer acessos à política que possam ter afetado ou substituído o veredicto de uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="9dce6-189">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="9dce6-190">Resultados de detonação atuais para ver se os URLs ou arquivos contidos na mensagem eram maliciosos ou não.</span><span class="sxs-lookup"><span data-stu-id="9dce6-190">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="9dce6-191">Comentários dos alunos.</span><span class="sxs-lookup"><span data-stu-id="9dce6-191">Feedback from graders.</span></span>

<span data-ttu-id="9dce6-192">Se uma substituição for encontrada, a nova varredura deve ser concluída em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="9dce6-192">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="9dce6-193">Se não houve um problema na autenticação ou na entrega de email não foi afetado por uma substituição, os comentários dos alunos podem levar até um dia.</span><span class="sxs-lookup"><span data-stu-id="9dce6-193">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="9dce6-194">Exibir envios de URL do administrador</span><span class="sxs-lookup"><span data-stu-id="9dce6-194">View admin URL submissions</span></span>

<span data-ttu-id="9dce6-195">Clique na **guia URL.**</span><span class="sxs-lookup"><span data-stu-id="9dce6-195">Click the **URL** tab.</span></span>

<span data-ttu-id="9dce6-196">Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:</span><span class="sxs-lookup"><span data-stu-id="9dce6-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9dce6-197">**Date**</span><span class="sxs-lookup"><span data-stu-id="9dce6-197">**Date**</span></span>
- <span data-ttu-id="9dce6-198">**ID do envio**</span><span class="sxs-lookup"><span data-stu-id="9dce6-198">**Submission ID**</span></span>
- <span data-ttu-id="9dce6-199">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9dce6-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9dce6-200">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9dce6-200">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="9dce6-201">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="9dce6-201">**Submission type**</span></span>
- <span data-ttu-id="9dce6-202">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9dce6-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="9dce6-203"><sup>\*</sup> Se você clicar nesse valor, informações detalhadas serão exibidas em um sobremenu.</span><span class="sxs-lookup"><span data-stu-id="9dce6-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-email-attachment-submissions"></a><span data-ttu-id="9dce6-204">Exibir envios de anexos de email</span><span class="sxs-lookup"><span data-stu-id="9dce6-204">View email attachment submissions</span></span>

<span data-ttu-id="9dce6-205">Clique na **guia Anexos.**</span><span class="sxs-lookup"><span data-stu-id="9dce6-205">Click the **Attachments** tab.</span></span>

<span data-ttu-id="9dce6-206">Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:</span><span class="sxs-lookup"><span data-stu-id="9dce6-206">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9dce6-207">**Date**</span><span class="sxs-lookup"><span data-stu-id="9dce6-207">**Date**</span></span>
- <span data-ttu-id="9dce6-208">**ID do envio**</span><span class="sxs-lookup"><span data-stu-id="9dce6-208">**Submission ID**</span></span>
- <span data-ttu-id="9dce6-209">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9dce6-209">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9dce6-210">**Nome do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9dce6-210">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="9dce6-211">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="9dce6-211">**Submission type**</span></span>
- <span data-ttu-id="9dce6-212">**Status**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9dce6-212">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="9dce6-213"><sup>\*</sup> Se você clicar nesse valor, informações detalhadas serão exibidas em um sobremenu.</span><span class="sxs-lookup"><span data-stu-id="9dce6-213"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="9dce6-214">Exibir envios de usuários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="9dce6-214">View user submissions to Microsoft</span></span>

<span data-ttu-id="9dce6-215">Se você tiver implantado o [add-in](enable-the-report-message-add-in.md)De Mensagem de Relatório, o complemento Relatar [Phishing](enable-the-report-phish-add-in.md)ou as pessoas usarem o relatório integrado no Outlook na [Web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)você poderá ver o que os usuários estão relatando na guia **Envios do** usuário.</span><span class="sxs-lookup"><span data-stu-id="9dce6-215">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="9dce6-216">No Centro de Conformidade & segurança, vá para **Envios de gerenciamento** \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="9dce6-216">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="9dce6-217">Selecione a **guia Envios de usuário** e clique em Novo **envio**.</span><span class="sxs-lookup"><span data-stu-id="9dce6-217">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="9dce6-218">Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:</span><span class="sxs-lookup"><span data-stu-id="9dce6-218">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9dce6-219">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="9dce6-219">**Submitted on**</span></span>
- <span data-ttu-id="9dce6-220">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9dce6-220">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9dce6-221">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9dce6-221">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="9dce6-222">**Sender**</span><span class="sxs-lookup"><span data-stu-id="9dce6-222">**Sender**</span></span>
- <span data-ttu-id="9dce6-223">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9dce6-223">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="9dce6-224">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="9dce6-224">**Submission type**</span></span>

<span data-ttu-id="9dce6-225"><sup>\*</sup> Se você clicar nesse valor, informações detalhadas serão exibidas em um sobremenu.</span><span class="sxs-lookup"><span data-stu-id="9dce6-225"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="9dce6-226">Na parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão) você pode filtrar por **Remetente** inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="9dce6-226">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="9dce6-227">Update</span><span class="sxs-lookup"><span data-stu-id="9dce6-227">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="9dce6-228">Para alterar os critérios de filtro, clique no botão **Remetente** e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="9dce6-228">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="9dce6-229">**Domínio do remetente**</span><span class="sxs-lookup"><span data-stu-id="9dce6-229">**Sender domain**</span></span>
- <span data-ttu-id="9dce6-230">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="9dce6-230">**Subject**</span></span>
- <span data-ttu-id="9dce6-231">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="9dce6-231">**Submitted by**</span></span>
- <span data-ttu-id="9dce6-232">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="9dce6-232">**Submission type**</span></span>
- <span data-ttu-id="9dce6-233">**IP do remetente**</span><span class="sxs-lookup"><span data-stu-id="9dce6-233">**Sender IP**</span></span>

![Novas opções de Filtro para envios de usuários](../../media/user-submissions-filter-options.png)

<span data-ttu-id="9dce6-235">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **Dados de gráfico** ou **Tabela**.</span><span class="sxs-lookup"><span data-stu-id="9dce6-235">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="9dce6-236">Na caixa de diálogo exibida, salve o arquivo .csv arquivo.</span><span class="sxs-lookup"><span data-stu-id="9dce6-236">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="9dce6-237">Exibir envios de usuário para a caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="9dce6-237">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="9dce6-238">**Se** você configurou [uma caixa](user-submission.md) de correio personalizada para receber mensagens relatadas pelo usuário, você pode exibir e também enviar mensagens que foram entregues à caixa de correio de relatório.</span><span class="sxs-lookup"><span data-stu-id="9dce6-238">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="9dce6-239">No Centro de Conformidade & segurança, vá para **Envios de gerenciamento** \> **de ameaças.**</span><span class="sxs-lookup"><span data-stu-id="9dce6-239">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="9dce6-240">Selecione a **guia Caixa de correio** Personalizada.</span><span class="sxs-lookup"><span data-stu-id="9dce6-240">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="9dce6-241">Você pode clicar no **botão Opções de** coluna perto da parte inferior da página para adicionar ou remover colunas do exibição:</span><span class="sxs-lookup"><span data-stu-id="9dce6-241">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="9dce6-242">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="9dce6-242">**Submitted on**</span></span>
- <span data-ttu-id="9dce6-243">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9dce6-243">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="9dce6-244">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9dce6-244">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="9dce6-245">**Sender**</span><span class="sxs-lookup"><span data-stu-id="9dce6-245">**Sender**</span></span>
- <span data-ttu-id="9dce6-246">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="9dce6-246">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="9dce6-247">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="9dce6-247">**Submission type**</span></span>

<span data-ttu-id="9dce6-248">Na parte superior da página, você pode inserir uma data de  início, uma data de término e filtrar enviando inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="9dce6-248">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="9dce6-249">Update</span><span class="sxs-lookup"><span data-stu-id="9dce6-249">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="9dce6-250">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **Dados de gráfico** ou **Tabela**.</span><span class="sxs-lookup"><span data-stu-id="9dce6-250">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="9dce6-251">Na caixa de diálogo exibida, salve o arquivo .csv arquivo.</span><span class="sxs-lookup"><span data-stu-id="9dce6-251">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="9dce6-252">Se as organizações estão configuradas para enviar somente para a caixa de correio personalizada, as mensagens relatadas não serão enviadas para análise novamente e os resultados no portal de mensagens relatadas pelo usuário sempre estarão vazios.</span><span class="sxs-lookup"><span data-stu-id="9dce6-252">If organizations are configured to send to custom mailbox only, reported messages will not be sent for rescan and results in the User reported messages portal will always be empty.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="9dce6-253">Desfazer envios de usuário</span><span class="sxs-lookup"><span data-stu-id="9dce6-253">Undo user submissions</span></span>

<span data-ttu-id="9dce6-254">Depois que um usuário envia um email suspeito para a caixa de correio personalizada, o usuário e o administrador não têm uma opção para desfazer o envio.</span><span class="sxs-lookup"><span data-stu-id="9dce6-254">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="9dce6-255">Se o usuário quiser recuperar o email, ele estará disponível para recuperação nas pastas Itens Excluídos ou Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="9dce6-255">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="9dce6-256">Enviar mensagens para a Microsoft da caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="9dce6-256">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="9dce6-257">Se você configurou a caixa de correio personalizada para interceptar mensagens relatadas pelo usuário sem enviar as mensagens para a Microsoft, você poderá encontrar e enviar mensagens específicas para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="9dce6-257">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="9dce6-258">Isso move efetivamente um envio de usuário para um envio de administrador.</span><span class="sxs-lookup"><span data-stu-id="9dce6-258">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="9dce6-259">Na guia **Mensagens relatadas pelo** usuário, selecione uma mensagem na lista, clique no botão **Ação** e faça uma das seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="9dce6-259">On the **User reported messages** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="9dce6-260">**Relatório limpo**</span><span class="sxs-lookup"><span data-stu-id="9dce6-260">**Report clean**</span></span>
- <span data-ttu-id="9dce6-261">**Relatar phishing**</span><span class="sxs-lookup"><span data-stu-id="9dce6-261">**Report phishing**</span></span>
- <span data-ttu-id="9dce6-262">**Relatar malware**</span><span class="sxs-lookup"><span data-stu-id="9dce6-262">**Report malware**</span></span>
- <span data-ttu-id="9dce6-263">**Relatar spam**</span><span class="sxs-lookup"><span data-stu-id="9dce6-263">**Report spam**</span></span>

![Novas opções no botão Ação](../../media/user-submission-custom-mailbox-action-button.png)
