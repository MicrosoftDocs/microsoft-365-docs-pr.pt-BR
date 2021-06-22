---
title: Responder a uma conta de email comprometida
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
search.appverid:
- MET150
description: Aprenda como reconhecer e responder a uma conta de e-mail comprometida no Microsoft 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 090253806295d0a5db67afbe769c9c0ca8be4b39
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054343"
---
# <a name="responding-to-a-compromised-email-account"></a>Responder a uma conta de email comprometida

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Resumo** Aprenda como reconhecer e responder a uma conta de email comprometida no Microsoft 365.

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a>O que é uma conta de email comprometida no Microsoft 365?

O acesso às caixas de correio, dados e outros serviços do Microsoft 365 é controlado por meio de credenciais, por exemplo, um nome de usuário e senha ou PIN. Quando alguém que não seja o usuário pretendido rouba essas credenciais, as credenciais roubadas são consideradas comprometidas. Com elas, o invasor pode entrar como o usuário original e executar ações ilícitas.

Usando as credenciais roubadas, o invasor pode acessar a caixa de correio do Microsoft 365, as pastas do SharePoint ou os arquivos no OneDrive do usuário. Uma ação comumente vista é o invasor enviar emails como o usuário original para os destinatários dentro e fora da organização. Quando o invasor envia dados por email para destinatários externos, isso é chamado de exfiltração de dados.

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a>Sintomas de uma conta de email da Microsoft comprometida

Os usuários podem notar e relatar atividades incomuns em suas caixas de correio do Microsoft 365. Aqui estão alguns sintomas comuns:

- Atividade suspeita, como emails ausentes ou excluídos.
- Outros usuários podem receber emails da conta comprometida sem o email correspondente estar na pasta **Itens Enviados** do remetente.
- A presença de regras de caixa de entrada que não foram criadas pelo usuário pretendido ou pelo administrador. Essas regras podem encaminhar emails automaticamente para endereços desconhecidos ou movê-los para as pastas **Anotações**, **Lixo Eletrônico** ou **Assinaturas RSS**.
- O nome de exibição do usuário pode ser alterado na Lista Global de Endereços.
- A caixa de correio se encontra impedida de enviar emails.
- As pastas Itens Enviados ou Excluídos no Microsoft Outlook ou Outlook na Web (anteriormente conhecido como Outlook Web App) contêm mensagens comuns de contas invadidas, como "Estou preso em Londres, envie dinheiro".
- Mudanças incomuns no perfil, como o nome, o número de telefone ou o CEP atualizados.
- Mudanças de credenciais incomuns, como várias alterações de senha necessárias.
- Encaminhamento de email adicionado recentemente.
- Uma assinatura incomum adicionada recentemente, como uma assinatura bancária falsa ou uma assinatura de medicamento de receita obrigatória.

