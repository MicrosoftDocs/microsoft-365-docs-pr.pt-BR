---
title: Confirmar uma notificação de retenção
f1.keywords:
- NOCSH
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
ms.custom:
- seo-marvel-apr2020
description: Saiba como usar a Descoberta Avançada para enviar e acompanhar notificações de espera legal por email, bem como monitorar o status de obrigação.
ms.openlocfilehash: 393d8884a4d4d39056267666fdce6a2754cb582b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034881"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="1c71e-103">Confirmar uma notificação de retenção</span><span class="sxs-lookup"><span data-stu-id="1c71e-103">Acknowledge a hold notification</span></span>

<span data-ttu-id="1c71e-104">Ao responder a uma solicitação ou investigação regulamentar, você pode ser solicitado a informar aos responsáveis sobre sua obrigação de preservar informações armazenadas eletronicamente (ESI) e quaisquer materiais que possam ser relevantes a um assunto legal ativo ou iminente.</span><span class="sxs-lookup"><span data-stu-id="1c71e-104">When responding to a regulatory request or investigation, you may be required to inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="1c71e-105">Depois de enviados, as equipes legais devem saber que cada custodiante recebeu, leu, compreendeu e aceitou seguir as instruções fornecidas.</span><span class="sxs-lookup"><span data-stu-id="1c71e-105">Once sent, legal teams must know that each custodian has received, read, understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="1c71e-106">Para ajudar a reduzir o tempo, o custo e o esforço de acompanhar seus responsáveis, a Descoberta Avançada permite que você envie e acompanhe as notificações de espera legal por email.</span><span class="sxs-lookup"><span data-stu-id="1c71e-106">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="1c71e-107">Além de avisos por email, cada custodiante terá acesso a um Portal de Conformidade individualizado, permitindo que os custodiantes sejam mantidos informados das alterações em seu status de obrigação.</span><span class="sxs-lookup"><span data-stu-id="1c71e-107">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="1c71e-108">Notificações por e-mail</span><span class="sxs-lookup"><span data-stu-id="1c71e-108">Email notifications</span></span>

<span data-ttu-id="1c71e-109">Depois que uma Notificação de Responsabilidade Legal tiver sido emitida, cada custodiante receberá um email exclusivo e personalizado contendo seu aviso de responsabilidade legal definido e instruções adicionadas.</span><span class="sxs-lookup"><span data-stu-id="1c71e-109">After a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!TIP]
> <span data-ttu-id="1c71e-110">Veja como você pode usar o  [Editor](using-communications-editor.md) de Comunicação interno para permitir que seus custodiantes confirmem sua notificação ou acessem o Portal de Conformidade diretamente de seus emails.</span><span class="sxs-lookup"><span data-stu-id="1c71e-110">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="1c71e-111">Com base na configuração da notificação de espera legal, seus responsáveis podem receber os seguintes avisos:</span><span class="sxs-lookup"><span data-stu-id="1c71e-111">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="1c71e-112">**Aviso de emissão:** O primeiro aviso enviado ao seu custodiado.</span><span class="sxs-lookup"><span data-stu-id="1c71e-112">**Issuance notice:** The first notice sent to your custodian.</span></span> <span data-ttu-id="1c71e-113">Este aviso conterá suas instruções de emissão e o aviso de espera anexado ao final da mensagem.</span><span class="sxs-lookup"><span data-stu-id="1c71e-113">This notice will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="1c71e-114">**Aviso de lembrete:** Se habilitada, um aviso de lembrete será enviado aos seus custodiantes com base na frequência e intervalo especificados.</span><span class="sxs-lookup"><span data-stu-id="1c71e-114">**Reminder notice:** If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="1c71e-115">Os lembretes continuarão a ser enviados até que o custodiatário tenha confirmado o aviso ou até que o número de lembretes tenha sido esgotado.</span><span class="sxs-lookup"><span data-stu-id="1c71e-115">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="1c71e-116">**Aviso de escalonamento:** Se habilitada, um aviso de escalonamento será enviado ao responsável e ao gerente depois que os avisos de lembrete se esgotarem.</span><span class="sxs-lookup"><span data-stu-id="1c71e-116">**Escalation notice:** If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="1c71e-117">O sistema enviará automaticamente avisos de escalonamento até que o número especificado de escalonamentos tenha sido concluído ou até que o custodiante confirme a notificação de suspensão.</span><span class="sxs-lookup"><span data-stu-id="1c71e-117">The system will automatically send escalation notices until the specified number of escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="1c71e-118">**Aviso de reemissão:** Durante o curso de uma investigação, se o conteúdo do aviso de suspensão for atualizado, o aviso atualizado será enviado automaticamente ao custodiante.</span><span class="sxs-lookup"><span data-stu-id="1c71e-118">**Reissue notice:** During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="1c71e-119">**Aviso de versão:** Quando um custodiante for liberado da ocorrência, ele será enviado o aviso de liberação.</span><span class="sxs-lookup"><span data-stu-id="1c71e-119">**Release notice:** When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="1c71e-120">Portal de Conformidade</span><span class="sxs-lookup"><span data-stu-id="1c71e-120">Compliance Portal</span></span>

<span data-ttu-id="1c71e-121">Além das notificações por email, cada custodiante terá acesso a um Portal de Conformidade exclusivo.</span><span class="sxs-lookup"><span data-stu-id="1c71e-121">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="1c71e-122">Por meio do portal, cada custodiante pode exibir, acessar e confirmar suas notificações de espera ativa.</span><span class="sxs-lookup"><span data-stu-id="1c71e-122">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![Portal de Conformidade para um custodiatário](../media/CustodianPortal.jpg)
