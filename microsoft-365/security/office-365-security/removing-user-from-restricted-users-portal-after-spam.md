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
# <a name="remove-blocked-users-from-the-restricted-users-portal-in-microsoft-365"></a><span data-ttu-id="a8fcc-104">Remover usuários bloqueados do portal Usuários restritos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a8fcc-104">Remove blocked users from the Restricted users portal in Microsoft 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a8fcc-105">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="a8fcc-105">**Applies to**</span></span>
- [<span data-ttu-id="a8fcc-106">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a8fcc-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="a8fcc-107">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="a8fcc-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="a8fcc-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a8fcc-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="a8fcc-109">Se um usuário exceder um dos limites de envio de saída, conforme especificado nos [limites de serviço](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) ou nas [políticas de spam de saída](configure-the-outbound-spam-policy.md), o usuário será impedido de enviar e-mails, mas ainda poderá receber e-mails.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-109">If a user exceeds one of the outbound sending limits as specified in [the service limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options) or in [outbound spam policies](configure-the-outbound-spam-policy.md), the user is restricted from sending email, but they can still receive email.</span></span>

<span data-ttu-id="a8fcc-110">O usuário é adicionado à página **Usuários restritos** no portal do Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-110">The user is added to the **Restricted users** page in the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="a8fcc-111">Ao tentarem enviar e-mails, a mensagem é retornada em um relatório de falha na entrega (também conhecido como NDR ou mensagens de devolução) com o código de erro [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) e o seguinte texto:</span><span class="sxs-lookup"><span data-stu-id="a8fcc-111">When they try to send email, the message is returned in a non-delivery report (also known as an NDR or bounce messages) with the error code [5.1.8](/Exchange/mail-flow-best-practices/non-delivery-reports-in-exchange-online/fix-error-code-5-1-8-in-exchange-online) and the following text:</span></span>

> <span data-ttu-id="a8fcc-112">"A mensagem não pôde ser entregue porque você não foi reconhecido como um remetente válido.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-112">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="a8fcc-113">O motivo mais comum para isso é que seu endereço de email é suspeito de enviar spam e não tem mais permissão para enviar emails.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-113">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="a8fcc-114">Fale com o administrador para obter assistência.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-114">Contact  your email admin for assistance.</span></span> <span data-ttu-id="a8fcc-115">O servidor remoto retornou ' 550 5.1.8 acesso negado, remetente de saída incorreto ".</span><span class="sxs-lookup"><span data-stu-id="a8fcc-115">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

<span data-ttu-id="a8fcc-116">Os administradores podem aprender a remover usuários do portal Usuários restritos no portal do Microsoft 365 Defender ou no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-116">Admins can remove users from the Restricted users page in the Microsoft 365 Defender or in Exchange Online PowerShell.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a8fcc-117">Do que você precisa saber para começar?</span><span class="sxs-lookup"><span data-stu-id="a8fcc-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a8fcc-118">Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-118">You open the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="a8fcc-119">Para ir diretamente para a página **Usuários restritos**, use <https://security.microsoft.com/restrictedusers>.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-119">Too go directly to the **Restricted users** page, use <https://security.microsoft.com/restrictedusers>.</span></span>

- <span data-ttu-id="a8fcc-120">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a8fcc-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="a8fcc-121">Você precisa ter permissões em **Exchange Online** antes de fazer os procedimentos deste artigo:</span><span class="sxs-lookup"><span data-stu-id="a8fcc-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="a8fcc-122">Para remover usuários do portal do Usuários restritos, você precisa ser membro dos grupos de funções **Gerenciamento da Organização** ou **Administrador de Segurança**.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-122">To remove users from the Restricted users portal, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="a8fcc-123">Para acesso somente para leitura do portal de Usuários restritos, você precisa ser membro dos grupos de função **Leitor Global** ou **Leitor de Segurança**.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-123">For read-only access to the Restricted users portal, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="a8fcc-124">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="a8fcc-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  > [!NOTE]
  >
  > - <span data-ttu-id="a8fcc-125">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-125">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="a8fcc-126">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a8fcc-126">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="a8fcc-127">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-127">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="a8fcc-128">Um remetente que exceder os limites de email de saída é um indicador de uma conta comprometida.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-128">A sender exceeding the outbound email limits is an indicator of a compromised account.</span></span> <span data-ttu-id="a8fcc-129">Antes de remover o usuário do portal Usuários restritos, siga as etapas necessárias para recuperar o controle da sua conta.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-129">Before you remove the user from the Restricted users portal, be sure to follow the required steps to regain control of their account.</span></span> <span data-ttu-id="a8fcc-130">Para obter mais informações, consulte [Responder a uma conta de e-mail comprometida no Office 365.](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="a8fcc-130">For more information, see [Responding to a compromised email account in Office 365](responding-to-a-compromised-email-account.md).</span></span>

## <a name="use-the-microsoft-365-defender-portal-to-remove-a-user-from-the-restricted-users-list"></a><span data-ttu-id="a8fcc-131">Use o portal do Microsoft 365 Defender para remover um usuário da lista de Usuários restritos</span><span class="sxs-lookup"><span data-stu-id="a8fcc-131">Use the Microsoft 365 Defender portal to remove a user from the Restricted users list</span></span>

1. <span data-ttu-id="a8fcc-132">No portal do Microsoft 365 Defender, acesse **Email e colaboração**  > **Analisar** > **Usuários restritos**.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-132">In the Microsoft 365 Defender portal, go to **Email & collaboration** > **Review** > **Restricted users**.</span></span>

2. <span data-ttu-id="a8fcc-133">Na página **Usuários restritos**, localize e selecione o usuário que você deseja desbloquear clicando no usuário.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-133">On the **Restricted users** page, find and select the user that you want to unblock by clicking on the user.</span></span>

3. <span data-ttu-id="a8fcc-134">Clique na ação **Desbloqueio** que aparece.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-134">Click the **Unblock** action that appears.</span></span>

4. <span data-ttu-id="a8fcc-135">No submenu **Desbloquear usuário** exibido, leia os detalhes sobre a conta restrita.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-135">In the **Unblock user** flyout that appears, read the details about the restricted account.</span></span> <span data-ttu-id="a8fcc-136">Você deve percorrer as recomendações para garantir que você esteja tomando as ações adequadas caso a conta seja realmente comprometida.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-136">You should go through the recommendations to ensure you're taking the proper actions in case the account is compromised.</span></span>

   <span data-ttu-id="a8fcc-137">Ao terminar, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-137">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="a8fcc-138">A tela seguinte tem recomendações para ajudar a evitar o futuro compromisso.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-138">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="a8fcc-139">A habilitação da autenticação multifator (MFA) e a alteração das senhas são uma boa defesa.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-139">Enabling multi-factor authentication (MFA) and resetting the password are a good defense.</span></span>

   <span data-ttu-id="a8fcc-140">Quando concluir, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-140">When you're finished, click **Submit**.</span></span>

6. <span data-ttu-id="a8fcc-141">Clique em **Sim** para confirmar a alteração.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-141">Click **Yes** to confirm the change.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a8fcc-142">Pode levar até 24 horas para que todas as restrições sejam removidas do usuário.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-142">It might take up to 24 hours for all restrictions to be removed from the user.</span></span>

## <a name="verify-the-alert-settings-for-restricted-users"></a><span data-ttu-id="a8fcc-143">Verifique as configurações de alertados usuários restritos</span><span class="sxs-lookup"><span data-stu-id="a8fcc-143">Verify the alert settings for restricted users</span></span>

<span data-ttu-id="a8fcc-144">A política de alerta padrão denominada **Usuário impedido de enviar e-mails** notificará automaticamente os administradores quando os usuários forem impedidos de enviar e-mails de saída.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-144">The default alert policy named **User restricted from sending email** will automatically notify admins when users are blocked from sending outbound mail.</span></span> <span data-ttu-id="a8fcc-145">Você pode verificar essas configurações e adicionar usuários adicionais para notificar.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-145">You can verify these settings and add additional users to notify.</span></span> <span data-ttu-id="a8fcc-146">Para obter mais informações sobre políticas de alerta, confira [Políticas de alerta no Microsoft 365](../../compliance/alert-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a8fcc-146">For more information about alert policies, see [Alert policies in Microsoft 365](../../compliance/alert-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8fcc-147">Para que os alertas funcionem, a pesquisa de logs de auditoria deve ser ativada.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-147">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="a8fcc-148">Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="a8fcc-148">For more information, see [Turn the audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

1. <span data-ttu-id="a8fcc-149">No portal do Microsoft 365 Defender, acesse **Email e colaboração** \>**Políticas e regras** \> **Política de alerta**.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-149">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Alert policy**.</span></span>

2. <span data-ttu-id="a8fcc-150">Na página **Política de alerta**, localize e selecione o alerta chamado **Usuário impedido de enviar e-mails**.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-150">On the **Alert policy** page, find and select the alert named **User restricted from sending email**.</span></span> <span data-ttu-id="a8fcc-151">Você pode classificar as políticas por nome ou usar a **Caixa de pesquisa** para localizar a política.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-151">You can sort the policies by name, or use the **Search box** to find the policy.</span></span>

3. <span data-ttu-id="a8fcc-152">No submenu **Usuário restringido de enviar e-mail** exibido, verifique ou defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a8fcc-152">In the **User restricted from sending email** flyout that appears, verify or configure the following settings:</span></span>
   - <span data-ttu-id="a8fcc-153">**Status**: Verifique se o alerta está ativado como ![Alternância](../../media/scc-toggle-on.png).</span><span class="sxs-lookup"><span data-stu-id="a8fcc-153">**Status**: Verify the alert is turned on ![Toggle on](../../media/scc-toggle-on.png).</span></span>
   - <span data-ttu-id="a8fcc-154">**Destinatários de e-mails**: Clique em **Editar** e verifique ou defina as seguintes configurações no menu **Editar destinatários** que é exibido:</span><span class="sxs-lookup"><span data-stu-id="a8fcc-154">**Email recipients**: Click **Edit** and verify or configure the following settings in the **Edit recipients** flyout that appears:</span></span>
     - <span data-ttu-id="a8fcc-155">**Enviar notificações por e-mail**: verificar se a caixa de seleção está marcada como (**Ativada**).</span><span class="sxs-lookup"><span data-stu-id="a8fcc-155">**Send email notifications**: Verify this is selected (**On**).</span></span>
     - <span data-ttu-id="a8fcc-156">**Destinatários de e-mails**: o valor padrão é **TenantAdmins** (ou seja, membros de **Administração global**).</span><span class="sxs-lookup"><span data-stu-id="a8fcc-156">**Email recipients**: The default value is **TenantAdmins** (meaning, **Global admin** members).</span></span> <span data-ttu-id="a8fcc-157">Para adicionar mais destinatários, clique em uma área em branco da caixa.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-157">To add more recipients, click in a blank area of the box.</span></span> <span data-ttu-id="a8fcc-158">Uma lista de destinatários será exibida e você poderá começar a digitar um nome para filtrar e selecionar um destinatário.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-158">A list of recipients will appear, and you can start typing a name to filter and select a recipient.</span></span> <span data-ttu-id="a8fcc-159">Você pode remover um destinatário existente da caixa clicando no ![ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) ao lado do nome.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-159">You can remove an existing recipient from the box by clicking ![Remove icon](../../media/m365-cc-sc-remove-selection-icon.png) next to their name.</span></span>
     - <span data-ttu-id="a8fcc-160">**Limite de notificação diário**: o valor padrão é **Sem limite**, mas você pode selecionar um limite para o número máximo de notificações por dia.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-160">**Daily notification limit**: The default value is **No limit** but you can select a limit for the maximum number of notifications per day.</span></span>

     <span data-ttu-id="a8fcc-161">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-161">When you're finished, click **Save**.</span></span>

4. <span data-ttu-id="a8fcc-162">Volte ao submenu **Usuário impedido de enviar e-mail**, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="a8fcc-162">Back on the **User restricted from sending email** flyout, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-to-view-and-remove-users-from-the-restricted-users-list"></a><span data-ttu-id="a8fcc-163">Use o Exchange Online PowerShell para exibir e remover usuários da lista Usuários restritos</span><span class="sxs-lookup"><span data-stu-id="a8fcc-163">Use Exchange Online PowerShell to view and remove users from the Restricted users list</span></span>

<span data-ttu-id="a8fcc-164">Para visualizar esta lista de usuários que estão impedidos de enviar e-mails, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a8fcc-164">To view this list of users that are restricted from sending email, run the following command:</span></span>

```powershell
Get-BlockedSenderAddress
```

<span data-ttu-id="a8fcc-165">Para exibir detalhes de um usuário específico, substitua o \<emailaddress\> pelo seu endereço de email e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a8fcc-165">To view details about a specific user, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Get-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="a8fcc-166">Para obter mais informações detalhadas de sintaxe e parâmetro, consulte [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="a8fcc-166">For detailed syntax and parameter information, see [Get-BlockedSenderAddress](/powershell/module/exchange/get-blockedsenderaddress).</span></span>

<span data-ttu-id="a8fcc-167">Para remover um usuário da lista de Usuários Restritos, substitua o \<emailaddress\> pelo seu endereço de e-mail e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a8fcc-167">To remove a user from the Restricted users list, replace \<emailaddress\> with their email address and run the following command:</span></span>

```powershell
Remove-BlockedSenderAddress -SenderAddress <emailaddress>
```

<span data-ttu-id="a8fcc-168">Para obter mais informações detalhadas de sintaxe e parâmetro, consulte [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress).</span><span class="sxs-lookup"><span data-stu-id="a8fcc-168">For detailed syntax and parameter information, see [Remove-BlockedSenderAddress](/powershell/module/exchange/remove-blockedsenderaddress).</span></span>
