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
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a remover usuários do portal Usuários restritos no Office 365. Os usuários são adicionados ao portal Usuários restritos para enviar spam de saída, geralmente como resultado de um comprometimento da conta.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f464a2c02ae6b6290e79cc9aff7d3a37bc08a6ff
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572436"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a>Remover usuários bloqueados do portal Usuários restritos no Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Se um usuário exceder um dos limites de envio de saída, conforme especificado nos [limites de serviço](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) ou nas [políticas de spam de saída](configure-the-outbound-spam-policy.md), o usuário será impedido de enviar e-mails, mas ainda poderá receber e-mails.

O usuário é adicionado ao portal Usuários Restritos no Centro de conformidade e segurança. Ao tentarem enviar e-mails, a mensagem é retornada em um relatório de falha na entrega (também conhecido como NDR ou mensagens de devolução) com o código de erro [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) e o seguinte texto:

> "A mensagem não pôde ser entregue porque você não foi reconhecido como um remetente válido. O motivo mais comum para isso é que seu endereço de email é suspeito de enviar spam e não tem mais permissão para enviar emails.  Fale com o administrador para obter assistência. O servidor remoto retornou ' 550 5.1.8 acesso negado, remetente de saída incorreto ".

Os administradores podem remover usuários do portal Remetentes restritos no Centro de conformidade e segurança ou no PowerShell do Exchange Online.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Você abrir o Centro de conformidade e segurança em <https://protection.office.com/>. Para ir diretamente para a página **Usuários restritos**, use <https://protection.office.com/restrictedusers>.

- Para se conectar ao Windows PowerShell do Exchange Online, confira [Conectar ao Windows PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos neste artigo:
  - Para remover usuários do portal do Usuários Restritos, você precisa ser membro dos grupos de funções **Gerenciamento da Organização** ou **Administrador de Segurança**.
  - Para acesso somente para leitura do portal de Usuários Restritos, você precisa ser membro dos grupos de função **Leitor Global** ou **Leitor de Segurança**.

  Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

- Um remetente que exceder os limites de email de saída é um indicador de uma conta comprometida. Antes de remover o usuário do portal Usuários Restritos, siga as etapas necessárias para recuperar o controle da sua conta. Para obter mais informações, consulte [Responder a uma conta de e-mail comprometida no Office 365.](responding-to-a-compromised-email-account.md).

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a>Use o Centro de conformidade e segurança para remover um usuário da lista Usuários restritos

1. No Centro de conformidade e segurança, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Usuários restritos**.

2. Encontre e selecione o usuário que você quer desbloquear. Na coluna **Ações**, clique em **Desbloquear**.

3. Um menu suspenso entrará em detalhes sobre a conta cujo envio é restrito. Você deve percorrer as recomendações para garantir que você esteja tomando as ações adequadas caso a conta seja realmente comprometida. Quando terminar, escolha **Avançar**.

4. A tela seguinte tem recomendações para ajudar a evitar o futuro compromisso. A habilitação da autenticação multifator (MFA) e a alteração das senhas são uma boa defesa. Clique em **desbloquear usuário** quando terminar.

5. Clique em **Sim** para confirmar a alteração.

   > [!NOTE]
   > Pode levar até 30 minutos para que as restrições sejam removidas.

## <a name="verify-the-alert-settings-for-restricted-users"></a>Verifique as configurações de alertados usuários restritos

A política de alerta padrão denominada **Usuário impedido de enviar e-mails** notificará automaticamente os administradores quando os usuários forem impedidos de enviar e-mails de saída. Você pode verificar essas configurações e adicionar usuários adicionais para notificar. Para obter mais informações sobre políticas de alerta, consulte [Políticas de alerta no centro de segurança e conformidade.](../../compliance/alert-policies.md).

> [!IMPORTANT]
> Para que os alertas funcionem, a pesquisa de logs de auditoria deve ser ativada. Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).

1. No Centro de conformidade e segurança, acesse **Alertas** \>**Políticas de alerta**.

2. Localize e selecione o alerta **Usuário impedido de enviar e-mails**.

3. No submenu desdobrável exibido, verifique ou defina as seguintes configurações:

   - **Status**: Verifique se o alerta está ativado como ![Alternância](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

   - **Destinatários de e-mails**: Clique em **Editar** e verifique ou defina as seguintes configurações no menu **Editar destinatários** que é exibido:

     - **Enviar notificações por e-mail**: verificar se a caixa de seleção está marcada como (**Ativada**).

     - **Destinatários de e-mails**: o valor padrão é **TenantAdmins** (ou seja, membros de **Administração global**). Para adicionar mais destinatários, clique em uma área em branco da caixa. Uma lista de destinatários será exibida e você poderá começar a digitar um nome para filtrar e selecionar um destinatário. Você pode remover um destinatário existente da caixa clicando no ![ícone Remover](../../media/scc-remove-icon.png) ao lado do nome.

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

Para obter mais informações detalhadas de sintaxe e parâmetro, consulte [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).

Para remover um usuário da lista de Usuários Restritos, substitua o \<emailaddress\>pelo seu endereço de email e execute o seguinte comando:

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

Para obter mais informações detalhadas de sintaxe e parâmetro, consulte [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).
