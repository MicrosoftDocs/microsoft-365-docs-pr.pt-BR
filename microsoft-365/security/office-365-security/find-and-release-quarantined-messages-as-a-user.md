---
title: Localizar e liberar mensagens em quarentena como um usuário
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os usuários podem aprender como exibir e gerenciar mensagens em quarentena no Exchange Online Protection (EOP) que deveriam ter sido entregues a eles.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e9a9da170dc0d3effba495c29672fb8f6bb02031
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599930"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a><span data-ttu-id="04941-103">Localizar e liberar mensagens em quarentena como usuário no EOP</span><span class="sxs-lookup"><span data-stu-id="04941-103">Find and release quarantined messages as a user in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="04941-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="04941-104">**Applies to**</span></span>
- [<span data-ttu-id="04941-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="04941-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="04941-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="04941-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="04941-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04941-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="04941-108">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena retém mensagens potencialmente perigosas ou indesejadas.</span><span class="sxs-lookup"><span data-stu-id="04941-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, quarantine holds potentially dangerous or unwanted messages.</span></span> <span data-ttu-id="04941-109">Para obter mais informações, consulte [Quarentena no EOP](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="04941-109">For more information, see [Quarantine in EOP](quarantine-email-messages.md).</span></span>

<span data-ttu-id="04941-110">Como usuário, você pode exibir, liberar e excluir mensagens em quarentena em que você é um destinatário, e a mensagem foi colocada em quarentena como spam ou email em massa.</span><span class="sxs-lookup"><span data-stu-id="04941-110">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam or bulk email.</span></span> <span data-ttu-id="04941-111">A partir de abril de 2020, você pode exibir ou excluir mensagens de phishing em quarentena (phishing sem alta confiança) em que você é um destinatário.</span><span class="sxs-lookup"><span data-stu-id="04941-111">As of April 2020, you can view or delete quarantined phishing (not high confidence phishing) messages where you are a recipient.</span></span> <span data-ttu-id="04941-112">Você visualiza e gerencia suas mensagens em quarentena no Centro de Conformidade e Segurança ou (se um administrador configurou isso) em [notificações de spam do usuário final](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="04941-112">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="04941-113">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="04941-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="04941-114">Para abrir o Centro de Conformidade e Segurança, acesse <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="04941-114">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="04941-115">Para abrir a página Quarentena imediatamente, vá para <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="04941-115">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="04941-116">Os administradores conseguem configurar pelo tempo que as mensagens forem mantidas em quarentena antes de serem excluídas permanentemente (políticas anti-spam).</span><span class="sxs-lookup"><span data-stu-id="04941-116">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="04941-117">As mensagens que saíram da quarentena se tornam irrecuperáveis.</span><span class="sxs-lookup"><span data-stu-id="04941-117">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="04941-118">Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="04941-118">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="04941-119">Os administradores também podem [habilitar as notificações de spam do usuário final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) na políticas anti-spam.</span><span class="sxs-lookup"><span data-stu-id="04941-119">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="04941-120">Os usuários podem liberar as mensagens de spam na quarentena, diretamente a partir dessas notificações.</span><span class="sxs-lookup"><span data-stu-id="04941-120">Users can release quarantined spam messages directly from these notifications.</span></span> <span data-ttu-id="04941-121">Os usuários podem revisar as mensagens de phishing na quarentena (menos as mensagens de phishing de alta confiança), diretamente a partir dessas notificações.</span><span class="sxs-lookup"><span data-stu-id="04941-121">Users can review quarantined phishing messages (not high confidence phishing messages) directly from these notifications.</span></span> <span data-ttu-id="04941-122">Para obter mais informações, consulte [Notificações de spam do usuário final no EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="04941-122">For more information, see [End-user spam notifications in EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="04941-123">As mensagens que foram colocadas na quarentena por phishing de alta confiança, malware ou por regras do fluxo de email (também conhecidas como regras de transporte) estão disponíveis apenas para administradores e não são visíveis para os usuários.</span><span class="sxs-lookup"><span data-stu-id="04941-123">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins, and aren't visible to users.</span></span> <span data-ttu-id="04941-124">Para obter mais informações, consulte [Gerenciar mensagens e arquivos em quarentena como administrador no EOP](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="04941-124">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="04941-125">Você só pode liberar uma mensagem e relatá-la como falso positivo (e não como lixo eletrônico) uma vez.</span><span class="sxs-lookup"><span data-stu-id="04941-125">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="04941-126">Visualizar suas mensagens em quarentena</span><span class="sxs-lookup"><span data-stu-id="04941-126">View your quarantined messages</span></span>

1. <span data-ttu-id="04941-127">No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.</span><span class="sxs-lookup"><span data-stu-id="04941-127">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="04941-128">Você pode classificar os resultados clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="04941-128">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="04941-129">Clique em **Modificar colunas** para exibir um máximo de sete colunas.</span><span class="sxs-lookup"><span data-stu-id="04941-129">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="04941-130">Os valores padrão são marcados com um asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="04941-130">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="04941-131">**Recebido**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="04941-131">**Received**<sup>\*</sup></span></span>
   - <span data-ttu-id="04941-132">**Remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="04941-132">**Sender**<sup>\*</sup></span></span>
   - <span data-ttu-id="04941-133">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="04941-133">**Subject**<sup>\*</sup></span></span>
   - <span data-ttu-id="04941-134">**Motivo da quarentena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="04941-134">**Quarantine reason**<sup>\*</sup></span></span>
   - <span data-ttu-id="04941-135">**Lançado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="04941-135">**Released?**<sup>\*</sup></span></span>
   - <span data-ttu-id="04941-136">**Tipo de política**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="04941-136">**Policy type**<sup>\*</sup></span></span>
   - <span data-ttu-id="04941-137">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="04941-137">**Expires**<sup>\*</sup></span></span>
   - <span data-ttu-id="04941-138">**Recipiente**</span><span class="sxs-lookup"><span data-stu-id="04941-138">**Recipient**</span></span>
   - <span data-ttu-id="04941-139">**ID da mensagem**</span><span class="sxs-lookup"><span data-stu-id="04941-139">**Message ID**</span></span>
   - <span data-ttu-id="04941-140">**Nome da política**</span><span class="sxs-lookup"><span data-stu-id="04941-140">**Policy name**</span></span>
   - <span data-ttu-id="04941-141">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="04941-141">**Size**</span></span>
   - <span data-ttu-id="04941-142">**Direção**</span><span class="sxs-lookup"><span data-stu-id="04941-142">**Direction**</span></span>

   <span data-ttu-id="04941-143">Quando você terminar, clique em **Salvar**, ou clique em **Definido como padrão**.</span><span class="sxs-lookup"><span data-stu-id="04941-143">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="04941-144">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="04941-144">To filter the results, click **Filter**.</span></span> <span data-ttu-id="04941-145">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="04941-145">The available filters are:</span></span>

   - <span data-ttu-id="04941-146">**Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:</span><span class="sxs-lookup"><span data-stu-id="04941-146">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>
     - <span data-ttu-id="04941-147">**Hoje**</span><span class="sxs-lookup"><span data-stu-id="04941-147">**Today**</span></span>
     - <span data-ttu-id="04941-148">**Próximos 2 dias**</span><span class="sxs-lookup"><span data-stu-id="04941-148">**Next 2 days**</span></span>
     - <span data-ttu-id="04941-149">**Próximas 7 semanas**</span><span class="sxs-lookup"><span data-stu-id="04941-149">**Next 7 days**</span></span>
     - <span data-ttu-id="04941-150">**Personalizado**: Insira uma **Data de início** e uma **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="04941-150">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="04941-151">**Hora recebida**: Insira uma **Data de início** e uma **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="04941-151">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="04941-152">**Motivo da quarentena**:</span><span class="sxs-lookup"><span data-stu-id="04941-152">**Quarantine reason**:</span></span>
     - <span data-ttu-id="04941-153">**Em massa**</span><span class="sxs-lookup"><span data-stu-id="04941-153">**Bulk**</span></span>
     - <span data-ttu-id="04941-154">**Spam**</span><span class="sxs-lookup"><span data-stu-id="04941-154">**Spam**</span></span>
     - <span data-ttu-id="04941-155">**Golpe**</span><span class="sxs-lookup"><span data-stu-id="04941-155">**Phish**</span></span>

   - <span data-ttu-id="04941-156">**Tipo de Política**: Filtre mensagens por tipo de política:</span><span class="sxs-lookup"><span data-stu-id="04941-156">**Policy Type**: Filter messages by policy type:</span></span>
     - <span data-ttu-id="04941-157">**Política Anti-phish**:</span><span class="sxs-lookup"><span data-stu-id="04941-157">**Anti-phish policy**</span></span>
     - <span data-ttu-id="04941-158">**Política de filtro de conteúdo hospedado** (política antispam)</span><span class="sxs-lookup"><span data-stu-id="04941-158">**Hosted content filter policy** (anti-spam policy)</span></span>

   <span data-ttu-id="04941-159">Para limpar o filtro, clique em **Limpar**.</span><span class="sxs-lookup"><span data-stu-id="04941-159">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="04941-160">Para ocultar o submenu do filtro, clique novamente em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="04941-160">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="04941-161">Use **Classificar resultados por** (o botão **ID da mensagem** por padrão) e um valor correspondente para localizar mensagens específicas.</span><span class="sxs-lookup"><span data-stu-id="04941-161">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="04941-162">Os curingas não possuem suporte.</span><span class="sxs-lookup"><span data-stu-id="04941-162">Wildcards aren't supported.</span></span> <span data-ttu-id="04941-163">Você pode pesquisar pelos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="04941-163">You can search by the following values:</span></span>

   - <span data-ttu-id="04941-164">**ID da mensagem**: o identificador globalmente exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="04941-164">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="04941-165">Se você selecionar uma mensagem na lista, o valor da **ID da mensagem** será exibido no painel **Detalhes** que é exibido.</span><span class="sxs-lookup"><span data-stu-id="04941-165">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="04941-166">Os administradores podem usar [Rastreamento da mensagem](message-trace-scc.md) para localizar mensagens e seus valores da ID da mensagem correspondentes.</span><span class="sxs-lookup"><span data-stu-id="04941-166">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="04941-167">**Endereço de e-mail do remetente**: o endereço de e-mail de um único remetente.</span><span class="sxs-lookup"><span data-stu-id="04941-167">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="04941-168">**Nome da política**: Use o nome completo da política da mensagem.</span><span class="sxs-lookup"><span data-stu-id="04941-168">**Policy name**: Use the entire policy name of the message.</span></span> <span data-ttu-id="04941-169">A pesquisa não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="04941-169">The search is not case-sensitive.</span></span>

   - <span data-ttu-id="04941-170">**Endereço de e-mail do destinatário**: o endereço de e-mail de um único destinatário.</span><span class="sxs-lookup"><span data-stu-id="04941-170">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="04941-171">**Assunto**: use todo o assunto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="04941-171">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="04941-172">A pesquisa não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="04941-172">The search is not case-sensitive.</span></span>

   <span data-ttu-id="04941-173">Depois de ter inserido os critérios da pesquisa, clique em ![Atualizar botão](../../media/scc-quarantine-refresh.png) **Atualizar** para filtrar os resultados.</span><span class="sxs-lookup"><span data-stu-id="04941-173">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="04941-174">Depois de encontrar uma mensagem específica em quarentena, selecione a mensagem para exibir detalhes sobre ela e execute uma ação (por exemplo: exibir, liberar, fazer download ou excluir a mensagem).</span><span class="sxs-lookup"><span data-stu-id="04941-174">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="04941-175">Exporte os resultados da mensagem </span><span class="sxs-lookup"><span data-stu-id="04941-175">Export message results</span></span>

1. <span data-ttu-id="04941-176">Selecione as mensagens que você está interessado e clique em **Exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="04941-176">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="04941-177">Clique em **Sim** na mensagem de confirmação que avisa para manter a janela do navegador aberta.</span><span class="sxs-lookup"><span data-stu-id="04941-177">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="04941-178">Quando a exportação estiver pronta, você poderá nomear e escolher o local de download do arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="04941-178">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="04941-179">Exiba detalhes da mensagem em quarentena</span><span class="sxs-lookup"><span data-stu-id="04941-179">View quarantined message details</span></span>

<span data-ttu-id="04941-180">Quando você clica em uma mensagem de e-mail na lista, os seguintes detalhes de mensagem são exibidos no painel de submenu **Detalhes**:</span><span class="sxs-lookup"><span data-stu-id="04941-180">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="04941-181">**ID da mensagem**: o identificador globalmente exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="04941-181">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="04941-182">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="04941-182">**Sender address**</span></span>

- <span data-ttu-id="04941-183">**Recebido**: a data e a hora em que a mensagem foi recebida.</span><span class="sxs-lookup"><span data-stu-id="04941-183">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="04941-184">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="04941-184">**Subject**</span></span>

- <span data-ttu-id="04941-185">**Motivo da quarentena**: Exibe se a mensagem foi identificada como **Spam**, **Em massa** ou **Golpe**.</span><span class="sxs-lookup"><span data-stu-id="04941-185">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or **Phish**.</span></span>

- <span data-ttu-id="04941-186">**Destinatários**: se a mensagem contiver vários destinatários, você precisará clicar em **Visualizar mensagem** ou **Exibir o cabeçalho da mensagem** para visualizar a lista completa dos destinatários.</span><span class="sxs-lookup"><span data-stu-id="04941-186">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="04941-187">**Expira**: a data/hora em que a mensagem será excluída de forma automática e permanente da quarentena.</span><span class="sxs-lookup"><span data-stu-id="04941-187">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="04941-188">**Liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem foi liberada.</span><span class="sxs-lookup"><span data-stu-id="04941-188">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="04941-189">**Sem liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem não foi liberada.</span><span class="sxs-lookup"><span data-stu-id="04941-189">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="04941-190">Tomar medidas quanto aos e-mails em quarentena</span><span class="sxs-lookup"><span data-stu-id="04941-190">Take action on quarantined email</span></span>

<span data-ttu-id="04941-191">Depois de selecionar uma mensagem, você tem opções para o que fazer com as mensagens no painel de submenu **Detalhes**:</span><span class="sxs-lookup"><span data-stu-id="04941-191">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="04941-192">**Mensagem de liberação**: no painel de submenu que é exibido, escolha se quer o **Relatório de mensagens do Microsoft para ser analisado**.</span><span class="sxs-lookup"><span data-stu-id="04941-192">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="04941-193">Essa opção é selecionada por padrão e relata a mensagem em quarentena incorreta à Microsoft como um falso positivo.</span><span class="sxs-lookup"><span data-stu-id="04941-193">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="04941-194">Quando terminar, clique em **Liberar mensagens**.</span><span class="sxs-lookup"><span data-stu-id="04941-194">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="04941-195">**Exibir cabeçalho da mensagem**: escolha este link para visualizar o texto do cabeçalho da mensagem.</span><span class="sxs-lookup"><span data-stu-id="04941-195">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="04941-196">Para analisar os valores e campos de cabeçalho em detalhes, copie o texto do cabeçalho da mensagem para a área de transferência e, em seguida, escolha **Analisador de Cabeçalhos de Mensagens da Microsoft** para acessar o Analisar de Conectividade Remota (clique com o botão direito e escolha **Abrir em uma nova guia** se não quiser deixar o Microsoft 365 para concluir essa tarefa).</span><span class="sxs-lookup"><span data-stu-id="04941-196">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="04941-197">Cole o cabeçalho da mensagem na página na seção Analisador do cabeçalho da mensagem e escolha **Analisar cabeçalhos**:</span><span class="sxs-lookup"><span data-stu-id="04941-197">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="04941-198">**Visualizar mensagem**: no painel de submenu que é exibido, escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="04941-198">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>
  - <span data-ttu-id="04941-199">**Visualização da fonte**: mostra a versão HTML do corpo da mensagem com todos os links desabilitados.</span><span class="sxs-lookup"><span data-stu-id="04941-199">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  - <span data-ttu-id="04941-200">**Visualização do texto**: mostra o corpo da mensagem em texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="04941-200">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="04941-201">**Remover da quarentena**: depois de clicar em **Sim** no aviso que é exibido, a mensagem é imediatamente excluída.</span><span class="sxs-lookup"><span data-stu-id="04941-201">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

- <span data-ttu-id="04941-202">**Bloquear Remetente**: evita que o remetente envie mensagens para você.</span><span class="sxs-lookup"><span data-stu-id="04941-202">**Block Sender**: Prevents the sender from sending messages to you.</span></span>

<span data-ttu-id="04941-203">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="04941-203">When you're finished, click **Close**.</span></span>

<span data-ttu-id="04941-204">Se você não liberar ou remover a mensagem, ela será excluída após o término do período de retenção da quarentena padrão.</span><span class="sxs-lookup"><span data-stu-id="04941-204">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="04941-205">Tome medidas em várias mensagens quanto aos e-mails em quarentena</span><span class="sxs-lookup"><span data-stu-id="04941-205">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="04941-206">Quando você seleciona várias mensagens que estão em quarentena na lista (até 100), o painel de submenu **Ações em massa** é exibido em que você pode realizar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="04941-206">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="04941-207">**Mensagens de lançamento**: as opções são as mesmas de quando você libera uma única mensagem, mas não é possível clicar em **Liberar mensagens para destinatários específicos**; você só pode clicar em **Mensagem de lançamento a todos os destinatários** ou **Liberar mensagens para outras pessoas**.</span><span class="sxs-lookup"><span data-stu-id="04941-207">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="04941-208">**Excluir mensagens**: depois de clicar em **Sim** no aviso que é exibido, a mensagem é imediatamente excluída sem ser enviada aos destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="04941-208">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="04941-209">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="04941-209">When you're finished, click **Close**.</span></span>
