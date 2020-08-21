---
title: Envios de administrador
f1.keywords:
- NOCSH
ms.author: chrisda
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
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o portal de envios no centro de conformidade de & de segurança para enviar emails suspeitos, emails de phishing, spam e outras mensagens, URLs e arquivos potencialmente nocivos para a Microsoft para verificação.
ms.openlocfilehash: 1b3715e3ed6f0472d9202573ff0cab92f7240ffa
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845961"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="8576a-103">Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft</span><span class="sxs-lookup"><span data-stu-id="8576a-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="8576a-104">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online, os administradores podem usar o portal de envios no centro de conformidade de & de segurança para enviar mensagens de email, URLs e anexos para a Microsoft para verificação.</span><span class="sxs-lookup"><span data-stu-id="8576a-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="8576a-105">Ao enviar um email, você receberá informações sobre qualquer política que possa ter permitido o email de entrada em seu locatário, bem como o exame de qualquer URL e anexo no email.</span><span class="sxs-lookup"><span data-stu-id="8576a-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="8576a-106">As políticas que podem ter permitido um email incluem a lista de remetentes confiáveis de um usuário individual, bem como políticas de nível de locatário, como regras de fluxo de emails do Exchange (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="8576a-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="8576a-107">Para obter outras maneiras de enviar mensagens de email, URLs e anexos para a Microsoft, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="8576a-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8576a-108">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="8576a-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8576a-109">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="8576a-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="8576a-110">Para ir diretamente para a página de **envio** , use <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="8576a-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="8576a-111">Você precisa ter permissões atribuídas antes de poder executar os procedimentos neste tópico:</span><span class="sxs-lookup"><span data-stu-id="8576a-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="8576a-112">Para enviar mensagens e arquivos para a Microsoft, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="8576a-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="8576a-113">**Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="8576a-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="8576a-114">**Gerenciamento de organizações** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="8576a-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="8576a-115">Para acesso somente leitura ao portal de envios, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="8576a-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="8576a-116">**Leitor de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="8576a-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="8576a-117">**Gerenciamento da organização Somente visualização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="8576a-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="8576a-118">Para obter mais informações sobre como os usuários podem enviar mensagens e arquivos para a Microsoft, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="8576a-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="8576a-119">Relatar conteúdo suspeito para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="8576a-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="8576a-120">No centro de conformidade & segurança, vá para **Threat management** \> **envios**de gerenciamento de ameaças, verifique se você está na guia **envios de administrador** e clique em **novo envio**.</span><span class="sxs-lookup"><span data-stu-id="8576a-120">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="8576a-121">Use um novo submenu de **envio** que parece enviar a mensagem, a URL ou o anexo, conforme descrito nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="8576a-121">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="8576a-122">Enviar um email questionável à Microsoft</span><span class="sxs-lookup"><span data-stu-id="8576a-122">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="8576a-123">Na seção **tipo de objeto** , selecione **email**.</span><span class="sxs-lookup"><span data-stu-id="8576a-123">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="8576a-124">Na seção **formato de envio** , use uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="8576a-124">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="8576a-125">**ID da mensagem de rede**: Este é um valor de GUID que está disponível no cabeçalho **X-MS-Exchange-Organization-Network-Message-ID** na mensagem.</span><span class="sxs-lookup"><span data-stu-id="8576a-125">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="8576a-126">**Arquivo**: clique em **escolher arquivo**.</span><span class="sxs-lookup"><span data-stu-id="8576a-126">**File**: Click **Choose file**.</span></span> <span data-ttu-id="8576a-127">Na caixa de diálogo que é aberta, localize e selecione o arquivo. eml ou. msg e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="8576a-127">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="8576a-128">Na seção **destinatários** , especifique um ou mais destinatários em relação à qual você gostaria de executar uma verificação de política.</span><span class="sxs-lookup"><span data-stu-id="8576a-128">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="8576a-129">A verificação de política determinará se o email ignorará a verificação por causa de políticas de usuário ou organização.</span><span class="sxs-lookup"><span data-stu-id="8576a-129">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="8576a-130">Na seção **motivo da envio** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="8576a-130">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="8576a-131">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="8576a-131">**Should not have been blocked**</span></span>

   - <span data-ttu-id="8576a-132">**Deveriam ter sido bloqueados**: selecione **spam**, **phishing**ou **malware**.</span><span class="sxs-lookup"><span data-stu-id="8576a-132">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="8576a-133">Se você não tiver certeza, use a melhor avaliação.</span><span class="sxs-lookup"><span data-stu-id="8576a-133">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="8576a-134">Se o filtro tiver sido ignorado devido às políticas após o envio, você verá informações sobre essa política.</span><span class="sxs-lookup"><span data-stu-id="8576a-134">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="8576a-135">Se o filtro não tiver sido ignorado devido a uma ou mais políticas, a verificação será concluída em vários minutos.</span><span class="sxs-lookup"><span data-stu-id="8576a-135">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="8576a-136">Você verá informações adicionais sobre o envio clicando no link status.</span><span class="sxs-lookup"><span data-stu-id="8576a-136">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="8576a-137">Isso inclui os resultados da verificação de política e a veredicto de nova verificação.</span><span class="sxs-lookup"><span data-stu-id="8576a-137">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="8576a-138">Observação isso não executa o email por meio da pilha de filtragem completa do Office 365 ATP novamente, mas executa uma verificação parcial com base em determinados atributos do email, da URL ou do arquivo.</span><span class="sxs-lookup"><span data-stu-id="8576a-138">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="8576a-139">Quando tiver concluído, clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="8576a-139">When you're finished, click the **Submit** button.</span></span>

![Exemplo de envio de URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="8576a-141">Enviar uma URL suspeita para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="8576a-141">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="8576a-142">Na seção **tipo de objeto** , selecione **URL**.</span><span class="sxs-lookup"><span data-stu-id="8576a-142">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="8576a-143">Na caixa exibida, digite a URL completa (por exemplo, <https://www.fabrikam.com/marketing.html> ).</span><span class="sxs-lookup"><span data-stu-id="8576a-143">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="8576a-144">Na seção **motivo da envio** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="8576a-144">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="8576a-145">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="8576a-145">**Should not have been blocked**</span></span>

   - <span data-ttu-id="8576a-146">**Deveria ter sido bloqueado**: selecione **phishing** ou **malware**.</span><span class="sxs-lookup"><span data-stu-id="8576a-146">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="8576a-147">Quando tiver concluído, clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="8576a-147">When you're finished, click the **Submit** button.</span></span>

![Exemplo de envio de email](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="8576a-149">Enviar um arquivo suspeito para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="8576a-149">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="8576a-150">Na seção **tipo de objeto** , selecione **anexo**.</span><span class="sxs-lookup"><span data-stu-id="8576a-150">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="8576a-151">Clique em **escolher arquivo**.</span><span class="sxs-lookup"><span data-stu-id="8576a-151">Click **Choose File**.</span></span> <span data-ttu-id="8576a-152">Na caixa de diálogo que é aberta, localize e selecione o arquivo e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="8576a-152">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="8576a-153">Na seção **motivo da envio** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="8576a-153">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="8576a-154">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="8576a-154">**Should not have been blocked**</span></span>

   - <span data-ttu-id="8576a-155">**Deveria ter sido bloqueado**: o **malware** é a única opção e é selecionado automaticamente..</span><span class="sxs-lookup"><span data-stu-id="8576a-155">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="8576a-156">Quando tiver concluído, clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="8576a-156">When you're finished, click the **Submit** button.</span></span>

![Exemplo de envio de anexos](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="8576a-158">Exibir envios de administradores</span><span class="sxs-lookup"><span data-stu-id="8576a-158">View admin submissions</span></span>

<span data-ttu-id="8576a-159">No centro de conformidade & segurança, vá para **Threat management** \> **envios**de gerenciamento de ameaças, verifique se você está na guia **envios de administrador** e clique em **novo envio**.</span><span class="sxs-lookup"><span data-stu-id="8576a-159">In the Security & Compliance Center, go to **Threat management** \> **Submissions**, verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="8576a-160">Próximo à parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão), você pode filtrar por **ID de envio** (um valor de GUID que é atribuído a cada envio) inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="8576a-160">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="8576a-161">Update</span><span class="sxs-lookup"><span data-stu-id="8576a-161">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="8576a-162">Para alterar os critérios de filtro, clique no botão **ID de envio** e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="8576a-162">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="8576a-163">**Sender**</span><span class="sxs-lookup"><span data-stu-id="8576a-163">**Sender**</span></span>
- <span data-ttu-id="8576a-164">**Assunto/URL/nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="8576a-164">**Subject/URL/File name**</span></span>
- <span data-ttu-id="8576a-165">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="8576a-165">**Submitted by**</span></span>
- <span data-ttu-id="8576a-166">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="8576a-166">**Submission type**</span></span>
- <span data-ttu-id="8576a-167">**Status**</span><span class="sxs-lookup"><span data-stu-id="8576a-167">**Status**</span></span>

![Opções de filtro para envios de administradores](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="8576a-169">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **dados do gráfico** ou **tabela**.</span><span class="sxs-lookup"><span data-stu-id="8576a-169">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="8576a-170">Na caixa de diálogo exibida, salve o arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="8576a-170">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="8576a-171">Abaixo do gráfico, há três guias: **email** (padrão), **URL**e **anexo**.</span><span class="sxs-lookup"><span data-stu-id="8576a-171">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="8576a-172">Exibir envios de email de administração</span><span class="sxs-lookup"><span data-stu-id="8576a-172">View admin email submissions</span></span>

<span data-ttu-id="8576a-173">Clique na guia **email** .</span><span class="sxs-lookup"><span data-stu-id="8576a-173">Click the **Email** tab.</span></span>

<span data-ttu-id="8576a-174">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="8576a-174">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="8576a-175">**Date**</span><span class="sxs-lookup"><span data-stu-id="8576a-175">**Date**</span></span>
- <span data-ttu-id="8576a-176">**ID de envio**: um valor de GUID que é atribuído a cada envio.</span><span class="sxs-lookup"><span data-stu-id="8576a-176">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="8576a-177">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8576a-177">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="8576a-178">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8576a-178">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="8576a-179">**Sender**</span><span class="sxs-lookup"><span data-stu-id="8576a-179">**Sender**</span></span>
- <span data-ttu-id="8576a-180">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8576a-180">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="8576a-181">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="8576a-181">**Submission type**</span></span>
- <span data-ttu-id="8576a-182">**Motivo da entrega**</span><span class="sxs-lookup"><span data-stu-id="8576a-182">**Delivery reason**</span></span>
- <span data-ttu-id="8576a-183">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8576a-183">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="8576a-184">**Tipo de controle**</span><span class="sxs-lookup"><span data-stu-id="8576a-184">**Control type**</span></span>
- <span data-ttu-id="8576a-185">**Fonte de controle**</span><span class="sxs-lookup"><span data-stu-id="8576a-185">**Control source**</span></span>

  <span data-ttu-id="8576a-186"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="8576a-186"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="8576a-187">Exibir envios de URL de administração</span><span class="sxs-lookup"><span data-stu-id="8576a-187">View admin URL submissions</span></span>

<span data-ttu-id="8576a-188">Clique na guia **URL** .</span><span class="sxs-lookup"><span data-stu-id="8576a-188">Click the **URL** tab.</span></span>

<span data-ttu-id="8576a-189">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="8576a-189">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="8576a-190">**Date**</span><span class="sxs-lookup"><span data-stu-id="8576a-190">**Date**</span></span>
- <span data-ttu-id="8576a-191">**ID de envio**</span><span class="sxs-lookup"><span data-stu-id="8576a-191">**Submission ID**</span></span>
- <span data-ttu-id="8576a-192">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8576a-192">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="8576a-193">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8576a-193">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="8576a-194">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="8576a-194">**Submission type**</span></span>
- <span data-ttu-id="8576a-195">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8576a-195">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="8576a-196"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="8576a-196"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="8576a-197">Exibir envios de anexo de administrador</span><span class="sxs-lookup"><span data-stu-id="8576a-197">View admin attachment submissions</span></span>

<span data-ttu-id="8576a-198">Clique na guia **anexos** .</span><span class="sxs-lookup"><span data-stu-id="8576a-198">Click the **Attachments** tab.</span></span>

<span data-ttu-id="8576a-199">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="8576a-199">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="8576a-200">**Date**</span><span class="sxs-lookup"><span data-stu-id="8576a-200">**Date**</span></span>
- <span data-ttu-id="8576a-201">**ID de envio**</span><span class="sxs-lookup"><span data-stu-id="8576a-201">**Submission ID**</span></span>
- <span data-ttu-id="8576a-202">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8576a-202">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="8576a-203">**Nome do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8576a-203">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="8576a-204">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="8576a-204">**Submission type**</span></span>
- <span data-ttu-id="8576a-205">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8576a-205">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="8576a-206"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="8576a-206"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="8576a-207">Exibir envios de usuários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="8576a-207">View user submissions to Microsoft</span></span>

<span data-ttu-id="8576a-208">Se você tiver implantado o [suplemento de mensagem de relatório](enable-the-report-message-add-in.md)ou se as pessoas usarem [relatórios internos no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), você poderá ver quais usuários estão relatando na guia **envios** de usuários.</span><span class="sxs-lookup"><span data-stu-id="8576a-208">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="8576a-209">No centro de conformidade & segurança, vá para **Threat management** \> **envios**de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="8576a-209">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="8576a-210">Selecione a guia envios de **usuário** e clique em **novo envio**.</span><span class="sxs-lookup"><span data-stu-id="8576a-210">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="8576a-211">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="8576a-211">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="8576a-212">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="8576a-212">**Submitted on**</span></span>
- <span data-ttu-id="8576a-213">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8576a-213">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="8576a-214">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8576a-214">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="8576a-215">**Sender**</span><span class="sxs-lookup"><span data-stu-id="8576a-215">**Sender**</span></span>
- <span data-ttu-id="8576a-216">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8576a-216">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="8576a-217">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="8576a-217">**Submission type**</span></span>

<span data-ttu-id="8576a-218"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="8576a-218"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="8576a-219">Próximo à parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão), você pode filtrar por **remetente** inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="8576a-219">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="8576a-220">Update</span><span class="sxs-lookup"><span data-stu-id="8576a-220">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="8576a-221">Para alterar os critérios de filtro, clique no botão **remetente** e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="8576a-221">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="8576a-222">**Domínio do remetente**</span><span class="sxs-lookup"><span data-stu-id="8576a-222">**Sender domain**</span></span>
- <span data-ttu-id="8576a-223">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="8576a-223">**Subject**</span></span>
- <span data-ttu-id="8576a-224">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="8576a-224">**Submitted by**</span></span>
- <span data-ttu-id="8576a-225">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="8576a-225">**Submission type**</span></span>
- <span data-ttu-id="8576a-226">**IP do remetente**</span><span class="sxs-lookup"><span data-stu-id="8576a-226">**Sender IP**</span></span>

![Opções de filtro para envios de usuários](../../media/user-submissions-filter-options.png)

<span data-ttu-id="8576a-228">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **dados do gráfico** ou **tabela**.</span><span class="sxs-lookup"><span data-stu-id="8576a-228">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="8576a-229">Na caixa de diálogo exibida, salve o arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="8576a-229">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="8576a-230">Exibir envios de usuários para a caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="8576a-230">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="8576a-231">Se você [configurou uma caixa de correio personalizada](user-submission.md) para receber mensagens relatadas pelo usuário, você pode exibir e também enviar mensagens que foram entregues à caixa de correio de relatório.</span><span class="sxs-lookup"><span data-stu-id="8576a-231">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="8576a-232">No centro de conformidade & segurança, vá para **Threat management** \> **envios**de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="8576a-232">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="8576a-233">Selecione a guia **caixa de correio personalizada** .</span><span class="sxs-lookup"><span data-stu-id="8576a-233">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="8576a-234">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="8576a-234">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="8576a-235">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="8576a-235">**Submitted on**</span></span>
- <span data-ttu-id="8576a-236">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8576a-236">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="8576a-237">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8576a-237">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="8576a-238">**Sender**</span><span class="sxs-lookup"><span data-stu-id="8576a-238">**Sender**</span></span>
- <span data-ttu-id="8576a-239">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="8576a-239">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="8576a-240">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="8576a-240">**Submission type**</span></span>

<span data-ttu-id="8576a-241">Próximo à parte superior da página, você pode inserir uma data de início, uma data de término e filtrar por **enviado** , inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="8576a-241">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="8576a-242">Update</span><span class="sxs-lookup"><span data-stu-id="8576a-242">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="8576a-243">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **dados do gráfico** ou **tabela**.</span><span class="sxs-lookup"><span data-stu-id="8576a-243">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="8576a-244">Na caixa de diálogo exibida, salve o arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="8576a-244">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="8576a-245">Enviar mensagens para a Microsoft a partir da caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="8576a-245">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="8576a-246">Se você tiver configurado a caixa de correio personalizada para interceptar mensagens relatadas pelo usuário sem enviar as mensagens à Microsoft, poderá encontrar e enviar mensagens específicas para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="8576a-246">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="8576a-247">Isso move efetivamente um envio de usuário para um envio de administrador.</span><span class="sxs-lookup"><span data-stu-id="8576a-247">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="8576a-248">Na guia **caixa de correio personalizada** , selecione uma mensagem na lista, clique no botão de **ação** e faça uma das seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="8576a-248">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="8576a-249">**Limpeza de relatório**</span><span class="sxs-lookup"><span data-stu-id="8576a-249">**Report clean**</span></span>
- <span data-ttu-id="8576a-250">**Relatar phishing**</span><span class="sxs-lookup"><span data-stu-id="8576a-250">**Report phishing**</span></span>
- <span data-ttu-id="8576a-251">**Relatar malware**</span><span class="sxs-lookup"><span data-stu-id="8576a-251">**Report malware**</span></span>
- <span data-ttu-id="8576a-252">**Relatar spam**</span><span class="sxs-lookup"><span data-stu-id="8576a-252">**Report spam**</span></span>

![Opções no botão de ação](../../media/user-submission-custom-mailbox-action-button.png)
