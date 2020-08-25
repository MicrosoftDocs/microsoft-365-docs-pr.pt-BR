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
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>Revogar emails criptografados por criptografia de mensagem avançada

A revogação de emails é oferecida como parte da criptografia de mensagem avançada do Office 365. O Office 365 Advanced Message Encryption está incluído no [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 e5, Microsoft 365 E5 (precificação de pessoas sem fins lucrativos), Office 365 Enterprise E5 (precificação de pessoas sem fins lucrativos) e Office 365 Education a5. Se sua organização tem uma assinatura que não inclui a criptografia de mensagem avançada do Office 365, você pode comprá-la com o complemento de SKU de conformidade da Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (preço de equipe sem fins lucrativos) ou o complemento avançado de SKU de conformidade avançada do Office para a Microsoft 365 E3, Microsoft 365 E3

Este artigo faz parte de uma série maior de artigos sobre a [criptografia de mensagens do Office 365](ome.md).

Se uma mensagem foi criptografada usando a criptografia de mensagem avançada do Office 365 e você for um administrador de 365 da Microsoft ou se for o remetente da mensagem, você poderá revogar a mensagem sob determinadas condições. Os administradores revogam mensagens usando o PowerShell. Como remetente, você revoga uma mensagem que enviou diretamente do Outlook na Web. Este artigo descreve as circunstâncias nas quais a revogação é possível e como fazê-la.
  
## <a name="encrypted-emails-that-you-can-revoke"></a>Emails criptografados que podem ser revogados

Os administradores e os remetentes de mensagens podem revogar emails criptografados se o destinatário recebeu um email criptografado com base em link e com marca. Se o destinatário recebeu uma experiência interna nativa em um cliente do Outlook com suporte, então você não poderá revogar a mensagem.

Se um destinatário recebe uma experiência baseada em links ou uma experiência embutida depende do tipo de identidade do destinatário: o Office 365 e os destinatários da conta da Microsoft (por exemplo, usuários do outlook.com) recebem uma experiência embutida em clientes do Outlook com suporte. Todos os outros tipos de destinatários, como os destinatários do Gmail e Yahoo, obtêm uma experiência baseada em links.

Os administradores e remetentes de mensagens podem revogar mensagens criptografadas usando a criptografia aplicada diretamente do Outlook na Web. Por exemplo, mensagens criptografadas com a opção somente criptografar.

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Captura de tela mostrando a opção somente criptografia no Outlook na Web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>Experiência de destinatário para emails criptografados revogados

Depois que um email é revogado, o destinatário recebe um erro quando acessa o email criptografado por meio do portal de criptografia de mensagem do Office 365: "a mensagem foi revogada pelo remetente".

![Captura de tela que mostra um email criptografado revogado.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>Como revogar uma mensagem criptografada que você enviou

Para revogar uma mensagem criptografada que você enviou, conclua estas etapas

1. No Outlook na Web, na pasta **enviado** , procure a mensagem que você deseja revogar.

   Se o email for revogável, você verá o link "remover acesso externo" na parte superior da mensagem.

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Captura de tela mostrando mensagens criptografadas que você deseja revogar no Outlook na Web.":::

2. Clique em **remover o acesso externo** para revogar a mensagem.

   A mensagem mostra que o status é revogado.

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Captura de tela mostrando a mensagem criptografada revogada no Outlook na Web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>Como revogar uma mensagem criptografada como administrador

Os administradores do Microsoft 365 seguem estas etapas gerais para revogar um email criptografado qualificado:

- Obtenha a ID da mensagem do email.
- Verifique se é possível revogar a mensagem.
- Revogar o email.

### <a name="step-1-obtain-the-message-id-of-the-email"></a>Etapa 1. Obter a ID da mensagem do email

Para que você possa revogar um email criptografado, colete a ID da mensagem do email. Em geral, a MessageId é do formato:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

Há várias maneiras de encontrar a ID da mensagem do email que você deseja revogar. Esta seção descreve algumas opções, mas você pode usar qualquer método que forneça a ID.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>Para identificar a ID de mensagem do email que você deseja revogar usando o rastreamento de mensagens no &amp; centro de conformidade de segurança

1. Procure o email por remetente ou destinatário usando o [rastreamento de novas mensagens no centro de conformidade e segurança &](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).

2. Depois de localizar o email, selecione-o para exibir o painel de **detalhes de rastreamento de mensagens** . Expanda **mais informações** para localizar a ID da mensagem.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>Para identificar a ID de mensagem do email que você deseja revogar usando os relatórios de criptografia de mensagem do Office no centro de conformidade de segurança &amp;

1. No centro de &amp; conformidade de segurança, navegue até o **relatório de criptografia de mensagem**. Para obter informações sobre este relatório, consulte [exibir relatórios de segurança de email no &amp; centro de conformidade de segurança](../security/office-365-security/view-email-security-reports.md).

2. Escolha a tabela **Exibir detalhes** e identifique a mensagem que você deseja revogar.

3. Clique duas vezes na mensagem para exibir os detalhes que incluem a ID da mensagem.

### <a name="step-2-verify-that-the-mail-is-revocable"></a>Etapa 2. Verifique se o email é revogável

Para verificar se você pode revogar uma mensagem, verifique se o campo status de revogação está visível no relatório de criptografia, na tabela **detalhes** no centro de conformidade de segurança &amp; .

Para verificar se você pode revogar uma mensagem de email específica usando o Windows PowerShell, conclua estas etapas.

1. Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, inicie uma sessão do Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).

2. Execute o cmdlet Get-OMEMessageStatus da seguinte maneira:

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   Este comando retorna o assunto da mensagem e se a mensagem é revogável. Por exemplo,

     ```text
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a>Etapa 3. Revogar o email

Quando você souber a ID da mensagem do email que deseja revogar e tiver verificado que a mensagem é revogável, é possível revogar o email usando o centro de conformidade de segurança &amp; ou o Windows PowerShell.

Para revogar a mensagem usando o &amp; centro de conformidade de segurança

1. Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, conecte-se ao centro de conformidade do & de segurança.

2. No **relatório de criptografia**, na tabela **detalhes** da mensagem, escolha **revogar mensagem**.

Para revogar um email usando o Windows PowerShell, use o cmdlet Set-OMEMessageRevocation.

1. Usando uma conta corporativa ou de estudante que tenha permissões de administrador global em sua organização, [Conecte-se ao PowerShell do Exchange Online](https://aka.ms/exopowershell).

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

- [Criptografia de Mensagem Avançada do 365 Office](ome-advanced-message-encryption.md)

- [Criptografia de mensagem avançada do Office 365-expiração de email](ome-advanced-expiration.md)

- [Descrição do serviço de conformidade e política de mensagens](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
