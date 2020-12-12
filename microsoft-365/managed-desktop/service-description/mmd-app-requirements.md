---
title: Requisitos do aplicativo da área de trabalho gerenciada da Microsoft
description: ''
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 322a46ce48cce4d080e51f482178462934d5c8f2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659709"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="99969-103">Requisitos do aplicativo da área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="99969-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="99969-104">O Microsoft Managed desktop exige que possamos gerenciar dispositivos usando uma abordagem específica para garantir o desempenho, a confiabilidade e a capacidade de manutenção dos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="99969-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span>


|<span data-ttu-id="99969-105">Área de gerenciamento</span><span class="sxs-lookup"><span data-stu-id="99969-105">Management area</span></span>  |<span data-ttu-id="99969-106">Abordagem da área de trabalho gerenciada da Microsoft</span><span class="sxs-lookup"><span data-stu-id="99969-106">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="99969-107">Configuração de dispositivo ou gerenciamento de políticas</span><span class="sxs-lookup"><span data-stu-id="99969-107">Device configuration or policy management</span></span>     |  <span data-ttu-id="99969-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="99969-108">Microsoft Intune</span></span>       |
|<span data-ttu-id="99969-109">Gerenciamento de aplicativo</span><span class="sxs-lookup"><span data-stu-id="99969-109">Application management</span></span>     | <span data-ttu-id="99969-110">Microsoft Intune e portal da empresa</span><span class="sxs-lookup"><span data-stu-id="99969-110">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="99969-111">Implantação de driver</span><span class="sxs-lookup"><span data-stu-id="99969-111">Driver deployment</span></span>     |  <span data-ttu-id="99969-112">Drivers incluídos no dispositivo, no Windows Update ou no Intune</span><span class="sxs-lookup"><span data-stu-id="99969-112">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="99969-113">Segurança do dispositivo</span><span class="sxs-lookup"><span data-stu-id="99969-113">Device security</span></span>     | <span data-ttu-id="99969-114">Consulte [segurança do dispositivo](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="99969-114">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="99969-115">Gerenciamento de identidades e acesso</span><span class="sxs-lookup"><span data-stu-id="99969-115">Identity and access management</span></span>     | <span data-ttu-id="99969-116">Consulte [Gerenciamento de identidade e acesso](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="99969-116">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="99969-117">Segurança da rede</span><span class="sxs-lookup"><span data-stu-id="99969-117">Network security</span></span>     | <span data-ttu-id="99969-118">Consulte [segurança de rede](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="99969-118">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="99969-119">Segurança de informações</span><span class="sxs-lookup"><span data-stu-id="99969-119">Information security</span></span>     |  <span data-ttu-id="99969-120">Consulte [segurança de informações](security.md#information-security)</span><span class="sxs-lookup"><span data-stu-id="99969-120">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="99969-121">Recuperação de dados</span><span class="sxs-lookup"><span data-stu-id="99969-121">Data recovery</span></span>     | <span data-ttu-id="99969-122">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="99969-122">OneDrive for Business</span></span>        |
|<span data-ttu-id="99969-123">Produtividade principal</span><span class="sxs-lookup"><span data-stu-id="99969-123">Core productivity</span></span>     | <span data-ttu-id="99969-124">Microsoft 365 Apps para empresas</span><span class="sxs-lookup"><span data-stu-id="99969-124">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="99969-125">Navegador</span><span class="sxs-lookup"><span data-stu-id="99969-125">Browser</span></span>     | <span data-ttu-id="99969-126">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="99969-126">Microsoft Edge</span></span>        |




<span data-ttu-id="99969-127">A área de trabalho gerenciada da Microsoft pode monitorar outros softwares em execução em dispositivos gerenciados.</span><span class="sxs-lookup"><span data-stu-id="99969-127">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="99969-128">Se isso afetar negativamente o gerenciamento de dispositivos, a segurança de dispositivos, o desempenho ou a confiabilidade, você poderá precisar solicitar uma [exceção para o plano de serviço](customizing.md).</span><span class="sxs-lookup"><span data-stu-id="99969-128">If it negatively impacts device management, device security, performance, or reliability, you might be required to request an [exception to the service plan](customizing.md).</span></span>
