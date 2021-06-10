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
description: Use ferramentas de Gerenciamento de Dispositivo Móvel para implantar o pacote de configuração em dispositivos para que eles sejam integrados ao serviço.
ms.openlocfilehash: 1ad1115308257fa3ce63f10edebb9129638fd52f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917987"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="9b659-103">Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="9b659-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="9b659-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9b659-104">**Applies to:**</span></span>

- [<span data-ttu-id="9b659-105">Microsoft 365 Prevenção contra perda de dados do ponto de extremidade (DLP)</span><span class="sxs-lookup"><span data-stu-id="9b659-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="9b659-106">Você pode usar soluções de gerenciamento de dispositivo móvel (MDM) para configurar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9b659-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="9b659-107">Microsoft 365 A prevenção contra perda de dados do ponto de extremidade dá suporte a MDMs fornecendo OMA-URIs para criar políticas para gerenciar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9b659-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="9b659-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="9b659-108">Before you begin</span></span>
<span data-ttu-id="9b659-109">Se você estiver usando Microsoft Intune, deverá ter o MDM do dispositivo inscrito.</span><span class="sxs-lookup"><span data-stu-id="9b659-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="9b659-110">Caso contrário, as configurações não serão aplicadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="9b659-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="9b659-111">Para obter mais informações sobre a habilitação do MDM com Microsoft Intune, consulte Registro de [dispositivo (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).</span><span class="sxs-lookup"><span data-stu-id="9b659-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="9b659-112">Dispositivos de integração usando Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9b659-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="9b659-113">Siga as instruções do [Intune](/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="9b659-113">Follow the instructions from [Intune](/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="9b659-114">A **política Status da Saúde para dispositivos conectados** usa propriedades somente leitura e não pode ser remediada.</span><span class="sxs-lookup"><span data-stu-id="9b659-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="9b659-115">Offboard e monitore dispositivos usando ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="9b659-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="9b659-116">Por motivos de segurança, o pacote usado para dispositivos offboard expirará 30 dias após a data em que foi baixado.</span><span class="sxs-lookup"><span data-stu-id="9b659-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="9b659-117">Os pacotes de offboard expirados enviados para um dispositivo serão rejeitados.</span><span class="sxs-lookup"><span data-stu-id="9b659-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="9b659-118">Ao baixar um pacote de offboard, você será notificado sobre a data de expiração dos pacotes e ele também será incluído no nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="9b659-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="9b659-119">As políticas de integração e de offboard não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.</span><span class="sxs-lookup"><span data-stu-id="9b659-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="9b659-120">Obter o pacote de offboard do [Centro de Conformidade da Microsoft.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="9b659-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="9b659-121">No painel de navegação, selecione **Configurações**  >  **Offboarding** de integração do  >  **dispositivo.**</span><span class="sxs-lookup"><span data-stu-id="9b659-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="9b659-122">No campo **Método de implantação,** selecione **Gerenciamento de Dispositivo Móvel /Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="9b659-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
4. <span data-ttu-id="9b659-123">Clique **em Baixar pacote** e salve o .zip arquivo.</span><span class="sxs-lookup"><span data-stu-id="9b659-123">Click **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="9b659-124">Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelos administradores de rede que implantarão o pacote.</span><span class="sxs-lookup"><span data-stu-id="9b659-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="9b659-125">Você deve ter um arquivo chamado *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span><span class="sxs-lookup"><span data-stu-id="9b659-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span></span>

6. <span data-ttu-id="9b659-126">Use a Microsoft Intune de configuração personalizada para implantar as seguintes configurações OMA-URI com suporte.</span><span class="sxs-lookup"><span data-stu-id="9b659-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="9b659-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="9b659-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="9b659-128">Tipo de data: Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9b659-128">Date type: String</span></span>      
      <span data-ttu-id="9b659-129">Valor: [Copiar e colar o valor do conteúdo do arquivo DeviceCompliance_valid_until_YYYY-MM-DD.offboarding]</span><span class="sxs-lookup"><span data-stu-id="9b659-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="9b659-130">Para obter mais informações sobre Microsoft Intune configurações de política, consulte Windows 10 [configurações](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)de política em Microsoft Intune .</span><span class="sxs-lookup"><span data-stu-id="9b659-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="9b659-131">A **política Status da Saúde para dispositivos** fora do quadro usa propriedades somente leitura e não pode ser remediada.</span><span class="sxs-lookup"><span data-stu-id="9b659-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b659-132">O offboard faz com que o dispositivo pare de enviar dados do sensor para o portal, mas os dados do dispositivo, incluindo a referência a todos os alertas que ele teve, serão mantidos por até 6 meses.</span><span class="sxs-lookup"><span data-stu-id="9b659-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9b659-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9b659-133">Related topics</span></span>
- [<span data-ttu-id="9b659-134">Integração Windows 10 usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="9b659-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="9b659-135">Integração Windows 10 dispositivos usando Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9b659-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="9b659-136">Integrar dispositivos Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="9b659-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="9b659-137">Dispositivos integrados de VDI (Virtual Desktop Infrastructure) não persistente</span><span class="sxs-lookup"><span data-stu-id="9b659-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="9b659-138">Solucionar Proteção Avançada contra Ameaças do Microsoft Defender problemas de integração</span><span class="sxs-lookup"><span data-stu-id="9b659-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)