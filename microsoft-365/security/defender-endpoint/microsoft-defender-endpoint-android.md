---
title: Microsoft Defender ATP para Android
ms.reviewer: ''
description: Descreve como instalar e usar o Microsoft Defender ATP para Android
keywords: microsoft, defender, atp, android, installation, deploy, uninstallation, intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e2432dc4aa2c67fadc9112512a080f24c0064df4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187608"
---
# <a name="microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="5aba2-104">Microsoft Defender para Ponto de Extremidade para Android</span><span class="sxs-lookup"><span data-stu-id="5aba2-104">Microsoft Defender for Endpoint for Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5aba2-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="5aba2-105">**Applies to:**</span></span>
- [<span data-ttu-id="5aba2-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5aba2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5aba2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5aba2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5aba2-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="5aba2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="5aba2-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="5aba2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="5aba2-110">Este tópico descreve como instalar, configurar, atualizar e usar o Defender para Ponto de Extremidade para Android.</span><span class="sxs-lookup"><span data-stu-id="5aba2-110">This topic describes how to install, configure, update, and use Defender for Endpoint for Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="5aba2-111">A execução de outros produtos de proteção de ponto de extremidade de terceiros juntamente com o Defender for Endpoint para Android provavelmente causará problemas de desempenho e erros imprevisíveis do sistema.</span><span class="sxs-lookup"><span data-stu-id="5aba2-111">Running other third-party endpoint protection products alongside Defender for Endpoint for Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="5aba2-112">Como instalar o Microsoft Defender para Ponto de Extremidade para Android</span><span class="sxs-lookup"><span data-stu-id="5aba2-112">How to install Microsoft Defender for Endpoint for Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="5aba2-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="5aba2-113">Prerequisites</span></span>

-   <span data-ttu-id="5aba2-114">**Para usuários finais**</span><span class="sxs-lookup"><span data-stu-id="5aba2-114">**For end users**</span></span>

    -   <span data-ttu-id="5aba2-115">Licença do Microsoft Defender para Ponto de Extremidade atribuída ao(s) usuário(s) final do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5aba2-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="5aba2-116">Consulte [Requisitos de licenciamento](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements) do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="5aba2-116">See [Microsoft Defender for Endpoint licensing requirements](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="5aba2-117">O aplicativo do Portal da Empresa do Intune pode ser baixado no [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e está disponível no dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="5aba2-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="5aba2-118">Além disso, os dispositivos podem [ser](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) inscritos por meio do aplicativo Portal da Empresa do Intune para impor políticas de conformidade de dispositivos do Intune.</span><span class="sxs-lookup"><span data-stu-id="5aba2-118">Additionally, device(s) can be [enrolled](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="5aba2-119">Isso exige que o usuário final seja atribuído a uma licença do Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="5aba2-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="5aba2-120">Para obter mais informações sobre como atribuir licenças, consulte [Atribuir licenças aos usuários](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="5aba2-120">For more information on how to assign licenses, see [Assign licenses to users](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="5aba2-121">**Para administradores**</span><span class="sxs-lookup"><span data-stu-id="5aba2-121">**For Administrators**</span></span>

    -   <span data-ttu-id="5aba2-122">Acesso ao portal do Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="5aba2-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="5aba2-123">O Microsoft Intune é a única solução MDM (Gerenciamento de Dispositivo Móvel) com suporte para implantar o Microsoft Defender para Ponto de Extremidade para Android.</span><span class="sxs-lookup"><span data-stu-id="5aba2-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint for Android.</span></span> <span data-ttu-id="5aba2-124">Atualmente, apenas dispositivos inscritos têm suporte para impor o Defender for Endpoint para políticas de conformidade de dispositivos android no Intune.</span><span class="sxs-lookup"><span data-stu-id="5aba2-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint for Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="5aba2-125">Acesse [o Centro de administração do Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431), para implantar o aplicativo em grupos de usuários inscritos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5aba2-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>

### <a name="system-requirements"></a><span data-ttu-id="5aba2-126">Requisitos do sistema</span><span class="sxs-lookup"><span data-stu-id="5aba2-126">System Requirements</span></span>

-   <span data-ttu-id="5aba2-127">Dispositivos Android executando o Android 6.0 e superior.</span><span class="sxs-lookup"><span data-stu-id="5aba2-127">Android devices running Android 6.0 and above.</span></span>
-   <span data-ttu-id="5aba2-128">O aplicativo do Portal da Empresa do Intune é baixado do [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e instalado.</span><span class="sxs-lookup"><span data-stu-id="5aba2-128">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="5aba2-129">O registro de dispositivo é necessário para que as políticas de conformidade do dispositivo Intune sejam impostas.</span><span class="sxs-lookup"><span data-stu-id="5aba2-129">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="5aba2-130">Instruções de instalação</span><span class="sxs-lookup"><span data-stu-id="5aba2-130">Installation instructions</span></span>

<span data-ttu-id="5aba2-131">O Microsoft Defender para Ponto de Extremidade para Android oferece suporte à instalação em ambos os modos de dispositivos inscritos - os modos herdados Administrador de Dispositivos e Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5aba2-131">Microsoft Defender for Endpoint for Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="5aba2-132">**Atualmente, dispositivos de propriedade pessoal com perfil de trabalho e inscrições de dispositivos de usuário totalmente gerenciados de propriedade corporativa são suportados no Android Enterprise. O suporte para outros modos Android Enterprise será anunciado quando estiver pronto.**</span><span class="sxs-lookup"><span data-stu-id="5aba2-132">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrolments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="5aba2-133">A implantação do Microsoft Defender para Ponto de Extremidade para Android é via Microsoft Intune (MDM).</span><span class="sxs-lookup"><span data-stu-id="5aba2-133">Deployment of Microsoft Defender for Endpoint for Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="5aba2-134">Para obter mais informações, [consulte Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune](android-intune.md).</span><span class="sxs-lookup"><span data-stu-id="5aba2-134">For more information, see [Deploy Microsoft Defender for Endpoint for Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="5aba2-135">**O Microsoft Defender para Ponto de Extremidade para Android está disponível no [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) agora.**</span><span class="sxs-lookup"><span data-stu-id="5aba2-135">**Microsoft Defender for Endpoint for Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="5aba2-136">Você pode se conectar ao Google Play do Intune para implantar o microsoft Defender para aplicativo de ponto de extremidade, em modos de entrolamento do Administrador de Dispositivos e Android Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5aba2-136">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-android"></a><span data-ttu-id="5aba2-137">Como configurar o Microsoft Defender para Ponto de Extremidade para Android</span><span class="sxs-lookup"><span data-stu-id="5aba2-137">How to Configure Microsoft Defender for Endpoint for Android</span></span>

<span data-ttu-id="5aba2-138">As diretrizes sobre como configurar o Microsoft Defender para Recursos do Ponto de Extremidade para Android estão disponíveis em Configurar o Microsoft Defender para Ponto de Extremidade [para recursos android.](android-configure.md)</span><span class="sxs-lookup"><span data-stu-id="5aba2-138">Guidance on how to configure Microsoft Defender for Endpoint for Android features is available in [Configure Microsoft Defender for Endpoint for Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="5aba2-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5aba2-139">Related topics</span></span>
- [<span data-ttu-id="5aba2-140">Implantar o Microsoft Defender para o Ponto de Extremidade com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5aba2-140">Deploy Microsoft Defender for Endpoint for with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="5aba2-141">Configurar o Microsoft Defender para o Ponto de Extremidade para recursos android</span><span class="sxs-lookup"><span data-stu-id="5aba2-141">Configure Microsoft Defender for Endpoint for Android features</span></span>](android-configure.md)

