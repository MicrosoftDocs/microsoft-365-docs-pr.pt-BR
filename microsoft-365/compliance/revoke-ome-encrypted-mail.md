---
title: Revogar emails criptografados pela criptografia de mensagem avançada do Office 365
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Como administrador do Office 365, você pode revogar determinados emails que foram criptografados com a criptografia de mensagem avançada do Office 365.
ms.openlocfilehash: e55129f68c7add589bd973b36f069d7cdbf631cf
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37073179"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a>Revogar emails criptografados pela criptografia de mensagem avançada do Office 365

A revogação de emails é oferecida como parte da criptografia de mensagem avançada do Office 365. A criptografia de mensagem avançada do Office 365 está disponível na parte superior da criptografia de mensagem do Office 365 em determinadas assinaturas. A criptografia avançada de mensagens está incluída no [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), no Office 365 Enterprise E5 e no Office 365 Education a5. Se sua organização tiver uma assinatura do Office 365 que não inclua a criptografia de mensagem avançada do Office 365, você poderá comprar a criptografia de mensagem avançada como um complemento com a conformidade E5 do SKU de conformidade avançada.

Este artigo faz parte de uma série maior de artigos sobre a [criptografia de mensagens do Office 365](ome.md).

Se uma mensagem foi criptografada usando a criptografia de mensagem avançada do Office 365 e você for um administrador do Office 365, poderá revogar a mensagem sob determinadas condições. Este artigo descreve as circunstâncias nas quais a revogação é possível e como fazê-la.
  
## <a name="encrypted-emails-that-you-can-revoke"></a>Emails criptografados que podem ser revogados

Você pode revogar emails criptografados se o destinatário recebeu um email criptografado com base em link e com marca. Se o destinatário recebeu uma experiência interna nativa em um cliente do Outlook com suporte, esses emails não podem ser revogados.

Se um destinatário recebe uma experiência baseada em links ou uma experiência embutida depende do tipo de identidade do destinatário: o Office 365 e os destinatários da conta da Microsoft (por exemplo, usuários do outlook.com) recebem uma experiência embutida em clientes do Outlook com suporte. Todos os outros tipos de destinatários, como destinatários do Gmail, obtêm uma experiência baseada em links.

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>Experiência de destinatário para emails criptografados revogados

Depois que um email é revogado, o destinatário recebe um erro quando acessa o email criptografado por meio do portal de criptografia de mensagem do Office 365: "a mensagem foi revogada pelo remetente".

![Captura de tela que mostra um email criptografado revogado.](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a>Como revogar um email criptografado

### <a name="step-1-obtain-the-message-id-of-the-email"></a>Etapa 1. Obter a ID da mensagem do email

Antes de poder revogar um email criptografado, você coleta a ID da mensagem do email. Em geral, a MessageId é do formato:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

Há várias maneiras de encontrar a ID da mensagem do email que você deseja revogar. Esta seção descreve algumas opções, mas você pode usar qualquer método que forneça a ID.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>Para identificar a ID de mensagem do email que você deseja revogar usando o rastreamento de mensagens no &amp; centro de conformidade de segurança

1. Procure o email por remetente ou destinatário usando o [rastreamento de novas mensagens no centro de conformidade & segurança do Office 365](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).

2. Depois de localizar o email, selecione-o para exibir o painel de **detalhes de rastreamento de mensagens** . Expanda **mais informações** para localizar a ID da mensagem.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>Para identificar a ID de mensagem do email que você deseja revogar usando os relatórios de criptografia de mensagem do &amp; Office no centro de conformidade de segurança

1. No centro de &amp; conformidade de segurança, navegue até o **relatório de criptografia de mensagem**. Para obter informações sobre este relatório, consulte [exibir relatórios de segurança de email &amp; no centro de conformidade de segurança](view-email-security-reports.md).

2. Escolha a tabela **Exibir detalhes** e identifique a mensagem que você deseja revogar.

3. Clique duas vezes na mensagem para exibir os detalhes que incluem a ID da mensagem.

### <a name="step-2-verify-that-the-mail-is-revocable"></a>Etapa 2. Verifique se o email é revogável

Para verificar se você pode revogar uma mensagem, verifique se o campo status de revogação está visível no relatório de criptografia, na tabela **detalhes** no centro &amp; de conformidade de segurança.

Para verificar se você pode revogar uma mensagem de email específica usando o Windows PowerShell, conclua estas etapas.

1. Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização do Office 365, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, consulte [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Execute o cmdlet Get-OMEMessageStatus da seguinte maneira:

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   Isso retorna o assunto da mensagem e se a mensagem é revogável. For example,

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a>Etapa 3. Revogar o email

Quando você souber a ID da mensagem do email que deseja revogar e tiver verificado que a mensagem é revogável, é possível revogar o email usando o centro de conformidade &amp; de segurança ou o Windows PowerShell.

Para revogar a mensagem usando o &amp; centro de conformidade de segurança

Para revogar o email no centro &amp; de conformidade de segurança, no relatório de criptografia, na tabela **detalhes** da mensagem, escolha **revogar mensagem**.

Você pode revogar um email usando o Windows PowerShell usando o cmdlet Set-OMEMessageRevocation.

1. [Conectar-se ao Exchange Online PowerShell](https://aka.ms/exopowershell).

2. Execute o cmdlet Set-OMEMessageRevocation da seguinte maneira:

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. Para verificar se o email foi revogado, execute o cmdlet Get-OMEMessageStatus da seguinte maneira:

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    Se a revogação tiver sido bem-sucedida, o cmdlet retornará o seguinte resultado:  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Mais informações sobre a criptografia de mensagem avançada do Office 365

- [Criptografia de mensagem avançada do Office 365](ome-advanced-message-encryption.md)

- [Criptografia de mensagem avançada do Office 365-expiração de email](ome-advanced-expiration.md)

- [Descrição do serviço de conformidade e política de mensagens](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
