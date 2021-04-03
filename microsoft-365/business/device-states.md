---
title: Estados do dispositivo
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Saiba mais sobre os vários estados de dispositivo na lista Ações do dispositivo na home admin no Microsoft 365 para empresas.
ms.openlocfilehash: e6f1b428413d094e0a1ce3afb026528074038736
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578458"
---
# <a name="device-states"></a><span data-ttu-id="65c81-103">Estados do dispositivo</span><span class="sxs-lookup"><span data-stu-id="65c81-103">Device states</span></span>

<span data-ttu-id="65c81-104">Este artigo se aplica ao Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="65c81-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="65c81-105">Os dispositivos na lista **Ações do dispositivo** (página inicial do administrador \> **Ações do dispositivo**) podem ter os estados a seguir.</span><span class="sxs-lookup"><span data-stu-id="65c81-105">Devices in the **Device actions** list (Admin home \> **Device actions**) can have the following states.</span></span>
  
![In the Device actions list, you can see the Devices states.](../media/a621c47e-45d9-4e1a-beb9-c03254d40c1d.png)
  
|<span data-ttu-id="65c81-107">**Status**</span><span class="sxs-lookup"><span data-stu-id="65c81-107">**Status**</span></span>|<span data-ttu-id="65c81-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="65c81-108">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="65c81-109">Gerenciado pelo Intune</span><span class="sxs-lookup"><span data-stu-id="65c81-109">Managed by Intune</span></span>  <br/> |<span data-ttu-id="65c81-110">Gerenciado pelo Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="65c81-110">Managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="65c81-111">Desativação pendente</span><span class="sxs-lookup"><span data-stu-id="65c81-111">Retire pending</span></span>  <br/> |<span data-ttu-id="65c81-112">O Microsoft 365 Business Premium está se preparando para remover dados da empresa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="65c81-112">Microsoft 365 Business Premium is getting ready to remove company data from the device.</span></span>  <br/> |
|<span data-ttu-id="65c81-113">Desativação em andamento</span><span class="sxs-lookup"><span data-stu-id="65c81-113">Retire in progress</span></span>  <br/> |<span data-ttu-id="65c81-114">O Microsoft 365 Business Premium está removendo dados da empresa do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="65c81-114">Microsoft 365 Business Premium is currently removing company data from the device.</span></span>  <br/> |
|<span data-ttu-id="65c81-115">Falha na desativação</span><span class="sxs-lookup"><span data-stu-id="65c81-115">Retire failed</span></span>  <br/> | <span data-ttu-id="65c81-116">Falha ao remover ação de dados da empresa.</span><span class="sxs-lookup"><span data-stu-id="65c81-116">Remove company data action failed.</span></span>  <br/> |
|<span data-ttu-id="65c81-117">Retirar cancelado</span><span class="sxs-lookup"><span data-stu-id="65c81-117">Retire canceled</span></span>  <br/> |<span data-ttu-id="65c81-118">A ação Desaposente foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="65c81-118">Retire action was canceled.</span></span>  <br/> |
|<span data-ttu-id="65c81-119">Apagamento pendente</span><span class="sxs-lookup"><span data-stu-id="65c81-119">Wipe pending</span></span>  <br/> |<span data-ttu-id="65c81-120">Aguardando redefinição de fábrica para iniciar.</span><span class="sxs-lookup"><span data-stu-id="65c81-120">Waiting for factory reset to start.</span></span>  <br/> |
|<span data-ttu-id="65c81-121">Apagamento em andamento</span><span class="sxs-lookup"><span data-stu-id="65c81-121">Wipe in progress</span></span>  <br/> |<span data-ttu-id="65c81-122">A redefinição de fábrica foi emitida.</span><span class="sxs-lookup"><span data-stu-id="65c81-122">Factory reset has been issued.</span></span>  <br/> |
|<span data-ttu-id="65c81-123">Falha ao apagar</span><span class="sxs-lookup"><span data-stu-id="65c81-123">Wipe failed</span></span>  <br/> |<span data-ttu-id="65c81-124">Não foi consegui fazer a redefinição de fábrica.</span><span class="sxs-lookup"><span data-stu-id="65c81-124">Couldn't do factory reset.</span></span>  <br/> |
|<span data-ttu-id="65c81-125">Apagar cancelado</span><span class="sxs-lookup"><span data-stu-id="65c81-125">Wipe canceled</span></span>  <br/> |<span data-ttu-id="65c81-126">A limpeza de fábrica foi cancelada.</span><span class="sxs-lookup"><span data-stu-id="65c81-126">Factory wipe was canceled.</span></span>  <br/> |
|<span data-ttu-id="65c81-127">Não íntegro</span><span class="sxs-lookup"><span data-stu-id="65c81-127">Unhealthy</span></span>  <br/> |<span data-ttu-id="65c81-128">Uma ação está pendente (ou em andamento), mas o dispositivo não faz check-in há mais de 30 dias.</span><span class="sxs-lookup"><span data-stu-id="65c81-128">An action is pending (or in progress), but the device hasn't checked in for 30+ days.</span></span>  <br/> |
|<span data-ttu-id="65c81-129">Exclusão pendente</span><span class="sxs-lookup"><span data-stu-id="65c81-129">Delete pending</span></span>  <br/> |<span data-ttu-id="65c81-130">Ação de Excluir está em andamento.</span><span class="sxs-lookup"><span data-stu-id="65c81-130">Delete action is pending.</span></span>  <br/> |
|<span data-ttu-id="65c81-131">Descoberto</span><span class="sxs-lookup"><span data-stu-id="65c81-131">Discovered</span></span>  <br/> |<span data-ttu-id="65c81-132">O Microsoft 365 Business Premium detectou o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="65c81-132">Microsoft 365 Business Premium has detected the device.</span></span>  <br/> |
   
