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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Saiba como definir as chaves do registro para habilitar a autenticação moderna para dispositivos que têm o Microsoft Office 2013 instalado.
ms.openlocfilehash: f1264affa5be93b19e564a0edea00bfb78f452f1
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42237830"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a><span data-ttu-id="06205-103">Habilitar a Autenticação Moderna do Office 2013 em dispositivos Windows.</span><span class="sxs-lookup"><span data-stu-id="06205-103">Enable Modern Authentication for Office 2013 on Windows devices</span></span>

<span data-ttu-id="06205-104">Para habilitar a autenticação moderna para qualquer dispositivo com Windows com o Office 2013 instalado, é necessário configurar chaves do Registro específicas.</span><span class="sxs-lookup"><span data-stu-id="06205-104">To enable modern authentication for any Windows devices that have Office 2013 installed, you need to set specific registry keys.</span></span>
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a><span data-ttu-id="06205-105">Habilitar a autenticação moderna para clientes do Office 2013</span><span class="sxs-lookup"><span data-stu-id="06205-105">Enable modern authentication for Office 2013 clients</span></span>

> [!NOTE]
> <span data-ttu-id="06205-106">A autenticação moderna já está habilitada para clientes do Office 2016, você não precisa definir chaves do Registro para Office 2016.</span><span class="sxs-lookup"><span data-stu-id="06205-106">Modern authentication is already enabled for Office 2016 clients, you do not need to set registry keys for Office 2016.</span></span> 
  
<span data-ttu-id="06205-p101">Para habilitar a autenticação moderna para os dispositivos com Windows (por exemplo em laptops e tablets), que têm o Microsoft Office 2013 instalado, você precisa definir as seguintes chaves do Registro. As teclas precisam ser definidas em cada dispositivo que você deseja habilitar para autenticação moderna:</span><span class="sxs-lookup"><span data-stu-id="06205-p101">To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:</span></span>
  
|<span data-ttu-id="06205-109">**Chave do Registro**</span><span class="sxs-lookup"><span data-stu-id="06205-109">**Registry key**</span></span>|<span data-ttu-id="06205-110">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="06205-110">**Type**</span></span>|<span data-ttu-id="06205-111">**Valor**</span><span class="sxs-lookup"><span data-stu-id="06205-111">**Value**</span></span> |
|:-------|:------:|--------:|
|<span data-ttu-id="06205-112">Hkcu\software\microsoft\office\15.0 \common\identity\enableadal com</span><span class="sxs-lookup"><span data-stu-id="06205-112">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  |<span data-ttu-id="06205-113">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="06205-113">REG_DWORD</span></span>  |<span data-ttu-id="06205-114">1</span><span class="sxs-lookup"><span data-stu-id="06205-114">1</span></span>  |
|<span data-ttu-id="06205-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="06205-115">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span> |<span data-ttu-id="06205-116">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="06205-116">REG_DWORD</span></span> |<span data-ttu-id="06205-117">1</span><span class="sxs-lookup"><span data-stu-id="06205-117">1</span></span> |
   
<span data-ttu-id="06205-118">Depois que você tiver configurado as chaves do Registro, será possível configurar aplicativos de dispositivos do Office 2013 para usar [autenticação multifator (MFA)](set-up-multi-factor-authentication.md) com o Office 365</span><span class="sxs-lookup"><span data-stu-id="06205-118">Once you have set the registry keys, you can set Office 2013 devices apps to use [multifactor authentication (MFA)](set-up-multi-factor-authentication.md) with Office 365</span></span> 
  
<span data-ttu-id="06205-p102">Se você estiver conectado no momento a qualquer um dos aplicativos cliente, você precisará sair e entrar novamente para que a alteração entre em vigor. Caso contrário, o MRU e as configurações de roaming estarão indisponíveis até que a identidade de ADAL seja estabelecida.</span><span class="sxs-lookup"><span data-stu-id="06205-p102">If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.</span></span>
  
## <a name="disable-modern-authentication-on-devices"></a><span data-ttu-id="06205-121">Desabilitar a autenticação moderna nos dispositivos</span><span class="sxs-lookup"><span data-stu-id="06205-121">Disable modern authentication on devices</span></span>

<span data-ttu-id="06205-122">Para desabilitar a autenticação moderna em um dispositivo, defina as seguintes chaves do Registro no dispositivo:</span><span class="sxs-lookup"><span data-stu-id="06205-122">To disable modern authentication on a device, set the following registry keys on the device:</span></span>
  
|<span data-ttu-id="06205-123">**Chave do Registro**</span><span class="sxs-lookup"><span data-stu-id="06205-123">**Registry key**</span></span>|<span data-ttu-id="06205-124">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="06205-124">**Type**</span></span>|<span data-ttu-id="06205-125">**Valor**</span><span class="sxs-lookup"><span data-stu-id="06205-125">**Value**</span></span>|
|:-------|:------:|--------:|
|<span data-ttu-id="06205-126">Hkcu\software\microsoft\office\15.0 \common\identity\enableadal com</span><span class="sxs-lookup"><span data-stu-id="06205-126">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span> |<span data-ttu-id="06205-127">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="06205-127">REG_DWORD</span></span>|<span data-ttu-id="06205-128">,0</span><span class="sxs-lookup"><span data-stu-id="06205-128">0</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="06205-129">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="06205-129">Related articles</span></span>
[<span data-ttu-id="06205-130">Entrar no Office 2013 com um segundo método de verificação</span><span class="sxs-lookup"><span data-stu-id="06205-130">Sign in to Office 2013 with a second verification method</span></span>](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx)

  

