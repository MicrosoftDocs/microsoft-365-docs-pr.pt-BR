---
title: Garantir que o spam seja direcionado para a pasta Lixo Eletrônico de cada usuário
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/16/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a rotear spam para pastas de lixo eletrônico do usuário no Exchange Online Protection.
ms.openlocfilehash: 6d1fd625669e8b638a408b2db1993f45fa653ffb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599358"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="8e49d-103">Garantir que o spam seja direcionado para a pasta Lixo Eletrônico de cada usuário</span><span class="sxs-lookup"><span data-stu-id="8e49d-103">Ensure that spam is routed to each user's Junk Email folder</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e49d-104">Este tópico aplica-se apenas aos clientes do proteção do Exchange Online (EOP) que hospedam caixas de correio no local em uma implantação híbrida.</span><span class="sxs-lookup"><span data-stu-id="8e49d-104">This topic only applies to Exchange Online Protection (EOP) customers who host mailboxes on-premises in a hybrid deployment.</span></span> <span data-ttu-id="8e49d-105">Os clientes do Exchange Online cujas caixas de correio são totalmente hospedadas no Office 365 não precisam executar esses comandos.</span><span class="sxs-lookup"><span data-stu-id="8e49d-105">Exchange Online customers whose mailboxes are fully-hosted in Office 365 do not need to run these commands.</span></span>

<span data-ttu-id="8e49d-106">A ação antispam padrão para clientes do EOP é mover as mensagens de spam para a pasta Lixo Eletrônico dos destinatários.</span><span class="sxs-lookup"><span data-stu-id="8e49d-106">The default anti-spam action for EOP customers is to move spam messages to the recipients' Junk Email folder.</span></span> <span data-ttu-id="8e49d-107">Para que essa ação funcione com caixas de correio locais, você deve configurar as regras de fluxo de mensagens do Exchange (também conhecidas como regras de transporte) em seus servidores de borda ou Hub no local para detectar cabeçalhos de spam adicionados pelo EOP.</span><span class="sxs-lookup"><span data-stu-id="8e49d-107">In order for this action to work with on-premises mailboxes, you must configure Exchange mail flow rules (also known as transport rules) on your on-premises Edge or Hub servers to detect spam headers added by EOP.</span></span> <span data-ttu-id="8e49d-108">Essas regras de fluxo de emails definem o nível de confiança de spam (SCL) usado pela propriedade SclJunkThreshold do cmdlet Set-OrganizationConfig para mover o spam para a pasta lixo eletrônico de cada caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="8e49d-108">These mail flow rules set the spam confidence level (SCL) used by the SclJunkThreshold property of the Set-OrganizationConfig cmdlet to move spam into the Junk Email folder of each mailbox.</span></span>

### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a><span data-ttu-id="8e49d-109">Para adicionar regras de fluxo de email para garantir que o spam seja movido para a pasta lixo eletrônico usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e49d-109">To add mail flow rules to ensure spam is moved to the Junk Email folder by using Windows PowerShell</span></span>

1. <span data-ttu-id="8e49d-110">Acesse o Shell de Gerenciamento do Exchange para seu servidor do Exchange local.</span><span class="sxs-lookup"><span data-stu-id="8e49d-110">Access the Exchange Management Shell for your on-premises Exchange server.</span></span> <span data-ttu-id="8e49d-111">Para saber como abrir o Shell de Gerenciamento do Exchange em sua organização Exchange local, confira **Open the Shell**.</span><span class="sxs-lookup"><span data-stu-id="8e49d-111">To learn how to open the Exchange Management Shell in your on-premises Exchange organization, see **Open the Shell**.</span></span>

2. <span data-ttu-id="8e49d-112">Execute o seguinte comando para encaminhar mensagens de spam filtradas por conteúdo para a pasta Lixo Eletrônico:</span><span class="sxs-lookup"><span data-stu-id="8e49d-112">Run the following command to route content-filtered spam messages to the Junk Email folder:</span></span>

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
   ```

   <span data-ttu-id="8e49d-113">Em que _NameForRule_ é o nome da nova regra, por exemplo, JunkContentFilteredMail.</span><span class="sxs-lookup"><span data-stu-id="8e49d-113">Where _NameForRule_ is the name for the new rule, for example, JunkContentFilteredMail.</span></span>

3. <span data-ttu-id="8e49d-114">Execute o seguinte comando para encaminhar mensagens marcadas como spam, antes da aplicação do filtro de conteúdo, para a pasta Lixo Eletrônico:</span><span class="sxs-lookup"><span data-stu-id="8e49d-114">Run the following command to route messages marked as spam prior to reaching the content filter to the Junk Email folder:</span></span>

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
   ```

   <span data-ttu-id="8e49d-115">Em que _NameForRule_ é o nome da nova regra, por exemplo, JunkMailBeforeReachingContentFilter.</span><span class="sxs-lookup"><span data-stu-id="8e49d-115">Where _NameForRule_ is the name for the new rule, for example, JunkMailBeforeReachingContentFilter.</span></span>

4. <span data-ttu-id="8e49d-116">Execute o seguinte comando para garantir que as mensagens de remetentes em uma lista de bloqueios na política de filtro de spam, como a lista de **bloqueios de remetente** , sejam encaminhadas para a pasta lixo eletrônico:</span><span class="sxs-lookup"><span data-stu-id="8e49d-116">Run the following command to ensure that messages from senders in a block list in the spam filter policy, such as the **Sender block** list, are routed to the Junk Email folder:</span></span>

   ```Powershell
   New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
   ```

   <span data-ttu-id="8e49d-117">Em que _NameForRule_ é o nome da nova regra, por exemplo, JunkMailInSenderBlockList.</span><span class="sxs-lookup"><span data-stu-id="8e49d-117">Where _NameForRule_ is the name for the new rule, for example, JunkMailInSenderBlockList.</span></span>

<span data-ttu-id="8e49d-118">Se você não quiser usar a ação **mover mensagem para a pasta lixo eletrônico** , você pode escolher outra ação em suas políticas de filtro de conteúdo no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="8e49d-118">If you do not want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="8e49d-119">Para obter mais informações, consulte [Configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8e49d-119">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="8e49d-120">Para obter mais informações sobre esses campos no cabeçalho da mensagem, consulte [anti-spam Message Headers](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="8e49d-120">For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

> [!TIP]
> <span data-ttu-id="8e49d-121">Se você não quiser usar a ação **mover mensagem para a pasta lixo eletrônico** , você pode escolher outra ação em suas políticas de filtro de conteúdo no centro de administração do Exchange.</span><span class="sxs-lookup"><span data-stu-id="8e49d-121">If you don't want to use the **Move message to Junk Email folder** action, you can choose another action in your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="8e49d-122">Para obter mais informações, consulte [Configurar suas políticas de filtro de spam](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8e49d-122">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="8e49d-123">Para obter mais informações sobre esses campos no cabeçalho da mensagem, consulte [anti-spam Message Headers](anti-spam-message-headers.md).</span><span class="sxs-lookup"><span data-stu-id="8e49d-123">For more information about these fields in the message header, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8e49d-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="8e49d-124">See also</span></span>

[<span data-ttu-id="8e49d-125">New-TransportRule</span><span class="sxs-lookup"><span data-stu-id="8e49d-125">New-TransportRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule)
