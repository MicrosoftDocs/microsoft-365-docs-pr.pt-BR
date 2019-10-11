---
title: Usar regras de fluxo de email para configurar a filtragem de email em massa no Exchange Online Protection
ms.author: tracyp
author: MSFTTracyP
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
description: Os administradores podem aprender a usar regras de fluxo de email no Exchange Online Protection para filtragem de email em massa.
ms.openlocfilehash: 557a12455284519cc224cbee5e40a564aa3d4f14
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441139"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a><span data-ttu-id="ac833-103">Usar regras de fluxo de email para configurar a filtragem de email em massa no Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="ac833-103">Use mail flow rules to configure bulk email filtering in Exchange Online Protection</span></span>

<span data-ttu-id="ac833-104">Você pode definir filtros de conteúdo para toda a empresa para spam e email em massa usando as políticas padrão de filtro de conteúdo de spam.</span><span class="sxs-lookup"><span data-stu-id="ac833-104">You can set company-wide content filters for spam and bulk email using the default spam content-filter policies.</span></span> <span data-ttu-id="ac833-105">Confira [configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md) e [set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) em como definir as políticas de filtro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ac833-105">Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) and [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) on how to set the content filter policies.</span></span>

<span data-ttu-id="ac833-106">Se você quiser mais opções para filtrar mensagens em massa, você pode criar regras de fluxo de emails (também conhecidas como regras de transporte) para procurar padrões de texto ou frases freqüentemente encontradas em emails em massa.</span><span class="sxs-lookup"><span data-stu-id="ac833-106">If you want to more options to filter bulk messages, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases frequently found in bulk emails.</span></span> <span data-ttu-id="ac833-107">Qualquer mensagem que contenha essas características será marcada como spam.</span><span class="sxs-lookup"><span data-stu-id="ac833-107">Any message containing these characteristics will be marked as spam.</span></span> <span data-ttu-id="ac833-108">O uso dessas regras pode ajudar a reduzir a quantidade de emails em massa indesejados que sua organização recebe.</span><span class="sxs-lookup"><span data-stu-id="ac833-108">Using these rules can help reduce the amount of unwanted bulk email your organization receives.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac833-109">Antes de criar as regras de fluxo de emails documentadas neste tópico, recomendamos que você leia primeiro [qual é a diferença entre lixo eletrônico e email em massa?](what-s-the-difference-between-junk-email-and-bulk-email.md) e [valores de nível de reclamação em massa](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="ac833-109">Before creating the mail flow rules documented this topic, we recommend that you first read [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk Complaint Level values](bulk-complaint-level-values.md).</span></span><br>
> <span data-ttu-id="ac833-110">Os seguintes procedimentos marcam uma mensagem como spam para toda a sua organização.</span><span class="sxs-lookup"><span data-stu-id="ac833-110">The following procedures mark a message as spam for your entire organization.</span></span> <span data-ttu-id="ac833-111">No entanto, você pode adicionar outra condição para aplicar essas regras somente a destinatários específicos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ac833-111">However, you can add another condition to apply these rules only to specific recipients in your organization.</span></span> <span data-ttu-id="ac833-112">Dessa forma, as configurações agressivas de filtragem de email em massa podem ser aplicadas a alguns usuários altamente direcionados, enquanto o restante de seus usuários (que recebem principalmente o email em massa que eles se inscreveram) não são afetados.</span><span class="sxs-lookup"><span data-stu-id="ac833-112">This way, the aggressive bulk email filtering settings can apply to a few users who are highly targeted, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span>

## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a><span data-ttu-id="ac833-113">Criar uma regra de fluxo de emails para filtrar mensagens de email em massa com base em padrões de texto</span><span class="sxs-lookup"><span data-stu-id="ac833-113">Create a mail flow rule to filter bulk email messages based on text patterns</span></span>

1. <span data-ttu-id="ac833-114">No Centro de administração do Exchange (EAC), acesse **Fluxo de emails** \> **Regras**.</span><span class="sxs-lookup"><span data-stu-id="ac833-114">In the Exchange admin center (EAC), go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="ac833-115">Clique em **Adicionar** ![ícone](../media/ITPro-EAC-AddIcon.gif) de adição e selecione **criar uma nova regra**.</span><span class="sxs-lookup"><span data-stu-id="ac833-115">Click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="ac833-116">Especifique um nome para a regra.</span><span class="sxs-lookup"><span data-stu-id="ac833-116">Specify a name for the rule.</span></span>

