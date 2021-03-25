---
title: Usar regras de fluxo de emails para filtrar emails em massa
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
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a usar regras de fluxo de emails (regras de transporte) para identificar e filtrar emails em massa (email cinza) no Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c86f229d6c7371854878a67937cc38374ed00961
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203112"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="5bb5b-103">Usar regras de fluxo de email para filtrar emails em massa no EOP</span><span class="sxs-lookup"><span data-stu-id="5bb5b-103">Use mail flow rules to filter bulk email in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5bb5b-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="5bb5b-104">**Applies to**</span></span>
- [<span data-ttu-id="5bb5b-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5bb5b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5bb5b-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="5bb5b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5bb5b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5bb5b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="5bb5b-108">Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP usa políticas anti-spam (também conhecidas como políticas de filtro de spam ou políticas de filtro de conteúdo) para verificar mensagens de entrada para spam e email em massa (também conhecido como email cinza).</span><span class="sxs-lookup"><span data-stu-id="5bb5b-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="5bb5b-109">Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5bb5b-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="5bb5b-110">Se quiser mais opções para filtrar emails em massa, você pode criar regras de fluxo de emails (também conhecidas como regras de transporte) para pesquisar padrões de texto ou frases que são encontradas com frequência em emails em massa e marcar essas mensagens como spam.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-110">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="5bb5b-111">Para obter mais informações sobre emails em massa, consulte Qual é a diferença entre lixo eletrônico e email em [massa?](what-s-the-difference-between-junk-email-and-bulk-email.md) e Nível de reclamação em massa [(BCL) no EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="5bb5b-111">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="5bb5b-112">Este tópico explica como criar essas regras de fluxo de emails no Centro de administração do Exchange (EAC) e no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="5bb5b-112">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5bb5b-113">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="5bb5b-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5bb5b-114">Você precisa ter permissões atribuídas no Exchange Online ou no Exchange Online Protection antes de poder fazer os procedimentos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-114">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="5bb5b-115">Especificamente, você precisa da função **Regras** de Transporte, que é atribuída aos  grupos de função Gerenciamento da **Organização,** Gerenciamento de **Conformidade** (administradores globais) e Gerenciamento de Registros por padrão.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-115">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="5bb5b-116">Para mais informações, confira os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="5bb5b-116">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="5bb5b-117">Permissões no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5bb5b-117">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="5bb5b-118">Permissões no EOP autônomo</span><span class="sxs-lookup"><span data-stu-id="5bb5b-118">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="5bb5b-119">Usar o EAC modificar a lista de membros em grupos de função</span><span class="sxs-lookup"><span data-stu-id="5bb5b-119">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="5bb5b-120">Para abrir o EAC no Exchange Online, consulte [Centro de administração do Exchange no Exchange Online](/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="5bb5b-120">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="5bb5b-121">Para abrir o EAC no EOP autônomo, consulte Centro de administração [do Exchange no EOP](exchange-admin-center-in-exchange-online-protection-eop.md)autônomo .</span><span class="sxs-lookup"><span data-stu-id="5bb5b-121">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="5bb5b-122">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="5bb5b-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="5bb5b-123">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="5bb5b-123">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="5bb5b-124">Para obter mais informações sobre regras de fluxo de emails no Exchange Online e no EOP autônomo, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="5bb5b-124">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="5bb5b-125">Regras de fluxo de emails (regras de transporte) no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5bb5b-125">Mail flow rules (transport rules) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="5bb5b-126">Condições e exceções de regra de fluxo de email (predicados) no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5bb5b-126">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="5bb5b-127">Ações de regra de fluxo de emails no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5bb5b-127">Mail flow rule actions in Exchange Online</span></span>](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="5bb5b-128">A lista de palavras e padrões de texto usados para identificar emails em massa nos exemplos não é exaustiva; você pode adicionar e remover entradas conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-128">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="5bb5b-129">No entanto, eles são um bom ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-129">However, they are a good starting point.</span></span>

- <span data-ttu-id="5bb5b-p107">A pesquisa de palavras ou padrões de texto nos campos de cabeçalho assunto ou outros na mensagem ocorre *após* a mensagem ter sido decodificada do método de codificação de transferência de conteúdo MIME, usado para transmitir a mensagem binária entre os servidores SMTP em texto ASCII. Não é possível usar condições ou exceções para buscar os valores codificados brutos (tipicamente com base64) dos campos de cabeçalho assunto ou outros nas mensagens.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-p107">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="5bb5b-132">Os procedimentos a seguir marcam uma mensagem em massa como spam para toda a organização.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-132">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="5bb5b-133">No entanto, você pode adicionar outra condição para aplicar essas regras somente a destinatários específicos, para que você possa usar a filtragem agressiva em alguns usuários altamente direcionados, enquanto o restante dos seus usuários (que, na maioria das vezes, recebe o email em massa para o qual se inscreveu) não é afetado.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-133">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="5bb5b-134">Usar o EAC para criar regras de fluxo de emails que filtram emails em massa</span><span class="sxs-lookup"><span data-stu-id="5bb5b-134">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="5bb5b-135">No EAC, vá para **Fluxo de emails** \> **Regras**.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-135">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="5bb5b-136">Clique **em Adicionar** ícone e selecione Criar uma nova ![ ](../../media/ITPro-EAC-AddIcon.png) **regra.**</span><span class="sxs-lookup"><span data-stu-id="5bb5b-136">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="5bb5b-137">Na página **Nova regra** que é aberta, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="5bb5b-137">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="5bb5b-138">**Nome**: Insira um nome exclusivo e descritivo para a regra.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-138">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="5bb5b-139">Clique **em Mais Opções**.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-139">Click **More Options**.</span></span>

   - <span data-ttu-id="5bb5b-140">**Aplique essa regra se**: Configurar uma das seguintes configurações para procurar conteúdo em mensagens usando expressões regulares (RegEx) ou palavras ou frases:</span><span class="sxs-lookup"><span data-stu-id="5bb5b-140">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="5bb5b-141">**O assunto ou o corpo** \> **subject ou body** corresponde a esses padrões de texto : na caixa de diálogo Especificar palavras ou **frases** que aparece, insira um dos seguintes valores, clique em **Adicionar** Ícone e repita até que você tenha inserido todos os ![ ](../../media/ITPro-EAC-AddIcon.png) valores.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-141">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `<img height="?1"? width="?1"? src=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      <span data-ttu-id="5bb5b-142">Para editar uma entrada, selecione-a e clique em **Editar** ![ ícone ](../../media/ITPro-EAC-EditIcon.png) editar.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-142">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="5bb5b-143">Para remover uma entrada, selecione-a e clique em **Remover** ![ ícone ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="5bb5b-143">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="5bb5b-144">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-144">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="5bb5b-145">**O assunto ou o corpo** \> **subject or body includes** any of these words : In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** Add Icon , and repeat ![ until you've entered all the ](../../media/ITPro-EAC-AddIcon.png) values.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-145">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `to change your preferences or unsubscribe`
       - `Modify email preferences or unsubscribe`
       - `This is a promotional email`
       - `You are receiving this email because you requested a subscription`
       - `click here to unsubscribe`
       - `You have received this email because you are subscribed`
       - `If you no longer wish to receive our email newsletter`
       - `to unsubscribe from this newsletter`
       - `If you have trouble viewing this email`
       - `This is an advertisement`
       - `you would like to unsubscribe or change your`
       - `view this email as a webpage`
       - `You are receiving this email because you are subscribed`

      <span data-ttu-id="5bb5b-146">Para editar uma entrada, selecione-a e clique em **Editar** ![ ícone ](../../media/ITPro-EAC-EditIcon.png) editar.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-146">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="5bb5b-147">Para remover uma entrada, selecione-a e clique em **Remover** ![ ícone ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="5bb5b-147">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="5bb5b-148">Quando terminar, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-148">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="5bb5b-149">**Faça o seguinte:** Selecione **Modificar as propriedades da mensagem** definir o nível de confiança de spam \> **(SCL)**.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-149">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="5bb5b-150">Na caixa **de diálogo Especificar SCL** exibida, configure uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="5bb5b-150">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="5bb5b-151">Para marcar mensagens como **Spam,** selecione **6**.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-151">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="5bb5b-152">A ação que você configurou para vereditos de filtragem de **spam** em suas políticas anti-spam é aplicada às mensagens (o valor padrão é Mover mensagem para a pasta **Lixo Eletrônico**).</span><span class="sxs-lookup"><span data-stu-id="5bb5b-152">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="5bb5b-153">Para marcar mensagens como **spam de alta confiança,** selecione **9**.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-153">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="5bb5b-154">A ação que você configurou para vereditos de filtragem de **spam** de alta confiança em suas políticas anti-spam é aplicada às mensagens (o valor padrão é Mover mensagem para a pasta Lixo **Eletrônico**).</span><span class="sxs-lookup"><span data-stu-id="5bb5b-154">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="5bb5b-155">Para obter mais informações sobre valores de SCL, consulte Nível de confiança [de spam (SCL) no EOP](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="5bb5b-155">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="5bb5b-156">Quando terminar, clique em **Salvar**</span><span class="sxs-lookup"><span data-stu-id="5bb5b-156">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="5bb5b-157">Usar o PowerShell para criar regras de fluxo de emails que filtram emails em massa</span><span class="sxs-lookup"><span data-stu-id="5bb5b-157">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="5bb5b-158">Use a sintaxe a seguir para criar uma ou ambas as regras de fluxo de emails (expressões regulares versus palavras):</span><span class="sxs-lookup"><span data-stu-id="5bb5b-158">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPhrase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="5bb5b-159">Este exemplo cria uma nova regra chamada "Filtragem de email em massa - RegEx" que usa a mesma lista de expressões regulares de anteriormente no tópico para definir mensagens como **Spam**.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-159">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? src=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="5bb5b-160">Este exemplo cria uma nova regra chamada "Filtragem de email em massa - Palavras" que usa a mesma lista de palavras de anteriormente no tópico para definir mensagens como spam de alta **confiança.**</span><span class="sxs-lookup"><span data-stu-id="5bb5b-160">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="5bb5b-161">Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](/powershell/module/exchange/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="5bb5b-161">For detailed syntax and parameter information, see [New-TransportRule](/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="5bb5b-162">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="5bb5b-162">How do you know this worked?</span></span>

<span data-ttu-id="5bb5b-163">Para verificar se você configurou regras de fluxo de emails para filtrar emails em massa, faça qualquer uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="5bb5b-163">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="5bb5b-164">No EAC, vá para **Regras de fluxo de** email selecione a regra clique em \>  \> \> **Editar** ícone editar e verifique ![ as ](../../media/ITPro-EAC-EditIcon.png) configurações.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-164">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="5bb5b-165">No PowerShell, substitua pelo nome da regra e execute \<Rule Name\> o seguinte comando para verificar as configurações:</span><span class="sxs-lookup"><span data-stu-id="5bb5b-165">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="5bb5b-166">De uma conta externa, envie uma mensagem de teste para um destinatário afetado que contém uma das frases ou padrões de texto e verifique os resultados.</span><span class="sxs-lookup"><span data-stu-id="5bb5b-166">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>