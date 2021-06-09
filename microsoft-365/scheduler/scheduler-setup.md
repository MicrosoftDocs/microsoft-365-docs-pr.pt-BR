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
ms.openlocfilehash: c17cdbbf71359a2725a3b0a145cba5feffd7c853
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809186"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="14eb2-103">Configurando o Agendador para Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="14eb2-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="14eb2-104">Para configurar o Agendador para Microsoft 365, a seguir estão os pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="14eb2-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="14eb2-105">**Do que preciso?**</span><span class="sxs-lookup"><span data-stu-id="14eb2-105">**What do I need?**</span></span> |<span data-ttu-id="14eb2-106">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="14eb2-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="14eb2-107">Caixa de correio da Cortana</span><span class="sxs-lookup"><span data-stu-id="14eb2-107">Cortana mailbox</span></span> |<span data-ttu-id="14eb2-108">Os administradores de locatários precisarão definir uma caixa de correio para servir como a caixa de correio "Cortana" (ou seja, cortana@yourdomain.com).</span><span class="sxs-lookup"><span data-stu-id="14eb2-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="14eb2-109">Caixa de correio do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="14eb2-109">Exchange Online mailbox</span></span> |<span data-ttu-id="14eb2-110">Os usuários devem ter um Exchange Online email e calendário</span><span class="sxs-lookup"><span data-stu-id="14eb2-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="14eb2-111">Licença do agendador</span><span class="sxs-lookup"><span data-stu-id="14eb2-111">Scheduler license</span></span> |<span data-ttu-id="14eb2-112">Para obter informações sobre licenciamento e preços, consulte [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span><span class="sxs-lookup"><span data-stu-id="14eb2-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="14eb2-113">Criar uma caixa de correio para a Cortana</span><span class="sxs-lookup"><span data-stu-id="14eb2-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="14eb2-114">Uma Exchange caixa de correio em seu locatário age como a caixa de correio da Cortana para seu locatário enviar e receber emails de e para a Cortana.</span><span class="sxs-lookup"><span data-stu-id="14eb2-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="14eb2-115">Todos os emails enviados à Cortana são mantidos na caixa de correio da Cortana do locatário com base em sua política de retenção.</span><span class="sxs-lookup"><span data-stu-id="14eb2-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="14eb2-116">Use o Microsoft 365 de administração para criar uma caixa de correio de usuário.</span><span class="sxs-lookup"><span data-stu-id="14eb2-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="14eb2-117">Uma política de retenção de 30 dias é recomendada.</span><span class="sxs-lookup"><span data-stu-id="14eb2-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="14eb2-118">Use o nome Cortana no endereço SMTP principal da caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="14eb2-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="14eb2-119">Nomes como "Cortana@yourdomain.com", "CortanaScheduler@contoso.com" ou "Cortana.Scheduler@yourdomain.com" são recomendados.</span><span class="sxs-lookup"><span data-stu-id="14eb2-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="14eb2-120">Designar a caixa de correio como Assistente do Agendador</span><span class="sxs-lookup"><span data-stu-id="14eb2-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="14eb2-121">Após a criação de uma caixa de correio exclusiva para o Agendador da Cortana, você deve designar a caixa de correio para Microsoft 365 formalmente.</span><span class="sxs-lookup"><span data-stu-id="14eb2-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="14eb2-122">Depois de designar a caixa de correio do Agendador da Cortana, ela estará disponível para agendar reuniões em nome de seus usuários.</span><span class="sxs-lookup"><span data-stu-id="14eb2-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="14eb2-123">Para designar a caixa de correio do Agendador da Cortana, um administrador autorizado deve executar um comando do PowerShell de uma linha.</span><span class="sxs-lookup"><span data-stu-id="14eb2-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="14eb2-124">Conexão para Microsoft 365 espaço de executar o PowerShell remoto para sua organização.</span><span class="sxs-lookup"><span data-stu-id="14eb2-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>
2. <span data-ttu-id="14eb2-125">Execute o seguinte script do PowerShell para designar a caixa de correio do Agendador:</span><span class="sxs-lookup"><span data-stu-id="14eb2-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

```powershell

Set-mailbox cortana@contoso.com -SchedulerAssistant:$true

```

<span data-ttu-id="14eb2-126">Depois de executar esse comando "set" na caixa de correio do Agendador da Cortana, um novo "PersistedCapability" é definido na caixa de correio para observar que essa caixa de correio é o "SchedulerAssistant".</span><span class="sxs-lookup"><span data-stu-id="14eb2-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="14eb2-127">Siga estas etapas para conectar sua organização ao PowerShell se você não tiver feito isso anteriormente: Conexão para Microsoft 365 [com o PowerShell - Microsoft 365 Enterprise | Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="14eb2-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell - Microsoft 365 Enterprise | Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)</span></span>

<span data-ttu-id="14eb2-128">Para descobrir qual caixa de correio em sua organização está definida como assistente do Agendador cortana, execute a função get:</span><span class="sxs-lookup"><span data-stu-id="14eb2-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>
 
```powershell

Get-mailbox -Organization contoso.com | where {($_.PersistedCapabilities -like "SchedulerAssistant")}

```

> [!IMPORTANT]
> <span data-ttu-id="14eb2-129">Pode levar até duas horas para a caixa de correio do Agendador concluir o provisionamento completo para definir o recurso SchedulerAssistant.</span><span class="sxs-lookup"><span data-stu-id="14eb2-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="14eb2-130">Caixa de correio do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="14eb2-130">Exchange Online mailbox</span></span>
<span data-ttu-id="14eb2-131">Agendador é um complemento para Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="14eb2-131">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="14eb2-132">Os organizadores da reunião devem ter uma caixa Exchange Online caixa de correio e calendário para o Agendador funcionar.</span><span class="sxs-lookup"><span data-stu-id="14eb2-132">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="14eb2-133">Requisitos do Exchange</span><span class="sxs-lookup"><span data-stu-id="14eb2-133">Exchange requirements</span></span>

<span data-ttu-id="14eb2-134">Além do Agendador de licenciamento, você deve ter uma das seguintes licenças:</span><span class="sxs-lookup"><span data-stu-id="14eb2-134">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="14eb2-135">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="14eb2-135">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="14eb2-136">Business Basic, Business, Business Standard, Business Premium</span><span class="sxs-lookup"><span data-stu-id="14eb2-136">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="14eb2-137">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="14eb2-137">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="14eb2-138">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="14eb2-138">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="14eb2-139">Exchange Online Plan 1 or Plan 2 license.</span><span class="sxs-lookup"><span data-stu-id="14eb2-139">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="14eb2-140">**O agendador Microsoft 365** não está disponível para usuários de Office 365 operados pela 21Vianet na China.</span><span class="sxs-lookup"><span data-stu-id="14eb2-140">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="14eb2-141">Ele também não está disponível para usuários de Microsoft 365 com a nuvem alemã que usa o data trustee German Telekom.</span><span class="sxs-lookup"><span data-stu-id="14eb2-141">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="14eb2-142">Ele tem suporte para usuários na Alemanha cujo local de dados não está no datacenter alemão.</span><span class="sxs-lookup"><span data-stu-id="14eb2-142">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="14eb2-143">Este recurso também não é compatível com usuários da Nuvem Governamental, incluindo GCC, Consumidor, GCC Alto ou DoD.</span><span class="sxs-lookup"><span data-stu-id="14eb2-143">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>