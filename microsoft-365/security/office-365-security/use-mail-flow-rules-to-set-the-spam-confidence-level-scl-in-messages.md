---
title: Usar regras de fluxo de emails para o SCL em mensagens
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: Saiba como criar regras de fluxo de emails (regras de transporte) para identificar mensagens e definir o nível de confiança de spam (SCL) de mensagens na Proteção do Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 795347046342ea17870e7758a6327facf51315a4
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203116"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages-in-eop"></a><span data-ttu-id="73c45-103">Usar regras de fluxo de emails para definir o nível de confiança de spam (SCL) em mensagens no EOP</span><span class="sxs-lookup"><span data-stu-id="73c45-103">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="73c45-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="73c45-104">**Applies to**</span></span>
- [<span data-ttu-id="73c45-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="73c45-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="73c45-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="73c45-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="73c45-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="73c45-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="73c45-108">Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, o EOP usa políticas anti-spam (também conhecidas como políticas de filtro de spam ou políticas de filtro de conteúdo) para verificar mensagens de entrada para spam.</span><span class="sxs-lookup"><span data-stu-id="73c45-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP uses anti-spam policies (also known as spam filter policies or content filter policies) to scan inbound messages for spam.</span></span> <span data-ttu-id="73c45-109">Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="73c45-109">For more information, see [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="73c45-110">Se você quiser marcar mensagens específicas como spam antes mesmo de ser verificado pela filtragem de spam ou marcar mensagens para que elas ignorem a filtragem de spam, você pode criar regras de fluxo de emails (também conhecidas como regras de transporte) para identificar as mensagens e definir o nível de confiança de spam (SCL).</span><span class="sxs-lookup"><span data-stu-id="73c45-110">If you want to mark specific messages as spam before they're even scanned by spam filtering, or mark messages so they'll skip spam filtering, you can create mail flow rules (also known as transport rules) to identify the messages and set the spam confidence level (SCL).</span></span> <span data-ttu-id="73c45-111">Para obter mais informações sobre a SCL, consulte Nível de confiança [de spam (SCL) no EOP](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="73c45-111">For more information about the SCL, see [Spam confidence level (SCL) in EOP](spam-confidence-levels.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="73c45-112">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="73c45-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="73c45-113">Você precisa ter permissões atribuídas no Exchange Online ou no Exchange Online Protection antes de poder fazer os procedimentos neste artigo.</span><span class="sxs-lookup"><span data-stu-id="73c45-113">You need to be assigned permissions in Exchange Online or Exchange Online Protection before you can do the procedures in this article.</span></span> <span data-ttu-id="73c45-114">Especificamente, você precisa da função **Regras** de Transporte, que é atribuída aos  grupos de função Gerenciamento da **Organização,** Gerenciamento de **Conformidade** (administradores globais) e Gerenciamento de Registros por padrão.</span><span class="sxs-lookup"><span data-stu-id="73c45-114">Specifically, you need the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management** (global admins), and **Records Management** role groups by default.</span></span>

  <span data-ttu-id="73c45-115">Para mais informações, confira os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="73c45-115">For more information, see the following topics:</span></span>

  - [<span data-ttu-id="73c45-116">Permissões no Exchange Online</span><span class="sxs-lookup"><span data-stu-id="73c45-116">Permissions in Exchange Online</span></span>](/exchange/permissions-exo/permissions-exo)
  - [<span data-ttu-id="73c45-117">Permissões no EOP autônomo</span><span class="sxs-lookup"><span data-stu-id="73c45-117">Permissions in standalone EOP</span></span>](feature-permissions-in-eop.md)
  - [<span data-ttu-id="73c45-118">Usar o EAC modificar a lista de membros em grupos de função</span><span class="sxs-lookup"><span data-stu-id="73c45-118">Use the EAC modify the list of members in role groups</span></span>](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)

- <span data-ttu-id="73c45-119">Para abrir o EAC no Exchange Online, consulte [Centro de administração do Exchange no Exchange Online](/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="73c45-119">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](/Exchange/exchange-admin-center).</span></span> <span data-ttu-id="73c45-120">Para abrir o EAC no EOP autônomo, consulte Centro de administração [do Exchange no EOP](exchange-admin-center-in-exchange-online-protection-eop.md)autônomo .</span><span class="sxs-lookup"><span data-stu-id="73c45-120">To open the EAC in standalone EOP, see [Exchange admin center in standalone EOP](exchange-admin-center-in-exchange-online-protection-eop.md).</span></span>

- <span data-ttu-id="73c45-121">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="73c45-121">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="73c45-122">Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="73c45-122">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="73c45-123">Para obter mais informações sobre regras de fluxo de emails no Exchange Online e na Proteção do Exchange Online, consulte Regras de fluxo de emails [(regras de transporte) no Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span><span class="sxs-lookup"><span data-stu-id="73c45-123">For more information about mail flow rules in Exchange Online and Exchange Online Protection, see [Mail flow rules (transport rules) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="73c45-124">Use o EAC para criar uma regra de fluxo de emails que define a SCL de uma mensagem</span><span class="sxs-lookup"><span data-stu-id="73c45-124">Use the EAC to create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="73c45-125">No EAC, vá para **Fluxo de emails** \> **Regras**.</span><span class="sxs-lookup"><span data-stu-id="73c45-125">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="73c45-126">Clique **em Adicionar** ícone e selecione Criar uma nova ![ ](../../media/ITPro-EAC-AddIcon.png) **regra.**</span><span class="sxs-lookup"><span data-stu-id="73c45-126">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="73c45-127">Na página **Nova regra** que é aberta, configure as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="73c45-127">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="73c45-128">**Nome**: Insira um nome exclusivo e descritivo para a regra.</span><span class="sxs-lookup"><span data-stu-id="73c45-128">**Name**: Enter a unique, descriptive name for the rule.</span></span>

   - <span data-ttu-id="73c45-129">Clique **em Mais Opções**.</span><span class="sxs-lookup"><span data-stu-id="73c45-129">Click **More Options**.</span></span>

   - <span data-ttu-id="73c45-130">**Aplique essa regra se**: Selecione uma ou mais condições para identificar mensagens.</span><span class="sxs-lookup"><span data-stu-id="73c45-130">**Apply this rule if**: Select one or more conditions to identify messages.</span></span> <span data-ttu-id="73c45-131">Para obter mais informações, consulte Condições de regra de fluxo de email e exceções [(predicados) no Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="73c45-131">For more information, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

   - <span data-ttu-id="73c45-132">**Faça o seguinte:** Selecione **Modificar as propriedades da mensagem** definir o nível de confiança de spam \> **(SCL)**.</span><span class="sxs-lookup"><span data-stu-id="73c45-132">**Do the following**: Select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span> <span data-ttu-id="73c45-133">Na caixa **de diálogo Especificar SCL** exibida, configure um dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="73c45-133">In the **Specify SCL** dialog that appears, configure one of the following values:</span></span>

   - <span data-ttu-id="73c45-134">**Ignorar a filtragem de** spam: as mensagens ignorarão a filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="73c45-134">**Bypass spam filtering**: The messages will skip spam filtering.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="73c45-135">Tenha muito cuidado ao permitir que as mensagens ignorem a filtragem de spam.</span><span class="sxs-lookup"><span data-stu-id="73c45-135">Be very careful about allowing messages to skip spam filtering.</span></span> <span data-ttu-id="73c45-136">Os invasores podem usar essa vulnerabilidade para enviar phishing e outras mensagens mal-intencionadas para sua organização.</span><span class="sxs-lookup"><span data-stu-id="73c45-136">Attackers can use this vulnerability to send phishing and other malicious messages into your organization.</span></span> <span data-ttu-id="73c45-137">As regras de fluxo de emails exigem mais do que apenas o endereço de email ou domínio do remetente.</span><span class="sxs-lookup"><span data-stu-id="73c45-137">The mail flow rules requires more than just the sender's email address or domain.</span></span> <span data-ttu-id="73c45-138">Para obter mais informações, consulte [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="73c45-138">For more information, see [Create safe sender lists in EOP](create-safe-sender-lists-in-office-365.md).</span></span>

   - <span data-ttu-id="73c45-139">**0 a 4**: A mensagem é enviada por meio de filtragem de spam para processamento adicional.</span><span class="sxs-lookup"><span data-stu-id="73c45-139">**0 to 4**: The message is sent through spam filtering for additional processing.</span></span>

   - <span data-ttu-id="73c45-140">**5 ou 6**: A mensagem é marcada como **Spam**.</span><span class="sxs-lookup"><span data-stu-id="73c45-140">**5 or 6**: The message is marked as **Spam**.</span></span> <span data-ttu-id="73c45-141">A ação que você configurou para vereditos de filtragem de **spam** em suas políticas anti-spam é aplicada à mensagem (o valor padrão é Mover mensagem para a pasta **Lixo Eletrônico**).</span><span class="sxs-lookup"><span data-stu-id="73c45-141">The action that you've configured for **Spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

   - <span data-ttu-id="73c45-142">**7 a 9**: A mensagem é marcada como **spam de alta confiança.**</span><span class="sxs-lookup"><span data-stu-id="73c45-142">**7 to 9**: The message is marked as **High confidence spam**.</span></span> <span data-ttu-id="73c45-143">A ação que você configurou para vereditos de filtragem de **spam** de alta confiança em suas políticas anti-spam é aplicada à mensagem (o valor padrão é Mover mensagem para a pasta Lixo **Eletrônico**).</span><span class="sxs-lookup"><span data-stu-id="73c45-143">The action that you've configured for **High confidence spam** filtering verdicts in your anti-spam policies is applied to the message (the default value is **Move message to Junk Email folder**).</span></span>

4. <span data-ttu-id="73c45-144">Especifique as propriedades adicionais que você deseja para a regra.</span><span class="sxs-lookup"><span data-stu-id="73c45-144">Specify any additional properties that you want for the rule.</span></span> <span data-ttu-id="73c45-145">Quando concluir, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="73c45-145">When you're finished, click **Save**.</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="73c45-146">Como saber se funcionou?</span><span class="sxs-lookup"><span data-stu-id="73c45-146">How do you know this worked?</span></span>

<span data-ttu-id="73c45-147">Para verificar se esse procedimento está funcionando corretamente, envie uma mensagem de email para alguém dentro da sua organização e verifique se a ação executada na mensagem é conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="73c45-147">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected.</span></span> <span data-ttu-id="73c45-148">Por exemplo, se você definir o nível de confiança de **spam (SCL)** como Ignorar a filtragem de **spam,** a mensagem deverá ser enviada para a caixa de entrada do destinatário especificado.</span><span class="sxs-lookup"><span data-stu-id="73c45-148">For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox.</span></span> <span data-ttu-id="73c45-149">No entanto, se você definir o nível de confiança de **spam** **(SCL)** como **9**, e a ação spam de alta confiança para suas políticas anti-spam aplicáveis for mover a mensagem para a pasta Lixo Eletrônico, a mensagem deverá ser enviada para a pasta Lixo Eletrônico do destinatário especificado.</span><span class="sxs-lookup"><span data-stu-id="73c45-149">However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable anti-spam policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span>