---
title: Revogar emails criptografados por criptografia de mensagem avançada
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Como administrador e como um remetente de mensagem, você pode revogar certos emails que foram criptografados com a criptografia de mensagem avançada do Office 365.
ms.openlocfilehash: 79ab3ef801d4d19317cbf1416d858de74d9f1393
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868928"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="182f6-103">Revogar emails criptografados por criptografia de mensagem avançada</span><span class="sxs-lookup"><span data-stu-id="182f6-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="182f6-104">A revogação de emails é oferecida como parte da criptografia de mensagem avançada do Office 365.</span><span class="sxs-lookup"><span data-stu-id="182f6-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="182f6-105">O Office 365 Advanced Message Encryption está incluído no [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 e5, Microsoft 365 E5 (precificação de pessoas sem fins lucrativos), Office 365 Enterprise E5 (precificação de pessoas sem fins lucrativos) e Office 365 Education a5.</span><span class="sxs-lookup"><span data-stu-id="182f6-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="182f6-106">Se sua organização tem uma assinatura que não inclui a criptografia de mensagem avançada do Office 365, você pode comprá-la com o complemento de SKU de conformidade da Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (preço de equipe sem fins lucrativos) ou o complemento avançado de SKU de conformidade avançada do Office para a Microsoft 365 E3, Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="182f6-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="182f6-107">Este artigo faz parte de uma série maior de artigos sobre a [criptografia de mensagens do Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="182f6-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="182f6-108">Se uma mensagem foi criptografada usando a criptografia de mensagem avançada do Office 365 e você for um administrador de 365 da Microsoft ou se for o remetente da mensagem, você poderá revogar a mensagem sob determinadas condições.</span><span class="sxs-lookup"><span data-stu-id="182f6-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="182f6-109">Os administradores revogam mensagens usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="182f6-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="182f6-110">Como remetente, você revoga uma mensagem que enviou diretamente do Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="182f6-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="182f6-111">Este artigo descreve as circunstâncias nas quais a revogação é possível e como fazê-la.</span><span class="sxs-lookup"><span data-stu-id="182f6-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="182f6-112">Emails criptografados que podem ser revogados</span><span class="sxs-lookup"><span data-stu-id="182f6-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="182f6-113">Os administradores e os remetentes de mensagens podem revogar emails criptografados se o destinatário recebeu um email criptografado com base em link e com marca.</span><span class="sxs-lookup"><span data-stu-id="182f6-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="182f6-114">Se o destinatário recebeu uma experiência interna nativa em um cliente do Outlook com suporte, então você não poderá revogar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="182f6-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="182f6-115">Se um destinatário recebe uma experiência baseada em links ou uma experiência embutida depende do tipo de identidade do destinatário: o Office 365 e os destinatários da conta da Microsoft (por exemplo, usuários do outlook.com) recebem uma experiência embutida em clientes do Outlook com suporte.</span><span class="sxs-lookup"><span data-stu-id="182f6-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="182f6-116">Todos os outros tipos de destinatários, como os destinatários do Gmail e Yahoo, obtêm uma experiência baseada em links.</span><span class="sxs-lookup"><span data-stu-id="182f6-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="182f6-117">Os administradores e remetentes de mensagens podem revogar mensagens criptografadas usando a criptografia aplicada diretamente do Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="182f6-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="182f6-118">Por exemplo, mensagens criptografadas com a opção somente criptografar.</span><span class="sxs-lookup"><span data-stu-id="182f6-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Captura de tela mostrando a opção somente criptografia no Outlook na Web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="182f6-120">Experiência de destinatário para emails criptografados revogados</span><span class="sxs-lookup"><span data-stu-id="182f6-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="182f6-121">Depois que um email é revogado, o destinatário recebe um erro quando acessa o email criptografado por meio do portal de criptografia de mensagem do Office 365: "a mensagem foi revogada pelo remetente".</span><span class="sxs-lookup"><span data-stu-id="182f6-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![Captura de tela que mostra um email criptografado revogado.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="182f6-123">Como revogar uma mensagem criptografada que você enviou</span><span class="sxs-lookup"><span data-stu-id="182f6-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="182f6-124">Para revogar uma mensagem criptografada que você enviou, conclua estas etapas</span><span class="sxs-lookup"><span data-stu-id="182f6-124">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="182f6-125">No Outlook na Web, na pasta **enviado** , procure a mensagem que você deseja revogar.</span><span class="sxs-lookup"><span data-stu-id="182f6-125">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="182f6-126">Se o email for revogável, você verá o link "remover acesso externo" na parte superior da mensagem.</span><span class="sxs-lookup"><span data-stu-id="182f6-126">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Captura de tela mostrando mensagens criptografadas que você deseja revogar no Outlook na Web.":::

2. <span data-ttu-id="182f6-128">Clique em **remover o acesso externo** para revogar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="182f6-128">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="182f6-129">A mensagem mostra que o status é revogado.</span><span class="sxs-lookup"><span data-stu-id="182f6-129">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Captura de tela mostrando a mensagem criptografada revogada no Outlook na Web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="182f6-131">Como revogar uma mensagem criptografada como administrador</span><span class="sxs-lookup"><span data-stu-id="182f6-131">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="182f6-132">Os administradores do Microsoft 365 seguem estas etapas gerais para revogar um email criptografado qualificado:</span><span class="sxs-lookup"><span data-stu-id="182f6-132">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="182f6-133">Obtenha a ID da mensagem do email.</span><span class="sxs-lookup"><span data-stu-id="182f6-133">Get the Message ID of the email.</span></span>
- <span data-ttu-id="182f6-134">Verifique se é possível revogar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="182f6-134">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="182f6-135">Revogar o email.</span><span class="sxs-lookup"><span data-stu-id="182f6-135">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="182f6-136">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="182f6-136">Step 1.</span></span> <span data-ttu-id="182f6-137">Obter a ID da mensagem do email</span><span class="sxs-lookup"><span data-stu-id="182f6-137">Obtain the Message ID of the email</span></span>

