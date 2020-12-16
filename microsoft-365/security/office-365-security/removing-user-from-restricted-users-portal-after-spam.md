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
ms.openlocfilehash: bca9366fdb8cacdc58c12757e870c8ead8f1fa7a
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683040"
---
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-office-365"></a><span data-ttu-id="7138f-104">Remover usuários bloqueados do portal Usuários restritos no Office 365</span><span class="sxs-lookup"><span data-stu-id="7138f-104">Remove blocked users from the Restricted Users portal in Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7138f-105">Se um usuário exceder um dos limites de envio de saída, conforme especificado nos [limites de serviço](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) ou nas [políticas de spam de saída](configure-the-outbound-spam-policy.md), o usuário será impedido de enviar e-mails, mas ainda poderá receber e-mails.</span><span class="sxs-lookup"><span data-stu-id="7138f-105">If a user exceeds one of the outbound sending limits as specified in [the service limits](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="7138f-106">O usuário é adicionado ao portal Usuários Restritos no Centro de conformidade e segurança.</span><span class="sxs-lookup"><span data-stu-id="7138f-106">The user is added to the Restricted Users portal in the Security & Compliance Center.</span></span> <span data-ttu-id="7138f-107">Ao tentarem enviar e-mails, a mensagem é retornada em um relatório de falha na entrega (também conhecido como NDR ou mensagens de devolução) com o código de erro [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) e o seguinte texto:</span><span class="sxs-lookup"><span data-stu-id="7138f-107">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](https://docs.microsoft.com/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="7138f-108">"A mensagem não pôde ser entregue porque você não foi reconhecido como um remetente válido.</span><span class="sxs-lookup"><span data-stu-id="7138f-108">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="7138f-109">O motivo mais comum para isso é que seu endereço de email é suspeito de enviar spam e não tem mais permissão para enviar emails.</span><span class="sxs-lookup"><span data-stu-id="7138f-109">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="7138f-110">Fale com o administrador para obter assistência.</span><span class="sxs-lookup"><span data-stu-id="7138f-110">Contact  your email admin for assistance.</span></span> <span data-ttu-id="7138f-111">O servidor remoto retornou ' 550 5.1.8 acesso negado, remetente de saída incorreto ".</span><span class="sxs-lookup"><span data-stu-id="7138f-111">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="7138f-112">Os administradores podem remover usuários do portal Remetentes restritos no Centro de conformidade e segurança ou no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7138f-112">Admins can remove users from the Restricted Senders portal in the Security & Compliance Center or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7138f-113">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="7138f-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7138f-114">Você abrir o Centro de conformidade e segurança em <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="7138f-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="7138f-115">Para ir diretamente para a página **Usuários restritos**, use <https://protection.office.com/restrictedusers>.</span><span class="sxs-lookup"><span data-stu-id="7138f-115">To go directly to the **Restricted Users** page, use <https://protection.office.com/restrictedusers>.</span></span>

- <span data-ttu-id="7138f-116">Para se conectar ao Windows PowerShell do Exchange Online, confira [Conectar ao Windows PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7138f-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="7138f-117">Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="7138f-117">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="7138f-118">Para remover usuários do portal do Usuários Restritos, você precisa ser membro dos grupos de funções **Gerenciamento da Organização** ou **Administrador de Segurança**.</span><span class="sxs-lookup"><span data-stu-id="7138f-118">To remove users from the Restricted Users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="7138f-119">Para acesso somente para leitura do portal de Usuários Restritos, você precisa ser membro dos grupos de função **Leitor Global** ou **Leitor de Segurança**.</span><span class="sxs-lookup"><span data-stu-id="7138f-119">For read-only access to the Restricted Users portal, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="7138f-120">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7138f-120">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="7138f-121">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="7138f-121">**Notes**:</span></span>

  - <span data-ttu-id="7138f-122">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7138f-122">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="7138f-123">Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="7138f-123">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="7138f-124">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="7138f-124">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="7138f-125">Um remetente que exceder os limites de email de saída é um indicador de uma conta comprometida.</span><span class="sxs-lookup"><span data-stu-id="7138f-125">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="7138f-126">Antes de remover o usuário do portal Usuários Restritos, siga as etapas necessárias para recuperar o controle da sua conta.</span><span class="sxs-lookup"><span data-stu-id="7138f-126">Before you remove the user from the Restricted Users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="7138f-127">Para obter mais informações, consulte [Responder a uma conta de e-mail comprometida no Office 365.](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="7138f-127">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-security--compliance-center-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="7138f-128">Use o Centro de conformidade e segurança para remover um usuário da lista Usuários restritos</span><span class="sxs-lookup"><span data-stu-id="7138f-128">Use the Security & Compliance Center to remove a user from the Restricted Users list</span></span>

1. <span data-ttu-id="7138f-129">No Centro de conformidade e segurança, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Usuários restritos**.</span><span class="sxs-lookup"><span data-stu-id="7138f-129">In the Security & Compliance Center, go to **Threat management** \> **Review** \> **Restricted users**.</span></span>

2. <span data-ttu-id="7138f-130">Encontre e selecione o usuário que você quer desbloquear.</span><span class="sxs-lookup"><span data-stu-id="7138f-130">Find and select the user that you want to unblock.</span></span> <span data-ttu-id="7138f-131">Na coluna **Ações**, clique em **Desbloquear**.</span><span class="sxs-lookup"><span data-stu-id="7138f-131">In the **Actions** column, click **Unblock**.</span></span>

3. <span data-ttu-id="7138f-132">Um menu suspenso entrará em detalhes sobre a conta cujo envio é restrito.</span><span class="sxs-lookup"><span data-stu-id="7138f-132">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="7138f-133">Você deve percorrer as recomendações para garantir que você esteja tomando as ações adequadas caso a conta seja realmente comprometida.</span><span class="sxs-lookup"><span data-stu-id="7138f-133">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="7138f-134">Quando terminar, escolha **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="7138f-134">Click **Next** when done.</span></span>

4. <span data-ttu-id="7138f-135">A tela seguinte tem recomendações para ajudar a evitar o futuro compromisso.</span><span class="sxs-lookup"><span data-stu-id="7138f-135">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="7138f-136">A habilitação da autenticação multifator (MFA) e a alteração das senhas são uma boa defesa.</span><span class="sxs-lookup"><span data-stu-id="7138f-136">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="7138f-137">Clique em **desbloquear usuário** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="7138f-137">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="7138f-138">Clique em **Sim** para confirmar a alteração.</span><span class="sxs-lookup"><span data-stu-id="7138f-138">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7138f-139">Pode levar até 30 minutos para que as restrições sejam removidas.</span><span class="sxs-lookup"><span data-stu-id="7138f-139">It may take 30 minutes or more before restrictions are removed.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="7138f-140">Verifique as configurações de alertados usuários restritos</span><span class="sxs-lookup"><span data-stu-id="7138f-140">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="7138f-141">A política de alerta padrão denominada **Usuário impedido de enviar e-mails** notificará automaticamente os administradores quando os usuários forem impedidos de enviar e-mails de saída.</span><span class="sxs-lookup"><span data-stu-id="7138f-141">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="7138f-142">Você pode verificar essas configurações e adicionar usuários adicionais para notificar.</span><span class="sxs-lookup"><span data-stu-id="7138f-142">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="7138f-143">Para obter mais informações sobre políticas de alerta, consulte [Políticas de alerta no centro de segurança e conformidade.](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7138f-143">For more information about alert policies, see [Alert policies in the security and compliance center](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7138f-144">Para que os alertas funcionem, a pesquisa de logs de auditoria deve ser ativada.</span><span class="sxs-lookup"><span data-stu-id="7138f-144">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="7138f-145">Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="7138f-145">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="7138f-146">No Centro de conformidade e segurança, acesse **Alertas** \>**Políticas de alerta**.</span><span class="sxs-lookup"><span data-stu-id="7138f-146">In the Security & Compliance Center, go to **Alerts** \> **Alert policies**.</span></span>

2. <span data-ttu-id="7138f-147">Localize e selecione o alerta **Usuário impedido de enviar e-mails**.</span><span class="sxs-lookup"><span data-stu-id="7138f-147">Find an select the **User restricted from sending email** alert.</span></span>

3. <span data-ttu-id="7138f-148">No submenu desdobrável exibido, verifique ou defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="7138f-148">In the flyout that appears, verify or configure the following settings:</span></span>

   - <span data-ttu-id="7138f-149">**Status**: Verifique se o alerta está ativado como ![Alternância](../../media/scc-toggle-on.png).</span><span class="sxs-lookup"><span data-stu-id="7138f-149">**Status**: Verify the alert is turned on ![Toggle on](../../media/scc-toggle-on.png).</span></span>

   - <span data-ttu-id="7138f-150">**Destinatários de e-mails**: Clique em **Editar** e verifique ou defina as seguintes configurações no menu **Editar destinatários** que é exibido:</span><span class="sxs-lookup"><span data-stu-id="7138f-150">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>

     - <span data-ttu-id="7138f-151">**Enviar notificações por e-mail**: verificar se a caixa de seleção está marcada como (**Ativada**).</span><span class="sxs-lookup"><span data-stu-id="7138f-151">**Send email notifications**: Verify the check box is selected (**On**).</span></span>

     - <span data-ttu-id="7138f-152">**Destinatários de e-mails**: o valor padrão é **TenantAdmins** (ou seja, membros de **Administração global**).</span><span class="sxs-lookup"><span data-stu-id="7138f-152">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="7138f-153">Para adicionar mais destinatários, clique em uma área em branco da caixa.</span><span class="sxs-lookup"><span data-stu-id="7138f-153">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="7138f-154">Uma lista de destinatários será exibida e você poderá começar a digitar um nome para filtrar e selecionar um destinatário.</span><span class="sxs-lookup"><span data-stu-id="7138f-154">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="7138f-155">Você pode remover um destinatário existente da caixa clicando no ![ícone Remover](../../media/scc-remove-icon.png) ao lado do nome.</span><span class="sxs-lookup"><span data-stu-id="7138f-155">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/scc-remove-icon.png) next to their name.</span></span>

     - <span data-ttu-id="7138f-156">**Limite de notificação diário**: o valor padrão é **Sem limite**, mas você pode selecionar um limite para o número máximo de notificações por dia.</span><span class="sxs-lookup"><span data-stu-id="7138f-156">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="7138f-157">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7138f-157">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="7138f-158">Volte ao submenu **Usuário impedido de enviar e-mail**, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="7138f-158">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="7138f-159">Use o Exchange Online PowerShell para exibir e remover usuários da lista Usuários restritos</span><span class="sxs-lookup"><span data-stu-id="7138f-159">Use Exchange Online PowerShell to view and remove users from the Restricted Users list</span></span>

<span data-ttu-id="7138f-160">Para visualizar esta lista de usuários que estão impedidos de enviar e-mails, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7138f-160">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="7138f-161">Para exibir detalhes de um usuário específico, substitua o \<emailaddress\> pelo seu endereço de email e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7138f-161">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="7138f-162">Para obter mais informações detalhadas de sintaxe e parâmetro, consulte [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="7138f-162">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="7138f-163">Para remover um usuário da lista de Usuários Restritos, substitua o \<emailaddress\>pelo seu endereço de email e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7138f-163">To remove a user from the Restricted Users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="7138f-164">Para obter mais informações detalhadas de sintaxe e parâmetro, consulte [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="7138f-164">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](https://docs.microsoft.com/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
