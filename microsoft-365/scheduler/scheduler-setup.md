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
ms.openlocfilehash: 924b25e3d921f402c97632f7475ed5beea98d5c7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362541"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="9da40-103">Configurando o Agendador para o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9da40-103">Setting up Scheduler for Microsoft 365</span></span>


<span data-ttu-id="9da40-104">Para configurar o Agendador para Microsoft 365, a seguir estão os pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="9da40-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

| <span data-ttu-id="9da40-105">Do que preciso?</span><span class="sxs-lookup"><span data-stu-id="9da40-105">What do I need?</span></span> | <span data-ttu-id="9da40-106">Descrição</span><span class="sxs-lookup"><span data-stu-id="9da40-106">Description</span></span> |
|-------------------|-------------|
|<span data-ttu-id="9da40-107">Cortana caixa de correio</span><span class="sxs-lookup"><span data-stu-id="9da40-107">Cortana mailbox</span></span> |<span data-ttu-id="9da40-108">Os administradores de locatários precisarão definir uma caixa de correio para servir como a caixa de correio "Cortana" (ou seja, cortana@yourdomain.com).</span><span class="sxs-lookup"><span data-stu-id="9da40-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="9da40-109">Caixa de correio do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9da40-109">Exchange Online mailbox</span></span> |<span data-ttu-id="9da40-110">Os usuários devem ter um Exchange Online email e calendário</span><span class="sxs-lookup"><span data-stu-id="9da40-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="9da40-111">Licença do agendador</span><span class="sxs-lookup"><span data-stu-id="9da40-111">Scheduler license</span></span> |<span data-ttu-id="9da40-112">Para obter informações sobre licenciamento e preços, consulte [Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).</span><span class="sxs-lookup"><span data-stu-id="9da40-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="9da40-113">Criar uma caixa de correio para Cortana</span><span class="sxs-lookup"><span data-stu-id="9da40-113">Create a mailbox for Cortana</span></span>

<span data-ttu-id="9da40-114">Uma Exchange de correio em seu locatário age como a caixa de correio Cortana seu locatário para enviar e receber emails de e para Cortana.</span><span class="sxs-lookup"><span data-stu-id="9da40-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="9da40-115">Todos os emails enviados Cortana são mantidos na caixa de correio de Cortana de seu locatário com base em sua política de retenção.</span><span class="sxs-lookup"><span data-stu-id="9da40-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="9da40-116">Use o Centro de administração do Microsoft 365 para criar uma caixa de correio de usuário.</span><span class="sxs-lookup"><span data-stu-id="9da40-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="9da40-117">Uma política de retenção de 30 dias é recomendada.</span><span class="sxs-lookup"><span data-stu-id="9da40-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="9da40-118">Use o nome Cortana no endereço SMTP principal da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="9da40-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="9da40-119">Nomes como "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" ou "Cortana. Scheduler@yourdomain.com' são recomendados.</span><span class="sxs-lookup"><span data-stu-id="9da40-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="9da40-120">Designar a caixa de correio como Assistente do Agendador</span><span class="sxs-lookup"><span data-stu-id="9da40-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="9da40-121">Depois que uma caixa de correio exclusiva para Cortana Agendador tiver sido criada, você deve designar a caixa de correio para Microsoft 365 formalmente.</span><span class="sxs-lookup"><span data-stu-id="9da40-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="9da40-122">Depois de designar Cortana caixa de correio do Agendador, ela estará disponível para agendar reuniões em nome de seus usuários.</span><span class="sxs-lookup"><span data-stu-id="9da40-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="9da40-123">Para designar Cortana caixa de correio do Agendador, um administrador autorizado deve executar um comando do PowerShell de uma linha.</span><span class="sxs-lookup"><span data-stu-id="9da40-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="9da40-124">Conexão para Microsoft 365 espaço de executar o PowerShell remoto para sua organização.</span><span class="sxs-lookup"><span data-stu-id="9da40-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>

2. <span data-ttu-id="9da40-125">Execute o seguinte script do PowerShell para designar a caixa de correio do Agendador:</span><span class="sxs-lookup"><span data-stu-id="9da40-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

    ```powershell
    Set-mailbox cortana@contoso.com -SchedulerAssistant:$true
    ```
    
    <span data-ttu-id="9da40-126">Depois de executar esse comando "set" na caixa de correio Cortana Agendador, um novo "PersistedCapability" é definido na caixa de correio para observar que essa caixa de correio é o "SchedulerAssistant".</span><span class="sxs-lookup"><span data-stu-id="9da40-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="9da40-127">Siga estas etapas para conectar sua organização ao PowerShell se você não tiver feito isso anteriormente: Conexão para Microsoft 365 [com o PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="9da40-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="9da40-128">Para descobrir qual caixa de correio na sua organização está definida como assistente Cortana agendador, execute a função get:</span><span class="sxs-lookup"><span data-stu-id="9da40-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> <span data-ttu-id="9da40-129">Pode levar até duas horas para a caixa de correio do Agendador concluir o provisionamento completo para definir o recurso SchedulerAssistant.</span><span class="sxs-lookup"><span data-stu-id="9da40-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="9da40-130">Caixa de correio do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="9da40-130">Exchange Online mailbox</span></span>
