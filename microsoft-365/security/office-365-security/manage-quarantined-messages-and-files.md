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
ms.openlocfilehash: a91f53f8efe4fa6944f0debff472da87b7f17e0c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167486"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="6f3fe-104">Gerenciar arquivos e mensagens em quarentena como administrador no EOP</span><span class="sxs-lookup"><span data-stu-id="6f3fe-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6f3fe-105">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-105">**Applies to**</span></span>
- [<span data-ttu-id="6f3fe-106">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6f3fe-106">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="6f3fe-107">Microsoft Defender para Office 365 plano 1 e plano 2</span><span class="sxs-lookup"><span data-stu-id="6f3fe-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="6f3fe-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6f3fe-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="6f3fe-109">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena retém mensagens potencialmente perigosas ou indesejadas.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="6f3fe-110">Para obter mais informações, consulte [Mensagens de email em quarentena no EOP.](quarantine-email-messages.md)</span><span class="sxs-lookup"><span data-stu-id="6f3fe-110">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="6f3fe-111">Os administradores podem exibir, liberar e excluir todos os tipos de mensagens em quarentena para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-111">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="6f3fe-112">Somente os administradores podem gerenciar mensagens que foram colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="6f3fe-112">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="6f3fe-113">Os administradores também podem relatar falsos positivos à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-113">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="6f3fe-114">Os administradores em organizações com o Microsoft Defender para Office 365 também podem exibir, baixar e excluir arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-114">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="6f3fe-115">Você pode exibir e gerenciar mensagens em quarentena no Centro de Conformidade e Segurança ou no PowerShell (organizações do PowerShell do Exchange Online para Microsoft 365 com caixas de correio no Exchange Online; PowerShell do EOP autônomo para organizações sem caixas de correio do Exchange Online). &</span><span class="sxs-lookup"><span data-stu-id="6f3fe-115">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6f3fe-116">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="6f3fe-116">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6f3fe-117">Para abrir o Centro de Conformidade e Segurança, acesse <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-117">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="6f3fe-118">Para abrir a página Quarentena imediatamente, vá para <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-118">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="6f3fe-119">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="6f3fe-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="6f3fe-120">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="6f3fe-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="6f3fe-121">Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos deste artigo:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-121">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="6f3fe-122">Para agir em mensagens em quarentena para todos os usuários, você precisa ser membro dos grupos de função Gerenciamento da **Organização,** Administrador de Segurança ou Administrador **de** <sup>\*</sup> Quarentena.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-122">To take action on quarantined messages for all users, you need to be a member of the **Organization Management**, **Security Administrator**, or **Quarantine Administrator**<sup>\*</sup> role groups.</span></span>
  - <span data-ttu-id="6f3fe-123">Para acesso somente leitura a mensagens em quarentena para todos os usuários, você precisa ser membro dos grupos de funções Leitor **Global** ou **Leitor de** Segurança.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-123">For read-only access to quarantined messages for all users, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="6f3fe-124">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6f3fe-124">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  <span data-ttu-id="6f3fe-125">**Observações**:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-125">**Notes**:</span></span>

  - <span data-ttu-id="6f3fe-126">Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="6f3fe-127">Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="6f3fe-127">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  - <span data-ttu-id="6f3fe-128">O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-128">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>
  - <span data-ttu-id="6f3fe-129"><sup>\*</sup>Os membros do grupo **de** função Administrador  de Quarentena também precisam ser membros do grupo de funções Gerenciamento de Higienização no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) para realizar procedimentos de quarentena no PowerShell do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-129"><sup>\*</sup> Members of the **Quarantine Administrator** role group also need to be members of the **Hygiene Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) in order to do quarantine procedures in Exchange Online PowerShell.</span></span>

