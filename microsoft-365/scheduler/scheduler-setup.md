---
title: Configurando o Agendador para Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Configurando o Agendador para Microsoft 365.
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286123"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="b1a9d-103">Configurando o Agendador para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b1a9d-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="b1a9d-104">Para configurar o Agendador para Microsoft 365, a seguir estão os pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="b1a9d-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="b1a9d-105">**Do que preciso?**</span><span class="sxs-lookup"><span data-stu-id="b1a9d-105">**What do I need?**</span></span> |<span data-ttu-id="b1a9d-106">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b1a9d-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="b1a9d-107">Caixa de correio da Cortana</span><span class="sxs-lookup"><span data-stu-id="b1a9d-107">Cortana mailbox</span></span> |<span data-ttu-id="b1a9d-108">Os administradores de locatários precisarão definir uma caixa de correio para servir como a caixa de correio "Cortana" (ou seja, cortana@yourdomain.com).</span><span class="sxs-lookup"><span data-stu-id="b1a9d-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="b1a9d-109">Caixa de correio do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b1a9d-109">Exchange Online mailbox</span></span> |<span data-ttu-id="b1a9d-110">Os usuários devem ter um Exchange Online email e calendário</span><span class="sxs-lookup"><span data-stu-id="b1a9d-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="b1a9d-111">Licença do agendador</span><span class="sxs-lookup"><span data-stu-id="b1a9d-111">Scheduler license</span></span> |<span data-ttu-id="b1a9d-112">Para obter informações sobre licenciamento e preços, consulte [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span><span class="sxs-lookup"><span data-stu-id="b1a9d-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="b1a9d-113">Criar uma caixa de correio para a Cortana</span><span class="sxs-lookup"><span data-stu-id="b1a9d-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="b1a9d-114">Uma Exchange caixa de correio em seu locatário age como a caixa de correio da Cortana para seu locatário enviar e receber emails de e para a Cortana.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="b1a9d-115">Todos os emails enviados à Cortana são mantidos na caixa de correio da Cortana do locatário com base em sua política de retenção.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="b1a9d-116">Use o Microsoft 365 de administração para criar uma nova caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-116">Use the Microsoft 365 admin center to create a new mailbox.</span></span> <span data-ttu-id="b1a9d-117">Uma política de retenção de 30 dias é recomendada.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-117">A 30-day retention policy is recommended.</span></span> <span data-ttu-id="b1a9d-118">Use o nome Cortana no endereço SMTP principal da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="b1a9d-119">Nomes como "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" ou "Cortana.Scheduler@yourdomain.com" são recomendados.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>
- <span data-ttu-id="b1a9d-120">Contate a Microsoft (scheduler_m365@microsoft.com) para habilitar sua caixa de correio da Cortana.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-120">Contact Microsoft (scheduler_m365@microsoft.com) to enable your Cortana mailbox.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="b1a9d-121">Entre em contato com a Microsoft para configurar sua caixa de correio da Cortana para usar o serviço Agendador enviando emails scheduler_m365@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-121">You must contact Microsoft to configure your Cortana mailbox to use the Scheduler service by emailing scheduler_m365@microsoft.com.</span></span> <span data-ttu-id="b1a9d-122">A habilitação da caixa de correio da Cortana pode levar até duas semanas.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-122">Enabling your Cortana mailbox may take up to two weeks.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="b1a9d-123">Caixa de correio do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b1a9d-123">Exchange Online mailbox</span></span>
<span data-ttu-id="b1a9d-124">Agendador é um complemento para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-124">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="b1a9d-125">Os organizadores da reunião devem ter uma caixa Exchange Online caixa de correio e calendário para o Agendador funcionar.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-125">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="b1a9d-126">Requisitos do Exchange</span><span class="sxs-lookup"><span data-stu-id="b1a9d-126">Exchange requirements</span></span>

<span data-ttu-id="b1a9d-127">Além do Agendador de licenciamento, você deve ter uma das seguintes licenças:</span><span class="sxs-lookup"><span data-stu-id="b1a9d-127">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="b1a9d-128">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="b1a9d-128">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="b1a9d-129">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="b1a9d-129">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="b1a9d-130">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="b1a9d-130">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="b1a9d-131">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="b1a9d-131">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="b1a9d-132">Exchange Online Plan 1 or Plan 2 license.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-132">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="b1a9d-133">**O agendador Microsoft 365** não está disponível para usuários de Office 365 operados pela 21Vianet na China.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-133">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="b1a9d-134">Ele também não está disponível para usuários de Microsoft 365 com a nuvem alemã que usa o data trustee German Telekom.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-134">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="b1a9d-135">Ele tem suporte para usuários na Alemanha cujo local de dados não está no datacenter alemão.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-135">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="b1a9d-136">Este recurso também não é compatível com usuários da Nuvem Governamental, incluindo GCC, Consumidor, GCC Alto ou DoD.</span><span class="sxs-lookup"><span data-stu-id="b1a9d-136">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
