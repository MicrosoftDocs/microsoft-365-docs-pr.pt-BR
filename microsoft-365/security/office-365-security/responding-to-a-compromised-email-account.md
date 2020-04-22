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
ms.custom: TopSMBIssues
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Aprenda como reconhecer e responder a uma conta de email comprometida no Microsoft 365
ms.openlocfilehash: 65e3827b578eec2f851c45d9acc69fb7132d01b8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634335"
---
# <a name="responding-to-a-compromised-email-account"></a><span data-ttu-id="0100d-103">Responder a uma conta de email comprometida</span><span class="sxs-lookup"><span data-stu-id="0100d-103">Responding to a Compromised Email Account</span></span>

<span data-ttu-id="0100d-104">**Resumo** Aprenda como reconhecer e responder a uma conta de email comprometida no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0100d-104">**Summary** Learn how to recognize and respond to a compromised email account in Microsoft 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a><span data-ttu-id="0100d-105">O que é uma conta de email comprometida no Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="0100d-105">What is a Compromised Email Account in Microsoft 365?</span></span>

<span data-ttu-id="0100d-106">O acesso a caixas de correio, dados e outros serviços do Microsoft 365 é controlado pelo uso de credenciais, por exemplo, um nome de usuários e senha ou PIN.</span><span class="sxs-lookup"><span data-stu-id="0100d-106">Access to Microsoft 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="0100d-107">Quando alguém que não seja o usuário pretendido rouba essas credenciais, as credenciais roubadas são consideradas comprometidas.</span><span class="sxs-lookup"><span data-stu-id="0100d-107">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="0100d-108">Com elas, o invasor pode entrar como o usuário original e executar ações ilícitas.</span><span class="sxs-lookup"><span data-stu-id="0100d-108">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="0100d-109">Usando as credenciais roubadas, o invasor pode acessar a caixa de correio do Microsoft 365, as pastas do SharePoint ou os arquivos no OneDrive do usuário.</span><span class="sxs-lookup"><span data-stu-id="0100d-109">Using the stolen credentials, the attacker can access the user's Microsoft 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="0100d-110">Uma ação comumente vista é o invasor enviar emails como o usuário original para os destinatários dentro e fora da organização.</span><span class="sxs-lookup"><span data-stu-id="0100d-110">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="0100d-111">Quando o invasor envia dados por email para destinatários externos, isso é chamado de exfiltração de dados.</span><span class="sxs-lookup"><span data-stu-id="0100d-111">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a><span data-ttu-id="0100d-112">Sintomas de uma conta de email da Microsoft comprometida</span><span class="sxs-lookup"><span data-stu-id="0100d-112">Symptoms of a Compromised Microsoft Email Account</span></span>

<span data-ttu-id="0100d-113">Os usuários pode notar e relatar atividades incomuns em suas caixas de correio do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0100d-113">Users might notice and report unusual activity in their Microsoft 365 mailboxes.</span></span> <span data-ttu-id="0100d-114">Veja alguns sintomas comuns:</span><span class="sxs-lookup"><span data-stu-id="0100d-114">Here are some common symptoms:</span></span>

