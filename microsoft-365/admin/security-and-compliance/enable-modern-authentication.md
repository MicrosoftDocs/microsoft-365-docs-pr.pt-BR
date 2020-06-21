---
title: Habilitar a Autenticação Moderna do Office 2013 em dispositivos Windows.
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Saiba como definir as chaves do registro para habilitar a autenticação moderna para dispositivos que têm o Microsoft Office 2013 instalado.
ms.openlocfilehash: 8edcedefc04d5018b8b61022c26cbe027f7c24a9
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779960"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="c826f-103">Habilitar a Autenticação Moderna do Office 2013 em dispositivos Windows.</span><span class="sxs-lookup"><span data-stu-id="c826f-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="c826f-104">Para habilitar a autenticação moderna para qualquer dispositivo com Windows com o Office 2013 instalado, é necessário configurar chaves do Registro específicas.</span><span class="sxs-lookup"><span data-stu-id="c826f-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="c826f-105">Habilitar a autenticação moderna para clientes do Office 2013</span><span class="sxs-lookup"><span data-stu-id="c826f-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="c826f-106">A autenticação moderna já está habilitada para clientes do Office 2016, você não precisa definir chaves do Registro para Office 2016.</span><span class="sxs-lookup"><span data-stu-id="c826f-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="c826f-107">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys.</span><span class="sxs-lookup"><span data-stu-id="c826f-107">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys.</span></span> <span data-ttu-id="c826f-108">The keys have to be set on each device that you want to enable for modern authentication:</span><span class="sxs-lookup"><span data-stu-id="c826f-108">The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="c826f-109">**Chave do Registro**</span><span class="sxs-lookup"><span data-stu-id="c826f-109">**Registry key**</span></span>|<span data-ttu-id="c826f-110">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c826f-110">**Type**</span></span>|<span data-ttu-id="c826f-111">**Valor**</span><span class="sxs-lookup"><span data-stu-id="c826f-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="c826f-112">Hkcu\software\microsoft\office\15.0 \common\identity\enableadal com</span><span class="sxs-lookup"><span data-stu-id="c826f-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="c826f-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c826f-113">REG_DWORD</span></span>  |<span data-ttu-id="c826f-114">1 </span><span class="sxs-lookup"><span data-stu-id="c826f-114">1</span></span>  |
|<span data-ttu-id="c826f-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="c826f-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="c826f-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c826f-116">REG_DWORD</span></span> |<span data-ttu-id="c826f-117">1 </span><span class="sxs-lookup"><span data-stu-id="c826f-117">1</span></span> |
   
<span data-ttu-id="c826f-118">Depois de definir as chaves do registro, você pode definir os aplicativos do Office 2013 para usar a [autenticação multifator (MFA)](set-up-multi-factor-authentication.md) com o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c826f-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Microsoft 365.</span></span> 
  
<span data-ttu-id="c826f-119">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect.</span><span class="sxs-lookup"><span data-stu-id="c826f-119">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect.</span></span> <span data-ttu-id="c826f-120">Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span><span class="sxs-lookup"><span data-stu-id="c826f-120">Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="c826f-121">Desabilitar a autenticação moderna nos dispositivos</span><span class="sxs-lookup"><span data-stu-id="c826f-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="c826f-122">Para desabilitar a autenticação moderna em um dispositivo, defina as seguintes chaves do Registro no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="c826f-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="c826f-123">**Chave do Registro**</span><span class="sxs-lookup"><span data-stu-id="c826f-123">**Registry key**</span></span>|<span data-ttu-id="c826f-124">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c826f-124">**Type**</span></span>|<span data-ttu-id="c826f-125">**Valor**</span><span class="sxs-lookup"><span data-stu-id="c826f-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="c826f-126">Hkcu\software\microsoft\office\15.0 \common\identity\enableadal com</span><span class="sxs-lookup"><span data-stu-id="c826f-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="c826f-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="c826f-127">REG_DWORD</span></span>|<span data-ttu-id="c826f-128">,0</span><span class="sxs-lookup"><span data-stu-id="c826f-128">0</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="c826f-129">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="c826f-129">Related articles</span></span>
[<span data-ttu-id="c826f-130">Entrar no Office 2013 com um segundo método de verificação</span><span class="sxs-lookup"><span data-stu-id="c826f-130">Sign in to Office 2013 with a second verification method</span></span>](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

  