Se um usuário relatar algum dos sintomas acima, você deverá realizar uma investigação adicional. O [Microsoft 365 Defender](https://security.microsoft.com) e o portal do Azure oferecem ferramentas para ajudá-lo a investigar a atividade de uma conta de usuário que você suspeita estar comprometida.

- **Logs de auditoria unificados no portal do Microsoft 365 Defender**: analise todas as atividades da conta suspeita, filtrando os resultados para o intervalo de datas imediatamente anterior à ocorrência da atividade suspeita até a data atual. Não filtre as atividades durante a pesquisa.

- **Logs de auditoria do administrador no EAC**: no Exchange Online, você pode usar o EAC (Centro de administração do Exchange) para procurar e exibir entradas no log de auditoria do administrador. O log de auditoria do administrador registra ações específicas, com base nos cmdlets do Exchange Online PowerShell, realizadas por administradores e usuários que receberam privilégios administrativos. As entradas do log de auditoria do administrador fornecem informações sobre qual cmdlet foi executado, quais parâmetros foram usados, quem executou o cmdlet e quais objetos foram afetados.

- **Registros de entrada do Azure AD e outros relatórios de risco no portal do Azure AD**: examine os valores destas colunas:
  - Revise o endereço IP
  - locais de entrada
  - horários de entrada
  - sucesso ou falha de entrada

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a>Como proteger e restaurar a funcionalidade de email de uma conta e caixa de correio do Microsoft 365 suspeitas de estarem comprometidas

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

Mesmo depois de ter recuperado o acesso à sua conta, o invasor pode ter adicionado entradas secundárias que permitem que ele retome o controle da conta.

Você deve realizar todas as etapas a seguir para recuperar o acesso à sua conta quanto antes, para garantir que o invasor não volte a controlar sua conta. Essas etapas ajudam você a remover todas as entradas secundárias que o sequestrador pode ter adicionado à sua conta. Depois de realizar essas etapas, recomendamos que você execute uma verificação de vírus para garantir que seu computador não esteja comprometido.

### <a name="step-1-reset-the-users-password"></a>Etapa 1 Redefina a senha do usuário

Siga os procedimentos em [ Redefinir uma senha comercial para alguém ](../../admin/add-users/reset-passwords.md#reset-my-admin-password).

> [!IMPORTANT]
>
> - Não envie a nova senha para o usuário pretendido por email, pois o invasor ainda terá acesso à caixa de correio neste momento.
>
> - Certifique-se de que a senha seja forte e que contenha letras maiúsculas e minúsculas, pelo menos um número e pelo menos um caractere especial.
>
> - Não reutilize nenhuma de suas últimas cinco senhas. Mesmo que o requisito de histórico de senha permita reutilizar uma senha mais recente, você deve selecionar algo que o invasor não consiga adivinhar.
>
> - Se a sua identidade local for federada com o Microsoft 365, será necessário alterar sua senha no local e, em seguida, notificar o administrador sobre o comprometimento.
>
> - Certifique-se de atualizar as senhas do aplicativo. As senhas do aplicativo não são revogadas automaticamente quando a senha da conta do usuário é redefinida. O usuário deve excluir as senhas dos aplicativos existentes e criar novas. Para instruções, consulte [Criar e excluir senhas dos aplicativos na página Verificação adicional de segurança](/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).
>
> - É altamente recomendável que você ative a Autenticação Multifator (MFA) para evitar comprometimentos, especialmente para contas com privilégios administrativos. Para saber mais sobre o MFA, acesse [Configurar autenticação multifator](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>Etapa 2 Remover endereços de encaminhamento de email suspeitos

1. Abra o Centro de administração do Microsoft 365 em <https://admin.microsoft.com>.

2. Vá até **Usuários** \> **Usuários ativos**. Encontre a conta do usuário em questão e o selecione (linha) sem marcar a caixa de seleção.

3. Nos detalhes que aparecem no meni desdobrável, selecione a guia **Email do Outlook**.

4. Se o valor na seção **Encaminhamento de e-mail** for **Aplicado**, clique em **Gerenciar encaminhamento de e-mail**. No menu desdobrável **Gerenciar encaminhamento de e-mail** que aparece, desmarque **Encaminhar todos os e-mails enviados para esta caixa de correio** e clique em **Salvar alterações**.

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>Etapa 3 Desabilite todas as regras de caixa de entrada suspeitas

1. Entre na caixa de correio do usuário usando o Outlook na web.

2. Clique no ícone de engrenagem e clique em **Email**.

3. Clique em **Regras de caixa de entrada e limpeza** e revise as regras.

4. Desative ou exclua regras suspeitas.

### <a name="step-4-unblock-the-user-from-sending-mail"></a>Etapa 4 Desbloqueie o usuário de enviar emails

Se a caixa de correio suspeita de estar comprometida foi usada ilicitamente para enviar emails de spam, é provável que esta tenha sido impedida de enviar emails.

Para desbloquear uma caixa de correio impedida de enviar emails, siga os procedimentos em [Removendo um usuário do portal de usuários restritos após o envio de emails de spam](removing-user-from-restricted-users-portal-after-spam.md).

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>Etapa 5 Opcional: bloqueie a conta de usuário no login

> [!IMPORTANT]
> Você pode impedir que a conta suspeita de estar comprometida inicie sessão, até considerar que é seguro reativar o acesso.

1. Abra o Centro de administração do Microsoft 365 em <https://admin.microsoft.com> e acesse **Usuários** \> **Usuários ativos**.

2. Encontre e selecione a conta do usuário, clique no ![ícone Mais ](../../media/ITPro-EAC-MoreOptionsIcon.png) e selecione **Editar status de login**.

3. No painel **Bloquear login** que aparece, selecione **Bloquear a assinatura deste usuário** e clique em **Salvar alterações**.

4. Abra o Centro de administração do Exchange (EAC) em <https://admin.exchange.microsoft.com> e acesse **Caixas de correio**\> de **Destinatários**.

5. Localize e selecione o usuário. No menu desdobrável de detalhes da caixa de correio que é aberto, execute as seguintes etapas:
   - Na seção **Aplicativos de email**, bloqueie todas as configurações disponíveis movendo o botão para a direita ![Desabilitar](../../media/scc-toggle-on.png):
     - **Outlook na Web**
     - **Área de trabalho do Outlook (MAPI)**
     - **Serviços Web do Exchange**
     - **Móvel (Exchange ActiveSync)**
     - **IMAP**
     - **POP3**

   Quando terminar, clique em **Salvar** e em **Fechar**.

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>Etapa 6 Opcional: Remova a conta suspeita de estar comprometida de todos os grupos de funções administrativas

> [!NOTE]
> A associação ao grupo de funções administrativas pode ser restaurada após a conta ter sido protegida.

1. Abra o Centro de administração do Microsoft 365 em <https://admin.microsoft.com> com uma conta de administrador global e execute as seguintes etapas:
   1. Vá até **Usuários** \> **Usuários ativos**.
   2. Encontre e selecione a conta do usuário, clique no ![ícone Mais](../../media/ITPro-EAC-MoreOptionsIcon.png) e selecione **Gerenciar funções**.
   3. Remova todas as funções administrativas atribuídas à conta. Quando terminar, clique em **Salvar alterações**.

2. Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com> e execute as seguintes etapas:
   1. Acesse **Permissões e funções** \> **Email e funções de colaboração** \> **Funções**.
   2. Na página **Permissões**, selecione cada grupo de função na lista e procure a conta do usuário na seção **Membros** do menu desdobrável de detalhes que aparece. Se o grupo de funções contiver a conta do usuário, execute as seguintes etapas:
      1. Na seção **Membros**, clique em **Editar**.
      2. No menu desdobrável **Editando Escolher membros** que aparece, clique em **Editar**.
      3. No menu desdobrável **Escolher membros** que aparece, clique em **Remover**.
      4. No menu desdobrável que aparece, selecione a conta do usuário e clique em **Remover**.

         Quando terminar, clique em **Concluído**, **Salvar** e depois em **Fechar**.

3. Abra o EAC em <https://admin.exchange.microsoft.com> e execute as seguintes etapas:
   1. Selecione **Funções** \> **Funções de administrador**.
   2. Na página **Funções de administrador**, selecione manualmente cada grupo de função e, no painel de detalhes, selecione a guia **Atribuído** para verificar as contas de usuário. Se o grupo de funções contiver a conta do usuário, execute as seguintes etapas:
      1. Selecione a conta do usuário.
      2. Clique no botão ![Ícone Excluir](../../media/m365-cc-sc-delete-icon.png).

         Quando concluir, clique em **Salvar**.

### <a name="step-7-optional-additional-precautionary-steps"></a>Etapa 7 Opcional: etapas adicionais de precaução

1. Certifique-se de verificar seus itens enviados. Você poderá ter que informar às pessoas em sua lista de contatos que sua conta foi comprometida. O invasor pode ter pedido dinheiro, forjando, por exemplo, que você estaria preso em um país diferente e precisaria de dinheiro, ou o invasor pode ter enviado um vírus para comprometer seus computadores também.

2. Qualquer outro serviço que tenha usado essa conta do Exchange como sua conta de email alternativa pode ter sido comprometido. Primeiro, realize estas etapas para sua assinatura do Microsoft 365 e, em seguida, realize estas etapas para suas outras contas.

3. Certifique-se de que suas informações de contato, como números de telefone e endereços, estejam corretas.

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Proteja o Microsoft 365 como um profissional de segurança cibernética

Sua assinatura do Microsoft 365 vem com um poderoso conjunto de recursos de segurança que você pode usar para proteger seus dados e seus usuários.  Use o [roteiro de segurança do Microsoft 365: principais prioridades para os primeiros 30 dias, 90 dias e depois](security-roadmap.md) para implementar práticas recomendadas para proteger o seu locatário do Microsoft 365.

- Tarefas a realizar nos primeiros 30 dias. Estas têm efeito imediato e baixo impacto para seus usuários.
- Tarefas a serem cumpridas em 90 dias. Isso leva um pouco mais de tempo para planejar e implementar, mas melhora muito sua postura de segurança.
- Mais de 90 dias. Essas melhorias são incluídas em seus primeiros 90 dias de trabalho.

## <a name="see-also"></a>Confira também

- [Detectar e corrigir ataques de injeção a regras e formulários personalizados do Outlook no Microsoft 365](detect-and-remediate-outlook-rules-forms-attack.md)
- [Centro de Reclamações contra Crimes pela Internet](https://www.ic3.gov/Home/Ransomware)
- [Comissão de Valores Mobiliários - Fraude de "Phishing"](https://www.sec.gov/investor/pubs/phishing.htm)
- Para denunciar emails de spam diretamente ao seu administrador e à Microsoft [Use o suplemento Reportar mensagem](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
