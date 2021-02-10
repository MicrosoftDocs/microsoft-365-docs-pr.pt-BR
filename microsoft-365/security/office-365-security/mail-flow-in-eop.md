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
description: O administrador pode saber mais sobre as opções para configurar o fluxo de emails e o roteamento no Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cd07c4448d9b30c90c97c7bc89c787b2fdc08cdd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167234"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="35fc3-103">Fluxo de emails no EOP</span><span class="sxs-lookup"><span data-stu-id="35fc3-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="35fc3-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="35fc3-104">**Applies to**</span></span>
- [<span data-ttu-id="35fc3-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="35fc3-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="35fc3-106">Microsoft Defender para Office 365 plano 1 e plano 2</span><span class="sxs-lookup"><span data-stu-id="35fc3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="35fc3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="35fc3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="35fc3-108">Em organizações do Microsoft 365 com caixas de correio do Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, todas as mensagens enviadas para sua organização passam pelo EOP antes que seus funcionários as vejam.</span><span class="sxs-lookup"><span data-stu-id="35fc3-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="35fc3-109">Você tem opções sobre como encaminhar mensagens que passam pelo EOP para processamento antes que elas sejam roteadas para suas caixas de entrada de trabalho.</span><span class="sxs-lookup"><span data-stu-id="35fc3-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="35fc3-110">Trabalhando com mensagens e opções de acesso a mensagens</span><span class="sxs-lookup"><span data-stu-id="35fc3-110">Working with messages and message access options</span></span>

<span data-ttu-id="35fc3-111">O EOP oferece flexibilidade na forma como suas mensagens são roteadas.</span><span class="sxs-lookup"><span data-stu-id="35fc3-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="35fc3-112">Os tópicos a seguir explicam as etapas no processo de fluxo de email.</span><span class="sxs-lookup"><span data-stu-id="35fc3-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="35fc3-113">[Usar Bloqueio de Borda Baseado em Diretório para rejeitar mensagens enviadas a destinatários inválidos](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Descreve o recurso Bloqueio de Borda Baseado em Diretório que permite rejeitar mensagens de destinatários inválidos no perímetro da rede de serviço.</span><span class="sxs-lookup"><span data-stu-id="35fc3-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="35fc3-114">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) descreve como gerenciar domínios que são associados ao seu serviço EOP.</span><span class="sxs-lookup"><span data-stu-id="35fc3-114">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="35fc3-115">Se você adicionar subdomínios à sua organização, o serviço do EOP poderá ajudá-lo a gerenciá-los também.</span><span class="sxs-lookup"><span data-stu-id="35fc3-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="35fc3-116">Saiba mais sobre sub-vírgulas em [Habilitar fluxo de emails para sub-vírgulas no Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)</span><span class="sxs-lookup"><span data-stu-id="35fc3-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="35fc3-117">[Configurar o fluxo de emails usando conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduz conectores e mostra como você pode usá-los para personalizar o roteamento de email.</span><span class="sxs-lookup"><span data-stu-id="35fc3-117">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="35fc3-118">Os cenários incluem garantir uma comunicação segura com uma organização parceira e configurar um host inteligente.</span><span class="sxs-lookup"><span data-stu-id="35fc3-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="35fc3-119">[A Filtragem Aprimorada](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) para Conectores descreve como configurar conectores se seu email for roteado para um serviço ou dispositivo antes do EOP.</span><span class="sxs-lookup"><span data-stu-id="35fc3-119">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="35fc3-120">Em organizações autônomas do EOP, você precisa executar algumas etapas de configuração para garantir que o lixo eletrônico seja roteado corretamente para a pasta de lixo eletrônico de cada usuário.</span><span class="sxs-lookup"><span data-stu-id="35fc3-120">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="35fc3-121">Eles são detalhados em Configurar o EOP autônomo para entregar spam à pasta Lixo Eletrônico [em ambientes híbridos.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)</span><span class="sxs-lookup"><span data-stu-id="35fc3-121">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="35fc3-122">Se você não quiser mover mensagens para a pasta de lixo eletrônico de cada usuário, poderá escolher outra ação editando suas políticas anti-spam (também conhecidas como políticas de filtro de conteúdo).</span><span class="sxs-lookup"><span data-stu-id="35fc3-122">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="35fc3-123">Para saber mais, confira [Configurar políticas anti-spam](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="35fc3-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="35fc3-124">Verificar fluxo de mensagens</span><span class="sxs-lookup"><span data-stu-id="35fc3-124">Verify mail flow</span></span>

<span data-ttu-id="35fc3-p106">Para verificar se a sua instalação do EOP, incluindo a configuração de conectores, está funcionando corretamente, consulte a seção "Como saber se esta tarefa funcionou?" em [Configurar seu serviço EOP](set-up-your-eop-service.md).</span><span class="sxs-lookup"><span data-stu-id="35fc3-p106">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="35fc3-127">Testar o fluxo de emails validando seus conectores [do Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) fornece instruções para testar se o fluxo de emails está definido corretamente.</span><span class="sxs-lookup"><span data-stu-id="35fc3-127">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
