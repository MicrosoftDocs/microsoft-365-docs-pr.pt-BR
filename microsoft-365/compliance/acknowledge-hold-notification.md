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
description: Saiba como usar o Advanced eDiscovery para enviar e acompanhar notificações de responsabilidade legal por email, bem como monitorar o status da obrigação.
ms.openlocfilehash: 393d8884a4d4d39056267666fdce6a2754cb582b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034881"
---
# <a name="acknowledge-a-hold-notification"></a><span data-ttu-id="fa247-103">Confirmar uma notificação de retenção</span><span class="sxs-lookup"><span data-stu-id="fa247-103">Acknowledge a hold notification</span></span>

<span data-ttu-id="fa247-104">Ao responder a uma solicitação ou investigação regulamentar, talvez seja necessário informar aos custodiantes sobre sua obrigação de preservar as informações armazenadas eletronicamente (ESI) e qualquer material que possa ser relevante para uma questão jurídica ativa ou iminente.</span><span class="sxs-lookup"><span data-stu-id="fa247-104">When responding to a regulatory request or investigation, you may be required to inform custodians of their obligation to preserve electronically stored information (ESI) and any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="fa247-105">Depois de enviado, as equipes jurídicas devem saber que cada custodiante recebeu, leu, compreendeu e aceitou seguir as instruções fornecidas.</span><span class="sxs-lookup"><span data-stu-id="fa247-105">Once sent, legal teams must know that each custodian has received, read, understood, and agreed to follow the given instructions.</span></span>

<span data-ttu-id="fa247-106">Para ajudar a reduzir o tempo, o custo e o esforço de acompanhamento com seus custodiantes, Advanced eDiscovery permite que você envie e acompanhe as notificações de diminuição legal por email.</span><span class="sxs-lookup"><span data-stu-id="fa247-106">To help reduce the time, cost, and effort of following up with your custodians,  Advanced eDiscovery allows you to send and follow up on legal hold notifications through email.</span></span> <span data-ttu-id="fa247-107">Além dos avisos por email, cada custodiante terá acesso a um Portal de Conformidade individualizado, permitindo que os custodiantes sejam mantidos informados sobre alterações no status da obrigação.</span><span class="sxs-lookup"><span data-stu-id="fa247-107">In addition to email notices, each custodian will have access to an individualized Compliance Portal, allowing custodians to be kept informed of changes to their obligation status.</span></span>

## <a name="email-notifications"></a><span data-ttu-id="fa247-108">Notificações por e-mail</span><span class="sxs-lookup"><span data-stu-id="fa247-108">Email notifications</span></span>

<span data-ttu-id="fa247-109">Depois que uma Notificação de Responsabilidade Legal tiver sido emitida, cada custodiante receberá um email exclusivo e personalizado contendo seu aviso de responsabilidade legal definido e instruções adicionadas.</span><span class="sxs-lookup"><span data-stu-id="fa247-109">After a Legal Hold Notification has been issued, each custodian will receive a unique and personalized email containing your defined legal hold notice and added instructions.</span></span> 

> [!TIP]
> <span data-ttu-id="fa247-110">Veja como você pode usar o  [Editor](using-communications-editor.md) de Comunicação interno para permitir que seus custodiantes reconheçam sua notificação ou acessem o Portal de Conformidade diretamente de seus emails.</span><span class="sxs-lookup"><span data-stu-id="fa247-110">See how you can use the built-in  [Communication Editor](using-communications-editor.md) to allow your custodians to acknowledge their notice or access their Compliance Portal directly from their email.</span></span>

<span data-ttu-id="fa247-111">Com base na configuração de sua notificação de enseada legal, seus custodiantes podem receber os seguintes avisos:</span><span class="sxs-lookup"><span data-stu-id="fa247-111">Based on the configuration of your legal hold notification, your custodians may receive the following notices:</span></span> 

- <span data-ttu-id="fa247-112">**Aviso de emissão:** O primeiro aviso enviado ao seu custodiado.</span><span class="sxs-lookup"><span data-stu-id="fa247-112">**Issuance notice:** The first notice sent to your custodian.</span></span> <span data-ttu-id="fa247-113">Este aviso conterá suas instruções de emissão e o aviso de espera anexado ao final da mensagem.</span><span class="sxs-lookup"><span data-stu-id="fa247-113">This notice will contain your issuance instructions and the hold notice appended to the end of your message.</span></span>

- <span data-ttu-id="fa247-114">**Aviso de lembrete:** Se habilitado, um aviso de lembrete será enviado aos seus custodiantes com base na frequência e intervalo especificados.</span><span class="sxs-lookup"><span data-stu-id="fa247-114">**Reminder notice:** If enabled, a reminder notice will be sent to your custodians based on the specified frequency and interval.</span></span> <span data-ttu-id="fa247-115">Os lembretes continuarão a ser enviados até que o custodiado tenha reconhecido o aviso ou até que o número de lembretes tenha sido esgotado.</span><span class="sxs-lookup"><span data-stu-id="fa247-115">The reminders will continue to be sent either until the custodian has acknowledged their notice or until the number of reminders have been exhausted.</span></span>

- <span data-ttu-id="fa247-116">**Aviso de escalonamento:** Se habilitado, um aviso de escalonamento será enviado para o seu custodiante e seu gerente depois que os avisos de lembrete foram esgotados.</span><span class="sxs-lookup"><span data-stu-id="fa247-116">**Escalation notice:** If enabled, an escalation notice will be sent to your custodian and their manager after the reminder notices have been exhausted.</span></span> <span data-ttu-id="fa247-117">O sistema enviará automaticamente avisos de escalonamento até que o número especificado de escalonamentos seja concluído ou até que o custodiante confirme a notificação de espera.</span><span class="sxs-lookup"><span data-stu-id="fa247-117">The system will automatically send escalation notices until the specified number of escalations have been completed or until the custodian acknowledges their hold notification.</span></span>

- <span data-ttu-id="fa247-118">**Aviso de reemissão:** Durante o curso de uma investigação, se o conteúdo do aviso de suspensão for atualizado, o aviso atualizado será enviado automaticamente para o custodiante.</span><span class="sxs-lookup"><span data-stu-id="fa247-118">**Reissue notice:** During the course of an investigation, if the contents of the hold notice are updated, then the updated notice will automatically be sent to the custodian.</span></span>

- <span data-ttu-id="fa247-119">**Aviso de lançamento:** Quando um custodiante é liberado do caso, eles serão enviados o aviso de versão.</span><span class="sxs-lookup"><span data-stu-id="fa247-119">**Release notice:** When a custodian is released from the case, they'll be sent the release notice.</span></span> 

## <a name="compliance-portal"></a><span data-ttu-id="fa247-120">Portal de Conformidade</span><span class="sxs-lookup"><span data-stu-id="fa247-120">Compliance Portal</span></span>

<span data-ttu-id="fa247-121">Além das notificações por email, cada custodiante terá acesso a um Portal de Conformidade exclusivo.</span><span class="sxs-lookup"><span data-stu-id="fa247-121">In addition to the email notifications, each custodian will have access to a unique Compliance Portal.</span></span> <span data-ttu-id="fa247-122">Por meio do portal, cada custodiante pode exibir, acessar e reconhecer suas notificações de espera ativas.</span><span class="sxs-lookup"><span data-stu-id="fa247-122">Through the portal, each custodian can view, access, and acknowledge their active hold notifications.</span></span>

![Portal de Conformidade para um custodiado](../media/CustodianPortal.jpg)