- <span data-ttu-id="6f3fe-130">As mensagens em quarentena são mantidas por um período padrão antes de elas ser excluídas automaticamente:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-130">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>
  - <span data-ttu-id="6f3fe-131">30 dias para mensagens em quarentena por políticas anti-spam (spam, phishing e email em massa).</span><span class="sxs-lookup"><span data-stu-id="6f3fe-131">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="6f3fe-132">Este é o valor padrão e máximo.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-132">This is the default and maximum value.</span></span> <span data-ttu-id="6f3fe-133">Para configurar (menos) esse valor, consulte [Configurar políticas anti-spam.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="6f3fe-133">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="6f3fe-134">15 dias para mensagens que contêm malware.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-134">15 days for messages that contain malware.</span></span>
  - <span data-ttu-id="6f3fe-135">15 dias para arquivos em quarentena pelos Anexos Seguros do SharePoint, OneDrive e Microsoft Teams no Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-135">15 days for files quarantined by Safe Attachments for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="6f3fe-136">Quando uma mensagem expira da quarentena, você não pode recuperá-la.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-136">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="6f3fe-137">Usar o Centro de Conformidade & segurança para gerenciar mensagens de email em quarentena</span><span class="sxs-lookup"><span data-stu-id="6f3fe-137">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="6f3fe-138">Exibir email em quarentena</span><span class="sxs-lookup"><span data-stu-id="6f3fe-138">View quarantined email</span></span>

