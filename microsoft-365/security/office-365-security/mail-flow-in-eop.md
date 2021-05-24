---
title: Fluxo de emails no EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: O administrador pode aprender sobre as opções para configurar o fluxo de email e o roteamento no Proteção do Exchange Online (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ad80c4176c1b8b1c47b6b9ecafd34b4ca301f3f
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623412"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="e48d2-103">Fluxo de emails no EOP</span><span class="sxs-lookup"><span data-stu-id="e48d2-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e48d2-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="e48d2-104">**Applies to**</span></span>
- [<span data-ttu-id="e48d2-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e48d2-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e48d2-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e48d2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e48d2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e48d2-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e48d2-108">Em organizações Microsoft 365 com caixas de correio Exchange Online ou organizações autônomas Proteção do Exchange Online (EOP) sem Exchange Online caixas de correio, todas as mensagens enviadas para sua organização passam pelo EOP antes que seus funcionários as vejam.</span><span class="sxs-lookup"><span data-stu-id="e48d2-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="e48d2-109">Você tem opções sobre como rotear mensagens que passam pelo EOP para processamento antes que elas sejam roteadas para suas caixas de entrada de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e48d2-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="e48d2-110">Trabalhando com mensagens e opções de acesso a mensagens</span><span class="sxs-lookup"><span data-stu-id="e48d2-110">Working with messages and message access options</span></span>

<span data-ttu-id="e48d2-111">O EOP oferece flexibilidade na forma como suas mensagens são roteadas.</span><span class="sxs-lookup"><span data-stu-id="e48d2-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="e48d2-112">Os tópicos a seguir explicam as etapas no processo de fluxo de email.</span><span class="sxs-lookup"><span data-stu-id="e48d2-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="e48d2-113">[Usar o Bloqueio de Borda Com Base em Diretório para rejeitar mensagens enviadas a destinatários inválidos](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Descreve o recurso Bloqueio de Borda Baseado em Diretório que permite rejeitar mensagens para destinatários inválidos no perímetro da rede de serviço.</span><span class="sxs-lookup"><span data-stu-id="e48d2-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="e48d2-114">[View or Edit Managed Domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) descreve como gerenciar domínios que são associados ao seu serviço EOP.</span><span class="sxs-lookup"><span data-stu-id="e48d2-114">[View or Edit Managed Domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="e48d2-115">Se você adicionar subdomínios à sua organização, o serviço do EOP poderá ajudá-lo a gerenciá-los também.</span><span class="sxs-lookup"><span data-stu-id="e48d2-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="e48d2-116">Saiba mais sobre subdomas em [Habilitar fluxo de emails para subdomas em Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span><span class="sxs-lookup"><span data-stu-id="e48d2-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="e48d2-117">[Configurar o fluxo de emails usando conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduz conectores e mostra como você pode usá-los para personalizar o roteamento de email.</span><span class="sxs-lookup"><span data-stu-id="e48d2-117">[Configure mail flow using connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="e48d2-118">Os cenários incluem garantir uma comunicação segura com uma organização parceira e configurar um host inteligente.</span><span class="sxs-lookup"><span data-stu-id="e48d2-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="e48d2-119">[A filtragem aprimorada](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) para conectores descreve como configurar conectores se seu email for roteado para um serviço ou dispositivo antes do EOP.</span><span class="sxs-lookup"><span data-stu-id="e48d2-119">[Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="e48d2-120">Em ambientes híbridos em que o EOP protege caixas de correio locais Exchange, você precisa configurar regras de fluxo de emails (também conhecidas como regras de transporte) no Exchange local para traduzir o veredito de filtragem de spam do EOP para que a regra de lixo eletrônico possa mover a mensagem para a pasta Lixo Eletrônico.</span><span class="sxs-lookup"><span data-stu-id="e48d2-120">In hybrid environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="e48d2-121">Para obter detalhes, [consulte Configure EOP to deliver spam to the Junk Email folder in hybrid environments](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span><span class="sxs-lookup"><span data-stu-id="e48d2-121">For details, see [Configure EOP to deliver spam to the Junk Email folder in hybrid environments](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span></span> <span data-ttu-id="e48d2-122">Se você não quiser mover mensagens para a pasta Lixo Eletrônico de cada usuário, poderá escolher outra ação editando suas políticas anti-spam (também conhecidas como políticas de filtro de conteúdo).</span><span class="sxs-lookup"><span data-stu-id="e48d2-122">If you don't  want to move messages to each user's Junk Email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="e48d2-123">Para saber mais, confira [Configurar políticas anti-spam](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e48d2-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="e48d2-124">Verificar fluxo de mensagens</span><span class="sxs-lookup"><span data-stu-id="e48d2-124">Verify mail flow</span></span>

<span data-ttu-id="e48d2-p106">Para verificar se a sua instalação do EOP, incluindo a configuração de conectores, está funcionando corretamente, consulte a seção "Como saber se esta tarefa funcionou?" em [Configurar seu serviço EOP](/exchange/standalone-eop/set-up-your-eop-service).</span><span class="sxs-lookup"><span data-stu-id="e48d2-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](/exchange/standalone-eop/set-up-your-eop-service).</span></span>

<span data-ttu-id="e48d2-127">[Testar o fluxo de emails validando seus conectores Microsoft 365 fornece](/exchange/mail-flow-best-practices/test-mail-flow) instruções para testar se o fluxo de email está definido corretamente.</span><span class="sxs-lookup"><span data-stu-id="e48d2-127">[Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
