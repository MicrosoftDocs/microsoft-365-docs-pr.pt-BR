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
ms.openlocfilehash: ef26a2ebc25d7f55e7dc22347d85767dab970536
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42372049"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="5e6ba-104">Pré-requisitos da proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="5e6ba-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="5e6ba-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5e6ba-105">**Applies to:**</span></span>
- <span data-ttu-id="5e6ba-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="5e6ba-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="5e6ba-107">Saiba mais sobre os requisitos de licenciamento, hardware e software e outras definições de configuração para provisionar e usar a proteção contra ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5e6ba-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="5e6ba-108">Requisitos de licença</span><span class="sxs-lookup"><span data-stu-id="5e6ba-108">Licensing requirements</span></span>
<span data-ttu-id="5e6ba-109">Para usar a proteção contra ameaças da Microsoft, você precisa de *uma* das seguintes licenças ou combinações de licenças:</span><span class="sxs-lookup"><span data-stu-id="5e6ba-109">To use Microsoft Threat Protection, you need *one* of the following licenses or combination of licenses:</span></span>

- <span data-ttu-id="5e6ba-110">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="5e6ba-110">Microsoft 365 E5</span></span>
- <span data-ttu-id="5e6ba-111">Segurança do Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="5e6ba-111">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="5e6ba-112">Office 365 E5 e "Enterprise Mobility + Security E5 (EMS E5)" e Windows e5</span><span class="sxs-lookup"><span data-stu-id="5e6ba-112">Office 365 E5 and "Enterprise Mobility + Security E5 (EMS E5)" and Windows E5</span></span>
- <span data-ttu-id="5e6ba-113">Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="5e6ba-113">Microsoft 365 A5</span></span>
- <span data-ttu-id="5e6ba-114">Segurança 365 A5 da Microsoft</span><span class="sxs-lookup"><span data-stu-id="5e6ba-114">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="5e6ba-115">Office 365 a5 e "Enterprise Mobility + Security a5 (EMS a5)" e Windows a5</span><span class="sxs-lookup"><span data-stu-id="5e6ba-115">Office 365 A5 and "Enterprise Mobility + Security A5 (EMS A5)" and Windows A5</span></span>

<span data-ttu-id="5e6ba-116">Para obter mais informações, [consulte o Microsoft 365 Enterprise Service Plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="5e6ba-116">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="5e6ba-117">Ainda não tem licença?</span><span class="sxs-lookup"><span data-stu-id="5e6ba-117">Don't have license yet?</span></span> [<span data-ttu-id="5e6ba-118">Experimentar ou comprar uma assinatura do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5e6ba-118">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="5e6ba-119">Verificar suas licenças existentes</span><span class="sxs-lookup"><span data-stu-id="5e6ba-119">Check your existing  licenses</span></span>
<span data-ttu-id="5e6ba-120">Vá para o centro de administração do Microsoft 365 ([admin.Microsoft.com](https://admin.microsoft.com/)) para exibir suas licenças existentes.</span><span class="sxs-lookup"><span data-stu-id="5e6ba-120">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="5e6ba-121">No Centro de administração, acesse **Cobrança** > **Licenças**.</span><span class="sxs-lookup"><span data-stu-id="5e6ba-121">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="5e6ba-122">Você precisa ser atribuído à função de **administrador de cobrança** ou **leitor global** [no Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para poder ver as informações de licença.</span><span class="sxs-lookup"><span data-stu-id="5e6ba-122">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="5e6ba-123">Se tiver problemas de acesso, entre em contato com um administrador global.</span><span class="sxs-lookup"><span data-stu-id="5e6ba-123">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="5e6ba-124">Requisitos de navegador</span><span class="sxs-lookup"><span data-stu-id="5e6ba-124">Browser requirements</span></span>
<span data-ttu-id="5e6ba-125">Acessar a proteção contra ameaças da Microsoft na central de segurança do Microsoft 365 usando o Microsoft Edge, o Internet Explorer 11 ou qualquer navegador da Web compatível com HTML 5.</span><span class="sxs-lookup"><span data-stu-id="5e6ba-125">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5e6ba-126">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5e6ba-126">Related topics</span></span>
- [<span data-ttu-id="5e6ba-127">Visão geral da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="5e6ba-127">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="5e6ba-128">Habilitar a Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="5e6ba-128">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
