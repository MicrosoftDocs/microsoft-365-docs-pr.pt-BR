---
title: Gerenciar arquivos e mensagens em quarentena como um administrador
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
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá como os administradores podem gerenciar mensagens e arquivos em quarentena para usuários no Office 365.
ms.openlocfilehash: e69887b54b3e892775c16fa3e306da3b17ab7db3
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036168"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator"></a><span data-ttu-id="e1e31-103">Gerenciar arquivos e mensagens em quarentena como um administrador</span><span class="sxs-lookup"><span data-stu-id="e1e31-103">Manage quarantined messages and files as an administrator</span></span>

<span data-ttu-id="e1e31-104">A quarentena contém mensagens potencialmente perigosas ou indesejadas nas organizações que utilizam Microsoft 365 com caixas de correio do Exchange Online ou Exchange Online Protection (EOP) de organizações autônomas, sem as caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e1e31-104">Quarantine holds potentially dangerous or unwanted messages in Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes.</span></span> <span data-ttu-id="e1e31-105">Para obter mais informações, consulte [Quarentena no Office 365](quarantine-email-messages.md).</span><span class="sxs-lookup"><span data-stu-id="e1e31-105">For more information, see [Quarantine in Office 365](quarantine-email-messages.md).</span></span>

<span data-ttu-id="e1e31-106">Os administradores podem exibir, liberar e excluir todos os tipos de mensagens em quarentena para todos os usuários.</span><span class="sxs-lookup"><span data-stu-id="e1e31-106">Admins can view, release, and delete all types of quarantined messages for all users.</span></span> <span data-ttu-id="e1e31-107">Somente os administradores podem gerenciar mensagens que foram colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (também conhecidas como regras de transporte).</span><span class="sxs-lookup"><span data-stu-id="e1e31-107">Only admins can manage messages that were quarantined as malware, high confidence phishing, or as a result of mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="e1e31-108">Os administradores também podem relatar falsos positivos para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e1e31-108">Admins can also report false positives to Microsoft.</span></span>

<span data-ttu-id="e1e31-109">Administradores nas organizações com a proteção avançada contra ameaças do Office 365 (ATP) também podem exibir, baixar e excluir arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e1e31-109">Admins in organizations with Office 365 Advance Threat Protection (ATP) can also view, download, and delete quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="e1e31-110">Você exibir e gerenciar mensagens em quarentena no centro de conformidade & segurança ou no PowerShell (PowerShell do Exchange Online para clientes do Microsoft 365; PowerShell de proteção do Exchange Online para clientes autônomos do EOP).</span><span class="sxs-lookup"><span data-stu-id="e1e31-110">You view and manage quarantined messages in the Security & Compliance Center or in PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e1e31-111">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="e1e31-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e1e31-112">Para abrir o Centro de Conformidade e Segurança, acesse <https://protection.office.com>.</span><span class="sxs-lookup"><span data-stu-id="e1e31-112">To open the Security & Compliance Center, go to <https://protection.office.com>.</span></span> <span data-ttu-id="e1e31-113">Para abrir a página Quarentena imediatamente, vá para <https://protection.office.com/quarantine>.</span><span class="sxs-lookup"><span data-stu-id="e1e31-113">To open the Quarantine page directly, go to <https://protection.office.com/quarantine>.</span></span>

