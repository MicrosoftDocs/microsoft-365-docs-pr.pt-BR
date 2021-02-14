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
description: Saiba mais sobre os vários estados de dispositivo na lista de ações do dispositivo na página de administração no Microsoft 365 para empresas.
ms.openlocfilehash: 64138e2b6ae73c067709cde1912a96615d08ebf1
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471170"
---
# <a name="device-states"></a><span data-ttu-id="0e65c-103">Estados do dispositivo</span><span class="sxs-lookup"><span data-stu-id="0e65c-103">Device states</span></span>

<span data-ttu-id="0e65c-104">Este artigo se aplica ao Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="0e65c-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="0e65c-105">Os dispositivos na lista **Ações do dispositivo** (página inicial do administrador \> **Ações do dispositivo**) podem ter os estados a seguir.</span><span class="sxs-lookup"><span data-stu-id="0e65c-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="0e65c-107">**Status**</span><span class="sxs-lookup"><span data-stu-id="0e65c-107">**Status**</span></span>|<span data-ttu-id="0e65c-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="0e65c-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0e65c-109">Gerenciado pelo Intune</span><span class="sxs-lookup"><span data-stu-id="0e65c-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="0e65c-110">Gerenciado pelo Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="0e65c-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="0e65c-111">Desativação pendente</span><span class="sxs-lookup"><span data-stu-id="0e65c-111">Retire pending</span></span>  <br/> |<span data-ttu-id="0e65c-112">O Microsoft 365 Business Premium está se preparando para remover dados da empresa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e65c-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="0e65c-113">Desativação em andamento</span><span class="sxs-lookup"><span data-stu-id="0e65c-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="0e65c-114">No momento, o Microsoft 365 Business Premium remove dados da empresa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e65c-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="0e65c-115">Falha na desativação</span><span class="sxs-lookup"><span data-stu-id="0e65c-115">Retire failed</span></span>  <br/> | <span data-ttu-id="0e65c-116">Falha ao remover ação de dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="0e65c-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="0e65c-117">Retire canceled</span><span class="sxs-lookup"><span data-stu-id="0e65c-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="0e65c-118">A ação Destivar foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="0e65c-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="0e65c-119">Apagamento pendente</span><span class="sxs-lookup"><span data-stu-id="0e65c-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="0e65c-120">Aguardando redefinição de fábrica para iniciar.</span><span class="sxs-lookup"><span data-stu-id="0e65c-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="0e65c-121">Apagamento em andamento</span><span class="sxs-lookup"><span data-stu-id="0e65c-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="0e65c-122">A redefinição de fábrica foi emitida.</span><span class="sxs-lookup"><span data-stu-id="0e65c-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="0e65c-123">Falha ao apagar</span><span class="sxs-lookup"><span data-stu-id="0e65c-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="0e65c-124">Não foi preciso redefinir a fábrica.</span><span class="sxs-lookup"><span data-stu-id="0e65c-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="0e65c-125">Apagando cancelado</span><span class="sxs-lookup"><span data-stu-id="0e65c-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="0e65c-126">A limpeza de fábrica foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="0e65c-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="0e65c-127">Não íntegro</span><span class="sxs-lookup"><span data-stu-id="0e65c-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="0e65c-128">Uma ação está pendente (ou em andamento), mas o dispositivo não fez check-in por mais de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="0e65c-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="0e65c-129">Exclusão pendente</span><span class="sxs-lookup"><span data-stu-id="0e65c-129">Delete pending</span></span>  <br/> |<span data-ttu-id="0e65c-130">Ação de Excluir está em andamento.</span><span class="sxs-lookup"><span data-stu-id="0e65c-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="0e65c-131">Descoberto</span><span class="sxs-lookup"><span data-stu-id="0e65c-131">Discovered</span></span>  <br/> |<span data-ttu-id="0e65c-132">O Microsoft 365 Business Premium detectou o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0e65c-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
