---
title: Revogar emails criptografados pela Criptografia Avançada de Mensagens
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
description: Como administrador e remetente de mensagem, você pode revogar determinados emails que foram criptografados com Criptografia de Mensagem Avançada do Office 365.
ms.openlocfilehash: 340a9e73dba50e28223ee561db749a089c649df6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051713"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="457ae-103">Revogar emails criptografados pela Criptografia Avançada de Mensagens</span><span class="sxs-lookup"><span data-stu-id="457ae-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="457ae-104">A revogação de email é oferecida como parte Criptografia de Mensagem Avançada do Office 365.</span><span class="sxs-lookup"><span data-stu-id="457ae-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="457ae-105">Criptografia de Mensagem Avançada do Office 365 está incluído no [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Preços de Funcionários sem fins lucrativos), Office 365 Enterprise E5 (Preços de Funcionários sem fins lucrativos) e Office 365 Education A5.</span><span class="sxs-lookup"><span data-stu-id="457ae-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="457ae-106">Se sua organização tiver uma assinatura que não inclua o Criptografia de Mensagem Avançada do Office 365, você poderá compre-la com o complemento SKU do Microsoft 365 E5 Compliance para Microsoft 365 E3, Microsoft 365 E3 (Preços de Funcionários sem fins lucrativos) ou o complemento SKU do Conformidade Avançada do Office 365 para Microsoft 365 E3, Microsoft 365 E3 (Preços de Funcionários sem fins lucrativos) ou Office 365 SKUs.</span><span class="sxs-lookup"><span data-stu-id="457ae-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="457ae-107">Este artigo faz parte de uma série maior de artigos sobre [Criptografia de Mensagens do Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="457ae-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="457ae-108">Se uma mensagem foi criptografada usando Criptografia de Mensagem Avançada do Office 365, e você for um administrador Microsoft 365 ou você for o remetente da mensagem, poderá revogar a mensagem em determinadas condições.</span><span class="sxs-lookup"><span data-stu-id="457ae-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="457ae-109">Os administradores revogam mensagens usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="457ae-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="457ae-110">Como remetente, você revoga uma mensagem enviada diretamente do Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="457ae-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="457ae-111">Este artigo descreve as circunstâncias em que a revogação é possível e como fazê-la.</span><span class="sxs-lookup"><span data-stu-id="457ae-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="457ae-112">Emails criptografados que você pode revogar</span><span class="sxs-lookup"><span data-stu-id="457ae-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="457ae-113">Os administradores e os destinatários de mensagens podem revogar emails criptografados se o destinatário recebeu um email criptografado baseado em link com a marca.</span><span class="sxs-lookup"><span data-stu-id="457ae-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="457ae-114">Se o destinatário recebeu uma experiência em linha nativa em um cliente Outlook com suporte, você não poderá revogar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="457ae-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="457ae-115">Se um destinatário recebe uma experiência baseada em link ou uma experiência em linha depende do tipo de identidade do destinatário: Office 365 e destinatários de conta da Microsoft (por exemplo, usuários outlook.com) obter uma experiência em linha em clientes Outlook com suporte.</span><span class="sxs-lookup"><span data-stu-id="457ae-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="457ae-116">Todos os outros tipos de destinatários, como destinatários do Gmail e do Yahoo, obterão uma experiência baseada em link.</span><span class="sxs-lookup"><span data-stu-id="457ae-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="457ae-117">Os administradores e os envios de mensagens podem revogar mensagens criptografadas usando criptografia aplicada diretamente do Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="457ae-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="457ae-118">Por exemplo, mensagens criptografadas com a opção Criptografar Somente.</span><span class="sxs-lookup"><span data-stu-id="457ae-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Captura de tela mostrando a opção Criptografar Somente Outlook na Web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="457ae-120">Experiência do destinatário para emails criptografados revogados</span><span class="sxs-lookup"><span data-stu-id="457ae-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="457ae-121">Depois que um email é revogado, o destinatário recebe um erro ao acessar o email criptografado por meio do portal Criptografia de Mensagens do Office 365: "A mensagem foi revogada pelo remetente".</span><span class="sxs-lookup"><span data-stu-id="457ae-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![Captura de tela que mostra um email criptografado revogado.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="457ae-123">Como revogar uma mensagem criptografada que você enviou</span><span class="sxs-lookup"><span data-stu-id="457ae-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="457ae-124">Você pode revogar um email enviado para um único destinatário que usa uma conta social como gmail.com ou yahoo.com.</span><span class="sxs-lookup"><span data-stu-id="457ae-124">You can revoke a mail that you sent to a single recipient that uses a social account such as gmail.com or yahoo.com.</span></span> <span data-ttu-id="457ae-125">Em outras palavras, você pode revogar um email enviado para um único destinatário que recebeu a experiência baseada em link.</span><span class="sxs-lookup"><span data-stu-id="457ae-125">In other words, you can revoke an email sent to a single recipient that received the link-based experience.</span></span>

