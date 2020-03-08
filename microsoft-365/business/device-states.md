---
title: Estados do dispositivo
f1.keywords:
- NOCSH
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
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Saiba mais sobre os vários Estados de dispositivos na lista de ações de dispositivos no Home Page do administrador no Microsoft 365 Business.
ms.openlocfilehash: bed1610814ca0d60adb4b4b3d0018e3e7e6d763f
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42560811"
---
# <a name="device-states"></a><span data-ttu-id="e902d-103">Estados do dispositivo</span><span class="sxs-lookup"><span data-stu-id="e902d-103">Device states</span></span>

<span data-ttu-id="e902d-104">Os dispositivos na lista **Ações do dispositivo** (página inicial do administrador \> **Ações do dispositivo**) podem ter os estados a seguir.</span><span class="sxs-lookup"><span data-stu-id="e902d-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="e902d-106">**Status**</span><span class="sxs-lookup"><span data-stu-id="e902d-106">**Status**</span></span>|<span data-ttu-id="e902d-107">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e902d-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e902d-108">Gerenciado pelo Intune</span><span class="sxs-lookup"><span data-stu-id="e902d-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="e902d-109">Gerenciado pelo Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="e902d-109">Managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="e902d-110">Desativação pendente</span><span class="sxs-lookup"><span data-stu-id="e902d-110">Retire pending</span></span>  <br/> |<span data-ttu-id="e902d-111">O Microsoft 365 Business está se preparando para remover dados da empresa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e902d-111">Microsoft 365 Business is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="e902d-112">Desativação em andamento</span><span class="sxs-lookup"><span data-stu-id="e902d-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="e902d-113">O Microsoft 365 Business no momento está removendo dados da empresa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e902d-113">Microsoft 365 Business is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="e902d-114">Falha na desativação</span><span class="sxs-lookup"><span data-stu-id="e902d-114">Retire failed</span></span>  <br/> | <span data-ttu-id="e902d-115">Falha ao remover ação de dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="e902d-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="e902d-116">Desativação cancelada</span><span class="sxs-lookup"><span data-stu-id="e902d-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="e902d-117">A ação de desativação foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="e902d-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="e902d-118">Apagamento pendente</span><span class="sxs-lookup"><span data-stu-id="e902d-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="e902d-119">Aguardando redefinição de fábrica para iniciar.</span><span class="sxs-lookup"><span data-stu-id="e902d-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="e902d-120">Apagamento em andamento</span><span class="sxs-lookup"><span data-stu-id="e902d-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="e902d-121">A redefinição de fábrica foi emitida.</span><span class="sxs-lookup"><span data-stu-id="e902d-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="e902d-122">Falha ao apagar</span><span class="sxs-lookup"><span data-stu-id="e902d-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="e902d-123">Não foi possível executar a redefinição de fábrica.</span><span class="sxs-lookup"><span data-stu-id="e902d-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="e902d-124">Apagamento cancelado</span><span class="sxs-lookup"><span data-stu-id="e902d-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="e902d-125">Apagamento de fábrica cancelado.</span><span class="sxs-lookup"><span data-stu-id="e902d-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="e902d-126">Não íntegro</span><span class="sxs-lookup"><span data-stu-id="e902d-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="e902d-127">Uma ação está pendente (ou em andamento), mas o dispositivo não foi verificado por mais de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="e902d-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="e902d-128">Exclusão pendente</span><span class="sxs-lookup"><span data-stu-id="e902d-128">Delete pending</span></span>  <br/> |<span data-ttu-id="e902d-129">Ação de Excluir está em andamento.</span><span class="sxs-lookup"><span data-stu-id="e902d-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="e902d-130">Descoberto</span><span class="sxs-lookup"><span data-stu-id="e902d-130">Discovered</span></span>  <br/> |<span data-ttu-id="e902d-131">O Microsoft 365 Business detectou o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e902d-131">Microsoft 365 Business has detected the device.</span></span>  <br/> |
   
