---
title: Microsoft Defender para Ponto de Extremidade para Android
ms.reviewer: ''
description: Descreve como instalar e usar o Microsoft Defender para Ponto de Extremidade no Android
keywords: microsoft, defender, Microsoft Defender for Endpoint, android, installation, deploy, uninstallation, intune
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
ms.openlocfilehash: ceccd9e3c8a8137f672e7be519675034a84c7881
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055107"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="05167-104">Microsoft Defender para Ponto de Extremidade para Android</span><span class="sxs-lookup"><span data-stu-id="05167-104">Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="05167-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="05167-105">**Applies to:**</span></span>
- [<span data-ttu-id="05167-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="05167-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="05167-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="05167-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="05167-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="05167-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="05167-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="05167-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="05167-110">Este tópico descreve como instalar, configurar, atualizar e usar o Defender para Ponto de Extremidade no Android.</span><span class="sxs-lookup"><span data-stu-id="05167-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Android.</span></span>

> [!CAUTION]
> <span data-ttu-id="05167-111">A execução de outros produtos de proteção de ponto de extremidade de terceiros juntamente com o Defender for Endpoint no Android provavelmente causará problemas de desempenho e erros imprevisíveis do sistema.</span><span class="sxs-lookup"><span data-stu-id="05167-111">Running other third-party endpoint protection products alongside Defender for Endpoint on Android is likely to cause performance problems and unpredictable system errors.</span></span>


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="05167-112">Como instalar o Microsoft Defender para Ponto de Extremidade no Android</span><span class="sxs-lookup"><span data-stu-id="05167-112">How to install Microsoft Defender for Endpoint on Android</span></span>

### <a name="prerequisites"></a><span data-ttu-id="05167-113">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="05167-113">Prerequisites</span></span>

-   <span data-ttu-id="05167-114">**Para usuários finais**</span><span class="sxs-lookup"><span data-stu-id="05167-114">**For end users**</span></span>

    -   <span data-ttu-id="05167-115">Licença do Microsoft Defender para Ponto de Extremidade atribuída ao(s) usuário(s) final do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05167-115">Microsoft Defender for Endpoint license assigned to the end user(s) of the app.</span></span> <span data-ttu-id="05167-116">Consulte [Requisitos de licenciamento](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements) do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="05167-116">See [Microsoft Defender for Endpoint licensing requirements](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)</span></span>

    -   <span data-ttu-id="05167-117">Portal da Empresa do Intune aplicativo pode ser baixado no [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e está disponível no dispositivo Android.</span><span class="sxs-lookup"><span data-stu-id="05167-117">Intune Company Portal app can be downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and is available on the Android device.</span></span>

        -   <span data-ttu-id="05167-118">Além disso, os dispositivos podem [ser](/mem/intune/user-help/enroll-device-android-company-portal) inscritos por meio do aplicativo Portal da Empresa do Intune para impor políticas de conformidade de dispositivos do Intune.</span><span class="sxs-lookup"><span data-stu-id="05167-118">Additionally, device(s) can be [enrolled](/mem/intune/user-help/enroll-device-android-company-portal) via the Intune Company Portal app to enforce Intune device compliance policies.</span></span> <span data-ttu-id="05167-119">Isso exige que o usuário final seja atribuído a uma Microsoft Intune de usuário.</span><span class="sxs-lookup"><span data-stu-id="05167-119">This requires the end user to be assigned a Microsoft Intune license.</span></span>

    -   <span data-ttu-id="05167-120">Para obter mais informações sobre como atribuir licenças, consulte [Atribuir licenças aos usuários](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="05167-120">For more information on how to assign licenses, see [Assign licenses to users](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>
        

-   <span data-ttu-id="05167-121">**Para administradores**</span><span class="sxs-lookup"><span data-stu-id="05167-121">**For Administrators**</span></span>

    -   <span data-ttu-id="05167-122">Acesso ao portal Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="05167-122">Access to the Microsoft Defender Security Center portal.</span></span>

        > [!NOTE]
        > <span data-ttu-id="05167-123">Microsoft Intune é a única solução MDM (Gerenciamento de Dispositivo Móvel) com suporte para implantar o Microsoft Defender para Ponto de Extremidade no Android.</span><span class="sxs-lookup"><span data-stu-id="05167-123">Microsoft Intune is the only supported Mobile Device Management (MDM) solution for deploying Microsoft Defender for Endpoint on Android.</span></span> <span data-ttu-id="05167-124">Atualmente, apenas dispositivos inscritos têm suporte para impor o Defender for Endpoint em políticas de conformidade de dispositivos relacionados ao Android no Intune.</span><span class="sxs-lookup"><span data-stu-id="05167-124">Currently only enrolled devices are supported for enforcing Defender for Endpoint on Android related device compliance policies in Intune.</span></span> 

    -   <span data-ttu-id="05167-125">Acesse [Microsoft Endpoint Manager centro de](https://go.microsoft.com/fwlink/?linkid=2109431)administração , para implantar o aplicativo em grupos de usuários inscritos em sua organização.</span><span class="sxs-lookup"><span data-stu-id="05167-125">Access [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), to deploy the app to enrolled user groups in your organization.</span></span>
        
### <a name="network-requirements"></a><span data-ttu-id="05167-126">Requisitos de rede</span><span class="sxs-lookup"><span data-stu-id="05167-126">Network Requirements</span></span>

- <span data-ttu-id="05167-127">Para que o Microsoft Defender para Ponto de Extremidade no Android funcione quando conectado a uma rede, o firewall/proxy precisará ser configurado para habilitar o acesso ao [Microsoft Defender para URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)de serviço de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="05167-127">For Microsoft Defender for Endpoint on Android to function when connected to a network the firewall/proxy will need to be configured to [enable access to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="05167-128">Requisitos do sistema</span><span class="sxs-lookup"><span data-stu-id="05167-128">System Requirements</span></span>

-   <span data-ttu-id="05167-129">Telefones celulares executando o Android 6.0 e superior.</span><span class="sxs-lookup"><span data-stu-id="05167-129">Mobile phones running Android 6.0 and above.</span></span> <span data-ttu-id="05167-130">**Tablets e outros dispositivos móveis que executam o Android não têm suporte no momento.**</span><span class="sxs-lookup"><span data-stu-id="05167-130">**Tablets and other mobile devices running Android are not currently supported.**</span></span> 

-   <span data-ttu-id="05167-131">Portal da Empresa do Intune aplicativo é baixado do [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) e instalado.</span><span class="sxs-lookup"><span data-stu-id="05167-131">Intune Company Portal app is downloaded from [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) and installed.</span></span> <span data-ttu-id="05167-132">O registro de dispositivo é necessário para que as políticas de conformidade do dispositivo Intune sejam impostas.</span><span class="sxs-lookup"><span data-stu-id="05167-132">Device enrollment is required for Intune device compliance policies to be enforced.</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="05167-133">Instruções de instalação</span><span class="sxs-lookup"><span data-stu-id="05167-133">Installation instructions</span></span>

<span data-ttu-id="05167-134">O Microsoft Defender para Ponto de Extremidade no Android dá suporte à instalação em ambos os modos de dispositivos inscritos - o administrador de dispositivos herdado e os modos Enterprise Android.</span><span class="sxs-lookup"><span data-stu-id="05167-134">Microsoft Defender for Endpoint on Android supports installation on both modes of enrolled devices - the legacy Device Administrator and Android Enterprise modes.</span></span>
<span data-ttu-id="05167-135">**Atualmente, dispositivos de propriedade pessoal com perfil de trabalho e registro de dispositivos de usuário totalmente gerenciados de propriedade corporativa são suportados no Android Enterprise. O suporte para outros modos Enterprise Android será anunciado quando estiver pronto.**</span><span class="sxs-lookup"><span data-stu-id="05167-135">**Currently, Personally-owned devices with work profile and Corporate-owned fully managed user device enrollments are supported in Android Enterprise. Support for other Android Enterprise modes will be announced when ready.**</span></span>

<span data-ttu-id="05167-136">A implantação do Microsoft Defender para Ponto de Extremidade no Android é Microsoft Intune (MDM).</span><span class="sxs-lookup"><span data-stu-id="05167-136">Deployment of Microsoft Defender for Endpoint on Android is via Microsoft Intune (MDM).</span></span>
<span data-ttu-id="05167-137">Para obter mais informações, [consulte Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).</span><span class="sxs-lookup"><span data-stu-id="05167-137">For more information, see [Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune](android-intune.md).</span></span>


> [!NOTE]
> <span data-ttu-id="05167-138">**O Microsoft Defender para Ponto de Extremidade no Android está disponível [no Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) agora.**</span><span class="sxs-lookup"><span data-stu-id="05167-138">**Microsoft Defender for Endpoint on Android is available on [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) now.**</span></span> <br> <span data-ttu-id="05167-139">Você pode se conectar ao Google Play do Intune para implantar o microsoft Defender para aplicativo de ponto de extremidade, nos modos De administrador de dispositivos e Enterprise de entrolamento do Android.</span><span class="sxs-lookup"><span data-stu-id="05167-139">You can connect to Google Play from Intune to deploy Microsoft Defender for Endpoint app, across Device Administrator and Android Enterprise entrollment modes.</span></span> 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="05167-140">Como configurar o Microsoft Defender para Ponto de Extremidade no Android</span><span class="sxs-lookup"><span data-stu-id="05167-140">How to Configure Microsoft Defender for Endpoint on Android</span></span>

<span data-ttu-id="05167-141">As diretrizes sobre como configurar o Microsoft Defender para Ponto de Extremidade em recursos android estão disponíveis em [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).</span><span class="sxs-lookup"><span data-stu-id="05167-141">Guidance on how to configure Microsoft Defender for Endpoint on Android features is available in [Configure Microsoft Defender for Endpoint on Android features](android-configure.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="05167-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="05167-142">Related topics</span></span>
- [<span data-ttu-id="05167-143">Implantar o Microsoft Defender para Ponto de Extremidade para Android com o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="05167-143">Deploy Microsoft Defender for Endpoint on Android with Microsoft Intune</span></span>](android-intune.md)
- [<span data-ttu-id="05167-144">Configurar o Microsoft Defender para Ponto de Extremidade para recursos do Android</span><span class="sxs-lookup"><span data-stu-id="05167-144">Configure Microsoft Defender for Endpoint on Android features</span></span>](android-configure.md)

