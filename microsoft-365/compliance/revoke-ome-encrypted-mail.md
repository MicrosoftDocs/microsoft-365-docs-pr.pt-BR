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
ms.date: 02/28/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Como administrador, você pode revogar certos emails que foram criptografados com a criptografia de mensagem avançada do Office 365.
ms.openlocfilehash: 271aa1b3644983907c341cf7f9ad6d526597ad59
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626487"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="cd91c-103">Revogar emails criptografados por criptografia de mensagem avançada</span><span class="sxs-lookup"><span data-stu-id="cd91c-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="cd91c-104">A revogação de emails é oferecida como parte da criptografia de mensagem avançada do Office 365.</span><span class="sxs-lookup"><span data-stu-id="cd91c-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="cd91c-105">O Office 365 Advanced Message Encryption está incluído no [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 e5, Microsoft 365 E5 (precificação de pessoas sem fins lucrativos), Office 365 Enterprise E5 (precificação de pessoas sem fins lucrativos) e Office 365 Education a5.</span><span class="sxs-lookup"><span data-stu-id="cd91c-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="cd91c-106">Se sua organização tem uma assinatura que não inclui a criptografia de mensagem avançada do Office 365, você pode comprá-la com o complemento de SKU de conformidade da Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (preço de equipe sem fins lucrativos) ou o complemento avançado de SKU de conformidade avançada do Office para a Microsoft 365 E3, Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="cd91c-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="cd91c-107">Este artigo faz parte de uma série maior de artigos sobre a [criptografia de mensagens do Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="cd91c-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="cd91c-108">Se uma mensagem foi criptografada usando a criptografia de mensagem avançada do Office 365 e você for um administrador de 365 da Microsoft, poderá revogar a mensagem sob determinadas condições.</span><span class="sxs-lookup"><span data-stu-id="cd91c-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="cd91c-109">Este artigo descreve as circunstâncias nas quais a revogação é possível e como fazê-la.</span><span class="sxs-lookup"><span data-stu-id="cd91c-109">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="cd91c-110">Emails criptografados que podem ser revogados</span><span class="sxs-lookup"><span data-stu-id="cd91c-110">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="cd91c-111">Você pode revogar emails criptografados se o destinatário recebeu um email criptografado com base em link e com marca.</span><span class="sxs-lookup"><span data-stu-id="cd91c-111">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="cd91c-112">Se o destinatário recebeu uma experiência embutida nativa em um cliente do Outlook com suporte, então você não poderá revogar esses.</span><span class="sxs-lookup"><span data-stu-id="cd91c-112">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke those.</span></span>

