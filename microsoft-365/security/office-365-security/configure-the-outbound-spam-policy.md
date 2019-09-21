---
title: Configurar a política de spam de saída
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/10/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: A filtragem de spam de saída está sempre habilitada se você utilizar o serviço de envio de email de saída, protegendo assim as organizações que utilizam o serviço e seus destinatários desejados.
ms.openlocfilehash: 9c8c2f7e9ff0be02f11fa66409690cbb854d8c56
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072842"
---
# <a name="configure-the-outbound-spam-policy"></a><span data-ttu-id="1c572-103">Configurar a política de spam de saída</span><span class="sxs-lookup"><span data-stu-id="1c572-103">Configure the outbound spam policy</span></span>

<span data-ttu-id="1c572-p101">A filtragem de spam de saída está sempre habilitada se você utilizar o serviço de envio de email de saída, protegendo assim as organizações que utilizam o serviço e seus destinatários desejados. Semelhante a filtragem de entrada, a filtragem de spam de saída é composta de filtragem de conexão e de conteúdo, porém, as configurações do filtro de saída não são configuráveis. Se uma mensagem de saída é considerada spam, ela é roteada através do pool de entrega de risco mais alto, que reduz a probabilidade do pool de IP de saída normal estar sendo adicionado a uma lista de bloqueio. Se um cliente continua a enviar spam de saída através do serviço, será impedido de enviar mensagens. Embora a filtragem de spam de saída não possa ser desabilitada nem modificada, você pode configurar várias configurações de spam de saída para toda a empresa por meio da política padrão de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="1c572-p101">Outbound spam filtering is always enabled if you use the service for sending outbound email, thereby protecting organizations using the service and their intended recipients. Similar to inbound filtering, outbound spam filtering is comprised of connection filtering and content filtering, however the outbound filter settings are not configurable. If an outbound message is determined to be spam, it is routed through the higher risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list. If a customer continues to send outbound spam through the service, they will be blocked from sending messages. Although outbound spam filtering cannot be disabled or changed, you can configure several company-wide outbound spam settings via the default outbound spam policy.</span></span> 
  
<span data-ttu-id="1c572-109">O vídeo a seguir mostra como configurar a política de spam de saída:</span><span class="sxs-lookup"><span data-stu-id="1c572-109">The following video shows how to configure the outbound spam policy:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1f20d655-0d3d-4141-9cae-e57f5a6cffe8?autoplay=false]
  
