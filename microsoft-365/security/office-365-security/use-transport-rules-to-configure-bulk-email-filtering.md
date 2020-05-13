---
title: Usar regras de fluxo de email para filtrar emails em massa
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
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a usar regras de fluxo de emails (regras de transporte) para identificar e filtrar emails em massa (emails cinza) na proteção do Exchange Online (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a31030ea2f844cdeb4bee68bf748a2ab8ca29dad
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213359"
---
# <a name="use-mail-flow-rules-to-filter-bulk-email-in-eop"></a><span data-ttu-id="70c5a-103">Usar regras de fluxo de email para filtrar emails em massa no EOP</span><span class="sxs-lookup"><span data-stu-id="70c5a-103">Use mail flow rules to filter bulk email in EOP</span></span>

<span data-ttu-id="70c5a-104">Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP usa políticas antispam (também conhecidas como políticas de filtro de spam ou políticas de filtro de conteúdo) para examinar mensagens de entrada para spam e emails em massa (também conhecido como email cinza).</span><span class="sxs-lookup"><span data-stu-id="70c5a-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam and bulk mail (also known as gray mail).</span></span> <span data-ttu-id="70c5a-105">Para obter mais informações, consulte [Configure anti-spam Policies in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="70c5a-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="70c5a-106">Se quiser mais opções para filtrar emails em massa, você poderá criar regras de fluxo de emails (também conhecidas como regras de transporte) para procurar padrões de texto ou frases que sejam frequentemente encontradas em emails em massa e marcar essas mensagens como spam.</span><span class="sxs-lookup"><span data-stu-id="70c5a-106">If you want more options to filter bulk mail, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases that are frequently found in bulk mail, and mark those messages as spam.</span></span> <span data-ttu-id="70c5a-107">Para saber mais sobre emails em massa, confira [a diferença entre lixo eletrônico e email em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md) e [BCL (nível de reclamação em massa) no EOP](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="70c5a-107">For more information about bulk mail, see [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk complaint level (BCL) in EOP](bulk-complaint-level-values.md).</span></span>

<span data-ttu-id="70c5a-108">Este tópico explica como criar essas regras de fluxo de email no centro de administração do Exchange (Eat) e no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).</span><span class="sxs-lookup"><span data-stu-id="70c5a-108">This topic explains how create these mail flow rules in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="70c5a-109">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="70c5a-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="70c5a-110">Você precisa ter permissões para poder executar estes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="70c5a-110">You need to be assigned permissions before you can do these procedures:</span></span>

  - <span data-ttu-id="70c5a-111">No Exchange Online, consulte o entrada "fluxo de email" em [permissões de recurso no Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).</span><span class="sxs-lookup"><span data-stu-id="70c5a-111">In Exchange Online, see the "Mail flow" entry in [Feature Permissions in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/feature-permissions).</span></span>
  
  - <span data-ttu-id="70c5a-112">Em EOP autônomo, você precisa da função de regras de transporte, que é atribuída às funções gerenciamento, ComplianceManagement e RecordsManagement por padrão.</span><span class="sxs-lookup"><span data-stu-id="70c5a-112">In standalone EOP, you need the Transport Rules role, which is assigned to the OrganizationManagement, ComplianceManagement, and RecordsManagement roles by default.</span></span> <span data-ttu-id="70c5a-113">Para obter mais informações, consulte [permissões em EOP autônomos](feature-permissions-in-eop.md) e [use o Eat modificar a lista de membros nos grupos de função](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span><span class="sxs-lookup"><span data-stu-id="70c5a-113">For more information, see [Permissions in standalone EOP](feature-permissions-in-eop.md) and [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).</span></span>

- <span data-ttu-id="70c5a-114">Para abrir o Eat no Exchange Online, confira [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="70c5a-114">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="70c5a-115">Para abrir o Eat no EOP autônomo, confira [centro de administração do Exchange no EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md).</span><span class="sxs-lookup"><span data-stu-id="70c5a-115">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="70c5a-116">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="70c5a-116">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="70c5a-117">Para se conectar ao PowerShell do EOP autônomo, confira [conectar-se ao PowerShell do Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="70c5a-117">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="70c5a-118">Para obter mais informações sobre regras de fluxo de emails no Exchange Online e EOP autônomos, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="70c5a-118">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="70c5a-119">Regras de fluxo de emails (regras de transporte) no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="70c5a-119">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="70c5a-120">Condições e exceções de regra de fluxo de emails (predicados) no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="70c5a-120">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="70c5a-121">Ações de regra de fluxo de email no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="70c5a-121">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- <span data-ttu-id="70c5a-122">A lista de palavras e padrões de texto usados para identificar emails em massa nos exemplos não são exaustivas; Você pode adicionar e remover entradas, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="70c5a-122">The list of words and text patterns that are used to identify bulk mail in the examples aren't exhaustive; you can add and remove entries as necessary.</span></span> <span data-ttu-id="70c5a-123">No entanto, eles são um bom ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="70c5a-123">However, they are a good starting point.</span></span>

- <span data-ttu-id="70c5a-p107">A pesquisa de palavras ou padrões de texto nos campos de cabeçalho assunto ou outros na mensagem ocorre *após* a mensagem ter sido decodificada do método de codificação de transferência de conteúdo MIME, usado para transmitir a mensagem binária entre os servidores SMTP em texto ASCII. Não é possível usar condições ou exceções para buscar os valores codificados brutos (tipicamente com base64) dos campos de cabeçalho assunto ou outros nas mensagens.</span><span class="sxs-lookup"><span data-stu-id="70c5a-p107">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

- <span data-ttu-id="70c5a-126">Os procedimentos a seguir marcam uma mensagem em massa como spam para toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="70c5a-126">The following procedures mark a bulk message as spam for your entire organization.</span></span> <span data-ttu-id="70c5a-127">No entanto, você pode adicionar outra condição para aplicar essas regras somente a destinatários específicos, de modo que você possa usar a filtragem agressiva em alguns usuários altamente direcionados, enquanto o restante de seus usuários (que recebem principalmente o email em massa que eles se inscreveram) não são afetados.</span><span class="sxs-lookup"><span data-stu-id="70c5a-127">However, you can add another condition to apply these rules only to specific recipients, so you can use aggressive filtering on a few, highly targeted users, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="use-the-eac-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="70c5a-128">Use o Eat para criar regras de fluxo de email que filtram emails em massa</span><span class="sxs-lookup"><span data-stu-id="70c5a-128">Use the EAC to create mail flow rules that filter bulk email</span></span>

1. <span data-ttu-id="70c5a-129">No EAC, vá para **Fluxo de emails** \> **Regras**.</span><span class="sxs-lookup"><span data-stu-id="70c5a-129">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="70c5a-130">Clique em **Adicionar** ![ ícone ](../../media/ITPro-EAC-AddIcon.png) de adição e selecione **criar uma nova regra**.</span><span class="sxs-lookup"><span data-stu-id="70c5a-130">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="70c5a-131">Na página **nova regra** que é aberta, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="70c5a-131">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="70c5a-132">**Name**: Insira um nome exclusivo e descritivo para a regra.</span><span class="sxs-lookup"><span data-stu-id="70c5a-132">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="70c5a-133">Clique em **mais opções**.</span><span class="sxs-lookup"><span data-stu-id="70c5a-133">Click **More Options**.</span></span>

   - <span data-ttu-id="70c5a-134">**Aplique esta regra se**: Configure uma das seguintes configurações para procurar conteúdo em mensagens usando expressões regulares (Regex) ou palavras ou frases:</span><span class="sxs-lookup"><span data-stu-id="70c5a-134">**Apply this rule if**: Configure one of the following settings to look for content in messages using regular expressions (RegEx) or words or phrases:</span></span>

     - <span data-ttu-id="70c5a-135">**O assunto ou corpo** \> o **assunto ou o corpo corresponde a estes padrões de texto**: na caixa de diálogo **especificar palavras ou frases** que aparece, insira um dos seguintes valores, clique em **Adicionar** ![ ícone de adição ](../../media/ITPro-EAC-AddIcon.png) e repita até inserir todos os valores.</span><span class="sxs-lookup"><span data-stu-id="70c5a-135">**The subject or body** \> **subject or body matches these text patterns**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

       - `If you are unable to view the content of this email\, please`
       - `\>(safe )?unsubscribe( here)?\</a\>`
       - `If you do not wish to receive further communications like this\, please`
       - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
       - `To stop receiving these+emails\:http\://`
       - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
       - `no longer (wish )?(to )?(be sent|receive) w+ email`
       - `If you are unable to view the content of this email\, please click here`
       - `To ensure you receive (your daily deals|our e-?mails)\, add`
       - `If you no longer wish to receive these emails`
       - `to change your (subscription preferences|preferences or unsubscribe)`
       - `click (here to|the) unsubscribe`

      <span data-ttu-id="70c5a-136">Para editar uma entrada, selecione-a e clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="70c5a-136">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="70c5a-137">Para remover uma entrada, selecione-a e clique em **remover** ![ ícone Remover ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="70c5a-137">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="70c5a-138">Quando tiver concluído, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="70c5a-138">When you're finished, click **OK**.</span></span>

     - <span data-ttu-id="70c5a-139">**O assunto ou corpo** \> o **assunto ou o corpo inclui qualquer uma destas palavras**: na caixa de diálogo **especificar palavras ou frases** que aparece, insira um dos seguintes valores, clique em **Adicionar** ![ ícone ](../../media/ITPro-EAC-AddIcon.png) de adição e repita até inserir todos os valores.</span><span class="sxs-lookup"><span data-stu-id="70c5a-139">**The subject or body** \> **subject or body includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

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

      <span data-ttu-id="70c5a-140">Para editar uma entrada, selecione-a e clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="70c5a-140">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="70c5a-141">Para remover uma entrada, selecione-a e clique em **remover** ![ ícone Remover ](../../media/ITPro-EAC-DeleteIcon.png) .</span><span class="sxs-lookup"><span data-stu-id="70c5a-141">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

       <span data-ttu-id="70c5a-142">Quando tiver concluído, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="70c5a-142">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="70c5a-143">**Faça o seguinte**: selecione **modificar as propriedades da mensagem** \> **definem o nível de confiança de spam (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="70c5a-143">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="70c5a-144">Na caixa de diálogo **especificar SCL** que aparece, configure uma das seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="70c5a-144">In the **Specify SCL** dialog that appears, configure one of the following settings:</span></span>

     - <span data-ttu-id="70c5a-145">Para marcar mensagens como **spam**, selecione **6**.</span><span class="sxs-lookup"><span data-stu-id="70c5a-145">To mark messages as **Spam**, select **6**.</span></span> <span data-ttu-id="70c5a-146">A ação que você configurou para filtragem de **spam** verdicts em suas políticas antispam é aplicada às mensagens (o valor padrão é **mover mensagem para a pasta lixo eletrônico**).</span><span class="sxs-lookup"><span data-stu-id="70c5a-146">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

     - <span data-ttu-id="70c5a-147">Para marcar mensagens como **spam de alta confiança** , selecione **9**.</span><span class="sxs-lookup"><span data-stu-id="70c5a-147">To mark messages as **High confidence spam** select **9**.</span></span> <span data-ttu-id="70c5a-148">A ação que você configurou para a filtragem de **spam de alta confiança** verdicts nas políticas antispam é aplicada às mensagens (o valor padrão é **mover mensagem para a pasta lixo eletrônico**).</span><span class="sxs-lookup"><span data-stu-id="70c5a-148">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the messages (the default value is **Move message to Junk Email folder**).</span></span>

    <span data-ttu-id="70c5a-149">Para obter mais informações sobre os valores de SCL, consulte [nível de confiança de spam (SCL) no EOP](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="70c5a-149">For more information about SCL values, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

   <span data-ttu-id="70c5a-150">Quando tiver terminado, clique em **salvar**</span><span class="sxs-lookup"><span data-stu-id="70c5a-150">When you're finished, click **Save**</span></span>

## <a name="use-powershell-to-create-mail-flow-rules-that-filter-bulk-email"></a><span data-ttu-id="70c5a-151">Usar o PowerShell para criar regras de fluxo de email que filtram emails em massa</span><span class="sxs-lookup"><span data-stu-id="70c5a-151">Use PowerShell to create mail flow rules that filter bulk email</span></span>

<span data-ttu-id="70c5a-152">Use a seguinte sintaxe para criar uma ou ambas as regras de fluxo de emails (expressões regulares versus palavras):</span><span class="sxs-lookup"><span data-stu-id="70c5a-152">Use the following syntax to create one or both of the mail flow rules (regular expressions vs. words):</span></span>

```powershell
New-TransportRule -Name "<UniqueName>" [-SubjectOrBodyMatchesPatterns "<RegEx1>","<RegEx2>"...] [-SubjectOrBodyContainsWords "<WordOrPrhase1>","<WordOrPhrase2>"...] -SetSCL <6 | 9>
```

<span data-ttu-id="70c5a-153">Este exemplo cria uma nova regra chamada "filtragem de email em massa-RegEx" que usa a mesma lista de expressões regulares do tópico para definir mensagens como **spam**.</span><span class="sxs-lookup"><span data-stu-id="70c5a-153">This example creates a new rule named "Bulk email filtering - RegEx" that uses the same list of regular expressions from earlier in the topic to set messages as **Spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - RegEx" -SubjectOrBodyMatchesPatterns "If you are unable to view the content of this email\, please","\>(safe )?unsubscribe( here)?\</a\>","If you do not wish to receive further communications like this\, please","\<img height\="?1"? width\="?1"? sr\c=.?http\://","To stop receiving these+emails\:http\://","To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)","no longer (wish )?(to )?(be sent|receive) w+ email","If you are unable to view the content of this email\, please click here","To ensure you receive (your daily deals|our e-?mails)\, add","If you no longer wish to receive these emails","to change your (subscription preferences|preferences or unsubscribe)","click (here to|the) unsubscribe"... -SetSCL 6
```

<span data-ttu-id="70c5a-154">Este exemplo cria uma nova regra chamada "filtragem de email em massa-palavras" que usa a mesma lista de palavras do anterior no tópico para definir mensagens como **spam de alta confiança**.</span><span class="sxs-lookup"><span data-stu-id="70c5a-154">This example creates a new rule named "Bulk email filtering - Words" that uses the same list of words from earlier in the topic to set messages as **High confidence spam**.</span></span>

```powershell
New-TransportRule -Name "Bulk email filtering - Words" -SubjectOrBodyContainsWords "to change your preferences or unsubscribe","Modify email preferences or unsubscribe","This is a promotional email","You are receiving this email because you requested a subscription","click here to unsubscribe","You have received this email because you are subscribed","If you no longer wish to receive our email newsletter","to unsubscribe from this newsletter","If you have trouble viewing this email","This is an advertisement","you would like to unsubscribe or change your","view this email as a webpage","You are receiving this email because you are subscribed" -SetSCL 9
```

<span data-ttu-id="70c5a-155">Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="70c5a-155">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="70c5a-156">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="70c5a-156">How do you know this worked?</span></span>

<span data-ttu-id="70c5a-157">Para verificar se você configurou regras de fluxo de email para filtrar emails em massa, execute uma das seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="70c5a-157">To verify that you've configured mail flow rules to filter bulk email, do any of the following steps:</span></span>

- <span data-ttu-id="70c5a-158">No Eat, vá para regras de **fluxo de emails** \> **Rules** \> Selecione a regra \> clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) e verifique as configurações.</span><span class="sxs-lookup"><span data-stu-id="70c5a-158">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="70c5a-159">No PowerShell, substitua o \< nome \> da regra pelo nome da regra e execute o seguinte comando para verificar as configurações:</span><span class="sxs-lookup"><span data-stu-id="70c5a-159">In PowerShell, replace \<Rule Name\> with the name of the rule, and run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "<Rule Name>" | Format-List
  ```

- <span data-ttu-id="70c5a-160">A partir de uma conta externa, envie uma mensagem de teste para um destinatário afetado que contenha uma das frases ou padrões de texto e verifique os resultados.</span><span class="sxs-lookup"><span data-stu-id="70c5a-160">From an external account, send a test messages to an affected recipient that contains one of the phrases or text patterns, and verify the results.</span></span>
