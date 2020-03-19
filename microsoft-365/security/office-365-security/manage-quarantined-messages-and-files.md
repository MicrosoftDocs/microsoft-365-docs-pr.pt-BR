---
title: Gerenciar arquivos e mensagens em quarentena como um administrador no Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: Os administradores podem exibir, liberar e excluir todos os tipos de mensagens em quarentena para todos os usuários. Somente os administradores podem gerenciar mensagens que foram colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (regras de transporte).
ms.openlocfilehash: fdab820d2ccedaf8e4f51ba71b15d2c807d06dd1
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857066"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a><span data-ttu-id="18197-104">Gerenciar arquivos e mensagens em quarentena como um administrador no Office 365</span><span class="sxs-lookup"><span data-stu-id="18197-104">Manage quarantined messages and files as an admin in Office 365</span></span>

<span data-ttu-id="18197-105">A quarentena contém mensagens potencialmente perigosas ou indesejadas nas organizações do Office 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) independentes sem caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="18197-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="18197-106">Para obter mais informações, consulte [Quarantine in Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="18197-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="18197-107">Os administradores podem exibir, liberar e excluir todos os tipos de mensagens em quarentena para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="18197-107">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="18197-108">Somente os administradores podem gerenciar mensagens que foram colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="18197-108">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="18197-109">Os administradores também podem relatar falsos positivos para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18197-109">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="18197-110">Administradores nas organizações com a proteção avançada contra ameaças do Office 365 (ATP) também podem exibir, baixar e excluir arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="18197-110">Admins in organizations with Office 365 Advance Threat Protection (ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="18197-111">Você exibir e gerenciar mensagens em quarentena no centro de conformidade & segurança ou no PowerShell (PowerShell do Exchange Online para clientes do Office 365; PowerShell de proteção do Exchange Online para clientes autônomos do EOP).</span><span class="sxs-lookup"><span data-stu-id="18197-111">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="18197-112">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="18197-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="18197-113">Para abrir o centro de conformidade & segurança do Office 365, <https://protection.office.com>vá para.</span><span class="sxs-lookup"><span data-stu-id="18197-113">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="18197-114">Para abrir a página de quarentena diretamente, acesse <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="18197-114">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="18197-115">Para se conectar ao Exchange Online PowerShell, confira [Conectar ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="18197-115">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="18197-116">Para se conectar ao PowerShell do Exchange Online Protection, confira [conectar-se ao PowerShell do Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="18197-116">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="18197-117">Você precisa receber permissões antes de gerenciar a quarentena como um administrador. As permissões são controladas pela função de **quarentena** no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="18197-117">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="18197-118">Por padrão, essa função é atribuída aos grupos de função **Gerenciamento da organização** (administradores globais), **administrador de quarentena**e administrador de **segurança** no centro de conformidade do & de segurança.</span><span class="sxs-lookup"><span data-stu-id="18197-118">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="18197-119">Para obter mais informações, consulte [permissões no centro de conformidade & segurança do Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="18197-119">For more information, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="18197-120">As mensagens em quarentena são mantidas por um período de tempo padrão antes de serem excluídas automaticamente:</span><span class="sxs-lookup"><span data-stu-id="18197-120">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="18197-121">Mensagens colocadas em quarentena por políticas antispam (spam, phishing e email em massa): 30 dias.</span><span class="sxs-lookup"><span data-stu-id="18197-121">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="18197-122">Este é o valor padrão e máximo.</span><span class="sxs-lookup"><span data-stu-id="18197-122">This is the default and maximum value.</span></span> <span data-ttu-id="18197-123">Para configurar esse valor, consulte [Configure anti-spam Policies in Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="18197-123">To configure this value, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

  - <span data-ttu-id="18197-124">Mensagens em quarentena por regras de fluxo de email (a ação de regra é **entregar a mensagem para a quarentena hospedada**): 30 dias.</span><span class="sxs-lookup"><span data-stu-id="18197-124">Messages quarantined by mail flow rules (the rule action is **Deliver the message to the hosted quarantine**): 30 days.</span></span> <span data-ttu-id="18197-125">Não é possível alterar esse valor.</span><span class="sxs-lookup"><span data-stu-id="18197-125">You can't change this value.</span></span>

  - <span data-ttu-id="18197-126">Mensagens que contêm malware: 15 dias.</span><span class="sxs-lookup"><span data-stu-id="18197-126">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="18197-127">Quando uma mensagem expira da quarentena, não é possível recuperá-la.</span><span class="sxs-lookup"><span data-stu-id="18197-127">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="18197-128">Usar o centro de conformidade de & de segurança para gerenciar mensagens de email em quarentena</span><span class="sxs-lookup"><span data-stu-id="18197-128">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="18197-129">Exibir email em quarentena</span><span class="sxs-lookup"><span data-stu-id="18197-129">View quarantined email</span></span>

