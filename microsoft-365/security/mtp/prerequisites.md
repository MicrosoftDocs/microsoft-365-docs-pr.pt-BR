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
ms.openlocfilehash: 12e68cd8fcd7c784b1d0b4c70c5c25370cbbb409
ms.sourcegitcommit: 997f6227f33c3683ade9672e881d09216df22ee9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2020
ms.locfileid: "44015997"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="753ff-104">Pré-requisitos da proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="753ff-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="753ff-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="753ff-105">**Applies to:**</span></span>
- <span data-ttu-id="753ff-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="753ff-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="753ff-107">Saiba mais sobre os requisitos de licenciamento, hardware e software e outras definições de configuração para provisionar e usar a proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="753ff-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="753ff-108">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="753ff-108">Licensing requirements</span></span>

<span data-ttu-id="753ff-109">Para usar a proteção contra ameaças da Microsoft, você precisa de uma única licença ou uma combinação de licenças.</span><span class="sxs-lookup"><span data-stu-id="753ff-109">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span> <span data-ttu-id="753ff-110">Essas combinações de licenças ou licenças dão acesso aos recursos de proteção contra ameaças da Microsoft sem custo adicional.</span><span class="sxs-lookup"><span data-stu-id="753ff-110">These licenses or license combinations give you access to Microsoft Threat Protection features without additional cost.</span></span>

### <a name="single-license"></a><span data-ttu-id="753ff-111">Licença única</span><span class="sxs-lookup"><span data-stu-id="753ff-111">Single license</span></span>
<span data-ttu-id="753ff-112">Você pode usar *uma* das seguintes licenças:</span><span class="sxs-lookup"><span data-stu-id="753ff-112">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="753ff-113">Microsoft 365 E5 ou a5</span><span class="sxs-lookup"><span data-stu-id="753ff-113">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="753ff-114">Segurança da Microsoft 365 E5 Security ou a5</span><span class="sxs-lookup"><span data-stu-id="753ff-114">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="753ff-115">Combinação de licenças</span><span class="sxs-lookup"><span data-stu-id="753ff-115">Combination of licenses</span></span>
<span data-ttu-id="753ff-116">Você também pode usar uma combinação de licenças para assinaturas E5 ou a5 para o Office 365, *Enterprise Mobility + Security (EMS)* e Windows.</span><span class="sxs-lookup"><span data-stu-id="753ff-116">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="753ff-117">A combinação de licenças deve incluir *todas* estas licenças:</span><span class="sxs-lookup"><span data-stu-id="753ff-117">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="753ff-118">Office 365 E5 ou a5</span><span class="sxs-lookup"><span data-stu-id="753ff-118">Office 365 E5 or A5</span></span>
- <span data-ttu-id="753ff-119">*Enterprise Mobility + Security (EMS)* E5 ou a5</span><span class="sxs-lookup"><span data-stu-id="753ff-119">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="753ff-120">Windows 10 Enterprise E5 ou a5</span><span class="sxs-lookup"><span data-stu-id="753ff-120">Windows 10 Enterprise E5 or A5</span></span>

<span data-ttu-id="753ff-121">Para obter mais informações, [consulte o Microsoft 365 Enterprise Service Plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="753ff-121">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="753ff-122">Ainda não tem licença?</span><span class="sxs-lookup"><span data-stu-id="753ff-122">Don't have license yet?</span></span> [<span data-ttu-id="753ff-123">Experimentar ou comprar uma assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="753ff-123">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="753ff-124">Verificar suas licenças existentes</span><span class="sxs-lookup"><span data-stu-id="753ff-124">Check your existing  licenses</span></span>
<span data-ttu-id="753ff-125">Vá para o centro de administração do Microsoft 365 ([admin.Microsoft.com](https://admin.microsoft.com/)) para exibir suas licenças existentes.</span><span class="sxs-lookup"><span data-stu-id="753ff-125">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="753ff-126">No Centro de administração, acesse **Cobrança** > **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="753ff-126">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="753ff-127">Você precisa ser atribuído à função de **administrador de cobrança** ou **leitor global** [no Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para poder ver as informações de licença.</span><span class="sxs-lookup"><span data-stu-id="753ff-127">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="753ff-128">Se tiver problemas de acesso, entre em contato com um administrador global.</span><span class="sxs-lookup"><span data-stu-id="753ff-128">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="753ff-129">Requisitos de navegador</span><span class="sxs-lookup"><span data-stu-id="753ff-129">Browser requirements</span></span>
<span data-ttu-id="753ff-130">Acessar a proteção contra ameaças da Microsoft na central de segurança do Microsoft 365 usando o Microsoft Edge, o Internet Explorer 11 ou qualquer navegador da Web compatível com HTML 5.</span><span class="sxs-lookup"><span data-stu-id="753ff-130">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a><span data-ttu-id="753ff-131">Proteção contra ameaças da Microsoft para a nuvem da Comunidade do governo dos EUA e clientes com a nuvem de comunidade dos EUA (GCC High)</span><span class="sxs-lookup"><span data-stu-id="753ff-131">Microsoft Threat Protection for US Government Community Cloud and US Government Community Cloud High (GCC High) customers</span></span>
<span data-ttu-id="753ff-132">Atualmente, a proteção contra ameaças da Microsoft não está disponível para os clientes GCC e GCC mais altos.</span><span class="sxs-lookup"><span data-stu-id="753ff-132">Currently, Microsoft Threat Protection is not available to US GCC and GCC High customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="753ff-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="753ff-133">Related topics</span></span>
- [<span data-ttu-id="753ff-134">Visão geral da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="753ff-134">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="753ff-135">Habilitar a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="753ff-135">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
