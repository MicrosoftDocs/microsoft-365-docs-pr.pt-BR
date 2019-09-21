---
title: Corrigir problemas de entrega de email com o código de erro 5.7.7 XX no Exchange Online
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/11/2019
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
ms.openlocfilehash: d55bc1f8a051a7f9932528a75aac8f1efa18911c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072474"
---
# <a name="fix-email-delivery-issues-for-error-code-577xx-in-exchange-online"></a>Corrigir problemas de entrega de email com o código de erro 5.7.7 XX no Exchange Online

Este tópico descreve o que você pode fazer se vir o código de status 550 5.7.7 XX em uma notificação de falha na entrega (também conhecida como NDR, mensagem de devolução, notificação de status de entrega ou DSN). Você verá essa notificação automatizada quando seu locatário estiver restrito ao envio de emails de uma forma ou de outra. Esses códigos de erro geralmente serão fornecidos como 705 ou 750.

## <a name="57705-tenant-has-exceeded-threshold-restriction-what-you-need-to-know"></a>5.7.705: o locatário excedeu a restrição de limite: o que você precisa saber

Os remetentes internos podem ver essa notificação sempre que você tenta enviar emails se o locatário foi comprometido. Isso geralmente occus quando a maior parte do tráfego de seu locatário foi detectada como suspeita e resultou em uma proibição na capacidade de envio para o locatário. Isso também pode ocorrer se seus usuários enviam uma grande quantidade de emails em massa do Office 365. Conforme mencionado na descrição do serviço, os clientes do Exchange Online que precisam enviar emails comerciais em massa legítimos (por exemplo, boletins informativos para clientes) devem usar provedores de terceiros especializados nesses serviços.

Depois que os usuários coletivamente, como um locatário, enviarem uma determinada quantidade de mensagens suspeitas pelo serviço, todos os usuários podem ser impedidos de enviar qualquer email até que o problema seja corrigido. Os usuários receberão uma NDR (notificação de falha na entrega) que diz:

- 550 5.7.705 acesso negado, o locatário excedeu o limite

## <a name="57750-unregistered-domain-email-restriction-what-you-need-to-know"></a>5.7.750: restrição de email de domínio não registrado: o que você precisa saber

O Office 365 permite que os locatários transmitam algumas mensagens por meio do Exchange Online Protection (EOP). Um exemplo com suporte é quando os usuários têm uma caixa de correio do Office 365 e alguém externo envia esses emails, mas o encaminhamento de emails é configurado para que ele volte para a caixa de correio externa do usuário. Isso é mais comum em ambientes educacionais em que os alunos querem aproveitar sua interface de email pessoal, mas ainda receber emails relacionados à escola. Outro exemplo é quando os clientes estão em um cenário híbrido e têm servidores locais que enviam emails do EOP.

### <a name="problems-with-unregistered-domains"></a>Problemas com domínios não registrados

O problema ocorre quando os servidores locais são comprometidos e acabam retransmitindo um grande volume de spam do EOP. Em quase todos os casos, os conectores corretos são configurados, mas o email é enviado de domínios não registrados, também conhecidos como desprovisionados,. O Office 365 permite uma quantidade razoável de emails provenientes de domínios não registrados, mas um domínio aceito deve ser configurado no centro de administração para cada domínio em que você pretende enviar.

Após o comprometimento, os locatários serão impedidos de enviar emails de saída para domínios não registrados. Os usuários receberão uma NDR (notificação de falha na entrega) que diz:

- 550 o serviço 5.7.750 não está disponível. Cliente impedido de enviar de domínios não registrados

## <a name="how-to-unblocking-tenant-in-order-to-send-again"></a>Como desbloquear o locatário para enviar novamente

Há várias coisas que você precisa fazer se o locatário for bloqueado para envio de email:

1. Certifique-se de registrar todos os seus domínios no centro de administração do Microsoft 365. Mais informações podem ser encontradas [aqui](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

2. Procure por conectores incomuns. Os atores mal-intencionados geralmente criarão novos conectores de entrada em seu locatário do Office 365 para enviar spam. Você pode encontrar mais informações sobre como verificar seus conectores [aqui](https://docs.microsoft.com/en-us/powershell/module/exchange/mail-flow/get-inboundconnector?view=exchange-ps). 

3. Bloqueie seus servidores locais e certifique-se de que eles não estão comprometidos.

> [!TIP]
> Há muitos fatores envolvidos aqui, especialmente se forem servidores de terceiros. Independentemente disso, você precisará confirmar que todos os emails que deixam seus servidores são legítimos.

4. Após concluir, você precisará ligar para o suporte da Microsoft e solicitar que o locatário seja desbloqueado para envio de domínios não registrados.  Fornecer o código de erro é útil, mas você precisará provar que seu ambiente está protegido e que o spam não será enviado novamente. É possível encontrar mais informações sobre como abrir um caso de suporte [aqui](https://support.office.com/en-us/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b#ID0EAADAAA=online).
  
## <a name="for-more-information"></a>Para saber mais

[Office 365 email anti-spam protection](anti-spam-protection.md)

[Notificações de falha na entrega de email no Office 365](https://support.office.com/article/email-non-delivery-reports-in-office-365-51daa6b9-2e35-49c4-a0c9-df85bf8533c3)

[Configurar o encaminhamento de email para uma caixa de correio](https://docs.microsoft.com/en-us/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)

[Como configurar um dispositivo multifuncional ou aplicativo para enviar email usando o Office 365](https://support.office.com/en-us/article/How-to-set-up-a-multifunction-device-or-application-to-send-email-using-Office-365-69f58e99-c550-4274-ad18-c805d654b4c4)

[Gerenciar domínios aceitos no Exchange Online](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).