1. <span data-ttu-id="18197-130">No centro de segurança e conformidade, vá para a **quarentena**de **análise** \> de **Gerenciamento** \> de ameaças.</span><span class="sxs-lookup"><span data-stu-id="18197-130">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="18197-131">Verifique se a **exibição em quarentena** está definida com o valor padrão **email**.</span><span class="sxs-lookup"><span data-stu-id="18197-131">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="18197-132">Você pode classificar os resultados clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="18197-132">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="18197-133">Clique em **Modificar colunas** para mostrar um máximo de sete colunas.</span><span class="sxs-lookup"><span data-stu-id="18197-133">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="18197-134">Os valores padrão são marcados com um asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="18197-134">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="18197-135">**Recebido**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18197-135">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="18197-136">**Enviou**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18197-136">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="18197-137">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18197-137">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="18197-138">**Motivo da quarentena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18197-138">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="18197-139">**Solta?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18197-139">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="18197-140">**Tipo de política**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18197-140">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="18197-141">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18197-141">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="18197-142">**Recipient**</span><span class="sxs-lookup"><span data-stu-id="18197-142">**Recipient**</span></span>

   - <span data-ttu-id="18197-143">**ID da mensagem**</span><span class="sxs-lookup"><span data-stu-id="18197-143">**Message ID**</span></span>

   - <span data-ttu-id="18197-144">**Nome da política**</span><span class="sxs-lookup"><span data-stu-id="18197-144">**Policy name**</span></span>

   - <span data-ttu-id="18197-145">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="18197-145">**Size**</span></span>

   - <span data-ttu-id="18197-146">**Direction**</span><span class="sxs-lookup"><span data-stu-id="18197-146">**Direction**</span></span>

   <span data-ttu-id="18197-147">Quando tiver terminado, clique em **salvar**ou em **definir como padrão**.</span><span class="sxs-lookup"><span data-stu-id="18197-147">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="18197-148">Para filtrar os resultados, clique em **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="18197-148">To filter the results, click **Filter**.</span></span> <span data-ttu-id="18197-149">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="18197-149">The available filters are:</span></span>

   - <span data-ttu-id="18197-150">**Tempo expira**: filtrar mensagens por quando elas expirarem da quarentena:</span><span class="sxs-lookup"><span data-stu-id="18197-150">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="18197-151">**Empresas**</span><span class="sxs-lookup"><span data-stu-id="18197-151">**Today**</span></span>

     - <span data-ttu-id="18197-152">**Próximos 2 dias**</span><span class="sxs-lookup"><span data-stu-id="18197-152">**Next 2 days**</span></span>

     - <span data-ttu-id="18197-153">**Próximos 7 dias**</span><span class="sxs-lookup"><span data-stu-id="18197-153">**Next 7 days**</span></span>

     - <span data-ttu-id="18197-154">**Personalizado**: Insira uma **data de início** e uma **data de término**.</span><span class="sxs-lookup"><span data-stu-id="18197-154">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="18197-155">**Hora de recebimento**: Insira uma **data de início** e uma data de **término**.</span><span class="sxs-lookup"><span data-stu-id="18197-155">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="18197-156">**Motivo da quarentena**:</span><span class="sxs-lookup"><span data-stu-id="18197-156">**Quarantine reason**:</span></span>

     - <span data-ttu-id="18197-157">**Política**: a mensagem correspondeu às condições de uma regra de fluxo de emails (também conhecida como regra de transporte).</span><span class="sxs-lookup"><span data-stu-id="18197-157">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="18197-158">**Impresso**</span><span class="sxs-lookup"><span data-stu-id="18197-158">**Bulk**</span></span>

     - <span data-ttu-id="18197-159">**Phish**</span><span class="sxs-lookup"><span data-stu-id="18197-159">**Phish**</span></span>

     - <span data-ttu-id="18197-160">**Malware**</span><span class="sxs-lookup"><span data-stu-id="18197-160">**Malware**</span></span>

     - <span data-ttu-id="18197-161">**Spam**</span><span class="sxs-lookup"><span data-stu-id="18197-161">**Spam**</span></span>

     - <span data-ttu-id="18197-162">**Phishing de alta confiança**</span><span class="sxs-lookup"><span data-stu-id="18197-162">**High Confidence Phish**</span></span>

   - <span data-ttu-id="18197-163">**Destinatário do email**: todos os usuários ou apenas as mensagens enviadas a você.</span><span class="sxs-lookup"><span data-stu-id="18197-163">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="18197-164">Os usuários finais só podem gerenciar mensagens em quarentena enviadas para eles.</span><span class="sxs-lookup"><span data-stu-id="18197-164">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="18197-165">Para limpar o filtro, clique em **limpar**.</span><span class="sxs-lookup"><span data-stu-id="18197-165">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="18197-166">Para ocultar o submenu de filtro, clique em **Filtrar** novamente.</span><span class="sxs-lookup"><span data-stu-id="18197-166">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="18197-167">Use **classificar resultados por** (o botão **ID da mensagem** por padrão) e um valor correspondente para localizar mensagens específicas.</span><span class="sxs-lookup"><span data-stu-id="18197-167">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="18197-168">Não há suporte para curingas.</span><span class="sxs-lookup"><span data-stu-id="18197-168">Wildcards aren't supported.</span></span> <span data-ttu-id="18197-169">Você pode pesquisar pelos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="18197-169">You can search by the following values:</span></span>

   - <span data-ttu-id="18197-170">**ID da mensagem**: o identificador global exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="18197-170">**Message ID**: The globally unique identifier of the message.</span></span>

        <span data-ttu-id="18197-171">Por exemplo, você usou o [rastreamento de mensagens](message-trace-scc.md) para procurar uma mensagem que foi enviada a um usuário na sua organização, e você determina que a mensagem foi colocada em quarentena em vez de distribuída.</span><span class="sxs-lookup"><span data-stu-id="18197-171">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="18197-172">Certifique-se de incluir o valor completo da ID da mensagem, que pode incluir colchetes angulares (\<\>).</span><span class="sxs-lookup"><span data-stu-id="18197-172">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="18197-173">Por exemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="18197-173">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="18197-174">**Endereço de email do remetente**: o endereço de email de um único remetente.</span><span class="sxs-lookup"><span data-stu-id="18197-174">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="18197-175">**Endereço de email do destinatário**: o endereço de email de um único destinatário.</span><span class="sxs-lookup"><span data-stu-id="18197-175">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="18197-176">**Subject**: usar o assunto inteiro da mensagem.</span><span class="sxs-lookup"><span data-stu-id="18197-176">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="18197-177">A pesquisa não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="18197-177">The search is not case-sensitive.</span></span>

   <span data-ttu-id="18197-178">Depois de inserir os critérios de pesquisa, clique ![em atualizar](../media/scc-quarantine-refresh.png) botão **Atualizar** para filtrar os resultados.</span><span class="sxs-lookup"><span data-stu-id="18197-178">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="18197-179">Após localizar uma mensagem em quarentena específica, selecione a mensagem para exibir os detalhes sobre ela e execute a ação sobre ela (por exemplo, exibir, liberar, baixar ou excluir a mensagem).</span><span class="sxs-lookup"><span data-stu-id="18197-179">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="18197-180">Exportar resultados de mensagens</span><span class="sxs-lookup"><span data-stu-id="18197-180">Export message results</span></span>