<span data-ttu-id="182f6-138">Para que você possa revogar um email criptografado, colete a ID da mensagem do email.</span><span class="sxs-lookup"><span data-stu-id="182f6-138">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="182f6-139">Em geral, a MessageId é do formato:</span><span class="sxs-lookup"><span data-stu-id="182f6-139">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="182f6-140">Há várias maneiras de encontrar a ID da mensagem do email que você deseja revogar.</span><span class="sxs-lookup"><span data-stu-id="182f6-140">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="182f6-141">Esta seção descreve algumas opções, mas você pode usar qualquer método que forneça a ID.</span><span class="sxs-lookup"><span data-stu-id="182f6-141">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="182f6-142">Para identificar a ID de mensagem do email que você deseja revogar usando o rastreamento de mensagens no &amp; centro de conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="182f6-142">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="182f6-143">Procure o email por remetente ou destinatário usando o [rastreamento de novas mensagens no centro de conformidade e segurança &](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="182f6-143">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="182f6-144">Depois de localizar o email, selecione-o para exibir o painel de **detalhes de rastreamento de mensagens** .</span><span class="sxs-lookup"><span data-stu-id="182f6-144">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="182f6-145">Expanda **mais informações** para localizar a ID da mensagem.</span><span class="sxs-lookup"><span data-stu-id="182f6-145">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="182f6-146">Para identificar a ID de mensagem do email que você deseja revogar usando os relatórios de criptografia de mensagem do Office no centro de conformidade de segurança &amp;</span><span class="sxs-lookup"><span data-stu-id="182f6-146">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="182f6-147">No centro de &amp; conformidade de segurança, navegue até o **relatório de criptografia de mensagem**.</span><span class="sxs-lookup"><span data-stu-id="182f6-147">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="182f6-148">Para obter informações sobre este relatório, consulte [exibir relatórios de segurança de email no &amp; centro de conformidade de segurança](../security/office-365-security/view-email-security-reports.md).</span><span class="sxs-lookup"><span data-stu-id="182f6-148">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="182f6-149">Escolha a tabela **Exibir detalhes** e identifique a mensagem que você deseja revogar.</span><span class="sxs-lookup"><span data-stu-id="182f6-149">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="182f6-150">Clique duas vezes na mensagem para exibir os detalhes que incluem a ID da mensagem.</span><span class="sxs-lookup"><span data-stu-id="182f6-150">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="182f6-151">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="182f6-151">Step 2.</span></span> <span data-ttu-id="182f6-152">Verifique se o email é revogável</span><span class="sxs-lookup"><span data-stu-id="182f6-152">Verify that the mail is revocable</span></span>

<span data-ttu-id="182f6-153">Para verificar se você pode revogar uma mensagem, verifique se o campo status de revogação está visível no relatório de criptografia, na tabela **detalhes** no centro de conformidade de segurança &amp; .</span><span class="sxs-lookup"><span data-stu-id="182f6-153">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="182f6-154">Para verificar se você pode revogar uma mensagem de email específica usando o Windows PowerShell, conclua estas etapas.</span><span class="sxs-lookup"><span data-stu-id="182f6-154">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="182f6-155">Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="182f6-155">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="182f6-156">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="182f6-156">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="182f6-157">Execute o cmdlet Get-OMEMessageStatus da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="182f6-157">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="182f6-158">Este comando retorna o assunto da mensagem e se a mensagem é revogável.</span><span class="sxs-lookup"><span data-stu-id="182f6-158">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="182f6-159">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="182f6-159">For example,</span></span>

     ```text
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="182f6-160">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="182f6-160">Step 3.</span></span> <span data-ttu-id="182f6-161">Revogar o email</span><span class="sxs-lookup"><span data-stu-id="182f6-161">Revoke the mail</span></span>

<span data-ttu-id="182f6-162">Quando você souber a ID da mensagem do email que deseja revogar e tiver verificado que a mensagem é revogável, é possível revogar o email usando o centro de conformidade de segurança &amp; ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="182f6-162">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="182f6-163">Para revogar a mensagem usando o &amp; centro de conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="182f6-163">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="182f6-164">Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, conecte-se ao centro de conformidade do & de segurança.</span><span class="sxs-lookup"><span data-stu-id="182f6-164">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="182f6-165">No **relatório de criptografia**, na tabela **detalhes** da mensagem, escolha **revogar mensagem**.</span><span class="sxs-lookup"><span data-stu-id="182f6-165">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="182f6-166">Para revogar um email usando o Windows PowerShell, use o cmdlet Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="182f6-166">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="182f6-167">Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, [Conecte-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="182f6-167">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="182f6-168">Execute o cmdlet Set-OMEMessageRevocation da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="182f6-168">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="182f6-169">Para verificar se o email foi revogado, execute o cmdlet Get-OMEMessageStatus da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="182f6-169">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="182f6-170">Se a revogação tiver sido bem-sucedida, o cmdlet retornará o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="182f6-170">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="182f6-171">Mais informações sobre a criptografia de mensagem avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="182f6-171">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="182f6-172">Criptografia de Mensagem Avançada do 365 Office</span><span class="sxs-lookup"><span data-stu-id="182f6-172">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="182f6-173">Criptografia de mensagem avançada do Office 365-expiração de email</span><span class="sxs-lookup"><span data-stu-id="182f6-173">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="182f6-174">Descrição do serviço de conformidade e política de mensagens</span><span class="sxs-lookup"><span data-stu-id="182f6-174">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
