---
title: Localizar e liberar mensagens em quarentena como usuário do Office 365
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
description: Como usuário do Office 365, você pode exibir, liberar e excluir suas mensagens em quarentena (mensagens em que você é um destinatário e a filtragem de spam em quarentena colocou a mensagem como spam ou e-mail em massa). Você exibe e gerencia suas mensagens em quarentena no Centro de conformidade e de segurança.
ms.openlocfilehash: 04f04cfddb123bf176f3c71568789c77d225a601
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893665"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a><span data-ttu-id="05e24-104">Localize e libere mensagens em quarentena como usuário do Office 365</span><span class="sxs-lookup"><span data-stu-id="05e24-104">Find and release quarantined messages as a user in Office 365</span></span>

<span data-ttu-id="05e24-105">A quarentena mantém mensagens potencialmente perigosas ou indesejadas nas organizações do Office 365 com caixas de correio do Exchange Online ou de organizações autônomas do Exchange Online Protection (EOP) sem as caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="05e24-105">Quarantine holds potentially dangerous or unwanted messages in Office 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="05e24-106">Para obter mais informações, consulte [Quarentena no Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="05e24-106">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="05e24-107">Como usuário, você pode exibir, liberar e excluir mensagens em quarentena em que você é um destinatário, e a mensagem foi colocada em quarentena como spam, e-mail em massa ou (a partir de abril de 2020) phishing.</span><span class="sxs-lookup"><span data-stu-id="05e24-107">As a user, you can view, release, and delete quarantined messages where you are a recipient, and the message was quarantined as spam, bulk email, or (as of April, 2020) phishing.</span></span> <span data-ttu-id="05e24-108">Você também pode relatar falsos positivos à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="05e24-108">You can also report false positives to Microsoft.</span></span>

<span data-ttu-id="05e24-109">Você exibe e gerencia suas mensagens em quarentena no Centro de conformidade e de segurança.</span><span class="sxs-lookup"><span data-stu-id="05e24-109">You view and manage your quarantined messages in the Security & Compliance Center.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="05e24-110">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="05e24-110">What do you need to know before you begin?</span></span>

- <span data-ttu-id="05e24-111">Para abrir o Centro de Conformidade e Segurança do Office 365, vá para <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="05e24-111">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="05e24-112">Para abrir a página Quarentena imediatamente, vá para <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="05e24-112">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="05e24-113">Os administradores conseguem configurar pelo tempo que as mensagens forem mantidas em quarentena antes de serem excluídas permanentemente (políticas anti-spam).</span><span class="sxs-lookup"><span data-stu-id="05e24-113">Admins can configure how long messages are kept in quarantine before they're permanently deleted (anti-spam policies).</span></span> <span data-ttu-id="05e24-114">As mensagens que saíram da quarentena se tornam irrecuperáveis.</span><span class="sxs-lookup"><span data-stu-id="05e24-114">Messages that have expired from quarantine are unrecoverable.</span></span> <span data-ttu-id="05e24-115">Para obter mais informações, consulte [Configure as políticas de anti-spam no Office 365](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="05e24-115">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

- <span data-ttu-id="05e24-116">Os administradores também podem [habilitar as notificações de spam do usuário final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) na políticas anti-spam.</span><span class="sxs-lookup"><span data-stu-id="05e24-116">Admins can also [enable end-user spam notifications](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) in anti-spam policies.</span></span> <span data-ttu-id="05e24-117">A partir de outubro de 2019, você não poderá mais liberar mensagens em quarentena diretamente dessas notificações.</span><span class="sxs-lookup"><span data-stu-id="05e24-117">As of October 2019, you can no longer release quarantined messages directly from these notifications.</span></span> <span data-ttu-id="05e24-118">Você pode clicar em **Revisão** na notificação, o que o levará à Quarentena no Centro de conformidade e segurança.</span><span class="sxs-lookup"><span data-stu-id="05e24-118">You can click **Review** in the notification, which will take you to Quarantine in the Security & Compliance Center.</span></span> <span data-ttu-id="05e24-119">Para obter mais informações sobre as notificações, consulte [Notificações de spam do usuário final no Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span><span class="sxs-lookup"><span data-stu-id="05e24-119">For more information about the notifications, see [End-user spam notifications in Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).</span></span>

- <span data-ttu-id="05e24-120">As mensagens que foram colocadas em quarentena por regras de phishing, malware ou fluxo de mensagens de alta confiança (também conhecidas como regras de transporte) estão disponíveis apenas aos administradores.</span><span class="sxs-lookup"><span data-stu-id="05e24-120">Messages that were quarantined for high confidence phishing, malware, or by mail flow rules (also known as transport rules) are only available to admins.</span></span> <span data-ttu-id="05e24-121">Para obter mais informações, consulte [Gerenciar arquivos e mensagens em quarentena como administrador no Office 365](manage-quarantined-messages-and-files.md).</span><span class="sxs-lookup"><span data-stu-id="05e24-121">For more information, see [Manage quarantined messages and files as an admin in Office 365](manage-quarantined-messages-and-files.md).</span></span>

- <span data-ttu-id="05e24-122">Você só pode liberar uma mensagem e relatá-la como falso positivo (e não como lixo eletrônico) uma vez.</span><span class="sxs-lookup"><span data-stu-id="05e24-122">You can only release a message and report it as a false positive (not junk) once.</span></span>

## <a name="view-your-quarantined-messages"></a><span data-ttu-id="05e24-123">Visualizar suas mensagens em quarentena</span><span class="sxs-lookup"><span data-stu-id="05e24-123">View your quarantined messages</span></span>

1. <span data-ttu-id="05e24-124">No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.</span><span class="sxs-lookup"><span data-stu-id="05e24-124">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="05e24-125">Você pode classificar os resultados clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="05e24-125">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="05e24-126">Clique em **Modificar colunas** para exibir um máximo de sete colunas.</span><span class="sxs-lookup"><span data-stu-id="05e24-126">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="05e24-127">Os valores padrão são marcados com um asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="05e24-127">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="05e24-128">**Recebido**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05e24-128">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="05e24-129">**Remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05e24-129">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="05e24-130">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05e24-130">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="05e24-131">**Motivo da quarentena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05e24-131">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="05e24-132">**Lançado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05e24-132">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="05e24-133">**Tipo de política**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05e24-133">**Policy type**<sup>\*</sup></span></span>

   - <span data-ttu-id="05e24-134">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="05e24-134">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="05e24-135">**Recipiente**</span><span class="sxs-lookup"><span data-stu-id="05e24-135">**Recipient**</span></span>

   - <span data-ttu-id="05e24-136">**ID da mensagem**</span><span class="sxs-lookup"><span data-stu-id="05e24-136">**Message ID**</span></span>

   - <span data-ttu-id="05e24-137">**Nome da política**</span><span class="sxs-lookup"><span data-stu-id="05e24-137">**Policy name**</span></span>

   - <span data-ttu-id="05e24-138">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="05e24-138">**Size**</span></span>

   - <span data-ttu-id="05e24-139">**Direção**</span><span class="sxs-lookup"><span data-stu-id="05e24-139">**Direction**</span></span>

   <span data-ttu-id="05e24-140">Quando você terminar, clique em **Salvar**, ou clique em **Definido como padrão**.</span><span class="sxs-lookup"><span data-stu-id="05e24-140">When you're finished, click **Save**, or click **Set to default**.</span></span>

3. <span data-ttu-id="05e24-141">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="05e24-141">To filter the results, click **Filter**.</span></span> <span data-ttu-id="05e24-142">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="05e24-142">The available filters are:</span></span>

   - <span data-ttu-id="05e24-143">**Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:</span><span class="sxs-lookup"><span data-stu-id="05e24-143">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="05e24-144">**Hoje**</span><span class="sxs-lookup"><span data-stu-id="05e24-144">**Today**</span></span>

     - <span data-ttu-id="05e24-145">**Próximos 2 dias**</span><span class="sxs-lookup"><span data-stu-id="05e24-145">**Next 2 days**</span></span>

     - <span data-ttu-id="05e24-146">**Próximas 7 semanas**</span><span class="sxs-lookup"><span data-stu-id="05e24-146">**Next 7 days**</span></span>

     - <span data-ttu-id="05e24-147">**Personalizado**: Insira uma **Data de início** e uma **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="05e24-147">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="05e24-148">**Hora recebida**: Insira uma **Data de início** e uma **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="05e24-148">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="05e24-149">**Motivo da quarentena**:</span><span class="sxs-lookup"><span data-stu-id="05e24-149">**Quarantine reason**:</span></span>

     - <span data-ttu-id="05e24-150">**Em massa**</span><span class="sxs-lookup"><span data-stu-id="05e24-150">**Bulk**</span></span>

     - <span data-ttu-id="05e24-151">**Spam**</span><span class="sxs-lookup"><span data-stu-id="05e24-151">**Spam**</span></span>

     - <span data-ttu-id="05e24-152">**Phish** (Em abril de 2020)</span><span class="sxs-lookup"><span data-stu-id="05e24-152">**Phish** (As of April, 2020)</span></span>

   <span data-ttu-id="05e24-153">Para limpar o filtro, clique em **Limpar**.</span><span class="sxs-lookup"><span data-stu-id="05e24-153">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="05e24-154">Para ocultar o submenu do filtro, clique novamente em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="05e24-154">To hide the filter flyout, click **Filter** again.</span></span>

4. <span data-ttu-id="05e24-155">Use **Classificar resultados por** (o botão **ID da mensagem** por padrão) e um valor correspondente para localizar mensagens específicas.</span><span class="sxs-lookup"><span data-stu-id="05e24-155">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="05e24-156">Os curingas não possuem suporte.</span><span class="sxs-lookup"><span data-stu-id="05e24-156">Wildcards aren't supported.</span></span> <span data-ttu-id="05e24-157">Você pode pesquisar pelos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="05e24-157">You can search by the following values:</span></span>

   - <span data-ttu-id="05e24-158">**ID da mensagem**: o identificador globalmente exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="05e24-158">**Message ID**: The globally unique identifier of the message.</span></span> <span data-ttu-id="05e24-159">Se você selecionar uma mensagem na lista, o valor da **ID da mensagem** será exibido no painel **Detalhes** que é exibido.</span><span class="sxs-lookup"><span data-stu-id="05e24-159">If you select a message in the list, the **Message ID** value appears in the **Details** flyout pane that appears.</span></span> <span data-ttu-id="05e24-160">Os administradores podem usar [Rastreamento da mensagem](message-trace-scc.md) para localizar mensagens e seus valores da ID da mensagem correspondentes.</span><span class="sxs-lookup"><span data-stu-id="05e24-160">Admins can use [message trace](message-trace-scc.md) to find messages and their corresponding Message ID values.</span></span>

   - <span data-ttu-id="05e24-161">**Endereço de e-mail do remetente**: o endereço de e-mail de um único remetente.</span><span class="sxs-lookup"><span data-stu-id="05e24-161">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="05e24-162">**Endereço de e-mail do destinatário**: o endereço de e-mail de um único destinatário.</span><span class="sxs-lookup"><span data-stu-id="05e24-162">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="05e24-163">**Assunto**: use todo o assunto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="05e24-163">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="05e24-164">A pesquisa não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="05e24-164">The search is not case-sensitive.</span></span>

   <span data-ttu-id="05e24-165">Depois de ter inserido os critérios da pesquisa, clique em ![Atualizar botão](../media/scc-quarantine-refresh.png) **Atualizar** para filtrar os resultados.</span><span class="sxs-lookup"><span data-stu-id="05e24-165">After you've entered the search criteria, click ![Refresh button](../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="05e24-166">Depois de encontrar uma mensagem específica em quarentena, selecione a mensagem para exibir detalhes sobre ela e execute uma ação (por exemplo: exibir, liberar, fazer download ou excluir a mensagem).</span><span class="sxs-lookup"><span data-stu-id="05e24-166">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

### <a name="export-message-results"></a><span data-ttu-id="05e24-167">Exporte os resultados da mensagem </span><span class="sxs-lookup"><span data-stu-id="05e24-167">Export message results</span></span>

1. <span data-ttu-id="05e24-168">Selecione as mensagens que você está interessado e clique em **Exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="05e24-168">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="05e24-169">Clique em **Sim** na mensagem de confirmação que avisa para manter a janela do navegador aberta.</span><span class="sxs-lookup"><span data-stu-id="05e24-169">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="05e24-170">Quando a exportação estiver pronta, você poderá nomear e escolher o local de download do arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="05e24-170">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

### <a name="view-quarantined-message-details"></a><span data-ttu-id="05e24-171">Exiba detalhes da mensagem em quarentena</span><span class="sxs-lookup"><span data-stu-id="05e24-171">View quarantined message details</span></span>

<span data-ttu-id="05e24-172">Quando você clica em uma mensagem de e-mail na lista, os seguintes detalhes de mensagem são exibidos no painel de submenu **Detalhes**:</span><span class="sxs-lookup"><span data-stu-id="05e24-172">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="05e24-173">**ID da mensagem**: o identificador globalmente exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="05e24-173">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="05e24-174">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="05e24-174">**Sender address**</span></span>

- <span data-ttu-id="05e24-175">**Recebido**: a data e a hora em que a mensagem foi recebida.</span><span class="sxs-lookup"><span data-stu-id="05e24-175">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="05e24-176">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="05e24-176">**Subject**</span></span>

- <span data-ttu-id="05e24-177">**Motivo da quarentena**: mostra se uma mensagem foi identificada como **Spam**, **Em massa** ou (desde abril de 2020) **Phish**.</span><span class="sxs-lookup"><span data-stu-id="05e24-177">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk** or (as of April, 2020) **Phish**.</span></span>

- <span data-ttu-id="05e24-178">**Destinatários**: se a mensagem contiver vários destinatários, você precisará clicar em **Visualizar mensagem** ou **Exibir o cabeçalho da mensagem** para visualizar a lista completa dos destinatários.</span><span class="sxs-lookup"><span data-stu-id="05e24-178">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="05e24-179">**Expira**: a data/hora em que a mensagem será excluída de forma automática e permanente da quarentena.</span><span class="sxs-lookup"><span data-stu-id="05e24-179">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="05e24-180">**Liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem foi liberada.</span><span class="sxs-lookup"><span data-stu-id="05e24-180">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="05e24-181">**Sem liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem não foi liberada.</span><span class="sxs-lookup"><span data-stu-id="05e24-181">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="05e24-182">Tomar medidas quanto aos e-mails em quarentena</span><span class="sxs-lookup"><span data-stu-id="05e24-182">Take action on quarantined email</span></span>

<span data-ttu-id="05e24-183">Depois de selecionar uma mensagem, você tem opções para o que fazer com as mensagens no painel de submenu **Detalhes**:</span><span class="sxs-lookup"><span data-stu-id="05e24-183">After you select a message, you have options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="05e24-184">**Mensagem de liberação**: no painel de submenu que é exibido, escolha se quer o **Relatório de mensagens do Microsoft para ser analisado**.</span><span class="sxs-lookup"><span data-stu-id="05e24-184">**Release message**: In the flyout pane that appears, choose whether to **Report messages to Microsoft for analysis**.</span></span> <span data-ttu-id="05e24-185">Essa opção é selecionada por padrão e relata a mensagem em quarentena incorreta à Microsoft como um falso positivo.</span><span class="sxs-lookup"><span data-stu-id="05e24-185">This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span>

  <span data-ttu-id="05e24-186">Quando terminar, clique em **Liberar mensagens**.</span><span class="sxs-lookup"><span data-stu-id="05e24-186">When you're finished, click **Release messages**.</span></span>

- <span data-ttu-id="05e24-187">**Exibir cabeçalho da mensagem**: escolha este link para visualizar o texto do cabeçalho da mensagem.</span><span class="sxs-lookup"><span data-stu-id="05e24-187">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="05e24-188">Para analisar os valores e campos de cabeçalho em detalhes, copie o texto do cabeçalho da mensagem para a área de transferência e escolha **Analisador de cabeçalho das mensagens da Microsoft** para acessar o Analisador de conectividade remota (clique com o botão direito do mouse e escolha **Abrir em uma nova guia** se não quiser sair do Office 365 para concluir essa tarefa).</span><span class="sxs-lookup"><span data-stu-id="05e24-188">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).</span></span> <span data-ttu-id="05e24-189">Cole o cabeçalho da mensagem na página na seção Analisador do cabeçalho da mensagem e escolha **Analisar cabeçalhos**:</span><span class="sxs-lookup"><span data-stu-id="05e24-189">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="05e24-190">**Visualizar mensagem**: no painel de submenu que é exibido, escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="05e24-190">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="05e24-191">**Visualização da fonte**: mostra a versão HTML do corpo da mensagem com todos os links desabilitados.</span><span class="sxs-lookup"><span data-stu-id="05e24-191">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="05e24-192">**Visualização do texto**: mostra o corpo da mensagem em texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="05e24-192">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="05e24-193">**Mensagem de download**: no painel de submenu que é exibido, clique em **Compreendo os riscos de baixar esta mensagem** para salvar uma cópia local da mensagem no formato .eml.</span><span class="sxs-lookup"><span data-stu-id="05e24-193">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="05e24-194">**Remover da quarentena**: depois de clicar em **Sim** no aviso que é exibido, a mensagem é imediatamente excluída.</span><span class="sxs-lookup"><span data-stu-id="05e24-194">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted.</span></span>

<span data-ttu-id="05e24-195">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="05e24-195">When you're finished, click **Close**.</span></span>

<span data-ttu-id="05e24-196">Se você não liberar ou remover a mensagem, ela será excluída após o término do período de retenção da quarentena padrão.</span><span class="sxs-lookup"><span data-stu-id="05e24-196">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="05e24-197">Tome medidas em várias mensagens quanto aos e-mails em quarentena</span><span class="sxs-lookup"><span data-stu-id="05e24-197">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="05e24-198">Quando você seleciona várias mensagens que estão em quarentena na lista (até 100), o painel de submenu **Ações em massa** é exibido em que você pode realizar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="05e24-198">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="05e24-199">**Mensagens de lançamento**: as opções são as mesmas de quando você libera uma única mensagem, mas não é possível clicar em **Liberar mensagens para destinatários específicos**; você só pode clicar em **Mensagem de lançamento a todos os destinatários** ou **Liberar mensagens para outras pessoas**.</span><span class="sxs-lookup"><span data-stu-id="05e24-199">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="05e24-200">**Excluir mensagens**: depois de clicar em **Sim** no aviso que é exibido, a mensagem é imediatamente excluída sem ser enviada aos destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="05e24-200">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="05e24-201">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="05e24-201">When you're finished, click **Close**.</span></span>