<span data-ttu-id="9da40-131">Uma licença do Agendador é um complemento para Microsoft 365, que permite ao organizador da reunião delegar suas tarefas de agendamento de reunião ao assistente do Agendador.</span><span class="sxs-lookup"><span data-stu-id="9da40-131">A Scheduler license is an add-on to Microsoft 365, that enables the meeting organizer to delegate their meeting scheduling tasks to their Scheduler assistant.</span></span> <span data-ttu-id="9da40-132">Para que o Agendador funcione, normalmente por meio Microsoft 365 licença, os organizadores da reunião exigem os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="9da40-132">For the Scheduler to work, typically through Microsoft 365 license, meeting organizers require the following components:</span></span>

- <span data-ttu-id="9da40-133">Uma caixa de correio designada como caixa de correio de assistente de agendamento</span><span class="sxs-lookup"><span data-stu-id="9da40-133">A mailbox designated as Scheduler assistant mailbox</span></span>
- <span data-ttu-id="9da40-134">Licença do agendador</span><span class="sxs-lookup"><span data-stu-id="9da40-134">Scheduler license</span></span>
- <span data-ttu-id="9da40-135">Exchange Online caixa de correio e calendário</span><span class="sxs-lookup"><span data-stu-id="9da40-135">Exchange Online mailbox and calendar</span></span>

<span data-ttu-id="9da40-136">Os participantes da reunião não exigem agendador ou Microsoft 365 licença.</span><span class="sxs-lookup"><span data-stu-id="9da40-136">The meeting attendees do not require Scheduler or Microsoft 365 license.</span></span>

## <a name="scheduler-end-user-license-requirements"></a><span data-ttu-id="9da40-137">Requisitos de licença do usuário final do agendador</span><span class="sxs-lookup"><span data-stu-id="9da40-137">Scheduler end-user license requirements</span></span>

<span data-ttu-id="9da40-138">Uma licença do Agendador requer uma das seguintes licenças:</span><span class="sxs-lookup"><span data-stu-id="9da40-138">A Scheduler license requires one of the following licenses:</span></span>

- <span data-ttu-id="9da40-139">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="9da40-139">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="9da40-140">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="9da40-140">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="9da40-141">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="9da40-141">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="9da40-142">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="9da40-142">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="9da40-143">Exchange Online Plan 1 or Plan 2 license.</span><span class="sxs-lookup"><span data-stu-id="9da40-143">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]

> <span data-ttu-id="9da40-144">O agendador para Microsoft 365 está disponível em ambientes multi-locatários em todo o mundo somente em inglês.</span><span class="sxs-lookup"><span data-stu-id="9da40-144">Scheduler for Microsoft 365 is available in worldwide multi-tenant environments in English only.</span></span> <span data-ttu-id="9da40-145">**O agendador Microsoft 365** não está disponível para os usuários de:</span><span class="sxs-lookup"><span data-stu-id="9da40-145">**Scheduler for Microsoft 365** isn't available to users of:</span></span>

- <span data-ttu-id="9da40-146">Microsoft 365 operado pela 21Vianet na China</span><span class="sxs-lookup"><span data-stu-id="9da40-146">Microsoft 365 operated by 21Vianet in China</span></span>
- <span data-ttu-id="9da40-147">Microsoft 365 com a nuvem alemã que usa o telekom alemão do destinatário de dados</span><span class="sxs-lookup"><span data-stu-id="9da40-147">Microsoft 365 with German cloud that uses the data trustee German Telekom</span></span>
- <span data-ttu-id="9da40-148">Nuvem governamental incluindo GCC, Consumidor, GCC Alta ou DoD</span><span class="sxs-lookup"><span data-stu-id="9da40-148">Government cloud including GCC, Consumer, GCC High, or DoD</span></span>

<span data-ttu-id="9da40-149">O agendador dá suporte a usuários na Alemanha cuja localização de dados não está no datacenter alemão.</span><span class="sxs-lookup"><span data-stu-id="9da40-149">Scheduler does support users in Germany whose data location is not in the German datacenter.</span></span>
