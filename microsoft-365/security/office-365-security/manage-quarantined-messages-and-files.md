---
title: Gerenciar arquivos e mensagens em quarentena como administrador
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
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
description: Os administradores podem aprender a exibir e gerenciar mensagens em quarentena para todos os usuários no Exchange Online Protection (EOP). Os administradores em organizações com o Microsoft Defender para Office 365 também podem gerenciar arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c5e2d6a3729a24766652d4c7c0973c63b1dcb207
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272199"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="f4662-104">Gerenciar arquivos e mensagens em quarentena como administrador no EOP</span><span class="sxs-lookup"><span data-stu-id="f4662-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="f4662-105">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="f4662-105">**Applies to**</span></span>
- [<span data-ttu-id="f4662-106">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f4662-106">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="f4662-107">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="f4662-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f4662-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4662-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f4662-109">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena retém mensagens potencialmente perigosas ou indesejadas.</span><span class="sxs-lookup"><span data-stu-id="f4662-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="f4662-110">Para obter mais informações, consulte [Mensagens de email em quarentena no EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="f4662-110">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="f4662-111">Os administradores podem exibir, liberar e excluir todos os tipos de mensagens em quarentena para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="f4662-111">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="f4662-112">Somente os administradores podem gerenciar mensagens que foram colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="f4662-112">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="f4662-113">Os administradores também podem relatar falsos positivos à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f4662-113">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="f4662-114">Os administradores em organizações com o Microsoft Defender para Office 365 também podem exibir, baixar e excluir arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f4662-114">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="f4662-115">Você visualiza e gerencia mensagens em quarentena no Centro de Conformidade & Segurança ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; PowerShell autônomo do EOP para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="f4662-115">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f4662-116">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="f4662-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f4662-117">Para abrir o Centro de Conformidade e Segurança, acesse <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="f4662-117">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="f4662-118">Para abrir a página Quarentena imediatamente, vá para <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="f4662-118">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="f4662-119">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="f4662-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="f4662-120">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="f4662-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="f4662-121">Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:</span><span class="sxs-lookup"><span data-stu-id="f4662-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="f4662-122">Para tomar medidas em mensagens em quarentena para todos os usuários, você precisa ser membro dos grupos de função Gerenciamento da **Organização,** Administrador de Segurança **ou** Administrador **de** <sup>\*</sup> Quarentena.</span><span class="sxs-lookup"><span data-stu-id="f4662-122">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="f4662-123">Para acesso somente leitura a mensagens em quarentena para todos os usuários, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="f4662-123">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="f4662-124">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="f4662-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="f4662-125">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="f4662-125">**Notes**:</span></span>

  - <span data-ttu-id="f4662-126">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f4662-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="f4662-127">Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="f4662-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="f4662-128">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="f4662-128">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="f4662-129"><sup>\*</sup> Membros do grupo de função **Administrador** de Quarentena também precisam ser membros do grupo de função **Gerenciamento** de Higienização no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) para realizar procedimentos de quarentena no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="f4662-129"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="f4662-130">As mensagens em quarentena são mantidas por um período de tempo padrão antes que sejam excluídas automaticamente:</span><span class="sxs-lookup"><span data-stu-id="f4662-130">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="f4662-131">30 dias para mensagens em quarentena por políticas anti-spam (spam, phishing e email em massa).</span><span class="sxs-lookup"><span data-stu-id="f4662-131">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="f4662-132">Esse é o valor padrão e máximo.</span><span class="sxs-lookup"><span data-stu-id="f4662-132">This is the default and maximum value.</span></span> <span data-ttu-id="f4662-133">Para configurar (mais baixo) esse valor, consulte [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f4662-133">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="f4662-134">15 dias para mensagens que contêm malware.</span><span class="sxs-lookup"><span data-stu-id="f4662-134">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="f4662-135">15 dias para arquivos em quarentena por Anexos Seguros para SharePoint, OneDrive e Microsoft Teams no Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="f4662-135">15 days for files quarantined by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="f4662-136">Quando uma mensagem expira da quarentena, você não pode recuperá-la.</span><span class="sxs-lookup"><span data-stu-id="f4662-136">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="f4662-137">Usar o Centro de Conformidade & segurança para gerenciar mensagens de email em quarentena</span><span class="sxs-lookup"><span data-stu-id="f4662-137">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="f4662-138">Exibir email em quarentena</span><span class="sxs-lookup"><span data-stu-id="f4662-138">View quarantined email</span></span>

1. <span data-ttu-id="f4662-139">No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.</span><span class="sxs-lookup"><span data-stu-id="f4662-139">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="f4662-140">Verifique se a **Exibição em quarentena** está definida como o valor padrão **email**.</span><span class="sxs-lookup"><span data-stu-id="f4662-140">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="f4662-141">Você pode classificar os resultados clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="f4662-141">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="f4662-142">Clique em **Modificar colunas** para exibir um máximo de sete colunas.</span><span class="sxs-lookup"><span data-stu-id="f4662-142">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="f4662-143">Os valores padrão são marcados com um asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="f4662-143">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="f4662-144">**Recebido**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f4662-144">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="f4662-145">**Remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f4662-145">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="f4662-146">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f4662-146">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="f4662-147">**Motivo da quarentena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f4662-147">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="f4662-148">**Lançado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f4662-148">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="f4662-149">**Tipo de política**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f4662-149">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="f4662-150">**Expires**</span><span class="sxs-lookup"><span data-stu-id="f4662-150">**Expires**</span></span>
   - <span data-ttu-id="f4662-151">**Recipiente**</span><span class="sxs-lookup"><span data-stu-id="f4662-151">**Recipient**</span></span>
   - <span data-ttu-id="f4662-152">**ID da mensagem**</span><span class="sxs-lookup"><span data-stu-id="f4662-152">**Message ID**</span></span>
   - <span data-ttu-id="f4662-153">**Nome da política**</span><span class="sxs-lookup"><span data-stu-id="f4662-153">**Policy name**</span></span>
   - <span data-ttu-id="f4662-154">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="f4662-154">**Size**</span></span>
   - <span data-ttu-id="f4662-155">**Direção**</span><span class="sxs-lookup"><span data-stu-id="f4662-155">**Direction**</span></span>

   <span data-ttu-id="f4662-156">Quando você terminar, clique em **Salvar**, ou clique em **Definido como padrão**.</span><span class="sxs-lookup"><span data-stu-id="f4662-156">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="f4662-157">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="f4662-157">To filter the results, click **Filter**.</span></span> <span data-ttu-id="f4662-158">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="f4662-158">The available filters are:</span></span>

   - <span data-ttu-id="f4662-159">**Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:</span><span class="sxs-lookup"><span data-stu-id="f4662-159">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="f4662-160">**Hoje**</span><span class="sxs-lookup"><span data-stu-id="f4662-160">**Today**</span></span>
     - <span data-ttu-id="f4662-161">**Próximos 2 dias**</span><span class="sxs-lookup"><span data-stu-id="f4662-161">**Next 2 days**</span></span>
     - <span data-ttu-id="f4662-162">**Próximas 7 semanas**</span><span class="sxs-lookup"><span data-stu-id="f4662-162">**Next 7 days**</span></span>
     - <span data-ttu-id="f4662-163">**Personalizado**: Insira uma **Data de início** e uma **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="f4662-163">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="f4662-164">**Hora recebida**: Insira uma **Data de início** e uma **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="f4662-164">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="f4662-165">**Motivo da quarentena**:</span><span class="sxs-lookup"><span data-stu-id="f4662-165">**Quarantine reason**:</span></span>
     - <span data-ttu-id="f4662-166">**Política**: A mensagem corresponderia às condições de uma regra de fluxo de emails (também conhecida como regra de transporte).</span><span class="sxs-lookup"><span data-stu-id="f4662-166">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="f4662-167">**Em massa**</span><span class="sxs-lookup"><span data-stu-id="f4662-167">**Bulk**</span></span>
     - <span data-ttu-id="f4662-168">**Phish**: O veredito do filtro de spam foi **phishing email** ou proteção anti-phishing em quarentena a mensagem ( configurações de [spoof](set-up-anti-phishing-policies.md#spoof-settings) ou proteção [de representação](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span><span class="sxs-lookup"><span data-stu-id="f4662-168">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="f4662-169">**Malware**</span><span class="sxs-lookup"><span data-stu-id="f4662-169">**Malware**</span></span>
     - <span data-ttu-id="f4662-170">**Spam**</span><span class="sxs-lookup"><span data-stu-id="f4662-170">**Spam**</span></span>
     - <span data-ttu-id="f4662-171">**Phishing de alta confiança**</span><span class="sxs-lookup"><span data-stu-id="f4662-171">**High Confidence Phish**</span></span>

   - <span data-ttu-id="f4662-172">**Tipo de Política**: Filtre mensagens por tipo de política:</span><span class="sxs-lookup"><span data-stu-id="f4662-172">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="f4662-173">**Política anti-malware**</span><span class="sxs-lookup"><span data-stu-id="f4662-173">**Anti-malware policy**</span></span>
     - <span data-ttu-id="f4662-174">**Política de Anexos Seguros**</span><span class="sxs-lookup"><span data-stu-id="f4662-174">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="f4662-175">**Política Anti-phish**:</span><span class="sxs-lookup"><span data-stu-id="f4662-175">**Anti-phish policy**</span></span>
     - <span data-ttu-id="f4662-176">**Política de filtro de conteúdo hospedado** (política antispam)</span><span class="sxs-lookup"><span data-stu-id="f4662-176">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="f4662-177">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="f4662-177">**Transport rule**</span></span>

   - <span data-ttu-id="f4662-178">**Destinatário de** email : Todos os usuários ou somente mensagens enviadas a você.</span><span class="sxs-lookup"><span data-stu-id="f4662-178">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="f4662-179">Os usuários finais só podem gerenciar mensagens em quarentena enviadas a eles.</span><span class="sxs-lookup"><span data-stu-id="f4662-179">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="f4662-180">Para limpar o filtro, clique em **Limpar**.</span><span class="sxs-lookup"><span data-stu-id="f4662-180">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="f4662-181">Para ocultar o submenu do filtro, clique novamente em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="f4662-181">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="f4662-182">Use **Classificar resultados por** (o botão **ID da mensagem** por padrão) e um valor correspondente para localizar mensagens específicas.</span><span class="sxs-lookup"><span data-stu-id="f4662-182">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="f4662-183">Os curingas não possuem suporte.</span><span class="sxs-lookup"><span data-stu-id="f4662-183">Wildcards aren't supported.</span></span> <span data-ttu-id="f4662-184">Você pode pesquisar pelos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="f4662-184">You can search by the following values:</span></span>

   - <span data-ttu-id="f4662-185">**ID da mensagem**: o identificador globalmente exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="f4662-185">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="f4662-186">Por exemplo, você [usou](message-trace-scc.md) o rastreamento de mensagens para procurar uma mensagem que foi enviada a um usuário em sua organização e determina que a mensagem foi colocada em quarentena em vez de entregue.</span><span class="sxs-lookup"><span data-stu-id="f4662-186">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="f4662-187">Certifique-se de incluir o valor completo da ID da mensagem, que pode incluir colchetes angulares ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="f4662-187">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="f4662-188">Por exemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="f4662-188">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="f4662-189">**Endereço de e-mail do remetente**: o endereço de e-mail de um único remetente.</span><span class="sxs-lookup"><span data-stu-id="f4662-189">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="f4662-190">**Nome da política**: Use o nome completo da política da mensagem.</span><span class="sxs-lookup"><span data-stu-id="f4662-190">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="f4662-191">A pesquisa não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f4662-191">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="f4662-192">**Endereço de e-mail do destinatário**: o endereço de e-mail de um único destinatário.</span><span class="sxs-lookup"><span data-stu-id="f4662-192">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="f4662-193">**Assunto**: use todo o assunto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="f4662-193">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="f4662-194">A pesquisa não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f4662-194">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="f4662-195">**Nome da** política : o nome da política responsável pela quarentena da mensagem.</span><span class="sxs-lookup"><span data-stu-id="f4662-195">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="f4662-196">Depois de ter inserido os critérios da pesquisa, clique em ![Atualizar botão](../../media/scc-quarantine-refresh.png) **Atualizar** para filtrar os resultados.</span><span class="sxs-lookup"><span data-stu-id="f4662-196">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="f4662-197">Depois de encontrar uma mensagem específica em quarentena, selecione a mensagem para exibir detalhes sobre ela e execute uma ação (por exemplo: exibir, liberar, fazer download ou excluir a mensagem).</span><span class="sxs-lookup"><span data-stu-id="f4662-197">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="f4662-198">Exiba detalhes da mensagem em quarentena</span><span class="sxs-lookup"><span data-stu-id="f4662-198">View quarantined message details</span></span>

<span data-ttu-id="f4662-199">Quando você clica em uma mensagem de e-mail na lista, os seguintes detalhes de mensagem são exibidos no painel de submenu **Detalhes**:</span><span class="sxs-lookup"><span data-stu-id="f4662-199">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="f4662-200">**ID da mensagem**: o identificador globalmente exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="f4662-200">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="f4662-201">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="f4662-201">**Sender address**</span></span>

- <span data-ttu-id="f4662-202">**Recebido**: a data e a hora em que a mensagem foi recebida.</span><span class="sxs-lookup"><span data-stu-id="f4662-202">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="f4662-203">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="f4662-203">**Subject**</span></span>

- <span data-ttu-id="f4662-204">**Motivo da** quarentena: mostra se uma mensagem foi identificada como **Spam,** **Massa,** **Phish,** correspondência de uma regra de fluxo de emails **(** regra de transporte ), ou foi identificada como contendo **Malware**.</span><span class="sxs-lookup"><span data-stu-id="f4662-204">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="f4662-205">**Contagem de destinatários**</span><span class="sxs-lookup"><span data-stu-id="f4662-205">**Recipient count**</span></span>

- <span data-ttu-id="f4662-206">**Destinatários**: se a mensagem contiver vários destinatários, você precisará clicar em **Visualizar mensagem** ou **Exibir o cabeçalho da mensagem** para visualizar a lista completa dos destinatários.</span><span class="sxs-lookup"><span data-stu-id="f4662-206">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="f4662-207">**Expira**: a data/hora em que a mensagem será excluída de forma automática e permanente da quarentena.</span><span class="sxs-lookup"><span data-stu-id="f4662-207">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="f4662-208">**Liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem foi liberada.</span><span class="sxs-lookup"><span data-stu-id="f4662-208">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="f4662-209">**Sem liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem não foi liberada.</span><span class="sxs-lookup"><span data-stu-id="f4662-209">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="f4662-210">Tomar medidas quanto aos e-mails em quarentena</span><span class="sxs-lookup"><span data-stu-id="f4662-210">Take action on quarantined email</span></span>

<span data-ttu-id="f4662-211">Depois de selecionar uma mensagem, você tem várias opções para o que fazer com as mensagens no painel **detalhes** do sobremenu:</span><span class="sxs-lookup"><span data-stu-id="f4662-211">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="f4662-212">**Mensagem de** versão : no painel de sobrevoos que aparece, escolha as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="f4662-212">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="f4662-213">**Relatar mensagens à Microsoft** para análise : isso é selecionado por padrão e relata a mensagem erroneamente em quarentena para a Microsoft como um falso positivo.</span><span class="sxs-lookup"><span data-stu-id="f4662-213">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="f4662-214">Se a mensagem foi colocada em quarentena como spam, massa, phishing ou malware, a mensagem também será relatada à Equipe de Análise de Spam da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f4662-214">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="f4662-215">Dependendo da análise, as regras de filtro de spam em todo o serviço podem ser ajustadas para permitir a passagem da mensagem.</span><span class="sxs-lookup"><span data-stu-id="f4662-215">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="f4662-216">Escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="f4662-216">Choose one of the following options:</span></span>
    - <span data-ttu-id="f4662-217">**Liberar mensagens para todos os destinatários**</span><span class="sxs-lookup"><span data-stu-id="f4662-217">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="f4662-218">**Liberar mensagens para destinatários específicos**</span><span class="sxs-lookup"><span data-stu-id="f4662-218">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="f4662-219">**Liberar mensagens para outras pessoas:** não há suporte para liberar mensagens de malware para outras pessoas que não os destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="f4662-219">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="f4662-220">Quando terminar, clique em **Liberar mensagens**.</span><span class="sxs-lookup"><span data-stu-id="f4662-220">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="f4662-221">Observações sobre a liberação de mensagens:</span><span class="sxs-lookup"><span data-stu-id="f4662-221">Notes about releasing messages:</span></span>

  - <span data-ttu-id="f4662-222">Não é possível liberar uma mensagem para o mesmo destinatário mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="f4662-222">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="f4662-223">Somente os destinatários que não receberam a mensagem aparecerão na lista de destinatários em potencial.</span><span class="sxs-lookup"><span data-stu-id="f4662-223">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="f4662-224">**Exibir cabeçalho da mensagem**: escolha este link para visualizar o texto do cabeçalho da mensagem.</span><span class="sxs-lookup"><span data-stu-id="f4662-224">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="f4662-225">Para analisar os valores e campos de cabeçalho em detalhes, copie o texto do cabeçalho da mensagem para a área de transferência e, em seguida, escolha **Analisador de Cabeçalhos de Mensagens da Microsoft** para acessar o Analisar de Conectividade Remota (clique com o botão direito e escolha **Abrir em uma nova guia** se não quiser deixar o Microsoft 365 para concluir essa tarefa).</span><span class="sxs-lookup"><span data-stu-id="f4662-225">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="f4662-226">Cole o cabeçalho da mensagem na página na seção Analisador do cabeçalho da mensagem e escolha **Analisar cabeçalhos**:</span><span class="sxs-lookup"><span data-stu-id="f4662-226">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="f4662-227">**Visualizar mensagem**: no painel de submenu que é exibido, escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="f4662-227">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="f4662-228">**Visualização da fonte**: mostra a versão HTML do corpo da mensagem com todos os links desabilitados.</span><span class="sxs-lookup"><span data-stu-id="f4662-228">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="f4662-229">**Visualização do texto**: mostra o corpo da mensagem em texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="f4662-229">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="f4662-230">**Remover da quarentena**: depois de clicar em **Sim** no aviso exibido, a mensagem será imediatamente excluída sem ser enviada aos destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="f4662-230">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="f4662-231">**Mensagem de download**: no painel de submenu que é exibido, clique em **Compreendo os riscos de baixar esta mensagem** para salvar uma cópia local da mensagem no formato .eml.</span><span class="sxs-lookup"><span data-stu-id="f4662-231">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="f4662-232">**Bloquear Remetente**: Adicione o remetente à lista Remetentes Bloqueados em sua caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="f4662-232">**Block Sender**: Add the sender to the Blocked Senders list on your mailbox.</span></span> <span data-ttu-id="f4662-233">Para obter mais informações, consulte [Bloquear um remetente de email](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span><span class="sxs-lookup"><span data-stu-id="f4662-233">For more information, see [Block a mail sender](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).</span></span>

- <span data-ttu-id="f4662-234">**Enviar mensagem**: no painel de sub-texto que aparece, escolha as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="f4662-234">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="f4662-235">**Tipo de objeto**: **Email** (padrão), **URL** ou **Anexo.**</span><span class="sxs-lookup"><span data-stu-id="f4662-235">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="f4662-236">**Formato de envio**: **ID** da Mensagem de Rede (padrão, com o valor correspondente na caixa **ID** da Mensagem de Rede) ou **Arquivo** (navegue até um arquivo .eml ou .msg local).</span><span class="sxs-lookup"><span data-stu-id="f4662-236">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="f4662-237">Observe que, se você selecionar **Arquivo** e, em seguida, selecionar ID da Mensagem de **Rede,** o valor inicial se foi.</span><span class="sxs-lookup"><span data-stu-id="f4662-237">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="f4662-238">**Destinatários**: Digite em locação um destinatário original da mensagem ou clique em **Selecionar Todos** para identificar todos os destinatários.</span><span class="sxs-lookup"><span data-stu-id="f4662-238">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="f4662-239">Você também pode clicar em **Selecionar Tudo** e remover seletivamente destinatários individuais.</span><span class="sxs-lookup"><span data-stu-id="f4662-239">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="f4662-240">**Motivo do envio:** **não deve ter sido bloqueado** (padrão) ou deve ter sido **bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="f4662-240">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="f4662-241">Quando terminar, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="f4662-241">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="f4662-242">Se você não liberar ou remover a mensagem, ela será excluída após o término do período de retenção da quarentena padrão.</span><span class="sxs-lookup"><span data-stu-id="f4662-242">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="f4662-243">Tome medidas em várias mensagens quanto aos e-mails em quarentena</span><span class="sxs-lookup"><span data-stu-id="f4662-243">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="f4662-244">Quando você seleciona várias mensagens que estão em quarentena na lista (até 100), o painel de submenu **Ações em massa** é exibido em que você pode realizar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="f4662-244">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="f4662-245">**Mensagens de lançamento**: as opções são as mesmas de quando você libera uma única mensagem, mas não é possível clicar em **Liberar mensagens para destinatários específicos**; você só pode clicar em **Mensagem de lançamento a todos os destinatários** ou **Liberar mensagens para outras pessoas**.</span><span class="sxs-lookup"><span data-stu-id="f4662-245">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="f4662-246">Considere o seguinte cenário: john@gmail.com envia uma mensagem para faith@contoso.com e john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f4662-246">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="f4662-247">O Gmail bifurca essa mensagem em duas cópias que são encaminhadas para a quarentena como phishing na Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f4662-247">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="f4662-248">Um administrador libera ambas as mensagens para admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="f4662-248">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="f4662-249">A primeira mensagem liberada que atinge a caixa de correio de administrador é entregue.</span><span class="sxs-lookup"><span data-stu-id="f4662-249">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="f4662-250">A segunda mensagem liberada é identificada como entrega duplicada e ignorada.</span><span class="sxs-lookup"><span data-stu-id="f4662-250">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="f4662-251">A mensagem será identificada como duplicata se tiver a mesma ID da mensagem e receber o tempo.</span><span class="sxs-lookup"><span data-stu-id="f4662-251">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="f4662-252">**Excluir mensagens**: depois de clicar em **Sim** no aviso exibido, as mensagens serão imediatamente excluídas sem serem enviadas aos destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="f4662-252">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="f4662-253">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="f4662-253">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="f4662-254">Microsoft Defender para Office 365 Somente: use o Centro de Conformidade & Segurança para gerenciar arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="f4662-254">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="f4662-255">Os procedimentos para arquivos em quarentena nesta seção estão disponíveis apenas para assinantes do Microsoft Defender para Office 365 Plano 1 e Plano 2.</span><span class="sxs-lookup"><span data-stu-id="f4662-255">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="f4662-256">Em organizações com o Defender para Office 365, os administradores podem gerenciar arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f4662-256">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="f4662-257">Para habilitar a proteção para esses arquivos, consulte [Ativar Anexos Seguros para SharePoint, OneDrive e Microsoft Teams.](turn-on-mdo-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f4662-257">To enable protection for these files, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="f4662-258">Exibir arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="f4662-258">View quarantined files</span></span>

1. <span data-ttu-id="f4662-259">No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.</span><span class="sxs-lookup"><span data-stu-id="f4662-259">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="f4662-260">Alterar **Exibição em quarentena** para os arquivos de **valor**.</span><span class="sxs-lookup"><span data-stu-id="f4662-260">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="f4662-261">Você pode classificar em um campo clicando em um header de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="f4662-261">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="f4662-262">Você pode classificar os resultados clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="f4662-262">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="f4662-263">Clique em **Modificar colunas** para exibir um máximo de sete colunas.</span><span class="sxs-lookup"><span data-stu-id="f4662-263">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="f4662-264">As colunas padrão são marcadas com um asterisco ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="f4662-264">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="f4662-265">**Usuário**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f4662-265">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="f4662-266">**Local**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f4662-266">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="f4662-267">**Nome do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f4662-267">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="f4662-268">**URL do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f4662-268">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="f4662-269">**Tamanho do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f4662-269">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="f4662-270">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f4662-270">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="f4662-271">**Lançado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="f4662-271">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="f4662-272">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="f4662-272">**Detected by**</span></span>
   - <span data-ttu-id="f4662-273">**Modificado pelo tempo**</span><span class="sxs-lookup"><span data-stu-id="f4662-273">**Modified by time**</span></span>

4. <span data-ttu-id="f4662-274">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="f4662-274">To filter the results, click **Filter**.</span></span> <span data-ttu-id="f4662-275">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="f4662-275">The available filters are:</span></span>

   - <span data-ttu-id="f4662-276">**Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:</span><span class="sxs-lookup"><span data-stu-id="f4662-276">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="f4662-277">**Hoje**</span><span class="sxs-lookup"><span data-stu-id="f4662-277">**Today**</span></span>
     - <span data-ttu-id="f4662-278">**Próximos 2 dias**</span><span class="sxs-lookup"><span data-stu-id="f4662-278">**Next 2 days**</span></span>
     - <span data-ttu-id="f4662-279">**Próximas 7 semanas**</span><span class="sxs-lookup"><span data-stu-id="f4662-279">**Next 7 days**</span></span>
     - <span data-ttu-id="f4662-280">Um intervalo de data/hora personalizado.</span><span class="sxs-lookup"><span data-stu-id="f4662-280">A custom date/time range.</span></span>
   - <span data-ttu-id="f4662-281">**Tempo de recebido**</span><span class="sxs-lookup"><span data-stu-id="f4662-281">**Received time**</span></span>
   - <span data-ttu-id="f4662-282">**Motivo da quarentena**: o único valor disponível é **Malware**.</span><span class="sxs-lookup"><span data-stu-id="f4662-282">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="f4662-283">**Tipo de política**</span><span class="sxs-lookup"><span data-stu-id="f4662-283">**Policy type**</span></span>

<span data-ttu-id="f4662-284">Depois de encontrar um arquivo em quarentena específico, selecione o arquivo para exibir detalhes sobre ele e para tomar medidas nele (por exemplo, exibir, liberar, baixar ou excluir a mensagem).</span><span class="sxs-lookup"><span data-stu-id="f4662-284">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="f4662-285">Exibir detalhes do arquivo em quarentena</span><span class="sxs-lookup"><span data-stu-id="f4662-285">View quarantined file details</span></span>

<span data-ttu-id="f4662-286">Quando você seleciona um arquivo na lista, os seguintes detalhes do arquivo aparecem no painel **Detalhes** do flyout:</span><span class="sxs-lookup"><span data-stu-id="f4662-286">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="f4662-287">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="f4662-287">**File Name**</span></span>
- <span data-ttu-id="f4662-288">**URL do** arquivo : URL que define o local do arquivo (por exemplo, no SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="f4662-288">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="f4662-289">**Conteúdo mal-intencionado detectado em** A data/hora em que o arquivo foi colocado em quarentena.</span><span class="sxs-lookup"><span data-stu-id="f4662-289">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="f4662-290">**Expira**: a data em que o arquivo será excluído da quarentena.</span><span class="sxs-lookup"><span data-stu-id="f4662-290">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="f4662-291">**Detectado por**: Defender para Office 365 ou mecanismo anti-malware da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f4662-291">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="f4662-292">**Lançado?**</span><span class="sxs-lookup"><span data-stu-id="f4662-292">**Released?**</span></span>
- <span data-ttu-id="f4662-293">**Nome do malware**</span><span class="sxs-lookup"><span data-stu-id="f4662-293">**Malware Name**</span></span>
- <span data-ttu-id="f4662-294">**ID do** documento: um identificador exclusivo para o documento.</span><span class="sxs-lookup"><span data-stu-id="f4662-294">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="f4662-295">**Tamanho do** arquivo : em quilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="f4662-295">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="f4662-296">**Organização** A ID exclusiva da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f4662-296">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="f4662-297">**Última modificação**</span><span class="sxs-lookup"><span data-stu-id="f4662-297">**Last modified**</span></span>
- <span data-ttu-id="f4662-298">**Modificado por**: o usuário que modificou o arquivo pela última vez.</span><span class="sxs-lookup"><span data-stu-id="f4662-298">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="f4662-299">Valor do Algoritmo de Hash Seguro de **256 bits (SHA-256)**: Você pode usar esse valor de hash para identificar o arquivo em outros armazenamentos de reputação ou em outros locais em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="f4662-299">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="f4662-300">Tomar medidas em arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="f4662-300">Take action on quarantined files</span></span>

<span data-ttu-id="f4662-301">Ao selecionar um arquivo na lista, você pode tomar as seguintes ações no arquivo no painel **Detalhes** do flyout:</span><span class="sxs-lookup"><span data-stu-id="f4662-301">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="f4662-302">**Arquivos de versão**: Selecione (padrão) ou desmarcar Arquivos de relatório para **a Microsoft** para análise e clique em **Liberar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="f4662-302">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="f4662-303">**Baixar o arquivo**</span><span class="sxs-lookup"><span data-stu-id="f4662-303">**Download file**</span></span>
- <span data-ttu-id="f4662-304">**Remover arquivo da quarentena**</span><span class="sxs-lookup"><span data-stu-id="f4662-304">**Remove file from quarantine**</span></span>

<span data-ttu-id="f4662-305">Se você não liberar ou remover os arquivos, eles serão excluídos depois que o período de retenção de quarentena padrão expirar.</span><span class="sxs-lookup"><span data-stu-id="f4662-305">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="f4662-306">Ações em vários arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="f4662-306">Actions on multiple quarantined files</span></span>

<span data-ttu-id="f4662-307">Quando você seleciona vários arquivos em quarentena na lista (até 100), o painel de destaque de ações em massa aparece onde você pode tomar as seguintes ações: </span><span class="sxs-lookup"><span data-stu-id="f4662-307">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="f4662-308">**Liberar arquivos**</span><span class="sxs-lookup"><span data-stu-id="f4662-308">**Release files**</span></span>
- <span data-ttu-id="f4662-309">**Excluir arquivos**: depois de clicar **em Sim** no aviso que aparece, os arquivos serão imediatamente excluídos.</span><span class="sxs-lookup"><span data-stu-id="f4662-309">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="f4662-310">Use o PowerShell do Exchange Online ou o EOP PowerShell autônomo para exibir e gerenciar mensagens e arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="f4662-310">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="f4662-311">Os cmdlets que você usa para exibir e gerencia mensagens e arquivos em quarentena são:</span><span class="sxs-lookup"><span data-stu-id="f4662-311">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="f4662-312">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="f4662-312">Delete-QuarantineMessage</span></span>](/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="f4662-313">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="f4662-313">Export-QuarantineMessage</span></span>](/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="f4662-314">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="f4662-314">Get-QuarantineMessage</span></span>](/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="f4662-315">[Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage): observe que esse cmdlet é apenas para mensagens, não arquivos em quarentena de Anexos Seguros para SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f4662-315">[Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not quarantined files from Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

- [<span data-ttu-id="f4662-316">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="f4662-316">Release-QuarantineMessage</span></span>](/powershell/module/exchange/release-quarantinemessage)