1. <span data-ttu-id="18197-181">Selecione as mensagens em que você está interessado e clique em **Exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="18197-181">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="18197-182">Clique em **Sim** na mensagem de confirmação que avisa para manter a janela do navegador aberta.</span><span class="sxs-lookup"><span data-stu-id="18197-182">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="18197-183">Quando a exportação estiver pronta, você poderá nomear e escolher o local de download para o arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="18197-183">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="18197-184">Exibir detalhes da mensagem em quarentena</span><span class="sxs-lookup"><span data-stu-id="18197-184">View quarantined message details</span></span>

<span data-ttu-id="18197-185">Quando você seleciona uma mensagem de email na lista, os seguintes detalhes da mensagem aparecem no painel de submenu **detalhes** :</span><span class="sxs-lookup"><span data-stu-id="18197-185">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="18197-186">**ID da mensagem**: o identificador global exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="18197-186">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="18197-187">**Endereço do remetente**</span><span class="sxs-lookup"><span data-stu-id="18197-187">**Sender address**</span></span>

- <span data-ttu-id="18197-188">**Recebido**: a data/hora em que a mensagem foi recebida.</span><span class="sxs-lookup"><span data-stu-id="18197-188">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="18197-189">**Subject**</span><span class="sxs-lookup"><span data-stu-id="18197-189">**Subject**</span></span>

