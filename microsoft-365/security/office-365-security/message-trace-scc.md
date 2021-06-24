---
title: Rastreamento de mensagens no Microsoft 365 Defender portal
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem usar o link de rastreamento de mensagens no portal Microsoft 365 Defender para descobrir o que aconteceu com as mensagens.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7b6f7b12086e46c6ad93b60e8c510ea533815a1
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108110"
---
# <a name="message-trace-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="cb4d7-103">Rastreamento de mensagens no Microsoft 365 Defender portal</span><span class="sxs-lookup"><span data-stu-id="cb4d7-103">Message trace in the Microsoft 365 Defender portal</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cb4d7-104">**Aplica-se a**</span><span class="sxs-lookup"><span data-stu-id="cb4d7-104">**Applies to**</span></span>
- [<span data-ttu-id="cb4d7-105">Proteção do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="cb4d7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="cb4d7-106">Plano 1 e plano 2 do Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="cb4d7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="cb4d7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb4d7-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="cb4d7-108">O rastreamento de mensagens no portal Microsoft 365 Defender segue mensagens de email à medida que elas viajam pela sua Exchange Online organização.</span><span class="sxs-lookup"><span data-stu-id="cb4d7-108">Message trace in the Microsoft 365 Defender portal follows email messages as they travel through your Exchange Online organization.</span></span> <span data-ttu-id="cb4d7-109">Você pode determinar se uma mensagem foi recebida, rejeitada, adiada ou entregue pelo serviço.</span><span class="sxs-lookup"><span data-stu-id="cb4d7-109">You can determine if a message was received, rejected, deferred, or delivered by the service.</span></span> <span data-ttu-id="cb4d7-110">Também mostra as ações feitas na mensagem antes de ela chegar em seu status final.</span><span class="sxs-lookup"><span data-stu-id="cb4d7-110">It also shows what actions were taken on the message before it reached its final status.</span></span>

<span data-ttu-id="cb4d7-111">Você pode usar as informações do rastreamento de mensagens para responder com eficiência às perguntas do usuário sobre o que aconteceu com as mensagens, solucionar problemas de fluxo de emails e validar alterações de política.</span><span class="sxs-lookup"><span data-stu-id="cb4d7-111">You can use the information from message trace to efficiently answer user questions about what happened to messages, troubleshoot mail flow issues, and validate policy changes.</span></span>

> [!NOTE]
> <span data-ttu-id="cb4d7-112">O rastreamento de mensagens no portal Microsoft 365 Defender é apenas uma passagem para rastreamento de mensagem no centro de administração Exchange de mensagens.</span><span class="sxs-lookup"><span data-stu-id="cb4d7-112">Message trace in the Microsoft 365 Defender portal is just a pass through to Message trace in the Exchange admin center.</span></span> <span data-ttu-id="cb4d7-113">Para obter mais informações, consulte [Rastreamento de mensagens no centro de administração Exchange moderno.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)</span><span class="sxs-lookup"><span data-stu-id="cb4d7-113">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cb4d7-114">O que você precisa saber antes de começar?</span><span class="sxs-lookup"><span data-stu-id="cb4d7-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cb4d7-115">Você precisa ser membro dos grupos de função Gerenciamento da **Organização,** Gerenciamento de **Conformidade** ou Help **Desk** **Exchange Online** usar rastreamento de mensagens.</span><span class="sxs-lookup"><span data-stu-id="cb4d7-115">You need to be a member of the **Organization Management**, **Compliance Management** or **Help Desk** role groups in **Exchange Online** to use message trace.</span></span> <span data-ttu-id="cb4d7-116">Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="cb4d7-116">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="cb4d7-117">**Observações**: a associação à função Azure Active Directory correspondente no Centro de administração do Microsoft 365 fornece  aos usuários as permissões e permissões necessárias para outros recursos no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cb4d7-117">**Notes**: Membership in the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="cb4d7-118">Para obter mais informações, confira [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="cb4d7-118">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="cb4d7-119">O número máximo de mensagens exibidas nos resultados de um rastreamento de mensagem depende do tipo de relatório selecionado (consulte a seção Escolher tipo [de](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) relatório para obter detalhes).</span><span class="sxs-lookup"><span data-stu-id="cb4d7-119">The maximum number of messages that are displayed in the results of a message trace depends on the report type you selected (see the [Choose report type](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac#choose-report-type) section for details).</span></span> <span data-ttu-id="cb4d7-120">O cmdlet [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) no Exchange Online PowerShell ou no EOP PowerShell autônomo retorna todas as mensagens nos resultados.</span><span class="sxs-lookup"><span data-stu-id="cb4d7-120">The [Get-HistoricalSearch](/powershell/module/exchange/get-historicalsearch) cmdlet in Exchange Online PowerShell or standalone EOP PowerShell returns all messages in the results.</span></span>

## <a name="open-message-trace"></a><span data-ttu-id="cb4d7-121">Abrir rastreamento de mensagens</span><span class="sxs-lookup"><span data-stu-id="cb4d7-121">Open message trace</span></span>

<span data-ttu-id="cb4d7-122">No portal Microsoft 365 Defender ( <https://security.microsoft.com> ), acesse **Email & colaboração Exchange** rastreamento de \> **mensagens.**</span><span class="sxs-lookup"><span data-stu-id="cb4d7-122">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration** \> **Exchange message trace**.</span></span> <span data-ttu-id="cb4d7-123">Ou, para ir diretamente para a página de rastreamento de mensagens, use <https://admin.exchange.microsoft.com/#/messagetrace> .</span><span class="sxs-lookup"><span data-stu-id="cb4d7-123">Or, to go directly to the message trace page, use <https://admin.exchange.microsoft.com/#/messagetrace>.</span></span>

<span data-ttu-id="cb4d7-124">Neste ponto, o rastreamento de mensagens no EAC é aberto.</span><span class="sxs-lookup"><span data-stu-id="cb4d7-124">At this point, message trace in the EAC opens.</span></span> <span data-ttu-id="cb4d7-125">Para obter mais informações, consulte [Rastreamento de mensagens no centro de administração Exchange moderno.](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac)</span><span class="sxs-lookup"><span data-stu-id="cb4d7-125">For more information, see [Message trace in the modern Exchange admin center](/exchange/monitoring/trace-an-email-message/message-trace-modern-eac).</span></span>
