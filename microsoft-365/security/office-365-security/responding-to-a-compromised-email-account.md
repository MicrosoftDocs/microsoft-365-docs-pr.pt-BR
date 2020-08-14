---
title: Responder a uma conta de email comprometida
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Aprenda como reconhecer e responder a uma conta de e-mail comprometida no Microsoft 365.
ms.openlocfilehash: d412f40a6c3e1e2f1182437419ce9e0d28ed10eb
ms.sourcegitcommit: 929ca8f4d5fc006c3827f7a8b7d2b43e54c1b42a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46674609"
---
# <a name="responding-to-a-compromised-email-account"></a>Responder a uma conta de email comprometida

**Resumo** Aprenda como reconhecer e responder a uma conta de email comprometida no Microsoft 365.

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a>O que é uma conta de email comprometida no Microsoft 365?

O acesso a caixas de correio, dados e outros serviços do Microsoft 365 é controlado pelo uso de credenciais, por exemplo, um nome de usuários e senha ou PIN. Quando alguém que não seja o usuário pretendido rouba essas credenciais, as credenciais roubadas são consideradas comprometidas. Com elas, o invasor pode entrar como o usuário original e executar ações ilícitas.
Usando as credenciais roubadas, o invasor pode acessar a caixa de correio do Microsoft 365, as pastas do SharePoint ou os arquivos no OneDrive do usuário. Uma ação comumente vista é o invasor enviar emails como o usuário original para os destinatários dentro e fora da organização. Quando o invasor envia dados por email para destinatários externos, isso é chamado de exfiltração de dados.

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a>Sintomas de uma conta de email da Microsoft comprometida

Os usuários pode notar e relatar atividades incomuns em suas caixas de correio do Microsoft 365. Veja alguns sintomas comuns:

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

Se um usuário relatar algum dos sintomas acima, você deverá realizar uma investigação adicional. O Centro de Conformidade e Segurança do Microsoft 365 e o Portal do Azure oferecem ferramentas para ajudá-lo a investigar a atividade de uma conta de usuário que você suspeita estar comprometida.

- **Logs de auditoria unificada no Centro de Conformidade e Segurança**: analise todas as atividades na conta suspeita, filtrando os resultados para o intervalo de datas desde imediatamente antes da atividade suspeita ocorrer até a data atual. Não filtre as atividades durante a pesquisa.

- **Logs de auditoria do administrador no EAC**: no Exchange Online, você pode usar o EAC (Centro de administração do Exchange) para procurar e exibir entradas no log de auditoria do administrador. O log de auditoria do administrador registra ações específicas, com base no cmdlet do PowerShell do Exchange Online, executadas por administradores e usuários que receberam privilégios administrativos. As entradas do log de auditoria do administrador fornecem informações sobre qual cmdlet foi executado, quais parâmetros foram usados, quem executou o cmdlet e quais objetos foram afetados.

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

