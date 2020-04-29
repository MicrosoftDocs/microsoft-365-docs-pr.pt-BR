---
title: Envios de administradores, envios, problemas de spam, falso negativo, enviar phishing, enviar email para verificação, email suspeito no Office 365, examinar um email, fazer com que a Microsoft examine o phishing, peça à Microsoft para spam, enviar emails, enviar emails, emails do dodgy, email de ator ruim, email suspeito e não confiável, relatar emails de Phish para a Microsoft, relatar emails de phishing para a Microsoft , relatar malware em email para a Microsoft, email de spam na caixa de entrada, vírus em email
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
description: Saiba como enviar emails suspeitos, emails de phishing, spam e outras mensagens, URLs e arquivos potencialmente nocivos da sua empresa para a Microsoft para verificação.
ms.openlocfilehash: 73c33ba1218a710c33f8b2675bc65c0a7486efda
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2020
ms.locfileid: "43921487"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="204f8-103">Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft</span><span class="sxs-lookup"><span data-stu-id="204f8-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="204f8-104">Se você for um administrador em uma organização do Microsoft 365 com caixas de correio no Exchange Online, você pode usar o portal de envios no centro de conformidade de & de segurança para enviar mensagens de email, URLs e anexos para a Microsoft para verificação.</span><span class="sxs-lookup"><span data-stu-id="204f8-104">If you're an admin in a Microsoft 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="204f8-105">Ao enviar um email, você receberá informações sobre qualquer política que possa ter permitido o email de entrada em seu locatário, bem como o exame de qualquer URL e anexo no email.</span><span class="sxs-lookup"><span data-stu-id="204f8-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="204f8-106">As políticas que podem ter permitido um email incluem a lista de remetentes confiáveis de um usuário individual, bem como políticas de nível de locatário, como regras de fluxo de emails do Exchange (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="204f8-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="204f8-107">Para obter outras maneiras de enviar mensagens de email, URLs e anexos para a Microsoft, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="204f8-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="204f8-108">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="204f8-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="204f8-109">Você abrir o Centro de conformidade e segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="204f8-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="204f8-110">Para ir diretamente para a página de **envio** , <https://protection.office.com/reportsubmission>use.</span><span class="sxs-lookup"><span data-stu-id="204f8-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="204f8-111">Você precisa receber permissões para executar esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="204f8-111">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="204f8-112">Para adicionar, modificar e excluir políticas antispam, você precisa ser membro dos grupos de função de gerenciamento da **organização**, **administrador de segurança**ou **leitor de segurança** .</span><span class="sxs-lookup"><span data-stu-id="204f8-112">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="204f8-113">Para obter mais informações sobre grupos de funções no Centro de Conformidade e Segurança, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="204f8-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="204f8-114">Para obter mais informações sobre como os usuários podem enviar mensagens e arquivos para a Microsoft, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="204f8-114">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="204f8-115">Relatar conteúdo suspeito para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="204f8-115">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="204f8-116">No centro de conformidade & segurança, vá para **Threat management** \> **análise** \> de gerenciamento de ameaça **mensagens de envio de administração**.</span><span class="sxs-lookup"><span data-stu-id="204f8-116">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="204f8-117">Na página **Submissions** envios que aparece, clique no botão **novo envio** .</span><span class="sxs-lookup"><span data-stu-id="204f8-117">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="204f8-118">Use um novo submenu de **envio** que parece enviar a mensagem, a URL ou o anexo, conforme descrito nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="204f8-118">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="204f8-119">Enviar um email questionável à Microsoft</span><span class="sxs-lookup"><span data-stu-id="204f8-119">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="204f8-120">Na seção **tipo de objeto** , selecione **email**.</span><span class="sxs-lookup"><span data-stu-id="204f8-120">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="204f8-121">Na seção **formato de envio** , use uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="204f8-121">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="204f8-122">**ID da mensagem de rede**: Este é um valor de GUID que está disponível no cabeçalho **X-MS-Exchange-Organization-Network-Message-ID** na mensagem.</span><span class="sxs-lookup"><span data-stu-id="204f8-122">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="204f8-123">**Arquivo**: clique em **escolher arquivo**.</span><span class="sxs-lookup"><span data-stu-id="204f8-123">**File**: Click **Choose file**.</span></span> <span data-ttu-id="204f8-124">Na caixa de diálogo que é aberta, localize e selecione o arquivo. eml ou. msg e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="204f8-124">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="204f8-125">Na seção **destinatários** , especifique um ou mais destinatários em relação à qual você gostaria de executar uma verificação de política.</span><span class="sxs-lookup"><span data-stu-id="204f8-125">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="204f8-126">A verificação de política determinará se o email ignorará a verificação por causa de políticas de usuário ou organização.</span><span class="sxs-lookup"><span data-stu-id="204f8-126">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="204f8-127">Na seção **motivo da envio** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="204f8-127">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="204f8-128">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="204f8-128">**Should not have been blocked**</span></span>

   - <span data-ttu-id="204f8-129">**Deveriam ter sido bloqueados**: selecione **spam**, **phishing**ou **malware**.</span><span class="sxs-lookup"><span data-stu-id="204f8-129">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="204f8-130">Se você não tiver certeza, use a melhor avaliação.</span><span class="sxs-lookup"><span data-stu-id="204f8-130">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="204f8-131">Se o filtro tiver sido ignorado devido às políticas após o envio, você verá informações sobre essa política.</span><span class="sxs-lookup"><span data-stu-id="204f8-131">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="204f8-132">Se o filtro não tiver sido ignorado devido a uma ou mais políticas, a verificação será concluída em vários minutos.</span><span class="sxs-lookup"><span data-stu-id="204f8-132">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="204f8-133">Você verá informações adicionais sobre o envio clicando no link status.</span><span class="sxs-lookup"><span data-stu-id="204f8-133">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="204f8-134">Isso inclui os resultados da verificação de política e a veredicto de nova verificação.</span><span class="sxs-lookup"><span data-stu-id="204f8-134">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="204f8-135">Observação isso não executa o email por meio da pilha de filtragem completa do Office 365 ATP novamente, mas executa uma verificação parcial com base em determinados atributos do email, da URL ou do arquivo.</span><span class="sxs-lookup"><span data-stu-id="204f8-135">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="204f8-136">Quando tiver concluído, clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="204f8-136">When you're finished, click the **Submit** button.</span></span>

![Exemplo de envio de URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="204f8-138">Enviar uma URL suspeita para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="204f8-138">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="204f8-139">Na seção **tipo de objeto** , selecione **URL**.</span><span class="sxs-lookup"><span data-stu-id="204f8-139">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="204f8-140">Na caixa exibida, digite a URL completa (por exemplo, <https://www.fabrikam.com/marketing.html>).</span><span class="sxs-lookup"><span data-stu-id="204f8-140">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="204f8-141">Na seção **motivo da envio** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="204f8-141">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="204f8-142">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="204f8-142">**Should not have been blocked**</span></span>

   - <span data-ttu-id="204f8-143">**Deveria ter sido bloqueado**: selecione **phishing** ou **malware**.</span><span class="sxs-lookup"><span data-stu-id="204f8-143">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="204f8-144">Quando tiver concluído, clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="204f8-144">When you're finished, click the **Submit** button.</span></span>

![Exemplo de envio de email](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="204f8-146">Enviar um arquivo suspeito para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="204f8-146">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="204f8-147">Na seção **tipo de objeto** , selecione **anexo**.</span><span class="sxs-lookup"><span data-stu-id="204f8-147">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="204f8-148">Clique em **escolher arquivo**.</span><span class="sxs-lookup"><span data-stu-id="204f8-148">Click **Choose File**.</span></span> <span data-ttu-id="204f8-149">Na caixa de diálogo que é aberta, localize e selecione o arquivo e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="204f8-149">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="204f8-150">Na seção **motivo da envio** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="204f8-150">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="204f8-151">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="204f8-151">**Should not have been blocked**</span></span>

   - <span data-ttu-id="204f8-152">**Deveria ter sido bloqueado**: o **malware** é a única opção e é selecionado automaticamente..</span><span class="sxs-lookup"><span data-stu-id="204f8-152">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="204f8-153">Quando tiver concluído, clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="204f8-153">When you're finished, click the **Submit** button.</span></span>

![Exemplo de envio de anexos](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="204f8-155">Exibir envios de administradores</span><span class="sxs-lookup"><span data-stu-id="204f8-155">View admin submissions</span></span>

1. <span data-ttu-id="204f8-156">No centro de conformidade & segurança, vá para **Threat management** \> **análise** \> de gerenciamento de ameaça **mensagens de envio de administração**.</span><span class="sxs-lookup"><span data-stu-id="204f8-156">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="204f8-157">Na página **envios** que aparece, verifique se a guia **envios de administrador** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="204f8-157">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="204f8-158">Próximo à parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão), você pode filtrar por **ID de envio** , inserindo um valor na ![caixa e](../../media/scc-quarantine-refresh.png)clicando em Atualizar botão.</span><span class="sxs-lookup"><span data-stu-id="204f8-158">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="204f8-159">Update</span><span class="sxs-lookup"><span data-stu-id="204f8-159">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="204f8-160">Para alterar os critérios de filtro, clique no botão **ID de envio** e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="204f8-160">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="204f8-161">**Sender**</span><span class="sxs-lookup"><span data-stu-id="204f8-161">**Sender**</span></span>
- <span data-ttu-id="204f8-162">**Assunto/URL/nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="204f8-162">**Subject/URL/File name**</span></span>
- <span data-ttu-id="204f8-163">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="204f8-163">**Submitted by**</span></span>
- <span data-ttu-id="204f8-164">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="204f8-164">**Submission type**</span></span>
- <span data-ttu-id="204f8-165">**Status**</span><span class="sxs-lookup"><span data-stu-id="204f8-165">**Status**</span></span>

![Opções de filtro para envios de administradores](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="204f8-167">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **dados do gráfico** ou **tabela**.</span><span class="sxs-lookup"><span data-stu-id="204f8-167">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="204f8-168">Na caixa de diálogo exibida, salve o arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="204f8-168">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="204f8-169">Abaixo do gráfico, há três guias: **email** (padrão), **URL**e **anexo**.</span><span class="sxs-lookup"><span data-stu-id="204f8-169">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="204f8-170">Exibir envios de email de administração</span><span class="sxs-lookup"><span data-stu-id="204f8-170">View admin email submissions</span></span>

<span data-ttu-id="204f8-171">Clique na guia **email** .</span><span class="sxs-lookup"><span data-stu-id="204f8-171">Click the **Email** tab.</span></span>

<span data-ttu-id="204f8-172">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="204f8-172">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="204f8-173">**Date**</span><span class="sxs-lookup"><span data-stu-id="204f8-173">**Date**</span></span>
- <span data-ttu-id="204f8-174">**ID de envio**</span><span class="sxs-lookup"><span data-stu-id="204f8-174">**Submission ID**</span></span>
- <span data-ttu-id="204f8-175">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="204f8-175">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="204f8-176">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="204f8-176">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="204f8-177">**Sender**</span><span class="sxs-lookup"><span data-stu-id="204f8-177">**Sender**</span></span>
- <span data-ttu-id="204f8-178">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="204f8-178">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="204f8-179">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="204f8-179">**Submission type**</span></span>
- <span data-ttu-id="204f8-180">**Motivo da entrega**</span><span class="sxs-lookup"><span data-stu-id="204f8-180">**Delivery reason**</span></span>
- <span data-ttu-id="204f8-181">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="204f8-181">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="204f8-182">**Tipo de controle**</span><span class="sxs-lookup"><span data-stu-id="204f8-182">**Control type**</span></span>
- <span data-ttu-id="204f8-183">**Fonte de controle**</span><span class="sxs-lookup"><span data-stu-id="204f8-183">**Control source**</span></span>

  <span data-ttu-id="204f8-184"><sup>\*</sup>Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="204f8-184"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="204f8-185">Exibir envios de URL de administração</span><span class="sxs-lookup"><span data-stu-id="204f8-185">View admin URL submissions</span></span>

<span data-ttu-id="204f8-186">Clique na guia **URL** .</span><span class="sxs-lookup"><span data-stu-id="204f8-186">Click the **URL** tab.</span></span>

<span data-ttu-id="204f8-187">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="204f8-187">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="204f8-188">**Date**</span><span class="sxs-lookup"><span data-stu-id="204f8-188">**Date**</span></span>
- <span data-ttu-id="204f8-189">**ID de envio**</span><span class="sxs-lookup"><span data-stu-id="204f8-189">**Submission ID**</span></span>
- <span data-ttu-id="204f8-190">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="204f8-190">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="204f8-191">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="204f8-191">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="204f8-192">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="204f8-192">**Submission type**</span></span>
- <span data-ttu-id="204f8-193">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="204f8-193">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="204f8-194"><sup>\*</sup>Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="204f8-194"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="204f8-195">Exibir envios de anexo de administrador</span><span class="sxs-lookup"><span data-stu-id="204f8-195">View admin attachment submissions</span></span>

<span data-ttu-id="204f8-196">Clique na guia **anexos** .</span><span class="sxs-lookup"><span data-stu-id="204f8-196">Click the **Attachments** tab.</span></span>

<span data-ttu-id="204f8-197">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="204f8-197">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="204f8-198">**Date**</span><span class="sxs-lookup"><span data-stu-id="204f8-198">**Date**</span></span>
- <span data-ttu-id="204f8-199">**ID de envio**</span><span class="sxs-lookup"><span data-stu-id="204f8-199">**Submission ID**</span></span>
- <span data-ttu-id="204f8-200">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="204f8-200">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="204f8-201">**Nome do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="204f8-201">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="204f8-202">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="204f8-202">**Submission type**</span></span>
- <span data-ttu-id="204f8-203">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="204f8-203">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="204f8-204"><sup>\*</sup>Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="204f8-204"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="204f8-205">Exibir envios de usuários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="204f8-205">View user submissions to Microsoft</span></span>

<span data-ttu-id="204f8-206">Se você tiver implantado o [suplemento de mensagem de relatório](enable-the-report-message-add-in.md)ou se as pessoas usarem [relatórios internos no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), você poderá ver quais usuários estão relatando na guia **envios** de usuários.</span><span class="sxs-lookup"><span data-stu-id="204f8-206">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="204f8-207">No centro de conformidade & segurança, vá para **Threat management** \> **análise** \> de gerenciamento de ameaça **mensagens de envio de administração**.</span><span class="sxs-lookup"><span data-stu-id="204f8-207">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="204f8-208">Na página **envios** que aparece, clique na guia **envios do usuário** .</span><span class="sxs-lookup"><span data-stu-id="204f8-208">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="204f8-209">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="204f8-209">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="204f8-210">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="204f8-210">**Submitted on**</span></span>
- <span data-ttu-id="204f8-211">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="204f8-211">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="204f8-212">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="204f8-212">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="204f8-213">**Sender**</span><span class="sxs-lookup"><span data-stu-id="204f8-213">**Sender**</span></span>
- <span data-ttu-id="204f8-214">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="204f8-214">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="204f8-215">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="204f8-215">**Submission type**</span></span>

<span data-ttu-id="204f8-216"><sup>\*</sup>Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="204f8-216"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="204f8-217">Próximo à parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão), você pode filtrar por **remetente** inserindo um valor na caixa e ![clicando em](../../media/scc-quarantine-refresh.png)Atualizar botão.</span><span class="sxs-lookup"><span data-stu-id="204f8-217">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="204f8-218">Update</span><span class="sxs-lookup"><span data-stu-id="204f8-218">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="204f8-219">Para alterar os critérios de filtro, clique no botão **remetente** e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="204f8-219">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="204f8-220">**Domínio do remetente**</span><span class="sxs-lookup"><span data-stu-id="204f8-220">**Sender domain**</span></span>
- <span data-ttu-id="204f8-221">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="204f8-221">**Subject**</span></span>
- <span data-ttu-id="204f8-222">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="204f8-222">**Submitted by**</span></span>
- <span data-ttu-id="204f8-223">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="204f8-223">**Submission type**</span></span>
- <span data-ttu-id="204f8-224">**IP do remetente**</span><span class="sxs-lookup"><span data-stu-id="204f8-224">**Sender IP**</span></span>

![Opções de filtro para envios de usuários](../../media/user-submissions-filter-options.png)

<span data-ttu-id="204f8-226">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **dados do gráfico** ou **tabela**.</span><span class="sxs-lookup"><span data-stu-id="204f8-226">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="204f8-227">Na caixa de diálogo exibida, salve o arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="204f8-227">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="204f8-228">Exibir envios de usuários para a caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="204f8-228">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="204f8-229">Se você [configurou uma caixa de correio personalizada](user-submission.md) para receber mensagens relatadas pelo usuário, você pode exibir e também enviar mensagens que foram entregues à caixa de correio de relatório.</span><span class="sxs-lookup"><span data-stu-id="204f8-229">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="204f8-230">No centro de conformidade & segurança, vá para **Threat management** \> **análise** \> de gerenciamento de ameaça **mensagens de envio de administração**.</span><span class="sxs-lookup"><span data-stu-id="204f8-230">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="204f8-231">Na página **envios** que aparece, clique na guia **caixa de correio personalizada** .</span><span class="sxs-lookup"><span data-stu-id="204f8-231">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="204f8-232">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="204f8-232">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="204f8-233">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="204f8-233">**Submitted on**</span></span>
- <span data-ttu-id="204f8-234">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="204f8-234">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="204f8-235">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="204f8-235">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="204f8-236">**Sender**</span><span class="sxs-lookup"><span data-stu-id="204f8-236">**Sender**</span></span>
- <span data-ttu-id="204f8-237">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="204f8-237">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="204f8-238">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="204f8-238">**Submission type**</span></span>

<span data-ttu-id="204f8-239">Próximo à parte superior da página, você pode inserir uma data de início, uma data de término e filtrar por **enviado** , inserindo um valor na caixa e clicando em ![Atualizar botão.](../../media/scc-quarantine-refresh.png)</span><span class="sxs-lookup"><span data-stu-id="204f8-239">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="204f8-240">Update</span><span class="sxs-lookup"><span data-stu-id="204f8-240">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="204f8-241">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **dados do gráfico** ou **tabela**.</span><span class="sxs-lookup"><span data-stu-id="204f8-241">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="204f8-242">Na caixa de diálogo exibida, salve o arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="204f8-242">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="204f8-243">Enviar mensagens para a Microsoft a partir da caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="204f8-243">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="204f8-244">Se você tiver configurado a caixa de correio personalizada para interceptar mensagens relatadas pelo usuário sem enviar as mensagens à Microsoft, poderá encontrar e enviar mensagens específicas para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="204f8-244">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="204f8-245">Isso move efetivamente um envio de usuário para um envio de administrador.</span><span class="sxs-lookup"><span data-stu-id="204f8-245">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="204f8-246">Na guia **caixa de correio personalizada** , selecione uma mensagem na lista, clique no botão de **ação** e faça uma das seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="204f8-246">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="204f8-247">**Limpeza de relatório**</span><span class="sxs-lookup"><span data-stu-id="204f8-247">**Report clean**</span></span>
- <span data-ttu-id="204f8-248">**Relatar phishing**</span><span class="sxs-lookup"><span data-stu-id="204f8-248">**Report phishing**</span></span>
- <span data-ttu-id="204f8-249">**Relatar malware**</span><span class="sxs-lookup"><span data-stu-id="204f8-249">**Report malware**</span></span>
- <span data-ttu-id="204f8-250">**Relatar spam**</span><span class="sxs-lookup"><span data-stu-id="204f8-250">**Report spam**</span></span>

![Opções no botão de ação](../../media/user-submission-custom-mailbox-action-button.png)
