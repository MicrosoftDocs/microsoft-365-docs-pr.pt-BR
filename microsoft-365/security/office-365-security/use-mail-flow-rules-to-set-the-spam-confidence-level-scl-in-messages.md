---
title: Usar regras de fluxo de emails para definir o SCL (nível de confiança de spam) em mensagens
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a definir o SCL de mensagens na proteção do Exchange Online.
ms.openlocfilehash: 35a1235ee8bbb1a61bf37c3cd29e06e62252351d
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871217"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a><span data-ttu-id="cec5e-103">Usar regras de fluxo de emails para definir o SCL (nível de confiança de spam) em mensagens</span><span class="sxs-lookup"><span data-stu-id="cec5e-103">Use mail flow rules to set the spam confidence level (SCL) in messages</span></span>

<span data-ttu-id="cec5e-104">Você pode criar uma regra de fluxo de emails (também conhecida como regra de transporte) que define o nível de confiança de spam (SCL) de uma mensagem de email.</span><span class="sxs-lookup"><span data-stu-id="cec5e-104">You can create a mail flow rule (also known as a transport rule) that sets the spam confidence level (SCL) of an email message.</span></span> <span data-ttu-id="cec5e-105">O SCL é uma medida da probabilidade de uma mensagem ser spam.</span><span class="sxs-lookup"><span data-stu-id="cec5e-105">The SCL is a measure of how likely a message is to be spam.</span></span> <span data-ttu-id="cec5e-106">Spam são mensagens de email não solicitadas (e normalmente indesejadas).</span><span class="sxs-lookup"><span data-stu-id="cec5e-106">Spam is unsolicited (and typically unwanted) email messages.</span></span> <span data-ttu-id="cec5e-107">O serviço executa ações diferentes em uma mensagem, dependendo da classificação de SCL.</span><span class="sxs-lookup"><span data-stu-id="cec5e-107">The service takes different action on a message depending on its SCL rating.</span></span> <span data-ttu-id="cec5e-108">Por exemplo, talvez você queira ignorar a filtragem de conteúdo de spam para mensagens enviadas de pessoas dentro da sua organização, pois você confia que uma mensagem enviada internamente por um colega não é spam.</span><span class="sxs-lookup"><span data-stu-id="cec5e-108">For example, you might want to bypass spam content filtering for messages that are sent from people inside your organization because you trust that a message sent internally from a colleague isn't spam.</span></span> <span data-ttu-id="cec5e-109">O uso de regras de fluxo de email para definir o valor de SCL de uma mensagem lhe dá maior controle no tratamento de spam.</span><span class="sxs-lookup"><span data-stu-id="cec5e-109">Using mail flow rules to set the SCL value of a message gives you increased control in handling spam.</span></span> 
  
 <span data-ttu-id="cec5e-110">**O que você precisa saber antes de começar?**</span><span class="sxs-lookup"><span data-stu-id="cec5e-110">**What do you need to know before you begin?**</span></span>
  
- <span data-ttu-id="cec5e-111">Tempo estimado para concluir este procedimento: 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="cec5e-111">Estimated time to complete this procedure: 10 minutes.</span></span>
    
