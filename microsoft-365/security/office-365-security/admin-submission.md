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
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o portal de envios no centro de conformidade de & de segurança para enviar emails suspeitos, emails de phishing, spam e outras mensagens, URLs e arquivos potencialmente nocivos para a Microsoft para verificação.
ms.openlocfilehash: 1ca1dc5e740aa5aa03a4c8b0c138eadb55c08a20
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844639"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="3d5b7-103">Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d5b7-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3d5b7-104">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online, os administradores podem usar o portal de envios no centro de conformidade de & de segurança para enviar mensagens de email, URLs e anexos para a Microsoft para verificação.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="3d5b7-105">Ao enviar um email, você receberá informações sobre qualquer política que possa ter permitido o email de entrada em seu locatário, bem como o exame de qualquer URL e anexo no email.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="3d5b7-106">As políticas que podem ter permitido um email incluem a lista de remetentes confiáveis de um usuário individual, bem como políticas de nível de locatário, como regras de fluxo de emails do Exchange (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="3d5b7-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="3d5b7-107">Para obter outras maneiras de enviar mensagens de email, URLs e anexos para a Microsoft, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="3d5b7-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3d5b7-108">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="3d5b7-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3d5b7-109">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3d5b7-110">Para ir diretamente para a página de **envio** , use <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="3d5b7-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="3d5b7-111">Para enviar mensagens e arquivos para a Microsoft, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="3d5b7-111">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="3d5b7-112">**Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3d5b7-112">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  - <span data-ttu-id="3d5b7-113">**Gerenciamento de organização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="3d5b7-113">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="3d5b7-114">Observe que a associação ao grupo de funções é necessária para [Exibir envios de usuários para a caixa de correio personalizada](#view-user-submissions-to-the-custom-mailbox) , conforme descrito mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-114">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-the-custom-mailbox) as described later in this topic.</span></span>

- <span data-ttu-id="3d5b7-115">Para obter mais informações sobre como os usuários podem enviar mensagens e arquivos para a Microsoft, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="3d5b7-115">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="3d5b7-116">Relatar conteúdo suspeito para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d5b7-116">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="3d5b7-117">No centro de conformidade & segurança, vá para **Threat management** \> **envios** de gerenciamento de ameaças, verifique se você está na guia **envios de administrador** e clique em **novo envio**.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-117">In the Security & Compliance Center, go to **Threat management** \> **Submissions** , verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

2. <span data-ttu-id="3d5b7-118">Use um novo submenu de **envio** que parece enviar a mensagem, a URL ou o anexo, conforme descrito nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="3d5b7-119">Enviar um email questionável à Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d5b7-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="3d5b7-120">Na seção **tipo de objeto** , selecione **email**.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="3d5b7-121">Na seção **formato de envio** , use uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="3d5b7-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="3d5b7-122">**ID da mensagem de rede** : Este é um valor de GUID que está disponível no cabeçalho **X-MS-Exchange-Organization-Network-Message-ID** na mensagem.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-122">**Network Message ID** : This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="3d5b7-123">**Arquivo** : clique em **escolher arquivo**.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-123">**File** : Click **Choose file**.</span></span> <span data-ttu-id="3d5b7-124">Na caixa de diálogo que é aberta, localize e selecione o arquivo. eml ou. msg e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="3d5b7-125">Na seção **destinatários** , especifique um ou mais destinatários em relação à qual você gostaria de executar uma verificação de política.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="3d5b7-126">A verificação de política determinará se o email ignorará a verificação por causa de políticas de usuário ou organização.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="3d5b7-127">Na seção **motivo da envio** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="3d5b7-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="3d5b7-128">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="3d5b7-129">**Deveriam ter sido bloqueados** : selecione **spam** , **phishing** ou **malware**.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-129">**Should have been blocked** : Select **Spam** , **Phishing** , or **Malware**.</span></span> <span data-ttu-id="3d5b7-130">Se você não tiver certeza, use a melhor avaliação.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="3d5b7-131">Se o filtro tiver sido ignorado devido às políticas após o envio, você verá informações sobre essa política.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="3d5b7-132">Se o filtro não tiver sido ignorado devido a uma ou mais políticas, a verificação será concluída em vários minutos.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="3d5b7-133">Você verá informações adicionais sobre o envio clicando no link status.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="3d5b7-134">Isso inclui os resultados da verificação de política e a veredicto de nova verificação.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="3d5b7-135">Observação isso não executa o email por meio da pilha de filtragem completa do Microsoft defender para Office 365 novamente, mas executa uma verificação parcial com base em determinados atributos do email, da URL ou do arquivo.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-135">Note this does not run the email through the Microsoft Defender for Office 365 full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="3d5b7-136">Quando tiver concluído, clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="3d5b7-136">When you're finished, click the **Submit** button.</span></span>

![Exemplo de envio de URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="3d5b7-138">Enviar uma URL suspeita para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d5b7-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="3d5b7-139">Na seção **tipo de objeto** , selecione **URL**.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="3d5b7-140">Na caixa exibida, digite a URL completa (por exemplo, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="3d5b7-140">In the box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

2. <span data-ttu-id="3d5b7-141">Na seção **motivo da envio** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="3d5b7-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="3d5b7-142">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="3d5b7-143">**Deveria ter sido bloqueado** : selecione **phishing** ou **malware**.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-143">**Should have been blocked** : Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="3d5b7-144">Quando tiver concluído, clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="3d5b7-144">When you're finished, click the **Submit** button.</span></span>

![Exemplo de envio de email](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="3d5b7-146">Enviar um arquivo suspeito para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d5b7-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="3d5b7-147">Na seção **tipo de objeto** , selecione **anexo**.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="3d5b7-148">Clique em **escolher arquivo**.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-148">Click **Choose File**.</span></span> <span data-ttu-id="3d5b7-149">Na caixa de diálogo que é aberta, localize e selecione o arquivo e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="3d5b7-150">Na seção **motivo da envio** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="3d5b7-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="3d5b7-151">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="3d5b7-152">**Deveria ter sido bloqueado** : o **malware** é a única opção e é selecionado automaticamente..</span><span class="sxs-lookup"><span data-stu-id="3d5b7-152">**Should have been blocked** : **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="3d5b7-153">Quando tiver concluído, clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="3d5b7-153">When you're finished, click the **Submit** button.</span></span>

![Exemplo de envio de anexos](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="3d5b7-155">Exibir envios de administradores</span><span class="sxs-lookup"><span data-stu-id="3d5b7-155">View admin submissions</span></span>

<span data-ttu-id="3d5b7-156">No centro de conformidade & segurança, vá para **Threat management** \> **envios** de gerenciamento de ameaças, verifique se você está na guia **envios de administrador** e clique em **novo envio**.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-156">In the Security & Compliance Center, go to **Threat management** \> **Submissions** , verify that you're on the **Admin submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="3d5b7-157">Próximo à parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão), você pode filtrar por **ID de envio** (um valor de GUID que é atribuído a cada envio) inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="3d5b7-157">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="3d5b7-158">Update</span><span class="sxs-lookup"><span data-stu-id="3d5b7-158">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="3d5b7-159">Para alterar os critérios de filtro, clique no botão **ID de envio** e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="3d5b7-159">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="3d5b7-160">**Sender**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-160">**Sender**</span></span>
- <span data-ttu-id="3d5b7-161">**Assunto/URL/nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-161">**Subject/URL/File name**</span></span>
- <span data-ttu-id="3d5b7-162">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-162">**Submitted by**</span></span>
- <span data-ttu-id="3d5b7-163">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-163">**Submission type**</span></span>
- <span data-ttu-id="3d5b7-164">**Status**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-164">**Status**</span></span>

![Opções de filtro para envios de administradores](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="3d5b7-166">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **dados do gráfico** ou **tabela**.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-166">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="3d5b7-167">Na caixa de diálogo exibida, salve o arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-167">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="3d5b7-168">Abaixo do gráfico, há três guias: **email** (padrão), **URL** e **anexo**.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-168">Below the graph, there are three tabs: **Email** (default), **URL** , and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="3d5b7-169">Exibir envios de email de administração</span><span class="sxs-lookup"><span data-stu-id="3d5b7-169">View admin email submissions</span></span>

<span data-ttu-id="3d5b7-170">Clique na guia **email** .</span><span class="sxs-lookup"><span data-stu-id="3d5b7-170">Click the **Email** tab.</span></span>

<span data-ttu-id="3d5b7-171">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="3d5b7-171">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3d5b7-172">**Date**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-172">**Date**</span></span>
- <span data-ttu-id="3d5b7-173">**ID de envio** : um valor de GUID que é atribuído a cada envio.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-173">**Submission ID** : A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="3d5b7-174">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d5b7-174">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3d5b7-175">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d5b7-175">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="3d5b7-176">**Sender**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-176">**Sender**</span></span>
- <span data-ttu-id="3d5b7-177">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d5b7-177">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="3d5b7-178">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-178">**Submission type**</span></span>
- <span data-ttu-id="3d5b7-179">**Motivo da entrega**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-179">**Delivery reason**</span></span>
- <span data-ttu-id="3d5b7-180">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d5b7-180">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="3d5b7-181">**Tipo de controle**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-181">**Control type**</span></span>
- <span data-ttu-id="3d5b7-182">**Fonte de controle**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-182">**Control source**</span></span>

  <span data-ttu-id="3d5b7-183"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-183"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="3d5b7-184">Exibir envios de URL de administração</span><span class="sxs-lookup"><span data-stu-id="3d5b7-184">View admin URL submissions</span></span>

<span data-ttu-id="3d5b7-185">Clique na guia **URL** .</span><span class="sxs-lookup"><span data-stu-id="3d5b7-185">Click the **URL** tab.</span></span>

<span data-ttu-id="3d5b7-186">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="3d5b7-186">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3d5b7-187">**Date**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-187">**Date**</span></span>
- <span data-ttu-id="3d5b7-188">**ID de envio**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-188">**Submission ID**</span></span>
- <span data-ttu-id="3d5b7-189">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d5b7-189">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3d5b7-190">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d5b7-190">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="3d5b7-191">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-191">**Submission type**</span></span>
- <span data-ttu-id="3d5b7-192">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d5b7-192">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="3d5b7-193"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-193"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="3d5b7-194">Exibir envios de anexo de administrador</span><span class="sxs-lookup"><span data-stu-id="3d5b7-194">View admin attachment submissions</span></span>

<span data-ttu-id="3d5b7-195">Clique na guia **anexos** .</span><span class="sxs-lookup"><span data-stu-id="3d5b7-195">Click the **Attachments** tab.</span></span>

<span data-ttu-id="3d5b7-196">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="3d5b7-196">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3d5b7-197">**Date**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-197">**Date**</span></span>
- <span data-ttu-id="3d5b7-198">**ID de envio**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-198">**Submission ID**</span></span>
- <span data-ttu-id="3d5b7-199">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d5b7-199">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3d5b7-200">**Nome do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d5b7-200">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="3d5b7-201">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-201">**Submission type**</span></span>
- <span data-ttu-id="3d5b7-202">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d5b7-202">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="3d5b7-203"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-203"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="3d5b7-204">Exibir envios de usuários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d5b7-204">View user submissions to Microsoft</span></span>

<span data-ttu-id="3d5b7-205">Se você tiver implantado o [suplemento de mensagem de relatório](enable-the-report-message-add-in.md)ou se as pessoas usarem [relatórios internos no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), você poderá ver quais usuários estão relatando na guia **envios** de usuários.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-205">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="3d5b7-206">No centro de conformidade & segurança, vá para **Threat management** \> **envios** de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-206">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="3d5b7-207">Selecione a guia envios de **usuário** e clique em **novo envio**.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-207">Select the **User submissions** tab, and then click **New submission**.</span></span>

<span data-ttu-id="3d5b7-208">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="3d5b7-208">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3d5b7-209">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-209">**Submitted on**</span></span>
- <span data-ttu-id="3d5b7-210">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d5b7-210">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3d5b7-211">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d5b7-211">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="3d5b7-212">**Sender**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-212">**Sender**</span></span>
- <span data-ttu-id="3d5b7-213">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d5b7-213">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="3d5b7-214">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-214">**Submission type**</span></span>

<span data-ttu-id="3d5b7-215"><sup>\*</sup> Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-215"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="3d5b7-216">Próximo à parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão), você pode filtrar por **remetente** inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="3d5b7-216">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="3d5b7-217">Update</span><span class="sxs-lookup"><span data-stu-id="3d5b7-217">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="3d5b7-218">Para alterar os critérios de filtro, clique no botão **remetente** e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="3d5b7-218">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="3d5b7-219">**Domínio do remetente**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-219">**Sender domain**</span></span>
- <span data-ttu-id="3d5b7-220">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-220">**Subject**</span></span>
- <span data-ttu-id="3d5b7-221">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-221">**Submitted by**</span></span>
- <span data-ttu-id="3d5b7-222">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-222">**Submission type**</span></span>
- <span data-ttu-id="3d5b7-223">**IP do remetente**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-223">**Sender IP**</span></span>

![Opções de filtro para envios de usuários](../../media/user-submissions-filter-options.png)

<span data-ttu-id="3d5b7-225">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **dados do gráfico** ou **tabela**.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-225">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="3d5b7-226">Na caixa de diálogo exibida, salve o arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-226">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="3d5b7-227">Exibir envios de usuários para a caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="3d5b7-227">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="3d5b7-228">**Se** você [configurou uma caixa de correio personalizada](user-submission.md) para receber mensagens relatadas pelo usuário, você pode exibir e também enviar mensagens que foram entregues à caixa de correio de relatório.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-228">**If** you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="3d5b7-229">No centro de conformidade & segurança, vá para **Threat management** \> **envios** de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-229">In the Security & Compliance Center, go to **Threat management** \> **Submissions**.</span></span>

2. <span data-ttu-id="3d5b7-230">Selecione a guia **caixa de correio personalizada** .</span><span class="sxs-lookup"><span data-stu-id="3d5b7-230">Select the **Custom mailbox** tab.</span></span>

<span data-ttu-id="3d5b7-231">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="3d5b7-231">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3d5b7-232">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-232">**Submitted on**</span></span>
- <span data-ttu-id="3d5b7-233">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d5b7-233">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3d5b7-234">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d5b7-234">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="3d5b7-235">**Sender**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-235">**Sender**</span></span>
- <span data-ttu-id="3d5b7-236">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d5b7-236">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="3d5b7-237">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-237">**Submission type**</span></span>

<span data-ttu-id="3d5b7-238">Próximo à parte superior da página, você pode inserir uma data de início, uma data de término e filtrar por **enviado** , inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="3d5b7-238">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="3d5b7-239">Update</span><span class="sxs-lookup"><span data-stu-id="3d5b7-239">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="3d5b7-240">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **dados do gráfico** ou **tabela**.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-240">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="3d5b7-241">Na caixa de diálogo exibida, salve o arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-241">In the dialog that appears, save the .csv file.</span></span>

## <a name="undo-user-submissions"></a><span data-ttu-id="3d5b7-242">Desfazer envios de usuários</span><span class="sxs-lookup"><span data-stu-id="3d5b7-242">Undo user submissions</span></span>

<span data-ttu-id="3d5b7-243">Quando um usuário envia um email suspeito para a caixa de correio personalizada, o usuário e o administrador não têm uma opção para desfazer o envio.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-243">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="3d5b7-244">Se o usuário quiser recuperar o email, ele estará disponível para recuperação nas pastas itens excluídos ou lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-244">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span> 

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="3d5b7-245">Enviar mensagens para a Microsoft a partir da caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="3d5b7-245">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="3d5b7-246">Se você tiver configurado a caixa de correio personalizada para interceptar mensagens relatadas pelo usuário sem enviar as mensagens à Microsoft, poderá encontrar e enviar mensagens específicas para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-246">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="3d5b7-247">Isso move efetivamente um envio de usuário para um envio de administrador.</span><span class="sxs-lookup"><span data-stu-id="3d5b7-247">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="3d5b7-248">Na guia **caixa de correio personalizada** , selecione uma mensagem na lista, clique no botão de **ação** e faça uma das seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="3d5b7-248">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="3d5b7-249">**Limpeza de relatório**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-249">**Report clean**</span></span>
- <span data-ttu-id="3d5b7-250">**Relatar phishing**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-250">**Report phishing**</span></span>
- <span data-ttu-id="3d5b7-251">**Relatar malware**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-251">**Report malware**</span></span>
- <span data-ttu-id="3d5b7-252">**Relatar spam**</span><span class="sxs-lookup"><span data-stu-id="3d5b7-252">**Report spam**</span></span>

![Opções no botão de ação](../../media/user-submission-custom-mailbox-action-button.png)
