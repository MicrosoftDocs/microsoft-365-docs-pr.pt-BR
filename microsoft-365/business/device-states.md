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
ms.openlocfilehash: b55e6a5d538ec28d195225e93797cea27afd2e8b
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2019
ms.locfileid: "38320199"
---
# <a name="device-states"></a><span data-ttu-id="20cc8-103">Estados do dispositivo</span><span class="sxs-lookup"><span data-stu-id="20cc8-103">Device states</span></span>

<span data-ttu-id="20cc8-104">Os dispositivos na lista **Ações do dispositivo** (página inicial do administrador \> **Ações do dispositivo**) podem ter os estados a seguir.</span><span class="sxs-lookup"><span data-stu-id="20cc8-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="20cc8-106">**Status**</span><span class="sxs-lookup"><span data-stu-id="20cc8-106">**Status**</span></span>|<span data-ttu-id="20cc8-107">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="20cc8-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="20cc8-108">Gerenciado pelo Intune</span><span class="sxs-lookup"><span data-stu-id="20cc8-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="20cc8-109">Gerenciado pelo Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="20cc8-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="20cc8-110">Desativação pendente</span><span class="sxs-lookup"><span data-stu-id="20cc8-110">Retire pending</span></span>  <br/> |<span data-ttu-id="20cc8-111">O Microsoft 365 Business está se preparando para remover dados da empresa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="20cc8-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="20cc8-112">Desativação em andamento</span><span class="sxs-lookup"><span data-stu-id="20cc8-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="20cc8-113">O Microsoft 365 Business no momento está removendo dados da empresa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="20cc8-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="20cc8-114">Falha na desativação</span><span class="sxs-lookup"><span data-stu-id="20cc8-114">Retire failed</span></span>  <br/> | <span data-ttu-id="20cc8-115">Falha ao remover ação de dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="20cc8-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="20cc8-116">Desativação cancelada</span><span class="sxs-lookup"><span data-stu-id="20cc8-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="20cc8-117">A ação de desativação foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="20cc8-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="20cc8-118">Apagamento pendente</span><span class="sxs-lookup"><span data-stu-id="20cc8-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="20cc8-119">Aguardando redefinição de fábrica para iniciar.</span><span class="sxs-lookup"><span data-stu-id="20cc8-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="20cc8-120">Apagamento em andamento</span><span class="sxs-lookup"><span data-stu-id="20cc8-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="20cc8-121">A redefinição de fábrica foi emitida.</span><span class="sxs-lookup"><span data-stu-id="20cc8-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="20cc8-122">Falha ao apagar</span><span class="sxs-lookup"><span data-stu-id="20cc8-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="20cc8-123">Não foi possível executar a redefinição de fábrica.</span><span class="sxs-lookup"><span data-stu-id="20cc8-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="20cc8-124">Apagamento cancelado</span><span class="sxs-lookup"><span data-stu-id="20cc8-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="20cc8-125">Apagamento de fábrica cancelado.</span><span class="sxs-lookup"><span data-stu-id="20cc8-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="20cc8-126">Não íntegro</span><span class="sxs-lookup"><span data-stu-id="20cc8-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="20cc8-127">Uma ação está pendente (ou em andamento), mas o dispositivo não foi verificado por mais de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="20cc8-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="20cc8-128">Exclusão pendente</span><span class="sxs-lookup"><span data-stu-id="20cc8-128">Delete pending</span></span>  <br/> |<span data-ttu-id="20cc8-129">Ação de Excluir está em andamento.</span><span class="sxs-lookup"><span data-stu-id="20cc8-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="20cc8-130">Descoberto</span><span class="sxs-lookup"><span data-stu-id="20cc8-130">Discovered</span></span>  <br/> |<span data-ttu-id="20cc8-131">O Microsoft 365 Business detectou o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="20cc8-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
