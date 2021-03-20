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
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>Revogar emails criptografados pela Criptografia Avançada de Mensagens

A revogação de email é oferecida como parte da Criptografia Avançada de Mensagens do Office 365. A Criptografia Avançada de Mensagens do Office 365 está incluída no [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), no Office 365 E5, no Microsoft 365 E5 (Preços de Funcionários sem fins lucrativos), no Office 365 Enterprise E5 (Preços de Funcionários sem fins lucrativos) e no Office 365 Education A5. Se sua organização tiver uma assinatura que não inclua a Criptografia Avançada de Mensagens do Office 365, você pode compra-lo com o complemento SKU de Conformidade do Microsoft 365 E5 para o Microsoft 365 E3, o Microsoft 365 E3 (Preços de Equipe sem fins lucrativos) ou o complemento SKU de Conformidade Avançada do Office 365 para o Microsoft 365 E3, o Microsoft 365 E3 (Preços da Equipe Sem Fins Lucrativos) ou o SKUs do Office 365.

Este artigo faz parte de uma série maior de artigos sobre a Criptografia de Mensagens do [Office 365.](ome.md)

Se uma mensagem foi criptografada usando a Criptografia Avançada de Mensagens do Office 365 e você é um administrador do Microsoft 365 ou você é o remetente da mensagem, você pode revogar a mensagem em determinadas condições. Os administradores revogam mensagens usando o PowerShell. Como remetente, você revoga uma mensagem enviada diretamente do Outlook na Web. Este artigo descreve as circunstâncias em que a revogação é possível e como fazê-la.
  
## <a name="encrypted-emails-that-you-can-revoke"></a>Emails criptografados que você pode revogar

Os administradores e os destinatários de mensagens podem revogar emails criptografados se o destinatário recebeu um email criptografado baseado em link com a marca. Se o destinatário recebeu uma experiência em linha nativa em um cliente do Outlook com suporte, você não pode revogar a mensagem.

Se um destinatário recebe uma experiência baseada em link ou uma experiência em linha depende do tipo de identidade do destinatário: os destinatários de contas do Office 365 e da Microsoft (por exemplo, outlook.com usuários) recebem uma experiência em linha nos clientes do Outlook com suporte. Todos os outros tipos de destinatários, como destinatários do Gmail e do Yahoo, obterão uma experiência baseada em link.

Os administradores e os envios de mensagens podem revogar mensagens criptografadas usando criptografia aplicada diretamente do Outlook na Web. Por exemplo, mensagens criptografadas com a opção Criptografar Somente.

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Captura de tela mostrando a opção Criptografar Somente no Outlook na Web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>Experiência do destinatário para emails criptografados revogados

Depois que um email é revogado, o destinatário recebe um erro ao acessar o email criptografado por meio do portal de Criptografia de Mensagens do Office 365: "A mensagem foi revogada pelo remetente".

