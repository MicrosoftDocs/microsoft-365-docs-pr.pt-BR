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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: c3ac23c5-d4b4-4b1b-b7ce-ea759521bf8c
description: Saiba mais sobre os vários Estados de dispositivos na lista de ações de dispositivos no Home Page do administrador no Microsoft 365 for Business.
ms.openlocfilehash: 90c11caa03249408ba2916d303bcb4a59fbcca8c
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400945"
---
# <a name="device-states"></a><span data-ttu-id="3cecc-103">Estados do dispositivo</span><span class="sxs-lookup"><span data-stu-id="3cecc-103">Device states</span></span>

<span data-ttu-id="3cecc-104">Os dispositivos na lista **Ações do dispositivo** (página inicial do administrador \> **Ações do dispositivo**) podem ter os estados a seguir.</span><span class="sxs-lookup"><span data-stu-id="3cecc-104">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="3cecc-106">**Status**</span><span class="sxs-lookup"><span data-stu-id="3cecc-106">**Status**</span></span>|<span data-ttu-id="3cecc-107">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3cecc-107">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3cecc-108">Gerenciado pelo Intune</span><span class="sxs-lookup"><span data-stu-id="3cecc-108">Managed by Intune</span></span>  <br/> |<span data-ttu-id="3cecc-109">Gerenciado pelo Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="3cecc-109">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="3cecc-110">Desativação pendente</span><span class="sxs-lookup"><span data-stu-id="3cecc-110">Retire pending</span></span>  <br/> |<span data-ttu-id="3cecc-111">O Microsoft 365 Business Premium está preparando para remover dados da empresa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3cecc-111">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="3cecc-112">Desativação em andamento</span><span class="sxs-lookup"><span data-stu-id="3cecc-112">Retire in progress</span></span>  <br/> |<span data-ttu-id="3cecc-113">O Microsoft 365 Business Premium está atualmente removendo dados da empresa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3cecc-113">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="3cecc-114">Falha na desativação</span><span class="sxs-lookup"><span data-stu-id="3cecc-114">Retire failed</span></span>  <br/> | <span data-ttu-id="3cecc-115">Falha ao remover ação de dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="3cecc-115">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="3cecc-116">Desativação cancelada</span><span class="sxs-lookup"><span data-stu-id="3cecc-116">Retire canceled</span></span>  <br/> |<span data-ttu-id="3cecc-117">A ação de desativação foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="3cecc-117">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="3cecc-118">Apagamento pendente</span><span class="sxs-lookup"><span data-stu-id="3cecc-118">Wipe pending</span></span>  <br/> |<span data-ttu-id="3cecc-119">Aguardando redefinição de fábrica para iniciar.</span><span class="sxs-lookup"><span data-stu-id="3cecc-119">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="3cecc-120">Apagamento em andamento</span><span class="sxs-lookup"><span data-stu-id="3cecc-120">Wipe in progress</span></span>  <br/> |<span data-ttu-id="3cecc-121">A redefinição de fábrica foi emitida.</span><span class="sxs-lookup"><span data-stu-id="3cecc-121">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="3cecc-122">Falha ao apagar</span><span class="sxs-lookup"><span data-stu-id="3cecc-122">Wipe failed</span></span>  <br/> |<span data-ttu-id="3cecc-123">Não foi possível executar a redefinição de fábrica.</span><span class="sxs-lookup"><span data-stu-id="3cecc-123">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="3cecc-124">Apagamento cancelado</span><span class="sxs-lookup"><span data-stu-id="3cecc-124">Wipe canceled</span></span>  <br/> |<span data-ttu-id="3cecc-125">Apagamento de fábrica cancelado.</span><span class="sxs-lookup"><span data-stu-id="3cecc-125">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="3cecc-126">Não íntegro</span><span class="sxs-lookup"><span data-stu-id="3cecc-126">Unhealthy</span></span>  <br/> |<span data-ttu-id="3cecc-127">Uma ação está pendente (ou em andamento), mas o dispositivo não foi verificado por mais de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="3cecc-127">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="3cecc-128">Exclusão pendente</span><span class="sxs-lookup"><span data-stu-id="3cecc-128">Delete pending</span></span>  <br/> |<span data-ttu-id="3cecc-129">Ação de Excluir está em andamento.</span><span class="sxs-lookup"><span data-stu-id="3cecc-129">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="3cecc-130">Descoberto</span><span class="sxs-lookup"><span data-stu-id="3cecc-130">Discovered</span></span>  <br/> |<span data-ttu-id="3cecc-131">O Microsoft 365 Business Premium detectou o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3cecc-131">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
