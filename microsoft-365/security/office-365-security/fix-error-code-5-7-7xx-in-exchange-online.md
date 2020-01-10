---
title: Corrigir problemas de entrega de email com o código de erro 5.7.7 XX no Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Saiba como corrigir problemas de email com o código de erro 5.7.7 XX no Exchange Online (locatário bloqueado pelo envio de emails).
ms.openlocfilehash: 4e82df78cfb83865142defb14cec0841ab29ba95
ms.sourcegitcommit: 55cb11c2475f40d0f1c64cf45446bf383d7d5f86
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002971"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a>Corrigir problemas de entrega de email com o código de erro 5.7.7 XX no Exchange Online

Este tópico descreve o que você pode fazer se vir o código de status 550 5.7.7 XX em uma notificação de falha na entrega (também conhecida como NDR, mensagem de devolução, notificação de status de entrega ou DSN). Você verá essa notificação automatizada quando seu locatário estiver restrito ao envio de emails de uma forma ou de outra. Esses códigos de erro geralmente serão fornecidos como 705 ou 750.

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a>5.7.705: o locatário excedeu a restrição de limite: o que você precisa saber

Depois que os usuários (coletivamente, como a organização) enviam uma determinada quantidade de emails suspeitos através do serviço, todos os usuários podem ser impedidos de enviar emails até que o problema seja corrigido. Isso geralmente é o resultado de um compromisso (mais comum) ou o envio de muitas mensagens em massa. Os usuários receberão uma notificação de falha na entrega:

`550 5.7.705 Access denied, tenant has exceeded threshold`

Em casos raros, isso também pode acontecer se você renovar sua assinatura após ela já ter expirado. Leva tempo para o serviço sincronizar as informações da nova assinatura (normalmente, não mais de um dia), mas sua organização pode ser impedida de enviar emails enquanto isso. A melhor maneira de evitar isso é garantir que sua assinatura não expire.

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a>5.7.750: restrição de email de domínio não registrado: o que você precisa saber

O Office 365 permite que os locatários transmitam algumas mensagens por meio do Exchange Online Protection (EOP). Por exemplo:

- Uma caixa de correio do Office 365 recebe email de um remetente externo. O encaminhamento de emails é configurado na caixa de correio do Office 365, portanto, a mensagem retorna ao endereço de email externo do usuário. Este cenário é mais comum em ambientes educacionais em que os alunos querem usar suas contas de email pessoais para exibir mensagens relacionadas à escola.

- Ambientes híbridos que têm servidores de email locais que enviam emails de saída por meio de EOP.

### <a name="problems-with-unregistered-domains"></a>Problemas com domínios não registrados

O problema ocorre quando os servidores de email no local estão comprometidos retransmitendo um grande volume de spam por meio do EOP. Em quase todos os casos, os conectores são configurados corretamente, mas o email é enviado de domínios não registrados (também conhecidos como desprovisionados). O Office 365 permite uma quantidade razoável de emails de domínios não registrados, mas você deve configurar todos os domínios que você usa para enviar email como um domínio aceito.

Após o comprometimento, os locatários serão impedidos de enviar emails de saída para domínios não registrados. Os usuários receberão uma notificação de falha na entrega:

`550 5.7.750 Service unavailable. Client blocked from sending from unregistered domains`

## <a name="unblocking-tenant-in-order-to-send-again"></a>Desbloqueando o locatário para enviar novamente

Há várias coisas que você precisa fazer se seu locatário estiver bloqueado de enviar emails:

1. Altere a senha das suas contas de administrador. Se um locatário estiver bloqueado para envio, é mais provável que uma conta de administrador tenha sido comprometida. Alterar senhas é a primeira etapa para evitar que o invasor faça mais danos.

2. [Habilitar a MFA](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) de todos os administradores na sua organização do Office 365.

3. Verifique se todos os seus domínios de email estão registrados. Para obter mais informações, consulte [Adicionar um domínio ao Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain) e [gerenciar domínios aceitos no Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

4. Procure por [conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)incomuns. Os atores mal-intencionados geralmente criarão novos conectores de entrada na sua organização do Office 365 para enviar spam. Para exibir os conectores existentes, consulte [Validate Connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors).

5. Verifique se há usuários comprometidos conforme descrito em [respondendo a uma conta de email comprometida no Office 365](responding-to-a-compromised-email-account.md).

6. Bloqueie seus servidores de email locais e verifique se eles não estão comprometidos.

   > [!TIP]
   > Há vários fatores aqui, especialmente se você estiver usando servidores de terceiros. Independentemente disso, você precisará verificar se seu email de saída não inclui spam.

7. Ligue para o suporte da Microsoft e peça para que o locatário não seja bloqueado para enviar emails novamente. O código de erro é útil, mas você precisará provar que seu ambiente foi protegido e que não é capaz de enviar spam. Para abrir um caso de suporte, confira [contatar o suporte para produtos de negócios-ajuda para administradores](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

## <a name="for-more-information"></a>Para obter mais informações

[Proteção antispam de emails do Office 365](anti-spam-protection.md)

[Orientação de email em massa na seção limites de envio da descrição do serviço do Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)

[Notificações de falha na entrega de email no Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/non-delivery-reports-in-exchange-online)

[Configurar o encaminhamento de email para uma caixa de correio](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[Como configurar um dispositivo multifuncional ou aplicativo para enviar email usando o Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/how-to-set-up-a-multifunction-device-or-application-to-send-email-using-office-3)

[Gerenciar domínios aceitos no Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
