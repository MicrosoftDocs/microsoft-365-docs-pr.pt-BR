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
ms.openlocfilehash: 64138e2b6ae73c067709cde1912a96615d08ebf1
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471170"
---
# <a name="device-states"></a><span data-ttu-id="d3994-103">Estados do dispositivo</span><span class="sxs-lookup"><span data-stu-id="d3994-103">Device states</span></span>

<span data-ttu-id="d3994-104">Este artigo se aplica ao Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="d3994-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="d3994-105">Os dispositivos na lista **Ações do dispositivo** (página inicial do administrador \> **Ações do dispositivo**) podem ter os estados a seguir.</span><span class="sxs-lookup"><span data-stu-id="d3994-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="d3994-107">**Status**</span><span class="sxs-lookup"><span data-stu-id="d3994-107">**Status**</span></span>|<span data-ttu-id="d3994-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d3994-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d3994-109">Gerenciado pelo Intune</span><span class="sxs-lookup"><span data-stu-id="d3994-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="d3994-110">Gerenciado pelo Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="d3994-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="d3994-111">Desativação pendente</span><span class="sxs-lookup"><span data-stu-id="d3994-111">Retire pending</span></span>  <br/> |<span data-ttu-id="d3994-112">O Microsoft 365 Business Premium está preparando para remover dados da empresa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d3994-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="d3994-113">Desativação em andamento</span><span class="sxs-lookup"><span data-stu-id="d3994-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="d3994-114">O Microsoft 365 Business Premium está atualmente removendo dados da empresa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d3994-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="d3994-115">Falha na desativação</span><span class="sxs-lookup"><span data-stu-id="d3994-115">Retire failed</span></span>  <br/> | <span data-ttu-id="d3994-116">Falha ao remover ação de dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="d3994-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="d3994-117">Desativação cancelada</span><span class="sxs-lookup"><span data-stu-id="d3994-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="d3994-118">A ação de desativação foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="d3994-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="d3994-119">Apagamento pendente</span><span class="sxs-lookup"><span data-stu-id="d3994-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="d3994-120">Aguardando redefinição de fábrica para iniciar.</span><span class="sxs-lookup"><span data-stu-id="d3994-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="d3994-121">Apagamento em andamento</span><span class="sxs-lookup"><span data-stu-id="d3994-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="d3994-122">A redefinição de fábrica foi emitida.</span><span class="sxs-lookup"><span data-stu-id="d3994-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="d3994-123">Falha ao apagar</span><span class="sxs-lookup"><span data-stu-id="d3994-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="d3994-124">Não foi possível executar a redefinição de fábrica.</span><span class="sxs-lookup"><span data-stu-id="d3994-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="d3994-125">Apagamento cancelado</span><span class="sxs-lookup"><span data-stu-id="d3994-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="d3994-126">Apagamento de fábrica cancelado.</span><span class="sxs-lookup"><span data-stu-id="d3994-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="d3994-127">Não íntegro</span><span class="sxs-lookup"><span data-stu-id="d3994-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="d3994-128">Uma ação está pendente (ou em andamento), mas o dispositivo não foi verificado por mais de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="d3994-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="d3994-129">Exclusão pendente</span><span class="sxs-lookup"><span data-stu-id="d3994-129">Delete pending</span></span>  <br/> |<span data-ttu-id="d3994-130">Ação de Excluir está em andamento.</span><span class="sxs-lookup"><span data-stu-id="d3994-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="d3994-131">Descoberto</span><span class="sxs-lookup"><span data-stu-id="d3994-131">Discovered</span></span>  <br/> |<span data-ttu-id="d3994-132">O Microsoft 365 Business Premium detectou o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d3994-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