![Captura de tela que mostra um email criptografado revogado.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>Como revogar uma mensagem criptografada que você enviou

Você pode revogar um email enviado para um único destinatário que usa uma conta social como gmail.com ou yahoo.com. Em outras palavras, você pode revogar um email enviado para um único destinatário que recebeu a experiência baseada em link.

Não é possível revogar um email enviado a um destinatário que usa uma conta de estudante ou de trabalho do Office 365 ou do Microsoft 365 ou de um usuário que usa uma conta da Microsoft, por exemplo, uma conta outlook.com. 

Para revogar uma mensagem criptografada enviada, conclua estas etapas

1. No Outlook na Web, em sua **pasta Enviada,** navegue até a mensagem que você deseja revogar.

   Se o email for revogado, você verá o link "Remover acesso externo" na parte superior da mensagem.

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Captura de tela mostrando emails criptografados que você deseja revogar no Outlook na Web.":::

2. Clique **em Remover acesso externo** para revogar a mensagem.

   A mensagem mostra que seu status foi revogado.

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Captura de tela mostrando a mensagem criptografada revogada no Outlook na Web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>Como revogar uma mensagem criptografada como administrador

Os administradores do Microsoft 365 seguem estas etapas gerais para revogar um email criptografado qualificado:

- Obter a ID da mensagem do email.
- Verifique se você pode revogar a mensagem.
- Revogar o email.

### <a name="step-1-obtain-the-message-id-of-the-email"></a>Etapa 1. Obter a ID da mensagem do email

Antes de revogar um email criptografado, reúna a ID da mensagem do email. MessageId geralmente é do formato:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

Há várias maneiras de encontrar a ID da mensagem do email que você deseja revogar. Esta seção descreve algumas opções, mas você pode usar qualquer método que fornece a ID.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>Para identificar a ID da mensagem do email que você deseja revogar usando o Rastreamento de Mensagens no Centro &amp; de Conformidade de Segurança

1. Pesquise o email por remetente ou destinatário usando Novo Rastreamento de Mensagens no Centro de [Conformidade & Segurança.](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)

2. Depois de localizar o email, selecione-o para trazer o painel Detalhes de **rastreamento de** mensagens. Expanda **Mais Informações** para localizar a ID da Mensagem.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>Para identificar a ID da mensagem do email que você deseja revogar usando relatórios de Criptografia de Mensagens do Office no Centro &amp; de Conformidade de Segurança

1. No Centro de &amp; Conformidade de Segurança, navegue até o **relatório de criptografia de mensagem**. Para obter informações sobre este relatório, consulte [Exibir relatórios de segurança de email no Centro de Conformidade de &amp; Segurança.](../security/office-365-security/view-email-security-reports.md)

2. Escolha a **tabela Exibir detalhes** e identifique a mensagem que você deseja revogar.

3. Clique duas vezes na mensagem para exibir detalhes que incluem a ID da mensagem.

### <a name="step-2-verify-that-the-mail-is-revocable"></a>Etapa 2. Verifique se o email é revogado

Para verificar se você pode revogar uma mensagem, verifique se o campo Status  de Revogação está visível no relatório de criptografia, na tabela Detalhes no Centro de Conformidade &amp; de Segurança.

Para verificar se você pode revogar uma mensagem de email específica usando Windows PowerShell, conclua estas etapas.

1. Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, inicie uma sessão Windows PowerShell e conecte-se ao Exchange Online. Para obter instruções, confira [Conectar-se ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

2. Execute o Get-OMEMessageStatus cmdlet da seguinte forma:

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   Este comando retorna o assunto da mensagem e se a mensagem é revogada. Por exemplo,

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a>Etapa 3. Revogar o email

Depois de saber a ID da mensagem do email que deseja revogar e verificar se a mensagem é revogada, você pode revogar o email usando o Centro de Conformidade de Segurança ou &amp; Windows PowerShell.

Para revogar a mensagem usando o Centro de &amp; Conformidade e Segurança

1. Usando uma conta de estudante ou de trabalho que tenha permissões globais de administrador em sua organização, conecte-se ao Centro de Conformidade & Segurança.

2. No relatório **criptografia**, na tabela **Detalhes** da mensagem, escolha **Revogar mensagem**.

Para revogar um email usando o Windows PowerShell, use o cmdlet Set-OMEMessageRevocation.

1. Usando uma conta de trabalho ou de estudante que tenha permissões globais de administrador em sua organização, [Conecte-se ao PowerShell do Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Execute o Set-OMEMessageRevocation cmdlet da seguinte forma:

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. Para verificar se o email foi revogado, execute o cmdlet Get-OMEMessageStatus da seguinte forma:

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    Se a revogação tiver sido bem-sucedida, o cmdlet retornará o seguinte resultado:  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Mais informações sobre a Criptografia Avançada de Mensagens do Office 365

- [Criptografia de Mensagem Avançada do 365 Office](ome-advanced-message-encryption.md)

- [Criptografia avançada de mensagens do Office 365 - expiração de email](ome-advanced-expiration.md)

- [Descrição do serviço de conformidade e política de mensagem](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)