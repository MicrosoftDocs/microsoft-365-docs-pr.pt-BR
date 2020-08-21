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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: O administrador pode aprender sobre as opções de configuração de fluxo de email e roteamento na proteção do Exchange Online (EOP).
ms.openlocfilehash: c58981afaadf2c4083b6a6db99c74cf9544715c3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827720"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="7ed78-103">Fluxo de e-mails no EOP</span><span class="sxs-lookup"><span data-stu-id="7ed78-103">Mail flow in EOP</span></span>

<span data-ttu-id="7ed78-104">Nas organizações do Microsoft 365 com caixas de correio do Exchange Online, ou organizações autônomas do Exchange Online Protection (EOP), sem caixas de correio do Exchange Online, todas as mensagens enviadas para sua organização passam pelo EOP antes que seus funcionários os vejam.</span><span class="sxs-lookup"><span data-stu-id="7ed78-104">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="7ed78-105">Você tem opções sobre como rotear mensagens que passam pelo EOP para processamento antes de serem encaminhadas para suas caixas de entrada de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7ed78-105">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="7ed78-106">Trabalhando com mensagens e opções de acesso a mensagens</span><span class="sxs-lookup"><span data-stu-id="7ed78-106">Working with messages and message access options</span></span>

<span data-ttu-id="7ed78-107">O EOP oferece flexibilidade no modo como as mensagens são encaminhadas.</span><span class="sxs-lookup"><span data-stu-id="7ed78-107">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="7ed78-108">Os tópicos a seguir explicam as etapas no processo de fluxo de email.</span><span class="sxs-lookup"><span data-stu-id="7ed78-108">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="7ed78-109">[Usar o bloqueio de borda baseado em diretório para rejeitar mensagens enviadas a destinatários inválidos](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Descreve o recurso de bloqueio de borda baseado em diretório, que permite rejeitar mensagens para destinatários inválidos no perímetro da rede de serviço.</span><span class="sxs-lookup"><span data-stu-id="7ed78-109">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="7ed78-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) descreve como gerenciar domínios que são associados ao seu serviço EOP.</span><span class="sxs-lookup"><span data-stu-id="7ed78-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="7ed78-111">Se você adicionar subdomínios à sua organização, o serviço do EOP poderá ajudá-lo a gerenciá-los também.</span><span class="sxs-lookup"><span data-stu-id="7ed78-111">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="7ed78-112">Saiba mais sobre subdomínios em [habilitar o fluxo de emails para subdomínios no Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span><span class="sxs-lookup"><span data-stu-id="7ed78-112">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="7ed78-113">[Configurar o fluxo de email usando conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduz conectores e mostra como você pode usá-los para personalizar o roteamento de emails.</span><span class="sxs-lookup"><span data-stu-id="7ed78-113">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="7ed78-114">Os cenários incluem garantir uma comunicação segura com uma organização parceira e configurar um host inteligente.</span><span class="sxs-lookup"><span data-stu-id="7ed78-114">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="7ed78-115">[Filtragem avançada para conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) descreve como configurar conectores se o email for roteado para um serviço ou dispositivo antes de EOP.</span><span class="sxs-lookup"><span data-stu-id="7ed78-115">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="7ed78-116">Em organizações EOP autônomas, você precisa executar algumas etapas de configuração para garantir que o lixo eletrônico seja roteado corretamente para a pasta lixo eletrônico de cada usuário.</span><span class="sxs-lookup"><span data-stu-id="7ed78-116">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="7ed78-117">Eles são detalhados em [Configurar o EOP autônomo para entregar o spam à pasta lixo eletrônico em ambientes híbridos](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span><span class="sxs-lookup"><span data-stu-id="7ed78-117">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="7ed78-118">Se não quiser mover mensagens para a pasta de lixo eletrônico de cada usuário, você pode escolher outra ação editando suas políticas antispam (também conhecidas como políticas de filtro de conteúdo).</span><span class="sxs-lookup"><span data-stu-id="7ed78-118">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="7ed78-119">Para saber mais, confira [Configurar políticas anti-spam](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7ed78-119">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="7ed78-120">Verificar fluxo de mensagens</span><span class="sxs-lookup"><span data-stu-id="7ed78-120">Verify mail flow</span></span>

<span data-ttu-id="7ed78-p106">Para verificar se a sua instalação do EOP, incluindo a configuração de conectores, está funcionando corretamente, consulte a seção "Como saber se esta tarefa funcionou?" em [Configurar seu serviço EOP](set-up-your-eop-service.md).</span><span class="sxs-lookup"><span data-stu-id="7ed78-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="7ed78-123">[Testar o fluxo de emails Validando seus conectores do Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) fornece instruções para testar se seu fluxo de email está configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="7ed78-123">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
