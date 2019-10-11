---
title: Controlar spam de saída no Office 365
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
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: Se sua organização enviar muitas mensagens em massa marcadas como spam, você poderá ter impedido de enviar emails com o Office 365. Leia este artigo para saber mais sobre por que isso acontece e o que você pode fazer sobre ele.
ms.openlocfilehash: 1985f9726a32e2726fd2814e5ec9079ad3ec211e
ms.sourcegitcommit: 6c42fb7123b9688f9b53bc7fa91fb8cdfcf4c718
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/11/2019
ms.locfileid: "37455063"
---
# <a name="control-outbound-spam-in-office-365"></a>Controlar spam de saída no Office 365

Adotamos o gerenciamento de spam de saída seriamente porque nosso é um serviço compartilhado.  Há muitos clientes por trás de um pool compartilhado de recursos, onde um cliente envia spams de saída, pode degradar a reputação de IP de saída do serviço e afeta a entrega bem-sucedida de emails para outros clientes.

> [!IMPORTANT]
> A notificação de quando um remetente é restrito agora faz parte da plataforma de alerta do centro de conformidade do & de segurança (SCC). Em vez de usar os métodos descritos abaixo para enviar notificações, a lista de usuários a serem alertados pode ser encontrada no alerta **usuário impedido de enviar email** . Comece a usar a [página políticas de alerta](https://sip.protection.office.com/alertpolicies) no centro de conformidade de & de segurança para configurar o alerta, pois o método anterior será removido no futuro. Leia sobre a nova [remoção de um usuário do portal de usuários restritos após o envio de email de spam](removing-user-from-restricted-users-portal-after-spam.md).

## <a name="what-admins-can-do-to-control-outbound-spam"></a>O que os administradores podem fazer para controlar o spam de saída

- **Habilitar notificações quando uma conta estiver enviando spam ou desligar**: os administradores podem obter estava sempre que uma mensagem é marcada como spam de saída e enviada através do pool de alto risco. Ao monitorar esta caixa de correio, um administrador pode detectar se eles têm uma conta comprometida em sua rede ou se o filtro de spam está marcando incorretamente o email como spam. Você pode encontrar mais informações sobre como configurar a política de spam de saída [aqui](configure-the-outbound-spam-policy.md).

- **Revise manualmente as reclamações de spam de provedores de email de terceiros**: vários serviços de email de terceiros, como o Outlook.com, o Yahoo e o AOL fornecem um loop de feedback em que, se qualquer usuário em seu serviço marcar um email de nosso serviço como spam, a mensagem será empacotada e enviado de volta para nós para revisão. Para saber mais sobre o suporte do remetente para o Outlook.com, clique [aqui](https://sendersupport.olc.protection.outlook.com/pm/services.aspx).

## <a name="what-eop-does-to-control-outbound-spam"></a>O que o EOP faz para controlar o spam de saída

1. **Diferenciação de tráfego de saída em pools de IPS separados**: todas as mensagens que os clientes enviam saída através do serviço são verificadas quanto ao spam. Se a mensagem for spam, ela será roteada através do pool de entrega de alto risco. Este pool de IPS contém notificações de status e spam não entregues. A entrega ao destinatário pretendido não é garantida, pois muitos terceiros não aceitarão emails, pois a qualidade do email emite.

   Dividir o tráfego dessa forma garante que o email de qualidade inferior (spam, NDRs de inspersão) não arraste para baixo a reputação dos pools de email de saída normais. O pool de alto risco geralmente tem baixa reputação de muitos receptores pela Internet, embora isso não seja universal.

2. **Monitoramento de reputação de IP**: o Office 365 consulta vários IP de terceiros listas e gera alertas se qualquer um dos nossos IPS de saída estiverem listados neles. Isso nos permite reagir rapidamente quando o spam causa a degradação da nossa reputação. Quando um alerta é gerado, temos documentação interna contratando quais etapas devem ser executadas para serem deslistadas.

3. **Desabilitar as contas incorretas quando eles enviam muitos emails marcados como spam**: embora segrego nosso spam e não spam em dois pools de IP de saída separados, as contas de email não podem enviar spam indefinidamente. Monitoramos quais contas estão enviando spam e se elas excedem um limite não divulgado, a conta é impedida de enviar spam.

   Uma única mensagem marcada como spam pode ser uma classificação inválida pelo mecanismo de spam e também conhecida como falso positivo. Nós o enviamos pelo pool de alto risco para dar a chance de sair; no entanto, um grande número de mensagens em um curto período de tempo indica um problema e, quando isso ocorre, impede que a conta envie mais email. Há diferentes limites que existem para contas de email individuais, bem como em agregação para o locatário inteiro.

4. **Desabilitação de contas incorretas quando eles enviam muito emails por um**período de tempo: além dos limites acima que procuram uma proporção de mensagens marcadas como spam, também há limites que bloqueiam contas quando atingem um limite geral independentemente Se as mensagens são ou não marcadas como spam. O motivo pelo qual esse limite existe é porque uma conta comprometida pode enviar spam de zero dias que não foi perdido pelo filtro de spam. Como é difícil, se não for impossível, para às vezes dizer a diferença entre uma campanha de email em massa legítima e uma campanha de spam maciça, esses limites são ativados para limitar qualquer dano em potencial.

> [!NOTE]
> Para #3 e #4, não anunciamos os limites exatos para evitar que os remetentes de spam entrem em jogos o sistema e para garantir que possamos alterar os limites quando precisarmos. Os limites são altos o suficiente, de forma que um usuário de negócios médio nunca o acessará e o suficiente para que ele contenha a maior parte dos danos que um spammer pode fazer.

## <a name="recommended-workarounds-for-customers-who-want-to-send-outbound-a-lot-of-email-through-eop"></a>Soluções alternativas recomendadas para clientes que desejam enviar uma grande quantidade de emails por meio do EOP

É difícil fazer um equilíbrio entre os clientes que desejam enviar um grande volume de emails versus proteger o serviço de contas comprometidas e emails em massa com práticas de aquisição de lista deficiente. Novamente, o custo de um início de IP de saída em uma barra de bloqueio de terceiros é maior do que impedir que um cliente envie emails de saída. Conforme descrito na [Descrição do serviço do Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits), o uso do EOP para enviar emails em massa não é um uso com suporte do serviço e só é permitido em uma base de "melhor esforço". Para clientes que desejam enviar email em massa, recomendamos o seguinte:

1. **Envie o email em massa por meio de seus próprios servidores de email locais**: isso significa que o cliente precisará manter sua própria infraestrutura de email para esse tipo de email.

2. **Use um email em massa de terceiros para enviar a comunicação em massa**: há vários emails em massa de terceiros, cujo único negócio é enviar email em massa. Eles podem trabalhar com os clientes para garantir que eles tenham boas práticas de email e que tenham recursos dedicados à imposição.

O grupo de trabalho do MAAWG (mensagens antiabuso, móvel e malware) publica sua lista de associação [aqui](http://www.maawg.org/about/roster). Vários provedores de email em massa estão na lista e são conhecidos como cidadãos da Internet responsáveis.

## <a name="for-more-information"></a>Para saber mais

[Notificação de exemplo de quando um remetente é bloqueado ao enviar spam de saída](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)

[Proteção antispam de emails do Office 365](anti-spam-protection.md)

[Proteção antifalsificação no Office 365](anti-spoofing-protection.md)

[Níveis de confiança de spam](spam-confidence-levels.md)
