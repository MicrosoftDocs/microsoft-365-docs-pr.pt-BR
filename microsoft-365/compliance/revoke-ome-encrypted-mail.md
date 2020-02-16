---
title: Revogar email criptografado pelo a Criptografia de Mensagem Avançada do Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/8/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Como administrador do Office 365, você pode revogar determinados emails que foram criptografados com a criptografia de mensagem avançada do Office 365.
ms.openlocfilehash: 6cbe0704d6e84282d71c37c72a45712c30f3ac61
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42070028"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="d6805-103">Revogar email criptografado pelo a Criptografia de Mensagem Avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="d6805-103">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="d6805-104">A revogação de emails é oferecida como parte da criptografia de mensagem avançada do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d6805-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="d6805-105">O Office 365 Advanced Message Encryption está incluído no [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 e5, Microsoft 365 E5 (precificação de pessoas sem fins lucrativos), Office 365 Enterprise E5 (precificação de pessoas sem fins lucrativos) e Office 365 Education a5.</span><span class="sxs-lookup"><span data-stu-id="d6805-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="d6805-106">Se sua organização tem uma assinatura que não inclui a criptografia de mensagem avançada do Office 365, você pode comprá-la com o complemento de SKU de conformidade da Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (precificação de pessoas sem fins lucrativos) ou o Office 365 Advanced Complemento de SKU de conformidade para o Microsoft 365 E3, Microsoft 365 E3 (preço de equipe sem fins lucrativos) ou SKUs do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d6805-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="d6805-107">Este artigo faz parte de uma série maior de artigos sobre a [criptografia de mensagens do Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="d6805-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="d6805-108">Se uma mensagem foi criptografada usando a criptografia de mensagem avançada do Office 365 e você for um administrador do Office 365, poderá revogar a mensagem sob determinadas condições.</span><span class="sxs-lookup"><span data-stu-id="d6805-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are an Office 365 admin, you can do revoke the message under certain conditions.</span></span> <span data-ttu-id="d6805-109">Este artigo descreve as circunstâncias nas quais a revogação é possível e como fazê-la.</span><span class="sxs-lookup"><span data-stu-id="d6805-109">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="d6805-110">Emails criptografados que podem ser revogados</span><span class="sxs-lookup"><span data-stu-id="d6805-110">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="d6805-111">Você pode revogar emails criptografados se o destinatário recebeu um email criptografado com base em link e com marca.</span><span class="sxs-lookup"><span data-stu-id="d6805-111">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="d6805-112">Se o destinatário recebeu uma experiência interna nativa em um cliente do Outlook com suporte, esses emails não podem ser revogados.</span><span class="sxs-lookup"><span data-stu-id="d6805-112">If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="d6805-113">Se um destinatário recebe uma experiência baseada em links ou uma experiência embutida depende do tipo de identidade do destinatário: o Office 365 e os destinatários da conta da Microsoft (por exemplo, usuários do outlook.com) recebem uma experiência embutida em clientes do Outlook com suporte.</span><span class="sxs-lookup"><span data-stu-id="d6805-113">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="d6805-114">Todos os outros tipos de destinatários, como destinatários do Gmail, obtêm uma experiência baseada em links.</span><span class="sxs-lookup"><span data-stu-id="d6805-114">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="d6805-115">Experiência de destinatário para emails criptografados revogados</span><span class="sxs-lookup"><span data-stu-id="d6805-115">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="d6805-116">Depois que um email é revogado, o destinatário recebe um erro quando acessa o email criptografado por meio do portal de criptografia de mensagem do Office 365: "a mensagem foi revogada pelo remetente".</span><span class="sxs-lookup"><span data-stu-id="d6805-116">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![Captura de tela que mostra um email criptografado revogado.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="d6805-118">Como revogar um email criptografado</span><span class="sxs-lookup"><span data-stu-id="d6805-118">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="d6805-119">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="d6805-119">Step 1.</span></span> <span data-ttu-id="d6805-120">Obter a ID da mensagem do email</span><span class="sxs-lookup"><span data-stu-id="d6805-120">Obtain the Message ID of the email</span></span>

<span data-ttu-id="d6805-121">Antes de poder revogar um email criptografado, você coleta a ID da mensagem do email.</span><span class="sxs-lookup"><span data-stu-id="d6805-121">Before you can revoke an encrypted mail you gather the Message ID of the mail.</span></span> <span data-ttu-id="d6805-122">Em geral, a MessageId é do formato:</span><span class="sxs-lookup"><span data-stu-id="d6805-122">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="d6805-123">Há várias maneiras de encontrar a ID da mensagem do email que você deseja revogar.</span><span class="sxs-lookup"><span data-stu-id="d6805-123">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="d6805-124">Esta seção descreve algumas opções, mas você pode usar qualquer método que forneça a ID.</span><span class="sxs-lookup"><span data-stu-id="d6805-124">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="d6805-125">Para identificar a ID de mensagem do email que você deseja revogar usando o rastreamento de mensagens no &amp; centro de conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="d6805-125">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="d6805-126">Procure o email por remetente ou destinatário usando o [rastreamento de novas mensagens no centro de conformidade & segurança do Office 365](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="d6805-126">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="d6805-127">Depois de localizar o email, selecione-o para exibir o painel de **detalhes de rastreamento de mensagens** .</span><span class="sxs-lookup"><span data-stu-id="d6805-127">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="d6805-128">Expanda **mais informações** para localizar a ID da mensagem.</span><span class="sxs-lookup"><span data-stu-id="d6805-128">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="d6805-129">Para identificar a ID de mensagem do email que você deseja revogar usando os relatórios de criptografia de mensagem do &amp; Office no centro de conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="d6805-129">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="d6805-130">No centro de &amp; conformidade de segurança, navegue até o **relatório de criptografia de mensagem**.</span><span class="sxs-lookup"><span data-stu-id="d6805-130">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="d6805-131">Para obter informações sobre este relatório, consulte [exibir relatórios de segurança de email &amp; no centro de conformidade de segurança](../security/office-365-security/view-email-security-reports.md).</span><span class="sxs-lookup"><span data-stu-id="d6805-131">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="d6805-132">Escolha a tabela **Exibir detalhes** e identifique a mensagem que você deseja revogar.</span><span class="sxs-lookup"><span data-stu-id="d6805-132">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="d6805-133">Clique duas vezes na mensagem para exibir os detalhes que incluem a ID da mensagem.</span><span class="sxs-lookup"><span data-stu-id="d6805-133">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="d6805-134">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="d6805-134">Step 2.</span></span> <span data-ttu-id="d6805-135">Verifique se o email é revogável</span><span class="sxs-lookup"><span data-stu-id="d6805-135">Verify that the mail is revocable</span></span>

<span data-ttu-id="d6805-136">Para verificar se você pode revogar uma mensagem, verifique se o campo status de revogação está visível no relatório de criptografia, na tabela **detalhes** no centro &amp; de conformidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="d6805-136">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="d6805-137">Para verificar se você pode revogar uma mensagem de email específica usando o Windows PowerShell, conclua estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d6805-137">To verify whether you can revoke a particular email message by using Windows Powershell, complete these steps.</span></span>

1. <span data-ttu-id="d6805-138">Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização do Office 365, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d6805-138">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="d6805-139">Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="d6805-139">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="d6805-140">Execute o cmdlet Get-OMEMessageStatus da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d6805-140">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="d6805-141">Isso retorna o assunto da mensagem e se a mensagem é revogável.</span><span class="sxs-lookup"><span data-stu-id="d6805-141">This returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="d6805-142">Por exemplo,</span><span class="sxs-lookup"><span data-stu-id="d6805-142">For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="d6805-143">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="d6805-143">Step 3.</span></span> <span data-ttu-id="d6805-144">Revogar o email</span><span class="sxs-lookup"><span data-stu-id="d6805-144">Revoke the mail</span></span>

<span data-ttu-id="d6805-145">Quando você souber a ID da mensagem do email que deseja revogar e tiver verificado que a mensagem é revogável, é possível revogar o email usando o centro de conformidade &amp; de segurança ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6805-145">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows Powershell.</span></span>

<span data-ttu-id="d6805-146">Para revogar a mensagem usando o &amp; centro de conformidade de segurança</span><span class="sxs-lookup"><span data-stu-id="d6805-146">To revoke the message using the Security &amp; Compliance Center</span></span>

<span data-ttu-id="d6805-147">Para revogar o email no centro &amp; de conformidade de segurança, no relatório de criptografia, na tabela **detalhes** da mensagem, escolha **revogar mensagem**.</span><span class="sxs-lookup"><span data-stu-id="d6805-147">To revoke the email in the Security &amp; Compliance Center, in the Encryption report, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="d6805-148">Você pode revogar um email usando o Windows PowerShell usando o cmdlet Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="d6805-148">You can revoke an email by using Windows Powershell by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="d6805-149">[Conectar-se ao Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="d6805-149">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="d6805-150">Execute o cmdlet Set-OMEMessageRevocation da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d6805-150">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="d6805-151">Para verificar se o email foi revogado, execute o cmdlet Get-OMEMessageStatus da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="d6805-151">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="d6805-152">Se a revogação tiver sido bem-sucedida, o cmdlet retornará o seguinte resultado:</span><span class="sxs-lookup"><span data-stu-id="d6805-152">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="d6805-153">Mais informações sobre a criptografia de mensagem avançada do Office 365</span><span class="sxs-lookup"><span data-stu-id="d6805-153">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="d6805-154">Criptografia de Mensagem Avançada do 365 Office</span><span class="sxs-lookup"><span data-stu-id="d6805-154">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="d6805-155">Criptografia de mensagem avançada do Office 365-expiração de email</span><span class="sxs-lookup"><span data-stu-id="d6805-155">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="d6805-156">Descrição do serviço de conformidade e política de mensagens</span><span class="sxs-lookup"><span data-stu-id="d6805-156">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