<span data-ttu-id="457ae-126">Não é possível revogar um email enviado a um destinatário que usa uma conta de estudante ou trabalho do Office 365 ou Microsoft 365 ou um usuário que usa uma conta da Microsoft, por exemplo, uma conta outlook.com.</span><span class="sxs-lookup"><span data-stu-id="457ae-126">You cannot revoke a mail that you sent to a recipient that uses a work or school account from Office 365 or Microsoft 365 or a user that uses a Microsoft account, for example, an outlook.com account.</span></span> 

<span data-ttu-id="457ae-127">Para revogar uma mensagem criptografada enviada, conclua estas etapas</span><span class="sxs-lookup"><span data-stu-id="457ae-127">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="457ae-128">Em Outlook na Web, em sua pasta **Enviada,** navegue até a mensagem que você deseja revogar.</span><span class="sxs-lookup"><span data-stu-id="457ae-128">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="457ae-129">Se o email for revogado, você verá o link "Remover acesso externo" na parte superior da mensagem.</span><span class="sxs-lookup"><span data-stu-id="457ae-129">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Captura de tela mostrando emails criptografados que você deseja revogar Outlook na Web.":::

2. <span data-ttu-id="457ae-131">Clique **em Remover acesso externo** para revogar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="457ae-131">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="457ae-132">A mensagem mostra que seu status foi revogado.</span><span class="sxs-lookup"><span data-stu-id="457ae-132">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Captura de tela mostrando a mensagem criptografada revogada Outlook na Web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="457ae-134">Como revogar uma mensagem criptografada como administrador</span><span class="sxs-lookup"><span data-stu-id="457ae-134">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="457ae-135">Microsoft 365 administradores seguem estas etapas gerais para revogar um email criptografado qualificado:</span><span class="sxs-lookup"><span data-stu-id="457ae-135">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="457ae-136">Obter a ID da mensagem do email.</span><span class="sxs-lookup"><span data-stu-id="457ae-136">Get the Message ID of the email.</span></span>
- <span data-ttu-id="457ae-137">Verifique se você pode revogar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="457ae-137">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="457ae-138">Revogar o email.</span><span class="sxs-lookup"><span data-stu-id="457ae-138">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="457ae-139">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="457ae-139">Step 1.</span></span> <span data-ttu-id="457ae-140">Obter a ID da mensagem do email</span><span class="sxs-lookup"><span data-stu-id="457ae-140">Obtain the Message ID of the email</span></span>

