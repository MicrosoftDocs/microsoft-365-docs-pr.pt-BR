---
title: Usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a usar regras de fluxo de emails (também conhecidas como regras de transporte) para receber cópias das mensagens que os usuários reportam à Microsoft.
ms.openlocfilehash: 2b1e82ece936551c48e5617955f546cf851a8913
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939494"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="30083-103">Usar regras de fluxo de emails para ver o que seus usuários estão relatando à Microsoft</span><span class="sxs-lookup"><span data-stu-id="30083-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="30083-104">Há várias maneiras de os usuários reportarem mensagens para a Microsoft para análise, conforme descrito em [mensagens e arquivos de relatório para a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="30083-104">There are multiple ways for users to report messages to Microsoft for analysis as described in [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

<span data-ttu-id="30083-105">Você pode criar uma regra de fluxo de emails (também conhecida como regra de transporte) que procura mensagens que os usuários relatam à Microsoft, e você pode configurar destinatários Cco para receber cópias dessas mensagens relatadas.</span><span class="sxs-lookup"><span data-stu-id="30083-105">You can create a mail flow rule (also known as a transport rule) that looks for messages that users report to Microsoft, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="30083-106">Você pode criar a regra de fluxo de emails no centro de administração do Exchange (Eat) e no PowerShell (Exchange Online PowerShell para clientes do Microsoft 365; PowerShell de proteção do Exchange Online para clientes autônomos do EOP).</span><span class="sxs-lookup"><span data-stu-id="30083-106">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="30083-107">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="30083-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="30083-108">Você precisa receber permissões no Exchange Online ou no EOP antes de poder executar estes procedimentos.</span><span class="sxs-lookup"><span data-stu-id="30083-108">You need to be assigned permissions in Exchange Online or EOP before you can do these procedures.</span></span> <span data-ttu-id="30083-109">Especificamente, você precisa receber a função de **regras de transporte** , que é atribuída às funções de gerenciamento da **organização**, **Gerenciamento de conformidade**e gerenciamento de **registros** por padrão.</span><span class="sxs-lookup"><span data-stu-id="30083-109">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="30083-110">Para saber mais, confira [Gerenciar Grupos de Funções do Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="30083-110">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="30083-111">Para abrir o Eat, confira [centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) ou [no centro de administração do Exchange no Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="30083-111">To open the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center) or [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="30083-112">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="30083-112">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="30083-113">Para se conectar ao PowerShell da Proteção do Exchange Online autônoma, confira [Conectar ao PowerShell da Proteção do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="30083-113">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="30083-114">Para obter mais informações sobre regras de fluxo de emails no Exchange Online e EOP autônomos, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="30083-114">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="30083-115">Regras de fluxo de emails (regras de transporte) no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="30083-115">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="30083-116">Condições e exceções de regra de fluxo de emails (predicados) no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="30083-116">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="30083-117">Ações de regra de fluxo de email no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="30083-117">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="30083-118">Use o Eat para criar uma regra de fluxo de emails para receber cópias de mensagens relatadas</span><span class="sxs-lookup"><span data-stu-id="30083-118">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="30083-119">No EAC, vá para **Fluxo de emails** \> **Regras**.</span><span class="sxs-lookup"><span data-stu-id="30083-119">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="30083-120">Clique em **Adicionar** ![ícone](../../media/ITPro-EAC-AddIcon.png) de adição e selecione **criar uma nova regra**.</span><span class="sxs-lookup"><span data-stu-id="30083-120">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="30083-121">Na página **nova regra** que é aberta, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="30083-121">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="30083-122">**Name**: Insira um nome exclusivo e descritivo para a regra.</span><span class="sxs-lookup"><span data-stu-id="30083-122">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="30083-123">Por exemplo, as mensagens Cco relatadas para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="30083-123">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="30083-124">Clique em **mais opções**.</span><span class="sxs-lookup"><span data-stu-id="30083-124">Click **More Options**.</span></span>

   - <span data-ttu-id="30083-125">**Aplicar esta regra se**: selecione **o** \> **endereço do destinatário inclui qualquer uma destas palavras**: na caixa de diálogo **especificar palavras ou expressões** que aparece, insira um dos seguintes valores, clique em **Adicionar** ![ícone](../../media/ITPro-EAC-AddIcon.png)de adição e repita até inserir todos os valores.</span><span class="sxs-lookup"><span data-stu-id="30083-125">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="30083-126">Para editar uma entrada, selecione-a e **Edit** ![clique em Editar](../../media/ITPro-EAC-EditIcon.png)ícone de edição.</span><span class="sxs-lookup"><span data-stu-id="30083-126">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="30083-127">Para remover uma entrada, selecione-a e **Remove** ![clique em Remover](../../media/ITPro-EAC-DeleteIcon.png)ícone Remover.</span><span class="sxs-lookup"><span data-stu-id="30083-127">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="30083-128">Quando tiver concluído, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="30083-128">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="30083-129">**Faça o seguinte**: selecione **Adicionar destinatários** \> **à caixa Cco**.</span><span class="sxs-lookup"><span data-stu-id="30083-129">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="30083-130">Na caixa de diálogo exibida, localize e selecione os destinatários que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="30083-130">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="30083-131">Quando tiver concluído, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="30083-131">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="30083-132">Você pode fazer seleções adicionais para auditar a regra, testar a regra, ativar a regra durante um período de tempo específico e outras configurações.</span><span class="sxs-lookup"><span data-stu-id="30083-132">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="30083-133">Recomendamos testar a regra antes de aplicá-la.</span><span class="sxs-lookup"><span data-stu-id="30083-133">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="30083-134">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="30083-134">When you're finished, click **Save**.</span></span>

## <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="30083-135">Use o PowerShell para criar uma regra de fluxo de emails para receber cópias de mensagens relatadas</span><span class="sxs-lookup"><span data-stu-id="30083-135">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="30083-136">Este exemplo cria uma nova regra de fluxo de emails chamada Cco mensagens relatadas à Microsoft que procura mensagens de email relatadas à Microsoft usando os métodos descritos neste tópico e adiciona os usuários laura@contoso.com e julia@contoso.com como destinatários Cco.</span><span class="sxs-lookup"><span data-stu-id="30083-136">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="30083-137">Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="30083-137">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="30083-138">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="30083-138">How do you know this worked?</span></span>

<span data-ttu-id="30083-139">Para verificar se você configurou uma regra de fluxo de emails para receber cópias de mensagens relatadas, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="30083-139">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="30083-140">No Eat, vá para **regras** \> de fluxo \> de **emails** selecione \> a regra clique em](../../media/ITPro-EAC-EditIcon.png) **Editar** ![ícone de edição e verifique as configurações.</span><span class="sxs-lookup"><span data-stu-id="30083-140">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="30083-141">No PowerShell, execute o seguinte comando para verificar as configurações:</span><span class="sxs-lookup"><span data-stu-id="30083-141">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="30083-142">Envie uma mensagem de teste para um dos endereços de email de relatório e verifique os resultados.</span><span class="sxs-lookup"><span data-stu-id="30083-142">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
