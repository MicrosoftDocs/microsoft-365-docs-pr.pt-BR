---
title: Configurar o EOP para o lixo eletrônico em ambientes híbridos
f1.keywords:
- NOCSH
ms.author: chrisda
author: MSFTTracyP
manager: chrisda
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a rotear spam para as pastas de lixo eletrônico do usuário em um ambiente híbrido do Exchange Online Protection.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5d8ba6aae599ee4dd327bd1ec82b46e8f3ee3ca8
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679115"
---
# <a name="configure-standalone-eop-to-deliver-spam-to-the-junk-email-folder-in-hybrid-environments"></a><span data-ttu-id="c8795-103">Configurar o EOP autônomo para fornecer spam para a pasta lixo eletrônico em ambientes híbridos</span><span class="sxs-lookup"><span data-stu-id="c8795-103">Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8795-104">Este tópico é somente para clientes autônomos do EOP em ambientes híbridos.</span><span class="sxs-lookup"><span data-stu-id="c8795-104">This topic is only for standalone EOP customers in hybrid environments.</span></span> <span data-ttu-id="c8795-105">Este tópico não se aplica a clientes da Microsoft 365 com caixas de correio do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c8795-105">This topic does not apply to Microsoft 365 customers with Exchange Online mailboxes.</span></span>

<span data-ttu-id="c8795-106">Se você for um cliente autônomo do Exchange Online Protection (EOP) em um ambiente híbrido, precisará configurar sua organização do Exchange local para reconhecer e traduzir o verdicts de filtragem de spam do EOP, para que a regra de lixo eletrônico na caixa de correio local possa mover mensagens para a pasta lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="c8795-106">If you're a standalone Exchange Online Protection (EOP) customer in a hybrid environment, you need to configure your on-premises Exchange organization to recognize and translate the spam filtering verdicts of EOP, so the junk email rule in the on-premises mailbox can move messages to the Junk Email folder.</span></span>

<span data-ttu-id="c8795-107">Especificamente, você precisa criar regras de fluxo de emails (também conhecidas como regras de transporte) em sua organização local do Exchange com condições que encontrem mensagens com qualquer um dos seguintes valores e cabeçalhos antispam do EOP, e ações que definem o nível de confiança de spam (SCL) dessas mensagens como 6:</span><span class="sxs-lookup"><span data-stu-id="c8795-107">Specifically, you need to create mail flow rules (also known as transport rules) in your on-premises Exchange organization with conditions that find messages with any of the following EOP anti-spam headers and values, and actions that set the spam confidence level (SCL) of those messages to 6:</span></span>

- <span data-ttu-id="c8795-108">`X-Forefront-Antispam-Report: SFV:SPM`(mensagem marcada como spam por filtragem de spam)</span><span class="sxs-lookup"><span data-stu-id="c8795-108">`X-Forefront-Antispam-Report: SFV:SPM` (message marked as spam by spam filtering)</span></span>

- <span data-ttu-id="c8795-109">`X-Forefront-Antispam-Report: SFV:SKS`(mensagem marcada como spam por regras de fluxo de email no EOP antes de filtragem de spam)</span><span class="sxs-lookup"><span data-stu-id="c8795-109">`X-Forefront-Antispam-Report: SFV:SKS` (message marked as spam by mail flow rules in EOP before spam filtering)</span></span>

