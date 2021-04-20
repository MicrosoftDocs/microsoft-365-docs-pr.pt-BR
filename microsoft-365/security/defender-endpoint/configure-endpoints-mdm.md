---
title: Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel
description: Use ferramentas de Gerenciamento de Dispositivo Móvel para implantar o pacote de configuração em dispositivos para que eles sejam integrados ao serviço.
keywords: onboard devices using mdm, device management, onboard Windows ATP devices, onboard Microsoft Defender for Endpoint devices, mdm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f3042ef9ced11ebc5439308d2781528d5267975f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893608"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="038bf-104">Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="038bf-104">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="038bf-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="038bf-105">**Applies to:**</span></span>
- [<span data-ttu-id="038bf-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="038bf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="038bf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="038bf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="038bf-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="038bf-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="038bf-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="038bf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

<span data-ttu-id="038bf-110">Você pode usar soluções de gerenciamento de dispositivo móvel (MDM) para configurar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="038bf-110">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="038bf-111">O Defender for Endpoint dá suporte a MDMs fornecendo OMA-URIs para criar políticas para gerenciar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="038bf-111">Defender for Endpoint supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>

<span data-ttu-id="038bf-112">Para obter mais informações sobre como usar o CSP do Defender para Ponto de Extremidade, consulte o arquivo [DDF do WindowsAdvancedThreatProtection](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) e o arquivo [DDF do WindowsAdvancedThreatProtection.](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)</span><span class="sxs-lookup"><span data-stu-id="038bf-112">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="038bf-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="038bf-113">Before you begin</span></span>
<span data-ttu-id="038bf-114">Se você estiver usando o Microsoft Intune, deverá ter o MDM do dispositivo inscrito.</span><span class="sxs-lookup"><span data-stu-id="038bf-114">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="038bf-115">Caso contrário, as configurações não serão aplicadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="038bf-115">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="038bf-116">Para obter mais informações sobre a habilitação do MDM com o Microsoft Intune, consulte [Registro de dispositivo (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span><span class="sxs-lookup"><span data-stu-id="038bf-116">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="038bf-117">Dispositivos de integração usando o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="038bf-117">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="038bf-118">[![Imagem do PDF mostrando dispositivos de integração para o Defender para Ponto de Extremidade usando o Microsoft Intune ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="038bf-118">[![Image of the PDF showing onboarding devices to Defender for Endpoint using Microsoft Intune](images/onboard-intune.png) ](images/onboard-intune-big.png#lightbox)</span></span>

<span data-ttu-id="038bf-119">Confira o [PDF ou](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  o  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) para ver os vários caminhos na implantação do Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="038bf-119">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Defender for Endpoint.</span></span> 

<span data-ttu-id="038bf-120">Siga as instruções do [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="038bf-120">Follow the instructions from [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

<span data-ttu-id="038bf-121">Para obter mais informações sobre como usar o CSP do Defender para Ponto de Extremidade, consulte o arquivo [DDF do WindowsAdvancedThreatProtection](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) e o arquivo [DDF do WindowsAdvancedThreatProtection.](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)</span><span class="sxs-lookup"><span data-stu-id="038bf-121">For more information on using Defender for Endpoint CSP see, [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) and [WindowsAdvancedThreatProtection DDF file](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx).</span></span>


> [!NOTE]
> - <span data-ttu-id="038bf-122">A **política Status da Saúde para dispositivos conectados** usa propriedades somente leitura e não pode ser remediada.</span><span class="sxs-lookup"><span data-stu-id="038bf-122">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>
> - <span data-ttu-id="038bf-123">A configuração da frequência de relatório de dados de diagnóstico só está disponível para dispositivos no Windows 10, versão 1703.</span><span class="sxs-lookup"><span data-stu-id="038bf-123">Configuration of diagnostic data reporting frequency is only available for devices on Windows 10, version 1703.</span></span>


>[!TIP]
> <span data-ttu-id="038bf-124">Após a integração do dispositivo, você pode optar por executar um teste de detecção para verificar se um dispositivo está corretamente conectado ao serviço.</span><span class="sxs-lookup"><span data-stu-id="038bf-124">After onboarding the device, you can choose to run a detection test to verify that a device is properly onboarded to the service.</span></span> <span data-ttu-id="038bf-125">Para obter mais informações, [consulte Execute a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span><span class="sxs-lookup"><span data-stu-id="038bf-125">For more information, see [Run a detection test on a newly onboarded Microsoft Defender for Endpoint device](run-detection-test.md).</span></span>


<span data-ttu-id="038bf-126">Confira o [PDF ou](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  o  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) para ver os vários caminhos na implantação do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="038bf-126">Check out the [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf)  or  [Visio](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) to see the various paths in deploying Microsoft Defender for Endpoint.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="038bf-127">Offboard e monitore dispositivos usando ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="038bf-127">Offboard and monitor devices using Mobile Device Management tools</span></span>
<span data-ttu-id="038bf-128">Por motivos de segurança, o pacote usado para dispositivos offboard expirará 30 dias após a data em que foi baixado.</span><span class="sxs-lookup"><span data-stu-id="038bf-128">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="038bf-129">Os pacotes de offboard expirados enviados para um dispositivo serão rejeitados.</span><span class="sxs-lookup"><span data-stu-id="038bf-129">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="038bf-130">Ao baixar um pacote de offboard, você será notificado sobre a data de expiração dos pacotes e ele também será incluído no nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="038bf-130">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="038bf-131">As políticas de integração e de offboard não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.</span><span class="sxs-lookup"><span data-stu-id="038bf-131">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="038bf-132">Obter o pacote de offboarding do [Centro de Segurança do Microsoft Defender](https://securitycenter.windows.com/):</span><span class="sxs-lookup"><span data-stu-id="038bf-132">Get the offboarding package from [Microsoft Defender Security Center](https://securitycenter.windows.com/):</span></span>

   1. <span data-ttu-id="038bf-133">No painel de navegação, selecione **Configurações**  >  **offboarding**.</span><span class="sxs-lookup"><span data-stu-id="038bf-133">In the navigation pane, select **Settings** > **Offboarding**.</span></span>

   1. <span data-ttu-id="038bf-134">Selecione Windows 10 como o sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="038bf-134">Select Windows 10 as the operating system.</span></span>

   1. <span data-ttu-id="038bf-135">No campo **Método de implantação,** selecione **Gerenciamento de Dispositivo Móvel / Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="038bf-135">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
   1. <span data-ttu-id="038bf-136">Clique **em Baixar pacote** e salve o arquivo .zip.</span><span class="sxs-lookup"><span data-stu-id="038bf-136">Click **Download package**, and save the .zip file.</span></span>

2. <span data-ttu-id="038bf-137">Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelos administradores de rede que implantarão o pacote.</span><span class="sxs-lookup"><span data-stu-id="038bf-137">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="038bf-138">Você deve ter um arquivo chamado *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.</span><span class="sxs-lookup"><span data-stu-id="038bf-138">You should have a file named *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding*.</span></span>

3. <span data-ttu-id="038bf-139">Use a política de configuração personalizada do Microsoft Intune para implantar as seguintes configurações OMA-URI com suporte.</span><span class="sxs-lookup"><span data-stu-id="038bf-139">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="038bf-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="038bf-140">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span><br/>
      <span data-ttu-id="038bf-141">Tipo de data: Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="038bf-141">Date type: String</span></span><br/>
      <span data-ttu-id="038bf-142">Valor: [Copiar e colar o valor do conteúdo do arquivo WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding]</span><span class="sxs-lookup"><span data-stu-id="038bf-142">Value: [Copy and paste the value from the content of the WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="038bf-143">Para obter mais informações sobre as configurações de política do Microsoft Intune, consulte Configurações de política do [Windows 10 no Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="038bf-143">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>


> [!NOTE]
> <span data-ttu-id="038bf-144">A **política Status da Saúde para dispositivos** fora do quadro usa propriedades somente leitura e não pode ser remediada.</span><span class="sxs-lookup"><span data-stu-id="038bf-144">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="038bf-145">O offboard faz com que o dispositivo pare de enviar dados do sensor para o portal, mas os dados do dispositivo, incluindo a referência a todos os alertas que ele teve, serão mantidos por até 6 meses.</span><span class="sxs-lookup"><span data-stu-id="038bf-145">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="038bf-146">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="038bf-146">Related topics</span></span>
- [<span data-ttu-id="038bf-147">Integração de dispositivos Windows 10 usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="038bf-147">Onboard Windows 10 devices using Group Policy</span></span>](configure-endpoints-gp.md)
- [<span data-ttu-id="038bf-148">Integração de dispositivos Windows 10 usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="038bf-148">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](configure-endpoints-sccm.md)
- [<span data-ttu-id="038bf-149">Integrar dispositivos Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="038bf-149">Onboard Windows 10 devices using a local script</span></span>](configure-endpoints-script.md)
- [<span data-ttu-id="038bf-150">Dispositivos integrados de VDI (Virtual Desktop Infrastructure) não persistente</span><span class="sxs-lookup"><span data-stu-id="038bf-150">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](configure-endpoints-vdi.md)
- [<span data-ttu-id="038bf-151">Executar um teste de detecção em um dispositivo recém-integrado do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="038bf-151">Run a detection test on a newly onboarded Microsoft Defender for Endpoint device</span></span>](run-detection-test.md)
- [<span data-ttu-id="038bf-152">Solucionar problemas de integração do Microsoft Defender para pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="038bf-152">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
