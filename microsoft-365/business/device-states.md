---
title: Estados do dispositivo
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Saiba mais sobre os Estados de dispositivos no Microsoft 365 Business.
ms.openlocfilehash: 06e5c800e6a104785c1fd0724223e05d7729722e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072711"
---
# <a name="device-states"></a><span data-ttu-id="14b88-103">Estados do dispositivo</span><span class="sxs-lookup"><span data-stu-id="14b88-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="14b88-104">Estados do dispositivo</span><span class="sxs-lookup"><span data-stu-id="14b88-104">Device states</span></span>

<span data-ttu-id="14b88-105">Os dispositivos na lista **Ações do dispositivo** (página inicial do administrador \> **Ações do dispositivo**) podem ter os estados a seguir.</span><span class="sxs-lookup"><span data-stu-id="14b88-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="14b88-107">**Status**</span><span class="sxs-lookup"><span data-stu-id="14b88-107">**Status**</span></span>|<span data-ttu-id="14b88-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="14b88-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="14b88-109">Gerenciado pelo Intune</span><span class="sxs-lookup"><span data-stu-id="14b88-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="14b88-110">Gerenciado pelo Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="14b88-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="14b88-111">Desativação pendente</span><span class="sxs-lookup"><span data-stu-id="14b88-111">Retire pending</span></span>  <br/> |<span data-ttu-id="14b88-112">O Microsoft 365 Business está se preparando para remover dados da empresa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="14b88-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="14b88-113">Desativação em andamento</span><span class="sxs-lookup"><span data-stu-id="14b88-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="14b88-114">O Microsoft 365 Business no momento está removendo dados da empresa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="14b88-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="14b88-115">Falha na desativação</span><span class="sxs-lookup"><span data-stu-id="14b88-115">Retire failed</span></span>  <br/> | <span data-ttu-id="14b88-116">Falha ao remover ação de dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="14b88-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="14b88-117">Desativação cancelada</span><span class="sxs-lookup"><span data-stu-id="14b88-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="14b88-118">A ação de desativação foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="14b88-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="14b88-119">Apagamento pendente</span><span class="sxs-lookup"><span data-stu-id="14b88-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="14b88-120">Aguardando redefinição de fábrica para iniciar.</span><span class="sxs-lookup"><span data-stu-id="14b88-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="14b88-121">Apagamento em andamento</span><span class="sxs-lookup"><span data-stu-id="14b88-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="14b88-122">A redefinição de fábrica foi emitida.</span><span class="sxs-lookup"><span data-stu-id="14b88-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="14b88-123">Falha ao apagar</span><span class="sxs-lookup"><span data-stu-id="14b88-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="14b88-124">Não foi possível realizar a restauração de fábrica.</span><span class="sxs-lookup"><span data-stu-id="14b88-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="14b88-125">Apagamento cancelado</span><span class="sxs-lookup"><span data-stu-id="14b88-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="14b88-126">O apagamento de fábrica foi cancelado.</span><span class="sxs-lookup"><span data-stu-id="14b88-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="14b88-127">Não íntegro</span><span class="sxs-lookup"><span data-stu-id="14b88-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="14b88-128">Isso significa que uma ação está aguardando (ou em andamento), mas o dispositivo não foi verificado em mais de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="14b88-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="14b88-129">Exclusão pendente</span><span class="sxs-lookup"><span data-stu-id="14b88-129">Delete pending</span></span>  <br/> |<span data-ttu-id="14b88-130">Ação de Excluir está em andamento.</span><span class="sxs-lookup"><span data-stu-id="14b88-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="14b88-131">Descoberto</span><span class="sxs-lookup"><span data-stu-id="14b88-131">Discovered</span></span>  <br/> |<span data-ttu-id="14b88-132">O Microsoft 365 Business detectou o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="14b88-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
