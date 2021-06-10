---
title: Serviço de localização do Windows 10
description: Como ter os Windows de localização atados para seus dispositivos
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 210356dd21b36efbb27d8faa4f8616145584159c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929455"
---
# <a name="windows-10-location-service"></a><span data-ttu-id="749b9-104">Serviço de localização do Windows 10</span><span class="sxs-lookup"><span data-stu-id="749b9-104">Windows 10 location service</span></span>

<span data-ttu-id="749b9-105">Os dispositivos Área de Trabalho Gerenciada da Microsoft são registrados usando o Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="749b9-105">Devices in Microsoft Managed Desktop are registered by using Windows Autopilot.</span></span> <span data-ttu-id="749b9-106">Esse processo nos permite gerenciá-los com Azure Active Directory e Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="749b9-106">This process lets us manage them with Azure Active Directory and Microsoft Intune.</span></span> <span data-ttu-id="749b9-107">Por padrão, o serviço de Windows 10 local é desabilitado quando um dispositivo está ativado pela primeira vez, a menos que esse recurso esteja habilitado nas configurações de Privacidade durante a "experiência fora da caixa".</span><span class="sxs-lookup"><span data-stu-id="749b9-107">By default, the Windows 10 location service is disabled when a device is turned on for the first time unless this feature is enabled in the Privacy settings during the "out of box experience."</span></span> <span data-ttu-id="749b9-108">Essas configurações ficam ocultas durante o registro do Piloto Automático no Área de Trabalho Gerenciada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="749b9-108">These settings are hidden during Autopilot enrollment in Microsoft Managed Desktop.</span></span> <span data-ttu-id="749b9-109">Para obter mais informações sobre como o Autopilot está definido, consulte Experiência de primeira executar com o Autopilot e a [Página de Status do Registro.](esp-first-run.md)</span><span class="sxs-lookup"><span data-stu-id="749b9-109">For more information about how Autopilot is set up, see [First-run experience with Autopilot and the Enrollment Status Page](esp-first-run.md).</span></span>

<span data-ttu-id="749b9-110">Por esse motivo, Área de Trabalho Gerenciada da Microsoft dispositivos não podem obter a localização do dispositivo, o que limita a funcionalidade de vários recursos Windows, como fusos horário.</span><span class="sxs-lookup"><span data-stu-id="749b9-110">For this reason, Microsoft Managed Desktop devices can't obtain their device location, which limits the functionality of several Windows features, such as time zones.</span></span> <span data-ttu-id="749b9-111">Para obter mais informações sobre o serviço Windows 10 local, [consulte Windows 10 local e privacidade.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)</span><span class="sxs-lookup"><span data-stu-id="749b9-111">For more information about the Windows 10 location service, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="749b9-112">Você não precisa usar o serviço de localização para participar do Área de Trabalho Gerenciada da Microsoft, mas a experiência do usuário será restrita.</span><span class="sxs-lookup"><span data-stu-id="749b9-112">You don't have to use the location service in order to participate in Microsoft Managed Desktop, but the user experience will be restricted.</span></span> <span data-ttu-id="749b9-113">Por exemplo, os dispositivos não poderão determinar automaticamente o fuso horário em que estão quando seus usuários trabalham em um fuso horário diferente.</span><span class="sxs-lookup"><span data-stu-id="749b9-113">For example, devices won't be able to automatically determine the time zone they're in when your users work in a different time zone.</span></span>

## <a name="enable-the-location-service"></a><span data-ttu-id="749b9-114">Habilitar o serviço de localização</span><span class="sxs-lookup"><span data-stu-id="749b9-114">Enable the location service</span></span>

<span data-ttu-id="749b9-115">Você pode optar por usar o serviço de localização ao registrar dispositivos no serviço Área de Trabalho Gerenciada da Microsoft ou ativar ou desativar o serviço após o registro.</span><span class="sxs-lookup"><span data-stu-id="749b9-115">You can either opt in to using the location service when you enroll devices into the Microsoft Managed Desktop service or you can turn the service on or off after enrollment.</span></span>

