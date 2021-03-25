---
title: Usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a usar regras de fluxo de emails (também conhecidas como regras de transporte) para receber cópias das mensagens relatadas pelos usuários à Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e6428a228ae64562f0b529f6aa90ddc3be46fdc
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203117"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="3ca9e-103">Usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft</span><span class="sxs-lookup"><span data-stu-id="3ca9e-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3ca9e-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="3ca9e-104">**Applies to**</span></span>
- [<span data-ttu-id="3ca9e-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3ca9e-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3ca9e-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="3ca9e-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3ca9e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3ca9e-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="3ca9e-108">Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, há várias maneiras de os usuários relatarem mensagens à Microsoft para análise, conforme descrito em Relatar mensagens e arquivos para a [Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="3ca9e-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, there are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="3ca9e-109">Você pode criar uma regra de fluxo de emails (também conhecida como regra de transporte) que procura mensagens que os usuários relatam para a Microsoft e pode configurar destinatários Cc para receber cópias dessas mensagens relatadas.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-109">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="3ca9e-110">Você pode criar a regra de fluxo de emails no Centro de administração do Exchange (EAC) e no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="3ca9e-110">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3ca9e-111">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="3ca9e-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3ca9e-112">Você precisa ter permissões atribuídas no Exchange Online ou no Exchange Online Protection antes de poder fazer os procedimentos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-112">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="3ca9e-113">Especificamente, você precisa da função **Regras** de Transporte, que é atribuída aos  grupos de função Gerenciamento da **Organização,** Gerenciamento de **Conformidade** (administradores globais) e Gerenciamento de Registros por padrão.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-113">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="3ca9e-114">Para mais informações, confira os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="3ca9e-114">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="3ca9e-115">Permissões no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3ca9e-115">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="3ca9e-116">Permissões no EOP autônomo</span><span class="sxs-lookup"><span data-stu-id="3ca9e-116">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="3ca9e-117">Usar o EAC modificar a lista de membros em grupos de função</span><span class="sxs-lookup"><span data-stu-id="3ca9e-117">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="3ca9e-118">Para abrir o EAC no Exchange Online, consulte [Centro de administração do Exchange no Exchange Online](/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="3ca9e-118">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="3ca9e-119">Para abrir o EAC no EOP autônomo, consulte Centro de administração [do Exchange no EOP](exchange-admin-center-in-exchange-online-protection-eop.md)autônomo .</span><span class="sxs-lookup"><span data-stu-id="3ca9e-119">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="3ca9e-120">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="3ca9e-120">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="3ca9e-121">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="3ca9e-121">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="3ca9e-122">Para obter mais informações sobre regras de fluxo de emails no Exchange Online e no EOP autônomo, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="3ca9e-122">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>
  - [<span data-ttu-id="3ca9e-123">Regras de fluxo de emails (regras de transporte) no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3ca9e-123">Mail flow rules (transport rules) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - [<span data-ttu-id="3ca9e-124">Condições e exceções de regra de fluxo de email (predicados) no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3ca9e-124">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)
  - [<span data-ttu-id="3ca9e-125">Ações de regra de fluxo de emails no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3ca9e-125">Mail flow rule actions in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="3ca9e-126">Usar o EAC para criar uma regra de fluxo de emails para receber cópias de mensagens relatadas</span><span class="sxs-lookup"><span data-stu-id="3ca9e-126">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="3ca9e-127">No EAC, vá para **Fluxo de emails** \> **Regras**.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-127">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="3ca9e-128">Clique **em Adicionar** ícone e selecione Criar uma nova ![ ](../../media/ITPro-EAC-AddIcon.png) **regra.**</span><span class="sxs-lookup"><span data-stu-id="3ca9e-128">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="3ca9e-129">Na página **Nova regra** que é aberta, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="3ca9e-129">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="3ca9e-130">**Nome**: Insira um nome exclusivo e descritivo para a regra.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-130">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="3ca9e-131">Por exemplo, Mensagens de Cc Reportadas à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-131">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="3ca9e-132">Clique **em Mais Opções**.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-132">Click **More Options**.</span></span>

   - <span data-ttu-id="3ca9e-133">Aplique esta regra se **:** **Selecione** O endereço do destinatário inclui qualquer uma dessas palavras : na caixa de diálogo Especificar palavras ou \>  **frases** que aparece, insira um dos seguintes valores, clique em **Adicionar** Ícone e repita até que você tenha inserido todos os ![ ](../../media/ITPro-EAC-AddIcon.png) valores.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-133">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `not_junk@office365.microsoft.com`

     <span data-ttu-id="3ca9e-134">Para editar uma entrada, selecione-a e clique em **Editar** ![ ícone ](../../media/ITPro-EAC-EditIcon.png) editar.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-134">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="3ca9e-135">Para remover uma entrada, selecione-a e clique em **Remover** ![ ícone ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="3ca9e-135">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="3ca9e-136">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-136">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="3ca9e-137">**Faça o seguinte:** Selecione **Adicionar destinatários** \> **à caixa Cc**.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-137">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="3ca9e-138">Na caixa de diálogo exibida, encontre e selecione os destinatários que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-138">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="3ca9e-139">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-139">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="3ca9e-140">Você pode fazer seleções adicionais para auditar a regra, testar a regra, ativar a regra durante um período de tempo específico e outras configurações.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-140">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="3ca9e-141">Recomendamos testar a regra antes de impor isso.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-141">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="3ca9e-142">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-142">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="3ca9e-143">Usar o PowerShell para criar uma regra de fluxo de emails para receber cópias de mensagens relatadas</span><span class="sxs-lookup"><span data-stu-id="3ca9e-143">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="3ca9e-144">Este exemplo cria uma nova regra de fluxo de emails chamada Mensagens Bcc Reportadas à Microsoft que procura mensagens de email relatadas à Microsoft usando os métodos descritos neste artigo e adiciona os usuários laura@contoso.com e julia@contoso.com como destinatários Cc.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-144">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this article, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="3ca9e-145">Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="3ca9e-145">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="3ca9e-146">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="3ca9e-146">How do you know this worked?</span></span>

<span data-ttu-id="3ca9e-147">Para verificar se você configurou uma regra de fluxo de emails para receber cópias de mensagens relatadas, faça qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="3ca9e-147">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="3ca9e-148">No EAC, vá para **Regras de fluxo de** email selecione a regra clique em \>  \> \> **Editar** ícone editar e verifique ![ as ](../../media/ITPro-EAC-EditIcon.png) configurações.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-148">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="3ca9e-149">No PowerShell, execute o seguinte comando para verificar as configurações:</span><span class="sxs-lookup"><span data-stu-id="3ca9e-149">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="3ca9e-150">Envie uma mensagem de teste para um dos endereços de email de relatório e verifique os resultados.</span><span class="sxs-lookup"><span data-stu-id="3ca9e-150">Send a test messages to one of the reporting email addresses and verify the results.</span></span>