- <span data-ttu-id="c8795-110">`X-Forefront-Antispam-Report: SFV:SKB`(mensagem marcada como spam por filtragem de spam devido ao endereço de email do remetente ou domínio de email que está na lista de remetentes bloqueados ou na lista de domínios bloqueados no EOP)</span><span class="sxs-lookup"><span data-stu-id="c8795-110">`X-Forefront-Antispam-Report: SFV:SKB` (message marked as spam by spam filtering due to the sender's email address or email domain being in the blocked sender list or the blocked domain list in EOP)</span></span>

<span data-ttu-id="c8795-111">Para obter mais informações sobre esses valores de cabeçalho, consulte [anti-spam Message Headers](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="c8795-111">For more information about these header values, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

<span data-ttu-id="c8795-112">Este tópico descreve como criar essas regras de fluxo de emails do centro de administração do Exchange (Eat) e no Shell de gerenciamento do Exchange (Exchange PowerShell) na organização do Exchange local.</span><span class="sxs-lookup"><span data-stu-id="c8795-112">This topic describes how to create these mail flow rules the Exchange admin center (EAC) and in the Exchange Management Shell (Exchange PowerShell) in the on-premises Exchange organization.</span></span>

> [!TIP]
> <span data-ttu-id="c8795-113">Em vez de entregar as mensagens à pasta de lixo eletrônico do usuário local, você pode configurar políticas antispam no EOP para colocar mensagens de spam em quarentena no EOP.</span><span class="sxs-lookup"><span data-stu-id="c8795-113">Instead of delivering the messages to the on-premises user's Junk Email folder, you can configure anti-spam policies in EOP to quarantine spam messages in EOP.</span></span> <span data-ttu-id="c8795-114">Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c8795-114">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c8795-115">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="c8795-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c8795-116">Você precisa receber permissões no ambiente local do Exchange antes de poder executar estes procedimentos.</span><span class="sxs-lookup"><span data-stu-id="c8795-116">You need to be assigned permissions in the on-premises Exchange environment before you can do these procedures.</span></span> <span data-ttu-id="c8795-117">Especificamente, você precisa receber a função de **regras de transporte** , que é atribuída às funções de gerenciamento da **organização**, **Gerenciamento de conformidade**e gerenciamento de **registros** por padrão.</span><span class="sxs-lookup"><span data-stu-id="c8795-117">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="c8795-118">Para obter mais informações, consulte [Adicionar membros a um grupo de funções](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).</span><span class="sxs-lookup"><span data-stu-id="c8795-118">For more information, see [Add members to a role group](https://docs.microsoft.com/Exchange/permissions/role-group-members?view=exchserver-2019#add-members-to-a-role-group).</span></span>

- <span data-ttu-id="c8795-119">Se e quando uma mensagem for enviada para a pasta lixo eletrônico em uma organização local do Exchange é controlada por uma combinação das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c8795-119">If and when a message is delivered to the Junk Email folder in an on-premises Exchange organization is controlled by a combination of the following settings:</span></span>

  - <span data-ttu-id="c8795-120">O valor do parâmetro _SCLJunkThreshold_ no cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) no Shell de gerenciamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="c8795-120">The _SCLJunkThreshold_ parameter value on the [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="c8795-121">O valor padrão é 4, o que significa que um SCL de 5 ou superior deve entregar a mensagem para a pasta lixo eletrônico do usuário.</span><span class="sxs-lookup"><span data-stu-id="c8795-121">The default value is 4, which means an SCL of 5 or higher should deliver the message to the user's Junk email folder.</span></span>

  - <span data-ttu-id="c8795-122">O valor do parâmetro _SCLJunkThreshold_ no cmdlet [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) no Shell de gerenciamento do Exchange.</span><span class="sxs-lookup"><span data-stu-id="c8795-122">The _SCLJunkThreshold_ parameter value on the [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox) cmdlet in the Exchange Management Shell.</span></span> <span data-ttu-id="c8795-123">O valor padrão é Blank ($null), o que significa que a configuração da organização é usada.</span><span class="sxs-lookup"><span data-stu-id="c8795-123">The default value is blank ($null), which means the organization setting is used.</span></span>

  <span data-ttu-id="c8795-124">Para obter detalhes, consulte [Exchange spam nível de confiança (SCL)](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span><span class="sxs-lookup"><span data-stu-id="c8795-124">For details, see [Exchange spam confidence level (SCL) thresholds](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/scl).</span></span>

  - <span data-ttu-id="c8795-125">Se a regra de lixo eletrônico está habilitada na caixa de correio (o valor do parâmetro _Enabled_ é $true no cmdlet [set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) no Shell de gerenciamento do Exchange).</span><span class="sxs-lookup"><span data-stu-id="c8795-125">Whether the junk email rule is enabled on the mailbox (the _Enabled_ parameter value is $true on the [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration) cmdlet in the Exchange Management Shell).</span></span> <span data-ttu-id="c8795-126">É a regra de lixo eletrônico que realmente move a mensagem para a pasta lixo eletrônico após a entrega.</span><span class="sxs-lookup"><span data-stu-id="c8795-126">It's the junk email rule that actually moves the message to the Junk Email folder after delivery.</span></span> <span data-ttu-id="c8795-127">Por padrão, a regra de lixo eletrônico está habilitada nas caixas de correio.</span><span class="sxs-lookup"><span data-stu-id="c8795-127">By default, the junk email rule is enabled on mailboxes.</span></span> <span data-ttu-id="c8795-128">Para obter mais informações, consulte [Configurar configurações antispam do Exchange em caixas de correio](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span><span class="sxs-lookup"><span data-stu-id="c8795-128">For more information, see [Configure Exchange antispam settings on mailboxes](https://docs.microsoft.com/Exchange/antispam-and-antimalware/antispam-protection/configure-antispam-settings).</span></span>
  
- <span data-ttu-id="c8795-129">Para abrir o Eat em um servidor Exchange, confira [centro de administração do Exchange no Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="c8795-129">To open the EAC on an Exchange Server, see [Exchange admin center in Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/exchange-admin-center).</span></span> <span data-ttu-id="c8795-130">Para abrir o Shell de gerenciamento do Exchange, confira [abrir o Shell de gerenciamento do Exchange](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span><span class="sxs-lookup"><span data-stu-id="c8795-130">To open the Exchange Management Shell, see [Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/open-the-exchange-management-shell).</span></span>

- <span data-ttu-id="c8795-131">Para obter mais informações sobre regras de fluxo de emails no Exchange local, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c8795-131">For more information about mail flow rules in on-premises Exchange, see the following topics:</span></span>

  - [<span data-ttu-id="c8795-132">Regras de fluxo de emails no Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c8795-132">Mail flow rules in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="c8795-133">Condições e exceções de regra de fluxo de emails (predicados) no Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c8795-133">Mail flow rule conditions and exceptions (predicates) in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="c8795-134">Ações de regra de fluxo de email no Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c8795-134">Mail flow rule actions in Exchange Server</span></span>](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/actions)

## <a name="use-the-eac-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="c8795-135">Use o Eat para criar regras de fluxo de email que definem o SCL das mensagens de spam do EOP</span><span class="sxs-lookup"><span data-stu-id="c8795-135">Use the EAC to create mail flow rules that set the SCL of EOP spam messages</span></span>

1. <span data-ttu-id="c8795-136">No EAC, vá para **Fluxo de emails** \> **Regras**.</span><span class="sxs-lookup"><span data-stu-id="c8795-136">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="c8795-137">Clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) e selecione **criar uma nova regra** no menu suspenso que aparece.</span><span class="sxs-lookup"><span data-stu-id="c8795-137">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and select **Create a new rule** in the drop-down that appears.</span></span>

3. <span data-ttu-id="c8795-138">Na página **nova regra** que é aberta, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="c8795-138">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="c8795-139">**Name**: Insira um nome exclusivo e descritivo para a regra.</span><span class="sxs-lookup"><span data-stu-id="c8795-139">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="c8795-140">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c8795-140">For example:</span></span>

     - <span data-ttu-id="c8795-141">EOP SFV: SPM para SCL 6</span><span class="sxs-lookup"><span data-stu-id="c8795-141">EOP SFV:SPM to SCL 6</span></span>

     - <span data-ttu-id="c8795-142">EOP SFV: SKS para SCL 6</span><span class="sxs-lookup"><span data-stu-id="c8795-142">EOP SFV:SKS to SCL 6</span></span>

     - <span data-ttu-id="c8795-143">EOP SFV: SKB para SCL 6</span><span class="sxs-lookup"><span data-stu-id="c8795-143">EOP SFV:SKB to SCL 6</span></span>

   - <span data-ttu-id="c8795-144">Clique em **mais opções**.</span><span class="sxs-lookup"><span data-stu-id="c8795-144">Click **More Options**.</span></span>

   - <span data-ttu-id="c8795-145">**Aplicar esta regra se**: selecionar **um cabeçalho de mensagem** \> **inclui qualquer uma destas palavras**.</span><span class="sxs-lookup"><span data-stu-id="c8795-145">**Apply this rule if**: Select **A message header** \> **includes any of these words**.</span></span>

     <span data-ttu-id="c8795-146">Na frase **Inserir cabeçalho de texto inclui palavras de entrada** que aparecem, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="c8795-146">In the **Enter text header includes Enter words** sentence that appears, do the following steps:</span></span>

     - <span data-ttu-id="c8795-147">Clique em **Inserir texto**.</span><span class="sxs-lookup"><span data-stu-id="c8795-147">Click **Enter text**.</span></span> <span data-ttu-id="c8795-148">Na caixa de diálogo **especificar nome do cabeçalho** que aparece, insira **X-Forefront-antispam-Report** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8795-148">In the **Specify header name** dialog that appears, enter **X-Forefront-Antispam-Report** and then click **OK**.</span></span>

     - <span data-ttu-id="c8795-149">Clique em **inserir palavras**.</span><span class="sxs-lookup"><span data-stu-id="c8795-149">Click  **Enter words**.</span></span> <span data-ttu-id="c8795-150">Na caixa de diálogo **especificar palavras ou frases** que aparece, insira um dos valores de cabeçalho de spam do EOP (**SFV: SPM**, **SFV: SKS**ou **SFV: SKB**), clique em **Adicionar** ![ ícone ](../../media/ITPro-EAC-AddIcon.png) de adição e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8795-150">In the **Specify words or phrases** dialog that appears, enter one of the EOP spam header values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**), click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png), and then click **OK**.</span></span>

   - <span data-ttu-id="c8795-151">**Faça o seguinte**: selecione **modificar as propriedades da mensagem** \> **definem o nível de confiança de spam (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="c8795-151">**Do the following**: Select **Modify the message properties** \> **Set the spam confidence level (SCL)**.</span></span>

     <span data-ttu-id="c8795-152">Na caixa de diálogo **especificar SCL** exibida, selecione **6** (o valor padrão é **5**).</span><span class="sxs-lookup"><span data-stu-id="c8795-152">In the **Specify SCL** dialog that appears, select **6** (the default value is **5**).</span></span>

   <span data-ttu-id="c8795-153">Quando tiver terminado, clique em **salvar**</span><span class="sxs-lookup"><span data-stu-id="c8795-153">When you're finished, click **Save**</span></span>

<span data-ttu-id="c8795-154">Repita essas etapas para os valores de veredicto de spam restantes do EOP (**SFV: SPM**, **SFV: SKS**ou **SFV: SKB**).</span><span class="sxs-lookup"><span data-stu-id="c8795-154">Repeat these steps for the remaining EOP spam verdict values (**SFV:SPM**, **SFV:SKS**, or **SFV:SKB**).</span></span>

## <a name="use-the-exchange-management-shell-to-create-mail-flow-rules-that-set-the-scl-of-eop-spam-messages"></a><span data-ttu-id="c8795-155">Usar o Shell de gerenciamento do Exchange para criar regras de fluxo de emails que definem o SCL das mensagens de spam do EOP</span><span class="sxs-lookup"><span data-stu-id="c8795-155">Use the Exchange Management Shell to create mail flow rules that set the SCL of EOP spam messages</span></span>

<span data-ttu-id="c8795-156">Use a seguinte sintaxe para criar as três regras de fluxo de emails:</span><span class="sxs-lookup"><span data-stu-id="c8795-156">Use the following syntax to create the three mail flow rules:</span></span>

```Powershell
New-TransportRule -Name "<RuleName>" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "<EOPSpamFilteringVerdict>" -SetSCL 6
```

<span data-ttu-id="c8795-157">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c8795-157">For example:</span></span>

```Powershell
New-TransportRule -Name "EOP SFV:SPM to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKS to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
```

```Powershell
New-TransportRule -Name "EOP SFV:SKB to SCL 6" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
```

<span data-ttu-id="c8795-158">Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="c8795-158">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="c8795-159">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="c8795-159">How do you know this worked?</span></span>

<span data-ttu-id="c8795-160">Para verificar se você configurou com êxito o EOP autônomo para entregar spam para a pasta lixo eletrônico no ambiente híbrido, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="c8795-160">To verify that you've successfully configured standalone EOP to deliver spam to the Junk Email folder in hybrid environment, do any of the following steps:</span></span>

- <span data-ttu-id="c8795-161">No Eat, vá para regras de **fluxo de emails** \> **Rules**, selecione a regra e clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) para verificar as configurações.</span><span class="sxs-lookup"><span data-stu-id="c8795-161">In the EAC, go to **Mail flow** \> **Rules**, select the rule, and then click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png) to verify the settings.</span></span>

- <span data-ttu-id="c8795-162">No Shell de gerenciamento do Exchange, substitua \<RuleName\> o nome da regra de fluxo de emails e regra o comando a seguir para verificar as configurações:</span><span class="sxs-lookup"><span data-stu-id="c8795-162">In the Exchange Management Shell, replace \<RuleName\> with the name of the mail flow rule, and rul the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<RuleName>" | Format-List
  ```

- <span data-ttu-id="c8795-163">Em um sistema de email externo **que não examina mensagens de saída para spam**, envie um teste genérico para uma mensagem de email em massa não solicitado (GTUBE) para um destinatário afetado e confirme se ele é entregue na pasta lixo eletrônico.</span><span class="sxs-lookup"><span data-stu-id="c8795-163">In an external email system **that doesn't scan outbound messages for spam**, send a Generic Test for Unsolicited Bulk Email (GTUBE) message to an affected recipient, and confirm that it's delivered to their Junk Email folder.</span></span> <span data-ttu-id="c8795-164">A mensagem do GTUBE é similar ao arquivo de texto do EICAR (Instituto Europeu para Pesquisa de Antivírus de Computador) em configurações de malware de teste.</span><span class="sxs-lookup"><span data-stu-id="c8795-164">A GTUBE message is similar to the European Institute for Computer Antivirus Research (EICAR) text file for testing malware settings.</span></span>

  <span data-ttu-id="c8795-165">Para enviar uma mensagem do GTUBE, inclua o seguinte texto no corpo de uma mensagem de email em uma única linha, sem espaços ou quebras de linha:</span><span class="sxs-lookup"><span data-stu-id="c8795-165">To send a GTUBE message, include the following text in the body of an email message on a single line, without any spaces or line breaks:</span></span>

  ```text
  XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
  ```