- <span data-ttu-id="0100d-115">Atividade suspeita, como emails ausentes ou excluídos.</span><span class="sxs-lookup"><span data-stu-id="0100d-115">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="0100d-116">Outros usuários podem receber emails da conta comprometida sem o email correspondente estar na pasta **Itens Enviados** do remetente.</span><span class="sxs-lookup"><span data-stu-id="0100d-116">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="0100d-117">A presença de regras de caixa de entrada que não foram criadas pelo usuário pretendido ou pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="0100d-117">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="0100d-118">Essas regras podem encaminhar emails automaticamente para endereços desconhecidos ou movê-los para as pastas **Anotações**, **Lixo Eletrônico** ou **Assinaturas RSS**.</span><span class="sxs-lookup"><span data-stu-id="0100d-118">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="0100d-119">O nome de exibição do usuário pode ser alterado na Lista Global de Endereços.</span><span class="sxs-lookup"><span data-stu-id="0100d-119">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="0100d-120">A caixa de correio se encontra impedida de enviar emails.</span><span class="sxs-lookup"><span data-stu-id="0100d-120">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="0100d-121">As pastas Itens Enviados ou Excluídos no Microsoft Outlook ou Outlook na Web (anteriormente conhecido como Outlook Web App) contêm mensagens comuns de contas invadidas, como "Estou preso em Londres, envie dinheiro".</span><span class="sxs-lookup"><span data-stu-id="0100d-121">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="0100d-122">Mudanças incomuns no perfil, como o nome, o número de telefone ou o CEP atualizados.</span><span class="sxs-lookup"><span data-stu-id="0100d-122">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="0100d-123">Mudanças de credenciais incomuns, como várias alterações de senha necessárias.</span><span class="sxs-lookup"><span data-stu-id="0100d-123">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="0100d-124">Encaminhamento de email adicionado recentemente.</span><span class="sxs-lookup"><span data-stu-id="0100d-124">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="0100d-125">Uma assinatura incomum adicionada recentemente, como uma assinatura bancária falsa ou uma assinatura de medicamento de receita obrigatória.</span><span class="sxs-lookup"><span data-stu-id="0100d-125">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="0100d-126">Se um usuário relatar algum dos sintomas acima, você deverá realizar uma investigação adicional.</span><span class="sxs-lookup"><span data-stu-id="0100d-126">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="0100d-127">O Centro de Conformidade e Segurança do Microsoft 365 e o Portal do Azure oferecem ferramentas para ajudá-lo a investigar a atividade de uma conta de usuário que você suspeita estar comprometida.</span><span class="sxs-lookup"><span data-stu-id="0100d-127">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="0100d-128">**Logs de auditoria unificada no Centro de Conformidade e Segurança**: analise todas as atividades na conta suspeita, filtrando os resultados para o intervalo de datas desde imediatamente antes da atividade suspeita ocorrer até a data atual.</span><span class="sxs-lookup"><span data-stu-id="0100d-128">**Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="0100d-129">Não filtre as atividades durante a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0100d-129">Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="0100d-130">**Logs de auditoria do administrador no EAC**: no Exchange Online, você pode usar o EAC (Centro de administração do Exchange) para procurar e exibir entradas no log de auditoria do administrador.</span><span class="sxs-lookup"><span data-stu-id="0100d-130">**Admin Audit logs in the EAC**: In Exchange Online, you can use the Exchange admin center (EAC) to search for and view entries in the administrator audit log.</span></span> <span data-ttu-id="0100d-131">O log de auditoria do administrador registra ações específicas, com base no cmdlet do PowerShell do Exchange Online, executadas por administradores e usuários que receberam privilégios administrativos.</span><span class="sxs-lookup"><span data-stu-id="0100d-131">The administrator audit log records specific actions, based on Exchange Online PowerShell cmdlets, performed by administrators and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="0100d-132">As entradas do log de auditoria do administrador fornecem informações sobre qual cmdlet foi executado, quais parâmetros foram usados, quem executou o cmdlet e quais objetos foram afetados.</span><span class="sxs-lookup"><span data-stu-id="0100d-132">Entries in the administrator audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

