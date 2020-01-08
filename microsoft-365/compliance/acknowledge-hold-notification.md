---
title: Confirmar uma notificação de retenção
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Talvez seja necessário informar os responsáveis pela obrigação de preservar as informações armazenadas eletronicamente como parte da investigação legal. A descoberta eletrônica avançada permite que você gerencie facilmente o processo de notificação de espera.
ms.openlocfilehash: 477396e9b249de0edbbe52c5310abe21a825a3e8
ms.sourcegitcommit: 8ac1b6586678035050fc422e6fb503fa478be397
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962360"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="8b811-104">Confirmar uma notificação de retenção</span><span class="sxs-lookup"><span data-stu-id="8b811-104">Acknowledge a hold notification</span></span>

<span data-ttu-id="8b811-105">Ao responder a uma solicitação ou investigação regulamentar, talvez seja necessário informar os responsáveis pela obrigação de preservar as ESI (electronicly Stored Information) e qualquer material que possa ser relevante para uma questão legal ativa ou iminente.</span><span class="sxs-lookup"><span data-stu-id="8b811-105">When responding to a regulatory request or investigation, you may be required to inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="8b811-106">Depois de enviada, as equipes jurídicas devem saber que cada um deles recebeu, leu, entendeu e concordou em seguir as instruções fornecidas.</span><span class="sxs-lookup"><span data-stu-id="8b811-106">Once sent, legal teams must know that each custodian has received, read, understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="8b811-107">Para ajudar a reduzir o tempo, o custo e o esforço de acompanhamento dos seus responsáveis, a descoberta eletrônica avançada permite que você envie e acompanhe notificações de bloqueio legal por email.</span><span class="sxs-lookup"><span data-stu-id="8b811-107">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="8b811-108">Além de avisos por email, todos os responsáveis terão acesso a um portal de conformidade individual, permitindo que os responsáveis sejam mantidos informados sobre as alterações no status de obrigação.</span><span class="sxs-lookup"><span data-stu-id="8b811-108">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="8b811-109">Notificações por e-mail</span><span class="sxs-lookup"><span data-stu-id="8b811-109">Email notifications</span></span>

<span data-ttu-id="8b811-110">Após a emissão de uma notificação de retenção legal, cada um receberá um email exclusivo e personalizado contendo o aviso de retenção legal definido e adicionadas instruções.</span><span class="sxs-lookup"><span data-stu-id="8b811-110">After a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!TIP]
> <span data-ttu-id="8b811-111">Veja como você pode usar o [Editor de comunicação](using-communications-editor.md) interno para permitir que seus responsáveis reconheçam o aviso ou acesse seu portal de conformidade diretamente de seus emails.</span><span class="sxs-lookup"><span data-stu-id="8b811-111">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="8b811-112">Com base na configuração de sua notificação de retenção legal, seus responsáveis podem receber os seguintes avisos:</span><span class="sxs-lookup"><span data-stu-id="8b811-112">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="8b811-113">**Aviso de emissão:** O primeiro aviso enviado para seus responsáveis.</span><span class="sxs-lookup"><span data-stu-id="8b811-113">**Issuance notice:** The first notice sent to your custodian.</span></span> <span data-ttu-id="8b811-114">Este aviso conterá as instruções de emissão e o aviso de isenção anexado ao final da mensagem.</span><span class="sxs-lookup"><span data-stu-id="8b811-114">This notice will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="8b811-115">**Aviso de lembrete:** Se for habilitada, um aviso de lembrete será enviado aos seus responsáveis com base na frequência e no intervalo especificados.</span><span class="sxs-lookup"><span data-stu-id="8b811-115">**Reminder notice:** If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="8b811-116">Os lembretes continuarão a ser enviados até que os responsáveis tenham confirmado o aviso ou até que o número de lembretes tenha sido esgotado.</span><span class="sxs-lookup"><span data-stu-id="8b811-116">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="8b811-117">**Aviso de escalonamento:** Se for habilitada, um aviso de escalonamento será enviado aos seus responsáveis e ao gerente após os avisos de lembrete terem sido esgotados.</span><span class="sxs-lookup"><span data-stu-id="8b811-117">**Escalation notice:** If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="8b811-118">O sistema enviará automaticamente notificações de escalonamento até que o número especificado de escalonamentos seja concluído ou até que os responsáveis reconheçam a notificação de espera.</span><span class="sxs-lookup"><span data-stu-id="8b811-118">The system will automatically send escalation notices until the specified number of escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="8b811-119">**Aviso de reemissão:** Durante o período de uma investigação, se o conteúdo de um aviso de isenção for atualizado, o aviso atualizado será enviado automaticamente para os responsáveis.</span><span class="sxs-lookup"><span data-stu-id="8b811-119">**Reissue notice:** During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="8b811-120">**Aviso de lançamento:** Quando um dos responsáveis é liberado do caso, ele enviará o aviso de lançamento.</span><span class="sxs-lookup"><span data-stu-id="8b811-120">**Release notice:** When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="8b811-121">Portal de conformidade</span><span class="sxs-lookup"><span data-stu-id="8b811-121">Compliance Portal</span></span>

<span data-ttu-id="8b811-122">Além das notificações por email, cada um dos responsáveis terá acesso a um portal de conformidade exclusivo.</span><span class="sxs-lookup"><span data-stu-id="8b811-122">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="8b811-123">Por meio do portal, cada um pode exibir, acessar e confirmar suas notificações de espera ativas.</span><span class="sxs-lookup"><span data-stu-id="8b811-123">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![Portal de conformidade para um responsáveis](media/CustodianPortal.jpg)
