---
title: Configurar o EOP para lixo eletrônico em ambientes híbridos
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a rotear spam para pastas de Lixo Eletrônico do usuário em um ambiente híbrido da Proteção do Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ae6ee551d04b242891c9638d6d99d79240480d27
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910853"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="4c677-103">Configurar o EOP autônomo para fornecer spam à pasta Lixo Eletrônico em ambientes híbridos</span><span class="sxs-lookup"><span data-stu-id="4c677-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4c677-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="4c677-104">**Applies to**</span></span>
-  [<span data-ttu-id="4c677-105">Proteção autônoma do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4c677-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

> [!IMPORTANT]
> <span data-ttu-id="4c677-106">Este tópico é apenas para clientes EOP autônomos em ambientes híbridos.</span><span class="sxs-lookup"><span data-stu-id="4c677-106">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="4c677-107">Este tópico não se aplica aos clientes do Microsoft 365 com caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4c677-107">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="4c677-108">Se você for um cliente do Exchange Online Protection (EOP) autônomo em um ambiente híbrido, será necessário configurar sua organização local do Exchange para reconhecer e traduzir os vereditos de filtragem de spam do EOP, para que a regra de lixo eletrônico na caixa de correio local possa mover mensagens para a pasta Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="4c677-108">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="4c677-109">Especificamente, você precisa criar regras de fluxo de emails (também conhecidas como regras de transporte) em sua organização local do Exchange com condições que encontram mensagens com qualquer um dos seguintes valores e headers anti-spam do EOP e ações que desempate o nível de confiança de spam (SCL) dessas mensagens como 6:</span><span class="sxs-lookup"><span data-stu-id="4c677-109">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="4c677-110">`X-Forefront-Antispam-Report: SFV:SPM` (mensagem marcada como spam pela filtragem de spam)</span><span class="sxs-lookup"><span data-stu-id="4c677-110">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="4c677-111">`X-Forefront-Antispam-Report: SFV:SKS` (mensagem marcada como spam por regras de fluxo de emails no EOP antes da filtragem de spam)</span><span class="sxs-lookup"><span data-stu-id="4c677-111">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="4c677-112">`X-Forefront-Antispam-Report: SFV:SKB` (mensagem marcada como spam pela filtragem de spam devido ao endereço de email ou domínio de email do remetente estar na lista de remetentes bloqueados ou na lista de domínios bloqueados no EOP)</span><span class="sxs-lookup"><span data-stu-id="4c677-112">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="4c677-113">Para obter mais informações sobre esses valores de header, consulte [Headers de mensagem anti-spam.](anti-spam-message-headers.md)</span><span class="sxs-lookup"><span data-stu-id="4c677-113">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="4c677-114">Este tópico descreve como criar essas regras de fluxo de emails no Centro de administração do Exchange (EAC) e no Shell de Gerenciamento do Exchange (Exchange PowerShell) na organização local do Exchange.</span><span class="sxs-lookup"><span data-stu-id="4c677-114">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="4c677-115">Em vez de entregar as mensagens para a pasta Lixo Eletrônico do usuário local, você pode configurar políticas anti-spam no EOP para colocar em quarentena mensagens de spam no EOP.</span><span class="sxs-lookup"><span data-stu-id="4c677-115">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="4c677-116">Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4c677-116">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4c677-117">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="4c677-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4c677-118">Você precisa ter permissões atribuídas no ambiente local do Exchange antes de poder fazer esses procedimentos.</span><span class="sxs-lookup"><span data-stu-id="4c677-118">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="4c677-119">Especificamente, você precisa ter  a função Regras de Transporte, que é atribuída  às funções Gerenciamento da **Organização,** Gerenciamento de Conformidade e Gerenciamento de Registros por padrão. </span><span class="sxs-lookup"><span data-stu-id="4c677-119">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="4c677-120">Para obter mais informações, consulte [Adicionar membros a um grupo de funções](/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span><span class="sxs-lookup"><span data-stu-id="4c677-120">For more information, see [Add members to a role group](/Exchange/permissions/role-group-members#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="4c677-121">Se e quando uma mensagem é entregue à pasta Lixo Eletrônico em uma organização local do Exchange é controlada por uma combinação das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="4c677-121">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="4c677-122">O _valor do parâmetro SCLJunkThreshold_ no cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) no Shell de Gerenciamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="4c677-122">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="4c677-123">O valor padrão é 4, o que significa que uma SCL de 5 ou superior deve entregar a mensagem para a pasta lixo eletrônico do usuário.</span><span class="sxs-lookup"><span data-stu-id="4c677-123">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="4c677-124">O _valor do parâmetro SCLJunkThreshold_ no cmdlet [Set-Mailbox](/powershell/module/exchange/set-mailbox) no Shell de Gerenciamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="4c677-124">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="4c677-125">O valor padrão está em branco ($null), o que significa que a configuração da organização é usada.</span><span class="sxs-lookup"><span data-stu-id="4c677-125">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="4c677-126">Para obter detalhes, consulte Limites de nível de confiança [de spam do Exchange (SCL).](/Exchange/antispam-and-antimalware/antispam-protection/scl)</span><span class="sxs-lookup"><span data-stu-id="4c677-126">For details, see [Exchange spam confidence level (SCL) thresholds](/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="4c677-127">Se a regra de lixo eletrônico está habilitada na caixa de correio (o valor do parâmetro _Enabled_ é $true no cmdlet [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration) no Shell de Gerenciamento do Exchange).</span><span class="sxs-lookup"><span data-stu-id="4c677-127">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="4c677-128">É a regra de lixo eletrônico que realmente move a mensagem para a pasta Lixo Eletrônico após a entrega.</span><span class="sxs-lookup"><span data-stu-id="4c677-128">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="4c677-129">Por padrão, a regra de lixo eletrônico está habilitada em caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="4c677-129">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="4c677-130">Para obter mais informações, consulte [Configure Exchange antispam settings on mailboxes](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span><span class="sxs-lookup"><span data-stu-id="4c677-130">For more information, see [Configure Exchange antispam settings on mailboxes](/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>

- <span data-ttu-id="4c677-131">Para abrir o EAC em um Exchange Server, consulte Centro de administração [do Exchange em Exchange Server](/Exchange/architecture/client-access/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="4c677-131">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="4c677-132">Para abrir o Shell de Gerenciamento do Exchange, confira [Abrir o Shell de Gerenciamento do Exchange](/powershell/exchange/open-the-exchange-management-shell).</span><span class="sxs-lookup"><span data-stu-id="4c677-132">To open the Exchange Management Shell, see [Open the Exchange Management Shell](/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="4c677-133">Para obter mais informações sobre regras de fluxo de emails no Exchange local, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="4c677-133">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="4c677-134">Regras de fluxo de emails em Exchange Server</span><span class="sxs-lookup"><span data-stu-id="4c677-134">Mail flow rules in Exchange Server</span></span>](/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="4c677-135">Condições e exceções de regra de fluxo de email (predicados) no Exchange Server</span><span class="sxs-lookup"><span data-stu-id="4c677-135">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="4c677-136">Ações de regra de fluxo de email em Exchange Server</span><span class="sxs-lookup"><span data-stu-id="4c677-136">Mail flow rule actions in Exchange Server</span></span>](/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="4c677-137">Use o EAC para criar regras de fluxo de emails que desemparecem a SCL de mensagens de spam do EOP</span><span class="sxs-lookup"><span data-stu-id="4c677-137">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="4c677-138">No EAC, vá para **Fluxo de emails** \> **Regras**.</span><span class="sxs-lookup"><span data-stu-id="4c677-138">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="4c677-139">Clique **em** ![ Adicionar ícone e selecione Criar uma nova ](../../media/ITPro-EAC-AddIcon.png) **regra** no menu drop-down exibido.</span><span class="sxs-lookup"><span data-stu-id="4c677-139">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="4c677-140">Na página **Nova regra** que é aberta, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="4c677-140">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="4c677-141">**Nome**: Insira um nome exclusivo e descritivo para a regra.</span><span class="sxs-lookup"><span data-stu-id="4c677-141">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="4c677-142">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4c677-142">For example:</span></span>

     - <span data-ttu-id="4c677-143">EOP SFV:SPM para SCL 6</span><span class="sxs-lookup"><span data-stu-id="4c677-143">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="4c677-144">EOP SFV:SKS para SCL 6</span><span class="sxs-lookup"><span data-stu-id="4c677-144">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="4c677-145">EOP SFV:SKB para SCL 6</span><span class="sxs-lookup"><span data-stu-id="4c677-145">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="4c677-146">Clique **em Mais Opções**.</span><span class="sxs-lookup"><span data-stu-id="4c677-146">Click **More Options**.</span></span>

   - <span data-ttu-id="4c677-147">**Aplique essa regra se**: Selecione **Um header** de \> **mensagem inclui qualquer uma dessas palavras**.</span><span class="sxs-lookup"><span data-stu-id="4c677-147">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="4c677-148">No header **Inserir texto inclui Enter words** sentence that appears, do the following steps:</span><span class="sxs-lookup"><span data-stu-id="4c677-148">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="4c677-149">Clique **em Inserir texto**.</span><span class="sxs-lookup"><span data-stu-id="4c677-149">Click **Enter text**.</span></span> <span data-ttu-id="4c677-150">Na caixa **de diálogo Especificar nome do header** que aparece, insira **X-Forefront-Antispam-Report** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c677-150">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="4c677-151">Clique  **em Inserir palavras**.</span><span class="sxs-lookup"><span data-stu-id="4c677-151">Click  **Enter words**.</span></span> <span data-ttu-id="4c677-152">Na caixa de diálogo Especificar palavras ou **frases exibidas,** insira um dos valores de header de spam do EOP (**SFV:SPM,** **SFV:SKS** ou **SFV:SKB**), clique em **Adicionar** ícone e clique ![ em ](../../media/ITPro-EAC-AddIcon.png) **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c677-152">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="4c677-153">**Faça o seguinte:** Selecione **Modificar as propriedades da mensagem** Definir o nível de confiança de spam \> **(SCL).**</span><span class="sxs-lookup"><span data-stu-id="4c677-153">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="4c677-154">Na caixa **de diálogo Especificar SCL** exibida, selecione **6** (o valor padrão é **5**).</span><span class="sxs-lookup"><span data-stu-id="4c677-154">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="4c677-155">Quando terminar, clique em **Salvar**</span><span class="sxs-lookup"><span data-stu-id="4c677-155">When you're finished, click **Save**</span></span>

<span data-ttu-id="4c677-156">Repita estas etapas para os valores de veredito de spam do EOP restantes (**SFV:SPM,** **SFV:SKS** ou **SFV:SKB**).</span><span class="sxs-lookup"><span data-stu-id="4c677-156">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="4c677-157">Use o Shell de Gerenciamento do Exchange para criar regras de fluxo de emails que desempareçam a SCL de mensagens de spam do EOP</span><span class="sxs-lookup"><span data-stu-id="4c677-157">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="4c677-158">Use a sintaxe a seguir para criar as três regras de fluxo de emails:</span><span class="sxs-lookup"><span data-stu-id="4c677-158">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="4c677-159">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4c677-159">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="4c677-160">Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="4c677-160">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="4c677-161">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="4c677-161">How do you know this worked?</span></span>

<span data-ttu-id="4c677-162">Para verificar se você configurou com êxito o EOP autônomo para fornecer spam à pasta Lixo Eletrônico em ambiente híbrido, faça uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="4c677-162">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="4c677-163">No EAC, vá para Regras de **fluxo** de email, selecione a regra e clique em Editar Ícone editar \> para verificar as  ![ ](../../media/ITPro-EAC-EditIcon.png) configurações.</span><span class="sxs-lookup"><span data-stu-id="4c677-163">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="4c677-164">No Shell de Gerenciamento do Exchange, substitua pelo nome da regra de fluxo de emails e rul o seguinte comando \<RuleName\> para verificar as configurações:</span><span class="sxs-lookup"><span data-stu-id="4c677-164">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="4c677-165">Em um sistema de email externo que não digitalizar mensagens de saída para **spam,** envie uma mensagem de Teste Genérico para Email em Massa Não Solicitado (GTUBE) para um destinatário afetado e confirme se ela foi entregue à pasta Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="4c677-165">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="4c677-166">A mensagem do GTUBE é similar ao arquivo de texto do EICAR (Instituto Europeu para Pesquisa de Antivírus de Computador) em configurações de malware de teste.</span><span class="sxs-lookup"><span data-stu-id="4c677-166">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="4c677-167">Para enviar uma mensagem GTUBE, inclua o seguinte texto no corpo de uma mensagem de email em uma única linha, sem espaços ou quebras de linha:</span><span class="sxs-lookup"><span data-stu-id="4c677-167">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```