- <span data-ttu-id="0100d-133">**Registros de entrada do Azure AD e outros relatórios de risco no portal do Azure AD**: examine os valores destas colunas:</span><span class="sxs-lookup"><span data-stu-id="0100d-133">**Azure AD Sign-in logs and other risk reports in the Azure AD portal**: Examine the values in these columns:</span></span>

  - <span data-ttu-id="0100d-134">Revise o endereço IP</span><span class="sxs-lookup"><span data-stu-id="0100d-134">Review IP address</span></span>

  - <span data-ttu-id="0100d-135">locais de entrada</span><span class="sxs-lookup"><span data-stu-id="0100d-135">sign-in locations</span></span>

  - <span data-ttu-id="0100d-136">horários de entrada</span><span class="sxs-lookup"><span data-stu-id="0100d-136">sign-in times</span></span>

  - <span data-ttu-id="0100d-137">sucesso ou falha de entrada</span><span class="sxs-lookup"><span data-stu-id="0100d-137">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a><span data-ttu-id="0100d-138">Como proteger e restaurar a funcionalidade de email de uma conta e caixa de correio do Microsoft 365 suspeitas de estarem comprometidas</span><span class="sxs-lookup"><span data-stu-id="0100d-138">How to secure and restore email function to a suspected compromised Microsoft 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="0100d-139">Mesmo depois de ter recuperado o acesso à sua conta, o invasor pode ter adicionado entradas secundárias que permitem que ele retome o controle da conta.</span><span class="sxs-lookup"><span data-stu-id="0100d-139">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="0100d-140">Você deve realizar todas as etapas a seguir para recuperar o acesso à sua conta quanto antes, para garantir que o invasor não volte a controlar sua conta.</span><span class="sxs-lookup"><span data-stu-id="0100d-140">You must perform all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="0100d-141">Essas etapas ajudam você a remover todas as entradas secundárias que o sequestrador pode ter adicionado à sua conta.</span><span class="sxs-lookup"><span data-stu-id="0100d-141">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="0100d-142">Depois de realizar essas etapas, recomendamos que você execute uma verificação de vírus para garantir que seu computador não esteja comprometido.</span><span class="sxs-lookup"><span data-stu-id="0100d-142">After you perform these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="0100d-143">Etapa 1 Redefina a senha do usuário</span><span class="sxs-lookup"><span data-stu-id="0100d-143">Step 1 Reset the user's password</span></span>

> [!WARNING]
> <span data-ttu-id="0100d-144">Não envie a nova senha para o usuário pretendido por email, pois o invasor ainda terá acesso à caixa de correio neste momento.</span><span class="sxs-lookup"><span data-stu-id="0100d-144">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>

