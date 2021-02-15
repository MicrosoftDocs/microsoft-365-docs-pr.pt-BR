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
ms.openlocfilehash: a34780b260a6e4bbc2d8b3f53af6b67de04fbdcd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166658"
---
# <a name="responding-to-a-compromised-email-account"></a><span data-ttu-id="14179-103">Responder a uma conta de email comprometida</span><span class="sxs-lookup"><span data-stu-id="14179-103">Responding to a Compromised Email Account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="14179-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="14179-104">**Applies to**</span></span>
- [<span data-ttu-id="14179-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="14179-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="14179-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="14179-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="14179-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="14179-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="14179-108">**Resumo** Aprenda como reconhecer e responder a uma conta de email comprometida no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14179-108">**Summary** Learn how to recognize and respond to a compromised email account in Microsoft 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a><span data-ttu-id="14179-109">O que é uma conta de email comprometida no Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="14179-109">What is a Compromised Email Account in Microsoft 365?</span></span>

<span data-ttu-id="14179-110">O acesso a caixas de correio, dados e outros serviços do Microsoft 365 é controlado pelo uso de credenciais, por exemplo, um nome de usuários e senha ou PIN.</span><span class="sxs-lookup"><span data-stu-id="14179-110">Access to Microsoft 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="14179-111">Quando alguém que não seja o usuário pretendido rouba essas credenciais, as credenciais roubadas são consideradas comprometidas.</span><span class="sxs-lookup"><span data-stu-id="14179-111">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="14179-112">Com elas, o invasor pode entrar como o usuário original e executar ações ilícitas.</span><span class="sxs-lookup"><span data-stu-id="14179-112">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="14179-113">Usando as credenciais roubadas, o invasor pode acessar a caixa de correio do Microsoft 365, as pastas do SharePoint ou os arquivos no OneDrive do usuário.</span><span class="sxs-lookup"><span data-stu-id="14179-113">Using the stolen credentials, the attacker can access the user's Microsoft 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="14179-114">Uma ação comumente vista é o invasor enviar emails como o usuário original para os destinatários dentro e fora da organização.</span><span class="sxs-lookup"><span data-stu-id="14179-114">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="14179-115">Quando o invasor envia dados por email para destinatários externos, isso é chamado de exfiltração de dados.</span><span class="sxs-lookup"><span data-stu-id="14179-115">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a><span data-ttu-id="14179-116">Sintomas de uma conta de email da Microsoft comprometida</span><span class="sxs-lookup"><span data-stu-id="14179-116">Symptoms of a Compromised Microsoft Email Account</span></span>

<span data-ttu-id="14179-117">Os usuários pode notar e relatar atividades incomuns em suas caixas de correio do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14179-117">Users might notice and report unusual activity in their Microsoft 365 mailboxes.</span></span> <span data-ttu-id="14179-118">Veja alguns sintomas comuns:</span><span class="sxs-lookup"><span data-stu-id="14179-118">Here are some common symptoms:</span></span>

- <span data-ttu-id="14179-119">Atividade suspeita, como emails ausentes ou excluídos.</span><span class="sxs-lookup"><span data-stu-id="14179-119">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="14179-120">Outros usuários podem receber emails da conta comprometida sem o email correspondente estar na pasta **Itens Enviados** do remetente.</span><span class="sxs-lookup"><span data-stu-id="14179-120">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="14179-121">A presença de regras de caixa de entrada que não foram criadas pelo usuário pretendido ou pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="14179-121">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="14179-122">Essas regras podem encaminhar emails automaticamente para endereços desconhecidos ou movê-los para as pastas **Anotações**, **Lixo Eletrônico** ou **Assinaturas RSS**.</span><span class="sxs-lookup"><span data-stu-id="14179-122">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="14179-123">O nome de exibição do usuário pode ser alterado na Lista Global de Endereços.</span><span class="sxs-lookup"><span data-stu-id="14179-123">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="14179-124">A caixa de correio se encontra impedida de enviar emails.</span><span class="sxs-lookup"><span data-stu-id="14179-124">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="14179-125">As pastas Itens Enviados ou Excluídos no Microsoft Outlook ou Outlook na Web (anteriormente conhecido como Outlook Web App) contêm mensagens comuns de contas invadidas, como "Estou preso em Londres, envie dinheiro".</span><span class="sxs-lookup"><span data-stu-id="14179-125">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="14179-126">Mudanças incomuns no perfil, como o nome, o número de telefone ou o CEP atualizados.</span><span class="sxs-lookup"><span data-stu-id="14179-126">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="14179-127">Mudanças de credenciais incomuns, como várias alterações de senha necessárias.</span><span class="sxs-lookup"><span data-stu-id="14179-127">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="14179-128">Encaminhamento de email adicionado recentemente.</span><span class="sxs-lookup"><span data-stu-id="14179-128">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="14179-129">Uma assinatura incomum adicionada recentemente, como uma assinatura bancária falsa ou uma assinatura de medicamento de receita obrigatória.</span><span class="sxs-lookup"><span data-stu-id="14179-129">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="14179-130">Se um usuário relatar algum dos sintomas acima, você deverá realizar uma investigação adicional.</span><span class="sxs-lookup"><span data-stu-id="14179-130">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="14179-131">O Centro de Conformidade e Segurança do Microsoft 365 e o Portal do Azure oferecem ferramentas para ajudá-lo a investigar a atividade de uma conta de usuário que você suspeita estar comprometida.</span><span class="sxs-lookup"><span data-stu-id="14179-131">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="14179-132">**Logs de auditoria unificada no Centro de Conformidade e Segurança**: analise todas as atividades na conta suspeita, filtrando os resultados para o intervalo de datas desde imediatamente antes da atividade suspeita ocorrer até a data atual.</span><span class="sxs-lookup"><span data-stu-id="14179-132">**Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="14179-133">Não filtre as atividades durante a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="14179-133">Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="14179-134">**Logs de auditoria do administrador no EAC**: no Exchange Online, você pode usar o EAC (Centro de administração do Exchange) para procurar e exibir entradas no log de auditoria do administrador.</span><span class="sxs-lookup"><span data-stu-id="14179-134">**Admin Audit logs in the EAC**: In Exchange Online, you can use the Exchange admin center (EAC) to search for and view entries in the administrator audit log.</span></span> <span data-ttu-id="14179-135">O log de auditoria do administrador registra ações específicas, com base no cmdlet do PowerShell do Exchange Online, executadas por administradores e usuários que receberam privilégios administrativos.</span><span class="sxs-lookup"><span data-stu-id="14179-135">The administrator audit log records specific actions, based on Exchange Online PowerShell cmdlets, performed by administrators and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="14179-136">As entradas do log de auditoria do administrador fornecem informações sobre qual cmdlet foi executado, quais parâmetros foram usados, quem executou o cmdlet e quais objetos foram afetados.</span><span class="sxs-lookup"><span data-stu-id="14179-136">Entries in the administrator audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

- <span data-ttu-id="14179-137">**Registros de entrada do Azure AD e outros relatórios de risco no portal do Azure AD**: examine os valores destas colunas:</span><span class="sxs-lookup"><span data-stu-id="14179-137">**Azure AD Sign-in logs and other risk reports in the Azure AD portal**: Examine the values in these columns:</span></span>

  - <span data-ttu-id="14179-138">Revise o endereço IP</span><span class="sxs-lookup"><span data-stu-id="14179-138">Review IP address</span></span>
  - <span data-ttu-id="14179-139">locais de entrada</span><span class="sxs-lookup"><span data-stu-id="14179-139">sign-in locations</span></span>
  - <span data-ttu-id="14179-140">horários de entrada</span><span class="sxs-lookup"><span data-stu-id="14179-140">sign-in times</span></span>
  - <span data-ttu-id="14179-141">sucesso ou falha de entrada</span><span class="sxs-lookup"><span data-stu-id="14179-141">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a><span data-ttu-id="14179-142">Como proteger e restaurar a funcionalidade de email de uma conta e caixa de correio do Microsoft 365 suspeitas de estarem comprometidas</span><span class="sxs-lookup"><span data-stu-id="14179-142">How to secure and restore email function to a suspected compromised Microsoft 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="14179-143">Mesmo depois de ter recuperado o acesso à sua conta, o invasor pode ter adicionado entradas secundárias que permitem que ele retome o controle da conta.</span><span class="sxs-lookup"><span data-stu-id="14179-143">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="14179-144">Você deve realizar todas as etapas a seguir para recuperar o acesso à sua conta quanto antes, para garantir que o invasor não volte a controlar sua conta.</span><span class="sxs-lookup"><span data-stu-id="14179-144">You must do all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="14179-145">Essas etapas ajudam você a remover todas as entradas secundárias que o sequestrador pode ter adicionado à sua conta.</span><span class="sxs-lookup"><span data-stu-id="14179-145">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="14179-146">Depois de realizar essas etapas, recomendamos que você execute uma verificação de vírus para garantir que seu computador não esteja comprometido.</span><span class="sxs-lookup"><span data-stu-id="14179-146">After you do these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="14179-147">Etapa 1 Redefina a senha do usuário</span><span class="sxs-lookup"><span data-stu-id="14179-147">Step 1 Reset the user's password</span></span>

<span data-ttu-id="14179-148">Siga os procedimentos em [ Redefinir uma senha comercial para alguém ](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords#reset-my-admin-password).</span><span class="sxs-lookup"><span data-stu-id="14179-148">Follow the procedures in [Reset a business password for someone](https://docs.microsoft.com/microsoft-365/admin/add-users/reset-passwords#reset-my-admin-password).</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="14179-149">Não envie a nova senha para o usuário pretendido por email, pois o invasor ainda terá acesso à caixa de correio neste momento.</span><span class="sxs-lookup"><span data-stu-id="14179-149">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>
>
> - <span data-ttu-id="14179-150">Certifique-se de que a senha seja forte e que contenha letras maiúsculas e minúsculas, pelo menos um número e pelo menos um caractere especial.</span><span class="sxs-lookup"><span data-stu-id="14179-150">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>
>
> - <span data-ttu-id="14179-151">Não reutilize nenhuma das suas últimas cinco senhas.</span><span class="sxs-lookup"><span data-stu-id="14179-151">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="14179-152">Mesmo que o requisito do histórico de senhas permita a reutilização de uma senha mais recente, você deve selecionar algo que o invasor não consiga adivinhar.</span><span class="sxs-lookup"><span data-stu-id="14179-152">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>
>
> - <span data-ttu-id="14179-153">Se a sua identidade local for federada com o Microsoft 365, será necessário alterar sua senha no local e, em seguida, notificar o administrador sobre o comprometimento.</span><span class="sxs-lookup"><span data-stu-id="14179-153">If your on-premises identity is federated with Microsoft 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>
>
> - <span data-ttu-id="14179-154">Certifique-se de atualizar as senhas do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="14179-154">Be sure to update app passwords.</span></span> <span data-ttu-id="14179-155">As senhas do aplicativo não são revogadas automaticamente quando a senha da conta do usuário é redefinida.</span><span class="sxs-lookup"><span data-stu-id="14179-155">App passwords aren't automatically revoked when a user account password reset.</span></span> <span data-ttu-id="14179-156">O usuário deve excluir as senhas dos aplicativos existentes e criar novas.</span><span class="sxs-lookup"><span data-stu-id="14179-156">The user should delete existing app passwords and create new ones.</span></span> <span data-ttu-id="14179-157">Para instruções, consulte [Criar e excluir senhas dos aplicativos na página Verificação adicional de segurança](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).</span><span class="sxs-lookup"><span data-stu-id="14179-157">For instructions, see [Create and delete app passwords from the Additional security verification page](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).</span></span>
>
> - <span data-ttu-id="14179-158">É altamente recomendável que você ative a Autenticação Multifator (MFA) para evitar comprometimentos, especialmente para contas com privilégios administrativos.</span><span class="sxs-lookup"><span data-stu-id="14179-158">We highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span> <span data-ttu-id="14179-159">Para saber mais sobre o MFA, acesse [Configurar autenticação multifator](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="14179-159">To learn more about MFA, go to [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="14179-160">Etapa 2 Remover endereços de encaminhamento de email suspeitos</span><span class="sxs-lookup"><span data-stu-id="14179-160">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="14179-161">Abra o Centro de administração do Microsoft 365 em <https://admin.microsoft.com></span><span class="sxs-lookup"><span data-stu-id="14179-161">Open the Microsoft 365 admin center at <https://admin.microsoft.com></span></span>

2. <span data-ttu-id="14179-162">Vá até **Usuários** \> **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="14179-162">Go to **Users** \> **Active users**.</span></span> <span data-ttu-id="14179-163">Encontre a conta do usuário em questão e o selecione (linha) sem marcar a caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="14179-163">Find the user account in question, and select the user (row) without selecting the checkbox.</span></span>

3. <span data-ttu-id="14179-164">Nos detalhes que aparecem no meni desdobrável, selecione a guia **Email do Outlook**.</span><span class="sxs-lookup"><span data-stu-id="14179-164">In the details flyout that appears, select the **Mail** tab.</span></span>

4. <span data-ttu-id="14179-165">Se o valor na seção **Encaminhamento de e-mail** for **Aplicado**, clique em **Gerenciar encaminhamento de e-mail**.</span><span class="sxs-lookup"><span data-stu-id="14179-165">If the value in the **Email forwarding** section is **Applied**, click **Manage email forwarding**.</span></span> <span data-ttu-id="14179-166">No menu desdobrável **Gerenciar encaminhamento de e-mail** que aparece, desmarque **Encaminhar todos os e-mails enviados para esta caixa de correio** e clique em **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="14179-166">In the **Manage email forwarding** flyout that appears, clear **Forward all email sent to this mailbox**, and then click **Save changes**.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="14179-167">Etapa 3 Desabilite todas as regras de caixa de entrada suspeitas</span><span class="sxs-lookup"><span data-stu-id="14179-167">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="14179-168">Entre na caixa de correio do usuário usando o Outlook na web.</span><span class="sxs-lookup"><span data-stu-id="14179-168">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="14179-169">Clique no ícone de engrenagem e clique em **Email**.</span><span class="sxs-lookup"><span data-stu-id="14179-169">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="14179-170">Clique em **Regras de caixa de entrada e limpeza** e revise as regras.</span><span class="sxs-lookup"><span data-stu-id="14179-170">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="14179-171">Desative ou exclua regras suspeitas.</span><span class="sxs-lookup"><span data-stu-id="14179-171">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="14179-172">Etapa 4 Desbloqueie o usuário de enviar emails</span><span class="sxs-lookup"><span data-stu-id="14179-172">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="14179-173">Se a caixa de correio suspeita de estar comprometida foi usada ilicitamente para enviar emails de spam, é provável que esta tenha sido impedida de enviar emails.</span><span class="sxs-lookup"><span data-stu-id="14179-173">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="14179-174">Para desbloquear uma caixa de correio impedida de enviar emails, siga os procedimentos em [Removendo um usuário do portal de usuários restritos após o envio de emails de spam](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="14179-174">To unblock a mailbox from sending mail, follow the procedures in [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="14179-175">Etapa 5 Opcional: bloqueie a conta de usuário no login</span><span class="sxs-lookup"><span data-stu-id="14179-175">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14179-176">Você pode impedir que a conta suspeita de estar comprometida inicie sessão, até considerar que é seguro reativar o acesso.</span><span class="sxs-lookup"><span data-stu-id="14179-176">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="14179-177">Abra o Centro de administração do Microsoft 365 e vá até **Usuários** \> **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="14179-177">Open the Microsoft 365 admin center and go to **Users** \> **Active users**.</span></span>

2. <span data-ttu-id="14179-178">Encontre e selecione a conta do usuário, clique no ![ícone Mais ](../../media/ITPro-EAC-MoreOptionsIcon.png) e selecione **Editar status de login**.</span><span class="sxs-lookup"><span data-stu-id="14179-178">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Edit sign-in status**.</span></span>

3. <span data-ttu-id="14179-179">No painel **Bloquear login** que aparece, selecione **Bloquear a assinatura deste usuário** e clique em **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="14179-179">On the **Block sign-in** pane that appears, select **Block this user from signing in**, and then click **Save changes**.</span></span>

4. <span data-ttu-id="14179-180">Abra o Centro de administração do Exchange (EAC) em <admin.protection.outlook.com/ecp/> e vá para **Destinatários > Caixas de correio**.</span><span class="sxs-lookup"><span data-stu-id="14179-180">Open the Exchange admin center (EAC) at <admin.protection.outlook.com/ecp/>, and go to **Recipients > Mailboxes**.</span></span>

5. <span data-ttu-id="14179-181">Encontre e selecione o usuário.</span><span class="sxs-lookup"><span data-stu-id="14179-181">Find and select the select the user.</span></span> <span data-ttu-id="14179-182">No painel de detalhes, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="14179-182">In the details pane, do the following steps:</span></span>

   - <span data-ttu-id="14179-183">Na seção **Recursos de telefone e voz**, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="14179-183">In the **Phone and voice features** section, do the following steps:</span></span>

     - <span data-ttu-id="14179-184">Selecione **Desativar Exchange ActiveSync** e clique em **Sim** no aviso que aparece.</span><span class="sxs-lookup"><span data-stu-id="14179-184">Select **Disable Exchange ActiveSync** and then click **Yes** in the warning that appears.</span></span>
     - <span data-ttu-id="14179-185">Selecione **Desabilitar OWA para Dispositivos** e clique em **Sim** no aviso que aparece.</span><span class="sxs-lookup"><span data-stu-id="14179-185">Select **Disable OWA for Devices** and then click **Yes** in the warning that appears.</span></span>

   - <span data-ttu-id="14179-186">Na seção **Conectividade de e-mail** para Outlook na Web, clique em **Desativar** e clique em **Sim** no aviso que aparece.</span><span class="sxs-lookup"><span data-stu-id="14179-186">In the **Email Connectivity** section for Outlook on the web, click **Disable** and then click **Yes** in the warning that appears.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="14179-187">Etapa 6 Opcional: Remova a conta suspeita de estar comprometida de todos os grupos de funções administrativas</span><span class="sxs-lookup"><span data-stu-id="14179-187">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="14179-188">A associação ao grupo de funções administrativas pode ser restaurada após a conta ter sido protegida.</span><span class="sxs-lookup"><span data-stu-id="14179-188">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="14179-189">Faça o login com uma conta de administrador global:</span><span class="sxs-lookup"><span data-stu-id="14179-189">Sign in with a global administrator account:</span></span>

2. <span data-ttu-id="14179-190">No Centro de administração do Microsoft 365, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="14179-190">In the Microsoft 365 admin center, do the following steps:</span></span>

   1. <span data-ttu-id="14179-191">Vá até **Usuários** \> **Usuários ativos**.</span><span class="sxs-lookup"><span data-stu-id="14179-191">Go to **Users** \> **Active users**.</span></span>
   2. <span data-ttu-id="14179-192">Encontre e selecione a conta do usuário, clique no ![ícone Mais](../../media/ITPro-EAC-MoreOptionsIcon.png) e selecione **Gerenciar funções**.</span><span class="sxs-lookup"><span data-stu-id="14179-192">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Manage roles**.</span></span>
   3. <span data-ttu-id="14179-193">Remova todas as funções administrativas atribuídas à conta.</span><span class="sxs-lookup"><span data-stu-id="14179-193">Remove any administrative roles that are assigned to the account.</span></span> <span data-ttu-id="14179-194">Quando terminar, clique em **Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="14179-194">When you're finished, click **Save changes**.</span></span>

3. <span data-ttu-id="14179-195">No Centro de Segurança e Conformidade em <https://protection.office.com>, execute os seguintes passos:</span><span class="sxs-lookup"><span data-stu-id="14179-195">In the Security & Compliance Center at <https://protection.office.com>, do the following steps:</span></span>

   <span data-ttu-id="14179-196">Selecione **Permissões**, selecione cada grupo de função na lista e procure a conta do usuário na seção **Membros** do menu desdobrável de detalhes que aparece.</span><span class="sxs-lookup"><span data-stu-id="14179-196">Select **Permissions**, select each role group in the list and look for the user account in the **Members** section of the details flyout that appears.</span></span> <span data-ttu-id="14179-197">Se o grupo de funções contiver a conta do usuário, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="14179-197">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="14179-198">a.</span><span class="sxs-lookup"><span data-stu-id="14179-198">a.</span></span> <span data-ttu-id="14179-199">Clique em **Editar** próximo a **Membros**.</span><span class="sxs-lookup"><span data-stu-id="14179-199">Click **Edit** next to **Members**.</span></span>
   <span data-ttu-id="14179-200">b.</span><span class="sxs-lookup"><span data-stu-id="14179-200">b.</span></span> <span data-ttu-id="14179-201">No menu desdobrável **Editando Escolher membros** que aparece, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="14179-201">On the **Editing Choose members** flyout that appears, click **Edit**.</span></span>
   <span data-ttu-id="14179-202">c.</span><span class="sxs-lookup"><span data-stu-id="14179-202">c.</span></span> <span data-ttu-id="14179-203">No menu desdobrável **Escolher membros** que aparece, selecione a conta do usuário e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="14179-203">In the **Choose members** flyout that appears, select the user account, and then click **Remove**.</span></span> <span data-ttu-id="14179-204">Quando terminar, clique em **Concluído**, **Salvar** e depois em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="14179-204">When you're finished, click **Done**, **Save**, and then **Close**.</span></span>

4. <span data-ttu-id="14179-205">Na EAC em <admin.protection.outlook.com/ecp/>, execute os seguintes passos:</span><span class="sxs-lookup"><span data-stu-id="14179-205">In the EAC at <admin.protection.outlook.com/ecp/>, do the following steps:</span></span>

   <span data-ttu-id="14179-206">Selecione **Permissões**, selecione manualmente cada grupo de função e, no painel de detalhes, verifique as contas de usuário na seção **Membros**.</span><span class="sxs-lookup"><span data-stu-id="14179-206">Select **Permissions**, manually select each role group, and in the details pane, verify the user accounts in the **Members** section.</span></span>  <span data-ttu-id="14179-207">Se o grupo de funções contiver a conta do usuário, execute as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="14179-207">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="14179-208">a.</span><span class="sxs-lookup"><span data-stu-id="14179-208">a.</span></span> <span data-ttu-id="14179-209">Selecione o grupo de funções, clique em **Editar** ![ícone Editar](../../media/ITPro-EAC-EditIcon.png).</span><span class="sxs-lookup"><span data-stu-id="14179-209">Select the role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>
   <span data-ttu-id="14179-210">b.</span><span class="sxs-lookup"><span data-stu-id="14179-210">b.</span></span> <span data-ttu-id="14179-211">Na seção **Membro**, selecione a conta do usuário e clique em **Remover** ![ícone Remover](../../media/ITPro-EAC-RemoveIcon.gif).</span><span class="sxs-lookup"><span data-stu-id="14179-211">In the **Member** section, select the user account, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span> <span data-ttu-id="14179-212">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="14179-212">When you're finished, click **Save**.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="14179-213">Etapa 7 Opcional: etapas adicionais de precaução</span><span class="sxs-lookup"><span data-stu-id="14179-213">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="14179-214">Certifique-se de verificar seus itens enviados.</span><span class="sxs-lookup"><span data-stu-id="14179-214">Make sure that you verify your sent items.</span></span> <span data-ttu-id="14179-215">Você poderá ter que informar às pessoas em sua lista de contatos que sua conta foi comprometida.</span><span class="sxs-lookup"><span data-stu-id="14179-215">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="14179-216">O invasor pode ter pedido dinheiro, forjando, por exemplo, que você estaria preso em um país diferente e precisaria de dinheiro, ou o invasor pode ter enviado um vírus para comprometer seus computadores também.</span><span class="sxs-lookup"><span data-stu-id="14179-216">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="14179-217">Qualquer outro serviço que tenha usado essa conta do Exchange como sua conta de email alternativa pode ter sido comprometido.</span><span class="sxs-lookup"><span data-stu-id="14179-217">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="14179-218">Primeiro, realize estas etapas para sua assinatura do Microsoft 365 e, em seguida, realize estas etapas para suas outras contas.</span><span class="sxs-lookup"><span data-stu-id="14179-218">First, do these steps for your Microsoft 365 subscription, and then do these steps for your other accounts.</span></span>

3. <span data-ttu-id="14179-219">Certifique-se de que suas informações de contato, como números de telefone e endereços, estejam corretas.</span><span class="sxs-lookup"><span data-stu-id="14179-219">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="14179-220">Proteja o Microsoft 365 como um profissional de segurança cibernética</span><span class="sxs-lookup"><span data-stu-id="14179-220">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="14179-221">Sua assinatura do Microsoft 365 vem com um poderoso conjunto de recursos de segurança que você pode usar para proteger seus dados e seus usuários.</span><span class="sxs-lookup"><span data-stu-id="14179-221">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="14179-222">Use o [roteiro de segurança do Microsoft 365: principais prioridades para os primeiros 30 dias, 90 dias e depois](security-roadmap.md) para implementar práticas recomendadas para proteger o seu locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14179-222">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="14179-223">Tarefas a realizar nos primeiros 30 dias.</span><span class="sxs-lookup"><span data-stu-id="14179-223">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="14179-224">Estas têm efeito imediato e baixo impacto para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="14179-224">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="14179-225">Tarefas para realizar em 90 dias.</span><span class="sxs-lookup"><span data-stu-id="14179-225">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="14179-226">Estas levam um pouco mais de tempo para planejar e implementar, mas melhoram muito sua postura de segurança.</span><span class="sxs-lookup"><span data-stu-id="14179-226">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="14179-227">Além de 90 dias.</span><span class="sxs-lookup"><span data-stu-id="14179-227">Beyond 90 days.</span></span> <span data-ttu-id="14179-228">Estes aprimoramentos são desenvolvidos nos seus primeiros 90 dias de trabalho.</span><span class="sxs-lookup"><span data-stu-id="14179-228">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="14179-229">Confira também</span><span class="sxs-lookup"><span data-stu-id="14179-229">See also</span></span>

- [<span data-ttu-id="14179-230">Detectar e corrigir ataques de injeção a regras e formulários personalizados do Outlook no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="14179-230">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Microsoft 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="14179-231">Centro de Reclamações contra Crimes pela Internet</span><span class="sxs-lookup"><span data-stu-id="14179-231">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/preventiontips.aspx)

- [<span data-ttu-id="14179-232">Comissão de Valores Mobiliários - Fraude de "Phishing"</span><span class="sxs-lookup"><span data-stu-id="14179-232">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="14179-233">Para denunciar emails de spam diretamente ao seu administrador e à Microsoft [Use o suplemento Reportar mensagem](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="14179-233">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>
