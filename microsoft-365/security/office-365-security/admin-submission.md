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
description: Os administradores podem aprender a usar o portal Envios no portal Microsoft 365 Defender para enviar emails suspeitos, emails suspeitos de phishing, spam e outras mensagens potencialmente prejudiciais, URLs e anexos de email para a Microsoft para análise de novo.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab25757c79b7978400e98fa36d48163e1681e7c1
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53061984"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="a4e5c-103">Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft</span><span class="sxs-lookup"><span data-stu-id="a4e5c-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a4e5c-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-104">**Applies to**</span></span>
- [<span data-ttu-id="a4e5c-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a4e5c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a4e5c-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a4e5c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)


<span data-ttu-id="a4e5c-107">Em Microsoft 365 organizações com caixas de correio Exchange Online, os administradores podem usar o portal Envios no portal Microsoft 365 Defender para enviar mensagens de email, URLs e anexos à Microsoft para verificação.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-107">In Microsoft 365 organizations with Exchange Online mailboxes, admins can use the Submissions portal in the Microsoft 365 Defender portal to submit email messages, URLs, and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="a4e5c-108">Ao enviar uma mensagem de email, você receberá:</span><span class="sxs-lookup"><span data-stu-id="a4e5c-108">When you submit an email message, you will get:</span></span>

- <span data-ttu-id="a4e5c-109">**Verificação de autenticação de** email : Detalhes sobre se a autenticação de email passou ou falhou quando ela foi entregue.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-109">**Email authentication check**: Details on whether email authentication passed or failed when it was delivered.</span></span>
- <span data-ttu-id="a4e5c-110">**Visitas de política**: informações sobre quaisquer políticas que possam ter permitido ou bloqueado o email de entrada em seu locatário, substituindo nossos vereditos de filtro de serviço.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-110">**Policy hits**: Information about any policies that may have allowed or blocked the incoming email into your tenant, overriding our service filter verdicts.</span></span>
- <span data-ttu-id="a4e5c-111">**Reputação/detonação** de carga : Exame de quaisquer URLs e anexos na mensagem.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-111">**Payload reputation/detonation**: Examination of any URLs and attachments in the message.</span></span>
- <span data-ttu-id="a4e5c-112">**Análise de notas**: Revisão feita por alunos de nível humano para confirmar se as mensagens são mal-intencionadas ou não.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-112">**Grader analysis**: Review done by human graders in order to confirm whether or not messages are malicious.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4e5c-113">A análise de reputação/detonação e classificação de carga não é feita em todos os locatários.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-113">Payload reputation/detonation and grader analysis are not done in all tenants.</span></span> <span data-ttu-id="a4e5c-114">As informações são impedidas de sair da organização quando os dados não devem sair do limite do locatário para fins de conformidade.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-114">Information is blocked from going outside the organization when data is not supposed to leave the tenant boundary for compliance purposes.</span></span>

<span data-ttu-id="a4e5c-115">Para outras maneiras de enviar mensagens de email, URLs e anexos à Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="a4e5c-115">For other ways to submit email messages, URLs, and attachments to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a4e5c-116">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="a4e5c-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a4e5c-117">Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com/>.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-117">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="a4e5c-118">Para ir diretamente para a página **Envios,** use <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="a4e5c-118">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="a4e5c-119">Para enviar mensagens e arquivos para a Microsoft, você precisa ser membro de um dos seguintes grupos de função:</span><span class="sxs-lookup"><span data-stu-id="a4e5c-119">To submit messages and files to Microsoft, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="a4e5c-120">**Gerenciamento da** organização **ou leitor de** segurança no portal Microsoft 365 Defender [.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="a4e5c-120">**Organization Management** or **Security Reader** in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="a4e5c-121">**Gerenciamento de organização** em [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="a4e5c-121">**Organization Management** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

    <span data-ttu-id="a4e5c-122">Observe que a associação neste grupo de funções é necessária para Exibir [envios](#view-user-submissions-to-microsoft) de usuário para a caixa de correio personalizada conforme descrito posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-122">Note that membership in this role group is required to [View user submissions to the custom mailbox](#view-user-submissions-to-microsoft) as described later in this article.</span></span>

- <span data-ttu-id="a4e5c-123">Para obter mais informações sobre como os usuários podem enviar mensagens e arquivos para a Microsoft, consulte [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="a4e5c-123">For more information about how users can submit messages and files to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="report-suspicious-content-to-microsoft"></a><span data-ttu-id="a4e5c-124">Relatar conteúdo suspeito à Microsoft</span><span class="sxs-lookup"><span data-stu-id="a4e5c-124">Report suspicious content to Microsoft</span></span>

1. <span data-ttu-id="a4e5c-125">No portal Microsoft 365 Defender, acesse **Email & envios de** \> **colaboração.**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-125">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="a4e5c-126">Na página **Envios,** verifique se a guia **Enviado** para análise está selecionada e clique em Ícone de ad Enviar para ![ a Microsoft para ](../../media/m365-cc-sc-create-icon.png) **análise**.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-126">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected, and then click ![Ad icon](../../media/m365-cc-sc-create-icon.png) **Submit to Microsoft for analysis**.</span></span>

3. <span data-ttu-id="a4e5c-127">Use o sub-sub-texto Enviar para **a Microsoft** para revisão que parece enviar a mensagem, a URL ou o anexo de email, conforme descrito nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-127">Use the **Submit to Microsoft for review** flyout that appears to submit the message, URL, or email attachment as described in the following sections.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="a4e5c-128">Enviar um email questionável à Microsoft</span><span class="sxs-lookup"><span data-stu-id="a4e5c-128">Submit a questionable email to Microsoft</span></span>

1. <span data-ttu-id="a4e5c-129">Na caixa **Selecionar o tipo de** envio, verifique se **Email** está selecionado na lista lista listada.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-129">In the **Select the submission type** box, verify that **Email** is selected in the drop down list.</span></span>

2. <span data-ttu-id="a4e5c-130">Na seção **Adicionar a ID da** mensagem de rede ou carregar o arquivo de email, use uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="a4e5c-130">In the **Add the network message ID or upload the email file** section, use one of the following options:</span></span>
   - <span data-ttu-id="a4e5c-131">Adicionar a **ID** da mensagem de rede de email : Este é um valor GUID que está disponível no header **X-MS-Exchange-Organization-Network-Message-Id** na mensagem ou no **header X-MS-Office365-Filtering-Correlation-Id** em mensagens em quarentena.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-131">**Add the email network message ID**: This is a GUID value that's available in the **X-MS-Exchange-Organization-Network-Message-Id** header in the message or in the **X-MS-Office365-Filtering-Correlation-Id** header in quarantined messages.</span></span>
   - <span data-ttu-id="a4e5c-132">**Upload arquivo de email (.msg ou .eml)**: Clique em **Procurar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-132">**Upload the email file (.msg or .eml)**: Click **Browse files**.</span></span> <span data-ttu-id="a4e5c-133">Na caixa de diálogo que é aberta, encontre e selecione o arquivo .eml ou .msg e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-133">In the dialog that opens, find and select the .eml or .msg file, and then click **Open**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a4e5c-134">A capacidade de enviar mensagens com até 30 dias foi temporariamente suspensa para o Defender Office 365 clientes.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-134">The ability to submit messages as old as 30 days has been temporarily suspended for Defender for Office 365 customers.</span></span> <span data-ttu-id="a4e5c-135">Os administradores só poderão voltar 7 dias.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-135">Admins will only be able to go back 7 days.</span></span>

3. <span data-ttu-id="a4e5c-136">Na caixa **Escolher um destinatário que tinha um** problema, especifique o destinatário com o qual você gostaria de executar uma verificação de política.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-136">In the **Choose a recipient who had an issue** box, specify the recipient that you would like to run a policy check against.</span></span> <span data-ttu-id="a4e5c-137">A verificação de política determinará se o email foi ignorado devido a políticas de usuário ou organização.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-137">The policy check will determine if the email bypassed scanning due to user or organization policies.</span></span>

4. <span data-ttu-id="a4e5c-138">Na seção **Selecionar um motivo para enviar à Microsoft,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="a4e5c-138">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="a4e5c-139">**Não deve ter sido bloqueado (falso positivo)**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-139">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="a4e5c-140">**Deve ter sido** bloqueado : Na seção O email deve ter sido **categorizado** como exibido, selecione um dos seguintes valores (se você não tiver certeza, use seu melhor julgamento):</span><span class="sxs-lookup"><span data-stu-id="a4e5c-140">**Should have been blocked**: In the **The email should have been categorized as** section that appears, select one of the following values (if you're not sure, use your best judgement):</span></span>
     - <span data-ttu-id="a4e5c-141">**Golpe**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-141">**Phish**</span></span>
     - <span data-ttu-id="a4e5c-142">**Spam**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-142">**Spam**</span></span>
     - <span data-ttu-id="a4e5c-143">**Malware**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-143">**Malware**</span></span>

5. <span data-ttu-id="a4e5c-144">Quando terminar, clique no **botão Enviar.**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-144">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a4e5c-145">![Novo exemplo de envio de URL](../../media/submission-flyout-email.png)</span><span class="sxs-lookup"><span data-stu-id="a4e5c-145">![New URL submission example](../../media/submission-flyout-email.png)</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="a4e5c-146">Enviar uma URL suspeita para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="a4e5c-146">Send a suspect URL to Microsoft</span></span>

1. <span data-ttu-id="a4e5c-147">Na caixa **Selecionar o tipo de** envio, selecione **URL** na lista lista listada.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-147">In the **Select the submission type** box, select **URL** from the drop down list.</span></span>

2. <span data-ttu-id="a4e5c-148">Na caixa **URL** exibida, insira a URL completa (por exemplo, `https://www.fabrikam.com/marketing.html` ).</span><span class="sxs-lookup"><span data-stu-id="a4e5c-148">In the **URL** box that appears, enter the full URL (for example, `https://www.fabrikam.com/marketing.html`).</span></span>

3. <span data-ttu-id="a4e5c-149">Na seção **Selecionar um motivo para enviar à Microsoft,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="a4e5c-149">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="a4e5c-150">**Não deve ter sido bloqueado (falso positivo)**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-150">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="a4e5c-151">**Deve ter sido bloqueado**: Na seção Essa URL deve ter sido **categorizada** como exibida, selecione **Phish** ou **Malware**.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-151">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, select **Phish** or **Malware**.</span></span>

4. <span data-ttu-id="a4e5c-152">Quando terminar, clique no **botão Enviar.**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-152">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a4e5c-153">![Novo exemplo de envio de email](../../media/submission-url-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="a4e5c-153">![New Email submission example](../../media/submission-url-flyout.png)</span></span>

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a><span data-ttu-id="a4e5c-154">Enviar um anexo de email suspeito à Microsoft</span><span class="sxs-lookup"><span data-stu-id="a4e5c-154">Submit a suspected email attachment to Microsoft</span></span>

1. <span data-ttu-id="a4e5c-155">Na caixa **Selecionar o tipo de** envio, selecione **Arquivo** na lista lista listada.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-155">In the **Select the submission type** box, select **File** from the drop down list.</span></span>

2. <span data-ttu-id="a4e5c-156">Na seção **Arquivo** que aparece, clique em **Procurar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-156">In the **File** section that appears, click **Browse files**.</span></span> <span data-ttu-id="a4e5c-157">Na caixa de diálogo que é aberta, encontre e selecione o arquivo e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-157">In the dialog that opens, find and select the file, and then click **Open**.</span></span>

3. <span data-ttu-id="a4e5c-158">Na seção **Selecionar um motivo para enviar à Microsoft,** selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="a4e5c-158">In the **Select a reason for submitting to Microsoft** section, select one of the following options:</span></span>
   - <span data-ttu-id="a4e5c-159">**Não deve ter sido bloqueado (falso positivo)**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-159">**Should not have been blocked (false positive)**</span></span>
   - <span data-ttu-id="a4e5c-160">**Deve ter sido bloqueado**: Na seção Essa URL deve ter sido **categorizada** como exibida, **Malware** é a única opção e é selecionado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-160">**Should have been blocked**: In the **This URL should have been categorized as** section that appears, **Malware** is the only choice, and is automatically selected.</span></span>

4. <span data-ttu-id="a4e5c-161">Quando terminar, clique no **botão Enviar.**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-161">When you're finished, click the **Submit** button.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a4e5c-162">![Novo exemplo de envio de anexo](../../media/submission-file-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="a4e5c-162">![New Attachment submission example](../../media/submission-file-flyout.png)</span></span>

## <a name="view-admin-submissions-to-microsoft"></a><span data-ttu-id="a4e5c-163">Exibir envios de administrador para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="a4e5c-163">View admin submissions to Microsoft</span></span>

1. <span data-ttu-id="a4e5c-164">No portal Microsoft 365 Defender, acesse **Email & envios de** \> **colaboração.**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-164">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="a4e5c-165">Na página **Envios,** verifique se a **guia Enviado para** análise está selecionada.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-165">On the **Submissions** page, verify that the **Submitted for analysis** tab is selected.</span></span>

   - <span data-ttu-id="a4e5c-166">Você pode classificar as entradas clicando em um header de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-166">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="a4e5c-167">Clique **em Personalizar colunas** para mostrar no máximo sete colunas.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-167">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="a4e5c-168">Os valores padrão são marcados com um asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="a4e5c-168">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>
     - <span data-ttu-id="a4e5c-169">**Nome do envio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4e5c-169">**Submission name**<sup>\*</sup></span></span>
     - <span data-ttu-id="a4e5c-170">**Remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4e5c-170">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="a4e5c-171">**Data enviada**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4e5c-171">**Date submitted**<sup>\*</sup></span></span>
     - <span data-ttu-id="a4e5c-172">**Tipo de envio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4e5c-172">**Submission type**<sup>\*</sup></span></span>
     - <span data-ttu-id="a4e5c-173">**Motivo para o envio**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4e5c-173">**Reason for submitting**<sup>\*</sup></span></span>
     - <span data-ttu-id="a4e5c-174">**Status da varredura novamente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4e5c-174">**Rescan status**<sup>\*</sup></span></span>
     - <span data-ttu-id="a4e5c-175">**Rescan result**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4e5c-175">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="a4e5c-176">**Veredito de filtro**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-176">**Filter verdict**</span></span>
     - <span data-ttu-id="a4e5c-177">**Motivo de entrega/bloqueio**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-177">**Delivery/Block reason**</span></span>
     - <span data-ttu-id="a4e5c-178">**ID do envio**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-178">**Submission ID**</span></span>
     - <span data-ttu-id="a4e5c-179">**ID de mensagem de rede/ID do objeto**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-179">**Network Message ID/Object ID**</span></span>
     - <span data-ttu-id="a4e5c-180">**Direção**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-180">**Direction**</span></span>
     - <span data-ttu-id="a4e5c-181">**IP do remetente**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-181">**Sender IP**</span></span>
     - <span data-ttu-id="a4e5c-182">**Nível compatível com massa (BCL)**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-182">**Bulk compliant level (BCL)**</span></span>
     - <span data-ttu-id="a4e5c-183">**Destino**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-183">**Destination**</span></span>
     - <span data-ttu-id="a4e5c-184">**Ação de política**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-184">**Policy action**</span></span>
     - <span data-ttu-id="a4e5c-185">**Enviado por**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-185">**Submitted by**</span></span>

     <span data-ttu-id="a4e5c-186">Quando terminar, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-186">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="a4e5c-187">Para filtrar as entradas, clique em **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-187">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="a4e5c-188">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="a4e5c-188">The available filters are:</span></span>
     - <span data-ttu-id="a4e5c-189">**Data enviada**: **Data de início** e data de **término.**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-189">**Date submitted**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="a4e5c-190">**Tipo de envio**: **Email,** **URL** ou **Arquivo.**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-190">**Submission type**: **Email**, **URL**, or **File**.</span></span>
     - <span data-ttu-id="a4e5c-191">**ID do envio:** um valor GUID atribuído a cada envio.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-191">**Submission ID**: A GUID value that's assigned to every submission.</span></span>
     - <span data-ttu-id="a4e5c-192">**ID da mensagem de rede**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-192">**Network Message ID**</span></span>
     - <span data-ttu-id="a4e5c-193">**Sender**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-193">**Sender**</span></span>

     <span data-ttu-id="a4e5c-194">Quando terminar, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-194">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="a4e5c-195">![Novas opções de Filtro para envios de administrador](../../media/admin-submission-filters.png)</span><span class="sxs-lookup"><span data-stu-id="a4e5c-195">![New Filter options for admin submissions](../../media/admin-submission-filters.png)</span></span>

   - <span data-ttu-id="a4e5c-196">Para agrupar as entradas, clique em **Grupo** e selecione um dos seguintes valores na listada:</span><span class="sxs-lookup"><span data-stu-id="a4e5c-196">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="a4e5c-197">**Nenhum**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-197">**None**</span></span>
     - <span data-ttu-id="a4e5c-198">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-198">**Type**</span></span>
     - <span data-ttu-id="a4e5c-199">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-199">**Reason**</span></span>
     - <span data-ttu-id="a4e5c-200">**Status**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-200">**Status**</span></span>
     - <span data-ttu-id="a4e5c-201">**Rescan result**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-201">**Rescan result**</span></span>

   - <span data-ttu-id="a4e5c-202">Para exportar as entradas, clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-202">To export the entries, click **Export**.</span></span> <span data-ttu-id="a4e5c-203">Na caixa de diálogo exibida, salve o arquivo .csv arquivo.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-203">In the dialog that appears, save the .csv file.</span></span>

### <a name="admin-submission-rescan-details"></a><span data-ttu-id="a4e5c-204">Detalhes da verificação de envio de administrador</span><span class="sxs-lookup"><span data-stu-id="a4e5c-204">Admin submission rescan details</span></span>

<span data-ttu-id="a4e5c-205">As mensagens enviadas em envios de administrador são revisadas e os resultados mostrados no submenu de detalhes de envios:</span><span class="sxs-lookup"><span data-stu-id="a4e5c-205">Messages that are submitted in admin submissions are reviewed and results shown in the submissions detail flyout:</span></span>

- <span data-ttu-id="a4e5c-206">Se houve falha na autenticação do email do remetente no momento da entrega.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-206">If there was a failure in the sender's email authentication at the time of delivery.</span></span>
- <span data-ttu-id="a4e5c-207">Informações sobre quaisquer acessos à política que possam ter afetado ou substituído o veredicto de uma mensagem.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-207">Information about any policy hits that could have affected or overridden the verdict of a message.</span></span>
- <span data-ttu-id="a4e5c-208">Resultados de detonação atuais para ver se os URLs ou arquivos contidos na mensagem eram maliciosos ou não.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-208">Current detonation results to see if the URLs or files contained in the message were malicious or not.</span></span>
- <span data-ttu-id="a4e5c-209">Comentários dos alunos.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-209">Feedback from graders.</span></span>

<span data-ttu-id="a4e5c-210">Se uma substituição for encontrada, a nova varredura deve ser concluída em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-210">If an override was found, the rescan should complete in several minutes.</span></span> <span data-ttu-id="a4e5c-211">Se não houve um problema na autenticação ou na entrega de email não foi afetado por uma substituição, os comentários dos alunos podem levar até um dia.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-211">If there wasn't a problem in email authentication or delivery wasn't affected by an override, then the feedback from graders could take up to a day.</span></span>

## <a name="view-user-submissions-to-microsoft"></a><span data-ttu-id="a4e5c-212">Exibir envios de usuários para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="a4e5c-212">View user submissions to Microsoft</span></span>

<span data-ttu-id="a4e5c-213">Se você tiver implantado o complemento Mensagem de [Relatório,](enable-the-report-message-add-in.md)o [add-in](enable-the-report-phish-add-in.md)Relatório phishing ou as pessoas usarem o relatório  integrado no [Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), você poderá ver o que os usuários estão relatando na guia Mensagem relatada pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-213">If you've deployed the [Report Message add-in](enable-the-report-message-add-in.md), the [Report Phishing add-in](enable-the-report-phish-add-in.md), or people use the [built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), you can see what users are reporting on the **User reported message** tab.</span></span>

1. <span data-ttu-id="a4e5c-214">No portal Microsoft 365 Defender, acesse **Email & envios de** \> **colaboração.**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-214">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Submissions**.</span></span>

2. <span data-ttu-id="a4e5c-215">Na página **Envios,** selecione a **guia Mensagens relatadas pelo** usuário.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-215">On the **Submissions** page, select the **User reported messages** tab.</span></span>

   - <span data-ttu-id="a4e5c-216">Você pode classificar as entradas clicando em um header de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-216">You can sort the entries by clicking on an available column header.</span></span> <span data-ttu-id="a4e5c-217">Clique **em Personalizar colunas** para mostrar no máximo sete colunas.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-217">Click **Customize columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="a4e5c-218">Os valores padrão são marcados com um asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="a4e5c-218">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

     - <span data-ttu-id="a4e5c-219">**Assunto de email**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4e5c-219">**Email subject**<sup>\*</sup></span></span>
     - <span data-ttu-id="a4e5c-220">**Relatado por**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4e5c-220">**Reported by**<sup>\*</sup></span></span>
     - <span data-ttu-id="a4e5c-221">**Data relatada**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4e5c-221">**Date reported**<sup>\*</sup></span></span>
     - <span data-ttu-id="a4e5c-222">**Remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4e5c-222">**Sender**<sup>\*</sup></span></span>
     - <span data-ttu-id="a4e5c-223">**Motivo relatado**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4e5c-223">**Reported reason**<sup>\*</sup></span></span>
     - <span data-ttu-id="a4e5c-224">**Rescan result**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a4e5c-224">**Rescan result**<sup>\*</sup></span></span>
     - <span data-ttu-id="a4e5c-225">**ID da mensagem relatada**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-225">**Message reported ID**</span></span>
     - <span data-ttu-id="a4e5c-226">**ID da mensagem de rede**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-226">**Network Message ID**</span></span>
     - <span data-ttu-id="a4e5c-227">**IP do remetente**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-227">**Sender IP**</span></span>
     - <span data-ttu-id="a4e5c-228">**Simulação de phishing**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-228">**Phish simulation**</span></span>

     <span data-ttu-id="a4e5c-229">Quando terminar, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-229">When you're finished, click **Apply**.</span></span>

   - <span data-ttu-id="a4e5c-230">Para filtrar as entradas, clique em **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-230">To filter the entries, click **Filter**.</span></span> <span data-ttu-id="a4e5c-231">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="a4e5c-231">The available filters are:</span></span>
     - <span data-ttu-id="a4e5c-232">**Data relatada**: **Data de início** e data de **término.**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-232">**Date reported**: **Start date** and **End date**.</span></span>
     - <span data-ttu-id="a4e5c-233">**Relatado por**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-233">**Reported by**</span></span>
     - <span data-ttu-id="a4e5c-234">**Assunto do email**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-234">**Email subject**</span></span>
     - <span data-ttu-id="a4e5c-235">**ID da mensagem relatada**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-235">**Message reported ID**</span></span>
     - <span data-ttu-id="a4e5c-236">**ID da mensagem de rede**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-236">**Network Message ID**</span></span>
     - <span data-ttu-id="a4e5c-237">**Sender**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-237">**Sender**</span></span>
     - <span data-ttu-id="a4e5c-238">**Motivo relatado:** **não lixo eletrônico,** **phishing** ou **spam.**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-238">**Reported reason**: **Not junk**, **Phish**, or **Spam**.</span></span>
     - <span data-ttu-id="a4e5c-239">**Simulação de phishing**: **Sim** ou **Não**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-239">**Phish simulation**: **Yes** or **No**</span></span>

     <span data-ttu-id="a4e5c-240">Quando terminar, clique em **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-240">When you're finished, click **Apply**.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="a4e5c-241">![Novas opções de Filtro para envios de usuários](../../media/admin-submission-reported-messages.png)</span><span class="sxs-lookup"><span data-stu-id="a4e5c-241">![New Filter options for user submissions](../../media/admin-submission-reported-messages.png)</span></span>

   - <span data-ttu-id="a4e5c-242">Para agrupar as entradas, clique em **Grupo** e selecione um dos seguintes valores na listada:</span><span class="sxs-lookup"><span data-stu-id="a4e5c-242">To group the entries, click **Group** and select one of the following values from the drop down list:</span></span>
     - <span data-ttu-id="a4e5c-243">**Nenhum**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-243">**None**</span></span>
     - <span data-ttu-id="a4e5c-244">**Motivo**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-244">**Reason**</span></span>
     - <span data-ttu-id="a4e5c-245">**Sender**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-245">**Sender**</span></span>
     - <span data-ttu-id="a4e5c-246">**Relatado por**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-246">**Reported by**</span></span>
     - <span data-ttu-id="a4e5c-247">**Rescan result**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-247">**Rescan result**</span></span>
     - <span data-ttu-id="a4e5c-248">**Simulação de phishing**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-248">**Phish simulation**</span></span>

   - <span data-ttu-id="a4e5c-249">Para exportar as entradas, clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-249">To export the entries, click **Export**.</span></span> <span data-ttu-id="a4e5c-250">Na caixa de diálogo exibida, salve o arquivo .csv arquivo.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-250">In the dialog that appears, save the .csv file.</span></span>

> [!NOTE]
> <span data-ttu-id="a4e5c-251">Se as organizações estão configuradas para enviar mensagens relatadas pelo usuário apenas para  a caixa de correio personalizada, as mensagens relatadas não serão enviadas para análise novamente e os resultados nas mensagens relatadas pelo usuário sempre estarão vazios.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-251">If organizations are configured to send user reported messages to the custom mailbox only, reported messages will not be sent for rescan and the results in **User reported messages** will always be empty.</span></span>

### <a name="undo-user-submissions"></a><span data-ttu-id="a4e5c-252">Desfazer envios de usuário</span><span class="sxs-lookup"><span data-stu-id="a4e5c-252">Undo user submissions</span></span>

<span data-ttu-id="a4e5c-253">Depois que um usuário envia um email suspeito para a caixa de correio personalizada, o usuário e o administrador não têm uma opção para desfazer o envio.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-253">Once a user submits a suspicious email to the custom mailbox, the user and admin don't have an option to undo the submission.</span></span> <span data-ttu-id="a4e5c-254">Se o usuário quiser recuperar o email, ele estará disponível para recuperação nas pastas Itens Excluídos ou Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-254">If the user would like to recover the email, it will be available for recovery in the Deleted Items or Junk Email folders.</span></span>

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a><span data-ttu-id="a4e5c-255">Enviar mensagens para a Microsoft da caixa de correio personalizada</span><span class="sxs-lookup"><span data-stu-id="a4e5c-255">Submit messages to Microsoft from the custom mailbox</span></span>

<span data-ttu-id="a4e5c-256">Se você configurou a caixa de correio personalizada para interceptar mensagens relatadas pelo usuário sem enviar as mensagens para a Microsoft, você poderá encontrar e enviar mensagens específicas para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-256">If you've configured the custom mailbox to intercept user-reported messages without sending the messages to Microsoft, you can find and send specific messages to Microsoft for analysis.</span></span> <span data-ttu-id="a4e5c-257">Isso move efetivamente um envio de usuário para um envio de administrador.</span><span class="sxs-lookup"><span data-stu-id="a4e5c-257">This effectively moves a user submission to an admin submission.</span></span>

<span data-ttu-id="a4e5c-258">Na guia **Mensagens relatadas pelo** usuário, selecione uma mensagem na lista, clique em Enviar para a **Microsoft** para análise e selecione um dos seguintes valores na listada:</span><span class="sxs-lookup"><span data-stu-id="a4e5c-258">On the **User reported messages** tab, select a message in the list, click **Submit to Microsoft for analysis**, and then select one of the following values from the drop down list:</span></span>

- <span data-ttu-id="a4e5c-259">**Relatório limpo**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-259">**Report clean**</span></span>
- <span data-ttu-id="a4e5c-260">**Relatar phishing**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-260">**Report phishing**</span></span>
- <span data-ttu-id="a4e5c-261">**Relatar malware**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-261">**Report malware**</span></span>
- <span data-ttu-id="a4e5c-262">**Relatar spam**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-262">**Report spam**</span></span>
- <span data-ttu-id="a4e5c-263">**Investigação de gatilho**</span><span class="sxs-lookup"><span data-stu-id="a4e5c-263">**Trigger investigation**</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="a4e5c-264">![Novas opções no botão Ação](../../media/admin-submission-main-action-button.png)</span><span class="sxs-lookup"><span data-stu-id="a4e5c-264">![New Options on the Action button](../../media/admin-submission-main-action-button.png)</span></span>
