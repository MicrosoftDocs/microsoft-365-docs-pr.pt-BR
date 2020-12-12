---
title: Gerenciar arquivos e mensagens em quarentena como administrador
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a exibir e gerenciar mensagens em quarentena para todos os usuários na proteção do Exchange Online (EOP). Os administradores nas organizações com o Microsoft defender para Office 365 também podem gerenciar arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.
ms.openlocfilehash: 5f4d63576e57ac50abe1ec1eb378221c4d457280
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659981"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="c8145-104">Gerenciar arquivos e mensagens em quarentena como administrador no EOP</span><span class="sxs-lookup"><span data-stu-id="c8145-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="c8145-105">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena retém mensagens potencialmente perigosas ou indesejadas.</span><span class="sxs-lookup"><span data-stu-id="c8145-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="c8145-106">Para obter mais informações, consulte [mensagens de email em quarentena no EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="c8145-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="c8145-107">Os administradores podem exibir, liberar e excluir todos os tipos de mensagens em quarentena para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="c8145-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="c8145-108">Somente os administradores podem gerenciar mensagens que foram colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="c8145-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="c8145-109">Os administradores também podem relatar falsos positivos para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c8145-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="c8145-110">Os administradores nas organizações com o Microsoft defender para Office 365 também podem exibir, baixar e excluir arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c8145-110">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="c8145-111">Você exibir e gerenciar mensagens em quarentena no centro de conformidade e segurança & ou no PowerShell (PowerShell do Exchange Online para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="c8145-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c8145-112">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="c8145-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c8145-113">Para abrir o Centro de Conformidade e Segurança, acesse <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="c8145-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="c8145-114">Para abrir a página Quarentena imediatamente, vá para <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="c8145-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="c8145-115">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c8145-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c8145-116">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="c8145-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c8145-117">Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos deste artigo:</span><span class="sxs-lookup"><span data-stu-id="c8145-117">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="c8145-118">Para executar a ação em mensagens em quarentena para todos os usuários, você precisa ser membro dos grupos de função de **Gerenciamento da organização**, **administrador de segurança** ou **administrador de quarentena** <sup>\*</sup> .</span><span class="sxs-lookup"><span data-stu-id="c8145-118">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="c8145-119">Para acesso somente leitura a mensagens em quarentena para todos os usuários, você precisa ser membro dos grupos de função **leitor global** ou **leitor de segurança** .</span><span class="sxs-lookup"><span data-stu-id="c8145-119">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="c8145-120">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c8145-120">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="c8145-121">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="c8145-121">**Notes**:</span></span>

  - <span data-ttu-id="c8145-122">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c8145-122">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="c8145-123">Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="c8145-123">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="c8145-124">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="c8145-124">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="c8145-125"><sup>\*</sup> Os membros do grupo de função **administrador de quarentena** também precisam ser membros do grupo de função **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) para fazer procedimentos de quarentena no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c8145-125"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="c8145-126">As mensagens em quarentena são mantidas por um período de tempo padrão antes de serem excluídas automaticamente:</span><span class="sxs-lookup"><span data-stu-id="c8145-126">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="c8145-127">30 dias para mensagens em quarentena por políticas antispam (spam, phishing e email em massa).</span><span class="sxs-lookup"><span data-stu-id="c8145-127">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="c8145-128">Este é o valor padrão e máximo.</span><span class="sxs-lookup"><span data-stu-id="c8145-128">This is the default and maximum value.</span></span> <span data-ttu-id="c8145-129">Para configurar (reduzir) esse valor, consulte [Configure anti-spam Policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c8145-129">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="c8145-130">15 dias para mensagens que contenham malware.</span><span class="sxs-lookup"><span data-stu-id="c8145-130">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="c8145-131">15 dias para arquivos colocados em quarentena pela ATP para SharePoint, OneDrive e Microsoft Teams no defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="c8145-131">15 days for files quarantined by ATP for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="c8145-132">Quando uma mensagem expira da quarentena, não é possível recuperá-la.</span><span class="sxs-lookup"><span data-stu-id="c8145-132">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="c8145-133">Usar o centro de conformidade de & de segurança para gerenciar mensagens de email em quarentena</span><span class="sxs-lookup"><span data-stu-id="c8145-133">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="c8145-134">Exibir email em quarentena</span><span class="sxs-lookup"><span data-stu-id="c8145-134">View quarantined email</span></span>

1. <span data-ttu-id="c8145-135">No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.</span><span class="sxs-lookup"><span data-stu-id="c8145-135">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="c8145-136">Verifique se a **exibição em quarentena** está definida com o valor padrão **email**.</span><span class="sxs-lookup"><span data-stu-id="c8145-136">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="c8145-137">Você pode classificar os resultados clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="c8145-137">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="c8145-138">Clique em **Modificar colunas** para exibir um máximo de sete colunas.</span><span class="sxs-lookup"><span data-stu-id="c8145-138">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="c8145-139">Os valores padrão são marcados com um asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="c8145-139">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="c8145-140">**Recebido**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c8145-140">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="c8145-141">**Remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c8145-141">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="c8145-142">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c8145-142">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="c8145-143">**Motivo da quarentena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c8145-143">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="c8145-144">**Lançado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c8145-144">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="c8145-145">**Tipo de política**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c8145-145">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="c8145-146">**Expires**</span><span class="sxs-lookup"><span data-stu-id="c8145-146">**Expires**</span></span>
   - <span data-ttu-id="c8145-147">**Recipiente**</span><span class="sxs-lookup"><span data-stu-id="c8145-147">**Recipient**</span></span>
   - <span data-ttu-id="c8145-148">**ID da mensagem**</span><span class="sxs-lookup"><span data-stu-id="c8145-148">**Message ID**</span></span>
   - <span data-ttu-id="c8145-149">**Nome da política**</span><span class="sxs-lookup"><span data-stu-id="c8145-149">**Policy name**</span></span>
   - <span data-ttu-id="c8145-150">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="c8145-150">**Size**</span></span>
   - <span data-ttu-id="c8145-151">**Direção**</span><span class="sxs-lookup"><span data-stu-id="c8145-151">**Direction**</span></span>

   <span data-ttu-id="c8145-152">Quando você terminar, clique em **Salvar**, ou clique em **Definido como padrão**.</span><span class="sxs-lookup"><span data-stu-id="c8145-152">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="c8145-153">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="c8145-153">To filter the results, click **Filter**.</span></span> <span data-ttu-id="c8145-154">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="c8145-154">The available filters are:</span></span>

   - <span data-ttu-id="c8145-155">**Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:</span><span class="sxs-lookup"><span data-stu-id="c8145-155">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="c8145-156">**Hoje**</span><span class="sxs-lookup"><span data-stu-id="c8145-156">**Today**</span></span>
     - <span data-ttu-id="c8145-157">**Próximos 2 dias**</span><span class="sxs-lookup"><span data-stu-id="c8145-157">**Next 2 days**</span></span>
     - <span data-ttu-id="c8145-158">**Próximas 7 semanas**</span><span class="sxs-lookup"><span data-stu-id="c8145-158">**Next 7 days**</span></span>
     - <span data-ttu-id="c8145-159">**Personalizado**: Insira uma **Data de início** e uma **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="c8145-159">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="c8145-160">**Hora recebida**: Insira uma **Data de início** e uma **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="c8145-160">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="c8145-161">**Motivo da quarentena**:</span><span class="sxs-lookup"><span data-stu-id="c8145-161">**Quarantine reason**:</span></span>
     - <span data-ttu-id="c8145-162">**Política**: a mensagem correspondeu às condições de uma regra de fluxo de emails (também conhecida como regra de transporte).</span><span class="sxs-lookup"><span data-stu-id="c8145-162">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="c8145-163">**Em massa**</span><span class="sxs-lookup"><span data-stu-id="c8145-163">**Bulk**</span></span>
     - <span data-ttu-id="c8145-164">**Phish**: o filtro de spam veredicto foi um **email de phishing** ou proteção contra phishing colocou em quarentena a mensagem ([configurações de spoof](set-up-anti-phishing-policies.md#spoof-settings) ou [proteção de personificação](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span><span class="sxs-lookup"><span data-stu-id="c8145-164">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="c8145-165">**Malware**</span><span class="sxs-lookup"><span data-stu-id="c8145-165">**Malware**</span></span>
     - <span data-ttu-id="c8145-166">**Spam**</span><span class="sxs-lookup"><span data-stu-id="c8145-166">**Spam**</span></span>
     - <span data-ttu-id="c8145-167">**Phishing de alta confiança**</span><span class="sxs-lookup"><span data-stu-id="c8145-167">**High Confidence Phish**</span></span>

   - <span data-ttu-id="c8145-168">**Tipo de Política**: Filtre mensagens por tipo de política:</span><span class="sxs-lookup"><span data-stu-id="c8145-168">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="c8145-169">**Política Antimalware**</span><span class="sxs-lookup"><span data-stu-id="c8145-169">**Anti-malware policy**</span></span>
     - <span data-ttu-id="c8145-170">**Política de anexos seguros**</span><span class="sxs-lookup"><span data-stu-id="c8145-170">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="c8145-171">**Política Anti-phish**:</span><span class="sxs-lookup"><span data-stu-id="c8145-171">**Anti-phish policy**</span></span>
     - <span data-ttu-id="c8145-172">**Política de filtro de conteúdo hospedado** (política antispam)</span><span class="sxs-lookup"><span data-stu-id="c8145-172">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="c8145-173">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="c8145-173">**Transport rule**</span></span>

   - <span data-ttu-id="c8145-174">**Destinatário do email**: todos os usuários ou apenas as mensagens enviadas a você.</span><span class="sxs-lookup"><span data-stu-id="c8145-174">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="c8145-175">Os usuários finais só podem gerenciar mensagens em quarentena enviadas para eles.</span><span class="sxs-lookup"><span data-stu-id="c8145-175">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="c8145-176">Para limpar o filtro, clique em **Limpar**.</span><span class="sxs-lookup"><span data-stu-id="c8145-176">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="c8145-177">Para ocultar o submenu do filtro, clique novamente em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="c8145-177">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="c8145-178">Use **Classificar resultados por** (o botão **ID da mensagem** por padrão) e um valor correspondente para localizar mensagens específicas.</span><span class="sxs-lookup"><span data-stu-id="c8145-178">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="c8145-179">Os curingas não possuem suporte.</span><span class="sxs-lookup"><span data-stu-id="c8145-179">Wildcards aren't supported.</span></span> <span data-ttu-id="c8145-180">Você pode pesquisar pelos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c8145-180">You can search by the following values:</span></span>

   - <span data-ttu-id="c8145-181">**ID da mensagem**: o identificador globalmente exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c8145-181">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="c8145-182">Por exemplo, você usou o [rastreamento de mensagens](message-trace-scc.md) para procurar uma mensagem que foi enviada a um usuário na sua organização, e você determina que a mensagem foi colocada em quarentena em vez de distribuída.</span><span class="sxs-lookup"><span data-stu-id="c8145-182">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="c8145-183">Certifique-se de incluir o valor completo da ID da mensagem, que pode incluir colchetes angulares ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="c8145-183">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="c8145-184">Por exemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="c8145-184">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="c8145-185">**Endereço de e-mail do remetente**: o endereço de e-mail de um único remetente.</span><span class="sxs-lookup"><span data-stu-id="c8145-185">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="c8145-186">**Nome da política**: Use o nome completo da política da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c8145-186">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="c8145-187">A pesquisa não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c8145-187">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="c8145-188">**Endereço de e-mail do destinatário**: o endereço de e-mail de um único destinatário.</span><span class="sxs-lookup"><span data-stu-id="c8145-188">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="c8145-189">**Assunto**: use todo o assunto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c8145-189">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="c8145-190">A pesquisa não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c8145-190">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="c8145-191">**Nome da política**: o nome da política responsável por colocar a mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="c8145-191">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="c8145-192">Depois de ter inserido os critérios da pesquisa, clique em ![Atualizar botão](../../media/scc-quarantine-refresh.png) **Atualizar** para filtrar os resultados.</span><span class="sxs-lookup"><span data-stu-id="c8145-192">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="c8145-193">Depois de encontrar uma mensagem específica em quarentena, selecione a mensagem para exibir detalhes sobre ela e execute uma ação (por exemplo: exibir, liberar, fazer download ou excluir a mensagem).</span><span class="sxs-lookup"><span data-stu-id="c8145-193">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="c8145-194">Exiba detalhes da mensagem em quarentena</span><span class="sxs-lookup"><span data-stu-id="c8145-194">View quarantined message details</span></span>

<span data-ttu-id="c8145-195">Quando você clica em uma mensagem de e-mail na lista, os seguintes detalhes de mensagem são exibidos no painel de submenu **Detalhes**:</span><span class="sxs-lookup"><span data-stu-id="c8145-195">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="c8145-196">**ID da mensagem**: o identificador globalmente exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c8145-196">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="c8145-197">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="c8145-197">**Sender address**</span></span>

- <span data-ttu-id="c8145-198">**Recebido**: a data e a hora em que a mensagem foi recebida.</span><span class="sxs-lookup"><span data-stu-id="c8145-198">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="c8145-199">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="c8145-199">**Subject**</span></span>

- <span data-ttu-id="c8145-200">**Motivo da quarentena**: mostra se uma mensagem foi identificada como **spam**, **em massa**, **Phish**, corresponde a uma regra de fluxo de emails (**regra de transporte**) ou foi identificada como contendo **malware**.</span><span class="sxs-lookup"><span data-stu-id="c8145-200">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="c8145-201">**Contagem de destinatários**</span><span class="sxs-lookup"><span data-stu-id="c8145-201">**Recipient count**</span></span>

- <span data-ttu-id="c8145-202">**Destinatários**: se a mensagem contiver vários destinatários, você precisará clicar em **Visualizar mensagem** ou **Exibir o cabeçalho da mensagem** para visualizar a lista completa dos destinatários.</span><span class="sxs-lookup"><span data-stu-id="c8145-202">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="c8145-203">**Expira**: a data/hora em que a mensagem será excluída de forma automática e permanente da quarentena.</span><span class="sxs-lookup"><span data-stu-id="c8145-203">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="c8145-204">**Liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem foi liberada.</span><span class="sxs-lookup"><span data-stu-id="c8145-204">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="c8145-205">**Sem liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem não foi liberada.</span><span class="sxs-lookup"><span data-stu-id="c8145-205">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="c8145-206">Tomar medidas quanto aos e-mails em quarentena</span><span class="sxs-lookup"><span data-stu-id="c8145-206">Take action on quarantined email</span></span>

<span data-ttu-id="c8145-207">Após selecionar uma mensagem, você tem várias opções para o que fazer com as mensagens no painel de submenu **detalhes** :</span><span class="sxs-lookup"><span data-stu-id="c8145-207">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="c8145-208">**Mensagem de lançamento**: no painel de submenus exibido, escolha as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c8145-208">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="c8145-209">**Relatar mensagens à Microsoft para análise**: isso é selecionado por padrão e relata a mensagem em quarentena errada à Microsoft como um falso positivo.</span><span class="sxs-lookup"><span data-stu-id="c8145-209">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="c8145-210">Se a mensagem foi colocada em quarentena como spam, em massa, phishing ou com malware, a mensagem também é relatada para a equipe de análise de spam da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c8145-210">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="c8145-211">Dependendo da análise, as regras de filtro de spam de todo o serviço podem ser ajustadas para permitir a mensagem.</span><span class="sxs-lookup"><span data-stu-id="c8145-211">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="c8145-212">Escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c8145-212">Choose one of the following options:</span></span>
    - <span data-ttu-id="c8145-213">**Liberar mensagens para todos os destinatários**</span><span class="sxs-lookup"><span data-stu-id="c8145-213">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="c8145-214">**Liberar mensagens para destinatários específicos**</span><span class="sxs-lookup"><span data-stu-id="c8145-214">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="c8145-215">**Liberar mensagens para outras pessoas**: Observe que não há suporte para a liberação de mensagens de malware para pessoas que não sejam destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="c8145-215">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="c8145-216">Quando terminar, clique em **Liberar mensagens**.</span><span class="sxs-lookup"><span data-stu-id="c8145-216">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="c8145-217">Observações sobre o lançamento de mensagens:</span><span class="sxs-lookup"><span data-stu-id="c8145-217">Notes about releasing messages:</span></span>

  - <span data-ttu-id="c8145-218">Você não pode liberar uma mensagem para o mesmo destinatário mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="c8145-218">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="c8145-219">Somente os destinatários que não receberam a mensagem aparecerão na lista de possíveis destinatários.</span><span class="sxs-lookup"><span data-stu-id="c8145-219">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="c8145-220">**Exibir cabeçalho da mensagem**: escolha este link para visualizar o texto do cabeçalho da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c8145-220">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="c8145-221">Para analisar os valores e campos de cabeçalho em detalhes, copie o texto do cabeçalho da mensagem para a área de transferência e, em seguida, escolha **Analisador de Cabeçalhos de Mensagens da Microsoft** para acessar o Analisar de Conectividade Remota (clique com o botão direito e escolha **Abrir em uma nova guia** se não quiser deixar o Microsoft 365 para concluir essa tarefa).</span><span class="sxs-lookup"><span data-stu-id="c8145-221">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="c8145-222">Cole o cabeçalho da mensagem na página na seção Analisador do cabeçalho da mensagem e escolha **Analisar cabeçalhos**:</span><span class="sxs-lookup"><span data-stu-id="c8145-222">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="c8145-223">**Visualizar mensagem**: no painel de submenu que é exibido, escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c8145-223">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="c8145-224">**Visualização da fonte**: mostra a versão HTML do corpo da mensagem com todos os links desabilitados.</span><span class="sxs-lookup"><span data-stu-id="c8145-224">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="c8145-225">**Visualização do texto**: mostra o corpo da mensagem em texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="c8145-225">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="c8145-226">**Remover da quarentena**: depois de clicar em **Sim** no aviso exibido, a mensagem será excluída imediatamente sem ser enviada aos destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="c8145-226">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="c8145-227">**Mensagem de download**: no painel de submenu que é exibido, clique em **Compreendo os riscos de baixar esta mensagem** para salvar uma cópia local da mensagem no formato .eml.</span><span class="sxs-lookup"><span data-stu-id="c8145-227">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="c8145-228">**Enviar mensagem**: no painel de submenu que aparece, escolha as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c8145-228">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="c8145-229">**Tipo de objeto**: **email** (padrão), **URL** ou **anexo**.</span><span class="sxs-lookup"><span data-stu-id="c8145-229">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="c8145-230">**Formato de envio**: **ID de mensagem de rede** (padrão, com o valor correspondente na caixa ID de mensagem de **rede** ) ou **arquivo** (navegue até um arquivo. eml ou. msg local).</span><span class="sxs-lookup"><span data-stu-id="c8145-230">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="c8145-231">Observe que, se você selecionar **arquivo** e selecionar **ID de mensagem de rede**, o valor inicial será desperdido.</span><span class="sxs-lookup"><span data-stu-id="c8145-231">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="c8145-232">**Destinatários**: digite no leasing um destinatário original da mensagem ou clique em **selecionar tudo** para identificar todos os destinatários.</span><span class="sxs-lookup"><span data-stu-id="c8145-232">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="c8145-233">Você também pode clicar em **selecionar todos** e, em seguida, remover seletivamente destinatários individuais.</span><span class="sxs-lookup"><span data-stu-id="c8145-233">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="c8145-234">**Motivo do envio**: **não deve ter sido bloqueado** (padrão) ou **deve ter sido bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="c8145-234">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="c8145-235">Quando tiver concluído, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="c8145-235">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="c8145-236">Se você não liberar ou remover a mensagem, ela será excluída após o término do período de retenção da quarentena padrão.</span><span class="sxs-lookup"><span data-stu-id="c8145-236">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="c8145-237">Tome medidas em várias mensagens quanto aos e-mails em quarentena</span><span class="sxs-lookup"><span data-stu-id="c8145-237">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="c8145-238">Quando você seleciona várias mensagens que estão em quarentena na lista (até 100), o painel de submenu **Ações em massa** é exibido em que você pode realizar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="c8145-238">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="c8145-239">**Mensagens de lançamento**: as opções são as mesmas de quando você libera uma única mensagem, mas não é possível clicar em **Liberar mensagens para destinatários específicos**; você só pode clicar em **Mensagem de lançamento a todos os destinatários** ou **Liberar mensagens para outras pessoas**.</span><span class="sxs-lookup"><span data-stu-id="c8145-239">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c8145-240">Considere o seguinte cenário: john@gmail.com envia uma mensagem para faith@contoso.com e john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c8145-240">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="c8145-241">O Gmail bifurcates esta mensagem em duas cópias que são direcionadas para quarentena como phishing no Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c8145-241">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="c8145-242">Um administrador libera essas duas mensagens para o admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c8145-242">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="c8145-243">A primeira mensagem liberada que alcança a caixa de correio de administrador é entregue.</span><span class="sxs-lookup"><span data-stu-id="c8145-243">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="c8145-244">A segunda mensagem liberada é identificada como entrega duplicada e é ignorada.</span><span class="sxs-lookup"><span data-stu-id="c8145-244">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="c8145-245">A mensagem será identificada como duplicatas se elas tiverem a mesma ID de mensagem e o tempo de recebimento.</span><span class="sxs-lookup"><span data-stu-id="c8145-245">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="c8145-246">**Excluir mensagens**: depois de clicar em **Sim** no aviso que aparece, as mensagens são excluídas imediatamente sem serem enviadas aos destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="c8145-246">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="c8145-247">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="c8145-247">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="c8145-248">Somente Microsoft defender para Office 365: usar o centro de conformidade de & de segurança para gerenciar arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="c8145-248">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="c8145-249">Os procedimentos para arquivos em quarentena nesta seção estão disponíveis somente para assinantes do Microsoft defender for Office 365 plano 1 e do plano 2.</span><span class="sxs-lookup"><span data-stu-id="c8145-249">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="c8145-250">Em organizações com o defender para Office 365, os administradores podem gerenciar arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c8145-250">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="c8145-251">Para habilitar a proteção desses arquivos, confira [Ativar ATP para SharePoint, onedrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="c8145-251">To enable protection for these files, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="c8145-252">Exibir arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="c8145-252">View quarantined files</span></span>

1. <span data-ttu-id="c8145-253">No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.</span><span class="sxs-lookup"><span data-stu-id="c8145-253">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="c8145-254">Altere o **modo de exibição colocado em quarentena** para os **arquivos** de valor.</span><span class="sxs-lookup"><span data-stu-id="c8145-254">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="c8145-255">Você pode classificar em um campo clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="c8145-255">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="c8145-256">Você pode classificar os resultados clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="c8145-256">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="c8145-257">Clique em **Modificar colunas** para exibir um máximo de sete colunas.</span><span class="sxs-lookup"><span data-stu-id="c8145-257">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="c8145-258">As colunas padrão são marcadas com um asterisco ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="c8145-258">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="c8145-259">**Usuário**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c8145-259">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="c8145-260">**Alocações**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c8145-260">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="c8145-261">**Nome do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c8145-261">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="c8145-262">**URL do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c8145-262">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="c8145-263">**Tamanho do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c8145-263">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="c8145-264">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c8145-264">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="c8145-265">**Lançado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="c8145-265">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="c8145-266">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="c8145-266">**Detected by**</span></span>
   - <span data-ttu-id="c8145-267">**Modificado por hora**</span><span class="sxs-lookup"><span data-stu-id="c8145-267">**Modified by time**</span></span>

4. <span data-ttu-id="c8145-268">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="c8145-268">To filter the results, click **Filter**.</span></span> <span data-ttu-id="c8145-269">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="c8145-269">The available filters are:</span></span>

   - <span data-ttu-id="c8145-270">**Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:</span><span class="sxs-lookup"><span data-stu-id="c8145-270">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="c8145-271">**Hoje**</span><span class="sxs-lookup"><span data-stu-id="c8145-271">**Today**</span></span>
     - <span data-ttu-id="c8145-272">**Próximos 2 dias**</span><span class="sxs-lookup"><span data-stu-id="c8145-272">**Next 2 days**</span></span>
     - <span data-ttu-id="c8145-273">**Próximas 7 semanas**</span><span class="sxs-lookup"><span data-stu-id="c8145-273">**Next 7 days**</span></span>
     - <span data-ttu-id="c8145-274">Um intervalo personalizado de data/hora.</span><span class="sxs-lookup"><span data-stu-id="c8145-274">A custom date/time range.</span></span>
   - <span data-ttu-id="c8145-275">**Hora de recebimento**</span><span class="sxs-lookup"><span data-stu-id="c8145-275">**Received time**</span></span>
   - <span data-ttu-id="c8145-276">**Motivo da quarentena**: o único valor disponível é **malware**.</span><span class="sxs-lookup"><span data-stu-id="c8145-276">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="c8145-277">**Tipo de política**</span><span class="sxs-lookup"><span data-stu-id="c8145-277">**Policy type**</span></span>

<span data-ttu-id="c8145-278">Depois de encontrar um arquivo em quarentena específico, selecione o arquivo para exibir os detalhes sobre ele e execute a ação nele (por exemplo, exibir, liberar, baixar ou excluir a mensagem).</span><span class="sxs-lookup"><span data-stu-id="c8145-278">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="c8145-279">Exibir detalhes de arquivo em quarentena</span><span class="sxs-lookup"><span data-stu-id="c8145-279">View quarantined file details</span></span>

<span data-ttu-id="c8145-280">Quando você seleciona um arquivo na lista, os seguintes detalhes de arquivo são exibidos no painel de submenu **detalhes** :</span><span class="sxs-lookup"><span data-stu-id="c8145-280">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="c8145-281">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="c8145-281">**File Name**</span></span>
- <span data-ttu-id="c8145-282">**URL do arquivo**: URL que define o local do arquivo (por exemplo, no SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="c8145-282">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="c8145-283">**Conteúdo mal-intencionado detectado em** A data/hora em que o arquivo foi colocado em quarentena.</span><span class="sxs-lookup"><span data-stu-id="c8145-283">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="c8145-284">**Expira**: a data em que o arquivo será excluído da quarentena.</span><span class="sxs-lookup"><span data-stu-id="c8145-284">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="c8145-285">**Detectado por**: defender para Office 365 ou mecanismo antimalware da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c8145-285">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="c8145-286">**Lançado?**</span><span class="sxs-lookup"><span data-stu-id="c8145-286">**Released?**</span></span>
- <span data-ttu-id="c8145-287">**Nome do malware**</span><span class="sxs-lookup"><span data-stu-id="c8145-287">**Malware Name**</span></span>
- <span data-ttu-id="c8145-288">**ID do documento**: um identificador exclusivo para o documento.</span><span class="sxs-lookup"><span data-stu-id="c8145-288">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="c8145-289">**Tamanho do arquivo**: em kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="c8145-289">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="c8145-290">**Organização** A ID exclusiva da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c8145-290">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="c8145-291">**Última modificação**</span><span class="sxs-lookup"><span data-stu-id="c8145-291">**Last modified**</span></span>
- <span data-ttu-id="c8145-292">**Modificado por**: o usuário que modificou o arquivo pela última vez.</span><span class="sxs-lookup"><span data-stu-id="c8145-292">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="c8145-293">**Algoritmo de hash seguro 256 bits (SHA-256) valor**: você pode usar esse valor de hash para identificar o arquivo em outros repositórios de reputação ou em outros locais em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="c8145-293">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="c8145-294">Executar ação em arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="c8145-294">Take action on quarantined files</span></span>

<span data-ttu-id="c8145-295">Ao selecionar um arquivo na lista, você pode executar as seguintes ações no arquivo no painel de submenu **detalhes** :</span><span class="sxs-lookup"><span data-stu-id="c8145-295">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="c8145-296">**Arquivos de lançamento**: selecione (padrão) ou desmarque **arquivos de relatório para a Microsoft para análise** e clique em **liberar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="c8145-296">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="c8145-297">**Baixar o arquivo**</span><span class="sxs-lookup"><span data-stu-id="c8145-297">**Download file**</span></span>
- <span data-ttu-id="c8145-298">**Remover arquivo da quarentena**</span><span class="sxs-lookup"><span data-stu-id="c8145-298">**Remove file from quarantine**</span></span>

<span data-ttu-id="c8145-299">Se você não liberar ou remover os arquivos, eles serão excluídos depois que o período de retenção de quarentena padrão expirar.</span><span class="sxs-lookup"><span data-stu-id="c8145-299">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="c8145-300">Ações em vários arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="c8145-300">Actions on multiple quarantined files</span></span>

<span data-ttu-id="c8145-301">Quando você seleciona vários arquivos em quarentena na lista (até 100), o painel de submenu **ações em massa** aparece onde você pode executar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="c8145-301">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="c8145-302">**Arquivos de versão**</span><span class="sxs-lookup"><span data-stu-id="c8145-302">**Release files**</span></span>
- <span data-ttu-id="c8145-303">**Excluir arquivos**: depois de clicar em **Sim** no aviso exibido, os arquivos serão excluídos imediatamente.</span><span class="sxs-lookup"><span data-stu-id="c8145-303">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="c8145-304">Usar o PowerShell do Exchange Online ou do EOP PowerShell para exibir e gerenciar mensagens em quarentena e arquivos</span><span class="sxs-lookup"><span data-stu-id="c8145-304">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="c8145-305">Os cmdlets que você usa para exibir e gerenciar mensagens e arquivos em quarentena são:</span><span class="sxs-lookup"><span data-stu-id="c8145-305">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="c8145-306">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="c8145-306">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="c8145-307">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="c8145-307">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="c8145-308">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="c8145-308">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="c8145-309">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Observe que este cmdlet é somente para mensagens, e não para arquivos de malware de ATP para SharePoint Online, onedrive for Business ou Teams.</span><span class="sxs-lookup"><span data-stu-id="c8145-309">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="c8145-310">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="c8145-310">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
