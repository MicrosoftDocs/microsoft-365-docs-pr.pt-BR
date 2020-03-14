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
ms.openlocfilehash: 2b653575e9e79ffe3448f622ca5be2cef37999dd
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633949"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="7ad30-104">Pré-requisitos da proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7ad30-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="7ad30-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="7ad30-105">**Applies to:**</span></span>
- <span data-ttu-id="7ad30-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7ad30-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="7ad30-107">Saiba mais sobre os requisitos de licenciamento, hardware e software e outras definições de configuração para provisionar e usar a proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ad30-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="7ad30-108">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="7ad30-108">Licensing requirements</span></span>
<span data-ttu-id="7ad30-109">Para usar a proteção contra ameaças da Microsoft, você precisa de *uma* das seguintes licenças ou combinações de licenças:</span><span class="sxs-lookup"><span data-stu-id="7ad30-109">To use Microsoft Threat Protection, you need *one* of the following licenses or combination of licenses:</span></span>

- <span data-ttu-id="7ad30-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="7ad30-110">Microsoft 365 E5</span></span>
- <span data-ttu-id="7ad30-111">Segurança do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="7ad30-111">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="7ad30-112">Office 365 E5 e "Enterprise Mobility + Security E5 (EMS E5)" e Windows e5</span><span class="sxs-lookup"><span data-stu-id="7ad30-112">Office 365 E5 and "Enterprise Mobility + Security E5 (EMS E5)" and Windows E5</span></span>
- <span data-ttu-id="7ad30-113">Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="7ad30-113">Microsoft 365 A5</span></span>

<span data-ttu-id="7ad30-114">Para obter mais informações, [consulte o Microsoft 365 Enterprise Service Plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="7ad30-114">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="7ad30-115">Ainda não tem licença?</span><span class="sxs-lookup"><span data-stu-id="7ad30-115">Don't have license yet?</span></span> [<span data-ttu-id="7ad30-116">Experimentar ou comprar uma assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7ad30-116">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="7ad30-117">Verificar suas licenças existentes</span><span class="sxs-lookup"><span data-stu-id="7ad30-117">Check your existing  licenses</span></span>
<span data-ttu-id="7ad30-118">Vá para o centro de administração do Microsoft 365 ([admin.Microsoft.com](https://admin.microsoft.com/)) para exibir suas licenças existentes.</span><span class="sxs-lookup"><span data-stu-id="7ad30-118">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="7ad30-119">No Centro de administração, acesse **Cobrança** > **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="7ad30-119">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="7ad30-120">Você precisa ser atribuído à função de **administrador de cobrança** ou **leitor global** [no Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para poder ver as informações de licença.</span><span class="sxs-lookup"><span data-stu-id="7ad30-120">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="7ad30-121">Se tiver problemas de acesso, entre em contato com um administrador global.</span><span class="sxs-lookup"><span data-stu-id="7ad30-121">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="7ad30-122">Requisitos de navegador</span><span class="sxs-lookup"><span data-stu-id="7ad30-122">Browser requirements</span></span>
<span data-ttu-id="7ad30-123">Acessar a proteção contra ameaças da Microsoft na central de segurança do Microsoft 365 usando o Microsoft Edge, o Internet Explorer 11 ou qualquer navegador da Web compatível com HTML 5.</span><span class="sxs-lookup"><span data-stu-id="7ad30-123">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a><span data-ttu-id="7ad30-124">Proteção contra ameaças da Microsoft para a nuvem da Comunidade do governo dos EUA e clientes com a nuvem de comunidade dos EUA (GCC High)</span><span class="sxs-lookup"><span data-stu-id="7ad30-124">Microsoft Threat Protection for US Government Community Cloud and US Government Community Cloud High (GCC High) customers</span></span>
<span data-ttu-id="7ad30-125">Atualmente, a proteção contra ameaças da Microsoft não está disponível para os clientes GCC e GCC mais altos.</span><span class="sxs-lookup"><span data-stu-id="7ad30-125">Currently, Microsoft Threat Protection is not available to US GCC and GCC High customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="7ad30-126">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="7ad30-126">Related topics</span></span>
- [<span data-ttu-id="7ad30-127">Visão geral da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7ad30-127">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="7ad30-128">Habilitar a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="7ad30-128">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
