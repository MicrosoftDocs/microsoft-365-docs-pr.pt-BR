---
title: Pré-requisitos da proteção contra ameaças da Microsoft
description: Saiba mais sobre os requisitos de licenciamento, hardware e software, além de outras configurações para proteção contra ameaças da Microsoft
keywords: requisitos, pré-requisitos, hardware, software, navegador, MTP, M365, licença, e5, a5, EMS, compra
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 66b3f7e446416b6252050e6f41a2b22d99d25767
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209230"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="73fd9-104">Pré-requisitos da proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="73fd9-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="73fd9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="73fd9-105">**Applies to:**</span></span>
- <span data-ttu-id="73fd9-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="73fd9-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="73fd9-107">Saiba mais sobre os requisitos de licenciamento, hardware e software e outras definições de configuração para provisionar e usar a proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="73fd9-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="73fd9-108">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="73fd9-108">Licensing requirements</span></span>

>[!IMPORTANT]
><span data-ttu-id="73fd9-109">A partir de 12 de maio de 2020, a Microsoft irá distribuir novas experiências otimizadas em torno dos requisitos de licenciamento e [ativando a proteção contra ameaças da Microsoft](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="73fd9-109">Starting May 12, 2020, Microsoft will gradually roll out new, optimized experiences around licensing requirements and [turning on Microsoft Threat Protection](mtp-enable.md).</span></span> <span data-ttu-id="73fd9-110">Durante várias semanas durante esse período, alguns clientes começarão a ver as alterações nas experiências do Portal.</span><span class="sxs-lookup"><span data-stu-id="73fd9-110">For several weeks during this period, some customers will start to see changes to their portal experiences.</span></span> <span data-ttu-id="73fd9-111">As informações sobre as novas experiências são marcadas como **nova experiência** neste artigo.</span><span class="sxs-lookup"><span data-stu-id="73fd9-111">Information about the new experiences are marked **New experience** in this article.</span></span>

<span data-ttu-id="73fd9-112">Para usar a proteção contra ameaças da Microsoft, você precisa de uma única licença ou uma combinação de licenças.</span><span class="sxs-lookup"><span data-stu-id="73fd9-112">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span> <span data-ttu-id="73fd9-113">Essas combinações de licenças ou licenças dão acesso aos recursos de proteção contra ameaças da Microsoft sem custo adicional.</span><span class="sxs-lookup"><span data-stu-id="73fd9-113">These licenses or license combinations give you access to Microsoft Threat Protection features without additional cost.</span></span>

### <a name="single-license"></a><span data-ttu-id="73fd9-114">Licença única</span><span class="sxs-lookup"><span data-stu-id="73fd9-114">Single license</span></span>
<span data-ttu-id="73fd9-115">Você pode usar *uma* das seguintes licenças:</span><span class="sxs-lookup"><span data-stu-id="73fd9-115">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="73fd9-116">Microsoft 365 E5 ou a5</span><span class="sxs-lookup"><span data-stu-id="73fd9-116">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="73fd9-117">Segurança da Microsoft 365 E5 Security ou a5</span><span class="sxs-lookup"><span data-stu-id="73fd9-117">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="73fd9-118">Combinação de licenças</span><span class="sxs-lookup"><span data-stu-id="73fd9-118">Combination of licenses</span></span>
<span data-ttu-id="73fd9-119">Você também pode usar uma combinação de licenças para assinaturas E5 ou a5 para o Office 365, *Enterprise Mobility + Security (EMS)* e Windows.</span><span class="sxs-lookup"><span data-stu-id="73fd9-119">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="73fd9-120">A combinação de licenças deve incluir *todas* estas licenças:</span><span class="sxs-lookup"><span data-stu-id="73fd9-120">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="73fd9-121">Office 365 E5 ou a5</span><span class="sxs-lookup"><span data-stu-id="73fd9-121">Office 365 E5 or A5</span></span>
- <span data-ttu-id="73fd9-122">*Enterprise Mobility + Security (EMS)* E5 ou a5</span><span class="sxs-lookup"><span data-stu-id="73fd9-122">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="73fd9-123">Windows 10 Enterprise E5 ou a5</span><span class="sxs-lookup"><span data-stu-id="73fd9-123">Windows 10 Enterprise E5 or A5</span></span>

<span data-ttu-id="73fd9-124">Para obter mais informações, [consulte o Microsoft 365 Enterprise Service Plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="73fd9-124">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="73fd9-125">Ainda não tem licença?</span><span class="sxs-lookup"><span data-stu-id="73fd9-125">Don't have license yet?</span></span> [<span data-ttu-id="73fd9-126">Experimentar ou comprar uma assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="73fd9-126">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)


<span data-ttu-id="73fd9-127">**Nova experiência:** A partir de 12 de maio de 2020, os clientes receberão gradualmente alterações nessa experiência.</span><span class="sxs-lookup"><span data-stu-id="73fd9-127">**New experience:** Starting May 12, 2020, customers will gradually receive changes to this experience.</span></span> <span data-ttu-id="73fd9-128">Para aqueles com a nova experiência, a opção de ativar a proteção contra ameaças da Microsoft estará disponível para *todos* os clientes com qualquer uma das seguintes licenças:</span><span class="sxs-lookup"><span data-stu-id="73fd9-128">For those with the new experience, the option to turn on Microsoft Threat Protection will be available to *all* customers with any of the following licenses:</span></span>

- <span data-ttu-id="73fd9-129">Microsoft 365 E5 ou a5</span><span class="sxs-lookup"><span data-stu-id="73fd9-129">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="73fd9-130">Segurança da Microsoft 365 E5 Security ou a5</span><span class="sxs-lookup"><span data-stu-id="73fd9-130">Microsoft 365 E5 Security or A5 Security</span></span>
- <span data-ttu-id="73fd9-131">Windows 10 Enterprise E5 ou a5</span><span class="sxs-lookup"><span data-stu-id="73fd9-131">Windows 10 Enterprise E5 or A5</span></span>
- <span data-ttu-id="73fd9-132">Enterprise Mobility + Security (EMS) E5 ou a5</span><span class="sxs-lookup"><span data-stu-id="73fd9-132">Enterprise Mobility + Security (EMS) E5 or A5</span></span> 
- <span data-ttu-id="73fd9-133">Office 365 E5 ou a5</span><span class="sxs-lookup"><span data-stu-id="73fd9-133">Office 365 E5 or A5</span></span>
- <span data-ttu-id="73fd9-134">Proteção avançada contra ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="73fd9-134">Microsoft Defender Advanced Threat Protection</span></span> 
- <span data-ttu-id="73fd9-135">Proteção Avançada contra Ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="73fd9-135">Azure Advanced Threat Protection</span></span> 
- <span data-ttu-id="73fd9-136">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="73fd9-136">Microsoft Cloud App Security</span></span> 
- <span data-ttu-id="73fd9-137">Proteção contra Ameaças do Office 365 Advanced (Plano 2)</span><span class="sxs-lookup"><span data-stu-id="73fd9-137">Office 365 Advanced Threat Protection (Plan 2)</span></span> 

### <a name="check-your-existing--licenses"></a><span data-ttu-id="73fd9-138">Verificar suas licenças existentes</span><span class="sxs-lookup"><span data-stu-id="73fd9-138">Check your existing  licenses</span></span>
<span data-ttu-id="73fd9-139">Vá para o centro de administração do Microsoft 365 ([admin.Microsoft.com](https://admin.microsoft.com/)) para exibir suas licenças existentes.</span><span class="sxs-lookup"><span data-stu-id="73fd9-139">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="73fd9-140">No Centro de administração, acesse **Cobrança** > **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="73fd9-140">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="73fd9-141">Você precisa ser atribuído à função de **administrador de cobrança** ou **leitor global** [no Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para poder ver as informações de licença.</span><span class="sxs-lookup"><span data-stu-id="73fd9-141">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="73fd9-142">Se tiver problemas de acesso, entre em contato com um administrador global.</span><span class="sxs-lookup"><span data-stu-id="73fd9-142">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="73fd9-143">Requisitos de navegador</span><span class="sxs-lookup"><span data-stu-id="73fd9-143">Browser requirements</span></span>
<span data-ttu-id="73fd9-144">Acessar a proteção contra ameaças da Microsoft na central de segurança do Microsoft 365 usando o Microsoft Edge, o Internet Explorer 11 ou qualquer navegador da Web compatível com HTML 5.</span><span class="sxs-lookup"><span data-stu-id="73fd9-144">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="us-gcc-and-gcc-high-availability"></a><span data-ttu-id="73fd9-145">Alta disponibilidade dos EUA e GCC</span><span class="sxs-lookup"><span data-stu-id="73fd9-145">US GCC and GCC High availability</span></span>
<span data-ttu-id="73fd9-146">Atualmente, a proteção contra ameaças da Microsoft não está disponível para clientes da nuvem da Comunidade do governo dos EUA (GCC) e a nuvem de comunidade do governo (GCC High).</span><span class="sxs-lookup"><span data-stu-id="73fd9-146">Currently, Microsoft Threat Protection is not available to US Government Community Cloud (GCC) and Government Community Cloud High (GCC High) customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="73fd9-147">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="73fd9-147">Related topics</span></span>
- [<span data-ttu-id="73fd9-148">Visão geral da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="73fd9-148">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="73fd9-149">Habilitar a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="73fd9-149">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