<span data-ttu-id="cd91c-113">Se um destinatário recebe uma experiência baseada em links ou uma experiência embutida depende do tipo de identidade do destinatário: o Office 365 e os destinatários da conta da Microsoft (por exemplo, usuários do outlook.com) recebem uma experiência embutida em clientes do Outlook com suporte.</span><span class="sxs-lookup"><span data-stu-id="cd91c-113">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="cd91c-114">Todos os outros tipos de destinatários, como destinatários do Gmail, obtêm uma experiência baseada em links.</span><span class="sxs-lookup"><span data-stu-id="cd91c-114">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="cd91c-115">Experiência de destinatário para emails criptografados revogados</span><span class="sxs-lookup"><span data-stu-id="cd91c-115">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="cd91c-116">Depois que um email é revogado, o destinatário recebe um erro quando acessa o email criptografado por meio do portal de criptografia de mensagem do Office 365: "a mensagem foi revogada pelo remetente".</span><span class="sxs-lookup"><span data-stu-id="cd91c-116">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![Captura de tela que mostra um email criptografado revogado.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="cd91c-118">Como revogar um email criptografado</span><span class="sxs-lookup"><span data-stu-id="cd91c-118">How to revoke an encrypted email</span></span>

<span data-ttu-id="cd91c-119">Os administradores do Microsoft 365 seguem estas etapas gerais para revogar um email criptografado qualificado:</span><span class="sxs-lookup"><span data-stu-id="cd91c-119">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="cd91c-120">Obtenha a ID da mensagem do email.</span><span class="sxs-lookup"><span data-stu-id="cd91c-120">Get the Message ID of the email.</span></span>
- <span data-ttu-id="cd91c-121">Verifique se é possível revogar a mensagem.</span><span class="sxs-lookup"><span data-stu-id="cd91c-121">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="cd91c-122">Revogar o email.</span><span class="sxs-lookup"><span data-stu-id="cd91c-122">Revoke the mail.</span></span>

<span data-ttu-id="cd91c-123">Continue lendo para obter instruções detalhadas para cada etapa no processo de revogação.</span><span class="sxs-lookup"><span data-stu-id="cd91c-123">Keep reading for in-depth instructions for each step in the revocation process.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="cd91c-124">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="cd91c-124">Step 1.</span></span> <span data-ttu-id="cd91c-125">Obter a ID da mensagem do email</span><span class="sxs-lookup"><span data-stu-id="cd91c-125">Obtain the Message ID of the email</span></span>

<span data-ttu-id="cd91c-126">Para que você possa revogar um email criptografado, colete a ID da mensagem do email.</span><span class="sxs-lookup"><span data-stu-id="cd91c-126">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="cd91c-127">Em geral, a MessageId é do formato:</span><span class="sxs-lookup"><span data-stu-id="cd91c-127">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="cd91c-128">Há várias maneiras de encontrar a ID da mensagem do email que você deseja revogar.</span><span class="sxs-lookup"><span data-stu-id="cd91c-128">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="cd91c-129">Esta seção descreve algumas opções, mas você pode usar qualquer método que forneça a ID.</span><span class="sxs-lookup"><span data-stu-id="cd91c-129">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="cd91c-130">Para identificar a ID de mensagem do email que você deseja revogar usando o rastreamento de mensagens no &amp; centro de conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="cd91c-130">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="cd91c-131">Procure o email por remetente ou destinatário usando o [rastreamento de novas mensagens no centro de conformidade e segurança &](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="cd91c-131">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="cd91c-132">Depois de localizar o email, selecione-o para exibir o painel de **detalhes de rastreamento de mensagens** .</span><span class="sxs-lookup"><span data-stu-id="cd91c-132">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="cd91c-133">Expanda **mais informações** para localizar a ID da mensagem.</span><span class="sxs-lookup"><span data-stu-id="cd91c-133">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="cd91c-134">Para identificar a ID de mensagem do email que você deseja revogar usando os relatórios de criptografia de mensagem do &amp; Office no centro de conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="cd91c-134">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="cd91c-135">No centro de &amp; conformidade de segurança, navegue até o **relatório de criptografia de mensagem**.</span><span class="sxs-lookup"><span data-stu-id="cd91c-135">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="cd91c-136">Para obter informações sobre este relatório, consulte [exibir relatórios de segurança de email &amp; no centro de conformidade de segurança](../security/office-365-security/view-email-security-reports.md).</span><span class="sxs-lookup"><span data-stu-id="cd91c-136">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="cd91c-137">Escolha a tabela **Exibir detalhes** e identifique a mensagem que você deseja revogar.</span><span class="sxs-lookup"><span data-stu-id="cd91c-137">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="cd91c-138">Clique duas vezes na mensagem para exibir os detalhes que incluem a ID da mensagem.</span><span class="sxs-lookup"><span data-stu-id="cd91c-138">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="cd91c-139">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="cd91c-139">Step 2.</span></span> <span data-ttu-id="cd91c-140">Verifique se o email é revogável</span><span class="sxs-lookup"><span data-stu-id="cd91c-140">Verify that the mail is revocable</span></span>

<span data-ttu-id="cd91c-141">Para verificar se você pode revogar uma mensagem, verifique se o campo status de revogação está visível no relatório de criptografia, na tabela **detalhes** no centro &amp; de conformidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="cd91c-141">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="cd91c-142">Para verificar se você pode revogar uma mensagem de email específica usando o Windows PowerShell, conclua estas etapas.</span><span class="sxs-lookup"><span data-stu-id="cd91c-142">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="cd91c-143">Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cd91c-143">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="cd91c-144">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="cd91c-144">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="cd91c-145">Execute o cmdlet Get-OMEMessageStatus da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="cd91c-145">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="cd91c-146">Este comando retorna o assunto da mensagem e se a mensagem é revogável.</span><span class="sxs-lookup"><span data-stu-id="cd91c-146">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="cd91c-147">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="cd91c-147">For example,</span></span>

     ```text
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="cd91c-148">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="cd91c-148">Step 3.</span></span> <span data-ttu-id="cd91c-149">Revogar o email</span><span class="sxs-lookup"><span data-stu-id="cd91c-149">Revoke the mail</span></span>

<span data-ttu-id="cd91c-150">Quando você souber a ID da mensagem do email que deseja revogar e tiver verificado que a mensagem é revogável, é possível revogar o email usando o centro de conformidade &amp; de segurança ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd91c-150">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="cd91c-151">Para revogar a mensagem usando o &amp; centro de conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="cd91c-151">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="cd91c-152">Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, conecte-se ao centro de conformidade do & de segurança.</span><span class="sxs-lookup"><span data-stu-id="cd91c-152">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="cd91c-153">No **relatório de criptografia**, na tabela **detalhes** da mensagem, escolha **revogar mensagem**.</span><span class="sxs-lookup"><span data-stu-id="cd91c-153">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="cd91c-154">Para revogar um email usando o Windows PowerShell, use o cmdlet Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="cd91c-154">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="cd91c-155">Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, [Conecte-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="cd91c-155">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="cd91c-156">Execute o cmdlet Set-OMEMessageRevocation da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="cd91c-156">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="cd91c-157">Para verificar se o email foi revogado, execute o cmdlet Get-OMEMessageStatus da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="cd91c-157">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="cd91c-158">Se a revogação tiver sido bem-sucedida, o cmdlet retornará o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="cd91c-158">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="cd91c-159">Mais informações sobre a criptografia de mensagem avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="cd91c-159">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="cd91c-160">Criptografia de Mensagem Avançada do 365 Office</span><span class="sxs-lookup"><span data-stu-id="cd91c-160">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="cd91c-161">Criptografia de mensagem avançada do Office 365-expiração de email</span><span class="sxs-lookup"><span data-stu-id="cd91c-161">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="cd91c-162">Descrição do serviço de conformidade e política de mensagens</span><span class="sxs-lookup"><span data-stu-id="cd91c-162">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