- <span data-ttu-id="e1e31-114">Para se conectar ao Exchange Online PowerShell, consulte [Conectar ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e1e31-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e1e31-115">Para se conectar ao PowerShell do Exchange Online Protection, confira [conectar-se ao PowerShell do Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="e1e31-115">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e1e31-116">Você precisa receber permissões antes de gerenciar a quarentena como um administrador. As permissões são controladas pela função de **quarentena** no centro de conformidade de & de segurança.</span><span class="sxs-lookup"><span data-stu-id="e1e31-116">You need to be assigned permissions before you can manage the quarantine as an admin. The permissions are controlled by the **Quarantine** role in the Security & Compliance Center.</span></span> <span data-ttu-id="e1e31-117">Por padrão, essa função é atribuída aos grupos de função **Gerenciamento da organização** (administradores globais), **administrador de quarentena**e administrador de **segurança** no centro de conformidade do & de segurança.</span><span class="sxs-lookup"><span data-stu-id="e1e31-117">By default, this role is assigned to the **Organization Management** (Global admins), **Quarantine Administrator**, and **Security Administrator** role groups in the Security & Compliance Center.</span></span> <span data-ttu-id="e1e31-118">Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e1e31-118">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="e1e31-119">As mensagens em quarentena são mantidas por um período de tempo padrão antes de serem excluídas automaticamente:</span><span class="sxs-lookup"><span data-stu-id="e1e31-119">Quarantined messages are retained for a default period of time before they're automatically deleted:</span></span>

  - <span data-ttu-id="e1e31-120">Mensagens colocadas em quarentena por políticas antispam (spam, phishing e email em massa): 30 dias.</span><span class="sxs-lookup"><span data-stu-id="e1e31-120">Messages quarantined by anti-spam policies (spam, phishing, and bulk email): 30 days.</span></span> <span data-ttu-id="e1e31-121">Este é o valor padrão e máximo.</span><span class="sxs-lookup"><span data-stu-id="e1e31-121">This is the default and maximum value.</span></span> <span data-ttu-id="e1e31-122">Para configurar esse valor, consulte [Configure anti-spam Policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e1e31-122">To configure this value, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

1. <span data-ttu-id="e1e31-123">Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global (ou funções apropriadas de segurança & central de conformidade) em sua organização, entre e [vá para o centro de conformidade de & de segurança](../../compliance/go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e1e31-123">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

  - <span data-ttu-id="e1e31-124">Mensagens que contêm malware: 15 dias.</span><span class="sxs-lookup"><span data-stu-id="e1e31-124">Messages that contain malware: 15 days.</span></span>

  <span data-ttu-id="e1e31-125">Quando uma mensagem expira da quarentena, não é possível recuperá-la.</span><span class="sxs-lookup"><span data-stu-id="e1e31-125">When a message expires from quarantine, you can't recover it.</span></span>

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a><span data-ttu-id="e1e31-126">Usar o centro de conformidade de & de segurança para gerenciar mensagens de email em quarentena</span><span class="sxs-lookup"><span data-stu-id="e1e31-126">Use the Security & Compliance Center to manage quarantined email messages</span></span>

### <a name="view-quarantined-email"></a><span data-ttu-id="e1e31-127">Exibir email em quarentena</span><span class="sxs-lookup"><span data-stu-id="e1e31-127">View quarantined email</span></span>

1. <span data-ttu-id="e1e31-128">No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-128">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="e1e31-129">Verifique se a **exibição em quarentena** está definida com o valor padrão **email**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-129">Verify that **View quarantined** is set to the default value **email**.</span></span>

3. <span data-ttu-id="e1e31-130">Você pode classificar os resultados clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="e1e31-130">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="e1e31-131">Clique em **Modificar colunas** para exibir um máximo de sete colunas.</span><span class="sxs-lookup"><span data-stu-id="e1e31-131">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="e1e31-132">Os valores padrão são marcados com um asterisco (<sup>\*</sup>):</span><span class="sxs-lookup"><span data-stu-id="e1e31-132">The default values are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="e1e31-133">**Recebido**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e1e31-133">**Received**<sup>\*</sup></span></span>

   - <span data-ttu-id="e1e31-134">**Remetente**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e1e31-134">**Sender**<sup>\*</sup></span></span>

   - <span data-ttu-id="e1e31-135">**Assunto**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e1e31-135">**Subject**<sup>\*</sup></span></span>

   - <span data-ttu-id="e1e31-136">**Motivo da quarentena**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e1e31-136">**Quarantine reason**<sup>\*</sup></span></span>

   - <span data-ttu-id="e1e31-137">**Lançado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e1e31-137">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="e1e31-138">**Tipo de política**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e1e31-138">**Policy type**<sup>\*</sup></span></span>

1. <span data-ttu-id="e1e31-139">Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global (ou funções apropriadas de segurança & central de conformidade) em sua organização, entre e [vá para o centro de conformidade de & de segurança](../../compliance/go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e1e31-139">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

   - <span data-ttu-id="e1e31-140">**Recipiente**</span><span class="sxs-lookup"><span data-stu-id="e1e31-140">**Recipient**</span></span>

   - <span data-ttu-id="e1e31-141">**ID da mensagem**</span><span class="sxs-lookup"><span data-stu-id="e1e31-141">**Message ID**</span></span>

   - <span data-ttu-id="e1e31-142">**Nome da política**</span><span class="sxs-lookup"><span data-stu-id="e1e31-142">**Policy name**</span></span>

   - <span data-ttu-id="e1e31-143">**Tamanho**</span><span class="sxs-lookup"><span data-stu-id="e1e31-143">**Size**</span></span>

   - <span data-ttu-id="e1e31-144">**Direção**</span><span class="sxs-lookup"><span data-stu-id="e1e31-144">**Direction**</span></span>

   <span data-ttu-id="e1e31-145">Quando você terminar, clique em **Salvar**, ou clique em **Definido como padrão**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-145">When you're finished, click **Save**, or click **Set to default**.</span></span>

4. <span data-ttu-id="e1e31-146">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-146">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e1e31-147">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="e1e31-147">The available filters are:</span></span>

   - <span data-ttu-id="e1e31-148">**Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:</span><span class="sxs-lookup"><span data-stu-id="e1e31-148">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="e1e31-149">**Hoje**</span><span class="sxs-lookup"><span data-stu-id="e1e31-149">**Today**</span></span>

     - <span data-ttu-id="e1e31-150">**Próximos 2 dias**</span><span class="sxs-lookup"><span data-stu-id="e1e31-150">**Next 2 days**</span></span>

     - <span data-ttu-id="e1e31-151">**Próximas 7 semanas**</span><span class="sxs-lookup"><span data-stu-id="e1e31-151">**Next 7 days**</span></span>

     - <span data-ttu-id="e1e31-152">**Personalizado**: Insira uma **Data de início** e uma **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-152">**Custom**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="e1e31-153">**Hora recebida**: Insira uma **Data de início** e uma **Data de término**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-153">**Received time**: Enter a **Start date** and **End date**.</span></span>

   - <span data-ttu-id="e1e31-154">**Motivo da quarentena**:</span><span class="sxs-lookup"><span data-stu-id="e1e31-154">**Quarantine reason**:</span></span>

     - <span data-ttu-id="e1e31-155">**Política**: a mensagem correspondeu às condições de uma regra de fluxo de emails (também conhecida como regra de transporte).</span><span class="sxs-lookup"><span data-stu-id="e1e31-155">**Policy**: The message matched the conditions of a mail flow rule (also known as a transport rule).</span></span>

     - <span data-ttu-id="e1e31-156">**Em massa**</span><span class="sxs-lookup"><span data-stu-id="e1e31-156">**Bulk**</span></span>

     - <span data-ttu-id="e1e31-157">**Phish**</span><span class="sxs-lookup"><span data-stu-id="e1e31-157">**Phish**</span></span>

     - <span data-ttu-id="e1e31-158">**Malware**</span><span class="sxs-lookup"><span data-stu-id="e1e31-158">**Malware**</span></span>

     - <span data-ttu-id="e1e31-159">**Spam**</span><span class="sxs-lookup"><span data-stu-id="e1e31-159">**Spam**</span></span>

     - <span data-ttu-id="e1e31-160">**Phishing de alta confiança**</span><span class="sxs-lookup"><span data-stu-id="e1e31-160">**High Confidence Phish**</span></span>

   - <span data-ttu-id="e1e31-161">**Destinatário do email**: todos os usuários ou apenas as mensagens enviadas a você.</span><span class="sxs-lookup"><span data-stu-id="e1e31-161">**Email recipient**: All users or only messages sent to you.</span></span> <span data-ttu-id="e1e31-162">Os usuários finais só podem gerenciar mensagens em quarentena enviadas para eles.</span><span class="sxs-lookup"><span data-stu-id="e1e31-162">End users can only manage quarantined messages sent to them.</span></span>

   <span data-ttu-id="e1e31-163">Para limpar o filtro, clique em **Limpar**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-163">To clear the filter, click **Clear**.</span></span> <span data-ttu-id="e1e31-164">Para ocultar o submenu do filtro, clique novamente em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-164">To hide the filter flyout, click **Filter** again.</span></span>

5. <span data-ttu-id="e1e31-165">Use **Classificar resultados por** (o botão **ID da mensagem** por padrão) e um valor correspondente para localizar mensagens específicas.</span><span class="sxs-lookup"><span data-stu-id="e1e31-165">Use **Sort results by** (the **Message ID** button by default) and a corresponding value to find specific messages.</span></span> <span data-ttu-id="e1e31-166">Os curingas não possuem suporte.</span><span class="sxs-lookup"><span data-stu-id="e1e31-166">Wildcards aren't supported.</span></span> <span data-ttu-id="e1e31-167">Você pode pesquisar pelos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e1e31-167">You can search by the following values:</span></span>

   - <span data-ttu-id="e1e31-168">**ID da mensagem**: o identificador globalmente exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="e1e31-168">**Message ID**: The globally unique identifier of the message.</span></span>

        <span data-ttu-id="e1e31-169">Por exemplo, você usou o [rastreamento de mensagens](message-trace-scc.md) para procurar uma mensagem que foi enviada a um usuário na sua organização, e você determina que a mensagem foi colocada em quarentena em vez de distribuída.</span><span class="sxs-lookup"><span data-stu-id="e1e31-169">For example, you used [message trace](message-trace-scc.md) to look for a message that was sent to a user in your organization, and you determine that the message was quarantined instead of delivered.</span></span> <span data-ttu-id="e1e31-170">Certifique-se de incluir o valor completo da ID da mensagem, que pode incluir colchetes angulares (\<\>).</span><span class="sxs-lookup"><span data-stu-id="e1e31-170">Be sure to include the full message ID value, which might include angle brackets (\<\>).</span></span> <span data-ttu-id="e1e31-171">Por exemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span><span class="sxs-lookup"><span data-stu-id="e1e31-171">For example: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.</span></span>

   - <span data-ttu-id="e1e31-172">**Endereço de e-mail do remetente**: o endereço de e-mail de um único remetente.</span><span class="sxs-lookup"><span data-stu-id="e1e31-172">**Sender email address**: A single sender's email address.</span></span>

   - <span data-ttu-id="e1e31-173">**Endereço de e-mail do destinatário**: o endereço de e-mail de um único destinatário.</span><span class="sxs-lookup"><span data-stu-id="e1e31-173">**Recipient email address**: A single recipient's email address.</span></span>

   - <span data-ttu-id="e1e31-174">**Assunto**: use todo o assunto da mensagem.</span><span class="sxs-lookup"><span data-stu-id="e1e31-174">**Subject**: Use the entire subject of the message.</span></span> <span data-ttu-id="e1e31-175">A pesquisa não diferencia maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="e1e31-175">The search is not case-sensitive.</span></span>

   <span data-ttu-id="e1e31-176">Depois de ter inserido os critérios da pesquisa, clique em ![Atualizar botão](../../media/scc-quarantine-refresh.png) **Atualizar** para filtrar os resultados.</span><span class="sxs-lookup"><span data-stu-id="e1e31-176">After you've entered the search criteria, click ![Refresh button](../../media/scc-quarantine-refresh.png) **Refresh** to filter the results.</span></span>

<span data-ttu-id="e1e31-177">Depois de encontrar uma mensagem específica em quarentena, selecione a mensagem para exibir detalhes sobre ela e execute uma ação (por exemplo: exibir, liberar, fazer download ou excluir a mensagem).</span><span class="sxs-lookup"><span data-stu-id="e1e31-177">After you find a specific quarantined message, select the message to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-message-results"></a><span data-ttu-id="e1e31-178">Exporte os resultados da mensagem </span><span class="sxs-lookup"><span data-stu-id="e1e31-178">Export message results</span></span>

1. <span data-ttu-id="e1e31-179">Selecione as mensagens que você está interessado e clique em **Exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-179">Select the messages you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="e1e31-180">Clique em **Sim** na mensagem de confirmação que avisa para manter a janela do navegador aberta.</span><span class="sxs-lookup"><span data-stu-id="e1e31-180">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="e1e31-181">Quando a exportação estiver pronta, você poderá nomear e escolher o local de download do arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="e1e31-181">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-message-details"></a><span data-ttu-id="e1e31-182">Exiba detalhes da mensagem em quarentena</span><span class="sxs-lookup"><span data-stu-id="e1e31-182">View quarantined message details</span></span>

<span data-ttu-id="e1e31-183">Quando você clica em uma mensagem de e-mail na lista, os seguintes detalhes de mensagem são exibidos no painel de submenu **Detalhes**:</span><span class="sxs-lookup"><span data-stu-id="e1e31-183">When you select an email message in the list, the following message details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e1e31-184">**ID da mensagem**: o identificador globalmente exclusivo da mensagem.</span><span class="sxs-lookup"><span data-stu-id="e1e31-184">**Message ID**: The globally unique identifier for the message.</span></span>

- <span data-ttu-id="e1e31-185">**Endereço do remetente**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-185">**Sender address**</span></span>

- <span data-ttu-id="e1e31-186">**Recebido**: a data e a hora em que a mensagem foi recebida.</span><span class="sxs-lookup"><span data-stu-id="e1e31-186">**Received**: The date/time when the message was received.</span></span>

- <span data-ttu-id="e1e31-187">**Assunto**</span><span class="sxs-lookup"><span data-stu-id="e1e31-187">**Subject**</span></span>

- <span data-ttu-id="e1e31-188">**Motivo da quarentena**: mostra se uma mensagem foi identificada como **spam**, **em massa**, **Phish**, corresponde a uma regra de fluxo de emails (**regra de transporte**) ou foi identificada como contendo **malware**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-188">**Quarantine reason**: Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule (**Transport rule**), or was identified as containing **Malware**.</span></span>

- <span data-ttu-id="e1e31-189">**Destinatários**: se a mensagem contiver vários destinatários, você precisará clicar em **Visualizar mensagem** ou **Exibir o cabeçalho da mensagem** para visualizar a lista completa dos destinatários.</span><span class="sxs-lookup"><span data-stu-id="e1e31-189">**Recipients**: If the message contains multiple recipients, you need to click **Preview message** or **View message header** to see the complete list of recipients.</span></span>

- <span data-ttu-id="e1e31-190">**Expira**: a data/hora em que a mensagem será excluída de forma automática e permanente da quarentena.</span><span class="sxs-lookup"><span data-stu-id="e1e31-190">**Expires**: The date/time when the message will be automatically and permanently deleted from quarantine.</span></span>

- <span data-ttu-id="e1e31-191">**Liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem foi liberada.</span><span class="sxs-lookup"><span data-stu-id="e1e31-191">**Released to**: All email addresses (if any) to which the message has been released.</span></span>

- <span data-ttu-id="e1e31-192">**Sem liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem não foi liberada.</span><span class="sxs-lookup"><span data-stu-id="e1e31-192">**Not yet released to**: All email addresses (if any) to which the message has not yet been released.</span></span>

### <a name="take-action-on-quarantined-email"></a><span data-ttu-id="e1e31-193">Tomar medidas quanto aos e-mails em quarentena</span><span class="sxs-lookup"><span data-stu-id="e1e31-193">Take action on quarantined email</span></span>

<span data-ttu-id="e1e31-194">Após selecionar uma mensagem, você tem várias opções para o que fazer com as mensagens no painel de submenu **detalhes** :</span><span class="sxs-lookup"><span data-stu-id="e1e31-194">After you select a message, you have several options for what to do with the messages in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e1e31-195">**Mensagem de lançamento**: no painel de submenus exibido, escolha as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="e1e31-195">**Release message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="e1e31-196">**Relatar mensagens à Microsoft para análise**: isso é selecionado por padrão e relata a mensagem em quarentena errada à Microsoft como um falso positivo.</span><span class="sxs-lookup"><span data-stu-id="e1e31-196">**Report messages to Microsoft for analysis**: This is selected by default, and reports the erroneously quarantined message to Microsoft as a false positive.</span></span> <span data-ttu-id="e1e31-197">Se a mensagem foi colocada em quarentena como spam, em massa, phishing ou com malware, a mensagem também é relatada para a equipe de análise de spam da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e1e31-197">If the message was quarantined as spam, bulk, phishing, or containing malware, the message is also reported to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="e1e31-198">Dependendo da análise, as regras de filtro de spam de todo o serviço podem ser ajustadas para permitir a mensagem.</span><span class="sxs-lookup"><span data-stu-id="e1e31-198">Depending on their analysis, the service-wide spam filter rules might be be adjusted to allow the message through.</span></span>

  - <span data-ttu-id="e1e31-199">Escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="e1e31-199">Choose one of the following options:</span></span>

    - <span data-ttu-id="e1e31-200">**Liberar mensagens para todos os destinatários**</span><span class="sxs-lookup"><span data-stu-id="e1e31-200">**Release messages to all recipients**</span></span>

    - <span data-ttu-id="e1e31-201">**Liberar mensagens para destinatários específicos**</span><span class="sxs-lookup"><span data-stu-id="e1e31-201">**Release messages to specific recipients**</span></span>

    - <span data-ttu-id="e1e31-202">**Liberar mensagens para outras pessoas**</span><span class="sxs-lookup"><span data-stu-id="e1e31-202">**Release messages to other people**</span></span>

  <span data-ttu-id="e1e31-203">Quando terminar, clique em **Liberar mensagens**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-203">When you're finished, click **Release messages**.</span></span>

  <span data-ttu-id="e1e31-204">Observações sobre o lançamento de mensagens:</span><span class="sxs-lookup"><span data-stu-id="e1e31-204">Notes about releasing messages:</span></span>

  - <span data-ttu-id="e1e31-205">Você não pode liberar uma mensagem para o mesmo destinatário mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="e1e31-205">You can't release a message to the same recipient more than once.</span></span>

  - <span data-ttu-id="e1e31-206">Somente os destinatários que não receberam a mensagem aparecerão na lista de possíveis destinatários.</span><span class="sxs-lookup"><span data-stu-id="e1e31-206">Only recipients who haven't received the message will appear in the list of potential recipients.</span></span>

- <span data-ttu-id="e1e31-207">**Exibir cabeçalho da mensagem**: escolha este link para visualizar o texto do cabeçalho da mensagem.</span><span class="sxs-lookup"><span data-stu-id="e1e31-207">**View message header**: Choose this link to see the message header text.</span></span> <span data-ttu-id="e1e31-208">Para analisar os valores e campos de cabeçalho em detalhes, copie o texto do cabeçalho da mensagem para a área de transferência e, em seguida, escolha **Analisador de Cabeçalhos de Mensagens da Microsoft** para acessar o Analisar de Conectividade Remota (clique com o botão direito e escolha **Abrir em uma nova guia** se não quiser deixar o Microsoft 365 para concluir essa tarefa).</span><span class="sxs-lookup"><span data-stu-id="e1e31-208">To analyze the header fields and values in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Microsoft 365 to complete this task).</span></span> <span data-ttu-id="e1e31-209">Cole o cabeçalho da mensagem na página na seção Analisador do cabeçalho da mensagem e escolha **Analisar cabeçalhos**:</span><span class="sxs-lookup"><span data-stu-id="e1e31-209">Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**:</span></span>

- <span data-ttu-id="e1e31-210">**Visualizar mensagem**: no painel de submenu que é exibido, escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="e1e31-210">**Preview message**: In the flyout pane that appears, choose one of the following options:</span></span>

  - <span data-ttu-id="e1e31-211">**Visualização da fonte**: mostra a versão HTML do corpo da mensagem com todos os links desabilitados.</span><span class="sxs-lookup"><span data-stu-id="e1e31-211">**Source view**: Shows the HTML version of the message body with all links disabled.</span></span>
  
  - <span data-ttu-id="e1e31-212">**Visualização do texto**: mostra o corpo da mensagem em texto sem formatação.</span><span class="sxs-lookup"><span data-stu-id="e1e31-212">**Text view**: Shows the message body in plain text.</span></span>

- <span data-ttu-id="e1e31-213">**Remover da quarentena**: depois de clicar em **Sim** no aviso exibido, a mensagem será excluída imediatamente sem ser enviada aos destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="e1e31-213">**Remove from quarantine**: After you click **Yes** in the warning that appears, the message is immediately deleted without being sent to the original recipients.</span></span>

- <span data-ttu-id="e1e31-214">**Mensagem de download**: no painel de submenu que é exibido, clique em **Compreendo os riscos de baixar esta mensagem** para salvar uma cópia local da mensagem no formato .eml.</span><span class="sxs-lookup"><span data-stu-id="e1e31-214">**Download message**: In the flyout pane that appears, select **I understand the risks from downloading this message** to save a local copy of the message in .eml format.</span></span>

- <span data-ttu-id="e1e31-215">**Enviar mensagem**: no painel de submenu que aparece, escolha as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="e1e31-215">**Submit message**: In the flyout pane that appears, choose the following options:</span></span>

  - <span data-ttu-id="e1e31-216">**Tipo de objeto**: **email** (padrão), **URL**ou **anexo**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-216">**Object type**: **Email** (default), **URL**, or **Attachment**.</span></span>

  - <span data-ttu-id="e1e31-217">**Formato de envio**: **ID de mensagem de rede** (padrão, com o valor correspondente na caixa ID de mensagem de **rede** ) ou **arquivo** (navegue até um arquivo. eml ou. msg local).</span><span class="sxs-lookup"><span data-stu-id="e1e31-217">**Submission format**: **Network Message ID** (default, with the corresponding value in the **Network Message ID** box) or **File** (browse to a local .eml or .msg file).</span></span> <span data-ttu-id="e1e31-218">Observe que, se você selecionar **arquivo** e, em seguida, selecionar **ID de mensagem de rede**, o valor inicialmente será desperdido.</span><span class="sxs-lookup"><span data-stu-id="e1e31-218">Note that if you select **File** and then select **Network Message ID**, the initially value is gone.</span></span>

  - <span data-ttu-id="e1e31-219">**Destinatários**: digite no leasing um destinatário original da mensagem ou clique em **selecionar tudo** para identificar todos os destinatários.</span><span class="sxs-lookup"><span data-stu-id="e1e31-219">**Recipients**: Type at lease one original recipient of the message, or click **Select All** to identify all recipients.</span></span> <span data-ttu-id="e1e31-220">Você também pode clicar em **selecionar todos** e, em seguida, remover seletivamente destinatários individuais.</span><span class="sxs-lookup"><span data-stu-id="e1e31-220">You can also click **Select All** and then selectively remove individual recipients.</span></span>

  - <span data-ttu-id="e1e31-221">**Motivo do envio**: **não deve ter sido bloqueado** (padrão) ou **deve ter sido bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-221">**Reason for submission**: **Should not have been blocked** (default) or **Should have been blocked**.</span></span>

  <span data-ttu-id="e1e31-222">Quando tiver concluído, clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-222">When you're finished, click **Submit**.</span></span>

<span data-ttu-id="e1e31-223">Se você não liberar ou remover a mensagem, ela será excluída após o término do período de retenção da quarentena padrão.</span><span class="sxs-lookup"><span data-stu-id="e1e31-223">If you don't release or remove the message, it will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="take-action-on-multiple-quarantined-email-messages"></a><span data-ttu-id="e1e31-224">Tome medidas em várias mensagens quanto aos e-mails em quarentena</span><span class="sxs-lookup"><span data-stu-id="e1e31-224">Take action on multiple quarantined email messages</span></span>

<span data-ttu-id="e1e31-225">Quando você seleciona várias mensagens que estão em quarentena na lista (até 100), o painel de submenu **Ações em massa** é exibido em que você pode realizar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="e1e31-225">When you select multiple quarantined messages in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="e1e31-226">**Mensagens de lançamento**: as opções são as mesmas de quando você libera uma única mensagem, mas não é possível clicar em **Liberar mensagens para destinatários específicos**; você só pode clicar em **Mensagem de lançamento a todos os destinatários** ou **Liberar mensagens para outras pessoas**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-226">**Release messages**: The options are the same as when you release a single message, except you can't select **Release messages to specific recipients**; you can only select **Release message to all recipients** or **Release messages to other people**.</span></span>

- <span data-ttu-id="e1e31-227">**Excluir mensagens**: depois de clicar em **Sim** no aviso que é exibido, a mensagem é imediatamente excluída sem ser enviada aos destinatários originais.</span><span class="sxs-lookup"><span data-stu-id="e1e31-227">**Delete messages**:  After you click **Yes** in the warning that appears, the message are immediately deleted without being sent to the original recipients.</span></span>

<span data-ttu-id="e1e31-228">Quando terminar, clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-228">When you're finished, click **Close**.</span></span>

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a><span data-ttu-id="e1e31-229">Somente ATP: usar o centro de conformidade de & de segurança para gerenciar arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="e1e31-229">ATP Only: Use the Security & Compliance Center to manage quarantined files</span></span>

> [!NOTE]
> <span data-ttu-id="e1e31-230">Os procedimentos para arquivos em quarentena nesta seção estão disponíveis somente para assinantes do plano ATP 1 e do plano 2.</span><span class="sxs-lookup"><span data-stu-id="e1e31-230">The procedures for quarantined files in this section are available only to ATP Plan 1 and Plan 2 subscribers.</span></span>

<span data-ttu-id="e1e31-231">Em organizações com ATP, os administradores podem gerenciar arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e1e31-231">In organizations with ATP, admins can managed quarantined files in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

### <a name="view-quarantined-files"></a><span data-ttu-id="e1e31-232">Exibir arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="e1e31-232">View quarantined files</span></span>

1. <span data-ttu-id="e1e31-233">No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-233">In the Security and Compliance Center, go to **Threat Management** \> **Review** \> **Quarantine**.</span></span>

2. <span data-ttu-id="e1e31-234">Altere o **modo de exibição colocado em quarentena** para os **arquivos**de valor padrão.</span><span class="sxs-lookup"><span data-stu-id="e1e31-234">Change **View quarantined** to the default value **files**.</span></span> <span data-ttu-id="e1e31-235">Você pode classificar em um campo clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="e1e31-235">You can sort on a field by clicking on an available column header.</span></span>

3. <span data-ttu-id="e1e31-236">Você pode classificar os resultados clicando em um cabeçalho de coluna disponível.</span><span class="sxs-lookup"><span data-stu-id="e1e31-236">You can sort the results by clicking on an available column header.</span></span> <span data-ttu-id="e1e31-237">Clique em **Modificar colunas** para exibir um máximo de sete colunas.</span><span class="sxs-lookup"><span data-stu-id="e1e31-237">Click **Modify columns** to show a maximum of seven columns.</span></span> <span data-ttu-id="e1e31-238">As colunas padrão são marcadas com um asterisco<sup>\*</sup>():</span><span class="sxs-lookup"><span data-stu-id="e1e31-238">The default columns are marked with an asterisk (<sup>\*</sup>):</span></span>

   - <span data-ttu-id="e1e31-239">**Usuário**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e1e31-239">**User**<sup>\*</sup></span></span>

   - <span data-ttu-id="e1e31-240">**Alocações**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e1e31-240">**Location**<sup>\*</sup></span></span>

   - <span data-ttu-id="e1e31-241">**Nome do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e1e31-241">**File name**<sup>\*</sup></span></span>

   - <span data-ttu-id="e1e31-242">**URL do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e1e31-242">**File URL**<sup>\*</sup></span></span>

   - <span data-ttu-id="e1e31-243">**Tamanho do arquivo**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e1e31-243">**File Size**<sup>\*</sup></span></span>

   - <span data-ttu-id="e1e31-244">**Expira**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e1e31-244">**Expires**<sup>\*</sup></span></span>

   - <span data-ttu-id="e1e31-245">**Lançado?**<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e1e31-245">**Released?**<sup>\*</sup></span></span>

   - <span data-ttu-id="e1e31-246">**Detectado por**</span><span class="sxs-lookup"><span data-stu-id="e1e31-246">**Detected by**</span></span>

   - <span data-ttu-id="e1e31-247">**Modificado por hora**</span><span class="sxs-lookup"><span data-stu-id="e1e31-247">**Modified by time**</span></span>

4. <span data-ttu-id="e1e31-248">Para filtrar os resultados, clique em **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-248">To filter the results, click **Filter**.</span></span> <span data-ttu-id="e1e31-249">Os filtros disponíveis são:</span><span class="sxs-lookup"><span data-stu-id="e1e31-249">The available filters are:</span></span>

   - <span data-ttu-id="e1e31-250">**Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:</span><span class="sxs-lookup"><span data-stu-id="e1e31-250">**Expires time**: Filter messages by when they will expire from quarantine:</span></span>

     - <span data-ttu-id="e1e31-251">**Hoje**</span><span class="sxs-lookup"><span data-stu-id="e1e31-251">**Today**</span></span>

     - <span data-ttu-id="e1e31-252">**Próximos 2 dias**</span><span class="sxs-lookup"><span data-stu-id="e1e31-252">**Next 2 days**</span></span>

     - <span data-ttu-id="e1e31-253">**Próximas 7 semanas**</span><span class="sxs-lookup"><span data-stu-id="e1e31-253">**Next 7 days**</span></span>

     - <span data-ttu-id="e1e31-254">Um intervalo personalizado de data/hora.</span><span class="sxs-lookup"><span data-stu-id="e1e31-254">A custom date/time range.</span></span>

   - <span data-ttu-id="e1e31-255">**Hora de recebimento**</span><span class="sxs-lookup"><span data-stu-id="e1e31-255">**Received time**</span></span>

   - <span data-ttu-id="e1e31-256">**Motivo da quarentena**: o único valor disponível é **malware**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-256">**Quarantine reason**: The only available value is **Malware**.</span></span>

<span data-ttu-id="e1e31-257">Depois de encontrar um arquivo em quarentena específico, selecione o arquivo para exibir os detalhes sobre ele e execute a ação nele (por exemplo, exibir, liberar, baixar ou excluir a mensagem).</span><span class="sxs-lookup"><span data-stu-id="e1e31-257">After you find a specific quarantined file, select the file to view details about it, and to take action on it (for example, view, release, download, or delete the message).</span></span>

#### <a name="export-file-results"></a><span data-ttu-id="e1e31-258">Exportar resultados de arquivo</span><span class="sxs-lookup"><span data-stu-id="e1e31-258">Export file results</span></span>

1. <span data-ttu-id="e1e31-259">Selecione os arquivos nos quais você está interessado e clique em **Exportar resultados**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-259">Select the files you're interested in, and click **Export results**.</span></span>

2. <span data-ttu-id="e1e31-260">Clique em **Sim** na mensagem de confirmação que avisa para manter a janela do navegador aberta.</span><span class="sxs-lookup"><span data-stu-id="e1e31-260">Click **Yes** in the confirmation message that warns you to keep the browser window open.</span></span>

3. <span data-ttu-id="e1e31-261">Quando a exportação estiver pronta, você poderá nomear e escolher o local de download do arquivo .csv.</span><span class="sxs-lookup"><span data-stu-id="e1e31-261">When your export is ready, you can name and choose the download location for the .csv file.</span></span>

#### <a name="view-quarantined-file-details"></a><span data-ttu-id="e1e31-262">Exibir detalhes de arquivo em quarentena</span><span class="sxs-lookup"><span data-stu-id="e1e31-262">View quarantined file details</span></span>

<span data-ttu-id="e1e31-263">Quando você seleciona um arquivo na lista, os seguintes detalhes de arquivo são exibidos no painel de submenu **detalhes** :</span><span class="sxs-lookup"><span data-stu-id="e1e31-263">When you select a file in the list, the following file details appear in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e1e31-264">**Nome do arquivo**</span><span class="sxs-lookup"><span data-stu-id="e1e31-264">**File Name**</span></span>

- <span data-ttu-id="e1e31-265">**URL do arquivo**: URL que define o local do arquivo (por exemplo, no SharePoint Online).</span><span class="sxs-lookup"><span data-stu-id="e1e31-265">**File URL**: URL that defines the location of the file (for example, in SharePoint Online).</span></span>

- <span data-ttu-id="e1e31-266">**Conteúdo mal-intencionado detectado em** A data/hora em que o arquivo foi colocado em quarentena.</span><span class="sxs-lookup"><span data-stu-id="e1e31-266">**Malicious content detected on** The date/time the file was quarantined.</span></span>

- <span data-ttu-id="e1e31-267">**Expira**: a data em que o arquivo será excluído da quarentena.</span><span class="sxs-lookup"><span data-stu-id="e1e31-267">**Expires**: The date when the file will be deleted from quarantine.</span></span>

- <span data-ttu-id="e1e31-268">**Detectado por**: ATP (proteção avançada contra ameaças) ou mecanismo antimalware da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e1e31-268">**Detected By**: ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span>

- <span data-ttu-id="e1e31-269">**Lançado?**</span><span class="sxs-lookup"><span data-stu-id="e1e31-269">**Released?**</span></span>

- <span data-ttu-id="e1e31-270">**Nome do malware**</span><span class="sxs-lookup"><span data-stu-id="e1e31-270">**Malware Name**</span></span>

- <span data-ttu-id="e1e31-271">**ID do documento**: um identificador exclusivo para o documento.</span><span class="sxs-lookup"><span data-stu-id="e1e31-271">**Document ID**: A unique identifier for the document.</span></span>

- <span data-ttu-id="e1e31-272">**Tamanho do arquivo**: em kilobytes (KB).</span><span class="sxs-lookup"><span data-stu-id="e1e31-272">**File Size**: In kilobytes (KB).</span></span>

- <span data-ttu-id="e1e31-273">**Organização** A ID exclusiva da sua organização.</span><span class="sxs-lookup"><span data-stu-id="e1e31-273">**Organization** Your organization's unique ID.</span></span>

- <span data-ttu-id="e1e31-274">**Última modificação**</span><span class="sxs-lookup"><span data-stu-id="e1e31-274">**Last modified**</span></span>

- <span data-ttu-id="e1e31-275">**Modificado por**: o usuário que modificou o arquivo pela última vez.</span><span class="sxs-lookup"><span data-stu-id="e1e31-275">**Modified By**: The user who last modified the file.</span></span>

- <span data-ttu-id="e1e31-276">**Algoritmo de hash seguro 256 bits (SHA-256) valor**: você pode usar esse valor de hash para identificar o arquivo em outros repositórios de reputação ou em outros locais em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="e1e31-276">**Secure Hash Algorithm 256-bit (SHA-256) value**: You can use this hash value to identify the file in other reputation stores or in other locations in your environment.</span></span>

### <a name="take-action-on-quarantined-files"></a><span data-ttu-id="e1e31-277">Executar ação em arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="e1e31-277">Take action on quarantined files</span></span>

<span data-ttu-id="e1e31-278">Ao selecionar um arquivo na lista, você pode executar as seguintes ações no arquivo no painel de submenu **detalhes** :</span><span class="sxs-lookup"><span data-stu-id="e1e31-278">When you select a file in the list, you can take the following actions on the file in the **Details** flyout pane:</span></span>

- <span data-ttu-id="e1e31-279">**Arquivos de lançamento**: selecione (padrão) ou desmarque **arquivos de relatório para a Microsoft para análise**e clique em **liberar arquivos**.</span><span class="sxs-lookup"><span data-stu-id="e1e31-279">**Release files**: Select (default) or unselect **Report files to Microsoft for analysis**, and then click **Release files**.</span></span>

- <span data-ttu-id="e1e31-280">**Baixar o arquivo**</span><span class="sxs-lookup"><span data-stu-id="e1e31-280">**Download file**</span></span>

- <span data-ttu-id="e1e31-281">**Remover arquivo da quarentena**</span><span class="sxs-lookup"><span data-stu-id="e1e31-281">**Remove file from quarantine**</span></span>

<span data-ttu-id="e1e31-282">Se você não liberar ou remover os arquivos, eles serão excluídos depois que o período de retenção de quarentena padrão expirar.</span><span class="sxs-lookup"><span data-stu-id="e1e31-282">If you don't release or remove the files, they will be deleted after the default quarantine retention period expires.</span></span>

#### <a name="actions-on-multiple-quarantined-files"></a><span data-ttu-id="e1e31-283">Ações em vários arquivos em quarentena</span><span class="sxs-lookup"><span data-stu-id="e1e31-283">Actions on multiple quarantined files</span></span>

<span data-ttu-id="e1e31-284">Quando você seleciona vários arquivos em quarentena na lista (até 100), o painel de submenu **ações em massa** aparece onde você pode executar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="e1e31-284">When you select multiple quarantined files in the list (up to 100), the **Bulk actions** flyout pane appears where you can take the following actions:</span></span>

- <span data-ttu-id="e1e31-285">**Arquivos de versão**</span><span class="sxs-lookup"><span data-stu-id="e1e31-285">**Release files**</span></span>

- <span data-ttu-id="e1e31-286">**Excluir arquivos**: depois de clicar em **Sim** no aviso exibido, os arquivos serão excluídos imediatamente.</span><span class="sxs-lookup"><span data-stu-id="e1e31-286">**Delete files**:  After you click **Yes** in the warning that appears, the files are immediately deleted.</span></span>

1. <span data-ttu-id="e1e31-287">Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global (ou funções apropriadas de segurança & central de conformidade) em sua organização, entre e [vá para o centro de conformidade de & de segurança](../../compliance/go-to-the-securitycompliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e1e31-287">Using a work or school account that has global administrator privileges (or appropriate Security & Compliance Center roles) in your organization, sign in and [go to the Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).</span></span>

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a><span data-ttu-id="e1e31-288">Usar o PowerShell do Exchange Online ou do Exchange Online Protection para exibir e gerenciar arquivos e mensagens em quarentena</span><span class="sxs-lookup"><span data-stu-id="e1e31-288">Use Exchange Online PowerShell or standalone Exchange Online Protection PowerShell to view and manage quarantined messages and files</span></span>

<span data-ttu-id="e1e31-289">Os cmdlets que você usa para exibir e gerenciar mensagens e arquivos em quarentena são:</span><span class="sxs-lookup"><span data-stu-id="e1e31-289">The cmdlets you use to view and manages messages and files in quarantine are:</span></span>

- [<span data-ttu-id="e1e31-290">Delete-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e1e31-290">Delete-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [<span data-ttu-id="e1e31-291">Export-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e1e31-291">Export-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [<span data-ttu-id="e1e31-292">Get-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e1e31-292">Get-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- <span data-ttu-id="e1e31-293">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Observe que este cmdlet é somente para mensagens, e não para arquivos de malware de ATP para SharePoint Online, onedrive for Business ou Teams.</span><span class="sxs-lookup"><span data-stu-id="e1e31-293">[Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Note that this cmdlet is only for messages, not malware files from ATP for SharePoint Online, OneDrive for Business, or Teams.</span></span>

- [<span data-ttu-id="e1e31-294">Release-QuarantineMessage</span><span class="sxs-lookup"><span data-stu-id="e1e31-294">Release-QuarantineMessage</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
