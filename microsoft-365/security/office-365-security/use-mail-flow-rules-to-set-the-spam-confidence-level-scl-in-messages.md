---
title: Usar regras de fluxo de email para o SCL nas mensagens
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Saiba como criar regras de fluxo de emails (regras de transporte) para identificar mensagens e definir o nível de confiança de spam (SCL) das mensagens na proteção do Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 791e6747e1ffa92d54e7d4f4a6c257c3aad4c0d9
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195850"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="a6695-103">Usar regras de fluxo de emails para definir o nível de confiança de spam (SCL) em mensagens no EOP</span><span class="sxs-lookup"><span data-stu-id="a6695-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a6695-104">Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP usa políticas antispam (também conhecidas como políticas de filtro de spam ou políticas de filtro de conteúdo) para examinar mensagens de entrada para spam.</span><span class="sxs-lookup"><span data-stu-id="a6695-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="a6695-105">Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a6695-105">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="a6695-106">Se você deseja marcar mensagens específicas como spam antes que elas sejam verificadas por filtragem de spam ou marcar mensagens para que elas ignorem a filtragem de spam, você pode criar regras de fluxo de emails (também conhecidas como regras de transporte) para identificar as mensagens e definir o SCL (nível de confiança de spam).</span><span class="sxs-lookup"><span data-stu-id="a6695-106">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="a6695-107">Para obter mais informações sobre o SCL, consulte [nível de confiança de spam (SCL) no EOP](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="a6695-107">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a6695-108">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="a6695-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a6695-109">Você precisa receber permissões no Exchange Online antes de poder executar estes procedimentos.</span><span class="sxs-lookup"><span data-stu-id="a6695-109">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="a6695-110">Especificamente, você precisa receber a função de **regras de transporte** , que é atribuída às funções de gerenciamento da **organização**, **Gerenciamento de conformidade**e gerenciamento de **registros** por padrão.</span><span class="sxs-lookup"><span data-stu-id="a6695-110">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="a6695-111">Para saber mais, confira [Gerenciar Grupos de Funções do Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="a6695-111">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="a6695-112">Para abrir o Eat no Exchange Online, confira [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="a6695-112">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="a6695-113">Para obter mais informações sobre regras de fluxo de email no Exchange Online, consulte [regras de fluxo de emails (regras de transporte) no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="a6695-113">For more information about mail flow rules in Exchange Online, see [Mail flow rules (transport rules) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="a6695-114">Use o Eat para criar uma regra de fluxo de emails que define o SCL de uma mensagem</span><span class="sxs-lookup"><span data-stu-id="a6695-114">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="a6695-115">No EAC, vá para **Fluxo de emails** \> **Regras**.</span><span class="sxs-lookup"><span data-stu-id="a6695-115">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="a6695-116">Clique em **Adicionar** ![ ícone ](../../media/ITPro-EAC-AddIcon.png) de adição e selecione **criar uma nova regra**.</span><span class="sxs-lookup"><span data-stu-id="a6695-116">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="a6695-117">Na página **nova regra** que é aberta, defina as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="a6695-117">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="a6695-118">**Name**: Insira um nome exclusivo e descritivo para a regra.</span><span class="sxs-lookup"><span data-stu-id="a6695-118">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="a6695-119">Clique em **mais opções**.</span><span class="sxs-lookup"><span data-stu-id="a6695-119">Click **More Options**.</span></span>

   - <span data-ttu-id="a6695-120">**Aplicar esta regra se**: selecione uma ou mais condições para identificar mensagens.</span><span class="sxs-lookup"><span data-stu-id="a6695-120">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="a6695-121">Para obter mais informações, consulte [regras e exceções de regra de fluxo de emails (predicados) no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="a6695-121">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="a6695-122">**Faça o seguinte**: selecione **modificar as propriedades da mensagem** \> **definem o nível de confiança de spam (SCL)**.</span><span class="sxs-lookup"><span data-stu-id="a6695-122">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="a6695-123">Na caixa de diálogo **especificar SCL** exibida, configure um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="a6695-123">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="a6695-124">**Ignorar filtragem de spam**: as mensagens irão ignorar a filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="a6695-124">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="a6695-125">Tenha muito cuidado para permitir que as mensagens ignorem a filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="a6695-125">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="a6695-126">Os invasores podem usar essa vulnerabilidade para enviar phishing e outras mensagens mal-intencionadas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="a6695-126">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="a6695-127">As regras de fluxo de emails exigem mais do que apenas o domínio ou endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="a6695-127">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="a6695-128">Para obter mais informações, consulte [criar listas de remetentes seguros no EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="a6695-128">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="a6695-129">**0 a 4**: a mensagem é enviada por filtragem de spam para processamento adicional.</span><span class="sxs-lookup"><span data-stu-id="a6695-129">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="a6695-130">**5 ou 6**: a mensagem é marcada como **spam**.</span><span class="sxs-lookup"><span data-stu-id="a6695-130">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="a6695-131">A ação que você configurou para filtragem de **spam** verdicts em suas políticas antispam é aplicada à mensagem (o valor padrão é **mover mensagem para a pasta lixo eletrônico**).</span><span class="sxs-lookup"><span data-stu-id="a6695-131">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="a6695-132">**7 a 9**: a mensagem é marcada como **spam de alta confiança**.</span><span class="sxs-lookup"><span data-stu-id="a6695-132">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="a6695-133">A ação que você configurou para a filtragem de **spam de alta confiança** verdicts nas políticas antispam é aplicada à mensagem (o valor padrão é **mover mensagem para a pasta lixo eletrônico**).</span><span class="sxs-lookup"><span data-stu-id="a6695-133">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="a6695-134">Especifique as propriedades adicionais que você deseja para a regra.</span><span class="sxs-lookup"><span data-stu-id="a6695-134">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="a6695-135">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a6695-135">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a6695-136">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="a6695-136">How do you know this worked?</span></span>

<span data-ttu-id="a6695-137">Para verificar se esse procedimento está funcionando corretamente, envie uma mensagem de email para alguém dentro da sua organização e verifique se a ação executada na mensagem é conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="a6695-137">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="a6695-138">Por exemplo, se você **definir o nível de confiança de spam (SCL)** para **ignorar a filtragem de spam**, a mensagem deverá ser enviada para a caixa de entrada do destinatário especificado.</span><span class="sxs-lookup"><span data-stu-id="a6695-138">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="a6695-139">No entanto, se você **definir o nível de confiança de spam (SCL)** como **9**e a ação de **spam de alta confiança** para suas políticas antispam aplicáveis for mover a mensagem para a pasta lixo eletrônico, a mensagem deverá ser enviada para a pasta de lixo eletrônico do destinatário especificado.</span><span class="sxs-lookup"><span data-stu-id="a6695-139">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>
