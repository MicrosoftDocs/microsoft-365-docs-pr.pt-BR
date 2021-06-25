---
title: Remover usuários bloqueados do portal Usuários restritos
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a remover usuários do portal Usuários restritos no portal do Microsoft 365 Defender. Os usuários são adicionados ao portal Usuários restritos para enviar spam de saída, geralmente como resultado de um comprometimento da conta.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 924db948103a4d3b45c499f433961762a45931af
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082847"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-microsoft-365"></a>Remover usuários bloqueados do portal Usuários restritos no Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Se um usuário exceder um dos limites de envio de saída, conforme especificado nos [limites de serviço](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) ou nas [políticas de spam de saída](configure-the-outbound-spam-policy.md), o usuário será impedido de enviar e-mails, mas ainda poderá receber e-mails.

O usuário é adicionado à página **Usuários restritos** no portal do Microsoft 365 Defender. Ao tentarem enviar e-mails, a mensagem é retornada em um relatório de falha na entrega (também conhecido como NDR ou mensagens de devolução) com o código de erro [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) e o seguinte texto:

> "A mensagem não pôde ser entregue porque você não foi reconhecido como um remetente válido. O motivo mais comum para isso é que seu endereço de email é suspeito de enviar spam e não tem mais permissão para enviar emails.  Fale com o administrador para obter assistência. O servidor remoto retornou ' 550 5.1.8 acesso negado, remetente de saída incorreto ".

Os administradores podem aprender a remover usuários do portal Usuários restritos no portal do Microsoft 365 Defender ou no PowerShell do Exchange Online.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com>. Para ir diretamente para a página **Usuários restritos**, use <https://security.microsoft.com/restrictedusers>.

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Você precisa ter permissões em **Exchange Online** antes de fazer os procedimentos deste artigo:
  - Para remover usuários do portal do Usuários restritos, você precisa ser membro dos grupos de funções **Gerenciamento da Organização** ou **Administrador de Segurança**.
  - Para acesso somente para leitura do portal de Usuários restritos, você precisa ser membro dos grupos de função **Leitor Global** ou **Leitor de Segurança**.

  Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  >
  > - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

- Um remetente que exceder os limites de email de saída é um indicador de uma conta comprometida. Antes de remover o usuário do portal Usuários restritos, siga as etapas necessárias para recuperar o controle da sua conta. Para obter mais informações, consulte [Responder a uma conta de e-mail comprometida no Office 365.](responding-to-a-compromised-email-account.md).

## <a name="use-the-microsoft-365-defender-portal-to-remove-a-user-from-the-restricted-users-list"></a>Use o portal do Microsoft 365 Defender para remover um usuário da lista de Usuários restritos

1. No portal do Microsoft 365 Defender, acesse **Email e colaboração**  > **Analisar** > **Usuários restritos**.

2. Na página **Usuários restritos**, localize e selecione o usuário que você deseja desbloquear clicando no usuário.

3. Clique na ação **Desbloqueio** que aparece.

4. No submenu **Desbloquear usuário** exibido, leia os detalhes sobre a conta restrita. Você deve percorrer as recomendações para garantir que você esteja tomando as ações adequadas caso a conta seja realmente comprometida.

   Ao terminar, clique em **Avançar**.

5. A tela seguinte tem recomendações para ajudar a evitar o futuro compromisso. A habilitação da autenticação multifator (MFA) e a alteração das senhas são uma boa defesa.

   Quando concluir, clique em **Enviar**.

6. Clique em **Sim** para confirmar a alteração.

   > [!NOTE]
   > Pode levar até 24 horas para que todas as restrições sejam removidas do usuário.

## <a name="verify-the-alert-settings-for-restricted-users"></a>Verifique as configurações de alertados usuários restritos

A política de alerta padrão denominada **Usuário impedido de enviar e-mails** notificará automaticamente os administradores quando os usuários forem impedidos de enviar e-mails de saída. Você pode verificar essas configurações e adicionar usuários adicionais para notificar. Para obter mais informações sobre políticas de alerta, confira [Políticas de alerta no Microsoft 365](../../compliance/alert-policies.md).

> [!IMPORTANT]
> Para que os alertas funcionem, a pesquisa de logs de auditoria deve ser ativada. Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).

1. No portal do Microsoft 365 Defender, acesse **Email e colaboração** \>**Políticas e regras** \> **Política de alerta**.

2. Na página **Política de alerta**, localize e selecione o alerta chamado **Usuário impedido de enviar e-mails**. Você pode classificar as políticas por nome ou usar a **Caixa de pesquisa** para localizar a política.

3. No submenu **Usuário restringido de enviar e-mail** exibido, verifique ou defina as seguintes configurações:
   - **Status**: Verifique se o alerta está ativado como ![Alternância](../../media/scc-toggle-on.png).
   - **Destinatários de e-mails**: Clique em **Editar** e verifique ou defina as seguintes configurações no menu **Editar destinatários** que é exibido:
     - **Enviar notificações por e-mail**: verificar se a caixa de seleção está marcada como (**Ativada**).
     - **Destinatários de e-mails**: o valor padrão é **TenantAdmins** (ou seja, membros de **Administração global**). Para adicionar mais destinatários, clique em uma área em branco da caixa. Uma lista de destinatários será exibida e você poderá começar a digitar um nome para filtrar e selecionar um destinatário. Você pode remover um destinatário existente da caixa clicando no ![ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) ao lado do nome.
     - **Limite de notificação diário**: o valor padrão é **Sem limite**, mas você pode selecionar um limite para o número máximo de notificações por dia.

     Quando concluir, clique em **Salvar**.

4. Volte ao submenu **Usuário impedido de enviar e-mail**, clique em **Fechar**.

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a>Use o Exchange Online PowerShell para exibir e remover usuários da lista Usuários restritos

Para visualizar esta lista de usuários que estão impedidos de enviar e-mails, execute o seguinte comando:

```powershell
Get-BlockedSenderAddress
```

Para exibir detalhes de um usuário específico, substitua o \<emailaddress\> pelo seu endereço de email e execute o seguinte comando:

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

Para obter mais informações detalhadas de sintaxe e parâmetro, consulte [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress).

Para remover um usuário da lista de Usuários Restritos, substitua o \<emailaddress\> pelo seu endereço de e-mail e execute o seguinte comando:

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

Para obter mais informações detalhadas de sintaxe e parâmetro, consulte [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress).
