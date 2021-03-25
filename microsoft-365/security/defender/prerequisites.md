---
title: Pré-requisitos do Microsoft 365 Defender
description: Saiba mais sobre os requisitos de licenciamento, hardware e software e outras configurações do Microsoft 365 Defender
keywords: requisitos, pré-requisitos, hardware, software, navegador, MTP, M365, licença, E5, A5, EMS, compra
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f9904ecb5b9ab0a0f634903a5dc0ee3049d06b38
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054031"
---
# <a name="microsoft-365-defender-prerequisites"></a><span data-ttu-id="244cb-104">Pré-requisitos do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="244cb-104">Microsoft 365 Defender prerequisites</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="244cb-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="244cb-105">**Applies to:**</span></span>
- <span data-ttu-id="244cb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="244cb-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="244cb-107">Saiba mais sobre licenciamento e outros requisitos para provisionamento e uso do [Microsoft 365 Defender](microsoft-365-defender.md).</span><span class="sxs-lookup"><span data-stu-id="244cb-107">Learn about licensing and other requirements for provisioning and using [Microsoft 365 Defender](microsoft-365-defender.md).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="244cb-108">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="244cb-108">Licensing requirements</span></span>
<span data-ttu-id="244cb-109">Qualquer uma dessas licenças oferece acesso aos recursos do Microsoft 365 Defender no Centro de segurança do Microsoft 365 sem custo adicional:</span><span class="sxs-lookup"><span data-stu-id="244cb-109">Any of these licenses gives you access to Microsoft 365 Defender features in Microsoft 365 security center without additional cost:</span></span>

- <span data-ttu-id="244cb-110">Microsoft 365 E5 ou A5</span><span class="sxs-lookup"><span data-stu-id="244cb-110">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="244cb-111">Segurança do Microsoft 365 E5 ou Segurança do A5</span><span class="sxs-lookup"><span data-stu-id="244cb-111">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="244cb-112">Windows 10 Enterprise E5 ou A5</span><span class="sxs-lookup"><span data-stu-id="244cb-112">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="244cb-113">Enterprise Mobility + Security (EMS) E5 ou A5</span><span class="sxs-lookup"><span data-stu-id="244cb-113">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="244cb-114">Office 365 E5 ou A5</span><span class="sxs-lookup"><span data-stu-id="244cb-114">Office 365 E5 or A5</span></span>
- <span data-ttu-id="244cb-115">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="244cb-115">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="244cb-116">Microsoft Defender para Identidade?</span><span class="sxs-lookup"><span data-stu-id="244cb-116">Microsoft Defender for Identity</span></span> 
- <span data-ttu-id="244cb-117">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="244cb-117">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="244cb-118">Defender para Office 365 (Plano 2)</span><span class="sxs-lookup"><span data-stu-id="244cb-118">Defender for Office 365 (Plan 2)</span></span>

<span data-ttu-id="244cb-119">Para obter mais informações, consulte os planos de serviço do [Microsoft 365 Enterprise.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)</span><span class="sxs-lookup"><span data-stu-id="244cb-119">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="244cb-120">Ainda não tem licença?</span><span class="sxs-lookup"><span data-stu-id="244cb-120">Don't have license yet?</span></span> [<span data-ttu-id="244cb-121">Experimentar ou comprar uma assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="244cb-121">Try or buy a Microsoft 365 subscription</span></span>](../../commerce/try-or-buy-microsoft-365.md?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="244cb-122">Verificar suas licenças existentes</span><span class="sxs-lookup"><span data-stu-id="244cb-122">Check your existing  licenses</span></span>
<span data-ttu-id="244cb-123">Vá para o Centro de administração do Microsoft 365 ([admin.microsoft.com](https://admin.microsoft.com/)) para exibir suas licenças existentes.</span><span class="sxs-lookup"><span data-stu-id="244cb-123">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="244cb-124">No Centro de administração, acesse **Cobrança** > **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="244cb-124">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="244cb-125">Você precisa ser atribuído ao administrador de **Cobrança** ou à função de leitor **global** no [Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para poder ver as informações de licença.</span><span class="sxs-lookup"><span data-stu-id="244cb-125">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="244cb-126">Se tiver problemas de acesso, entre em contato com um administrador global.</span><span class="sxs-lookup"><span data-stu-id="244cb-126">If you encounter access problems, contact a global admin.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="244cb-127">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="244cb-127">Required permissions</span></span>
<span data-ttu-id="244cb-128">Você deve ser um **administrador global** ou um administrador **de** segurança no Azure Active Directory para ativar o Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="244cb-128">You must be a **global administrator** or a **security administrator** in Azure Active Directory to turn on Microsoft 365 Defender.</span></span> <span data-ttu-id="244cb-129">Para obter a lista de funções necessárias para usar o Microsoft 365 Defender e informações sobre como o acesso aos dados é regulado, leia sobre como gerenciar o acesso ao [Microsoft 365 Defender](m365d-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="244cb-129">For the list of roles required to use Microsoft 365 Defender and information on how access to data is regulated, read about [managing access to Microsoft 365 Defender](m365d-permissions.md).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="244cb-130">Requisitos de navegador</span><span class="sxs-lookup"><span data-stu-id="244cb-130">Browser requirements</span></span>
<span data-ttu-id="244cb-131">Acesse o Microsoft 365 Defender no centro de segurança do Microsoft 365 usando o Microsoft Edge, o Internet Explorer 11 ou qualquer navegador da Web compatível com HTML 5.</span><span class="sxs-lookup"><span data-stu-id="244cb-131">Access Microsoft 365 Defender in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a><span data-ttu-id="244cb-132">Disponibilidade para US GCC, GCC High e outras instituições governamentais dos EUA</span><span class="sxs-lookup"><span data-stu-id="244cb-132">Availability to US GCC, GCC High, and other US government institutions</span></span>
<span data-ttu-id="244cb-133">Atualmente, o Microsoft 365 Defender *não* está disponível para:</span><span class="sxs-lookup"><span data-stu-id="244cb-133">Currently, Microsoft 365 Defender is *not* available to:</span></span>
- <span data-ttu-id="244cb-134">Nuvem da Comunidade governamental dos EUA (GCC)</span><span class="sxs-lookup"><span data-stu-id="244cb-134">US Government Community Cloud (GCC)</span></span>
- <span data-ttu-id="244cb-135">Nuvem da comunidade governamental dos EUA alta (GCC High)</span><span class="sxs-lookup"><span data-stu-id="244cb-135">US Government Community Cloud High (GCC High)</span></span>
- <span data-ttu-id="244cb-136">Departamento de Defesa dos EUA</span><span class="sxs-lookup"><span data-stu-id="244cb-136">US Department of Defense</span></span>
- <span data-ttu-id="244cb-137">Todas as instituições governamentais dos EUA com licenças comerciais</span><span class="sxs-lookup"><span data-stu-id="244cb-137">All US government institutions with commercial licenses</span></span>

## <a name="related-topics"></a><span data-ttu-id="244cb-138">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="244cb-138">Related topics</span></span>
- [<span data-ttu-id="244cb-139">Visão geral do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="244cb-139">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="244cb-140">Ativar o Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="244cb-140">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
- [<span data-ttu-id="244cb-141">Gerenciar acesso e permissões</span><span class="sxs-lookup"><span data-stu-id="244cb-141">Manage access and permissions</span></span>](m365d-permissions.md)