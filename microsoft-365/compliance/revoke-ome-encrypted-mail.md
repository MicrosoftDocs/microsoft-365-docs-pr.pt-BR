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
description: Como administrador e remetente de mensagem, você pode revogar determinados emails que foram criptografados com a Criptografia Avançada de Mensagens do Office 365.
ms.openlocfilehash: b49915b6ef72d366a4b2718319150d2d5b640b9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917193"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="a5f07-103">Revogar emails criptografados pela Criptografia Avançada de Mensagens</span><span class="sxs-lookup"><span data-stu-id="a5f07-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="a5f07-104">A revogação de email é oferecida como parte da Criptografia Avançada de Mensagens do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a5f07-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="a5f07-105">A Criptografia Avançada de Mensagens do Office 365 está incluída no [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), no Office 365 E5, no Microsoft 365 E5 (Preços de Funcionários sem fins lucrativos), no Office 365 Enterprise E5 (Preços de Funcionários sem fins lucrativos) e no Office 365 Education A5.</span><span class="sxs-lookup"><span data-stu-id="a5f07-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="a5f07-106">Se sua organização tiver uma assinatura que não inclua a Criptografia Avançada de Mensagens do Office 365, você pode compra-lo com o complemento SKU de Conformidade do Microsoft 365 E5 para o Microsoft 365 E3, o Microsoft 365 E3 (Preços de Equipe sem fins lucrativos) ou o complemento SKU de Conformidade Avançada do Office 365 para o Microsoft 365 E3, o Microsoft 365 E3 (Preços da Equipe Sem Fins Lucrativos) ou o SKUs do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a5f07-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="a5f07-107">Este artigo faz parte de uma série maior de artigos sobre a Criptografia de Mensagens do [Office 365.](ome.md)</span><span class="sxs-lookup"><span data-stu-id="a5f07-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="a5f07-108">Se uma mensagem foi criptografada usando a Criptografia Avançada de Mensagens do Office 365 e você é um administrador do Microsoft 365 ou você é o remetente da mensagem, você pode revogar a mensagem em determinadas condições.</span><span class="sxs-lookup"><span data-stu-id="a5f07-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="a5f07-109">Os administradores revogam mensagens usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a5f07-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="a5f07-110">Como remetente, você revoga uma mensagem enviada diretamente do Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="a5f07-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="a5f07-111">Este artigo descreve as circunstâncias em que a revogação é possível e como fazê-la.</span><span class="sxs-lookup"><span data-stu-id="a5f07-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="a5f07-112">Emails criptografados que você pode revogar</span><span class="sxs-lookup"><span data-stu-id="a5f07-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="a5f07-113">Os administradores e os destinatários de mensagens podem revogar emails criptografados se o destinatário recebeu um email criptografado baseado em link com a marca.</span><span class="sxs-lookup"><span data-stu-id="a5f07-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="a5f07-114">Se o destinatário recebeu uma experiência em linha nativa em um cliente do Outlook com suporte, você não pode revogar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="a5f07-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="a5f07-115">Se um destinatário recebe uma experiência baseada em link ou uma experiência em linha depende do tipo de identidade do destinatário: os destinatários de contas do Office 365 e da Microsoft (por exemplo, outlook.com usuários) recebem uma experiência em linha nos clientes do Outlook com suporte.</span><span class="sxs-lookup"><span data-stu-id="a5f07-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="a5f07-116">Todos os outros tipos de destinatários, como destinatários do Gmail e do Yahoo, obterão uma experiência baseada em link.</span><span class="sxs-lookup"><span data-stu-id="a5f07-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="a5f07-117">Os administradores e os envios de mensagens podem revogar mensagens criptografadas usando criptografia aplicada diretamente do Outlook na Web.</span><span class="sxs-lookup"><span data-stu-id="a5f07-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="a5f07-118">Por exemplo, mensagens criptografadas com a opção Criptografar Somente.</span><span class="sxs-lookup"><span data-stu-id="a5f07-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Captura de tela mostrando a opção Criptografar Somente no Outlook na Web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="a5f07-120">Experiência do destinatário para emails criptografados revogados</span><span class="sxs-lookup"><span data-stu-id="a5f07-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="a5f07-121">Depois que um email é revogado, o destinatário recebe um erro ao acessar o email criptografado por meio do portal de Criptografia de Mensagens do Office 365: "A mensagem foi revogada pelo remetente".</span><span class="sxs-lookup"><span data-stu-id="a5f07-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![Captura de tela que mostra um email criptografado revogado.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="a5f07-123">Como revogar uma mensagem criptografada que você enviou</span><span class="sxs-lookup"><span data-stu-id="a5f07-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="a5f07-124">Você pode revogar um email enviado para um único destinatário que usa uma conta social como gmail.com ou yahoo.com.</span><span class="sxs-lookup"><span data-stu-id="a5f07-124">You can revoke a mail that you sent to a single recipient that uses a social account such as gmail.com or yahoo.com.</span></span> <span data-ttu-id="a5f07-125">Em outras palavras, você pode revogar um email enviado para um único destinatário que recebeu a experiência baseada em link.</span><span class="sxs-lookup"><span data-stu-id="a5f07-125">In other words, you can revoke an email sent to a single recipient that received the link-based experience.</span></span>

<span data-ttu-id="a5f07-126">Não é possível revogar um email enviado a um destinatário que usa uma conta de estudante ou de trabalho do Office 365 ou do Microsoft 365 ou de um usuário que usa uma conta da Microsoft, por exemplo, uma conta outlook.com.</span><span class="sxs-lookup"><span data-stu-id="a5f07-126">You cannot revoke a mail that you sent to a recipient that uses a work or school account from Office 365 or Microsoft 365 or a user that uses a Microsoft account, for example, an outlook.com account.</span></span> 

<span data-ttu-id="a5f07-127">Para revogar uma mensagem criptografada enviada, conclua estas etapas</span><span class="sxs-lookup"><span data-stu-id="a5f07-127">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="a5f07-128">No Outlook na Web, em sua **pasta Enviada,** navegue até a mensagem que você deseja revogar.</span><span class="sxs-lookup"><span data-stu-id="a5f07-128">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="a5f07-129">Se o email for revogado, você verá o link "Remover acesso externo" na parte superior da mensagem.</span><span class="sxs-lookup"><span data-stu-id="a5f07-129">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Captura de tela mostrando emails criptografados que você deseja revogar no Outlook na Web.":::

2. <span data-ttu-id="a5f07-131">Clique **em Remover acesso externo** para revogar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="a5f07-131">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="a5f07-132">A mensagem mostra que seu status foi revogado.</span><span class="sxs-lookup"><span data-stu-id="a5f07-132">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Captura de tela mostrando a mensagem criptografada revogada no Outlook na Web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="a5f07-134">Como revogar uma mensagem criptografada como administrador</span><span class="sxs-lookup"><span data-stu-id="a5f07-134">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="a5f07-135">Os administradores do Microsoft 365 seguem estas etapas gerais para revogar um email criptografado qualificado:</span><span class="sxs-lookup"><span data-stu-id="a5f07-135">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="a5f07-136">Obter a ID da mensagem do email.</span><span class="sxs-lookup"><span data-stu-id="a5f07-136">Get the Message ID of the email.</span></span>
- <span data-ttu-id="a5f07-137">Verifique se você pode revogar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="a5f07-137">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="a5f07-138">Revogar o email.</span><span class="sxs-lookup"><span data-stu-id="a5f07-138">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="a5f07-139">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="a5f07-139">Step 1.</span></span> <span data-ttu-id="a5f07-140">Obter a ID da mensagem do email</span><span class="sxs-lookup"><span data-stu-id="a5f07-140">Obtain the Message ID of the email</span></span>

<span data-ttu-id="a5f07-141">Antes de revogar um email criptografado, reúna a ID da mensagem do email.</span><span class="sxs-lookup"><span data-stu-id="a5f07-141">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="a5f07-142">MessageId geralmente é do formato:</span><span class="sxs-lookup"><span data-stu-id="a5f07-142">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="a5f07-143">Há várias maneiras de encontrar a ID da mensagem do email que você deseja revogar.</span><span class="sxs-lookup"><span data-stu-id="a5f07-143">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="a5f07-144">Esta seção descreve algumas opções, mas você pode usar qualquer método que fornece a ID.</span><span class="sxs-lookup"><span data-stu-id="a5f07-144">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="a5f07-145">Para identificar a ID da mensagem do email que você deseja revogar usando o Rastreamento de Mensagens no Centro &amp; de Conformidade de Segurança</span><span class="sxs-lookup"><span data-stu-id="a5f07-145">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="a5f07-146">Pesquise o email por remetente ou destinatário usando Novo Rastreamento de Mensagens no Centro de [Conformidade & Segurança.](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)</span><span class="sxs-lookup"><span data-stu-id="a5f07-146">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="a5f07-147">Depois de localizar o email, selecione-o para trazer o painel Detalhes de **rastreamento de** mensagens.</span><span class="sxs-lookup"><span data-stu-id="a5f07-147">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="a5f07-148">Expanda **Mais Informações** para localizar a ID da Mensagem.</span><span class="sxs-lookup"><span data-stu-id="a5f07-148">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="a5f07-149">Para identificar a ID da mensagem do email que você deseja revogar usando relatórios de Criptografia de Mensagens do Office no Centro &amp; de Conformidade de Segurança</span><span class="sxs-lookup"><span data-stu-id="a5f07-149">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="a5f07-150">No Centro de &amp; Conformidade de Segurança, navegue até o **relatório de criptografia de mensagem**.</span><span class="sxs-lookup"><span data-stu-id="a5f07-150">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="a5f07-151">Para obter informações sobre este relatório, consulte [Exibir relatórios de segurança de email no Centro de Conformidade de &amp; Segurança.](../security/office-365-security/view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="a5f07-151">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="a5f07-152">Escolha a **tabela Exibir detalhes** e identifique a mensagem que você deseja revogar.</span><span class="sxs-lookup"><span data-stu-id="a5f07-152">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="a5f07-153">Clique duas vezes na mensagem para exibir detalhes que incluem a ID da mensagem.</span><span class="sxs-lookup"><span data-stu-id="a5f07-153">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="a5f07-154">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="a5f07-154">Step 2.</span></span> <span data-ttu-id="a5f07-155">Verifique se o email é revogado</span><span class="sxs-lookup"><span data-stu-id="a5f07-155">Verify that the mail is revocable</span></span>

<span data-ttu-id="a5f07-156">Para verificar se você pode revogar uma mensagem, verifique se o campo Status  de Revogação está visível no relatório de criptografia, na tabela Detalhes no Centro de Conformidade &amp; de Segurança.</span><span class="sxs-lookup"><span data-stu-id="a5f07-156">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="a5f07-157">Para verificar se você pode revogar uma mensagem de email específica usando Windows PowerShell, conclua estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a5f07-157">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="a5f07-158">Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, inicie uma sessão Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a5f07-158">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="a5f07-159">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a5f07-159">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="a5f07-160">Execute o Get-OMEMessageStatus cmdlet da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="a5f07-160">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="a5f07-161">Este comando retorna o assunto da mensagem e se a mensagem é revogada.</span><span class="sxs-lookup"><span data-stu-id="a5f07-161">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="a5f07-162">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="a5f07-162">For example,</span></span>

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="a5f07-163">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="a5f07-163">Step 3.</span></span> <span data-ttu-id="a5f07-164">Revogar o email</span><span class="sxs-lookup"><span data-stu-id="a5f07-164">Revoke the mail</span></span>

<span data-ttu-id="a5f07-165">Depois de saber a ID da mensagem do email que deseja revogar e verificar se a mensagem é revogada, você pode revogar o email usando o Centro de Conformidade de Segurança ou &amp; Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a5f07-165">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="a5f07-166">Para revogar a mensagem usando o Centro de &amp; Conformidade e Segurança</span><span class="sxs-lookup"><span data-stu-id="a5f07-166">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="a5f07-167">Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, conecte-se ao Centro de Conformidade & Segurança.</span><span class="sxs-lookup"><span data-stu-id="a5f07-167">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="a5f07-168">No relatório **criptografia**, na tabela **Detalhes** da mensagem, escolha **Revogar mensagem**.</span><span class="sxs-lookup"><span data-stu-id="a5f07-168">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="a5f07-169">Para revogar um email usando o Windows PowerShell, use o cmdlet Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="a5f07-169">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="a5f07-170">Usando uma conta de trabalho ou de estudante que tenha permissões globais de administrador em sua organização, [Conecte-se ao PowerShell do Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="a5f07-170">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="a5f07-171">Execute o Set-OMEMessageRevocation cmdlet da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="a5f07-171">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="a5f07-172">Para verificar se o email foi revogado, execute o cmdlet Get-OMEMessageStatus da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="a5f07-172">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="a5f07-173">Se a revogação tiver sido bem-sucedida, o cmdlet retornará o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="a5f07-173">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="a5f07-174">Mais informações sobre a Criptografia Avançada de Mensagens do Office 365</span><span class="sxs-lookup"><span data-stu-id="a5f07-174">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="a5f07-175">Criptografia de Mensagem Avançada do 365 Office</span><span class="sxs-lookup"><span data-stu-id="a5f07-175">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="a5f07-176">Criptografia avançada de mensagens do Office 365 - expiração de email</span><span class="sxs-lookup"><span data-stu-id="a5f07-176">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="a5f07-177">Descrição do serviço de conformidade e política de mensagem</span><span class="sxs-lookup"><span data-stu-id="a5f07-177">Message policy and compliance service description</span></span>](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)