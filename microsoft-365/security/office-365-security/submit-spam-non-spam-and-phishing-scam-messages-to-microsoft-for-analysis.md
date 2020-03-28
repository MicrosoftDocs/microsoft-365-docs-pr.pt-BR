---
title: Enviar mensagens manualmente para a Microsoft para análise
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'Você e seus usuários podem enviar mensagens de spam falsas negativas e falsos positivos para a Microsoft para análise. '
ms.openlocfilehash: 13b2e42f749b54e0c2b71fe095c077992560ea8c
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032799"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="ec92e-103">Enviar mensagens manualmente para a Microsoft para análise</span><span class="sxs-lookup"><span data-stu-id="ec92e-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="ec92e-104">Se você for um administrador em uma organização do Office 365 com caixas de correio do Exchange Online, recomendamos que você use o portal de envios no centro de conformidade & segurança do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ec92e-104">If you're an admin in an Office 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="ec92e-105">Para obter mais informações, consulte [usar o envio do administrador para enviar spam, phishing, URLs e arquivos suspeitos à Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="ec92e-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="ec92e-106">Pode ser frustrante quando os usuários da sua organização recebem mensagens de lixo eletrônico (spam) ou mensagens de phishing em sua caixa de entrada ou se não recebem uma mensagem de email legítima porque estão marcados como lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="ec92e-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="ec92e-107">Estamos constantemente ajustando os nossos filtros de spam para serem mais precisos.</span><span class="sxs-lookup"><span data-stu-id="ec92e-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="ec92e-108">Você e seus usuários podem ajudar nesse processo enviando falsos positivos (emails satisfatórios marcados como defeituosos), falsos negativos (email incorreto) e mensagens de phishing para a Microsoft para análise.</span><span class="sxs-lookup"><span data-stu-id="ec92e-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="ec92e-109">Devido ao alto volume de envios que recebemos, talvez não seja possível atender a todas as solicitações para análise.</span><span class="sxs-lookup"><span data-stu-id="ec92e-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="ec92e-110">Enviar falsos negativos para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="ec92e-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="ec92e-111">Em vez de usar os procedimentos a seguir para relatar falsos negativos, os usuários do Outlook e do Outlook na Web (anteriormente conhecido como Outlook Web App) podem usar o suplemento de mensagem de relatório para o Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="ec92e-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="ec92e-112">Para obter informações sobre como instalar e usar essa ferramenta, consulte [habilitar o suplemento de mensagem de relatório](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="ec92e-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="ec92e-113">Se você receber uma mensagem que passa pelo filtro de spam que deve ter sido identificada como spam ou phishing, você pode enviar a mensagem para a análise de spam da Microsoft e para as equipes de análise de phishing da Microsoft, conforme apropriado.</span><span class="sxs-lookup"><span data-stu-id="ec92e-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="ec92e-114">Os analistas revisarão a mensagem e a adicionarão aos filtros de todo o serviço se atenderem aos critérios de classificação.</span><span class="sxs-lookup"><span data-stu-id="ec92e-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="ec92e-115">Crie uma nova mensagem de email em branco com um dos seguintes destinatários:</span><span class="sxs-lookup"><span data-stu-id="ec92e-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="ec92e-116">**Lixo eletrônico**:`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="ec92e-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="ec92e-117">**Phishing**:`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="ec92e-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="ec92e-118">Arraste e solte a mensagem de lixo eletrônico ou phishing na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="ec92e-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="ec92e-119">Isso salvará o lixo eletrônico ou a mensagem de phishing como um anexo na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="ec92e-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="ec92e-120">Não copie e cole o conteúdo da mensagem ou encaminhe a mensagem (precisamos da mensagem original para que possamos inspecionar os cabeçalhos da mensagem).</span><span class="sxs-lookup"><span data-stu-id="ec92e-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="ec92e-121">Você pode anexar várias mensagens na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="ec92e-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="ec92e-122">Certifique-se de que todas as mensagens são do mesmo tipo: mensagens golpes de phishing ou mensagens de lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="ec92e-122">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="ec92e-123">Deixe o corpo da nova mensagem vazio.</span><span class="sxs-lookup"><span data-stu-id="ec92e-123">Leave the body of the new message empty.</span></span><li></li><span data-ttu-id="ec92e-124">Use formatos. msg (formato padrão do Outlook) ou. eml (padrão Outlook no formato da Web) para as mensagens anexadas.</span><span class="sxs-lookup"><span data-stu-id="ec92e-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="ec92e-125">Quando tiver terminado, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="ec92e-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="ec92e-126">Os administradores têm várias maneiras diferentes de bloquear mensagens específicas que estão sendo inalgumas identificadas como spam.</span><span class="sxs-lookup"><span data-stu-id="ec92e-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="ec92e-127">Para obter detalhes, consulte [criar listas de remetentes bloqueados no Office 365](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ec92e-127">For details, see [Create blocked sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="ec92e-128">Enviar falsos positivos para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="ec92e-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="ec92e-129">Em vez de usar os procedimentos a seguir para relatar falsos positivos, os usuários do Outlook e do Outlook na Web podem usar o suplemento de mensagem de relatório para o Microsoft Outlook.</span><span class="sxs-lookup"><span data-stu-id="ec92e-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="ec92e-130">Para obter informações sobre como instalar e usar essa ferramenta, consulte [habilitar o suplemento de mensagem de relatório](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="ec92e-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="ec92e-131">Se uma mensagem foi identificada incorretamente como spam, você pode enviar a mensagem para a equipe de análise de spam da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ec92e-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="ec92e-132">Os analistas avaliarão a mensagem e (dependendo dos resultados da análise) os filtros de todo o serviço podem ser ajustados para permitir a mensagem.</span><span class="sxs-lookup"><span data-stu-id="ec92e-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="ec92e-133">Crie uma nova mensagem de email em branco `not_junk@office365.microsoft.com` com o destinatário:</span><span class="sxs-lookup"><span data-stu-id="ec92e-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="ec92e-134">Arraste e solte a mensagem inidentificada na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="ec92e-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="ec92e-135">Isso salvará a mensagem inidentificada como um anexo na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="ec92e-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="ec92e-136">Não copie e cole o conteúdo da mensagem ou encaminhe a mensagem (precisamos da mensagem original para que possamos inspecionar os cabeçalhos da mensagem).</span><span class="sxs-lookup"><span data-stu-id="ec92e-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="ec92e-137">Você pode anexar várias mensagens na nova mensagem.</span><span class="sxs-lookup"><span data-stu-id="ec92e-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="ec92e-138">Certifique-se de que todas as mensagens são do mesmo tipo: mensagens golpes de phishing ou mensagens de lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="ec92e-138">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="ec92e-139">Deixe o corpo da nova mensagem vazio.</span><span class="sxs-lookup"><span data-stu-id="ec92e-139">Leave the body of the new message empty.</span></span><li></li><span data-ttu-id="ec92e-140">Use formatos. msg (formato padrão do Outlook) ou. eml (padrão Outlook no formato da Web) para as mensagens anexadas.</span><span class="sxs-lookup"><span data-stu-id="ec92e-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="ec92e-141">Quando tiver terminado, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="ec92e-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="ec92e-142">Os administradores têm várias maneiras diferentes de permitir que mensagens específicas ignorem a filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="ec92e-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="ec92e-143">Para obter detalhes, consulte [criar listas de remetentes seguros no Office 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="ec92e-143">For details, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="ec92e-144">Criar uma regra de fluxo de email para receber cópias de mensagens relatadas para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="ec92e-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="ec92e-145">Você pode criar uma regra de fluxo de emails (também conhecida como regra de transporte) que procura mensagens de email relatadas à Microsoft usando os métodos descritos neste tópico, e você pode configurar destinatários Cco para receber cópias dessas mensagens relatadas.</span><span class="sxs-lookup"><span data-stu-id="ec92e-145">You can create a mail flow rule (also known as a transport rule) that looks for email messages that are reported to Microsoft by using the methods described in this topic, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="ec92e-146">Você pode criar a regra de fluxo de emails no centro de administração do Exchange (Eat) e no PowerShell (Exchange Online PowerShell para clientes do Office 365; PowerShell de proteção do Exchange Online para clientes autônomos do EOP).</span><span class="sxs-lookup"><span data-stu-id="ec92e-146">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Office 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ec92e-147">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="ec92e-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ec92e-148">Você precisa receber permissões no Exchange Online antes de poder executar estes procedimentos.</span><span class="sxs-lookup"><span data-stu-id="ec92e-148">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="ec92e-149">Especificamente, você precisa receber a função de **regras de transporte** , que é atribuída às funções de gerenciamento da **organização**, **Gerenciamento de conformidade**e gerenciamento de **registros** por padrão.</span><span class="sxs-lookup"><span data-stu-id="ec92e-149">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="ec92e-150">Para saber mais, confira [Gerenciar Grupos de Funções do Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="ec92e-150">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="ec92e-151">Para abrir o Eat no Exchange Online, confira [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="ec92e-151">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="ec92e-152">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ec92e-152">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ec92e-153">Para se conectar ao PowerShell da Proteção do Exchange Online autônoma, confira [Conectar ao PowerShell da Proteção do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="ec92e-153">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ec92e-154">Para obter mais informações sobre regras de fluxo de emails no Exchange Online e EOP autônomos, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="ec92e-154">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="ec92e-155">Regras de fluxo de emails (regras de transporte) no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ec92e-155">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="ec92e-156">Condições e exceções de regra de fluxo de emails (predicados) no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ec92e-156">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="ec92e-157">Ações de regra de fluxo de email no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ec92e-157">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="ec92e-158">Use o Eat para criar uma regra de fluxo de emails para receber cópias de mensagens relatadas</span><span class="sxs-lookup"><span data-stu-id="ec92e-158">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="ec92e-159">No EAC, vá para **Fluxo de emails** \> **Regras**.</span><span class="sxs-lookup"><span data-stu-id="ec92e-159">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="ec92e-160">Clique em **Adicionar** ![ícone](../../media/ITPro-EAC-AddIcon.png) de adição e selecione **criar uma nova regra**.</span><span class="sxs-lookup"><span data-stu-id="ec92e-160">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="ec92e-161">Na página **nova regra** que é aberta, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="ec92e-161">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="ec92e-162">**Name**: Insira um nome exclusivo e descritivo para a regra.</span><span class="sxs-lookup"><span data-stu-id="ec92e-162">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="ec92e-163">Por exemplo, as mensagens Cco relatadas para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ec92e-163">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="ec92e-164">Clique em **mais opções**.</span><span class="sxs-lookup"><span data-stu-id="ec92e-164">Click **More Options**.</span></span>

   - <span data-ttu-id="ec92e-165">**Aplicar esta regra se**: selecione **o** \> **endereço do destinatário inclui qualquer uma destas palavras**: na caixa de diálogo **especificar palavras ou expressões** que aparece, insira um dos seguintes valores, clique em **Adicionar** ![ícone](../../media/ITPro-EAC-AddIcon.png)de adição e repita até inserir todos os valores.</span><span class="sxs-lookup"><span data-stu-id="ec92e-165">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="ec92e-166">Para editar uma entrada, selecione-a e **Edit** ![clique em Editar](../../media/ITPro-EAC-EditIcon.png)ícone de edição.</span><span class="sxs-lookup"><span data-stu-id="ec92e-166">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="ec92e-167">Para remover uma entrada, selecione-a e **Remove** ![clique em Remover](../../media/ITPro-EAC-DeleteIcon.png)ícone Remover.</span><span class="sxs-lookup"><span data-stu-id="ec92e-167">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="ec92e-168">Quando tiver concluído, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec92e-168">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="ec92e-169">**Faça o seguinte**: selecione **Adicionar destinatários** \> **à caixa Cco**.</span><span class="sxs-lookup"><span data-stu-id="ec92e-169">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="ec92e-170">Na caixa de diálogo exibida, localize e selecione os destinatários que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="ec92e-170">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="ec92e-171">Quando tiver concluído, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec92e-171">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="ec92e-172">Você pode fazer seleções adicionais para auditar a regra, testar a regra, ativar a regra durante um período de tempo específico e outras configurações.</span><span class="sxs-lookup"><span data-stu-id="ec92e-172">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="ec92e-173">Recomendamos testar a regra antes de aplicá-la.</span><span class="sxs-lookup"><span data-stu-id="ec92e-173">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="ec92e-174">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ec92e-174">When you're finished, click **Save**.</span></span>

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="ec92e-175">Use o PowerShell para criar uma regra de fluxo de emails para receber cópias de mensagens relatadas</span><span class="sxs-lookup"><span data-stu-id="ec92e-175">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="ec92e-176">Este exemplo cria uma nova regra de fluxo de emails chamada Cco mensagens relatadas à Microsoft que procura mensagens de email relatadas à Microsoft usando os métodos descritos neste tópico e adiciona os usuários laura@contoso.com e julia@contoso.com como destinatários Cco.</span><span class="sxs-lookup"><span data-stu-id="ec92e-176">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="ec92e-177">Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="ec92e-177">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="ec92e-178">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="ec92e-178">How do you know this worked?</span></span>

<span data-ttu-id="ec92e-179">Para verificar se você configurou uma regra de fluxo de emails para receber cópias de mensagens relatadas, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="ec92e-179">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="ec92e-180">No Eat, vá para **regras** \> de fluxo \> de **emails** selecione \> a regra clique em](../../media/ITPro-EAC-EditIcon.png) **Editar** ![ícone de edição e verifique as configurações.</span><span class="sxs-lookup"><span data-stu-id="ec92e-180">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="ec92e-181">No PowerShell, execute o seguinte comando para verificar as configurações:</span><span class="sxs-lookup"><span data-stu-id="ec92e-181">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="ec92e-182">Envie uma mensagem de teste para um dos endereços de email de relatório e verifique os resultados.</span><span class="sxs-lookup"><span data-stu-id="ec92e-182">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