### <a name="opt-in-during-enrollment"></a><span data-ttu-id="749b9-116">Optar durante o registro</span><span class="sxs-lookup"><span data-stu-id="749b9-116">Opt in during enrollment</span></span>

<span data-ttu-id="749b9-117">Você pode ter o serviço Área de Trabalho Gerenciada da Microsoft habilitar o serviço de localização.</span><span class="sxs-lookup"><span data-stu-id="749b9-117">You can have the Microsoft Managed Desktop service enable the location service.</span></span> <span data-ttu-id="749b9-118">Durante a sequência de inscrição, você será solicitado a selecionar se deseja permitir que o serviço de Windows 10 local seja habilitado em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="749b9-118">During the enrollment sequence, you'll be asked to select whether you want to allow the Windows 10 location service to be enabled on devices.</span></span>

### <a name="control-the-location-service-after-enrollment"></a><span data-ttu-id="749b9-119">Controlar o serviço de localização após o registro</span><span class="sxs-lookup"><span data-stu-id="749b9-119">Control the location service after enrollment</span></span>

<span data-ttu-id="749b9-120">Você pode ter o serviço de localização ligado (ou desligado) [a](../working-with-managed-desktop/admin-support.md) qualquer momento enviando uma solicitação de suporte por meio do portal [de administração](access-admin-portal.md).</span><span class="sxs-lookup"><span data-stu-id="749b9-120">You can have the location service turned on (or off) at any time by submitting a [support request](../working-with-managed-desktop/admin-support.md) through the [Admin portal](access-admin-portal.md).</span></span>

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a><span data-ttu-id="749b9-121">Como Área de Trabalho Gerenciada da Microsoft configura o serviço de Windows 10 local</span><span class="sxs-lookup"><span data-stu-id="749b9-121">How Microsoft Managed Desktop configures the Windows 10 location service</span></span>

<span data-ttu-id="749b9-122">Se você optar por usar o serviço de localização, usamos as configurações mínimas necessárias sem afetar a privacidade dos usuários.</span><span class="sxs-lookup"><span data-stu-id="749b9-122">If you opt in to using the location service, we use the minimum settings necessary without affecting users' privacy.</span></span> <span data-ttu-id="749b9-123">Para obter mais informações, [consulte Windows 10 local e privacidade.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)</span><span class="sxs-lookup"><span data-stu-id="749b9-123">For more information, see [Windows 10 location service and privacy](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).</span></span>

<span data-ttu-id="749b9-124">Área de Trabalho Gerenciada da Microsoft habilita a **configuração de** privacidade local **em Windows para** Permitir o acesso ao local **neste dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="749b9-124">Microsoft Managed Desktop enables the **Location privacy** setting in **Windows settings** to **Allow access to location on this device**.</span></span> <span data-ttu-id="749b9-125">A interface do usuário tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="749b9-125">The user interface looks like this:</span></span>

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Configurações de local em Windows configurações":::

> [!NOTE]
> <span data-ttu-id="749b9-127">Se você optar por usar o serviço de localização, isso se aplica somente ao sistema operacional Windows sistema operacional em si.</span><span class="sxs-lookup"><span data-stu-id="749b9-127">If you opt in to using the location service, this applies only to the Windows operating system itself.</span></span> <span data-ttu-id="749b9-128">Os aplicativos não têm permissão para usar serviços de localização.</span><span class="sxs-lookup"><span data-stu-id="749b9-128">Apps are not allowed to use location services.</span></span> <span data-ttu-id="749b9-129">Cada usuário pode escolher se permite que os aplicativos acessem sua localização.</span><span class="sxs-lookup"><span data-stu-id="749b9-129">Each user can choose whether to allow apps to access their location.</span></span>