- <span data-ttu-id="cec5e-112">Para executar este procedimento ou estes procedimentos, você precisa receber permissões.</span><span class="sxs-lookup"><span data-stu-id="cec5e-112">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="cec5e-113">Para ver de que permissões você precisa, consulte o entrada "regras de fluxo de email" em [permissões de recurso no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) ou [permissões de recurso no EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="cec5e-113">To see what permissions you need, see the "Mail flow rules" entry in [Feature Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) or [Feature permissions in EOP](feature-permissions-in-eop.md).</span></span> 
    
- <span data-ttu-id="cec5e-114">Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="cec5e-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
    
### <a name="to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="cec5e-115">Para criar uma regra de fluxo de emails que define o SCL de uma mensagem</span><span class="sxs-lookup"><span data-stu-id="cec5e-115">To create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="cec5e-116">No centro de administração do Exchange (Eat), escolha \> **regras**de **fluxo de emails** .</span><span class="sxs-lookup"><span data-stu-id="cec5e-116">In the Exchange admin center (EAC), choose **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="cec5e-117">Escolha **novo**![ícone](../media/ITPro-EAC-AddIcon.gif)de adição e, em seguida, selecione **criar uma nova regra**.</span><span class="sxs-lookup"><span data-stu-id="cec5e-117">Choose **New**![Add Icon](../media/ITPro-EAC-AddIcon.gif), and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="cec5e-118">Especifique um nome para a regra.</span><span class="sxs-lookup"><span data-stu-id="cec5e-118">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="cec5e-119">Escolha **mais opções**e, em **aplicar esta regra se**, especifique uma condição que disparará a ação que será definida para esta regra (que é definir o valor de SCL).</span><span class="sxs-lookup"><span data-stu-id="cec5e-119">Choose **More options**, and then under **Apply this rule if**, specify a condition that will trigger the action you'll be setting for this rule (which is to set the SCL value).</span></span>
    
    <span data-ttu-id="cec5e-120">Por exemplo, você pode definir que **o remetente** \> **é interno/externo**e, em seguida, na caixa de diálogo **selecionar local do remetente** , selecione **dentro da organização**e escolha **OK**.</span><span class="sxs-lookup"><span data-stu-id="cec5e-120">For example, you can set **The sender** \> **is internal/external**, and then in the **select sender location** dialog box, select **Inside the organization**, and choose **ok**.</span></span><br/>
    <span data-ttu-id="cec5e-121">![Selecione o local do remetente](../media/EOP-ETR-SetSCL-1.jpg)</span><span class="sxs-lookup"><span data-stu-id="cec5e-121">![Select sender location](../media/EOP-ETR-SetSCL-1.jpg)</span></span>
  
5. <span data-ttu-id="cec5e-122">Em **Execute a ação a seguir**, selecione **Modificar as propriedades da mensagem** \> **definir o SCL (nível de confiança de spam)**.</span><span class="sxs-lookup"><span data-stu-id="cec5e-122">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
  
6. <span data-ttu-id="cec5e-123">Na caixa de diálogo **especificar SCL** , selecione um dos seguintes valores e escolha **OK**:</span><span class="sxs-lookup"><span data-stu-id="cec5e-123">In the **specify SCL** dialog box, select one of the following values, and choose **ok**:</span></span>
    
  - <span data-ttu-id="cec5e-124">**Ignorar filtragem de spam** : define o SCL como-1, o que significa que a filtragem de conteúdo não será executada.</span><span class="sxs-lookup"><span data-stu-id="cec5e-124">**Bypass spam filtering** - This sets the SCL to -1, which means that content filtering won't be performed.</span></span> 
    
  - <span data-ttu-id="cec5e-125">**0-4** -quando você definir o SCL como um desses valores, a mensagem será passada para o filtro de conteúdo para processamento adicional.</span><span class="sxs-lookup"><span data-stu-id="cec5e-125">**0-4** - When you set the SCL to one of these values, the message will be passed along to the content filter for additional processing.</span></span> 
    
  - <span data-ttu-id="cec5e-126">**5, 6** -quando você definir o SCL como um desses valores, a ação especificada para **spam** nas políticas de filtro de conteúdo aplicáveis será aplicada.</span><span class="sxs-lookup"><span data-stu-id="cec5e-126">**5, 6** - When you set the SCL to one of these values, the action specified for **Spam** in the applicable content filter policies will be applied.</span></span> <span data-ttu-id="cec5e-127">Por padrão, a ação é enviar a mensagem para a pasta lixo eletrônico do destinatário.</span><span class="sxs-lookup"><span data-stu-id="cec5e-127">By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
  - <span data-ttu-id="cec5e-128">**7-9** -quando você definir o SCL como um desses valores, a ação especificada para **spam de alta confiança** nas políticas de filtro de conteúdo aplicáveis será aplicada.</span><span class="sxs-lookup"><span data-stu-id="cec5e-128">**7-9** - When you set the SCL to one of these values, the action specified for **High confidence spam** in the applicable content filter policies will be applied.</span></span> <span data-ttu-id="cec5e-129">Por padrão, a ação é enviar a mensagem para a pasta lixo eletrônico do destinatário.</span><span class="sxs-lookup"><span data-stu-id="cec5e-129">By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
    <span data-ttu-id="cec5e-130">Para obter mais informações sobre como configurar suas políticas de filtro de conteúdo, consulte [Configure Your spam filter Policies](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="cec5e-130">For more information about configuring your content filter policies, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="cec5e-131">Para saber mais sobre os valores de SCL do serviço, veja [Níveis de confiança de spam](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="cec5e-131">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
7. <span data-ttu-id="cec5e-132">Especifique propriedades adicionais para a regra e escolha **salvar**.</span><span class="sxs-lookup"><span data-stu-id="cec5e-132">Specify additional properties for the rule, and choose **save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="cec5e-133">Para obter mais informações sobre as propriedades adicionais que você pode selecionar ou especificar para esta regra, consulte [usar o Eat para criar regras de fluxo de email](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="cec5e-133">For more information about the additional properties you can select or specify for this rule, see [Use the EAC to create mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules).</span></span> 
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="cec5e-134">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="cec5e-134">How do you know this worked?</span></span>

<span data-ttu-id="cec5e-135">Para verificar se esse procedimento está funcionando corretamente, envie uma mensagem de email para alguém dentro da sua organização e verifique se a ação executada na mensagem é conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="cec5e-135">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="cec5e-136">Por exemplo, se você **definir o nível de confiança de spam (SCL)** para **ignorar a filtragem de spam**, a mensagem deverá ser enviada para a caixa de entrada do destinatário especificado.</span><span class="sxs-lookup"><span data-stu-id="cec5e-136">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="cec5e-137">No entanto, se você **definir o nível de confiança de spam (SCL)** como **9**e a ação de **spam de alta confiança** para suas políticas de filtro de conteúdo aplicáveis for mover a mensagem para a pasta lixo eletrônico, a mensagem deverá ser enviada para a pasta de lixo eletrônico do destinatário especificado.</span><span class="sxs-lookup"><span data-stu-id="cec5e-137">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable content filter policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span> 
  

