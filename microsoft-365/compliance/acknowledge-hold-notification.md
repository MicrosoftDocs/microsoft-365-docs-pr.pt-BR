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
description: ''
ms.openlocfilehash: de542ad950fce061b63aa4b2aaf37821582d7466
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2019
ms.locfileid: "39256798"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="c7bd7-102">Confirmar uma notificação de retenção</span><span class="sxs-lookup"><span data-stu-id="c7bd7-102">Acknowledge a hold notification</span></span> 
<span data-ttu-id="c7bd7-103">Ao responder a uma solicitação ou investigação regulamentar, talvez seja necessário informar os responsáveis pela obrigação de preservar as ESI (electronicly Stored Information) e qualquer material que possa ser relevante para uma questão legal ativa ou iminente.</span><span class="sxs-lookup"><span data-stu-id="c7bd7-103">When responding to a regulatory request or investigation, you may be required to  inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="c7bd7-104">Depois de enviada, as equipes jurídicas devem saber que cada um deles recebeu, leu e entendeu e concordou em seguir as instruções fornecidas.</span><span class="sxs-lookup"><span data-stu-id="c7bd7-104">Once sent, legal teams must know that each custodian has received, read, and understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="c7bd7-105">Para ajudar a reduzir o tempo, o custo e o esforço de acompanhamento dos seus responsáveis, a descoberta eletrônica avançada permite que você envie e acompanhe notificações de bloqueio legal por email.</span><span class="sxs-lookup"><span data-stu-id="c7bd7-105">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="c7bd7-106">Além de avisos por email, todos os responsáveis terão acesso a um portal de conformidade individual, permitindo que os responsáveis sejam mantidos informados sobre as alterações no status de obrigação.</span><span class="sxs-lookup"><span data-stu-id="c7bd7-106">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="c7bd7-107">Notificações por e-mail</span><span class="sxs-lookup"><span data-stu-id="c7bd7-107">Email notifications</span></span>
<span data-ttu-id="c7bd7-108">Após a emissão de uma notificação de retenção legal, todos os responsáveis receberão um email exclusivo e personalizado contendo o aviso de retenção legal definido e adicionarão instruções.</span><span class="sxs-lookup"><span data-stu-id="c7bd7-108">Once a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!Tip] 
> <span data-ttu-id="c7bd7-109">Veja como você pode usar o [Editor de comunicação](using-communications-editor.md) interno para permitir que seus responsáveis reconheçam o aviso ou acesse seu portal de conformidade diretamente de seus emails.</span><span class="sxs-lookup"><span data-stu-id="c7bd7-109">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="c7bd7-110">Com base na configuração de sua notificação de retenção legal, seus responsáveis podem receber os seguintes avisos:</span><span class="sxs-lookup"><span data-stu-id="c7bd7-110">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="c7bd7-111">**Aviso de emissão** – este é o primeiro aviso enviado ao seu seu.</span><span class="sxs-lookup"><span data-stu-id="c7bd7-111">**Issuance notice** - This is the first notice sent to your custodian.</span></span> <span data-ttu-id="c7bd7-112">Isso conterá as instruções de emissão e o aviso de espera anexado ao final da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c7bd7-112">This will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="c7bd7-113">**Aviso de lembrete** -se habilitado, um aviso de lembrete será enviado aos seus responsáveis com base na frequência e no intervalo especificados.</span><span class="sxs-lookup"><span data-stu-id="c7bd7-113">**Reminder notice** - If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="c7bd7-114">Os lembretes continuarão a ser enviados até que os responsáveis tenham confirmado o aviso ou até que o número de lembretes tenha sido esgotado.</span><span class="sxs-lookup"><span data-stu-id="c7bd7-114">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="c7bd7-115">**Aviso de escalonamento** -se habilitado, um aviso de escalonamento será enviado aos seus responsáveis e ao gerente após os avisos de lembrete terem sido esgotados.</span><span class="sxs-lookup"><span data-stu-id="c7bd7-115">**Escalation notice** - If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="c7bd7-116">O sistema enviará automaticamente notificações de escalonamento até que os enrolamentos encaminhadas tenham sido concluídos ou até que os responsáveis reconheçam a notificação de espera.</span><span class="sxs-lookup"><span data-stu-id="c7bd7-116">The system will automatically send escalation notices until the alloted escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="c7bd7-117">**Aviso de reemissão** – durante o período de uma investigação, se o conteúdo de um aviso de isenção for atualizado, o aviso atualizado será enviado automaticamente para os responsáveis.</span><span class="sxs-lookup"><span data-stu-id="c7bd7-117">**Reissue notice** - During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="c7bd7-118">**Aviso de liberação** : quando um dos responsáveis é liberado do caso, ele receberá o aviso de lançamento.</span><span class="sxs-lookup"><span data-stu-id="c7bd7-118">**Release notice** - When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="c7bd7-119">Portal de conformidade</span><span class="sxs-lookup"><span data-stu-id="c7bd7-119">Compliance Portal</span></span>
<span data-ttu-id="c7bd7-120">Além das notificações por email, cada um dos responsáveis terá acesso a um portal de conformidade exclusivo.</span><span class="sxs-lookup"><span data-stu-id="c7bd7-120">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="c7bd7-121">Por meio do portal, cada um pode exibir, acessar e confirmar suas notificações de espera ativas.</span><span class="sxs-lookup"><span data-stu-id="c7bd7-121">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![Portal de conformidade para um responsáveis](media/CustodianPortal.jpg)
