---
title: Obter dispositivos conectados ao Microsoft Defender para Ponto de Extremidade
description: Acompanhe a integração de dispositivos gerenciados pelo Intune ao Microsoft Defender para Ponto de Extremidade e aumente a taxa de integração.
keywords: onboard, gerenciamento do Intune, Microsoft Defender para Ponto de Extremidade, Microsoft Defender, Windows Defender, gerenciamento de configuração
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7798f3b6bd2f99d48a8fa85ecf088023f4629b7b
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841563"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="01b09-104">Obter dispositivos conectados ao Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="01b09-104">Get devices onboarded to Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="01b09-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="01b09-105">**Applies to:**</span></span>
- [<span data-ttu-id="01b09-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="01b09-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="01b09-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01b09-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="01b09-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="01b09-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="01b09-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="01b09-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="01b09-110">Cada dispositivo integrado adiciona um sensor de detecção e resposta de ponto de extremidade (EDR) e aumenta a visibilidade sobre a atividade de violação em sua rede.</span><span class="sxs-lookup"><span data-stu-id="01b09-110">Each onboarded device adds an additional endpoint detection and response (EDR) sensor and increases visibility over breach activity in your network.</span></span> <span data-ttu-id="01b09-111">A integração também garante que um dispositivo possa ser verificado se há componentes vulneráveis, bem como problemas de configuração de segurança e pode receber ações críticas de correção durante ataques.</span><span class="sxs-lookup"><span data-stu-id="01b09-111">Onboarding also ensures that a device can be checked for vulnerable components as well security configuration issues and can receive critical remediation actions during attacks.</span></span>

<span data-ttu-id="01b09-112">Antes de rastrear e gerenciar a integração de dispositivos:</span><span class="sxs-lookup"><span data-stu-id="01b09-112">Before you can track and manage onboarding of devices:</span></span>
- [<span data-ttu-id="01b09-113">Registrar seus dispositivos no gerenciamento do Intune</span><span class="sxs-lookup"><span data-stu-id="01b09-113">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="01b09-114">Verifique se você tem as permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="01b09-114">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a><span data-ttu-id="01b09-115">Descobrir e rastrear dispositivos desprotegidos</span><span class="sxs-lookup"><span data-stu-id="01b09-115">Discover and track unprotected devices</span></span>

<span data-ttu-id="01b09-116">O **cartão onboarding** fornece uma visão geral de alto nível de sua taxa de integração comparando o número de dispositivos Windows 10 que realmente integraram com o Defender para Ponto de Extremidade em relação ao número total de dispositivos Windows 10 gerenciados pelo Intune.</span><span class="sxs-lookup"><span data-stu-id="01b09-116">The **Onboarding** card provides a high-level overview of your onboarding rate by comparing the number of Windows 10 devices that have actually onboarded to Defender for Endpoint against the total number of Intune-managed Windows 10 devices.</span></span>

<span data-ttu-id="01b09-117">![Cartão de integração de gerenciamento de configuração de dispositivo](images/secconmgmt_onboarding_card.png)</span><span class="sxs-lookup"><span data-stu-id="01b09-117">![Device configuration management Onboarding card](images/secconmgmt_onboarding_card.png)</span></span><br>
<span data-ttu-id="01b09-118">*Cartão mostrando dispositivos conectados em comparação com o número total de dispositivos gerenciados Windows 10 Intune*</span><span class="sxs-lookup"><span data-stu-id="01b09-118">*Card showing onboarded devices compared to the total number of Intune-managed Windows 10 device*</span></span>

>[!NOTE]
><span data-ttu-id="01b09-119">Se você usou o Security Center Configuration Manager, o script de integração ou outros métodos de integração que não usam perfis do Intune, poderá encontrar discrepâncias de dados.</span><span class="sxs-lookup"><span data-stu-id="01b09-119">If you used Security Center Configuration Manager, the onboarding script, or other onboarding methods that don’t use Intune profiles, you might encounter data discrepancies.</span></span> <span data-ttu-id="01b09-120">Para resolver essas discrepâncias, crie um perfil de configuração do Intune correspondente para a integração do Defender para Ponto de Extremidade e atribua esse perfil aos seus dispositivos.</span><span class="sxs-lookup"><span data-stu-id="01b09-120">To resolve these discrepancies, create a corresponding Intune configuration profile for Defender for Endpoint onboarding and assign that profile to your devices.</span></span>

## <a name="onboard-more-devices-with-intune-profiles"></a><span data-ttu-id="01b09-121">Integrar mais dispositivos com perfis do Intune</span><span class="sxs-lookup"><span data-stu-id="01b09-121">Onboard more devices with Intune profiles</span></span>

<span data-ttu-id="01b09-122">O Defender para Ponto de Extremidade fornece várias opções convenientes para [integração Windows 10 dispositivos](onboard-configure.md).</span><span class="sxs-lookup"><span data-stu-id="01b09-122">Defender for Endpoint provides several convenient options for [onboarding Windows 10 devices](onboard-configure.md).</span></span> <span data-ttu-id="01b09-123">No entanto, para dispositivos gerenciados pelo Intune, você pode aproveitar os perfis do Intune para implantar convenientemente o sensor Defender para Ponto de Extremidade para selecionar dispositivos, integrando efetivamente esses dispositivos ao serviço.</span><span class="sxs-lookup"><span data-stu-id="01b09-123">For Intune-managed devices, however, you can leverage Intune profiles to conveniently deploy the Defender for Endpoint sensor to select devices, effectively onboarding these devices to the service.</span></span>

<span data-ttu-id="01b09-124">No cartão **De integração,** selecione **Onboard more devices** to create and assign a profile on Intune.</span><span class="sxs-lookup"><span data-stu-id="01b09-124">From the **Onboarding** card, select **Onboard more devices** to create and assign a profile on Intune.</span></span> <span data-ttu-id="01b09-125">O link leva você para a página de conformidade do dispositivo no Intune, que fornece uma visão geral semelhante do seu estado de integração.</span><span class="sxs-lookup"><span data-stu-id="01b09-125">The link takes you to the device compliance page on Intune, which provides a similar overview of your onboarding state.</span></span>

<span data-ttu-id="01b09-126">![Página de conformidade de dispositivo do Microsoft Defender para Ponto de Extremidade no gerenciamento de dispositivos do Intune](images/secconmgmt_onboarding_1deviceconfprofile.png)</span><span class="sxs-lookup"><span data-stu-id="01b09-126">![Microsoft Defender for Endpoint device compliance page on Intune device management](images/secconmgmt_onboarding_1deviceconfprofile.png)</span></span><br>
   <span data-ttu-id="01b09-127">*Página de conformidade de dispositivo do Microsoft Defender para Ponto de Extremidade no gerenciamento de dispositivos do Intune*</span><span class="sxs-lookup"><span data-stu-id="01b09-127">*Microsoft Defender for Endpoint device compliance page on Intune device management*</span></span>

>[!TIP]
><span data-ttu-id="01b09-128">Como alternativa, você pode navegar até a página de conformidade de integração do Defender for Endpoint no [portal](https://portal.azure.com/) Microsoft Azure de Todos os serviços > **Intune > Device compliance > Microsoft Defender ATP**.</span><span class="sxs-lookup"><span data-stu-id="01b09-128">Alternatively, you can navigate to the Defender for Endpoint onboarding compliance page in the [Microsoft Azure portal](https://portal.azure.com/) from **All services > Intune > Device compliance > Microsoft Defender ATP**.</span></span>

>[!NOTE]
> <span data-ttu-id="01b09-129">Se você quiser exibir os dados de dispositivo mais atualizados, clique em Lista de dispositivos sem sensor **ATP**.</span><span class="sxs-lookup"><span data-stu-id="01b09-129">If you want to view the most up-to-date device data, click on **List of devices without ATP sensor**.</span></span>

<span data-ttu-id="01b09-130">Na página de conformidade do dispositivo, crie um perfil de configuração especificamente para a implantação do sensor Defender para Ponto de Extremidade e atribua esse perfil aos dispositivos que você deseja integrar.</span><span class="sxs-lookup"><span data-stu-id="01b09-130">From the device compliance page, create a configuration profile specifically for the deployment of the Defender for Endpoint sensor and assign that profile to the devices you want to onboard.</span></span> <span data-ttu-id="01b09-131">Para fazer isso, você pode:</span><span class="sxs-lookup"><span data-stu-id="01b09-131">To do this, you can either:</span></span>

- <span data-ttu-id="01b09-132">Selecione **Criar um perfil de configuração de dispositivo para configurar o sensor ATP** para começar com um perfil de configuração de dispositivo predefinido.</span><span class="sxs-lookup"><span data-stu-id="01b09-132">Select **Create a device configuration profile to configure ATP sensor** to start with a predefined device configuration profile.</span></span>
- <span data-ttu-id="01b09-133">Crie o perfil de configuração do dispositivo do zero.</span><span class="sxs-lookup"><span data-stu-id="01b09-133">Create the device configuration profile from scratch.</span></span>

<span data-ttu-id="01b09-134">Para obter mais informações, [leia sobre como usar perfis de configuração](/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile)de dispositivo do Intune para integração de dispositivos no Defender for Endpoint .</span><span class="sxs-lookup"><span data-stu-id="01b09-134">For more information, [read about using Intune device configuration profiles to onboard devices to Defender for Endpoint](/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile).</span></span>

><span data-ttu-id="01b09-135">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="01b09-135">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="01b09-136">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="01b09-136">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="01b09-137">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="01b09-137">Related topics</span></span>
- [<span data-ttu-id="01b09-138">Verificar se os dispositivos estão configurados corretamente</span><span class="sxs-lookup"><span data-stu-id="01b09-138">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="01b09-139">Aumentar a conformidade com a linha de base de segurança do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="01b09-139">Increase compliance to the Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
- [<span data-ttu-id="01b09-140">Otimizar a implantação e as detecções de regras ASR</span><span class="sxs-lookup"><span data-stu-id="01b09-140">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
