---
title: Remoção de um usuário do portal de Usuários Restritos após o envio de email de spam
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/10/2019
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Se um usuário que continuamente envia emails do Office 365 é classificado como spam, ele será impedido de enviar qualquer outra mensagem de email.
ms.openlocfilehash: c817add2581ffdbe709023dc3b348631defec169
ms.sourcegitcommit: 6ae69c40bafa6aef633789c3df0fa20590bdcf40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "40823813"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a>Remoção de um usuário do portal de Usuários Restritos após o envio de email de spam

Se um usuário enviar emails continuamente classificados como spam do Office 365, eles não poderão enviar emails, mas ainda poderão recebê-los. O usuário será listado no serviço como um remetente de saída incorreto e receberá uma notificação de falha na entrega (NDR) que diz:

> "A mensagem não pôde ser entregue porque você não foi reconhecido como um remetente válido. O motivo mais comum para isso é que seu endereço de email é suspeito de enviar spam e não tem mais permissão para enviar emails.  Fale com o administrador para obter assistência. O servidor remoto retornou ' 550 5.1.8 acesso negado, remetente de saída incorreto ".

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?
<a name="sectionSection0"> </a>

Tempo estimado para conclusão: 5 minutos

Para executar este procedimento ou estes procedimentos, você precisa receber permissões. Para ver quais são as permissões necessárias, confira a Entrada antispam, no tópico [Permissões de recursos no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions).

O procedimento a seguir também pode ser realizado pelo PowerShell remoto. Use o cmdlet Get-BlockedSenderAddress para obter a lista de usuários restritos e remover-BlockedSenderAddress para remover a restrição. Para saber como usar o Windows PowerShell para se conectar ao Exchange Online, confira o artigo [Conectar-se ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a>Remover restrições de uma conta de email bloqueada do Office 365

Você conclui essa tarefa no centro de conformidade & de segurança (SCC). [Vá para o centro de conformidade e de segurança](../../compliance/go-to-the-securitycompliance-center.md) para obter mais detalhes sobre o SCC. É necessário estar **no grupo de função gerenciamento** da organização ou **administrador** de segurança para executar essas funções. [Vá para permissões no centro de conformidade e de segurança](permissions-in-the-security-and-compliance-center.md) para obter mais detalhes sobre os grupos de funções SCC.

1. Usando uma conta corporativa ou de estudante com privilégios de administrador global do Office 365, entre no centro de segurança e conformidade do Office 365 e na lista à esquerda, **expanda**gerenciamento de **ameaças, escolha revisão**e, em seguida **, escolha**usuários restritos.

    > [!TIP]
    > Para ir diretamente para a página **Usuários Restritos** (conhecida anteriormente como Central de Ações) no centro de &amp;Conformidade de Segurança, use esta URL: [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)

2. Esta página conterá a lista de usuários que foram impedidos de enviar emails.  Localize o usuário para o qual você deseja remover restrições e selecione **desbloquear**.

3. Um menu suspenso entrará em detalhes sobre a conta cujo envio é restrito. Você deve percorrer as recomendações para garantir que você esteja tomando as ações adequadas caso a conta seja realmente comprometida. Quando terminar, escolha **Avançar**.

4. A tela seguinte tem recomendações para ajudar a evitar o futuro compromisso. A habilitação da autenticação multifator (MFA) e a alteração das senhas são uma boa defesa. Clique em **desbloquear usuário** quando terminar.

5. Clique em **Sim** para confirmar a alteração.

    > [!NOTE]
    > Pode levar até 30 minutos para que as restrições sejam removidas.

## <a name="making-sure-admins-are-alerted-when-this-happens"></a>Garantindo que os administradores sejam alertados quando isso acontecer

O alerta "o usuário não restringiu o email" está disponível como uma política na página políticas de alerta de conformidade e segurança do Office 365. Essa era uma política de spam de saída, mas agora era nativa à plataforma de alerta do Office 365. Vá para [políticas de alerta no centro](../../compliance/alert-policies.md) de conformidade e de segurança para obter mais informações sobre alertas.

> [!IMPORTANT]
> Para que os alertas funcionem, a pesquisa de logs de auditoria deve ser ativada. Confira como [ativar ou desativar a pesquisa de log de auditoria do Office 365](../../compliance/turn-audit-log-search-on-or-off.md) para obter mais informações.

A política desse alerta é um padrão e acompanha cada locatário do Office 365 e não precisa ser configurada. Ele é considerado um alerta de alta gravidade e enviará por email o grupo configurado TenantAdmins quando o alerta for disparado sempre que um usuário tiver sido restringido de enviar emails. Os administradores podem atualizar o grupo notificado quando esse alerta acontece indo para o alerta no portal SCC > Alertas > políticas de alerta > usuários restritos a enviar emails.

Você poderá editar o alerta no:
- Ativivar/desativar as notificações por email
- Enviar por email os destinatários necessários
- Limitar as notificações obtidas por dia

## <a name="checking-for-and-removing-restrictions-using-powershell"></a>Verificando e removendo restrições usando o PowerShell
Os comandos do PowerShell para usuários restritos são:
- `Get-BlockedSenderAddress`: Executar a lista de usuários que estão restritos ao envio de emails
- `Remove-BlockedSenderAddress`: Executar para remover usuário (s) da restrição

## <a name="for-more-information"></a>Para obter mais informações

[Responder a uma conta de email comprometida](responding-to-a-compromised-email-account.md)

[Entender o usuário restrito de enviar alerta de emails](https://docs.microsoft.com/office365/securitycompliance/alert-policies)

[Pool de entrega de alto risco para mensagens de saída](high-risk-delivery-pool-for-outbound-messages.md)

[Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md)

[Políticas de alerta no Centro de Conformidade e Segurança](https://docs.microsoft.com/office365/securitycompliance/alert-policies)