- <span data-ttu-id="18197-190">**Motivo da quarentena**: mostra se uma mensagem foi identificada como **spam**, **em massa**, **Phish**, corresponde a uma regra de fluxo de emails (**regra de transporte**) ou foi identificada como contendo **malware**.</span><span class="sxs-lookup"><span data-stu-id="18197-190">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="18197-191">**Destinatários**: se a mensagem contiver vários destinatários, você precisará clicar em **Visualizar mensagem** ou **exibir cabeçalho da mensagem** para ver a lista completa de destinatários.</span><span class="sxs-lookup"><span data-stu-id="18197-191">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="18197-192">**Expira**: a data/hora em que a mensagem será excluída automaticamente e permanentemente da quarentena.</span><span class="sxs-lookup"><span data-stu-id="18197-192">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="18197-193">**Liberação para**: todos os endereços de email (se houver) para os quais a mensagem foi liberada.</span><span class="sxs-lookup"><span data-stu-id="18197-193">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="18197-194">**Ainda não foi liberado para**: todos os endereços de email (se houver) para os quais a mensagem ainda não foi liberada.</span><span class="sxs-lookup"><span data-stu-id="18197-194">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="18197-195">Executar ação em emails em quarentena</span><span class="sxs-lookup"><span data-stu-id="18197-195">Take action on quarantined email</span></span>

