---
title: Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Use as ferramentas de Gerenciamento de Dispositivo Móvel para implantar o pacote de configuração em dispositivos para que eles sejam integrados ao serviço.
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769392"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="f235d-103">Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="f235d-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="f235d-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f235d-104">**Applies to:**</span></span>

- [<span data-ttu-id="f235d-105">Prevenção contra perda de dados de ponto de extremidade (DLP) do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f235d-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](/microsoft-365/compliance/endpoint-dlp-learn-about)

<span data-ttu-id="f235d-106">Você pode usar soluções de gerenciamento de dispositivo móvel (MDM) para configurar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f235d-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="f235d-107">A prevenção contra perda de dados de ponto de extremidade do Microsoft 365 dá suporte a MDMs OMA-URIs criar políticas para gerenciar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f235d-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="f235d-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="f235d-108">Before you begin</span></span>
<span data-ttu-id="f235d-109">Se você estiver usando o Microsoft Intune, deverá ter o MDM do dispositivo inscrito.</span><span class="sxs-lookup"><span data-stu-id="f235d-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="f235d-110">Caso contrário, as configurações não serão aplicadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="f235d-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="f235d-111">Para obter mais informações sobre a habilitação do MDM com o Microsoft Intune, consulte [Registro de dispositivo (Microsoft Intune).](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)</span><span class="sxs-lookup"><span data-stu-id="f235d-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="f235d-112">Dispositivos onboard usando o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f235d-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="f235d-113">Siga as instruções do [Intune.](https://docs.microsoft.com/intune/advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="f235d-113">Follow the instructions from [Intune](https://docs.microsoft.com/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="f235d-114">A **política status de saúde para dispositivos onboarded** usa propriedades somente leitura e não pode ser remediada.</span><span class="sxs-lookup"><span data-stu-id="f235d-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="f235d-115">Fazer o offboard e monitorar dispositivos usando ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="f235d-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="f235d-116">Por motivos de segurança, o pacote usado para dispositivos offboard expirará 30 dias após a data em que foi baixado.</span><span class="sxs-lookup"><span data-stu-id="f235d-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="f235d-117">Os pacotes de reexenciamento expirados enviados para um dispositivo serão rejeitados.</span><span class="sxs-lookup"><span data-stu-id="f235d-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="f235d-118">Ao baixar um pacote de descarregamento, você será notificado sobre a data de vencimento dos pacotes e ele também será incluído no nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="f235d-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="f235d-119">As políticas de integração e de transferência não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.</span><span class="sxs-lookup"><span data-stu-id="f235d-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="f235d-120">Obter o pacote de redação do Centro [de Conformidade da Microsoft.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="f235d-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="f235d-121">No painel de navegação, selecione **Configurações**  >  **integração do dispositivo** à  >  **rebordagem.**</span><span class="sxs-lookup"><span data-stu-id="f235d-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="f235d-122">No campo **do método de implantação,** selecione Gerenciamento de **Dispositivo Móvel/Microsoft Intune.**</span><span class="sxs-lookup"><span data-stu-id="f235d-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
4. <span data-ttu-id="f235d-123">Clique **em Baixar pacote** e salve o arquivo .zip.</span><span class="sxs-lookup"><span data-stu-id="f235d-123">Click **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="f235d-124">Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que possa ser acessado pelos administradores de rede que implantarão o pacote.</span><span class="sxs-lookup"><span data-stu-id="f235d-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="f235d-125">Você deve ter um arquivo *chamado DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span><span class="sxs-lookup"><span data-stu-id="f235d-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span></span>

6. <span data-ttu-id="f235d-126">Use a política de configuração personalizada do Microsoft Intune para implantar as seguintes configurações OMA-URI com suporte.</span><span class="sxs-lookup"><span data-stu-id="f235d-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="f235d-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="f235d-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="f235d-128">Tipo de data: Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f235d-128">Date type: String</span></span>      
      <span data-ttu-id="f235d-129">Valor: [Copiar e colar o valor do conteúdo do arquivo DeviceCompliance_valid_until_YYYY-MM-DD.offboarding]</span><span class="sxs-lookup"><span data-stu-id="f235d-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="f235d-130">Para obter mais informações sobre as configurações de política do Microsoft Intune, consulte as configurações de política do [Windows 10 no Microsoft Intune.](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="f235d-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="f235d-131">O **Status de Saúde para dispositivos** de fora da área usa propriedades somente leitura e não pode ser remediado.</span><span class="sxs-lookup"><span data-stu-id="f235d-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f235d-132">A reação faz com que o dispositivo pare de enviar dados do sensor para o portal, mas os dados do dispositivo, incluindo a referência a todos os alertas que ele recebeu, serão retidos por até seis meses.</span><span class="sxs-lookup"><span data-stu-id="f235d-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f235d-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="f235d-133">Related topics</span></span>
- [<span data-ttu-id="f235d-134">Integração de dispositivos Windows 10 usando Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="f235d-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="f235d-135">Integração de dispositivos Windows 10 usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f235d-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="f235d-136">Integrar dispositivos Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="f235d-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="f235d-137">Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)</span><span class="sxs-lookup"><span data-stu-id="f235d-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="f235d-138">Solucionar problemas de integração da Proteção Avançada contra Ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f235d-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
