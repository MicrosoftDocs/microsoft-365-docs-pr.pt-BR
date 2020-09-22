---
title: Gerenciar arquivos e mensagens em quarentena como um administrador
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
description: Os administradores podem aprender a exibir e gerenciar mensagens em quarentena para todos os usuários na proteção do Exchange Online (EOP). Administradores nas organizações com a proteção avançada contra ameaças do Office 365 (Office 365 ATP) também podem gerenciar arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.
ms.openlocfilehash: 1969a282d5d083886b9ad5a8aae54896ea9b1fc1
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202418"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="52c40-104">Gerenciar arquivos e mensagens em quarentena como administrador no EOP</span><span class="sxs-lookup"><span data-stu-id="52c40-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="52c40-105">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena retém mensagens potencialmente perigosas ou indesejadas.</span><span class="sxs-lookup"><span data-stu-id="52c40-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="52c40-106">Para obter mais informações, consulte [mensagens de email em quarentena no EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="52c40-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="52c40-107">Os administradores podem exibir, liberar e excluir todos os tipos de mensagens em quarentena para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="52c40-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="52c40-108">Somente os administradores podem gerenciar mensagens que foram colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="52c40-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="52c40-109">Os administradores também podem relatar falsos positivos para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="52c40-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="52c40-110">Administradores nas organizações com a proteção avançada contra ameaças do Office 365 (Office 365 ATP) também podem exibir, baixar e excluir arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="52c40-110">Admins in organizations with Office 365 Advance Threat Protection (Office 365 ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="52c40-111">Você exibir e gerenciar mensagens em quarentena no centro de conformidade e segurança & ou no PowerShell (PowerShell do Exchange Online para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="52c40-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="52c40-112">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="52c40-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="52c40-113">Para abrir o Centro de Conformidade e Segurança, acesse <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="52c40-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="52c40-114">Para abrir a página Quarentena imediatamente, vá para <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="52c40-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="52c40-115">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="52c40-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="52c40-116">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="52c40-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="52c40-117">Você precisa receber permissões antes de gerenciar a quarentena como um administrador. As permissões são controladas pela função de **quarentena** no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="52c40-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="52c40-118">Por padrão, essa função é atribuída aos grupos de função **Gerenciamento da organização** (administradores globais), **administrador de quarentena**e administrador de **segurança** no centro de conformidade do & de segurança.</span><span class="sxs-lookup"><span data-stu-id="52c40-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="52c40-119">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="52c40-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="52c40-120">As mensagens em quarentena são mantidas por um período de tempo padrão antes de serem excluídas automaticamente:</span><span class="sxs-lookup"><span data-stu-id="52c40-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="52c40-121">Mensagens colocadas em quarentena por políticas antispam (spam, phishing e email em massa): 30 dias.</span><span class="sxs-lookup"><span data-stu-id="52c40-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="52c40-122">Este é o valor padrão e máximo.</span><span class="sxs-lookup"><span data-stu-id="52c40-122">This is the default and maximum value.</span></span> <span data-ttu-id="52c40-123">Para configurar esse valor, consulte [Configure anti-spam Policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="52c40-123">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="52c40-124">Mensagens que contêm malware: 15 dias.</span><span class="sxs-lookup"><span data-stu-id="52c40-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="52c40-125">Quando uma mensagem expira da quarentena, não é possível recuperá-la.</span><span class="sxs-lookup"><span data-stu-id="52c40-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="52c40-126">Usar o centro de conformidade de & de segurança para gerenciar mensagens de email em quarentena</span><span class="sxs-lookup"><span data-stu-id="52c40-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="52c40-127">Exibir email em quarentena</span><span class="sxs-lookup"><span data-stu-id="52c40-127">View quarantined email</span></span>

1. <span data-ttu-id="52c40-128">No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.</span><span class="sxs-lookup"><span data-stu-id="52c40-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="52c40-129">Verifique se a **exibição em quarentena** está definida com o valor padrão **email**.</span><span class="sxs-lookup"><span data-stu-id="52c40-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="52c40-130">Você pode classificar os resultados clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="52c40-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="52c40-131">Clique em **Modificar colunas** para exibir um máximo de sete colunas.</span><span class="sxs-lookup"><span data-stu-id="52c40-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="52c40-132">Os valores padrão são marcados com um asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="52c40-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="52c40-133">**Recebido**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52c40-133">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="52c40-134">**Remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52c40-134">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="52c40-135">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52c40-135">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="52c40-136">**Motivo da quarentena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52c40-136">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="52c40-137">**Lançado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52c40-137">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="52c40-138">**Tipo de política**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52c40-138">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="52c40-139">**Recipiente**</span><span class="sxs-lookup"><span data-stu-id="52c40-139">**Recipient**</span></span>

   - <span data-ttu-id="52c40-140">**ID da mensagem**</span><span class="sxs-lookup"><span data-stu-id="52c40-140">**Message ID**</span></span>

   - <span data-ttu-id="52c40-141">**Nome da política**</span><span class="sxs-lookup"><span data-stu-id="52c40-141">**Policy name**</span></span>

   - <span data-ttu-id="52c40-142">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="52c40-142">**Size**</span></span>

   - <span data-ttu-id="52c40-143">**Direção**</span><span class="sxs-lookup"><span data-stu-id="52c40-143">**Direction**</span></span>

   <span data-ttu-id="52c40-144">Quando você terminar, clique em **Salvar**, ou clique em **Definido como padrão**.</span><span class="sxs-lookup"><span data-stu-id="52c40-144">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="52c40-145">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="52c40-145">To filter the results, click **Filter**.</span></span> <span data-ttu-id="52c40-146">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="52c40-146">The available filters are:</span></span>

   - <span data-ttu-id="52c40-147">**Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:</span><span class="sxs-lookup"><span data-stu-id="52c40-147">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="52c40-148">**Hoje**</span><span class="sxs-lookup"><span data-stu-id="52c40-148">**Today**</span></span>

     - <span data-ttu-id="52c40-149">**Próximos 2 dias**</span><span class="sxs-lookup"><span data-stu-id="52c40-149">**Next 2 days**</span></span>

     - <span data-ttu-id="52c40-150">**Próximas 7 semanas**</span><span class="sxs-lookup"><span data-stu-id="52c40-150">**Next 7 days**</span></span>

     - <span data-ttu-id="52c40-151">**Personalizado**: Insira uma **Data de início** e uma **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="52c40-151">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="52c40-152">**Hora recebida**: Insira uma **Data de início** e uma **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="52c40-152">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="52c40-153">**Motivo da quarentena**:</span><span class="sxs-lookup"><span data-stu-id="52c40-153">**Quarantine reason**:</span></span>

     - <span data-ttu-id="52c40-154">**Política**: a mensagem correspondeu às condições de uma regra de fluxo de emails (também conhecida como regra de transporte).</span><span class="sxs-lookup"><span data-stu-id="52c40-154">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="52c40-155">**Em massa**</span><span class="sxs-lookup"><span data-stu-id="52c40-155">**Bulk**</span></span>

     - <span data-ttu-id="52c40-156">**Golpe**</span><span class="sxs-lookup"><span data-stu-id="52c40-156">**Phish**</span></span>

     - <span data-ttu-id="52c40-157">**Malware**</span><span class="sxs-lookup"><span data-stu-id="52c40-157">**Malware**</span></span>

     - <span data-ttu-id="52c40-158">**Spam**</span><span class="sxs-lookup"><span data-stu-id="52c40-158">**Spam**</span></span>

     - <span data-ttu-id="52c40-159">**Phishing de alta confiança**</span><span class="sxs-lookup"><span data-stu-id="52c40-159">**High Confidence Phish**</span></span>

   - <span data-ttu-id="52c40-160">**Destinatário do email**: todos os usuários ou apenas as mensagens enviadas a você.</span><span class="sxs-lookup"><span data-stu-id="52c40-160">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="52c40-161">Os usuários finais só podem gerenciar mensagens em quarentena enviadas para eles.</span><span class="sxs-lookup"><span data-stu-id="52c40-161">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="52c40-162">Para limpar o filtro, clique em **Limpar**.</span><span class="sxs-lookup"><span data-stu-id="52c40-162">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="52c40-163">Para ocultar o submenu do filtro, clique novamente em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="52c40-163">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="52c40-164">Use **Classificar resultados por** (o botão **ID da mensagem** por padrão) e um valor correspondente para localizar mensagens específicas.</span><span class="sxs-lookup"><span data-stu-id="52c40-164">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="52c40-165">Os curingas não possuem suporte.</span><span class="sxs-lookup"><span data-stu-id="52c40-165">Wildcards aren't supported.</span></span> <span data-ttu-id="52c40-166">Você pode pesquisar pelos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="52c40-166">You can search by the following values:</span></span>

   - <span data-ttu-id="52c40-167">**ID da mensagem**: o identificador globalmente exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="52c40-167">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="52c40-168">Por exemplo, você usou o [rastreamento de mensagens](message-trace-scc.md) para procurar uma mensagem que foi enviada a um usuário na sua organização, e você determina que a mensagem foi colocada em quarentena em vez de distribuída.</span><span class="sxs-lookup"><span data-stu-id="52c40-168">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="52c40-169">Certifique-se de incluir o valor completo da ID da mensagem, que pode incluir colchetes angulares ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="52c40-169">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="52c40-170">Por exemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="52c40-170">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="52c40-171">**Endereço de e-mail do remetente**: o endereço de e-mail de um único remetente.</span><span class="sxs-lookup"><span data-stu-id="52c40-171">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="52c40-172">**Endereço de e-mail do destinatário**: o endereço de e-mail de um único destinatário.</span><span class="sxs-lookup"><span data-stu-id="52c40-172">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="52c40-173">**Assunto**: use todo o assunto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="52c40-173">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="52c40-174">A pesquisa não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="52c40-174">The search is not case-sensitive.</span></span>

   <span data-ttu-id="52c40-175">Depois de ter inserido os critérios da pesquisa, clique em ![Atualizar botão](../../media/scc-quarantine-refresh.png) **Atualizar** para filtrar os resultados.</span><span class="sxs-lookup"><span data-stu-id="52c40-175">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="52c40-176">Depois de encontrar uma mensagem específica em quarentena, selecione a mensagem para exibir detalhes sobre ela e execute uma ação (por exemplo: exibir, liberar, fazer download ou excluir a mensagem).</span><span class="sxs-lookup"><span data-stu-id="52c40-176">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="52c40-177">Exporte os resultados da mensagem </span><span class="sxs-lookup"><span data-stu-id="52c40-177">Export message results</span></span>

1. <span data-ttu-id="52c40-178">Selecione as mensagens que você está interessado e clique em **Exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="52c40-178">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="52c40-179">Clique em **Sim** na mensagem de confirmação que avisa para manter a janela do navegador aberta.</span><span class="sxs-lookup"><span data-stu-id="52c40-179">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="52c40-180">Quando a exportação estiver pronta, você poderá nomear e escolher o local de download do arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="52c40-180">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="52c40-181">Exiba detalhes da mensagem em quarentena</span><span class="sxs-lookup"><span data-stu-id="52c40-181">View quarantined message details</span></span>

<span data-ttu-id="52c40-182">Quando você clica em uma mensagem de e-mail na lista, os seguintes detalhes de mensagem são exibidos no painel de submenu **Detalhes**:</span><span class="sxs-lookup"><span data-stu-id="52c40-182">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="52c40-183">**ID da mensagem**: o identificador globalmente exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="52c40-183">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="52c40-184">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="52c40-184">**Sender address**</span></span>

- <span data-ttu-id="52c40-185">**Recebido**: a data e a hora em que a mensagem foi recebida.</span><span class="sxs-lookup"><span data-stu-id="52c40-185">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="52c40-186">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="52c40-186">**Subject**</span></span>

- <span data-ttu-id="52c40-187">**Motivo da quarentena**: mostra se uma mensagem foi identificada como **spam**, **em massa**, **Phish**, corresponde a uma regra de fluxo de emails (**regra de transporte**) ou foi identificada como contendo **malware**.</span><span class="sxs-lookup"><span data-stu-id="52c40-187">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="52c40-188">**Destinatários**: se a mensagem contiver vários destinatários, você precisará clicar em **Visualizar mensagem** ou **Exibir o cabeçalho da mensagem** para visualizar a lista completa dos destinatários.</span><span class="sxs-lookup"><span data-stu-id="52c40-188">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="52c40-189">**Expira**: a data/hora em que a mensagem será excluída de forma automática e permanente da quarentena.</span><span class="sxs-lookup"><span data-stu-id="52c40-189">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="52c40-190">**Liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem foi liberada.</span><span class="sxs-lookup"><span data-stu-id="52c40-190">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="52c40-191">**Sem liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem não foi liberada.</span><span class="sxs-lookup"><span data-stu-id="52c40-191">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="52c40-192">Tomar medidas quanto aos e-mails em quarentena</span><span class="sxs-lookup"><span data-stu-id="52c40-192">Take action on quarantined email</span></span>

<span data-ttu-id="52c40-193">Após selecionar uma mensagem, você tem várias opções para o que fazer com as mensagens no painel de submenu **detalhes** :</span><span class="sxs-lookup"><span data-stu-id="52c40-193">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="52c40-194">**Mensagem de lançamento**: no painel de submenus exibido, escolha as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="52c40-194">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="52c40-195">**Relatar mensagens à Microsoft para análise**: isso é selecionado por padrão e relata a mensagem em quarentena errada à Microsoft como um falso positivo.</span><span class="sxs-lookup"><span data-stu-id="52c40-195">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="52c40-196">Se a mensagem foi colocada em quarentena como spam, em massa, phishing ou com malware, a mensagem também é relatada para a equipe de análise de spam da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="52c40-196">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="52c40-197">Dependendo da análise, as regras de filtro de spam de todo o serviço podem ser ajustadas para permitir a mensagem.</span><span class="sxs-lookup"><span data-stu-id="52c40-197">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="52c40-198">Escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="52c40-198">Choose one of the following options:</span></span>

    - <span data-ttu-id="52c40-199">**Liberar mensagens para todos os destinatários**</span><span class="sxs-lookup"><span data-stu-id="52c40-199">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="52c40-200">**Liberar mensagens para destinatários específicos**</span><span class="sxs-lookup"><span data-stu-id="52c40-200">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="52c40-201">**Liberar mensagens para outras pessoas**</span><span class="sxs-lookup"><span data-stu-id="52c40-201">**Release messages to other people**</span></span>

  <span data-ttu-id="52c40-202">Quando terminar, clique em **Liberar mensagens**.</span><span class="sxs-lookup"><span data-stu-id="52c40-202">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="52c40-203">Observações sobre o lançamento de mensagens:</span><span class="sxs-lookup"><span data-stu-id="52c40-203">Notes about releasing messages:</span></span>

  - <span data-ttu-id="52c40-204">Você não pode liberar uma mensagem para o mesmo destinatário mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="52c40-204">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="52c40-205">Somente os destinatários que não receberam a mensagem aparecerão na lista de possíveis destinatários.</span><span class="sxs-lookup"><span data-stu-id="52c40-205">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="52c40-206">**Exibir cabeçalho da mensagem**: escolha este link para visualizar o texto do cabeçalho da mensagem.</span><span class="sxs-lookup"><span data-stu-id="52c40-206">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="52c40-207">Para analisar os valores e campos de cabeçalho em detalhes, copie o texto do cabeçalho da mensagem para a área de transferência e, em seguida, escolha **Analisador de Cabeçalhos de Mensagens da Microsoft** para acessar o Analisar de Conectividade Remota (clique com o botão direito e escolha **Abrir em uma nova guia** se não quiser deixar o Microsoft 365 para concluir essa tarefa).</span><span class="sxs-lookup"><span data-stu-id="52c40-207">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="52c40-208">Cole o cabeçalho da mensagem na página na seção Analisador do cabeçalho da mensagem e escolha **Analisar cabeçalhos**:</span><span class="sxs-lookup"><span data-stu-id="52c40-208">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="52c40-209">**Visualizar mensagem**: no painel de submenu que é exibido, escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="52c40-209">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="52c40-210">**Visualização da fonte**: mostra a versão HTML do corpo da mensagem com todos os links desabilitados.</span><span class="sxs-lookup"><span data-stu-id="52c40-210">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="52c40-211">**Visualização do texto**: mostra o corpo da mensagem em texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="52c40-211">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="52c40-212">**Remover da quarentena**: depois de clicar em **Sim** no aviso exibido, a mensagem será excluída imediatamente sem ser enviada aos destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="52c40-212">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="52c40-213">**Mensagem de download**: no painel de submenu que é exibido, clique em **Compreendo os riscos de baixar esta mensagem** para salvar uma cópia local da mensagem no formato .eml.</span><span class="sxs-lookup"><span data-stu-id="52c40-213">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="52c40-214">**Enviar mensagem**: no painel de submenu que aparece, escolha as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="52c40-214">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="52c40-215">**Tipo de objeto**: **email** (padrão), **URL**ou **anexo**.</span><span class="sxs-lookup"><span data-stu-id="52c40-215">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="52c40-216">**Formato de envio**: **ID de mensagem de rede** (padrão, com o valor correspondente na caixa ID de mensagem de **rede** ) ou **arquivo** (navegue até um arquivo. eml ou. msg local).</span><span class="sxs-lookup"><span data-stu-id="52c40-216">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="52c40-217">Observe que, se você selecionar **arquivo** e, em seguida, selecionar **ID de mensagem de rede**, o valor inicialmente será desperdido.</span><span class="sxs-lookup"><span data-stu-id="52c40-217">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="52c40-218">**Destinatários**: digite no leasing um destinatário original da mensagem ou clique em **selecionar tudo** para identificar todos os destinatários.</span><span class="sxs-lookup"><span data-stu-id="52c40-218">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="52c40-219">Você também pode clicar em **selecionar todos** e, em seguida, remover seletivamente destinatários individuais.</span><span class="sxs-lookup"><span data-stu-id="52c40-219">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="52c40-220">**Motivo do envio**: **não deve ter sido bloqueado** (padrão) ou **deve ter sido bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="52c40-220">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="52c40-221">Quando tiver concluído, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="52c40-221">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="52c40-222">Se você não liberar ou remover a mensagem, ela será excluída após o término do período de retenção da quarentena padrão.</span><span class="sxs-lookup"><span data-stu-id="52c40-222">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="52c40-223">Tome medidas em várias mensagens quanto aos e-mails em quarentena</span><span class="sxs-lookup"><span data-stu-id="52c40-223">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="52c40-224">Quando você seleciona várias mensagens que estão em quarentena na lista (até 100), o painel de submenu **Ações em massa** é exibido em que você pode realizar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="52c40-224">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="52c40-225">**Mensagens de lançamento**: as opções são as mesmas de quando você libera uma única mensagem, mas não é possível clicar em **Liberar mensagens para destinatários específicos**; você só pode clicar em **Mensagem de lançamento a todos os destinatários** ou **Liberar mensagens para outras pessoas**.</span><span class="sxs-lookup"><span data-stu-id="52c40-225">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="52c40-226">Considere o seguinte cenário: john@gmail.com envia uma mensagem para faith@contoso.com e john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="52c40-226">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="52c40-227">O Gmail bifurcates esta mensagem em duas cópias que são direcionadas para quarentena como phishing no Microsoft.</span><span class="sxs-lookup"><span data-stu-id="52c40-227">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="52c40-228">Um administrador libera essas duas mensagens para o admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="52c40-228">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="52c40-229">A primeira mensagem liberada que alcança a caixa de correio de administrador é entregue.</span><span class="sxs-lookup"><span data-stu-id="52c40-229">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="52c40-230">A segunda mensagem liberada é identificada como entrega duplicada e é ignorada.</span><span class="sxs-lookup"><span data-stu-id="52c40-230">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="52c40-231">A mensagem será identificada como duplicatas se elas tiverem a mesma ID de mensagem e o tempo de recebimento.</span><span class="sxs-lookup"><span data-stu-id="52c40-231">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="52c40-232">**Excluir mensagens**: depois de clicar em **Sim** no aviso que é exibido, a mensagem é imediatamente excluída sem ser enviada aos destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="52c40-232">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="52c40-233">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="52c40-233">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="52c40-234">Somente ATP: usar o centro de conformidade de & de segurança para gerenciar arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="52c40-234">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="52c40-235">Os procedimentos para arquivos em quarentena nesta seção estão disponíveis somente para assinantes do plano ATP 1 e do plano 2.</span><span class="sxs-lookup"><span data-stu-id="52c40-235">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="52c40-236">Em organizações com ATP, os administradores podem gerenciar arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="52c40-236">In organizations with ATP, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="52c40-237">Exibir arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="52c40-237">View quarantined files</span></span>

1. <span data-ttu-id="52c40-238">No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.</span><span class="sxs-lookup"><span data-stu-id="52c40-238">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="52c40-239">Altere o **modo de exibição colocado em quarentena** para os **arquivos**de valor padrão.</span><span class="sxs-lookup"><span data-stu-id="52c40-239">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="52c40-240">Você pode classificar em um campo clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="52c40-240">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="52c40-241">Você pode classificar os resultados clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="52c40-241">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="52c40-242">Clique em **Modificar colunas** para exibir um máximo de sete colunas.</span><span class="sxs-lookup"><span data-stu-id="52c40-242">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="52c40-243">As colunas padrão são marcadas com um asterisco ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="52c40-243">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="52c40-244">**Usuário**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52c40-244">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="52c40-245">**Alocações**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52c40-245">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="52c40-246">**Nome do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52c40-246">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="52c40-247">**URL do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52c40-247">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="52c40-248">**Tamanho do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52c40-248">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="52c40-249">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52c40-249">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="52c40-250">**Lançado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="52c40-250">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="52c40-251">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="52c40-251">**Detected by**</span></span>

   - <span data-ttu-id="52c40-252">**Modificado por hora**</span><span class="sxs-lookup"><span data-stu-id="52c40-252">**Modified by time**</span></span>

4. <span data-ttu-id="52c40-253">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="52c40-253">To filter the results, click **Filter**.</span></span> <span data-ttu-id="52c40-254">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="52c40-254">The available filters are:</span></span>

   - <span data-ttu-id="52c40-255">**Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:</span><span class="sxs-lookup"><span data-stu-id="52c40-255">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="52c40-256">**Hoje**</span><span class="sxs-lookup"><span data-stu-id="52c40-256">**Today**</span></span>

     - <span data-ttu-id="52c40-257">**Próximos 2 dias**</span><span class="sxs-lookup"><span data-stu-id="52c40-257">**Next 2 days**</span></span>

     - <span data-ttu-id="52c40-258">**Próximas 7 semanas**</span><span class="sxs-lookup"><span data-stu-id="52c40-258">**Next 7 days**</span></span>

     - <span data-ttu-id="52c40-259">Um intervalo personalizado de data/hora.</span><span class="sxs-lookup"><span data-stu-id="52c40-259">A custom date/time range.</span></span>

   - <span data-ttu-id="52c40-260">**Hora de recebimento**</span><span class="sxs-lookup"><span data-stu-id="52c40-260">**Received time**</span></span>

   - <span data-ttu-id="52c40-261">**Motivo da quarentena**: o único valor disponível é **malware**.</span><span class="sxs-lookup"><span data-stu-id="52c40-261">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="52c40-262">Depois de encontrar um arquivo em quarentena específico, selecione o arquivo para exibir os detalhes sobre ele e execute a ação nele (por exemplo, exibir, liberar, baixar ou excluir a mensagem).</span><span class="sxs-lookup"><span data-stu-id="52c40-262">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="52c40-263">Exportar resultados de arquivo</span><span class="sxs-lookup"><span data-stu-id="52c40-263">Export file results</span></span>

1. <span data-ttu-id="52c40-264">Selecione os arquivos nos quais você está interessado e clique em **Exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="52c40-264">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="52c40-265">Clique em **Sim** na mensagem de confirmação que avisa para manter a janela do navegador aberta.</span><span class="sxs-lookup"><span data-stu-id="52c40-265">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="52c40-266">Quando a exportação estiver pronta, você poderá nomear e escolher o local de download do arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="52c40-266">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="52c40-267">Exibir detalhes de arquivo em quarentena</span><span class="sxs-lookup"><span data-stu-id="52c40-267">View quarantined file details</span></span>

<span data-ttu-id="52c40-268">Quando você seleciona um arquivo na lista, os seguintes detalhes de arquivo são exibidos no painel de submenu **detalhes** :</span><span class="sxs-lookup"><span data-stu-id="52c40-268">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="52c40-269">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="52c40-269">**File Name**</span></span>

- <span data-ttu-id="52c40-270">**URL do arquivo**: URL que define o local do arquivo (por exemplo, no SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="52c40-270">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="52c40-271">**Conteúdo mal-intencionado detectado em** A data/hora em que o arquivo foi colocado em quarentena.</span><span class="sxs-lookup"><span data-stu-id="52c40-271">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="52c40-272">**Expira**: a data em que o arquivo será excluído da quarentena.</span><span class="sxs-lookup"><span data-stu-id="52c40-272">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="52c40-273">**Detectado por**: ATP (proteção avançada contra ameaças) ou mecanismo antimalware da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="52c40-273">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="52c40-274">**Lançado?**</span><span class="sxs-lookup"><span data-stu-id="52c40-274">**Released?**</span></span>

- <span data-ttu-id="52c40-275">**Nome do malware**</span><span class="sxs-lookup"><span data-stu-id="52c40-275">**Malware Name**</span></span>

- <span data-ttu-id="52c40-276">**ID do documento**: um identificador exclusivo para o documento.</span><span class="sxs-lookup"><span data-stu-id="52c40-276">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="52c40-277">**Tamanho do arquivo**: em kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="52c40-277">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="52c40-278">**Organização** A ID exclusiva da sua organização.</span><span class="sxs-lookup"><span data-stu-id="52c40-278">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="52c40-279">**Última modificação**</span><span class="sxs-lookup"><span data-stu-id="52c40-279">**Last modified**</span></span>

- <span data-ttu-id="52c40-280">**Modificado por**: o usuário que modificou o arquivo pela última vez.</span><span class="sxs-lookup"><span data-stu-id="52c40-280">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="52c40-281">**Algoritmo de hash seguro 256 bits (SHA-256) valor**: você pode usar esse valor de hash para identificar o arquivo em outros repositórios de reputação ou em outros locais em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="52c40-281">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="52c40-282">Executar ação em arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="52c40-282">Take action on quarantined files</span></span>

<span data-ttu-id="52c40-283">Ao selecionar um arquivo na lista, você pode executar as seguintes ações no arquivo no painel de submenu **detalhes** :</span><span class="sxs-lookup"><span data-stu-id="52c40-283">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="52c40-284">**Arquivos de lançamento**: selecione (padrão) ou desmarque **arquivos de relatório para a Microsoft para análise**e clique em **liberar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="52c40-284">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="52c40-285">**Baixar o arquivo**</span><span class="sxs-lookup"><span data-stu-id="52c40-285">**Download file**</span></span>

- <span data-ttu-id="52c40-286">**Remover arquivo da quarentena**</span><span class="sxs-lookup"><span data-stu-id="52c40-286">**Remove file from quarantine**</span></span>

<span data-ttu-id="52c40-287">Se você não liberar ou remover os arquivos, eles serão excluídos depois que o período de retenção de quarentena padrão expirar.</span><span class="sxs-lookup"><span data-stu-id="52c40-287">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="52c40-288">Ações em vários arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="52c40-288">Actions on multiple quarantined files</span></span>

<span data-ttu-id="52c40-289">Quando você seleciona vários arquivos em quarentena na lista (até 100), o painel de submenu **ações em massa** aparece onde você pode executar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="52c40-289">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="52c40-290">**Arquivos de versão**</span><span class="sxs-lookup"><span data-stu-id="52c40-290">**Release files**</span></span>

- <span data-ttu-id="52c40-291">**Excluir arquivos**: depois de clicar em **Sim** no aviso exibido, os arquivos serão excluídos imediatamente.</span><span class="sxs-lookup"><span data-stu-id="52c40-291">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="52c40-292">Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global (ou funções apropriadas de segurança & central de conformidade) em sua organização, entre e [vá para o centro de conformidade de & de segurança](../../compliance/go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="52c40-292">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="52c40-293">Usar o PowerShell do Exchange Online ou do EOP PowerShell para exibir e gerenciar mensagens em quarentena e arquivos</span><span class="sxs-lookup"><span data-stu-id="52c40-293">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="52c40-294">Os cmdlets que você usa para exibir e gerenciar mensagens e arquivos em quarentena são:</span><span class="sxs-lookup"><span data-stu-id="52c40-294">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="52c40-295">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="52c40-295">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="52c40-296">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="52c40-296">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="52c40-297">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="52c40-297">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="52c40-298">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Observe que este cmdlet é somente para mensagens, e não para arquivos de malware de ATP para SharePoint Online, onedrive for Business ou Teams.</span><span class="sxs-lookup"><span data-stu-id="52c40-298">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="52c40-299">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="52c40-299">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