<span data-ttu-id="457ae-141">Antes de revogar um email criptografado, reúna a ID da mensagem do email.</span><span class="sxs-lookup"><span data-stu-id="457ae-141">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="457ae-142">MessageId geralmente é do formato:</span><span class="sxs-lookup"><span data-stu-id="457ae-142">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="457ae-143">Há várias maneiras de encontrar a ID da mensagem do email que você deseja revogar.</span><span class="sxs-lookup"><span data-stu-id="457ae-143">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="457ae-144">Esta seção descreve algumas opções, mas você pode usar qualquer método que fornece a ID.</span><span class="sxs-lookup"><span data-stu-id="457ae-144">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="457ae-145">Para identificar a ID da mensagem do email que você deseja revogar usando o Rastreamento de Mensagens no Centro &amp; de Conformidade de Segurança</span><span class="sxs-lookup"><span data-stu-id="457ae-145">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="457ae-146">Pesquise o email por remetente ou destinatário usando Novo Rastreamento de Mensagens no Centro de [Conformidade & Segurança.](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)</span><span class="sxs-lookup"><span data-stu-id="457ae-146">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="457ae-147">Depois de localizar o email, selecione-o para trazer o painel Detalhes de **rastreamento de** mensagens.</span><span class="sxs-lookup"><span data-stu-id="457ae-147">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="457ae-148">Expanda **Mais Informações** para localizar a ID da Mensagem.</span><span class="sxs-lookup"><span data-stu-id="457ae-148">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="457ae-149">Para identificar a ID da mensagem do email que você deseja revogar usando Office de Criptografia de Mensagens no Centro de &amp; Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="457ae-149">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="457ae-150">No Centro de &amp; Conformidade de Segurança, navegue até o **relatório de criptografia de mensagem**.</span><span class="sxs-lookup"><span data-stu-id="457ae-150">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="457ae-151">Para obter informações sobre este relatório, consulte [Exibir relatórios de segurança de email no Centro de Conformidade de &amp; Segurança.](../security/defender-365-security/view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="457ae-151">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/defender-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="457ae-152">Escolha a **tabela Exibir detalhes** e identifique a mensagem que você deseja revogar.</span><span class="sxs-lookup"><span data-stu-id="457ae-152">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="457ae-153">Clique duas vezes na mensagem para exibir detalhes que incluem a ID da mensagem.</span><span class="sxs-lookup"><span data-stu-id="457ae-153">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="457ae-154">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="457ae-154">Step 2.</span></span> <span data-ttu-id="457ae-155">Verifique se o email é revogado</span><span class="sxs-lookup"><span data-stu-id="457ae-155">Verify that the mail is revocable</span></span>

<span data-ttu-id="457ae-156">Para verificar se você pode revogar uma mensagem, verifique se o campo Status  de Revogação está visível no relatório de criptografia, na tabela Detalhes no Centro de Conformidade &amp; de Segurança.</span><span class="sxs-lookup"><span data-stu-id="457ae-156">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="457ae-157">Para verificar se você pode revogar uma mensagem de email específica usando Windows PowerShell, conclua estas etapas.</span><span class="sxs-lookup"><span data-stu-id="457ae-157">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="457ae-158">Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, inicie uma sessão de Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="457ae-158">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="457ae-159">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="457ae-159">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="457ae-160">Execute o Get-OMEMessageStatus cmdlet da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="457ae-160">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="457ae-161">Este comando retorna o assunto da mensagem e se a mensagem é revogada.</span><span class="sxs-lookup"><span data-stu-id="457ae-161">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="457ae-162">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="457ae-162">For example,</span></span>

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="457ae-163">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="457ae-163">Step 3.</span></span> <span data-ttu-id="457ae-164">Revogar o email</span><span class="sxs-lookup"><span data-stu-id="457ae-164">Revoke the mail</span></span>

<span data-ttu-id="457ae-165">Depois de saber a ID da mensagem do email que deseja revogar e verificar se a mensagem é revogada, você pode revogar o email usando o Centro de Conformidade de Segurança ou &amp; Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="457ae-165">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="457ae-166">Para revogar a mensagem usando o Centro de &amp; Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="457ae-166">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="457ae-167">Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, conecte-se ao Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="457ae-167">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="457ae-168">No relatório **criptografia**, na tabela **Detalhes** da mensagem, escolha **Revogar mensagem**.</span><span class="sxs-lookup"><span data-stu-id="457ae-168">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="457ae-169">Para revogar um email usando o Windows PowerShell, use o cmdlet Set-OMEMessageRevocation usuário.</span><span class="sxs-lookup"><span data-stu-id="457ae-169">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="457ae-170">Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, Conexão [para Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="457ae-170">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="457ae-171">Execute o Set-OMEMessageRevocation cmdlet da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="457ae-171">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="457ae-172">Para verificar se o email foi revogado, execute o cmdlet Get-OMEMessageStatus da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="457ae-172">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="457ae-173">Se a revogação tiver sido bem-sucedida, o cmdlet retornará o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="457ae-173">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="457ae-174">Mais informações sobre Criptografia de Mensagem Avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="457ae-174">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="457ae-175">Criptografia de Mensagem Avançada do 365 Office</span><span class="sxs-lookup"><span data-stu-id="457ae-175">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="457ae-176">Criptografia de Mensagem Avançada do Office 365 - expiração de email</span><span class="sxs-lookup"><span data-stu-id="457ae-176">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="457ae-177">Descrição do serviço de conformidade e política de mensagem</span><span class="sxs-lookup"><span data-stu-id="457ae-177">Message policy and compliance service description</span></span>](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)