4. <span data-ttu-id="ac833-117">Clique em **mais opções** ![ícone](../media/ITPro-EAC-MoreOptionsIcon.png)de mais opções.</span><span class="sxs-lookup"><span data-stu-id="ac833-117">Click **More options** ![More options icon](../media/ITPro-EAC-MoreOptionsIcon.png).</span></span> <span data-ttu-id="ac833-118">Em **aplicar esta regra se**, selecione **o assunto ou o** \> **assunto ou o corpo corresponde a esses padrões de texto**.</span><span class="sxs-lookup"><span data-stu-id="ac833-118">Under **Apply this rule if**, select **The subject or body** \> **subject or body matches these text patterns**.</span></span>

5. <span data-ttu-id="ac833-119">Na caixa de diálogo **especificar palavras ou frases** , adicione as seguintes expressões regulares comumente encontradas em emails em massa, uma de cada vez, e clique em **OK** quando tiver concluído:</span><span class="sxs-lookup"><span data-stu-id="ac833-119">In the **specify words or phrases** dialog box, add the following regular expressions commonly found in bulk emails, one at a time, and click **OK** when you're done:</span></span>

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

   <span data-ttu-id="ac833-120">A lista acima não é um conjunto completo de expressões regulares encontradas em emails em massa; é possível adicionar ou remover mais, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ac833-120">The above list isn't an exhaustive set of regular expressions found in bulk emails; more can be added or removed as needed.</span></span> <span data-ttu-id="ac833-121">Entretanto, é um bom ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="ac833-121">However, it's a good starting point.</span></span>

   <span data-ttu-id="ac833-p106">A pesquisa de palavras ou padrões de texto nos campos de cabeçalho assunto ou outros na mensagem ocorre *após* a mensagem ter sido decodificada do método de codificação de transferência de conteúdo MIME, usado para transmitir a mensagem binária entre os servidores SMTP em texto ASCII. Não é possível usar condições ou exceções para buscar os valores codificados brutos (tipicamente com base64) dos campos de cabeçalho assunto ou outros nas mensagens.</span><span class="sxs-lookup"><span data-stu-id="ac833-p106">The search for words or text patterns in the subject or other header fields in the message occurs *after* the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text. You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span>

6. <span data-ttu-id="ac833-124">Em **Execute a ação a seguir**, selecione **Modificar as propriedades da mensagem** \> **definir o SCL (nível de confiança de spam)**.</span><span class="sxs-lookup"><span data-stu-id="ac833-124">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>

