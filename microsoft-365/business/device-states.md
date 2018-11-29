---
title: Estados do dispositivo
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
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
description: Saiba mais sobre estados de dispositivo no Microsoft 365 Business.
ms.openlocfilehash: bd6f1ad7f7671d9616fd14d477dfcfb164ff6bd0
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864907"
---
# <a name="device-states"></a><span data-ttu-id="d473a-103">Estados do dispositivo</span><span class="sxs-lookup"><span data-stu-id="d473a-103">Device states</span></span>

## <a name="device-states"></a><span data-ttu-id="d473a-104">Estados do dispositivo</span><span class="sxs-lookup"><span data-stu-id="d473a-104">Device states</span></span>

<span data-ttu-id="d473a-105">Os dispositivos na lista **Ações do dispositivo** (página inicial do administrador \> **Ações do dispositivo**) podem ter os estados a seguir.</span><span class="sxs-lookup"><span data-stu-id="d473a-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="d473a-107">**Status**</span><span class="sxs-lookup"><span data-stu-id="d473a-107">**Status**</span></span>|<span data-ttu-id="d473a-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d473a-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d473a-109">Gerenciado pelo Intune</span><span class="sxs-lookup"><span data-stu-id="d473a-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="d473a-110">Gerenciado pelo Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="d473a-110">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="d473a-111">Desativação pendente</span><span class="sxs-lookup"><span data-stu-id="d473a-111">Retire pending</span></span>  <br/> |<span data-ttu-id="d473a-112">O Microsoft 365 Business está se preparando para remover dados da empresa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d473a-112">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="d473a-113">Desativação em andamento</span><span class="sxs-lookup"><span data-stu-id="d473a-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="d473a-114">O Microsoft 365 Business no momento está removendo dados da empresa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d473a-114">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="d473a-115">Falha na desativação</span><span class="sxs-lookup"><span data-stu-id="d473a-115">Retire failed</span></span>  <br/> | <span data-ttu-id="d473a-116">Falha ao remover ação de dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="d473a-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="d473a-117">Desativação cancelada</span><span class="sxs-lookup"><span data-stu-id="d473a-117">Retire cancelled</span></span>  <br/> |<span data-ttu-id="d473a-118">A ação de desativação foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="d473a-118">Retire action was cancelled.</span></span>  <br/> |
|<span data-ttu-id="d473a-119">Apagamento pendente</span><span class="sxs-lookup"><span data-stu-id="d473a-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="d473a-120">Aguardando redefinição de fábrica para iniciar.</span><span class="sxs-lookup"><span data-stu-id="d473a-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="d473a-121">Apagamento em andamento</span><span class="sxs-lookup"><span data-stu-id="d473a-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="d473a-122">A redefinição de fábrica foi emitida.</span><span class="sxs-lookup"><span data-stu-id="d473a-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="d473a-123">Falha ao apagar</span><span class="sxs-lookup"><span data-stu-id="d473a-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="d473a-124">Não foi possível realizar a restauração de fábrica.</span><span class="sxs-lookup"><span data-stu-id="d473a-124">Couldn't perform factory reset.</span></span>  <br/> |
|<span data-ttu-id="d473a-125">Apagamento cancelado</span><span class="sxs-lookup"><span data-stu-id="d473a-125">Wipe cancelled</span></span>  <br/> |<span data-ttu-id="d473a-126">O apagamento de fábrica foi cancelado.</span><span class="sxs-lookup"><span data-stu-id="d473a-126">Factory wipe was cancelled.</span></span>  <br/> |
|<span data-ttu-id="d473a-127">Não íntegro</span><span class="sxs-lookup"><span data-stu-id="d473a-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="d473a-128">Isso significa que uma ação está aguardando (ou em andamento), mas o dispositivo não foi verificado em mais de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="d473a-128">This means that an action is pending (or in progress) but the device has not checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="d473a-129">Exclusão pendente</span><span class="sxs-lookup"><span data-stu-id="d473a-129">Delete pending</span></span>  <br/> |<span data-ttu-id="d473a-130">Ação de Excluir está em andamento.</span><span class="sxs-lookup"><span data-stu-id="d473a-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="d473a-131">Descoberto</span><span class="sxs-lookup"><span data-stu-id="d473a-131">Discovered</span></span>  <br/> |<span data-ttu-id="d473a-132">O Microsoft 365 Business detectou o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d473a-132">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