1. <span data-ttu-id="6f3fe-139">No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-139">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="6f3fe-140">Verifique se **o modo de exibição** em quarentena está definido como o email de valor **padrão.**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-140">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="6f3fe-141">Você pode classificar os resultados clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-141">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="6f3fe-142">Clique em **Modificar colunas** para exibir um máximo de sete colunas.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-142">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="6f3fe-143">Os valores padrão são marcados com um asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="6f3fe-143">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="6f3fe-144">**Recebido**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6f3fe-144">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="6f3fe-145">**Remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6f3fe-145">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="6f3fe-146">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6f3fe-146">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="6f3fe-147">**Motivo da quarentena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6f3fe-147">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="6f3fe-148">**Lançado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6f3fe-148">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="6f3fe-149">**Tipo de política**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6f3fe-149">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="6f3fe-150">**Expires**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-150">**Expires**</span></span>
   - <span data-ttu-id="6f3fe-151">**Recipiente**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-151">**Recipient**</span></span>
   - <span data-ttu-id="6f3fe-152">**ID da mensagem**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-152">**Message ID**</span></span>
   - <span data-ttu-id="6f3fe-153">**Nome da política**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-153">**Policy name**</span></span>
   - <span data-ttu-id="6f3fe-154">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-154">**Size**</span></span>
   - <span data-ttu-id="6f3fe-155">**Direção**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-155">**Direction**</span></span>

   <span data-ttu-id="6f3fe-156">Quando você terminar, clique em **Salvar**, ou clique em **Definido como padrão**.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-156">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="6f3fe-157">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-157">To filter the results, click **Filter**.</span></span> <span data-ttu-id="6f3fe-158">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-158">The available filters are:</span></span>

   - <span data-ttu-id="6f3fe-159">**Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-159">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="6f3fe-160">**Hoje**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-160">**Today**</span></span>
     - <span data-ttu-id="6f3fe-161">**Próximos 2 dias**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-161">**Next 2 days**</span></span>
     - <span data-ttu-id="6f3fe-162">**Próximas 7 semanas**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-162">**Next 7 days**</span></span>
     - <span data-ttu-id="6f3fe-163">**Personalizado**: Insira uma **Data de início** e uma **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-163">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="6f3fe-164">**Hora recebida**: Insira uma **Data de início** e uma **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-164">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="6f3fe-165">**Motivo da quarentena**:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-165">**Quarantine reason**:</span></span>
     - <span data-ttu-id="6f3fe-166">**Política:** a mensagem a correspondência das condições de uma regra de fluxo de emails (também conhecida como regra de transporte).</span><span class="sxs-lookup"><span data-stu-id="6f3fe-166">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="6f3fe-167">**Em massa**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-167">**Bulk**</span></span>
     - <span data-ttu-id="6f3fe-168">**Phish**: o veredito do filtro de spam foi email de **phishing** ou proteção anti-phishing colocou a mensagem em quarentena (configurações de [spoof](set-up-anti-phishing-policies.md#spoof-settings) ou proteção [contra representação).](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</span><span class="sxs-lookup"><span data-stu-id="6f3fe-168">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="6f3fe-169">**Malware**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-169">**Malware**</span></span>
     - <span data-ttu-id="6f3fe-170">**Spam**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-170">**Spam**</span></span>
     - <span data-ttu-id="6f3fe-171">**Phishing de alta confiança**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-171">**High Confidence Phish**</span></span>

   - <span data-ttu-id="6f3fe-172">**Tipo de Política**: Filtre mensagens por tipo de política:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-172">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="6f3fe-173">**Política anti-malware**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-173">**Anti-malware policy**</span></span>
     - <span data-ttu-id="6f3fe-174">**Política de Anexos Seguros**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-174">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="6f3fe-175">**Política Anti-phish**:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-175">**Anti-phish policy**</span></span>
     - <span data-ttu-id="6f3fe-176">**Política de filtro de conteúdo hospedado** (política antispam)</span><span class="sxs-lookup"><span data-stu-id="6f3fe-176">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="6f3fe-177">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-177">**Transport rule**</span></span>

   - <span data-ttu-id="6f3fe-178">**Destinatário de** email: todos os usuários ou apenas mensagens enviadas para você.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-178">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="6f3fe-179">Os usuários finais só podem gerenciar mensagens em quarentena enviadas a eles.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-179">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="6f3fe-180">Para limpar o filtro, clique em **Limpar**.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-180">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="6f3fe-181">Para ocultar o submenu do filtro, clique novamente em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-181">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="6f3fe-182">Use **Classificar resultados por** (o botão **ID da mensagem** por padrão) e um valor correspondente para localizar mensagens específicas.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-182">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="6f3fe-183">Os curingas não possuem suporte.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-183">Wildcards aren't supported.</span></span> <span data-ttu-id="6f3fe-184">Você pode pesquisar pelos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-184">You can search by the following values:</span></span>

   - <span data-ttu-id="6f3fe-185">**ID da mensagem**: o identificador globalmente exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-185">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="6f3fe-186">Por exemplo, [](message-trace-scc.md) você usou o rastreamento de mensagens para procurar uma mensagem que foi enviada para um usuário em sua organização e você determina que a mensagem foi colocada em quarentena em vez de entregue.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-186">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="6f3fe-187">Certifique-se de incluir o valor completo da ID da mensagem, que pode incluir colchetes angulares ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="6f3fe-187">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="6f3fe-188">Por exemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-188">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="6f3fe-189">**Endereço de e-mail do remetente**: o endereço de e-mail de um único remetente.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-189">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="6f3fe-190">**Nome da política**: Use o nome completo da política da mensagem.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-190">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="6f3fe-191">A pesquisa não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-191">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="6f3fe-192">**Endereço de e-mail do destinatário**: o endereço de e-mail de um único destinatário.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-192">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="6f3fe-193">**Assunto**: use todo o assunto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-193">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="6f3fe-194">A pesquisa não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-194">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="6f3fe-195">**Nome da** política: o nome da política responsável pela quarentena da mensagem.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-195">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="6f3fe-196">Depois de ter inserido os critérios da pesquisa, clique em ![Atualizar botão](../../media/scc-quarantine-refresh.png) **Atualizar** para filtrar os resultados.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-196">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="6f3fe-197">Depois de encontrar uma mensagem específica em quarentena, selecione a mensagem para exibir detalhes sobre ela e execute uma ação (por exemplo: exibir, liberar, fazer download ou excluir a mensagem).</span><span class="sxs-lookup"><span data-stu-id="6f3fe-197">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="6f3fe-198">Exiba detalhes da mensagem em quarentena</span><span class="sxs-lookup"><span data-stu-id="6f3fe-198">View quarantined message details</span></span>

<span data-ttu-id="6f3fe-199">Quando você clica em uma mensagem de e-mail na lista, os seguintes detalhes de mensagem são exibidos no painel de submenu **Detalhes**:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-199">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="6f3fe-200">**ID da mensagem**: o identificador globalmente exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-200">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="6f3fe-201">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-201">**Sender address**</span></span>

- <span data-ttu-id="6f3fe-202">**Recebido**: a data e a hora em que a mensagem foi recebida.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-202">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="6f3fe-203">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-203">**Subject**</span></span>

- <span data-ttu-id="6f3fe-204">**Motivo da** quarentena: mostra se uma mensagem foi identificada como **Spam** **,** Bulk , **Phish**, matched a mail flow rule (**Transport rule**), ou foi identificada como contendo **Malware**.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-204">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="6f3fe-205">**Contagem de destinatários**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-205">**Recipient count**</span></span>

- <span data-ttu-id="6f3fe-206">**Destinatários**: se a mensagem contiver vários destinatários, você precisará clicar em **Visualizar mensagem** ou **Exibir o cabeçalho da mensagem** para visualizar a lista completa dos destinatários.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-206">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="6f3fe-207">**Expira**: a data/hora em que a mensagem será excluída de forma automática e permanente da quarentena.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-207">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="6f3fe-208">**Liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem foi liberada.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-208">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="6f3fe-209">**Sem liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem não foi liberada.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-209">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="6f3fe-210">Tomar medidas quanto aos e-mails em quarentena</span><span class="sxs-lookup"><span data-stu-id="6f3fe-210">Take action on quarantined email</span></span>

<span data-ttu-id="6f3fe-211">Depois de selecionar uma mensagem, você tem várias opções sobre o que fazer com as mensagens no painel do **menu** desdopo Detalhes:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-211">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="6f3fe-212">**Mensagem de** liberação: no painel do menu desdolado exibido, escolha as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-212">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="6f3fe-213">**Relatar mensagens à Microsoft para** análise: ela é selecionada por padrão e relata a mensagem erroneamente em quarentena à Microsoft como um falso positivo.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-213">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="6f3fe-214">Se a mensagem foi colocada em quarentena como spam, em massa, phishing ou malware, a mensagem também será relatada à Equipe de Análise de Spam da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-214">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="6f3fe-215">Dependendo da análise, as regras de filtro de spam de todo o serviço podem ser ajustadas para permitir a passagem da mensagem.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-215">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="6f3fe-216">Escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-216">Choose one of the following options:</span></span>
    - <span data-ttu-id="6f3fe-217">**Liberar mensagens para todos os destinatários**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-217">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="6f3fe-218">**Liberar mensagens para destinatários específicos**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-218">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="6f3fe-219">**Liberar mensagens para outras pessoas:** Observe que não há suporte para a liberação de mensagens de malware para pessoas que não são destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-219">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span>

  <span data-ttu-id="6f3fe-220">Quando terminar, clique em **Liberar mensagens**.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-220">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="6f3fe-221">Observações sobre a liberação de mensagens:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-221">Notes about releasing messages:</span></span>

  - <span data-ttu-id="6f3fe-222">Você não pode liberar uma mensagem para o mesmo destinatário mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-222">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="6f3fe-223">Somente os destinatários que não receberam a mensagem aparecerão na lista de possíveis destinatários.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-223">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="6f3fe-224">**Exibir cabeçalho da mensagem**: escolha este link para visualizar o texto do cabeçalho da mensagem.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-224">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="6f3fe-225">Para analisar os valores e campos de cabeçalho em detalhes, copie o texto do cabeçalho da mensagem para a área de transferência e, em seguida, escolha **Analisador de Cabeçalhos de Mensagens da Microsoft** para acessar o Analisar de Conectividade Remota (clique com o botão direito e escolha **Abrir em uma nova guia** se não quiser deixar o Microsoft 365 para concluir essa tarefa).</span><span class="sxs-lookup"><span data-stu-id="6f3fe-225">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="6f3fe-226">Cole o cabeçalho da mensagem na página na seção Analisador do cabeçalho da mensagem e escolha **Analisar cabeçalhos**:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-226">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="6f3fe-227">**Visualizar mensagem**: no painel de submenu que é exibido, escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-227">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="6f3fe-228">**Visualização da fonte**: mostra a versão HTML do corpo da mensagem com todos os links desabilitados.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-228">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="6f3fe-229">**Visualização do texto**: mostra o corpo da mensagem em texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-229">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="6f3fe-230">**Remover da quarentena:** depois de clicar em **Sim** no aviso exibido, a mensagem será imediatamente excluída sem ser enviada aos destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-230">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="6f3fe-231">**Mensagem de download**: no painel de submenu que é exibido, clique em **Compreendo os riscos de baixar esta mensagem** para salvar uma cópia local da mensagem no formato .eml.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-231">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="6f3fe-232">**Enviar mensagem:** no painel do sub-menu que aparece, escolha as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-232">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="6f3fe-233">**Tipo de** objeto: **Email** (padrão), **URL** ou **Anexo.**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-233">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="6f3fe-234">**Formato de** envio: **ID** da Mensagem de Rede (padrão, com o valor correspondente na caixa **ID** da Mensagem de Rede) ou **Arquivo** (navegue até um arquivo .eml ou .msg local).</span><span class="sxs-lookup"><span data-stu-id="6f3fe-234">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="6f3fe-235">Observe que, se você selecionar **Arquivo** e, em seguida, selecionar **a ID** da Mensagem de Rede, o valor inicial será eliminado.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-235">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="6f3fe-236">**Destinatários:** digite na concessão um destinatário original da mensagem ou clique em **Selecionar Tudo** para identificar todos os destinatários.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-236">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="6f3fe-237">Você também pode clicar **em Selecionar Tudo** e remover seletivamente destinatários individuais.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-237">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="6f3fe-238">**Motivo do envio:** **Não deveria ter sido bloqueado** (padrão) ou deveria ter sido **bloqueado.**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-238">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="6f3fe-239">Quando terminar, clique em **Enviar.**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-239">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="6f3fe-240">Se você não liberar ou remover a mensagem, ela será excluída após o término do período de retenção da quarentena padrão.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-240">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="6f3fe-241">Tome medidas em várias mensagens quanto aos e-mails em quarentena</span><span class="sxs-lookup"><span data-stu-id="6f3fe-241">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="6f3fe-242">Quando você seleciona várias mensagens que estão em quarentena na lista (até 100), o painel de submenu **Ações em massa** é exibido em que você pode realizar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-242">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="6f3fe-243">**Mensagens de lançamento**: as opções são as mesmas de quando você libera uma única mensagem, mas não é possível clicar em **Liberar mensagens para destinatários específicos**; você só pode clicar em **Mensagem de lançamento a todos os destinatários** ou **Liberar mensagens para outras pessoas**.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-243">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="6f3fe-244">Considere o seguinte cenário: john@gmail.com envia uma mensagem para faith@contoso.com e john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-244">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="6f3fe-245">O Gmail bifurca essa mensagem em duas cópias que são encaminhadas para a quarentena como phishing na Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-245">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="6f3fe-246">Um administrador libera essas duas mensagens para admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-246">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="6f3fe-247">A primeira mensagem liberada que atinge a caixa de correio de administrador é entregue.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-247">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="6f3fe-248">A segunda mensagem liberada é identificada como entrega duplicada e ignorada.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-248">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="6f3fe-249">As mensagens serão identificadas como duplicatas se elas têm a mesma ID de mensagem e hora recebida.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-249">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="6f3fe-250">**Excluir mensagens:** depois de clicar em **Sim** no aviso exibido, as mensagens são imediatamente excluídas sem serem enviadas aos destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-250">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="6f3fe-251">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-251">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="6f3fe-252">Microsoft Defender para Office 365 Apenas: use o Centro de Conformidade e Segurança & gerenciar arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="6f3fe-252">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="6f3fe-253">Os procedimentos para arquivos em quarentena nesta seção estão disponíveis apenas para assinantes do Microsoft Defender para Office 365 Plano 1 e Plano 2.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-253">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="6f3fe-254">Em organizações com o Defender para Office 365, os administradores podem gerenciar arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-254">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="6f3fe-255">Para habilitar a proteção para esses arquivos, confira [Ativar Anexos Seguros para SharePoint, OneDrive e Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="6f3fe-255">To enable protection for these files, see [Turn on Safe Attachments for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="6f3fe-256">Exibir arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="6f3fe-256">View quarantined files</span></span>

1. <span data-ttu-id="6f3fe-257">No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-257">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="6f3fe-258">Alterar **o exibição em quarentena** para os arquivos de **valor.**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-258">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="6f3fe-259">Você pode classificar em um campo clicando em um header de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-259">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="6f3fe-260">Você pode classificar os resultados clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-260">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="6f3fe-261">Clique em **Modificar colunas** para exibir um máximo de sete colunas.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-261">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="6f3fe-262">As colunas padrão são marcadas com um asterisco ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="6f3fe-262">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="6f3fe-263">**Usuário**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6f3fe-263">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="6f3fe-264">**Localização**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6f3fe-264">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="6f3fe-265">**Nome do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6f3fe-265">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="6f3fe-266">**URL do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6f3fe-266">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="6f3fe-267">**Tamanho do Arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6f3fe-267">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="6f3fe-268">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6f3fe-268">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="6f3fe-269">**Lançado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="6f3fe-269">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="6f3fe-270">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-270">**Detected by**</span></span>
   - <span data-ttu-id="6f3fe-271">**Modificado por hora**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-271">**Modified by time**</span></span>

4. <span data-ttu-id="6f3fe-272">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-272">To filter the results, click **Filter**.</span></span> <span data-ttu-id="6f3fe-273">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-273">The available filters are:</span></span>

   - <span data-ttu-id="6f3fe-274">**Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-274">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="6f3fe-275">**Hoje**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-275">**Today**</span></span>
     - <span data-ttu-id="6f3fe-276">**Próximos 2 dias**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-276">**Next 2 days**</span></span>
     - <span data-ttu-id="6f3fe-277">**Próximas 7 semanas**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-277">**Next 7 days**</span></span>
     - <span data-ttu-id="6f3fe-278">Um intervalo de data/hora personalizado.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-278">A custom date/time range.</span></span>
   - <span data-ttu-id="6f3fe-279">**Hora de recebido**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-279">**Received time**</span></span>
   - <span data-ttu-id="6f3fe-280">**Motivo da quarentena:** o único valor disponível é **Malware**.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-280">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="6f3fe-281">**Tipo de política**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-281">**Policy type**</span></span>

<span data-ttu-id="6f3fe-282">Depois de encontrar um arquivo em quarentena específico, selecione o arquivo para exibir detalhes sobre ele e para agir sobre ele (por exemplo, exibir, liberar, baixar ou excluir a mensagem).</span><span class="sxs-lookup"><span data-stu-id="6f3fe-282">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="6f3fe-283">Exibir detalhes do arquivo em quarentena</span><span class="sxs-lookup"><span data-stu-id="6f3fe-283">View quarantined file details</span></span>

<span data-ttu-id="6f3fe-284">Quando você seleciona um arquivo na lista, os seguintes detalhes do arquivo são exibidos **no** painel de detalhes do painel:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-284">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="6f3fe-285">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-285">**File Name**</span></span>
- <span data-ttu-id="6f3fe-286">**URL do** arquivo: URL que define o local do arquivo (por exemplo, no SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="6f3fe-286">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="6f3fe-287">**Conteúdo mal-intencionado detectado em** A data/hora em que o arquivo foi colocado em quarentena.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-287">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="6f3fe-288">**Expira :** a data em que o arquivo será excluído da quarentena.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-288">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="6f3fe-289">**Detectado por:** Defender para Office 365 ou mecanismo anti-malware da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-289">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="6f3fe-290">**Lançado?**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-290">**Released?**</span></span>
- <span data-ttu-id="6f3fe-291">**Nome do malware**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-291">**Malware Name**</span></span>
- <span data-ttu-id="6f3fe-292">**ID do** documento: um identificador exclusivo para o documento.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-292">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="6f3fe-293">**Tamanho do** arquivo: em kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="6f3fe-293">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="6f3fe-294">**Organização** A ID exclusiva da sua organização.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-294">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="6f3fe-295">**Última modificação**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-295">**Last modified**</span></span>
- <span data-ttu-id="6f3fe-296">**Modificado por:** o usuário que modificou o arquivo pela última vez.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-296">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="6f3fe-297">Valor de Algoritmo de Hash Seguro de **256 bits (SHA-256).** Você pode usar esse valor de hash para identificar o arquivo em outros armazenamentos de reputação ou em outros locais em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-297">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="6f3fe-298">Tomar medidas em arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="6f3fe-298">Take action on quarantined files</span></span>

<span data-ttu-id="6f3fe-299">Ao selecionar um arquivo na lista, você pode tomar as seguintes ações no arquivo no **painel** de detalhes do painel:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-299">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="6f3fe-300">**Arquivos de** versão: Selecione (padrão) ou desmarque arquivos de relatório para análise da **Microsoft** e clique em **Liberar arquivos.**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-300">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="6f3fe-301">**Baixar o arquivo**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-301">**Download file**</span></span>
- <span data-ttu-id="6f3fe-302">**Remover arquivo da quarentena**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-302">**Remove file from quarantine**</span></span>

<span data-ttu-id="6f3fe-303">Se você não liberar ou remover os arquivos, eles serão excluídos depois que o período de retenção de quarentena padrão expirar.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-303">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="6f3fe-304">Ações em vários arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="6f3fe-304">Actions on multiple quarantined files</span></span>

<span data-ttu-id="6f3fe-305">Quando você seleciona vários arquivos em quarentena na lista (até 100), o painel do flyout ações em massa é exibido onde você pode tomar as seguintes ações: </span><span class="sxs-lookup"><span data-stu-id="6f3fe-305">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="6f3fe-306">**Liberar arquivos**</span><span class="sxs-lookup"><span data-stu-id="6f3fe-306">**Release files**</span></span>
- <span data-ttu-id="6f3fe-307">**Excluir arquivos:** depois de clicar em **Sim** no aviso exibido, os arquivos serão imediatamente excluídos.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-307">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="6f3fe-308">Usar o PowerShell do Exchange Online ou o EOP PowerShell autônomo para exibir e gerenciar arquivos e mensagens em quarentena</span><span class="sxs-lookup"><span data-stu-id="6f3fe-308">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="6f3fe-309">Os cmdlets que você usa para exibir e gerencia mensagens e arquivos em quarentena são:</span><span class="sxs-lookup"><span data-stu-id="6f3fe-309">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="6f3fe-310">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="6f3fe-310">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="6f3fe-311">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="6f3fe-311">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="6f3fe-312">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="6f3fe-312">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="6f3fe-313">[Preview-QuarantineMessage:](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)observe que esse cmdlet é destinado apenas a mensagens, não a arquivos de malware de Anexos Seguros para SharePoint, OneDrive e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6f3fe-313">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from Safe Attachments for SharePoint, OneDrive, and Microsoft Teams.</span></span>

- [<span data-ttu-id="6f3fe-314">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="6f3fe-314">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
