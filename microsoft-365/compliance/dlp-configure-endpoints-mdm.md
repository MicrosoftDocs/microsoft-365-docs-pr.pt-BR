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
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a><span data-ttu-id="db856-103">Integrar dispositivo Windows 10 usando as ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="db856-103">Onboard Windows 10 devices using Mobile Device Management tools</span></span>

<span data-ttu-id="db856-104">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="db856-104">**Applies to:**</span></span>

- [<span data-ttu-id="db856-105">Prevenção contra perda de dados do Microsoft 365 Endpoint (DLP)</span><span class="sxs-lookup"><span data-stu-id="db856-105">Microsoft 365 Endpoint data loss prevention (DLP)</span></span>](./endpoint-dlp-learn-about.md)

<span data-ttu-id="db856-106">Você pode usar soluções de gerenciamento de dispositivo móvel (MDM) para configurar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="db856-106">You can use mobile device management (MDM) solutions to configure devices.</span></span> <span data-ttu-id="db856-107">A prevenção contra perda de dados do Ponto de Extremidade do Microsoft 365 dá suporte a MDMs, fornecendo OMA-URIs para criar políticas para gerenciar dispositivos.</span><span class="sxs-lookup"><span data-stu-id="db856-107">Microsoft 365 Endpoint data loss prevention supports MDMs by providing OMA-URIs to create policies to manage devices.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="db856-108">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="db856-108">Before you begin</span></span>
<span data-ttu-id="db856-109">Se você estiver usando o Microsoft Intune, deverá ter o MDM do dispositivo inscrito.</span><span class="sxs-lookup"><span data-stu-id="db856-109">If you're using Microsoft Intune, you must have the device MDM Enrolled.</span></span> <span data-ttu-id="db856-110">Caso contrário, as configurações não serão aplicadas com êxito.</span><span class="sxs-lookup"><span data-stu-id="db856-110">Otherwise, settings will not be applied successfully.</span></span> 