7. <span data-ttu-id="ac833-125">Na caixa de diálogo **especificar SCL**, defina o SCL como **5**, **6** ou **9** e clique em **ok**.</span><span class="sxs-lookup"><span data-stu-id="ac833-125">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>

   <span data-ttu-id="ac833-126">Configurar o SCL como 5 ou 6 executa a ação **Spam**; configurar o SCL como 9 executa a ação **Spam de alta confiança**, conforme definido na política de filtro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ac833-126">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy.</span></span> <span data-ttu-id="ac833-127">O serviço executará a ação definida na política de filtro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ac833-127">The service will perform the action set in the content filter policy.</span></span> <span data-ttu-id="ac833-128">A ação padrão é entregar a mensagem para a pasta lixo eletrônico dos destinatários, mas ações diferentes podem ser configuradas conforme descrito em [configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ac833-128">The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

   <span data-ttu-id="ac833-129">Se sua ação configurada for colocar em quarentena a mensagem em vez de enviá-la para a pasta lixo eletrônico dos destinatários, a mensagem será enviada para a quarentena do administrador como uma correspondência de regra de fluxo de email e não estará disponível na quarentena de spam do usuário final ou via usuário final notificações de spam.</span><span class="sxs-lookup"><span data-stu-id="ac833-129">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span>

   <span data-ttu-id="ac833-130">Para saber mais sobre os valores de SCL do serviço, veja [Níveis de confiança de spam](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ac833-130">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

8. <span data-ttu-id="ac833-131">Salve a regra.</span><span class="sxs-lookup"><span data-stu-id="ac833-131">Save the rule.</span></span>

## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a><span data-ttu-id="ac833-132">Criar uma regra de fluxo de emails para filtrar mensagens de email em massa com base em frases</span><span class="sxs-lookup"><span data-stu-id="ac833-132">Create a mail flow rule to filter bulk email messages based on phrases</span></span>

1. <span data-ttu-id="ac833-133">No EAC, vá para **Fluxo de emails** \> **Regras**.</span><span class="sxs-lookup"><span data-stu-id="ac833-133">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="ac833-134">Clique em **Adicionar** ![ícone](../media/ITPro-EAC-AddIcon.gif) de adição e selecione **criar uma nova regra**.</span><span class="sxs-lookup"><span data-stu-id="ac833-134">Click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="ac833-135">Especifique um nome para a regra.</span><span class="sxs-lookup"><span data-stu-id="ac833-135">Specify a name for the rule.</span></span>

4. <span data-ttu-id="ac833-136">Clique em **Mais opções**.</span><span class="sxs-lookup"><span data-stu-id="ac833-136">Click **More options**.</span></span> <span data-ttu-id="ac833-137">Em **aplicar esta regra se**, selecione **o assunto ou o** \> **assunto ou o corpo da mensagem inclui qualquer uma destas palavras**.</span><span class="sxs-lookup"><span data-stu-id="ac833-137">Under **Apply this rule if**, select **The subject or body** \> **subject or body includes any of these words**.</span></span>

5. <span data-ttu-id="ac833-138">Na caixa de diálogo **especificar palavras ou expressões**, adicione, uma de cada vez, as seguintes frases comuns encontradas em emails em massa e clique em **ok** quando tiver concluído:</span><span class="sxs-lookup"><span data-stu-id="ac833-138">In the **specify words or phrases** dialog box, add the following phrases commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span>

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

   <span data-ttu-id="ac833-139">Essa lista não é um conjunto exaustivo de frases encontradas em emails em massa; é possível adicionar ou remover mais, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ac833-139">This list isn't an exhaustive set of phrases found in bulk emails; more can be added or removed as needed.</span></span> <span data-ttu-id="ac833-140">Entretanto, é um bom ponto de partida.</span><span class="sxs-lookup"><span data-stu-id="ac833-140">However, it's a good starting point.</span></span>

6. <span data-ttu-id="ac833-141">Em **Execute a ação a seguir**, selecione **Modificar as propriedades da mensagem** \> **definir o SCL (nível de confiança de spam)**.</span><span class="sxs-lookup"><span data-stu-id="ac833-141">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>

7. <span data-ttu-id="ac833-142">Na caixa de diálogo **especificar SCL**, defina o SCL como **5**, **6** ou **9** e clique em **ok**.</span><span class="sxs-lookup"><span data-stu-id="ac833-142">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>

   <span data-ttu-id="ac833-143">Configurar o SCL como 5 ou 6 executa a ação **Spam**; configurar o SCL como 9 executa a ação **Spam de alta confiança**, conforme definido na política de filtro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ac833-143">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy.</span></span> <span data-ttu-id="ac833-144">O serviço executará a ação definida na política de filtro de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="ac833-144">The service will perform the action set in the content filter policy.</span></span> <span data-ttu-id="ac833-145">A ação padrão é entregar a mensagem para a pasta lixo eletrônico dos destinatários, mas ações diferentes podem ser configuradas conforme descrito em [configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ac833-145">The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>

   <span data-ttu-id="ac833-146">Se sua ação configurada for colocar em quarentena a mensagem em vez de enviá-la para a pasta lixo eletrônico dos destinatários, a mensagem será enviada para a quarentena do administrador como uma correspondência de regra de fluxo de email e não estará disponível na quarentena de spam do usuário final ou via usuário final notificações de spam.</span><span class="sxs-lookup"><span data-stu-id="ac833-146">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span>

   <span data-ttu-id="ac833-147">Para saber mais sobre os valores de SCL do serviço, veja [Níveis de confiança de spam](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ac833-147">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

8. <span data-ttu-id="ac833-148">Salve a regra.</span><span class="sxs-lookup"><span data-stu-id="ac833-148">Save the rule.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="ac833-149">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="ac833-149">For more information</span></span>

[<span data-ttu-id="ac833-150">Qual é a diferença entre lixo eletrônico e email em massa?</span><span class="sxs-lookup"><span data-stu-id="ac833-150">What's the difference between junk email and bulk email?</span></span>](what-s-the-difference-between-junk-email-and-bulk-email.md)

[<span data-ttu-id="ac833-151">Valores de nível de reclamação em massa</span><span class="sxs-lookup"><span data-stu-id="ac833-151">Bulk Complaint Level values</span></span>](bulk-complaint-level-values.md)

[<span data-ttu-id="ac833-152">Configurar suas políticas de filtro de spam</span><span class="sxs-lookup"><span data-stu-id="ac833-152">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="ac833-153">Opções avançadas de filtragem de spam</span><span class="sxs-lookup"><span data-stu-id="ac833-153">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
