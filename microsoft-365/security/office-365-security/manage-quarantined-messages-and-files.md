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
ms.openlocfilehash: fed05ee202e4352200a80516e0ec1b62c8421178
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357128"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a><span data-ttu-id="a82ae-104">Gerenciar arquivos e mensagens em quarentena como administrador no EOP</span><span class="sxs-lookup"><span data-stu-id="a82ae-104">Manage quarantined messages and files as an admin in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a82ae-105">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena retém mensagens potencialmente perigosas ou indesejadas.</span><span class="sxs-lookup"><span data-stu-id="a82ae-105">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="a82ae-106">Para obter mais informações, consulte [mensagens de email em quarentena no EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="a82ae-106">For more information, see [Quarantined email messages in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="a82ae-107">Os administradores podem exibir, liberar e excluir todos os tipos de mensagens em quarentena para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="a82ae-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="a82ae-108">Somente os administradores podem gerenciar mensagens que foram colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="a82ae-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="a82ae-109">Os administradores também podem relatar falsos positivos para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a82ae-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="a82ae-110">Os administradores nas organizações com o Microsoft defender para Office 365 também podem exibir, baixar e excluir arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a82ae-110">Admins in organizations with Microsoft Defender for Office 365 can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="a82ae-111">Você exibir e gerenciar mensagens em quarentena no centro de conformidade e segurança & ou no PowerShell (PowerShell do Exchange Online para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="a82ae-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a82ae-112">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="a82ae-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a82ae-113">Para abrir o Centro de Conformidade e Segurança, acesse <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="a82ae-113">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="a82ae-114">Para abrir a página Quarentena imediatamente, vá para <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="a82ae-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="a82ae-115">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a82ae-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a82ae-116">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="a82ae-116">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a82ae-117">Você precisa receber permissões antes de gerenciar a quarentena como um administrador. As permissões são controladas pela função de **quarentena** no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="a82ae-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="a82ae-118">Por padrão, essa função é atribuída aos grupos de função **Gerenciamento da organização** (administradores globais), **administrador de quarentena** e administrador de **segurança** no centro de conformidade do & de segurança.</span><span class="sxs-lookup"><span data-stu-id="a82ae-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="a82ae-119">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a82ae-119">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="a82ae-120">As mensagens em quarentena são mantidas por um período de tempo padrão antes de serem excluídas automaticamente:</span><span class="sxs-lookup"><span data-stu-id="a82ae-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="a82ae-121">30 dias para mensagens em quarentena por políticas antispam (spam, phishing e email em massa).</span><span class="sxs-lookup"><span data-stu-id="a82ae-121">30 days for messages quarantined by anti-spam policies (spam, phishing, and bulk email).</span></span> <span data-ttu-id="a82ae-122">Este é o valor padrão e máximo.</span><span class="sxs-lookup"><span data-stu-id="a82ae-122">This is the default and maximum value.</span></span> <span data-ttu-id="a82ae-123">Para configurar (reduzir) esse valor, consulte [Configure anti-spam Policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a82ae-123">To configure (lower) this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="a82ae-124">15 dias para mensagens que contenham malware.</span><span class="sxs-lookup"><span data-stu-id="a82ae-124">15 days for messages that contain malware.</span></span>

  - <span data-ttu-id="a82ae-125">15 dias para arquivos colocados em quarentena pela ATP para SharePoint, OneDrive e Microsoft Teams no defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="a82ae-125">15 days for files quarantined by ATP for SharePoint, OneDrive, and Microsoft Teams in Defender for Office 365.</span></span>

  <span data-ttu-id="a82ae-126">Quando uma mensagem expira da quarentena, não é possível recuperá-la.</span><span class="sxs-lookup"><span data-stu-id="a82ae-126">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="a82ae-127">Usar o centro de conformidade de & de segurança para gerenciar mensagens de email em quarentena</span><span class="sxs-lookup"><span data-stu-id="a82ae-127">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="a82ae-128">Exibir email em quarentena</span><span class="sxs-lookup"><span data-stu-id="a82ae-128">View quarantined email</span></span>

1. <span data-ttu-id="a82ae-129">No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-129">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="a82ae-130">Verifique se a **exibição em quarentena** está definida com o valor padrão **email**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-130">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="a82ae-131">Você pode classificar os resultados clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="a82ae-131">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="a82ae-132">Clique em **Modificar colunas** para exibir um máximo de sete colunas.</span><span class="sxs-lookup"><span data-stu-id="a82ae-132">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="a82ae-133">Os valores padrão são marcados com um asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="a82ae-133">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="a82ae-134">**Recebido**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a82ae-134">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="a82ae-135">**Remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a82ae-135">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="a82ae-136">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a82ae-136">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="a82ae-137">**Motivo da quarentena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a82ae-137">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="a82ae-138">**Lançado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a82ae-138">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="a82ae-139">**Tipo de política**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a82ae-139">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="a82ae-140">**Expires**</span><span class="sxs-lookup"><span data-stu-id="a82ae-140">**Expires**</span></span>
   - <span data-ttu-id="a82ae-141">**Recipiente**</span><span class="sxs-lookup"><span data-stu-id="a82ae-141">**Recipient**</span></span>
   - <span data-ttu-id="a82ae-142">**ID da mensagem**</span><span class="sxs-lookup"><span data-stu-id="a82ae-142">**Message ID**</span></span>
   - <span data-ttu-id="a82ae-143">**Nome da política**</span><span class="sxs-lookup"><span data-stu-id="a82ae-143">**Policy name**</span></span>
   - <span data-ttu-id="a82ae-144">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="a82ae-144">**Size**</span></span>
   - <span data-ttu-id="a82ae-145">**Direção**</span><span class="sxs-lookup"><span data-stu-id="a82ae-145">**Direction**</span></span>

   <span data-ttu-id="a82ae-146">Quando você terminar, clique em **Salvar**, ou clique em **Definido como padrão**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-146">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="a82ae-147">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-147">To filter the results, click **Filter**.</span></span> <span data-ttu-id="a82ae-148">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="a82ae-148">The available filters are:</span></span>

   - <span data-ttu-id="a82ae-149">**Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:</span><span class="sxs-lookup"><span data-stu-id="a82ae-149">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="a82ae-150">**Hoje**</span><span class="sxs-lookup"><span data-stu-id="a82ae-150">**Today**</span></span>
     - <span data-ttu-id="a82ae-151">**Próximos 2 dias**</span><span class="sxs-lookup"><span data-stu-id="a82ae-151">**Next 2 days**</span></span>
     - <span data-ttu-id="a82ae-152">**Próximas 7 semanas**</span><span class="sxs-lookup"><span data-stu-id="a82ae-152">**Next 7 days**</span></span>
     - <span data-ttu-id="a82ae-153">**Personalizado**: Insira uma **Data de início** e uma **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-153">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="a82ae-154">**Hora recebida**: Insira uma **Data de início** e uma **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-154">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="a82ae-155">**Motivo da quarentena**:</span><span class="sxs-lookup"><span data-stu-id="a82ae-155">**Quarantine reason**:</span></span>
     - <span data-ttu-id="a82ae-156">**Política**: a mensagem correspondeu às condições de uma regra de fluxo de emails (também conhecida como regra de transporte).</span><span class="sxs-lookup"><span data-stu-id="a82ae-156">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>
     - <span data-ttu-id="a82ae-157">**Em massa**</span><span class="sxs-lookup"><span data-stu-id="a82ae-157">**Bulk**</span></span>
     - <span data-ttu-id="a82ae-158">**Phish**: o filtro de spam veredicto foi um **email de phishing** ou proteção contra phishing colocou em quarentena a mensagem ([configurações de spoof](set-up-anti-phishing-policies.md#spoof-settings) ou [proteção de personificação](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span><span class="sxs-lookup"><span data-stu-id="a82ae-158">**Phish**: The spam filter verdict was **Phishing email** or anti-phishing protection quarantined the message ([spoof settings](set-up-anti-phishing-policies.md#spoof-settings) or [impersonation protection](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).</span></span>
     - <span data-ttu-id="a82ae-159">**Malware**</span><span class="sxs-lookup"><span data-stu-id="a82ae-159">**Malware**</span></span>
     - <span data-ttu-id="a82ae-160">**Spam**</span><span class="sxs-lookup"><span data-stu-id="a82ae-160">**Spam**</span></span>
     - <span data-ttu-id="a82ae-161">**Phishing de alta confiança**</span><span class="sxs-lookup"><span data-stu-id="a82ae-161">**High Confidence Phish**</span></span>

   - <span data-ttu-id="a82ae-162">**Tipo de Política**: Filtre mensagens por tipo de política:</span><span class="sxs-lookup"><span data-stu-id="a82ae-162">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="a82ae-163">**Política Antimalware**</span><span class="sxs-lookup"><span data-stu-id="a82ae-163">**Anti-malware policy**</span></span>
     - <span data-ttu-id="a82ae-164">**Política de anexos seguros**</span><span class="sxs-lookup"><span data-stu-id="a82ae-164">**Safe Attachments policy**</span></span>
     - <span data-ttu-id="a82ae-165">**Política Anti-phish**:</span><span class="sxs-lookup"><span data-stu-id="a82ae-165">**Anti-phish policy**</span></span>
     - <span data-ttu-id="a82ae-166">**Política de filtro de conteúdo hospedado** (política antispam)</span><span class="sxs-lookup"><span data-stu-id="a82ae-166">**Hosted content filter policy** (anti-spam policy)</span></span>
     - <span data-ttu-id="a82ae-167">**Regra de transporte**</span><span class="sxs-lookup"><span data-stu-id="a82ae-167">**Transport rule**</span></span>

   - <span data-ttu-id="a82ae-168">**Destinatário do email**: todos os usuários ou apenas as mensagens enviadas a você.</span><span class="sxs-lookup"><span data-stu-id="a82ae-168">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="a82ae-169">Os usuários finais só podem gerenciar mensagens em quarentena enviadas para eles.</span><span class="sxs-lookup"><span data-stu-id="a82ae-169">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="a82ae-170">Para limpar o filtro, clique em **Limpar**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-170">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="a82ae-171">Para ocultar o submenu do filtro, clique novamente em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-171">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="a82ae-172">Use **Classificar resultados por** (o botão **ID da mensagem** por padrão) e um valor correspondente para localizar mensagens específicas.</span><span class="sxs-lookup"><span data-stu-id="a82ae-172">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="a82ae-173">Os curingas não possuem suporte.</span><span class="sxs-lookup"><span data-stu-id="a82ae-173">Wildcards aren't supported.</span></span> <span data-ttu-id="a82ae-174">Você pode pesquisar pelos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="a82ae-174">You can search by the following values:</span></span>

   - <span data-ttu-id="a82ae-175">**ID da mensagem**: o identificador globalmente exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="a82ae-175">**Message ID**: The globally unique identifier of the message.</span></span>

     <span data-ttu-id="a82ae-176">Por exemplo, você usou o [rastreamento de mensagens](message-trace-scc.md) para procurar uma mensagem que foi enviada a um usuário na sua organização, e você determina que a mensagem foi colocada em quarentena em vez de distribuída.</span><span class="sxs-lookup"><span data-stu-id="a82ae-176">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="a82ae-177">Certifique-se de incluir o valor completo da ID da mensagem, que pode incluir colchetes angulares ( \<\> ).</span><span class="sxs-lookup"><span data-stu-id="a82ae-177">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="a82ae-178">Por exemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="a82ae-178">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="a82ae-179">**Endereço de e-mail do remetente**: o endereço de e-mail de um único remetente.</span><span class="sxs-lookup"><span data-stu-id="a82ae-179">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="a82ae-180">**Nome da política**: Use o nome completo da política da mensagem.</span><span class="sxs-lookup"><span data-stu-id="a82ae-180">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="a82ae-181">A pesquisa não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a82ae-181">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="a82ae-182">**Endereço de e-mail do destinatário**: o endereço de e-mail de um único destinatário.</span><span class="sxs-lookup"><span data-stu-id="a82ae-182">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="a82ae-183">**Assunto**: use todo o assunto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="a82ae-183">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="a82ae-184">A pesquisa não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a82ae-184">The search is not case-sensitive.</span></span>
  
   - <span data-ttu-id="a82ae-185">**Nome da política**: o nome da política responsável por colocar a mensagem em quarentena.</span><span class="sxs-lookup"><span data-stu-id="a82ae-185">**Policy name**: The name of the policy that was responsible for quarantining the message.</span></span>

   <span data-ttu-id="a82ae-186">Depois de ter inserido os critérios da pesquisa, clique em ![Atualizar botão](../../media/scc-quarantine-refresh.png) **Atualizar** para filtrar os resultados.</span><span class="sxs-lookup"><span data-stu-id="a82ae-186">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="a82ae-187">Depois de encontrar uma mensagem específica em quarentena, selecione a mensagem para exibir detalhes sobre ela e execute uma ação (por exemplo: exibir, liberar, fazer download ou excluir a mensagem).</span><span class="sxs-lookup"><span data-stu-id="a82ae-187">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="a82ae-188">Exiba detalhes da mensagem em quarentena</span><span class="sxs-lookup"><span data-stu-id="a82ae-188">View quarantined message details</span></span>

<span data-ttu-id="a82ae-189">Quando você clica em uma mensagem de e-mail na lista, os seguintes detalhes de mensagem são exibidos no painel de submenu **Detalhes**:</span><span class="sxs-lookup"><span data-stu-id="a82ae-189">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="a82ae-190">**ID da mensagem**: o identificador globalmente exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="a82ae-190">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="a82ae-191">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-191">**Sender address**</span></span>

- <span data-ttu-id="a82ae-192">**Recebido**: a data e a hora em que a mensagem foi recebida.</span><span class="sxs-lookup"><span data-stu-id="a82ae-192">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="a82ae-193">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="a82ae-193">**Subject**</span></span>

- <span data-ttu-id="a82ae-194">**Motivo da quarentena**: mostra se uma mensagem foi identificada como **spam**, **em massa**, **Phish**, corresponde a uma regra de fluxo de emails (**regra de transporte**) ou foi identificada como contendo **malware**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-194">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="a82ae-195">**Contagem de destinatários**</span><span class="sxs-lookup"><span data-stu-id="a82ae-195">**Recipient count**</span></span>

- <span data-ttu-id="a82ae-196">**Destinatários**: se a mensagem contiver vários destinatários, você precisará clicar em **Visualizar mensagem** ou **Exibir o cabeçalho da mensagem** para visualizar a lista completa dos destinatários.</span><span class="sxs-lookup"><span data-stu-id="a82ae-196">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="a82ae-197">**Expira**: a data/hora em que a mensagem será excluída de forma automática e permanente da quarentena.</span><span class="sxs-lookup"><span data-stu-id="a82ae-197">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="a82ae-198">**Liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem foi liberada.</span><span class="sxs-lookup"><span data-stu-id="a82ae-198">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="a82ae-199">**Sem liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem não foi liberada.</span><span class="sxs-lookup"><span data-stu-id="a82ae-199">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="a82ae-200">Tomar medidas quanto aos e-mails em quarentena</span><span class="sxs-lookup"><span data-stu-id="a82ae-200">Take action on quarantined email</span></span>

<span data-ttu-id="a82ae-201">Após selecionar uma mensagem, você tem várias opções para o que fazer com as mensagens no painel de submenu **detalhes** :</span><span class="sxs-lookup"><span data-stu-id="a82ae-201">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="a82ae-202">**Mensagem de lançamento**: no painel de submenus exibido, escolha as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="a82ae-202">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="a82ae-203">**Relatar mensagens à Microsoft para análise**: isso é selecionado por padrão e relata a mensagem em quarentena errada à Microsoft como um falso positivo.</span><span class="sxs-lookup"><span data-stu-id="a82ae-203">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="a82ae-204">Se a mensagem foi colocada em quarentena como spam, em massa, phishing ou com malware, a mensagem também é relatada para a equipe de análise de spam da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a82ae-204">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="a82ae-205">Dependendo da análise, as regras de filtro de spam de todo o serviço podem ser ajustadas para permitir a mensagem.</span><span class="sxs-lookup"><span data-stu-id="a82ae-205">Depending on their analysis, the service-wide spam filter rules might be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="a82ae-206">Escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="a82ae-206">Choose one of the following options:</span></span>
    - <span data-ttu-id="a82ae-207">**Liberar mensagens para todos os destinatários**</span><span class="sxs-lookup"><span data-stu-id="a82ae-207">**Release messages to all recipients**</span></span>
    - <span data-ttu-id="a82ae-208">**Liberar mensagens para destinatários específicos**</span><span class="sxs-lookup"><span data-stu-id="a82ae-208">**Release messages to specific recipients**</span></span>
    - <span data-ttu-id="a82ae-209">**Liberar mensagens para outras pessoas**: Observe que não há suporte para a liberação de mensagens de malware para pessoas que não sejam destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="a82ae-209">**Release messages to other people**: Note that releasing malware messages to people other than original recipients is not supported.</span></span> 

  <span data-ttu-id="a82ae-210">Quando terminar, clique em **Liberar mensagens**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-210">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="a82ae-211">Observações sobre o lançamento de mensagens:</span><span class="sxs-lookup"><span data-stu-id="a82ae-211">Notes about releasing messages:</span></span>

  - <span data-ttu-id="a82ae-212">Você não pode liberar uma mensagem para o mesmo destinatário mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="a82ae-212">You can't release a message to the same recipient more than once.</span></span>
  - <span data-ttu-id="a82ae-213">Somente os destinatários que não receberam a mensagem aparecerão na lista de possíveis destinatários.</span><span class="sxs-lookup"><span data-stu-id="a82ae-213">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="a82ae-214">**Exibir cabeçalho da mensagem**: escolha este link para visualizar o texto do cabeçalho da mensagem.</span><span class="sxs-lookup"><span data-stu-id="a82ae-214">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="a82ae-215">Para analisar os valores e campos de cabeçalho em detalhes, copie o texto do cabeçalho da mensagem para a área de transferência e, em seguida, escolha **Analisador de Cabeçalhos de Mensagens da Microsoft** para acessar o Analisar de Conectividade Remota (clique com o botão direito e escolha **Abrir em uma nova guia** se não quiser deixar o Microsoft 365 para concluir essa tarefa).</span><span class="sxs-lookup"><span data-stu-id="a82ae-215">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="a82ae-216">Cole o cabeçalho da mensagem na página na seção Analisador do cabeçalho da mensagem e escolha **Analisar cabeçalhos**:</span><span class="sxs-lookup"><span data-stu-id="a82ae-216">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="a82ae-217">**Visualizar mensagem**: no painel de submenu que é exibido, escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="a82ae-217">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="a82ae-218">**Visualização da fonte**: mostra a versão HTML do corpo da mensagem com todos os links desabilitados.</span><span class="sxs-lookup"><span data-stu-id="a82ae-218">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="a82ae-219">**Visualização do texto**: mostra o corpo da mensagem em texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="a82ae-219">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="a82ae-220">**Remover da quarentena**: depois de clicar em **Sim** no aviso exibido, a mensagem será excluída imediatamente sem ser enviada aos destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="a82ae-220">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="a82ae-221">**Mensagem de download**: no painel de submenu que é exibido, clique em **Compreendo os riscos de baixar esta mensagem** para salvar uma cópia local da mensagem no formato .eml.</span><span class="sxs-lookup"><span data-stu-id="a82ae-221">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="a82ae-222">**Enviar mensagem**: no painel de submenu que aparece, escolha as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="a82ae-222">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="a82ae-223">**Tipo de objeto**: **email** (padrão), **URL** ou **anexo**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-223">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="a82ae-224">**Formato de envio**: **ID de mensagem de rede** (padrão, com o valor correspondente na caixa ID de mensagem de **rede** ) ou **arquivo** (navegue até um arquivo. eml ou. msg local).</span><span class="sxs-lookup"><span data-stu-id="a82ae-224">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="a82ae-225">Observe que, se você selecionar **arquivo** e selecionar **ID de mensagem de rede**, o valor inicial será desperdido.</span><span class="sxs-lookup"><span data-stu-id="a82ae-225">Note that if you select **File** and then select **Network Message ID**, the initial value is gone.</span></span>

  - <span data-ttu-id="a82ae-226">**Destinatários**: digite no leasing um destinatário original da mensagem ou clique em **selecionar tudo** para identificar todos os destinatários.</span><span class="sxs-lookup"><span data-stu-id="a82ae-226">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="a82ae-227">Você também pode clicar em **selecionar todos** e, em seguida, remover seletivamente destinatários individuais.</span><span class="sxs-lookup"><span data-stu-id="a82ae-227">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="a82ae-228">**Motivo do envio**: **não deve ter sido bloqueado** (padrão) ou **deve ter sido bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-228">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="a82ae-229">Quando tiver concluído, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-229">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="a82ae-230">Se você não liberar ou remover a mensagem, ela será excluída após o término do período de retenção da quarentena padrão.</span><span class="sxs-lookup"><span data-stu-id="a82ae-230">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="a82ae-231">Tome medidas em várias mensagens quanto aos e-mails em quarentena</span><span class="sxs-lookup"><span data-stu-id="a82ae-231">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="a82ae-232">Quando você seleciona várias mensagens que estão em quarentena na lista (até 100), o painel de submenu **Ações em massa** é exibido em que você pode realizar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="a82ae-232">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="a82ae-233">**Mensagens de lançamento**: as opções são as mesmas de quando você libera uma única mensagem, mas não é possível clicar em **Liberar mensagens para destinatários específicos**; você só pode clicar em **Mensagem de lançamento a todos os destinatários** ou **Liberar mensagens para outras pessoas**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-233">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="a82ae-234">Considere o seguinte cenário: john@gmail.com envia uma mensagem para faith@contoso.com e john@subsidiary.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a82ae-234">Consider the following scenario: john@gmail.com sends a message to faith@contoso.com and john@subsidiary.contoso.com.</span></span> <span data-ttu-id="a82ae-235">O Gmail bifurcates esta mensagem em duas cópias que são direcionadas para quarentena como phishing no Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a82ae-235">Gmail bifurcates this message into two copies that are both routed to quarantine as phishing in Microsoft.</span></span> <span data-ttu-id="a82ae-236">Um administrador libera essas duas mensagens para o admin@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a82ae-236">An admin releases both of these messages to admin@contoso.com.</span></span> <span data-ttu-id="a82ae-237">A primeira mensagem liberada que alcança a caixa de correio de administrador é entregue.</span><span class="sxs-lookup"><span data-stu-id="a82ae-237">The first released message that reaches the admin mailbox is delivered.</span></span> <span data-ttu-id="a82ae-238">A segunda mensagem liberada é identificada como entrega duplicada e é ignorada.</span><span class="sxs-lookup"><span data-stu-id="a82ae-238">The second released message is identified as duplicate delivery and is skipped.</span></span> <span data-ttu-id="a82ae-239">A mensagem será identificada como duplicatas se elas tiverem a mesma ID de mensagem e o tempo de recebimento.</span><span class="sxs-lookup"><span data-stu-id="a82ae-239">Message are identified as duplicates if they have the same message ID and received time.</span></span>

- <span data-ttu-id="a82ae-240">**Excluir mensagens**: depois de clicar em **Sim** no aviso que aparece, as mensagens são excluídas imediatamente sem serem enviadas aos destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="a82ae-240">**Delete messages**:  After you click **Yes** in the warning that appears, the messages are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="a82ae-241">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-241">When you're finished, click **Close**.</span></span>

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="a82ae-242">Somente Microsoft defender para Office 365: usar o centro de conformidade de & de segurança para gerenciar arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="a82ae-242">Microsoft Defender for Office 365 Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="a82ae-243">Os procedimentos para arquivos em quarentena nesta seção estão disponíveis somente para assinantes do Microsoft defender for Office 365 plano 1 e do plano 2.</span><span class="sxs-lookup"><span data-stu-id="a82ae-243">The procedures for quarantined files in this section are available only to Microsoft Defender for Office 365 Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="a82ae-244">Em organizações com o defender para Office 365, os administradores podem gerenciar arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a82ae-244">In organizations with Defender for Office 365, admins can manage quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span> <span data-ttu-id="a82ae-245">Para habilitar a proteção desses arquivos, confira [Ativar ATP para SharePoint, onedrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span><span class="sxs-lookup"><span data-stu-id="a82ae-245">To enable protection for these files, see [Turn on ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="a82ae-246">Exibir arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="a82ae-246">View quarantined files</span></span>

1. <span data-ttu-id="a82ae-247">No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-247">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="a82ae-248">Altere o **modo de exibição colocado em quarentena** para os **arquivos** de valor.</span><span class="sxs-lookup"><span data-stu-id="a82ae-248">Change **View quarantined** to the value **files**.</span></span> <span data-ttu-id="a82ae-249">Você pode classificar em um campo clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="a82ae-249">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="a82ae-250">Você pode classificar os resultados clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="a82ae-250">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="a82ae-251">Clique em **Modificar colunas** para exibir um máximo de sete colunas.</span><span class="sxs-lookup"><span data-stu-id="a82ae-251">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="a82ae-252">As colunas padrão são marcadas com um asterisco ( <sup>\*</sup> ):</span><span class="sxs-lookup"><span data-stu-id="a82ae-252">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="a82ae-253">**Usuário**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a82ae-253">**User**<sup>\*</sup></span></span>
   - <span data-ttu-id="a82ae-254">**Alocações**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a82ae-254">**Location**<sup>\*</sup></span></span>
   - <span data-ttu-id="a82ae-255">**Nome do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a82ae-255">**File name**<sup>\*</sup></span></span>
   - <span data-ttu-id="a82ae-256">**URL do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a82ae-256">**File URL**<sup>\*</sup></span></span>
   - <span data-ttu-id="a82ae-257">**Tamanho do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a82ae-257">**File Size**<sup>\*</sup></span></span>
   - <span data-ttu-id="a82ae-258">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a82ae-258">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="a82ae-259">**Lançado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="a82ae-259">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="a82ae-260">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="a82ae-260">**Detected by**</span></span>
   - <span data-ttu-id="a82ae-261">**Modificado por hora**</span><span class="sxs-lookup"><span data-stu-id="a82ae-261">**Modified by time**</span></span>

4. <span data-ttu-id="a82ae-262">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-262">To filter the results, click **Filter**.</span></span> <span data-ttu-id="a82ae-263">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="a82ae-263">The available filters are:</span></span>

   - <span data-ttu-id="a82ae-264">**Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:</span><span class="sxs-lookup"><span data-stu-id="a82ae-264">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="a82ae-265">**Hoje**</span><span class="sxs-lookup"><span data-stu-id="a82ae-265">**Today**</span></span>
     - <span data-ttu-id="a82ae-266">**Próximos 2 dias**</span><span class="sxs-lookup"><span data-stu-id="a82ae-266">**Next 2 days**</span></span>
     - <span data-ttu-id="a82ae-267">**Próximas 7 semanas**</span><span class="sxs-lookup"><span data-stu-id="a82ae-267">**Next 7 days**</span></span>
     - <span data-ttu-id="a82ae-268">Um intervalo personalizado de data/hora.</span><span class="sxs-lookup"><span data-stu-id="a82ae-268">A custom date/time range.</span></span>
   - <span data-ttu-id="a82ae-269">**Hora de recebimento**</span><span class="sxs-lookup"><span data-stu-id="a82ae-269">**Received time**</span></span>
   - <span data-ttu-id="a82ae-270">**Motivo da quarentena**: o único valor disponível é **malware**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-270">**Quarantine reason**: The only available value is **Malware**.</span></span>
   - <span data-ttu-id="a82ae-271">**Tipo de política**</span><span class="sxs-lookup"><span data-stu-id="a82ae-271">**Policy type**</span></span>

<span data-ttu-id="a82ae-272">Depois de encontrar um arquivo em quarentena específico, selecione o arquivo para exibir os detalhes sobre ele e execute a ação nele (por exemplo, exibir, liberar, baixar ou excluir a mensagem).</span><span class="sxs-lookup"><span data-stu-id="a82ae-272">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="a82ae-273">Exibir detalhes de arquivo em quarentena</span><span class="sxs-lookup"><span data-stu-id="a82ae-273">View quarantined file details</span></span>

<span data-ttu-id="a82ae-274">Quando você seleciona um arquivo na lista, os seguintes detalhes de arquivo são exibidos no painel de submenu **detalhes** :</span><span class="sxs-lookup"><span data-stu-id="a82ae-274">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="a82ae-275">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="a82ae-275">**File Name**</span></span>
- <span data-ttu-id="a82ae-276">**URL do arquivo**: URL que define o local do arquivo (por exemplo, no SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="a82ae-276">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>
- <span data-ttu-id="a82ae-277">**Conteúdo mal-intencionado detectado em** A data/hora em que o arquivo foi colocado em quarentena.</span><span class="sxs-lookup"><span data-stu-id="a82ae-277">**Malicious content detected on** The date/time the file was quarantined.</span></span>
- <span data-ttu-id="a82ae-278">**Expira**: a data em que o arquivo será excluído da quarentena.</span><span class="sxs-lookup"><span data-stu-id="a82ae-278">**Expires**: The date when the file will be deleted from quarantine.</span></span>
- <span data-ttu-id="a82ae-279">**Detectado por**: defender para Office 365 ou mecanismo antimalware da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a82ae-279">**Detected By**: Defender for Office 365 or Microsoft's anti-malware engine.</span></span>
- <span data-ttu-id="a82ae-280">**Lançado?**</span><span class="sxs-lookup"><span data-stu-id="a82ae-280">**Released?**</span></span>
- <span data-ttu-id="a82ae-281">**Nome do malware**</span><span class="sxs-lookup"><span data-stu-id="a82ae-281">**Malware Name**</span></span>
- <span data-ttu-id="a82ae-282">**ID do documento**: um identificador exclusivo para o documento.</span><span class="sxs-lookup"><span data-stu-id="a82ae-282">**Document ID**: A unique identifier for the document.</span></span>
- <span data-ttu-id="a82ae-283">**Tamanho do arquivo**: em kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="a82ae-283">**File Size**: In kilobytes (KB).</span></span>
- <span data-ttu-id="a82ae-284">**Organização** A ID exclusiva da sua organização.</span><span class="sxs-lookup"><span data-stu-id="a82ae-284">**Organization** Your organization's unique ID.</span></span>
- <span data-ttu-id="a82ae-285">**Última modificação**</span><span class="sxs-lookup"><span data-stu-id="a82ae-285">**Last modified**</span></span>
- <span data-ttu-id="a82ae-286">**Modificado por**: o usuário que modificou o arquivo pela última vez.</span><span class="sxs-lookup"><span data-stu-id="a82ae-286">**Modified By**: The user who last modified the file.</span></span>
- <span data-ttu-id="a82ae-287">**Algoritmo de hash seguro 256 bits (SHA-256) valor**: você pode usar esse valor de hash para identificar o arquivo em outros repositórios de reputação ou em outros locais em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="a82ae-287">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="a82ae-288">Executar ação em arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="a82ae-288">Take action on quarantined files</span></span>

<span data-ttu-id="a82ae-289">Ao selecionar um arquivo na lista, você pode executar as seguintes ações no arquivo no painel de submenu **detalhes** :</span><span class="sxs-lookup"><span data-stu-id="a82ae-289">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="a82ae-290">**Arquivos de lançamento**: selecione (padrão) ou desmarque **arquivos de relatório para a Microsoft para análise** e clique em **liberar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="a82ae-290">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>
- <span data-ttu-id="a82ae-291">**Baixar o arquivo**</span><span class="sxs-lookup"><span data-stu-id="a82ae-291">**Download file**</span></span>
- <span data-ttu-id="a82ae-292">**Remover arquivo da quarentena**</span><span class="sxs-lookup"><span data-stu-id="a82ae-292">**Remove file from quarantine**</span></span>

<span data-ttu-id="a82ae-293">Se você não liberar ou remover os arquivos, eles serão excluídos depois que o período de retenção de quarentena padrão expirar.</span><span class="sxs-lookup"><span data-stu-id="a82ae-293">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="a82ae-294">Ações em vários arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="a82ae-294">Actions on multiple quarantined files</span></span>

<span data-ttu-id="a82ae-295">Quando você seleciona vários arquivos em quarentena na lista (até 100), o painel de submenu **ações em massa** aparece onde você pode executar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="a82ae-295">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="a82ae-296">**Arquivos de versão**</span><span class="sxs-lookup"><span data-stu-id="a82ae-296">**Release files**</span></span>
- <span data-ttu-id="a82ae-297">**Excluir arquivos**: depois de clicar em **Sim** no aviso exibido, os arquivos serão excluídos imediatamente.</span><span class="sxs-lookup"><span data-stu-id="a82ae-297">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="a82ae-298">Usar o PowerShell do Exchange Online ou do EOP PowerShell para exibir e gerenciar mensagens em quarentena e arquivos</span><span class="sxs-lookup"><span data-stu-id="a82ae-298">Use Exchange Online PowerShell or standalone EOP PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="a82ae-299">Os cmdlets que você usa para exibir e gerenciar mensagens e arquivos em quarentena são:</span><span class="sxs-lookup"><span data-stu-id="a82ae-299">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="a82ae-300">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="a82ae-300">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [<span data-ttu-id="a82ae-301">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="a82ae-301">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [<span data-ttu-id="a82ae-302">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="a82ae-302">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- <span data-ttu-id="a82ae-303">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Observe que este cmdlet é somente para mensagens, e não para arquivos de malware de ATP para SharePoint Online, onedrive for Business ou Teams.</span><span class="sxs-lookup"><span data-stu-id="a82ae-303">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="a82ae-304">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="a82ae-304">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