<span data-ttu-id="db856-111">Para obter mais informações sobre a habilitação do MDM com o Microsoft Intune, consulte [Registro de dispositivo (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).</span><span class="sxs-lookup"><span data-stu-id="db856-111">For more information on enabling MDM with Microsoft Intune, see [Device enrollment (Microsoft Intune)](/mem/intune/enrollment/device-enrollment).</span></span>

## <a name="onboard-devices-using-microsoft-intune"></a><span data-ttu-id="db856-112">Dispositivos de integração usando o Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="db856-112">Onboard devices using Microsoft Intune</span></span>

<span data-ttu-id="db856-113">Siga as instruções do [Intune](/intune/advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="db856-113">Follow the instructions from [Intune](/intune/advanced-threat-protection).</span></span>

> [!NOTE]
> - <span data-ttu-id="db856-114">A **política Status da Saúde para dispositivos conectados** usa propriedades somente leitura e não pode ser remediada.</span><span class="sxs-lookup"><span data-stu-id="db856-114">The **Health Status for onboarded devices** policy uses read-only properties and can't be remediated.</span></span>

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a><span data-ttu-id="db856-115">Offboard e monitore dispositivos usando ferramentas de Gerenciamento de Dispositivo Móvel</span><span class="sxs-lookup"><span data-stu-id="db856-115">Offboard and monitor devices using Mobile Device Management tools</span></span>

<span data-ttu-id="db856-116">Por motivos de segurança, o pacote usado para dispositivos offboard expirará 30 dias após a data em que foi baixado.</span><span class="sxs-lookup"><span data-stu-id="db856-116">For security reasons, the package used to Offboard devices will expire 30 days after the date it was downloaded.</span></span> <span data-ttu-id="db856-117">Os pacotes de offboard expirados enviados para um dispositivo serão rejeitados.</span><span class="sxs-lookup"><span data-stu-id="db856-117">Expired offboarding packages sent to a device will be rejected.</span></span> <span data-ttu-id="db856-118">Ao baixar um pacote de offboard, você será notificado sobre a data de expiração dos pacotes e ele também será incluído no nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="db856-118">When downloading an offboarding package you will be notified of the packages expiry date and it will also be included in the package name.</span></span>

> [!NOTE]
> <span data-ttu-id="db856-119">As políticas de integração e de offboard não devem ser implantadas no mesmo dispositivo ao mesmo tempo, caso contrário, isso causará colisões imprevisíveis.</span><span class="sxs-lookup"><span data-stu-id="db856-119">Onboarding and offboarding policies must not be deployed on the same device at the same time, otherwise this will cause unpredictable collisions.</span></span>

1. <span data-ttu-id="db856-120">Obter o pacote de offboard do [Centro de Conformidade da Microsoft.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="db856-120">Get the offboarding package from [Microsoft Compliance center](https://compliance.microsoft.com/).</span></span>

2. <span data-ttu-id="db856-121">No painel de navegação, selecione **Configurações**  >  **Integrando o** Dispositivo  >  **offboarding**.</span><span class="sxs-lookup"><span data-stu-id="db856-121">In the navigation pane, select **Settings** > **Device onboarding** > **Offboarding**.</span></span>

3. <span data-ttu-id="db856-122">No campo **Método de implantação,** selecione **Gerenciamento de Dispositivo Móvel / Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="db856-122">In the **Deployment method** field, select **Mobile Device Management / Microsoft Intune**.</span></span>
    
4. <span data-ttu-id="db856-123">Clique **em Baixar pacote** e salve o arquivo .zip.</span><span class="sxs-lookup"><span data-stu-id="db856-123">Click **Download package**, and save the .zip file.</span></span>

5. <span data-ttu-id="db856-124">Extraia o conteúdo do arquivo .zip para um local compartilhado somente leitura que pode ser acessado pelos administradores de rede que implantarão o pacote.</span><span class="sxs-lookup"><span data-stu-id="db856-124">Extract the contents of the .zip file to a shared, read-only location that can be accessed by the network administrators who will deploy the package.</span></span> <span data-ttu-id="db856-125">Você deve ter um arquivo chamado *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span><span class="sxs-lookup"><span data-stu-id="db856-125">You should have a file named *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding*.</span></span>

6. <span data-ttu-id="db856-126">Use a política de configuração personalizada do Microsoft Intune para implantar as seguintes configurações OMA-URI com suporte.</span><span class="sxs-lookup"><span data-stu-id="db856-126">Use the Microsoft Intune custom configuration policy to deploy the following supported OMA-URI settings.</span></span>

      <span data-ttu-id="db856-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span><span class="sxs-lookup"><span data-stu-id="db856-127">OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding</span></span>      
      <span data-ttu-id="db856-128">Tipo de data: Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="db856-128">Date type: String</span></span>      
      <span data-ttu-id="db856-129">Valor: [Copiar e colar o valor do conteúdo do arquivo DeviceCompliance_valid_until_YYYY-MM-DD.offboarding]</span><span class="sxs-lookup"><span data-stu-id="db856-129">Value: [Copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]</span></span>

<span data-ttu-id="db856-130">Para obter mais informações sobre as configurações de política do Microsoft Intune, consulte Configurações de política do [Windows 10 no Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="db856-130">For more information on Microsoft Intune policy settings see, [Windows 10 policy settings in Microsoft Intune](/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).</span></span>

> [!NOTE]
> <span data-ttu-id="db856-131">A **política Status da Saúde para dispositivos** fora do quadro usa propriedades somente leitura e não pode ser remediada.</span><span class="sxs-lookup"><span data-stu-id="db856-131">The **Health Status for offboarded devices** policy uses read-only properties and can't be remediated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db856-132">O offboard faz com que o dispositivo pare de enviar dados do sensor para o portal, mas os dados do dispositivo, incluindo a referência a todos os alertas que ele teve, serão mantidos por até 6 meses.</span><span class="sxs-lookup"><span data-stu-id="db856-132">Offboarding causes the device to stop sending sensor data to the portal but data from the device, including reference to any alerts it has had will be retained for up to 6 months.</span></span>

## <a name="related-topics"></a><span data-ttu-id="db856-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="db856-133">Related topics</span></span>
- [<span data-ttu-id="db856-134">Integração de dispositivos Windows 10 usando a Política de Grupo</span><span class="sxs-lookup"><span data-stu-id="db856-134">Onboard Windows 10 devices using Group Policy</span></span>](dlp-configure-endpoints-gp.md)
- [<span data-ttu-id="db856-135">Integração de dispositivos Windows 10 usando o Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="db856-135">Onboard Windows 10 devices using Microsoft Endpoint Configuration Manager</span></span>](dlp-configure-endpoints-sccm.md)
- [<span data-ttu-id="db856-136">Integrar dispositivos Windows 10 usando um script local</span><span class="sxs-lookup"><span data-stu-id="db856-136">Onboard Windows 10 devices using a local script</span></span>](dlp-configure-endpoints-script.md)
- [<span data-ttu-id="db856-137">Integrar dispositivos não persistentes de VDI (virtual desktop infrastructure)</span><span class="sxs-lookup"><span data-stu-id="db856-137">Onboard non-persistent virtual desktop infrastructure (VDI) devices</span></span>](dlp-configure-endpoints-vdi.md)
- [<span data-ttu-id="db856-138">Solucionar problemas de integração da Proteção Avançada contra Ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="db856-138">Troubleshoot Microsoft Defender Advanced Threat Protection onboarding issues</span></span>](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)