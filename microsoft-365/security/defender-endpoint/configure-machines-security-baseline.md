---
title: Aumentar a conformidade com a linha de base de segurança do Microsoft Defender for Endpoint
description: A linha de base de segurança do Microsoft Defender para Ponto de Extremidade define controles de segurança para fornecer proteção ideal.
keywords: Gerenciamento do Intune, Microsoft Defender para Ponto de Extremidade, Microsoft Defender, Microsoft Defender para Endpoint ASR, linha de base de segurança
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
ms.openlocfilehash: fbdc0d02d4c5ba5cfda9773e62082217ba4f8c4e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933596"
---
# <a name="increase-compliance-to-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="76abb-104">Aumentar a conformidade com a linha de base de segurança do Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="76abb-104">Increase compliance to the Microsoft Defender for Endpoint security baseline</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="76abb-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="76abb-105">**Applies to:**</span></span>
- [<span data-ttu-id="76abb-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="76abb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="76abb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="76abb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="76abb-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="76abb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="76abb-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="76abb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

<span data-ttu-id="76abb-110">As linhas de base de segurança garantem que os recursos de segurança sejam configurados de acordo com as diretrizes de especialistas em segurança e administradores especialistas do sistema Windows.</span><span class="sxs-lookup"><span data-stu-id="76abb-110">Security baselines ensure that security features are configured according to guidance from both security experts and expert Windows system administrators.</span></span> <span data-ttu-id="76abb-111">Quando implantada, a linha de base de segurança do Defender for Endpoint define os controles de segurança do Defender para Ponto de Extremidade para fornecer proteção ideal.</span><span class="sxs-lookup"><span data-stu-id="76abb-111">When deployed, the Defender for Endpoint security baseline sets Defender for Endpoint security controls to provide optimal protection.</span></span>

<span data-ttu-id="76abb-112">Para entender as linhas de base de segurança e como elas são atribuídas no Intune usando perfis de configuração, [leia esta perguntas frequentes](https://docs.microsoft.com/intune/security-baselines#q--a).</span><span class="sxs-lookup"><span data-stu-id="76abb-112">To understand security baselines and how they are assigned on Intune using configuration profiles, [read this FAQ](https://docs.microsoft.com/intune/security-baselines#q--a).</span></span>

<span data-ttu-id="76abb-113">Antes de implantar e rastrear a conformidade com as linhas de base de segurança:</span><span class="sxs-lookup"><span data-stu-id="76abb-113">Before you can deploy and track compliance to security baselines:</span></span>
- [<span data-ttu-id="76abb-114">Registrar seus dispositivos no gerenciamento do Intune</span><span class="sxs-lookup"><span data-stu-id="76abb-114">Enroll your devices to Intune management</span></span>](configure-machines.md#enroll-devices-to-intune-management)
- [<span data-ttu-id="76abb-115">Verifique se você tem as permissões necessárias</span><span class="sxs-lookup"><span data-stu-id="76abb-115">Ensure you have the necessary permissions</span></span>](configure-machines.md#obtain-required-permissions)

## <a name="compare-the-microsoft-defender-for-endpoint-and-the-windows-intune-security-baselines"></a><span data-ttu-id="76abb-116">Comparar o Microsoft Defender para Ponto de Extremidade e as linhas de base de segurança do Windows Intune</span><span class="sxs-lookup"><span data-stu-id="76abb-116">Compare the Microsoft Defender for Endpoint and the Windows Intune security baselines</span></span>
<span data-ttu-id="76abb-117">A linha de base de segurança do Windows Intune fornece um conjunto abrangente de configurações recomendadas necessárias para configurar com segurança dispositivos que executam o Windows, incluindo configurações do navegador, configurações do PowerShell, bem como configurações para alguns recursos de segurança, como o Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="76abb-117">The Windows Intune security baseline provides a comprehensive set of recommended settings needed to securely configure devices running Windows, including browser settings, PowerShell settings, as well as settings for some security features like Microsoft Defender Antivirus.</span></span> <span data-ttu-id="76abb-118">Por outro lado, a linha de base do Defender for Endpoint fornece configurações que otimizam todos os controles de segurança na pilha do Defender para Ponto de Extremidade, incluindo configurações para detecção e resposta do ponto de extremidade (EDR), bem como configurações também encontradas na linha de base de segurança do Windows Intune.</span><span class="sxs-lookup"><span data-stu-id="76abb-118">In contrast, the Defender for Endpoint baseline provides settings that optimize all the security controls in the Defender for Endpoint stack, including settings for endpoint detection and response (EDR) as well as settings also found in the Windows Intune security baseline.</span></span> <span data-ttu-id="76abb-119">Para obter mais informações sobre cada linha de base, consulte:</span><span class="sxs-lookup"><span data-stu-id="76abb-119">For more information about each baseline, see:</span></span>

- [<span data-ttu-id="76abb-120">Configurações de linha de base de segurança do Windows para o Intune</span><span class="sxs-lookup"><span data-stu-id="76abb-120">Windows security baseline settings for Intune</span></span>](https://docs.microsoft.com/intune/security-baseline-settings-windows)
- [<span data-ttu-id="76abb-121">Configurações de linha de base do Microsoft Defender para Ponto de Extremidade para Intune</span><span class="sxs-lookup"><span data-stu-id="76abb-121">Microsoft Defender for Endpoint baseline settings for Intune</span></span>](https://docs.microsoft.com/intune/security-baseline-settings-defender-atp)

<span data-ttu-id="76abb-122">O ideal é que os dispositivos que integram o Defender para o Ponto de Extremidade sejam implantados em ambas as linhas de base: a linha de base de segurança do Windows Intune para proteger inicialmente o Windows e, em seguida, a linha de base de segurança do Defender for Endpoint em camadas na parte superior para configurar idealmente os controles de segurança do Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="76abb-122">Ideally, devices onboarded to Defender for Endpoint are deployed both baselines: the Windows Intune security baseline to initially secure Windows and then the Defender for Endpoint security baseline layered on top to optimally configure the Defender for Endpoint security controls.</span></span> <span data-ttu-id="76abb-123">Para se beneficiar dos dados mais recentes sobre riscos e ameaças e minimizar conflitos à medida que as linhas de base evoluem, sempre aplique as versões mais recentes das linhas de base em todos os produtos assim que eles são lançados.</span><span class="sxs-lookup"><span data-stu-id="76abb-123">To benefit from the latest data on risks and threats and to minimize conflicts as baselines evolve, always apply the latest versions of the baselines across all products as soon as they are released.</span></span>

>[!NOTE]
><span data-ttu-id="76abb-124">A linha de base de segurança do Defender para Ponto de Extremidade foi otimizada para dispositivos físicos e atualmente não é recomendada para uso em pontos de extremidade de máquina virtual (VMs) ou VDI.</span><span class="sxs-lookup"><span data-stu-id="76abb-124">The Defender for Endpoint security baseline has been optimized for physical devices and is currently not recommended for use on virtual machine (VMs) or VDI endpoints.</span></span> <span data-ttu-id="76abb-125">Determinadas configurações de linha de base podem afetar sessões interativas remotas em ambientes virtualizados.</span><span class="sxs-lookup"><span data-stu-id="76abb-125">Certain baseline settings can impact remote interactive sessions on virtualized environments.</span></span>

## <a name="monitor-compliance-to-the-defender-for-endpoint-security-baseline"></a><span data-ttu-id="76abb-126">Monitorar a conformidade com a linha de base de segurança do Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="76abb-126">Monitor compliance to the Defender for Endpoint security baseline</span></span>

<span data-ttu-id="76abb-127">O cartão de [](configure-machines.md) linha de **base** de segurança no gerenciamento de configuração de dispositivo fornece uma visão geral da conformidade entre dispositivos Windows 10 que foram atribuídos à linha de base de segurança do Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="76abb-127">The **Security baseline** card on [device configuration management](configure-machines.md) provides an overview of compliance across Windows 10 devices that have been assigned the Defender for Endpoint security baseline.</span></span>

<span data-ttu-id="76abb-128">![Cartão de linha de base de segurança](images/secconmgmt_baseline_card.png)</span><span class="sxs-lookup"><span data-stu-id="76abb-128">![Security baseline card](images/secconmgmt_baseline_card.png)</span></span><br>
<span data-ttu-id="76abb-129">*Cartão mostrando conformidade com a linha de base de segurança do Defender para Ponto de Extremidade*</span><span class="sxs-lookup"><span data-stu-id="76abb-129">*Card showing compliance to the Defender for Endpoint security baseline*</span></span>

<span data-ttu-id="76abb-130">Cada dispositivo recebe um dos seguintes tipos de status:</span><span class="sxs-lookup"><span data-stu-id="76abb-130">Each device is given one of the following status types:</span></span>

- <span data-ttu-id="76abb-131">**Corresponde à linha** de base — as configurações do dispositivo coincidem com todas as configurações na linha de base</span><span class="sxs-lookup"><span data-stu-id="76abb-131">**Matches baseline**—device settings match all the settings in the baseline</span></span>
- <span data-ttu-id="76abb-132">**Não combina com a linha de** base — pelo menos uma configuração de dispositivo não combina com a linha de base</span><span class="sxs-lookup"><span data-stu-id="76abb-132">**Does not match baseline**—at least one device setting doesn't match the baseline</span></span>
- <span data-ttu-id="76abb-133">**Configurada incorretamente**— pelo menos uma configuração de linha de base não está configurada corretamente no dispositivo e está em conflito, erro ou estado pendente</span><span class="sxs-lookup"><span data-stu-id="76abb-133">**Misconfigured**—at least one baseline setting isn't properly configured on the device and is in a conflict, error, or pending state</span></span>
- <span data-ttu-id="76abb-134">**Não aplicável**— Pelo menos uma configuração de linha de base não é aplicável no dispositivo</span><span class="sxs-lookup"><span data-stu-id="76abb-134">**Not applicable**—At least one baseline setting isn't applicable on the device</span></span>

<span data-ttu-id="76abb-135">Para revisar dispositivos específicos, selecione **Configurar a linha de base de segurança** no cartão.</span><span class="sxs-lookup"><span data-stu-id="76abb-135">To review specific devices, select **Configure security baseline** on the card.</span></span> <span data-ttu-id="76abb-136">Isso o leva ao gerenciamento de dispositivos do Intune.</span><span class="sxs-lookup"><span data-stu-id="76abb-136">This takes you to Intune device management.</span></span> <span data-ttu-id="76abb-137">A partir daí, selecione **Status do dispositivo** para os nomes e status dos dispositivos.</span><span class="sxs-lookup"><span data-stu-id="76abb-137">From there, select **Device status** for the names and statuses of the devices.</span></span>

>[!NOTE]
><span data-ttu-id="76abb-138">Você pode ter discrepâncias nos dados agregados exibidos na página de gerenciamento de configuração do dispositivo e nas telas de visão geral no Intune.</span><span class="sxs-lookup"><span data-stu-id="76abb-138">You might experience discrepancies in aggregated data displayed on the device configuration management page and those displayed on overview screens in Intune.</span></span>

## <a name="review-and-assign-the-microsoft-defender-for-endpoint-security-baseline"></a><span data-ttu-id="76abb-139">Revisar e atribuir a linha de base de segurança do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="76abb-139">Review and assign the Microsoft Defender for Endpoint security baseline</span></span>

<span data-ttu-id="76abb-140">O gerenciamento de configuração de dispositivo monitora apenas a conformidade da linha de base de dispositivos Windows 10 que foram especificamente atribuídos à linha de base de segurança do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="76abb-140">Device configuration management monitors baseline compliance only of Windows 10 devices that have been specifically assigned the Microsoft Defender for Endpoint security baseline.</span></span> <span data-ttu-id="76abb-141">Você pode convenientemente revisar a linha de base e atribuí-la a dispositivos no gerenciamento de dispositivos do Intune.</span><span class="sxs-lookup"><span data-stu-id="76abb-141">You can conveniently review the baseline and assign it to devices on Intune device management.</span></span>

1. <span data-ttu-id="76abb-142">Selecione **Configurar a linha de base de** segurança no cartão de linha de **base** de segurança para ir para o gerenciamento de dispositivos do Intune.</span><span class="sxs-lookup"><span data-stu-id="76abb-142">Select **Configure security baseline** on the **Security baseline** card to go to Intune device management.</span></span> <span data-ttu-id="76abb-143">Uma visão geral semelhante da conformidade da linha de base é exibida.</span><span class="sxs-lookup"><span data-stu-id="76abb-143">A similar overview of baseline compliance is displayed.</span></span>

   >[!TIP]
   > <span data-ttu-id="76abb-144">Como alternativa, você pode navegar até a linha de base de segurança do Defender para Ponto de Extremidade no portal do Microsoft Azure a partir de Todos os serviços **> Intune > Linha** de base de segurança de dispositivo > Segurança > linha de base do Microsoft Defender ATP .</span><span class="sxs-lookup"><span data-stu-id="76abb-144">Alternatively, you can navigate to the Defender for Endpoint security baseline in the Microsoft Azure portal from **All services > Intune > Device security > Security baselines > Microsoft Defender ATP baseline**.</span></span>


2. <span data-ttu-id="76abb-145">Crie um novo perfil.</span><span class="sxs-lookup"><span data-stu-id="76abb-145">Create a new profile.</span></span>

   <span data-ttu-id="76abb-146">![Visão geral da linha de base de segurança do Microsoft Defender para Ponto de Extremidade no Intune](images/secconmgmt_baseline_intuneprofile1.png)</span><span class="sxs-lookup"><span data-stu-id="76abb-146">![Microsoft Defender for Endpoint security baseline overview on Intune](images/secconmgmt_baseline_intuneprofile1.png)</span></span><br>
   <span data-ttu-id="76abb-147">*Visão geral da linha de base de segurança do Microsoft Defender para Ponto de Extremidade no Intune*</span><span class="sxs-lookup"><span data-stu-id="76abb-147">*Microsoft Defender for Endpoint security baseline overview on Intune*</span></span>

3. <span data-ttu-id="76abb-148">Durante a criação de perfil, você pode revisar e ajustar configurações específicas na linha de base.</span><span class="sxs-lookup"><span data-stu-id="76abb-148">During profile creation, you can review and adjust specific settings on the baseline.</span></span>

   <span data-ttu-id="76abb-149">![Opções de linha de base de segurança durante a criação de perfil no Intune](images/secconmgmt_baseline_intuneprofile2.png)</span><span class="sxs-lookup"><span data-stu-id="76abb-149">![Security baseline options during profile creation on Intune](images/secconmgmt_baseline_intuneprofile2.png)</span></span><br>
   <span data-ttu-id="76abb-150">*Opções de linha de base de segurança durante a criação de perfil no Intune*</span><span class="sxs-lookup"><span data-stu-id="76abb-150">*Security baseline options during profile creation on Intune*</span></span>

4. <span data-ttu-id="76abb-151">Atribua o perfil ao grupo de dispositivos apropriado.</span><span class="sxs-lookup"><span data-stu-id="76abb-151">Assign the profile to the appropriate device group.</span></span>

   <span data-ttu-id="76abb-152">![Perfis de linha de base de segurança no Intune](images/secconmgmt_baseline_intuneprofile3.png)</span><span class="sxs-lookup"><span data-stu-id="76abb-152">![Security baseline profiles on Intune](images/secconmgmt_baseline_intuneprofile3.png)</span></span><br>
   <span data-ttu-id="76abb-153">*Atribuindo o perfil de linha de base de segurança no Intune*</span><span class="sxs-lookup"><span data-stu-id="76abb-153">*Assigning the security baseline profile on Intune*</span></span>

5. <span data-ttu-id="76abb-154">Crie o perfil para salvá-lo e implantá-lo no grupo de dispositivos atribuído.</span><span class="sxs-lookup"><span data-stu-id="76abb-154">Create the profile to save it and deploy it to the assigned device group.</span></span>

   <span data-ttu-id="76abb-155">![Atribuindo a linha de base de segurança no Intune](images/secconmgmt_baseline_intuneprofile4.png)</span><span class="sxs-lookup"><span data-stu-id="76abb-155">![Assigning the security baseline on Intune](images/secconmgmt_baseline_intuneprofile4.png)</span></span><br>
   <span data-ttu-id="76abb-156">*Criando o perfil de linha de base de segurança no Intune*</span><span class="sxs-lookup"><span data-stu-id="76abb-156">*Creating the security baseline profile on Intune*</span></span>

>[!TIP]
><span data-ttu-id="76abb-157">As linhas de base de segurança no Intune fornecem uma maneira conveniente de proteger e proteger seus dispositivos de forma abrangente.</span><span class="sxs-lookup"><span data-stu-id="76abb-157">Security baselines on Intune provide a convenient way to comprehensively secure and protect your devices.</span></span> <span data-ttu-id="76abb-158">[Saiba mais sobre linhas de base de segurança no Intune](https://docs.microsoft.com/intune/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="76abb-158">[Learn more about security baselines on Intune](https://docs.microsoft.com/intune/security-baselines).</span></span>

><span data-ttu-id="76abb-159">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="76abb-159">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="76abb-160">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="76abb-160">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="76abb-161">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="76abb-161">Related topics</span></span>
- [<span data-ttu-id="76abb-162">Verificar se os dispositivos estão configurados corretamente</span><span class="sxs-lookup"><span data-stu-id="76abb-162">Ensure your devices are configured properly</span></span>](configure-machines.md)
- [<span data-ttu-id="76abb-163">Obter dispositivos conectados ao Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="76abb-163">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
- [<span data-ttu-id="76abb-164">Otimizar a implantação e as detecções de regras ASR</span><span class="sxs-lookup"><span data-stu-id="76abb-164">Optimize ASR rule deployment and detections</span></span>](configure-machines-asr.md)