Siga os procedimentos em [ Redefinir uma senha comercial para alguém ](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords#reset-my-admin-password).

> [!IMPORTANT]
>
> - Não envie a nova senha para o usuário pretendido por email, pois o invasor ainda terá acesso à caixa de correio neste momento.
>
> - Certifique-se de que a senha seja forte e que contenha letras maiúsculas e minúsculas, pelo menos um número e pelo menos um caractere especial.
>
> - Não reutilize nenhuma das suas últimas cinco senhas. Mesmo que o requisito do histórico de senhas permita a reutilização de uma senha mais recente, você deve selecionar algo que o invasor não consiga adivinhar.
>
> - Se a sua identidade local for federada com o Microsoft 365, será necessário alterar sua senha no local e, em seguida, notificar o administrador sobre o comprometimento.
>
> - Certifique-se de atualizar as senhas do aplicativo. As senhas do aplicativo não são revogadas automaticamente quando a senha da conta do usuário é redefinida. O usuário deve excluir as senhas dos aplicativos existentes e criar novas. Para instruções, consulte [Criar e excluir senhas dos aplicativos na página Verificação adicional de segurança](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).
>
> - É altamente recomendável que você ative a Autenticação Multifator (MFA) para evitar comprometimentos, especialmente para contas com privilégios administrativos. Para saber mais sobre o MFA, acesse [Configurar autenticação multifator](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>Etapa 2 Remover endereços de encaminhamento de email suspeitos

1. Abra o Centro de administração do Microsoft 365 em <https://admin.microsoft.com>

2. Vá até**Usuários** \> **Usuários ativos**. Encontre a conta do usuário em questão e o selecione (linha) sem marcar a caixa de seleção.

3. Nos detalhes que aparecem no meni desdobrável, selecione a guia **Email do Outlook**.

4. Se o valor na seção **Encaminhamento de e-mail** for **Aplicado**, clique em ** Gerenciar encaminhamento de e-mail **. No menu desdobrável **Gerenciar encaminhamento de e-mail** que aparece, desmarque **Encaminhar todos os e-mails enviados para esta caixa de correio** e clique em **Salvar alterações **.

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

1. Abra o Centro de administração do Microsoft 365 e vá até **Usuários** \> ** Usuários ativos **.

2. Encontre e selecione a conta do usuário, clique no ![ícone Mais ](../../media/ITPro-EAC-MoreOptionsIcon.png) e selecione ** Editar status de login **.

3. No painel **Bloquear login** que aparece, selecione **Bloquear a assinatura deste usuário** e clique em **Salvar alterações**.

4. Abra o Centro de administração do Exchange (EAC) em <admin.protection.outlook.com/ecp/> e vá para ** Destinatários > Caixas de correio **.

5. Encontre e selecione o usuário. No painel de detalhes, execute as seguintes etapas:

   - Na seção **Recursos de telefone e voz**, execute as seguintes etapas:

     - Selecione **Desativar Exchange ActiveSync** e clique em ** Sim ** no aviso que aparece.
     - Selecione **Desabilitar OWA para Dispositivos** e clique em ** Sim ** no aviso que aparece.

   - Na seção **Conectividade de e-mail** para Outlook na Web, clique em **Desativar** e clique em **Sim** no aviso que aparece.

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>Etapa 6 Opcional: Remova a conta suspeita de estar comprometida de todos os grupos de funções administrativas

> [!NOTE]
> A associação ao grupo de funções administrativas pode ser restaurada após a conta ter sido protegida.

1. Faça o login com uma conta de administrador global:

2. No Centro de administração do Microsoft 365, execute as seguintes etapas:

   1. Vá até**Usuários** \> **Usuários ativos**.
   2. Encontre e selecione a conta do usuário, clique no ![ícone Mais](../../media/ITPro-EAC-MoreOptionsIcon.png) e selecione **Gerenciar funções**.
   3. Remova todas as funções administrativas atribuídas à conta. Quando terminar, clique em **Salvar alterações**.

3. No Centro de Segurança e Conformidade em <https://protection.office.com>, execute os seguintes passos:

   Selecione **Permissões**, selecione cada grupo de função na lista e procure a conta do usuário na seção **Membros** do menu desdobrável de detalhes que aparece. Se o grupo de funções contiver a conta do usuário, execute as seguintes etapas:

   a. Clique em **Editar** próximo a ** Membros **.
   b. No menu desdobrável **Editando Escolher membros** que aparece, clique em ** Editar **.
   c. No menu desdobrável **Escolher membros** que aparece, selecione a conta do usuário e clique em **Remover**. Quando terminar, clique em **Concluído**, **Salvar** e depois em **Fechar**.

4. Na EAC em <admin.protection.outlook.com/ecp/>, execute os seguintes passos:

   Selecione **Permissões**, selecione manualmente cada grupo de função e, no painel de detalhes, verifique as contas de usuário na seção **Membros**.  Se o grupo de funções contiver a conta do usuário, execute as seguintes etapas:

   a. Selecione o grupo de funções, clique em **Editar** ![ícone Editar](../../media/ITPro-EAC-EditIcon.png).
   b. Na seção **Membro**, selecione a conta do usuário e clique em **Remover** ![ícone Remover](../../media/ITPro-EAC-RemoveIcon.gif). Quando concluir, clique em **Salvar**.

### <a name="step-7-optional-additional-precautionary-steps"></a>Etapa 7 Opcional: etapas adicionais de precaução

1. Certifique-se de verificar seus itens enviados. Você poderá ter que informar às pessoas em sua lista de contatos que sua conta foi comprometida. O invasor pode ter pedido dinheiro, forjando, por exemplo, que você estaria preso em um país diferente e precisaria de dinheiro, ou o invasor pode ter enviado um vírus para comprometer seus computadores também.

2. Qualquer outro serviço que tenha usado essa conta do Exchange como sua conta de email alternativa pode ter sido comprometido. Primeiro, realize estas etapas para sua assinatura do Microsoft 365 e, em seguida, realize estas etapas para suas outras contas.

3. Certifique-se de que suas informações de contato, como números de telefone e endereços, estejam corretas.

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a>Proteja o Microsoft 365 como um profissional de segurança cibernética

Sua assinatura do Microsoft 365 vem com um poderoso conjunto de recursos de segurança que você pode usar para proteger seus dados e seus usuários.  Use o [roteiro de segurança do Microsoft 365: principais prioridades para os primeiros 30 dias, 90 dias e depois](security-roadmap.md) para implementar práticas recomendadas para proteger o seu locatário do Microsoft 365.

- Tarefas a realizar nos primeiros 30 dias.  Estas têm efeito imediato e baixo impacto para seus usuários.

- Tarefas para realizar em 90 dias. Estas levam um pouco mais de tempo para planejar e implementar, mas melhoram muito sua postura de segurança.

- Além de 90 dias. Estes aprimoramentos são desenvolvidos nos seus primeiros 90 dias de trabalho.

## <a name="see-also"></a>Confira também

- [Detectar e corrigir ataques de injeção a regras e formulários personalizados do Outlook no Microsoft 365](detect-and-remediate-outlook-rules-forms-attack.md)

- [Centro de Reclamações contra Crimes pela Internet](https://www.ic3.gov/preventiontips.aspx)

- [Comissão de Valores Mobiliários - Fraude de "Phishing"](https://www.sec.gov/investor/pubs/phishing.htm)

- Para denunciar emails de spam diretamente ao seu administrador e à Microsoft [Use o suplemento Reportar mensagem](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