<span data-ttu-id="18197-196">Após selecionar uma mensagem, você tem várias opções para o que fazer com as mensagens no painel de submenu **detalhes** :</span><span class="sxs-lookup"><span data-stu-id="18197-196">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="18197-197">**Mensagem de lançamento**: no painel de submenus exibido, escolha as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="18197-197">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="18197-198">**Relatar mensagens à Microsoft para análise**: isso é selecionado por padrão e relata a mensagem em quarentena errada à Microsoft como um falso positivo.</span><span class="sxs-lookup"><span data-stu-id="18197-198">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="18197-199">Se a mensagem foi colocada em quarentena como spam, em massa, phishing ou com malware, a mensagem também é relatada para a equipe de análise de spam da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18197-199">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="18197-200">Dependendo da análise, as regras de filtro de spam de todo o serviço podem ser ajustadas para permitir a mensagem.</span><span class="sxs-lookup"><span data-stu-id="18197-200">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="18197-201">Escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="18197-201">Choose one of the following options:</span></span>

    - <span data-ttu-id="18197-202">**Liberar mensagens para todos os destinatários**</span><span class="sxs-lookup"><span data-stu-id="18197-202">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="18197-203">**Liberar mensagens para destinatários específicos**</span><span class="sxs-lookup"><span data-stu-id="18197-203">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="18197-204">**Liberar mensagens para outras pessoas**</span><span class="sxs-lookup"><span data-stu-id="18197-204">**Release messages to other people**</span></span>

  <span data-ttu-id="18197-205">Quando tiver concluído, clique em **liberar mensagens**.</span><span class="sxs-lookup"><span data-stu-id="18197-205">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="18197-206">Observações sobre o lançamento de mensagens:</span><span class="sxs-lookup"><span data-stu-id="18197-206">Notes about releasing messages:</span></span>

  - <span data-ttu-id="18197-207">Você não pode liberar uma mensagem para o mesmo destinatário mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="18197-207">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="18197-208">Somente os destinatários que não receberam a mensagem aparecerão na lista de possíveis destinatários.</span><span class="sxs-lookup"><span data-stu-id="18197-208">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="18197-209">**Exibir cabeçalho da mensagem**: escolha este link para ver o texto do cabeçalho da mensagem.</span><span class="sxs-lookup"><span data-stu-id="18197-209">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="18197-210">Para analisar os valores e campos de cabeçalho em profundidade, copie o texto do cabeçalho da mensagem para a área de transferência e escolha **analisador de cabeçalho de mensagem da Microsoft** para ir para o analisador de conectividade remota (clique com o botão direito do mouse e escolha **abrir em uma nova guia** se não quiser deixar o Office 365 para concluir essa tarefa).</span><span class="sxs-lookup"><span data-stu-id="18197-210">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="18197-211">Cole o cabeçalho da mensagem na página na seção analisador de cabeçalho de mensagem e escolha **analisar cabeçalhos**:</span><span class="sxs-lookup"><span data-stu-id="18197-211">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="18197-212">**Mensagem de visualização**: no painel de submenus que aparece, escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="18197-212">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="18197-213">**Modo de exibição Source**: mostra a versão HTML do corpo da mensagem com todos os links desabilitados.</span><span class="sxs-lookup"><span data-stu-id="18197-213">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="18197-214">**Exibição de texto**: mostra o corpo da mensagem em texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="18197-214">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="18197-215">**Remover da quarentena**: depois de clicar em **Sim** no aviso exibido, a mensagem será excluída imediatamente sem ser enviada aos destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="18197-215">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="18197-216">**Mensagem de download**: no painel do submenu que aparece, selecione compreendo **os riscos de baixar esta mensagem** para salvar uma cópia local da mensagem no formato. eml.</span><span class="sxs-lookup"><span data-stu-id="18197-216">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="18197-217">**Enviar mensagem**: no painel de submenu que aparece, escolha as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="18197-217">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="18197-218">**Tipo de objeto**: **email** (padrão), **URL**ou **anexo**.</span><span class="sxs-lookup"><span data-stu-id="18197-218">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="18197-219">**Formato de envio**: **ID de mensagem de rede** (padrão, com o valor correspondente na caixa ID de mensagem de **rede** ) ou **arquivo** (navegue até um arquivo. eml ou. msg local).</span><span class="sxs-lookup"><span data-stu-id="18197-219">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="18197-220">Observe que, se você selecionar **arquivo** e, em seguida, selecionar **ID de mensagem de rede**, o valor inicialmente será desperdido.</span><span class="sxs-lookup"><span data-stu-id="18197-220">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="18197-221">**Destinatários**: digite no leasing um destinatário original da mensagem ou clique em **selecionar tudo** para identificar todos os destinatários.</span><span class="sxs-lookup"><span data-stu-id="18197-221">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="18197-222">Você também pode clicar em **selecionar todos** e, em seguida, remover seletivamente destinatários individuais.</span><span class="sxs-lookup"><span data-stu-id="18197-222">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="18197-223">**Motivo do envio**: **não deve ter sido bloqueado** (padrão) ou **deve ter sido bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="18197-223">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="18197-224">Quando tiver concluído, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="18197-224">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="18197-225">Se você não liberar ou remover a mensagem, ela será excluída depois que o período de retenção de quarentena padrão expirar.</span><span class="sxs-lookup"><span data-stu-id="18197-225">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="18197-226">Executar ação em várias mensagens de email em quarentena</span><span class="sxs-lookup"><span data-stu-id="18197-226">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="18197-227">Quando você seleciona várias mensagens em quarentena na lista (até 100), o painel de submenu **ações em massa** aparece onde você pode executar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="18197-227">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="18197-228">**Mensagens de lançamento**: as opções são as mesmas que quando você libera uma única mensagem, exceto que não é possível selecionar **mensagens de liberação para destinatários específicos**; Você só pode selecionar **a mensagem de liberação para todos os destinatários** ou **liberar mensagens para outras pessoas**.</span><span class="sxs-lookup"><span data-stu-id="18197-228">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="18197-229">**Excluir mensagens**: depois de clicar em **Sim** no aviso exibido, a mensagem será excluída imediatamente sem ser enviada aos destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="18197-229">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="18197-230">Quando tiver concluído, clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="18197-230">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="18197-231">Somente ATP: usar o centro de conformidade de & de segurança para gerenciar arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="18197-231">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="18197-232">Os procedimentos para arquivos em quarentena nesta seção estão disponíveis somente para assinantes do plano ATP 1 e do plano 2.</span><span class="sxs-lookup"><span data-stu-id="18197-232">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="18197-233">Em organizações com ATP, os administradores podem gerenciar arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="18197-233">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="18197-234">Exibir arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="18197-234">View quarantined files</span></span>

