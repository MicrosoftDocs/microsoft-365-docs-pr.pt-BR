---
title: Envios de administrador
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
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a usar o portal de envios no centro de conformidade de & de segurança para enviar emails suspeitos, emails de phishing, spam e outras mensagens, URLs e arquivos potencialmente nocivos para a Microsoft para verificação.
ms.openlocfilehash: 4d0737d881334db9cc4aeda43037ab89d7444618
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577865"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="3d0cb-103">Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d0cb-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="3d0cb-104">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online, os administradores podem usar o portal de envios no centro de conformidade de & de segurança para enviar mensagens de email, URLs e anexos para a Microsoft para verificação.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-104">In Microsoft 365 organizations with mailboxes in Exchange Online, admins can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="3d0cb-105">Ao enviar um email, você receberá informações sobre qualquer política que possa ter permitido o email de entrada em seu locatário, bem como o exame de qualquer URL e anexo no email.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="3d0cb-106">As políticas que podem ter permitido um email incluem a lista de remetentes confiáveis de um usuário individual, bem como políticas de nível de locatário, como regras de fluxo de emails do Exchange (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="3d0cb-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="3d0cb-107">Para obter outras maneiras de enviar mensagens de email, URLs e anexos para a Microsoft, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="3d0cb-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3d0cb-108">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="3d0cb-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3d0cb-109">Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="3d0cb-110">Para ir diretamente para a página de **envio** , use <https://protection.office.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="3d0cb-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="3d0cb-111">Você precisa ter permissões atribuídas antes de poder executar os procedimentos neste tópico:</span><span class="sxs-lookup"><span data-stu-id="3d0cb-111">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="3d0cb-112">Para enviar mensagens e arquivos para a Microsoft, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="3d0cb-112">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="3d0cb-113">**Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3d0cb-113">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="3d0cb-114">**Gerenciamento de organizações** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="3d0cb-114">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="3d0cb-115">Para acesso somente leitura ao portal de envios, você precisa ser membro de um dos grupos de função a seguir:</span><span class="sxs-lookup"><span data-stu-id="3d0cb-115">For read-only access to the Submissions portal, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="3d0cb-116">**Leitor de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="3d0cb-116">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="3d0cb-117">**Gerenciamento da organização Somente visualização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="3d0cb-117">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="3d0cb-118">Para obter mais informações sobre como os usuários podem enviar mensagens e arquivos para a Microsoft, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="3d0cb-118">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="3d0cb-119">Relatar conteúdo suspeito para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d0cb-119">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="3d0cb-120">No centro de conformidade & segurança, vá para análise de **Gerenciamento de ameaça** \> **Review** \> **mensagens de envio de administração**.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-120">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="3d0cb-121">Na página **Submissions** envios que aparece, clique no botão **novo envio** .</span><span class="sxs-lookup"><span data-stu-id="3d0cb-121">On the **Submissions** page that appears, click the **New submission** button.</span></span>

3. <span data-ttu-id="3d0cb-122">Use um novo submenu de **envio** que parece enviar a mensagem, a URL ou o anexo, conforme descrito nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-122">Use **New submission** flyout that appears to submit the message, URL, or attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="3d0cb-123">Enviar um email questionável à Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d0cb-123">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="3d0cb-124">Na seção **tipo de objeto** , selecione **email**.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-124">In the **Object type** section, select **Email**.</span></span> <span data-ttu-id="3d0cb-125">Na seção **formato de envio** , use uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="3d0cb-125">In the **Submission format** section, use one of the following options:</span></span>

   - <span data-ttu-id="3d0cb-126">**ID da mensagem de rede**: Este é um valor de GUID que está disponível no cabeçalho **X-MS-Exchange-Organization-Network-Message-ID** na mensagem.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-126">**Network Message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message.</span></span>

   - <span data-ttu-id="3d0cb-127">**Arquivo**: clique em **escolher arquivo**.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-127">**File**: Click **Choose file**.</span></span> <span data-ttu-id="3d0cb-128">Na caixa de diálogo que é aberta, localize e selecione o arquivo. eml ou. msg e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-128">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

2. <span data-ttu-id="3d0cb-129">Na seção **destinatários** , especifique um ou mais destinatários em relação à qual você gostaria de executar uma verificação de política.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-129">In the **Recipients** section, specify one or more recipients that you would like to run a policy check against.</span></span> <span data-ttu-id="3d0cb-130">A verificação de política determinará se o email ignorará a verificação por causa de políticas de usuário ou organização.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-130">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

3. <span data-ttu-id="3d0cb-131">Na seção **motivo da envio** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="3d0cb-131">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="3d0cb-132">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-132">**Should not have been blocked**</span></span>

   - <span data-ttu-id="3d0cb-133">**Deveriam ter sido bloqueados**: selecione **spam**, **phishing**ou **malware**.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-133">**Should have been blocked**: Select **Spam**, **Phishing**, or **Malware**.</span></span> <span data-ttu-id="3d0cb-134">Se você não tiver certeza, use a melhor avaliação.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-134">If you're not sure, use your best judgment.</span></span>

4. <span data-ttu-id="3d0cb-135">Se o filtro tiver sido ignorado devido às políticas após o envio, você verá informações sobre essa política.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-135">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   <span data-ttu-id="3d0cb-136">Se o filtro não tiver sido ignorado devido a uma ou mais políticas, a verificação será concluída em vários minutos.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-136">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="3d0cb-137">Você verá informações adicionais sobre o envio clicando no link status.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-137">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="3d0cb-138">Isso inclui os resultados da verificação de política e a veredicto de nova verificação.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-138">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="3d0cb-139">Observação isso não executa o email por meio da pilha de filtragem completa do Office 365 ATP novamente, mas executa uma verificação parcial com base em determinados atributos do email, da URL ou do arquivo.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-139">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

5. <span data-ttu-id="3d0cb-140">Quando tiver concluído, clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="3d0cb-140">When you're finished, click the **Submit** button.</span></span>

![Exemplo de envio de URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="3d0cb-142">Enviar uma URL suspeita para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d0cb-142">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="3d0cb-143">Na seção **tipo de objeto** , selecione **URL**.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-143">In the **Object type** section, select **URL**.</span></span> <span data-ttu-id="3d0cb-144">Na caixa exibida, digite a URL completa (por exemplo, <https://www.fabrikam.com/marketing.html> ).</span><span class="sxs-lookup"><span data-stu-id="3d0cb-144">In the box that appears, enter the full URL (for example, <https://www.fabrikam.com/marketing.html>).</span></span>

2. <span data-ttu-id="3d0cb-145">Na seção **motivo da envio** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="3d0cb-145">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="3d0cb-146">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-146">**Should not have been blocked**</span></span>

   - <span data-ttu-id="3d0cb-147">**Deveria ter sido bloqueado**: selecione **phishing** ou **malware**.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-147">**Should have been blocked**: Select **Phishing** or **Malware**.</span></span>

3. <span data-ttu-id="3d0cb-148">Quando tiver concluído, clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="3d0cb-148">When you're finished, click the **Submit** button.</span></span>

![Exemplo de envio de email](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="3d0cb-150">Enviar um arquivo suspeito para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d0cb-150">Submit a suspected file to Microsoft</span></span>

1. <span data-ttu-id="3d0cb-151">Na seção **tipo de objeto** , selecione **anexo**.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-151">In the **Object type** section, select **Attachment**.</span></span>

2. <span data-ttu-id="3d0cb-152">Clique em **escolher arquivo**.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-152">Click **Choose File**.</span></span> <span data-ttu-id="3d0cb-153">Na caixa de diálogo que é aberta, localize e selecione o arquivo e clique em **abrir**.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-153">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="3d0cb-154">Na seção **motivo da envio** , selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="3d0cb-154">In the **Reason for submission** section, select one of the following options:</span></span>

   - <span data-ttu-id="3d0cb-155">**Não deve ter sido bloqueado**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-155">**Should not have been blocked**</span></span>

   - <span data-ttu-id="3d0cb-156">**Deveria ter sido bloqueado**: o **malware** é a única opção e é selecionado automaticamente..</span><span class="sxs-lookup"><span data-stu-id="3d0cb-156">**Should have been blocked**: **Malware** is the only choice, and is automatically selected..</span></span>

4. <span data-ttu-id="3d0cb-157">Quando tiver concluído, clique no botão **Enviar** .</span><span class="sxs-lookup"><span data-stu-id="3d0cb-157">When you're finished, click the **Submit** button.</span></span>

![Exemplo de envio de anexos](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a><span data-ttu-id="3d0cb-159">Exibir envios de administradores</span><span class="sxs-lookup"><span data-stu-id="3d0cb-159">View admin submissions</span></span>

1. <span data-ttu-id="3d0cb-160">No centro de conformidade & segurança, vá para análise de **Gerenciamento de ameaça** \> **Review** \> **mensagens de envio de administração**.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-160">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="3d0cb-161">Na página **envios** que aparece, verifique se a guia **envios de administrador** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-161">On the **Submissions** page that appears, verify that the **Admin submissions** tab is selected.</span></span>

<span data-ttu-id="3d0cb-162">Próximo à parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão), você pode filtrar por **ID de envio** (um valor de GUID que é atribuído a cada envio) inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="3d0cb-162">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Submission ID** (a GUID value that's assigned to every submission) by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="3d0cb-163">Update</span><span class="sxs-lookup"><span data-stu-id="3d0cb-163">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="3d0cb-164">Para alterar os critérios de filtro, clique no botão **ID de envio** e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="3d0cb-164">To change the filter criteria, click the **Submission ID** button and choose one of the following values:</span></span>

- <span data-ttu-id="3d0cb-165">**Sender**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-165">**Sender**</span></span>
- <span data-ttu-id="3d0cb-166">**Assunto/URL/nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-166">**Subject/URL/File name**</span></span>
- <span data-ttu-id="3d0cb-167">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-167">**Submitted by**</span></span>
- <span data-ttu-id="3d0cb-168">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-168">**Submission type**</span></span>
- <span data-ttu-id="3d0cb-169">**Status**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-169">**Status**</span></span>

![Opções de filtro para envios de administradores](../../media/admin-submission-email-filter-options.png)

<span data-ttu-id="3d0cb-171">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **dados do gráfico** ou **tabela**.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-171">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="3d0cb-172">Na caixa de diálogo exibida, salve o arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-172">In the dialog that appears, save the .csv file.</span></span>

<span data-ttu-id="3d0cb-173">Abaixo do gráfico, há três guias: **email** (padrão), **URL**e **anexo**.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-173">Below the graph, there are three tabs: **Email** (default), **URL**, and **Attachment**.</span></span>

### <a name="view-admin-email-submissions"></a><span data-ttu-id="3d0cb-174">Exibir envios de email de administração</span><span class="sxs-lookup"><span data-stu-id="3d0cb-174">View admin email submissions</span></span>

<span data-ttu-id="3d0cb-175">Clique na guia **email** .</span><span class="sxs-lookup"><span data-stu-id="3d0cb-175">Click the **Email** tab.</span></span>

<span data-ttu-id="3d0cb-176">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="3d0cb-176">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3d0cb-177">**Date**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-177">**Date**</span></span>
- <span data-ttu-id="3d0cb-178">**ID de envio**: um valor de GUID que é atribuído a cada envio.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-178">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
- <span data-ttu-id="3d0cb-179">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d0cb-179">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3d0cb-180">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d0cb-180">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="3d0cb-181">**Sender**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-181">**Sender**</span></span>
- <span data-ttu-id="3d0cb-182">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d0cb-182">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="3d0cb-183">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-183">**Submission type**</span></span>
- <span data-ttu-id="3d0cb-184">**Motivo da entrega**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-184">**Delivery reason**</span></span>
- <span data-ttu-id="3d0cb-185">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d0cb-185">**Status**<sup>\*</sup></span></span>
- <span data-ttu-id="3d0cb-186">**Tipo de controle**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-186">**Control type**</span></span>
- <span data-ttu-id="3d0cb-187">**Fonte de controle**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-187">**Control source**</span></span>

  <span data-ttu-id="3d0cb-188"><sup>\*</sup>Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-188"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-url-submissions"></a><span data-ttu-id="3d0cb-189">Exibir envios de URL de administração</span><span class="sxs-lookup"><span data-stu-id="3d0cb-189">View admin URL submissions</span></span>

<span data-ttu-id="3d0cb-190">Clique na guia **URL** .</span><span class="sxs-lookup"><span data-stu-id="3d0cb-190">Click the **URL** tab.</span></span>

<span data-ttu-id="3d0cb-191">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="3d0cb-191">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3d0cb-192">**Date**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-192">**Date**</span></span>
- <span data-ttu-id="3d0cb-193">**ID de envio**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-193">**Submission ID**</span></span>
- <span data-ttu-id="3d0cb-194">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d0cb-194">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3d0cb-195">**URL**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d0cb-195">**URL**<sup>\*</sup></span></span>
- <span data-ttu-id="3d0cb-196">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-196">**Submission type**</span></span>
- <span data-ttu-id="3d0cb-197">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d0cb-197">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="3d0cb-198"><sup>\*</sup>Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-198"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

### <a name="view-admin-attachment-submissions"></a><span data-ttu-id="3d0cb-199">Exibir envios de anexo de administrador</span><span class="sxs-lookup"><span data-stu-id="3d0cb-199">View admin attachment submissions</span></span>

<span data-ttu-id="3d0cb-200">Clique na guia **anexos** .</span><span class="sxs-lookup"><span data-stu-id="3d0cb-200">Click the **Attachments** tab.</span></span>

<span data-ttu-id="3d0cb-201">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="3d0cb-201">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3d0cb-202">**Date**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-202">**Date**</span></span>
- <span data-ttu-id="3d0cb-203">**ID de envio**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-203">**Submission ID**</span></span>
- <span data-ttu-id="3d0cb-204">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d0cb-204">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3d0cb-205">**Nome do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d0cb-205">**File name**<sup>\*</sup></span></span>
- <span data-ttu-id="3d0cb-206">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-206">**Submission type**</span></span>
- <span data-ttu-id="3d0cb-207">**Estado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d0cb-207">**Status**<sup>\*</sup></span></span>

  <span data-ttu-id="3d0cb-208"><sup>\*</sup>Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-208"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="3d0cb-209">Exibir envios de usuários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="3d0cb-209">View user submissions to Microsoft</span></span>

<span data-ttu-id="3d0cb-210">Se você tiver implantado o [suplemento de mensagem de relatório](enable-the-report-message-add-in.md)ou se as pessoas usarem [relatórios internos no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), você poderá ver quais usuários estão relatando na guia **envios** de usuários.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-210">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User submissions** tab.</span></span>

1. <span data-ttu-id="3d0cb-211">No centro de conformidade & segurança, vá para análise de **Gerenciamento de ameaça** \> **Review** \> **mensagens de envio de administração**.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-211">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="3d0cb-212">Na página **envios** que aparece, clique na guia **envios do usuário** .</span><span class="sxs-lookup"><span data-stu-id="3d0cb-212">On the **Submissions** page that appears, click the **User submissions** tab.</span></span>

<span data-ttu-id="3d0cb-213">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="3d0cb-213">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3d0cb-214">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-214">**Submitted on**</span></span>
- <span data-ttu-id="3d0cb-215">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d0cb-215">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3d0cb-216">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d0cb-216">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="3d0cb-217">**Sender**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-217">**Sender**</span></span>
- <span data-ttu-id="3d0cb-218">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d0cb-218">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="3d0cb-219">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-219">**Submission type**</span></span>

<span data-ttu-id="3d0cb-220"><sup>\*</sup>Se você clicar nesse valor, as informações detalhadas serão exibidas em um submenu.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-220"><sup>\*</sup> If you click this value, detailed information is displayed in a flyout.</span></span>

<span data-ttu-id="3d0cb-221">Próximo à parte superior da página, você pode inserir uma data de início, uma data de término e (por padrão), você pode filtrar por **remetente** inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="3d0cb-221">Near the top of the page, you can enter a start date, an end date, and (by default) you can filter by **Sender** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="3d0cb-222">Update</span><span class="sxs-lookup"><span data-stu-id="3d0cb-222">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="3d0cb-223">Para alterar os critérios de filtro, clique no botão **remetente** e escolha um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="3d0cb-223">To change the filter criteria, click the **Sender** button and choose one of the following values:</span></span>

- <span data-ttu-id="3d0cb-224">**Domínio do remetente**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-224">**Sender domain**</span></span>
- <span data-ttu-id="3d0cb-225">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-225">**Subject**</span></span>
- <span data-ttu-id="3d0cb-226">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-226">**Submitted by**</span></span>
- <span data-ttu-id="3d0cb-227">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-227">**Submission type**</span></span>
- <span data-ttu-id="3d0cb-228">**IP do remetente**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-228">**Sender IP**</span></span>

![Opções de filtro para envios de usuários](../../media/user-submissions-filter-options.png)

<span data-ttu-id="3d0cb-230">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **dados do gráfico** ou **tabela**.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-230">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="3d0cb-231">Na caixa de diálogo exibida, salve o arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-231">In the dialog that appears, save the .csv file.</span></span>

## <a name="view-user-submissions-to-the-custom-mailbox"></a><span data-ttu-id="3d0cb-232">Exibir envios de usuários para a caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="3d0cb-232">View user submissions to the custom mailbox</span></span>

<span data-ttu-id="3d0cb-233">Se você [configurou uma caixa de correio personalizada](user-submission.md) para receber mensagens relatadas pelo usuário, você pode exibir e também enviar mensagens que foram entregues à caixa de correio de relatório.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-233">If you've [configured a custom mailbox](user-submission.md) to receive user reported messages, you can view and also submit messages that were delivered to the reporting mailbox.</span></span>

1. <span data-ttu-id="3d0cb-234">No centro de conformidade & segurança, vá para análise de **Gerenciamento de ameaça** \> **Review** \> **mensagens de envio de administração**.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-234">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Admin submission messages**.</span></span>

2. <span data-ttu-id="3d0cb-235">Na página **envios** que aparece, clique na guia **caixa de correio personalizada** .</span><span class="sxs-lookup"><span data-stu-id="3d0cb-235">On the **Submissions** page that appears, click the **Custom mailbox** tab.</span></span>

<span data-ttu-id="3d0cb-236">Você pode clicar no botão **Opções de coluna** próximo à parte inferior da página para adicionar ou remover colunas da exibição:</span><span class="sxs-lookup"><span data-stu-id="3d0cb-236">You can click the **Column options** button near the bottom of the page to add or remove columns from the view:</span></span>

- <span data-ttu-id="3d0cb-237">**Enviado em**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-237">**Submitted on**</span></span>
- <span data-ttu-id="3d0cb-238">**Enviado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d0cb-238">**Submitted by**<sup>\*</sup></span></span>
- <span data-ttu-id="3d0cb-239">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d0cb-239">**Subject**<sup>\*</sup></span></span>
- <span data-ttu-id="3d0cb-240">**Sender**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-240">**Sender**</span></span>
- <span data-ttu-id="3d0cb-241">**IP do remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="3d0cb-241">**Sender IP**<sup>\*</sup></span></span>
- <span data-ttu-id="3d0cb-242">**Tipo de envio**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-242">**Submission type**</span></span>

<span data-ttu-id="3d0cb-243">Próximo à parte superior da página, você pode inserir uma data de início, uma data de término e filtrar por **enviado** , inserindo um valor na caixa e clicando em ![ Atualizar botão ](../../media/scc-quarantine-refresh.png) .</span><span class="sxs-lookup"><span data-stu-id="3d0cb-243">Near the top of the page, you can enter a start date, an end date, and you can filter by **Submitted by** by entering a value in the box and clicking ![Refresh button](../../media/scc-quarantine-refresh.png).</span></span> <span data-ttu-id="3d0cb-244">Update</span><span class="sxs-lookup"><span data-stu-id="3d0cb-244">You can enter multiple values separated by commas.</span></span>

<span data-ttu-id="3d0cb-245">Para exportar os resultados, clique em **Exportar** próximo à parte superior da página e selecione **dados do gráfico** ou **tabela**.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-245">To export the results, click **Export** near the top of the page and select **Chart data** or **Table**.</span></span> <span data-ttu-id="3d0cb-246">Na caixa de diálogo exibida, salve o arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-246">In the dialog that appears, save the .csv file.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="3d0cb-247">Enviar mensagens para a Microsoft a partir da caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="3d0cb-247">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="3d0cb-248">Se você tiver configurado a caixa de correio personalizada para interceptar mensagens relatadas pelo usuário sem enviar as mensagens à Microsoft, poderá encontrar e enviar mensagens específicas para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-248">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="3d0cb-249">Isso move efetivamente um envio de usuário para um envio de administrador.</span><span class="sxs-lookup"><span data-stu-id="3d0cb-249">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="3d0cb-250">Na guia **caixa de correio personalizada** , selecione uma mensagem na lista, clique no botão de **ação** e faça uma das seguintes seleções:</span><span class="sxs-lookup"><span data-stu-id="3d0cb-250">On the **Custom mailbox** tab, select a message in the list, click the **Action** button, and make one of the following selections:</span></span>

- <span data-ttu-id="3d0cb-251">**Limpeza de relatório**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-251">**Report clean**</span></span>
- <span data-ttu-id="3d0cb-252">**Relatar phishing**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-252">**Report phishing**</span></span>
- <span data-ttu-id="3d0cb-253">**Relatar malware**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-253">**Report malware**</span></span>
- <span data-ttu-id="3d0cb-254">**Relatar spam**</span><span class="sxs-lookup"><span data-stu-id="3d0cb-254">**Report spam**</span></span>

![Opções no botão de ação](../../media/user-submission-custom-mailbox-action-button.png)