1. <span data-ttu-id="0100d-145">Siga os procedimentos para redefinir uma senha corporativa dos Aplicativos do Microsoft 365 de outra pessoa em [Redefinir senhas corporativas dos Aplicativos do Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/reset-passwords)</span><span class="sxs-lookup"><span data-stu-id="0100d-145">Follow the Reset a Microsoft 365 Apps for business password for someone else procedures in [Reset Microsoft 365 Apps for business passwords](https://docs.microsoft.com/office365/admin/add-users/reset-passwords)</span></span>

<span data-ttu-id="0100d-146">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="0100d-146">**Notes**:</span></span>

- <span data-ttu-id="0100d-147">Certifique-se de que a senha seja forte e que contenha letras maiúsculas e minúsculas, pelo menos um número e pelo menos um caractere especial.</span><span class="sxs-lookup"><span data-stu-id="0100d-147">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>

- <span data-ttu-id="0100d-148">Não reutilize nenhuma das suas últimas cinco senhas.</span><span class="sxs-lookup"><span data-stu-id="0100d-148">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="0100d-149">Mesmo que o requisito do histórico de senhas permita a reutilização de uma senha mais recente, você deve selecionar algo que o invasor não consiga adivinhar.</span><span class="sxs-lookup"><span data-stu-id="0100d-149">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>

- <span data-ttu-id="0100d-150">Se a sua identidade local for federada com o Microsoft 365, será necessário alterar sua senha no local e, em seguida, notificar o administrador sobre o comprometimento.</span><span class="sxs-lookup"><span data-stu-id="0100d-150">If your on-premises identity is federated with Microsoft 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>

> [!TIP]
> <span data-ttu-id="0100d-151">É altamente recomendável que você ative a Autenticação Multifator (MFA) para evitar comprometimentos, especialmente para contas com privilégios administrativos.</span><span class="sxs-lookup"><span data-stu-id="0100d-151">We highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span>  <span data-ttu-id="0100d-152">É possível saber mais sobre o MFA[aqui ](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span><span class="sxs-lookup"><span data-stu-id="0100d-152">You can learn more about MFA [here](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="0100d-153">Etapa 2 Remover endereços de encaminhamento de email suspeitos</span><span class="sxs-lookup"><span data-stu-id="0100d-153">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="0100d-154">Abra o **Centro de administração do Microsoft 365 > Usuários Ativos**.</span><span class="sxs-lookup"><span data-stu-id="0100d-154">Open the **Microsoft 365 admin center > Active Users**.</span></span>

2. <span data-ttu-id="0100d-155">Encontre a conta de usuário em questão e expanda **Configurações de Email**.</span><span class="sxs-lookup"><span data-stu-id="0100d-155">Find the user account in question and expand **Mail Settings**.</span></span>

3. <span data-ttu-id="0100d-156">Para o **encaminhamento de Email**, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0100d-156">For **Email forwarding**, click **Edit**.</span></span>

4. <span data-ttu-id="0100d-157">Remova todos os endereços de encaminhamento suspeitos.</span><span class="sxs-lookup"><span data-stu-id="0100d-157">Remove any suspicious forwarding addresses.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="0100d-158">Etapa 3 Desabilite todas as regras de caixa de entrada suspeitas</span><span class="sxs-lookup"><span data-stu-id="0100d-158">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="0100d-159">Entre na caixa de correio do usuário usando o Outlook na web.</span><span class="sxs-lookup"><span data-stu-id="0100d-159">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="0100d-160">Clique no ícone de engrenagem e clique em **Email**.</span><span class="sxs-lookup"><span data-stu-id="0100d-160">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="0100d-161">Clique em **Regras de caixa de entrada e limpeza** e revise as regras.</span><span class="sxs-lookup"><span data-stu-id="0100d-161">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="0100d-162">Desative ou exclua regras suspeitas.</span><span class="sxs-lookup"><span data-stu-id="0100d-162">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="0100d-163">Etapa 4 Desbloqueie o usuário de enviar emails</span><span class="sxs-lookup"><span data-stu-id="0100d-163">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="0100d-164">Se a caixa de correio suspeita de estar comprometida foi usada ilicitamente para enviar emails de spam, é provável que esta tenha sido impedida de enviar emails.</span><span class="sxs-lookup"><span data-stu-id="0100d-164">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="0100d-165">Para desbloquear uma caixa de correio impedida de enviar emails, siga os procedimentos em [Removendo um usuário do portal de usuários restritos após o envio de emails de spam](removing-user-from-restricted-users-portal-after-spam.md).</span><span class="sxs-lookup"><span data-stu-id="0100d-165">To unblock a mailbox from sending mail, follow the procedures in [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="0100d-166">Etapa 5 Opcional: bloqueie a conta de usuário no login</span><span class="sxs-lookup"><span data-stu-id="0100d-166">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0100d-167">Você pode impedir que a conta suspeita de estar comprometida inicie sessão, até considerar que é seguro reativar o acesso.</span><span class="sxs-lookup"><span data-stu-id="0100d-167">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="0100d-168">Vá para o centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0100d-168">Go to the Microsoft 365 admin center.</span></span>

2. <span data-ttu-id="0100d-169">No centro de administração do Microsoft 365, selecione **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="0100d-169">In the Microsoft 365 admin center, select **Users**.</span></span>

3. <span data-ttu-id="0100d-170">Selecione o funcionário que deseja bloquear e escolha **Editar**, ao lado do **Status de entrada**, no painel de usuário.</span><span class="sxs-lookup"><span data-stu-id="0100d-170">Select the employee that you want to block, and then choose **Edit** next to **Sign-in status** in the user pane.</span></span>

4. <span data-ttu-id="0100d-171">No painel **Status de entrada**, escolha **Entrada bloqueada** e **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0100d-171">On the **Sign-in status** pane, choose **Sign-in blocked** and then **Save**.</span></span>

5. <span data-ttu-id="0100d-172">No centro de Administração, no painel de navegação inferior esquerdo, expanda **Centros de Administração** e selecione **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="0100d-172">In the Admin center, in the lower-left navigation pane, expand **Admin Centers** and select **Exchange**.</span></span>

6. <span data-ttu-id="0100d-173">No centro de administração do Exchange, navegue até **Destinatários> Caixas de Correio**.</span><span class="sxs-lookup"><span data-stu-id="0100d-173">In the Exchange admin center, navigate to **Recipients > Mailboxes**.</span></span>

7. <span data-ttu-id="0100d-174">Selecione o usuário e, na página de propriedades do usuário, em **Dispositivos Móveis**, clique em **Desabilitar Exchange ActivcSync** e **Desabilitar OWA para Dispositivos** e responda **sim** a ambos.</span><span class="sxs-lookup"><span data-stu-id="0100d-174">Select the user, and on the user properties page, under **Mobile Devices**, click **Disable Exchange ActivcSync** and **Disable OWA for Devices** and answer **yes** to both.</span></span>

8. <span data-ttu-id="0100d-175">Em **Conectividade de Email**, **Desativar** e responda **sim**.</span><span class="sxs-lookup"><span data-stu-id="0100d-175">Under **Email Connectivity**, **Disable** and answer **yes**.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="0100d-176">Etapa 6 Opcional: Remova a conta suspeita de estar comprometida de todos os grupos de funções administrativas</span><span class="sxs-lookup"><span data-stu-id="0100d-176">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="0100d-177">A associação ao grupo de funções administrativas pode ser restaurada após a conta ter sido protegida.</span><span class="sxs-lookup"><span data-stu-id="0100d-177">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="0100d-178">Entre no centro de administração do Microsoft 365 com uma conta de administrador global e abra **Usuários Ativos**.</span><span class="sxs-lookup"><span data-stu-id="0100d-178">Sign in to the Microsoft 365 admin center with a global administrator account and open **Active Users**.</span></span>

2. <span data-ttu-id="0100d-179">Encontre a conta suspeita de estar comprometida e verifique manualmente se há alguma função administrativa atribuída à conta.</span><span class="sxs-lookup"><span data-stu-id="0100d-179">Find the suspected compromised account and manually check to see if there are any administrative roles assigned to the account.</span></span>

3. <span data-ttu-id="0100d-180">Abra o **Centro de Conformidade e Segurança**.</span><span class="sxs-lookup"><span data-stu-id="0100d-180">Open the **Security & Compliance Center**.</span></span>

4. <span data-ttu-id="0100d-181">Clique em **Permissões**.</span><span class="sxs-lookup"><span data-stu-id="0100d-181">Click **Permissions**.</span></span>

5. <span data-ttu-id="0100d-182">Reveja manualmente os grupos de funções para ver se a conta suspeita de estar comprometida é um membro de qualquer um deles.</span><span class="sxs-lookup"><span data-stu-id="0100d-182">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span>  <span data-ttu-id="0100d-183">Caso seja:</span><span class="sxs-lookup"><span data-stu-id="0100d-183">If it is:</span></span>

   <span data-ttu-id="0100d-184">a.</span><span class="sxs-lookup"><span data-stu-id="0100d-184">a.</span></span> <span data-ttu-id="0100d-185">Clique no grupo de funções e clique em **Editar Grupo de Funções**.</span><span class="sxs-lookup"><span data-stu-id="0100d-185">Click the role group and click **Edit Role Group**.</span></span>

   <span data-ttu-id="0100d-186">b.</span><span class="sxs-lookup"><span data-stu-id="0100d-186">b.</span></span> <span data-ttu-id="0100d-187">Clique em **Escolher Membros** e **Editar** para remover o usuário do grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="0100d-187">Click **Chose Members** and **Edit** to remove the user from the role group.</span></span>

6. <span data-ttu-id="0100d-188">Abra o **centro de administração do Exchange**.</span><span class="sxs-lookup"><span data-stu-id="0100d-188">Open the **Exchange admin center**.</span></span>

7. <span data-ttu-id="0100d-189">Clique em **Permissões**.</span><span class="sxs-lookup"><span data-stu-id="0100d-189">Click **Permissions**.</span></span>

8. <span data-ttu-id="0100d-190">Reveja manualmente os grupos de funções para ver se a conta suspeita de estar comprometida é um membro de qualquer um deles.</span><span class="sxs-lookup"><span data-stu-id="0100d-190">Manually review the role groups to see if the suspected compromised account is a member of any of them.</span></span> <span data-ttu-id="0100d-191">Caso seja:</span><span class="sxs-lookup"><span data-stu-id="0100d-191">If it is:</span></span>

   <span data-ttu-id="0100d-192">a.</span><span class="sxs-lookup"><span data-stu-id="0100d-192">a.</span></span> <span data-ttu-id="0100d-193">Clique no grupo de funções e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0100d-193">Click the role group and click **Edit**.</span></span>

   <span data-ttu-id="0100d-194">b.</span><span class="sxs-lookup"><span data-stu-id="0100d-194">b.</span></span> <span data-ttu-id="0100d-195">Use a seção de **membros** para remover o usuário do grupo de funções.</span><span class="sxs-lookup"><span data-stu-id="0100d-195">Use the **members** section to remove the user from the role group.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="0100d-196">Etapa 7 Opcional: etapas adicionais de precaução</span><span class="sxs-lookup"><span data-stu-id="0100d-196">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="0100d-197">Certifique-se de verificar seus itens enviados.</span><span class="sxs-lookup"><span data-stu-id="0100d-197">Make sure that you verify your sent items.</span></span> <span data-ttu-id="0100d-198">Você poderá ter que informar às pessoas em sua lista de contatos que sua conta foi comprometida.</span><span class="sxs-lookup"><span data-stu-id="0100d-198">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="0100d-199">O invasor pode ter pedido dinheiro, forjando, por exemplo, que você estaria preso em um país diferente e precisaria de dinheiro, ou o invasor pode ter enviado um vírus para comprometer seus computadores também.</span><span class="sxs-lookup"><span data-stu-id="0100d-199">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="0100d-200">Qualquer outro serviço que tenha usado essa conta do Exchange como sua conta de email alternativa pode ter sido comprometido.</span><span class="sxs-lookup"><span data-stu-id="0100d-200">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="0100d-201">Primeiro, realize estas etapas para sua assinatura do Microsoft 365 e, em seguida, realize estas etapas para suas outras contas.</span><span class="sxs-lookup"><span data-stu-id="0100d-201">First, perform these steps for your Microsoft 365 subscription, and then perform these steps for your other accounts.</span></span>

3. <span data-ttu-id="0100d-202">Certifique-se de que suas informações de contato, como números de telefone e endereços, estejam corretas.</span><span class="sxs-lookup"><span data-stu-id="0100d-202">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="0100d-203">Proteja o Microsoft 365 como um profissional de segurança cibernética</span><span class="sxs-lookup"><span data-stu-id="0100d-203">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="0100d-204">Sua assinatura do Microsoft 365 vem com um poderoso conjunto de recursos de segurança que você pode usar para proteger seus dados e seus usuários.</span><span class="sxs-lookup"><span data-stu-id="0100d-204">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="0100d-205">Use o [roteiro de segurança do Microsoft 365: principais prioridades para os primeiros 30 dias, 90 dias e depois](security-roadmap.md) para implementar práticas recomendadas para proteger o seu locatário do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0100d-205">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="0100d-206">Tarefas a realizar nos primeiros 30 dias.</span><span class="sxs-lookup"><span data-stu-id="0100d-206">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="0100d-207">Estas têm efeito imediato e baixo impacto para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="0100d-207">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="0100d-208">Tarefas para realizar em 90 dias.</span><span class="sxs-lookup"><span data-stu-id="0100d-208">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="0100d-209">Estas levam um pouco mais de tempo para planejar e implementar, mas melhoram muito sua postura de segurança.</span><span class="sxs-lookup"><span data-stu-id="0100d-209">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="0100d-210">Além de 90 dias.</span><span class="sxs-lookup"><span data-stu-id="0100d-210">Beyond 90 days.</span></span> <span data-ttu-id="0100d-211">Estes aprimoramentos são desenvolvidos nos seus primeiros 90 dias de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0100d-211">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="0100d-212">Confira também</span><span class="sxs-lookup"><span data-stu-id="0100d-212">See also</span></span>

- [<span data-ttu-id="0100d-213">Detectar e corrigir ataques de injeção a regras e formulários personalizados do Outlook no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0100d-213">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Microsoft 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="0100d-214">Centro de Reclamações contra Crimes pela Internet</span><span class="sxs-lookup"><span data-stu-id="0100d-214">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/preventiontips.aspx)

- [<span data-ttu-id="0100d-215">Comissão de Valores Mobiliários - Fraude de "Phishing"</span><span class="sxs-lookup"><span data-stu-id="0100d-215">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="0100d-216">Para denunciar emails de spam diretamente ao seu administrador e à Microsoft [Use o suplemento Reportar mensagem](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="0100d-216">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>