1. <span data-ttu-id="18197-235">No centro de segurança e conformidade, vá para a **quarentena**de **análise** \> de **Gerenciamento** \> de ameaças.</span><span class="sxs-lookup"><span data-stu-id="18197-235">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="18197-236">Altere o **modo de exibição colocado em quarentena** para os **arquivos**de valor padrão.</span><span class="sxs-lookup"><span data-stu-id="18197-236">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="18197-237">Você pode classificar em um campo clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="18197-237">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="18197-238">Você pode classificar os resultados clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="18197-238">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="18197-239">Clique em **Modificar colunas** para mostrar um máximo de sete colunas.</span><span class="sxs-lookup"><span data-stu-id="18197-239">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="18197-240">As colunas padrão são marcadas com um asterisco<sup>\*</sup>():</span><span class="sxs-lookup"><span data-stu-id="18197-240">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="18197-241">**Usuário**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18197-241">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="18197-242">**Alocações**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18197-242">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="18197-243">**Nome do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18197-243">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="18197-244">**URL do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18197-244">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="18197-245">**Tamanho do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18197-245">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="18197-246">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18197-246">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="18197-247">**Solta?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="18197-247">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="18197-248">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="18197-248">**Detected by**</span></span>

   - <span data-ttu-id="18197-249">**Modificado por hora**</span><span class="sxs-lookup"><span data-stu-id="18197-249">**Modified by time**</span></span>

4. <span data-ttu-id="18197-250">Para filtrar os resultados, clique em **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="18197-250">To filter the results, click **Filter**.</span></span> <span data-ttu-id="18197-251">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="18197-251">The available filters are:</span></span>

   - <span data-ttu-id="18197-252">**Tempo expira**: filtrar mensagens por quando elas expirarem da quarentena:</span><span class="sxs-lookup"><span data-stu-id="18197-252">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="18197-253">**Empresas**</span><span class="sxs-lookup"><span data-stu-id="18197-253">**Today**</span></span>

     - <span data-ttu-id="18197-254">**Próximos 2 dias**</span><span class="sxs-lookup"><span data-stu-id="18197-254">**Next 2 days**</span></span>

     - <span data-ttu-id="18197-255">**Próximos 7 dias**</span><span class="sxs-lookup"><span data-stu-id="18197-255">**Next 7 days**</span></span>

     - <span data-ttu-id="18197-256">Um intervalo personalizado de data/hora.</span><span class="sxs-lookup"><span data-stu-id="18197-256">A custom date/time range.</span></span>

   - <span data-ttu-id="18197-257">**Hora de recebimento**</span><span class="sxs-lookup"><span data-stu-id="18197-257">**Received time**</span></span>

   - <span data-ttu-id="18197-258">**Motivo da quarentena**: o único valor disponível é **malware**.</span><span class="sxs-lookup"><span data-stu-id="18197-258">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="18197-259">Depois de encontrar um arquivo em quarentena específico, selecione o arquivo para exibir os detalhes sobre ele e execute a ação nele (por exemplo, exibir, liberar, baixar ou excluir a mensagem).</span><span class="sxs-lookup"><span data-stu-id="18197-259">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="18197-260">Exportar resultados de arquivo</span><span class="sxs-lookup"><span data-stu-id="18197-260">Export file results</span></span>

1. <span data-ttu-id="18197-261">Selecione os arquivos nos quais você está interessado e clique em **Exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="18197-261">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="18197-262">Clique em **Sim** na mensagem de confirmação que avisa para manter a janela do navegador aberta.</span><span class="sxs-lookup"><span data-stu-id="18197-262">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="18197-263">Quando a exportação estiver pronta, você poderá nomear e escolher o local de download para o arquivo. csv.</span><span class="sxs-lookup"><span data-stu-id="18197-263">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="18197-264">Exibir detalhes de arquivo em quarentena</span><span class="sxs-lookup"><span data-stu-id="18197-264">View quarantined file details</span></span>

<span data-ttu-id="18197-265">Quando você seleciona um arquivo na lista, os seguintes detalhes de arquivo são exibidos no painel de submenu **detalhes** :</span><span class="sxs-lookup"><span data-stu-id="18197-265">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="18197-266">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="18197-266">**File Name**</span></span>