> [!NOTE]
> <span data-ttu-id="1c572-110">Para obter os melhores resultados de filtragem, o conteúdo do vídeo acima deve ser usado com uma configuração adequada e familiaridade com os [controles de spam de saída no Office 365](https://docs.microsoft.com/office365/securitycompliance/outbound-spam-controls).</span><span class="sxs-lookup"><span data-stu-id="1c572-110">For the best filtering results, the content in the video above should used with a proper setup, and familiarity with [Outbound spam controls in Office 365](https://docs.microsoft.com/office365/securitycompliance/outbound-spam-controls).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1c572-111">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="1c572-111">What do you need to know before you begin?</span></span>
<span data-ttu-id="1c572-112"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="1c572-112"></span></span>

<span data-ttu-id="1c572-113">Tempo estimado para conclusão: 5 minutos</span><span class="sxs-lookup"><span data-stu-id="1c572-113">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="1c572-114">Para executar este procedimento ou estes procedimentos, você precisa receber permissões.</span><span class="sxs-lookup"><span data-stu-id="1c572-114">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="1c572-115">Para ver de que permissões você precisa, consulte o tópico "entrada antispam no tópico [permissões de recurso no Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) .</span><span class="sxs-lookup"><span data-stu-id="1c572-115">To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="1c572-116">Para obter informações sobre os atalhos de teclado que podem se aplicar aos procedimentos deste tópico, consulte [atalhos de teclado para o centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="1c572-116">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
<span data-ttu-id="1c572-117">O procedimento a seguir também pode ser realizado pelo PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="1c572-117">The following procedure can also be performed via remote PowerShell.</span></span> <span data-ttu-id="1c572-118">Use o cmdlet [Get-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) para analisar suas configurações e o cmdlet [Set-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx) para editar as configurações de política de spam de saída.</span><span class="sxs-lookup"><span data-stu-id="1c572-118">Use the [Get-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) cmdlet to review your settings, and the [Set-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx) to edit your outbound spam policy settings.</span></span> <span data-ttu-id="1c572-119">Para saber como usar o Windows PowerShell para se conectar à proteção do Exchange Online, confira [conectar-se ao PowerShell do Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=627290).</span><span class="sxs-lookup"><span data-stu-id="1c572-119">To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span> <span data-ttu-id="1c572-120">Para saber como usar o Windows PowerShell para se conectar ao Exchange Online, confira [Connect to Exchange Online Using Remote PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="1c572-120">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
  
## <a name="use-the-eac-to-edit-the-default-outbound-spam-policy"></a><span data-ttu-id="1c572-121">Utilize o EAC para editar a política de spam de saída padrão</span><span class="sxs-lookup"><span data-stu-id="1c572-121">Use the EAC to edit the default outbound spam policy</span></span>
<span data-ttu-id="1c572-122"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="1c572-122"></span></span>

<span data-ttu-id="1c572-123">Utilize o procedimento a seguir para editar a política de spam de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="1c572-123">Use the following procedure to edit the default outbound spam policy:</span></span>
  
### <a name="to-configure-the-default-outbound-spam-policy"></a><span data-ttu-id="1c572-124">Para configurar a política de spam de saída padrão.</span><span class="sxs-lookup"><span data-stu-id="1c572-124">To configure the default outbound spam policy</span></span>

1. <span data-ttu-id="1c572-125">No centro de administração do Exchange (Eat), navegue até **proteger** \> **spam de saída**e, em seguida, clique duas vezes na política padrão.</span><span class="sxs-lookup"><span data-stu-id="1c572-125">In the Exchange admin center (EAC), navigate to **Protection** \> **Outbound spam**, and then double-click the default policy.</span></span>
    
2. <span data-ttu-id="1c572-126">Selecione a opção de menu **Preferências de saída de spam** .</span><span class="sxs-lookup"><span data-stu-id="1c572-126">Select the **Outbound spam preferences** menu option.</span></span> 
    
3. <span data-ttu-id="1c572-127">Marque as seguintes caixas de seleção referentes às mensagens de saída e, em seguida, especifique um endereço de email associado ou endereços na caixa de entrada associada (elas podem ser listas de distribuição se forem resolvidas como destinos SMTP válidos):</span><span class="sxs-lookup"><span data-stu-id="1c572-127">Select the following check boxes pertaining to outbound messages, and then specify an associated email address or addresses in the accompanying input box (these can be distribution lists if they resolve as valid SMTP destinations):</span></span>
    
1. <span data-ttu-id="1c572-p104">Envie uma cópia de todas as mensagens suspeitas de email de saída para **o(s) seguinte(s) endereço(s) de email**. Estas são as mensagens que são marcadas como spam pelo filtro (independentemente da classificação de SCL) Elas não são rejeitadas pelo filtro, mas são roteadas pelo pool de entrega de risco mais alto. Separe com ponto e vírgula os diversos endereços. Observe que os destinatários especificados receberão as mensagens como um endereço com cópia oculta (Bcc) (os campos De e Para são o remetente e o destinatário originais).</span><span class="sxs-lookup"><span data-stu-id="1c572-p104">**Send a copy of all suspicious outbound email messages to the following email address or addresses**. These are messages that are marked as spam by the filter (regardless of the SCL rating). They are not rejected by the filter but are routed through the higher risk delivery pool. Separate multiple addresses with a semicolon. Note that the recipients specified will receive the messages as a Blind carbon copy (Bcc) address (the From and To fields are the original sender and recipient).</span></span>
    
2. <span data-ttu-id="1c572-p105">Envie uma notificação para o seguinte endereço de email quando um remetente for bloqueado por enviar **spam de saída**. Separe com ponto e vírgula os diversos endereços.</span><span class="sxs-lookup"><span data-stu-id="1c572-p105">**Send a notification to the following email address when a sender is blocked sending outbound spam**. Separate multiple addresses with a semicolon.</span></span>
    
    <span data-ttu-id="1c572-135">Quando uma quantidade significativa de spam está sendo originada a partir de um usuário específico, este usuário é desabilitado para envio de mensagens de email.</span><span class="sxs-lookup"><span data-stu-id="1c572-135">When a significant amount of spam is originating from a particular user, the user is disabled from sending email messages.</span></span> <span data-ttu-id="1c572-136">O administrador para o domínio, especificado usando esta configuração, será informado de que as mensagens de saída estão bloqueadas para este usuário.</span><span class="sxs-lookup"><span data-stu-id="1c572-136">The administrator for the domain, who is specified using this setting, will be informed that outbound messages are blocked for this user.</span></span> <span data-ttu-id="1c572-137">Para ver a aparência dessa notificação, confira [exemplo de notificação quando um remetente estiver bloqueado enviando spam de saída](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md).</span><span class="sxs-lookup"><span data-stu-id="1c572-137">To see what this notification looks like, see [Sample notification when a sender is blocked sending outbound spam](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md).</span></span> <span data-ttu-id="1c572-138">Para obter informações sobre como habilitar novamente, consulte [removendo um usuário, domínio ou endereço IP de uma lista de bloqueios após o envio de email de spam](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span><span class="sxs-lookup"><span data-stu-id="1c572-138">For information about getting re-enabled, see [Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span></span>
    
4. <span data-ttu-id="1c572-p107">Clique em **salvar**. Um resumo das suas configurações de política padrão aparece no painel à direita.</span><span class="sxs-lookup"><span data-stu-id="1c572-p107">Click **save**. A summary of your default policy settings appears in the right pane.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="1c572-141">Para obter mais informações</span><span class="sxs-lookup"><span data-stu-id="1c572-141">For more information</span></span>
<span data-ttu-id="1c572-142"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="1c572-142"></span></span>

[<span data-ttu-id="1c572-143">Pool de entrega de alto risco para mensagens de saída</span><span class="sxs-lookup"><span data-stu-id="1c572-143">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)
  
[<span data-ttu-id="1c572-144">Perguntas frequentes sobre proteção antispam</span><span class="sxs-lookup"><span data-stu-id="1c572-144">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  

