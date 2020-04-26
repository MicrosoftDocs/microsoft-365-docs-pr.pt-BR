---
title: Localizar e liberar mensagens em quarentena como um usuário
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: Como um usuário do Microsoft 365, você pode exibir, liberar e excluir suas mensagens em quarentena (mensagens em que você é um destinatário e a filtragem de spam colocou a mensagem como spam ou email em massa). Você exibe e gerencia suas mensagens em quarentena no Centro de conformidade e de segurança.
ms.openlocfilehash: b8ab5835a29ccf0c58d27f56fe84d29745419b1a
ms.sourcegitcommit: 481fb95d8b80cf2102a9c73b21e7effa79e594e7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/24/2020
ms.locfileid: "43809016"
---
# <a name="find-and-release-quarantined-messages-as-a-user"></a><span data-ttu-id="ce276-104">Localizar e liberar mensagens em quarentena como um usuário</span><span class="sxs-lookup"><span data-stu-id="ce276-104">Find and release quarantined messages as a user</span></span>

<span data-ttu-id="ce276-105">A quarentena contém mensagens potencialmente perigosas ou indesejadas nas organizações que utilizam Microsoft 365 com caixas de correio do Exchange Online ou Exchange Online Protection (EOP) de organizações autônomas, sem as caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ce276-105">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="ce276-106">Para obter mais informações, consulte [Quarentena no Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="ce276-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="ce276-107">Como usuário, você pode exibir, liberar e excluir mensagens em quarentena em que você é um destinatário, e a mensagem foi colocada em quarentena como spam, e-mail em massa ou (a partir de abril de 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="ce276-107">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="ce276-108">Você visualiza e gerencia suas mensagens em quarentena no Centro de Conformidade e Segurança ou (se um administrador configurou isso) em [notificações de spam do usuário final](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="ce276-108">You view and manage your quarantined messages in the Security & Compliance Center or (if an admin has set this up) in [end-user spam notifications](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ce276-109">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="ce276-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ce276-110">Para abrir o Centro de Conformidade e Segurança, acesse <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="ce276-110">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="ce276-111">Para abrir a página Quarentena imediatamente, vá para <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="ce276-111">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="ce276-112">Os administradores conseguem configurar pelo tempo que as mensagens forem mantidas em quarentena antes de serem excluídas permanentemente (políticas anti-spam).</span><span class="sxs-lookup"><span data-stu-id="ce276-112">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="ce276-113">As mensagens que saíram da quarentena se tornam irrecuperáveis.</span><span class="sxs-lookup"><span data-stu-id="ce276-113">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="ce276-114">Para obter mais informações, consulte [Configure as políticas de anti-spam no Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ce276-114">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="ce276-115">Os administradores também podem [habilitar as notificações de spam do usuário final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) na políticas anti-spam.</span><span class="sxs-lookup"><span data-stu-id="ce276-115">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="ce276-116">Os usuários podem liberar mensagens em quarentena de spam em quarentena, mas não as mensagens de phishing em quarentena diretamente dessas notificações.</span><span class="sxs-lookup"><span data-stu-id="ce276-116">Users can release spam quarantined messages but not phish quarantined messages directly from these notifications.</span></span> <span data-ttu-id="ce276-117">Para obter mais informações, consulte [Notificações de spam do usuário final no Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="ce276-117">For more information, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="ce276-118">As mensagens que foram colocadas em quarentena por regras de phishing, malware ou fluxo de mensagens de alta confiança (também conhecidas como regras de transporte) estão disponíveis apenas aos administradores.</span><span class="sxs-lookup"><span data-stu-id="ce276-118">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="ce276-119">As mensagens de phishing podem ser analisadas pelos usuários, mas apenas liberados por administradores.</span><span class="sxs-lookup"><span data-stu-id="ce276-119">Phish messages can be reviewed by users but only released by admins.</span></span> <span data-ttu-id="ce276-120">Para obter mais informações, consulte [Gerenciar arquivos e mensagens em quarentena como administrador no Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="ce276-120">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="ce276-121">Você só pode liberar uma mensagem e relatá-la como falso positivo (e não como lixo eletrônico) uma vez.</span><span class="sxs-lookup"><span data-stu-id="ce276-121">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="ce276-122">Visualizar suas mensagens em quarentena</span><span class="sxs-lookup"><span data-stu-id="ce276-122">View your quarantined messages</span></span>

1. <span data-ttu-id="ce276-123">No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.</span><span class="sxs-lookup"><span data-stu-id="ce276-123">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="ce276-124">Você pode classificar os resultados clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="ce276-124">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="ce276-125">Clique em **Modificar colunas** para exibir um máximo de sete colunas.</span><span class="sxs-lookup"><span data-stu-id="ce276-125">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="ce276-126">Os valores padrão são marcados com um asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="ce276-126">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="ce276-127">**Recebido**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ce276-127">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="ce276-128">**Remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ce276-128">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="ce276-129">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ce276-129">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="ce276-130">**Motivo da quarentena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ce276-130">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="ce276-131">**Lançado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ce276-131">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="ce276-132">**Tipo de política**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ce276-132">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="ce276-133">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="ce276-133">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="ce276-134">**Recipiente**</span><span class="sxs-lookup"><span data-stu-id="ce276-134">**Recipient**</span></span>

   - <span data-ttu-id="ce276-135">**ID da mensagem**</span><span class="sxs-lookup"><span data-stu-id="ce276-135">**Message ID**</span></span>

   - <span data-ttu-id="ce276-136">**Nome da política**</span><span class="sxs-lookup"><span data-stu-id="ce276-136">**Policy name**</span></span>

   - <span data-ttu-id="ce276-137">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="ce276-137">**Size**</span></span>

   - <span data-ttu-id="ce276-138">**Direção**</span><span class="sxs-lookup"><span data-stu-id="ce276-138">**Direction**</span></span>

   <span data-ttu-id="ce276-139">Quando você terminar, clique em **Salvar**, ou clique em **Definido como padrão**.</span><span class="sxs-lookup"><span data-stu-id="ce276-139">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="ce276-140">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="ce276-140">To filter the results, click **Filter**.</span></span> <span data-ttu-id="ce276-141">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="ce276-141">The available filters are:</span></span>

   - <span data-ttu-id="ce276-142">**Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:</span><span class="sxs-lookup"><span data-stu-id="ce276-142">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="ce276-143">**Hoje**</span><span class="sxs-lookup"><span data-stu-id="ce276-143">**Today**</span></span>

     - <span data-ttu-id="ce276-144">**Próximos 2 dias**</span><span class="sxs-lookup"><span data-stu-id="ce276-144">**Next 2 days**</span></span>

     - <span data-ttu-id="ce276-145">**Próximas 7 semanas**</span><span class="sxs-lookup"><span data-stu-id="ce276-145">**Next 7 days**</span></span>

     - <span data-ttu-id="ce276-146">**Personalizado**: Insira uma **Data de início** e uma **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="ce276-146">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="ce276-147">**Hora recebida**: Insira uma **Data de início** e uma **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="ce276-147">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="ce276-148">**Motivo da quarentena**:</span><span class="sxs-lookup"><span data-stu-id="ce276-148">**Quarantine reason**:</span></span>

     - <span data-ttu-id="ce276-149">**Em massa**</span><span class="sxs-lookup"><span data-stu-id="ce276-149">**Bulk**</span></span>

     - <span data-ttu-id="ce276-150">**Spam**</span><span class="sxs-lookup"><span data-stu-id="ce276-150">**Spam**</span></span>

     - <span data-ttu-id="ce276-151">**Phish** (Em abril de 2020)</span><span class="sxs-lookup"><span data-stu-id="ce276-151">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="ce276-152">Para limpar o filtro, clique em **Limpar**.</span><span class="sxs-lookup"><span data-stu-id="ce276-152">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="ce276-153">Para ocultar o submenu do filtro, clique novamente em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="ce276-153">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="ce276-154">Use **Classificar resultados por** (o botão **ID da mensagem** por padrão) e um valor correspondente para localizar mensagens específicas.</span><span class="sxs-lookup"><span data-stu-id="ce276-154">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="ce276-155">Os curingas não possuem suporte.</span><span class="sxs-lookup"><span data-stu-id="ce276-155">Wildcards aren't supported.</span></span> <span data-ttu-id="ce276-156">Você pode pesquisar pelos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ce276-156">You can search by the following values:</span></span>

   - <span data-ttu-id="ce276-157">**ID da mensagem**: o identificador globalmente exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="ce276-157">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="ce276-158">Se você selecionar uma mensagem na lista, o valor da **ID da mensagem** será exibido no painel **Detalhes** que é exibido.</span><span class="sxs-lookup"><span data-stu-id="ce276-158">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="ce276-159">Os administradores podem usar [Rastreamento da mensagem](message-trace-scc.md) para localizar mensagens e seus valores da ID da mensagem correspondentes.</span><span class="sxs-lookup"><span data-stu-id="ce276-159">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="ce276-160">**Endereço de e-mail do remetente**: o endereço de e-mail de um único remetente.</span><span class="sxs-lookup"><span data-stu-id="ce276-160">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="ce276-161">**Endereço de e-mail do destinatário**: o endereço de e-mail de um único destinatário.</span><span class="sxs-lookup"><span data-stu-id="ce276-161">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="ce276-162">**Assunto**: use todo o assunto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="ce276-162">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="ce276-163">A pesquisa não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ce276-163">The search is not case-sensitive.</span></span>

   <span data-ttu-id="ce276-164">Depois de ter inserido os critérios da pesquisa, clique em ![Atualizar botão](../../media/scc-quarantine-refresh.png) **Atualizar** para filtrar os resultados.</span><span class="sxs-lookup"><span data-stu-id="ce276-164">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="ce276-165">Depois de encontrar uma mensagem específica em quarentena, selecione a mensagem para exibir detalhes sobre ela e execute uma ação (por exemplo: exibir, liberar, fazer download ou excluir a mensagem).</span><span class="sxs-lookup"><span data-stu-id="ce276-165">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="ce276-166">Exporte os resultados da mensagem </span><span class="sxs-lookup"><span data-stu-id="ce276-166">Export message results</span></span>

1. <span data-ttu-id="ce276-167">Selecione as mensagens que você está interessado e clique em **Exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="ce276-167">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="ce276-168">Clique em **Sim** na mensagem de confirmação que avisa para manter a janela do navegador aberta.</span><span class="sxs-lookup"><span data-stu-id="ce276-168">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="ce276-169">Quando a exportação estiver pronta, você poderá nomear e escolher o local de download do arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="ce276-169">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="ce276-170">Exiba detalhes da mensagem em quarentena</span><span class="sxs-lookup"><span data-stu-id="ce276-170">View quarantined message details</span></span>

<span data-ttu-id="ce276-171">Quando você clica em uma mensagem de e-mail na lista, os seguintes detalhes de mensagem são exibidos no painel de submenu **Detalhes**:</span><span class="sxs-lookup"><span data-stu-id="ce276-171">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="ce276-172">**ID da mensagem**: o identificador globalmente exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="ce276-172">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="ce276-173">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="ce276-173">**Sender address**</span></span>

- <span data-ttu-id="ce276-174">**Recebido**: a data e a hora em que a mensagem foi recebida.</span><span class="sxs-lookup"><span data-stu-id="ce276-174">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="ce276-175">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="ce276-175">**Subject**</span></span>

- <span data-ttu-id="ce276-176">**Motivo da quarentena**: mostra se uma mensagem foi identificada como **Spam**, **Em massa** ou (desde abril de 2020) **Phish**.</span><span class="sxs-lookup"><span data-stu-id="ce276-176">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="ce276-177">**Destinatários**: se a mensagem contiver vários destinatários, você precisará clicar em **Visualizar mensagem** ou **Exibir o cabeçalho da mensagem** para visualizar a lista completa dos destinatários.</span><span class="sxs-lookup"><span data-stu-id="ce276-177">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="ce276-178">**Expira**: a data/hora em que a mensagem será excluída de forma automática e permanente da quarentena.</span><span class="sxs-lookup"><span data-stu-id="ce276-178">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="ce276-179">**Liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem foi liberada.</span><span class="sxs-lookup"><span data-stu-id="ce276-179">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="ce276-180">**Sem liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem não foi liberada.</span><span class="sxs-lookup"><span data-stu-id="ce276-180">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="ce276-181">Tomar medidas quanto aos e-mails em quarentena</span><span class="sxs-lookup"><span data-stu-id="ce276-181">Take action on quarantined email</span></span>

<span data-ttu-id="ce276-182">Depois de selecionar uma mensagem, você tem opções para o que fazer com as mensagens no painel de submenu **Detalhes**:</span><span class="sxs-lookup"><span data-stu-id="ce276-182">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="ce276-183">**Mensagem de liberação**: no painel de submenu que é exibido, escolha se quer o **Relatório de mensagens do Microsoft para ser analisado**.</span><span class="sxs-lookup"><span data-stu-id="ce276-183">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="ce276-184">Essa opção é selecionada por padrão e relata a mensagem em quarentena incorreta à Microsoft como um falso positivo.</span><span class="sxs-lookup"><span data-stu-id="ce276-184">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="ce276-185">Quando terminar, clique em **Liberar mensagens**.</span><span class="sxs-lookup"><span data-stu-id="ce276-185">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="ce276-186">**Exibir cabeçalho da mensagem**: escolha este link para visualizar o texto do cabeçalho da mensagem.</span><span class="sxs-lookup"><span data-stu-id="ce276-186">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="ce276-187">Para analisar os valores e campos de cabeçalho em detalhes, copie o texto do cabeçalho da mensagem para a área de transferência e, em seguida, escolha **Analisador de Cabeçalhos de Mensagens da Microsoft** para acessar o Analisar de Conectividade Remota (clique com o botão direito e escolha **Abrir em uma nova guia** se não quiser deixar o Microsoft 365 para concluir essa tarefa).</span><span class="sxs-lookup"><span data-stu-id="ce276-187">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="ce276-188">Cole o cabeçalho da mensagem na página na seção Analisador do cabeçalho da mensagem e escolha **Analisar cabeçalhos**:</span><span class="sxs-lookup"><span data-stu-id="ce276-188">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="ce276-189">**Visualizar mensagem**: no painel de submenu que é exibido, escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="ce276-189">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="ce276-190">**Visualização da fonte**: mostra a versão HTML do corpo da mensagem com todos os links desabilitados.</span><span class="sxs-lookup"><span data-stu-id="ce276-190">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="ce276-191">**Visualização do texto**: mostra o corpo da mensagem em texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="ce276-191">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="ce276-192">**Mensagem de download**: no painel de submenu que é exibido, clique em **Compreendo os riscos de baixar esta mensagem** para salvar uma cópia local da mensagem no formato .eml.</span><span class="sxs-lookup"><span data-stu-id="ce276-192">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="ce276-193">**Remover da quarentena**: depois de clicar em **Sim** no aviso que é exibido, a mensagem é imediatamente excluída.</span><span class="sxs-lookup"><span data-stu-id="ce276-193">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="ce276-194">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="ce276-194">When you're finished, click **Close**.</span></span>

<span data-ttu-id="ce276-195">Se você não liberar ou remover a mensagem, ela será excluída após o término do período de retenção da quarentena padrão.</span><span class="sxs-lookup"><span data-stu-id="ce276-195">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="ce276-196">Tome medidas em várias mensagens quanto aos e-mails em quarentena</span><span class="sxs-lookup"><span data-stu-id="ce276-196">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="ce276-197">Quando você seleciona várias mensagens que estão em quarentena na lista (até 100), o painel de submenu **Ações em massa** é exibido em que você pode realizar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="ce276-197">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="ce276-198">**Mensagens de lançamento**: as opções são as mesmas de quando você libera uma única mensagem, mas não é possível clicar em **Liberar mensagens para destinatários específicos**; você só pode clicar em **Mensagem de lançamento a todos os destinatários** ou **Liberar mensagens para outras pessoas**.</span><span class="sxs-lookup"><span data-stu-id="ce276-198">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="ce276-199">**Excluir mensagens**: depois de clicar em **Sim** no aviso que é exibido, a mensagem é imediatamente excluída sem ser enviada aos destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="ce276-199">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="ce276-200">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="ce276-200">When you're finished, click **Close**.</span></span>