- <span data-ttu-id="18197-267">**URL do arquivo**: URL que define o local do arquivo (por exemplo, no SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="18197-267">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="18197-268">**Conteúdo mal-intencionado detectado em** A data/hora em que o arquivo foi colocado em quarentena.</span><span class="sxs-lookup"><span data-stu-id="18197-268">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="18197-269">**Expira**: a data em que o arquivo será excluído da quarentena.</span><span class="sxs-lookup"><span data-stu-id="18197-269">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="18197-270">**Detectado por**: ATP (proteção avançada contra ameaças) ou mecanismo antimalware da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="18197-270">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="18197-271">**Solta?**</span><span class="sxs-lookup"><span data-stu-id="18197-271">**Released?**</span></span>

- <span data-ttu-id="18197-272">**Nome do malware**</span><span class="sxs-lookup"><span data-stu-id="18197-272">**Malware Name**</span></span>

- <span data-ttu-id="18197-273">**ID do documento**: um identificador exclusivo para o documento.</span><span class="sxs-lookup"><span data-stu-id="18197-273">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="18197-274">**Tamanho do arquivo**: em kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="18197-274">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="18197-275">**Organização** A ID exclusiva da sua organização.</span><span class="sxs-lookup"><span data-stu-id="18197-275">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="18197-276">**Última modificação**</span><span class="sxs-lookup"><span data-stu-id="18197-276">**Last modified**</span></span>

- <span data-ttu-id="18197-277">**Modificado por**: o usuário que modificou o arquivo pela última vez.</span><span class="sxs-lookup"><span data-stu-id="18197-277">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="18197-278">**Algoritmo de hash seguro 256 bits (SHA-256) valor**: você pode usar esse valor de hash para identificar o arquivo em outros repositórios de reputação ou em outros locais em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="18197-278">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="18197-279">Executar ação em arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="18197-279">Take action on quarantined files</span></span>

<span data-ttu-id="18197-280">Ao selecionar um arquivo na lista, você pode executar as seguintes ações no arquivo no painel de submenu **detalhes** :</span><span class="sxs-lookup"><span data-stu-id="18197-280">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="18197-281">**Arquivos de lançamento**: selecione (padrão) ou desmarque **arquivos de relatório para a Microsoft para análise**e clique em **liberar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="18197-281">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="18197-282">**Baixar o arquivo**</span><span class="sxs-lookup"><span data-stu-id="18197-282">**Download file**</span></span>

- <span data-ttu-id="18197-283">**Remover arquivo da quarentena**</span><span class="sxs-lookup"><span data-stu-id="18197-283">**Remove file from quarantine**</span></span>

<span data-ttu-id="18197-284">Se você não liberar ou remover os arquivos, eles serão excluídos depois que o período de retenção de quarentena padrão expirar.</span><span class="sxs-lookup"><span data-stu-id="18197-284">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="18197-285">Ações em vários arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="18197-285">Actions on multiple quarantined files</span></span>

<span data-ttu-id="18197-286">Quando você seleciona vários arquivos em quarentena na lista (até 100), o painel de submenu **ações em massa** aparece onde você pode executar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="18197-286">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="18197-287">**Arquivos de versão**</span><span class="sxs-lookup"><span data-stu-id="18197-287">**Release files**</span></span>

- <span data-ttu-id="18197-288">**Excluir arquivos**: depois de clicar em **Sim** no aviso exibido, os arquivos serão excluídos imediatamente.</span><span class="sxs-lookup"><span data-stu-id="18197-288">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

<span data-ttu-id="18197-289">Quando tiver concluído, clique em **fechar**.</span><span class="sxs-lookup"><span data-stu-id="18197-289">When you're finished, click **Close**.</span></span>

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="18197-290">Usar o PowerShell do Exchange Online ou do Exchange Online Protection para exibir e gerenciar arquivos e mensagens em quarentena</span><span class="sxs-lookup"><span data-stu-id="18197-290">Use Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="18197-291">Os cmdlets que você usa para exibir e gerenciar mensagens e arquivos em quarentena são:</span><span class="sxs-lookup"><span data-stu-id="18197-291">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="18197-292">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="18197-292">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [<span data-ttu-id="18197-293">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="18197-293">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [<span data-ttu-id="18197-294">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="18197-294">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- <span data-ttu-id="18197-295">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Observe que este cmdlet é somente para mensagens, e não para arquivos de malware de ATP para SharePoint Online, onedrive for Business ou Teams.</span><span class="sxs-lookup"><span data-stu-id="18197-295">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="18197-296">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="18197-296">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
